# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000dd3c`
- end: `0x18000ddf9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000da30`

## callees

- `0x18000aeec`
- `0x18000dd3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dd96`

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
0x18000dd3c  mov     [rsp+arg_0], rbx
0x18000dd41  push    rdi
0x18000dd42  sub     rsp, 20h
0x18000dd46  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000dd4d  xor     ebx, ebx
0x18000dd4f  test    rdi, rdi
0x18000dd52  jz      loc_18000DDEB
0x18000dd58  cmp     [rdi+8], rbx
0x18000dd5c  jnz     short loc_18000DD83
0x18000dd5e  mov     rcx, [rdi]
0x18000dd61  lea     rdx, [rsp+28h+arg_8]
0x18000dd66  mov     [rsp+28h+arg_8], rbx
0x18000dd6b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000dd70  test    eax, eax
0x18000dd72  js      short loc_18000DD83
0x18000dd74  cmp     [rdi+8], rbx
0x18000dd78  jnz     short loc_18000DD83
0x18000dd7a  mov     rax, [rsp+28h+arg_8]
0x18000dd7f  mov     [rdi+8], rax
0x18000dd83  mov     rax, [rdi+8]
0x18000dd87  lea     rcx, [rax+20h]
0x18000dd8b  neg     rax
0x18000dd8e  sbb     rdi, rdi
0x18000dd91  and     rdi, rcx
0x18000dd94  jz      short loc_18000DDEB
0x18000dd96  call    cs:__imp_GetCurrentThreadId
0x18000dd9c  mov     r8d, eax
0x18000dd9f  mov     r9d, eax
0x18000dda2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ddac  shr     r8, 2
0x18000ddb0  mul     r8
0x18000ddb3  shr     rdx, 3
0x18000ddb7  lea     rcx, [rdx+rdx*4]
0x18000ddbb  add     rcx, rcx
0x18000ddbe  sub     r8, rcx
0x18000ddc1  mov     rbx, [rdi+r8*8+8]
0x18000ddc6  test    rbx, rbx
0x18000ddc9  jz      short loc_18000DDEB
0x18000ddcb  cmp     [rbx], r9d
0x18000ddce  jz      short loc_18000DDD6
0x18000ddd0  mov     rbx, [rbx+8]
0x18000ddd4  jmp     short loc_18000DDC6
0x18000ddd6  add     rbx, 10h
0x18000ddda  jz      short loc_18000DDEB
0x18000dddc  cmp     qword ptr [rbx+8], 0
0x18000dde1  jnz     short loc_18000DDEB
0x18000dde3  lea     rax, [rdi+4]
0x18000dde7  mov     [rbx+8], rax
0x18000ddeb  mov     rax, rbx
0x18000ddee  mov     rbx, [rsp+28h+arg_0]
0x18000ddf3  add     rsp, 20h
0x18000ddf7  pop     rdi
0x18000ddf8  retn
```
