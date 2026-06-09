# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140003c18`
- end: `0x140003cd5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400035a0`

## callees

- `0x140002f70`
- `0x140003c18`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003c72`
- `KERNEL32!GetCurrentThreadId` at `0x140003c72`

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
0x140003c18  mov     [rsp+arg_0], rbx
0x140003c1d  push    rdi
0x140003c1e  sub     rsp, 20h
0x140003c22  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140003c29  xor     ebx, ebx
0x140003c2b  test    rdi, rdi
0x140003c2e  jz      loc_140003CC7
0x140003c34  cmp     [rdi+8], rbx
0x140003c38  jnz     short loc_140003C5F
0x140003c3a  mov     rcx, [rdi]
0x140003c3d  lea     rdx, [rsp+28h+arg_8]
0x140003c42  mov     [rsp+28h+arg_8], rbx
0x140003c47  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140003c4c  test    eax, eax
0x140003c4e  js      short loc_140003C5F
0x140003c50  cmp     [rdi+8], rbx
0x140003c54  jnz     short loc_140003C5F
0x140003c56  mov     rax, [rsp+28h+arg_8]
0x140003c5b  mov     [rdi+8], rax
0x140003c5f  mov     rax, [rdi+8]
0x140003c63  lea     rcx, [rax+20h]
0x140003c67  neg     rax
0x140003c6a  sbb     rdi, rdi
0x140003c6d  and     rdi, rcx
0x140003c70  jz      short loc_140003CC7
0x140003c72  call    cs:__imp_GetCurrentThreadId
0x140003c78  mov     r8d, eax
0x140003c7b  mov     r9d, eax
0x140003c7e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003c88  shr     r8, 2
0x140003c8c  mul     r8
0x140003c8f  shr     rdx, 3
0x140003c93  lea     rcx, [rdx+rdx*4]
0x140003c97  add     rcx, rcx
0x140003c9a  sub     r8, rcx
0x140003c9d  mov     rbx, [rdi+r8*8+8]
0x140003ca2  test    rbx, rbx
0x140003ca5  jz      short loc_140003CC7
0x140003ca7  cmp     [rbx], r9d
0x140003caa  jz      short loc_140003CB2
0x140003cac  mov     rbx, [rbx+8]
0x140003cb0  jmp     short loc_140003CA2
0x140003cb2  add     rbx, 10h
0x140003cb6  jz      short loc_140003CC7
0x140003cb8  cmp     qword ptr [rbx+8], 0
0x140003cbd  jnz     short loc_140003CC7
0x140003cbf  lea     rax, [rdi+4]
0x140003cc3  mov     [rbx+8], rax
0x140003cc7  mov     rax, rbx
0x140003cca  mov     rbx, [rsp+28h+arg_0]
0x140003ccf  add     rsp, 20h
0x140003cd3  pop     rdi
0x140003cd4  retn
```
