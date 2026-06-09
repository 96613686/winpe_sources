# DwSaveIpSecInfo

- ea: `0x18003c098`
- end: `0x18003c6f7`
- name: `DwSaveIpSecInfo`
- size: `1631`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800152c0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18003c098`
- `0x18004033c`
- `0x180047934`
- `0x18009d3f4`
- `0x18009d5dc`
- `0x18009d698`
- `0x1800e71e2`

## import_xrefs

- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18003c1d4`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18003c1d4`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003c25b`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003c607`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003c25b`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18003c607`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003c198`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003c61b`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003c198`
- `fwpuclnt!FwpmFreeMemory0` at `0x18003c61b`
- `fwpuclnt!IPsecSaEnum0` at `0x18003c22b`
- `fwpuclnt!IPsecSaEnum0` at `0x18003c22b`
- `WS2_32!__imp_htonl` at `0x18003c36a`
- `WS2_32!__imp_htonl` at `0x18003c36a`

## string_xrefs

- `0x18003c1fa`: `DwQueryAssociations: Ikeext service is not running`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 545, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 546, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 547, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v11);
  }
  SetUserData(v52, 7, &v57);
  v43 = *(_QWORD *)(a1 + 1064);
  if ( v43 )
    SetUserData(v43 + 32, 5, &v57);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 548, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18003c098  mov     rax, rsp
0x18003c09b  mov     [rax+8], rcx
0x18003c09f  push    rbp
0x18003c0a0  push    rbx
0x18003c0a1  push    rsi
0x18003c0a2  push    rdi
0x18003c0a3  push    r12
0x18003c0a5  push    r13
0x18003c0a7  push    r14
0x18003c0a9  push    r15
0x18003c0ab  lea     rbp, [rax-5Fh]
0x18003c0af  sub     rsp, 0B8h
0x18003c0b6  movaps  xmmword ptr [rax-58h], xmm6
0x18003c0ba  mov     r14, rcx
0x18003c0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0c4  lea     rsi, WPP_GLOBAL_Control
0x18003c0cb  mov     edi, 2000h
0x18003c0d0  cmp     rcx, rsi
0x18003c0d3  jz      short loc_18003C0F5
0x18003c0d5  test    [rcx+1Ch], edi
0x18003c0d8  jz      short loc_18003C0F5
0x18003c0da  cmp     byte ptr [rcx+19h], 6
0x18003c0de  jb      short loc_18003C0F5
0x18003c0e0  mov     rcx, [rcx+10h]
0x18003c0e4  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003c0eb  mov     edx, 221h
0x18003c0f0  call    WPP_SF_
0x18003c0f5  lea     r15, [r14+438h]
0x18003c0fc  xorps   xmm6, xmm6
0x18003c0ff  xor     ebx, ebx
0x18003c101  mov     [rbp+57h+var_88], r15
0x18003c105  mov     rcx, r15
0x18003c108  movups  [rbp+57h+var_A0], xmm6
0x18003c10c  lea     edx, [rbx+0Dh]
0x18003c10f  call    GetUserData
0x18003c114  xor     r13d, r13d
0x18003c117  test    rax, rax
0x18003c11a  jz      short loc_18003C129
0x18003c11c  movups  xmm6, xmmword ptr [rax+18h]
0x18003c120  mov     ebx, [rax+28h]
0x18003c123  movups  [rbp+57h+var_A0], xmm6
0x18003c127  jmp     short loc_18003C155
0x18003c129  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c130  cmp     rcx, rsi
0x18003c133  jz      short loc_18003C155
0x18003c135  test    [rcx+1Ch], edi
0x18003c138  jz      short loc_18003C155
0x18003c13a  cmp     byte ptr [rcx+19h], 3
0x18003c13e  jb      short loc_18003C155
0x18003c140  mov     rcx, [rcx+10h]
0x18003c144  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003c14b  mov     edx, 222h
0x18003c150  call    WPP_SF_
0x18003c155  mov     ecx, [r14+20h]
0x18003c159  mov     rax, r13
0x18003c15c  and     ecx, 1
0x18003c15f  mov     [rbp+57h+var_70], ebx
0x18003c162  mov     ebx, ecx
0x18003c164  movaps  [rbp+57h+Buf2], xmm6
0x18003c168  xor     ebx, 1
0x18003c16b  mov     [rbp+57h+numEntriesReturned], r13d
0x18003c16f  mov     [rbp+57h+var_A4], ebx
0x18003c172  mov     r12d, r13d
0x18003c175  mov     [rbp+57h+enumHandle], r13
0x18003c179  mov     esi, r13d
0x18003c17c  mov     [rbp+57h+p], rax
0x18003c180  mov     [rbp+57h+enumTemplate.saDirection], r13d
0x18003c184  mov     [rbp+57h+var_B4], ecx
0x18003c187  mov     [rbp+57h+var_B8], r13d
0x18003c18b  mov     [rbp+57h+arg_8], r13d
0x18003c18f  test    rax, rax
0x18003c192  jz      short loc_18003C1A2
0x18003c194  lea     rcx, [rbp+57h+p]; p
0x18003c198  call    cs:__imp_FwpmFreeMemory0
0x18003c19e  mov     [rbp+57h+numEntriesReturned], r13d
0x18003c1a2  lea     rcx, aDwqueryassocia_2; "DwQueryAssociations"
0x18003c1a9  mov     [rbp+57h+enumTemplate.saDirection], ebx
0x18003c1ac  mov     [rbp+57h+p], r13
0x18003c1b0  call    RasIpsecTrace
0x18003c1b5  xor     ecx, ecx
0x18003c1b7  call    DwInitializeIpSec
0x18003c1bc  mov     rdx, [rbp+57h+enumHandle]
0x18003c1c0  test    rdx, rdx
0x18003c1c3  jnz     short loc_18003C211
0x18003c1c5  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18003c1cc  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x18003c1d0  lea     rdx, [rbp+57h+enumTemplate]; enumTemplate
0x18003c1d4  call    cs:__imp_IPsecSaCreateEnumHandle0
0x18003c1da  mov     [rbp+57h+arg_18], eax
0x18003c1dd  mov     edi, eax
0x18003c1df  test    eax, eax
0x18003c1e1  jz      short loc_18003C20D
0x18003c1e3  mov     edx, eax
0x18003c1e5  lea     rcx, aDwqueryassocia_3; "DwQueryAssociations: Failed to get enum"...
0x18003c1ec  call    RasIpsecTrace
0x18003c1f1  call    IsServiceRunning
0x18003c1f6  test    eax, eax
0x18003c1f8  jnz     short loc_18003C26D
0x18003c1fa  lea     rcx, aDwqueryassocia_0; "DwQueryAssociations: Ikeext service is "...
0x18003c201  call    RasIpsecTrace
0x18003c206  mov     edi, 33Bh
0x18003c20b  jmp     short loc_18003C26A
0x18003c20d  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x18003c211  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18003c218  lea     rax, [rbp+57h+numEntriesReturned]
0x18003c21c  lea     r9, [rbp+57h+p]; entries
0x18003c220  mov     [rsp+20h], rax; numEntriesReturned
0x18003c225  mov     r8d, 0Ah; numEntriesRequested
0x18003c22b  call    cs:__imp_IPsecSaEnum0
0x18003c231  mov     [rbp+57h+arg_18], eax
0x18003c234  mov     edi, eax
0x18003c236  test    eax, eax
0x18003c238  jz      short loc_18003C24A
0x18003c23a  mov     edx, eax
0x18003c23c  lea     rcx, aDwqueryassocia; "DwQueryAssociations: Failed to enum IPS"...
0x18003c243  call    RasIpsecTrace
0x18003c248  jmp     short loc_18003C26D
0x18003c24a  cmp     [rbp+57h+numEntriesReturned], r13d
0x18003c24e  jnz     short loc_18003C26D
0x18003c250  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x18003c254  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18003c25b  call    cs:__imp_IPsecSaDestroyEnumHandle0
0x18003c261  mov     [rbp+57h+enumHandle], r13
0x18003c265  mov     edi, 0E8h
0x18003c26a  mov     [rbp+57h+arg_18], edi
0x18003c26d  mov     edx, edi
0x18003c26f  lea     rcx, aDwqueryassocia_1; "DwQueryAssociation rc=0x%x"
0x18003c276  call    RasIpsecTrace
0x18003c27b  mov     rbx, [rbp+57h+p]
0x18003c27f  test    edi, edi
0x18003c281  jnz     loc_18003C5E1
0x18003c287  test    rbx, rbx
0x18003c28a  jz      loc_18003C5E1
0x18003c290  cmp     dword ptr [rbp+57h+var_A0], 1
0x18003c294  jnz     loc_18003C3B4
0x18003c29a  mov     r12d, r13d
0x18003c29d  mov     [rbp+57h+arg_18], r13d
0x18003c2a1  cmp     [rbp+57h+numEntriesReturned], r13d
0x18003c2a5  jbe     loc_18003C494
0x18003c2ab  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18003c2b2  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18003c2b9  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18003c2c0  mov     eax, r12d
0x18003c2c3  mov     rcx, [rbx+rax*8]
0x18003c2c7  cmp     [rcx+4], r13d
0x18003c2cb  jnz     short loc_18003C2D7
0x18003c2cd  mov     r13d, [rcx+0Ch]
0x18003c2d1  lea     r12, [rcx+1Ch]
0x18003c2d5  jmp     short loc_18003C2DF
0x18003c2d7  mov     r13d, [rcx+1Ch]
0x18003c2db  lea     r12, [rcx+0Ch]
0x18003c2df  mov     rdx, [rcx+0A0h]
0x18003c2e6  xor     r11d, r11d
0x18003c2e9  mov     r9d, [rdx+70h]
0x18003c2ed  test    r9d, r9d
0x18003c2f0  jz      short loc_18003C353
0x18003c2f2  mov     rdx, [rdx+78h]
0x18003c2f6  xor     r10d, r10d
0x18003c2f9  mov     rbx, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18003c300  xor     r8d, r8d
0x18003c303  lea     rcx, [r8+r8*4]
0x18003c307  cmp     rbx, [rdx+rcx*8]
0x18003c30b  jnz     short loc_18003C31C
0x18003c30d  cmp     rsi, [rdx+rcx*8+8]
0x18003c312  jnz     short loc_18003C31C
0x18003c314  movzx   r10d, word ptr [rdx+rcx*8+20h]
0x18003c31a  jmp     short loc_18003C32F
0x18003c31c  cmp     r15, [rdx+rcx*8]
0x18003c320  jnz     short loc_18003C32F
0x18003c322  cmp     r14, [rdx+rcx*8+8]
0x18003c327  jnz     short loc_18003C32F
0x18003c329  movzx   r11d, word ptr [rdx+rcx*8+20h]
0x18003c32f  inc     r8d
0x18003c332  cmp     r8d, r9d
0x18003c335  jb      short loc_18003C303
0x18003c337  mov     rbx, [rbp+57h+p]
0x18003c33b  mov     ecx, 6A5h
0x18003c340  cmp     cx, r10w
0x18003c344  jnz     short loc_18003C358
0x18003c346  mov     eax, [rbp+57h+var_B4]
0x18003c349  test    eax, eax
0x18003c34b  jz      short loc_18003C367
0x18003c34d  mov     ecx, [r12]
0x18003c351  jmp     short loc_18003C36A
0x18003c353  mov     ecx, 6A5h
0x18003c358  mov     eax, [rbp+57h+var_B4]
0x18003c35b  test    eax, eax
0x18003c35d  jz      short loc_18003C38E
0x18003c35f  cmp     cx, r11w
0x18003c363  jnz     short loc_18003C38E
0x18003c365  jmp     short loc_18003C349
0x18003c367  mov     ecx, r13d; hostlong
0x18003c36a  call    cs:__imp_htonl
0x18003c370  mov     rbx, [rbp+57h+p]
0x18003c374  cmp     dword ptr [rbp+57h+var_A0+4], eax
0x18003c377  jz      short loc_18003C3AB
0x18003c379  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18003c380  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18003c387  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18003c38e  mov     r12d, [rbp+57h+arg_18]
0x18003c392  xor     r13d, r13d
0x18003c395  inc     r12d
0x18003c398  mov     [rbp+57h+arg_18], r12d
0x18003c39c  cmp     r12d, [rbp+57h+numEntriesReturned]
0x18003c3a0  jnb     loc_18003C491
0x18003c3a6  jmp     loc_18003C2C0
0x18003c3ab  mov     r12d, [rbp+57h+arg_18]
0x18003c3af  jmp     loc_18003C48E
0x18003c3b4  cmp     dword ptr [rbp+57h+var_A0], 2
0x18003c3b8  jnz     loc_18003C494
0x18003c3be  mov     r12d, r13d
0x18003c3c1  cmp     [rbp+57h+numEntriesReturned], r13d
0x18003c3c5  jbe     loc_18003C494
0x18003c3cb  mov     rsi, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x18003c3d2  mov     r13, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18003c3d9  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18003c3e0  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18003c3e7  mov     edi, [rbp+57h+var_B4]
0x18003c3ea  mov     eax, r12d
0x18003c3ed  xor     r11d, r11d
0x18003c3f0  mov     rcx, [rbx+rax*8]
0x18003c3f4  mov     rdx, [rcx+0A0h]
0x18003c3fb  movups  xmm0, xmmword ptr [rcx+1Ch]
0x18003c3ff  mov     r10d, [rdx+70h]
0x18003c403  movdqu  xmmword ptr [rbp-9], xmm0
0x18003c408  test    r10d, r10d
0x18003c40b  jz      short loc_18003C458
0x18003c40d  mov     rdx, [rdx+78h]
0x18003c411  xor     r9d, r9d
0x18003c414  xor     r8d, r8d
0x18003c417  lea     rcx, [r8+r8*4]
0x18003c41b  cmp     r13, [rdx+rcx*8]
0x18003c41f  jnz     short loc_18003C430
0x18003c421  cmp     rsi, [rdx+rcx*8+8]
0x18003c426  jnz     short loc_18003C430
0x18003c428  movzx   r9d, word ptr [rdx+rcx*8+20h]
0x18003c42e  jmp     short loc_18003C443
0x18003c430  cmp     r15, [rdx+rcx*8]
0x18003c434  jnz     short loc_18003C443
0x18003c436  cmp     r14, [rdx+rcx*8+8]
0x18003c43b  jnz     short loc_18003C443
0x18003c43d  movzx   r11d, word ptr [rdx+rcx*8+20h]
0x18003c443  inc     r8d
0x18003c446  cmp     r8d, r10d
0x18003c449  jb      short loc_18003C417
0x18003c44b  mov     eax, 6A5h
0x18003c450  cmp     ax, r9w
0x18003c454  jz      short loc_18003C467
0x18003c456  jmp     short loc_18003C45D
0x18003c458  mov     eax, 6A5h
0x18003c45d  test    edi, edi
0x18003c45f  jz      short loc_18003C47E
0x18003c461  cmp     ax, r11w
0x18003c465  jnz     short loc_18003C47E
0x18003c467  mov     r8d, 10h; Size
0x18003c46d  lea     rdx, [rbp+57h+Buf2+4]; Buf2
0x18003c471  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003c475  call    memcmp_0
0x18003c47a  test    eax, eax
0x18003c47c  jz      short loc_18003C48B
0x18003c47e  inc     r12d
0x18003c481  cmp     r12d, [rbp+57h+numEntriesReturned]
0x18003c485  jb      loc_18003C3EA
0x18003c48b  mov     edi, [rbp+57h+arg_18]
0x18003c48e  xor     r13d, r13d
0x18003c491  mov     esi, [rbp+57h+var_B8]
0x18003c494  cmp     r12d, [rbp+57h+numEntriesReturned]
0x18003c498  jnz     short loc_18003C4A3
0x18003c49a  lea     rcx, aNoMatchFoundFo; "No match found for the SA"
0x18003c4a1  jmp     short loc_18003C4E4
0x18003c4a3  mov     eax, r12d
0x18003c4a6  mov     ecx, r13d
0x18003c4a9  mov     rdx, [rbx+rax*8]
0x18003c4ad  mov     r8d, [rdx+68h]
0x18003c4b1  test    r8d, r8d
0x18003c4b4  jz      short loc_18003C4D8
0x18003c4b6  mov     r9, [rdx+70h]
0x18003c4ba  mov     eax, ecx
0x18003c4bc  add     rax, rax
0x18003c4bf  mov     esi, [r9+rax*8+4]
0x18003c4c4  mov     [rbp+57h+var_B8], esi
0x18003c4c7  cmp     esi, 3
0x18003c4ca  jz      short loc_18003C502
0x18003c4cc  cmp     esi, 4
0x18003c4cf  jz      short loc_18003C4FA
0x18003c4d1  inc     ecx
0x18003c4d3  cmp     ecx, r8d
0x18003c4d6  jb      short loc_18003C4BA
0x18003c4d8  cmp     ecx, r8d
0x18003c4db  jnz     short loc_18003C4F5
0x18003c4dd  lea     rcx, aNoEncryptionAl; "No Encryption algorithm was returned"
0x18003c4e4  call    RasIpsecTrace
0x18003c4e9  mov     rax, [rbp+57h+p]
0x18003c4ed  mov     ebx, [rbp+57h+var_A4]
0x18003c4f0  jmp     loc_18003C18F
0x18003c4f5  cmp     esi, 3
0x18003c4f8  jz      short loc_18003C502
0x18003c4fa  mov     rbx, r13
0x18003c4fd  cmp     esi, 4
0x18003c500  jnz     short loc_18003C50E
  ... truncated ...
```
