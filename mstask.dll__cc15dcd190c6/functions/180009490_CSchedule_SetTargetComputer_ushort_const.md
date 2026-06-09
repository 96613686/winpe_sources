# CSchedule::SetTargetComputer(ushort const *)

- ea: `0x180009490`
- end: `0x1800099fd`
- name: `?SetTargetComputer@CSchedule@@UEAAJPEBG@Z`
- size: `1389`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x180002ab0`
- `0x180006ec0`
- `0x180006f90`
- `0x180009490`
- `0x180009ef8`
- `0x180009f38`
- `0x18000a608`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800096e7`
- `msvcrt!_wcsnicmp` at `0x18000970a`
- `msvcrt!_wcsnicmp` at `0x1800096e7`
- `msvcrt!_wcsnicmp` at `0x18000970a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009512`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000960f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000975e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000960f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000975e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009812`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009681`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800097a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009681`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800097a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000974d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000974d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180009550`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180009550`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000957a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000958d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000957a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000958d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180009508`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180009508`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800095d1`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800095d1`

## string_xrefs

- `0x1800095f7`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x180009660`: `TasksFolder`
- `0x180009691`: `%SystemRoot%\Tasks`

## pseudocode

```c
signed int __fastcall CSchedule::SetTargetComputer(CSchedule *this, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // r13
  BOOL v5; // r15d
  signed int result; // eax
  bool v7; // cc
  LSTATUS v8; // ebx
  unsigned __int64 v9; // rcx
  DWORD v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // r12
  _WORD *v16; // rax
  void *v17; // r14
  __int64 v18; // rax
  unsigned __int16 *v19; // rbx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v26; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String2; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v29; // [rsp+52h] [rbp-AEh]
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 Data[264]; // [rsp+470h] [rbp+370h] BYREF

  v2 = 0;
  nSize = 0;
  v5 = 1;
  if ( a2 )
  {
    memset_0(Buffer, 0, 0x202u);
    nSize = 257;
    if ( !GetComputerNameW(Buffer, &nSize)
      || (memset_0(&String2, 0, 0x202u),
          nSize = 257,
          !GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, &String2, &nSize)) )
    {
      result = GetLastError();
      v7 = result <= 0;
      goto LABEL_4;
    }
    if ( !*a2 || !a2[1] )
      return -2147418113;
    if ( lstrcmpiW(a2 + 2, Buffer) )
      v5 = lstrcmpiW(a2 + 2, &String2) == 0;
  }
  memset_0(&String2, 0, 0x20Au);
  if ( v5 )
  {
    v14 = -1;
    do
      ++v14;
    while ( g_TasksFolderInfo[v14] );
    v13 = v14 + 1;
    goto LABEL_48;
  }
  phkResult = 0;
  hKey = 0;
  result = RegConnectRegistryW(a2, HKEY_LOCAL_MACHINE, &phkResult);
  v7 = result <= 0;
  if ( result )
  {
LABEL_4:
    if ( !v7 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v8 = RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  if ( !v8 )
  {
    memset_0(Buffer, 0, 0x20Au);
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"TasksFolder", 0, 0, (LPBYTE)Buffer, &cbData) )
    {
      StringCchCopyW(Buffer, 0x105u, L"%SystemRoot%\\Tasks");
    }
    else
    {
      v9 = cbData & 0xFFFFFFFE;
      if ( v9 >= 0x20A )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)Buffer + v9) = 0;
    }
    RegCloseKey(hKey);
    nSize = 12;
    if ( _wcsnicmp(Buffer, L"%SystemRoot%", 0xCu) && (nSize = 8, _wcsnicmp(Buffer, L"%WinDir%", 8u)) )
    {
      v10 = 0;
      nSize = 0;
    }
    else
    {
      v10 = nSize;
    }
    if ( v10 )
    {
      v26 = 0;
      v8 = RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0xF003Fu, &v26);
      if ( v8 )
      {
LABEL_30:
        RegCloseKey(phkResult);
        goto LABEL_16;
      }
      memset_0(Data, 0, 0x20Au);
      cbData = 522;
      v8 = RegQueryValueExW(v26, L"SystemRoot", 0, 0, (LPBYTE)Data, &cbData);
      if ( v8 )
      {
        RegCloseKey(v26);
        goto LABEL_30;
      }
      RegCloseKey(v26);
      StringCchCopyW(&String2, 0x105u, Data);
      StringCchCatW(&String2, 0x105u, &Buffer[nSize]);
    }
    else
    {
      StringCchCopyW(&String2, 0x105u, Buffer);
    }
    RegCloseKey(phkResult);
    if ( (unsigned __int16)(String2 - 65) > 0x19u && (unsigned __int16)(String2 - 97) > 0x19u || v29 != 58 )
      return -2147024735;
    v11 = -1;
    do
      ++v11;
    while ( *(&String2 + v11) );
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = v12 + v11 + 2;
LABEL_48:
    nSize = v13;
    v15 = v13;
    v16 = operator new(saturated_mul(v13, 2u));
    v17 = v16;
    if ( !v16 )
      return -2147024882;
    *v16 = 0;
    if ( v5 )
    {
      v19 = 0;
    }
    else
    {
      v18 = -1;
      do
        ++v18;
      while ( a2[v18] );
      v2 = v18 + 1;
      v19 = (unsigned __int16 *)operator new(saturated_mul(v18 + 1, 2u));
      if ( !v19 )
      {
        operator delete(v17);
        return -2147024882;
      }
      *v19 = 0;
    }
    v20 = (void *)*((_QWORD *)this + 7);
    if ( v20 )
      operator delete(v20);
    v21 = (void *)*((_QWORD *)this + 8);
    if ( v21 )
      operator delete(v21);
    if ( v5 )
    {
      *((_QWORD *)this + 8) = v17;
      *((_QWORD *)this + 7) = 0;
      StringCchCopyW((unsigned __int16 *)v17, v15, g_TasksFolderInfo);
      v8 = FolderAccessCheckOnThreadToken(*((LPCWSTR *)this + 8), 1u);
      if ( v8 < 0 )
      {
        operator delete(*((void **)this + 7));
        v22 = (void *)*((_QWORD *)this + 8);
        *((_QWORD *)this + 7) = 0;
        operator delete(v22);
        *((_QWORD *)this + 8) = 0;
        CSchedule::Init(this);
        return v8;
      }
    }
    else
    {
      *((_QWORD *)this + 7) = v19;
      StringCchCopyW(v19, v2, a2);
      *((_QWORD *)this + 8) = v17;
      v29 = 36;
      StringCchCopyW((unsigned __int16 *)v17, v15, a2);
      StringCchCatW(*((unsigned __int16 **)this + 8), v15, L"\\");
      StringCchCatW(*((unsigned __int16 **)this + 8), v15, &String2);
    }
    return 0;
  }
  RegCloseKey(phkResult);
  if ( v8 != 1010 && v8 != 2 )
  {
LABEL_16:
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return v8;
  }
  return -2147216628;
}

```

## disassembly

```asm
0x180009490  mov     [rsp-8+arg_10], rbx
0x180009495  push    rbp
0x180009496  push    rsi
0x180009497  push    rdi
0x180009498  push    r12
0x18000949a  push    r13
0x18000949c  push    r14
0x18000949e  push    r15
0x1800094a0  lea     rbp, [rsp-590h]
0x1800094a8  sub     rsp, 690h
0x1800094af  mov     rax, cs:__security_cookie
0x1800094b6  xor     rax, rsp
0x1800094b9  mov     [rbp+5C0h+var_40], rax
0x1800094c0  xor     r13d, r13d
0x1800094c3  mov     rsi, rdx
0x1800094c6  mov     [rsp+6C0h+nSize], r13d
0x1800094cb  mov     rdi, rcx
0x1800094ce  lea     r15d, [r13+1]
0x1800094d2  test    rdx, rdx
0x1800094d5  jz      loc_18000959A
0x1800094db  mov     ebx, 202h
0x1800094e0  lea     rcx, [rbp+5C0h+Buffer]; void *
0x1800094e7  mov     r8d, ebx; Size
0x1800094ea  xor     edx, edx; Val
0x1800094ec  call    memset_0
0x1800094f1  mov     r14d, 101h
0x1800094f7  lea     rdx, [rsp+6C0h+nSize]; nSize
0x1800094fc  lea     rcx, [rbp+5C0h+Buffer]; lpBuffer
0x180009503  mov     [rsp+6C0h+nSize], r14d
0x180009508  call    cs:__imp_GetComputerNameW
0x18000950e  test    eax, eax
0x180009510  jnz     short loc_18000952D
0x180009512  call    cs:__imp_GetLastError
0x180009518  test    eax, eax
0x18000951a  jle     loc_1800099D3
0x180009520  movzx   eax, ax
0x180009523  or      eax, 80070000h
0x180009528  jmp     loc_1800099D3
0x18000952d  mov     r8, rbx; Size
0x180009530  lea     rcx, [rsp+6C0h+String2]; void *
0x180009535  xor     edx, edx; Val
0x180009537  call    memset_0
0x18000953c  lea     r8, [rsp+6C0h+nSize]; nSize
0x180009541  mov     [rsp+6C0h+nSize], r14d
0x180009546  lea     rdx, [rsp+6C0h+String2]; lpBuffer
0x18000954b  mov     ecx, 7; NameType
0x180009550  call    cs:__imp_GetComputerNameExW
0x180009556  test    eax, eax
0x180009558  jz      short loc_180009512
0x18000955a  cmp     [rsi], r13w
0x18000955e  jz      loc_1800099CE
0x180009564  cmp     [rsi+2], r13w
0x180009569  jz      loc_1800099CE
0x18000956f  lea     rdx, [rbp+5C0h+Buffer]; lpString2
0x180009576  lea     rcx, [rsi+4]; lpString1
0x18000957a  call    cs:__imp_lstrcmpiW
0x180009580  test    eax, eax
0x180009582  jz      short loc_18000959A
0x180009584  lea     rdx, [rsp+6C0h+String2]; lpString2
0x180009589  lea     rcx, [rsi+4]; lpString1
0x18000958d  call    cs:__imp_lstrcmpiW
0x180009593  test    eax, eax
0x180009595  jz      short loc_18000959A
0x180009597  mov     r15d, r13d
0x18000959a  mov     r14d, 20Ah
0x1800095a0  lea     rcx, [rsp+6C0h+String2]; void *
0x1800095a5  mov     r8d, r14d; Size
0x1800095a8  xor     edx, edx; Val
0x1800095aa  call    memset_0
0x1800095af  test    r15d, r15d
0x1800095b2  jnz     loc_180009872
0x1800095b8  lea     r8, [rsp+6C0h+phkResult]; phkResult
0x1800095bd  mov     [rsp+6C0h+phkResult], r13
0x1800095c2  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800095c9  mov     [rsp+6C0h+hKey], r13
0x1800095ce  mov     rcx, rsi; lpMachineName
0x1800095d1  call    cs:__imp_RegConnectRegistryW
0x1800095d7  test    eax, eax
0x1800095d9  jnz     loc_18000951A
0x1800095df  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x1800095e4  lea     rax, [rsp+6C0h+hKey]
0x1800095e9  mov     r9d, 20019h; samDesired
0x1800095ef  mov     [rsp+6C0h+var_6A0], rax; phkResult
0x1800095f4  xor     r8d, r8d; ulOptions
0x1800095f7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x1800095fe  call    cs:__imp_RegOpenKeyExW
0x180009604  mov     ebx, eax
0x180009606  test    eax, eax
0x180009608  jz      short loc_180009640
0x18000960a  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18000960f  call    cs:__imp_RegCloseKey
0x180009615  cmp     ebx, 3F2h
0x18000961b  jz      short loc_180009636
0x18000961d  cmp     ebx, 2
0x180009620  jz      short loc_180009636
0x180009622  test    ebx, ebx
0x180009624  jle     short loc_18000962F
0x180009626  movzx   ebx, bx
0x180009629  or      ebx, 80070000h
0x18000962f  mov     eax, ebx
0x180009631  jmp     loc_1800099D3
0x180009636  mov     eax, 8004130Ch
0x18000963b  jmp     loc_1800099D3
0x180009640  mov     r8, r14; Size
0x180009643  lea     rcx, [rbp+5C0h+Buffer]; void *
0x18000964a  xor     edx, edx; Val
0x18000964c  call    memset_0
0x180009651  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180009656  lea     rax, [rsp+6C0h+cbData]
0x18000965b  mov     [rsp+6C0h+lpcbData], rax; lpcbData
0x180009660  lea     rdx, aTasksfolder; "TasksFolder"
0x180009667  lea     rax, [rbp+5C0h+Buffer]
0x18000966e  mov     [rsp+6C0h+cbData], 208h
0x180009676  xor     r9d, r9d; lpType
0x180009679  mov     [rsp+6C0h+var_6A0], rax; lpData
0x18000967e  xor     r8d, r8d; lpReserved
0x180009681  call    cs:__imp_RegQueryValueExW
0x180009687  mov     r12d, 105h
0x18000968d  test    eax, eax
0x18000968f  jz      short loc_1800096A9
0x180009691  lea     r8, aSystemrootTask; "%SystemRoot%\\Tasks"
0x180009698  mov     edx, r12d; unsigned __int64
0x18000969b  lea     rcx, [rbp+5C0h+Buffer]; unsigned __int16 *
0x1800096a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800096a7  jmp     short loc_1800096C3
0x1800096a9  mov     ecx, [rsp+6C0h+cbData]
0x1800096ad  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800096b1  cmp     rcx, r14
0x1800096b4  jnb     loc_18000986C
0x1800096ba  mov     [rbp+rcx+5C0h+Buffer], r13w
0x1800096c3  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800096c8  call    cs:__imp_RegCloseKey
0x1800096ce  mov     r8d, 0Ch; MaxCount
0x1800096d4  lea     rdx, aSystemroot_0; "%SystemRoot%"
0x1800096db  lea     rcx, [rbp+5C0h+Buffer]; String1
0x1800096e2  mov     [rsp+6C0h+nSize], r8d
0x1800096e7  call    cs:__imp__wcsnicmp
0x1800096ed  test    eax, eax
0x1800096ef  jz      short loc_18000971D
0x1800096f1  mov     r8d, 8; MaxCount
0x1800096f7  lea     rdx, aWindir; "%WinDir%"
0x1800096fe  lea     rcx, [rbp+5C0h+Buffer]; String1
0x180009705  mov     [rsp+6C0h+nSize], r8d
0x18000970a  call    cs:__imp__wcsnicmp
0x180009710  test    eax, eax
0x180009712  jz      short loc_18000971D
0x180009714  mov     eax, r13d
0x180009717  mov     [rsp+6C0h+nSize], eax
0x18000971b  jmp     short loc_180009721
0x18000971d  mov     eax, [rsp+6C0h+nSize]
0x180009721  test    eax, eax
0x180009723  jz      loc_1800097F9
0x180009729  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18000972e  lea     rax, [rsp+6C0h+var_680]
0x180009733  mov     r9d, 0F003Fh; samDesired
0x180009739  mov     [rsp+6C0h+var_6A0], rax; phkResult
0x18000973e  xor     r8d, r8d; ulOptions
0x180009741  mov     [rsp+6C0h+var_680], r13
0x180009746  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000974d  call    cs:__imp_RegOpenKeyExW
0x180009753  mov     ebx, eax
0x180009755  test    eax, eax
0x180009757  jz      short loc_180009769
0x180009759  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18000975e  call    cs:__imp_RegCloseKey
0x180009764  jmp     loc_180009622
0x180009769  mov     r8, r14; Size
0x18000976c  lea     rcx, [rbp+5C0h+Data]; void *
0x180009773  xor     edx, edx; Val
0x180009775  call    memset_0
0x18000977a  mov     rcx, [rsp+6C0h+var_680]; hKey
0x18000977f  lea     rax, [rsp+6C0h+cbData]
0x180009784  mov     [rsp+6C0h+lpcbData], rax; lpcbData
0x180009789  lea     rdx, aSystemroot; "SystemRoot"
0x180009790  lea     rax, [rbp+5C0h+Data]
0x180009797  mov     [rsp+6C0h+cbData], r14d
0x18000979c  xor     r9d, r9d; lpType
0x18000979f  mov     [rsp+6C0h+var_6A0], rax; lpData
0x1800097a4  xor     r8d, r8d; lpReserved
0x1800097a7  call    cs:__imp_RegQueryValueExW
0x1800097ad  mov     rcx, [rsp+6C0h+var_680]; hKey
0x1800097b2  mov     ebx, eax
0x1800097b4  test    eax, eax
0x1800097b6  jz      short loc_1800097C0
0x1800097b8  call    cs:__imp_RegCloseKey
0x1800097be  jmp     short loc_180009759
0x1800097c0  call    cs:__imp_RegCloseKey
0x1800097c6  lea     r8, [rbp+5C0h+Data]; unsigned __int16 *
0x1800097cd  mov     rdx, r12; unsigned __int64
0x1800097d0  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x1800097d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800097da  mov     r10d, [rsp+6C0h+nSize]
0x1800097df  lea     r8, [rbp+5C0h+Buffer]
0x1800097e6  mov     rdx, r12; unsigned __int64
0x1800097e9  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x1800097ee  lea     r8, [r8+r10*2]; unsigned __int16 *
0x1800097f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097f7  jmp     short loc_18000980D
0x1800097f9  lea     r8, [rbp+5C0h+Buffer]; unsigned __int16 *
0x180009800  mov     rdx, r12; unsigned __int64
0x180009803  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x180009808  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000980d  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x180009812  call    cs:__imp_RegCloseKey
0x180009818  movzx   ecx, [rsp+6C0h+String2]
0x18000981d  lea     eax, [rcx-41h]
0x180009820  cmp     ax, 19h
0x180009824  jbe     short loc_180009830
0x180009826  sub     cx, 61h ; 'a'
0x18000982a  cmp     cx, 19h
0x18000982e  ja      short loc_180009862
0x180009830  cmp     [rsp+6C0h+var_66E], 3Ah ; ':'
0x180009836  jnz     short loc_180009862
0x180009838  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000983c  lea     rcx, [rsp+6C0h+String2]
0x180009841  mov     rax, rbx
0x180009844  inc     rax
0x180009847  cmp     [rcx+rax*2], r13w
0x18000984c  jnz     short loc_180009844
0x18000984e  mov     rcx, rbx
0x180009851  inc     rcx
0x180009854  cmp     [rsi+rcx*2], r13w
0x180009859  jnz     short loc_180009851
0x18000985b  add     eax, 2
0x18000985e  add     eax, ecx
0x180009860  jmp     short loc_18000988C
0x180009862  mov     eax, 800700A1h
0x180009867  jmp     loc_1800099D3
0x18000986c  call    __report_rangecheckfailure
0x180009872  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180009879  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000987d  mov     rax, rbx
0x180009880  inc     rax
0x180009883  cmp     [rcx+rax*2], r13w
0x180009888  jnz     short loc_180009880
0x18000988a  inc     eax
0x18000988c  mov     [rsp+6C0h+nSize], eax
0x180009890  mov     r12d, eax
0x180009893  mov     eax, 2
0x180009898  mul     r12
0x18000989b  cmovb   rax, rbx
0x18000989f  mov     rcx, rax; Size
0x1800098a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800098a7  mov     r14, rax
0x1800098aa  test    rax, rax
0x1800098ad  jnz     short loc_1800098B9
0x1800098af  mov     eax, 8007000Eh
0x1800098b4  jmp     loc_1800099D3
0x1800098b9  mov     [rax], r13w
0x1800098bd  test    r15d, r15d
0x1800098c0  jnz     short loc_180009900
0x1800098c2  mov     rax, rbx
0x1800098c5  inc     rax
0x1800098c8  cmp     [rsi+rax*2], r13w
0x1800098cd  jnz     short loc_1800098C5
0x1800098cf  lea     r13, [rax+1]
0x1800098d3  mov     eax, 2
0x1800098d8  mul     r13
0x1800098db  cmovb   rax, rbx
0x1800098df  mov     rcx, rax; Size
0x1800098e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800098e7  mov     rbx, rax
0x1800098ea  test    rax, rax
0x1800098ed  jnz     short loc_1800098F9
0x1800098ef  mov     rcx, r14; Block
0x1800098f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800098f7  jmp     short loc_1800098AF
0x1800098f9  xor     eax, eax
0x1800098fb  mov     [rbx], ax
0x1800098fe  jmp     short loc_180009902
0x180009900  xor     ebx, ebx
0x180009902  mov     rcx, [rdi+38h]; Block
0x180009906  test    rcx, rcx
0x180009909  jz      short loc_180009910
0x18000990b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009910  mov     rcx, [rdi+40h]; Block
0x180009914  test    rcx, rcx
0x180009917  jz      short loc_18000991E
0x180009919  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000991e  test    r15d, r15d
0x180009921  jz      short loc_180009978
0x180009923  mov     [rdi+40h], r14
0x180009927  xor     esi, esi
0x180009929  mov     [rdi+38h], rsi
0x18000992d  mov     rdx, r12; unsigned __int64
0x180009930  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180009937  mov     rcx, r14; unsigned __int16 *
0x18000993a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000993f  mov     rcx, [rdi+40h]; lpFileName
0x180009943  lea     edx, [rsi+1]; DesiredAccess
0x180009946  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x18000994b  mov     ebx, eax
0x18000994d  test    eax, eax
0x18000994f  jns     short loc_1800099CA
0x180009951  mov     rcx, [rdi+38h]; Block
0x180009955  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000995a  mov     rcx, [rdi+40h]; Block
0x18000995e  mov     [rdi+38h], rsi
0x180009962  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009967  mov     rcx, rdi; this
  ... truncated ...
```
