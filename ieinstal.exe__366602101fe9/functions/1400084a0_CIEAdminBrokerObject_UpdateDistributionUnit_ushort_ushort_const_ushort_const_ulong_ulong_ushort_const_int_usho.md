# CIEAdminBrokerObject::UpdateDistributionUnit(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)

- ea: `0x1400084a0`
- end: `0x140008577`
- name: `?UpdateDistributionUnit@CIEAdminBrokerObject@@UEAAJPEAGPEBG1KPEAK1H11J111KPEAPEBGK3K33@Z`
- size: `215`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400061e4`
- `0x1400084a0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::UpdateDistributionUnit(
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
        unsigned int a17,
        unsigned __int16 **a18)
{
  CActiveXInstallBroker *v18; // rcx
  __int64 result; // rax

  v18 = (CActiveXInstallBroker *)*((_QWORD *)this + 2);
  result = 2147500037LL;
  if ( v18 )
    return CActiveXInstallBroker::UpdateDistributionUnit2(
             v18,
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
             0,
             a17,
             a18);
  return result;
}

```

## disassembly

```asm
0x1400084a0  mov     r11, rsp
0x1400084a3  sub     rsp, 0B8h
0x1400084aa  mov     rcx, [rcx+10h]; this
0x1400084ae  mov     eax, 80004005h
0x1400084b3  test    rcx, rcx
0x1400084b6  jz      loc_14000856E
0x1400084bc  mov     rax, [rsp+0B8h+arg_88]
0x1400084c4  mov     [r11-28h], rax
0x1400084c8  mov     eax, [rsp+0B8h+arg_80]
0x1400084cf  mov     [r11-30h], eax
0x1400084d3  mov     rax, [rsp+0B8h+arg_78]
0x1400084db  mov     qword ptr [r11-38h], 0
0x1400084e3  mov     [r11-40h], rax
0x1400084e7  mov     eax, [rsp+0B8h+arg_70]
0x1400084ee  mov     [rsp+0B8h+var_48], eax; unsigned int
0x1400084f2  mov     rax, [rsp+0B8h+arg_68]
0x1400084fa  mov     [r11-50h], rax
0x1400084fe  mov     rax, [rsp+0B8h+arg_60]
0x140008506  mov     [r11-58h], rax
0x14000850a  mov     rax, [rsp+0B8h+arg_58]
0x140008512  mov     [r11-60h], rax
0x140008516  mov     eax, [rsp+0B8h+arg_50]
0x14000851d  mov     [rsp+0B8h+var_68], eax; int
0x140008521  mov     rax, [rsp+0B8h+arg_48]
0x140008529  mov     [r11-70h], rax
0x14000852d  mov     rax, [rsp+0B8h+arg_40]
0x140008535  mov     [r11-78h], rax
0x140008539  mov     eax, [rsp+0B8h+arg_38]
0x140008540  mov     [rsp+0B8h+var_80], eax; int
0x140008544  mov     rax, [rsp+0B8h+arg_30]
0x14000854c  mov     [rsp+0B8h+var_88], rax; unsigned __int16 *
0x140008551  mov     rax, [rsp+0B8h+arg_28]
0x140008559  mov     [rsp+0B8h+var_90], rax; unsigned int *
0x14000855e  mov     eax, [rsp+0B8h+arg_20]
0x140008565  mov     [rsp+0B8h+var_98], eax; unsigned int
0x140008569  call    ?UpdateDistributionUnit2@CActiveXInstallBroker@@QEAAJPEAGPEBG1KPEAK1H11J111KPEAPEBGPEAHK3K33@Z; CActiveXInstallBroker::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)
0x14000856e  add     rsp, 0B8h
0x140008575  retn
```
