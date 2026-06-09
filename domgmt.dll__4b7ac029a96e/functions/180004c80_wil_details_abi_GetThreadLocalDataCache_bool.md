# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004c80`
- end: `0x180004d3b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044a0`

## callees

- `0x180003db8`
- `0x180004c80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cd6`

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
0x180004c80  mov     [rsp+arg_0], rbx
0x180004c85  push    rdi
0x180004c86  sub     rsp, 20h
0x180004c8a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004c91  xor     ebx, ebx
0x180004c93  test    rdi, rdi
0x180004c96  jz      short loc_180004D16
0x180004c98  cmp     [rdi+8], rbx
0x180004c9c  jnz     short loc_180004CC3
0x180004c9e  mov     rcx, [rdi]
0x180004ca1  lea     rdx, [rsp+28h+arg_8]
0x180004ca6  mov     [rsp+28h+arg_8], rbx
0x180004cab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004cb0  test    eax, eax
0x180004cb2  js      short loc_180004CC3
0x180004cb4  cmp     [rdi+8], rbx
0x180004cb8  jnz     short loc_180004CC3
0x180004cba  mov     rax, [rsp+28h+arg_8]
0x180004cbf  mov     [rdi+8], rax
0x180004cc3  mov     rax, [rdi+8]
0x180004cc7  lea     rcx, [rax+20h]
0x180004ccb  neg     rax
0x180004cce  sbb     rdi, rdi
0x180004cd1  and     rdi, rcx
0x180004cd4  jz      short loc_180004D16
0x180004cd6  call    cs:__imp_GetCurrentThreadId
0x180004cdc  mov     r8d, eax
0x180004cdf  mov     r9d, eax
0x180004ce2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004cec  shr     r8, 2
0x180004cf0  mul     r8
0x180004cf3  shr     rdx, 3
0x180004cf7  lea     rcx, [rdx+rdx*4]
0x180004cfb  add     rcx, rcx
0x180004cfe  sub     r8, rcx
0x180004d01  mov     rbx, [rdi+r8*8+8]
0x180004d06  jmp     short loc_180004D11
0x180004d08  cmp     [rbx], r9d
0x180004d0b  jz      short loc_180004D24
0x180004d0d  mov     rbx, [rbx+8]
0x180004d11  test    rbx, rbx
0x180004d14  jnz     short loc_180004D08
0x180004d16  mov     rax, rbx
0x180004d19  mov     rbx, [rsp+28h+arg_0]
0x180004d1e  add     rsp, 20h
0x180004d22  pop     rdi
0x180004d23  retn
0x180004d24  add     rbx, 10h
0x180004d28  jz      short loc_180004D16
0x180004d2a  cmp     qword ptr [rbx+8], 0
0x180004d2f  jnz     short loc_180004D16
0x180004d31  lea     rax, [rdi+4]
0x180004d35  mov     [rbx+8], rax
0x180004d39  jmp     short loc_180004D16
```
