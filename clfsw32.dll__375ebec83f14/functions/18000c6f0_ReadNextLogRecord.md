# ReadNextLogRecord

- ea: `0x18000c6f0`
- end: `0x18000c8f6`
- name: `ReadNextLogRecord`
- size: `518`
- prototype: `BOOL __stdcall(PVOID pvReadContext, PVOID *ppvBuffer, PULONG pcbBuffer, PCLFS_RECORD_TYPE peRecordType, PCLFS_LSN plsnUser, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, PCLFS_LSN plsnRecord, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c6f0`
- `0x1800124f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015573`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015573`

## pseudocode

```c
BOOL __stdcall ReadNextLogRecord(
        PVOID pvReadContext,
        PVOID *ppvBuffer,
        PULONG pcbBuffer,
        PCLFS_RECORD_TYPE peRecordType,
        PCLFS_LSN plsnUser,
        PCLFS_LSN plsnUndoNext,
        PCLFS_LSN plsnPrevious,
        PCLFS_LSN plsnRecord,
        LPOVERLAPPED pOverlapped)
{
  PCLFS_LSN v13; // rdi
  PCLFS_LSN v14; // rsi
  PCLFS_LSN v15; // r15
  CLS_RECORD_TYPE v16; // cl
  unsigned __int8 v17; // r8
  CClfsMarshallingContext *v18; // rcx
  DWORD v19; // ebx
  struct _CLFS_RECORD_HEADER *v20; // rdx
  struct _CLFS_RECORD_HEADER *v22; // [rsp+70h] [rbp+8h] BYREF

  v22 = 0;
  if ( !pvReadContext )
    goto LABEL_28;
  if ( !ppvBuffer )
    goto LABEL_28;
  if ( !peRecordType )
    goto LABEL_28;
  v13 = plsnUndoNext;
  if ( !plsnUndoNext )
    goto LABEL_28;
  v14 = plsnPrevious;
  if ( !plsnPrevious )
    goto LABEL_28;
  v15 = plsnRecord;
  if ( !plsnRecord )
    goto LABEL_28;
  if ( !pcbBuffer )
    goto LABEL_28;
  *ppvBuffer = 0;
  *pcbBuffer = 0;
  *v13 = CLFS_LSN_NULL;
  *v14 = CLFS_LSN_NULL;
  *v15 = CLFS_LSN_NULL;
  if ( plsnUser )
  {
    if ( CLFS_LSN_INVALID.ullOffset == plsnUser->ullOffset )
      goto LABEL_28;
  }
  v16 = *peRecordType;
  if ( !*peRecordType )
  {
    v16 = 1;
    goto LABEL_13;
  }
  if ( v16 != (v16 & 0x3F) )
  {
LABEL_28:
    SetLastError(0x57u);
    return 0;
  }
LABEL_13:
  v17 = v16 & 3;
  if ( (v16 & 3) == 0
    || *((_DWORD *)pvReadContext + 4) != -1040322545
    || *((_DWORD *)pvReadContext + 5) != 224
    || (*((_BYTE *)pvReadContext + 28) & 0x14) == 0
    || plsnUser && (*((_BYTE *)pvReadContext + 28) & 0x10) != 0
    || plsnUser && (unsigned int)(*((_DWORD *)pvReadContext + 32) - 1) > 1 )
  {
    goto LABEL_28;
  }
  v18 = (CClfsMarshallingContext *)*((_QWORD *)pvReadContext + 24);
  if ( v18 )
  {
    v19 = CClfsMarshallingContext::ReadNextLogRecord(v18, (char *)pvReadContext, v17, plsnUser, &v22, pOverlapped);
    if ( !v19 )
    {
      v20 = v22;
      if ( v22 )
      {
        *peRecordType = *((_BYTE *)v22 + 36) & 3;
        *v15 = *(PCLFS_LSN)v20;
        *v13 = *(CLFS_LSN *)((char *)v20 + 8);
        *v14 = *(CLFS_LSN *)((char *)v20 + 16);
        *pcbBuffer = *((_DWORD *)v20 + 6) - *((unsigned __int16 *)v20 + 17);
        *ppvBuffer = (char *)v20 + *((unsigned __int16 *)v20 + 17);
      }
      else
      {
        v19 = 1168;
      }
    }
  }
  else
  {
    v19 = 87;
  }
  SetLastError(v19);
  return v19 == 0;
}

```

## disassembly

```asm
0x18000c6f0  mov     [rsp+arg_8], rbx
0x18000c6f5  mov     [rsp+arg_10], rsi
0x18000c6fa  push    rdi
0x18000c6fb  push    r12
0x18000c6fd  push    r13
0x18000c6ff  push    r14
0x18000c701  push    r15
0x18000c703  sub     rsp, 40h
0x18000c707  mov     r14, r9
0x18000c70a  mov     r13, r8
0x18000c70d  mov     r12, rdx
0x18000c710  mov     rdx, rcx; void *
0x18000c713  mov     [rsp+68h+arg_0], 0
0x18000c71c  test    rcx, rcx
0x18000c71f  jz      loc_18000C8C8
0x18000c725  test    r12, r12
0x18000c728  jz      loc_18000C8C8
0x18000c72e  test    r9, r9
0x18000c731  jz      loc_18000C8C8
0x18000c737  mov     rdi, [rsp+68h+plsnUndoNext]
0x18000c73f  test    rdi, rdi
0x18000c742  jz      loc_18000C8C8
0x18000c748  mov     rsi, [rsp+68h+plsnPrevious]
0x18000c750  test    rsi, rsi
0x18000c753  jz      loc_18000C8C8
0x18000c759  mov     r15, [rsp+68h+plsnRecord]
0x18000c761  test    r15, r15
0x18000c764  jz      loc_18000C8C8
0x18000c76a  test    r8, r8
0x18000c76d  jz      loc_18000C8C8
0x18000c773  mov     qword ptr [r12], 0
0x18000c77b  mov     dword ptr [r8], 0
0x18000c782  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000c789  mov     [rdi], rax
0x18000c78c  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000c793  mov     [rsi], rax
0x18000c796  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000c79d  mov     [r15], rax
0x18000c7a0  mov     r9, [rsp+68h+plsnUser]; union _CLS_LSN *
0x18000c7a8  test    r9, r9
0x18000c7ab  jz      short loc_18000C7BD
0x18000c7ad  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000c7b4  cmp     rax, [r9]
0x18000c7b7  jz      loc_18000C8C8
0x18000c7bd  mov     cl, [r14]
0x18000c7c0  test    cl, cl
0x18000c7c2  jnz     short loc_18000C7C8
0x18000c7c4  mov     cl, 1
0x18000c7c6  jmp     short loc_18000C7D4
0x18000c7c8  mov     al, cl
0x18000c7ca  and     al, 3Fh
0x18000c7cc  cmp     cl, al
0x18000c7ce  jnz     loc_18000C8C8
0x18000c7d4  and     cl, 3
0x18000c7d7  mov     r8b, cl; unsigned __int8
0x18000c7da  jz      loc_18000C8C8
0x18000c7e0  cmp     dword ptr [rdx+10h], 0C1FDF00Fh
0x18000c7e7  jnz     loc_18000C8C8
0x18000c7ed  cmp     dword ptr [rdx+14h], 0E0h
0x18000c7f4  jnz     loc_18000C8C8
0x18000c7fa  test    byte ptr [rdx+1Ch], 14h
0x18000c7fe  jz      loc_18000C8C8
0x18000c804  test    r9, r9
0x18000c807  jz      short loc_18000C813
0x18000c809  test    byte ptr [rdx+1Ch], 10h
0x18000c80d  jnz     loc_18000C8C8
0x18000c813  mov     [rsp+68h+var_38], 0
0x18000c81b  test    r9, r9
0x18000c81e  jz      short loc_18000C831
0x18000c820  mov     eax, [rdx+80h]
0x18000c826  dec     eax
0x18000c828  cmp     eax, 1
0x18000c82b  ja      loc_18000C8C8
0x18000c831  mov     rcx, [rdx+0C0h]; this
0x18000c838  test    rcx, rcx
0x18000c83b  jnz     short loc_18000C846
0x18000c83d  lea     ebx, [rcx+57h]
0x18000c840  mov     [rsp+68h+var_38], ebx
0x18000c844  jmp     short loc_18000C8B1
0x18000c846  mov     rax, [rsp+68h+pOverlapped]
0x18000c84e  mov     [rsp+68h+var_40], rax; struct _OVERLAPPED *
0x18000c853  lea     rax, [rsp+68h+arg_0]
0x18000c858  mov     [rsp+68h+var_48], rax; struct _CLFS_RECORD_HEADER **
0x18000c85d  call    ?ReadNextLogRecord@CClfsMarshallingContext@@QEAAKQEAXEQEAT_CLS_LSN@@AEAPEAU_CLFS_RECORD_HEADER@@PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReadNextLogRecord(void * const,uchar,_CLS_LSN * const,_CLFS_RECORD_HEADER * &,_OVERLAPPED *)
0x18000c862  mov     ebx, eax
0x18000c864  mov     [rsp+68h+var_38], eax
0x18000c868  test    eax, eax
0x18000c86a  jnz     short loc_18000C8B1
0x18000c86c  mov     rdx, [rsp+68h+arg_0]
0x18000c871  test    rdx, rdx
0x18000c874  jnz     short loc_18000C87D
0x18000c876  mov     ebx, 490h
0x18000c87b  jmp     short loc_18000C840
0x18000c87d  mov     al, [rdx+24h]
0x18000c880  and     al, 3
0x18000c882  mov     [r14], al
0x18000c885  mov     rax, [rdx]
0x18000c888  mov     [r15], rax
0x18000c88b  mov     rax, [rdx+8]
0x18000c88f  mov     [rdi], rax
0x18000c892  mov     rax, [rdx+10h]
0x18000c896  mov     [rsi], rax
0x18000c899  movzx   eax, word ptr [rdx+22h]
0x18000c89d  mov     ecx, [rdx+18h]
0x18000c8a0  sub     ecx, eax
0x18000c8a2  mov     [r13+0], ecx
0x18000c8a6  movzx   eax, word ptr [rdx+22h]
0x18000c8aa  add     rax, rdx
0x18000c8ad  mov     [r12], rax
0x18000c8b1  mov     ecx, ebx; dwErrCode
0x18000c8b3  call    cs:__imp_SetLastError
0x18000c8ba  nop     dword ptr [rax+rax+00h]
0x18000c8bf  xor     eax, eax
0x18000c8c1  test    ebx, ebx
0x18000c8c3  setz    al
0x18000c8c6  jmp     short loc_18000C8DB
0x18000c8c8  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c8cd  call    cs:__imp_SetLastError
0x18000c8d4  nop     dword ptr [rax+rax+00h]
0x18000c8d9  xor     eax, eax
0x18000c8db  lea     r11, [rsp+68h+var_28]
0x18000c8e0  mov     rbx, [r11+38h]
0x18000c8e4  mov     rsi, [r11+40h]
0x18000c8e8  mov     rsp, r11
0x18000c8eb  pop     r15
0x18000c8ed  pop     r14
0x18000c8ef  pop     r13
0x18000c8f1  pop     r12
0x18000c8f3  pop     rdi
0x18000c8f4  retn
0x180015567  push    rbp
0x180015569  sub     rsp, 30h
0x18001556d  mov     rbp, rdx
0x180015570  mov     ecx, [rbp+30h]; dwErrCode
0x180015573  call    cs:__imp_SetLastError
0x18001557a  nop     dword ptr [rax+rax+00h]
0x18001557f  nop
0x180015580  add     rsp, 30h
0x180015584  pop     rbp
0x180015585  retn
```
