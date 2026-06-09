# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001dfa4`
- end: `0x18001e069`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d820`

## callees

- `0x18001c684`
- `0x18001dfa4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dffe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dffe`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x18001dfa4  mov     [rsp+arg_0], rbx
0x18001dfa9  push    rdi
0x18001dfaa  sub     rsp, 20h
0x18001dfae  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001dfb5  xor     edi, edi
0x18001dfb7  test    rbx, rbx
0x18001dfba  jz      loc_18001E05A
0x18001dfc0  cmp     [rbx+8], rdi
0x18001dfc4  jnz     short loc_18001DFEB
0x18001dfc6  mov     rcx, [rbx]
0x18001dfc9  lea     rdx, [rsp+28h+arg_8]
0x18001dfce  and     [rsp+28h+arg_8], rdi
0x18001dfd3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001dfd8  test    eax, eax
0x18001dfda  js      short loc_18001DFEB
0x18001dfdc  cmp     [rbx+8], rdi
0x18001dfe0  jnz     short loc_18001DFEB
0x18001dfe2  mov     rax, [rsp+28h+arg_8]
0x18001dfe7  mov     [rbx+8], rax
0x18001dfeb  mov     rax, [rbx+8]
0x18001dfef  lea     rcx, [rax+20h]
0x18001dff3  neg     rax
0x18001dff6  sbb     rbx, rbx
0x18001dff9  and     rbx, rcx
0x18001dffc  jz      short loc_18001E05A
0x18001dffe  call    cs:__imp_GetCurrentThreadId
0x18001e005  nop     dword ptr [rax+rax+00h]
0x18001e00a  mov     r8d, eax
0x18001e00d  mov     r9d, eax
0x18001e010  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001e01a  mul     r9
0x18001e01d  shr     rdx, 3
0x18001e021  lea     rcx, [rdx+rdx*4]
0x18001e025  add     rcx, rcx
0x18001e028  sub     r8, rcx
0x18001e02b  mov     rcx, [rbx+r8*8+8]
0x18001e030  jmp     short loc_18001E03B
0x18001e032  cmp     [rcx], r9d
0x18001e035  jz      short loc_18001E042
0x18001e037  mov     rcx, [rcx+8]
0x18001e03b  test    rcx, rcx
0x18001e03e  jnz     short loc_18001E032
0x18001e040  jmp     short loc_18001E05A
0x18001e042  add     rcx, 10h
0x18001e046  mov     rdi, rcx
0x18001e049  jz      short loc_18001E05A
0x18001e04b  cmp     qword ptr [rcx+8], 0
0x18001e050  jnz     short loc_18001E05A
0x18001e052  lea     rax, [rbx+4]
0x18001e056  mov     [rcx+8], rax
0x18001e05a  mov     rbx, [rsp+28h+arg_0]
0x18001e05f  mov     rax, rdi
0x18001e062  add     rsp, 20h
0x18001e066  pop     rdi
0x18001e067  retn
```
