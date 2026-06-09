# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009f70`
- end: `0x18000a02b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009850`

## callees

- `0x180008828`
- `0x180009f70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009fc6`
- `KERNEL32!GetCurrentThreadId` at `0x180009fc6`

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
0x180009f70  mov     [rsp+arg_0], rbx
0x180009f75  push    rdi
0x180009f76  sub     rsp, 20h
0x180009f7a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009f81  xor     ebx, ebx
0x180009f83  test    rdi, rdi
0x180009f86  jz      short loc_18000A006
0x180009f88  cmp     [rdi+8], rbx
0x180009f8c  jnz     short loc_180009FB3
0x180009f8e  mov     rcx, [rdi]
0x180009f91  lea     rdx, [rsp+28h+arg_8]
0x180009f96  mov     [rsp+28h+arg_8], rbx
0x180009f9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009fa0  test    eax, eax
0x180009fa2  js      short loc_180009FB3
0x180009fa4  cmp     [rdi+8], rbx
0x180009fa8  jnz     short loc_180009FB3
0x180009faa  mov     rax, [rsp+28h+arg_8]
0x180009faf  mov     [rdi+8], rax
0x180009fb3  mov     rax, [rdi+8]
0x180009fb7  lea     rcx, [rax+20h]
0x180009fbb  neg     rax
0x180009fbe  sbb     rdi, rdi
0x180009fc1  and     rdi, rcx
0x180009fc4  jz      short loc_18000A006
0x180009fc6  call    cs:__imp_GetCurrentThreadId
0x180009fcc  mov     r8d, eax
0x180009fcf  mov     r9d, eax
0x180009fd2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009fdc  shr     r8, 2
0x180009fe0  mul     r8
0x180009fe3  shr     rdx, 3
0x180009fe7  lea     rcx, [rdx+rdx*4]
0x180009feb  add     rcx, rcx
0x180009fee  sub     r8, rcx
0x180009ff1  mov     rbx, [rdi+r8*8+8]
0x180009ff6  jmp     short loc_18000A001
0x180009ff8  cmp     [rbx], r9d
0x180009ffb  jz      short loc_18000A014
0x180009ffd  mov     rbx, [rbx+8]
0x18000a001  test    rbx, rbx
0x18000a004  jnz     short loc_180009FF8
0x18000a006  mov     rax, rbx
0x18000a009  mov     rbx, [rsp+28h+arg_0]
0x18000a00e  add     rsp, 20h
0x18000a012  pop     rdi
0x18000a013  retn
0x18000a014  add     rbx, 10h
0x18000a018  jz      short loc_18000A006
0x18000a01a  cmp     qword ptr [rbx+8], 0
0x18000a01f  jnz     short loc_18000A006
0x18000a021  lea     rax, [rdi+4]
0x18000a025  mov     [rbx+8], rax
0x18000a029  jmp     short loc_18000A006
```
