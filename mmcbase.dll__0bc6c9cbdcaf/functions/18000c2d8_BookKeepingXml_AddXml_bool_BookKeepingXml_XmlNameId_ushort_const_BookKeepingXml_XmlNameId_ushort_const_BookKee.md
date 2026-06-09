# BookKeepingXml::AddXml(bool,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *)

- ea: `0x18000c2d8`
- end: `0x18000c370`
- name: `?AddXml@BookKeepingXml@@AEAAJ_NW4_XmlNameId@1@PEBG1212@Z`
- size: `152`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000be80`
- `0x18000bf80`
- `0x18000c914`
- `0x18000caf0`
- `0x18000cb94`

## callees

- `0x18000bfcc`
- `0x18000c2d8`
- `0x18000c8f4`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddXml(
        BookKeepingXml *a1,
        char a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned __int16 *a8)
{
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r10d
  const unsigned __int16 *v12; // r11
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rdx

  v12 = (const unsigned __int16 *)BookKeepingXml::LookupName(a3);
  if ( v12 )
  {
    v13 = 0;
    if ( a5 == 50 || (v13 = (unsigned __int16 *)BookKeepingXml::LookupName(a5)) != 0 )
    {
      v14 = 0;
      if ( a7 == 50 )
        return (unsigned int)BookKeepingXml::AddXml(a1, a2, v12, v10, v13, a6, v14, a8);
      v14 = (unsigned __int16 *)BookKeepingXml::LookupName(a7);
      if ( v14 )
        return (unsigned int)BookKeepingXml::AddXml(a1, a2, v12, v10, v13, a6, v14, a8);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18000c2d8  mov     [rsp+arg_0], rbx
0x18000c2dd  push    rdi
0x18000c2de  sub     rsp, 40h
0x18000c2e2  mov     rdi, rcx
0x18000c2e5  mov     bl, dl
0x18000c2e7  mov     ecx, r8d
0x18000c2ea  mov     r10d, 80070057h
0x18000c2f0  call    ?LookupName@BookKeepingXml@@CAPEBGW4_XmlNameId@1@@Z; BookKeepingXml::LookupName(BookKeepingXml::_XmlNameId)
0x18000c2f5  mov     r11, rax
0x18000c2f8  test    rax, rax
0x18000c2fb  jz      short loc_18000C362
0x18000c2fd  mov     ecx, [rsp+48h+arg_20]
0x18000c301  xor     r8d, r8d
0x18000c304  cmp     ecx, 32h ; '2'
0x18000c307  jz      short loc_18000C316
0x18000c309  call    ?LookupName@BookKeepingXml@@CAPEBGW4_XmlNameId@1@@Z; BookKeepingXml::LookupName(BookKeepingXml::_XmlNameId)
0x18000c30e  mov     r8, rax
0x18000c311  test    rax, rax
0x18000c314  jz      short loc_18000C362
0x18000c316  mov     ecx, [rsp+48h+arg_30]
0x18000c31d  xor     edx, edx
0x18000c31f  cmp     ecx, 32h ; '2'
0x18000c322  jz      short loc_18000C331
0x18000c324  call    ?LookupName@BookKeepingXml@@CAPEBGW4_XmlNameId@1@@Z; BookKeepingXml::LookupName(BookKeepingXml::_XmlNameId)
0x18000c329  mov     rdx, rax
0x18000c32c  test    rax, rax
0x18000c32f  jz      short loc_18000C362
0x18000c331  mov     rax, [rsp+48h+arg_38]
0x18000c339  mov     rcx, rdi; this
0x18000c33c  mov     [rsp+48h+var_10], rax; unsigned __int16 *
0x18000c341  mov     rax, [rsp+48h+arg_28]
0x18000c346  mov     [rsp+48h+var_18], rdx; unsigned __int16 *
0x18000c34b  mov     dl, bl; bool
0x18000c34d  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18000c352  mov     [rsp+48h+var_28], r8; unsigned __int16 *
0x18000c357  mov     r8, r11; unsigned __int16 *
0x18000c35a  call    ?AddXml@BookKeepingXml@@AEAAJ_NPEBG11111@Z; BookKeepingXml::AddXml(bool,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000c35f  mov     r10d, eax
0x18000c362  mov     rbx, [rsp+48h+arg_0]
0x18000c367  mov     eax, r10d
0x18000c36a  add     rsp, 40h
0x18000c36e  pop     rdi
0x18000c36f  retn
```
