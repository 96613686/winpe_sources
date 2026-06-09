# DwGetIpSecInformation

- ea: `0x1800851d8`
- end: `0x18008570e`
- name: `DwGetIpSecInformation`
- size: `1334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180045818`

## callees

- `0x1800851d8`
- `0x1800859a4`
- `0x180085bb0`
- `0x180085cb4`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18008541d`
- `WS2_32!__imp_htonl` at `0x18008541d`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x180085328`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x1800856c4`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x180085328`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x1800856c4`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x180085295`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x180085295`
- `fwpuclnt!FwpmFreeMemory0` at `0x18008524b`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800856de`
- `fwpuclnt!FwpmFreeMemory0` at `0x18008524b`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800856de`
- `fwpuclnt!IPsecSaEnum0` at `0x1800852f2`
- `fwpuclnt!IPsecSaEnum0` at `0x1800852f2`

## string_xrefs

- `0x1800852c1`: `DwQueryAssociations: Ikeext service is not running`

## pseudocode

```c
__int64 __fastcall DwGetIpSecInformation(_DWORD *a1, int a2, _DWORD *a3)
{
  __int16 v3; // r13
  void *v4; // rax
  _DWORD *v5; // rbx
  int v6; // edi
  _DWORD *v7; // r15
  UINT32 v8; // r14d
  __int64 *v9; // rsi
  unsigned int v10; // edi
  HANDLE v11; // rdx
  _QWORD *v12; // r10
  __int64 v13; // r9
  __int64 v14; // r11
  __int64 v15; // r15
  __int64 v16; // r12
  __int64 v17; // rcx
  u_long *v18; // rdx
  __int16 v19; // r8
  __int64 v20; // rax
  unsigned int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  u_long v25; // ecx
  u_long v26; // eax
  __int64 v27; // rdx
  __int16 v28; // r8
  __int16 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rax
  __m128i v32; // xmm0
  unsigned int v33; // ecx
  __int64 v34; // rax
  const CHAR *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rdx
  unsigned int v38; // r8d
  __int64 v39; // r9
  __int64 v40; // rax
  __int64 v41; // rcx
  UINT32 numEntriesReturned; // [rsp+30h] [rbp-50h] BYREF
  DWORD v44; // [rsp+34h] [rbp-4Ch]
  void *p; // [rsp+38h] [rbp-48h] BYREF
  int v46; // [rsp+40h] [rbp-40h]
  HANDLE enumHandle; // [rsp+48h] [rbp-38h] BYREF
  IPSEC_SA_ENUM_TEMPLATE0 enumTemplate; // [rsp+50h] [rbp-30h] BYREF
  int v49; // [rsp+54h] [rbp-2Ch]
  _DWORD *v50; // [rsp+58h] [rbp-28h]
  u_long hostlong; // [rsp+60h] [rbp-20h]
  _DWORD *v52; // [rsp+68h] [rbp-18h]
  __int64 *v53; // [rsp+70h] [rbp-10h]

  v3 = 0;
  v46 = a2;
  v50 = a1;
  v4 = 0;
  p = 0;
  v5 = a3;
  v52 = a3;
  v6 = a2;
  numEntriesReturned = 0;
  v7 = a1;
  enumHandle = 0;
  v8 = 0;
  v49 = 0;
  v9 = 0;
  v53 = 0;
  enumTemplate.saDirection = FWP_DIRECTION_OUTBOUND;
  if ( !a3 )
    return 87;
  *a3 = 0;
  while ( 1 )
  {
    if ( v4 )
    {
      FwpmFreeMemory0(&p);
      numEntriesReturned = 0;
    }
    p = 0;
    enumTemplate.saDirection = v6 == 0;
    RasIpsecTrace("DwQueryAssociations");
    DwInitializeIpSec(0);
    v11 = enumHandle;
    if ( !enumHandle )
    {
      v44 = IPsecSaCreateEnumHandle0(gFwpEngineHandle, &enumTemplate, &enumHandle);
      v10 = v44;
      if ( v44 )
      {
        RasIpsecTrace("DwQueryAssociations: Failed to get enum handle %d");
        if ( !IsServiceRunning() )
        {
          RasIpsecTrace("DwQueryAssociations: Ikeext service is not running");
          v10 = 827;
LABEL_15:
          v44 = v10;
          goto LABEL_16;
        }
        goto LABEL_16;
      }
      v11 = enumHandle;
    }
    v44 = IPsecSaEnum0(gFwpEngineHandle, v11, 0xAu, (IPSEC_SA_DETAILS0 ***)&p, &numEntriesReturned);
    v10 = v44;
    if ( v44 )
    {
      RasIpsecTrace("DwQueryAssociations: Failed to enum IPSec SA %d");
    }
    else if ( !numEntriesReturned )
    {
      IPsecSaDestroyEnumHandle0(gFwpEngineHandle, enumHandle);
      enumHandle = 0;
      v10 = 232;
      goto LABEL_15;
    }
LABEL_16:
    RasIpsecTrace("DwQueryAssociation rc=0x%x");
    v12 = p;
    if ( v10 || !p )
      break;
    if ( *v7 == 1 )
    {
      v8 = 0;
      if ( numEntriesReturned )
      {
        v13 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
        v14 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
        v15 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
        v16 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
        while ( 1 )
        {
          v17 = v12[v8];
          v18 = (u_long *)(v17 + 28);
          if ( *(_DWORD *)(v17 + 4) )
          {
            v44 = *v18;
            v18 = (u_long *)(v17 + 12);
          }
          else
          {
            v44 = *(_DWORD *)(v17 + 12);
          }
          v19 = 0;
          hostlong = *v18;
          v20 = *(_QWORD *)(v17 + 160);
          v21 = *(_DWORD *)(v20 + 112);
          if ( !v21 )
            goto LABEL_39;
          v22 = *(_QWORD *)(v20 + 120);
          v23 = v21;
          do
          {
            if ( v14 == *(_QWORD *)v22 && v13 == *(_QWORD *)(v22 + 8) )
            {
              v19 = *(_WORD *)(v22 + 32);
            }
            else if ( v16 == *(_QWORD *)v22 && v15 == *(_QWORD *)(v22 + 8) )
            {
              v3 = *(_WORD *)(v22 + 32);
            }
            v22 += 40;
            --v23;
          }
          while ( v23 );
          if ( v19 == 1701 )
          {
            v24 = v46;
          }
          else
          {
LABEL_39:
            v24 = v46;
            if ( !v46 || v3 != 1701 )
            {
              v3 = 0;
              goto LABEL_42;
            }
          }
          v3 = 0;
          if ( v24 )
            v25 = hostlong;
          else
            v25 = v44;
          v26 = htonl(v25);
          v7 = v50;
          v12 = p;
          if ( v50[1] == v26 )
            break;
          v13 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
          v14 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
          v15 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
          v16 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
LABEL_42:
          if ( ++v8 >= numEntriesReturned )
            goto LABEL_64;
        }
      }
    }
    else if ( *v7 == 2 )
    {
      v8 = 0;
      if ( numEntriesReturned )
      {
        LOWORD(v27) = 0;
        do
        {
          v28 = v27;
          v29 = v27;
          v30 = *((_QWORD *)p + v8);
          v31 = *(_QWORD *)(v30 + 160);
          v32 = *(__m128i *)(v30 + 28);
          v33 = *(_DWORD *)(v31 + 112);
          if ( v33 )
          {
            v34 = *(_QWORD *)(v31 + 120);
            v27 = v33;
            do
            {
              if ( *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1 == *(_QWORD *)v34
                && *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4 == *(_QWORD *)(v34 + 8) )
              {
                v28 = *(_WORD *)(v34 + 32);
              }
              else if ( *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1 == *(_QWORD *)v34
                     && *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4 == *(_QWORD *)(v34 + 8) )
              {
                v29 = *(_WORD *)(v34 + 32);
              }
              v34 += 40;
              --v27;
            }
            while ( v27 );
            if ( v28 == 1701 )
              goto LABEL_61;
          }
          if ( v46 && v29 == 1701 )
          {
LABEL_61:
            if ( v32.m128i_i64[0] == *(_QWORD *)(v50 + 1) && _mm_srli_si128(v32, 8).m128i_u64[0] == *(_QWORD *)(v50 + 3) )
              break;
          }
          ++v8;
        }
        while ( v8 < numEntriesReturned );
        v5 = v52;
        v3 = 0;
        v10 = v44;
        v9 = v53;
LABEL_64:
        v7 = v50;
      }
    }
    if ( v8 == numEntriesReturned )
    {
      v35 = "No match found for the SA";
    }
    else
    {
      v36 = 0;
      v37 = v12[v8];
      v38 = *(_DWORD *)(v37 + 104);
      if ( v38 )
      {
        v39 = *(_QWORD *)(v37 + 112);
        do
        {
          v49 = *(_DWORD *)(v39 + 16LL * (unsigned int)v36 + 4);
          if ( (unsigned int)(v49 - 3) <= 1 )
            break;
          v36 = (unsigned int)(v36 + 1);
        }
        while ( (unsigned int)v36 < v38 );
        v12 = p;
      }
      v40 = v12[v8];
      if ( (_DWORD)v36 != *(_DWORD *)(v40 + 104) )
      {
        if ( v49 == 3 || v49 == 4 )
          v9 = *(__int64 **)(*(_QWORD *)(v40 + 112) + 16 * v36 + 8);
        RasIpsecTrace("CipherId = (%d, %d)");
        if ( *v9 == 0x100000001LL && g_dwAllowL2TPWeakCrypto )
        {
          *v5 |= 1u;
          goto LABEL_100;
        }
        v41 = *v9;
        if ( *v9 == 0x200000002LL )
        {
          *v5 |= 4u;
          goto LABEL_100;
        }
        switch ( v41 )
        {
          case 0x300000003LL:
            *v5 |= 0x10u;
            goto LABEL_100;
          case 0x500000005LL:
            *v5 |= 0x20u;
            goto LABEL_100;
          case 0x400000004LL:
            *v5 |= 0x40u;
            goto LABEL_100;
          case 0x600000003LL:
            *v5 |= 0x80u;
            goto LABEL_100;
          case 0x700000004LL:
            *v5 |= 0x100u;
            goto LABEL_100;
          case 0x800000005LL:
            *v5 |= 0x200u;
            goto LABEL_100;
        }
        if ( v41 == 0x100000001LL && !g_dwAllowL2TPWeakCrypto )
        {
          RasIpsecTrace("Cipher Id obtained is not supported.");
          goto LABEL_99;
        }
        goto LABEL_100;
      }
      v35 = "No Encryption algorithm was returned";
    }
    RasIpsecTrace(v35);
    v4 = p;
    v6 = v46;
  }
  RasIpsecTrace("QuerySA returned dwErr=0x%x, pSAList=0x%x");
LABEL_99:
  v10 = 774;
LABEL_100:
  if ( enumHandle )
  {
    IPsecSaDestroyEnumHandle0(gFwpEngineHandle, enumHandle);
    enumHandle = 0;
  }
  if ( p )
    FwpmFreeMemory0(&p);
  return v10;
}

```

## disassembly

```asm
0x1800851d8  mov     [rsp-28h+arg_0], rbx
0x1800851dd  mov     [rsp-28h+arg_8], rsi
0x1800851e2  mov     [rsp-28h+arg_18], rdi
0x1800851e7  push    rbp
0x1800851e8  push    r12
0x1800851ea  push    r13
0x1800851ec  push    r14
0x1800851ee  push    r15
0x1800851f0  mov     rbp, rsp
0x1800851f3  sub     rsp, 80h
0x1800851fa  xor     r13d, r13d
0x1800851fd  mov     [rbp+var_40], edx
0x180085200  mov     [rbp+var_28], rcx
0x180085204  mov     eax, r13d
0x180085207  mov     [rbp+p], rax
0x18008520b  mov     rbx, r8
0x18008520e  mov     [rbp+var_18], rbx
0x180085212  mov     edi, edx
0x180085214  mov     [rbp+var_50], r13d
0x180085218  mov     r15, rcx
0x18008521b  mov     [rbp+enumHandle], r13
0x18008521f  mov     r14d, r13d
0x180085222  mov     [rbp+var_2C], r13d
0x180085226  mov     esi, r13d
0x180085229  mov     [rbp+var_10], r13
0x18008522d  mov     [rbp+enumTemplate.saDirection], r13d
0x180085231  test    r8, r8
0x180085234  jnz     short loc_18008523F
0x180085236  lea     edi, [r8+57h]
0x18008523a  jmp     loc_1800856EA
0x18008523f  mov     [r8], r13d
0x180085242  test    rax, rax
0x180085245  jz      short loc_18008525B
0x180085247  lea     rcx, [rbp+p]; p
0x18008524b  call    cs:__imp_FwpmFreeMemory0
0x180085252  nop     dword ptr [rax+rax+00h]
0x180085257  mov     [rbp+var_50], r13d
0x18008525b  mov     eax, r13d
0x18008525e  mov     [rbp+p], r13
0x180085262  test    edi, edi
0x180085264  lea     rcx, aDwqueryassocia_2; "DwQueryAssociations"
0x18008526b  setz    al
0x18008526e  mov     [rbp+enumTemplate.saDirection], eax
0x180085271  call    RasIpsecTrace
0x180085276  xor     ecx, ecx
0x180085278  call    DwInitializeIpSec
0x18008527d  mov     rdx, [rbp+enumHandle]
0x180085281  test    rdx, rdx
0x180085284  jnz     short loc_1800852D8
0x180085286  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18008528d  lea     r8, [rbp+enumHandle]; enumHandle
0x180085291  lea     rdx, [rbp+enumTemplate]; enumTemplate
0x180085295  call    cs:__imp_IPsecSaCreateEnumHandle0
0x18008529c  nop     dword ptr [rax+rax+00h]
0x1800852a1  mov     [rbp+var_4C], eax
0x1800852a4  mov     edi, eax
0x1800852a6  test    eax, eax
0x1800852a8  jz      short loc_1800852D4
0x1800852aa  mov     edx, eax
0x1800852ac  lea     rcx, aDwqueryassocia_3; "DwQueryAssociations: Failed to get enum"...
0x1800852b3  call    RasIpsecTrace
0x1800852b8  call    IsServiceRunning
0x1800852bd  test    eax, eax
0x1800852bf  jnz     short loc_180085340
0x1800852c1  lea     rcx, aDwqueryassocia_0; "DwQueryAssociations: Ikeext service is "...
0x1800852c8  call    RasIpsecTrace
0x1800852cd  mov     edi, 33Bh
0x1800852d2  jmp     short loc_18008533D
0x1800852d4  mov     rdx, [rbp+enumHandle]; enumHandle
0x1800852d8  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800852df  lea     rax, [rbp+var_50]
0x1800852e3  lea     r9, [rbp+p]; entries
0x1800852e7  mov     [rsp+80h+numEntriesReturned], rax; numEntriesReturned
0x1800852ec  mov     r8d, 0Ah; numEntriesRequested
0x1800852f2  call    cs:__imp_IPsecSaEnum0
0x1800852f9  nop     dword ptr [rax+rax+00h]
0x1800852fe  mov     [rbp+var_4C], eax
0x180085301  mov     edi, eax
0x180085303  test    eax, eax
0x180085305  jz      short loc_180085317
0x180085307  mov     edx, eax
0x180085309  lea     rcx, aDwqueryassocia; "DwQueryAssociations: Failed to enum IPS"...
0x180085310  call    RasIpsecTrace
0x180085315  jmp     short loc_180085340
0x180085317  cmp     [rbp+var_50], r13d
0x18008531b  jnz     short loc_180085340
0x18008531d  mov     rdx, [rbp+enumHandle]; enumHandle
0x180085321  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180085328  call    cs:__imp_IPsecSaDestroyEnumHandle0
0x18008532f  nop     dword ptr [rax+rax+00h]
0x180085334  mov     [rbp+enumHandle], r13
0x180085338  mov     edi, 0E8h
0x18008533d  mov     [rbp+var_4C], edi
0x180085340  mov     edx, edi
0x180085342  lea     rcx, aDwqueryassocia_1; "DwQueryAssociation rc=0x%x"
0x180085349  call    RasIpsecTrace
0x18008534e  mov     r10, [rbp+p]
0x180085352  test    edi, edi
0x180085354  jnz     loc_18008569E
0x18008535a  test    r10, r10
0x18008535d  jz      loc_18008569E
0x180085363  cmp     dword ptr [r15], 1
0x180085367  jnz     loc_180085485
0x18008536d  mov     r14d, r13d
0x180085370  cmp     [rbp+var_50], r13d
0x180085374  jbe     loc_180085563
0x18008537a  mov     r9, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x180085381  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180085388  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18008538f  mov     r12, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180085396  mov     eax, r14d
0x180085399  mov     rcx, [r10+rax*8]
0x18008539d  lea     rdx, [rcx+1Ch]
0x1800853a1  cmp     [rcx+4], r13d
0x1800853a5  jnz     short loc_1800853AF
0x1800853a7  mov     eax, [rcx+0Ch]
0x1800853aa  mov     [rbp+var_4C], eax
0x1800853ad  jmp     short loc_1800853B8
0x1800853af  mov     edx, [rdx]
0x1800853b1  mov     [rbp+var_4C], edx
0x1800853b4  lea     rdx, [rcx+0Ch]
0x1800853b8  mov     eax, [rdx]
0x1800853ba  movzx   r8d, r13w
0x1800853be  mov     [rbp+hostlong], eax
0x1800853c1  mov     rax, [rcx+0A0h]
0x1800853c8  mov     ecx, [rax+70h]
0x1800853cb  test    ecx, ecx
0x1800853cd  jz      loc_180085459
0x1800853d3  mov     rax, [rax+78h]
0x1800853d7  mov     edx, ecx
0x1800853d9  cmp     r11, [rax]
0x1800853dc  jnz     short loc_1800853EB
0x1800853de  cmp     r9, [rax+8]
0x1800853e2  jnz     short loc_1800853EB
0x1800853e4  movzx   r8d, word ptr [rax+20h]
0x1800853e9  jmp     short loc_1800853FB
0x1800853eb  cmp     r12, [rax]
0x1800853ee  jnz     short loc_1800853FB
0x1800853f0  cmp     r15, [rax+8]
0x1800853f4  jnz     short loc_1800853FB
0x1800853f6  movzx   r13d, word ptr [rax+20h]
0x1800853fb  add     rax, 28h ; '('
0x1800853ff  sub     rdx, 1
0x180085403  jnz     short loc_1800853D9
0x180085405  mov     ecx, 6A5h
0x18008540a  cmp     cx, r8w
0x18008540e  jnz     short loc_18008545E
0x180085410  mov     eax, [rbp+var_40]
0x180085413  xor     r13d, r13d
0x180085416  test    eax, eax
0x180085418  jz      short loc_180085480
0x18008541a  mov     ecx, [rbp+hostlong]; hostlong
0x18008541d  call    cs:__imp_htonl
0x180085424  nop     dword ptr [rax+rax+00h]
0x180085429  mov     r15, [rbp+var_28]
0x18008542d  mov     r10, [rbp+p]
0x180085431  cmp     [r15+4], eax
0x180085435  jz      loc_180085563
0x18008543b  mov     r9, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x180085442  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180085449  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x180085450  mov     r12, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180085457  jmp     short loc_18008546E
0x180085459  mov     ecx, 6A5h
0x18008545e  mov     eax, [rbp+var_40]
0x180085461  test    eax, eax
0x180085463  jz      short loc_18008546B
0x180085465  cmp     cx, r13w
0x180085469  jz      short loc_180085413
0x18008546b  xor     r13d, r13d
0x18008546e  inc     r14d
0x180085471  cmp     r14d, [rbp+var_50]
0x180085475  jb      loc_180085396
0x18008547b  jmp     loc_18008555F
0x180085480  mov     ecx, [rbp+var_4C]
0x180085483  jmp     short loc_18008541D
0x180085485  cmp     dword ptr [r15], 2
0x180085489  jnz     loc_180085563
0x18008548f  mov     r14d, r13d
0x180085492  cmp     [rbp+var_50], r13d
0x180085496  jbe     loc_180085563
0x18008549c  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x1800854a3  xor     edx, edx
0x1800854a5  mov     r15, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x1800854ac  mov     edi, 6A5h
0x1800854b1  mov     r12, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x1800854b8  mov     r13, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x1800854bf  mov     ebx, [rbp+var_40]
0x1800854c2  mov     rsi, [rbp+var_28]
0x1800854c6  mov     eax, r14d
0x1800854c9  movzx   r8d, dx
0x1800854cd  movzx   r9d, dx
0x1800854d1  mov     rcx, [r10+rax*8]
0x1800854d5  mov     rax, [rcx+0A0h]
0x1800854dc  movups  xmm0, xmmword ptr [rcx+1Ch]
0x1800854e0  mov     ecx, [rax+70h]
0x1800854e3  test    ecx, ecx
0x1800854e5  jz      short loc_18008551F
0x1800854e7  mov     rax, [rax+78h]
0x1800854eb  mov     edx, ecx
0x1800854ed  cmp     r15, [rax]
0x1800854f0  jnz     short loc_1800854FF
0x1800854f2  cmp     r11, [rax+8]
0x1800854f6  jnz     short loc_1800854FF
0x1800854f8  movzx   r8d, word ptr [rax+20h]
0x1800854fd  jmp     short loc_18008550F
0x1800854ff  cmp     r13, [rax]
0x180085502  jnz     short loc_18008550F
0x180085504  cmp     r12, [rax+8]
0x180085508  jnz     short loc_18008550F
0x18008550a  movzx   r9d, word ptr [rax+20h]
0x18008550f  add     rax, 28h ; '('
0x180085513  sub     rdx, 1
0x180085517  jnz     short loc_1800854ED
0x180085519  cmp     di, r8w
0x18008551d  jz      short loc_180085529
0x18008551f  test    ebx, ebx
0x180085521  jz      short loc_180085544
0x180085523  cmp     di, r9w
0x180085527  jnz     short loc_180085544
0x180085529  movq    rax, xmm0
0x18008552e  cmp     rax, [rsi+4]
0x180085532  jnz     short loc_180085544
0x180085534  psrldq  xmm0, 8
0x180085539  movq    rax, xmm0
0x18008553e  cmp     rax, [rsi+0Ch]
0x180085542  jz      short loc_180085551
0x180085544  inc     r14d
0x180085547  cmp     r14d, [rbp+var_50]
0x18008554b  jb      loc_1800854C6
0x180085551  mov     rbx, [rbp+var_18]
0x180085555  xor     r13d, r13d
0x180085558  mov     edi, [rbp+var_4C]
0x18008555b  mov     rsi, [rbp+var_10]
0x18008555f  mov     r15, [rbp+var_28]
0x180085563  cmp     r14d, [rbp+var_50]
0x180085567  jnz     short loc_180085572
0x180085569  lea     rcx, aNoMatchFoundFo; "No match found for the SA"
0x180085570  jmp     short loc_1800855BE
0x180085572  mov     eax, r14d
0x180085575  mov     ecx, r13d
0x180085578  mov     rdx, [r10+rax*8]
0x18008557c  mov     r8d, [rdx+68h]
0x180085580  test    r8d, r8d
0x180085583  jz      short loc_1800855AB
0x180085585  mov     r9, [rdx+70h]
0x180085589  mov     eax, ecx
0x18008558b  add     rax, rax
0x18008558e  mov     r10d, [r9+rax*8+4]
0x180085593  mov     [rbp+var_2C], r10d
0x180085597  lea     eax, [r10-3]
0x18008559b  cmp     eax, 1
0x18008559e  jbe     short loc_1800855A7
0x1800855a0  inc     ecx
0x1800855a2  cmp     ecx, r8d
0x1800855a5  jb      short loc_180085589
0x1800855a7  mov     r10, [rbp+p]
0x1800855ab  mov     eax, r14d
0x1800855ae  mov     rax, [r10+rax*8]
0x1800855b2  cmp     ecx, [rax+68h]
0x1800855b5  jnz     short loc_1800855CF
0x1800855b7  lea     rcx, aNoEncryptionAl; "No Encryption algorithm was returned"
0x1800855be  call    RasIpsecTrace
0x1800855c3  mov     rax, [rbp+p]
0x1800855c7  mov     edi, [rbp+var_40]
0x1800855ca  jmp     loc_180085242
0x1800855cf  mov     r8d, [rbp+var_2C]
0x1800855d3  cmp     r8d, 3
0x1800855d7  jz      short loc_1800855DF
0x1800855d9  cmp     r8d, 4
0x1800855dd  jnz     short loc_1800855EB
0x1800855df  mov     rax, [rax+70h]
0x1800855e3  add     rcx, rcx
0x1800855e6  mov     rsi, [rax+rcx*8+8]
0x1800855eb  movzx   r8d, byte ptr [rsi+4]
0x1800855f0  lea     rcx, aCipheridDD; "CipherId = (%d, %d)"
0x1800855f7  mov     edx, [rsi]
0x1800855f9  call    RasIpsecTrace
0x1800855fe  mov     rax, cs:qword_1800BB210
0x180085605  mov     edx, cs:g_dwAllowL2TPWeakCrypto
0x18008560b  cmp     [rsi], rax
0x18008560e  jnz     short loc_18008561C
0x180085610  test    edx, edx
0x180085612  jz      short loc_18008561C
0x180085614  or      dword ptr [rbx], 1
0x180085617  jmp     loc_1800856B4
0x18008561c  mov     rcx, [rsi]
0x18008561f  cmp     rcx, cs:qword_1800BB1D0
0x180085626  jnz     short loc_180085630
0x180085628  or      dword ptr [rbx], 4
0x18008562b  jmp     loc_1800856B4
0x180085630  cmp     rcx, cs:qword_1800BB200
0x180085637  jnz     short loc_18008563E
0x180085639  or      dword ptr [rbx], 10h
0x18008563c  jmp     short loc_1800856B4
0x18008563e  cmp     rcx, cs:qword_1800BB220
0x180085645  jnz     short loc_18008564C
0x180085647  or      dword ptr [rbx], 20h
0x18008564a  jmp     short loc_1800856B4
0x18008564c  cmp     rcx, cs:qword_1800BB208
  ... truncated ...
```
