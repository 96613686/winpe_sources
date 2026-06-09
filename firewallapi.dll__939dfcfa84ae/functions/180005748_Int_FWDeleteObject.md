# Int_FWDeleteObject

- ea: `0x180005748`
- end: `0x180005e05`
- name: `Int_FWDeleteObject`
- size: `1725`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005630`
- `0x18004edb0`
- `0x18004eea0`
- `0x18004ef90`
- `0x18004f080`
- `0x18004f170`
- `0x18004f260`
- `0x18004f350`
- `0x18004f440`
- `0x18004f9c0`

## callees

- `0x180005748`
- `0x180005e0c`
- `0x180026798`
- `0x180026c9c`
- `0x18003336c`
- `0x180054d58`
- `0x180054db8`
- `0x180055378`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005f978`
- `RPCRT4!RpcExceptionFilter` at `0x18005f978`
- `fwbase!FwHResultToWindowsError` at `0x1800059d2`
- `fwbase!FwHResultToWindowsError` at `0x180005a25`
- `fwbase!FwHResultToWindowsError` at `0x180005a86`
- `fwbase!FwHResultToWindowsError` at `0x180005ae7`
- `fwbase!FwHResultToWindowsError` at `0x1800059d2`
- `fwbase!FwHResultToWindowsError` at `0x180005a25`
- `fwbase!FwHResultToWindowsError` at `0x180005a86`
- `fwbase!FwHResultToWindowsError` at `0x180005ae7`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x180005a78`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x180005a78`
- `FWPolicyIOMgr!FwDeleteRule` at `0x180005ad9`
- `FWPolicyIOMgr!FwDeleteRule` at `0x180005ad9`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180005a17`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180005a17`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800059c4`
- `FWPolicyIOMgr!FwDeleteAllSets` at `0x1800059c4`

## pseudocode

```c
__int64 __fastcall Int_FWDeleteObject(
        unsigned int a1,
        int a2,
        __int64 (__fastcall *a3)(__int64, __int64),
        __int64 (__fastcall *a4)(__int64, __int64),
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  int v8; // r9d
  FwPolicy2 *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // r8d
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // eax
  __int64 v35; // [rsp+38h] [rbp-30h]

  v8 = a2;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    v10 = WPP_GLOBAL_Control;
    v8 = a2;
  }
  v35 = 0;
  if ( !a5 )
  {
    v11 = 87;
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v12 = 314;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v10 + 2), v12, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
      v10 = WPP_GLOBAL_Control;
      v13 = 0;
      goto LABEL_30;
    }
    goto LABEL_112;
  }
  if ( !v8 && !a6 )
  {
    v11 = 87;
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v12 = 315;
      goto LABEL_8;
    }
LABEL_112:
    v13 = v35;
    goto LABEL_30;
  }
  if ( a1 - 3 <= 1 && a7 - 1 > 1 )
  {
    v11 = 87;
    if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      v12 = 316;
      goto LABEL_8;
    }
    goto LABEL_112;
  }
  v35 = a5;
  v14 = *(_DWORD *)(a5 + 4);
  if ( v14 > 1 )
  {
    if ( v14 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v15 = Int_FWOpenGPOPolicyStore(a5);
    v11 = v15;
    if ( v15 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v16 = 324;
      goto LABEL_26;
    }
    if ( !*(_QWORD *)(a5 + 56) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a1 <= 2 )
    {
      v24 = 0;
      if ( a2 )
      {
        v25 = FwDeleteAllRules(*(_QWORD *)(a5 + 56));
        v15 = FwHResultToWindowsError(v25);
        v11 = v15;
        if ( !v15 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v16 = 325;
      }
      else
      {
        if ( a1 )
        {
          LOBYTE(v24) = a1 != 1;
          v24 = (unsigned int)(v24 + 1);
        }
        v26 = FwDeleteRule(*(_QWORD *)(a5 + 56), v24, a6);
        v15 = FwHResultToWindowsError(v26);
        v11 = v15;
        if ( !v15 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v16 = 326;
      }
    }
    else
    {
      v19 = a1 - 3;
      if ( (unsigned int)v19 >= 2 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(v19, a1);
LABEL_43:
        v15 = Int_FWCloseGPOPolicyStore(a5, 1);
        v11 = v15;
        if ( !v15 )
          goto LABEL_28;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v16 = 329;
        goto LABEL_26;
      }
      v20 = 0;
      v21 = *(_QWORD *)(a5 + 56);
      if ( a2 )
      {
        LOBYTE(v20) = a1 != 3;
        v22 = FwDeleteAllSets(v21, v20, a7);
        v15 = FwHResultToWindowsError(v22);
        v11 = v15;
        if ( !v15 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v16 = 327;
      }
      else
      {
        LOBYTE(v20) = a1 != 3;
        v23 = FwDeleteSet(v21, v20, a7, a6);
        v15 = FwHResultToWindowsError(v23);
        v11 = v15;
        if ( !v15 )
          goto LABEL_43;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v16 = 328;
      }
    }
LABEL_26:
    v17 = v15;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v10 + 2), v16, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v17);
LABEL_28:
    v10 = WPP_GLOBAL_Control;
LABEL_29:
    v13 = a5;
    goto LABEL_30;
  }
  if ( !*(_QWORD *)(a5 + 32) || (v11 = 0, !*(_QWORD *)(a5 + 40)) )
  {
    v17 = 87;
    v11 = 87;
    if ( v10 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
      goto LABEL_112;
    v16 = 317;
    goto LABEL_27;
  }
  if ( a1 < 2 )
  {
LABEL_93:
    v31 = *(_QWORD *)(a5 + 40);
    v32 = *(_QWORD *)(a5 + 32);
    if ( v8 )
    {
      if ( v14 )
        a3 = a4;
      v33 = a3(v32, v31);
      v11 = v33;
      if ( !v33 )
        goto LABEL_108;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v33);
        v10 = WPP_GLOBAL_Control;
      }
      v13 = a5;
    }
    else
    {
      if ( v14 )
        a3 = a4;
      v34 = ((__int64 (__fastcall *)(__int64, __int64, __int64))a3)(v32, v31, a6);
      v11 = v34;
      if ( !v34 )
        goto LABEL_108;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v34);
        v10 = WPP_GLOBAL_Control;
      }
      v13 = a5;
    }
    goto LABEL_30;
  }
  if ( a1 == 2 )
  {
    if ( *(_WORD *)(a5 + 2) < 0x20Au )
    {
      v11 = 50;
      if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v10 + 2), 318, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 50);
        v10 = WPP_GLOBAL_Control;
      }
      v13 = a5;
      goto LABEL_30;
    }
    goto LABEL_93;
  }
  if ( a1 - 3 >= 2 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(v10, a1);
LABEL_108:
    v10 = WPP_GLOBAL_Control;
    v13 = a5;
    goto LABEL_30;
  }
  v27 = *(_QWORD *)(a5 + 40);
  v28 = *(_QWORD *)(a5 + 32);
  if ( v8 )
  {
    if ( v14 )
      a3 = a4;
    v29 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))a3)(v28, v27, a7);
    v11 = v29;
    if ( !v29 )
      goto LABEL_108;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v29);
      v10 = WPP_GLOBAL_Control;
    }
    v13 = a5;
  }
  else
  {
    if ( v14 )
      a3 = a4;
    v30 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))a3)(v28, v27, a7, a6);
    v11 = v30;
    if ( !v30 )
      goto LABEL_108;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v30);
      v10 = WPP_GLOBAL_Control;
    }
    v13 = a5;
  }
LABEL_30:
  if ( (v11 & 0xFFFFFFFD) != 0 && v13 && *(_DWORD *)(v13 + 4) == 2 )
  {
    Int_FWCleanupGPOPolicyStore(v13);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 330, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  return v11;
}

```

## disassembly

```asm
0x180005748  mov     rax, rsp
0x18000574b  mov     [rax+8], rbx
0x18000574f  mov     [rax+18h], rsi
0x180005753  mov     [rax+20h], r9
0x180005757  mov     [rax+10h], edx
0x18000575a  push    rdi
0x18000575b  push    r12
0x18000575d  push    r13
0x18000575f  push    r14
0x180005761  push    r15
0x180005763  sub     rsp, 40h
0x180005767  mov     r12, r8
0x18000576a  mov     r9d, edx
0x18000576d  mov     r15d, ecx
0x180005770  lea     rsi, WPP_GLOBAL_Control
0x180005777  mov     rcx, cs:WPP_GLOBAL_Control
0x18000577e  lea     r14, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180005785  cmp     rcx, rsi
0x180005788  jz      short loc_1800057AD
0x18000578a  test    byte ptr [rcx+1Ch], 8
0x18000578e  jz      short loc_1800057AD
0x180005790  mov     edx, 139h
0x180005795  mov     r8, r14
0x180005798  mov     rcx, [rcx+10h]
0x18000579c  call    WPP_SF_
0x1800057a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057a8  mov     r9d, [rsp+68h+arg_8]
0x1800057ad  xor     eax, eax
0x1800057af  mov     [rsp+68h+var_30], rax
0x1800057b4  mov     r13, [rsp+68h+arg_20]
0x1800057bc  test    r13, r13
0x1800057bf  jnz     short loc_1800057FD
0x1800057c1  lea     r9d, [rax+57h]
0x1800057c5  mov     ebx, r9d
0x1800057c8  cmp     rcx, rsi
0x1800057cb  jz      loc_180005DFB
0x1800057d1  lea     edi, [rax+1]
0x1800057d4  test    [rcx+1Ch], dil
0x1800057d8  jz      loc_180005DFB
0x1800057de  mov     edx, 13Ah
0x1800057e3  mov     r8, r14
0x1800057e6  mov     rcx, [rcx+10h]
0x1800057ea  call    WPP_SF_d
0x1800057ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057f6  xor     eax, eax
0x1800057f8  jmp     loc_1800058DB
0x1800057fd  test    r9d, r9d
0x180005800  jnz     short loc_180005833
0x180005802  cmp     [rsp+68h+arg_28], rax
0x18000580a  jnz     short loc_180005833
0x18000580c  mov     r9d, 57h ; 'W'
0x180005812  mov     ebx, r9d
0x180005815  cmp     rcx, rsi
0x180005818  jz      loc_180005DFB
0x18000581e  lea     edi, [r9-56h]
0x180005822  test    [rcx+1Ch], dil
0x180005826  jz      loc_180005DFB
0x18000582c  mov     edx, 13Bh
0x180005831  jmp     short loc_1800057E3
0x180005833  lea     eax, [r15-3]
0x180005837  mov     edi, 1
0x18000583c  cmp     eax, edi
0x18000583e  ja      short loc_180005871
0x180005840  mov     eax, [rsp+68h+arg_30]
0x180005847  dec     eax
0x180005849  cmp     eax, edi
0x18000584b  jbe     short loc_180005871
0x18000584d  lea     r9d, [rdi+56h]
0x180005851  mov     ebx, r9d
0x180005854  cmp     rcx, rsi
0x180005857  jz      loc_180005DFB
0x18000585d  test    [rcx+1Ch], dil
0x180005861  jz      loc_180005DFB
0x180005867  mov     edx, 13Ch
0x18000586c  jmp     loc_1800057E3
0x180005871  mov     rax, r13
0x180005874  mov     [rsp+68h+var_30], rax
0x180005879  mov     [rsp+68h+arg_20], rax
0x180005881  mov     r8d, [r13+4]
0x180005885  cmp     r8d, edi
0x180005888  jbe     loc_180005B21
0x18000588e  cmp     r8d, 2
0x180005892  jz      short loc_180005899
0x180005894  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClient->HandleType == FWINT_CLIENT_HANDLE_GPO")
0x180005899  mov     rcx, r13
0x18000589c  call    Int_FWOpenGPOPolicyStore
0x1800058a1  mov     ebx, eax
0x1800058a3  test    eax, eax
0x1800058a5  jz      loc_180005936
0x1800058ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058b2  cmp     rcx, rsi
0x1800058b5  jz      short loc_1800058D8
0x1800058b7  test    [rcx+1Ch], dil
0x1800058bb  jz      short loc_1800058D8
0x1800058bd  mov     edx, 144h
0x1800058c2  mov     r9d, eax
0x1800058c5  mov     r8, r14
0x1800058c8  mov     rcx, [rcx+10h]
0x1800058cc  call    WPP_SF_d
0x1800058d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058d8  mov     rax, r13
0x1800058db  test    ebx, 0FFFFFFFDh
0x1800058e1  jz      short loc_1800058FD
0x1800058e3  test    rax, rax
0x1800058e6  jz      short loc_1800058FD
0x1800058e8  cmp     dword ptr [rax+4], 2
0x1800058ec  jnz     short loc_1800058FD
0x1800058ee  mov     rcx, rax
0x1800058f1  call    Int_FWCleanupGPOPolicyStore
0x1800058f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058fd  cmp     rcx, rsi
0x180005900  jz      short loc_180005919
0x180005902  test    byte ptr [rcx+1Ch], 8
0x180005906  jz      short loc_180005919
0x180005908  mov     edx, 14Ah
0x18000590d  mov     r8, r14
0x180005910  mov     rcx, [rcx+10h]
0x180005914  call    WPP_SF_
0x180005919  mov     eax, ebx
0x18000591b  lea     r11, [rsp+68h+var_28]
0x180005920  mov     rbx, [r11+30h]
0x180005924  mov     rsi, [r11+40h]
0x180005928  mov     rsp, r11
0x18000592b  pop     r15
0x18000592d  pop     r14
0x18000592f  pop     r13
0x180005931  pop     r12
0x180005933  pop     rdi
0x180005934  retn
0x180005936  cmp     qword ptr [r13+38h], 0
0x18000593b  jnz     short loc_180005942
0x18000593d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClient->PolicyHandle != NULL")
0x180005942  mov     ecx, r15d
0x180005945  test    r15d, r15d
0x180005948  jz      loc_180005A5F
0x18000594e  sub     ecx, edi
0x180005950  jz      loc_180005A5F
0x180005956  sub     ecx, edi
0x180005958  jz      loc_180005A5F
0x18000595e  sub     ecx, edi
0x180005960  jz      short loc_1800059A9
0x180005962  cmp     ecx, edi
0x180005964  jz      short loc_1800059A9
0x180005966  mov     edx, r15d; __annotation("Debug", "TelemetryAssert", "FALSE", "objectType is invalid. HandleType is not LRPC or RRPC")
0x180005969  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000596e  xor     r8d, r8d
0x180005971  mov     edx, edi
0x180005973  mov     rcx, r13
0x180005976  call    Int_FWCloseGPOPolicyStore
0x18000597b  mov     ebx, eax
0x18000597d  test    eax, eax
0x18000597f  jz      loc_1800058D1
0x180005985  mov     rcx, cs:WPP_GLOBAL_Control
0x18000598c  cmp     rcx, rsi
0x18000598f  jz      loc_1800058D8
0x180005995  test    [rcx+1Ch], dil
0x180005999  jz      loc_1800058D8
0x18000599f  mov     edx, 149h
0x1800059a4  jmp     loc_1800058C2
0x1800059a9  xor     edx, edx
0x1800059ab  mov     r8d, [rsp+68h+arg_30]
0x1800059b3  mov     rcx, [r13+38h]
0x1800059b7  cmp     [rsp+68h+arg_8], edx
0x1800059bb  jz      short loc_180005A08
0x1800059bd  cmp     r15d, 3
0x1800059c1  setnz   dl
0x1800059c4  call    cs:__imp_FwDeleteAllSets
0x1800059cb  nop     dword ptr [rax+rax+00h]
0x1800059d0  mov     ecx, eax
0x1800059d2  call    cs:__imp_FwHResultToWindowsError
0x1800059d9  nop     dword ptr [rax+rax+00h]
0x1800059de  mov     ebx, eax
0x1800059e0  test    eax, eax
0x1800059e2  jz      short loc_18000596E
0x1800059e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059eb  cmp     rcx, rsi
0x1800059ee  jz      loc_1800058D8
0x1800059f4  test    [rcx+1Ch], dil
0x1800059f8  jz      loc_1800058D8
0x1800059fe  mov     edx, 147h
0x180005a03  jmp     loc_1800058C2
0x180005a08  cmp     r15d, 3
0x180005a0c  setnz   dl
0x180005a0f  mov     r9, [rsp+68h+arg_28]
0x180005a17  call    cs:__imp_FwDeleteSet
0x180005a1e  nop     dword ptr [rax+rax+00h]
0x180005a23  mov     ecx, eax
0x180005a25  call    cs:__imp_FwHResultToWindowsError
0x180005a2c  nop     dword ptr [rax+rax+00h]
0x180005a31  mov     ebx, eax
0x180005a33  test    eax, eax
0x180005a35  jz      loc_18000596E
0x180005a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a42  cmp     rcx, rsi
0x180005a45  jz      loc_1800058D8
0x180005a4b  test    [rcx+1Ch], dil
0x180005a4f  jz      loc_1800058D8
0x180005a55  mov     edx, 148h
0x180005a5a  jmp     loc_1800058C2
0x180005a5f  xor     edx, edx
0x180005a61  cmp     [rsp+68h+arg_8], edx
0x180005a65  jz      short loc_180005AC0
0x180005a67  test    r15d, r15d
0x180005a6a  jz      short loc_180005A74
0x180005a6c  cmp     r15d, edi
0x180005a6f  setnz   dl
0x180005a72  add     edx, edi
0x180005a74  mov     rcx, [r13+38h]
0x180005a78  call    cs:__imp_FwDeleteAllRules
0x180005a7f  nop     dword ptr [rax+rax+00h]
0x180005a84  mov     ecx, eax
0x180005a86  call    cs:__imp_FwHResultToWindowsError
0x180005a8d  nop     dword ptr [rax+rax+00h]
0x180005a92  mov     ebx, eax
0x180005a94  test    eax, eax
0x180005a96  jz      loc_18000596E
0x180005a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aa3  cmp     rcx, rsi
0x180005aa6  jz      loc_1800058D8
0x180005aac  test    [rcx+1Ch], dil
0x180005ab0  jz      loc_1800058D8
0x180005ab6  mov     edx, 145h
0x180005abb  jmp     loc_1800058C2
0x180005ac0  test    r15d, r15d
0x180005ac3  jz      short loc_180005ACD
0x180005ac5  cmp     r15d, edi
0x180005ac8  setnz   dl
0x180005acb  add     edx, edi
0x180005acd  mov     r8, [rsp+68h+arg_28]
0x180005ad5  mov     rcx, [r13+38h]
0x180005ad9  call    cs:__imp_FwDeleteRule
0x180005ae0  nop     dword ptr [rax+rax+00h]
0x180005ae5  mov     ecx, eax
0x180005ae7  call    cs:__imp_FwHResultToWindowsError
0x180005aee  nop     dword ptr [rax+rax+00h]
0x180005af3  mov     ebx, eax
0x180005af5  test    eax, eax
0x180005af7  jz      loc_18000596E
0x180005afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b04  cmp     rcx, rsi
0x180005b07  jz      loc_1800058D8
0x180005b0d  test    [rcx+1Ch], dil
0x180005b11  jz      loc_1800058D8
0x180005b17  mov     edx, 146h
0x180005b1c  jmp     loc_1800058C2
0x180005b21  mov     r10, [r13+20h]
0x180005b25  test    r10, r10
0x180005b28  jz      loc_180005DDD
0x180005b2e  xor     ebx, ebx
0x180005b30  mov     r11, [r13+28h]
0x180005b34  test    r11, r11
0x180005b37  jz      loc_180005DDD
0x180005b3d  mov     edx, r15d
0x180005b40  test    r15d, r15d
0x180005b43  jz      loc_180005C8C
0x180005b49  sub     edx, 1
0x180005b4c  jz      loc_180005C8C
0x180005b52  sub     edx, 1
0x180005b55  jz      loc_180005C47
0x180005b5b  sub     edx, 1
0x180005b5e  jz      short loc_180005B72
0x180005b60  cmp     edx, 1
0x180005b63  jz      short loc_180005B72
0x180005b65  mov     edx, r15d; __annotation("Debug", "TelemetryAssert", "FALSE", "objectType is invalid. HandleType is LRPC or RRPC")
0x180005b68  call    MicrosoftTelemetryAssertTriggeredArgs
0x180005b6d  jmp     loc_180005D4D
0x180005b72  mov     rdx, r11
0x180005b75  mov     rcx, r10
0x180005b78  test    r9d, r9d
0x180005b7b  jz      short loc_180005BDE
0x180005b7d  test    r8d, r8d
0x180005b80  cmovnz  r12, [rsp+68h+arg_18]
0x180005b89  mov     r8d, [rsp+68h+arg_30]
0x180005b91  mov     rax, r12
0x180005b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b99  mov     ebx, eax
0x180005b9b  mov     [rsp+68h+var_38], eax
0x180005b9f  test    eax, eax
0x180005ba1  jz      loc_180005D4D
0x180005ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bae  cmp     rcx, rsi
0x180005bb1  jz      short loc_180005BD4
0x180005bb3  test    [rcx+1Ch], dil
0x180005bb7  jz      short loc_180005BD4
0x180005bb9  mov     edx, 141h
0x180005bbe  mov     r9d, eax
0x180005bc1  mov     r8, r14
0x180005bc4  mov     rcx, [rcx+10h]
0x180005bc8  call    WPP_SF_d
0x180005bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bd4  mov     rax, [rsp+68h+var_30]
0x180005bd9  jmp     loc_1800058DB
0x180005bde  test    r8d, r8d
0x180005be1  cmovnz  r12, [rsp+68h+arg_18]
0x180005bea  mov     r9, [rsp+68h+arg_28]
0x180005bf2  mov     r8d, [rsp+68h+arg_30]
0x180005bfa  mov     rax, r12
0x180005bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c02  mov     ebx, eax
0x180005c04  mov     [rsp+68h+var_38], eax
  ... truncated ...
```
