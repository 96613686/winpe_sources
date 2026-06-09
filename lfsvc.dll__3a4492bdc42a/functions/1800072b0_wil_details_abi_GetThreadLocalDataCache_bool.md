# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800072b0`
- end: `0x18000736d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ca0`

## callees

- `0x180006308`
- `0x1800072b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000730a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000730a`

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
0x1800072b0  mov     [rsp+arg_0], rbx
0x1800072b5  push    rdi
0x1800072b6  sub     rsp, 20h
0x1800072ba  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800072c1  xor     ebx, ebx
0x1800072c3  test    rdi, rdi
0x1800072c6  jz      loc_18000735F
0x1800072cc  cmp     [rdi+8], rbx
0x1800072d0  jnz     short loc_1800072F7
0x1800072d2  mov     rcx, [rdi]
0x1800072d5  lea     rdx, [rsp+28h+arg_8]
0x1800072da  mov     [rsp+28h+arg_8], rbx
0x1800072df  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800072e4  test    eax, eax
0x1800072e6  js      short loc_1800072F7
0x1800072e8  cmp     [rdi+8], rbx
0x1800072ec  jnz     short loc_1800072F7
0x1800072ee  mov     rax, [rsp+28h+arg_8]
0x1800072f3  mov     [rdi+8], rax
0x1800072f7  mov     rax, [rdi+8]
0x1800072fb  lea     rcx, [rax+20h]
0x1800072ff  neg     rax
0x180007302  sbb     rdi, rdi
0x180007305  and     rdi, rcx
0x180007308  jz      short loc_18000735F
0x18000730a  call    cs:__imp_GetCurrentThreadId
0x180007310  mov     r8d, eax
0x180007313  mov     r9d, eax
0x180007316  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007320  shr     r8, 2
0x180007324  mul     r8
0x180007327  shr     rdx, 3
0x18000732b  lea     rcx, [rdx+rdx*4]
0x18000732f  add     rcx, rcx
0x180007332  sub     r8, rcx
0x180007335  mov     rbx, [rdi+r8*8+8]
0x18000733a  test    rbx, rbx
0x18000733d  jz      short loc_18000735F
0x18000733f  cmp     [rbx], r9d
0x180007342  jz      short loc_18000734A
0x180007344  mov     rbx, [rbx+8]
0x180007348  jmp     short loc_18000733A
0x18000734a  add     rbx, 10h
0x18000734e  jz      short loc_18000735F
0x180007350  cmp     qword ptr [rbx+8], 0
0x180007355  jnz     short loc_18000735F
0x180007357  lea     rax, [rdi+4]
0x18000735b  mov     [rbx+8], rax
0x18000735f  mov     rax, rbx
0x180007362  mov     rbx, [rsp+28h+arg_0]
0x180007367  add     rsp, 20h
0x18000736b  pop     rdi
0x18000736c  retn
```
