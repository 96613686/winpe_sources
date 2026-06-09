# Smb2Create_Finalize

- ea: `0x140007020`
- end: `0x14000745b`
- name: `Smb2Create_Finalize`
- size: `1083`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140005820`
- `0x140006cd0`
- `0x140007020`
- `0x140007470`
- `0x1400122d0`
- `0x140013210`
- `0x140029840`
- `0x140029f30`
- `0x14002a1dc`
- `0x14002a304`
- `0x140037120`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007375`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007375`
- `mrxsmb!RDR_PERF_ENTER` at `0x1400070c7`
- `mrxsmb!RDR_PERF_ENTER` at `0x1400070c7`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400072b5`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400072b5`

## pseudocode

```c
__int64 __fastcall Smb2Create_Finalize(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rsi
  bool v4; // zf
  _QWORD *v5; // rdx
  _QWORD *v6; // r15
  __int64 v7; // rbx
  __int64 v8; // r12
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int SuccessCompletion; // edi
  __int64 v14; // r14
  unsigned __int64 v15; // r9
  char v16; // cl
  __int64 v17; // rbx
  __int64 v18; // rbp
  int v19; // eax
  __int64 v20; // r9
  int v21; // ecx
  __int64 v22; // rcx
  __int64 v24; // rdi
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rbx
  KIRQL v28; // r12
  __int64 v29; // rax
  char v30; // al
  int v31; // r8d
  __int64 v32; // [rsp+40h] [rbp-88h]
  __int64 v33; // [rsp+48h] [rbp-80h]
  __int64 v34; // [rsp+50h] [rbp-78h]
  __int64 v35; // [rsp+58h] [rbp-70h]
  __int128 v36; // [rsp+60h] [rbp-68h] BYREF
  __int128 v37; // [rsp+70h] [rbp-58h]
  __int128 v38; // [rsp+80h] [rbp-48h]
  __int64 v39; // [rsp+90h] [rbp-38h]

  v5 = (_QWORD *)(a1 + 160);
  v2 = *(_QWORD *)(a1 + 160);
  v3 = 0;
  v4 = *v5 == (_QWORD)v5;
  LOBYTE(v5) = 18;
  v6 = *(_QWORD **)(a1 + 48);
  v7 = *(_QWORD *)(a1 + 16);
  if ( !v4 )
    v3 = v2 - 8;
  v32 = *(_QWORD *)(a1 + 16);
  v8 = v6[9];
  v35 = v6[7];
  v34 = v8;
  v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL) + 424LL) + 88LL);
  v10 = *(_QWORD *)(a1 + 88);
  v36 = 0;
  v33 = v10;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  RDR_PERF_ENTER(a1 + 512, v5);
  if ( *(int *)(a1 + 16) >= 0 && v3 )
  {
    v7 = *(_QWORD *)(v3 + 48);
    LODWORD(v32) = v7;
  }
  SuccessCompletion = v32;
  if ( (int)v32 < 0 )
  {
    Smb2CompleteSrvOpenInitialization(v8, 0, v7);
    goto LABEL_27;
  }
  v39 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v14 = *(_QWORD *)(v3 + 712);
  v15 = *(_QWORD *)(v14 + 40);
  if ( v15 > 0x7FFFFFFFFFFFFFFFLL || *(_QWORD *)(v14 + 48) > 0x7FFFFFFFFFFFFFFFuLL )
  {
    SuccessCompletion = -1073741629;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
        v15,
        *(_QWORD *)(v14 + 48));
    }
    goto LABEL_12;
  }
  v16 = *(_BYTE *)(v14 + 2);
  if ( v16 == -1 )
  {
    if ( (*(_DWORD *)(v9 + 716) & 0x20) == 0 )
    {
      SuccessCompletion = -1073741629;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
          *(_QWORD *)(a1 + 48),
          a1);
      }
      goto LABEL_12;
    }
  }
  else if ( ((unsigned __int8)(v16 - 8) <= 1u || v16 == 1) && (*(_DWORD *)(v35 + 156) & 0x10) != 0 )
  {
    SuccessCompletion = -1073741629;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
        *(_QWORD *)(a1 + 48),
        a1);
    }
    goto LABEL_12;
  }
  v20 = *(unsigned int *)(v14 + 84);
  v21 = 0;
  if ( !(_DWORD)v20 )
    goto LABEL_23;
  v22 = *(unsigned int *)(v14 + 80);
  if ( (unsigned int)v22 >= 0x98 )
  {
    v11 = (unsigned int)(*(_DWORD *)(v3 + 748) + 64);
    if ( (unsigned int)v22 <= (unsigned int)v11 && (unsigned int)v20 <= (unsigned int)v11 )
    {
      if ( ((v22 + 7) & 0xFFFFFFFFFFFFFFF8uLL) == v22 )
      {
        if ( (int)v22 + (int)v20 <= (unsigned int)v11 )
        {
          v21 = Smb2ValidateAndProcessEcpList(*(_QWORD *)(a1 + 48), &v36, v14 + (unsigned int)v22 - 64LL);
          goto LABEL_23;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
            *(_QWORD *)(a1 + 48),
            a1);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
          *(_QWORD *)(a1 + 48),
          a1);
        SuccessCompletion = -1073741629;
        goto LABEL_12;
      }
      SuccessCompletion = -1073741629;
      goto LABEL_12;
    }
  }
  SuccessCompletion = -1073741629;
  v21 = -1073741629;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
      *(_QWORD *)(a1 + 48),
      a1);
    goto LABEL_12;
  }
LABEL_23:
  SuccessCompletion = v21;
  if ( v21 < 0 )
    goto LABEL_26;
  if ( *(_BYTE *)(a1 + 2410) )
  {
    v27 = *(_QWORD *)(v33 + 24);
    v28 = SmbCeAcquireSpinLock(v27, v11, v12, v20);
    v29 = *(_QWORD *)(v33 + 416);
    if ( !*(_BYTE *)(v29 + 465) || *(_BYTE *)(v29 + 466) )
    {
      if ( *(_DWORD *)(v29 + 12) )
      {
        v25 = *(unsigned __int16 *)(v29 + 2);
        if ( (_WORD)v25 )
          v24 = v29 + v25;
        else
          v24 = 0;
        SuccessCompletion = *(_DWORD *)(v24 + 208);
      }
      else
      {
        *(_BYTE *)(v29 + 656) = 1;
      }
    }
    else
    {
      SuccessCompletion = -1073740776;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
          *(_QWORD *)(a1 + 48),
          -1073740776);
      }
    }
    *(_DWORD *)(v27 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v27 + 1920), v28);
    if ( SuccessCompletion < 0 )
    {
LABEL_42:
      v8 = v34;
      goto LABEL_12;
    }
    v8 = v34;
  }
  SuccessCompletion = Smb2CreateSuccessCompletion(v6, a1, v14, (__int64)&v36);
  if ( SuccessCompletion >= 0 )
  {
LABEL_26:
    if ( SuccessCompletion >= 0 )
      goto LABEL_27;
    goto LABEL_42;
  }
LABEL_12:
  v17 = *(_QWORD *)(v8 + 48);
  v18 = *(_QWORD *)(v35 + 136);
  *(_OWORD *)(v17 + 28) = *(_OWORD *)(v14 + 64);
  Smb2CompleteSrvOpenInitialization(v8, 0, 0);
  v19 = *(_DWORD *)(v17 + 8);
  if ( (v19 & 0x400) != 0 )
  {
    ++*(_DWORD *)(v18 + 76);
  }
  else if ( (v19 & 0x200) != 0 )
  {
    ++*(_DWORD *)(v18 + 72);
  }
  v30 = MRxSmb2Close(v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qZDDq(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)WPP_GLOBAL_Control,
      v31,
      v6[9],
      v6[7] + 360LL,
      SuccessCompletion,
      v30,
      (char)v6);
  }
LABEL_27:
  if ( v3 )
  {
    if ( SuccessCompletion == -2147483603 )
    {
      v26 = Smb2ProcessSymlinkReparseData((__int64)v6, v3);
      if ( v26 < 0 )
        SuccessCompletion = v26;
    }
    SmbCseFinalizeBufferContext(v3);
  }
  return (unsigned int)SuccessCompletion;
}

```

## disassembly

```asm
0x140007020  mov     r11, rsp
0x140007023  push    rsi
0x140007024  push    rdi
0x140007025  push    r15
0x140007027  sub     rsp, 0B0h
0x14000702e  mov     rax, cs:__security_cookie
0x140007035  xor     rax, rsp
0x140007038  mov     [rsp+0C8h+var_30], rax
0x140007040  lea     rdx, [rcx+0A0h]
0x140007047  mov     [r11+10h], rbx
0x14000704b  mov     [r11+18h], rbp
0x14000704f  xorps   xmm0, xmm0
0x140007052  mov     rbp, rcx
0x140007055  mov     [r11+20h], r12
0x140007059  mov     rcx, [rdx]
0x14000705c  xor     esi, esi
0x14000705e  cmp     rcx, rdx
0x140007061  mov     [r11-20h], r13
0x140007065  mov     dl, 12h
0x140007067  mov     r15, [rbp+30h]
0x14000706b  mov     rbx, [rbp+10h]
0x14000706f  lea     rax, [rcx-8]
0x140007073  cmovnz  rsi, rax
0x140007077  mov     [rsp+0C8h+var_88], rbx
0x14000707c  mov     r12, [r15+48h]
0x140007080  mov     rax, [r15+38h]
0x140007084  mov     [rsp+0C8h+var_70], rax
0x140007089  mov     [rsp+0C8h+var_78], r12
0x14000708e  mov     rax, [r12+28h]
0x140007093  mov     rcx, [rax+28h]
0x140007097  mov     rax, [rcx+1A8h]
0x14000709e  lea     rcx, [rbp+200h]
0x1400070a5  mov     r13, [rax+58h]
0x1400070a9  mov     rax, [rbp+58h]
0x1400070ad  movups  [rsp+0C8h+var_68], xmm0
0x1400070b2  mov     [rsp+0C8h+var_80], rax
0x1400070b7  xor     eax, eax
0x1400070b9  movups  [rsp+0C8h+var_58], xmm0
0x1400070be  mov     [r11-38h], rax
0x1400070c2  movups  xmmword ptr [r11-48h], xmm0
0x1400070c7  call    cs:__imp_RDR_PERF_ENTER
0x1400070ce  nop     dword ptr [rax+rax+00h]
0x1400070d3  cmp     dword ptr [rbp+10h], 0
0x1400070d7  jl      short loc_1400070E7
0x1400070d9  test    rsi, rsi
0x1400070dc  jz      short loc_1400070E7
0x1400070de  mov     rbx, [rsi+30h]
0x1400070e2  mov     [rsp+0C8h+var_88], rbx
0x1400070e7  mov     edi, dword ptr [rsp+0C8h+var_88]
0x1400070eb  test    edi, edi
0x1400070ed  js      loc_1400072E0
0x1400070f3  xorps   xmm0, xmm0
0x1400070f6  mov     [rsp+0C8h+var_28], r14
0x1400070fe  xor     eax, eax
0x140007100  mov     [rsp+0C8h+var_38], rax
0x140007108  mov     rax, 7FFFFFFFFFFFFFFFh
0x140007112  movups  [rsp+0C8h+var_68], xmm0
0x140007117  movups  [rsp+0C8h+var_58], xmm0
0x14000711c  movups  [rsp+0C8h+var_48], xmm0
0x140007124  mov     r14, [rsi+2C8h]
0x14000712b  mov     r9, [r14+28h]
0x14000712f  cmp     r9, rax
0x140007132  ja      loc_140038AD7
0x140007138  cmp     [r14+30h], rax
0x14000713c  ja      loc_140038AD7
0x140007142  movzx   ecx, byte ptr [r14+2]
0x140007147  cmp     cl, 0FFh
0x14000714a  jnz     short loc_1400071BA
0x14000714c  mov     eax, [r13+2CCh]
0x140007153  test    al, 20h
0x140007155  jnz     short loc_1400071CE
0x140007157  mov     edi, 0C00000C3h
0x14000715c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007163  lea     r13, WPP_GLOBAL_Control
0x14000716a  cmp     rcx, r13
0x14000716d  jnz     loc_1400073B2
0x140007173  mov     rax, [rsp+0C8h+var_70]
0x140007178  xor     edx, edx
0x14000717a  mov     rbx, [r12+30h]
0x14000717f  mov     rcx, r12
0x140007182  movups  xmm0, xmmword ptr [r14+40h]
0x140007187  mov     [rsp+0C8h+var_88], 0
0x140007190  mov     rbp, [rax+88h]
0x140007197  mov     r8, [rsp+0C8h+var_88]
0x14000719c  movups  xmmword ptr [rbx+1Ch], xmm0
0x1400071a0  call    Smb2CompleteSrvOpenInitialization
0x1400071a5  mov     eax, [rbx+8]
0x1400071a8  bt      eax, 0Ah
0x1400071ac  jnb     loc_140038B2E
0x1400071b2  inc     dword ptr [rbp+4Ch]
0x1400071b5  jmp     loc_140038B37
0x1400071ba  lea     eax, [rcx-8]
0x1400071bd  cmp     al, 1
0x1400071bf  jbe     loc_1400072EF
0x1400071c5  cmp     cl, 1
0x1400071c8  jz      loc_1400072EF
0x1400071ce  mov     r9d, [r14+54h]
0x1400071d2  lea     r13, WPP_GLOBAL_Control
0x1400071d9  xor     ecx, ecx
0x1400071db  test    r9d, r9d
0x1400071de  jz      short loc_140007241
0x1400071e0  mov     ecx, [r14+50h]
0x1400071e4  cmp     ecx, 98h
0x1400071ea  jb      loc_140007307
0x1400071f0  mov     edx, [rsi+2ECh]
0x1400071f6  add     edx, 40h ; '@'
0x1400071f9  cmp     ecx, edx
0x1400071fb  ja      loc_140007307
0x140007201  cmp     r9d, edx
0x140007204  ja      loc_140007307
0x14000720a  lea     rax, [rcx+7]
0x14000720e  mov     r8d, ecx
0x140007211  and     rax, 0FFFFFFFFFFFFFFF8h
0x140007215  cmp     rax, rcx
0x140007218  jnz     loc_1400389FD
0x14000721e  lea     eax, [rcx+r9]
0x140007222  cmp     eax, edx
0x140007224  ja      loc_1400073EA
0x14000722a  mov     rcx, [rbp+30h]
0x14000722e  lea     rdx, [rsp+0C8h+var_68]
0x140007233  add     r8, 0FFFFFFFFFFFFFFC0h
0x140007237  add     r8, r14
0x14000723a  call    Smb2ValidateAndProcessEcpList
0x14000723f  mov     ecx, eax
0x140007241  mov     edi, ecx
0x140007243  test    ecx, ecx
0x140007245  js      short loc_140007271
0x140007247  cmp     byte ptr [rbp+96Ah], 0
0x14000724e  jnz     loc_140038A4F
0x140007254  lea     r9, [rsp+0C8h+var_68]
0x140007259  mov     r8, r14
0x14000725c  mov     rdx, rbp
0x14000725f  mov     rcx, r15; pContext
0x140007262  call    Smb2CreateSuccessCompletion
0x140007267  mov     edi, eax
0x140007269  test    eax, eax
0x14000726b  js      loc_140007173
0x140007271  test    edi, edi
0x140007273  js      loc_14000738F
0x140007279  mov     r14, [rsp+0C8h+var_28]
0x140007281  mov     r13, [rsp+0C8h+var_20]
0x140007289  mov     r12, [rsp+0C8h+arg_18]
0x140007291  mov     rbp, [rsp+0C8h+arg_10]
0x140007299  mov     rbx, [rsp+0C8h+arg_8]
0x1400072a1  test    rsi, rsi
0x1400072a4  jz      short loc_1400072C1
0x1400072a6  cmp     edi, 8000002Dh
0x1400072ac  jz      loc_140007446
0x1400072b2  mov     rcx, rsi
0x1400072b5  call    cs:__imp_SmbCseFinalizeBufferContext
0x1400072bc  nop     dword ptr [rax+rax+00h]
0x1400072c1  mov     eax, edi
0x1400072c3  mov     rcx, [rsp+0C8h+var_30]
0x1400072cb  xor     rcx, rsp; StackCookie
0x1400072ce  call    __security_check_cookie
0x1400072d3  add     rsp, 0B0h
0x1400072da  pop     r15
0x1400072dc  pop     rdi
0x1400072dd  pop     rsi
0x1400072de  retn
0x1400072e0  mov     r8, rbx
0x1400072e3  xor     edx, edx
0x1400072e5  mov     rcx, r12
0x1400072e8  call    Smb2CompleteSrvOpenInitialization
0x1400072ed  jmp     short loc_140007281
0x1400072ef  mov     rax, [rsp+0C8h+var_70]
0x1400072f4  mov     eax, [rax+9Ch]
0x1400072fa  test    al, 10h
0x1400072fc  jz      loc_1400071CE
0x140007302  jmp     loc_1400389A8
0x140007307  mov     edi, 0C00000C3h
0x14000730c  mov     ecx, edi
0x14000730e  mov     r10, cs:WPP_GLOBAL_Control
0x140007315  cmp     r10, r13
0x140007318  jz      loc_140007241
0x14000731e  mov     eax, [r10+2Ch]
0x140007322  test    al, 1
0x140007324  jz      loc_140007241
0x14000732a  cmp     byte ptr [r10+29h], 1
0x14000732f  jb      loc_140007241
0x140007335  mov     r9, [rbp+30h]
0x140007339  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140007340  mov     rcx, [r10+18h]
0x140007344  mov     edx, 1Ah
0x140007349  mov     [rsp+0C8h+var_A8], rbp
0x14000734e  call    WPP_SF_qq
0x140007353  jmp     loc_140007173
0x140007358  xor     edi, edi
0x14000735a  mov     edi, [rdi+0D0h]
0x140007360  lea     rcx, [rbx+780h]; SpinLock
0x140007367  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140007371  movzx   edx, r12b; OldIrql
0x140007375  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000737c  nop     dword ptr [rax+rax+00h]
0x140007381  test    edi, edi
0x140007383  js      short loc_14000738F
0x140007385  mov     r12, [rsp+0C8h+var_78]
0x14000738a  jmp     loc_140007254
0x14000738f  mov     r12, [rsp+0C8h+var_78]
0x140007394  jmp     loc_140007173
0x140007399  cmp     dword ptr [rax+0Ch], 0
0x14000739d  jz      loc_14000743A
0x1400073a3  movzx   ecx, word ptr [rax+2]
0x1400073a7  test    cx, cx
0x1400073aa  jz      short loc_140007358
0x1400073ac  lea     rdi, [rax+rcx]
0x1400073b0  jmp     short loc_14000735A
0x1400073b2  mov     eax, [rcx+2Ch]
0x1400073b5  test    al, 1
0x1400073b7  jz      loc_140007173
0x1400073bd  cmp     byte ptr [rcx+29h], 1
0x1400073c1  jb      loc_140007173
0x1400073c7  mov     r9, [rbp+30h]
0x1400073cb  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x1400073d2  mov     rcx, [rcx+18h]
0x1400073d6  mov     edx, 1Eh
0x1400073db  mov     [rsp+0C8h+var_A8], rbp
0x1400073e0  call    WPP_SF_qq
0x1400073e5  jmp     loc_140007173
0x1400073ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073f1  lea     r13, WPP_GLOBAL_Control
0x1400073f8  cmp     rcx, r13
0x1400073fb  jz      loc_140038A45
0x140007401  mov     eax, [rcx+2Ch]
0x140007404  test    al, 1
0x140007406  jz      loc_140038A45
0x14000740c  cmp     byte ptr [rcx+29h], 1
0x140007410  jb      loc_140038A45
0x140007416  mov     r9, [rbp+30h]
0x14000741a  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140007421  mov     rcx, [rcx+18h]
0x140007425  mov     edx, 1Ch
0x14000742a  mov     [rsp+0C8h+var_A8], rbp
0x14000742f  call    WPP_SF_qq
0x140007434  nop
0x140007435  jmp     loc_140038A45
0x14000743a  mov     byte ptr [rax+290h], 1
0x140007441  jmp     loc_140007360
0x140007446  mov     rdx, rsi
0x140007449  mov     rcx, r15
0x14000744c  call    Smb2ProcessSymlinkReparseData
0x140007451  test    eax, eax
0x140007453  cmovs   edi, eax
0x140007456  jmp     loc_1400072B2
0x1400389a8  mov     edi, 0C00000C3h
0x1400389ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400389b4  lea     r13, WPP_GLOBAL_Control
0x1400389bb  cmp     rcx, r13
0x1400389be  jz      loc_140007173
0x1400389c4  mov     eax, [rcx+2Ch]
0x1400389c7  test    al, 1
0x1400389c9  jz      loc_140007173
0x1400389cf  cmp     byte ptr [rcx+29h], 1
0x1400389d3  jb      loc_140007173
0x1400389d9  mov     r9, [rbp+30h]
0x1400389dd  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x1400389e4  mov     rcx, [rcx+18h]
0x1400389e8  mov     edx, 1Fh
0x1400389ed  mov     [rsp+0C8h+var_A8], rbp
0x1400389f2  call    WPP_SF_qq
0x1400389f7  nop
0x1400389f8  jmp     loc_140007173
0x1400389fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a04  lea     r13, WPP_GLOBAL_Control
0x140038a0b  cmp     rcx, r13
0x140038a0e  jz      short loc_140038A45
0x140038a10  mov     eax, [rcx+2Ch]
0x140038a13  test    al, 1
0x140038a15  jz      short loc_140038A45
0x140038a17  cmp     byte ptr [rcx+29h], 1
0x140038a1b  jb      short loc_140038A45
0x140038a1d  mov     r9, [rbp+30h]
0x140038a21  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140038a28  mov     rcx, [rcx+18h]
0x140038a2c  mov     edx, 1Bh
0x140038a31  mov     [rsp+0C8h+var_A8], rbp
0x140038a36  call    WPP_SF_qq
0x140038a3b  mov     edi, 0C00000C3h
0x140038a40  jmp     loc_140007173
0x140038a45  mov     edi, 0C00000C3h
0x140038a4a  jmp     loc_140007173
0x140038a4f  mov     rbx, [rsp+0C8h+var_80]
0x140038a54  mov     rbx, [rbx+18h]
0x140038a58  mov     rcx, rbx
0x140038a5b  call    SmbCeAcquireSpinLock
0x140038a60  movzx   r12d, al
0x140038a64  mov     rax, [rsp+0C8h+var_80]
0x140038a69  mov     rax, [rax+1A0h]
0x140038a70  cmp     byte ptr [rax+1D1h], 0
0x140038a77  jz      loc_140007399
0x140038a7d  cmp     byte ptr [rax+1D2h], 0
0x140038a84  jnz     loc_140007399
0x140038a8a  mov     edi, 0C0000418h
0x140038a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a96  cmp     rcx, r13
0x140038a99  jz      loc_140007360
0x140038a9f  mov     eax, [rcx+2Ch]
0x140038aa2  test    al, 1
0x140038aa4  jz      loc_140007360
0x140038aaa  cmp     byte ptr [rcx+29h], 1
  ... truncated ...
```
