# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140014afc`
- end: `0x140014bb7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014320`

## callees

- `0x14001339c`
- `0x140014afc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140014b52`
- `KERNEL32!GetCurrentThreadId` at `0x140014b52`

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
0x140014afc  mov     [rsp+arg_0], rbx
0x140014b01  push    rdi
0x140014b02  sub     rsp, 20h
0x140014b06  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140014b0d  xor     ebx, ebx
0x140014b0f  test    rdi, rdi
0x140014b12  jz      short loc_140014B92
0x140014b14  cmp     [rdi+8], rbx
0x140014b18  jnz     short loc_140014B3F
0x140014b1a  mov     rcx, [rdi]
0x140014b1d  lea     rdx, [rsp+28h+arg_8]
0x140014b22  mov     [rsp+28h+arg_8], rbx
0x140014b27  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140014b2c  test    eax, eax
0x140014b2e  js      short loc_140014B3F
0x140014b30  cmp     [rdi+8], rbx
0x140014b34  jnz     short loc_140014B3F
0x140014b36  mov     rax, [rsp+28h+arg_8]
0x140014b3b  mov     [rdi+8], rax
0x140014b3f  mov     rax, [rdi+8]
0x140014b43  lea     rcx, [rax+20h]
0x140014b47  neg     rax
0x140014b4a  sbb     rdi, rdi
0x140014b4d  and     rdi, rcx
0x140014b50  jz      short loc_140014B92
0x140014b52  call    cs:__imp_GetCurrentThreadId
0x140014b58  mov     r8d, eax
0x140014b5b  mov     r9d, eax
0x140014b5e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140014b68  shr     r8, 2
0x140014b6c  mul     r8
0x140014b6f  shr     rdx, 3
0x140014b73  lea     rcx, [rdx+rdx*4]
0x140014b77  add     rcx, rcx
0x140014b7a  sub     r8, rcx
0x140014b7d  mov     rbx, [rdi+r8*8+8]
0x140014b82  jmp     short loc_140014B8D
0x140014b84  cmp     [rbx], r9d
0x140014b87  jz      short loc_140014BA0
0x140014b89  mov     rbx, [rbx+8]
0x140014b8d  test    rbx, rbx
0x140014b90  jnz     short loc_140014B84
0x140014b92  mov     rax, rbx
0x140014b95  mov     rbx, [rsp+28h+arg_0]
0x140014b9a  add     rsp, 20h
0x140014b9e  pop     rdi
0x140014b9f  retn
0x140014ba0  add     rbx, 10h
0x140014ba4  jz      short loc_140014B92
0x140014ba6  cmp     qword ptr [rbx+8], 0
0x140014bab  jnz     short loc_140014B92
0x140014bad  lea     rax, [rdi+4]
0x140014bb1  mov     [rbx+8], rax
0x140014bb5  jmp     short loc_140014B92
```
