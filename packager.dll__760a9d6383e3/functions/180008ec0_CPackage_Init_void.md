# CPackage::Init(void)

- ea: `0x180008ec0`
- end: `0x18000913b`
- name: `?Init@CPackage@@QEAAJXZ`
- size: `635`
- prototype: `__int64 __fastcall(CPackage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a760`

## callees

- `0x180008ec0`
- `0x18000a624`
- `0x18000cba6`
- `0x18000cbbe`
- `0x18000cbf0`

## import_xrefs

- `SHLWAPI!SHGetValueW` at `0x1800090ad`
- `SHLWAPI!SHGetValueW` at `0x1800090ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009008`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009008`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800090d6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800090d6`
- `ole32!CreateDataCache` at `0x18000910f`
- `ole32!CreateDataCache` at `0x18000910f`
- `USER32!RegisterClipboardFormatW` at `0x180009015`
- `USER32!RegisterClipboardFormatW` at `0x180009028`
- `USER32!RegisterClipboardFormatW` at `0x18000903b`
- `USER32!RegisterClipboardFormatW` at `0x18000904e`
- `USER32!RegisterClipboardFormatW` at `0x180009061`
- `USER32!RegisterClipboardFormatW` at `0x180009015`
- `USER32!RegisterClipboardFormatW` at `0x180009028`
- `USER32!RegisterClipboardFormatW` at `0x18000903b`
- `USER32!RegisterClipboardFormatW` at `0x18000904e`
- `USER32!RegisterClipboardFormatW` at `0x180009061`
- `USER32!GetSystemMetrics` at `0x180008f12`
- `USER32!GetSystemMetrics` at `0x180008f23`
- `USER32!GetSystemMetrics` at `0x180008f12`
- `USER32!GetSystemMetrics` at `0x180008f23`
- `USER32!SystemParametersInfoW` at `0x180008ef2`
- `USER32!SystemParametersInfoW` at `0x180008f07`
- `USER32!SystemParametersInfoW` at `0x180008f59`
- `USER32!SystemParametersInfoW` at `0x180008ef2`
- `USER32!SystemParametersInfoW` at `0x180008f07`
- `USER32!SystemParametersInfoW` at `0x180008f59`
- `GDI32!CreateFontIndirectW` at `0x180008fb2`
- `GDI32!CreateFontIndirectW` at `0x180008fb2`
- `GDI32!DeleteObject` at `0x180008fa8`
- `GDI32!DeleteObject` at `0x180008fa8`

## string_xrefs

- `0x18000901b`: `FileGroupDescriptorW`
- `0x18000902e`: `Object Descriptor`
- `0x180009078`: `AllowCommandLinePackages`

## pseudocode

```c
__int64 __fastcall CPackage::Init(CPackage *this)
{
  WCHAR *lfFaceName; // rax
  int v3; // r8d
  int v4; // edx
  HFONT v5; // rax
  HGLOBAL v6; // rax
  DWORD pdwType; // [rsp+30h] [rbp-29h] BYREF
  int pvData; // [rsp+34h] [rbp-25h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-21h] BYREF
  LOGFONTW pvParam; // [rsp+40h] [rbp-19h] BYREF

  SystemParametersInfoW(0xDu, 0, &g_cxArrange, 0);
  SystemParametersInfoW(0x18u, 0, &g_cyArrange, 0);
  g_cxIcon = GetSystemMetrics(11);
  g_cyIcon = GetSystemMetrics(12);
  memset_0(&pvParam, 0, sizeof(pvParam));
  AcquireSRWLockExclusive(&PackagerFontLock);
  SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
  if ( memcmp_0(&pvParam, &g_lfCachedFont, 0x1Cu) )
    goto LABEL_6;
  lfFaceName = pvParam.lfFaceName;
  do
  {
    v3 = *(WCHAR *)((char *)lfFaceName + (char *)&xmmword_180014890 + 12 - (char *)pvParam.lfFaceName);
    v4 = *lfFaceName - v3;
    if ( v4 )
      break;
    ++lfFaceName;
  }
  while ( v3 );
  if ( v4 )
  {
LABEL_6:
    DeleteObject(g_hfontTitle);
    v5 = CreateFontIndirectW(&pvParam);
    xmmword_180014890 = *(_OWORD *)&pvParam.lfWeight;
    *(_OWORD *)&g_lfCachedFont.lfHeight = *(_OWORD *)&pvParam.lfHeight;
    xmmword_1800148B0 = *(_OWORD *)&pvParam.lfFaceName[10];
    g_hfontTitle = v5;
    xmmword_1800148A0 = *(_OWORD *)&pvParam.lfFaceName[2];
    xmmword_1800148C0 = *(_OWORD *)&pvParam.lfFaceName[18];
    *(__int128 *)((char *)&xmmword_1800148C0 + 12) = *(_OWORD *)&pvParam.lfFaceName[24];
  }
  ReleaseSRWLockExclusive(&PackagerFontLock);
  g_cfFileContents = RegisterClipboardFormatW(L"FileContents");
  g_cfFileDescriptor = RegisterClipboardFormatW(L"FileGroupDescriptorW");
  g_cfObjectDescriptor = RegisterClipboardFormatW(L"Object Descriptor");
  g_cfEmbedSource = RegisterClipboardFormatW(L"Embed Source");
  pvData = 0;
  g_cfFileNameW = RegisterClipboardFormatW(L"FileNameW");
  pdwType = 0;
  pcbData = 4;
  if ( !SHGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Packager",
          L"AllowCommandLinePackages",
          &pdwType,
          &pvData,
          &pcbData)
    && pdwType == 4
    && pvData )
  {
    gCmdLineOK = 1;
  }
  v6 = GlobalAlloc(0x40u, 0x430u);
  *((_QWORD *)this + 12) = v6;
  if ( !v6 )
    return 2147942414LL;
  CPackage::_IconRefresh((HICON **)this);
  CreateDataCache(
    (LPUNKNOWN)(((unsigned __int64)this + 16) & -(__int64)(this != 0)),
    &GUID_NULL,
    &GUID_00000000_0000_0000_c000_000000000046,
    (LPVOID *)this + 33);
  return 0;
}

```

## disassembly

```asm
0x180008ec0  mov     [rsp-8+arg_8], rbx
0x180008ec5  push    rbp
0x180008ec6  lea     rbp, [rsp-57h]
0x180008ecb  sub     rsp, 0B0h
0x180008ed2  mov     rax, cs:__security_cookie
0x180008ed9  xor     rax, rsp
0x180008edc  mov     [rbp+57h+var_10], rax
0x180008ee0  xor     edx, edx; uiParam
0x180008ee2  lea     r8, ?g_cxArrange@@3HA; pvParam
0x180008ee9  mov     rbx, rcx
0x180008eec  xor     r9d, r9d; fWinIni
0x180008eef  lea     ecx, [rdx+0Dh]; uiAction
0x180008ef2  call    cs:__imp_SystemParametersInfoW
0x180008ef8  xor     edx, edx; uiParam
0x180008efa  lea     r8, ?g_cyArrange@@3HA; pvParam
0x180008f01  xor     r9d, r9d; fWinIni
0x180008f04  lea     ecx, [rdx+18h]; uiAction
0x180008f07  call    cs:__imp_SystemParametersInfoW
0x180008f0d  mov     ecx, 0Bh; nIndex
0x180008f12  call    cs:__imp_GetSystemMetrics
0x180008f18  mov     ecx, 0Ch; nIndex
0x180008f1d  mov     cs:?g_cxIcon@@3HA, eax; int g_cxIcon
0x180008f23  call    cs:__imp_GetSystemMetrics
0x180008f29  xor     edx, edx; Val
0x180008f2b  lea     rcx, [rbp+57h+pvParam]; void *
0x180008f2f  mov     cs:?g_cyIcon@@3HA, eax; int g_cyIcon
0x180008f35  lea     r8d, [rdx+5Ch]; Size
0x180008f39  call    memset_0
0x180008f3e  lea     rcx, ?PackagerFontLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180008f45  call    cs:__imp_AcquireSRWLockExclusive
0x180008f4b  xor     r9d, r9d; fWinIni
0x180008f4e  lea     r8, [rbp+57h+pvParam]; pvParam
0x180008f52  lea     edx, [r9+5Ch]; uiParam
0x180008f56  lea     ecx, [rdx-3Dh]; uiAction
0x180008f59  call    cs:__imp_SystemParametersInfoW
0x180008f5f  mov     r8d, 1Ch; Size
0x180008f65  lea     rdx, ?g_lfCachedFont@@3UtagLOGFONTW@@A; Buf2
0x180008f6c  lea     rcx, [rbp+57h+pvParam]; Buf1
0x180008f70  call    memcmp_0
0x180008f75  test    eax, eax
0x180008f77  jnz     short loc_180008FA1
0x180008f79  lea     rax, [rbp+57h+var_54]
0x180008f7d  lea     rcx, xmmword_180014890+0Ch
0x180008f84  sub     rcx, rax
0x180008f87  movzx   edx, word ptr [rax]
0x180008f8a  movzx   r8d, word ptr [rax+rcx]
0x180008f8f  sub     edx, r8d
0x180008f92  jnz     short loc_180008F9D
0x180008f94  add     rax, 2
0x180008f98  test    r8d, r8d
0x180008f9b  jnz     short loc_180008F87
0x180008f9d  test    edx, edx
0x180008f9f  jz      short loc_180009001
0x180008fa1  mov     rcx, cs:?g_hfontTitle@@3PEAUHFONT__@@EA; ho
0x180008fa8  call    cs:__imp_DeleteObject
0x180008fae  lea     rcx, [rbp+57h+pvParam]; lplf
0x180008fb2  call    cs:__imp_CreateFontIndirectW
0x180008fb8  movaps  xmm1, xmmword ptr [rbp-9]
0x180008fbc  movaps  xmm0, [rbp+57h+pvParam]
0x180008fc0  movaps  cs:xmmword_180014890, xmm1
0x180008fc7  movaps  xmm1, [rbp+57h+var_40]
0x180008fcb  movaps  cs:?g_lfCachedFont@@3UtagLOGFONTW@@A, xmm0; tagLOGFONTW g_lfCachedFont
0x180008fd2  movaps  xmm0, [rbp+57h+var_50]
0x180008fd6  movaps  cs:xmmword_1800148B0, xmm1
0x180008fdd  movups  xmm1, [rbp+57h+var_24]
0x180008fe1  mov     cs:?g_hfontTitle@@3PEAUHFONT__@@EA, rax; HFONT__ * g_hfontTitle
0x180008fe8  movaps  cs:xmmword_1800148A0, xmm0
0x180008fef  movaps  xmm0, xmmword ptr [rbp+27h]
0x180008ff3  movaps  cs:xmmword_1800148C0, xmm0
0x180008ffa  movups  cs:xmmword_1800148C0+0Ch, xmm1
0x180009001  lea     rcx, ?PackagerFontLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180009008  call    cs:__imp_ReleaseSRWLockExclusive
0x18000900e  lea     rcx, szFormat; "FileContents"
0x180009015  call    cs:__imp_RegisterClipboardFormatW
0x18000901b  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x180009022  mov     cs:?g_cfFileContents@@3IA, eax; uint g_cfFileContents
0x180009028  call    cs:__imp_RegisterClipboardFormatW
0x18000902e  lea     rcx, aObjectDescript; "Object Descriptor"
0x180009035  mov     cs:?g_cfFileDescriptor@@3IA, eax; uint g_cfFileDescriptor
0x18000903b  call    cs:__imp_RegisterClipboardFormatW
0x180009041  lea     rcx, aEmbedSource; "Embed Source"
0x180009048  mov     cs:?g_cfObjectDescriptor@@3IA, eax; uint g_cfObjectDescriptor
0x18000904e  call    cs:__imp_RegisterClipboardFormatW
0x180009054  lea     rcx, aFilenamew; "FileNameW"
0x18000905b  mov     cs:?g_cfEmbedSource@@3IA, eax; uint g_cfEmbedSource
0x180009061  call    cs:__imp_RegisterClipboardFormatW
0x180009067  lea     r9, [rbp+57h+pdwType]; pdwType
0x18000906b  mov     [rbp+57h+var_7C], 0
0x180009072  mov     cs:?g_cfFileNameW@@3IA, eax; uint g_cfFileNameW
0x180009078  lea     r8, pszValue; "AllowCommandLinePackages"
0x18000907f  lea     rax, [rbp+57h+var_78]
0x180009083  mov     [rbp+57h+pdwType], 0
0x18000908a  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18000908f  lea     rdx, pszSubKey; "Software\\Policies\\Microsoft\\Packager"
0x180009096  lea     rax, [rbp+57h+var_7C]
0x18000909a  mov     [rbp+57h+var_78], 4
0x1800090a1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800090a8  mov     [rsp+0B0h+pvData], rax; pvData
0x1800090ad  call    cs:__imp_SHGetValueW
0x1800090b3  test    eax, eax
0x1800090b5  jnz     short loc_1800090CC
0x1800090b7  cmp     [rbp+57h+pdwType], 4
0x1800090bb  jnz     short loc_1800090CC
0x1800090bd  cmp     [rbp+57h+var_7C], eax
0x1800090c0  jz      short loc_1800090CC
0x1800090c2  mov     cs:?gCmdLineOK@@3HA, 1; int gCmdLineOK
0x1800090cc  mov     edx, 430h; dwBytes
0x1800090d1  mov     ecx, 40h ; '@'; uFlags
0x1800090d6  call    cs:__imp_GlobalAlloc
0x1800090dc  mov     [rbx+60h], rax
0x1800090e0  test    rax, rax
0x1800090e3  jz      short loc_180009119
0x1800090e5  mov     rcx, rbx; this
0x1800090e8  call    ?_IconRefresh@CPackage@@IEAAJXZ; CPackage::_IconRefresh(void)
0x1800090ed  lea     rax, [rbx+10h]
0x1800090f1  lea     r9, [rbx+108h]; ppv
0x1800090f8  neg     rbx
0x1800090fb  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180009102  sbb     rcx, rcx
0x180009105  lea     rdx, GUID_NULL; rclsid
0x18000910c  and     rcx, rax; pUnkOuter
0x18000910f  call    cs:__imp_CreateDataCache
0x180009115  xor     eax, eax
0x180009117  jmp     short loc_18000911E
0x180009119  mov     eax, 8007000Eh
0x18000911e  mov     rcx, [rbp+57h+var_10]
0x180009122  xor     rcx, rsp; StackCookie
0x180009125  call    __security_check_cookie
0x18000912a  mov     rbx, [rsp+0B0h+arg_8]
0x180009132  add     rsp, 0B0h
0x180009139  pop     rbp
0x18000913a  retn
```
