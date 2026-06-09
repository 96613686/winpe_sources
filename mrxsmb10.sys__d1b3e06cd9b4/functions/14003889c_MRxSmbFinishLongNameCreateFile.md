# MRxSmbFinishLongNameCreateFile

- ea: `0x14003889c`
- end: `0x140038abe`
- name: `MRxSmbFinishLongNameCreateFile`
- size: `546`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140037780`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x140010660`
- `0x14003889c`
- `0x1400499e0`
- `0x140052f50`

## import_xrefs

- `rdbss!RxInferFileType` at `0x14003891f`
- `rdbss!RxInferFileType` at `0x14003891f`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishLongNameCreateFile(PRX_CONTEXT RxContext, __int64 a2, __int64 a3, int a4)
{
  PMRX_SRV_OPEN pRelevantSrvOpen; // rbp
  PMRX_FCB pFcb; // rdi
  __int64 v9; // r15
  ULONGLONG ActualAllocationLength; // rax
  RX_FILE_TYPE v11; // ebx
  __int64 v13; // r10
  unsigned int v14; // r15d
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // edx
  bool v18; // cc
  __int64 v19; // rdx
  struct _RX_CONTEXT *v20; // rcx
  __int64 v21; // r10
  unsigned __int16 v22; // r11
  int v23; // eax
  unsigned int FileSuccessTail; // ebx

  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  pFcb = RxContext->pFcb;
  if ( pRelevantSrvOpen )
    v9 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  else
    v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( (*((_DWORD *)&RxContext->9 + 35) & 0x1000) != 0 )
  {
    if ( pFcb )
      ActualAllocationLength = pFcb->ActualAllocationLength;
    else
      ActualAllocationLength = 0;
    *(_DWORD *)(ActualAllocationLength + 4) |= 1u;
  }
  v11 = RxInferFileType(RxContext);
  if ( v11 == FileTypeNotYetKnown )
  {
    v11 = 2 - (*(_BYTE *)(a2 + 68) != 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        65,
        WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
        (unsigned int)v11);
  }
  if ( LODWORD(pFcb[1].Header.PagingIoResource) && v11 && (unsigned __int16)pFcb->Header.NodeTypeCode != v11 + 60448 )
    return 3221225508LL;
  v13 = v9 + 40;
  v14 = *(_DWORD *)(a2 + 4);
  *(_DWORD *)(v13 + 32) = *(_DWORD *)(a2 + 44);
  *(_QWORD *)v13 = *(_QWORD *)(a2 + 12);
  *(_QWORD *)(v13 + 8) = *(_QWORD *)(a2 + 20);
  *(_QWORD *)(v13 + 16) = *(_QWORD *)(a2 + 28);
  *(_QWORD *)(v13 + 24) = *(_QWORD *)(a2 + 36);
  *(_DWORD *)(v13 + 56) = 1;
  *(_QWORD *)(v13 + 40) = *(_QWORD *)(a2 + 48);
  v15 = *(_QWORD *)(a2 + 56);
  v16 = *(_DWORD *)(v13 + 44);
  *(_QWORD *)(v13 + 48) = v15;
  v17 = *(_DWORD *)(v13 + 52);
  *(_BYTE *)(v13 + 61) = *(_BYTE *)(a2 + 68);
  v18 = v16 < v17;
  if ( v16 == v17 )
  {
    if ( *(_DWORD *)(v13 + 40) < (unsigned int)v15 )
    {
LABEL_24:
      *(_QWORD *)(v13 + 40) = v15;
      goto LABEL_25;
    }
    v18 = v16 < v17;
  }
  if ( v18 )
    goto LABEL_24;
LABEL_25:
  MRxSmbCopyAndTranslatePipeState(RxContext, *(unsigned __int16 *)(a2 + 66));
  if ( *(_BYTE *)(a2 + 1) )
  {
    LODWORD(pRelevantSrvOpen[1].Context2) = *(_DWORD *)(a2 + 93);
    v23 = *(_DWORD *)(a2 + 97);
  }
  else
  {
    LODWORD(pRelevantSrvOpen[1].Context2) = 2032127;
    v23 = 0;
  }
  HIDWORD(pRelevantSrvOpen[1].Context2) = v23;
  LODWORD(pRelevantSrvOpen->Key) &= ~0x100000u;
  FileSuccessTail = MRxSmbCreateFileSuccessTail(v20, v19, (unsigned int)v11, v22, a4, *(_BYTE *)a2, v14, v21);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      66,
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
0x14003889c  push    rbx
0x14003889e  push    rbp
0x14003889f  push    rsi
0x1400388a0  push    rdi
0x1400388a1  push    r12
0x1400388a3  push    r14
0x1400388a5  push    r15
0x1400388a7  sub     rsp, 40h
0x1400388ab  mov     rbp, [rcx+48h]
0x1400388af  mov     r12d, r9d
0x1400388b2  mov     rdi, [rcx+38h]
0x1400388b6  mov     rsi, rdx
0x1400388b9  mov     r14, rcx
0x1400388bc  test    rbp, rbp
0x1400388bf  jnz     short loc_1400388C6
0x1400388c1  xor     r15d, r15d
0x1400388c4  jmp     short loc_1400388CA
0x1400388c6  mov     r15, [rbp+30h]
0x1400388ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400388d1  lea     rax, WPP_GLOBAL_Control
0x1400388d8  cmp     rcx, rax
0x1400388db  jz      short loc_1400388FB
0x1400388dd  test    dword ptr [rcx+2Ch], 400h
0x1400388e4  jz      short loc_1400388FB
0x1400388e6  mov     rcx, [rcx+18h]
0x1400388ea  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400388f1  mov     edx, 40h ; '@'
0x1400388f6  call    WPP_SF_
0x1400388fb  test    dword ptr [r14+21Ch], 1000h
0x140038906  jz      short loc_14003891C
0x140038908  test    rdi, rdi
0x14003890b  jnz     short loc_140038911
0x14003890d  xor     eax, eax
0x14003890f  jmp     short loc_140038918
0x140038911  mov     rax, [rdi+88h]
0x140038918  or      dword ptr [rax+4], 1
0x14003891c  mov     rcx, r14; RxContext
0x14003891f  call    cs:__imp_RxInferFileType
0x140038926  nop     dword ptr [rax+rax+00h]
0x14003892b  mov     ebx, eax
0x14003892d  test    eax, eax
0x14003892f  jnz     short loc_14003896F
0x140038931  mov     al, [rsi+44h]
0x140038934  neg     al
0x140038936  sbb     ebx, ebx
0x140038938  add     ebx, 2
0x14003893b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038942  lea     rax, WPP_GLOBAL_Control
0x140038949  cmp     rcx, rax
0x14003894c  jz      short loc_14003896F
0x14003894e  test    dword ptr [rcx+2Ch], 400h
0x140038955  jz      short loc_14003896F
0x140038957  mov     rcx, [rcx+18h]
0x14003895b  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140038962  mov     edx, 41h ; 'A'
0x140038967  mov     r9d, ebx
0x14003896a  call    WPP_SF_d
0x14003896f  cmp     dword ptr [rdi+0C0h], 0
0x140038976  jz      short loc_140038993
0x140038978  test    ebx, ebx
0x14003897a  jz      short loc_140038993
0x14003897c  movzx   eax, word ptr [rdi]
0x14003897f  lea     ecx, [rbx+0EC20h]
0x140038985  cmp     eax, ecx
0x140038987  jz      short loc_140038993
0x140038989  mov     eax, 0C0000024h
0x14003898e  jmp     loc_140038AAE
0x140038993  mov     eax, [rsi+2Ch]
0x140038996  lea     r10, [r15+28h]
0x14003899a  mov     r15d, [rsi+4]
0x14003899e  movzx   r11d, word ptr [rsi+2]
0x1400389a3  mov     [r10+20h], eax
0x1400389a7  mov     rax, [rsi+0Ch]
0x1400389ab  mov     [r10], rax
0x1400389ae  mov     rax, [rsi+14h]
0x1400389b2  mov     [r10+8], rax
0x1400389b6  mov     rax, [rsi+1Ch]
0x1400389ba  mov     [r10+10h], rax
0x1400389be  mov     rax, [rsi+24h]
0x1400389c2  mov     [r10+18h], rax
0x1400389c6  mov     dword ptr [r10+38h], 1
0x1400389ce  mov     rax, [rsi+30h]
0x1400389d2  mov     [r10+28h], rax
0x1400389d6  mov     rcx, [rsi+38h]
0x1400389da  mov     r8d, [r10+2Ch]
0x1400389de  mov     [r10+30h], rcx
0x1400389e2  mov     al, [rsi+44h]
0x1400389e5  mov     edx, [r10+34h]
0x1400389e9  mov     [r10+3Dh], al
0x1400389ed  cmp     r8d, edx
0x1400389f0  jnz     short loc_1400389FD
0x1400389f2  mov     eax, ecx
0x1400389f4  cmp     [r10+28h], eax
0x1400389f8  jb      short loc_1400389FF
0x1400389fa  cmp     r8d, edx
0x1400389fd  jge     short loc_140038A03
0x1400389ff  mov     [r10+28h], rcx
0x140038a03  movzx   edx, word ptr [rsi+42h]
0x140038a07  mov     rcx, r14
0x140038a0a  call    MRxSmbCopyAndTranslatePipeState
0x140038a0f  cmp     byte ptr [rsi+1], 0
0x140038a13  jz      short loc_140038A23
0x140038a15  mov     eax, [rsi+5Dh]
0x140038a18  mov     [rbp+98h], eax
0x140038a1e  mov     eax, [rsi+61h]
0x140038a21  jmp     short loc_140038A2F
0x140038a23  mov     dword ptr [rbp+98h], 1F01FFh
0x140038a2d  xor     eax, eax
0x140038a2f  mov     [rsp+78h+var_40], r10; __int64
0x140038a34  movzx   r9d, r11w
0x140038a38  mov     [rbp+9Ch], eax
0x140038a3e  mov     r8d, ebx
0x140038a41  btr     dword ptr [rbp+48h], 14h
0x140038a46  mov     al, [rsi]
0x140038a48  mov     [rsp+78h+var_48], r15d; int
0x140038a4d  mov     [rsp+78h+var_50], al; char
0x140038a51  mov     [rsp+78h+var_58], r12d; int
0x140038a56  call    MRxSmbCreateFileSuccessTail
0x140038a5b  mov     ebx, eax
0x140038a5d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038a64  lea     rax, WPP_GLOBAL_Control
0x140038a6b  cmp     rcx, rax
0x140038a6e  jz      short loc_140038AAC
0x140038a70  test    dword ptr [rcx+2Ch], 400h
0x140038a77  jz      short loc_140038AAC
0x140038a79  mov     r8d, [rdi+0A0h]
0x140038a80  mov     edx, 42h ; 'B'
0x140038a85  mov     eax, [rdi+9Ch]
0x140038a8b  mov     r9d, ebx
0x140038a8e  mov     rcx, [rcx+18h]
0x140038a92  mov     [rsp+78h+var_48], r8d
0x140038a97  mov     r8d, [rdi+0A4h]
0x140038a9e  mov     dword ptr [rsp+78h+var_50], r8d
0x140038aa3  mov     [rsp+78h+var_58], eax
0x140038aa7  call    WPP_SF_LDDD
0x140038aac  mov     eax, ebx
0x140038aae  add     rsp, 40h
0x140038ab2  pop     r15
0x140038ab4  pop     r14
0x140038ab6  pop     r12
0x140038ab8  pop     rdi
0x140038ab9  pop     rsi
0x140038aba  pop     rbp
0x140038abb  pop     rbx
0x140038abc  retn
```
