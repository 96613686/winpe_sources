# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005b64`
- end: `0x180005c1f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800052e0`

## callees

- `0x180004b38`
- `0x180005b64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bba`

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
0x180005b64  mov     [rsp+arg_0], rbx
0x180005b69  push    rdi
0x180005b6a  sub     rsp, 20h
0x180005b6e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005b75  xor     ebx, ebx
0x180005b77  test    rdi, rdi
0x180005b7a  jz      short loc_180005BFA
0x180005b7c  cmp     [rdi+8], rbx
0x180005b80  jnz     short loc_180005BA7
0x180005b82  mov     rcx, [rdi]
0x180005b85  lea     rdx, [rsp+28h+arg_8]
0x180005b8a  mov     [rsp+28h+arg_8], rbx
0x180005b8f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005b94  test    eax, eax
0x180005b96  js      short loc_180005BA7
0x180005b98  cmp     [rdi+8], rbx
0x180005b9c  jnz     short loc_180005BA7
0x180005b9e  mov     rax, [rsp+28h+arg_8]
0x180005ba3  mov     [rdi+8], rax
0x180005ba7  mov     rax, [rdi+8]
0x180005bab  lea     rcx, [rax+20h]
0x180005baf  neg     rax
0x180005bb2  sbb     rdi, rdi
0x180005bb5  and     rdi, rcx
0x180005bb8  jz      short loc_180005BFA
0x180005bba  call    cs:__imp_GetCurrentThreadId
0x180005bc0  mov     r8d, eax
0x180005bc3  mov     r9d, eax
0x180005bc6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005bd0  shr     r8, 2
0x180005bd4  mul     r8
0x180005bd7  shr     rdx, 3
0x180005bdb  lea     rcx, [rdx+rdx*4]
0x180005bdf  add     rcx, rcx
0x180005be2  sub     r8, rcx
0x180005be5  mov     rbx, [rdi+r8*8+8]
0x180005bea  jmp     short loc_180005BF5
0x180005bec  cmp     [rbx], r9d
0x180005bef  jz      short loc_180005C08
0x180005bf1  mov     rbx, [rbx+8]
0x180005bf5  test    rbx, rbx
0x180005bf8  jnz     short loc_180005BEC
0x180005bfa  mov     rax, rbx
0x180005bfd  mov     rbx, [rsp+28h+arg_0]
0x180005c02  add     rsp, 20h
0x180005c06  pop     rdi
0x180005c07  retn
0x180005c08  add     rbx, 10h
0x180005c0c  jz      short loc_180005BFA
0x180005c0e  cmp     qword ptr [rbx+8], 0
0x180005c13  jnz     short loc_180005BFA
0x180005c15  lea     rax, [rdi+4]
0x180005c19  mov     [rbx+8], rax
0x180005c1d  jmp     short loc_180005BFA
```
