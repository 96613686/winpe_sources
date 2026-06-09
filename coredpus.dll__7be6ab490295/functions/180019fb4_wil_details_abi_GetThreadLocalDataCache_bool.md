# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180019fb4`
- end: `0x18001a078`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019930`

## callees

- `0x180018d0c`
- `0x180019fb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a00e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a00e`

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
0x180019fb4  mov     [rsp+arg_0], rbx
0x180019fb9  push    rdi
0x180019fba  sub     rsp, 20h
0x180019fbe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180019fc5  xor     ebx, ebx
0x180019fc7  test    rdi, rdi
0x180019fca  jz      loc_18001A069
0x180019fd0  cmp     [rdi+8], rbx
0x180019fd4  jnz     short loc_180019FFB
0x180019fd6  mov     rcx, [rdi]
0x180019fd9  lea     rdx, [rsp+28h+arg_8]
0x180019fde  mov     [rsp+28h+arg_8], rbx
0x180019fe3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180019fe8  test    eax, eax
0x180019fea  js      short loc_180019FFB
0x180019fec  cmp     [rdi+8], rbx
0x180019ff0  jnz     short loc_180019FFB
0x180019ff2  mov     rax, [rsp+28h+arg_8]
0x180019ff7  mov     [rdi+8], rax
0x180019ffb  mov     rax, [rdi+8]
0x180019fff  lea     rcx, [rax+20h]
0x18001a003  neg     rax
0x18001a006  sbb     rdi, rdi
0x18001a009  and     rdi, rcx
0x18001a00c  jz      short loc_18001A069
0x18001a00e  call    cs:__imp_GetCurrentThreadId
0x18001a015  nop     dword ptr [rax+rax+00h]
0x18001a01a  mov     r8d, eax
0x18001a01d  mov     r9d, eax
0x18001a020  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001a02a  shr     r8, 2
0x18001a02e  mul     r8
0x18001a031  shr     rdx, 3
0x18001a035  lea     rcx, [rdx+rdx*4]
0x18001a039  add     rcx, rcx
0x18001a03c  sub     r8, rcx
0x18001a03f  mov     rbx, [rdi+r8*8+8]
0x18001a044  test    rbx, rbx
0x18001a047  jz      short loc_18001A069
0x18001a049  cmp     [rbx], r9d
0x18001a04c  jz      short loc_18001A054
0x18001a04e  mov     rbx, [rbx+8]
0x18001a052  jmp     short loc_18001A044
0x18001a054  add     rbx, 10h
0x18001a058  jz      short loc_18001A069
0x18001a05a  cmp     qword ptr [rbx+8], 0
0x18001a05f  jnz     short loc_18001A069
0x18001a061  lea     rax, [rdi+4]
0x18001a065  mov     [rbx+8], rax
0x18001a069  mov     rax, rbx
0x18001a06c  mov     rbx, [rsp+28h+arg_0]
0x18001a071  add     rsp, 20h
0x18001a075  pop     rdi
0x18001a076  retn
```
