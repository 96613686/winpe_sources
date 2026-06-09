# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140003b9c`
- end: `0x140003c62`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003440`

## callees

- `0x14000308c`
- `0x140003b9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003bf6`

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
0x140003b9c  mov     [rsp+arg_0], rbx
0x140003ba1  push    rdi
0x140003ba2  sub     rsp, 20h
0x140003ba6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140003bad  xor     ebx, ebx
0x140003baf  test    rdi, rdi
0x140003bb2  jz      loc_140003C3C
0x140003bb8  cmp     [rdi+8], rbx
0x140003bbc  jnz     short loc_140003BE3
0x140003bbe  mov     rcx, [rdi]
0x140003bc1  lea     rdx, [rsp+28h+arg_8]
0x140003bc6  mov     [rsp+28h+arg_8], rbx
0x140003bcb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140003bd0  test    eax, eax
0x140003bd2  js      short loc_140003BE3
0x140003bd4  cmp     [rdi+8], rbx
0x140003bd8  jnz     short loc_140003BE3
0x140003bda  mov     rax, [rsp+28h+arg_8]
0x140003bdf  mov     [rdi+8], rax
0x140003be3  mov     rax, [rdi+8]
0x140003be7  lea     rcx, [rax+20h]
0x140003beb  neg     rax
0x140003bee  sbb     rdi, rdi
0x140003bf1  and     rdi, rcx
0x140003bf4  jz      short loc_140003C3C
0x140003bf6  call    cs:__imp_GetCurrentThreadId
0x140003bfd  nop     dword ptr [rax+rax+00h]
0x140003c02  mov     r8d, eax
0x140003c05  mov     r9d, eax
0x140003c08  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003c12  shr     r8, 2
0x140003c16  mul     r8
0x140003c19  shr     rdx, 3
0x140003c1d  lea     rcx, [rdx+rdx*4]
0x140003c21  add     rcx, rcx
0x140003c24  sub     r8, rcx
0x140003c27  mov     rbx, [rdi+r8*8+8]
0x140003c2c  jmp     short loc_140003C37
0x140003c2e  cmp     [rbx], r9d
0x140003c31  jz      short loc_140003C4B
0x140003c33  mov     rbx, [rbx+8]
0x140003c37  test    rbx, rbx
0x140003c3a  jnz     short loc_140003C2E
0x140003c3c  mov     rax, rbx
0x140003c3f  mov     rbx, [rsp+28h+arg_0]
0x140003c44  add     rsp, 20h
0x140003c48  pop     rdi
0x140003c49  retn
0x140003c4b  add     rbx, 10h
0x140003c4f  jz      short loc_140003C3C
0x140003c51  cmp     qword ptr [rbx+8], 0
0x140003c56  jnz     short loc_140003C3C
0x140003c58  lea     rax, [rdi+4]
0x140003c5c  mov     [rbx+8], rax
0x140003c60  jmp     short loc_140003C3C
```
