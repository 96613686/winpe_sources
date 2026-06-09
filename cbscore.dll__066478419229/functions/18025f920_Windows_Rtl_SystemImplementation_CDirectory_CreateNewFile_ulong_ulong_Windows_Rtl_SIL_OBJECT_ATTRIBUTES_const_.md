# Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile(ulong,ulong,Windows::Rtl::SIL_OBJECT_ATTRIBUTES const &,ulong,ulong,ulong,ulong,Windows::Auto<Windows::Rtl::IRtlFile *> *,ulong *)

- ea: `0x18025f920`
- end: `0x1802600ed`
- name: `?CreateNewFile@CDirectory@SystemImplementation@Rtl@Windows@@UEAAJKKAEBUSIL_OBJECT_ATTRIBUTES@34@KKKKPEAV?$Auto@PEAUIRtlFile@Rtl@Windows@@@4@PEAK@Z`
- size: `1997`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, unsigned int, int, int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180019bdc`
- `0x18001a1a0`
- `0x180070398`
- `0x1800a26b0`
- `0x1800aa1d4`
- `0x1800c21b0`
- `0x1800eb920`
- `0x1800ef360`
- `0x180155c88`
- `0x1801f077c`
- `0x180210910`
- `0x18021211c`
- `0x18021398c`
- `0x180228fe4`
- `0x180228ffc`
- `0x18022d734`
- `0x18025f920`
- `0x1802d5010`

## string_xrefs

- `0x18025fa80`: `Valid flags check failed: ShareAccess`
- `0x18025faf2`: `CreateOptions`
- `0x18025fac4`: `Valid flags check failed: CreateOptions`
- `0x18025fdea`: `ValidateForEnsureSetSecurity(DesiredAccess, CreateOptions, LocalObjectAttributes)`
- `0x18025f9fb`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fa28`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fa6d`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fab1`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fadf`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fb20`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fb55`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fd03`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fd78`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fdcc`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fe10`: `onecore\base\wcp\sil\directory.cpp`
- `0x18025fe2e`: `ValidateForEnsureSetAttributes(DesiredAccess, FileAttributes)`
- `0x18025fd31`: `!m_FileSystemProvider->IsUnbufferedSil()`
- `0x18025f99a`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x18025f9eb`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x18025fd23`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x18025fd8b`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x18025fddf`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x18025fe23`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        Windows::Rtl::SystemImplementation **a9,
        _DWORD *a10)
{
  _QWORD *v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  int inited; // esi
  unsigned int v18; // r8d
  __int64 v19; // rax
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  unsigned int v24; // esi
  const char **v25; // rdx
  const char *v26; // rax
  __int64 v27; // r9
  unsigned int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  Windows::Rtl::SystemImplementation *v33; // rax
  unsigned __int64 v34; // [rsp+58h] [rbp-A8h]
  Windows::Rtl::SystemImplementation *v35; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[24]; // [rsp+88h] [rbp-78h] BYREF
  const char *v37; // [rsp+A0h] [rbp-60h]
  const char *v38; // [rsp+A8h] [rbp-58h] BYREF
  const char *v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  const char *v41; // [rsp+C0h] [rbp-40h]
  Windows::Rtl::SystemImplementation **v42; // [rsp+C8h] [rbp-38h]
  _QWORD v43[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v44[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v45[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v46[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v47[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v48[4]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v49[4]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v50; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v51; // [rsp+1C0h] [rbp+C0h]
  _OWORD v52[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v53; // [rsp+200h] [rbp+100h] BYREF
  __int128 v54; // [rsp+208h] [rbp+108h] BYREF
  __int128 v55; // [rsp+218h] [rbp+118h]
  __int128 v56; // [rsp+228h] [rbp+128h]
  int v57; // [rsp+238h] [rbp+138h] BYREF
  __int128 v58; // [rsp+240h] [rbp+140h] BYREF
  int v59; // [rsp+250h] [rbp+150h] BYREF
  __int128 v60; // [rsp+258h] [rbp+158h] BYREF
  __int128 v61; // [rsp+268h] [rbp+168h] BYREF
  int v62[14]; // [rsp+280h] [rbp+180h] BYREF
  char v63; // [rsp+2B8h] [rbp+1B8h]

  LODWORD(v35) = a3;
  v42 = a9;
  v57 = 0;
  if ( a10 )
    *a10 = 0;
  v62[10] = 0;
  v63 = 0;
  v62[2] = 1;
  if ( (unsigned __int8)Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::ShouldArm() )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(
      (int)v62,
      0,
      (int)&v57,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      a1,
      (__int64)"Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
      0,
      0,
      0,
      0,
      v34);
  if ( (a2 & 0xFFFFC200) != 0 )
  {
    *(_QWORD *)&v36[8] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    *(_QWORD *)v36 = "onecore\\base\\wcp\\sil\\directory.cpp";
    v13 = v36;
    *(_QWORD *)&v36[16] = 696;
    v37 = "Valid flags check failed: Flags";
LABEL_12:
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v57,
            v13);
    goto LABEL_9;
  }
  if ( !a9 )
  {
    v43[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v43[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v43[2] = 698;
    v43[3] = "Not-null check failed: File";
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v57,
            v43);
LABEL_9:
    v15 = v14;
LABEL_63:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v62);
    return v15;
  }
  if ( (a6 & 0xFFFFFFF8) != 0 )
  {
    v44[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v44[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v13 = v44;
    v44[2] = 699;
    v44[3] = "Valid flags check failed: ShareAccess";
    goto LABEL_12;
  }
  if ( (a8 & 0xFF000000) != 0 )
  {
    v45[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v45[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v13 = v45;
    v45[2] = 700;
    v45[3] = "Valid flags check failed: CreateOptions";
    goto LABEL_12;
  }
  if ( (a8 & 0x40) == 0 )
  {
    v46[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v46[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v13 = v46;
    v46[2] = 701;
    v46[3] = "CreateOptions";
    goto LABEL_12;
  }
  if ( (a2 & 1) != 0 )
  {
    if ( a7 - 2 > 1 && a7 != 5 )
    {
      v47[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v47[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
      v13 = v47;
      v47[2] = 707;
      v47[3] = "CreationDisposition == 0x00000002 || CreationDisposition == 0x00000003 || CreationDisposition == 0x00000005";
      goto LABEL_12;
    }
  }
  else if ( a7 != 2 && a7 != 5 )
  {
    v48[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v48[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v13 = v48;
    v48[2] = 712;
    v48[3] = "CreationDisposition == 0x00000002 || CreationDisposition == 0x00000005";
    goto LABEL_12;
  }
  v16 = *(_QWORD *)(a4 + 8);
  v53 = 0;
  v50 = 0;
  v51 = 0;
  v61 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v58 = 0;
  memset(v36, 0, sizeof(v36));
  v60 = 0;
  memset(v52, 0, 40);
  inited = Windows::StringUtil::Rtl::CombineNtPaths<_LUNICODE_STRING,_LUNICODE_STRING>(a1 + 48, v16, v36);
  if ( inited < 0 )
    goto LABEL_25;
  inited = RtlInitUnicodeStringFromLUnicodeString(*(_QWORD *)(a4 + 8), &v60);
  if ( inited < 0 )
    goto LABEL_25;
  *((_QWORD *)&v54 + 1) = *(_QWORD *)(a1 + 40);
  DWORD2(v55) = *(_DWORD *)(a4 + 16);
  *(_QWORD *)&v55 = &v60;
  *(_QWORD *)&v56 = *(_QWORD *)(a4 + 24);
  v19 = *(_QWORD *)(a4 + 32);
  LODWORD(v54) = 48;
  *((_QWORD *)&v56 + 1) = v19;
  v59 = 0;
  if ( (a2 & 0x400) == 0 )
  {
    inited = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 24LL))(*(_QWORD *)(a1 + 24), &v53);
    if ( inited < 0 )
      goto LABEL_25;
  }
  v20 = a2 & 4 | 8;
  if ( (a2 & 8) == 0 )
    v20 = a2 & 4;
  v21 = v20 | 1;
  if ( (a2 & 2) == 0 )
    v21 = v20;
  v22 = v21 | 0x200;
  if ( (a2 & 0x20) == 0 )
    v22 = v21;
  v23 = v22 | 0x400;
  if ( (a2 & 0x40) == 0 )
    v23 = v22;
  v24 = v23 | 0x800;
  if ( (a2 & 0x80u) == 0 )
    v24 = v23;
  if ( (a2 & 0x800) != 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 72) + 264LL))(*(_QWORD *)(a1 + 72)) )
    {
      v49[2] = 777;
      v49[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
      v25 = (const char **)v49;
      v49[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v49[3] = "!m_FileSystemProvider->IsUnbufferedSil()";
LABEL_42:
      v15 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
              &v57,
              v25);
      Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)v52);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v36);
      Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v58);
      goto LABEL_63;
    }
    if ( a7 != 5 )
    {
      v40 = 778;
      v38 = "onecore\\base\\wcp\\sil\\directory.cpp";
      v39 = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v26 = "CreationDisposition == 0x00000005";
LABEL_45:
      v41 = v26;
      v25 = &v38;
      goto LABEL_42;
    }
    v24 |= 0x10000u;
  }
  v27 = (unsigned int)v35;
  if ( (a2 & 0x1000) != 0 )
  {
    if ( !(unsigned __int8)Windows::Rtl::SystemImplementation::ValidateForEnsureSetSecurity(
                             (unsigned int)v35,
                             a8,
                             v56,
                             (unsigned int)v35) )
    {
      v40 = 784;
      v38 = "onecore\\base\\wcp\\sil\\directory.cpp";
      v39 = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v26 = "ValidateForEnsureSetSecurity(DesiredAccess, CreateOptions, LocalObjectAttributes)";
      goto LABEL_45;
    }
    v24 |= 0x20000u;
  }
  v28 = a5;
  if ( (a2 & 0x2000) != 0 )
  {
    if ( !Windows::Rtl::SystemImplementation::ValidateForEnsureSetAttributes(
            (Windows::Rtl::SystemImplementation *)(unsigned int)v27,
            a5,
            v18) )
    {
      v40 = 790;
      v38 = "onecore\\base\\wcp\\sil\\directory.cpp";
      v39 = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v26 = "ValidateForEnsureSetAttributes(DesiredAccess, FileAttributes)";
      goto LABEL_45;
    }
    v24 |= 0x40000u;
  }
  inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, __int128 *, __int128 *, _QWORD, unsigned int, int, unsigned int, unsigned int, _QWORD, _DWORD, __int64, int *))(**(_QWORD **)(a1 + 72) + 112LL))(
             *(_QWORD *)(a1 + 72),
             v24,
             &v58,
             v27,
             &v54,
             &v61,
             0,
             v28,
             a6,
             a7,
             a8,
             0,
             0,
             v53,
             &v59);
  if ( inited < 0 )
  {
LABEL_25:
    v57 = inited;
LABEL_62:
    Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)v52);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v36);
    Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v58);
    v15 = inited;
    goto LABEL_63;
  }
  if ( v59 != 1 )
  {
    if ( a10 )
    {
      switch ( v59 )
      {
        case 4:
          *a10 = 4;
          break;
        case 2:
          *a10 = 2;
          break;
        case 5:
          *a10 = 5;
          break;
        case 11:
          *a10 = 6;
          break;
        case 12:
          *a10 = 7;
          break;
        case 13:
          *a10 = 8;
          break;
        default:
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x1802600ECLL);
      }
    }
    goto LABEL_75;
  }
  v29 = *((_QWORD *)&v52[0] + 1);
  v50 = *(unsigned __int64 *)(a1 + 72);
  *((_QWORD *)&v51 + 1) = *(_QWORD *)(a1 + 24);
  *((_QWORD *)&v52[0] + 1) = *((_QWORD *)&v58 + 1);
  *((_QWORD *)&v58 + 1) = v29;
  v30 = v58;
  *(_QWORD *)&v58 = *(_QWORD *)&v52[0];
  *(_QWORD *)&v52[0] = v30;
  *(_QWORD *)&v52[1] = *(_QWORD *)v36;
  *(_QWORD *)&v51 = 0;
  v35 = 0;
  *(_OWORD *)((char *)&v52[1] + 8) = *(_OWORD *)&v36[8];
  if ( (a2 & 0x10) != 0 )
    v31 = Windows::Rtl::CRtlRefCountedObjectBase<Windows::Rtl::SystemImplementation::CIniFile,Windows::Rtl::IRtlIniFile,Windows::Rtl::IRtlFile,Windows::Rtl::IRtlSystemObject,Windows::Rtl::IRtlFilesystemObject,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface>::CreateInstance<Windows::Rtl::SystemImplementation::CreateObjectSource,Windows::Rtl::IRtlFile>(
            &v50,
            &v35);
  else
    v31 = Windows::Rtl::CRtlRefCountedObjectBase<Windows::Rtl::SystemImplementation::CFile,Windows::Rtl::IRtlFile,Windows::Rtl::IRtlSystemObject,Windows::Rtl::IRtlFilesystemObject,Windows::Rtl::SystemImplementation::IRtlFilesystemObjectBaseInternal,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface>::CreateInstance<Windows::Rtl::SystemImplementation::CreateObjectSource,Windows::Rtl::IRtlFilesystemObject>(
            &v50,
            &v35);
  inited = v31;
  if ( v31 < 0 )
  {
    v57 = v31;
    Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v35);
    goto LABEL_62;
  }
  v33 = v35;
  v35 = *v42;
  *v42 = v33;
  if ( a10 )
  {
    if ( (unsigned __int64)(*((_QWORD *)&v61 + 1) - 2LL) <= 1 )
    {
      if ( *((_QWORD *)&v61 + 1) )
        goto LABEL_73;
    }
    else if ( *((_QWORD *)&v61 + 1) )
    {
      if ( *((_QWORD *)&v61 + 1) == 1
        || (MicrosoftTelemetryAssertTriggeredArgs("wcp_sil", a7, *((_QWORD *)&v61 + 1), 0), ((a7 - 1) & 0xFFFFFFFD) == 0) )
      {
        *a10 = 3;
        goto LABEL_74;
      }
LABEL_73:
      *a10 = 1;
      goto LABEL_74;
    }
    if ( a7 )
      MicrosoftTelemetryAssertTriggeredArgs("wcp_sil", a7, *((_QWORD *)&v61 + 1), 0);
    goto LABEL_73;
  }
LABEL_74:
  Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v35);
LABEL_75:
  v63 = 1;
  Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)v52);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v36);
  Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v58);
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v62);
  return (unsigned int)v57;
}

```

## disassembly

```asm
0x18025f920  mov     [rsp-8+arg_8], rbx
0x18025f925  push    rbp
0x18025f926  push    rsi
0x18025f927  push    rdi
0x18025f928  push    r12
0x18025f92a  push    r13
0x18025f92c  push    r14
0x18025f92e  push    r15
0x18025f930  lea     rbp, [rsp-310h]
0x18025f938  sub     rsp, 410h
0x18025f93f  mov     rax, cs:__security_cookie
0x18025f946  xor     rax, rsp
0x18025f949  mov     [rbp+340h+var_40], rax
0x18025f950  mov     rbx, [rbp+340h+arg_48]
0x18025f957  xor     esi, esi
0x18025f959  mov     rdi, [rbp+340h+arg_40]
0x18025f960  mov     r13, r9
0x18025f963  mov     dword ptr [rbp+340h+var_3C0], r8d
0x18025f967  mov     r14d, edx
0x18025f96a  mov     [rbp+340h+var_378], rdi
0x18025f96e  mov     r15, rcx
0x18025f971  mov     [rbp+340h+var_208], esi
0x18025f977  test    rbx, rbx
0x18025f97a  jz      short loc_18025F97E
0x18025f97c  mov     [rbx], esi
0x18025f97e  mov     [rbp+340h+var_198], esi
0x18025f984  mov     [rbp+340h+var_188], sil
0x18025f98b  mov     [rbp+340h+var_1B8], 1
0x18025f995  call    ?ShouldArm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0N@@Rtl@WCP@Windows@@SA_NPEAU_RTL_TRACING_FACILITY@234@@Z; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::ShouldArm(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x18025f99a  lea     rcx, aWindowsRtlSyst_313; "Windows::Rtl::SystemImplementation::CDi"...
0x18025f9a1  test    al, al
0x18025f9a3  jz      short loc_18025F9F2
0x18025f9a5  mov     qword ptr [rsp+440h+var_3F0], rsi; unsigned int
0x18025f9aa  lea     rax, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18025f9b1  mov     [rsp+440h+var_3F8], rsi; __int64
0x18025f9b6  lea     r9, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x18025f9bd  mov     [rsp+440h+var_400], rsi; __int64
0x18025f9c2  lea     r8, [rbp+340h+var_208]; int
0x18025f9c9  mov     [rsp+440h+var_408], rsi; __int64
0x18025f9ce  xor     edx, edx; int
0x18025f9d0  mov     [rsp+440h+var_410], rax; Windows::WCP::Rtl *
0x18025f9d5  mov     [rsp+440h+var_418], rcx; __int64
0x18025f9da  lea     rcx, [rbp+340h+var_1C0]; int
0x18025f9e1  mov     [rsp+440h+var_420], r15; __int64
0x18025f9e6  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAAXKAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(ulong,Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x18025f9eb  lea     rcx, aWindowsRtlSyst_313; "Windows::Rtl::SystemImplementation::CDi"...
0x18025f9f2  test    r14d, 0FFFFC200h
0x18025f9f9  jz      short loc_18025FA23
0x18025f9fb  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fa02  mov     qword ptr [rbp+340h+var_3B8+8], rcx
0x18025fa06  mov     qword ptr [rbp+340h+var_3B8], rax
0x18025fa0a  lea     rdx, [rbp+340h+var_3B8]
0x18025fa0e  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x18025fa15  mov     [rbp+340h+var_3A8], 2B8h
0x18025fa1d  mov     [rbp+340h+var_3A0], rax
0x18025fa21  jmp     short loc_18025FA93
0x18025fa23  test    rdi, rdi
0x18025fa26  jnz     short loc_18025FA61
0x18025fa28  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fa2f  mov     [rbp+340h+var_368], rcx
0x18025fa33  mov     [rbp+340h+var_370], rax
0x18025fa37  lea     rdx, [rbp+340h+var_370]
0x18025fa3b  lea     rax, aNotNullCheckFa_35; "Not-null check failed: File"
0x18025fa42  mov     [rbp+340h+var_360], 2BAh
0x18025fa4a  lea     rcx, [rbp+340h+var_208]
0x18025fa51  mov     [rbp+340h+var_358], rax
0x18025fa55  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18025fa5a  mov     ebx, eax
0x18025fa5c  jmp     loc_18025FF98
0x18025fa61  test    [rbp+340h+arg_28], 0FFFFFFF8h
0x18025fa6b  jz      short loc_18025FAA1
0x18025fa6d  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fa74  mov     [rbp+340h+var_348], rcx
0x18025fa78  mov     [rbp+340h+var_350], rax
0x18025fa7c  lea     rdx, [rbp+340h+var_350]
0x18025fa80  lea     rax, aValidFlagsChec; "Valid flags check failed: ShareAccess"
0x18025fa87  mov     [rbp+340h+var_340], 2BBh
0x18025fa8f  mov     [rbp+340h+var_338], rax
0x18025fa93  lea     rcx, [rbp+340h+var_208]
0x18025fa9a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18025fa9f  jmp     short loc_18025FA5A
0x18025faa1  mov     r12d, [rbp+340h+arg_38]
0x18025faa8  test    r12d, 0FF000000h
0x18025faaf  jz      short loc_18025FAD9
0x18025fab1  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fab8  mov     [rbp+340h+var_328], rcx
0x18025fabc  mov     [rbp+340h+var_330], rax
0x18025fac0  lea     rdx, [rbp+340h+var_330]
0x18025fac4  lea     rax, aValidFlagsChec_5; "Valid flags check failed: CreateOptions"
0x18025facb  mov     [rbp+340h+var_320], 2BCh
0x18025fad3  mov     [rbp+340h+var_318], rax
0x18025fad7  jmp     short loc_18025FA93
0x18025fad9  test    r12b, 40h
0x18025fadd  jnz     short loc_18025FB07
0x18025fadf  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fae6  mov     [rbp+340h+var_308], rcx
0x18025faea  mov     [rbp+340h+var_310], rax
0x18025faee  lea     rdx, [rbp+340h+var_310]
0x18025faf2  lea     rax, aCreateoptions; "CreateOptions"
0x18025faf9  mov     [rbp+340h+var_300], 2BDh
0x18025fb01  mov     [rbp+340h+var_2F8], rax
0x18025fb05  jmp     short loc_18025FA93
0x18025fb07  mov     edi, [rbp+340h+arg_30]
0x18025fb0d  test    r14b, 1
0x18025fb11  jz      short loc_18025FB4B
0x18025fb13  lea     eax, [rdi-2]
0x18025fb16  cmp     eax, 1
0x18025fb19  jbe     short loc_18025FB86
0x18025fb1b  cmp     edi, 5
0x18025fb1e  jz      short loc_18025FB86
0x18025fb20  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fb27  mov     [rbp+340h+var_2E8], rcx
0x18025fb2b  mov     [rbp+340h+var_2F0], rax
0x18025fb2f  lea     rdx, [rbp+340h+var_2F0]
0x18025fb33  lea     rax, aCreationdispos_0; "CreationDisposition == 0x00000002 || Cr"...
0x18025fb3a  mov     [rbp+340h+var_2E0], 2C3h
0x18025fb42  mov     [rbp+340h+var_2D8], rax
0x18025fb46  jmp     loc_18025FA93
0x18025fb4b  cmp     edi, 2
0x18025fb4e  jz      short loc_18025FB86
0x18025fb50  cmp     edi, 5
0x18025fb53  jz      short loc_18025FB86
0x18025fb55  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fb5c  mov     [rbp+340h+var_2C8], rcx
0x18025fb60  mov     [rbp+340h+var_2D0], rax
0x18025fb64  lea     rdx, [rbp+340h+var_2D0]
0x18025fb68  lea     rax, aCreationdispos; "CreationDisposition == 0x00000002 || Cr"...
0x18025fb6f  mov     [rbp+340h+var_2C0], 2C8h
0x18025fb7a  mov     [rbp+340h+var_2B8], rax
0x18025fb81  jmp     loc_18025FA93
0x18025fb86  mov     rdx, [r13+8]
0x18025fb8a  lea     rcx, [r15+30h]
0x18025fb8e  xorps   xmm1, xmm1
0x18025fb91  mov     [rbp+340h+var_240], rsi
0x18025fb98  xorps   xmm0, xmm0
0x18025fb9b  movdqa  [rbp+340h+var_290], xmm1
0x18025fba3  xor     eax, eax
0x18025fba5  movdqa  [rbp+340h+var_280], xmm0
0x18025fbad  lea     r8, [rbp+340h+var_3B8]
0x18025fbb1  mov     [rbp+340h+var_3A8], rax
0x18025fbb5  movups  [rbp+340h+var_1D8], xmm0
0x18025fbbc  mov     [rbp+340h+var_250], rax
0x18025fbc3  movups  [rbp+340h+var_238], xmm1
0x18025fbca  movups  [rbp+340h+var_228], xmm1
0x18025fbd1  movups  [rbp+340h+var_218], xmm1
0x18025fbd8  movdqu  [rbp+340h+var_200], xmm0
0x18025fbe0  movups  [rbp+340h+var_3B8], xmm1
0x18025fbe4  movups  [rbp+340h+var_1E8], xmm0
0x18025fbeb  movdqa  [rbp+340h+var_270], xmm0
0x18025fbf3  movups  [rbp+340h+var_260], xmm1
0x18025fbfa  call    ??$CombineNtPaths@U_LUNICODE_STRING@@U1@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@0PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineNtPaths<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x18025fbff  mov     esi, eax
0x18025fc01  test    eax, eax
0x18025fc03  jns     short loc_18025FC10
0x18025fc05  mov     [rbp+340h+var_208], esi
0x18025fc0b  jmp     loc_18025FF75
0x18025fc10  mov     rcx, [r13+8]
0x18025fc14  lea     rdx, [rbp+340h+var_1E8]
0x18025fc1b  call    RtlInitUnicodeStringFromLUnicodeString
0x18025fc20  mov     esi, eax
0x18025fc22  test    eax, eax
0x18025fc24  js      short loc_18025FC05
0x18025fc26  mov     rax, [r15+28h]
0x18025fc2a  mov     qword ptr [rbp+340h+var_238+8], rax
0x18025fc31  mov     eax, [r13+10h]
0x18025fc35  mov     dword ptr [rbp+340h+var_228+8], eax
0x18025fc3b  lea     rax, [rbp+340h+var_1E8]
0x18025fc42  mov     qword ptr [rbp+340h+var_228], rax
0x18025fc49  mov     rax, [r13+18h]
0x18025fc4d  mov     qword ptr [rbp+340h+var_218], rax
0x18025fc54  mov     rax, [r13+20h]
0x18025fc58  xor     r13d, r13d
0x18025fc5b  mov     dword ptr [rbp+340h+var_238], 30h ; '0'
0x18025fc65  mov     qword ptr [rbp+340h+var_218+8], rax
0x18025fc6c  mov     [rbp+340h+var_1F0], r13d
0x18025fc73  bt      r14d, 0Ah
0x18025fc78  jb      short loc_18025FC9B
0x18025fc7a  mov     rcx, [r15+18h]
0x18025fc7e  lea     rdx, [rbp+340h+var_240]
0x18025fc85  mov     rax, [rcx]
0x18025fc88  mov     rax, [rax+18h]
0x18025fc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025fc91  mov     esi, eax
0x18025fc93  test    eax, eax
0x18025fc95  js      loc_18025FC05
0x18025fc9b  mov     ecx, r14d
0x18025fc9e  and     ecx, 4
0x18025fca1  mov     edx, ecx
0x18025fca3  or      edx, 8
0x18025fca6  test    r14b, 8
0x18025fcaa  cmovz   edx, ecx
0x18025fcad  mov     ecx, edx
0x18025fcaf  or      ecx, 1
0x18025fcb2  test    r14b, 2
0x18025fcb6  cmovz   ecx, edx
0x18025fcb9  mov     edx, ecx
0x18025fcbb  bts     edx, 9
0x18025fcbf  test    r14b, 20h
0x18025fcc3  cmovz   edx, ecx
0x18025fcc6  mov     ecx, edx
0x18025fcc8  bts     ecx, 0Ah
0x18025fccc  test    r14b, 40h
0x18025fcd0  cmovz   ecx, edx
0x18025fcd3  mov     edx, 800h
0x18025fcd8  mov     esi, ecx
0x18025fcda  or      esi, edx
0x18025fcdc  test    r14b, 80h
0x18025fce0  cmovz   esi, ecx
0x18025fce3  test    edx, r14d
0x18025fce6  jz      loc_18025FDAB
0x18025fcec  mov     rcx, [r15+48h]
0x18025fcf0  mov     rax, [rcx]
0x18025fcf3  mov     rax, [rax+108h]
0x18025fcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025fcff  test    al, al
0x18025fd01  jz      short loc_18025FD73
0x18025fd03  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fd0a  mov     [rbp+340h+var_2A0], 309h
0x18025fd15  mov     [rbp+340h+var_2B0], rax
0x18025fd1c  lea     rdx, [rbp+340h+var_2B0]
0x18025fd23  lea     rax, aWindowsRtlSyst_313; "Windows::Rtl::SystemImplementation::CDi"...
0x18025fd2a  mov     [rbp+340h+var_2A8], rax
0x18025fd31  lea     rax, aMFilesystempro_4; "!m_FileSystemProvider->IsUnbufferedSil("...
0x18025fd38  mov     [rbp+340h+var_298], rax
0x18025fd3f  lea     rcx, [rbp+340h+var_208]
0x18025fd46  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18025fd4b  lea     rcx, [rbp+340h+var_270]; this
0x18025fd52  mov     ebx, eax
0x18025fd54  call    ??1CSilHandle@SystemImplementation@Rtl@Windows@@QEAA@XZ; Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle(void)
0x18025fd59  lea     rcx, [rbp+340h+var_3B8]
0x18025fd5d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18025fd62  lea     rcx, [rbp+340h+var_200]; this
0x18025fd69  call    ??1CSilHandle@SystemImplementation@Rtl@Windows@@QEAA@XZ; Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle(void)
0x18025fd6e  jmp     loc_18025FF98
0x18025fd73  cmp     edi, 5
0x18025fd76  jz      short loc_18025FDA7
0x18025fd78  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fd7f  mov     [rbp+340h+var_388], 30Ah
0x18025fd87  mov     [rbp+340h+var_398], rax
0x18025fd8b  lea     rax, aWindowsRtlSyst_313; "Windows::Rtl::SystemImplementation::CDi"...
0x18025fd92  mov     [rbp+340h+var_390], rax
0x18025fd96  lea     rax, aCreationdispos_1; "CreationDisposition == 0x00000005"
0x18025fd9d  mov     [rbp+340h+var_380], rax
0x18025fda1  lea     rdx, [rbp+340h+var_398]
0x18025fda5  jmp     short loc_18025FD3F
0x18025fda7  bts     esi, 10h
0x18025fdab  mov     r9d, dword ptr [rbp+340h+var_3C0]
0x18025fdaf  bt      r14d, 0Ch
0x18025fdb4  jnb     short loc_18025FDF7
0x18025fdb6  mov     r8, qword ptr [rbp+340h+var_218]
0x18025fdbd  mov     edx, r12d
0x18025fdc0  mov     ecx, r9d
0x18025fdc3  call    Windows__Rtl__SystemImplementation__ValidateForEnsureSetSecurity
0x18025fdc8  test    al, al
0x18025fdca  jnz     short loc_18025FDF3
0x18025fdcc  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fdd3  mov     [rbp+340h+var_388], 310h
0x18025fddb  mov     [rbp+340h+var_398], rax
0x18025fddf  lea     rax, aWindowsRtlSyst_313; "Windows::Rtl::SystemImplementation::CDi"...
0x18025fde6  mov     [rbp+340h+var_390], rax
0x18025fdea  lea     rax, aValidateforens; "ValidateForEnsureSetSecurity(DesiredAcc"...
0x18025fdf1  jmp     short loc_18025FD9D
0x18025fdf3  bts     esi, 11h
0x18025fdf7  mov     edx, [rbp+340h+arg_20]; unsigned int
0x18025fdfd  bt      r14d, 0Dh
0x18025fe02  jnb     short loc_18025FE3E
0x18025fe04  mov     ecx, r9d; this
0x18025fe07  call    ?ValidateForEnsureSetAttributes@SystemImplementation@Rtl@Windows@@YA_NKK@Z; Windows::Rtl::SystemImplementation::ValidateForEnsureSetAttributes(ulong,ulong)
0x18025fe0c  test    al, al
0x18025fe0e  jnz     short loc_18025FE3A
0x18025fe10  lea     rax, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\sil\\directory.cpp"
0x18025fe17  mov     [rbp+340h+var_388], 316h
0x18025fe1f  mov     [rbp+340h+var_398], rax
0x18025fe23  lea     rax, aWindowsRtlSyst_313; "Windows::Rtl::SystemImplementation::CDi"...
0x18025fe2a  mov     [rbp+340h+var_390], rax
0x18025fe2e  lea     rax, aValidateforens_3; "ValidateForEnsureSetAttributes(DesiredA"...
0x18025fe35  jmp     loc_18025FD9D
0x18025fe3a  bts     esi, 12h
0x18025fe3e  mov     rax, [rbp+340h+var_240]
0x18025fe45  lea     r8, [rbp+340h+var_200]
0x18025fe4c  mov     r11, [r15+48h]
0x18025fe50  mov     rcx, [r11]
0x18025fe53  mov     r10, [rcx+70h]
0x18025fe57  lea     rcx, [rbp+340h+var_1F0]
0x18025fe5e  mov     [rsp+440h+var_3D0], rcx
0x18025fe63  mov     rcx, r11
0x18025fe66  mov     [rsp+440h+var_3D8], rax
0x18025fe6b  mov     eax, [rbp+340h+arg_28]
0x18025fe71  mov     [rsp+440h+var_3E0], r13d
0x18025fe76  mov     [rsp+440h+var_3E8], r13
0x18025fe7b  mov     [rsp+440h+var_3F0], r12d
0x18025fe80  mov     dword ptr [rsp+440h+var_3F8], edi
0x18025fe84  mov     dword ptr [rsp+440h+var_400], eax
0x18025fe88  lea     rax, [rbp+340h+var_1D8]
0x18025fe8f  mov     dword ptr [rsp+440h+var_408], edx
0x18025fe93  mov     edx, esi
0x18025fe95  mov     [rsp+440h+var_410], r13
0x18025fe9a  mov     [rsp+440h+var_418], rax
0x18025fe9f  lea     rax, [rbp+340h+var_238]
0x18025fea6  mov     [rsp+440h+var_420], rax
  ... truncated ...
```
