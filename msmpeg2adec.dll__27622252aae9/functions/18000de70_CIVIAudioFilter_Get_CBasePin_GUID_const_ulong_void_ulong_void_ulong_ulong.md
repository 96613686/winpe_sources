# CIVIAudioFilter::Get(CBasePin *,_GUID const &,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x18000de70`
- end: `0x18000e5e9`
- name: `?Get@CIVIAudioFilter@@UEAAJPEAVCBasePin@@AEBU_GUID@@KPEAXK2KPEAK@Z`
- size: `1913`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, struct CBasePin *, const struct _GUID *, unsigned int, void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18001d8c0`

## callees

- `0x1800017b0`
- `0x18000de70`
- `0x180018450`
- `0x1800205b0`
- `0x180024290`
- `0x18005e7a0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e09a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e25a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e43a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e09a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e25a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e43a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e07f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e23f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e41f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e07f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e23f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e47b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e05d`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e21d`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e3fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000df58`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e10e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e2fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000df58`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e10e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e2fb`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000e00f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000e1cf`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000e3af`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000e00f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000e1cf`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18000e3af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e535`

## string_xrefs

- `0x18000e078`: `ntdll.dll`
- `0x18000e238`: `ntdll.dll`
- `0x18000e418`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::Get(
        CIVIAudioFilter *this,
        struct CBasePin *a2,
        const struct _GUID *a3,
        int a4,
        void *a5,
        unsigned int a6,
        _BYTE *a7,
        unsigned int a8,
        unsigned int *a9)
{
  __int64 result; // rax
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  int v14; // r14d
  const CHAR *v15; // rbx
  HANDLE FileA; // rax
  HMODULE v17; // rax
  FARPROC v18; // rax
  unsigned int v19; // r14d
  const CHAR *v20; // rbx
  HMODULE v21; // rax
  FARPROC v22; // rax
  unsigned int v23; // r14d
  const CHAR *v24; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  void *v27; // rcx
  int v28; // r8d
  int Key; // ebx
  _WORD v30[2]; // [rsp+40h] [rbp-40h] BYREF
  int v31; // [rsp+44h] [rbp-3Ch] BYREF
  int v32; // [rsp+48h] [rbp-38h] BYREF
  int v33; // [rsp+4Ch] [rbp-34h]
  int v34; // [rsp+50h] [rbp-30h]
  int v35; // [rsp+54h] [rbp-2Ch]
  int v36; // [rsp+58h] [rbp-28h]
  int v37; // [rsp+5Ch] [rbp-24h]
  int v38; // [rsp+60h] [rbp-20h]
  int v39; // [rsp+64h] [rbp-1Ch]
  char v40; // [rsp+68h] [rbp-18h]

  if ( a9 )
    *a9 = 0;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&AM_KSPROPSETID_DvdKaraoke.Data1
    && *(_QWORD *)a3->Data4 == *(_QWORD *)AM_KSPROPSETID_DvdKaraoke.Data4 )
  {
    return 2147943568LL;
  }
  if ( *(_QWORD *)&a3->Data1 != *(_QWORD *)&AM_KSPROPSETID_CopyProt.Data1
    || *(_QWORD *)a3->Data4 != *(_QWORD *)AM_KSPROPSETID_CopyProt.Data4 )
  {
    if ( *((_DWORD *)this + 1616)
      && *(_QWORD *)&a3->Data1 == *(_QWORD *)&AM_KSPROPSETID_TSRateChange.Data1
      && *(_QWORD *)a3->Data4 == *(_QWORD *)AM_KSPROPSETID_TSRateChange.Data4 )
    {
      if ( a4 == 3 )
      {
        if ( a8 >= 4 )
        {
          *(_DWORD *)a7 = 20000;
          result = 0;
          *a9 = 4;
          return result;
        }
        return 2147500037LL;
      }
      if ( a4 == 9 )
      {
        if ( a8 >= 4 )
        {
          *(_DWORD *)a7 = 0;
          result = 0;
          *a9 = 4;
          return result;
        }
        return 2147500037LL;
      }
    }
    return 2147943570LL;
  }
  if ( !*((_DWORD *)this + 10) )
    return 2147746343LL;
  if ( !a7 )
    return 2147500035LL;
  v11 = a4 - 1;
  if ( !v11 )
  {
    if ( a8 < 0xC )
      return 2147942487LL;
    if ( IsDebuggerPresent() )
      goto LABEL_68;
    v32 = -1540288806;
    v23 = 0;
    v33 = -938834218;
    v34 = -626301380;
    v35 = -878431986;
    v36 = 2043543707;
    v37 = 249220523;
    v38 = -1681152975;
    v39 = 573627668;
    v40 = -50;
    while ( 1 )
    {
      v24 = (char *)&v32 + 11 * v23;
      *v24 ^= 0x86u;
      *((_BYTE *)v24 + 1) ^= 0x52u;
      *((_BYTE *)v24 + 2) ^= 0x1Fu;
      *((_BYTE *)v24 + 3) ^= 0xF8u;
      *((_BYTE *)v24 + 4) ^= 0x98u;
      *((_BYTE *)v24 + 5) ^= 0xD2u;
      *((_BYTE *)v24 + 6) ^= 0x43u;
      *((_BYTE *)v24 + 7) ^= 0x8Bu;
      *((_BYTE *)v24 + 8) ^= 0x79u;
      *((_BYTE *)v24 + 9) ^= 0x66u;
      *((_BYTE *)v24 + 10) ^= 0xCEu;
      FileA = CreateFileA(v24, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
      *v24 ^= 0x86u;
      *((_BYTE *)v24 + 1) ^= 0x52u;
      *((_BYTE *)v24 + 2) ^= 0x1Fu;
      *((_BYTE *)v24 + 3) ^= 0xF8u;
      *((_BYTE *)v24 + 4) ^= 0x98u;
      *((_BYTE *)v24 + 5) ^= 0xD2u;
      *((_BYTE *)v24 + 6) ^= 0x43u;
      *((_BYTE *)v24 + 7) ^= 0x8Bu;
      *((_BYTE *)v24 + 8) ^= 0x79u;
      *((_BYTE *)v24 + 9) ^= 0x66u;
      *((_BYTE *)v24 + 10) ^= 0xCEu;
      if ( FileA != (HANDLE)-1LL )
        goto LABEL_67;
      if ( (int)++v23 >= 3 )
      {
        if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
          goto LABEL_68;
        v30[0] = 257;
        Library = LoadLibraryExA("ntdll.dll", 0, 0);
        if ( Library && (ProcAddress = GetProcAddress(Library, "NtQuerySystemInformation")) != 0 )
        {
          v31 = -1;
          if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, int *))ProcAddress)(35, v30, 2, &v31)
            && LOBYTE(v30[0]) )
          {
            goto LABEL_68;
          }
        }
        else
        {
          GetLastError();
        }
        if ( (unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt() )
          return 2147549183LL;
        Key = DRM_GenerateKey(v27, (unsigned __int8 *)this + 17192, v28);
        if ( (unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt() )
          return 2147549183LL;
        *a7 = *((_BYTE *)this + 17201);
        a7[1] = *((_BYTE *)this + 17200);
        a7[2] = *((_BYTE *)this + 17199);
        a7[3] = *((_BYTE *)this + 17198);
        a7[4] = *((_BYTE *)this + 17197);
        a7[5] = *((_BYTE *)this + 17196);
        a7[6] = *((_BYTE *)this + 17195);
        a7[7] = *((_BYTE *)this + 17194);
        a7[8] = *((_BYTE *)this + 17193);
        a7[9] = *((_BYTE *)this + 17192);
        if ( a9 )
          *a9 = 12;
        return Key != 0 ? 0x80070032 : 0;
      }
    }
  }
  v12 = v11 - 2;
  if ( !v12 )
  {
    if ( a8 < 6 )
      return 2147942487LL;
    if ( IsDebuggerPresent() )
      goto LABEL_68;
    v32 = -1540288806;
    v19 = 0;
    v33 = -938834218;
    v34 = -626301380;
    v35 = -878431986;
    v36 = 2043543707;
    v37 = 249220523;
    v38 = -1681152975;
    v39 = 573627668;
    v40 = -50;
    while ( 1 )
    {
      v20 = (char *)&v32 + 11 * v19;
      *v20 ^= 0x86u;
      *((_BYTE *)v20 + 1) ^= 0x52u;
      *((_BYTE *)v20 + 2) ^= 0x1Fu;
      *((_BYTE *)v20 + 3) ^= 0xF8u;
      *((_BYTE *)v20 + 4) ^= 0x98u;
      *((_BYTE *)v20 + 5) ^= 0xD2u;
      *((_BYTE *)v20 + 6) ^= 0x43u;
      *((_BYTE *)v20 + 7) ^= 0x8Bu;
      *((_BYTE *)v20 + 8) ^= 0x79u;
      *((_BYTE *)v20 + 9) ^= 0x66u;
      *((_BYTE *)v20 + 10) ^= 0xCEu;
      FileA = CreateFileA(v20, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
      *v20 ^= 0x86u;
      *((_BYTE *)v20 + 1) ^= 0x52u;
      *((_BYTE *)v20 + 2) ^= 0x1Fu;
      *((_BYTE *)v20 + 3) ^= 0xF8u;
      *((_BYTE *)v20 + 4) ^= 0x98u;
      *((_BYTE *)v20 + 5) ^= 0xD2u;
      *((_BYTE *)v20 + 6) ^= 0x43u;
      *((_BYTE *)v20 + 7) ^= 0x8Bu;
      *((_BYTE *)v20 + 8) ^= 0x79u;
      *((_BYTE *)v20 + 9) ^= 0x66u;
      *((_BYTE *)v20 + 10) ^= 0xCEu;
      if ( FileA != (HANDLE)-1LL )
        break;
      if ( (int)++v19 >= 3 )
      {
        if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
          goto LABEL_68;
        v30[0] = 257;
        v21 = LoadLibraryExA("ntdll.dll", 0, 0);
        if ( v21 && (v22 = GetProcAddress(v21, "NtQuerySystemInformation")) != 0 )
        {
          v31 = -1;
          if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, int *))v22)(35, v30, 2, &v31) && LOBYTE(v30[0]) )
            goto LABEL_68;
        }
        else
        {
          GetLastError();
        }
        *a7 = *((_BYTE *)this + 17221);
        a7[1] = *((_BYTE *)this + 17220);
        a7[2] = *((_BYTE *)this + 17219);
        a7[3] = *((_BYTE *)this + 17218);
        a7[4] = *((_BYTE *)this + 17217);
        if ( a9 )
          *a9 = 6;
        return 0;
      }
    }
LABEL_67:
    CloseHandle(FileA);
    goto LABEL_68;
  }
  v13 = v12 - 4;
  if ( !v13 )
  {
    if ( a8 < 4 )
      return 2147942487LL;
    if ( !IsDebuggerPresent() )
    {
      v32 = -1540288806;
      v14 = 0;
      v33 = -938834218;
      v34 = -626301380;
      v35 = -878431986;
      v36 = 2043543707;
      v37 = 249220523;
      v38 = -1681152975;
      v39 = 573627668;
      v40 = -50;
      do
      {
        v15 = (char *)&v32 + 11 * (unsigned int)v14;
        *v15 ^= 0x86u;
        *((_BYTE *)v15 + 1) ^= 0x52u;
        *((_BYTE *)v15 + 2) ^= 0x1Fu;
        *((_BYTE *)v15 + 3) ^= 0xF8u;
        *((_BYTE *)v15 + 4) ^= 0x98u;
        *((_BYTE *)v15 + 5) ^= 0xD2u;
        *((_BYTE *)v15 + 6) ^= 0x43u;
        *((_BYTE *)v15 + 7) ^= 0x8Bu;
        *((_BYTE *)v15 + 8) ^= 0x79u;
        *((_BYTE *)v15 + 9) ^= 0x66u;
        *((_BYTE *)v15 + 10) ^= 0xCEu;
        FileA = CreateFileA(v15, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
        *v15 ^= 0x86u;
        *((_BYTE *)v15 + 1) ^= 0x52u;
        *((_BYTE *)v15 + 2) ^= 0x1Fu;
        *((_BYTE *)v15 + 3) ^= 0xF8u;
        *((_BYTE *)v15 + 4) ^= 0x98u;
        *((_BYTE *)v15 + 5) ^= 0xD2u;
        *((_BYTE *)v15 + 6) ^= 0x43u;
        *((_BYTE *)v15 + 7) ^= 0x8Bu;
        *((_BYTE *)v15 + 8) ^= 0x79u;
        *((_BYTE *)v15 + 9) ^= 0x66u;
        *((_BYTE *)v15 + 10) ^= 0xCEu;
        if ( FileA != (HANDLE)-1LL )
          goto LABEL_67;
        ++v14;
      }
      while ( v14 < 3 );
      if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
        goto LABEL_68;
      v30[0] = 257;
      v17 = LoadLibraryExA("ntdll.dll", 0, 0);
      if ( !v17 || (v18 = GetProcAddress(v17, "NtQuerySystemInformation")) == 0 )
      {
        GetLastError();
LABEL_30:
        *(_DWORD *)a7 = 3;
        goto LABEL_31;
      }
      v31 = -1;
      if ( ((unsigned int (__fastcall *)(__int64, _WORD *, __int64, int *))v18)(35, v30, 2, &v31) || !LOBYTE(v30[0]) )
        goto LABEL_30;
    }
LABEL_68:
    CMFSampleProtection::UpdateInputInfo((CMFSampleProtection *)(*((_QWORD *)this + 27) + 320LL));
    return 0;
  }
  if ( v13 != 4 )
    return 2147943568LL;
  if ( a8 < 4 )
    return 2147942487LL;
  *(_DWORD *)a7 = 1;
LABEL_31:
  if ( !a9 )
    return 0;
  *a9 = 4;
  return 0;
}

```

## disassembly

```asm
0x18000de70  push    rbp
0x18000de72  push    rsi
0x18000de73  push    rdi
0x18000de74  push    r12
0x18000de76  push    r15
0x18000de78  mov     rbp, rsp
0x18000de7b  sub     rsp, 80h
0x18000de82  mov     rax, cs:__security_cookie
0x18000de89  xor     rax, rsp
0x18000de8c  mov     [rbp+var_10], rax
0x18000de90  mov     r15, [rbp+arg_40]
0x18000de94  xor     r12d, r12d
0x18000de97  mov     rsi, [rbp+arg_30]
0x18000de9b  mov     rdi, rcx
0x18000de9e  test    r15, r15
0x18000dea1  jz      short loc_18000DEA6
0x18000dea3  mov     [r15], r12d
0x18000dea6  mov     rax, [r8]
0x18000dea9  cmp     rax, qword ptr cs:AM_KSPROPSETID_DvdKaraoke.Data1
0x18000deb0  mov     [rsp+80h+arg_8], rbx
0x18000deb8  mov     [rsp+80h+arg_10], r14
0x18000dec0  jnz     short loc_18000DECF
0x18000dec2  mov     rax, [r8+8]
0x18000dec6  cmp     rax, qword ptr cs:AM_KSPROPSETID_DvdKaraoke.Data4
0x18000decd  jz      short loc_18000DF44
0x18000decf  mov     rax, [r8]
0x18000ded2  cmp     rax, qword ptr cs:AM_KSPROPSETID_CopyProt.Data1
0x18000ded9  jnz     loc_18000E558
0x18000dedf  mov     rax, [r8+8]
0x18000dee3  cmp     rax, qword ptr cs:AM_KSPROPSETID_CopyProt.Data4
0x18000deea  jnz     loc_18000E558
0x18000def0  cmp     [rcx+28h], r12d
0x18000def4  jnz     short loc_18000DF00
0x18000def6  mov     eax, 80040227h
0x18000defb  jmp     loc_18000E5BD
0x18000df00  test    rsi, rsi
0x18000df03  jnz     short loc_18000DF0F
0x18000df05  mov     eax, 80004003h
0x18000df0a  jmp     loc_18000E5BD
0x18000df0f  sub     r9d, 1
0x18000df13  jz      loc_18000E2EB
0x18000df19  sub     r9d, 2
0x18000df1d  jz      loc_18000E104
0x18000df23  sub     r9d, 4
0x18000df27  jz      short loc_18000DF4E
0x18000df29  cmp     r9d, 4
0x18000df2d  jnz     short loc_18000DF44
0x18000df2f  cmp     [rbp+arg_38], r9d
0x18000df33  jb      loc_18000E2F1
0x18000df39  mov     dword ptr [rsi], 1
0x18000df3f  jmp     loc_18000E0ED
0x18000df44  mov     eax, 80070490h
0x18000df49  jmp     loc_18000E5BD
0x18000df4e  cmp     [rbp+arg_38], 4
0x18000df52  jb      loc_18000E2F1
0x18000df58  call    cs:__imp_IsDebuggerPresent
0x18000df5f  nop     dword ptr [rax+rax+00h]
0x18000df64  test    eax, eax
0x18000df66  jnz     loc_18000E541
0x18000df6c  mov     [rbp+var_38], 0A4310EDAh
0x18000df73  mov     r14d, r12d
0x18000df76  mov     [rbp+var_34], 0C80A86D6h
0x18000df7d  mov     [rbp+var_30], 0DAAB663Ch
0x18000df84  mov     [rbp+var_2C], 0CBA4310Eh
0x18000df8b  mov     [rbp+var_28], 79CE009Bh
0x18000df92  mov     [rbp+var_24], 0EDACDABh
0x18000df99  mov     [rbp+var_20], 9BCBA431h
0x18000dfa0  mov     [rbp+var_1C], 2230DD14h
0x18000dfa7  mov     [rbp+var_18], 0CEh
0x18000dfab  nop     dword ptr [rax+rax+00h]
0x18000dfb0  mov     eax, r14d
0x18000dfb3  lea     rbx, [rbp+var_38]
0x18000dfb7  imul    rcx, rax, 0Bh
0x18000dfbb  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18000dfc0  xor     r9d, r9d; lpSecurityAttributes
0x18000dfc3  add     rbx, rcx
0x18000dfc6  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000dfce  mov     edx, 0C0000000h; dwDesiredAccess
0x18000dfd3  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18000dfdb  mov     r8d, 3; dwShareMode
0x18000dfe1  mov     rcx, rbx; lpFileName
0x18000dfe4  xor     byte ptr [rbx], 86h
0x18000dfe7  xor     byte ptr [rbx+1], 52h
0x18000dfeb  xor     byte ptr [rbx+2], 1Fh
0x18000dfef  xor     byte ptr [rbx+3], 0F8h
0x18000dff3  xor     byte ptr [rbx+4], 98h
0x18000dff7  xor     byte ptr [rbx+5], 0D2h
0x18000dffb  xor     byte ptr [rbx+6], 43h
0x18000dfff  xor     byte ptr [rbx+7], 8Bh
0x18000e003  xor     byte ptr [rbx+8], 79h
0x18000e007  xor     byte ptr [rbx+9], 66h
0x18000e00b  xor     byte ptr [rbx+0Ah], 0CEh
0x18000e00f  call    cs:__imp_CreateFileA
0x18000e016  nop     dword ptr [rax+rax+00h]
0x18000e01b  xor     byte ptr [rbx], 86h
0x18000e01e  xor     byte ptr [rbx+1], 52h
0x18000e022  xor     byte ptr [rbx+2], 1Fh
0x18000e026  xor     byte ptr [rbx+3], 0F8h
0x18000e02a  xor     byte ptr [rbx+4], 98h
0x18000e02e  xor     byte ptr [rbx+5], 0D2h
0x18000e032  xor     byte ptr [rbx+6], 43h
0x18000e036  xor     byte ptr [rbx+7], 8Bh
0x18000e03a  xor     byte ptr [rbx+8], 79h
0x18000e03e  xor     byte ptr [rbx+9], 66h
0x18000e042  xor     byte ptr [rbx+0Ah], 0CEh
0x18000e046  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e04a  jnz     loc_18000E532
0x18000e050  inc     r14d
0x18000e053  cmp     r14d, 3
0x18000e057  jl      loc_18000DFB0
0x18000e05d  mov     rax, cs:__imp_UnhandledExceptionFilter
0x18000e064  cmp     byte ptr [rax], 0CCh
0x18000e067  jz      loc_18000E541
0x18000e06d  xor     r8d, r8d; dwFlags
0x18000e070  mov     [rbp+var_40], 101h
0x18000e076  xor     edx, edx; hFile
0x18000e078  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e07f  call    cs:__imp_LoadLibraryExA
0x18000e086  nop     dword ptr [rax+rax+00h]
0x18000e08b  test    rax, rax
0x18000e08e  jz      short loc_18000E0DB
0x18000e090  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x18000e097  mov     rcx, rax; hModule
0x18000e09a  call    cs:__imp_GetProcAddress
0x18000e0a1  nop     dword ptr [rax+rax+00h]
0x18000e0a6  test    rax, rax
0x18000e0a9  jz      short loc_18000E0DB
0x18000e0ab  lea     r9, [rbp+var_3C]
0x18000e0af  mov     [rbp+var_3C], 0FFFFFFFFh
0x18000e0b6  mov     r8d, 2
0x18000e0bc  lea     rdx, [rbp+var_40]
0x18000e0c0  mov     ecx, 23h ; '#'
0x18000e0c5  call    cs:__guard_dispatch_icall_fptr
0x18000e0cb  test    eax, eax
0x18000e0cd  jnz     short loc_18000E0E7
0x18000e0cf  cmp     byte ptr [rbp+var_40], r12b
0x18000e0d3  jnz     loc_18000E541
0x18000e0d9  jmp     short loc_18000E0E7
0x18000e0db  call    cs:__imp_GetLastError
0x18000e0e2  nop     dword ptr [rax+rax+00h]
0x18000e0e7  mov     dword ptr [rsi], 3
0x18000e0ed  test    r15, r15
0x18000e0f0  jz      loc_18000E2E4
0x18000e0f6  mov     dword ptr [r15], 4
0x18000e0fd  xor     eax, eax
0x18000e0ff  jmp     loc_18000E5BD
0x18000e104  cmp     [rbp+arg_38], 6
0x18000e108  jb      loc_18000E2F1
0x18000e10e  call    cs:__imp_IsDebuggerPresent
0x18000e115  nop     dword ptr [rax+rax+00h]
0x18000e11a  test    eax, eax
0x18000e11c  jnz     loc_18000E541
0x18000e122  mov     [rbp+var_38], 0A4310EDAh
0x18000e129  mov     r14d, r12d
0x18000e12c  mov     [rbp+var_34], 0C80A86D6h
0x18000e133  mov     [rbp+var_30], 0DAAB663Ch
0x18000e13a  mov     [rbp+var_2C], 0CBA4310Eh
0x18000e141  mov     [rbp+var_28], 79CE009Bh
0x18000e148  mov     [rbp+var_24], 0EDACDABh
0x18000e14f  mov     [rbp+var_20], 9BCBA431h
0x18000e156  mov     [rbp+var_1C], 2230DD14h
0x18000e15d  mov     [rbp+var_18], 0CEh
0x18000e161  nop     dword ptr [rax+00h]
0x18000e165  nop     word ptr [rax+rax+00000000h]
0x18000e170  mov     eax, r14d
0x18000e173  lea     rbx, [rbp+var_38]
0x18000e177  imul    rcx, rax, 0Bh
0x18000e17b  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18000e180  xor     r9d, r9d; lpSecurityAttributes
0x18000e183  add     rbx, rcx
0x18000e186  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e18e  mov     edx, 0C0000000h; dwDesiredAccess
0x18000e193  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e19b  mov     r8d, 3; dwShareMode
0x18000e1a1  mov     rcx, rbx; lpFileName
0x18000e1a4  xor     byte ptr [rbx], 86h
0x18000e1a7  xor     byte ptr [rbx+1], 52h
0x18000e1ab  xor     byte ptr [rbx+2], 1Fh
0x18000e1af  xor     byte ptr [rbx+3], 0F8h
0x18000e1b3  xor     byte ptr [rbx+4], 98h
0x18000e1b7  xor     byte ptr [rbx+5], 0D2h
0x18000e1bb  xor     byte ptr [rbx+6], 43h
0x18000e1bf  xor     byte ptr [rbx+7], 8Bh
0x18000e1c3  xor     byte ptr [rbx+8], 79h
0x18000e1c7  xor     byte ptr [rbx+9], 66h
0x18000e1cb  xor     byte ptr [rbx+0Ah], 0CEh
0x18000e1cf  call    cs:__imp_CreateFileA
0x18000e1d6  nop     dword ptr [rax+rax+00h]
0x18000e1db  xor     byte ptr [rbx], 86h
0x18000e1de  xor     byte ptr [rbx+1], 52h
0x18000e1e2  xor     byte ptr [rbx+2], 1Fh
0x18000e1e6  xor     byte ptr [rbx+3], 0F8h
0x18000e1ea  xor     byte ptr [rbx+4], 98h
0x18000e1ee  xor     byte ptr [rbx+5], 0D2h
0x18000e1f2  xor     byte ptr [rbx+6], 43h
0x18000e1f6  xor     byte ptr [rbx+7], 8Bh
0x18000e1fa  xor     byte ptr [rbx+8], 79h
0x18000e1fe  xor     byte ptr [rbx+9], 66h
0x18000e202  xor     byte ptr [rbx+0Ah], 0CEh
0x18000e206  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e20a  jnz     loc_18000E532
0x18000e210  inc     r14d
0x18000e213  cmp     r14d, 3
0x18000e217  jl      loc_18000E170
0x18000e21d  mov     rax, cs:__imp_UnhandledExceptionFilter
0x18000e224  cmp     byte ptr [rax], 0CCh
0x18000e227  jz      loc_18000E541
0x18000e22d  xor     r8d, r8d; dwFlags
0x18000e230  mov     [rbp+var_40], 101h
0x18000e236  xor     edx, edx; hFile
0x18000e238  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e23f  call    cs:__imp_LoadLibraryExA
0x18000e246  nop     dword ptr [rax+rax+00h]
0x18000e24b  test    rax, rax
0x18000e24e  jz      short loc_18000E29B
0x18000e250  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x18000e257  mov     rcx, rax; hModule
0x18000e25a  call    cs:__imp_GetProcAddress
0x18000e261  nop     dword ptr [rax+rax+00h]
0x18000e266  test    rax, rax
0x18000e269  jz      short loc_18000E29B
0x18000e26b  lea     r9, [rbp+var_3C]
0x18000e26f  mov     [rbp+var_3C], 0FFFFFFFFh
0x18000e276  mov     r8d, 2
0x18000e27c  lea     rdx, [rbp+var_40]
0x18000e280  mov     ecx, 23h ; '#'
0x18000e285  call    cs:__guard_dispatch_icall_fptr
0x18000e28b  test    eax, eax
0x18000e28d  jnz     short loc_18000E2A7
0x18000e28f  cmp     byte ptr [rbp+var_40], r12b
0x18000e293  jnz     loc_18000E541
0x18000e299  jmp     short loc_18000E2A7
0x18000e29b  call    cs:__imp_GetLastError
0x18000e2a2  nop     dword ptr [rax+rax+00h]
0x18000e2a7  movzx   eax, byte ptr [rdi+4345h]
0x18000e2ae  mov     [rsi], al
0x18000e2b0  movzx   eax, byte ptr [rdi+4344h]
0x18000e2b7  mov     [rsi+1], al
0x18000e2ba  movzx   eax, byte ptr [rdi+4343h]
0x18000e2c1  mov     [rsi+2], al
0x18000e2c4  movzx   eax, byte ptr [rdi+4342h]
0x18000e2cb  mov     [rsi+3], al
0x18000e2ce  movzx   eax, byte ptr [rdi+4341h]
0x18000e2d5  mov     [rsi+4], al
0x18000e2d8  test    r15, r15
0x18000e2db  jz      short loc_18000E2E4
0x18000e2dd  mov     dword ptr [r15], 6
0x18000e2e4  xor     eax, eax
0x18000e2e6  jmp     loc_18000E5BD
0x18000e2eb  cmp     [rbp+arg_38], 0Ch
0x18000e2ef  jnb     short loc_18000E2FB
0x18000e2f1  mov     eax, 80070057h
0x18000e2f6  jmp     loc_18000E5BD
0x18000e2fb  call    cs:__imp_IsDebuggerPresent
0x18000e302  nop     dword ptr [rax+rax+00h]
0x18000e307  test    eax, eax
0x18000e309  jnz     loc_18000E541
0x18000e30f  mov     [rbp+var_38], 0A4310EDAh
0x18000e316  mov     r14d, r12d
0x18000e319  mov     [rbp+var_34], 0C80A86D6h
0x18000e320  mov     [rbp+var_30], 0DAAB663Ch
0x18000e327  mov     [rbp+var_2C], 0CBA4310Eh
0x18000e32e  mov     [rbp+var_28], 79CE009Bh
0x18000e335  mov     [rbp+var_24], 0EDACDABh
0x18000e33c  mov     [rbp+var_20], 9BCBA431h
0x18000e343  mov     [rbp+var_1C], 2230DD14h
0x18000e34a  mov     [rbp+var_18], 0CEh
0x18000e34e  xchg    ax, ax
0x18000e350  mov     eax, r14d
0x18000e353  lea     rbx, [rbp+var_38]
0x18000e357  imul    rcx, rax, 0Bh
0x18000e35b  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18000e360  xor     r9d, r9d; lpSecurityAttributes
0x18000e363  add     rbx, rcx
0x18000e366  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e36e  mov     edx, 0C0000000h; dwDesiredAccess
0x18000e373  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e37b  mov     r8d, 3; dwShareMode
0x18000e381  mov     rcx, rbx; lpFileName
0x18000e384  xor     byte ptr [rbx], 86h
0x18000e387  xor     byte ptr [rbx+1], 52h
0x18000e38b  xor     byte ptr [rbx+2], 1Fh
0x18000e38f  xor     byte ptr [rbx+3], 0F8h
0x18000e393  xor     byte ptr [rbx+4], 98h
0x18000e397  xor     byte ptr [rbx+5], 0D2h
0x18000e39b  xor     byte ptr [rbx+6], 43h
0x18000e39f  xor     byte ptr [rbx+7], 8Bh
0x18000e3a3  xor     byte ptr [rbx+8], 79h
0x18000e3a7  xor     byte ptr [rbx+9], 66h
0x18000e3ab  xor     byte ptr [rbx+0Ah], 0CEh
0x18000e3af  call    cs:__imp_CreateFileA
0x18000e3b6  nop     dword ptr [rax+rax+00h]
0x18000e3bb  xor     byte ptr [rbx], 86h
0x18000e3be  xor     byte ptr [rbx+1], 52h
0x18000e3c2  xor     byte ptr [rbx+2], 1Fh
0x18000e3c6  xor     byte ptr [rbx+3], 0F8h
0x18000e3ca  xor     byte ptr [rbx+4], 98h
0x18000e3ce  xor     byte ptr [rbx+5], 0D2h
0x18000e3d2  xor     byte ptr [rbx+6], 43h
0x18000e3d6  xor     byte ptr [rbx+7], 8Bh
  ... truncated ...
```
