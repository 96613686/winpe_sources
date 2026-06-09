# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000efb0`
- end: `0x14000f076`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e910`

## callees

- `0x14000e5f8`
- `0x14000efb0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000f00a`
- `KERNEL32!GetCurrentThreadId` at `0x14000f00a`

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
0x14000efb0  mov     [rsp+arg_0], rbx
0x14000efb5  push    rdi
0x14000efb6  sub     rsp, 20h
0x14000efba  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000efc1  xor     ebx, ebx
0x14000efc3  test    rdi, rdi
0x14000efc6  jz      loc_14000F050
0x14000efcc  cmp     [rdi+8], rbx
0x14000efd0  jnz     short loc_14000EFF7
0x14000efd2  mov     rcx, [rdi]
0x14000efd5  lea     rdx, [rsp+28h+arg_8]
0x14000efda  mov     [rsp+28h+arg_8], rbx
0x14000efdf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000efe4  test    eax, eax
0x14000efe6  js      short loc_14000EFF7
0x14000efe8  cmp     [rdi+8], rbx
0x14000efec  jnz     short loc_14000EFF7
0x14000efee  mov     rax, [rsp+28h+arg_8]
0x14000eff3  mov     [rdi+8], rax
0x14000eff7  mov     rax, [rdi+8]
0x14000effb  lea     rcx, [rax+20h]
0x14000efff  neg     rax
0x14000f002  sbb     rdi, rdi
0x14000f005  and     rdi, rcx
0x14000f008  jz      short loc_14000F050
0x14000f00a  call    cs:__imp_GetCurrentThreadId
0x14000f011  nop     dword ptr [rax+rax+00h]
0x14000f016  mov     r8d, eax
0x14000f019  mov     r9d, eax
0x14000f01c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000f026  shr     r8, 2
0x14000f02a  mul     r8
0x14000f02d  shr     rdx, 3
0x14000f031  lea     rcx, [rdx+rdx*4]
0x14000f035  add     rcx, rcx
0x14000f038  sub     r8, rcx
0x14000f03b  mov     rbx, [rdi+r8*8+8]
0x14000f040  jmp     short loc_14000F04B
0x14000f042  cmp     [rbx], r9d
0x14000f045  jz      short loc_14000F05F
0x14000f047  mov     rbx, [rbx+8]
0x14000f04b  test    rbx, rbx
0x14000f04e  jnz     short loc_14000F042
0x14000f050  mov     rax, rbx
0x14000f053  mov     rbx, [rsp+28h+arg_0]
0x14000f058  add     rsp, 20h
0x14000f05c  pop     rdi
0x14000f05d  retn
0x14000f05f  add     rbx, 10h
0x14000f063  jz      short loc_14000F050
0x14000f065  cmp     qword ptr [rbx+8], 0
0x14000f06a  jnz     short loc_14000F050
0x14000f06c  lea     rax, [rdi+4]
0x14000f070  mov     [rbx+8], rax
0x14000f074  jmp     short loc_14000F050
```
