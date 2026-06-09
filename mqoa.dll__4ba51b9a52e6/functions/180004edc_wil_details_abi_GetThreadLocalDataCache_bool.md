# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004edc`
- end: `0x180004f9c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `192`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046c0`

## callees

- `0x180003d10`
- `0x180004edc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004f36`
- `KERNEL32!GetCurrentThreadId` at `0x180004f36`

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
0x180004edc  mov     [rsp+arg_0], rbx
0x180004ee1  push    rdi
0x180004ee2  sub     rsp, 20h
0x180004ee6  xor     ebx, ebx
0x180004ee8  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004eef  test    rdi, rdi
0x180004ef2  jz      loc_180004F8E
0x180004ef8  cmp     [rdi+8], rbx
0x180004efc  jnz     short loc_180004F23
0x180004efe  mov     [rsp+28h+arg_8], rbx
0x180004f03  lea     rdx, [rsp+28h+arg_8]
0x180004f08  mov     rcx, [rdi]
0x180004f0b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004f10  test    eax, eax
0x180004f12  js      short loc_180004F23
0x180004f14  cmp     [rdi+8], rbx
0x180004f18  jnz     short loc_180004F23
0x180004f1a  mov     rax, [rsp+28h+arg_8]
0x180004f1f  mov     [rdi+8], rax
0x180004f23  mov     rcx, [rdi+8]
0x180004f27  lea     rax, [rcx+20h]
0x180004f2b  neg     rcx
0x180004f2e  sbb     rdi, rdi
0x180004f31  and     rdi, rax
0x180004f34  jz      short loc_180004F8E
0x180004f36  call    cs:__imp_GetCurrentThreadId
0x180004f3c  mov     r9d, eax
0x180004f3f  mov     r8d, eax
0x180004f42  shr     r8, 2
0x180004f46  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004f50  mul     r8
0x180004f53  shr     rdx, 3
0x180004f57  lea     rcx, [rdx+rdx*4]
0x180004f5b  add     rcx, rcx
0x180004f5e  sub     r8, rcx
0x180004f61  mov     rbx, [rdi+r8*8+8]
0x180004f66  test    rbx, rbx
0x180004f69  jz      short loc_180004F7A
0x180004f6b  cmp     [rbx], r9d
0x180004f6e  jz      short loc_180004F76
0x180004f70  mov     rbx, [rbx+8]
0x180004f74  jmp     short loc_180004F66
0x180004f76  add     rbx, 10h
0x180004f7a  test    rbx, rbx
0x180004f7d  jz      short loc_180004F8E
0x180004f7f  cmp     qword ptr [rbx+8], 0
0x180004f84  jnz     short loc_180004F8E
0x180004f86  lea     rcx, [rdi+4]
0x180004f8a  mov     [rbx+8], rcx
0x180004f8e  mov     rax, rbx
0x180004f91  mov     rbx, [rsp+28h+arg_0]
0x180004f96  add     rsp, 20h
0x180004f9a  pop     rdi
0x180004f9b  retn
```
