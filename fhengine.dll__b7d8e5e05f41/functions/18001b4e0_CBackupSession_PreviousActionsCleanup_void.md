# CBackupSession::PreviousActionsCleanup(void)

- ea: `0x18001b4e0`
- end: `0x18001baf1`
- name: `?PreviousActionsCleanup@CBackupSession@@AEAAJXZ`
- size: `1553`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180021240`

## callees

- `0x1800077f0`
- `0x180007818`
- `0x1800093a8`
- `0x180009404`
- `0x1800094ec`
- `0x18000cafc`
- `0x180012278`
- `0x1800122d8`
- `0x1800127b0`
- `0x18001b4e0`
- `0x180030b88`
- `0x180034010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18001b5aa`
- `ADVAPI32!RegGetValueW` at `0x18001b5eb`
- `ADVAPI32!RegGetValueW` at `0x18001b5aa`
- `ADVAPI32!RegGetValueW` at `0x18001b5eb`
- `ADVAPI32!RegSetKeyValueW` at `0x18001b68e`
- `ADVAPI32!RegSetKeyValueW` at `0x18001ba1a`
- `ADVAPI32!RegSetKeyValueW` at `0x18001ba94`
- `ADVAPI32!RegSetKeyValueW` at `0x18001b68e`
- `ADVAPI32!RegSetKeyValueW` at `0x18001ba1a`
- `ADVAPI32!RegSetKeyValueW` at `0x18001ba94`
- `ADVAPI32!SetThreadToken` at `0x18001b50c`
- `ADVAPI32!SetThreadToken` at `0x18001b50c`
- `KERNEL32!GetLastError` at `0x18001b516`
- `KERNEL32!GetLastError` at `0x18001b711`
- `KERNEL32!GetLastError` at `0x18001b71c`
- `KERNEL32!GetLastError` at `0x18001b516`
- `KERNEL32!GetLastError` at `0x18001b711`
- `KERNEL32!GetLastError` at `0x18001b71c`
- `KERNEL32!DeleteFileW` at `0x18001b6f9`
- `KERNEL32!DeleteFileW` at `0x18001b6f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b9c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b9c1`

## string_xrefs

- `0x18001b73e`: `ret || GetLastError() == ERROR_FILE_NOT_FOUND || GetLastError() == ERROR_PATH_NOT_FOUND`
- `0x18001b930`: `PerformDirectoryTreeOperation has failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::PreviousActionsCleanup(CBackupSession *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  int v7; // eax
  int v8; // eax
  LSTATUS v9; // eax
  PVOID *v10; // rcx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, char *, __int64); // rbx
  _QWORD *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  PVOID *v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, int *, __int64); // rbx
  _QWORD *v24; // rax
  LSTATUS v25; // eax
  LSTATUS v26; // eax
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  int pvData; // [rsp+90h] [rbp+40h] BYREF
  int v30; // [rsp+98h] [rbp+48h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+50h] BYREF
  int Data; // [rsp+A8h] [rbp+58h] BYREF

  pvData = 0;
  v30 = 0;
  Data = 0;
  pcbData = 0;
  if ( !SetThreadToken(0, *((HANDLE *)this + 48)) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 85;
      v6 = v3;
LABEL_7:
      WPP_SF_d(v4[2], v5, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v6);
      return v3;
    }
    return v3;
  }
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
         L"ReassociationPerformed",
         0x10u,
         0,
         &pvData,
         &pcbData)
    || pcbData != 4 )
  {
    pvData = 0;
  }
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
         L"TargetChanged",
         0x10u,
         0,
         &v30,
         &pcbData)
    || pcbData != 4 )
  {
    v30 = 0;
  }
  v3 = 0;
  v7 = pvData;
  if ( !pvData )
    goto LABEL_20;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3), 1);
  v3 = v8;
  if ( v8 >= 0 )
  {
    v7 = pvData;
    if ( pvData )
    {
LABEL_21:
      Data = 1;
      v9 = RegSetKeyValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
             L"SearchRebuildRequired",
             4u,
             &Data,
             4u);
      if ( v9 )
      {
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
        else
          v3 = v9;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
            (__int64)L"SearchRebuildRequired",
            v3);
        return v3;
      }
      v7 = pvData;
LABEL_29:
      if ( !v7 && !v30 )
        return v3;
      if ( !DeleteFileW(*((LPCWSTR *)this + 15)) && GetLastError() != 2 && GetLastError() != 3 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
LABEL_38:
          v11 = pvData;
          if ( !pvData )
            goto LABEL_60;
          *((_DWORD *)this + 95) = *((_DWORD *)this + 11);
          v12 = *((_QWORD *)this + 3);
          v13 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v12 + 168LL);
          v14 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"LastReassociationBSet");
          v3 = v13(v12, *v14, (char *)this + 380, 4);
          SysFreeString(bstrString[0]);
          if ( (v3 & 0x80000000) != 0 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v3;
            v5 = 89;
            goto LABEL_43;
          }
          v11 = pvData;
          if ( !pvData )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_60;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
          v15 = CSessionBaseRW::CleanupStagingArea((CBackupSession *)((char *)this + 8), 0, 0, 0);
          v16 = v15;
          if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2147023661 )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_57;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_ss(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                91,
                (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                (int)"FALSE",
                (__int64)"CleanupStagingArea has failed");
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
            {
LABEL_57:
              v3 = 0;
              v11 = pvData;
              if ( pvData )
              {
LABEL_61:
                if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
                  WPP_SF_S(v10[2], 93, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((_QWORD *)this + 8));
                v17 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        bstrString,
                        (char *)this + 64);
                v19 = FheFileOperations::PerformDirectoryTreeOperation(v18, v17, 0, (int)this + 160, 0, 0, 0);
                v20 = v19;
                if ( ((v19 + 0x80000000) & 0x80000000) == 0 && v19 != -2147023661 )
                {
                  v21 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      WPP_SF_ss(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        94,
                        (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        (int)"FALSE",
                        (__int64)"PerformDirectoryTreeOperation has failed");
                      v21 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
                      WPP_SF_d(v21[2], 95, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v20);
                  }
                }
                v3 = 0;
                v11 = pvData;
LABEL_73:
                if ( v11 )
                {
                  v22 = *((_QWORD *)this + 3);
                  v23 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64))(*(_QWORD *)v22 + 168LL);
                  v24 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"ReassociationPerformed");
                  v3 = v23(v22, *v24, &pvData, 4);
                  SysFreeString(bstrString[0]);
                  if ( (v3 & 0x80000000) != 0 )
                  {
                    v4 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      return v3;
                    v5 = 96;
LABEL_43:
                    v6 = v3;
                    goto LABEL_7;
                  }
                  pvData = 0;
                  v25 = RegSetKeyValueW(
                          HKEY_CURRENT_USER,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
                          L"ReassociationPerformed",
                          4u,
                          &pvData,
                          4u);
                  if ( v25 )
                  {
                    if ( v25 > 0 )
                      v3 = (unsigned __int16)v25 | 0x80070000;
                    else
                      v3 = v25;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_SSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        97,
                        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
                        (__int64)L"ReassociationPerformed",
                        v3);
                    return v3;
                  }
                }
                if ( v30 )
                {
                  v30 = 0;
                  v26 = RegSetKeyValueW(
                          HKEY_CURRENT_USER,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
                          L"TargetChanged",
                          4u,
                          &v30,
                          4u);
                  if ( v26 )
                  {
                    v3 = v26 > 0 ? (unsigned __int16)v26 | 0x80070000 : v26;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_SSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        98,
                        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
                        (__int64)L"TargetChanged",
                        v3);
                  }
                }
                return v3;
              }
LABEL_60:
              if ( !v30 )
                goto LABEL_73;
              goto LABEL_61;
            }
            WPP_SF_d(v10[2], 92, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v16);
          }
          v10 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_57;
        }
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          "ret || GetLastError() == ERROR_FILE_NOT_FOUND || GetLastError() == ERROR_PATH_NOT_FOUND");
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_38;
    }
LABEL_20:
    if ( !v30 )
      goto LABEL_29;
    goto LABEL_21;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 86;
    v6 = (unsigned int)v8;
    goto LABEL_7;
  }
  return v3;
}

```

## disassembly

```asm
0x18001b4e0  push    rbp
0x18001b4e2  push    rbx
0x18001b4e3  push    rsi
0x18001b4e4  push    rdi
0x18001b4e5  push    r13
0x18001b4e7  push    r14
0x18001b4e9  push    r15
0x18001b4eb  mov     rbp, rsp
0x18001b4ee  sub     rsp, 50h
0x18001b4f2  mov     r13, rcx
0x18001b4f5  xor     esi, esi
0x18001b4f7  mov     [rbp+arg_0], esi
0x18001b4fa  mov     [rbp+arg_8], esi
0x18001b4fd  mov     [rbp+Data], esi
0x18001b500  mov     [rbp+arg_10], esi
0x18001b503  mov     rdx, [rcx+180h]; Token
0x18001b50a  xor     ecx, ecx; Thread
0x18001b50c  call    cs:__imp_SetThreadToken
0x18001b512  test    eax, eax
0x18001b514  jnz     short loc_18001B569
0x18001b516  call    cs:__imp_GetLastError
0x18001b51c  mov     ebx, eax
0x18001b51e  test    eax, eax
0x18001b520  jle     short loc_18001B52B
0x18001b522  movzx   ebx, ax
0x18001b525  or      ebx, 80070000h
0x18001b52b  lea     r14, WPP_GLOBAL_Control
0x18001b532  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b539  cmp     rcx, r14
0x18001b53c  jz      loc_18001BAE0
0x18001b542  test    byte ptr [rcx+1Ch], 1
0x18001b546  jz      loc_18001BAE0
0x18001b54c  mov     edx, 55h ; 'U'
0x18001b551  mov     r9d, ebx
0x18001b554  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001b55b  mov     rcx, [rcx+10h]
0x18001b55f  call    WPP_SF_d
0x18001b564  jmp     loc_18001BAE0
0x18001b569  mov     [rbp+arg_10], 4
0x18001b570  lea     rax, [rbp+arg_10]
0x18001b574  mov     [rsp+50h+pcbData], rax; pcbData
0x18001b579  lea     rax, [rbp+arg_0]
0x18001b57d  mov     [rsp+50h+pvData], rax; pvData
0x18001b582  mov     [rsp+50h+pdwType], rsi; pdwType
0x18001b587  mov     ebx, 10h
0x18001b58c  mov     r9d, ebx; dwFlags
0x18001b58f  lea     r8, Value; "ReassociationPerformed"
0x18001b596  lea     rdi, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001b59d  mov     rdx, rdi; lpSubKey
0x18001b5a0  mov     r14, 0FFFFFFFF80000001h
0x18001b5a7  mov     rcx, r14; hkey
0x18001b5aa  call    cs:__imp_RegGetValueW
0x18001b5b0  test    eax, eax
0x18001b5b2  jnz     short loc_18001B5BA
0x18001b5b4  cmp     [rbp+arg_10], 4
0x18001b5b8  jz      short loc_18001B5BD
0x18001b5ba  mov     [rbp+arg_0], esi
0x18001b5bd  mov     [rbp+arg_10], 4
0x18001b5c4  lea     rax, [rbp+arg_10]
0x18001b5c8  mov     [rsp+50h+pcbData], rax; pcbData
0x18001b5cd  lea     rax, [rbp+arg_8]
0x18001b5d1  mov     [rsp+50h+pvData], rax; pvData
0x18001b5d6  mov     [rsp+50h+pdwType], rsi; pdwType
0x18001b5db  mov     r9d, ebx; dwFlags
0x18001b5de  lea     r8, aTargetchanged; "TargetChanged"
0x18001b5e5  mov     rdx, rdi; lpSubKey
0x18001b5e8  mov     rcx, r14; hkey
0x18001b5eb  call    cs:__imp_RegGetValueW
0x18001b5f1  test    eax, eax
0x18001b5f3  jnz     short loc_18001B5FB
0x18001b5f5  cmp     [rbp+arg_10], 4
0x18001b5f9  jz      short loc_18001B5FE
0x18001b5fb  mov     [rbp+arg_8], esi
0x18001b5fe  mov     ebx, esi
0x18001b600  mov     eax, [rbp+arg_0]
0x18001b603  test    eax, eax
0x18001b605  jz      short loc_18001B657
0x18001b607  mov     rcx, [r13+18h]
0x18001b60b  mov     rax, [rcx]
0x18001b60e  mov     edx, 1
0x18001b613  mov     rax, [rax+38h]
0x18001b617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b61c  mov     ebx, eax
0x18001b61e  test    eax, eax
0x18001b620  jns     short loc_18001B650
0x18001b622  lea     r14, WPP_GLOBAL_Control
0x18001b629  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b630  cmp     rcx, r14
0x18001b633  jz      loc_18001BAE0
0x18001b639  test    byte ptr [rcx+1Ch], 1
0x18001b63d  jz      loc_18001BAE0
0x18001b643  mov     edx, 56h ; 'V'
0x18001b648  mov     r9d, eax
0x18001b64b  jmp     loc_18001B554
0x18001b650  mov     eax, [rbp+arg_0]
0x18001b653  test    eax, eax
0x18001b655  jnz     short loc_18001B660
0x18001b657  cmp     [rbp+arg_8], esi
0x18001b65a  jz      loc_18001B6E8
0x18001b660  mov     [rbp+Data], 1
0x18001b667  mov     dword ptr [rsp+50h+pvData], 4; cbData
0x18001b66f  lea     rax, [rbp+Data]
0x18001b673  mov     [rsp+50h+pdwType], rax; lpData
0x18001b678  mov     r9d, 4; dwType
0x18001b67e  lea     r15, aSearchrebuildr; "SearchRebuildRequired"
0x18001b685  mov     r8, r15; lpValueName
0x18001b688  mov     rdx, rdi; lpSubKey
0x18001b68b  mov     rcx, r14; hKey
0x18001b68e  call    cs:__imp_RegSetKeyValueW
0x18001b694  test    eax, eax
0x18001b696  jz      short loc_18001B6E5
0x18001b698  jg      short loc_18001B69E
0x18001b69a  mov     ebx, eax
0x18001b69c  jmp     short loc_18001B6A7
0x18001b69e  movzx   ebx, ax
0x18001b6a1  or      ebx, 80070000h
0x18001b6a7  lea     r14, WPP_GLOBAL_Control
0x18001b6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6b5  cmp     rcx, r14
0x18001b6b8  jz      loc_18001BAE0
0x18001b6be  test    byte ptr [rcx+1Ch], 1
0x18001b6c2  jz      loc_18001BAE0
0x18001b6c8  mov     edx, 57h ; 'W'
0x18001b6cd  mov     dword ptr [rsp+50h+pvData], ebx
0x18001b6d1  mov     [rsp+50h+pdwType], r15
0x18001b6d6  mov     r9, rdi
0x18001b6d9  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001b6e0  jmp     loc_18001BAD7
0x18001b6e5  mov     eax, [rbp+arg_0]
0x18001b6e8  test    eax, eax
0x18001b6ea  jnz     short loc_18001B6F5
0x18001b6ec  cmp     [rbp+arg_8], esi
0x18001b6ef  jz      loc_18001BAE0
0x18001b6f5  mov     rcx, [r13+78h]; lpFileName
0x18001b6f9  call    cs:__imp_DeleteFileW
0x18001b6ff  lea     r15, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001b706  lea     r14, WPP_GLOBAL_Control
0x18001b70d  test    eax, eax
0x18001b70f  jnz     short loc_18001B751
0x18001b711  call    cs:__imp_GetLastError
0x18001b717  cmp     eax, 2
0x18001b71a  jz      short loc_18001B751
0x18001b71c  call    cs:__imp_GetLastError
0x18001b722  cmp     eax, 3
0x18001b725  jz      short loc_18001B751
0x18001b727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b72e  cmp     rcx, r14
0x18001b731  jz      short loc_18001B758
0x18001b733  test    byte ptr [rcx+1Ch], 4
0x18001b737  jz      short loc_18001B758
0x18001b739  mov     edx, 58h ; 'X'
0x18001b73e  lea     r9, aRetGetlasterro; "ret || GetLastError() == ERROR_FILE_NOT"...
0x18001b745  mov     r8, r15
0x18001b748  mov     rcx, [rcx+10h]
0x18001b74c  call    WPP_SF_s
0x18001b751  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b758  mov     edi, 80000000h
0x18001b75d  mov     eax, [rbp+arg_0]
0x18001b760  test    eax, eax
0x18001b762  jz      loc_18001B8B2
0x18001b768  lea     rsi, [r13+17Ch]
0x18001b76f  mov     eax, [r13+2Ch]
0x18001b773  mov     [rsi], eax
0x18001b775  mov     rdi, [r13+18h]
0x18001b779  mov     rax, [rdi]
0x18001b77c  mov     rbx, [rax+0A8h]
0x18001b783  lea     rdx, aLastreassociat; "LastReassociationBSet"
0x18001b78a  lea     rcx, [rbp+bstrString]; this
0x18001b78e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001b793  mov     r9d, 4
0x18001b799  mov     r8, rsi
0x18001b79c  mov     rdx, [rax]
0x18001b79f  mov     rcx, rdi
0x18001b7a2  mov     rax, rbx
0x18001b7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7aa  mov     ebx, eax
0x18001b7ac  mov     rcx, [rbp+bstrString]; bstrString
0x18001b7b0  call    cs:__imp_SysFreeString
0x18001b7b6  xor     esi, esi
0x18001b7b8  test    ebx, ebx
0x18001b7ba  jns     short loc_18001B7E4
0x18001b7bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7c3  cmp     rcx, r14
0x18001b7c6  jz      loc_18001BAE0
0x18001b7cc  test    byte ptr [rcx+1Ch], 1
0x18001b7d0  jz      loc_18001BAE0
0x18001b7d6  lea     edx, [rsi+59h]
0x18001b7d9  mov     r9d, ebx
0x18001b7dc  mov     r8, r15
0x18001b7df  jmp     loc_18001B55B
0x18001b7e4  mov     eax, [rbp+arg_0]
0x18001b7e7  test    eax, eax
0x18001b7e9  jz      loc_18001B8A6
0x18001b7ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7f6  cmp     rcx, r14
0x18001b7f9  jz      short loc_18001B812
0x18001b7fb  test    byte ptr [rcx+1Ch], 8
0x18001b7ff  jz      short loc_18001B812
0x18001b801  mov     edx, 5Ah ; 'Z'
0x18001b806  mov     r8, r15
0x18001b809  mov     rcx, [rcx+10h]
0x18001b80d  call    WPP_SF_
0x18001b812  lea     rcx, [r13+8]; this
0x18001b816  xor     r9d, r9d; struct IFhEngineCleanupProgressEvent *
0x18001b819  xor     r8d, r8d; __int64 *
0x18001b81c  xor     edx, edx; int *
0x18001b81e  call    ?CleanupStagingArea@CSessionBaseRW@@IEAAJPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; CSessionBaseRW::CleanupStagingArea(long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x18001b823  mov     ebx, eax
0x18001b825  mov     edi, 80000000h
0x18001b82a  lea     ecx, [rax+rdi]
0x18001b82d  test    edi, ecx
0x18001b82f  jnz     short loc_18001B894
0x18001b831  cmp     eax, 800704D3h
0x18001b836  jz      short loc_18001B894
0x18001b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b83f  cmp     rcx, r14
0x18001b842  jz      short loc_18001B89B
0x18001b844  test    byte ptr [rcx+1Ch], 4
0x18001b848  jz      short loc_18001B875
0x18001b84a  mov     edx, 5Bh ; '['
0x18001b84f  lea     rax, aCleanupstaging; "CleanupStagingArea has failed"
0x18001b856  mov     [rsp+50h+pdwType], rax
0x18001b85b  lea     r9, aFalse; "FALSE"
0x18001b862  mov     r8, r15
0x18001b865  mov     rcx, [rcx+10h]
0x18001b869  call    WPP_SF_ss
0x18001b86e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b875  cmp     rcx, r14
0x18001b878  jz      short loc_18001B89B
0x18001b87a  test    byte ptr [rcx+1Ch], 1
0x18001b87e  jz      short loc_18001B89B
0x18001b880  mov     edx, 5Ch ; '\'
0x18001b885  mov     r9d, ebx
0x18001b888  mov     r8, r15
0x18001b88b  mov     rcx, [rcx+10h]
0x18001b88f  call    WPP_SF_d
0x18001b894  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b89b  mov     ebx, esi
0x18001b89d  mov     eax, [rbp+arg_0]
0x18001b8a0  test    eax, eax
0x18001b8a2  jnz     short loc_18001B8BB
0x18001b8a4  jmp     short loc_18001B8B2
0x18001b8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8ad  mov     edi, 80000000h
0x18001b8b2  cmp     [rbp+arg_8], esi
0x18001b8b5  jz      loc_18001B97A
0x18001b8bb  cmp     rcx, r14
0x18001b8be  jz      short loc_18001B8DB
0x18001b8c0  test    byte ptr [rcx+1Ch], 8
0x18001b8c4  jz      short loc_18001B8DB
0x18001b8c6  mov     edx, 5Dh ; ']'
0x18001b8cb  mov     r9, [r13+40h]
0x18001b8cf  mov     r8, r15
0x18001b8d2  mov     rcx, [rcx+10h]
0x18001b8d6  call    WPP_SF_S
0x18001b8db  lea     rdx, [r13+40h]
0x18001b8df  lea     rcx, [rbp+bstrString]
0x18001b8e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001b8e8  mov     rdx, rax
0x18001b8eb  mov     [rsp+50h+pcbData], rsi
0x18001b8f0  mov     [rsp+50h+pvData], rsi
0x18001b8f5  mov     [rsp+50h+pdwType], rsi
0x18001b8fa  lea     r9, [r13+0A0h]
0x18001b901  xor     r8d, r8d
0x18001b904  call    ?PerformDirectoryTreeOperation@FheFileOperations@@YAJW4DirectoryTreeOp@1@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEAHPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; FheFileOperations::PerformDirectoryTreeOperation(FheFileOperations::DirectoryTreeOp,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int,int *,long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x18001b909  mov     ebx, eax
0x18001b90b  lea     ecx, [rax+rdi]
0x18001b90e  test    edi, ecx
0x18001b910  jnz     short loc_18001B975
0x18001b912  cmp     eax, 800704D3h
0x18001b917  jz      short loc_18001B975
0x18001b919  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b920  cmp     rcx, r14
0x18001b923  jz      short loc_18001B975
0x18001b925  test    byte ptr [rcx+1Ch], 4
0x18001b929  jz      short loc_18001B956
0x18001b92b  mov     edx, 5Eh ; '^'
0x18001b930  lea     rax, aPerformdirecto; "PerformDirectoryTreeOperation has faile"...
0x18001b937  mov     [rsp+50h+pdwType], rax
0x18001b93c  lea     r9, aFalse; "FALSE"
0x18001b943  mov     r8, r15
0x18001b946  mov     rcx, [rcx+10h]
0x18001b94a  call    WPP_SF_ss
0x18001b94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b956  cmp     rcx, r14
0x18001b959  jz      short loc_18001B975
0x18001b95b  test    byte ptr [rcx+1Ch], 1
0x18001b95f  jz      short loc_18001B975
0x18001b961  mov     edx, 5Fh ; '_'
0x18001b966  mov     r9d, ebx
0x18001b969  mov     r8, r15
0x18001b96c  mov     rcx, [rcx+10h]
0x18001b970  call    WPP_SF_d
0x18001b975  mov     ebx, esi
0x18001b977  mov     eax, [rbp+arg_0]
0x18001b97a  test    eax, eax
0x18001b97c  jz      loc_18001BA5D
0x18001b982  mov     rdi, [r13+18h]
0x18001b986  mov     rax, [rdi]
0x18001b989  mov     rbx, [rax+0A8h]
  ... truncated ...
```
