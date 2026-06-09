# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004880`
- end: `0x18000493d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042e0`

## callees

- `0x180003890`
- `0x180004880`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800048da`
- `KERNEL32!GetCurrentThreadId` at `0x1800048da`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180004880  mov     [rsp+arg_0], rbx
0x180004885  push    rdi
0x180004886  sub     rsp, 20h
0x18000488a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004891  xor     ebx, ebx
0x180004893  test    rdi, rdi
0x180004896  jz      loc_18000492F
0x18000489c  cmp     [rdi+8], rbx
0x1800048a0  jnz     short loc_1800048C7
0x1800048a2  mov     rcx, [rdi]
0x1800048a5  lea     rdx, [rsp+28h+arg_8]
0x1800048aa  mov     [rsp+28h+arg_8], rbx
0x1800048af  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800048b4  test    eax, eax
0x1800048b6  js      short loc_1800048C7
0x1800048b8  cmp     [rdi+8], rbx
0x1800048bc  jnz     short loc_1800048C7
0x1800048be  mov     rax, [rsp+28h+arg_8]
0x1800048c3  mov     [rdi+8], rax
0x1800048c7  mov     rax, [rdi+8]
0x1800048cb  lea     rcx, [rax+20h]
0x1800048cf  neg     rax
0x1800048d2  sbb     rdi, rdi
0x1800048d5  and     rdi, rcx
0x1800048d8  jz      short loc_18000492F
0x1800048da  call    cs:__imp_GetCurrentThreadId
0x1800048e0  mov     r8d, eax
0x1800048e3  mov     r9d, eax
0x1800048e6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800048f0  shr     r8, 2
0x1800048f4  mul     r8
0x1800048f7  shr     rdx, 3
0x1800048fb  lea     rcx, [rdx+rdx*4]
0x1800048ff  add     rcx, rcx
0x180004902  sub     r8, rcx
0x180004905  mov     rbx, [rdi+r8*8+8]
0x18000490a  test    rbx, rbx
0x18000490d  jz      short loc_18000492F
0x18000490f  cmp     [rbx], r9d
0x180004912  jz      short loc_18000491A
0x180004914  mov     rbx, [rbx+8]
0x180004918  jmp     short loc_18000490A
0x18000491a  add     rbx, 10h
0x18000491e  jz      short loc_18000492F
0x180004920  cmp     qword ptr [rbx+8], 0
0x180004925  jnz     short loc_18000492F
0x180004927  lea     rax, [rdi+4]
0x18000492b  mov     [rbx+8], rax
0x18000492f  mov     rax, rbx
0x180004932  mov     rbx, [rsp+28h+arg_0]
0x180004937  add     rsp, 20h
0x18000493b  pop     rdi
0x18000493c  retn
```
