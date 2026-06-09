# CDplDuck::Deserialize(uchar *,ulong)

- ea: `0x1800bf914`
- end: `0x1800c0147`
- name: `?Deserialize@CDplDuck@@AEAAJPEAEK@Z`
- size: `2099`
- prototype: `__int64 __fastcall(CDplDuck *__hidden this, unsigned __int8 *Src, size_t Size)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b5d70`

## callees

- `0x180004f86`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800b494c`
- `0x1800bf914`
- `0x1800c7f4c`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bfb40`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bfb40`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bfb20`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bfb20`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bf9f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bf9f2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c0073`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c0088`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c009d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c0073`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c0088`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c009d`
- `bcrypt!BCryptGetProperty` at `0x1800bfcee`
- `bcrypt!BCryptGetProperty` at `0x1800bfdb7`
- `bcrypt!BCryptGetProperty` at `0x1800bfe83`
- `bcrypt!BCryptGetProperty` at `0x1800bfcee`
- `bcrypt!BCryptGetProperty` at `0x1800bfdb7`
- `bcrypt!BCryptGetProperty` at `0x1800bfe83`
- `bcrypt!BCryptSetProperty` at `0x1800bfc80`
- `bcrypt!BCryptSetProperty` at `0x1800bfc80`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800bfc14`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800bfd4b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800bfe17`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800bfc14`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800bfd4b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800bfe17`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfc2a`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfc96`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfd04`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfd61`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfdcd`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfe2d`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfe99`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfc2a`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfc96`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfd04`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfd61`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfdcd`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfe2d`
- `ntdll!RtlNtStatusToDosError` at `0x1800bfe99`

## pseudocode

```c
__int64 __fastcall CDplDuck::Deserialize(CDplUser **this, unsigned __int8 *Src, size_t Size)
{
  size_t v3; // r14
  unsigned __int16 *v6; // rdi
  CDplUser *v7; // r13
  int v8; // r15d
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // ecx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // r9d
  unsigned int v15; // edx
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // edx
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  int v22; // r14d
  signed int v23; // eax
  int v24; // eax
  int v25; // r14d
  signed int v26; // eax
  int Property; // eax
  int v28; // r14d
  signed int v29; // eax
  int v30; // eax
  int v31; // r14d
  signed int v32; // eax
  int v33; // eax
  int v34; // r14d
  signed int v35; // eax
  int v36; // eax
  int v37; // r14d
  signed int v38; // eax
  int v39; // eax
  int v40; // ecx
  int v41; // r14d
  signed int v42; // eax
  char dwFlags; // [rsp+20h] [rbp-49h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-19h] BYREF
  BCRYPT_ALG_HANDLE hObject; // [rsp+58h] [rbp-11h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+60h] [rbp-9h] BYREF
  UCHAR v48[4]; // [rsp+68h] [rbp-1h] BYREF
  UCHAR v49[4]; // [rsp+6Ch] [rbp+3h] BYREF
  int v50; // [rsp+70h] [rbp+7h] BYREF
  DWORD LengthSid; // [rsp+74h] [rbp+Bh]
  void *v52; // [rsp+78h] [rbp+Fh] BYREF
  void *v53; // [rsp+80h] [rbp+17h] BYREF
  ULONG pcbResult; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v55; // [rsp+D8h] [rbp+6Fh] BYREF
  int pbOutput; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = (unsigned int)Size;
  v53 = 0;
  v52 = 0;
  phAlgorithm = 0;
  pbOutput = 0;
  hObject = 0;
  v6 = 0;
  *(_DWORD *)v48 = 0;
  v7 = 0;
  hAlgorithm = 0;
  *(_DWORD *)v49 = 0;
  v8 = 0;
  pcbResult = 0;
  v55 = 0;
  v50 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 28);
  if ( !Src )
  {
    dwFlags = 34;
LABEL_3:
    v9 = -2147024809;
    v10 = -2147024809;
LABEL_97:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 39, dwFlags);
    goto LABEL_98;
  }
  if ( (unsigned int)v3 < 0x20 )
  {
    v8 = 1;
    dwFlags = 39;
    goto LABEL_3;
  }
  if ( !(unsigned int)CDplUser::IsCurrentLockOwner(this[16]) )
  {
    dwFlags = 46;
LABEL_8:
    v9 = -2147418113;
    v10 = -2147418113;
    goto LABEL_97;
  }
  LengthSid = GetLengthSid(*((PSID *)this[16] + 14));
  fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 58);
  v9 = DplibpMemAllocEx(v3, 0, 0, &v53);
  v12 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v9,
          39,
          58);
  v6 = (unsigned __int16 *)v53;
  if ( v12 < 0 )
    goto LABEL_98;
  memcpy_0(v53, Src, v3);
  if ( *v6 < 0x20u || (v13 = v6[2], *v6 > (unsigned __int16)v13) )
  {
    dwFlags = 73;
    goto LABEL_96;
  }
  if ( (unsigned __int16)v13 < 0x20u || !v6[3] )
  {
    dwFlags = 80;
    goto LABEL_96;
  }
  v14 = v6[3];
  if ( (int)v13 + v14 < (unsigned int)v13 )
  {
    dwFlags = 90;
LABEL_96:
    v10 = -2147024809;
    v8 = 1;
    v9 = -2147024809;
    goto LABEL_97;
  }
  v15 = *((_DWORD *)v6 + 2);
  if ( v15 < (int)v13 + v14 || (v16 = *((_DWORD *)v6 + 3)) == 0 )
  {
    dwFlags = 97;
    goto LABEL_96;
  }
  v17 = v15 + v16;
  if ( v17 < v15 )
  {
    dwFlags = 107;
    goto LABEL_96;
  }
  v18 = v6[1];
  if ( v17 > v18 || v17 > (unsigned int)v3 || v18 > (unsigned int)v3 )
  {
    dwFlags = 115;
    goto LABEL_96;
  }
  if ( LengthSid != v14 || !IsValidSid((char *)v6 + v13) )
  {
    dwFlags = 127;
    goto LABEL_96;
  }
  if ( !EqualSid(*((PSID *)this[16] + 14), (char *)v6 + v6[2]) )
  {
    dwFlags = -117;
    goto LABEL_96;
  }
  if ( *((_QWORD *)v6 + 3) <= (unsigned __int64)this[14] )
  {
    v9 = 1;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 39, 152);
    goto LABEL_98;
  }
  fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 164);
  v9 = DplibpMemAllocEx(*((unsigned int *)v6 + 3), 0, 0, &v52);
  v20 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v9,
          39,
          164);
  v7 = (CDplUser *)v52;
  if ( v20 >= 0 )
  {
    memcpy_0(v52, (char *)v6 + *((unsigned int *)v6 + 2), *((unsigned int *)v6 + 3));
    v21 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
    v22 = v21;
    if ( v21 )
    {
      v9 = 0;
      if ( v21 < 0 )
      {
        v23 = RtlNtStatusToDosError(v21);
        v9 = v23;
        if ( !v23 || v23 == 317 )
        {
          v9 = v22 | 0x10000000;
        }
        else if ( v23 > 0 )
        {
          v9 = (unsigned __int16)v23 | 0x80070000;
        }
      }
      dwFlags = -78;
    }
    else
    {
      v24 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
      v25 = v24;
      if ( v24 )
      {
        v9 = 0;
        if ( v24 < 0 )
        {
          v26 = RtlNtStatusToDosError(v24);
          v9 = v26;
          if ( !v26 || v26 == 317 )
          {
            v9 = v25 | 0x10000000;
          }
          else if ( v26 > 0 )
          {
            v9 = (unsigned __int16)v26 | 0x80070000;
          }
        }
        dwFlags = -67;
      }
      else
      {
        Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
        v28 = Property;
        if ( Property )
        {
          v9 = 0;
          if ( Property < 0 )
          {
            v29 = RtlNtStatusToDosError(Property);
            v9 = v29;
            if ( !v29 || v29 == 317 )
            {
              v9 = v28 | 0x10000000;
            }
            else if ( v29 > 0 )
            {
              v9 = (unsigned __int16)v29 | 0x80070000;
            }
          }
          dwFlags = -55;
        }
        else
        {
          v30 = BCryptOpenAlgorithmProvider(&hObject, L"SP800_108_CTR_HMAC", 0, 0);
          v31 = v30;
          if ( v30 )
          {
            v9 = 0;
            if ( v30 < 0 )
            {
              v32 = RtlNtStatusToDosError(v30);
              v9 = v32;
              if ( !v32 || v32 == 317 )
              {
                v9 = v31 | 0x10000000;
              }
              else if ( v32 > 0 )
              {
                v9 = (unsigned __int16)v32 | 0x80070000;
              }
            }
            dwFlags = -41;
          }
          else
          {
            v33 = BCryptGetProperty(hObject, L"ObjectLength", v48, 4u, &pcbResult, 0);
            v34 = v33;
            if ( v33 )
            {
              v9 = 0;
              if ( v33 < 0 )
              {
                v35 = RtlNtStatusToDosError(v33);
                v9 = v35;
                if ( !v35 || v35 == 317 )
                {
                  v9 = v34 | 0x10000000;
                }
                else if ( v35 > 0 )
                {
                  v9 = (unsigned __int16)v35 | 0x80070000;
                }
              }
              dwFlags = -29;
            }
            else
            {
              v36 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"SHA256", 0, 8u);
              v37 = v36;
              if ( v36 )
              {
                v9 = 0;
                if ( v36 < 0 )
                {
                  v38 = RtlNtStatusToDosError(v36);
                  v9 = v38;
                  if ( !v38 || v38 == 317 )
                  {
                    v9 = v37 | 0x10000000;
                  }
                  else if ( v38 > 0 )
                  {
                    v9 = (unsigned __int16)v38 | 0x80070000;
                  }
                }
                dwFlags = -15;
              }
              else
              {
                v39 = BCryptGetProperty(hAlgorithm, L"ObjectLength", v49, 4u, &pcbResult, 0);
                v41 = v39;
                if ( !v39 )
                {
                  fnEfsLogTrace1Strings(v40, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 12);
                  v9 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, CDplUser *, _DWORD, _QWORD, _DWORD, unsigned int *, int *))this[2]
                        + 12))(
                         0,
                         0,
                         *((_QWORD *)this[16] + 13),
                         v7,
                         *((_DWORD *)v6 + 3),
                         0,
                         0,
                         &v55,
                         &v50);
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              v9,
                              39,
                              12) < 0 )
                    goto LABEL_98;
                  if ( ((v55 + 15) & 0xFFFFFFF0) >= v55 )
                  {
                    CDplDuck::ReleaseKeyMaterial((CDplDuck *)this);
                    this[4] = (CDplUser *)phAlgorithm;
                    *((_DWORD *)this + 10) = pbOutput;
                    this[6] = (CDplUser *)hObject;
                    *((_DWORD *)this + 14) = *(_DWORD *)v48;
                    this[8] = (CDplUser *)hAlgorithm;
                    *((_DWORD *)this + 18) = *(_DWORD *)v49;
                    this[10] = v7;
                    v7 = 0;
                    phAlgorithm = 0;
                    hObject = 0;
                    hAlgorithm = 0;
                    *((_DWORD *)this + 22) = *((_DWORD *)v6 + 3);
                    *((_DWORD *)this + 31) = v50;
                    this[3] = (CDplUser *)*((_QWORD *)v6 + 2);
                    this[14] = (CDplUser *)*((_QWORD *)v6 + 3);
                    *((_DWORD *)this + 30) = 0;
                    goto LABEL_98;
                  }
                  dwFlags = 15;
                  goto LABEL_8;
                }
                v9 = 0;
                if ( v39 < 0 )
                {
                  v42 = RtlNtStatusToDosError(v39);
                  v9 = v42;
                  if ( !v42 || v42 == 317 )
                  {
                    v9 = v41 | 0x10000000;
                  }
                  else if ( v42 > 0 )
                  {
                    v9 = (unsigned __int16)v42 | 0x80070000;
                  }
                }
                dwFlags = -3;
              }
            }
          }
        }
      }
    }
    v10 = v9;
    goto LABEL_97;
  }
LABEL_98:
  if ( v7 )
    DplibMemFree(v7);
  if ( v6 )
    DplibMemFree(v6);
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( hObject )
  {
    BCryptCloseAlgorithmProvider(hObject, 0);
    hObject = 0;
  }
  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  if ( v8 )
  {
    v9 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, -2147024809, 39, 72);
  }
  else if ( v9 == -2147024809 )
  {
    v9 = -2147467259;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, -2147467259, 39, 78);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v9,
    39,
    82);
  return v9;
}

```

## disassembly

```asm
0x1800bf914  mov     [rsp-8+arg_10], rbx
0x1800bf919  push    rbp
0x1800bf91a  push    rsi
0x1800bf91b  push    rdi
0x1800bf91c  push    r12
0x1800bf91e  push    r13
0x1800bf920  push    r14
0x1800bf922  push    r15
0x1800bf924  lea     rbp, [rsp-27h]
0x1800bf929  sub     rsp, 90h
0x1800bf930  xor     ebx, ebx
0x1800bf932  mov     r14d, r8d
0x1800bf935  mov     r12, rdx
0x1800bf938  mov     [rbp+57h+var_40], rbx
0x1800bf93c  lea     r8, sourceString
0x1800bf943  mov     [rbp+57h+var_48], rbx
0x1800bf947  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800bf94e  mov     [rbp+57h+phAlgorithm], rbx
0x1800bf952  lea     r9d, [rbx+27h]
0x1800bf956  mov     [rbp+57h+pbOutput], ebx
0x1800bf959  mov     rsi, rcx
0x1800bf95c  mov     [rbp+57h+hObject], rbx
0x1800bf960  mov     edi, ebx
0x1800bf962  mov     dword ptr [rbp+57h+var_58], ebx
0x1800bf965  mov     r13d, ebx
0x1800bf968  mov     [rbp+57h+hAlgorithm], rbx
0x1800bf96c  mov     dword ptr [rbp+57h+var_54], ebx
0x1800bf96f  mov     r15d, ebx
0x1800bf972  mov     [rbp+57h+pcbResult], ebx
0x1800bf975  mov     [rbp+57h+arg_8], ebx
0x1800bf978  mov     [rbp+57h+var_50], ebx
0x1800bf97b  mov     [rsp+0C0h+dwFlags], 1B1Ch
0x1800bf983  call    fnEfsLogTrace1Strings
0x1800bf988  mov     eax, 80070057h
0x1800bf98d  mov     ecx, 80070057h
0x1800bf992  test    r12, r12
0x1800bf995  jnz     short loc_1800BF9A9
0x1800bf997  mov     [rsp+0C0h+dwFlags], 1B22h
0x1800bf99f  mov     ebx, eax
0x1800bf9a1  mov     r8d, ecx
0x1800bf9a4  jmp     loc_1800C0033
0x1800bf9a9  cmp     r14d, 20h ; ' '
0x1800bf9ad  jnb     short loc_1800BF9BF
0x1800bf9af  mov     r15d, 1
0x1800bf9b5  mov     [rsp+0C0h+dwFlags], 1B27h
0x1800bf9bd  jmp     short loc_1800BF99F
0x1800bf9bf  mov     rcx, [rsi+80h]; this
0x1800bf9c6  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800bf9cb  test    eax, eax
0x1800bf9cd  jnz     short loc_1800BF9E7
0x1800bf9cf  mov     [rsp+0C0h+dwFlags], 1B2Eh
0x1800bf9d7  mov     ebx, 8000FFFFh
0x1800bf9dc  mov     r8d, 8000FFFFh
0x1800bf9e2  jmp     loc_1800C0033
0x1800bf9e7  mov     rcx, [rsi+80h]
0x1800bf9ee  mov     rcx, [rcx+70h]; pSid
0x1800bf9f2  call    cs:__imp_GetLengthSid
0x1800bf9f8  mov     r9d, 27h ; '''
0x1800bf9fe  mov     [rsp+0C0h+dwFlags], 1B3Ah
0x1800bfa06  lea     r8, sourceString
0x1800bfa0d  mov     [rbp+57h+var_4C], eax
0x1800bfa10  lea     rdx, EFS_TRACE_START_EVENT
0x1800bfa17  call    fnEfsLogTrace1Strings
0x1800bfa1c  lea     r9, [rbp+57h+var_40]
0x1800bfa20  xor     r8d, r8d
0x1800bfa23  xor     edx, edx
0x1800bfa25  mov     rcx, r14
0x1800bfa28  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800bfa2d  mov     rcx, cs:g_hPublisher
0x1800bfa34  lea     r9, sourceString
0x1800bfa3b  mov     [rsp+0C0h+var_90], 1B3Ah
0x1800bfa43  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bfa4a  mov     [rsp+0C0h+var_98], 27h ; '''
0x1800bfa52  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bfa59  mov     [rsp+0C0h+dwFlags], eax
0x1800bfa5d  mov     ebx, eax
0x1800bfa5f  call    fnEfsLogTrace1String1Dword
0x1800bfa64  mov     rdi, [rbp+57h+var_40]
0x1800bfa68  test    eax, eax
0x1800bfa6a  js      loc_1800C004C
0x1800bfa70  mov     r8, r14; Size
0x1800bfa73  mov     rdx, r12; Src
0x1800bfa76  mov     rcx, rdi; void *
0x1800bfa79  call    memcpy_0
0x1800bfa7e  mov     eax, 20h ; ' '
0x1800bfa83  cmp     [rdi], ax
0x1800bfa86  jb      loc_1800C001A
0x1800bfa8c  movzx   ecx, word ptr [rdi+4]
0x1800bfa90  cmp     [rdi], cx
0x1800bfa93  ja      loc_1800C001A
0x1800bfa99  cmp     cx, ax
0x1800bfa9c  jb      loc_1800C0010
0x1800bfaa2  xor     r12d, r12d
0x1800bfaa5  cmp     [rdi+6], r12w
0x1800bfaaa  jz      loc_1800C0010
0x1800bfab0  movzx   r9d, word ptr [rdi+6]
0x1800bfab5  lea     r8d, [rcx+r9]
0x1800bfab9  cmp     r8d, ecx
0x1800bfabc  jnb     short loc_1800BFACB
0x1800bfabe  mov     [rsp+0C0h+dwFlags], 1B5Ah
0x1800bfac6  jmp     loc_1800C0022
0x1800bfacb  mov     edx, [rdi+8]
0x1800bface  cmp     edx, r8d
0x1800bfad1  jb      loc_1800C0006
0x1800bfad7  mov     eax, [rdi+0Ch]
0x1800bfada  test    eax, eax
0x1800bfadc  jz      loc_1800C0006
0x1800bfae2  add     eax, edx
0x1800bfae4  cmp     eax, edx
0x1800bfae6  jnb     short loc_1800BFAF5
0x1800bfae8  mov     [rsp+0C0h+dwFlags], 1B6Bh
0x1800bfaf0  jmp     loc_1800C0022
0x1800bfaf5  movzx   edx, word ptr [rdi+2]
0x1800bfaf9  cmp     eax, edx
0x1800bfafb  ja      loc_1800BFFFC
0x1800bfb01  cmp     eax, r14d
0x1800bfb04  ja      loc_1800BFFFC
0x1800bfb0a  cmp     edx, r14d
0x1800bfb0d  ja      loc_1800BFFFC
0x1800bfb13  cmp     [rbp+57h+var_4C], r9d
0x1800bfb17  jnz     loc_1800BFFF2
0x1800bfb1d  add     rcx, rdi; pSid
0x1800bfb20  call    cs:__imp_IsValidSid
0x1800bfb26  test    eax, eax
0x1800bfb28  jz      loc_1800BFFF2
0x1800bfb2e  mov     rcx, [rsi+80h]
0x1800bfb35  movzx   edx, word ptr [rdi+4]
0x1800bfb39  add     rdx, rdi; pSid2
0x1800bfb3c  mov     rcx, [rcx+70h]; pSid1
0x1800bfb40  call    cs:__imp_EqualSid
0x1800bfb46  test    eax, eax
0x1800bfb48  jnz     short loc_1800BFB57
0x1800bfb4a  mov     [rsp+0C0h+dwFlags], 1B8Bh
0x1800bfb52  jmp     loc_1800C0022
0x1800bfb57  mov     rax, [rsi+70h]
0x1800bfb5b  mov     r9d, 27h ; '''
0x1800bfb61  cmp     [rdi+18h], rax
0x1800bfb65  ja      short loc_1800BFB82
0x1800bfb67  lea     ebx, [r9-26h]
0x1800bfb6b  mov     [rsp+0C0h+dwFlags], 1B98h
0x1800bfb73  mov     r8d, ebx
0x1800bfb76  lea     rdx, EFS_TRACE_STATUS
0x1800bfb7d  jmp     loc_1800C0040
0x1800bfb82  mov     r14d, 1BA4h
0x1800bfb88  lea     r8, sourceString
0x1800bfb8f  lea     rdx, EFS_TRACE_START_EVENT
0x1800bfb96  mov     [rsp+0C0h+dwFlags], r14d
0x1800bfb9b  call    fnEfsLogTrace1Strings
0x1800bfba0  mov     ecx, [rdi+0Ch]
0x1800bfba3  lea     r9, [rbp+57h+var_48]
0x1800bfba7  xor     r8d, r8d
0x1800bfbaa  xor     edx, edx
0x1800bfbac  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800bfbb1  mov     rcx, cs:g_hPublisher
0x1800bfbb8  lea     r9, sourceString
0x1800bfbbf  mov     [rsp+0C0h+var_90], r14d
0x1800bfbc4  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bfbcb  mov     [rsp+0C0h+var_98], 27h ; '''
0x1800bfbd3  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bfbda  mov     [rsp+0C0h+dwFlags], eax
0x1800bfbde  mov     ebx, eax
0x1800bfbe0  call    fnEfsLogTrace1String1Dword
0x1800bfbe5  mov     r13, [rbp+57h+var_48]
0x1800bfbe9  test    eax, eax
0x1800bfbeb  js      loc_1800C004C
0x1800bfbf1  mov     edx, [rdi+8]
0x1800bfbf4  mov     rcx, r13; void *
0x1800bfbf7  mov     r8d, [rdi+0Ch]; Size
0x1800bfbfb  add     rdx, rdi; Src
0x1800bfbfe  call    memcpy_0
0x1800bfc03  xor     r9d, r9d; dwFlags
0x1800bfc06  lea     rdx, pszAlgId; "AES"
0x1800bfc0d  xor     r8d, r8d; pszImplementation
0x1800bfc10  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800bfc14  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800bfc1a  mov     r14d, eax
0x1800bfc1d  test    eax, eax
0x1800bfc1f  jz      short loc_1800BFC63
0x1800bfc21  mov     ebx, r12d
0x1800bfc24  test    eax, eax
0x1800bfc26  jns     short loc_1800BFC53
0x1800bfc28  mov     ecx, eax; Status
0x1800bfc2a  call    cs:__imp_RtlNtStatusToDosError
0x1800bfc30  mov     ebx, eax
0x1800bfc32  test    eax, eax
0x1800bfc34  jz      short loc_1800BFC4C
0x1800bfc36  cmp     eax, 13Dh
0x1800bfc3b  jz      short loc_1800BFC4C
0x1800bfc3d  test    eax, eax
0x1800bfc3f  jle     short loc_1800BFC53
0x1800bfc41  movzx   ebx, ax
0x1800bfc44  or      ebx, 80070000h
0x1800bfc4a  jmp     short loc_1800BFC53
0x1800bfc4c  mov     ebx, r14d
0x1800bfc4f  bts     ebx, 1Ch
0x1800bfc53  mov     [rsp+0C0h+dwFlags], 1BB2h
0x1800bfc5b  mov     r8d, ebx
0x1800bfc5e  jmp     loc_1800C0033
0x1800bfc63  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800bfc67  lea     r8, pbInput; "ChainingModeCBC"
0x1800bfc6e  mov     r9d, 20h ; ' '; cbInput
0x1800bfc74  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x1800bfc79  lea     rdx, aChainingmode; "ChainingMode"
0x1800bfc80  call    cs:__imp_BCryptSetProperty
0x1800bfc86  mov     r14d, eax
0x1800bfc89  test    eax, eax
0x1800bfc8b  jz      short loc_1800BFCC9
0x1800bfc8d  mov     ebx, r12d
0x1800bfc90  test    eax, eax
0x1800bfc92  jns     short loc_1800BFCBF
0x1800bfc94  mov     ecx, eax; Status
0x1800bfc96  call    cs:__imp_RtlNtStatusToDosError
0x1800bfc9c  mov     ebx, eax
0x1800bfc9e  test    eax, eax
0x1800bfca0  jz      short loc_1800BFCB8
0x1800bfca2  cmp     eax, 13Dh
0x1800bfca7  jz      short loc_1800BFCB8
0x1800bfca9  test    eax, eax
0x1800bfcab  jle     short loc_1800BFCBF
0x1800bfcad  movzx   ebx, ax
0x1800bfcb0  or      ebx, 80070000h
0x1800bfcb6  jmp     short loc_1800BFCBF
0x1800bfcb8  mov     ebx, r14d
0x1800bfcbb  bts     ebx, 1Ch
0x1800bfcbf  mov     [rsp+0C0h+dwFlags], 1BBDh
0x1800bfcc7  jmp     short loc_1800BFC5B
0x1800bfcc9  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800bfccd  lea     rax, [rbp+57h+pcbResult]
0x1800bfcd1  mov     ebx, 4
0x1800bfcd6  mov     [rsp+0C0h+var_98], r12d; dwFlags
0x1800bfcdb  mov     r9d, ebx; cbOutput
0x1800bfcde  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbResult
0x1800bfce3  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800bfce7  lea     rdx, aObjectlength; "ObjectLength"
0x1800bfcee  call    cs:__imp_BCryptGetProperty
0x1800bfcf4  mov     r14d, eax
0x1800bfcf7  test    eax, eax
0x1800bfcf9  jz      short loc_1800BFD3A
0x1800bfcfb  mov     ebx, r12d
0x1800bfcfe  test    eax, eax
0x1800bfd00  jns     short loc_1800BFD2D
0x1800bfd02  mov     ecx, eax; Status
0x1800bfd04  call    cs:__imp_RtlNtStatusToDosError
0x1800bfd0a  mov     ebx, eax
0x1800bfd0c  test    eax, eax
0x1800bfd0e  jz      short loc_1800BFD26
0x1800bfd10  cmp     eax, 13Dh
0x1800bfd15  jz      short loc_1800BFD26
0x1800bfd17  test    eax, eax
0x1800bfd19  jle     short loc_1800BFD2D
0x1800bfd1b  movzx   ebx, ax
0x1800bfd1e  or      ebx, 80070000h
0x1800bfd24  jmp     short loc_1800BFD2D
0x1800bfd26  mov     ebx, r14d
0x1800bfd29  bts     ebx, 1Ch
0x1800bfd2d  mov     [rsp+0C0h+dwFlags], 1BC9h
0x1800bfd35  jmp     loc_1800BFC5B
0x1800bfd3a  xor     r9d, r9d; dwFlags
0x1800bfd3d  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x1800bfd44  xor     r8d, r8d; pszImplementation
0x1800bfd47  lea     rcx, [rbp+57h+hObject]; phAlgorithm
0x1800bfd4b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800bfd51  mov     r14d, eax
0x1800bfd54  test    eax, eax
0x1800bfd56  jz      short loc_1800BFD97
0x1800bfd58  mov     ebx, r12d
0x1800bfd5b  test    eax, eax
0x1800bfd5d  jns     short loc_1800BFD8A
0x1800bfd5f  mov     ecx, eax; Status
0x1800bfd61  call    cs:__imp_RtlNtStatusToDosError
0x1800bfd67  mov     ebx, eax
0x1800bfd69  test    eax, eax
0x1800bfd6b  jz      short loc_1800BFD83
0x1800bfd6d  cmp     eax, 13Dh
0x1800bfd72  jz      short loc_1800BFD83
0x1800bfd74  test    eax, eax
0x1800bfd76  jle     short loc_1800BFD8A
0x1800bfd78  movzx   ebx, ax
0x1800bfd7b  or      ebx, 80070000h
0x1800bfd81  jmp     short loc_1800BFD8A
0x1800bfd83  mov     ebx, r14d
0x1800bfd86  bts     ebx, 1Ch
0x1800bfd8a  mov     [rsp+0C0h+dwFlags], 1BD7h
0x1800bfd92  jmp     loc_1800BFC5B
0x1800bfd97  mov     rcx, [rbp+57h+hObject]; hObject
0x1800bfd9b  lea     rax, [rbp+57h+pcbResult]
0x1800bfd9f  mov     [rsp+0C0h+var_98], r12d; dwFlags
0x1800bfda4  lea     r8, [rbp+57h+var_58]; pbOutput
0x1800bfda8  mov     r9d, ebx; cbOutput
0x1800bfdab  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbResult
0x1800bfdb0  lea     rdx, aObjectlength; "ObjectLength"
0x1800bfdb7  call    cs:__imp_BCryptGetProperty
0x1800bfdbd  mov     r14d, eax
0x1800bfdc0  test    eax, eax
0x1800bfdc2  jz      short loc_1800BFE03
0x1800bfdc4  mov     ebx, r12d
0x1800bfdc7  test    eax, eax
0x1800bfdc9  jns     short loc_1800BFDF6
0x1800bfdcb  mov     ecx, eax; Status
0x1800bfdcd  call    cs:__imp_RtlNtStatusToDosError
  ... truncated ...
```
