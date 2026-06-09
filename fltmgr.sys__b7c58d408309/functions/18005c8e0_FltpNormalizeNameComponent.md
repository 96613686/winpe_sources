# FltpNormalizeNameComponent

- ea: `0x18005c8e0`
- end: `0x18005ceeb`
- name: `FltpNormalizeNameComponent`
- size: `1547`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005c7c0`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x18000eb80`
- `0x1800148b0`
- `0x180014cf0`
- `0x18005c8e0`
- `0x18005cf00`
- `0x18005d850`
- `0x18005df50`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18005ce8e`
- `ntoskrnl!KeBugCheckEx` at `0x18005ce8e`
- `ntoskrnl!ObfDereferenceObject` at `0x18005cec1`
- `ntoskrnl!ObfDereferenceObject` at `0x18005cec1`
- `ntoskrnl!ZwClose` at `0x18005cde0`
- `ntoskrnl!ZwClose` at `0x18005ced7`
- `ntoskrnl!ZwClose` at `0x18005cde0`
- `ntoskrnl!ZwClose` at `0x18005ced7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005cdb0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005cdb0`
- `ntoskrnl!IoFileObjectType` at `0x18005cd8d`
- `ntoskrnl!IoCreateFileEx` at `0x18005cd45`
- `ntoskrnl!IoCreateFileEx` at `0x180079589`
- `ntoskrnl!IoCreateFileEx` at `0x18005cd45`
- `ntoskrnl!IoCreateFileEx` at `0x180079589`
- `ntoskrnl!IoGetSilo` at `0x18005cc96`
- `ntoskrnl!IoGetSilo` at `0x18005cc96`
- `ntoskrnl!PsGetHostSilo` at `0x18005ccab`
- `ntoskrnl!PsGetHostSilo` at `0x18005ccab`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x18007951b`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x18007951b`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x18005c990`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x18005c990`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x18005caa6`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x18005caa6`

## pseudocode

```c
__int64 __fastcall FltpNormalizeNameComponent(__int64 a1)
{
  void **v1; // r15
  __int64 v3; // r13
  _DWORD *v4; // rdi
  struct _FILE_OBJECT **v5; // r14
  unsigned int ECP; // esi
  int v7; // ecx
  struct _FILE_OBJECT *v8; // r8
  _QWORD *v9; // rdx
  int InitializeNameGenerationContext; // eax
  int FileNameInformation; // r14d
  int v12; // eax
  _QWORD *v13; // rsi
  __int64 v14; // rax
  _DWORD *v15; // r12
  volatile signed __int32 *v16; // rcx
  ULONG_PTR v17; // r8
  _QWORD *v19; // r9
  __int64 v20; // rax
  int v21; // r8d
  void *v22; // rdx
  void *v23; // rcx
  int v24; // r8d
  int v25; // eax
  __int64 v26; // rcx
  char v27; // al
  void *v28; // rcx
  int IoStatusBlocka; // [rsp+20h] [rbp-A9h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-A9h]
  PUNICODE_STRING FileName; // [rsp+48h] [rbp-81h]
  struct _IO_STATUS_BLOCK v32; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-39h] BYREF
  __int64 Silo; // [rsp+B0h] [rbp-19h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-11h] BYREF
  bool v36; // [rsp+130h] [rbp+67h]
  __int64 v37; // [rsp+138h] [rbp+6Fh] BYREF
  PVOID Entry; // [rsp+140h] [rbp+77h] BYREF

  v1 = (void **)(a1 + 232);
  v3 = 0;
  v37 = 0;
  LOWORD(Silo) = 0;
  memset(&ObjectAttributes, 0, 44);
  v36 = 0;
  v32 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  if ( *(_QWORD *)(a1 + 232) )
  {
    v4 = (_DWORD *)(a1 + 40);
    v5 = (struct _FILE_OBJECT **)(a1 + 240);
  }
  else
  {
    v19 = *(_QWORD **)(a1 + 8);
    DriverContext.Size = 40;
    DriverContext.DeviceObjectHint = *(PVOID *)a1;
    Silo = 1;
    if ( v19 )
    {
      v20 = *(_QWORD *)(a1 + 16);
      if ( v20 )
      {
        v21 = *(_DWORD *)(a1 + 108);
        v22 = 0;
        v23 = *(void **)(v20 + 72);
        v24 = 2 * (v21 & 0x1000000 | 0x800000);
      }
      else
      {
        v24 = 16777218;
        v23 = 0;
        v20 = 0;
        v22 = v19;
      }
      ECP = TargetedIOCtrlGenerateECP((int)&v37, 0, v24, v19[13], v23, v20, v22, &DriverContext.ExtraCreateParameter, 0);
      v25 = FltpDbgStatus(ECP);
      v3 = v37;
      if ( v25 < 0 )
      {
        v4 = (_DWORD *)(a1 + 40);
        goto LABEL_20;
      }
      v36 = (*(_BYTE *)(v37 + 6) & 8) != 0;
    }
    v26 = *(_QWORD *)(a1 + 64);
    DriverContext.TxnParameters = *(PTXN_PARAMETER_BLOCK *)(a1 + 72);
    Silo = IoGetSilo(v26);
    if ( !Silo )
      Silo = PsGetHostSilo();
    v4 = (_DWORD *)(a1 + 40);
    v27 = 2 * *(_DWORD *)(a1 + 40);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = ~v27 & 0x40 | 0x200;
    ObjectAttributes.ObjectName = *(PUNICODE_STRING *)(a1 + 112);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ECP = IoCreateFileEx(
            v1,
            0x100001u,
            &ObjectAttributes,
            &v32,
            0,
            0x90u,
            7u,
            1u,
            0x4021u,
            0,
            0,
            CreateFileTypeNone,
            0,
            0x800u,
            &DriverContext);
    if ( ECP == -1073741191 )
    {
      if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(LODWORD(v32.Information)) )
        goto LABEL_20;
      ECP = IoCreateFileEx(
              v1,
              0x100001u,
              &ObjectAttributes,
              &v32,
              0,
              0x90u,
              7u,
              1u,
              0x204021u,
              0,
              0,
              CreateFileTypeNone,
              0,
              0x800u,
              &DriverContext);
    }
    if ( (int)FltpDbgStatus(ECP) < 0 )
      goto LABEL_20;
    v5 = (struct _FILE_OBJECT **)(a1 + 240);
    ECP = ObReferenceObjectByHandle(*v1, 0, (POBJECT_TYPE)IoFileObjectType, 0, (PVOID *)(a1 + 240), 0);
    if ( (int)FltpDbgStatus(ECP) < 0 )
    {
      ZwClose(*v1);
      *v1 = 0;
      goto LABEL_20;
    }
  }
  LODWORD(v37) = ZwQueryDirectoryFile(
                   *v1,
                   0,
                   0,
                   0,
                   &v32,
                   *(PVOID *)(a1 + 208),
                   *(_DWORD *)(a1 + 216),
                   FileNamesInformation,
                   1u,
                   (PUNICODE_STRING)(a1 + 176),
                   1u);
  ECP = v37;
  FltpDbgStatus(v37);
  v7 = *v4;
  if ( (*v4 & 0xA001) == 1 )
  {
    v8 = *v5;
    v9 = *(_QWORD **)(a1 + 16);
    IoStatusBlocka = *(_DWORD *)(a1 + 108) & 0x100FF00 | 1;
    Entry = 0;
    InitializeNameGenerationContext = FltpAllocateInitializeNameGenerationContext(
                                        (PVOID **)&Entry,
                                        v9,
                                        v8,
                                        0,
                                        IoStatusBlocka,
                                        0,
                                        0,
                                        0,
                                        0,
                                        (__int64)FileName,
                                        v7 & 0x400 | 0x4001u);
    IoStatusBlock = 0;
    FileNameInformation = InitializeNameGenerationContext;
    v12 = FltpDbgStatus(InitializeNameGenerationContext);
    v13 = Entry;
    if ( v12 < 0
      || (FileNameInformation = FltpGetFileNameInformation((__int64)Entry), (int)FltpDbgStatus(FileNameInformation) < 0) )
    {
      v15 = v4;
    }
    else
    {
      v14 = v13[15];
      if ( RtlCompareUnicodeStrings(
             *(PCWCH *)(v14 + 16),
             (unsigned __int64)*(unsigned __int16 *)(v14 + 8) >> 1,
             *(PCWCH *)(*(_QWORD *)(a1 + 112) + 8LL),
             ((unsigned __int64)**(unsigned __int16 **)(a1 + 112) >> 1)
           - (*(_WORD *)(*(_QWORD *)(v14 + 16) + 2 * ((unsigned __int64)*(unsigned __int16 *)(v14 + 8) >> 1) - 2) != 92),
             0) )
      {
        *(_QWORD *)(a1 + 224) = v13[15];
        v13[15] = 0;
        v15 = (_DWORD *)(a1 + 40);
      }
      else
      {
        v15 = v4;
      }
      *v4 |= 0x8000u;
    }
    if ( v13 )
    {
      *v15 |= v13[5] & 0x3000;
      v16 = (volatile signed __int32 *)v13[15];
      Entry = (PVOID)v16;
      if ( v16 )
      {
        if ( (byte_1800404C3 & 8) != 0 )
        {
          McTemplateU0sp_EtwWriteTransfer(
            (__int64)v16,
            (__int64)NameCacheSup_c6404,
            "FltReleaseFileNameInformation",
            v16,
            IoStatusBlock);
          v16 = (volatile signed __int32 *)Entry;
        }
        v17 = (ULONG_PTR)(v16 - 20);
        if ( _InterlockedExchangeAdd(v16 + 30, 0xFFFFFFFF) <= 1 )
        {
          if ( (*(_DWORD *)(v17 + 72) & 0x1E000) != 0 )
            KeBugCheckEx(0xF5u, 0x68u, v17, (ULONG_PTR)v16, 0);
          if ( (byte_1800404C3 & 8) != 0 )
            McTemplateU0s_EtwWriteTransfer((__int64)v16, (__int64)NameCacheSup_c6433, "FltReleaseFileNameInformation");
          FltpFreeFileNameInformation();
          v15 = (_DWORD *)(a1 + 40);
        }
        if ( (byte_1800404C3 & 8) != 0 )
          McTemplateU0s_EtwWriteTransfer((__int64)v16, (__int64)NameCacheSup_c6442, "FltReleaseFileNameInformation");
      }
      FltpFreeNameGenerationContext(v13);
      if ( (*v15 & 0x2000) != 0 )
        FileNameInformation = 0;
    }
    ECP = FileNameInformation;
    if ( (int)FltpDbgStatus(FileNameInformation) >= 0 )
      ECP = v37;
  }
LABEL_20:
  if ( v3 )
  {
    if ( (int)FltpDbgStatus(ECP) < 0 )
      v3 = 0;
    CleanupTargetedIo(v3, &DriverContext.ExtraCreateParameter, v36);
  }
  if ( *v1 && (*v4 & 0x100) == 0 )
  {
    ObfDereferenceObject(*(PVOID *)(a1 + 240));
    v28 = *v1;
    *(_QWORD *)(a1 + 240) = 0;
    ZwClose(v28);
    *v1 = 0;
  }
  return ECP;
}

```

## disassembly

```asm
0x18005c8e0  mov     [rsp-8+arg_18], rbx
0x18005c8e5  push    rbp
0x18005c8e6  push    rsi
0x18005c8e7  push    rdi
0x18005c8e8  push    r12
0x18005c8ea  push    r13
0x18005c8ec  push    r14
0x18005c8ee  push    r15
0x18005c8f0  lea     rbp, [rsp-27h]
0x18005c8f5  sub     rsp, 0F0h
0x18005c8fc  xorps   xmm0, xmm0
0x18005c8ff  lea     r15, [rcx+0E8h]
0x18005c906  xor     eax, eax
0x18005c908  xor     r12d, r12d
0x18005c90b  mov     rbx, rcx
0x18005c90e  mov     r13d, r12d
0x18005c911  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005c915  mov     [rbp+57h+arg_8], r12
0x18005c919  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005c91d  mov     word ptr [rbp+57h+var_70], ax
0x18005c921  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005c925  mov     [rbp+57h+arg_0], al
0x18005c928  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18005c92c  movups  xmmword ptr [rbp+57h+var_90.Size], xmm0
0x18005c930  movups  xmmword ptr [rbp+57h+var_90.DeviceObjectHint], xmm0
0x18005c934  cmp     [r15], rax
0x18005c937  jz      loc_18005CBE0
0x18005c93d  lea     rdi, [rcx+28h]
0x18005c941  lea     r14, [rcx+0F0h]
0x18005c948  mov     rcx, [r15]; FileHandle
0x18005c94b  lea     rax, [rbx+0B0h]
0x18005c952  mov     [rsp+120h+RestartScan], 1; RestartScan
0x18005c957  xor     r9d, r9d; ApcContext
0x18005c95a  mov     [rsp+120h+FileName], rax; FileName
0x18005c95f  xor     r8d, r8d; ApcRoutine
0x18005c962  mov     eax, [rbx+0D8h]
0x18005c968  xor     edx, edx; Event
0x18005c96a  mov     [rsp+120h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18005c96f  mov     [rsp+120h+FileInformationClass], 0Ch; FileInformationClass
0x18005c977  mov     [rsp+120h+Length], eax; Length
0x18005c97b  mov     rax, [rbx+0D0h]
0x18005c982  mov     [rsp+120h+FileInformation], rax; FileInformation
0x18005c987  lea     rax, [rbp+57h+var_A0]
0x18005c98b  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x18005c990  call    cs:__imp_ZwQueryDirectoryFile
0x18005c997  nop     dword ptr [rax+rax+00h]
0x18005c99c  mov     r8d, 14F5h
0x18005c9a2  mov     [rsp+120h+IoStatusBlock], r12
0x18005c9a7  mov     ecx, eax
0x18005c9a9  mov     dword ptr [rbp+57h+arg_8], eax
0x18005c9ac  mov     r9d, 0C000000Fh
0x18005c9b2  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005c9b9  mov     esi, eax
0x18005c9bb  call    FltpDbgStatus
0x18005c9c0  mov     ecx, [rdi]
0x18005c9c2  mov     eax, ecx
0x18005c9c4  and     eax, 0A001h
0x18005c9c9  cmp     eax, 1
0x18005c9cc  jnz     loc_18005CB66
0x18005c9d2  mov     eax, [rbx+6Ch]
0x18005c9d5  and     ecx, 400h
0x18005c9db  mov     r8, [r14]
0x18005c9de  or      ecx, 4001h
0x18005c9e4  mov     rdx, [rbx+10h]
0x18005c9e8  and     eax, 100FF00h
0x18005c9ed  mov     dword ptr [rsp+120h+RestartScan], ecx
0x18005c9f1  or      eax, 1
0x18005c9f4  mov     dword ptr [rsp+120h+ReturnSingleEntry], r12d
0x18005c9f9  lea     rcx, [rbp+57h+Entry]
0x18005c9fd  mov     qword ptr [rsp+120h+FileInformationClass], r12
0x18005ca02  xor     r9d, r9d
0x18005ca05  mov     qword ptr [rsp+120h+Length], r12
0x18005ca0a  mov     [rsp+120h+FileInformation], r12
0x18005ca0f  mov     dword ptr [rsp+120h+IoStatusBlock], eax
0x18005ca13  mov     [rbp+57h+Entry], r12
0x18005ca17  call    FltpAllocateInitializeNameGenerationContext
0x18005ca1c  mov     r8d, 151Eh
0x18005ca22  mov     [rsp+120h+IoStatusBlock], r12
0x18005ca27  mov     r9d, 0C000009Ah
0x18005ca2d  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ca34  mov     ecx, eax
0x18005ca36  mov     r14d, eax
0x18005ca39  call    FltpDbgStatus
0x18005ca3e  mov     rsi, [rbp+57h+Entry]
0x18005ca42  test    eax, eax
0x18005ca44  js      loc_18005CBD8
0x18005ca4a  mov     rcx, rsi
0x18005ca4d  call    FltpGetFileNameInformation
0x18005ca52  mov     r8d, 1526h
0x18005ca58  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ca5f  xor     r9d, r9d
0x18005ca62  mov     ecx, eax
0x18005ca64  mov     r14d, eax
0x18005ca67  call    FltpDbgStatus
0x18005ca6c  test    eax, eax
0x18005ca6e  js      loc_18005CBD8
0x18005ca74  mov     rax, [rsi+78h]
0x18005ca78  mov     r8, [rbx+70h]
0x18005ca7c  mov     byte ptr [rsp+120h+IoStatusBlock], r12b; CaseInSensitive
0x18005ca81  movzx   edx, word ptr [rax+8]
0x18005ca85  mov     rcx, [rax+10h]; String1
0x18005ca89  mov     rax, r12
0x18005ca8c  movzx   r9d, word ptr [r8]
0x18005ca90  mov     r8, [r8+8]; String2
0x18005ca94  shr     rdx, 1; String1Length
0x18005ca97  cmp     word ptr [rcx+rdx*2-2], 5Ch ; '\'
0x18005ca9d  setnz   al
0x18005caa0  shr     r9, 1
0x18005caa3  sub     r9, rax; String2Length
0x18005caa6  call    cs:__imp_RtlCompareUnicodeStrings
0x18005caad  nop     dword ptr [rax+rax+00h]
0x18005cab2  test    eax, eax
0x18005cab4  jz      loc_18005CB9F
0x18005caba  mov     rax, [rsi+78h]
0x18005cabe  mov     [rbx+0E0h], rax
0x18005cac5  mov     [rsi+78h], r12
0x18005cac9  lea     r12, [rbx+28h]
0x18005cacd  or      dword ptr [rdi], 8000h
0x18005cad3  test    rsi, rsi
0x18005cad6  jz      loc_18005CBD0
0x18005cadc  mov     eax, [rsi+28h]
0x18005cadf  and     eax, 3000h
0x18005cae4  or      [r12], eax
0x18005cae8  mov     rcx, [rsi+78h]
0x18005caec  mov     [rbp+57h+Entry], rcx
0x18005caf0  test    rcx, rcx
0x18005caf3  jz      short loc_18005CB2A
0x18005caf5  test    cs:byte_1800404C3, 8
0x18005cafc  jnz     loc_18005CE9B
0x18005cb02  lea     r8, [rcx-50h]; BugCheckParameter2
0x18005cb06  mov     eax, 0FFFFFFFFh
0x18005cb0b  lock xadd [r8+0C8h], eax
0x18005cb14  sub     eax, 1
0x18005cb17  jle     loc_18005CBA7
0x18005cb1d  test    cs:byte_1800404C3, 8
0x18005cb24  jnz     loc_18005CE44
0x18005cb2a  mov     rcx, rsi; Entry
0x18005cb2d  call    FltpFreeNameGenerationContext
0x18005cb32  test    dword ptr [r12], 2000h
0x18005cb3a  mov     r12d, 0
0x18005cb40  cmovnz  r14d, r12d
0x18005cb44  mov     r8d, 158Dh
0x18005cb4a  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005cb51  xor     r9d, r9d
0x18005cb54  mov     ecx, r14d
0x18005cb57  call    FltpDbgStatus
0x18005cb5c  mov     esi, r14d
0x18005cb5f  test    eax, eax
0x18005cb61  js      short loc_18005CB66
0x18005cb63  mov     esi, dword ptr [rbp+57h+arg_8]
0x18005cb66  test    r13, r13
0x18005cb69  jnz     loc_18005CDF4
0x18005cb6f  cmp     qword ptr [r15], 0
0x18005cb73  jz      short loc_18005CB81
0x18005cb75  test    dword ptr [rdi], 100h
0x18005cb7b  jz      loc_18005CEBA
0x18005cb81  mov     rbx, [rsp+120h+arg_18]
0x18005cb89  mov     eax, esi
0x18005cb8b  add     rsp, 0F0h
0x18005cb92  pop     r15
0x18005cb94  pop     r14
0x18005cb96  pop     r13
0x18005cb98  pop     r12
0x18005cb9a  pop     rdi
0x18005cb9b  pop     rsi
0x18005cb9c  pop     rbp
0x18005cb9d  retn
0x18005cb9f  mov     r12, rdi
0x18005cba2  jmp     loc_18005CACD
0x18005cba7  test    dword ptr [r8+48h], 1E000h
0x18005cbaf  jnz     loc_18005CE78
0x18005cbb5  test    cs:byte_1800404C3, 8
0x18005cbbc  jnz     loc_18005CE5C
0x18005cbc2  call    FltpFreeFileNameInformation
0x18005cbc7  lea     r12, [rbx+28h]
0x18005cbcb  jmp     loc_18005CB1D
0x18005cbd0  xor     r12d, r12d
0x18005cbd3  jmp     loc_18005CB44
0x18005cbd8  mov     r12, rdi
0x18005cbdb  jmp     loc_18005CAD3
0x18005cbe0  mov     r9, [rcx+8]
0x18005cbe4  mov     eax, 28h ; '('
0x18005cbe9  mov     [rbp+57h+var_90.Size], ax
0x18005cbed  mov     rax, [rcx]
0x18005cbf0  mov     [rbp+57h+var_90.DeviceObjectHint], rax
0x18005cbf4  mov     [rbp+57h+var_70], 1
0x18005cbfc  test    r9, r9
0x18005cbff  jz      loc_18005CC8A
0x18005cc05  mov     rax, [rcx+10h]
0x18005cc09  test    rax, rax
0x18005cc0c  jz      loc_18005CE30
0x18005cc12  mov     r8d, [rcx+6Ch]
0x18005cc16  mov     rdx, r12
0x18005cc19  mov     rcx, [rax+48h]
0x18005cc1d  and     r8d, 1000000h
0x18005cc24  bts     r8d, 17h
0x18005cc29  add     r8d, r8d; int
0x18005cc2c  mov     r9, [r9+68h]; int
0x18005cc30  lea     r10, [rbp+57h+var_90.ExtraCreateParameter]
0x18005cc34  mov     qword ptr [rsp+120h+ReturnSingleEntry], r12; __int64
0x18005cc39  mov     qword ptr [rsp+120h+FileInformationClass], r10; EcpList
0x18005cc3e  mov     qword ptr [rsp+120h+Length], rdx; PVOID
0x18005cc43  xor     edx, edx; int
0x18005cc45  mov     [rsp+120h+FileInformation], rax; __int64
0x18005cc4a  mov     [rsp+120h+IoStatusBlock], rcx; FltObject
0x18005cc4f  lea     rcx, [rbp+57h+arg_8]; int
0x18005cc53  call    TargetedIOCtrlGenerateECP
0x18005cc58  mov     r8d, 144Dh
0x18005cc5e  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005cc65  xor     r9d, r9d
0x18005cc68  mov     ecx, eax
0x18005cc6a  mov     esi, eax
0x18005cc6c  call    FltpDbgStatus
0x18005cc71  mov     r13, [rbp+57h+arg_8]
0x18005cc75  test    eax, eax
0x18005cc77  js      loc_18005CE27
0x18005cc7d  movzx   eax, byte ptr [r13+6]
0x18005cc82  shr     al, 3
0x18005cc85  and     al, 1
0x18005cc87  mov     [rbp+57h+arg_0], al
0x18005cc8a  mov     rax, [rbx+48h]
0x18005cc8e  mov     rcx, [rbx+40h]
0x18005cc92  mov     [rbp+57h+var_90.TxnParameters], rax
0x18005cc96  call    cs:__imp_IoGetSilo
0x18005cc9d  nop     dword ptr [rax+rax+00h]
0x18005cca2  mov     [rbp+57h+var_70], rax
0x18005cca6  test    rax, rax
0x18005cca9  jnz     short loc_18005CCBB
0x18005ccab  call    cs:__imp_PsGetHostSilo
0x18005ccb2  nop     dword ptr [rax+rax+00h]
0x18005ccb7  mov     [rbp+57h+var_70], rax
0x18005ccbb  mov     eax, [rbx+28h]
0x18005ccbe  lea     rdi, [rbx+28h]
0x18005ccc2  add     eax, eax
0x18005ccc4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005cccb  not     eax
0x18005cccd  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18005ccd1  and     eax, 40h
0x18005ccd4  lea     r9, [rbp+57h+var_A0]; IoStatusBlock
0x18005ccd8  bts     eax, 9
0x18005ccdc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005cce0  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x18005cce3  xorps   xmm0, xmm0
0x18005cce6  mov     rax, [rbx+70h]
0x18005ccea  mov     edx, 100001h; DesiredAccess
0x18005ccef  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005ccf3  mov     rcx, r15; FileHandle
0x18005ccf6  lea     rax, [rbp+57h+var_90]
0x18005ccfa  mov     [rsp+120h+DriverContext], rax; DriverContext
0x18005ccff  mov     [rsp+120h+Options], 800h; Options
0x18005cd07  mov     [rsp+120h+InternalParameters], r12; InternalParameters
0x18005cd0c  mov     [rsp+120h+CreateFileType], r12d; CreateFileType
0x18005cd11  mov     dword ptr [rsp+120h+RestartScan], r12d; EaLength
0x18005cd16  mov     [rsp+120h+FileName], r12; EaBuffer
0x18005cd1b  mov     dword ptr [rsp+120h+ReturnSingleEntry], 4021h; CreateOptions
0x18005cd23  mov     [rsp+120h+FileInformationClass], 1; Disposition
0x18005cd2b  mov     [rsp+120h+Length], 7; ShareAccess
0x18005cd33  mov     dword ptr [rsp+120h+FileInformation], 90h; FileAttributes
0x18005cd3b  mov     [rsp+120h+IoStatusBlock], r12; AllocationSize
0x18005cd40  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005cd45  call    cs:__imp_IoCreateFileEx
0x18005cd4c  nop     dword ptr [rax+rax+00h]
0x18005cd51  mov     esi, eax
0x18005cd53  cmp     eax, 0C0000279h
0x18005cd58  jz      loc_180079518
0x18005cd5e  mov     r8d, 14B5h
0x18005cd64  mov     [rsp+120h+FileInformation], r12
0x18005cd69  mov     r9d, 0C0000368h
0x18005cd6f  mov     dword ptr [rsp+120h+IoStatusBlock], 0C000003Ah
0x18005cd77  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005cd7e  mov     ecx, esi
0x18005cd80  call    FltpDbgStatus
0x18005cd85  test    eax, eax
0x18005cd87  js      loc_18005CB66
0x18005cd8d  mov     r8, cs:__imp_IoFileObjectType
0x18005cd94  lea     r14, [rbx+0F0h]
0x18005cd9b  mov     rcx, [r15]; Handle
0x18005cd9e  xor     r9d, r9d; AccessMode
0x18005cda1  mov     [rsp+120h+FileInformation], r12; HandleInformation
0x18005cda6  xor     edx, edx; DesiredAccess
0x18005cda8  mov     [rsp+120h+IoStatusBlock], r14; Object
0x18005cdad  mov     r8, [r8]; ObjectType
0x18005cdb0  call    cs:__imp_ObReferenceObjectByHandle
0x18005cdb7  nop     dword ptr [rax+rax+00h]
0x18005cdbc  mov     r8d, 14D0h
0x18005cdc2  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005cdc9  mov     ecx, eax
0x18005cdcb  xor     r9d, r9d
0x18005cdce  mov     esi, eax
0x18005cdd0  call    FltpDbgStatus
0x18005cdd5  test    eax, eax
0x18005cdd7  jns     loc_18005C948
0x18005cddd  mov     rcx, [r15]; Handle
0x18005cde0  call    cs:__imp_ZwClose
0x18005cde7  nop     dword ptr [rax+rax+00h]
0x18005cdec  mov     [r15], r12
0x18005cdef  jmp     loc_18005CB66
0x18005cdf4  xor     r9d, r9d
0x18005cdf7  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005cdfe  mov     r8d, 1598h
  ... truncated ...
```
