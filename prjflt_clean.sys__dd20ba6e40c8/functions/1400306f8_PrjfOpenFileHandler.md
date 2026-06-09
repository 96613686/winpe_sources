# PrjfOpenFileHandler

- ea: `0x1400306f8`
- end: `0x1400311aa`
- name: `PrjfOpenFileHandler`
- size: `2738`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d008`
- `0x14000d128`
- `0x14000d5e8`
- `0x14000d754`
- `0x140021f8c`
- `0x1400306f8`
- `0x140033878`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003114e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003114e`
- `ntoskrnl!KeDelayExecutionThread` at `0x140030e10`
- `ntoskrnl!KeDelayExecutionThread` at `0x140030e10`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140030e8f`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140030e8f`
- `ntoskrnl!ObfReferenceObject` at `0x140030f0e`
- `ntoskrnl!ObfReferenceObject` at `0x140030f0e`
- `ntoskrnl!ExAllocatePool2` at `0x140030b58`
- `ntoskrnl!ExAllocatePool2` at `0x140030b58`
- `ntoskrnl!IoGetCurrentProcess` at `0x140030a2c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140030a2c`
- `ntoskrnl!ExUuidCreate` at `0x140030d8d`
- `ntoskrnl!ExUuidCreate` at `0x140030d8d`
- `FLTMGR!FltCreateFileEx` at `0x140030cd9`
- `FLTMGR!FltCreateFileEx` at `0x140030cd9`
- `FLTMGR!FltClose` at `0x140031163`
- `FLTMGR!FltClose` at `0x140031163`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140030e71`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140030e71`
- `FLTMGR!FltReleaseResource` at `0x140030ea6`
- `FLTMGR!FltReleaseResource` at `0x140030f1d`
- `FLTMGR!FltReleaseResource` at `0x140030ea6`
- `FLTMGR!FltReleaseResource` at `0x140030f1d`

## pseudocode

```c
__int64 __fastcall PrjfOpenFileHandler(PFLT_INSTANCE Instance, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r9
  __int64 v5; // rdi
  NTSTATUS v7; // ebx
  unsigned int v8; // ecx
  int v9; // eax
  _QWORD *UnionContextByVirtualizationInstanceInfo; // rax
  _QWORD *v11; // r12
  struct _KPROCESS *v12; // rbx
  _WORD *v13; // rsi
  _WORD *v14; // rax
  unsigned __int64 i; // rcx
  _WORD *v16; // rax
  unsigned __int16 v17; // r14
  __int16 v18; // bx
  __int64 v19; // r12
  int v20; // eax
  NTSTATUS v21; // eax
  char *v22; // rbx
  struct _ERESOURCE *v23; // r13
  _OWORD *inserted; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  _OWORD *v28; // r12
  void *v29; // rcx
  __int64 v30; // rcx
  char v31; // di
  ACCESS_MASK DesiredAccess; // [rsp+20h] [rbp-E0h]
  __int16 IoStatusBlock; // [rsp+30h] [rbp-D0h]
  __int16 IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  char ShareAccess; // [rsp+48h] [rbp-B8h]
  char ShareAccessa; // [rsp+48h] [rbp-B8h]
  char CreateDisposition; // [rsp+50h] [rbp-B0h]
  char v39; // [rsp+80h] [rbp-80h]
  unsigned __int8 NewElement[7]; // [rsp+81h] [rbp-7Fh] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  PVOID v42; // [rsp+98h] [rbp-68h]
  union _LARGE_INTEGER Interval[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK v46; // [rsp+E8h] [rbp-18h] BYREF
  UUID Uuid; // [rsp+F8h] [rbp-8h] BYREF
  void *FileHandle[2]; // [rsp+108h] [rbp+8h] BYREF

  v44 = a4;
  v4 = *(unsigned int *)a2;
  v42 = 0;
  v39 = 0;
  v5 = a2;
  NewElement[0] = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v46 = 0;
  Uuid = 0;
  *(_OWORD *)FileHandle = 0;
  if ( (unsigned int)v4 > (unsigned int)a3 )
  {
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = 27;
    IoStatusBlock = 23;
    goto LABEL_5;
  }
  if ( (unsigned int)v4 < 0x62 )
  {
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDdd(526, a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 8));
    goto LABEL_93;
  }
  v8 = *(_DWORD *)(a2 + 92);
  if ( v8 < 0x62 )
  {
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = 42;
    IoStatusBlock = 25;
    goto LABEL_5;
  }
  a2 = v8 + *(unsigned __int16 *)(a2 + 96);
  if ( (unsigned int)a2 < v8 )
  {
    v7 = -1073741675;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        26,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        51,
        149);
    goto LABEL_93;
  }
  if ( (unsigned int)v4 < (unsigned int)a2 )
  {
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = 58;
    IoStatusBlock = 27;
    goto LABEL_5;
  }
  v9 = *(_DWORD *)(v5 + 88);
  if ( (v9 & 0x3FFFFFFF) != 0 )
  {
    v7 = -1073741790;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        28,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        69,
        v9);
    goto LABEL_93;
  }
  UnionContextByVirtualizationInstanceInfo = (_QWORD *)PrjfGetUnionContextByVirtualizationInstanceInfo(v5 + 8, Instance);
  v42 = UnionContextByVirtualizationInstanceInfo;
  v11 = UnionContextByVirtualizationInstanceInfo;
  if ( !UnionContextByVirtualizationInstanceInfo )
  {
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = 80;
    IoStatusBlock = 29;
    goto LABEL_5;
  }
  v12 = (struct _KPROCESS *)UnionContextByVirtualizationInstanceInfo[4];
  if ( IoGetCurrentProcess() != v12 )
  {
    v7 = -1073741790;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = 92;
    IoStatusBlock = 30;
    goto LABEL_5;
  }
  v13 = (_WORD *)(v5 + *(unsigned int *)(v5 + 92));
  if ( !v13 )
  {
    v7 = -1073741811;
LABEL_87:
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    CreateDisposition = 13;
    ShareAccessa = 108;
    IoStatusBlocka = 31;
    goto LABEL_51;
  }
  v14 = (_WORD *)(v5 + *(unsigned int *)(v5 + 92));
  for ( i = (unsigned __int64)*(unsigned __int16 *)(v5 + 96) >> 1; i; --i )
  {
    if ( !*v14 )
      break;
    ++v14;
  }
  a2 = i == 0 ? 0xC000000D : 0;
  if ( !i )
  {
    v7 = -1073741811;
    goto LABEL_87;
  }
  a2 = 0x7FFF;
  *(_OWORD *)&Interval[0].LowPart = 0;
  v16 = v13;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --a2;
  }
  while ( a2 );
  v7 = a2 == 0 ? 0xC000000D : 0;
  if ( !a2 )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    a2 = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    CreateDisposition = v7;
    ShareAccessa = 116;
    IoStatusBlocka = 32;
LABEL_51:
    WPP_RECORDER_AND_TRACE_SF_sDL(
      526,
      a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      IoStatusBlocka,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      ShareAccessa,
      CreateDisposition);
    goto LABEL_93;
  }
  v17 = *((_WORD *)v11 + 20);
  LOWORD(a2) = 2 * a2;
  v18 = -2 - a2;
  if ( (unsigned __int16)(-2 - a2 + v17) < v17 )
  {
    WORD1(P[0]) = -1;
    v7 = -1073741675;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    CreateDisposition = -107;
    ShareAccessa = 125;
    IoStatusBlocka = 33;
    goto LABEL_51;
  }
  if ( (unsigned __int16)(v17 - a2) < 2u )
  {
    WORD1(P[0]) = -1;
    v7 = -1073741675;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    CreateDisposition = -107;
    ShareAccessa = -123;
    IoStatusBlocka = 34;
    goto LABEL_51;
  }
  v19 = v11[6];
  WORD1(P[0]) = v17 - a2;
  P[1] = (PVOID)ExAllocatePool2(256, (unsigned __int16)(v17 - a2), 1953319504);
  if ( !P[1] )
  {
    v7 = -1073741670;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = -112;
    IoStatusBlock = 35;
    goto LABEL_5;
  }
  v20 = PrjfRelPathToFullPath(P, v17, v19, v13, v18);
  v7 = v20;
  if ( v20 < 0 )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    CreateDisposition = v20;
    ShareAccessa = -100;
    IoStatusBlocka = 36;
    goto LABEL_51;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  DesiredAccess = *(_DWORD *)(v5 + 88);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1600;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = FltCreateFileEx(
         Globals,
         Instance,
         &FileHandle[1],
         (PFILE_OBJECT *)FileHandle,
         DesiredAccess,
         &ObjectAttributes,
         &v46,
         0,
         0,
         7u,
         1u,
         0x20u,
         0,
         0,
         1u);
  if ( v7 < 0 )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        37,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        201,
        v7,
        (__int64)P);
    goto LABEL_93;
  }
  v39 = 1;
  while ( 1 )
  {
    v21 = ExUuidCreate(&Uuid);
    v7 = v21;
    if ( v21 != -1073741267 )
      break;
    Interval[0].QuadPart = 0;
    if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE9(xmmword_14001A3D0) & 0x40;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        782,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        14,
        38,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        225);
    }
    Interval[0].QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, Interval);
  }
  if ( v21 < 0 )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    CreateDisposition = v21;
    ShareAccessa = -24;
    IoStatusBlocka = 39;
    goto LABEL_51;
  }
  v22 = (char *)v42;
  v23 = (struct _ERESOURCE *)((char *)v42 + 96);
  FltAcquireResourceExclusive((PERESOURCE)((char *)v42 + 96));
  inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v22 + 200), &Uuid, 0x20u, NewElement);
  v28 = inserted;
  if ( !inserted )
  {
    FltReleaseResource(v23);
    v7 = -1073741670;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    ShareAccess = 6;
    IoStatusBlock = 40;
LABEL_5:
    WPP_RECORDER_AND_TRACE_SF_sD(
      526,
      a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      IoStatusBlock,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      ShareAccess);
LABEL_93:
    v31 = v39;
    goto LABEL_94;
  }
  v7 = 0;
  if ( NewElement[0] )
  {
    v29 = FileHandle[0];
    if ( FileHandle[0] != *((void **)inserted + 2) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(FileHandle[0], v25, v26, v27);
      v29 = FileHandle[0];
    }
    ObfReferenceObject(v29);
  }
  FltReleaseResource(v23);
  v31 = 0;
  if ( !NewElement[0] )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, a2, a3, v4);
  *(_OWORD *)(v44 + 4) = *v28;
LABEL_94:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x746D4A50u);
  if ( v31 )
    FltClose(FileHandle[1]);
  if ( v42 )
    PrjfReleaseUnionContext((char *)v42, a2, a3, v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400306f8  mov     [rsp-8+arg_10], rbx
0x1400306fd  push    rbp
0x1400306fe  push    rsi
0x1400306ff  push    rdi
0x140030700  push    r12
0x140030702  push    r13
0x140030704  push    r14
0x140030706  push    r15
0x140030708  lea     rbp, [rsp-20h]
0x14003070d  sub     rsp, 120h
0x140030714  mov     rax, cs:__security_cookie
0x14003071b  xor     rax, rsp
0x14003071e  mov     [rbp+50h+var_38], rax
0x140030722  xorps   xmm1, xmm1
0x140030725  mov     [rbp+50h+var_A0], r9
0x140030729  mov     r9d, [rdx]
0x14003072c  xor     r10d, r10d
0x14003072f  mov     [rbp+50h+var_B8], r10
0x140030733  xorps   xmm0, xmm0
0x140030736  mov     [rbp+50h+var_D0], r10b
0x14003073a  mov     rdi, rdx
0x14003073d  mov     [rbp+50h+NewElement], r10b
0x140030741  mov     r13, rcx
0x140030744  movups  xmmword ptr [rbp+50h+P], xmm0
0x140030748  movups  xmmword ptr [rbp+50h+var_98.Length], xmm1
0x14003074c  movups  xmmword ptr [rbp+50h+var_98.ObjectName], xmm1
0x140030750  movups  xmmword ptr [rbp+50h+var_98.SecurityDescriptor], xmm1
0x140030754  movups  xmmword ptr [rbp+50h+var_68], xmm0
0x140030758  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm1
0x14003075c  movups  xmmword ptr [rbp+50h+FileHandle], xmm1
0x140030760  cmp     r9d, r8d
0x140030763  jbe     short loc_1400307DE
0x140030765  mov     ebx, 0C000000Dh
0x14003076a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140030770  lea     rdi, WPP_RECORDER_INITIALIZED
0x140030777  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003077e  setnz   r8b
0x140030782  and     dl, 40h
0x140030785  jnz     short loc_140030790
0x140030787  test    r8b, r8b
0x14003078a  jz      loc_14003113C
0x140030790  mov     dword ptr [rsp+150h+ShareAccess], 31Bh
0x140030798  lea     rsi, aOnecoreBaseFsG_5
0x14003079f  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x1400307a4  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400307ab  mov     [rsp+150h+AllocationSize], r14
0x1400307b0  mov     word ptr [rsp+150h+IoStatusBlock], 17h
0x1400307b7  mov     dword ptr [rsp+150h+ObjectAttributes], 0Eh
0x1400307bf  mov     byte ptr [rsp+150h+DesiredAccess], 2
0x1400307c4  mov     r9, cs:WPP_GLOBAL_Control
0x1400307cb  mov     ecx, 20Eh
0x1400307d0  mov     r9, [r9+40h]
0x1400307d4  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400307d9  jmp     loc_14003113C
0x1400307de  cmp     r9d, 62h ; 'b'
0x1400307e2  jnb     loc_140030869
0x1400307e8  mov     ebx, 0C000000Dh
0x1400307ed  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400307f3  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400307fa  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030801  setnz   r8b
0x140030805  and     dl, 40h
0x140030808  jnz     short loc_140030813
0x14003080a  test    r8b, r8b
0x14003080d  jz      loc_14003113C
0x140030813  mov     [rsp+150h+CreateOptions], 62h ; 'b'
0x14003081b  lea     rsi, aOnecoreBaseFsG_5
0x140030822  mov     dword ptr [rsp+150h+CreateDisposition], r9d
0x140030827  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003082e  mov     r9, cs:WPP_GLOBAL_Control
0x140030835  mov     ecx, 20Eh
0x14003083a  mov     dword ptr [rsp+150h+ShareAccess], 323h
0x140030842  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x140030847  mov     [rsp+150h+AllocationSize], r14
0x14003084c  mov     r9, [r9+40h]
0x140030850  mov     word ptr [rsp+150h+IoStatusBlock], 18h
0x140030857  mov     dword ptr [rsp+150h+ObjectAttributes], 0Eh
0x14003085f  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x140030864  jmp     loc_14003113C
0x140030869  mov     ecx, [rdx+5Ch]
0x14003086c  cmp     ecx, 62h ; 'b'
0x14003086f  jnb     short loc_1400308C8
0x140030871  mov     ebx, 0C000000Dh
0x140030876  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003087c  lea     rdi, WPP_RECORDER_INITIALIZED
0x140030883  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003088a  setnz   r8b
0x14003088e  and     dl, 40h
0x140030891  jnz     short loc_14003089C
0x140030893  test    r8b, r8b
0x140030896  jz      loc_14003113C
0x14003089c  mov     dword ptr [rsp+150h+ShareAccess], 32Ah
0x1400308a4  lea     rsi, aOnecoreBaseFsG_5
0x1400308ab  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x1400308b0  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400308b7  mov     [rsp+150h+AllocationSize], r14
0x1400308bc  mov     word ptr [rsp+150h+IoStatusBlock], 19h
0x1400308c3  jmp     loc_1400307B7
0x1400308c8  movzx   edx, word ptr [rdx+60h]
0x1400308cc  add     edx, ecx
0x1400308ce  cmp     edx, ecx
0x1400308d0  jb      loc_1400310C6
0x1400308d6  cmp     r9d, edx
0x1400308d9  jnb     short loc_140030932
0x1400308db  mov     ebx, 0C000000Dh
0x1400308e0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400308e6  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400308ed  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400308f4  setnz   r8b
0x1400308f8  and     dl, 40h
0x1400308fb  jnz     short loc_140030906
0x1400308fd  test    r8b, r8b
0x140030900  jz      loc_14003113C
0x140030906  mov     dword ptr [rsp+150h+ShareAccess], 33Ah
0x14003090e  lea     rsi, aOnecoreBaseFsG_5
0x140030915  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x14003091a  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030921  mov     [rsp+150h+AllocationSize], r14
0x140030926  mov     word ptr [rsp+150h+IoStatusBlock], 1Bh
0x14003092d  jmp     loc_1400307B7
0x140030932  mov     eax, [rdi+58h]
0x140030935  test    eax, 3FFFFFFFh
0x14003093a  jz      short loc_1400309B9
0x14003093c  mov     ebx, 0C0000022h
0x140030941  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140030947  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003094e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030955  setnz   r8b
0x140030959  and     dl, 40h
0x14003095c  jnz     short loc_140030967
0x14003095e  test    r8b, r8b
0x140030961  jz      loc_14003113C
0x140030967  mov     r9, cs:WPP_GLOBAL_Control
0x14003096e  lea     rsi, aOnecoreBaseFsG_5
0x140030975  mov     dword ptr [rsp+150h+CreateDisposition], eax
0x140030979  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030980  mov     dword ptr [rsp+150h+ShareAccess], 345h
0x140030988  mov     ecx, 20Eh
0x14003098d  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x140030992  mov     r9, [r9+40h]
0x140030996  mov     [rsp+150h+AllocationSize], r14
0x14003099b  mov     word ptr [rsp+150h+IoStatusBlock], 1Ch
0x1400309a2  mov     dword ptr [rsp+150h+ObjectAttributes], 0Eh
0x1400309aa  mov     byte ptr [rsp+150h+DesiredAccess], 2
0x1400309af  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400309b4  jmp     loc_14003113C
0x1400309b9  lea     rcx, [rdi+8]
0x1400309bd  mov     rdx, r13
0x1400309c0  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x1400309c5  mov     [rbp+50h+var_B8], rax
0x1400309c9  mov     r12, rax
0x1400309cc  test    rax, rax
0x1400309cf  jnz     short loc_140030A28
0x1400309d1  mov     ebx, 0C000000Dh
0x1400309d6  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400309dc  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400309e3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400309ea  setnz   r8b
0x1400309ee  and     dl, 40h
0x1400309f1  jnz     short loc_1400309FC
0x1400309f3  test    r8b, r8b
0x1400309f6  jz      loc_14003113C
0x1400309fc  mov     dword ptr [rsp+150h+ShareAccess], 350h
0x140030a04  lea     rsi, aOnecoreBaseFsG_5
0x140030a0b  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x140030a10  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030a17  mov     [rsp+150h+AllocationSize], r14
0x140030a1c  mov     word ptr [rsp+150h+IoStatusBlock], 1Dh
0x140030a23  jmp     loc_1400307B7
0x140030a28  mov     rbx, [rax+20h]
0x140030a2c  call    cs:__imp_IoGetCurrentProcess
0x140030a33  nop     dword ptr [rax+rax+00h]
0x140030a38  cmp     rax, rbx
0x140030a3b  jz      short loc_140030A94
0x140030a3d  mov     ebx, 0C0000022h
0x140030a42  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140030a48  lea     rdi, WPP_RECORDER_INITIALIZED
0x140030a4f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030a56  setnz   r8b
0x140030a5a  and     dl, 40h
0x140030a5d  jnz     short loc_140030A68
0x140030a5f  test    r8b, r8b
0x140030a62  jz      loc_14003113C
0x140030a68  mov     dword ptr [rsp+150h+ShareAccess], 35Ch
0x140030a70  lea     rsi, aOnecoreBaseFsG_5
0x140030a77  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x140030a7c  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030a83  mov     [rsp+150h+AllocationSize], r14
0x140030a88  mov     word ptr [rsp+150h+IoStatusBlock], 1Eh
0x140030a8f  jmp     loc_1400307B7
0x140030a94  mov     esi, [rdi+5Ch]
0x140030a97  xor     r10d, r10d
0x140030a9a  mov     r15d, 2
0x140030aa0  add     rsi, rdi
0x140030aa3  jz      loc_14003106B
0x140030aa9  movzx   ecx, word ptr [rdi+60h]
0x140030aad  mov     rax, rsi
0x140030ab0  shr     rcx, 1
0x140030ab3  jz      short loc_140030AC4
0x140030ab5  cmp     [rax], r10w
0x140030ab9  jz      short loc_140030AC4
0x140030abb  add     rax, r15
0x140030abe  sub     rcx, 1
0x140030ac2  jnz     short loc_140030AB5
0x140030ac4  mov     rax, rcx
0x140030ac7  mov     ebx, 0C000000Dh
0x140030acc  neg     rax
0x140030acf  sbb     edx, edx
0x140030ad1  not     edx
0x140030ad3  and     edx, ebx
0x140030ad5  test    rcx, rcx
0x140030ad8  jnz     short loc_140030AE1
0x140030ada  mov     ebx, edx
0x140030adc  jmp     loc_140031070
0x140030ae1  xorps   xmm0, xmm0
0x140030ae4  mov     edx, 7FFFh
0x140030ae9  movups  xmmword ptr [rbp+50h+Interval], xmm0
0x140030aed  mov     rax, rsi
0x140030af0  cmp     [rax], r10w
0x140030af4  jz      short loc_140030AFF
0x140030af6  add     rax, r15
0x140030af9  sub     rdx, 1
0x140030afd  jnz     short loc_140030AF0
0x140030aff  mov     rax, rdx
0x140030b02  neg     rax
0x140030b05  sbb     ecx, ecx
0x140030b07  not     ecx
0x140030b09  and     ebx, ecx
0x140030b0b  test    rdx, rdx
0x140030b0e  jz      loc_140031015
0x140030b14  movzx   r14d, word ptr [r12+28h]
0x140030b1a  add     dx, dx
0x140030b1d  mov     ebx, 0FFFEh
0x140030b22  sub     bx, dx
0x140030b25  lea     eax, [rbx+r14]
0x140030b29  cmp     ax, r14w
0x140030b2d  jb      loc_140030FAF
0x140030b33  add     ax, r15w
0x140030b37  cmp     ax, r15w
0x140030b3b  jb      loc_140030F49
0x140030b41  mov     r12, [r12+30h]
0x140030b46  mov     ecx, 100h
0x140030b4b  movzx   edx, ax
0x140030b4e  mov     r8d, 746D4A50h
0x140030b54  mov     word ptr [rbp+50h+P+2], ax
0x140030b58  call    cs:__imp_ExAllocatePool2
0x140030b5f  nop     dword ptr [rax+rax+00h]
0x140030b64  mov     [rbp+50h+P+8], rax
0x140030b68  test    rax, rax
0x140030b6b  jnz     short loc_140030BD1
0x140030b6d  mov     ebx, 0C000009Ah
0x140030b72  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140030b78  lea     rdi, WPP_RECORDER_INITIALIZED
0x140030b7f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030b86  setnz   r8b
0x140030b8a  and     dl, 40h
0x140030b8d  jnz     short loc_140030B98
0x140030b8f  test    r8b, r8b
0x140030b92  jz      loc_14003113C
0x140030b98  mov     dword ptr [rsp+150h+ShareAccess], 390h
0x140030ba0  lea     rsi, aOnecoreBaseFsG_5
0x140030ba7  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x140030bac  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030bb3  mov     [rsp+150h+AllocationSize], r14
0x140030bb8  mov     word ptr [rsp+150h+IoStatusBlock], 23h ; '#'
0x140030bbf  mov     dword ptr [rsp+150h+ObjectAttributes], 0Eh
0x140030bc7  mov     byte ptr [rsp+150h+DesiredAccess], r15b
0x140030bcc  jmp     loc_1400307C4
0x140030bd1  mov     r9, rsi
0x140030bd4  mov     word ptr [rsp+150h+DesiredAccess], bx
0x140030bd9  mov     r8, r12
0x140030bdc  lea     rcx, [rbp+50h+P]
0x140030be0  movzx   edx, r14w
0x140030be4  call    PrjfRelPathToFullPath
0x140030be9  xor     r10d, r10d
0x140030bec  mov     ebx, eax
0x140030bee  test    eax, eax
0x140030bf0  jns     short loc_140030C55
0x140030bf2  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140030bf8  lea     rdi, WPP_RECORDER_INITIALIZED
0x140030bff  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030c06  setnz   r8b
0x140030c0a  and     dl, 40h
0x140030c0d  jnz     short loc_140030C18
0x140030c0f  test    r8b, r8b
0x140030c12  jz      loc_14003113C
0x140030c18  mov     dword ptr [rsp+150h+CreateDisposition], eax
0x140030c1c  lea     rsi, aOnecoreBaseFsG_5
0x140030c23  mov     dword ptr [rsp+150h+ShareAccess], 39Ch
0x140030c2b  lea     r14, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140030c32  mov     qword ptr [rsp+150h+FileAttributes], rsi
0x140030c37  mov     [rsp+150h+AllocationSize], r14
0x140030c3c  mov     word ptr [rsp+150h+IoStatusBlock], 24h ; '$'
0x140030c43  mov     dword ptr [rsp+150h+ObjectAttributes], 0Eh
0x140030c4b  mov     byte ptr [rsp+150h+DesiredAccess], r15b
0x140030c50  jmp     loc_140031127
0x140030c55  mov     rcx, cs:Globals; Filter
0x140030c5c  lea     rax, [rbp+50h+P]
0x140030c60  mov     [rsp+150h+Flags], 1; Flags
0x140030c68  lea     r9, [rbp+50h+FileHandle]; FileObject
  ... truncated ...
```
