# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003d10`
- end: `0x180003dcb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003530`

## callees

- `0x180002e48`
- `0x180003d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d66`

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
0x180003d10  mov     [rsp+arg_0], rbx
0x180003d15  push    rdi
0x180003d16  sub     rsp, 20h
0x180003d1a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003d21  xor     ebx, ebx
0x180003d23  test    rdi, rdi
0x180003d26  jz      short loc_180003DA6
0x180003d28  cmp     [rdi+8], rbx
0x180003d2c  jnz     short loc_180003D53
0x180003d2e  mov     rcx, [rdi]
0x180003d31  lea     rdx, [rsp+28h+arg_8]
0x180003d36  mov     [rsp+28h+arg_8], rbx
0x180003d3b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003d40  test    eax, eax
0x180003d42  js      short loc_180003D53
0x180003d44  cmp     [rdi+8], rbx
0x180003d48  jnz     short loc_180003D53
0x180003d4a  mov     rax, [rsp+28h+arg_8]
0x180003d4f  mov     [rdi+8], rax
0x180003d53  mov     rax, [rdi+8]
0x180003d57  lea     rcx, [rax+20h]
0x180003d5b  neg     rax
0x180003d5e  sbb     rdi, rdi
0x180003d61  and     rdi, rcx
0x180003d64  jz      short loc_180003DA6
0x180003d66  call    cs:__imp_GetCurrentThreadId
0x180003d6c  mov     r8d, eax
0x180003d6f  mov     r9d, eax
0x180003d72  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003d7c  shr     r8, 2
0x180003d80  mul     r8
0x180003d83  shr     rdx, 3
0x180003d87  lea     rcx, [rdx+rdx*4]
0x180003d8b  add     rcx, rcx
0x180003d8e  sub     r8, rcx
0x180003d91  mov     rbx, [rdi+r8*8+8]
0x180003d96  jmp     short loc_180003DA1
0x180003d98  cmp     [rbx], r9d
0x180003d9b  jz      short loc_180003DB4
0x180003d9d  mov     rbx, [rbx+8]
0x180003da1  test    rbx, rbx
0x180003da4  jnz     short loc_180003D98
0x180003da6  mov     rax, rbx
0x180003da9  mov     rbx, [rsp+28h+arg_0]
0x180003dae  add     rsp, 20h
0x180003db2  pop     rdi
0x180003db3  retn
0x180003db4  add     rbx, 10h
0x180003db8  jz      short loc_180003DA6
0x180003dba  cmp     qword ptr [rbx+8], 0
0x180003dbf  jnz     short loc_180003DA6
0x180003dc1  lea     rax, [rdi+4]
0x180003dc5  mov     [rbx+8], rax
0x180003dc9  jmp     short loc_180003DA6
```
