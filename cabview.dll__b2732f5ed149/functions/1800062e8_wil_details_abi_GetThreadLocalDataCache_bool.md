# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800062e8`
- end: `0x1800063a5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x1800043f8`
- `0x1800062e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006342`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006342`

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
0x1800062e8  mov     [rsp+arg_0], rbx
0x1800062ed  push    rdi
0x1800062ee  sub     rsp, 20h
0x1800062f2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800062f9  xor     ebx, ebx
0x1800062fb  test    rdi, rdi
0x1800062fe  jz      loc_180006397
0x180006304  cmp     [rdi+8], rbx
0x180006308  jnz     short loc_18000632F
0x18000630a  mov     rcx, [rdi]
0x18000630d  lea     rdx, [rsp+28h+arg_8]
0x180006312  mov     [rsp+28h+arg_8], rbx
0x180006317  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000631c  test    eax, eax
0x18000631e  js      short loc_18000632F
0x180006320  cmp     [rdi+8], rbx
0x180006324  jnz     short loc_18000632F
0x180006326  mov     rax, [rsp+28h+arg_8]
0x18000632b  mov     [rdi+8], rax
0x18000632f  mov     rax, [rdi+8]
0x180006333  lea     rcx, [rax+20h]
0x180006337  neg     rax
0x18000633a  sbb     rdi, rdi
0x18000633d  and     rdi, rcx
0x180006340  jz      short loc_180006397
0x180006342  call    cs:__imp_GetCurrentThreadId
0x180006348  mov     r8d, eax
0x18000634b  mov     r9d, eax
0x18000634e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006358  shr     r8, 2
0x18000635c  mul     r8
0x18000635f  shr     rdx, 3
0x180006363  lea     rcx, [rdx+rdx*4]
0x180006367  add     rcx, rcx
0x18000636a  sub     r8, rcx
0x18000636d  mov     rbx, [rdi+r8*8+8]
0x180006372  test    rbx, rbx
0x180006375  jz      short loc_180006397
0x180006377  cmp     [rbx], r9d
0x18000637a  jz      short loc_180006382
0x18000637c  mov     rbx, [rbx+8]
0x180006380  jmp     short loc_180006372
0x180006382  add     rbx, 10h
0x180006386  jz      short loc_180006397
0x180006388  cmp     qword ptr [rbx+8], 0
0x18000638d  jnz     short loc_180006397
0x18000638f  lea     rax, [rdi+4]
0x180006393  mov     [rbx+8], rax
0x180006397  mov     rax, rbx
0x18000639a  mov     rbx, [rsp+28h+arg_0]
0x18000639f  add     rsp, 20h
0x1800063a3  pop     rdi
0x1800063a4  retn
```
