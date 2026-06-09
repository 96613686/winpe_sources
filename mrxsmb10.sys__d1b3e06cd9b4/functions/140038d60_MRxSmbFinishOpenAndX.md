# MRxSmbFinishOpenAndX

- ea: `0x140038d60`
- end: `0x140038f63`
- name: `MRxSmbFinishOpenAndX`
- size: `515`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x140010660`
- `0x140038d60`
- `0x14003b944`
- `0x1400499e0`
- `0x140051990`
- `0x1400526e4`
- `0x140052f50`

## import_xrefs

- `rdbss!RxInferFileType` at `0x140038dd8`
- `rdbss!RxInferFileType` at `0x140038dd8`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishOpenAndX(__int64 a1, __int64 a2)
{
  struct _RX_CONTEXT *v2; // rsi
  PMRX_SRV_OPEN pRelevantSrvOpen; // r14
  _DWORD *p_NodeTypeCode; // rbp
  __int64 v6; // rax
  __int64 v7; // r12
  RX_FILE_TYPE v8; // r15d
  unsigned __int16 v9; // bx
  __int64 v10; // r9
  int v11; // eax
  unsigned int FileSuccessTail; // ebx
  ULONG PipeCompletionMode; // [rsp+80h] [rbp+8h]

  v2 = *(struct _RX_CONTEXT **)(a1 + 24);
  pRelevantSrvOpen = v2->pRelevantSrvOpen;
  p_NodeTypeCode = &v2->pFcb->Header.NodeTypeCode;
  PipeCompletionMode = v2->Create.PipeCompletionMode;
  if ( pRelevantSrvOpen )
    v6 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  else
    v6 = 0;
  v7 = v6 + 40;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  }
  v8 = RxInferFileType(v2);
  if ( v8 == FileTypeNotYetKnown )
  {
    v8 = FileTypeDirectory;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, 2);
    }
  }
  v9 = *(_WORD *)(a2 + 23);
  *(_DWORD *)(v7 + 32) = MRxSmbMapSmbAttributes(*(unsigned __int16 *)(a2 + 7));
  pRelevantSrvOpen[1].Context2 = (PVOID)2032127;
  MRxSmbSecondsSince1970ToTime(*(unsigned int *)(v10 + 9), *(_QWORD *)(a1 + 80) + 400LL, v7 + 16);
  *(_DWORD *)(v7 + 52) = 0;
  *(_DWORD *)(v7 + 56) = 1;
  *(_QWORD *)v7 = 0;
  *(_QWORD *)(v7 + 8) = 0;
  *(_QWORD *)(v7 + 24) = 0;
  *(_DWORD *)(v7 + 48) = *(_DWORD *)(a2 + 13);
  *(_QWORD *)(v7 + 40) = *(_QWORD *)(v7 + 48);
  *(_BYTE *)(v7 + 61) = v8 == 1;
  MRxSmbCopyAndTranslatePipeState(v2, *(unsigned __int16 *)(a2 + 21));
  LODWORD(pRelevantSrvOpen->Key) &= ~0x100000u;
  v11 = MRxSmbUnmapDisposition(v9, PipeCompletionMode);
  FileSuccessTail = MRxSmbCreateFileSuccessTail(v2, *(_DWORD *)(a1 + 52), (v9 & 0x8000u) == 0 ? 0 : 2, v11, v7);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      55,
      (unsigned int)p_NodeTypeCode[41],
      FileSuccessTail,
      p_NodeTypeCode[39],
      p_NodeTypeCode[41],
      p_NodeTypeCode[40]);
  return FileSuccessTail;
}

```

## disassembly

```asm
0x140038d60  mov     [rsp+arg_10], rbx
0x140038d65  mov     [rsp+arg_8], rdx
0x140038d6a  push    rbp
0x140038d6b  push    rsi
0x140038d6c  push    rdi
0x140038d6d  push    r12
0x140038d6f  push    r13
0x140038d71  push    r14
0x140038d73  push    r15
0x140038d75  sub     rsp, 40h
0x140038d79  mov     rsi, [rcx+18h]
0x140038d7d  mov     r13, rcx
0x140038d80  mov     r14, [rsi+48h]
0x140038d84  mov     eax, [rsi+218h]
0x140038d8a  mov     rbp, [rsi+38h]
0x140038d8e  mov     [rsp+78h+arg_0], eax
0x140038d95  test    r14, r14
0x140038d98  jnz     short loc_140038D9E
0x140038d9a  xor     eax, eax
0x140038d9c  jmp     short loc_140038DA2
0x140038d9e  mov     rax, [r14+30h]
0x140038da2  lea     r12, [rax+28h]
0x140038da6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038dad  lea     rdi, WPP_GLOBAL_Control
0x140038db4  cmp     rcx, rdi
0x140038db7  jz      short loc_140038DD5
0x140038db9  bt      dword ptr [rcx+2Ch], 0Ah
0x140038dbe  jnb     short loc_140038DD5
0x140038dc0  mov     rcx, [rcx+18h]
0x140038dc4  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140038dcb  mov     edx, 35h ; '5'
0x140038dd0  call    WPP_SF_
0x140038dd5  mov     rcx, rsi; RxContext
0x140038dd8  call    cs:__imp_RxInferFileType
0x140038ddf  nop     dword ptr [rax+rax+00h]
0x140038de4  mov     r15d, eax
0x140038de7  mov     r8d, 2
0x140038ded  test    eax, eax
0x140038def  jnz     short loc_140038E1D
0x140038df1  mov     r15d, r8d
0x140038df4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038dfb  cmp     rcx, rdi
0x140038dfe  jz      short loc_140038E1D
0x140038e00  bt      dword ptr [rcx+2Ch], 0Ah
0x140038e05  jnb     short loc_140038E1D
0x140038e07  mov     rcx, [rcx+18h]
0x140038e0b  lea     edx, [rax+36h]
0x140038e0e  mov     r9d, r8d
0x140038e11  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140038e18  call    WPP_SF_d
0x140038e1d  mov     r9, [rsp+78h+arg_8]
0x140038e25  movzx   ecx, word ptr [r9+7]
0x140038e2a  movzx   edi, word ptr [r9+5]
0x140038e2f  movzx   ebx, word ptr [r9+17h]
0x140038e34  call    MRxSmbMapSmbAttributes
0x140038e39  mov     [r12+20h], eax
0x140038e3e  lea     r8, [r12+10h]
0x140038e43  mov     qword ptr [r14+98h], 1F01FFh
0x140038e4e  mov     rdx, [r13+50h]
0x140038e52  mov     ecx, [r9+9]
0x140038e56  add     rdx, 190h
0x140038e5d  call    MRxSmbSecondsSince1970ToTime
0x140038e62  mov     rdx, [rsp+78h+arg_8]
0x140038e6a  xor     r10d, r10d
0x140038e6d  mov     [r12+34h], r10d
0x140038e72  cmp     r15d, 1
0x140038e76  mov     dword ptr [r12+38h], 1
0x140038e7f  mov     rcx, rsi
0x140038e82  mov     [r12], r10
0x140038e86  mov     [r12+8], r10
0x140038e8b  mov     [r12+18h], r10
0x140038e90  mov     eax, [rdx+0Dh]
0x140038e93  mov     [r12+30h], eax
0x140038e98  mov     rax, [r12+30h]
0x140038e9d  mov     [r12+28h], rax
0x140038ea2  setz    al
0x140038ea5  mov     [r12+3Dh], al
0x140038eaa  movzx   edx, word ptr [rdx+15h]
0x140038eae  call    MRxSmbCopyAndTranslatePipeState
0x140038eb3  mov     edx, [rsp+78h+arg_0]
0x140038eba  movzx   ecx, bx
0x140038ebd  btr     dword ptr [r14+48h], 14h
0x140038ec3  call    MRxSmbUnmapDisposition
0x140038ec8  mov     [rsp+78h+var_40], r12; __int64
0x140038ecd  test    bx, bx
0x140038ed0  mov     [rsp+78h+var_48], eax; int
0x140038ed4  movzx   r9d, di
0x140038ed8  mov     eax, [r13+34h]
0x140038edc  setns   dl
0x140038edf  dec     dl
0x140038ee1  mov     r8d, r15d
0x140038ee4  and     dl, 2
0x140038ee7  mov     rcx, rsi; RxContext
0x140038eea  mov     [rsp+78h+var_50], dl; char
0x140038eee  mov     [rsp+78h+var_58], eax; int
0x140038ef2  call    MRxSmbCreateFileSuccessTail
0x140038ef7  mov     ebx, eax
0x140038ef9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038f00  lea     rax, WPP_GLOBAL_Control
0x140038f07  cmp     rcx, rax
0x140038f0a  jz      short loc_140038F48
0x140038f0c  test    dword ptr [rcx+2Ch], 400h
0x140038f13  jz      short loc_140038F48
0x140038f15  mov     r8d, [rbp+0A0h]
0x140038f1c  mov     edx, 37h ; '7'
0x140038f21  mov     eax, [rbp+9Ch]
0x140038f27  mov     r9d, ebx
0x140038f2a  mov     rcx, [rcx+18h]
0x140038f2e  mov     [rsp+78h+var_48], r8d
0x140038f33  mov     r8d, [rbp+0A4h]
0x140038f3a  mov     dword ptr [rsp+78h+var_50], r8d
0x140038f3f  mov     [rsp+78h+var_58], eax
0x140038f43  call    WPP_SF_LDDD
0x140038f48  mov     eax, ebx
0x140038f4a  mov     rbx, [rsp+78h+arg_10]
0x140038f52  add     rsp, 40h
0x140038f56  pop     r15
0x140038f58  pop     r14
0x140038f5a  pop     r13
0x140038f5c  pop     r12
0x140038f5e  pop     rdi
0x140038f5f  pop     rsi
0x140038f60  pop     rbp
0x140038f61  retn
```
