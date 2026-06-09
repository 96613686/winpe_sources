# CCatalogServer::CreateReplicationDir(ushort * *)

- ea: `0x18000a420`
- end: `0x18000a64e`
- name: `?CreateReplicationDir@CCatalogServer@@UEAAJPEAPEAG@Z`
- size: `558`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180009098`
- `0x18000a01c`
- `0x18000a420`
- `0x18000ae48`
- `0x18000ae78`
- `0x18001ec1c`
- `0x1800308c4`
- `0x180032c98`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a59c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a59c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a518`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a583`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a518`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a5da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a5da`

## string_xrefs

- `0x18000a548`: `'CreateReplicationDir:CreateDirectory(COM)'`
- `0x18000a5ae`: `'CreateReplicationDir:CreateDirectory(COM\Replication)'`
- `0x18000a489`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000a474`: `'CreateReplicationDir'`
- `0x18000a4de`: `'CreateReplicationDir:ImpersonateClient'`
- `0x18000a4ff`: `'CreateReplicationDir:GetDefaultComPlusInstallDirectory'`

## pseudocode

```c
__int64 __fastcall CCatalogServer::CreateReplicationDir(CCatalogServer *this, LPVOID *a2)
{
  signed int DefaultComPlusInstallDirectory; // eax
  const unsigned __int16 *v4; // r9
  unsigned int v5; // r8d
  unsigned __int64 v6; // rdx
  DWORD LastError; // eax
  DWORD v8; // eax
  __int64 v9; // rax
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  signed int v14; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-D4h]
  int v16; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+54h] [rbp-ACh]
  void *ppInterface; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  WCHAR PathName[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(PathName, 0, 0x20Au);
  ppInterface = 0;
  v23 = 0;
  v24 = 0;
  if ( !a2 )
  {
    DefaultComPlusInstallDirectory = -2147024809;
    v4 = L"'CreateReplicationDir'";
    v5 = 640;
LABEL_3:
    LODWORD(v13) = DefaultComPlusInstallDirectory;
LABEL_4:
    v14 = DefaultComPlusInstallDirectory;
    v16 = -1073737001;
    v15 = 22;
    v17 = v4;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 1;
    CError::WriteToLog((CError *)&v14, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", v5, v4, v13);
    goto LABEL_28;
  }
  DefaultComPlusInstallDirectory = CImpersonate::ImpersonateClient(&ppInterface);
  LODWORD(v13) = DefaultComPlusInstallDirectory;
  if ( DefaultComPlusInstallDirectory < 0 )
  {
    v4 = L"'CreateReplicationDir:ImpersonateClient'";
    v5 = 647;
    goto LABEL_4;
  }
  DefaultComPlusInstallDirectory = GetDefaultComPlusInstallDirectory(PathName, v6);
  LODWORD(v13) = DefaultComPlusInstallDirectory;
  if ( DefaultComPlusInstallDirectory < 0 )
  {
    v4 = L"'CreateReplicationDir:GetDefaultComPlusInstallDirectory'";
    v5 = 655;
    goto LABEL_4;
  }
  if ( !CreateDirectoryW(PathName, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 80 && LastError != 183 )
    {
      DefaultComPlusInstallDirectory = GetLastError();
      if ( DefaultComPlusInstallDirectory > 0 )
        DefaultComPlusInstallDirectory = (unsigned __int16)DefaultComPlusInstallDirectory | 0x80070000;
      v4 = L"'CreateReplicationDir:CreateDirectory(COM)'";
      v5 = 666;
      goto LABEL_3;
    }
  }
  LODWORD(v13) = StringCchCatW(PathName, 0x105u, L"\\Replication");
  if ( (int)v13 < 0 )
    goto LABEL_28;
  if ( !CreateDirectoryW(PathName, 0) )
  {
    v8 = GetLastError();
    if ( v8 != 80 && v8 != 183 )
    {
      DefaultComPlusInstallDirectory = GetLastError();
      if ( DefaultComPlusInstallDirectory > 0 )
        DefaultComPlusInstallDirectory = (unsigned __int16)DefaultComPlusInstallDirectory | 0x80070000;
      v4 = L"'CreateReplicationDir:CreateDirectory(COM\\Replication)'";
      v5 = 680;
      goto LABEL_3;
    }
  }
  v9 = -1;
  do
    ++v9;
  while ( PathName[v9] );
  v10 = v9 + 1;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v9 + 1));
  *a2 = v11;
  if ( v11 )
  {
    LODWORD(v13) = StringCchCopyW(v11, v10, PathName);
    if ( (int)v13 < 0 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
  }
  else
  {
    LODWORD(v13) = -2147024882;
  }
LABEL_28:
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, (int *)&v13);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000a420  push    rbp
0x18000a422  push    rbx
0x18000a423  push    rsi
0x18000a424  push    rdi
0x18000a425  lea     rbp, [rsp-198h]
0x18000a42d  sub     rsp, 298h
0x18000a434  mov     rax, cs:__security_cookie
0x18000a43b  xor     rax, rsp
0x18000a43e  mov     [rbp+1B0h+var_30], rax
0x18000a445  mov     rbx, rdx
0x18000a448  lea     rcx, [rsp+2B0h+PathName]; void *
0x18000a44d  xor     edx, edx; Val
0x18000a44f  mov     r8d, 20Ah; Size
0x18000a455  call    memset_0
0x18000a45a  xor     esi, esi
0x18000a45c  mov     [rsp+2B0h+ppInterface], rsi
0x18000a461  mov     [rsp+2B0h+var_250], esi
0x18000a465  mov     [rsp+2B0h+var_248], rsi
0x18000a46a  test    rbx, rbx
0x18000a46d  jnz     short loc_18000A4CC
0x18000a46f  mov     eax, 80070057h
0x18000a474  lea     r9, aCreatereplicat; "'CreateReplicationDir'"
0x18000a47b  mov     r8d, 280h; unsigned int
0x18000a481  mov     dword ptr [rsp+2B0h+var_290], eax
0x18000a485  mov     [rsp+2B0h+var_288], eax
0x18000a489  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000a490  mov     eax, 16h
0x18000a495  mov     [rsp+2B0h+var_280], 0C00012D7h
0x18000a49d  lea     rcx, [rsp+2B0h+var_288]; this
0x18000a4a2  mov     [rsp+2B0h+var_284], ax
0x18000a4a7  mov     [rsp+2B0h+var_278], r9
0x18000a4ac  mov     [rsp+2B0h+var_270], rsi
0x18000a4b1  mov     [rsp+2B0h+var_268], rsi
0x18000a4b6  mov     [rsp+2B0h+var_260], esi
0x18000a4ba  mov     [rsp+2B0h+var_25C], 1
0x18000a4c2  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000a4c7  jmp     loc_18000A616
0x18000a4cc  lea     rcx, [rsp+2B0h+ppInterface]; ppInterface
0x18000a4d1  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18000a4d6  mov     dword ptr [rsp+2B0h+var_290], eax
0x18000a4da  test    eax, eax
0x18000a4dc  jns     short loc_18000A4ED
0x18000a4de  lea     r9, aCreatereplicat_1; "'CreateReplicationDir:ImpersonateClient"...
0x18000a4e5  mov     r8d, 287h
0x18000a4eb  jmp     short loc_18000A485
0x18000a4ed  lea     rcx, [rsp+2B0h+PathName]; unsigned __int16 *
0x18000a4f2  call    ?GetDefaultComPlusInstallDirectory@@YAJPEAG_K@Z; GetDefaultComPlusInstallDirectory(ushort *,unsigned __int64)
0x18000a4f7  mov     dword ptr [rsp+2B0h+var_290], eax
0x18000a4fb  test    eax, eax
0x18000a4fd  jns     short loc_18000A511
0x18000a4ff  lea     r9, aCreatereplicat_0; "'CreateReplicationDir:GetDefaultComPlus"...
0x18000a506  mov     r8d, 28Fh
0x18000a50c  jmp     loc_18000A485
0x18000a511  xor     edx, edx; lpSecurityAttributes
0x18000a513  lea     rcx, [rsp+2B0h+PathName]; lpPathName
0x18000a518  call    cs:__imp_CreateDirectoryW
0x18000a51e  mov     edi, 0B7h
0x18000a523  test    eax, eax
0x18000a525  jnz     short loc_18000A55A
0x18000a527  call    cs:__imp_GetLastError
0x18000a52d  cmp     eax, 50h ; 'P'
0x18000a530  jz      short loc_18000A55A
0x18000a532  cmp     eax, edi
0x18000a534  jz      short loc_18000A55A
0x18000a536  call    cs:__imp_GetLastError
0x18000a53c  test    eax, eax
0x18000a53e  jle     short loc_18000A548
0x18000a540  movzx   eax, ax
0x18000a543  or      eax, 80070000h
0x18000a548  lea     r9, aCreatereplicat_2; "'CreateReplicationDir:CreateDirectory(C"...
0x18000a54f  mov     r8d, 29Ah
0x18000a555  jmp     loc_18000A481
0x18000a55a  lea     r8, aReplication; "\\Replication"
0x18000a561  mov     edx, 105h; unsigned __int64
0x18000a566  lea     rcx, [rsp+2B0h+PathName]; unsigned __int16 *
0x18000a56b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a570  mov     dword ptr [rsp+2B0h+var_290], eax
0x18000a574  test    eax, eax
0x18000a576  js      loc_18000A616
0x18000a57c  xor     edx, edx; lpSecurityAttributes
0x18000a57e  lea     rcx, [rsp+2B0h+PathName]; lpPathName
0x18000a583  call    cs:__imp_CreateDirectoryW
0x18000a589  test    eax, eax
0x18000a58b  jnz     short loc_18000A5C0
0x18000a58d  call    cs:__imp_GetLastError
0x18000a593  cmp     eax, 50h ; 'P'
0x18000a596  jz      short loc_18000A5C0
0x18000a598  cmp     eax, edi
0x18000a59a  jz      short loc_18000A5C0
0x18000a59c  call    cs:__imp_GetLastError
0x18000a5a2  test    eax, eax
0x18000a5a4  jle     short loc_18000A5AE
0x18000a5a6  movzx   eax, ax
0x18000a5a9  or      eax, 80070000h
0x18000a5ae  lea     r9, aCreatereplicat_3; "'CreateReplicationDir:CreateDirectory(C"...
0x18000a5b5  mov     r8d, 2A8h
0x18000a5bb  jmp     loc_18000A481
0x18000a5c0  lea     rcx, [rsp+2B0h+PathName]
0x18000a5c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a5c9  inc     rax
0x18000a5cc  cmp     [rcx+rax*2], si
0x18000a5d0  jnz     short loc_18000A5C9
0x18000a5d2  lea     rdi, [rax+1]
0x18000a5d6  lea     rcx, [rdi+rdi]; cb
0x18000a5da  call    cs:__imp_CoTaskMemAlloc
0x18000a5e0  mov     [rbx], rax
0x18000a5e3  test    rax, rax
0x18000a5e6  jnz     short loc_18000A5F2
0x18000a5e8  mov     dword ptr [rsp+2B0h+var_290], 8007000Eh
0x18000a5f0  jmp     short loc_18000A616
0x18000a5f2  lea     r8, [rsp+2B0h+PathName]; unsigned __int16 *
0x18000a5f7  mov     rdx, rdi; unsigned __int64
0x18000a5fa  mov     rcx, rax; unsigned __int16 *
0x18000a5fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a602  mov     dword ptr [rsp+2B0h+var_290], eax
0x18000a606  test    eax, eax
0x18000a608  jns     short loc_18000A616
0x18000a60a  mov     rcx, [rbx]; pv
0x18000a60d  call    cs:__imp_CoTaskMemFree
0x18000a613  mov     [rbx], rsi
0x18000a616  lea     rdx, [rsp+2B0h+var_290]; int *
0x18000a61b  lea     rcx, [rsp+2B0h+ppInterface]; this
0x18000a620  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x18000a625  lea     rcx, [rsp+2B0h+ppInterface]; this
0x18000a62a  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18000a62f  mov     eax, dword ptr [rsp+2B0h+var_290]
0x18000a633  mov     rcx, [rbp+1B0h+var_30]
0x18000a63a  xor     rcx, rsp; StackCookie
0x18000a63d  call    __security_check_cookie
0x18000a642  add     rsp, 298h
0x18000a649  pop     rdi
0x18000a64a  pop     rsi
0x18000a64b  pop     rbx
0x18000a64c  pop     rbp
0x18000a64d  retn
```
