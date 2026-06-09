# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a4c0`
- end: `0x18000a586`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e20`

## callees

- `0x180009a10`
- `0x18000a4c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a51a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a51a`

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
0x18000a4c0  mov     [rsp+arg_0], rbx
0x18000a4c5  push    rdi
0x18000a4c6  sub     rsp, 20h
0x18000a4ca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a4d1  xor     ebx, ebx
0x18000a4d3  test    rdi, rdi
0x18000a4d6  jz      loc_18000A560
0x18000a4dc  cmp     [rdi+8], rbx
0x18000a4e0  jnz     short loc_18000A507
0x18000a4e2  mov     rcx, [rdi]
0x18000a4e5  lea     rdx, [rsp+28h+arg_8]
0x18000a4ea  mov     [rsp+28h+arg_8], rbx
0x18000a4ef  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a4f4  test    eax, eax
0x18000a4f6  js      short loc_18000A507
0x18000a4f8  cmp     [rdi+8], rbx
0x18000a4fc  jnz     short loc_18000A507
0x18000a4fe  mov     rax, [rsp+28h+arg_8]
0x18000a503  mov     [rdi+8], rax
0x18000a507  mov     rax, [rdi+8]
0x18000a50b  lea     rcx, [rax+20h]
0x18000a50f  neg     rax
0x18000a512  sbb     rdi, rdi
0x18000a515  and     rdi, rcx
0x18000a518  jz      short loc_18000A560
0x18000a51a  call    cs:__imp_GetCurrentThreadId
0x18000a521  nop     dword ptr [rax+rax+00h]
0x18000a526  mov     r8d, eax
0x18000a529  mov     r9d, eax
0x18000a52c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a536  shr     r8, 2
0x18000a53a  mul     r8
0x18000a53d  shr     rdx, 3
0x18000a541  lea     rcx, [rdx+rdx*4]
0x18000a545  add     rcx, rcx
0x18000a548  sub     r8, rcx
0x18000a54b  mov     rbx, [rdi+r8*8+8]
0x18000a550  jmp     short loc_18000A55B
0x18000a552  cmp     [rbx], r9d
0x18000a555  jz      short loc_18000A56F
0x18000a557  mov     rbx, [rbx+8]
0x18000a55b  test    rbx, rbx
0x18000a55e  jnz     short loc_18000A552
0x18000a560  mov     rax, rbx
0x18000a563  mov     rbx, [rsp+28h+arg_0]
0x18000a568  add     rsp, 20h
0x18000a56c  pop     rdi
0x18000a56d  retn
0x18000a56f  add     rbx, 10h
0x18000a573  jz      short loc_18000A560
0x18000a575  cmp     qword ptr [rbx+8], 0
0x18000a57a  jnz     short loc_18000A560
0x18000a57c  lea     rax, [rdi+4]
0x18000a580  mov     [rbx+8], rax
0x18000a584  jmp     short loc_18000A560
```
