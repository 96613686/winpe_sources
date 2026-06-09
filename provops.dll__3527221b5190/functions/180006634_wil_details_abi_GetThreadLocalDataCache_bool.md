# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006634`
- end: `0x1800066ef`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e10`

## callees

- `0x180005480`
- `0x180006634`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000668a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000668a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006634  mov     [rsp+arg_0], rbx
0x180006639  push    rdi
0x18000663a  sub     rsp, 20h
0x18000663e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006645  xor     ebx, ebx
0x180006647  test    rdi, rdi
0x18000664a  jz      short loc_1800066CA
0x18000664c  cmp     [rdi+8], rbx
0x180006650  jnz     short loc_180006677
0x180006652  mov     rcx, [rdi]
0x180006655  lea     rdx, [rsp+28h+arg_8]
0x18000665a  mov     [rsp+28h+arg_8], rbx
0x18000665f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006664  test    eax, eax
0x180006666  js      short loc_180006677
0x180006668  cmp     [rdi+8], rbx
0x18000666c  jnz     short loc_180006677
0x18000666e  mov     rax, [rsp+28h+arg_8]
0x180006673  mov     [rdi+8], rax
0x180006677  mov     rax, [rdi+8]
0x18000667b  lea     rcx, [rax+20h]
0x18000667f  neg     rax
0x180006682  sbb     rdi, rdi
0x180006685  and     rdi, rcx
0x180006688  jz      short loc_1800066CA
0x18000668a  call    cs:__imp_GetCurrentThreadId
0x180006690  mov     r8d, eax
0x180006693  mov     r9d, eax
0x180006696  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800066a0  shr     r8, 2
0x1800066a4  mul     r8
0x1800066a7  shr     rdx, 3
0x1800066ab  lea     rcx, [rdx+rdx*4]
0x1800066af  add     rcx, rcx
0x1800066b2  sub     r8, rcx
0x1800066b5  mov     rbx, [rdi+r8*8+8]
0x1800066ba  jmp     short loc_1800066C5
0x1800066bc  cmp     [rbx], r9d
0x1800066bf  jz      short loc_1800066D8
0x1800066c1  mov     rbx, [rbx+8]
0x1800066c5  test    rbx, rbx
0x1800066c8  jnz     short loc_1800066BC
0x1800066ca  mov     rax, rbx
0x1800066cd  mov     rbx, [rsp+28h+arg_0]
0x1800066d2  add     rsp, 20h
0x1800066d6  pop     rdi
0x1800066d7  retn
0x1800066d8  add     rbx, 10h
0x1800066dc  jz      short loc_1800066CA
0x1800066de  cmp     qword ptr [rbx+8], 0
0x1800066e3  jnz     short loc_1800066CA
0x1800066e5  lea     rax, [rdi+4]
0x1800066e9  mov     [rbx+8], rax
0x1800066ed  jmp     short loc_1800066CA
```
