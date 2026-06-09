# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000586c`
- end: `0x180005927`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005090`

## callees

- `0x18000410c`
- `0x18000586c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058c2`

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
0x18000586c  mov     [rsp+arg_0], rbx
0x180005871  push    rdi
0x180005872  sub     rsp, 20h
0x180005876  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000587d  xor     ebx, ebx
0x18000587f  test    rdi, rdi
0x180005882  jz      short loc_180005902
0x180005884  cmp     [rdi+8], rbx
0x180005888  jnz     short loc_1800058AF
0x18000588a  mov     rcx, [rdi]
0x18000588d  lea     rdx, [rsp+28h+arg_8]
0x180005892  mov     [rsp+28h+arg_8], rbx
0x180005897  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000589c  test    eax, eax
0x18000589e  js      short loc_1800058AF
0x1800058a0  cmp     [rdi+8], rbx
0x1800058a4  jnz     short loc_1800058AF
0x1800058a6  mov     rax, [rsp+28h+arg_8]
0x1800058ab  mov     [rdi+8], rax
0x1800058af  mov     rax, [rdi+8]
0x1800058b3  lea     rcx, [rax+20h]
0x1800058b7  neg     rax
0x1800058ba  sbb     rdi, rdi
0x1800058bd  and     rdi, rcx
0x1800058c0  jz      short loc_180005902
0x1800058c2  call    cs:__imp_GetCurrentThreadId
0x1800058c8  mov     r8d, eax
0x1800058cb  mov     r9d, eax
0x1800058ce  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800058d8  shr     r8, 2
0x1800058dc  mul     r8
0x1800058df  shr     rdx, 3
0x1800058e3  lea     rcx, [rdx+rdx*4]
0x1800058e7  add     rcx, rcx
0x1800058ea  sub     r8, rcx
0x1800058ed  mov     rbx, [rdi+r8*8+8]
0x1800058f2  jmp     short loc_1800058FD
0x1800058f4  cmp     [rbx], r9d
0x1800058f7  jz      short loc_180005910
0x1800058f9  mov     rbx, [rbx+8]
0x1800058fd  test    rbx, rbx
0x180005900  jnz     short loc_1800058F4
0x180005902  mov     rax, rbx
0x180005905  mov     rbx, [rsp+28h+arg_0]
0x18000590a  add     rsp, 20h
0x18000590e  pop     rdi
0x18000590f  retn
0x180005910  add     rbx, 10h
0x180005914  jz      short loc_180005902
0x180005916  cmp     qword ptr [rbx+8], 0
0x18000591b  jnz     short loc_180005902
0x18000591d  lea     rax, [rdi+4]
0x180005921  mov     [rbx+8], rax
0x180005925  jmp     short loc_180005902
```
