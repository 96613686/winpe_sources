# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180010818`
- end: `0x1800108d5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800101a0`

## callees

- `0x18000fb50`
- `0x180010818`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010872`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010872`

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
0x180010818  mov     [rsp+arg_0], rbx
0x18001081d  push    rdi
0x18001081e  sub     rsp, 20h
0x180010822  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180010829  xor     ebx, ebx
0x18001082b  test    rdi, rdi
0x18001082e  jz      loc_1800108C7
0x180010834  cmp     [rdi+8], rbx
0x180010838  jnz     short loc_18001085F
0x18001083a  mov     rcx, [rdi]
0x18001083d  lea     rdx, [rsp+28h+arg_8]
0x180010842  mov     [rsp+28h+arg_8], rbx
0x180010847  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001084c  test    eax, eax
0x18001084e  js      short loc_18001085F
0x180010850  cmp     [rdi+8], rbx
0x180010854  jnz     short loc_18001085F
0x180010856  mov     rax, [rsp+28h+arg_8]
0x18001085b  mov     [rdi+8], rax
0x18001085f  mov     rax, [rdi+8]
0x180010863  lea     rcx, [rax+20h]
0x180010867  neg     rax
0x18001086a  sbb     rdi, rdi
0x18001086d  and     rdi, rcx
0x180010870  jz      short loc_1800108C7
0x180010872  call    cs:__imp_GetCurrentThreadId
0x180010878  mov     r8d, eax
0x18001087b  mov     r9d, eax
0x18001087e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180010888  shr     r8, 2
0x18001088c  mul     r8
0x18001088f  shr     rdx, 3
0x180010893  lea     rcx, [rdx+rdx*4]
0x180010897  add     rcx, rcx
0x18001089a  sub     r8, rcx
0x18001089d  mov     rbx, [rdi+r8*8+8]
0x1800108a2  test    rbx, rbx
0x1800108a5  jz      short loc_1800108C7
0x1800108a7  cmp     [rbx], r9d
0x1800108aa  jz      short loc_1800108B2
0x1800108ac  mov     rbx, [rbx+8]
0x1800108b0  jmp     short loc_1800108A2
0x1800108b2  add     rbx, 10h
0x1800108b6  jz      short loc_1800108C7
0x1800108b8  cmp     qword ptr [rbx+8], 0
0x1800108bd  jnz     short loc_1800108C7
0x1800108bf  lea     rax, [rdi+4]
0x1800108c3  mov     [rbx+8], rax
0x1800108c7  mov     rax, rbx
0x1800108ca  mov     rbx, [rsp+28h+arg_0]
0x1800108cf  add     rsp, 20h
0x1800108d3  pop     rdi
0x1800108d4  retn
```
