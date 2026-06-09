# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800176d8`
- end: `0x180017795`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017070`

## callees

- `0x180016668`
- `0x1800176d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017732`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x1800176d8  mov     [rsp+arg_0], rbx
0x1800176dd  push    rdi
0x1800176de  sub     rsp, 20h
0x1800176e2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800176e9  xor     ebx, ebx
0x1800176eb  test    rdi, rdi
0x1800176ee  jz      loc_180017787
0x1800176f4  cmp     [rdi+8], rbx
0x1800176f8  jnz     short loc_18001771F
0x1800176fa  mov     rcx, [rdi]
0x1800176fd  lea     rdx, [rsp+28h+arg_8]
0x180017702  mov     [rsp+28h+arg_8], rbx
0x180017707  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001770c  test    eax, eax
0x18001770e  js      short loc_18001771F
0x180017710  cmp     [rdi+8], rbx
0x180017714  jnz     short loc_18001771F
0x180017716  mov     rax, [rsp+28h+arg_8]
0x18001771b  mov     [rdi+8], rax
0x18001771f  mov     rax, [rdi+8]
0x180017723  lea     rcx, [rax+20h]
0x180017727  neg     rax
0x18001772a  sbb     rdi, rdi
0x18001772d  and     rdi, rcx
0x180017730  jz      short loc_180017787
0x180017732  call    cs:__imp_GetCurrentThreadId
0x180017738  mov     r8d, eax
0x18001773b  mov     r9d, eax
0x18001773e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180017748  shr     r8, 2
0x18001774c  mul     r8
0x18001774f  shr     rdx, 3
0x180017753  lea     rcx, [rdx+rdx*4]
0x180017757  add     rcx, rcx
0x18001775a  sub     r8, rcx
0x18001775d  mov     rbx, [rdi+r8*8+8]
0x180017762  test    rbx, rbx
0x180017765  jz      short loc_180017787
0x180017767  cmp     [rbx], r9d
0x18001776a  jz      short loc_180017772
0x18001776c  mov     rbx, [rbx+8]
0x180017770  jmp     short loc_180017762
0x180017772  add     rbx, 10h
0x180017776  jz      short loc_180017787
0x180017778  cmp     qword ptr [rbx+8], 0
0x18001777d  jnz     short loc_180017787
0x18001777f  lea     rax, [rdi+4]
0x180017783  mov     [rbx+8], rax
0x180017787  mov     rax, rbx
0x18001778a  mov     rbx, [rsp+28h+arg_0]
0x18001778f  add     rsp, 20h
0x180017793  pop     rdi
0x180017794  retn
```
