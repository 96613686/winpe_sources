# ReserveAndAppendLogAligned

- ea: `0x18000d170`
- end: `0x18000d2f1`
- name: `ReserveAndAppendLogAligned`
- size: `385`
- prototype: `BOOL __stdcall(PVOID pvMarshal, PCLFS_WRITE_ENTRY rgWriteEntries, ULONG cWriteEntries, ULONG cbEntryAlignment, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, ULONG cReserveRecords, LONGLONG rgcbReservation[], ULONG fFlags, PCLFS_LSN plsn, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d170`
- `0x180013178`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2d0`

## pseudocode

```c
BOOL __stdcall ReserveAndAppendLogAligned(
        PVOID pvMarshal,
        PCLFS_WRITE_ENTRY rgWriteEntries,
        ULONG cWriteEntries,
        ULONG cbEntryAlignment,
        PCLFS_LSN plsnUndoNext,
        PCLFS_LSN plsnPrevious,
        ULONG cReserveRecords,
        LONGLONG rgcbReservation[],
        ULONG fFlags,
        PCLFS_LSN plsn,
        LPOVERLAPPED pOverlapped)
{
  char v12; // r9
  PCLFS_LSN v13; // rbx
  DWORD v14; // ecx
  DWORD appended; // eax
  BOOL v16; // ebx
  union _CLS_LSN v18; // [rsp+60h] [rbp-18h] BYREF
  union _CLS_LSN v19; // [rsp+68h] [rbp-10h] BYREF
  union _CLS_LSN v20; // [rsp+80h] [rbp+8h] BYREF

  v19 = CLFS_LSN_NULL;
  v18 = CLFS_LSN_INVALID;
  v20 = CLFS_LSN_INVALID;
  if ( !pvMarshal )
    goto LABEL_21;
  v12 = fFlags;
  if ( fFlags != (fFlags & 7) || !cbEntryAlignment )
    goto LABEL_21;
  if ( plsnUndoNext )
    v18 = *plsnUndoNext;
  if ( plsnPrevious )
    v20 = *plsnPrevious;
  v13 = plsn;
  if ( plsn )
    *plsn = CLFS_LSN_NULL;
  if ( cWriteEntries && !rgWriteEntries )
  {
    v14 = 1784;
LABEL_22:
    SetLastError(v14);
    return 0;
  }
  if ( cReserveRecords && (!rgcbReservation || (v12 & 4) != 0)
    || *(_DWORD *)pvMarshal != -1040322550
    || *((_DWORD *)pvMarshal + 1) != 368 )
  {
LABEL_21:
    v14 = 87;
    goto LABEL_22;
  }
  appended = CClfsMarshallingContext::ReserveAndAppendLog(
               (CClfsMarshallingContext *)pvMarshal,
               rgWriteEntries,
               cWriteEntries,
               cbEntryAlignment,
               cReserveRecords,
               rgcbReservation,
               &v18,
               &v20,
               v12,
               &v19,
               pOverlapped);
  if ( v13 )
    *v13 = v19;
  v16 = appended == 0;
  SetLastError(appended);
  return v16;
}

```

## disassembly

```asm
0x18000d170  mov     [rsp+arg_8], rbx
0x18000d175  mov     [rsp+arg_10], rsi
0x18000d17a  push    rdi
0x18000d17b  sub     rsp, 70h
0x18000d17f  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000d186  mov     r11d, r9d
0x18000d189  mov     r10, qword ptr cs:CLFS_LSN_NULL
0x18000d190  mov     edi, r8d
0x18000d193  mov     qword ptr [rsp+78h+var_10], r10
0x18000d198  mov     rsi, rdx
0x18000d19b  mov     qword ptr [rsp+78h+var_18], rax
0x18000d1a0  mov     qword ptr [rsp+78h+arg_0], rax
0x18000d1a8  test    rcx, rcx
0x18000d1ab  jz      loc_18000D2CB
0x18000d1b1  mov     r9d, [rsp+78h+fFlags]
0x18000d1b9  mov     eax, r9d
0x18000d1bc  and     eax, 7
0x18000d1bf  cmp     r9d, eax
0x18000d1c2  jnz     loc_18000D2CB
0x18000d1c8  test    r11d, r11d
0x18000d1cb  jz      loc_18000D2CB
0x18000d1d1  mov     rax, [rsp+78h+plsnUndoNext]
0x18000d1d9  test    rax, rax
0x18000d1dc  jz      short loc_18000D1E6
0x18000d1de  mov     rax, [rax]
0x18000d1e1  mov     qword ptr [rsp+78h+var_18], rax
0x18000d1e6  mov     rax, [rsp+78h+plsnPrevious]
0x18000d1ee  test    rax, rax
0x18000d1f1  jz      short loc_18000D1FE
0x18000d1f3  mov     rax, [rax]
0x18000d1f6  mov     qword ptr [rsp+78h+arg_0], rax
0x18000d1fe  mov     rbx, [rsp+78h+plsn]
0x18000d206  test    rbx, rbx
0x18000d209  jz      short loc_18000D20E
0x18000d20b  mov     [rbx], r10
0x18000d20e  test    edi, edi
0x18000d210  jz      short loc_18000D221
0x18000d212  test    rsi, rsi
0x18000d215  jnz     short loc_18000D221
0x18000d217  mov     ecx, 6F8h; this
0x18000d21c  jmp     loc_18000D2D0
0x18000d221  mov     r8d, [rsp+78h+cReserveRecords]
0x18000d229  mov     rdx, [rsp+78h+rgcbReservation]
0x18000d231  test    r8d, r8d
0x18000d234  jz      short loc_18000D249
0x18000d236  test    rdx, rdx
0x18000d239  jz      loc_18000D2CB
0x18000d23f  test    r9b, 4
0x18000d243  jnz     loc_18000D2CB
0x18000d249  cmp     dword ptr [rcx], 0C1FDF00Ah
0x18000d24f  jnz     short loc_18000D2CB
0x18000d251  cmp     dword ptr [rcx+4], 170h
0x18000d258  jnz     short loc_18000D2CB
0x18000d25a  mov     rax, [rsp+78h+pOverlapped]
0x18000d262  mov     [rsp+78h+var_28], rax; struct _OVERLAPPED *
0x18000d267  lea     rax, [rsp+78h+var_10]
0x18000d26c  mov     [rsp+78h+var_30], rax; union _CLS_LSN *
0x18000d271  lea     rax, [rsp+78h+arg_0]
0x18000d279  mov     dword ptr [rsp+78h+var_38], r9d; char
0x18000d27e  mov     r9d, r11d; unsigned int
0x18000d281  mov     [rsp+78h+var_40], rax; union _CLS_LSN *
0x18000d286  lea     rax, [rsp+78h+var_18]
0x18000d28b  mov     [rsp+78h+var_48], rax; union _CLS_LSN *
0x18000d290  mov     [rsp+78h+var_50], rdx; __int64 *
0x18000d295  mov     rdx, rsi; struct _CLS_WRITE_ENTRY *
0x18000d298  mov     [rsp+78h+var_58], r8d; unsigned int
0x18000d29d  mov     r8d, edi; unsigned int
0x18000d2a0  call    ?ReserveAndAppendLog@CClfsMarshallingContext@@QEAAKPEAU_CLS_WRITE_ENTRY@@KKKQEA_JAEBT_CLS_LSN@@2KAEAT3@PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReserveAndAppendLog(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,_CLS_LSN const &,_CLS_LSN const &,ulong,_CLS_LSN &,_OVERLAPPED *)
0x18000d2a5  test    rbx, rbx
0x18000d2a8  jz      short loc_18000D2B2
0x18000d2aa  mov     rcx, qword ptr [rsp+78h+var_10]
0x18000d2af  mov     [rbx], rcx
0x18000d2b2  xor     ebx, ebx
0x18000d2b4  mov     ecx, eax; dwErrCode
0x18000d2b6  test    eax, eax
0x18000d2b8  setz    bl
0x18000d2bb  call    cs:__imp_SetLastError
0x18000d2c2  nop     dword ptr [rax+rax+00h]
0x18000d2c7  mov     eax, ebx
0x18000d2c9  jmp     short loc_18000D2DE
0x18000d2cb  mov     ecx, 57h ; 'W'; dwErrCode
0x18000d2d0  call    cs:__imp_SetLastError
0x18000d2d7  nop     dword ptr [rax+rax+00h]
0x18000d2dc  xor     eax, eax
0x18000d2de  lea     r11, [rsp+78h+var_8]
0x18000d2e3  mov     rbx, [r11+18h]
0x18000d2e7  mov     rsi, [r11+20h]
0x18000d2eb  mov     rsp, r11
0x18000d2ee  pop     rdi
0x18000d2ef  retn
```
