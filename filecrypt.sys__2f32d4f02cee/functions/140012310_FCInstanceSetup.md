# FCInstanceSetup

- ea: `0x140012310`
- end: `0x1400127aa`
- name: `FCInstanceSetup`
- size: `1178`
- prototype: `__int64 __fastcall(PFLT_FILTER *, __int64, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000d398`
- `0x140012310`
- `0x1400127b0`

## import_xrefs

- `ntoskrnl!IoGetLowerDeviceObject` at `0x1400126f4`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x1400126f4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400125e6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400125e6`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1400123e2`
- `ntoskrnl!FsRtlIsMobileOS` at `0x140012685`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1400123e2`
- `ntoskrnl!FsRtlIsMobileOS` at `0x140012685`
- `ntoskrnl!ObfDereferenceObject` at `0x140012706`
- `ntoskrnl!ObfDereferenceObject` at `0x14001279c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001392c`
- `ntoskrnl!ObfDereferenceObject` at `0x140012706`
- `ntoskrnl!ObfDereferenceObject` at `0x14001279c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001392c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400125fe`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400125fe`
- `ntoskrnl!RtlVolumeDeviceToDosName` at `0x140012551`
- `ntoskrnl!RtlVolumeDeviceToDosName` at `0x140012551`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001276a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012780`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001276a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012780`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138f9`
- `ntoskrnl!_wcsnicmp` at `0x140012493`
- `ntoskrnl!_wcsnicmp` at `0x140012493`
- `ntoskrnl!ExAllocatePool2` at `0x140012384`
- `ntoskrnl!ExAllocatePool2` at `0x140012423`
- `ntoskrnl!ExAllocatePool2` at `0x1400125a9`
- `ntoskrnl!ExAllocatePool2` at `0x140012384`
- `ntoskrnl!ExAllocatePool2` at `0x140012423`
- `ntoskrnl!ExAllocatePool2` at `0x1400125a9`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400126d5`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400126d5`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140012533`
- `FLTMGR!FltGetDiskDeviceObject` at `0x140012533`
- `FLTMGR!FltSetVolumeContext` at `0x140012657`
- `FLTMGR!FltSetVolumeContext` at `0x140012657`
- `FLTMGR!FltQueryVolumeInformation` at `0x14001245d`
- `FLTMGR!FltQueryVolumeInformation` at `0x14001245d`
- `FLTMGR!FltReleaseContext` at `0x14001278e`
- `FLTMGR!FltReleaseContext` at `0x140013916`
- `FLTMGR!FltReleaseContext` at `0x14001278e`
- `FLTMGR!FltReleaseContext` at `0x140013916`
- `FLTMGR!FltGetVolumeProperties` at `0x1400123b3`
- `FLTMGR!FltGetVolumeProperties` at `0x1400123b3`
- `FLTMGR!FltAllocateContext` at `0x1400124e1`
- `FLTMGR!FltAllocateContext` at `0x1400124e1`

## pseudocode

```c
__int64 __fastcall FCInstanceSetup(PFLT_FILTER *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // r14d
  struct _FLT_VOLUME_PROPERTIES *v6; // rdi
  wchar_t *v7; // rsi
  bool v8; // bl
  char v9; // r12
  struct _FLT_VOLUME_PROPERTIES *Pool2; // rax
  __int64 v11; // rcx
  wchar_t *v12; // rax
  int SectorSize; // ebx
  _OWORD *v14; // rax
  USHORT Length; // ax
  _QWORD *v16; // rbx
  _QWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // eax
  PVPB Vpb; // rbx
  PDEVICE_OBJECT AttachedDeviceReference; // r14
  PDEVICE_OBJECT v22; // rbx
  ULONG LengthReturned; // [rsp+30h] [rbp-88h] BYREF
  PFLT_CONTEXT ReturnedContext; // [rsp+38h] [rbp-80h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+40h] [rbp-78h] BYREF
  struct _FLT_VOLUME_PROPERTIES *v27; // [rsp+48h] [rbp-70h]
  wchar_t *v28; // [rsp+50h] [rbp-68h]
  PCUNICODE_STRING SourceString; // [rsp+58h] [rbp-60h]
  __int64 v30; // [rsp+60h] [rbp-58h]
  struct _IO_STATUS_BLOCK Iosb; // [rsp+68h] [rbp-50h] BYREF

  Iosb = 0;
  DiskDeviceObject = 0;
  ReturnedContext = 0;
  v5 = -1071906801;
  LengthReturned = 0;
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v28 = 0;
  v8 = 0;
  v9 = 0;
  if ( a3 == 8 && ((unsigned int)(a4 - 2) <= 1 || a4 == 22) )
  {
    Pool2 = (struct _FLT_VOLUME_PROPERTIES *)ExAllocatePool2(256, 584, 1886798662);
    v6 = Pool2;
    v27 = Pool2;
    if ( Pool2 )
    {
      if ( FltGetVolumeProperties(a1[2], Pool2, 0x248u, &LengthReturned) >= 0 )
      {
        if ( (v6->DeviceCharacteristics & 1) != 0 )
          v9 = 1;
        if ( (gFCFlags & 8) != 0 )
        {
          v12 = (wchar_t *)ExAllocatePool2(256, 88, 1769358150);
          v7 = v12;
          v28 = v12;
          if ( !v12 || FltQueryVolumeInformation(a1[3], &Iosb, v12, 0x58u, FileFsVolumeInformation) < 0 )
            goto LABEL_43;
          v11 = *((unsigned int *)v7 + 3);
          if ( (*((_DWORD *)v7 + 3) & 0xFFFFFFFE) == 0xC )
            v8 = _wcsnicmp(v7 + 9, L"SDCARD", (unsigned __int64)(unsigned int)v11 >> 1) == 0;
        }
        if ( (unsigned __int8)FsRtlIsMobileOS(v11) )
        {
          if ( !v9 && !v8 )
            goto LABEL_43;
        }
        else if ( (int)FCpRetrieveAppPairingId(a1) < 0 && !v8 )
        {
          goto LABEL_43;
        }
        SectorSize = 512;
        if ( FltAllocateContext(a1[1], 1u, 0x38u, (POOL_TYPE)512, &ReturnedContext) >= 0 )
        {
          v14 = ReturnedContext;
          *(_OWORD *)ReturnedContext = 0;
          v14[1] = 0;
          v14[2] = 0;
          *((_QWORD *)v14 + 6) = 0;
          if ( v6->SectorSize > 0x200u )
            SectorSize = v6->SectorSize;
          *((_DWORD *)ReturnedContext + 4) = SectorSize;
          *((_QWORD *)ReturnedContext + 1) = 0;
          if ( FltGetDiskDeviceObject(a1[2], &DiskDeviceObject) >= 0 )
          {
            if ( RtlVolumeDeviceToDosName(DiskDeviceObject, (PUNICODE_STRING)ReturnedContext) < 0 )
            {
              SourceString = &v6->RealDeviceName;
              Length = v6->RealDeviceName.Length;
              if ( !Length )
              {
                SourceString = &v6->FileSystemDeviceName;
                Length = v6->FileSystemDeviceName.Length;
                if ( !Length )
                  goto LABEL_43;
              }
              v30 = (unsigned __int16)(Length + 2);
              v16 = ReturnedContext;
              v16[1] = ExAllocatePool2(64, v30, 1986937670);
              if ( !*((_QWORD *)ReturnedContext + 1) )
                goto LABEL_43;
              *(_WORD *)ReturnedContext = 0;
              *((_WORD *)ReturnedContext + 1) = v30;
              RtlCopyUnicodeString((PUNICODE_STRING)ReturnedContext, SourceString);
              RtlAppendUnicodeToString((PUNICODE_STRING)ReturnedContext, L":");
            }
            v17 = ReturnedContext;
            v18 = *((_DWORD *)ReturnedContext + 4);
            *(_OWORD *)((char *)ReturnedContext + 24) = 0;
            v17[5] = 0;
            *((_DWORD *)v17 + 10) = v18;
            *((_DWORD *)v17 + 11) = 16;
            *((_BYTE *)ReturnedContext + 48) = 1;
            if ( (int)FCpEncVolumeStart((__int64)ReturnedContext + 24) >= 0 )
            {
              v19 = FltSetVolumeContext(a1[2], FLT_SET_CONTEXT_KEEP_IF_EXISTS, ReturnedContext, 0);
              if ( (int)(v19 + 0x80000000) < 0 || v19 == -1071906814 )
              {
                Vpb = DiskDeviceObject->Vpb;
                if ( (unsigned __int8)FsRtlIsMobileOS(v19) || (Vpb->DeviceObject->Flags & 0x20000) == 0 )
                {
                  *((_BYTE *)ReturnedContext + 49) = 1;
                  Vpb->DeviceObject->Flags |= 0x20000u;
                }
                else
                {
                  *((_BYTE *)ReturnedContext + 49) = 0;
                }
                if ( (gFCFlags & 8) != 0 && !v9 )
                {
                  AttachedDeviceReference = IoGetAttachedDeviceReference(DiskDeviceObject);
                  while ( AttachedDeviceReference )
                  {
                    AttachedDeviceReference->Characteristics |= 1u;
                    v22 = AttachedDeviceReference;
                    AttachedDeviceReference = IoGetLowerDeviceObject(AttachedDeviceReference);
                    ObfDereferenceObject(v22);
                  }
                }
                if ( (gFCFlags & 0x10) != 0 )
                  DiskDeviceObject->Characteristics &= ~0x100u;
                v5 = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x70764346u);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x69764346u);
  if ( ReturnedContext )
    FltReleaseContext(ReturnedContext);
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  return v5;
}

```

## disassembly

```asm
0x140012310  push    rbx
0x140012312  push    rsi
0x140012313  push    rdi
0x140012314  push    r12
0x140012316  push    r13
0x140012318  push    r14
0x14001231a  push    r15
0x14001231c  sub     rsp, 80h
0x140012323  mov     r15, rcx
0x140012326  xorps   xmm0, xmm0
0x140012329  movups  xmmword ptr [rsp+0B8h+Iosb], xmm0
0x14001232e  xor     eax, eax
0x140012330  mov     [rsp+0B8h+DiskDeviceObject], rax
0x140012335  mov     [rsp+0B8h+ReturnedContext], rax
0x14001233a  mov     r14d, 0C01C000Fh
0x140012340  mov     [rsp+0B8h+LengthReturned], eax
0x140012344  mov     edi, eax
0x140012346  mov     [rsp+0B8h+var_70], rax
0x14001234b  mov     esi, eax
0x14001234d  mov     [rsp+0B8h+var_68], rax
0x140012352  xor     bl, bl
0x140012354  xor     r12b, r12b
0x140012357  cmp     r8d, 8
0x14001235b  jnz     loc_14001272D
0x140012361  lea     eax, [r9-2]
0x140012365  cmp     eax, 1
0x140012368  jbe     short loc_140012374
0x14001236a  cmp     r9d, 16h
0x14001236e  jnz     loc_14001272D
0x140012374  mov     edx, 248h
0x140012379  mov     ecx, 100h
0x14001237e  mov     r8d, 70764346h
0x140012384  call    cs:__imp_ExAllocatePool2
0x14001238b  nop     dword ptr [rax+rax+00h]
0x140012390  mov     rdi, rax
0x140012393  mov     [rsp+0B8h+var_70], rax
0x140012398  test    rax, rax
0x14001239b  jz      loc_14001272D
0x1400123a1  lea     r9, [rsp+0B8h+LengthReturned]; LengthReturned
0x1400123a6  mov     r8d, 248h; VolumePropertiesLength
0x1400123ac  mov     rdx, rax; VolumeProperties
0x1400123af  mov     rcx, [r15+10h]; Volume
0x1400123b3  call    cs:__imp_FltGetVolumeProperties
0x1400123ba  nop     dword ptr [rax+rax+00h]
0x1400123bf  test    eax, eax
0x1400123c1  js      loc_14001272D
0x1400123c7  mov     eax, [rdi+4]
0x1400123ca  test    al, 1
0x1400123cc  jnz     loc_1400124AD
0x1400123d2  mov     eax, cs:gFCFlags
0x1400123d8  test    al, 8
0x1400123da  jnz     short loc_140012413
0x1400123dc  mov     r13d, 1
0x1400123e2  call    cs:__imp_FsRtlIsMobileOS
0x1400123e9  nop     dword ptr [rax+rax+00h]
0x1400123ee  test    al, al
0x1400123f0  jnz     loc_1400124B5
0x1400123f6  mov     rcx, r15
0x1400123f9  call    FCpRetrieveAppPairingId
0x1400123fe  test    eax, eax
0x140012400  jns     loc_1400124C2
0x140012406  test    bl, bl
0x140012408  jnz     loc_1400124C2
0x14001240e  jmp     loc_14001272D
0x140012413  mov     edx, 58h ; 'X'
0x140012418  mov     ecx, 100h
0x14001241d  mov     r8d, 69764346h
0x140012423  call    cs:__imp_ExAllocatePool2
0x14001242a  nop     dword ptr [rax+rax+00h]
0x14001242f  mov     rsi, rax
0x140012432  mov     [rsp+0B8h+var_68], rax
0x140012437  test    rax, rax
0x14001243a  jz      loc_14001272D
0x140012440  mov     r13d, 1
0x140012446  mov     [rsp+0B8h+FsInformationClass], r13d; FsInformationClass
0x14001244b  mov     r9d, 58h ; 'X'; Length
0x140012451  mov     r8, rax; FsInformation
0x140012454  lea     rdx, [rsp+0B8h+Iosb]; Iosb
0x140012459  mov     rcx, [r15+18h]; Instance
0x14001245d  call    cs:__imp_FltQueryVolumeInformation
0x140012464  nop     dword ptr [rax+rax+00h]
0x140012469  test    eax, eax
0x14001246b  js      loc_14001272D
0x140012471  mov     ecx, [rsi+0Ch]
0x140012474  mov     eax, ecx
0x140012476  and     eax, 0FFFFFFFEh
0x140012479  cmp     eax, 0Ch
0x14001247c  jnz     loc_1400123E2
0x140012482  mov     r8d, ecx
0x140012485  shr     r8, 1; MaxCount
0x140012488  lea     rcx, [rsi+12h]; Str1
0x14001248c  lea     rdx, aSdcard; "SDCARD"
0x140012493  call    cs:__imp__wcsnicmp
0x14001249a  nop     dword ptr [rax+rax+00h]
0x14001249f  movzx   ebx, bl
0x1400124a2  test    eax, eax
0x1400124a4  cmovz   ebx, r13d
0x1400124a8  jmp     loc_1400123E2
0x1400124ad  mov     r12b, 1
0x1400124b0  jmp     loc_1400123D2
0x1400124b5  test    r12b, r12b
0x1400124b8  jnz     short loc_1400124C2
0x1400124ba  test    bl, bl
0x1400124bc  jz      loc_14001272D
0x1400124c2  mov     edx, r13d; ContextType
0x1400124c5  lea     rax, [rsp+0B8h+ReturnedContext]
0x1400124ca  mov     qword ptr [rsp+0B8h+FsInformationClass], rax; ReturnedContext
0x1400124cf  mov     ebx, 200h
0x1400124d4  mov     r9d, ebx; PoolType
0x1400124d7  mov     r8d, 38h ; '8'; ContextSize
0x1400124dd  mov     rcx, [r15+8]; Filter
0x1400124e1  call    cs:__imp_FltAllocateContext
0x1400124e8  nop     dword ptr [rax+rax+00h]
0x1400124ed  test    eax, eax
0x1400124ef  js      loc_14001272D
0x1400124f5  xorps   xmm0, xmm0
0x1400124f8  xor     ecx, ecx
0x1400124fa  mov     rax, [rsp+0B8h+ReturnedContext]
0x1400124ff  movups  xmmword ptr [rax], xmm0
0x140012502  movups  xmmword ptr [rax+10h], xmm0
0x140012506  movups  xmmword ptr [rax+20h], xmm0
0x14001250a  mov     [rax+30h], rcx
0x14001250e  movzx   eax, word ptr [rdi+10h]
0x140012512  cmp     ax, bx
0x140012515  jbe     short loc_140012519
0x140012517  mov     ebx, eax
0x140012519  mov     rax, [rsp+0B8h+ReturnedContext]
0x14001251e  mov     [rax+10h], ebx
0x140012521  mov     rax, [rsp+0B8h+ReturnedContext]
0x140012526  mov     [rax+8], rcx
0x14001252a  lea     rdx, [rsp+0B8h+DiskDeviceObject]; DiskDeviceObject
0x14001252f  mov     rcx, [r15+10h]; Volume
0x140012533  call    cs:__imp_FltGetDiskDeviceObject
0x14001253a  nop     dword ptr [rax+rax+00h]
0x14001253f  test    eax, eax
0x140012541  js      loc_14001272D
0x140012547  mov     rdx, [rsp+0B8h+ReturnedContext]; DosName
0x14001254c  mov     rcx, [rsp+0B8h+DiskDeviceObject]; VolumeDeviceObject
0x140012551  call    cs:__imp_RtlVolumeDeviceToDosName
0x140012558  nop     dword ptr [rax+rax+00h]
0x14001255d  test    eax, eax
0x14001255f  jns     loc_14001260A
0x140012565  lea     rax, [rdi+38h]
0x140012569  mov     [rsp+0B8h+SourceString], rax
0x14001256e  movzx   eax, word ptr [rax]
0x140012571  test    ax, ax
0x140012574  jnz     short loc_14001258B
0x140012576  lea     rax, [rdi+28h]
0x14001257a  mov     [rsp+0B8h+SourceString], rax
0x14001257f  movzx   eax, word ptr [rax]
0x140012582  test    ax, ax
0x140012585  jz      loc_14001272D
0x14001258b  add     ax, 2
0x14001258f  movzx   eax, ax
0x140012592  mov     [rsp+0B8h+var_58], rax
0x140012597  mov     rbx, [rsp+0B8h+ReturnedContext]
0x14001259c  mov     edx, eax
0x14001259e  mov     ecx, 40h ; '@'
0x1400125a3  mov     r8d, 766E4346h
0x1400125a9  call    cs:__imp_ExAllocatePool2
0x1400125b0  nop     dword ptr [rax+rax+00h]
0x1400125b5  mov     [rbx+8], rax
0x1400125b9  mov     rcx, [rsp+0B8h+ReturnedContext]
0x1400125be  cmp     qword ptr [rcx+8], 0
0x1400125c3  jz      loc_14001272D
0x1400125c9  xor     eax, eax
0x1400125cb  mov     [rcx], ax
0x1400125ce  mov     rax, [rsp+0B8h+ReturnedContext]
0x1400125d3  mov     rcx, [rsp+0B8h+var_58]
0x1400125d8  mov     [rax+2], cx
0x1400125dc  mov     rdx, [rsp+0B8h+SourceString]; SourceString
0x1400125e1  mov     rcx, [rsp+0B8h+ReturnedContext]; DestinationString
0x1400125e6  call    cs:__imp_RtlCopyUnicodeString
0x1400125ed  nop     dword ptr [rax+rax+00h]
0x1400125f2  lea     rdx, asc_140006A40; ":"
0x1400125f9  mov     rcx, [rsp+0B8h+ReturnedContext]; Destination
0x1400125fe  call    cs:__imp_RtlAppendUnicodeToString
0x140012605  nop     dword ptr [rax+rax+00h]
0x14001260a  mov     rcx, [rsp+0B8h+ReturnedContext]
0x14001260f  mov     eax, [rcx+10h]
0x140012612  xorps   xmm0, xmm0
0x140012615  xor     edx, edx
0x140012617  movups  xmmword ptr [rcx+18h], xmm0
0x14001261b  mov     [rcx+28h], rdx
0x14001261f  mov     [rcx+28h], eax
0x140012622  mov     dword ptr [rcx+2Ch], 10h
0x140012629  mov     rax, [rsp+0B8h+ReturnedContext]
0x14001262e  mov     byte ptr [rax+30h], 1
0x140012632  mov     rcx, [rsp+0B8h+ReturnedContext]
0x140012637  add     rcx, 18h
0x14001263b  call    FCpEncVolumeStart
0x140012640  test    eax, eax
0x140012642  js      loc_14001272D
0x140012648  xor     r9d, r9d; OldContext
0x14001264b  mov     r8, [rsp+0B8h+ReturnedContext]; NewContext
0x140012650  mov     edx, r13d; Operation
0x140012653  mov     rcx, [r15+10h]; Volume
0x140012657  call    cs:__imp_FltSetVolumeContext
0x14001265e  nop     dword ptr [rax+rax+00h]
0x140012663  mov     ecx, eax
0x140012665  mov     edx, 80000000h
0x14001266a  add     eax, edx
0x14001266c  test    edx, eax
0x14001266e  jnz     short loc_14001267C
0x140012670  cmp     ecx, 0C01C0002h
0x140012676  jnz     loc_14001272D
0x14001267c  mov     rax, [rsp+0B8h+DiskDeviceObject]
0x140012681  mov     rbx, [rax+38h]
0x140012685  call    cs:__imp_FsRtlIsMobileOS
0x14001268c  nop     dword ptr [rax+rax+00h]
0x140012691  test    al, al
0x140012693  jnz     short loc_1400126AD
0x140012695  mov     rax, [rbx+8]
0x140012699  test    dword ptr [rax+30h], 20000h
0x1400126a0  jz      short loc_1400126AD
0x1400126a2  mov     rax, [rsp+0B8h+ReturnedContext]
0x1400126a7  mov     byte ptr [rax+31h], 0
0x1400126ab  jmp     short loc_1400126C1
0x1400126ad  mov     rax, [rsp+0B8h+ReturnedContext]
0x1400126b2  mov     byte ptr [rax+31h], 1
0x1400126b6  mov     rax, [rbx+8]
0x1400126ba  or      dword ptr [rax+30h], 20000h
0x1400126c1  mov     eax, cs:gFCFlags
0x1400126c7  test    al, 8
0x1400126c9  jz      short loc_140012714
0x1400126cb  test    r12b, r12b
0x1400126ce  jnz     short loc_140012714
0x1400126d0  mov     rcx, [rsp+0B8h+DiskDeviceObject]; DeviceObject
0x1400126d5  call    cs:__imp_IoGetAttachedDeviceReference
0x1400126dc  nop     dword ptr [rax+rax+00h]
0x1400126e1  mov     r14, rax
0x1400126e4  test    r14, r14
0x1400126e7  jz      short loc_140012714
0x1400126e9  or      dword ptr [r14+34h], 1
0x1400126ee  mov     rbx, r14
0x1400126f1  mov     rcx, r14; DeviceObject
0x1400126f4  call    cs:__imp_IoGetLowerDeviceObject
0x1400126fb  nop     dword ptr [rax+rax+00h]
0x140012700  mov     r14, rax
0x140012703  mov     rcx, rbx; Object
0x140012706  call    cs:__imp_ObfDereferenceObject
0x14001270d  nop     dword ptr [rax+rax+00h]
0x140012712  jmp     short loc_1400126E4
0x140012714  mov     eax, cs:gFCFlags
0x14001271a  test    al, 10h
0x14001271c  jz      short loc_14001272A
0x14001271e  mov     rax, [rsp+0B8h+DiskDeviceObject]
0x140012723  and     dword ptr [rax+34h], 0FFFFFEFFh
0x14001272a  xor     r14d, r14d
0x14001272d  test    rdi, rdi
0x140012730  jnz     short loc_140012762
0x140012732  test    rsi, rsi
0x140012735  jnz     short loc_140012778
0x140012737  mov     rcx, [rsp+0B8h+ReturnedContext]; Context
0x14001273c  test    rcx, rcx
0x14001273f  jnz     short loc_14001278E
0x140012741  mov     rcx, [rsp+0B8h+DiskDeviceObject]; Object
0x140012746  test    rcx, rcx
0x140012749  jnz     short loc_14001279C
0x14001274b  mov     eax, r14d
0x14001274e  add     rsp, 80h
0x140012755  pop     r15
0x140012757  pop     r14
0x140012759  pop     r13
0x14001275b  pop     r12
0x14001275d  pop     rdi
0x14001275e  pop     rsi
0x14001275f  pop     rbx
0x140012760  retn
0x140012762  mov     edx, 70764346h; Tag
0x140012767  mov     rcx, rdi; P
0x14001276a  call    cs:__imp_ExFreePoolWithTag
0x140012771  nop     dword ptr [rax+rax+00h]
0x140012776  jmp     short loc_140012732
0x140012778  mov     edx, 69764346h; Tag
0x14001277d  mov     rcx, rsi; P
0x140012780  call    cs:__imp_ExFreePoolWithTag
0x140012787  nop     dword ptr [rax+rax+00h]
0x14001278c  jmp     short loc_140012737
0x14001278e  call    cs:__imp_FltReleaseContext
0x140012795  nop     dword ptr [rax+rax+00h]
0x14001279a  jmp     short loc_140012741
0x14001279c  call    cs:__imp_ObfDereferenceObject
0x1400127a3  nop     dword ptr [rax+rax+00h]
0x1400127a8  jmp     short loc_14001274B
0x1400138c0  push    rbp
0x1400138c2  sub     rsp, 30h
0x1400138c6  mov     rbp, rdx
0x1400138c9  mov     rcx, [rbp+48h]; P
0x1400138cd  test    rcx, rcx
0x1400138d0  jz      short loc_1400138EB
0x1400138d2  mov     edx, 70764346h; Tag
0x1400138d7  call    cs:__imp_ExFreePoolWithTag
0x1400138de  nop     dword ptr [rax+rax+00h]
0x1400138e3  mov     qword ptr [rbp+48h], 0
0x1400138eb  mov     rcx, [rbp+50h]; P
0x1400138ef  test    rcx, rcx
0x1400138f2  jz      short loc_14001390D
0x1400138f4  mov     edx, 69764346h; Tag
0x1400138f9  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
