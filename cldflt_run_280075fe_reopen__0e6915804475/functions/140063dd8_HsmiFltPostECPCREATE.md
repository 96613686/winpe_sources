# HsmiFltPostECPCREATE

- ea: `0x140063dd8`
- end: `0x140064514`
- name: `HsmiFltPostECPCREATE`
- size: `1852`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140063c70`
- `0x140063dc0`

## callees

- `0x140001590`
- `0x140003c50`
- `0x140007360`
- `0x14000abb8`
- `0x14000ac28`
- `0x14001d2b4`
- `0x14001d340`
- `0x14005aaf0`
- `0x140063dd8`
- `0x14006451c`
- `0x14006474c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006412e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006412e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140064122`
- `ntoskrnl!ExReleaseResourceLite` at `0x140064122`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400640ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400640ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400640d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400640d7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140063f58`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140063f58`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140064105`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400641d7`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140064105`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400641d7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400641f8`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400642c7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400641f8`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400642c7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063f1c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063f1c`
- `FLTMGR!FltCancelFileOpen` at `0x1400644fc`
- `FLTMGR!FltCancelFileOpen` at `0x1400644fc`
- `FLTMGR!FltReissueSynchronousIo` at `0x14006424e`
- `FLTMGR!FltReissueSynchronousIo` at `0x14006424e`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140063f06`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140063f06`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140064236`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140064236`
- `FLTMGR!FltGetInstanceContext` at `0x140063e2c`
- `FLTMGR!FltGetInstanceContext` at `0x140063e2c`
- `FLTMGR!FltObjectDereference` at `0x14006403b`
- `FLTMGR!FltObjectDereference` at `0x14006403b`
- `FLTMGR!FltReleaseContext` at `0x140063f68`
- `FLTMGR!FltReleaseContext` at `0x140063f68`

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
  __int64 v12; // rbx
  char v13; // r13
  __int64 i; // rcx
  unsigned int v15; // eax
  PFLT_CALLBACK_DATA v16; // rdx
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
  __int64 v34; // [rsp+28h] [rbp-30h]
  char v35[3]; // [rsp+41h] [rbp-17h] BYREF
  unsigned int v36; // [rsp+44h] [rbp-14h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-10h] BYREF
  PFLT_CALLBACK_DATA Buffer; // [rsp+A0h] [rbp+48h] BYREF
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
  LODWORD(v12) = Buffer->IoStatus.Status;
  HsmDbgBreakOnStatus((unsigned int)v12);
  if ( (int)v12 >= 0 )
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
        LODWORD(v12) = -1073741184;
        HsmDbgBreakOnStatus(3221226112LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          LOBYTE(v34) = v41;
          WPP_SF_qqcqd(WPP_GLOBAL_Control->AttachedDevice, 29, v10, v4, v6, v34, Buffer, -1073741184);
        }
        goto LABEL_38;
      }
      LOBYTE(v10) = v7 == 1;
      v12 = (unsigned int)HsmiCreateEnsureDirectoryFullyPopulated(
                            Context,
                            Buffer,
                            v10,
                            Buffer->TagData->UnparsedNameLength,
                            &v41,
                            v35);
      HsmDbgBreakOnStatus(v12);
      if ( (int)v12 < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v31 = 30;
LABEL_72:
          WPP_SF_qqqd(v30->AttachedDevice, v31, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids, v4, v6, Buffer, v12);
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
          WPP_SF_qqcqd(WPP_GLOBAL_Control->AttachedDevice, 31, v29, v4, v6, v34, Buffer, v12);
        }
        LODWORD(v12) = Buffer->IoStatus.Status;
        HsmDbgBreakOnStatus((unsigned int)v12);
        if ( (int)v12 < 0 )
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
    LODWORD(v12) = IsUnsupportedLogfilePlaceholder;
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
              v12);
          }
          FltCancelFileOpen(v4, v6);
          goto LABEL_28;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v33 = "Encountered an unsupported CLFS Logfile placeholder: ";
          if ( !v21 )
            v33 = "Failed to check if placeholder is a CLFS Logfile: ";
          WPP_SF_sqqqd(WPP_GLOBAL_Control->AttachedDevice, v20, v10, (_DWORD)v33, (char)v4, (char)v6, (char)Buffer, v12);
        }
LABEL_12:
        if ( (int)v12 >= 0 )
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
      v12 = (unsigned int)HsmpSetupContexts(Context, Buffer->Iopb->TargetFileObject, v36);
      HsmDbgBreakOnStatus(v12);
      if ( (int)v12 >= 0 )
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
          v12);
      }
      goto LABEL_94;
    }
    LODWORD(v12) = -1073688822;
    HsmDbgBreakOnStatus(3221278474LL);
    goto LABEL_87;
  }
  if ( (_DWORD)v12 != -1073741772
    && (_DWORD)v12 != -1073741766
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
      v12);
  }
LABEL_28:
  Buffer->IoStatus.Status = v12;
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
0x140063dd8  mov     [rsp-40h+arg_18], r9d
0x140063ddd  mov     [rsp-40h+arg_8], rdx
0x140063de2  mov     [rsp-40h+Buffer], rcx
0x140063de7  push    rbp
0x140063de8  push    rbx
0x140063de9  push    rsi
0x140063dea  push    rdi
0x140063deb  push    r12
0x140063ded  push    r13
0x140063def  push    r14
0x140063df1  push    r15
0x140063df3  mov     rbp, rsp
0x140063df6  sub     rsp, 58h
0x140063dfa  mov     r15, [rdx+18h]
0x140063dfe  mov     rdi, r8
0x140063e01  mov     r12, [rdx+20h]
0x140063e05  xor     esi, esi
0x140063e07  xor     bl, bl
0x140063e09  mov     [rbp+Context], 0
0x140063e11  mov     rdx, rdi
0x140063e14  mov     [rbp+var_14], esi
0x140063e17  xor     r9d, r9d
0x140063e1a  mov     [rbp+arg_10], bl
0x140063e1d  mov     r8b, 1
0x140063e20  call    HsmpTracePostCallbackEnter
0x140063e25  lea     rdx, [rbp+Context]; Context
0x140063e29  mov     rcx, r15; Instance
0x140063e2c  call    cs:__imp_FltGetInstanceContext
0x140063e33  nop     dword ptr [rax+rax+00h]
0x140063e38  mov     rcx, [rbp+Context]
0x140063e3c  test    rcx, rcx
0x140063e3f  jz      loc_140063ECB
0x140063e45  cmp     dword ptr [rcx], 32497348h
0x140063e4b  jz      loc_1400640D7
0x140063e51  mov     rax, [rbp+Buffer]
0x140063e55  mov     [rbp+var_18], 1
0x140063e59  mov     ebx, [rax+18h]
0x140063e5c  mov     ecx, ebx
0x140063e5e  call    HsmDbgBreakOnStatus
0x140063e63  test    ebx, ebx
0x140063e65  js      loc_140063F76
0x140063e6b  xor     r13b, r13b
0x140063e6e  lea     r14, WPP_GLOBAL_Control
0x140063e75  xor     ecx, ecx
0x140063e77  cmp     ecx, 10h
0x140063e7a  jnb     loc_1400642D8
0x140063e80  lea     rax, [rcx+rcx*2]
0x140063e84  add     rax, rax
0x140063e87  mov     eax, [rdi+rax*8+14h]
0x140063e8b  test    al, 1
0x140063e8d  jnz     short loc_140063E93
0x140063e8f  inc     ecx
0x140063e91  jmp     short loc_140063E77
0x140063e93  mov     eax, ecx
0x140063e95  shl     eax, 0Ch
0x140063e98  or      eax, 9000001Ah
0x140063e9d  mov     [rbp+var_14], eax
0x140063ea0  mov     rdx, [rbp+Buffer]
0x140063ea4  cmp     dword ptr [rdx+18h], 104h
0x140063eab  jz      loc_14006413F
0x140063eb1  cmp     qword ptr [r12+18h], 0
0x140063eb7  jnz     loc_140063F9A
0x140063ebd  test    ebx, ebx
0x140063ebf  js      loc_14006404C
0x140063ec5  mov     esi, [rbp+var_14]
0x140063ec8  mov     bl, [rbp+var_18]
0x140063ecb  test    rdi, rdi
0x140063ece  jz      short loc_140063F28
0x140063ed0  cmp     [rdi], rdi
0x140063ed3  jz      short loc_140063F12
0x140063ed5  mov     rax, [rdi+2D0h]
0x140063edc  mov     rdx, [rbp+Buffer]
0x140063ee0  mov     [rax+8], rdi
0x140063ee4  mov     rcx, [rdi+2D0h]
0x140063eeb  mov     [rdi], rcx
0x140063eee  mov     rax, [rdx+10h]
0x140063ef2  cmp     byte ptr [rax+4], 0
0x140063ef6  jnz     loc_140064016
0x140063efc  mov     rcx, cs:Filter
0x140063f03  mov     r8, rdi
0x140063f06  call    cs:__imp_FltRemoveOpenReparseEntry
0x140063f0d  nop     dword ptr [rax+rax+00h]
0x140063f12  mov     rdx, rdi; Entry
0x140063f15  lea     rcx, stru_1400292C0; Lookaside
0x140063f1c  call    cs:__imp_ExFreeToPagedLookasideList
0x140063f23  nop     dword ptr [rax+rax+00h]
0x140063f28  mov     rcx, [rbp+Context]
0x140063f2c  test    rcx, rcx
0x140063f2f  jnz     short loc_140063F4D
0x140063f31  test    esi, esi
0x140063f33  jnz     loc_1400640C4
0x140063f39  xor     eax, eax
0x140063f3b  add     rsp, 58h
0x140063f3f  pop     r15
0x140063f41  pop     r14
0x140063f43  pop     r13
0x140063f45  pop     r12
0x140063f47  pop     rdi
0x140063f48  pop     rsi
0x140063f49  pop     rbx
0x140063f4a  pop     rbp
0x140063f4b  retn
0x140063f4d  test    bl, bl
0x140063f4f  jz      short loc_140063F64
0x140063f51  add     rcx, 0B0h; RunRef
0x140063f58  call    cs:__imp_ExReleaseRundownProtection
0x140063f5f  nop     dword ptr [rax+rax+00h]
0x140063f64  mov     rcx, [rbp+Context]; Context
0x140063f68  call    cs:__imp_FltReleaseContext
0x140063f6f  nop     dword ptr [rax+rax+00h]
0x140063f74  jmp     short loc_140063F31
0x140063f76  cmp     ebx, 0C0000034h
0x140063f7c  jnz     loc_14006405D
0x140063f82  mov     rax, [rbp+Buffer]
0x140063f86  mov     [rax+18h], ebx
0x140063f89  mov     rax, [rbp+Buffer]
0x140063f8d  mov     qword ptr [rax+20h], 0
0x140063f95  jmp     loc_140063EC8
0x140063f9a  mov     r13b, 1
0x140063f9d  test    eax, eax
0x140063f9f  jz      loc_140063EBD
0x140063fa5  mov     rdx, [rbp+Buffer]
0x140063fa9  lea     r9, [rbp+arg_10]
0x140063fad  mov     rcx, [rbp+Context]
0x140063fb1  mov     r8d, eax
0x140063fb4  call    HsmiIsUnsupportedLogfilePlaceholder
0x140063fb9  mov     sil, [rbp+arg_10]
0x140063fbd  mov     ebx, eax
0x140063fbf  test    eax, eax
0x140063fc1  js      loc_14006443E
0x140063fc7  test    sil, sil
0x140063fca  jnz     loc_140064443
0x140063fd0  mov     rcx, [rbp+Buffer]
0x140063fd4  mov     r9b, r13b
0x140063fd7  xor     r8d, r8d
0x140063fda  mov     rdx, rdi
0x140063fdd  call    HsmpTracePostCallbackEnter
0x140063fe2  mov     r9, [rbp+Buffer]
0x140063fe6  mov     esi, [rbp+var_14]
0x140063fe9  mov     r8d, esi
0x140063fec  mov     rcx, [rbp+Context]
0x140063ff0  mov     rdx, [r9+10h]
0x140063ff4  mov     rdx, [rdx+8]
0x140063ff8  call    HsmpSetupContexts
0x140063ffd  mov     ecx, eax
0x140063fff  mov     ebx, eax
0x140064001  call    HsmDbgBreakOnStatus
0x140064006  test    ebx, ebx
0x140064008  js      loc_1400643E7
0x14006400e  mov     bl, r13b
0x140064011  jmp     loc_140063ECB
0x140064016  cmp     [rcx+8], rdi
0x14006401a  jnz     loc_14006450D
0x140064020  mov     rax, [rdi+8]
0x140064024  cmp     [rax], rdi
0x140064027  jnz     loc_14006450D
0x14006402d  mov     [rax], rcx
0x140064030  mov     [rcx+8], rax
0x140064034  mov     rcx, cs:Filter; FltObject
0x14006403b  call    cs:__imp_FltObjectDereference
0x140064042  nop     dword ptr [rax+rax+00h]
0x140064047  jmp     loc_140063F12
0x14006404c  test    r13b, r13b
0x14006404f  jnz     loc_1400644AB
0x140064055  mov     esi, [rbp+var_14]
0x140064058  jmp     loc_140063F82
0x14006405d  cmp     ebx, 0C000003Ah
0x140064063  jz      loc_140063F82
0x140064069  mov     rcx, cs:WPP_GLOBAL_Control
0x140064070  lea     r14, WPP_GLOBAL_Control
0x140064077  cmp     rcx, r14
0x14006407a  jz      loc_140063F82
0x140064080  mov     eax, [rcx+2Ch]
0x140064083  test    al, 1
0x140064085  jz      loc_140063F82
0x14006408b  cmp     byte ptr [rcx+29h], 5
0x14006408f  jb      loc_140063F82
0x140064095  mov     rax, [rbp+Buffer]
0x140064099  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x1400640a0  mov     rcx, [rcx+18h]
0x1400640a4  mov     edx, 1Ch
0x1400640a9  mov     dword ptr [rsp+58h+var_28], ebx
0x1400640ad  mov     r9, r15
0x1400640b0  mov     [rsp+58h+var_30], rax
0x1400640b5  mov     [rsp+58h+var_38], r12
0x1400640ba  call    WPP_SF_qqqd
0x1400640bf  jmp     loc_140063F82
0x1400640c4  mov     rdx, [rbp+Buffer]
0x1400640c8  mov     r9b, 1
0x1400640cb  xor     ecx, ecx
0x1400640cd  call    HsmpTracePostCallbackExit
0x1400640d2  jmp     loc_140063F39
0x1400640d7  call    cs:__imp_KeEnterCriticalRegion
0x1400640de  nop     dword ptr [rax+rax+00h]
0x1400640e3  mov     rcx, [rbp+Context]
0x1400640e7  mov     dl, 1; Wait
0x1400640e9  add     rcx, 8; Resource
0x1400640ed  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400640f4  nop     dword ptr [rax+rax+00h]
0x1400640f9  mov     rcx, [rbp+Context]
0x1400640fd  lea     rdx, [rbp+Buffer]; Buffer
0x140064101  add     rcx, 70h ; 'p'; Table
0x140064105  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14006410c  nop     dword ptr [rax+rax+00h]
0x140064111  test    rax, rax
0x140064114  jnz     loc_1400641C8
0x14006411a  mov     rcx, [rbp+Context]
0x14006411e  add     rcx, 8; Resource
0x140064122  call    cs:__imp_ExReleaseResourceLite
0x140064129  nop     dword ptr [rax+rax+00h]
0x14006412e  call    cs:__imp_KeLeaveCriticalRegion
0x140064135  nop     dword ptr [rax+rax+00h]
0x14006413a  jmp     loc_140063ECB
0x14006413f  mov     byte ptr [rbp+arg_18], r13b
0x140064143  mov     [rbp+var_17], r13b
0x140064147  mov     eax, [rdx+20h]
0x14006414a  and     eax, 0FFFF0FFFh
0x14006414f  cmp     eax, cs:dword_140029670
0x140064155  jnz     loc_140063EBD
0x14006415b  inc     esi
0x14006415d  cmp     esi, 100h
0x140064163  ja      loc_140064387
0x140064169  mov     r9, [rdx+28h]
0x14006416d  lea     rax, [rbp+var_17]
0x140064171  mov     rcx, [rbp+Context]
0x140064175  cmp     esi, 1
0x140064178  mov     [rsp+58h+var_30], rax
0x14006417d  lea     rax, [rbp+arg_18]
0x140064181  setz    r8b
0x140064185  mov     [rsp+58h+var_38], rax
0x14006418a  movzx   r9d, word ptr [r9+6]
0x14006418f  call    HsmiCreateEnsureDirectoryFullyPopulated
0x140064194  mov     ecx, eax
0x140064196  mov     ebx, eax
0x140064198  call    HsmDbgBreakOnStatus
0x14006419d  test    ebx, ebx
0x14006419f  js      loc_140064360
0x1400641a5  cmp     [rbp+var_17], r13b
0x1400641a9  jz      short loc_140064209
0x1400641ab  xor     eax, eax
0x1400641ad  lea     rcx, [rax+rax*2]
0x1400641b1  inc     rax
0x1400641b4  shl     rcx, 4
0x1400641b8  and     dword ptr [rcx+rdi+14h], 0FFFFFFFDh
0x1400641bd  cmp     rax, 10h
0x1400641c1  jnz     short loc_1400641AD
0x1400641c3  jmp     loc_140063E75
0x1400641c8  mov     rcx, [rbp+Context]
0x1400641cc  lea     rdx, [rax+8]; Buffer
0x1400641d0  add     rcx, 0D8h; Table
0x1400641d7  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400641de  nop     dword ptr [rax+rax+00h]
0x1400641e3  test    rax, rax
0x1400641e6  jnz     loc_1400642AF
0x1400641ec  mov     rcx, [rbp+Context]
0x1400641f0  lea     rdx, [rbp+Buffer]; Buffer
0x1400641f4  add     rcx, 70h ; 'p'; Table
0x1400641f8  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400641ff  nop     dword ptr [rax+rax+00h]
0x140064204  jmp     loc_14006411A
0x140064209  xor     edx, edx
0x14006420b  lea     rcx, [rdx+rdx*2]
0x14006420f  shl     rcx, 4
0x140064213  cmp     byte ptr [rbp+arg_18], r13b
0x140064217  jnz     loc_1400642E0
0x14006421d  and     dword ptr [rdi+rcx+14h], 0FFFFFFFEh
0x140064222  xor     eax, eax
0x140064224  inc     rdx
0x140064227  mov     [rdi+rcx+2Ah], ax
0x14006422c  cmp     rdx, 10h
0x140064230  jnz     short loc_14006420B
0x140064232  mov     rcx, [rbp+Buffer]; Data
0x140064236  call    cs:__imp_FltSetCallbackDataDirty
0x14006423d  nop     dword ptr [rax+rax+00h]
0x140064242  mov     rax, [rbp+arg_8]
0x140064246  mov     rdx, [rbp+Buffer]; CallbackData
0x14006424a  mov     rcx, [rax+18h]; InitiatingInstance
0x14006424e  call    cs:__imp_FltReissueSynchronousIo
0x140064255  nop     dword ptr [rax+rax+00h]
0x14006425a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064261  cmp     rcx, r14
0x140064264  jnz     loc_1400642ED
0x14006426a  mov     rax, [rbp+Buffer]
0x14006426e  mov     ebx, [rax+18h]
0x140064271  mov     ecx, ebx
0x140064273  call    HsmDbgBreakOnStatus
0x140064278  test    ebx, ebx
0x14006427a  jns     loc_140063E75
0x140064280  mov     rcx, cs:WPP_GLOBAL_Control
0x140064287  cmp     rcx, r14
0x14006428a  jz      loc_140064055
0x140064290  mov     eax, [rcx+2Ch]
0x140064293  test    al, 1
0x140064295  jz      loc_140064055
0x14006429b  cmp     byte ptr [rcx+29h], 2
0x14006429f  jb      loc_140064055
0x1400642a5  mov     edx, 20h ; ' '
0x1400642aa  jmp     loc_140064336
0x1400642af  add     dword ptr [rax+8], 0FFFFFFFFh
0x1400642b3  jnz     loc_1400641EC
  ... truncated ...
```
