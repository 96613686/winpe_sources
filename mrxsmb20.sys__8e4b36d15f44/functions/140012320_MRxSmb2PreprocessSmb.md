# MRxSmb2PreprocessSmb

- ea: `0x140012320`
- end: `0x140012442`
- name: `MRxSmb2PreprocessSmb`
- size: `290`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140012320`
- `0x140029c14`
- `0x14002a9ac`
- `0x140030130`
- `0x1400301e0`
- `0x140035f18`
- `0x140037120`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14003acec`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003acec`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003ab34`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003acb1`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003ab34`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003acb1`
- `rdbss!RxIndicateChangeOfOplockStateWithCreateHint` at `0x14003ab65`
- `rdbss!RxIndicateChangeOfOplockStateWithCreateHint` at `0x14003ab65`
- `rdbss!RxIndicateChangeOfOplockState` at `0x14003acd9`
- `rdbss!RxIndicateChangeOfOplockState` at `0x14003acd9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140012351`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140012351`

## pseudocode

```c
__int64 __fastcall MRxSmb2PreprocessSmb(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // rbx
  unsigned int v11; // ebx
  __int64 v13; // rcx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v18; // edx
  __int16 v19; // cx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // r14
  __int64 v22; // r8
  __int128 v23; // [rsp+90h] [rbp-58h] BYREF

  v6 = *(unsigned __int16 *)(a3 + 12);
  if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 64) & 8) != 0 && a2 && *(_DWORD *)(a6 + 20) != 259 )
  {
    v13 = 20;
    if ( (unsigned int)v6 <= 0x14 )
      v13 = v6;
    _InterlockedAdd64((volatile signed __int64 *)(a2 + 728), a5);
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 4 * v13 + 864));
  }
  if ( (_DWORD)v6 == 13 )
    return 0;
  if ( (_DWORD)v6 != 18 )
  {
    if ( (_DWORD)v6 == 19 )
      return (unsigned int)Smb2ProcessNotification(a1, a3, a4);
    else
      return (unsigned int)-1073741802;
  }
  if ( *(_QWORD *)a6 != -1 )
  {
    v11 = -1073741802;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v15 = 11;
LABEL_19:
      WPP_SF_(v14->AttachedDevice, v15, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids);
      return v11;
    }
    return v11;
  }
  if ( a4 < 0x42 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return (unsigned int)-1073741629;
    }
    v17 = 12;
    goto LABEL_25;
  }
  v11 = 0;
  v19 = *(_WORD *)(a3 + 64);
  if ( (*(_DWORD *)(a1 + 716) & 0x20) == 0 || v19 != 44 )
  {
    if ( v19 == 24 )
    {
      v23 = 0;
      if ( !*(_DWORD *)(a6 + 16) )
      {
        if ( a4 < 0x58 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return (unsigned int)-1073741629;
          }
          v18 = 18;
LABEL_26:
          WPP_SF_qZ(
            v20->AttachedDevice,
            v18,
            (unsigned int)WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids,
            a1,
            a1 + 80);
          return (unsigned int)-1073741629;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qDDiiLLL(
            WPP_GLOBAL_Control->AttachedDevice,
            *(unsigned __int16 *)(a3 + 14),
            a5,
            a1,
            a4,
            a5,
            -1,
            *(_QWORD *)(a3 + 40),
            *(_DWORD *)(a3 + 36),
            *(unsigned __int16 *)(a3 + 14),
            *(_DWORD *)(a3 + 8));
        }
        v23 = *(unsigned __int64 *)(a3 + 72);
        if ( !*(_QWORD *)(a1 + 48) || !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 512)) )
          return v11;
        LOBYTE(v22) = 1;
        RxIndicateChangeOfOplockState(*(_QWORD *)(a1 + 48), &v23, v22, *(unsigned __int8 *)(a3 + 66));
LABEL_73:
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 512));
        return v11;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return (unsigned int)-1073741629;
      }
      v17 = 17;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return (unsigned int)-1073741629;
      }
      v17 = 20;
    }
LABEL_25:
    WPP_SF_(v16->AttachedDevice, v17, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids);
    return (unsigned int)-1073741629;
  }
  if ( (*(_BYTE *)(a1 + 736) & 0x10) == 0 && *(_DWORD *)(a6 + 16) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return (unsigned int)-1073741629;
    }
    v17 = 13;
    goto LABEL_25;
  }
  if ( a4 < 0x6C )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return (unsigned int)-1073741629;
    }
    v18 = 14;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDDiiLLLiiqdddd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int16 *)(a3 + 14),
      a5,
      a1,
      a4,
      a5,
      -1,
      *(_QWORD *)(a3 + 40),
      *(_DWORD *)(a3 + 36),
      *(_WORD *)(a3 + 14),
      *(_DWORD *)(a3 + 8),
      *(_QWORD *)(a3 + 80),
      *(_QWORD *)(a3 + 72),
      *(_QWORD *)(a1 + 48),
      *(_WORD *)(a3 + 66),
      *(_DWORD *)(a3 + 92),
      *(_DWORD *)(a3 + 88),
      *(_DWORD *)(a3 + 68));
  }
  if ( !*(_QWORD *)(a1 + 48) )
    return v11;
  if ( *(int *)(a3 + 8) < 0 )
    v21 = *(int *)(a3 + 8);
  else
    v21 = (32LL * *(unsigned __int16 *)(a3 + 66)) | *(_DWORD *)(a3 + 92) & 0x1F;
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 512)) )
  {
    RxIndicateChangeOfOplockStateWithCreateHint(
      *(_QWORD *)(a1 + 48),
      a3 + 72,
      *(_BYTE *)(a3 + 68) & 1,
      *(unsigned int *)(a3 + 100),
      *(_DWORD *)(a3 + 104),
      v21);
    goto LABEL_73;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v15 = 16;
    goto LABEL_19;
  }
  return v11;
}

```

## disassembly

```asm
0x140012320  push    rbx
0x140012322  push    rbp
0x140012323  push    rsi
0x140012324  push    rdi
0x140012325  push    r14
0x140012327  sub     rsp, 0C0h
0x14001232e  mov     rax, cs:__security_cookie
0x140012335  xor     rax, rsp
0x140012338  mov     [rsp+0E8h+var_48], rax
0x140012340  movzx   ebx, word ptr [r8+0Ch]
0x140012345  mov     r14d, r9d
0x140012348  mov     rdi, r8
0x14001234b  mov     rsi, rdx
0x14001234e  mov     rbp, rcx
0x140012351  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140012358  nop     dword ptr [rax+rax+00h]
0x14001235d  mov     rdx, [rsp+0E8h+arg_28]
0x140012365  mov     r8d, [rsp+0E8h+arg_20]
0x14001236d  test    byte ptr [rax+40h], 8
0x140012371  jnz     short loc_1400123BE
0x140012373  mov     eax, ebx
0x140012375  mov     [rsp+0E8h+var_30], r15
0x14001237d  sub     eax, 0Dh
0x140012380  jz      loc_14001243B
0x140012386  sub     eax, 5
0x140012389  jz      short loc_1400123F4
0x14001238b  cmp     eax, 1
0x14001238e  jz      short loc_1400123E2
0x140012390  mov     ebx, 0C0000016h
0x140012395  mov     r15, [rsp+0E8h+var_30]
0x14001239d  mov     eax, ebx
0x14001239f  mov     rcx, [rsp+0E8h+var_48]
0x1400123a7  xor     rcx, rsp; StackCookie
0x1400123aa  call    __security_check_cookie
0x1400123af  add     rsp, 0C0h
0x1400123b6  pop     r14
0x1400123b8  pop     rdi
0x1400123b9  pop     rsi
0x1400123ba  pop     rbp
0x1400123bb  pop     rbx
0x1400123bc  retn
0x1400123be  test    rsi, rsi
0x1400123c1  jz      short loc_140012373
0x1400123c3  cmp     dword ptr [rdx+14h], 103h
0x1400123ca  jz      short loc_140012373
0x1400123cc  mov     ecx, 14h
0x1400123d1  cmp     ebx, 14h
0x1400123d4  ja      loc_14003A936
0x1400123da  mov     rcx, rbx
0x1400123dd  jmp     loc_14003A936
0x1400123e2  mov     r8d, r14d
0x1400123e5  mov     rdx, rdi
0x1400123e8  mov     rcx, rbp
0x1400123eb  call    Smb2ProcessNotification
0x1400123f0  mov     ebx, eax
0x1400123f2  jmp     short loc_140012395
0x1400123f4  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1400123f8  jz      loc_14003A969
0x1400123fe  mov     ebx, 0C0000016h
0x140012403  mov     rcx, cs:WPP_GLOBAL_Control
0x14001240a  lea     rsi, WPP_GLOBAL_Control
0x140012411  cmp     rcx, rsi
0x140012414  jz      loc_140012395
0x14001241a  test    dword ptr [rcx+2Ch], 200h
0x140012421  jz      loc_140012395
0x140012427  cmp     byte ptr [rcx+29h], 4
0x14001242b  jb      loc_140012395
0x140012431  mov     edx, 0Bh
0x140012436  jmp     loc_14003A953
0x14001243b  xor     ebx, ebx
0x14001243d  jmp     loc_140012395
0x14003a936  mov     rax, r8
0x14003a939  lock add [rsi+2D8h], rax
0x14003a941  lock inc dword ptr [rsi+rcx*4+360h]
0x14003a949  jmp     loc_140012373
0x14003a94e  mov     edx, 10h
0x14003a953  mov     rcx, [rcx+18h]
0x14003a957  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x14003a95e  call    WPP_SF_
0x14003a963  nop
0x14003a964  jmp     loc_140012395
0x14003a969  cmp     r14d, 42h ; 'B'
0x14003a96d  jnb     short loc_14003A9D8
0x14003a96f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a976  lea     rsi, WPP_GLOBAL_Control
0x14003a97d  cmp     rcx, rsi
0x14003a980  jz      short loc_14003A9CE
0x14003a982  mov     eax, [rcx+2Ch]
0x14003a985  test    al, 1
0x14003a987  jz      short loc_14003A9CE
0x14003a989  cmp     byte ptr [rcx+29h], 1
0x14003a98d  jb      short loc_14003A9CE
0x14003a98f  mov     edx, 0Ch
0x14003a994  jmp     short loc_14003A99B
0x14003a996  mov     edx, 14h
0x14003a99b  mov     rcx, [rcx+18h]
0x14003a99f  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x14003a9a6  call    WPP_SF_
0x14003a9ab  jmp     short loc_14003A9CE
0x14003a9ad  mov     edx, 0Eh
0x14003a9b2  mov     rcx, [rcx+18h]
0x14003a9b6  lea     rax, [rbp+50h]
0x14003a9ba  mov     r9, rbp
0x14003a9bd  mov     [rsp+0E8h+var_C8], rax
0x14003a9c2  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x14003a9c9  call    WPP_SF_qZ
0x14003a9ce  mov     ebx, 0C00000C3h
0x14003a9d3  jmp     loc_140012395
0x14003a9d8  mov     eax, [rbp+2CCh]
0x14003a9de  xor     ebx, ebx
0x14003a9e0  movzx   ecx, word ptr [rdi+40h]
0x14003a9e4  test    al, 20h
0x14003a9e6  jz      loc_14003ABA2
0x14003a9ec  cmp     cx, 2Ch ; ','
0x14003a9f0  jnz     loc_14003ABA2
0x14003a9f6  test    byte ptr [rbp+2E0h], 10h
0x14003a9fd  jnz     short loc_14003AA2E
0x14003a9ff  cmp     [rdx+10h], ebx
0x14003aa02  jz      short loc_14003AA2E
0x14003aa04  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa0b  lea     rsi, WPP_GLOBAL_Control
0x14003aa12  cmp     rcx, rsi
0x14003aa15  jz      short loc_14003A9CE
0x14003aa17  mov     eax, [rcx+2Ch]
0x14003aa1a  test    al, 1
0x14003aa1c  jz      short loc_14003A9CE
0x14003aa1e  cmp     byte ptr [rcx+29h], 1
0x14003aa22  jb      short loc_14003A9CE
0x14003aa24  mov     edx, 0Dh
0x14003aa29  jmp     loc_14003A99B
0x14003aa2e  cmp     r14d, 6Ch ; 'l'
0x14003aa32  jnb     short loc_14003AA5D
0x14003aa34  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa3b  lea     rsi, WPP_GLOBAL_Control
0x14003aa42  cmp     rcx, rsi
0x14003aa45  jz      short loc_14003A9CE
0x14003aa47  mov     eax, [rcx+2Ch]
0x14003aa4a  test    al, 1
0x14003aa4c  jz      short loc_14003A9CE
0x14003aa4e  cmp     byte ptr [rcx+29h], 1
0x14003aa52  jb      loc_14003A9CE
0x14003aa58  jmp     loc_14003A9AD
0x14003aa5d  mov     r10, cs:WPP_GLOBAL_Control
0x14003aa64  lea     rsi, WPP_GLOBAL_Control
0x14003aa6b  cmp     r10, rsi
0x14003aa6e  jz      loc_14003AB03
0x14003aa74  mov     eax, [r10+2Ch]
0x14003aa78  test    al, 4
0x14003aa7a  jz      loc_14003AB03
0x14003aa80  cmp     byte ptr [r10+29h], 2
0x14003aa85  jb      short loc_14003AB03
0x14003aa87  mov     eax, [rdi+44h]
0x14003aa8a  mov     r9, rbp
0x14003aa8d  movzx   ecx, word ptr [rdi+42h]
0x14003aa91  movzx   edx, word ptr [rdi+0Eh]
0x14003aa95  mov     [rsp+0E8h+var_60], eax
0x14003aa9c  mov     eax, [rdi+58h]
0x14003aa9f  mov     [rsp+0E8h+var_68], eax
0x14003aaa6  mov     eax, [rdi+5Ch]
0x14003aaa9  mov     [rsp+0E8h+var_70], eax
0x14003aaad  mov     rax, [rbp+30h]
0x14003aab1  mov     [rsp+0E8h+var_78], ecx
0x14003aab5  mov     rcx, [r10+18h]
0x14003aab9  mov     [rsp+0E8h+var_80], rax
0x14003aabe  mov     rax, [rdi+48h]
0x14003aac2  mov     [rsp+0E8h+var_88], rax
0x14003aac7  mov     rax, [rdi+50h]
0x14003aacb  mov     [rsp+0E8h+var_90], rax
0x14003aad0  mov     eax, [rdi+8]
0x14003aad3  mov     [rsp+0E8h+var_98], eax
0x14003aad7  mov     eax, [rdi+24h]
0x14003aada  mov     [rsp+0E8h+var_A0], edx
0x14003aade  mov     [rsp+0E8h+var_A8], eax
0x14003aae2  mov     rax, [rdi+28h]
0x14003aae6  mov     [rsp+0E8h+var_B0], rax
0x14003aaeb  mov     [rsp+0E8h+var_B8], 0FFFFFFFFFFFFFFFFh
0x14003aaf4  mov     dword ptr [rsp+0E8h+var_C0], r8d
0x14003aaf9  mov     dword ptr [rsp+0E8h+var_C8], r14d
0x14003aafe  call    WPP_SF_qDDiiLLLiiqdddd
0x14003ab03  cmp     [rbp+30h], rbx
0x14003ab07  jz      loc_140012395
0x14003ab0d  movsxd  rax, dword ptr [rdi+8]
0x14003ab11  test    eax, eax
0x14003ab13  js      short loc_14003AB2A
0x14003ab15  mov     r14d, [rdi+5Ch]
0x14003ab19  movzx   eax, word ptr [rdi+42h]
0x14003ab1d  and     r14d, 1Fh
0x14003ab21  shl     rax, 5
0x14003ab25  or      r14, rax
0x14003ab28  jmp     short loc_14003AB2D
0x14003ab2a  mov     r14, rax
0x14003ab2d  lea     rcx, [rbp+200h]; RunRef
0x14003ab34  call    cs:__imp_ExAcquireRundownProtection
0x14003ab3b  nop     dword ptr [rax+rax+00h]
0x14003ab40  test    al, al
0x14003ab42  jz      short loc_14003AB76
0x14003ab44  movzx   r8d, byte ptr [rdi+44h]
0x14003ab49  lea     rdx, [rdi+48h]
0x14003ab4d  mov     eax, [rdi+68h]
0x14003ab50  and     r8b, 1
0x14003ab54  mov     r9d, [rdi+64h]
0x14003ab58  mov     rcx, [rbp+30h]
0x14003ab5c  mov     [rsp+0E8h+var_C0], r14
0x14003ab61  mov     dword ptr [rsp+0E8h+var_C8], eax
0x14003ab65  call    cs:__imp_RxIndicateChangeOfOplockStateWithCreateHint
0x14003ab6c  nop     dword ptr [rax+rax+00h]
0x14003ab71  jmp     loc_14003ACE5
0x14003ab76  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab7d  cmp     rcx, rsi
0x14003ab80  jz      loc_140012395
0x14003ab86  test    dword ptr [rcx+2Ch], 200h
0x14003ab8d  jz      loc_140012395
0x14003ab93  cmp     byte ptr [rcx+29h], 4
0x14003ab97  jb      loc_140012395
0x14003ab9d  jmp     loc_14003A94E
0x14003aba2  cmp     cx, 18h
0x14003aba6  jnz     loc_14003ACFE
0x14003abac  xorps   xmm0, xmm0
0x14003abaf  movups  [rsp+0E8h+var_58], xmm0
0x14003abb7  cmp     [rdx+10h], ebx
0x14003abba  jz      short loc_14003ABF2
0x14003abbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003abc3  lea     rsi, WPP_GLOBAL_Control
0x14003abca  cmp     rcx, rsi
0x14003abcd  jz      loc_14003A9CE
0x14003abd3  mov     eax, [rcx+2Ch]
0x14003abd6  test    al, 1
0x14003abd8  jz      loc_14003A9CE
0x14003abde  cmp     byte ptr [rcx+29h], 1
0x14003abe2  jb      loc_14003A9CE
0x14003abe8  mov     edx, 11h
0x14003abed  jmp     loc_14003A99B
0x14003abf2  cmp     r14d, 58h ; 'X'
0x14003abf6  jnb     short loc_14003AC2E
0x14003abf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003abff  lea     rsi, WPP_GLOBAL_Control
0x14003ac06  cmp     rcx, rsi
0x14003ac09  jz      loc_14003A9CE
0x14003ac0f  mov     eax, [rcx+2Ch]
0x14003ac12  test    al, 1
0x14003ac14  jz      loc_14003A9CE
0x14003ac1a  cmp     byte ptr [rcx+29h], 1
0x14003ac1e  jb      loc_14003A9CE
0x14003ac24  mov     edx, 12h
0x14003ac29  jmp     loc_14003A9B2
0x14003ac2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac35  lea     rsi, WPP_GLOBAL_Control
0x14003ac3c  cmp     rcx, rsi
0x14003ac3f  jz      short loc_14003AC8C
0x14003ac41  mov     eax, [rcx+2Ch]
0x14003ac44  test    al, 4
0x14003ac46  jz      short loc_14003AC8C
0x14003ac48  cmp     byte ptr [rcx+29h], 2
0x14003ac4c  jb      short loc_14003AC8C
0x14003ac4e  mov     eax, [rdi+8]
0x14003ac51  mov     r9, rbp
0x14003ac54  movzx   edx, word ptr [rdi+0Eh]
0x14003ac58  mov     rcx, [rcx+18h]
0x14003ac5c  mov     [rsp+0E8h+var_98], eax
0x14003ac60  mov     eax, [rdi+24h]
0x14003ac63  mov     [rsp+0E8h+var_A0], edx
0x14003ac67  mov     [rsp+0E8h+var_A8], eax
0x14003ac6b  mov     rax, [rdi+28h]
0x14003ac6f  mov     [rsp+0E8h+var_B0], rax
0x14003ac74  mov     [rsp+0E8h+var_B8], 0FFFFFFFFFFFFFFFFh
0x14003ac7d  mov     dword ptr [rsp+0E8h+var_C0], r8d
0x14003ac82  mov     dword ptr [rsp+0E8h+var_C8], r14d
0x14003ac87  call    WPP_SF_qDDiiLLL
0x14003ac8c  mov     rax, [rdi+48h]
0x14003ac90  mov     qword ptr [rsp+0E8h+var_58], rax
0x14003ac98  mov     qword ptr [rsp+0E8h+var_58+8], rbx
0x14003aca0  cmp     [rbp+30h], rbx
0x14003aca4  jz      loc_140012395
0x14003acaa  lea     rcx, [rbp+200h]; RunRef
0x14003acb1  call    cs:__imp_ExAcquireRundownProtection
0x14003acb8  nop     dword ptr [rax+rax+00h]
0x14003acbd  test    al, al
0x14003acbf  jz      loc_140012395
0x14003acc5  movzx   r9d, byte ptr [rdi+42h]
0x14003acca  lea     rdx, [rsp+0E8h+var_58]
0x14003acd2  mov     rcx, [rbp+30h]
0x14003acd6  mov     r8b, 1
0x14003acd9  call    cs:__imp_RxIndicateChangeOfOplockState
0x14003ace0  nop     dword ptr [rax+rax+00h]
0x14003ace5  lea     rcx, [rbp+200h]; RunRef
0x14003acec  call    cs:__imp_ExReleaseRundownProtection
0x14003acf3  nop     dword ptr [rax+rax+00h]
0x14003acf8  nop
0x14003acf9  jmp     loc_140012395
0x14003acfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad05  lea     rsi, WPP_GLOBAL_Control
0x14003ad0c  cmp     rcx, rsi
0x14003ad0f  jz      loc_14003A9CE
0x14003ad15  mov     eax, [rcx+2Ch]
0x14003ad18  test    al, 1
0x14003ad1a  jz      loc_14003A9CE
0x14003ad20  cmp     byte ptr [rcx+29h], 1
0x14003ad24  jb      loc_14003A9CE
0x14003ad2a  jmp     loc_14003A996
```
