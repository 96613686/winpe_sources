# CIEAdminBrokerObject::InstallFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong)

- ea: `0x140007fe0`
- end: `0x140008029`
- name: `?InstallFile@CIEAdminBrokerObject@@UEAAJPEAGPEAUHWND__@@0000K@Z`
- size: `73`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004e20`
- `0x140007fe0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::InstallFile(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        HWND a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int a8)
{
  CActiveXInstallBroker *v8; // rcx
  __int64 result; // rax

  v8 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v8 )
    return CActiveXInstallBroker::InstallFile(v8, a2, a3, a4, a5, a6, a7, a8);
  return result;
}

```

## disassembly

```asm
0x140007fe0  sub     rsp, 48h
0x140007fe4  mov     rcx, [rcx+10h]; this
0x140007fe8  mov     eax, 80004005h
0x140007fed  test    rcx, rcx
0x140007ff0  jz      short loc_140008023
0x140007ff2  mov     eax, [rsp+48h+arg_38]
0x140007ff9  mov     [rsp+48h+var_10], eax; unsigned int
0x140007ffd  mov     rax, [rsp+48h+arg_30]
0x140008005  mov     [rsp+48h+var_18], rax; unsigned __int16 *
0x14000800a  mov     rax, [rsp+48h+arg_28]
0x14000800f  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x140008014  mov     rax, [rsp+48h+arg_20]
0x140008019  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x14000801e  call    ?InstallFile@CActiveXInstallBroker@@QEAAJPEAGPEAUHWND__@@0000K@Z; CActiveXInstallBroker::InstallFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong)
0x140008023  add     rsp, 48h
0x140008027  retn
```
