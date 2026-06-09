# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800064b4`
- end: `0x18000656f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d40`

## callees

- `0x180004d50`
- `0x1800064b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000650a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000650a`

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
0x1800064b4  mov     [rsp+arg_0], rbx
0x1800064b9  push    rdi
0x1800064ba  sub     rsp, 20h
0x1800064be  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800064c5  xor     ebx, ebx
0x1800064c7  test    rdi, rdi
0x1800064ca  jz      short loc_18000654A
0x1800064cc  cmp     [rdi+8], rbx
0x1800064d0  jnz     short loc_1800064F7
0x1800064d2  mov     rcx, [rdi]
0x1800064d5  lea     rdx, [rsp+28h+arg_8]
0x1800064da  mov     [rsp+28h+arg_8], rbx
0x1800064df  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800064e4  test    eax, eax
0x1800064e6  js      short loc_1800064F7
0x1800064e8  cmp     [rdi+8], rbx
0x1800064ec  jnz     short loc_1800064F7
0x1800064ee  mov     rax, [rsp+28h+arg_8]
0x1800064f3  mov     [rdi+8], rax
0x1800064f7  mov     rax, [rdi+8]
0x1800064fb  lea     rcx, [rax+20h]
0x1800064ff  neg     rax
0x180006502  sbb     rdi, rdi
0x180006505  and     rdi, rcx
0x180006508  jz      short loc_18000654A
0x18000650a  call    cs:__imp_GetCurrentThreadId
0x180006510  mov     r8d, eax
0x180006513  mov     r9d, eax
0x180006516  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006520  shr     r8, 2
0x180006524  mul     r8
0x180006527  shr     rdx, 3
0x18000652b  lea     rcx, [rdx+rdx*4]
0x18000652f  add     rcx, rcx
0x180006532  sub     r8, rcx
0x180006535  mov     rbx, [rdi+r8*8+8]
0x18000653a  jmp     short loc_180006545
0x18000653c  cmp     [rbx], r9d
0x18000653f  jz      short loc_180006558
0x180006541  mov     rbx, [rbx+8]
0x180006545  test    rbx, rbx
0x180006548  jnz     short loc_18000653C
0x18000654a  mov     rax, rbx
0x18000654d  mov     rbx, [rsp+28h+arg_0]
0x180006552  add     rsp, 20h
0x180006556  pop     rdi
0x180006557  retn
0x180006558  add     rbx, 10h
0x18000655c  jz      short loc_18000654A
0x18000655e  cmp     qword ptr [rbx+8], 0
0x180006563  jnz     short loc_18000654A
0x180006565  lea     rax, [rdi+4]
0x180006569  mov     [rbx+8], rax
0x18000656d  jmp     short loc_18000654A
```
