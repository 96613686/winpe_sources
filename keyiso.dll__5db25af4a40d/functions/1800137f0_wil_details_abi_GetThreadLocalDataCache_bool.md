# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800137f0`
- end: `0x1800138ad`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013140`

## callees

- `0x180012668`
- `0x1800137f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001384a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001384a`

## pseudocode

```c
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
0x1800137f0  mov     [rsp+arg_0], rbx
0x1800137f5  push    rdi
0x1800137f6  sub     rsp, 20h
0x1800137fa  xor     ebx, ebx
0x1800137fc  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180013803  test    rdi, rdi
0x180013806  jz      loc_18001389F
0x18001380c  cmp     [rdi+8], rbx
0x180013810  jnz     short loc_180013837
0x180013812  mov     [rsp+28h+arg_8], rbx
0x180013817  lea     rdx, [rsp+28h+arg_8]
0x18001381c  mov     rcx, [rdi]
0x18001381f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180013824  test    eax, eax
0x180013826  js      short loc_180013837
0x180013828  cmp     [rdi+8], rbx
0x18001382c  jnz     short loc_180013837
0x18001382e  mov     rax, [rsp+28h+arg_8]
0x180013833  mov     [rdi+8], rax
0x180013837  mov     rcx, [rdi+8]
0x18001383b  lea     rax, [rcx+20h]
0x18001383f  neg     rcx
0x180013842  sbb     rdi, rdi
0x180013845  and     rdi, rax
0x180013848  jz      short loc_18001389F
0x18001384a  call    cs:__imp_GetCurrentThreadId
0x180013850  mov     r9d, eax
0x180013853  mov     r8d, eax
0x180013856  shr     r8, 2
0x18001385a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013864  mul     r8
0x180013867  shr     rdx, 3
0x18001386b  lea     rcx, [rdx+rdx*4]
0x18001386f  add     rcx, rcx
0x180013872  sub     r8, rcx
0x180013875  mov     rbx, [rdi+r8*8+8]
0x18001387a  test    rbx, rbx
0x18001387d  jz      short loc_18001389F
0x18001387f  cmp     [rbx], r9d
0x180013882  jz      short loc_18001388A
0x180013884  mov     rbx, [rbx+8]
0x180013888  jmp     short loc_18001387A
0x18001388a  add     rbx, 10h
0x18001388e  jz      short loc_18001389F
0x180013890  cmp     qword ptr [rbx+8], 0
0x180013895  jnz     short loc_18001389F
0x180013897  lea     rax, [rdi+4]
0x18001389b  mov     [rbx+8], rax
0x18001389f  mov     rax, rbx
0x1800138a2  mov     rbx, [rsp+28h+arg_0]
0x1800138a7  add     rsp, 20h
0x1800138ab  pop     rdi
0x1800138ac  retn
```
