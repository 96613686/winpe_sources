# CGroupPolicySession::DeleteStaleLGPOsCallback(void *,uchar)

- ea: `0x18001d8b0`
- end: `0x18001dce8`
- name: `?DeleteStaleLGPOsCallback@CGroupPolicySession@@CAXPEAXE@Z`
- size: `1080`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a504`
- `0x18001d8b0`
- `0x18001ee6c`
- `0x18002c690`
- `0x180045660`
- `0x180075ec0`
- `0x1800877e4`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dc8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dc8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d8fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dab8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d8fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dab8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d94c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d94c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d979`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001da68`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001da68`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001dcdc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001dcdc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001dc05`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001dc05`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d91f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d91f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001daf0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001daf0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001db2c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001dbca`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001db2c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001dbca`

## string_xrefs

- `0x18001d918`: `%SystemRoot%\System32\GroupPolicyUsers`
- `0x18001dc44`: `DeleteStaleLGPOsCallback: FindNextFile() failed due to error %d, Could not complete deletion of stale LGPOs.`
- `0x18001dcc8`: `DeleteStaleLGPOsCallback: FindNextFile() failed due to error %d, Could not complete deletion of stale LGPOs.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CGroupPolicySession::DeleteStaleLGPOsCallback(void *a1)
{
  WCHAR *v1; // rbx
  WCHAR *ReferencedDomainName; // rdi
  struct _WIN32_FIND_DATAW *v3; // rsi
  WCHAR *v4; // rax
  WCHAR *v5; // r14
  __int64 v6; // rcx
  unsigned __int16 *v7; // r9
  int v8; // edx
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  __int64 v12; // r8
  int v13; // r10d
  wchar_t v14; // ax
  struct _WIN32_FIND_DATAW *v15; // rax
  HANDLE FirstFileW; // r15
  HLOCAL v17; // rax
  DWORD v18; // r13d
  HLOCAL v19; // rax
  DWORD LastError; // eax
  HLOCAL v21; // rax
  HLOCAL v22; // rax
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // r12
  DWORD v24; // eax
  DWORD v25; // eax
  PSID Sid; // [rsp+40h] [rbp-29h] BYREF
  DWORD v27; // [rsp+48h] [rbp-21h]
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-1Dh] BYREF
  LPWSTR Name; // [rsp+50h] [rbp-19h] BYREF
  LPWSTR v30; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v31; // [rsp+60h] [rbp-9h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v33; // [rsp+70h] [rbp+7h]
  WCHAR *v34; // [rsp+78h] [rbp+Fh]
  struct _WIN32_FIND_DATAW *v35; // [rsp+80h] [rbp+17h]
  DWORD cchReferencedDomainName; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = 0;
  Name = 0;
  ReferencedDomainName = 0;
  v30 = 0;
  v3 = 0;
  peUse = SidTypeUnknown;
  if ( !*((_QWORD *)a1 + 34) )
    return;
  v4 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
  v5 = v4;
  v34 = v4;
  if ( !v4 )
    goto LABEL_7;
  if ( !ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\GroupPolicyUsers", v4, 0x104u) )
    goto LABEL_7;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( (unsigned int)v6 >= 0x103 )
    goto LABEL_7;
  v7 = &v5[(unsigned int)v6];
  v31 = v7;
  v8 = 259 - v6;
  if ( *(v7 - 1) != 92 )
  {
    *v7++ = 92;
    v31 = v7;
    *v7 = 0;
    --v8;
  }
  if ( !v7 )
    goto LABEL_7;
  v9 = (unsigned int)(v8 + 1);
  v33 = v9;
  if ( v8 == -1 )
    goto LABEL_7;
  if ( v9 > 0x7FFFFFFF )
  {
    *v7 = 0;
    goto LABEL_7;
  }
  v10 = 2147483646;
  v11 = L"S-*";
  v12 = (unsigned int)v9;
  v13 = 0;
  while ( v10 )
  {
    v14 = *v11;
    if ( !*v11 )
    {
      if ( !v12 )
      {
LABEL_25:
        --v7;
        v13 = -2147024774;
        break;
      }
      break;
    }
    ++v11;
    *v7++ = v14;
    --v10;
    if ( !--v12 )
      goto LABEL_25;
  }
  *v7 = 0;
  if ( v13 < 0 )
    goto LABEL_7;
  v15 = (struct _WIN32_FIND_DATAW *)LocalAlloc(0x40u, 0x250u);
  v3 = v15;
  v35 = v15;
  if ( !v15 )
    goto LABEL_7;
  FirstFileW = FindFirstFileW(v5, v15);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_7;
  v17 = LocalAlloc(0x40u, 0x40u);
  XPtrLF<unsigned short>::operator=(&Name, v17);
  v1 = Name;
  if ( !Name )
    goto LABEL_55;
  v27 = 32;
  v18 = 128;
  v19 = LocalAlloc(0x40u, 0x100u);
  XPtrLF<unsigned short>::operator=(&v30, v19);
  ReferencedDomainName = v30;
  if ( !v30 )
    goto LABEL_55;
  do
  {
    Sid = 0;
    if ( (v3->dwFileAttributes & 0x10) == 0 )
      goto LABEL_42;
    if ( !ConvertStringSidToSidW(v3->cFileName, &Sid) )
      goto LABEL_42;
    cchName = v27;
    cchReferencedDomainName = v18;
    if ( LookupAccountSidW(0, Sid, v1, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      goto LABEL_42;
    LastError = GetLastError();
    if ( LastError != 122 )
      goto LABEL_40;
    v27 = cchName;
    v21 = LocalAlloc(0x40u, 2LL * cchName);
    XPtrLF<unsigned short>::operator=(&Name, v21);
    v1 = Name;
    if ( !Name
      || (v18 = cchReferencedDomainName,
          v22 = LocalAlloc(0x40u, 2LL * cchReferencedDomainName),
          XPtrLF<unsigned short>::operator=(&v30, v22),
          (ReferencedDomainName = v30) == 0) )
    {
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&Sid);
      goto LABEL_55;
    }
    if ( !LookupAccountSidW(0, Sid, v1, &cchName, v30, &cchReferencedDomainName, &peUse) )
    {
      LastError = GetLastError();
LABEL_40:
      if ( LastError == 1332 && (int)StringCchCopyW(v31, v33, v3->cFileName) >= 0 )
      {
        XEnterCritSec::XEnterCritSec((XEnterCritSec *)&lpCriticalSection, *((struct _RTL_CRITICAL_SECTION **)a1 + 34));
        DeleteDirectory(v5);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
    }
LABEL_42:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&Sid);
  }
  while ( FindNextFileW(FirstFileW, v3) );
  if ( GetLastError() != 18 && *(_DWORD *)&g_dwDebugLevel )
  {
    v23 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v24 = GetLastError();
      v23(
        2u,
        L"DeleteStaleLGPOsCallback: FindNextFile() failed due to error %d, Could not complete deletion of stale LGPOs.",
        v24);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v25 = GetLastError();
      RedirectDebugMsg(
        2u,
        L"DeleteStaleLGPOsCallback: FindNextFile() failed due to error %d, Could not complete deletion of stale LGPOs.",
        v25);
    }
  }
LABEL_55:
  FindClose(FirstFileW);
LABEL_7:
  if ( v3 )
    LocalFree(v3);
  if ( ReferencedDomainName )
    LocalFree(ReferencedDomainName);
  if ( v1 )
    LocalFree(v1);
  if ( v5 )
    LocalFree(v5);
}

```

## disassembly

```asm
0x18001d8b0  mov     [rsp-8+arg_8], rbx
0x18001d8b5  mov     [rsp-8+arg_0], rcx
0x18001d8ba  push    rbp
0x18001d8bb  push    rsi
0x18001d8bc  push    rdi
0x18001d8bd  push    r12
0x18001d8bf  push    r13
0x18001d8c1  push    r14
0x18001d8c3  push    r15
0x18001d8c5  lea     rbp, [rsp-27h]
0x18001d8ca  sub     rsp, 90h
0x18001d8d1  xor     ebx, ebx
0x18001d8d3  mov     [rbp+57h+Name], rbx
0x18001d8d7  xor     edi, edi
0x18001d8d9  mov     [rbp+57h+var_68], rdi
0x18001d8dd  xor     esi, esi
0x18001d8df  mov     [rbp+57h+var_74], 8
0x18001d8e6  cmp     [rcx+110h], rsi
0x18001d8ed  jz      loc_18001DC5A
0x18001d8f3  mov     edx, 208h; uBytes
0x18001d8f8  mov     ecx, 40h ; '@'; uFlags
0x18001d8fd  call    cs:__imp_LocalAlloc
0x18001d903  mov     r14, rax
0x18001d906  mov     [rbp+57h+var_48], rax
0x18001d90a  test    rax, rax
0x18001d90d  jz      short loc_18001D944
0x18001d90f  mov     r8d, 104h; nSize
0x18001d915  mov     rdx, rax; lpDst
0x18001d918  lea     rcx, Src; "%SystemRoot%\\System32\\GroupPolicyUser"...
0x18001d91f  call    cs:__imp_ExpandEnvironmentStringsW
0x18001d925  test    eax, eax
0x18001d927  jz      short loc_18001D944
0x18001d929  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d930  inc     rcx
0x18001d933  cmp     word ptr [r14+rcx*2], 0
0x18001d939  jnz     short loc_18001D930
0x18001d93b  mov     edx, 103h
0x18001d940  cmp     ecx, edx
0x18001d942  jb      short loc_18001D99A
0x18001d944  test    rsi, rsi
0x18001d947  jz      short loc_18001D953
0x18001d949  mov     rcx, rsi; hMem
0x18001d94c  call    cs:__imp_LocalFree
0x18001d952  nop
0x18001d953  test    rdi, rdi
0x18001d956  jz      short loc_18001D962
0x18001d958  mov     rcx, rdi; hMem
0x18001d95b  call    cs:__imp_LocalFree
0x18001d961  nop
0x18001d962  test    rbx, rbx
0x18001d965  jz      short loc_18001D971
0x18001d967  mov     rcx, rbx; hMem
0x18001d96a  call    cs:__imp_LocalFree
0x18001d970  nop
0x18001d971  test    r14, r14
0x18001d974  jz      short loc_18001D97F
0x18001d976  mov     rcx, r14; hMem
0x18001d979  call    cs:__imp_LocalFree
0x18001d97f  mov     rbx, [rsp+0C0h+arg_8]
0x18001d987  add     rsp, 90h
0x18001d98e  pop     r15
0x18001d990  pop     r14
0x18001d992  pop     r13
0x18001d994  pop     r12
0x18001d996  pop     rdi
0x18001d997  pop     rsi
0x18001d998  pop     rbp
0x18001d999  retn
0x18001d99a  mov     eax, ecx
0x18001d99c  lea     r9, [r14+rax*2]
0x18001d9a0  mov     [rbp+57h+var_60], r9
0x18001d9a4  sub     edx, ecx
0x18001d9a6  cmp     word ptr [r9-2], 5Ch ; '\'
0x18001d9ac  jz      short loc_18001D9C4
0x18001d9ae  mov     word ptr [r9], 5Ch ; '\'
0x18001d9b4  add     r9, 2
0x18001d9b8  mov     [rbp+57h+var_60], r9
0x18001d9bc  xor     eax, eax
0x18001d9be  mov     [r9], ax
0x18001d9c2  dec     edx
0x18001d9c4  test    r9, r9
0x18001d9c7  jz      loc_18001D944
0x18001d9cd  lea     eax, [rdx+1]
0x18001d9d0  mov     [rbp+57h+var_50], rax
0x18001d9d4  test    rax, rax
0x18001d9d7  jz      loc_18001D944
0x18001d9dd  cmp     rax, 7FFFFFFFh
0x18001d9e3  ja      loc_18001DC95
0x18001d9e9  mov     ecx, 7FFFFFFEh
0x18001d9ee  lea     rdx, aS; "S-*"
0x18001d9f5  mov     r8d, eax
0x18001d9f8  xor     r10d, r10d
0x18001d9fb  nop     dword ptr [rax+rax+00h]
0x18001da00  test    rcx, rcx
0x18001da03  jz      short loc_18001DA33
0x18001da05  movzx   eax, word ptr [rdx]
0x18001da08  test    ax, ax
0x18001da0b  jz      short loc_18001DA2E
0x18001da0d  add     rdx, 2
0x18001da11  mov     [r9], ax
0x18001da15  add     r9, 2
0x18001da19  dec     rcx
0x18001da1c  sub     r8, 1
0x18001da20  jnz     short loc_18001DA00
0x18001da22  sub     r9, 2
0x18001da26  mov     r10d, 8007007Ah
0x18001da2c  jmp     short loc_18001DA33
0x18001da2e  test    r8, r8
0x18001da31  jz      short loc_18001DA22
0x18001da33  xor     eax, eax
0x18001da35  mov     [r9], ax
0x18001da39  test    r10d, r10d
0x18001da3c  js      loc_18001D944
0x18001da42  mov     edx, 250h; uBytes
0x18001da47  mov     ecx, 40h ; '@'; uFlags
0x18001da4c  call    cs:__imp_LocalAlloc
0x18001da52  mov     rsi, rax
0x18001da55  mov     [rbp+57h+var_40], rax
0x18001da59  test    rax, rax
0x18001da5c  jz      loc_18001D944
0x18001da62  mov     rdx, rax; lpFindFileData
0x18001da65  mov     rcx, r14; lpFileName
0x18001da68  call    cs:__imp_FindFirstFileW
0x18001da6e  mov     r15, rax
0x18001da71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001da75  jz      loc_18001D944
0x18001da7b  mov     edx, 40h ; '@'; uBytes
0x18001da80  mov     ecx, edx; uFlags
0x18001da82  call    cs:__imp_LocalAlloc
0x18001da88  mov     rdx, rax
0x18001da8b  lea     rcx, [rbp+57h+Name]
0x18001da8f  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18001da94  mov     rbx, [rbp+57h+Name]
0x18001da98  test    rbx, rbx
0x18001da9b  jz      loc_18001DCD9
0x18001daa1  mov     [rbp+57h+var_78], 20h ; ' '
0x18001daa8  mov     edx, 100h; uBytes
0x18001daad  mov     ecx, 40h ; '@'; uFlags
0x18001dab2  mov     r13d, 80h
0x18001dab8  call    cs:__imp_LocalAlloc
0x18001dabe  mov     rdx, rax
0x18001dac1  lea     rcx, [rbp+57h+var_68]
0x18001dac5  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18001daca  mov     rdi, [rbp+57h+var_68]
0x18001dace  test    rdi, rdi
0x18001dad1  jz      loc_18001DCD9
0x18001dad7  mov     [rbp+57h+Sid], 0
0x18001dadf  test    byte ptr [rsi], 10h
0x18001dae2  jz      loc_18001DBF6
0x18001dae8  lea     rdx, [rbp+57h+Sid]; Sid
0x18001daec  lea     rcx, [rsi+2Ch]; StringSid
0x18001daf0  call    cs:__imp_ConvertStringSidToSidW
0x18001daf6  test    eax, eax
0x18001daf8  jz      loc_18001DBF6
0x18001dafe  mov     eax, [rbp+57h+var_78]
0x18001db01  mov     [rbp+57h+cchName], eax
0x18001db04  mov     [rbp+57h+arg_10], r13d
0x18001db08  lea     rax, [rbp+57h+var_74]
0x18001db0c  mov     [rsp+0C0h+peUse], rax; peUse
0x18001db11  lea     rax, [rbp+57h+arg_10]
0x18001db15  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001db1a  mov     [rsp+0C0h+ReferencedDomainName], rdi; ReferencedDomainName
0x18001db1f  lea     r9, [rbp+57h+cchName]; cchName
0x18001db23  mov     r8, rbx; Name
0x18001db26  mov     rdx, [rbp+57h+Sid]; Sid
0x18001db2a  xor     ecx, ecx; lpSystemName
0x18001db2c  call    cs:__imp_LookupAccountSidW
0x18001db32  test    eax, eax
0x18001db34  jnz     loc_18001DBF6
0x18001db3a  call    cs:__imp_GetLastError
0x18001db40  cmp     eax, 7Ah ; 'z'
0x18001db43  jnz     loc_18001DBDA
0x18001db49  mov     eax, [rbp+57h+cchName]
0x18001db4c  mov     [rbp+57h+var_78], eax
0x18001db4f  mov     edx, eax
0x18001db51  add     rdx, rdx; uBytes
0x18001db54  mov     ecx, 40h ; '@'; uFlags
0x18001db59  call    cs:__imp_LocalAlloc
0x18001db5f  mov     rdx, rax
0x18001db62  lea     rcx, [rbp+57h+Name]
0x18001db66  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18001db6b  mov     rbx, [rbp+57h+Name]
0x18001db6f  test    rbx, rbx
0x18001db72  jz      loc_18001DCA0
0x18001db78  mov     r13d, [rbp+57h+arg_10]
0x18001db7c  mov     edx, r13d
0x18001db7f  add     rdx, rdx; uBytes
0x18001db82  mov     ecx, 40h ; '@'; uFlags
0x18001db87  call    cs:__imp_LocalAlloc
0x18001db8d  mov     rdx, rax
0x18001db90  lea     rcx, [rbp+57h+var_68]
0x18001db94  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18001db99  mov     rdi, [rbp+57h+var_68]
0x18001db9d  test    rdi, rdi
0x18001dba0  jz      loc_18001DCA0
0x18001dba6  lea     rax, [rbp+57h+var_74]
0x18001dbaa  mov     [rsp+0C0h+peUse], rax; peUse
0x18001dbaf  lea     rax, [rbp+57h+arg_10]
0x18001dbb3  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001dbb8  mov     [rsp+0C0h+ReferencedDomainName], rdi; ReferencedDomainName
0x18001dbbd  lea     r9, [rbp+57h+cchName]; cchName
0x18001dbc1  mov     r8, rbx; Name
0x18001dbc4  mov     rdx, [rbp+57h+Sid]; Sid
0x18001dbc8  xor     ecx, ecx; lpSystemName
0x18001dbca  call    cs:__imp_LookupAccountSidW
0x18001dbd0  test    eax, eax
0x18001dbd2  jnz     short loc_18001DBF6
0x18001dbd4  call    cs:__imp_GetLastError
0x18001dbda  cmp     eax, 534h
0x18001dbdf  jnz     short loc_18001DBF6
0x18001dbe1  lea     r8, [rsi+2Ch]; unsigned __int16 *
0x18001dbe5  mov     rdx, [rbp+57h+var_50]; unsigned __int64
0x18001dbe9  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18001dbed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001dbf2  test    eax, eax
0x18001dbf4  jns     short loc_18001DC5F
0x18001dbf6  lea     rcx, [rbp+57h+Sid]
0x18001dbfa  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001dbff  mov     rdx, rsi; lpFindFileData
0x18001dc02  mov     rcx, r15; hFindFile
0x18001dc05  call    cs:__imp_FindNextFileW
0x18001dc0b  test    eax, eax
0x18001dc0d  jnz     loc_18001DAD7
0x18001dc13  call    cs:__imp_GetLastError
0x18001dc19  cmp     eax, 12h
0x18001dc1c  jz      loc_18001DCD9
0x18001dc22  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18001dc29  jz      loc_18001DCD9
0x18001dc2f  mov     r12, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001dc36  test    r12, r12
0x18001dc39  jz      short loc_18001DCAB
0x18001dc3b  call    cs:__imp_GetLastError
0x18001dc41  mov     r8d, eax
0x18001dc44  lea     rdx, aDeletestalelgp; "DeleteStaleLGPOsCallback: FindNextFile("...
0x18001dc4b  mov     ecx, 2
0x18001dc50  mov     rax, r12
0x18001dc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc58  jmp     short loc_18001DCD9
0x18001dc5a  jmp     loc_18001D97F
0x18001dc5f  mov     rax, [rbp+57h+arg_0]
0x18001dc63  mov     rdx, [rax+110h]; struct _RTL_CRITICAL_SECTION *
0x18001dc6a  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18001dc6e  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x18001dc73  nop
0x18001dc74  mov     rcx, r14; unsigned __int16 *
0x18001dc77  call    ?DeleteDirectory@@YAHPEAG@Z; DeleteDirectory(ushort *)
0x18001dc7c  nop
0x18001dc7d  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18001dc81  test    rcx, rcx
0x18001dc84  jz      loc_18001DBF6
0x18001dc8a  call    cs:__imp_LeaveCriticalSection
0x18001dc90  jmp     loc_18001DBF6
0x18001dc95  xor     eax, eax
0x18001dc97  mov     [r9], ax
0x18001dc9b  jmp     loc_18001D944
0x18001dca0  lea     rcx, [rbp+57h+Sid]
0x18001dca4  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001dca9  jmp     short loc_18001DCD9
0x18001dcab  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18001dcb3  jz      short loc_18001DCD9
0x18001dcb5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001dcbd  jz      short loc_18001DCD9
0x18001dcbf  call    cs:__imp_GetLastError
0x18001dcc5  mov     r8d, eax
0x18001dcc8  lea     rdx, aDeletestalelgp; "DeleteStaleLGPOsCallback: FindNextFile("...
0x18001dccf  mov     ecx, 2; unsigned int
0x18001dcd4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001dcd9  mov     rcx, r15; hFindFile
0x18001dcdc  call    cs:__imp_FindClose
0x18001dce2  jmp     loc_18001D944
```
