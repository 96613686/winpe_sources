# MRxSmbFinishT2OpenFile

- ea: `0x140038f6c`
- end: `0x140039200`
- name: `MRxSmbFinishT2OpenFile`
- size: `660`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400394f0`

## callees

- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x14000cbbc`
- `0x14000dfa8`
- `0x14000ee78`
- `0x140010660`
- `0x140038f6c`
- `0x14003b944`
- `0x1400499e0`
- `0x140051990`
- `0x1400526e4`
- `0x140052f50`

## import_xrefs

- `rdbss!RxInferFileType` at `0x140038ff1`
- `rdbss!RxInferFileType` at `0x140038ff1`

## string_xrefs

- `0x1400390eb`: `MRxSmbFinishT2OpenFile`
- `0x140039107`: `MRxSmbFinishT2OpenFile`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishT2OpenFile(PRX_CONTEXT RxContext, __int64 a2, __int64 a3, int a4)
{
  PMRX_SRV_OPEN pRelevantSrvOpen; // r12
  PMRX_FCB pFcb; // rsi
  __int64 v8; // r15
  ULONG PipeCompletionMode; // ebx
  RX_FILE_TYPE v10; // edi
  unsigned int v12; // eax
  int v13; // r9d
  __int64 v14; // r10
  char *v15; // rbx
  __int64 v16; // rax
  PRX_CONTEXT v17; // rcx
  unsigned int FileSuccessTail; // ebx
  int v19; // [rsp+90h] [rbp+8h]
  int v20; // [rsp+98h] [rbp+10h]

  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  pFcb = RxContext->pFcb;
  if ( pRelevantSrvOpen )
    v8 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  else
    v8 = 0;
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  v20 = MRxSmbMapSmbAttributes(*(unsigned __int16 *)(a2 + 2));
  v10 = RxInferFileType(RxContext);
  if ( v10 == FileTypeNotYetKnown )
    v10 = 2 - ((v20 & 0x10) != 0);
  if ( LODWORD(pFcb[1].Header.PagingIoResource) && v10 && (unsigned __int16)pFcb->Header.NodeTypeCode != v10 + 60448 )
    return 3221225508LL;
  v12 = MRxSmbUnmapDisposition(*(unsigned __int16 *)(a2 + 18), PipeCompletionMode);
  v19 = v12;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_LLL(
      WPP_GLOBAL_Control->AttachedDevice,
      59,
      WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      (unsigned int)v10,
      v13,
      v12);
    v12 = v19;
    v14 = 0;
  }
  if ( *(__int16 *)(a2 + 18) < (__int16)v14 )
    *(_BYTE *)(v8 + 10) = 2;
  *((_QWORD *)&RxContext->9 + 25) = v12;
  if ( LODWORD(pFcb[1].Header.PagingIoResource) == (_DWORD)v14 )
  {
    v15 = (char *)SmbCeReferenceAssociatedServerEntry(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease);
    MRxSmbSecondsSince1970ToTime(*(_DWORD *)(a2 + 4) & 0xFFFFFFFE, v15 + 400, v8 + 40);
    MRxSmbTrackDerefCount(v15, "MRxSmbFinishT2OpenFile", 3428);
    SmbReferenceRecord(v15 + 792, "MRxSmbFinishT2OpenFile", 3428);
    SmbCepDereferenceServerEntry(v15);
    v14 = 0;
  }
  *(_DWORD *)(v8 + 72) = v20;
  *(_QWORD *)(v8 + 48) = v14;
  *(_QWORD *)(v8 + 56) = v14;
  *(_QWORD *)(v8 + 64) = v14;
  *(_DWORD *)(v8 + 96) = 1;
  v16 = *(unsigned int *)(a2 + 8);
  *(_QWORD *)(v8 + 88) = v16;
  *(_QWORD *)(v8 + 80) = v16;
  *(_BYTE *)(v8 + 101) = v10 == 1;
  MRxSmbCopyAndTranslatePipeState(RxContext, *(unsigned __int16 *)(a2 + 16));
  LODWORD(pRelevantSrvOpen->Key) &= ~0x100000u;
  FileSuccessTail = MRxSmbCreateFileSuccessTail(v17, a4, *(_BYTE *)(v8 + 10), v19, v8 + 40);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      60,
      HIDWORD(pFcb->SrvOpenList.Blink),
      FileSuccessTail,
      HIDWORD(pFcb->SrvOpenList.Flink),
      HIDWORD(pFcb->SrvOpenList.Blink),
      pFcb->SrvOpenList.Blink);
  return FileSuccessTail;
}

```

## disassembly

```asm
0x140038f6c  mov     [rsp+arg_18], r9d
0x140038f71  mov     [rsp+arg_10], r8
0x140038f76  push    rbx
0x140038f77  push    rbp
0x140038f78  push    rsi
0x140038f79  push    rdi
0x140038f7a  push    r12
0x140038f7c  push    r13
0x140038f7e  push    r14
0x140038f80  push    r15
0x140038f82  sub     rsp, 48h
0x140038f86  mov     r12, [rcx+48h]
0x140038f8a  mov     r14, rdx
0x140038f8d  mov     rsi, [rcx+38h]
0x140038f91  mov     rbp, rcx
0x140038f94  test    r12, r12
0x140038f97  jnz     short loc_140038F9E
0x140038f99  xor     r15d, r15d
0x140038f9c  jmp     short loc_140038FA3
0x140038f9e  mov     r15, [r12+30h]
0x140038fa3  mov     ebx, [rcx+218h]
0x140038fa9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038fb0  lea     rax, WPP_GLOBAL_Control
0x140038fb7  cmp     rcx, rax
0x140038fba  jz      short loc_140038FDA
0x140038fbc  test    dword ptr [rcx+2Ch], 400h
0x140038fc3  jz      short loc_140038FDA
0x140038fc5  mov     rcx, [rcx+18h]
0x140038fc9  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140038fd0  mov     edx, 3Ah ; ':'
0x140038fd5  call    WPP_SF_
0x140038fda  movzx   ecx, word ptr [r14+2]
0x140038fdf  call    MRxSmbMapSmbAttributes
0x140038fe4  mov     rcx, rbp; RxContext
0x140038fe7  mov     [rsp+88h+arg_8], eax
0x140038fee  mov     r13d, eax
0x140038ff1  call    cs:__imp_RxInferFileType
0x140038ff8  nop     dword ptr [rax+rax+00h]
0x140038ffd  xor     r10d, r10d
0x140039000  mov     edi, eax
0x140039002  test    eax, eax
0x140039004  jnz     short loc_140039013
0x140039006  mov     cl, r13b
0x140039009  and     cl, 10h
0x14003900c  neg     cl
0x14003900e  sbb     edi, edi
0x140039010  add     edi, 2
0x140039013  cmp     [rsi+0C0h], r10d
0x14003901a  jz      short loc_140039037
0x14003901c  test    edi, edi
0x14003901e  jz      short loc_140039037
0x140039020  movzx   eax, word ptr [rsi]
0x140039023  lea     ecx, [rdi+0EC20h]
0x140039029  cmp     eax, ecx
0x14003902b  jz      short loc_140039037
0x14003902d  mov     eax, 0C0000024h
0x140039032  jmp     loc_1400391EE
0x140039037  movzx   r9d, word ptr [r14]
0x14003903b  lea     r13, [r15+28h]
0x14003903f  movzx   ecx, word ptr [r14+12h]
0x140039044  mov     edx, ebx
0x140039046  mov     word ptr [rsp+88h+arg_10], r9w
0x14003904f  call    MRxSmbUnmapDisposition
0x140039054  mov     [rsp+88h+arg_0], eax
0x14003905b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039062  lea     rdx, WPP_GLOBAL_Control
0x140039069  cmp     rcx, rdx
0x14003906c  jz      short loc_1400390A2
0x14003906e  test    dword ptr [rcx+2Ch], 400h
0x140039075  jz      short loc_1400390A2
0x140039077  mov     rcx, [rcx+18h]
0x14003907b  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140039082  mov     dword ptr [rsp+88h+var_60], eax
0x140039086  mov     edx, 3Bh ; ';'
0x14003908b  mov     [rsp+88h+var_68], r9d
0x140039090  mov     r9d, edi
0x140039093  call    WPP_SF_LLL
0x140039098  mov     eax, [rsp+88h+arg_0]
0x14003909f  xor     r10d, r10d
0x1400390a2  cmp     [r14+12h], r10w
0x1400390a7  jge     short loc_1400390AE
0x1400390a9  mov     byte ptr [r15+0Ah], 2
0x1400390ae  mov     eax, eax
0x1400390b0  mov     [rbp+258h], rax
0x1400390b7  cmp     [rsi+0C0h], r10d
0x1400390be  jnz     short loc_14003911E
0x1400390c0  mov     rcx, [rbp+280h]
0x1400390c7  call    SmbCeReferenceAssociatedServerEntry
0x1400390cc  mov     ecx, [r14+4]
0x1400390d0  mov     r8, r13
0x1400390d3  and     ecx, 0FFFFFFFEh
0x1400390d6  mov     rbx, rax
0x1400390d9  lea     rdx, [rax+190h]
0x1400390e0  call    MRxSmbSecondsSince1970ToTime
0x1400390e5  mov     r8d, 0D64h
0x1400390eb  lea     rdx, aMrxsmbfinisht2; "MRxSmbFinishT2OpenFile"
0x1400390f2  mov     rcx, rbx
0x1400390f5  call    MRxSmbTrackDerefCount
0x1400390fa  lea     rcx, [rbx+318h]
0x140039101  mov     r8d, 0D64h
0x140039107  lea     rdx, aMrxsmbfinisht2; "MRxSmbFinishT2OpenFile"
0x14003910e  call    SmbReferenceRecord
0x140039113  mov     rcx, rbx; pContext
0x140039116  call    SmbCepDereferenceServerEntry
0x14003911b  xor     r10d, r10d
0x14003911e  mov     eax, [rsp+88h+arg_8]
0x140039125  cmp     edi, 1
0x140039128  mov     [r13+20h], eax
0x14003912c  mov     rcx, rbp
0x14003912f  mov     [r13+8], r10
0x140039133  mov     [r13+10h], r10
0x140039137  mov     [r13+18h], r10
0x14003913b  mov     dword ptr [r13+38h], 1
0x140039143  mov     eax, [r14+8]
0x140039147  mov     [r13+30h], rax
0x14003914b  mov     [r13+28h], rax
0x14003914f  setz    al
0x140039152  mov     [r13+3Dh], al
0x140039156  movzx   edx, word ptr [r14+10h]
0x14003915b  call    MRxSmbCopyAndTranslatePipeState
0x140039160  mov     eax, [rsp+88h+arg_0]
0x140039167  mov     r8d, edi
0x14003916a  btr     dword ptr [r12+48h], 14h
0x140039171  movzx   r9d, word ptr [rsp+88h+arg_10]
0x14003917a  mov     [rsp+88h+var_50], r13; __int64
0x14003917f  mov     [rsp+88h+var_58], eax; int
0x140039183  mov     al, [r15+0Ah]
0x140039187  mov     [rsp+88h+var_60], al; char
0x14003918b  mov     eax, [rsp+88h+arg_18]
0x140039192  mov     [rsp+88h+var_68], eax; int
0x140039196  call    MRxSmbCreateFileSuccessTail
0x14003919b  mov     ebx, eax
0x14003919d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400391a4  lea     rax, WPP_GLOBAL_Control
0x1400391ab  cmp     rcx, rax
0x1400391ae  jz      short loc_1400391EC
0x1400391b0  test    dword ptr [rcx+2Ch], 400h
0x1400391b7  jz      short loc_1400391EC
0x1400391b9  mov     r8d, [rsi+0A0h]
0x1400391c0  mov     edx, 3Ch ; '<'
0x1400391c5  mov     eax, [rsi+9Ch]
0x1400391cb  mov     r9d, ebx
0x1400391ce  mov     rcx, [rcx+18h]
0x1400391d2  mov     [rsp+88h+var_58], r8d
0x1400391d7  mov     r8d, [rsi+0A4h]
0x1400391de  mov     dword ptr [rsp+88h+var_60], r8d
0x1400391e3  mov     [rsp+88h+var_68], eax
0x1400391e7  call    WPP_SF_LDDD
0x1400391ec  mov     eax, ebx
0x1400391ee  add     rsp, 48h
0x1400391f2  pop     r15
0x1400391f4  pop     r14
0x1400391f6  pop     r13
0x1400391f8  pop     r12
0x1400391fa  pop     rdi
0x1400391fb  pop     rsi
0x1400391fc  pop     rbp
0x1400391fd  pop     rbx
0x1400391fe  retn
```
