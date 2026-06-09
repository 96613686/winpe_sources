# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008590`
- end: `0x18000864d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077d0`

## callees

- `0x1800064fc`
- `0x180008590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180008590  mov     [rsp+arg_0], rbx
0x180008595  push    rdi
0x180008596  sub     rsp, 20h
0x18000859a  xor     ebx, ebx
0x18000859c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800085a3  test    rdi, rdi
0x1800085a6  jz      loc_18000863F
0x1800085ac  cmp     [rdi+8], rbx
0x1800085b0  jnz     short loc_1800085D7
0x1800085b2  mov     [rsp+28h+arg_8], rbx
0x1800085b7  lea     rdx, [rsp+28h+arg_8]
0x1800085bc  mov     rcx, [rdi]
0x1800085bf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800085c4  test    eax, eax
0x1800085c6  js      short loc_1800085D7
0x1800085c8  cmp     [rdi+8], rbx
0x1800085cc  jnz     short loc_1800085D7
0x1800085ce  mov     rax, [rsp+28h+arg_8]
0x1800085d3  mov     [rdi+8], rax
0x1800085d7  mov     rcx, [rdi+8]
0x1800085db  lea     rax, [rcx+20h]
0x1800085df  neg     rcx
0x1800085e2  sbb     rdi, rdi
0x1800085e5  and     rdi, rax
0x1800085e8  jz      short loc_18000863F
0x1800085ea  call    cs:__imp_GetCurrentThreadId
0x1800085f0  mov     r9d, eax
0x1800085f3  mov     r8d, eax
0x1800085f6  shr     r8, 2
0x1800085fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008604  mul     r8
0x180008607  shr     rdx, 3
0x18000860b  lea     rcx, [rdx+rdx*4]
0x18000860f  add     rcx, rcx
0x180008612  sub     r8, rcx
0x180008615  mov     rbx, [rdi+r8*8+8]
0x18000861a  test    rbx, rbx
0x18000861d  jz      short loc_18000863F
0x18000861f  cmp     [rbx], r9d
0x180008622  jz      short loc_18000862A
0x180008624  mov     rbx, [rbx+8]
0x180008628  jmp     short loc_18000861A
0x18000862a  add     rbx, 10h
0x18000862e  jz      short loc_18000863F
0x180008630  cmp     qword ptr [rbx+8], 0
0x180008635  jnz     short loc_18000863F
0x180008637  lea     rax, [rdi+4]
0x18000863b  mov     [rbx+8], rax
0x18000863f  mov     rax, rbx
0x180008642  mov     rbx, [rsp+28h+arg_0]
0x180008647  add     rsp, 20h
0x18000864b  pop     rdi
0x18000864c  retn
```
