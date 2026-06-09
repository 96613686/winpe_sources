# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004520`
- end: `0x1800045db`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d40`

## callees

- `0x1800034b8`
- `0x180004520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004576`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004576`

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
0x180004520  mov     [rsp+arg_0], rbx
0x180004525  push    rdi
0x180004526  sub     rsp, 20h
0x18000452a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004531  xor     ebx, ebx
0x180004533  test    rdi, rdi
0x180004536  jz      short loc_1800045B6
0x180004538  cmp     [rdi+8], rbx
0x18000453c  jnz     short loc_180004563
0x18000453e  mov     rcx, [rdi]
0x180004541  lea     rdx, [rsp+28h+arg_8]
0x180004546  mov     [rsp+28h+arg_8], rbx
0x18000454b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004550  test    eax, eax
0x180004552  js      short loc_180004563
0x180004554  cmp     [rdi+8], rbx
0x180004558  jnz     short loc_180004563
0x18000455a  mov     rax, [rsp+28h+arg_8]
0x18000455f  mov     [rdi+8], rax
0x180004563  mov     rax, [rdi+8]
0x180004567  lea     rcx, [rax+20h]
0x18000456b  neg     rax
0x18000456e  sbb     rdi, rdi
0x180004571  and     rdi, rcx
0x180004574  jz      short loc_1800045B6
0x180004576  call    cs:__imp_GetCurrentThreadId
0x18000457c  mov     r8d, eax
0x18000457f  mov     r9d, eax
0x180004582  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000458c  shr     r8, 2
0x180004590  mul     r8
0x180004593  shr     rdx, 3
0x180004597  lea     rcx, [rdx+rdx*4]
0x18000459b  add     rcx, rcx
0x18000459e  sub     r8, rcx
0x1800045a1  mov     rbx, [rdi+r8*8+8]
0x1800045a6  jmp     short loc_1800045B1
0x1800045a8  cmp     [rbx], r9d
0x1800045ab  jz      short loc_1800045C4
0x1800045ad  mov     rbx, [rbx+8]
0x1800045b1  test    rbx, rbx
0x1800045b4  jnz     short loc_1800045A8
0x1800045b6  mov     rax, rbx
0x1800045b9  mov     rbx, [rsp+28h+arg_0]
0x1800045be  add     rsp, 20h
0x1800045c2  pop     rdi
0x1800045c3  retn
0x1800045c4  add     rbx, 10h
0x1800045c8  jz      short loc_1800045B6
0x1800045ca  cmp     qword ptr [rbx+8], 0
0x1800045cf  jnz     short loc_1800045B6
0x1800045d1  lea     rax, [rdi+4]
0x1800045d5  mov     [rbx+8], rax
0x1800045d9  jmp     short loc_1800045B6
```
