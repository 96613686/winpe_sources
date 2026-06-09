# _ConvertDaclToNT5Format

- ea: `0x1800247e4`
- end: `0x180024b8a`
- name: `_ConvertDaclToNT5Format`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180023310`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x1800136f0`
- `0x180017430`
- `0x180023e0c`
- `0x180023ef8`
- `0x1800247e4`
- `0x180024b90`
- `0x1800253b8`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x180024a59`
- `ADVAPI32!AddAccessAllowedAce` at `0x180024aca`
- `ADVAPI32!AddAccessAllowedAce` at `0x180024a59`
- `ADVAPI32!AddAccessAllowedAce` at `0x180024aca`
- `ADVAPI32!GetAce` at `0x18002495e`
- `ADVAPI32!GetAce` at `0x18002498b`
- `ADVAPI32!GetAce` at `0x18002495e`
- `ADVAPI32!GetAce` at `0x18002498b`
- `KERNEL32!GetLastError` at `0x1800249e3`
- `KERNEL32!GetLastError` at `0x180024a0c`
- `KERNEL32!GetLastError` at `0x180024a63`
- `KERNEL32!GetLastError` at `0x180024ad4`
- `KERNEL32!GetLastError` at `0x1800249e3`
- `KERNEL32!GetLastError` at `0x180024a0c`
- `KERNEL32!GetLastError` at `0x180024a63`
- `KERNEL32!GetLastError` at `0x180024ad4`

## pseudocode

```c
__int64 __fastcall ConvertDaclToNT5Format(__int64 a1, void *a2, struct _ACL *a3, __int64 a4, PACL *a5, _DWORD *a6)
{
  _DWORD *v6; // r15
  void *v9; // r12
  signed int LastError; // edi
  unsigned int v11; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD AceCount; // r15d
  DWORD v16; // edi
  DWORD v17; // r12d
  DWORD v18; // eax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  DWORD v22; // [rsp+68h] [rbp-18h] BYREF
  LPVOID pAce[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp+30h]

  v24 = a1;
  v6 = a6;
  v9 = a2;
  LODWORD(a6) = *a6;
  v22 = 0;
  LastError = AddMandatoryDenyACEs(a1, a2, a3, a4, a5);
  if ( LastError < 0 )
  {
    LOWORD(a6) = 100;
    v22 = LastError;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v11 = mqwcslen(L"acssctrl/secd4to5");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v11 + 1),
        L"acssctrl/secd4to5",
        2,
        &a6,
        4,
        &v22,
        0,
        0);
    }
    return (unsigned int)LastError;
  }
  if ( (_DWORD)a6 )
  {
    *v6 = 1;
    if ( v22 )
      return 0;
    LastError = AddMandatoryAllowACEs(v9, *a5);
    if ( LastError < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        return (unsigned int)LastError;
      v14 = 31;
      goto LABEL_45;
    }
LABEL_46:
    ShrinkAcl(a5, a4);
    return 0;
  }
  *v6 = 0;
  if ( !a3 )
  {
    if ( AddAccessAllowedAce(*a5, 4u, 0xF01FFu, g_pWorldSid) )
    {
      if ( AddAccessAllowedAce(*a5, 4u, 0xF01FFu, g_pAnonymSid) )
      {
LABEL_41:
        LastError = AddMandatoryAllowACEs(v9, *a5);
        if ( LastError < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
            return (unsigned int)LastError;
          v14 = 36;
LABEL_45:
          WPP_SF_d(v13[32], v14, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, (unsigned int)LastError);
          return (unsigned int)LastError;
        }
        goto LABEL_46;
      }
      LastError = GetLastError();
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v21 = 33;
        goto LABEL_33;
      }
    }
    else
    {
      LastError = GetLastError();
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v21 = 32;
LABEL_33:
        WPP_SF_d(v20[32], v21, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, (unsigned int)LastError);
      }
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  AceCount = a3->AceCount;
  if ( !a3->AceCount )
    goto LABEL_41;
  v16 = 0;
LABEL_14:
  pAce[0] = 0;
  if ( GetAce(a3, v16, pAce) )
  {
    v22 = v16;
    LOBYTE(a6) = *(_BYTE *)pAce[0];
    while ( 1 )
    {
      v17 = v16++;
      if ( v16 >= AceCount )
      {
LABEL_19:
        ConvertGroupOfDaclAces(v24, a3, v22, v17, *a5);
        if ( v16 < AceCount )
          goto LABEL_14;
        v9 = a2;
        goto LABEL_41;
      }
      if ( !GetAce(a3, v16, pAce) )
        break;
      if ( (_BYTE)a6 != *(_BYTE *)pAce[0] )
        goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v18 = GetLastError();
      v19 = 35;
      goto LABEL_27;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
  {
    v18 = GetLastError();
    v19 = 34;
LABEL_27:
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 32), v19, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, v16, v18);
  }
  return 3222146058LL;
}

```

## disassembly

```asm
0x1800247e4  mov     r11, rsp
0x1800247e7  mov     [r11+18h], rsi
0x1800247eb  mov     [r11+20h], rdi
0x1800247ef  mov     [r11+10h], rdx
0x1800247f3  mov     [rsp-28h+arg_0], ecx
0x1800247f7  push    rbp
0x1800247f8  push    r12
0x1800247fa  push    r13
0x1800247fc  push    r14
0x1800247fe  push    r15
0x180024800  mov     rbp, rsp
0x180024803  sub     rsp, 80h
0x18002480a  mov     r15, [rbp+arg_28]
0x18002480e  mov     r13, r9
0x180024811  mov     rsi, [rbp+arg_20]
0x180024815  mov     r14, r8
0x180024818  mov     r12, rdx
0x18002481b  mov     eax, [r15]
0x18002481e  mov     dword ptr [rbp+arg_28], eax
0x180024821  xor     eax, eax
0x180024823  mov     [rbp+var_18], eax
0x180024826  mov     [rbp+var_1C], eax
0x180024829  mov     [rbp+var_20], eax
0x18002482c  lea     rax, [rbp+var_20]
0x180024830  mov     [r11-68h], rax
0x180024834  lea     rax, [rbp+var_1C]
0x180024838  mov     [r11-70h], rax
0x18002483c  lea     rax, [rbp+var_18]
0x180024840  mov     [r11-78h], rax
0x180024844  lea     rax, [rbp+arg_28]
0x180024848  mov     [r11-80h], rax
0x18002484c  mov     [rsp+80h+var_60], rsi
0x180024851  call    _AddMandatoryDenyACEs
0x180024856  xor     ecx, ecx
0x180024858  mov     edi, eax
0x18002485a  test    eax, eax
0x18002485c  jns     short loc_1800248DD
0x18002485e  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rcx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180024865  lea     eax, [rcx+64h]
0x180024868  mov     word ptr [rbp+arg_28], ax
0x18002486c  mov     [rbp+var_18], edi
0x18002486f  jz      short loc_1800248D6
0x180024871  lea     rsi, aAcssctrlSecd4t; "acssctrl/secd4to5"
0x180024878  mov     rcx, rsi; wchar_t *
0x18002487b  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180024880  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180024887  mov     edx, 1
0x18002488c  mov     [rsp+80h+var_30], 0
0x180024895  mov     r8d, edx
0x180024898  mov     [rsp+80h+var_38], 0
0x1800248a1  lea     r9d, [rax+1]
0x1800248a5  lea     rax, [rbp+var_18]
0x1800248a9  add     r9, r9
0x1800248ac  mov     [rsp+80h+var_40], rax
0x1800248b1  lea     rax, [rbp+arg_28]
0x1800248b5  mov     [rsp+80h+var_48], 4
0x1800248be  mov     [rsp+80h+var_50], rax
0x1800248c3  mov     [rsp+80h+var_58], 2
0x1800248cc  mov     [rsp+80h+var_60], rsi
0x1800248d1  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800248d6  mov     eax, edi
0x1800248d8  jmp     loc_180024B6D
0x1800248dd  cmp     dword ptr [rbp+arg_28], ecx
0x1800248e0  jz      short loc_180024935
0x1800248e2  mov     dword ptr [r15], 1
0x1800248e9  cmp     [rbp+var_18], ecx
0x1800248ec  jnz     loc_180024B6B
0x1800248f2  mov     r9d, [rbp+var_20]
0x1800248f6  mov     rcx, r12; pSid
0x1800248f9  mov     r8d, [rbp+var_1C]
0x1800248fd  mov     rdx, [rsi]; pAcl
0x180024900  call    _AddMandatoryAllowACEs
0x180024905  mov     edi, eax
0x180024907  test    eax, eax
0x180024909  jns     loc_180024B60
0x18002490f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024916  lea     rdx, WPP_GLOBAL_Control
0x18002491d  cmp     rcx, rdx
0x180024920  jz      short loc_1800248D6
0x180024922  test    byte ptr [rcx+10Ch], 1
0x180024929  jz      short loc_1800248D6
0x18002492b  mov     edx, 1Fh
0x180024930  jmp     loc_180024B45
0x180024935  mov     [r15], ecx
0x180024938  test    r14, r14
0x18002493b  jz      loc_180024A42
0x180024941  movzx   r15d, word ptr [r14+4]
0x180024946  test    r15d, r15d
0x180024949  jz      loc_180024B03
0x18002494f  mov     edi, ecx
0x180024951  mov     [rbp+pAce], rcx
0x180024955  lea     r8, [rbp+pAce]; pAce
0x180024959  mov     rcx, r14; pAcl
0x18002495c  mov     edx, edi; dwAceIndex
0x18002495e  call    cs:__imp_GetAce
0x180024964  test    eax, eax
0x180024966  jz      loc_1800249F0
0x18002496c  mov     rax, [rbp+pAce]
0x180024970  mov     [rbp+var_18], edi
0x180024973  mov     al, [rax]
0x180024975  mov     byte ptr [rbp+arg_28], al
0x180024978  mov     r12d, edi
0x18002497b  inc     edi
0x18002497d  cmp     edi, r15d
0x180024980  jnb     short loc_1800249A0
0x180024982  lea     r8, [rbp+pAce]; pAce
0x180024986  mov     edx, edi; dwAceIndex
0x180024988  mov     rcx, r14; pAcl
0x18002498b  call    cs:__imp_GetAce
0x180024991  test    eax, eax
0x180024993  jz      short loc_1800249C7
0x180024995  mov     rax, [rbp+pAce]
0x180024999  mov     cl, byte ptr [rbp+arg_28]
0x18002499c  cmp     cl, [rax]
0x18002499e  jz      short loc_180024978
0x1800249a0  mov     rax, [rsi]
0x1800249a3  mov     r9d, r12d
0x1800249a6  mov     r8d, [rbp+var_18]
0x1800249aa  mov     rdx, r14
0x1800249ad  mov     ecx, [rbp+arg_0]
0x1800249b0  mov     [rsp+80h+var_60], rax
0x1800249b5  call    _ConvertGroupOfDaclAces
0x1800249ba  cmp     edi, r15d
0x1800249bd  jnb     loc_180024AFF
0x1800249c3  xor     ecx, ecx
0x1800249c5  jmp     short loc_180024951
0x1800249c7  mov     rax, cs:WPP_GLOBAL_Control
0x1800249ce  lea     rdx, WPP_GLOBAL_Control
0x1800249d5  cmp     rax, rdx
0x1800249d8  jz      short loc_180024A38
0x1800249da  test    byte ptr [rax+10Ch], 1
0x1800249e1  jz      short loc_180024A38
0x1800249e3  call    cs:__imp_GetLastError
0x1800249e9  mov     edx, 23h ; '#'
0x1800249ee  jmp     short loc_180024A17
0x1800249f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800249f7  lea     rdx, WPP_GLOBAL_Control
0x1800249fe  cmp     rax, rdx
0x180024a01  jz      short loc_180024A38
0x180024a03  test    byte ptr [rax+10Ch], 1
0x180024a0a  jz      short loc_180024A38
0x180024a0c  call    cs:__imp_GetLastError
0x180024a12  mov     edx, 22h ; '"'
0x180024a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a1e  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180024a25  mov     r9d, edi
0x180024a28  mov     dword ptr [rsp+80h+var_60], eax
0x180024a2c  mov     rcx, [rcx+100h]
0x180024a33  call    WPP_SF_dd
0x180024a38  mov     eax, 0C00E0C0Ah
0x180024a3d  jmp     loc_180024B6D
0x180024a42  mov     r9, cs:?g_pWorldSid@@3PEAXEA; pSid
0x180024a49  mov     edi, 0F01FFh
0x180024a4e  mov     rcx, [rsi]; pAcl
0x180024a51  mov     r8d, edi; AccessMask
0x180024a54  mov     edx, 4; dwAceRevision
0x180024a59  call    cs:__imp_AddAccessAllowedAce
0x180024a5f  test    eax, eax
0x180024a61  jnz     short loc_180024AB8
0x180024a63  call    cs:__imp_GetLastError
0x180024a69  mov     edi, eax
0x180024a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a72  lea     rdx, WPP_GLOBAL_Control
0x180024a79  cmp     rcx, rdx
0x180024a7c  jz      short loc_180024AA2
0x180024a7e  test    byte ptr [rcx+10Ch], 1
0x180024a85  jz      short loc_180024AA2
0x180024a87  mov     edx, 20h ; ' '
0x180024a8c  mov     rcx, [rcx+100h]
0x180024a93  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180024a9a  mov     r9d, edi
0x180024a9d  call    WPP_SF_d
0x180024aa2  test    edi, edi
0x180024aa4  jle     loc_1800248D6
0x180024aaa  movzx   edi, di
0x180024aad  or      edi, 80070000h
0x180024ab3  jmp     loc_1800248D6
0x180024ab8  mov     r9, cs:?g_pAnonymSid@@3PEAXEA; pSid
0x180024abf  mov     r8d, edi; AccessMask
0x180024ac2  mov     rcx, [rsi]; pAcl
0x180024ac5  mov     edx, 4; dwAceRevision
0x180024aca  call    cs:__imp_AddAccessAllowedAce
0x180024ad0  test    eax, eax
0x180024ad2  jnz     short loc_180024B03
0x180024ad4  call    cs:__imp_GetLastError
0x180024ada  mov     edi, eax
0x180024adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ae3  lea     rdx, WPP_GLOBAL_Control
0x180024aea  cmp     rcx, rdx
0x180024aed  jz      short loc_180024AA2
0x180024aef  test    byte ptr [rcx+10Ch], 1
0x180024af6  jz      short loc_180024AA2
0x180024af8  mov     edx, 21h ; '!'
0x180024afd  jmp     short loc_180024A8C
0x180024aff  mov     r12, [rbp+arg_8]
0x180024b03  mov     r9d, [rbp+var_20]
0x180024b07  mov     rcx, r12; pSid
0x180024b0a  mov     r8d, [rbp+var_1C]
0x180024b0e  mov     rdx, [rsi]; pAcl
0x180024b11  call    _AddMandatoryAllowACEs
0x180024b16  mov     edi, eax
0x180024b18  test    eax, eax
0x180024b1a  jns     short loc_180024B60
0x180024b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b23  lea     rdx, WPP_GLOBAL_Control
0x180024b2a  cmp     rcx, rdx
0x180024b2d  jz      loc_1800248D6
0x180024b33  test    byte ptr [rcx+10Ch], 1
0x180024b3a  jz      loc_1800248D6
0x180024b40  mov     edx, 24h ; '$'
0x180024b45  mov     rcx, [rcx+100h]
0x180024b4c  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180024b53  mov     r9d, edi
0x180024b56  call    WPP_SF_d
0x180024b5b  jmp     loc_1800248D6
0x180024b60  mov     rdx, r13
0x180024b63  mov     rcx, rsi
0x180024b66  call    _ShrinkAcl
0x180024b6b  xor     eax, eax
0x180024b6d  lea     r11, [rsp+80h+var_s0]
0x180024b75  mov     rsi, [r11+40h]
0x180024b79  mov     rdi, [r11+48h]
0x180024b7d  mov     rsp, r11
0x180024b80  pop     r15
0x180024b82  pop     r14
0x180024b84  pop     r13
0x180024b86  pop     r12
0x180024b88  pop     rbp
0x180024b89  retn
```
