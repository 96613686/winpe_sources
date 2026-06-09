# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001ad64`
- end: `0x18001ae21`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a660`

## callees

- `0x18001966c`
- `0x18001ad64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001adbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001adbe`

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
0x18001ad64  mov     [rsp+arg_0], rbx
0x18001ad69  push    rdi
0x18001ad6a  sub     rsp, 20h
0x18001ad6e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001ad75  xor     ebx, ebx
0x18001ad77  test    rdi, rdi
0x18001ad7a  jz      loc_18001AE13
0x18001ad80  cmp     [rdi+8], rbx
0x18001ad84  jnz     short loc_18001ADAB
0x18001ad86  mov     rcx, [rdi]
0x18001ad89  lea     rdx, [rsp+28h+arg_8]
0x18001ad8e  mov     [rsp+28h+arg_8], rbx
0x18001ad93  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001ad98  test    eax, eax
0x18001ad9a  js      short loc_18001ADAB
0x18001ad9c  cmp     [rdi+8], rbx
0x18001ada0  jnz     short loc_18001ADAB
0x18001ada2  mov     rax, [rsp+28h+arg_8]
0x18001ada7  mov     [rdi+8], rax
0x18001adab  mov     rax, [rdi+8]
0x18001adaf  lea     rcx, [rax+20h]
0x18001adb3  neg     rax
0x18001adb6  sbb     rdi, rdi
0x18001adb9  and     rdi, rcx
0x18001adbc  jz      short loc_18001AE13
0x18001adbe  call    cs:__imp_GetCurrentThreadId
0x18001adc4  mov     r8d, eax
0x18001adc7  mov     r9d, eax
0x18001adca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001add4  shr     r8, 2
0x18001add8  mul     r8
0x18001addb  shr     rdx, 3
0x18001addf  lea     rcx, [rdx+rdx*4]
0x18001ade3  add     rcx, rcx
0x18001ade6  sub     r8, rcx
0x18001ade9  mov     rbx, [rdi+r8*8+8]
0x18001adee  test    rbx, rbx
0x18001adf1  jz      short loc_18001AE13
0x18001adf3  cmp     [rbx], r9d
0x18001adf6  jz      short loc_18001ADFE
0x18001adf8  mov     rbx, [rbx+8]
0x18001adfc  jmp     short loc_18001ADEE
0x18001adfe  add     rbx, 10h
0x18001ae02  jz      short loc_18001AE13
0x18001ae04  cmp     qword ptr [rbx+8], 0
0x18001ae09  jnz     short loc_18001AE13
0x18001ae0b  lea     rax, [rdi+4]
0x18001ae0f  mov     [rbx+8], rax
0x18001ae13  mov     rax, rbx
0x18001ae16  mov     rbx, [rsp+28h+arg_0]
0x18001ae1b  add     rsp, 20h
0x18001ae1f  pop     rdi
0x18001ae20  retn
```
