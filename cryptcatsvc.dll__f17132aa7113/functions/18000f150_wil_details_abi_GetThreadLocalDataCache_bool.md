# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000f150`
- end: `0x18000f20d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eb20`

## callees

- `0x18000e108`
- `0x18000f150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f1aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f1aa`

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
0x18000f150  mov     [rsp+arg_0], rbx
0x18000f155  push    rdi
0x18000f156  sub     rsp, 20h
0x18000f15a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000f161  xor     ebx, ebx
0x18000f163  test    rdi, rdi
0x18000f166  jz      loc_18000F1FF
0x18000f16c  cmp     [rdi+8], rbx
0x18000f170  jnz     short loc_18000F197
0x18000f172  mov     rcx, [rdi]
0x18000f175  lea     rdx, [rsp+28h+arg_8]
0x18000f17a  mov     [rsp+28h+arg_8], rbx
0x18000f17f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000f184  test    eax, eax
0x18000f186  js      short loc_18000F197
0x18000f188  cmp     [rdi+8], rbx
0x18000f18c  jnz     short loc_18000F197
0x18000f18e  mov     rax, [rsp+28h+arg_8]
0x18000f193  mov     [rdi+8], rax
0x18000f197  mov     rax, [rdi+8]
0x18000f19b  lea     rcx, [rax+20h]
0x18000f19f  neg     rax
0x18000f1a2  sbb     rdi, rdi
0x18000f1a5  and     rdi, rcx
0x18000f1a8  jz      short loc_18000F1FF
0x18000f1aa  call    cs:__imp_GetCurrentThreadId
0x18000f1b0  mov     r8d, eax
0x18000f1b3  mov     r9d, eax
0x18000f1b6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000f1c0  shr     r8, 2
0x18000f1c4  mul     r8
0x18000f1c7  shr     rdx, 3
0x18000f1cb  lea     rcx, [rdx+rdx*4]
0x18000f1cf  add     rcx, rcx
0x18000f1d2  sub     r8, rcx
0x18000f1d5  mov     rbx, [rdi+r8*8+8]
0x18000f1da  test    rbx, rbx
0x18000f1dd  jz      short loc_18000F1FF
0x18000f1df  cmp     [rbx], r9d
0x18000f1e2  jz      short loc_18000F1EA
0x18000f1e4  mov     rbx, [rbx+8]
0x18000f1e8  jmp     short loc_18000F1DA
0x18000f1ea  add     rbx, 10h
0x18000f1ee  jz      short loc_18000F1FF
0x18000f1f0  cmp     qword ptr [rbx+8], 0
0x18000f1f5  jnz     short loc_18000F1FF
0x18000f1f7  lea     rax, [rdi+4]
0x18000f1fb  mov     [rbx+8], rax
0x18000f1ff  mov     rax, rbx
0x18000f202  mov     rbx, [rsp+28h+arg_0]
0x18000f207  add     rsp, 20h
0x18000f20b  pop     rdi
0x18000f20c  retn
```
