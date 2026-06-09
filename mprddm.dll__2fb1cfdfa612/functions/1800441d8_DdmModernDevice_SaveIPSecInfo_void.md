# DdmModernDevice::SaveIPSecInfo(void)

- ea: `0x1800441d8`
- end: `0x180044887`
- name: `?SaveIPSecInfo@DdmModernDevice@@QEAAXXZ`
- size: `1711`
- prototype: `void __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041750`

## callees

- `0x180002bbe`
- `0x180007c50`
- `0x1800441d8`
- `0x180071cec`
- `0x180080100`
- `0x1800802ec`
- `0x1800803a8`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800442ae`
- `msvcrt!_itow_s` at `0x18004482c`
- `msvcrt!_itow_s` at `0x1800442ae`
- `msvcrt!_itow_s` at `0x18004482c`
- `WS2_32!__imp_htonl` at `0x18004452a`
- `WS2_32!__imp_htonl` at `0x18004452a`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x180044429`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x1800447dd`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x180044429`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x1800447dd`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18004439b`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18004439b`
- `fwpuclnt!FwpmFreeMemory0` at `0x180044359`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800447f4`
- `fwpuclnt!FwpmFreeMemory0` at `0x180044359`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800447f4`
- `fwpuclnt!IPsecSaEnum0` at `0x1800443f6`
- `fwpuclnt!IPsecSaEnum0` at `0x1800443f6`

## string_xrefs

- `0x1800443c2`: `DwQueryAssociations: Ikeext service is not running`

## pseudocode

```c
void __fastcall DdmModernDevice::SaveIPSecInfo(DdmModernDevice *this)
{
  __int16 v1; // r12
  __int64 v3; // rax
  __int64 (__fastcall *v4)(DdmModernDevice *, __int64, __int128 *, int *); // rax
  unsigned int v5; // ebx
  int v6; // ecx
  UINT32 v7; // ebx
  int v8; // r14d
  int v9; // ecx
  FWP_DIRECTION v10; // edi
  void *v11; // rax
  HANDLE v12; // rdx
  unsigned int v13; // edi
  _QWORD *v14; // rsi
  __int64 v15; // r11
  __int64 v16; // r13
  __int64 v17; // r14
  __int64 v18; // r15
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // r9d
  __int64 v23; // rdx
  __int16 v24; // r10
  __int64 v25; // r8
  int v26; // eax
  u_long v27; // ecx
  u_long v28; // eax
  int v29; // edi
  __int16 v30; // r11
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // r10d
  __int64 v34; // rdx
  __int16 v35; // r9
  __int64 v36; // r8
  const CHAR *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // r8d
  __int64 v41; // r9
  __int64 *v42; // rbx
  __int64 v43; // rcx
  int v44; // ecx
  int v45; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 numEntriesReturned; // [rsp+34h] [rbp-CCh] BYREF
  DWORD v47; // [rsp+38h] [rbp-C8h]
  void *p; // [rsp+40h] [rbp-C0h] BYREF
  int v49; // [rsp+48h] [rbp-B8h]
  int v50; // [rsp+4Ch] [rbp-B4h]
  HANDLE enumHandle; // [rsp+50h] [rbp-B0h] BYREF
  IPSEC_SA_ENUM_TEMPLATE0 enumTemplate; // [rsp+58h] [rbp-A8h] BYREF
  int v53; // [rsp+5Ch] [rbp-A4h] BYREF
  int v54; // [rsp+60h] [rbp-A0h]
  DdmModernDevice *v55; // [rsp+68h] [rbp-98h]
  __int128 Buf2; // [rsp+70h] [rbp-90h] BYREF
  int v57; // [rsp+80h] [rbp-80h]
  __int128 Buf1; // [rsp+90h] [rbp-70h] BYREF
  __int128 v59; // [rsp+A0h] [rbp-60h] BYREF
  int v60; // [rsp+B0h] [rbp-50h]
  __int128 v61; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t Buffer[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v63; // [rsp+CCh] [rbp-34h]
  __int128 v64; // [rsp+DCh] [rbp-24h]
  int v65; // [rsp+ECh] [rbp-14h]
  int v66; // [rsp+F0h] [rbp-10h] BYREF
  char v67[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  v1 = 0;
  v55 = this;
  v45 = 0;
  v66 = 0;
  v60 = 0;
  v53 = 20;
  v59 = 0;
  memset_0(v67, 0, sizeof(v67));
  *(_DWORD *)Buffer = 0;
  v65 = 0;
  v3 = *(_QWORD *)this;
  v63 = 0;
  v4 = *(__int64 (__fastcall **)(DdmModernDevice *, __int64, __int128 *, int *))(v3 + 416);
  v64 = 0;
  v61 = 0;
  v5 = v4(this, 13, &v59, &v53);
  if ( v5 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v6 = *((_DWORD *)this + 24);
      LOWORD(v66) = 0;
      Buffer[0] = 0;
      if ( v6 != -1 )
        _itow_s(v6, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v66, L"SaveIPSecInfo: failed to get remote addr 0x%x", v5);
      goto LABEL_6;
    }
    return;
  }
  v7 = 0;
  v8 = 0;
  v9 = *((_DWORD *)this + 2800) & 1;
  v57 = v60;
  numEntriesReturned = 0;
  v10 = v9 ^ 1;
  Buf2 = v59;
  v11 = 0;
  v54 = v9 ^ 1;
  enumHandle = 0;
  p = 0;
  enumTemplate.saDirection = FWP_DIRECTION_OUTBOUND;
  v50 = v9;
  v49 = 0;
  v45 = 0;
  while ( 1 )
  {
    if ( v11 )
    {
      FwpmFreeMemory0(&p);
      numEntriesReturned = 0;
    }
    enumTemplate.saDirection = v10;
    p = 0;
    RasIpsecTrace("DwQueryAssociations");
    DwInitializeIpSec(0);
    v12 = enumHandle;
    if ( !enumHandle )
    {
      v47 = IPsecSaCreateEnumHandle0(gFwpEngineHandle, &enumTemplate, &enumHandle);
      v13 = v47;
      if ( v47 )
      {
        RasIpsecTrace("DwQueryAssociations: Failed to get enum handle %d");
        if ( !IsServiceRunning() )
        {
          RasIpsecTrace("DwQueryAssociations: Ikeext service is not running");
          v13 = 827;
LABEL_20:
          v47 = v13;
          goto LABEL_21;
        }
        goto LABEL_21;
      }
      v12 = enumHandle;
    }
    v47 = IPsecSaEnum0(gFwpEngineHandle, v12, 0xAu, (IPSEC_SA_DETAILS0 ***)&p, &numEntriesReturned);
    v13 = v47;
    if ( v47 )
    {
      RasIpsecTrace("DwQueryAssociations: Failed to enum IPSec SA %d");
    }
    else if ( !numEntriesReturned )
    {
      IPsecSaDestroyEnumHandle0(gFwpEngineHandle, enumHandle);
      enumHandle = 0;
      v13 = 232;
      goto LABEL_20;
    }
LABEL_21:
    RasIpsecTrace("DwQueryAssociation rc=0x%x");
    v14 = p;
    if ( v13 || !p )
      break;
    if ( (_DWORD)Buf2 == 1 )
    {
      v7 = 0;
      if ( numEntriesReturned )
      {
        v15 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
        v16 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
        v17 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
        v18 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
        while ( 1 )
        {
          v19 = v14[v7];
          if ( *(_DWORD *)(v19 + 4) )
          {
            v20 = *(_DWORD *)(v19 + 28);
            *(_QWORD *)&Buf1 = v19 + 12;
          }
          else
          {
            *(_QWORD *)&Buf1 = v19 + 28;
            v20 = *(_DWORD *)(v19 + 12);
          }
          v21 = *(_QWORD *)(v19 + 160);
          v47 = v20;
          v22 = *(_DWORD *)(v21 + 112);
          if ( !v22 )
            goto LABEL_44;
          v23 = *(_QWORD *)(v21 + 120);
          v24 = 0;
          v25 = 0;
          do
          {
            if ( v16 == *(_QWORD *)(v23 + 40 * v25) && v15 == *(_QWORD *)(v23 + 40 * v25 + 8) )
            {
              v24 = *(_WORD *)(v23 + 40 * v25 + 32);
            }
            else if ( v18 == *(_QWORD *)(v23 + 40 * v25) && v17 == *(_QWORD *)(v23 + 40 * v25 + 8) )
            {
              v1 = *(_WORD *)(v23 + 40 * v25 + 32);
            }
            v25 = (unsigned int)(v25 + 1);
          }
          while ( (unsigned int)v25 < v22 );
          if ( v24 == 1701 )
          {
            v26 = v50;
          }
          else
          {
LABEL_44:
            v26 = v50;
            if ( !v50 || v1 != 1701 )
            {
              v1 = 0;
              goto LABEL_47;
            }
          }
          v1 = 0;
          if ( v26 )
            v27 = *(_DWORD *)Buf1;
          else
            v27 = v47;
          v28 = htonl(v27);
          v14 = p;
          if ( DWORD1(Buf2) == v28 )
            goto LABEL_68;
          v15 = *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4;
          v16 = *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1;
          v17 = *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4;
          v18 = *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1;
LABEL_47:
          if ( ++v7 >= numEntriesReturned )
            goto LABEL_68;
        }
      }
    }
    else if ( (_DWORD)Buf2 == 2 )
    {
      v7 = 0;
      if ( numEntriesReturned )
      {
        v29 = v50;
        do
        {
          v30 = 0;
          v31 = v14[v7];
          v32 = *(_QWORD *)(v31 + 160);
          v33 = *(_DWORD *)(v32 + 112);
          Buf1 = *(_OWORD *)(v31 + 28);
          if ( v33 )
          {
            v34 = *(_QWORD *)(v32 + 120);
            v35 = 0;
            v36 = 0;
            do
            {
              if ( *(_QWORD *)&FWPM_CONDITION_IP_LOCAL_PORT.Data1 == *(_QWORD *)(v34 + 40 * v36)
                && *(_QWORD *)FWPM_CONDITION_IP_LOCAL_PORT.Data4 == *(_QWORD *)(v34 + 40 * v36 + 8) )
              {
                v35 = *(_WORD *)(v34 + 40 * v36 + 32);
              }
              else if ( *(_QWORD *)&FWPM_CONDITION_IP_REMOTE_PORT.Data1 == *(_QWORD *)(v34 + 40 * v36)
                     && *(_QWORD *)FWPM_CONDITION_IP_REMOTE_PORT.Data4 == *(_QWORD *)(v34 + 40 * v36 + 8) )
              {
                v30 = *(_WORD *)(v34 + 40 * v36 + 32);
              }
              v36 = (unsigned int)(v36 + 1);
            }
            while ( (unsigned int)v36 < v33 );
            if ( v35 == 1701 )
              goto LABEL_116;
          }
          if ( v29 && v30 == 1701 )
          {
LABEL_116:
            if ( !memcmp_0(&Buf1, (char *)&Buf2 + 4, 0x10u) )
              break;
          }
          ++v7;
        }
        while ( v7 < numEntriesReturned );
        v13 = v47;
        v1 = 0;
LABEL_68:
        v8 = v49;
      }
    }
    if ( v7 == numEntriesReturned )
    {
      v37 = "No match found for the SA";
      goto LABEL_78;
    }
    v38 = 0;
    v39 = v14[v7];
    v40 = *(_DWORD *)(v39 + 104);
    if ( v40 )
    {
      v41 = *(_QWORD *)(v39 + 112);
      do
      {
        v8 = *(_DWORD *)(v41 + 16LL * (unsigned int)v38 + 4);
        v49 = v8;
        if ( v8 == 3 )
          goto LABEL_81;
        if ( v8 == 4 )
          goto LABEL_80;
        v38 = (unsigned int)(v38 + 1);
      }
      while ( (unsigned int)v38 < v40 );
    }
    if ( (_DWORD)v38 != v40 )
    {
      if ( v8 == 3 )
        goto LABEL_81;
LABEL_80:
      v42 = 0;
      if ( v8 == 4 )
LABEL_81:
        v42 = *(__int64 **)(*(_QWORD *)(v39 + 112) + 16 * v38 + 8);
      RasIpsecTrace("CipherId = (%d, %d)");
      if ( *v42 == 0x100000001LL && g_dwAllowL2TPWeakCrypto )
      {
        v45 |= 1u;
      }
      else
      {
        v43 = *v42;
        if ( *v42 == 0x200000002LL )
        {
          v45 |= 4u;
        }
        else
        {
          switch ( v43 )
          {
            case 0x300000003LL:
              v45 |= 0x10u;
              break;
            case 0x500000005LL:
              v45 |= 0x20u;
              break;
            case 0x400000004LL:
              v45 |= 0x40u;
              break;
            case 0x600000003LL:
              v45 |= 0x80u;
              break;
            case 0x700000004LL:
              v45 |= 0x100u;
              break;
            case 0x800000005LL:
              v45 |= 0x200u;
              break;
            default:
              if ( v43 == 0x100000001LL && !g_dwAllowL2TPWeakCrypto )
              {
                RasIpsecTrace("Cipher Id obtained is not supported.");
                goto LABEL_103;
              }
              break;
          }
        }
      }
      goto LABEL_104;
    }
    v37 = "No Encryption algorithm was returned";
LABEL_78:
    RasIpsecTrace(v37);
    v11 = p;
    v10 = v54;
  }
  RasIpsecTrace("QuerySA returned dwErr=0x%x, pSAList=0x%x");
LABEL_103:
  v13 = 774;
LABEL_104:
  if ( enumHandle )
  {
    IPsecSaDestroyEnumHandle0(gFwpEngineHandle, enumHandle);
    enumHandle = 0;
  }
  if ( p )
    FwpmFreeMemory0(&p);
  if ( v13 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v66) = 0;
      Buffer[0] = 0;
      v44 = *((_DWORD *)v55 + 24);
      if ( v44 != -1 )
        _itow_s(v44, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v66, L"SaveIPSecInfo: failed to get ipsec info. 0x%x", v13);
LABEL_6:
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v66,
          (unsigned int)&v61,
          0,
          (__int64)Buffer);
    }
  }
  else
  {
    (*(void (__fastcall **)(DdmModernDevice *, __int64, int *))(*(_QWORD *)v55 + 424LL))(v55, 7, &v45);
  }
}

```

## disassembly

```asm
0x1800441d8  push    rbp
0x1800441da  push    rbx
0x1800441db  push    rsi
0x1800441dc  push    rdi
0x1800441dd  push    r12
0x1800441df  push    r13
0x1800441e1  push    r14
0x1800441e3  push    r15
0x1800441e5  lea     rbp, [rsp-808h]
0x1800441ed  sub     rsp, 908h
0x1800441f4  mov     rax, cs:__security_cookie
0x1800441fb  xor     rax, rsp
0x1800441fe  mov     [rbp+840h+var_50], rax
0x180044205  xor     r12d, r12d
0x180044208  mov     [rsp+940h+var_8D8], rcx
0x18004420d  mov     r15, rcx
0x180044210  mov     [rsp+940h+var_910], r12d
0x180044215  xorps   xmm0, xmm0
0x180044218  mov     [rbp+840h+var_850], r12d
0x18004421c  xor     eax, eax
0x18004421e  lea     rcx, [rbp+840h+var_84C]; void *
0x180044222  lea     r13d, [r12+14h]
0x180044227  mov     [rbp+840h+var_890], eax
0x18004422a  xor     edx, edx; Val
0x18004422c  mov     [rsp+940h+var_8E4], r13d
0x180044231  mov     r8d, 7FCh; Size
0x180044237  movups  [rbp+840h+var_8A0], xmm0
0x18004423b  call    memset_0
0x180044240  xor     eax, eax
0x180044242  mov     dword ptr [rbp+840h+Buffer], r12d
0x180044246  xorps   xmm0, xmm0
0x180044249  mov     [rbp+840h+var_854], eax
0x18004424c  mov     rax, [r15]
0x18004424f  lea     r9, [rsp+940h+var_8E4]
0x180044254  lea     r8, [rbp+840h+var_8A0]
0x180044258  mov     rcx, r15
0x18004425b  lea     edx, [r12+0Dh]
0x180044260  movups  [rbp+840h+var_874], xmm0
0x180044264  mov     rax, [rax+1A0h]
0x18004426b  movups  [rbp+840h+var_864], xmm0
0x18004426f  movups  [rbp+840h+var_888], xmm0
0x180044273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044278  mov     ebx, eax
0x18004427a  test    eax, eax
0x18004427c  jz      loc_180044302
0x180044282  test    cs:byte_1800C8404, 8
0x180044289  jz      loc_180044864
0x18004428f  mov     ecx, [r15+60h]; Value
0x180044293  mov     word ptr [rbp+840h+var_850], r12w
0x180044298  mov     [rbp+840h+Buffer], r12w
0x18004429d  cmp     ecx, 0FFFFFFFFh
0x1800442a0  jz      short loc_1800442B4
0x1800442a2  lea     r9d, [r12+0Ah]; Radix
0x1800442a7  mov     r8d, r13d; BufferCount
0x1800442aa  lea     rdx, [rbp+840h+Buffer]; Buffer
0x1800442ae  call    cs:__imp__itow_s
0x1800442b4  mov     r8d, ebx
0x1800442b7  lea     rdx, aSaveipsecinfoF_0; "SaveIPSecInfo: failed to get remote add"...
0x1800442be  lea     rcx, [rbp+840h+var_850]
0x1800442c2  call    FormatRRASErrorString
0x1800442c7  test    cs:byte_1800C8404, 8
0x1800442ce  jz      loc_180044864
0x1800442d4  lea     rax, [rbp+840h+Buffer]
0x1800442d8  mov     [rsp+940h+var_918], rax
0x1800442dd  lea     r9, [rbp+840h+var_888]
0x1800442e1  lea     r8, [rbp+840h+var_850]
0x1800442e5  mov     [rsp+940h+numEntriesReturned], r12
0x1800442ea  lea     rdx, RasDdmParamTraceError
0x1800442f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800442f8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800442fd  jmp     loc_180044864
0x180044302  mov     eax, [rbp+840h+var_890]
0x180044305  mov     ebx, r12d
0x180044308  mov     ecx, [r15+2BC0h]
0x18004430f  mov     r14d, r12d
0x180044312  movups  xmm0, [rbp+840h+var_8A0]
0x180044316  and     ecx, 1
0x180044319  mov     [rbp+840h+var_8C0], eax
0x18004431c  mov     edi, ecx
0x18004431e  mov     [rsp+940h+var_90C], r12d
0x180044323  xor     edi, 1
0x180044326  movaps  [rsp+940h+Buf2], xmm0
0x18004432b  mov     rax, r12
0x18004432e  mov     [rsp+940h+var_8E0], edi
0x180044332  mov     [rsp+940h+enumHandle], r12
0x180044337  mov     [rsp+940h+p], rax
0x18004433c  mov     [rsp+940h+enumTemplate.saDirection], r12d
0x180044341  mov     [rsp+940h+var_8F4], ecx
0x180044345  mov     [rsp+940h+var_8F8], r12d
0x18004434a  mov     [rsp+940h+var_910], r12d
0x18004434f  test    rax, rax
0x180044352  jz      short loc_180044364
0x180044354  lea     rcx, [rsp+940h+p]; p
0x180044359  call    cs:__imp_FwpmFreeMemory0
0x18004435f  mov     [rsp+940h+var_90C], r12d
0x180044364  lea     rcx, aDwqueryassocia_2; "DwQueryAssociations"
0x18004436b  mov     [rsp+940h+enumTemplate.saDirection], edi
0x18004436f  mov     [rsp+940h+p], r12
0x180044374  call    RasIpsecTrace
0x180044379  xor     ecx, ecx
0x18004437b  call    DwInitializeIpSec
0x180044380  mov     rdx, [rsp+940h+enumHandle]
0x180044385  test    rdx, rdx
0x180044388  jnz     short loc_1800443DA
0x18004438a  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180044391  lea     r8, [rsp+940h+enumHandle]; enumHandle
0x180044396  lea     rdx, [rsp+940h+enumTemplate]; enumTemplate
0x18004439b  call    cs:__imp_IPsecSaCreateEnumHandle0
0x1800443a1  mov     [rsp+940h+var_908], eax
0x1800443a5  mov     edi, eax
0x1800443a7  test    eax, eax
0x1800443a9  jz      short loc_1800443D5
0x1800443ab  mov     edx, eax
0x1800443ad  lea     rcx, aDwqueryassocia_3; "DwQueryAssociations: Failed to get enum"...
0x1800443b4  call    RasIpsecTrace
0x1800443b9  call    IsServiceRunning
0x1800443be  test    eax, eax
0x1800443c0  jnz     short loc_18004443D
0x1800443c2  lea     rcx, aDwqueryassocia_0; "DwQueryAssociations: Ikeext service is "...
0x1800443c9  call    RasIpsecTrace
0x1800443ce  mov     edi, 33Bh
0x1800443d3  jmp     short loc_180044439
0x1800443d5  mov     rdx, [rsp+940h+enumHandle]; enumHandle
0x1800443da  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800443e1  lea     rax, [rsp+940h+var_90C]
0x1800443e6  lea     r9, [rsp+940h+p]; entries
0x1800443eb  mov     [rsp+940h+numEntriesReturned], rax; numEntriesReturned
0x1800443f0  mov     r8d, 0Ah; numEntriesRequested
0x1800443f6  call    cs:__imp_IPsecSaEnum0
0x1800443fc  mov     [rsp+940h+var_908], eax
0x180044400  mov     edi, eax
0x180044402  test    eax, eax
0x180044404  jz      short loc_180044416
0x180044406  mov     edx, eax
0x180044408  lea     rcx, aDwqueryassocia; "DwQueryAssociations: Failed to enum IPS"...
0x18004440f  call    RasIpsecTrace
0x180044414  jmp     short loc_18004443D
0x180044416  cmp     [rsp+940h+var_90C], r12d
0x18004441b  jnz     short loc_18004443D
0x18004441d  mov     rdx, [rsp+940h+enumHandle]; enumHandle
0x180044422  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180044429  call    cs:__imp_IPsecSaDestroyEnumHandle0
0x18004442f  mov     [rsp+940h+enumHandle], r12
0x180044434  mov     edi, 0E8h
0x180044439  mov     [rsp+940h+var_908], edi
0x18004443d  mov     edx, edi
0x18004443f  lea     rcx, aDwqueryassocia_1; "DwQueryAssociation rc=0x%x"
0x180044446  call    RasIpsecTrace
0x18004444b  mov     rsi, [rsp+940h+p]
0x180044450  test    edi, edi
0x180044452  jnz     loc_1800447B6
0x180044458  test    rsi, rsi
0x18004445b  jz      loc_1800447B6
0x180044461  cmp     dword ptr [rsp+940h+Buf2], 1
0x180044466  jnz     loc_18004458A
0x18004446c  mov     ebx, r12d
0x18004446f  cmp     [rsp+940h+var_90C], r12d
0x180044474  jbe     loc_18004466F
0x18004447a  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x180044481  mov     r13, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180044488  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x18004448f  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180044496  mov     eax, ebx
0x180044498  mov     rcx, [rsi+rax*8]
0x18004449c  lea     rax, [rcx+1Ch]
0x1800444a0  lea     rdx, [rcx+0Ch]
0x1800444a4  cmp     [rcx+4], r12d
0x1800444a8  jnz     short loc_1800444B2
0x1800444aa  mov     qword ptr [rbp+840h+Buf1], rax
0x1800444ae  mov     eax, [rdx]
0x1800444b0  jmp     short loc_1800444B8
0x1800444b2  mov     eax, [rax]
0x1800444b4  mov     qword ptr [rbp+840h+Buf1], rdx
0x1800444b8  mov     rdx, [rcx+0A0h]
0x1800444bf  mov     [rsp+940h+var_908], eax
0x1800444c3  mov     r9d, [rdx+70h]
0x1800444c7  test    r9d, r9d
0x1800444ca  jz      loc_18004455D
0x1800444d0  mov     rdx, [rdx+78h]
0x1800444d4  xor     r10d, r10d
0x1800444d7  xor     r8d, r8d
0x1800444da  lea     rcx, [r8+r8*4]
0x1800444de  cmp     r13, [rdx+rcx*8]
0x1800444e2  jnz     short loc_1800444F3
0x1800444e4  cmp     r11, [rdx+rcx*8+8]
0x1800444e9  jnz     short loc_1800444F3
0x1800444eb  movzx   r10d, word ptr [rdx+rcx*8+20h]
0x1800444f1  jmp     short loc_180044506
0x1800444f3  cmp     r15, [rdx+rcx*8]
0x1800444f7  jnz     short loc_180044506
0x1800444f9  cmp     r14, [rdx+rcx*8+8]
0x1800444fe  jnz     short loc_180044506
0x180044500  movzx   r12d, word ptr [rdx+rcx*8+20h]
0x180044506  inc     r8d
0x180044509  cmp     r8d, r9d
0x18004450c  jb      short loc_1800444DA
0x18004450e  mov     ecx, 6A5h
0x180044513  cmp     cx, r10w
0x180044517  jnz     short loc_180044562
0x180044519  mov     eax, [rsp+940h+var_8F4]
0x18004451d  xor     r12d, r12d
0x180044520  test    eax, eax
0x180044522  jz      short loc_180044584
0x180044524  mov     rcx, qword ptr [rbp+840h+Buf1]
0x180044528  mov     ecx, [rcx]; hostlong
0x18004452a  call    cs:__imp_htonl
0x180044530  mov     rsi, [rsp+940h+p]
0x180044535  cmp     dword ptr [rsp+940h+Buf2+4], eax
0x180044539  jz      loc_18004466A
0x18004453f  mov     r11, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x180044546  mov     r13, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18004454d  mov     r14, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x180044554  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18004455b  jmp     short loc_180044573
0x18004455d  mov     ecx, 6A5h
0x180044562  mov     eax, [rsp+940h+var_8F4]
0x180044566  test    eax, eax
0x180044568  jz      short loc_180044570
0x18004456a  cmp     cx, r12w
0x18004456e  jz      short loc_18004451D
0x180044570  xor     r12d, r12d
0x180044573  inc     ebx
0x180044575  cmp     ebx, [rsp+940h+var_90C]
0x180044579  jb      loc_180044496
0x18004457f  jmp     loc_18004466A
0x180044584  mov     ecx, [rsp+940h+var_908]
0x180044588  jmp     short loc_18004452A
0x18004458a  cmp     dword ptr [rsp+940h+Buf2], 2
0x18004458f  jnz     loc_18004466F
0x180044595  mov     ebx, r12d
0x180044598  cmp     [rsp+940h+var_90C], r12d
0x18004459d  jbe     loc_18004466F
0x1800445a3  mov     r14, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data4
0x1800445aa  mov     r13, qword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x1800445b1  mov     r15, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data4
0x1800445b8  mov     r12, qword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x1800445bf  mov     edi, [rsp+940h+var_8F4]
0x1800445c3  mov     eax, ebx
0x1800445c5  xor     r11d, r11d
0x1800445c8  mov     rcx, [rsi+rax*8]
0x1800445cc  mov     rdx, [rcx+0A0h]
0x1800445d3  movups  xmm0, xmmword ptr [rcx+1Ch]
0x1800445d7  mov     r10d, [rdx+70h]
0x1800445db  movdqu  [rbp+840h+Buf1], xmm0
0x1800445e0  test    r10d, r10d
0x1800445e3  jz      short loc_180044630
0x1800445e5  mov     rdx, [rdx+78h]
0x1800445e9  xor     r9d, r9d
0x1800445ec  xor     r8d, r8d
0x1800445ef  lea     rcx, [r8+r8*4]
0x1800445f3  cmp     r13, [rdx+rcx*8]
0x1800445f7  jnz     short loc_180044608
0x1800445f9  cmp     r14, [rdx+rcx*8+8]
0x1800445fe  jnz     short loc_180044608
0x180044600  movzx   r9d, word ptr [rdx+rcx*8+20h]
0x180044606  jmp     short loc_18004461B
0x180044608  cmp     r12, [rdx+rcx*8]
0x18004460c  jnz     short loc_18004461B
0x18004460e  cmp     r15, [rdx+rcx*8+8]
0x180044613  jnz     short loc_18004461B
0x180044615  movzx   r11d, word ptr [rdx+rcx*8+20h]
0x18004461b  inc     r8d
0x18004461e  cmp     r8d, r10d
0x180044621  jb      short loc_1800445EF
0x180044623  mov     eax, 6A5h
0x180044628  cmp     ax, r9w
0x18004462c  jz      short loc_18004463F
0x18004462e  jmp     short loc_180044635
0x180044630  mov     eax, 6A5h
0x180044635  test    edi, edi
0x180044637  jz      short loc_180044657
0x180044639  cmp     ax, r11w
0x18004463d  jnz     short loc_180044657
0x18004463f  mov     r8d, 10h; Size
0x180044645  lea     rdx, [rsp+940h+Buf2+4]; Buf2
0x18004464a  lea     rcx, [rbp+840h+Buf1]; Buf1
0x18004464e  call    memcmp_0
0x180044653  test    eax, eax
0x180044655  jz      short loc_180044663
0x180044657  inc     ebx
0x180044659  cmp     ebx, [rsp+940h+var_90C]
0x18004465d  jb      loc_1800445C3
0x180044663  mov     edi, [rsp+940h+var_908]
0x180044667  xor     r12d, r12d
0x18004466a  mov     r14d, [rsp+940h+var_8F8]
0x18004466f  cmp     ebx, [rsp+940h+var_90C]
0x180044673  jnz     short loc_18004467E
0x180044675  lea     rcx, aNoMatchFoundFo; "No match found for the SA"
0x18004467c  jmp     short loc_1800446C2
0x18004467e  mov     eax, ebx
0x180044680  mov     ecx, r12d
0x180044683  mov     rdx, [rsi+rax*8]
0x180044687  mov     r8d, [rdx+68h]
0x18004468b  test    r8d, r8d
0x18004468e  jz      short loc_1800446B6
0x180044690  mov     r9, [rdx+70h]
0x180044694  mov     eax, ecx
0x180044696  add     rax, rax
0x180044699  mov     r14d, [r9+rax*8+4]
0x18004469e  mov     [rsp+940h+var_8F8], r14d
  ... truncated ...
```
