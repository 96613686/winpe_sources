# NbtDispatchInternalCtrl

- ea: `0x1400062b0`
- end: `0x1400067d1`
- name: `NbtDispatchInternalCtrl`
- size: `1313`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140047d90`

## callees

- `0x1400062b0`
- `0x140006900`
- `0x1400148a0`
- `0x140022ed0`
- `0x140025e98`
- `0x140026758`
- `0x1400269a8`
- `0x14002d588`
- `0x14002d608`
- `0x14002d9f8`
- `0x1400400a4`
- `0x140040214`
- `0x14004025c`
- `0x14004031c`
- `0x140045128`
- `0x140045220`
- `0x14004f08c`
- `0x14004f81c`
- `0x140050490`
- `0x140050f88`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400063f4`
- `ntoskrnl!IofCompleteRequest` at `0x14000658b`
- `ntoskrnl!IofCompleteRequest` at `0x1400063f4`
- `ntoskrnl!IofCompleteRequest` at `0x14000658b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400063d7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400063d7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400063bd`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400063bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006326`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006326`

## pseudocode

```c
__int64 __fastcall NbtDispatchInternalCtrl(__int64 a1, __int64 a2)
{
  unsigned __int8 *v2; // r15
  KIRQL v5; // al
  char v6; // di
  unsigned __int8 v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int *v10; // r14
  unsigned int v11; // eax
  unsigned int v12; // esi
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // ecx
  unsigned int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // eax
  KIRQL Irql; // [rsp+80h] [rbp+8h] BYREF

  v2 = *(unsigned __int8 **)(a2 + 184);
  if ( v2[1] == 7 )
  {
    v12 = NTSend();
    if ( (BYTE3(xmmword_140038420) & 4) == 0 )
      return v12;
    v15 = 26;
    v16 = 1050;
    goto LABEL_19;
  }
  v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( a1 && *(_DWORD *)(a1 + 360) == 1131832644 )
  {
    _InterlockedAdd((volatile signed __int32 *)(a1 + 364), 1u);
    ++*(_DWORD *)(a1 + 1084);
    v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  KeReleaseSpinLock(&SpinLock, v5);
  if ( !v6 )
  {
    if ( (xmmword_140038420 & 4) != 0 )
      WPP_SF_qD(1026, 27, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, a1, *((_DWORD *)v2 + 6));
    v23 = -1073741436;
    *(_DWORD *)(a2 + 48) = -1073741436;
    IofCompleteRequest((PIRP)a2, 2);
    return v23;
  }
  v7 = v2[3];
  if ( (xmmword_140038420 & 4) != 0 )
    WPP_SF_dd(1026, 28, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, *v2, v2[1]);
  v8 = v2[1];
  if ( (unsigned int)v8 > 8 )
  {
    v14 = v8 - 9;
    if ( v14 )
    {
      v17 = (unsigned int)(v14 - 1);
      if ( !(_DWORD)v17 )
      {
        v12 = NTReceiveDatagram(v17, a2);
        NBT_DEREFERENCE_DEVICE(a1, 0);
        if ( (BYTE3(xmmword_140038420) & 0x20) == 0 )
          return v12;
        v15 = 38;
        v16 = 1053;
        goto LABEL_19;
      }
      v18 = (unsigned int)(v17 - 1);
      if ( !(_DWORD)v18 )
      {
        v10 = (unsigned int *)(a2 + 48);
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
        *(_DWORD *)(a2 + 48) = 259;
        *(_QWORD *)(a2 + 56) = 0;
        v11 = NTSetEventHandler(v18, a2);
        v12 = v11;
        if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
          goto LABEL_12;
        v19 = 41;
        goto LABEL_24;
      }
      v20 = v18 - 1;
      if ( v20 )
      {
        if ( v20 == 1 )
        {
          v10 = (unsigned int *)(a2 + 48);
          *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
          *(_DWORD *)(a2 + 48) = 259;
          *(_QWORD *)(a2 + 56) = 0;
          v11 = NTSetInformation();
          v12 = v11;
          if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
            goto LABEL_12;
          v19 = 42;
          goto LABEL_24;
        }
        goto LABEL_58;
      }
      v12 = NTQueryInformation(a1, a2);
      NBT_DEREFERENCE_DEVICE(a1, 0);
      if ( SBYTE2(xmmword_140038420) < 0 )
      {
        v15 = 36;
LABEL_30:
        v16 = 1047;
        goto LABEL_19;
      }
    }
    else
    {
      v12 = NTSendDatagram(a1, a2);
      NBT_DEREFERENCE_DEVICE(a1, 0);
      if ( (BYTE3(xmmword_140038420) & 0x10) != 0 )
      {
        v15 = 40;
        v16 = 1052;
LABEL_19:
        WPP_SF_qD(v16, v15, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, a2, v12);
      }
    }
    return v12;
  }
  if ( (_DWORD)v8 == 8 )
  {
    v26 = NTReceive(v8, a2);
    v12 = v26;
    if ( (BYTE3(xmmword_140038420) & 8) != 0 )
      WPP_SF_qD(1051, 37, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, a2, v26);
    v10 = (unsigned int *)(a2 + 48);
    goto LABEL_12;
  }
  v9 = (unsigned int)(v8 - 1);
  if ( !(_DWORD)v9 )
  {
    v10 = (unsigned int *)(a2 + 48);
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_DWORD *)(a2 + 48) = 259;
    *(_QWORD *)(a2 + 56) = 0;
    v11 = NTAssocAddress(v9, a2);
    v12 = v11;
    if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
    {
LABEL_12:
      if ( v12 != 259 )
      {
        v2[3] = v7;
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0);
        IoReleaseCancelSpinLock(Irql);
        *v10 = v12;
        IofCompleteRequest((PIRP)a2, v12 == 0 ? 2 : 0);
      }
      NBT_DEREFERENCE_DEVICE(a1, 0);
      return v12;
    }
    v19 = 30;
LABEL_24:
    WPP_SF_qD(1047, v19, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, a2, v11);
    goto LABEL_12;
  }
  v21 = (unsigned int)(v9 - 1);
  if ( !(_DWORD)v21 )
  {
    v10 = (unsigned int *)(a2 + 48);
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_DWORD *)(a2 + 48) = 259;
    *(_QWORD *)(a2 + 56) = 0;
    v11 = NTDisAssociateAddress(v21, a2);
    v12 = v11;
    if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
      goto LABEL_12;
    v19 = 31;
    goto LABEL_24;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v10 = (unsigned int *)(a2 + 48);
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_DWORD *)(a2 + 48) = 259;
    *(_QWORD *)(a2 + 56) = 0;
    v11 = NTConnect(a1, a2);
    v12 = v11;
    if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
      goto LABEL_12;
    v19 = 32;
    goto LABEL_24;
  }
  v24 = (unsigned int)(v22 - 1);
  if ( !(_DWORD)v24 )
  {
    v12 = NTListen(v24, a2);
    NBT_DEREFERENCE_DEVICE(a1, 0);
    if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
      return v12;
    v15 = 34;
    goto LABEL_30;
  }
  v25 = (unsigned int)(v24 - 1);
  if ( !(_DWORD)v25 )
  {
    v10 = (unsigned int *)(a2 + 48);
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_DWORD *)(a2 + 48) = 259;
    *(_QWORD *)(a2 + 56) = 0;
    v11 = NTAccept(v25, a2);
    v12 = v11;
    if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
      goto LABEL_12;
    v19 = 29;
    goto LABEL_24;
  }
  if ( (_DWORD)v25 == 1 )
  {
    v10 = (unsigned int *)(a2 + 48);
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *(_DWORD *)(a2 + 48) = 259;
    *(_QWORD *)(a2 + 56) = 0;
    v11 = NTDisconnect(v25, a2);
    v12 = v11;
    if ( (SBYTE2(xmmword_140038420) & 0x80u) == 0 )
      goto LABEL_12;
    v19 = 33;
    goto LABEL_24;
  }
LABEL_58:
  if ( SBYTE2(xmmword_140038420) < 0 )
    WPP_SF_q(1047, 45, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, a2);
  if ( (xmmword_140038420 & 4) != 0 )
    WPP_SF_d(1026, 46, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, v2[1]);
  v23 = -1073741808;
  ReturnIrp((PIRP)a2);
  NBT_DEREFERENCE_DEVICE(a1, 0);
  return v23;
}

```

## disassembly

```asm
0x1400062b0  push    rbx
0x1400062b2  push    rbp
0x1400062b3  push    rsi
0x1400062b4  push    rdi
0x1400062b5  push    r12
0x1400062b7  push    r13
0x1400062b9  push    r14
0x1400062bb  push    r15
0x1400062bd  sub     rsp, 38h
0x1400062c1  mov     r15, [rdx+0B8h]
0x1400062c8  mov     rbx, rdx
0x1400062cb  mov     rbp, rcx
0x1400062ce  cmp     byte ptr [r15+1], 7
0x1400062d3  jz      loc_1400064BB
0x1400062d9  lea     rcx, SpinLock; SpinLock
0x1400062e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062e7  nop     dword ptr [rax+rax+00h]
0x1400062ec  xor     r13d, r13d
0x1400062ef  mov     esi, 1
0x1400062f4  test    rbp, rbp
0x1400062f7  jz      loc_140006523
0x1400062fd  cmp     dword ptr [rbp+168h], 43766544h
0x140006307  jnz     loc_140006523
0x14000630d  lock add [rbp+16Ch], esi
0x140006314  add     [rbp+43Ch], esi
0x14000631a  mov     dil, sil
0x14000631d  mov     dl, al; NewIrql
0x14000631f  lea     rcx, SpinLock; SpinLock
0x140006326  call    cs:__imp_KeReleaseSpinLock
0x14000632d  nop     dword ptr [rax+rax+00h]
0x140006332  test    dil, dil
0x140006335  jz      loc_140006575
0x14000633b  mov     r12b, [r15+3]
0x14000633f  test    byte ptr cs:xmmword_140038420, 4
0x140006346  lea     rdi, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14000634d  jnz     loc_1400065C1
0x140006353  movzx   ecx, byte ptr [r15+1]
0x140006358  mov     edx, 103h
0x14000635d  cmp     ecx, 8
0x140006360  ja      loc_140006421
0x140006366  jz      loc_1400066D2
0x14000636c  sub     ecx, esi
0x14000636e  jnz     loc_14000652B
0x140006374  mov     rax, [rbx+0B8h]
0x14000637b  lea     r14, [rbx+30h]
0x14000637f  or      [rax+3], sil
0x140006383  mov     [r14], edx
0x140006386  mov     rdx, rbx
0x140006389  mov     [rbx+38h], r13
0x14000638d  call    NTAssocAddress
0x140006392  mov     esi, eax
0x140006394  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x14000639b  jl      loc_1400066C8
0x1400063a1  cmp     esi, 103h
0x1400063a7  jz      short loc_140006400
0x1400063a9  lea     rcx, [rsp+78h+Irql]; Irql
0x1400063b1  mov     [r15+3], r12b
0x1400063b5  mov     [rsp+78h+Irql], r13b
0x1400063bd  call    cs:__imp_IoAcquireCancelSpinLock
0x1400063c4  nop     dword ptr [rax+rax+00h]
0x1400063c9  mov     rax, r13
0x1400063cc  xchg    rax, [rbx+68h]
0x1400063d0  mov     cl, [rsp+78h+Irql]; Irql
0x1400063d7  call    cs:__imp_IoReleaseCancelSpinLock
0x1400063de  nop     dword ptr [rax+rax+00h]
0x1400063e3  mov     eax, esi
0x1400063e5  mov     [r14], esi
0x1400063e8  neg     eax
0x1400063ea  mov     rcx, rbx; Irp
0x1400063ed  sbb     dl, dl
0x1400063ef  not     dl
0x1400063f1  and     dl, 2; PriorityBoost
0x1400063f4  call    cs:__imp_IofCompleteRequest
0x1400063fb  nop     dword ptr [rax+rax+00h]
0x140006400  xor     r8d, r8d
0x140006403  xor     edx, edx
0x140006405  mov     rcx, rbp
0x140006408  call    NBT_DEREFERENCE_DEVICE
0x14000640d  mov     eax, esi
0x14000640f  add     rsp, 38h
0x140006413  pop     r15
0x140006415  pop     r14
0x140006417  pop     r13
0x140006419  pop     r12
0x14000641b  pop     rdi
0x14000641c  pop     rsi
0x14000641d  pop     rbp
0x14000641e  pop     rbx
0x14000641f  retn
0x140006421  sub     ecx, 9
0x140006424  jnz     short loc_140006464
0x140006426  mov     rdx, rbx
0x140006429  mov     rcx, rbp
0x14000642c  call    NTSendDatagram
0x140006431  xor     r8d, r8d
0x140006434  xor     edx, edx
0x140006436  mov     rcx, rbp
0x140006439  mov     esi, eax
0x14000643b  call    NBT_DEREFERENCE_DEVICE
0x140006440  test    byte ptr cs:xmmword_140038420+3, 10h
0x140006447  jz      short loc_14000640D
0x140006449  mov     edx, 28h ; '('
0x14000644e  mov     ecx, 41Ch
0x140006453  mov     r8, rdi
0x140006456  mov     r9, rbx
0x140006459  mov     [rsp+78h+var_58], esi
0x14000645d  call    WPP_SF_qD
0x140006462  jmp     short loc_14000640D
0x140006464  sub     ecx, esi
0x140006466  jz      loc_14000679E
0x14000646c  sub     ecx, esi
0x14000646e  jnz     short loc_1400064E5
0x140006470  mov     rax, [rbx+0B8h]
0x140006477  lea     r14, [rbx+30h]
0x14000647b  or      [rax+3], sil
0x14000647f  mov     [r14], edx
0x140006482  mov     rdx, rbx
0x140006485  mov     [rbx+38h], r13
0x140006489  call    NTSetEventHandler
0x14000648e  mov     esi, eax
0x140006490  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x140006497  jge     loc_1400063A1
0x14000649d  mov     edx, 29h ; ')'
0x1400064a2  mov     r9, rbx
0x1400064a5  mov     [rsp+78h+var_58], eax
0x1400064a9  mov     r8, rdi
0x1400064ac  mov     ecx, 417h
0x1400064b1  call    WPP_SF_qD
0x1400064b6  jmp     loc_1400063A1
0x1400064bb  call    NTSend
0x1400064c0  mov     esi, eax
0x1400064c2  test    byte ptr cs:xmmword_140038420+3, 4
0x1400064c9  jz      loc_14000640D
0x1400064cf  mov     edx, 1Ah
0x1400064d4  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x1400064db  mov     ecx, 41Ah
0x1400064e0  jmp     loc_140006456
0x1400064e5  sub     ecx, esi
0x1400064e7  jnz     loc_140006707
0x1400064ed  mov     rdx, rbx
0x1400064f0  mov     rcx, rbp
0x1400064f3  call    NTQueryInformation
0x1400064f8  xor     r8d, r8d
0x1400064fb  xor     edx, edx
0x1400064fd  mov     rcx, rbp
0x140006500  mov     esi, eax
0x140006502  call    NBT_DEREFERENCE_DEVICE
0x140006507  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x14000650e  jge     loc_14000640D
0x140006514  mov     edx, 24h ; '$'
0x140006519  mov     ecx, 417h
0x14000651e  jmp     loc_140006453
0x140006523  mov     dil, r13b
0x140006526  jmp     loc_14000631D
0x14000652b  sub     ecx, esi
0x14000652d  jz      loc_140006691
0x140006533  sub     ecx, esi
0x140006535  jnz     loc_1400065E5
0x14000653b  mov     rax, [rbx+0B8h]
0x140006542  lea     r14, [rbx+30h]
0x140006546  mov     rcx, rbp
0x140006549  or      [rax+3], sil
0x14000654d  mov     [r14], edx
0x140006550  mov     rdx, rbx
0x140006553  mov     [rbx+38h], r13
0x140006557  call    NTConnect
0x14000655c  mov     esi, eax
0x14000655e  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x140006565  jge     loc_1400063A1
0x14000656b  mov     edx, 20h ; ' '
0x140006570  jmp     loc_1400064A2
0x140006575  test    byte ptr cs:xmmword_140038420, 4
0x14000657c  jnz     short loc_14000659E
0x14000657e  mov     edi, 0C0000184h
0x140006583  mov     dl, 2; PriorityBoost
0x140006585  mov     rcx, rbx; Irp
0x140006588  mov     [rbx+30h], edi
0x14000658b  call    cs:__imp_IofCompleteRequest
0x140006592  nop     dword ptr [rax+rax+00h]
0x140006597  mov     eax, edi
0x140006599  jmp     loc_14000640F
0x14000659e  mov     eax, [r15+18h]
0x1400065a2  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x1400065a9  mov     edx, 1Bh
0x1400065ae  mov     [rsp+78h+var_58], eax
0x1400065b2  mov     ecx, 402h
0x1400065b7  mov     r9, rbp
0x1400065ba  call    WPP_SF_qD
0x1400065bf  jmp     short loc_14000657E
0x1400065c1  movzx   eax, byte ptr [r15+1]
0x1400065c6  mov     edx, 1Ch
0x1400065cb  movzx   r9d, byte ptr [r15]
0x1400065cf  mov     ecx, 402h
0x1400065d4  mov     r8, rdi
0x1400065d7  mov     [rsp+78h+var_58], eax
0x1400065db  call    WPP_SF_dd
0x1400065e0  jmp     loc_140006353
0x1400065e5  sub     ecx, esi
0x1400065e7  jz      short loc_140006663
0x1400065e9  sub     ecx, esi
0x1400065eb  jz      short loc_14000662C
0x1400065ed  cmp     ecx, esi
0x1400065ef  jnz     loc_14000673F
0x1400065f5  mov     rax, [rbx+0B8h]
0x1400065fc  lea     r14, [rbx+30h]
0x140006600  or      [rax+3], sil
0x140006604  mov     [r14], edx
0x140006607  mov     rdx, rbx
0x14000660a  mov     [rbx+38h], r13
0x14000660e  call    NTDisconnect
0x140006613  mov     esi, eax
0x140006615  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x14000661c  jge     loc_1400063A1
0x140006622  mov     edx, 21h ; '!'
0x140006627  jmp     loc_1400064A2
0x14000662c  mov     rax, [rbx+0B8h]
0x140006633  lea     r14, [rbx+30h]
0x140006637  or      [rax+3], sil
0x14000663b  mov     [r14], edx
0x14000663e  mov     rdx, rbx
0x140006641  mov     [rbx+38h], r13
0x140006645  call    NTAccept
0x14000664a  mov     esi, eax
0x14000664c  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x140006653  jge     loc_1400063A1
0x140006659  mov     edx, 1Dh
0x14000665e  jmp     loc_1400064A2
0x140006663  mov     rdx, rbx
0x140006666  call    NTListen
0x14000666b  xor     r8d, r8d
0x14000666e  xor     edx, edx
0x140006670  mov     rcx, rbp
0x140006673  mov     esi, eax
0x140006675  call    NBT_DEREFERENCE_DEVICE
0x14000667a  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x140006681  jge     loc_14000640D
0x140006687  mov     edx, 22h ; '"'
0x14000668c  jmp     loc_140006519
0x140006691  mov     rax, [rbx+0B8h]
0x140006698  lea     r14, [rbx+30h]
0x14000669c  or      [rax+3], sil
0x1400066a0  mov     [r14], edx
0x1400066a3  mov     rdx, rbx
0x1400066a6  mov     [rbx+38h], r13
0x1400066aa  call    NTDisAssociateAddress
0x1400066af  mov     esi, eax
0x1400066b1  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x1400066b8  jge     loc_1400063A1
0x1400066be  mov     edx, 1Fh
0x1400066c3  jmp     loc_1400064A2
0x1400066c8  mov     edx, 1Eh
0x1400066cd  jmp     loc_1400064A2
0x1400066d2  mov     rdx, rbx
0x1400066d5  call    NTReceive
0x1400066da  mov     esi, eax
0x1400066dc  test    byte ptr cs:xmmword_140038420+3, 8
0x1400066e3  jz      short loc_1400066FE
0x1400066e5  mov     edx, 25h ; '%'
0x1400066ea  mov     [rsp+78h+var_58], eax
0x1400066ee  mov     ecx, 41Bh
0x1400066f3  mov     r9, rbx
0x1400066f6  mov     r8, rdi
0x1400066f9  call    WPP_SF_qD
0x1400066fe  lea     r14, [rbx+30h]
0x140006702  jmp     loc_1400063A1
0x140006707  cmp     ecx, esi
0x140006709  jnz     short loc_14000673F
0x14000670b  mov     rax, [rbx+0B8h]
0x140006712  lea     r14, [rbx+30h]
0x140006716  or      [rax+3], sil
0x14000671a  mov     [r14], edx
0x14000671d  mov     [rbx+38h], r13
0x140006721  call    NTSetInformation
0x140006726  mov     esi, eax
0x140006728  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x14000672f  jge     loc_1400063A1
0x140006735  mov     edx, 2Ah ; '*'
0x14000673a  jmp     loc_1400064A2
0x14000673f  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x140006746  jge     short loc_14000675D
0x140006748  mov     edx, 2Dh ; '-'
0x14000674d  mov     ecx, 417h
0x140006752  mov     r9, rbx
0x140006755  mov     r8, rdi
0x140006758  call    WPP_SF_q
0x14000675d  test    byte ptr cs:xmmword_140038420, 4
0x140006764  jz      short loc_14000677D
0x140006766  movzx   r9d, byte ptr [r15+1]
0x14000676b  mov     edx, 2Eh ; '.'
0x140006770  mov     ecx, 402h
0x140006775  mov     r8, rdi
0x140006778  call    WPP_SF_d
0x14000677d  mov     edi, 0C0000010h
0x140006782  mov     rcx, rbx; Irp
0x140006785  mov     edx, edi
0x140006787  call    ReturnIrp
0x14000678c  xor     r8d, r8d
0x14000678f  xor     edx, edx
0x140006791  mov     rcx, rbp
0x140006794  call    NBT_DEREFERENCE_DEVICE
  ... truncated ...
```
