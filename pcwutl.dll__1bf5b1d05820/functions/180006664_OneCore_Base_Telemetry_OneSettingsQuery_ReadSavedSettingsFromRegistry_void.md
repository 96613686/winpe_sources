# OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)

- ea: `0x180006664`
- end: `0x18000692d`
- name: `?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `713`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800055f4`

## callees

- `0x180002c04`
- `0x180003094`
- `0x180006664`
- `0x180007b54`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800068e9`
- `ADVAPI32!RegCloseKey` at `0x1800068e9`
- `ADVAPI32!RegEnumValueW` at `0x1800068bd`
- `ADVAPI32!RegEnumValueW` at `0x1800068bd`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000681e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000681e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000674b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000674b`
- `KERNEL32!HeapAlloc` at `0x180006841`
- `KERNEL32!HeapAlloc` at `0x180006841`
- `KERNEL32!GetProcessHeap` at `0x1800067bd`
- `KERNEL32!GetProcessHeap` at `0x180006832`
- `KERNEL32!GetProcessHeap` at `0x1800068f4`
- `KERNEL32!GetProcessHeap` at `0x1800067bd`
- `KERNEL32!GetProcessHeap` at `0x180006832`
- `KERNEL32!GetProcessHeap` at `0x1800068f4`
- `KERNEL32!HeapFree` at `0x180006788`
- `KERNEL32!HeapFree` at `0x1800067a9`
- `KERNEL32!HeapFree` at `0x180006902`
- `KERNEL32!HeapFree` at `0x180006788`
- `KERNEL32!HeapFree` at `0x1800067a9`
- `KERNEL32!HeapFree` at `0x180006902`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  char *v1; // r14
  char *v2; // r12
  char *v3; // r15
  BYTE *v5; // rsi
  signed int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // cc
  int v9; // ebx
  RtlNameValueArray *v10; // rdi
  void *v11; // r8
  void *v12; // r8
  HANDLE ProcessHeap; // rax
  HKEY v14; // rcx
  DWORD v15; // ebx
  HANDLE v16; // rax
  int v17; // r14d
  DWORD i; // edx
  LSTATUS v19; // eax
  HANDLE v20; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  v1 = (char *)this + 560;
  v2 = (char *)this + 1080;
  v3 = (char *)this + 40;
  cchValueName = 0;
  cbData = 0;
  cbMaxValueLen = 0;
  Type = 0;
  hKey = 0;
  v5 = 0;
  v6 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", (char *)this + 1080, (char *)this + 40, (char *)this + 560);
  if ( v6 >= 0 )
  {
    v6 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls\\%ls", v2, v3, v1, L"Settings");
    if ( v6 >= 0 )
    {
      v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v6 = v7;
      v8 = v7 <= 0;
      if ( v7 )
        goto LABEL_4;
      v10 = (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608);
      RtlNameValueArray::Clear(v10);
      v11 = (void *)*((_QWORD *)v10 + 5);
      if ( v11 )
        HeapFree(*(HANDLE *)v10, 0, v11);
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_OWORD *)v10 + 2) = 0;
      v12 = (void *)*((_QWORD *)v10 + 5);
      if ( v12 )
        HeapFree(0, 0, v12);
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_OWORD *)v10 + 2) = 0;
      ProcessHeap = GetProcessHeap();
      v14 = hKey;
      *(_QWORD *)v10 = ProcessHeap;
      *((_QWORD *)v10 + 4) = 16;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 1) = 8;
      v7 = RegQueryInfoKeyW(v14, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
      v6 = v7;
      v8 = v7 <= 0;
      if ( v7 )
      {
LABEL_4:
        if ( v8 )
          goto LABEL_22;
        v9 = (unsigned __int16)v7;
        goto LABEL_6;
      }
      v15 = cbMaxValueLen;
      v16 = GetProcessHeap();
      v5 = (BYTE *)HeapAlloc(v16, 8u, v15);
      if ( !v5 )
      {
        v6 = -2147024882;
        goto LABEL_22;
      }
      v17 = 1;
      for ( i = 0; ; i = v17++ )
      {
        cbData = cbMaxValueLen;
        cchValueName = 260;
        v19 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, v5, &cbData);
        v6 = v19;
        if ( v19 )
          break;
        v6 = RtlNameValueArray::Append(v10, ValueName, (const unsigned __int16 *)v5);
        if ( v6 < 0 )
          goto LABEL_22;
      }
      if ( v19 == 259 )
      {
        v6 = 0;
      }
      else if ( v19 > 0 )
      {
        v9 = (unsigned __int16)v19;
LABEL_6:
        v6 = v9 | 0x80070000;
      }
    }
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006664  push    rbp
0x180006666  push    rbx
0x180006667  push    rsi
0x180006668  push    rdi
0x180006669  push    r12
0x18000666b  push    r13
0x18000666d  push    r14
0x18000666f  push    r15
0x180006671  lea     rbp, [rsp-3B8h]
0x180006679  sub     rsp, 4B8h
0x180006680  mov     rax, cs:__security_cookie
0x180006687  xor     rax, rsp
0x18000668a  mov     [rbp+3F0h+var_50], rax
0x180006691  xor     r13d, r13d
0x180006694  lea     r14, [rcx+230h]
0x18000669b  lea     r12, [rcx+438h]
0x1800066a2  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x1800066a7  lea     r15, [rcx+28h]
0x1800066ab  mov     [rsp+4F0h+cchValueName], r13d
0x1800066b0  mov     rdi, rcx
0x1800066b3  mov     [rsp+4F0h+phkResult], r15
0x1800066b8  mov     r9, r12
0x1800066bb  mov     [rsp+4F0h+cbData], r13d
0x1800066c0  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x1800066c7  mov     [rsp+4F0h+cbMaxValueLen], r13d
0x1800066cc  mov     edx, 104h; unsigned __int64
0x1800066d1  mov     [rsp+4F0h+Type], r13d
0x1800066d6  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x1800066da  mov     [rsp+4F0h+hKey], r13
0x1800066df  mov     esi, r13d
0x1800066e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800066e7  mov     ebx, eax
0x1800066e9  test    eax, eax
0x1800066eb  js      loc_1800068DF
0x1800066f1  lea     rax, SubKey; "Settings"
0x1800066f8  mov     r9, r12
0x1800066fb  mov     [rsp+4F0h+lpcbMaxClassLen], rax
0x180006700  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x180006707  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x18000670c  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x180006710  mov     [rsp+4F0h+phkResult], r15
0x180006715  mov     r15d, 104h
0x18000671b  mov     edx, r15d; unsigned __int64
0x18000671e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006723  mov     ebx, eax
0x180006725  test    eax, eax
0x180006727  js      loc_1800068DF
0x18000672d  lea     rax, [rsp+4F0h+hKey]
0x180006732  mov     r9d, 20019h; samDesired
0x180006738  xor     r8d, r8d; ulOptions
0x18000673b  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180006740  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180006744  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000674b  call    cs:__imp_RegOpenKeyExW
0x180006751  mov     ebx, eax
0x180006753  test    eax, eax
0x180006755  jz      short loc_18000676B
0x180006757  jle     loc_1800068DF
0x18000675d  movzx   ebx, ax
0x180006760  or      ebx, 80070000h
0x180006766  jmp     loc_1800068DF
0x18000676b  add     rdi, 648h
0x180006772  mov     rcx, rdi; this
0x180006775  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x18000677a  mov     r8, [rdi+28h]; lpMem
0x18000677e  test    r8, r8
0x180006781  jz      short loc_18000678E
0x180006783  mov     rcx, [rdi]; hHeap
0x180006786  xor     edx, edx; dwFlags
0x180006788  call    cs:__imp_HeapFree
0x18000678e  xorps   xmm0, xmm0
0x180006791  movups  xmmword ptr [rdi], xmm0
0x180006794  movups  xmmword ptr [rdi+10h], xmm0
0x180006798  movups  xmmword ptr [rdi+20h], xmm0
0x18000679c  mov     r8, [rdi+28h]; lpMem
0x1800067a0  test    r8, r8
0x1800067a3  jz      short loc_1800067AF
0x1800067a5  xor     edx, edx; dwFlags
0x1800067a7  xor     ecx, ecx; hHeap
0x1800067a9  call    cs:__imp_HeapFree
0x1800067af  xorps   xmm0, xmm0
0x1800067b2  movups  xmmword ptr [rdi], xmm0
0x1800067b5  movups  xmmword ptr [rdi+10h], xmm0
0x1800067b9  movups  xmmword ptr [rdi+20h], xmm0
0x1800067bd  call    cs:__imp_GetProcessHeap
0x1800067c3  mov     rcx, [rsp+4F0h+hKey]; hKey
0x1800067c8  mov     r14d, 8
0x1800067ce  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800067d3  xor     r9d, r9d; lpReserved
0x1800067d6  mov     [rsp+4F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800067db  xor     r8d, r8d; lpcchClass
0x1800067de  mov     [rdi], rax
0x1800067e1  xor     edx, edx; lpClass
0x1800067e3  lea     rax, [rsp+4F0h+cbMaxValueLen]
0x1800067e8  mov     qword ptr [rdi+20h], 10h
0x1800067f0  mov     [rsp+4F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800067f5  mov     [rsp+4F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800067fa  mov     [rsp+4F0h+lpcValues], r13; lpcValues
0x1800067ff  mov     [rsp+4F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180006804  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180006809  mov     [rsp+4F0h+phkResult], r13; lpcSubKeys
0x18000680e  mov     [rdi+10h], r13
0x180006812  mov     [rdi+18h], r13
0x180006816  mov     [rdi+28h], r13
0x18000681a  mov     [rdi+8], r14
0x18000681e  call    cs:__imp_RegQueryInfoKeyW
0x180006824  mov     ebx, eax
0x180006826  test    eax, eax
0x180006828  jnz     loc_180006757
0x18000682e  mov     ebx, [rsp+4F0h+cbMaxValueLen]
0x180006832  call    cs:__imp_GetProcessHeap
0x180006838  mov     r8d, ebx; dwBytes
0x18000683b  mov     edx, r14d; dwFlags
0x18000683e  mov     rcx, rax; hHeap
0x180006841  call    cs:__imp_HeapAlloc
0x180006847  mov     rsi, rax
0x18000684a  test    rax, rax
0x18000684d  jnz     short loc_180006859
0x18000684f  mov     ebx, 8007000Eh
0x180006854  jmp     loc_1800068DF
0x180006859  mov     r14d, 1
0x18000685f  xor     edx, edx
0x180006861  jmp     short loc_180006881
0x180006863  mov     r8, rsi; unsigned __int16 *
0x180006866  lea     rdx, [rbp+3F0h+ValueName]; unsigned __int16 *
0x18000686d  mov     rcx, rdi; this
0x180006870  call    ?Append@RtlNameValueArray@@QEAAKPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x180006875  mov     ebx, eax
0x180006877  test    eax, eax
0x180006879  js      short loc_1800068DF
0x18000687b  mov     edx, r14d; dwIndex
0x18000687e  inc     r14d
0x180006881  mov     eax, [rsp+4F0h+cbMaxValueLen]
0x180006885  lea     r9, [rsp+4F0h+cchValueName]; lpcchValueName
0x18000688a  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18000688f  lea     r8, [rbp+3F0h+ValueName]; lpValueName
0x180006896  mov     [rsp+4F0h+cbData], eax
0x18000689a  lea     rax, [rsp+4F0h+cbData]
0x18000689f  mov     [rsp+4F0h+lpcValues], rax; lpcbData
0x1800068a4  lea     rax, [rsp+4F0h+Type]
0x1800068a9  mov     [rsp+4F0h+lpcbMaxClassLen], rsi; lpData
0x1800068ae  mov     [rsp+4F0h+lpcbMaxSubKeyLen], rax; lpType
0x1800068b3  mov     [rsp+4F0h+phkResult], r13; lpReserved
0x1800068b8  mov     [rsp+4F0h+cchValueName], r15d
0x1800068bd  call    cs:__imp_RegEnumValueW
0x1800068c3  mov     ebx, eax
0x1800068c5  test    eax, eax
0x1800068c7  jz      short loc_180006863
0x1800068c9  cmp     eax, 103h
0x1800068ce  jz      short loc_1800068DC
0x1800068d0  test    eax, eax
0x1800068d2  jle     short loc_1800068DF
0x1800068d4  movzx   ebx, bx
0x1800068d7  jmp     loc_180006760
0x1800068dc  mov     ebx, r13d
0x1800068df  mov     rcx, [rsp+4F0h+hKey]; hKey
0x1800068e4  test    rcx, rcx
0x1800068e7  jz      short loc_1800068EF
0x1800068e9  call    cs:__imp_RegCloseKey
0x1800068ef  test    rsi, rsi
0x1800068f2  jz      short loc_180006908
0x1800068f4  call    cs:__imp_GetProcessHeap
0x1800068fa  mov     r8, rsi; lpMem
0x1800068fd  xor     edx, edx; dwFlags
0x1800068ff  mov     rcx, rax; hHeap
0x180006902  call    cs:__imp_HeapFree
0x180006908  mov     eax, ebx
0x18000690a  mov     rcx, [rbp+3F0h+var_50]
0x180006911  xor     rcx, rsp; StackCookie
0x180006914  call    __security_check_cookie
0x180006919  add     rsp, 4B8h
0x180006920  pop     r15
0x180006922  pop     r14
0x180006924  pop     r13
0x180006926  pop     r12
0x180006928  pop     rdi
0x180006929  pop     rsi
0x18000692a  pop     rbx
0x18000692b  pop     rbp
0x18000692c  retn
```
