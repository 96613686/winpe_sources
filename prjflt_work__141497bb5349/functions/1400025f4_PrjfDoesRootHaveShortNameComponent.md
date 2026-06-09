# PrjfDoesRootHaveShortNameComponent

- ea: `0x1400025f4`
- end: `0x140002b47`
- name: `PrjfDoesRootHaveShortNameComponent`
- size: `1363`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002e374`

## callees

- `0x140001008`
- `0x1400025f4`
- `0x14000ba20`
- `0x14000d26c`
- `0x14000d754`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002af0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002af0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400028e4`
- `ntoskrnl!ObfDereferenceObject` at `0x140002b1a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400028e4`
- `ntoskrnl!ObfDereferenceObject` at `0x140002b1a`
- `ntoskrnl!ExAllocatePool2` at `0x140002662`
- `ntoskrnl!ExAllocatePool2` at `0x140002662`
- `FLTMGR!FltCreateFileEx2` at `0x140002801`
- `FLTMGR!FltCreateFileEx2` at `0x140002801`
- `FLTMGR!FltClose` at `0x1400028d0`
- `FLTMGR!FltClose` at `0x140002b05`
- `FLTMGR!FltClose` at `0x1400028d0`
- `FLTMGR!FltClose` at `0x140002b05`
- `FLTMGR!FltQueryInformationFile` at `0x14000283a`
- `FLTMGR!FltQueryInformationFile` at `0x14000283a`

## pseudocode

```c
__int64 __fastcall PrjfDoesRootHaveShortNameComponent(struct _FLT_INSTANCE *a1, __int64 a2, _BYTE *a3)
{
  int v5; // edx
  int v6; // r8d
  unsigned __int16 v8; // r15
  NTSTATUS v9; // edi
  unsigned __int16 v10; // bx
  unsigned __int16 v11; // r15
  __int64 v12; // rdx
  int v13; // edx
  int v14; // r8d
  NTSTATUS InformationFile; // eax
  int v16; // edx
  int v17; // r8d
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  __int128 v20; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-60h] BYREF
  PFLT_INSTANCE Instance; // [rsp+A8h] [rbp-58h]
  __int64 v23; // [rsp+B0h] [rbp-50h]
  PVOID FileInformation; // [rsp+B8h] [rbp-48h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v27[32]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v28; // [rsp+120h] [rbp+20h]
  __int64 v29; // [rsp+128h] [rbp+28h]
  __int64 v30; // [rsp+130h] [rbp+30h]
  _DWORD v31[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 *v32; // [rsp+140h] [rbp+40h]
  __int64 v33; // [rsp+148h] [rbp+48h]

  v21 = (__int64)a3;
  v23 = a2;
  Instance = a1;
  FileHandle = 0;
  FileObject = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  FileInformation = (PVOID)ExAllocatePool2(256, 28, 1768835664);
  if ( !FileInformation )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v5,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        46,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        47,
        0,
        (__int64)&v20);
    }
    return 3221225626LL;
  }
  *a3 = 0;
  v8 = *(_WORD *)(a2 + 8);
  v9 = 0;
  v10 = (*(_WORD *)(a2 + 24) >> 1) + 1;
  v11 = v8 >> 1;
  if ( v10 > v11 )
    goto LABEL_31;
  while ( 1 )
  {
    v12 = *(_QWORD *)(v23 + 16);
    if ( *(_WORD *)(v12 + 2LL * v10) != 92 )
    {
      v9 = 0;
      if ( (unsigned int)v10 + 1 <= v11 )
        goto LABEL_16;
    }
    LOWORD(v20) = 2 * v10;
    WORD1(v20) = 2 * v10;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
    *((_QWORD *)&v20 + 1) = v12;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = FltCreateFileEx2(
           Globals,
           Instance,
           &FileHandle,
           &FileObject,
           0x100001u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0x90u,
           7u,
           1u,
           0x4021u,
           0,
           0,
           0x800u,
           0);
    if ( v9 < 0 )
      break;
    InformationFile = FltQueryInformationFile(
                        Instance,
                        FileObject,
                        FileInformation,
                        0x1Cu,
                        FileAlternateNameInformation,
                        0);
    v9 = InformationFile;
    if ( InformationFile >= 0 )
    {
      if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = BYTE9(xmmword_14001A3D0) & 0x40;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDZ(
          782,
          v16,
          v17,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          14,
          50,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          148,
          (__int64)&v20);
      }
      *(_BYTE *)v21 = 1;
      if ( (unsigned int)dword_14001A068 > 5
        && (qword_14001A078 & 0x400000000000LL) != 0
        && (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
      {
        v28 = v31;
        v29 = 2;
        v31[1] = 0;
        v30 = *(_QWORD *)(v23 + 16);
        v31[0] = *(unsigned __int16 *)(v23 + 8);
        v32 = &v21;
        v21 = 0x1000000;
        v33 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_14001A068, byte_140016411, 0, 0, 5, v27);
      }
      goto LABEL_31;
    }
    if ( InformationFile != -1073741772 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v16,
          v17,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          49,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          141,
          InformationFile,
          (__int64)&v20);
      }
      goto LABEL_31;
    }
    if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = BYTE1(xmmword_14001A3E0) & 0x40;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        1038,
        v16,
        v17,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        14,
        48,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        126,
        52,
        (__int64)&v20);
    }
    v9 = 0;
    FltClose(FileHandle);
    FileHandle = 0;
    ObfDereferenceObject(FileObject);
    FileObject = 0;
LABEL_16:
    if ( ++v10 > v11 )
      goto LABEL_31;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      526,
      v13,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      47,
      (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      107,
      v9,
      (__int64)&v20);
  }
LABEL_31:
  ExFreePoolWithTag(FileInformation, 0x696E4A50u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400025f4  push    rbp
0x1400025f6  push    rbx
0x1400025f7  push    rsi
0x1400025f8  push    rdi
0x1400025f9  push    r13
0x1400025fb  push    r14
0x1400025fd  push    r15
0x1400025ff  lea     rbp, [rsp-60h]
0x140002604  sub     rsp, 160h
0x14000260b  mov     rax, cs:__security_cookie
0x140002612  xor     rax, rsp
0x140002615  mov     [rbp+90h+var_40], rax
0x140002619  xorps   xmm0, xmm0
0x14000261c  mov     [rbp+90h+var_F0], r8
0x140002620  mov     rsi, r8
0x140002623  mov     [rbp+90h+var_E0], rdx
0x140002627  mov     rbx, rdx
0x14000262a  mov     [rbp+90h+Instance], rcx
0x14000262e  mov     edx, 1Ch
0x140002633  mov     [rbp+90h+FileHandle], 0
0x14000263b  mov     ecx, 100h
0x140002640  mov     [rbp+90h+FileObject], 0
0x140002648  mov     r8d, 696E4A50h
0x14000264e  movups  [rbp+90h+var_100], xmm0
0x140002652  movups  xmmword ptr [rbp+90h+var_D0.Length], xmm0
0x140002656  movups  xmmword ptr [rbp+90h+var_D0.ObjectName], xmm0
0x14000265a  movups  xmmword ptr [rbp+90h+var_D0.SecurityDescriptor], xmm0
0x14000265e  movups  xmmword ptr [rbp+90h+var_A0], xmm0
0x140002662  call    cs:__imp_ExAllocatePool2
0x140002669  nop     dword ptr [rax+rax+00h]
0x14000266e  xor     r10d, r10d
0x140002671  mov     [rbp+90h+FileInformation], rax
0x140002675  test    rax, rax
0x140002678  jnz     loc_140002704
0x14000267e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140002684  lea     r14, WPP_RECORDER_INITIALIZED
0x14000268b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002692  mov     sil, 40h ; '@'
0x140002695  setnz   r8b
0x140002699  and     dl, sil
0x14000269c  jnz     short loc_1400026A3
0x14000269e  test    r8b, r8b
0x1400026a1  jz      short loc_1400026FA
0x1400026a3  mov     r9, cs:WPP_GLOBAL_Control
0x1400026aa  lea     rax, [rbp+90h+var_100]
0x1400026ae  mov     qword ptr [rsp+190h+CreateOptions], rax
0x1400026b3  lea     r13, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400026ba  mov     [rsp+190h+CreateDisposition], r10d
0x1400026bf  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400026c6  mov     [rsp+190h+ShareAccess], 0A2Fh
0x1400026ce  mov     ecx, 20Eh
0x1400026d3  mov     r9, [r9+40h]
0x1400026d7  mov     qword ptr [rsp+190h+FileAttributes], r13
0x1400026dc  mov     [rsp+190h+AllocationSize], rax
0x1400026e1  mov     word ptr [rsp+190h+IoStatusBlock], 2Eh ; '.'
0x1400026e8  mov     dword ptr [rsp+190h+ObjectAttributes], 0Eh
0x1400026f0  mov     byte ptr [rsp+190h+DesiredAccess], 2
0x1400026f5  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400026fa  mov     eax, 0C000009Ah
0x1400026ff  jmp     loc_140002B28
0x140002704  mov     [rsi], r10b
0x140002707  mov     r8d, 1
0x14000270d  movzx   r15d, word ptr [rbx+8]
0x140002712  mov     edi, r10d
0x140002715  movzx   ebx, word ptr [rbx+18h]
0x140002719  shr     bx, 1
0x14000271c  add     bx, r8w
0x140002720  shr     r15w, 1
0x140002724  cmp     bx, r15w
0x140002728  ja      loc_140002AE7
0x14000272e  mov     sil, 40h ; '@'
0x140002731  lea     r14, WPP_RECORDER_INITIALIZED
0x140002738  lea     r13, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000273f  lea     r9d, [r8+2Fh]
0x140002743  mov     rax, [rbp+90h+var_E0]
0x140002747  mov     rdx, [rax+10h]
0x14000274b  movzx   eax, bx
0x14000274e  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x140002753  jz      short loc_14000276A
0x140002755  movzx   ecx, bx
0x140002758  mov     edi, r10d
0x14000275b  add     ecx, r8d
0x14000275e  movzx   eax, r15w
0x140002762  cmp     ecx, eax
0x140002764  jbe     loc_1400028FF
0x14000276a  mov     rcx, cs:Globals; Filter
0x140002771  movzx   eax, bx
0x140002774  mov     [rsp+190h+DriverContext], r10; DriverContext
0x140002779  add     ax, ax
0x14000277c  mov     [rsp+190h+Flags], 800h; Flags
0x140002784  xorps   xmm0, xmm0
0x140002787  mov     [rsp+190h+EaLength], r10d; EaLength
0x14000278c  mov     [rsp+190h+EaBuffer], r10; EaBuffer
0x140002791  mov     [rsp+190h+CreateOptions], 4021h; CreateOptions
0x140002799  mov     [rsp+190h+CreateDisposition], r8d; CreateDisposition
0x14000279e  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x1400027a2  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x1400027aa  mov     word ptr [rbp+90h+var_100], ax
0x1400027ae  mov     word ptr [rbp+90h+var_100+2], ax
0x1400027b2  lea     rax, [rbp+90h+var_100]
0x1400027b6  mov     [rsp+190h+FileAttributes], 90h; FileAttributes
0x1400027be  mov     [rsp+190h+AllocationSize], r10; AllocationSize
0x1400027c3  mov     [rbp+90h+var_D0.ObjectName], rax
0x1400027c7  lea     rax, [rbp+90h+var_A0]
0x1400027cb  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x1400027d0  lea     rax, [rbp+90h+var_D0]
0x1400027d4  mov     qword ptr [rbp+90h+var_100+8], rdx
0x1400027d8  mov     rdx, [rbp+90h+Instance]; Instance
0x1400027dc  mov     [rbp+90h+var_D0.Length], r9d
0x1400027e0  lea     r9, [rbp+90h+FileObject]; FileObject
0x1400027e4  mov     [rsp+190h+ObjectAttributes], rax; ObjectAttributes
0x1400027e9  mov     [rsp+190h+DesiredAccess], 100001h; DesiredAccess
0x1400027f1  mov     [rbp+90h+var_D0.RootDirectory], r10
0x1400027f5  mov     [rbp+90h+var_D0.Attributes], 240h
0x1400027fc  movdqu  xmmword ptr [rbp+90h+var_D0.SecurityDescriptor], xmm0
0x140002801  call    cs:__imp_FltCreateFileEx2
0x140002808  nop     dword ptr [rax+rax+00h]
0x14000280d  mov     edi, eax
0x14000280f  test    eax, eax
0x140002811  js      loc_140002A7D
0x140002817  mov     r8, [rbp+90h+FileInformation]; FileInformation
0x14000281b  mov     r9d, 1Ch; Length
0x140002821  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140002825  mov     rcx, [rbp+90h+Instance]; Instance
0x140002829  mov     [rsp+190h+ObjectAttributes], 0; LengthReturned
0x140002832  mov     [rsp+190h+DesiredAccess], 15h; FileInformationClass
0x14000283a  call    cs:__imp_FltQueryInformationFile
0x140002841  nop     dword ptr [rax+rax+00h]
0x140002846  mov     edi, eax
0x140002848  test    eax, eax
0x14000284a  jns     loc_140002963
0x140002850  mov     r9d, 0C0000034h
0x140002856  cmp     eax, r9d
0x140002859  jnz     loc_140002912
0x14000285f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002866  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14000286c  setnz   r8b
0x140002870  and     dl, sil
0x140002873  jnz     short loc_14000287A
0x140002875  test    r8b, r8b
0x140002878  jz      short loc_1400028CA
0x14000287a  lea     rax, [rbp+90h+var_100]
0x14000287e  mov     ecx, 40Eh
0x140002883  mov     qword ptr [rsp+190h+CreateOptions], rax
0x140002888  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x14000288f  mov     [rsp+190h+CreateDisposition], r9d
0x140002894  mov     r9, cs:WPP_GLOBAL_Control
0x14000289b  mov     [rsp+190h+ShareAccess], 0A7Eh
0x1400028a3  mov     qword ptr [rsp+190h+FileAttributes], r13
0x1400028a8  mov     [rsp+190h+AllocationSize], rax
0x1400028ad  mov     r9, [r9+40h]
0x1400028b1  mov     word ptr [rsp+190h+IoStatusBlock], 30h ; '0'
0x1400028b8  mov     dword ptr [rsp+190h+ObjectAttributes], 0Eh
0x1400028c0  mov     byte ptr [rsp+190h+DesiredAccess], 4
0x1400028c5  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400028ca  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x1400028ce  xor     edi, edi
0x1400028d0  call    cs:__imp_FltClose
0x1400028d7  nop     dword ptr [rax+rax+00h]
0x1400028dc  mov     rcx, [rbp+90h+FileObject]; Object
0x1400028e0  mov     [rbp+90h+FileHandle], rdi
0x1400028e4  call    cs:__imp_ObfDereferenceObject
0x1400028eb  nop     dword ptr [rax+rax+00h]
0x1400028f0  xor     r10d, r10d
0x1400028f3  lea     r8d, [rdi+1]
0x1400028f7  mov     [rbp+90h+FileObject], r10
0x1400028fb  lea     r9d, [rdi+30h]
0x1400028ff  add     bx, r8w
0x140002903  cmp     bx, r15w
0x140002907  jbe     loc_140002743
0x14000290d  jmp     loc_140002AE7
0x140002912  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002919  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000291f  setnz   r8b
0x140002923  and     dl, sil
0x140002926  jnz     short loc_140002931
0x140002928  test    r8b, r8b
0x14000292b  jz      loc_140002AE7
0x140002931  lea     rax, [rbp+90h+var_100]
0x140002935  mov     qword ptr [rsp+190h+CreateOptions], rax
0x14000293a  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002941  mov     [rsp+190h+CreateDisposition], edi
0x140002945  mov     [rsp+190h+ShareAccess], 0A8Dh
0x14000294d  mov     qword ptr [rsp+190h+FileAttributes], r13
0x140002952  mov     [rsp+190h+AllocationSize], rax
0x140002957  mov     word ptr [rsp+190h+IoStatusBlock], 31h ; '1'
0x14000295e  jmp     loc_140002AC5
0x140002963  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000296a  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140002970  setnz   r8b
0x140002974  and     dl, sil
0x140002977  jnz     short loc_14000297E
0x140002979  test    r8b, r8b
0x14000297c  jz      short loc_1400029C9
0x14000297e  mov     r9, cs:WPP_GLOBAL_Control
0x140002985  lea     rax, [rbp+90h+var_100]
0x140002989  mov     qword ptr [rsp+190h+CreateDisposition], rax
0x14000298e  mov     ecx, 30Eh
0x140002993  mov     [rsp+190h+ShareAccess], 0A94h
0x14000299b  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400029a2  mov     qword ptr [rsp+190h+FileAttributes], r13
0x1400029a7  mov     r9, [r9+40h]
0x1400029ab  mov     [rsp+190h+AllocationSize], rax
0x1400029b0  mov     word ptr [rsp+190h+IoStatusBlock], 32h ; '2'
0x1400029b7  mov     dword ptr [rsp+190h+ObjectAttributes], 0Eh
0x1400029bf  mov     byte ptr [rsp+190h+DesiredAccess], 3
0x1400029c4  call    WPP_RECORDER_AND_TRACE_SF_sDZ
0x1400029c9  mov     rax, [rbp+90h+var_F0]
0x1400029cd  mov     byte ptr [rax], 1
0x1400029d0  mov     eax, cs:dword_14001A068
0x1400029d6  cmp     eax, 5
0x1400029d9  jbe     loc_140002AE7
0x1400029df  mov     rcx, cs:qword_14001A080
0x1400029e6  mov     rdx, 400000000000h
0x1400029f0  mov     rax, cs:qword_14001A078
0x1400029f7  test    rdx, rax
0x1400029fa  jz      loc_140002AE7
0x140002a00  mov     rax, rcx
0x140002a03  and     rax, rdx
0x140002a06  cmp     rax, rcx
0x140002a09  jnz     loc_140002AE7
0x140002a0f  mov     rcx, [rbp+90h+var_E0]
0x140002a13  lea     rax, [rbp+90h+var_58]
0x140002a17  mov     [rbp+90h+var_70], rax
0x140002a1b  lea     rdx, byte_140016411
0x140002a22  xor     r9d, r9d
0x140002a25  mov     [rbp+90h+var_68], 2
0x140002a2d  xor     r8d, r8d
0x140002a30  mov     [rbp+90h+var_54], 0
0x140002a37  mov     rax, [rcx+10h]
0x140002a3b  mov     [rbp+90h+var_60], rax
0x140002a3f  movzx   eax, word ptr [rcx+8]
0x140002a43  lea     rcx, dword_14001A068
0x140002a4a  mov     [rbp+90h+var_58], eax
0x140002a4d  lea     rax, [rbp+90h+var_F0]
0x140002a51  mov     [rbp+90h+var_50], rax
0x140002a55  lea     rax, [rbp+90h+var_90]
0x140002a59  mov     [rsp+190h+ObjectAttributes], rax
0x140002a5e  mov     [rsp+190h+DesiredAccess], 5
0x140002a66  mov     [rbp+90h+var_F0], 1000000h
0x140002a6e  mov     [rbp+90h+var_48], 8
0x140002a76  call    _tlgWriteTransfer_EtwWriteTransfer
0x140002a7b  jmp     short loc_140002AE7
0x140002a7d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002a84  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140002a8a  setnz   r8b
0x140002a8e  and     dl, sil
0x140002a91  jnz     short loc_140002A98
0x140002a93  test    r8b, r8b
0x140002a96  jz      short loc_140002AE7
0x140002a98  lea     rax, [rbp+90h+var_100]
0x140002a9c  mov     qword ptr [rsp+190h+CreateOptions], rax
0x140002aa1  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002aa8  mov     [rsp+190h+CreateDisposition], edi
0x140002aac  mov     [rsp+190h+ShareAccess], 0A6Bh
0x140002ab4  mov     qword ptr [rsp+190h+FileAttributes], r13
0x140002ab9  mov     [rsp+190h+AllocationSize], rax
0x140002abe  mov     word ptr [rsp+190h+IoStatusBlock], 2Fh ; '/'
0x140002ac5  mov     r9, cs:WPP_GLOBAL_Control
0x140002acc  mov     ecx, 20Eh
0x140002ad1  mov     dword ptr [rsp+190h+ObjectAttributes], 0Eh
0x140002ad9  mov     byte ptr [rsp+190h+DesiredAccess], 2
0x140002ade  mov     r9, [r9+40h]
0x140002ae2  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140002ae7  mov     rcx, [rbp+90h+FileInformation]; P
0x140002aeb  mov     edx, 696E4A50h; Tag
0x140002af0  call    cs:__imp_ExFreePoolWithTag
0x140002af7  nop     dword ptr [rax+rax+00h]
0x140002afc  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x140002b00  test    rcx, rcx
0x140002b03  jz      short loc_140002B11
0x140002b05  call    cs:__imp_FltClose
0x140002b0c  nop     dword ptr [rax+rax+00h]
0x140002b11  mov     rcx, [rbp+90h+FileObject]; Object
0x140002b15  test    rcx, rcx
0x140002b18  jz      short loc_140002B26
0x140002b1a  call    cs:__imp_ObfDereferenceObject
0x140002b21  nop     dword ptr [rax+rax+00h]
0x140002b26  mov     eax, edi
0x140002b28  mov     rcx, [rbp+90h+var_40]
0x140002b2c  xor     rcx, rsp; StackCookie
0x140002b2f  call    __security_check_cookie
0x140002b34  add     rsp, 160h
0x140002b3b  pop     r15
0x140002b3d  pop     r14
0x140002b3f  pop     r13
0x140002b41  pop     rdi
0x140002b42  pop     rsi
0x140002b43  pop     rbx
0x140002b44  pop     rbp
0x140002b45  retn
```
