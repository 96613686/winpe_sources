# CIEAdminBrokerObject::RunSetupCommand(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong,unsigned __int64 *)

- ea: `0x1400082d0`
- end: `0x14000832b`
- name: `?RunSetupCommand@CIEAdminBrokerObject@@UEAAJPEAGPEAUHWND__@@0000KPEA_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005b10`
- `0x1400082d0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::RunSetupCommand(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        HWND a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned __int64 *a9)
{
  CActiveXInstallBroker *v9; // rcx
  __int64 result; // rax

  v9 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v9 )
    return CActiveXInstallBroker::RunSetupCommand(v9, a2, a3, a4, a5, a6, a7, a8, (void **)a9);
  return result;
}

```

## disassembly

```asm
0x1400082d0  mov     r11, rsp
0x1400082d3  sub     rsp, 58h
0x1400082d7  mov     rcx, [rcx+10h]; this
0x1400082db  mov     eax, 80004005h
0x1400082e0  test    rcx, rcx
0x1400082e3  jz      short loc_140008325
0x1400082e5  mov     rax, [rsp+58h+arg_40]
0x1400082ed  mov     [r11-18h], rax
0x1400082f1  mov     eax, [rsp+58h+arg_38]
0x1400082f8  mov     [rsp+58h+var_20], eax; unsigned int
0x1400082fc  mov     rax, [rsp+58h+arg_30]
0x140008304  mov     [r11-28h], rax
0x140008308  mov     rax, [rsp+58h+arg_28]
0x140008310  mov     [r11-30h], rax
0x140008314  mov     rax, [rsp+58h+arg_20]
0x14000831c  mov     [r11-38h], rax
0x140008320  call    ?RunSetupCommand@CActiveXInstallBroker@@QEAAJPEAGPEAUHWND__@@0000KPEAPEAX@Z; CActiveXInstallBroker::RunSetupCommand(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong,void * *)
0x140008325  add     rsp, 58h
0x140008329  retn
```
