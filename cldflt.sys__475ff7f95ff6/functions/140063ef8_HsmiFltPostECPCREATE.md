# HsmiFltPostECPCREATE

- ea: `0x140063ef8`
- end: `0x140064634`
- name: `HsmiFltPostECPCREATE`
- size: `1852`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64, _QWORD *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140063d90`
- `0x140063ee0`

## callees

- `0x140001590`
- `0x140003c50`
- `0x140007360`
- `0x14000abb8`
- `0x14000ac28`
- `0x14001d334`
- `0x14001d3c0`
- `0x14005ac10`
- `0x140063ef8`
- `0x14006463c`
- `0x14006486c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006424e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006424e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140064242`
- `ntoskrnl!ExReleaseResourceLite` at `0x140064242`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006420d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006420d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400641f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400641f7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140064078`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140064078`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140064225`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400642f7`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140064225`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400642f7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140064318`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400643e7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140064318`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400643e7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14006403c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14006403c`
- `FLTMGR!FltCancelFileOpen` at `0x14006461c`
- `FLTMGR!FltCancelFileOpen` at `0x14006461c`
- `FLTMGR!FltReissueSynchronousIo` at `0x14006436e`
- `FLTMGR!FltReissueSynchronousIo` at `0x14006436e`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140064026`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140064026`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140064356`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140064356`
- `FLTMGR!FltGetInstanceContext` at `0x140063f4c`
- `FLTMGR!FltGetInstanceContext` at `0x140063f4c`
- `FLTMGR!FltObjectDereference` at `0x14006415b`
- `FLTMGR!FltObjectDereference` at `0x14006415b`
- `FLTMGR!FltReleaseContext` at `0x140064088`
- `FLTMGR!FltReleaseContext` at `0x140064088`

## pseudocode

```c
__int64 __fastcall HsmiFltPostECPCREATE(struct _FLT_CALLBACK_DATA *a1, __int64 a2, _QWORD *a3, int a4)
{
  struct _FLT_INSTANCE *v4; // r15
  _QWORD *v5; // rdi
  struct _FILE_OBJECT *v6; // r12
  unsigned int v7; // esi
  char v8; // bl
  _QWORD *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int Status; // ebx
  char v13; // r13
  __int64 i; // rcx
  unsigned int v15; // eax
  struct _FLT_CALLBACK_DATA *v16; // rdx
  __int64 v17; // rcx
  int IsUnsupportedLogfilePlaceholder; // eax
  int v20; // edx
  char v21; // si
  _QWORD *v22; // rax
  char *v23; // rax
  __int64 j; // rax
  __int64 v25; // rcx
  _DWORD *v26; // rax
  __int64 k; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  const char *v33; // r9
  int v34; // [rsp+28h] [rbp-30h]
  char v35[3]; // [rsp+41h] [rbp-17h] BYREF
  unsigned int v36; // [rsp+44h] [rbp-14h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-10h] BYREF
  struct _FLT_CALLBACK_DATA *Buffer; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v39; // [rsp+A8h] [rbp+50h]
  char v40; // [rsp+B0h] [rbp+58h] BYREF
  int v41; // [rsp+B8h] [rbp+60h] BYREF

  v41 = a4;
  v39 = a2;
  Buffer = a1;
  v4 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v5 = a3;
  v6 = *(struct _FILE_OBJECT **)(a2 + 32);
  v7 = 0;
  v8 = 0;
  Context = 0;
  v9 = a3;
  v36 = 0;
  v40 = 0;
  LOBYTE(a3) = 1;
  HsmpTracePostCallbackEnter(a1, v9, a3, 0);
  FltGetInstanceContext(v4, &Context);
  if ( !Context )
    goto LABEL_15;
  if ( *(_DWORD *)Context == 843674440 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)Context + 8), 1u);
    v23 = (char *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 112), &Buffer);
    if ( v23 )
    {
      v26 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 216), v23 + 8);
      if ( v26 )
      {
        if ( v26[2]-- == 1 )
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 216), v26);
      }
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 112), &Buffer);
    }
    ExReleaseResourceLite((PERESOURCE)((char *)Context + 8));
    KeLeaveCriticalRegion();
    goto LABEL_15;
  }
  Status = Buffer->IoStatus.Status;
  HsmDbgBreakOnStatus(Status);
  if ( Status >= 0 )
  {
    v13 = 0;
    while ( 1 )
    {
      for ( i = 0; (unsigned int)i < 0x10; i = (unsigned int)(i + 1) )
      {
        if ( (v5[6 * i + 2] & 0x100000000LL) != 0 )
        {
          v15 = ((_DWORD)i << 12) | 0x9000001A;
          v36 = v15;
          goto LABEL_10;
        }
      }
      v15 = v36;
LABEL_10:
      if ( Buffer->IoStatus.Status != 260 )
        break;
      LOBYTE(v41) = 0;
      v35[0] = 0;
      if ( (Buffer->IoStatus.Information & 0xFFFF0FFF) != dword_140029670 )
        goto LABEL_12;
      if ( ++v7 > 0x100 )
      {
        Status = -1073741184;
        HsmDbgBreakOnStatus(-1073741184);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          LOBYTE(v34) = v41;
          WPP_SF_qqcqd(WPP_GLOBAL_Control->AttachedDevice, 29, v10, v4, v6, v34, Buffer, -1073741184);
        }
        goto LABEL_38;
      }
      Status = HsmiCreateEnsureDirectoryFullyPopulated(
                 (__int64)Context,
                 Buffer,
                 v7 == 1,
                 Buffer->TagData->UnparsedNameLength,
                 &v41,
                 v35);
      HsmDbgBreakOnStatus(Status);
      if ( Status < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v31 = 30;
LABEL_72:
          WPP_SF_qqqd(v30->AttachedDevice, v31, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids, v4, v6, Buffer, Status);
        }
LABEL_38:
        v7 = v36;
        goto LABEL_28;
      }
      if ( v35[0] )
      {
        for ( j = 0; j != 16; ++j )
        {
          v25 = 3 * j;
          HIDWORD(v5[2 * v25 + 2]) &= ~2u;
        }
      }
      else
      {
        for ( k = 0; k != 16; ++k )
        {
          v28 = 6 * k;
          if ( (_BYTE)v41 )
            HIDWORD(v5[v28 + 2]) = 0x80000000;
          else
            HIDWORD(v5[v28 + 2]) &= ~1u;
          WORD1(v5[v28 + 5]) = 0;
        }
        FltSetCallbackDataDirty(Buffer);
        FltReissueSynchronousIo(*(PFLT_INSTANCE *)(v39 + 24), Buffer);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          LOBYTE(v34) = v41;
          WPP_SF_qqcqd(WPP_GLOBAL_Control->AttachedDevice, 31, v29, v4, v6, v34, Buffer, Status);
        }
        Status = Buffer->IoStatus.Status;
        HsmDbgBreakOnStatus(Status);
        if ( Status < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v31 = 32;
            goto LABEL_72;
          }
          goto LABEL_38;
        }
      }
    }
    if ( !v6->FsContext )
      goto LABEL_12;
    v13 = 1;
    if ( !v15 )
      goto LABEL_12;
    IsUnsupportedLogfilePlaceholder = HsmiIsUnsupportedLogfilePlaceholder(Context, Buffer, v15, &v40);
    v21 = v40;
    Status = IsUnsupportedLogfilePlaceholder;
    if ( IsUnsupportedLogfilePlaceholder < 0 )
    {
      if ( !v40 )
      {
LABEL_87:
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_93:
          v7 = v36;
LABEL_94:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqiqd(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
              v4,
              v4,
              v6,
              Buffer,
              Status);
          }
          FltCancelFileOpen(v4, v6);
          goto LABEL_28;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v33 = "Encountered an unsupported CLFS Logfile placeholder: ";
          if ( !v21 )
            v33 = "Failed to check if placeholder is a CLFS Logfile: ";
          WPP_SF_sqqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            v20,
            v10,
            (_DWORD)v33,
            (char)v4,
            (char)v6,
            (char)Buffer,
            Status);
        }
LABEL_12:
        if ( Status >= 0 )
        {
          v7 = v36;
          goto LABEL_14;
        }
        if ( !v13 )
          goto LABEL_38;
        goto LABEL_93;
      }
    }
    else if ( !v40 )
    {
      LOBYTE(v11) = 1;
      HsmpTracePostCallbackEnter(Buffer, v5, 0, v11);
      v7 = v36;
      Status = HsmpSetupContexts(Context, Buffer->Iopb->TargetFileObject, v36, Buffer);
      HsmDbgBreakOnStatus(Status);
      if ( Status >= 0 )
      {
        v8 = 1;
        goto LABEL_15;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
          v4,
          v4,
          v6,
          Buffer,
          Status);
      }
      goto LABEL_94;
    }
    Status = -1073688822;
    HsmDbgBreakOnStatus(-1073688822);
    goto LABEL_87;
  }
  if ( Status != -1073741772
    && Status != -1073741766
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
      v4,
      v6,
      Buffer,
      Status);
  }
LABEL_28:
  Buffer->IoStatus.Status = Status;
  Buffer->IoStatus.Information = 0;
LABEL_14:
  v8 = 1;
LABEL_15:
  if ( v5 )
  {
    if ( (_QWORD *)*v5 != v5 )
    {
      v16 = Buffer;
      *(_QWORD *)(v5[90] + 8LL) = v5;
      v17 = v5[90];
      *v5 = v17;
      if ( v16->Iopb->MajorFunction )
      {
        if ( *(_QWORD **)(v17 + 8) != v5 || (v22 = (_QWORD *)v5[1], (_QWORD *)*v22 != v5) )
          __fastfail(3u);
        *v22 = v17;
        *(_QWORD *)(v17 + 8) = v22;
        FltObjectDereference(Filter);
      }
      else
      {
        FltRemoveOpenReparseEntry(Filter, v16, v5);
      }
    }
    ExFreeToPagedLookasideList(&stru_1400292C0, v5);
  }
  if ( Context )
  {
    if ( v8 )
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)Context + 22);
    FltReleaseContext(Context);
  }
  if ( v7 )
  {
    LOBYTE(v11) = 1;
    HsmpTracePostCallbackExit(0, Buffer, v10, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x140063ef8  mov     [rsp-40h+arg_18], r9d
0x140063efd  mov     [rsp-40h+arg_8], rdx
0x140063f02  mov     [rsp-40h+Buffer], rcx
0x140063f07  push    rbp
0x140063f08  push    rbx
0x140063f09  push    rsi
0x140063f0a  push    rdi
0x140063f0b  push    r12
0x140063f0d  push    r13
0x140063f0f  push    r14
0x140063f11  push    r15
0x140063f13  mov     rbp, rsp
0x140063f16  sub     rsp, 58h
0x140063f1a  mov     r15, [rdx+18h]
0x140063f1e  mov     rdi, r8
0x140063f21  mov     r12, [rdx+20h]
0x140063f25  xor     esi, esi
0x140063f27  xor     bl, bl
0x140063f29  mov     [rbp+Context], 0
0x140063f31  mov     rdx, rdi
0x140063f34  mov     [rbp+var_14], esi
0x140063f37  xor     r9d, r9d
0x140063f3a  mov     [rbp+arg_10], bl
0x140063f3d  mov     r8b, 1
0x140063f40  call    HsmpTracePostCallbackEnter
0x140063f45  lea     rdx, [rbp+Context]; Context
0x140063f49  mov     rcx, r15; Instance
0x140063f4c  call    cs:__imp_FltGetInstanceContext
0x140063f53  nop     dword ptr [rax+rax+00h]
0x140063f58  mov     rcx, [rbp+Context]
0x140063f5c  test    rcx, rcx
0x140063f5f  jz      loc_140063FEB
0x140063f65  cmp     dword ptr [rcx], 32497348h
0x140063f6b  jz      loc_1400641F7
0x140063f71  mov     rax, [rbp+Buffer]
0x140063f75  mov     [rbp+var_18], 1
0x140063f79  mov     ebx, [rax+18h]
0x140063f7c  mov     ecx, ebx
0x140063f7e  call    HsmDbgBreakOnStatus
0x140063f83  test    ebx, ebx
0x140063f85  js      loc_140064096
0x140063f8b  xor     r13b, r13b
0x140063f8e  lea     r14, WPP_GLOBAL_Control
0x140063f95  xor     ecx, ecx
0x140063f97  cmp     ecx, 10h
0x140063f9a  jnb     loc_1400643F8
0x140063fa0  lea     rax, [rcx+rcx*2]
0x140063fa4  add     rax, rax
0x140063fa7  mov     eax, [rdi+rax*8+14h]
0x140063fab  test    al, 1
0x140063fad  jnz     short loc_140063FB3
0x140063faf  inc     ecx
0x140063fb1  jmp     short loc_140063F97
0x140063fb3  mov     eax, ecx
0x140063fb5  shl     eax, 0Ch
0x140063fb8  or      eax, 9000001Ah
0x140063fbd  mov     [rbp+var_14], eax
0x140063fc0  mov     rdx, [rbp+Buffer]
0x140063fc4  cmp     dword ptr [rdx+18h], 104h
0x140063fcb  jz      loc_14006425F
0x140063fd1  cmp     qword ptr [r12+18h], 0
0x140063fd7  jnz     loc_1400640BA
0x140063fdd  test    ebx, ebx
0x140063fdf  js      loc_14006416C
0x140063fe5  mov     esi, [rbp+var_14]
0x140063fe8  mov     bl, [rbp+var_18]
0x140063feb  test    rdi, rdi
0x140063fee  jz      short loc_140064048
0x140063ff0  cmp     [rdi], rdi
0x140063ff3  jz      short loc_140064032
0x140063ff5  mov     rax, [rdi+2D0h]
0x140063ffc  mov     rdx, [rbp+Buffer]
0x140064000  mov     [rax+8], rdi
0x140064004  mov     rcx, [rdi+2D0h]
0x14006400b  mov     [rdi], rcx
0x14006400e  mov     rax, [rdx+10h]
0x140064012  cmp     byte ptr [rax+4], 0
0x140064016  jnz     loc_140064136
0x14006401c  mov     rcx, cs:Filter
0x140064023  mov     r8, rdi
0x140064026  call    cs:__imp_FltRemoveOpenReparseEntry
0x14006402d  nop     dword ptr [rax+rax+00h]
0x140064032  mov     rdx, rdi; Entry
0x140064035  lea     rcx, stru_1400292C0; Lookaside
0x14006403c  call    cs:__imp_ExFreeToPagedLookasideList
0x140064043  nop     dword ptr [rax+rax+00h]
0x140064048  mov     rcx, [rbp+Context]
0x14006404c  test    rcx, rcx
0x14006404f  jnz     short loc_14006406D
0x140064051  test    esi, esi
0x140064053  jnz     loc_1400641E4
0x140064059  xor     eax, eax
0x14006405b  add     rsp, 58h
0x14006405f  pop     r15
0x140064061  pop     r14
0x140064063  pop     r13
0x140064065  pop     r12
0x140064067  pop     rdi
0x140064068  pop     rsi
0x140064069  pop     rbx
0x14006406a  pop     rbp
0x14006406b  retn
0x14006406d  test    bl, bl
0x14006406f  jz      short loc_140064084
0x140064071  add     rcx, 0B0h; RunRef
0x140064078  call    cs:__imp_ExReleaseRundownProtection
0x14006407f  nop     dword ptr [rax+rax+00h]
0x140064084  mov     rcx, [rbp+Context]; Context
0x140064088  call    cs:__imp_FltReleaseContext
0x14006408f  nop     dword ptr [rax+rax+00h]
0x140064094  jmp     short loc_140064051
0x140064096  cmp     ebx, 0C0000034h
0x14006409c  jnz     loc_14006417D
0x1400640a2  mov     rax, [rbp+Buffer]
0x1400640a6  mov     [rax+18h], ebx
0x1400640a9  mov     rax, [rbp+Buffer]
0x1400640ad  mov     qword ptr [rax+20h], 0
0x1400640b5  jmp     loc_140063FE8
0x1400640ba  mov     r13b, 1
0x1400640bd  test    eax, eax
0x1400640bf  jz      loc_140063FDD
0x1400640c5  mov     rdx, [rbp+Buffer]
0x1400640c9  lea     r9, [rbp+arg_10]
0x1400640cd  mov     rcx, [rbp+Context]
0x1400640d1  mov     r8d, eax
0x1400640d4  call    HsmiIsUnsupportedLogfilePlaceholder
0x1400640d9  mov     sil, [rbp+arg_10]
0x1400640dd  mov     ebx, eax
0x1400640df  test    eax, eax
0x1400640e1  js      loc_14006455E
0x1400640e7  test    sil, sil
0x1400640ea  jnz     loc_140064563
0x1400640f0  mov     rcx, [rbp+Buffer]
0x1400640f4  mov     r9b, r13b
0x1400640f7  xor     r8d, r8d
0x1400640fa  mov     rdx, rdi
0x1400640fd  call    HsmpTracePostCallbackEnter
0x140064102  mov     r9, [rbp+Buffer]
0x140064106  mov     esi, [rbp+var_14]
0x140064109  mov     r8d, esi
0x14006410c  mov     rcx, [rbp+Context]
0x140064110  mov     rdx, [r9+10h]
0x140064114  mov     rdx, [rdx+8]
0x140064118  call    HsmpSetupContexts
0x14006411d  mov     ecx, eax
0x14006411f  mov     ebx, eax
0x140064121  call    HsmDbgBreakOnStatus
0x140064126  test    ebx, ebx
0x140064128  js      loc_140064507
0x14006412e  mov     bl, r13b
0x140064131  jmp     loc_140063FEB
0x140064136  cmp     [rcx+8], rdi
0x14006413a  jnz     loc_14006462D
0x140064140  mov     rax, [rdi+8]
0x140064144  cmp     [rax], rdi
0x140064147  jnz     loc_14006462D
0x14006414d  mov     [rax], rcx
0x140064150  mov     [rcx+8], rax
0x140064154  mov     rcx, cs:Filter; FltObject
0x14006415b  call    cs:__imp_FltObjectDereference
0x140064162  nop     dword ptr [rax+rax+00h]
0x140064167  jmp     loc_140064032
0x14006416c  test    r13b, r13b
0x14006416f  jnz     loc_1400645CB
0x140064175  mov     esi, [rbp+var_14]
0x140064178  jmp     loc_1400640A2
0x14006417d  cmp     ebx, 0C000003Ah
0x140064183  jz      loc_1400640A2
0x140064189  mov     rcx, cs:WPP_GLOBAL_Control
0x140064190  lea     r14, WPP_GLOBAL_Control
0x140064197  cmp     rcx, r14
0x14006419a  jz      loc_1400640A2
0x1400641a0  mov     eax, [rcx+2Ch]
0x1400641a3  test    al, 1
0x1400641a5  jz      loc_1400640A2
0x1400641ab  cmp     byte ptr [rcx+29h], 5
0x1400641af  jb      loc_1400640A2
0x1400641b5  mov     rax, [rbp+Buffer]
0x1400641b9  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x1400641c0  mov     rcx, [rcx+18h]
0x1400641c4  mov     edx, 1Ch
0x1400641c9  mov     dword ptr [rsp+58h+var_28], ebx
0x1400641cd  mov     r9, r15
0x1400641d0  mov     [rsp+58h+var_30], rax
0x1400641d5  mov     [rsp+58h+var_38], r12
0x1400641da  call    WPP_SF_qqqd
0x1400641df  jmp     loc_1400640A2
0x1400641e4  mov     rdx, [rbp+Buffer]
0x1400641e8  mov     r9b, 1
0x1400641eb  xor     ecx, ecx
0x1400641ed  call    HsmpTracePostCallbackExit
0x1400641f2  jmp     loc_140064059
0x1400641f7  call    cs:__imp_KeEnterCriticalRegion
0x1400641fe  nop     dword ptr [rax+rax+00h]
0x140064203  mov     rcx, [rbp+Context]
0x140064207  mov     dl, 1; Wait
0x140064209  add     rcx, 8; Resource
0x14006420d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140064214  nop     dword ptr [rax+rax+00h]
0x140064219  mov     rcx, [rbp+Context]
0x14006421d  lea     rdx, [rbp+Buffer]; Buffer
0x140064221  add     rcx, 70h ; 'p'; Table
0x140064225  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14006422c  nop     dword ptr [rax+rax+00h]
0x140064231  test    rax, rax
0x140064234  jnz     loc_1400642E8
0x14006423a  mov     rcx, [rbp+Context]
0x14006423e  add     rcx, 8; Resource
0x140064242  call    cs:__imp_ExReleaseResourceLite
0x140064249  nop     dword ptr [rax+rax+00h]
0x14006424e  call    cs:__imp_KeLeaveCriticalRegion
0x140064255  nop     dword ptr [rax+rax+00h]
0x14006425a  jmp     loc_140063FEB
0x14006425f  mov     byte ptr [rbp+arg_18], r13b
0x140064263  mov     [rbp+var_17], r13b
0x140064267  mov     eax, [rdx+20h]
0x14006426a  and     eax, 0FFFF0FFFh
0x14006426f  cmp     eax, cs:dword_140029670
0x140064275  jnz     loc_140063FDD
0x14006427b  inc     esi
0x14006427d  cmp     esi, 100h
0x140064283  ja      loc_1400644A7
0x140064289  mov     r9, [rdx+28h]
0x14006428d  lea     rax, [rbp+var_17]
0x140064291  mov     rcx, [rbp+Context]
0x140064295  cmp     esi, 1
0x140064298  mov     [rsp+58h+var_30], rax
0x14006429d  lea     rax, [rbp+arg_18]
0x1400642a1  setz    r8b
0x1400642a5  mov     [rsp+58h+var_38], rax
0x1400642aa  movzx   r9d, word ptr [r9+6]
0x1400642af  call    HsmiCreateEnsureDirectoryFullyPopulated
0x1400642b4  mov     ecx, eax
0x1400642b6  mov     ebx, eax
0x1400642b8  call    HsmDbgBreakOnStatus
0x1400642bd  test    ebx, ebx
0x1400642bf  js      loc_140064480
0x1400642c5  cmp     [rbp+var_17], r13b
0x1400642c9  jz      short loc_140064329
0x1400642cb  xor     eax, eax
0x1400642cd  lea     rcx, [rax+rax*2]
0x1400642d1  inc     rax
0x1400642d4  shl     rcx, 4
0x1400642d8  and     dword ptr [rcx+rdi+14h], 0FFFFFFFDh
0x1400642dd  cmp     rax, 10h
0x1400642e1  jnz     short loc_1400642CD
0x1400642e3  jmp     loc_140063F95
0x1400642e8  mov     rcx, [rbp+Context]
0x1400642ec  lea     rdx, [rax+8]; Buffer
0x1400642f0  add     rcx, 0D8h; Table
0x1400642f7  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400642fe  nop     dword ptr [rax+rax+00h]
0x140064303  test    rax, rax
0x140064306  jnz     loc_1400643CF
0x14006430c  mov     rcx, [rbp+Context]
0x140064310  lea     rdx, [rbp+Buffer]; Buffer
0x140064314  add     rcx, 70h ; 'p'; Table
0x140064318  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14006431f  nop     dword ptr [rax+rax+00h]
0x140064324  jmp     loc_14006423A
0x140064329  xor     edx, edx
0x14006432b  lea     rcx, [rdx+rdx*2]
0x14006432f  shl     rcx, 4
0x140064333  cmp     byte ptr [rbp+arg_18], r13b
0x140064337  jnz     loc_140064400
0x14006433d  and     dword ptr [rdi+rcx+14h], 0FFFFFFFEh
0x140064342  xor     eax, eax
0x140064344  inc     rdx
0x140064347  mov     [rdi+rcx+2Ah], ax
0x14006434c  cmp     rdx, 10h
0x140064350  jnz     short loc_14006432B
0x140064352  mov     rcx, [rbp+Buffer]; Data
0x140064356  call    cs:__imp_FltSetCallbackDataDirty
0x14006435d  nop     dword ptr [rax+rax+00h]
0x140064362  mov     rax, [rbp+arg_8]
0x140064366  mov     rdx, [rbp+Buffer]; CallbackData
0x14006436a  mov     rcx, [rax+18h]; InitiatingInstance
0x14006436e  call    cs:__imp_FltReissueSynchronousIo
0x140064375  nop     dword ptr [rax+rax+00h]
0x14006437a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064381  cmp     rcx, r14
0x140064384  jnz     loc_14006440D
0x14006438a  mov     rax, [rbp+Buffer]
0x14006438e  mov     ebx, [rax+18h]
0x140064391  mov     ecx, ebx
0x140064393  call    HsmDbgBreakOnStatus
0x140064398  test    ebx, ebx
0x14006439a  jns     loc_140063F95
0x1400643a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400643a7  cmp     rcx, r14
0x1400643aa  jz      loc_140064175
0x1400643b0  mov     eax, [rcx+2Ch]
0x1400643b3  test    al, 1
0x1400643b5  jz      loc_140064175
0x1400643bb  cmp     byte ptr [rcx+29h], 2
0x1400643bf  jb      loc_140064175
0x1400643c5  mov     edx, 20h ; ' '
0x1400643ca  jmp     loc_140064456
0x1400643cf  add     dword ptr [rax+8], 0FFFFFFFFh
0x1400643d3  jnz     loc_14006430C
  ... truncated ...
```
