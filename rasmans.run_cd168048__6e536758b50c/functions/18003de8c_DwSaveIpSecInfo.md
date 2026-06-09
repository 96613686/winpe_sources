# DwSaveIpSecInfo

- ea: `0x18003de8c`
- end: `0x18003e516`
- name: `DwSaveIpSecInfo`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180015b10`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18003de8c`
- `0x18004236c`
- `0x180049c18`
- `0x1800a2844`
- `0x1800a2a50`
- `0x1800a2b38`
- `0x1800e8e72`

## import_xrefs

- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003e061`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003e419`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003e061`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003e419`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18003dfce`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18003dfce`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003df8c`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003e433`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003df8c`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003e433`
- `fwpuclnt!IPsecSaEnum0` at `0x18003e02b`
- `fwpuclnt!IPsecSaEnum0` at `0x18003e02b`
- `WS2_32!__imp_htonl` at `0x18003e176`
- `WS2_32!__imp_htonl` at `0x18003e176`

## string_xrefs

- `0x18003dffa`: `DwQueryAssociations: Ikeext service is not running`

## pseudocode

```c
__int64 __fastcall DwSaveIpSecInfo(__int64 a1)
{
  __int128 v2; // xmm6
  int v3; // ebx
  __int64 UserData; // rax
  void *v5; // rax
  int v6; // ecx
  FWP_DIRECTION v7; // ebx
  UINT32 v8; // r12d
  int v9; // esi
  HANDLE v10; // rdx
  unsigned int v11; // edi
  _QWORD *v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // r14
  __int64 v15; // r15
  __int64 v16; // rcx
  u_long v17; // r13d
  u_long *v18; // r12
  __int64 v19; // rdx
  __int16 v20; // r11
  unsigned int v21; // r9d
  __int64 v22; // rdx
  __int16 v23; // r10
  __int64 v24; // r8
  int v25; // eax
  u_long v26; // ecx
  u_long v27; // eax
  int v28; // edi
  __int16 v29; // r11
  __int64 v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // r10d
  __int64 v33; // rdx
  __int16 v34; // r9
  __int64 v35; // r8
  const CHAR *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rdx
  unsigned int v39; // r8d
  __int64 v40; // r9
  __int64 *v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rcx
  void *p; // [rsp+38h] [rbp-69h] BYREF
  int v46; // [rsp+40h] [rbp-61h]
  int v47; // [rsp+44h] [rbp-5Dh]
  HANDLE enumHandle; // [rsp+48h] [rbp-59h] BYREF
  IPSEC_SA_ENUM_TEMPLATE0 enumTemplate; // [rsp+50h] [rbp-51h] BYREF
  int v50; // [rsp+54h] [rbp-4Dh]
  __int128 v51; // [rsp+58h] [rbp-49h]
  __int64 v52; // [rsp+70h] [rbp-31h]
  __int128 Buf2; // [rsp+78h] [rbp-29h] BYREF
  int v54; // [rsp+88h] [rbp-19h]
  __int128 Buf1; // [rsp+98h] [rbp-9h] BYREF
  int v57; // [rsp+110h] [rbp+6Fh] BYREF
  UINT32 numEntriesReturned; // [rsp+118h] [rbp+77h] BYREF
  DWORD v59; // [rsp+120h] [rbp+7Fh]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 543, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  v2 = 0;
  v3 = 0;
  v52 = a1 + 1080;
  v51 = 0;
  UserData = GetUserData(a1 + 1080, 13);
  if ( UserData )
  {
    v2 = *(_OWORD *)(UserData + 24);
    v3 = *(_DWORD *)(UserData + 40);
    v51 = v2;
  }
  else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
         && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 544, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  v5 = 0;
  v6 = *(_DWORD *)(a1 + 32) & 1;
  v54 = v3;
  Buf2 = v2;
  v7 = v6 ^ 1;
  numEntriesReturned = 0;
  v50 = v6 ^ 1;
  v8 = 0;
  enumHandle = 0;
  v9 = 0;
  p = 0;
  enumTemplate.saDirection = FWP_DIRECTION_OUTBOUND;
  v47 = v6;
  v46 = 0;
  v57 = 0;
  while ( 1 )
  {
    if ( v5 )
    {
      FwpmFreeMemory0(&p);
      numEntriesReturned = 0;
    }
    enumTemplate.saDirection = v7;
    p = 0;
    RasIpsecTrace("DwQueryAssociations");
    DwInitializeIpSec(0);
    v10 = enumHandle;
    if ( !enumHandle )
    {
      v59 = IPsecSaCreateEnumHandle0(gFwpEngineHandle, &enumTemplate, &enumHandle);
      v11 = v59;
      if ( v59 )
      {
        RasIpsecTrace("DwQueryAssociations: Failed to get enum handle %d");
        if ( !IsServiceRunning() )
        {
          RasIpsecTrace("DwQueryAssociations: Ikeext service is not running");
          v11 = 827;
LABEL_23:
          v59 = v11;
          goto LABEL_24;
        }
        goto LABEL_24;
      }
      v10 = enumHandle;
    }
    v59 = IPsecSaEnum0(gFwpEngineHandle, v10, 0xAu, (IPSEC_SA_DETAILS0 ***)&p, &numEntriesReturned);
    v11 = v59;
    if ( v59 )
    {
      RasIpsecTrace("DwQueryAssociations: Failed to enum IPSec SA %d");
    }
    else if ( !numEntriesReturned )
    {
      IPsecSaDestroyEnumHandle0(gFwpEngineHandle, enumHandle);
      enumHandle = 0;
      v11 = 232;
      goto LABEL_23;
    }
LABEL_24:
    RasIpsecTrace("DwQueryAssociation rc=0x%x");
    v12 = p;
    if ( v11 || !p )
      break;
    if ( (_DWORD)v51 == 1 )
    {
      v8 = 0;
      v59 = 0;
      if ( numEntriesReturned )
      {
        v13 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
        v14 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
        v15 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
        while ( 1 )
        {
          v16 = v12[v8];
          if ( *(_DWORD *)(v16 + 4) )
          {
            v17 = *(_DWORD *)(v16 + 28);
            v18 = (u_long *)(v16 + 12);
          }
          else
          {
            v17 = *(_DWORD *)(v16 + 12);
            v18 = (u_long *)(v16 + 28);
          }
          v19 = *(_QWORD *)(v16 + 160);
          v20 = 0;
          v21 = *(_DWORD *)(v19 + 112);
          if ( !v21 )
            goto LABEL_45;
          v22 = *(_QWORD *)(v19 + 120);
          v23 = 0;
          v24 = 0;
          do
          {
            if ( *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1 == *(_QWORD *)(v22 + 40 * v24)
              && v13 == *(_QWORD *)(v22 + 40 * v24 + 8) )
            {
              v23 = *(_WORD *)(v22 + 40 * v24 + 32);
            }
            else if ( v15 == *(_QWORD *)(v22 + 40 * v24) && v14 == *(_QWORD *)(v22 + 40 * v24 + 8) )
            {
              v20 = *(_WORD *)(v22 + 40 * v24 + 32);
            }
            v24 = (unsigned int)(v24 + 1);
          }
          while ( (unsigned int)v24 < v21 );
          v12 = p;
          if ( v23 == 1701 )
          {
            v25 = v47;
          }
          else
          {
LABEL_45:
            v25 = v47;
            if ( !v47 || v20 != 1701 )
              goto LABEL_51;
          }
          if ( v25 )
            v26 = *v18;
          else
            v26 = v17;
          v27 = htonl(v26);
          v12 = p;
          if ( DWORD1(v51) == v27 )
          {
            v8 = v59;
            goto LABEL_72;
          }
          v15 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
          v14 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
          v13 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
LABEL_51:
          v8 = v59 + 1;
          v59 = v8;
          if ( v8 >= numEntriesReturned )
            goto LABEL_72;
        }
      }
    }
    else if ( (_DWORD)v51 == 2 )
    {
      v8 = 0;
      if ( numEntriesReturned )
      {
        v28 = v47;
        do
        {
          v29 = 0;
          v30 = v12[v8];
          v31 = *(_QWORD *)(v30 + 160);
          v32 = *(_DWORD *)(v31 + 112);
          Buf1 = *(_OWORD *)(v30 + 28);
          if ( v32 )
          {
            v33 = *(_QWORD *)(v31 + 120);
            v34 = 0;
            v35 = 0;
            do
            {
              if ( *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1 == *(_QWORD *)(v33 + 40 * v35)
                && *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4 == *(_QWORD *)(v33 + 40 * v35 + 8) )
              {
                v34 = *(_WORD *)(v33 + 40 * v35 + 32);
              }
              else if ( *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1 == *(_QWORD *)(v33 + 40 * v35)
                     && *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4 == *(_QWORD *)(v33 + 40 * v35 + 8) )
              {
                v29 = *(_WORD *)(v33 + 40 * v35 + 32);
              }
              v35 = (unsigned int)(v35 + 1);
            }
            while ( (unsigned int)v35 < v32 );
            if ( v34 == 1701 )
              goto LABEL_126;
          }
          if ( v28 && v29 == 1701 )
          {
LABEL_126:
            if ( !memcmp_0(&Buf1, (char *)&Buf2 + 4, 0x10u) )
              break;
          }
          ++v8;
        }
        while ( v8 < numEntriesReturned );
        v11 = v59;
LABEL_72:
        v9 = v46;
      }
    }
    if ( v8 == numEntriesReturned )
    {
      v36 = "No match found for the SA";
      goto LABEL_82;
    }
    v37 = 0;
    v38 = v12[v8];
    v39 = *(_DWORD *)(v38 + 104);
    if ( v39 )
    {
      v40 = *(_QWORD *)(v38 + 112);
      do
      {
        v9 = *(_DWORD *)(v40 + 16LL * (unsigned int)v37 + 4);
        v46 = v9;
        if ( v9 == 3 )
          goto LABEL_85;
        if ( v9 == 4 )
          goto LABEL_84;
        v37 = (unsigned int)(v37 + 1);
      }
      while ( (unsigned int)v37 < v39 );
    }
    if ( (_DWORD)v37 != v39 )
    {
      if ( v9 == 3 )
        goto LABEL_85;
LABEL_84:
      v41 = 0;
      if ( v9 == 4 )
LABEL_85:
        v41 = *(__int64 **)(*(_QWORD *)(v38 + 112) + 16 * v37 + 8);
      RasIpsecTrace("CipherId = (%d, %d)");
      if ( *v41 == 0x100000001LL && g_dwAllowL2TPWeakCrypto )
      {
        v57 = 1;
      }
      else
      {
        v42 = *v41;
        if ( *v41 == 0x200000002LL )
        {
          v57 = 4;
        }
        else
        {
          switch ( v42 )
          {
            case 0x300000003LL:
              v57 = 16;
              break;
            case 0x500000005LL:
              v57 = 32;
              break;
            case 0x400000004LL:
              v57 = 64;
              break;
            case 0x600000003LL:
              v57 = 128;
              break;
            case 0x700000004LL:
              v57 = 256;
              break;
            case 0x800000005LL:
              v57 = 512;
              break;
            default:
              if ( v42 == 0x100000001LL && !g_dwAllowL2TPWeakCrypto )
              {
                RasIpsecTrace("Cipher Id obtained is not supported.");
                goto LABEL_107;
              }
              break;
          }
        }
      }
      goto LABEL_108;
    }
    v36 = "No Encryption algorithm was returned";
LABEL_82:
    RasIpsecTrace(v36);
    v5 = p;
    v7 = v50;
  }
  RasIpsecTrace("QuerySA returned dwErr=0x%x, pSAList=0x%x");
LABEL_107:
  v11 = 774;
LABEL_108:
  if ( enumHandle )
  {
    IPsecSaDestroyEnumHandle0(gFwpEngineHandle, enumHandle);
    enumHandle = 0;
  }
  if ( p )
    FwpmFreeMemory0(&p);
  if ( v11
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 545, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v11);
  }
  SetUserData(v52, 7u, &v57, 4u);
  v43 = *(_QWORD *)(a1 + 1064);
  if ( v43 )
    SetUserData(v43 + 32, 5u, &v57, 4u);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 546, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18003de8c  mov     rax, rsp
0x18003de8f  mov     [rax+8], rcx
0x18003de93  push    rbp
0x18003de94  push    rbx
0x18003de95  push    rsi
0x18003de96  push    rdi
0x18003de97  push    r12
0x18003de99  push    r13
0x18003de9b  push    r14
0x18003de9d  push    r15
0x18003de9f  lea     rbp, [rax-5Fh]
0x18003dea3  sub     rsp, 0B8h
0x18003deaa  movaps  xmmword ptr [rax-58h], xmm6
0x18003deae  mov     r14, rcx
0x18003deb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003deb8  lea     rsi, WPP_GLOBAL_Control
0x18003debf  mov     edi, 2000h
0x18003dec4  cmp     rcx, rsi
0x18003dec7  jz      short loc_18003DEE9
0x18003dec9  test    [rcx+1Ch], edi
0x18003decc  jz      short loc_18003DEE9
0x18003dece  cmp     byte ptr [rcx+19h], 6
0x18003ded2  jb      short loc_18003DEE9
0x18003ded4  mov     rcx, [rcx+10h]
0x18003ded8  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003dedf  mov     edx, 21Fh
0x18003dee4  call    WPP_SF_
0x18003dee9  lea     r15, [r14+438h]
0x18003def0  xorps   xmm6, xmm6
0x18003def3  xor     ebx, ebx
0x18003def5  mov     [rbp+57h+var_88], r15
0x18003def9  mov     rcx, r15
0x18003defc  movups  [rbp+57h+var_A0], xmm6
0x18003df00  lea     edx, [rbx+0Dh]
0x18003df03  call    GetUserData
0x18003df08  xor     r13d, r13d
0x18003df0b  test    rax, rax
0x18003df0e  jz      short loc_18003DF1D
0x18003df10  movups  xmm6, xmmword ptr [rax+18h]
0x18003df14  mov     ebx, [rax+28h]
0x18003df17  movups  [rbp+57h+var_A0], xmm6
0x18003df1b  jmp     short loc_18003DF49
0x18003df1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df24  cmp     rcx, rsi
0x18003df27  jz      short loc_18003DF49
0x18003df29  test    [rcx+1Ch], edi
0x18003df2c  jz      short loc_18003DF49
0x18003df2e  cmp     byte ptr [rcx+19h], 3
0x18003df32  jb      short loc_18003DF49
0x18003df34  mov     rcx, [rcx+10h]
0x18003df38  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003df3f  mov     edx, 220h
0x18003df44  call    WPP_SF_
0x18003df49  mov     ecx, [r14+20h]
0x18003df4d  mov     rax, r13
0x18003df50  and     ecx, 1
0x18003df53  mov     [rbp+57h+var_70], ebx
0x18003df56  mov     ebx, ecx
0x18003df58  movaps  [rbp+57h+Buf2], xmm6
0x18003df5c  xor     ebx, 1
0x18003df5f  mov     [rbp+57h+numEntriesReturned], r13d
0x18003df63  mov     [rbp+57h+var_A4], ebx
0x18003df66  mov     r12d, r13d
0x18003df69  mov     [rbp+57h+enumHandle], r13
0x18003df6d  mov     esi, r13d
0x18003df70  mov     [rbp+57h+p], rax
0x18003df74  mov     [rbp+57h+enumTemplate.saDirection], r13d
0x18003df78  mov     [rbp+57h+var_B4], ecx
0x18003df7b  mov     [rbp+57h+var_B8], r13d
0x18003df7f  mov     [rbp+57h+arg_8], r13d
0x18003df83  test    rax, rax
0x18003df86  jz      short loc_18003DF9C
0x18003df88  lea     rcx, [rbp+57h+p]; p
0x18003df8c  call    cs:__imp_FwpmFreeMemory0
0x18003df93  nop     dword ptr [rax+rax+00h]
0x18003df98  mov     [rbp+57h+numEntriesReturned], r13d
0x18003df9c  lea     rcx, aDwqueryassocia_2; "DwQueryAssociations"
0x18003dfa3  mov     [rbp+57h+enumTemplate.saDirection], ebx
0x18003dfa6  mov     [rbp+57h+p], r13
0x18003dfaa  call    RasIpsecTrace
0x18003dfaf  xor     ecx, ecx
0x18003dfb1  call    DwInitializeIpSec
0x18003dfb6  mov     rdx, [rbp+57h+enumHandle]
0x18003dfba  test    rdx, rdx
0x18003dfbd  jnz     short loc_18003E011
0x18003dfbf  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18003dfc6  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x18003dfca  lea     rdx, [rbp+57h+enumTemplate]; enumTemplate
0x18003dfce  call    cs:__imp_IPsecSaCreateEnumHandle0
0x18003dfd5  nop     dword ptr [rax+rax+00h]
0x18003dfda  mov     [rbp+57h+arg_18], eax
0x18003dfdd  mov     edi, eax
0x18003dfdf  test    eax, eax
0x18003dfe1  jz      short loc_18003E00D
0x18003dfe3  mov     edx, eax
0x18003dfe5  lea     rcx, aDwqueryassocia_3; "DwQueryAssociations: Failed to get enum"...
0x18003dfec  call    RasIpsecTrace
0x18003dff1  call    IsServiceRunning
0x18003dff6  test    eax, eax
0x18003dff8  jnz     short loc_18003E079
0x18003dffa  lea     rcx, aDwqueryassocia_0; "DwQueryAssociations: Ikeext service is "...
0x18003e001  call    RasIpsecTrace
0x18003e006  mov     edi, 33Bh
0x18003e00b  jmp     short loc_18003E076
0x18003e00d  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x18003e011  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18003e018  lea     rax, [rbp+57h+numEntriesReturned]
0x18003e01c  lea     r9, [rbp+57h+p]; entries
0x18003e020  mov     [rsp+20h], rax; numEntriesReturned
0x18003e025  mov     r8d, 0Ah; numEntriesRequested
0x18003e02b  call    cs:__imp_IPsecSaEnum0
0x18003e032  nop     dword ptr [rax+rax+00h]
0x18003e037  mov     [rbp+57h+arg_18], eax
0x18003e03a  mov     edi, eax
0x18003e03c  test    eax, eax
0x18003e03e  jz      short loc_18003E050
0x18003e040  mov     edx, eax
0x18003e042  lea     rcx, aDwqueryassocia; "DwQueryAssociations: Failed to enum IPS"...
0x18003e049  call    RasIpsecTrace
0x18003e04e  jmp     short loc_18003E079
0x18003e050  cmp     [rbp+57h+numEntriesReturned], r13d
0x18003e054  jnz     short loc_18003E079
0x18003e056  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x18003e05a  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18003e061  call    cs:__imp_IPsecSaDestroyEnumHandle0
0x18003e068  nop     dword ptr [rax+rax+00h]
0x18003e06d  mov     [rbp+57h+enumHandle], r13
0x18003e071  mov     edi, 0E8h
0x18003e076  mov     [rbp+57h+arg_18], edi
0x18003e079  mov     edx, edi
0x18003e07b  lea     rcx, aDwqueryassocia_1; "DwQueryAssociation rc=0x%x"
0x18003e082  call    RasIpsecTrace
0x18003e087  mov     rbx, [rbp+57h+p]
0x18003e08b  test    edi, edi
0x18003e08d  jnz     loc_18003E3F3
0x18003e093  test    rbx, rbx
0x18003e096  jz      loc_18003E3F3
0x18003e09c  cmp     dword ptr [rbp+57h+var_A0], 1
0x18003e0a0  jnz     loc_18003E1C6
0x18003e0a6  mov     r12d, r13d
0x18003e0a9  mov     [rbp+57h+arg_18], r13d
0x18003e0ad  cmp     [rbp+57h+numEntriesReturned], r13d
0x18003e0b1  jbe     loc_18003E2A6
0x18003e0b7  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18003e0be  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18003e0c5  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18003e0cc  mov     eax, r12d
0x18003e0cf  mov     rcx, [rbx+rax*8]
0x18003e0d3  cmp     [rcx+4], r13d
0x18003e0d7  jnz     short loc_18003E0E3
0x18003e0d9  mov     r13d, [rcx+0Ch]
0x18003e0dd  lea     r12, [rcx+1Ch]
0x18003e0e1  jmp     short loc_18003E0EB
0x18003e0e3  mov     r13d, [rcx+1Ch]
0x18003e0e7  lea     r12, [rcx+0Ch]
0x18003e0eb  mov     rdx, [rcx+0A0h]
0x18003e0f2  xor     r11d, r11d
0x18003e0f5  mov     r9d, [rdx+70h]
0x18003e0f9  test    r9d, r9d
0x18003e0fc  jz      short loc_18003E15F
0x18003e0fe  mov     rdx, [rdx+78h]
0x18003e102  xor     r10d, r10d
0x18003e105  mov     rbx, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18003e10c  xor     r8d, r8d
0x18003e10f  lea     rcx, [r8+r8*4]
0x18003e113  cmp     rbx, [rdx+rcx*8]
0x18003e117  jnz     short loc_18003E128
0x18003e119  cmp     rsi, [rdx+rcx*8+8]
0x18003e11e  jnz     short loc_18003E128
0x18003e120  movzx   r10d, word ptr [rdx+rcx*8+20h]
0x18003e126  jmp     short loc_18003E13B
0x18003e128  cmp     r15, [rdx+rcx*8]
0x18003e12c  jnz     short loc_18003E13B
0x18003e12e  cmp     r14, [rdx+rcx*8+8]
0x18003e133  jnz     short loc_18003E13B
0x18003e135  movzx   r11d, word ptr [rdx+rcx*8+20h]
0x18003e13b  inc     r8d
0x18003e13e  cmp     r8d, r9d
0x18003e141  jb      short loc_18003E10F
0x18003e143  mov     rbx, [rbp+57h+p]
0x18003e147  mov     ecx, 6A5h
0x18003e14c  cmp     cx, r10w
0x18003e150  jnz     short loc_18003E164
0x18003e152  mov     eax, [rbp+57h+var_B4]
0x18003e155  test    eax, eax
0x18003e157  jz      short loc_18003E173
0x18003e159  mov     ecx, [r12]
0x18003e15d  jmp     short loc_18003E176
0x18003e15f  mov     ecx, 6A5h
0x18003e164  mov     eax, [rbp+57h+var_B4]
0x18003e167  test    eax, eax
0x18003e169  jz      short loc_18003E1A0
0x18003e16b  cmp     cx, r11w
0x18003e16f  jnz     short loc_18003E1A0
0x18003e171  jmp     short loc_18003E155
0x18003e173  mov     ecx, r13d; hostlong
0x18003e176  call    cs:__imp_htonl
0x18003e17d  nop     dword ptr [rax+rax+00h]
0x18003e182  mov     rbx, [rbp+57h+p]
0x18003e186  cmp     dword ptr [rbp+57h+var_A0+4], eax
0x18003e189  jz      short loc_18003E1BD
0x18003e18b  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18003e192  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18003e199  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18003e1a0  mov     r12d, [rbp+57h+arg_18]
0x18003e1a4  xor     r13d, r13d
0x18003e1a7  inc     r12d
0x18003e1aa  mov     [rbp+57h+arg_18], r12d
0x18003e1ae  cmp     r12d, [rbp+57h+numEntriesReturned]
0x18003e1b2  jnb     loc_18003E2A3
0x18003e1b8  jmp     loc_18003E0CC
0x18003e1bd  mov     r12d, [rbp+57h+arg_18]
0x18003e1c1  jmp     loc_18003E2A0
0x18003e1c6  cmp     dword ptr [rbp+57h+var_A0], 2
0x18003e1ca  jnz     loc_18003E2A6
0x18003e1d0  mov     r12d, r13d
0x18003e1d3  cmp     [rbp+57h+numEntriesReturned], r13d
0x18003e1d7  jbe     loc_18003E2A6
0x18003e1dd  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18003e1e4  mov     r13, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18003e1eb  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18003e1f2  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18003e1f9  mov     edi, [rbp+57h+var_B4]
0x18003e1fc  mov     eax, r12d
0x18003e1ff  xor     r11d, r11d
0x18003e202  mov     rcx, [rbx+rax*8]
0x18003e206  mov     rdx, [rcx+0A0h]
0x18003e20d  movups  xmm0, xmmword ptr [rcx+1Ch]
0x18003e211  mov     r10d, [rdx+70h]
0x18003e215  movdqu  xmmword ptr [rbp-9], xmm0
0x18003e21a  test    r10d, r10d
0x18003e21d  jz      short loc_18003E26A
0x18003e21f  mov     rdx, [rdx+78h]
0x18003e223  xor     r9d, r9d
0x18003e226  xor     r8d, r8d
0x18003e229  lea     rcx, [r8+r8*4]
0x18003e22d  cmp     r13, [rdx+rcx*8]
0x18003e231  jnz     short loc_18003E242
0x18003e233  cmp     rsi, [rdx+rcx*8+8]
0x18003e238  jnz     short loc_18003E242
0x18003e23a  movzx   r9d, word ptr [rdx+rcx*8+20h]
0x18003e240  jmp     short loc_18003E255
0x18003e242  cmp     r15, [rdx+rcx*8]
0x18003e246  jnz     short loc_18003E255
0x18003e248  cmp     r14, [rdx+rcx*8+8]
0x18003e24d  jnz     short loc_18003E255
0x18003e24f  movzx   r11d, word ptr [rdx+rcx*8+20h]
0x18003e255  inc     r8d
0x18003e258  cmp     r8d, r10d
0x18003e25b  jb      short loc_18003E229
0x18003e25d  mov     eax, 6A5h
0x18003e262  cmp     ax, r9w
0x18003e266  jz      short loc_18003E279
0x18003e268  jmp     short loc_18003E26F
0x18003e26a  mov     eax, 6A5h
0x18003e26f  test    edi, edi
0x18003e271  jz      short loc_18003E290
0x18003e273  cmp     ax, r11w
0x18003e277  jnz     short loc_18003E290
0x18003e279  mov     r8d, 10h; Size
0x18003e27f  lea     rdx, [rbp+57h+Buf2+4]; Buf2
0x18003e283  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003e287  call    memcmp_0
0x18003e28c  test    eax, eax
0x18003e28e  jz      short loc_18003E29D
0x18003e290  inc     r12d
0x18003e293  cmp     r12d, [rbp+57h+numEntriesReturned]
0x18003e297  jb      loc_18003E1FC
0x18003e29d  mov     edi, [rbp+57h+arg_18]
0x18003e2a0  xor     r13d, r13d
0x18003e2a3  mov     esi, [rbp+57h+var_B8]
0x18003e2a6  cmp     r12d, [rbp+57h+numEntriesReturned]
0x18003e2aa  jnz     short loc_18003E2B5
0x18003e2ac  lea     rcx, aNoMatchFoundFo; "No match found for the SA"
0x18003e2b3  jmp     short loc_18003E2F6
0x18003e2b5  mov     eax, r12d
0x18003e2b8  mov     ecx, r13d
0x18003e2bb  mov     rdx, [rbx+rax*8]
0x18003e2bf  mov     r8d, [rdx+68h]
0x18003e2c3  test    r8d, r8d
0x18003e2c6  jz      short loc_18003E2EA
0x18003e2c8  mov     r9, [rdx+70h]
0x18003e2cc  mov     eax, ecx
0x18003e2ce  add     rax, rax
0x18003e2d1  mov     esi, [r9+rax*8+4]
0x18003e2d6  mov     [rbp+57h+var_B8], esi
0x18003e2d9  cmp     esi, 3
0x18003e2dc  jz      short loc_18003E314
0x18003e2de  cmp     esi, 4
0x18003e2e1  jz      short loc_18003E30C
0x18003e2e3  inc     ecx
0x18003e2e5  cmp     ecx, r8d
0x18003e2e8  jb      short loc_18003E2CC
0x18003e2ea  cmp     ecx, r8d
0x18003e2ed  jnz     short loc_18003E307
0x18003e2ef  lea     rcx, aNoEncryptionAl; "No Encryption algorithm was returned"
0x18003e2f6  call    RasIpsecTrace
0x18003e2fb  mov     rax, [rbp+57h+p]
0x18003e2ff  mov     ebx, [rbp+57h+var_A4]
0x18003e302  jmp     loc_18003DF83
  ... truncated ...
```
