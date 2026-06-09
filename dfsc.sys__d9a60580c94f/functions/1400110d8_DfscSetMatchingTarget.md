# DfscSetMatchingTarget

- ea: `0x1400110d8`
- end: `0x140011343`
- name: `DfscSetMatchingTarget`
- size: `619`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140023120`

## callees

- `0x1400025f4`
- `0x140002fcc`
- `0x140005310`
- `0x1400110d8`
- `0x1400119cc`
- `0x1400119f8`
- `0x140020fd0`
- `0x140021820`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140011205`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011205`

## pseudocode

```c
__int64 __fastcall DfscSetMatchingTarget(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  __int64 v4; // r14
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  const UNICODE_STRING *PrimaryTarget; // r15
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  const UNICODE_STRING *CurrentTarget; // rax
  __int64 v18; // rdx
  __int64 v19; // r8

  v2 = *(_QWORD *)(a1 + 16);
  v4 = *(_QWORD *)(a2 + 16);
  if ( v4 == v2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0 )
    {
      return 0;
    }
    v7 = 28;
    goto LABEL_9;
  }
  v8 = *(_DWORD *)(v2 + 8);
  if ( *(_DWORD *)(v4 + 8) != v8 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
    {
      return 0;
    }
    v7 = 29;
LABEL_9:
    WPP_SF_qq(v6->AttachedDevice, v7, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, a2, a1);
    return 0;
  }
  if ( v8 || *(_WORD *)(v2 + 24) )
  {
    PrimaryTarget = (const UNICODE_STRING *)DfscReferralGetPrimaryTarget(a1);
    v13 = PrimaryTarget == 0 ? 0x8000001A : 0;
    while ( 1 )
    {
      if ( v13 )
        goto LABEL_36;
      v13 = DfscReferralIterate(a2, v9, v10, v11);
      if ( v13 )
        break;
      CurrentTarget = (const UNICODE_STRING *)DfscReferralGetCurrentTarget(v15);
      if ( !RtlCompareUnicodeString(PrimaryTarget + 5, CurrentTarget + 5, 1u) )
      {
        *(_WORD *)(*(_QWORD *)(a2 + 16) + 26LL) = *(_WORD *)(a2 + 32);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, v13 + 33, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, a2);
        }
        if ( (*(_DWORD *)(a1 + 8) & 8) != 0 )
        {
          if ( (*(_BYTE *)(v2 + 12) & 8) != 0 )
          {
            v18 = *(_QWORD *)(a2 + 16);
            v19 = *(unsigned __int16 *)(v18 + 26);
            *(_WORD *)(a2 + 26) = v19;
            *(_WORD *)(a2 + 32) = v19;
            *(_DWORD *)(a2 + 28) = *(_DWORD *)(112 * v19 + v18 + 164);
            if ( (_WORD)v19 )
              *(_WORD *)(a2 + 24) = *(_WORD *)(a2 + 24) & 0xFFFA | 4;
            return 0;
          }
        }
        else
        {
          *(_BYTE *)(v4 + 14) = *(_BYTE *)(v2 + 14);
        }
LABEL_36:
        DfscReferralIterateInitialize(a2);
        return v13;
      }
    }
    if ( v13 == -2147483622 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, a1, a2);
      }
      v13 = -1073741772;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, v14, v16, v13, a1, a2);
    }
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids, a1);
  return 0;
}

```

## disassembly

```asm
0x1400110d8  push    rbx
0x1400110da  push    rbp
0x1400110db  push    rsi
0x1400110dc  push    rdi
0x1400110dd  push    r12
0x1400110df  push    r14
0x1400110e1  push    r15
0x1400110e3  sub     rsp, 30h
0x1400110e7  mov     rbp, [rcx+10h]
0x1400110eb  mov     rbx, rdx
0x1400110ee  mov     r14, [rdx+10h]
0x1400110f2  mov     rsi, rcx
0x1400110f5  cmp     r14, rbp
0x1400110f8  jnz     short loc_140011125
0x1400110fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140011101  lea     rax, WPP_GLOBAL_Control
0x140011108  cmp     rcx, rax
0x14001110b  jz      loc_14001129F
0x140011111  test    dword ptr [rcx+2Ch], 200000h
0x140011118  jz      loc_14001129F
0x14001111e  mov     edx, 1Ch
0x140011123  jmp     short loc_140011157
0x140011125  mov     eax, [rbp+8]
0x140011128  cmp     [r14+8], eax
0x14001112c  jz      short loc_140011174
0x14001112e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011135  lea     rax, WPP_GLOBAL_Control
0x14001113c  cmp     rcx, rax
0x14001113f  jz      loc_14001129F
0x140011145  test    dword ptr [rcx+2Ch], 100000h
0x14001114c  jz      loc_14001129F
0x140011152  mov     edx, 1Dh
0x140011157  mov     rcx, [rcx+18h]
0x14001115b  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x140011162  mov     r9, rbx
0x140011165  mov     [rsp+68h+var_48], rsi
0x14001116a  call    WPP_SF_qq
0x14001116f  jmp     loc_14001129F
0x140011174  xor     r12d, r12d
0x140011177  test    eax, eax
0x140011179  jnz     short loc_1400111C3
0x14001117b  cmp     [rbp+18h], r12w
0x140011180  jnz     short loc_1400111C3
0x140011182  mov     rcx, cs:WPP_GLOBAL_Control
0x140011189  lea     rax, WPP_GLOBAL_Control
0x140011190  cmp     rcx, rax
0x140011193  jz      loc_14001129F
0x140011199  test    dword ptr [rcx+2Ch], 200000h
0x1400111a0  jz      loc_14001129F
0x1400111a6  mov     rcx, [rcx+18h]
0x1400111aa  lea     edx, [r12+1Eh]
0x1400111af  mov     r9, rsi
0x1400111b2  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x1400111b9  call    WPP_SF_q
0x1400111be  jmp     loc_14001129F
0x1400111c3  call    DfscReferralGetPrimaryTarget
0x1400111c8  mov     rcx, rax
0x1400111cb  mov     r15, rax
0x1400111ce  neg     rcx
0x1400111d1  sbb     edi, edi
0x1400111d3  not     edi
0x1400111d5  and     edi, 8000001Ah
0x1400111db  test    edi, edi
0x1400111dd  jnz     loc_140011329
0x1400111e3  mov     rcx, rbx
0x1400111e6  call    DfscReferralIterate
0x1400111eb  mov     edi, eax
0x1400111ed  test    eax, eax
0x1400111ef  jnz     loc_1400112AF
0x1400111f5  call    DfscReferralGetCurrentTarget
0x1400111fa  lea     rcx, [r15+50h]; String1
0x1400111fe  mov     r8b, 1; CaseInSensitive
0x140011201  lea     rdx, [rax+50h]; String2
0x140011205  call    cs:__imp_RtlCompareUnicodeString
0x14001120c  nop     dword ptr [rax+rax+00h]
0x140011211  test    eax, eax
0x140011213  jnz     short loc_1400111DB
0x140011215  mov     rcx, [rbx+10h]
0x140011219  movzx   eax, word ptr [rbx+20h]
0x14001121d  mov     [rcx+1Ah], ax
0x140011221  mov     rcx, cs:WPP_GLOBAL_Control
0x140011228  lea     rax, WPP_GLOBAL_Control
0x14001122f  cmp     rcx, rax
0x140011232  jz      short loc_140011253
0x140011234  test    dword ptr [rcx+2Ch], 100000h
0x14001123b  jz      short loc_140011253
0x14001123d  mov     rcx, [rcx+18h]
0x140011241  lea     edx, [rdi+21h]
0x140011244  mov     r9, rbx
0x140011247  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14001124e  call    WPP_SF_q
0x140011253  mov     eax, [rsi+8]
0x140011256  test    al, 8
0x140011258  jz      short loc_1400112A6
0x14001125a  test    byte ptr [rbp+0Ch], 8
0x14001125e  jz      loc_140011329
0x140011264  mov     rdx, [rbx+10h]
0x140011268  movzx   r8d, word ptr [rdx+1Ah]
0x14001126d  imul    rcx, r8, 70h ; 'p'
0x140011271  mov     [rbx+1Ah], r8w
0x140011276  mov     [rbx+20h], r8w
0x14001127b  mov     eax, [rcx+rdx+0A4h]
0x140011282  mov     [rbx+1Ch], eax
0x140011285  test    r8w, r8w
0x140011289  jz      short loc_14001129F
0x14001128b  movzx   eax, word ptr [rbx+18h]
0x14001128f  mov     ecx, 0FFFEh
0x140011294  and     ax, cx
0x140011297  or      ax, 4
0x14001129b  mov     [rbx+18h], ax
0x14001129f  xor     eax, eax
0x1400112a1  jmp     loc_140011333
0x1400112a6  mov     al, [rbp+0Eh]
0x1400112a9  mov     [r14+0Eh], al
0x1400112ad  jmp     short loc_140011329
0x1400112af  cmp     edi, 8000001Ah
0x1400112b5  jnz     short loc_1400112F7
0x1400112b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112be  lea     rax, WPP_GLOBAL_Control
0x1400112c5  cmp     rcx, rax
0x1400112c8  jz      short loc_1400112F0
0x1400112ca  test    dword ptr [rcx+2Ch], 100000h
0x1400112d1  jz      short loc_1400112F0
0x1400112d3  mov     rcx, [rcx+18h]
0x1400112d7  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x1400112de  mov     edx, 1Fh
0x1400112e3  mov     [rsp+68h+var_48], rbx
0x1400112e8  mov     r9, rsi
0x1400112eb  call    WPP_SF_qq
0x1400112f0  mov     edi, 0C0000034h
0x1400112f5  jmp     short loc_140011329
0x1400112f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112fe  lea     rax, WPP_GLOBAL_Control
0x140011305  cmp     rcx, rax
0x140011308  jz      short loc_140011329
0x14001130a  test    dword ptr [rcx+2Ch], 100000h
0x140011311  jz      short loc_140011329
0x140011313  mov     rcx, [rcx+18h]
0x140011317  mov     r9d, edi
0x14001131a  mov     [rsp+68h+var_40], rbx
0x14001131f  mov     [rsp+68h+var_48], rsi
0x140011324  call    WPP_SF_Dqq
0x140011329  mov     rcx, rbx
0x14001132c  call    DfscReferralIterateInitialize
0x140011331  mov     eax, edi
0x140011333  add     rsp, 30h
0x140011337  pop     r15
0x140011339  pop     r14
0x14001133b  pop     r12
0x14001133d  pop     rdi
0x14001133e  pop     rsi
0x14001133f  pop     rbp
0x140011340  pop     rbx
0x140011341  retn
```
