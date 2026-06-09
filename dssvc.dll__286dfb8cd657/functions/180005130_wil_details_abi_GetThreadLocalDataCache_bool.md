# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005130`
- end: `0x1800051ed`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a70`

## callees

- `0x180004548`
- `0x180005130`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000518a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000518a`

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
0x180005130  mov     [rsp+arg_0], rbx
0x180005135  push    rdi
0x180005136  sub     rsp, 20h
0x18000513a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005141  xor     ebx, ebx
0x180005143  test    rdi, rdi
0x180005146  jz      loc_1800051DF
0x18000514c  cmp     [rdi+8], rbx
0x180005150  jnz     short loc_180005177
0x180005152  mov     rcx, [rdi]
0x180005155  lea     rdx, [rsp+28h+arg_8]
0x18000515a  mov     [rsp+28h+arg_8], rbx
0x18000515f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005164  test    eax, eax
0x180005166  js      short loc_180005177
0x180005168  cmp     [rdi+8], rbx
0x18000516c  jnz     short loc_180005177
0x18000516e  mov     rax, [rsp+28h+arg_8]
0x180005173  mov     [rdi+8], rax
0x180005177  mov     rax, [rdi+8]
0x18000517b  lea     rcx, [rax+20h]
0x18000517f  neg     rax
0x180005182  sbb     rdi, rdi
0x180005185  and     rdi, rcx
0x180005188  jz      short loc_1800051DF
0x18000518a  call    cs:__imp_GetCurrentThreadId
0x180005190  mov     r8d, eax
0x180005193  mov     r9d, eax
0x180005196  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800051a0  shr     r8, 2
0x1800051a4  mul     r8
0x1800051a7  shr     rdx, 3
0x1800051ab  lea     rcx, [rdx+rdx*4]
0x1800051af  add     rcx, rcx
0x1800051b2  sub     r8, rcx
0x1800051b5  mov     rbx, [rdi+r8*8+8]
0x1800051ba  test    rbx, rbx
0x1800051bd  jz      short loc_1800051DF
0x1800051bf  cmp     [rbx], r9d
0x1800051c2  jz      short loc_1800051CA
0x1800051c4  mov     rbx, [rbx+8]
0x1800051c8  jmp     short loc_1800051BA
0x1800051ca  add     rbx, 10h
0x1800051ce  jz      short loc_1800051DF
0x1800051d0  cmp     qword ptr [rbx+8], 0
0x1800051d5  jnz     short loc_1800051DF
0x1800051d7  lea     rax, [rdi+4]
0x1800051db  mov     [rbx+8], rax
0x1800051df  mov     rax, rbx
0x1800051e2  mov     rbx, [rsp+28h+arg_0]
0x1800051e7  add     rsp, 20h
0x1800051eb  pop     rdi
0x1800051ec  retn
```
