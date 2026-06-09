# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004c80`
- end: `0x180004d40`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `192`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045d0`

## callees

- `0x180003ce0`
- `0x180004c80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004cda`
- `KERNEL32!GetCurrentThreadId` at `0x180004cda`

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
          break;
        }
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180004c80  mov     [rsp+arg_0], rbx
0x180004c85  push    rdi
0x180004c86  sub     rsp, 20h
0x180004c8a  xor     ebx, ebx
0x180004c8c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004c93  test    rdi, rdi
0x180004c96  jz      loc_180004D32
0x180004c9c  cmp     [rdi+8], rbx
0x180004ca0  jnz     short loc_180004CC7
0x180004ca2  mov     [rsp+28h+arg_8], rbx
0x180004ca7  lea     rdx, [rsp+28h+arg_8]
0x180004cac  mov     rcx, [rdi]
0x180004caf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004cb4  test    eax, eax
0x180004cb6  js      short loc_180004CC7
0x180004cb8  cmp     [rdi+8], rbx
0x180004cbc  jnz     short loc_180004CC7
0x180004cbe  mov     rax, [rsp+28h+arg_8]
0x180004cc3  mov     [rdi+8], rax
0x180004cc7  mov     rcx, [rdi+8]
0x180004ccb  lea     rax, [rcx+20h]
0x180004ccf  neg     rcx
0x180004cd2  sbb     rdi, rdi
0x180004cd5  and     rdi, rax
0x180004cd8  jz      short loc_180004D32
0x180004cda  call    cs:__imp_GetCurrentThreadId
0x180004ce0  mov     r9d, eax
0x180004ce3  mov     r8d, eax
0x180004ce6  shr     r8, 2
0x180004cea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004cf4  mul     r8
0x180004cf7  shr     rdx, 3
0x180004cfb  lea     rcx, [rdx+rdx*4]
0x180004cff  add     rcx, rcx
0x180004d02  sub     r8, rcx
0x180004d05  mov     rbx, [rdi+r8*8+8]
0x180004d0a  test    rbx, rbx
0x180004d0d  jz      short loc_180004D1E
0x180004d0f  cmp     [rbx], r9d
0x180004d12  jz      short loc_180004D1A
0x180004d14  mov     rbx, [rbx+8]
0x180004d18  jmp     short loc_180004D0A
0x180004d1a  add     rbx, 10h
0x180004d1e  test    rbx, rbx
0x180004d21  jz      short loc_180004D32
0x180004d23  cmp     qword ptr [rbx+8], 0
0x180004d28  jnz     short loc_180004D32
0x180004d2a  lea     rcx, [rdi+4]
0x180004d2e  mov     [rbx+8], rcx
0x180004d32  mov     rax, rbx
0x180004d35  mov     rbx, [rsp+28h+arg_0]
0x180004d3a  add     rsp, 20h
0x180004d3e  pop     rdi
0x180004d3f  retn
```
