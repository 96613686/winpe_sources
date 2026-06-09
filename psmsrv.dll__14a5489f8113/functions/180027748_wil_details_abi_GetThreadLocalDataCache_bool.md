# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180027748`
- end: `0x180027805`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800270e0`

## callees

- `0x180026724`
- `0x180027748`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800277a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800277a2`

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
0x180027748  mov     [rsp+arg_0], rbx
0x18002774d  push    rdi
0x18002774e  sub     rsp, 20h
0x180027752  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180027759  xor     ebx, ebx
0x18002775b  test    rdi, rdi
0x18002775e  jz      loc_1800277F7
0x180027764  cmp     [rdi+8], rbx
0x180027768  jnz     short loc_18002778F
0x18002776a  mov     rcx, [rdi]
0x18002776d  lea     rdx, [rsp+28h+arg_8]
0x180027772  mov     [rsp+28h+arg_8], rbx
0x180027777  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002777c  test    eax, eax
0x18002777e  js      short loc_18002778F
0x180027780  cmp     [rdi+8], rbx
0x180027784  jnz     short loc_18002778F
0x180027786  mov     rax, [rsp+28h+arg_8]
0x18002778b  mov     [rdi+8], rax
0x18002778f  mov     rax, [rdi+8]
0x180027793  lea     rcx, [rax+20h]
0x180027797  neg     rax
0x18002779a  sbb     rdi, rdi
0x18002779d  and     rdi, rcx
0x1800277a0  jz      short loc_1800277F7
0x1800277a2  call    cs:__imp_GetCurrentThreadId
0x1800277a8  mov     r8d, eax
0x1800277ab  mov     r9d, eax
0x1800277ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800277b8  shr     r8, 2
0x1800277bc  mul     r8
0x1800277bf  shr     rdx, 3
0x1800277c3  lea     rcx, [rdx+rdx*4]
0x1800277c7  add     rcx, rcx
0x1800277ca  sub     r8, rcx
0x1800277cd  mov     rbx, [rdi+r8*8+8]
0x1800277d2  test    rbx, rbx
0x1800277d5  jz      short loc_1800277F7
0x1800277d7  cmp     [rbx], r9d
0x1800277da  jz      short loc_1800277E2
0x1800277dc  mov     rbx, [rbx+8]
0x1800277e0  jmp     short loc_1800277D2
0x1800277e2  add     rbx, 10h
0x1800277e6  jz      short loc_1800277F7
0x1800277e8  cmp     qword ptr [rbx+8], 0
0x1800277ed  jnz     short loc_1800277F7
0x1800277ef  lea     rax, [rdi+4]
0x1800277f3  mov     [rbx+8], rax
0x1800277f7  mov     rax, rbx
0x1800277fa  mov     rbx, [rsp+28h+arg_0]
0x1800277ff  add     rsp, 20h
0x180027803  pop     rdi
0x180027804  retn
```
