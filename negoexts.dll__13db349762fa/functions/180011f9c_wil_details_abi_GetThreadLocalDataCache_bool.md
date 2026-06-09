# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180011f9c`
- end: `0x180012059`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800117d0`

## callees

- `0x180010b6c`
- `0x180011f9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ff6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ff6`

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
0x180011f9c  mov     [rsp+arg_0], rbx
0x180011fa1  push    rdi
0x180011fa2  sub     rsp, 20h
0x180011fa6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180011fad  xor     ebx, ebx
0x180011faf  test    rdi, rdi
0x180011fb2  jz      loc_18001204B
0x180011fb8  cmp     [rdi+8], rbx
0x180011fbc  jnz     short loc_180011FE3
0x180011fbe  mov     rcx, [rdi]
0x180011fc1  lea     rdx, [rsp+28h+arg_8]
0x180011fc6  mov     [rsp+28h+arg_8], rbx
0x180011fcb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180011fd0  test    eax, eax
0x180011fd2  js      short loc_180011FE3
0x180011fd4  cmp     [rdi+8], rbx
0x180011fd8  jnz     short loc_180011FE3
0x180011fda  mov     rax, [rsp+28h+arg_8]
0x180011fdf  mov     [rdi+8], rax
0x180011fe3  mov     rax, [rdi+8]
0x180011fe7  lea     rcx, [rax+20h]
0x180011feb  neg     rax
0x180011fee  sbb     rdi, rdi
0x180011ff1  and     rdi, rcx
0x180011ff4  jz      short loc_18001204B
0x180011ff6  call    cs:__imp_GetCurrentThreadId
0x180011ffc  mov     r8d, eax
0x180011fff  mov     r9d, eax
0x180012002  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001200c  shr     r8, 2
0x180012010  mul     r8
0x180012013  shr     rdx, 3
0x180012017  lea     rcx, [rdx+rdx*4]
0x18001201b  add     rcx, rcx
0x18001201e  sub     r8, rcx
0x180012021  mov     rbx, [rdi+r8*8+8]
0x180012026  test    rbx, rbx
0x180012029  jz      short loc_18001204B
0x18001202b  cmp     [rbx], r9d
0x18001202e  jz      short loc_180012036
0x180012030  mov     rbx, [rbx+8]
0x180012034  jmp     short loc_180012026
0x180012036  add     rbx, 10h
0x18001203a  jz      short loc_18001204B
0x18001203c  cmp     qword ptr [rbx+8], 0
0x180012041  jnz     short loc_18001204B
0x180012043  lea     rax, [rdi+4]
0x180012047  mov     [rbx+8], rax
0x18001204b  mov     rax, rbx
0x18001204e  mov     rbx, [rsp+28h+arg_0]
0x180012053  add     rsp, 20h
0x180012057  pop     rdi
0x180012058  retn
```
