# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140007274`
- end: `0x14000732f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006b00`

## callees

- `0x140004bd0`
- `0x140007274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400072ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400072ca`

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
0x140007274  mov     [rsp+arg_0], rbx
0x140007279  push    rdi
0x14000727a  sub     rsp, 20h
0x14000727e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140007285  xor     ebx, ebx
0x140007287  test    rdi, rdi
0x14000728a  jz      short loc_14000730A
0x14000728c  cmp     [rdi+8], rbx
0x140007290  jnz     short loc_1400072B7
0x140007292  mov     rcx, [rdi]
0x140007295  lea     rdx, [rsp+28h+arg_8]
0x14000729a  mov     [rsp+28h+arg_8], rbx
0x14000729f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400072a4  test    eax, eax
0x1400072a6  js      short loc_1400072B7
0x1400072a8  cmp     [rdi+8], rbx
0x1400072ac  jnz     short loc_1400072B7
0x1400072ae  mov     rax, [rsp+28h+arg_8]
0x1400072b3  mov     [rdi+8], rax
0x1400072b7  mov     rax, [rdi+8]
0x1400072bb  lea     rcx, [rax+20h]
0x1400072bf  neg     rax
0x1400072c2  sbb     rdi, rdi
0x1400072c5  and     rdi, rcx
0x1400072c8  jz      short loc_14000730A
0x1400072ca  call    cs:__imp_GetCurrentThreadId
0x1400072d0  mov     r8d, eax
0x1400072d3  mov     r9d, eax
0x1400072d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400072e0  shr     r8, 2
0x1400072e4  mul     r8
0x1400072e7  shr     rdx, 3
0x1400072eb  lea     rcx, [rdx+rdx*4]
0x1400072ef  add     rcx, rcx
0x1400072f2  sub     r8, rcx
0x1400072f5  mov     rbx, [rdi+r8*8+8]
0x1400072fa  jmp     short loc_140007305
0x1400072fc  cmp     [rbx], r9d
0x1400072ff  jz      short loc_140007318
0x140007301  mov     rbx, [rbx+8]
0x140007305  test    rbx, rbx
0x140007308  jnz     short loc_1400072FC
0x14000730a  mov     rax, rbx
0x14000730d  mov     rbx, [rsp+28h+arg_0]
0x140007312  add     rsp, 20h
0x140007316  pop     rdi
0x140007317  retn
0x140007318  add     rbx, 10h
0x14000731c  jz      short loc_14000730A
0x14000731e  cmp     qword ptr [rbx+8], 0
0x140007323  jnz     short loc_14000730A
0x140007325  lea     rax, [rdi+4]
0x140007329  mov     [rbx+8], rax
0x14000732d  jmp     short loc_14000730A
```
