# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d824`
- end: `0x18000d8df`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cfa0`

## callees

- `0x18000c8ec`
- `0x18000d824`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d87a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d87a`

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
0x18000d824  mov     [rsp+arg_0], rbx
0x18000d829  push    rdi
0x18000d82a  sub     rsp, 20h
0x18000d82e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d835  xor     ebx, ebx
0x18000d837  test    rdi, rdi
0x18000d83a  jz      short loc_18000D8BA
0x18000d83c  cmp     [rdi+8], rbx
0x18000d840  jnz     short loc_18000D867
0x18000d842  mov     rcx, [rdi]
0x18000d845  lea     rdx, [rsp+28h+arg_8]
0x18000d84a  mov     [rsp+28h+arg_8], rbx
0x18000d84f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d854  test    eax, eax
0x18000d856  js      short loc_18000D867
0x18000d858  cmp     [rdi+8], rbx
0x18000d85c  jnz     short loc_18000D867
0x18000d85e  mov     rax, [rsp+28h+arg_8]
0x18000d863  mov     [rdi+8], rax
0x18000d867  mov     rax, [rdi+8]
0x18000d86b  lea     rcx, [rax+20h]
0x18000d86f  neg     rax
0x18000d872  sbb     rdi, rdi
0x18000d875  and     rdi, rcx
0x18000d878  jz      short loc_18000D8BA
0x18000d87a  call    cs:__imp_GetCurrentThreadId
0x18000d880  mov     r8d, eax
0x18000d883  mov     r9d, eax
0x18000d886  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d890  shr     r8, 2
0x18000d894  mul     r8
0x18000d897  shr     rdx, 3
0x18000d89b  lea     rcx, [rdx+rdx*4]
0x18000d89f  add     rcx, rcx
0x18000d8a2  sub     r8, rcx
0x18000d8a5  mov     rbx, [rdi+r8*8+8]
0x18000d8aa  jmp     short loc_18000D8B5
0x18000d8ac  cmp     [rbx], r9d
0x18000d8af  jz      short loc_18000D8C8
0x18000d8b1  mov     rbx, [rbx+8]
0x18000d8b5  test    rbx, rbx
0x18000d8b8  jnz     short loc_18000D8AC
0x18000d8ba  mov     rax, rbx
0x18000d8bd  mov     rbx, [rsp+28h+arg_0]
0x18000d8c2  add     rsp, 20h
0x18000d8c6  pop     rdi
0x18000d8c7  retn
0x18000d8c8  add     rbx, 10h
0x18000d8cc  jz      short loc_18000D8BA
0x18000d8ce  cmp     qword ptr [rbx+8], 0
0x18000d8d3  jnz     short loc_18000D8BA
0x18000d8d5  lea     rax, [rdi+4]
0x18000d8d9  mov     [rbx+8], rax
0x18000d8dd  jmp     short loc_18000D8BA
```
