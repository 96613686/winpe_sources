# PptpCmRegSapPassive

- ea: `0x140006810`
- end: `0x1400069f6`
- name: `PptpCmRegSapPassive`
- size: `486`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002850`
- `0x1400028b0`
- `0x140003e08`
- `0x140003e38`
- `0x140006810`
- `0x140012da4`
- `0x140014fd8`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x140006831`
- `ntoskrnl!MmLockPagableDataSection` at `0x140006831`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000699b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000699b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006901`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006901`
- `NDIS!NdisCmRegisterSapComplete` at `0x1400069dc`
- `NDIS!NdisCmRegisterSapComplete` at `0x1400069dc`

## pseudocode

```c
void __fastcall PptpCmRegSapPassive(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // esi
  int v3; // edi
  unsigned int v4; // edi
  KIRQL v5; // al
  void *v6; // rbp

  v1 = *(_QWORD *)(a1 + 24);
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(PptpCmActivateVcComplete);
    g_fPagesLocked = 1;
  }
  v2 = PptpInitialize(v1);
  if ( v2
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  v3 = CtlListen(v1);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    if ( v3 < 0 )
      goto LABEL_38;
  }
  v4 = 0;
  if ( v2 < 0 )
  {
LABEL_38:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    v4 = -1073741823;
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 8));
  v6 = *(void **)(v1 + 136);
  *(_BYTE *)(v1 + 16) = v5;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    *(_QWORD *)(v1 + 136) = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    *(_DWORD *)(v1 + 164) = 1;
    ReferenceAdapter(v1);
    ReferenceAf(v1);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 8), *(_BYTE *)(v1 + 16));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, v4);
  }
  NdisCmRegisterSapComplete(v4, v6, (NDIS_HANDLE)v1);
}

```

## disassembly

```asm
0x140006810  push    rbx
0x140006812  push    rbp
0x140006813  push    rsi
0x140006814  push    rdi
0x140006815  push    r12
0x140006817  push    r13
0x140006819  sub     rsp, 28h
0x14000681d  cmp     cs:g_fPagesLocked, 0
0x140006824  mov     rbx, [rcx+18h]
0x140006828  jnz     short loc_140006844
0x14000682a  lea     rcx, PptpCmActivateVcComplete; AddressWithinSection
0x140006831  call    cs:__imp_MmLockPagableDataSection
0x140006838  nop     dword ptr [rax+rax+00h]
0x14000683d  mov     cs:g_fPagesLocked, 1
0x140006844  mov     rcx, rbx
0x140006847  call    PptpInitialize
0x14000684c  lea     r13, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140006853  mov     esi, eax
0x140006855  lea     r12, WPP_GLOBAL_Control
0x14000685c  test    eax, eax
0x14000685e  jz      short loc_14000688B
0x140006860  mov     rcx, cs:WPP_GLOBAL_Control
0x140006867  cmp     rcx, r12
0x14000686a  jz      short loc_14000688B
0x14000686c  mov     edx, [rcx+2Ch]
0x14000686f  test    dl, 4
0x140006872  jz      short loc_14000688B
0x140006874  cmp     byte ptr [rcx+29h], 1
0x140006878  jb      short loc_14000688B
0x14000687a  mov     rcx, [rcx+18h]
0x14000687e  mov     edx, 1Ah
0x140006883  mov     r8, r13
0x140006886  call    WPP_SF_
0x14000688b  mov     rcx, rbx
0x14000688e  call    CtlListen
0x140006893  mov     edi, eax
0x140006895  test    eax, eax
0x140006897  jz      short loc_1400068C8
0x140006899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068a0  cmp     rcx, r12
0x1400068a3  jz      short loc_1400068C4
0x1400068a5  mov     edx, [rcx+2Ch]
0x1400068a8  test    dl, 4
0x1400068ab  jz      short loc_1400068C4
0x1400068ad  cmp     byte ptr [rcx+29h], 1
0x1400068b1  jb      short loc_1400068C4
0x1400068b3  mov     rcx, [rcx+18h]
0x1400068b7  mov     edx, 1Bh
0x1400068bc  mov     r8, r13
0x1400068bf  call    WPP_SF_
0x1400068c4  test    edi, edi
0x1400068c6  js      short loc_1400068CE
0x1400068c8  xor     edi, edi
0x1400068ca  test    esi, esi
0x1400068cc  jns     short loc_1400068FD
0x1400068ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068d5  cmp     rcx, r12
0x1400068d8  jz      short loc_1400068F8
0x1400068da  mov     eax, [rcx+2Ch]
0x1400068dd  test    al, 4
0x1400068df  jz      short loc_1400068F8
0x1400068e1  cmp     byte ptr [rcx+29h], 1
0x1400068e5  jb      short loc_1400068F8
0x1400068e7  mov     rcx, [rcx+18h]
0x1400068eb  mov     edx, 1Ch
0x1400068f0  mov     r8, r13
0x1400068f3  call    WPP_SF_
0x1400068f8  mov     edi, 0C0000001h
0x1400068fd  lea     rcx, [rbx+8]; SpinLock
0x140006901  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006908  nop     dword ptr [rax+rax+00h]
0x14000690d  mov     rbp, [rbx+88h]
0x140006914  mov     [rbx+10h], al
0x140006917  test    edi, edi
0x140006919  jnz     short loc_14000695F
0x14000691b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006922  cmp     rcx, r12
0x140006925  jz      short loc_140006943
0x140006927  mov     eax, [rcx+2Ch]
0x14000692a  test    al, 4
0x14000692c  jz      short loc_140006943
0x14000692e  cmp     byte ptr [rcx+29h], 2
0x140006932  jb      short loc_140006943
0x140006934  mov     rcx, [rcx+18h]
0x140006938  lea     edx, [rdi+1Dh]
0x14000693b  mov     r8, r13
0x14000693e  call    WPP_SF_
0x140006943  mov     rcx, rbx
0x140006946  mov     dword ptr [rbx+0A4h], 1
0x140006950  call    ReferenceAdapter
0x140006955  mov     rcx, rbx
0x140006958  call    ReferenceAf
0x14000695d  jmp     short loc_140006994
0x14000695f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006966  cmp     rcx, r12
0x140006969  jz      short loc_140006989
0x14000696b  mov     eax, [rcx+2Ch]
0x14000696e  test    al, 4
0x140006970  jz      short loc_140006989
0x140006972  cmp     byte ptr [rcx+29h], 1
0x140006976  jb      short loc_140006989
0x140006978  mov     rcx, [rcx+18h]
0x14000697c  mov     edx, 1Eh
0x140006981  mov     r8, r13
0x140006984  call    WPP_SF_
0x140006989  mov     qword ptr [rbx+88h], 0
0x140006994  mov     dl, [rbx+10h]; NewIrql
0x140006997  lea     rcx, [rbx+8]; SpinLock
0x14000699b  call    cs:__imp_KeReleaseSpinLock
0x1400069a2  nop     dword ptr [rax+rax+00h]
0x1400069a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069ae  cmp     rcx, r12
0x1400069b1  jz      short loc_1400069D4
0x1400069b3  mov     eax, [rcx+2Ch]
0x1400069b6  test    al, 4
0x1400069b8  jz      short loc_1400069D4
0x1400069ba  cmp     byte ptr [rcx+29h], 2
0x1400069be  jb      short loc_1400069D4
0x1400069c0  mov     rcx, [rcx+18h]
0x1400069c4  mov     edx, 1Fh
0x1400069c9  mov     r9d, edi
0x1400069cc  mov     r8, r13
0x1400069cf  call    WPP_SF_d
0x1400069d4  mov     r8, rbx; CallMgrSapContext
0x1400069d7  mov     rdx, rbp; NdisSapHandle
0x1400069da  mov     ecx, edi; Status
0x1400069dc  call    cs:__imp_NdisCmRegisterSapComplete
0x1400069e3  nop     dword ptr [rax+rax+00h]
0x1400069e8  add     rsp, 28h
0x1400069ec  pop     r13
0x1400069ee  pop     r12
0x1400069f0  pop     rdi
0x1400069f1  pop     rsi
0x1400069f2  pop     rbp
0x1400069f3  pop     rbx
0x1400069f4  retn
```
