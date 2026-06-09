# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004e40`
- end: `0x180004efb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004720`

## callees

- `0x1800037a8`
- `0x180004e40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e96`

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
0x180004e40  mov     [rsp+arg_0], rbx
0x180004e45  push    rdi
0x180004e46  sub     rsp, 20h
0x180004e4a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004e51  xor     ebx, ebx
0x180004e53  test    rdi, rdi
0x180004e56  jz      short loc_180004ED6
0x180004e58  cmp     [rdi+8], rbx
0x180004e5c  jnz     short loc_180004E83
0x180004e5e  mov     rcx, [rdi]
0x180004e61  lea     rdx, [rsp+28h+arg_8]
0x180004e66  mov     [rsp+28h+arg_8], rbx
0x180004e6b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004e70  test    eax, eax
0x180004e72  js      short loc_180004E83
0x180004e74  cmp     [rdi+8], rbx
0x180004e78  jnz     short loc_180004E83
0x180004e7a  mov     rax, [rsp+28h+arg_8]
0x180004e7f  mov     [rdi+8], rax
0x180004e83  mov     rax, [rdi+8]
0x180004e87  lea     rcx, [rax+20h]
0x180004e8b  neg     rax
0x180004e8e  sbb     rdi, rdi
0x180004e91  and     rdi, rcx
0x180004e94  jz      short loc_180004ED6
0x180004e96  call    cs:__imp_GetCurrentThreadId
0x180004e9c  mov     r8d, eax
0x180004e9f  mov     r9d, eax
0x180004ea2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004eac  shr     r8, 2
0x180004eb0  mul     r8
0x180004eb3  shr     rdx, 3
0x180004eb7  lea     rcx, [rdx+rdx*4]
0x180004ebb  add     rcx, rcx
0x180004ebe  sub     r8, rcx
0x180004ec1  mov     rbx, [rdi+r8*8+8]
0x180004ec6  jmp     short loc_180004ED1
0x180004ec8  cmp     [rbx], r9d
0x180004ecb  jz      short loc_180004EE4
0x180004ecd  mov     rbx, [rbx+8]
0x180004ed1  test    rbx, rbx
0x180004ed4  jnz     short loc_180004EC8
0x180004ed6  mov     rax, rbx
0x180004ed9  mov     rbx, [rsp+28h+arg_0]
0x180004ede  add     rsp, 20h
0x180004ee2  pop     rdi
0x180004ee3  retn
0x180004ee4  add     rbx, 10h
0x180004ee8  jz      short loc_180004ED6
0x180004eea  cmp     qword ptr [rbx+8], 0
0x180004eef  jnz     short loc_180004ED6
0x180004ef1  lea     rax, [rdi+4]
0x180004ef5  mov     [rbx+8], rax
0x180004ef9  jmp     short loc_180004ED6
```
