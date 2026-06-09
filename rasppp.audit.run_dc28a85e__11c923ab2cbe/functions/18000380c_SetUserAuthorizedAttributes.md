# SetUserAuthorizedAttributes

- ea: `0x18000380c`
- end: `0x1800041ca`
- name: `SetUserAuthorizedAttributes`
- size: `2494`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800023c0`
- `0x180015100`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000339c`
- `0x180003568`
- `0x1800036f8`
- `0x18000380c`
- `0x18001063c`
- `0x180011230`
- `0x18001ae70`
- `0x18001b424`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## string_xrefs

- `0x180003e91`: `Tunnel type configuration mismatch, returning ERROR_WRONG_TUNNEL_TYPE`
- `0x180004094`: `Service Type %d is not of type Framed`

## pseudocode

```c
__int64 __fastcall SetUserAuthorizedAttributes(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  unsigned int v8; // r15d
  __int64 v9; // rcx
  int v10; // eax
  int v11; // edi
  __int64 VendorSpecific; // rax
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // rax
  bool v16; // zf
  const wchar_t *v17; // r8
  __int64 result; // rax
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // r10d
  int v23; // r8d
  __int64 v24; // rax
  int v25; // ecx
  unsigned __int8 *v26; // rax
  _QWORD *v27; // rsi
  __int64 v28; // r14
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // r14d
  __int64 v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // edi
  int v35; // ecx
  int v36; // esi
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  bool v44; // zf
  int v45; // edi
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rax
  unsigned int v54; // edx
  __int64 v55; // r8
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rax
  int v59; // ecx
  __int64 v60; // rdi
  __int64 v61; // rax
  __int64 v62; // r8
  __int64 v63; // rdx
  int v64; // eax
  __int64 v65; // r8
  __int64 v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+30h] [rbp-D0h] BYREF
  int v68; // [rsp+34h] [rbp-CCh] BYREF
  int v69; // [rsp+38h] [rbp-C8h]
  unsigned int v70; // [rsp+3Ch] [rbp-C4h]
  int v71; // [rsp+40h] [rbp-C0h] BYREF
  char v72[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v69 = a3;
  v71 = 0;
  v70 = 0;
  v8 = 0;
  memset_0(v72, 0, sizeof(v72));
  CreateAccountingAttributes(a1);
  v10 = (unsigned __int16)*(_DWORD *)(a1 + 60);
  v67 = v10;
  if ( v10 == 9 || (v11 = 0, v10 == 14) )
    v11 = 1;
  VendorSpecific = RasAuthAttributeGetVendorSpecific(v9, 7, a2);
  if ( VendorSpecific )
  {
    v14 = *(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 9LL)
        + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 6LL) << 24)
        + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 8LL) << 8)
        + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 7LL) << 16);
    v70 = v14;
    v15 = RasAuthAttributeGetVendorSpecific(v13, 8, a2);
    if ( v15 )
    {
      v8 = *(unsigned __int8 *)(*(_QWORD *)(v15 + 8) + 9LL)
         + (*(unsigned __int8 *)(*(_QWORD *)(v15 + 8) + 6LL) << 24)
         + (*(unsigned __int8 *)(*(_QWORD *)(v15 + 8) + 8LL) << 8)
         + (*(unsigned __int8 *)(*(_QWORD *)(v15 + 8) + 7LL) << 16);
      if ( v14 == 2 )
      {
        if ( v11 )
          goto LABEL_32;
        if ( !g_dwAllowPPTPWeakCrypto )
        {
          if ( (*(_BYTE *)(*(_QWORD *)(v15 + 8) + 9LL) & 4) != 0 )
          {
            *(_DWORD *)(a1 + 184) |= 0x1000u;
            LOBYTE(v68) = byte_18004DF34 & 1;
            if ( (byte_18004DF34 & 1) == 0 )
              goto LABEL_32;
            v17 = L"Strong encryption";
LABEL_31:
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, v17);
            goto LABEL_32;
          }
          if ( v8 )
          {
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasPppTraceInfo,
                L"Encryption policy not supported");
            return 741;
          }
          *(_DWORD *)(a1 + 184) |= 0x80000u;
          v16 = (byte_18004DF34 & 1) == 0;
          LOBYTE(v68) = byte_18004DF34 & 1;
LABEL_29:
          if ( v16 )
            goto LABEL_32;
          v17 = L"Encryption is not allowed";
          goto LABEL_31;
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v15 + 8) + 9LL) & 0xA) != 0 )
        {
          *(_DWORD *)(a1 + 184) |= 0x80u;
          LOBYTE(v68) = byte_18004DF34 & 1;
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, L"Encryption");
        }
        if ( (v8 & 4) != 0 )
        {
          *(_DWORD *)(a1 + 184) |= 0x1000u;
          LOBYTE(v68) = byte_18004DF34 & 1;
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceInfo,
              L"Strong encryption");
        }
        if ( !v8 )
        {
          *(_DWORD *)(a1 + 184) |= 0x80000u;
          v16 = (byte_18004DF34 & 1) == 0;
          LOBYTE(v68) = byte_18004DF34 & 1;
          goto LABEL_29;
        }
      }
      else if ( v14 == 1 && !v11 && !v8 )
      {
        *(_DWORD *)(a1 + 184) |= 0x80000u;
        v16 = (byte_18004DF34 & 1) == 0;
        LOBYTE(v68) = byte_18004DF34 & 1;
        goto LABEL_29;
      }
    }
  }
LABEL_32:
  v19 = *(_DWORD *)(a1 + 56);
  if ( (v19 & 0x200) != 0 )
  {
    v27 = (_QWORD *)(a1 + 16);
    goto LABEL_51;
  }
  v20 = RasAuthAttributeGetVendorSpecific(v13, 12, a2);
  v22 = v20;
  if ( !v20 )
  {
    v27 = (_QWORD *)(a1 + 16);
    goto LABEL_44;
  }
  v23 = 0;
  v24 = *(_QWORD *)(a1 + 1472);
  v25 = *(_DWORD *)((-(__int64)(v69 != 0) & 0xFFFFFFFFFFFFFF38uLL) + v24 + 1420);
  if ( v25 == 49699 )
  {
    if ( v69 )
      v26 = *(unsigned __int8 **)(v24 + 1232);
    else
      v26 = *(unsigned __int8 **)(v24 + 1432);
    v23 = *v26;
  }
  v27 = (_QWORD *)(a1 + 16);
  result = SetMsChapMppeKeys(*(_QWORD *)(a1 + 16), v22, a4, a5, v25, v23);
  if ( !(_DWORD)result )
  {
    LOBYTE(v68) = byte_18004DF34 & 1;
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"MS-CHAP-MPPE-Keys set");
    *(_DWORD *)(a1 + 56) |= 0x200u;
    v19 = *(_DWORD *)(a1 + 56);
LABEL_44:
    v28 = RasAuthAttributeGetVendorSpecific(v21, 16, a2);
    v30 = RasAuthAttributeGetVendorSpecific(v29, 17, a2);
    if ( v28 && v30 )
    {
      result = SetMsMppeSendRecvKeys(*v27, v28, v30);
      if ( (_DWORD)result )
        return result;
      LOBYTE(v68) = byte_18004DF34 & 1;
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"MPPE-Send/Recv-Keys set");
      *(_DWORD *)(a1 + 56) |= 0x200u;
      v19 = *(_DWORD *)(a1 + 56);
    }
LABEL_51:
    if ( (v19 & 0x200) == 0 )
      SetNoMppeKeys(*v27);
    v31 = v67;
    if ( v67 != 9 )
    {
      v36 = v69;
      if ( v67 == 14 )
      {
        *(_DWORD *)(a1 + 184) &= 0xFFFFEF7F;
        *(_DWORD *)(a1 + 184) |= 0x80000u;
      }
      goto LABEL_103;
    }
    v32 = *v27;
    v67 = 0;
    v68 = 4;
    v33 = ((__int64 (__fastcall *)(__int64, __int64, int *, int *))qword_18004D408)(v32, 7, &v67, &v68);
    if ( v33 )
    {
      if ( byte_18004DF33 < 0 )
      {
        LOWORD(v71) = 0;
        FormatRRASErrorString(&v71, L"RasGetPortUserData failed: 0x%x", v33);
        if ( byte_18004DF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v71);
      }
    }
    v34 = v70;
    if ( (byte_18004DF34 & 1) != 0 )
    {
      LODWORD(v66) = v67;
      LOWORD(v71) = 0;
      FormatRRASErrorString(&v71, L"Checking encryption. Policy=0x%x,Types=0x%x,Mask=0x%x", v70, v8, v66);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v71);
    }
    v35 = v67;
    switch ( v67 )
    {
      case 1:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x800u;
        break;
      case 16:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x8000u;
        break;
      case 4:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x2000u;
        break;
      case 32:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x10000u;
        break;
      case 64:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x20000u;
        break;
      case 128:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x40000u;
        break;
      case 256:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x80000u;
        break;
      case 512:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x100000u;
        break;
      default:
        goto LABEL_78;
    }
    v35 = v67;
LABEL_78:
    v36 = v69;
    if ( !v69 )
    {
      if ( (*(_DWORD *)(a1 + 184) & 0x81080) == 0x1000 && v35 != 4 && v35 != 32 )
        return 742;
      *(_DWORD *)(a1 + 184) &= 0xFFFFEF7F;
LABEL_103:
      if ( g_dwAllowPPTPWeakCrypto == 1 && (*(_DWORD *)(a1 + 184) & 0x1080) != 0
        || !g_dwAllowPPTPWeakCrypto && (*(_DWORD *)(a1 + 184) & 0x1000) != 0 )
      {
        v45 = *(_DWORD *)(a1 + 56);
        if ( (v45 & 0x200) == 0 || (unsigned int)GetCpIndexFromProtocol(33021) == -1 )
        {
          *(_DWORD *)(a1 + 56) = v45 | 0x2000;
          return 741;
        }
      }
      if ( v36 )
      {
        v46 = RasAuthAttributeGet(7, a2);
        if ( v46 && *(_DWORD *)(v46 + 8) != 1 )
        {
          result = 794;
          goto LABEL_152;
        }
        v48 = RasAuthAttributeGet(64, v47);
        if ( v48
          && (v31 == 8 && *(_DWORD *)(v48 + 8) != 1
           || v31 == 9 && *(_DWORD *)(v48 + 8) != 3
           || v31 == 14 && *(_DWORD *)(v48 + 8) != 79617) )
        {
          *(_DWORD *)(a1 + 56) |= 0x2000u;
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceError,
              L"Tunnel type configuration mismatch, returning ERROR_WRONG_TUNNEL_TYPE");
          return 795;
        }
        v50 = RasAuthAttributeGet(8099, v49);
        if ( v50 )
          v52 = *(_DWORD *)(v50 + 8);
        else
          v52 = 0;
        *(_DWORD *)(a1 + 144) = v52;
        v53 = RasAuthAttributeGetVendorSpecific(v51, 10, a2);
        if ( v53 )
        {
          v54 = 15;
          if ( (unsigned int)(*(_DWORD *)(v53 + 4) - 7) < 0xF )
            v54 = *(_DWORD *)(v53 + 4) - 7;
          *(_OWORD *)(*(_QWORD *)(a1 + 8) + 473LL) = 0;
          memcpy_0((void *)(*(_QWORD *)(a1 + 8) + 473LL), (const void *)(*(_QWORD *)(v53 + 8) + 7LL), v54);
          if ( (byte_18004DF34 & 1) != 0 )
          {
            v55 = *(_QWORD *)(a1 + 8) + 473LL;
            LOWORD(v71) = 0;
            FormatRRASErrorString(&v71, L"Auth Attribute Domain = %hs", v55);
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v71);
          }
        }
        *(_DWORD *)(a1 + 112) = 1;
        *(_BYTE *)(a1 + 1536) = 0;
        v56 = RasAuthAttributeGet(6, a2);
        if ( v56 )
        {
          if ( *(_DWORD *)(v56 + 8) == 4 )
          {
            v58 = RasAuthAttributeGet(19, v57);
            v60 = v58;
            if ( v58 && *(_DWORD *)(v58 + 4) )
            {
              *(_DWORD *)(a1 + 112) = 2;
              memset_0((void *)(a1 + 1536), 0, (unsigned int)(v59 + 110));
              memcpy_0((void *)(a1 + 1536), *(const void **)(v60 + 8), *(unsigned int *)(v60 + 4));
              if ( (byte_18004DF34 & 1) != 0 )
              {
                LOWORD(v71) = 0;
                FormatRRASErrorString(&v71, L"Auth Attribute Forced callback to %hs", a1 + 1536);
                if ( (byte_18004DF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v71);
              }
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) &= ~4u;
            }
            else
            {
              *(_DWORD *)(a1 + 112) = 5;
              if ( (byte_18004DF34 & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasPppTraceInfo,
                  L"Auth Attribute Caller Specifiable callback");
            }
          }
          else if ( *(_DWORD *)(v56 + 8) != 2 )
          {
            if ( (byte_18004DF34 & 1) != 0 )
            {
              LOWORD(v71) = 0;
              FormatRRASErrorString(&v71, L"Service Type %d is not of type Framed", *(unsigned int *)(v56 + 8));
              if ( (byte_18004DF34 & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v71);
            }
            result = 796;
            goto LABEL_152;
          }
        }
        if ( (*(_BYTE *)(a1 + 112) & 6) != 0 )
          *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 2u;
        v61 = RasAuthAttributeGet(28, a2);
        if ( v61 )
        {
          v62 = *(unsigned int *)(v61 + 8);
          *(_DWORD *)(a1 + 88) = v62;
        }
        else
        {
          *(_DWORD *)(a1 + 88) = dword_18004DA14;
          v62 = (unsigned int)dword_18004DA14;
        }
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v71) = 0;
          FormatRRASErrorString(&v71, L"Auth Attribute Idle Timeout Seconds = %d", v62);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v71);
        }
        v63 = RasAuthAttributeGet(62, a2);
        v64 = dword_18004DA0C;
        if ( v63 && *(_DWORD *)(v63 + 8) )
          v64 = *(_DWORD *)(v63 + 8);
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL) = v64;
        if ( (byte_18004DF34 & 1) != 0 )
        {
          v65 = *(_QWORD *)(a1 + 8);
          LOWORD(v71) = 0;
          FormatRRASErrorString(&v71, L"AuthAttribute MaxChannelsAllowed = %d", *(unsigned int *)(v65 + 24));
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v71);
        }
      }
      return 0;
    }
    if ( !v34 )
      goto LABEL_103;
    if ( !v35 )
    {
      if ( v34 != 2 || !v8 )
        goto LABEL_103;
LABEL_100:
      result = 742;
LABEL_152:
      *(_DWORD *)(a1 + 56) |= 0x2000u;
      return result;
    }
    v37 = v35 - 1;
    if ( !v37 )
      goto LABEL_97;
    v38 = v37 - 3;
    if ( v38 )
    {
      v39 = v38 - 12;
      if ( !v39 )
        goto LABEL_97;
      v40 = v39 - 16;
      if ( v40 )
      {
        v41 = v40 - 32;
        if ( v41 )
        {
          v42 = v41 - 64;
          if ( v42 )
          {
            v43 = v42 - 128;
            if ( v43 )
            {
              if ( v43 != 256 )
                goto LABEL_103;
              goto LABEL_94;
            }
          }
        }
LABEL_97:
        v44 = (v8 & 0xA) == 0;
LABEL_95:
        if ( !v44 )
          goto LABEL_103;
        goto LABEL_100;
      }
    }
LABEL_94:
    v44 = (v8 & 4) == 0;
    goto LABEL_95;
  }
  return result;
}

```

## disassembly

```asm
0x18000380c  mov     [rsp-8+arg_10], rbx
0x180003811  push    rbp
0x180003812  push    rsi
0x180003813  push    rdi
0x180003814  push    r12
0x180003816  push    r13
0x180003818  push    r14
0x18000381a  push    r15
0x18000381c  lea     rbp, [rsp-750h]
0x180003824  sub     rsp, 850h
0x18000382b  mov     rax, cs:__security_cookie
0x180003832  xor     rax, rsp
0x180003835  mov     [rbp+780h+var_40], rax
0x18000383c  mov     r12, [rbp+780h+arg_20]
0x180003843  mov     r13, rdx
0x180003846  mov     [rsp+880h+var_848], r8d
0x18000384b  mov     rbx, rcx
0x18000384e  xor     eax, eax
0x180003850  lea     rcx, [rsp+880h+var_83C]; void *
0x180003855  xor     esi, esi
0x180003857  mov     [rsp+880h+var_840], eax
0x18000385b  xor     edx, edx; Val
0x18000385d  mov     [rsp+880h+var_844], esi
0x180003861  mov     r8d, 7FCh; Size
0x180003867  mov     r14, r9
0x18000386a  xor     r15d, r15d
0x18000386d  call    memset_0
0x180003872  mov     rcx, rbx
0x180003875  call    CreateAccountingAttributes
0x18000387a  mov     eax, [rbx+3Ch]
0x18000387d  movzx   eax, ax
0x180003880  mov     [rsp+880h+var_850], eax
0x180003884  cmp     eax, 9
0x180003887  jz      short loc_180003890
0x180003889  xor     edi, edi
0x18000388b  cmp     eax, 0Eh
0x18000388e  jnz     short loc_180003895
0x180003890  mov     edi, 1
0x180003895  mov     r8, r13
0x180003898  mov     edx, 7
0x18000389d  call    RasAuthAttributeGetVendorSpecific
0x1800038a2  test    rax, rax
0x1800038a5  jz      loc_180003A6B
0x1800038ab  mov     rdx, [rax+8]
0x1800038af  mov     r8, r13
0x1800038b2  movzx   esi, byte ptr [rdx+7]
0x1800038b6  movzx   eax, byte ptr [rdx+8]
0x1800038ba  shl     eax, 8
0x1800038bd  shl     esi, 10h
0x1800038c0  add     esi, eax
0x1800038c2  movzx   eax, byte ptr [rdx+6]
0x1800038c6  shl     eax, 18h
0x1800038c9  add     esi, eax
0x1800038cb  movzx   eax, byte ptr [rdx+9]
0x1800038cf  add     esi, eax
0x1800038d1  mov     edx, 8
0x1800038d6  mov     [rsp+880h+var_844], esi
0x1800038da  call    RasAuthAttributeGetVendorSpecific
0x1800038df  test    rax, rax
0x1800038e2  jz      loc_180003A6B
0x1800038e8  mov     rdx, [rax+8]
0x1800038ec  movzx   r15d, byte ptr [rdx+7]
0x1800038f1  movzx   eax, byte ptr [rdx+8]
0x1800038f5  shl     eax, 8
0x1800038f8  shl     r15d, 10h
0x1800038fc  add     r15d, eax
0x1800038ff  movzx   eax, byte ptr [rdx+6]
0x180003903  shl     eax, 18h
0x180003906  add     r15d, eax
0x180003909  movzx   eax, byte ptr [rdx+9]
0x18000390d  add     r15d, eax
0x180003910  cmp     esi, 2
0x180003913  jnz     loc_180003A2C
0x180003919  test    edi, edi
0x18000391b  jnz     loc_180003A6B
0x180003921  cmp     cs:g_dwAllowPPTPWeakCrypto, edi
0x180003927  jz      loc_1800039BB
0x18000392d  test    r15b, 0Ah
0x180003931  jz      short loc_180003963
0x180003933  bts     dword ptr [rbx+0B8h], 7
0x18000393b  mov     al, cs:byte_18004DF34
0x180003941  and     al, 1
0x180003943  mov     byte ptr [rsp+880h+var_84C], al
0x180003947  jz      short loc_180003963
0x180003949  lea     r8, aEncryption; "Encryption"
0x180003950  lea     rdx, RasPppTraceInfo
0x180003957  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000395e  call    McTemplateU0z_EventWriteTransfer
0x180003963  test    r15b, 4
0x180003967  jz      short loc_180003999
0x180003969  bts     dword ptr [rbx+0B8h], 0Ch
0x180003971  mov     al, cs:byte_18004DF34
0x180003977  and     al, 1
0x180003979  mov     byte ptr [rsp+880h+var_84C], al
0x18000397d  jz      short loc_180003999
0x18000397f  lea     r8, aStrongEncrypti; "Strong encryption"
0x180003986  lea     rdx, RasPppTraceInfo
0x18000398d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003994  call    McTemplateU0z_EventWriteTransfer
0x180003999  test    r15d, r15d
0x18000399c  jnz     loc_180003A6B
0x1800039a2  bts     dword ptr [rbx+0B8h], 13h
0x1800039aa  mov     al, cs:byte_18004DF34
0x1800039b0  and     al, 1
0x1800039b2  mov     byte ptr [rsp+880h+var_84C], al
0x1800039b6  jmp     loc_180003A4F
0x1800039bb  test    r15b, 4
0x1800039bf  jz      short loc_1800039E4
0x1800039c1  bts     dword ptr [rbx+0B8h], 0Ch
0x1800039c9  mov     al, cs:byte_18004DF34
0x1800039cf  and     al, 1
0x1800039d1  mov     byte ptr [rsp+880h+var_84C], al
0x1800039d5  jz      loc_180003A6B
0x1800039db  lea     r8, aStrongEncrypti; "Strong encryption"
0x1800039e2  jmp     short loc_180003A58
0x1800039e4  test    r15d, r15d
0x1800039e7  jnz     short loc_1800039FF
0x1800039e9  bts     dword ptr [rbx+0B8h], 13h
0x1800039f1  mov     al, cs:byte_18004DF34
0x1800039f7  and     al, 1
0x1800039f9  mov     byte ptr [rsp+880h+var_84C], al
0x1800039fd  jmp     short loc_180003A4F
0x1800039ff  test    cs:byte_18004DF34, 1
0x180003a06  jz      short loc_180003A22
0x180003a08  lea     r8, aEncryptionPoli; "Encryption policy not supported"
0x180003a0f  lea     rdx, RasPppTraceInfo
0x180003a16  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a1d  call    McTemplateU0z_EventWriteTransfer
0x180003a22  mov     eax, 2E5h
0x180003a27  jmp     loc_18000419F
0x180003a2c  cmp     esi, 1
0x180003a2f  jnz     short loc_180003A6B
0x180003a31  test    edi, edi
0x180003a33  jnz     short loc_180003A6B
0x180003a35  test    r15d, r15d
0x180003a38  jnz     short loc_180003A6B
0x180003a3a  bts     dword ptr [rbx+0B8h], 13h
0x180003a42  mov     al, cs:byte_18004DF34
0x180003a48  and     al, sil
0x180003a4b  mov     byte ptr [rsp+880h+var_84C], al
0x180003a4f  jz      short loc_180003A6B
0x180003a51  lea     r8, aEncryptionIsNo; "Encryption is not allowed"
0x180003a58  lea     rdx, RasPppTraceInfo
0x180003a5f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a66  call    McTemplateU0z_EventWriteTransfer
0x180003a6b  mov     edi, [rbx+38h]
0x180003a6e  bt      edi, 9
0x180003a72  jb      loc_180003BA8
0x180003a78  mov     r8, r13
0x180003a7b  mov     edx, 0Ch
0x180003a80  call    RasAuthAttributeGetVendorSpecific
0x180003a85  mov     r10, rax
0x180003a88  test    rax, rax
0x180003a8b  jz      loc_180003B32
0x180003a91  mov     r9d, [rsp+880h+var_848]
0x180003a96  xor     r8d, r8d
0x180003a99  mov     rax, [rbx+5C0h]
0x180003aa0  mov     ecx, r9d
0x180003aa3  neg     ecx
0x180003aa5  sbb     rdx, rdx
0x180003aa8  and     rdx, 0FFFFFFFFFFFFFF38h
0x180003aaf  mov     ecx, [rdx+rax+58Ch]
0x180003ab6  cmp     ecx, 0C223h
0x180003abc  jnz     short loc_180003AD7
0x180003abe  test    r9d, r9d
0x180003ac1  jz      short loc_180003ACC
0x180003ac3  mov     rax, [rax+4D0h]
0x180003aca  jmp     short loc_180003AD3
0x180003acc  mov     rax, [rax+598h]
0x180003ad3  movzx   r8d, byte ptr [rax]
0x180003ad7  mov     [rsp+880h+var_858], r8d
0x180003adc  lea     rsi, [rbx+10h]
0x180003ae0  mov     dword ptr [rsp+880h+var_860], ecx
0x180003ae4  mov     r9, r12
0x180003ae7  mov     rcx, [rsi]
0x180003aea  mov     r8, r14
0x180003aed  mov     rdx, r10
0x180003af0  call    SetMsChapMppeKeys
0x180003af5  xor     r12d, r12d
0x180003af8  test    eax, eax
0x180003afa  jnz     loc_18000419F
0x180003b00  mov     al, cs:byte_18004DF34
0x180003b06  and     al, 1
0x180003b08  mov     byte ptr [rsp+880h+var_84C], al
0x180003b0c  jz      short loc_180003B28
0x180003b0e  lea     r8, aMsChapMppeKeys; "MS-CHAP-MPPE-Keys set"
0x180003b15  lea     rdx, RasPppTraceInfo
0x180003b1c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b23  call    McTemplateU0z_EventWriteTransfer
0x180003b28  bts     dword ptr [rbx+38h], 9
0x180003b2d  mov     edi, [rbx+38h]
0x180003b30  jmp     short loc_180003B39
0x180003b32  lea     rsi, [rbx+10h]
0x180003b36  xor     r12d, r12d
0x180003b39  mov     r8, r13
0x180003b3c  mov     edx, 10h
0x180003b41  call    RasAuthAttributeGetVendorSpecific
0x180003b46  mov     r8, r13
0x180003b49  mov     edx, 11h
0x180003b4e  mov     r14, rax
0x180003b51  call    RasAuthAttributeGetVendorSpecific
0x180003b56  test    r14, r14
0x180003b59  jz      short loc_180003BAF
0x180003b5b  test    rax, rax
0x180003b5e  jz      short loc_180003BAF
0x180003b60  mov     rcx, [rsi]
0x180003b63  mov     r8, rax
0x180003b66  mov     rdx, r14
0x180003b69  call    SetMsMppeSendRecvKeys
0x180003b6e  test    eax, eax
0x180003b70  jnz     loc_18000419F
0x180003b76  mov     al, cs:byte_18004DF34
0x180003b7c  and     al, 1
0x180003b7e  mov     byte ptr [rsp+880h+var_84C], al
0x180003b82  jz      short loc_180003B9E
0x180003b84  lea     r8, aMppeSendRecvKe; "MPPE-Send/Recv-Keys set"
0x180003b8b  lea     rdx, RasPppTraceInfo
0x180003b92  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b99  call    McTemplateU0z_EventWriteTransfer
0x180003b9e  bts     dword ptr [rbx+38h], 9
0x180003ba3  mov     edi, [rbx+38h]
0x180003ba6  jmp     short loc_180003BAF
0x180003ba8  lea     rsi, [rbx+10h]
0x180003bac  xor     r12d, r12d
0x180003baf  bt      edi, 9
0x180003bb3  jb      short loc_180003BBD
0x180003bb5  mov     rcx, [rsi]
0x180003bb8  call    SetNoMppeKeys
0x180003bbd  mov     r14d, [rsp+880h+var_850]
0x180003bc2  cmp     r14d, 9
0x180003bc6  jnz     loc_180003DB3
0x180003bcc  mov     rcx, [rsi]
0x180003bcf  lea     r9, [rsp+880h+var_84C]
0x180003bd4  mov     rax, cs:qword_18004D408
0x180003bdb  lea     r8, [rsp+880h+var_850]
0x180003be0  lea     edx, [r14-2]
0x180003be4  mov     [rsp+880h+var_850], r12d
0x180003be9  mov     [rsp+880h+var_84C], 4
0x180003bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf6  test    eax, eax
0x180003bf8  jz      short loc_180003C3E
0x180003bfa  cmp     cs:byte_18004DF33, r12b
0x180003c01  jge     short loc_180003C3E
0x180003c03  mov     r8d, eax
0x180003c06  mov     word ptr [rsp+880h+var_840], r12w
0x180003c0c  lea     rdx, aRasgetportuser; "RasGetPortUserData failed: 0x%x"
0x180003c13  lea     rcx, [rsp+880h+var_840]
0x180003c18  call    FormatRRASErrorString
0x180003c1d  cmp     cs:byte_18004DF33, r12b
0x180003c24  jge     short loc_180003C3E
0x180003c26  lea     r8, [rsp+880h+var_840]
0x180003c2b  lea     rdx, RasPppTraceError
0x180003c32  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003c39  call    McTemplateU0z_EventWriteTransfer
0x180003c3e  test    cs:byte_18004DF34, 1
0x180003c45  mov     edi, [rsp+880h+var_844]
0x180003c49  jz      short loc_180003C91
0x180003c4b  mov     eax, [rsp+880h+var_850]
0x180003c4f  lea     rdx, aCheckingEncryp; "Checking encryption. Policy=0x%x,Types="...
0x180003c56  mov     r9d, r15d
0x180003c59  mov     dword ptr [rsp+880h+var_860], eax
0x180003c5d  mov     r8d, edi
0x180003c60  mov     word ptr [rsp+880h+var_840], r12w
0x180003c66  lea     rcx, [rsp+880h+var_840]
0x180003c6b  call    FormatRRASErrorString
0x180003c70  test    cs:byte_18004DF34, 1
0x180003c77  jz      short loc_180003C91
0x180003c79  lea     r8, [rsp+880h+var_840]
0x180003c7e  lea     rdx, RasPppTraceInfo
0x180003c85  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003c8c  call    McTemplateU0z_EventWriteTransfer
0x180003c91  mov     ecx, [rsp+880h+var_850]
0x180003c95  mov     edx, 100h
0x180003c9a  cmp     ecx, 1
0x180003c9d  jnz     short loc_180003CAA
0x180003c9f  mov     rax, [rbx+8]
0x180003ca3  bts     dword ptr [rax+34h], 0Bh
0x180003ca8  jmp     short loc_180003D1D
0x180003caa  cmp     ecx, 10h
0x180003cad  jnz     short loc_180003CBA
0x180003caf  mov     rax, [rbx+8]
0x180003cb3  bts     dword ptr [rax+34h], 0Fh
0x180003cb8  jmp     short loc_180003D1D
0x180003cba  cmp     ecx, 4
0x180003cbd  jnz     short loc_180003CCA
0x180003cbf  mov     rax, [rbx+8]
0x180003cc3  bts     dword ptr [rax+34h], 0Dh
0x180003cc8  jmp     short loc_180003D1D
0x180003cca  cmp     ecx, 20h ; ' '
0x180003ccd  jnz     short loc_180003CDA
0x180003ccf  mov     rax, [rbx+8]
0x180003cd3  bts     dword ptr [rax+34h], 10h
0x180003cd8  jmp     short loc_180003D1D
0x180003cda  cmp     ecx, 40h ; '@'
0x180003cdd  jnz     short loc_180003CEA
0x180003cdf  mov     rax, [rbx+8]
0x180003ce3  bts     dword ptr [rax+34h], 11h
0x180003ce8  jmp     short loc_180003D1D
0x180003cea  cmp     ecx, 80h
0x180003cf0  jnz     short loc_180003CFD
  ... truncated ...
```
