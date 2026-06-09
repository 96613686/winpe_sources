# EapProcessEaphostFailure

- ea: `0x18001d208`
- end: `0x18001d5ac`
- name: `EapProcessEaphostFailure`
- size: `932`
- prototype: ``
- caller_count: `7`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180005b00`
- `0x180006bd0`
- `0x18000a550`
- `0x180010820`
- `0x180014190`
- `0x180015220`
- `0x180015f90`

## callees

- `0x180004f40`
- `0x180007f60`
- `0x180010ae0`
- `0x18001b044`
- `0x18001d108`
- `0x18001d208`
- `0x18001d5b4`
- `0x18001d654`
- `0x1800214f0`
- `0x180024238`
- `0x1800258c8`
- `0x180027e84`
- `0x18002a3a0`

## pseudocode

```c
__int64 __fastcall EapProcessEaphostFailure(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r14
  int v5; // r12d
  unsigned int v7; // ebp
  unsigned int v9; // edi
  void *v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  int v22; // [rsp+70h] [rbp+8h] BYREF
  int v23; // [rsp+78h] [rbp+10h] BYREF
  int v24; // [rsp+80h] [rbp+18h] BYREF

  v24 = a3;
  v4 = *a1;
  v5 = 0;
  v24 = 0;
  v7 = a2;
  v23 = 0;
  v22 = 0;
  v9 = *(_DWORD *)(v4 + 20);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
  {
    if ( a4 )
      v11 = *(_DWORD *)(a4 + 20);
    else
      v11 = 327685;
    WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 7), a2, a3, v9, a2, v11);
  }
  if ( (Microsoft_Windows_OneXEnableBits & 4) != 0 )
  {
    if ( a4 )
      v12 = *(_DWORD *)(a4 + 20);
    else
      LOBYTE(v12) = 5;
    McTemplateU0qqq_EtwEventWriteTransfer((__int64)v10, (__int64)EAPFailureIndication, v9, v7, v12);
  }
  if ( v7 == 1115 )
    *((_DWORD *)a1 + 57) = 1;
  EapDumpEaphostError(v7, v9, a4);
  if ( *((_DWORD *)a1 + 42)
    || v7 != 1078067472
    || *(_DWORD *)(v4 + 2828) != 2
    || (unsigned int)IsDomainUser(*(_DWORD *)(v4 + 2832), &v24)
    || v24 )
  {
LABEL_33:
    if ( (*(_BYTE *)(v4 + 2784) & 0x20) != 0 )
    {
      v14 = SupplicantProcessAuthModeDiscoveryOnFailure(v4, v7, v13, &v22);
      v15 = v14;
      if ( v14 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v15;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_61;
        v17 = 165;
        goto LABEL_23;
      }
      if ( v22 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v15;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0 )
          goto LABEL_61;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 166, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
        goto LABEL_60;
      }
      *(_DWORD *)(*(_QWORD *)(v4 + 2744) + 12LL) &= ~0x20u;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0 )
        goto LABEL_46;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 167, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
    }
    v20 = WPP_GLOBAL_Control;
LABEL_46:
    if ( v5 )
    {
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x10) != 0 )
        WPP_SF_d(v20[7], 168, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
      if ( (Microsoft_Windows_OneXEnableBits & 8) != 0 )
        McTemplateU0q_EtwEventWriteTransfer((__int64)v20, (__int64)RetryAltCredAuthentication, v9);
      v14 = OneXGenerateSelfAuthRestartedEvent(v4, 7);
      v15 = v14;
      if ( !v14 )
        goto LABEL_60;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v15;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_61;
      v17 = 169;
    }
    else
    {
      v14 = OneXGenerateLocalEapFailureEvent(v4, v7, 327685, a4);
      v15 = v14;
      if ( !v14 )
        goto LABEL_60;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v15;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_61;
      v17 = 170;
    }
LABEL_23:
    WPP_SF_dd(v16[7], v17, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9, v14);
LABEL_60:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  v14 = EapChangeUseWinlogonCreds(a1, 0, &v23);
  v15 = v14;
  if ( !v14 )
  {
    v5 = v23;
    if ( v23 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0 )
        goto LABEL_32;
      v19 = 163;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0 )
        goto LABEL_32;
      v19 = 164;
    }
    WPP_SF_d(v18[7], v19, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
LABEL_32:
    *((_DWORD *)a1 + 43) = v5;
    *((_DWORD *)a1 + 42) = v5;
    goto LABEL_33;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v17 = 162;
    goto LABEL_23;
  }
LABEL_61:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x800) != 0 )
    WPP_SF_D(v16[7], 171, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x18001d208  mov     rax, rsp
0x18001d20b  mov     [rax+18h], r8d
0x18001d20f  push    rbx
0x18001d210  push    rbp
0x18001d211  push    rsi
0x18001d212  push    rdi
0x18001d213  push    r12
0x18001d215  push    r14
0x18001d217  push    r15
0x18001d219  sub     rsp, 30h
0x18001d21d  mov     r14, [rcx]
0x18001d220  xor     r12d, r12d
0x18001d223  mov     r15, r9
0x18001d226  mov     dword ptr [rax+18h], 0
0x18001d22d  mov     ebp, edx
0x18001d22f  mov     [rax+10h], r12d
0x18001d233  mov     rsi, rcx
0x18001d236  mov     [rax+8], r12d
0x18001d23a  mov     edi, [r14+14h]
0x18001d23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d245  lea     rbx, WPP_GLOBAL_Control
0x18001d24c  cmp     rcx, rbx
0x18001d24f  jz      short loc_18001D27B
0x18001d251  test    byte ptr [rcx+44h], 10h
0x18001d255  jz      short loc_18001D27B
0x18001d257  test    r9, r9
0x18001d25a  jz      short loc_18001D262
0x18001d25c  mov     eax, [r9+14h]
0x18001d260  jmp     short loc_18001D267
0x18001d262  mov     eax, 50005h
0x18001d267  mov     rcx, [rcx+38h]
0x18001d26b  mov     r9d, edi
0x18001d26e  mov     [rsp+68h+var_40], eax
0x18001d272  mov     [rsp+68h+var_48], ebp
0x18001d276  call    WPP_SF_dDD
0x18001d27b  test    cs:Microsoft_Windows_OneXEnableBits, 4
0x18001d282  jz      short loc_18001D2AA
0x18001d284  test    r15, r15
0x18001d287  jz      short loc_18001D28F
0x18001d289  mov     eax, [r15+14h]
0x18001d28d  jmp     short loc_18001D294
0x18001d28f  mov     eax, 50005h
0x18001d294  mov     r9d, ebp
0x18001d297  mov     [rsp+68h+var_48], eax
0x18001d29b  mov     r8d, edi
0x18001d29e  lea     rdx, EAPFailureIndication
0x18001d2a5  call    McTemplateU0qqq_EtwEventWriteTransfer
0x18001d2aa  cmp     ebp, 45Bh
0x18001d2b0  jnz     short loc_18001D2BC
0x18001d2b2  mov     dword ptr [rsi+0E4h], 1
0x18001d2bc  mov     r8, r15
0x18001d2bf  mov     edx, edi
0x18001d2c1  mov     ecx, ebp
0x18001d2c3  call    EapDumpEaphostError
0x18001d2c8  cmp     [rsi+0A8h], r12d
0x18001d2cf  jnz     loc_18001D3D9
0x18001d2d5  cmp     ebp, 40420110h
0x18001d2db  jnz     loc_18001D3D9
0x18001d2e1  cmp     dword ptr [r14+0B0Ch], 2
0x18001d2e9  jnz     loc_18001D3D9
0x18001d2ef  mov     ecx, [r14+0B10h]; SessionId
0x18001d2f6  lea     rdx, [rsp+68h+arg_10]
0x18001d2fe  call    IsDomainUser
0x18001d303  test    eax, eax
0x18001d305  jnz     loc_18001D3D9
0x18001d30b  cmp     [rsp+68h+arg_10], r12d
0x18001d313  jnz     loc_18001D3D9
0x18001d319  lea     r8, [rsp+68h+arg_8]
0x18001d31e  xor     edx, edx
0x18001d320  mov     rcx, rsi
0x18001d323  call    EapChangeUseWinlogonCreds
0x18001d328  mov     ebx, eax
0x18001d32a  test    eax, eax
0x18001d32c  jz      short loc_18001D370
0x18001d32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d335  lea     rsi, WPP_GLOBAL_Control
0x18001d33c  cmp     rcx, rsi
0x18001d33f  jz      loc_18001D59B
0x18001d345  test    byte ptr [rcx+44h], 1
0x18001d349  jz      loc_18001D575
0x18001d34f  mov     edx, 0A2h
0x18001d354  mov     rcx, [rcx+38h]
0x18001d358  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d35f  mov     r9d, edi
0x18001d362  mov     [rsp+68h+var_48], eax
0x18001d366  call    WPP_SF_dd
0x18001d36b  jmp     loc_18001D56E
0x18001d370  mov     r12d, [rsp+68h+arg_8]
0x18001d375  test    r12d, r12d
0x18001d378  jz      short loc_18001D39A
0x18001d37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d381  lea     rbx, WPP_GLOBAL_Control
0x18001d388  cmp     rcx, rbx
0x18001d38b  jz      short loc_18001D3CB
0x18001d38d  test    byte ptr [rcx+44h], 10h
0x18001d391  jz      short loc_18001D3CB
0x18001d393  mov     edx, 0A3h
0x18001d398  jmp     short loc_18001D3B8
0x18001d39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3a1  lea     rbx, WPP_GLOBAL_Control
0x18001d3a8  cmp     rcx, rbx
0x18001d3ab  jz      short loc_18001D3CB
0x18001d3ad  test    byte ptr [rcx+44h], 10h
0x18001d3b1  jz      short loc_18001D3CB
0x18001d3b3  mov     edx, 0A4h
0x18001d3b8  mov     rcx, [rcx+38h]
0x18001d3bc  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d3c3  mov     r9d, edi
0x18001d3c6  call    WPP_SF_d
0x18001d3cb  mov     [rsi+0ACh], r12d
0x18001d3d2  mov     [rsi+0A8h], r12d
0x18001d3d9  test    byte ptr [r14+0AE0h], 20h
0x18001d3e1  jz      loc_18001D4A8
0x18001d3e7  lea     r9, [rsp+68h+arg_0]
0x18001d3ec  mov     edx, ebp
0x18001d3ee  mov     rcx, r14
0x18001d3f1  call    SupplicantProcessAuthModeDiscoveryOnFailure
0x18001d3f6  mov     ebx, eax
0x18001d3f8  test    eax, eax
0x18001d3fa  jz      short loc_18001D427
0x18001d3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d403  lea     rsi, WPP_GLOBAL_Control
0x18001d40a  cmp     rcx, rsi
0x18001d40d  jz      loc_18001D59B
0x18001d413  test    byte ptr [rcx+44h], 1
0x18001d417  jz      loc_18001D575
0x18001d41d  mov     edx, 0A5h
0x18001d422  jmp     loc_18001D354
0x18001d427  cmp     [rsp+68h+arg_0], 0
0x18001d42c  jz      short loc_18001D46C
0x18001d42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d435  lea     rsi, WPP_GLOBAL_Control
0x18001d43c  cmp     rcx, rsi
0x18001d43f  jz      loc_18001D59B
0x18001d445  test    byte ptr [rcx+44h], 10h
0x18001d449  jz      loc_18001D575
0x18001d44f  mov     rcx, [rcx+38h]
0x18001d453  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d45a  mov     edx, 0A6h
0x18001d45f  mov     r9d, edi
0x18001d462  call    WPP_SF_d
0x18001d467  jmp     loc_18001D56E
0x18001d46c  mov     rax, [r14+0AB8h]
0x18001d473  and     dword ptr [rax+0Ch], 0FFFFFFDFh
0x18001d477  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d47e  lea     rbx, WPP_GLOBAL_Control
0x18001d485  cmp     rcx, rbx
0x18001d488  jz      short loc_18001D4AF
0x18001d48a  test    byte ptr [rcx+44h], 10h
0x18001d48e  jz      short loc_18001D4AF
0x18001d490  mov     rcx, [rcx+38h]
0x18001d494  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d49b  mov     edx, 0A7h
0x18001d4a0  mov     r9d, edi
0x18001d4a3  call    WPP_SF_d
0x18001d4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4af  test    r12d, r12d
0x18001d4b2  jz      short loc_18001D52B
0x18001d4b4  cmp     rcx, rbx
0x18001d4b7  jz      short loc_18001D4D7
0x18001d4b9  test    byte ptr [rcx+44h], 10h
0x18001d4bd  jz      short loc_18001D4D7
0x18001d4bf  mov     rcx, [rcx+38h]
0x18001d4c3  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d4ca  mov     edx, 0A8h
0x18001d4cf  mov     r9d, edi
0x18001d4d2  call    WPP_SF_d
0x18001d4d7  test    cs:Microsoft_Windows_OneXEnableBits, 8
0x18001d4de  jz      short loc_18001D4EF
0x18001d4e0  mov     r8d, edi
0x18001d4e3  lea     rdx, RetryAltCredAuthentication
0x18001d4ea  call    McTemplateU0q_EtwEventWriteTransfer
0x18001d4ef  xor     r8d, r8d
0x18001d4f2  mov     rcx, r14
0x18001d4f5  lea     edx, [r8+7]
0x18001d4f9  call    OneXGenerateSelfAuthRestartedEvent
0x18001d4fe  mov     ebx, eax
0x18001d500  test    eax, eax
0x18001d502  jz      short loc_18001D567
0x18001d504  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d50b  lea     rsi, WPP_GLOBAL_Control
0x18001d512  cmp     rcx, rsi
0x18001d515  jz      loc_18001D59B
0x18001d51b  test    byte ptr [rcx+44h], 1
0x18001d51f  jz      short loc_18001D575
0x18001d521  mov     edx, 0A9h
0x18001d526  jmp     loc_18001D354
0x18001d52b  mov     r9, r15
0x18001d52e  mov     r8d, 50005h
0x18001d534  mov     edx, ebp
0x18001d536  mov     rcx, r14
0x18001d539  call    OneXGenerateLocalEapFailureEvent
0x18001d53e  mov     ebx, eax
0x18001d540  test    eax, eax
0x18001d542  jz      short loc_18001D567
0x18001d544  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d54b  lea     rsi, WPP_GLOBAL_Control
0x18001d552  cmp     rcx, rsi
0x18001d555  jz      short loc_18001D59B
0x18001d557  test    byte ptr [rcx+44h], 1
0x18001d55b  jz      short loc_18001D575
0x18001d55d  mov     edx, 0AAh
0x18001d562  jmp     loc_18001D354
0x18001d567  lea     rsi, WPP_GLOBAL_Control
0x18001d56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d575  cmp     rcx, rsi
0x18001d578  jz      short loc_18001D59B
0x18001d57a  test    dword ptr [rcx+44h], 800h
0x18001d581  jz      short loc_18001D59B
0x18001d583  mov     rcx, [rcx+38h]
0x18001d587  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d58e  mov     edx, 0ABh
0x18001d593  mov     r9d, ebx
0x18001d596  call    WPP_SF_D
0x18001d59b  mov     eax, ebx
0x18001d59d  add     rsp, 30h
0x18001d5a1  pop     r15
0x18001d5a3  pop     r14
0x18001d5a5  pop     r12
0x18001d5a7  pop     rdi
0x18001d5a8  pop     rsi
0x18001d5a9  pop     rbp
0x18001d5aa  pop     rbx
0x18001d5ab  retn
```
