# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004a4c`
- end: `0x180004b07`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004270`

## callees

- `0x180003114`
- `0x180004a4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004aa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004aa2`

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
0x180004a4c  mov     [rsp+arg_0], rbx
0x180004a51  push    rdi
0x180004a52  sub     rsp, 20h
0x180004a56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004a5d  xor     ebx, ebx
0x180004a5f  test    rdi, rdi
0x180004a62  jz      short loc_180004AE2
0x180004a64  cmp     [rdi+8], rbx
0x180004a68  jnz     short loc_180004A8F
0x180004a6a  mov     rcx, [rdi]
0x180004a6d  lea     rdx, [rsp+28h+arg_8]
0x180004a72  mov     [rsp+28h+arg_8], rbx
0x180004a77  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004a7c  test    eax, eax
0x180004a7e  js      short loc_180004A8F
0x180004a80  cmp     [rdi+8], rbx
0x180004a84  jnz     short loc_180004A8F
0x180004a86  mov     rax, [rsp+28h+arg_8]
0x180004a8b  mov     [rdi+8], rax
0x180004a8f  mov     rax, [rdi+8]
0x180004a93  lea     rcx, [rax+20h]
0x180004a97  neg     rax
0x180004a9a  sbb     rdi, rdi
0x180004a9d  and     rdi, rcx
0x180004aa0  jz      short loc_180004AE2
0x180004aa2  call    cs:__imp_GetCurrentThreadId
0x180004aa8  mov     r8d, eax
0x180004aab  mov     r9d, eax
0x180004aae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004ab8  shr     r8, 2
0x180004abc  mul     r8
0x180004abf  shr     rdx, 3
0x180004ac3  lea     rcx, [rdx+rdx*4]
0x180004ac7  add     rcx, rcx
0x180004aca  sub     r8, rcx
0x180004acd  mov     rbx, [rdi+r8*8+8]
0x180004ad2  jmp     short loc_180004ADD
0x180004ad4  cmp     [rbx], r9d
0x180004ad7  jz      short loc_180004AF0
0x180004ad9  mov     rbx, [rbx+8]
0x180004add  test    rbx, rbx
0x180004ae0  jnz     short loc_180004AD4
0x180004ae2  mov     rax, rbx
0x180004ae5  mov     rbx, [rsp+28h+arg_0]
0x180004aea  add     rsp, 20h
0x180004aee  pop     rdi
0x180004aef  retn
0x180004af0  add     rbx, 10h
0x180004af4  jz      short loc_180004AE2
0x180004af6  cmp     qword ptr [rbx+8], 0
0x180004afb  jnz     short loc_180004AE2
0x180004afd  lea     rax, [rdi+4]
0x180004b01  mov     [rbx+8], rax
0x180004b05  jmp     short loc_180004AE2
```
