# _LoadInterface

- ea: `0x18003b348`
- end: `0x18003baf5`
- name: `_LoadInterface`
- size: `1965`
- prototype: `__int64 __fastcall(__int64, int *, int, _WORD **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003af6c`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003b348`
- `0x180074fb0`
- `0x18009f6d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18003b91c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003b91c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b844`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b85d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b844`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b85d`
- `ntoskrnl!IofCallDriver` at `0x18003b8f2`
- `ntoskrnl!IofCallDriver` at `0x18003b8f2`
- `ntoskrnl!KeInitializeEvent` at `0x18003b87a`
- `ntoskrnl!KeInitializeEvent` at `0x18003b87a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18003b8be`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18003b8be`

## string_xrefs

- `0x18003b416`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b5c1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b5ec`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b6fa`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b7df`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b8d4`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b953`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003ba33`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003bacd`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadInterface(__int64 a1, int *a2, int a3, _WORD **a4)
{
  bool v4; // zf
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  NTSTATUS RngInterface; // ebx
  __int64 v18; // r9
  __int64 v19; // r9
  int v20; // eax
  int v21; // r15d
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // r9
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  ULONG v41; // ebx
  const WCHAR *v42; // rdx
  const WCHAR *v43; // rdx
  IRP *v44; // rax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // r9
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  __int64 v55; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-29h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-1h] BYREF
  __int128 v60; // [rsp+88h] [rbp+Fh]
  __int64 v61; // [rsp+98h] [rbp+1Fh]
  _WORD *OutputBuffer; // [rsp+E0h] [rbp+67h] BYREF

  v4 = *(_QWORD *)a1 == 0;
  v61 = 0;
  OutputBuffer = 0;
  v8 = *a2;
  DestinationString = 0;
  v60 = 0;
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  if ( v4 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  v16 = v15 - 1;
                  if ( v16 )
                  {
                    if ( v16 != 65530 )
                    {
                      RngInterface = -1073741637;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          (_DWORD)a2,
                          a3,
                          (unsigned int)"sResult",
                          187,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                          172);
                      }
                      return (unsigned int)RngInterface;
                    }
                    RngInterface = ((__int64 (__fastcall *)(_QWORD, _WORD **, _QWORD))GetSChannelInterface)(
                                     *((_QWORD *)a2 + 2),
                                     a4,
                                     0);
                    if ( RngInterface < 0 )
                    {
                      v18 = 1608;
LABEL_32:
                      DebugTraceError(
                        (unsigned int)RngInterface,
                        "ntStatus",
                        "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                        v18);
                      v19 = 1728;
LABEL_143:
                      v27 = (unsigned int)RngInterface;
                      goto LABEL_144;
                    }
                  }
                  else
                  {
                    RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetKeyEncapsulationInterface)(
                                     *((_QWORD *)a2 + 2),
                                     *((_QWORD *)a2 + 1),
                                     a4,
                                     0);
                    if ( RngInterface < 0 )
                    {
                      v18 = 1572;
                      goto LABEL_32;
                    }
                  }
                }
                else
                {
                  RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetKeyDerivationInterface)(
                                   *((_QWORD *)a2 + 2),
                                   *((_QWORD *)a2 + 1),
                                   a4,
                                   0);
                  if ( RngInterface < 0 )
                  {
                    v18 = 1559;
                    goto LABEL_32;
                  }
                }
              }
              else
              {
                RngInterface = GetRngInterface(*((_QWORD *)a2 + 2), a4, 0);
                if ( RngInterface < 0 )
                {
                  v18 = 1546;
                  goto LABEL_32;
                }
              }
            }
            else
            {
              RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetSignatureInterface)(
                               *((_QWORD *)a2 + 2),
                               *((_QWORD *)a2 + 1),
                               a4,
                               0);
              if ( RngInterface < 0 )
              {
                v18 = 1534;
                goto LABEL_32;
              }
            }
          }
          else
          {
            RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetSecretAgreementInterface)(
                             *((_QWORD *)a2 + 2),
                             *((_QWORD *)a2 + 1),
                             a4,
                             0);
            if ( RngInterface < 0 )
            {
              v18 = 1521;
              goto LABEL_32;
            }
          }
        }
        else
        {
          RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetAsymmetricEncryptionInterface)(
                           *((_QWORD *)a2 + 2),
                           *((_QWORD *)a2 + 1),
                           a4,
                           0);
          if ( RngInterface < 0 )
          {
            v18 = 1508;
            goto LABEL_32;
          }
        }
      }
      else
      {
        RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetHashInterface)(
                         *((_QWORD *)a2 + 2),
                         *((_QWORD *)a2 + 1),
                         a4,
                         0);
        if ( RngInterface < 0 )
        {
          v18 = 1495;
          goto LABEL_32;
        }
      }
    }
    else
    {
      RngInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))GetCipherInterface)(
                       *((_QWORD *)a2 + 2),
                       *((_QWORD *)a2 + 1),
                       a4,
                       0);
      if ( RngInterface < 0 )
      {
        v18 = 1482;
        goto LABEL_32;
      }
    }
    v20 = *a2;
    v21 = 0;
    if ( (unsigned int)*a2 > 6 )
    {
      v28 = v20 - 7;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 65529;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( v31 )
            {
              if ( v31 != 2 )
              {
LABEL_61:
                v32 = 1450;
LABEL_62:
                RngInterface = -1073741637;
                v21 = -1073741637;
                DebugTraceError(
                  3221225659LL,
                  "ntStatus",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                  v32);
LABEL_52:
                v19 = 1723;
LABEL_53:
                v27 = (unsigned int)v21;
LABEL_144:
                DebugTraceError(v27, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v19);
                return (unsigned int)RngInterface;
              }
              if ( !**a4 )
              {
                v26 = 1434;
                goto LABEL_50;
              }
            }
            else if ( !**a4 )
            {
              v26 = 1444;
              goto LABEL_50;
            }
          }
          else if ( !**a4 )
          {
            v26 = 1424;
            goto LABEL_50;
          }
        }
        else if ( !**a4 )
        {
          v26 = 1414;
          goto LABEL_50;
        }
      }
      else if ( !**a4 )
      {
        v32 = 1404;
        goto LABEL_62;
      }
    }
    else
    {
      if ( v20 != 6 )
      {
        v22 = v20 - 1;
        if ( !v22 )
        {
          if ( **a4 )
            goto LABEL_51;
          v26 = 1344;
          goto LABEL_50;
        }
        v23 = v22 - 1;
        if ( !v23 )
        {
          if ( **a4 )
            goto LABEL_51;
          v26 = 1354;
          goto LABEL_50;
        }
        v24 = v23 - 1;
        if ( !v24 )
        {
          if ( **a4 )
            goto LABEL_51;
          v26 = 1364;
          goto LABEL_50;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          if ( **a4 )
            goto LABEL_51;
          v26 = 1374;
          goto LABEL_50;
        }
        if ( v25 == 1 )
        {
          if ( **a4 )
            goto LABEL_51;
          v26 = 1384;
          goto LABEL_50;
        }
        goto LABEL_61;
      }
      if ( !**a4 )
      {
        v26 = 1394;
LABEL_50:
        v21 = -1073741637;
        DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v26);
      }
    }
LABEL_51:
    RngInterface = v21;
    if ( v21 >= 0 )
      return (unsigned int)RngInterface;
    goto LABEL_52;
  }
  v33 = v8 - 1;
  if ( v33 )
  {
    v34 = v33 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( v36 )
        {
          v37 = v36 - 1;
          if ( v37 )
          {
            v38 = v37 - 1;
            if ( v38 )
            {
              v39 = v38 - 1;
              if ( v39 )
              {
                v40 = v39 - 1;
                if ( v40 )
                {
                  if ( v40 != 65530 )
                  {
                    RngInterface = -1073741637;
                    v19 = 1778;
                    v27 = 3221225659LL;
                    goto LABEL_144;
                  }
                  v41 = 2228259;
                }
                else
                {
                  v41 = 2228263;
                }
              }
              else
              {
                v41 = 2228255;
              }
            }
            else
            {
              v41 = 2228251;
            }
          }
          else
          {
            v41 = 2228247;
          }
        }
        else
        {
          v41 = 2228243;
        }
      }
      else
      {
        v41 = 2228239;
      }
    }
    else
    {
      v41 = 2228235;
    }
  }
  else
  {
    v41 = 2228231;
  }
  v42 = (const WCHAR *)*((_QWORD *)a2 + 2);
  *(_QWORD *)&DestinationString.Length = 1;
  RtlInitUnicodeString((PUNICODE_STRING)&DestinationString.Buffer, v42);
  v43 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( v43 )
    RtlInitUnicodeString((PUNICODE_STRING)&DestinationString.Buffer, v43);
  OutputBuffer = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v44 = IoBuildDeviceIoControlRequest(
          v41,
          *(PDEVICE_OBJECT *)(a1 + 8),
          &DestinationString,
          0x28u,
          &OutputBuffer,
          8u,
          1u,
          &Event,
          &IoStatusBlock);
  if ( !v44 )
  {
    RngInterface = -1073741670;
    v19 = 1823;
    v27 = 3221225626LL;
    goto LABEL_144;
  }
  RngInterface = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 8), v44);
  if ( RngInterface == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    RngInterface = IoStatusBlock.Status;
  }
  if ( RngInterface < 0 )
  {
    v19 = 1859;
    goto LABEL_143;
  }
  if ( OutputBuffer )
    *a4 = OutputBuffer;
  else
    RngInterface = -1073741511;
  if ( RngInterface >= 0 )
  {
    v45 = *a2;
    v21 = 0;
    if ( (unsigned int)*a2 > 6 )
    {
      v51 = v45 - 7;
      if ( v51 )
      {
        v52 = v51 - 1;
        if ( v52 )
        {
          v53 = v52 - 65529;
          if ( v53 )
          {
            v54 = v53 - 1;
            if ( v54 )
            {
              if ( v54 != 2 )
              {
LABEL_130:
                v55 = 1450;
LABEL_131:
                RngInterface = -1073741637;
                v21 = -1073741637;
                DebugTraceError(
                  3221225659LL,
                  "ntStatus",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                  v55);
LABEL_122:
                v19 = 1874;
                goto LABEL_53;
              }
              if ( !**a4 )
              {
                v50 = 1434;
                goto LABEL_120;
              }
            }
            else if ( !**a4 )
            {
              v50 = 1444;
              goto LABEL_120;
            }
          }
          else if ( !**a4 )
          {
            v50 = 1424;
            goto LABEL_120;
          }
        }
        else if ( !**a4 )
        {
          v50 = 1414;
          goto LABEL_120;
        }
      }
      else if ( !**a4 )
      {
        v55 = 1404;
        goto LABEL_131;
      }
    }
    else
    {
      if ( v45 != 6 )
      {
        v46 = v45 - 1;
        if ( !v46 )
        {
          if ( **a4 )
            goto LABEL_121;
          v50 = 1344;
          goto LABEL_120;
        }
        v47 = v46 - 1;
        if ( !v47 )
        {
          if ( **a4 )
            goto LABEL_121;
          v50 = 1354;
          goto LABEL_120;
        }
        v48 = v47 - 1;
        if ( !v48 )
        {
          if ( **a4 )
            goto LABEL_121;
          v50 = 1364;
          goto LABEL_120;
        }
        v49 = v48 - 1;
        if ( !v49 )
        {
          if ( **a4 )
            goto LABEL_121;
          v50 = 1374;
          goto LABEL_120;
        }
        if ( v49 == 1 )
        {
          if ( **a4 )
            goto LABEL_121;
          v50 = 1384;
          goto LABEL_120;
        }
        goto LABEL_130;
      }
      if ( !**a4 )
      {
        v50 = 1394;
LABEL_120:
        v21 = -1073741637;
        DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v50);
      }
    }
LABEL_121:
    RngInterface = v21;
    if ( v21 >= 0 )
      return (unsigned int)RngInterface;
    goto LABEL_122;
  }
  return (unsigned int)RngInterface;
}

```

## disassembly

```asm
0x18003b348  push    rbp
0x18003b34a  push    rbx
0x18003b34b  push    rsi
0x18003b34c  push    rdi
0x18003b34d  push    r14
0x18003b34f  push    r15
0x18003b351  lea     rbp, [rsp-2Fh]
0x18003b356  sub     rsp, 0A8h
0x18003b35d  xor     eax, eax
0x18003b35f  xorps   xmm0, xmm0
0x18003b362  cmp     qword ptr [rcx], 0
0x18003b366  xorps   xmm1, xmm1
0x18003b369  mov     [rbp+57h+var_38], rax
0x18003b36d  mov     r14, r9
0x18003b370  mov     [rbp+57h+arg_0], rax
0x18003b374  mov     rdi, rdx
0x18003b377  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18003b37b  mov     r15, rcx
0x18003b37e  mov     eax, [rdx]
0x18003b380  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003b384  movups  [rbp+57h+var_48], xmm0
0x18003b388  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18003b38c  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x18003b390  jnz     loc_18003B7AB
0x18003b396  sub     eax, 1
0x18003b399  jz      loc_18003B59B
0x18003b39f  sub     eax, 1
0x18003b3a2  jz      loc_18003B573
0x18003b3a8  sub     eax, 1
0x18003b3ab  jz      loc_18003B54B
0x18003b3b1  sub     eax, 1
0x18003b3b4  jz      loc_18003B51F
0x18003b3ba  sub     eax, 1
0x18003b3bd  jz      loc_18003B4F0
0x18003b3c3  sub     eax, 1
0x18003b3c6  jz      loc_18003B4CC
0x18003b3cc  sub     eax, 1
0x18003b3cf  jz      loc_18003B49D
0x18003b3d5  sub     eax, 1
0x18003b3d8  jz      loc_18003B46E
0x18003b3de  cmp     eax, 0FFFAh
0x18003b3e3  jz      short loc_18003B443
0x18003b3e5  mov     ebx, 0C00000BBh
0x18003b3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3f1  lea     rax, WPP_GLOBAL_Control
0x18003b3f8  cmp     rcx, rax
0x18003b3fb  jz      loc_18003BAE2
0x18003b401  mov     eax, [rcx+2Ch]
0x18003b404  mov     esi, 1
0x18003b409  test    sil, al
0x18003b40c  jz      loc_18003BAE2
0x18003b412  mov     rcx, [rcx+18h]
0x18003b416  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b41d  mov     dword ptr [rsp+0D0h+InternalDeviceIoControl], 6ACh
0x18003b425  lea     r9, aSresult; "sResult"
0x18003b42c  mov     qword ptr [rsp+0D0h+OutputBufferLength], rdi
0x18003b431  mov     dword ptr [rsp+0D0h+OutputBuffer], 0C00000BBh
0x18003b439  call    WPP_SF_sDsd
0x18003b43e  jmp     loc_18003BAE2
0x18003b443  mov     rcx, [rdi+10h]
0x18003b447  lea     rax, GetSChannelInterface
0x18003b44e  xor     r8d, r8d
0x18003b451  mov     rdx, r14
0x18003b454  call    _guard_dispatch_icall
0x18003b459  mov     ebx, eax
0x18003b45b  test    eax, eax
0x18003b45d  jns     loc_18003B5E7
0x18003b463  mov     r9d, 648h
0x18003b469  jmp     loc_18003B5C1
0x18003b46e  mov     rdx, [rdx+8]
0x18003b472  lea     rax, GetKeyEncapsulationInterface
0x18003b479  mov     rcx, [rdi+10h]
0x18003b47d  xor     r9d, r9d
0x18003b480  mov     r8, r14
0x18003b483  call    _guard_dispatch_icall
0x18003b488  mov     ebx, eax
0x18003b48a  test    eax, eax
0x18003b48c  jns     loc_18003B5E7
0x18003b492  mov     r9d, 624h
0x18003b498  jmp     loc_18003B5C1
0x18003b49d  mov     rdx, [rdx+8]
0x18003b4a1  lea     rax, GetKeyDerivationInterface
0x18003b4a8  mov     rcx, [rdi+10h]
0x18003b4ac  xor     r9d, r9d
0x18003b4af  mov     r8, r14
0x18003b4b2  call    _guard_dispatch_icall
0x18003b4b7  mov     ebx, eax
0x18003b4b9  test    eax, eax
0x18003b4bb  jns     loc_18003B5E7
0x18003b4c1  mov     r9d, 617h
0x18003b4c7  jmp     loc_18003B5C1
0x18003b4cc  mov     rcx, [rdi+10h]
0x18003b4d0  xor     r8d, r8d
0x18003b4d3  mov     rdx, r14
0x18003b4d6  call    GetRngInterface
0x18003b4db  mov     ebx, eax
0x18003b4dd  test    eax, eax
0x18003b4df  jns     loc_18003B5E7
0x18003b4e5  mov     r9d, 60Ah
0x18003b4eb  jmp     loc_18003B5C1
0x18003b4f0  mov     rdx, [rdx+8]
0x18003b4f4  lea     rax, GetSignatureInterface
0x18003b4fb  mov     rcx, [rdi+10h]
0x18003b4ff  xor     r9d, r9d
0x18003b502  mov     r8, r14
0x18003b505  call    _guard_dispatch_icall
0x18003b50a  mov     ebx, eax
0x18003b50c  test    eax, eax
0x18003b50e  jns     loc_18003B5E7
0x18003b514  mov     r9d, 5FEh
0x18003b51a  jmp     loc_18003B5C1
0x18003b51f  mov     rdx, [rdx+8]
0x18003b523  lea     rax, GetSecretAgreementInterface
0x18003b52a  mov     rcx, [rdi+10h]
0x18003b52e  xor     r9d, r9d
0x18003b531  mov     r8, r14
0x18003b534  call    _guard_dispatch_icall
0x18003b539  mov     ebx, eax
0x18003b53b  test    eax, eax
0x18003b53d  jns     loc_18003B5E7
0x18003b543  mov     r9d, 5F1h
0x18003b549  jmp     short loc_18003B5C1
0x18003b54b  mov     rdx, [rdx+8]
0x18003b54f  lea     rax, GetAsymmetricEncryptionInterface
0x18003b556  mov     rcx, [rdi+10h]
0x18003b55a  xor     r9d, r9d
0x18003b55d  mov     r8, r14
0x18003b560  call    _guard_dispatch_icall
0x18003b565  mov     ebx, eax
0x18003b567  test    eax, eax
0x18003b569  jns     short loc_18003B5E7
0x18003b56b  mov     r9d, 5E4h
0x18003b571  jmp     short loc_18003B5C1
0x18003b573  mov     rdx, [rdx+8]
0x18003b577  lea     rax, GetHashInterface
0x18003b57e  mov     rcx, [rdi+10h]
0x18003b582  xor     r9d, r9d
0x18003b585  mov     r8, r14
0x18003b588  call    _guard_dispatch_icall
0x18003b58d  mov     ebx, eax
0x18003b58f  test    eax, eax
0x18003b591  jns     short loc_18003B5E7
0x18003b593  mov     r9d, 5D7h
0x18003b599  jmp     short loc_18003B5C1
0x18003b59b  mov     rdx, [rdx+8]
0x18003b59f  lea     rax, GetCipherInterface
0x18003b5a6  mov     rcx, [rdi+10h]
0x18003b5aa  xor     r9d, r9d
0x18003b5ad  mov     r8, r14
0x18003b5b0  call    _guard_dispatch_icall
0x18003b5b5  mov     ebx, eax
0x18003b5b7  test    eax, eax
0x18003b5b9  jns     short loc_18003B5E7
0x18003b5bb  mov     r9d, 5CAh
0x18003b5c1  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b5c8  mov     ecx, ebx
0x18003b5ca  mov     r8, rdi
0x18003b5cd  lea     rdx, aNtstatus; "ntStatus"
0x18003b5d4  call    DebugTraceError
0x18003b5d9  mov     r9d, 6C0h
0x18003b5df  mov     r8, rdi
0x18003b5e2  jmp     loc_18003BAD4
0x18003b5e7  mov     eax, [rdi]
0x18003b5e9  xor     r15d, r15d
0x18003b5ec  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b5f3  cmp     eax, 6
0x18003b5f6  ja      loc_18003B6D1
0x18003b5fc  jz      loc_18003B6BC
0x18003b602  sub     eax, 1
0x18003b605  jz      short loc_18003B672
0x18003b607  sub     eax, 1
0x18003b60a  jz      short loc_18003B65D
0x18003b60c  sub     eax, 1
0x18003b60f  jz      short loc_18003B648
0x18003b611  sub     eax, 1
0x18003b614  jz      short loc_18003B633
0x18003b616  cmp     eax, 1
0x18003b619  jnz     loc_18003B6F4
0x18003b61f  mov     rax, [r14]
0x18003b622  lea     esi, [r15+1]
0x18003b626  cmp     si, [rax]
0x18003b629  jbe     short loc_18003B69F
0x18003b62b  mov     r9d, 568h
0x18003b631  jmp     short loc_18003B685
0x18003b633  mov     rax, [r14]
0x18003b636  mov     esi, 1
0x18003b63b  cmp     si, [rax]
0x18003b63e  jbe     short loc_18003B69F
0x18003b640  mov     r9d, 55Eh
0x18003b646  jmp     short loc_18003B685
0x18003b648  mov     rax, [r14]
0x18003b64b  mov     esi, 1
0x18003b650  cmp     si, [rax]
0x18003b653  jbe     short loc_18003B69F
0x18003b655  mov     r9d, 554h
0x18003b65b  jmp     short loc_18003B685
0x18003b65d  mov     rax, [r14]
0x18003b660  mov     esi, 1
0x18003b665  cmp     si, [rax]
0x18003b668  jbe     short loc_18003B69F
0x18003b66a  mov     r9d, 54Ah
0x18003b670  jmp     short loc_18003B685
0x18003b672  mov     rax, [r14]
0x18003b675  mov     esi, 1
0x18003b67a  cmp     si, [rax]
0x18003b67d  jbe     short loc_18003B69F
0x18003b67f  mov     r9d, 540h
0x18003b685  mov     r8, rdi
0x18003b688  lea     rdx, aNtstatus; "ntStatus"
0x18003b68f  mov     ecx, 0C00000BBh
0x18003b694  mov     r15d, 0C00000BBh
0x18003b69a  call    DebugTraceError
0x18003b69f  mov     ebx, r15d
0x18003b6a2  test    r15d, r15d
0x18003b6a5  jns     loc_18003BAE2
0x18003b6ab  mov     r9d, 6BBh
0x18003b6b1  mov     r8, rdi
0x18003b6b4  mov     ecx, r15d
0x18003b6b7  jmp     loc_18003BAD6
0x18003b6bc  mov     rax, [r14]
0x18003b6bf  mov     esi, 1
0x18003b6c4  cmp     si, [rax]
0x18003b6c7  jbe     short loc_18003B69F
0x18003b6c9  mov     r9d, 572h
0x18003b6cf  jmp     short loc_18003B685
0x18003b6d1  sub     eax, 7
0x18003b6d4  jz      loc_18003B78F
0x18003b6da  sub     eax, 1
0x18003b6dd  jz      loc_18003B773
0x18003b6e3  sub     eax, 0FFF9h
0x18003b6e8  jz      short loc_18003B757
0x18003b6ea  sub     eax, 1
0x18003b6ed  jz      short loc_18003B73B
0x18003b6ef  cmp     eax, 2
0x18003b6f2  jz      short loc_18003B71F
0x18003b6f4  mov     r9d, 5AAh
0x18003b6fa  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b701  mov     ebx, 0C00000BBh
0x18003b706  mov     r8, rdi
0x18003b709  lea     rdx, aNtstatus; "ntStatus"
0x18003b710  mov     ecx, 0C00000BBh
0x18003b715  mov     r15d, ebx
0x18003b718  call    DebugTraceError
0x18003b71d  jmp     short loc_18003B6AB
0x18003b71f  mov     rax, [r14]
0x18003b722  mov     esi, 1
0x18003b727  cmp     si, [rax]
0x18003b72a  jbe     loc_18003B69F
0x18003b730  mov     r9d, 59Ah
0x18003b736  jmp     loc_18003B685
0x18003b73b  mov     rax, [r14]
0x18003b73e  mov     esi, 1
0x18003b743  cmp     si, [rax]
0x18003b746  jbe     loc_18003B69F
0x18003b74c  mov     r9d, 5A4h
0x18003b752  jmp     loc_18003B685
0x18003b757  mov     rax, [r14]
0x18003b75a  mov     esi, 1
0x18003b75f  cmp     si, [rax]
0x18003b762  jbe     loc_18003B69F
0x18003b768  mov     r9d, 590h
0x18003b76e  jmp     loc_18003B685
0x18003b773  mov     rax, [r14]
0x18003b776  mov     esi, 1
0x18003b77b  cmp     si, [rax]
0x18003b77e  jbe     loc_18003B69F
0x18003b784  mov     r9d, 586h
0x18003b78a  jmp     loc_18003B685
0x18003b78f  mov     rax, [r14]
0x18003b792  mov     esi, 1
0x18003b797  cmp     si, [rax]
0x18003b79a  jbe     loc_18003B69F
0x18003b7a0  mov     r9d, 57Ch
0x18003b7a6  jmp     loc_18003B6FA
0x18003b7ab  sub     eax, 1
0x18003b7ae  jz      short loc_18003B82E
0x18003b7b0  sub     eax, 1
0x18003b7b3  jz      short loc_18003B827
0x18003b7b5  sub     eax, 1
0x18003b7b8  jz      short loc_18003B820
0x18003b7ba  sub     eax, 1
0x18003b7bd  jz      short loc_18003B819
0x18003b7bf  sub     eax, 1
0x18003b7c2  jz      short loc_18003B812
0x18003b7c4  sub     eax, 1
0x18003b7c7  jz      short loc_18003B80B
0x18003b7c9  sub     eax, 1
0x18003b7cc  jz      short loc_18003B804
0x18003b7ce  sub     eax, 1
0x18003b7d1  jz      short loc_18003B7FD
0x18003b7d3  cmp     eax, 0FFFAh
0x18003b7d8  jz      short loc_18003B7F6
0x18003b7da  mov     ebx, 0C00000BBh
0x18003b7df  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b7e6  mov     r9d, 6F2h
0x18003b7ec  mov     ecx, 0C00000BBh
0x18003b7f1  jmp     loc_18003BAD6
0x18003b7f6  mov     ebx, 220023h
0x18003b7fb  jmp     short loc_18003B833
0x18003b7fd  mov     ebx, 220027h
  ... truncated ...
```
