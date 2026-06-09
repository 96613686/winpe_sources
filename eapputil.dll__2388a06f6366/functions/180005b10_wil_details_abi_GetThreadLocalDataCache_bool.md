# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005b10`
- end: `0x180005bcb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005330`

## callees

- `0x180004998`
- `0x180005b10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b66`

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
0x180005b10  mov     [rsp+arg_0], rbx
0x180005b15  push    rdi
0x180005b16  sub     rsp, 20h
0x180005b1a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005b21  xor     ebx, ebx
0x180005b23  test    rdi, rdi
0x180005b26  jz      short loc_180005BA6
0x180005b28  cmp     [rdi+8], rbx
0x180005b2c  jnz     short loc_180005B53
0x180005b2e  mov     rcx, [rdi]
0x180005b31  lea     rdx, [rsp+28h+arg_8]
0x180005b36  mov     [rsp+28h+arg_8], rbx
0x180005b3b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005b40  test    eax, eax
0x180005b42  js      short loc_180005B53
0x180005b44  cmp     [rdi+8], rbx
0x180005b48  jnz     short loc_180005B53
0x180005b4a  mov     rax, [rsp+28h+arg_8]
0x180005b4f  mov     [rdi+8], rax
0x180005b53  mov     rax, [rdi+8]
0x180005b57  lea     rcx, [rax+20h]
0x180005b5b  neg     rax
0x180005b5e  sbb     rdi, rdi
0x180005b61  and     rdi, rcx
0x180005b64  jz      short loc_180005BA6
0x180005b66  call    cs:__imp_GetCurrentThreadId
0x180005b6c  mov     r8d, eax
0x180005b6f  mov     r9d, eax
0x180005b72  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005b7c  shr     r8, 2
0x180005b80  mul     r8
0x180005b83  shr     rdx, 3
0x180005b87  lea     rcx, [rdx+rdx*4]
0x180005b8b  add     rcx, rcx
0x180005b8e  sub     r8, rcx
0x180005b91  mov     rbx, [rdi+r8*8+8]
0x180005b96  jmp     short loc_180005BA1
0x180005b98  cmp     [rbx], r9d
0x180005b9b  jz      short loc_180005BB4
0x180005b9d  mov     rbx, [rbx+8]
0x180005ba1  test    rbx, rbx
0x180005ba4  jnz     short loc_180005B98
0x180005ba6  mov     rax, rbx
0x180005ba9  mov     rbx, [rsp+28h+arg_0]
0x180005bae  add     rsp, 20h
0x180005bb2  pop     rdi
0x180005bb3  retn
0x180005bb4  add     rbx, 10h
0x180005bb8  jz      short loc_180005BA6
0x180005bba  cmp     qword ptr [rbx+8], 0
0x180005bbf  jnz     short loc_180005BA6
0x180005bc1  lea     rax, [rdi+4]
0x180005bc5  mov     [rbx+8], rax
0x180005bc9  jmp     short loc_180005BA6
```
