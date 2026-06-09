# CWANPPPConnectionService::RequestConnection(void)

- ea: `0x18008d170`
- end: `0x18008d48b`
- name: `?RequestConnection@CWANPPPConnectionService@@UEAAJXZ`
- size: `795`
- prototype: `__int64 __fastcall(CWANPPPConnectionService *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180034eb8`
- `0x18004e0c0`
- `0x18004ed64`
- `0x1800891d8`
- `0x18008b404`
- `0x18008b4dc`
- `0x18008b68c`
- `0x18008d170`
- `0x18008e890`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d3d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d3d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008d406`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008d406`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008d3c1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008d3c1`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18008d39d`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18008d39d`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasDialW` at `0x18008d30f`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasDialW` at `0x18008d30f`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetCredentialsW` at `0x18008d228`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetCredentialsW` at `0x18008d228`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedConnection` at `0x18008d1df`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedConnection` at `0x18008d1df`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x18008d426`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x18008d426`

## string_xrefs

- `0x18008d3ba`: `RASDLG.DLL`

## pseudocode

```c
__int64 __fastcall CWANPPPConnectionService::RequestConnection(CWANPPPConnectionService *this)
{
  int v2; // ebx
  __int64 v3; // rdi
  __int64 v4; // rsi
  unsigned int v5; // r11d
  unsigned int v6; // r11d
  tagRASCREDENTIALSW *v7; // rax
  DWORD EntryPropertiesW; // edi
  tagRASDIALPARAMSW *v9; // rax
  HMODULE LibraryW; // rax
  HMODULE v11; // rsi
  FARPROC ProcAddress; // rax
  DWORD v14; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v15; // [rsp+34h] [rbp-CCh] BYREF
  HRASCONN v16; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v17[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[16]; // [rsp+70h] [rbp-90h] BYREF
  tagRASDIALEXTENSIONS v19; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[12]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v21[260]; // [rsp+CCh] [rbp-34h] BYREF
  WCHAR v22[262]; // [rsp+2D4h] [rbp+1D4h] BYREF
  tagRASCREDENTIALSW v23; // [rsp+4E0h] [rbp+3E0h] BYREF
  tagRASDIALPARAMSW v24; // [rsp+910h] [rbp+810h] BYREF
  tagRASENTRYW v25; // [rsp+1160h] [rbp+1060h] BYREF

  *((_DWORD *)this + 36) = 0;
  v2 = CWANConnectionBase::ControlEnabled(this);
  if ( v2 < 0 )
  {
    SetUPnPError(L"800");
    return (unsigned int)v2;
  }
  memset_0(v20, 0, 0x420u);
  CSwitchSecurityContext::CSwitchSecurityContext((CSwitchSecurityContext *)v18);
  if ( (unsigned int)RasQuerySharedConnection(v20) )
  {
    v2 = -2147467259;
    goto LABEL_23;
  }
  memset_0(v23.szUserName, 0, 0x424u);
  v3 = 1068;
  v23.dwMask = 15;
  v23.dwSize = 1068;
  if ( RasGetCredentialsW(v22, v21, &v23) )
  {
    v2 = -2147467259;
  }
  else
  {
    memset(&v19.hwndParent, 0, 52);
    v19.dwSize = 60;
    v19.dwfOptions = 512;
    memset_0(v24.szEntryName, 0, 0x844u);
    v4 = 2120;
    v24.dwSize = 2120;
    StringCchCopyW(v24.szEntryName, 0x101u, v21);
    StringCchCopyW(v24.szUserName, v5, v23.szUserName);
    StringCchCopyW(v24.szDomain, 0x10u, v23.szDomain);
    StringCchCopyW(v24.szPassword, v6, v23.szPassword);
    v7 = &v23;
    do
    {
      LOBYTE(v7->dwSize) = 0;
      v7 = (tagRASCREDENTIALSW *)((char *)v7 + 1);
      --v3;
    }
    while ( v3 );
    v16 = 0;
    EntryPropertiesW = RasDialW(&v19, v22, &v24, 0, 0, &v16);
    v9 = &v24;
    do
    {
      LOBYTE(v9->dwSize) = 0;
      v9 = (tagRASDIALPARAMSW *)((char *)v9 + 1);
      --v4;
    }
    while ( v4 );
    if ( EntryPropertiesW == -2147467263 )
    {
      v14 = 0;
      memset(v17, 0, sizeof(v17));
      LODWORD(v17[0]) = 48;
      memset_0(&v25.dwfOptions, 0, 0x1A40u);
      v15 = 6724;
      v25.dwSize = 6724;
      EntryPropertiesW = RasGetEntryPropertiesW(v22, v21, &v25, &v15, 0, &v14);
      if ( !EntryPropertiesW )
      {
        EntryPropertiesW = 50;
        if ( v25.dwType == 4 )
        {
          HIDWORD(v17[0]) |= 2u;
          LibraryW = LoadLibraryW(L"RASDLG.DLL");
          v11 = LibraryW;
          if ( LibraryW )
          {
            ProcAddress = GetProcAddress(LibraryW, "RasDialDlgW");
            if ( ProcAddress
              && ((unsigned int (__fastcall *)(WCHAR *, WCHAR *, _QWORD, _OWORD *))ProcAddress)(v22, v21, 0, v17) )
            {
              EntryPropertiesW = 0;
            }
            FreeLibrary(v11);
          }
        }
      }
    }
    *((_DWORD *)this + 36) = EntryPropertiesW;
    if ( EntryPropertiesW )
    {
      v2 = -2147467259;
      if ( v16 )
      {
        RasHangUpW(v16);
        goto LABEL_20;
      }
LABEL_23:
      SetUPnPError(L"704");
      goto LABEL_24;
    }
  }
LABEL_20:
  if ( v2 < 0 )
    goto LABEL_23;
LABEL_24:
  CSwitchSecurityContext::~CSwitchSecurityContext((CSwitchSecurityContext *)v18);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008d170  mov     [rsp-8+arg_8], rbx
0x18008d175  mov     [rsp-8+arg_10], rsi
0x18008d17a  push    rbp
0x18008d17b  push    rdi
0x18008d17c  push    r14
0x18008d17e  lea     rbp, [rsp-2AC0h]
0x18008d186  mov     eax, 2BC0h
0x18008d18b  call    _alloca_probe
0x18008d190  sub     rsp, rax
0x18008d193  mov     rax, cs:__security_cookie
0x18008d19a  xor     rax, rsp
0x18008d19d  mov     [rbp+2AD0h+var_20], rax
0x18008d1a4  mov     r14, rcx
0x18008d1a7  mov     dword ptr [rcx+90h], 0
0x18008d1b1  call    ?ControlEnabled@CWANConnectionBase@@IEAAJXZ; CWANConnectionBase::ControlEnabled(void)
0x18008d1b6  mov     ebx, eax
0x18008d1b8  test    eax, eax
0x18008d1ba  js      loc_18008D456
0x18008d1c0  xor     edx, edx; Val
0x18008d1c2  lea     rcx, [rbp+2AD0h+var_2B10]; void *
0x18008d1c6  mov     r8d, 420h; Size
0x18008d1cc  call    memset_0
0x18008d1d1  lea     rcx, [rsp+2BD0h+var_2B60]; this
0x18008d1d6  call    ??0CSwitchSecurityContext@@QEAA@XZ; CSwitchSecurityContext::CSwitchSecurityContext(void)
0x18008d1db  lea     rcx, [rbp+2AD0h+var_2B10]
0x18008d1df  call    cs:__imp_RasQuerySharedConnection
0x18008d1e5  test    eax, eax
0x18008d1e7  jnz     loc_18008D439
0x18008d1ed  xor     edx, edx; Val
0x18008d1ef  lea     rcx, [rbp+2AD0h+var_26F0.szUserName]; void *
0x18008d1f6  mov     r8d, 424h; Size
0x18008d1fc  call    memset_0
0x18008d201  mov     edi, 42Ch
0x18008d206  mov     [rbp+2AD0h+var_26F0.dwMask], 0Fh
0x18008d210  lea     r8, [rbp+2AD0h+var_26F0]; struct tagRASCREDENTIALSW *
0x18008d217  mov     [rbp+2AD0h+var_26F0.dwSize], edi
0x18008d21d  lea     rdx, [rbp+2AD0h+var_2B04]; LPCWSTR
0x18008d221  lea     rcx, [rbp+2AD0h+var_28FC]; LPCWSTR
0x18008d228  call    cs:__imp_RasGetCredentialsW
0x18008d22e  test    eax, eax
0x18008d230  jnz     loc_18008D42E
0x18008d236  xorps   xmm0, xmm0
0x18008d239  lea     rcx, [rbp+2AD0h+var_22C0.szEntryName]; void *
0x18008d240  movups  xmmword ptr [rbp+2AD0h+var_2B50.dwSize], xmm0
0x18008d244  xor     edx, edx; Val
0x18008d246  mov     r8d, 844h; Size
0x18008d24c  movups  xmmword ptr [rbp+2AD0h+var_2B50.RasEapInfo.dwSizeofEapInfo], xmm0
0x18008d250  mov     [rbp+2AD0h+var_2B50.dwSize], 3Ch ; '<'
0x18008d257  movups  xmmword ptr [rbp+2AD0h+var_2B50.fSkipPppAuth], xmm0
0x18008d25b  mov     [rbp+2AD0h+var_2B50.dwfOptions], 200h
0x18008d262  movups  xmmword ptr [rbp+2AD0h+var_2B50.reserved], xmm0
0x18008d266  call    memset_0
0x18008d26b  mov     r11d, 101h
0x18008d271  lea     r8, [rbp+2AD0h+var_2B04]; unsigned __int16 *
0x18008d275  mov     esi, 848h
0x18008d27a  lea     rcx, [rbp+2AD0h+var_22C0.szEntryName]; unsigned __int16 *
0x18008d281  mov     edx, r11d; unsigned __int64
0x18008d284  mov     [rbp+2AD0h+var_22C0.dwSize], esi
0x18008d28a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d28f  lea     r8, [rbp+2AD0h+var_26F0.szUserName]; unsigned __int16 *
0x18008d296  mov     edx, r11d; unsigned __int64
0x18008d299  lea     rcx, [rbp+2AD0h+var_22C0.szUserName]; unsigned __int16 *
0x18008d2a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d2a5  lea     r8, [rbp+2AD0h+var_26F0.szDomain]; unsigned __int16 *
0x18008d2ac  mov     edx, 10h; unsigned __int64
0x18008d2b1  lea     rcx, [rbp+2AD0h+var_22C0.szDomain]; unsigned __int16 *
0x18008d2b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d2bd  lea     r8, [rbp+2AD0h+var_26F0.szPassword]; unsigned __int16 *
0x18008d2c4  mov     edx, r11d; unsigned __int64
0x18008d2c7  lea     rcx, [rbp+2AD0h+var_22C0.szPassword]; unsigned __int16 *
0x18008d2ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d2d3  lea     rax, [rbp+2AD0h+var_26F0]
0x18008d2da  mov     byte ptr [rax], 0
0x18008d2dd  inc     rax
0x18008d2e0  sub     rdi, 1
0x18008d2e4  jnz     short loc_18008D2DA
0x18008d2e6  lea     rax, [rsp+2BD0h+var_2B98]
0x18008d2eb  mov     [rsp+2BD0h+var_2B98], rdi
0x18008d2f0  mov     [rsp+2BD0h+var_2BA8], rax; HRASCONN *
0x18008d2f5  lea     r8, [rbp+2AD0h+var_22C0]; struct tagRASDIALPARAMSW *
0x18008d2fc  xor     r9d, r9d; DWORD
0x18008d2ff  mov     [rsp+2BD0h+var_2BB0], rdi; LPVOID
0x18008d304  lea     rdx, [rbp+2AD0h+var_28FC]; LPCWSTR
0x18008d30b  lea     rcx, [rbp+2AD0h+var_2B50]; struct tagRASDIALEXTENSIONS *
0x18008d30f  call    cs:__imp_RasDialW
0x18008d315  mov     edi, eax
0x18008d317  lea     rax, [rbp+2AD0h+var_22C0]
0x18008d31e  mov     byte ptr [rax], 0
0x18008d321  inc     rax
0x18008d324  sub     rsi, 1
0x18008d328  jnz     short loc_18008D31E
0x18008d32a  cmp     edi, 80004001h
0x18008d330  jnz     loc_18008D40C
0x18008d336  xorps   xmm0, xmm0
0x18008d339  mov     [rsp+2BD0h+var_2BA0], esi
0x18008d33d  movups  [rsp+2BD0h+var_2B90], xmm0
0x18008d342  xor     edx, edx; Val
0x18008d344  mov     dword ptr [rsp+2BD0h+var_2B90], 30h ; '0'
0x18008d34c  mov     r8d, 1A40h; Size
0x18008d352  lea     rcx, [rbp+2AD0h+var_1A70.dwfOptions]; void *
0x18008d359  movups  [rsp+2BD0h+var_2B80], xmm0
0x18008d35e  movups  [rsp+2BD0h+var_2B70], xmm0
0x18008d363  call    memset_0
0x18008d368  mov     eax, 1A44h
0x18008d36d  lea     r9, [rsp+2BD0h+var_2B9C]; LPDWORD
0x18008d372  mov     [rsp+2BD0h+var_2B9C], eax
0x18008d376  lea     r8, [rbp+2AD0h+var_1A70]; struct tagRASENTRYW *
0x18008d37d  mov     [rbp+2AD0h+var_1A70.dwSize], eax
0x18008d383  lea     rdx, [rbp+2AD0h+var_2B04]; LPCWSTR
0x18008d387  lea     rax, [rsp+2BD0h+var_2BA0]
0x18008d38c  mov     [rsp+2BD0h+var_2BA8], rax; LPDWORD
0x18008d391  lea     rcx, [rbp+2AD0h+var_28FC]; LPCWSTR
0x18008d398  mov     [rsp+2BD0h+var_2BB0], rsi; LPBYTE
0x18008d39d  call    cs:__imp_RasGetEntryPropertiesW
0x18008d3a3  mov     edi, eax
0x18008d3a5  test    eax, eax
0x18008d3a7  jnz     short loc_18008D40C
0x18008d3a9  cmp     [rbp+2AD0h+var_1A70.dwType], 4
0x18008d3b0  lea     edi, [rsi+32h]
0x18008d3b3  jnz     short loc_18008D40C
0x18008d3b5  or      dword ptr [rsp+2BD0h+var_2B90+0Ch], 2
0x18008d3ba  lea     rcx, aRasdlgDll; "RASDLG.DLL"
0x18008d3c1  call    cs:__imp_LoadLibraryW
0x18008d3c7  mov     rsi, rax
0x18008d3ca  test    rax, rax
0x18008d3cd  jz      short loc_18008D40C
0x18008d3cf  lea     rdx, aRasdialdlgw; "RasDialDlgW"
0x18008d3d6  mov     rcx, rax; hModule
0x18008d3d9  call    cs:__imp_GetProcAddress
0x18008d3df  test    rax, rax
0x18008d3e2  jz      short loc_18008D403
0x18008d3e4  lea     r9, [rsp+2BD0h+var_2B90]
0x18008d3e9  xor     r8d, r8d
0x18008d3ec  lea     rdx, [rbp+2AD0h+var_2B04]
0x18008d3f0  lea     rcx, [rbp+2AD0h+var_28FC]
0x18008d3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d3fc  xor     ecx, ecx
0x18008d3fe  test    eax, eax
0x18008d400  cmovnz  edi, ecx
0x18008d403  mov     rcx, rsi; hLibModule
0x18008d406  call    cs:__imp_FreeLibrary
0x18008d40c  mov     [r14+90h], edi
0x18008d413  test    edi, edi
0x18008d415  jz      short loc_18008D433
0x18008d417  mov     rcx, [rsp+2BD0h+var_2B98]; HRASCONN
0x18008d41c  mov     ebx, 80004005h
0x18008d421  test    rcx, rcx
0x18008d424  jz      short loc_18008D43E
0x18008d426  call    cs:__imp_RasHangUpW
0x18008d42c  jmp     short loc_18008D433
0x18008d42e  mov     ebx, 80004005h
0x18008d433  test    ebx, ebx
0x18008d435  jns     short loc_18008D44A
0x18008d437  jmp     short loc_18008D43E
0x18008d439  mov     ebx, 80004005h
0x18008d43e  lea     rcx, a704; "704"
0x18008d445  call    ?SetUPnPError@@YAJPEAG@Z; SetUPnPError(ushort *)
0x18008d44a  lea     rcx, [rsp+2BD0h+var_2B60]; this
0x18008d44f  call    ??1CSwitchSecurityContext@@QEAA@XZ; CSwitchSecurityContext::~CSwitchSecurityContext(void)
0x18008d454  jmp     short loc_18008D462
0x18008d456  lea     rcx, a800; "800"
0x18008d45d  call    ?SetUPnPError@@YAJPEAG@Z; SetUPnPError(ushort *)
0x18008d462  mov     eax, ebx
0x18008d464  mov     rcx, [rbp+2AD0h+var_20]
0x18008d46b  xor     rcx, rsp; StackCookie
0x18008d46e  call    __security_check_cookie
0x18008d473  lea     r11, [rsp+2BD0h+var_10]
0x18008d47b  mov     rbx, [r11+28h]
0x18008d47f  mov     rsi, [r11+30h]
0x18008d483  mov     rsp, r11
0x18008d486  pop     r14
0x18008d488  pop     rdi
0x18008d489  pop     rbp
0x18008d48a  retn
```
