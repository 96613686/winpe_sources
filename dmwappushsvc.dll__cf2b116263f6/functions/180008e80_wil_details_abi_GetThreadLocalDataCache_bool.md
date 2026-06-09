# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008e80`
- end: `0x180008f3d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008b30`

## callees

- `0x180007ee0`
- `0x180008e80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eda`

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
0x180008e80  mov     [rsp+arg_0], rbx
0x180008e85  push    rdi
0x180008e86  sub     rsp, 20h
0x180008e8a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008e91  xor     ebx, ebx
0x180008e93  test    rdi, rdi
0x180008e96  jz      loc_180008F2F
0x180008e9c  cmp     [rdi+8], rbx
0x180008ea0  jnz     short loc_180008EC7
0x180008ea2  mov     rcx, [rdi]
0x180008ea5  lea     rdx, [rsp+28h+arg_8]
0x180008eaa  mov     [rsp+28h+arg_8], rbx
0x180008eaf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008eb4  test    eax, eax
0x180008eb6  js      short loc_180008EC7
0x180008eb8  cmp     [rdi+8], rbx
0x180008ebc  jnz     short loc_180008EC7
0x180008ebe  mov     rax, [rsp+28h+arg_8]
0x180008ec3  mov     [rdi+8], rax
0x180008ec7  mov     rax, [rdi+8]
0x180008ecb  lea     rcx, [rax+20h]
0x180008ecf  neg     rax
0x180008ed2  sbb     rdi, rdi
0x180008ed5  and     rdi, rcx
0x180008ed8  jz      short loc_180008F2F
0x180008eda  call    cs:__imp_GetCurrentThreadId
0x180008ee0  mov     r8d, eax
0x180008ee3  mov     r9d, eax
0x180008ee6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008ef0  shr     r8, 2
0x180008ef4  mul     r8
0x180008ef7  shr     rdx, 3
0x180008efb  lea     rcx, [rdx+rdx*4]
0x180008eff  add     rcx, rcx
0x180008f02  sub     r8, rcx
0x180008f05  mov     rbx, [rdi+r8*8+8]
0x180008f0a  test    rbx, rbx
0x180008f0d  jz      short loc_180008F2F
0x180008f0f  cmp     [rbx], r9d
0x180008f12  jz      short loc_180008F1A
0x180008f14  mov     rbx, [rbx+8]
0x180008f18  jmp     short loc_180008F0A
0x180008f1a  add     rbx, 10h
0x180008f1e  jz      short loc_180008F2F
0x180008f20  cmp     qword ptr [rbx+8], 0
0x180008f25  jnz     short loc_180008F2F
0x180008f27  lea     rax, [rdi+4]
0x180008f2b  mov     [rbx+8], rax
0x180008f2f  mov     rax, rbx
0x180008f32  mov     rbx, [rsp+28h+arg_0]
0x180008f37  add     rsp, 20h
0x180008f3b  pop     rdi
0x180008f3c  retn
```
