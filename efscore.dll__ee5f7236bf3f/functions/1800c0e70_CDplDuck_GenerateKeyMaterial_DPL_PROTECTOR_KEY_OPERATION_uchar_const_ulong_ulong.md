# CDplDuck::GenerateKeyMaterial(_DPL_PROTECTOR_KEY_OPERATION,uchar const *,ulong,ulong)

- ea: `0x1800c0e70`
- end: `0x1800c1779`
- name: `?GenerateKeyMaterial@CDplDuck@@AEAAJW4_DPL_PROTECTOR_KEY_OPERATION@@PEBEKK@Z`
- size: `2313`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009975c`
- `0x1800b0e7c`

## callees

- `0x180004f86`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800b494c`
- `0x1800c0e70`
- `0x1800c7f4c`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c145c`
- `CRYPT32!CryptUnprotectMemory` at `0x1800c135d`
- `CRYPT32!CryptUnprotectMemory` at `0x1800c135d`
- `CRYPT32!CryptProtectMemory` at `0x1800c1450`
- `CRYPT32!CryptProtectMemory` at `0x1800c1450`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c16a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c16a6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c16e7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c1700`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c1719`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c16e7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c1700`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c1719`
- `bcrypt!BCryptGetProperty` at `0x1800c107f`
- `bcrypt!BCryptGetProperty` at `0x1800c1144`
- `bcrypt!BCryptGetProperty` at `0x1800c120c`
- `bcrypt!BCryptGetProperty` at `0x1800c107f`
- `bcrypt!BCryptGetProperty` at `0x1800c1144`
- `bcrypt!BCryptGetProperty` at `0x1800c120c`
- `bcrypt!BCryptSetProperty` at `0x1800c1017`
- `bcrypt!BCryptSetProperty` at `0x1800c1017`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c0faf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c10d9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c11a1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c0faf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c10d9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c11a1`
- `bcrypt!BCryptGenRandom` at `0x1800c13c6`
- `bcrypt!BCryptGenRandom` at `0x1800c13c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0fc2`
- `ntdll!RtlNtStatusToDosError` at `0x1800c102a`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1092`
- `ntdll!RtlNtStatusToDosError` at `0x1800c10ec`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1157`
- `ntdll!RtlNtStatusToDosError` at `0x1800c11b4`
- `ntdll!RtlNtStatusToDosError` at `0x1800c121f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c13db`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0fc2`
- `ntdll!RtlNtStatusToDosError` at `0x1800c102a`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1092`
- `ntdll!RtlNtStatusToDosError` at `0x1800c10ec`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1157`
- `ntdll!RtlNtStatusToDosError` at `0x1800c11b4`
- `ntdll!RtlNtStatusToDosError` at `0x1800c121f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c13db`

## pseudocode

```c
__int64 __fastcall CDplDuck::GenerateKeyMaterial(__int64 a1, __int64 a2, void *a3, unsigned int a4, ULONG cbBuffer)
{
  size_t v5; // r13
  PUCHAR v8; // rsi
  void *v9; // r14
  ULONG v10; // r15d
  unsigned int v11; // ebx
  int v12; // ebx
  int v13; // r8d
  int v14; // eax
  int v15; // r12d
  signed int v16; // eax
  int v17; // eax
  int v18; // r12d
  signed int v19; // eax
  int Property; // eax
  int v21; // r12d
  signed int v22; // eax
  int v23; // eax
  int v24; // r12d
  signed int v25; // eax
  int v26; // eax
  int v27; // r12d
  signed int v28; // eax
  int v29; // eax
  int v30; // r12d
  signed int v31; // eax
  int v32; // eax
  int v33; // ecx
  int v34; // r12d
  signed int v35; // eax
  __int64 v36; // r12
  int v37; // ecx
  signed int LastError; // eax
  PUCHAR v39; // rdx
  void *v40; // rcx
  int v41; // eax
  int v42; // r14d
  signed int v43; // eax
  int v44; // ecx
  signed int v45; // eax
  int v46; // ecx
  PUCHAR v47; // rax
  __int64 v48; // rax
  DWORD dwHighDateTime; // ecx
  char dwFlags; // [rsp+28h] [rbp-61h]
  DWORD cbDataIn; // [rsp+58h] [rbp-31h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-29h] BYREF
  PUCHAR pbBuffer; // [rsp+68h] [rbp-21h] BYREF
  BCRYPT_ALG_HANDLE hObject; // [rsp+70h] [rbp-19h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp-11h] BYREF
  UCHAR pbOutput[4]; // [rsp+80h] [rbp-9h] BYREF
  UCHAR v58[4]; // [rsp+84h] [rbp-5h] BYREF
  UCHAR v59[4]; // [rsp+88h] [rbp-1h] BYREF
  int v60; // [rsp+8Ch] [rbp+3h] BYREF
  void *pDataIn; // [rsp+90h] [rbp+7h] BYREF
  __int64 v62; // [rsp+98h] [rbp+Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp+17h] BYREF
  ULONG pcbResult; // [rsp+E8h] [rbp+5Fh] BYREF
  unsigned int v65; // [rsp+F0h] [rbp+67h] BYREF
  void *Src; // [rsp+F8h] [rbp+6Fh]

  Src = a3;
  v5 = a4;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  hObject = 0;
  *(_DWORD *)v58 = 0;
  v65 = 32;
  hAlgorithm = 0;
  *(_DWORD *)v59 = 0;
  v8 = 0;
  pbBuffer = 0;
  v9 = 0;
  pDataIn = 0;
  v62 = 0;
  pcbResult = 0;
  SystemTimeAsFileTime = 0;
  v60 = 0;
  fnEfsLogTrace1Strings(a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 59);
  if ( a3 )
  {
    if ( !(_DWORD)v5 || (v10 = cbBuffer) == 0 || (unsigned int)v5 < cbBuffer )
    {
      v12 = -2147024809;
      dwFlags = 71;
      v13 = -2147024809;
LABEL_7:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 39, dwFlags);
      goto LABEL_103;
    }
    v11 = v5;
  }
  else
  {
    v10 = 32;
    v11 = 32;
  }
  cbDataIn = v11;
  if ( !(unsigned int)CDplUser::IsCurrentLockOwner(*(CDplUser **)(a1 + 128)) )
  {
    dwFlags = 82;
LABEL_11:
    v12 = -2147418113;
    v13 = -2147418113;
    goto LABEL_7;
  }
  if ( v11 < v10 )
  {
    dwFlags = 84;
    goto LABEL_11;
  }
  v12 = 0;
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 16) + 88LL) )
  {
    dwFlags = 85;
    goto LABEL_11;
  }
  v14 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  v15 = v14;
  if ( v14 )
  {
    if ( v14 < 0 )
    {
      v16 = RtlNtStatusToDosError(v14);
      v12 = v16;
      if ( !v16 || v16 == 317 )
      {
        v12 = v15 | 0x10000000;
      }
      else if ( v16 > 0 )
      {
        v12 = (unsigned __int16)v16 | 0x80070000;
      }
    }
    dwFlags = 95;
    goto LABEL_24;
  }
  v17 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  v18 = v17;
  if ( v17 )
  {
    if ( v17 < 0 )
    {
      v19 = RtlNtStatusToDosError(v17);
      v12 = v19;
      if ( !v19 || v19 == 317 )
      {
        v12 = v18 | 0x10000000;
      }
      else if ( v19 > 0 )
      {
        v12 = (unsigned __int16)v19 | 0x80070000;
      }
    }
    dwFlags = 106;
    goto LABEL_24;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v21 = Property;
  if ( Property )
  {
    if ( Property < 0 )
    {
      v22 = RtlNtStatusToDosError(Property);
      v12 = v22;
      if ( !v22 || v22 == 317 )
      {
        v12 = v21 | 0x10000000;
      }
      else if ( v22 > 0 )
      {
        v12 = (unsigned __int16)v22 | 0x80070000;
      }
    }
    dwFlags = 118;
    goto LABEL_24;
  }
  v23 = BCryptOpenAlgorithmProvider(&hObject, L"SP800_108_CTR_HMAC", 0, 0);
  v24 = v23;
  if ( v23 )
  {
    if ( v23 < 0 )
    {
      v25 = RtlNtStatusToDosError(v23);
      v12 = v25;
      if ( !v25 || v25 == 317 )
      {
        v12 = v24 | 0x10000000;
      }
      else if ( v25 > 0 )
      {
        v12 = (unsigned __int16)v25 | 0x80070000;
      }
    }
    dwFlags = -124;
    goto LABEL_24;
  }
  v26 = BCryptGetProperty(hObject, L"ObjectLength", v58, 4u, &pcbResult, 0);
  v27 = v26;
  if ( v26 )
  {
    if ( v26 < 0 )
    {
      v28 = RtlNtStatusToDosError(v26);
      v12 = v28;
      if ( !v28 || v28 == 317 )
      {
        v12 = v27 | 0x10000000;
      }
      else if ( v28 > 0 )
      {
        v12 = (unsigned __int16)v28 | 0x80070000;
      }
    }
    dwFlags = -112;
    goto LABEL_24;
  }
  v29 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"SHA256", 0, 8u);
  v30 = v29;
  if ( v29 )
  {
    if ( v29 < 0 )
    {
      v31 = RtlNtStatusToDosError(v29);
      v12 = v31;
      if ( !v31 || v31 == 317 )
      {
        v12 = v30 | 0x10000000;
      }
      else if ( v31 > 0 )
      {
        v12 = (unsigned __int16)v31 | 0x80070000;
      }
    }
    dwFlags = -98;
    goto LABEL_24;
  }
  v32 = BCryptGetProperty(hAlgorithm, L"ObjectLength", v59, 4u, &pcbResult, 0);
  v34 = v32;
  if ( v32 )
  {
    if ( v32 < 0 )
    {
      v35 = RtlNtStatusToDosError(v32);
      v12 = v35;
      if ( !v35 || v35 == 317 )
      {
        v12 = v34 | 0x10000000;
      }
      else if ( v35 > 0 )
      {
        v12 = (unsigned __int16)v35 | 0x80070000;
      }
    }
    dwFlags = -86;
    goto LABEL_24;
  }
  fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 180);
  v36 = v10;
  v12 = DplibpMemAllocEx(v10, 1, 1, &pbBuffer);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v12,
              39,
              180) < 0 )
    goto LABEL_102;
  fnEfsLogTrace1Strings(v37, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 185);
  v12 = DplibpMemAllocEx(cbDataIn, 1, 1, &pDataIn);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v12,
              39,
              185) < 0 )
  {
    v9 = pDataIn;
LABEL_102:
    v8 = pbBuffer;
    goto LABEL_103;
  }
  if ( Src )
  {
    v9 = pDataIn;
    memcpy_0(pDataIn, Src, v5);
    if ( !CryptUnprotectMemory(v9, cbDataIn, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 39, 203);
      goto LABEL_102;
    }
    v8 = pbBuffer;
    v39 = (PUCHAR)v9;
    v40 = pbBuffer;
  }
  else
  {
    v8 = pbBuffer;
    v41 = BCryptGenRandom(0, pbBuffer, v10, 2u);
    v42 = v41;
    if ( v41 )
    {
      v12 = 0;
      if ( v41 < 0 )
      {
        v43 = RtlNtStatusToDosError(v41);
        v12 = v43;
        if ( !v43 || v43 == 317 )
        {
          v12 = v42 | 0x10000000;
        }
        else if ( v43 > 0 )
        {
          v12 = (unsigned __int16)v43 | 0x80070000;
        }
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 39, 225);
      v9 = pDataIn;
      goto LABEL_103;
    }
    v9 = pDataIn;
    v39 = v8;
    v40 = pDataIn;
  }
  memcpy_0(v40, v39, v10);
  if ( !CryptProtectMemory(v9, cbDataIn, 0) )
  {
    v45 = GetLastError();
    v12 = v45;
    if ( v45 > 0 )
      v12 = (unsigned __int16)v45 | 0x80070000;
    dwFlags = -13;
    goto LABEL_24;
  }
  fnEfsLogTrace1Strings(v44, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 1);
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, PUCHAR, _QWORD, _QWORD, _DWORD, unsigned int *, _QWORD))(*(_QWORD *)(a1 + 16) + 88LL))(
          *(_QWORD *)(*(_QWORD *)(a1 + 128) + 104LL),
          1,
          v8,
          v10,
          0,
          0,
          &v65,
          0);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v12,
              39,
              1) >= 0 )
  {
    fnEfsLogTrace1Strings(v46, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 10);
    v12 = DplibpMemAllocEx(v65, 0, 0, &v62);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v12,
                39,
                10) >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, PUCHAR, _QWORD, __int64, unsigned int, unsigned int *, int *))(*(_QWORD *)(a1 + 16) + 88LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 128) + 104LL),
              1,
              v8,
              v10,
              v62,
              v65,
              &v65,
              &v60);
      v47 = v8;
      if ( v10 )
      {
        do
        {
          *v47++ = 0;
          --v36;
        }
        while ( v36 );
      }
      if ( v12 < 0 )
      {
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
          (unsigned int)L"Failed to protect DUCK",
          v12,
          39,
          29);
        dwFlags = 30;
LABEL_24:
        v13 = v12;
        goto LABEL_7;
      }
      CDplDuck::ReleaseKeyMaterial((CDplDuck *)a1);
      *(_QWORD *)(a1 + 32) = phAlgorithm;
      *(_DWORD *)(a1 + 40) = *(_DWORD *)pbOutput;
      *(_QWORD *)(a1 + 48) = hObject;
      *(_DWORD *)(a1 + 56) = *(_DWORD *)v58;
      *(_QWORD *)(a1 + 64) = hAlgorithm;
      *(_DWORD *)(a1 + 72) = *(_DWORD *)v59;
      *(_DWORD *)(a1 + 124) = v60;
      *(_QWORD *)(a1 + 80) = v62;
      *(_DWORD *)(a1 + 88) = v65;
      v48 = *(_QWORD *)(a1 + 128);
      *(_QWORD *)(a1 + 96) = v9;
      v9 = 0;
      phAlgorithm = 0;
      hObject = 0;
      hAlgorithm = 0;
      *(_DWORD *)(a1 + 104) = cbDataIn;
      *(_DWORD *)(a1 + 108) = v10;
      *(_DWORD *)(a1 + 120) = 1;
      *(_DWORD *)(v48 + 284) = 1;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
      *(_DWORD *)(a1 + 24) = SystemTimeAsFileTime.dwLowDateTime;
      *(_DWORD *)(a1 + 28) = dwHighDateTime;
    }
  }
LABEL_103:
  if ( v9 )
    DplibMemFree(v9);
  if ( v8 )
    DplibMemFree(v8);
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
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v12,
    39,
    92);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800c0e70  mov     rax, rsp
0x1800c0e73  mov     [rax+20h], rbx
0x1800c0e77  mov     [rax+18h], r8
0x1800c0e7b  mov     [rax+10h], edx
0x1800c0e7e  push    rbp
0x1800c0e7f  push    rsi
0x1800c0e80  push    rdi
0x1800c0e81  push    r12
0x1800c0e83  push    r13
0x1800c0e85  push    r14
0x1800c0e87  push    r15
0x1800c0e89  lea     rbp, [rax-57h]
0x1800c0e8d  sub     rsp, 0A0h
0x1800c0e94  xor     r15d, r15d
0x1800c0e97  mov     r13d, r9d
0x1800c0e9a  mov     rbx, r8
0x1800c0e9d  mov     [rbp+4Fh+phAlgorithm], r15
0x1800c0ea1  lea     r8, sourceString
0x1800c0ea8  mov     dword ptr [rbp+4Fh+pbOutput], r15d
0x1800c0eac  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800c0eb3  mov     [rbp+4Fh+hObject], r15
0x1800c0eb7  lea     r12d, [r15+20h]
0x1800c0ebb  mov     dword ptr [rbp+4Fh+var_54], r15d
0x1800c0ebf  lea     r9d, [r15+27h]
0x1800c0ec3  mov     [rbp+4Fh+arg_8], r12d
0x1800c0ec7  mov     rdi, rcx
0x1800c0eca  mov     [rbp+4Fh+hAlgorithm], r15
0x1800c0ece  mov     dword ptr [rbp+4Fh+var_50], r15d
0x1800c0ed2  mov     esi, r15d
0x1800c0ed5  mov     [rbp+4Fh+pbBuffer], r15
0x1800c0ed9  mov     r14d, r15d
0x1800c0edc  mov     [rbp+4Fh+pDataIn], r15
0x1800c0ee0  mov     [rbp+4Fh+var_40], r15
0x1800c0ee4  mov     [rbp+4Fh+pcbResult], r15d
0x1800c0ee8  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800c0eec  mov     [rbp+4Fh+var_4C], r15d
0x1800c0ef0  mov     dword ptr [rsp+0D0h+dwFlags], 193Bh
0x1800c0ef8  call    fnEfsLogTrace1Strings
0x1800c0efd  test    rbx, rbx
0x1800c0f00  jz      short loc_1800C0F4B
0x1800c0f02  test    r13d, r13d
0x1800c0f05  jz      short loc_1800C0F1A
0x1800c0f07  mov     r15d, [rbp+4Fh+cbBuffer]
0x1800c0f0b  test    r15d, r15d
0x1800c0f0e  jz      short loc_1800C0F1A
0x1800c0f10  cmp     r13d, r15d
0x1800c0f13  jb      short loc_1800C0F1A
0x1800c0f15  mov     ebx, r13d
0x1800c0f18  jmp     short loc_1800C0F51
0x1800c0f1a  mov     ebx, 80070057h
0x1800c0f1f  mov     dword ptr [rsp+0D0h+dwFlags], 1947h
0x1800c0f27  mov     r8d, 80070057h
0x1800c0f2d  mov     rcx, cs:g_hPublisher
0x1800c0f34  lea     rdx, EFS_TRACE_ERROR
0x1800c0f3b  mov     r9d, 27h ; '''
0x1800c0f41  call    fnEfsLogTrace1
0x1800c0f46  jmp     loc_1800C16C2
0x1800c0f4b  mov     r15d, r12d
0x1800c0f4e  mov     ebx, r12d
0x1800c0f51  mov     rcx, [rdi+80h]; this
0x1800c0f58  mov     [rbp+4Fh+cbDataIn], ebx
0x1800c0f5b  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800c0f60  test    eax, eax
0x1800c0f62  jnz     short loc_1800C0F79
0x1800c0f64  mov     dword ptr [rsp+0D0h+dwFlags], 1952h
0x1800c0f6c  mov     ebx, 8000FFFFh
0x1800c0f71  mov     r8d, 8000FFFFh
0x1800c0f77  jmp     short loc_1800C0F2D
0x1800c0f79  cmp     ebx, r15d
0x1800c0f7c  jnb     short loc_1800C0F88
0x1800c0f7e  mov     dword ptr [rsp+0D0h+dwFlags], 1954h
0x1800c0f86  jmp     short loc_1800C0F6C
0x1800c0f88  mov     rax, [rdi+10h]
0x1800c0f8c  xor     ebx, ebx
0x1800c0f8e  cmp     [rax+58h], rbx
0x1800c0f92  jnz     short loc_1800C0F9E
0x1800c0f94  mov     dword ptr [rsp+0D0h+dwFlags], 1955h
0x1800c0f9c  jmp     short loc_1800C0F6C
0x1800c0f9e  xor     r9d, r9d; dwFlags
0x1800c0fa1  lea     rdx, pszAlgId; "AES"
0x1800c0fa8  xor     r8d, r8d; pszImplementation
0x1800c0fab  lea     rcx, [rbp+4Fh+phAlgorithm]; phAlgorithm
0x1800c0faf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c0fb5  mov     r12d, eax
0x1800c0fb8  test    eax, eax
0x1800c0fba  jz      short loc_1800C0FFB
0x1800c0fbc  test    eax, eax
0x1800c0fbe  jns     short loc_1800C0FEB
0x1800c0fc0  mov     ecx, eax; Status
0x1800c0fc2  call    cs:__imp_RtlNtStatusToDosError
0x1800c0fc8  mov     ebx, eax
0x1800c0fca  test    eax, eax
0x1800c0fcc  jz      short loc_1800C0FE4
0x1800c0fce  cmp     eax, 13Dh
0x1800c0fd3  jz      short loc_1800C0FE4
0x1800c0fd5  test    eax, eax
0x1800c0fd7  jle     short loc_1800C0FEB
0x1800c0fd9  movzx   ebx, ax
0x1800c0fdc  or      ebx, 80070000h
0x1800c0fe2  jmp     short loc_1800C0FEB
0x1800c0fe4  mov     ebx, r12d
0x1800c0fe7  bts     ebx, 1Ch
0x1800c0feb  mov     dword ptr [rsp+0D0h+dwFlags], 195Fh
0x1800c0ff3  mov     r8d, ebx
0x1800c0ff6  jmp     loc_1800C0F2D
0x1800c0ffb  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x1800c0fff  lea     r8, pbInput; "ChainingModeCBC"
0x1800c1006  mov     r9d, 20h ; ' '; cbInput
0x1800c100c  mov     dword ptr [rsp+0D0h+dwFlags], ebx; dwFlags
0x1800c1010  lea     rdx, aChainingmode; "ChainingMode"
0x1800c1017  call    cs:__imp_BCryptSetProperty
0x1800c101d  mov     r12d, eax
0x1800c1020  test    eax, eax
0x1800c1022  jz      short loc_1800C105D
0x1800c1024  test    eax, eax
0x1800c1026  jns     short loc_1800C1053
0x1800c1028  mov     ecx, eax; Status
0x1800c102a  call    cs:__imp_RtlNtStatusToDosError
0x1800c1030  mov     ebx, eax
0x1800c1032  test    eax, eax
0x1800c1034  jz      short loc_1800C104C
0x1800c1036  cmp     eax, 13Dh
0x1800c103b  jz      short loc_1800C104C
0x1800c103d  test    eax, eax
0x1800c103f  jle     short loc_1800C1053
0x1800c1041  movzx   ebx, ax
0x1800c1044  or      ebx, 80070000h
0x1800c104a  jmp     short loc_1800C1053
0x1800c104c  mov     ebx, r12d
0x1800c104f  bts     ebx, 1Ch
0x1800c1053  mov     dword ptr [rsp+0D0h+dwFlags], 196Ah
0x1800c105b  jmp     short loc_1800C0FF3
0x1800c105d  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x1800c1061  lea     rax, [rbp+4Fh+pcbResult]
0x1800c1065  mov     [rsp+0D0h+var_A8], ebx; dwFlags
0x1800c1069  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x1800c106d  mov     r9d, 4; cbOutput
0x1800c1073  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbResult
0x1800c1078  lea     rdx, aObjectlength; "ObjectLength"
0x1800c107f  call    cs:__imp_BCryptGetProperty
0x1800c1085  mov     r12d, eax
0x1800c1088  test    eax, eax
0x1800c108a  jz      short loc_1800C10C8
0x1800c108c  test    eax, eax
0x1800c108e  jns     short loc_1800C10BB
0x1800c1090  mov     ecx, eax; Status
0x1800c1092  call    cs:__imp_RtlNtStatusToDosError
0x1800c1098  mov     ebx, eax
0x1800c109a  test    eax, eax
0x1800c109c  jz      short loc_1800C10B4
0x1800c109e  cmp     eax, 13Dh
0x1800c10a3  jz      short loc_1800C10B4
0x1800c10a5  test    eax, eax
0x1800c10a7  jle     short loc_1800C10BB
0x1800c10a9  movzx   ebx, ax
0x1800c10ac  or      ebx, 80070000h
0x1800c10b2  jmp     short loc_1800C10BB
0x1800c10b4  mov     ebx, r12d
0x1800c10b7  bts     ebx, 1Ch
0x1800c10bb  mov     dword ptr [rsp+0D0h+dwFlags], 1976h
0x1800c10c3  jmp     loc_1800C0FF3
0x1800c10c8  xor     r9d, r9d; dwFlags
0x1800c10cb  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x1800c10d2  xor     r8d, r8d; pszImplementation
0x1800c10d5  lea     rcx, [rbp+4Fh+hObject]; phAlgorithm
0x1800c10d9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c10df  mov     r12d, eax
0x1800c10e2  test    eax, eax
0x1800c10e4  jz      short loc_1800C1122
0x1800c10e6  test    eax, eax
0x1800c10e8  jns     short loc_1800C1115
0x1800c10ea  mov     ecx, eax; Status
0x1800c10ec  call    cs:__imp_RtlNtStatusToDosError
0x1800c10f2  mov     ebx, eax
0x1800c10f4  test    eax, eax
0x1800c10f6  jz      short loc_1800C110E
0x1800c10f8  cmp     eax, 13Dh
0x1800c10fd  jz      short loc_1800C110E
0x1800c10ff  test    eax, eax
0x1800c1101  jle     short loc_1800C1115
0x1800c1103  movzx   ebx, ax
0x1800c1106  or      ebx, 80070000h
0x1800c110c  jmp     short loc_1800C1115
0x1800c110e  mov     ebx, r12d
0x1800c1111  bts     ebx, 1Ch
0x1800c1115  mov     dword ptr [rsp+0D0h+dwFlags], 1984h
0x1800c111d  jmp     loc_1800C0FF3
0x1800c1122  mov     rcx, [rbp+4Fh+hObject]; hObject
0x1800c1126  lea     rax, [rbp+4Fh+pcbResult]
0x1800c112a  mov     [rsp+0D0h+var_A8], ebx; dwFlags
0x1800c112e  lea     r8, [rbp+4Fh+var_54]; pbOutput
0x1800c1132  mov     r9d, 4; cbOutput
0x1800c1138  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbResult
0x1800c113d  lea     rdx, aObjectlength; "ObjectLength"
0x1800c1144  call    cs:__imp_BCryptGetProperty
0x1800c114a  mov     r12d, eax
0x1800c114d  test    eax, eax
0x1800c114f  jz      short loc_1800C118D
0x1800c1151  test    eax, eax
0x1800c1153  jns     short loc_1800C1180
0x1800c1155  mov     ecx, eax; Status
0x1800c1157  call    cs:__imp_RtlNtStatusToDosError
0x1800c115d  mov     ebx, eax
0x1800c115f  test    eax, eax
0x1800c1161  jz      short loc_1800C1179
0x1800c1163  cmp     eax, 13Dh
0x1800c1168  jz      short loc_1800C1179
0x1800c116a  test    eax, eax
0x1800c116c  jle     short loc_1800C1180
0x1800c116e  movzx   ebx, ax
0x1800c1171  or      ebx, 80070000h
0x1800c1177  jmp     short loc_1800C1180
0x1800c1179  mov     ebx, r12d
0x1800c117c  bts     ebx, 1Ch
0x1800c1180  mov     dword ptr [rsp+0D0h+dwFlags], 1990h
0x1800c1188  jmp     loc_1800C0FF3
0x1800c118d  mov     r9d, 8; dwFlags
0x1800c1193  lea     rdx, aSha256; "SHA256"
0x1800c119a  xor     r8d, r8d; pszImplementation
0x1800c119d  lea     rcx, [rbp+4Fh+hAlgorithm]; phAlgorithm
0x1800c11a1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c11a7  mov     r12d, eax
0x1800c11aa  test    eax, eax
0x1800c11ac  jz      short loc_1800C11EA
0x1800c11ae  test    eax, eax
0x1800c11b0  jns     short loc_1800C11DD
0x1800c11b2  mov     ecx, eax; Status
0x1800c11b4  call    cs:__imp_RtlNtStatusToDosError
0x1800c11ba  mov     ebx, eax
0x1800c11bc  test    eax, eax
0x1800c11be  jz      short loc_1800C11D6
0x1800c11c0  cmp     eax, 13Dh
0x1800c11c5  jz      short loc_1800C11D6
0x1800c11c7  test    eax, eax
0x1800c11c9  jle     short loc_1800C11DD
0x1800c11cb  movzx   ebx, ax
0x1800c11ce  or      ebx, 80070000h
0x1800c11d4  jmp     short loc_1800C11DD
0x1800c11d6  mov     ebx, r12d
0x1800c11d9  bts     ebx, 1Ch
0x1800c11dd  mov     dword ptr [rsp+0D0h+dwFlags], 199Eh
0x1800c11e5  jmp     loc_1800C0FF3
0x1800c11ea  mov     rcx, [rbp+4Fh+hAlgorithm]; hObject
0x1800c11ee  lea     rax, [rbp+4Fh+pcbResult]
0x1800c11f2  mov     [rsp+0D0h+var_A8], ebx; dwFlags
0x1800c11f6  lea     r8, [rbp+4Fh+var_50]; pbOutput
0x1800c11fa  mov     r9d, 4; cbOutput
0x1800c1200  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbResult
0x1800c1205  lea     rdx, aObjectlength; "ObjectLength"
0x1800c120c  call    cs:__imp_BCryptGetProperty
0x1800c1212  mov     r12d, eax
0x1800c1215  test    eax, eax
0x1800c1217  jz      short loc_1800C1255
0x1800c1219  test    eax, eax
0x1800c121b  jns     short loc_1800C1248
0x1800c121d  mov     ecx, eax; Status
0x1800c121f  call    cs:__imp_RtlNtStatusToDosError
0x1800c1225  mov     ebx, eax
0x1800c1227  test    eax, eax
0x1800c1229  jz      short loc_1800C1241
0x1800c122b  cmp     eax, 13Dh
0x1800c1230  jz      short loc_1800C1241
0x1800c1232  test    eax, eax
0x1800c1234  jle     short loc_1800C1248
0x1800c1236  movzx   ebx, ax
0x1800c1239  or      ebx, 80070000h
0x1800c123f  jmp     short loc_1800C1248
0x1800c1241  mov     ebx, r12d
0x1800c1244  bts     ebx, 1Ch
0x1800c1248  mov     dword ptr [rsp+0D0h+dwFlags], 19AAh
0x1800c1250  jmp     loc_1800C0FF3
0x1800c1255  mov     esi, 19B4h
0x1800c125a  lea     r8, sourceString
0x1800c1261  mov     r9d, 27h ; '''
0x1800c1267  mov     dword ptr [rsp+0D0h+dwFlags], esi
0x1800c126b  lea     rdx, EFS_TRACE_START_EVENT
0x1800c1272  call    fnEfsLogTrace1Strings
0x1800c1277  mov     edx, 1
0x1800c127c  mov     ecx, r15d
0x1800c127f  mov     r8d, edx
0x1800c1282  mov     r12d, r15d
0x1800c1285  lea     r9, [rbp+4Fh+pbBuffer]
0x1800c1289  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c128e  mov     rcx, cs:g_hPublisher
0x1800c1295  lea     r9, sourceString
0x1800c129c  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800c12a0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c12a7  mov     esi, 27h ; '''
0x1800c12ac  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c12b3  mov     [rsp+0D0h+var_A8], esi
0x1800c12b7  mov     ebx, eax
0x1800c12b9  mov     dword ptr [rsp+0D0h+dwFlags], eax
0x1800c12bd  call    fnEfsLogTrace1String1Dword
0x1800c12c2  test    eax, eax
0x1800c12c4  js      loc_1800C16BE
0x1800c12ca  mov     r14d, 19B9h
0x1800c12d0  lea     r8, sourceString
0x1800c12d7  mov     r9d, esi
0x1800c12da  mov     dword ptr [rsp+0D0h+dwFlags], r14d
0x1800c12df  lea     rdx, EFS_TRACE_START_EVENT
  ... truncated ...
```
