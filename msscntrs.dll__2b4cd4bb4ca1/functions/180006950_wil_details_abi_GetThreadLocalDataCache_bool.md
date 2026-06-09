# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006950`
- end: `0x180006a0b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006170`

## callees

- `0x1800050b8`
- `0x180006950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069a6`

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
0x180006950  mov     [rsp+arg_0], rbx
0x180006955  push    rdi
0x180006956  sub     rsp, 20h
0x18000695a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006961  xor     ebx, ebx
0x180006963  test    rdi, rdi
0x180006966  jz      short loc_1800069E6
0x180006968  cmp     [rdi+8], rbx
0x18000696c  jnz     short loc_180006993
0x18000696e  mov     rcx, [rdi]
0x180006971  lea     rdx, [rsp+28h+arg_8]
0x180006976  mov     [rsp+28h+arg_8], rbx
0x18000697b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006980  test    eax, eax
0x180006982  js      short loc_180006993
0x180006984  cmp     [rdi+8], rbx
0x180006988  jnz     short loc_180006993
0x18000698a  mov     rax, [rsp+28h+arg_8]
0x18000698f  mov     [rdi+8], rax
0x180006993  mov     rax, [rdi+8]
0x180006997  lea     rcx, [rax+20h]
0x18000699b  neg     rax
0x18000699e  sbb     rdi, rdi
0x1800069a1  and     rdi, rcx
0x1800069a4  jz      short loc_1800069E6
0x1800069a6  call    cs:__imp_GetCurrentThreadId
0x1800069ac  mov     r8d, eax
0x1800069af  mov     r9d, eax
0x1800069b2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800069bc  shr     r8, 2
0x1800069c0  mul     r8
0x1800069c3  shr     rdx, 3
0x1800069c7  lea     rcx, [rdx+rdx*4]
0x1800069cb  add     rcx, rcx
0x1800069ce  sub     r8, rcx
0x1800069d1  mov     rbx, [rdi+r8*8+8]
0x1800069d6  jmp     short loc_1800069E1
0x1800069d8  cmp     [rbx], r9d
0x1800069db  jz      short loc_1800069F4
0x1800069dd  mov     rbx, [rbx+8]
0x1800069e1  test    rbx, rbx
0x1800069e4  jnz     short loc_1800069D8
0x1800069e6  mov     rax, rbx
0x1800069e9  mov     rbx, [rsp+28h+arg_0]
0x1800069ee  add     rsp, 20h
0x1800069f2  pop     rdi
0x1800069f3  retn
0x1800069f4  add     rbx, 10h
0x1800069f8  jz      short loc_1800069E6
0x1800069fa  cmp     qword ptr [rbx+8], 0
0x1800069ff  jnz     short loc_1800069E6
0x180006a01  lea     rax, [rdi+4]
0x180006a05  mov     [rbx+8], rax
0x180006a09  jmp     short loc_1800069E6
```
