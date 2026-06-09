# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140006cc0`
- end: `0x140006d7d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006500`

## callees

- `0x140005730`
- `0x140006cc0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006d1a`
- `KERNEL32!GetCurrentThreadId` at `0x140006d1a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x140006cc0  mov     [rsp+arg_0], rbx
0x140006cc5  push    rdi
0x140006cc6  sub     rsp, 20h
0x140006cca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006cd1  xor     ebx, ebx
0x140006cd3  test    rdi, rdi
0x140006cd6  jz      loc_140006D6F
0x140006cdc  cmp     [rdi+8], rbx
0x140006ce0  jnz     short loc_140006D07
0x140006ce2  mov     rcx, [rdi]
0x140006ce5  lea     rdx, [rsp+28h+arg_8]
0x140006cea  mov     [rsp+28h+arg_8], rbx
0x140006cef  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140006cf4  test    eax, eax
0x140006cf6  js      short loc_140006D07
0x140006cf8  cmp     [rdi+8], rbx
0x140006cfc  jnz     short loc_140006D07
0x140006cfe  mov     rax, [rsp+28h+arg_8]
0x140006d03  mov     [rdi+8], rax
0x140006d07  mov     rax, [rdi+8]
0x140006d0b  lea     rcx, [rax+20h]
0x140006d0f  neg     rax
0x140006d12  sbb     rdi, rdi
0x140006d15  and     rdi, rcx
0x140006d18  jz      short loc_140006D6F
0x140006d1a  call    cs:__imp_GetCurrentThreadId
0x140006d20  mov     r8d, eax
0x140006d23  mov     r9d, eax
0x140006d26  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006d30  shr     r8, 2
0x140006d34  mul     r8
0x140006d37  shr     rdx, 3
0x140006d3b  lea     rcx, [rdx+rdx*4]
0x140006d3f  add     rcx, rcx
0x140006d42  sub     r8, rcx
0x140006d45  mov     rbx, [rdi+r8*8+8]
0x140006d4a  test    rbx, rbx
0x140006d4d  jz      short loc_140006D6F
0x140006d4f  cmp     [rbx], r9d
0x140006d52  jz      short loc_140006D5A
0x140006d54  mov     rbx, [rbx+8]
0x140006d58  jmp     short loc_140006D4A
0x140006d5a  add     rbx, 10h
0x140006d5e  jz      short loc_140006D6F
0x140006d60  cmp     qword ptr [rbx+8], 0
0x140006d65  jnz     short loc_140006D6F
0x140006d67  lea     rax, [rdi+4]
0x140006d6b  mov     [rbx+8], rax
0x140006d6f  mov     rax, rbx
0x140006d72  mov     rbx, [rsp+28h+arg_0]
0x140006d77  add     rsp, 20h
0x140006d7b  pop     rdi
0x140006d7c  retn
```
