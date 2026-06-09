# CIEAdminBrokerObject::InstallCatalogFile(ushort *,ushort *)

- ea: `0x140007fb0`
- end: `0x140007fcd`
- name: `?InstallCatalogFile@CIEAdminBrokerObject@@UEAAJPEAG0@Z`
- size: `29`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004c88`
- `0x140007fb0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::InstallCatalogFile(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CActiveXInstallBroker *v3; // rcx
  __int64 result; // rax

  v3 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v3 )
    return CActiveXInstallBroker::InstallCatalogFile(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x140007fb0  sub     rsp, 28h
0x140007fb4  mov     rcx, [rcx+10h]; this
0x140007fb8  mov     eax, 80004005h
0x140007fbd  test    rcx, rcx
0x140007fc0  jz      short loc_140007FC7
0x140007fc2  call    ?InstallCatalogFile@CActiveXInstallBroker@@QEAAJPEAG0@Z; CActiveXInstallBroker::InstallCatalogFile(ushort *,ushort *)
0x140007fc7  add     rsp, 28h
0x140007fcb  retn
```
