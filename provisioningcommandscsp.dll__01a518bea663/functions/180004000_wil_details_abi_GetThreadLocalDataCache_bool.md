# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004000`
- end: `0x1800040bb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038e0`

## callees

- `0x180003140`
- `0x180004000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004056`

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
0x180004000  mov     [rsp+arg_0], rbx
0x180004005  push    rdi
0x180004006  sub     rsp, 20h
0x18000400a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004011  xor     ebx, ebx
0x180004013  test    rdi, rdi
0x180004016  jz      short loc_180004096
0x180004018  cmp     [rdi+8], rbx
0x18000401c  jnz     short loc_180004043
0x18000401e  mov     rcx, [rdi]
0x180004021  lea     rdx, [rsp+28h+arg_8]
0x180004026  mov     [rsp+28h+arg_8], rbx
0x18000402b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004030  test    eax, eax
0x180004032  js      short loc_180004043
0x180004034  cmp     [rdi+8], rbx
0x180004038  jnz     short loc_180004043
0x18000403a  mov     rax, [rsp+28h+arg_8]
0x18000403f  mov     [rdi+8], rax
0x180004043  mov     rax, [rdi+8]
0x180004047  lea     rcx, [rax+20h]
0x18000404b  neg     rax
0x18000404e  sbb     rdi, rdi
0x180004051  and     rdi, rcx
0x180004054  jz      short loc_180004096
0x180004056  call    cs:__imp_GetCurrentThreadId
0x18000405c  mov     r8d, eax
0x18000405f  mov     r9d, eax
0x180004062  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000406c  shr     r8, 2
0x180004070  mul     r8
0x180004073  shr     rdx, 3
0x180004077  lea     rcx, [rdx+rdx*4]
0x18000407b  add     rcx, rcx
0x18000407e  sub     r8, rcx
0x180004081  mov     rbx, [rdi+r8*8+8]
0x180004086  jmp     short loc_180004091
0x180004088  cmp     [rbx], r9d
0x18000408b  jz      short loc_1800040A4
0x18000408d  mov     rbx, [rbx+8]
0x180004091  test    rbx, rbx
0x180004094  jnz     short loc_180004088
0x180004096  mov     rax, rbx
0x180004099  mov     rbx, [rsp+28h+arg_0]
0x18000409e  add     rsp, 20h
0x1800040a2  pop     rdi
0x1800040a3  retn
0x1800040a4  add     rbx, 10h
0x1800040a8  jz      short loc_180004096
0x1800040aa  cmp     qword ptr [rbx+8], 0
0x1800040af  jnz     short loc_180004096
0x1800040b1  lea     rax, [rdi+4]
0x1800040b5  mov     [rbx+8], rax
0x1800040b9  jmp     short loc_180004096
```
