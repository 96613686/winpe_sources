# ClfsReadLogRecord

- ea: `0x140059070`
- end: `0x140059354`
- name: `ClfsReadLogRecord`
- size: `740`
- prototype: `NTSTATUS __stdcall(PVOID pvMarshalContext, PCLFS_LSN plsnFirst, CLFS_CONTEXT_MODE peContextMode, PVOID *ppvReadBuffer, PULONG pcbReadBuffer, PCLFS_RECORD_TYPE peRecordType, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, PVOID *ppvReadContext)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x140059070`
- `0x14005935c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140059172`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140059172`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059216`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079bf2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059216`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079bf2`

## string_xrefs

- `0x140059259`: `ClfsReadLogRecord`
- `0x14005927f`: `ClfsReadLogRecord`
- `0x1400592c1`: `ClfsReadLogRecord`
- `0x140059333`: `ClfsReadLogRecord`

## pseudocode

```c
NTSTATUS __stdcall ClfsReadLogRecord(
        PVOID pvMarshalContext,
        PCLFS_LSN plsnFirst,
        CLFS_CONTEXT_MODE peContextMode,
        PVOID *ppvReadBuffer,
        PULONG pcbReadBuffer,
        PCLFS_RECORD_TYPE peRecordType,
        PCLFS_LSN plsnUndoNext,
        PCLFS_LSN plsnPrevious,
        PVOID *ppvReadContext)
{
  PCLFS_RECORD_TYPE v12; // rcx
  PCLFS_LSN v13; // r9
  PULONG v14; // rdx
  PVOID *v15; // r12
  NTSTATUS v16; // esi
  struct _CLFS_RECORD_HEADER *v17; // rdx
  struct _CLFS_RECORD_HEADER *v19; // [rsp+70h] [rbp+8h] BYREF
  PCLFS_LSN v20; // [rsp+78h] [rbp+10h]
  _CLFS_CONTEXT_MODE v21; // [rsp+80h] [rbp+18h]
  PVOID *v22; // [rsp+88h] [rbp+20h]

  v22 = ppvReadBuffer;
  v21 = peContextMode;
  v20 = plsnFirst;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      226,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadLogRecord",
      205);
  }
  if ( !pvMarshalContext
    || !plsnFirst
    || (v12 = peRecordType) == 0
    || !plsnUndoNext
    || (v13 = plsnPrevious) == 0
    || !ppvReadBuffer
    || (v14 = pcbReadBuffer) == 0
    || (v15 = ppvReadContext) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        227,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadLogRecord",
        220,
        -1073741811);
    }
    return -1073741811;
  }
  *plsnUndoNext = CLFS_LSN_NULL;
  *v13 = CLFS_LSN_NULL;
  *ppvReadBuffer = 0;
  *v14 = 0;
  *v12 = 0;
  *v15 = 0;
  if ( *(_DWORD *)pvMarshalContext != -1040322550 || *((_DWORD *)pvMarshalContext + 1) != 200 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        228,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadLogRecord",
        247,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  v16 = CClfsKernelMarshallingContext::ReadLogRecord(
          (CClfsKernelMarshallingContext *)pvMarshalContext,
          plsnFirst,
          v21,
          &v19,
          v15);
  if ( v16 >= 0 )
  {
    v17 = v19;
    *peRecordType = *((_BYTE *)v19 + 36);
    *plsnFirst = *(PCLFS_LSN)v17;
    *plsnUndoNext = *(CLFS_LSN *)((char *)v17 + 8);
    *plsnPrevious = *(CLFS_LSN *)((char *)v17 + 16);
    *pcbReadBuffer = *((_DWORD *)v17 + 6) - *((unsigned __int16 *)v17 + 17);
    *ppvReadBuffer = (char *)v17 + *((unsigned __int16 *)v17 + 17);
  }
  KeLeaveCriticalRegion();
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        229,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadLogRecord",
        55,
        v16,
        v16);
    }
  }
  else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      230,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadLogRecord",
      59);
  }
  return v16;
}

```

## disassembly

```asm
0x140059070  mov     rax, rsp
0x140059073  mov     [rax+20h], r9
0x140059077  mov     [rax+18h], r8d
0x14005907b  mov     [rax+10h], rdx
0x14005907f  push    rsi
0x140059080  push    r12
0x140059082  push    r13
0x140059084  push    r14
0x140059086  push    r15
0x140059088  sub     rsp, 40h
0x14005908c  mov     r15, r9
0x14005908f  mov     r13, rdx
0x140059092  mov     rsi, rcx
0x140059095  mov     qword ptr [rax+8], 0
0x14005909d  lea     r14, WPP_GLOBAL_Control
0x1400590a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590ab  cmp     rcx, r14
0x1400590ae  jz      short loc_1400590BD
0x1400590b0  test    dword ptr [rcx+2Ch], 4000000h
0x1400590b7  jnz     loc_140059272
0x1400590bd  test    rsi, rsi
0x1400590c0  jz      loc_140059309
0x1400590c6  test    r13, r13
0x1400590c9  jz      loc_140059309
0x1400590cf  mov     rcx, [rsp+68h+peRecordType]
0x1400590d7  test    rcx, rcx
0x1400590da  jz      loc_140059309
0x1400590e0  mov     r8, [rsp+68h+plsnUndoNext]
0x1400590e8  test    r8, r8
0x1400590eb  jz      loc_140059309
0x1400590f1  mov     r9, [rsp+68h+plsnPrevious]
0x1400590f9  test    r9, r9
0x1400590fc  jz      loc_140059309
0x140059102  test    r15, r15
0x140059105  jz      loc_140059309
0x14005910b  mov     rdx, [rsp+68h+pcbReadBuffer]
0x140059113  test    rdx, rdx
0x140059116  jz      loc_140059309
0x14005911c  mov     r12, [rsp+68h+ppvReadContext]
0x140059124  test    r12, r12
0x140059127  jz      loc_140059309
0x14005912d  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140059134  mov     [r8], rax
0x140059137  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x14005913e  mov     [r9], rax
0x140059141  mov     qword ptr [r15], 0
0x140059148  mov     dword ptr [rdx], 0
0x14005914e  mov     byte ptr [rcx], 0
0x140059151  mov     qword ptr [r12], 0
0x140059159  cmp     dword ptr [rsi], 0C1FDF00Ah
0x14005915f  jnz     loc_1400592DD
0x140059165  cmp     dword ptr [rsi+4], 0C8h
0x14005916c  jnz     loc_1400592DD
0x140059172  call    cs:__imp_KeEnterCriticalRegion
0x140059179  nop     dword ptr [rax+rax+00h]
0x14005917e  nop
0x14005917f  mov     [rsp+68h+var_48], r12; void **
0x140059184  lea     r9, [rsp+68h+arg_0]; struct _CLFS_RECORD_HEADER **
0x140059189  mov     r8d, [rsp+68h+arg_10]; enum _CLFS_CONTEXT_MODE
0x140059191  mov     rdx, r13; union _CLS_LSN *
0x140059194  mov     rcx, rsi; this
0x140059197  call    ?ReadLogRecord@CClfsKernelMarshallingContext@@QEAAJAEBT_CLS_LSN@@W4_CLFS_CONTEXT_MODE@@AEAPEAU_CLFS_RECORD_HEADER@@AEAPEAX@Z; CClfsKernelMarshallingContext::ReadLogRecord(_CLS_LSN const &,_CLFS_CONTEXT_MODE,_CLFS_RECORD_HEADER * &,void * &)
0x14005919c  mov     esi, eax
0x14005919e  mov     [rsp+68h+var_38], eax
0x1400591a2  jmp     short loc_1400591BE
0x1400591a4  mov     esi, eax
0x1400591a6  mov     [rsp+68h+var_38], eax
0x1400591aa  lea     r14, WPP_GLOBAL_Control
0x1400591b1  mov     r15, [rsp+68h+arg_18]
0x1400591b9  mov     r13, [rsp+68h+arg_8]
0x1400591be  test    esi, esi
0x1400591c0  js      short loc_140059216
0x1400591c2  mov     rdx, [rsp+68h+arg_0]
0x1400591c7  mov     al, [rdx+24h]
0x1400591ca  mov     rcx, [rsp+68h+peRecordType]
0x1400591d2  mov     [rcx], al
0x1400591d4  mov     rax, [rdx]
0x1400591d7  mov     [r13+0], rax
0x1400591db  mov     rax, [rdx+8]
0x1400591df  mov     rcx, [rsp+68h+plsnUndoNext]
0x1400591e7  mov     [rcx], rax
0x1400591ea  mov     rax, [rdx+10h]
0x1400591ee  mov     rcx, [rsp+68h+plsnPrevious]
0x1400591f6  mov     [rcx], rax
0x1400591f9  movzx   eax, word ptr [rdx+22h]
0x1400591fd  mov     ecx, [rdx+18h]
0x140059200  sub     ecx, eax
0x140059202  mov     rax, [rsp+68h+pcbReadBuffer]
0x14005920a  mov     [rax], ecx
0x14005920c  movzx   eax, word ptr [rdx+22h]
0x140059210  add     rax, rdx
0x140059213  mov     [r15], rax
0x140059216  call    cs:__imp_KeLeaveCriticalRegion
0x14005921d  nop     dword ptr [rax+rax+00h]
0x140059222  test    esi, esi
0x140059224  js      short loc_14005929B
0x140059226  mov     rcx, cs:WPP_GLOBAL_Control
0x14005922d  cmp     rcx, r14
0x140059230  jnz     short loc_140059243
0x140059232  mov     eax, esi
0x140059234  add     rsp, 40h
0x140059238  pop     r15
0x14005923a  pop     r14
0x14005923c  pop     r13
0x14005923e  pop     r12
0x140059240  pop     rsi
0x140059241  retn
0x140059243  test    dword ptr [rcx+2Ch], 4000000h
0x14005924a  jz      short loc_140059232
0x14005924c  mov     edx, 0E6h
0x140059251  mov     dword ptr [rsp+68h+var_48], 1C3Bh
0x140059259  lea     r9, aClfsreadlogrec; "ClfsReadLogRecord"
0x140059260  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140059267  mov     rcx, [rcx+18h]
0x14005926b  call    WPP_SF_sd
0x140059270  jmp     short loc_140059232
0x140059272  mov     edx, 0E2h
0x140059277  mov     dword ptr [rsp+68h+var_48], 1BCDh
0x14005927f  lea     r9, aClfsreadlogrec; "ClfsReadLogRecord"
0x140059286  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005928d  mov     rcx, [rcx+18h]
0x140059291  call    WPP_SF_sd
0x140059296  jmp     loc_1400590BD
0x14005929b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400592a2  cmp     rcx, r14
0x1400592a5  jz      short loc_140059232
0x1400592a7  test    dword ptr [rcx+2Ch], 4000000h
0x1400592ae  jz      short loc_140059232
0x1400592b0  mov     edx, 0E5h
0x1400592b5  mov     [rsp+68h+var_40], esi
0x1400592b9  mov     dword ptr [rsp+68h+var_48], 1C37h
0x1400592c1  lea     r9, aClfsreadlogrec; "ClfsReadLogRecord"
0x1400592c8  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400592cf  mov     rcx, [rcx+18h]
0x1400592d3  call    WPP_SF_slD
0x1400592d8  jmp     loc_140059232
0x1400592dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400592e4  cmp     rcx, r14
0x1400592e7  jz      short loc_14005934A
0x1400592e9  test    dword ptr [rcx+2Ch], 4000000h
0x1400592f0  jz      short loc_14005934A
0x1400592f2  mov     edx, 0E4h
0x1400592f7  mov     [rsp+68h+var_40], 0C000000Dh
0x1400592ff  mov     dword ptr [rsp+68h+var_48], 1BF7h
0x140059307  jmp     short loc_140059333
0x140059309  mov     rcx, cs:WPP_GLOBAL_Control
0x140059310  cmp     rcx, r14
0x140059313  jz      short loc_14005934A
0x140059315  test    dword ptr [rcx+2Ch], 4000000h
0x14005931c  jz      short loc_14005934A
0x14005931e  mov     edx, 0E3h
0x140059323  mov     [rsp+68h+var_40], 0C000000Dh
0x14005932b  mov     dword ptr [rsp+68h+var_48], 1BDCh
0x140059333  lea     r9, aClfsreadlogrec; "ClfsReadLogRecord"
0x14005933a  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140059341  mov     rcx, [rcx+18h]
0x140059345  call    WPP_SF_slD
0x14005934a  mov     eax, 0C000000Dh
0x14005934f  jmp     loc_140059234
0x140079be9  push    rbp
0x140079beb  sub     rsp, 30h
0x140079bef  mov     rbp, rdx
0x140079bf2  call    cs:__imp_KeLeaveCriticalRegion
0x140079bf9  nop     dword ptr [rax+rax+00h]
0x140079bfe  nop
0x140079bff  add     rsp, 30h
0x140079c03  pop     rbp
0x140079c04  retn
```
