# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18005a7b8`
- end: `0x18005a87c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005a1a0`

## callees

- `0x1800542b4`
- `0x18005a7b8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005a812`
- `KERNEL32!GetCurrentThreadId` at `0x18005a812`

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
0x18005a7b8  mov     [rsp+arg_0], rbx
0x18005a7bd  push    rdi
0x18005a7be  sub     rsp, 20h
0x18005a7c2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18005a7c9  xor     ebx, ebx
0x18005a7cb  test    rdi, rdi
0x18005a7ce  jz      loc_18005A86D
0x18005a7d4  cmp     [rdi+8], rbx
0x18005a7d8  jnz     short loc_18005A7FF
0x18005a7da  mov     rcx, [rdi]
0x18005a7dd  lea     rdx, [rsp+28h+arg_8]
0x18005a7e2  mov     [rsp+28h+arg_8], rbx
0x18005a7e7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18005a7ec  test    eax, eax
0x18005a7ee  js      short loc_18005A7FF
0x18005a7f0  cmp     [rdi+8], rbx
0x18005a7f4  jnz     short loc_18005A7FF
0x18005a7f6  mov     rax, [rsp+28h+arg_8]
0x18005a7fb  mov     [rdi+8], rax
0x18005a7ff  mov     rax, [rdi+8]
0x18005a803  lea     rcx, [rax+20h]
0x18005a807  neg     rax
0x18005a80a  sbb     rdi, rdi
0x18005a80d  and     rdi, rcx
0x18005a810  jz      short loc_18005A86D
0x18005a812  call    cs:__imp_GetCurrentThreadId
0x18005a819  nop     dword ptr [rax+rax+00h]
0x18005a81e  mov     r8d, eax
0x18005a821  mov     r9d, eax
0x18005a824  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005a82e  shr     r8, 2
0x18005a832  mul     r8
0x18005a835  shr     rdx, 3
0x18005a839  lea     rcx, [rdx+rdx*4]
0x18005a83d  add     rcx, rcx
0x18005a840  sub     r8, rcx
0x18005a843  mov     rbx, [rdi+r8*8+8]
0x18005a848  test    rbx, rbx
0x18005a84b  jz      short loc_18005A86D
0x18005a84d  cmp     [rbx], r9d
0x18005a850  jz      short loc_18005A858
0x18005a852  mov     rbx, [rbx+8]
0x18005a856  jmp     short loc_18005A848
0x18005a858  add     rbx, 10h
0x18005a85c  jz      short loc_18005A86D
0x18005a85e  cmp     qword ptr [rbx+8], 0
0x18005a863  jnz     short loc_18005A86D
0x18005a865  lea     rax, [rdi+4]
0x18005a869  mov     [rbx+8], rax
0x18005a86d  mov     rax, rbx
0x18005a870  mov     rbx, [rsp+28h+arg_0]
0x18005a875  add     rsp, 20h
0x18005a879  pop     rdi
0x18005a87a  retn
```
