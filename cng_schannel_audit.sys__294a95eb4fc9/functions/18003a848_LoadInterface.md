# _LoadInterface

- ea: `0x18003a848`
- end: `0x18003aff5`
- name: `_LoadInterface`
- size: `1965`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003a46c`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003a848`
- `0x1800745b0`
- `0x18009d860`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18003ae1c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003ae1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003ad44`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003ad5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003ad44`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003ad5d`
- `ntoskrnl!IofCallDriver` at `0x18003adf2`
- `ntoskrnl!IofCallDriver` at `0x18003adf2`
- `ntoskrnl!KeInitializeEvent` at `0x18003ad7a`
- `ntoskrnl!KeInitializeEvent` at `0x18003ad7a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18003adbe`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18003adbe`

## string_xrefs

- `0x18003a916`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003aac1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003aaec`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003abfa`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003acdf`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003add4`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003ae53`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003af33`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003afcd`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18003a848  push    rbp
0x18003a84a  push    rbx
0x18003a84b  push    rsi
0x18003a84c  push    rdi
0x18003a84d  push    r14
0x18003a84f  push    r15
0x18003a851  lea     rbp, [rsp-2Fh]
0x18003a856  sub     rsp, 0A8h
0x18003a85d  xor     eax, eax
0x18003a85f  xorps   xmm0, xmm0
0x18003a862  cmp     qword ptr [rcx], 0
0x18003a866  xorps   xmm1, xmm1
0x18003a869  mov     [rbp+57h+var_38], rax
0x18003a86d  mov     r14, r9
0x18003a870  mov     [rbp+57h+arg_0], rax
0x18003a874  mov     rdi, rdx
0x18003a877  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18003a87b  mov     r15, rcx
0x18003a87e  mov     eax, [rdx]
0x18003a880  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003a884  movups  [rbp+57h+var_48], xmm0
0x18003a888  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18003a88c  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x18003a890  jnz     loc_18003ACAB
0x18003a896  sub     eax, 1
0x18003a899  jz      loc_18003AA9B
0x18003a89f  sub     eax, 1
0x18003a8a2  jz      loc_18003AA73
0x18003a8a8  sub     eax, 1
0x18003a8ab  jz      loc_18003AA4B
0x18003a8b1  sub     eax, 1
0x18003a8b4  jz      loc_18003AA1F
0x18003a8ba  sub     eax, 1
0x18003a8bd  jz      loc_18003A9F0
0x18003a8c3  sub     eax, 1
0x18003a8c6  jz      loc_18003A9CC
0x18003a8cc  sub     eax, 1
0x18003a8cf  jz      loc_18003A99D
0x18003a8d5  sub     eax, 1
0x18003a8d8  jz      loc_18003A96E
0x18003a8de  cmp     eax, 0FFFAh
0x18003a8e3  jz      short loc_18003A943
0x18003a8e5  mov     ebx, 0C00000BBh
0x18003a8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8f1  lea     rax, WPP_GLOBAL_Control
0x18003a8f8  cmp     rcx, rax
0x18003a8fb  jz      loc_18003AFE2
0x18003a901  mov     eax, [rcx+2Ch]
0x18003a904  mov     esi, 1
0x18003a909  test    sil, al
0x18003a90c  jz      loc_18003AFE2
0x18003a912  mov     rcx, [rcx+18h]
0x18003a916  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a91d  mov     dword ptr [rsp+0D0h+InternalDeviceIoControl], 6ACh
0x18003a925  lea     r9, aSresult; "sResult"
0x18003a92c  mov     qword ptr [rsp+0D0h+OutputBufferLength], rdi
0x18003a931  mov     dword ptr [rsp+0D0h+OutputBuffer], 0C00000BBh
0x18003a939  call    WPP_SF_sDsd
0x18003a93e  jmp     loc_18003AFE2
0x18003a943  mov     rcx, [rdi+10h]
0x18003a947  lea     rax, GetSChannelInterface
0x18003a94e  xor     r8d, r8d
0x18003a951  mov     rdx, r14
0x18003a954  call    _guard_dispatch_icall
0x18003a959  mov     ebx, eax
0x18003a95b  test    eax, eax
0x18003a95d  jns     loc_18003AAE7
0x18003a963  mov     r9d, 648h
0x18003a969  jmp     loc_18003AAC1
0x18003a96e  mov     rdx, [rdx+8]
0x18003a972  lea     rax, GetKeyEncapsulationInterface
0x18003a979  mov     rcx, [rdi+10h]
0x18003a97d  xor     r9d, r9d
0x18003a980  mov     r8, r14
0x18003a983  call    _guard_dispatch_icall
0x18003a988  mov     ebx, eax
0x18003a98a  test    eax, eax
0x18003a98c  jns     loc_18003AAE7
0x18003a992  mov     r9d, 624h
0x18003a998  jmp     loc_18003AAC1
0x18003a99d  mov     rdx, [rdx+8]
0x18003a9a1  lea     rax, GetKeyDerivationInterface
0x18003a9a8  mov     rcx, [rdi+10h]
0x18003a9ac  xor     r9d, r9d
0x18003a9af  mov     r8, r14
0x18003a9b2  call    _guard_dispatch_icall
0x18003a9b7  mov     ebx, eax
0x18003a9b9  test    eax, eax
0x18003a9bb  jns     loc_18003AAE7
0x18003a9c1  mov     r9d, 617h
0x18003a9c7  jmp     loc_18003AAC1
0x18003a9cc  mov     rcx, [rdi+10h]
0x18003a9d0  xor     r8d, r8d
0x18003a9d3  mov     rdx, r14
0x18003a9d6  call    GetRngInterface
0x18003a9db  mov     ebx, eax
0x18003a9dd  test    eax, eax
0x18003a9df  jns     loc_18003AAE7
0x18003a9e5  mov     r9d, 60Ah
0x18003a9eb  jmp     loc_18003AAC1
0x18003a9f0  mov     rdx, [rdx+8]
0x18003a9f4  lea     rax, GetSignatureInterface
0x18003a9fb  mov     rcx, [rdi+10h]
0x18003a9ff  xor     r9d, r9d
0x18003aa02  mov     r8, r14
0x18003aa05  call    _guard_dispatch_icall
0x18003aa0a  mov     ebx, eax
0x18003aa0c  test    eax, eax
0x18003aa0e  jns     loc_18003AAE7
0x18003aa14  mov     r9d, 5FEh
0x18003aa1a  jmp     loc_18003AAC1
0x18003aa1f  mov     rdx, [rdx+8]
0x18003aa23  lea     rax, GetSecretAgreementInterface
0x18003aa2a  mov     rcx, [rdi+10h]
0x18003aa2e  xor     r9d, r9d
0x18003aa31  mov     r8, r14
0x18003aa34  call    _guard_dispatch_icall
0x18003aa39  mov     ebx, eax
0x18003aa3b  test    eax, eax
0x18003aa3d  jns     loc_18003AAE7
0x18003aa43  mov     r9d, 5F1h
0x18003aa49  jmp     short loc_18003AAC1
0x18003aa4b  mov     rdx, [rdx+8]
0x18003aa4f  lea     rax, GetAsymmetricEncryptionInterface
0x18003aa56  mov     rcx, [rdi+10h]
0x18003aa5a  xor     r9d, r9d
0x18003aa5d  mov     r8, r14
0x18003aa60  call    _guard_dispatch_icall
0x18003aa65  mov     ebx, eax
0x18003aa67  test    eax, eax
0x18003aa69  jns     short loc_18003AAE7
0x18003aa6b  mov     r9d, 5E4h
0x18003aa71  jmp     short loc_18003AAC1
0x18003aa73  mov     rdx, [rdx+8]
0x18003aa77  lea     rax, GetHashInterface
0x18003aa7e  mov     rcx, [rdi+10h]
0x18003aa82  xor     r9d, r9d
0x18003aa85  mov     r8, r14
0x18003aa88  call    _guard_dispatch_icall
0x18003aa8d  mov     ebx, eax
0x18003aa8f  test    eax, eax
0x18003aa91  jns     short loc_18003AAE7
0x18003aa93  mov     r9d, 5D7h
0x18003aa99  jmp     short loc_18003AAC1
0x18003aa9b  mov     rdx, [rdx+8]
0x18003aa9f  lea     rax, GetCipherInterface
0x18003aaa6  mov     rcx, [rdi+10h]
0x18003aaaa  xor     r9d, r9d
0x18003aaad  mov     r8, r14
0x18003aab0  call    _guard_dispatch_icall
0x18003aab5  mov     ebx, eax
0x18003aab7  test    eax, eax
0x18003aab9  jns     short loc_18003AAE7
0x18003aabb  mov     r9d, 5CAh
0x18003aac1  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003aac8  mov     ecx, ebx
0x18003aaca  mov     r8, rdi
0x18003aacd  lea     rdx, aNtstatus; "ntStatus"
0x18003aad4  call    DebugTraceError
0x18003aad9  mov     r9d, 6C0h
0x18003aadf  mov     r8, rdi
0x18003aae2  jmp     loc_18003AFD4
0x18003aae7  mov     eax, [rdi]
0x18003aae9  xor     r15d, r15d
0x18003aaec  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003aaf3  cmp     eax, 6
0x18003aaf6  ja      loc_18003ABD1
0x18003aafc  jz      loc_18003ABBC
0x18003ab02  sub     eax, 1
0x18003ab05  jz      short loc_18003AB72
0x18003ab07  sub     eax, 1
0x18003ab0a  jz      short loc_18003AB5D
0x18003ab0c  sub     eax, 1
0x18003ab0f  jz      short loc_18003AB48
0x18003ab11  sub     eax, 1
0x18003ab14  jz      short loc_18003AB33
0x18003ab16  cmp     eax, 1
0x18003ab19  jnz     loc_18003ABF4
0x18003ab1f  mov     rax, [r14]
0x18003ab22  lea     esi, [r15+1]
0x18003ab26  cmp     si, [rax]
0x18003ab29  jbe     short loc_18003AB9F
0x18003ab2b  mov     r9d, 568h
0x18003ab31  jmp     short loc_18003AB85
0x18003ab33  mov     rax, [r14]
0x18003ab36  mov     esi, 1
0x18003ab3b  cmp     si, [rax]
0x18003ab3e  jbe     short loc_18003AB9F
0x18003ab40  mov     r9d, 55Eh
0x18003ab46  jmp     short loc_18003AB85
0x18003ab48  mov     rax, [r14]
0x18003ab4b  mov     esi, 1
0x18003ab50  cmp     si, [rax]
0x18003ab53  jbe     short loc_18003AB9F
0x18003ab55  mov     r9d, 554h
0x18003ab5b  jmp     short loc_18003AB85
0x18003ab5d  mov     rax, [r14]
0x18003ab60  mov     esi, 1
0x18003ab65  cmp     si, [rax]
0x18003ab68  jbe     short loc_18003AB9F
0x18003ab6a  mov     r9d, 54Ah
0x18003ab70  jmp     short loc_18003AB85
0x18003ab72  mov     rax, [r14]
0x18003ab75  mov     esi, 1
0x18003ab7a  cmp     si, [rax]
0x18003ab7d  jbe     short loc_18003AB9F
0x18003ab7f  mov     r9d, 540h
0x18003ab85  mov     r8, rdi
0x18003ab88  lea     rdx, aNtstatus; "ntStatus"
0x18003ab8f  mov     ecx, 0C00000BBh
0x18003ab94  mov     r15d, 0C00000BBh
0x18003ab9a  call    DebugTraceError
0x18003ab9f  mov     ebx, r15d
0x18003aba2  test    r15d, r15d
0x18003aba5  jns     loc_18003AFE2
0x18003abab  mov     r9d, 6BBh
0x18003abb1  mov     r8, rdi
0x18003abb4  mov     ecx, r15d
0x18003abb7  jmp     loc_18003AFD6
0x18003abbc  mov     rax, [r14]
0x18003abbf  mov     esi, 1
0x18003abc4  cmp     si, [rax]
0x18003abc7  jbe     short loc_18003AB9F
0x18003abc9  mov     r9d, 572h
0x18003abcf  jmp     short loc_18003AB85
0x18003abd1  sub     eax, 7
0x18003abd4  jz      loc_18003AC8F
0x18003abda  sub     eax, 1
0x18003abdd  jz      loc_18003AC73
0x18003abe3  sub     eax, 0FFF9h
0x18003abe8  jz      short loc_18003AC57
0x18003abea  sub     eax, 1
0x18003abed  jz      short loc_18003AC3B
0x18003abef  cmp     eax, 2
0x18003abf2  jz      short loc_18003AC1F
0x18003abf4  mov     r9d, 5AAh
0x18003abfa  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ac01  mov     ebx, 0C00000BBh
0x18003ac06  mov     r8, rdi
0x18003ac09  lea     rdx, aNtstatus; "ntStatus"
0x18003ac10  mov     ecx, 0C00000BBh
0x18003ac15  mov     r15d, ebx
0x18003ac18  call    DebugTraceError
0x18003ac1d  jmp     short loc_18003ABAB
0x18003ac1f  mov     rax, [r14]
0x18003ac22  mov     esi, 1
0x18003ac27  cmp     si, [rax]
0x18003ac2a  jbe     loc_18003AB9F
0x18003ac30  mov     r9d, 59Ah
0x18003ac36  jmp     loc_18003AB85
0x18003ac3b  mov     rax, [r14]
0x18003ac3e  mov     esi, 1
0x18003ac43  cmp     si, [rax]
0x18003ac46  jbe     loc_18003AB9F
0x18003ac4c  mov     r9d, 5A4h
0x18003ac52  jmp     loc_18003AB85
0x18003ac57  mov     rax, [r14]
0x18003ac5a  mov     esi, 1
0x18003ac5f  cmp     si, [rax]
0x18003ac62  jbe     loc_18003AB9F
0x18003ac68  mov     r9d, 590h
0x18003ac6e  jmp     loc_18003AB85
0x18003ac73  mov     rax, [r14]
0x18003ac76  mov     esi, 1
0x18003ac7b  cmp     si, [rax]
0x18003ac7e  jbe     loc_18003AB9F
0x18003ac84  mov     r9d, 586h
0x18003ac8a  jmp     loc_18003AB85
0x18003ac8f  mov     rax, [r14]
0x18003ac92  mov     esi, 1
0x18003ac97  cmp     si, [rax]
0x18003ac9a  jbe     loc_18003AB9F
0x18003aca0  mov     r9d, 57Ch
0x18003aca6  jmp     loc_18003ABFA
0x18003acab  sub     eax, 1
0x18003acae  jz      short loc_18003AD2E
0x18003acb0  sub     eax, 1
0x18003acb3  jz      short loc_18003AD27
0x18003acb5  sub     eax, 1
0x18003acb8  jz      short loc_18003AD20
0x18003acba  sub     eax, 1
0x18003acbd  jz      short loc_18003AD19
0x18003acbf  sub     eax, 1
0x18003acc2  jz      short loc_18003AD12
0x18003acc4  sub     eax, 1
0x18003acc7  jz      short loc_18003AD0B
0x18003acc9  sub     eax, 1
0x18003accc  jz      short loc_18003AD04
0x18003acce  sub     eax, 1
0x18003acd1  jz      short loc_18003ACFD
0x18003acd3  cmp     eax, 0FFFAh
0x18003acd8  jz      short loc_18003ACF6
0x18003acda  mov     ebx, 0C00000BBh
0x18003acdf  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ace6  mov     r9d, 6F2h
0x18003acec  mov     ecx, 0C00000BBh
0x18003acf1  jmp     loc_18003AFD6
0x18003acf6  mov     ebx, 220023h
0x18003acfb  jmp     short loc_18003AD33
0x18003acfd  mov     ebx, 220027h
  ... truncated ...
```
