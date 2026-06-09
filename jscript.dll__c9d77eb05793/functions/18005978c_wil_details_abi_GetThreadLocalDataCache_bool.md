# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18005978c`
- end: `0x180059849`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800591b0`

## callees

- `0x180053484`
- `0x18005978c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800597e6`
- `KERNEL32!GetCurrentThreadId` at `0x1800597e6`

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
0x18005978c  mov     [rsp+arg_0], rbx
0x180059791  push    rdi
0x180059792  sub     rsp, 20h
0x180059796  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18005979d  xor     ebx, ebx
0x18005979f  test    rdi, rdi
0x1800597a2  jz      loc_18005983B
0x1800597a8  cmp     [rdi+8], rbx
0x1800597ac  jnz     short loc_1800597D3
0x1800597ae  mov     rcx, [rdi]
0x1800597b1  lea     rdx, [rsp+28h+arg_8]
0x1800597b6  mov     [rsp+28h+arg_8], rbx
0x1800597bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800597c0  test    eax, eax
0x1800597c2  js      short loc_1800597D3
0x1800597c4  cmp     [rdi+8], rbx
0x1800597c8  jnz     short loc_1800597D3
0x1800597ca  mov     rax, [rsp+28h+arg_8]
0x1800597cf  mov     [rdi+8], rax
0x1800597d3  mov     rax, [rdi+8]
0x1800597d7  lea     rcx, [rax+20h]
0x1800597db  neg     rax
0x1800597de  sbb     rdi, rdi
0x1800597e1  and     rdi, rcx
0x1800597e4  jz      short loc_18005983B
0x1800597e6  call    cs:__imp_GetCurrentThreadId
0x1800597ec  mov     r8d, eax
0x1800597ef  mov     r9d, eax
0x1800597f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800597fc  shr     r8, 2
0x180059800  mul     r8
0x180059803  shr     rdx, 3
0x180059807  lea     rcx, [rdx+rdx*4]
0x18005980b  add     rcx, rcx
0x18005980e  sub     r8, rcx
0x180059811  mov     rbx, [rdi+r8*8+8]
0x180059816  test    rbx, rbx
0x180059819  jz      short loc_18005983B
0x18005981b  cmp     [rbx], r9d
0x18005981e  jz      short loc_180059826
0x180059820  mov     rbx, [rbx+8]
0x180059824  jmp     short loc_180059816
0x180059826  add     rbx, 10h
0x18005982a  jz      short loc_18005983B
0x18005982c  cmp     qword ptr [rbx+8], 0
0x180059831  jnz     short loc_18005983B
0x180059833  lea     rax, [rdi+4]
0x180059837  mov     [rbx+8], rax
0x18005983b  mov     rax, rbx
0x18005983e  mov     rbx, [rsp+28h+arg_0]
0x180059843  add     rsp, 20h
0x180059847  pop     rdi
0x180059848  retn
```
