# CIEAdminBrokerObject::UpdateModuleUsage(ushort *,char const *,char const *,char const *,char const *,ulong)

- ea: `0x1400085b0`
- end: `0x1400085ec`
- name: `?UpdateModuleUsage@CIEAdminBrokerObject@@UEAAJPEAGPEBD111K@Z`
- size: `60`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const char *, const char *, LPCSTR, const char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006fa4`
- `0x1400085b0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::UpdateModuleUsage(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        const char *a3,
        char *a4,
        const BYTE *lpString2,
        char *a6,
        char a7)
{
  CActiveXInstallBroker *v7; // rcx
  __int64 result; // rax

  v7 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v7 )
    return CActiveXInstallBroker::UpdateModuleUsage(v7, a2, a3, a4, lpString2, a6, a7);
  return result;
}

```

## disassembly

```asm
0x1400085b0  sub     rsp, 48h
0x1400085b4  mov     rcx, [rcx+10h]; this
0x1400085b8  mov     eax, 80004005h
0x1400085bd  test    rcx, rcx
0x1400085c0  jz      short loc_1400085E6
0x1400085c2  mov     eax, [rsp+48h+arg_30]
0x1400085c9  mov     [rsp+48h+var_18], eax; unsigned int
0x1400085cd  mov     rax, [rsp+48h+arg_28]
0x1400085d2  mov     [rsp+48h+var_20], rax; char *
0x1400085d7  mov     rax, [rsp+48h+arg_20]
0x1400085dc  mov     [rsp+48h+lpString2], rax; lpString2
0x1400085e1  call    ?UpdateModuleUsage@CActiveXInstallBroker@@QEAAJPEAGPEBD111K@Z; CActiveXInstallBroker::UpdateModuleUsage(ushort *,char const *,char const *,char const *,char const *,ulong)
0x1400085e6  add     rsp, 48h
0x1400085ea  retn
```
