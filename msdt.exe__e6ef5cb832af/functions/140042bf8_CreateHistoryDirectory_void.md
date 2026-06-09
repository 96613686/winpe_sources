# CreateHistoryDirectory(void)

- ea: `0x140042bf8`
- end: `0x14004301b`
- name: `?CreateHistoryDirectory@@YAJXZ`
- size: `1059`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140043a14`

## callees

- `0x140006fe0`
- `0x14000706c`
- `0x1400070b0`
- `0x140020420`
- `0x140021f70`
- `0x1400407b0`
- `0x140040a40`
- `0x140041020`
- `0x14004175c`
- `0x140042bf8`
- `0x14004331c`
- `0x14004a13c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140042eb9`
- `KERNEL32!GetLastError` at `0x140042ed1`
- `KERNEL32!GetLastError` at `0x140042eb9`
- `KERNEL32!GetLastError` at `0x140042ed1`
- `KERNEL32!HeapAlloc` at `0x140042c6c`
- `KERNEL32!HeapAlloc` at `0x140042cc5`
- `KERNEL32!HeapAlloc` at `0x140042cf3`
- `KERNEL32!HeapAlloc` at `0x140042d24`
- `KERNEL32!HeapAlloc` at `0x140042c6c`
- `KERNEL32!HeapAlloc` at `0x140042cc5`
- `KERNEL32!HeapAlloc` at `0x140042cf3`
- `KERNEL32!HeapAlloc` at `0x140042d24`
- `KERNEL32!HeapFree` at `0x140042f44`
- `KERNEL32!HeapFree` at `0x140042fa9`
- `KERNEL32!HeapFree` at `0x140042fce`
- `KERNEL32!HeapFree` at `0x140042ff3`
- `KERNEL32!HeapFree` at `0x140042f44`
- `KERNEL32!HeapFree` at `0x140042fa9`
- `KERNEL32!HeapFree` at `0x140042fce`
- `KERNEL32!HeapFree` at `0x140042ff3`
- `KERNEL32!GetProcessHeap` at `0x140042c53`
- `KERNEL32!GetProcessHeap` at `0x140042cb1`
- `KERNEL32!GetProcessHeap` at `0x140042cdf`
- `KERNEL32!GetProcessHeap` at `0x140042d10`
- `KERNEL32!GetProcessHeap` at `0x140042f30`
- `KERNEL32!GetProcessHeap` at `0x140042f95`
- `KERNEL32!GetProcessHeap` at `0x140042fba`
- `KERNEL32!GetProcessHeap` at `0x140042fdf`
- `KERNEL32!GetProcessHeap` at `0x140042c53`
- `KERNEL32!GetProcessHeap` at `0x140042cb1`
- `KERNEL32!GetProcessHeap` at `0x140042cdf`
- `KERNEL32!GetProcessHeap` at `0x140042d10`
- `KERNEL32!GetProcessHeap` at `0x140042f30`
- `KERNEL32!GetProcessHeap` at `0x140042f95`
- `KERNEL32!GetProcessHeap` at `0x140042fba`
- `KERNEL32!GetProcessHeap` at `0x140042fdf`
- `KERNEL32!LocalFree` at `0x140042f7c`
- `KERNEL32!LocalFree` at `0x140042f7c`
- `KERNEL32!CreateDirectoryW` at `0x140042ea5`
- `KERNEL32!CreateDirectoryW` at `0x140042ea5`
- `OLEAUT32!__imp_SysFreeString` at `0x140042f67`
- `OLEAUT32!__imp_SysFreeString` at `0x140042f67`

## string_xrefs

- `0x140042c8b`: `CreateHistoryDirectory`
- `0x140042ef6`: `CreateHistoryDirectory`

## pseudocode

```c
__int64 CreateHistoryDirectory(void)
{
  unsigned __int16 *v0; // rsi
  unsigned __int16 *v1; // r15
  unsigned __int16 *v2; // rdi
  OLECHAR *v3; // r12
  int DirectoryW; // eax
  unsigned int v5; // ebx
  int v6; // r9d
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  const unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned int i; // r14d
  signed int LastError; // eax
  WCHAR *v17; // r14
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  __int64 v23; // [rsp+20h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v26; // [rsp+88h] [rbp+38h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v0 = 0;
  IsMember = 0;
  v1 = 0;
  v26 = 0;
  v2 = 0;
  v3 = 0;
  DirectoryW = IsAdminToken(&IsMember);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 58;
LABEL_7:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryDirectory", v6, DirectoryW);
LABEL_46:
    v17 = (WCHAR *)g_HistoryDirectory;
    if ( g_HistoryDirectory )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v17);
      g_HistoryDirectory = 0;
    }
    goto LABEL_49;
  }
  if ( g_HistoryDirectory )
  {
LABEL_48:
    v5 = 0;
    goto LABEL_49;
  }
  v7 = GetProcessHeap();
  v2 = (unsigned __int16 *)HeapAlloc(v7, 0, 0x208u);
  if ( !v2 )
  {
    v6 = 66;
LABEL_6:
    DirectoryW = -2147024882;
    v5 = -2147024882;
    goto LABEL_7;
  }
  *v2 = 0;
  v8 = GetProcessHeap();
  v1 = (unsigned __int16 *)HeapAlloc(v8, 0, 0x208u);
  if ( !v1 )
  {
    v6 = 69;
    goto LABEL_6;
  }
  v9 = GetProcessHeap();
  v0 = (unsigned __int16 *)HeapAlloc(v9, 0, 0x208u);
  if ( !v0 )
  {
    v6 = 70;
    goto LABEL_6;
  }
  v10 = GetProcessHeap();
  g_HistoryDirectory = (LPCWSTR)HeapAlloc(v10, 0, 0x208u);
  if ( !g_HistoryDirectory )
  {
    v6 = 71;
    goto LABEL_6;
  }
  v11 = L"%LocalAppData%\\ElevatedDiagnostics\\";
  if ( !IsMember )
    v11 = L"%LocalAppData%\\Diagnostics\\";
  DirectoryW = StringCchCopyW(v1, 0x104u, v11);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 80;
    goto LABEL_7;
  }
  v12 = Packages_ID();
  v13 = L"DefaultID";
  v3 = v12;
  if ( v12 )
    v13 = v12;
  DirectoryW = HashString(v13, &v26);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 92;
    goto LABEL_7;
  }
  DirectoryW = StringCchPrintfW(v0, 0x104u, L"%s%u\\", v1, v26);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 95;
    goto LABEL_7;
  }
  DirectoryW = ExpandVariables(v2, 0x104u, v0);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 98;
    goto LABEL_7;
  }
  DirectoryW = CreateDirectoryW(v2);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 101;
    goto LABEL_7;
  }
  DirectoryW = GetTimestamp(v0, v14);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 107;
    goto LABEL_7;
  }
  DirectoryW = StringCchCatW(v2, 0x104u, v0);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 110;
    goto LABEL_7;
  }
  DirectoryW = CreateSecurityDescriptor(&SecurityAttributes);
  v5 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v6 = 113;
    goto LABEL_7;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x4C4B40 )
    {
      v5 = 1;
      goto LABEL_46;
    }
    LODWORD(v23) = i;
    DirectoryW = StringCchPrintfW((unsigned __int16 *)g_HistoryDirectory, 0x104u, L"%s.%03d\\", v2, v23);
    v5 = DirectoryW;
    if ( DirectoryW < 0 )
    {
      v6 = 125;
      goto LABEL_7;
    }
    if ( CreateDirectoryW(g_HistoryDirectory, &SecurityAttributes) )
      goto LABEL_48;
    if ( GetLastError() != 183 )
      break;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryDirectory", 140, v5);
  if ( v5 )
    goto LABEL_46;
LABEL_49:
  if ( v3 )
    SysFreeString(v3);
  if ( SecurityAttributes.lpSecurityDescriptor )
  {
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
    SecurityAttributes.lpSecurityDescriptor = 0;
  }
  if ( v2 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v2);
  }
  if ( v1 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v1);
  }
  if ( v0 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v0);
  }
  return v5;
}

```

## disassembly

```asm
0x140042bf8  mov     [rsp-28h+arg_10], rbx
0x140042bfd  mov     [rsp-28h+arg_18], rsi
0x140042c02  push    rbp
0x140042c03  push    rdi
0x140042c04  push    r12
0x140042c06  push    r14
0x140042c08  push    r15
0x140042c0a  mov     rbp, rsp
0x140042c0d  sub     rsp, 50h
0x140042c11  xorps   xmm0, xmm0
0x140042c14  mov     qword ptr [rbp+SecurityAttributes.nLength], 0
0x140042c1c  xor     esi, esi
0x140042c1e  lea     rcx, [rbp+IsMember]; IsMember
0x140042c22  movdqu  xmmword ptr [rbp+SecurityAttributes.lpSecurityDescriptor], xmm0
0x140042c27  mov     [rbp+IsMember], esi
0x140042c2a  xor     r15d, r15d
0x140042c2d  mov     [rbp+arg_8], esi
0x140042c30  xor     edi, edi
0x140042c32  xor     r12d, r12d
0x140042c35  call    ?IsAdminToken@@YAJPEAH@Z; IsAdminToken(int *)
0x140042c3a  mov     ebx, eax
0x140042c3c  test    eax, eax
0x140042c3e  jns     short loc_140042C46
0x140042c40  lea     r9d, [rsi+3Ah]
0x140042c44  jmp     short loc_140042C8B
0x140042c46  cmp     cs:?g_HistoryDirectory@@3PEAGEA, rsi; ushort * g_HistoryDirectory
0x140042c4d  jnz     loc_140042F5D
0x140042c53  call    cs:__imp_GetProcessHeap
0x140042c5a  nop     dword ptr [rax+rax+00h]
0x140042c5f  mov     ebx, 208h
0x140042c64  xor     edx, edx; dwFlags
0x140042c66  mov     rcx, rax; hHeap
0x140042c69  mov     r8d, ebx; dwBytes
0x140042c6c  call    cs:__imp_HeapAlloc
0x140042c73  nop     dword ptr [rax+rax+00h]
0x140042c78  mov     rdi, rax
0x140042c7b  test    rax, rax
0x140042c7e  jnz     short loc_140042CAC
0x140042c80  lea     r9d, [rax+42h]
0x140042c84  mov     eax, 8007000Eh
0x140042c89  mov     ebx, eax
0x140042c8b  lea     r8, aCreatehistoryd; "CreateHistoryDirectory"
0x140042c92  mov     [rsp+50h+var_30], eax
0x140042c96  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042c9d  mov     ecx, 1; Level
0x140042ca2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140042ca7  jmp     loc_140042F24
0x140042cac  xor     eax, eax
0x140042cae  mov     [rdi], ax
0x140042cb1  call    cs:__imp_GetProcessHeap
0x140042cb8  nop     dword ptr [rax+rax+00h]
0x140042cbd  mov     r8, rbx; dwBytes
0x140042cc0  xor     edx, edx; dwFlags
0x140042cc2  mov     rcx, rax; hHeap
0x140042cc5  call    cs:__imp_HeapAlloc
0x140042ccc  nop     dword ptr [rax+rax+00h]
0x140042cd1  mov     r15, rax
0x140042cd4  test    rax, rax
0x140042cd7  jnz     short loc_140042CDF
0x140042cd9  lea     r9d, [rax+45h]
0x140042cdd  jmp     short loc_140042C84
0x140042cdf  call    cs:__imp_GetProcessHeap
0x140042ce6  nop     dword ptr [rax+rax+00h]
0x140042ceb  mov     r8, rbx; dwBytes
0x140042cee  xor     edx, edx; dwFlags
0x140042cf0  mov     rcx, rax; hHeap
0x140042cf3  call    cs:__imp_HeapAlloc
0x140042cfa  nop     dword ptr [rax+rax+00h]
0x140042cff  mov     rsi, rax
0x140042d02  test    rax, rax
0x140042d05  jnz     short loc_140042D10
0x140042d07  lea     r9d, [rax+46h]
0x140042d0b  jmp     loc_140042C84
0x140042d10  call    cs:__imp_GetProcessHeap
0x140042d17  nop     dword ptr [rax+rax+00h]
0x140042d1c  mov     r8, rbx; dwBytes
0x140042d1f  xor     edx, edx; dwFlags
0x140042d21  mov     rcx, rax; hHeap
0x140042d24  call    cs:__imp_HeapAlloc
0x140042d2b  nop     dword ptr [rax+rax+00h]
0x140042d30  mov     cs:?g_HistoryDirectory@@3PEAGEA, rax; ushort * g_HistoryDirectory
0x140042d37  test    rax, rax
0x140042d3a  jnz     short loc_140042D45
0x140042d3c  lea     r9d, [rax+47h]
0x140042d40  jmp     loc_140042C84
0x140042d45  cmp     [rbp+IsMember], r12d
0x140042d49  lea     rax, aLocalappdataDi; "%LocalAppData%\\Diagnostics\\"
0x140042d50  lea     r8, aLocalappdataEl; "%LocalAppData%\\ElevatedDiagnostics\\"
0x140042d57  mov     r14d, 104h
0x140042d5d  cmovz   r8, rax; unsigned __int16 *
0x140042d61  mov     edx, r14d; unsigned __int64
0x140042d64  mov     rcx, r15; unsigned __int16 *
0x140042d67  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140042d6c  mov     ebx, eax
0x140042d6e  test    eax, eax
0x140042d70  jns     short loc_140042D7D
0x140042d72  mov     r9d, 50h ; 'P'
0x140042d78  jmp     loc_140042C8B
0x140042d7d  call    ?Packages_ID@@YAPEAGXZ; Packages_ID(void)
0x140042d82  test    rax, rax
0x140042d85  lea     rcx, aDefaultid; "DefaultID"
0x140042d8c  lea     rdx, [rbp+arg_8]; unsigned int *
0x140042d90  mov     r12, rax
0x140042d93  cmovnz  rcx, rax; unsigned __int16 *
0x140042d97  call    ?HashString@@YAJPEBGPEAK@Z; HashString(ushort const *,ulong *)
0x140042d9c  mov     ebx, eax
0x140042d9e  test    eax, eax
0x140042da0  jns     short loc_140042DAD
0x140042da2  mov     r9d, 5Ch ; '\'
0x140042da8  jmp     loc_140042C8B
0x140042dad  mov     eax, [rbp+arg_8]
0x140042db0  lea     r8, aSU_1; "%s%u\\"
0x140042db7  mov     r9, r15
0x140042dba  mov     [rsp+50h+var_30], eax
0x140042dbe  mov     rdx, r14; unsigned __int64
0x140042dc1  mov     rcx, rsi; unsigned __int16 *
0x140042dc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140042dc9  mov     ebx, eax
0x140042dcb  test    eax, eax
0x140042dcd  jns     short loc_140042DDA
0x140042dcf  mov     r9d, 5Fh ; '_'
0x140042dd5  jmp     loc_140042C8B
0x140042dda  mov     r8, rsi; lpSrc
0x140042ddd  mov     rdx, r14; unsigned __int64
0x140042de0  mov     rcx, rdi; unsigned __int16 *
0x140042de3  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140042de8  mov     ebx, eax
0x140042dea  test    eax, eax
0x140042dec  jns     short loc_140042DF9
0x140042dee  mov     r9d, 62h ; 'b'
0x140042df4  jmp     loc_140042C8B
0x140042df9  mov     rcx, rdi; lpSrc
0x140042dfc  call    ?CreateDirectoryW@@YAJPEBG@Z; CreateDirectoryW(ushort const *)
0x140042e01  mov     ebx, eax
0x140042e03  test    eax, eax
0x140042e05  jns     short loc_140042E12
0x140042e07  mov     r9d, 65h ; 'e'
0x140042e0d  jmp     loc_140042C8B
0x140042e12  mov     rcx, rsi; unsigned __int16 *
0x140042e15  call    ?GetTimestamp@@YAJPEAG_K@Z; GetTimestamp(ushort *,unsigned __int64)
0x140042e1a  mov     ebx, eax
0x140042e1c  test    eax, eax
0x140042e1e  jns     short loc_140042E2B
0x140042e20  mov     r9d, 6Bh ; 'k'
0x140042e26  jmp     loc_140042C8B
0x140042e2b  mov     r8, rsi; unsigned __int16 *
0x140042e2e  mov     rdx, r14; unsigned __int64
0x140042e31  mov     rcx, rdi; unsigned __int16 *
0x140042e34  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140042e39  mov     ebx, eax
0x140042e3b  test    eax, eax
0x140042e3d  jns     short loc_140042E4A
0x140042e3f  mov     r9d, 6Eh ; 'n'
0x140042e45  jmp     loc_140042C8B
0x140042e4a  lea     rcx, [rbp+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x140042e4e  call    ?CreateSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; CreateSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x140042e53  mov     ebx, eax
0x140042e55  test    eax, eax
0x140042e57  jns     short loc_140042E64
0x140042e59  mov     r9d, 71h ; 'q'
0x140042e5f  jmp     loc_140042C8B
0x140042e64  xor     r14d, r14d
0x140042e67  cmp     r14d, 4C4B40h
0x140042e6e  jnb     loc_140042F1F
0x140042e74  mov     rcx, cs:?g_HistoryDirectory@@3PEAGEA; unsigned __int16 *
0x140042e7b  lea     r8, aS03d; "%s.%03d\\"
0x140042e82  mov     r9, rdi
0x140042e85  mov     [rsp+50h+var_30], r14d
0x140042e8a  mov     edx, 104h; unsigned __int64
0x140042e8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140042e94  mov     ebx, eax
0x140042e96  test    eax, eax
0x140042e98  js      short loc_140042F14
0x140042e9a  mov     rcx, cs:?g_HistoryDirectory@@3PEAGEA; lpPathName
0x140042ea1  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x140042ea5  call    cs:__imp_CreateDirectoryW
0x140042eac  nop     dword ptr [rax+rax+00h]
0x140042eb1  test    eax, eax
0x140042eb3  jnz     loc_140042F5D
0x140042eb9  call    cs:__imp_GetLastError
0x140042ec0  nop     dword ptr [rax+rax+00h]
0x140042ec5  cmp     eax, 0B7h
0x140042eca  jnz     short loc_140042ED1
0x140042ecc  inc     r14d
0x140042ecf  jmp     short loc_140042E67
0x140042ed1  call    cs:__imp_GetLastError
0x140042ed8  nop     dword ptr [rax+rax+00h]
0x140042edd  mov     ebx, eax
0x140042edf  test    eax, eax
0x140042ee1  jle     short loc_140042EEC
0x140042ee3  movzx   ebx, ax
0x140042ee6  or      ebx, 80070000h
0x140042eec  mov     r9d, 8Ch
0x140042ef2  mov     [rsp+50h+var_30], ebx
0x140042ef6  lea     r8, aCreatehistoryd; "CreateHistoryDirectory"
0x140042efd  mov     ecx, 1; Level
0x140042f02  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042f09  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140042f0e  test    ebx, ebx
0x140042f10  jz      short loc_140042F5F
0x140042f12  jmp     short loc_140042F24
0x140042f14  mov     r9d, 7Dh ; '}'
0x140042f1a  jmp     loc_140042C8B
0x140042f1f  mov     ebx, 1
0x140042f24  mov     r14, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x140042f2b  test    r14, r14
0x140042f2e  jz      short loc_140042F5F
0x140042f30  call    cs:__imp_GetProcessHeap
0x140042f37  nop     dword ptr [rax+rax+00h]
0x140042f3c  mov     r8, r14; lpMem
0x140042f3f  xor     edx, edx; dwFlags
0x140042f41  mov     rcx, rax; hHeap
0x140042f44  call    cs:__imp_HeapFree
0x140042f4b  nop     dword ptr [rax+rax+00h]
0x140042f50  mov     cs:?g_HistoryDirectory@@3PEAGEA, 0; ushort * g_HistoryDirectory
0x140042f5b  jmp     short loc_140042F5F
0x140042f5d  xor     ebx, ebx
0x140042f5f  test    r12, r12
0x140042f62  jz      short loc_140042F73
0x140042f64  mov     rcx, r12; bstrString
0x140042f67  call    cs:__imp_SysFreeString
0x140042f6e  nop     dword ptr [rax+rax+00h]
0x140042f73  mov     rcx, [rbp+SecurityAttributes.lpSecurityDescriptor]; hMem
0x140042f77  test    rcx, rcx
0x140042f7a  jz      short loc_140042F90
0x140042f7c  call    cs:__imp_LocalFree
0x140042f83  nop     dword ptr [rax+rax+00h]
0x140042f88  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], 0
0x140042f90  test    rdi, rdi
0x140042f93  jz      short loc_140042FB5
0x140042f95  call    cs:__imp_GetProcessHeap
0x140042f9c  nop     dword ptr [rax+rax+00h]
0x140042fa1  mov     r8, rdi; lpMem
0x140042fa4  xor     edx, edx; dwFlags
0x140042fa6  mov     rcx, rax; hHeap
0x140042fa9  call    cs:__imp_HeapFree
0x140042fb0  nop     dword ptr [rax+rax+00h]
0x140042fb5  test    r15, r15
0x140042fb8  jz      short loc_140042FDA
0x140042fba  call    cs:__imp_GetProcessHeap
0x140042fc1  nop     dword ptr [rax+rax+00h]
0x140042fc6  mov     r8, r15; lpMem
0x140042fc9  xor     edx, edx; dwFlags
0x140042fcb  mov     rcx, rax; hHeap
0x140042fce  call    cs:__imp_HeapFree
0x140042fd5  nop     dword ptr [rax+rax+00h]
0x140042fda  test    rsi, rsi
0x140042fdd  jz      short loc_140042FFF
0x140042fdf  call    cs:__imp_GetProcessHeap
0x140042fe6  nop     dword ptr [rax+rax+00h]
0x140042feb  mov     r8, rsi; lpMem
0x140042fee  xor     edx, edx; dwFlags
0x140042ff0  mov     rcx, rax; hHeap
0x140042ff3  call    cs:__imp_HeapFree
0x140042ffa  nop     dword ptr [rax+rax+00h]
0x140042fff  lea     r11, [rsp+50h+var_s0]
0x140043004  mov     eax, ebx
0x140043006  mov     rbx, [r11+40h]
0x14004300a  mov     rsi, [r11+48h]
0x14004300e  mov     rsp, r11
0x140043011  pop     r15
0x140043013  pop     r14
0x140043015  pop     r12
0x140043017  pop     rdi
0x140043018  pop     rbp
0x140043019  retn
```
