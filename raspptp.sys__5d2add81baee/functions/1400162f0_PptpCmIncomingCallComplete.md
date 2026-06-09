# PptpCmIncomingCallComplete

- ea: `0x1400162f0`
- end: `0x14001697a`
- name: `PptpCmIncomingCallComplete`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011050`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x1400039f8`
- `0x140003d58`
- `0x140003e08`
- `0x140003e38`
- `0x140006cf8`
- `0x1400076d0`
- `0x140011b90`
- `0x140013164`
- `0x140015a40`
- `0x1400162f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140016588`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400166b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400167fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400168e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400168fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016588`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400166b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400167fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400168e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400168fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001637a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016658`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001687b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001637a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016658`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001687b`
- `NDIS!NdisMCmActivateVc` at `0x1400166dc`
- `NDIS!NdisMCmActivateVc` at `0x1400166dc`

## pseudocode

```c
void __fastcall PptpCmIncomingCallComplete(unsigned int a1, __int64 a2)
{
  NDIS_STATUS v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // rbx
  __int16 v12; // dx
  bool v13; // zf
  __int16 v14; // dx
  __int16 v15; // cx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  __int16 v19; // bx
  __int16 v20; // di
  int v21; // esi
  struct _DEVICE_OBJECT *AttachedDevice; // rbp
  int StringFromSockAddr; // eax
  int v24; // edx
  int v25; // r8d
  KIRQL v26; // al
  __int64 v27; // rax
  __int64 v28; // rbx
  __int16 v29; // dx
  __int16 v30; // dx
  __int16 v31; // cx
  __int64 v32; // [rsp+40h] [rbp-A8h]
  _BYTE v33[80]; // [rsp+50h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  if ( a2 && *(_DWORD *)(a2 + 48) == 1129337936 )
  {
    v4 = -1073741823;
    *(_BYTE *)(a2 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
    if ( a1 )
    {
      ++dword_14000B43C;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v8 = 82;
        v6 = a1;
LABEL_76:
        WPP_SF_d(v7->AttachedDevice, v8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, v6);
        goto LABEL_77;
      }
      goto LABEL_77;
    }
    *(_DWORD *)(a2 + 424) |= 8u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    _InterlockedIncrement((volatile signed __int32 *)a2);
    v6 = *(unsigned int *)(a2 + 112);
    if ( (_DWORD)v6 == 11 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
      }
      goto LABEL_77;
    }
    v9 = *(_QWORD *)(a2 + 80);
    if ( !v9 )
    {
      ++dword_14000B448;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v6 = *(unsigned int *)(a2 + 200);
        v8 = 85;
        goto LABEL_76;
      }
LABEL_77:
      *(_DWORD *)(a2 + 424) &= ~0x100u;
      if ( v4 )
      {
        LOBYTE(v6) = 1;
        CallSetState(a2, 11, v5, v6);
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
        CallCleanup(a2);
      }
      else
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
      }
      DereferenceRefCount(a2);
      return;
    }
    if ( (_DWORD)v6 == 4 )
    {
      v10 = CtlAllocPacket(*(_QWORD *)(a2 + 80), 8);
      v11 = v10;
      v32 = v10;
      v12 = _InterlockedIncrement(&g_CallSerialNumber);
      v13 = PptpClientSide == 0;
      *(_WORD *)(a2 + 216) = v12;
      if ( v13 )
      {
        v15 = *(_WORD *)(a2 + 208);
      }
      else
      {
        v5 = 0x4000;
        v14 = *(_WORD *)(a2 + 200) + (v12 << 14);
        v15 = v14 + 0x4000;
        if ( *(_WORD *)(a2 + 320) != v14 )
          v15 = v14;
      }
      *(_WORD *)(a2 + 320) = v15;
      if ( !v10 )
      {
        ++dword_14000B44C;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_38;
        }
        v17 = 86;
LABEL_37:
        WPP_SF_d(v16->AttachedDevice, v17, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, *(unsigned int *)(a2 + 200));
LABEL_38:
        v4 = -1073741670;
        goto LABEL_77;
      }
      LOBYTE(v6) = 1;
      CallSetState(a2, 9, v5, v6);
      v18 = *(_DWORD *)(v9 + 656);
      *(_DWORD *)(a2 + 424) |= 0x20000u;
      *(_DWORD *)(a2 + 432) = v18;
      _InterlockedIncrement((volatile signed __int32 *)a2);
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
      *(_WORD *)(v11 + 14) = __ROR2__(*(_WORD *)(a2 + 316), 8);
      *(_WORD *)(v11 + 12) = __ROR2__(*(_WORD *)(a2 + 320), 8);
      *(_BYTE *)(v11 + 16) = 1;
      *(_WORD *)(v11 + 24) = 64;
      *(_DWORD *)(v11 + 20) = *(_DWORD *)(a2 + 432);
      *(_WORD *)(v11 + 26) = 0;
      *(_DWORD *)(v11 + 28) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v19 = *(_WORD *)(a2 + 316);
        v20 = *(_WORD *)(a2 + 320);
        v21 = *(_DWORD *)(a2 + 200);
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        StringFromSockAddr = GetStringFromSockAddr(a2 + 280, v33);
        WPP_SF_sddd((_DWORD)AttachedDevice, v24, v25, StringFromSockAddr, v21, v20, v19);
        v11 = v32;
      }
      v4 = CtlSend(v9, v11);
      if ( v4 )
      {
        v26 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
        *(_DWORD *)(a2 + 424) &= ~0x20000u;
        *(_BYTE *)(a2 + 104) = v26;
        ++dword_14000B450;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            88,
            WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids,
            *(unsigned int *)(a2 + 200));
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
        DereferenceRefCount(a2);
      }
      else
      {
        v4 = NdisMCmActivateVc(*(NDIS_HANDLE *)(a2 + 224), *(PCO_CALL_PARAMETERS *)(a2 + 232));
        if ( v4 != 259 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
          }
          PptpCmActivateVcComplete(v4, a2, *(_QWORD *)(a2 + 232));
        }
      }
    }
    else
    {
      if ( (_DWORD)v6 != 5 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v8 = 92;
          goto LABEL_76;
        }
        goto LABEL_77;
      }
      v27 = CtlAllocPacket(*(_QWORD *)(a2 + 80), 10);
      v28 = v27;
      v29 = _InterlockedIncrement(&g_CallSerialNumber);
      v13 = PptpClientSide == 0;
      *(_WORD *)(a2 + 216) = v29;
      if ( v13 )
      {
        v31 = *(_WORD *)(a2 + 208);
      }
      else
      {
        v5 = 0x4000;
        v30 = *(_WORD *)(a2 + 200) + (v29 << 14);
        v31 = v30 + 0x4000;
        if ( *(_WORD *)(a2 + 320) != v30 )
          v31 = v30;
      }
      *(_WORD *)(a2 + 320) = v31;
      if ( !v27 )
      {
        ++dword_14000B44C;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_38;
        }
        v17 = 90;
        goto LABEL_37;
      }
      LOBYTE(v6) = 1;
      CallSetState(a2, 6, v5, v6);
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
      *(_WORD *)(v28 + 14) = __ROR2__(*(_WORD *)(a2 + 316), 8);
      *(_WORD *)(v28 + 12) = __ROR2__(*(_WORD *)(a2 + 320), 8);
      *(_BYTE *)(v28 + 16) = 1;
      *(_DWORD *)(v28 + 18) = 64;
      v4 = CtlSend(v9, v28);
      if ( v4
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          91,
          WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids,
          *(unsigned int *)(a2 + 200));
      }
    }
    *(_BYTE *)(a2 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
    goto LABEL_77;
  }
  ++dword_14000B444;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
}

```

## disassembly

```asm
0x1400162f0  mov     [rsp+arg_10], rbx
0x1400162f5  push    rbp
0x1400162f6  push    rsi
0x1400162f7  push    rdi
0x1400162f8  push    r12
0x1400162fa  push    r13
0x1400162fc  push    r14
0x1400162fe  push    r15
0x140016300  sub     rsp, 0B0h
0x140016307  mov     rax, cs:__security_cookie
0x14001630e  xor     rax, rsp
0x140016311  mov     [rsp+0E8h+var_48], rax
0x140016319  mov     r14, rdx
0x14001631c  mov     edi, ecx
0x14001631e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016325  lea     rbp, WPP_GLOBAL_Control
0x14001632c  mov     esi, 4
0x140016331  cmp     rcx, rbp
0x140016334  jz      short loc_140016357
0x140016336  mov     eax, [rcx+2Ch]
0x140016339  test    sil, al
0x14001633c  jz      short loc_140016357
0x14001633e  cmp     byte ptr [rcx+29h], 2
0x140016342  jb      short loc_140016357
0x140016344  mov     rcx, [rcx+18h]
0x140016348  lea     edx, [rsi+4Ch]
0x14001634b  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140016352  call    WPP_SF_
0x140016357  test    r14, r14
0x14001635a  jz      loc_140016913
0x140016360  cmp     dword ptr [r14+30h], 43505450h
0x140016368  jnz     loc_140016913
0x14001636e  lea     r12, [r14+60h]
0x140016372  mov     ebx, 0C0000001h
0x140016377  mov     rcx, r12; SpinLock
0x14001637a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016381  nop     dword ptr [rax+rax+00h]
0x140016386  mov     [r14+68h], al
0x14001638a  mov     r15d, 1
0x140016390  test    edi, edi
0x140016392  jz      short loc_1400163CD
0x140016394  add     cs:dword_14000B43C, r15d
0x14001639b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163a2  cmp     rcx, rbp
0x1400163a5  jz      loc_1400168BC
0x1400163ab  mov     eax, [rcx+2Ch]
0x1400163ae  test    sil, al
0x1400163b1  jz      loc_1400168BC
0x1400163b7  cmp     [rcx+29h], r15b
0x1400163bb  jb      loc_1400168BC
0x1400163c1  lea     edx, [r15+51h]
0x1400163c5  mov     r9d, edi
0x1400163c8  jmp     loc_1400168AC
0x1400163cd  or      dword ptr [r14+1A8h], 8
0x1400163d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163dc  cmp     rcx, rbp
0x1400163df  jz      short loc_140016404
0x1400163e1  mov     eax, [rcx+2Ch]
0x1400163e4  test    sil, al
0x1400163e7  jz      short loc_140016404
0x1400163e9  cmp     byte ptr [rcx+29h], 2
0x1400163ed  jb      short loc_140016404
0x1400163ef  mov     rcx, [rcx+18h]
0x1400163f3  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400163fa  mov     edx, 53h ; 'S'
0x1400163ff  call    WPP_SF_
0x140016404  lock inc dword ptr [r14]
0x140016408  mov     r9d, [r14+70h]
0x14001640c  cmp     r9d, 0Bh
0x140016410  jnz     short loc_140016451
0x140016412  mov     rcx, cs:WPP_GLOBAL_Control
0x140016419  cmp     rcx, rbp
0x14001641c  jz      loc_1400168BC
0x140016422  mov     eax, [rcx+2Ch]
0x140016425  test    sil, al
0x140016428  jz      loc_1400168BC
0x14001642e  cmp     [rcx+29h], r15b
0x140016432  jb      loc_1400168BC
0x140016438  mov     rcx, [rcx+18h]
0x14001643c  lea     edx, [r9+49h]
0x140016440  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140016447  call    WPP_SF_
0x14001644c  jmp     loc_1400168BC
0x140016451  mov     r13, [r14+50h]
0x140016455  xor     edi, edi
0x140016457  test    r13, r13
0x14001645a  jnz     short loc_140016498
0x14001645c  add     cs:dword_14000B448, r15d
0x140016463  mov     rcx, cs:WPP_GLOBAL_Control
0x14001646a  cmp     rcx, rbp
0x14001646d  jz      loc_1400168BC
0x140016473  mov     eax, [rcx+2Ch]
0x140016476  test    sil, al
0x140016479  jz      loc_1400168BC
0x14001647f  cmp     [rcx+29h], r15b
0x140016483  jb      loc_1400168BC
0x140016489  mov     r9d, [r14+0C8h]
0x140016490  lea     edx, [rdi+55h]
0x140016493  jmp     loc_1400168AC
0x140016498  cmp     r9d, esi
0x14001649b  jnz     loc_14001673A
0x1400164a1  mov     edx, 8
0x1400164a6  mov     rcx, r13
0x1400164a9  call    CtlAllocPacket
0x1400164ae  mov     rbx, rax
0x1400164b1  mov     [rsp+0E8h+var_A8], rax
0x1400164b6  mov     edx, r15d
0x1400164b9  lock xadd cs:g_CallSerialNumber, edx
0x1400164c1  add     edx, r15d
0x1400164c4  cmp     cs:PptpClientSide, dil
0x1400164cb  mov     [r14+0D8h], dx
0x1400164d3  jz      short loc_1400164FC
0x1400164d5  mov     r8d, 4000h
0x1400164db  movzx   edx, dx
0x1400164de  imul    edx, r8d
0x1400164e2  add     dx, [r14+0C8h]
0x1400164ea  cmp     [r14+140h], dx
0x1400164f2  lea     ecx, [r8+rdx]
0x1400164f6  cmovnz  cx, dx
0x1400164fa  jmp     short loc_140016504
0x1400164fc  movzx   ecx, word ptr [r14+0D0h]
0x140016504  mov     [r14+140h], cx
0x14001650c  test    rbx, rbx
0x14001650f  jnz     short loc_140016556
0x140016511  add     cs:dword_14000B44C, r15d
0x140016518  mov     rcx, cs:WPP_GLOBAL_Control
0x14001651f  cmp     rcx, rbp
0x140016522  jz      short loc_14001654C
0x140016524  mov     eax, [rcx+2Ch]
0x140016527  test    sil, al
0x14001652a  jz      short loc_14001654C
0x14001652c  cmp     [rcx+29h], r15b
0x140016530  jb      short loc_14001654C
0x140016532  lea     edx, [rbx+56h]
0x140016535  mov     r9d, [r14+0C8h]
0x14001653c  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140016543  mov     rcx, [rcx+18h]
0x140016547  call    WPP_SF_d
0x14001654c  mov     ebx, 0C000009Ah
0x140016551  jmp     loc_1400168BC
0x140016556  mov     r9b, r15b
0x140016559  mov     edx, 9
0x14001655e  mov     rcx, r14
0x140016561  call    CallSetState
0x140016566  mov     eax, [r13+290h]
0x14001656d  bts     dword ptr [r14+1A8h], 11h
0x140016576  mov     [r14+1B0h], eax
0x14001657d  lock inc dword ptr [r14]
0x140016581  mov     dl, [r14+68h]; NewIrql
0x140016585  mov     rcx, r12; SpinLock
0x140016588  call    cs:__imp_KeReleaseSpinLock
0x14001658f  nop     dword ptr [rax+rax+00h]
0x140016594  movzx   eax, word ptr [r14+13Ch]
0x14001659c  ror     ax, 8
0x1400165a0  mov     [rbx+0Eh], ax
0x1400165a4  movzx   eax, word ptr [r14+140h]
0x1400165ac  ror     ax, 8
0x1400165b0  mov     [rbx+0Ch], ax
0x1400165b4  mov     [rbx+10h], r15b
0x1400165b8  mov     word ptr [rbx+18h], 40h ; '@'
0x1400165be  mov     eax, [r14+1B0h]
0x1400165c5  mov     [rbx+14h], eax
0x1400165c8  mov     [rbx+1Ah], di
0x1400165cc  mov     [rbx+1Ch], edi
0x1400165cf  mov     rbp, cs:WPP_GLOBAL_Control
0x1400165d6  lea     rdi, WPP_GLOBAL_Control
0x1400165dd  cmp     rbp, rdi
0x1400165e0  jz      short loc_140016644
0x1400165e2  mov     eax, [rbp+2Ch]
0x1400165e5  test    sil, al
0x1400165e8  jz      short loc_140016644
0x1400165ea  cmp     byte ptr [rbp+29h], 2
0x1400165ee  jb      short loc_140016644
0x1400165f0  movzx   ebx, word ptr [r14+13Ch]
0x1400165f8  lea     rcx, [r14+118h]
0x1400165ff  movzx   edi, word ptr [r14+140h]
0x140016607  lea     rdx, [rsp+0E8h+var_98]
0x14001660c  mov     esi, [r14+0C8h]
0x140016613  mov     rbp, [rbp+18h]
0x140016617  call    GetStringFromSockAddr
0x14001661c  mov     [rsp+0E8h+var_B8], ebx
0x140016620  mov     r9, rax
0x140016623  mov     [rsp+0E8h+var_C0], edi
0x140016627  mov     rcx, rbp
0x14001662a  mov     [rsp+0E8h+var_C8], esi
0x14001662e  call    WPP_SF_sddd
0x140016633  mov     rbx, [rsp+0E8h+var_A8]
0x140016638  lea     rdi, WPP_GLOBAL_Control
0x14001663f  mov     esi, 4
0x140016644  mov     rdx, rbx
0x140016647  mov     rcx, r13
0x14001664a  call    CtlSend
0x14001664f  mov     ebx, eax
0x140016651  test    eax, eax
0x140016653  jz      short loc_1400166CE
0x140016655  mov     rcx, r12; SpinLock
0x140016658  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001665f  nop     dword ptr [rax+rax+00h]
0x140016664  btr     dword ptr [r14+1A8h], 11h
0x14001666d  mov     [r14+68h], al
0x140016671  add     cs:dword_14000B450, r15d
0x140016678  mov     rcx, cs:WPP_GLOBAL_Control
0x14001667f  cmp     rcx, rdi
0x140016682  jz      short loc_1400166AE
0x140016684  mov     eax, [rcx+2Ch]
0x140016687  test    sil, al
0x14001668a  jz      short loc_1400166AE
0x14001668c  cmp     [rcx+29h], r15b
0x140016690  jb      short loc_1400166AE
0x140016692  mov     r9d, [r14+0C8h]
0x140016699  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400166a0  mov     rcx, [rcx+18h]
0x1400166a4  mov     edx, 58h ; 'X'
0x1400166a9  call    WPP_SF_d
0x1400166ae  mov     dl, [r14+68h]; NewIrql
0x1400166b2  mov     rcx, r12; SpinLock
0x1400166b5  call    cs:__imp_KeReleaseSpinLock
0x1400166bc  nop     dword ptr [rax+rax+00h]
0x1400166c1  mov     rcx, r14
0x1400166c4  call    DereferenceRefCount
0x1400166c9  jmp     loc_140016878
0x1400166ce  mov     rdx, [r14+0E8h]; CallParameters
0x1400166d5  mov     rcx, [r14+0E0h]; NdisVcHandle
0x1400166dc  call    cs:__imp_NdisMCmActivateVc
0x1400166e3  nop     dword ptr [rax+rax+00h]
0x1400166e8  mov     ebx, eax
0x1400166ea  cmp     eax, 103h
0x1400166ef  jz      loc_140016878
0x1400166f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166fc  cmp     rcx, rdi
0x1400166ff  jz      short loc_140016724
0x140016701  mov     eax, [rcx+2Ch]
0x140016704  test    sil, al
0x140016707  jz      short loc_140016724
0x140016709  cmp     byte ptr [rcx+29h], 2
0x14001670d  jb      short loc_140016724
0x14001670f  mov     rcx, [rcx+18h]
0x140016713  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x14001671a  mov     edx, 59h ; 'Y'
0x14001671f  call    WPP_SF_
0x140016724  mov     r8, [r14+0E8h]
0x14001672b  mov     rdx, r14
0x14001672e  mov     ecx, ebx
0x140016730  call    PptpCmActivateVcComplete
0x140016735  jmp     loc_140016878
0x14001673a  cmp     r9d, 5
0x14001673e  jnz     loc_14001688D
0x140016744  lea     edx, [r9+5]
0x140016748  mov     rcx, r13
0x14001674b  call    CtlAllocPacket
0x140016750  mov     rbx, rax
0x140016753  mov     edx, r15d
0x140016756  lock xadd cs:g_CallSerialNumber, edx
0x14001675e  add     edx, r15d
0x140016761  cmp     cs:PptpClientSide, dil
0x140016768  mov     [r14+0D8h], dx
0x140016770  jz      short loc_140016799
0x140016772  mov     r8d, 4000h
0x140016778  movzx   edx, dx
0x14001677b  imul    edx, r8d
0x14001677f  add     dx, [r14+0C8h]
0x140016787  cmp     [r14+140h], dx
0x14001678f  lea     ecx, [r8+rdx]
0x140016793  cmovnz  cx, dx
0x140016797  jmp     short loc_1400167A1
0x140016799  movzx   ecx, word ptr [r14+0D0h]
0x1400167a1  mov     [r14+140h], cx
0x1400167a9  test    rbx, rbx
0x1400167ac  jnz     short loc_1400167E3
0x1400167ae  add     cs:dword_14000B44C, r15d
0x1400167b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167bc  cmp     rcx, rbp
0x1400167bf  jz      loc_14001654C
0x1400167c5  mov     eax, [rcx+2Ch]
0x1400167c8  test    sil, al
0x1400167cb  jz      loc_14001654C
0x1400167d1  cmp     [rcx+29h], r15b
0x1400167d5  jb      loc_14001654C
0x1400167db  lea     edx, [rbx+5Ah]
0x1400167de  jmp     loc_140016535
0x1400167e3  mov     r9b, r15b
0x1400167e6  mov     edx, 6
0x1400167eb  mov     rcx, r14
0x1400167ee  call    CallSetState
0x1400167f3  mov     dl, [r14+68h]; NewIrql
0x1400167f7  mov     rcx, r12; SpinLock
0x1400167fa  call    cs:__imp_KeReleaseSpinLock
0x140016801  nop     dword ptr [rax+rax+00h]
0x140016806  movzx   eax, word ptr [r14+13Ch]
0x14001680e  mov     rdx, rbx
0x140016811  ror     ax, 8
0x140016815  mov     rcx, r13
0x140016818  mov     [rbx+0Eh], ax
0x14001681c  movzx   eax, word ptr [r14+140h]
0x140016824  ror     ax, 8
0x140016828  mov     [rbx+0Ch], ax
0x14001682c  mov     [rbx+10h], r15b
0x140016830  mov     dword ptr [rbx+12h], 40h ; '@'
0x140016837  call    CtlSend
0x14001683c  mov     ebx, eax
  ... truncated ...
```
