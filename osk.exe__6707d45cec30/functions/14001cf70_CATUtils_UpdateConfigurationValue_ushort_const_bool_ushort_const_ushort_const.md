# CATUtils::_UpdateConfigurationValue(ushort const *,bool,ushort const *,ushort const *)

- ea: `0x14001cf70`
- end: `0x14001d095`
- name: `?_UpdateConfigurationValue@CATUtils@@CAXPEBG_N00@Z`
- size: `293`
- prototype: `static void(const unsigned __int16 *, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x14001b51c`

## callees

- `0x140002de3`
- `0x1400045f4`
- `0x140005c90`
- `0x140009524`
- `0x1400170d8`
- `0x14001c324`
- `0x14001c58c`
- `0x14001c8a8`
- `0x14001cb58`
- `0x14001cf70`
- `0x140025d70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CATUtils::_UpdateConfigurationValue(
        const unsigned __int16 *a1,
        char a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HKEY v6; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v7; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v8[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v9[1024]; // [rsp+60h] [rbp-A0h] BYREF

  memset(v8, 0, sizeof(v8));
  if ( !(unsigned int)ATL::CRegKey::Create((ATL::CRegKey *)v8, HKEY_LOCAL_MACHINE, a3, a4, 0, 0x2001Fu, v6, 0) )
  {
    memset_0(v9, 0, sizeof(v9));
    LODWORD(v7) = 1024;
    if ( !(unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v8, a4, v9, (unsigned int *)&v7) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v7,
        v9);
      if ( a2 )
        CATUtils::AddAppNameToConfig(&v7);
      else
        CATUtils::DeleteAppNameFromConfig(&v7);
      ATL::CRegKey::SetStringValue(v8, a4, (const BYTE *)v7);
      ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v8);
}

```

## disassembly

```asm
0x14001cf70  mov     [rsp-8+arg_0], rbx
0x14001cf75  mov     [rsp-8+arg_8], rdi
0x14001cf7a  push    rbp
0x14001cf7b  lea     rbp, [rsp-770h]
0x14001cf83  sub     rsp, 870h
0x14001cf8a  mov     rax, cs:__security_cookie
0x14001cf91  xor     rax, rsp
0x14001cf94  mov     [rbp+770h+var_10], rax
0x14001cf9b  mov     rbx, r9
0x14001cf9e  mov     dil, dl
0x14001cfa1  mov     [rsp+870h+var_828], 0
0x14001cfaa  mov     [rsp+870h+var_820], 0
0x14001cfb3  mov     [rsp+870h+var_818], 0
0x14001cfbc  mov     [rsp+870h+var_838], 0; unsigned int *
0x14001cfc5  mov     [rsp+870h+var_848], 2001Fh; REGSAM
0x14001cfcd  mov     [rsp+870h+var_850], 0; DWORD
0x14001cfd5  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001cfdc  lea     rcx, [rsp+870h+var_828]; this
0x14001cfe1  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14001cfe6  test    eax, eax
0x14001cfe8  jnz     short loc_14001D067
0x14001cfea  xor     edx, edx; Val
0x14001cfec  mov     r8d, 800h; Size
0x14001cff2  lea     rcx, [rsp+870h+var_810]; void *
0x14001cff7  call    memset_0
0x14001cffc  mov     dword ptr [rsp+870h+var_830], 400h
0x14001d004  lea     r9, [rsp+870h+var_830]; unsigned int *
0x14001d009  lea     r8, [rsp+870h+var_810]; unsigned __int16 *
0x14001d00e  mov     rdx, rbx; unsigned __int16 *
0x14001d011  lea     rcx, [rsp+870h+var_828]; this
0x14001d016  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001d01b  test    eax, eax
0x14001d01d  jnz     short loc_14001D067
0x14001d01f  lea     rdx, [rsp+870h+var_810]
0x14001d024  lea     rcx, [rsp+870h+var_830]
0x14001d029  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001d02e  nop
0x14001d02f  lea     rcx, [rsp+870h+var_830]
0x14001d034  test    dil, dil
0x14001d037  jz      short loc_14001D040
0x14001d039  call    ?AddAppNameToConfig@CATUtils@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CATUtils::AddAppNameToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x14001d03e  jmp     short loc_14001D045
0x14001d040  call    ?DeleteAppNameFromConfig@CATUtils@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CATUtils::DeleteAppNameFromConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x14001d045  mov     r8, [rsp+870h+var_830]; unsigned __int16 *
0x14001d04a  mov     rdx, rbx; unsigned __int16 *
0x14001d04d  lea     rcx, [rsp+870h+var_828]; this
0x14001d052  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x14001d057  nop
0x14001d058  mov     rcx, [rsp+870h+var_830]
0x14001d05d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001d061  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001d066  nop
0x14001d067  lea     rcx, [rsp+870h+var_828]; this
0x14001d06c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001d071  mov     rcx, [rbp+770h+var_10]
0x14001d078  xor     rcx, rsp; StackCookie
0x14001d07b  call    __security_check_cookie
0x14001d080  lea     r11, [rsp+870h+var_s0]
0x14001d088  mov     rbx, [r11+10h]
0x14001d08c  mov     rdi, [r11+18h]
0x14001d090  mov     rsp, r11
0x14001d093  pop     rbp
0x14001d094  retn
```
