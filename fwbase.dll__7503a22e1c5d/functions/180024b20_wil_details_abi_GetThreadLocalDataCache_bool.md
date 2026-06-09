# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180024b20`
- end: `0x180024bfa`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `218`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800242b0`

## callees

- `0x180022d20`
- `0x180024b20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024b7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024b7d`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rcx
  struct wil::details_abi::ThreadLocalData *result; // rax
  __int64 v5; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 v7; // rax
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    v2 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
    v8 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v2, &v8) >= 0
      && !*(_QWORD *)(v1 + 8) )
    {
      *(_QWORD *)(v1 + 8) = v8;
    }
  }
  v3 = *(_QWORD *)(v1 + 8);
  result = 0;
  v5 = v3 + 32;
  if ( !v3 )
    v5 = 0;
  if ( v5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = *(_QWORD *)(v5 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8);
    if ( v7 )
    {
      while ( *(_DWORD *)v7 != CurrentThreadId )
      {
        v7 = *(_QWORD *)(v7 + 8);
        if ( !v7 )
          return 0;
      }
      result = (struct wil::details_abi::ThreadLocalData *)(v7 + 16);
      if ( result )
      {
        if ( !*((_QWORD *)result + 1) )
          *((_QWORD *)result + 1) = v5 + 4;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024b20  mov     [rsp+arg_0], rbx
0x180024b25  push    rdi
0x180024b26  sub     rsp, 20h
0x180024b2a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180024b31  xor     edi, edi
0x180024b33  test    rbx, rbx
0x180024b36  jz      loc_180024BEC
0x180024b3c  cmp     [rbx+8], rdi
0x180024b40  jnz     short loc_180024B67
0x180024b42  mov     rcx, [rbx]
0x180024b45  lea     rdx, [rsp+28h+arg_8]
0x180024b4a  mov     [rsp+28h+arg_8], rdi
0x180024b4f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180024b54  test    eax, eax
0x180024b56  js      short loc_180024B67
0x180024b58  cmp     [rbx+8], rdi
0x180024b5c  jnz     short loc_180024B67
0x180024b5e  mov     rax, [rsp+28h+arg_8]
0x180024b63  mov     [rbx+8], rax
0x180024b67  mov     rcx, [rbx+8]
0x180024b6b  xor     eax, eax
0x180024b6d  test    rcx, rcx
0x180024b70  lea     rbx, [rcx+20h]
0x180024b74  cmovz   rbx, rax
0x180024b78  test    rbx, rbx
0x180024b7b  jz      short loc_180024BEF
0x180024b7d  call    cs:__imp_GetCurrentThreadId
0x180024b83  mov     r8d, eax
0x180024b86  mov     r9d, eax
0x180024b89  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180024b93  shr     r8, 2
0x180024b97  mul     r8
0x180024b9a  shr     rdx, 3
0x180024b9e  lea     rcx, [rdx+rdx*4]
0x180024ba2  add     rcx, rcx
0x180024ba5  sub     r8, rcx
0x180024ba8  mov     rax, [rbx+r8*8+8]
0x180024bad  test    rax, rax
0x180024bb0  jz      short loc_180024BC0
0x180024bb2  cmp     [rax], r9d
0x180024bb5  jz      short loc_180024BCD
0x180024bb7  mov     rax, [rax+8]
0x180024bbb  test    rax, rax
0x180024bbe  jnz     short loc_180024BB2
0x180024bc0  xor     eax, eax
0x180024bc2  mov     rbx, [rsp+28h+arg_0]
0x180024bc7  add     rsp, 20h
0x180024bcb  pop     rdi
0x180024bcc  retn
0x180024bcd  add     rax, 10h
0x180024bd1  jz      short loc_180024BEF
0x180024bd3  cmp     [rax+8], rdi
0x180024bd7  jnz     short loc_180024BEF
0x180024bd9  lea     rcx, [rbx+4]
0x180024bdd  mov     [rax+8], rcx
0x180024be1  mov     rbx, [rsp+28h+arg_0]
0x180024be6  add     rsp, 20h
0x180024bea  pop     rdi
0x180024beb  retn
0x180024bec  mov     rax, rdi
0x180024bef  mov     rbx, [rsp+28h+arg_0]
0x180024bf4  add     rsp, 20h
0x180024bf8  pop     rdi
0x180024bf9  retn
```
