# MRxSmb2IsValidDirectory

- ea: `0x140021fb0`
- end: `0x14002247c`
- name: `MRxSmb2IsValidDirectory`
- size: `1228`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140021fb0`
- `0x140022490`
- `0x1400286c0`
- `0x140029084`
- `0x140029840`
- `0x14002ed54`
- `0x140055890`

## import_xrefs

- `rdbss!RxCrackPathName` at `0x14002222d`
- `rdbss!RxCrackPathName` at `0x14002222d`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x1400223fa`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x1400223fa`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x1400223b0`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x1400223b0`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x1400222c5`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x1400222c5`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140022381`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140022381`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400223d1`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400223eb`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400223d1`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400223eb`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002239f`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002239f`
- `mrxsmb!SmbCeInitializeExchange` at `0x140022324`
- `mrxsmb!SmbCeInitializeExchange` at `0x140022324`

## pseudocode

```c
__int64 __fastcall MRxSmb2IsValidDirectory(__int64 a1, unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  unsigned __int16 *v5; // r14
  __int64 v6; // rsi
  __int64 v7; // rbp
  __int64 v8; // rcx
  int v9; // ebx
  char v10; // si
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  bool v13; // zf
  int v14; // edx
  __int64 CompoundingKey; // rbp
  int v16; // eax
  __int128 v18; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v5 = a2;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 656) + 40LL);
  v7 = *(_QWORD *)(*(_QWORD *)(v6 + 416) + 384LL);
  v19 = 0;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
  {
    LOBYTE(a4) = -76;
    McTemplateK0uq_EtwWriteTransfer(a1, a2, a1 + 412, a4, 0);
  }
  v8 = *(_QWORD *)(a1 + 672);
  if ( (*(_DWORD *)(v8 + 12) & 8) != 0 && !*(_BYTE *)(*(_QWORD *)(v6 + 416) + 466LL) )
  {
    v9 = -1073741311;
    v10 = 15;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 10;
LABEL_9:
      WPP_SF_qD(v11->AttachedDevice, v12, WPP_ee24b2b8a5db353f82ee6bd9c10172b6_Traceguids, a1, -1073741311);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  if ( *(_DWORD *)(v8 + 8) == 3 && (*(_DWORD *)(v7 + 716) & 0x8000) == 0 )
  {
    v9 = -1073741311;
    v10 = 24;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 11;
      goto LABEL_9;
    }
LABEL_61:
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer((_DWORD)v11, (unsigned int)CreateFileError, a1 + 412, v9, v10, 0);
    goto LABEL_63;
  }
  v9 = Smb2SetupAlternateSPNForSession(*(_QWORD *)(v6 + 416), *(USHORT **)(a1 + 680));
  if ( v9 < 0 )
  {
    v10 = 38;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_ee24b2b8a5db353f82ee6bd9c10172b6_Traceguids, a1, v9);
    }
    goto LABEL_61;
  }
  v11 = (PDEVICE_OBJECT)*(unsigned int *)(*(_QWORD *)(a1 + 672) + 8LL);
  if ( (_DWORD)v11 == 4 )
  {
    v13 = (*(_DWORD *)(v7 + 716) & 0x8000) == 0;
    v14 = 1024;
  }
  else
  {
    if ( (_DWORD)v11 == 3 )
    {
      v14 = (*(_DWORD *)(v7 + 716) >> 5) & 0x400;
      goto LABEL_29;
    }
    v14 = 0;
    v13 = (_DWORD)v11 == 2;
  }
  if ( v13 )
    v14 = 512;
LABEL_29:
  if ( (*(_BYTE *)(a1 + 749) & 8) != 0 )
    *(_DWORD *)(v6 + 448) |= v14;
  a2 = (unsigned __int16 *)(*(_DWORD *)(v6 + 448) | (unsigned int)v14);
  if ( ((unsigned __int16)a2 & 0x600) != 0 && (*(_BYTE *)(*(_QWORD *)(v6 + 416) + 4LL) & 3) != 0 )
  {
    v10 = -1;
    v9 = -1073741311;
    goto LABEL_61;
  }
  if ( ((unsigned __int16)a2 & 0x400) != 0 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 672) + 20LL) = 3;
  }
  else if ( ((unsigned __int16)a2 & 0x200) != 0 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 672) + 20LL) = 2;
  }
  v11 = *(PDEVICE_OBJECT *)(a1 + 672);
  if ( (HIDWORD(v11->DriverObject) & 8) != 0 )
    LODWORD(v11->AttachedDevice) |= 8u;
  if ( *v5 && (*v5 != 2 || **((_WORD **)v5 + 1) != 92) )
  {
    if ( (*(_BYTE *)(a1 + 750) & 8) != 0
      && (v18 = 0,
          RxCrackPathName(v5, &v18, 0, 0),
          (int)Smb2FetchFileIdentityFromCacheEx(a1, *(_QWORD *)(v6 + 424) + 192LL, &v18, 0, 0) >= 0) )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ee24b2b8a5db353f82ee6bd9c10172b6_Traceguids, &v18);
      }
    }
    else
    {
      if ( (*(_BYTE *)(a1 + 749) & 0x18) == 0x18 )
      {
        v9 = 0;
        goto LABEL_63;
      }
      CompoundingKey = SmbCseAllocateCompoundingKey(32);
      if ( !CompoundingKey )
      {
        v9 = -1073741670;
        v10 = -101;
        goto LABEL_61;
      }
      v16 = *v5;
      v19 = 0;
      v9 = SmbCeInitializeExchange(&v19, a1, 0, 0, 0, v6, ((v16 + 9) & 0xFFFFFFF8) + 4096, &CheckPathDispatch);
      if ( v9 )
      {
        v10 = -83;
      }
      else
      {
        if ( *(_QWORD *)(a1 + 560) == 4282664531LL )
          _InterlockedOr((volatile signed __int32 *)(v19 + 68), 0x8000u);
        *(_QWORD *)(v19 + 3792) = v5;
        *(_BYTE *)(v19 + 3800) = 1;
        SmbCeAssociateExchangeWithCompoundingKeyEx(v19, CompoundingKey, 0xFFFF);
        _InterlockedOr((volatile signed __int32 *)(v19 + 68), 0x81u);
        v9 = SmbCeInitiateExchange(v19);
        SmbCseReleaseCompoundingKey(CompoundingKey);
        if ( v9 == 259 )
        {
          v9 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v19, 0, 0, 0);
          v10 = -57;
        }
        else
        {
          v10 = -64;
          SmbCeWaitForCompletionAndFinalizeExchangeEx(v19, 0, 0, 0);
        }
      }
      SmbCseDereferenceCompoundingKey(CompoundingKey);
      if ( v9 < 0 )
        goto LABEL_61;
    }
  }
LABEL_63:
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
  {
    LOBYTE(a4) = -75;
    McTemplateK0uq_EtwWriteTransfer(v11, a2, a1 + 412, a4, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140021fb0  mov     r11, rsp
0x140021fb3  push    rdi
0x140021fb4  sub     rsp, 60h
0x140021fb8  mov     rax, [rcx+290h]
0x140021fbf  mov     rdi, rcx
0x140021fc2  mov     [r11+18h], rbp
0x140021fc6  mov     [r11+20h], rsi
0x140021fca  mov     [r11-10h], r14
0x140021fce  mov     r14, rdx
0x140021fd1  mov     rsi, [rax+28h]
0x140021fd5  mov     [r11-18h], r15
0x140021fd9  xor     r15d, r15d
0x140021fdc  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 2
0x140021fe3  mov     rax, [rsi+1A0h]
0x140021fea  mov     rbp, [rax+180h]
0x140021ff1  mov     [r11+8], r15
0x140021ff5  jz      short loc_14002200A
0x140021ff7  lea     r8, [rcx+19Ch]
0x140021ffe  mov     [r11-48h], r15d
0x140022002  mov     r9b, 0B4h
0x140022005  call    McTemplateK0uq_EtwWriteTransfer
0x14002200a  mov     rcx, [rdi+2A0h]
0x140022011  mov     [rsp+68h+arg_8], rbx
0x140022016  mov     eax, [rcx+0Ch]
0x140022019  test    al, 8
0x14002201b  jz      short loc_140022088
0x14002201d  mov     rax, [rsi+1A0h]
0x140022024  cmp     [rax+1D2h], r15b
0x14002202b  jnz     short loc_140022088
0x14002202d  mov     ebx, 0C0000201h
0x140022032  mov     esi, 20Fh
0x140022037  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002203e  lea     rax, WPP_GLOBAL_Control
0x140022045  cmp     rcx, rax
0x140022048  jz      loc_14002240A
0x14002204e  mov     eax, [rcx+2Ch]
0x140022051  test    al, 1
0x140022053  jz      loc_14002240A
0x140022059  cmp     byte ptr [rcx+29h], 1
0x14002205d  jb      loc_14002240A
0x140022063  mov     edx, 0Ah
0x140022068  mov     dword ptr [rsp+68h+var_48], 0C0000201h
0x140022070  mov     rcx, [rcx+18h]
0x140022074  lea     r8, WPP_ee24b2b8a5db353f82ee6bd9c10172b6_Traceguids
0x14002207b  mov     r9, rdi
0x14002207e  call    WPP_SF_qD
0x140022083  jmp     loc_14002240A
0x140022088  cmp     dword ptr [rcx+8], 3
0x14002208c  jnz     short loc_1400220D7
0x14002208e  test    dword ptr [rbp+2CCh], 8000h
0x140022098  jnz     short loc_1400220D7
0x14002209a  mov     ebx, 0C0000201h
0x14002209f  mov     esi, 218h
0x1400220a4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400220ab  lea     rax, WPP_GLOBAL_Control
0x1400220b2  cmp     rcx, rax
0x1400220b5  jz      loc_14002240A
0x1400220bb  mov     eax, [rcx+2Ch]
0x1400220be  test    al, 1
0x1400220c0  jz      loc_14002240A
0x1400220c6  cmp     byte ptr [rcx+29h], 1
0x1400220ca  jb      loc_14002240A
0x1400220d0  mov     edx, 0Bh
0x1400220d5  jmp     short loc_140022068
0x1400220d7  mov     rdx, [rdi+2A8h]
0x1400220de  mov     rcx, [rsi+1A0h]
0x1400220e5  call    Smb2SetupAlternateSPNForSession
0x1400220ea  mov     ebx, eax
0x1400220ec  test    eax, eax
0x1400220ee  jns     short loc_14002212F
0x1400220f0  mov     esi, 226h
0x1400220f5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400220fc  lea     rax, WPP_GLOBAL_Control
0x140022103  cmp     rcx, rax
0x140022106  jz      loc_14002240A
0x14002210c  mov     eax, [rcx+2Ch]
0x14002210f  test    al, 1
0x140022111  jz      loc_14002240A
0x140022117  cmp     byte ptr [rcx+29h], 1
0x14002211b  jb      loc_14002240A
0x140022121  mov     edx, 0Ch
0x140022126  mov     dword ptr [rsp+68h+var_48], ebx
0x14002212a  jmp     loc_140022070
0x14002212f  mov     rax, [rdi+2A0h]
0x140022136  mov     r8d, 200h
0x14002213c  mov     ecx, [rax+8]
0x14002213f  cmp     ecx, 4
0x140022142  jnz     short loc_140022155
0x140022144  test    dword ptr [rbp+2CCh], 8000h
0x14002214e  mov     edx, 400h
0x140022153  jmp     short loc_140022171
0x140022155  cmp     ecx, 3
0x140022158  jnz     short loc_14002216B
0x14002215a  mov     edx, [rbp+2CCh]
0x140022160  shr     edx, 5
0x140022163  and     edx, 400h
0x140022169  jmp     short loc_140022175
0x14002216b  mov     edx, r15d
0x14002216e  cmp     ecx, 2
0x140022171  cmovz   edx, r8d
0x140022175  test    byte ptr [rdi+2EDh], 8
0x14002217c  jz      short loc_140022184
0x14002217e  or      [rsi+1C0h], edx
0x140022184  or      edx, [rsi+1C0h]
0x14002218a  test    edx, 600h
0x140022190  jz      short loc_1400221AE
0x140022192  mov     rax, [rsi+1A0h]
0x140022199  test    byte ptr [rax+4], 3
0x14002219d  jz      short loc_1400221AE
0x14002219f  mov     esi, 1FFh
0x1400221a4  mov     ebx, 0C0000201h
0x1400221a9  jmp     loc_14002240A
0x1400221ae  bt      edx, 0Ah
0x1400221b2  jnb     short loc_1400221C4
0x1400221b4  mov     rax, [rdi+2A0h]
0x1400221bb  mov     dword ptr [rax+14h], 3
0x1400221c2  jmp     short loc_1400221D7
0x1400221c4  test    r8d, edx
0x1400221c7  jz      short loc_1400221D7
0x1400221c9  mov     rax, [rdi+2A0h]
0x1400221d0  mov     dword ptr [rax+14h], 2
0x1400221d7  mov     rcx, [rdi+2A0h]
0x1400221de  mov     eax, [rcx+0Ch]
0x1400221e1  test    al, 8
0x1400221e3  jz      short loc_1400221E9
0x1400221e5  or      dword ptr [rcx+18h], 8
0x1400221e9  movzx   eax, word ptr [r14]
0x1400221ed  test    ax, ax
0x1400221f0  jz      loc_140022438
0x1400221f6  cmp     ax, 2
0x1400221fa  jnz     short loc_14002220A
0x1400221fc  mov     rax, [r14+8]
0x140022200  cmp     word ptr [rax], 5Ch ; '\'
0x140022204  jz      loc_140022438
0x14002220a  test    byte ptr [rdi+2EEh], 8
0x140022211  jz      loc_1400222AB
0x140022217  xorps   xmm0, xmm0
0x14002221a  lea     rdx, [rsp+68h+var_28]
0x14002221f  xor     r9d, r9d
0x140022222  xor     r8d, r8d
0x140022225  mov     rcx, r14
0x140022228  movups  [rsp+68h+var_28], xmm0
0x14002222d  call    cs:__imp_RxCrackPathName
0x140022234  nop     dword ptr [rax+rax+00h]
0x140022239  mov     rdx, [rsi+1A8h]
0x140022240  lea     r8, [rsp+68h+var_28]
0x140022245  add     rdx, 0C0h
0x14002224c  mov     [rsp+68h+var_48], r15
0x140022251  xor     r9d, r9d
0x140022254  mov     rcx, rdi
0x140022257  call    Smb2FetchFileIdentityFromCacheEx
0x14002225c  test    eax, eax
0x14002225e  js      short loc_1400222AB
0x140022260  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022267  lea     rax, WPP_GLOBAL_Control
0x14002226e  cmp     rcx, rax
0x140022271  jz      loc_140022438
0x140022277  mov     eax, [rcx+2Ch]
0x14002227a  test    al, al
0x14002227c  jns     loc_140022438
0x140022282  cmp     byte ptr [rcx+29h], 2
0x140022286  jb      loc_140022438
0x14002228c  mov     rcx, [rcx+18h]
0x140022290  lea     r9, [rsp+68h+var_28]
0x140022295  mov     edx, 0Dh
0x14002229a  lea     r8, WPP_ee24b2b8a5db353f82ee6bd9c10172b6_Traceguids
0x1400222a1  call    WPP_SF_Z
0x1400222a6  jmp     loc_140022438
0x1400222ab  movzx   eax, byte ptr [rdi+2EDh]
0x1400222b2  and     al, 18h
0x1400222b4  cmp     al, 18h
0x1400222b6  jnz     short loc_1400222C0
0x1400222b8  mov     ebx, r15d
0x1400222bb  jmp     loc_140022438
0x1400222c0  mov     ecx, 20h ; ' '
0x1400222c5  call    cs:__imp_SmbCseAllocateCompoundingKey
0x1400222cc  nop     dword ptr [rax+rax+00h]
0x1400222d1  mov     rbp, rax
0x1400222d4  test    rax, rax
0x1400222d7  jnz     short loc_1400222E8
0x1400222d9  mov     ebx, 0C000009Ah
0x1400222de  mov     esi, 29Bh
0x1400222e3  jmp     loc_14002240A
0x1400222e8  movzx   eax, word ptr [r14]
0x1400222ec  lea     rcx, CheckPathDispatch
0x1400222f3  mov     [rsp+68h+var_30], rcx
0x1400222f8  add     eax, 9
0x1400222fb  and     eax, 0FFFFFFF8h
0x1400222fe  mov     [rsp+68h+arg_0], r15
0x140022303  add     eax, 1000h
0x140022308  lea     rcx, [rsp+68h+arg_0]
0x14002230d  mov     [rsp+68h+var_38], eax
0x140022311  xor     r9d, r9d
0x140022314  mov     [rsp+68h+var_40], rsi
0x140022319  xor     r8d, r8d
0x14002231c  mov     rdx, rdi
0x14002231f  mov     [rsp+68h+var_48], r15
0x140022324  call    cs:__imp_SmbCeInitializeExchange
0x14002232b  nop     dword ptr [rax+rax+00h]
0x140022330  mov     ebx, eax
0x140022332  test    eax, eax
0x140022334  jz      short loc_140022340
0x140022336  mov     esi, 2ADh
0x14002233b  jmp     loc_1400223F7
0x140022340  mov     eax, 0FF444653h
0x140022345  cmp     [rdi+230h], rax
0x14002234c  jnz     short loc_14002235B
0x14002234e  mov     rax, [rsp+68h+arg_0]
0x140022353  lock or dword ptr [rax+44h], 8000h
0x14002235b  mov     rax, [rsp+68h+arg_0]
0x140022360  mov     r8d, 0FFFFh
0x140022366  mov     rdx, rbp
0x140022369  mov     [rax+0ED0h], r14
0x140022370  mov     rax, [rsp+68h+arg_0]
0x140022375  mov     byte ptr [rax+0ED8h], 1
0x14002237c  mov     rcx, [rsp+68h+arg_0]
0x140022381  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140022388  nop     dword ptr [rax+rax+00h]
0x14002238d  mov     rax, [rsp+68h+arg_0]
0x140022392  lock or dword ptr [rax+44h], 81h
0x14002239a  mov     rcx, [rsp+68h+arg_0]
0x14002239f  call    cs:__imp_SmbCeInitiateExchange
0x1400223a6  nop     dword ptr [rax+rax+00h]
0x1400223ab  mov     rcx, rbp
0x1400223ae  mov     ebx, eax
0x1400223b0  call    cs:__imp_SmbCseReleaseCompoundingKey
0x1400223b7  nop     dword ptr [rax+rax+00h]
0x1400223bc  mov     rcx, [rsp+68h+arg_0]
0x1400223c1  xor     r9d, r9d
0x1400223c4  xor     r8d, r8d
0x1400223c7  xor     edx, edx
0x1400223c9  cmp     ebx, 103h
0x1400223cf  jnz     short loc_1400223E6
0x1400223d1  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x1400223d8  nop     dword ptr [rax+rax+00h]
0x1400223dd  mov     ebx, eax
0x1400223df  mov     esi, 2C7h
0x1400223e4  jmp     short loc_1400223F7
0x1400223e6  mov     esi, 2C0h
0x1400223eb  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x1400223f2  nop     dword ptr [rax+rax+00h]
0x1400223f7  mov     rcx, rbp
0x1400223fa  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140022401  nop     dword ptr [rax+rax+00h]
0x140022406  test    ebx, ebx
0x140022408  jns     short loc_140022438
0x14002240a  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 1
0x140022411  jz      short loc_140022438
0x140022413  or      esi, 20400000h
0x140022419  mov     dword ptr [rsp+68h+var_40], r15d
0x14002241e  lea     r8, [rdi+19Ch]
0x140022425  mov     dword ptr [rsp+68h+var_48], esi
0x140022429  mov     r9d, ebx
0x14002242c  lea     rdx, CreateFileError
0x140022433  call    McTemplateK0qqq_EtwWriteTransfer
0x140022438  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 2
0x14002243f  mov     r15, [rsp+68h+var_18]
0x140022444  mov     r14, [rsp+68h+var_10]
0x140022449  mov     rsi, [rsp+68h+arg_18]
0x140022451  mov     rbp, [rsp+68h+arg_10]
0x140022459  jz      short loc_14002246E
0x14002245b  lea     r8, [rdi+19Ch]
0x140022462  mov     dword ptr [rsp+68h+var_48], ebx
0x140022466  mov     r9b, 0B5h
0x140022469  call    McTemplateK0uq_EtwWriteTransfer
0x14002246e  mov     eax, ebx
0x140022470  mov     rbx, [rsp+68h+arg_8]
0x140022475  add     rsp, 60h
0x140022479  pop     rdi
0x14002247a  retn
```
