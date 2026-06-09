# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000917c`
- end: `0x180009239`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008b20`

## callees

- `0x180004d28`
- `0x18000917c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800091d6`
- `KERNEL32!GetCurrentThreadId` at `0x1800091d6`

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
0x18000917c  mov     [rsp+arg_0], rbx
0x180009181  push    rdi
0x180009182  sub     rsp, 20h
0x180009186  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000918d  xor     ebx, ebx
0x18000918f  test    rdi, rdi
0x180009192  jz      loc_18000922B
0x180009198  cmp     [rdi+8], rbx
0x18000919c  jnz     short loc_1800091C3
0x18000919e  mov     rcx, [rdi]
0x1800091a1  lea     rdx, [rsp+28h+arg_8]
0x1800091a6  mov     [rsp+28h+arg_8], rbx
0x1800091ab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800091b0  test    eax, eax
0x1800091b2  js      short loc_1800091C3
0x1800091b4  cmp     [rdi+8], rbx
0x1800091b8  jnz     short loc_1800091C3
0x1800091ba  mov     rax, [rsp+28h+arg_8]
0x1800091bf  mov     [rdi+8], rax
0x1800091c3  mov     rax, [rdi+8]
0x1800091c7  lea     rcx, [rax+20h]
0x1800091cb  neg     rax
0x1800091ce  sbb     rdi, rdi
0x1800091d1  and     rdi, rcx
0x1800091d4  jz      short loc_18000922B
0x1800091d6  call    cs:__imp_GetCurrentThreadId
0x1800091dc  mov     r8d, eax
0x1800091df  mov     r9d, eax
0x1800091e2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800091ec  shr     r8, 2
0x1800091f0  mul     r8
0x1800091f3  shr     rdx, 3
0x1800091f7  lea     rcx, [rdx+rdx*4]
0x1800091fb  add     rcx, rcx
0x1800091fe  sub     r8, rcx
0x180009201  mov     rbx, [rdi+r8*8+8]
0x180009206  test    rbx, rbx
0x180009209  jz      short loc_18000922B
0x18000920b  cmp     [rbx], r9d
0x18000920e  jz      short loc_180009216
0x180009210  mov     rbx, [rbx+8]
0x180009214  jmp     short loc_180009206
0x180009216  add     rbx, 10h
0x18000921a  jz      short loc_18000922B
0x18000921c  cmp     qword ptr [rbx+8], 0
0x180009221  jnz     short loc_18000922B
0x180009223  lea     rax, [rdi+4]
0x180009227  mov     [rbx+8], rax
0x18000922b  mov     rax, rbx
0x18000922e  mov     rbx, [rsp+28h+arg_0]
0x180009233  add     rsp, 20h
0x180009237  pop     rdi
0x180009238  retn
```
