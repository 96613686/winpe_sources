# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005530`
- end: `0x1800055ed`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e70`

## callees

- `0x1800049e0`
- `0x180005530`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000558a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000558a`

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
0x180005530  mov     [rsp+arg_0], rbx
0x180005535  push    rdi
0x180005536  sub     rsp, 20h
0x18000553a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005541  xor     ebx, ebx
0x180005543  test    rdi, rdi
0x180005546  jz      loc_1800055DF
0x18000554c  cmp     [rdi+8], rbx
0x180005550  jnz     short loc_180005577
0x180005552  mov     rcx, [rdi]
0x180005555  lea     rdx, [rsp+28h+arg_8]
0x18000555a  mov     [rsp+28h+arg_8], rbx
0x18000555f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005564  test    eax, eax
0x180005566  js      short loc_180005577
0x180005568  cmp     [rdi+8], rbx
0x18000556c  jnz     short loc_180005577
0x18000556e  mov     rax, [rsp+28h+arg_8]
0x180005573  mov     [rdi+8], rax
0x180005577  mov     rax, [rdi+8]
0x18000557b  lea     rcx, [rax+20h]
0x18000557f  neg     rax
0x180005582  sbb     rdi, rdi
0x180005585  and     rdi, rcx
0x180005588  jz      short loc_1800055DF
0x18000558a  call    cs:__imp_GetCurrentThreadId
0x180005590  mov     r8d, eax
0x180005593  mov     r9d, eax
0x180005596  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800055a0  shr     r8, 2
0x1800055a4  mul     r8
0x1800055a7  shr     rdx, 3
0x1800055ab  lea     rcx, [rdx+rdx*4]
0x1800055af  add     rcx, rcx
0x1800055b2  sub     r8, rcx
0x1800055b5  mov     rbx, [rdi+r8*8+8]
0x1800055ba  test    rbx, rbx
0x1800055bd  jz      short loc_1800055DF
0x1800055bf  cmp     [rbx], r9d
0x1800055c2  jz      short loc_1800055CA
0x1800055c4  mov     rbx, [rbx+8]
0x1800055c8  jmp     short loc_1800055BA
0x1800055ca  add     rbx, 10h
0x1800055ce  jz      short loc_1800055DF
0x1800055d0  cmp     qword ptr [rbx+8], 0
0x1800055d5  jnz     short loc_1800055DF
0x1800055d7  lea     rax, [rdi+4]
0x1800055db  mov     [rbx+8], rax
0x1800055df  mov     rax, rbx
0x1800055e2  mov     rbx, [rsp+28h+arg_0]
0x1800055e7  add     rsp, 20h
0x1800055eb  pop     rdi
0x1800055ec  retn
```
