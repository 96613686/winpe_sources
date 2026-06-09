# TpIndicateNewCall

- ea: `0x1400145e0`
- end: `0x14001487d`
- name: `TpIndicateNewCall`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140016534`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140002520`
- `0x1400145e0`
- `0x140018054`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001465b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014785`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001485e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001465b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014785`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001485e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001463b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400146b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001476c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001463b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400146b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001476c`
- `NDIS!NdisCmDispatchIncomingCall` at `0x1400146f3`
- `NDIS!NdisCmDispatchIncomingCall` at `0x1400146f3`

## pseudocode

```c
char __fastcall TpIndicateNewCall(__int64 a1, _BYTE *a2, int *a3)
{
  KIRQL v6; // al
  int v7; // ecx
  __int64 v8; // rsi
  KIRQL v9; // al
  unsigned int v10; // eax
  int v11; // esi
  char v12; // di
  KIRQL v13; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v7 = *(_DWORD *)(a1 + 80);
  *(_BYTE *)(a1 + 64) = v6;
  if ( (v7 & 0xC) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 126, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    return 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v6);
  v8 = PppoeCmBuildCallParams(a1);
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
    }
    return 0;
  }
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_QWORD *)(a1 + 176) = v8;
  *(_BYTE *)(a1 + 64) = v9;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v9);
  v10 = NdisCmDispatchIncomingCall(
          *(NDIS_HANDLE *)(*(_QWORD *)(a1 + 96) + 136LL),
          *(NDIS_HANDLE *)(a1 + 168),
          *(PCO_CALL_PARAMETERS *)(a1 + 176));
  v11 = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, v10);
  }
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1, v11);
    }
    v12 = 0;
    goto LABEL_22;
  }
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_DWORD *)(a1 + 88) |= 0x100u;
  *(_BYTE *)(a1 + 64) = v13;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v13);
  v12 = 1;
  if ( v11 != 259 )
  {
LABEL_22:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1, v11);
    }
    *a2 = 1;
    *a3 = v11;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  return v12;
}

```

## disassembly

```asm
0x1400145e0  push    rbx
0x1400145e2  push    rsi
0x1400145e3  push    rdi
0x1400145e4  push    r12
0x1400145e6  push    r13
0x1400145e8  push    r14
0x1400145ea  push    r15
0x1400145ec  sub     rsp, 30h
0x1400145f0  mov     r14, r8
0x1400145f3  mov     r15, rdx
0x1400145f6  mov     rbx, rcx
0x1400145f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014600  lea     r12, WPP_GLOBAL_Control
0x140014607  lea     r13, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x14001460e  mov     sil, 3
0x140014611  cmp     rcx, r12
0x140014614  jz      short loc_140014634
0x140014616  mov     eax, [rcx+2Ch]
0x140014619  test    al, 2
0x14001461b  jz      short loc_140014634
0x14001461d  cmp     [rcx+29h], sil
0x140014621  jb      short loc_140014634
0x140014623  mov     rcx, [rcx+18h]
0x140014627  mov     edx, 7Ch ; '|'
0x14001462c  mov     r8, r13
0x14001462f  call    WPP_SF_
0x140014634  lea     rdi, [rbx+38h]
0x140014638  mov     rcx, rdi; SpinLock
0x14001463b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014642  nop     dword ptr [rax+rax+00h]
0x140014647  mov     ecx, [rbx+50h]
0x14001464a  mov     [rbx+40h], al
0x14001464d  test    cl, 0Ch
0x140014650  jnz     loc_140014804
0x140014656  mov     dl, al; NewIrql
0x140014658  mov     rcx, rdi; SpinLock
0x14001465b  call    cs:__imp_KeReleaseSpinLock
0x140014662  nop     dword ptr [rax+rax+00h]
0x140014667  mov     rcx, rbx
0x14001466a  call    PppoeCmBuildCallParams
0x14001466f  mov     rsi, rax
0x140014672  test    rax, rax
0x140014675  jnz     short loc_1400146B0
0x140014677  mov     rcx, cs:WPP_GLOBAL_Control
0x14001467e  cmp     rcx, r12
0x140014681  jz      loc_14001486A
0x140014687  mov     eax, [rcx+2Ch]
0x14001468a  test    al, 2
0x14001468c  jz      loc_14001486A
0x140014692  cmp     byte ptr [rcx+29h], 1
0x140014696  jb      loc_14001486A
0x14001469c  mov     rcx, [rcx+18h]
0x1400146a0  lea     edx, [rsi+7Fh]
0x1400146a3  mov     r8, r13
0x1400146a6  call    WPP_SF_
0x1400146ab  jmp     loc_14001486A
0x1400146b0  mov     rcx, rdi; SpinLock
0x1400146b3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400146ba  nop     dword ptr [rax+rax+00h]
0x1400146bf  mov     rcx, rdi; SpinLock
0x1400146c2  mov     [rbx+0B0h], rsi
0x1400146c9  mov     dl, al; NewIrql
0x1400146cb  mov     [rbx+40h], al
0x1400146ce  call    cs:__imp_KeReleaseSpinLock
0x1400146d5  nop     dword ptr [rax+rax+00h]
0x1400146da  mov     rcx, [rbx+60h]
0x1400146de  mov     r8, [rbx+0B0h]; CallParameters
0x1400146e5  mov     rdx, [rbx+0A8h]; NdisVcHandle
0x1400146ec  mov     rcx, [rcx+88h]; NdisSapHandle
0x1400146f3  call    cs:__imp_NdisCmDispatchIncomingCall
0x1400146fa  nop     dword ptr [rax+rax+00h]
0x1400146ff  mov     esi, eax
0x140014701  mov     rcx, cs:WPP_GLOBAL_Control
0x140014708  cmp     rcx, r12
0x14001470b  jz      short loc_14001472F
0x14001470d  mov     edx, [rcx+2Ch]
0x140014710  test    dl, 2
0x140014713  jz      short loc_14001472F
0x140014715  cmp     byte ptr [rcx+29h], 2
0x140014719  jb      short loc_14001472F
0x14001471b  mov     rcx, [rcx+18h]
0x14001471f  mov     edx, 80h
0x140014724  mov     r9d, eax
0x140014727  mov     r8, r13
0x14001472a  call    WPP_SF_d
0x14001472f  test    esi, esi
0x140014731  jns     short loc_140014769
0x140014733  mov     rcx, cs:WPP_GLOBAL_Control
0x14001473a  cmp     rcx, r12
0x14001473d  jz      short loc_140014764
0x14001473f  mov     eax, [rcx+2Ch]
0x140014742  test    al, 2
0x140014744  jz      short loc_140014764
0x140014746  cmp     byte ptr [rcx+29h], 1
0x14001474a  jb      short loc_140014764
0x14001474c  mov     rcx, [rcx+18h]
0x140014750  mov     edx, 81h
0x140014755  mov     r9, rbx
0x140014758  mov     [rsp+68h+var_48], esi
0x14001475c  mov     r8, r13
0x14001475f  call    WPP_SF_qd
0x140014764  xor     dil, dil
0x140014767  jmp     short loc_14001479C
0x140014769  mov     rcx, rdi; SpinLock
0x14001476c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014773  nop     dword ptr [rax+rax+00h]
0x140014778  bts     dword ptr [rbx+58h], 8
0x14001477d  mov     rcx, rdi; SpinLock
0x140014780  mov     dl, al; NewIrql
0x140014782  mov     [rbx+40h], al
0x140014785  call    cs:__imp_KeReleaseSpinLock
0x14001478c  nop     dword ptr [rax+rax+00h]
0x140014791  mov     dil, 1
0x140014794  cmp     esi, 103h
0x14001479a  jz      short loc_1400147D4
0x14001479c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147a3  cmp     rcx, r12
0x1400147a6  jz      short loc_1400147CD
0x1400147a8  mov     eax, [rcx+2Ch]
0x1400147ab  test    al, 2
0x1400147ad  jz      short loc_1400147CD
0x1400147af  cmp     byte ptr [rcx+29h], 2
0x1400147b3  jb      short loc_1400147CD
0x1400147b5  mov     rcx, [rcx+18h]
0x1400147b9  mov     edx, 82h
0x1400147be  mov     r9, rbx
0x1400147c1  mov     [rsp+68h+var_48], esi
0x1400147c5  mov     r8, r13
0x1400147c8  call    WPP_SF_qd
0x1400147cd  mov     byte ptr [r15], 1
0x1400147d1  mov     [r14], esi
0x1400147d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147db  cmp     rcx, r12
0x1400147de  jz      short loc_1400147FF
0x1400147e0  mov     edx, [rcx+2Ch]
0x1400147e3  test    dl, 2
0x1400147e6  jz      short loc_1400147FF
0x1400147e8  cmp     byte ptr [rcx+29h], 3
0x1400147ec  jb      short loc_1400147FF
0x1400147ee  mov     rcx, [rcx+18h]
0x1400147f2  mov     edx, 83h
0x1400147f7  mov     r8, r13
0x1400147fa  call    WPP_SF_
0x1400147ff  mov     al, dil
0x140014802  jmp     short loc_14001486C
0x140014804  mov     rcx, cs:WPP_GLOBAL_Control
0x14001480b  cmp     rcx, r12
0x14001480e  jz      short loc_140014858
0x140014810  mov     eax, [rcx+2Ch]
0x140014813  test    al, 2
0x140014815  jz      short loc_14001482E
0x140014817  cmp     [rcx+29h], sil
0x14001481b  jb      short loc_14001482E
0x14001481d  mov     rcx, [rcx+18h]
0x140014821  mov     edx, 7Dh ; '}'
0x140014826  mov     r8, r13
0x140014829  call    WPP_SF_
0x14001482e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014835  cmp     rcx, r12
0x140014838  jz      short loc_140014858
0x14001483a  mov     eax, [rcx+2Ch]
0x14001483d  test    al, 2
0x14001483f  jz      short loc_140014858
0x140014841  cmp     [rcx+29h], sil
0x140014845  jb      short loc_140014858
0x140014847  mov     rcx, [rcx+18h]
0x14001484b  mov     edx, 7Eh ; '~'
0x140014850  mov     r8, r13
0x140014853  call    WPP_SF_
0x140014858  mov     dl, [rbx+40h]; NewIrql
0x14001485b  mov     rcx, rdi; SpinLock
0x14001485e  call    cs:__imp_KeReleaseSpinLock
0x140014865  nop     dword ptr [rax+rax+00h]
0x14001486a  xor     al, al
0x14001486c  add     rsp, 30h
0x140014870  pop     r15
0x140014872  pop     r14
0x140014874  pop     r13
0x140014876  pop     r12
0x140014878  pop     rdi
0x140014879  pop     rsi
0x14001487a  pop     rbx
0x14001487b  retn
```
