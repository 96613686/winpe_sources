# CmpRmReDoPhase

- ea: `0x1408061b4`
- end: `0x14080638a`
- name: `CmpRmReDoPhase`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1408e5618`

## callees

- `0x140468330`
- `0x140805d44`
- `0x140805ea8`
- `0x1408061b4`
- `0x140806548`
- `0x140809810`
- `0x140a2ceb8`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x14080634b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x14080634b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14080636f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14080636f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x14080623a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x14080623a`

## pseudocode

```c
int __fastcall CmpRmReDoPhase(__int64 a1, CLFS_LSN a2)
{
  _QWORD *v2; // rax
  int v3; // esi
  struct _PRIVILEGE_SET *v4; // rbx
  ULONG v5; // edx
  int v6; // eax
  __int64 v7; // rdi
  PVOID ppvReadBuffer; // [rsp+58h] [rbp-9h] BYREF
  PVOID pvReadContext; // [rsp+60h] [rbp-1h] BYREF
  struct _PRIVILEGE_SET *v11; // [rsp+68h] [rbp+7h] BYREF
  __int64 v12; // [rsp+70h] [rbp+Fh] BYREF
  CLFS_LSN plsnPrevious; // [rsp+78h] [rbp+17h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+80h] [rbp+1Fh] BYREF
  CLFS_LSN plsnRecord; // [rsp+88h] [rbp+27h] BYREF
  CLS_RECORD_TYPE peRecordType; // [rsp+C8h] [rbp+67h] BYREF
  CLFS_LSN plsnFirst; // [rsp+D0h] [rbp+6Fh] BYREF
  ULONG pcbBuffer; // [rsp+D8h] [rbp+77h] BYREF
  ULONG v19; // [rsp+E0h] [rbp+7Fh] BYREF

  plsnFirst = a2;
  v2 = (_QWORD *)(a1 + 16);
  v3 = a1;
  pvReadContext = 0;
  ppvReadBuffer = 0;
  pcbBuffer = 0;
  plsnUndoNext.ullOffset = 0;
  plsnPrevious.ullOffset = 0;
  plsnRecord.ullOffset = 0;
  peRecordType = 0;
  v12 = 0;
  if ( (_QWORD *)*v2 == v2 )
    return (int)v2;
  LODWORD(v2) = ClfsReadLogRecord(
                  *(PVOID *)(a1 + 96),
                  &plsnFirst,
                  ClfsContextForward,
                  &ppvReadBuffer,
                  &pcbBuffer,
                  &peRecordType,
                  &plsnUndoNext,
                  &plsnPrevious,
                  &pvReadContext);
  while ( (int)v2 >= 0 )
  {
    if ( (peRecordType & 1) == 0 )
      goto LABEL_17;
    if ( pcbBuffer < 0x30 )
      break;
    if ( (int)CmpTransSearchAddTransFromRm(v3, 0, (int)ppvReadBuffer + 16, 0, (__int64)&v12) < 0 )
      goto LABEL_17;
    v4 = (struct _PRIVILEGE_SET *)ppvReadBuffer;
    v5 = pcbBuffer;
    v11 = (struct _PRIVILEGE_SET *)ppvReadBuffer;
    v19 = pcbBuffer;
    if ( *((int *)ppvReadBuffer + 3) < 0 )
    {
      LODWORD(v2) = CmpDoReadTxRBigLogRecord(
                      (_DWORD)pvReadContext,
                      (_DWORD)ppvReadBuffer,
                      pcbBuffer,
                      (unsigned int)&v11,
                      (__int64)&v19);
      if ( (int)v2 < 0 )
        break;
      v4 = v11;
      v5 = v19;
    }
    v6 = CmpVerifyLogRecord((__int64)v4, v5);
    v7 = v12;
    if ( v6 >= 0 )
    {
      CmpRealignLogBuffers((__int64)v4);
      if ( (int)CmpDoReDoRecord(v7, (__int64)v4) >= 0 )
        goto LABEL_15;
    }
    else if ( (_BYTE)KdDebuggerEnabled && !(_BYTE)KdDebuggerNotPresent )
    {
      __debugbreak();
    }
    *(_DWORD *)(v7 + 48) |= 2u;
LABEL_15:
    if ( *((int *)ppvReadBuffer + 3) < 0 )
      CmSiFreeMemory(v4);
LABEL_17:
    peRecordType = 1;
    LODWORD(v2) = ClfsReadNextLogRecord(
                    pvReadContext,
                    &ppvReadBuffer,
                    &pcbBuffer,
                    &peRecordType,
                    0,
                    &plsnUndoNext,
                    &plsnPrevious,
                    &plsnRecord);
    if ( (_DWORD)v2 == -1073741807 )
      break;
  }
  if ( pvReadContext )
    LODWORD(v2) = ClfsTerminateReadLog(pvReadContext);
  return (int)v2;
}

```

## disassembly

```asm
0x1408061b4  mov     r11, rsp
0x1408061b7  mov     [r11+10h], rdx
0x1408061bb  push    rbp
0x1408061bc  push    rbx
0x1408061bd  push    rsi
0x1408061be  push    rdi
0x1408061bf  push    r14
0x1408061c1  lea     rbp, [r11-5Fh]
0x1408061c5  sub     rsp, 90h
0x1408061cc  xor     r14d, r14d
0x1408061cf  lea     rax, [rcx+10h]
0x1408061d3  mov     rsi, rcx
0x1408061d6  mov     [rbp+57h+pvReadContext], r14
0x1408061da  mov     [rbp+57h+ppvReadBuffer], r14
0x1408061de  mov     [rbp+57h+pcbBuffer], r14d
0x1408061e2  mov     qword ptr [rbp+57h+var_38], r14
0x1408061e6  mov     qword ptr [rbp+57h+plsnPrevious], r14
0x1408061ea  mov     qword ptr [rbp+57h+plsnRecord], r14
0x1408061ee  mov     [rbp+57h+arg_0], r14b
0x1408061f2  mov     [rbp+57h+var_48], r14
0x1408061f6  cmp     [rax], rax
0x1408061f9  jz      loc_14080637B
0x1408061ff  mov     rcx, [rcx+60h]; pvMarshalContext
0x140806203  lea     rax, [rbp+57h+pvReadContext]
0x140806207  mov     [r11-78h], rax
0x14080620b  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x14080620f  lea     rax, [rbp+57h+plsnPrevious]
0x140806213  mov     [r11-80h], rax
0x140806217  lea     r8d, [r14+3]; peContextMode
0x14080621b  lea     rax, [rbp+57h+var_38]
0x14080621f  mov     [rsp+0B0h+plsnUndoNext], rax; plsnUndoNext
0x140806224  lea     rdx, [rbp+57h+plsnFirst]; plsnFirst
0x140806228  lea     rax, [rbp+57h+arg_0]
0x14080622c  mov     [rsp+0B0h+peRecordType], rax; peRecordType
0x140806231  lea     rax, [rbp+57h+pcbBuffer]
0x140806235  mov     [rsp+0B0h+pcbReadBuffer], rax; pcbReadBuffer
0x14080623a  call    cs:__imp_ClfsReadLogRecord
0x140806241  nop     dword ptr [rax+rax+00h]
0x140806246  jmp     loc_14080635E
0x14080624b  test    [rbp+57h+arg_0], 1
0x14080624f  jz      loc_140806317
0x140806255  cmp     [rbp+57h+pcbBuffer], 30h ; '0'
0x140806259  jb      loc_140806366
0x14080625f  mov     r8, [rbp+57h+ppvReadBuffer]
0x140806263  lea     rax, [rbp+57h+var_48]
0x140806267  add     r8, 10h
0x14080626b  mov     [rsp+0B0h+pcbReadBuffer], rax
0x140806270  mov     rdx, r14
0x140806273  xor     r9d, r9d
0x140806276  mov     rcx, rsi
0x140806279  call    CmpTransSearchAddTransFromRm
0x14080627e  test    eax, eax
0x140806280  js      loc_140806317
0x140806286  mov     rbx, [rbp+57h+ppvReadBuffer]
0x14080628a  mov     edx, [rbp+57h+pcbBuffer]
0x14080628d  mov     [rbp+57h+var_50], rbx
0x140806291  mov     [rbp+57h+arg_18], edx
0x140806294  cmp     [rbx+0Ch], r14d
0x140806298  jge     short loc_1408062C5
0x14080629a  mov     rcx, [rbp+57h+pvReadContext]
0x14080629e  lea     rax, [rbp+57h+arg_18]
0x1408062a2  mov     r8d, edx
0x1408062a5  mov     [rsp+0B0h+pcbReadBuffer], rax
0x1408062aa  mov     rdx, rbx
0x1408062ad  lea     r9, [rbp+57h+var_50]
0x1408062b1  call    CmpDoReadTxRBigLogRecord
0x1408062b6  test    eax, eax
0x1408062b8  js      loc_140806366
0x1408062be  mov     rbx, [rbp+57h+var_50]
0x1408062c2  mov     edx, [rbp+57h+arg_18]
0x1408062c5  mov     rcx, rbx
0x1408062c8  call    CmpVerifyLogRecord
0x1408062cd  mov     rdi, [rbp+57h+var_48]
0x1408062d1  test    eax, eax
0x1408062d3  jns     short loc_1408062EA
0x1408062d5  cmp     byte ptr cs:KdDebuggerEnabled, r14b
0x1408062dc  jz      short loc_140806301
0x1408062de  cmp     byte ptr cs:KdDebuggerNotPresent, r14b
0x1408062e5  jnz     short loc_140806301
0x1408062e7  int     3; Trap to Debugger
0x1408062e8  jmp     short loc_140806301
0x1408062ea  mov     rcx, rbx
0x1408062ed  call    CmpRealignLogBuffers
0x1408062f2  mov     rdx, rbx
0x1408062f5  mov     rcx, rdi
0x1408062f8  call    CmpDoReDoRecord
0x1408062fd  test    eax, eax
0x1408062ff  jns     short loc_140806305
0x140806301  or      dword ptr [rdi+30h], 2
0x140806305  mov     rax, [rbp+57h+ppvReadBuffer]
0x140806309  cmp     [rax+0Ch], r14d
0x14080630d  jge     short loc_140806317
0x14080630f  mov     rcx, rbx; Privileges
0x140806312  call    CmSiFreeMemory
0x140806317  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x14080631b  lea     rax, [rbp+57h+plsnRecord]
0x14080631f  mov     [rsp+38h], rax; plsnRecord
0x140806324  lea     r9, [rbp+57h+arg_0]; peRecordType
0x140806328  lea     rax, [rbp+57h+plsnPrevious]
0x14080632c  mov     [rbp+57h+arg_0], 1
0x140806330  mov     [rsp+0B0h+plsnUndoNext], rax; plsnPrevious
0x140806335  lea     r8, [rbp+57h+pcbBuffer]; pcbBuffer
0x140806339  lea     rax, [rbp+57h+var_38]
0x14080633d  mov     [rsp+0B0h+peRecordType], rax; plsnUndoNext
0x140806342  lea     rdx, [rbp+57h+ppvReadBuffer]; ppvBuffer
0x140806346  mov     [rsp+0B0h+pcbReadBuffer], r14; plsnUser
0x14080634b  call    cs:__imp_ClfsReadNextLogRecord
0x140806352  nop     dword ptr [rax+rax+00h]
0x140806357  cmp     eax, 0C0000011h
0x14080635c  jz      short loc_140806366
0x14080635e  test    eax, eax
0x140806360  jns     loc_14080624B
0x140806366  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x14080636a  test    rcx, rcx
0x14080636d  jz      short loc_14080637B
0x14080636f  call    cs:__imp_ClfsTerminateReadLog
0x140806376  nop     dword ptr [rax+rax+00h]
0x14080637b  add     rsp, 90h
0x140806382  pop     r14
0x140806384  pop     rdi
0x140806385  pop     rsi
0x140806386  pop     rbx
0x140806387  pop     rbp
0x140806388  retn
```
