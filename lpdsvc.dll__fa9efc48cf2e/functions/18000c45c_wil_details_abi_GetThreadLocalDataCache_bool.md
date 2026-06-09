# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000c45c`
- end: `0x18000c517`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bc80`

## callees

- `0x18000b59c`
- `0x18000c45c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c4b2`
- `KERNEL32!GetCurrentThreadId` at `0x18000c4b2`

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
0x18000c45c  mov     [rsp+arg_0], rbx
0x18000c461  push    rdi
0x18000c462  sub     rsp, 20h
0x18000c466  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000c46d  xor     ebx, ebx
0x18000c46f  test    rdi, rdi
0x18000c472  jz      short loc_18000C4F2
0x18000c474  cmp     [rdi+8], rbx
0x18000c478  jnz     short loc_18000C49F
0x18000c47a  mov     rcx, [rdi]
0x18000c47d  lea     rdx, [rsp+28h+arg_8]
0x18000c482  mov     [rsp+28h+arg_8], rbx
0x18000c487  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000c48c  test    eax, eax
0x18000c48e  js      short loc_18000C49F
0x18000c490  cmp     [rdi+8], rbx
0x18000c494  jnz     short loc_18000C49F
0x18000c496  mov     rax, [rsp+28h+arg_8]
0x18000c49b  mov     [rdi+8], rax
0x18000c49f  mov     rax, [rdi+8]
0x18000c4a3  lea     rcx, [rax+20h]
0x18000c4a7  neg     rax
0x18000c4aa  sbb     rdi, rdi
0x18000c4ad  and     rdi, rcx
0x18000c4b0  jz      short loc_18000C4F2
0x18000c4b2  call    cs:__imp_GetCurrentThreadId
0x18000c4b8  mov     r8d, eax
0x18000c4bb  mov     r9d, eax
0x18000c4be  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c4c8  shr     r8, 2
0x18000c4cc  mul     r8
0x18000c4cf  shr     rdx, 3
0x18000c4d3  lea     rcx, [rdx+rdx*4]
0x18000c4d7  add     rcx, rcx
0x18000c4da  sub     r8, rcx
0x18000c4dd  mov     rbx, [rdi+r8*8+8]
0x18000c4e2  jmp     short loc_18000C4ED
0x18000c4e4  cmp     [rbx], r9d
0x18000c4e7  jz      short loc_18000C500
0x18000c4e9  mov     rbx, [rbx+8]
0x18000c4ed  test    rbx, rbx
0x18000c4f0  jnz     short loc_18000C4E4
0x18000c4f2  mov     rax, rbx
0x18000c4f5  mov     rbx, [rsp+28h+arg_0]
0x18000c4fa  add     rsp, 20h
0x18000c4fe  pop     rdi
0x18000c4ff  retn
0x18000c500  add     rbx, 10h
0x18000c504  jz      short loc_18000C4F2
0x18000c506  cmp     qword ptr [rbx+8], 0
0x18000c50b  jnz     short loc_18000C4F2
0x18000c50d  lea     rax, [rdi+4]
0x18000c511  mov     [rbx+8], rax
0x18000c515  jmp     short loc_18000C4F2
```
