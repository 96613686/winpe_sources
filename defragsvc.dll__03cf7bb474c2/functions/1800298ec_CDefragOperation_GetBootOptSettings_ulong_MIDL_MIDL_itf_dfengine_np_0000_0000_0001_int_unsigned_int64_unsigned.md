# CDefragOperation::_GetBootOptSettings(ulong,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *,int *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ushort * *)

- ea: `0x1800298ec`
- end: `0x180029db5`
- name: `?_GetBootOptSettings@CDefragOperation@@IEAAJKPEAU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@PEAHPEA_K22PEAPEAG@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CDefragOperation *this, char, struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *, int *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e4e0`
- `0x180053410`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180017e34`
- `0x18001913c`
- `0x18001a6c0`
- `0x18001ff18`
- `0x1800244ac`
- `0x1800298ec`
- `0x18002a720`
- `0x18004e8dc`

## import_xrefs

- `msvcrt!_wtoi64` at `0x180029b3f`
- `msvcrt!_wtoi64` at `0x180029b8a`
- `msvcrt!_wtoi64` at `0x180029bd5`
- `msvcrt!_wtoi64` at `0x180029c23`
- `msvcrt!_wtoi64` at `0x180029c55`
- `msvcrt!_wtoi64` at `0x180029b3f`
- `msvcrt!_wtoi64` at `0x180029b8a`
- `msvcrt!_wtoi64` at `0x180029bd5`
- `msvcrt!_wtoi64` at `0x180029c23`
- `msvcrt!_wtoi64` at `0x180029c55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029ca0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029a78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029a78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d7b`

## string_xrefs

- `0x180029aaf`: `LayoutFilePath`

## pseudocode

```c
__int64 __fastcall CDefragOperation::_GetBootOptSettings(
        CDefragOperation *this,
        char a2,
        struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *a3,
        int *a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int16 **a8)
{
  HKEY v12; // rdx
  unsigned int v13; // r9d
  __int64 FileW; // rbx
  __int16 v15; // ax
  HKEY v16; // rdx
  const unsigned __int16 *v17; // r8
  unsigned int v18; // r9d
  const unsigned __int16 *v19; // rcx
  int v20; // eax
  wchar_t *v21; // rbx
  __int64 v22; // r15
  __int64 v23; // rax
  int v24; // eax
  wchar_t *v25; // rbx
  __int64 v26; // r14
  __int64 v27; // rax
  __int64 v28; // rdi
  __int64 v29; // rax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // r12
  unsigned __int64 v33; // r13
  const WCHAR *v34; // rcx
  unsigned int v35; // edi
  unsigned __int16 *dwCreationDisposition; // [rsp+28h] [rbp-A9h]
  unsigned int dwCreationDispositiona; // [rsp+28h] [rbp-A9h]
  unsigned int dwFlagsAndAttributes; // [rsp+30h] [rbp-A1h]
  struct _SECURITY_ATTRIBUTES *v40; // [rsp+40h] [rbp-91h]
  unsigned int *v41; // [rsp+50h] [rbp-81h]
  wchar_t *String; // [rsp+58h] [rbp-79h] BYREF
  __int64 v43; // [rsp+60h] [rbp-71h]
  HKEY v44; // [rsp+68h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-61h] BYREF
  int v46; // [rsp+78h] [rbp-59h]
  int v47; // [rsp+80h] [rbp-51h] BYREF
  __int16 v48; // [rsp+84h] [rbp-4Dh]
  __int16 v49; // [rsp+86h] [rbp-4Bh]
  LPCWSTR lpFileName[10]; // [rsp+B8h] [rbp-19h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v47, "CDefragOperation::_GetBootOptSettings", 2049, 1);
  lpFileName[0] = &qword_18006F470;
  lpFileName[1] = 0;
  v44 = 0;
  String = (wchar_t *)&qword_18006F470;
  v43 = 0;
  hKey = 0;
  FileW = -1;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  v15 = 2070;
  if ( !a3 || (v48 = 2070, v15 = 2071, !a4) )
  {
    v47 = -2147024809;
LABEL_81:
    v49 = v15;
    goto LABEL_82;
  }
  v48 = 2071;
  v15 = 2074;
  if ( !*((_DWORD *)this + 38) )
  {
    v47 = -2147418113;
    goto LABEL_81;
  }
  v47 = 0;
  v48 = 2074;
  if ( (int)SxRegCreateKeyExStateSeparated(
              L"DfrgBootOptimizeFunction",
              v12,
              L"SOFTWARE\\Microsoft\\Dfrg\\BootOptimizeFunction",
              v13,
              dwCreationDisposition,
              dwFlagsAndAttributes,
              0x2001Fu,
              v40,
              &v44,
              v41) < 0
    || (unsigned __int64)v44 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v15 = 2096;
    goto LABEL_79;
  }
  if ( (a2 & 4) == 0 )
  {
    CBsString::Empty((CBsString *)&String);
    if ( (int)SxRegReadString(v44, L"Enable", (struct CBsString *)&String) >= 0 )
    {
      if ( (_DWORD)v43 )
      {
        v15 = 2110;
        if ( *String == 78 )
        {
LABEL_80:
          v47 = -1996488680;
          goto LABEL_81;
        }
        v47 = 0;
        v48 = 2110;
      }
    }
  }
  v46 = a2 & 1;
  if ( (a2 & 1) != 0 )
    goto LABEL_30;
  v19 = (const unsigned __int16 *)hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)SxRegOpenKeyExStateSeparated(v19, v16, v17, v18, dwCreationDispositiona, &hKey) < 0 || !hKey )
  {
    v15 = 2141;
LABEL_79:
    *a4 = 0;
    goto LABEL_80;
  }
  CBsString::Empty((CBsString *)&String);
  v47 = SxRegReadString(hKey, L"LayoutFilePath", (struct CBsString *)&String);
  v15 = 2147;
  if ( v47 < 0 )
  {
    v47 = -1996488681;
    goto LABEL_81;
  }
  v48 = 2147;
  v47 = CBsString::Set((CBsString *)lpFileName, String);
  v15 = 2148;
  if ( v47 < 0 )
    goto LABEL_81;
  v48 = 2148;
LABEL_30:
  if ( (_DWORD)v43 )
  {
    LODWORD(v43) = 0;
    *String = 0;
  }
  v20 = SxRegReadString(v44, L"MaxFileSizeMB", (struct CBsString *)&String);
  v21 = String;
  if ( v20 >= 0 )
  {
    v23 = _wtoi64(String);
    if ( !v23 )
      v23 = 32;
    v22 = v23;
  }
  else
  {
    v22 = 32;
  }
  if ( (_DWORD)v43 )
  {
    LODWORD(v43) = 0;
    *v21 = 0;
  }
  v24 = SxRegReadString(v44, L"MaxZoneSizeMB", (struct CBsString *)&String);
  v25 = String;
  if ( v24 >= 0 )
  {
    v27 = _wtoi64(String);
    if ( !v27 )
      v27 = 12288;
    v26 = v27;
  }
  else
  {
    v26 = 12288;
  }
  if ( (_DWORD)v43 )
  {
    LODWORD(v43) = 0;
    *v25 = 0;
  }
  if ( (int)SxRegReadString(v44, L"MaxTotalFileSizeMB", (struct CBsString *)&String) >= 0 )
  {
    v29 = _wtoi64(String);
    if ( !v29 )
      v29 = 4096;
    v28 = v29;
  }
  else
  {
    v28 = 4096;
  }
  if ( (a2 & 2) != 0 )
  {
    v30 = *(_QWORD *)a3;
    v31 = *((_QWORD *)a3 + 1);
  }
  else
  {
    CBsString::Empty((CBsString *)&String);
    if ( (int)SxRegReadString(v44, L"LcnStartLocation", (struct CBsString *)&String) >= 0 )
      v30 = _wtoi64(String);
    else
      v30 = 0;
    CBsString::Empty((CBsString *)&String);
    if ( (int)SxRegReadString(v44, L"LcnEndLocation", (struct CBsString *)&String) >= 0 )
      v31 = _wtoi64(String);
    else
      v31 = 0;
  }
  v32 = 0;
  if ( v30 <= v31 )
    v32 = v31;
  v33 = 0;
  if ( v30 <= v31 )
    v33 = v30;
  if ( v46 )
    v34 = *a8;
  else
    v34 = lpFileName[0];
  FileW = (__int64)CreateFileW(v34, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    v47 = -1996488677;
    v15 = 2258;
    goto LABEL_81;
  }
  *(_QWORD *)a3 = v33;
  *((_QWORD *)a3 + 1) = v32;
  *a4 = 1;
  if ( a5 )
    *a5 = v26 << 20;
  if ( a6 )
    *a6 = v22 << 20;
  if ( a7 )
    *a7 = v28 << 20;
  if ( a8 && !v46 )
    CBsString::Detach((CBsString *)lpFileName, a8);
LABEL_82:
  v35 = v47;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CBsString::_FreeData(String);
  if ( (unsigned __int64)v44 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v44);
    v44 = 0;
  }
  CBsString::_FreeData((unsigned __int16 *)lpFileName[0]);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v47);
  return v35;
}

```

## disassembly

```asm
0x1800298ec  mov     rax, rsp
0x1800298ef  mov     [rax+8], rbx
0x1800298f3  mov     [rax+20h], r9
0x1800298f7  mov     [rax+18h], r8
0x1800298fb  push    rbp
0x1800298fc  push    rsi
0x1800298fd  push    rdi
0x1800298fe  push    r12
0x180029900  push    r13
0x180029902  push    r14
0x180029904  push    r15
0x180029906  lea     rbp, [rax-3Fh]
0x18002990a  sub     rsp, 0D0h
0x180029911  mov     rdi, r9
0x180029914  mov     r13, r8
0x180029917  mov     r12d, edx
0x18002991a  mov     rsi, rcx
0x18002991d  mov     r9d, 1; unsigned __int16
0x180029923  mov     r8d, 801h; unsigned __int16
0x180029929  lea     rdx, aCdefragoperati_21; "CDefragOperation::_GetBootOptSettings"
0x180029930  lea     rcx, [rbp+37h+var_88]; this
0x180029934  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180029939  nop
0x18002993a  lea     rax, qword_18006F470
0x180029941  mov     [rbp+37h+lpFileName], rax
0x180029945  xor     r14d, r14d
0x180029948  mov     [rbp+37h+var_48], r14
0x18002994c  mov     [rbp+37h+var_A0], r14
0x180029950  mov     [rbp+37h+String], rax
0x180029954  mov     [rbp+37h+var_A8], r14
0x180029958  mov     [rbp+37h+hKey], r14
0x18002995c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029960  test    rdi, rdi
0x180029963  jz      short loc_180029968
0x180029965  mov     [rdi], r14d
0x180029968  mov     rax, [rbp+37h+arg_20]
0x18002996c  test    rax, rax
0x18002996f  jz      short loc_180029974
0x180029971  mov     [rax], r14
0x180029974  mov     rax, [rbp+37h+arg_28]
0x180029978  test    rax, rax
0x18002997b  jz      short loc_180029980
0x18002997d  mov     [rax], r14
0x180029980  mov     rax, [rbp+37h+arg_30]
0x180029984  test    rax, rax
0x180029987  jz      short loc_18002998C
0x180029989  mov     [rax], r14
0x18002998c  mov     eax, 816h
0x180029991  test    r13, r13
0x180029994  jnz     short loc_1800299A2
0x180029996  mov     [rbp+37h+var_88], 80070057h
0x18002999d  jmp     loc_180029D30
0x1800299a2  mov     [rbp+37h+var_84], ax
0x1800299a6  mov     eax, 817h
0x1800299ab  test    rdi, rdi
0x1800299ae  jz      short loc_180029996
0x1800299b0  mov     [rbp+37h+var_84], ax
0x1800299b4  mov     eax, 81Ah
0x1800299b9  cmp     [rsi+98h], r14d
0x1800299c0  ja      short loc_1800299CE
0x1800299c2  mov     [rbp+37h+var_88], 8000FFFFh
0x1800299c9  jmp     loc_180029D30
0x1800299ce  mov     [rbp+37h+var_88], r14d
0x1800299d2  mov     [rbp+37h+var_84], ax
0x1800299d6  lea     rax, [rbp+37h+var_A0]
0x1800299da  mov     [rsp+40h], rax; PHKEY
0x1800299df  mov     [rsp+100h+dwFlagsAndAttributes+8], 2001Fh; REGSAM
0x1800299e7  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Dfrg\\BootOptimize"...
0x1800299ee  lea     rcx, aDfrgbootoptimi; "DfrgBootOptimizeFunction"
0x1800299f5  call    ?SxRegCreateKeyExStateSeparated@@YAJPEBGPEAUHKEY__@@0KPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SxRegCreateKeyExStateSeparated(ushort const *,HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1800299fa  test    eax, eax
0x1800299fc  js      loc_180029D21
0x180029a02  mov     rax, [rbp+37h+var_A0]
0x180029a06  dec     rax
0x180029a09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029a0d  ja      loc_180029D21
0x180029a13  test    r12b, 4
0x180029a17  jnz     short loc_180029A5B
0x180029a19  lea     rcx, [rbp+37h+String]; this
0x180029a1d  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180029a22  lea     r8, [rbp+37h+String]; this
0x180029a26  lea     rdx, aEnable; "Enable"
0x180029a2d  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029a31  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029a36  test    eax, eax
0x180029a38  js      short loc_180029A5B
0x180029a3a  cmp     dword ptr [rbp+37h+var_A8], r14d
0x180029a3e  jz      short loc_180029A5B
0x180029a40  mov     rax, [rbp+37h+String]
0x180029a44  cmp     word ptr [rax], 4Eh ; 'N'
0x180029a48  mov     eax, 83Eh
0x180029a4d  jz      loc_180029D29
0x180029a53  mov     [rbp+37h+var_88], r14d
0x180029a57  mov     [rbp+37h+var_84], ax
0x180029a5b  mov     eax, r12d
0x180029a5e  and     eax, 1
0x180029a61  mov     [rbp+37h+var_90], eax
0x180029a64  jnz     loc_180029AFC
0x180029a6a  mov     rcx, [rbp+37h+hKey]; hKey
0x180029a6e  lea     rax, [rcx-1]
0x180029a72  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029a76  ja      short loc_180029A82
0x180029a78  call    cs:__imp_RegCloseKey
0x180029a7e  mov     [rbp+37h+hKey], r14
0x180029a82  lea     rax, [rbp+37h+hKey]
0x180029a86  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax; PHKEY
0x180029a8b  call    ?SxRegOpenKeyExStateSeparated@@YAJPEBGPEAUHKEY__@@0KKPEAPEAU1@@Z; SxRegOpenKeyExStateSeparated(ushort const *,HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180029a90  test    eax, eax
0x180029a92  js      loc_180029B32
0x180029a98  cmp     [rbp+37h+hKey], r14
0x180029a9c  jz      loc_180029B32
0x180029aa2  lea     rcx, [rbp+37h+String]; this
0x180029aa6  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180029aab  lea     r8, [rbp+37h+String]; this
0x180029aaf  lea     rdx, aLayoutfilepath; "LayoutFilePath"
0x180029ab6  mov     rcx, [rbp+37h+hKey]; hKey
0x180029aba  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029abf  mov     [rbp+37h+var_88], eax
0x180029ac2  test    eax, eax
0x180029ac4  mov     eax, 863h
0x180029ac9  jns     short loc_180029AD7
0x180029acb  mov     [rbp+37h+var_88], 89000017h
0x180029ad2  jmp     loc_180029D30
0x180029ad7  mov     [rbp+37h+var_84], ax
0x180029adb  mov     rdx, [rbp+37h+String]; unsigned __int16 *
0x180029adf  lea     rcx, [rbp+37h+lpFileName]; this
0x180029ae3  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180029ae8  mov     [rbp+37h+var_88], eax
0x180029aeb  test    eax, eax
0x180029aed  mov     eax, 864h
0x180029af2  js      loc_180029D30
0x180029af8  mov     [rbp+37h+var_84], ax
0x180029afc  cmp     dword ptr [rbp+37h+var_A8], r14d
0x180029b00  jz      short loc_180029B0E
0x180029b02  mov     dword ptr [rbp+37h+var_A8], r14d
0x180029b06  mov     rax, [rbp+37h+String]
0x180029b0a  mov     [rax], r14w
0x180029b0e  lea     r8, [rbp+37h+String]; this
0x180029b12  lea     rdx, aMaxfilesizemb; "MaxFileSizeMB"
0x180029b19  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029b1d  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029b22  mov     rbx, [rbp+37h+String]
0x180029b26  test    eax, eax
0x180029b28  jns     short loc_180029B3C
0x180029b2a  mov     r15d, 20h ; ' '
0x180029b30  jmp     short loc_180029B55
0x180029b32  mov     eax, 85Dh
0x180029b37  jmp     loc_180029D26
0x180029b3c  mov     rcx, rbx; String
0x180029b3f  call    cs:__imp__wtoi64
0x180029b45  mov     r15d, 20h ; ' '
0x180029b4b  test    rax, rax
0x180029b4e  cmovz   rax, r15
0x180029b52  mov     r15, rax
0x180029b55  cmp     dword ptr [rbp+37h+var_A8], r14d
0x180029b59  jz      short loc_180029B63
0x180029b5b  mov     dword ptr [rbp+37h+var_A8], r14d
0x180029b5f  mov     [rbx], r14w
0x180029b63  lea     r8, [rbp+37h+String]; this
0x180029b67  lea     rdx, aMaxzonesizemb; "MaxZoneSizeMB"
0x180029b6e  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029b72  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029b77  mov     rbx, [rbp+37h+String]
0x180029b7b  test    eax, eax
0x180029b7d  jns     short loc_180029B87
0x180029b7f  mov     r14d, 3000h
0x180029b85  jmp     short loc_180029BA0
0x180029b87  mov     rcx, rbx; String
0x180029b8a  call    cs:__imp__wtoi64
0x180029b90  mov     r14d, 3000h
0x180029b96  test    rax, rax
0x180029b99  cmovz   rax, r14
0x180029b9d  mov     r14, rax
0x180029ba0  cmp     dword ptr [rbp+37h+var_A8], 0
0x180029ba4  jz      short loc_180029BB2
0x180029ba6  mov     dword ptr [rbp+37h+var_A8], 0
0x180029bad  xor     eax, eax
0x180029baf  mov     [rbx], ax
0x180029bb2  lea     r8, [rbp+37h+String]; this
0x180029bb6  lea     rdx, aMaxtotalfilesi; "MaxTotalFileSizeMB"
0x180029bbd  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029bc1  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029bc6  test    eax, eax
0x180029bc8  jns     short loc_180029BD1
0x180029bca  mov     edi, 1000h
0x180029bcf  jmp     short loc_180029BEA
0x180029bd1  mov     rcx, [rbp+37h+String]; String
0x180029bd5  call    cs:__imp__wtoi64
0x180029bdb  mov     edi, 1000h
0x180029be0  test    rax, rax
0x180029be3  cmovz   rax, rdi
0x180029be7  mov     rdi, rax
0x180029bea  test    r12b, 2
0x180029bee  jz      short loc_180029BFA
0x180029bf0  mov     rbx, [r13+0]
0x180029bf4  mov     rax, [r13+8]
0x180029bf8  jmp     short loc_180029C5B
0x180029bfa  lea     rcx, [rbp+37h+String]; this
0x180029bfe  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180029c03  lea     r8, [rbp+37h+String]; this
0x180029c07  lea     rdx, aLcnstartlocati; "LcnStartLocation"
0x180029c0e  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029c12  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029c17  test    eax, eax
0x180029c19  jns     short loc_180029C1F
0x180029c1b  xor     ebx, ebx
0x180029c1d  jmp     short loc_180029C2C
0x180029c1f  mov     rcx, [rbp+37h+String]; String
0x180029c23  call    cs:__imp__wtoi64
0x180029c29  mov     rbx, rax
0x180029c2c  lea     rcx, [rbp+37h+String]; this
0x180029c30  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180029c35  lea     r8, [rbp+37h+String]; this
0x180029c39  lea     rdx, aLcnendlocation; "LcnEndLocation"
0x180029c40  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029c44  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180029c49  test    eax, eax
0x180029c4b  jns     short loc_180029C51
0x180029c4d  xor     eax, eax
0x180029c4f  jmp     short loc_180029C5B
0x180029c51  mov     rcx, [rbp+37h+String]; String
0x180029c55  call    cs:__imp__wtoi64
0x180029c5b  xor     r12d, r12d
0x180029c5e  cmp     rbx, rax
0x180029c61  cmovbe  r12, rax
0x180029c65  xor     r13d, r13d
0x180029c68  cmp     rbx, rax
0x180029c6b  cmovbe  r13, rbx
0x180029c6f  mov     rsi, [rbp+37h+arg_38]
0x180029c73  xor     eax, eax
0x180029c75  cmp     [rbp+37h+var_90], eax
0x180029c78  jz      short loc_180029C7F
0x180029c7a  mov     rcx, [rsi]
0x180029c7d  jmp     short loc_180029C83
0x180029c7f  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x180029c83  mov     qword ptr [rsp+100h+dwFlagsAndAttributes+8], rax; hTemplateFile
0x180029c88  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180029c8c  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x180029c94  xor     r9d, r9d; lpSecurityAttributes
0x180029c97  mov     edx, 80000000h; dwDesiredAccess
0x180029c9c  lea     r8d, [r9+1]; dwShareMode
0x180029ca0  call    cs:__imp_CreateFileW
0x180029ca6  mov     rbx, rax
0x180029ca9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029cad  jnz     short loc_180029CC0
0x180029caf  mov     [rbp+37h+var_88], 8900001Bh
0x180029cb6  mov     eax, 8D2h
0x180029cbb  xor     r14d, r14d
0x180029cbe  jmp     short loc_180029D30
0x180029cc0  mov     rax, [rbp+37h+arg_10]
0x180029cc4  mov     [rax], r13
0x180029cc7  mov     [rax+8], r12
0x180029ccb  mov     rax, [rbp+37h+arg_18]
0x180029ccf  mov     dword ptr [rax], 1
0x180029cd5  mov     rax, [rbp+37h+arg_20]
0x180029cd9  test    rax, rax
0x180029cdc  jz      short loc_180029CE5
0x180029cde  shl     r14, 14h
0x180029ce2  mov     [rax], r14
0x180029ce5  mov     rax, [rbp+37h+arg_28]
0x180029ce9  xor     r14d, r14d
0x180029cec  test    rax, rax
0x180029cef  jz      short loc_180029CF8
0x180029cf1  shl     r15, 14h
0x180029cf5  mov     [rax], r15
0x180029cf8  mov     rax, [rbp+37h+arg_30]
0x180029cfc  test    rax, rax
0x180029cff  jz      short loc_180029D08
0x180029d01  shl     rdi, 14h
0x180029d05  mov     [rax], rdi
0x180029d08  test    rsi, rsi
0x180029d0b  jz      short loc_180029D34
0x180029d0d  cmp     [rbp+37h+var_90], r14d
0x180029d11  jnz     short loc_180029D34
0x180029d13  mov     rdx, rsi; unsigned __int16 **
0x180029d16  lea     rcx, [rbp+37h+lpFileName]; this
0x180029d1a  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x180029d1f  jmp     short loc_180029D34
0x180029d21  mov     eax, 830h
0x180029d26  mov     [rdi], r14d
0x180029d29  mov     [rbp+37h+var_88], 89000018h
0x180029d30  mov     [rbp+37h+var_82], ax
0x180029d34  mov     edi, [rbp+37h+var_88]
0x180029d37  lea     rax, [rbx-1]
0x180029d3b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029d3f  ja      short loc_180029D4B
0x180029d41  mov     rcx, rbx; hObject
0x180029d44  call    cs:__imp_CloseHandle
0x180029d4a  nop
0x180029d4b  mov     rcx, [rbp+37h+hKey]; hKey
0x180029d4f  lea     rax, [rcx-1]
0x180029d53  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029d57  ja      short loc_180029D63
0x180029d59  call    cs:__imp_RegCloseKey
0x180029d5f  mov     [rbp+37h+hKey], r14
0x180029d63  mov     rcx, [rbp+37h+String]; unsigned __int16 *
0x180029d67  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180029d6c  nop
0x180029d6d  mov     rcx, [rbp+37h+var_A0]; hKey
0x180029d71  lea     rdx, [rcx-1]
  ... truncated ...
```
