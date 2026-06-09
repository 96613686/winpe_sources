# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800079c8`
- end: `0x180007a85`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007350`

## callees

- `0x180006ea8`
- `0x1800079c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a22`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x1800079c8  mov     [rsp+arg_0], rbx
0x1800079cd  push    rdi
0x1800079ce  sub     rsp, 20h
0x1800079d2  xor     ebx, ebx
0x1800079d4  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800079db  test    rdi, rdi
0x1800079de  jz      loc_180007A77
0x1800079e4  cmp     [rdi+8], rbx
0x1800079e8  jnz     short loc_180007A0F
0x1800079ea  mov     [rsp+28h+arg_8], rbx
0x1800079ef  lea     rdx, [rsp+28h+arg_8]
0x1800079f4  mov     rcx, [rdi]
0x1800079f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800079fc  test    eax, eax
0x1800079fe  js      short loc_180007A0F
0x180007a00  cmp     [rdi+8], rbx
0x180007a04  jnz     short loc_180007A0F
0x180007a06  mov     rax, [rsp+28h+arg_8]
0x180007a0b  mov     [rdi+8], rax
0x180007a0f  mov     rcx, [rdi+8]
0x180007a13  lea     rax, [rcx+20h]
0x180007a17  neg     rcx
0x180007a1a  sbb     rdi, rdi
0x180007a1d  and     rdi, rax
0x180007a20  jz      short loc_180007A77
0x180007a22  call    cs:__imp_GetCurrentThreadId
0x180007a28  mov     r9d, eax
0x180007a2b  mov     r8d, eax
0x180007a2e  shr     r8, 2
0x180007a32  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007a3c  mul     r8
0x180007a3f  shr     rdx, 3
0x180007a43  lea     rcx, [rdx+rdx*4]
0x180007a47  add     rcx, rcx
0x180007a4a  sub     r8, rcx
0x180007a4d  mov     rbx, [rdi+r8*8+8]
0x180007a52  test    rbx, rbx
0x180007a55  jz      short loc_180007A77
0x180007a57  cmp     [rbx], r9d
0x180007a5a  jz      short loc_180007A62
0x180007a5c  mov     rbx, [rbx+8]
0x180007a60  jmp     short loc_180007A52
0x180007a62  add     rbx, 10h
0x180007a66  jz      short loc_180007A77
0x180007a68  cmp     qword ptr [rbx+8], 0
0x180007a6d  jnz     short loc_180007A77
0x180007a6f  lea     rax, [rdi+4]
0x180007a73  mov     [rbx+8], rax
0x180007a77  mov     rax, rbx
0x180007a7a  mov     rbx, [rsp+28h+arg_0]
0x180007a7f  add     rsp, 20h
0x180007a83  pop     rdi
0x180007a84  retn
```
