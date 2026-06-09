# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005bc4`
- end: `0x140005c8a`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005460`

## callees

- `0x1400042a4`
- `0x140005bc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c1e`

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
0x140005bc4  mov     [rsp+arg_0], rbx
0x140005bc9  push    rdi
0x140005bca  sub     rsp, 20h
0x140005bce  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005bd5  xor     ebx, ebx
0x140005bd7  test    rdi, rdi
0x140005bda  jz      loc_140005C64
0x140005be0  cmp     [rdi+8], rbx
0x140005be4  jnz     short loc_140005C0B
0x140005be6  mov     rcx, [rdi]
0x140005be9  lea     rdx, [rsp+28h+arg_8]
0x140005bee  mov     [rsp+28h+arg_8], rbx
0x140005bf3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005bf8  test    eax, eax
0x140005bfa  js      short loc_140005C0B
0x140005bfc  cmp     [rdi+8], rbx
0x140005c00  jnz     short loc_140005C0B
0x140005c02  mov     rax, [rsp+28h+arg_8]
0x140005c07  mov     [rdi+8], rax
0x140005c0b  mov     rax, [rdi+8]
0x140005c0f  lea     rcx, [rax+20h]
0x140005c13  neg     rax
0x140005c16  sbb     rdi, rdi
0x140005c19  and     rdi, rcx
0x140005c1c  jz      short loc_140005C64
0x140005c1e  call    cs:__imp_GetCurrentThreadId
0x140005c25  nop     dword ptr [rax+rax+00h]
0x140005c2a  mov     r8d, eax
0x140005c2d  mov     r9d, eax
0x140005c30  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005c3a  shr     r8, 2
0x140005c3e  mul     r8
0x140005c41  shr     rdx, 3
0x140005c45  lea     rcx, [rdx+rdx*4]
0x140005c49  add     rcx, rcx
0x140005c4c  sub     r8, rcx
0x140005c4f  mov     rbx, [rdi+r8*8+8]
0x140005c54  jmp     short loc_140005C5F
0x140005c56  cmp     [rbx], r9d
0x140005c59  jz      short loc_140005C73
0x140005c5b  mov     rbx, [rbx+8]
0x140005c5f  test    rbx, rbx
0x140005c62  jnz     short loc_140005C56
0x140005c64  mov     rax, rbx
0x140005c67  mov     rbx, [rsp+28h+arg_0]
0x140005c6c  add     rsp, 20h
0x140005c70  pop     rdi
0x140005c71  retn
0x140005c73  add     rbx, 10h
0x140005c77  jz      short loc_140005C64
0x140005c79  cmp     qword ptr [rbx+8], 0
0x140005c7e  jnz     short loc_140005C64
0x140005c80  lea     rax, [rdi+4]
0x140005c84  mov     [rbx+8], rax
0x140005c88  jmp     short loc_140005C64
```
