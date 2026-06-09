# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005790`
- end: `0x14000584b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005070`

## callees

- `0x140003de0`
- `0x140005790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400057e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400057e6`

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
0x140005790  mov     [rsp+arg_0], rbx
0x140005795  push    rdi
0x140005796  sub     rsp, 20h
0x14000579a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400057a1  xor     ebx, ebx
0x1400057a3  test    rdi, rdi
0x1400057a6  jz      short loc_140005826
0x1400057a8  cmp     [rdi+8], rbx
0x1400057ac  jnz     short loc_1400057D3
0x1400057ae  mov     rcx, [rdi]
0x1400057b1  lea     rdx, [rsp+28h+arg_8]
0x1400057b6  mov     [rsp+28h+arg_8], rbx
0x1400057bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400057c0  test    eax, eax
0x1400057c2  js      short loc_1400057D3
0x1400057c4  cmp     [rdi+8], rbx
0x1400057c8  jnz     short loc_1400057D3
0x1400057ca  mov     rax, [rsp+28h+arg_8]
0x1400057cf  mov     [rdi+8], rax
0x1400057d3  mov     rax, [rdi+8]
0x1400057d7  lea     rcx, [rax+20h]
0x1400057db  neg     rax
0x1400057de  sbb     rdi, rdi
0x1400057e1  and     rdi, rcx
0x1400057e4  jz      short loc_140005826
0x1400057e6  call    cs:__imp_GetCurrentThreadId
0x1400057ec  mov     r8d, eax
0x1400057ef  mov     r9d, eax
0x1400057f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400057fc  shr     r8, 2
0x140005800  mul     r8
0x140005803  shr     rdx, 3
0x140005807  lea     rcx, [rdx+rdx*4]
0x14000580b  add     rcx, rcx
0x14000580e  sub     r8, rcx
0x140005811  mov     rbx, [rdi+r8*8+8]
0x140005816  jmp     short loc_140005821
0x140005818  cmp     [rbx], r9d
0x14000581b  jz      short loc_140005834
0x14000581d  mov     rbx, [rbx+8]
0x140005821  test    rbx, rbx
0x140005824  jnz     short loc_140005818
0x140005826  mov     rax, rbx
0x140005829  mov     rbx, [rsp+28h+arg_0]
0x14000582e  add     rsp, 20h
0x140005832  pop     rdi
0x140005833  retn
0x140005834  add     rbx, 10h
0x140005838  jz      short loc_140005826
0x14000583a  cmp     qword ptr [rbx+8], 0
0x14000583f  jnz     short loc_140005826
0x140005841  lea     rax, [rdi+4]
0x140005845  mov     [rbx+8], rax
0x140005849  jmp     short loc_140005826
```
