# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005d88`
- end: `0x180005e45`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800057b0`

## callees

- `0x180005338`
- `0x180005d88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005de2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005de2`

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
0x180005d88  mov     [rsp+arg_0], rbx
0x180005d8d  push    rdi
0x180005d8e  sub     rsp, 20h
0x180005d92  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005d99  xor     ebx, ebx
0x180005d9b  test    rdi, rdi
0x180005d9e  jz      loc_180005E37
0x180005da4  cmp     [rdi+8], rbx
0x180005da8  jnz     short loc_180005DCF
0x180005daa  mov     rcx, [rdi]
0x180005dad  lea     rdx, [rsp+28h+arg_8]
0x180005db2  mov     [rsp+28h+arg_8], rbx
0x180005db7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005dbc  test    eax, eax
0x180005dbe  js      short loc_180005DCF
0x180005dc0  cmp     [rdi+8], rbx
0x180005dc4  jnz     short loc_180005DCF
0x180005dc6  mov     rax, [rsp+28h+arg_8]
0x180005dcb  mov     [rdi+8], rax
0x180005dcf  mov     rax, [rdi+8]
0x180005dd3  lea     rcx, [rax+20h]
0x180005dd7  neg     rax
0x180005dda  sbb     rdi, rdi
0x180005ddd  and     rdi, rcx
0x180005de0  jz      short loc_180005E37
0x180005de2  call    cs:__imp_GetCurrentThreadId
0x180005de8  mov     r8d, eax
0x180005deb  mov     r9d, eax
0x180005dee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005df8  shr     r8, 2
0x180005dfc  mul     r8
0x180005dff  shr     rdx, 3
0x180005e03  lea     rcx, [rdx+rdx*4]
0x180005e07  add     rcx, rcx
0x180005e0a  sub     r8, rcx
0x180005e0d  mov     rbx, [rdi+r8*8+8]
0x180005e12  test    rbx, rbx
0x180005e15  jz      short loc_180005E37
0x180005e17  cmp     [rbx], r9d
0x180005e1a  jz      short loc_180005E22
0x180005e1c  mov     rbx, [rbx+8]
0x180005e20  jmp     short loc_180005E12
0x180005e22  add     rbx, 10h
0x180005e26  jz      short loc_180005E37
0x180005e28  cmp     qword ptr [rbx+8], 0
0x180005e2d  jnz     short loc_180005E37
0x180005e2f  lea     rax, [rdi+4]
0x180005e33  mov     [rbx+8], rax
0x180005e37  mov     rax, rbx
0x180005e3a  mov     rbx, [rsp+28h+arg_0]
0x180005e3f  add     rsp, 20h
0x180005e43  pop     rdi
0x180005e44  retn
```
