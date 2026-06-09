# CActiveXInstallSecurityManager::QueryCustomPolicy(_GUID const &,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x14000bf00`
- end: `0x14000bf61`
- name: `?QueryCustomPolicy@CActiveXInstallSecurityManager@@UEAAJAEBU_GUID@@PEAPEAEPEAKPEAEKK@Z`
- size: `97`
- prototype: `__int64 __fastcall(CActiveXInstallSecurityManager *__hidden this, const struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000bf00`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CActiveXInstallSecurityManager::QueryCustomPolicy(
        CActiveXInstallSecurityManager *this,
        const struct _GUID *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx

  result = 2147500037LL;
  v9 = *((_QWORD *)this + 2);
  if ( v9 )
  {
    v10 = *((_QWORD *)this + 3);
    if ( v10 )
      return (*(__int64 (__fastcall **)(__int64, __int64, const struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int))(*(_QWORD *)v10 + 64LL))(
               v10,
               v9,
               a2,
               a3,
               a4,
               a5,
               a6,
               a7);
  }
  return result;
}

```

## disassembly

```asm
0x14000bf00  sub     rsp, 58h
0x14000bf04  mov     r11, rdx
0x14000bf07  mov     eax, 80004005h
0x14000bf0c  mov     rdx, [rcx+10h]
0x14000bf10  test    rdx, rdx
0x14000bf13  jz      short loc_14000BF5B
0x14000bf15  mov     rcx, [rcx+18h]
0x14000bf19  test    rcx, rcx
0x14000bf1c  jz      short loc_14000BF5B
0x14000bf1e  mov     rax, [rcx]
0x14000bf21  mov     r10, [rax+40h]
0x14000bf25  mov     eax, [rsp+58h+arg_30]
0x14000bf2c  mov     [rsp+58h+var_20], eax
0x14000bf30  mov     eax, [rsp+58h+arg_28]
0x14000bf37  mov     [rsp+58h+var_28], eax
0x14000bf3b  mov     rax, [rsp+58h+arg_20]
0x14000bf43  mov     [rsp+58h+var_30], rax
0x14000bf48  mov     rax, r10
0x14000bf4b  mov     [rsp+58h+var_38], r9
0x14000bf50  mov     r9, r8
0x14000bf53  mov     r8, r11
0x14000bf56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf5b  add     rsp, 58h
0x14000bf5f  retn
```
