# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005d98`
- end: `0x180005e55`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005760`

## callees

- `0x180004ce0`
- `0x180005d98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005df2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005df2`

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
0x180005d98  mov     [rsp+arg_0], rbx
0x180005d9d  push    rdi
0x180005d9e  sub     rsp, 20h
0x180005da2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005da9  xor     ebx, ebx
0x180005dab  test    rdi, rdi
0x180005dae  jz      loc_180005E47
0x180005db4  cmp     [rdi+8], rbx
0x180005db8  jnz     short loc_180005DDF
0x180005dba  mov     rcx, [rdi]
0x180005dbd  lea     rdx, [rsp+28h+arg_8]
0x180005dc2  mov     [rsp+28h+arg_8], rbx
0x180005dc7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005dcc  test    eax, eax
0x180005dce  js      short loc_180005DDF
0x180005dd0  cmp     [rdi+8], rbx
0x180005dd4  jnz     short loc_180005DDF
0x180005dd6  mov     rax, [rsp+28h+arg_8]
0x180005ddb  mov     [rdi+8], rax
0x180005ddf  mov     rax, [rdi+8]
0x180005de3  lea     rcx, [rax+20h]
0x180005de7  neg     rax
0x180005dea  sbb     rdi, rdi
0x180005ded  and     rdi, rcx
0x180005df0  jz      short loc_180005E47
0x180005df2  call    cs:__imp_GetCurrentThreadId
0x180005df8  mov     r8d, eax
0x180005dfb  mov     r9d, eax
0x180005dfe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005e08  shr     r8, 2
0x180005e0c  mul     r8
0x180005e0f  shr     rdx, 3
0x180005e13  lea     rcx, [rdx+rdx*4]
0x180005e17  add     rcx, rcx
0x180005e1a  sub     r8, rcx
0x180005e1d  mov     rbx, [rdi+r8*8+8]
0x180005e22  test    rbx, rbx
0x180005e25  jz      short loc_180005E47
0x180005e27  cmp     [rbx], r9d
0x180005e2a  jz      short loc_180005E32
0x180005e2c  mov     rbx, [rbx+8]
0x180005e30  jmp     short loc_180005E22
0x180005e32  add     rbx, 10h
0x180005e36  jz      short loc_180005E47
0x180005e38  cmp     qword ptr [rbx+8], 0
0x180005e3d  jnz     short loc_180005E47
0x180005e3f  lea     rax, [rdi+4]
0x180005e43  mov     [rbx+8], rax
0x180005e47  mov     rax, rbx
0x180005e4a  mov     rbx, [rsp+28h+arg_0]
0x180005e4f  add     rsp, 20h
0x180005e53  pop     rdi
0x180005e54  retn
```
