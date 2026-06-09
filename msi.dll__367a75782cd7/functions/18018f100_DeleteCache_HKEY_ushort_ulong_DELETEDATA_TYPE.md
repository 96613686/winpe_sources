# DeleteCache(HKEY__ *,ushort *,ulong,DELETEDATA_TYPE)

- ea: `0x18018f100`
- end: `0x18018f5de`
- name: `?DeleteCache@@YAIPEAUHKEY__@@PEAGKW4DELETEDATA_TYPE@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180019bb4`
- `0x180025a18`
- `0x180072450`
- `0x18018f100`
- `0x18019358c`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18018f469`
- `ADVAPI32!RegQueryValueExW` at `0x18018f469`
- `ADVAPI32!RegCloseKey` at `0x18018f5a5`
- `ADVAPI32!RegCloseKey` at `0x18018f5b5`
- `ADVAPI32!RegCloseKey` at `0x18018f5a5`
- `ADVAPI32!RegCloseKey` at `0x18018f5b5`
- `KERNEL32!DeleteFileW` at `0x18018f265`
- `KERNEL32!DeleteFileW` at `0x18018f4cc`
- `KERNEL32!DeleteFileW` at `0x18018f265`
- `KERNEL32!DeleteFileW` at `0x18018f4cc`
- `KERNEL32!GetLastError` at `0x18018f26f`
- `KERNEL32!GetLastError` at `0x18018f52c`
- `KERNEL32!GetLastError` at `0x18018f26f`
- `KERNEL32!GetLastError` at `0x18018f52c`
- `KERNEL32!GlobalFree` at `0x18018f1c5`
- `KERNEL32!GlobalFree` at `0x18018f595`
- `KERNEL32!GlobalFree` at `0x18018f1c5`
- `KERNEL32!GlobalFree` at `0x18018f595`

## string_xrefs

- `0x18018f395`: `InstallProperties`
- `0x18018f3f3`: `DeleteCache: RegOpenKeyEx returned %08x.`
- `0x18018f494`: `DeleteCache: RegQueryValueEx returned %08x.`
- `0x18018f4e9`: `DeleteCache: Deleted cached package %s.`
- `0x18018f523`: `DeleteCache: Deleted cached patch %s.`
- `0x18018f292`: `Failed to delete file %s with error %08x.`
- `0x18018f542`: `Failed to delete file %s with error %08x.`
- `0x18018f2e6`: `DeleteCache: Deleted cached transform %s.`

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
0x18018f100  push    rbp
0x18018f102  push    rbx
0x18018f103  push    rsi
0x18018f104  push    rdi
0x18018f105  push    r12
0x18018f107  push    r14
0x18018f109  push    r15
0x18018f10b  lea     rbp, [rsp-3D0h]
0x18018f113  sub     rsp, 4D0h
0x18018f11a  mov     rax, cs:__security_cookie
0x18018f121  xor     rax, rsp
0x18018f124  mov     [rbp+400h+var_40], rax
0x18018f12b  xor     r12d, r12d
0x18018f12e  mov     r14d, r9d
0x18018f131  mov     [rsp+500h+var_498], r12
0x18018f136  mov     rdi, rdx
0x18018f139  mov     [rsp+500h+hKey], r12
0x18018f13e  mov     r15, rcx
0x18018f141  test    rdx, rdx
0x18018f144  jnz     short loc_18018F14E
0x18018f146  lea     eax, [rdx+57h]
0x18018f149  jmp     loc_18018F5BD
0x18018f14e  lea     eax, [r9-2]
0x18018f152  mov     ebx, 104h
0x18018f157  mov     [rbp+400h+var_478], ebx
0x18018f15a  cmp     eax, 1
0x18018f15d  jbe     loc_18018F362
0x18018f163  mov     [rsp+500h+cbData], r12d
0x18018f168  lea     rax, [rbp+400h+var_250]
0x18018f16f  mov     [rbp+400h+var_260], rax
0x18018f176  lea     rax, [rbp+400h+var_470]
0x18018f17a  mov     [rbp+400h+hMem], rax
0x18018f17e  mov     [rbp+400h+var_258], ebx
0x18018f184  cmp     r14d, 4
0x18018f188  jnz     short loc_18018F1EE
0x18018f18a  mov     esi, r8d
0x18018f18d  mov     rcx, rdi; unsigned __int16 *
0x18018f190  mov     edx, esi; unsigned __int64
0x18018f192  lea     r8, asc_18026F7A4; "\\"
0x18018f199  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18018f19e  test    eax, eax
0x18018f1a0  js      short loc_18018F1B7
0x18018f1a2  lea     r8, aTransforms_1; "Transforms"
0x18018f1a9  mov     edx, esi; unsigned __int64
0x18018f1ab  mov     rcx, rdi; unsigned __int16 *
0x18018f1ae  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18018f1b3  test    eax, eax
0x18018f1b5  jns     short loc_18018F1EE
0x18018f1b7  mov     edi, 0Eh
0x18018f1bc  cmp     [rbp+400h+var_478], ebx
0x18018f1bf  jle     short loc_18018F1CB
0x18018f1c1  mov     rcx, [rbp+400h+hMem]; hMem
0x18018f1c5  call    cs:__imp_GlobalFree
0x18018f1cb  lea     rax, [rbp+400h+var_470]
0x18018f1cf  mov     [rbp+400h+var_478], ebx
0x18018f1d2  mov     [rbp+400h+hMem], rax
0x18018f1d6  cmp     [rbp+400h+var_258], ebx
0x18018f1dc  jle     loc_18018F59B
0x18018f1e2  mov     rcx, [rbp+400h+var_260]
0x18018f1e9  jmp     loc_18018F595
0x18018f1ee  lea     rax, [rsp+500h+var_498]
0x18018f1f3  mov     r9d, 20019h; unsigned int
0x18018f1f9  mov     rdx, rdi; unsigned __int16 *
0x18018f1fc  mov     [rsp+500h+lpData], rax; int
0x18018f201  mov     rcx, r15; HKEY
0x18018f204  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18018f209  mov     edi, eax
0x18018f20b  test    eax, 0FFFFFFFDh
0x18018f210  jnz     short loc_18018F1BC
0x18018f212  mov     rcx, [rsp+500h+var_498]; hKey
0x18018f217  lea     rax, [rbp+400h+hMem]
0x18018f21b  mov     qword ptr [rsp+500h+cbMaxValueLen], rax; cbMaxValueLen
0x18018f220  lea     r8, [rbp+400h+var_260]
0x18018f227  lea     rax, [rsp+500h+cbData]
0x18018f22c  mov     [rbp+400h+var_474], ebx
0x18018f22f  xor     edx, edx; dwIndex
0x18018f231  mov     [rsp+500h+lpcbData], rax; lpType
0x18018f236  mov     edi, r12d
0x18018f239  mov     [rbp+400h+var_254], ebx
0x18018f23f  mov     r15d, r12d
0x18018f242  call    ?MsiRegEnumValueW@@YAJPEAUHKEY__@@KAEAV?$CAPITempBufferRef@G@@PEAK2212@Z; MsiRegEnumValueW(HKEY__ *,ulong,CAPITempBufferRef<ushort> &,ulong *,ulong *,ulong *,CAPITempBufferRef<ushort> &,ulong *)
0x18018f247  test    eax, eax
0x18018f249  jnz     loc_18018F1BC
0x18018f24f  lea     rsi, aNull; "(NULL)"
0x18018f256  cmp     [rsp+500h+cbData], 1
0x18018f25b  jnz     loc_18018F322
0x18018f261  mov     rcx, [rbp+400h+hMem]; lpFileName
0x18018f265  call    cs:__imp_DeleteFileW
0x18018f26b  test    eax, eax
0x18018f26d  jnz     short loc_18018F2D9
0x18018f26f  call    cs:__imp_GetLastError
0x18018f275  mov     r14d, eax
0x18018f278  cmp     eax, 2
0x18018f27b  jz      loc_18018F322
0x18018f281  test    eax, eax
0x18018f283  jz      short loc_18018F2D9
0x18018f285  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f28c  jz      short loc_18018F2CE
0x18018f28e  mov     rax, [rbp+400h+hMem]
0x18018f292  lea     r9, aFailedToDelete_2; "Failed to delete file %s with error %08"...
0x18018f299  mov     [rsp+500h+var_4A8], r12; void *
0x18018f29e  xor     edx, edx; unsigned __int16
0x18018f2a0  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x18018f2a5  xor     r8d, r8d; int
0x18018f2a8  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x18018f2ad  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x18018f2b2  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x18018f2b7  lea     ecx, [rdx+5]; int
0x18018f2ba  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x18018f2bf  mov     [rsp+500h+lpcbData], r14; unsigned __int16 *
0x18018f2c4  mov     [rsp+500h+lpData], rax; unsigned __int16 *
0x18018f2c9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18018f2ce  test    edi, edi
0x18018f2d0  cmovnz  r14d, edi
0x18018f2d4  mov     edi, r14d
0x18018f2d7  jmp     short loc_18018F322
0x18018f2d9  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f2e0  jz      short loc_18018F322
0x18018f2e2  mov     rax, [rbp+400h+hMem]
0x18018f2e6  lea     r9, aDeletecacheDel_1; "DeleteCache: Deleted cached transform %"...
0x18018f2ed  mov     [rsp+500h+var_4A8], r12; void *
0x18018f2f2  xor     edx, edx; unsigned __int16
0x18018f2f4  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x18018f2f9  xor     r8d, r8d; int
0x18018f2fc  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x18018f301  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x18018f306  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x18018f30b  lea     ecx, [rdx+0Ah]; int
0x18018f30e  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x18018f313  mov     [rsp+500h+lpcbData], rsi; unsigned __int16 *
0x18018f318  mov     [rsp+500h+lpData], rax; int
0x18018f31d  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18018f322  mov     rcx, [rsp+500h+var_498]; hKey
0x18018f327  lea     rax, [rbp+400h+hMem]
0x18018f32b  mov     qword ptr [rsp+500h+cbMaxValueLen], rax; cbMaxValueLen
0x18018f330  lea     r8, [rbp+400h+var_260]
0x18018f337  lea     rax, [rsp+500h+cbData]
0x18018f33c  mov     [rbp+400h+var_474], ebx
0x18018f33f  inc     r15d
0x18018f342  mov     [rsp+500h+lpcbData], rax; lpType
0x18018f347  mov     edx, r15d; dwIndex
0x18018f34a  mov     [rbp+400h+var_254], ebx
0x18018f350  call    ?MsiRegEnumValueW@@YAJPEAUHKEY__@@KAEAV?$CAPITempBufferRef@G@@PEAK2212@Z; MsiRegEnumValueW(HKEY__ *,ulong,CAPITempBufferRef<ushort> &,ulong *,ulong *,ulong *,CAPITempBufferRef<ushort> &,ulong *)
0x18018f355  test    eax, eax
0x18018f357  jz      loc_18018F256
0x18018f35d  jmp     loc_18018F1BC
0x18018f362  mov     [rsp+500h+Type], r12d
0x18018f367  lea     rax, [rbp+400h+var_470]
0x18018f36b  mov     [rbp+400h+hMem], rax
0x18018f36f  mov     [rsp+500h+cbData], 208h
0x18018f377  cmp     r14d, 2
0x18018f37b  jnz     short loc_18018F3B4
0x18018f37d  mov     esi, r8d
0x18018f380  mov     rcx, rdi; unsigned __int16 *
0x18018f383  mov     edx, esi; unsigned __int64
0x18018f385  lea     r8, asc_18026F7A4; "\\"
0x18018f38c  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18018f391  test    eax, eax
0x18018f393  js      short loc_18018F3AA
0x18018f395  lea     r8, aInstallpropert; "InstallProperties"
0x18018f39c  mov     edx, esi; unsigned __int64
0x18018f39e  mov     rcx, rdi; unsigned __int16 *
0x18018f3a1  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18018f3a6  test    eax, eax
0x18018f3a8  jns     short loc_18018F3B4
0x18018f3aa  mov     edi, 0Eh
0x18018f3af  jmp     loc_18018F58C
0x18018f3b4  lea     rax, [rsp+500h+hKey]
0x18018f3b9  mov     r9d, 20019h; unsigned int
0x18018f3bf  mov     rdx, rdi; unsigned __int16 *
0x18018f3c2  mov     [rsp+500h+lpData], rax; HKEY *
0x18018f3c7  mov     rcx, r15; HKEY
0x18018f3ca  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18018f3cf  mov     edi, eax
0x18018f3d1  test    eax, eax
0x18018f3d3  jz      short loc_18018F42A
0x18018f3d5  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f3dc  jz      loc_18018F58C
0x18018f3e2  mov     [rsp+500h+var_4A8], r12; void *
0x18018f3e7  lea     rsi, aNull; "(NULL)"
0x18018f3ee  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x18018f3f3  lea     r9, aDeletecacheReg; "DeleteCache: RegOpenKeyEx returned %08x"...
0x18018f3fa  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x18018f3ff  xor     edx, edx; unsigned __int16
0x18018f401  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x18018f406  xor     r8d, r8d; int
0x18018f409  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x18018f40e  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x18018f413  mov     [rsp+500h+lpcbData], rsi; unsigned __int16 *
0x18018f418  lea     ecx, [rdx+0Ah]; int
0x18018f41b  mov     [rsp+500h+lpData], rdi; unsigned __int16 *
0x18018f420  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18018f425  jmp     loc_18018F58C
0x18018f42a  mov     r15d, r12d
0x18018f42d  lea     rsi, aNull; "(NULL)"
0x18018f434  mov     rax, [rbp+400h+hMem]
0x18018f438  lea     rcx, aManagedlocalpa; "ManagedLocalPackage"
0x18018f43f  test    r15d, r15d
0x18018f442  lea     rdx, aLocalpackage_0; "LocalPackage"
0x18018f449  lea     r9, [rsp+500h+Type]; lpType
0x18018f44e  cmovnz  rdx, rcx; lpValueName
0x18018f452  lea     rcx, [rsp+500h+cbData]
0x18018f457  mov     [rsp+500h+lpcbData], rcx; lpcbData
0x18018f45c  xor     r8d, r8d; lpReserved
0x18018f45f  mov     rcx, [rsp+500h+hKey]; hKey
0x18018f464  mov     [rsp+500h+lpData], rax; lpData
0x18018f469  call    cs:__imp_RegQueryValueExW
0x18018f46f  mov     edi, eax
0x18018f471  cmp     eax, 2
0x18018f474  jnz     short loc_18018F47E
0x18018f476  mov     edi, r12d
0x18018f479  jmp     loc_18018F57F
0x18018f47e  test    eax, eax
0x18018f480  jz      short loc_18018F4C8
0x18018f482  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f489  jz      loc_18018F57F
0x18018f48f  mov     [rsp+500h+var_4A8], r12
0x18018f494  lea     r9, aDeletecacheReg_0; "DeleteCache: RegQueryValueEx returned %"...
0x18018f49b  mov     [rsp+500h+var_4B0], r12d
0x18018f4a0  mov     ecx, 0Ah
0x18018f4a5  mov     [rsp+500h+var_4B8], rsi
0x18018f4aa  mov     [rsp+500h+var_4C0], rsi
0x18018f4af  mov     [rsp+500h+var_4C8], rsi
0x18018f4b4  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi
0x18018f4b9  mov     [rsp+500h+lpcbData], rsi
0x18018f4be  mov     [rsp+500h+lpData], rdi
0x18018f4c3  jmp     loc_18018F575
0x18018f4c8  mov     rcx, [rbp+400h+hMem]; lpFileName
0x18018f4cc  call    cs:__imp_DeleteFileW
0x18018f4d2  test    eax, eax
0x18018f4d4  jz      short loc_18018F52C
0x18018f4d6  cmp     r14d, 2
0x18018f4da  jnz     short loc_18018F51A
0x18018f4dc  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f4e3  jz      loc_18018F57F
0x18018f4e9  lea     r9, aDeletecacheDel; "DeleteCache: Deleted cached package %s."
0x18018f4f0  mov     [rsp+500h+var_4A8], r12
0x18018f4f5  mov     ecx, 0Ah
0x18018f4fa  mov     [rsp+500h+var_4B0], r12d
0x18018f4ff  mov     [rsp+500h+var_4B8], rsi
0x18018f504  mov     [rsp+500h+var_4C0], rsi
0x18018f509  mov     [rsp+500h+var_4C8], rsi
0x18018f50e  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi
0x18018f513  mov     [rsp+500h+lpcbData], rsi
0x18018f518  jmp     short loc_18018F56C
0x18018f51a  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f521  jz      short loc_18018F57F
0x18018f523  lea     r9, aDeletecacheDel_0; "DeleteCache: Deleted cached patch %s."
0x18018f52a  jmp     short loc_18018F4F0
0x18018f52c  call    cs:__imp_GetLastError
0x18018f532  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18018f539  mov     edi, eax
0x18018f53b  jz      short loc_18018F57F
0x18018f53d  mov     [rsp+500h+var_4A8], r12; void *
0x18018f542  lea     r9, aFailedToDelete_2; "Failed to delete file %s with error %08"...
0x18018f549  mov     [rsp+500h+var_4B0], r12d; unsigned int
0x18018f54e  mov     ecx, 5; int
0x18018f553  mov     [rsp+500h+var_4B8], rsi; unsigned __int16 *
0x18018f558  mov     [rsp+500h+var_4C0], rsi; unsigned __int16 *
0x18018f55d  mov     [rsp+500h+var_4C8], rsi; unsigned __int16 *
0x18018f562  mov     qword ptr [rsp+500h+cbMaxValueLen], rsi; unsigned __int16 *
0x18018f567  mov     [rsp+500h+lpcbData], rdi; unsigned __int16 *
0x18018f56c  mov     rax, [rbp+400h+hMem]
0x18018f570  mov     [rsp+500h+lpData], rax; unsigned __int16 *
0x18018f575  xor     r8d, r8d; int
0x18018f578  xor     edx, edx; unsigned __int16
0x18018f57a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18018f57f  inc     r15d
0x18018f582  cmp     r15d, 2
0x18018f586  jl      loc_18018F434
0x18018f58c  cmp     [rbp+400h+var_478], ebx
0x18018f58f  jle     short loc_18018F59B
0x18018f591  mov     rcx, [rbp+400h+hMem]; hMem
0x18018f595  call    cs:__imp_GlobalFree
0x18018f59b  mov     rcx, [rsp+500h+var_498]; hKey
0x18018f5a0  test    rcx, rcx
0x18018f5a3  jz      short loc_18018F5AB
0x18018f5a5  call    cs:__imp_RegCloseKey
0x18018f5ab  mov     rcx, [rsp+500h+hKey]; hKey
0x18018f5b0  test    rcx, rcx
0x18018f5b3  jz      short loc_18018F5BB
0x18018f5b5  call    cs:__imp_RegCloseKey
0x18018f5bb  mov     eax, edi
0x18018f5bd  mov     rcx, [rbp+400h+var_40]
0x18018f5c4  xor     rcx, rsp; StackCookie
0x18018f5c7  call    __security_check_cookie
0x18018f5cc  add     rsp, 4D0h
0x18018f5d3  pop     r15
0x18018f5d5  pop     r14
0x18018f5d7  pop     r12
0x18018f5d9  pop     rdi
0x18018f5da  pop     rsi
0x18018f5db  pop     rbx
0x18018f5dc  pop     rbp
0x18018f5dd  retn
```
