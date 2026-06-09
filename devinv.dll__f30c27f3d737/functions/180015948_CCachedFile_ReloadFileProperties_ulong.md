# CCachedFile::_ReloadFileProperties(ulong)

- ea: `0x180015948`
- end: `0x18001621d`
- name: `?_ReloadFileProperties@CCachedFile@@AEAAJK@Z`
- size: `2261`
- prototype: `__int64 __fastcall(CCachedFile *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180014ce8`
- `0x18001509c`
- `0x180015268`

## callees

- `0x180006d02`
- `0x180006eb8`
- `0x180007014`
- `0x1800103e0`
- `0x180015768`
- `0x180015948`
- `0x180016224`
- `0x180053edc`
- `0x1800544e8`
- `0x180054d28`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800161fa`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800161da`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800161da`

## string_xrefs

- `0x1800159e6`: `CCachedFile::_ReloadFileProperties`
- `0x180015b53`: `CCachedFile::_ReloadFileProperties`
- `0x180015c07`: `CCachedFile::_ReloadFileProperties`
- `0x180015c42`: `CCachedFile::_ReloadFileProperties`
- `0x180015e24`: `CCachedFile::_ReloadFileProperties`

## pseudocode

```c
__int64 __fastcall CCachedFile::_ReloadFileProperties(CCachedFile *this, char a2)
{
  unsigned int FileVersions; // r14d
  char *v5; // r15
  char *v6; // rax
  FILE *v7; // rax
  char *v8; // r13
  FILE *v9; // rax
  FILE *v10; // rax
  const WCHAR *v11; // rcx
  _QWORD *v12; // r15
  char *v13; // r15
  char *v14; // rax
  FILE *v15; // rax
  char *v16; // r13
  FILE *v17; // rax
  FILE *v18; // rax
  char *v19; // r14
  char *v20; // rax
  __int64 v21; // r8
  FILE *v22; // rax
  char *v23; // r15
  FILE *v24; // rax
  FILE *v25; // rax
  __int64 v26; // r8
  _WORD *v27; // r15
  __int64 v28; // r8
  _WORD *v29; // r15
  __int64 v30; // r8
  _WORD *v31; // r15
  const unsigned __int16 *v32; // rcx
  int FileImageInfo; // eax
  char *v34; // r15
  char *v35; // rax
  FILE *v36; // rax
  char *v37; // r13
  FILE *v38; // rax
  FILE *v39; // rax
  char *v40; // rax
  FILE *v41; // rax
  char *v42; // r13
  FILE *v43; // rax
  FILE *v44; // rax
  int v45; // ecx
  char *v46; // r15
  char *v47; // rax
  FILE *v48; // rax
  char *v49; // r13
  FILE *v50; // rax
  FILE *v51; // rax
  FILE *v53; // rax
  FILE *v54; // rax
  FILE *v55; // rax
  HANDLE hObject[2]; // [rsp+30h] [rbp-58h] BYREF
  LPCVOID lpBaseAddress[2]; // [rsp+40h] [rbp-48h]
  __int64 v58; // [rsp+50h] [rbp-38h]

  *(_OWORD *)hObject = 0;
  *(_OWORD *)lpBaseAddress = 0;
  v58 = 0;
  *((_DWORD *)this + 265) = 1;
  if ( (a2 & 1) != 0 && (*((_BYTE *)this + 904) & 1) == 0 )
  {
    FileVersions = CCachedFile::_ComputeFileId(this);
    if ( (FileVersions & 0x80000000) != 0 )
    {
      v5 = (char *)this + 8;
      if ( *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 4) <= 7u )
          v6 = (char *)this + 8;
        else
          v6 = *(char **)v5;
      }
      else
      {
        v6 = 0;
      }
      AslLogCallPrintf(
        2,
        "CCachedFile::_ReloadFileProperties",
        583,
        "Failed getting FileId for [%ws] 0x%08x",
        v6,
        FileVersions);
      if ( EnableDevInvStdErrLog )
      {
        v7 = o___acrt_iob_func_0(2u);
        fprintf(v7, "Error: %s, %u: ", "CCachedFile::_ReloadFileProperties", 583);
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) <= 7u )
            v8 = (char *)this + 8;
          else
            v8 = *(char **)v5;
        }
        else
        {
          v8 = 0;
        }
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "Failed getting FileId for [%ws] 0x%08x", v8, FileVersions);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) > 7u )
            v5 = *(char **)v5;
        }
        else
        {
          v5 = 0;
        }
        TraceMessageCallback(0x2000000, "Failed getting FileId for [%ws] 0x%08x", v5, FileVersions);
      }
      goto LABEL_151;
    }
    *((_DWORD *)this + 226) |= 1u;
  }
  if ( (a2 & 2) != 0 && (*((_BYTE *)this + 904) & 2) == 0 )
  {
    v11 = (const WCHAR *)((char *)this + 1008);
    if ( *((_QWORD *)this + 129) > 7u )
      v11 = *(const WCHAR **)v11;
    v12 = (_QWORD *)((char *)this + 152);
    FileVersions = GetFileVersions(v11, (__int64)this + 296);
    if ( FileVersions + 2147023084 <= 1 )
    {
      v19 = (char *)this + 8;
      if ( *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 4) <= 7u )
          v20 = (char *)this + 8;
        else
          v20 = *(char **)v19;
      }
      else
      {
        v20 = 0;
      }
      AslLogCallPrintf(
        2,
        "CCachedFile::_ReloadFileProperties",
        606,
        "File [%ws] does not have a version resource.",
        v20);
      if ( EnableDevInvStdErrLog )
      {
        v22 = o___acrt_iob_func_0(2u);
        fprintf(v22, "Warning: %s, %u: ", "CCachedFile::_ReloadFileProperties", 606);
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) <= 7u )
            v23 = (char *)this + 8;
          else
            v23 = *(char **)v19;
        }
        else
        {
          v23 = 0;
        }
        v24 = o___acrt_iob_func_0(2u);
        fprintf(v24, "File [%ws] does not have a version resource.", v23);
        v25 = o___acrt_iob_func_0(2u);
        fprintf(v25, "\n");
        v12 = (_QWORD *)((char *)this + 152);
      }
      if ( g_DeviceMapLogFunction )
      {
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) > 7u )
            v19 = *(char **)v19;
        }
        else
        {
          v19 = 0;
        }
        TraceMessageCallback(50331648, "File [%ws] does not have a version resource.", v19);
      }
      try
      {
        if ( v12[3] < 7u )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v12,
            7,
            v21,
            L"Missing");
        }
        else
        {
          if ( v12[3] > 7u )
            v12 = (_QWORD *)*v12;
          *((_QWORD *)this + 21) = 7;
          memmove_0(v12, L"Missing", 0xEu);
          *((_WORD *)v12 + 7) = 0;
        }
        if ( *((_QWORD *)this + 28) < 7u )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char *)this + 200,
            7,
            v26,
            L"Missing");
        }
        else
        {
          if ( *((_QWORD *)this + 28) <= 7u )
            v27 = (_WORD *)((char *)this + 200);
          else
            v27 = (_WORD *)*((_QWORD *)this + 25);
          *((_QWORD *)this + 27) = 7;
          memmove_0(v27, L"Missing", 0xEu);
          v27[7] = 0;
        }
        if ( *((_QWORD *)this + 34) < 7u )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char *)this + 248,
            7,
            v28,
            L"Missing");
        }
        else
        {
          if ( *((_QWORD *)this + 34) <= 7u )
            v29 = (_WORD *)((char *)this + 248);
          else
            v29 = (_WORD *)*((_QWORD *)this + 31);
          *((_QWORD *)this + 33) = 7;
          memmove_0(v29, L"Missing", 0xEu);
          v29[7] = 0;
        }
        if ( *((_QWORD *)this + 40) < 7u )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char *)this + 296,
            7,
            v30,
            L"Missing");
        }
        else
        {
          if ( *((_QWORD *)this + 40) <= 7u )
            v31 = (_WORD *)((char *)this + 296);
          else
            v31 = (_WORD *)*((_QWORD *)this + 37);
          *((_QWORD *)this + 39) = 7;
          memmove_0(v31, L"Missing", 0xEu);
          v31[7] = 0;
        }
      }
      catch ( std::bad_alloc )
      {
        AslLogCallPrintf(2, "CCachedFile::_ReloadFileProperties", 617, "Out of memory");
        if ( EnableDevInvStdErrLog )
        {
          v53 = o___acrt_iob_func_0(2u);
          fprintf(v53, "Error: %s, %u: ", "CCachedFile::_ReloadFileProperties", 617);
          v54 = o___acrt_iob_func_0(2u);
          fprintf(v54, "Out of memory");
          v55 = o___acrt_iob_func_0(2u);
          fprintf(v55, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Out of memory");
        FileVersions = -2147024888;
        goto LABEL_158;
      }
    }
    else if ( (FileVersions & 0x80000000) != 0 )
    {
      v13 = (char *)this + 8;
      if ( *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 4) <= 7u )
          v14 = (char *)this + 8;
        else
          v14 = *(char **)v13;
      }
      else
      {
        v14 = 0;
      }
      AslLogCallPrintf(
        2,
        "CCachedFile::_ReloadFileProperties",
        633,
        "Failed getting file version for [%ws] 0x%08x",
        v14,
        FileVersions);
      if ( EnableDevInvStdErrLog )
      {
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "Error: %s, %u: ", "CCachedFile::_ReloadFileProperties", 633);
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) <= 7u )
            v16 = (char *)this + 8;
          else
            v16 = *(char **)v13;
        }
        else
        {
          v16 = 0;
        }
        v17 = o___acrt_iob_func_0(2u);
        fprintf(v17, "Failed getting file version for [%ws] 0x%08x", v16, FileVersions);
        v18 = o___acrt_iob_func_0(2u);
        fprintf(v18, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) > 7u )
            v13 = *(char **)v13;
        }
        else
        {
          v13 = 0;
        }
        TraceMessageCallback(0x2000000, "Failed getting file version for [%ws] 0x%08x", v13, FileVersions);
      }
      goto LABEL_151;
    }
    *((_DWORD *)this + 226) |= 2u;
  }
  if ( (a2 & 4) == 0 )
  {
LABEL_157:
    FileVersions = 0;
    goto LABEL_158;
  }
  if ( *((_QWORD *)this + 129) <= 7u )
    v32 = (const unsigned __int16 *)((char *)this + 1008);
  else
    v32 = (const unsigned __int16 *)*((_QWORD *)this + 126);
  FileImageInfo = GetFileImageInfo(v32, (struct _FILE_IMAGE_INFO *)hObject);
  FileVersions = FileImageInfo;
  if ( FileImageInfo >= 0 )
  {
    v45 = *((_DWORD *)this + 226);
    if ( (*((_BYTE *)this + 904) & 0xC) != 0xC )
    {
      FileVersions = CCachedFile::_ReloadPEProperties(this, (struct _FILE_IMAGE_INFO *)hObject);
      if ( (FileVersions & 0x80000000) != 0 )
      {
        v46 = (char *)this + 8;
        if ( *((_QWORD *)this + 3) )
        {
          if ( *((_QWORD *)this + 4) <= 7u )
            v47 = (char *)this + 8;
          else
            v47 = *(char **)v46;
        }
        else
        {
          v47 = 0;
        }
        AslLogCallPrintf(
          2,
          "CCachedFile::_ReloadFileProperties",
          681,
          "Failed getting file image information for [%ws] 0x%08x",
          v47,
          FileVersions);
        if ( EnableDevInvStdErrLog )
        {
          v48 = o___acrt_iob_func_0(2u);
          fprintf(v48, "Error: %s, %u: ", "CCachedFile::_ReloadFileProperties", 681);
          if ( *((_QWORD *)this + 3) )
          {
            if ( *((_QWORD *)this + 4) <= 7u )
              v49 = (char *)this + 8;
            else
              v49 = *(char **)v46;
          }
          else
          {
            v49 = 0;
          }
          v50 = o___acrt_iob_func_0(2u);
          fprintf(v50, "Failed getting file image information for [%ws] 0x%08x", v49, FileVersions);
          v51 = o___acrt_iob_func_0(2u);
          fprintf(v51, "\n");
        }
        if ( g_DeviceMapLogFunction )
        {
          if ( *((_QWORD *)this + 3) )
          {
            if ( *((_QWORD *)this + 4) > 7u )
              v46 = *(char **)v46;
          }
          else
          {
            v46 = 0;
          }
          TraceMessageCallback(0x2000000, "Failed getting file image information for [%ws] 0x%08x", v46, FileVersions);
        }
        goto LABEL_151;
      }
      *((_DWORD *)this + 226) |= 0xCu;
      v45 = *((_DWORD *)this + 226);
    }
    if ( (v45 & 0x10) == 0 )
    {
      *((_DWORD *)this + 250) = 0;
      GetDriverSignInfo(hObject[0], (unsigned __int16 *)this + 172, (__int64)this + 392);
      *((_DWORD *)this + 226) |= 0x10u;
    }
    goto LABEL_157;
  }
  v34 = (char *)this + 8;
  if ( (unsigned int)(FileImageInfo + 2147024894) <= 1 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      if ( *((_QWORD *)this + 4) <= 7u )
        v40 = (char *)this + 8;
      else
        v40 = *(char **)v34;
    }
    else
    {
      v40 = 0;
    }
    AslLogCallPrintf(
      2,
      "CCachedFile::_ReloadFileProperties",
      655,
      "GetFileImageInfo failed for for [%ws] 0x%08x",
      v40,
      FileVersions);
    if ( EnableDevInvStdErrLog )
    {
      v41 = o___acrt_iob_func_0(2u);
      fprintf(v41, "Warning: %s, %u: ", "CCachedFile::_ReloadFileProperties", 655);
      if ( *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 4) <= 7u )
          v42 = (char *)this + 8;
        else
          v42 = *(char **)v34;
      }
      else
      {
        v42 = 0;
      }
      v43 = o___acrt_iob_func_0(2u);
      fprintf(v43, "GetFileImageInfo failed for for [%ws] 0x%08x", v42, FileVersions);
      v44 = o___acrt_iob_func_0(2u);
      fprintf(v44, "\n");
    }
    if ( g_DeviceMapLogFunction )
    {
      if ( *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 4) > 7u )
          v34 = *(char **)v34;
      }
      else
      {
        v34 = 0;
      }
      TraceMessageCallback(50331648, "GetFileImageInfo failed for for [%ws] 0x%08x", v34, FileVersions);
    }
    goto LABEL_151;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_QWORD *)this + 4) <= 7u )
      v35 = (char *)this + 8;
    else
      v35 = *(char **)v34;
  }
  else
  {
    v35 = 0;
  }
  AslLogCallPrintf(
    2,
    "CCachedFile::_ReloadFileProperties",
    659,
    "GetFileImageInfo failed for for [%ws] 0x%08x",
    v35,
    FileVersions);
  if ( EnableDevInvStdErrLog )
  {
    v36 = o___acrt_iob_func_0(2u);
    fprintf(v36, "Error: %s, %u: ", "CCachedFile::_ReloadFileProperties", 659);
    if ( *((_QWORD *)this + 3) )
    {
      if ( *((_QWORD *)this + 4) <= 7u )
        v37 = (char *)this + 8;
      else
        v37 = *(char **)v34;
    }
    else
    {
      v37 = 0;
    }
    v38 = o___acrt_iob_func_0(2u);
    fprintf(v38, "GetFileImageInfo failed for for [%ws] 0x%08x", v37, FileVersions);
    v39 = o___acrt_iob_func_0(2u);
    fprintf(v39, "\n");
  }
  if ( !g_DeviceMapLogFunction )
  {
LABEL_151:
    if ( FileVersions == -2147024893 || FileVersions == -2147024894 )
      *((_DWORD *)this + 226) = 32;
    goto LABEL_158;
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_QWORD *)this + 4) > 7u )
      v34 = *(char **)v34;
  }
  else
  {
    v34 = 0;
  }
  TraceMessageCallback(0x2000000, "GetFileImageInfo failed for for [%ws] 0x%08x", v34, FileVersions);
LABEL_158:
  if ( lpBaseAddress[1] )
    UnmapViewOfFile(lpBaseAddress[1]);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  return FileVersions;
}

```

## disassembly

```asm
0x180015948  mov     [rsp+arg_0], rbx
0x18001594d  mov     [rsp+arg_10], rsi
0x180015952  mov     [rsp+arg_8], edx
0x180015956  push    rdi
0x180015957  push    r12
0x180015959  push    r13
0x18001595b  push    r14
0x18001595d  push    r15
0x18001595f  sub     rsp, 60h
0x180015963  mov     esi, edx
0x180015965  mov     rdi, rcx
0x180015968  xorps   xmm0, xmm0
0x18001596b  xor     eax, eax
0x18001596d  movups  xmmword ptr [rsp+88h+hObject], xmm0
0x180015972  movups  xmmword ptr [rsp+88h+lpBaseAddress], xmm0
0x180015977  mov     [rsp+88h+var_38], rax
0x18001597c  lea     r13d, [rax+1]
0x180015980  mov     [rcx+424h], r13d
0x180015987  test    r13b, dl
0x18001598a  jz      loc_180015AA9
0x180015990  test    [rcx+388h], r13b
0x180015997  jnz     loc_180015AA9
0x18001599d  call    ?_ComputeFileId@CCachedFile@@AEAAJXZ; CCachedFile::_ComputeFileId(void)
0x1800159a2  mov     r14d, eax
0x1800159a5  xor     ebx, ebx
0x1800159a7  test    eax, eax
0x1800159a9  jns     loc_180015AA0
0x1800159af  lea     r15, [rdi+8]
0x1800159b3  lea     esi, [rbx+7]
0x1800159b6  cmp     [rdi+18h], rbx
0x1800159ba  jz      short loc_1800159CC
0x1800159bc  cmp     [r15+18h], rsi
0x1800159c0  jbe     short loc_1800159C7
0x1800159c2  mov     rax, [r15]
0x1800159c5  jmp     short loc_1800159CF
0x1800159c7  mov     rax, r15
0x1800159ca  jmp     short loc_1800159CF
0x1800159cc  mov     rax, rbx
0x1800159cf  mov     dword ptr [rsp+88h+var_60], r14d
0x1800159d4  mov     [rsp+88h+pvObject], rax
0x1800159d9  lea     r9, aFailedGettingF_1; "Failed getting FileId for [%ws] 0x%08x"
0x1800159e0  mov     r8d, 247h
0x1800159e6  lea     r13, aCcachedfileRel; "CCachedFile::_ReloadFileProperties"
0x1800159ed  mov     rdx, r13
0x1800159f0  mov     r12d, 2
0x1800159f6  mov     ecx, r12d
0x1800159f9  call    AslLogCallPrintf
0x1800159fe  cmp     cs:EnableDevInvStdErrLog, ebx
0x180015a04  jz      short loc_180015A73
0x180015a06  mov     ecx, r12d; Ix
0x180015a09  call    _o___acrt_iob_func_0
0x180015a0e  mov     rcx, rax; Stream
0x180015a11  mov     r9d, 247h
0x180015a17  mov     r8, r13
0x180015a1a  lea     rdx, Format; "Error: %s, %u: "
0x180015a21  call    fprintf
0x180015a26  cmp     [rdi+18h], rbx
0x180015a2a  jz      short loc_180015A3C
0x180015a2c  cmp     [r15+18h], rsi
0x180015a30  jbe     short loc_180015A37
0x180015a32  mov     r13, [r15]
0x180015a35  jmp     short loc_180015A3F
0x180015a37  mov     r13, r15
0x180015a3a  jmp     short loc_180015A3F
0x180015a3c  mov     r13, rbx
0x180015a3f  mov     ecx, r12d; Ix
0x180015a42  call    _o___acrt_iob_func_0
0x180015a47  mov     r9d, r14d
0x180015a4a  mov     r8, r13
0x180015a4d  lea     rdx, aFailedGettingF_1; "Failed getting FileId for [%ws] 0x%08x"
0x180015a54  mov     rcx, rax; Stream
0x180015a57  call    fprintf
0x180015a5c  mov     ecx, r12d; Ix
0x180015a5f  call    _o___acrt_iob_func_0
0x180015a64  mov     rcx, rax; Stream
0x180015a67  lea     rdx, asc_18011EAD8; "\n"
0x180015a6e  call    fprintf
0x180015a73  cmp     cs:g_DeviceMapLogFunction, rbx
0x180015a7a  jz      loc_180016157
0x180015a80  cmp     [rdi+18h], rbx
0x180015a84  jz      short loc_180015A91
0x180015a86  cmp     [r15+18h], rsi
0x180015a8a  jbe     short loc_180015A94
0x180015a8c  mov     r15, [r15]
0x180015a8f  jmp     short loc_180015A94
0x180015a91  mov     r15, rbx
0x180015a94  lea     rdx, aFailedGettingF_1; "Failed getting FileId for [%ws] 0x%08x"
0x180015a9b  jmp     loc_180016147
0x180015aa0  or      [rdi+388h], r13d
0x180015aa7  jmp     short loc_180015AAB
0x180015aa9  xor     ebx, ebx
0x180015aab  mov     r12d, 2
0x180015ab1  test    r12b, sil
0x180015ab4  jz      loc_180015E1F
0x180015aba  test    [rdi+388h], r12b
0x180015ac1  jnz     loc_180015E1F
0x180015ac7  lea     rcx, [rdi+3F0h]
0x180015ace  lea     esi, [r12+5]
0x180015ad3  cmp     [rcx+18h], rsi
0x180015ad7  jbe     short loc_180015ADC
0x180015ad9  mov     rcx, [rcx]; lptstrFilename
0x180015adc  lea     rax, [rdi+128h]
0x180015ae3  lea     r9, [rdi+0F8h]
0x180015aea  lea     r8, [rdi+0C8h]
0x180015af1  lea     r15, [rdi+98h]
0x180015af8  mov     [rsp+88h+pvObject], rax; __int64
0x180015afd  mov     rdx, r15
0x180015b00  call    ?GetFileVersions@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; GetFileVersions(ushort const *,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x180015b05  mov     r14d, eax
0x180015b08  add     eax, 7FF8F8ECh
0x180015b0d  cmp     eax, r13d
0x180015b10  jbe     loc_180015C13
0x180015b16  test    r14d, r14d
0x180015b19  jns     loc_180015C07
0x180015b1f  lea     r15, [rdi+8]
0x180015b23  cmp     [rdi+18h], rbx
0x180015b27  jz      short loc_180015B39
0x180015b29  cmp     [r15+18h], rsi
0x180015b2d  jbe     short loc_180015B34
0x180015b2f  mov     rax, [r15]
0x180015b32  jmp     short loc_180015B3C
0x180015b34  mov     rax, r15
0x180015b37  jmp     short loc_180015B3C
0x180015b39  mov     rax, rbx
0x180015b3c  mov     dword ptr [rsp+88h+var_60], r14d
0x180015b41  mov     [rsp+88h+pvObject], rax
0x180015b46  lea     r9, aFailedGettingF; "Failed getting file version for [%ws] 0"...
0x180015b4d  mov     r8d, 279h
0x180015b53  lea     r13, aCcachedfileRel; "CCachedFile::_ReloadFileProperties"
0x180015b5a  mov     rdx, r13
0x180015b5d  mov     ecx, r12d
0x180015b60  call    AslLogCallPrintf
0x180015b65  cmp     cs:EnableDevInvStdErrLog, ebx
0x180015b6b  jz      short loc_180015BDA
0x180015b6d  mov     ecx, r12d; Ix
0x180015b70  call    _o___acrt_iob_func_0
0x180015b75  mov     rcx, rax; Stream
0x180015b78  mov     r9d, 279h
0x180015b7e  mov     r8, r13
0x180015b81  lea     rdx, Format; "Error: %s, %u: "
0x180015b88  call    fprintf
0x180015b8d  cmp     [rdi+18h], rbx
0x180015b91  jz      short loc_180015BA3
0x180015b93  cmp     [r15+18h], rsi
0x180015b97  jbe     short loc_180015B9E
0x180015b99  mov     r13, [r15]
0x180015b9c  jmp     short loc_180015BA6
0x180015b9e  mov     r13, r15
0x180015ba1  jmp     short loc_180015BA6
0x180015ba3  mov     r13, rbx
0x180015ba6  mov     ecx, r12d; Ix
0x180015ba9  call    _o___acrt_iob_func_0
0x180015bae  mov     r9d, r14d
0x180015bb1  mov     r8, r13
0x180015bb4  lea     rdx, aFailedGettingF; "Failed getting file version for [%ws] 0"...
0x180015bbb  mov     rcx, rax; Stream
0x180015bbe  call    fprintf
0x180015bc3  mov     ecx, r12d; Ix
0x180015bc6  call    _o___acrt_iob_func_0
0x180015bcb  mov     rcx, rax; Stream
0x180015bce  lea     rdx, asc_18011EAD8; "\n"
0x180015bd5  call    fprintf
0x180015bda  cmp     cs:g_DeviceMapLogFunction, rbx
0x180015be1  jz      loc_180016157
0x180015be7  cmp     [rdi+18h], rbx
0x180015beb  jz      short loc_180015BF8
0x180015bed  cmp     [r15+18h], rsi
0x180015bf1  jbe     short loc_180015BFB
0x180015bf3  mov     r15, [r15]
0x180015bf6  jmp     short loc_180015BFB
0x180015bf8  mov     r15, rbx
0x180015bfb  lea     rdx, aFailedGettingF; "Failed getting file version for [%ws] 0"...
0x180015c02  jmp     loc_180016147
0x180015c07  lea     r13, aCcachedfileRel; "CCachedFile::_ReloadFileProperties"
0x180015c0e  jmp     loc_180015E09
0x180015c13  lea     r14, [rdi+8]
0x180015c17  cmp     [rdi+18h], rbx
0x180015c1b  jz      short loc_180015C2D
0x180015c1d  cmp     [r14+18h], rsi
0x180015c21  jbe     short loc_180015C28
0x180015c23  mov     rax, [r14]
0x180015c26  jmp     short loc_180015C30
0x180015c28  mov     rax, r14
0x180015c2b  jmp     short loc_180015C30
0x180015c2d  mov     rax, rbx
0x180015c30  mov     [rsp+88h+pvObject], rax
0x180015c35  lea     r9, aFileWsDoesNotH; "File [%ws] does not have a version reso"...
0x180015c3c  mov     r8d, 25Eh
0x180015c42  lea     r13, aCcachedfileRel; "CCachedFile::_ReloadFileProperties"
0x180015c49  mov     rdx, r13
0x180015c4c  mov     ecx, r12d
0x180015c4f  call    AslLogCallPrintf
0x180015c54  cmp     cs:EnableDevInvStdErrLog, ebx
0x180015c5a  jz      short loc_180015CCD
0x180015c5c  mov     ecx, r12d; Ix
0x180015c5f  call    _o___acrt_iob_func_0
0x180015c64  mov     rcx, rax; Stream
0x180015c67  mov     r9d, 25Eh
0x180015c6d  mov     r8, r13
0x180015c70  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180015c77  call    fprintf
0x180015c7c  cmp     [rdi+18h], rbx
0x180015c80  jz      short loc_180015C92
0x180015c82  cmp     [r14+18h], rsi
0x180015c86  jbe     short loc_180015C8D
0x180015c88  mov     r15, [r14]
0x180015c8b  jmp     short loc_180015C95
0x180015c8d  mov     r15, r14
0x180015c90  jmp     short loc_180015C95
0x180015c92  mov     r15, rbx
0x180015c95  mov     ecx, r12d; Ix
0x180015c98  call    _o___acrt_iob_func_0
0x180015c9d  mov     r8, r15
0x180015ca0  lea     rdx, aFileWsDoesNotH; "File [%ws] does not have a version reso"...
0x180015ca7  mov     rcx, rax; Stream
0x180015caa  call    fprintf
0x180015caf  mov     ecx, r12d; Ix
0x180015cb2  call    _o___acrt_iob_func_0
0x180015cb7  mov     rcx, rax; Stream
0x180015cba  lea     rdx, asc_18011EAD8; "\n"
0x180015cc1  call    fprintf
0x180015cc6  lea     r15, [rdi+98h]
0x180015ccd  cmp     cs:g_DeviceMapLogFunction, rbx
0x180015cd4  jz      short loc_180015CFF
0x180015cd6  cmp     [rdi+18h], rbx
0x180015cda  jz      short loc_180015CE7
0x180015cdc  cmp     [r14+18h], rsi
0x180015ce0  jbe     short loc_180015CEA
0x180015ce2  mov     r14, [r14]
0x180015ce5  jmp     short loc_180015CEA
0x180015ce7  mov     r14, rbx
0x180015cea  mov     r8, r14
0x180015ced  lea     rdx, aFileWsDoesNotH; "File [%ws] does not have a version reso"...
0x180015cf4  mov     ecx, 3000000h
0x180015cf9  call    TraceMessageCallback
0x180015cfe  nop
0x180015cff  cmp     [r15+18h], rsi
0x180015d03  jb      short loc_180015D30
0x180015d05  jbe     short loc_180015D0A
0x180015d07  mov     r15, [r15]
0x180015d0a  mov     [rdi+0A8h], rsi
0x180015d11  mov     r8d, 0Eh; Size
0x180015d17  lea     r14, aMissing; "Missing"
0x180015d1e  mov     rdx, r14; Src
0x180015d21  mov     rcx, r15; void *
0x180015d24  call    memmove_0
0x180015d29  mov     [r15+0Eh], bx
0x180015d2e  jmp     short loc_180015D45
0x180015d30  lea     r14, aMissing; "Missing"
0x180015d37  mov     r9, r14
0x180015d3a  mov     rdx, rsi
0x180015d3d  mov     rcx, r15
0x180015d40  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015d45  lea     rax, [rdi+0C8h]
0x180015d4c  cmp     [rax+18h], rsi
0x180015d50  jb      short loc_180015D78
0x180015d52  jbe     short loc_180015D59
0x180015d54  mov     r15, [rax]
0x180015d57  jmp     short loc_180015D5C
0x180015d59  mov     r15, rax
0x180015d5c  mov     [rax+10h], rsi
0x180015d60  mov     r8d, 0Eh; Size
0x180015d66  mov     rdx, r14; Src
0x180015d69  mov     rcx, r15; void *
0x180015d6c  call    memmove_0
0x180015d71  mov     [r15+0Eh], bx
0x180015d76  jmp     short loc_180015D86
0x180015d78  mov     r9, r14
0x180015d7b  mov     rdx, rsi
0x180015d7e  mov     rcx, rax
0x180015d81  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015d86  lea     rax, [rdi+0F8h]
0x180015d8d  cmp     [rax+18h], rsi
0x180015d91  jb      short loc_180015DB9
0x180015d93  jbe     short loc_180015D9A
0x180015d95  mov     r15, [rax]
0x180015d98  jmp     short loc_180015D9D
0x180015d9a  mov     r15, rax
0x180015d9d  mov     [rax+10h], rsi
0x180015da1  mov     r8d, 0Eh; Size
0x180015da7  mov     rdx, r14; Src
0x180015daa  mov     rcx, r15; void *
0x180015dad  call    memmove_0
0x180015db2  mov     [r15+0Eh], bx
0x180015db7  jmp     short loc_180015DC7
0x180015db9  mov     r9, r14
0x180015dbc  mov     rdx, rsi
0x180015dbf  mov     rcx, rax
0x180015dc2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015dc7  lea     rax, [rdi+128h]
0x180015dce  cmp     [rax+18h], rsi
0x180015dd2  jb      short loc_180015DFA
0x180015dd4  jbe     short loc_180015DDB
0x180015dd6  mov     r15, [rax]
0x180015dd9  jmp     short loc_180015DDE
0x180015ddb  mov     r15, rax
0x180015dde  mov     [rax+10h], rsi
0x180015de2  mov     r8d, 0Eh; Size
0x180015de8  mov     rdx, r14; Src
0x180015deb  mov     rcx, r15; void *
  ... truncated ...
```
