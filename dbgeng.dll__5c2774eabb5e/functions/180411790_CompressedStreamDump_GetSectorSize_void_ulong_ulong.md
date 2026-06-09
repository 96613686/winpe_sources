# CompressedStreamDump::GetSectorSize(void *,ulong *,ulong *)

- ea: `0x180411790`
- end: `0x180411be0`
- name: `?GetSectorSize@CompressedStreamDump@@YA_NPEAXPEAK1@Z`
- size: `1104`
- prototype: `bool __fastcall(HANDLE hFile, void *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18040aa64`

## callees

- `0x18007fca0`
- `0x180080424`
- `0x180080468`
- `0x1800aea44`
- `0x1800c24b0`
- `0x1800c7034`
- `0x1800cc410`
- `0x1800d6534`
- `0x1800d6560`
- `0x1800f0f40`
- `0x1800f17b0`
- `0x180190080`
- `0x180411224`
- `0x1804113b4`
- `0x180411790`
- `0x180411be8`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804118eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804119b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804118eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804119b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411b4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180411a8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180411a8e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180411816`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1804118c4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180411816`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1804118c4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1804119a6`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1804119a6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180411b29`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180411b29`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180411a0c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180411a0c`

## string_xrefs

- `0x180411832`: `GetFinalPathNameByHandleW failed. Error: %u\n`
- `0x180411abf`: `CreateFileW failed for volume: %s. Error: %u\n`
- `0x180411a32`: `GetVolumeNameForVolumeMountPointW failed for volume path: %s. Error: %u\n`
- `0x1804119d2`: `GetVolumePathNameW failed for path: %s. Error: %u\n`
- `0x1804118f7`: `GetFinalPathNameByHandleW (resized buffer) failed. Error: %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CompressedStreamDump::GetSectorSize(HANDLE hFile, _DWORD *a2, char *a3, unsigned int *a4)
{
  DWORD FinalPathNameByHandleW; // eax
  DWORD LastError; // eax
  const char *v9; // rdx
  char *v10; // rdi
  unsigned __int64 v11; // rcx
  char *v12; // r8
  size_t v13; // rbx
  DWORD v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx
  const WCHAR *v20; // rax
  __int64 v21; // rdx
  const char *v22; // r8
  __int64 v23; // rax
  unsigned __int64 v24; // rcx
  HANDLE FileW; // rax
  DWORD v26; // eax
  char v27; // di
  DWORD v28; // eax
  LPWSTR lpszFilePath; // [rsp+48h] [rbp-C0h] BYREF
  void *v31; // [rsp+50h] [rbp-B8h]
  __int64 v32; // [rsp+58h] [rbp-B0h]
  DWORD BytesReturned[2]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v34[2]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v35[16]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v36; // [rsp+88h] [rbp-80h]
  int InBuffer; // [rsp+98h] [rbp-70h] BYREF
  __int64 v38; // [rsp+9Ch] [rbp-6Ch]
  _OWORD OutBuffer[2]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v40[32]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR szVolumeName[264]; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2F8h] [rbp+1F0h] BYREF

  v34[1] = -2;
  if ( hFile == (HANDLE)-1LL || !a3 || !a2 )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Invalid input parameters to GetSectorSize.\n",
      a3,
      a4);
    return 0;
  }
  std::vector<unsigned short>::vector<unsigned short>(&lpszFilePath, a2, a3, a4);
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(
                             hFile,
                             lpszFilePath,
                             ((_BYTE *)v31 - (_BYTE *)lpszFilePath) >> 1,
                             0);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    v9 = "GetFinalPathNameByHandleW failed. Error: %u\n";
LABEL_6:
    CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)v9, (const char *)LastError);
LABEL_7:
    std::vector<unsigned short>::_Tidy(&lpszFilePath);
    return 0;
  }
  v10 = (char *)v31;
  v11 = ((_BYTE *)v31 - (_BYTE *)lpszFilePath) >> 1;
  if ( FinalPathNameByHandleW > v11 )
  {
    if ( FinalPathNameByHandleW <= (unsigned __int64)((v32 - (__int64)lpszFilePath) >> 1) )
    {
      v13 = 2 * (FinalPathNameByHandleW - v11);
      memset(v31, 0, v13);
      v12 = &v10[v13];
      v31 = &v10[v13];
    }
    else
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpszFilePath, FinalPathNameByHandleW);
      v12 = (char *)v31;
    }
    v14 = GetFinalPathNameByHandleW(hFile, lpszFilePath, (v12 - (char *)lpszFilePath) >> 1, 0);
    if ( !v14 || v14 > (unsigned __int64)(((_BYTE *)v31 - (_BYTE *)lpszFilePath) >> 1) )
    {
      LastError = GetLastError();
      v9 = "GetFinalPathNameByHandleW (resized buffer) failed. Error: %u\n";
      goto LABEL_6;
    }
  }
  std::wstring::wstring(v35);
  std::_String_val<std::_Simple_types<unsigned short>>::_Check_offset(v35, 0);
  v15 = 4;
  if ( v36 < 4 )
    v15 = v36;
  v16 = std::wstring::c_str(v35, v15);
  if ( !(unsigned int)std::_Traits_compare<std::char_traits<unsigned short>>(v16, v17, L"\\\\?\\", 4) )
  {
    v18 = std::wstring::substr(v35, v40, 4, -1);
    std::wstring::operator=(v35, v18);
    std::wstring::_Tidy_deallocate(v40);
  }
  memset(szVolumePathName, 0, 0x208u);
  v20 = (const WCHAR *)std::wstring::c_str(v35, v19);
  if ( !GetVolumePathNameW(v20, szVolumePathName, 0x104u) )
  {
    GetLastError();
    v22 = (const char *)std::wstring::c_str(v35, v21);
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"GetVolumePathNameW failed for path: %s. Error: %u\n",
      v22);
LABEL_21:
    std::wstring::_Tidy_deallocate(v35);
    goto LABEL_7;
  }
  memset(szVolumeName, 0, 0x208u);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"GetVolumeNameForVolumeMountPointW failed for volume path: %s. Error: %u\n",
      (const char *)szVolumePathName);
    goto LABEL_21;
  }
  v23 = -1;
  do
    ++v23;
  while ( szVolumeName[v23] );
  if ( v23 && *(_WORD *)&v40[2 * v23 + 30] == 92 )
  {
    v24 = 2 * v23 - 2;
    if ( v24 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v24) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 3u, 0, 3u, 0, 0);
  v34[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v26 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"CreateFileW failed for volume: %s. Error: %u\n",
      (const char *)szVolumeName,
      v26);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v34);
    goto LABEL_21;
  }
  v38 = 0;
  InBuffer = 6;
  memset(OutBuffer, 0, 28);
  BytesReturned[0] = 0;
  if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, OutBuffer, 0x1Cu, BytesReturned, 0) )
  {
    *a2 = OutBuffer[1];
    *(_DWORD *)a3 = DWORD1(OutBuffer[1]);
    v27 = 1;
  }
  else
  {
    v27 = 0;
    v28 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DeviceIoControl(IOCTL_STORAGE_QUERY_PROPERTY) failed. Error: %u\n",
      (const char *)v28);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v34,
    -1);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v34);
  std::wstring::_Tidy_deallocate(v35);
  std::vector<unsigned short>::_Tidy(&lpszFilePath);
  return v27;
}

```

## disassembly

```asm
0x180411790  mov     rax, rsp
0x180411793  push    rbp
0x180411794  push    rsi
0x180411795  push    rdi
0x180411796  push    r12
0x180411798  push    r13
0x18041179a  push    r14
0x18041179c  push    r15
0x18041179e  lea     rbp, [rax-448h]
0x1804117a5  sub     rsp, 510h
0x1804117ac  mov     qword ptr [rsp+540h+var_4D8], 0FFFFFFFFFFFFFFFEh
0x1804117b5  mov     [rax+20h], rbx
0x1804117b9  mov     rax, cs:__security_cookie
0x1804117c0  xor     rax, rsp
0x1804117c3  mov     [rbp+440h+var_40], rax
0x1804117ca  mov     r15, r8
0x1804117cd  mov     r14, rdx
0x1804117d0  mov     rsi, rcx
0x1804117d3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1804117d7  cmp     rcx, r13
0x1804117da  jz      loc_180411B9C
0x1804117e0  xor     r12d, r12d
0x1804117e3  test    r8, r8
0x1804117e6  jz      loc_180411B9C
0x1804117ec  test    rdx, rdx
0x1804117ef  jz      loc_180411B9C
0x1804117f5  lea     rcx, [rsp+540h+lpszFilePath]
0x1804117fa  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1804117ff  nop
0x180411800  mov     rdx, [rsp+540h+lpszFilePath]; lpszFilePath
0x180411805  mov     r8, [rsp+540h+var_4F8]
0x18041180a  sub     r8, rdx
0x18041180d  sar     r8, 1; cchFilePath
0x180411810  xor     r9d, r9d; dwFlags
0x180411813  mov     rcx, rsi; hFile
0x180411816  call    cs:__imp_GetFinalPathNameByHandleW
0x18041181d  nop     dword ptr [rax+rax+00h]
0x180411822  test    eax, eax
0x180411824  jnz     short loc_180411856
0x180411826  call    cs:__imp_GetLastError
0x18041182d  nop     dword ptr [rax+rax+00h]
0x180411832  lea     rdx, aGetfinalpathna; "GetFinalPathNameByHandleW failed. Error"...
0x180411839  mov     r8d, eax; char *
0x18041183c  mov     ecx, 4; this
0x180411841  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180411846  nop
0x180411847  lea     rcx, [rsp+540h+lpszFilePath]
0x18041184c  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180411851  jmp     loc_180411BAD
0x180411856  mov     rdx, [rsp+540h+lpszFilePath]
0x18041185b  mov     rdi, [rsp+540h+var_4F8]
0x180411860  mov     rcx, rdi
0x180411863  sub     rcx, rdx
0x180411866  sar     rcx, 1
0x180411869  mov     ebx, eax
0x18041186b  cmp     rbx, rcx
0x18041186e  jbe     loc_180411903
0x180411874  mov     rax, [rsp+540h+var_4F0]
0x180411879  sub     rax, rdx
0x18041187c  sar     rax, 1
0x18041187f  cmp     rbx, rax
0x180411882  jbe     short loc_180411897
0x180411884  mov     edx, ebx
0x180411886  lea     rcx, [rsp+540h+lpszFilePath]
0x18041188b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180411890  mov     r8, [rsp+540h+var_4F8]
0x180411895  jmp     short loc_1804118B3
0x180411897  sub     rbx, rcx
0x18041189a  add     rbx, rbx
0x18041189d  mov     r8, rbx; Size
0x1804118a0  xor     edx, edx; Val
0x1804118a2  mov     rcx, rdi; void *
0x1804118a5  call    memset
0x1804118aa  lea     r8, [rbx+rdi]
0x1804118ae  mov     [rsp+540h+var_4F8], r8
0x1804118b3  mov     rdx, [rsp+540h+lpszFilePath]; lpszFilePath
0x1804118b8  sub     r8, rdx
0x1804118bb  sar     r8, 1; cchFilePath
0x1804118be  xor     r9d, r9d; dwFlags
0x1804118c1  mov     rcx, rsi; hFile
0x1804118c4  call    cs:__imp_GetFinalPathNameByHandleW
0x1804118cb  nop     dword ptr [rax+rax+00h]
0x1804118d0  test    eax, eax
0x1804118d2  jz      short loc_1804118EB
0x1804118d4  mov     rcx, [rsp+540h+var_4F8]
0x1804118d9  mov     rdx, [rsp+540h+lpszFilePath]
0x1804118de  sub     rcx, rdx
0x1804118e1  sar     rcx, 1
0x1804118e4  mov     eax, eax
0x1804118e6  cmp     rax, rcx
0x1804118e9  jbe     short loc_180411903
0x1804118eb  call    cs:__imp_GetLastError
0x1804118f2  nop     dword ptr [rax+rax+00h]
0x1804118f7  lea     rdx, aGetfinalpathna_0; "GetFinalPathNameByHandleW (resized buff"...
0x1804118fe  jmp     loc_180411839
0x180411903  lea     rcx, [rsp+70h]
0x180411908  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18041190d  nop
0x18041190e  xor     edx, edx
0x180411910  lea     rcx, [rsp+70h]
0x180411915  call    ?_Check_offset@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAX_K@Z; std::_String_val<std::_Simple_types<ushort>>::_Check_offset(unsigned __int64)
0x18041191a  mov     ebx, 4
0x18041191f  mov     edx, ebx
0x180411921  cmp     [rbp+440h+var_4C0], rbx
0x180411925  cmovb   rdx, [rbp+440h+var_4C0]
0x18041192a  lea     rcx, [rsp+70h]
0x18041192f  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180411934  mov     rcx, rax
0x180411937  mov     r9d, ebx
0x18041193a  lea     r8, asc_180684078; "\\\\?\\"
0x180411941  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180411946  test    eax, eax
0x180411948  jnz     short loc_180411974
0x18041194a  mov     r9, r13
0x18041194d  mov     r8d, ebx
0x180411950  lea     rdx, [rbp+440h+var_480]
0x180411954  lea     rcx, [rsp+70h]
0x180411959  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18041195e  mov     rdx, rax
0x180411961  lea     rcx, [rsp+70h]
0x180411966  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18041196b  lea     rcx, [rbp+440h+var_480]
0x18041196f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180411974  mov     edi, 208h
0x180411979  mov     r8d, edi; Size
0x18041197c  xor     edx, edx; Val
0x18041197e  lea     rcx, [rbp+440h+szVolumePathName]; void *
0x180411985  call    memset
0x18041198a  lea     rcx, [rsp+70h]
0x18041198f  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180411994  mov     rcx, rax; lpszFileName
0x180411997  mov     esi, 104h
0x18041199c  mov     r8d, esi; cchBufferLength
0x18041199f  lea     rdx, [rbp+440h+szVolumePathName]; lpszVolumePathName
0x1804119a6  call    cs:__imp_GetVolumePathNameW
0x1804119ad  nop     dword ptr [rax+rax+00h]
0x1804119b2  test    eax, eax
0x1804119b4  jnz     short loc_1804119F0
0x1804119b6  call    cs:__imp_GetLastError
0x1804119bd  nop     dword ptr [rax+rax+00h]
0x1804119c2  mov     r9d, eax
0x1804119c5  lea     rcx, [rsp+70h]
0x1804119ca  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1804119cf  mov     r8, rax; char *
0x1804119d2  lea     rdx, aGetvolumepathn; "GetVolumePathNameW failed for path: %s."...
0x1804119d9  mov     ecx, ebx; this
0x1804119db  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x1804119e0  nop
0x1804119e1  lea     rcx, [rsp+70h]
0x1804119e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1804119eb  jmp     loc_180411847
0x1804119f0  mov     r8, rdi; Size
0x1804119f3  xor     edx, edx; Val
0x1804119f5  lea     rcx, [rbp+440h+szVolumeName]; void *
0x1804119f9  call    memset
0x1804119fe  mov     r8d, esi; cchBufferLength
0x180411a01  lea     rdx, [rbp+440h+szVolumeName]; lpszVolumeName
0x180411a05  lea     rcx, [rbp+440h+szVolumePathName]; lpszVolumeMountPoint
0x180411a0c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180411a13  nop     dword ptr [rax+rax+00h]
0x180411a18  test    eax, eax
0x180411a1a  jnz     short loc_180411A3B
0x180411a1c  call    cs:__imp_GetLastError
0x180411a23  nop     dword ptr [rax+rax+00h]
0x180411a28  mov     r9d, eax
0x180411a2b  lea     r8, [rbp+440h+szVolumePathName]
0x180411a32  lea     rdx, aGetvolumenamef; "GetVolumeNameForVolumeMountPointW faile"...
0x180411a39  jmp     short loc_1804119D9
0x180411a3b  lea     rcx, [rbp+440h+szVolumeName]
0x180411a3f  mov     rax, r13
0x180411a42  inc     rax
0x180411a45  cmp     [rcx+rax*2], r12w
0x180411a4a  jnz     short loc_180411A42
0x180411a4c  test    rax, rax
0x180411a4f  jz      short loc_180411A70
0x180411a51  cmp     [rbp+rax*2+440h+var_462], 5Ch ; '\'
0x180411a57  jnz     short loc_180411A70
0x180411a59  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180411a61  cmp     rcx, rdi
0x180411a64  jnb     loc_180411BDA
0x180411a6a  mov     [rbp+rcx+440h+szVolumeName], r12w
0x180411a70  mov     [rsp+540h+hTemplateFile], r12; hTemplateFile
0x180411a75  mov     [rsp+540h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180411a7a  mov     r8d, 3; dwShareMode
0x180411a80  mov     [rsp+540h+dwCreationDisposition], r8d; dwCreationDisposition
0x180411a85  xor     r9d, r9d; lpSecurityAttributes
0x180411a88  xor     edx, edx; dwDesiredAccess
0x180411a8a  lea     rcx, [rbp+440h+szVolumeName]; lpFileName
0x180411a8e  call    cs:__imp_CreateFileW
0x180411a95  nop     dword ptr [rax+rax+00h]
0x180411a9a  mov     [rsp+540h+var_4E0], rax
0x180411a9f  lea     rcx, [rax+1]
0x180411aa3  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180411aaa  jnz     short loc_180411ADC
0x180411aac  call    cs:__imp_GetLastError
0x180411ab3  nop     dword ptr [rax+rax+00h]
0x180411ab8  mov     r9d, eax
0x180411abb  lea     r8, [rbp+440h+szVolumeName]; char *
0x180411abf  lea     rdx, aCreatefilewFai; "CreateFileW failed for volume: %s. Erro"...
0x180411ac6  mov     ecx, ebx; this
0x180411ac8  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180411acd  lea     rcx, [rsp+540h+var_4E0]
0x180411ad2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180411ad7  jmp     loc_1804119E1
0x180411adc  mov     [rbp+440h+var_4AC], r12
0x180411ae0  mov     [rbp+440h+InBuffer], 6
0x180411ae7  xorps   xmm0, xmm0
0x180411aea  movups  [rbp+440h+OutBuffer], xmm0
0x180411aee  movups  [rbp+440h+OutBuffer+0Ch], xmm0
0x180411af2  mov     [rsp+540h+BytesReturned], r12d
0x180411af7  mov     [rsp+540h+lpOverlapped], r12; lpOverlapped
0x180411afc  lea     rcx, [rsp+540h+BytesReturned]
0x180411b01  mov     [rsp+540h+hTemplateFile], rcx; lpBytesReturned
0x180411b06  mov     [rsp+540h+dwFlagsAndAttributes], 1Ch; nOutBufferSize
0x180411b0e  lea     rcx, [rbp+440h+OutBuffer]
0x180411b12  mov     qword ptr [rsp+540h+dwCreationDisposition], rcx; lpOutBuffer
0x180411b17  mov     r9d, 0Ch; nInBufferSize
0x180411b1d  lea     r8, [rbp+440h+InBuffer]; lpInBuffer
0x180411b21  mov     edx, 2D1400h; dwIoControlCode
0x180411b26  mov     rcx, rax; hDevice
0x180411b29  call    cs:__imp_DeviceIoControl
0x180411b30  nop     dword ptr [rax+rax+00h]
0x180411b35  test    eax, eax
0x180411b37  jz      short loc_180411B4A
0x180411b39  mov     eax, [rbp+440h+var_490]
0x180411b3c  mov     [r14], eax
0x180411b3f  mov     eax, [rbp+440h+var_48C]
0x180411b42  mov     [r15], eax
0x180411b45  mov     dil, 1
0x180411b48  jmp     short loc_180411B6A
0x180411b4a  mov     dil, r12b
0x180411b4d  call    cs:__imp_GetLastError
0x180411b54  nop     dword ptr [rax+rax+00h]
0x180411b59  mov     r8d, eax; char *
0x180411b5c  lea     rdx, aDeviceiocontro; "DeviceIoControl(IOCTL_STORAGE_QUERY_PRO"...
0x180411b63  mov     ecx, ebx; this
0x180411b65  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180411b6a  mov     rdx, r13
0x180411b6d  lea     rcx, [rsp+540h+var_4E0]
0x180411b72  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180411b77  lea     rcx, [rsp+540h+var_4E0]
0x180411b7c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180411b81  nop
0x180411b82  lea     rcx, [rsp+70h]
0x180411b87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180411b8c  nop
0x180411b8d  lea     rcx, [rsp+540h+lpszFilePath]
0x180411b92  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180411b97  mov     al, dil
0x180411b9a  jmp     short loc_180411BAF
0x180411b9c  lea     rdx, aInvalidInputPa; "Invalid input parameters to GetSectorSi"...
0x180411ba3  mov     ecx, 4; this
0x180411ba8  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180411bad  xor     al, al
0x180411baf  mov     rcx, [rbp+440h+var_40]
0x180411bb6  xor     rcx, rsp; StackCookie
0x180411bb9  call    __security_check_cookie
0x180411bbe  mov     rbx, [rsp+540h+arg_18]
0x180411bc6  add     rsp, 510h
0x180411bcd  pop     r15
0x180411bcf  pop     r14
0x180411bd1  pop     r13
0x180411bd3  pop     r12
0x180411bd5  pop     rdi
0x180411bd6  pop     rsi
0x180411bd7  pop     rbp
0x180411bd8  retn
0x180411bda  call    __report_rangecheckfailure
```
