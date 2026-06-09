# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004890`
- end: `0x18000494d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041d0`

## callees

- `0x180003c38`
- `0x180004890`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800048ea`
- `KERNEL32!GetCurrentThreadId` at `0x1800048ea`

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
0x180004890  mov     [rsp+arg_0], rbx
0x180004895  push    rdi
0x180004896  sub     rsp, 20h
0x18000489a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800048a1  xor     ebx, ebx
0x1800048a3  test    rdi, rdi
0x1800048a6  jz      loc_18000493F
0x1800048ac  cmp     [rdi+8], rbx
0x1800048b0  jnz     short loc_1800048D7
0x1800048b2  mov     rcx, [rdi]
0x1800048b5  lea     rdx, [rsp+28h+arg_8]
0x1800048ba  mov     [rsp+28h+arg_8], rbx
0x1800048bf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800048c4  test    eax, eax
0x1800048c6  js      short loc_1800048D7
0x1800048c8  cmp     [rdi+8], rbx
0x1800048cc  jnz     short loc_1800048D7
0x1800048ce  mov     rax, [rsp+28h+arg_8]
0x1800048d3  mov     [rdi+8], rax
0x1800048d7  mov     rax, [rdi+8]
0x1800048db  lea     rcx, [rax+20h]
0x1800048df  neg     rax
0x1800048e2  sbb     rdi, rdi
0x1800048e5  and     rdi, rcx
0x1800048e8  jz      short loc_18000493F
0x1800048ea  call    cs:__imp_GetCurrentThreadId
0x1800048f0  mov     r8d, eax
0x1800048f3  mov     r9d, eax
0x1800048f6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004900  shr     r8, 2
0x180004904  mul     r8
0x180004907  shr     rdx, 3
0x18000490b  lea     rcx, [rdx+rdx*4]
0x18000490f  add     rcx, rcx
0x180004912  sub     r8, rcx
0x180004915  mov     rbx, [rdi+r8*8+8]
0x18000491a  test    rbx, rbx
0x18000491d  jz      short loc_18000493F
0x18000491f  cmp     [rbx], r9d
0x180004922  jz      short loc_18000492A
0x180004924  mov     rbx, [rbx+8]
0x180004928  jmp     short loc_18000491A
0x18000492a  add     rbx, 10h
0x18000492e  jz      short loc_18000493F
0x180004930  cmp     qword ptr [rbx+8], 0
0x180004935  jnz     short loc_18000493F
0x180004937  lea     rax, [rdi+4]
0x18000493b  mov     [rbx+8], rax
0x18000493f  mov     rax, rbx
0x180004942  mov     rbx, [rsp+28h+arg_0]
0x180004947  add     rsp, 20h
0x18000494b  pop     rdi
0x18000494c  retn
```
