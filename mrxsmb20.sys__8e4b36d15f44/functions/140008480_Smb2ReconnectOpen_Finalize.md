# Smb2ReconnectOpen_Finalize

- ea: `0x140008480`
- end: `0x1400087ac`
- name: `Smb2ReconnectOpen_Finalize`
- size: `812`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007470`
- `0x140008480`
- `0x1400087c0`
- `0x140029b64`
- `0x14002a1dc`

## import_xrefs

- `rdbss!RxIndicateChangeOfOplockState` at `0x14000868b`
- `rdbss!RxIndicateChangeOfOplockState` at `0x14000868b`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x140038d74`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x140038d74`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140008621`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140008621`

## pseudocode

```c
__int64 __fastcall Smb2ReconnectOpen_Finalize(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  struct _RX_CONTEXT *v3; // rbp
  __int64 v5; // rdi
  PMRX_SRV_OPEN pRelevantSrvOpen; // rsi
  PMRX_FCB pFcb; // r12
  __int64 v8; // r13
  __int64 v9; // r14
  ULONGLONG ActualAllocationLength; // r11
  int v11; // ecx
  unsigned int v12; // r9d
  int v13; // r15d
  __int64 v14; // rcx
  unsigned int v15; // edx
  int v16; // eax
  unsigned int v18; // ecx
  unsigned int v19; // edx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  char v22; // r8
  unsigned __int16 v23; // dx
  __int16 v24; // cx
  _OWORD v25[2]; // [rsp+30h] [rbp-78h] BYREF
  __int128 v26; // [rsp+50h] [rbp-58h]
  __int64 v27; // [rsp+60h] [rbp-48h]
  char v28; // [rsp+B0h] [rbp+8h]
  ULONGLONG v29; // [rsp+C0h] [rbp+18h]

  v1 = *(_QWORD *)(a1 + 16);
  v2 = *(_QWORD *)(a1 + 160);
  v3 = *(struct _RX_CONTEXT **)(a1 + 48);
  v5 = v2 - 8;
  if ( v2 == a1 + 160 )
    v5 = 0;
  if ( (int)v1 >= 0 )
  {
    if ( !v5 )
      goto LABEL_8;
    v1 = *(_QWORD *)(v5 + 48);
  }
  if ( (_DWORD)v1 == -2147483603 )
    LODWORD(v1) = -1073741766;
LABEL_8:
  if ( *(_BYTE *)(a1 + 2416) || (pRelevantSrvOpen = v3->pRelevantSrvOpen, (int)v1 < 0) )
  {
    if ( v5 )
      goto LABEL_25;
  }
  else if ( v5 )
  {
    pFcb = v3->pFcb;
    v8 = *(_QWORD *)&pRelevantSrvOpen->Flags;
    v9 = *(_QWORD *)(v5 + 712);
    ActualAllocationLength = pFcb->ActualAllocationLength;
    v11 = *(_DWORD *)(v8 + 8);
    v28 = v11;
    v29 = ActualAllocationLength;
    if ( v9 )
      *(_OWORD *)(v8 + 28) = *(_OWORD *)(v9 + 64);
    v12 = *(_DWORD *)(v9 + 84);
    v27 = 0;
    v13 = 0;
    memset(v25, 0, sizeof(v25));
    v26 = 0;
    if ( !v12 )
    {
LABEL_21:
      if ( v13 >= 0 && (v11 & 4) != 0 )
      {
        v18 = *(unsigned __int8 *)(v9 + 2);
        v19 = *(_DWORD *)(v8 + 24);
        if ( (_BYTE)v18 == 0xFF )
        {
          if ( v19 == 255 )
          {
            if ( (v25[0] & 8) != 0 )
            {
              if ( (v22 = BYTE4(v26), v23 = WORD4(v26), (v25[0] & 0x10) != 0)
                && (v24 = *(_WORD *)(ActualAllocationLength + 68), (unsigned __int16)(WORD4(v26) - v24) <= 0x7FFFu)
                && WORD4(v26) != v24
                || (DWORD1(v26) & *(_DWORD *)(ActualAllocationLength + 64)) != *(_DWORD *)(ActualAllocationLength + 64) )
              {
                *(_BYTE *)(ActualAllocationLength + 80) = 1;
                RxIndicateChangeOfOplockStateForTarget(
                  *(_QWORD *)(*(_QWORD *)&pFcb->UncleanCount + 32LL),
                  pFcb,
                  0,
                  v22 & 0x1F | (unsigned __int64)(32 * (unsigned int)v23));
              }
            }
            goto LABEL_25;
          }
        }
        else if ( v19 != 255 )
        {
          if ( v19 > v18 )
            RxIndicateChangeOfOplockState(
              *(_QWORD *)(*(_QWORD *)&pFcb->UncleanCount + 32LL),
              &pRelevantSrvOpen->SrvOpenQLinks,
              0,
              *(unsigned __int8 *)(v9 + 2));
          goto LABEL_25;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDZ(
            WPP_GLOBAL_Control->AttachedDevice,
            48,
            (unsigned int)WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
            (_DWORD)pRelevantSrvOpen,
            195,
            *(_QWORD *)&pRelevantSrvOpen->DesiredAccess);
        }
      }
LABEL_25:
      SmbCseFinalizeBufferContext(v5);
      goto LABEL_26;
    }
    v14 = *(unsigned int *)(v9 + 80);
    if ( (unsigned int)v14 >= 0x98 )
    {
      v15 = *(_DWORD *)(v5 + 748) + 64;
      if ( (unsigned int)v14 <= v15 && v12 <= v15 )
      {
        if ( ((v14 + 7) & 0xFFFFFFFFFFFFFFF8uLL) == v14 )
        {
          if ( (unsigned int)v14 + v12 <= v15 )
          {
            v16 = Smb2ValidateAndProcessEcpList(
                    *(_QWORD *)(a1 + 48),
                    (__int64)v25,
                    (unsigned int *)(v9 + (unsigned int)v14 - 64LL),
                    v12);
            ActualAllocationLength = v29;
            v13 = v16;
LABEL_20:
            LOBYTE(v11) = v28;
            goto LABEL_21;
          }
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_25;
          }
          v21 = 28;
        }
        else
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            goto LABEL_25;
          }
          v21 = 27;
        }
        WPP_SF_qq(v20->AttachedDevice, v21, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, *(_QWORD *)(a1 + 48), a1);
        goto LABEL_25;
      }
    }
    v13 = -1073741629;
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
      goto LABEL_25;
    }
    goto LABEL_20;
  }
LABEL_26:
  Smb2CompleteSrvOpenReconnectionCallback(v3);
  return 0;
}

```

## disassembly

```asm
0x140008480  push    rbx
0x140008482  push    rbp
0x140008483  push    rsi
0x140008484  push    rdi
0x140008485  sub     rsp, 88h
0x14000848c  mov     rbx, [rcx+10h]
0x140008490  lea     r8, [rcx+0A0h]
0x140008497  mov     rdx, [r8]
0x14000849a  xor     eax, eax
0x14000849c  mov     rbp, [rcx+30h]
0x1400084a0  cmp     rdx, r8
0x1400084a3  mov     r10, rcx
0x1400084a6  mov     [rsp+0A8h+arg_8], rbx
0x1400084ae  lea     rdi, [rdx-8]
0x1400084b2  cmovz   rdi, rax
0x1400084b6  xor     esi, esi
0x1400084b8  test    ebx, ebx
0x1400084ba  js      short loc_1400084CD
0x1400084bc  test    rdi, rdi
0x1400084bf  jz      short loc_1400084DA
0x1400084c1  mov     rbx, [rdi+30h]
0x1400084c5  mov     [rsp+0A8h+arg_8], rbx
0x1400084cd  cmp     ebx, 8000002Dh
0x1400084d3  jnz     short loc_1400084DA
0x1400084d5  mov     ebx, 0C000003Ah
0x1400084da  cmp     [rcx+970h], al
0x1400084e0  jnz     loc_140008619
0x1400084e6  mov     rsi, [rbp+48h]
0x1400084ea  test    ebx, ebx
0x1400084ec  js      loc_140008619
0x1400084f2  test    rdi, rdi
0x1400084f5  jz      loc_14000862D
0x1400084fb  mov     [rsp+0A8h+arg_18], r12
0x140008503  mov     r12, [rbp+38h]
0x140008507  mov     [rsp+0A8h+var_28], r13
0x14000850f  mov     r13, [rsi+30h]
0x140008513  mov     [rsp+0A8h+var_30], r14
0x140008518  mov     r14, [rdi+2C8h]
0x14000851f  mov     r11, [r12+88h]
0x140008527  mov     ecx, [r13+8]
0x14000852b  mov     [rsp+0A8h+arg_0], ecx
0x140008532  mov     [rsp+0A8h+arg_10], r11
0x14000853a  mov     [rsp+0A8h+var_38], r15
0x14000853f  test    r14, r14
0x140008542  jz      short loc_14000854E
0x140008544  movups  xmm0, xmmword ptr [r14+40h]
0x140008549  movups  xmmword ptr [r13+1Ch], xmm0
0x14000854e  mov     r9d, [r14+54h]
0x140008552  lea     r8, WPP_GLOBAL_Control
0x140008559  xorps   xmm0, xmm0
0x14000855c  mov     [rsp+0A8h+var_48], rax
0x140008561  xor     r15d, r15d
0x140008564  movups  [rsp+0A8h+var_78], xmm0
0x140008569  movups  [rsp+0A8h+var_68], xmm0
0x14000856e  movups  [rsp+0A8h+var_58], xmm0
0x140008573  test    r9d, r9d
0x140008576  jz      short loc_1400085F0
0x140008578  mov     ecx, [r14+50h]
0x14000857c  cmp     ecx, 98h
0x140008582  jb      loc_14000869C
0x140008588  mov     edx, [rdi+2ECh]
0x14000858e  add     edx, 40h ; '@'
0x140008591  cmp     ecx, edx
0x140008593  ja      loc_14000869C
0x140008599  cmp     r9d, edx
0x14000859c  ja      loc_14000869C
0x1400085a2  lea     rax, [rcx+7]
0x1400085a6  mov     r8d, ecx
0x1400085a9  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400085ad  cmp     rax, rcx
0x1400085b0  jnz     loc_1400086ED
0x1400085b6  lea     eax, [rcx+r9]
0x1400085ba  cmp     eax, edx
0x1400085bc  ja      loc_140008723
0x1400085c2  mov     rcx, [r10+30h]
0x1400085c6  lea     rdx, [rsp+0A8h+var_78]
0x1400085cb  add     r8, 0FFFFFFFFFFFFFFC0h
0x1400085cf  add     r8, r14
0x1400085d2  call    Smb2ValidateAndProcessEcpList
0x1400085d7  mov     r11, [rsp+0A8h+arg_10]
0x1400085df  lea     r8, WPP_GLOBAL_Control
0x1400085e6  mov     r15d, eax
0x1400085e9  mov     ecx, [rsp+0A8h+arg_0]
0x1400085f0  mov     ebx, r15d
0x1400085f3  test    r15d, r15d
0x1400085f6  js      short loc_1400085FD
0x1400085f8  test    cl, 4
0x1400085fb  jnz     short loc_140008656
0x1400085fd  mov     r14, [rsp+0A8h+var_30]
0x140008602  mov     r13, [rsp+0A8h+var_28]
0x14000860a  mov     r12, [rsp+0A8h+arg_18]
0x140008612  mov     r15, [rsp+0A8h+var_38]
0x140008617  jmp     short loc_14000861E
0x140008619  test    rdi, rdi
0x14000861c  jz      short loc_14000862D
0x14000861e  mov     rcx, rdi
0x140008621  call    cs:__imp_SmbCseFinalizeBufferContext
0x140008628  nop     dword ptr [rax+rax+00h]
0x14000862d  mov     dword ptr [rsp+0A8h+arg_8], ebx
0x140008634  mov     rdx, rsi
0x140008637  mov     r8, [rsp+0A8h+arg_8]
0x14000863f  mov     rcx, rbp; RxContext
0x140008642  call    Smb2CompleteSrvOpenReconnectionCallback
0x140008647  xor     eax, eax
0x140008649  add     rsp, 88h
0x140008650  pop     rdi
0x140008651  pop     rsi
0x140008652  pop     rbp
0x140008653  pop     rbx
0x140008654  retn
0x140008656  movzx   ecx, byte ptr [r14+2]
0x14000865b  mov     edx, [r13+18h]
0x14000865f  cmp     cl, 0FFh
0x140008662  jz      loc_140008759
0x140008668  cmp     edx, 0FFh
0x14000866e  jz      loc_140038D86
0x140008674  cmp     edx, ecx
0x140008676  jbe     short loc_1400085FD
0x140008678  mov     r9d, ecx
0x14000867b  lea     rdx, [rsi+68h]
0x14000867f  mov     rcx, [r12+78h]
0x140008684  xor     r8d, r8d
0x140008687  mov     rcx, [rcx+20h]
0x14000868b  call    cs:__imp_RxIndicateChangeOfOplockState
0x140008692  nop     dword ptr [rax+rax+00h]
0x140008697  jmp     loc_1400085FD
0x14000869c  mov     r15d, 0C00000C3h
0x1400086a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086a9  cmp     rcx, r8
0x1400086ac  jz      loc_1400085E9
0x1400086b2  mov     eax, [rcx+2Ch]
0x1400086b5  test    al, 1
0x1400086b7  jz      loc_1400085E9
0x1400086bd  cmp     byte ptr [rcx+29h], 1
0x1400086c1  jb      loc_1400085E9
0x1400086c7  mov     r9, [r10+30h]
0x1400086cb  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x1400086d2  mov     rcx, [rcx+18h]
0x1400086d6  mov     edx, 1Ah
0x1400086db  mov     [rsp+0A8h+var_88], r10
0x1400086e0  call    WPP_SF_qq
0x1400086e5  mov     ebx, r15d
0x1400086e8  jmp     loc_1400085FD
0x1400086ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086f4  lea     rax, WPP_GLOBAL_Control
0x1400086fb  cmp     rcx, rax
0x1400086fe  jz      loc_140038DF8
0x140008704  mov     eax, [rcx+2Ch]
0x140008707  test    al, 1
0x140008709  jz      loc_140038DF8
0x14000870f  cmp     byte ptr [rcx+29h], 1
0x140008713  jb      loc_140038DF8
0x140008719  mov     edx, 1Bh
0x14000871e  jmp     loc_140038DDF
0x140008723  mov     rcx, cs:WPP_GLOBAL_Control
0x14000872a  lea     rax, WPP_GLOBAL_Control
0x140008731  cmp     rcx, rax
0x140008734  jz      loc_140038DF8
0x14000873a  mov     eax, [rcx+2Ch]
0x14000873d  test    al, 1
0x14000873f  jz      loc_140038DF8
0x140008745  cmp     byte ptr [rcx+29h], 1
0x140008749  jb      loc_140038DF8
0x14000874f  mov     edx, 1Ch
0x140008754  jmp     loc_140038DDF
0x140008759  cmp     edx, 0FFh
0x14000875f  jnz     loc_140038D86
0x140008765  movzx   eax, byte ptr [rsp+0A8h+var_78]
0x14000876a  test    al, 8
0x14000876c  jz      loc_1400085FD
0x140008772  mov     r8d, dword ptr [rsp+0A8h+var_58+4]
0x140008777  mov     edx, dword ptr [rsp+0A8h+var_58+8]
0x14000877b  test    al, 10h
0x14000877d  jz      loc_140038D3E
0x140008783  movzx   ecx, word ptr [r11+44h]
0x140008788  movzx   eax, dx
0x14000878b  sub     ax, cx
0x14000878e  mov     r9d, 7FFFh
0x140008794  cmp     ax, r9w
0x140008798  ja      loc_140038D3E
0x14000879e  cmp     dx, cx
0x1400087a1  jz      loc_140038D3E
0x1400087a7  jmp     loc_140038D4F
0x140038d3e  mov     ecx, [r11+40h]
0x140038d42  mov     eax, ecx
0x140038d44  and     eax, r8d
0x140038d47  cmp     eax, ecx
0x140038d49  jz      loc_1400085FD
0x140038d4f  movzx   r9d, dx
0x140038d53  mov     eax, r8d
0x140038d56  mov     byte ptr [r11+50h], 1
0x140038d5b  and     eax, 1Fh
0x140038d5e  mov     rcx, [r12+78h]
0x140038d63  xor     r8d, r8d
0x140038d66  shl     r9d, 5
0x140038d6a  mov     rdx, r12
0x140038d6d  or      r9, rax
0x140038d70  mov     rcx, [rcx+20h]
0x140038d74  call    cs:__imp_RxIndicateChangeOfOplockStateForTarget
0x140038d7b  nop     dword ptr [rax+rax+00h]
0x140038d80  nop
0x140038d81  jmp     loc_1400085FD
0x140038d86  mov     ebx, 0C00000C3h
0x140038d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d92  cmp     rcx, r8
0x140038d95  jz      loc_1400085FD
0x140038d9b  mov     eax, [rcx+2Ch]
0x140038d9e  test    al, 1
0x140038da0  jz      loc_1400085FD
0x140038da6  cmp     byte ptr [rcx+29h], 1
0x140038daa  jb      loc_1400085FD
0x140038db0  mov     rax, [rsi+50h]
0x140038db4  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140038dbb  mov     rcx, [rcx+18h]
0x140038dbf  mov     edx, 30h ; '0'
0x140038dc4  mov     [rsp+0A8h+var_80], rax
0x140038dc9  mov     r9, rsi
0x140038dcc  mov     dword ptr [rsp+0A8h+var_88], 0C00000C3h
0x140038dd4  call    WPP_SF_qDZ
0x140038dd9  nop
0x140038dda  jmp     loc_1400085FD
0x140038ddf  mov     r9, [r10+30h]
0x140038de3  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140038dea  mov     rcx, [rcx+18h]
0x140038dee  mov     [rsp+0A8h+var_88], r10
0x140038df3  call    WPP_SF_qq
0x140038df8  mov     ebx, 0C00000C3h
0x140038dfd  jmp     loc_1400085FD
```
