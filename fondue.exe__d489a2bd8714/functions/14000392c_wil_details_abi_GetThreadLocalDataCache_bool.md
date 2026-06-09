# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000392c`
- end: `0x1400039e7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003150`

## callees

- `0x140002ab8`
- `0x14000392c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003982`
- `KERNEL32!GetCurrentThreadId` at `0x140003982`

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
0x14000392c  mov     [rsp+arg_0], rbx
0x140003931  push    rdi
0x140003932  sub     rsp, 20h
0x140003936  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000393d  xor     ebx, ebx
0x14000393f  test    rdi, rdi
0x140003942  jz      short loc_1400039C2
0x140003944  cmp     [rdi+8], rbx
0x140003948  jnz     short loc_14000396F
0x14000394a  mov     rcx, [rdi]
0x14000394d  lea     rdx, [rsp+28h+arg_8]
0x140003952  mov     [rsp+28h+arg_8], rbx
0x140003957  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000395c  test    eax, eax
0x14000395e  js      short loc_14000396F
0x140003960  cmp     [rdi+8], rbx
0x140003964  jnz     short loc_14000396F
0x140003966  mov     rax, [rsp+28h+arg_8]
0x14000396b  mov     [rdi+8], rax
0x14000396f  mov     rax, [rdi+8]
0x140003973  lea     rcx, [rax+20h]
0x140003977  neg     rax
0x14000397a  sbb     rdi, rdi
0x14000397d  and     rdi, rcx
0x140003980  jz      short loc_1400039C2
0x140003982  call    cs:__imp_GetCurrentThreadId
0x140003988  mov     r8d, eax
0x14000398b  mov     r9d, eax
0x14000398e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003998  shr     r8, 2
0x14000399c  mul     r8
0x14000399f  shr     rdx, 3
0x1400039a3  lea     rcx, [rdx+rdx*4]
0x1400039a7  add     rcx, rcx
0x1400039aa  sub     r8, rcx
0x1400039ad  mov     rbx, [rdi+r8*8+8]
0x1400039b2  jmp     short loc_1400039BD
0x1400039b4  cmp     [rbx], r9d
0x1400039b7  jz      short loc_1400039D0
0x1400039b9  mov     rbx, [rbx+8]
0x1400039bd  test    rbx, rbx
0x1400039c0  jnz     short loc_1400039B4
0x1400039c2  mov     rax, rbx
0x1400039c5  mov     rbx, [rsp+28h+arg_0]
0x1400039ca  add     rsp, 20h
0x1400039ce  pop     rdi
0x1400039cf  retn
0x1400039d0  add     rbx, 10h
0x1400039d4  jz      short loc_1400039C2
0x1400039d6  cmp     qword ptr [rbx+8], 0
0x1400039db  jnz     short loc_1400039C2
0x1400039dd  lea     rax, [rdi+4]
0x1400039e1  mov     [rbx+8], rax
0x1400039e5  jmp     short loc_1400039C2
```
