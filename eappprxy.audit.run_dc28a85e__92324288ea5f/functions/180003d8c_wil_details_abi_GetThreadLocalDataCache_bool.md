# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003d8c`
- end: `0x180003e52`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003630`

## callees

- `0x18000327c`
- `0x180003d8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180003d8c  mov     [rsp+arg_0], rbx
0x180003d91  push    rdi
0x180003d92  sub     rsp, 20h
0x180003d96  xor     ebx, ebx
0x180003d98  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003d9f  test    rdi, rdi
0x180003da2  jz      loc_180003E2C
0x180003da8  cmp     [rdi+8], rbx
0x180003dac  jnz     short loc_180003DD3
0x180003dae  mov     [rsp+28h+arg_8], rbx
0x180003db3  lea     rdx, [rsp+28h+arg_8]
0x180003db8  mov     rcx, [rdi]
0x180003dbb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003dc0  test    eax, eax
0x180003dc2  js      short loc_180003DD3
0x180003dc4  cmp     [rdi+8], rbx
0x180003dc8  jnz     short loc_180003DD3
0x180003dca  mov     rax, [rsp+28h+arg_8]
0x180003dcf  mov     [rdi+8], rax
0x180003dd3  mov     rcx, [rdi+8]
0x180003dd7  lea     rax, [rcx+20h]
0x180003ddb  neg     rcx
0x180003dde  sbb     rdi, rdi
0x180003de1  and     rdi, rax
0x180003de4  jz      short loc_180003E2C
0x180003de6  call    cs:__imp_GetCurrentThreadId
0x180003ded  nop     dword ptr [rax+rax+00h]
0x180003df2  mov     r9d, eax
0x180003df5  mov     r8d, eax
0x180003df8  shr     r8, 2
0x180003dfc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e06  mul     r8
0x180003e09  shr     rdx, 3
0x180003e0d  lea     rcx, [rdx+rdx*4]
0x180003e11  add     rcx, rcx
0x180003e14  sub     r8, rcx
0x180003e17  mov     rbx, [rdi+r8*8+8]
0x180003e1c  jmp     short loc_180003E27
0x180003e1e  cmp     [rbx], r9d
0x180003e21  jz      short loc_180003E3B
0x180003e23  mov     rbx, [rbx+8]
0x180003e27  test    rbx, rbx
0x180003e2a  jnz     short loc_180003E1E
0x180003e2c  mov     rax, rbx
0x180003e2f  mov     rbx, [rsp+28h+arg_0]
0x180003e34  add     rsp, 20h
0x180003e38  pop     rdi
0x180003e39  retn
0x180003e3b  add     rbx, 10h
0x180003e3f  jz      short loc_180003E2C
0x180003e41  cmp     qword ptr [rbx+8], 0
0x180003e46  jnz     short loc_180003E2C
0x180003e48  lea     rax, [rdi+4]
0x180003e4c  mov     [rbx+8], rax
0x180003e50  jmp     short loc_180003E2C
```
