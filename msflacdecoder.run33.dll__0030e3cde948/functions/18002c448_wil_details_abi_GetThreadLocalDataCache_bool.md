# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002c448`
- end: `0x18002c505`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b940`

## callees

- `0x18002a688`
- `0x18002c448`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c4a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c4a2`

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
0x18002c448  mov     [rsp+arg_0], rbx
0x18002c44d  push    rdi
0x18002c44e  sub     rsp, 20h
0x18002c452  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002c459  xor     ebx, ebx
0x18002c45b  test    rdi, rdi
0x18002c45e  jz      loc_18002C4F7
0x18002c464  cmp     [rdi+8], rbx
0x18002c468  jnz     short loc_18002C48F
0x18002c46a  mov     rcx, [rdi]
0x18002c46d  lea     rdx, [rsp+28h+arg_8]
0x18002c472  mov     [rsp+28h+arg_8], rbx
0x18002c477  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002c47c  test    eax, eax
0x18002c47e  js      short loc_18002C48F
0x18002c480  cmp     [rdi+8], rbx
0x18002c484  jnz     short loc_18002C48F
0x18002c486  mov     rax, [rsp+28h+arg_8]
0x18002c48b  mov     [rdi+8], rax
0x18002c48f  mov     rax, [rdi+8]
0x18002c493  lea     rcx, [rax+20h]
0x18002c497  neg     rax
0x18002c49a  sbb     rdi, rdi
0x18002c49d  and     rdi, rcx
0x18002c4a0  jz      short loc_18002C4F7
0x18002c4a2  call    cs:__imp_GetCurrentThreadId
0x18002c4a8  mov     r8d, eax
0x18002c4ab  mov     r9d, eax
0x18002c4ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002c4b8  shr     r8, 2
0x18002c4bc  mul     r8
0x18002c4bf  shr     rdx, 3
0x18002c4c3  lea     rcx, [rdx+rdx*4]
0x18002c4c7  add     rcx, rcx
0x18002c4ca  sub     r8, rcx
0x18002c4cd  mov     rbx, [rdi+r8*8+8]
0x18002c4d2  test    rbx, rbx
0x18002c4d5  jz      short loc_18002C4F7
0x18002c4d7  cmp     [rbx], r9d
0x18002c4da  jz      short loc_18002C4E2
0x18002c4dc  mov     rbx, [rbx+8]
0x18002c4e0  jmp     short loc_18002C4D2
0x18002c4e2  add     rbx, 10h
0x18002c4e6  jz      short loc_18002C4F7
0x18002c4e8  cmp     qword ptr [rbx+8], 0
0x18002c4ed  jnz     short loc_18002C4F7
0x18002c4ef  lea     rax, [rdi+4]
0x18002c4f3  mov     [rbx+8], rax
0x18002c4f7  mov     rax, rbx
0x18002c4fa  mov     rbx, [rsp+28h+arg_0]
0x18002c4ff  add     rsp, 20h
0x18002c503  pop     rdi
0x18002c504  retn
```
