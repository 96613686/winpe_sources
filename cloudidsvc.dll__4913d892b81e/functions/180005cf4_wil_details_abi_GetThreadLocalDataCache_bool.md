# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005cf4`
- end: `0x180005db1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005580`

## callees

- `0x180004d28`
- `0x180005cf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d4e`

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
0x180005cf4  mov     [rsp+arg_0], rbx
0x180005cf9  push    rdi
0x180005cfa  sub     rsp, 20h
0x180005cfe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005d05  xor     ebx, ebx
0x180005d07  test    rdi, rdi
0x180005d0a  jz      loc_180005DA3
0x180005d10  cmp     [rdi+8], rbx
0x180005d14  jnz     short loc_180005D3B
0x180005d16  mov     rcx, [rdi]
0x180005d19  lea     rdx, [rsp+28h+arg_8]
0x180005d1e  mov     [rsp+28h+arg_8], rbx
0x180005d23  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005d28  test    eax, eax
0x180005d2a  js      short loc_180005D3B
0x180005d2c  cmp     [rdi+8], rbx
0x180005d30  jnz     short loc_180005D3B
0x180005d32  mov     rax, [rsp+28h+arg_8]
0x180005d37  mov     [rdi+8], rax
0x180005d3b  mov     rax, [rdi+8]
0x180005d3f  lea     rcx, [rax+20h]
0x180005d43  neg     rax
0x180005d46  sbb     rdi, rdi
0x180005d49  and     rdi, rcx
0x180005d4c  jz      short loc_180005DA3
0x180005d4e  call    cs:__imp_GetCurrentThreadId
0x180005d54  mov     r8d, eax
0x180005d57  mov     r9d, eax
0x180005d5a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005d64  shr     r8, 2
0x180005d68  mul     r8
0x180005d6b  shr     rdx, 3
0x180005d6f  lea     rcx, [rdx+rdx*4]
0x180005d73  add     rcx, rcx
0x180005d76  sub     r8, rcx
0x180005d79  mov     rbx, [rdi+r8*8+8]
0x180005d7e  test    rbx, rbx
0x180005d81  jz      short loc_180005DA3
0x180005d83  cmp     [rbx], r9d
0x180005d86  jz      short loc_180005D8E
0x180005d88  mov     rbx, [rbx+8]
0x180005d8c  jmp     short loc_180005D7E
0x180005d8e  add     rbx, 10h
0x180005d92  jz      short loc_180005DA3
0x180005d94  cmp     qword ptr [rbx+8], 0
0x180005d99  jnz     short loc_180005DA3
0x180005d9b  lea     rax, [rdi+4]
0x180005d9f  mov     [rbx+8], rax
0x180005da3  mov     rax, rbx
0x180005da6  mov     rbx, [rsp+28h+arg_0]
0x180005dab  add     rsp, 20h
0x180005daf  pop     rdi
0x180005db0  retn
```
