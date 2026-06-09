# DeleteCache(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)

- ea: `0x1801959c0`
- end: `0x180195ed5`
- name: `?DeleteCache@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z`
- size: `1301`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x18000c4bc`
- `0x180040908`
- `0x18006c9fc`
- `0x1801959c0`
- `0x18019a128`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180195d3b`
- `ADVAPI32!RegQueryValueExW` at `0x180195d3b`
- `ADVAPI32!RegCloseKey` at `0x180195e8f`
- `ADVAPI32!RegCloseKey` at `0x180195ea5`
- `ADVAPI32!RegCloseKey` at `0x180195e8f`
- `ADVAPI32!RegCloseKey` at `0x180195ea5`
- `KERNEL32!DeleteFileW` at `0x180195b2b`
- `KERNEL32!DeleteFileW` at `0x180195da4`
- `KERNEL32!DeleteFileW` at `0x180195b2b`
- `KERNEL32!DeleteFileW` at `0x180195da4`
- `KERNEL32!GetLastError` at `0x180195b3b`
- `KERNEL32!GetLastError` at `0x180195e0a`
- `KERNEL32!GetLastError` at `0x180195b3b`
- `KERNEL32!GetLastError` at `0x180195e0a`
- `KERNEL32!GlobalFree` at `0x180195a85`
- `KERNEL32!GlobalFree` at `0x180195e79`
- `KERNEL32!GlobalFree` at `0x180195a85`
- `KERNEL32!GlobalFree` at `0x180195e79`

## string_xrefs

- `0x180195c67`: `InstallProperties`
- `0x180195cc5`: `DeleteCache: RegOpenKeyEx returned %08x.`
- `0x180195d6c`: `DeleteCache: RegQueryValueEx returned %08x.`
- `0x180195dc7`: `DeleteCache: Deleted cached package %s.`
- `0x180195e01`: `DeleteCache: Deleted cached patch %s.`
- `0x180195b64`: `Failed to delete file %s with error %08x.`
- `0x180195e26`: `Failed to delete file %s with error %08x.`
- `0x180195bb8`: `DeleteCache: Deleted cached transform %s.`

## pseudocode

```c
__int64 __fastcall DeleteCache(HKEY a1, unsigned __int16 *a2, unsigned int a3, int a4)
{
  unsigned int v9; // edi
  HGLOBAL v10; // rcx
  DWORD v11; // r15d
  DWORD LastError; // eax
  DWORD v13; // r14d
  unsigned int v15; // eax
  int v16; // r15d
  const WCHAR *v17; // rdx
  unsigned int v18; // eax
  const unsigned __int16 *v19; // r9
  DWORD v20; // eax
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v24; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HGLOBAL hMem; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  _BYTE v30[528]; // [rsp+90h] [rbp-70h] BYREF
  char *v31; // [rsp+2A0h] [rbp+1A0h]
  int v32; // [rsp+2A8h] [rbp+1A8h]
  int v33; // [rsp+2ACh] [rbp+1ACh]
  char v34; // [rsp+2B0h] [rbp+1B0h] BYREF

  v24 = 0;
  hKey = 0;
  if ( !a2 )
    return 87;
  v28 = 260;
  if ( (unsigned int)(a4 - 2) > 1 )
  {
    cbData = 0;
    v31 = &v34;
    hMem = v30;
    v32 = 260;
    if ( a4 == 4 && (StringCbCatW(a2, a3, L"\\") < 0 || StringCbCatW(a2, a3, L"Transforms") < 0) )
    {
      v9 = 14;
LABEL_8:
      if ( v28 > 260 )
        GlobalFree(hMem);
      v28 = 260;
      hMem = v30;
      if ( v32 <= 260 )
        goto LABEL_55;
      v10 = v31;
      goto LABEL_54;
    }
    v9 = MsiRegOpen64bitKey(a1, a2, a3, 0x20019u, &v24);
    if ( (v9 & 0xFFFFFFFD) != 0 )
      goto LABEL_8;
    v29 = 260;
    v9 = 0;
    v33 = 260;
    v11 = 0;
    if ( (unsigned int)MsiRegEnumValueW(v24, 0, lpData, &cbData, (DWORD)&hMem) )
      goto LABEL_8;
    while ( 1 )
    {
      if ( cbData == 1 )
      {
        if ( DeleteFileW((LPCWSTR)hMem) )
          goto LABEL_23;
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError != 2 )
        {
          if ( !LastError )
          {
LABEL_23:
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"DeleteCache: Deleted cached transform %s.",
                (const unsigned __int16 *)hMem,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_25;
          }
          if ( g_dmDiagnosticMode )
            DebugString(
              5,
              0,
              0,
              L"Failed to delete file %s with error %08x.",
              (const unsigned __int16 *)hMem,
              (const unsigned __int16 *)LastError,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          if ( v9 )
            v13 = v9;
          v9 = v13;
        }
      }
LABEL_25:
      v29 = 260;
      ++v11;
      v33 = 260;
      if ( (unsigned int)MsiRegEnumValueW(v24, v11, lpDataa, &cbData, (DWORD)&hMem) )
        goto LABEL_8;
    }
  }
  Type = 0;
  hMem = v30;
  cbData = 520;
  if ( a4 == 2 && (StringCbCatW(a2, a3, L"\\") < 0 || StringCbCatW(a2, a3, L"InstallProperties") < 0) )
  {
    v9 = 14;
    goto LABEL_52;
  }
  v15 = MsiRegOpen64bitKey(a1, a2, a3, 0x20019u, &hKey);
  v9 = v15;
  if ( !v15 )
  {
    v16 = 0;
    while ( 1 )
    {
      v17 = L"LocalPackage";
      if ( v16 )
        v17 = L"ManagedLocalPackage";
      v18 = RegQueryValueExW(hKey, v17, 0, &Type, (LPBYTE)hMem, &cbData);
      v9 = v18;
      if ( v18 == 2 )
      {
        v9 = 0;
      }
      else
      {
        if ( v18 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"DeleteCache: RegQueryValueEx returned %08x.",
              (const unsigned __int16 *)v18,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_51;
        }
        if ( !DeleteFileW((LPCWSTR)hMem) )
        {
          v20 = GetLastError();
          v9 = v20;
          if ( g_dmDiagnosticMode )
            DebugString(
              5,
              0,
              0,
              L"Failed to delete file %s with error %08x.",
              (const unsigned __int16 *)hMem,
              (const unsigned __int16 *)v20,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_51;
        }
        if ( a4 != 2 )
        {
          if ( !g_dmDiagnosticMode )
            goto LABEL_51;
          v19 = L"DeleteCache: Deleted cached patch %s.";
          goto LABEL_46;
        }
        if ( g_dmDiagnosticMode )
        {
          v19 = L"DeleteCache: Deleted cached package %s.";
LABEL_46:
          DebugString(
            10,
            0,
            0,
            v19,
            (const unsigned __int16 *)hMem,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
LABEL_51:
      if ( ++v16 >= 2 )
        goto LABEL_52;
    }
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      L"DeleteCache: RegOpenKeyEx returned %08x.",
      (const unsigned __int16 *)v15,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
LABEL_52:
  if ( v28 > 260 )
  {
    v10 = hMem;
LABEL_54:
    GlobalFree(v10);
  }
LABEL_55:
  if ( v24 )
    RegCloseKey(v24);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x1801959c0  push    rbp
0x1801959c2  push    rbx
0x1801959c3  push    rsi
0x1801959c4  push    rdi
0x1801959c5  push    r12
0x1801959c7  push    r14
0x1801959c9  push    r15
0x1801959cb  lea     rbp, [rsp-3D0h]
0x1801959d3  sub     rsp, 4D0h
0x1801959da  mov     rax, cs:__security_cookie
0x1801959e1  xor     rax, rsp
0x1801959e4  mov     [rbp+400h+var_40], rax
0x1801959eb  xor     r12d, r12d
0x1801959ee  mov     r14d, r9d
0x1801959f1  mov     [rsp+500h+var_498], r12
0x1801959f6  mov     rdi, rdx
0x1801959f9  mov     [rsp+500h+hKey], r12
0x1801959fe  mov     r15, rcx
0x180195a01  test    rdx, rdx
0x180195a04  jnz     short loc_180195A0E
0x180195a06  lea     eax, [rdx+57h]
0x180195a09  jmp     loc_180195EB3
0x180195a0e  lea     eax, [r9-2]
0x180195a12  mov     ebx, 104h
0x180195a17  mov     [rbp+400h+var_478], ebx
0x180195a1a  cmp     eax, 1
0x180195a1d  jbe     loc_180195C34
0x180195a23  mov     [rsp+500h+cbData], r12d
0x180195a28  lea     rax, [rbp+400h+var_250]
0x180195a2f  mov     [rbp+400h+var_260], rax
0x180195a36  lea     rax, [rbp+400h+var_470]
0x180195a3a  mov     [rbp+400h+hMem], rax
0x180195a3e  mov     [rbp+400h+var_258], ebx
0x180195a44  cmp     r14d, 4
0x180195a48  jnz     short loc_180195AB4
0x180195a4a  mov     esi, r8d
0x180195a4d  mov     rcx, rdi; unsigned __int16 *
0x180195a50  mov     edx, esi; unsigned __int64
0x180195a52  lea     r8, asc_18027979C; "\\"
0x180195a59  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180195a5e  test    eax, eax
0x180195a60  js      short loc_180195A77
0x180195a62  lea     r8, aTransforms_1; "Transforms"
0x180195a69  mov     edx, esi; unsigned __int64
0x180195a6b  mov     rcx, rdi; unsigned __int16 *
0x180195a6e  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180195a73  test    eax, eax
0x180195a75  jns     short loc_180195AB4
0x180195a77  mov     edi, 0Eh
0x180195a7c  cmp     [rbp+400h+var_478], ebx
0x180195a7f  jle     short loc_180195A91
0x180195a81  mov     rcx, [rbp+400h+hMem]; hMem
0x180195a85  call    cs:__imp_GlobalFree
0x180195a8c  nop     dword ptr [rax+rax+00h]
0x180195a91  lea     rax, [rbp+400h+var_470]
0x180195a95  mov     [rbp+400h+var_478], ebx
0x180195a98  mov     [rbp+400h+hMem], rax
0x180195a9c  cmp     [rbp+400h+var_258], ebx
0x180195aa2  jle     loc_180195E85
0x180195aa8  mov     rcx, [rbp+400h+var_260]
0x180195aaf  jmp     loc_180195E79
0x180195ab4  lea     rax, [rsp+500h+var_498]
0x180195ab9  mov     r9d, 20019h; unsigned int
0x180195abf  mov     rdx, rdi; unsigned __int16 *
0x180195ac2  mov     [rsp+500h+lpData], rax; int
0x180195ac7  mov     rcx, r15; HKEY
0x180195aca  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180195acf  mov     edi, eax
0x180195ad1  test    eax, 0FFFFFFFDh
0x180195ad6  jnz     short loc_180195A7C
0x180195ad8  mov     rcx, [rsp+500h+var_498]; hKey
0x180195add  lea     rax, [rbp+400h+hMem]
0x180195ae1  mov     qword ptr [rsp+500h+cbMaxValueLen], rax; cbMaxValueLen
0x180195ae6  lea     r8, [rbp+400h+var_260]
0x180195aed  lea     rax, [rsp+500h+cbData]
0x180195af2  mov     [rbp+400h+var_474], ebx
0x180195af5  xor     edx, edx; dwIndex
0x180195af7  mov     [rsp+500h+lpcbData], rax; lpType
0x180195afc  mov     edi, r12d
0x180195aff  mov     [rbp+400h+var_254], ebx
0x180195b05  mov     r15d, r12d
0x180195b08  call    ?MsiRegEnumValueW@@YAJPEAUHKEY__@@KAEAV?$CAPITempBufferRef@G@@PEAK2212@Z; MsiRegEnumValueW(HKEY__ *,ulong,CAPITempBufferRef<ushort> &,ulong *,ulong *,ulong *,CAPITempBufferRef<ushort> &,ulong *)
0x180195b0d  test    eax, eax
0x180195b0f  jnz     loc_180195A7C
0x180195b15  lea     rsi, aNull; "(NULL)"
0x180195b1c  cmp     [rsp+500h+cbData], 1
0x180195b21  jnz     loc_180195BF4
0x180195b27  mov     rcx, [rbp+400h+hMem]; lpFileName
0x180195b2b  call    cs:__imp_DeleteFileW
0x180195b32  nop     dword ptr [rax+rax+00h]
0x180195b37  test    eax, eax
0x180195b39  jnz     short loc_180195BAB
0x180195b3b  call    cs:__imp_GetLastError
0x180195b42  nop     dword ptr [rax+rax+00h]
0x180195b47  mov     r14d, eax
0x180195b4a  cmp     eax, 2
0x180195b4d  jz      loc_180195BF4
0x180195b53  test    eax, eax
0x180195b55  jz      short loc_180195BAB
0x180195b57  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195b5e  jz      short loc_180195BA0
0x180195b60  mov     rax, [rbp+400h+hMem]
0x180195b64  lea     r9, aFailedToDelete_2; "Failed to delete file %s with error %08"...
0x180195b6b  mov     [rsp+500h+var_4A8], r12; void *
0x180195b70  xor     edx, edx; unsigned __int16
0x180195b72  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x180195b77  xor     r8d, r8d; int
0x180195b7a  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x180195b7f  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x180195b84  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x180195b89  lea     ecx, [rdx+5]; int
0x180195b8c  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x180195b91  mov     [rsp+500h+lpcbData], r14; unsigned __int16 *
0x180195b96  mov     [rsp+500h+lpData], rax; unsigned __int16 *
0x180195b9b  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180195ba0  test    edi, edi
0x180195ba2  cmovnz  r14d, edi
0x180195ba6  mov     edi, r14d
0x180195ba9  jmp     short loc_180195BF4
0x180195bab  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195bb2  jz      short loc_180195BF4
0x180195bb4  mov     rax, [rbp+400h+hMem]
0x180195bb8  lea     r9, aDeletecacheDel_1; "DeleteCache: Deleted cached transform %"...
0x180195bbf  mov     [rsp+500h+var_4A8], r12; void *
0x180195bc4  xor     edx, edx; unsigned __int16
0x180195bc6  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x180195bcb  xor     r8d, r8d; int
0x180195bce  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x180195bd3  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x180195bd8  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x180195bdd  lea     ecx, [rdx+0Ah]; int
0x180195be0  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x180195be5  mov     [rsp+500h+lpcbData], rsi; unsigned __int16 *
0x180195bea  mov     [rsp+500h+lpData], rax; int
0x180195bef  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180195bf4  mov     rcx, [rsp+500h+var_498]; hKey
0x180195bf9  lea     rax, [rbp+400h+hMem]
0x180195bfd  mov     qword ptr [rsp+500h+cbMaxValueLen], rax; cbMaxValueLen
0x180195c02  lea     r8, [rbp+400h+var_260]
0x180195c09  lea     rax, [rsp+500h+cbData]
0x180195c0e  mov     [rbp+400h+var_474], ebx
0x180195c11  inc     r15d
0x180195c14  mov     [rsp+500h+lpcbData], rax; lpType
0x180195c19  mov     edx, r15d; dwIndex
0x180195c1c  mov     [rbp+400h+var_254], ebx
0x180195c22  call    ?MsiRegEnumValueW@@YAJPEAUHKEY__@@KAEAV?$CAPITempBufferRef@G@@PEAK2212@Z; MsiRegEnumValueW(HKEY__ *,ulong,CAPITempBufferRef<ushort> &,ulong *,ulong *,ulong *,CAPITempBufferRef<ushort> &,ulong *)
0x180195c27  test    eax, eax
0x180195c29  jz      loc_180195B1C
0x180195c2f  jmp     loc_180195A7C
0x180195c34  mov     [rsp+500h+Type], r12d
0x180195c39  lea     rax, [rbp+400h+var_470]
0x180195c3d  mov     [rbp+400h+hMem], rax
0x180195c41  mov     [rsp+500h+cbData], 208h
0x180195c49  cmp     r14d, 2
0x180195c4d  jnz     short loc_180195C86
0x180195c4f  mov     esi, r8d
0x180195c52  mov     rcx, rdi; unsigned __int16 *
0x180195c55  mov     edx, esi; unsigned __int64
0x180195c57  lea     r8, asc_18027979C; "\\"
0x180195c5e  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180195c63  test    eax, eax
0x180195c65  js      short loc_180195C7C
0x180195c67  lea     r8, aInstallpropert; "InstallProperties"
0x180195c6e  mov     edx, esi; unsigned __int64
0x180195c70  mov     rcx, rdi; unsigned __int16 *
0x180195c73  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180195c78  test    eax, eax
0x180195c7a  jns     short loc_180195C86
0x180195c7c  mov     edi, 0Eh
0x180195c81  jmp     loc_180195E70
0x180195c86  lea     rax, [rsp+500h+hKey]
0x180195c8b  mov     r9d, 20019h; unsigned int
0x180195c91  mov     rdx, rdi; unsigned __int16 *
0x180195c94  mov     [rsp+500h+lpData], rax; HKEY *
0x180195c99  mov     rcx, r15; HKEY
0x180195c9c  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180195ca1  mov     edi, eax
0x180195ca3  test    eax, eax
0x180195ca5  jz      short loc_180195CFC
0x180195ca7  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195cae  jz      loc_180195E70
0x180195cb4  mov     [rsp+500h+var_4A8], r12; void *
0x180195cb9  lea     rsi, aNull; "(NULL)"
0x180195cc0  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x180195cc5  lea     r9, aDeletecacheReg; "DeleteCache: RegOpenKeyEx returned %08x"...
0x180195ccc  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x180195cd1  xor     edx, edx; unsigned __int16
0x180195cd3  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x180195cd8  xor     r8d, r8d; int
0x180195cdb  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x180195ce0  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x180195ce5  mov     [rsp+500h+lpcbData], rsi; unsigned __int16 *
0x180195cea  lea     ecx, [rdx+0Ah]; int
0x180195ced  mov     [rsp+500h+lpData], rdi; unsigned __int16 *
0x180195cf2  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180195cf7  jmp     loc_180195E70
0x180195cfc  mov     r15d, r12d
0x180195cff  lea     rsi, aNull; "(NULL)"
0x180195d06  mov     rax, [rbp+400h+hMem]
0x180195d0a  lea     rcx, aManagedlocalpa; "ManagedLocalPackage"
0x180195d11  test    r15d, r15d
0x180195d14  lea     rdx, aLocalpackage_0; "LocalPackage"
0x180195d1b  lea     r9, [rsp+500h+Type]; lpType
0x180195d20  cmovnz  rdx, rcx; lpValueName
0x180195d24  lea     rcx, [rsp+500h+cbData]
0x180195d29  mov     [rsp+500h+lpcbData], rcx; lpcbData
0x180195d2e  xor     r8d, r8d; lpReserved
0x180195d31  mov     rcx, [rsp+500h+hKey]; hKey
0x180195d36  mov     [rsp+500h+lpData], rax; lpData
0x180195d3b  call    cs:__imp_RegQueryValueExW
0x180195d42  nop     dword ptr [rax+rax+00h]
0x180195d47  mov     edi, eax
0x180195d49  cmp     eax, 2
0x180195d4c  jnz     short loc_180195D56
0x180195d4e  mov     edi, r12d
0x180195d51  jmp     loc_180195E63
0x180195d56  test    eax, eax
0x180195d58  jz      short loc_180195DA0
0x180195d5a  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195d61  jz      loc_180195E63
0x180195d67  mov     [rsp+500h+var_4A8], r12
0x180195d6c  lea     r9, aDeletecacheReg_0; "DeleteCache: RegQueryValueEx returned %"...
0x180195d73  mov     [rsp+500h+var_4B0], r12d
0x180195d78  mov     ecx, 0Ah
0x180195d7d  mov     [rsp+500h+var_4B8], rsi
0x180195d82  mov     [rsp+500h+var_4C0], rsi
0x180195d87  mov     [rsp+500h+var_4C8], rsi
0x180195d8c  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi
0x180195d91  mov     [rsp+500h+lpcbData], rsi
0x180195d96  mov     [rsp+500h+lpData], rdi
0x180195d9b  jmp     loc_180195E59
0x180195da0  mov     rcx, [rbp+400h+hMem]; lpFileName
0x180195da4  call    cs:__imp_DeleteFileW
0x180195dab  nop     dword ptr [rax+rax+00h]
0x180195db0  test    eax, eax
0x180195db2  jz      short loc_180195E0A
0x180195db4  cmp     r14d, 2
0x180195db8  jnz     short loc_180195DF8
0x180195dba  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195dc1  jz      loc_180195E63
0x180195dc7  lea     r9, aDeletecacheDel; "DeleteCache: Deleted cached package %s."
0x180195dce  mov     [rsp+500h+var_4A8], r12
0x180195dd3  mov     ecx, 0Ah
0x180195dd8  mov     [rsp+500h+var_4B0], r12d
0x180195ddd  mov     [rsp+500h+var_4B8], rsi
0x180195de2  mov     [rsp+500h+var_4C0], rsi
0x180195de7  mov     [rsp+500h+var_4C8], rsi
0x180195dec  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi
0x180195df1  mov     [rsp+500h+lpcbData], rsi
0x180195df6  jmp     short loc_180195E50
0x180195df8  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195dff  jz      short loc_180195E63
0x180195e01  lea     r9, aDeletecacheDel_0; "DeleteCache: Deleted cached patch %s."
0x180195e08  jmp     short loc_180195DCE
0x180195e0a  call    cs:__imp_GetLastError
0x180195e11  nop     dword ptr [rax+rax+00h]
0x180195e16  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180195e1d  mov     edi, eax
0x180195e1f  jz      short loc_180195E63
0x180195e21  mov     [rsp+500h+var_4A8], r12; void *
0x180195e26  lea     r9, aFailedToDelete_2; "Failed to delete file %s with error %08"...
0x180195e2d  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x180195e32  mov     ecx, 5; int
0x180195e37  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x180195e3c  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x180195e41  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x180195e46  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x180195e4b  mov     [rsp+500h+lpcbData], rdi; unsigned __int16 *
0x180195e50  mov     rax, [rbp+400h+hMem]
0x180195e54  mov     [rsp+500h+lpData], rax; unsigned __int16 *
0x180195e59  xor     r8d, r8d; int
0x180195e5c  xor     edx, edx; unsigned __int16
0x180195e5e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180195e63  inc     r15d
0x180195e66  cmp     r15d, 2
0x180195e6a  jl      loc_180195D06
0x180195e70  cmp     [rbp+400h+var_478], ebx
0x180195e73  jle     short loc_180195E85
0x180195e75  mov     rcx, [rbp+400h+hMem]; hMem
0x180195e79  call    cs:__imp_GlobalFree
0x180195e80  nop     dword ptr [rax+rax+00h]
0x180195e85  mov     rcx, [rsp+500h+var_498]; hKey
0x180195e8a  test    rcx, rcx
0x180195e8d  jz      short loc_180195E9B
0x180195e8f  call    cs:__imp_RegCloseKey
0x180195e96  nop     dword ptr [rax+rax+00h]
0x180195e9b  mov     rcx, [rsp+500h+hKey]; hKey
0x180195ea0  test    rcx, rcx
0x180195ea3  jz      short loc_180195EB1
0x180195ea5  call    cs:__imp_RegCloseKey
0x180195eac  nop     dword ptr [rax+rax+00h]
0x180195eb1  mov     eax, edi
0x180195eb3  mov     rcx, [rbp+400h+var_40]
0x180195eba  xor     rcx, rsp; StackCookie
0x180195ebd  call    __security_check_cookie
0x180195ec2  add     rsp, 4D0h
0x180195ec9  pop     r15
0x180195ecb  pop     r14
0x180195ecd  pop     r12
0x180195ecf  pop     rdi
  ... truncated ...
```
