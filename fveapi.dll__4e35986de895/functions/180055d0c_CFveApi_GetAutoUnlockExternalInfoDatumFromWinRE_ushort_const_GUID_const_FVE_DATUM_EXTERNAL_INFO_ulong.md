# CFveApi::GetAutoUnlockExternalInfoDatumFromWinRE(ushort const *,_GUID const *,_FVE_DATUM_EXTERNAL_INFO *,ulong)

- ea: `0x180055d0c`
- end: `0x180056245`
- name: `?GetAutoUnlockExternalInfoDatumFromWinRE@CFveApi@@KAJPEBGPEBU_GUID@@PEAU_FVE_DATUM_EXTERNAL_INFO@@K@Z`
- size: `1337`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, GUID *Guid, struct _FVE_DATUM_EXTERNAL_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cfe3c`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x18000aae0`
- `0x180018b10`
- `0x18001c770`
- `0x18001ee3c`
- `0x180037f50`
- `0x18003d000`
- `0x18004a264`
- `0x180055d0c`
- `0x180060196`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800561c7`
- `ntdll!RtlFreeUnicodeString` at `0x1800561c7`
- `ntdll!RtlStringFromGUID` at `0x180055ee6`
- `ntdll!RtlStringFromGUID` at `0x180055ee6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005602b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005602b`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180055e8e`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180055e8e`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800561e6`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800561e6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055e0a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055e0a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180055dc2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180055dc2`

## string_xrefs

- `0x180055dae`: `Windows\System32\Config\SYSTEM`

## pseudocode

```c
__int64 __fastcall CFveApi::GetAutoUnlockExternalInfoDatumFromWinRE(
        PCWSTR pszPathIn,
        GUID *Guid,
        struct _FVE_DATUM_EXTERNAL_INFO *a3)
{
  char v6; // r15
  unsigned int v7; // eax
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  LSTATUS KeyW; // eax
  NTSTATUS v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  void *pvData; // rdi
  LSTATUS ValueW; // eax
  unsigned int v17; // ecx
  PVOID *v18; // rcx
  bool v19; // zf
  int IsValidBounded; // eax
  unsigned int v21; // eax
  int MustBe; // eax
  unsigned int v23; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(SubKey, 0, 0x208u);
  pcbData = 0xFFFF;
  v6 = 0;
  GuidString = 0;
  memset_0(pszPathOut, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
  v7 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"Windows\\System32\\Config\\SYSTEM");
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v7);
    if ( v8 < 0 )
      goto LABEL_71;
  }
  if ( GetFileAttributesW(pszPathOut) == -1 )
  {
    v8 = -2147024894;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v10 = 35;
LABEL_13:
      WPP_SF_d(v9[2], v10, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, (unsigned int)v8);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, pszPathOut);
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", pszPathOut);
  v8 = KeyW;
  if ( KeyW > 0 )
    v8 = (unsigned __int16)KeyW | 0x80070000;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_82fbf6316f983a090a97009b222379cf_Traceguids,
        (unsigned int)v8);
    if ( v8 < 0 )
      goto LABEL_71;
  }
  v6 = 1;
  v12 = RtlStringFromGUID(Guid, &GuidString);
  v13 = FromNtStatus(v12);
  v8 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v13);
    if ( v8 < 0 )
      goto LABEL_71;
  }
  v14 = StringCchPrintfW(
          SubKey,
          0x104u,
          L"%s\\%s\\%wZ",
          L"BitLockerSystemRoot",
          L"ControlSet001\\Control\\FVEAutoUnlock",
          &GuidString);
  v8 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v14);
    if ( v8 < 0 )
      goto LABEL_71;
  }
  pvData = CFveApiBase::ZeroAlloc(pcbData);
  if ( pvData )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, SubKey);
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Data", 8u, 0, pvData, &pcbData);
    v17 = ValueW;
    if ( ValueW > 0 )
      v17 = (unsigned __int16)ValueW | 0x80070000;
    if ( v17 == -2147024894 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, Guid);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      v8 = -2144272361;
    }
    else
    {
      v8 = v17;
      v19 = v17 == 0;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( v19 )
      {
LABEL_53:
        if ( pcbData - 8 > 0xFFF7 )
        {
          v8 = -2144272362;
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 )
            WPP_SF_d(v18[2], 44, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, 2150694934LL);
        }
        else
        {
          IsValidBounded = FveDatumIsValidBounded(pvData, pcbData, 0);
          v21 = FromNtStatus(IsValidBounded);
          v8 = v21;
          if ( !v21 )
            goto LABEL_59;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v21);
          if ( v8 >= 0 )
          {
LABEL_59:
            MustBe = FveDatumMustBe(pvData, 9);
            v23 = FromNtStatus(MustBe);
            v8 = v23;
            if ( !v23 )
              goto LABEL_64;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v23);
            if ( v8 >= 0 )
            {
LABEL_64:
              memcpy_0(a3, pvData, pcbData);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF__guid_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  47,
                  WPP_82fbf6316f983a090a97009b222379cf_Traceguids,
                  Guid);
            }
          }
        }
LABEL_70:
        CFveApiBase::ZeroFree(pvData, pcbData);
        goto LABEL_71;
      }
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 )
    {
      WPP_SF_d(v18[2], 43, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, (unsigned int)v8);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 < 0 )
      goto LABEL_70;
    goto LABEL_53;
  }
  v8 = -2147024882;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v10 = 40;
    goto LABEL_13;
  }
LABEL_71:
  RtlFreeUnicodeString(&GuidString);
  if ( v6 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180055d0c  mov     [rsp-8+arg_18], rbx
0x180055d11  push    rbp
0x180055d12  push    rsi
0x180055d13  push    rdi
0x180055d14  push    r12
0x180055d16  push    r13
0x180055d18  push    r14
0x180055d1a  push    r15
0x180055d1c  lea     rbp, [rsp-390h]
0x180055d24  sub     rsp, 490h
0x180055d2b  mov     rax, cs:__security_cookie
0x180055d32  xor     rax, rsp
0x180055d35  mov     [rbp+3C0h+var_40], rax
0x180055d3c  mov     r14, r8
0x180055d3f  mov     rsi, rdx
0x180055d42  mov     rbx, rcx
0x180055d45  mov     edi, 208h
0x180055d4a  mov     r8d, edi; Size
0x180055d4d  lea     rcx, [rbp+3C0h+SubKey]; void *
0x180055d54  xor     edx, edx; Val
0x180055d56  call    memset_0
0x180055d5b  xorps   xmm0, xmm0
0x180055d5e  mov     [rsp+4C0h+var_480], 0FFFFh
0x180055d66  xor     r15b, r15b
0x180055d69  lea     rcx, [rsp+4C0h+pszPathOut]; void *
0x180055d6e  mov     r8d, edi; Size
0x180055d71  xor     edx, edx; Val
0x180055d73  movups  xmmword ptr [rsp+4C0h+GuidString.Length], xmm0
0x180055d78  call    memset_0
0x180055d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d84  lea     r12, WPP_GLOBAL_Control
0x180055d8b  lea     r13, WPP_82fbf6316f983a090a97009b222379cf_Traceguids
0x180055d92  cmp     rcx, r12
0x180055d95  jz      short loc_180055DAE
0x180055d97  test    byte ptr [rcx+1Ch], 20h
0x180055d9b  jz      short loc_180055DAE
0x180055d9d  mov     rcx, [rcx+10h]
0x180055da1  mov     edx, 21h ; '!'
0x180055da6  mov     r8, r13
0x180055da9  call    WPP_SF_
0x180055dae  lea     r9, pszMore; "Windows\\System32\\Config\\SYSTEM"
0x180055db5  mov     r8, rbx; pszPathIn
0x180055db8  mov     edx, 104h; cchPathOut
0x180055dbd  lea     rcx, [rsp+4C0h+pszPathOut]; pszPathOut
0x180055dc2  call    cs:__imp_PathCchCombine
0x180055dc9  nop     dword ptr [rax+rax+00h]
0x180055dce  mov     ebx, eax
0x180055dd0  mov     dil, 40h ; '@'
0x180055dd3  test    eax, eax
0x180055dd5  jz      short loc_180055E05
0x180055dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180055dde  cmp     rcx, r12
0x180055de1  jz      short loc_180055DFD
0x180055de3  test    [rcx+1Ch], dil
0x180055de7  jz      short loc_180055DFD
0x180055de9  mov     rcx, [rcx+10h]
0x180055ded  mov     edx, 22h ; '"'
0x180055df2  mov     r9d, eax
0x180055df5  mov     r8, r13
0x180055df8  call    WPP_SF_d
0x180055dfd  test    ebx, ebx
0x180055dff  js      loc_1800561C2
0x180055e05  lea     rcx, [rsp+4C0h+pszPathOut]; lpFileName
0x180055e0a  call    cs:__imp_GetFileAttributesW
0x180055e11  nop     dword ptr [rax+rax+00h]
0x180055e16  cmp     eax, 0FFFFFFFFh
0x180055e19  jnz     short loc_180055E53
0x180055e1b  mov     ebx, 80070002h
0x180055e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e27  cmp     rcx, r12
0x180055e2a  jz      loc_1800561C2
0x180055e30  test    [rcx+1Ch], dil
0x180055e34  jz      loc_1800561C2
0x180055e3a  mov     edx, 23h ; '#'
0x180055e3f  mov     rcx, [rcx+10h]
0x180055e43  mov     r9d, ebx
0x180055e46  mov     r8, r13
0x180055e49  call    WPP_SF_d
0x180055e4e  jmp     loc_1800561C2
0x180055e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e5a  cmp     rcx, r12
0x180055e5d  jz      short loc_180055E7B
0x180055e5f  test    byte ptr [rcx+1Ch], 8
0x180055e63  jz      short loc_180055E7B
0x180055e65  mov     rcx, [rcx+10h]
0x180055e69  lea     r9, [rsp+4C0h+pszPathOut]
0x180055e6e  mov     edx, 24h ; '$'
0x180055e73  mov     r8, r13
0x180055e76  call    WPP_SF_S
0x180055e7b  lea     r8, [rsp+4C0h+pszPathOut]; lpFile
0x180055e80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055e87  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x180055e8e  call    cs:__imp_RegLoadKeyW
0x180055e95  nop     dword ptr [rax+rax+00h]
0x180055e9a  mov     ebx, eax
0x180055e9c  test    eax, eax
0x180055e9e  jle     short loc_180055EA9
0x180055ea0  movzx   ebx, ax
0x180055ea3  or      ebx, 80070000h
0x180055ea9  test    ebx, ebx
0x180055eab  jz      short loc_180055EDB
0x180055ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180055eb4  cmp     rcx, r12
0x180055eb7  jz      short loc_180055ED3
0x180055eb9  test    [rcx+1Ch], dil
0x180055ebd  jz      short loc_180055ED3
0x180055ebf  mov     rcx, [rcx+10h]
0x180055ec3  mov     edx, 25h ; '%'
0x180055ec8  mov     r9d, ebx
0x180055ecb  mov     r8, r13
0x180055ece  call    WPP_SF_d
0x180055ed3  test    ebx, ebx
0x180055ed5  js      loc_1800561C2
0x180055edb  lea     rdx, [rsp+4C0h+GuidString]; GuidString
0x180055ee0  mov     rcx, rsi; Guid
0x180055ee3  mov     r15b, 1
0x180055ee6  call    cs:__imp_RtlStringFromGUID
0x180055eed  nop     dword ptr [rax+rax+00h]
0x180055ef2  mov     ecx, eax; int
0x180055ef4  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180055ef9  mov     ebx, eax
0x180055efb  test    eax, eax
0x180055efd  jz      short loc_180055F2D
0x180055eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f06  cmp     rcx, r12
0x180055f09  jz      short loc_180055F25
0x180055f0b  test    [rcx+1Ch], dil
0x180055f0f  jz      short loc_180055F25
0x180055f11  mov     rcx, [rcx+10h]
0x180055f15  mov     edx, 26h ; '&'
0x180055f1a  mov     r9d, eax
0x180055f1d  mov     r8, r13
0x180055f20  call    WPP_SF_d
0x180055f25  test    ebx, ebx
0x180055f27  js      loc_1800561C2
0x180055f2d  lea     rax, [rsp+4C0h+GuidString]
0x180055f32  mov     edx, 104h; unsigned __int64
0x180055f37  mov     [rsp+4C0h+pvData], rax
0x180055f3c  lea     r9, aBitlockersyste; "BitLockerSystemRoot"
0x180055f43  lea     rax, aControlset001C; "ControlSet001\\Control\\FVEAutoUnlock"
0x180055f4a  lea     r8, aSSWz; "%s\\%s\\%wZ"
0x180055f51  mov     [rsp+4C0h+pdwType], rax
0x180055f56  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x180055f5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055f62  mov     ebx, eax
0x180055f64  test    eax, eax
0x180055f66  jz      short loc_180055F96
0x180055f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f6f  cmp     rcx, r12
0x180055f72  jz      short loc_180055F8E
0x180055f74  test    [rcx+1Ch], dil
0x180055f78  jz      short loc_180055F8E
0x180055f7a  mov     rcx, [rcx+10h]
0x180055f7e  mov     edx, 27h ; '''
0x180055f83  mov     r9d, eax
0x180055f86  mov     r8, r13
0x180055f89  call    WPP_SF_d
0x180055f8e  test    ebx, ebx
0x180055f90  js      loc_1800561C2
0x180055f96  mov     ecx, [rsp+4C0h+var_480]; unsigned __int64
0x180055f9a  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x180055f9f  mov     rdi, rax
0x180055fa2  test    rax, rax
0x180055fa5  jnz     short loc_180055FCE
0x180055fa7  mov     ebx, 8007000Eh
0x180055fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180055fb3  cmp     rcx, r12
0x180055fb6  jz      loc_1800561C2
0x180055fbc  test    byte ptr [rcx+1Ch], 40h
0x180055fc0  jz      loc_1800561C2
0x180055fc6  lea     edx, [rax+28h]
0x180055fc9  jmp     loc_180055E3F
0x180055fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180055fd5  cmp     rcx, r12
0x180055fd8  jz      short loc_180055FF8
0x180055fda  test    byte ptr [rcx+1Ch], 8
0x180055fde  jz      short loc_180055FF8
0x180055fe0  mov     rcx, [rcx+10h]
0x180055fe4  lea     r9, [rbp+3C0h+SubKey]
0x180055feb  mov     edx, 29h ; ')'
0x180055ff0  mov     r8, r13
0x180055ff3  call    WPP_SF_S
0x180055ff8  lea     rax, [rsp+4C0h+var_480]
0x180055ffd  mov     r9d, 8; dwFlags
0x180056003  mov     [rsp+4C0h+pcbData], rax; pcbData
0x180056008  lea     r8, aData_1; "Data"
0x18005600f  mov     [rsp+4C0h+pvData], rdi; pvData
0x180056014  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x18005601b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180056022  mov     [rsp+4C0h+pdwType], 0; pdwType
0x18005602b  call    cs:__imp_RegGetValueW
0x180056032  nop     dword ptr [rax+rax+00h]
0x180056037  mov     ecx, eax
0x180056039  test    eax, eax
0x18005603b  jle     short loc_180056046
0x18005603d  movzx   ecx, ax
0x180056040  or      ecx, 80070000h
0x180056046  mov     ebx, 80070002h
0x18005604b  cmp     ecx, ebx
0x18005604d  jnz     short loc_180056083
0x18005604f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056056  cmp     rcx, r12
0x180056059  jz      short loc_18005607C
0x18005605b  test    byte ptr [rcx+1Ch], 4
0x18005605f  jz      short loc_18005607C
0x180056061  mov     rcx, [rcx+10h]
0x180056065  mov     edx, 2Ah ; '*'
0x18005606a  mov     r9, rsi
0x18005606d  mov     r8, r13
0x180056070  call    WPP_SF__guid_
0x180056075  mov     rcx, cs:WPP_GLOBAL_Control
0x18005607c  mov     ebx, 80310017h
0x180056081  jmp     short loc_180056090
0x180056083  mov     ebx, ecx
0x180056085  test    ecx, ecx
0x180056087  mov     rcx, cs:WPP_GLOBAL_Control
0x18005608e  jz      short loc_1800560BE
0x180056090  cmp     rcx, r12
0x180056093  jz      short loc_1800560B6
0x180056095  test    byte ptr [rcx+1Ch], 40h
0x180056099  jz      short loc_1800560B6
0x18005609b  mov     rcx, [rcx+10h]
0x18005609f  mov     edx, 2Bh ; '+'
0x1800560a4  mov     r9d, ebx
0x1800560a7  mov     r8, r13
0x1800560aa  call    WPP_SF_d
0x1800560af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560b6  test    ebx, ebx
0x1800560b8  js      loc_1800561B6
0x1800560be  mov     edx, [rsp+4C0h+var_480]
0x1800560c2  lea     eax, [rdx-8]
0x1800560c5  cmp     eax, 0FFF7h
0x1800560ca  ja      loc_180056192
0x1800560d0  xor     r8d, r8d
0x1800560d3  mov     rcx, rdi
0x1800560d6  call    FveDatumIsValidBounded
0x1800560db  mov     ecx, eax; int
0x1800560dd  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800560e2  mov     ebx, eax
0x1800560e4  test    eax, eax
0x1800560e6  jz      short loc_180056116
0x1800560e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560ef  cmp     rcx, r12
0x1800560f2  jz      short loc_18005610E
0x1800560f4  test    byte ptr [rcx+1Ch], 40h
0x1800560f8  jz      short loc_18005610E
0x1800560fa  mov     rcx, [rcx+10h]
0x1800560fe  mov     edx, 2Dh ; '-'
0x180056103  mov     r9d, eax
0x180056106  mov     r8, r13
0x180056109  call    WPP_SF_d
0x18005610e  test    ebx, ebx
0x180056110  js      loc_1800561B6
0x180056116  mov     edx, 9
0x18005611b  mov     rcx, rdi
0x18005611e  call    FveDatumMustBe
0x180056123  mov     ecx, eax; int
0x180056125  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18005612a  mov     ebx, eax
0x18005612c  test    eax, eax
0x18005612e  jz      short loc_18005615A
0x180056130  mov     rcx, cs:WPP_GLOBAL_Control
0x180056137  cmp     rcx, r12
0x18005613a  jz      short loc_180056156
0x18005613c  test    byte ptr [rcx+1Ch], 40h
0x180056140  jz      short loc_180056156
0x180056142  mov     rcx, [rcx+10h]
0x180056146  mov     edx, 2Eh ; '.'
0x18005614b  mov     r9d, eax
0x18005614e  mov     r8, r13
0x180056151  call    WPP_SF_d
0x180056156  test    ebx, ebx
0x180056158  js      short loc_1800561B6
0x18005615a  mov     r8d, [rsp+4C0h+var_480]; Size
0x18005615f  mov     rdx, rdi; Src
0x180056162  mov     rcx, r14; void *
0x180056165  call    memcpy_0
0x18005616a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056171  cmp     rcx, r12
0x180056174  jz      short loc_1800561B6
0x180056176  test    byte ptr [rcx+1Ch], 8
0x18005617a  jz      short loc_1800561B6
0x18005617c  mov     rcx, [rcx+10h]
0x180056180  mov     edx, 2Fh ; '/'
0x180056185  mov     r9, rsi
0x180056188  mov     r8, r13
0x18005618b  call    WPP_SF__guid_
0x180056190  jmp     short loc_1800561B6
0x180056192  mov     ebx, 80310016h
0x180056197  cmp     rcx, r12
0x18005619a  jz      short loc_1800561B6
0x18005619c  test    byte ptr [rcx+1Ch], 40h
0x1800561a0  jz      short loc_1800561B6
0x1800561a2  mov     rcx, [rcx+10h]
0x1800561a6  mov     edx, 2Ch ; ','
0x1800561ab  mov     r9d, ebx
0x1800561ae  mov     r8, r13
0x1800561b1  call    WPP_SF_d
0x1800561b6  mov     edx, [rsp+4C0h+var_480]; unsigned __int64
0x1800561ba  mov     rcx, rdi; lpMem
  ... truncated ...
```
