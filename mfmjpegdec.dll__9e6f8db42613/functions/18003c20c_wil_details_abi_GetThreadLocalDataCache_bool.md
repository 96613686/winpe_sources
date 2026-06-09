# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18003c20c`
- end: `0x18003c2c9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b8c0`

## callees

- `0x18003afa0`
- `0x18003c20c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c266`

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
0x18003c20c  mov     [rsp+arg_0], rbx
0x18003c211  push    rdi
0x18003c212  sub     rsp, 20h
0x18003c216  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18003c21d  xor     ebx, ebx
0x18003c21f  test    rdi, rdi
0x18003c222  jz      loc_18003C2BB
0x18003c228  cmp     [rdi+8], rbx
0x18003c22c  jnz     short loc_18003C253
0x18003c22e  mov     rcx, [rdi]
0x18003c231  lea     rdx, [rsp+28h+arg_8]
0x18003c236  mov     [rsp+28h+arg_8], rbx
0x18003c23b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18003c240  test    eax, eax
0x18003c242  js      short loc_18003C253
0x18003c244  cmp     [rdi+8], rbx
0x18003c248  jnz     short loc_18003C253
0x18003c24a  mov     rax, [rsp+28h+arg_8]
0x18003c24f  mov     [rdi+8], rax
0x18003c253  mov     rax, [rdi+8]
0x18003c257  lea     rcx, [rax+20h]
0x18003c25b  neg     rax
0x18003c25e  sbb     rdi, rdi
0x18003c261  and     rdi, rcx
0x18003c264  jz      short loc_18003C2BB
0x18003c266  call    cs:__imp_GetCurrentThreadId
0x18003c26c  mov     r8d, eax
0x18003c26f  mov     r9d, eax
0x18003c272  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003c27c  shr     r8, 2
0x18003c280  mul     r8
0x18003c283  shr     rdx, 3
0x18003c287  lea     rcx, [rdx+rdx*4]
0x18003c28b  add     rcx, rcx
0x18003c28e  sub     r8, rcx
0x18003c291  mov     rbx, [rdi+r8*8+8]
0x18003c296  test    rbx, rbx
0x18003c299  jz      short loc_18003C2BB
0x18003c29b  cmp     [rbx], r9d
0x18003c29e  jz      short loc_18003C2A6
0x18003c2a0  mov     rbx, [rbx+8]
0x18003c2a4  jmp     short loc_18003C296
0x18003c2a6  add     rbx, 10h
0x18003c2aa  jz      short loc_18003C2BB
0x18003c2ac  cmp     qword ptr [rbx+8], 0
0x18003c2b1  jnz     short loc_18003C2BB
0x18003c2b3  lea     rax, [rdi+4]
0x18003c2b7  mov     [rbx+8], rax
0x18003c2bb  mov     rax, rbx
0x18003c2be  mov     rbx, [rsp+28h+arg_0]
0x18003c2c3  add     rsp, 20h
0x18003c2c7  pop     rdi
0x18003c2c8  retn
```
