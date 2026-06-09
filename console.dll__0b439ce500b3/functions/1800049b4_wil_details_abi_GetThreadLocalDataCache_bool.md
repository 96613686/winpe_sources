# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800049b4`
- end: `0x180004a78`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004300`

## callees

- `0x180003d7c`
- `0x1800049b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a0e`

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
0x1800049b4  mov     [rsp+arg_0], rbx
0x1800049b9  push    rdi
0x1800049ba  sub     rsp, 20h
0x1800049be  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800049c5  xor     ebx, ebx
0x1800049c7  test    rdi, rdi
0x1800049ca  jz      loc_180004A69
0x1800049d0  cmp     [rdi+8], rbx
0x1800049d4  jnz     short loc_1800049FB
0x1800049d6  mov     rcx, [rdi]
0x1800049d9  lea     rdx, [rsp+28h+arg_8]
0x1800049de  mov     [rsp+28h+arg_8], rbx
0x1800049e3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800049e8  test    eax, eax
0x1800049ea  js      short loc_1800049FB
0x1800049ec  cmp     [rdi+8], rbx
0x1800049f0  jnz     short loc_1800049FB
0x1800049f2  mov     rax, [rsp+28h+arg_8]
0x1800049f7  mov     [rdi+8], rax
0x1800049fb  mov     rax, [rdi+8]
0x1800049ff  lea     rcx, [rax+20h]
0x180004a03  neg     rax
0x180004a06  sbb     rdi, rdi
0x180004a09  and     rdi, rcx
0x180004a0c  jz      short loc_180004A69
0x180004a0e  call    cs:__imp_GetCurrentThreadId
0x180004a15  nop     dword ptr [rax+rax+00h]
0x180004a1a  mov     r8d, eax
0x180004a1d  mov     r9d, eax
0x180004a20  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a2a  shr     r8, 2
0x180004a2e  mul     r8
0x180004a31  shr     rdx, 3
0x180004a35  lea     rcx, [rdx+rdx*4]
0x180004a39  add     rcx, rcx
0x180004a3c  sub     r8, rcx
0x180004a3f  mov     rbx, [rdi+r8*8+8]
0x180004a44  test    rbx, rbx
0x180004a47  jz      short loc_180004A69
0x180004a49  cmp     [rbx], r9d
0x180004a4c  jz      short loc_180004A54
0x180004a4e  mov     rbx, [rbx+8]
0x180004a52  jmp     short loc_180004A44
0x180004a54  add     rbx, 10h
0x180004a58  jz      short loc_180004A69
0x180004a5a  cmp     qword ptr [rbx+8], 0
0x180004a5f  jnz     short loc_180004A69
0x180004a61  lea     rax, [rdi+4]
0x180004a65  mov     [rbx+8], rax
0x180004a69  mov     rax, rbx
0x180004a6c  mov     rbx, [rsp+28h+arg_0]
0x180004a71  add     rsp, 20h
0x180004a75  pop     rdi
0x180004a76  retn
```
