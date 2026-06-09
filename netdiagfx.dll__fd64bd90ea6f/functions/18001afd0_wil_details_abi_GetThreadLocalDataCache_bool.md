# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001afd0`
- end: `0x18001b08d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a7d0`

## callees

- `0x1800182ac`
- `0x18001afd0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001b02a`
- `KERNEL32!GetCurrentThreadId` at `0x18001b02a`

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
0x18001afd0  mov     [rsp+arg_0], rbx
0x18001afd5  push    rdi
0x18001afd6  sub     rsp, 20h
0x18001afda  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001afe1  xor     ebx, ebx
0x18001afe3  test    rdi, rdi
0x18001afe6  jz      loc_18001B07F
0x18001afec  cmp     [rdi+8], rbx
0x18001aff0  jnz     short loc_18001B017
0x18001aff2  mov     rcx, [rdi]
0x18001aff5  lea     rdx, [rsp+28h+arg_8]
0x18001affa  mov     [rsp+28h+arg_8], rbx
0x18001afff  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001b004  test    eax, eax
0x18001b006  js      short loc_18001B017
0x18001b008  cmp     [rdi+8], rbx
0x18001b00c  jnz     short loc_18001B017
0x18001b00e  mov     rax, [rsp+28h+arg_8]
0x18001b013  mov     [rdi+8], rax
0x18001b017  mov     rax, [rdi+8]
0x18001b01b  lea     rcx, [rax+20h]
0x18001b01f  neg     rax
0x18001b022  sbb     rdi, rdi
0x18001b025  and     rdi, rcx
0x18001b028  jz      short loc_18001B07F
0x18001b02a  call    cs:__imp_GetCurrentThreadId
0x18001b030  mov     r8d, eax
0x18001b033  mov     r9d, eax
0x18001b036  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001b040  shr     r8, 2
0x18001b044  mul     r8
0x18001b047  shr     rdx, 3
0x18001b04b  lea     rcx, [rdx+rdx*4]
0x18001b04f  add     rcx, rcx
0x18001b052  sub     r8, rcx
0x18001b055  mov     rbx, [rdi+r8*8+8]
0x18001b05a  test    rbx, rbx
0x18001b05d  jz      short loc_18001B07F
0x18001b05f  cmp     [rbx], r9d
0x18001b062  jz      short loc_18001B06A
0x18001b064  mov     rbx, [rbx+8]
0x18001b068  jmp     short loc_18001B05A
0x18001b06a  add     rbx, 10h
0x18001b06e  jz      short loc_18001B07F
0x18001b070  cmp     qword ptr [rbx+8], 0
0x18001b075  jnz     short loc_18001B07F
0x18001b077  lea     rax, [rdi+4]
0x18001b07b  mov     [rbx+8], rax
0x18001b07f  mov     rax, rbx
0x18001b082  mov     rbx, [rsp+28h+arg_0]
0x18001b087  add     rsp, 20h
0x18001b08b  pop     rdi
0x18001b08c  retn
```
