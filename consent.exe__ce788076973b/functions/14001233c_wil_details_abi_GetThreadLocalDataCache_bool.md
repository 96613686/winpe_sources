# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14001233c`
- end: `0x1400123f9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011d60`

## callees

- `0x14000e354`
- `0x14001233c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012396`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012396`

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
0x14001233c  mov     [rsp+arg_0], rbx
0x140012341  push    rdi
0x140012342  sub     rsp, 20h
0x140012346  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14001234d  xor     ebx, ebx
0x14001234f  test    rdi, rdi
0x140012352  jz      loc_1400123EB
0x140012358  cmp     [rdi+8], rbx
0x14001235c  jnz     short loc_140012383
0x14001235e  mov     rcx, [rdi]
0x140012361  lea     rdx, [rsp+28h+arg_8]
0x140012366  mov     [rsp+28h+arg_8], rbx
0x14001236b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140012370  test    eax, eax
0x140012372  js      short loc_140012383
0x140012374  cmp     [rdi+8], rbx
0x140012378  jnz     short loc_140012383
0x14001237a  mov     rax, [rsp+28h+arg_8]
0x14001237f  mov     [rdi+8], rax
0x140012383  mov     rax, [rdi+8]
0x140012387  lea     rcx, [rax+20h]
0x14001238b  neg     rax
0x14001238e  sbb     rdi, rdi
0x140012391  and     rdi, rcx
0x140012394  jz      short loc_1400123EB
0x140012396  call    cs:__imp_GetCurrentThreadId
0x14001239c  mov     r8d, eax
0x14001239f  mov     r9d, eax
0x1400123a2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400123ac  shr     r8, 2
0x1400123b0  mul     r8
0x1400123b3  shr     rdx, 3
0x1400123b7  lea     rcx, [rdx+rdx*4]
0x1400123bb  add     rcx, rcx
0x1400123be  sub     r8, rcx
0x1400123c1  mov     rbx, [rdi+r8*8+8]
0x1400123c6  test    rbx, rbx
0x1400123c9  jz      short loc_1400123EB
0x1400123cb  cmp     [rbx], r9d
0x1400123ce  jz      short loc_1400123D6
0x1400123d0  mov     rbx, [rbx+8]
0x1400123d4  jmp     short loc_1400123C6
0x1400123d6  add     rbx, 10h
0x1400123da  jz      short loc_1400123EB
0x1400123dc  cmp     qword ptr [rbx+8], 0
0x1400123e1  jnz     short loc_1400123EB
0x1400123e3  lea     rax, [rdi+4]
0x1400123e7  mov     [rbx+8], rax
0x1400123eb  mov     rax, rbx
0x1400123ee  mov     rbx, [rsp+28h+arg_0]
0x1400123f3  add     rsp, 20h
0x1400123f7  pop     rdi
0x1400123f8  retn
```
