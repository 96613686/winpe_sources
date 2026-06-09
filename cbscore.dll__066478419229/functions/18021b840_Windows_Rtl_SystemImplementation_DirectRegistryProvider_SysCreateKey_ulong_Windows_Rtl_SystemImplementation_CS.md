# Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,_UNICODE_STRING *,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x18021b840`
- end: `0x18021c0ba`
- name: `?SysCreateKey@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KPEAU_UNICODE_STRING@@KUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `2170`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001a1a0`
- `0x1800645d8`
- `0x180064788`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800c16bc`
- `0x1800c21b0`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f70dc`
- `0x18021211c`
- `0x1802138e8`
- `0x180215b14`
- `0x180217ab0`
- `0x180218e80`
- `0x180219834`
- `0x18021b840`
- `0x180223250`
- `0x180225b38`
- `0x1802265f0`
- `0x18027ed9c`
- `0x1802d5010`

## import_xrefs

- `ntdll!NtCreateKey` at `0x18021bca1`
- `ntdll!NtCreateKey` at `0x18021bd45`
- `ntdll!NtCreateKey` at `0x18021bca1`
- `ntdll!NtCreateKey` at `0x18021bd45`
- `ntdll!NtCreateKeyTransacted` at `0x18021bcd7`
- `ntdll!NtCreateKeyTransacted` at `0x18021bd7b`
- `ntdll!NtCreateKeyTransacted` at `0x18021bcd7`
- `ntdll!NtCreateKeyTransacted` at `0x18021bd7b`

## string_xrefs

- `0x18021bf3d`: `Failed to create key {key}, desired access {da} object attributes {oa} titleindex {ti} class {class} createoptions {co}`
- `0x18021b8f0`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x18021ba7a`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x18021bbe2`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x18021bc35`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x18021c03a`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x18021bdb3`: `Transient insufficient resources at NtCreateKey for {oa}`
- `0x18021bbed`: `DesiredAccess`
- `0x18021bc40`: `DesiredAccess`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        ACCESS_MASK a4,
        __int128 *a5,
        ULONG TitleIndex,
        struct _UNICODE_STRING *a7,
        ULONG CreateOptions,
        _QWORD *a9,
        _DWORD *a10)
{
  _DWORD *v10; // rdi
  struct _UNICODE_STRING *v11; // rbx
  char ShouldArm; // al
  Windows::Rtl::SystemImplementation::DirectRegistryProvider *v16; // rcx
  const struct _UNICODE_STRING *v17; // rdx
  int IsUnacceptableKeyPrefix; // eax
  unsigned int v19; // ebx
  int v20; // eax
  _QWORD *v21; // rbx
  __int64 v22; // rdx
  bool *v23; // rdx
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  bool v27; // al
  int CanSetSystemOwner; // esi
  struct _SECURITY_DESCRIPTOR *v29; // rax
  const char **v30; // rdx
  unsigned int v31; // eax
  NTSTATUS v32; // eax
  bool *v33; // r8
  unsigned int v34; // esi
  NTSTATUS v35; // eax
  __int64 v36; // r9
  __int64 v37; // rsi
  int v38; // eax
  const struct _SECURITY_DESCRIPTOR *v39; // rax
  __int64 v40; // rcx
  bool v42[4]; // [rsp+100h] [rbp-80h] BYREF
  PUNICODE_STRING Class; // [rsp+108h] [rbp-78h]
  struct _SECURITY_DESCRIPTOR *v44; // [rsp+110h] [rbp-70h] BYREF
  __int128 v45; // [rsp+118h] [rbp-68h] BYREF
  const char *v46; // [rsp+128h] [rbp-58h] BYREF
  const char *v47; // [rsp+130h] [rbp-50h]
  __int64 v48; // [rsp+138h] [rbp-48h]
  const char *v49; // [rsp+140h] [rbp-40h]
  _QWORD v50[4]; // [rsp+148h] [rbp-38h] BYREF
  _QWORD v51[4]; // [rsp+168h] [rbp-18h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+188h] [rbp+8h] BYREF
  unsigned int v53; // [rsp+1B8h] [rbp+38h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+1C0h] [rbp+40h] BYREF
  ULONG Disposition; // [rsp+1C8h] [rbp+48h] BYREF
  void *KeyHandle[2]; // [rsp+1D0h] [rbp+50h] BYREF
  __int128 v57; // [rsp+1E0h] [rbp+60h] BYREF
  __int64 v58; // [rsp+1F0h] [rbp+70h]
  char v59; // [rsp+1F8h] [rbp+78h]
  __int16 v60; // [rsp+1FAh] [rbp+7Ah]
  __int128 v61; // [rsp+200h] [rbp+80h]
  __int128 v62; // [rsp+210h] [rbp+90h]
  char v63[8]; // [rsp+220h] [rbp+A0h] BYREF
  int v64; // [rsp+228h] [rbp+A8h]
  int v65; // [rsp+248h] [rbp+C8h]
  char v66; // [rsp+258h] [rbp+D8h]

  v10 = a10;
  v11 = a7;
  DesiredAccess = a4;
  Class = a7;
  v53 = 0;
  KeyHandle[0] = 0;
  Disposition = 0;
  v45 = 0;
  if ( a10 )
    *a10 = 0;
  v65 = 0;
  v66 = 0;
  v64 = 1;
  ShouldArm = Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::ShouldArm();
  v16 = (Windows::Rtl::SystemImplementation::DirectRegistryProvider *)"Windows::Rtl::SystemImplementation::DirectRegistry"
                                                                      "Provider::SysCreateKey";
  if ( ShouldArm )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(
      v63,
      &v53,
      Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      a1,
      "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey",
      &Windows::WCP::Rtl::Facility_SIL,
      "(key = {key}, da = {da}, oa = {oa}, ti = {ti}, class = {class}, co = {co})\n",
      "(key = {key}, da = {da}, oa = {oa}, ti = {ti}, class = {class}, co = {co}, disp = {disp})\n",
      "(key = {key}, disp = {disp})\n",
      7,
      "key",
      Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle,
      a3,
      "da",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess,
      &DesiredAccess,
      "oa",
      Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
      a5,
      "ti",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
      &TitleIndex,
      "class",
      Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING,
      v11,
      "co",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions,
      &CreateOptions,
      "disp",
      Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysCreateKeyDisposition,
      v10);
  v17 = (const struct _UNICODE_STRING *)*((_QWORD *)a5 + 2);
  v42[0] = 0;
  IsUnacceptableKeyPrefix = Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(
                              v16,
                              v17,
                              v42);
  v19 = IsUnacceptableKeyPrefix;
  if ( IsUnacceptableKeyPrefix >= 0 )
  {
    if ( v42[0] )
    {
      v50[2] = 5253;
      v50[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
      v50[3] = 0;
      v50[1] = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
      v20 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v53,
              v50,
              3221225529LL);
LABEL_9:
      v19 = v20;
      goto LABEL_81;
    }
    v21 = a9;
    if ( a9 )
      v22 = *a9;
    else
      v22 = 0;
    v20 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(
            a5,
            v22);
    if ( v20 < 0 )
    {
      v53 = v20;
      goto LABEL_9;
    }
    DesiredAccess |= 0x100u;
    v57 = 0;
    v61 = 0;
    v24 = *a5;
    v58 = 0;
    v62 = 0;
    v25 = a5[1];
    v59 = 0;
    *(_OWORD *)&ObjectAttributes.Length = v24;
    v60 = 0;
    v26 = a5[2];
    v42[1] = 0;
    *(_OWORD *)&ObjectAttributes.ObjectName = v25;
    v42[2] = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v26;
    if ( !(_QWORD)v26 && (a2 & 4) == 0 )
    {
      if ( (CreateOptions & 4) != 0 )
      {
        v27 = 1;
      }
      else
      {
        v42[0] = 0;
        CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                              (Windows::WCP::Implementation::Rtl *)v42,
                              v23);
        if ( CanSetSystemOwner < 0 )
          goto LABEL_25;
        v27 = v42[0];
      }
      if ( !v27 )
      {
LABEL_37:
        if ( ObjectAttributes.RootDirectory )
          ObjectAttributes.RootDirectory = *(HANDLE *)ObjectAttributes.RootDirectory;
        if ( v21 )
          v32 = NtCreateKeyTransacted(
                  KeyHandle,
                  DesiredAccess,
                  &ObjectAttributes,
                  TitleIndex,
                  Class,
                  CreateOptions,
                  *v21,
                  &Disposition);
        else
          v32 = NtCreateKey(KeyHandle, DesiredAccess, &ObjectAttributes, TitleIndex, Class, CreateOptions, &Disposition);
        v34 = v32;
        if ( v32 == -1073741670 )
        {
          LODWORD(v44) = 0;
          v42[0] = 1;
          while ( 1 )
          {
            CanSetSystemOwner = Windows::Rtl::SystemImplementation::DelayForInsufficientResources(
                                  (Windows::Rtl::SystemImplementation *)&v44,
                                  (unsigned int *)v42,
                                  v33);
            if ( CanSetSystemOwner < 0 )
              goto LABEL_25;
            if ( v21 )
              v35 = NtCreateKeyTransacted(
                      KeyHandle,
                      DesiredAccess,
                      &ObjectAttributes,
                      TitleIndex,
                      Class,
                      CreateOptions,
                      *v21,
                      &Disposition);
            else
              v35 = NtCreateKey(
                      KeyHandle,
                      DesiredAccess,
                      &ObjectAttributes,
                      TitleIndex,
                      Class,
                      CreateOptions,
                      &Disposition);
            v34 = v35;
            if ( !v42[0] || v35 != -1073741670 )
            {
              if ( v35 < 0 )
                goto LABEL_68;
              Windows::WCP::Rtl::RtlTrace(
                0,
                (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
                (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Transient insufficient resources at NtCreateKey for {oa}",
                (const char *const)1,
                (unsigned __int64)"oa",
                Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
                a5);
              goto LABEL_53;
            }
          }
        }
        if ( v32 >= 0 )
        {
LABEL_53:
          if ( v21 )
            v36 = *v21;
          else
            v36 = 0;
          CanSetSystemOwner = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::Create(
                                a1,
                                KeyHandle,
                                &v45,
                                v36);
          if ( CanSetSystemOwner >= 0 )
          {
            if ( Disposition == 1 )
            {
              v37 = *((_QWORD *)&v45 + 1);
              if ( !v42[1] && !v42[2]
                || (v38 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(
                            a1,
                            2,
                            *((_QWORD *)&v45 + 1)),
                    v19 = v38,
                    v38 >= 0) )
              {
                if ( v10 )
                  *v10 = 1;
LABEL_67:
                v40 = *a3;
                *((_QWORD *)&v45 + 1) = a3[1];
                *a3 = v45;
                a3[1] = v37;
                *(_QWORD *)&v45 = v40;
LABEL_77:
                v66 = 1;
                Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v57);
                Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v63);
                Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(KeyHandle);
                Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
                return v53;
              }
            }
            else
            {
              v39 = Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v57);
              v37 = *((_QWORD *)&v45 + 1);
              v38 = Windows::Rtl::SystemImplementation::IRtlRegistryProvider::EnsureSetSecurityIfRequired(
                      a1,
                      a2,
                      *((_QWORD *)&v45 + 1),
                      v39,
                      v21);
              v19 = v38;
              if ( v38 >= 0 )
              {
                if ( v10 )
                  *v10 = 2;
                goto LABEL_67;
              }
            }
            v53 = v38;
LABEL_80:
            Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v57);
            goto LABEL_81;
          }
LABEL_25:
          v53 = CanSetSystemOwner;
          Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v57);
          v19 = CanSetSystemOwner;
          goto LABEL_81;
        }
LABEL_68:
        if ( (v34 == -1073741772 || v34 == -1073741766) && (a2 & 1) != 0 )
        {
          if ( v10 )
            *v10 = 3;
          goto LABEL_77;
        }
        if ( v34 == -1073741790 && (a2 & 2) != 0 )
        {
          if ( v10 )
            *v10 = 4;
          goto LABEL_77;
        }
        Windows::WCP::Rtl::RtlTrace(
          (Windows::WCP::Rtl *)2,
          (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Failed to create key {key}, desired access {da} object attr"
                                                             "ibutes {oa} titleindex {ti} class {class} createoptions {co}",
          (const char *const)6,
          (unsigned __int64)"key",
          Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle,
          a3,
          "da",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess,
          &DesiredAccess,
          "oa",
          Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
          a5,
          "ti",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
          &TitleIndex,
          "class",
          Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING,
          Class,
          "co",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions,
          &CreateOptions);
        v48 = 5455;
        v46 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v49 = 0;
        v47 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
        v31 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v53,
                &v46,
                v34);
LABEL_79:
        v19 = v31;
        goto LABEL_80;
      }
      v44 = 0;
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                            (Windows::WCP::Implementation::Rtl *)&v44,
                            (struct _SECURITY_DESCRIPTOR **)v23);
      if ( CanSetSystemOwner < 0 )
        goto LABEL_25;
      v29 = v44;
LABEL_36:
      ObjectAttributes.SecurityDescriptor = v29;
      goto LABEL_37;
    }
    CanSetSystemOwner = Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(
                          a1,
                          25,
                          ObjectAttributes.RootDirectory,
                          ObjectAttributes.ObjectName,
                          v26,
                          0,
                          v21,
                          &v57,
                          0);
    if ( CanSetSystemOwner < 0 )
      goto LABEL_25;
    if ( (v60 & 0x400) != 0 )
    {
      if ( (DesiredAccess & 0x40000) == 0 )
      {
        v51[2] = 5283;
        v51[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v30 = (const char **)v51;
        v51[1] = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
        v51[3] = "DesiredAccess";
LABEL_29:
        v31 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                &v53,
                v30);
        goto LABEL_79;
      }
      v42[1] = 1;
    }
    if ( (v60 & 0x800) != 0 )
    {
      if ( (DesiredAccess & 0x1000000) == 0 )
      {
        v48 = 5292;
        v46 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v30 = &v46;
        v47 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
        v49 = "DesiredAccess";
        goto LABEL_29;
      }
      v42[2] = 1;
    }
    v29 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v57);
    goto LABEL_36;
  }
  v53 = IsUnacceptableKeyPrefix;
LABEL_81:
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v63);
  Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(KeyHandle);
  Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
  return v19;
}

```

## disassembly

```asm
0x18021b840  mov     [rsp-8+arg_8], rbx
0x18021b845  push    rbp
0x18021b846  push    rsi
0x18021b847  push    rdi
0x18021b848  push    r12
0x18021b84a  push    r13
0x18021b84c  push    r14
0x18021b84e  push    r15
0x18021b850  lea     rbp, [rsp-230h]
0x18021b858  sub     rsp, 3B0h
0x18021b85f  mov     rax, cs:__security_cookie
0x18021b866  xor     rax, rsp
0x18021b869  mov     [rbp+260h+var_40], rax
0x18021b870  mov     rdi, [rbp+260h+arg_48]
0x18021b877  xor     esi, esi
0x18021b879  mov     rbx, [rbp+260h+arg_30]
0x18021b880  xorps   xmm0, xmm0
0x18021b883  mov     r13, [rbp+260h+arg_20]
0x18021b88a  mov     r14, r8
0x18021b88d  mov     [rbp+260h+DesiredAccess], r9d
0x18021b891  mov     r12d, edx
0x18021b894  mov     [rbp+260h+var_2D8], rbx
0x18021b898  mov     r15, rcx
0x18021b89b  mov     [rbp+260h+var_228], esi
0x18021b89e  mov     [rbp+260h+KeyHandle], rsi
0x18021b8a2  mov     [rbp+260h+var_218], esi
0x18021b8a5  movdqu  [rbp+260h+var_2C8], xmm0
0x18021b8aa  test    rdi, rdi
0x18021b8ad  jz      short loc_18021B8B1
0x18021b8af  mov     [rdi], esi
0x18021b8b1  mov     [rbp+260h+var_198], esi
0x18021b8b7  mov     [rbp+260h+var_188], sil
0x18021b8be  mov     [rbp+260h+var_1B8], 1
0x18021b8c8  call    ?ShouldArm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0N@@Rtl@WCP@Windows@@SA_NPEAU_RTL_TRACING_FACILITY@234@@Z; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::ShouldArm(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x18021b8cd  lea     r10, ?RtlTraceFormat_PCULONG_AsRegKeyCreateOptions@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b8d4  lea     r11, aCo; "co"
0x18021b8db  lea     r8, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b8e2  lea     r9, aOa; "oa"
0x18021b8e9  lea     rdx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18021b8f0  lea     rcx, aWindowsRtlSyst_61; "Windows::Rtl::SystemImplementation::Dir"...
0x18021b8f7  test    al, al
0x18021b8f9  jz      loc_18021BA3E
0x18021b8ff  mov     [rsp+3E0h+var_2F0], rdi
0x18021b907  lea     rax, ?Format_PCULONG_AsSysCreateKeyDisposition@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysCreateKeyDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b90e  mov     [rsp+3E0h+var_2F8], rax
0x18021b916  lea     rax, aDisp; "disp"
0x18021b91d  mov     [rsp+3E0h+var_300], rax
0x18021b925  lea     rax, [rbp+260h+arg_38]
0x18021b92c  mov     [rsp+3E0h+var_308], rax
0x18021b934  lea     rax, ?RtlTraceFormat_PCUNICODE_STRING@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b93b  mov     [rsp+3E0h+var_310], r10
0x18021b943  mov     [rsp+3E0h+var_318], r11
0x18021b94b  mov     [rsp+3E0h+var_320], rbx
0x18021b953  mov     [rsp+3E0h+var_328], rax
0x18021b95b  lea     rax, aClass; "class"
0x18021b962  mov     [rsp+3E0h+var_330], rax
0x18021b96a  lea     rax, [rbp+260h+TitleIndex]
0x18021b971  mov     [rsp+3E0h+var_338], rax
0x18021b979  lea     rax, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b980  mov     [rsp+3E0h+var_340], rax
0x18021b988  lea     rax, aTi; "ti"
0x18021b98f  mov     [rsp+3E0h+var_348], rax
0x18021b997  lea     rax, [rbp+260h+DesiredAccess]
0x18021b99b  mov     [rsp+3E0h+var_350], r13
0x18021b9a3  mov     [rsp+3E0h+var_358], r8
0x18021b9ab  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b9b2  mov     [rsp+3E0h+var_360], r9
0x18021b9ba  mov     r9, r15
0x18021b9bd  mov     [rsp+3E0h+var_368], rax
0x18021b9c2  lea     rax, ?RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b9c9  mov     [rsp+3E0h+var_370], rax
0x18021b9ce  lea     rax, aDa; "da"
0x18021b9d5  mov     [rsp+3E0h+var_378], rax
0x18021b9da  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021b9e1  mov     [rsp+3E0h+var_380], r14
0x18021b9e6  mov     [rsp+3E0h+var_388], rax
0x18021b9eb  lea     rax, aKey; "key"
0x18021b9f2  mov     [rsp+3E0h+var_390], rax
0x18021b9f7  lea     rax, aKeyKeyDispDisp_0; "(key = {key}, disp = {disp})\n"
0x18021b9fe  mov     [rsp+3E0h+var_398], 7
0x18021ba07  mov     [rsp+3E0h+var_3A0], rax
0x18021ba0c  lea     rax, aKeyKeyDaDaOaOa; "(key = {key}, da = {da}, oa = {oa}, ti "...
0x18021ba13  mov     [rsp+3E0h+var_3A8], rax
0x18021ba18  lea     rax, aKeyKeyDaDaOaOa_0; "(key = {key}, da = {da}, oa = {oa}, ti "...
0x18021ba1f  mov     [rsp+3E0h+Disposition], rax
0x18021ba24  mov     qword ptr [rsp+3E0h+CreateOptions], rdx
0x18021ba29  lea     rdx, [rbp+260h+var_228]
0x18021ba2d  mov     [rsp+3E0h+Class], rcx
0x18021ba32  lea     rcx, [rbp+260h+var_1C0]
0x18021ba39  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x18021ba3e  mov     rdx, [r13+10h]; struct _UNICODE_STRING *
0x18021ba42  lea     r8, [rbp+260h+var_2E0]; bool *
0x18021ba46  mov     [rbp+260h+var_2E0], sil
0x18021ba4a  call    ?IsUnacceptableKeyPrefix@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@PEA_N@Z; Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(_UNICODE_STRING const &,bool *)
0x18021ba4f  mov     ebx, eax
0x18021ba51  test    eax, eax
0x18021ba53  jns     short loc_18021BA5D
0x18021ba55  mov     [rbp+260h+var_228], eax
0x18021ba58  jmp     loc_18021C064
0x18021ba5d  cmp     [rbp+260h+var_2E0], sil
0x18021ba61  jz      short loc_18021BA9F
0x18021ba63  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021ba6a  mov     [rbp+260h+var_288], 1485h
0x18021ba72  mov     [rbp+260h+var_298], rax
0x18021ba76  lea     rdx, [rbp+260h+var_298]
0x18021ba7a  lea     rax, aWindowsRtlSyst_61; "Windows::Rtl::SystemImplementation::Dir"...
0x18021ba81  mov     [rbp+260h+var_280], rsi
0x18021ba85  mov     r8d, 0C0000039h
0x18021ba8b  mov     [rbp+260h+var_290], rax
0x18021ba8f  lea     rcx, [rbp+260h+var_228]
0x18021ba93  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18021ba98  mov     ebx, eax
0x18021ba9a  jmp     loc_18021C064
0x18021ba9f  mov     rbx, [rbp+260h+arg_40]
0x18021baa6  test    rbx, rbx
0x18021baa9  jz      short loc_18021BAB0
0x18021baab  mov     rdx, [rbx]
0x18021baae  jmp     short loc_18021BAB3
0x18021bab0  mov     rdx, rsi
0x18021bab3  mov     rcx, r13
0x18021bab6  call    ?ValidateTransaction@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJAEAU_OBJECT_ATTRIBUTES@@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(_OBJECT_ATTRIBUTES &,void *)
0x18021babb  test    eax, eax
0x18021babd  jns     short loc_18021BAC4
0x18021babf  mov     [rbp+260h+var_228], eax
0x18021bac2  jmp     short loc_18021BA98
0x18021bac4  bts     [rbp+260h+DesiredAccess], 8
0x18021bac9  xorps   xmm0, xmm0
0x18021bacc  movdqa  [rbp+260h+var_200], xmm0
0x18021bad1  xorps   xmm1, xmm1
0x18021bad4  movdqa  [rbp+260h+var_1E0], xmm0
0x18021badc  movups  xmm0, xmmword ptr [r13+0]
0x18021bae1  mov     [rbp+260h+var_1F0], rsi
0x18021bae5  movdqa  [rbp+260h+var_1D0], xmm1
0x18021baed  movups  xmm1, xmmword ptr [r13+10h]
0x18021baf2  mov     [rbp+260h+var_1E8], sil
0x18021baf6  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x18021bafa  mov     [rbp+260h+var_1E6], si
0x18021bafe  movups  xmm0, xmmword ptr [r13+20h]
0x18021bb03  mov     [rbp+260h+var_2E0+1], sil
0x18021bb07  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm1
0x18021bb0b  mov     [rbp+260h+var_2E0+2], sil
0x18021bb0f  movq    rax, xmm0
0x18021bb14  movups  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x18021bb18  test    rax, rax
0x18021bb1b  jnz     short loc_18021BB6C
0x18021bb1d  test    r12b, 4
0x18021bb21  jnz     short loc_18021BB6C
0x18021bb23  test    byte ptr [rbp+260h+arg_38], 4
0x18021bb2a  jz      short loc_18021BB30
0x18021bb2c  mov     al, 1
0x18021bb2e  jmp     short loc_18021BB48
0x18021bb30  lea     rcx, [rbp+260h+var_2E0]; this
0x18021bb34  mov     [rbp+260h+var_2E0], sil
0x18021bb38  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18021bb3d  mov     esi, eax
0x18021bb3f  test    eax, eax
0x18021bb41  js      short loc_18021BBA4
0x18021bb43  mov     al, [rbp+260h+var_2E0]
0x18021bb46  xor     esi, esi
0x18021bb48  test    al, al
0x18021bb4a  jz      loc_18021BC5E
0x18021bb50  lea     rcx, [rbp+260h+var_2D0]; this
0x18021bb54  mov     [rbp+260h+var_2D0], rsi
0x18021bb58  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18021bb5d  mov     esi, eax
0x18021bb5f  test    eax, eax
0x18021bb61  js      short loc_18021BBA4
0x18021bb63  mov     rax, [rbp+260h+var_2D0]
0x18021bb67  jmp     loc_18021BC5A
0x18021bb6c  mov     r9, [rbp+260h+ObjectAttributes.ObjectName]
0x18021bb70  lea     rcx, [rbp+260h+var_200]
0x18021bb74  mov     r8, [rbp+260h+ObjectAttributes.RootDirectory]
0x18021bb78  mov     edx, 19h
0x18021bb7d  mov     [rsp+3E0h+var_3A0], rsi
0x18021bb82  mov     [rsp+3E0h+var_3A8], rcx
0x18021bb87  mov     rcx, r15
0x18021bb8a  mov     [rsp+3E0h+Disposition], rbx
0x18021bb8f  mov     qword ptr [rsp+3E0h+CreateOptions], rsi
0x18021bb94  mov     [rsp+3E0h+Class], rax
0x18021bb99  call    ?CalculateSecurityForCreate@IRtlObjectProvider@SystemImplementation@Rtl@Windows@@QEAAJW4CalculateInheritedSecurityFlags@1234@PEAXAEBU_UNICODE_STRING@@11UKtmTransactionInfoPointer@34@PEAVSecurityDescriptor@34@4@Z; Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateInheritedSecurityFlags,void *,_UNICODE_STRING const &,void *,void *,Windows::Rtl::KtmTransactionInfoPointer,Windows::Rtl::SecurityDescriptor *,Windows::Rtl::SecurityDescriptor *)
0x18021bb9e  mov     esi, eax
0x18021bba0  test    eax, eax
0x18021bba2  jns     short loc_18021BBB7
0x18021bba4  lea     rcx, [rbp+260h+var_200]
0x18021bba8  mov     [rbp+260h+var_228], esi
0x18021bbab  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x18021bbb0  mov     ebx, esi
0x18021bbb2  jmp     loc_18021C064
0x18021bbb7  mov     eax, 400h
0x18021bbbc  test    [rbp+260h+var_1E6], ax
0x18021bbc0  jz      short loc_18021BC0A
0x18021bbc2  test    [rbp+260h+DesiredAccess], 40000h
0x18021bbc9  jnz     short loc_18021BC06
0x18021bbcb  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021bbd2  mov     [rbp+260h+var_268], 14A3h
0x18021bbda  mov     [rbp+260h+var_278], rax
0x18021bbde  lea     rdx, [rbp+260h+var_278]
0x18021bbe2  lea     rax, aWindowsRtlSyst_61; "Windows::Rtl::SystemImplementation::Dir"...
0x18021bbe9  mov     [rbp+260h+var_270], rax
0x18021bbed  lea     rax, aDesiredaccess; "DesiredAccess"
0x18021bbf4  mov     [rbp+260h+var_260], rax
0x18021bbf8  lea     rcx, [rbp+260h+var_228]
0x18021bbfc  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18021bc01  jmp     loc_18021C059
0x18021bc06  mov     [rbp+260h+var_2E0+1], 1
0x18021bc0a  mov     eax, 800h
0x18021bc0f  test    [rbp+260h+var_1E6], ax
0x18021bc13  jz      short loc_18021BC51
0x18021bc15  test    [rbp+260h+DesiredAccess], 1000000h
0x18021bc1c  jnz     short loc_18021BC4D
0x18021bc1e  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021bc25  mov     [rbp+260h+var_2A8], 14ACh
0x18021bc2d  mov     [rbp+260h+var_2B8], rax
0x18021bc31  lea     rdx, [rbp+260h+var_2B8]
0x18021bc35  lea     rax, aWindowsRtlSyst_61; "Windows::Rtl::SystemImplementation::Dir"...
0x18021bc3c  mov     [rbp+260h+var_2B0], rax
0x18021bc40  lea     rax, aDesiredaccess; "DesiredAccess"
0x18021bc47  mov     [rbp+260h+var_2A0], rax
0x18021bc4b  jmp     short loc_18021BBF8
0x18021bc4d  mov     [rbp+260h+var_2E0+2], 1
0x18021bc51  lea     rcx, [rbp+260h+var_200]; this
0x18021bc55  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18021bc5a  mov     [rbp+260h+ObjectAttributes.SecurityDescriptor], rax
0x18021bc5e  mov     rax, [rbp+260h+ObjectAttributes.RootDirectory]
0x18021bc62  test    rax, rax
0x18021bc65  jz      short loc_18021BC6E
0x18021bc67  mov     rax, [rax]
0x18021bc6a  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x18021bc6e  mov     r9d, [rbp+260h+TitleIndex]; TitleIndex
0x18021bc75  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18021bc79  mov     edx, [rbp+260h+DesiredAccess]; DesiredAccess
0x18021bc7c  test    rbx, rbx
0x18021bc7f  jnz     short loc_18021BCAF
0x18021bc81  mov     eax, [rbp+260h+arg_38]
0x18021bc87  lea     rcx, [rbp+260h+var_218]
0x18021bc8b  mov     [rsp+3E0h+Disposition], rcx; Disposition
0x18021bc90  lea     rcx, [rbp+260h+KeyHandle]; KeyHandle
0x18021bc94  mov     [rsp+3E0h+CreateOptions], eax; CreateOptions
0x18021bc98  mov     rax, [rbp+260h+var_2D8]
0x18021bc9c  mov     [rsp+3E0h+Class], rax; Class
0x18021bca1  call    cs:__imp_NtCreateKey
0x18021bca8  nop     dword ptr [rax+rax+00h]
0x18021bcad  jmp     short loc_18021BCE3
0x18021bcaf  mov     ecx, [rbp+260h+arg_38]
0x18021bcb5  lea     rax, [rbp+260h+var_218]
0x18021bcb9  mov     [rsp+3E0h+var_3A8], rax
0x18021bcbe  mov     rax, [rbx]
0x18021bcc1  mov     [rsp+3E0h+Disposition], rax
0x18021bcc6  mov     rax, [rbp+260h+var_2D8]
0x18021bcca  mov     [rsp+3E0h+CreateOptions], ecx
0x18021bcce  lea     rcx, [rbp+260h+KeyHandle]
0x18021bcd2  mov     [rsp+3E0h+Class], rax
0x18021bcd7  call    cs:__imp_NtCreateKeyTransacted
0x18021bcde  nop     dword ptr [rax+rax+00h]
0x18021bce3  mov     esi, eax
0x18021bce5  cmp     eax, 0C000009Ah
0x18021bcea  jnz     loc_18021BDDC
0x18021bcf0  mov     dword ptr [rbp+260h+var_2D0], 0
0x18021bcf7  mov     [rbp+260h+var_2E0], 1
0x18021bcfb  lea     rdx, [rbp+260h+var_2E0]; unsigned int *
0x18021bcff  lea     rcx, [rbp+260h+var_2D0]; this
0x18021bd03  call    ?DelayForInsufficientResources@SystemImplementation@Rtl@Windows@@YAJPEAKPEA_N@Z; Windows::Rtl::SystemImplementation::DelayForInsufficientResources(ulong *,bool *)
0x18021bd08  mov     esi, eax
0x18021bd0a  test    eax, eax
0x18021bd0c  js      loc_18021BBA4
0x18021bd12  mov     r9d, [rbp+260h+TitleIndex]; TitleIndex
0x18021bd19  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18021bd1d  mov     edx, [rbp+260h+DesiredAccess]; DesiredAccess
0x18021bd20  test    rbx, rbx
0x18021bd23  jnz     short loc_18021BD53
0x18021bd25  mov     eax, [rbp+260h+arg_38]
0x18021bd2b  lea     rcx, [rbp+260h+var_218]
0x18021bd2f  mov     [rsp+3E0h+Disposition], rcx; Disposition
0x18021bd34  lea     rcx, [rbp+260h+KeyHandle]; KeyHandle
0x18021bd38  mov     [rsp+3E0h+CreateOptions], eax; CreateOptions
0x18021bd3c  mov     rax, [rbp+260h+var_2D8]
0x18021bd40  mov     [rsp+3E0h+Class], rax; Class
0x18021bd45  call    cs:__imp_NtCreateKey
0x18021bd4c  nop     dword ptr [rax+rax+00h]
0x18021bd51  jmp     short loc_18021BD87
0x18021bd53  mov     ecx, [rbp+260h+arg_38]
0x18021bd59  lea     rax, [rbp+260h+var_218]
0x18021bd5d  mov     [rsp+3E0h+var_3A8], rax
0x18021bd62  mov     rax, [rbx]
0x18021bd65  mov     [rsp+3E0h+Disposition], rax
0x18021bd6a  mov     rax, [rbp+260h+var_2D8]
0x18021bd6e  mov     [rsp+3E0h+CreateOptions], ecx
0x18021bd72  lea     rcx, [rbp+260h+KeyHandle]
0x18021bd76  mov     [rsp+3E0h+Class], rax
0x18021bd7b  call    cs:__imp_NtCreateKeyTransacted
0x18021bd82  nop     dword ptr [rax+rax+00h]
0x18021bd87  cmp     [rbp+260h+var_2E0], 0
0x18021bd8b  mov     esi, eax
0x18021bd8d  jz      short loc_18021BD9A
0x18021bd8f  cmp     eax, 0C000009Ah
0x18021bd94  jz      loc_18021BCFB
0x18021bd9a  test    esi, esi
0x18021bd9c  js      loc_18021BEB6
0x18021bda2  lea     rax, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021bda9  mov     [rsp+3E0h+Disposition], r13
  ... truncated ...
```
