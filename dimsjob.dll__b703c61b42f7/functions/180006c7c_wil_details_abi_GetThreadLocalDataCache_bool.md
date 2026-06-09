# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006c7c`
- end: `0x180006d39`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065d0`

## callees

- `0x180005ca8`
- `0x180006c7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cd6`

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
0x180006c7c  mov     [rsp+arg_0], rbx
0x180006c81  push    rdi
0x180006c82  sub     rsp, 20h
0x180006c86  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006c8d  xor     ebx, ebx
0x180006c8f  test    rdi, rdi
0x180006c92  jz      loc_180006D2B
0x180006c98  cmp     [rdi+8], rbx
0x180006c9c  jnz     short loc_180006CC3
0x180006c9e  mov     rcx, [rdi]
0x180006ca1  lea     rdx, [rsp+28h+arg_8]
0x180006ca6  mov     [rsp+28h+arg_8], rbx
0x180006cab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006cb0  test    eax, eax
0x180006cb2  js      short loc_180006CC3
0x180006cb4  cmp     [rdi+8], rbx
0x180006cb8  jnz     short loc_180006CC3
0x180006cba  mov     rax, [rsp+28h+arg_8]
0x180006cbf  mov     [rdi+8], rax
0x180006cc3  mov     rax, [rdi+8]
0x180006cc7  lea     rcx, [rax+20h]
0x180006ccb  neg     rax
0x180006cce  sbb     rdi, rdi
0x180006cd1  and     rdi, rcx
0x180006cd4  jz      short loc_180006D2B
0x180006cd6  call    cs:__imp_GetCurrentThreadId
0x180006cdc  mov     r8d, eax
0x180006cdf  mov     r9d, eax
0x180006ce2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006cec  shr     r8, 2
0x180006cf0  mul     r8
0x180006cf3  shr     rdx, 3
0x180006cf7  lea     rcx, [rdx+rdx*4]
0x180006cfb  add     rcx, rcx
0x180006cfe  sub     r8, rcx
0x180006d01  mov     rbx, [rdi+r8*8+8]
0x180006d06  test    rbx, rbx
0x180006d09  jz      short loc_180006D2B
0x180006d0b  cmp     [rbx], r9d
0x180006d0e  jz      short loc_180006D16
0x180006d10  mov     rbx, [rbx+8]
0x180006d14  jmp     short loc_180006D06
0x180006d16  add     rbx, 10h
0x180006d1a  jz      short loc_180006D2B
0x180006d1c  cmp     qword ptr [rbx+8], 0
0x180006d21  jnz     short loc_180006D2B
0x180006d23  lea     rax, [rdi+4]
0x180006d27  mov     [rbx+8], rax
0x180006d2b  mov     rax, rbx
0x180006d2e  mov     rbx, [rsp+28h+arg_0]
0x180006d33  add     rsp, 20h
0x180006d37  pop     rdi
0x180006d38  retn
```
