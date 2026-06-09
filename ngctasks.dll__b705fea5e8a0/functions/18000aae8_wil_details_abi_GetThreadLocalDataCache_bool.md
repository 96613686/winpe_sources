# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000aae8`
- end: `0x18000aba5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a0f0`

## callees

- `0x180009508`
- `0x18000aae8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab42`

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
0x18000aae8  mov     [rsp+arg_0], rbx
0x18000aaed  push    rdi
0x18000aaee  sub     rsp, 20h
0x18000aaf2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000aaf9  xor     ebx, ebx
0x18000aafb  test    rdi, rdi
0x18000aafe  jz      loc_18000AB97
0x18000ab04  cmp     [rdi+8], rbx
0x18000ab08  jnz     short loc_18000AB2F
0x18000ab0a  mov     rcx, [rdi]
0x18000ab0d  lea     rdx, [rsp+28h+arg_8]
0x18000ab12  mov     [rsp+28h+arg_8], rbx
0x18000ab17  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000ab1c  test    eax, eax
0x18000ab1e  js      short loc_18000AB2F
0x18000ab20  cmp     [rdi+8], rbx
0x18000ab24  jnz     short loc_18000AB2F
0x18000ab26  mov     rax, [rsp+28h+arg_8]
0x18000ab2b  mov     [rdi+8], rax
0x18000ab2f  mov     rax, [rdi+8]
0x18000ab33  lea     rcx, [rax+20h]
0x18000ab37  neg     rax
0x18000ab3a  sbb     rdi, rdi
0x18000ab3d  and     rdi, rcx
0x18000ab40  jz      short loc_18000AB97
0x18000ab42  call    cs:__imp_GetCurrentThreadId
0x18000ab48  mov     r8d, eax
0x18000ab4b  mov     r9d, eax
0x18000ab4e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ab58  shr     r8, 2
0x18000ab5c  mul     r8
0x18000ab5f  shr     rdx, 3
0x18000ab63  lea     rcx, [rdx+rdx*4]
0x18000ab67  add     rcx, rcx
0x18000ab6a  sub     r8, rcx
0x18000ab6d  mov     rbx, [rdi+r8*8+8]
0x18000ab72  test    rbx, rbx
0x18000ab75  jz      short loc_18000AB97
0x18000ab77  cmp     [rbx], r9d
0x18000ab7a  jz      short loc_18000AB82
0x18000ab7c  mov     rbx, [rbx+8]
0x18000ab80  jmp     short loc_18000AB72
0x18000ab82  add     rbx, 10h
0x18000ab86  jz      short loc_18000AB97
0x18000ab88  cmp     qword ptr [rbx+8], 0
0x18000ab8d  jnz     short loc_18000AB97
0x18000ab8f  lea     rax, [rdi+4]
0x18000ab93  mov     [rbx+8], rax
0x18000ab97  mov     rax, rbx
0x18000ab9a  mov     rbx, [rsp+28h+arg_0]
0x18000ab9f  add     rsp, 20h
0x18000aba3  pop     rdi
0x18000aba4  retn
```
