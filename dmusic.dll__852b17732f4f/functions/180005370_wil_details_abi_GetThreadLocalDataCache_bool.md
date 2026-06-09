# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005370`
- end: `0x18000542b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b90`

## callees

- `0x180003ac8`
- `0x180005370`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053c6`

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
0x180005370  mov     [rsp+arg_0], rbx
0x180005375  push    rdi
0x180005376  sub     rsp, 20h
0x18000537a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005381  xor     ebx, ebx
0x180005383  test    rdi, rdi
0x180005386  jz      short loc_180005406
0x180005388  cmp     [rdi+8], rbx
0x18000538c  jnz     short loc_1800053B3
0x18000538e  mov     rcx, [rdi]
0x180005391  lea     rdx, [rsp+28h+arg_8]
0x180005396  mov     [rsp+28h+arg_8], rbx
0x18000539b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800053a0  test    eax, eax
0x1800053a2  js      short loc_1800053B3
0x1800053a4  cmp     [rdi+8], rbx
0x1800053a8  jnz     short loc_1800053B3
0x1800053aa  mov     rax, [rsp+28h+arg_8]
0x1800053af  mov     [rdi+8], rax
0x1800053b3  mov     rax, [rdi+8]
0x1800053b7  lea     rcx, [rax+20h]
0x1800053bb  neg     rax
0x1800053be  sbb     rdi, rdi
0x1800053c1  and     rdi, rcx
0x1800053c4  jz      short loc_180005406
0x1800053c6  call    cs:__imp_GetCurrentThreadId
0x1800053cc  mov     r8d, eax
0x1800053cf  mov     r9d, eax
0x1800053d2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800053dc  shr     r8, 2
0x1800053e0  mul     r8
0x1800053e3  shr     rdx, 3
0x1800053e7  lea     rcx, [rdx+rdx*4]
0x1800053eb  add     rcx, rcx
0x1800053ee  sub     r8, rcx
0x1800053f1  mov     rbx, [rdi+r8*8+8]
0x1800053f6  jmp     short loc_180005401
0x1800053f8  cmp     [rbx], r9d
0x1800053fb  jz      short loc_180005414
0x1800053fd  mov     rbx, [rbx+8]
0x180005401  test    rbx, rbx
0x180005404  jnz     short loc_1800053F8
0x180005406  mov     rax, rbx
0x180005409  mov     rbx, [rsp+28h+arg_0]
0x18000540e  add     rsp, 20h
0x180005412  pop     rdi
0x180005413  retn
0x180005414  add     rbx, 10h
0x180005418  jz      short loc_180005406
0x18000541a  cmp     qword ptr [rbx+8], 0
0x18000541f  jnz     short loc_180005406
0x180005421  lea     rax, [rdi+4]
0x180005425  mov     [rbx+8], rax
0x180005429  jmp     short loc_180005406
```
