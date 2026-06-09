# FltCreateFileEx2

- ea: `0x18005d2b0`
- end: `0x18005d3b8`
- name: `FltCreateFileEx2`
- size: `264`
- prototype: `NTSTATUS __stdcall(PFLT_FILTER Filter, PFLT_INSTANCE Instance, PHANDLE FileHandle, PFILE_OBJECT *FileObject, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PIO_STATUS_BLOCK IoStatusBlock, PLARGE_INTEGER AllocationSize, ULONG FileAttributes, ULONG ShareAccess, ULONG CreateDisposition, ULONG CreateOptions, PVOID EaBuffer, ULONG EaLength, ULONG Flags, PIO_DRIVER_CREATE_CONTEXT DriverContext)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005d0c0`
- `0x18006d360`
- `0x180074ef0`
- `0x1800762d0`
- `0x180082ef0`

## callees

- `0x180009f20`
- `0x18005c1d0`
- `0x18005c3b0`
- `0x18005c450`
- `0x18005d2b0`
- `0x18005d470`
- `0x180066990`
- `0x1800718a0`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1800795c0`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1800795c0`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1800798ce`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1800798f2`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1800798ce`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1800798f2`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x1800796d5`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x1800796d5`

## pseudocode

```c
NTSTATUS __stdcall FltCreateFileEx2(
        PFLT_FILTER Filter,
        PFLT_INSTANCE Instance,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PIO_STATUS_BLOCK IoStatusBlock,
        PLARGE_INTEGER AllocationSize,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        PVOID EaBuffer,
        ULONG EaLength,
        ULONG Flags,
        PIO_DRIVER_CREATE_CONTEXT DriverContext)
{
  PFLT_INSTANCE v16; // r12
  POBJECT_ATTRIBUTES v17; // r13
  ULONG_PTR v18; // r14
  struct _FLT_INSTANCE *v19; // rdi
  void *v20; // r15
  NTSTATUS File; // ebx
  struct _ECP_LIST *ExtraCreateParameter; // rcx
  NTSTATUS v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  int v27; // r12d
  _FLT_FILTER *v28; // rdx
  PVOID v29; // r12
  int TargetInfo; // edi
  _QWORD *v31; // rcx
  __int128 v32; // xmm0
  __int16 v33; // ax
  _QWORD *v34; // rcx
  char v35; // [rsp+80h] [rbp-69h]
  NTSTATUS v36; // [rsp+84h] [rbp-65h]
  __int16 v37; // [rsp+84h] [rbp-65h]
  int v38; // [rsp+88h] [rbp-61h]
  PVOID v39; // [rsp+90h] [rbp-59h] BYREF
  PVOID EcpContext; // [rsp+98h] [rbp-51h] BYREF
  void *v41; // [rsp+A0h] [rbp-49h] BYREF
  ULONG_PTR v42; // [rsp+A8h] [rbp-41h] BYREF
  struct _FLT_INSTANCE *v43; // [rsp+B0h] [rbp-39h] BYREF
  OBJECT_ATTRIBUTES v44; // [rsp+B8h] [rbp-31h] BYREF

  v16 = Instance;
  v17 = ObjectAttributes;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset(&v44, 0, 44);
  v39 = 0;
  EcpContext = 0;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  File = FltpCreateFile(
           Filter,
           (__int64)Instance,
           FileHandle,
           DesiredAccess,
           ObjectAttributes,
           IoStatusBlock,
           AllocationSize,
           FileAttributes,
           ShareAccess,
           CreateDisposition,
           CreateOptions,
           EaBuffer,
           EaLength,
           Flags,
           (ULONG)DriverContext);
  if ( (unsigned int)(File + 1073740952) > 1 )
    return File;
  if ( !DriverContext )
    return File;
  ExtraCreateParameter = DriverContext->ExtraCreateParameter;
  if ( !ExtraCreateParameter )
    return File;
  v24 = FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_FLT_CREATEFILE_TARGET, &EcpContext, 0);
  if ( (int)FltpDbgStatus(v24) < 0 )
    return File;
  v36 = FltpGenerateDeviceHintEcp(&v39, ObjectAttributes->ObjectName->Length, DriverContext->ExtraCreateParameter);
  if ( (int)FltpDbgStatus(v36) < 0 )
    return v36;
  v25 = FltpCreateFile(
          Filter,
          (__int64)v16,
          FileHandle,
          DesiredAccess,
          ObjectAttributes,
          IoStatusBlock,
          AllocationSize,
          FileAttributes,
          ShareAccess,
          CreateDisposition,
          CreateOptions,
          EaBuffer,
          EaLength,
          Flags,
          (ULONG)DriverContext);
  v38 = v25;
  if ( (unsigned int)(v25 + 1073740952) <= 1 || v25 == -1073740650 )
  {
    v37 = 1;
    while ( FsRtlIsEcpAcknowledged(v39) )
    {
      if ( v38 == -1073740650 )
      {
        LOBYTE(v26) = 1;
        v27 = FltpResetDeviceHintEcp(v39, v26);
        if ( (int)FltpDbgStatus(v27) < 0 )
        {
          File = v27;
          break;
        }
        v35 = 0;
      }
      else
      {
        v28 = v16->Filter;
        v29 = v39;
        TargetInfo = FltpGetTargetInfo((_DWORD)v39, (_DWORD)v28, (unsigned int)&v43, (unsigned int)&v41, (__int64)&v42);
        if ( (int)FltpDbgStatus(TargetInfo) < 0 )
        {
          File = TargetInfo;
          break;
        }
        v19 = v43;
        v31 = EcpContext;
        if ( !v43 || (*((_BYTE *)EcpContext + 24) & 1) == 0 )
        {
          *((_QWORD *)EcpContext + 1) = v41;
          v31[2] = v42;
          *v31 = v19;
          FsRtlAcknowledgeEcp(v31);
          break;
        }
        FltpResetDeviceHintEcp(v29, 0);
        v20 = v41;
        v18 = v42;
        v35 = 1;
      }
      v16 = v19;
      *(_OWORD *)&v44.Length = *(_OWORD *)&v17->Length;
      *(_OWORD *)&v44.ObjectName = *(_OWORD *)&v17->ObjectName;
      v32 = *(_OWORD *)&v17->SecurityDescriptor;
      v44.ObjectName = (PUNICODE_STRING)(v18 + 8);
      *(_OWORD *)&v44.SecurityDescriptor = v32;
      v38 = FltpCreateFile(
              Filter,
              (__int64)v19,
              FileHandle,
              DesiredAccess,
              &v44,
              IoStatusBlock,
              AllocationSize,
              FileAttributes,
              ShareAccess,
              CreateDisposition,
              CreateOptions,
              EaBuffer,
              EaLength,
              Flags,
              (ULONG)DriverContext);
      if ( (int)FltpDbgStatus(v38) >= 0 )
      {
        v34 = EcpContext;
        *(_QWORD *)EcpContext = v19;
        v34[1] = v20;
        v34[2] = v18;
        FsRtlAcknowledgeEcp(v34);
        File = v38;
        break;
      }
      if ( (unsigned int)(v38 + 1073740952) > 1 && v38 != -1073740650 )
      {
        File = v38;
        FltpCleanupTargetInfo(v19, v20, v18);
        break;
      }
      FltpCleanupTargetInfo(v19, v20, v18);
      v33 = v37 + 1;
      if ( !v35 )
        v33 = v37;
      if ( (unsigned __int16)v33 >= 0x40u )
        break;
      v17 = &v44;
      v37 = v33;
    }
    FltpCleanupDeviceHintEcp(DriverContext->ExtraCreateParameter);
    return File;
  }
  FltpCleanupDeviceHintEcp(DriverContext->ExtraCreateParameter);
  return v38;
}

```

## disassembly

```asm
0x18005d2b0  mov     [rsp-8+arg_8], rbx
0x18005d2b5  mov     [rsp-8+arg_18], r9
0x18005d2ba  mov     [rsp-8+FileHandle], r8
0x18005d2bf  mov     [rsp-8+FltObject], rcx
0x18005d2c4  push    rbp
0x18005d2c5  push    rsi
0x18005d2c6  push    rdi
0x18005d2c7  push    r12
0x18005d2c9  push    r13
0x18005d2cb  push    r14
0x18005d2cd  push    r15
0x18005d2cf  lea     rbp, [rsp-7]
0x18005d2d4  sub     rsp, 0F0h
0x18005d2db  mov     rsi, [rbp+37h+DriverContext]
0x18005d2e2  mov     r12, rdx
0x18005d2e5  mov     r13, [rbp+37h+ObjectAttributes]
0x18005d2e9  xor     edx, edx
0x18005d2eb  mov     edx, [rbp+37h+Flags]
0x18005d2f1  xor     r14d, r14d
0x18005d2f4  mov     qword ptr [rsp+120h+EcpContextSize], rsi; EcpContextSize
0x18005d2f9  xorps   xmm0, xmm0
0x18005d2fc  mov     [rsp+120h+var_B0], edx; ULONG
0x18005d300  mov     edi, r14d
0x18005d303  mov     edx, [rbp+37h+EaLength]
0x18005d309  mov     r15d, r14d
0x18005d30c  mov     [rsp+120h+var_B8], edx; ULONG
0x18005d310  mov     rdx, [rbp+37h+EaBuffer]
0x18005d317  mov     [rsp+120h+var_C0], rdx; PVOID
0x18005d31c  mov     edx, [rbp+37h+CreateOptions]
0x18005d322  mov     [rsp+120h+var_C8], edx; ULONG
0x18005d326  mov     edx, [rbp+37h+CreateDisposition]
0x18005d32c  mov     [rsp+120h+var_D0], edx; ULONG
0x18005d330  mov     edx, [rbp+37h+ShareAccess]
0x18005d336  mov     [rsp+120h+var_D8], edx; ULONG
0x18005d33a  mov     edx, [rbp+37h+FileAttributes]
0x18005d340  mov     [rsp+120h+var_E0], edx; ULONG
0x18005d344  mov     rdx, [rbp+37h+AllocationSize]
0x18005d348  mov     [rsp+120h+var_E8], rdx; PLARGE_INTEGER
0x18005d34d  mov     rdx, [rbp+37h+IoStatusBlock]
0x18005d351  mov     [rsp+120h+var_F0], rdx; IoStatusBlock
0x18005d356  mov     edx, [rbp+37h+DesiredAccess]
0x18005d359  movups  xmmword ptr [rbp+37h+var_68.ObjectName], xmm0
0x18005d35d  mov     [rsp+120h+var_F8], r13; ObjectAttributes
0x18005d362  mov     [rsp+120h+var_100], edx; DesiredAccess
0x18005d366  mov     rdx, r12; __int64
0x18005d369  movups  xmmword ptr [rbp+37h+var_68.Length], xmm0
0x18005d36d  mov     [rbp+37h+var_90], r14
0x18005d371  movups  xmmword ptr [rbp+37h+var_68+1Ch], xmm0
0x18005d375  mov     [rbp+37h+EcpContext], r14
0x18005d379  mov     [rbp+37h+var_70], r14
0x18005d37d  mov     [rbp+37h+var_80], r14
0x18005d381  mov     [rbp+37h+var_78], r14
0x18005d385  call    FltpCreateFile
0x18005d38a  mov     ebx, eax
0x18005d38c  add     eax, 3FFFFC98h
0x18005d391  cmp     eax, 1
0x18005d394  jbe     loc_18007959C
0x18005d39a  mov     eax, ebx
0x18005d39c  mov     rbx, [rsp+120h+arg_8]
0x18005d3a4  add     rsp, 0F0h
0x18005d3ab  pop     r15
0x18005d3ad  pop     r14
0x18005d3af  pop     r13
0x18005d3b1  pop     r12
0x18005d3b3  pop     rdi
0x18005d3b4  pop     rsi
0x18005d3b5  pop     rbp
0x18005d3b6  retn
0x18007959c  test    rsi, rsi
0x18007959f  jz      loc_18005D39A
0x1800795a5  mov     rcx, [rsi+8]; EcpList
0x1800795a9  test    rcx, rcx
0x1800795ac  jz      loc_18005D39A
0x1800795b2  xor     r9d, r9d; EcpContextSize
0x1800795b5  lea     r8, [rbp+37h+EcpContext]; EcpContext
0x1800795b9  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x1800795c0  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1800795c7  nop     dword ptr [rax+rax+00h]
0x1800795cc  mov     r8d, 0CF8h
0x1800795d2  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800795d9  mov     ecx, eax
0x1800795db  xor     r9d, r9d
0x1800795de  call    FltpDbgStatus
0x1800795e3  test    eax, eax
0x1800795e5  js      loc_18005D39A
0x1800795eb  mov     rdx, [r13+10h]
0x1800795ef  lea     rcx, [rbp+37h+var_90]
0x1800795f3  mov     r8, [rsi+8]
0x1800795f7  movzx   edx, word ptr [rdx]
0x1800795fa  call    FltpGenerateDeviceHintEcp
0x1800795ff  mov     r8d, 0D05h
0x180079605  mov     [rbp+37h+var_9C], eax
0x180079608  xor     r9d, r9d
0x18007960b  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079612  mov     ecx, eax
0x180079614  call    FltpDbgStatus
0x180079619  test    eax, eax
0x18007961b  jns     short loc_180079625
0x18007961d  mov     eax, [rbp+37h+var_9C]
0x180079620  jmp     loc_18005D39C
0x180079625  mov     eax, [rbp+37h+Flags]
0x18007962b  mov     rdx, r12; __int64
0x18007962e  mov     r9, [rbp+37h+arg_18]
0x180079632  mov     r8, [rbp+37h+FileHandle]; FileHandle
0x180079636  mov     rcx, [rbp+37h+FltObject]; FltObject
0x18007963a  mov     qword ptr [rsp+120h+EcpContextSize], rsi; EcpContextSize
0x18007963f  mov     [rsp+120h+var_B0], eax; ULONG
0x180079643  mov     eax, [rbp+37h+EaLength]
0x180079649  mov     [rsp+120h+var_B8], eax; ULONG
0x18007964d  mov     rax, [rbp+37h+EaBuffer]
0x180079654  mov     [rsp+120h+var_C0], rax; PVOID
0x180079659  mov     eax, [rbp+37h+CreateOptions]
0x18007965f  mov     [rsp+120h+var_C8], eax; ULONG
0x180079663  mov     eax, [rbp+37h+CreateDisposition]
0x180079669  mov     [rsp+120h+var_D0], eax; ULONG
0x18007966d  mov     eax, [rbp+37h+ShareAccess]
0x180079673  mov     [rsp+120h+var_D8], eax; ULONG
0x180079677  mov     eax, [rbp+37h+FileAttributes]
0x18007967d  mov     [rsp+120h+var_E0], eax; ULONG
0x180079681  mov     rax, [rbp+37h+AllocationSize]
0x180079685  mov     [rsp+120h+var_E8], rax; PLARGE_INTEGER
0x18007968a  mov     rax, [rbp+37h+IoStatusBlock]
0x18007968e  mov     [rsp+120h+var_F0], rax; IoStatusBlock
0x180079693  mov     eax, [rbp+37h+DesiredAccess]
0x180079696  mov     [rsp+120h+var_F8], r13; ObjectAttributes
0x18007969b  mov     [rsp+120h+var_100], eax; DesiredAccess
0x18007969f  call    FltpCreateFile
0x1800796a4  mov     [rbp+37h+var_98], eax
0x1800796a7  lea     ecx, [rax+3FFFFC98h]
0x1800796ad  cmp     ecx, 1
0x1800796b0  jbe     short loc_1800796CA
0x1800796b2  cmp     eax, 0C0000496h
0x1800796b7  jz      short loc_1800796CA
0x1800796b9  mov     rcx, [rsi+8]
0x1800796bd  call    FltpCleanupDeviceHintEcp
0x1800796c2  mov     eax, [rbp+37h+var_98]
0x1800796c5  jmp     loc_18005D39C
0x1800796ca  mov     [rbp+37h+var_9C], 1
0x1800796d1  mov     rcx, [rbp+37h+var_90]; EcpContext
0x1800796d5  call    cs:__imp_FsRtlIsEcpAcknowledged
0x1800796dc  nop     dword ptr [rax+rax+00h]
0x1800796e1  test    al, al
0x1800796e3  jz      loc_180079902
0x1800796e9  cmp     [rbp+37h+var_98], 0C0000496h
0x1800796f0  jnz     short loc_180079725
0x1800796f2  mov     rcx, [rbp+37h+var_90]
0x1800796f6  mov     dl, 1
0x1800796f8  call    FltpResetDeviceHintEcp
0x1800796fd  xor     r9d, r9d
0x180079700  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079707  mov     r8d, 0D42h
0x18007970d  mov     ecx, eax
0x18007970f  mov     r12d, eax
0x180079712  call    FltpDbgStatus
0x180079717  test    eax, eax
0x180079719  js      loc_1800798BA
0x18007971f  mov     [rbp+37h+var_A0], 0
0x180079723  jmp     short loc_180079799
0x180079725  mov     rdx, [r12+48h]
0x18007972a  lea     rax, [rbp+37h+var_78]
0x18007972e  mov     r12, [rbp+37h+var_90]
0x180079732  lea     r9, [rbp+37h+var_80]
0x180079736  mov     rcx, r12
0x180079739  mov     qword ptr [rsp+120h+var_100], rax
0x18007973e  lea     r8, [rbp+37h+var_70]
0x180079742  call    FltpGetTargetInfo
0x180079747  xor     r9d, r9d
0x18007974a  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079751  mov     r8d, 0D5Bh
0x180079757  mov     ecx, eax
0x180079759  mov     edi, eax
0x18007975b  call    FltpDbgStatus
0x180079760  test    eax, eax
0x180079762  js      loc_180079900
0x180079768  mov     rdi, [rbp+37h+var_70]
0x18007976c  mov     rcx, [rbp+37h+EcpContext]; EcpContext
0x180079770  test    rdi, rdi
0x180079773  jz      loc_1800798DF
0x180079779  test    byte ptr [rcx+18h], 1
0x18007977d  jz      loc_1800798DF
0x180079783  xor     edx, edx
0x180079785  mov     rcx, r12
0x180079788  call    FltpResetDeviceHintEcp
0x18007978d  mov     r15, [rbp+37h+var_80]
0x180079791  mov     r14, [rbp+37h+var_78]
0x180079795  mov     [rbp+37h+var_A0], 1
0x180079799  movups  xmm0, xmmword ptr [r13+0]
0x18007979e  mov     r9, [rbp+37h+arg_18]
0x1800797a2  lea     rax, [r14+8]
0x1800797a6  mov     r8, [rbp+37h+FileHandle]; FileHandle
0x1800797aa  mov     rdx, rdi; __int64
0x1800797ad  mov     rcx, [rbp+37h+FltObject]; FltObject
0x1800797b1  mov     r12, rdi
0x1800797b4  mov     qword ptr [rsp+120h+EcpContextSize], rsi; EcpContextSize
0x1800797b9  movups  xmmword ptr [rbp+37h+var_68.Length], xmm0
0x1800797bd  movups  xmm1, xmmword ptr [r13+10h]
0x1800797c2  movups  xmmword ptr [rbp+37h+var_68.ObjectName], xmm1
0x1800797c6  movups  xmm0, xmmword ptr [r13+20h]
0x1800797cb  mov     [rbp+37h+var_68.ObjectName], rax
0x1800797cf  mov     eax, [rbp+37h+Flags]
0x1800797d5  mov     [rsp+120h+var_B0], eax; ULONG
0x1800797d9  mov     eax, [rbp+37h+EaLength]
0x1800797df  mov     [rsp+120h+var_B8], eax; ULONG
0x1800797e3  mov     rax, [rbp+37h+EaBuffer]
0x1800797ea  mov     [rsp+120h+var_C0], rax; PVOID
0x1800797ef  mov     eax, [rbp+37h+CreateOptions]
0x1800797f5  mov     [rsp+120h+var_C8], eax; ULONG
0x1800797f9  mov     eax, [rbp+37h+CreateDisposition]
0x1800797ff  mov     [rsp+120h+var_D0], eax; ULONG
0x180079803  mov     eax, [rbp+37h+ShareAccess]
0x180079809  mov     [rsp+120h+var_D8], eax; ULONG
0x18007980d  mov     eax, [rbp+37h+FileAttributes]
0x180079813  mov     [rsp+120h+var_E0], eax; ULONG
0x180079817  mov     rax, [rbp+37h+AllocationSize]
0x18007981b  mov     [rsp+120h+var_E8], rax; PLARGE_INTEGER
0x180079820  mov     rax, [rbp+37h+IoStatusBlock]
0x180079824  mov     [rsp+120h+var_F0], rax; IoStatusBlock
0x180079829  lea     rax, [rbp+37h+var_68]
0x18007982d  mov     [rsp+120h+var_F8], rax; ObjectAttributes
0x180079832  mov     eax, [rbp+37h+DesiredAccess]
0x180079835  mov     [rsp+120h+var_100], eax; DesiredAccess
0x180079839  movups  xmmword ptr [rbp+37h+var_68.SecurityDescriptor], xmm0
0x18007983d  call    FltpCreateFile
0x180079842  xor     r9d, r9d
0x180079845  mov     [rbp+37h+var_98], eax
0x180079848  mov     r8d, 0D9Dh
0x18007984e  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079855  mov     ecx, eax
0x180079857  mov     r13d, eax
0x18007985a  call    FltpDbgStatus
0x18007985f  test    eax, eax
0x180079861  jns     short loc_1800798BF
0x180079863  lea     eax, [r13+3FFFFC98h]
0x18007986a  cmp     eax, 1
0x18007986d  jbe     short loc_18007988B
0x18007986f  cmp     r13d, 0C0000496h
0x180079876  jz      short loc_18007988B
0x180079878  mov     r8, r14
0x18007987b  mov     rdx, r15
0x18007987e  mov     rcx, rdi
0x180079881  mov     ebx, r13d
0x180079884  call    FltpCleanupTargetInfo
0x180079889  jmp     short loc_180079902
0x18007988b  mov     r8, r14
0x18007988e  mov     rdx, r15
0x180079891  mov     rcx, rdi
0x180079894  call    FltpCleanupTargetInfo
0x180079899  mov     ecx, [rbp+37h+var_9C]
0x18007989c  cmp     [rbp+37h+var_A0], 0
0x1800798a0  lea     eax, [rcx+1]
0x1800798a3  cmovz   ax, cx
0x1800798a7  cmp     ax, 40h ; '@'
0x1800798ab  jnb     short loc_180079902
0x1800798ad  lea     r13, [rbp+37h+var_68]
0x1800798b1  mov     word ptr [rbp+37h+var_9C], ax
0x1800798b5  jmp     loc_1800796D1
0x1800798ba  mov     ebx, r12d
0x1800798bd  jmp     short loc_180079902
0x1800798bf  mov     rcx, [rbp+37h+EcpContext]; EcpContext
0x1800798c3  mov     [rcx], rdi
0x1800798c6  mov     [rcx+8], r15
0x1800798ca  mov     [rcx+10h], r14
0x1800798ce  call    cs:__imp_FsRtlAcknowledgeEcp
0x1800798d5  nop     dword ptr [rax+rax+00h]
0x1800798da  mov     ebx, r13d
0x1800798dd  jmp     short loc_180079902
0x1800798df  mov     rax, [rbp+37h+var_80]
0x1800798e3  mov     [rcx+8], rax
0x1800798e7  mov     rax, [rbp+37h+var_78]
0x1800798eb  mov     [rcx+10h], rax
0x1800798ef  mov     [rcx], rdi
0x1800798f2  call    cs:__imp_FsRtlAcknowledgeEcp
0x1800798f9  nop     dword ptr [rax+rax+00h]
0x1800798fe  jmp     short loc_180079902
0x180079900  mov     ebx, edi
0x180079902  mov     rcx, [rsi+8]
0x180079906  call    FltpCleanupDeviceHintEcp
0x18007990b  nop
0x18007990c  jmp     loc_18005D39A
```
