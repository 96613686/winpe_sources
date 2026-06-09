# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006d80`
- end: `0x180006e3b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006310`

## callees

- `0x1800048f8`
- `0x180006d80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dd6`

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
0x180006d80  mov     [rsp+arg_0], rbx
0x180006d85  push    rdi
0x180006d86  sub     rsp, 20h
0x180006d8a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006d91  xor     ebx, ebx
0x180006d93  test    rdi, rdi
0x180006d96  jz      short loc_180006E16
0x180006d98  cmp     [rdi+8], rbx
0x180006d9c  jnz     short loc_180006DC3
0x180006d9e  mov     rcx, [rdi]
0x180006da1  lea     rdx, [rsp+28h+arg_8]
0x180006da6  mov     [rsp+28h+arg_8], rbx
0x180006dab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006db0  test    eax, eax
0x180006db2  js      short loc_180006DC3
0x180006db4  cmp     [rdi+8], rbx
0x180006db8  jnz     short loc_180006DC3
0x180006dba  mov     rax, [rsp+28h+arg_8]
0x180006dbf  mov     [rdi+8], rax
0x180006dc3  mov     rax, [rdi+8]
0x180006dc7  lea     rcx, [rax+20h]
0x180006dcb  neg     rax
0x180006dce  sbb     rdi, rdi
0x180006dd1  and     rdi, rcx
0x180006dd4  jz      short loc_180006E16
0x180006dd6  call    cs:__imp_GetCurrentThreadId
0x180006ddc  mov     r8d, eax
0x180006ddf  mov     r9d, eax
0x180006de2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006dec  shr     r8, 2
0x180006df0  mul     r8
0x180006df3  shr     rdx, 3
0x180006df7  lea     rcx, [rdx+rdx*4]
0x180006dfb  add     rcx, rcx
0x180006dfe  sub     r8, rcx
0x180006e01  mov     rbx, [rdi+r8*8+8]
0x180006e06  jmp     short loc_180006E11
0x180006e08  cmp     [rbx], r9d
0x180006e0b  jz      short loc_180006E24
0x180006e0d  mov     rbx, [rbx+8]
0x180006e11  test    rbx, rbx
0x180006e14  jnz     short loc_180006E08
0x180006e16  mov     rax, rbx
0x180006e19  mov     rbx, [rsp+28h+arg_0]
0x180006e1e  add     rsp, 20h
0x180006e22  pop     rdi
0x180006e23  retn
0x180006e24  add     rbx, 10h
0x180006e28  jz      short loc_180006E16
0x180006e2a  cmp     qword ptr [rbx+8], 0
0x180006e2f  jnz     short loc_180006E16
0x180006e31  lea     rax, [rdi+4]
0x180006e35  mov     [rbx+8], rax
0x180006e39  jmp     short loc_180006E16
```
