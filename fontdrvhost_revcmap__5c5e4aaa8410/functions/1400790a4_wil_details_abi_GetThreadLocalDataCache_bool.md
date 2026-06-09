# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400790a4`
- end: `0x140079161`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400789a0`

## callees

- `0x140078088`
- `0x1400790a4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400790fe`
- `KERNEL32!GetCurrentThreadId` at `0x1400790fe`

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
0x1400790a4  mov     [rsp+arg_0], rbx
0x1400790a9  push    rdi
0x1400790aa  sub     rsp, 20h
0x1400790ae  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400790b5  xor     ebx, ebx
0x1400790b7  test    rdi, rdi
0x1400790ba  jz      loc_140079153
0x1400790c0  cmp     [rdi+8], rbx
0x1400790c4  jnz     short loc_1400790EB
0x1400790c6  mov     rcx, [rdi]
0x1400790c9  lea     rdx, [rsp+28h+arg_8]
0x1400790ce  mov     [rsp+28h+arg_8], rbx
0x1400790d3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400790d8  test    eax, eax
0x1400790da  js      short loc_1400790EB
0x1400790dc  cmp     [rdi+8], rbx
0x1400790e0  jnz     short loc_1400790EB
0x1400790e2  mov     rax, [rsp+28h+arg_8]
0x1400790e7  mov     [rdi+8], rax
0x1400790eb  mov     rax, [rdi+8]
0x1400790ef  lea     rcx, [rax+20h]
0x1400790f3  neg     rax
0x1400790f6  sbb     rdi, rdi
0x1400790f9  and     rdi, rcx
0x1400790fc  jz      short loc_140079153
0x1400790fe  call    cs:__imp_GetCurrentThreadId
0x140079104  mov     r8d, eax
0x140079107  mov     r9d, eax
0x14007910a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140079114  shr     r8, 2
0x140079118  mul     r8
0x14007911b  shr     rdx, 3
0x14007911f  lea     rcx, [rdx+rdx*4]
0x140079123  add     rcx, rcx
0x140079126  sub     r8, rcx
0x140079129  mov     rbx, [rdi+r8*8+8]
0x14007912e  test    rbx, rbx
0x140079131  jz      short loc_140079153
0x140079133  cmp     [rbx], r9d
0x140079136  jz      short loc_14007913E
0x140079138  mov     rbx, [rbx+8]
0x14007913c  jmp     short loc_14007912E
0x14007913e  add     rbx, 10h
0x140079142  jz      short loc_140079153
0x140079144  cmp     qword ptr [rbx+8], 0
0x140079149  jnz     short loc_140079153
0x14007914b  lea     rax, [rdi+4]
0x14007914f  mov     [rbx+8], rax
0x140079153  mov     rax, rbx
0x140079156  mov     rbx, [rsp+28h+arg_0]
0x14007915b  add     rsp, 20h
0x14007915f  pop     rdi
0x140079160  retn
```
