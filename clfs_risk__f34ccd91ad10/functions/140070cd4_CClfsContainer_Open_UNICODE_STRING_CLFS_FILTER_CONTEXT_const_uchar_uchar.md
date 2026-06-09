# CClfsContainer::Open(_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,uchar,uchar &)

- ea: `0x140070cd4`
- end: `0x140071240`
- name: `?Open@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@EAEAE@Z`
- size: `1388`
- prototype: `__int64 __usercall@<rax>(CClfsContainer *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, const struct _CLFS_FILTER_CONTEXT *@<r8>, unsigned __int8@<r9b>, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003a7cc`
- `0x140078d5c`

## callees

- `0x140007470`
- `0x140014824`
- `0x140017e40`
- `0x140018280`
- `0x1400326b0`
- `0x140032bb8`
- `0x140032d88`
- `0x140070cd4`
- `0x140071248`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140071212`
- `ntoskrnl!ObfDereferenceObject` at `0x14007bd1e`
- `ntoskrnl!ObfDereferenceObject` at `0x140071212`
- `ntoskrnl!ObfDereferenceObject` at `0x14007bd1e`
- `ntoskrnl!ZwClose` at `0x140071226`
- `ntoskrnl!ZwClose` at `0x14007bd36`
- `ntoskrnl!ZwClose` at `0x140071226`
- `ntoskrnl!ZwClose` at `0x14007bd36`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140070f52`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140070f52`
- `ntoskrnl!FsRtlInitializeExtraCreateParameterList` at `0x140070dd7`
- `ntoskrnl!FsRtlInitializeExtraCreateParameterList` at `0x140070dd7`
- `ntoskrnl!FsRtlInitializeExtraCreateParameter` at `0x140070e15`
- `ntoskrnl!FsRtlInitializeExtraCreateParameter` at `0x140070e15`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140070e31`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140070e31`
- `ntoskrnl!IoCreateFileEx` at `0x140070f0e`
- `ntoskrnl!IoCreateFileEx` at `0x140070f0e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140070f7f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140070f7f`

## string_xrefs

- `0x1400710eb`: `CClfsContainer::Open`

## pseudocode

```c
__int64 __fastcall CClfsContainer::Open(
        CClfsContainer *this,
        struct _UNICODE_STRING *a2,
        const struct _CLFS_FILTER_CONTEXT *a3,
        char a4,
        bool *a5)
{
  NTSTATUS ParameterList; // ebx
  void **v10; // rsi
  void *v11; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  enum _EVENT_TYPE v13; // ecx
  struct _DEVOBJ_EXTENSION *DeviceObjectExtension; // rax
  int v15; // r8d
  unsigned __int8 v16; // r8
  PDEVICE_OBJECT AttachedTo; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-190h] BYREF
  PVOID Object; // [rsp+98h] [rbp-180h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A0h] [rbp-178h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-158h]
  CClfsContainer *v23; // [rsp+C8h] [rbp-150h]
  struct _IO_STATUS_BLOCK v24; // [rsp+D0h] [rbp-148h] BYREF
  __int128 v25; // [rsp+E0h] [rbp-138h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-128h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-120h] BYREF
  __int128 v28; // [rsp+128h] [rbp-F0h] BYREF
  _OWORD v29[2]; // [rsp+138h] [rbp-E0h] BYREF
  __int64 v30; // [rsp+158h] [rbp-C0h]
  __int128 v31; // [rsp+160h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+170h] [rbp-A8h]
  _BYTE v33[72]; // [rsp+180h] [rbp-98h] BYREF
  char EcpContext[8]; // [rsp+1C8h] [rbp-50h] BYREF

  v23 = this;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  memset(v33, 0, sizeof(v33));
  v25 = 0;
  v26 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v22 = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *a5 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ParameterList = FsRtlInitializeExtraCreateParameterList((PECP_LIST)&v25);
  if ( ParameterList >= 0 )
  {
    FsRtlInitializeExtraCreateParameter((PECP_HEADER)v33, 0, 0, 0x48u, &ECP_TYPE_CLFS_OPEN_CONTAINER, 0);
    ParameterList = FsRtlInsertExtraCreateParameter((PECP_LIST)&v25, EcpContext);
    if ( ParameterList >= 0 )
    {
      *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
      *(_QWORD *)&DriverContext.Size = 40;
      v22 = 1;
      DriverContext.ExtraCreateParameter = (struct _ECP_LIST *)&v25;
      DriverContext.DeviceObjectHint = *(PVOID *)a3;
      v10 = (void **)((char *)this + 32);
      ParameterList = IoCreateFileEx(
                        (PHANDLE)this + 4,
                        0xC0020000,
                        &ObjectAttributes,
                        &IoStatusBlock,
                        0,
                        a4 != 0 ? 6 : 128,
                        1u,
                        1u,
                        0x800Eu,
                        *((PVOID *)a3 + 1),
                        *((_DWORD *)a3 + 4),
                        CreateFileTypeNone,
                        0,
                        0x100u,
                        &DriverContext);
      if ( ParameterList < 0 )
      {
        *v10 = 0;
      }
      else
      {
        v11 = *v10;
        Object = 0;
        ParameterList = ObReferenceObjectByHandle(v11, 3u, 0, 0, &Object, 0);
        *((_QWORD *)this + 6) = Object;
        if ( ParameterList < 0 )
        {
          *((_QWORD *)this + 6) = 0;
        }
        else
        {
          RelatedDeviceObject = IoGetRelatedDeviceObject(*((PFILE_OBJECT *)this + 6));
          if ( RelatedDeviceObject )
          {
            if ( RelatedDeviceObject->DeviceType == 20
              || (DeviceObjectExtension = RelatedDeviceObject->DeviceObjectExtension) != 0
              && (AttachedTo = DeviceObjectExtension->AttachedTo) != 0
              && AttachedTo->DeviceType == 20 )
            {
              ParameterList = -1073741637;
            }
            else
            {
              if ( !*((_QWORD *)this + 5) )
              {
                ParameterList = ClfsCreateEventObject(v13, (struct _KEVENT **)this + 5);
                if ( ParameterList < 0 )
                  goto LABEL_34;
                if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
                {
                  WPP_SF_slq(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    13,
                    v15,
                    (unsigned int)"CClfsContainer::Open",
                    18,
                    *((_QWORD *)this + 5));
                }
              }
              ParameterList = CClfsContainer::QueryInformation(
                                this,
                                &IoStatusBlock,
                                &v31,
                                0x18u,
                                FileStandardInformation);
              if ( ParameterList >= 0 )
              {
                ParameterList = CClfsContainer::QueryVolumeInformation(
                                  this,
                                  &IoStatusBlock,
                                  &v28,
                                  0x10u,
                                  FileFsAttributeInformation);
                if ( (int)(ParameterList + 0x80000000) < 0 || ParameterList == -2147483643 )
                {
                  if ( (v28 & 0x10) != 0 )
                  {
                    ParameterList = CClfsContainer::SetCompression(this, &IoStatusBlock, v16);
                    if ( ParameterList < 0 )
                      ParameterList = 0;
                  }
                  else
                  {
                    ParameterList = 0;
                  }
                  if ( !a4
                    || (memset(v29, 0, sizeof(v29)),
                        v30 = 0,
                        v24.Status = 0,
                        v24.Information = 0,
                        ParameterList = CClfsContainer::QueryInformation(this, &v24, v29, 0x28u, FileBasicInformation),
                        ParameterList >= 0)
                    && ((v30 & 4) != 0 && (v30 & 2) != 0
                     || (LODWORD(v30) = v30 | 6,
                         ParameterList = CClfsContainer::SetInformation(this, &v24, v29, 0x28u, FileBasicInformation),
                         ParameterList >= 0)) )
                  {
                    *a5 = (v28 & 8) != 0;
                    *((_QWORD *)this + 1) = *((_QWORD *)&v31 + 1);
                  }
                }
              }
            }
          }
          else
          {
            ParameterList = -1073741808;
          }
        }
      }
    }
  }
LABEL_34:
  if ( ParameterList < 0 )
  {
    if ( *((_QWORD *)this + 4) )
    {
      if ( *((_QWORD *)this + 6) )
      {
        ObfDereferenceObject(*((PVOID *)this + 6));
        *((_QWORD *)this + 6) = 0;
      }
      ZwClose(*((HANDLE *)this + 4));
    }
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 1) = 0;
  }
  return (unsigned int)ParameterList;
}

```

## disassembly

```asm
0x140070cd4  mov     r11, rsp
0x140070cd7  push    rbx
0x140070cd8  push    rsi
0x140070cd9  push    rdi
0x140070cda  push    r12
0x140070cdc  push    r13
0x140070cde  push    r14
0x140070ce0  push    r15
0x140070ce2  sub     rsp, 1E0h
0x140070ce9  mov     rax, cs:__security_cookie
0x140070cf0  xor     rax, rsp
0x140070cf3  mov     [rsp+218h+var_48], rax
0x140070cfb  mov     r15b, r9b
0x140070cfe  mov     r14, r8
0x140070d01  mov     rbx, rdx
0x140070d04  mov     rdi, rcx
0x140070d07  mov     [rsp+218h+var_150], rcx
0x140070d0f  mov     r12, [rsp+218h+arg_20]
0x140070d17  xor     r13d, r13d
0x140070d1a  mov     qword ptr [r11-120h], 30h ; '0'
0x140070d25  mov     qword ptr [r11-108h], 240h
0x140070d30  mov     [r11-190h], r13
0x140070d37  mov     [r11-188h], r13
0x140070d3e  mov     [r11-198h], r13d
0x140070d45  lea     esi, [r13+48h]
0x140070d49  mov     r8d, esi; Size
0x140070d4c  xor     edx, edx; Val
0x140070d4e  lea     rcx, [r11-98h]; void *
0x140070d55  call    memset
0x140070d5a  xorps   xmm0, xmm0
0x140070d5d  xor     eax, eax
0x140070d5f  movups  [rsp+218h+var_138], xmm0
0x140070d67  mov     [rsp+218h+var_128], rax
0x140070d6f  xorps   xmm1, xmm1
0x140070d72  movups  xmmword ptr [rsp+218h+var_178.Size], xmm1
0x140070d7a  movups  xmmword ptr [rsp+218h+var_178.DeviceObjectHint], xmm1
0x140070d82  mov     [rsp+218h+var_158], rax
0x140070d8a  movups  [rsp+218h+var_B8], xmm0
0x140070d92  mov     [rsp+218h+var_A8], rax
0x140070d9a  movups  [rsp+218h+var_F0], xmm0
0x140070da2  mov     [rdi+8], r13
0x140070da6  mov     [rdi+40h], r13d
0x140070daa  mov     [rdi+18h], r13
0x140070dae  mov     [rdi+10h], r13
0x140070db2  mov     [r12], r13b
0x140070db6  mov     [rsp+218h+ObjectAttributes.RootDirectory], r13
0x140070dbe  mov     [rsp+218h+ObjectAttributes.ObjectName], rbx
0x140070dc6  movdqu  xmmword ptr [rsp+218h+ObjectAttributes.SecurityDescriptor], xmm0
0x140070dcf  lea     rcx, [rsp+218h+var_138]; EcpList
0x140070dd7  call    cs:__imp_FsRtlInitializeExtraCreateParameterList
0x140070dde  nop     dword ptr [rax+rax+00h]
0x140070de3  mov     ebx, eax
0x140070de5  mov     [rsp+218h+var_198], eax
0x140070dec  test    eax, eax
0x140070dee  js      loc_1400711D5
0x140070df4  mov     [rsp+218h+ListAllocatedFrom], r13; ListAllocatedFrom
0x140070df9  lea     rax, ECP_TYPE_CLFS_OPEN_CONTAINER
0x140070e00  mov     [rsp+218h+EcpType], rax; EcpType
0x140070e05  mov     r9d, esi; TotalSize
0x140070e08  xor     r8d, r8d; CleanupCallback
0x140070e0b  xor     edx, edx; EcpFlags
0x140070e0d  lea     rcx, [rsp+218h+var_98]; Ecp
0x140070e15  call    cs:__imp_FsRtlInitializeExtraCreateParameter
0x140070e1c  nop     dword ptr [rax+rax+00h]
0x140070e21  lea     rdx, [rsp+218h+EcpContext]; EcpContext
0x140070e29  lea     rcx, [rsp+218h+var_138]; EcpList
0x140070e31  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140070e38  nop     dword ptr [rax+rax+00h]
0x140070e3d  mov     ebx, eax
0x140070e3f  mov     [rsp+218h+var_198], eax
0x140070e46  test    eax, eax
0x140070e48  js      loc_1400711D5
0x140070e4e  xorps   xmm0, xmm0
0x140070e51  xor     eax, eax
0x140070e53  movups  xmmword ptr [rsp+218h+var_178.Size], xmm0
0x140070e5b  movups  xmmword ptr [rsp+218h+var_178.DeviceObjectHint], xmm0
0x140070e63  mov     [rsp+218h+var_158], rax
0x140070e6b  lea     eax, [rsi-20h]
0x140070e6e  mov     [rsp+218h+var_178.Size], ax
0x140070e76  lea     edx, [rsi-47h]
0x140070e79  mov     [rsp+218h+var_158], rdx
0x140070e81  lea     rax, [rsp+218h+var_138]
0x140070e89  mov     [rsp+218h+var_178.ExtraCreateParameter], rax
0x140070e91  mov     rax, [r14]
0x140070e94  mov     [rsp+218h+var_178.DeviceObjectHint], rax
0x140070e9c  lea     rsi, [rdi+20h]
0x140070ea0  mov     al, r15b
0x140070ea3  neg     al
0x140070ea5  sbb     ecx, ecx
0x140070ea7  and     ecx, 0FFFFFF86h
0x140070eaa  sub     ecx, 0FFFFFF80h
0x140070ead  lea     rax, [rsp+218h+var_178]
0x140070eb5  mov     [rsp+218h+DriverContext], rax; DriverContext
0x140070eba  mov     [rsp+218h+Options], 100h; Options
0x140070ec2  mov     [rsp+218h+InternalParameters], r13; InternalParameters
0x140070ec7  mov     [rsp+218h+CreateFileType], r13d; CreateFileType
0x140070ecc  mov     eax, [r14+10h]
0x140070ed0  mov     [rsp+218h+EaLength], eax; EaLength
0x140070ed4  mov     rax, [r14+8]
0x140070ed8  mov     [rsp+218h+EaBuffer], rax; EaBuffer
0x140070edd  mov     [rsp+218h+CreateOptions], 800Eh; CreateOptions
0x140070ee5  mov     [rsp+218h+Disposition], edx; Disposition
0x140070ee9  mov     [rsp+218h+ShareAccess], edx; ShareAccess
0x140070eed  mov     dword ptr [rsp+218h+ListAllocatedFrom], ecx; FileAttributes
0x140070ef1  mov     [rsp+218h+EcpType], r13; AllocationSize
0x140070ef6  lea     r9, [rsp+218h+IoStatusBlock]; IoStatusBlock
0x140070efe  lea     r8, [rsp+218h+ObjectAttributes]; ObjectAttributes
0x140070f06  mov     edx, 0C0020000h; DesiredAccess
0x140070f0b  mov     rcx, rsi; FileHandle
0x140070f0e  call    cs:__imp_IoCreateFileEx
0x140070f15  nop     dword ptr [rax+rax+00h]
0x140070f1a  mov     ebx, eax
0x140070f1c  mov     [rsp+218h+var_198], eax
0x140070f23  test    eax, eax
0x140070f25  js      loc_1400710A6
0x140070f2b  mov     rcx, [rsi]; Handle
0x140070f2e  mov     [rsp+218h+Object], r13
0x140070f36  mov     [rsp+218h+ListAllocatedFrom], r13; HandleInformation
0x140070f3b  lea     rax, [rsp+218h+Object]
0x140070f43  mov     [rsp+218h+EcpType], rax; Object
0x140070f48  xor     r9d, r9d; AccessMode
0x140070f4b  xor     r8d, r8d; ObjectType
0x140070f4e  lea     edx, [r13+3]; DesiredAccess
0x140070f52  call    cs:__imp_ObReferenceObjectByHandle
0x140070f59  nop     dword ptr [rax+rax+00h]
0x140070f5e  mov     ebx, eax
0x140070f60  mov     rax, [rsp+218h+Object]
0x140070f68  mov     [rdi+30h], rax
0x140070f6c  mov     [rsp+218h+var_198], ebx
0x140070f73  test    ebx, ebx
0x140070f75  js      loc_1400710AE
0x140070f7b  mov     rcx, [rdi+30h]; FileObject
0x140070f7f  call    cs:__imp_IoGetRelatedDeviceObject
0x140070f86  nop     dword ptr [rax+rax+00h]
0x140070f8b  test    rax, rax
0x140070f8e  jz      loc_140071095
0x140070f94  cmp     dword ptr [rax+48h], 14h
0x140070f98  jz      loc_1400710B7
0x140070f9e  mov     rax, [rax+138h]
0x140070fa5  test    rax, rax
0x140070fa8  jnz     loc_1400710BE
0x140070fae  lea     rsi, [rdi+28h]
0x140070fb2  cmp     [rsi], r13
0x140070fb5  jnz     short loc_140070FF0
0x140070fb7  mov     rdx, rsi; struct _KEVENT **
0x140070fba  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x140070fbf  mov     ebx, eax
0x140070fc1  mov     [rsp+218h+var_198], eax
0x140070fc8  test    eax, eax
0x140070fca  js      loc_1400711D5
0x140070fd0  lea     rax, WPP_GLOBAL_Control
0x140070fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140070fde  cmp     rcx, rax
0x140070fe1  jz      short loc_140070FF0
0x140070fe3  test    dword ptr [rcx+2Ch], 4000000h
0x140070fea  jnz     loc_1400710D6
0x140070ff0  mov     esi, 5
0x140070ff5  mov     dword ptr [rsp+218h+EcpType], esi; enum _FILE_INFORMATION_CLASS
0x140070ff9  lea     r9d, [rsi+13h]; unsigned int
0x140070ffd  lea     r8, [rsp+218h+var_B8]; void *
0x140071005  lea     rdx, [rsp+218h+IoStatusBlock]; struct _IO_STATUS_BLOCK *
0x14007100d  mov     rcx, rdi; this
0x140071010  call    ?QueryInformation@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@@Z; CClfsContainer::QueryInformation(_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS)
0x140071015  mov     ebx, eax
0x140071017  mov     [rsp+218h+var_198], eax
0x14007101e  test    eax, eax
0x140071020  js      loc_1400711D5
0x140071026  mov     dword ptr [rsp+218h+EcpType], esi; enum _FSINFOCLASS
0x14007102a  lea     r9d, [rsi+0Bh]; unsigned int
0x14007102e  lea     r8, [rsp+218h+var_F0]; void *
0x140071036  lea     rdx, [rsp+218h+IoStatusBlock]; struct _IO_STATUS_BLOCK *
0x14007103e  mov     rcx, rdi; this
0x140071041  call    ?QueryVolumeInformation@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@PEAXKW4_FSINFOCLASS@@@Z; CClfsContainer::QueryVolumeInformation(_IO_STATUS_BLOCK *,void *,ulong,_FSINFOCLASS)
0x140071046  mov     ebx, eax
0x140071048  mov     [rsp+218h+var_198], eax
0x14007104f  mov     ecx, 80000000h
0x140071054  add     eax, ecx
0x140071056  test    ecx, eax
0x140071058  jnz     short loc_140071066
0x14007105a  cmp     ebx, 80000005h
0x140071060  jnz     loc_1400711D5
0x140071066  test    byte ptr [rsp+218h+var_F0], 10h
0x14007106e  jz      loc_140071100
0x140071074  lea     rdx, [rsp+218h+IoStatusBlock]; struct _IO_STATUS_BLOCK *
0x14007107c  mov     rcx, rdi; this
0x14007107f  call    ?SetCompression@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@E@Z; CClfsContainer::SetCompression(_IO_STATUS_BLOCK *,uchar)
0x140071084  mov     ebx, eax
0x140071086  mov     [rsp+218h+var_198], eax
0x14007108d  test    eax, eax
0x14007108f  cmovs   ebx, r13d
0x140071093  jmp     short loc_140071103
0x140071095  mov     ebx, 0C0000010h
0x14007109a  mov     [rsp+218h+var_198], ebx
0x1400710a1  jmp     loc_1400711D5
0x1400710a6  mov     [rsi], r13
0x1400710a9  jmp     loc_1400711D5
0x1400710ae  mov     [rdi+30h], r13
0x1400710b2  jmp     loc_1400711D5
0x1400710b7  mov     ebx, 0C00000BBh
0x1400710bc  jmp     short loc_14007109A
0x1400710be  mov     rax, [rax+30h]
0x1400710c2  test    rax, rax
0x1400710c5  jz      loc_140070FAE
0x1400710cb  cmp     dword ptr [rax+48h], 14h
0x1400710cf  jz      short loc_1400710B7
0x1400710d1  jmp     loc_140070FAE
0x1400710d6  mov     edx, 0Dh
0x1400710db  mov     rax, [rsi]
0x1400710de  mov     [rsp+218h+ListAllocatedFrom], rax
0x1400710e3  mov     dword ptr [rsp+218h+EcpType], 0A12h
0x1400710eb  lea     r9, aCclfscontainer_0; "CClfsContainer::Open"
0x1400710f2  mov     rcx, [rcx+18h]
0x1400710f6  call    WPP_SF_slq
0x1400710fb  jmp     loc_140070FF0
0x140071100  mov     ebx, r13d
0x140071103  mov     [rsp+218h+var_198], ebx
0x14007110a  test    r15b, r15b
0x14007110d  jz      loc_1400711B9
0x140071113  xorps   xmm0, xmm0
0x140071116  xor     eax, eax
0x140071118  movups  [rsp+218h+var_E0], xmm0
0x140071120  movups  [rsp+218h+var_D0], xmm0
0x140071128  mov     [rsp+218h+var_C0], rax
0x140071130  mov     dword ptr [rsp+218h+var_148], r13d
0x140071138  mov     [rsp+218h+var_148.Information], r13
0x140071140  lea     esi, [rax+4]
0x140071143  mov     dword ptr [rsp+218h+EcpType], esi; enum _FILE_INFORMATION_CLASS
0x140071147  lea     r14d, [rax+28h]
0x14007114b  mov     r9d, r14d; unsigned int
0x14007114e  lea     r8, [rsp+218h+var_E0]; void *
0x140071156  lea     rdx, [rsp+218h+var_148]; struct _IO_STATUS_BLOCK *
0x14007115e  mov     rcx, rdi; this
0x140071161  call    ?QueryInformation@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@@Z; CClfsContainer::QueryInformation(_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS)
0x140071166  mov     ebx, eax
0x140071168  mov     [rsp+218h+var_198], eax
0x14007116f  test    eax, eax
0x140071171  js      short loc_1400711D5
0x140071173  mov     eax, dword ptr [rsp+218h+var_C0]
0x14007117a  test    sil, al
0x14007117d  jz      short loc_140071183
0x14007117f  test    al, 2
0x140071181  jnz     short loc_1400711B9
0x140071183  or      eax, 6
0x140071186  mov     dword ptr [rsp+218h+var_C0], eax
0x14007118d  mov     dword ptr [rsp+218h+EcpType], esi; enum _FILE_INFORMATION_CLASS
0x140071191  mov     r9d, r14d; unsigned int
0x140071194  lea     r8, [rsp+218h+var_E0]; void *
0x14007119c  lea     rdx, [rsp+218h+var_148]; struct _IO_STATUS_BLOCK *
0x1400711a4  mov     rcx, rdi; this
0x1400711a7  call    ?SetInformation@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@@Z; CClfsContainer::SetInformation(_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS)
0x1400711ac  mov     ebx, eax
0x1400711ae  mov     [rsp+218h+var_198], eax
0x1400711b5  test    eax, eax
0x1400711b7  js      short loc_1400711D5
0x1400711b9  mov     eax, dword ptr [rsp+218h+var_F0]
0x1400711c0  shr     eax, 3
0x1400711c3  and     al, 1
0x1400711c5  mov     [r12], al
0x1400711c9  mov     rax, qword ptr [rsp+218h+var_B8+8]
0x1400711d1  mov     [rdi+8], rax
0x1400711d5  test    ebx, ebx
0x1400711d7  js      short loc_1400711FF
0x1400711d9  mov     eax, ebx
0x1400711db  mov     rcx, [rsp+218h+var_48]
0x1400711e3  xor     rcx, rsp; StackCookie
0x1400711e6  call    __security_check_cookie
0x1400711eb  add     rsp, 1E0h
0x1400711f2  pop     r15
0x1400711f4  pop     r14
0x1400711f6  pop     r13
0x1400711f8  pop     r12
0x1400711fa  pop     rdi
0x1400711fb  pop     rsi
0x1400711fc  pop     rbx
0x1400711fd  retn
0x1400711ff  cmp     [rdi+20h], r13
0x140071203  jz      short loc_140071232
0x140071205  mov     rax, [rdi+30h]
0x140071209  test    rax, rax
0x14007120c  jz      short loc_140071222
0x14007120e  mov     rcx, [rdi+30h]; Object
0x140071212  call    cs:__imp_ObfDereferenceObject
0x140071219  nop     dword ptr [rax+rax+00h]
0x14007121e  mov     [rdi+30h], r13
0x140071222  mov     rcx, [rdi+20h]; Handle
0x140071226  call    cs:__imp_ZwClose
0x14007122d  nop     dword ptr [rax+rax+00h]
0x140071232  mov     [rdi+20h], r13
0x140071236  mov     [rdi+30h], r13
0x14007123a  mov     [rdi+8], r13
0x14007123e  jmp     short loc_1400711D9
0x14007bced  push    rbx
0x14007bcef  push    rbp
0x14007bcf0  sub     rsp, 88h
0x14007bcf7  mov     rbp, rdx
0x14007bcfa  cmp     dword ptr [rbp+80h], 0
0x14007bd01  jge     short loc_14007BD5B
0x14007bd03  mov     rbx, [rbp+0C8h]
0x14007bd0a  cmp     qword ptr [rbx+20h], 0
0x14007bd0f  jz      short loc_14007BD43
  ... truncated ...
```
