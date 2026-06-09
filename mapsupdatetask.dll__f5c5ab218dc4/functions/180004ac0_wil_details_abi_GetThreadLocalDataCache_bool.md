# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004ac0`
- end: `0x180004b7b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042e0`

## callees

- `0x1800037d4`
- `0x180004ac0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b16`

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
0x180004ac0  mov     [rsp+arg_0], rbx
0x180004ac5  push    rdi
0x180004ac6  sub     rsp, 20h
0x180004aca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004ad1  xor     ebx, ebx
0x180004ad3  test    rdi, rdi
0x180004ad6  jz      short loc_180004B56
0x180004ad8  cmp     [rdi+8], rbx
0x180004adc  jnz     short loc_180004B03
0x180004ade  mov     rcx, [rdi]
0x180004ae1  lea     rdx, [rsp+28h+arg_8]
0x180004ae6  mov     [rsp+28h+arg_8], rbx
0x180004aeb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004af0  test    eax, eax
0x180004af2  js      short loc_180004B03
0x180004af4  cmp     [rdi+8], rbx
0x180004af8  jnz     short loc_180004B03
0x180004afa  mov     rax, [rsp+28h+arg_8]
0x180004aff  mov     [rdi+8], rax
0x180004b03  mov     rax, [rdi+8]
0x180004b07  lea     rcx, [rax+20h]
0x180004b0b  neg     rax
0x180004b0e  sbb     rdi, rdi
0x180004b11  and     rdi, rcx
0x180004b14  jz      short loc_180004B56
0x180004b16  call    cs:__imp_GetCurrentThreadId
0x180004b1c  mov     r8d, eax
0x180004b1f  mov     r9d, eax
0x180004b22  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004b2c  shr     r8, 2
0x180004b30  mul     r8
0x180004b33  shr     rdx, 3
0x180004b37  lea     rcx, [rdx+rdx*4]
0x180004b3b  add     rcx, rcx
0x180004b3e  sub     r8, rcx
0x180004b41  mov     rbx, [rdi+r8*8+8]
0x180004b46  jmp     short loc_180004B51
0x180004b48  cmp     [rbx], r9d
0x180004b4b  jz      short loc_180004B64
0x180004b4d  mov     rbx, [rbx+8]
0x180004b51  test    rbx, rbx
0x180004b54  jnz     short loc_180004B48
0x180004b56  mov     rax, rbx
0x180004b59  mov     rbx, [rsp+28h+arg_0]
0x180004b5e  add     rsp, 20h
0x180004b62  pop     rdi
0x180004b63  retn
0x180004b64  add     rbx, 10h
0x180004b68  jz      short loc_180004B56
0x180004b6a  cmp     qword ptr [rbx+8], 0
0x180004b6f  jnz     short loc_180004B56
0x180004b71  lea     rax, [rdi+4]
0x180004b75  mov     [rbx+8], rax
0x180004b79  jmp     short loc_180004B56
```
