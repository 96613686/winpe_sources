# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004c10`
- end: `0x140004ccb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004430`

## callees

- `0x140003d68`
- `0x140004c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004c66`

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
0x140004c10  mov     [rsp+arg_0], rbx
0x140004c15  push    rdi
0x140004c16  sub     rsp, 20h
0x140004c1a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004c21  xor     ebx, ebx
0x140004c23  test    rdi, rdi
0x140004c26  jz      short loc_140004CA6
0x140004c28  cmp     [rdi+8], rbx
0x140004c2c  jnz     short loc_140004C53
0x140004c2e  mov     rcx, [rdi]
0x140004c31  lea     rdx, [rsp+28h+arg_8]
0x140004c36  mov     [rsp+28h+arg_8], rbx
0x140004c3b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004c40  test    eax, eax
0x140004c42  js      short loc_140004C53
0x140004c44  cmp     [rdi+8], rbx
0x140004c48  jnz     short loc_140004C53
0x140004c4a  mov     rax, [rsp+28h+arg_8]
0x140004c4f  mov     [rdi+8], rax
0x140004c53  mov     rax, [rdi+8]
0x140004c57  lea     rcx, [rax+20h]
0x140004c5b  neg     rax
0x140004c5e  sbb     rdi, rdi
0x140004c61  and     rdi, rcx
0x140004c64  jz      short loc_140004CA6
0x140004c66  call    cs:__imp_GetCurrentThreadId
0x140004c6c  mov     r8d, eax
0x140004c6f  mov     r9d, eax
0x140004c72  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004c7c  shr     r8, 2
0x140004c80  mul     r8
0x140004c83  shr     rdx, 3
0x140004c87  lea     rcx, [rdx+rdx*4]
0x140004c8b  add     rcx, rcx
0x140004c8e  sub     r8, rcx
0x140004c91  mov     rbx, [rdi+r8*8+8]
0x140004c96  jmp     short loc_140004CA1
0x140004c98  cmp     [rbx], r9d
0x140004c9b  jz      short loc_140004CB4
0x140004c9d  mov     rbx, [rbx+8]
0x140004ca1  test    rbx, rbx
0x140004ca4  jnz     short loc_140004C98
0x140004ca6  mov     rax, rbx
0x140004ca9  mov     rbx, [rsp+28h+arg_0]
0x140004cae  add     rsp, 20h
0x140004cb2  pop     rdi
0x140004cb3  retn
0x140004cb4  add     rbx, 10h
0x140004cb8  jz      short loc_140004CA6
0x140004cba  cmp     qword ptr [rbx+8], 0
0x140004cbf  jnz     short loc_140004CA6
0x140004cc1  lea     rax, [rdi+4]
0x140004cc5  mov     [rbx+8], rax
0x140004cc9  jmp     short loc_140004CA6
```
