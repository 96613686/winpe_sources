# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004900`
- end: `0x1800049bd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004240`

## callees

- `0x1800038d0`
- `0x180004900`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000495a`
- `KERNEL32!GetCurrentThreadId` at `0x18000495a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004900  mov     [rsp+arg_0], rbx
0x180004905  push    rdi
0x180004906  sub     rsp, 20h
0x18000490a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004911  xor     ebx, ebx
0x180004913  test    rdi, rdi
0x180004916  jz      loc_1800049AF
0x18000491c  cmp     [rdi+8], rbx
0x180004920  jnz     short loc_180004947
0x180004922  mov     rcx, [rdi]
0x180004925  lea     rdx, [rsp+28h+arg_8]
0x18000492a  mov     [rsp+28h+arg_8], rbx
0x18000492f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004934  test    eax, eax
0x180004936  js      short loc_180004947
0x180004938  cmp     [rdi+8], rbx
0x18000493c  jnz     short loc_180004947
0x18000493e  mov     rax, [rsp+28h+arg_8]
0x180004943  mov     [rdi+8], rax
0x180004947  mov     rax, [rdi+8]
0x18000494b  lea     rcx, [rax+20h]
0x18000494f  neg     rax
0x180004952  sbb     rdi, rdi
0x180004955  and     rdi, rcx
0x180004958  jz      short loc_1800049AF
0x18000495a  call    cs:__imp_GetCurrentThreadId
0x180004960  mov     r8d, eax
0x180004963  mov     r9d, eax
0x180004966  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004970  shr     r8, 2
0x180004974  mul     r8
0x180004977  shr     rdx, 3
0x18000497b  lea     rcx, [rdx+rdx*4]
0x18000497f  add     rcx, rcx
0x180004982  sub     r8, rcx
0x180004985  mov     rbx, [rdi+r8*8+8]
0x18000498a  test    rbx, rbx
0x18000498d  jz      short loc_1800049AF
0x18000498f  cmp     [rbx], r9d
0x180004992  jz      short loc_18000499A
0x180004994  mov     rbx, [rbx+8]
0x180004998  jmp     short loc_18000498A
0x18000499a  add     rbx, 10h
0x18000499e  jz      short loc_1800049AF
0x1800049a0  cmp     qword ptr [rbx+8], 0
0x1800049a5  jnz     short loc_1800049AF
0x1800049a7  lea     rax, [rdi+4]
0x1800049ab  mov     [rbx+8], rax
0x1800049af  mov     rax, rbx
0x1800049b2  mov     rbx, [rsp+28h+arg_0]
0x1800049b7  add     rsp, 20h
0x1800049bb  pop     rdi
0x1800049bc  retn
```
