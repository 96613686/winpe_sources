# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800045c0`
- end: `0x18000467b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003de0`

## callees

- `0x180003734`
- `0x1800045c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004616`

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
0x1800045c0  mov     [rsp+arg_0], rbx
0x1800045c5  push    rdi
0x1800045c6  sub     rsp, 20h
0x1800045ca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800045d1  xor     ebx, ebx
0x1800045d3  test    rdi, rdi
0x1800045d6  jz      short loc_180004656
0x1800045d8  cmp     [rdi+8], rbx
0x1800045dc  jnz     short loc_180004603
0x1800045de  mov     rcx, [rdi]
0x1800045e1  lea     rdx, [rsp+28h+arg_8]
0x1800045e6  mov     [rsp+28h+arg_8], rbx
0x1800045eb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800045f0  test    eax, eax
0x1800045f2  js      short loc_180004603
0x1800045f4  cmp     [rdi+8], rbx
0x1800045f8  jnz     short loc_180004603
0x1800045fa  mov     rax, [rsp+28h+arg_8]
0x1800045ff  mov     [rdi+8], rax
0x180004603  mov     rax, [rdi+8]
0x180004607  lea     rcx, [rax+20h]
0x18000460b  neg     rax
0x18000460e  sbb     rdi, rdi
0x180004611  and     rdi, rcx
0x180004614  jz      short loc_180004656
0x180004616  call    cs:__imp_GetCurrentThreadId
0x18000461c  mov     r8d, eax
0x18000461f  mov     r9d, eax
0x180004622  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000462c  shr     r8, 2
0x180004630  mul     r8
0x180004633  shr     rdx, 3
0x180004637  lea     rcx, [rdx+rdx*4]
0x18000463b  add     rcx, rcx
0x18000463e  sub     r8, rcx
0x180004641  mov     rbx, [rdi+r8*8+8]
0x180004646  jmp     short loc_180004651
0x180004648  cmp     [rbx], r9d
0x18000464b  jz      short loc_180004664
0x18000464d  mov     rbx, [rbx+8]
0x180004651  test    rbx, rbx
0x180004654  jnz     short loc_180004648
0x180004656  mov     rax, rbx
0x180004659  mov     rbx, [rsp+28h+arg_0]
0x18000465e  add     rsp, 20h
0x180004662  pop     rdi
0x180004663  retn
0x180004664  add     rbx, 10h
0x180004668  jz      short loc_180004656
0x18000466a  cmp     qword ptr [rbx+8], 0
0x18000466f  jnz     short loc_180004656
0x180004671  lea     rax, [rdi+4]
0x180004675  mov     [rbx+8], rax
0x180004679  jmp     short loc_180004656
```
