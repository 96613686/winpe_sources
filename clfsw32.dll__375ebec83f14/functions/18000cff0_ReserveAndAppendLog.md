# ReserveAndAppendLog

- ea: `0x18000cff0`
- end: `0x18000d167`
- name: `ReserveAndAppendLog`
- size: `375`
- prototype: `BOOL __stdcall(PVOID pvMarshal, PCLFS_WRITE_ENTRY rgWriteEntries, ULONG cWriteEntries, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, ULONG cReserveRecords, LONGLONG rgcbReservation[], ULONG fFlags, PCLFS_LSN plsn, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cff0`
- `0x180013178`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d12c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d146`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d12c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d146`

## pseudocode

```c
BOOL __stdcall ReserveAndAppendLog(
        PVOID pvMarshal,
        PCLFS_WRITE_ENTRY rgWriteEntries,
        ULONG cWriteEntries,
        PCLFS_LSN plsnUndoNext,
        PCLFS_LSN plsnPrevious,
        ULONG cReserveRecords,
        LONGLONG rgcbReservation[],
        ULONG fFlags,
        PCLFS_LSN plsn,
        LPOVERLAPPED pOverlapped)
{
  char v11; // cl
  PCLFS_LSN v12; // rbx
  DWORD v13; // ecx
  DWORD appended; // edi
  union _CLS_LSN v16; // [rsp+60h] [rbp-18h] BYREF
  union _CLS_LSN v17; // [rsp+68h] [rbp-10h] BYREF
  union _CLS_LSN v18; // [rsp+80h] [rbp+8h] BYREF

  v17 = CLFS_LSN_NULL;
  v16 = CLFS_LSN_INVALID;
  v18 = CLFS_LSN_INVALID;
  if ( !pvMarshal )
    goto LABEL_20;
  v11 = fFlags;
  if ( fFlags != (fFlags & 7) )
    goto LABEL_20;
  if ( plsnUndoNext )
    v16 = *plsnUndoNext;
  if ( plsnPrevious )
    v18 = *plsnPrevious;
  v12 = plsn;
  if ( plsn )
    *plsn = CLFS_LSN_NULL;
  if ( cWriteEntries && !rgWriteEntries )
  {
    v13 = 1784;
LABEL_21:
    SetLastError(v13);
    return 0;
  }
  if ( cReserveRecords && (!rgcbReservation || (v11 & 4) != 0)
    || *(_DWORD *)pvMarshal != -1040322550
    || *((_DWORD *)pvMarshal + 1) != 368 )
  {
LABEL_20:
    v13 = 87;
    goto LABEL_21;
  }
  appended = CClfsMarshallingContext::ReserveAndAppendLog(
               (CClfsMarshallingContext *)pvMarshal,
               rgWriteEntries,
               cWriteEntries,
               1,
               cReserveRecords,
               rgcbReservation,
               &v16,
               &v18,
               v11,
               &v17,
               pOverlapped);
  if ( v12 )
    *v12 = v17;
  SetLastError(appended);
  return appended == 0;
}

```

## disassembly

```asm
0x18000cff0  mov     [rsp+arg_8], rbx
0x18000cff5  mov     [rsp+arg_10], rsi
0x18000cffa  push    rdi
0x18000cffb  sub     rsp, 70h
0x18000cfff  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000d006  mov     edi, r8d
0x18000d009  mov     r10, qword ptr cs:CLFS_LSN_NULL
0x18000d010  mov     rsi, rdx
0x18000d013  mov     qword ptr [rsp+78h+var_10], r10
0x18000d018  mov     r11, rcx
0x18000d01b  mov     qword ptr [rsp+78h+var_18], rax
0x18000d020  mov     qword ptr [rsp+78h+arg_0], rax
0x18000d028  test    rcx, rcx
0x18000d02b  jz      loc_18000D141
0x18000d031  mov     ecx, [rsp+78h+fFlags]
0x18000d038  mov     eax, ecx
0x18000d03a  and     eax, 7
0x18000d03d  cmp     ecx, eax
0x18000d03f  jnz     loc_18000D141
0x18000d045  test    r9, r9
0x18000d048  jz      short loc_18000D052
0x18000d04a  mov     rax, [r9]
0x18000d04d  mov     qword ptr [rsp+78h+var_18], rax
0x18000d052  mov     rax, [rsp+78h+plsnPrevious]
0x18000d05a  test    rax, rax
0x18000d05d  jz      short loc_18000D06A
0x18000d05f  mov     rax, [rax]
0x18000d062  mov     qword ptr [rsp+78h+arg_0], rax
0x18000d06a  mov     rbx, [rsp+78h+plsn]
0x18000d072  test    rbx, rbx
0x18000d075  jz      short loc_18000D07A
0x18000d077  mov     [rbx], r10
0x18000d07a  test    edi, edi
0x18000d07c  jz      short loc_18000D08D
0x18000d07e  test    rsi, rsi
0x18000d081  jnz     short loc_18000D08D
0x18000d083  mov     ecx, 6F8h
0x18000d088  jmp     loc_18000D146
0x18000d08d  mov     r8d, [rsp+78h+cReserveRecords]
0x18000d095  mov     rdx, [rsp+78h+rgcbReservation]
0x18000d09d  test    r8d, r8d
0x18000d0a0  jz      short loc_18000D0B4
0x18000d0a2  test    rdx, rdx
0x18000d0a5  jz      loc_18000D141
0x18000d0ab  test    cl, 4
0x18000d0ae  jnz     loc_18000D141
0x18000d0b4  cmp     dword ptr [r11], 0C1FDF00Ah
0x18000d0bb  jnz     loc_18000D141
0x18000d0c1  cmp     dword ptr [r11+4], 170h
0x18000d0c9  jnz     short loc_18000D141
0x18000d0cb  mov     rax, [rsp+78h+pOverlapped]
0x18000d0d3  mov     r9d, 1; unsigned int
0x18000d0d9  mov     [rsp+78h+var_28], rax; struct _OVERLAPPED *
0x18000d0de  lea     rax, [rsp+78h+var_10]
0x18000d0e3  mov     [rsp+78h+var_30], rax; union _CLS_LSN *
0x18000d0e8  lea     rax, [rsp+78h+arg_0]
0x18000d0f0  mov     dword ptr [rsp+78h+var_38], ecx; char
0x18000d0f4  mov     rcx, r11; this
0x18000d0f7  mov     [rsp+78h+var_40], rax; union _CLS_LSN *
0x18000d0fc  lea     rax, [rsp+78h+var_18]
0x18000d101  mov     [rsp+78h+var_48], rax; union _CLS_LSN *
0x18000d106  mov     [rsp+78h+var_50], rdx; __int64 *
0x18000d10b  mov     rdx, rsi; struct _CLS_WRITE_ENTRY *
0x18000d10e  mov     [rsp+78h+var_58], r8d; unsigned int
0x18000d113  mov     r8d, edi; unsigned int
0x18000d116  call    ?ReserveAndAppendLog@CClfsMarshallingContext@@QEAAKPEAU_CLS_WRITE_ENTRY@@KKKQEA_JAEBT_CLS_LSN@@2KAEAT3@PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReserveAndAppendLog(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,_CLS_LSN const &,_CLS_LSN const &,ulong,_CLS_LSN &,_OVERLAPPED *)
0x18000d11b  mov     edi, eax
0x18000d11d  test    rbx, rbx
0x18000d120  jz      short loc_18000D12A
0x18000d122  mov     rax, qword ptr [rsp+78h+var_10]
0x18000d127  mov     [rbx], rax
0x18000d12a  mov     ecx, edi; dwErrCode
0x18000d12c  call    cs:__imp_SetLastError
0x18000d133  nop     dword ptr [rax+rax+00h]
0x18000d138  xor     eax, eax
0x18000d13a  test    edi, edi
0x18000d13c  setz    al
0x18000d13f  jmp     short loc_18000D154
0x18000d141  mov     ecx, 57h ; 'W'; dwErrCode
0x18000d146  call    cs:__imp_SetLastError
0x18000d14d  nop     dword ptr [rax+rax+00h]
0x18000d152  xor     eax, eax
0x18000d154  lea     r11, [rsp+78h+var_8]
0x18000d159  mov     rbx, [r11+18h]
0x18000d15d  mov     rsi, [r11+20h]
0x18000d161  mov     rsp, r11
0x18000d164  pop     rdi
0x18000d165  retn
```
