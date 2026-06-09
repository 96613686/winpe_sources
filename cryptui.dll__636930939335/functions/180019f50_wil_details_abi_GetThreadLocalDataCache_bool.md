# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180019f50`
- end: `0x18001a00d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019470`

## callees

- `0x1800171a0`
- `0x180019f50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019faa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019faa`

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
0x180019f50  mov     [rsp+arg_0], rbx
0x180019f55  push    rdi
0x180019f56  sub     rsp, 20h
0x180019f5a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180019f61  xor     ebx, ebx
0x180019f63  test    rdi, rdi
0x180019f66  jz      loc_180019FFF
0x180019f6c  cmp     [rdi+8], rbx
0x180019f70  jnz     short loc_180019F97
0x180019f72  mov     rcx, [rdi]
0x180019f75  lea     rdx, [rsp+28h+arg_8]
0x180019f7a  mov     [rsp+28h+arg_8], rbx
0x180019f7f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180019f84  test    eax, eax
0x180019f86  js      short loc_180019F97
0x180019f88  cmp     [rdi+8], rbx
0x180019f8c  jnz     short loc_180019F97
0x180019f8e  mov     rax, [rsp+28h+arg_8]
0x180019f93  mov     [rdi+8], rax
0x180019f97  mov     rax, [rdi+8]
0x180019f9b  lea     rcx, [rax+20h]
0x180019f9f  neg     rax
0x180019fa2  sbb     rdi, rdi
0x180019fa5  and     rdi, rcx
0x180019fa8  jz      short loc_180019FFF
0x180019faa  call    cs:__imp_GetCurrentThreadId
0x180019fb0  mov     r8d, eax
0x180019fb3  mov     r9d, eax
0x180019fb6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180019fc0  shr     r8, 2
0x180019fc4  mul     r8
0x180019fc7  shr     rdx, 3
0x180019fcb  lea     rcx, [rdx+rdx*4]
0x180019fcf  add     rcx, rcx
0x180019fd2  sub     r8, rcx
0x180019fd5  mov     rbx, [rdi+r8*8+8]
0x180019fda  test    rbx, rbx
0x180019fdd  jz      short loc_180019FFF
0x180019fdf  cmp     [rbx], r9d
0x180019fe2  jz      short loc_180019FEA
0x180019fe4  mov     rbx, [rbx+8]
0x180019fe8  jmp     short loc_180019FDA
0x180019fea  add     rbx, 10h
0x180019fee  jz      short loc_180019FFF
0x180019ff0  cmp     qword ptr [rbx+8], 0
0x180019ff5  jnz     short loc_180019FFF
0x180019ff7  lea     rax, [rdi+4]
0x180019ffb  mov     [rbx+8], rax
0x180019fff  mov     rax, rbx
0x18001a002  mov     rbx, [rsp+28h+arg_0]
0x18001a007  add     rsp, 20h
0x18001a00b  pop     rdi
0x18001a00c  retn
```
