# PrjfCreateTombstone

- ea: `0x1400422ec`
- end: `0x140042650`
- name: `PrjfCreateTombstone`
- size: `868`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _UNICODE_STRING *, char)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140009d20`
- `0x14002c3f8`
- `0x140041e28`
- `0x140042eac`
- `0x140043d88`

## callees

- `0x14000be80`
- `0x14000d128`
- `0x1400422ec`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x14004251b`
- `ntoskrnl!PsGetHostSilo` at `0x14004251b`
- `ntoskrnl!ObfDereferenceObject` at `0x140042631`
- `ntoskrnl!ObfDereferenceObject` at `0x140042631`
- `FLTMGR!FltIsEcpAcknowledged` at `0x1400425e1`
- `FLTMGR!FltIsEcpAcknowledged` at `0x1400425e1`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140042607`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140042607`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400424f5`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400424f5`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140042425`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140042425`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140042362`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140042362`
- `FLTMGR!FltCreateFileEx2` at `0x1400425c4`
- `FLTMGR!FltCreateFileEx2` at `0x1400425c4`
- `FLTMGR!FltClose` at `0x14004261c`
- `FLTMGR!FltClose` at `0x14004261c`

## pseudocode

```c
__int64 __fastcall PrjfCreateTombstone(PFLT_INSTANCE Instance, struct _UNICODE_STRING *a2, char a3)
{
  ULONG CreateOptions; // esi
  int v6; // edx
  NTSTATUS v7; // ebx
  int v8; // r8d
  int v9; // edx
  int v10; // r8d
  PECP_LIST EcpList; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-68h] BYREF
  __int64 HostSilo; // [rsp+B8h] [rbp-48h]
  __int128 v17; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+178h] [rbp+78h] BYREF

  EcpList = 0;
  EcpContext = 0;
  v18 = 0;
  LOWORD(HostSilo) = 0;
  FileHandle = 0;
  FileObject = 0;
  CreateOptions = (a3 != 0) + 2162728;
  v17 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v7 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  if ( v7 >= 0 )
  {
    v7 = FltAllocateExtraCreateParameterFromLookasideList(
           Globals,
           &GUID_ECP_ATOMIC_CREATE,
           0x58u,
           0,
           0,
           qword_14001A5C0,
           &EcpContext);
    if ( v7 >= 0 )
    {
      WORD2(v17) = 0;
      LODWORD(v17) = -1610612702;
      memset(EcpContext, 0, 0x58u);
      *(_WORD *)EcpContext = 88;
      *((_WORD *)EcpContext + 1) = 2;
      *((_WORD *)EcpContext + 2) = 0;
      *((_WORD *)EcpContext + 3) = 8;
      *((_QWORD *)EcpContext + 1) = &v17;
      FltInsertExtraCreateParameter(Globals, EcpList, EcpContext);
      HostSilo = 1;
      memset(&DriverContext, 0, sizeof(DriverContext));
      DriverContext.Size = 40;
      HostSilo = PsGetHostSilo();
      DriverContext.ExtraCreateParameter = EcpList;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = a2;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = FltCreateFileEx2(
             Globals,
             Instance,
             &FileHandle,
             &FileObject,
             0x40000000u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             6u,
             0,
             2u,
             CreateOptions,
             0,
             0,
             0,
             &DriverContext);
      if ( v7 >= 0 && !FltIsEcpAcknowledged(Globals, EcpContext) )
        v7 = -1073741823;
    }
    else if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        20,
        (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
        118,
        v7);
    }
  }
  else if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = BYTE2(xmmword_14001A3D0) & 8;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      531,
      v6,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      19,
      19,
      (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
      104,
      v7);
  }
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400422ec  push    rbp
0x1400422ee  push    rbx
0x1400422ef  push    rsi
0x1400422f0  push    rdi
0x1400422f1  push    r14
0x1400422f3  push    r15
0x1400422f5  lea     rbp, [rsp-28h]
0x1400422fa  sub     rsp, 128h
0x140042301  xorps   xmm0, xmm0
0x140042304  mov     [rbp+50h+EcpList], 0
0x14004230c  xor     eax, eax
0x14004230e  mov     [rbp+50h+arg_18], 0
0x140042316  neg     r8b
0x140042319  mov     [rbp+50h+var_80], rax
0x14004231d  mov     r14, rdx
0x140042320  mov     word ptr [rbp+50h+var_98], ax
0x140042324  sbb     esi, esi
0x140042326  mov     [rbp+50h+FileHandle], rax
0x14004232a  mov     r15, rcx
0x14004232d  mov     [rbp+50h+FileObject], rax
0x140042331  mov     rcx, cs:Globals; Filter
0x140042338  lea     r8, [rbp+50h+EcpList]; EcpList
0x14004233c  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x140042340  neg     esi
0x140042342  xor     edx, edx; Flags
0x140042344  add     esi, 210028h
0x14004234a  movups  [rbp+50h+var_90], xmm0
0x14004234e  movups  xmmword ptr [rbp+50h+var_B8.Size], xmm0
0x140042352  movups  xmmword ptr [rbp+50h+var_B8.DeviceObjectHint], xmm0
0x140042356  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14004235a  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14004235e  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x140042362  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140042369  nop     dword ptr [rax+rax+00h]
0x14004236e  mov     ebx, eax
0x140042370  test    eax, eax
0x140042372  jns     short loc_1400423EF
0x140042374  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14004237a  lea     rax, WPP_RECORDER_INITIALIZED
0x140042381  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140042388  mov     ecx, 8
0x14004238d  setnz   r8b
0x140042391  and     dl, cl
0x140042393  jnz     short loc_14004239E
0x140042395  test    r8b, r8b
0x140042398  jz      loc_1400425F7
0x14004239e  mov     [rsp+150h+CreateDisposition], ebx
0x1400423a2  lea     r9, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400423a9  mov     [rsp+150h+ShareAccess], 268h
0x1400423b1  mov     eax, 13h
0x1400423b6  mov     qword ptr [rsp+150h+FileAttributes], r9
0x1400423bb  lea     r9, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x1400423c2  mov     [rsp+150h+AllocationSize], r9
0x1400423c7  mov     word ptr [rsp+150h+EcpContext], ax
0x1400423cc  mov     dword ptr [rsp+150h+LookasideList], eax
0x1400423d0  mov     r9, cs:WPP_GLOBAL_Control
0x1400423d7  mov     ecx, 213h
0x1400423dc  mov     byte ptr [rsp+150h+CleanupCallback], 2
0x1400423e1  mov     r9, [r9+40h]
0x1400423e5  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400423ea  jmp     loc_1400425F7
0x1400423ef  mov     rcx, cs:Globals; Filter
0x1400423f6  lea     rax, [rbp+50h+arg_18]
0x1400423fa  mov     [rsp+150h+EcpContext], rax; EcpContext
0x1400423ff  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x140042406  xor     r9d, r9d; Flags
0x140042409  lea     rax, qword_14001A5C0
0x140042410  mov     [rsp+150h+LookasideList], rax; LookasideList
0x140042415  mov     [rsp+150h+CleanupCallback], 0; CleanupCallback
0x14004241e  lea     edi, [r9+58h]
0x140042422  mov     r8d, edi; SizeOfContext
0x140042425  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14004242c  nop     dword ptr [rax+rax+00h]
0x140042431  mov     ebx, eax
0x140042433  test    eax, eax
0x140042435  jns     short loc_140042497
0x140042437  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14004243d  lea     rax, WPP_RECORDER_INITIALIZED
0x140042444  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004244b  lea     ecx, [rdi-50h]
0x14004244e  setnz   r8b
0x140042452  and     dl, cl
0x140042454  jnz     short loc_14004245F
0x140042456  test    r8b, r8b
0x140042459  jz      loc_1400425F7
0x14004245f  mov     [rsp+150h+CreateDisposition], ebx
0x140042463  lea     r9, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004246a  mov     [rsp+150h+ShareAccess], 276h
0x140042472  mov     qword ptr [rsp+150h+FileAttributes], r9
0x140042477  lea     r9, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x14004247e  mov     [rsp+150h+AllocationSize], r9
0x140042483  mov     word ptr [rsp+150h+EcpContext], 14h
0x14004248a  mov     dword ptr [rsp+150h+LookasideList], 13h
0x140042492  jmp     loc_1400423D0
0x140042497  mov     rcx, [rbp+50h+arg_18]; void *
0x14004249b  xor     eax, eax
0x14004249d  mov     r8, rdi; Size
0x1400424a0  mov     word ptr [rbp+50h+var_90+4], ax
0x1400424a4  xor     edx, edx; Val
0x1400424a6  mov     dword ptr [rbp+50h+var_90], 0A0000022h
0x1400424ad  call    memset
0x1400424b2  mov     rax, [rbp+50h+arg_18]
0x1400424b6  xor     ecx, ecx
0x1400424b8  mov     [rax], di
0x1400424bb  mov     edi, 2
0x1400424c0  mov     rax, [rbp+50h+arg_18]
0x1400424c4  mov     [rax+2], di
0x1400424c8  mov     rax, [rbp+50h+arg_18]
0x1400424cc  mov     [rax+4], cx
0x1400424d0  lea     rcx, [rbp+50h+var_90]
0x1400424d4  mov     rax, [rbp+50h+arg_18]
0x1400424d8  mov     word ptr [rax+6], 8
0x1400424de  mov     rax, [rbp+50h+arg_18]
0x1400424e2  mov     [rax+8], rcx
0x1400424e6  mov     r8, [rbp+50h+arg_18]; EcpContext
0x1400424ea  mov     rdx, [rbp+50h+EcpList]; EcpList
0x1400424ee  mov     rcx, cs:Globals; Filter
0x1400424f5  call    cs:__imp_FltInsertExtraCreateParameter
0x1400424fc  nop     dword ptr [rax+rax+00h]
0x140042501  xorps   xmm0, xmm0
0x140042504  mov     [rbp+50h+var_98], 1
0x14004250c  lea     eax, [rdi+26h]
0x14004250f  movups  xmmword ptr [rbp+50h+var_B8.Size], xmm0
0x140042513  mov     [rbp+50h+var_B8.Size], ax
0x140042517  movups  xmmword ptr [rbp+50h+var_B8.DeviceObjectHint], xmm0
0x14004251b  call    cs:__imp_PsGetHostSilo
0x140042522  nop     dword ptr [rax+rax+00h]
0x140042527  mov     rcx, cs:Globals; Filter
0x14004252e  lea     r9, [rbp+50h+FileObject]; FileObject
0x140042532  mov     [rbp+50h+var_98], rax
0x140042536  lea     r8, [rbp+50h+FileHandle]; FileHandle
0x14004253a  mov     rax, [rbp+50h+EcpList]
0x14004253e  xorps   xmm0, xmm0
0x140042541  mov     [rbp+50h+var_B8.ExtraCreateParameter], rax
0x140042545  mov     rdx, r15; Instance
0x140042548  lea     rax, [rbp+50h+var_B8]
0x14004254c  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x140042553  mov     [rsp+150h+DriverContext], rax; DriverContext
0x140042558  lea     rax, [rbp+50h+IoStatusBlock]
0x14004255c  mov     [rsp+150h+Flags], 0; Flags
0x140042564  mov     [rsp+150h+EaLength], 0; EaLength
0x14004256c  mov     [rsp+150h+EaBuffer], 0; EaBuffer
0x140042575  mov     [rsp+150h+CreateOptions], esi; CreateOptions
0x140042579  mov     [rsp+150h+CreateDisposition], edi; CreateDisposition
0x14004257d  mov     [rsp+150h+ShareAccess], 0; ShareAccess
0x140042585  mov     [rsp+150h+FileAttributes], 6; FileAttributes
0x14004258d  mov     [rsp+150h+AllocationSize], 0; AllocationSize
0x140042596  mov     [rsp+150h+EcpContext], rax; IoStatusBlock
0x14004259b  lea     rax, [rbp+50h+ObjectAttributes]
0x14004259f  mov     [rsp+150h+LookasideList], rax; ObjectAttributes
0x1400425a4  mov     dword ptr [rsp+150h+CleanupCallback], 40000000h; DesiredAccess
0x1400425ac  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x1400425b4  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x1400425bb  mov     [rbp+50h+ObjectAttributes.ObjectName], r14
0x1400425bf  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400425c4  call    cs:__imp_FltCreateFileEx2
0x1400425cb  nop     dword ptr [rax+rax+00h]
0x1400425d0  mov     ebx, eax
0x1400425d2  test    eax, eax
0x1400425d4  js      short loc_1400425F7
0x1400425d6  mov     rdx, [rbp+50h+arg_18]; EcpContext
0x1400425da  mov     rcx, cs:Globals; Filter
0x1400425e1  call    cs:__imp_FltIsEcpAcknowledged
0x1400425e8  nop     dword ptr [rax+rax+00h]
0x1400425ed  test    al, al
0x1400425ef  mov     ecx, 0C0000001h
0x1400425f4  cmovz   ebx, ecx
0x1400425f7  mov     rdx, [rbp+50h+EcpList]; EcpList
0x1400425fb  test    rdx, rdx
0x1400425fe  jz      short loc_140042613
0x140042600  mov     rcx, cs:Globals; Filter
0x140042607  call    cs:__imp_FltFreeExtraCreateParameterList
0x14004260e  nop     dword ptr [rax+rax+00h]
0x140042613  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x140042617  test    rcx, rcx
0x14004261a  jz      short loc_140042628
0x14004261c  call    cs:__imp_FltClose
0x140042623  nop     dword ptr [rax+rax+00h]
0x140042628  mov     rcx, [rbp+50h+FileObject]; Object
0x14004262c  test    rcx, rcx
0x14004262f  jz      short loc_14004263D
0x140042631  call    cs:__imp_ObfDereferenceObject
0x140042638  nop     dword ptr [rax+rax+00h]
0x14004263d  mov     eax, ebx
0x14004263f  add     rsp, 128h
0x140042646  pop     r15
0x140042648  pop     r14
0x14004264a  pop     rdi
0x14004264b  pop     rsi
0x14004264c  pop     rbx
0x14004264d  pop     rbp
0x14004264e  retn
```
