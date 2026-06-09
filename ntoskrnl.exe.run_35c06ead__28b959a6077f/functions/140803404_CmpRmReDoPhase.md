# CmpRmReDoPhase

- ea: `0x140803404`
- end: `0x1408035da`
- name: `CmpRmReDoPhase`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1408b0708`

## callees

- `0x140456940`
- `0x140802f94`
- `0x1408030f8`
- `0x140803404`
- `0x140803798`
- `0x140806b20`
- `0x1408872d8`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x14080359b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x14080359b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408035bf`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408035bf`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x14080348a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x14080348a`

## pseudocode

```c
int __fastcall CmpRmReDoPhase(__int64 a1, CLFS_LSN a2)
{
  _QWORD *v2; // rax
  int v3; // esi
  struct _PRIVILEGE_SET *v4; // rbx
  int v5; // eax
  __int64 v6; // rdi
  PVOID ppvReadBuffer; // [rsp+58h] [rbp-9h] BYREF
  PVOID pvReadContext; // [rsp+60h] [rbp-1h] BYREF
  struct _PRIVILEGE_SET *v10; // [rsp+68h] [rbp+7h] BYREF
  __int64 v11; // [rsp+70h] [rbp+Fh] BYREF
  CLFS_LSN plsnPrevious; // [rsp+78h] [rbp+17h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+80h] [rbp+1Fh] BYREF
  CLFS_LSN plsnRecord; // [rsp+88h] [rbp+27h] BYREF
  CLS_RECORD_TYPE peRecordType; // [rsp+C8h] [rbp+67h] BYREF
  CLFS_LSN plsnFirst; // [rsp+D0h] [rbp+6Fh] BYREF
  ULONG pcbBuffer; // [rsp+D8h] [rbp+77h] BYREF
  ULONG v18; // [rsp+E0h] [rbp+7Fh] BYREF

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
  v11 = 0;
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
    if ( (int)CmpTransSearchAddTransFromRm(v3, 0, (int)ppvReadBuffer + 16, 0, (__int64)&v11) < 0 )
      goto LABEL_17;
    v4 = (struct _PRIVILEGE_SET *)ppvReadBuffer;
    v10 = (struct _PRIVILEGE_SET *)ppvReadBuffer;
    v18 = pcbBuffer;
    if ( *((int *)ppvReadBuffer + 3) < 0 )
    {
      LODWORD(v2) = CmpDoReadTxRBigLogRecord(
                      (_DWORD)pvReadContext,
                      (_DWORD)ppvReadBuffer,
                      pcbBuffer,
                      (unsigned int)&v10,
                      (__int64)&v18);
      if ( (int)v2 < 0 )
        break;
      v4 = v10;
    }
    v5 = CmpVerifyLogRecord(v4);
    v6 = v11;
    if ( v5 >= 0 )
    {
      CmpRealignLogBuffers(v4);
      if ( (int)CmpDoReDoRecord(v6, v4) >= 0 )
        goto LABEL_15;
    }
    else if ( (_BYTE)KdDebuggerEnabled && !(_BYTE)KdDebuggerNotPresent )
    {
      __debugbreak();
    }
    *(_DWORD *)(v6 + 48) |= 2u;
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
0x140803404  mov     r11, rsp
0x140803407  mov     [r11+10h], rdx
0x14080340b  push    rbp
0x14080340c  push    rbx
0x14080340d  push    rsi
0x14080340e  push    rdi
0x14080340f  push    r14
0x140803411  lea     rbp, [r11-5Fh]
0x140803415  sub     rsp, 90h
0x14080341c  xor     r14d, r14d
0x14080341f  lea     rax, [rcx+10h]
0x140803423  mov     rsi, rcx
0x140803426  mov     [rbp+57h+pvReadContext], r14
0x14080342a  mov     [rbp+57h+ppvReadBuffer], r14
0x14080342e  mov     [rbp+57h+pcbBuffer], r14d
0x140803432  mov     qword ptr [rbp+57h+var_38], r14
0x140803436  mov     qword ptr [rbp+57h+plsnPrevious], r14
0x14080343a  mov     qword ptr [rbp+57h+plsnRecord], r14
0x14080343e  mov     [rbp+57h+arg_0], r14b
0x140803442  mov     [rbp+57h+var_48], r14
0x140803446  cmp     [rax], rax
0x140803449  jz      loc_1408035CB
0x14080344f  mov     rcx, [rcx+60h]; pvMarshalContext
0x140803453  lea     rax, [rbp+57h+pvReadContext]
0x140803457  mov     [r11-78h], rax
0x14080345b  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x14080345f  lea     rax, [rbp+57h+plsnPrevious]
0x140803463  mov     [r11-80h], rax
0x140803467  lea     r8d, [r14+3]; peContextMode
0x14080346b  lea     rax, [rbp+57h+var_38]
0x14080346f  mov     [rsp+0B0h+plsnUndoNext], rax; plsnUndoNext
0x140803474  lea     rdx, [rbp+57h+plsnFirst]; plsnFirst
0x140803478  lea     rax, [rbp+57h+arg_0]
0x14080347c  mov     [rsp+0B0h+peRecordType], rax; peRecordType
0x140803481  lea     rax, [rbp+57h+pcbBuffer]
0x140803485  mov     [rsp+0B0h+pcbReadBuffer], rax; pcbReadBuffer
0x14080348a  call    cs:__imp_ClfsReadLogRecord
0x140803491  nop     dword ptr [rax+rax+00h]
0x140803496  jmp     loc_1408035AE
0x14080349b  test    [rbp+57h+arg_0], 1
0x14080349f  jz      loc_140803567
0x1408034a5  cmp     [rbp+57h+pcbBuffer], 30h ; '0'
0x1408034a9  jb      loc_1408035B6
0x1408034af  mov     r8, [rbp+57h+ppvReadBuffer]
0x1408034b3  lea     rax, [rbp+57h+var_48]
0x1408034b7  add     r8, 10h
0x1408034bb  mov     [rsp+0B0h+pcbReadBuffer], rax
0x1408034c0  mov     rdx, r14
0x1408034c3  xor     r9d, r9d
0x1408034c6  mov     rcx, rsi
0x1408034c9  call    CmpTransSearchAddTransFromRm
0x1408034ce  test    eax, eax
0x1408034d0  js      loc_140803567
0x1408034d6  mov     rbx, [rbp+57h+ppvReadBuffer]
0x1408034da  mov     edx, [rbp+57h+pcbBuffer]
0x1408034dd  mov     [rbp+57h+var_50], rbx
0x1408034e1  mov     [rbp+57h+arg_18], edx
0x1408034e4  cmp     [rbx+0Ch], r14d
0x1408034e8  jge     short loc_140803515
0x1408034ea  mov     rcx, [rbp+57h+pvReadContext]
0x1408034ee  lea     rax, [rbp+57h+arg_18]
0x1408034f2  mov     r8d, edx
0x1408034f5  mov     [rsp+0B0h+pcbReadBuffer], rax
0x1408034fa  mov     rdx, rbx
0x1408034fd  lea     r9, [rbp+57h+var_50]
0x140803501  call    CmpDoReadTxRBigLogRecord
0x140803506  test    eax, eax
0x140803508  js      loc_1408035B6
0x14080350e  mov     rbx, [rbp+57h+var_50]
0x140803512  mov     edx, [rbp+57h+arg_18]
0x140803515  mov     rcx, rbx
0x140803518  call    CmpVerifyLogRecord
0x14080351d  mov     rdi, [rbp+57h+var_48]
0x140803521  test    eax, eax
0x140803523  jns     short loc_14080353A
0x140803525  cmp     byte ptr cs:KdDebuggerEnabled, r14b
0x14080352c  jz      short loc_140803551
0x14080352e  cmp     cs:KdDebuggerNotPresent, r14b
0x140803535  jnz     short loc_140803551
0x140803537  int     3; Trap to Debugger
0x140803538  jmp     short loc_140803551
0x14080353a  mov     rcx, rbx
0x14080353d  call    CmpRealignLogBuffers
0x140803542  mov     rdx, rbx
0x140803545  mov     rcx, rdi
0x140803548  call    CmpDoReDoRecord
0x14080354d  test    eax, eax
0x14080354f  jns     short loc_140803555
0x140803551  or      dword ptr [rdi+30h], 2
0x140803555  mov     rax, [rbp+57h+ppvReadBuffer]
0x140803559  cmp     [rax+0Ch], r14d
0x14080355d  jge     short loc_140803567
0x14080355f  mov     rcx, rbx; Privileges
0x140803562  call    CmSiFreeMemory
0x140803567  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x14080356b  lea     rax, [rbp+57h+plsnRecord]
0x14080356f  mov     [rsp+38h], rax; plsnRecord
0x140803574  lea     r9, [rbp+57h+arg_0]; peRecordType
0x140803578  lea     rax, [rbp+57h+plsnPrevious]
0x14080357c  mov     [rbp+57h+arg_0], 1
0x140803580  mov     [rsp+0B0h+plsnUndoNext], rax; plsnPrevious
0x140803585  lea     r8, [rbp+57h+pcbBuffer]; pcbBuffer
0x140803589  lea     rax, [rbp+57h+var_38]
0x14080358d  mov     [rsp+0B0h+peRecordType], rax; plsnUndoNext
0x140803592  lea     rdx, [rbp+57h+ppvReadBuffer]; ppvBuffer
0x140803596  mov     [rsp+0B0h+pcbReadBuffer], r14; plsnUser
0x14080359b  call    cs:__imp_ClfsReadNextLogRecord
0x1408035a2  nop     dword ptr [rax+rax+00h]
0x1408035a7  cmp     eax, 0C0000011h
0x1408035ac  jz      short loc_1408035B6
0x1408035ae  test    eax, eax
0x1408035b0  jns     loc_14080349B
0x1408035b6  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x1408035ba  test    rcx, rcx
0x1408035bd  jz      short loc_1408035CB
0x1408035bf  call    cs:__imp_ClfsTerminateReadLog
0x1408035c6  nop     dword ptr [rax+rax+00h]
0x1408035cb  add     rsp, 90h
0x1408035d2  pop     r14
0x1408035d4  pop     rdi
0x1408035d5  pop     rsi
0x1408035d6  pop     rbx
0x1408035d7  pop     rbp
0x1408035d8  retn
```
