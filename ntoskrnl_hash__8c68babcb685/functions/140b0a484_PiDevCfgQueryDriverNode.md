# PiDevCfgQueryDriverNode

- ea: `0x140b0a484`
- end: `0x140b0adf5`
- name: `PiDevCfgQueryDriverNode`
- size: `2417`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, int, int, char, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140a84f54`

## callees

- `0x1404d44e0`
- `0x1404e89b4`
- `0x1405e51c8`
- `0x1405e5224`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406f7380`
- `0x140760240`
- `0x14076de80`
- `0x140878f34`
- `0x140901d60`
- `0x14094b120`
- `0x1409bb9d0`
- `0x140a4b070`
- `0x140a84d94`
- `0x140a87ec8`
- `0x140a87f94`
- `0x140ac77c0`
- `0x140b0a484`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140b0ab93`: `Configuration`
- `0x140b0ab07`: `Descriptors`
- `0x140b0ad03`: `ConfigFlags`

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
  __int64 v12; // rcx
  wchar_t *Buffer; // rbx
  __int64 v14; // rax
  __int64 Pool2; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  PVOID *v21; // rsi
  int v22; // ecx
  __int64 v23; // rcx
  char v24; // al
  int v25; // eax
  char v26; // al
  __int64 v27; // r8
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  char v34; // al
  ULONG v35; // [rsp+20h] [rbp-E0h]
  char v36; // [rsp+40h] [rbp-C0h] BYREF
  char v37; // [rsp+41h] [rbp-BFh] BYREF
  char v38; // [rsp+42h] [rbp-BEh] BYREF
  char v39; // [rsp+43h] [rbp-BDh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE v43; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v45; // [rsp+70h] [rbp-90h] BYREF
  __int128 v46; // [rsp+78h] [rbp-88h] BYREF
  int v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v49; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v51; // [rsp+B0h] [rbp-50h]
  ULONG v52[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v53; // [rsp+C8h] [rbp-38h]
  char *v54; // [rsp+D0h] [rbp-30h]
  int v55; // [rsp+D8h] [rbp-28h]
  int v56; // [rsp+E0h] [rbp-20h]
  __int64 *v57; // [rsp+E8h] [rbp-18h]
  int v58; // [rsp+F0h] [rbp-10h]
  UNICODE_STRING *v59; // [rsp+F8h] [rbp-8h]
  int v60; // [rsp+100h] [rbp+0h]
  int v61; // [rsp+104h] [rbp+4h]
  int v62; // [rsp+108h] [rbp+8h]
  __int64 *v63; // [rsp+110h] [rbp+10h]
  int v64; // [rsp+118h] [rbp+18h]
  __int64 *v65; // [rsp+120h] [rbp+20h]
  int v66; // [rsp+128h] [rbp+28h]
  int v67; // [rsp+130h] [rbp+30h]
  __int64 *v68; // [rsp+138h] [rbp+38h]
  int v69; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+148h] [rbp+48h]
  int v71; // [rsp+150h] [rbp+50h]
  int v72; // [rsp+158h] [rbp+58h]
  __int64 *v73; // [rsp+160h] [rbp+60h]
  int v74; // [rsp+168h] [rbp+68h]
  __int64 v75; // [rsp+170h] [rbp+70h]
  unsigned int v76; // [rsp+178h] [rbp+78h]
  int v77; // [rsp+17Ch] [rbp+7Ch]
  int v78; // [rsp+180h] [rbp+80h]
  int v79[2]; // [rsp+190h] [rbp+90h] BYREF
  int v80; // [rsp+198h] [rbp+98h]
  const wchar_t *v81; // [rsp+1A0h] [rbp+A0h]
  __int64 v82; // [rsp+1A8h] [rbp+A8h]
  int v83; // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v84)(int, int, int, int, int, __int64); // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v85; // [rsp+1D8h] [rbp+D8h]
  __int64 v86; // [rsp+1E0h] [rbp+E0h]
  int v87; // [rsp+208h] [rbp+108h]
  const wchar_t *v88; // [rsp+210h] [rbp+110h]
  __int64 v89; // [rsp+218h] [rbp+118h]
  int v90; // [rsp+220h] [rbp+120h]

  v51 = a7;
  *(_QWORD *)&UnicodeString.Length = 0;
  v8 = -1;
  UnicodeString.Buffer = 0;
  Handle = 0;
  v39 = 0;
  *(_QWORD *)&v50.Length = 0;
  v50.Buffer = 0;
  v37 = 0;
  v42 = -1;
  v48 = -1;
  v36 = 0;
  v38 = 0;
  v46 = 0;
  v49 = 0;
  v45 = 0;
  v43 = 0;
  v47 = a3;
  v41 = -16777216;
  DriverPackageId = PiDevCfgGetDriverPackageId(SourceString, &UnicodeString);
  if ( DriverPackageId >= 0 )
  {
    DriverPackageId = PnpOpenObjectRegKey(
                        *(__int64 *)&PiPnpRtlCtx,
                        (__int64)UnicodeString.Buffer,
                        8,
                        131097,
                        0,
                        (__int64)&Handle);
    if ( DriverPackageId >= 0 )
    {
      memset_0(v52, 0, 0xC8u);
      *(_QWORD *)v52 = DEVPKEY_DriverPackage_Invalidated;
      v54 = &v39;
      v57 = DEVPKEY_DriverPackage_TargetComputerIds;
      v59 = &v50;
      v53 = 17;
      v55 = 1;
      v58 = 8210;
      v61 = 6;
      DriverPackageId = PiDevCfgQueryObjectProperties(v12, (__int64)UnicodeString.Buffer, 8u, Handle, (__int64)v52, 2u);
      if ( DriverPackageId >= 0 )
      {
        if ( v56 >= 0 && v39 == -1 )
        {
          DriverPackageId = -1073741738;
          goto LABEL_29;
        }
        Buffer = 0;
        if ( v62 >= 0 && v50.Buffer && v50.Length > 2u )
        {
          Buffer = v50.Buffer;
          if ( !*v50.Buffer )
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
          && PnpDuplicateUnicodeString(Pool2 + 56, (__int64)&UnicodeString)
          && RtlCreateUnicodeString((PUNICODE_STRING)(Pool2 + 72), a2)
          && (!Buffer || RtlCreateUnicodeString((PUNICODE_STRING)(Pool2 + 128), Buffer)) )
        {
          memset_0(v52, 0, 0xC8u);
          *(_QWORD *)v52 = DEVPKEY_DriverPackage_DriverDate;
          v53 = 16;
          v54 = (char *)(Pool2 + 112);
          v21 = (PVOID *)(Pool2 + 144);
          v58 = 9;
          v57 = DEVPKEY_DriverPackage_DriverVersion;
          v55 = 8;
          v59 = (UNICODE_STRING *)(Pool2 + 120);
          v60 = 8;
          v63 = (__int64 *)&DEVPKEY_DriverPackage_SignerScore;
          v65 = (__int64 *)&v41;
          v68 = DEVPKEY_DriverPackage_ExtensionId;
          v73 = DEVPKEY_DriverPackage_ExtensionContractIds;
          v64 = 7;
          v66 = 4;
          v69 = 13;
          v70 = Pool2 + 188;
          v71 = 16;
          v74 = 4109;
          v75 = Pool2 + 144;
          v77 = 2;
          DriverPackageId = PiDevCfgQueryObjectProperties(
                              16,
                              (__int64)UnicodeString.Buffer,
                              8u,
                              Handle,
                              (__int64)v52,
                              5u);
          if ( DriverPackageId >= 0 )
          {
            if ( v56 < 0 )
              *(_QWORD *)(Pool2 + 112) = 0;
            if ( v62 < 0 )
              *(_QWORD *)(Pool2 + 120) = 0;
            if ( v67 < 0 )
              v41 = -16777216;
            if ( v72 < 0 )
              *(_OWORD *)(Pool2 + 188) = 0;
            if ( v78 >= 0 )
            {
              if ( (v76 & 0xF) != 0 )
              {
                ExFreePoolWithTag(*v21, 0);
                *v21 = 0;
              }
              else
              {
                *(_DWORD *)(Pool2 + 152) = v76 >> 4;
              }
            }
            else
            {
              *v21 = 0;
            }
            if ( (a5 & 4) != 0 )
              v22 = -1;
            else
              v22 = (unsigned __int16)v47 | a4 & 0xFF0000 | v41 & ((a5 & 1) != 0 ? -268435456 : -16777216);
            *(_DWORD *)(Pool2 + 108) = v22;
            if ( (a5 & 2) != 0 )
            {
              memset_0(v52, 0, 0xC8u);
              *(_QWORD *)v52 = DEVPKEY_DriverPackage_F6;
              v54 = &v36;
              v53 = 17;
              v55 = 1;
              DriverPackageId = PiDevCfgQueryObjectProperties(
                                  v23,
                                  (__int64)UnicodeString.Buffer,
                                  8u,
                                  Handle,
                                  (__int64)v52,
                                  1u);
              if ( DriverPackageId < 0 )
                goto LABEL_28;
              if ( v56 >= 0 )
              {
                v24 = v36;
              }
              else
              {
                v24 = 0;
                v36 = 0;
              }
              if ( v24 == -1 )
                *(_DWORD *)(Pool2 + 184) |= 2u;
            }
            if ( (Feature_KernelPnP_CheckDriverIntegrity__private_featureState & 0x10) != 0 )
              v25 = Feature_KernelPnP_CheckDriverIntegrity__private_featureState & 1;
            else
              v25 = Feature_KernelPnP_CheckDriverIntegrity__private_IsEnabledDeviceUsageNoInline();
            if ( v25 && a6 && (*a6 & 2) != 0 )
            {
              memset_0(v52, 0, 0xC8u);
              *(_QWORD *)v52 = &DEVPKEY_DriverPackage_Inbox;
              v54 = &v37;
              v57 = DEVPKEY_DriverPackage_CatalogAttributes;
              v59 = (UNICODE_STRING *)&v42;
              v63 = DEVPKEY_DriverPackage_CertificationVersion;
              v65 = &v48;
              v53 = 17;
              v55 = 1;
              v58 = 7;
              v60 = 4;
              v64 = 9;
              v66 = 8;
              DriverPackageId = PiDevCfgQueryObjectProperties(
                                  8,
                                  (__int64)UnicodeString.Buffer,
                                  8u,
                                  Handle,
                                  (__int64)v52,
                                  3u);
              if ( DriverPackageId < 0 )
                goto LABEL_28;
              if ( v56 >= 0 )
              {
                v26 = v37;
              }
              else
              {
                v26 = 0;
                v37 = 0;
              }
              if ( v62 >= 0 )
                v8 = v42;
              else
                v42 = -1;
              if ( v67 >= 0 )
              {
                v27 = v48;
              }
              else
              {
                v27 = -1;
                v48 = -1;
              }
              LOBYTE(v19) = v26 == -1;
              v28 = PiDevCfgEnforceDriverPolicy(a6, v8, v27, v19);
              if ( v28 < 0 )
              {
                *(_DWORD *)(Pool2 + 184) |= 0x200u;
                *(_DWORD *)(Pool2 + 448) = v28;
              }
            }
            LODWORD(v46) = 1572886;
            *((_QWORD *)&v46 + 1) = L"Descriptors";
            v29 = IopOpenRegistryKeyEx(&v49, Handle, &v46, 131097);
            DriverPackageId = v29;
            if ( v29 == -1073741772 )
              goto LABEL_87;
            if ( v29 < 0 )
              goto LABEL_28;
            v30 = IopOpenRegistryKeyEx(&v45, v49, Pool2 + 72, 131097);
            DriverPackageId = v30;
            if ( v30 == -1073741772 )
            {
LABEL_87:
              DriverPackageId = 0;
            }
            else
            {
              if ( v30 < 0 )
                goto LABEL_28;
              memset_0(v79, 0, 0xE0u);
              v81 = L"Configuration";
              v83 = 0x1000000;
              v82 = Pool2 + 88;
              v80 = 288;
              DriverPackageId = RtlpQueryRegistryValues(3221225472LL, (const WCHAR *)v45, v79, 0, v35, 1);
              if ( DriverPackageId < 0 )
                goto LABEL_28;
              if ( !*(_WORD *)(Pool2 + 88) && *(_QWORD *)(Pool2 + 96) )
                RtlFreeAnsiString((PUNICODE_STRING)(Pool2 + 88));
            }
            v31 = *(_QWORD *)(Pool2 + 96);
            if ( v31 )
            {
              v32 = PiDevCfgOpenDriverConfiguration(Handle, v31, &v43);
              DriverPackageId = v32;
              if ( v32 == -1073741772 )
              {
                DriverPackageId = 0;
              }
              else
              {
                if ( v32 < 0 )
                  goto LABEL_28;
                memset_0(v79, 0, 0xE0u);
                v90 = 117440512;
                *(_QWORD *)v79 = PiDevCfgQueryDriverVersionValueCallback;
                v81 = L"DriverDate";
                v84 = PiDevCfgQueryDriverVersionValueCallback;
                v82 = Pool2 + 112;
                v89 = Pool2 + 160;
                v85 = L"DriverVersion";
                v87 = 304;
                v86 = Pool2 + 120;
                v88 = L"ExcludeIds";
                DriverPackageId = RtlpQueryRegistryValues(3221225472LL, (const WCHAR *)v43, v79, 0, v35, 1);
                if ( DriverPackageId < 0 )
                  goto LABEL_28;
                if ( *(_WORD *)(Pool2 + 160) <= 2u && *(_QWORD *)(Pool2 + 168) )
                  RtlFreeAnsiString((PUNICODE_STRING)(Pool2 + 160));
              }
            }
            if ( !PnpBootMode )
              goto LABEL_112;
            LODWORD(v46) = 1572886;
            *((_QWORD *)&v46 + 1) = L"ConfigFlags";
            if ( !v43 || !(unsigned __int8)PnpRegistryValueExists(v43, &v46) )
              *(_DWORD *)(Pool2 + 184) |= 4u;
            if ( (*(_DWORD *)(Pool2 + 184) & 0x24) != 0 )
              goto LABEL_112;
            memset_0(v52, 0, 0xC8u);
            *(_QWORD *)v52 = DEVPKEY_DriverPackage_NeedsReconfig;
            v54 = &v38;
            v53 = 17;
            v55 = 1;
            DriverPackageId = PiDevCfgQueryObjectProperties(
                                v33,
                                (__int64)UnicodeString.Buffer,
                                8u,
                                Handle,
                                (__int64)v52,
                                1u);
            if ( DriverPackageId >= 0 )
            {
              if ( v56 >= 0 )
              {
                v34 = v38;
              }
              else
              {
                v34 = 0;
                v38 = 0;
              }
              if ( v34 == -1 )
                *(_DWORD *)(Pool2 + 184) |= 4u;
LABEL_112:
              *(_QWORD *)(Pool2 + 16) = Handle;
              *(_QWORD *)(Pool2 + 24) = v45;
              *(_QWORD *)(Pool2 + 32) = v43;
              Handle = 0;
              v45 = 0;
              v43 = 0;
              *v51 = Pool2;
              goto LABEL_29;
            }
          }
        }
        else
        {
          DriverPackageId = -1073741670;
        }
LABEL_28:
        PiDevCfgFreeDriverNode(Pool2, v17, v18, v19);
      }
    }
  }
LABEL_29:
  if ( Handle )
    ZwClose(Handle);
  if ( v45 )
    ZwClose(v45);
  if ( v49 )
    ZwClose(v49);
  if ( v43 )
    ZwClose(v43);
  RtlFreeAnsiString(&UnicodeString);
  RtlFreeAnsiString(&v50);
  return (unsigned int)DriverPackageId;
}

```

## disassembly

```asm
0x140b0a484  mov     [rsp-8+arg_10], rbx
0x140b0a489  push    rbp
0x140b0a48a  push    rsi
0x140b0a48b  push    rdi
0x140b0a48c  push    r12
0x140b0a48e  push    r13
0x140b0a490  push    r14
0x140b0a492  push    r15
0x140b0a494  lea     rbp, [rsp-180h]
0x140b0a49c  sub     rsp, 280h
0x140b0a4a3  mov     rax, cs:__security_cookie
0x140b0a4aa  xor     rax, rsp
0x140b0a4ad  mov     [rbp+1B0h+var_40], rax
0x140b0a4b4  mov     rax, [rbp+1B0h+arg_30]
0x140b0a4bb  xor     r14d, r14d
0x140b0a4be  mov     r15, rdx
0x140b0a4c1  mov     [rbp+1B0h+var_200], rax
0x140b0a4c5  xorps   xmm0, xmm0
0x140b0a4c8  mov     qword ptr [rsp+2B0h+UnicodeString.Length], r14
0x140b0a4cd  or      r12d, 0FFFFFFFFh
0x140b0a4d1  mov     [rsp+2B0h+UnicodeString.Buffer], r14
0x140b0a4d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140b0a4da  mov     [rsp+2B0h+Handle], r14
0x140b0a4df  lea     rdx, [rsp+2B0h+UnicodeString]
0x140b0a4e4  mov     [rsp+2B0h+var_26D], r14b
0x140b0a4e9  mov     qword ptr [rbp+1B0h+var_210.Length], r14
0x140b0a4ed  mov     r13d, r9d
0x140b0a4f0  mov     [rbp+1B0h+var_210.Buffer], r14
0x140b0a4f4  mov     rsi, rcx
0x140b0a4f7  mov     [rsp+2B0h+var_26F], r14b
0x140b0a4fc  mov     [rsp+2B0h+var_25C], r12d
0x140b0a501  mov     [rbp+1B0h+var_220], rdi
0x140b0a505  mov     [rsp+2B0h+var_270], r14b
0x140b0a50a  mov     [rsp+2B0h+var_26E], r14b
0x140b0a50f  movups  [rsp+2B0h+var_238], xmm0
0x140b0a514  mov     [rbp+1B0h+var_218], r14
0x140b0a518  mov     [rsp+2B0h+var_240], r14
0x140b0a51d  mov     [rsp+2B0h+var_258], r14
0x140b0a522  mov     [rbp+1B0h+var_228], r8d
0x140b0a526  mov     [rsp+2B0h+var_260], 0FF000000h
0x140b0a52e  call    PiDevCfgGetDriverPackageId
0x140b0a533  mov     ebx, eax
0x140b0a535  test    eax, eax
0x140b0a537  js      loc_140B0A700
0x140b0a53d  mov     rdx, [rsp+2B0h+UnicodeString.Buffer]
0x140b0a542  lea     rax, [rsp+2B0h+Handle]
0x140b0a547  mov     rcx, cs:PiPnpRtlCtx
0x140b0a54e  lea     r8d, [r14+8]
0x140b0a552  mov     qword ptr [rsp+2B0h+var_288], rax
0x140b0a557  mov     r9d, 20019h
0x140b0a55d  mov     byte ptr [rsp+2B0h+var_290], r14b
0x140b0a562  call    _PnpOpenObjectRegKey
0x140b0a567  mov     ebx, eax
0x140b0a569  test    eax, eax
0x140b0a56b  js      loc_140B0A700
0x140b0a571  xor     edx, edx; Val
0x140b0a573  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x140b0a577  mov     r8d, 0C8h; Size
0x140b0a57d  call    memset_0
0x140b0a582  mov     r9, [rsp+2B0h+Handle]
0x140b0a587  lea     rax, DEVPKEY_DriverPackage_Invalidated
0x140b0a58e  mov     rdx, [rsp+2B0h+UnicodeString.Buffer]
0x140b0a593  lea     r8d, [r14+8]
0x140b0a597  mov     qword ptr [rbp+1B0h+var_1F0], rax
0x140b0a59b  lea     rax, [rsp+2B0h+var_26D]
0x140b0a5a0  mov     [rbp+1B0h+var_1E0], rax
0x140b0a5a4  lea     rax, DEVPKEY_DriverPackage_TargetComputerIds
0x140b0a5ab  mov     [rbp+1B0h+var_1C8], rax
0x140b0a5af  lea     rax, [rbp+1B0h+var_210]
0x140b0a5b3  mov     [rbp+1B0h+var_1B8], rax
0x140b0a5b7  lea     rax, [rbp+1B0h+var_1F0]
0x140b0a5bb  mov     dword ptr [rsp+2B0h+var_288], 2
0x140b0a5c3  mov     qword ptr [rsp+2B0h+var_290], rax
0x140b0a5c8  mov     [rbp+1B0h+var_1E8], 11h
0x140b0a5cf  mov     [rbp+1B0h+var_1D8], 1
0x140b0a5d6  mov     [rbp+1B0h+var_1C0], 2012h
0x140b0a5dd  mov     [rbp+1B0h+var_1AC], 6
0x140b0a5e4  call    PiDevCfgQueryObjectProperties
0x140b0a5e9  mov     ebx, eax
0x140b0a5eb  test    eax, eax
0x140b0a5ed  js      loc_140B0A700
0x140b0a5f3  cmp     [rbp+1B0h+var_1D0], r14d
0x140b0a5f7  jl      short loc_140B0A60A
0x140b0a5f9  cmp     [rsp+2B0h+var_26D], dil
0x140b0a5fe  jnz     short loc_140B0A60A
0x140b0a600  mov     ebx, 0C0000056h
0x140b0a605  jmp     loc_140B0A700
0x140b0a60a  mov     rbx, r14
0x140b0a60d  cmp     [rbp+1B0h+var_1A8], r14d
0x140b0a611  jl      short loc_140B0A667
0x140b0a613  mov     rax, [rbp+1B0h+var_210.Buffer]
0x140b0a617  test    rax, rax
0x140b0a61a  jz      short loc_140B0A667
0x140b0a61c  mov     ecx, 2
0x140b0a621  cmp     [rbp+1B0h+var_210.Length], cx
0x140b0a625  jbe     short loc_140B0A667
0x140b0a627  mov     rbx, rax
0x140b0a62a  cmp     [rax], r14w
0x140b0a62e  jz      short loc_140B0A65D
0x140b0a630  mov     rcx, rbx; SourceString
0x140b0a633  call    PipCheckComputerSupported
0x140b0a638  test    al, al
0x140b0a63a  jnz     short loc_140B0A657
0x140b0a63c  mov     rax, rdi
0x140b0a63f  inc     rax
0x140b0a642  cmp     [rbx+rax*2], r14w
0x140b0a647  jnz     short loc_140B0A63F
0x140b0a649  lea     rbx, [rbx+rax*2]
0x140b0a64d  add     rbx, 2
0x140b0a651  cmp     [rbx], r14w
0x140b0a655  jnz     short loc_140B0A630
0x140b0a657  cmp     [rbx], r14w
0x140b0a65b  jnz     short loc_140B0A667
0x140b0a65d  mov     ebx, 0C0000424h
0x140b0a662  jmp     loc_140B0A700
0x140b0a667  mov     r14d, dword ptr [rbp+1B0h+arg_20]
0x140b0a66e  test    r14b, 8
0x140b0a672  jz      short loc_140B0A679
0x140b0a674  test    rbx, rbx
0x140b0a677  jz      short loc_140B0A65D
0x140b0a679  mov     edx, 1C8h
0x140b0a67e  mov     ecx, 100h
0x140b0a683  mov     r8d, 63647050h
0x140b0a689  call    ExAllocatePool2
0x140b0a68e  mov     rdi, rax
0x140b0a691  test    rax, rax
0x140b0a694  jnz     short loc_140B0A69D
0x140b0a696  mov     ebx, 0C000009Ah
0x140b0a69b  jmp     short loc_140B0A700
0x140b0a69d  mov     eax, cs:Feature_KernelPnP_LogBlockedDrivers__private_featureState
0x140b0a6a3  test    al, 10h
0x140b0a6a5  jz      short loc_140B0A6AC
0x140b0a6a7  and     eax, 1
0x140b0a6aa  jmp     short loc_140B0A6B1
0x140b0a6ac  call    Feature_KernelPnP_LogBlockedDrivers__private_IsEnabledDeviceUsageNoInline
0x140b0a6b1  test    eax, eax
0x140b0a6b3  jnz     short loc_140B0A6C3
0x140b0a6b5  lea     rax, [rdi+0E0h]
0x140b0a6bc  mov     [rax+8], rax
0x140b0a6c0  mov     [rax], rax
0x140b0a6c3  lea     rax, [rdi+0D0h]
0x140b0a6ca  mov     rdx, rsi; SourceString
0x140b0a6cd  mov     [rax+8], rax
0x140b0a6d1  lea     rcx, [rdi+28h]; DestinationString
0x140b0a6d5  mov     [rax], rax
0x140b0a6d8  lea     rax, [rdi+180h]
0x140b0a6df  mov     [rax+8], rax
0x140b0a6e3  mov     [rax], rax
0x140b0a6e6  call    RtlCreateUnicodeString
0x140b0a6eb  test    al, al
0x140b0a6ed  jnz     loc_140B0A77B
0x140b0a6f3  mov     ebx, 0C000009Ah
0x140b0a6f8  mov     rcx, rdi
0x140b0a6fb  call    PiDevCfgFreeDriverNode
0x140b0a700  mov     rcx, [rsp+2B0h+Handle]; Handle
0x140b0a705  test    rcx, rcx
0x140b0a708  jz      short loc_140B0A70F
0x140b0a70a  call    ZwClose
0x140b0a70f  mov     rcx, [rsp+2B0h+var_240]; Handle
0x140b0a714  test    rcx, rcx
0x140b0a717  jz      short loc_140B0A71E
0x140b0a719  call    ZwClose
0x140b0a71e  mov     rcx, [rbp+1B0h+var_218]; Handle
0x140b0a722  test    rcx, rcx
0x140b0a725  jz      short loc_140B0A72C
0x140b0a727  call    ZwClose
0x140b0a72c  mov     rcx, [rsp+2B0h+var_258]; Handle
0x140b0a731  test    rcx, rcx
0x140b0a734  jz      short loc_140B0A73B
0x140b0a736  call    ZwClose
0x140b0a73b  lea     rcx, [rsp+2B0h+UnicodeString]; UnicodeString
0x140b0a740  call    RtlFreeAnsiString
0x140b0a745  lea     rcx, [rbp+1B0h+var_210]; UnicodeString
0x140b0a749  call    RtlFreeAnsiString
0x140b0a74e  mov     eax, ebx
0x140b0a750  mov     rcx, [rbp+1B0h+var_40]
0x140b0a757  xor     rcx, rsp; StackCookie
0x140b0a75a  call    __security_check_cookie
0x140b0a75f  mov     rbx, [rsp+2B0h+arg_10]
0x140b0a767  add     rsp, 280h
0x140b0a76e  pop     r15
0x140b0a770  pop     r14
0x140b0a772  pop     r13
0x140b0a774  pop     r12
0x140b0a776  pop     rdi
0x140b0a777  pop     rsi
0x140b0a778  pop     rbp
0x140b0a779  retn
0x140b0a77b  lea     rcx, [rdi+38h]
0x140b0a77f  lea     rdx, [rsp+2B0h+UnicodeString]
0x140b0a784  call    PnpDuplicateUnicodeString
0x140b0a789  test    al, al
0x140b0a78b  jz      loc_140B0A6F3
0x140b0a791  lea     rcx, [rdi+48h]; DestinationString
0x140b0a795  mov     rdx, r15; SourceString
0x140b0a798  call    RtlCreateUnicodeString
0x140b0a79d  test    al, al
0x140b0a79f  jz      loc_140B0A6F3
0x140b0a7a5  test    rbx, rbx
0x140b0a7a8  jz      short loc_140B0A7C1
0x140b0a7aa  lea     rcx, [rdi+80h]; DestinationString
0x140b0a7b1  mov     rdx, rbx; SourceString
0x140b0a7b4  call    RtlCreateUnicodeString
0x140b0a7b9  test    al, al
0x140b0a7bb  jz      loc_140B0A6F3
0x140b0a7c1  xor     edx, edx; Val
0x140b0a7c3  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x140b0a7c7  mov     r8d, 0C8h; Size
0x140b0a7cd  call    memset_0
0x140b0a7d2  mov     r9, [rsp+2B0h+Handle]
0x140b0a7d7  lea     rax, DEVPKEY_DriverPackage_DriverDate
0x140b0a7de  mov     qword ptr [rbp+1B0h+var_1F0], rax
0x140b0a7e2  lea     r15, [rdi+0BCh]
0x140b0a7e9  mov     ecx, 10h
0x140b0a7ee  mov     dword ptr [rsp+2B0h+var_288], 5
0x140b0a7f6  lea     rax, [rdi+70h]
0x140b0a7fa  mov     [rbp+1B0h+var_1E8], ecx
0x140b0a7fd  mov     [rbp+1B0h+var_1E0], rax
0x140b0a801  lea     rsi, [rdi+90h]
0x140b0a808  lea     rax, DEVPKEY_DriverPackage_DriverVersion
0x140b0a80f  mov     [rbp+1B0h+var_1C0], 9
0x140b0a816  mov     [rbp+1B0h+var_1C8], rax
0x140b0a81a  lea     edx, [rcx-8]
0x140b0a81d  lea     rax, [rdi+78h]
0x140b0a821  mov     [rbp+1B0h+var_1D8], edx
0x140b0a824  mov     [rbp+1B0h+var_1B8], rax
0x140b0a828  mov     r8d, edx
0x140b0a82b  lea     rax, DEVPKEY_DriverPackage_SignerScore
0x140b0a832  mov     [rbp+1B0h+var_1B0], edx
0x140b0a835  mov     rdx, [rsp+2B0h+UnicodeString.Buffer]
0x140b0a83a  mov     [rbp+1B0h+var_1A0], rax
0x140b0a83e  lea     rax, [rsp+2B0h+var_260]
0x140b0a843  mov     [rbp+1B0h+var_190], rax
0x140b0a847  lea     rax, DEVPKEY_DriverPackage_ExtensionId
0x140b0a84e  mov     [rbp+1B0h+var_178], rax
0x140b0a852  lea     rax, DEVPKEY_DriverPackage_ExtensionContractIds
0x140b0a859  mov     [rbp+1B0h+var_150], rax
0x140b0a85d  lea     rax, [rbp+1B0h+var_1F0]
0x140b0a861  mov     qword ptr [rsp+2B0h+var_290], rax
0x140b0a866  mov     [rbp+1B0h+var_198], 7
0x140b0a86d  mov     [rbp+1B0h+var_188], 4
0x140b0a874  mov     [rbp+1B0h+var_170], 0Dh
0x140b0a87b  mov     [rbp+1B0h+var_168], r15
0x140b0a87f  mov     [rbp+1B0h+var_160], ecx
0x140b0a882  mov     [rbp+1B0h+var_148], 100Dh
0x140b0a889  mov     [rbp+1B0h+var_140], rsi
0x140b0a88d  mov     [rbp+1B0h+var_134], 2
0x140b0a894  call    PiDevCfgQueryObjectProperties
0x140b0a899  xor     ecx, ecx
0x140b0a89b  mov     ebx, eax
0x140b0a89d  test    eax, eax
0x140b0a89f  js      loc_140B0A6F8
0x140b0a8a5  cmp     [rbp+1B0h+var_1D0], ecx
0x140b0a8a8  jge     short loc_140B0A8B0
0x140b0a8aa  xor     eax, eax
0x140b0a8ac  mov     [rdi+70h], rax
0x140b0a8b0  cmp     [rbp+1B0h+var_1A8], ecx
0x140b0a8b3  jge     short loc_140B0A8BB
0x140b0a8b5  xor     eax, eax
0x140b0a8b7  mov     [rdi+78h], rax
0x140b0a8bb  cmp     [rbp+1B0h+var_180], ecx
0x140b0a8be  jge     short loc_140B0A8C8
0x140b0a8c0  mov     [rsp+2B0h+var_260], 0FF000000h
0x140b0a8c8  cmp     [rbp+1B0h+var_158], ecx
0x140b0a8cb  jge     short loc_140B0A8D4
0x140b0a8cd  xorps   xmm0, xmm0
0x140b0a8d0  movups  xmmword ptr [r15], xmm0
0x140b0a8d4  cmp     [rbp+1B0h+var_130], ecx
0x140b0a8da  jge     short loc_140B0A8E1
0x140b0a8dc  mov     [rsi], rcx
0x140b0a8df  jmp     short loc_140B0A904
0x140b0a8e1  mov     eax, [rbp+1B0h+var_138]
0x140b0a8e4  test    al, 0Fh
0x140b0a8e6  jnz     short loc_140B0A8F3
0x140b0a8e8  shr     eax, 4
0x140b0a8eb  mov     [rdi+98h], eax
0x140b0a8f1  jmp     short loc_140B0A904
0x140b0a8f3  mov     rcx, [rsi]; P
0x140b0a8f6  xor     edx, edx; Tag
0x140b0a8f8  call    ExFreePoolWithTag
0x140b0a8fd  mov     qword ptr [rsi], 0
0x140b0a904  mov     r15d, 1
0x140b0a90a  test    r14b, 4
0x140b0a90e  jz      short loc_140B0A915
0x140b0a910  mov     ecx, r12d
0x140b0a913  jmp     short loc_140B0A93F
0x140b0a915  mov     eax, r14d
0x140b0a918  and     al, r15b
0x140b0a91b  neg     al
0x140b0a91d  movzx   eax, word ptr [rbp+1B0h+var_228]
0x140b0a921  sbb     ecx, ecx
0x140b0a923  and     r13d, 0FF0000h
0x140b0a92a  and     ecx, 0F1000000h
0x140b0a930  add     ecx, 0FF000000h
0x140b0a936  and     ecx, [rsp+2B0h+var_260]
0x140b0a93a  or      ecx, r13d
0x140b0a93d  or      ecx, eax
0x140b0a93f  mov     r13d, 2
0x140b0a945  mov     [rdi+6Ch], ecx
0x140b0a948  test    r13b, r14b
  ... truncated ...
```
