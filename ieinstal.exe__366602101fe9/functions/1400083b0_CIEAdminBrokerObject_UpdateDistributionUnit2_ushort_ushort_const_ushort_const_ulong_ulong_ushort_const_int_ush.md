# CIEAdminBrokerObject::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)

- ea: `0x1400083b0`
- end: `0x14000848b`
- name: `?UpdateDistributionUnit2@CIEAdminBrokerObject@@UEAAJPEAGPEBG1KPEAK1H11J111KPEAPEBGPEAHK3K33@Z`
- size: `219`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 **, int *, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400061e4`
- `0x1400083b0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::UpdateDistributionUnit2(
        CIEAdminBrokerObject *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int16 *a7,
        int a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        int a11,
        BYTE *a12,
        BYTE *a13,
        BYTE *a14,
        unsigned int a15,
        unsigned __int16 **a16,
        int *a17,
        unsigned int a18,
        unsigned __int16 **a19)
{
  CActiveXInstallBroker *v19; // rcx
  __int64 result; // rax

  v19 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v19 )
    return CActiveXInstallBroker::UpdateDistributionUnit2(
             v19,
             a2,
             a3,
             a4,
             a5,
             (BYTE *)a6,
             (BYTE *)a7,
             a8,
             a9,
             a10,
             a11,
             a12,
             a13,
             a14,
             a15,
             a16,
             a17,
             a18,
             a19);
  return result;
}

```

## disassembly

```asm
0x1400083b0  mov     r11, rsp
0x1400083b3  sub     rsp, 0B8h
0x1400083ba  mov     rcx, [rcx+10h]; this
0x1400083be  mov     eax, 80004005h
0x1400083c3  test    rcx, rcx
0x1400083c6  jz      loc_140008482
0x1400083cc  mov     rax, [rsp+0B8h+arg_90]
0x1400083d4  mov     [r11-28h], rax
0x1400083d8  mov     eax, [rsp+0B8h+arg_88]
0x1400083df  mov     [r11-30h], eax
0x1400083e3  mov     rax, [rsp+0B8h+arg_80]
0x1400083eb  mov     [r11-38h], rax
0x1400083ef  mov     rax, [rsp+0B8h+arg_78]
0x1400083f7  mov     [r11-40h], rax
0x1400083fb  mov     eax, [rsp+0B8h+arg_70]
0x140008402  mov     [rsp+0B8h+var_48], eax; unsigned int
0x140008406  mov     rax, [rsp+0B8h+arg_68]
0x14000840e  mov     [r11-50h], rax
0x140008412  mov     rax, [rsp+0B8h+arg_60]
0x14000841a  mov     [r11-58h], rax
0x14000841e  mov     rax, [rsp+0B8h+arg_58]
0x140008426  mov     [r11-60h], rax
0x14000842a  mov     eax, [rsp+0B8h+arg_50]
0x140008431  mov     [rsp+0B8h+var_68], eax; int
0x140008435  mov     rax, [rsp+0B8h+arg_48]
0x14000843d  mov     [r11-70h], rax
0x140008441  mov     rax, [rsp+0B8h+arg_40]
0x140008449  mov     [r11-78h], rax
0x14000844d  mov     eax, [rsp+0B8h+arg_38]
0x140008454  mov     [rsp+0B8h+var_80], eax; int
0x140008458  mov     rax, [rsp+0B8h+arg_30]
0x140008460  mov     [rsp+0B8h+var_88], rax; unsigned __int16 *
0x140008465  mov     rax, [rsp+0B8h+arg_28]
0x14000846d  mov     [rsp+0B8h+var_90], rax; unsigned int *
0x140008472  mov     eax, [rsp+0B8h+arg_20]
0x140008479  mov     [rsp+0B8h+var_98], eax; unsigned int
0x14000847d  call    ?UpdateDistributionUnit2@CActiveXInstallBroker@@QEAAJPEAGPEBG1KPEAK1H11J111KPEAPEBGPEAHK3K33@Z; CActiveXInstallBroker::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)
0x140008482  add     rsp, 0B8h
0x140008489  retn
```
