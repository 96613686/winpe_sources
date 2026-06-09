# CDisplayMonitor::EnsureColorTransformShimIccFile(ushort const *)

- ea: `0x180026c10`
- end: `0x180027381`
- name: `?EnsureColorTransformShimIccFile@CDisplayMonitor@@AEAAJPEBG@Z`
- size: `1905`
- prototype: `__int64 __fastcall(CDisplayMonitor *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800804ac`

## callees

- `0x1800269d4`
- `0x180026c10`
- `0x180027388`
- `0x1800273c4`
- `0x1800273e8`
- `0x1800280a8`
- `0x180028158`
- `0x1800281a0`
- `0x18002d518`
- `0x18002e5f0`
- `0x18007fb10`
- `0x180080864`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800271ca`
- `msvcp_win!_Mtx_unlock` at `0x18002729b`
- `msvcp_win!_Mtx_unlock` at `0x1800271ca`
- `msvcp_win!_Mtx_unlock` at `0x18002729b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026cf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026d72`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026cf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026d72`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800272b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800272b0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180026e33`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180027188`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180026e33`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180027188`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180026dc0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800271bb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180026dc0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800271bb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027222`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027222`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDisplayMonitor::EnsureColorTransformShimIccFile(CDisplayMonitor *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  signed int v5; // ebx
  int i; // r14d
  const WCHAR *v7; // rsi
  const WCHAR *v8; // rcx
  signed int LastError; // eax
  const WCHAR *v10; // rcx
  HANDLE v11; // rbx
  __int64 v12; // rax
  __int16 v13; // r8
  __int16 v14; // dx
  const char *v15; // r9
  float v16; // xmm6_4
  float v17; // xmm7_4
  float v18; // xmm8_4
  float v19; // xmm9_4
  float v20; // xmm10_4
  float v21; // xmm11_4
  float v22; // xmm5_4
  float v23; // xmm1_4
  int v24; // xmm2_4
  signed int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  const char *v29; // r9
  bool v30; // sf
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-E0h]
  _BYTE FileInformation[4]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD FileInformation_4; // [rsp+4Ch] [rbp-BCh] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE FileW; // [rsp+58h] [rbp-B0h] BYREF
  float v36[3]; // [rsp+60h] [rbp-A8h] BYREF
  float v37; // [rsp+6Ch] [rbp-9Ch]
  float v38; // [rsp+70h] [rbp-98h]
  float v39; // [rsp+74h] [rbp-94h]
  float v40; // [rsp+78h] [rbp-90h]
  float v41; // [rsp+7Ch] [rbp-8Ch]
  float v42; // [rsp+80h] [rbp-88h]
  float v43; // [rsp+88h] [rbp-80h] BYREF
  float v44; // [rsp+8Ch] [rbp-7Ch]
  float v45; // [rsp+90h] [rbp-78h]
  float v46[4]; // [rsp+98h] [rbp-70h] BYREF
  float v47; // [rsp+A8h] [rbp-60h] BYREF
  float v48; // [rsp+ACh] [rbp-5Ch]
  float v49; // [rsp+B0h] [rbp-58h]
  float v50[4]; // [rsp+B8h] [rbp-50h] BYREF
  float v51[3]; // [rsp+C8h] [rbp-40h] BYREF
  float v52[2]; // [rsp+D4h] [rbp-34h] BYREF
  int v53; // [rsp+DCh] [rbp-2Ch]
  float v54; // [rsp+E0h] [rbp-28h] BYREF
  int v55; // [rsp+E4h] [rbp-24h]
  float v56; // [rsp+E8h] [rbp-20h]
  float v57[10]; // [rsp+F0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]

  if ( *((_BYTE *)this + 44) )
  {
    if ( *((_BYTE *)this + 45) )
      return 0;
    v4 = 1146;
LABEL_60:
    v5 = -2147467259;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
    return (unsigned int)v5;
  }
  *((_BYTE *)this + 44) = 1;
  v5 = CDisplayMonitor::BuildColorTransformShimIccFileName(this, a2);
  if ( v5 < 0 )
  {
    v4 = 1155;
    goto LABEL_61;
  }
  v5 = 0;
  for ( i = 0; i < 3; ++i )
  {
    hFile = (HANDLE)-1LL;
    v7 = (const WCHAR *)((char *)this + 96);
    if ( *((_QWORD *)this + 15) <= 7u )
      v8 = (const WCHAR *)((char *)this + 96);
    else
      v8 = *(const WCHAR **)v7;
    FileW = CreateFileW(v8, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &hFile,
      &FileW);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      *((_BYTE *)this + 45) = 1;
      v5 = 0;
      goto LABEL_53;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError != 5 )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
          goto LABEL_53;
        v26 = 1423;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
          (const char *)(unsigned int)v5,
          dwCreationDisposition);
        goto LABEL_53;
      }
      goto LABEL_33;
    }
    if ( *((_QWORD *)this + 15) <= 7u )
      v10 = (const WCHAR *)((char *)this + 96);
    else
      v10 = *(const WCHAR **)v7;
    FileW = CreateFileW(v10, 0x1F01FFu, 4u, 0, 1u, 0x10000080u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &hFile,
      &FileW);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
    v11 = hFile;
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v25 = GetLastError();
      v5 = v25;
      if ( v25 != 80 )
      {
        if ( v25 > 0 )
          v5 = (unsigned __int16)v25 | 0x80070000;
        if ( v5 >= 0 )
          goto LABEL_53;
        v26 = 1220;
        goto LABEL_31;
      }
LABEL_33:
      Sleep(0xC8u);
      goto LABEL_34;
    }
    FileInformation[0] = 1;
    if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u) )
    {
      if ( *((_QWORD *)this + 15) > 7u )
        v7 = *(const WCHAR **)v7;
      DeleteFileW(v7);
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4D9,
             (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
             v29);
      goto LABEL_53;
    }
    std::_Mutex_base::lock((std::_Mutex_base *)qword_18009EEE0);
    v12 = *((_QWORD *)this + 7);
    v13 = __ROR2__(*((_WORD *)this + 26), 8);
    v14 = __ROR2__(*((_WORD *)this + 27), 8);
    dword_18009ECF4 = _byteswap_ulong(*((_DWORD *)this + 12));
    word_18009ECF8 = v13;
    word_18009ECFA = v14;
    qword_18009ECFC = v12;
    FileInformation_4 = 0;
    if ( !WriteFile(v11, qword_18009ECA0, 0x80u, &FileInformation_4, 0) )
    {
      v27 = 1268;
LABEL_43:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v27,
             (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
             v15);
LABEL_44:
      _Mtx_unlock((_Mtx_t)qword_18009EEE0);
LABEL_53:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      return (unsigned int)v5;
    }
    if ( FileInformation_4 != 128 )
    {
      v28 = 1269;
LABEL_40:
      v5 = -2147024883;
      goto LABEL_41;
    }
    v46[0] = *((float *)this + 6) / *((float *)this + 7);
    v46[1] = 1.0;
    v46[2] = fmaxf((float)((float)(1.0 - *((float *)this + 6)) - *((float *)this + 7)) / *((float *)this + 7), 0.0);
    MatrixMultiply(&v43, (const float (*const)[3])qword_18008FD90, v46);
    v43 = 0.99628443 / v43;
    v44 = 1.0204275 / v44;
    v45 = 0.81864434 / v45;
    v36[0] = v43 * 0.9869929;
    v36[1] = v44 * -0.1470543;
    v36[2] = v45 * 0.1599627;
    v37 = v43 * 0.43230531;
    v38 = v44 * 0.51836032;
    v39 = v45 * 0.049291201;
    v40 = v43 * -0.0085287001;
    v41 = v44 * 0.040042799;
    v42 = v45 * 0.96848673;
    MatrixMultiply((float (*const)[3])v57, (const float (*const)[3])v36, (const float (*const)[3])qword_18008FD90);
    v16 = *(float *)this / *((float *)this + 1);
    v51[0] = v16;
    v17 = *((float *)this + 2) / *((float *)this + 3);
    v51[1] = v17;
    v18 = *((float *)this + 4) / *((float *)this + 5);
    v51[2] = v18;
    v52[0] = 1.0;
    v52[1] = 1.0;
    v53 = 1065353216;
    v19 = fmaxf((float)((float)(1.0 - *(float *)this) - *((float *)this + 1)) / *((float *)this + 1), 0.0);
    v54 = v19;
    v20 = fmaxf((float)((float)(1.0 - *((float *)this + 2)) - *((float *)this + 3)) / *((float *)this + 3), 0.0);
    v55 = LODWORD(v20);
    v21 = fmaxf((float)((float)(1.0 - *((float *)this + 4)) - *((float *)this + 5)) / *((float *)this + 5), 0.0);
    v56 = v21;
    if ( !InvertMatrix((float (*const)[3])v36, (const float (*const)[3])v51) )
    {
      v5 = -2147467259;
      v28 = 1340;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\windows\\core\\color\\colorshimlib\\legacycolorshim.cxx",
        (const char *)(unsigned int)v5,
        dwCreationDisposition);
      goto LABEL_44;
    }
    MatrixMultiply(&v47, (const float (*const)[3])v36, v46);
    v36[0] = v16 * v47;
    v36[1] = v17 * v48;
    v36[2] = v18 * v49;
    v37 = v47;
    v38 = v48;
    v39 = v49;
    v40 = v47 * v19;
    v41 = v48 * v20;
    v42 = v49 * v21;
    MatrixMultiply((float (*const)[3])v51, (const float (*const)[3])v57, (const float (*const)[3])v36);
    v22 = v51[1];
    v51[1] = v52[0];
    v52[0] = v22;
    v23 = v51[2];
    v51[2] = v54;
    v54 = v23;
    v24 = v53;
    v53 = v55;
    v55 = v24;
    UpdateXYZTag(aXyz, v46);
    UpdateXYZTag(aXyz_0, v51);
    UpdateXYZTag(aXyz_1, v52);
    UpdateXYZTag(aXyz_2, &v54);
    v50[0] = 0.0;
    v50[1] = *((float *)this + 10);
    v50[2] = 0.0;
    UpdateXYZTag(aXyz_3, v50);
    if ( !WriteFile(v11, &unk_18009ED20, 0x1B4u, &FileInformation_4, 0) )
    {
      v27 = 1387;
      goto LABEL_43;
    }
    if ( FileInformation_4 != 436 )
    {
      v28 = 1388;
      goto LABEL_40;
    }
    FileInformation[0] = 0;
    if ( !SetFileInformationByHandle(v11, FileDispositionInfo, FileInformation, 1u) )
    {
      v27 = 1399;
      goto LABEL_43;
    }
    v5 = 0;
    _Mtx_unlock((_Mtx_t)qword_18009EEE0);
LABEL_34:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  }
  v30 = v5 < 0;
  if ( !v5 )
  {
    v4 = 1454;
    goto LABEL_60;
  }
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5 | 0x80070000;
    v30 = v5 < 0;
  }
  if ( v30 )
  {
    v4 = 1450;
    goto LABEL_61;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026c10  mov     rax, rsp
0x180026c13  mov     [rax+18h], rbx
0x180026c17  push    rbp
0x180026c18  push    rsi
0x180026c19  push    rdi
0x180026c1a  push    r12
0x180026c1c  push    r14
0x180026c1e  lea     rbp, [rax-0B8h]
0x180026c25  sub     rsp, 190h
0x180026c2c  movaps  xmmword ptr [rax-38h], xmm6
0x180026c30  movaps  xmmword ptr [rax-48h], xmm7
0x180026c34  movaps  xmmword ptr [rax-58h], xmm8
0x180026c39  movaps  xmmword ptr [rax-68h], xmm9
0x180026c3e  movaps  xmmword ptr [rax-78h], xmm10
0x180026c43  movaps  xmmword ptr [rax-88h], xmm11
0x180026c4b  movaps  xmmword ptr [rax-98h], xmm13
0x180026c53  mov     rax, cs:__security_cookie
0x180026c5a  xor     rax, rsp
0x180026c5d  mov     [rbp+0B0h+var_A0], rax
0x180026c61  mov     rdi, rcx
0x180026c64  cmp     byte ptr [rcx+2Ch], 0
0x180026c68  jz      short loc_180026C81
0x180026c6a  cmp     byte ptr [rcx+2Dh], 0
0x180026c6e  jz      short loc_180026C77
0x180026c70  xor     eax, eax
0x180026c72  jmp     loc_18002733B
0x180026c77  mov     edx, 47Ah; unsigned __int16 *
0x180026c7c  jmp     loc_18002731E
0x180026c81  mov     byte ptr [rcx+2Ch], 1
0x180026c85  call    ?BuildColorTransformShimIccFileName@CDisplayMonitor@@AEAAJPEBG@Z; CDisplayMonitor::BuildColorTransformShimIccFileName(ushort const *)
0x180026c8a  mov     ebx, eax
0x180026c8c  test    eax, eax
0x180026c8e  jns     short loc_180026C9A
0x180026c90  mov     edx, 483h
0x180026c95  jmp     loc_180027323
0x180026c9a  xor     ebx, ebx
0x180026c9c  xor     r14d, r14d
0x180026c9f  lea     r12, qword_18009EEE0
0x180026ca6  xorps   xmm13, xmm13
0x180026caa  cmp     r14d, 3
0x180026cae  jge     loc_1800272FF
0x180026cb4  mov     [rsp+1B0h+hFile], 0FFFFFFFFFFFFFFFFh
0x180026cbd  lea     rsi, [rdi+60h]
0x180026cc1  cmp     qword ptr [rdi+78h], 7
0x180026cc6  jbe     short loc_180026CCD
0x180026cc8  mov     rcx, [rsi]
0x180026ccb  jmp     short loc_180026CD0
0x180026ccd  mov     rcx, rsi; lpFileName
0x180026cd0  mov     [rsp+1B0h+hTemplateFile], 0; hTemplateFile
0x180026cd9  mov     [rsp+1B0h+dwFlagsAndAttributes], 10000080h; dwFlagsAndAttributes
0x180026ce1  mov     [rsp+1B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180026ce9  xor     r9d, r9d; lpSecurityAttributes
0x180026cec  mov     edx, 80000000h; dwDesiredAccess
0x180026cf1  lea     r8d, [r9+1]; dwShareMode
0x180026cf5  call    cs:__imp_CreateFileW
0x180026cfb  mov     [rsp+1B0h+var_160], rax
0x180026d00  lea     rdx, [rsp+1B0h+var_160]
0x180026d05  lea     rcx, [rsp+1B0h+hFile]
0x180026d0a  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180026d0f  lea     rcx, [rsp+1B0h+var_160]
0x180026d14  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026d19  mov     rax, [rsp+1B0h+hFile]
0x180026d1e  inc     rax
0x180026d21  test    rax, 0FFFFFFFFFFFFFFFEh
0x180026d27  jnz     loc_1800272ED
0x180026d2d  call    cs:__imp_GetLastError
0x180026d33  mov     ebx, eax
0x180026d35  cmp     eax, 2
0x180026d38  jnz     loc_180027214
0x180026d3e  cmp     qword ptr [rdi+78h], 7
0x180026d43  jbe     short loc_180026D4A
0x180026d45  mov     rcx, [rsi]
0x180026d48  jmp     short loc_180026D4D
0x180026d4a  mov     rcx, rsi; lpFileName
0x180026d4d  mov     [rsp+1B0h+hTemplateFile], 0; hTemplateFile
0x180026d56  mov     [rsp+1B0h+dwFlagsAndAttributes], 10000080h; dwFlagsAndAttributes
0x180026d5e  mov     [rsp+1B0h+dwCreationDisposition], 1; int
0x180026d66  xor     r9d, r9d; lpSecurityAttributes
0x180026d69  mov     edx, 1F01FFh; dwDesiredAccess
0x180026d6e  lea     r8d, [r9+4]; dwShareMode
0x180026d72  call    cs:__imp_CreateFileW
0x180026d78  mov     [rsp+1B0h+var_160], rax
0x180026d7d  lea     rdx, [rsp+1B0h+var_160]
0x180026d82  lea     rcx, [rsp+1B0h+hFile]
0x180026d87  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180026d8c  lea     rcx, [rsp+1B0h+var_160]
0x180026d91  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026d96  mov     rbx, [rsp+1B0h+hFile]
0x180026d9b  lea     rax, [rbx-1]
0x180026d9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026da3  ja      loc_1800271D2
0x180026da9  mov     byte ptr [rsp+1B0h+FileInformation], 1
0x180026dae  mov     r9d, 1; dwBufferSize
0x180026db4  lea     r8, [rsp+1B0h+FileInformation]; lpFileInformation
0x180026db9  lea     edx, [r9+3]; FileInformationClass
0x180026dbd  mov     rcx, rbx; hFile
0x180026dc0  call    cs:__imp_SetFileInformationByHandle
0x180026dc6  test    eax, eax
0x180026dc8  jz      loc_1800272A3
0x180026dce  mov     rcx, r12; this
0x180026dd1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180026dd6  mov     rax, [rdi+38h]
0x180026dda  movzx   r8d, word ptr [rdi+34h]
0x180026ddf  ror     r8w, 8
0x180026de4  movzx   edx, word ptr [rdi+36h]
0x180026de8  ror     dx, 8
0x180026dec  mov     ecx, [rdi+30h]
0x180026def  bswap   ecx
0x180026df1  mov     cs:dword_18009ECF4, ecx
0x180026df7  mov     cs:word_18009ECF8, r8w
0x180026dff  mov     cs:word_18009ECFA, dx
0x180026e06  mov     cs:qword_18009ECFC, rax
0x180026e0d  mov     dword ptr [rsp+1B0h+FileInformation+4], 0
0x180026e15  mov     qword ptr [rsp+1B0h+dwCreationDisposition], 0; int
0x180026e1e  lea     r9, [rsp+1B0h+FileInformation+4]; lpNumberOfBytesWritten
0x180026e23  mov     r8d, 80h; nNumberOfBytesToWrite
0x180026e29  lea     rdx, qword_18009ECA0; lpBuffer
0x180026e30  mov     rcx, rbx; hFile
0x180026e33  call    cs:__imp_WriteFile
0x180026e39  test    eax, eax
0x180026e3b  jz      loc_18002727E
0x180026e41  cmp     dword ptr [rsp+1B0h+FileInformation+4], 80h
0x180026e49  jnz     loc_18002725C
0x180026e4f  movss   xmm0, dword ptr [rdi+18h]
0x180026e54  divss   xmm0, dword ptr [rdi+1Ch]
0x180026e59  movss   [rbp+0B0h+var_120], xmm0
0x180026e5e  mov     [rbp+0B0h+var_11C], 3F800000h
0x180026e65  movss   xmm1, cs:__real@3f800000
0x180026e6d  subss   xmm1, dword ptr [rdi+18h]
0x180026e72  subss   xmm1, dword ptr [rdi+1Ch]
0x180026e77  divss   xmm1, dword ptr [rdi+1Ch]
0x180026e7c  maxss   xmm1, xmm13
0x180026e81  movss   [rbp+0B0h+var_118], xmm1
0x180026e86  lea     r8, [rbp+0B0h+var_120]; float *
0x180026e8a  lea     rdx, qword_18008FD90; float (*)[3]
0x180026e91  lea     rcx, [rbp+0B0h+var_130]; float *
0x180026e95  call    ?MatrixMultiply@@YAXQEAMQEAY02$$CBMQEBM@Z; MatrixMultiply(float * const,float const (* const)[3],float const * const)
0x180026e9a  movss   xmm4, cs:__real@3f7f0c7f
0x180026ea2  divss   xmm4, [rbp+0B0h+var_130]
0x180026ea7  movss   [rbp+0B0h+var_130], xmm4
0x180026eac  movss   xmm3, cs:__real@3f829d5e
0x180026eb4  divss   xmm3, [rbp+0B0h+var_12C]
0x180026eb9  movss   [rbp+0B0h+var_12C], xmm3
0x180026ebe  movss   xmm2, cs:__real@3f5192ad
0x180026ec6  divss   xmm2, [rbp+0B0h+var_128]
0x180026ecb  movss   [rbp+0B0h+var_128], xmm2
0x180026ed0  movaps  xmm0, xmm4
0x180026ed3  mulss   xmm0, cs:__real@3f7cab91
0x180026edb  movss   [rsp+1B0h+var_158], xmm0
0x180026ee1  movaps  xmm1, xmm3
0x180026ee4  mulss   xmm1, cs:__real@be169567
0x180026eec  movss   [rsp+1B0h+var_158+4], xmm1
0x180026ef2  movaps  xmm0, xmm2
0x180026ef5  mulss   xmm0, cs:__real@3e23cd43
0x180026efd  movss   [rsp+1B0h+var_158+8], xmm0
0x180026f03  movaps  xmm1, xmm4
0x180026f06  mulss   xmm1, cs:__real@3edd571f
0x180026f0e  movss   [rsp+1B0h+var_14C], xmm1
0x180026f14  movaps  xmm0, xmm3
0x180026f17  mulss   xmm0, cs:__real@3f04b343
0x180026f1f  movss   [rsp+1B0h+var_148], xmm0
0x180026f25  movaps  xmm1, xmm2
0x180026f28  mulss   xmm1, cs:__real@3d49e592
0x180026f30  movss   [rsp+1B0h+var_144], xmm1
0x180026f36  mulss   xmm4, cs:__real@bc0bbbf6
0x180026f3e  movss   [rsp+1B0h+var_140], xmm4
0x180026f44  mulss   xmm3, cs:__real@3d2403eb
0x180026f4c  movss   [rsp+1B0h+var_13C], xmm3
0x180026f52  mulss   xmm2, cs:__real@3f77eebf
0x180026f5a  movss   [rsp+1B0h+var_138], xmm2
0x180026f60  lea     r8, qword_18008FD90; float (*)[3]
0x180026f67  lea     rdx, [rsp+1B0h+var_158]; float (*)[3]
0x180026f6c  lea     rcx, [rbp+0B0h+var_C8]; float (*)[3]
0x180026f70  call    ?MatrixMultiply@@YAXQEAY02MQEAY02$$CBM1@Z; MatrixMultiply(float (* const)[3],float const (* const)[3],float const (* const)[3])
0x180026f75  movss   xmm6, dword ptr [rdi]
0x180026f79  divss   xmm6, dword ptr [rdi+4]
0x180026f7e  movss   [rbp+0B0h+var_F0], xmm6
0x180026f83  movss   xmm7, dword ptr [rdi+8]
0x180026f88  divss   xmm7, dword ptr [rdi+0Ch]
0x180026f8d  movss   [rbp+0B0h+var_F0+4], xmm7
0x180026f92  movss   xmm8, dword ptr [rdi+10h]
0x180026f98  divss   xmm8, dword ptr [rdi+14h]
0x180026f9e  movss   [rbp+0B0h+var_F0+8], xmm8
0x180026fa4  mov     [rbp+0B0h+var_E4], 3F800000h
0x180026fab  mov     [rbp+0B0h+var_E0], 3F800000h
0x180026fb2  mov     [rbp+0B0h+var_DC], 3F800000h
0x180026fb9  movss   xmm9, cs:__real@3f800000
0x180026fc2  subss   xmm9, dword ptr [rdi]
0x180026fc7  subss   xmm9, dword ptr [rdi+4]
0x180026fcd  divss   xmm9, dword ptr [rdi+4]
0x180026fd3  maxss   xmm9, xmm13
0x180026fd8  movss   [rbp+0B0h+var_D8], xmm9
0x180026fde  movss   xmm10, cs:__real@3f800000
0x180026fe7  subss   xmm10, dword ptr [rdi+8]
0x180026fed  subss   xmm10, dword ptr [rdi+0Ch]
0x180026ff3  divss   xmm10, dword ptr [rdi+0Ch]
0x180026ff9  maxss   xmm10, xmm13
0x180026ffe  movss   [rbp+0B0h+var_D4], xmm10
0x180027004  movss   xmm11, cs:__real@3f800000
0x18002700d  subss   xmm11, dword ptr [rdi+10h]
0x180027013  subss   xmm11, dword ptr [rdi+14h]
0x180027019  divss   xmm11, dword ptr [rdi+14h]
0x18002701f  maxss   xmm11, xmm13
0x180027024  movss   [rbp+0B0h+var_D0], xmm11
0x18002702a  lea     rdx, [rbp+0B0h+var_F0]; float (*)[3]
0x18002702e  lea     rcx, [rsp+1B0h+var_158]; float (*)[3]
0x180027033  call    ?InvertMatrix@@YA_NQEAY02MQEAY02$$CBM@Z; InvertMatrix(float (* const)[3],float const (* const)[3])
0x180027038  test    al, al
0x18002703a  jz      loc_180027250
0x180027040  lea     r8, [rbp+0B0h+var_120]; float *
0x180027044  lea     rdx, [rsp+1B0h+var_158]; float (*)[3]
0x180027049  lea     rcx, [rbp+0B0h+var_110]; float *
0x18002704d  call    ?MatrixMultiply@@YAXQEAMQEAY02$$CBMQEBM@Z; MatrixMultiply(float * const,float const (* const)[3],float const * const)
0x180027052  movss   xmm4, [rbp+0B0h+var_110]
0x180027057  mulss   xmm6, xmm4
0x18002705b  movss   [rsp+1B0h+var_158], xmm6
0x180027061  movss   xmm1, [rbp+0B0h+var_10C]
0x180027066  mulss   xmm7, xmm1
0x18002706a  movss   [rsp+1B0h+var_158+4], xmm7
0x180027070  movss   xmm0, [rbp+0B0h+var_108]
0x180027075  mulss   xmm8, xmm0
0x18002707a  movss   [rsp+1B0h+var_158+8], xmm8
0x180027081  movss   [rsp+1B0h+var_14C], xmm4
0x180027087  movss   [rsp+1B0h+var_148], xmm1
0x18002708d  movss   [rsp+1B0h+var_144], xmm0
0x180027093  mulss   xmm4, xmm9
0x180027098  movss   [rsp+1B0h+var_140], xmm4
0x18002709e  mulss   xmm1, xmm10
0x1800270a3  movss   [rsp+1B0h+var_13C], xmm1
0x1800270a9  mulss   xmm0, xmm11
0x1800270ae  movss   [rsp+1B0h+var_138], xmm0
0x1800270b4  lea     r8, [rsp+1B0h+var_158]; float (*)[3]
0x1800270b9  lea     rdx, [rbp+0B0h+var_C8]; float (*)[3]
0x1800270bd  lea     rcx, [rbp+0B0h+var_F0]; float (*)[3]
0x1800270c1  call    ?MatrixMultiply@@YAXQEAY02MQEAY02$$CBM1@Z; MatrixMultiply(float (* const)[3],float const (* const)[3],float const (* const)[3])
0x1800270c6  movss   xmm5, [rbp+0B0h+var_F0+4]
0x1800270cb  movss   xmm4, [rbp+0B0h+var_E4]
0x1800270d0  movss   [rbp+0B0h+var_F0+4], xmm4
0x1800270d5  movss   [rbp+0B0h+var_E4], xmm5
0x1800270da  movss   xmm1, [rbp+0B0h+var_F0+8]
0x1800270df  movss   xmm0, [rbp+0B0h+var_D8]
0x1800270e4  movss   [rbp+0B0h+var_F0+8], xmm0
0x1800270e9  movss   [rbp+0B0h+var_D8], xmm1
0x1800270ee  movss   xmm2, [rbp+0B0h+var_DC]
0x1800270f3  movss   xmm0, [rbp+0B0h+var_D4]
0x1800270f8  movss   [rbp+0B0h+var_DC], xmm0
0x1800270fd  movss   [rbp+0B0h+var_D4], xmm2
0x180027102  lea     rdx, [rbp+0B0h+var_120]; float *
0x180027106  lea     rcx, aXyz; "XYZ "
0x18002710d  call    ?UpdateXYZTag@@YAXPEAKQEBM@Z; UpdateXYZTag(ulong *,float const * const)
0x180027112  lea     rdx, [rbp+0B0h+var_F0]; float *
0x180027116  lea     rcx, aXyz_0; "XYZ "
0x18002711d  call    ?UpdateXYZTag@@YAXPEAKQEBM@Z; UpdateXYZTag(ulong *,float const * const)
0x180027122  lea     rdx, [rbp+0B0h+var_E4]; float *
0x180027126  lea     rcx, aXyz_1; "XYZ "
0x18002712d  call    ?UpdateXYZTag@@YAXPEAKQEBM@Z; UpdateXYZTag(ulong *,float const * const)
0x180027132  lea     rdx, [rbp+0B0h+var_D8]; float *
0x180027136  lea     rcx, aXyz_2; "XYZ "
0x18002713d  call    ?UpdateXYZTag@@YAXPEAKQEBM@Z; UpdateXYZTag(ulong *,float const * const)
0x180027142  mov     [rbp+0B0h+var_100], 0
0x180027149  movss   xmm2, dword ptr [rdi+28h]
0x18002714e  movss   [rbp+0B0h+var_FC], xmm2
0x180027153  mov     [rbp+0B0h+var_F8], 0
0x18002715a  lea     rdx, [rbp+0B0h+var_100]; float *
0x18002715e  lea     rcx, aXyz_3; "XYZ "
0x180027165  call    ?UpdateXYZTag@@YAXPEAKQEBM@Z; UpdateXYZTag(ulong *,float const * const)
0x18002716a  mov     qword ptr [rsp+1B0h+dwCreationDisposition], 0; lpOverlapped
0x180027173  lea     r9, [rsp+1B0h+FileInformation+4]; lpNumberOfBytesWritten
0x180027178  mov     r8d, 1B4h; nNumberOfBytesToWrite
0x18002717e  lea     rdx, unk_18009ED20; lpBuffer
0x180027185  mov     rcx, rbx; hFile
0x180027188  call    cs:__imp_WriteFile
0x18002718e  test    eax, eax
0x180027190  jz      loc_180027249
0x180027196  cmp     dword ptr [rsp+1B0h+FileInformation+4], 1B4h
0x18002719e  jnz     loc_180027242
0x1800271a4  mov     byte ptr [rsp+1B0h+FileInformation], 0
0x1800271a9  mov     r9d, 1; dwBufferSize
0x1800271af  lea     r8, [rsp+1B0h+FileInformation]; lpFileInformation
0x1800271b4  lea     edx, [r9+3]; FileInformationClass
0x1800271b8  mov     rcx, rbx; hFile
0x1800271bb  call    cs:__imp_SetFileInformationByHandle
0x1800271c1  test    eax, eax
0x1800271c3  jz      short loc_18002723B
0x1800271c5  xor     ebx, ebx
0x1800271c7  mov     rcx, r12; _Mtx_t
0x1800271ca  call    cs:__imp__Mtx_unlock
0x1800271d0  jmp     short loc_180027229
0x1800271d2  call    cs:__imp_GetLastError
0x1800271d8  mov     ebx, eax
0x1800271da  cmp     eax, 50h ; 'P'
0x1800271dd  jz      short loc_18002721D
0x1800271df  test    eax, eax
0x1800271e1  jle     short loc_1800271EC
0x1800271e3  movzx   ebx, ax
0x1800271e6  or      ebx, 80070000h
0x1800271ec  test    ebx, ebx
0x1800271ee  jns     loc_1800272F3
0x1800271f4  mov     edx, 4C4h; void *
0x1800271f9  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\color\\color"...
  ... truncated ...
```
