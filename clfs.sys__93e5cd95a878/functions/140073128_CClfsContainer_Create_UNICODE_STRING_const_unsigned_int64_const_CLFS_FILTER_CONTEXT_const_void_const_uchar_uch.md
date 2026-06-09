# CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)

- ea: `0x140073128`
- end: `0x14007374f`
- name: `?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z`
- size: `1575`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter4@<rcx>, const struct _UNICODE_STRING *@<rdx>, const unsigned __int64 *@<r8>, const struct _CLFS_FILTER_CONTEXT *@<r9>, void *const, unsigned __int8, unsigned __int8, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003a7cc`
- `0x14003b7d0`
- `0x140078d5c`

## callees

- `0x140007470`
- `0x14000ab00`
- `0x140012418`
- `0x140014824`
- `0x140017e40`
- `0x140018280`
- `0x1400326b0`
- `0x140032d88`
- `0x1400371a4`
- `0x14003cee8`
- `0x14004b314`
- `0x140073128`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400736f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14007c1ca`
- `ntoskrnl!ObfDereferenceObject` at `0x1400736f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14007c1ca`
- `ntoskrnl!ZwClose` at `0x14007370d`
- `ntoskrnl!ZwClose` at `0x14007c1e2`
- `ntoskrnl!ZwClose` at `0x14007370d`
- `ntoskrnl!ZwClose` at `0x14007c1e2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007351f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007351f`
- `ntoskrnl!FsRtlInitializeExtraCreateParameterList` at `0x140073312`
- `ntoskrnl!FsRtlInitializeExtraCreateParameterList` at `0x140073312`
- `ntoskrnl!FsRtlInitializeExtraCreateParameter` at `0x140073357`
- `ntoskrnl!FsRtlInitializeExtraCreateParameter` at `0x140073357`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140073373`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140073373`
- `ntoskrnl!IoCreateFileEx` at `0x140073437`
- `ntoskrnl!IoCreateFileEx` at `0x140073437`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140073555`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140073555`

## string_xrefs

- `0x140073248`: `CClfsContainer::Create`
- `0x1400735ef`: `CClfsContainer::Create`

## pseudocode

```c
__int64 __fastcall CClfsContainer::Create(
        ULONG_PTR BugCheckParameter4,
        struct _UNICODE_STRING *a2,
        const unsigned __int64 *a3,
        const struct _CLFS_FILTER_CONTEXT *a4,
        void *const a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        unsigned __int8 *a8)
{
  unsigned __int8 v12; // r14
  void *CreateFileType; // r8
  ULONG v14; // esi
  NTSTATUS EventObject; // ebx
  ULONG v16; // eax
  void **v17; // r14
  unsigned int v18; // r9d
  int v19; // eax
  void *v20; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  enum _EVENT_TYPE v22; // ecx
  struct _DEVOBJ_EXTENSION *DeviceObjectExtension; // rax
  PDEVICE_OBJECT AttachedTo; // rax
  int v25; // r8d
  ULONG CreateOptions; // [rsp+40h] [rbp-1A8h]
  unsigned int EaBuffer; // [rsp+48h] [rbp-1A0h]
  ULONG EaLength; // [rsp+50h] [rbp-198h]
  ULONG Options; // [rsp+68h] [rbp-180h]
  unsigned __int8 v31; // [rsp+80h] [rbp-168h] BYREF
  char v32[3]; // [rsp+81h] [rbp-167h] BYREF
  NTSTATUS v33; // [rsp+84h] [rbp-164h]
  LARGE_INTEGER AllocationSize; // [rsp+88h] [rbp-160h] BYREF
  int v35; // [rsp+90h] [rbp-158h]
  void *v36; // [rsp+98h] [rbp-150h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-148h] BYREF
  PVOID Object; // [rsp+B0h] [rbp-138h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+B8h] [rbp-130h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-110h]
  unsigned __int8 *v41; // [rsp+E0h] [rbp-108h]
  ULONG_PTR v42; // [rsp+E8h] [rbp-100h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-F8h] BYREF
  __int128 v44; // [rsp+120h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+130h] [rbp-B8h]
  __int128 v46; // [rsp+138h] [rbp-B0h] BYREF
  enum _FILE_INFORMATION_CLASS v47[18]; // [rsp+150h] [rbp-98h] BYREF
  char EcpContext[8]; // [rsp+198h] [rbp-50h] BYREF

  v42 = BugCheckParameter4;
  v41 = a8;
  v12 = 0;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  AllocationSize.QuadPart = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v33 = 0;
  v32[0] = 0;
  v46 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v40 = 0;
  memset(v47, 0, sizeof(v47));
  v44 = 0;
  v45 = 0;
  v36 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slS(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      11,
      (unsigned int)WPP_e6b4d78dd9313ac32e42f0dcea3d4c75_Traceguids,
      (unsigned int)"CClfsContainer::Create",
      91,
      (__int64)a2->Buffer);
  }
  *a8 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a2;
  ObjectAttributes.SecurityDescriptor = a5;
  ObjectAttributes.SecurityQualityOfService = 0;
  AllocationSize.QuadPart = ClfsAlignToBoundary(a3, *(_DWORD *)(BugCheckParameter4 + 68));
  v14 = a7 != 0 ? 8198 : 0x2000;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = (_WORD)CreateFileType + 40;
  v40 = 1;
  DriverContext.DeviceObjectHint = *(PVOID *)a4;
  if ( !DriverContext.DeviceObjectHint )
  {
LABEL_8:
    v16 = 256;
    v35 = 256;
    if ( a6 != (_BYTE)CreateFileType )
      v16 = 257;
    v35 = v16;
    v17 = (void **)(BugCheckParameter4 + 32);
    EventObject = IoCreateFileEx(
                    (PHANDLE)(BugCheckParameter4 + 32),
                    0xC0120000,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    &AllocationSize,
                    v14,
                    1u,
                    2u,
                    0x20804Eu,
                    *((PVOID *)a4 + 1),
                    *((_DWORD *)a4 + 4),
                    (CREATE_FILE_TYPE)CreateFileType,
                    CreateFileType,
                    v16,
                    &DriverContext);
    v33 = EventObject;
    if ( EventObject == -1073741727 && a5 && (*((_WORD *)a5 + 1) & 0x2000) != 0 )
    {
      v19 = ClfsCreateSaclProtectedLogFile(
              (PHANDLE)(BugCheckParameter4 + 32),
              &v36,
              &v31,
              v18,
              &ObjectAttributes,
              &IoStatusBlock,
              &AllocationSize,
              v14,
              CreateOptions,
              EaBuffer,
              EaLength,
              *((PVOID *)a4 + 1),
              *((_DWORD *)a4 + 4),
              Options,
              &DriverContext);
      if ( v19 >= 0 )
        EventObject = v19;
      v33 = EventObject;
    }
    if ( EventObject >= 0 )
    {
      *(_QWORD *)(BugCheckParameter4 + 8) = *a3;
      v20 = *v17;
      Object = 0;
      EventObject = ObReferenceObjectByHandle(v20, 0xC0000000, 0, 0, &Object, 0);
      *(_QWORD *)(BugCheckParameter4 + 48) = Object;
      v33 = EventObject;
      if ( EventObject >= 0 )
      {
        RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(BugCheckParameter4 + 48));
        if ( RelatedDeviceObject )
        {
          if ( RelatedDeviceObject->DeviceType == 20
            || (DeviceObjectExtension = RelatedDeviceObject->DeviceObjectExtension) != 0
            && (AttachedTo = DeviceObjectExtension->AttachedTo) != 0
            && AttachedTo->DeviceType == 20 )
          {
            EventObject = -1073741637;
          }
          else
          {
            if ( !*(_QWORD *)(BugCheckParameter4 + 40) )
            {
              EventObject = ClfsCreateEventObject(v22, (struct _KEVENT **)(BugCheckParameter4 + 40));
              v33 = EventObject;
              if ( EventObject < 0 )
                goto LABEL_41;
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
              {
                WPP_SF_slq(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  12,
                  v25,
                  (unsigned int)"CClfsContainer::Create",
                  117,
                  *(_QWORD *)(BugCheckParameter4 + 40));
              }
            }
            EventObject = CClfsContainer::QueryVolumeInformation(
                            (CClfsContainer *)BugCheckParameter4,
                            &IoStatusBlock,
                            &v46,
                            0x10u,
                            FileFsAttributeInformation);
            v33 = EventObject;
            if ( (int)(EventObject + 0x80000000) >= 0 && EventObject != -2147483643 )
              goto LABEL_41;
            *v41 = (v46 & 8) != 0;
            if ( (v46 & 8) != 0 || !a5 )
            {
              if ( *a3 )
              {
                EventObject = CClfsContainer::InitializeFile(BugCheckParameter4);
                v33 = EventObject;
                goto LABEL_41;
              }
              EventObject = 0;
            }
            else
            {
              EventObject = -1073741609;
            }
          }
        }
        else
        {
          EventObject = -1073741808;
        }
        v33 = EventObject;
        goto LABEL_41;
      }
      *(_QWORD *)(BugCheckParameter4 + 48) = 0;
    }
    else
    {
      *v17 = 0;
    }
LABEL_41:
    v12 = v31;
    goto LABEL_42;
  }
  EventObject = FsRtlInitializeExtraCreateParameterList((PECP_LIST)&v44);
  v33 = EventObject;
  if ( EventObject >= 0 )
  {
    FsRtlInitializeExtraCreateParameter((PECP_HEADER)v47, 0, 0, 0x48u, &ECP_TYPE_CLFS_CREATE_CONTAINER, 0);
    EventObject = FsRtlInsertExtraCreateParameter((PECP_LIST)&v44, EcpContext);
    v33 = EventObject;
    CreateFileType = 0;
    if ( EventObject >= 0 )
    {
      DriverContext.ExtraCreateParameter = (struct _ECP_LIST *)&v44;
      goto LABEL_8;
    }
  }
LABEL_42:
  if ( v12 )
    ClfsSetThreadImpersonationToken(v36);
  if ( EventObject < 0 && *(_QWORD *)(BugCheckParameter4 + 32) )
  {
    v32[0] = 1;
    CClfsContainer::SetInformation(
      (CClfsContainer *)BugCheckParameter4,
      &IoStatusBlock,
      v32,
      1u,
      FileDispositionInformation);
    if ( *(_QWORD *)(BugCheckParameter4 + 48) )
    {
      ObfDereferenceObject(*(PVOID *)(BugCheckParameter4 + 48));
      *(_QWORD *)(BugCheckParameter4 + 48) = 0;
    }
    ZwClose(*(HANDLE *)(BugCheckParameter4 + 32));
    *(_QWORD *)(BugCheckParameter4 + 32) = 0;
    *(_QWORD *)(BugCheckParameter4 + 8) = 0;
  }
  return (unsigned int)EventObject;
}

```

## disassembly

```asm
0x140073128  mov     r11, rsp
0x14007312b  push    rbx
0x14007312c  push    rsi
0x14007312d  push    rdi
0x14007312e  push    r12
0x140073130  push    r13
0x140073132  push    r14
0x140073134  push    r15
0x140073136  sub     rsp, 1B0h
0x14007313d  mov     rax, cs:__security_cookie
0x140073144  xor     rax, rsp
0x140073147  mov     [rsp+1E8h+var_48], rax
0x14007314f  mov     r12, r9
0x140073152  mov     r13, r8
0x140073155  mov     rbx, rdx
0x140073158  mov     rdi, rcx
0x14007315b  mov     [rsp+1E8h+var_100], rcx
0x140073163  mov     r15, [rsp+1E8h+arg_20]
0x14007316b  mov     rsi, [rsp+1E8h+arg_38]
0x140073173  mov     [rsp+1E8h+var_108], rsi
0x14007317b  xor     r14d, r14d
0x14007317e  mov     [r11-148h], r14
0x140073185  mov     [r11-140h], r14
0x14007318c  mov     [r11-160h], r14
0x140073193  xorps   xmm0, xmm0
0x140073196  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.Length], xmm0
0x14007319e  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.ObjectName], xmm0
0x1400731a6  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400731ae  mov     [r11-164h], r14d
0x1400731b5  mov     [r11-167h], r14b
0x1400731bc  movups  [rsp+1E8h+var_B0], xmm0
0x1400731c4  xorps   xmm1, xmm1
0x1400731c7  xor     eax, eax
0x1400731c9  movups  xmmword ptr [rsp+1E8h+var_130.Size], xmm1
0x1400731d1  movups  xmmword ptr [rsp+1E8h+var_130.DeviceObjectHint], xmm1
0x1400731d9  mov     [r11-110h], rax
0x1400731e0  xor     edx, edx; Val
0x1400731e2  lea     r8d, [r14+48h]; Size
0x1400731e6  lea     rcx, [r11-98h]; void *
0x1400731ed  call    memset
0x1400731f2  xorps   xmm0, xmm0
0x1400731f5  xor     eax, eax
0x1400731f7  movups  [rsp+1E8h+var_C8], xmm0
0x1400731ff  mov     [rsp+1E8h+var_B8], rax
0x140073207  mov     [rsp+1E8h+var_150], r14
0x14007320f  mov     [rsp+1E8h+var_168], r14b
0x140073217  lea     rax, WPP_GLOBAL_Control
0x14007321e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073225  cmp     rcx, rax
0x140073228  jz      short loc_14007325F
0x14007322a  test    dword ptr [rcx+2Ch], 4000000h
0x140073231  jz      short loc_14007325F
0x140073233  lea     edx, [r14+0Bh]
0x140073237  mov     rax, [rbx+8]
0x14007323b  mov     [rsp+1E8h+ListAllocatedFrom], rax
0x140073240  mov     dword ptr [rsp+1E8h+EcpType], 55Bh
0x140073248  lea     r9, aCclfscontainer_2; "CClfsContainer::Create"
0x14007324f  lea     r8, WPP_e6b4d78dd9313ac32e42f0dcea3d4c75_Traceguids
0x140073256  mov     rcx, [rcx+18h]
0x14007325a  call    WPP_SF_slS
0x14007325f  xor     r8d, r8d
0x140073262  mov     [rsi], r8b
0x140073265  mov     [rsp+1E8h+ObjectAttributes.Length], 30h ; '0'
0x140073270  mov     [rsp+1E8h+ObjectAttributes.RootDirectory], r8
0x140073278  mov     [rsp+1E8h+ObjectAttributes.Attributes], 240h
0x140073283  mov     [rsp+1E8h+ObjectAttributes.ObjectName], rbx
0x14007328b  mov     [rsp+1E8h+ObjectAttributes.SecurityDescriptor], r15
0x140073293  mov     [rsp+1E8h+ObjectAttributes.SecurityQualityOfService], r8
0x14007329b  mov     edx, [rdi+44h]; unsigned int
0x14007329e  mov     rcx, r13; unsigned __int64 *
0x1400732a1  call    ?ClfsAlignToBoundary@@YA_KAEB_KK@Z; ClfsAlignToBoundary(unsigned __int64 const &,ulong)
0x1400732a6  mov     qword ptr [rsp+1E8h+AllocationSize], rax
0x1400732ae  neg     [rsp+1E8h+arg_30]
0x1400732b5  sbb     esi, esi
0x1400732b7  and     esi, 6
0x1400732ba  add     esi, 2000h
0x1400732c0  xorps   xmm0, xmm0
0x1400732c3  xor     eax, eax
0x1400732c5  movups  xmmword ptr [rsp+1E8h+var_130.Size], xmm0
0x1400732cd  movups  xmmword ptr [rsp+1E8h+var_130.DeviceObjectHint], xmm0
0x1400732d5  mov     [rsp+1E8h+var_110], rax
0x1400732dd  lea     eax, [r8+28h]
0x1400732e1  mov     [rsp+1E8h+var_130.Size], ax
0x1400732e9  mov     [rsp+1E8h+var_110], 1
0x1400732f5  mov     rax, [r12]
0x1400732f9  mov     [rsp+1E8h+var_130.DeviceObjectHint], rax
0x140073301  test    rax, rax
0x140073304  jz      loc_1400733A3
0x14007330a  lea     rcx, [rsp+1E8h+var_C8]; EcpList
0x140073312  call    cs:__imp_FsRtlInitializeExtraCreateParameterList
0x140073319  nop     dword ptr [rax+rax+00h]
0x14007331e  mov     ebx, eax
0x140073320  mov     [rsp+1E8h+var_164], eax
0x140073327  test    eax, eax
0x140073329  js      loc_14007369D
0x14007332f  mov     [rsp+1E8h+ListAllocatedFrom], 0; ListAllocatedFrom
0x140073338  lea     rax, ECP_TYPE_CLFS_CREATE_CONTAINER
0x14007333f  mov     [rsp+1E8h+EcpType], rax; EcpType
0x140073344  mov     r9d, 48h ; 'H'; TotalSize
0x14007334a  xor     r8d, r8d; CleanupCallback
0x14007334d  xor     edx, edx; EcpFlags
0x14007334f  lea     rcx, [rsp+1E8h+var_98]; Ecp
0x140073357  call    cs:__imp_FsRtlInitializeExtraCreateParameter
0x14007335e  nop     dword ptr [rax+rax+00h]
0x140073363  lea     rdx, [rsp+1E8h+EcpContext]; EcpContext
0x14007336b  lea     rcx, [rsp+1E8h+var_C8]; EcpList
0x140073373  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007337a  nop     dword ptr [rax+rax+00h]
0x14007337f  mov     ebx, eax
0x140073381  mov     [rsp+1E8h+var_164], eax
0x140073388  xor     r8d, r8d
0x14007338b  test    eax, eax
0x14007338d  js      loc_14007369D
0x140073393  lea     rax, [rsp+1E8h+var_C8]
0x14007339b  mov     [rsp+1E8h+var_130.ExtraCreateParameter], rax
0x1400733a3  mov     eax, 100h
0x1400733a8  mov     [rsp+1E8h+var_158], eax
0x1400733af  lea     ecx, [rax+1]
0x1400733b2  cmp     [rsp+1E8h+arg_28], r8b
0x1400733ba  cmovnz  eax, ecx
0x1400733bd  mov     [rsp+1E8h+var_158], eax
0x1400733c4  lea     r14, [rdi+20h]
0x1400733c8  lea     rcx, [rsp+1E8h+var_130]
0x1400733d0  mov     [rsp+1E8h+DriverContext], rcx; DriverContext
0x1400733d5  mov     [rsp+1E8h+Options], eax; unsigned int
0x1400733d9  mov     [rsp+1E8h+InternalParameters], r8; InternalParameters
0x1400733de  mov     [rsp+1E8h+CreateFileType], r8d; CreateFileType
0x1400733e3  mov     eax, [r12+10h]
0x1400733e8  mov     [rsp+1E8h+EaLength], eax; unsigned int
0x1400733ec  mov     rax, [r12+8]
0x1400733f1  mov     [rsp+1E8h+EaBuffer], rax; unsigned int
0x1400733f6  mov     [rsp+1E8h+CreateOptions], 20804Eh; unsigned int
0x1400733fe  mov     [rsp+1E8h+Disposition], 2; Disposition
0x140073406  mov     [rsp+1E8h+ShareAccess], 1; ShareAccess
0x14007340e  mov     dword ptr [rsp+1E8h+ListAllocatedFrom], esi; FileAttributes
0x140073412  lea     rax, [rsp+1E8h+AllocationSize]
0x14007341a  mov     [rsp+1E8h+EcpType], rax; AllocationSize
0x14007341f  lea     r9, [rsp+1E8h+IoStatusBlock]; IoStatusBlock
0x140073427  lea     r8, [rsp+1E8h+ObjectAttributes]; ObjectAttributes
0x14007342f  mov     edx, 0C0120000h; DesiredAccess
0x140073434  mov     rcx, r14; FileHandle
0x140073437  call    cs:__imp_IoCreateFileEx
0x14007343e  nop     dword ptr [rax+rax+00h]
0x140073443  mov     ebx, eax
0x140073445  mov     [rsp+1E8h+var_164], eax
0x14007344c  cmp     eax, 0C0000061h
0x140073451  jnz     loc_1400734D7
0x140073457  test    r15, r15
0x14007345a  jz      short loc_1400734D7
0x14007345c  movzx   eax, word ptr [r15+2]
0x140073461  bt      ax, 0Dh
0x140073466  jnb     short loc_1400734D7
0x140073468  lea     rax, [rsp+1E8h+var_130]
0x140073470  mov     [rsp+1E8h+DriverContext], rax; struct _IO_DRIVER_CREATE_CONTEXT *
0x140073475  mov     eax, [r12+10h]
0x14007347a  mov     dword ptr [rsp+1E8h+InternalParameters], eax; unsigned int
0x14007347e  mov     rax, [r12+8]
0x140073483  mov     qword ptr [rsp+1E8h+CreateFileType], rax; PVOID
0x140073488  mov     [rsp+1E8h+Disposition], esi; ULONG
0x14007348c  lea     rax, [rsp+1E8h+AllocationSize]
0x140073494  mov     qword ptr [rsp+1E8h+ShareAccess], rax; PLARGE_INTEGER
0x140073499  lea     rax, [rsp+1E8h+IoStatusBlock]
0x1400734a1  mov     [rsp+1E8h+ListAllocatedFrom], rax; IoStatusBlock
0x1400734a6  lea     rax, [rsp+1E8h+ObjectAttributes]
0x1400734ae  mov     [rsp+1E8h+EcpType], rax; ObjectAttributes
0x1400734b3  lea     r8, [rsp+1E8h+var_168]; unsigned __int8 *
0x1400734bb  lea     rdx, [rsp+1E8h+var_150]; void **
0x1400734c3  mov     rcx, r14; FileHandle
0x1400734c6  call    ?ClfsCreateSaclProtectedLogFile@@YAJPEAPEAX0PEAEKPEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAT_LARGE_INTEGER@@KKKKPEAXKKPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; ClfsCreateSaclProtectedLogFile(void * *,void * *,uchar *,ulong,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void *,ulong,ulong,_IO_DRIVER_CREATE_CONTEXT *)
0x1400734cb  test    eax, eax
0x1400734cd  cmovns  ebx, eax
0x1400734d0  mov     [rsp+1E8h+var_164], ebx
0x1400734d7  test    ebx, ebx
0x1400734d9  jns     short loc_1400734E7
0x1400734db  mov     qword ptr [r14], 0
0x1400734e2  jmp     loc_140073695
0x1400734e7  mov     rax, [r13+0]
0x1400734eb  mov     [rdi+8], rax
0x1400734ef  mov     rcx, [r14]; Handle
0x1400734f2  mov     [rsp+1E8h+Object], 0
0x1400734fe  mov     [rsp+1E8h+ListAllocatedFrom], 0; HandleInformation
0x140073507  lea     rax, [rsp+1E8h+Object]
0x14007350f  mov     [rsp+1E8h+EcpType], rax; Object
0x140073514  xor     r9d, r9d; AccessMode
0x140073517  xor     r8d, r8d; ObjectType
0x14007351a  mov     edx, 0C0000000h; DesiredAccess
0x14007351f  call    cs:__imp_ObReferenceObjectByHandle
0x140073526  nop     dword ptr [rax+rax+00h]
0x14007352b  mov     ebx, eax
0x14007352d  mov     rax, [rsp+1E8h+Object]
0x140073535  mov     [rdi+30h], rax
0x140073539  mov     [rsp+1E8h+var_164], ebx
0x140073540  test    ebx, ebx
0x140073542  jns     short loc_140073551
0x140073544  mov     qword ptr [rdi+30h], 0
0x14007354c  jmp     loc_140073695
0x140073551  mov     rcx, [rdi+30h]; FileObject
0x140073555  call    cs:__imp_IoGetRelatedDeviceObject
0x14007355c  nop     dword ptr [rax+rax+00h]
0x140073561  test    rax, rax
0x140073564  jnz     short loc_140073570
0x140073566  mov     ebx, 0C0000010h
0x14007356b  jmp     loc_14007368E
0x140073570  cmp     dword ptr [rax+48h], 14h
0x140073574  jnz     short loc_140073580
0x140073576  mov     ebx, 0C00000BBh
0x14007357b  jmp     loc_14007368E
0x140073580  mov     rax, [rax+138h]
0x140073587  test    rax, rax
0x14007358a  jz      short loc_14007359B
0x14007358c  mov     rax, [rax+30h]
0x140073590  test    rax, rax
0x140073593  jz      short loc_14007359B
0x140073595  cmp     dword ptr [rax+48h], 14h
0x140073599  jz      short loc_140073576
0x14007359b  lea     rsi, [rdi+28h]
0x14007359f  cmp     qword ptr [rsi], 0
0x1400735a3  jnz     short loc_1400735FF
0x1400735a5  mov     rdx, rsi; struct _KEVENT **
0x1400735a8  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x1400735ad  mov     ebx, eax
0x1400735af  mov     [rsp+1E8h+var_164], eax
0x1400735b6  test    eax, eax
0x1400735b8  js      loc_140073695
0x1400735be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400735c5  lea     rax, WPP_GLOBAL_Control
0x1400735cc  cmp     rcx, rax
0x1400735cf  jz      short loc_1400735FF
0x1400735d1  test    dword ptr [rcx+2Ch], 4000000h
0x1400735d8  jz      short loc_1400735FF
0x1400735da  mov     edx, 0Ch
0x1400735df  mov     rax, [rsi]
0x1400735e2  mov     [rsp+1E8h+ListAllocatedFrom], rax
0x1400735e7  mov     dword ptr [rsp+1E8h+EcpType], 675h
0x1400735ef  lea     r9, aCclfscontainer_2; "CClfsContainer::Create"
0x1400735f6  mov     rcx, [rcx+18h]
0x1400735fa  call    WPP_SF_slq
0x1400735ff  mov     dword ptr [rsp+1E8h+EcpType], 5; enum _FSINFOCLASS
0x140073607  mov     r9d, 10h; unsigned int
0x14007360d  lea     r8, [rsp+1E8h+var_B0]; void *
0x140073615  lea     rdx, [rsp+1E8h+IoStatusBlock]; struct _IO_STATUS_BLOCK *
0x14007361d  mov     rcx, rdi; this
0x140073620  call    ?QueryVolumeInformation@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@PEAXKW4_FSINFOCLASS@@@Z; CClfsContainer::QueryVolumeInformation(_IO_STATUS_BLOCK *,void *,ulong,_FSINFOCLASS)
0x140073625  mov     ebx, eax
0x140073627  mov     [rsp+1E8h+var_164], eax
0x14007362e  mov     ecx, 80000000h
0x140073633  add     eax, ecx
0x140073635  test    ecx, eax
0x140073637  jnz     short loc_140073641
0x140073639  cmp     ebx, 80000005h
0x14007363f  jnz     short loc_140073695
0x140073641  test    dword ptr [rsp+1E8h+var_B0], 8
0x14007364c  setnz   al
0x14007364f  mov     rdx, [rsp+1E8h+var_108]
0x140073657  mov     [rdx], al
0x140073659  test    dword ptr [rsp+1E8h+var_B0], 8
0x140073664  jnz     short loc_140073672
0x140073666  test    r15, r15
0x140073669  jz      short loc_140073672
0x14007366b  mov     ebx, 0C00000D7h
0x140073670  jmp     short loc_14007368E
0x140073672  cmp     qword ptr [r13+0], 0
0x140073677  jbe     short loc_14007368C
0x140073679  mov     rcx, rdi; BugCheckParameter4
0x14007367c  call    ?InitializeFile@CClfsContainer@@QEAAJXZ; CClfsContainer::InitializeFile(void)
0x140073681  mov     ebx, eax
0x140073683  mov     [rsp+1E8h+var_164], eax
0x14007368a  jmp     short loc_140073695
0x14007368c  xor     ebx, ebx
0x14007368e  mov     [rsp+1E8h+var_164], ebx
0x140073695  mov     r14b, [rsp+1E8h+var_168]
0x14007369d  test    r14b, r14b
0x1400736a0  jz      short loc_1400736AF
0x1400736a2  mov     rcx, [rsp+1E8h+var_150]; void *
0x1400736aa  call    ?ClfsSetThreadImpersonationToken@@YAJPEAX@Z; ClfsSetThreadImpersonationToken(void *)
0x1400736af  test    ebx, ebx
0x1400736b1  jns     short loc_140073729
0x1400736b3  cmp     qword ptr [rdi+20h], 0
0x1400736b8  jz      short loc_140073729
0x1400736ba  mov     [rsp+1E8h+var_167], 1
0x1400736c2  mov     dword ptr [rsp+1E8h+EcpType], 0Dh; enum _FILE_INFORMATION_CLASS
0x1400736ca  mov     r9d, 1; unsigned int
0x1400736d0  lea     r8, [rsp+1E8h+var_167]; void *
0x1400736d8  lea     rdx, [rsp+1E8h+IoStatusBlock]; struct _IO_STATUS_BLOCK *
0x1400736e0  mov     rcx, rdi; this
0x1400736e3  call    ?SetInformation@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@@Z; CClfsContainer::SetInformation(_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS)
0x1400736e8  mov     rax, [rdi+30h]
0x1400736ec  test    rax, rax
0x1400736ef  jz      short loc_140073709
0x1400736f1  mov     rcx, [rdi+30h]; Object
0x1400736f5  call    cs:__imp_ObfDereferenceObject
0x1400736fc  nop     dword ptr [rax+rax+00h]
0x140073701  mov     qword ptr [rdi+30h], 0
0x140073709  mov     rcx, [rdi+20h]; Handle
0x14007370d  call    cs:__imp_ZwClose
0x140073714  nop     dword ptr [rax+rax+00h]
0x140073719  mov     qword ptr [rdi+20h], 0
0x140073721  mov     qword ptr [rdi+8], 0
0x140073729  mov     eax, ebx
0x14007372b  mov     rcx, [rsp+1E8h+var_48]
  ... truncated ...
```
