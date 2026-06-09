# RxDrainIOForSrvOpens

- ea: `0x140074600`
- end: `0x1400747ff`
- name: `RxDrainIOForSrvOpens`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400441c0`

## callees

- `0x140009b80`
- `0x14000ec40`
- `0x1400120c0`
- `0x1400167d0`
- `0x1400173d0`
- `0x140025540`
- `0x140057660`
- `0x140074600`
- `0x140074810`
- `0x140074a00`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007464a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007464a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400747cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b817`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400747cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b817`

## pseudocode

```c
__int64 __fastcall RxDrainIOForSrvOpens(__int64 a1, struct _MRX_NET_ROOT_ *a2)
{
  struct _FCB *i; // rax
  struct _MRX_FCB_ *p_Header; // rdi
  _QWORD *v6; // r8
  const CHAR *v7; // r9
  PMRX_NET_ROOT *p_pNetRoot; // r13
  PMRX_NET_ROOT *v9; // rax
  PMRX_NET_ROOT *v10; // rcx
  PMRX_NET_ROOT *v11; // rax
  PMRX_NET_ROOT *v12; // r15
  _QWORD *v13; // r12
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // r14
  __int64 v17; // rdx
  __int64 v18; // r8
  PCSTR FileName[2]; // [rsp+20h] [rbp-88h] BYREF
  __int128 v21; // [rsp+30h] [rbp-78h]
  __int128 v22; // [rsp+40h] [rbp-68h]
  _OWORD v23[3]; // [rsp+50h] [rbp-58h] BYREF

  *(_OWORD *)FileName = 0;
  v21 = 0;
  v22 = 0;
  RfsInitializeRundownBatch(FileName);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 344), 1u);
  memset(v23, 0, sizeof(v23));
  for ( i = (struct _FCB *)RxFcbTableLookupFirstFcb(a1 + 296, 0, 0, v23); ; i = (struct _FCB *)RxFcbTableLookupNextFcb(v23) )
  {
    p_Header = (struct _MRX_FCB_ *)&i->Header;
    if ( !i )
      break;
    if ( (i->Header.NodeTypeCode & 0xFFF0) != 0xEC20 )
      __int2c();
    if ( _RxAcquireFcb(i, (PRX_CONTEXT)0xFFFFFFFFFFFFFFFELL, 1u, 0, FileName[0], (ULONG)FileName[1]) )
      __int2c();
    p_pNetRoot = &p_Header[1].pNetRoot;
    v9 = &p_Header[1].pNetRoot;
    while ( 1 )
    {
      v9 = (PMRX_NET_ROOT *)*v9;
      if ( v9 == p_pNetRoot )
        break;
      v10 = v9 - 17;
      if ( *((_WORD *)v9 - 68) != 0xEBAA )
        goto LABEL_11;
    }
    v10 = 0;
LABEL_11:
    while ( v10 )
    {
      v11 = v10 + 17;
      while ( 1 )
      {
        v11 = (PMRX_NET_ROOT *)*v11;
        if ( v11 == p_pNetRoot )
          break;
        v12 = v11 - 17;
        if ( *((_WORD *)v11 - 68) != 0xEBAA )
          goto LABEL_16;
      }
      v12 = 0;
LABEL_16:
      if ( v10[5] == a2 )
      {
        v13 = v10 + 23;
        v14 = v10 + 23;
        while ( 1 )
        {
          v14 = (_QWORD *)*v14;
          if ( v14 == v13 )
            break;
          v6 = v14 - 14;
          if ( *((_WORD *)v14 - 56) != 0xEBAA )
            goto LABEL_21;
        }
        v6 = 0;
LABEL_21:
        while ( v6 )
        {
          v15 = v6 + 14;
          while ( 1 )
          {
            v15 = (_QWORD *)*v15;
            if ( v15 == v13 )
              break;
            v16 = v15 - 14;
            if ( *((_WORD *)v15 - 56) != 0xEBAA )
              goto LABEL_26;
          }
          v16 = 0;
LABEL_26:
          RfsStartRundownProtectionReleaseAndAddToBatch(FileName, v6[13] + 8LL);
          RxCancelNotifyChangeDirectoryRequestsForFobxOnCleanup(v18, v17, v18);
          v6 = v16;
        }
      }
      v10 = v12;
    }
    _RxReleaseFcb(0, p_Header, (ULONG)v6, v7, (ULONG)FileName[0]);
  }
  RxFcbTableEndLookup(v23);
  ExReleaseResourceLite((PERESOURCE)(a1 + 344));
  return RfsWaitForRundownBatch(FileName);
}

```

## disassembly

```asm
0x140074600  mov     [rsp+arg_8], rbx
0x140074605  mov     [rsp+arg_10], rsi
0x14007460a  mov     [rsp+arg_0], rcx
0x14007460f  push    rdi
0x140074610  push    r12
0x140074612  push    r13
0x140074614  push    r14
0x140074616  push    r15
0x140074618  sub     rsp, 80h
0x14007461f  mov     rsi, rdx
0x140074622  mov     rbx, rcx
0x140074625  xorps   xmm0, xmm0
0x140074628  movups  xmmword ptr [rsp+0A8h+FileName], xmm0; SerialNumber
0x14007462d  movups  [rsp+0A8h+var_78], xmm0
0x140074632  movups  [rsp+0A8h+var_68], xmm0
0x140074637  lea     rcx, [rsp+0A8h+FileName]
0x14007463c  call    RfsInitializeRundownBatch
0x140074641  lea     rcx, [rbx+158h]; Resource
0x140074648  mov     dl, 1; Wait
0x14007464a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140074651  nop     dword ptr [rax+rax+00h]
0x140074656  nop
0x140074657  xorps   xmm0, xmm0
0x14007465a  movups  [rsp+0A8h+var_58], xmm0
0x14007465f  movups  [rsp+0A8h+var_48], xmm0
0x140074664  movups  [rsp+0A8h+var_38], xmm0
0x140074669  lea     r9, [rsp+0A8h+var_58]
0x14007466e  xor     r8d, r8d
0x140074671  xor     edx, edx
0x140074673  lea     rcx, [rbx+128h]
0x14007467a  call    RxFcbTableLookupFirstFcb
0x14007467f  mov     r14d, 0EBAAh
0x140074685  mov     rdi, rax
0x140074688  mov     edx, 0EC20h
0x14007468d  mov     eax, 0FFF0h
0x140074692  test    rdi, rdi
0x140074695  jz      loc_1400747B9
0x14007469b  movzx   ecx, word ptr [rdi]
0x14007469e  and     cx, ax
0x1400746a1  cmp     cx, dx
0x1400746a4  jz      short loc_1400746A8
0x1400746a6  int     2Ch; Windows NT - assertion failure
0x1400746a8  xor     r9d, r9d; LineNumber
0x1400746ab  mov     rdx, 0FFFFFFFFFFFFFFFEh; RxContext
0x1400746b2  mov     r8d, 1; Mode
0x1400746b8  mov     rcx, rdi; Fcb
0x1400746bb  call    __RxAcquireFcb
0x1400746c0  test    eax, eax
0x1400746c2  jz      short loc_1400746C6
0x1400746c4  int     2Ch; Windows NT - assertion failure
0x1400746c6  lea     r13, [rdi+108h]
0x1400746cd  mov     rax, r13
0x1400746d0  mov     rax, [rax]
0x1400746d3  cmp     rax, r13
0x1400746d6  jnz     short loc_1400746DC
0x1400746d8  xor     ecx, ecx
0x1400746da  jmp     short loc_1400746ED
0x1400746dc  lea     rcx, [rax-88h]
0x1400746e3  cmp     [rcx], r14w
0x1400746e7  jz      loc_1400747B4
0x1400746ed  test    rcx, rcx
0x1400746f0  jz      loc_14007479B
0x1400746f6  lea     rax, [rcx+88h]
0x1400746fd  mov     rax, [rax]
0x140074700  cmp     rax, r13
0x140074703  jnz     short loc_14007470A
0x140074705  xor     r15d, r15d
0x140074708  jmp     short loc_140074717
0x14007470a  lea     r15, [rax-88h]
0x140074711  cmp     [r15], r14w
0x140074715  jz      short loc_140074796
0x140074717  cmp     [rcx+28h], rsi
0x14007471b  jz      short loc_14007471F
0x14007471d  jmp     short loc_14007478C
0x14007471f  lea     r12, [rcx+0B8h]
0x140074726  mov     rax, r12
0x140074729  mov     rax, [rax]
0x14007472c  cmp     rax, r12
0x14007472f  jnz     short loc_140074736
0x140074731  xor     r8d, r8d
0x140074734  jmp     short loc_140074740
0x140074736  lea     r8, [rax-70h]
0x14007473a  cmp     [r8], r14w
0x14007473e  jz      short loc_140074794
0x140074740  test    r8, r8
0x140074743  jz      short loc_140074786
0x140074745  lea     rax, [r8+70h]
0x140074749  mov     ecx, 0EBAAh
0x14007474e  mov     rax, [rax]
0x140074751  cmp     rax, r12
0x140074754  jnz     short loc_14007475B
0x140074756  xor     r14d, r14d
0x140074759  jmp     short loc_140074765
0x14007475b  lea     r14, [rax-70h]
0x14007475f  cmp     [r14], cx
0x140074763  jz      short loc_140074784
0x140074765  mov     rdx, [r8+68h]
0x140074769  add     rdx, 8
0x14007476d  lea     rcx, [rsp+0A8h+FileName]
0x140074772  call    RfsStartRundownProtectionReleaseAndAddToBatch
0x140074777  mov     rcx, r8
0x14007477a  call    RxCancelNotifyChangeDirectoryRequestsForFobxOnCleanup
0x14007477f  mov     r8, r14
0x140074782  jmp     short loc_140074740
0x140074784  jmp     short loc_14007474E
0x140074786  mov     r14d, 0EBAAh
0x14007478c  mov     rcx, r15
0x14007478f  jmp     loc_1400746ED
0x140074794  jmp     short loc_140074729
0x140074796  jmp     loc_1400746FD
0x14007479b  mov     rdx, rdi; MrxFcb
0x14007479e  xor     ecx, ecx; RxContext
0x1400747a0  call    __RxReleaseFcb
0x1400747a5  lea     rcx, [rsp+0A8h+var_58]
0x1400747aa  call    RxFcbTableLookupNextFcb
0x1400747af  jmp     loc_140074685
0x1400747b4  jmp     loc_1400746D0
0x1400747b9  lea     rcx, [rsp+0A8h+var_58]
0x1400747be  call    RxFcbTableEndLookup
0x1400747c3  nop
0x1400747c4  lea     rcx, [rbx+158h]; Resource
0x1400747cb  call    cs:__imp_ExReleaseResourceLite
0x1400747d2  nop     dword ptr [rax+rax+00h]
0x1400747d7  lea     rcx, [rsp+0A8h+FileName]
0x1400747dc  call    RfsWaitForRundownBatch
0x1400747e1  lea     r11, [rsp+0A8h+var_28]
0x1400747e9  mov     rbx, [r11+38h]
0x1400747ed  mov     rsi, [r11+40h]
0x1400747f1  mov     rsp, r11
0x1400747f4  pop     r15
0x1400747f6  pop     r14
0x1400747f8  pop     r13
0x1400747fa  pop     r12
0x1400747fc  pop     rdi
0x1400747fd  retn
0x14007b800  push    rbp
0x14007b802  sub     rsp, 20h
0x14007b806  mov     rbp, rdx
0x14007b809  mov     rcx, [rbp+0B0h]
0x14007b810  add     rcx, 158h; Resource
0x14007b817  call    cs:__imp_ExReleaseResourceLite
0x14007b81e  nop     dword ptr [rax+rax+00h]
0x14007b823  lea     rcx, [rbp+20h]
0x14007b827  call    RfsWaitForRundownBatch
0x14007b82c  nop
0x14007b82d  add     rsp, 20h
0x14007b831  pop     rbp
0x14007b832  retn
```
