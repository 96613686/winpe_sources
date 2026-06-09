# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006c4c`
- end: `0x180006d07`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063a0`

## callees

- `0x180005a88`
- `0x180006c4c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006ca2`
- `KERNEL32!GetCurrentThreadId` at `0x180006ca2`

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
0x180006c4c  mov     [rsp+arg_0], rbx
0x180006c51  push    rdi
0x180006c52  sub     rsp, 20h
0x180006c56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006c5d  xor     ebx, ebx
0x180006c5f  test    rdi, rdi
0x180006c62  jz      short loc_180006CE2
0x180006c64  cmp     [rdi+8], rbx
0x180006c68  jnz     short loc_180006C8F
0x180006c6a  mov     rcx, [rdi]
0x180006c6d  lea     rdx, [rsp+28h+arg_8]
0x180006c72  mov     [rsp+28h+arg_8], rbx
0x180006c77  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006c7c  test    eax, eax
0x180006c7e  js      short loc_180006C8F
0x180006c80  cmp     [rdi+8], rbx
0x180006c84  jnz     short loc_180006C8F
0x180006c86  mov     rax, [rsp+28h+arg_8]
0x180006c8b  mov     [rdi+8], rax
0x180006c8f  mov     rax, [rdi+8]
0x180006c93  lea     rcx, [rax+20h]
0x180006c97  neg     rax
0x180006c9a  sbb     rdi, rdi
0x180006c9d  and     rdi, rcx
0x180006ca0  jz      short loc_180006CE2
0x180006ca2  call    cs:__imp_GetCurrentThreadId
0x180006ca8  mov     r8d, eax
0x180006cab  mov     r9d, eax
0x180006cae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006cb8  shr     r8, 2
0x180006cbc  mul     r8
0x180006cbf  shr     rdx, 3
0x180006cc3  lea     rcx, [rdx+rdx*4]
0x180006cc7  add     rcx, rcx
0x180006cca  sub     r8, rcx
0x180006ccd  mov     rbx, [rdi+r8*8+8]
0x180006cd2  jmp     short loc_180006CDD
0x180006cd4  cmp     [rbx], r9d
0x180006cd7  jz      short loc_180006CF0
0x180006cd9  mov     rbx, [rbx+8]
0x180006cdd  test    rbx, rbx
0x180006ce0  jnz     short loc_180006CD4
0x180006ce2  mov     rax, rbx
0x180006ce5  mov     rbx, [rsp+28h+arg_0]
0x180006cea  add     rsp, 20h
0x180006cee  pop     rdi
0x180006cef  retn
0x180006cf0  add     rbx, 10h
0x180006cf4  jz      short loc_180006CE2
0x180006cf6  cmp     qword ptr [rbx+8], 0
0x180006cfb  jnz     short loc_180006CE2
0x180006cfd  lea     rax, [rdi+4]
0x180006d01  mov     [rbx+8], rax
0x180006d05  jmp     short loc_180006CE2
```
