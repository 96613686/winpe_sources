# CWANPPPConnectionService::RequestConnection(void)

- ea: `0x180094240`
- end: `0x18009458c`
- name: `?RequestConnection@CWANPPPConnectionService@@UEAAJXZ`
- size: `844`
- prototype: `__int64 __fastcall(CWANPPPConnectionService *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180037994`
- `0x180051f30`
- `0x180052bf4`
- `0x18008ff28`
- `0x180092408`
- `0x180092500`
- `0x1800926d8`
- `0x180094240`
- `0x180095ab0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800944c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800944c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800944fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800944fa`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800944a9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800944a9`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18009447f`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x18009447f`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasDialW` at `0x1800943eb`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasDialW` at `0x1800943eb`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetCredentialsW` at `0x1800942fe`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetCredentialsW` at `0x1800942fe`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedConnection` at `0x1800942af`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedConnection` at `0x1800942af`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x180094520`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x180094520`

## string_xrefs

- `0x1800944a2`: `RASDLG.DLL`

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
0x180094240  mov     [rsp-8+arg_8], rbx
0x180094245  mov     [rsp-8+arg_10], rsi
0x18009424a  push    rbp
0x18009424b  push    rdi
0x18009424c  push    r14
0x18009424e  lea     rbp, [rsp-2AC0h]
0x180094256  mov     eax, 2BC0h
0x18009425b  call    _alloca_probe
0x180094260  sub     rsp, rax
0x180094263  mov     rax, cs:__security_cookie
0x18009426a  xor     rax, rsp
0x18009426d  mov     [rbp+2AD0h+var_20], rax
0x180094274  mov     r14, rcx
0x180094277  mov     dword ptr [rcx+90h], 0
0x180094281  call    ?ControlEnabled@CWANConnectionBase@@IEAAJXZ; CWANConnectionBase::ControlEnabled(void)
0x180094286  mov     ebx, eax
0x180094288  test    eax, eax
0x18009428a  js      loc_180094556
0x180094290  xor     edx, edx; Val
0x180094292  lea     rcx, [rbp+2AD0h+var_2B10]; void *
0x180094296  mov     r8d, 420h; Size
0x18009429c  call    memset_0
0x1800942a1  lea     rcx, [rsp+2BD0h+var_2B60]; this
0x1800942a6  call    ??0CSwitchSecurityContext@@QEAA@XZ; CSwitchSecurityContext::CSwitchSecurityContext(void)
0x1800942ab  lea     rcx, [rbp+2AD0h+var_2B10]
0x1800942af  call    cs:__imp_RasQuerySharedConnection
0x1800942b6  nop     dword ptr [rax+rax+00h]
0x1800942bb  test    eax, eax
0x1800942bd  jnz     loc_180094539
0x1800942c3  xor     edx, edx; Val
0x1800942c5  lea     rcx, [rbp+2AD0h+var_26F0.szUserName]; void *
0x1800942cc  mov     r8d, 424h; Size
0x1800942d2  call    memset_0
0x1800942d7  mov     edi, 42Ch
0x1800942dc  mov     [rbp+2AD0h+var_26F0.dwMask], 0Fh
0x1800942e6  lea     r8, [rbp+2AD0h+var_26F0]; struct tagRASCREDENTIALSW *
0x1800942ed  mov     [rbp+2AD0h+var_26F0.dwSize], edi
0x1800942f3  lea     rdx, [rbp+2AD0h+var_2B04]; LPCWSTR
0x1800942f7  lea     rcx, [rbp+2AD0h+var_28FC]; LPCWSTR
0x1800942fe  call    cs:__imp_RasGetCredentialsW
0x180094305  nop     dword ptr [rax+rax+00h]
0x18009430a  test    eax, eax
0x18009430c  jnz     loc_18009452E
0x180094312  xorps   xmm0, xmm0
0x180094315  lea     rcx, [rbp+2AD0h+var_22C0.szEntryName]; void *
0x18009431c  movups  xmmword ptr [rbp+2AD0h+var_2B50.dwSize], xmm0
0x180094320  xor     edx, edx; Val
0x180094322  mov     r8d, 844h; Size
0x180094328  movups  xmmword ptr [rbp+2AD0h+var_2B50.RasEapInfo.dwSizeofEapInfo], xmm0
0x18009432c  mov     [rbp+2AD0h+var_2B50.dwSize], 3Ch ; '<'
0x180094333  movups  xmmword ptr [rbp+2AD0h+var_2B50.fSkipPppAuth], xmm0
0x180094337  mov     [rbp+2AD0h+var_2B50.dwfOptions], 200h
0x18009433e  movups  xmmword ptr [rbp+2AD0h+var_2B50.reserved], xmm0
0x180094342  call    memset_0
0x180094347  mov     r11d, 101h
0x18009434d  lea     r8, [rbp+2AD0h+var_2B04]; unsigned __int16 *
0x180094351  mov     esi, 848h
0x180094356  lea     rcx, [rbp+2AD0h+var_22C0.szEntryName]; unsigned __int16 *
0x18009435d  mov     edx, r11d; unsigned __int64
0x180094360  mov     [rbp+2AD0h+var_22C0.dwSize], esi
0x180094366  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009436b  lea     r8, [rbp+2AD0h+var_26F0.szUserName]; unsigned __int16 *
0x180094372  mov     edx, r11d; unsigned __int64
0x180094375  lea     rcx, [rbp+2AD0h+var_22C0.szUserName]; unsigned __int16 *
0x18009437c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180094381  lea     r8, [rbp+2AD0h+var_26F0.szDomain]; unsigned __int16 *
0x180094388  mov     edx, 10h; unsigned __int64
0x18009438d  lea     rcx, [rbp+2AD0h+var_22C0.szDomain]; unsigned __int16 *
0x180094394  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180094399  lea     r8, [rbp+2AD0h+var_26F0.szPassword]; unsigned __int16 *
0x1800943a0  mov     edx, r11d; unsigned __int64
0x1800943a3  lea     rcx, [rbp+2AD0h+var_22C0.szPassword]; unsigned __int16 *
0x1800943aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800943af  lea     rax, [rbp+2AD0h+var_26F0]
0x1800943b6  mov     byte ptr [rax], 0
0x1800943b9  inc     rax
0x1800943bc  sub     rdi, 1
0x1800943c0  jnz     short loc_1800943B6
0x1800943c2  lea     rax, [rsp+2BD0h+var_2B98]
0x1800943c7  mov     [rsp+2BD0h+var_2B98], rdi
0x1800943cc  mov     [rsp+2BD0h+var_2BA8], rax; HRASCONN *
0x1800943d1  lea     r8, [rbp+2AD0h+var_22C0]; struct tagRASDIALPARAMSW *
0x1800943d8  xor     r9d, r9d; DWORD
0x1800943db  mov     [rsp+2BD0h+var_2BB0], rdi; LPVOID
0x1800943e0  lea     rdx, [rbp+2AD0h+var_28FC]; LPCWSTR
0x1800943e7  lea     rcx, [rbp+2AD0h+var_2B50]; struct tagRASDIALEXTENSIONS *
0x1800943eb  call    cs:__imp_RasDialW
0x1800943f2  nop     dword ptr [rax+rax+00h]
0x1800943f7  mov     edi, eax
0x1800943f9  lea     rax, [rbp+2AD0h+var_22C0]
0x180094400  mov     byte ptr [rax], 0
0x180094403  inc     rax
0x180094406  sub     rsi, 1
0x18009440a  jnz     short loc_180094400
0x18009440c  cmp     edi, 80004001h
0x180094412  jnz     loc_180094506
0x180094418  xorps   xmm0, xmm0
0x18009441b  mov     [rsp+2BD0h+var_2BA0], esi
0x18009441f  movups  [rsp+2BD0h+var_2B90], xmm0
0x180094424  xor     edx, edx; Val
0x180094426  mov     dword ptr [rsp+2BD0h+var_2B90], 30h ; '0'
0x18009442e  mov     r8d, 1A40h; Size
0x180094434  lea     rcx, [rbp+2AD0h+var_1A70.dwfOptions]; void *
0x18009443b  movups  [rsp+2BD0h+var_2B80], xmm0
0x180094440  movups  [rsp+2BD0h+var_2B70], xmm0
0x180094445  call    memset_0
0x18009444a  mov     eax, 1A44h
0x18009444f  lea     r9, [rsp+2BD0h+var_2B9C]; LPDWORD
0x180094454  mov     [rsp+2BD0h+var_2B9C], eax
0x180094458  lea     r8, [rbp+2AD0h+var_1A70]; struct tagRASENTRYW *
0x18009445f  mov     [rbp+2AD0h+var_1A70.dwSize], eax
0x180094465  lea     rdx, [rbp+2AD0h+var_2B04]; LPCWSTR
0x180094469  lea     rax, [rsp+2BD0h+var_2BA0]
0x18009446e  mov     [rsp+2BD0h+var_2BA8], rax; LPDWORD
0x180094473  lea     rcx, [rbp+2AD0h+var_28FC]; LPCWSTR
0x18009447a  mov     [rsp+2BD0h+var_2BB0], rsi; LPBYTE
0x18009447f  call    cs:__imp_RasGetEntryPropertiesW
0x180094486  nop     dword ptr [rax+rax+00h]
0x18009448b  mov     edi, eax
0x18009448d  test    eax, eax
0x18009448f  jnz     short loc_180094506
0x180094491  cmp     [rbp+2AD0h+var_1A70.dwType], 4
0x180094498  lea     edi, [rsi+32h]
0x18009449b  jnz     short loc_180094506
0x18009449d  or      dword ptr [rsp+2BD0h+var_2B90+0Ch], 2
0x1800944a2  lea     rcx, aRasdlgDll; "RASDLG.DLL"
0x1800944a9  call    cs:__imp_LoadLibraryW
0x1800944b0  nop     dword ptr [rax+rax+00h]
0x1800944b5  mov     rsi, rax
0x1800944b8  test    rax, rax
0x1800944bb  jz      short loc_180094506
0x1800944bd  lea     rdx, aRasdialdlgw; "RasDialDlgW"
0x1800944c4  mov     rcx, rax; hModule
0x1800944c7  call    cs:__imp_GetProcAddress
0x1800944ce  nop     dword ptr [rax+rax+00h]
0x1800944d3  test    rax, rax
0x1800944d6  jz      short loc_1800944F7
0x1800944d8  lea     r9, [rsp+2BD0h+var_2B90]
0x1800944dd  xor     r8d, r8d
0x1800944e0  lea     rdx, [rbp+2AD0h+var_2B04]
0x1800944e4  lea     rcx, [rbp+2AD0h+var_28FC]
0x1800944eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800944f0  xor     ecx, ecx
0x1800944f2  test    eax, eax
0x1800944f4  cmovnz  edi, ecx
0x1800944f7  mov     rcx, rsi; hLibModule
0x1800944fa  call    cs:__imp_FreeLibrary
0x180094501  nop     dword ptr [rax+rax+00h]
0x180094506  mov     [r14+90h], edi
0x18009450d  test    edi, edi
0x18009450f  jz      short loc_180094533
0x180094511  mov     rcx, [rsp+2BD0h+var_2B98]; HRASCONN
0x180094516  mov     ebx, 80004005h
0x18009451b  test    rcx, rcx
0x18009451e  jz      short loc_18009453E
0x180094520  call    cs:__imp_RasHangUpW
0x180094527  nop     dword ptr [rax+rax+00h]
0x18009452c  jmp     short loc_180094533
0x18009452e  mov     ebx, 80004005h
0x180094533  test    ebx, ebx
0x180094535  jns     short loc_18009454A
0x180094537  jmp     short loc_18009453E
0x180094539  mov     ebx, 80004005h
0x18009453e  lea     rcx, a704; "704"
0x180094545  call    ?SetUPnPError@@YAJPEAG@Z; SetUPnPError(ushort *)
0x18009454a  lea     rcx, [rsp+2BD0h+var_2B60]; this
0x18009454f  call    ??1CSwitchSecurityContext@@QEAA@XZ; CSwitchSecurityContext::~CSwitchSecurityContext(void)
0x180094554  jmp     short loc_180094562
0x180094556  lea     rcx, a800; "800"
0x18009455d  call    ?SetUPnPError@@YAJPEAG@Z; SetUPnPError(ushort *)
0x180094562  mov     eax, ebx
0x180094564  mov     rcx, [rbp+2AD0h+var_20]
0x18009456b  xor     rcx, rsp; StackCookie
0x18009456e  call    __security_check_cookie
0x180094573  lea     r11, [rsp+2BD0h+var_10]
0x18009457b  mov     rbx, [r11+28h]
0x18009457f  mov     rsi, [r11+30h]
0x180094583  mov     rsp, r11
0x180094586  pop     r14
0x180094588  pop     rdi
0x180094589  pop     rbp
0x18009458a  retn
```
