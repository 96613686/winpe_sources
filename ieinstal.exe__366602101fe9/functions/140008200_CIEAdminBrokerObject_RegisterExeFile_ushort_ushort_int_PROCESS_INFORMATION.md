# CIEAdminBrokerObject::RegisterExeFile(ushort *,ushort *,int,_PROCESS_INFORMATION *)

- ea: `0x140008200`
- end: `0x140008227`
- name: `?RegisterExeFile@CIEAdminBrokerObject@@UEAAJPEAG0HPEAU_PROCESS_INFORMATION@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *, int, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005630`
- `0x140008200`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::RegisterExeFile(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        struct _PROCESS_INFORMATION *a5)
{
  CActiveXInstallBroker *v5; // rcx
  __int64 result; // rax

  v5 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v5 )
    return CActiveXInstallBroker::RegisterExeFile(v5, a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x140008200  sub     rsp, 38h
0x140008204  mov     rcx, [rcx+10h]; this
0x140008208  mov     eax, 80004005h
0x14000820d  test    rcx, rcx
0x140008210  jz      short loc_140008221
0x140008212  mov     rax, [rsp+38h+arg_20]
0x140008217  mov     [rsp+38h+var_18], rax; struct _PROCESS_INFORMATION *
0x14000821c  call    ?RegisterExeFile@CActiveXInstallBroker@@QEAAJPEAG0HPEAU_PROCESS_INFORMATION@@@Z; CActiveXInstallBroker::RegisterExeFile(ushort *,ushort *,int,_PROCESS_INFORMATION *)
0x140008221  add     rsp, 38h
0x140008225  retn
```
