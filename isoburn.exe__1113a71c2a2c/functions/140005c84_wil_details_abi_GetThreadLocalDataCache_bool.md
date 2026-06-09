# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005c84`
- end: `0x140005d3f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004dd0`

## callees

- `0x140003ecc`
- `0x140005c84`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005cda`
- `KERNEL32!GetCurrentThreadId` at `0x140005cda`

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
0x140005c84  mov     [rsp+arg_0], rbx
0x140005c89  push    rdi
0x140005c8a  sub     rsp, 20h
0x140005c8e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005c95  xor     ebx, ebx
0x140005c97  test    rdi, rdi
0x140005c9a  jz      short loc_140005D1A
0x140005c9c  cmp     [rdi+8], rbx
0x140005ca0  jnz     short loc_140005CC7
0x140005ca2  mov     rcx, [rdi]
0x140005ca5  lea     rdx, [rsp+28h+arg_8]
0x140005caa  mov     [rsp+28h+arg_8], rbx
0x140005caf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005cb4  test    eax, eax
0x140005cb6  js      short loc_140005CC7
0x140005cb8  cmp     [rdi+8], rbx
0x140005cbc  jnz     short loc_140005CC7
0x140005cbe  mov     rax, [rsp+28h+arg_8]
0x140005cc3  mov     [rdi+8], rax
0x140005cc7  mov     rax, [rdi+8]
0x140005ccb  lea     rcx, [rax+20h]
0x140005ccf  neg     rax
0x140005cd2  sbb     rdi, rdi
0x140005cd5  and     rdi, rcx
0x140005cd8  jz      short loc_140005D1A
0x140005cda  call    cs:__imp_GetCurrentThreadId
0x140005ce0  mov     r8d, eax
0x140005ce3  mov     r9d, eax
0x140005ce6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005cf0  shr     r8, 2
0x140005cf4  mul     r8
0x140005cf7  shr     rdx, 3
0x140005cfb  lea     rcx, [rdx+rdx*4]
0x140005cff  add     rcx, rcx
0x140005d02  sub     r8, rcx
0x140005d05  mov     rbx, [rdi+r8*8+8]
0x140005d0a  jmp     short loc_140005D15
0x140005d0c  cmp     [rbx], r9d
0x140005d0f  jz      short loc_140005D28
0x140005d11  mov     rbx, [rbx+8]
0x140005d15  test    rbx, rbx
0x140005d18  jnz     short loc_140005D0C
0x140005d1a  mov     rax, rbx
0x140005d1d  mov     rbx, [rsp+28h+arg_0]
0x140005d22  add     rsp, 20h
0x140005d26  pop     rdi
0x140005d27  retn
0x140005d28  add     rbx, 10h
0x140005d2c  jz      short loc_140005D1A
0x140005d2e  cmp     qword ptr [rbx+8], 0
0x140005d33  jnz     short loc_140005D1A
0x140005d35  lea     rax, [rdi+4]
0x140005d39  mov     [rbx+8], rax
0x140005d3d  jmp     short loc_140005D1A
```
