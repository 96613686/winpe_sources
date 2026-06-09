# _LoadInterface

- ea: `0x1800448d8`
- end: `0x180045085`
- name: `_LoadInterface`
- size: `1965`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800444fc`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x1800448d8`
- `0x18007e750`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x180044eac`
- `ntoskrnl!KeWaitForSingleObject` at `0x180044eac`
- `ntoskrnl!RtlInitUnicodeString` at `0x180044dd4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180044ded`
- `ntoskrnl!RtlInitUnicodeString` at `0x180044dd4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180044ded`
- `ntoskrnl!IofCallDriver` at `0x180044e82`
- `ntoskrnl!IofCallDriver` at `0x180044e82`
- `ntoskrnl!KeInitializeEvent` at `0x180044e0a`
- `ntoskrnl!KeInitializeEvent` at `0x180044e0a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180044e4e`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180044e4e`

## string_xrefs

- `0x1800449a6`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044b51`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044b7c`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044c8a`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044d6f`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044e64`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044ee3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180044fc3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18004505d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x1800448d8  push    rbp
0x1800448da  push    rbx
0x1800448db  push    rsi
0x1800448dc  push    rdi
0x1800448dd  push    r14
0x1800448df  push    r15
0x1800448e1  lea     rbp, [rsp-2Fh]
0x1800448e6  sub     rsp, 0A8h
0x1800448ed  xor     eax, eax
0x1800448ef  xorps   xmm0, xmm0
0x1800448f2  cmp     qword ptr [rcx], 0
0x1800448f6  xorps   xmm1, xmm1
0x1800448f9  mov     [rbp+57h+var_38], rax
0x1800448fd  mov     r14, r9
0x180044900  mov     [rbp+57h+arg_0], rax
0x180044904  mov     rdi, rdx
0x180044907  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18004490b  mov     r15, rcx
0x18004490e  mov     eax, [rdx]
0x180044910  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180044914  movups  [rbp+57h+var_48], xmm0
0x180044918  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18004491c  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x180044920  jnz     loc_180044D3B
0x180044926  sub     eax, 1
0x180044929  jz      loc_180044B2B
0x18004492f  sub     eax, 1
0x180044932  jz      loc_180044B03
0x180044938  sub     eax, 1
0x18004493b  jz      loc_180044ADB
0x180044941  sub     eax, 1
0x180044944  jz      loc_180044AAF
0x18004494a  sub     eax, 1
0x18004494d  jz      loc_180044A80
0x180044953  sub     eax, 1
0x180044956  jz      loc_180044A5C
0x18004495c  sub     eax, 1
0x18004495f  jz      loc_180044A2D
0x180044965  sub     eax, 1
0x180044968  jz      loc_1800449FE
0x18004496e  cmp     eax, 0FFFAh
0x180044973  jz      short loc_1800449D3
0x180044975  mov     ebx, 0C00000BBh
0x18004497a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044981  lea     rax, WPP_GLOBAL_Control
0x180044988  cmp     rcx, rax
0x18004498b  jz      loc_180045072
0x180044991  mov     eax, [rcx+2Ch]
0x180044994  mov     esi, 1
0x180044999  test    sil, al
0x18004499c  jz      loc_180045072
0x1800449a2  mov     rcx, [rcx+18h]
0x1800449a6  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800449ad  mov     dword ptr [rsp+0D0h+InternalDeviceIoControl], 6ACh
0x1800449b5  lea     r9, aSresult; "sResult"
0x1800449bc  mov     qword ptr [rsp+0D0h+OutputBufferLength], rdi
0x1800449c1  mov     dword ptr [rsp+0D0h+OutputBuffer], 0C00000BBh
0x1800449c9  call    WPP_SF_sDsd
0x1800449ce  jmp     loc_180045072
0x1800449d3  mov     rcx, [rdi+10h]
0x1800449d7  lea     rax, GetSChannelInterface
0x1800449de  xor     r8d, r8d
0x1800449e1  mov     rdx, r14
0x1800449e4  call    _guard_dispatch_icall
0x1800449e9  mov     ebx, eax
0x1800449eb  test    eax, eax
0x1800449ed  jns     loc_180044B77
0x1800449f3  mov     r9d, 648h
0x1800449f9  jmp     loc_180044B51
0x1800449fe  mov     rdx, [rdx+8]
0x180044a02  lea     rax, GetKeyEncapsulationInterface
0x180044a09  mov     rcx, [rdi+10h]
0x180044a0d  xor     r9d, r9d
0x180044a10  mov     r8, r14
0x180044a13  call    _guard_dispatch_icall
0x180044a18  mov     ebx, eax
0x180044a1a  test    eax, eax
0x180044a1c  jns     loc_180044B77
0x180044a22  mov     r9d, 624h
0x180044a28  jmp     loc_180044B51
0x180044a2d  mov     rdx, [rdx+8]
0x180044a31  lea     rax, GetKeyDerivationInterface
0x180044a38  mov     rcx, [rdi+10h]
0x180044a3c  xor     r9d, r9d
0x180044a3f  mov     r8, r14
0x180044a42  call    _guard_dispatch_icall
0x180044a47  mov     ebx, eax
0x180044a49  test    eax, eax
0x180044a4b  jns     loc_180044B77
0x180044a51  mov     r9d, 617h
0x180044a57  jmp     loc_180044B51
0x180044a5c  mov     rcx, [rdi+10h]
0x180044a60  xor     r8d, r8d
0x180044a63  mov     rdx, r14
0x180044a66  call    GetRngInterface
0x180044a6b  mov     ebx, eax
0x180044a6d  test    eax, eax
0x180044a6f  jns     loc_180044B77
0x180044a75  mov     r9d, 60Ah
0x180044a7b  jmp     loc_180044B51
0x180044a80  mov     rdx, [rdx+8]
0x180044a84  lea     rax, GetSignatureInterface
0x180044a8b  mov     rcx, [rdi+10h]
0x180044a8f  xor     r9d, r9d
0x180044a92  mov     r8, r14
0x180044a95  call    _guard_dispatch_icall
0x180044a9a  mov     ebx, eax
0x180044a9c  test    eax, eax
0x180044a9e  jns     loc_180044B77
0x180044aa4  mov     r9d, 5FEh
0x180044aaa  jmp     loc_180044B51
0x180044aaf  mov     rdx, [rdx+8]
0x180044ab3  lea     rax, GetSecretAgreementInterface
0x180044aba  mov     rcx, [rdi+10h]
0x180044abe  xor     r9d, r9d
0x180044ac1  mov     r8, r14
0x180044ac4  call    _guard_dispatch_icall
0x180044ac9  mov     ebx, eax
0x180044acb  test    eax, eax
0x180044acd  jns     loc_180044B77
0x180044ad3  mov     r9d, 5F1h
0x180044ad9  jmp     short loc_180044B51
0x180044adb  mov     rdx, [rdx+8]
0x180044adf  lea     rax, GetAsymmetricEncryptionInterface
0x180044ae6  mov     rcx, [rdi+10h]
0x180044aea  xor     r9d, r9d
0x180044aed  mov     r8, r14
0x180044af0  call    _guard_dispatch_icall
0x180044af5  mov     ebx, eax
0x180044af7  test    eax, eax
0x180044af9  jns     short loc_180044B77
0x180044afb  mov     r9d, 5E4h
0x180044b01  jmp     short loc_180044B51
0x180044b03  mov     rdx, [rdx+8]
0x180044b07  lea     rax, GetHashInterface
0x180044b0e  mov     rcx, [rdi+10h]
0x180044b12  xor     r9d, r9d
0x180044b15  mov     r8, r14
0x180044b18  call    _guard_dispatch_icall
0x180044b1d  mov     ebx, eax
0x180044b1f  test    eax, eax
0x180044b21  jns     short loc_180044B77
0x180044b23  mov     r9d, 5D7h
0x180044b29  jmp     short loc_180044B51
0x180044b2b  mov     rdx, [rdx+8]
0x180044b2f  lea     rax, GetCipherInterface
0x180044b36  mov     rcx, [rdi+10h]
0x180044b3a  xor     r9d, r9d
0x180044b3d  mov     r8, r14
0x180044b40  call    _guard_dispatch_icall
0x180044b45  mov     ebx, eax
0x180044b47  test    eax, eax
0x180044b49  jns     short loc_180044B77
0x180044b4b  mov     r9d, 5CAh
0x180044b51  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044b58  mov     ecx, ebx
0x180044b5a  mov     r8, rdi
0x180044b5d  lea     rdx, aNtstatus; "ntStatus"
0x180044b64  call    DebugTraceError
0x180044b69  mov     r9d, 6C0h
0x180044b6f  mov     r8, rdi
0x180044b72  jmp     loc_180045064
0x180044b77  mov     eax, [rdi]
0x180044b79  xor     r15d, r15d
0x180044b7c  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044b83  cmp     eax, 6
0x180044b86  ja      loc_180044C61
0x180044b8c  jz      loc_180044C4C
0x180044b92  sub     eax, 1
0x180044b95  jz      short loc_180044C02
0x180044b97  sub     eax, 1
0x180044b9a  jz      short loc_180044BED
0x180044b9c  sub     eax, 1
0x180044b9f  jz      short loc_180044BD8
0x180044ba1  sub     eax, 1
0x180044ba4  jz      short loc_180044BC3
0x180044ba6  cmp     eax, 1
0x180044ba9  jnz     loc_180044C84
0x180044baf  mov     rax, [r14]
0x180044bb2  lea     esi, [r15+1]
0x180044bb6  cmp     si, [rax]
0x180044bb9  jbe     short loc_180044C2F
0x180044bbb  mov     r9d, 568h
0x180044bc1  jmp     short loc_180044C15
0x180044bc3  mov     rax, [r14]
0x180044bc6  mov     esi, 1
0x180044bcb  cmp     si, [rax]
0x180044bce  jbe     short loc_180044C2F
0x180044bd0  mov     r9d, 55Eh
0x180044bd6  jmp     short loc_180044C15
0x180044bd8  mov     rax, [r14]
0x180044bdb  mov     esi, 1
0x180044be0  cmp     si, [rax]
0x180044be3  jbe     short loc_180044C2F
0x180044be5  mov     r9d, 554h
0x180044beb  jmp     short loc_180044C15
0x180044bed  mov     rax, [r14]
0x180044bf0  mov     esi, 1
0x180044bf5  cmp     si, [rax]
0x180044bf8  jbe     short loc_180044C2F
0x180044bfa  mov     r9d, 54Ah
0x180044c00  jmp     short loc_180044C15
0x180044c02  mov     rax, [r14]
0x180044c05  mov     esi, 1
0x180044c0a  cmp     si, [rax]
0x180044c0d  jbe     short loc_180044C2F
0x180044c0f  mov     r9d, 540h
0x180044c15  mov     r8, rdi
0x180044c18  lea     rdx, aNtstatus; "ntStatus"
0x180044c1f  mov     ecx, 0C00000BBh
0x180044c24  mov     r15d, 0C00000BBh
0x180044c2a  call    DebugTraceError
0x180044c2f  mov     ebx, r15d
0x180044c32  test    r15d, r15d
0x180044c35  jns     loc_180045072
0x180044c3b  mov     r9d, 6BBh
0x180044c41  mov     r8, rdi
0x180044c44  mov     ecx, r15d
0x180044c47  jmp     loc_180045066
0x180044c4c  mov     rax, [r14]
0x180044c4f  mov     esi, 1
0x180044c54  cmp     si, [rax]
0x180044c57  jbe     short loc_180044C2F
0x180044c59  mov     r9d, 572h
0x180044c5f  jmp     short loc_180044C15
0x180044c61  sub     eax, 7
0x180044c64  jz      loc_180044D1F
0x180044c6a  sub     eax, 1
0x180044c6d  jz      loc_180044D03
0x180044c73  sub     eax, 0FFF9h
0x180044c78  jz      short loc_180044CE7
0x180044c7a  sub     eax, 1
0x180044c7d  jz      short loc_180044CCB
0x180044c7f  cmp     eax, 2
0x180044c82  jz      short loc_180044CAF
0x180044c84  mov     r9d, 5AAh
0x180044c8a  lea     rdi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044c91  mov     ebx, 0C00000BBh
0x180044c96  mov     r8, rdi
0x180044c99  lea     rdx, aNtstatus; "ntStatus"
0x180044ca0  mov     ecx, 0C00000BBh
0x180044ca5  mov     r15d, ebx
0x180044ca8  call    DebugTraceError
0x180044cad  jmp     short loc_180044C3B
0x180044caf  mov     rax, [r14]
0x180044cb2  mov     esi, 1
0x180044cb7  cmp     si, [rax]
0x180044cba  jbe     loc_180044C2F
0x180044cc0  mov     r9d, 59Ah
0x180044cc6  jmp     loc_180044C15
0x180044ccb  mov     rax, [r14]
0x180044cce  mov     esi, 1
0x180044cd3  cmp     si, [rax]
0x180044cd6  jbe     loc_180044C2F
0x180044cdc  mov     r9d, 5A4h
0x180044ce2  jmp     loc_180044C15
0x180044ce7  mov     rax, [r14]
0x180044cea  mov     esi, 1
0x180044cef  cmp     si, [rax]
0x180044cf2  jbe     loc_180044C2F
0x180044cf8  mov     r9d, 590h
0x180044cfe  jmp     loc_180044C15
0x180044d03  mov     rax, [r14]
0x180044d06  mov     esi, 1
0x180044d0b  cmp     si, [rax]
0x180044d0e  jbe     loc_180044C2F
0x180044d14  mov     r9d, 586h
0x180044d1a  jmp     loc_180044C15
0x180044d1f  mov     rax, [r14]
0x180044d22  mov     esi, 1
0x180044d27  cmp     si, [rax]
0x180044d2a  jbe     loc_180044C2F
0x180044d30  mov     r9d, 57Ch
0x180044d36  jmp     loc_180044C8A
0x180044d3b  sub     eax, 1
0x180044d3e  jz      short loc_180044DBE
0x180044d40  sub     eax, 1
0x180044d43  jz      short loc_180044DB7
0x180044d45  sub     eax, 1
0x180044d48  jz      short loc_180044DB0
0x180044d4a  sub     eax, 1
0x180044d4d  jz      short loc_180044DA9
0x180044d4f  sub     eax, 1
0x180044d52  jz      short loc_180044DA2
0x180044d54  sub     eax, 1
0x180044d57  jz      short loc_180044D9B
0x180044d59  sub     eax, 1
0x180044d5c  jz      short loc_180044D94
0x180044d5e  sub     eax, 1
0x180044d61  jz      short loc_180044D8D
0x180044d63  cmp     eax, 0FFFAh
0x180044d68  jz      short loc_180044D86
0x180044d6a  mov     ebx, 0C00000BBh
0x180044d6f  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044d76  mov     r9d, 6F2h
0x180044d7c  mov     ecx, 0C00000BBh
0x180044d81  jmp     loc_180045066
0x180044d86  mov     ebx, 220023h
0x180044d8b  jmp     short loc_180044DC3
0x180044d8d  mov     ebx, 220027h
  ... truncated ...
```
