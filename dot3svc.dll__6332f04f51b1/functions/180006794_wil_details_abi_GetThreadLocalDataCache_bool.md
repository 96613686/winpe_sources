# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006794`
- end: `0x180006851`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006090`

## callees

- `0x180005788`
- `0x180006794`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ee`

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
0x180006794  mov     [rsp+arg_0], rbx
0x180006799  push    rdi
0x18000679a  sub     rsp, 20h
0x18000679e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800067a5  xor     ebx, ebx
0x1800067a7  test    rdi, rdi
0x1800067aa  jz      loc_180006843
0x1800067b0  cmp     [rdi+8], rbx
0x1800067b4  jnz     short loc_1800067DB
0x1800067b6  mov     rcx, [rdi]
0x1800067b9  lea     rdx, [rsp+28h+arg_8]
0x1800067be  mov     [rsp+28h+arg_8], rbx
0x1800067c3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800067c8  test    eax, eax
0x1800067ca  js      short loc_1800067DB
0x1800067cc  cmp     [rdi+8], rbx
0x1800067d0  jnz     short loc_1800067DB
0x1800067d2  mov     rax, [rsp+28h+arg_8]
0x1800067d7  mov     [rdi+8], rax
0x1800067db  mov     rax, [rdi+8]
0x1800067df  lea     rcx, [rax+20h]
0x1800067e3  neg     rax
0x1800067e6  sbb     rdi, rdi
0x1800067e9  and     rdi, rcx
0x1800067ec  jz      short loc_180006843
0x1800067ee  call    cs:__imp_GetCurrentThreadId
0x1800067f4  mov     r8d, eax
0x1800067f7  mov     r9d, eax
0x1800067fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006804  shr     r8, 2
0x180006808  mul     r8
0x18000680b  shr     rdx, 3
0x18000680f  lea     rcx, [rdx+rdx*4]
0x180006813  add     rcx, rcx
0x180006816  sub     r8, rcx
0x180006819  mov     rbx, [rdi+r8*8+8]
0x18000681e  test    rbx, rbx
0x180006821  jz      short loc_180006843
0x180006823  cmp     [rbx], r9d
0x180006826  jz      short loc_18000682E
0x180006828  mov     rbx, [rbx+8]
0x18000682c  jmp     short loc_18000681E
0x18000682e  add     rbx, 10h
0x180006832  jz      short loc_180006843
0x180006834  cmp     qword ptr [rbx+8], 0
0x180006839  jnz     short loc_180006843
0x18000683b  lea     rax, [rdi+4]
0x18000683f  mov     [rbx+8], rax
0x180006843  mov     rax, rbx
0x180006846  mov     rbx, [rsp+28h+arg_0]
0x18000684b  add     rsp, 20h
0x18000684f  pop     rdi
0x180006850  retn
```
