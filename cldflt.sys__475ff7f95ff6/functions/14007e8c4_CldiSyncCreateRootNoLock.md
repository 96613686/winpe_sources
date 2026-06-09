# CldiSyncCreateRootNoLock

- ea: `0x14007e8c4`
- end: `0x14007eda6`
- name: `CldiSyncCreateRootNoLock`
- size: `1250`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003d9d0`
- `0x14007e7b4`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x140035728`
- `0x14007e8c4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14007eb24`
- `ntoskrnl!KeInitializeEvent` at `0x14007eb24`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14007ed47`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14007ed47`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007eb0f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007eb0f`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14007ec5d`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14007ec5d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007ec7b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007ec7b`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14007eca4`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14007eca4`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14007ebe0`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14007ebe0`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14007e8f6`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14007e8f6`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14007eb62`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14007eb62`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ecb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ea7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ecb8`
- `ntoskrnl!ExAllocatePool2` at `0x14007e933`
- `ntoskrnl!ExAllocatePool2` at `0x14007e9b6`
- `ntoskrnl!ExAllocatePool2` at `0x14007eab1`
- `ntoskrnl!ExAllocatePool2` at `0x14007ecd4`
- `ntoskrnl!ExAllocatePool2` at `0x14007e933`
- `ntoskrnl!ExAllocatePool2` at `0x14007e9b6`
- `ntoskrnl!ExAllocatePool2` at `0x14007eab1`
- `ntoskrnl!ExAllocatePool2` at `0x14007ecd4`
- `FLTMGR!FltInitializePushLock` at `0x14007eb34`
- `FLTMGR!FltInitializePushLock` at `0x14007eb72`
- `FLTMGR!FltInitializePushLock` at `0x14007eb34`
- `FLTMGR!FltInitializePushLock` at `0x14007eb72`

## pseudocode

```c
__int64 __fastcall CldiSyncCreateRootNoLock(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  struct _RTL_AVL_TABLE *v4; // rbx
  __int64 v7; // r13
  _QWORD *v8; // rax
  _QWORD *v9; // r15
  __int64 v10; // rdi
  __int64 Pool2; // rax
  unsigned int v12; // ebp
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rbx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  __int64 v20; // rax
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v24; // rbx
  __int64 v25; // rax
  _QWORD Buffer[9]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 NewElement; // [rsp+80h] [rbp+8h] BYREF
  __int64 v28; // [rsp+88h] [rbp+10h] BYREF
  __int64 *v29; // [rsp+98h] [rbp+20h]

  v29 = a4;
  v28 = a2;
  v4 = (struct _RTL_AVL_TABLE *)(a1 + 16);
  v7 = 0;
  v8 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), &v28);
  v9 = v8;
  if ( v8 )
  {
    v7 = v8[1];
    if ( v7 )
    {
      v10 = v8[1];
      goto LABEL_29;
    }
  }
  Pool2 = ExAllocatePool2(256, 216, 1920166979);
  v10 = Pool2;
  if ( Pool2 )
  {
    v13 = *(unsigned __int16 *)(a3 + 2);
    *(_WORD *)(Pool2 + 10) = v13;
    *(_WORD *)(Pool2 + 8) = 0;
    v14 = ExAllocatePool2(256, v13, 1934979912);
    *(_QWORD *)(v10 + 16) = v14;
    v15 = v14;
    v12 = v14 == 0 ? 0xC000009A : 0;
    HsmDbgBreakOnStatus(v12);
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_84af94341c2b38590a04322a1aa95385_Traceguids, a1, v12);
      }
      goto LABEL_14;
    }
    v20 = ExAllocatePool2(66, 24, 1920166979);
    *(_QWORD *)(v10 + 80) = v20;
    if ( !v20 )
    {
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_84af94341c2b38590a04322a1aa95385_Traceguids,
          a1,
          -1073741670);
      }
      goto LABEL_14;
    }
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v10 + 88));
    KeInitializeEvent(*(PRKEVENT *)(v10 + 80), NotificationEvent, 0);
    FltInitializePushLock((PULONG_PTR)(v10 + 104));
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(v10 + 112),
      CldiSyncStreamTableCompare,
      CldiSyncStreamTableAllocate,
      CldiSyncStreamTableFree,
      0);
    FltInitializePushLock((PULONG_PTR)(v10 + 56));
    v4 = (struct _RTL_AVL_TABLE *)(a1 + 16);
LABEL_29:
    v12 = CldiSyncInitializeRootNoLock(a1, v10, v28, a3);
    HsmDbgBreakOnStatus(v12);
    if ( (v12 & 0x80000000) == 0 )
    {
      if ( !v9 )
      {
        Buffer[0] = v28;
        NewElement = 0;
        Buffer[1] = v10;
        if ( !RtlInsertElementGenericTableAvl(v4, Buffer, 0x10u, &NewElement) )
        {
          v12 = -1073741670;
          HsmDbgBreakOnStatus(3221225626LL);
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v22 = 30;
LABEL_48:
            WPP_SF_qd(v21->AttachedDevice, v22, WPP_84af94341c2b38590a04322a1aa95385_Traceguids, a1, -1073741670);
            goto LABEL_49;
          }
          goto LABEL_49;
        }
        if ( !NewElement )
        {
          v12 = -1073741595;
          HsmDbgBreakOnStatus(3221225701LL);
          goto LABEL_49;
        }
      }
      UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)(a1 + 120), (PCUNICODE_STRING)(v10 + 8), 0);
      v24 = UnicodePrefix;
      if ( UnicodePrefix )
      {
        if ( RtlEqualUnicodeString(UnicodePrefix->Prefix, (PCUNICODE_STRING)(v10 + 8), 1u) )
        {
          if ( *(_QWORD *)&v24[1].NodeTypeCode != v10 )
            *(_QWORD *)&v24[1].NodeTypeCode = v10;
LABEL_52:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qqd(
              WPP_GLOBAL_Control->AttachedDevice,
              32,
              WPP_84af94341c2b38590a04322a1aa95385_Traceguids,
              a1,
              v10,
              v12);
          }
          *v29 = v10;
          return v12;
        }
        RtlRemoveUnicodePrefix((PUNICODE_PREFIX_TABLE)(a1 + 120), v24);
        ExFreePoolWithTag(v24, 0x65707343u);
      }
      v25 = ExAllocatePool2(256, 64, 1701868355);
      if ( !v25 )
      {
        v12 = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v22 = 31;
          goto LABEL_48;
        }
LABEL_49:
        if ( !v10 )
          return v12;
        goto LABEL_14;
      }
      *(_QWORD *)(v25 + 56) = v10;
      RtlInsertUnicodePrefix(
        (PUNICODE_PREFIX_TABLE)(a1 + 120),
        (PUNICODE_STRING)(v10 + 8),
        (PUNICODE_PREFIX_TABLE_ENTRY)v25);
      goto LABEL_52;
    }
LABEL_14:
    if ( v10 != v7 )
    {
      v16 = *(void **)(v10 + 32);
      if ( v16 )
        ExFreePoolWithTag(v16, 0x69537348u);
      v17 = *(void **)(v10 + 16);
      if ( v17 )
        ExFreePoolWithTag(v17, 0x73557348u);
      v18 = *(void **)(v10 + 80);
      if ( v18 )
        ExFreePoolWithTag(v18, 0x72736C43u);
      ExFreePoolWithTag((PVOID)v10, 0x72736C43u);
    }
    return v12;
  }
  v12 = -1073741670;
  HsmDbgBreakOnStatus(3221225626LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_84af94341c2b38590a04322a1aa95385_Traceguids, a1, -1073741670);
  }
  return v12;
}

```

## disassembly

```asm
0x14007e8c4  mov     rax, rsp
0x14007e8c7  mov     [rax+18h], rbx
0x14007e8cb  mov     [rax+20h], r9
0x14007e8cf  mov     [rax+10h], rdx
0x14007e8d3  push    rbp
0x14007e8d4  push    rsi
0x14007e8d5  push    rdi
0x14007e8d6  push    r12
0x14007e8d8  push    r13
0x14007e8da  push    r14
0x14007e8dc  push    r15
0x14007e8de  sub     rsp, 40h
0x14007e8e2  lea     rbx, [rcx+10h]
0x14007e8e6  mov     r14, rcx
0x14007e8e9  mov     rcx, rbx; Table
0x14007e8ec  lea     rdx, [rax+10h]; Buffer
0x14007e8f0  mov     r12, r8
0x14007e8f3  xor     r13d, r13d
0x14007e8f6  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14007e8fd  nop     dword ptr [rax+rax+00h]
0x14007e902  mov     ebp, 100h
0x14007e907  mov     esi, 0C000009Ah
0x14007e90c  mov     r15, rax
0x14007e90f  test    rax, rax
0x14007e912  jz      short loc_14007E925
0x14007e914  mov     r13, [rax+8]
0x14007e918  test    r13, r13
0x14007e91b  jz      short loc_14007E925
0x14007e91d  mov     rdi, r13
0x14007e920  jmp     loc_14007EB82
0x14007e925  mov     edx, 0D8h
0x14007e92a  mov     r8d, 72736C43h
0x14007e930  mov     rcx, rbp
0x14007e933  call    cs:__imp_ExAllocatePool2
0x14007e93a  nop     dword ptr [rax+rax+00h]
0x14007e93f  mov     rdi, rax
0x14007e942  test    rax, rax
0x14007e945  jnz     short loc_14007E99D
0x14007e947  mov     ecx, esi
0x14007e949  mov     ebp, esi
0x14007e94b  call    HsmDbgBreakOnStatus
0x14007e950  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e957  lea     rax, WPP_GLOBAL_Control
0x14007e95e  cmp     rcx, rax
0x14007e961  jz      loc_14007EA88
0x14007e967  test    dword ptr [rcx+2Ch], 100h
0x14007e96e  jz      loc_14007EA88
0x14007e974  cmp     byte ptr [rcx+29h], 2
0x14007e978  jb      loc_14007EA88
0x14007e97e  mov     rcx, [rcx+18h]
0x14007e982  lea     edx, [rdi+1Bh]
0x14007e985  mov     r9, r14
0x14007e988  mov     dword ptr [rsp+78h+TableContext], esi
0x14007e98c  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007e993  call    WPP_SF_qd
0x14007e998  jmp     loc_14007EA88
0x14007e99d  movzx   edx, word ptr [r12+2]
0x14007e9a3  mov     r8d, 73557348h
0x14007e9a9  mov     [rax+0Ah], dx
0x14007e9ad  mov     rcx, rbp
0x14007e9b0  xor     eax, eax
0x14007e9b2  mov     [rdi+8], ax
0x14007e9b6  call    cs:__imp_ExAllocatePool2
0x14007e9bd  nop     dword ptr [rax+rax+00h]
0x14007e9c2  mov     rcx, rax
0x14007e9c5  mov     [rdi+10h], rax
0x14007e9c9  neg     rcx
0x14007e9cc  mov     rbx, rax
0x14007e9cf  sbb     ebp, ebp
0x14007e9d1  not     ebp
0x14007e9d3  and     ebp, esi
0x14007e9d5  mov     ecx, ebp
0x14007e9d7  call    HsmDbgBreakOnStatus
0x14007e9dc  test    rbx, rbx
0x14007e9df  jnz     loc_14007EAA3
0x14007e9e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e9ec  lea     rax, WPP_GLOBAL_Control
0x14007e9f3  cmp     rcx, rax
0x14007e9f6  jz      short loc_14007EA21
0x14007e9f8  test    dword ptr [rcx+2Ch], 100h
0x14007e9ff  jz      short loc_14007EA21
0x14007ea01  cmp     byte ptr [rcx+29h], 2
0x14007ea05  jb      short loc_14007EA21
0x14007ea07  lea     edx, [rbx+1Ch]
0x14007ea0a  mov     dword ptr [rsp+78h+TableContext], ebp
0x14007ea0e  mov     rcx, [rcx+18h]
0x14007ea12  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007ea19  mov     r9, r14
0x14007ea1c  call    WPP_SF_qd
0x14007ea21  cmp     rdi, r13
0x14007ea24  jz      short loc_14007EA88
0x14007ea26  mov     rcx, [rdi+20h]; P
0x14007ea2a  test    rcx, rcx
0x14007ea2d  jz      short loc_14007EA40
0x14007ea2f  mov     edx, 69537348h; Tag
0x14007ea34  call    cs:__imp_ExFreePoolWithTag
0x14007ea3b  nop     dword ptr [rax+rax+00h]
0x14007ea40  mov     rcx, [rdi+10h]; P
0x14007ea44  test    rcx, rcx
0x14007ea47  jz      short loc_14007EA5A
0x14007ea49  mov     edx, 73557348h; Tag
0x14007ea4e  call    cs:__imp_ExFreePoolWithTag
0x14007ea55  nop     dword ptr [rax+rax+00h]
0x14007ea5a  mov     rcx, [rdi+50h]; P
0x14007ea5e  test    rcx, rcx
0x14007ea61  jz      short loc_14007EA74
0x14007ea63  mov     edx, 72736C43h; Tag
0x14007ea68  call    cs:__imp_ExFreePoolWithTag
0x14007ea6f  nop     dword ptr [rax+rax+00h]
0x14007ea74  mov     edx, 72736C43h; Tag
0x14007ea79  mov     rcx, rdi; P
0x14007ea7c  call    cs:__imp_ExFreePoolWithTag
0x14007ea83  nop     dword ptr [rax+rax+00h]
0x14007ea88  mov     rbx, [rsp+78h+arg_10]
0x14007ea90  mov     eax, ebp
0x14007ea92  add     rsp, 40h
0x14007ea96  pop     r15
0x14007ea98  pop     r14
0x14007ea9a  pop     r13
0x14007ea9c  pop     r12
0x14007ea9e  pop     rdi
0x14007ea9f  pop     rsi
0x14007eaa0  pop     rbp
0x14007eaa1  retn
0x14007eaa3  mov     edx, 18h
0x14007eaa8  mov     r8d, 72736C43h
0x14007eaae  lea     ecx, [rdx+2Ah]
0x14007eab1  call    cs:__imp_ExAllocatePool2
0x14007eab8  nop     dword ptr [rax+rax+00h]
0x14007eabd  mov     [rdi+50h], rax
0x14007eac1  test    rax, rax
0x14007eac4  jnz     short loc_14007EB0B
0x14007eac6  mov     ecx, esi
0x14007eac8  mov     ebp, esi
0x14007eaca  call    HsmDbgBreakOnStatus
0x14007eacf  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ead6  lea     rax, WPP_GLOBAL_Control
0x14007eadd  cmp     rcx, rax
0x14007eae0  jz      loc_14007EA21
0x14007eae6  test    dword ptr [rcx+2Ch], 100h
0x14007eaed  jz      loc_14007EA21
0x14007eaf3  cmp     byte ptr [rcx+29h], 2
0x14007eaf7  jb      loc_14007EA21
0x14007eafd  mov     edx, 1Dh
0x14007eb02  mov     dword ptr [rsp+78h+TableContext], esi
0x14007eb06  jmp     loc_14007EA0E
0x14007eb0b  lea     rcx, [rdi+58h]; RunRef
0x14007eb0f  call    cs:__imp_ExInitializeRundownProtection
0x14007eb16  nop     dword ptr [rax+rax+00h]
0x14007eb1b  mov     rcx, [rdi+50h]; Event
0x14007eb1f  xor     r8d, r8d; State
0x14007eb22  xor     edx, edx; Type
0x14007eb24  call    cs:__imp_KeInitializeEvent
0x14007eb2b  nop     dword ptr [rax+rax+00h]
0x14007eb30  lea     rcx, [rdi+68h]; PushLock
0x14007eb34  call    cs:__imp_FltInitializePushLock
0x14007eb3b  nop     dword ptr [rax+rax+00h]
0x14007eb40  lea     rcx, [rdi+70h]; Table
0x14007eb44  mov     [rsp+78h+TableContext], 0; TableContext
0x14007eb4d  lea     r9, CldiSyncStreamTableFree; FreeRoutine
0x14007eb54  lea     r8, CldiSyncStreamTableAllocate; AllocateRoutine
0x14007eb5b  lea     rdx, CldiSyncStreamTableCompare; CompareRoutine
0x14007eb62  call    cs:__imp_RtlInitializeGenericTableAvl
0x14007eb69  nop     dword ptr [rax+rax+00h]
0x14007eb6e  lea     rcx, [rdi+38h]; PushLock
0x14007eb72  call    cs:__imp_FltInitializePushLock
0x14007eb79  nop     dword ptr [rax+rax+00h]
0x14007eb7e  lea     rbx, [r14+10h]
0x14007eb82  mov     r8, [rsp+78h+arg_8]
0x14007eb8a  mov     r9, r12
0x14007eb8d  mov     rdx, rdi
0x14007eb90  mov     rcx, r14
0x14007eb93  call    CldiSyncInitializeRootNoLock
0x14007eb98  mov     ecx, eax
0x14007eb9a  mov     ebp, eax
0x14007eb9c  call    HsmDbgBreakOnStatus
0x14007eba1  test    ebp, ebp
0x14007eba3  js      loc_14007EA21
0x14007eba9  test    r15, r15
0x14007ebac  jnz     loc_14007EC4C
0x14007ebb2  mov     rdx, [rsp+78h+arg_8]
0x14007ebba  lea     r9, [rsp+78h+NewElement]; NewElement
0x14007ebc2  mov     [rsp+78h+Buffer], rdx
0x14007ebc7  lea     r8d, [r15+10h]; BufferSize
0x14007ebcb  lea     rdx, [rsp+78h+Buffer]; Buffer
0x14007ebd0  mov     [rsp+78h+NewElement], r15b
0x14007ebd8  mov     rcx, rbx; Table
0x14007ebdb  mov     [rsp+78h+var_40], rdi
0x14007ebe0  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14007ebe7  nop     dword ptr [rax+rax+00h]
0x14007ebec  test    rax, rax
0x14007ebef  jnz     short loc_14007EC31
0x14007ebf1  mov     ecx, esi
0x14007ebf3  mov     ebp, esi
0x14007ebf5  call    HsmDbgBreakOnStatus
0x14007ebfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec01  lea     rax, WPP_GLOBAL_Control
0x14007ec08  cmp     rcx, rax
0x14007ec0b  jz      loc_14007ED2C
0x14007ec11  test    dword ptr [rcx+2Ch], 100h
0x14007ec18  jz      loc_14007ED2C
0x14007ec1e  cmp     byte ptr [rcx+29h], 2
0x14007ec22  jb      loc_14007ED2C
0x14007ec28  lea     edx, [r15+1Eh]
0x14007ec2c  jmp     loc_14007ED15
0x14007ec31  cmp     [rsp+78h+NewElement], 0
0x14007ec39  jnz     short loc_14007EC4C
0x14007ec3b  mov     ebp, 0C00000E5h
0x14007ec40  mov     ecx, ebp
0x14007ec42  call    HsmDbgBreakOnStatus
0x14007ec47  jmp     loc_14007ED2C
0x14007ec4c  lea     r12, [rdi+8]
0x14007ec50  xor     r8d, r8d; CaseInsensitiveIndex
0x14007ec53  lea     r15, [r14+78h]
0x14007ec57  mov     rdx, r12; FullName
0x14007ec5a  mov     rcx, r15; PrefixTable
0x14007ec5d  call    cs:__imp_RtlFindUnicodePrefix
0x14007ec64  nop     dword ptr [rax+rax+00h]
0x14007ec69  mov     rbx, rax
0x14007ec6c  test    rax, rax
0x14007ec6f  jz      short loc_14007ECC4
0x14007ec71  mov     rcx, [rax+30h]; String1
0x14007ec75  mov     r8b, 1; CaseInSensitive
0x14007ec78  mov     rdx, r12; String2
0x14007ec7b  call    cs:__imp_RtlEqualUnicodeString
0x14007ec82  nop     dword ptr [rax+rax+00h]
0x14007ec87  test    al, al
0x14007ec89  jz      short loc_14007EC9E
0x14007ec8b  cmp     [rbx+38h], rdi
0x14007ec8f  jz      loc_14007ED53
0x14007ec95  mov     [rbx+38h], rdi
0x14007ec99  jmp     loc_14007ED53
0x14007ec9e  mov     rdx, rbx; PrefixTableEntry
0x14007eca1  mov     rcx, r15; PrefixTable
0x14007eca4  call    cs:__imp_RtlRemoveUnicodePrefix
0x14007ecab  nop     dword ptr [rax+rax+00h]
0x14007ecb0  mov     edx, 65707343h; Tag
0x14007ecb5  mov     rcx, rbx; P
0x14007ecb8  call    cs:__imp_ExFreePoolWithTag
0x14007ecbf  nop     dword ptr [rax+rax+00h]
0x14007ecc4  mov     edx, 40h ; '@'
0x14007ecc9  mov     ecx, 100h
0x14007ecce  mov     r8d, 65707343h
0x14007ecd4  call    cs:__imp_ExAllocatePool2
0x14007ecdb  nop     dword ptr [rax+rax+00h]
0x14007ece0  test    rax, rax
0x14007ece3  jnz     short loc_14007ED3A
0x14007ece5  mov     ecx, esi
0x14007ece7  mov     ebp, esi
0x14007ece9  call    HsmDbgBreakOnStatus
0x14007ecee  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ecf5  lea     rax, WPP_GLOBAL_Control
0x14007ecfc  cmp     rcx, rax
0x14007ecff  jz      short loc_14007ED2C
0x14007ed01  test    dword ptr [rcx+2Ch], 100h
0x14007ed08  jz      short loc_14007ED2C
0x14007ed0a  cmp     byte ptr [rcx+29h], 2
0x14007ed0e  jb      short loc_14007ED2C
0x14007ed10  mov     edx, 1Fh
0x14007ed15  mov     rcx, [rcx+18h]
0x14007ed19  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007ed20  mov     r9, r14
0x14007ed23  mov     dword ptr [rsp+78h+TableContext], esi
0x14007ed27  call    WPP_SF_qd
0x14007ed2c  test    rdi, rdi
0x14007ed2f  jnz     loc_14007EA21
0x14007ed35  jmp     loc_14007EA88
0x14007ed3a  mov     r8, rax; PrefixTableEntry
0x14007ed3d  mov     [rax+38h], rdi
0x14007ed41  mov     rdx, r12; Prefix
0x14007ed44  mov     rcx, r15; PrefixTable
0x14007ed47  call    cs:__imp_RtlInsertUnicodePrefix
0x14007ed4e  nop     dword ptr [rax+rax+00h]
0x14007ed53  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed5a  lea     rax, WPP_GLOBAL_Control
0x14007ed61  cmp     rcx, rax
0x14007ed64  jz      short loc_14007ED96
0x14007ed66  test    dword ptr [rcx+2Ch], 100h
0x14007ed6d  jz      short loc_14007ED96
0x14007ed6f  cmp     byte ptr [rcx+29h], 4
0x14007ed73  jb      short loc_14007ED96
0x14007ed75  mov     rcx, [rcx+18h]
0x14007ed79  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007ed80  mov     edx, 20h ; ' '
0x14007ed85  mov     [rsp+78h+var_50], ebp
0x14007ed89  mov     r9, r14
0x14007ed8c  mov     [rsp+78h+TableContext], rdi
0x14007ed91  call    WPP_SF_qqd
0x14007ed96  mov     rax, [rsp+78h+arg_18]
0x14007ed9e  mov     [rax], rdi
0x14007eda1  jmp     loc_14007EA88
```
