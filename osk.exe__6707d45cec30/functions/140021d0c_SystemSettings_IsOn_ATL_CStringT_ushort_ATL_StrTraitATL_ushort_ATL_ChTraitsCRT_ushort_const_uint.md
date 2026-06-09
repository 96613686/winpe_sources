# SystemSettings::IsOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint)

- ea: `0x140021d0c`
- end: `0x140021dab`
- name: `?IsOn@SystemSettings@@SAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140021724`

## callees

- `0x140021d0c`
- `0x140025d70`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x140021d84`
- `USER32!SystemParametersInfoW` at `0x140021d84`

## pseudocode

```c
__int64 __fastcall SystemSettings::IsOn(_QWORD *a1, unsigned int a2)
{
  __int64 v2; // r10
  unsigned __int16 *v3; // rax
  __int64 v4; // r8
  int v5; // edx
  int v6; // ecx
  UINT v7; // edx
  UINT v8; // ecx
  _OWORD pvParam[4]; // [rsp+20h] [rbp-58h] BYREF

  v2 = 32LL * a2;
  v3 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v2);
  v4 = *a1 - (_QWORD)v3;
  do
  {
    v5 = *(unsigned __int16 *)((char *)v3 + v4);
    v6 = *v3 - v5;
    if ( v6 )
      break;
    ++v3;
  }
  while ( v5 );
  if ( !v6
    && *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 16) == 2
    && (v7 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 20),
        v8 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 8),
        memset(pvParam, 0, 60),
        LODWORD(pvParam[0]) = v7,
        SystemParametersInfoW(v8, v7, pvParam, 0)) )
  {
    return BYTE4(pvParam[0]) & 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140021d0c  sub     rsp, 78h
0x140021d10  mov     rax, cs:__security_cookie
0x140021d17  xor     rax, rsp
0x140021d1a  mov     [rsp+78h+var_18], rax
0x140021d1f  mov     r8, [rcx]
0x140021d22  lea     r11, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x140021d29  mov     r10d, edx
0x140021d2c  shl     r10, 5
0x140021d30  mov     rax, [r10+r11]
0x140021d34  sub     r8, rax
0x140021d37  movzx   ecx, word ptr [rax]
0x140021d3a  movzx   edx, word ptr [rax+r8]
0x140021d3f  sub     ecx, edx
0x140021d41  jnz     short loc_140021D4B
0x140021d43  add     rax, 2
0x140021d47  test    edx, edx
0x140021d49  jnz     short loc_140021D37
0x140021d4b  test    ecx, ecx
0x140021d4d  jnz     short loc_140021D97
0x140021d4f  cmp     dword ptr [r10+r11+10h], 2
0x140021d55  jnz     short loc_140021D97
0x140021d57  mov     edx, [r10+r11+14h]; uiParam
0x140021d5c  lea     r8, [rsp+78h+pvParam]; pvParam
0x140021d61  mov     ecx, [r10+r11+8]; uiAction
0x140021d66  xorps   xmm0, xmm0
0x140021d69  movups  [rsp+78h+pvParam], xmm0
0x140021d6e  xor     r9d, r9d; fWinIni
0x140021d71  mov     dword ptr [rsp+78h+pvParam], edx
0x140021d75  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x140021d7a  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm0
0x140021d7f  movups  [rsp+78h+var_48], xmm0
0x140021d84  call    cs:__imp_SystemParametersInfoW
0x140021d8a  test    eax, eax
0x140021d8c  jz      short loc_140021D97
0x140021d8e  mov     eax, dword ptr [rsp+78h+pvParam+4]
0x140021d92  and     eax, 1
0x140021d95  jmp     short loc_140021D99
0x140021d97  xor     eax, eax
0x140021d99  mov     rcx, [rsp+78h+var_18]
0x140021d9e  xor     rcx, rsp; StackCookie
0x140021da1  call    __security_check_cookie
0x140021da6  add     rsp, 78h
0x140021daa  retn
```
