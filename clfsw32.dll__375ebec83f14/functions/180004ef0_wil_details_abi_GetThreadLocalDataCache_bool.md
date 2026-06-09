# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004ef0`
- end: `0x180004fb6`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046d0`

## callees

- `0x1800037f4`
- `0x180004ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f4a`

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
0x180004ef0  mov     [rsp+arg_0], rbx
0x180004ef5  push    rdi
0x180004ef6  sub     rsp, 20h
0x180004efa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004f01  xor     ebx, ebx
0x180004f03  test    rdi, rdi
0x180004f06  jz      loc_180004F90
0x180004f0c  cmp     [rdi+8], rbx
0x180004f10  jnz     short loc_180004F37
0x180004f12  mov     rcx, [rdi]
0x180004f15  lea     rdx, [rsp+28h+arg_8]
0x180004f1a  mov     [rsp+28h+arg_8], rbx
0x180004f1f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004f24  test    eax, eax
0x180004f26  js      short loc_180004F37
0x180004f28  cmp     [rdi+8], rbx
0x180004f2c  jnz     short loc_180004F37
0x180004f2e  mov     rax, [rsp+28h+arg_8]
0x180004f33  mov     [rdi+8], rax
0x180004f37  mov     rax, [rdi+8]
0x180004f3b  lea     rcx, [rax+20h]
0x180004f3f  neg     rax
0x180004f42  sbb     rdi, rdi
0x180004f45  and     rdi, rcx
0x180004f48  jz      short loc_180004F90
0x180004f4a  call    cs:__imp_GetCurrentThreadId
0x180004f51  nop     dword ptr [rax+rax+00h]
0x180004f56  mov     r8d, eax
0x180004f59  mov     r9d, eax
0x180004f5c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004f66  shr     r8, 2
0x180004f6a  mul     r8
0x180004f6d  shr     rdx, 3
0x180004f71  lea     rcx, [rdx+rdx*4]
0x180004f75  add     rcx, rcx
0x180004f78  sub     r8, rcx
0x180004f7b  mov     rbx, [rdi+r8*8+8]
0x180004f80  jmp     short loc_180004F8B
0x180004f82  cmp     [rbx], r9d
0x180004f85  jz      short loc_180004F9F
0x180004f87  mov     rbx, [rbx+8]
0x180004f8b  test    rbx, rbx
0x180004f8e  jnz     short loc_180004F82
0x180004f90  mov     rax, rbx
0x180004f93  mov     rbx, [rsp+28h+arg_0]
0x180004f98  add     rsp, 20h
0x180004f9c  pop     rdi
0x180004f9d  retn
0x180004f9f  add     rbx, 10h
0x180004fa3  jz      short loc_180004F90
0x180004fa5  cmp     qword ptr [rbx+8], 0
0x180004faa  jnz     short loc_180004F90
0x180004fac  lea     rax, [rdi+4]
0x180004fb0  mov     [rbx+8], rax
0x180004fb4  jmp     short loc_180004F90
```
