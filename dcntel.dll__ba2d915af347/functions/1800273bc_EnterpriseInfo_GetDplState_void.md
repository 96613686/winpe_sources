# EnterpriseInfo::GetDplState(void)

- ea: `0x1800273bc`
- end: `0x180027950`
- name: `?GetDplState@EnterpriseInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a110`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x18001286c`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x180019324`
- `0x1800220b4`
- `0x1800273bc`
- `0x18002b470`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800274b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002757e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800274b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002757e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002752f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002752f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027619`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002765f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800276ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027619`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002765f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800276ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800275dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800275dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseInfo::GetDplState(__int64 a1)
{
  DWORD v2; // ebx
  int v3; // r14d
  int v4; // esi
  int v5; // r13d
  HKEY v6; // rcx
  DWORD v7; // r12d
  __int64 v8; // r8
  __int64 v10; // rdi
  char *v11; // rbx
  char *v12; // rbx
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  char *v15; // r9
  __int64 v16; // rcx
  char *v17; // r9
  __int64 v18; // rax
  char *v19; // r9
  __int64 v20; // rax
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v26; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v29; // [rsp+70h] [rbp-90h] BYREF
  DWORD v30; // [rsp+74h] [rbp-8Ch] BYREF
  BYTE v31[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  _OWORD v34[2]; // [rsp+90h] [rbp-70h] BYREF
  char *Src[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR v38[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  WCHAR v39[264]; // [rsp+700h] [rbp+600h] BYREF

  v32 = a1;
  v33 = a1;
  v2 = 0;
  cchName = 260;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  phkResult = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  hKey = 0;
  v7 = 0;
  v26 = 260;
  *(_DWORD *)Data = 0;
  cbData = 4;
  *(_DWORD *)v31 = 0;
  v30 = 4;
  *(_DWORD *)v23 = 0;
  v29 = 4;
  while ( 1 )
  {
    if ( v6 )
    {
      RegCloseKey(v6);
      phkResult = 0;
    }
    cchName = 260;
    if ( RegEnumKeyExW(HKEY_USERS, v2, Name, &cchName, 0, 0, 0, 0) )
      break;
    ++v2;
    if ( (int)StringCchPrintfW(
                SubKey,
                0x104u,
                L"%s\\%s",
                Name,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\EdpCredentials") >= 0
      && !RegOpenKeyExW(HKEY_USERS, SubKey, 0, 8u, &phkResult) )
    {
      while ( 1 )
      {
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        v26 = 260;
        if ( RegEnumKeyExW(phkResult, v7++, v38, &v26, 0, 0, 0, 0) )
          break;
        if ( (int)StringCchPrintfW(v39, 0x104u, L"%s\\%s", SubKey, v38) >= 0
          && !RegOpenKeyExW(HKEY_USERS, v39, 0, 1u, &hKey) )
        {
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"ConsumerCredential", 0, 0, Data, &cbData) )
          {
            if ( *(_DWORD *)Data )
            {
              v29 = 4;
              if ( !RegQueryValueExW(hKey, L"ConsumerCredentialLevel", 0, 0, v23, &v29) )
              {
                if ( *(_DWORD *)v23 == 1 )
                {
                  v3 = 1;
                }
                else if ( *(_DWORD *)v23 == 2 )
                {
                  v4 = 1;
                }
                v30 = 4;
                if ( !RegQueryValueExW(hKey, L"CDplEnforced", 0, 0, v31, &v30) && *(_DWORD *)v31 == 1 )
                  v5 = 1;
              }
            }
          }
        }
      }
    }
    v6 = phkResult;
  }
  v10 = v32;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v3 )
  {
    if ( *(_QWORD *)(v10 + 24) < 0xEu )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v10,
        0xEu,
        v8,
        L"DPL_PRESENT_L1");
    }
    else
    {
      v12 = *(char **)v10;
      *(_QWORD *)(v10 + 16) = 14;
      memmove_0(v12, L"DPL_PRESENT_L1", 0x1Cu);
      *((_WORD *)v12 + 14) = 0;
    }
  }
  else if ( !v4 )
  {
    if ( *(_QWORD *)(v10 + 24) < 8u )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v10,
        8u,
        v8,
        L"DPL_NONE");
    }
    else
    {
      v11 = *(char **)v10;
      *(_QWORD *)(v10 + 16) = 8;
      memmove_0(v11, L"DPL_NONE", 0x10u);
      *((_WORD *)v11 + 8) = 0;
    }
    return v10;
  }
  v13 = L"|";
  if ( v4 == 1 )
  {
    if ( v3 == 1 )
    {
      v14 = *(_QWORD *)(v10 + 16);
      if ( 0x7FFFFFFFFFFFFFFELL == v14 )
        goto LABEL_55;
      if ( *(_QWORD *)(v10 + 24) <= 7u )
        v15 = (char *)v10;
      else
        v15 = *(char **)v10;
      std::wstring::wstring(v34, L"|", v8, v15, v14, L"|", 1);
      std::wstring::operator=(v10, v34);
      std::wstring::~wstring((char **)v34);
    }
    v16 = *(_QWORD *)(v10 + 16);
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v16) >= 0xE )
    {
      if ( *(_QWORD *)(v10 + 24) <= 7u )
        v17 = (char *)v10;
      else
        v17 = *(char **)v10;
      std::wstring::wstring(v34, v13, v8, v17, v16, L"DPL_PRESENT_L2", 14);
      std::wstring::operator=(v10, v34);
      std::wstring::~wstring((char **)v34);
      goto LABEL_47;
    }
LABEL_55:
    std::_Xlen_string();
  }
LABEL_47:
  if ( v5 )
  {
    v18 = *(_QWORD *)(v10 + 16);
    if ( 0x7FFFFFFFFFFFFFFELL == v18 )
      std::_Xlen_string();
    if ( *(_QWORD *)(v10 + 24) <= 7u )
      v19 = (char *)v10;
    else
      v19 = *(char **)v10;
    std::wstring::wstring(Src, L"|", v8, v19, v18, L"|", 1);
    v20 = std::wstring::append(Src, L"DPL_ENABLED");
    v34[0] = *(_OWORD *)v20;
    v34[1] = *(_OWORD *)(v20 + 16);
    *(_QWORD *)(v20 + 16) = 0;
    *(_QWORD *)(v20 + 24) = 7;
    *(_WORD *)v20 = 0;
    std::wstring::operator=(v10, v34);
    std::wstring::~wstring((char **)v34);
    std::wstring::~wstring(Src);
  }
  return v10;
}

```

## disassembly

```asm
0x1800273bc  push    rbp
0x1800273be  push    rbx
0x1800273bf  push    rsi
0x1800273c0  push    rdi
0x1800273c1  push    r12
0x1800273c3  push    r13
0x1800273c5  push    r14
0x1800273c7  push    r15
0x1800273c9  lea     rbp, [rsp-828h]
0x1800273d1  sub     rsp, 928h
0x1800273d8  mov     rax, cs:__security_cookie
0x1800273df  xor     rax, rsp
0x1800273e2  mov     [rbp+860h+var_50], rax
0x1800273e9  mov     rdi, rcx
0x1800273ec  mov     [rbp+860h+var_8E0], rcx
0x1800273f0  mov     [rbp+860h+var_8D8], rcx
0x1800273f4  mov     [rsp+960h+var_920], 1
0x1800273fc  xor     ebx, ebx
0x1800273fe  mov     [rsp+960h+cchName], 104h
0x180027406  xor     r14d, r14d
0x180027409  xor     esi, esi
0x18002740b  xor     r13d, r13d
0x18002740e  xor     ecx, ecx; hKey
0x180027410  mov     [rsp+960h+phkResult], rcx
0x180027415  xorps   xmm0, xmm0
0x180027418  movups  xmmword ptr [rdi], xmm0
0x18002741b  mov     [rdi+10h], rcx
0x18002741f  mov     qword ptr [rdi+18h], 7
0x180027427  xor     eax, eax
0x180027429  mov     [rdi], ax
0x18002742c  lea     edi, [rbx+1]
0x18002742f  mov     r15d, edi
0x180027432  mov     [rsp+960h+var_920], edi
0x180027436  mov     [rsp+960h+hKey], rax
0x18002743b  xor     r12d, r12d
0x18002743e  mov     [rsp+960h+var_8FC], 104h
0x180027446  mov     dword ptr [rsp+960h+Data], r12d
0x18002744b  lea     eax, [rbx+4]
0x18002744e  mov     [rsp+960h+cbData], eax
0x180027452  mov     dword ptr [rsp+960h+var_8E8], r12d
0x180027457  mov     [rsp+960h+var_8EC], eax
0x18002745b  mov     dword ptr [rsp+960h+var_910], r12d
0x180027460  mov     [rsp+960h+var_8F0], eax
0x180027464  test    rcx, rcx
0x180027467  jz      short loc_180027478
0x180027469  call    cs:__imp_RegCloseKey
0x18002746f  mov     [rsp+960h+phkResult], 0
0x180027478  mov     [rsp+960h+cchName], 104h
0x180027480  mov     [rsp+960h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180027489  mov     [rsp+960h+lpcchClass], 0; lpcchClass
0x180027492  mov     [rsp+960h+lpClass], 0; lpClass
0x18002749b  mov     [rsp+960h+lpReserved], 0; lpReserved
0x1800274a4  lea     r9, [rsp+960h+cchName]; lpcchName
0x1800274a9  lea     r8, [rbp+860h+Name]; lpName
0x1800274b0  mov     edx, ebx; dwIndex
0x1800274b2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800274b9  call    cs:__imp_RegEnumKeyExW
0x1800274bf  test    eax, eax
0x1800274c1  jnz     loc_1800276D8
0x1800274c7  add     ebx, edi
0x1800274c9  lea     rax, aSoftwareMicros_60; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800274d0  mov     [rsp+960h+lpReserved], rax
0x1800274d5  lea     r9, [rbp+860h+Name]
0x1800274dc  lea     r8, aSS_1; "%s\\%s"
0x1800274e3  mov     edx, 104h; unsigned __int64
0x1800274e8  lea     rcx, [rbp+860h+SubKey]; unsigned __int16 *
0x1800274ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800274f1  test    eax, eax
0x1800274f3  js      loc_1800276CE
0x1800274f9  lea     rax, [rsp+960h+phkResult]
0x1800274fe  mov     [rsp+960h+lpReserved], rax; phkResult
0x180027503  mov     r9d, 8; samDesired
0x180027509  xor     r8d, r8d; ulOptions
0x18002750c  lea     rdx, [rbp+860h+SubKey]; lpSubKey
0x180027510  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180027517  call    cs:__imp_RegOpenKeyExW
0x18002751d  test    eax, eax
0x18002751f  jnz     loc_1800276CE
0x180027525  mov     rcx, [rsp+960h+hKey]; hKey
0x18002752a  test    rcx, rcx
0x18002752d  jz      short loc_18002753E
0x18002752f  call    cs:__imp_RegCloseKey
0x180027535  mov     [rsp+960h+hKey], 0
0x18002753e  mov     [rsp+960h+var_8FC], 104h
0x180027546  mov     [rsp+960h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002754f  mov     [rsp+960h+lpcchClass], 0; lpcchClass
0x180027558  mov     [rsp+960h+lpClass], 0; lpClass
0x180027561  mov     [rsp+960h+lpReserved], 0; lpReserved
0x18002756a  lea     r9, [rsp+960h+var_8FC]; lpcchName
0x18002756f  lea     r8, [rbp+860h+var_470]; lpName
0x180027576  mov     edx, r12d; dwIndex
0x180027579  mov     rcx, [rsp+960h+phkResult]; hKey
0x18002757e  call    cs:__imp_RegEnumKeyExW
0x180027584  add     r12d, edi
0x180027587  test    eax, eax
0x180027589  jnz     loc_1800276CE
0x18002758f  lea     rax, [rbp+860h+var_470]
0x180027596  mov     [rsp+960h+lpReserved], rax
0x18002759b  lea     r9, [rbp+860h+SubKey]
0x18002759f  lea     r8, aSS_1; "%s\\%s"
0x1800275a6  mov     edx, 104h; unsigned __int64
0x1800275ab  lea     rcx, [rbp+860h+var_260]; unsigned __int16 *
0x1800275b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800275b7  test    eax, eax
0x1800275b9  js      loc_180027525
0x1800275bf  lea     rax, [rsp+960h+hKey]
0x1800275c4  mov     [rsp+960h+lpReserved], rax; phkResult
0x1800275c9  mov     r9d, edi; samDesired
0x1800275cc  xor     r8d, r8d; ulOptions
0x1800275cf  lea     rdx, [rbp+860h+var_260]; lpSubKey
0x1800275d6  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800275dd  call    cs:__imp_RegOpenKeyExW
0x1800275e3  test    eax, eax
0x1800275e5  jnz     loc_180027525
0x1800275eb  mov     [rsp+960h+cbData], 4
0x1800275f3  lea     rax, [rsp+960h+cbData]
0x1800275f8  mov     [rsp+960h+lpClass], rax; lpcbData
0x1800275fd  lea     rax, [rsp+960h+Data]
0x180027602  mov     [rsp+960h+lpReserved], rax; lpData
0x180027607  xor     r9d, r9d; lpType
0x18002760a  xor     r8d, r8d; lpReserved
0x18002760d  lea     rdx, ValueName; "ConsumerCredential"
0x180027614  mov     rcx, [rsp+960h+hKey]; hKey
0x180027619  call    cs:__imp_RegQueryValueExW
0x18002761f  test    eax, eax
0x180027621  jnz     loc_180027525
0x180027627  cmp     dword ptr [rsp+960h+Data], eax
0x18002762b  jz      loc_180027525
0x180027631  mov     [rsp+960h+var_8F0], 4
0x180027639  lea     rax, [rsp+960h+var_8F0]
0x18002763e  mov     [rsp+960h+lpClass], rax; lpcbData
0x180027643  lea     rax, [rsp+960h+var_910]
0x180027648  mov     [rsp+960h+lpReserved], rax; lpData
0x18002764d  xor     r9d, r9d; lpType
0x180027650  xor     r8d, r8d; lpReserved
0x180027653  lea     rdx, aConsumercreden; "ConsumerCredentialLevel"
0x18002765a  mov     rcx, [rsp+960h+hKey]; hKey
0x18002765f  call    cs:__imp_RegQueryValueExW
0x180027665  test    eax, eax
0x180027667  jnz     loc_180027525
0x18002766d  cmp     dword ptr [rsp+960h+var_910], edi
0x180027671  jnz     short loc_180027678
0x180027673  mov     r14d, edi
0x180027676  jmp     short loc_180027680
0x180027678  cmp     dword ptr [rsp+960h+var_910], 2
0x18002767d  cmovz   esi, edi
0x180027680  mov     [rsp+960h+var_8EC], 4
0x180027688  lea     rax, [rsp+960h+var_8EC]
0x18002768d  mov     [rsp+960h+lpClass], rax; lpcbData
0x180027692  lea     rax, [rsp+960h+var_8E8]
0x180027697  mov     [rsp+960h+lpReserved], rax; lpData
0x18002769c  xor     r9d, r9d; lpType
0x18002769f  xor     r8d, r8d; lpReserved
0x1800276a2  lea     rdx, aCdplenforced; "CDplEnforced"
0x1800276a9  mov     rcx, [rsp+960h+hKey]; hKey
0x1800276ae  call    cs:__imp_RegQueryValueExW
0x1800276b4  test    eax, eax
0x1800276b6  jnz     loc_180027525
0x1800276bc  cmp     dword ptr [rsp+960h+var_8E8], edi
0x1800276c0  jnz     loc_180027525
0x1800276c6  mov     r13d, edi
0x1800276c9  jmp     loc_180027525
0x1800276ce  mov     rcx, [rsp+960h+phkResult]
0x1800276d3  jmp     loc_180027464
0x1800276d8  mov     rcx, [rsp+960h+hKey]; hKey
0x1800276dd  xor     r12d, r12d
0x1800276e0  test    rcx, rcx
0x1800276e3  mov     rdi, [rbp+860h+var_8E0]
0x1800276e7  jz      short loc_1800276F4
0x1800276e9  call    cs:__imp_RegCloseKey
0x1800276ef  mov     [rsp+960h+hKey], r12
0x1800276f4  mov     rcx, [rsp+960h+phkResult]; hKey
0x1800276f9  test    rcx, rcx
0x1800276fc  jz      short loc_180027709
0x1800276fe  call    cs:__imp_RegCloseKey
0x180027704  mov     [rsp+960h+phkResult], r12
0x180027709  mov     eax, 0Eh
0x18002770e  test    r14d, r14d
0x180027711  jnz     short loc_18002775F
0x180027713  test    esi, esi
0x180027715  jnz     loc_18002779F
0x18002771b  lea     eax, [rsi+8]
0x18002771e  cmp     [rdi+18h], rax
0x180027722  jb      short loc_180027748
0x180027724  mov     rbx, [rdi]
0x180027727  mov     [rdi+10h], rax
0x18002772b  lea     r8d, [r14+10h]; Size
0x18002772f  lea     rdx, aDplNone; "DPL_NONE"
0x180027736  mov     rcx, rbx; void *
0x180027739  call    memmove_0
0x18002773e  mov     [rbx+10h], r12w
0x180027743  jmp     loc_18002791E
0x180027748  lea     r9, aDplNone; "DPL_NONE"
0x18002774f  mov     rdx, rax
0x180027752  mov     rcx, rdi
0x180027755  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002775a  jmp     loc_18002791E
0x18002775f  cmp     r14d, r15d
0x180027762  jnz     short loc_18002779F
0x180027764  cmp     [rdi+18h], rax
0x180027768  jb      short loc_18002778D
0x18002776a  mov     rbx, [rdi]
0x18002776d  mov     [rdi+10h], rax
0x180027771  mov     r8d, 1Ch; Size
0x180027777  lea     rdx, aDplPresentL1; "DPL_PRESENT_L1"
0x18002777e  mov     rcx, rbx; void *
0x180027781  call    memmove_0
0x180027786  mov     [rbx+1Ch], r12w
0x18002778b  jmp     short loc_18002779F
0x18002778d  lea     r9, aDplPresentL1; "DPL_PRESENT_L1"
0x180027794  mov     rdx, rax
0x180027797  mov     rcx, rdi
0x18002779a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002779f  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1800277a9  lea     rdx, asc_1801B58D8; "|"
0x1800277b0  cmp     esi, r15d
0x1800277b3  mov     rsi, r15
0x1800277b6  jnz     loc_180027886
0x1800277bc  cmp     r14d, r15d
0x1800277bf  jnz     short loc_18002781B
0x1800277c1  mov     rcx, [rdi+10h]
0x1800277c5  mov     rax, rbx
0x1800277c8  sub     rax, rcx
0x1800277cb  cmp     rax, r15
0x1800277ce  jb      loc_18002794A
0x1800277d4  cmp     qword ptr [rdi+18h], 7
0x1800277d9  jbe     short loc_1800277E0
0x1800277db  mov     r9, [rdi]
0x1800277de  jmp     short loc_1800277E3
0x1800277e0  mov     r9, rdi
0x1800277e3  mov     [rsp+960h+lpcchClass], r15
0x1800277e8  mov     [rsp+960h+lpClass], rdx
0x1800277ed  mov     [rsp+960h+lpReserved], rcx
0x1800277f2  lea     rcx, [rbp+860h+var_8D0]
0x1800277f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800277fb  mov     r15d, 3
0x180027801  mov     [rsp+960h+var_920], r15d
0x180027806  lea     rdx, [rbp+860h+var_8D0]
0x18002780a  mov     rcx, rdi
0x18002780d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180027812  lea     rcx, [rbp+860h+var_8D0]
0x180027816  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002781b  mov     rcx, [rdi+10h]
0x18002781f  mov     rax, rbx
0x180027822  sub     rax, rcx
0x180027825  cmp     rax, 0Eh
0x180027829  jb      loc_18002794A
0x18002782f  cmp     qword ptr [rdi+18h], 7
0x180027834  jbe     short loc_18002783B
0x180027836  mov     r9, [rdi]
0x180027839  jmp     short loc_18002783E
0x18002783b  mov     r9, rdi
0x18002783e  mov     [rsp+960h+lpcchClass], 0Eh
0x180027847  lea     rax, aDplPresentL2; "DPL_PRESENT_L2"
0x18002784e  mov     [rsp+960h+lpClass], rax
0x180027853  mov     [rsp+960h+lpReserved], rcx
0x180027858  lea     rcx, [rbp+860h+var_8D0]
0x18002785c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180027861  or      r15d, 4
0x180027865  mov     [rsp+960h+var_920], r15d
0x18002786a  lea     rdx, [rbp+860h+var_8D0]
0x18002786e  mov     rcx, rdi
0x180027871  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180027876  lea     rcx, [rbp+860h+var_8D0]
0x18002787a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002787f  lea     rdx, asc_1801B58D8; "|"
0x180027886  test    r13d, r13d
0x180027889  jz      loc_18002791E
0x18002788f  mov     rax, [rdi+10h]
0x180027893  sub     rbx, rax
0x180027896  cmp     rbx, rsi
0x180027899  jb      loc_180027944
0x18002789f  cmp     qword ptr [rdi+18h], 7
0x1800278a4  jbe     short loc_1800278AB
0x1800278a6  mov     r9, [rdi]
0x1800278a9  jmp     short loc_1800278AE
0x1800278ab  mov     r9, rdi
0x1800278ae  mov     [rsp+960h+lpcchClass], rsi
0x1800278b3  mov     [rsp+960h+lpClass], rdx
0x1800278b8  mov     [rsp+960h+lpReserved], rax
0x1800278bd  lea     rcx, [rbp+860h+Src]
0x1800278c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800278c6  or      r15d, 8
0x1800278ca  mov     [rsp+960h+var_920], r15d
0x1800278cf  lea     rdx, aDplEnabled; "DPL_ENABLED"
0x1800278d6  lea     rcx, [rbp+860h+Src]; Src
0x1800278da  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800278df  movups  xmm0, xmmword ptr [rax]
0x1800278e2  movups  [rbp+860h+var_8D0], xmm0
0x1800278e6  movups  xmm1, xmmword ptr [rax+10h]
0x1800278ea  movups  [rbp+860h+var_8C0], xmm1
0x1800278ee  mov     [rax+10h], r12
0x1800278f2  mov     qword ptr [rax+18h], 7
0x1800278fa  mov     [rax], r12w
0x1800278fe  lea     rdx, [rbp+860h+var_8D0]
0x180027902  mov     rcx, rdi
0x180027905  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002790a  lea     rcx, [rbp+860h+var_8D0]
0x18002790e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027913  nop
  ... truncated ...
```
