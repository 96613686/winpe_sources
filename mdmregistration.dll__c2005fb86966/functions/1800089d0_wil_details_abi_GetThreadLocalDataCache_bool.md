# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800089d0`
- end: `0x180008a96`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008220`

## callees

- `0x18000717c`
- `0x1800089d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a2a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

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
0x1800089d0  mov     [rsp+arg_0], rbx
0x1800089d5  push    rdi
0x1800089d6  sub     rsp, 20h
0x1800089da  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800089e1  xor     ebx, ebx
0x1800089e3  test    rdi, rdi
0x1800089e6  jz      loc_180008A70
0x1800089ec  cmp     [rdi+8], rbx
0x1800089f0  jnz     short loc_180008A17
0x1800089f2  mov     rcx, [rdi]
0x1800089f5  lea     rdx, [rsp+28h+arg_8]
0x1800089fa  mov     [rsp+28h+arg_8], rbx
0x1800089ff  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008a04  test    eax, eax
0x180008a06  js      short loc_180008A17
0x180008a08  cmp     [rdi+8], rbx
0x180008a0c  jnz     short loc_180008A17
0x180008a0e  mov     rax, [rsp+28h+arg_8]
0x180008a13  mov     [rdi+8], rax
0x180008a17  mov     rax, [rdi+8]
0x180008a1b  lea     rcx, [rax+20h]
0x180008a1f  neg     rax
0x180008a22  sbb     rdi, rdi
0x180008a25  and     rdi, rcx
0x180008a28  jz      short loc_180008A70
0x180008a2a  call    cs:__imp_GetCurrentThreadId
0x180008a31  nop     dword ptr [rax+rax+00h]
0x180008a36  mov     r8d, eax
0x180008a39  mov     r9d, eax
0x180008a3c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008a46  shr     r8, 2
0x180008a4a  mul     r8
0x180008a4d  shr     rdx, 3
0x180008a51  lea     rcx, [rdx+rdx*4]
0x180008a55  add     rcx, rcx
0x180008a58  sub     r8, rcx
0x180008a5b  mov     rbx, [rdi+r8*8+8]
0x180008a60  jmp     short loc_180008A6B
0x180008a62  cmp     [rbx], r9d
0x180008a65  jz      short loc_180008A7F
0x180008a67  mov     rbx, [rbx+8]
0x180008a6b  test    rbx, rbx
0x180008a6e  jnz     short loc_180008A62
0x180008a70  mov     rax, rbx
0x180008a73  mov     rbx, [rsp+28h+arg_0]
0x180008a78  add     rsp, 20h
0x180008a7c  pop     rdi
0x180008a7d  retn
0x180008a7f  add     rbx, 10h
0x180008a83  jz      short loc_180008A70
0x180008a85  cmp     qword ptr [rbx+8], 0
0x180008a8a  jnz     short loc_180008A70
0x180008a8c  lea     rax, [rdi+4]
0x180008a90  mov     [rbx+8], rax
0x180008a94  jmp     short loc_180008A70
```
