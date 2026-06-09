# MRxSmbFinishCoreOpen

- ea: `0x14003adf0`
- end: `0x14003af5b`
- name: `MRxSmbFinishCoreOpen`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x14000dfa8`
- `0x14003adf0`
- `0x1400499e0`
- `0x14004fff0`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishCoreOpen(__int64 a1, __int64 a2)
{
  struct _RX_CONTEXT *v2; // r13
  __int64 v5; // rdi
  PMRX_SRV_OPEN pRelevantSrvOpen; // rbp
  __int64 v7; // r14
  int v8; // r15d
  __int64 v9; // r9
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 result; // rax

  v2 = *(struct _RX_CONTEXT **)(a1 + 24);
  v5 = 0;
  pRelevantSrvOpen = v2->pRelevantSrvOpen;
  if ( pRelevantSrvOpen )
    v5 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids);
  if ( *(_BYTE *)a2 != 7 || *(_WORD *)(a2 + 15) || *(_DWORD *)(a1 + 1456) < 0x31u )
  {
    result = 3221225667LL;
    *(_DWORD *)(a1 + 48) = -1073741629;
  }
  else
  {
    v7 = v5 + 40;
    v8 = *(unsigned __int16 *)(a2 + 1);
    *(_DWORD *)(a1 + 572) = v8;
    v9 = *(unsigned int *)(a2 + 9);
    *(_DWORD *)(a1 + 576) = v9;
    if ( *(_BYTE *)(a1 + 580) )
      v10 = 2;
    else
      v10 = *(_BYTE *)(a1 + 581) != 0 ? 3 : 1;
    MRxSmbPopulateFileInfoInOE(a1, *(unsigned __int16 *)(a2 + 3), *(unsigned int *)(a2 + 5), v9);
    *(_DWORD *)(v7 + 32) = *(_DWORD *)(a1 + 504);
    *(_QWORD *)v7 = *(_QWORD *)(a1 + 472);
    *(_QWORD *)(v7 + 8) = *(_QWORD *)(a1 + 480);
    *(_QWORD *)(v7 + 16) = *(_QWORD *)(a1 + 488);
    *(_QWORD *)(v7 + 24) = *(_QWORD *)(a1 + 496);
    *(_DWORD *)(v7 + 56) = *(_DWORD *)(a1 + 528);
    *(_QWORD *)(v7 + 40) = *(_QWORD *)(a1 + 512);
    *(_QWORD *)(v7 + 48) = *(_QWORD *)(a1 + 520);
    *(_BYTE *)(v7 + 61) = 0;
    LODWORD(pRelevantSrvOpen->Key) &= ~0x100000u;
    return MRxSmbCreateFileSuccessTail(v2, v11, 2, v8, *(_DWORD *)(a1 + 52), 0, v10, v7);
  }
  return result;
}

```

## disassembly

```asm
0x14003adf0  push    rbx
0x14003adf2  push    rbp
0x14003adf3  push    rsi
0x14003adf4  push    rdi
0x14003adf5  push    r12
0x14003adf7  push    r13
0x14003adf9  push    r14
0x14003adfb  push    r15
0x14003adfd  sub     rsp, 48h
0x14003ae01  mov     r13, [rcx+18h]
0x14003ae05  xor     r12d, r12d
0x14003ae08  mov     rsi, rdx
0x14003ae0b  mov     rbx, rcx
0x14003ae0e  mov     edi, r12d
0x14003ae11  mov     rbp, [r13+48h]
0x14003ae15  test    rbp, rbp
0x14003ae18  jz      short loc_14003AE1E
0x14003ae1a  mov     rdi, [rbp+30h]
0x14003ae1e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003ae25  lea     rax, WPP_GLOBAL_Control
0x14003ae2c  cmp     rcx, rax
0x14003ae2f  jz      short loc_14003AE4F
0x14003ae31  test    dword ptr [rcx+2Ch], 400h
0x14003ae38  jz      short loc_14003AE4F
0x14003ae3a  mov     rcx, [rcx+18h]
0x14003ae3e  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003ae45  mov     edx, 2Bh ; '+'
0x14003ae4a  call    WPP_SF_
0x14003ae4f  cmp     byte ptr [rsi], 7
0x14003ae52  jnz     loc_14003AF41
0x14003ae58  cmp     [rsi+0Fh], r12w
0x14003ae5d  jnz     loc_14003AF41
0x14003ae63  cmp     dword ptr [rbx+5B0h], 31h ; '1'
0x14003ae6a  jb      loc_14003AF41
0x14003ae70  lea     r14, [rdi+28h]
0x14003ae74  movzx   r15d, word ptr [rsi+1]
0x14003ae79  mov     [rbx+23Ch], r15d
0x14003ae80  mov     r9d, [rsi+9]
0x14003ae84  mov     [rbx+240h], r9d
0x14003ae8b  cmp     [rbx+244h], r12b
0x14003ae92  jz      short loc_14003AE9B
0x14003ae94  mov     edi, 2
0x14003ae99  jmp     short loc_14003AEAA
0x14003ae9b  mov     al, [rbx+245h]
0x14003aea1  neg     al
0x14003aea3  sbb     edi, edi
0x14003aea5  and     edi, 2
0x14003aea8  inc     edi
0x14003aeaa  mov     r8d, [rsi+5]
0x14003aeae  mov     rcx, rbx
0x14003aeb1  movzx   edx, word ptr [rsi+3]
0x14003aeb5  call    MRxSmbPopulateFileInfoInOE
0x14003aeba  mov     eax, [rbx+1F8h]
0x14003aec0  movzx   r9d, r15w
0x14003aec4  mov     [r14+20h], eax
0x14003aec8  mov     r8d, 2
0x14003aece  mov     rax, [rbx+1D8h]
0x14003aed5  mov     rcx, r13; RxContext
0x14003aed8  mov     [r14], rax
0x14003aedb  mov     rax, [rbx+1E0h]
0x14003aee2  mov     [r14+8], rax
0x14003aee6  mov     rax, [rbx+1E8h]
0x14003aeed  mov     [r14+10h], rax
0x14003aef1  mov     rax, [rbx+1F0h]
0x14003aef8  mov     [r14+18h], rax
0x14003aefc  mov     eax, [rbx+210h]
0x14003af02  mov     [r14+38h], eax
0x14003af06  mov     rax, [rbx+200h]
0x14003af0d  mov     [r14+28h], rax
0x14003af11  mov     rax, [rbx+208h]
0x14003af18  mov     [r14+30h], rax
0x14003af1c  mov     [r14+3Dh], r12b
0x14003af20  btr     dword ptr [rbp+48h], 14h
0x14003af25  mov     eax, [rbx+34h]
0x14003af28  mov     [rsp+88h+var_50], r14; __int64
0x14003af2d  mov     [rsp+88h+var_58], edi; int
0x14003af31  mov     [rsp+88h+var_60], r12b; char
0x14003af36  mov     [rsp+88h+var_68], eax; int
0x14003af3a  call    MRxSmbCreateFileSuccessTail
0x14003af3f  jmp     short loc_14003AF49
0x14003af41  mov     eax, 0C00000C3h
0x14003af46  mov     [rbx+30h], eax
0x14003af49  add     rsp, 48h
0x14003af4d  pop     r15
0x14003af4f  pop     r14
0x14003af51  pop     r13
0x14003af53  pop     r12
0x14003af55  pop     rdi
0x14003af56  pop     rsi
0x14003af57  pop     rbp
0x14003af58  pop     rbx
0x14003af59  retn
```
