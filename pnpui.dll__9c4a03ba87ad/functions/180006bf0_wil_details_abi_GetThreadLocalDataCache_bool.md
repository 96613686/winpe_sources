# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006bf0`
- end: `0x180006cab`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061f0`

## callees

- `0x180004d1c`
- `0x180006bf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c46`

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
0x180006bf0  mov     [rsp+arg_0], rbx
0x180006bf5  push    rdi
0x180006bf6  sub     rsp, 20h
0x180006bfa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006c01  xor     ebx, ebx
0x180006c03  test    rdi, rdi
0x180006c06  jz      short loc_180006C86
0x180006c08  cmp     [rdi+8], rbx
0x180006c0c  jnz     short loc_180006C33
0x180006c0e  mov     rcx, [rdi]
0x180006c11  lea     rdx, [rsp+28h+arg_8]
0x180006c16  mov     [rsp+28h+arg_8], rbx
0x180006c1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006c20  test    eax, eax
0x180006c22  js      short loc_180006C33
0x180006c24  cmp     [rdi+8], rbx
0x180006c28  jnz     short loc_180006C33
0x180006c2a  mov     rax, [rsp+28h+arg_8]
0x180006c2f  mov     [rdi+8], rax
0x180006c33  mov     rax, [rdi+8]
0x180006c37  lea     rcx, [rax+20h]
0x180006c3b  neg     rax
0x180006c3e  sbb     rdi, rdi
0x180006c41  and     rdi, rcx
0x180006c44  jz      short loc_180006C86
0x180006c46  call    cs:__imp_GetCurrentThreadId
0x180006c4c  mov     r8d, eax
0x180006c4f  mov     r9d, eax
0x180006c52  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006c5c  shr     r8, 2
0x180006c60  mul     r8
0x180006c63  shr     rdx, 3
0x180006c67  lea     rcx, [rdx+rdx*4]
0x180006c6b  add     rcx, rcx
0x180006c6e  sub     r8, rcx
0x180006c71  mov     rbx, [rdi+r8*8+8]
0x180006c76  jmp     short loc_180006C81
0x180006c78  cmp     [rbx], r9d
0x180006c7b  jz      short loc_180006C94
0x180006c7d  mov     rbx, [rbx+8]
0x180006c81  test    rbx, rbx
0x180006c84  jnz     short loc_180006C78
0x180006c86  mov     rax, rbx
0x180006c89  mov     rbx, [rsp+28h+arg_0]
0x180006c8e  add     rsp, 20h
0x180006c92  pop     rdi
0x180006c93  retn
0x180006c94  add     rbx, 10h
0x180006c98  jz      short loc_180006C86
0x180006c9a  cmp     qword ptr [rbx+8], 0
0x180006c9f  jnz     short loc_180006C86
0x180006ca1  lea     rax, [rdi+4]
0x180006ca5  mov     [rbx+8], rax
0x180006ca9  jmp     short loc_180006C86
```
