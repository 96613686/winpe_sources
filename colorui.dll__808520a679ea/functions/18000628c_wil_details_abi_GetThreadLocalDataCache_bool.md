# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000628c`
- end: `0x180006347`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a20`

## callees

- `0x180003828`
- `0x18000628c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800062e2`
- `KERNEL32!GetCurrentThreadId` at `0x1800062e2`

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
0x18000628c  mov     [rsp+arg_0], rbx
0x180006291  push    rdi
0x180006292  sub     rsp, 20h
0x180006296  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000629d  xor     ebx, ebx
0x18000629f  test    rdi, rdi
0x1800062a2  jz      short loc_180006322
0x1800062a4  cmp     [rdi+8], rbx
0x1800062a8  jnz     short loc_1800062CF
0x1800062aa  mov     rcx, [rdi]
0x1800062ad  lea     rdx, [rsp+28h+arg_8]
0x1800062b2  mov     [rsp+28h+arg_8], rbx
0x1800062b7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800062bc  test    eax, eax
0x1800062be  js      short loc_1800062CF
0x1800062c0  cmp     [rdi+8], rbx
0x1800062c4  jnz     short loc_1800062CF
0x1800062c6  mov     rax, [rsp+28h+arg_8]
0x1800062cb  mov     [rdi+8], rax
0x1800062cf  mov     rax, [rdi+8]
0x1800062d3  lea     rcx, [rax+20h]
0x1800062d7  neg     rax
0x1800062da  sbb     rdi, rdi
0x1800062dd  and     rdi, rcx
0x1800062e0  jz      short loc_180006322
0x1800062e2  call    cs:__imp_GetCurrentThreadId
0x1800062e8  mov     r8d, eax
0x1800062eb  mov     r9d, eax
0x1800062ee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800062f8  shr     r8, 2
0x1800062fc  mul     r8
0x1800062ff  shr     rdx, 3
0x180006303  lea     rcx, [rdx+rdx*4]
0x180006307  add     rcx, rcx
0x18000630a  sub     r8, rcx
0x18000630d  mov     rbx, [rdi+r8*8+8]
0x180006312  jmp     short loc_18000631D
0x180006314  cmp     [rbx], r9d
0x180006317  jz      short loc_180006330
0x180006319  mov     rbx, [rbx+8]
0x18000631d  test    rbx, rbx
0x180006320  jnz     short loc_180006314
0x180006322  mov     rax, rbx
0x180006325  mov     rbx, [rsp+28h+arg_0]
0x18000632a  add     rsp, 20h
0x18000632e  pop     rdi
0x18000632f  retn
0x180006330  add     rbx, 10h
0x180006334  jz      short loc_180006322
0x180006336  cmp     qword ptr [rbx+8], 0
0x18000633b  jnz     short loc_180006322
0x18000633d  lea     rax, [rdi+4]
0x180006341  mov     [rbx+8], rax
0x180006345  jmp     short loc_180006322
```
