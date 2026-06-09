# ReadLogRecord

- ea: `0x18000c4e0`
- end: `0x18000c637`
- name: `ReadLogRecord`
- size: `343`
- prototype: `BOOL __stdcall(PVOID pvMarshal, PCLFS_LSN plsnFirst, CLFS_CONTEXT_MODE eContextMode, PVOID *ppvReadBuffer, PULONG pcbReadBuffer, PCLFS_RECORD_TYPE peRecordType, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, PVOID *ppvReadContext, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c4e0`
- `0x18001195c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c606`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c61b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c606`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c61b`

## pseudocode

```c
BOOL __stdcall ReadLogRecord(
        PVOID pvMarshal,
        PCLFS_LSN plsnFirst,
        CLFS_CONTEXT_MODE eContextMode,
        PVOID *ppvReadBuffer,
        PULONG pcbReadBuffer,
        PCLFS_RECORD_TYPE peRecordType,
        PCLFS_LSN plsnUndoNext,
        PCLFS_LSN plsnPrevious,
        PVOID *ppvReadContext,
        LPOVERLAPPED pOverlapped)
{
  PCLFS_RECORD_TYPE v12; // rbx
  PCLFS_LSN v13; // rdi
  PCLFS_LSN v14; // rsi
  void **v15; // rdx
  PULONG v16; // r15
  BOOL v17; // ebp
  DWORD v18; // r8d
  struct _CLFS_RECORD_HEADER *v19; // rdx
  struct _CLFS_RECORD_HEADER *v21; // [rsp+70h] [rbp+8h] BYREF

  v21 = 0;
  if ( !pvMarshal )
    goto LABEL_13;
  if ( !ppvReadBuffer )
    goto LABEL_13;
  if ( !plsnFirst )
    goto LABEL_13;
  v12 = peRecordType;
  if ( !peRecordType )
    goto LABEL_13;
  v13 = plsnUndoNext;
  if ( !plsnUndoNext )
    goto LABEL_13;
  v14 = plsnPrevious;
  if ( !plsnPrevious )
    goto LABEL_13;
  v15 = ppvReadContext;
  if ( !ppvReadContext )
    goto LABEL_13;
  v16 = pcbReadBuffer;
  if ( pcbReadBuffer
    && (*plsnUndoNext = CLFS_LSN_NULL,
        *v14 = CLFS_LSN_NULL,
        *v16 = 0,
        *v15 = 0,
        *ppvReadBuffer = 0,
        *v12 = 0,
        *(_QWORD *)pvMarshal == 0x170C1FDF00ALL) )
  {
    v17 = 0;
    v18 = CClfsMarshallingContext::ReadLogRecord(
            (CClfsMarshallingContext *)pvMarshal,
            plsnFirst,
            eContextMode,
            &v21,
            v15,
            pOverlapped);
    if ( !v18 )
    {
      v19 = v21;
      v17 = 1;
      *v12 = *((_BYTE *)v21 + 36) & 3;
      *v13 = *(CLFS_LSN *)((char *)v19 + 8);
      *v14 = *(CLFS_LSN *)((char *)v19 + 16);
      *v16 = *((_DWORD *)v19 + 6) - *((unsigned __int16 *)v19 + 17);
      *ppvReadBuffer = (char *)v19 + *((unsigned __int16 *)v19 + 17);
    }
    SetLastError(v18);
    return v17;
  }
  else
  {
LABEL_13:
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c4e0  mov     r11, rsp
0x18000c4e3  push    rbx
0x18000c4e4  push    rbp
0x18000c4e5  push    rsi
0x18000c4e6  push    rdi
0x18000c4e7  push    r14
0x18000c4e9  push    r15
0x18000c4eb  sub     rsp, 38h
0x18000c4ef  mov     qword ptr [r11+8], 0
0x18000c4f7  mov     r14, r9
0x18000c4fa  mov     r10, rdx
0x18000c4fd  test    rcx, rcx
0x18000c500  jz      loc_18000C616
0x18000c506  test    r9, r9
0x18000c509  jz      loc_18000C616
0x18000c50f  test    rdx, rdx
0x18000c512  jz      loc_18000C616
0x18000c518  mov     rbx, [rsp+68h+peRecordType]
0x18000c520  test    rbx, rbx
0x18000c523  jz      loc_18000C616
0x18000c529  mov     rdi, [rsp+68h+plsnUndoNext]
0x18000c531  test    rdi, rdi
0x18000c534  jz      loc_18000C616
0x18000c53a  mov     rsi, [rsp+68h+plsnPrevious]
0x18000c542  test    rsi, rsi
0x18000c545  jz      loc_18000C616
0x18000c54b  mov     rdx, [rsp+68h+ppvReadContext]
0x18000c553  test    rdx, rdx
0x18000c556  jz      loc_18000C616
0x18000c55c  mov     r15, [rsp+68h+pcbReadBuffer]
0x18000c564  test    r15, r15
0x18000c567  jz      loc_18000C616
0x18000c56d  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000c574  mov     [rdi], rax
0x18000c577  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000c57e  mov     [rsi], rax
0x18000c581  mov     dword ptr [r15], 0
0x18000c588  mov     qword ptr [rdx], 0
0x18000c58f  mov     qword ptr [r9], 0
0x18000c596  mov     byte ptr [rbx], 0
0x18000c599  cmp     dword ptr [rcx], 0C1FDF00Ah
0x18000c59f  jnz     short loc_18000C616
0x18000c5a1  cmp     dword ptr [rcx+4], 170h
0x18000c5a8  jnz     short loc_18000C616
0x18000c5aa  mov     rax, [rsp+68h+pOverlapped]
0x18000c5b2  lea     r9, [r11+8]; struct _CLFS_RECORD_HEADER **
0x18000c5b6  mov     [r11-40h], rax
0x18000c5ba  xor     ebp, ebp
0x18000c5bc  mov     [r11-48h], rdx
0x18000c5c0  mov     rdx, r10; union _CLS_LSN *
0x18000c5c3  call    ?ReadLogRecord@CClfsMarshallingContext@@QEAAKAEBT_CLS_LSN@@W4_CLFS_CONTEXT_MODE@@AEAPEAU_CLFS_RECORD_HEADER@@AEAPEAXPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReadLogRecord(_CLS_LSN const &,_CLFS_CONTEXT_MODE,_CLFS_RECORD_HEADER * &,void * &,_OVERLAPPED *)
0x18000c5c8  mov     r8d, eax
0x18000c5cb  test    eax, eax
0x18000c5cd  jnz     short loc_18000C603
0x18000c5cf  mov     rdx, [rsp+68h+arg_0]
0x18000c5d4  lea     ebp, [r8+1]
0x18000c5d8  mov     al, [rdx+24h]
0x18000c5db  and     al, 3
0x18000c5dd  mov     [rbx], al
0x18000c5df  mov     rax, [rdx+8]
0x18000c5e3  mov     [rdi], rax
0x18000c5e6  mov     rax, [rdx+10h]
0x18000c5ea  mov     [rsi], rax
0x18000c5ed  movzx   eax, word ptr [rdx+22h]
0x18000c5f1  mov     ecx, [rdx+18h]
0x18000c5f4  sub     ecx, eax
0x18000c5f6  mov     [r15], ecx
0x18000c5f9  movzx   eax, word ptr [rdx+22h]
0x18000c5fd  add     rax, rdx
0x18000c600  mov     [r14], rax
0x18000c603  mov     ecx, r8d; dwErrCode
0x18000c606  call    cs:__imp_SetLastError
0x18000c60d  nop     dword ptr [rax+rax+00h]
0x18000c612  mov     eax, ebp
0x18000c614  jmp     short loc_18000C629
0x18000c616  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c61b  call    cs:__imp_SetLastError
0x18000c622  nop     dword ptr [rax+rax+00h]
0x18000c627  xor     eax, eax
0x18000c629  add     rsp, 38h
0x18000c62d  pop     r15
0x18000c62f  pop     r14
0x18000c631  pop     rdi
0x18000c632  pop     rsi
0x18000c633  pop     rbp
0x18000c634  pop     rbx
0x18000c635  retn
```
