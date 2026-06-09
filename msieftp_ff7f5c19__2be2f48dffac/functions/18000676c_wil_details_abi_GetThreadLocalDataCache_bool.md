# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000676c`
- end: `0x180006827`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e40`

## callees

- `0x18000443c`
- `0x18000676c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067c2`

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
0x18000676c  mov     [rsp+arg_0], rbx
0x180006771  push    rdi
0x180006772  sub     rsp, 20h
0x180006776  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000677d  xor     ebx, ebx
0x18000677f  test    rdi, rdi
0x180006782  jz      short loc_180006802
0x180006784  cmp     [rdi+8], rbx
0x180006788  jnz     short loc_1800067AF
0x18000678a  mov     rcx, [rdi]
0x18000678d  lea     rdx, [rsp+28h+arg_8]
0x180006792  mov     [rsp+28h+arg_8], rbx
0x180006797  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000679c  test    eax, eax
0x18000679e  js      short loc_1800067AF
0x1800067a0  cmp     [rdi+8], rbx
0x1800067a4  jnz     short loc_1800067AF
0x1800067a6  mov     rax, [rsp+28h+arg_8]
0x1800067ab  mov     [rdi+8], rax
0x1800067af  mov     rax, [rdi+8]
0x1800067b3  lea     rcx, [rax+20h]
0x1800067b7  neg     rax
0x1800067ba  sbb     rdi, rdi
0x1800067bd  and     rdi, rcx
0x1800067c0  jz      short loc_180006802
0x1800067c2  call    cs:__imp_GetCurrentThreadId
0x1800067c8  mov     r8d, eax
0x1800067cb  mov     r9d, eax
0x1800067ce  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800067d8  shr     r8, 2
0x1800067dc  mul     r8
0x1800067df  shr     rdx, 3
0x1800067e3  lea     rcx, [rdx+rdx*4]
0x1800067e7  add     rcx, rcx
0x1800067ea  sub     r8, rcx
0x1800067ed  mov     rbx, [rdi+r8*8+8]
0x1800067f2  jmp     short loc_1800067FD
0x1800067f4  cmp     [rbx], r9d
0x1800067f7  jz      short loc_180006810
0x1800067f9  mov     rbx, [rbx+8]
0x1800067fd  test    rbx, rbx
0x180006800  jnz     short loc_1800067F4
0x180006802  mov     rax, rbx
0x180006805  mov     rbx, [rsp+28h+arg_0]
0x18000680a  add     rsp, 20h
0x18000680e  pop     rdi
0x18000680f  retn
0x180006810  add     rbx, 10h
0x180006814  jz      short loc_180006802
0x180006816  cmp     qword ptr [rbx+8], 0
0x18000681b  jnz     short loc_180006802
0x18000681d  lea     rax, [rdi+4]
0x180006821  mov     [rbx+8], rax
0x180006825  jmp     short loc_180006802
```
