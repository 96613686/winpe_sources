# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180020520`
- end: `0x1800205dd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ffb0`

## callees

- `0x18001f3d8`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002057a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002057a`

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
0x180020520  mov     [rsp+arg_0], rbx
0x180020525  push    rdi
0x180020526  sub     rsp, 20h
0x18002052a  xor     ebx, ebx
0x18002052c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180020533  test    rdi, rdi
0x180020536  jz      loc_1800205CF
0x18002053c  cmp     [rdi+8], rbx
0x180020540  jnz     short loc_180020567
0x180020542  mov     [rsp+28h+arg_8], rbx
0x180020547  lea     rdx, [rsp+28h+arg_8]
0x18002054c  mov     rcx, [rdi]
0x18002054f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180020554  test    eax, eax
0x180020556  js      short loc_180020567
0x180020558  cmp     [rdi+8], rbx
0x18002055c  jnz     short loc_180020567
0x18002055e  mov     rax, [rsp+28h+arg_8]
0x180020563  mov     [rdi+8], rax
0x180020567  mov     rcx, [rdi+8]
0x18002056b  lea     rax, [rcx+20h]
0x18002056f  neg     rcx
0x180020572  sbb     rdi, rdi
0x180020575  and     rdi, rax
0x180020578  jz      short loc_1800205CF
0x18002057a  call    cs:__imp_GetCurrentThreadId
0x180020580  mov     r9d, eax
0x180020583  mov     r8d, eax
0x180020586  shr     r8, 2
0x18002058a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180020594  mul     r8
0x180020597  shr     rdx, 3
0x18002059b  lea     rcx, [rdx+rdx*4]
0x18002059f  add     rcx, rcx
0x1800205a2  sub     r8, rcx
0x1800205a5  mov     rbx, [rdi+r8*8+8]
0x1800205aa  test    rbx, rbx
0x1800205ad  jz      short loc_1800205CF
0x1800205af  cmp     [rbx], r9d
0x1800205b2  jz      short loc_1800205BA
0x1800205b4  mov     rbx, [rbx+8]
0x1800205b8  jmp     short loc_1800205AA
0x1800205ba  add     rbx, 10h
0x1800205be  jz      short loc_1800205CF
0x1800205c0  cmp     qword ptr [rbx+8], 0
0x1800205c5  jnz     short loc_1800205CF
0x1800205c7  lea     rax, [rdi+4]
0x1800205cb  mov     [rbx+8], rax
0x1800205cf  mov     rax, rbx
0x1800205d2  mov     rbx, [rsp+28h+arg_0]
0x1800205d7  add     rsp, 20h
0x1800205db  pop     rdi
0x1800205dc  retn
```
