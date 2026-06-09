# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140003c2c`
- end: `0x140003ce7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003450`

## callees

- `0x140002b44`
- `0x140003c2c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003c82`
- `KERNEL32!GetCurrentThreadId` at `0x140003c82`

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
0x140003c2c  mov     [rsp+arg_0], rbx
0x140003c31  push    rdi
0x140003c32  sub     rsp, 20h
0x140003c36  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140003c3d  xor     ebx, ebx
0x140003c3f  test    rdi, rdi
0x140003c42  jz      short loc_140003CC2
0x140003c44  cmp     [rdi+8], rbx
0x140003c48  jnz     short loc_140003C6F
0x140003c4a  mov     rcx, [rdi]
0x140003c4d  lea     rdx, [rsp+28h+arg_8]
0x140003c52  mov     [rsp+28h+arg_8], rbx
0x140003c57  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140003c5c  test    eax, eax
0x140003c5e  js      short loc_140003C6F
0x140003c60  cmp     [rdi+8], rbx
0x140003c64  jnz     short loc_140003C6F
0x140003c66  mov     rax, [rsp+28h+arg_8]
0x140003c6b  mov     [rdi+8], rax
0x140003c6f  mov     rax, [rdi+8]
0x140003c73  lea     rcx, [rax+20h]
0x140003c77  neg     rax
0x140003c7a  sbb     rdi, rdi
0x140003c7d  and     rdi, rcx
0x140003c80  jz      short loc_140003CC2
0x140003c82  call    cs:__imp_GetCurrentThreadId
0x140003c88  mov     r8d, eax
0x140003c8b  mov     r9d, eax
0x140003c8e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003c98  shr     r8, 2
0x140003c9c  mul     r8
0x140003c9f  shr     rdx, 3
0x140003ca3  lea     rcx, [rdx+rdx*4]
0x140003ca7  add     rcx, rcx
0x140003caa  sub     r8, rcx
0x140003cad  mov     rbx, [rdi+r8*8+8]
0x140003cb2  jmp     short loc_140003CBD
0x140003cb4  cmp     [rbx], r9d
0x140003cb7  jz      short loc_140003CD0
0x140003cb9  mov     rbx, [rbx+8]
0x140003cbd  test    rbx, rbx
0x140003cc0  jnz     short loc_140003CB4
0x140003cc2  mov     rax, rbx
0x140003cc5  mov     rbx, [rsp+28h+arg_0]
0x140003cca  add     rsp, 20h
0x140003cce  pop     rdi
0x140003ccf  retn
0x140003cd0  add     rbx, 10h
0x140003cd4  jz      short loc_140003CC2
0x140003cd6  cmp     qword ptr [rbx+8], 0
0x140003cdb  jnz     short loc_140003CC2
0x140003cdd  lea     rax, [rdi+4]
0x140003ce1  mov     [rbx+8], rax
0x140003ce5  jmp     short loc_140003CC2
```
