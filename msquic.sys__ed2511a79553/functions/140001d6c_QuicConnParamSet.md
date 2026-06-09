# QuicConnParamSet

- ea: `0x140001d6c`
- end: `0x140002830`
- name: `QuicConnParamSet`
- size: `2756`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140001b00`

## callees

- `0x140001860`
- `0x140001d6c`
- `0x140004460`
- `0x140005184`
- `0x140005aa4`
- `0x14000d490`
- `0x1400123b0`
- `0x14001cd20`
- `0x1400206e8`
- `0x1400228b8`
- `0x14002bfd8`
- `0x14002cb4c`
- `0x14002d09c`
- `0x14002efdc`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003fdf8`
- `0x14003fea4`
- `0x1400452d0`
- `0x140045e34`
- `0x1400465f4`
- `0x140046774`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140001f1d`
- `ntoskrnl!_snprintf_s` at `0x140001fed`
- `ntoskrnl!_snprintf_s` at `0x1400024a7`
- `ntoskrnl!_snprintf_s` at `0x1400024fb`
- `ntoskrnl!_snprintf_s` at `0x140002596`
- `ntoskrnl!_snprintf_s` at `0x1400026f9`
- `ntoskrnl!_snprintf_s` at `0x140001f1d`
- `ntoskrnl!_snprintf_s` at `0x140001fed`
- `ntoskrnl!_snprintf_s` at `0x1400024a7`
- `ntoskrnl!_snprintf_s` at `0x1400024fb`
- `ntoskrnl!_snprintf_s` at `0x140002596`
- `ntoskrnl!_snprintf_s` at `0x1400026f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002046`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002046`
- `ntoskrnl!ExAllocatePool2` at `0x14000205d`
- `ntoskrnl!ExAllocatePool2` at `0x14000205d`

## string_xrefs

- `0x1400020e6`: `Updated ShareBinding = %hhu`
- `0x140001fd9`: `Updated Stream Scheduling Scheme = %u`
- `0x140001f88`: `Updated datagram receive enabled to %hhu`
- `0x140001eff`: `Updated disable 1-RTT encrytption to %hhu`
- `0x140002583`: `Forcing key update`
- `0x1400025d0`: `Forced key update`
- `0x1400024e8`: `Forcing destination CID update`

## pseudocode

```c
__int64 __fastcall QuicConnParamSet(__int64 a1, unsigned int a2, unsigned int a3, _BYTE *a4)
{
  size_t v4; // r14
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  __int64 v17; // rcx
  int Binding; // ebx
  __int64 v19; // rdx
  unsigned __int8 v20; // cl
  const char *v21; // r9
  int v22; // eax
  __int64 v23; // rcx
  char v24; // cl
  char v25; // al
  unsigned __int8 v26; // cl
  int v27; // edx
  __int64 v28; // rcx
  __int64 *v29; // rdx
  void *v30; // rcx
  void *Pool2; // rax
  unsigned __int8 v32; // cl
  __int64 v33; // rdx
  char v34; // dl
  int v35; // r9d
  unsigned int v36; // eax
  int v37; // ecx
  char *v38; // r14
  __int64 v39; // rcx
  bool v40; // zf
  int v41; // eax
  bool v42; // sf
  char v43; // cl
  __int64 v44; // rdx
  int v45; // ecx
  int v46; // r9d
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  int v52; // ecx
  int v53; // ecx
  __int64 result; // rax
  __int64 v55; // rcx
  __int64 v56; // rdx
  int v57; // ecx
  _BYTE v58[144]; // [rsp+40h] [rbp-C0h] BYREF
  char DstBuf[128]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = a3;
  memset(v58, 0, sizeof(v58));
  if ( a2 <= 0x5000011 )
  {
    if ( a2 == 83886097 )
    {
      if ( (_DWORD)v4 != 1 || !a4 )
        return (unsigned int)-1073741811;
      LOBYTE(v8) = *a4;
      QuicCryptoCustomCertValidationComplete(a1 + 2784, v8, 42);
    }
    else
    {
      v9 = a2 - 83886081;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 2;
          if ( !v11 )
          {
            if ( a4 )
            {
              Binding = QuicSettingsSettingsToInternal((unsigned int)v4, a4, v58);
              if ( Binding < 0 )
                return (unsigned int)Binding;
              LOBYTE(v33) = 1;
              if ( (unsigned __int8)QuicConnApplyNewSettings(a1, v33, v58) )
                return (unsigned int)Binding;
            }
            return (unsigned int)-1073741811;
          }
          v12 = v11 - 3;
          if ( v12 )
          {
            v13 = v12 - 4;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  v16 = v15 - 2;
                  if ( v16 )
                  {
                    if ( v16 == 1 && (_DWORD)v4 && a4 )
                    {
                      if ( !(unsigned __int8)QuicConnIsServer(a1) && (*(_BYTE *)(a1 + 248) & 0x14) == 0 )
                      {
                        Binding = QuicCryptoDecodeClientTicket(
                                    v17,
                                    v4,
                                    (__int64)a4,
                                    (char *)(a1 + 1624),
                                    (_QWORD *)(a1 + 3400),
                                    (_DWORD *)(a1 + 3408),
                                    (_DWORD *)(a1 + 3636));
                        if ( Binding >= 0 )
                        {
                          QuicConnOnQuicVersionSet(a1);
                          LOBYTE(v19) = 1;
                          return (unsigned int)QuicConnProcessPeerTransportParameters(a1, v19);
                        }
                        return (unsigned int)Binding;
                      }
                      return (unsigned int)-1073741436;
                    }
                    return (unsigned int)-1073741811;
                  }
                  if ( (_DWORD)v4 == 1 )
                  {
                    if ( (*(_BYTE *)(a1 + 248) & 0x14) == 0
                      && ((*(_BYTE *)(a1 + 250) & 0x20) == 0 || (*(_DWORD *)(a1 + 1624) & 0x40000) != 0) )
                    {
                      Binding = 0;
                      v20 = *(_BYTE *)(a1 + 249) ^ (*(_BYTE *)(a1 + 249) ^ (16 * *a4)) & 0x10;
                      *(_BYTE *)(a1 + 249) = v20;
                      if ( (byte_14005C48C & 1) == 0 )
                        return (unsigned int)Binding;
                      v21 = "Updated disable 1-RTT encrytption to %hhu";
                      v22 = v20 >> 4;
LABEL_24:
                      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v21, v22 & 1);
                      McTemplateU0ps_EtwWriteTransfer(v23, QuicConnLogVerbose, a1, DstBuf);
                      return (unsigned int)Binding;
                    }
                    return (unsigned int)-1073741436;
                  }
                }
                else if ( (_DWORD)v4 == 1 )
                {
                  if ( (*(_BYTE *)(a1 + 248) & 0x14) == 0 )
                  {
                    v24 = *a4;
                    Binding = 0;
                    v25 = *(_BYTE *)(a1 + 235);
                    *(_QWORD *)(a1 + 96) |= 0x10000000uLL;
                    v26 = v25 ^ (v25 ^ (8 * v24)) & 8;
                    *(_BYTE *)(a1 + 235) = v26;
                    if ( (byte_14005C48C & 1) == 0 )
                      return (unsigned int)Binding;
                    v21 = "Updated datagram receive enabled to %hhu";
                    v22 = v26 >> 3;
                    goto LABEL_24;
                  }
                  return (unsigned int)-1073741436;
                }
                return (unsigned int)-1073741811;
              }
              if ( (_DWORD)v4 != 4 )
                return (unsigned int)-1073741811;
              v27 = *(_DWORD *)a4;
              if ( *(int *)a4 >= 2 )
                return (unsigned int)-1073741811;
              *(_BYTE *)(a1 + 251) = *(_BYTE *)(a1 + 251) & 0xF7 | (v27 != 1 ? 0 : 8);
              if ( byte_14005C48B < 0 )
              {
                _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Updated Stream Scheduling Scheme = %u", v27);
LABEL_33:
                v29 = QuicConnLogInfo;
LABEL_34:
                McTemplateU0ps_EtwWriteTransfer(v28, v29, a1, DstBuf);
              }
            }
            else
            {
              if ( (unsigned int)v4 > 0x200 || a4 && a4[(unsigned int)(v4 - 1)] )
                return (unsigned int)-1073741811;
              v30 = *(void **)(a1 + 1600);
              if ( v30 )
                ExFreePoolWithTag(v30, 0x35336351u);
              Pool2 = (void *)ExAllocatePool2(66, v4, 892560209);
              *(_QWORD *)(a1 + 1600) = Pool2;
              if ( !a4 || !Pool2 )
                return (unsigned int)-1073741801;
              memmove(Pool2, a4, v4);
            }
          }
          else
          {
            if ( (_DWORD)v4 != 1 )
              return (unsigned int)-1073741811;
            if ( (*(_BYTE *)(a1 + 248) & 0x14) != 0 || (unsigned __int8)QuicConnIsServer(a1) )
              return (unsigned int)-1073741436;
            v32 = *(_BYTE *)(a1 + 251) ^ (*(_BYTE *)(a1 + 251) ^ (2 * *a4)) & 2;
            *(_BYTE *)(a1 + 251) = v32;
            if ( byte_14005C48B < 0 )
            {
              _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Updated ShareBinding = %hhu", (v32 >> 1) & 1);
              goto LABEL_33;
            }
          }
        }
        else
        {
          if ( (*(_BYTE *)(a1 + 248) & 0x14) != 0 )
            return (unsigned int)-1073741436;
          if ( (_DWORD)v4 != 28 || (unsigned __int8)QuicAddrIsWildCard(a4) || (unsigned __int8)QuicConnIsServer(a1) )
            return (unsigned int)-1073741811;
          *(_BYTE *)(a1 + 250) |= 0x10u;
          *(_OWORD *)(a1 + 376) = *(_OWORD *)a4;
          *(_QWORD *)(a1 + 392) = *((_QWORD *)a4 + 2);
          *(_DWORD *)(a1 + 400) = *((_DWORD *)a4 + 6);
        }
      }
      else
      {
        if ( (_DWORD)v4 != 28 )
          return (unsigned int)-1073741811;
        if ( (*(_BYTE *)(a1 + 248) & 0x10) != 0
          || (unsigned __int8)QuicConnIsServer(a1)
          || (v34 & 4) != 0 && (*(_BYTE *)(a1 + 250) & 2) == 0 )
        {
          return (unsigned int)-1073741436;
        }
        v36 = *(unsigned __int16 *)a4;
        if ( v36 > 0x17 )
          return (unsigned int)-1073741811;
        v37 = 8388613;
        if ( !_bittest(&v37, v36) )
          return (unsigned int)-1073741811;
        *(_BYTE *)(a1 + 250) |= 8u;
        *(_OWORD *)(a1 + 404) = *(_OWORD *)a4;
        *(_QWORD *)(a1 + 420) = *((_QWORD *)a4 + 2);
        *(_DWORD *)(a1 + 428) = *((_DWORD *)a4 + 6);
        if ( (byte_14005C489 & 0x40) != 0 )
        {
          LOBYTE(v35) = 28;
          McTemplateU0pubr1_EtwWriteTransfer(a1 + 404, (unsigned int)QuicConnLocalAddrAdded, a1, v35, a1 + 404);
        }
        if ( (*(_BYTE *)(a1 + 248) & 4) != 0 )
        {
          v38 = *(char **)(a1 + 360);
          memset(DstBuf, 0, 0x48u);
          *(_DWORD *)&DstBuf[16] = 0;
          *(_DWORD *)&DstBuf[20] = 0;
          v39 = *(_QWORD *)(a1 + 88);
          v40 = (*(_BYTE *)(a1 + 251) & 2) == 0;
          *(_QWORD *)&DstBuf[8] = a1 + 376;
          *(_QWORD *)DstBuf = a4;
          *(_DWORD *)&DstBuf[40] = *(_DWORD *)(v39 + 56);
          *(_QWORD *)&DstBuf[48] = *(_QWORD *)(v39 + 80);
          v41 = 0;
          if ( !v40 )
            v41 = 2;
          v42 = *(char *)(a1 + 236) < 0;
          *(_DWORD *)&DstBuf[16] = v41;
          if ( v42 )
          {
            v41 |= 8u;
            *(_DWORD *)&DstBuf[16] = v41;
          }
          v43 = *(_BYTE *)(a1 + 237);
          if ( (v43 & 1) != 0 )
          {
            v41 |= 0x10u;
            *(_DWORD *)&DstBuf[16] = v41;
          }
          if ( (v43 & 2) != 0 )
            *(_DWORD *)&DstBuf[16] = v41 | 0x20;
          Binding = QuicLibraryGetBinding(DstBuf, a1 + 360);
          if ( Binding < 0 )
          {
            *(_QWORD *)(a1 + 360) = v38;
            return (unsigned int)Binding;
          }
          v44 = *(_QWORD *)(a1 + 360);
          *(_DWORD *)(a1 + 448) = 0;
          *(_QWORD *)(a1 + 368) = 0;
          QuicLookupMoveLocalConnectionIDs(v38 + 64, v44 + 64, a1);
          QuicLibraryReleaseBinding(v38);
          if ( (byte_14005C489 & 0x40) != 0 )
          {
            LOBYTE(v46) = 28;
            McTemplateU0pubr1_EtwWriteTransfer(v45, (unsigned int)QuicConnLocalAddrRemoved, a1, v46, a1 + 404);
          }
          v47 = *(_QWORD *)(*(_QWORD *)(a1 + 360) + 32LL);
          *(_OWORD *)(a1 + 404) = *(_OWORD *)v47;
          *(_QWORD *)(a1 + 420) = *(_QWORD *)(v47 + 16);
          *(_DWORD *)(a1 + 428) = *(_DWORD *)(v47 + 24);
          if ( (byte_14005C489 & 0x40) != 0 )
          {
            LOBYTE(v46) = 28;
            McTemplateU0pubr1_EtwWriteTransfer(v45, (unsigned int)QuicConnLocalAddrAdded, a1, v46, a1 + 404);
          }
          QuicSendSetSendFlag(a1 + 3416, 4096);
        }
      }
    }
    return 0;
  }
  switch ( a2 )
  {
    case 0x5000012u:
      if ( (_DWORD)v4 != 4 )
        return (unsigned int)-1073741811;
      if ( (unsigned __int8)QuicConnIsServer(a1) || (*(_BYTE *)(a1 + 248) & 0x14) != 0 )
        return (unsigned int)-1073741436;
      *(_BYTE *)(a1 + 252) |= 1u;
      v57 = *(_DWORD *)a4;
      *(_DWORD *)(a1 + 428) = *(_DWORD *)a4;
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Local interface set to %u", v57);
        goto LABEL_33;
      }
      return 0;
    case 0x5000013u:
      if ( (_DWORD)v4 != 354 || !a4 )
        return (unsigned int)-1073741811;
      if ( (*(_BYTE *)(a1 + 248) & 0x14) != 0 )
        return (unsigned int)-1073741436;
      *(_QWORD *)(a1 + 3872) = a4;
      memset(a4, 0, 0x162u);
      return 0;
    case 0x5000014u:
      if ( a4 )
      {
        Binding = QuicSettingsVersionSettingsToInternal((unsigned int)v4, a4, v58);
        if ( Binding < 0 )
          return (unsigned int)Binding;
        LOBYTE(v56) = 1;
        if ( (unsigned __int8)QuicConnApplyNewSettings(a1, v56, v58) )
        {
          QuicSettingsCleanup(v58);
          return (unsigned int)Binding;
        }
        QuicSettingsCleanup(v58);
      }
      return (unsigned int)-1073741811;
  }
  if ( a2 != 83886101 )
  {
    switch ( a2 )
    {
      case 0x5000019u:
        if ( (_DWORD)v4 != 1 )
          return (unsigned int)-1073741811;
        if ( !a4 )
          return (unsigned int)-1073741811;
        v53 = (unsigned __int8)*a4;
        if ( (unsigned __int8)v53 > 0x3Fu )
          return (unsigned int)-1073741811;
        *(_BYTE *)(a1 + 284) = v53;
        if ( byte_14005C48B < 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Connection DSCP set to %hhu", v53);
          goto LABEL_33;
        }
        break;
      case 0x85000000:
        if ( (*(_BYTE *)(a1 + 248) & 8) == 0 )
          return (unsigned int)-1073741436;
        v49 = *(_QWORD *)(a1 + 2776);
        if ( !v49 || (*(_BYTE *)(v49 + 424) & 2) != 0 || (*(_BYTE *)(a1 + 250) & 2) == 0 )
          return (unsigned int)-1073741436;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Forcing key update");
          McTemplateU0ps_EtwWriteTransfer(v50, QuicConnLogVerbose, a1, DstBuf);
        }
        Binding = QuicCryptoGenerateNewKeys(a1);
        if ( Binding < 0 )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              v52,
              (unsigned int)QuicConnErrorStatus,
              a1,
              Binding,
              (__int64)"Forced key update");
          return (unsigned int)Binding;
        }
        LOBYTE(v51) = 1;
        QuicCryptoUpdateKeyPhase(a1, v51);
        break;
      case 0x85000001:
        if ( (*(_BYTE *)(a1 + 248) & 8) == 0 || (*(_BYTE *)(a1 + 250) & 2) == 0 )
          return (unsigned int)-1073741436;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Forcing destination CID update");
          McTemplateU0ps_EtwWriteTransfer(v48, QuicConnLogVerbose, a1, DstBuf);
        }
        if ( !(unsigned __int8)QuicConnRetireCurrentDestCid(a1, a1 + 320) )
          return (unsigned int)-1073741436;
        *(_BYTE *)(a1 + 321) |= 4u;
        break;
      case 0x85000002:
        if ( (_DWORD)v4 != 16 )
          return (unsigned int)-1073741811;
        if ( (*(_BYTE *)(a1 + 248) & 0x14) != 0 )
          return (unsigned int)-1073741436;
        memmove((void *)(a1 + 3856), a4, v4);
        *(_BYTE *)(a1 + 251) |= 4u;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Setting Test Transport Parameter (type %x, %hu bytes)",
            *(_DWORD *)(a1 + 3856),
            *(unsigned __int16 *)(a1 + 3860));
          v29 = QuicConnLogVerbose;
          goto LABEL_34;
        }
        break;
      default:
        if ( a2 != -2063597565 || (_DWORD)v4 != 2 )
          return (unsigned int)-1073741811;
        *(_WORD *)(a1 + 3888) = *(_WORD *)a4;
        break;
    }
    return 0;
  }
  if ( (unsigned __int8)QuicConnIsServer(a1) || (*(_BYTE *)(a1 + 248) & 0x14) != 0 || (*(_BYTE *)(a1 + 251) & 2) == 0 )
    return 3221225860LL;
  if ( (unsigned int)v4 > 7 )
    return 3221225485LL;
  if ( !(_DWORD)v4 )
  {
    result = 0;
    *(_QWORD *)(a1 + 1312) = 0;
    return result;
  }
  if ( (unsigned int)v4 < 2 )
    return 3221225485LL;
  if ( *a4 )
    return 3221225659LL;
  *(_BYTE *)(a1 + 1312) = v4 - 1;
  memmove((void *)(a1 + 1313), a4, v4);
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "CIBIR ID set (len %hhu, offset %hhu)",
      *(unsigned __int8 *)(a1 + 1312),
      *(unsigned __int8 *)(a1 + 1313));
    McTemplateU0ps_EtwWriteTransfer(v55, QuicConnLogInfo, a1, DstBuf);
  }
  return 0;
}

```

## disassembly

```asm
0x140001d6c  mov     [rsp-8+arg_8], rbx
0x140001d71  push    rbp
0x140001d72  push    rsi
0x140001d73  push    rdi
0x140001d74  push    r14
0x140001d76  push    r15
0x140001d78  lea     rbp, [rsp-60h]
0x140001d7d  sub     rsp, 160h
0x140001d84  mov     rax, cs:__security_cookie
0x140001d8b  xor     rax, rsp
0x140001d8e  mov     [rbp+80h+var_30], rax
0x140001d92  mov     r14d, r8d
0x140001d95  mov     ebx, edx
0x140001d97  mov     rdi, rcx
0x140001d9a  xor     edx, edx; Val
0x140001d9c  mov     r8d, 90h; Size
0x140001da2  lea     rcx, [rsp+180h+var_140]; void *
0x140001da7  mov     rsi, r9
0x140001daa  call    memset
0x140001daf  mov     eax, 5000011h
0x140001db4  cmp     ebx, eax
0x140001db6  ja      loc_1400023BD
0x140001dbc  jz      loc_140002396
0x140001dc2  sub     ebx, 5000001h
0x140001dc8  jz      loc_14000218E
0x140001dce  sub     ebx, 1
0x140001dd1  jz      loc_140002137
0x140001dd7  mov     r15d, 2
0x140001ddd  sub     ebx, r15d
0x140001de0  jz      loc_1400020FB
0x140001de6  sub     ebx, 3
0x140001de9  jz      loc_140002097
0x140001def  sub     ebx, 4
0x140001df2  jz      loc_140002011
0x140001df8  sub     ebx, 1
0x140001dfb  jz      loc_140001F97
0x140001e01  sub     ebx, 1
0x140001e04  jz      loc_140001F41
0x140001e0a  sub     ebx, r15d
0x140001e0d  jz      loc_140001EA5
0x140001e13  cmp     ebx, 1
0x140001e16  jnz     loc_140002194
0x140001e1c  test    r14d, r14d
0x140001e1f  jz      loc_140002194
0x140001e25  test    rsi, rsi
0x140001e28  jz      loc_140002194
0x140001e2e  mov     rcx, rdi
0x140001e31  call    QuicConnIsServer
0x140001e36  test    al, al
0x140001e38  jnz     loc_140002805
0x140001e3e  test    byte ptr [rdi+0F8h], 14h
0x140001e45  jnz     loc_140002805
0x140001e4b  lea     rax, [rdi+0E34h]
0x140001e52  mov     r8, rsi
0x140001e55  mov     [rsp+180h+var_150], rax; __int64
0x140001e5a  lea     r10, [rdi+0D50h]
0x140001e61  lea     r11, [rdi+0D48h]
0x140001e68  mov     [rsp+180h+var_158], r10; __int64
0x140001e6d  lea     r9, [rdi+658h]
0x140001e74  mov     [rsp+180h+var_160], r11; __int64
0x140001e79  movzx   edx, r14w
0x140001e7d  call    QuicCryptoDecodeClientTicket
0x140001e82  mov     ebx, eax
0x140001e84  test    eax, eax
0x140001e86  js      loc_14000280A
0x140001e8c  mov     rcx, rdi
0x140001e8f  call    QuicConnOnQuicVersionSet
0x140001e94  mov     dl, 1
0x140001e96  mov     rcx, rdi
0x140001e99  call    QuicConnProcessPeerTransportParameters
0x140001e9e  mov     ebx, eax
0x140001ea0  jmp     loc_14000280A
0x140001ea5  cmp     r14d, 1
0x140001ea9  jnz     loc_140002194
0x140001eaf  test    byte ptr [rdi+0F8h], 14h
0x140001eb6  jnz     loc_140002805
0x140001ebc  test    byte ptr [rdi+0FAh], 20h
0x140001ec3  jz      short loc_140001ED5
0x140001ec5  test    dword ptr [rdi+658h], 40000h
0x140001ecf  jz      loc_140002805
0x140001ed5  mov     al, [rdi+0F9h]
0x140001edb  xor     ebx, ebx
0x140001edd  mov     cl, [rsi]
0x140001edf  shl     cl, 4
0x140001ee2  xor     cl, al
0x140001ee4  and     cl, 10h
0x140001ee7  xor     cl, al
0x140001ee9  mov     [rdi+0F9h], cl
0x140001eef  test    cs:byte_14005C48C, 1
0x140001ef6  jz      loc_14000280A
0x140001efc  movzx   eax, cl
0x140001eff  lea     r9, aUpdatedDisable; "Updated disable 1-RTT encrytption to %h"...
0x140001f06  shr     eax, 4
0x140001f09  and     eax, 1
0x140001f0c  lea     rcx, [rbp+80h+DstBuf]; DstBuf
0x140001f10  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140001f14  mov     dword ptr [rsp+180h+var_160], eax
0x140001f18  mov     edx, 80h; SizeInBytes
0x140001f1d  call    cs:__imp__snprintf_s
0x140001f24  nop     dword ptr [rax+rax+00h]
0x140001f29  lea     r9, [rbp+80h+DstBuf]
0x140001f2d  mov     r8, rdi
0x140001f30  lea     rdx, QuicConnLogVerbose
0x140001f37  call    McTemplateU0ps_EtwWriteTransfer
0x140001f3c  jmp     loc_14000280A
0x140001f41  cmp     r14d, 1
0x140001f45  jnz     loc_140002194
0x140001f4b  test    byte ptr [rdi+0F8h], 14h
0x140001f52  jnz     loc_140002805
0x140001f58  mov     cl, [rsi]
0x140001f5a  xor     ebx, ebx
0x140001f5c  mov     al, [rdi+0EBh]
0x140001f62  bts     qword ptr [rdi+60h], 1Ch
0x140001f68  shl     cl, 3
0x140001f6b  xor     cl, al
0x140001f6d  and     cl, 8
0x140001f70  xor     cl, al
0x140001f72  mov     [rdi+0EBh], cl
0x140001f78  test    cs:byte_14005C48C, r14b
0x140001f7f  jz      loc_14000280A
0x140001f85  movzx   eax, cl
0x140001f88  lea     r9, aUpdatedDatagra; "Updated datagram receive enabled to %hh"...
0x140001f8f  shr     eax, 3
0x140001f92  jmp     loc_140001F09
0x140001f97  cmp     r14d, 4
0x140001f9b  jnz     loc_140002194
0x140001fa1  mov     edx, [rsi]
0x140001fa3  cmp     edx, r15d
0x140001fa6  jge     loc_140002194
0x140001fac  mov     al, [rdi+0FBh]
0x140001fb2  cmp     edx, 1
0x140001fb5  setnz   cl
0x140001fb8  and     al, 0F7h
0x140001fba  dec     cl
0x140001fbc  and     cl, 8
0x140001fbf  or      cl, al
0x140001fc1  mov     [rdi+0FBh], cl
0x140001fc7  mov     al, cs:byte_14005C48B
0x140001fcd  test    al, al
0x140001fcf  jns     loc_14000238F
0x140001fd5  mov     dword ptr [rsp+180h+var_160], edx
0x140001fd9  lea     r9, aUpdatedStreamS; "Updated Stream Scheduling Scheme = %u"
0x140001fe0  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140001fe4  lea     rcx, [rbp+80h+DstBuf]; DstBuf
0x140001fe8  mov     edx, 80h; SizeInBytes
0x140001fed  call    cs:__imp__snprintf_s
0x140001ff4  nop     dword ptr [rax+rax+00h]
0x140001ff9  lea     rdx, QuicConnLogInfo
0x140002000  mov     r8, rdi
0x140002003  lea     r9, [rbp+80h+DstBuf]
0x140002007  call    McTemplateU0ps_EtwWriteTransfer
0x14000200c  jmp     loc_14000238F
0x140002011  cmp     r14d, 200h
0x140002018  ja      loc_140002194
0x14000201e  test    rsi, rsi
0x140002021  jz      short loc_140002031
0x140002023  lea     eax, [r14-1]
0x140002027  cmp     byte ptr [rax+rsi], 0
0x14000202b  jnz     loc_140002194
0x140002031  mov     rcx, [rdi+640h]; P
0x140002038  mov     r15d, 35336351h
0x14000203e  test    rcx, rcx
0x140002041  jz      short loc_140002052
0x140002043  mov     edx, r15d; Tag
0x140002046  call    cs:__imp_ExFreePoolWithTag
0x14000204d  nop     dword ptr [rax+rax+00h]
0x140002052  mov     r8d, r15d
0x140002055  mov     rdx, r14
0x140002058  mov     ecx, 42h ; 'B'
0x14000205d  call    cs:__imp_ExAllocatePool2
0x140002064  nop     dword ptr [rax+rax+00h]
0x140002069  mov     [rdi+640h], rax
0x140002070  test    rsi, rsi
0x140002073  jz      short loc_14000208D
0x140002075  test    rax, rax
0x140002078  jz      short loc_14000208D
0x14000207a  mov     r8, r14; Size
0x14000207d  mov     rdx, rsi; Src
0x140002080  mov     rcx, rax; void *
0x140002083  call    memmove
0x140002088  jmp     loc_14000238F
0x14000208d  mov     ebx, 0C0000017h
0x140002092  jmp     loc_14000280A
0x140002097  cmp     r14d, 1
0x14000209b  jnz     loc_140002194
0x1400020a1  test    byte ptr [rdi+0F8h], 14h
0x1400020a8  jnz     loc_140002805
0x1400020ae  mov     rcx, rdi
0x1400020b1  call    QuicConnIsServer
0x1400020b6  test    al, al
0x1400020b8  jnz     loc_140002805
0x1400020be  mov     al, [rdi+0FBh]
0x1400020c4  mov     cl, [rsi]
0x1400020c6  add     cl, cl
0x1400020c8  xor     cl, al
0x1400020ca  and     cl, r15b
0x1400020cd  xor     cl, al
0x1400020cf  mov     [rdi+0FBh], cl
0x1400020d5  mov     al, cs:byte_14005C48B
0x1400020db  test    al, al
0x1400020dd  jns     loc_14000238F
0x1400020e3  movzx   eax, cl
0x1400020e6  lea     r9, aUpdatedSharebi; "Updated ShareBinding = %hhu"
0x1400020ed  shr     eax, 1
0x1400020ef  and     eax, r14d
0x1400020f2  mov     dword ptr [rsp+180h+var_160], eax
0x1400020f6  jmp     loc_140001FE0
0x1400020fb  test    rsi, rsi
0x1400020fe  jz      loc_140002194
0x140002104  lea     r8, [rsp+180h+var_140]
0x140002109  mov     rdx, rsi
0x14000210c  mov     ecx, r14d
0x14000210f  call    QuicSettingsSettingsToInternal
0x140002114  mov     ebx, eax
0x140002116  test    eax, eax
0x140002118  js      loc_14000280A
0x14000211e  lea     r8, [rsp+180h+var_140]
0x140002123  mov     dl, 1
0x140002125  mov     rcx, rdi
0x140002128  call    QuicConnApplyNewSettings
0x14000212d  test    al, al
0x14000212f  jnz     loc_14000280A
0x140002135  jmp     short loc_140002194
0x140002137  test    byte ptr [rdi+0F8h], 14h
0x14000213e  jnz     loc_140002805
0x140002144  cmp     r14d, 1Ch
0x140002148  jnz     short loc_140002194
0x14000214a  mov     rcx, rsi
0x14000214d  call    QuicAddrIsWildCard
0x140002152  test    al, al
0x140002154  jnz     short loc_140002194
0x140002156  mov     rcx, rdi
0x140002159  call    QuicConnIsServer
0x14000215e  test    al, al
0x140002160  jnz     short loc_140002194
0x140002162  or      byte ptr [rdi+0FAh], 10h
0x140002169  movups  xmm0, xmmword ptr [rsi]
0x14000216c  movups  xmmword ptr [rdi+178h], xmm0
0x140002173  movsd   xmm1, qword ptr [rsi+10h]
0x140002178  movsd   qword ptr [rdi+188h], xmm1
0x140002180  mov     eax, [rsi+18h]
0x140002183  mov     [rdi+190h], eax
0x140002189  jmp     loc_14000238F
0x14000218e  cmp     r14d, 1Ch
0x140002192  jz      short loc_14000219E
0x140002194  mov     ebx, 0C000000Dh
0x140002199  jmp     loc_14000280A
0x14000219e  mov     dl, [rdi+0F8h]
0x1400021a4  test    dl, 10h
0x1400021a7  jnz     loc_140002805
0x1400021ad  mov     rcx, rdi
0x1400021b0  call    QuicConnIsServer
0x1400021b5  test    al, al
0x1400021b7  jnz     loc_140002805
0x1400021bd  mov     r15d, 2
0x1400021c3  test    dl, 4
0x1400021c6  jz      short loc_1400021D5
0x1400021c8  test    [rdi+0FAh], r15b
0x1400021cf  jz      loc_140002805
0x1400021d5  movzx   eax, word ptr [rsi]
0x1400021d8  cmp     eax, 17h
0x1400021db  ja      short loc_140002194
0x1400021dd  mov     ecx, 800005h
0x1400021e2  bt      ecx, eax
0x1400021e5  jnb     short loc_140002194
0x1400021e7  or      byte ptr [rdi+0FAh], 8
0x1400021ee  lea     rcx, [rdi+194h]
0x1400021f5  movups  xmm0, xmmword ptr [rsi]
0x1400021f8  movups  xmmword ptr [rcx], xmm0
0x1400021fb  movsd   xmm1, qword ptr [rsi+10h]
0x140002200  movsd   qword ptr [rcx+10h], xmm1
0x140002205  mov     eax, [rsi+18h]
0x140002208  mov     [rcx+18h], eax
0x14000220b  test    cs:byte_14005C489, 40h
0x140002212  jz      short loc_14000222B
0x140002214  mov     r9b, 1Ch
0x140002217  mov     [rsp+180h+var_160], rcx
0x14000221c  mov     r8, rdi
0x14000221f  lea     rdx, QuicConnLocalAddrAdded
0x140002226  call    McTemplateU0pubr1_EtwWriteTransfer
0x14000222b  test    byte ptr [rdi+0F8h], 4
0x140002232  jz      loc_14000238F
0x140002238  mov     r14, [rdi+168h]
0x14000223f  lea     rcx, [rbp+80h+DstBuf]; void *
0x140002243  xor     edx, edx; Val
0x140002245  lea     r8d, [rdx+48h]; Size
0x140002249  call    memset
0x14000224e  and     [rbp+80h+var_A0], 0
0x140002252  lea     rax, [rdi+178h]
0x140002259  and     [rbp+80h+var_9C], 0
0x14000225d  mov     rcx, [rdi+58h]
0x140002261  test    [rdi+0FBh], r15b
0x140002268  mov     [rbp+80h+var_A8], rax
0x14000226c  mov     qword ptr [rbp+80h+DstBuf], rsi
0x140002270  mov     eax, [rcx+38h]
0x140002273  mov     [rbp+80h+var_88], eax
0x140002276  mov     rax, [rcx+50h]
0x14000227a  mov     [rbp+80h+var_80], rax
0x14000227e  mov     eax, 0
0x140002283  cmovnz  eax, r15d
  ... truncated ...
```
