# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004b10`
- end: `0x140004bcd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x140003ff8`
- `0x140004b10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004b6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004b6a`

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
0x140004b10  mov     [rsp+arg_0], rbx
0x140004b15  push    rdi
0x140004b16  sub     rsp, 20h
0x140004b1a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004b21  xor     ebx, ebx
0x140004b23  test    rdi, rdi
0x140004b26  jz      loc_140004BBF
0x140004b2c  cmp     [rdi+8], rbx
0x140004b30  jnz     short loc_140004B57
0x140004b32  mov     rcx, [rdi]
0x140004b35  lea     rdx, [rsp+28h+arg_8]
0x140004b3a  mov     [rsp+28h+arg_8], rbx
0x140004b3f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004b44  test    eax, eax
0x140004b46  js      short loc_140004B57
0x140004b48  cmp     [rdi+8], rbx
0x140004b4c  jnz     short loc_140004B57
0x140004b4e  mov     rax, [rsp+28h+arg_8]
0x140004b53  mov     [rdi+8], rax
0x140004b57  mov     rax, [rdi+8]
0x140004b5b  lea     rcx, [rax+20h]
0x140004b5f  neg     rax
0x140004b62  sbb     rdi, rdi
0x140004b65  and     rdi, rcx
0x140004b68  jz      short loc_140004BBF
0x140004b6a  call    cs:__imp_GetCurrentThreadId
0x140004b70  mov     r8d, eax
0x140004b73  mov     r9d, eax
0x140004b76  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004b80  shr     r8, 2
0x140004b84  mul     r8
0x140004b87  shr     rdx, 3
0x140004b8b  lea     rcx, [rdx+rdx*4]
0x140004b8f  add     rcx, rcx
0x140004b92  sub     r8, rcx
0x140004b95  mov     rbx, [rdi+r8*8+8]
0x140004b9a  test    rbx, rbx
0x140004b9d  jz      short loc_140004BBF
0x140004b9f  cmp     [rbx], r9d
0x140004ba2  jz      short loc_140004BAA
0x140004ba4  mov     rbx, [rbx+8]
0x140004ba8  jmp     short loc_140004B9A
0x140004baa  add     rbx, 10h
0x140004bae  jz      short loc_140004BBF
0x140004bb0  cmp     qword ptr [rbx+8], 0
0x140004bb5  jnz     short loc_140004BBF
0x140004bb7  lea     rax, [rdi+4]
0x140004bbb  mov     [rbx+8], rax
0x140004bbf  mov     rax, rbx
0x140004bc2  mov     rbx, [rsp+28h+arg_0]
0x140004bc7  add     rsp, 20h
0x140004bcb  pop     rdi
0x140004bcc  retn
```
