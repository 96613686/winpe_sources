# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180052848`
- end: `0x180052905`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180051f00`

## callees

- `0x18005138c`
- `0x180052848`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800528a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800528a2`

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
0x180052848  mov     [rsp+arg_0], rbx
0x18005284d  push    rdi
0x18005284e  sub     rsp, 20h
0x180052852  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180052859  xor     ebx, ebx
0x18005285b  test    rdi, rdi
0x18005285e  jz      loc_1800528F7
0x180052864  cmp     [rdi+8], rbx
0x180052868  jnz     short loc_18005288F
0x18005286a  mov     rcx, [rdi]
0x18005286d  lea     rdx, [rsp+28h+arg_8]
0x180052872  mov     [rsp+28h+arg_8], rbx
0x180052877  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18005287c  test    eax, eax
0x18005287e  js      short loc_18005288F
0x180052880  cmp     [rdi+8], rbx
0x180052884  jnz     short loc_18005288F
0x180052886  mov     rax, [rsp+28h+arg_8]
0x18005288b  mov     [rdi+8], rax
0x18005288f  mov     rax, [rdi+8]
0x180052893  lea     rcx, [rax+20h]
0x180052897  neg     rax
0x18005289a  sbb     rdi, rdi
0x18005289d  and     rdi, rcx
0x1800528a0  jz      short loc_1800528F7
0x1800528a2  call    cs:__imp_GetCurrentThreadId
0x1800528a8  mov     r8d, eax
0x1800528ab  mov     r9d, eax
0x1800528ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800528b8  shr     r8, 2
0x1800528bc  mul     r8
0x1800528bf  shr     rdx, 3
0x1800528c3  lea     rcx, [rdx+rdx*4]
0x1800528c7  add     rcx, rcx
0x1800528ca  sub     r8, rcx
0x1800528cd  mov     rbx, [rdi+r8*8+8]
0x1800528d2  test    rbx, rbx
0x1800528d5  jz      short loc_1800528F7
0x1800528d7  cmp     [rbx], r9d
0x1800528da  jz      short loc_1800528E2
0x1800528dc  mov     rbx, [rbx+8]
0x1800528e0  jmp     short loc_1800528D2
0x1800528e2  add     rbx, 10h
0x1800528e6  jz      short loc_1800528F7
0x1800528e8  cmp     qword ptr [rbx+8], 0
0x1800528ed  jnz     short loc_1800528F7
0x1800528ef  lea     rax, [rdi+4]
0x1800528f3  mov     [rbx+8], rax
0x1800528f7  mov     rax, rbx
0x1800528fa  mov     rbx, [rsp+28h+arg_0]
0x1800528ff  add     rsp, 20h
0x180052903  pop     rdi
0x180052904  retn
```
