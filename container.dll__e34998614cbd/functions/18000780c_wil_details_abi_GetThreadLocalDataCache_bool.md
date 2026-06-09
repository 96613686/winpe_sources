# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000780c`
- end: `0x1800078d2`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f50`

## callees

- `0x180005c6c`
- `0x18000780c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007866`

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
0x18000780c  mov     [rsp+arg_0], rbx
0x180007811  push    rdi
0x180007812  sub     rsp, 20h
0x180007816  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000781d  xor     ebx, ebx
0x18000781f  test    rdi, rdi
0x180007822  jz      loc_1800078AC
0x180007828  cmp     [rdi+8], rbx
0x18000782c  jnz     short loc_180007853
0x18000782e  mov     rcx, [rdi]
0x180007831  lea     rdx, [rsp+28h+arg_8]
0x180007836  mov     [rsp+28h+arg_8], rbx
0x18000783b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007840  test    eax, eax
0x180007842  js      short loc_180007853
0x180007844  cmp     [rdi+8], rbx
0x180007848  jnz     short loc_180007853
0x18000784a  mov     rax, [rsp+28h+arg_8]
0x18000784f  mov     [rdi+8], rax
0x180007853  mov     rax, [rdi+8]
0x180007857  lea     rcx, [rax+20h]
0x18000785b  neg     rax
0x18000785e  sbb     rdi, rdi
0x180007861  and     rdi, rcx
0x180007864  jz      short loc_1800078AC
0x180007866  call    cs:__imp_GetCurrentThreadId
0x18000786d  nop     dword ptr [rax+rax+00h]
0x180007872  mov     r8d, eax
0x180007875  mov     r9d, eax
0x180007878  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007882  shr     r8, 2
0x180007886  mul     r8
0x180007889  shr     rdx, 3
0x18000788d  lea     rcx, [rdx+rdx*4]
0x180007891  add     rcx, rcx
0x180007894  sub     r8, rcx
0x180007897  mov     rbx, [rdi+r8*8+8]
0x18000789c  jmp     short loc_1800078A7
0x18000789e  cmp     [rbx], r9d
0x1800078a1  jz      short loc_1800078BB
0x1800078a3  mov     rbx, [rbx+8]
0x1800078a7  test    rbx, rbx
0x1800078aa  jnz     short loc_18000789E
0x1800078ac  mov     rax, rbx
0x1800078af  mov     rbx, [rsp+28h+arg_0]
0x1800078b4  add     rsp, 20h
0x1800078b8  pop     rdi
0x1800078b9  retn
0x1800078bb  add     rbx, 10h
0x1800078bf  jz      short loc_1800078AC
0x1800078c1  cmp     qword ptr [rbx+8], 0
0x1800078c6  jnz     short loc_1800078AC
0x1800078c8  lea     rax, [rdi+4]
0x1800078cc  mov     [rbx+8], rax
0x1800078d0  jmp     short loc_1800078AC
```
