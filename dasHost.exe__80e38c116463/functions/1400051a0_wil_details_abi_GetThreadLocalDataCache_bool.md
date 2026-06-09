# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400051a0`
- end: `0x14000525b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400049c0`

## callees

- `0x1400039d8`
- `0x1400051a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051f6`

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
0x1400051a0  mov     [rsp+arg_0], rbx
0x1400051a5  push    rdi
0x1400051a6  sub     rsp, 20h
0x1400051aa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400051b1  xor     ebx, ebx
0x1400051b3  test    rdi, rdi
0x1400051b6  jz      short loc_140005236
0x1400051b8  cmp     [rdi+8], rbx
0x1400051bc  jnz     short loc_1400051E3
0x1400051be  mov     rcx, [rdi]
0x1400051c1  lea     rdx, [rsp+28h+arg_8]
0x1400051c6  mov     [rsp+28h+arg_8], rbx
0x1400051cb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400051d0  test    eax, eax
0x1400051d2  js      short loc_1400051E3
0x1400051d4  cmp     [rdi+8], rbx
0x1400051d8  jnz     short loc_1400051E3
0x1400051da  mov     rax, [rsp+28h+arg_8]
0x1400051df  mov     [rdi+8], rax
0x1400051e3  mov     rax, [rdi+8]
0x1400051e7  lea     rcx, [rax+20h]
0x1400051eb  neg     rax
0x1400051ee  sbb     rdi, rdi
0x1400051f1  and     rdi, rcx
0x1400051f4  jz      short loc_140005236
0x1400051f6  call    cs:__imp_GetCurrentThreadId
0x1400051fc  mov     r8d, eax
0x1400051ff  mov     r9d, eax
0x140005202  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000520c  shr     r8, 2
0x140005210  mul     r8
0x140005213  shr     rdx, 3
0x140005217  lea     rcx, [rdx+rdx*4]
0x14000521b  add     rcx, rcx
0x14000521e  sub     r8, rcx
0x140005221  mov     rbx, [rdi+r8*8+8]
0x140005226  jmp     short loc_140005231
0x140005228  cmp     [rbx], r9d
0x14000522b  jz      short loc_140005244
0x14000522d  mov     rbx, [rbx+8]
0x140005231  test    rbx, rbx
0x140005234  jnz     short loc_140005228
0x140005236  mov     rax, rbx
0x140005239  mov     rbx, [rsp+28h+arg_0]
0x14000523e  add     rsp, 20h
0x140005242  pop     rdi
0x140005243  retn
0x140005244  add     rbx, 10h
0x140005248  jz      short loc_140005236
0x14000524a  cmp     qword ptr [rbx+8], 0
0x14000524f  jnz     short loc_140005236
0x140005251  lea     rax, [rdi+4]
0x140005255  mov     [rbx+8], rax
0x140005259  jmp     short loc_140005236
```
