# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d384`
- end: `0x18000d43f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c7b0`

## callees

- `0x180008cc8`
- `0x18000d384`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000d3da`
- `KERNEL32!GetCurrentThreadId` at `0x18000d3da`

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
0x18000d384  mov     [rsp+arg_0], rbx
0x18000d389  push    rdi
0x18000d38a  sub     rsp, 20h
0x18000d38e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d395  xor     ebx, ebx
0x18000d397  test    rdi, rdi
0x18000d39a  jz      short loc_18000D41A
0x18000d39c  cmp     [rdi+8], rbx
0x18000d3a0  jnz     short loc_18000D3C7
0x18000d3a2  mov     rcx, [rdi]
0x18000d3a5  lea     rdx, [rsp+28h+arg_8]
0x18000d3aa  mov     [rsp+28h+arg_8], rbx
0x18000d3af  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d3b4  test    eax, eax
0x18000d3b6  js      short loc_18000D3C7
0x18000d3b8  cmp     [rdi+8], rbx
0x18000d3bc  jnz     short loc_18000D3C7
0x18000d3be  mov     rax, [rsp+28h+arg_8]
0x18000d3c3  mov     [rdi+8], rax
0x18000d3c7  mov     rax, [rdi+8]
0x18000d3cb  lea     rcx, [rax+20h]
0x18000d3cf  neg     rax
0x18000d3d2  sbb     rdi, rdi
0x18000d3d5  and     rdi, rcx
0x18000d3d8  jz      short loc_18000D41A
0x18000d3da  call    cs:__imp_GetCurrentThreadId
0x18000d3e0  mov     r8d, eax
0x18000d3e3  mov     r9d, eax
0x18000d3e6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d3f0  shr     r8, 2
0x18000d3f4  mul     r8
0x18000d3f7  shr     rdx, 3
0x18000d3fb  lea     rcx, [rdx+rdx*4]
0x18000d3ff  add     rcx, rcx
0x18000d402  sub     r8, rcx
0x18000d405  mov     rbx, [rdi+r8*8+8]
0x18000d40a  jmp     short loc_18000D415
0x18000d40c  cmp     [rbx], r9d
0x18000d40f  jz      short loc_18000D428
0x18000d411  mov     rbx, [rbx+8]
0x18000d415  test    rbx, rbx
0x18000d418  jnz     short loc_18000D40C
0x18000d41a  mov     rax, rbx
0x18000d41d  mov     rbx, [rsp+28h+arg_0]
0x18000d422  add     rsp, 20h
0x18000d426  pop     rdi
0x18000d427  retn
0x18000d428  add     rbx, 10h
0x18000d42c  jz      short loc_18000D41A
0x18000d42e  cmp     qword ptr [rbx+8], 0
0x18000d433  jnz     short loc_18000D41A
0x18000d435  lea     rax, [rdi+4]
0x18000d439  mov     [rbx+8], rax
0x18000d43d  jmp     short loc_18000D41A
```
