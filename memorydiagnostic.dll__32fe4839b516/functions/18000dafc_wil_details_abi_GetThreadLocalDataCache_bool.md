# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000dafc`
- end: `0x18000dbc1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d070`

## callees

- `0x180008cc4`
- `0x18000dafc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000db56`
- `KERNEL32!GetCurrentThreadId` at `0x18000db56`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x18000dafc  mov     [rsp+arg_0], rbx
0x18000db01  push    rdi
0x18000db02  sub     rsp, 20h
0x18000db06  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000db0d  xor     edi, edi
0x18000db0f  test    rbx, rbx
0x18000db12  jz      loc_18000DBB2
0x18000db18  cmp     [rbx+8], rdi
0x18000db1c  jnz     short loc_18000DB43
0x18000db1e  mov     rcx, [rbx]
0x18000db21  lea     rdx, [rsp+28h+arg_8]
0x18000db26  and     [rsp+28h+arg_8], rdi
0x18000db2b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000db30  test    eax, eax
0x18000db32  js      short loc_18000DB43
0x18000db34  cmp     [rbx+8], rdi
0x18000db38  jnz     short loc_18000DB43
0x18000db3a  mov     rax, [rsp+28h+arg_8]
0x18000db3f  mov     [rbx+8], rax
0x18000db43  mov     rax, [rbx+8]
0x18000db47  lea     rcx, [rax+20h]
0x18000db4b  neg     rax
0x18000db4e  sbb     rbx, rbx
0x18000db51  and     rbx, rcx
0x18000db54  jz      short loc_18000DBB2
0x18000db56  call    cs:__imp_GetCurrentThreadId
0x18000db5d  nop     dword ptr [rax+rax+00h]
0x18000db62  mov     r8d, eax
0x18000db65  mov     r9d, eax
0x18000db68  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000db72  mul     r9
0x18000db75  shr     rdx, 3
0x18000db79  lea     rcx, [rdx+rdx*4]
0x18000db7d  add     rcx, rcx
0x18000db80  sub     r8, rcx
0x18000db83  mov     rcx, [rbx+r8*8+8]
0x18000db88  jmp     short loc_18000DB93
0x18000db8a  cmp     [rcx], r9d
0x18000db8d  jz      short loc_18000DB9A
0x18000db8f  mov     rcx, [rcx+8]
0x18000db93  test    rcx, rcx
0x18000db96  jnz     short loc_18000DB8A
0x18000db98  jmp     short loc_18000DBB2
0x18000db9a  add     rcx, 10h
0x18000db9e  mov     rdi, rcx
0x18000dba1  jz      short loc_18000DBB2
0x18000dba3  cmp     qword ptr [rcx+8], 0
0x18000dba8  jnz     short loc_18000DBB2
0x18000dbaa  lea     rax, [rbx+4]
0x18000dbae  mov     [rcx+8], rax
0x18000dbb2  mov     rbx, [rsp+28h+arg_0]
0x18000dbb7  mov     rax, rdi
0x18000dbba  add     rsp, 20h
0x18000dbbe  pop     rdi
0x18000dbbf  retn
```
