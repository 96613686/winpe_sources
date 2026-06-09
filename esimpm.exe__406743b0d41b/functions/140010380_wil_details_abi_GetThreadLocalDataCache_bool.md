# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140010380`
- end: `0x14001043b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fba0`

## callees

- `0x14000eb58`
- `0x140010380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400103d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400103d6`

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
0x140010380  mov     [rsp+arg_0], rbx
0x140010385  push    rdi
0x140010386  sub     rsp, 20h
0x14001038a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140010391  xor     ebx, ebx
0x140010393  test    rdi, rdi
0x140010396  jz      short loc_140010416
0x140010398  cmp     [rdi+8], rbx
0x14001039c  jnz     short loc_1400103C3
0x14001039e  mov     rcx, [rdi]
0x1400103a1  lea     rdx, [rsp+28h+arg_8]
0x1400103a6  mov     [rsp+28h+arg_8], rbx
0x1400103ab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400103b0  test    eax, eax
0x1400103b2  js      short loc_1400103C3
0x1400103b4  cmp     [rdi+8], rbx
0x1400103b8  jnz     short loc_1400103C3
0x1400103ba  mov     rax, [rsp+28h+arg_8]
0x1400103bf  mov     [rdi+8], rax
0x1400103c3  mov     rax, [rdi+8]
0x1400103c7  lea     rcx, [rax+20h]
0x1400103cb  neg     rax
0x1400103ce  sbb     rdi, rdi
0x1400103d1  and     rdi, rcx
0x1400103d4  jz      short loc_140010416
0x1400103d6  call    cs:__imp_GetCurrentThreadId
0x1400103dc  mov     r8d, eax
0x1400103df  mov     r9d, eax
0x1400103e2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400103ec  shr     r8, 2
0x1400103f0  mul     r8
0x1400103f3  shr     rdx, 3
0x1400103f7  lea     rcx, [rdx+rdx*4]
0x1400103fb  add     rcx, rcx
0x1400103fe  sub     r8, rcx
0x140010401  mov     rbx, [rdi+r8*8+8]
0x140010406  jmp     short loc_140010411
0x140010408  cmp     [rbx], r9d
0x14001040b  jz      short loc_140010424
0x14001040d  mov     rbx, [rbx+8]
0x140010411  test    rbx, rbx
0x140010414  jnz     short loc_140010408
0x140010416  mov     rax, rbx
0x140010419  mov     rbx, [rsp+28h+arg_0]
0x14001041e  add     rsp, 20h
0x140010422  pop     rdi
0x140010423  retn
0x140010424  add     rbx, 10h
0x140010428  jz      short loc_140010416
0x14001042a  cmp     qword ptr [rbx+8], 0
0x14001042f  jnz     short loc_140010416
0x140010431  lea     rax, [rdi+4]
0x140010435  mov     [rbx+8], rax
0x140010439  jmp     short loc_140010416
```
