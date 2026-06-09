# CldiSyncCreateRootNoLock

- ea: `0x14007e72c`
- end: `0x14007ec0e`
- name: `CldiSyncCreateRootNoLock`
- size: `1250`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003d9b0`
- `0x14007e61c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x140035728`
- `0x14007e72c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14007e98c`
- `ntoskrnl!KeInitializeEvent` at `0x14007e98c`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14007ebaf`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14007ebaf`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007e977`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007e977`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14007eac5`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14007eac5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007eae3`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007eae3`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14007eb0c`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14007eb0c`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14007ea48`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14007ea48`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14007e75e`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14007e75e`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14007e9ca`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14007e9ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e89c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eb20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e89c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eb20`
- `ntoskrnl!ExAllocatePool2` at `0x14007e79b`
- `ntoskrnl!ExAllocatePool2` at `0x14007e81e`
- `ntoskrnl!ExAllocatePool2` at `0x14007e919`
- `ntoskrnl!ExAllocatePool2` at `0x14007eb3c`
- `ntoskrnl!ExAllocatePool2` at `0x14007e79b`
- `ntoskrnl!ExAllocatePool2` at `0x14007e81e`
- `ntoskrnl!ExAllocatePool2` at `0x14007e919`
- `ntoskrnl!ExAllocatePool2` at `0x14007eb3c`
- `FLTMGR!FltInitializePushLock` at `0x14007e99c`
- `FLTMGR!FltInitializePushLock` at `0x14007e9da`
- `FLTMGR!FltInitializePushLock` at `0x14007e99c`
- `FLTMGR!FltInitializePushLock` at `0x14007e9da`

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
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  __int64 v22; // rax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v26; // rbx
  __int64 v27; // rax
  PVOID TableContext; // [rsp+20h] [rbp-58h]
  int TableContexta; // [rsp+20h] [rbp-58h]
  _QWORD Buffer[9]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 NewElement; // [rsp+80h] [rbp+8h] BYREF
  __int64 v32; // [rsp+88h] [rbp+10h] BYREF
  __int64 *v33; // [rsp+98h] [rbp+20h]

  v33 = a4;
  v32 = a2;
  v4 = (struct _RTL_AVL_TABLE *)(a1 + 16);
  v7 = 0;
  v8 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), &v32);
  v9 = v8;
  if ( v8 )
  {
    v7 = v8[1];
    if ( v7 )
    {
      v10 = v8[1];
      goto LABEL_30;
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
    if ( v15 )
    {
      v22 = ExAllocatePool2(66, 24, 1920166979);
      *(_QWORD *)(v10 + 80) = v22;
      if ( v22 )
      {
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
LABEL_30:
        v12 = CldiSyncInitializeRootNoLock(a1, v10, v32, a3);
        HsmDbgBreakOnStatus(v12);
        if ( (v12 & 0x80000000) == 0 )
        {
          if ( !v9 )
          {
            Buffer[0] = v32;
            NewElement = 0;
            Buffer[1] = v10;
            if ( !RtlInsertElementGenericTableAvl(v4, Buffer, 0x10u, &NewElement) )
            {
              v12 = -1073741670;
              HsmDbgBreakOnStatus(3221225626LL);
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v24 = 30;
LABEL_49:
                LODWORD(TableContext) = -1073741670;
                WPP_SF_qd(v23->AttachedDevice, v24, WPP_84af94341c2b38590a04322a1aa95385_Traceguids, a1, TableContext);
                goto LABEL_50;
              }
              goto LABEL_50;
            }
            if ( !NewElement )
            {
              v12 = -1073741595;
              HsmDbgBreakOnStatus(3221225701LL);
              goto LABEL_50;
            }
          }
          UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)(a1 + 120), (PCUNICODE_STRING)(v10 + 8), 0);
          v26 = UnicodePrefix;
          if ( UnicodePrefix )
          {
            if ( RtlEqualUnicodeString(UnicodePrefix->Prefix, (PCUNICODE_STRING)(v10 + 8), 1u) )
            {
              if ( *(_QWORD *)&v26[1].NodeTypeCode != v10 )
                *(_QWORD *)&v26[1].NodeTypeCode = v10;
LABEL_53:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qqd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  32,
                  WPP_84af94341c2b38590a04322a1aa95385_Traceguids,
                  a1,
                  v10);
              }
              *v33 = v10;
              return v12;
            }
            RtlRemoveUnicodePrefix((PUNICODE_PREFIX_TABLE)(a1 + 120), v26);
            ExFreePoolWithTag(v26, 0x65707343u);
          }
          v27 = ExAllocatePool2(256, 64, 1701868355);
          if ( !v27 )
          {
            v12 = -1073741670;
            HsmDbgBreakOnStatus(3221225626LL);
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v24 = 31;
              goto LABEL_49;
            }
LABEL_50:
            if ( !v10 )
              return v12;
            goto LABEL_15;
          }
          *(_QWORD *)(v27 + 56) = v10;
          RtlInsertUnicodePrefix(
            (PUNICODE_PREFIX_TABLE)(a1 + 120),
            (PUNICODE_STRING)(v10 + 8),
            (PUNICODE_PREFIX_TABLE_ENTRY)v27);
          goto LABEL_53;
        }
LABEL_15:
        if ( v10 != v7 )
        {
          v18 = *(void **)(v10 + 32);
          if ( v18 )
            ExFreePoolWithTag(v18, 0x69537348u);
          v19 = *(void **)(v10 + 16);
          if ( v19 )
            ExFreePoolWithTag(v19, 0x73557348u);
          v20 = *(void **)(v10 + 80);
          if ( v20 )
            ExFreePoolWithTag(v20, 0x72736C43u);
          ExFreePoolWithTag((PVOID)v10, 0x72736C43u);
        }
        return v12;
      }
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_15;
      }
      v17 = 29;
      TableContexta = -1073741670;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_15;
      }
      v17 = 28;
      TableContexta = v12;
    }
    WPP_SF_qd(v16->AttachedDevice, v17, WPP_84af94341c2b38590a04322a1aa95385_Traceguids, a1, TableContexta);
    goto LABEL_15;
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
0x14007e72c  mov     rax, rsp
0x14007e72f  mov     [rax+18h], rbx
0x14007e733  mov     [rax+20h], r9
0x14007e737  mov     [rax+10h], rdx
0x14007e73b  push    rbp
0x14007e73c  push    rsi
0x14007e73d  push    rdi
0x14007e73e  push    r12
0x14007e740  push    r13
0x14007e742  push    r14
0x14007e744  push    r15
0x14007e746  sub     rsp, 40h
0x14007e74a  lea     rbx, [rcx+10h]
0x14007e74e  mov     r14, rcx
0x14007e751  mov     rcx, rbx; Table
0x14007e754  lea     rdx, [rax+10h]; Buffer
0x14007e758  mov     r12, r8
0x14007e75b  xor     r13d, r13d
0x14007e75e  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14007e765  nop     dword ptr [rax+rax+00h]
0x14007e76a  mov     ebp, 100h
0x14007e76f  mov     esi, 0C000009Ah
0x14007e774  mov     r15, rax
0x14007e777  test    rax, rax
0x14007e77a  jz      short loc_14007E78D
0x14007e77c  mov     r13, [rax+8]
0x14007e780  test    r13, r13
0x14007e783  jz      short loc_14007E78D
0x14007e785  mov     rdi, r13
0x14007e788  jmp     loc_14007E9EA
0x14007e78d  mov     edx, 0D8h
0x14007e792  mov     r8d, 72736C43h
0x14007e798  mov     rcx, rbp
0x14007e79b  call    cs:__imp_ExAllocatePool2
0x14007e7a2  nop     dword ptr [rax+rax+00h]
0x14007e7a7  mov     rdi, rax
0x14007e7aa  test    rax, rax
0x14007e7ad  jnz     short loc_14007E805
0x14007e7af  mov     ecx, esi
0x14007e7b1  mov     ebp, esi
0x14007e7b3  call    HsmDbgBreakOnStatus
0x14007e7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e7bf  lea     rax, WPP_GLOBAL_Control
0x14007e7c6  cmp     rcx, rax
0x14007e7c9  jz      loc_14007E8F0
0x14007e7cf  test    dword ptr [rcx+2Ch], 100h
0x14007e7d6  jz      loc_14007E8F0
0x14007e7dc  cmp     byte ptr [rcx+29h], 2
0x14007e7e0  jb      loc_14007E8F0
0x14007e7e6  mov     rcx, [rcx+18h]
0x14007e7ea  lea     edx, [rdi+1Bh]
0x14007e7ed  mov     r9, r14
0x14007e7f0  mov     dword ptr [rsp+78h+TableContext], esi
0x14007e7f4  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007e7fb  call    WPP_SF_qd
0x14007e800  jmp     loc_14007E8F0
0x14007e805  movzx   edx, word ptr [r12+2]
0x14007e80b  mov     r8d, 73557348h
0x14007e811  mov     [rax+0Ah], dx
0x14007e815  mov     rcx, rbp
0x14007e818  xor     eax, eax
0x14007e81a  mov     [rdi+8], ax
0x14007e81e  call    cs:__imp_ExAllocatePool2
0x14007e825  nop     dword ptr [rax+rax+00h]
0x14007e82a  mov     rcx, rax
0x14007e82d  mov     [rdi+10h], rax
0x14007e831  neg     rcx
0x14007e834  mov     rbx, rax
0x14007e837  sbb     ebp, ebp
0x14007e839  not     ebp
0x14007e83b  and     ebp, esi
0x14007e83d  mov     ecx, ebp
0x14007e83f  call    HsmDbgBreakOnStatus
0x14007e844  test    rbx, rbx
0x14007e847  jnz     loc_14007E90B
0x14007e84d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e854  lea     rax, WPP_GLOBAL_Control
0x14007e85b  cmp     rcx, rax
0x14007e85e  jz      short loc_14007E889
0x14007e860  test    dword ptr [rcx+2Ch], 100h
0x14007e867  jz      short loc_14007E889
0x14007e869  cmp     byte ptr [rcx+29h], 2
0x14007e86d  jb      short loc_14007E889
0x14007e86f  lea     edx, [rbx+1Ch]
0x14007e872  mov     dword ptr [rsp+78h+TableContext], ebp
0x14007e876  mov     rcx, [rcx+18h]
0x14007e87a  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007e881  mov     r9, r14
0x14007e884  call    WPP_SF_qd
0x14007e889  cmp     rdi, r13
0x14007e88c  jz      short loc_14007E8F0
0x14007e88e  mov     rcx, [rdi+20h]; P
0x14007e892  test    rcx, rcx
0x14007e895  jz      short loc_14007E8A8
0x14007e897  mov     edx, 69537348h; Tag
0x14007e89c  call    cs:__imp_ExFreePoolWithTag
0x14007e8a3  nop     dword ptr [rax+rax+00h]
0x14007e8a8  mov     rcx, [rdi+10h]; P
0x14007e8ac  test    rcx, rcx
0x14007e8af  jz      short loc_14007E8C2
0x14007e8b1  mov     edx, 73557348h; Tag
0x14007e8b6  call    cs:__imp_ExFreePoolWithTag
0x14007e8bd  nop     dword ptr [rax+rax+00h]
0x14007e8c2  mov     rcx, [rdi+50h]; P
0x14007e8c6  test    rcx, rcx
0x14007e8c9  jz      short loc_14007E8DC
0x14007e8cb  mov     edx, 72736C43h; Tag
0x14007e8d0  call    cs:__imp_ExFreePoolWithTag
0x14007e8d7  nop     dword ptr [rax+rax+00h]
0x14007e8dc  mov     edx, 72736C43h; Tag
0x14007e8e1  mov     rcx, rdi; P
0x14007e8e4  call    cs:__imp_ExFreePoolWithTag
0x14007e8eb  nop     dword ptr [rax+rax+00h]
0x14007e8f0  mov     rbx, [rsp+78h+arg_10]
0x14007e8f8  mov     eax, ebp
0x14007e8fa  add     rsp, 40h
0x14007e8fe  pop     r15
0x14007e900  pop     r14
0x14007e902  pop     r13
0x14007e904  pop     r12
0x14007e906  pop     rdi
0x14007e907  pop     rsi
0x14007e908  pop     rbp
0x14007e909  retn
0x14007e90b  mov     edx, 18h
0x14007e910  mov     r8d, 72736C43h
0x14007e916  lea     ecx, [rdx+2Ah]
0x14007e919  call    cs:__imp_ExAllocatePool2
0x14007e920  nop     dword ptr [rax+rax+00h]
0x14007e925  mov     [rdi+50h], rax
0x14007e929  test    rax, rax
0x14007e92c  jnz     short loc_14007E973
0x14007e92e  mov     ecx, esi
0x14007e930  mov     ebp, esi
0x14007e932  call    HsmDbgBreakOnStatus
0x14007e937  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e93e  lea     rax, WPP_GLOBAL_Control
0x14007e945  cmp     rcx, rax
0x14007e948  jz      loc_14007E889
0x14007e94e  test    dword ptr [rcx+2Ch], 100h
0x14007e955  jz      loc_14007E889
0x14007e95b  cmp     byte ptr [rcx+29h], 2
0x14007e95f  jb      loc_14007E889
0x14007e965  mov     edx, 1Dh
0x14007e96a  mov     dword ptr [rsp+78h+TableContext], esi
0x14007e96e  jmp     loc_14007E876
0x14007e973  lea     rcx, [rdi+58h]; RunRef
0x14007e977  call    cs:__imp_ExInitializeRundownProtection
0x14007e97e  nop     dword ptr [rax+rax+00h]
0x14007e983  mov     rcx, [rdi+50h]; Event
0x14007e987  xor     r8d, r8d; State
0x14007e98a  xor     edx, edx; Type
0x14007e98c  call    cs:__imp_KeInitializeEvent
0x14007e993  nop     dword ptr [rax+rax+00h]
0x14007e998  lea     rcx, [rdi+68h]; PushLock
0x14007e99c  call    cs:__imp_FltInitializePushLock
0x14007e9a3  nop     dword ptr [rax+rax+00h]
0x14007e9a8  lea     rcx, [rdi+70h]; Table
0x14007e9ac  mov     [rsp+78h+TableContext], 0; TableContext
0x14007e9b5  lea     r9, CldiSyncStreamTableFree; FreeRoutine
0x14007e9bc  lea     r8, CldiSyncStreamTableAllocate; AllocateRoutine
0x14007e9c3  lea     rdx, CldiSyncStreamTableCompare; CompareRoutine
0x14007e9ca  call    cs:__imp_RtlInitializeGenericTableAvl
0x14007e9d1  nop     dword ptr [rax+rax+00h]
0x14007e9d6  lea     rcx, [rdi+38h]; PushLock
0x14007e9da  call    cs:__imp_FltInitializePushLock
0x14007e9e1  nop     dword ptr [rax+rax+00h]
0x14007e9e6  lea     rbx, [r14+10h]
0x14007e9ea  mov     r8, [rsp+78h+arg_8]
0x14007e9f2  mov     r9, r12
0x14007e9f5  mov     rdx, rdi
0x14007e9f8  mov     rcx, r14
0x14007e9fb  call    CldiSyncInitializeRootNoLock
0x14007ea00  mov     ecx, eax
0x14007ea02  mov     ebp, eax
0x14007ea04  call    HsmDbgBreakOnStatus
0x14007ea09  test    ebp, ebp
0x14007ea0b  js      loc_14007E889
0x14007ea11  test    r15, r15
0x14007ea14  jnz     loc_14007EAB4
0x14007ea1a  mov     rdx, [rsp+78h+arg_8]
0x14007ea22  lea     r9, [rsp+78h+NewElement]; NewElement
0x14007ea2a  mov     [rsp+78h+Buffer], rdx
0x14007ea2f  lea     r8d, [r15+10h]; BufferSize
0x14007ea33  lea     rdx, [rsp+78h+Buffer]; Buffer
0x14007ea38  mov     [rsp+78h+NewElement], r15b
0x14007ea40  mov     rcx, rbx; Table
0x14007ea43  mov     [rsp+78h+var_40], rdi
0x14007ea48  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14007ea4f  nop     dword ptr [rax+rax+00h]
0x14007ea54  test    rax, rax
0x14007ea57  jnz     short loc_14007EA99
0x14007ea59  mov     ecx, esi
0x14007ea5b  mov     ebp, esi
0x14007ea5d  call    HsmDbgBreakOnStatus
0x14007ea62  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ea69  lea     rax, WPP_GLOBAL_Control
0x14007ea70  cmp     rcx, rax
0x14007ea73  jz      loc_14007EB94
0x14007ea79  test    dword ptr [rcx+2Ch], 100h
0x14007ea80  jz      loc_14007EB94
0x14007ea86  cmp     byte ptr [rcx+29h], 2
0x14007ea8a  jb      loc_14007EB94
0x14007ea90  lea     edx, [r15+1Eh]
0x14007ea94  jmp     loc_14007EB7D
0x14007ea99  cmp     [rsp+78h+NewElement], 0
0x14007eaa1  jnz     short loc_14007EAB4
0x14007eaa3  mov     ebp, 0C00000E5h
0x14007eaa8  mov     ecx, ebp
0x14007eaaa  call    HsmDbgBreakOnStatus
0x14007eaaf  jmp     loc_14007EB94
0x14007eab4  lea     r12, [rdi+8]
0x14007eab8  xor     r8d, r8d; CaseInsensitiveIndex
0x14007eabb  lea     r15, [r14+78h]
0x14007eabf  mov     rdx, r12; FullName
0x14007eac2  mov     rcx, r15; PrefixTable
0x14007eac5  call    cs:__imp_RtlFindUnicodePrefix
0x14007eacc  nop     dword ptr [rax+rax+00h]
0x14007ead1  mov     rbx, rax
0x14007ead4  test    rax, rax
0x14007ead7  jz      short loc_14007EB2C
0x14007ead9  mov     rcx, [rax+30h]; String1
0x14007eadd  mov     r8b, 1; CaseInSensitive
0x14007eae0  mov     rdx, r12; String2
0x14007eae3  call    cs:__imp_RtlEqualUnicodeString
0x14007eaea  nop     dword ptr [rax+rax+00h]
0x14007eaef  test    al, al
0x14007eaf1  jz      short loc_14007EB06
0x14007eaf3  cmp     [rbx+38h], rdi
0x14007eaf7  jz      loc_14007EBBB
0x14007eafd  mov     [rbx+38h], rdi
0x14007eb01  jmp     loc_14007EBBB
0x14007eb06  mov     rdx, rbx; PrefixTableEntry
0x14007eb09  mov     rcx, r15; PrefixTable
0x14007eb0c  call    cs:__imp_RtlRemoveUnicodePrefix
0x14007eb13  nop     dword ptr [rax+rax+00h]
0x14007eb18  mov     edx, 65707343h; Tag
0x14007eb1d  mov     rcx, rbx; P
0x14007eb20  call    cs:__imp_ExFreePoolWithTag
0x14007eb27  nop     dword ptr [rax+rax+00h]
0x14007eb2c  mov     edx, 40h ; '@'
0x14007eb31  mov     ecx, 100h
0x14007eb36  mov     r8d, 65707343h
0x14007eb3c  call    cs:__imp_ExAllocatePool2
0x14007eb43  nop     dword ptr [rax+rax+00h]
0x14007eb48  test    rax, rax
0x14007eb4b  jnz     short loc_14007EBA2
0x14007eb4d  mov     ecx, esi
0x14007eb4f  mov     ebp, esi
0x14007eb51  call    HsmDbgBreakOnStatus
0x14007eb56  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb5d  lea     rax, WPP_GLOBAL_Control
0x14007eb64  cmp     rcx, rax
0x14007eb67  jz      short loc_14007EB94
0x14007eb69  test    dword ptr [rcx+2Ch], 100h
0x14007eb70  jz      short loc_14007EB94
0x14007eb72  cmp     byte ptr [rcx+29h], 2
0x14007eb76  jb      short loc_14007EB94
0x14007eb78  mov     edx, 1Fh
0x14007eb7d  mov     rcx, [rcx+18h]
0x14007eb81  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007eb88  mov     r9, r14
0x14007eb8b  mov     dword ptr [rsp+78h+TableContext], esi
0x14007eb8f  call    WPP_SF_qd
0x14007eb94  test    rdi, rdi
0x14007eb97  jnz     loc_14007E889
0x14007eb9d  jmp     loc_14007E8F0
0x14007eba2  mov     r8, rax; PrefixTableEntry
0x14007eba5  mov     [rax+38h], rdi
0x14007eba9  mov     rdx, r12; Prefix
0x14007ebac  mov     rcx, r15; PrefixTable
0x14007ebaf  call    cs:__imp_RtlInsertUnicodePrefix
0x14007ebb6  nop     dword ptr [rax+rax+00h]
0x14007ebbb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ebc2  lea     rax, WPP_GLOBAL_Control
0x14007ebc9  cmp     rcx, rax
0x14007ebcc  jz      short loc_14007EBFE
0x14007ebce  test    dword ptr [rcx+2Ch], 100h
0x14007ebd5  jz      short loc_14007EBFE
0x14007ebd7  cmp     byte ptr [rcx+29h], 4
0x14007ebdb  jb      short loc_14007EBFE
0x14007ebdd  mov     rcx, [rcx+18h]
0x14007ebe1  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14007ebe8  mov     edx, 20h ; ' '
0x14007ebed  mov     [rsp+78h+var_50], ebp
0x14007ebf1  mov     r9, r14
0x14007ebf4  mov     [rsp+78h+TableContext], rdi
0x14007ebf9  call    WPP_SF_qqd
0x14007ebfe  mov     rax, [rsp+78h+arg_18]
0x14007ec06  mov     [rax], rdi
0x14007ec09  jmp     loc_14007E8F0
```
