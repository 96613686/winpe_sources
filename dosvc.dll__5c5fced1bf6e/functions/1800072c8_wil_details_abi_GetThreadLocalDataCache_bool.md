# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800072c8`
- end: `0x180007385`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d20`

## callees

- `0x180006858`
- `0x1800072c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007322`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007322`

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
0x1800072c8  mov     [rsp+arg_0], rbx
0x1800072cd  push    rdi
0x1800072ce  sub     rsp, 20h
0x1800072d2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800072d9  xor     ebx, ebx
0x1800072db  test    rdi, rdi
0x1800072de  jz      loc_180007377
0x1800072e4  cmp     [rdi+8], rbx
0x1800072e8  jnz     short loc_18000730F
0x1800072ea  mov     rcx, [rdi]
0x1800072ed  lea     rdx, [rsp+28h+arg_8]
0x1800072f2  mov     [rsp+28h+arg_8], rbx
0x1800072f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800072fc  test    eax, eax
0x1800072fe  js      short loc_18000730F
0x180007300  cmp     [rdi+8], rbx
0x180007304  jnz     short loc_18000730F
0x180007306  mov     rax, [rsp+28h+arg_8]
0x18000730b  mov     [rdi+8], rax
0x18000730f  mov     rax, [rdi+8]
0x180007313  lea     rcx, [rax+20h]
0x180007317  neg     rax
0x18000731a  sbb     rdi, rdi
0x18000731d  and     rdi, rcx
0x180007320  jz      short loc_180007377
0x180007322  call    cs:__imp_GetCurrentThreadId
0x180007328  mov     r8d, eax
0x18000732b  mov     r9d, eax
0x18000732e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007338  shr     r8, 2
0x18000733c  mul     r8
0x18000733f  shr     rdx, 3
0x180007343  lea     rcx, [rdx+rdx*4]
0x180007347  add     rcx, rcx
0x18000734a  sub     r8, rcx
0x18000734d  mov     rbx, [rdi+r8*8+8]
0x180007352  test    rbx, rbx
0x180007355  jz      short loc_180007377
0x180007357  cmp     [rbx], r9d
0x18000735a  jz      short loc_180007362
0x18000735c  mov     rbx, [rbx+8]
0x180007360  jmp     short loc_180007352
0x180007362  add     rbx, 10h
0x180007366  jz      short loc_180007377
0x180007368  cmp     qword ptr [rbx+8], 0
0x18000736d  jnz     short loc_180007377
0x18000736f  lea     rax, [rdi+4]
0x180007373  mov     [rbx+8], rax
0x180007377  mov     rax, rbx
0x18000737a  mov     rbx, [rsp+28h+arg_0]
0x18000737f  add     rsp, 20h
0x180007383  pop     rdi
0x180007384  retn
```
