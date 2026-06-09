# CompressedStreamDump::GetSectorSize(void *,ulong *,ulong *)

- ea: `0x18002849c`
- end: `0x1800289b0`
- name: `?GetSectorSize@CompressedStreamDump@@YA_NPEAXPEAK1@Z`
- size: `1300`
- prototype: `bool __fastcall(HANDLE hFile, void *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18001e8f0`

## callees

- `0x180001710`
- `0x180001ae0`
- `0x180001b1c`
- `0x180001b70`
- `0x1800021f4`
- `0x180027afc`
- `0x180027d98`
- `0x180027f54`
- `0x180027fd0`
- `0x1800280a8`
- `0x18002849c`
- `0x1800289b8`
- `0x180028b30`
- `0x180028f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002856e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002879d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002891c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002856e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002879d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002891c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028933`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028946`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002893e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002893e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028564`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028606`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028564`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028606`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180028793`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180028793`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028865`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028865`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800288fd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800288fd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800287f5`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800287f5`

## string_xrefs

- `0x180028574`: `GetFinalPathNameByHandleW failed. Error: %u\n`
- `0x18002862d`: `GetFinalPathNameByHandleW (resized buffer) failed. Error: %u\n`
- `0x1800287b2`: `GetVolumePathNameW failed for path: %s. Error: %u\n`
- `0x18002880c`: `GetVolumeNameForVolumeMountPointW failed for volume path: %s. Error: %u\n`
- `0x180028886`: `CreateFileW failed for volume: %s. Error: %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CompressedStreamDump::GetSectorSize(HANDLE hFile, _DWORD *a2, char *a3, unsigned int *a4)
{
  __int64 v7; // rsi
  DWORD FinalPathNameByHandleW; // eax
  DWORD LastError; // eax
  const char *v10; // rdx
  LPWSTR v11; // rdx
  unsigned __int64 v12; // rcx
  char *v13; // r8
  size_t v14; // rbx
  DWORD v15; // eax
  __int64 v16; // r8
  const wchar_t *v17; // rdx
  size_t v18; // rbx
  const wchar_t *p_S1_8; // rcx
  unsigned __int64 v20; // rdx
  void *v21; // rcx
  const WCHAR *v22; // rcx
  DWORD v23; // eax
  const char *v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  DWORD v29; // eax
  unsigned __int64 v30; // rsi
  char *FileW; // rbx
  DWORD v32; // eax
  char v33; // si
  DWORD v34; // eax
  DWORD v35; // edi
  LPWSTR lpszFilePath[2]; // [rsp+40h] [rbp-C8h] BYREF
  void *v38; // [rsp+50h] [rbp-B8h]
  LPWSTR v39; // [rsp+58h] [rbp-B0h]
  DWORD BytesReturned[2]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v41[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 S1_8; // [rsp+78h] [rbp-90h] BYREF
  __int128 v43; // [rsp+88h] [rbp-80h]
  int InBuffer; // [rsp+98h] [rbp-70h] BYREF
  __int64 v45; // [rsp+9Ch] [rbp-6Ch]
  __int128 v46; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v47; // [rsp+B8h] [rbp-50h]
  _OWORD OutBuffer[2]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR szVolumeName[264]; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2F8h] [rbp+1F0h] BYREF

  v41[1] = -2;
  v7 = -1;
  if ( hFile == (HANDLE)-1LL || !a3 || !a2 )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Invalid input parameters to GetSectorSize.\n",
      a3,
      a4);
    return 0;
  }
  lpszFilePath[1] = (LPWSTR)operator new(0x208u);
  v39 = lpszFilePath[1] + 260;
  memset_0(lpszFilePath[1], 0, 0x208u);
  v38 = lpszFilePath[1] + 260;
  v41[0] = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(v41);
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath[1], 0x104u, 0);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    v10 = "GetFinalPathNameByHandleW failed. Error: %u\n";
LABEL_6:
    CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)v10, (const char *)LastError);
LABEL_7:
    std::vector<unsigned short>::~vector<unsigned short>(&lpszFilePath[1]);
    return 0;
  }
  v11 = lpszFilePath[1];
  v12 = (signed __int64)((__int64)v38 - (unsigned __int64)lpszFilePath[1]) >> 1;
  if ( FinalPathNameByHandleW > v12 )
  {
    if ( FinalPathNameByHandleW <= (unsigned __int64)(v39 - lpszFilePath[1]) )
    {
      v14 = 2 * (FinalPathNameByHandleW - v12);
      memset_0(v38, 0, v14);
      v13 = (char *)v38 + v14;
      v38 = (char *)v38 + v14;
    }
    else
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpszFilePath[1], FinalPathNameByHandleW);
      v13 = (char *)v38;
    }
    v15 = GetFinalPathNameByHandleW(hFile, lpszFilePath[1], (v13 - (char *)lpszFilePath[1]) >> 1, 0);
    if ( !v15
      || (v11 = lpszFilePath[1],
          v15 > (unsigned __int64)((signed __int64)((__int64)v38 - (unsigned __int64)lpszFilePath[1]) >> 1)) )
    {
      LastError = GetLastError();
      v10 = "GetFinalPathNameByHandleW (resized buffer) failed. Error: %u\n";
      goto LABEL_6;
    }
  }
  S1_8 = 0;
  v43 = 0u;
  v16 = -1;
  do
    ++v16;
  while ( v11[v16] );
  std::wstring::_Construct<1,unsigned short const *>(&S1_8);
  v18 = 4;
  if ( (unsigned __int64)v43 < 4 )
    v18 = v43;
  p_S1_8 = (const wchar_t *)&S1_8;
  if ( *((_QWORD *)&v43 + 1) > 7u )
    p_S1_8 = (const wchar_t *)S1_8;
  if ( !wmemcmp(p_S1_8, v17, v18) && v18 == 4 )
  {
    v46 = 0;
    v47 = 0u;
    if ( (unsigned __int64)v43 < 4 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    std::wstring::_Construct<1,unsigned short const *>(&v46);
    if ( *((_QWORD *)&v43 + 1) > 7u )
    {
      v20 = 2LL * *((_QWORD *)&v43 + 1) + 2;
      if ( v20 < 0x1000 )
      {
        v21 = (void *)S1_8;
      }
      else
      {
        v21 = *(void **)(S1_8 - 8);
        if ( (unsigned __int64)(S1_8 - (_QWORD)v21 - 8) > 0x1F )
          __fastfail(5u);
        v20 = 2LL * *((_QWORD *)&v43 + 1) + 41;
      }
      operator delete(v21, v20);
    }
    S1_8 = v46;
    v43 = v47;
    *(_QWORD *)&v47 = 0;
    *((_QWORD *)&v47 + 1) = 7;
    LOWORD(v46) = 0;
    std::wstring::~wstring(&v46);
  }
  memset_0(szVolumePathName, 0, 0x208u);
  v22 = (const WCHAR *)&S1_8;
  if ( *((_QWORD *)&v43 + 1) > 7u )
    v22 = (const WCHAR *)S1_8;
  if ( !GetVolumePathNameW(v22, szVolumePathName, 0x104u) )
  {
    v23 = GetLastError();
    v24 = (const char *)&S1_8;
    if ( *((_QWORD *)&v43 + 1) > 7u )
      v24 = (const char *)S1_8;
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"GetVolumePathNameW failed for path: %s. Error: %u\n",
      v24,
      v23);
    goto LABEL_38;
  }
  memset_0(szVolumeName, 0, 0x208u);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v29 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"GetVolumeNameForVolumeMountPointW failed for volume path: %s. Error: %u\n",
      (const char *)szVolumePathName,
      v29);
LABEL_38:
    std::wstring::~wstring(&S1_8);
    goto LABEL_7;
  }
  do
    ++v7;
  while ( szVolumeName[v7] );
  if ( v7 && *((_WORD *)&OutBuffer[1] + v7 + 7) == 92 )
  {
    v30 = 2 * v7 - 2;
    if ( v30 >= 0x208 )
      _report_rangecheckfailure(v26, v25, v27, v28);
    *(WCHAR *)((char *)szVolumeName + v30) = 0;
  }
  FileW = (char *)CreateFileW(szVolumeName, 0, 3u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v32 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"CreateFileW failed for volume: %s. Error: %u\n",
      (const char *)szVolumeName,
      v32);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    goto LABEL_38;
  }
  v45 = 0;
  InBuffer = 6;
  memset(OutBuffer, 0, 28);
  BytesReturned[0] = 0;
  if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, OutBuffer, 0x1Cu, BytesReturned, 0) )
  {
    *a2 = OutBuffer[1];
    *(_DWORD *)a3 = DWORD1(OutBuffer[1]);
    v33 = 1;
  }
  else
  {
    v33 = 0;
    v34 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DeviceIoControl(IOCTL_STORAGE_QUERY_PROPERTY) failed. Error: %u\n",
      (const char *)v34);
  }
  v35 = GetLastError();
  CloseHandle(FileW);
  SetLastError(v35);
  std::wstring::~wstring(&S1_8);
  std::vector<unsigned short>::~vector<unsigned short>(&lpszFilePath[1]);
  return v33;
}

```

## disassembly

```asm
0x18002849c  mov     rax, rsp
0x18002849f  push    rbp
0x1800284a0  push    rsi
0x1800284a1  push    rdi
0x1800284a2  push    r12
0x1800284a4  push    r13
0x1800284a6  push    r14
0x1800284a8  push    r15
0x1800284aa  lea     rbp, [rax-448h]
0x1800284b1  sub     rsp, 510h
0x1800284b8  mov     qword ptr [rsp+540h+S1], 0FFFFFFFFFFFFFFFEh
0x1800284c1  mov     [rax+20h], rbx
0x1800284c5  mov     rax, cs:__security_cookie
0x1800284cc  xor     rax, rsp
0x1800284cf  mov     [rbp+440h+var_40], rax
0x1800284d6  mov     r12, r8
0x1800284d9  mov     r15, rdx
0x1800284dc  mov     r14, rcx
0x1800284df  xor     r13d, r13d
0x1800284e2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800284e6  cmp     rcx, rsi
0x1800284e9  jz      loc_180028967
0x1800284ef  test    r8, r8
0x1800284f2  jz      loc_180028967
0x1800284f8  test    rdx, rdx
0x1800284fb  jz      loc_180028967
0x180028501  xorps   xmm0, xmm0
0x180028504  movdqu  xmmword ptr [rsp+540h+lpszFilePath+8], xmm0
0x18002850a  mov     [rsp+540h+var_4F0], r13
0x18002850f  mov     edi, 208h
0x180028514  mov     ecx, edi; Size
0x180028516  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002851b  mov     [rsp+540h+lpszFilePath+8], rax
0x180028520  lea     rbx, [rax+208h]
0x180028527  mov     [rsp+540h+var_4F0], rbx
0x18002852c  mov     r8d, edi; Size
0x18002852f  xor     edx, edx; Val
0x180028531  mov     rcx, rax; void *
0x180028534  call    memset_0
0x180028539  mov     [rsp+540h+var_4F8], rbx
0x18002853e  mov     [rsp+540h+var_4E0], r13
0x180028543  lea     rcx, [rsp+540h+var_4E0]
0x180028548  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x18002854d  nop
0x18002854e  mov     rdx, [rsp+540h+lpszFilePath+8]; lpszFilePath
0x180028553  mov     r8, [rsp+540h+var_4F8]
0x180028558  sub     r8, rdx
0x18002855b  sar     r8, 1; cchFilePath
0x18002855e  xor     r9d, r9d; dwFlags
0x180028561  mov     rcx, r14; hFile
0x180028564  call    cs:__imp_GetFinalPathNameByHandleW
0x18002856a  test    eax, eax
0x18002856c  jnz     short loc_180028598
0x18002856e  call    cs:__imp_GetLastError
0x180028574  lea     rdx, aGetfinalpathna; "GetFinalPathNameByHandleW failed. Error"...
0x18002857b  mov     r8d, eax; char *
0x18002857e  mov     ecx, 4; this
0x180028583  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180028588  nop
0x180028589  lea     rcx, [rsp+540h+lpszFilePath+8]
0x18002858e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180028593  jmp     loc_180028978
0x180028598  mov     rdi, [rsp+540h+var_4F8]
0x18002859d  mov     rdx, [rsp+540h+lpszFilePath+8]
0x1800285a2  mov     rcx, rdi
0x1800285a5  sub     rcx, rdx
0x1800285a8  sar     rcx, 1
0x1800285ab  mov     ebx, eax
0x1800285ad  cmp     rbx, rcx
0x1800285b0  jbe     loc_180028639
0x1800285b6  mov     rax, [rsp+540h+var_4F0]
0x1800285bb  sub     rax, rdx
0x1800285be  sar     rax, 1
0x1800285c1  cmp     rbx, rax
0x1800285c4  jbe     short loc_1800285D9
0x1800285c6  mov     edx, ebx
0x1800285c8  lea     rcx, [rsp+540h+lpszFilePath+8]
0x1800285cd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800285d2  mov     r8, [rsp+540h+var_4F8]
0x1800285d7  jmp     short loc_1800285F5
0x1800285d9  sub     rbx, rcx
0x1800285dc  add     rbx, rbx
0x1800285df  mov     r8, rbx; Size
0x1800285e2  xor     edx, edx; Val
0x1800285e4  mov     rcx, rdi; void *
0x1800285e7  call    memset_0
0x1800285ec  lea     r8, [rbx+rdi]
0x1800285f0  mov     [rsp+540h+var_4F8], r8
0x1800285f5  mov     rdx, [rsp+540h+lpszFilePath+8]; lpszFilePath
0x1800285fa  sub     r8, rdx
0x1800285fd  sar     r8, 1; cchFilePath
0x180028600  xor     r9d, r9d; dwFlags
0x180028603  mov     rcx, r14; hFile
0x180028606  call    cs:__imp_GetFinalPathNameByHandleW
0x18002860c  test    eax, eax
0x18002860e  jz      short loc_180028627
0x180028610  mov     rdx, [rsp+540h+lpszFilePath+8]
0x180028615  mov     rcx, [rsp+540h+var_4F8]
0x18002861a  sub     rcx, rdx
0x18002861d  sar     rcx, 1
0x180028620  mov     eax, eax
0x180028622  cmp     rax, rcx
0x180028625  jbe     short loc_180028639
0x180028627  call    cs:__imp_GetLastError
0x18002862d  lea     rdx, aGetfinalpathna_0; "GetFinalPathNameByHandleW (resized buff"...
0x180028634  jmp     loc_18002857B
0x180028639  xorps   xmm0, xmm0
0x18002863c  movups  xmmword ptr [rsp+540h+S1+8], xmm0
0x180028641  mov     qword ptr [rbp+440h+var_4C0], r13
0x180028645  mov     qword ptr [rbp+440h+var_4C0+8], r13
0x180028649  mov     r8, rsi
0x18002864c  inc     r8
0x18002864f  cmp     [rdx+r8*2], r13w
0x180028654  jnz     short loc_18002864C
0x180028656  lea     rcx, [rsp+540h+S1+8]
0x18002865b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028660  nop
0x180028661  mov     edi, 4
0x180028666  mov     ebx, edi
0x180028668  cmp     qword ptr [rbp+440h+var_4C0], rdi
0x18002866c  cmovb   rbx, qword ptr [rbp+440h+var_4C0]
0x180028671  lea     rcx, [rsp+540h+S1+8]
0x180028676  lea     r14d, [rdi+3]
0x18002867a  cmp     qword ptr [rbp+440h+var_4C0+8], r14
0x18002867e  cmova   rcx, qword ptr [rsp+540h+S1+8]; S1
0x180028684  mov     r8, rbx
0x180028687  cmp     rbx, rdi
0x18002868a  cmova   r8, rdi; N
0x18002868e  call    wmemcmp
0x180028693  test    eax, eax
0x180028695  jnz     loc_180028761
0x18002869b  cmp     rbx, rdi
0x18002869e  jnz     loc_180028761
0x1800286a4  mov     eax, r13d
0x1800286a7  test    eax, eax
0x1800286a9  jnz     loc_180028761
0x1800286af  xorps   xmm0, xmm0
0x1800286b2  movups  [rbp+440h+var_4A0], xmm0
0x1800286b6  mov     qword ptr [rbp+440h+var_490], r13
0x1800286ba  mov     qword ptr [rbp+440h+var_490+8], r13
0x1800286be  mov     rax, qword ptr [rbp+440h+var_4C0]
0x1800286c2  cmp     rax, rdi
0x1800286c5  jb      loc_1800289AA
0x1800286cb  add     rax, 0FFFFFFFFFFFFFFFCh
0x1800286cf  mov     r8, rsi
0x1800286d2  cmp     rax, rsi
0x1800286d5  cmovb   r8, rax
0x1800286d9  lea     rdx, [rsp+540h+S1+8]
0x1800286de  cmp     qword ptr [rbp+440h+var_4C0+8], r14
0x1800286e2  cmova   rdx, qword ptr [rsp+540h+S1+8]
0x1800286e8  add     rdx, 8
0x1800286ec  lea     rcx, [rbp+440h+var_4A0]
0x1800286f0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800286f5  mov     rdx, qword ptr [rbp+440h+var_4C0+8]
0x1800286f9  cmp     rdx, r14
0x1800286fc  jbe     short loc_18002873A
0x1800286fe  mov     rax, qword ptr [rsp+540h+S1+8]
0x180028703  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18002870b  cmp     rdx, 1000h
0x180028712  jb      short loc_180028732
0x180028714  mov     rcx, [rax-8]
0x180028718  sub     rax, rcx
0x18002871b  sub     rax, 8
0x18002871f  cmp     rax, 1Fh
0x180028723  ja      short loc_18002872B
0x180028725  add     rdx, 27h ; '''
0x180028729  jmp     short loc_180028735
0x18002872b  mov     ecx, 5
0x180028730  int     29h; Win8: RtlFailFast(ecx)
0x180028732  mov     rcx, rax; void *
0x180028735  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002873a  movups  xmm0, [rbp+440h+var_4A0]
0x18002873e  movups  xmmword ptr [rsp+540h+S1+8], xmm0
0x180028743  movups  xmm1, [rbp+440h+var_490]
0x180028747  movups  [rbp+440h+var_4C0], xmm1
0x18002874b  mov     qword ptr [rbp+440h+var_490], r13
0x18002874f  mov     qword ptr [rbp+440h+var_490+8], r14
0x180028753  mov     word ptr [rbp+440h+var_4A0], r13w
0x180028758  lea     rcx, [rbp+440h+var_4A0]
0x18002875c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028761  xor     edx, edx; Val
0x180028763  mov     r8d, 208h; Size
0x180028769  lea     rcx, [rbp+440h+szVolumePathName]; void *
0x180028770  call    memset_0
0x180028775  lea     rcx, [rsp+540h+S1+8]
0x18002877a  cmp     qword ptr [rbp+440h+var_4C0+8], r14
0x18002877e  cmova   rcx, qword ptr [rsp+540h+S1+8]; lpszFileName
0x180028784  mov     ebx, 104h
0x180028789  mov     r8d, ebx; cchBufferLength
0x18002878c  lea     rdx, [rbp+440h+szVolumePathName]; lpszVolumePathName
0x180028793  call    cs:__imp_GetVolumePathNameW
0x180028799  test    eax, eax
0x18002879b  jnz     short loc_1800287D3
0x18002879d  call    cs:__imp_GetLastError
0x1800287a3  lea     r8, [rsp+540h+S1+8]
0x1800287a8  cmp     qword ptr [rbp+440h+var_4C0+8], r14
0x1800287ac  cmova   r8, qword ptr [rsp+540h+S1+8]; char *
0x1800287b2  lea     rdx, aGetvolumepathn; "GetVolumePathNameW failed for path: %s."...
0x1800287b9  mov     r9d, eax
0x1800287bc  mov     ecx, edi; this
0x1800287be  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x1800287c3  nop
0x1800287c4  lea     rcx, [rsp+540h+S1+8]
0x1800287c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800287ce  jmp     loc_180028589
0x1800287d3  mov     r14d, 208h
0x1800287d9  mov     r8d, r14d; Size
0x1800287dc  xor     edx, edx; Val
0x1800287de  lea     rcx, [rbp+440h+szVolumeName]; void *
0x1800287e2  call    memset_0
0x1800287e7  mov     r8d, ebx; cchBufferLength
0x1800287ea  lea     rdx, [rbp+440h+szVolumeName]; lpszVolumeName
0x1800287ee  lea     rcx, [rbp+440h+szVolumePathName]; lpszVolumeMountPoint
0x1800287f5  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800287fb  test    eax, eax
0x1800287fd  jnz     short loc_180028815
0x1800287ff  call    cs:__imp_GetLastError
0x180028805  lea     r8, [rbp+440h+szVolumePathName]
0x18002880c  lea     rdx, aGetvolumenamef; "GetVolumeNameForVolumeMountPointW faile"...
0x180028813  jmp     short loc_1800287B9
0x180028815  lea     rax, [rbp+440h+szVolumeName]
0x180028819  inc     rsi
0x18002881c  cmp     [rax+rsi*2], r13w
0x180028821  jnz     short loc_180028819
0x180028823  test    rsi, rsi
0x180028826  jz      short loc_180028847
0x180028828  cmp     [rbp+rsi*2+440h+var_462], 5Ch ; '\'
0x18002882e  jnz     short loc_180028847
0x180028830  lea     rsi, ds:0FFFFFFFFFFFFFFFEh[rsi*2]
0x180028838  cmp     rsi, r14
0x18002883b  jnb     loc_1800289A4
0x180028841  mov     [rbp+rsi+440h+szVolumeName], r13w
0x180028847  mov     [rsp+540h+hTemplateFile], r13; hTemplateFile
0x18002884c  mov     [rsp+540h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180028851  mov     r8d, 3; dwShareMode
0x180028857  mov     [rsp+540h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002885c  xor     r9d, r9d; lpSecurityAttributes
0x18002885f  xor     edx, edx; dwDesiredAccess
0x180028861  lea     rcx, [rbp+440h+szVolumeName]; lpFileName
0x180028865  call    cs:__imp_CreateFileW
0x18002886b  mov     rbx, rax
0x18002886e  inc     rax
0x180028871  test    rax, 0FFFFFFFFFFFFFFFEh
0x180028877  jnz     short loc_1800288B0
0x180028879  call    cs:__imp_GetLastError
0x18002887f  mov     r9d, eax
0x180028882  lea     r8, [rbp+440h+szVolumeName]; char *
0x180028886  lea     rdx, aCreatefilewFai; "CreateFileW failed for volume: %s. Erro"...
0x18002888d  mov     ecx, edi; this
0x18002888f  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180028894  lea     rax, [rbx-1]
0x180028898  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002889c  ja      loc_1800287C4
0x1800288a2  mov     rcx, rbx; hObject
0x1800288a5  call    cs:__imp_CloseHandle
0x1800288ab  jmp     loc_1800287C4
0x1800288b0  mov     [rbp+440h+var_4AC], r13
0x1800288b4  mov     [rbp+440h+InBuffer], 6
0x1800288bb  xorps   xmm0, xmm0
0x1800288be  movups  [rbp+440h+OutBuffer], xmm0
0x1800288c2  movups  [rbp+440h+OutBuffer+0Ch], xmm0
0x1800288c6  mov     [rsp+540h+BytesReturned], r13d
0x1800288cb  mov     [rsp+540h+lpszFilePath], r13; lpOverlapped
0x1800288d0  lea     rax, [rsp+540h+BytesReturned]
0x1800288d5  mov     [rsp+540h+hTemplateFile], rax; lpBytesReturned
0x1800288da  mov     [rsp+540h+dwFlagsAndAttributes], 1Ch; nOutBufferSize
0x1800288e2  lea     rax, [rbp+440h+OutBuffer]
0x1800288e6  mov     qword ptr [rsp+540h+dwCreationDisposition], rax; lpOutBuffer
0x1800288eb  mov     r9d, 0Ch; nInBufferSize
0x1800288f1  lea     r8, [rbp+440h+InBuffer]; lpInBuffer
0x1800288f5  mov     edx, 2D1400h; dwIoControlCode
0x1800288fa  mov     rcx, rbx; hDevice
0x1800288fd  call    cs:__imp_DeviceIoControl
0x180028903  test    eax, eax
0x180028905  jz      short loc_180028919
0x180028907  mov     eax, [rbp+440h+var_470]
0x18002890a  mov     [r15], eax
0x18002890d  mov     eax, [rbp+440h+var_46C]
0x180028910  mov     [r12], eax
0x180028914  mov     sil, 1
0x180028917  jmp     short loc_180028933
0x180028919  mov     sil, r13b
0x18002891c  call    cs:__imp_GetLastError
0x180028922  mov     r8d, eax; char *
0x180028925  lea     rdx, aDeviceiocontro; "DeviceIoControl(IOCTL_STORAGE_QUERY_PRO"...
0x18002892c  mov     ecx, edi; this
0x18002892e  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180028933  call    cs:__imp_GetLastError
0x180028939  mov     edi, eax
0x18002893b  mov     rcx, rbx; hObject
0x18002893e  call    cs:__imp_CloseHandle
0x180028944  mov     ecx, edi; dwErrCode
0x180028946  call    cs:__imp_SetLastError
0x18002894c  nop
0x18002894d  lea     rcx, [rsp+540h+S1+8]
0x180028952  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028957  nop
0x180028958  lea     rcx, [rsp+540h+lpszFilePath+8]
0x18002895d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180028962  mov     al, sil
  ... truncated ...
```
