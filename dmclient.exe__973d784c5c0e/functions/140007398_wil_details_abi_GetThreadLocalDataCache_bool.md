# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140007398`
- end: `0x14000745e`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006be0`

## callees

- `0x140004ce4`
- `0x140007398`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400073f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400073f2`

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
0x140007398  mov     [rsp+arg_0], rbx
0x14000739d  push    rdi
0x14000739e  sub     rsp, 20h
0x1400073a2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400073a9  xor     ebx, ebx
0x1400073ab  test    rdi, rdi
0x1400073ae  jz      loc_140007438
0x1400073b4  cmp     [rdi+8], rbx
0x1400073b8  jnz     short loc_1400073DF
0x1400073ba  mov     rcx, [rdi]
0x1400073bd  lea     rdx, [rsp+28h+arg_8]
0x1400073c2  mov     [rsp+28h+arg_8], rbx
0x1400073c7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400073cc  test    eax, eax
0x1400073ce  js      short loc_1400073DF
0x1400073d0  cmp     [rdi+8], rbx
0x1400073d4  jnz     short loc_1400073DF
0x1400073d6  mov     rax, [rsp+28h+arg_8]
0x1400073db  mov     [rdi+8], rax
0x1400073df  mov     rax, [rdi+8]
0x1400073e3  lea     rcx, [rax+20h]
0x1400073e7  neg     rax
0x1400073ea  sbb     rdi, rdi
0x1400073ed  and     rdi, rcx
0x1400073f0  jz      short loc_140007438
0x1400073f2  call    cs:__imp_GetCurrentThreadId
0x1400073f9  nop     dword ptr [rax+rax+00h]
0x1400073fe  mov     r8d, eax
0x140007401  mov     r9d, eax
0x140007404  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000740e  shr     r8, 2
0x140007412  mul     r8
0x140007415  shr     rdx, 3
0x140007419  lea     rcx, [rdx+rdx*4]
0x14000741d  add     rcx, rcx
0x140007420  sub     r8, rcx
0x140007423  mov     rbx, [rdi+r8*8+8]
0x140007428  jmp     short loc_140007433
0x14000742a  cmp     [rbx], r9d
0x14000742d  jz      short loc_140007447
0x14000742f  mov     rbx, [rbx+8]
0x140007433  test    rbx, rbx
0x140007436  jnz     short loc_14000742A
0x140007438  mov     rax, rbx
0x14000743b  mov     rbx, [rsp+28h+arg_0]
0x140007440  add     rsp, 20h
0x140007444  pop     rdi
0x140007445  retn
0x140007447  add     rbx, 10h
0x14000744b  jz      short loc_140007438
0x14000744d  cmp     qword ptr [rbx+8], 0
0x140007452  jnz     short loc_140007438
0x140007454  lea     rax, [rdi+4]
0x140007458  mov     [rbx+8], rax
0x14000745c  jmp     short loc_140007438
```
