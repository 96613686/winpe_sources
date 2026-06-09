# SetUserAuthorizedAttributes

- ea: `0x180003770`
- end: `0x18000412d`
- name: `SetUserAuthorizedAttributes`
- size: `2493`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64 *, __int128 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800023a8`
- `0x1800149e0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180003308`
- `0x1800034d4`
- `0x180003660`
- `0x180003770`
- `0x18001016c`
- `0x180010cfc`
- `0x18001a4bc`
- `0x18001aa34`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## string_xrefs

- `0x180003df5`: `Tunnel type configuration mismatch, returning ERROR_WRONG_TUNNEL_TYPE`
- `0x180003ff8`: `Service Type %d is not of type Framed`

## pseudocode

```c
__int64 __fastcall SetUserAuthorizedAttributes(__int64 a1, __int64 a2, int a3, __int64 *a4, __int128 *a5)
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
  __int64 v20; // rcx
  __int64 v21; // r10
  int v22; // r8d
  __int64 v23; // rax
  int v24; // ecx
  unsigned __int8 *v25; // rax
  __int64 *v26; // rsi
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // r14d
  __int64 v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // edi
  int v34; // ecx
  int v35; // esi
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  bool v43; // zf
  int v44; // edi
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rax
  unsigned int v53; // edx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  int v58; // ecx
  __int64 v59; // rdi
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rdx
  int v63; // eax
  __int64 v64; // r8
  __int64 v65; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+30h] [rbp-D0h] BYREF
  int v67; // [rsp+34h] [rbp-CCh] BYREF
  int v68; // [rsp+38h] [rbp-C8h]
  unsigned int v69; // [rsp+3Ch] [rbp-C4h]
  int v70; // [rsp+40h] [rbp-C0h] BYREF
  char v71[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v68 = a3;
  v70 = 0;
  v69 = 0;
  v8 = 0;
  memset_0(v71, 0, sizeof(v71));
  CreateAccountingAttributes(a1);
  v10 = (unsigned __int16)*(_DWORD *)(a1 + 60);
  v66 = v10;
  if ( v10 == 9 || (v11 = 0, v10 == 14) )
    v11 = 1;
  VendorSpecific = RasAuthAttributeGetVendorSpecific(v9, 7, a2);
  if ( VendorSpecific )
  {
    v14 = *(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 9LL)
        + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 6LL) << 24)
        + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 8LL) << 8)
        + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 7LL) << 16);
    v69 = v14;
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
            LOBYTE(v67) = byte_18004CF34 & 1;
            if ( (byte_18004CF34 & 1) == 0 )
              goto LABEL_32;
            v17 = L"Strong encryption";
LABEL_31:
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, v17);
            goto LABEL_32;
          }
          if ( v8 )
          {
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasPppTraceInfo,
                L"Encryption policy not supported");
            return 741;
          }
          *(_DWORD *)(a1 + 184) |= 0x80000u;
          v16 = (byte_18004CF34 & 1) == 0;
          LOBYTE(v67) = byte_18004CF34 & 1;
LABEL_29:
          if ( v16 )
            goto LABEL_32;
          v17 = L"Encryption is not allowed";
          goto LABEL_31;
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v15 + 8) + 9LL) & 0xA) != 0 )
        {
          *(_DWORD *)(a1 + 184) |= 0x80u;
          LOBYTE(v67) = byte_18004CF34 & 1;
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, L"Encryption");
        }
        if ( (v8 & 4) != 0 )
        {
          *(_DWORD *)(a1 + 184) |= 0x1000u;
          LOBYTE(v67) = byte_18004CF34 & 1;
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceInfo,
              L"Strong encryption");
        }
        if ( !v8 )
        {
          *(_DWORD *)(a1 + 184) |= 0x80000u;
          v16 = (byte_18004CF34 & 1) == 0;
          LOBYTE(v67) = byte_18004CF34 & 1;
          goto LABEL_29;
        }
      }
      else if ( v14 == 1 && !v11 && !v8 )
      {
        *(_DWORD *)(a1 + 184) |= 0x80000u;
        v16 = (byte_18004CF34 & 1) == 0;
        LOBYTE(v67) = byte_18004CF34 & 1;
        goto LABEL_29;
      }
    }
  }
LABEL_32:
  v19 = *(_DWORD *)(a1 + 56);
  if ( (v19 & 0x200) != 0 )
  {
    v26 = (__int64 *)(a1 + 16);
    goto LABEL_51;
  }
  v21 = RasAuthAttributeGetVendorSpecific(v13, 12, a2);
  if ( !v21 )
  {
    v26 = (__int64 *)(a1 + 16);
    goto LABEL_44;
  }
  v22 = 0;
  v23 = *(_QWORD *)(a1 + 1472);
  v24 = *(_DWORD *)((-(__int64)(v68 != 0) & 0xFFFFFFFFFFFFFF38uLL) + v23 + 1420);
  if ( v24 == 49699 )
  {
    if ( v68 )
      v25 = *(unsigned __int8 **)(v23 + 1232);
    else
      v25 = *(unsigned __int8 **)(v23 + 1432);
    v22 = *v25;
  }
  v26 = (__int64 *)(a1 + 16);
  result = SetMsChapMppeKeys(*(_QWORD *)(a1 + 16), v21, a4, a5, v24, v22);
  if ( !(_DWORD)result )
  {
    LOBYTE(v67) = byte_18004CF34 & 1;
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"MS-CHAP-MPPE-Keys set");
    *(_DWORD *)(a1 + 56) |= 0x200u;
    v19 = *(_DWORD *)(a1 + 56);
LABEL_44:
    v27 = RasAuthAttributeGetVendorSpecific(v20, 16, a2);
    v29 = RasAuthAttributeGetVendorSpecific(v28, 17, a2);
    if ( v27 && v29 )
    {
      result = SetMsMppeSendRecvKeys(*v26, v27, v29);
      if ( (_DWORD)result )
        return result;
      LOBYTE(v67) = byte_18004CF34 & 1;
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"MPPE-Send/Recv-Keys set");
      *(_DWORD *)(a1 + 56) |= 0x200u;
      v19 = *(_DWORD *)(a1 + 56);
    }
LABEL_51:
    if ( (v19 & 0x200) == 0 )
      SetNoMppeKeys(*v26);
    v30 = v66;
    if ( v66 != 9 )
    {
      v35 = v68;
      if ( v66 == 14 )
      {
        *(_DWORD *)(a1 + 184) &= 0xFFFFEF7F;
        *(_DWORD *)(a1 + 184) |= 0x80000u;
      }
      goto LABEL_103;
    }
    v31 = *v26;
    v66 = 0;
    v67 = 4;
    v32 = ((__int64 (__fastcall *)(__int64, __int64, int *, int *))qword_18004C408)(v31, 7, &v66, &v67);
    if ( v32 )
    {
      if ( byte_18004CF33 < 0 )
      {
        LOWORD(v70) = 0;
        FormatRRASErrorString(&v70, L"RasGetPortUserData failed: 0x%x", v32);
        if ( byte_18004CF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v70);
      }
    }
    v33 = v69;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      LODWORD(v65) = v66;
      LOWORD(v70) = 0;
      FormatRRASErrorString(&v70, L"Checking encryption. Policy=0x%x,Types=0x%x,Mask=0x%x", v69, v8, v65);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v70);
    }
    v34 = v66;
    switch ( v66 )
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
    v34 = v66;
LABEL_78:
    v35 = v68;
    if ( !v68 )
    {
      if ( (*(_DWORD *)(a1 + 184) & 0x81080) == 0x1000 && v34 != 4 && v34 != 32 )
        return 742;
      *(_DWORD *)(a1 + 184) &= 0xFFFFEF7F;
LABEL_103:
      if ( g_dwAllowPPTPWeakCrypto == 1 && (*(_DWORD *)(a1 + 184) & 0x1080) != 0
        || !g_dwAllowPPTPWeakCrypto && (*(_DWORD *)(a1 + 184) & 0x1000) != 0 )
      {
        v44 = *(_DWORD *)(a1 + 56);
        if ( (v44 & 0x200) == 0 || (unsigned int)GetCpIndexFromProtocol(33021) == -1 )
        {
          *(_DWORD *)(a1 + 56) = v44 | 0x2000;
          return 741;
        }
      }
      if ( v35 )
      {
        v45 = RasAuthAttributeGet(7, a2);
        if ( v45 && *(_DWORD *)(v45 + 8) != 1 )
        {
          result = 794;
          goto LABEL_152;
        }
        v47 = RasAuthAttributeGet(64, v46);
        if ( v47
          && (v30 == 8 && *(_DWORD *)(v47 + 8) != 1
           || v30 == 9 && *(_DWORD *)(v47 + 8) != 3
           || v30 == 14 && *(_DWORD *)(v47 + 8) != 79617) )
        {
          *(_DWORD *)(a1 + 56) |= 0x2000u;
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceError,
              L"Tunnel type configuration mismatch, returning ERROR_WRONG_TUNNEL_TYPE");
          return 795;
        }
        v49 = RasAuthAttributeGet(8099, v48);
        if ( v49 )
          v51 = *(_DWORD *)(v49 + 8);
        else
          v51 = 0;
        *(_DWORD *)(a1 + 144) = v51;
        v52 = RasAuthAttributeGetVendorSpecific(v50, 10, a2);
        if ( v52 )
        {
          v53 = 15;
          if ( (unsigned int)(*(_DWORD *)(v52 + 4) - 7) < 0xF )
            v53 = *(_DWORD *)(v52 + 4) - 7;
          *(_OWORD *)(*(_QWORD *)(a1 + 8) + 473LL) = 0;
          memcpy_0((void *)(*(_QWORD *)(a1 + 8) + 473LL), (const void *)(*(_QWORD *)(v52 + 8) + 7LL), v53);
          if ( (byte_18004CF34 & 1) != 0 )
          {
            v54 = *(_QWORD *)(a1 + 8) + 473LL;
            LOWORD(v70) = 0;
            FormatRRASErrorString(&v70, L"Auth Attribute Domain = %hs", v54);
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v70);
          }
        }
        *(_DWORD *)(a1 + 112) = 1;
        *(_BYTE *)(a1 + 1536) = 0;
        v55 = RasAuthAttributeGet(6, a2);
        if ( v55 )
        {
          if ( *(_DWORD *)(v55 + 8) == 4 )
          {
            v57 = RasAuthAttributeGet(19, v56);
            v59 = v57;
            if ( v57 && *(_DWORD *)(v57 + 4) )
            {
              *(_DWORD *)(a1 + 112) = 2;
              memset_0((void *)(a1 + 1536), 0, (unsigned int)(v58 + 110));
              memcpy_0((void *)(a1 + 1536), *(const void **)(v59 + 8), *(unsigned int *)(v59 + 4));
              if ( (byte_18004CF34 & 1) != 0 )
              {
                LOWORD(v70) = 0;
                FormatRRASErrorString(&v70, L"Auth Attribute Forced callback to %hs", a1 + 1536);
                if ( (byte_18004CF34 & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v70);
              }
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) &= ~4u;
            }
            else
            {
              *(_DWORD *)(a1 + 112) = 5;
              if ( (byte_18004CF34 & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasPppTraceInfo,
                  L"Auth Attribute Caller Specifiable callback");
            }
          }
          else if ( *(_DWORD *)(v55 + 8) != 2 )
          {
            if ( (byte_18004CF34 & 1) != 0 )
            {
              LOWORD(v70) = 0;
              FormatRRASErrorString(&v70, L"Service Type %d is not of type Framed", *(unsigned int *)(v55 + 8));
              if ( (byte_18004CF34 & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v70);
            }
            result = 796;
            goto LABEL_152;
          }
        }
        if ( (*(_BYTE *)(a1 + 112) & 6) != 0 )
          *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 2u;
        v60 = RasAuthAttributeGet(28, a2);
        if ( v60 )
        {
          v61 = *(unsigned int *)(v60 + 8);
          *(_DWORD *)(a1 + 88) = v61;
        }
        else
        {
          *(_DWORD *)(a1 + 88) = dword_18004CA14;
          v61 = (unsigned int)dword_18004CA14;
        }
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v70) = 0;
          FormatRRASErrorString(&v70, L"Auth Attribute Idle Timeout Seconds = %d", v61);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v70);
        }
        v62 = RasAuthAttributeGet(62, a2);
        v63 = dword_18004CA0C;
        if ( v62 && *(_DWORD *)(v62 + 8) )
          v63 = *(_DWORD *)(v62 + 8);
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL) = v63;
        if ( (byte_18004CF34 & 1) != 0 )
        {
          v64 = *(_QWORD *)(a1 + 8);
          LOWORD(v70) = 0;
          FormatRRASErrorString(&v70, L"AuthAttribute MaxChannelsAllowed = %d", *(unsigned int *)(v64 + 24));
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v70);
        }
      }
      return 0;
    }
    if ( !v33 )
      goto LABEL_103;
    if ( !v34 )
    {
      if ( v33 != 2 || !v8 )
        goto LABEL_103;
LABEL_100:
      result = 742;
LABEL_152:
      *(_DWORD *)(a1 + 56) |= 0x2000u;
      return result;
    }
    v36 = v34 - 1;
    if ( !v36 )
      goto LABEL_97;
    v37 = v36 - 3;
    if ( v37 )
    {
      v38 = v37 - 12;
      if ( !v38 )
        goto LABEL_97;
      v39 = v38 - 16;
      if ( v39 )
      {
        v40 = v39 - 32;
        if ( v40 )
        {
          v41 = v40 - 64;
          if ( v41 )
          {
            v42 = v41 - 128;
            if ( v42 )
            {
              if ( v42 != 256 )
                goto LABEL_103;
              goto LABEL_94;
            }
          }
        }
LABEL_97:
        v43 = (v8 & 0xA) == 0;
LABEL_95:
        if ( !v43 )
          goto LABEL_103;
        goto LABEL_100;
      }
    }
LABEL_94:
    v43 = (v8 & 4) == 0;
    goto LABEL_95;
  }
  return result;
}

```

## disassembly

```asm
0x180003770  mov     [rsp-8+arg_10], rbx
0x180003775  push    rbp
0x180003776  push    rsi
0x180003777  push    rdi
0x180003778  push    r12
0x18000377a  push    r13
0x18000377c  push    r14
0x18000377e  push    r15
0x180003780  lea     rbp, [rsp-750h]
0x180003788  sub     rsp, 850h
0x18000378f  mov     rax, cs:__security_cookie
0x180003796  xor     rax, rsp
0x180003799  mov     [rbp+780h+var_40], rax
0x1800037a0  mov     r12, [rbp+780h+arg_20]
0x1800037a7  mov     r13, rdx
0x1800037aa  mov     [rsp+880h+var_848], r8d
0x1800037af  mov     rbx, rcx
0x1800037b2  xor     eax, eax
0x1800037b4  lea     rcx, [rsp+880h+var_83C]; void *
0x1800037b9  xor     esi, esi
0x1800037bb  mov     [rsp+880h+var_840], eax
0x1800037bf  xor     edx, edx; Val
0x1800037c1  mov     [rsp+880h+var_844], esi
0x1800037c5  mov     r8d, 7FCh; Size
0x1800037cb  mov     r14, r9
0x1800037ce  xor     r15d, r15d
0x1800037d1  call    memset_0
0x1800037d6  mov     rcx, rbx
0x1800037d9  call    CreateAccountingAttributes
0x1800037de  mov     eax, [rbx+3Ch]
0x1800037e1  movzx   eax, ax
0x1800037e4  mov     [rsp+880h+var_850], eax
0x1800037e8  cmp     eax, 9
0x1800037eb  jz      short loc_1800037F4
0x1800037ed  xor     edi, edi
0x1800037ef  cmp     eax, 0Eh
0x1800037f2  jnz     short loc_1800037F9
0x1800037f4  mov     edi, 1
0x1800037f9  mov     r8, r13
0x1800037fc  mov     edx, 7
0x180003801  call    RasAuthAttributeGetVendorSpecific
0x180003806  test    rax, rax
0x180003809  jz      loc_1800039CF
0x18000380f  mov     rdx, [rax+8]
0x180003813  mov     r8, r13
0x180003816  movzx   esi, byte ptr [rdx+7]
0x18000381a  movzx   eax, byte ptr [rdx+8]
0x18000381e  shl     eax, 8
0x180003821  shl     esi, 10h
0x180003824  add     esi, eax
0x180003826  movzx   eax, byte ptr [rdx+6]
0x18000382a  shl     eax, 18h
0x18000382d  add     esi, eax
0x18000382f  movzx   eax, byte ptr [rdx+9]
0x180003833  add     esi, eax
0x180003835  mov     edx, 8
0x18000383a  mov     [rsp+880h+var_844], esi
0x18000383e  call    RasAuthAttributeGetVendorSpecific
0x180003843  test    rax, rax
0x180003846  jz      loc_1800039CF
0x18000384c  mov     rdx, [rax+8]
0x180003850  movzx   r15d, byte ptr [rdx+7]
0x180003855  movzx   eax, byte ptr [rdx+8]
0x180003859  shl     eax, 8
0x18000385c  shl     r15d, 10h
0x180003860  add     r15d, eax
0x180003863  movzx   eax, byte ptr [rdx+6]
0x180003867  shl     eax, 18h
0x18000386a  add     r15d, eax
0x18000386d  movzx   eax, byte ptr [rdx+9]
0x180003871  add     r15d, eax
0x180003874  cmp     esi, 2
0x180003877  jnz     loc_180003990
0x18000387d  test    edi, edi
0x18000387f  jnz     loc_1800039CF
0x180003885  cmp     cs:g_dwAllowPPTPWeakCrypto, edi
0x18000388b  jz      loc_18000391F
0x180003891  test    r15b, 0Ah
0x180003895  jz      short loc_1800038C7
0x180003897  bts     dword ptr [rbx+0B8h], 7
0x18000389f  mov     al, cs:byte_18004CF34
0x1800038a5  and     al, 1
0x1800038a7  mov     byte ptr [rsp+880h+var_84C], al
0x1800038ab  jz      short loc_1800038C7
0x1800038ad  lea     r8, aEncryption; "Encryption"
0x1800038b4  lea     rdx, RasPppTraceInfo
0x1800038bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800038c2  call    McTemplateU0z_EventWriteTransfer
0x1800038c7  test    r15b, 4
0x1800038cb  jz      short loc_1800038FD
0x1800038cd  bts     dword ptr [rbx+0B8h], 0Ch
0x1800038d5  mov     al, cs:byte_18004CF34
0x1800038db  and     al, 1
0x1800038dd  mov     byte ptr [rsp+880h+var_84C], al
0x1800038e1  jz      short loc_1800038FD
0x1800038e3  lea     r8, aStrongEncrypti; "Strong encryption"
0x1800038ea  lea     rdx, RasPppTraceInfo
0x1800038f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800038f8  call    McTemplateU0z_EventWriteTransfer
0x1800038fd  test    r15d, r15d
0x180003900  jnz     loc_1800039CF
0x180003906  bts     dword ptr [rbx+0B8h], 13h
0x18000390e  mov     al, cs:byte_18004CF34
0x180003914  and     al, 1
0x180003916  mov     byte ptr [rsp+880h+var_84C], al
0x18000391a  jmp     loc_1800039B3
0x18000391f  test    r15b, 4
0x180003923  jz      short loc_180003948
0x180003925  bts     dword ptr [rbx+0B8h], 0Ch
0x18000392d  mov     al, cs:byte_18004CF34
0x180003933  and     al, 1
0x180003935  mov     byte ptr [rsp+880h+var_84C], al
0x180003939  jz      loc_1800039CF
0x18000393f  lea     r8, aStrongEncrypti; "Strong encryption"
0x180003946  jmp     short loc_1800039BC
0x180003948  test    r15d, r15d
0x18000394b  jnz     short loc_180003963
0x18000394d  bts     dword ptr [rbx+0B8h], 13h
0x180003955  mov     al, cs:byte_18004CF34
0x18000395b  and     al, 1
0x18000395d  mov     byte ptr [rsp+880h+var_84C], al
0x180003961  jmp     short loc_1800039B3
0x180003963  test    cs:byte_18004CF34, 1
0x18000396a  jz      short loc_180003986
0x18000396c  lea     r8, aEncryptionPoli; "Encryption policy not supported"
0x180003973  lea     rdx, RasPppTraceInfo
0x18000397a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003981  call    McTemplateU0z_EventWriteTransfer
0x180003986  mov     eax, 2E5h
0x18000398b  jmp     loc_180004103
0x180003990  cmp     esi, 1
0x180003993  jnz     short loc_1800039CF
0x180003995  test    edi, edi
0x180003997  jnz     short loc_1800039CF
0x180003999  test    r15d, r15d
0x18000399c  jnz     short loc_1800039CF
0x18000399e  bts     dword ptr [rbx+0B8h], 13h
0x1800039a6  mov     al, cs:byte_18004CF34
0x1800039ac  and     al, sil
0x1800039af  mov     byte ptr [rsp+880h+var_84C], al
0x1800039b3  jz      short loc_1800039CF
0x1800039b5  lea     r8, aEncryptionIsNo; "Encryption is not allowed"
0x1800039bc  lea     rdx, RasPppTraceInfo
0x1800039c3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800039ca  call    McTemplateU0z_EventWriteTransfer
0x1800039cf  mov     edi, [rbx+38h]
0x1800039d2  bt      edi, 9
0x1800039d6  jb      loc_180003B0C
0x1800039dc  mov     r8, r13
0x1800039df  mov     edx, 0Ch
0x1800039e4  call    RasAuthAttributeGetVendorSpecific
0x1800039e9  mov     r10, rax
0x1800039ec  test    rax, rax
0x1800039ef  jz      loc_180003A96
0x1800039f5  mov     r9d, [rsp+880h+var_848]
0x1800039fa  xor     r8d, r8d
0x1800039fd  mov     rax, [rbx+5C0h]
0x180003a04  mov     ecx, r9d
0x180003a07  neg     ecx
0x180003a09  sbb     rdx, rdx
0x180003a0c  and     rdx, 0FFFFFFFFFFFFFF38h
0x180003a13  mov     ecx, [rdx+rax+58Ch]
0x180003a1a  cmp     ecx, 0C223h
0x180003a20  jnz     short loc_180003A3B
0x180003a22  test    r9d, r9d
0x180003a25  jz      short loc_180003A30
0x180003a27  mov     rax, [rax+4D0h]
0x180003a2e  jmp     short loc_180003A37
0x180003a30  mov     rax, [rax+598h]
0x180003a37  movzx   r8d, byte ptr [rax]
0x180003a3b  mov     [rsp+880h+var_858], r8d
0x180003a40  lea     rsi, [rbx+10h]
0x180003a44  mov     dword ptr [rsp+880h+var_860], ecx
0x180003a48  mov     r9, r12
0x180003a4b  mov     rcx, [rsi]
0x180003a4e  mov     r8, r14
0x180003a51  mov     rdx, r10
0x180003a54  call    SetMsChapMppeKeys
0x180003a59  xor     r12d, r12d
0x180003a5c  test    eax, eax
0x180003a5e  jnz     loc_180004103
0x180003a64  mov     al, cs:byte_18004CF34
0x180003a6a  and     al, 1
0x180003a6c  mov     byte ptr [rsp+880h+var_84C], al
0x180003a70  jz      short loc_180003A8C
0x180003a72  lea     r8, aMsChapMppeKeys; "MS-CHAP-MPPE-Keys set"
0x180003a79  lea     rdx, RasPppTraceInfo
0x180003a80  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a87  call    McTemplateU0z_EventWriteTransfer
0x180003a8c  bts     dword ptr [rbx+38h], 9
0x180003a91  mov     edi, [rbx+38h]
0x180003a94  jmp     short loc_180003A9D
0x180003a96  lea     rsi, [rbx+10h]
0x180003a9a  xor     r12d, r12d
0x180003a9d  mov     r8, r13
0x180003aa0  mov     edx, 10h
0x180003aa5  call    RasAuthAttributeGetVendorSpecific
0x180003aaa  mov     r8, r13
0x180003aad  mov     edx, 11h
0x180003ab2  mov     r14, rax
0x180003ab5  call    RasAuthAttributeGetVendorSpecific
0x180003aba  test    r14, r14
0x180003abd  jz      short loc_180003B13
0x180003abf  test    rax, rax
0x180003ac2  jz      short loc_180003B13
0x180003ac4  mov     rcx, [rsi]
0x180003ac7  mov     r8, rax
0x180003aca  mov     rdx, r14
0x180003acd  call    SetMsMppeSendRecvKeys
0x180003ad2  test    eax, eax
0x180003ad4  jnz     loc_180004103
0x180003ada  mov     al, cs:byte_18004CF34
0x180003ae0  and     al, 1
0x180003ae2  mov     byte ptr [rsp+880h+var_84C], al
0x180003ae6  jz      short loc_180003B02
0x180003ae8  lea     r8, aMppeSendRecvKe; "MPPE-Send/Recv-Keys set"
0x180003aef  lea     rdx, RasPppTraceInfo
0x180003af6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003afd  call    McTemplateU0z_EventWriteTransfer
0x180003b02  bts     dword ptr [rbx+38h], 9
0x180003b07  mov     edi, [rbx+38h]
0x180003b0a  jmp     short loc_180003B13
0x180003b0c  lea     rsi, [rbx+10h]
0x180003b10  xor     r12d, r12d
0x180003b13  bt      edi, 9
0x180003b17  jb      short loc_180003B21
0x180003b19  mov     rcx, [rsi]
0x180003b1c  call    SetNoMppeKeys
0x180003b21  mov     r14d, [rsp+880h+var_850]
0x180003b26  cmp     r14d, 9
0x180003b2a  jnz     loc_180003D17
0x180003b30  mov     rcx, [rsi]
0x180003b33  lea     r9, [rsp+880h+var_84C]
0x180003b38  mov     rax, cs:qword_18004C408
0x180003b3f  lea     r8, [rsp+880h+var_850]
0x180003b44  lea     edx, [r14-2]
0x180003b48  mov     [rsp+880h+var_850], r12d
0x180003b4d  mov     [rsp+880h+var_84C], 4
0x180003b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5a  test    eax, eax
0x180003b5c  jz      short loc_180003BA2
0x180003b5e  cmp     cs:byte_18004CF33, r12b
0x180003b65  jge     short loc_180003BA2
0x180003b67  mov     r8d, eax
0x180003b6a  mov     word ptr [rsp+880h+var_840], r12w
0x180003b70  lea     rdx, aRasgetportuser; "RasGetPortUserData failed: 0x%x"
0x180003b77  lea     rcx, [rsp+880h+var_840]
0x180003b7c  call    FormatRRASErrorString
0x180003b81  cmp     cs:byte_18004CF33, r12b
0x180003b88  jge     short loc_180003BA2
0x180003b8a  lea     r8, [rsp+880h+var_840]
0x180003b8f  lea     rdx, RasPppTraceError
0x180003b96  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b9d  call    McTemplateU0z_EventWriteTransfer
0x180003ba2  test    cs:byte_18004CF34, 1
0x180003ba9  mov     edi, [rsp+880h+var_844]
0x180003bad  jz      short loc_180003BF5
0x180003baf  mov     eax, [rsp+880h+var_850]
0x180003bb3  lea     rdx, aCheckingEncryp; "Checking encryption. Policy=0x%x,Types="...
0x180003bba  mov     r9d, r15d
0x180003bbd  mov     dword ptr [rsp+880h+var_860], eax
0x180003bc1  mov     r8d, edi
0x180003bc4  mov     word ptr [rsp+880h+var_840], r12w
0x180003bca  lea     rcx, [rsp+880h+var_840]
0x180003bcf  call    FormatRRASErrorString
0x180003bd4  test    cs:byte_18004CF34, 1
0x180003bdb  jz      short loc_180003BF5
0x180003bdd  lea     r8, [rsp+880h+var_840]
0x180003be2  lea     rdx, RasPppTraceInfo
0x180003be9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003bf0  call    McTemplateU0z_EventWriteTransfer
0x180003bf5  mov     ecx, [rsp+880h+var_850]
0x180003bf9  mov     edx, 100h
0x180003bfe  cmp     ecx, 1
0x180003c01  jnz     short loc_180003C0E
0x180003c03  mov     rax, [rbx+8]
0x180003c07  bts     dword ptr [rax+34h], 0Bh
0x180003c0c  jmp     short loc_180003C81
0x180003c0e  cmp     ecx, 10h
0x180003c11  jnz     short loc_180003C1E
0x180003c13  mov     rax, [rbx+8]
0x180003c17  bts     dword ptr [rax+34h], 0Fh
0x180003c1c  jmp     short loc_180003C81
0x180003c1e  cmp     ecx, 4
0x180003c21  jnz     short loc_180003C2E
0x180003c23  mov     rax, [rbx+8]
0x180003c27  bts     dword ptr [rax+34h], 0Dh
0x180003c2c  jmp     short loc_180003C81
0x180003c2e  cmp     ecx, 20h ; ' '
0x180003c31  jnz     short loc_180003C3E
0x180003c33  mov     rax, [rbx+8]
0x180003c37  bts     dword ptr [rax+34h], 10h
0x180003c3c  jmp     short loc_180003C81
0x180003c3e  cmp     ecx, 40h ; '@'
0x180003c41  jnz     short loc_180003C4E
0x180003c43  mov     rax, [rbx+8]
0x180003c47  bts     dword ptr [rax+34h], 11h
0x180003c4c  jmp     short loc_180003C81
0x180003c4e  cmp     ecx, 80h
0x180003c54  jnz     short loc_180003C61
  ... truncated ...
```
