# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009cd0`
- end: `0x180009d8d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ef0`

## callees

- `0x1800079a8`
- `0x180009cd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d2a`

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
0x180009cd0  mov     [rsp+arg_0], rbx
0x180009cd5  push    rdi
0x180009cd6  sub     rsp, 20h
0x180009cda  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009ce1  xor     ebx, ebx
0x180009ce3  test    rdi, rdi
0x180009ce6  jz      loc_180009D7F
0x180009cec  cmp     [rdi+8], rbx
0x180009cf0  jnz     short loc_180009D17
0x180009cf2  mov     rcx, [rdi]
0x180009cf5  lea     rdx, [rsp+28h+arg_8]
0x180009cfa  mov     [rsp+28h+arg_8], rbx
0x180009cff  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009d04  test    eax, eax
0x180009d06  js      short loc_180009D17
0x180009d08  cmp     [rdi+8], rbx
0x180009d0c  jnz     short loc_180009D17
0x180009d0e  mov     rax, [rsp+28h+arg_8]
0x180009d13  mov     [rdi+8], rax
0x180009d17  mov     rax, [rdi+8]
0x180009d1b  lea     rcx, [rax+20h]
0x180009d1f  neg     rax
0x180009d22  sbb     rdi, rdi
0x180009d25  and     rdi, rcx
0x180009d28  jz      short loc_180009D7F
0x180009d2a  call    cs:__imp_GetCurrentThreadId
0x180009d30  mov     r8d, eax
0x180009d33  mov     r9d, eax
0x180009d36  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009d40  shr     r8, 2
0x180009d44  mul     r8
0x180009d47  shr     rdx, 3
0x180009d4b  lea     rcx, [rdx+rdx*4]
0x180009d4f  add     rcx, rcx
0x180009d52  sub     r8, rcx
0x180009d55  mov     rbx, [rdi+r8*8+8]
0x180009d5a  test    rbx, rbx
0x180009d5d  jz      short loc_180009D7F
0x180009d5f  cmp     [rbx], r9d
0x180009d62  jz      short loc_180009D6A
0x180009d64  mov     rbx, [rbx+8]
0x180009d68  jmp     short loc_180009D5A
0x180009d6a  add     rbx, 10h
0x180009d6e  jz      short loc_180009D7F
0x180009d70  cmp     qword ptr [rbx+8], 0
0x180009d75  jnz     short loc_180009D7F
0x180009d77  lea     rax, [rdi+4]
0x180009d7b  mov     [rbx+8], rax
0x180009d7f  mov     rax, rbx
0x180009d82  mov     rbx, [rsp+28h+arg_0]
0x180009d87  add     rsp, 20h
0x180009d8b  pop     rdi
0x180009d8c  retn
```
