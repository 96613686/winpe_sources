# FileSigningInfo::GetCatalogSignerInfo(void)

- ea: `0x1800787fc`
- end: `0x180078cc6`
- name: `?GetCatalogSignerInfo@FileSigningInfo@@AEAAJXZ`
- size: `1226`
- prototype: `__int64 __fastcall(FileSigningInfo *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18007857c`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000fa50`
- `0x180010a9c`
- `0x180016440`
- `0x18001dc84`
- `0x180066c10`
- `0x1800783bc`
- `0x1800787fc`
- `0x180079084`

## import_xrefs

- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180078929`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180078929`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x180078b56`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x180078b56`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x180078a35`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x180078a35`
- `WINTRUST!WinVerifyTrust` at `0x180078af6`
- `WINTRUST!WinVerifyTrust` at `0x180078b1e`
- `WINTRUST!WinVerifyTrust` at `0x180078bf0`
- `WINTRUST!WinVerifyTrust` at `0x180078c6d`
- `WINTRUST!WinVerifyTrust` at `0x180078af6`
- `WINTRUST!WinVerifyTrust` at `0x180078b1e`
- `WINTRUST!WinVerifyTrust` at `0x180078bf0`
- `WINTRUST!WinVerifyTrust` at `0x180078c6d`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x180078b87`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x180078b87`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180078c87`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180078c87`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180078a87`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180078a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800788ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007893e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800788ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007893e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078934`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800788bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800788bb`

## string_xrefs

- `0x1800788ed`: `0x%08x CreateFile failed for file %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FileSigningInfo::GetCatalogSignerInfo(FileSigningInfo *this)
{
  const WCHAR **v2; // rdi
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  void *v5; // r14
  signed int LastError; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  BOOL v10; // ebx
  __int64 v11; // rcx
  signed int v12; // eax
  __int64 v13; // rax
  const WCHAR *v14; // rax
  __int128 *v15; // rax
  signed int v16; // eax
  const WCHAR *v17; // r14
  signed int v18; // eax
  LONG v19; // eax
  HCATINFO v20; // rax
  signed int v21; // eax
  WCHAR *v22; // rax
  LONG v23; // eax
  char **v24; // rcx
  __int64 v25; // rax
  char *v26; // r8
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  DWORD pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  HCATADMIN phCatAdmin; // [rsp+48h] [rbp-B8h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD pWVTData[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+80h] [rbp-80h]
  int *v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  int v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR *wszCatalogFile; // [rsp+C8h] [rbp-38h]
  __int128 *v42; // [rsp+D0h] [rbp-30h]
  const WCHAR *v43; // [rsp+D8h] [rbp-28h]
  BYTE *v44; // [rsp+E8h] [rbp-18h]
  DWORD v45; // [rsp+F0h] [rbp-10h]
  __int128 v46; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  _BYTE v48[32]; // [rsp+130h] [rbp+30h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+150h] [rbp+50h] BYREF
  BYTE pbHash[64]; // [rsp+360h] [rbp+260h] BYREF

  memset_0(pWVTData, 0, 0x58u);
  memset_0(&v40, 0, 0x48u);
  memset_0(pbHash, 0, sizeof(pbHash));
  pcbHash = 64;
  v46 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v46) = 0;
  phCatAdmin = 0;
  v2 = (const WCHAR **)((char *)this + 48);
  if ( *((_QWORD *)this + 9) <= 7u )
    v3 = (const WCHAR *)((char *)this + 48);
  else
    v3 = *v2;
  FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    *((_BYTE *)this + 8) = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( *((_QWORD *)this + 9) > 7u )
      v2 = (const WCHAR **)*v2;
    v8 = "0x%08x CreateFile failed for file %ws";
    v9 = 561;
LABEL_10:
    dwCreationDisposition[0] = v7;
    AslLogCallPrintf(1, "FileSigningInfo::GetCatalogSignerInfo", v9, v8, *(_QWORD *)dwCreationDisposition, v2);
    goto LABEL_54;
  }
  v10 = CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, pbHash, 0);
  CloseHandle(v5);
  if ( !v10 )
  {
    v12 = GetLastError();
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( *((_QWORD *)this + 9) > 7u )
      v2 = (const WCHAR **)*v2;
    v8 = "0x%08x CryptCATAdminCalcHashFromFileHandle failed for file %ws";
    v9 = 576;
    goto LABEL_10;
  }
  v7 = 0;
  v13 = FileSigningInfo::ConvertBytesToHexStr(v11, v48, pbHash, pcbHash);
  std::wstring::operator=(&v46, v13);
  std::wstring::~wstring(v48);
  pWVTData[0] = 88;
  v34 = 2;
  v39 = 1024;
  v37 = 1;
  v40 = 72;
  if ( *((_QWORD *)this + 9) <= 7u )
    v14 = (const WCHAR *)((char *)this + 48);
  else
    v14 = *v2;
  v43 = v14;
  v15 = &v46;
  if ( si128.m128i_i64[1] > 7uLL )
    v15 = (__int128 *)v46;
  v42 = v15;
  v45 = pcbHash;
  v44 = pbHash;
  v35 = 2;
  v36 = &v40;
  if ( *((_QWORD *)this + 28) )
  {
    v22 = (WCHAR *)((char *)this + 208);
    if ( *((_QWORD *)this + 29) > 7u )
      v22 = *(WCHAR **)v22;
    wszCatalogFile = v22;
    v23 = WinVerifyTrust(0, &FileSigningInfo::m_wvtGenericActionId, pWVTData);
    if ( v23 )
      v7 = v23;
    else
      FileSigningInfo::SaveSignerInfo(this, v38, (char *)this + 112);
  }
  else
  {
    phPrevCatInfo = 0;
    memset_0(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
    psCatInfo.cbStruct = 524;
    if ( CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
    {
      while ( 1 )
      {
        v20 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, pcbHash, 0, &phPrevCatInfo);
        phPrevCatInfo = v20;
        if ( !v20 )
          break;
        if ( CryptCATCatalogInfoFromContext(v20, &psCatInfo, 0) )
        {
          if ( v38 )
          {
            v37 = 2;
            v19 = WinVerifyTrust(0, &FileSigningInfo::m_wvtGenericActionId, pWVTData);
            if ( v19 )
            {
              v7 = v19;
              v20 = phPrevCatInfo;
              break;
            }
            v38 = 0;
          }
          wszCatalogFile = psCatInfo.wszCatalogFile;
          v37 = 1;
          if ( !WinVerifyTrust(0, &FileSigningInfo::m_wvtGenericActionId, pWVTData) )
            FileSigningInfo::SaveSignerInfo(this, v38, (char *)this + 112);
        }
        else
        {
          if ( *((_QWORD *)this + 9) <= 7u )
            v17 = (const WCHAR *)((char *)this + 48);
          else
            v17 = *v2;
          v18 = GetLastError();
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          dwCreationDispositiona[0] = v18;
          AslLogCallPrintf(
            3,
            "FileSigningInfo::GetCatalogSignerInfo",
            644,
            "0x%08x CryptCATCatalogInfoFromContext failed for file %ws",
            *(_QWORD *)dwCreationDispositiona,
            v17);
        }
      }
      if ( v20 && !CryptCATAdminReleaseCatalogContext(phCatAdmin, v20, 0) )
      {
        if ( *((_QWORD *)this + 9) > 7u )
          v2 = (const WCHAR **)*v2;
        v21 = GetLastError();
        if ( v21 > 0 )
          v21 = (unsigned __int16)v21 | 0x80070000;
        dwCreationDispositiona[0] = v21;
        AslLogCallPrintf(
          3,
          "FileSigningInfo::GetCatalogSignerInfo",
          683,
          "0x%08x CryptCATAdminReleaseCatalogContext failed for file %ws",
          *(_QWORD *)dwCreationDispositiona,
          v2);
      }
    }
    else
    {
      v16 = GetLastError();
      v7 = v16;
      if ( v16 > 0 )
        v7 = (unsigned __int16)v16 | 0x80070000;
      AslLogCallPrintf(
        1,
        "FileSigningInfo::GetCatalogSignerInfo",
        624,
        "0x%08x Failed to acquire cat admin context.",
        v7);
    }
  }
LABEL_54:
  v24 = (char **)((char *)this + 176);
  v25 = *((_QWORD *)this + 24);
  if ( v25 )
  {
    *((_QWORD *)this + 24) = v25 - 1;
    if ( *((_QWORD *)this + 25) <= 7u )
      v26 = (char *)this + 176;
    else
      v26 = *v24;
    *(_WORD *)&v26[2 * v25 - 2] = 0;
  }
  std::wstring::append(v24, L";");
  if ( v38 )
  {
    v37 = 2;
    WinVerifyTrust(0, &FileSigningInfo::m_wvtGenericActionId, pWVTData);
    v38 = 0;
  }
  if ( phCatAdmin )
  {
    CryptCATAdminReleaseContext(phCatAdmin, 0);
    phCatAdmin = 0;
  }
  std::wstring::~wstring(&v46);
  return v7;
}

```

## disassembly

```asm
0x1800787fc  push    rbp
0x1800787fe  push    rbx
0x1800787ff  push    rsi
0x180078800  push    rdi
0x180078801  push    r12
0x180078803  push    r14
0x180078805  lea     rbp, [rsp-2B8h]
0x18007880d  sub     rsp, 3B8h
0x180078814  mov     rax, cs:__security_cookie
0x18007881b  xor     rax, rsp
0x18007881e  mov     [rbp+2E0h+var_40], rax
0x180078825  mov     rsi, rcx
0x180078828  xor     edx, edx; Val
0x18007882a  lea     r8d, [rdx+58h]; Size
0x18007882e  lea     rcx, [rsp+3E0h+pWVTData]; void *
0x180078833  call    memset_0
0x180078838  xor     edx, edx; Val
0x18007883a  lea     r8d, [rdx+48h]; Size
0x18007883e  lea     rcx, [rbp+2E0h+var_320]; void *
0x180078842  call    memset_0
0x180078847  mov     ebx, 40h ; '@'
0x18007884c  mov     r8d, ebx; Size
0x18007884f  xor     edx, edx; Val
0x180078851  lea     rcx, [rbp+2E0h+pbHash]; void *
0x180078858  call    memset_0
0x18007885d  mov     [rsp+3E0h+pcbHash], ebx
0x180078861  xorps   xmm0, xmm0
0x180078864  movups  [rbp+2E0h+var_2D0], xmm0
0x180078868  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180078870  movdqu  [rbp+2E0h+var_2C0], xmm1
0x180078875  xor     eax, eax
0x180078877  mov     word ptr [rbp+2E0h+var_2D0], ax
0x18007887b  mov     [rsp+3E0h+phCatAdmin], rax
0x180078880  lea     rdi, [rsi+30h]
0x180078884  cmp     qword ptr [rdi+18h], 7
0x180078889  jbe     short loc_180078890
0x18007888b  mov     rcx, [rdi]
0x18007888e  jmp     short loc_180078893
0x180078890  mov     rcx, rdi; lpFileName
0x180078893  mov     [rsp+3E0h+hTemplateFile], 0; hTemplateFile
0x18007889c  mov     [rsp+3E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800788a4  mov     [rsp+3E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800788ac  xor     r9d, r9d; lpSecurityAttributes
0x1800788af  lea     r12d, [r9+1]
0x1800788b3  mov     r8d, r12d; dwShareMode
0x1800788b6  mov     edx, 80000000h; dwDesiredAccess
0x1800788bb  call    cs:__imp_CreateFileW
0x1800788c1  mov     r14, rax
0x1800788c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800788c8  jnz     short loc_180078917
0x1800788ca  mov     byte ptr [rsi+8], 0
0x1800788ce  call    cs:__imp_GetLastError
0x1800788d4  mov     ebx, eax
0x1800788d6  test    eax, eax
0x1800788d8  jle     short loc_1800788E3
0x1800788da  movzx   ebx, ax
0x1800788dd  or      ebx, 80070000h
0x1800788e3  cmp     qword ptr [rdi+18h], 7
0x1800788e8  jbe     short loc_1800788ED
0x1800788ea  mov     rdi, [rdi]
0x1800788ed  lea     r9, a0x08xCreatefil; "0x%08x CreateFile failed for file %ws"
0x1800788f4  mov     r8d, 231h
0x1800788fa  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], rdi
0x1800788ff  mov     [rsp+3E0h+dwCreationDisposition], ebx
0x180078903  mov     ecx, r12d
0x180078906  lea     rdx, aFilesigninginf_0; "FileSigningInfo::GetCatalogSignerInfo"
0x18007890d  call    AslLogCallPrintf
0x180078912  jmp     loc_180078C0E
0x180078917  xor     r9d, r9d; dwFlags
0x18007891a  lea     r8, [rbp+2E0h+pbHash]; pbHash
0x180078921  lea     rdx, [rsp+3E0h+pcbHash]; pcbHash
0x180078926  mov     rcx, r14; hFile
0x180078929  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18007892f  mov     ebx, eax
0x180078931  mov     rcx, r14; hObject
0x180078934  call    cs:__imp_CloseHandle
0x18007893a  test    ebx, ebx
0x18007893c  jnz     short loc_18007896C
0x18007893e  call    cs:__imp_GetLastError
0x180078944  mov     ebx, eax
0x180078946  test    eax, eax
0x180078948  jle     short loc_180078953
0x18007894a  movzx   ebx, ax
0x18007894d  or      ebx, 80070000h
0x180078953  cmp     qword ptr [rdi+18h], 7
0x180078958  jbe     short loc_18007895D
0x18007895a  mov     rdi, [rdi]
0x18007895d  lea     r9, a0x08xCryptcata; "0x%08x CryptCATAdminCalcHashFromFileHan"...
0x180078964  mov     r8d, 240h
0x18007896a  jmp     short loc_1800788FA
0x18007896c  xor     ebx, ebx
0x18007896e  mov     r9d, [rsp+3E0h+pcbHash]
0x180078973  lea     r8, [rbp+2E0h+pbHash]
0x18007897a  lea     rdx, [rbp+2E0h+var_2B0]
0x18007897e  call    ?ConvertBytesToHexStr@FileSigningInfo@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAEK@Z; FileSigningInfo::ConvertBytesToHexStr(uchar *,ulong)
0x180078983  mov     rdx, rax
0x180078986  lea     rcx, [rbp+2E0h+var_2D0]
0x18007898a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007898f  lea     rcx, [rbp+2E0h+var_2B0]; void *
0x180078993  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180078998  mov     [rsp+3E0h+pWVTData], 58h ; 'X'
0x1800789a0  mov     [rsp+3E0h+var_368], 2
0x1800789a9  mov     [rbp+2E0h+var_338], 400h
0x1800789b0  mov     [rbp+2E0h+var_350], r12d
0x1800789b4  mov     [rbp+2E0h+var_320], 48h ; 'H'
0x1800789bb  cmp     qword ptr [rdi+18h], 7
0x1800789c0  jbe     short loc_1800789C7
0x1800789c2  mov     rax, [rdi]
0x1800789c5  jmp     short loc_1800789CA
0x1800789c7  mov     rax, rdi
0x1800789ca  mov     [rbp+2E0h+var_308], rax
0x1800789ce  lea     rax, [rbp+2E0h+var_2D0]
0x1800789d2  cmp     qword ptr [rbp+2E0h+var_2C0+8], 7
0x1800789d7  cmova   rax, qword ptr [rbp+2E0h+var_2D0]
0x1800789dc  mov     [rbp+2E0h+var_310], rax
0x1800789e0  mov     eax, [rsp+3E0h+pcbHash]
0x1800789e4  mov     [rbp+2E0h+var_2F0], eax
0x1800789e7  lea     rax, [rbp+2E0h+pbHash]
0x1800789ee  mov     [rbp+2E0h+var_2F8], rax
0x1800789f2  mov     [rbp+2E0h+var_360], 2
0x1800789f9  lea     rax, [rbp+2E0h+var_320]
0x1800789fd  mov     [rbp+2E0h+var_358], rax
0x180078a01  cmp     [rsi+0E0h], rbx
0x180078a08  jnz     loc_180078BCD
0x180078a0e  mov     [rsp+3E0h+phPrevCatInfo], rbx
0x180078a13  xor     edx, edx; Val
0x180078a15  mov     r8d, 208h; Size
0x180078a1b  lea     rcx, [rbp+2E0h+psCatInfo.wszCatalogFile]; void *
0x180078a1f  call    memset_0
0x180078a24  mov     [rbp+2E0h+psCatInfo.cbStruct], 20Ch
0x180078a2b  xor     r8d, r8d; dwFlags
0x180078a2e  xor     edx, edx; pgSubsystem
0x180078a30  lea     rcx, [rsp+3E0h+phCatAdmin]; phCatAdmin
0x180078a35  call    cs:__imp_CryptCATAdminAcquireContext
0x180078a3b  test    eax, eax
0x180078a3d  jnz     loc_180078B38
0x180078a43  call    cs:__imp_GetLastError
0x180078a49  mov     ebx, eax
0x180078a4b  test    eax, eax
0x180078a4d  jle     short loc_180078A58
0x180078a4f  movzx   ebx, ax
0x180078a52  or      ebx, 80070000h
0x180078a58  mov     [rsp+3E0h+dwCreationDisposition], ebx
0x180078a5c  lea     r9, a0x08xFailedToA_0; "0x%08x Failed to acquire cat admin cont"...
0x180078a63  mov     r8d, 270h
0x180078a69  lea     rdx, aFilesigninginf_0; "FileSigningInfo::GetCatalogSignerInfo"
0x180078a70  mov     ecx, r12d
0x180078a73  call    AslLogCallPrintf
0x180078a78  jmp     loc_180078C0E
0x180078a7d  xor     r8d, r8d; dwFlags
0x180078a80  lea     rdx, [rbp+2E0h+psCatInfo]; psCatInfo
0x180078a84  mov     rcx, rax; hCatInfo
0x180078a87  call    cs:__imp_CryptCATCatalogInfoFromContext
0x180078a8d  test    eax, eax
0x180078a8f  jnz     short loc_180078ADB
0x180078a91  cmp     qword ptr [rsi+48h], 7
0x180078a96  jbe     short loc_180078A9D
0x180078a98  mov     r14, [rdi]
0x180078a9b  jmp     short loc_180078AA0
0x180078a9d  mov     r14, rdi
0x180078aa0  call    cs:__imp_GetLastError
0x180078aa6  test    eax, eax
0x180078aa8  jle     short loc_180078AB2
0x180078aaa  movzx   eax, ax
0x180078aad  or      eax, 80070000h
0x180078ab2  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], r14
0x180078ab7  mov     [rsp+3E0h+dwCreationDisposition], eax
0x180078abb  lea     r9, a0x08xCryptcatc; "0x%08x CryptCATCatalogInfoFromContext f"...
0x180078ac2  mov     r8d, 284h
0x180078ac8  lea     rdx, aFilesigninginf_0; "FileSigningInfo::GetCatalogSignerInfo"
0x180078acf  mov     ecx, 3
0x180078ad4  call    AslLogCallPrintf
0x180078ad9  jmp     short loc_180078B38
0x180078adb  cmp     [rbp+2E0h+var_348], rbx
0x180078adf  jz      short loc_180078B04
0x180078ae1  mov     [rbp+2E0h+var_350], 2
0x180078ae8  lea     r8, [rsp+3E0h+pWVTData]; pWVTData
0x180078aed  lea     rdx, ?m_wvtGenericActionId@FileSigningInfo@@0U_GUID@@A; pgActionID
0x180078af4  xor     ecx, ecx; hwnd
0x180078af6  call    cs:__imp_WinVerifyTrust
0x180078afc  test    eax, eax
0x180078afe  jnz     short loc_180078B6C
0x180078b00  mov     [rbp+2E0h+var_348], rbx
0x180078b04  lea     rax, [rbp+2E0h+psCatInfo.wszCatalogFile]
0x180078b08  mov     [rbp+2E0h+var_318], rax
0x180078b0c  mov     [rbp+2E0h+var_350], r12d
0x180078b10  lea     r8, [rsp+3E0h+pWVTData]; pWVTData
0x180078b15  lea     rdx, ?m_wvtGenericActionId@FileSigningInfo@@0U_GUID@@A; pgActionID
0x180078b1c  xor     ecx, ecx; hwnd
0x180078b1e  call    cs:__imp_WinVerifyTrust
0x180078b24  test    eax, eax
0x180078b26  jnz     short loc_180078B38
0x180078b28  lea     r8, [rsi+70h]
0x180078b2c  mov     rdx, [rbp+2E0h+var_348]
0x180078b30  mov     rcx, rsi
0x180078b33  call    ?SaveSignerInfo@FileSigningInfo@@AEAAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileSigningInfo::SaveSignerInfo(void *,std::wstring &)
0x180078b38  lea     rax, [rsp+3E0h+phPrevCatInfo]
0x180078b3d  mov     qword ptr [rsp+3E0h+dwCreationDisposition], rax; phPrevCatInfo
0x180078b42  xor     r9d, r9d; dwFlags
0x180078b45  mov     r8d, [rsp+3E0h+pcbHash]; cbHash
0x180078b4a  lea     rdx, [rbp+2E0h+pbHash]; pbHash
0x180078b51  mov     rcx, [rsp+3E0h+phCatAdmin]; hCatAdmin
0x180078b56  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x180078b5c  test    rax, rax
0x180078b5f  mov     [rsp+3E0h+phPrevCatInfo], rax
0x180078b64  jnz     loc_180078A7D
0x180078b6a  jmp     short loc_180078B73
0x180078b6c  mov     ebx, eax
0x180078b6e  mov     rax, [rsp+3E0h+phPrevCatInfo]
0x180078b73  test    rax, rax
0x180078b76  jz      loc_180078C0E
0x180078b7c  xor     r8d, r8d; dwFlags
0x180078b7f  mov     rdx, rax; hCatInfo
0x180078b82  mov     rcx, [rsp+3E0h+phCatAdmin]; hCatAdmin
0x180078b87  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x180078b8d  test    eax, eax
0x180078b8f  jnz     short loc_180078C0E
0x180078b91  cmp     qword ptr [rdi+18h], 7
0x180078b96  jbe     short loc_180078B9B
0x180078b98  mov     rdi, [rdi]
0x180078b9b  call    cs:__imp_GetLastError
0x180078ba1  test    eax, eax
0x180078ba3  jle     short loc_180078BAD
0x180078ba5  movzx   eax, ax
0x180078ba8  or      eax, 80070000h
0x180078bad  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], rdi
0x180078bb2  mov     [rsp+3E0h+dwCreationDisposition], eax
0x180078bb6  lea     r9, a0x08xCryptcata_0; "0x%08x CryptCATAdminReleaseCatalogConte"...
0x180078bbd  mov     r8d, 2ABh
0x180078bc3  mov     ecx, 3
0x180078bc8  jmp     loc_180078906
0x180078bcd  lea     rax, [rsi+0D0h]
0x180078bd4  cmp     qword ptr [rax+18h], 7
0x180078bd9  jbe     short loc_180078BDE
0x180078bdb  mov     rax, [rax]
0x180078bde  mov     [rbp+2E0h+var_318], rax
0x180078be2  lea     r8, [rsp+3E0h+pWVTData]; pWVTData
0x180078be7  lea     rdx, ?m_wvtGenericActionId@FileSigningInfo@@0U_GUID@@A; pgActionID
0x180078bee  xor     ecx, ecx; hwnd
0x180078bf0  call    cs:__imp_WinVerifyTrust
0x180078bf6  test    eax, eax
0x180078bf8  jz      short loc_180078BFE
0x180078bfa  mov     ebx, eax
0x180078bfc  jmp     short loc_180078C0E
0x180078bfe  lea     r8, [rsi+70h]
0x180078c02  mov     rdx, [rbp+2E0h+var_348]
0x180078c06  mov     rcx, rsi
0x180078c09  call    ?SaveSignerInfo@FileSigningInfo@@AEAAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileSigningInfo::SaveSignerInfo(void *,std::wstring &)
0x180078c0e  lea     rcx, [rsi+0B0h]; Src
0x180078c15  mov     rax, [rcx+10h]
0x180078c19  test    rax, rax
0x180078c1c  jz      short loc_180078C45
0x180078c1e  lea     rdx, [rax-1]
0x180078c22  cmp     rax, rdx
0x180078c25  jb      loc_180078CC0
0x180078c2b  mov     [rcx+10h], rdx
0x180078c2f  cmp     qword ptr [rcx+18h], 7
0x180078c34  jbe     short loc_180078C3B
0x180078c36  mov     r8, [rcx]
0x180078c39  jmp     short loc_180078C3E
0x180078c3b  mov     r8, rcx
0x180078c3e  xor     eax, eax
0x180078c40  mov     [r8+rdx*2], ax
0x180078c45  lea     rdx, asc_180123B10; ";"
0x180078c4c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180078c51  cmp     [rbp+2E0h+var_348], 0
0x180078c56  jz      short loc_180078C7B
0x180078c58  mov     [rbp+2E0h+var_350], 2
0x180078c5f  lea     r8, [rsp+3E0h+pWVTData]; pWVTData
0x180078c64  lea     rdx, ?m_wvtGenericActionId@FileSigningInfo@@0U_GUID@@A; pgActionID
0x180078c6b  xor     ecx, ecx; hwnd
0x180078c6d  call    cs:__imp_WinVerifyTrust
0x180078c73  mov     [rbp+2E0h+var_348], 0
0x180078c7b  mov     rcx, [rsp+3E0h+phCatAdmin]; hCatAdmin
0x180078c80  test    rcx, rcx
0x180078c83  jz      short loc_180078C96
0x180078c85  xor     edx, edx; dwFlags
0x180078c87  call    cs:__imp_CryptCATAdminReleaseContext
0x180078c8d  mov     [rsp+3E0h+phCatAdmin], 0
0x180078c96  lea     rcx, [rbp+2E0h+var_2D0]; void *
0x180078c9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180078c9f  mov     eax, ebx
0x180078ca1  mov     rcx, [rbp+2E0h+var_40]
0x180078ca8  xor     rcx, rsp; StackCookie
0x180078cab  call    __security_check_cookie
0x180078cb0  add     rsp, 3B8h
0x180078cb7  pop     r14
0x180078cb9  pop     r12
0x180078cbb  pop     rdi
0x180078cbc  pop     rsi
0x180078cbd  pop     rbx
0x180078cbe  pop     rbp
0x180078cbf  retn
0x180078cc0  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
