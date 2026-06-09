# LsapMakeLowBoxRpcSD

- ea: `0x140002d30`
- end: `0x14000308b`
- name: `LsapMakeLowBoxRpcSD`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140002c24`

## callees

- `0x1400020c0`
- `0x140002d30`

## import_xrefs

- `ntdll!RtlCreateAndSetSD` at `0x140002ffd`
- `ntdll!RtlCreateAndSetSD` at `0x140002ffd`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140002fd3`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140002fd3`
- `ntdll!RtlFreeSid` at `0x14000301a`
- `ntdll!RtlFreeSid` at `0x14000302a`
- `ntdll!RtlFreeSid` at `0x14000303a`
- `ntdll!RtlFreeSid` at `0x14000304a`
- `ntdll!RtlFreeSid` at `0x140003059`
- `ntdll!RtlFreeSid` at `0x140003068`
- `ntdll!RtlFreeSid` at `0x14000301a`
- `ntdll!RtlFreeSid` at `0x14000302a`
- `ntdll!RtlFreeSid` at `0x14000303a`
- `ntdll!RtlFreeSid` at `0x14000304a`
- `ntdll!RtlFreeSid` at `0x140003059`
- `ntdll!RtlFreeSid` at `0x140003068`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002e7d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002ebc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002efb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002f3d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002f7b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002fbb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002e7d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002ebc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002efb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002f3d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002f7b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140002fbb`

## string_xrefs

- `0x140002d78`: `lpacIdentityServices`

## pseudocode

```c
__int64 __fastcall LsapMakeLowBoxRpcSD(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS v2; // ebx
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v5; // [rsp+68h] [rbp-98h] BYREF
  PSID v6; // [rsp+70h] [rbp-90h] BYREF
  PSID v7; // [rsp+78h] [rbp-88h] BYREF
  PSID v8; // [rsp+80h] [rbp-80h] BYREF
  PSID v9; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v10; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v12[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v13; // [rsp+B0h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v16; // [rsp+C8h] [rbp-38h] BYREF
  __int16 AceData; // [rsp+D0h] [rbp-30h] BYREF
  char v18; // [rsp+D2h] [rbp-2Eh]
  int v19; // [rsp+D4h] [rbp-2Ch]
  PSID *p_Sid; // [rsp+D8h] [rbp-28h]
  __int16 v21; // [rsp+E0h] [rbp-20h]
  char v22; // [rsp+E2h] [rbp-1Eh]
  int v23; // [rsp+E4h] [rbp-1Ch]
  PSID *v24; // [rsp+E8h] [rbp-18h]
  __int16 v25; // [rsp+F0h] [rbp-10h]
  char v26; // [rsp+F2h] [rbp-Eh]
  unsigned int v27; // [rsp+F4h] [rbp-Ch]
  PSID *v28; // [rsp+F8h] [rbp-8h]
  __int16 v29; // [rsp+100h] [rbp+0h]
  char v30; // [rsp+102h] [rbp+2h]
  int v31; // [rsp+104h] [rbp+4h]
  PSID *v32; // [rsp+108h] [rbp+8h]
  __int16 v33; // [rsp+110h] [rbp+10h]
  char v34; // [rsp+112h] [rbp+12h]
  int v35; // [rsp+114h] [rbp+14h]
  PSID *v36; // [rsp+118h] [rbp+18h]
  __int16 v37; // [rsp+120h] [rbp+20h]
  char v38; // [rsp+122h] [rbp+22h]
  unsigned int v39; // [rsp+124h] [rbp+24h]
  PSID *v40; // [rsp+128h] [rbp+28h]
  __int16 v41; // [rsp+130h] [rbp+30h]
  char v42; // [rsp+132h] [rbp+32h]
  unsigned int v43; // [rsp+134h] [rbp+34h]
  _QWORD *v44; // [rsp+138h] [rbp+38h]
  _BYTE v45[48]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v46[48]; // [rsp+170h] [rbp+70h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  Sid = 0;
  v27 = 0x80000000;
  v39 = 0x80000000;
  v19 = -536870912;
  v12[1] = L"lpacIdentityServices";
  v23 = -536870912;
  p_Sid = &Sid;
  v31 = 0x10000000;
  v24 = &v5;
  v35 = 0x10000000;
  v28 = &v6;
  v43 = 0x80000000;
  v32 = &v7;
  v5 = 0;
  v36 = &v8;
  v40 = &v9;
  v44 = &v10;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v6 = 0;
  v10 = 0;
  NewDescriptor = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v13.Value = 0;
  *(_WORD *)&v13.Value[4] = 1280;
  *(_DWORD *)v15.Value = 0;
  *(_WORD *)&v15.Value[4] = 768;
  *(_DWORD *)v16.Value = 0;
  *(_WORD *)&v16.Value[4] = 3840;
  v12[0] = 2752552;
  AceData = 0;
  v18 = 0;
  v21 = 1;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  v38 = 0;
  v41 = 0;
  v42 = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v2 >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(&v13, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v5);
    if ( v2 >= 0 )
    {
      v2 = RtlAllocateAndInitializeSid(&v13, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, &v6);
      if ( v2 >= 0 )
      {
        v2 = RtlAllocateAndInitializeSid(&v13, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7);
        if ( v2 >= 0 )
        {
          v2 = RtlAllocateAndInitializeSid(&v15, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v8);
          if ( v2 >= 0 )
          {
            v2 = RtlAllocateAndInitializeSid(&v16, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v9);
            if ( v2 >= 0 )
            {
              v2 = RtlDeriveCapabilitySidsFromName(v12, v46, v45);
              if ( v2 >= 0 )
              {
                v10 = v45;
                v2 = RtlCreateAndSetSD(&AceData, 7u, 0, 0, &NewDescriptor);
                if ( v2 >= 0 )
                  *a1 = NewDescriptor;
              }
            }
          }
        }
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v5 )
    RtlFreeSid(v5);
  if ( v6 )
    RtlFreeSid(v6);
  if ( v7 )
    RtlFreeSid(v7);
  if ( v8 )
    RtlFreeSid(v8);
  if ( v9 )
    RtlFreeSid(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140002d30  push    rbp
0x140002d32  push    rbx
0x140002d33  push    rsi
0x140002d34  push    rdi
0x140002d35  lea     rbp, [rsp-0B8h]
0x140002d3d  sub     rsp, 1B8h
0x140002d44  mov     rax, cs:__security_cookie
0x140002d4b  xor     rax, rsp
0x140002d4e  mov     [rbp+0D0h+var_30], rax
0x140002d55  xor     esi, esi
0x140002d57  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 100h
0x140002d5d  mov     edx, 80000000h
0x140002d62  mov     [rsp+1D0h+var_170], rsi
0x140002d67  mov     rdi, rcx
0x140002d6a  mov     [rbp+0D0h+var_DC], edx
0x140002d6d  mov     ecx, 0E0000000h
0x140002d72  mov     [rbp+0D0h+var_AC], edx
0x140002d75  mov     [rbp+0D0h+var_FC], ecx
0x140002d78  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x140002d7f  mov     [rbp+0D0h+var_128], rax
0x140002d83  xor     r9d, r9d; SubAuthority1
0x140002d86  mov     [rbp+0D0h+var_EC], ecx
0x140002d89  lea     rax, [rsp+1D0h+var_170]
0x140002d8e  mov     [rbp+0D0h+var_F8], rax
0x140002d92  mov     ecx, 10000000h
0x140002d97  lea     rax, [rsp+1D0h+var_168]
0x140002d9c  mov     [rbp+0D0h+var_CC], ecx
0x140002d9f  mov     [rbp+0D0h+var_E8], rax
0x140002da3  xor     r8d, r8d; SubAuthority0
0x140002da6  lea     rax, [rsp+1D0h+var_160]
0x140002dab  mov     [rbp+0D0h+var_BC], ecx
0x140002dae  mov     [rbp+0D0h+var_D8], rax
0x140002db2  lea     rcx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x140002db6  lea     rax, [rsp+1D0h+var_158]
0x140002dbb  mov     [rbp+0D0h+var_9C], edx
0x140002dbe  mov     [rbp+0D0h+var_C8], rax
0x140002dc2  mov     dl, 1; SubAuthorityCount
0x140002dc4  lea     rax, [rbp+0D0h+var_150]
0x140002dc8  mov     [rsp+1D0h+var_168], rsi
0x140002dcd  mov     [rbp+0D0h+var_B8], rax
0x140002dd1  lea     rax, [rbp+0D0h+var_148]
0x140002dd5  mov     [rbp+0D0h+var_A8], rax
0x140002dd9  lea     rax, [rbp+0D0h+var_140]
0x140002ddd  mov     [rbp+0D0h+var_98], rax
0x140002de1  lea     rax, [rsp+1D0h+var_170]
0x140002de6  mov     [rsp+1D0h+Sid], rax; Sid
0x140002deb  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x140002def  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x140002df3  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x140002df7  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x140002dfb  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x140002dff  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x140002e03  mov     [rsp+1D0h+var_158], rsi
0x140002e08  mov     [rbp+0D0h+var_150], rsi
0x140002e0c  mov     [rbp+0D0h+var_148], rsi
0x140002e10  mov     [rsp+1D0h+var_160], rsi
0x140002e15  mov     [rbp+0D0h+var_140], rsi
0x140002e19  mov     [rbp+0D0h+NewDescriptor], rsi
0x140002e1d  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], esi
0x140002e20  mov     dword ptr [rbp+0D0h+var_120.Value], esi
0x140002e23  mov     word ptr [rbp+0D0h+var_120.Value+4], 500h
0x140002e29  mov     dword ptr [rbp+0D0h+var_110.Value], esi
0x140002e2c  mov     word ptr [rbp+0D0h+var_110.Value+4], 300h
0x140002e32  mov     dword ptr [rbp+0D0h+var_108.Value], esi
0x140002e35  mov     word ptr [rbp+0D0h+var_108.Value+4], 0F00h
0x140002e3b  mov     [rbp+0D0h+var_130], 2A0028h
0x140002e43  mov     [rbp+0D0h+AceData], si
0x140002e47  mov     [rbp+0D0h+var_FE], sil
0x140002e4b  mov     [rbp+0D0h+var_F0], 1
0x140002e51  mov     [rbp+0D0h+var_EE], sil
0x140002e55  mov     [rbp+0D0h+var_E0], si
0x140002e59  mov     [rbp+0D0h+var_DE], sil
0x140002e5d  mov     [rbp+0D0h+var_D0], si
0x140002e61  mov     [rbp+0D0h+var_CE], sil
0x140002e65  mov     [rbp+0D0h+var_C0], si
0x140002e69  mov     [rbp+0D0h+var_BE], sil
0x140002e6d  mov     [rbp+0D0h+var_B0], si
0x140002e71  mov     [rbp+0D0h+var_AE], sil
0x140002e75  mov     [rbp+0D0h+var_A0], si
0x140002e79  mov     [rbp+0D0h+var_9E], sil
0x140002e7d  call    cs:__imp_RtlAllocateAndInitializeSid
0x140002e83  mov     ebx, eax
0x140002e85  test    eax, eax
0x140002e87  js      loc_140003010
0x140002e8d  lea     rax, [rsp+1D0h+var_168]
0x140002e92  xor     r9d, r9d; SubAuthority1
0x140002e95  mov     [rsp+1D0h+Sid], rax; Sid
0x140002e9a  lea     r8d, [rsi+0Ch]; SubAuthority0
0x140002e9e  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x140002ea2  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x140002ea6  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x140002eaa  mov     dl, 1; SubAuthorityCount
0x140002eac  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x140002eb0  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x140002eb4  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x140002eb8  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x140002ebc  call    cs:__imp_RtlAllocateAndInitializeSid
0x140002ec2  mov     ebx, eax
0x140002ec4  test    eax, eax
0x140002ec6  js      loc_140003010
0x140002ecc  lea     rax, [rsp+1D0h+var_160]
0x140002ed1  xor     r9d, r9d; SubAuthority1
0x140002ed4  mov     [rsp+1D0h+Sid], rax; Sid
0x140002ed9  lea     r8d, [rsi+7]; SubAuthority0
0x140002edd  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x140002ee1  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x140002ee5  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x140002ee9  mov     dl, 1; SubAuthorityCount
0x140002eeb  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x140002eef  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x140002ef3  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x140002ef7  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x140002efb  call    cs:__imp_RtlAllocateAndInitializeSid
0x140002f01  mov     ebx, eax
0x140002f03  test    eax, eax
0x140002f05  js      loc_140003010
0x140002f0b  lea     rax, [rsp+1D0h+var_158]
0x140002f10  mov     r9d, 220h; SubAuthority1
0x140002f16  mov     [rsp+1D0h+Sid], rax; Sid
0x140002f1b  lea     r8d, [rsi+20h]; SubAuthority0
0x140002f1f  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x140002f23  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x140002f27  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x140002f2b  mov     dl, 2; SubAuthorityCount
0x140002f2d  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x140002f31  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x140002f35  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x140002f39  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x140002f3d  call    cs:__imp_RtlAllocateAndInitializeSid
0x140002f43  mov     ebx, eax
0x140002f45  test    eax, eax
0x140002f47  js      loc_140003010
0x140002f4d  lea     rax, [rbp+0D0h+var_150]
0x140002f51  xor     r9d, r9d; SubAuthority1
0x140002f54  mov     [rsp+1D0h+Sid], rax; Sid
0x140002f59  lea     r8d, [rsi+4]; SubAuthority0
0x140002f5d  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x140002f61  lea     rcx, [rbp+0D0h+var_110]; IdentifierAuthority
0x140002f65  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x140002f69  mov     dl, 1; SubAuthorityCount
0x140002f6b  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x140002f6f  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x140002f73  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x140002f77  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x140002f7b  call    cs:__imp_RtlAllocateAndInitializeSid
0x140002f81  mov     ebx, eax
0x140002f83  test    eax, eax
0x140002f85  js      loc_140003010
0x140002f8b  lea     rax, [rbp+0D0h+var_148]
0x140002f8f  mov     [rsp+1D0h+Sid], rax; Sid
0x140002f94  lea     r8d, [rsi+2]; SubAuthority0
0x140002f98  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x140002f9c  lea     r9d, [rsi+1]; SubAuthority1
0x140002fa0  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x140002fa4  lea     rcx, [rbp+0D0h+var_108]; IdentifierAuthority
0x140002fa8  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x140002fac  mov     dl, r8b; SubAuthorityCount
0x140002faf  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x140002fb3  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x140002fb7  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x140002fbb  call    cs:__imp_RtlAllocateAndInitializeSid
0x140002fc1  mov     ebx, eax
0x140002fc3  test    eax, eax
0x140002fc5  js      short loc_140003010
0x140002fc7  lea     r8, [rbp+0D0h+var_90]
0x140002fcb  lea     rdx, [rbp+0D0h+var_60]
0x140002fcf  lea     rcx, [rbp+0D0h+var_130]
0x140002fd3  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x140002fd9  mov     ebx, eax
0x140002fdb  test    eax, eax
0x140002fdd  js      short loc_140003010
0x140002fdf  lea     rax, [rbp+0D0h+var_90]
0x140002fe3  xor     r9d, r9d; GroupSid
0x140002fe6  mov     [rbp+0D0h+var_140], rax
0x140002fea  lea     edx, [rsi+7]; AceCount
0x140002fed  lea     rax, [rbp+0D0h+NewDescriptor]
0x140002ff1  xor     r8d, r8d; OwnerSid
0x140002ff4  lea     rcx, [rbp+0D0h+AceData]; AceData
0x140002ff8  mov     qword ptr [rsp+1D0h+SubAuthority2], rax; NewDescriptor
0x140002ffd  call    cs:__imp_RtlCreateAndSetSD
0x140003003  mov     ebx, eax
0x140003005  test    eax, eax
0x140003007  js      short loc_140003010
0x140003009  mov     rax, [rbp+0D0h+NewDescriptor]
0x14000300d  mov     [rdi], rax
0x140003010  mov     rcx, [rsp+1D0h+var_170]; Sid
0x140003015  test    rcx, rcx
0x140003018  jz      short loc_140003020
0x14000301a  call    cs:__imp_RtlFreeSid
0x140003020  mov     rcx, [rsp+1D0h+var_168]; Sid
0x140003025  test    rcx, rcx
0x140003028  jz      short loc_140003030
0x14000302a  call    cs:__imp_RtlFreeSid
0x140003030  mov     rcx, [rsp+1D0h+var_160]; Sid
0x140003035  test    rcx, rcx
0x140003038  jz      short loc_140003040
0x14000303a  call    cs:__imp_RtlFreeSid
0x140003040  mov     rcx, [rsp+1D0h+var_158]; Sid
0x140003045  test    rcx, rcx
0x140003048  jz      short loc_140003050
0x14000304a  call    cs:__imp_RtlFreeSid
0x140003050  mov     rcx, [rbp+0D0h+var_150]; Sid
0x140003054  test    rcx, rcx
0x140003057  jz      short loc_14000305F
0x140003059  call    cs:__imp_RtlFreeSid
0x14000305f  mov     rcx, [rbp+0D0h+var_148]; Sid
0x140003063  test    rcx, rcx
0x140003066  jz      short loc_14000306E
0x140003068  call    cs:__imp_RtlFreeSid
0x14000306e  mov     eax, ebx
0x140003070  mov     rcx, [rbp+0D0h+var_30]
0x140003077  xor     rcx, rsp; StackCookie
0x14000307a  call    __security_check_cookie
0x14000307f  add     rsp, 1B8h
0x140003086  pop     rdi
0x140003087  pop     rsi
0x140003088  pop     rbx
0x140003089  pop     rbp
0x14000308a  retn
```
