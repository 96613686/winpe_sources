# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004548`
- end: `0x180004605`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f00`

## callees

- `0x180003a38`
- `0x180004548`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045a2`

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
0x180004548  mov     [rsp+arg_0], rbx
0x18000454d  push    rdi
0x18000454e  sub     rsp, 20h
0x180004552  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004559  xor     ebx, ebx
0x18000455b  test    rdi, rdi
0x18000455e  jz      loc_1800045F7
0x180004564  cmp     [rdi+8], rbx
0x180004568  jnz     short loc_18000458F
0x18000456a  mov     rcx, [rdi]
0x18000456d  lea     rdx, [rsp+28h+arg_8]
0x180004572  mov     [rsp+28h+arg_8], rbx
0x180004577  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000457c  test    eax, eax
0x18000457e  js      short loc_18000458F
0x180004580  cmp     [rdi+8], rbx
0x180004584  jnz     short loc_18000458F
0x180004586  mov     rax, [rsp+28h+arg_8]
0x18000458b  mov     [rdi+8], rax
0x18000458f  mov     rax, [rdi+8]
0x180004593  lea     rcx, [rax+20h]
0x180004597  neg     rax
0x18000459a  sbb     rdi, rdi
0x18000459d  and     rdi, rcx
0x1800045a0  jz      short loc_1800045F7
0x1800045a2  call    cs:__imp_GetCurrentThreadId
0x1800045a8  mov     r8d, eax
0x1800045ab  mov     r9d, eax
0x1800045ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800045b8  shr     r8, 2
0x1800045bc  mul     r8
0x1800045bf  shr     rdx, 3
0x1800045c3  lea     rcx, [rdx+rdx*4]
0x1800045c7  add     rcx, rcx
0x1800045ca  sub     r8, rcx
0x1800045cd  mov     rbx, [rdi+r8*8+8]
0x1800045d2  test    rbx, rbx
0x1800045d5  jz      short loc_1800045F7
0x1800045d7  cmp     [rbx], r9d
0x1800045da  jz      short loc_1800045E2
0x1800045dc  mov     rbx, [rbx+8]
0x1800045e0  jmp     short loc_1800045D2
0x1800045e2  add     rbx, 10h
0x1800045e6  jz      short loc_1800045F7
0x1800045e8  cmp     qword ptr [rbx+8], 0
0x1800045ed  jnz     short loc_1800045F7
0x1800045ef  lea     rax, [rdi+4]
0x1800045f3  mov     [rbx+8], rax
0x1800045f7  mov     rax, rbx
0x1800045fa  mov     rbx, [rsp+28h+arg_0]
0x1800045ff  add     rsp, 20h
0x180004603  pop     rdi
0x180004604  retn
```
