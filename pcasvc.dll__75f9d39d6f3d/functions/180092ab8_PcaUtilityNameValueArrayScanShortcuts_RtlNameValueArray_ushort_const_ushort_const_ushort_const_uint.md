# PcaUtilityNameValueArrayScanShortcuts(RtlNameValueArray &,ushort const *,ushort const *,ushort const *,uint)

- ea: `0x180092ab8`
- end: `0x180092ee2`
- name: `?PcaUtilityNameValueArrayScanShortcuts@@YAKAEAVRtlNameValueArray@@PEBG11I@Z`
- size: `1066`
- prototype: `unsigned int __fastcall(struct RtlNameValueArray *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a7a60`
- `0x1800b15f0`

## callees

- `0x180012920`
- `0x18007a710`
- `0x18007a780`
- `0x18007a9cf`
- `0x180092ab8`
- `0x1800933e4`
- `0x1800ee188`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092e57`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180092cbe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180092cbe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180092ce0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180092df7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180092ce0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180092df7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180092c32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180092c32`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180092eb7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180092eb7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180092bd6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180092bd6`

## string_xrefs

- `0x180092be4`: `Failed to initialize COM while trying to parse shortcuts [%x]`
- `0x180092d75`: `Failed to get program data directory [%d]`
- `0x180092c3e`: `Failed to create link object [%d]`
- `0x180092e71`: `Failed to read user environment [%d]`
- `0x180092d5e`: `Failed to append full program data directory path [%d]`
- `0x180092e5d`: `Failed to append full program data directory path [%d]`

## pseudocode

```c
__int64 __fastcall PcaUtilityNameValueArrayScanShortcuts(
        struct RtlNameValueArray *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v9; // rbx
  HRESULT Instance; // ebx
  int v11; // esi
  const char *v12; // r9
  int v13; // r8d
  unsigned int i; // esi
  int v15; // r8d
  const char *v16; // r9
  DWORD v17; // eax
  DWORD LastError; // eax
  unsigned int j; // esi
  unsigned int v20; // edx
  DWORD v21; // eax
  struct IShellLinkW *ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IPersistFile *v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v25; // [rsp+58h] [rbp-A8h]
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v25 = a4;
  ppv = 0;
  v24 = 0;
  v9 = ThreadLocalStoragePointer[tls_index];
  if ( dword_18015C65C > *(_DWORD *)(v9 + 8) )
  {
    Init_thread_header(&dword_18015C65C);
    if ( dword_18015C65C == -1 )
    {
      qword_180155A78[0] = (__int64)L"Microsoft\\Windows\\Start Menu\\Programs";
      qword_180155A80 = (__int64)L"%Public%";
      qword_180155A88 = (__int64)L"Desktop";
      Init_thread_footer(&dword_18015C65C);
    }
  }
  if ( dword_18015C648 > *(_DWORD *)(v9 + 8) )
  {
    Init_thread_header(&dword_18015C648);
    if ( dword_18015C648 == -1 )
    {
      qword_180155A58[0] = (__int64)L"Microsoft\\Windows\\Start Menu\\Programs";
      qword_180155A60 = (__int64)L"USERPROFILE";
      qword_180155A68 = (__int64)L"Desktop";
      Init_thread_footer(&dword_18015C648);
    }
  }
  ppv = 0;
  v24 = 0;
  Instance = CoInitializeEx(0, 2u);
  if ( Instance < 0 )
  {
    v11 = 0;
    v12 = "Failed to initialize COM while trying to parse shortcuts [%x]";
    v13 = 1406;
LABEL_9:
    AslLogCallPrintf(1, (unsigned int)"PcaUtilityNameValueArrayScanShortcuts", v13, (_DWORD)v12);
    Instance = (unsigned __int16)Instance;
    goto LABEL_42;
  }
  v11 = 1;
  Instance = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    v12 = "Failed to create link object [%d]";
    v13 = 1419;
    goto LABEL_9;
  }
  Instance = ((__int64 (__fastcall *)(struct IShellLinkW *, GUID *, struct IPersistFile **))ppv->lpVtbl->QueryInterface)(
               ppv,
               &IID_IPersistFile,
               &v24);
  if ( Instance < 0 )
  {
    v12 = "Failed to get persist file interface [%d]";
    v13 = 1426;
    goto LABEL_9;
  }
  for ( i = 0; i < 2; ++i )
  {
    memset_0(Dst, 0, 0x208u);
    if ( !ExpandEnvironmentStringsW((&off_180155A70)[2 * i], Dst, 0x104u) )
    {
      LastError = GetLastError();
      v16 = "Failed to get program data directory [%d]";
      v15 = 1440;
      Instance = LastError;
      goto LABEL_24;
    }
    if ( !PathAppendW(Dst, (LPCWSTR)qword_180155A78[2 * i]) )
    {
      v17 = GetLastError();
      v16 = "Failed to append full program data directory path [%d]";
      v15 = 1447;
      Instance = v17;
LABEL_24:
      AslLogCallPrintf(1, (unsigned int)"PcaUtilityNameValueArrayScanShortcuts", v15, (_DWORD)v16);
      goto LABEL_41;
    }
    Instance = PcapFolderScan(a1, ppv, v24, a3, a4, Dst, 0xAu);
    if ( Instance )
    {
      v15 = 1459;
LABEL_23:
      v16 = "Failed to scan folder [%d]";
      goto LABEL_24;
    }
    if ( a3 && *((_QWORD *)a1 + 2) )
      goto LABEL_40;
  }
  if ( a2 && *a2 )
  {
    for ( j = 0; j < 2; ++j )
    {
      memset_0(Dst, 0, 0x208u);
      Instance = PcaUtilityGetVolatileEnvForUser(Dst, v20, a2, (&off_180155A50)[2 * j]);
      if ( Instance )
      {
        v16 = "Failed to read user environment [%d]";
        v15 = 1487;
        goto LABEL_24;
      }
      if ( !PathAppendW(Dst, (LPCWSTR)qword_180155A58[2 * j]) )
      {
        v21 = GetLastError();
        v16 = "Failed to append full program data directory path [%d]";
        v15 = 1494;
        Instance = v21;
        goto LABEL_24;
      }
      Instance = PcapFolderScan(a1, ppv, v24, a3, v25, Dst, 0xAu);
      if ( Instance )
      {
        v15 = 1506;
        goto LABEL_23;
      }
      if ( a3 && *((_QWORD *)a1 + 2) )
        break;
    }
  }
LABEL_40:
  Instance = 0;
LABEL_41:
  v11 = 1;
LABEL_42:
  if ( ppv )
    ((void (__fastcall *)(struct IShellLinkW *))ppv->lpVtbl->Release)(ppv);
  if ( v24 )
    ((void (__fastcall *)(struct IPersistFile *))v24->lpVtbl->Release)(v24);
  if ( v11 )
    CoUninitialize();
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180092ab8  push    rbp
0x180092aba  push    rbx
0x180092abb  push    rsi
0x180092abc  push    rdi
0x180092abd  push    r12
0x180092abf  push    r13
0x180092ac1  push    r14
0x180092ac3  push    r15
0x180092ac5  lea     rbp, [rsp-188h]
0x180092acd  sub     rsp, 288h
0x180092ad4  mov     rax, cs:__security_cookie
0x180092adb  xor     rax, rsp
0x180092ade  mov     [rbp+1C0h+var_50], rax
0x180092ae5  mov     rax, gs:58h
0x180092aee  lea     rsi, aMicrosoftWindo_0; "Microsoft\\Windows\\Start Menu\\Program"...
0x180092af5  xor     edi, edi
0x180092af7  mov     [rsp+2C0h+var_268], r9
0x180092afc  mov     r14, r9
0x180092aff  mov     [rsp+2C0h+var_278], rdi
0x180092b04  mov     r9d, cs:_tls_index
0x180092b0b  mov     r15, rcx
0x180092b0e  mov     ecx, 8
0x180092b13  mov     r12, r8
0x180092b16  mov     r13, rdx
0x180092b19  mov     [rsp+2C0h+var_270], rdi
0x180092b1e  mov     rbx, [rax+r9*8]
0x180092b22  mov     eax, [rbx+rcx]
0x180092b25  cmp     cs:dword_18015C65C, eax
0x180092b2b  jle     short loc_180092B76
0x180092b2d  lea     rcx, dword_18015C65C
0x180092b34  call    _Init_thread_header
0x180092b39  cmp     cs:dword_18015C65C, 0FFFFFFFFh
0x180092b40  jnz     short loc_180092B71
0x180092b42  lea     rax, aPublic; "%Public%"
0x180092b49  mov     cs:qword_180155A78, rsi
0x180092b50  mov     cs:qword_180155A80, rax
0x180092b57  lea     rcx, dword_18015C65C
0x180092b5e  lea     rax, aDesktop; "Desktop"
0x180092b65  mov     cs:qword_180155A88, rax
0x180092b6c  call    _Init_thread_footer
0x180092b71  mov     ecx, 8
0x180092b76  mov     eax, [rbx+rcx]
0x180092b79  cmp     cs:dword_18015C648, eax
0x180092b7f  jle     short loc_180092BC5
0x180092b81  lea     rcx, dword_18015C648
0x180092b88  call    _Init_thread_header
0x180092b8d  cmp     cs:dword_18015C648, 0FFFFFFFFh
0x180092b94  jnz     short loc_180092BC5
0x180092b96  lea     rax, aUserprofile; "USERPROFILE"
0x180092b9d  mov     cs:qword_180155A58, rsi
0x180092ba4  mov     cs:qword_180155A60, rax
0x180092bab  lea     rcx, dword_18015C648
0x180092bb2  lea     rax, aDesktop; "Desktop"
0x180092bb9  mov     cs:qword_180155A68, rax
0x180092bc0  call    _Init_thread_footer
0x180092bc5  mov     edx, 2; dwCoInit
0x180092bca  mov     [rsp+2C0h+var_278], rdi
0x180092bcf  xor     ecx, ecx; pvReserved
0x180092bd1  mov     [rsp+2C0h+var_270], rdi
0x180092bd6  call    cs:__imp_CoInitializeEx
0x180092bdc  mov     ebx, eax
0x180092bde  test    eax, eax
0x180092be0  jns     short loc_180092C0E
0x180092be2  mov     esi, edi
0x180092be4  lea     r9, aFailedToInitia_6; "Failed to initialize COM while trying t"...
0x180092beb  mov     r8d, 57Eh
0x180092bf1  mov     ecx, 1
0x180092bf6  lea     rdx, aPcautilityname; "PcaUtilityNameValueArrayScanShortcuts"
0x180092bfd  mov     dword ptr [rsp+2C0h+ppv], ebx
0x180092c01  call    AslLogCallPrintf
0x180092c06  movzx   ebx, bx
0x180092c09  jmp     loc_180092E87
0x180092c0e  mov     edi, 1
0x180092c13  lea     rax, [rsp+2C0h+var_278]
0x180092c18  mov     r8d, edi; dwClsContext
0x180092c1b  mov     [rsp+2C0h+ppv], rax; ppv
0x180092c20  lea     r9, IID_IShellLinkW; riid
0x180092c27  xor     edx, edx; pUnkOuter
0x180092c29  lea     rcx, CLSID_ShellLink; rclsid
0x180092c30  mov     esi, edi
0x180092c32  call    cs:__imp_CoCreateInstance
0x180092c38  mov     ebx, eax
0x180092c3a  test    eax, eax
0x180092c3c  jns     short loc_180092C4F
0x180092c3e  lea     r9, aFailedToCreate_32; "Failed to create link object [%d]"
0x180092c45  mov     r8d, 58Bh
0x180092c4b  mov     ecx, edi
0x180092c4d  jmp     short loc_180092BF6
0x180092c4f  mov     rcx, [rsp+2C0h+var_278]
0x180092c54  lea     r8, [rsp+2C0h+var_270]
0x180092c59  lea     rdx, IID_IPersistFile
0x180092c60  mov     rax, [rcx]
0x180092c63  mov     rax, [rax]
0x180092c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c6b  xor     ecx, ecx
0x180092c6d  mov     ebx, eax
0x180092c6f  test    eax, eax
0x180092c71  jns     short loc_180092C82
0x180092c73  lea     r9, aFailedToGetPer_2; "Failed to get persist file interface [%"...
0x180092c7a  mov     r8d, 592h
0x180092c80  jmp     short loc_180092C4B
0x180092c82  mov     esi, ecx
0x180092c84  cmp     esi, 2
0x180092c87  jnb     loc_180092D86
0x180092c8d  xor     edx, edx; Val
0x180092c8f  lea     rcx, [rsp+2C0h+Dst]; void *
0x180092c94  mov     r8d, 208h; Size
0x180092c9a  call    memset_0
0x180092c9f  mov     ebx, esi
0x180092ca1  lea     rcx, __ImageBase
0x180092ca8  add     rbx, rbx
0x180092cab  lea     rdx, [rsp+2C0h+Dst]; lpDst
0x180092cb0  mov     r8d, 104h; nSize
0x180092cb6  mov     rcx, rva off_180155A70[rcx+rbx*8]; lpSrc
0x180092cbe  call    cs:__imp_ExpandEnvironmentStringsW
0x180092cc4  test    eax, eax
0x180092cc6  jz      loc_180092D6F
0x180092ccc  lea     rax, __ImageBase
0x180092cd3  mov     rdx, rva qword_180155A78[rax+rbx*8]; pszMore
0x180092cdb  lea     rcx, [rsp+2C0h+Dst]; pszPath
0x180092ce0  call    cs:__imp_PathAppendW
0x180092ce6  test    eax, eax
0x180092ce8  jz      short loc_180092D58
0x180092cea  mov     r8, [rsp+2C0h+var_270]; struct IPersistFile *
0x180092cef  lea     rax, [rsp+2C0h+Dst]
0x180092cf4  mov     rdx, [rsp+2C0h+var_278]; struct IShellLinkW *
0x180092cf9  mov     r9, r12; unsigned __int16 *
0x180092cfc  mov     [rsp+2C0h+var_290], 0Ah; unsigned int
0x180092d04  mov     rcx, r15; struct RtlNameValueArray *
0x180092d07  mov     [rsp+2C0h+Source], rax; Source
0x180092d0c  mov     [rsp+2C0h+ppv], r14; unsigned __int16 *
0x180092d11  call    ?PcapFolderScan@@YAKAEAVRtlNameValueArray@@PEAUIShellLinkW@@PEAUIPersistFile@@PEBG33I@Z; PcapFolderScan(RtlNameValueArray &,IShellLinkW *,IPersistFile *,ushort const *,ushort const *,ushort const *,uint)
0x180092d16  xor     ecx, ecx
0x180092d18  mov     ebx, eax
0x180092d1a  test    eax, eax
0x180092d1c  jnz     short loc_180092D34
0x180092d1e  test    r12, r12
0x180092d21  jz      short loc_180092D2D
0x180092d23  cmp     [r15+10h], rcx
0x180092d27  jnz     loc_180092E83
0x180092d2d  add     esi, edi
0x180092d2f  jmp     loc_180092C84
0x180092d34  mov     r8d, 5B3h
0x180092d3a  lea     r9, aFailedToScanFo; "Failed to scan folder [%d]"
0x180092d41  lea     rdx, aPcautilityname; "PcaUtilityNameValueArrayScanShortcuts"
0x180092d48  mov     dword ptr [rsp+2C0h+ppv], eax
0x180092d4c  mov     ecx, edi
0x180092d4e  call    AslLogCallPrintf
0x180092d53  jmp     loc_180092E85
0x180092d58  call    cs:__imp_GetLastError
0x180092d5e  lea     r9, aFailedToAppend_2; "Failed to append full program data dire"...
0x180092d65  mov     r8d, 5A7h
0x180092d6b  mov     ebx, eax
0x180092d6d  jmp     short loc_180092D41
0x180092d6f  call    cs:__imp_GetLastError
0x180092d75  lea     r9, aFailedToGetPro_1; "Failed to get program data directory [%"...
0x180092d7c  mov     r8d, 5A0h
0x180092d82  mov     ebx, eax
0x180092d84  jmp     short loc_180092D41
0x180092d86  test    r13, r13
0x180092d89  jz      loc_180092E83
0x180092d8f  cmp     [r13+0], cx
0x180092d94  jz      loc_180092E83
0x180092d9a  mov     esi, ecx
0x180092d9c  cmp     esi, 2
0x180092d9f  jnb     loc_180092E83
0x180092da5  xor     edx, edx; Val
0x180092da7  lea     rcx, [rsp+2C0h+Dst]; void *
0x180092dac  mov     r8d, 208h; Size
0x180092db2  call    memset_0
0x180092db7  lea     rax, __ImageBase
0x180092dbe  mov     r14d, esi
0x180092dc1  add     r14, r14
0x180092dc4  lea     rcx, [rsp+2C0h+Dst]; pvData
0x180092dc9  mov     r8, r13; unsigned __int16 *
0x180092dcc  mov     r9, rva off_180155A50[rax+r14*8]; unsigned __int16 *
0x180092dd4  call    ?PcaUtilityGetVolatileEnvForUser@@YAKPEAGIPEBG1@Z; PcaUtilityGetVolatileEnvForUser(ushort *,uint,ushort const *,ushort const *)
0x180092dd9  mov     ebx, eax
0x180092ddb  test    eax, eax
0x180092ddd  jnz     loc_180092E71
0x180092de3  lea     rax, __ImageBase
0x180092dea  mov     rdx, rva qword_180155A58[rax+r14*8]; pszMore
0x180092df2  lea     rcx, [rsp+2C0h+Dst]; pszPath
0x180092df7  call    cs:__imp_PathAppendW
0x180092dfd  test    eax, eax
0x180092dff  jz      short loc_180092E57
0x180092e01  mov     r8, [rsp+2C0h+var_270]; struct IPersistFile *
0x180092e06  lea     rax, [rsp+2C0h+Dst]
0x180092e0b  mov     rdx, [rsp+2C0h+var_278]; struct IShellLinkW *
0x180092e10  mov     r9, r12; unsigned __int16 *
0x180092e13  mov     [rsp+2C0h+var_290], 0Ah; unsigned int
0x180092e1b  mov     rcx, r15; struct RtlNameValueArray *
0x180092e1e  mov     [rsp+2C0h+Source], rax; Source
0x180092e23  mov     rax, [rsp+2C0h+var_268]
0x180092e28  mov     [rsp+2C0h+ppv], rax; unsigned __int16 *
0x180092e2d  call    ?PcapFolderScan@@YAKAEAVRtlNameValueArray@@PEAUIShellLinkW@@PEAUIPersistFile@@PEBG33I@Z; PcapFolderScan(RtlNameValueArray &,IShellLinkW *,IPersistFile *,ushort const *,ushort const *,ushort const *,uint)
0x180092e32  xor     ecx, ecx
0x180092e34  mov     ebx, eax
0x180092e36  test    eax, eax
0x180092e38  jnz     short loc_180092E4C
0x180092e3a  test    r12, r12
0x180092e3d  jz      short loc_180092E45
0x180092e3f  cmp     [r15+10h], rcx
0x180092e43  jnz     short loc_180092E83
0x180092e45  add     esi, edi
0x180092e47  jmp     loc_180092D9C
0x180092e4c  mov     r8d, 5E2h
0x180092e52  jmp     loc_180092D3A
0x180092e57  call    cs:__imp_GetLastError
0x180092e5d  lea     r9, aFailedToAppend_2; "Failed to append full program data dire"...
0x180092e64  mov     r8d, 5D6h
0x180092e6a  mov     ebx, eax
0x180092e6c  jmp     loc_180092D41
0x180092e71  lea     r9, aFailedToReadUs; "Failed to read user environment [%d]"
0x180092e78  mov     r8d, 5CFh
0x180092e7e  jmp     loc_180092D41
0x180092e83  mov     ebx, ecx
0x180092e85  mov     esi, edi
0x180092e87  mov     rcx, [rsp+2C0h+var_278]
0x180092e8c  test    rcx, rcx
0x180092e8f  jz      short loc_180092E9D
0x180092e91  mov     rax, [rcx]
0x180092e94  mov     rax, [rax+10h]
0x180092e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092e9d  mov     rcx, [rsp+2C0h+var_270]
0x180092ea2  test    rcx, rcx
0x180092ea5  jz      short loc_180092EB3
0x180092ea7  mov     rax, [rcx]
0x180092eaa  mov     rax, [rax+10h]
0x180092eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092eb3  test    esi, esi
0x180092eb5  jz      short loc_180092EBD
0x180092eb7  call    cs:__imp_CoUninitialize
0x180092ebd  mov     eax, ebx
0x180092ebf  mov     rcx, [rbp+1C0h+var_50]
0x180092ec6  xor     rcx, rsp; StackCookie
0x180092ec9  call    __security_check_cookie
0x180092ece  add     rsp, 288h
0x180092ed5  pop     r15
0x180092ed7  pop     r14
0x180092ed9  pop     r13
0x180092edb  pop     r12
0x180092edd  pop     rdi
0x180092ede  pop     rsi
0x180092edf  pop     rbx
0x180092ee0  pop     rbp
0x180092ee1  retn
```
