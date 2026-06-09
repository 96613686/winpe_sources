# MdaDevFcbXXXControlFile

- ea: `0x140017770`
- end: `0x140017b61`
- name: `MdaDevFcbXXXControlFile`
- size: `1009`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140017628`
- `0x140017770`
- `0x140017b68`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14001786c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001786c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400178e1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400178e1`
- `ntoskrnl!ExGetPreviousMode` at `0x140017841`
- `ntoskrnl!ExGetPreviousMode` at `0x140017841`
- `ntoskrnl!SeAccessCheck` at `0x1400178ce`
- `ntoskrnl!SeAccessCheck` at `0x1400178ce`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140017878`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140017878`
- `rdbss!RxStopMinirdr` at `0x1400179a7`
- `rdbss!RxStopMinirdr` at `0x1400179a7`

## pseudocode

```c
__int64 __fastcall MdaDevFcbXXXControlFile(PRX_CONTEXT RxContext)
{
  PMRX_FOBX pFobx; // rbp
  PIO_STACK_LOCATION CurrentIrpSp; // rbx
  PNON_PAGED_FCB NonPagedFcb; // r15
  __int64 MajorFunction; // r9
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // ebx
  DWORD LowPart; // r14d
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v11; // bl
  int RdbssDbgExtension; // eax
  NTSTATUS v13; // eax
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-48h] BYREF
  int AccessStatus; // [rsp+A0h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp+10h] BYREF

  pFobx = RxContext->pFobx;
  CurrentIrpSp = RxContext->CurrentIrpSp;
  NonPagedFcb = RxContext->NonPagedFcb;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessStatus = -1073741790;
  GrantedAccess = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
  MajorFunction = CurrentIrpSp->MajorFunction;
  if ( CurrentIrpSp->MajorFunction != 13 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_9;
    v7 = 19;
    goto LABEL_8;
  }
  if ( CurrentIrpSp->MinorFunction )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_9;
    MajorFunction = CurrentIrpSp->MinorFunction;
    v7 = 18;
LABEL_8:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids, MajorFunction);
LABEL_9:
    v8 = -1073741808;
    goto LABEL_66;
  }
  LowPart = CurrentIrpSp->Parameters.Read.ByteOffset.LowPart;
  if ( ExGetPreviousMode() != 1
    || ((LowPart - 1345856) & 0xFFFFFFFB) != 0
    || (SeCaptureSubjectContext(&SubjectContext),
        GenericMapping = IoGetFileObjectGenericMapping(),
        v11 = SeAccessCheck(
                &NonPagedFcb[4].PagingIoResource.OwnerTable,
                &SubjectContext,
                0,
                0x120116u,
                0,
                0,
                GenericMapping,
                1,
                &GrantedAccess,
                &AccessStatus),
        SeReleaseSubjectContext(&SubjectContext),
        v11) )
  {
    v8 = 0;
  }
  else
  {
    v8 = AccessStatus;
    if ( AccessStatus < 0 )
      goto LABEL_66;
  }
  switch ( LowPart )
  {
    case 0x140948u:
      if ( pFobx )
      {
        v8 = MdaDeleteConnection(RxContext, (char *)&RxContext->RealDevice + 3);
        if ( v8 >= 0 )
          goto LABEL_58;
      }
      else
      {
        v8 = -1073741811;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_66;
      v15 = 13;
      v16 = (unsigned int)v8;
LABEL_65:
      WPP_SF_d(v14->AttachedDevice, v15, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids, v16);
      goto LABEL_66;
    case 0x14094Cu:
      if ( LODWORD(RxContext->NonPagedFcb->BufferedLocksResource.ExclusiveWaiters) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
LABEL_54:
      if ( v8 < 0 )
        goto LABEL_66;
      goto LABEL_58;
    case 0x148940u:
      if ( pFobx )
      {
        v8 = -1073741808;
      }
      else if ( v8 >= 0 )
      {
        v8 = MdaExternalStart(RxContext);
        if ( v8 >= 0 )
          goto LABEL_58;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids,
          (unsigned int)v8);
      goto LABEL_54;
  }
  if ( LowPart != 1345860 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids, LowPart);
    RxContext->pFobx = 0;
    v8 = -1073741822;
LABEL_66:
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      v18 = 21;
      goto LABEL_69;
    }
    return (unsigned int)v8;
  }
  if ( pFobx )
    goto LABEL_9;
  if ( v8 < 0 )
    goto LABEL_66;
  if ( LODWORD(RxContext->NonPagedFcb->BufferedLocksResource.ExclusiveWaiters) )
  {
LABEL_31:
    v8 = -2147483613;
    goto LABEL_66;
  }
  RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
  if ( (RdbssDbgExtension & 0x200) == 0 )
  {
    v8 = -1069481981;
    BYTE3(RxContext->RealDevice) = 1;
    goto LABEL_66;
  }
  if ( (RdbssDbgExtension & 2) == 0 )
    __int2c();
  v13 = RxStopMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
  v8 = v13;
  if ( v13 < 0 )
  {
    __int2c();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_66;
    v15 = 12;
    v16 = (unsigned int)v13;
    goto LABEL_65;
  }
LABEL_58:
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    v18 = 20;
LABEL_69:
    WPP_SF_d(v17->AttachedDevice, v18, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140017770  mov     rax, rsp
0x140017773  mov     [rax+20h], rbx
0x140017777  push    rbp
0x140017778  push    rdi
0x140017779  push    r13
0x14001777b  push    r14
0x14001777d  push    r15
0x14001777f  sub     rsp, 70h
0x140017783  mov     rbp, [rcx+40h]
0x140017787  xorps   xmm0, xmm0
0x14001778a  mov     rbx, [rcx+30h]
0x14001778e  mov     rdi, rcx
0x140017791  mov     r15, [rcx+50h]
0x140017795  movups  xmmword ptr [rax-48h], xmm0
0x140017799  mov     dword ptr [rax+8], 0C0000022h
0x1400177a0  movups  xmmword ptr [rax-38h], xmm0
0x1400177a4  mov     dword ptr [rax+10h], 0
0x1400177ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177b2  lea     r13, WPP_GLOBAL_Control
0x1400177b9  cmp     rcx, r13
0x1400177bc  jz      short loc_1400177DA
0x1400177be  mov     eax, [rcx+2Ch]
0x1400177c1  test    al, 8
0x1400177c3  jz      short loc_1400177DA
0x1400177c5  mov     rcx, [rcx+18h]
0x1400177c9  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x1400177d0  mov     edx, 0Ah
0x1400177d5  call    WPP_SF_
0x1400177da  movzx   r9d, byte ptr [rbx]
0x1400177de  mov     ecx, r9d
0x1400177e1  sub     ecx, 0Dh
0x1400177e4  jz      short loc_140017818
0x1400177e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177ed  cmp     rcx, r13
0x1400177f0  jz      short loc_14001780E
0x1400177f2  mov     eax, [rcx+2Ch]
0x1400177f5  test    al, 2
0x1400177f7  jz      short loc_14001780E
0x1400177f9  mov     edx, 13h
0x1400177fe  mov     rcx, [rcx+18h]
0x140017802  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017809  call    WPP_SF_d
0x14001780e  mov     ebx, 0C0000010h
0x140017813  jmp     loc_140017B1E
0x140017818  movzx   edx, byte ptr [rbx+1]
0x14001781c  test    dl, dl
0x14001781e  jz      short loc_14001783D
0x140017820  mov     rcx, cs:WPP_GLOBAL_Control
0x140017827  cmp     rcx, r13
0x14001782a  jz      short loc_14001780E
0x14001782c  mov     eax, [rcx+2Ch]
0x14001782f  test    al, 1
0x140017831  jz      short loc_14001780E
0x140017833  mov     r9d, edx
0x140017836  mov     edx, 12h
0x14001783b  jmp     short loc_1400177FE
0x14001783d  mov     r14d, [rbx+18h]
0x140017841  call    cs:__imp_ExGetPreviousMode
0x140017848  nop     dword ptr [rax+rax+00h]
0x14001784d  cmp     al, 1
0x14001784f  jnz     loc_140017902
0x140017855  lea     eax, [r14-148940h]
0x14001785c  test    eax, 0FFFFFFFBh
0x140017861  jnz     loc_140017902
0x140017867  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x14001786c  call    cs:__imp_SeCaptureSubjectContext
0x140017873  nop     dword ptr [rax+rax+00h]
0x140017878  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001787f  nop     dword ptr [rax+rax+00h]
0x140017884  lea     rdx, [rsp+98h+arg_0]
0x14001788c  mov     r9d, 120116h; DesiredAccess
0x140017892  mov     [rsp+98h+AccessStatus], rdx; AccessStatus
0x140017897  lea     rcx, [r15+7F8h]; SecurityDescriptor
0x14001789e  lea     rdx, [rsp+98h+arg_8]
0x1400178a6  xor     r8d, r8d; SubjectContextLocked
0x1400178a9  mov     [rsp+98h+GrantedAccess], rdx; GrantedAccess
0x1400178ae  lea     rdx, [rsp+98h+SubjectContext]; SubjectSecurityContext
0x1400178b3  mov     [rsp+98h+AccessMode], 1; AccessMode
0x1400178b8  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x1400178bd  mov     [rsp+98h+Privileges], 0; Privileges
0x1400178c6  mov     [rsp+98h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400178ce  call    cs:__imp_SeAccessCheck
0x1400178d5  nop     dword ptr [rax+rax+00h]
0x1400178da  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x1400178df  mov     bl, al
0x1400178e1  call    cs:__imp_SeReleaseSubjectContext
0x1400178e8  nop     dword ptr [rax+rax+00h]
0x1400178ed  test    bl, bl
0x1400178ef  jnz     short loc_140017902
0x1400178f1  mov     ebx, [rsp+98h+arg_0]
0x1400178f8  test    ebx, ebx
0x1400178fa  js      loc_140017B1E
0x140017900  jmp     short loc_140017904
0x140017902  xor     ebx, ebx
0x140017904  mov     eax, r14d
0x140017907  sub     eax, 140948h
0x14001790c  jz      loc_140017ABD
0x140017912  sub     eax, 4
0x140017915  jz      loc_140017A4D
0x14001791b  sub     eax, 7FF4h
0x140017920  jz      loc_1400179F6
0x140017926  cmp     eax, 4
0x140017929  jz      short loc_140017968
0x14001792b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017932  cmp     rcx, r13
0x140017935  jz      short loc_140017956
0x140017937  mov     eax, [rcx+2Ch]
0x14001793a  test    al, 1
0x14001793c  jz      short loc_140017956
0x14001793e  mov     rcx, [rcx+18h]
0x140017942  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017949  mov     edx, 10h
0x14001794e  mov     r9d, r14d
0x140017951  call    WPP_SF_d
0x140017956  mov     qword ptr [rdi+40h], 0
0x14001795e  mov     ebx, 0C0000002h
0x140017963  jmp     loc_140017B1E
0x140017968  test    rbp, rbp
0x14001796b  jnz     loc_14001780E
0x140017971  test    ebx, ebx
0x140017973  js      loc_140017B1E
0x140017979  mov     rax, [rdi+50h]
0x14001797d  cmp     [rax+198h], ebp
0x140017983  jbe     short loc_14001798F
0x140017985  mov     ebx, 80000023h
0x14001798a  jmp     loc_140017B1E
0x14001798f  mov     eax, [rdi+78h]
0x140017992  bt      eax, 9
0x140017996  jnb     short loc_1400179E8
0x140017998  bt      eax, 1
0x14001799c  jb      short loc_1400179A0
0x14001799e  int     2Ch; Windows NT - assertion failure
0x1400179a0  lea     rdx, [rdi+23h]; PostToFsp
0x1400179a4  mov     rcx, rdi; RxContext
0x1400179a7  call    cs:__imp_RxStopMinirdr
0x1400179ae  nop     dword ptr [rax+rax+00h]
0x1400179b3  mov     ebx, eax
0x1400179b5  test    eax, eax
0x1400179b7  jns     loc_140017AD4
0x1400179bd  int     2Ch; Windows NT - assertion failure
0x1400179bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400179c6  cmp     rcx, r13
0x1400179c9  jz      loc_140017B1E
0x1400179cf  mov     edx, [rcx+2Ch]
0x1400179d2  test    dl, 1
0x1400179d5  jz      loc_140017B1E
0x1400179db  mov     edx, 0Ch
0x1400179e0  mov     r9d, eax
0x1400179e3  jmp     loc_140017B0E
0x1400179e8  mov     ebx, 0C0410003h
0x1400179ed  mov     byte ptr [rdi+23h], 1
0x1400179f1  jmp     loc_140017B1E
0x1400179f6  test    rbp, rbp
0x1400179f9  jz      short loc_140017A02
0x1400179fb  mov     ebx, 0C0000010h
0x140017a00  jmp     short loc_140017A18
0x140017a02  test    ebx, ebx
0x140017a04  js      short loc_140017A18
0x140017a06  mov     rcx, rdi; RxContext
0x140017a09  call    MdaExternalStart
0x140017a0e  mov     ebx, eax
0x140017a10  test    eax, eax
0x140017a12  jns     loc_140017AD4
0x140017a18  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a1f  cmp     rcx, r13
0x140017a22  jz      loc_140017AB7
0x140017a28  mov     eax, [rcx+2Ch]
0x140017a2b  test    al, 1
0x140017a2d  jz      loc_140017AB7
0x140017a33  mov     rcx, [rcx+18h]
0x140017a37  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017a3e  mov     edx, 0Bh
0x140017a43  mov     r9d, ebx
0x140017a46  call    WPP_SF_d
0x140017a4b  jmp     short loc_140017AB7
0x140017a4d  mov     rax, [rdi+50h]
0x140017a51  cmp     dword ptr [rax+198h], 0
0x140017a58  jbe     short loc_140017A8F
0x140017a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a61  cmp     rcx, r13
0x140017a64  jz      loc_140017985
0x140017a6a  mov     eax, [rcx+2Ch]
0x140017a6d  test    al, 1
0x140017a6f  jz      loc_140017985
0x140017a75  mov     rcx, [rcx+18h]
0x140017a79  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017a80  mov     edx, 0Eh
0x140017a85  call    WPP_SF_
0x140017a8a  jmp     loc_140017985
0x140017a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a96  cmp     rcx, r13
0x140017a99  jz      short loc_140017AB7
0x140017a9b  mov     eax, [rcx+2Ch]
0x140017a9e  test    al, 4
0x140017aa0  jz      short loc_140017AB7
0x140017aa2  mov     rcx, [rcx+18h]
0x140017aa6  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017aad  mov     edx, 0Fh
0x140017ab2  call    WPP_SF_
0x140017ab7  test    ebx, ebx
0x140017ab9  js      short loc_140017B1E
0x140017abb  jmp     short loc_140017AD4
0x140017abd  test    rbp, rbp
0x140017ac0  jz      short loc_140017AEE
0x140017ac2  lea     rdx, [rdi+23h]
0x140017ac6  mov     rcx, rdi
0x140017ac9  call    MdaDeleteConnection
0x140017ace  mov     ebx, eax
0x140017ad0  test    eax, eax
0x140017ad2  js      short loc_140017AF3
0x140017ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140017adb  cmp     rcx, r13
0x140017ade  jz      short loc_140017B49
0x140017ae0  mov     eax, [rcx+2Ch]
0x140017ae3  test    al, 8
0x140017ae5  jz      short loc_140017B49
0x140017ae7  mov     edx, 14h
0x140017aec  jmp     short loc_140017B36
0x140017aee  mov     ebx, 0C000000Dh
0x140017af3  mov     rcx, cs:WPP_GLOBAL_Control
0x140017afa  cmp     rcx, r13
0x140017afd  jz      short loc_140017B1E
0x140017aff  mov     eax, [rcx+2Ch]
0x140017b02  test    al, 1
0x140017b04  jz      short loc_140017B1E
0x140017b06  mov     edx, 0Dh
0x140017b0b  mov     r9d, ebx
0x140017b0e  mov     rcx, [rcx+18h]
0x140017b12  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017b19  call    WPP_SF_d
0x140017b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b25  cmp     rcx, r13
0x140017b28  jz      short loc_140017B49
0x140017b2a  mov     eax, [rcx+2Ch]
0x140017b2d  test    al, 2
0x140017b2f  jz      short loc_140017B49
0x140017b31  mov     edx, 15h
0x140017b36  mov     rcx, [rcx+18h]
0x140017b3a  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017b41  mov     r9d, ebx
0x140017b44  call    WPP_SF_d
0x140017b49  mov     eax, ebx
0x140017b4b  mov     rbx, [rsp+98h+arg_18]
0x140017b53  add     rsp, 70h
0x140017b57  pop     r15
0x140017b59  pop     r14
0x140017b5b  pop     r13
0x140017b5d  pop     rdi
0x140017b5e  pop     rbp
0x140017b5f  retn
```
