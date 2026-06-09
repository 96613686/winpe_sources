# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005d40`
- end: `0x180005dfb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005560`

## callees

- `0x180004428`
- `0x180005d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d96`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180005d40  mov     [rsp+arg_0], rbx
0x180005d45  push    rdi
0x180005d46  sub     rsp, 20h
0x180005d4a  xor     ebx, ebx
0x180005d4c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005d53  test    rdi, rdi
0x180005d56  jz      short loc_180005DD6
0x180005d58  cmp     [rdi+8], rbx
0x180005d5c  jnz     short loc_180005D83
0x180005d5e  mov     [rsp+28h+arg_8], rbx
0x180005d63  lea     rdx, [rsp+28h+arg_8]
0x180005d68  mov     rcx, [rdi]
0x180005d6b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005d70  test    eax, eax
0x180005d72  js      short loc_180005D83
0x180005d74  cmp     [rdi+8], rbx
0x180005d78  jnz     short loc_180005D83
0x180005d7a  mov     rax, [rsp+28h+arg_8]
0x180005d7f  mov     [rdi+8], rax
0x180005d83  mov     rcx, [rdi+8]
0x180005d87  lea     rax, [rcx+20h]
0x180005d8b  neg     rcx
0x180005d8e  sbb     rdi, rdi
0x180005d91  and     rdi, rax
0x180005d94  jz      short loc_180005DD6
0x180005d96  call    cs:__imp_GetCurrentThreadId
0x180005d9c  mov     r9d, eax
0x180005d9f  mov     r8d, eax
0x180005da2  shr     r8, 2
0x180005da6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005db0  mul     r8
0x180005db3  shr     rdx, 3
0x180005db7  lea     rcx, [rdx+rdx*4]
0x180005dbb  add     rcx, rcx
0x180005dbe  sub     r8, rcx
0x180005dc1  mov     rbx, [rdi+r8*8+8]
0x180005dc6  jmp     short loc_180005DD1
0x180005dc8  cmp     [rbx], r9d
0x180005dcb  jz      short loc_180005DE4
0x180005dcd  mov     rbx, [rbx+8]
0x180005dd1  test    rbx, rbx
0x180005dd4  jnz     short loc_180005DC8
0x180005dd6  mov     rax, rbx
0x180005dd9  mov     rbx, [rsp+28h+arg_0]
0x180005dde  add     rsp, 20h
0x180005de2  pop     rdi
0x180005de3  retn
0x180005de4  add     rbx, 10h
0x180005de8  jz      short loc_180005DD6
0x180005dea  cmp     qword ptr [rbx+8], 0
0x180005def  jnz     short loc_180005DD6
0x180005df1  lea     rax, [rdi+4]
0x180005df5  mov     [rbx+8], rax
0x180005df9  jmp     short loc_180005DD6
```
