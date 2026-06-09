# CUACCheck::_ResetWatcher(void)

- ea: `0x180001390`
- end: `0x18000147f`
- name: `?_ResetWatcher@CUACCheck@@AEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(CUACCheck *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001320`

## callees

- `0x180001390`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800013ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800013ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180001460`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180001460`

## pseudocode

```c
__int64 __fastcall CUACCheck::_ResetWatcher(CUACCheck *this)
{
  HRESULT v2; // ebx
  __int64 result; // rax
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF
  __int64 v5; // [rsp+60h] [rbp+18h] BYREF

  v5 = 0;
  ppv = 0;
  v2 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
           ppv,
           CUACCheckProviderSSO::s_dwCookie,
           &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
           &v5);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v2 >= 0 )
    {
      result = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 32LL))(
                 v5,
                 &qword_18000D440,
                 100,
                 0,
                 0,
                 0);
      v2 = result;
      if ( (int)result < 0 )
        return result;
      SetThreadpoolWait(*((PTP_WAIT *)this + 29), *((HANDLE *)this + 28), 0);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001390  mov     [rsp+arg_0], rbx
0x180001395  mov     [rsp+arg_18], rsi
0x18000139a  push    rdi
0x18000139b  sub     rsp, 40h
0x18000139f  mov     rdi, rcx
0x1800013a2  lea     rax, [rsp+48h+arg_8]
0x1800013a7  xor     esi, esi
0x1800013a9  mov     [rsp+48h+ppv], rax; ppv
0x1800013ae  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800013b5  mov     [rsp+48h+arg_10], rsi
0x1800013ba  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800013c1  mov     [rsp+48h+arg_8], rsi
0x1800013c6  xor     edx, edx; pUnkOuter
0x1800013c8  mov     r8d, 1; dwClsContext
0x1800013ce  call    cs:__imp_CoCreateInstance
0x1800013d5  nop     dword ptr [rax+rax+00h]
0x1800013da  mov     ebx, eax
0x1800013dc  test    eax, eax
0x1800013de  js      loc_18000146C
0x1800013e4  mov     rcx, [rsp+48h+arg_8]
0x1800013e9  lea     r9, [rsp+48h+arg_10]
0x1800013ee  mov     edx, cs:?s_dwCookie@CUACCheckProviderSSO@@0KA; ulong CUACCheckProviderSSO::s_dwCookie
0x1800013f4  lea     r8, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x1800013fb  mov     rax, [rcx]
0x1800013fe  mov     rax, [rax+28h]
0x180001402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001407  mov     rcx, [rsp+48h+arg_8]
0x18000140c  mov     ebx, eax
0x18000140e  mov     rax, [rcx]
0x180001411  mov     rax, [rax+10h]
0x180001415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000141a  test    ebx, ebx
0x18000141c  js      short loc_18000146C
0x18000141e  mov     rcx, [rsp+48h+arg_10]
0x180001423  lea     rdx, qword_18000D440
0x18000142a  mov     [rsp+48h+var_20], rsi
0x18000142f  xor     r9d, r9d
0x180001432  mov     r8d, 64h ; 'd'
0x180001438  mov     [rsp+48h+ppv], rsi
0x18000143d  mov     rax, [rcx]
0x180001440  mov     rax, [rax+20h]
0x180001444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001449  mov     ebx, eax
0x18000144b  test    eax, eax
0x18000144d  js      short loc_18000146E
0x18000144f  mov     rdx, [rdi+0E0h]; h
0x180001456  xor     r8d, r8d; pftTimeout
0x180001459  mov     rcx, [rdi+0E8h]; pwa
0x180001460  call    cs:__imp_SetThreadpoolWait
0x180001467  nop     dword ptr [rax+rax+00h]
0x18000146c  mov     eax, ebx
0x18000146e  mov     rbx, [rsp+48h+arg_0]
0x180001473  mov     rsi, [rsp+48h+arg_18]
0x180001478  add     rsp, 40h
0x18000147c  pop     rdi
0x18000147d  retn
```
