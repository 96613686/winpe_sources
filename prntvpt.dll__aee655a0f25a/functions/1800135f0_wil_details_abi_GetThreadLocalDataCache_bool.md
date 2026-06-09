# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800135f0`
- end: `0x1800136ad`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012df0`

## callees

- `0x18001145c`
- `0x1800135f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001364a`
- `KERNEL32!GetCurrentThreadId` at `0x18001364a`

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
0x1800135f0  mov     [rsp+arg_0], rbx
0x1800135f5  push    rdi
0x1800135f6  sub     rsp, 20h
0x1800135fa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180013601  xor     ebx, ebx
0x180013603  test    rdi, rdi
0x180013606  jz      loc_18001369F
0x18001360c  cmp     [rdi+8], rbx
0x180013610  jnz     short loc_180013637
0x180013612  mov     rcx, [rdi]
0x180013615  lea     rdx, [rsp+28h+arg_8]
0x18001361a  mov     [rsp+28h+arg_8], rbx
0x18001361f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180013624  test    eax, eax
0x180013626  js      short loc_180013637
0x180013628  cmp     [rdi+8], rbx
0x18001362c  jnz     short loc_180013637
0x18001362e  mov     rax, [rsp+28h+arg_8]
0x180013633  mov     [rdi+8], rax
0x180013637  mov     rax, [rdi+8]
0x18001363b  lea     rcx, [rax+20h]
0x18001363f  neg     rax
0x180013642  sbb     rdi, rdi
0x180013645  and     rdi, rcx
0x180013648  jz      short loc_18001369F
0x18001364a  call    cs:__imp_GetCurrentThreadId
0x180013650  mov     r8d, eax
0x180013653  mov     r9d, eax
0x180013656  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013660  shr     r8, 2
0x180013664  mul     r8
0x180013667  shr     rdx, 3
0x18001366b  lea     rcx, [rdx+rdx*4]
0x18001366f  add     rcx, rcx
0x180013672  sub     r8, rcx
0x180013675  mov     rbx, [rdi+r8*8+8]
0x18001367a  test    rbx, rbx
0x18001367d  jz      short loc_18001369F
0x18001367f  cmp     [rbx], r9d
0x180013682  jz      short loc_18001368A
0x180013684  mov     rbx, [rbx+8]
0x180013688  jmp     short loc_18001367A
0x18001368a  add     rbx, 10h
0x18001368e  jz      short loc_18001369F
0x180013690  cmp     qword ptr [rbx+8], 0
0x180013695  jnz     short loc_18001369F
0x180013697  lea     rax, [rdi+4]
0x18001369b  mov     [rbx+8], rax
0x18001369f  mov     rax, rbx
0x1800136a2  mov     rbx, [rsp+28h+arg_0]
0x1800136a7  add     rsp, 20h
0x1800136ab  pop     rdi
0x1800136ac  retn
```
