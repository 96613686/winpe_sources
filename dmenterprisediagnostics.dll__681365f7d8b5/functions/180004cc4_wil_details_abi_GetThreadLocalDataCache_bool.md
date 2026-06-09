# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004cc4`
- end: `0x180004d88`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004610`

## callees

- `0x180003d2c`
- `0x180004cc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d1e`

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
0x180004cc4  mov     [rsp+arg_0], rbx
0x180004cc9  push    rdi
0x180004cca  sub     rsp, 20h
0x180004cce  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004cd5  xor     ebx, ebx
0x180004cd7  test    rdi, rdi
0x180004cda  jz      loc_180004D79
0x180004ce0  cmp     [rdi+8], rbx
0x180004ce4  jnz     short loc_180004D0B
0x180004ce6  mov     rcx, [rdi]
0x180004ce9  lea     rdx, [rsp+28h+arg_8]
0x180004cee  mov     [rsp+28h+arg_8], rbx
0x180004cf3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004cf8  test    eax, eax
0x180004cfa  js      short loc_180004D0B
0x180004cfc  cmp     [rdi+8], rbx
0x180004d00  jnz     short loc_180004D0B
0x180004d02  mov     rax, [rsp+28h+arg_8]
0x180004d07  mov     [rdi+8], rax
0x180004d0b  mov     rax, [rdi+8]
0x180004d0f  lea     rcx, [rax+20h]
0x180004d13  neg     rax
0x180004d16  sbb     rdi, rdi
0x180004d19  and     rdi, rcx
0x180004d1c  jz      short loc_180004D79
0x180004d1e  call    cs:__imp_GetCurrentThreadId
0x180004d25  nop     dword ptr [rax+rax+00h]
0x180004d2a  mov     r8d, eax
0x180004d2d  mov     r9d, eax
0x180004d30  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004d3a  shr     r8, 2
0x180004d3e  mul     r8
0x180004d41  shr     rdx, 3
0x180004d45  lea     rcx, [rdx+rdx*4]
0x180004d49  add     rcx, rcx
0x180004d4c  sub     r8, rcx
0x180004d4f  mov     rbx, [rdi+r8*8+8]
0x180004d54  test    rbx, rbx
0x180004d57  jz      short loc_180004D79
0x180004d59  cmp     [rbx], r9d
0x180004d5c  jz      short loc_180004D64
0x180004d5e  mov     rbx, [rbx+8]
0x180004d62  jmp     short loc_180004D54
0x180004d64  add     rbx, 10h
0x180004d68  jz      short loc_180004D79
0x180004d6a  cmp     qword ptr [rbx+8], 0
0x180004d6f  jnz     short loc_180004D79
0x180004d71  lea     rax, [rdi+4]
0x180004d75  mov     [rbx+8], rax
0x180004d79  mov     rax, rbx
0x180004d7c  mov     rbx, [rsp+28h+arg_0]
0x180004d81  add     rsp, 20h
0x180004d85  pop     rdi
0x180004d86  retn
```
