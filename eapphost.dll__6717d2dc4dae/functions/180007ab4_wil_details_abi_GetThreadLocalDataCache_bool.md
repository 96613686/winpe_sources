# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007ab4`
- end: `0x180007b71`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007430`

## callees

- `0x180005158`
- `0x180007ab4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

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
0x180007ab4  mov     [rsp+arg_0], rbx
0x180007ab9  push    rdi
0x180007aba  sub     rsp, 20h
0x180007abe  xor     ebx, ebx
0x180007ac0  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007ac7  test    rdi, rdi
0x180007aca  jz      loc_180007B63
0x180007ad0  cmp     [rdi+8], rbx
0x180007ad4  jnz     short loc_180007AFB
0x180007ad6  mov     [rsp+28h+arg_8], rbx
0x180007adb  lea     rdx, [rsp+28h+arg_8]
0x180007ae0  mov     rcx, [rdi]
0x180007ae3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007ae8  test    eax, eax
0x180007aea  js      short loc_180007AFB
0x180007aec  cmp     [rdi+8], rbx
0x180007af0  jnz     short loc_180007AFB
0x180007af2  mov     rax, [rsp+28h+arg_8]
0x180007af7  mov     [rdi+8], rax
0x180007afb  mov     rcx, [rdi+8]
0x180007aff  lea     rax, [rcx+20h]
0x180007b03  neg     rcx
0x180007b06  sbb     rdi, rdi
0x180007b09  and     rdi, rax
0x180007b0c  jz      short loc_180007B63
0x180007b0e  call    cs:__imp_GetCurrentThreadId
0x180007b14  mov     r9d, eax
0x180007b17  mov     r8d, eax
0x180007b1a  shr     r8, 2
0x180007b1e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007b28  mul     r8
0x180007b2b  shr     rdx, 3
0x180007b2f  lea     rcx, [rdx+rdx*4]
0x180007b33  add     rcx, rcx
0x180007b36  sub     r8, rcx
0x180007b39  mov     rbx, [rdi+r8*8+8]
0x180007b3e  test    rbx, rbx
0x180007b41  jz      short loc_180007B63
0x180007b43  cmp     [rbx], r9d
0x180007b46  jz      short loc_180007B4E
0x180007b48  mov     rbx, [rbx+8]
0x180007b4c  jmp     short loc_180007B3E
0x180007b4e  add     rbx, 10h
0x180007b52  jz      short loc_180007B63
0x180007b54  cmp     qword ptr [rbx+8], 0
0x180007b59  jnz     short loc_180007B63
0x180007b5b  lea     rax, [rdi+4]
0x180007b5f  mov     [rbx+8], rax
0x180007b63  mov     rax, rbx
0x180007b66  mov     rbx, [rsp+28h+arg_0]
0x180007b6b  add     rsp, 20h
0x180007b6f  pop     rdi
0x180007b70  retn
```
