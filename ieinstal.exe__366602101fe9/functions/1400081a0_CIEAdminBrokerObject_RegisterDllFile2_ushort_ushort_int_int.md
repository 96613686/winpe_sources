# CIEAdminBrokerObject::RegisterDllFile2(ushort *,ushort *,int,int)

- ea: `0x1400081a0`
- end: `0x1400081c5`
- name: `?RegisterDllFile2@CIEAdminBrokerObject@@UEAAJPEAG0HH@Z`
- size: `37`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005108`
- `0x1400081a0`

## pseudocode

```c
HRESULT __fastcall CIEAdminBrokerObject::RegisterDllFile2(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        int a5)
{
  CActiveXInstallBroker *v5; // rcx
  HRESULT result; // eax

  v5 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = -2147467259;
  if ( v5 )
    return CActiveXInstallBroker::RegisterDllFile2(v5, a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x1400081a0  sub     rsp, 38h
0x1400081a4  mov     rcx, [rcx+10h]; this
0x1400081a8  mov     eax, 80004005h
0x1400081ad  test    rcx, rcx
0x1400081b0  jz      short loc_1400081BF
0x1400081b2  mov     eax, [rsp+38h+arg_20]
0x1400081b6  mov     [rsp+38h+var_18], eax; int
0x1400081ba  call    ?RegisterDllFile2@CActiveXInstallBroker@@QEAAJPEAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2(ushort *,ushort *,int,int)
0x1400081bf  add     rsp, 38h
0x1400081c3  retn
```
