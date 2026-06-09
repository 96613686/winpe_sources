# CIEAdminBrokerObject::RegisterDllFile(ushort *,ushort *,int)

- ea: `0x1400081d0`
- end: `0x1400081f5`
- name: `?RegisterDllFile@CIEAdminBrokerObject@@UEAAJPEAG0H@Z`
- size: `37`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005108`
- `0x1400081d0`

## pseudocode

```c
HRESULT __fastcall CIEAdminBrokerObject::RegisterDllFile(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  CActiveXInstallBroker *v4; // rcx
  HRESULT result; // eax

  v4 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = -2147467259;
  if ( v4 )
    return CActiveXInstallBroker::RegisterDllFile2(v4, a2, a3, 0, a4);
  return result;
}

```

## disassembly

```asm
0x1400081d0  sub     rsp, 38h
0x1400081d4  mov     rcx, [rcx+10h]; this
0x1400081d8  mov     eax, 80004005h
0x1400081dd  test    rcx, rcx
0x1400081e0  jz      short loc_1400081EF
0x1400081e2  mov     [rsp+38h+var_18], r9d; int
0x1400081e7  xor     r9d, r9d; int
0x1400081ea  call    ?RegisterDllFile2@CActiveXInstallBroker@@QEAAJPEAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2(ushort *,ushort *,int,int)
0x1400081ef  add     rsp, 38h
0x1400081f3  retn
```
