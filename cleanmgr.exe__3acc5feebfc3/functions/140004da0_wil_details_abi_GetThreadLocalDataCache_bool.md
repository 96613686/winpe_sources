# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004da0`
- end: `0x140004e5d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046e0`

## callees

- `0x140004238`
- `0x140004da0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004dfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004dfa`

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
0x140004da0  mov     [rsp+arg_0], rbx
0x140004da5  push    rdi
0x140004da6  sub     rsp, 20h
0x140004daa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004db1  xor     ebx, ebx
0x140004db3  test    rdi, rdi
0x140004db6  jz      loc_140004E4F
0x140004dbc  cmp     [rdi+8], rbx
0x140004dc0  jnz     short loc_140004DE7
0x140004dc2  mov     rcx, [rdi]
0x140004dc5  lea     rdx, [rsp+28h+arg_8]
0x140004dca  mov     [rsp+28h+arg_8], rbx
0x140004dcf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004dd4  test    eax, eax
0x140004dd6  js      short loc_140004DE7
0x140004dd8  cmp     [rdi+8], rbx
0x140004ddc  jnz     short loc_140004DE7
0x140004dde  mov     rax, [rsp+28h+arg_8]
0x140004de3  mov     [rdi+8], rax
0x140004de7  mov     rax, [rdi+8]
0x140004deb  lea     rcx, [rax+20h]
0x140004def  neg     rax
0x140004df2  sbb     rdi, rdi
0x140004df5  and     rdi, rcx
0x140004df8  jz      short loc_140004E4F
0x140004dfa  call    cs:__imp_GetCurrentThreadId
0x140004e00  mov     r8d, eax
0x140004e03  mov     r9d, eax
0x140004e06  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004e10  shr     r8, 2
0x140004e14  mul     r8
0x140004e17  shr     rdx, 3
0x140004e1b  lea     rcx, [rdx+rdx*4]
0x140004e1f  add     rcx, rcx
0x140004e22  sub     r8, rcx
0x140004e25  mov     rbx, [rdi+r8*8+8]
0x140004e2a  test    rbx, rbx
0x140004e2d  jz      short loc_140004E4F
0x140004e2f  cmp     [rbx], r9d
0x140004e32  jz      short loc_140004E3A
0x140004e34  mov     rbx, [rbx+8]
0x140004e38  jmp     short loc_140004E2A
0x140004e3a  add     rbx, 10h
0x140004e3e  jz      short loc_140004E4F
0x140004e40  cmp     qword ptr [rbx+8], 0
0x140004e45  jnz     short loc_140004E4F
0x140004e47  lea     rax, [rdi+4]
0x140004e4b  mov     [rbx+8], rax
0x140004e4f  mov     rax, rbx
0x140004e52  mov     rbx, [rsp+28h+arg_0]
0x140004e57  add     rsp, 20h
0x140004e5b  pop     rdi
0x140004e5c  retn
```
