# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007228`
- end: `0x1800072ec`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006c10`

## callees

- `0x1800066b8`
- `0x180007228`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007282`

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
0x180007228  mov     [rsp+arg_0], rbx
0x18000722d  push    rdi
0x18000722e  sub     rsp, 20h
0x180007232  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007239  xor     ebx, ebx
0x18000723b  test    rdi, rdi
0x18000723e  jz      loc_1800072DD
0x180007244  cmp     [rdi+8], rbx
0x180007248  jnz     short loc_18000726F
0x18000724a  mov     rcx, [rdi]
0x18000724d  lea     rdx, [rsp+28h+arg_8]
0x180007252  mov     [rsp+28h+arg_8], rbx
0x180007257  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000725c  test    eax, eax
0x18000725e  js      short loc_18000726F
0x180007260  cmp     [rdi+8], rbx
0x180007264  jnz     short loc_18000726F
0x180007266  mov     rax, [rsp+28h+arg_8]
0x18000726b  mov     [rdi+8], rax
0x18000726f  mov     rax, [rdi+8]
0x180007273  lea     rcx, [rax+20h]
0x180007277  neg     rax
0x18000727a  sbb     rdi, rdi
0x18000727d  and     rdi, rcx
0x180007280  jz      short loc_1800072DD
0x180007282  call    cs:__imp_GetCurrentThreadId
0x180007289  nop     dword ptr [rax+rax+00h]
0x18000728e  mov     r8d, eax
0x180007291  mov     r9d, eax
0x180007294  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000729e  shr     r8, 2
0x1800072a2  mul     r8
0x1800072a5  shr     rdx, 3
0x1800072a9  lea     rcx, [rdx+rdx*4]
0x1800072ad  add     rcx, rcx
0x1800072b0  sub     r8, rcx
0x1800072b3  mov     rbx, [rdi+r8*8+8]
0x1800072b8  test    rbx, rbx
0x1800072bb  jz      short loc_1800072DD
0x1800072bd  cmp     [rbx], r9d
0x1800072c0  jz      short loc_1800072C8
0x1800072c2  mov     rbx, [rbx+8]
0x1800072c6  jmp     short loc_1800072B8
0x1800072c8  add     rbx, 10h
0x1800072cc  jz      short loc_1800072DD
0x1800072ce  cmp     qword ptr [rbx+8], 0
0x1800072d3  jnz     short loc_1800072DD
0x1800072d5  lea     rax, [rdi+4]
0x1800072d9  mov     [rbx+8], rax
0x1800072dd  mov     rax, rbx
0x1800072e0  mov     rbx, [rsp+28h+arg_0]
0x1800072e5  add     rsp, 20h
0x1800072e9  pop     rdi
0x1800072ea  retn
```
