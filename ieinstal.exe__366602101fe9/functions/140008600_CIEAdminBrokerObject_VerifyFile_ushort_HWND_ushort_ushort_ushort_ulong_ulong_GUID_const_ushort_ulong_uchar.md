# CIEAdminBrokerObject::VerifyFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ulong,ulong,_GUID const &,ushort * *,ulong *,uchar * *)

- ea: `0x140008600`
- end: `0x14000867e`
- name: `?VerifyFile@CIEAdminBrokerObject@@UEAAJPEAGPEAUHWND__@@000KKAEBU_GUID@@PEAPEAGPEAKPEAPEAE@Z`
- size: `126`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, const struct _GUID *, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000747c`
- `0x140008600`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::VerifyFile(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        HWND a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8,
        const struct _GUID *a9,
        unsigned __int16 **a10,
        unsigned int *a11,
        unsigned __int8 **a12)
{
  CActiveXInstallBroker *v12; // rcx
  __int64 result; // rax

  v12 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v12 )
    return CActiveXInstallBroker::VerifyFile(v12, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12);
  return result;
}

```

## disassembly

```asm
0x140008600  mov     r11, rsp
0x140008603  sub     rsp, 68h
0x140008607  mov     rcx, [rcx+10h]; this
0x14000860b  mov     eax, 80004005h
0x140008610  test    rcx, rcx
0x140008613  jz      short loc_140008678
0x140008615  mov     rax, [rsp+68h+arg_58]
0x14000861d  mov     [r11-10h], rax
0x140008621  mov     rax, [rsp+68h+arg_50]
0x140008629  mov     [r11-18h], rax
0x14000862d  mov     rax, [rsp+68h+arg_48]
0x140008635  mov     [r11-20h], rax
0x140008639  mov     rax, [rsp+68h+arg_40]
0x140008641  mov     [r11-28h], rax
0x140008645  mov     eax, [rsp+68h+arg_38]
0x14000864c  mov     [rsp+68h+var_30], eax; unsigned int
0x140008650  mov     eax, [rsp+68h+arg_30]
0x140008657  mov     [rsp+68h+var_38], eax; unsigned int
0x14000865b  mov     rax, [rsp+68h+arg_28]
0x140008663  mov     [r11-40h], rax
0x140008667  mov     rax, [rsp+68h+arg_20]
0x14000866f  mov     [r11-48h], rax
0x140008673  call    ?VerifyFile@CActiveXInstallBroker@@QEAAJPEAGPEAUHWND__@@000KKAEBU_GUID@@PEAPEAGPEAKPEAPEAE@Z; CActiveXInstallBroker::VerifyFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ulong,ulong,_GUID const &,ushort * *,ulong *,uchar * *)
0x140008678  add     rsp, 68h
0x14000867c  retn
```
