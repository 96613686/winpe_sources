# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005060`
- end: `0x140005126`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004990`

## callees

- `0x14000418c`
- `0x140005060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400050ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400050ba`

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
0x140005060  mov     [rsp+arg_0], rbx
0x140005065  push    rdi
0x140005066  sub     rsp, 20h
0x14000506a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005071  xor     ebx, ebx
0x140005073  test    rdi, rdi
0x140005076  jz      loc_140005100
0x14000507c  cmp     [rdi+8], rbx
0x140005080  jnz     short loc_1400050A7
0x140005082  mov     rcx, [rdi]
0x140005085  lea     rdx, [rsp+28h+arg_8]
0x14000508a  mov     [rsp+28h+arg_8], rbx
0x14000508f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005094  test    eax, eax
0x140005096  js      short loc_1400050A7
0x140005098  cmp     [rdi+8], rbx
0x14000509c  jnz     short loc_1400050A7
0x14000509e  mov     rax, [rsp+28h+arg_8]
0x1400050a3  mov     [rdi+8], rax
0x1400050a7  mov     rax, [rdi+8]
0x1400050ab  lea     rcx, [rax+20h]
0x1400050af  neg     rax
0x1400050b2  sbb     rdi, rdi
0x1400050b5  and     rdi, rcx
0x1400050b8  jz      short loc_140005100
0x1400050ba  call    cs:__imp_GetCurrentThreadId
0x1400050c1  nop     dword ptr [rax+rax+00h]
0x1400050c6  mov     r8d, eax
0x1400050c9  mov     r9d, eax
0x1400050cc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400050d6  shr     r8, 2
0x1400050da  mul     r8
0x1400050dd  shr     rdx, 3
0x1400050e1  lea     rcx, [rdx+rdx*4]
0x1400050e5  add     rcx, rcx
0x1400050e8  sub     r8, rcx
0x1400050eb  mov     rbx, [rdi+r8*8+8]
0x1400050f0  jmp     short loc_1400050FB
0x1400050f2  cmp     [rbx], r9d
0x1400050f5  jz      short loc_14000510F
0x1400050f7  mov     rbx, [rbx+8]
0x1400050fb  test    rbx, rbx
0x1400050fe  jnz     short loc_1400050F2
0x140005100  mov     rax, rbx
0x140005103  mov     rbx, [rsp+28h+arg_0]
0x140005108  add     rsp, 20h
0x14000510c  pop     rdi
0x14000510d  retn
0x14000510f  add     rbx, 10h
0x140005113  jz      short loc_140005100
0x140005115  cmp     qword ptr [rbx+8], 0
0x14000511a  jnz     short loc_140005100
0x14000511c  lea     rax, [rdi+4]
0x140005120  mov     [rbx+8], rax
0x140005124  jmp     short loc_140005100
```
