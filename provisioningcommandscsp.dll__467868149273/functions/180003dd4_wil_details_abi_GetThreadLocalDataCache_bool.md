# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003dd4`
- end: `0x180003e9a`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003670`

## callees

- `0x1800031d4`
- `0x180003dd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e2e`

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
0x180003dd4  mov     [rsp+arg_0], rbx
0x180003dd9  push    rdi
0x180003dda  sub     rsp, 20h
0x180003dde  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003de5  xor     ebx, ebx
0x180003de7  test    rdi, rdi
0x180003dea  jz      loc_180003E74
0x180003df0  cmp     [rdi+8], rbx
0x180003df4  jnz     short loc_180003E1B
0x180003df6  mov     rcx, [rdi]
0x180003df9  lea     rdx, [rsp+28h+arg_8]
0x180003dfe  mov     [rsp+28h+arg_8], rbx
0x180003e03  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003e08  test    eax, eax
0x180003e0a  js      short loc_180003E1B
0x180003e0c  cmp     [rdi+8], rbx
0x180003e10  jnz     short loc_180003E1B
0x180003e12  mov     rax, [rsp+28h+arg_8]
0x180003e17  mov     [rdi+8], rax
0x180003e1b  mov     rax, [rdi+8]
0x180003e1f  lea     rcx, [rax+20h]
0x180003e23  neg     rax
0x180003e26  sbb     rdi, rdi
0x180003e29  and     rdi, rcx
0x180003e2c  jz      short loc_180003E74
0x180003e2e  call    cs:__imp_GetCurrentThreadId
0x180003e35  nop     dword ptr [rax+rax+00h]
0x180003e3a  mov     r8d, eax
0x180003e3d  mov     r9d, eax
0x180003e40  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e4a  shr     r8, 2
0x180003e4e  mul     r8
0x180003e51  shr     rdx, 3
0x180003e55  lea     rcx, [rdx+rdx*4]
0x180003e59  add     rcx, rcx
0x180003e5c  sub     r8, rcx
0x180003e5f  mov     rbx, [rdi+r8*8+8]
0x180003e64  jmp     short loc_180003E6F
0x180003e66  cmp     [rbx], r9d
0x180003e69  jz      short loc_180003E83
0x180003e6b  mov     rbx, [rbx+8]
0x180003e6f  test    rbx, rbx
0x180003e72  jnz     short loc_180003E66
0x180003e74  mov     rax, rbx
0x180003e77  mov     rbx, [rsp+28h+arg_0]
0x180003e7c  add     rsp, 20h
0x180003e80  pop     rdi
0x180003e81  retn
0x180003e83  add     rbx, 10h
0x180003e87  jz      short loc_180003E74
0x180003e89  cmp     qword ptr [rbx+8], 0
0x180003e8e  jnz     short loc_180003E74
0x180003e90  lea     rax, [rdi+4]
0x180003e94  mov     [rbx+8], rax
0x180003e98  jmp     short loc_180003E74
```
