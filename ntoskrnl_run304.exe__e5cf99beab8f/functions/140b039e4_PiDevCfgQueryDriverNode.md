# PiDevCfgQueryDriverNode

- ea: `0x140b039e4`
- end: `0x140b04355`
- name: `PiDevCfgQueryDriverNode`
- size: `2417`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140a7e6e8`

## callees

- `0x1404c4c90`
- `0x1404d94cc`
- `0x1405de5e8`
- `0x1405de644`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406f4880`
- `0x14075bdd0`
- `0x140769a10`
- `0x1408ccf80`
- `0x1408eeff0`
- `0x14096c1c0`
- `0x1409737d4`
- `0x1409b3930`
- `0x140a7e528`
- `0x140a8165c`
- `0x140a81728`
- `0x140ac2340`
- `0x140b039e4`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x140b040f3`: `Configuration`
- `0x140b04263`: `ConfigFlags`
- `0x140b04067`: `Descriptors`

## pseudocode

```c
__int64 __fastcall PiDevCfgQueryDriverNode(
        PCWSTR SourceString,
        PCWSTR a2,
        int a3,
        int a4,
        char a5,
        _DWORD *a6,
        __int64 *a7)
{
  unsigned int v8; // r12d
  int DriverPackageId; // ebx
  int v12; // ecx
  wchar_t *Buffer; // rbx
  __int64 v14; // rax
  __int64 Pool2; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  PVOID *v18; // rsi
  int v19; // ecx
  int v20; // ecx
  char v21; // al
  int v22; // eax
  __int64 v23; // r9
  char v24; // al
  __int64 v25; // r8
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  int v31; // ecx
  char v32; // al
  ULONG v33; // [rsp+20h] [rbp-E0h]
  char v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35; // [rsp+41h] [rbp-BFh] BYREF
  char v36; // [rsp+42h] [rbp-BEh] BYREF
  char v37; // [rsp+43h] [rbp-BDh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE v41; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v43; // [rsp+70h] [rbp-90h] BYREF
  __int128 v44; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v47; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v49; // [rsp+B0h] [rbp-50h]
  ULONG v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v51; // [rsp+C8h] [rbp-38h]
  char *v52; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+E0h] [rbp-20h]
  __int64 *v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+F0h] [rbp-10h]
  UNICODE_STRING *v57; // [rsp+F8h] [rbp-8h]
  int v58; // [rsp+100h] [rbp+0h]
  int v59; // [rsp+104h] [rbp+4h]
  int v60; // [rsp+108h] [rbp+8h]
  __int64 *v61; // [rsp+110h] [rbp+10h]
  int v62; // [rsp+118h] [rbp+18h]
  __int64 *v63; // [rsp+120h] [rbp+20h]
  int v64; // [rsp+128h] [rbp+28h]
  int v65; // [rsp+130h] [rbp+30h]
  __int64 *v66; // [rsp+138h] [rbp+38h]
  int v67; // [rsp+140h] [rbp+40h]
  __int64 v68; // [rsp+148h] [rbp+48h]
  int v69; // [rsp+150h] [rbp+50h]
  int v70; // [rsp+158h] [rbp+58h]
  __int64 *v71; // [rsp+160h] [rbp+60h]
  int v72; // [rsp+168h] [rbp+68h]
  __int64 v73; // [rsp+170h] [rbp+70h]
  unsigned int v74; // [rsp+178h] [rbp+78h]
  int v75; // [rsp+17Ch] [rbp+7Ch]
  int v76; // [rsp+180h] [rbp+80h]
  int v77[2]; // [rsp+190h] [rbp+90h] BYREF
  int v78; // [rsp+198h] [rbp+98h]
  const wchar_t *v79; // [rsp+1A0h] [rbp+A0h]
  __int64 v80; // [rsp+1A8h] [rbp+A8h]
  int v81; // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v82)(int, int, int, int, int, __int64); // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v83; // [rsp+1D8h] [rbp+D8h]
  __int64 v84; // [rsp+1E0h] [rbp+E0h]
  int v85; // [rsp+208h] [rbp+108h]
  const wchar_t *v86; // [rsp+210h] [rbp+110h]
  __int64 v87; // [rsp+218h] [rbp+118h]
  int v88; // [rsp+220h] [rbp+120h]

  v49 = a7;
  *(_QWORD *)&UnicodeString.Length = 0;
  v8 = -1;
  UnicodeString.Buffer = 0;
  Handle = 0;
  v37 = 0;
  *(_QWORD *)&v48.Length = 0;
  v48.Buffer = 0;
  v35 = 0;
  v40 = -1;
  v46 = -1;
  v34 = 0;
  v36 = 0;
  v44 = 0;
  v47 = 0;
  v43 = 0;
  v41 = 0;
  v45 = a3;
  v39 = -16777216;
  DriverPackageId = PiDevCfgGetDriverPackageId(SourceString, &UnicodeString);
  if ( DriverPackageId >= 0 )
  {
    DriverPackageId = PnpOpenObjectRegKey(PiPnpRtlCtx, UnicodeString.Buffer, 8, 131097, 0, (__int64)&Handle);
    if ( DriverPackageId >= 0 )
    {
      memset_0(v50, 0, 0xC8u);
      *(_QWORD *)v50 = DEVPKEY_DriverPackage_Invalidated;
      v52 = &v37;
      v55 = DEVPKEY_DriverPackage_TargetComputerIds;
      v57 = &v48;
      v51 = 17;
      v53 = 1;
      v56 = 8210;
      v59 = 6;
      DriverPackageId = PiDevCfgQueryObjectProperties(v12, UnicodeString.Buffer, 8, (_DWORD)Handle, (__int64)v50, 2);
      if ( DriverPackageId >= 0 )
      {
        if ( v54 >= 0 && v37 == -1 )
        {
          DriverPackageId = -1073741738;
          goto LABEL_29;
        }
        Buffer = 0;
        if ( v60 >= 0 && v48.Buffer && v48.Length > 2u )
        {
          Buffer = v48.Buffer;
          if ( !*v48.Buffer )
            goto LABEL_16;
          do
          {
            if ( (unsigned __int8)PipCheckComputerSupported(Buffer) )
              break;
            v14 = -1;
            do
              ++v14;
            while ( Buffer[v14] );
            Buffer += v14 + 1;
          }
          while ( *Buffer );
          if ( !*Buffer )
            goto LABEL_16;
        }
        if ( (a5 & 8) != 0 && !Buffer )
        {
LABEL_16:
          DriverPackageId = -1073740764;
          goto LABEL_29;
        }
        Pool2 = ExAllocatePool2(256, 456, 1667526736);
        if ( !Pool2 )
        {
          DriverPackageId = -1073741670;
          goto LABEL_29;
        }
        if ( (Feature_KernelPnP_LogBlockedDrivers__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_KernelPnP_LogBlockedDrivers__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_KernelPnP_LogBlockedDrivers__private_IsEnabledDeviceUsageNoInline();
        if ( !IsEnabledDeviceUsageNoInline )
        {
          *(_QWORD *)(Pool2 + 232) = Pool2 + 224;
          *(_QWORD *)(Pool2 + 224) = Pool2 + 224;
        }
        *(_QWORD *)(Pool2 + 216) = Pool2 + 208;
        *(_QWORD *)(Pool2 + 208) = Pool2 + 208;
        *(_QWORD *)(Pool2 + 392) = Pool2 + 384;
        *(_QWORD *)(Pool2 + 384) = Pool2 + 384;
        if ( RtlCreateUnicodeString((PUNICODE_STRING)(Pool2 + 40), SourceString)
          && (unsigned __int8)PnpDuplicateUnicodeString(Pool2 + 56, &UnicodeString)
          && RtlCreateUnicodeString((PUNICODE_STRING)(Pool2 + 72), a2)
          && (!Buffer || RtlCreateUnicodeString((PUNICODE_STRING)(Pool2 + 128), Buffer)) )
        {
          memset_0(v50, 0, 0xC8u);
          *(_QWORD *)v50 = DEVPKEY_DriverPackage_DriverDate;
          v51 = 16;
          v52 = (char *)(Pool2 + 112);
          v18 = (PVOID *)(Pool2 + 144);
          v56 = 9;
          v55 = DEVPKEY_DriverPackage_DriverVersion;
          v53 = 8;
          v57 = (UNICODE_STRING *)(Pool2 + 120);
          v58 = 8;
          v61 = (__int64 *)&DEVPKEY_DriverPackage_SignerScore;
          v63 = (__int64 *)&v39;
          v66 = DEVPKEY_DriverPackage_ExtensionId;
          v71 = DEVPKEY_DriverPackage_ExtensionContractIds;
          v62 = 7;
          v64 = 4;
          v67 = 13;
          v68 = Pool2 + 188;
          v69 = 16;
          v72 = 4109;
          v73 = Pool2 + 144;
          v75 = 2;
          DriverPackageId = PiDevCfgQueryObjectProperties(16, UnicodeString.Buffer, 8, (_DWORD)Handle, (__int64)v50, 5);
          if ( DriverPackageId >= 0 )
          {
            if ( v54 < 0 )
              *(_QWORD *)(Pool2 + 112) = 0;
            if ( v60 < 0 )
              *(_QWORD *)(Pool2 + 120) = 0;
            if ( v65 < 0 )
              v39 = -16777216;
            if ( v70 < 0 )
              *(_OWORD *)(Pool2 + 188) = 0;
            if ( v76 >= 0 )
            {
              if ( (v74 & 0xF) != 0 )
              {
                ExFreePoolWithTag(*v18, 0);
                *v18 = 0;
              }
              else
              {
                *(_DWORD *)(Pool2 + 152) = v74 >> 4;
              }
            }
            else
            {
              *v18 = 0;
            }
            if ( (a5 & 4) != 0 )
              v19 = -1;
            else
              v19 = (unsigned __int16)v45 | a4 & 0xFF0000 | v39 & ((a5 & 1) != 0 ? -268435456 : -16777216);
            *(_DWORD *)(Pool2 + 108) = v19;
            if ( (a5 & 2) != 0 )
            {
              memset_0(v50, 0, 0xC8u);
              *(_QWORD *)v50 = DEVPKEY_DriverPackage_F6;
              v52 = &v34;
              v51 = 17;
              v53 = 1;
              DriverPackageId = PiDevCfgQueryObjectProperties(
                                  v20,
                                  UnicodeString.Buffer,
                                  8,
                                  (_DWORD)Handle,
                                  (__int64)v50,
                                  1);
              if ( DriverPackageId < 0 )
                goto LABEL_28;
              if ( v54 >= 0 )
              {
                v21 = v34;
              }
              else
              {
                v21 = 0;
                v34 = 0;
              }
              if ( v21 == -1 )
                *(_DWORD *)(Pool2 + 184) |= 2u;
            }
            if ( (Feature_KernelPnP_CheckDriverIntegrity__private_featureState & 0x10) != 0 )
              v22 = Feature_KernelPnP_CheckDriverIntegrity__private_featureState & 1;
            else
              v22 = Feature_KernelPnP_CheckDriverIntegrity__private_IsEnabledDeviceUsageNoInline();
            if ( v22 && a6 && (*a6 & 2) != 0 )
            {
              memset_0(v50, 0, 0xC8u);
              *(_QWORD *)v50 = &DEVPKEY_DriverPackage_Inbox;
              v52 = &v35;
              v55 = DEVPKEY_DriverPackage_CatalogAttributes;
              v57 = (UNICODE_STRING *)&v40;
              v61 = DEVPKEY_DriverPackage_CertificationVersion;
              v63 = &v46;
              v51 = 17;
              v53 = 1;
              v56 = 7;
              v58 = 4;
              v62 = 9;
              v64 = 8;
              DriverPackageId = PiDevCfgQueryObjectProperties(
                                  8,
                                  UnicodeString.Buffer,
                                  8,
                                  (_DWORD)Handle,
                                  (__int64)v50,
                                  3);
              if ( DriverPackageId < 0 )
                goto LABEL_28;
              if ( v54 >= 0 )
              {
                v24 = v35;
              }
              else
              {
                v24 = 0;
                v35 = 0;
              }
              if ( v60 >= 0 )
                v8 = v40;
              else
                v40 = -1;
              if ( v65 >= 0 )
              {
                v25 = v46;
              }
              else
              {
                v25 = -1;
                v46 = -1;
              }
              LOBYTE(v23) = v24 == -1;
              v26 = PiDevCfgEnforceDriverPolicy(a6, v8, v25, v23);
              if ( v26 < 0 )
              {
                *(_DWORD *)(Pool2 + 184) |= 0x200u;
                *(_DWORD *)(Pool2 + 448) = v26;
              }
            }
            LODWORD(v44) = 1572886;
            *((_QWORD *)&v44 + 1) = L"Descriptors";
            v27 = IopOpenRegistryKeyEx(&v47, Handle, &v44, 131097);
            DriverPackageId = v27;
            if ( v27 == -1073741772 )
              goto LABEL_87;
            if ( v27 < 0 )
              goto LABEL_28;
            v28 = IopOpenRegistryKeyEx(&v43, v47, Pool2 + 72, 131097);
            DriverPackageId = v28;
            if ( v28 == -1073741772 )
            {
LABEL_87:
              DriverPackageId = 0;
            }
            else
            {
              if ( v28 < 0 )
                goto LABEL_28;
              memset_0(v77, 0, 0xE0u);
              v79 = L"Configuration";
              v81 = 0x1000000;
              v80 = Pool2 + 88;
              v78 = 288;
              DriverPackageId = RtlpQueryRegistryValues(-1073741824, (int)v43, (int)v77, 0, v33, 1);
              if ( DriverPackageId < 0 )
                goto LABEL_28;
              if ( !*(_WORD *)(Pool2 + 88) && *(_QWORD *)(Pool2 + 96) )
                RtlFreeAnsiString((PUNICODE_STRING)(Pool2 + 88));
            }
            v29 = *(_QWORD *)(Pool2 + 96);
            if ( v29 )
            {
              v30 = PiDevCfgOpenDriverConfiguration(Handle, v29, &v41);
              DriverPackageId = v30;
              if ( v30 == -1073741772 )
              {
                DriverPackageId = 0;
              }
              else
              {
                if ( v30 < 0 )
                  goto LABEL_28;
                memset_0(v77, 0, 0xE0u);
                v88 = 117440512;
                *(_QWORD *)v77 = PiDevCfgQueryDriverVersionValueCallback;
                v79 = L"DriverDate";
                v82 = PiDevCfgQueryDriverVersionValueCallback;
                v80 = Pool2 + 112;
                v87 = Pool2 + 160;
                v83 = L"DriverVersion";
                v85 = 304;
                v84 = Pool2 + 120;
                v86 = L"ExcludeIds";
                DriverPackageId = RtlpQueryRegistryValues(-1073741824, (int)v41, (int)v77, 0, v33, 1);
                if ( DriverPackageId < 0 )
                  goto LABEL_28;
                if ( *(_WORD *)(Pool2 + 160) <= 2u && *(_QWORD *)(Pool2 + 168) )
                  RtlFreeAnsiString((PUNICODE_STRING)(Pool2 + 160));
              }
            }
            if ( !PnpBootMode )
              goto LABEL_112;
            LODWORD(v44) = 1572886;
            *((_QWORD *)&v44 + 1) = L"ConfigFlags";
            if ( !v41 || !(unsigned __int8)PnpRegistryValueExists(v41, &v44) )
              *(_DWORD *)(Pool2 + 184) |= 4u;
            if ( (*(_DWORD *)(Pool2 + 184) & 0x24) != 0 )
              goto LABEL_112;
            memset_0(v50, 0, 0xC8u);
            *(_QWORD *)v50 = DEVPKEY_DriverPackage_NeedsReconfig;
            v52 = &v36;
            v51 = 17;
            v53 = 1;
            DriverPackageId = PiDevCfgQueryObjectProperties(
                                v31,
                                UnicodeString.Buffer,
                                8,
                                (_DWORD)Handle,
                                (__int64)v50,
                                1);
            if ( DriverPackageId >= 0 )
            {
              if ( v54 >= 0 )
              {
                v32 = v36;
              }
              else
              {
                v32 = 0;
                v36 = 0;
              }
              if ( v32 == -1 )
                *(_DWORD *)(Pool2 + 184) |= 4u;
LABEL_112:
              *(_QWORD *)(Pool2 + 16) = Handle;
              *(_QWORD *)(Pool2 + 24) = v43;
              *(_QWORD *)(Pool2 + 32) = v41;
              Handle = 0;
              v43 = 0;
              v41 = 0;
              *v49 = Pool2;
              goto LABEL_29;
            }
          }
        }
        else
        {
          DriverPackageId = -1073741670;
        }
LABEL_28:
        PiDevCfgFreeDriverNode(Pool2);
      }
    }
  }
LABEL_29:
  if ( Handle )
    ZwClose(Handle);
  if ( v43 )
    ZwClose(v43);
  if ( v47 )
    ZwClose(v47);
  if ( v41 )
    ZwClose(v41);
  RtlFreeAnsiString(&UnicodeString);
  RtlFreeAnsiString(&v48);
  return (unsigned int)DriverPackageId;
}

```

## disassembly

```asm
0x140b039e4  mov     [rsp-8+arg_10], rbx
0x140b039e9  push    rbp
0x140b039ea  push    rsi
0x140b039eb  push    rdi
0x140b039ec  push    r12
0x140b039ee  push    r13
0x140b039f0  push    r14
0x140b039f2  push    r15
0x140b039f4  lea     rbp, [rsp-180h]
0x140b039fc  sub     rsp, 280h
0x140b03a03  mov     rax, cs:__security_cookie
0x140b03a0a  xor     rax, rsp
0x140b03a0d  mov     [rbp+1B0h+var_40], rax
0x140b03a14  mov     rax, [rbp+1B0h+arg_30]
0x140b03a1b  xor     r14d, r14d
0x140b03a1e  mov     r15, rdx
0x140b03a21  mov     [rbp+1B0h+var_200], rax
0x140b03a25  xorps   xmm0, xmm0
0x140b03a28  mov     qword ptr [rsp+2B0h+UnicodeString.Length], r14
0x140b03a2d  or      r12d, 0FFFFFFFFh
0x140b03a31  mov     [rsp+2B0h+UnicodeString.Buffer], r14
0x140b03a36  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140b03a3a  mov     [rsp+2B0h+Handle], r14
0x140b03a3f  lea     rdx, [rsp+2B0h+UnicodeString]
0x140b03a44  mov     [rsp+2B0h+var_26D], r14b
0x140b03a49  mov     qword ptr [rbp+1B0h+var_210.Length], r14
0x140b03a4d  mov     r13d, r9d
0x140b03a50  mov     [rbp+1B0h+var_210.Buffer], r14
0x140b03a54  mov     rsi, rcx
0x140b03a57  mov     [rsp+2B0h+var_26F], r14b
0x140b03a5c  mov     [rsp+2B0h+var_25C], r12d
0x140b03a61  mov     [rbp+1B0h+var_220], rdi
0x140b03a65  mov     [rsp+2B0h+var_270], r14b
0x140b03a6a  mov     [rsp+2B0h+var_26E], r14b
0x140b03a6f  movups  [rsp+2B0h+var_238], xmm0
0x140b03a74  mov     [rbp+1B0h+var_218], r14
0x140b03a78  mov     [rsp+2B0h+var_240], r14
0x140b03a7d  mov     [rsp+2B0h+var_258], r14
0x140b03a82  mov     [rbp+1B0h+var_228], r8d
0x140b03a86  mov     [rsp+2B0h+var_260], 0FF000000h
0x140b03a8e  call    PiDevCfgGetDriverPackageId
0x140b03a93  mov     ebx, eax
0x140b03a95  test    eax, eax
0x140b03a97  js      loc_140B03C60
0x140b03a9d  mov     rdx, [rsp+2B0h+UnicodeString.Buffer]
0x140b03aa2  lea     rax, [rsp+2B0h+Handle]
0x140b03aa7  mov     rcx, cs:PiPnpRtlCtx
0x140b03aae  lea     r8d, [r14+8]
0x140b03ab2  mov     qword ptr [rsp+2B0h+var_288], rax
0x140b03ab7  mov     r9d, 20019h
0x140b03abd  mov     byte ptr [rsp+2B0h+var_290], r14b
0x140b03ac2  call    _PnpOpenObjectRegKey
0x140b03ac7  mov     ebx, eax
0x140b03ac9  test    eax, eax
0x140b03acb  js      loc_140B03C60
0x140b03ad1  xor     edx, edx; Val
0x140b03ad3  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x140b03ad7  mov     r8d, 0C8h; Size
0x140b03add  call    memset_0
0x140b03ae2  mov     r9, [rsp+2B0h+Handle]
0x140b03ae7  lea     rax, DEVPKEY_DriverPackage_Invalidated
0x140b03aee  mov     rdx, [rsp+2B0h+UnicodeString.Buffer]
0x140b03af3  lea     r8d, [r14+8]
0x140b03af7  mov     qword ptr [rbp+1B0h+var_1F0], rax
0x140b03afb  lea     rax, [rsp+2B0h+var_26D]
0x140b03b00  mov     [rbp+1B0h+var_1E0], rax
0x140b03b04  lea     rax, DEVPKEY_DriverPackage_TargetComputerIds
0x140b03b0b  mov     [rbp+1B0h+var_1C8], rax
0x140b03b0f  lea     rax, [rbp+1B0h+var_210]
0x140b03b13  mov     [rbp+1B0h+var_1B8], rax
0x140b03b17  lea     rax, [rbp+1B0h+var_1F0]
0x140b03b1b  mov     dword ptr [rsp+2B0h+var_288], 2
0x140b03b23  mov     qword ptr [rsp+2B0h+var_290], rax
0x140b03b28  mov     [rbp+1B0h+var_1E8], 11h
0x140b03b2f  mov     [rbp+1B0h+var_1D8], 1
0x140b03b36  mov     [rbp+1B0h+var_1C0], 2012h
0x140b03b3d  mov     [rbp+1B0h+var_1AC], 6
0x140b03b44  call    PiDevCfgQueryObjectProperties
0x140b03b49  mov     ebx, eax
0x140b03b4b  test    eax, eax
0x140b03b4d  js      loc_140B03C60
0x140b03b53  cmp     [rbp+1B0h+var_1D0], r14d
0x140b03b57  jl      short loc_140B03B6A
0x140b03b59  cmp     [rsp+2B0h+var_26D], dil
0x140b03b5e  jnz     short loc_140B03B6A
0x140b03b60  mov     ebx, 0C0000056h
0x140b03b65  jmp     loc_140B03C60
0x140b03b6a  mov     rbx, r14
0x140b03b6d  cmp     [rbp+1B0h+var_1A8], r14d
0x140b03b71  jl      short loc_140B03BC7
0x140b03b73  mov     rax, [rbp+1B0h+var_210.Buffer]
0x140b03b77  test    rax, rax
0x140b03b7a  jz      short loc_140B03BC7
0x140b03b7c  mov     ecx, 2
0x140b03b81  cmp     [rbp+1B0h+var_210.Length], cx
0x140b03b85  jbe     short loc_140B03BC7
0x140b03b87  mov     rbx, rax
0x140b03b8a  cmp     [rax], r14w
0x140b03b8e  jz      short loc_140B03BBD
0x140b03b90  mov     rcx, rbx; SourceString
0x140b03b93  call    PipCheckComputerSupported
0x140b03b98  test    al, al
0x140b03b9a  jnz     short loc_140B03BB7
0x140b03b9c  mov     rax, rdi
0x140b03b9f  inc     rax
0x140b03ba2  cmp     [rbx+rax*2], r14w
0x140b03ba7  jnz     short loc_140B03B9F
0x140b03ba9  lea     rbx, [rbx+rax*2]
0x140b03bad  add     rbx, 2
0x140b03bb1  cmp     [rbx], r14w
0x140b03bb5  jnz     short loc_140B03B90
0x140b03bb7  cmp     [rbx], r14w
0x140b03bbb  jnz     short loc_140B03BC7
0x140b03bbd  mov     ebx, 0C0000424h
0x140b03bc2  jmp     loc_140B03C60
0x140b03bc7  mov     r14d, dword ptr [rbp+1B0h+arg_20]
0x140b03bce  test    r14b, 8
0x140b03bd2  jz      short loc_140B03BD9
0x140b03bd4  test    rbx, rbx
0x140b03bd7  jz      short loc_140B03BBD
0x140b03bd9  mov     edx, 1C8h
0x140b03bde  mov     ecx, 100h
0x140b03be3  mov     r8d, 63647050h
0x140b03be9  call    ExAllocatePool2
0x140b03bee  mov     rdi, rax
0x140b03bf1  test    rax, rax
0x140b03bf4  jnz     short loc_140B03BFD
0x140b03bf6  mov     ebx, 0C000009Ah
0x140b03bfb  jmp     short loc_140B03C60
0x140b03bfd  mov     eax, cs:Feature_KernelPnP_LogBlockedDrivers__private_featureState
0x140b03c03  test    al, 10h
0x140b03c05  jz      short loc_140B03C0C
0x140b03c07  and     eax, 1
0x140b03c0a  jmp     short loc_140B03C11
0x140b03c0c  call    Feature_KernelPnP_LogBlockedDrivers__private_IsEnabledDeviceUsageNoInline
0x140b03c11  test    eax, eax
0x140b03c13  jnz     short loc_140B03C23
0x140b03c15  lea     rax, [rdi+0E0h]
0x140b03c1c  mov     [rax+8], rax
0x140b03c20  mov     [rax], rax
0x140b03c23  lea     rax, [rdi+0D0h]
0x140b03c2a  mov     rdx, rsi; SourceString
0x140b03c2d  mov     [rax+8], rax
0x140b03c31  lea     rcx, [rdi+28h]; DestinationString
0x140b03c35  mov     [rax], rax
0x140b03c38  lea     rax, [rdi+180h]
0x140b03c3f  mov     [rax+8], rax
0x140b03c43  mov     [rax], rax
0x140b03c46  call    RtlCreateUnicodeString
0x140b03c4b  test    al, al
0x140b03c4d  jnz     loc_140B03CDB
0x140b03c53  mov     ebx, 0C000009Ah
0x140b03c58  mov     rcx, rdi
0x140b03c5b  call    PiDevCfgFreeDriverNode
0x140b03c60  mov     rcx, [rsp+2B0h+Handle]; Handle
0x140b03c65  test    rcx, rcx
0x140b03c68  jz      short loc_140B03C6F
0x140b03c6a  call    ZwClose
0x140b03c6f  mov     rcx, [rsp+2B0h+var_240]; Handle
0x140b03c74  test    rcx, rcx
0x140b03c77  jz      short loc_140B03C7E
0x140b03c79  call    ZwClose
0x140b03c7e  mov     rcx, [rbp+1B0h+var_218]; Handle
0x140b03c82  test    rcx, rcx
0x140b03c85  jz      short loc_140B03C8C
0x140b03c87  call    ZwClose
0x140b03c8c  mov     rcx, [rsp+2B0h+var_258]; Handle
0x140b03c91  test    rcx, rcx
0x140b03c94  jz      short loc_140B03C9B
0x140b03c96  call    ZwClose
0x140b03c9b  lea     rcx, [rsp+2B0h+UnicodeString]; UnicodeString
0x140b03ca0  call    RtlFreeAnsiString
0x140b03ca5  lea     rcx, [rbp+1B0h+var_210]; UnicodeString
0x140b03ca9  call    RtlFreeAnsiString
0x140b03cae  mov     eax, ebx
0x140b03cb0  mov     rcx, [rbp+1B0h+var_40]
0x140b03cb7  xor     rcx, rsp; StackCookie
0x140b03cba  call    __security_check_cookie
0x140b03cbf  mov     rbx, [rsp+2B0h+arg_10]
0x140b03cc7  add     rsp, 280h
0x140b03cce  pop     r15
0x140b03cd0  pop     r14
0x140b03cd2  pop     r13
0x140b03cd4  pop     r12
0x140b03cd6  pop     rdi
0x140b03cd7  pop     rsi
0x140b03cd8  pop     rbp
0x140b03cd9  retn
0x140b03cdb  lea     rcx, [rdi+38h]
0x140b03cdf  lea     rdx, [rsp+2B0h+UnicodeString]
0x140b03ce4  call    PnpDuplicateUnicodeString
0x140b03ce9  test    al, al
0x140b03ceb  jz      loc_140B03C53
0x140b03cf1  lea     rcx, [rdi+48h]; DestinationString
0x140b03cf5  mov     rdx, r15; SourceString
0x140b03cf8  call    RtlCreateUnicodeString
0x140b03cfd  test    al, al
0x140b03cff  jz      loc_140B03C53
0x140b03d05  test    rbx, rbx
0x140b03d08  jz      short loc_140B03D21
0x140b03d0a  lea     rcx, [rdi+80h]; DestinationString
0x140b03d11  mov     rdx, rbx; SourceString
0x140b03d14  call    RtlCreateUnicodeString
0x140b03d19  test    al, al
0x140b03d1b  jz      loc_140B03C53
0x140b03d21  xor     edx, edx; Val
0x140b03d23  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x140b03d27  mov     r8d, 0C8h; Size
0x140b03d2d  call    memset_0
0x140b03d32  mov     r9, [rsp+2B0h+Handle]
0x140b03d37  lea     rax, DEVPKEY_DriverPackage_DriverDate
0x140b03d3e  mov     qword ptr [rbp+1B0h+var_1F0], rax
0x140b03d42  lea     r15, [rdi+0BCh]
0x140b03d49  mov     ecx, 10h
0x140b03d4e  mov     dword ptr [rsp+2B0h+var_288], 5
0x140b03d56  lea     rax, [rdi+70h]
0x140b03d5a  mov     [rbp+1B0h+var_1E8], ecx
0x140b03d5d  mov     [rbp+1B0h+var_1E0], rax
0x140b03d61  lea     rsi, [rdi+90h]
0x140b03d68  lea     rax, DEVPKEY_DriverPackage_DriverVersion
0x140b03d6f  mov     [rbp+1B0h+var_1C0], 9
0x140b03d76  mov     [rbp+1B0h+var_1C8], rax
0x140b03d7a  lea     edx, [rcx-8]
0x140b03d7d  lea     rax, [rdi+78h]
0x140b03d81  mov     [rbp+1B0h+var_1D8], edx
0x140b03d84  mov     [rbp+1B0h+var_1B8], rax
0x140b03d88  mov     r8d, edx
0x140b03d8b  lea     rax, DEVPKEY_DriverPackage_SignerScore
0x140b03d92  mov     [rbp+1B0h+var_1B0], edx
0x140b03d95  mov     rdx, [rsp+2B0h+UnicodeString.Buffer]
0x140b03d9a  mov     [rbp+1B0h+var_1A0], rax
0x140b03d9e  lea     rax, [rsp+2B0h+var_260]
0x140b03da3  mov     [rbp+1B0h+var_190], rax
0x140b03da7  lea     rax, DEVPKEY_DriverPackage_ExtensionId
0x140b03dae  mov     [rbp+1B0h+var_178], rax
0x140b03db2  lea     rax, DEVPKEY_DriverPackage_ExtensionContractIds
0x140b03db9  mov     [rbp+1B0h+var_150], rax
0x140b03dbd  lea     rax, [rbp+1B0h+var_1F0]
0x140b03dc1  mov     qword ptr [rsp+2B0h+var_290], rax
0x140b03dc6  mov     [rbp+1B0h+var_198], 7
0x140b03dcd  mov     [rbp+1B0h+var_188], 4
0x140b03dd4  mov     [rbp+1B0h+var_170], 0Dh
0x140b03ddb  mov     [rbp+1B0h+var_168], r15
0x140b03ddf  mov     [rbp+1B0h+var_160], ecx
0x140b03de2  mov     [rbp+1B0h+var_148], 100Dh
0x140b03de9  mov     [rbp+1B0h+var_140], rsi
0x140b03ded  mov     [rbp+1B0h+var_134], 2
0x140b03df4  call    PiDevCfgQueryObjectProperties
0x140b03df9  xor     ecx, ecx
0x140b03dfb  mov     ebx, eax
0x140b03dfd  test    eax, eax
0x140b03dff  js      loc_140B03C58
0x140b03e05  cmp     [rbp+1B0h+var_1D0], ecx
0x140b03e08  jge     short loc_140B03E10
0x140b03e0a  xor     eax, eax
0x140b03e0c  mov     [rdi+70h], rax
0x140b03e10  cmp     [rbp+1B0h+var_1A8], ecx
0x140b03e13  jge     short loc_140B03E1B
0x140b03e15  xor     eax, eax
0x140b03e17  mov     [rdi+78h], rax
0x140b03e1b  cmp     [rbp+1B0h+var_180], ecx
0x140b03e1e  jge     short loc_140B03E28
0x140b03e20  mov     [rsp+2B0h+var_260], 0FF000000h
0x140b03e28  cmp     [rbp+1B0h+var_158], ecx
0x140b03e2b  jge     short loc_140B03E34
0x140b03e2d  xorps   xmm0, xmm0
0x140b03e30  movups  xmmword ptr [r15], xmm0
0x140b03e34  cmp     [rbp+1B0h+var_130], ecx
0x140b03e3a  jge     short loc_140B03E41
0x140b03e3c  mov     [rsi], rcx
0x140b03e3f  jmp     short loc_140B03E64
0x140b03e41  mov     eax, [rbp+1B0h+var_138]
0x140b03e44  test    al, 0Fh
0x140b03e46  jnz     short loc_140B03E53
0x140b03e48  shr     eax, 4
0x140b03e4b  mov     [rdi+98h], eax
0x140b03e51  jmp     short loc_140B03E64
0x140b03e53  mov     rcx, [rsi]; P
0x140b03e56  xor     edx, edx; Tag
0x140b03e58  call    ExFreePoolWithTag
0x140b03e5d  mov     qword ptr [rsi], 0
0x140b03e64  mov     r15d, 1
0x140b03e6a  test    r14b, 4
0x140b03e6e  jz      short loc_140B03E75
0x140b03e70  mov     ecx, r12d
0x140b03e73  jmp     short loc_140B03E9F
0x140b03e75  mov     eax, r14d
0x140b03e78  and     al, r15b
0x140b03e7b  neg     al
0x140b03e7d  movzx   eax, word ptr [rbp+1B0h+var_228]
0x140b03e81  sbb     ecx, ecx
0x140b03e83  and     r13d, 0FF0000h
0x140b03e8a  and     ecx, 0F1000000h
0x140b03e90  add     ecx, 0FF000000h
0x140b03e96  and     ecx, [rsp+2B0h+var_260]
0x140b03e9a  or      ecx, r13d
0x140b03e9d  or      ecx, eax
0x140b03e9f  mov     r13d, 2
0x140b03ea5  mov     [rdi+6Ch], ecx
0x140b03ea8  test    r13b, r14b
  ... truncated ...
```
