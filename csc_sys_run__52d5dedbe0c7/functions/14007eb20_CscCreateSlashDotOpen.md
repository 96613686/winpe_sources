# CscCreateSlashDotOpen

- ea: `0x14007eb20`
- end: `0x14007f3ca`
- name: `CscCreateSlashDotOpen`
- size: `2218`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140062b70`

## callees

- `0x14000a634`
- `0x14000e100`
- `0x14000f8b0`
- `0x1400119d0`
- `0x140012118`
- `0x140012860`
- `0x14001362c`
- `0x1400190ec`
- `0x14001b710`
- `0x14001cd9c`
- `0x14002f010`
- `0x14007eb20`
- `0x14007f3d0`
- `0x14007f444`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007eef7`
- `ntoskrnl!ExAllocatePool2` at `0x14007f073`
- `ntoskrnl!ExAllocatePool2` at `0x14007f217`
- `ntoskrnl!ExAllocatePool2` at `0x14007eef7`
- `ntoskrnl!ExAllocatePool2` at `0x14007f073`
- `ntoskrnl!ExAllocatePool2` at `0x14007f217`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f26b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f26b`
- `ntoskrnl!SeAccessCheck` at `0x14007ece7`
- `ntoskrnl!SeAccessCheck` at `0x14007ece7`
- `ntoskrnl!SeTokenIsAdmin` at `0x14007ec33`
- `ntoskrnl!SeTokenIsAdmin` at `0x14007ec33`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007f246`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007f259`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007f246`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007f259`
- `rdbss!RxCreateNetFobx` at `0x14007edb1`
- `rdbss!RxCreateNetFobx` at `0x14007edb1`
- `rdbss!RxSubjectContextFromRxContext` at `0x14007ec62`
- `rdbss!RxSubjectContextFromRxContext` at `0x14007ef38`
- `rdbss!RxSubjectContextFromRxContext` at `0x14007ec62`
- `rdbss!RxSubjectContextFromRxContext` at `0x14007ef38`
- `rdbss!RxFinishFcbInitialization` at `0x14007f052`
- `rdbss!RxFinishFcbInitialization` at `0x14007f052`

## pseudocode

```c
__int64 __fastcall CscCreateSlashDotOpen(PRX_CONTEXT RxContext, __int64 a2)
{
  PMRX_FCB pFcb; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // r15
  int Blink; // r14d
  char v8; // dl
  PMRX_SRV_OPEN pRelevantSrvOpen; // r12
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int Entry; // ebx
  struct _LIST_ENTRY *v14; // rbx
  DWORD v15; // r14d
  __int64 v16; // r9
  __int64 v17; // rdx
  void *v18; // rcx
  PIRP CurrentIrp; // rax
  void *v20; // rcx
  int v21; // ebx
  PMRX_FCB v22; // r14
  PMRX_FCB v23; // r13
  struct _MRX_FOBX_ *NetFobx; // rax
  int v25; // eax
  int v26; // r14d
  _DWORD *Pool2; // rax
  struct _FCB_INIT_PACKET *v29; // r8
  struct _UNICODE_STRING *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  PMRX_FCB v33; // rdi
  PIO_STACK_LOCATION CurrentIrpSp; // rax
  __int64 v35; // rdx
  PFILE_OBJECT FileObject; // rsi
  struct _UNICODE_STRING v37; // xmm0
  __int64 v38; // rcx
  int v39; // eax
  KPROCESSOR_MODE AccessMode; // [rsp+38h] [rbp-41h]
  char v41; // [rsp+50h] [rbp-29h]
  PMRX_FCB Fcb; // [rsp+58h] [rbp-21h]
  int AccessStatus[2]; // [rsp+60h] [rbp-19h] BYREF
  DWORD GrantedAccess[2]; // [rsp+68h] [rbp-11h] BYREF
  PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-1h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+88h] [rbp+Fh] BYREF

  SubjectSecurityContext = 0;
  pFcb = RxContext->pFcb;
  v4 = (_QWORD *)(a2 + 344);
  v5 = 0;
  Fcb = pFcb;
  *(_QWORD *)AccessStatus = 0;
  Blink = (int)RxContext->WorkQueueItem.List.Blink;
  v8 = 0;
  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  v41 = 0;
  if ( (Blink & 0x10) != 0 || (*((_DWORD *)&RxContext->9 + 35) & 0x1000) != 0 )
  {
    Entry = -1073741811;
    v26 = 3800;
    goto LABEL_59;
  }
  *(_QWORD *)GrantedAccess = (char *)pFcb + 360;
  v10 = CscCreateSlashDotOpenCheckReparse(&pFcb[2].Header.Resource);
  Entry = v10;
  if ( v10 < 0 )
  {
    v8 = 0;
    v26 = 3812;
    goto LABEL_59;
  }
  if ( v10 == 260 )
  {
    *(_QWORD *)&GenericMapping.GenericExecute = L"\\Device\\Mup";
    CurrentIrpSp = RxContext->CurrentIrpSp;
    Destination = 0;
    v35 = (unsigned __int16)(**(_WORD **)GrantedAccess + 22);
    *(_QWORD *)&GenericMapping.GenericRead = 1572886;
    FileObject = CurrentIrpSp->FileObject;
    Destination.MaximumLength = v35;
    Destination.Buffer = (PWSTR)ExAllocatePool2(66, v35, 1061124178, v12);
    if ( Destination.Buffer )
    {
      RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&GenericMapping);
      RtlAppendUnicodeStringToString(&Destination, *(PCUNICODE_STRING *)GrantedAccess);
      ExFreePoolWithTag(FileObject->FileName.Buffer, 0);
      v26 = 3850;
      FileObject->FileName.Buffer = 0;
      v37 = Destination;
      FileObject->RelatedFileObject = 0;
      FileObject->FileName = v37;
      goto LABEL_35;
    }
    Entry = -1073741670;
    v8 = 0;
    v26 = 3833;
    goto LABEL_59;
  }
  v14 = (struct _LIST_ENTRY *)(Blink | 8u);
  *(_QWORD *)&Destination.Length = v14;
  RxContext->WorkQueueItem.List.Blink = v14;
  v15 = GrantedAccess[0];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      56,
      (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (_DWORD)Fcb,
      (char)pRelevantSrvOpen,
      *(__int64 *)GrantedAccess);
  CscGetContexts(RxContext, v4, v11, v12);
  if ( !v4[1] )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(256, 120, 1061124178, v16);
    v4[1] = Pool2;
    if ( !Pool2 )
    {
      Entry = -1073741670;
      v8 = 0;
      v26 = 3881;
      goto LABEL_59;
    }
    *(_QWORD *)&Fcb->Attributes = Pool2;
    *Pool2 = 7924385;
    *(_DWORD *)(v4[1] + 4LL) = 64;
  }
  if ( !v4[2] )
  {
    v30 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 48, 1061124178, v16);
    v4[2] = v30;
    if ( !v30 )
    {
      Entry = -1073741670;
      v8 = 0;
      v26 = 3900;
      goto LABEL_59;
    }
    pRelevantSrvOpen->pAlreadyPrefixedName = v30;
    *(_DWORD *)&v30->Length = 3205794;
  }
  *(_DWORD *)(v4[2] + 24LL) |= 1u;
  *(_DWORD *)(v4[2] + 32LL) = (_DWORD)v14;
  v17 = *(_QWORD *)(*((_QWORD *)&RxContext->9 + 18) + 8LL);
  v18 = *(void **)(v17 + 32);
  if ( !v18 )
    v18 = *(void **)(v17 + 48);
  if ( SeTokenIsAdmin(v18) )
    *(_DWORD *)(v4[2] + 24LL) |= 0x4000u;
  if ( *(char *)(a2 + 533) < 0 )
  {
    v38 = v4[2];
    v39 = *(_DWORD *)(v38 + 24);
    if ( (v39 & 0x4000) == 0 )
    {
      Entry = -1073741790;
      v8 = 0;
      v26 = 3929;
      goto LABEL_59;
    }
    *(_DWORD *)(v38 + 24) = v39 | 0x800;
  }
  Entry = RxSubjectContextFromRxContext(RxContext, &SubjectSecurityContext);
  if ( Entry < 0 )
  {
    v8 = 0;
    v26 = 3944;
    goto LABEL_59;
  }
  CurrentIrp = RxContext->CurrentIrp;
  AccessStatus[0] = 0;
  AccessMode = CurrentIrp->RequestorMode;
  v20 = *(void **)(CscDevExtn + 1416);
  GrantedAccess[0] = 0;
  GenericMapping.GenericRead = 131073;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031617;
  v21 = SeAccessCheck(
          v20,
          SubjectSecurityContext,
          0,
          1u,
          0,
          0,
          &GenericMapping,
          AccessMode,
          GrantedAccess,
          AccessStatus);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids,
      (unsigned int)AccessStatus[0],
      v21);
  if ( (_BYTE)v21 )
    *(_DWORD *)(v4[2] + 24LL) |= 0x2000u;
  ++*(_DWORD *)(v4[1] + 20LL);
  LODWORD(pRelevantSrvOpen->Key) |= 0x1080u;
  v5 = *(_QWORD *)(v4[1] + 56LL);
  *(_QWORD *)AccessStatus = v5;
  if ( v5 )
    goto LABEL_20;
  RxSubjectContextFromRxContext(RxContext, &SubjectSecurityContext);
  Entry = CscStoreFindOrCreateEntry((unsigned int)AccessStatus, 0, 0, v15, 8, 0, 0, (__int64)SubjectSecurityContext);
  if ( Entry >= 0 )
  {
    v41 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v5 = *(_QWORD *)AccessStatus;
      v22 = Fcb;
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        57,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        *(_QWORD *)AccessStatus,
        Fcb,
        pRelevantSrvOpen);
LABEL_21:
      Entry = CscStoreOpenEntryHandle((unsigned int)v4[2] + 16, v5, 0, 0, 0, 0, 0, 0);
      if ( Entry < 0 )
      {
        v26 = 4017;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_qqq(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
            v5,
            v22,
            pRelevantSrvOpen);
        }
        if ( *(_QWORD *)(v4[1] + 56LL) )
        {
          v23 = Fcb;
          goto LABEL_25;
        }
        GrantedAccess[0] = 1;
        Entry = CscStoreQueryInformationEntryEx(v5, 0, 0, (int)a2 + 56, 0, 0, 0);
        if ( Entry >= 0 )
        {
          *(_QWORD *)(a2 + 456) = a2 + 104;
          v29 = (struct _FCB_INIT_PACKET *)(a2 + 448);
          *(_DWORD *)(a2 + 448) = 0;
          *(_QWORD *)(a2 + 464) = GrantedAccess;
          *(_QWORD *)(a2 + 472) = a2 + 56;
          *(_QWORD *)(a2 + 480) = a2 + 64;
          *(_QWORD *)(a2 + 488) = a2 + 72;
          *(_QWORD *)(a2 + 496) = a2 + 80;
          *(_QWORD *)(a2 + 504) = a2 + 88;
          *(_QWORD *)(a2 + 512) = a2 + 96;
          *(_QWORD *)(a2 + 520) = a2 + 96;
          v23 = Fcb;
          RxFinishFcbInitialization(Fcb, (RX_FILE_TYPE)60449, v29);
LABEL_25:
          NetFobx = RxCreateNetFobx(RxContext, pRelevantSrvOpen);
          RxContext->pFobx = NetFobx;
          if ( NetFobx )
          {
            v25 = CscCreateAndInitializeFobxContext(NetFobx, v4, 0, 0);
            Entry = v25;
            if ( v25 )
            {
              v26 = 4079;
              if ( v25 >= 0 )
                goto LABEL_35;
            }
            else
            {
              v26 = 0;
              if ( (Destination.Length & 0x40) != 0 )
              {
                *(_DWORD *)(*v4 + 32LL) = 3;
              }
              else if ( SLOBYTE(Destination.Length) < 0 )
              {
                *(_DWORD *)(*v4 + 32LL) = 2;
              }
              else if ( (Destination.Length & 0x100) != 0 )
              {
                *(_DWORD *)(*v4 + 32LL) = 1;
              }
              *((_QWORD *)&RxContext->9 + 25) = 1;
              Entry = 0;
              if ( *(_QWORD *)(v4[1] + 56LL) )
                goto LABEL_35;
              Entry = CscSetFcbStoreEntry(v23, v5);
              if ( Entry >= 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_qqq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    59,
                    WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                    v5,
                    v23,
                    pRelevantSrvOpen);
                }
                goto LABEL_35;
              }
            }
          }
          else
          {
            Entry = -1073741670;
            v26 = 4067;
          }
          goto LABEL_58;
        }
        v26 = 4038;
      }
LABEL_58:
      v8 = v41;
      goto LABEL_59;
    }
    v5 = *(_QWORD *)AccessStatus;
LABEL_20:
    v22 = Fcb;
    goto LABEL_21;
  }
  v5 = *(_QWORD *)AccessStatus;
  v26 = 3988;
  v8 = 0;
LABEL_59:
  v31 = v4[2];
  if ( v31 && (v32 = *(_QWORD *)(v31 + 16)) != 0 )
  {
    CscStoreCloseEntryHandle(v32, 0, 0);
    *(_QWORD *)(v4[2] + 16LL) = 0;
    v33 = Fcb;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v5,
        Fcb,
        pRelevantSrvOpen);
    v8 = v41;
  }
  else
  {
    v33 = Fcb;
  }
  if ( v5 && v8 )
  {
    CscStoreDereferenceEntry(AccessStatus);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)Entry;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        61,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v5,
        v33,
        pRelevantSrvOpen);
  }
LABEL_35:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      62,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)Entry,
      v26);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x14007eb20  mov     [rsp-8+arg_10], rbx
0x14007eb25  push    rbp
0x14007eb26  push    rsi
0x14007eb27  push    rdi
0x14007eb28  push    r12
0x14007eb2a  push    r13
0x14007eb2c  push    r14
0x14007eb2e  push    r15
0x14007eb30  lea     rbp, [rsp-27h]
0x14007eb35  sub     rsp, 0A0h
0x14007eb3c  mov     rax, cs:__security_cookie
0x14007eb43  xor     rax, rsp
0x14007eb46  mov     [rbp+57h+var_38], rax
0x14007eb4a  mov     rsi, rcx
0x14007eb4d  mov     [rbp+57h+SubjectSecurityContext], 0
0x14007eb55  mov     rcx, [rcx+38h]
0x14007eb59  lea     rdi, [rdx+158h]
0x14007eb60  xor     r15d, r15d
0x14007eb63  mov     [rbp+57h+Fcb], rcx
0x14007eb67  mov     r13, rdx
0x14007eb6a  mov     qword ptr [rbp+57h+var_70], r15
0x14007eb6e  mov     r14d, [rsi+100h]
0x14007eb75  xor     dl, dl
0x14007eb77  mov     r12, [rsi+48h]
0x14007eb7b  mov     [rbp+57h+var_80], dl
0x14007eb7e  test    r14b, 10h
0x14007eb82  jnz     loc_14007F35B
0x14007eb88  test    dword ptr [rsi+21Ch], 1000h
0x14007eb92  jnz     loc_14007F35B
0x14007eb98  lea     rax, [rcx+168h]
0x14007eb9f  mov     rcx, rax
0x14007eba2  mov     qword ptr [rbp+57h+var_68], rax
0x14007eba6  call    CscCreateSlashDotOpenCheckReparse
0x14007ebab  mov     ebx, eax
0x14007ebad  test    eax, eax
0x14007ebaf  js      loc_14007F1C9
0x14007ebb5  cmp     eax, 104h
0x14007ebba  jz      loc_14007F1D6
0x14007ebc0  or      r14d, 8
0x14007ebc4  mov     ebx, r14d
0x14007ebc7  mov     qword ptr [rbp+57h+Destination.Length], rbx
0x14007ebcb  mov     [rsi+100h], rbx
0x14007ebd2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ebd9  lea     rax, WPP_GLOBAL_Control
0x14007ebe0  mov     r14, qword ptr [rbp+57h+var_68]
0x14007ebe4  cmp     rcx, rax
0x14007ebe7  jnz     loc_14007F09C
0x14007ebed  mov     rdx, rdi
0x14007ebf0  mov     rcx, rsi
0x14007ebf3  call    CscGetContexts
0x14007ebf8  cmp     [rdi+8], r15
0x14007ebfc  jz      loc_14007EEE7
0x14007ec02  cmp     [rdi+10h], r15
0x14007ec06  jz      loc_14007F063
0x14007ec0c  mov     rax, [rdi+10h]
0x14007ec10  or      dword ptr [rax+18h], 1
0x14007ec14  mov     rax, [rdi+10h]
0x14007ec18  mov     [rax+20h], ebx
0x14007ec1b  mov     rax, [rsi+220h]
0x14007ec22  mov     rdx, [rax+8]
0x14007ec26  mov     rcx, [rdx+20h]
0x14007ec2a  test    rcx, rcx
0x14007ec2d  jnz     short loc_14007EC33
0x14007ec2f  mov     rcx, [rdx+30h]; Token
0x14007ec33  call    cs:__imp_SeTokenIsAdmin
0x14007ec3a  nop     dword ptr [rax+rax+00h]
0x14007ec3f  test    al, al
0x14007ec41  jz      short loc_14007EC4E
0x14007ec43  mov     rax, [rdi+10h]
0x14007ec47  or      dword ptr [rax+18h], 4000h
0x14007ec4e  cmp     [r13+215h], r15b
0x14007ec55  jl      loc_14007F2B8
0x14007ec5b  lea     rdx, [rbp+57h+SubjectSecurityContext]
0x14007ec5f  mov     rcx, rsi
0x14007ec62  call    cs:__imp_RxSubjectContextFromRxContext
0x14007ec69  nop     dword ptr [rax+rax+00h]
0x14007ec6e  mov     ebx, eax
0x14007ec70  test    eax, eax
0x14007ec72  js      loc_14007F2E3
0x14007ec78  mov     rax, [rsi+28h]
0x14007ec7c  lea     rcx, [rbp+57h+var_70]
0x14007ec80  mov     [rsp+0D0h+AccessStatus], rcx; AccessStatus
0x14007ec85  xor     edx, edx
0x14007ec87  lea     rcx, [rbp+57h+var_68]
0x14007ec8b  mov     [rbp+57h+var_70], edx
0x14007ec8e  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x14007ec93  mov     r9d, 1; DesiredAccess
0x14007ec99  movzx   eax, byte ptr [rax+40h]
0x14007ec9d  xor     r8d, r8d; SubjectContextLocked
0x14007eca0  mov     rcx, cs:CscDevExtn
0x14007eca7  mov     [rsp+0D0h+AccessMode], al; AccessMode
0x14007ecab  lea     rax, [rbp+57h+var_48]
0x14007ecaf  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x14007ecb4  mov     [rsp+0D0h+Privileges], rdx; Privileges
0x14007ecb9  mov     rcx, [rcx+588h]; SecurityDescriptor
0x14007ecc0  mov     [rsp+0D0h+PreviouslyGrantedAccess], edx; PreviouslyGrantedAccess
0x14007ecc4  mov     [rbp+57h+var_68], edx
0x14007ecc7  mov     rdx, [rbp+57h+SubjectSecurityContext]; SubjectSecurityContext
0x14007eccb  mov     [rbp+57h+var_48.GenericRead], 20001h
0x14007ecd2  mov     [rbp+57h+var_48.GenericWrite], 20000h
0x14007ecd9  mov     [rbp+57h+var_48.GenericExecute], 20000h
0x14007ece0  mov     [rbp+57h+var_48.GenericAll], 1F0001h
0x14007ece7  call    cs:__imp_SeAccessCheck
0x14007ecee  nop     dword ptr [rax+rax+00h]
0x14007ecf3  movzx   ebx, al
0x14007ecf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ecfd  lea     rax, WPP_GLOBAL_Control
0x14007ed04  cmp     rcx, rax
0x14007ed07  jz      short loc_14007ED15
0x14007ed09  mov     edx, [rcx+2Ch]
0x14007ed0c  test    dl, 40h
0x14007ed0f  jnz     loc_14007F2F0
0x14007ed15  test    bl, bl
0x14007ed17  jz      short loc_14007ED24
0x14007ed19  mov     rax, [rdi+10h]
0x14007ed1d  or      dword ptr [rax+18h], 2000h
0x14007ed24  mov     rax, [rdi+8]
0x14007ed28  inc     dword ptr [rax+14h]
0x14007ed2b  or      dword ptr [r12+48h], 1080h
0x14007ed34  mov     rax, [rdi+8]
0x14007ed38  mov     r15, [rax+38h]
0x14007ed3c  mov     qword ptr [rbp+57h+var_70], r15
0x14007ed40  test    r15, r15
0x14007ed43  jz      loc_14007EF31
0x14007ed49  mov     r14, [rbp+57h+Fcb]
0x14007ed4d  mov     rcx, [rdi+10h]
0x14007ed51  xor     eax, eax
0x14007ed53  mov     qword ptr [rsp+0D0h+AccessMode], rax
0x14007ed58  add     rcx, 10h
0x14007ed5c  mov     [rsp+0D0h+GenericMapping], rax
0x14007ed61  xor     r9d, r9d
0x14007ed64  mov     byte ptr [rsp+0D0h+Privileges], al
0x14007ed68  xor     r8d, r8d
0x14007ed6b  mov     rdx, r15
0x14007ed6e  mov     [rsp+0D0h+PreviouslyGrantedAccess], eax
0x14007ed72  call    CscStoreOpenEntryHandle
0x14007ed77  mov     ebx, eax
0x14007ed79  test    eax, eax
0x14007ed7b  js      loc_14007F341
0x14007ed81  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed88  lea     rax, WPP_GLOBAL_Control
0x14007ed8f  cmp     rcx, rax
0x14007ed92  jnz     loc_14007EEB5
0x14007ed98  mov     rax, [rdi+8]
0x14007ed9c  cmp     qword ptr [rax+38h], 0
0x14007eda1  jz      loc_14007EFA7
0x14007eda7  mov     r13, [rbp+57h+Fcb]
0x14007edab  mov     rdx, r12; MrxSrvOpen
0x14007edae  mov     rcx, rsi; RxContext
0x14007edb1  call    cs:__imp_RxCreateNetFobx
0x14007edb8  nop     dword ptr [rax+rax+00h]
0x14007edbd  mov     [rsi+40h], rax
0x14007edc1  test    rax, rax
0x14007edc4  jz      loc_14007F1B9
0x14007edca  xor     r9d, r9d
0x14007edcd  xor     r8d, r8d
0x14007edd0  mov     rdx, rdi
0x14007edd3  mov     rcx, rax
0x14007edd6  call    CscCreateAndInitializeFobxContext
0x14007eddb  mov     ebx, eax
0x14007eddd  test    eax, eax
0x14007eddf  jnz     loc_14007EE68
0x14007ede5  mov     rax, qword ptr [rbp+57h+Destination.Length]
0x14007ede9  xor     r14d, r14d
0x14007edec  test    al, 40h
0x14007edee  jz      loc_14007F0CF
0x14007edf4  mov     rax, [rdi]
0x14007edf7  mov     dword ptr [rax+20h], 3
0x14007edfe  mov     qword ptr [rsi+258h], 1
0x14007ee09  xor     ebx, ebx
0x14007ee0b  mov     rax, [rdi+8]
0x14007ee0f  cmp     [rax+38h], rbx
0x14007ee13  jnz     short loc_14007EE74
0x14007ee15  mov     rdx, r15
0x14007ee18  mov     rcx, r13
0x14007ee1b  call    CscSetFcbStoreEntry
0x14007ee20  mov     ebx, eax
0x14007ee22  test    eax, eax
0x14007ee24  js      loc_14007F131
0x14007ee2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ee31  lea     rsi, WPP_GLOBAL_Control
0x14007ee38  cmp     rcx, rsi
0x14007ee3b  jz      short loc_14007EE7B
0x14007ee3d  mov     eax, [rcx+2Ch]
0x14007ee40  test    al, 40h
0x14007ee42  jz      short loc_14007EE7B
0x14007ee44  mov     rcx, [rcx+18h]
0x14007ee48  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14007ee4f  mov     edx, 3Bh ; ';'
0x14007ee54  mov     [rsp+0D0h+Privileges], r12
0x14007ee59  mov     r9, r15
0x14007ee5c  mov     qword ptr [rsp+0D0h+PreviouslyGrantedAccess], r13
0x14007ee61  call    WPP_SF_qqq
0x14007ee66  jmp     short loc_14007EE7B
0x14007ee68  mov     r14d, 0FEFh
0x14007ee6e  js      loc_14007F131
0x14007ee74  lea     rsi, WPP_GLOBAL_Control
0x14007ee7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ee82  cmp     rcx, rsi
0x14007ee85  jnz     loc_14007F0F0
0x14007ee8b  mov     eax, ebx
0x14007ee8d  mov     rcx, [rbp+57h+var_38]
0x14007ee91  xor     rcx, rsp; StackCookie
0x14007ee94  call    __security_check_cookie
0x14007ee99  mov     rbx, [rsp+0D0h+arg_10]
0x14007eea1  add     rsp, 0A0h
0x14007eea8  pop     r15
0x14007eeaa  pop     r14
0x14007eeac  pop     r13
0x14007eeae  pop     r12
0x14007eeb0  pop     rdi
0x14007eeb1  pop     rsi
0x14007eeb2  pop     rbp
0x14007eeb3  retn
0x14007eeb5  mov     eax, [rcx+2Ch]
0x14007eeb8  test    al, 40h
0x14007eeba  jz      loc_14007ED98
0x14007eec0  mov     rcx, [rcx+18h]
0x14007eec4  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14007eecb  mov     edx, 3Ah ; ':'
0x14007eed0  mov     [rsp+0D0h+Privileges], r12
0x14007eed5  mov     r9, r15
0x14007eed8  mov     qword ptr [rsp+0D0h+PreviouslyGrantedAccess], r14
0x14007eedd  call    WPP_SF_qqq
0x14007eee2  jmp     loc_14007ED98
0x14007eee7  mov     edx, 78h ; 'x'
0x14007eeec  mov     ecx, 100h
0x14007eef1  mov     r8d, 3F3F7852h
0x14007eef7  call    cs:__imp_ExAllocatePool2
0x14007eefe  nop     dword ptr [rax+rax+00h]
0x14007ef03  mov     [rdi+8], rax
0x14007ef07  test    rax, rax
0x14007ef0a  jz      loc_14007F294
0x14007ef10  mov     rcx, [rbp+57h+Fcb]
0x14007ef14  mov     [rcx+90h], rax
0x14007ef1b  mov     dword ptr [rax], 78EAA1h
0x14007ef21  mov     rax, [rdi+8]
0x14007ef25  mov     dword ptr [rax+4], 40h ; '@'
0x14007ef2c  jmp     loc_14007EC02
0x14007ef31  lea     rdx, [rbp+57h+SubjectSecurityContext]
0x14007ef35  mov     rcx, rsi
0x14007ef38  call    cs:__imp_RxSubjectContextFromRxContext
0x14007ef3f  nop     dword ptr [rax+rax+00h]
0x14007ef44  mov     rax, [rbp+57h+SubjectSecurityContext]
0x14007ef48  lea     rcx, [rbp+57h+var_70]
0x14007ef4c  mov     qword ptr [rsp+0D0h+AccessMode], rax
0x14007ef51  mov     r9, r14
0x14007ef54  xor     eax, eax
0x14007ef56  xor     r8d, r8d
0x14007ef59  mov     [rsp+0D0h+GenericMapping], rax
0x14007ef5e  xor     edx, edx
0x14007ef60  mov     [rsp+0D0h+Privileges], rax
0x14007ef65  mov     [rsp+0D0h+PreviouslyGrantedAccess], 8
0x14007ef6d  call    CscStoreFindOrCreateEntry
0x14007ef72  mov     ebx, eax
0x14007ef74  test    eax, eax
0x14007ef76  js      loc_14007F11D
0x14007ef7c  mov     [rbp+57h+var_80], 1
0x14007ef80  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ef87  lea     rax, WPP_GLOBAL_Control
0x14007ef8e  cmp     rcx, rax
0x14007ef91  jz      short loc_14007EF9E
0x14007ef93  mov     eax, [rcx+2Ch]
0x14007ef96  test    al, 40h
0x14007ef98  jnz     loc_14007F312
0x14007ef9e  mov     r15, qword ptr [rbp+57h+var_70]
0x14007efa2  jmp     loc_14007ED49
0x14007efa7  xor     eax, eax
0x14007efa9  mov     [rbp+57h+var_68], 1
0x14007efb0  mov     [rsp+0D0h+GenericMapping], rax
0x14007efb5  lea     r14, [r13+38h]
0x14007efb9  mov     [rsp+0D0h+Privileges], rax
0x14007efbe  mov     r9, r14
0x14007efc1  xor     r8d, r8d
0x14007efc4  mov     qword ptr [rsp+0D0h+PreviouslyGrantedAccess], rax
0x14007efc9  xor     edx, edx
0x14007efcb  mov     rcx, r15
0x14007efce  call    CscStoreQueryInformationEntryEx
0x14007efd3  mov     ebx, eax
0x14007efd5  test    eax, eax
0x14007efd7  js      loc_14007F12B
0x14007efdd  lea     rax, [r13+68h]
0x14007efe1  mov     edx, 0EC21h; FileType
0x14007efe6  mov     [r13+1C8h], rax
0x14007efed  lea     r8, [r13+1C0h]; InitPacket
0x14007eff4  mov     dword ptr [r8], 0
0x14007effb  lea     rax, [rbp+57h+var_68]
0x14007efff  mov     [r13+1D0h], rax
0x14007f006  lea     rax, [r13+40h]
0x14007f00a  mov     [r13+1D8h], r14
0x14007f011  mov     [r13+1E0h], rax
0x14007f018  lea     rax, [r13+48h]
0x14007f01c  mov     [r13+1E8h], rax
0x14007f023  lea     rax, [r13+50h]
0x14007f027  mov     [r13+1F0h], rax
0x14007f02e  lea     rax, [r13+58h]
0x14007f032  mov     [r13+1F8h], rax
0x14007f039  lea     rax, [r13+60h]
0x14007f03d  mov     [r13+200h], rax
0x14007f044  mov     [r13+208h], rax
  ... truncated ...
```
