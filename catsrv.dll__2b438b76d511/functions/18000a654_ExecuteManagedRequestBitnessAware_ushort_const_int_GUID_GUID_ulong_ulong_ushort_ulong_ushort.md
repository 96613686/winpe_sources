# ExecuteManagedRequestBitnessAware(ushort const *,int,_GUID,_GUID,ulong,ulong,ushort * *,ulong,ushort * *)

- ea: `0x18000a654`
- end: `0x18000ab02`
- name: `?ExecuteManagedRequestBitnessAware@@YAJPEBGHU_GUID@@1KKPEAPEAGK2@Z`
- size: `1198`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, struct _GUID *, struct _GUID *, unsigned int, unsigned int, unsigned __int16 **, unsigned int, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010900`
- `0x180029744`
- `0x180029b14`
- `0x180030e28`
- `0x18003c2c8`
- `0x1800413e0`

## callees

- `0x18000a01c`
- `0x18000a654`
- `0x18000ae48`
- `0x18000ae78`
- `0x18000f014`
- `0x18001ec1c`
- `0x180031504`
- `0x180031688`
- `0x18003188c`
- `0x180032c98`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000aa58`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aa58`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aab8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aaa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aaa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a90e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a90e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000a940`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000a940`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000aa82`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000aa82`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000a8d3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000a8d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a71a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a71a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000a8a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000a8a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a78b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a78b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a772`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a772`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18000a6f2`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18000a6f2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a811`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a811`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a82f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a82f`

## string_xrefs

- `0x18000a724`: `\RunDll32.exe`
- `0x18000a9d5`: `RunDll32.exe catsrvut.dll,ManagedRequest `

## pseudocode

```c
__int64 __fastcall ExecuteManagedRequestBitnessAware(
        const unsigned __int16 *a1,
        int a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 **a7,
        unsigned int a8,
        unsigned __int16 **a9)
{
  unsigned __int16 **v11; // r15
  unsigned int v12; // esi
  signed int LastError; // eax
  int Process; // edi
  signed int v15; // eax
  HANDLE CurrentThread; // rax
  unsigned int v17; // r8d
  unsigned __int64 v18; // rbx
  unsigned int i; // ecx
  unsigned __int16 *v20; // rdx
  __int64 v21; // rax
  DWORD dwMaximumSizeLow; // r15d
  HANDLE v23; // r12
  signed int v24; // eax
  signed int v25; // eax
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rbx
  unsigned int v28; // r11d
  int v29; // r8d
  unsigned __int16 **v30; // r15
  const OLECHAR *v31; // rcx
  unsigned int j; // eax
  BSTR v33; // rax
  int v35; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 **v37; // [rsp+40h] [rbp-C0h]
  struct _GUID *v38; // [rsp+48h] [rbp-B8h]
  struct _GUID *v39; // [rsp+50h] [rbp-B0h]
  unsigned __int16 **v40; // [rsp+58h] [rbp-A8h]
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+60h] [rbp-A0h] BYREF
  void *ppInterface; // [rsp+78h] [rbp-88h] BYREF
  int v43; // [rsp+80h] [rbp-80h]
  __int64 v44; // [rsp+88h] [rbp-78h]
  _SYSTEM_INFO SystemInfo; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pSecurityDescriptor[56]; // [rsp+C0h] [rbp-40h] BYREF
  GUID pguid; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR Name[7]; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR sz[49]; // [rsp+11Eh] [rbp+1Eh] BYREF
  WCHAR CommandLine[104]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  v39 = a4;
  v38 = a3;
  v11 = a9;
  v37 = a9;
  v40 = a7;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v12 = 0;
  TokenHandle = 0;
  pguid = 0;
  memset_0(Buffer, 0, 0x20Au);
  ppInterface = 0;
  v43 = 0;
  v44 = 0;
  if ( a2 )
  {
    if ( !GetSystemDirectoryW(Buffer, 0x105u) )
      goto LABEL_11;
  }
  else if ( !GetSystemWow64DirectoryW(Buffer, 0x105u) )
  {
    LastError = GetLastError();
    Process = LastError;
    if ( LastError > 0 )
      Process = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_66;
  }
  v15 = StringCchCatW(Buffer, 0x105u, L"\\RunDll32.exe");
  if ( v15 < 0
    || (v15 = StringCchCopyW(Name, 0x32u, L"Global\\"), v15 < 0)
    || (v15 = CImpersonate::ImpersonateClient(&ppInterface), v35 = v15, v15 < 0) )
  {
LABEL_7:
    Process = v15;
    goto LABEL_66;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
LABEL_11:
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    goto LABEL_7;
  }
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v35);
  Process = v35;
  if ( v35 < 0 )
  {
    CloseHandle(TokenHandle);
    goto LABEL_66;
  }
  if ( a8 )
    memset_0(a9, 0, 8LL * a8);
  CSystemAndUserDescriptor::CSystemAndUserDescriptor(pSecurityDescriptor, TokenHandle, v17, &v35);
  Process = v35;
  if ( v35 >= 0 )
  {
    Process = CoCreateGuid(&pguid);
    if ( Process >= 0 )
    {
      if ( !StringFromGUID2(&pguid, sz, 43) )
      {
        Process = -2147467259;
        goto LABEL_60;
      }
      FileMappingAttributes.nLength = 24;
      FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
      FileMappingAttributes.bInheritHandle = 0;
      v18 = 1616;
      for ( i = 0; i < a6; ++i )
      {
        v18 += 2LL;
        v20 = a7[i];
        if ( v20 )
        {
          v21 = -1;
          do
            ++v21;
          while ( v20[v21] );
          v18 += 2 * v21;
        }
      }
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetSystemInfo(&SystemInfo);
      dwMaximumSizeLow = SystemInfo.dwAllocationGranularity;
      if ( v18 >= SystemInfo.dwAllocationGranularity )
        dwMaximumSizeLow = v18;
      v23 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, dwMaximumSizeLow, Name);
      if ( !v23 )
      {
        v24 = GetLastError();
        Process = v24;
        v12 = 0;
        if ( v24 > 0 )
          Process = (unsigned __int16)v24 | 0x80070000;
        goto LABEL_59;
      }
      if ( GetLastError() == 183 || (v26 = (unsigned __int16 *)MapViewOfFile(v23, 6u, 0, 0, 0), (v27 = v26) == 0) )
      {
        v25 = GetLastError();
        Process = v25;
        v12 = 0;
        if ( v25 > 0 )
          Process = (unsigned __int16)v25 | 0x80070000;
        goto LABEL_58;
      }
      if ( a1 )
      {
        Process = StringCchCopyW(v26, 0x30Cu, a1);
        if ( Process < 0 )
          goto LABEL_54;
      }
      else
      {
        *v26 = 0;
      }
      *((_DWORD *)v27 + 390) = dwMaximumSizeLow;
      *(struct _GUID *)(v27 + 782) = *v38;
      *(struct _GUID *)(v27 + 790) = *v39;
      *((_DWORD *)v27 + 399) = a5;
      *((_DWORD *)v27 + 400) = a6;
      *((_DWORD *)v27 + 401) = a8;
      *((_DWORD *)v27 + 402) = 0;
      Process = SPR_Data::SetParams((struct SPR_Data *)v27, a6, v40);
      v12 = 0;
      if ( Process < 0 )
        goto LABEL_55;
      Process = StringCchCopyW(CommandLine, 0x64u, L"RunDll32.exe catsrvut.dll,ManagedRequest ");
      if ( Process < 0 )
        goto LABEL_55;
      Process = StringCchCatW(CommandLine, v28, Name);
      if ( Process < 0 )
        goto LABEL_55;
      Process = ImpersonatingCreateProcess(Buffer, CommandLine, v29);
      if ( Process < 0 )
        goto LABEL_55;
      v30 = v37;
      while ( v12 < a8 )
      {
        v31 = v27 + 806;
        for ( j = 0; j < v12; ++j )
        {
          while ( *v31 )
            ++v31;
          ++v31;
        }
        v33 = SysAllocString(v31);
        v30[v12] = v33;
        if ( !v33 )
        {
          Process = -2147024882;
          break;
        }
        ++v12;
      }
LABEL_54:
      v12 = 0;
LABEL_55:
      if ( *((int *)v27 + 402) < 0 )
        Process = *((_DWORD *)v27 + 402);
      UnmapViewOfFile(v27);
LABEL_58:
      CloseHandle(v23);
LABEL_59:
      v11 = v37;
    }
  }
LABEL_60:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Process < 0 && a8 )
  {
    do
    {
      SysFreeString(v11[v12]);
      v11[v12++] = 0;
    }
    while ( v12 < a8 );
  }
  CSystemAndUserDescriptor::~CSystemAndUserDescriptor((CSystemAndUserDescriptor *)pSecurityDescriptor);
LABEL_66:
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)Process;
}

```

## disassembly

```asm
0x18000a654  push    rbp
0x18000a656  push    rbx
0x18000a657  push    rsi
0x18000a658  push    rdi
0x18000a659  push    r12
0x18000a65b  push    r13
0x18000a65d  push    r14
0x18000a65f  push    r15
0x18000a661  lea     rbp, [rsp-378h]
0x18000a669  sub     rsp, 478h
0x18000a670  mov     rax, cs:__security_cookie
0x18000a677  xor     rax, rsp
0x18000a67a  mov     [rbp+3B0h+var_50], rax
0x18000a681  mov     [rsp+4B0h+var_460], r9
0x18000a686  mov     [rsp+4B0h+var_468], r8
0x18000a68b  mov     ebx, edx
0x18000a68d  mov     r13, rcx
0x18000a690  mov     r15, [rbp+3B0h+arg_40]
0x18000a697  mov     [rsp+4B0h+var_470], r15
0x18000a69c  mov     r12, [rbp+3B0h+arg_30]
0x18000a6a3  mov     [rsp+4B0h+var_458], r12
0x18000a6a8  xorps   xmm0, xmm0
0x18000a6ab  xor     eax, eax
0x18000a6ad  movups  xmmword ptr [rsp+4B0h+FileMappingAttributes.nLength], xmm0
0x18000a6b2  mov     qword ptr [rsp+4B0h+FileMappingAttributes.bInheritHandle], rax
0x18000a6b7  xor     esi, esi
0x18000a6b9  mov     [rsp+4B0h+TokenHandle], rsi
0x18000a6be  movups  xmmword ptr [rbp+3B0h+pguid.Data1], xmm0
0x18000a6c2  xor     edx, edx; Val
0x18000a6c4  mov     r8d, 20Ah; Size
0x18000a6ca  lea     rcx, [rbp+3B0h+Buffer]; void *
0x18000a6d1  call    memset_0
0x18000a6d6  mov     [rsp+4B0h+ppInterface], rsi
0x18000a6db  mov     [rbp+3B0h+var_430], esi
0x18000a6de  mov     [rbp+3B0h+var_428], rsi
0x18000a6e2  mov     edx, 105h; uSize
0x18000a6e7  lea     rcx, [rbp+3B0h+Buffer]; lpBuffer
0x18000a6ee  test    ebx, ebx
0x18000a6f0  jnz     short loc_18000A71A
0x18000a6f2  call    cs:__imp_GetSystemWow64DirectoryW
0x18000a6f8  test    eax, eax
0x18000a6fa  jnz     short loc_18000A724
0x18000a6fc  call    cs:__imp_GetLastError
0x18000a702  mov     edi, eax
0x18000a704  test    eax, eax
0x18000a706  jle     loc_18000AAD3
0x18000a70c  movzx   edi, ax
0x18000a70f  or      edi, 80070000h
0x18000a715  jmp     loc_18000AAD3
0x18000a71a  call    cs:__imp_GetSystemDirectoryW
0x18000a720  test    eax, eax
0x18000a722  jz      short loc_18000A795
0x18000a724  lea     r8, aRundll32Exe; "\\RunDll32.exe"
0x18000a72b  mov     edx, 105h; unsigned __int64
0x18000a730  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x18000a737  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a73c  test    eax, eax
0x18000a73e  jns     short loc_18000A747
0x18000a740  mov     edi, eax
0x18000a742  jmp     loc_18000AAD3
0x18000a747  lea     r8, aGlobal; "Global\\"
0x18000a74e  mov     edx, 32h ; '2'; unsigned __int64
0x18000a753  lea     rcx, [rbp+3B0h+Name]; unsigned __int16 *
0x18000a757  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a75c  test    eax, eax
0x18000a75e  js      short loc_18000A740
0x18000a760  lea     rcx, [rsp+4B0h+ppInterface]; ppInterface
0x18000a765  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18000a76a  mov     [rsp+4B0h+var_480], eax
0x18000a76e  test    eax, eax
0x18000a770  js      short loc_18000A740
0x18000a772  call    cs:__imp_GetCurrentThread
0x18000a778  mov     rcx, rax; ThreadHandle
0x18000a77b  lea     r9, [rsp+4B0h+TokenHandle]; TokenHandle
0x18000a780  mov     edx, 0F01FFh; DesiredAccess
0x18000a785  mov     r8d, 1; OpenAsSelf
0x18000a78b  call    cs:__imp_OpenThreadToken
0x18000a791  test    eax, eax
0x18000a793  jnz     short loc_18000A7A9
0x18000a795  call    cs:__imp_GetLastError
0x18000a79b  test    eax, eax
0x18000a79d  jle     short loc_18000A740
0x18000a79f  movzx   eax, ax
0x18000a7a2  or      eax, 80070000h
0x18000a7a7  jmp     short loc_18000A740
0x18000a7a9  lea     rdx, [rsp+4B0h+var_480]; int *
0x18000a7ae  lea     rcx, [rsp+4B0h+ppInterface]; this
0x18000a7b3  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x18000a7b8  mov     edi, [rsp+4B0h+var_480]
0x18000a7bc  test    edi, edi
0x18000a7be  jns     short loc_18000A7D0
0x18000a7c0  mov     rcx, [rsp+4B0h+TokenHandle]; hObject
0x18000a7c5  call    cs:__imp_CloseHandle
0x18000a7cb  jmp     loc_18000AAD3
0x18000a7d0  mov     r14d, [rbp+3B0h+arg_38]
0x18000a7d7  test    r14d, r14d
0x18000a7da  jz      short loc_18000A7ED
0x18000a7dc  mov     r8d, r14d
0x18000a7df  shl     r8, 3; Size
0x18000a7e3  xor     edx, edx; Val
0x18000a7e5  mov     rcx, r15; void *
0x18000a7e8  call    memset_0
0x18000a7ed  lea     r9, [rsp+4B0h+var_480]; int *
0x18000a7f2  mov     rdx, [rsp+4B0h+TokenHandle]; TokenHandle
0x18000a7f7  lea     rcx, [rbp+3B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18000a7fb  call    ??0CSystemAndUserDescriptor@@QEAA@PEAXKPEAJ@Z; CSystemAndUserDescriptor::CSystemAndUserDescriptor(void *,ulong,long *)
0x18000a800  nop
0x18000a801  mov     edi, [rsp+4B0h+var_480]
0x18000a805  test    edi, edi
0x18000a807  js      loc_18000AA96
0x18000a80d  lea     rcx, [rbp+3B0h+pguid]; pguid
0x18000a811  call    cs:__imp_CoCreateGuid
0x18000a817  mov     edi, eax
0x18000a819  test    eax, eax
0x18000a81b  js      loc_18000AA96
0x18000a821  mov     r8d, 2Bh ; '+'; cchMax
0x18000a827  lea     rdx, [rbp+3B0h+sz]; lpsz
0x18000a82b  lea     rcx, [rbp+3B0h+pguid]; rguid
0x18000a82f  call    cs:__imp_StringFromGUID2
0x18000a835  test    eax, eax
0x18000a837  jnz     short loc_18000A843
0x18000a839  mov     edi, 80004005h
0x18000a83e  jmp     loc_18000AA96
0x18000a843  mov     [rsp+4B0h+FileMappingAttributes.nLength], 18h
0x18000a84b  lea     rax, [rbp+3B0h+pSecurityDescriptor]
0x18000a84f  mov     [rsp+4B0h+FileMappingAttributes.lpSecurityDescriptor], rax
0x18000a854  mov     [rsp+4B0h+FileMappingAttributes.bInheritHandle], esi
0x18000a858  mov     ebx, 650h
0x18000a85d  mov     ecx, esi
0x18000a85f  mov     esi, [rbp+3B0h+arg_28]
0x18000a865  xor     edi, edi
0x18000a867  test    esi, esi
0x18000a869  jz      short loc_18000A891
0x18000a86b  add     rbx, 2
0x18000a86f  mov     eax, ecx
0x18000a871  mov     rdx, [r12+rax*8]
0x18000a875  test    rdx, rdx
0x18000a878  jz      short loc_18000A88B
0x18000a87a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a87e  inc     rax
0x18000a881  cmp     [rdx+rax*2], di
0x18000a885  jnz     short loc_18000A87E
0x18000a887  lea     rbx, [rbx+rax*2]
0x18000a88b  inc     ecx
0x18000a88d  cmp     ecx, esi
0x18000a88f  jb      short loc_18000A86B
0x18000a891  xorps   xmm0, xmm0
0x18000a894  movups  xmmword ptr [rbp+3B0h+SystemInfo], xmm0
0x18000a898  movups  xmmword ptr [rbp+3B0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000a89c  movups  xmmword ptr [rbp+3B0h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000a8a0  lea     rcx, [rbp+3B0h+SystemInfo]; lpSystemInfo
0x18000a8a4  call    cs:__imp_GetSystemInfo
0x18000a8aa  mov     r15d, [rbp+3B0h+SystemInfo.dwAllocationGranularity]
0x18000a8ae  cmp     rbx, r15
0x18000a8b1  cmovnb  r15d, ebx
0x18000a8b5  lea     rax, [rbp+3B0h+Name]
0x18000a8b9  mov     [rsp+4B0h+lpName], rax; lpName
0x18000a8be  mov     [rsp+4B0h+dwMaximumSizeLow], r15d; dwMaximumSizeLow
0x18000a8c3  xor     r9d, r9d; dwMaximumSizeHigh
0x18000a8c6  lea     r8d, [r9+4]; flProtect
0x18000a8ca  lea     rdx, [rsp+4B0h+FileMappingAttributes]; lpFileMappingAttributes
0x18000a8cf  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000a8d3  call    cs:__imp_CreateFileMappingW
0x18000a8d9  mov     r12, rax
0x18000a8dc  test    rax, rax
0x18000a8df  jnz     short loc_18000A901
0x18000a8e1  call    cs:__imp_GetLastError
0x18000a8e7  mov     edi, eax
0x18000a8e9  xor     esi, esi
0x18000a8eb  test    eax, eax
0x18000a8ed  jle     loc_18000AA91
0x18000a8f3  movzx   edi, ax
0x18000a8f6  or      edi, 80070000h
0x18000a8fc  jmp     loc_18000AA91
0x18000a901  call    cs:__imp_GetLastError
0x18000a907  cmp     eax, 0B7h
0x18000a90c  jnz     short loc_18000A92E
0x18000a90e  call    cs:__imp_GetLastError
0x18000a914  mov     edi, eax
0x18000a916  xor     esi, esi
0x18000a918  test    eax, eax
0x18000a91a  jle     loc_18000AA88
0x18000a920  movzx   edi, ax
0x18000a923  or      edi, 80070000h
0x18000a929  jmp     loc_18000AA88
0x18000a92e  mov     qword ptr [rsp+4B0h+dwMaximumSizeLow], rdi; dwNumberOfBytesToMap
0x18000a933  xor     r9d, r9d; dwFileOffsetLow
0x18000a936  xor     r8d, r8d; dwFileOffsetHigh
0x18000a939  lea     edx, [r9+6]; dwDesiredAccess
0x18000a93d  mov     rcx, r12; hFileMappingObject
0x18000a940  call    cs:__imp_MapViewOfFile
0x18000a946  mov     rbx, rax
0x18000a949  test    rax, rax
0x18000a94c  jz      short loc_18000A90E
0x18000a94e  test    r13, r13
0x18000a951  jz      short loc_18000A971
0x18000a953  mov     r8, r13; unsigned __int16 *
0x18000a956  mov     edx, 30Ch; unsigned __int64
0x18000a95b  mov     rcx, rax; unsigned __int16 *
0x18000a95e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a963  mov     edi, eax
0x18000a965  test    eax, eax
0x18000a967  js      loc_18000AA72
0x18000a96d  xor     edi, edi
0x18000a96f  jmp     short loc_18000A974
0x18000a971  mov     [rax], di
0x18000a974  mov     [rbx+618h], r15d
0x18000a97b  mov     rax, [rsp+4B0h+var_468]
0x18000a980  movaps  xmm0, xmmword ptr [rax]
0x18000a983  movdqu  xmmword ptr [rbx+61Ch], xmm0
0x18000a98b  mov     rax, [rsp+4B0h+var_460]
0x18000a990  movaps  xmm1, xmmword ptr [rax]
0x18000a993  movdqu  xmmword ptr [rbx+62Ch], xmm1
0x18000a99b  mov     eax, [rbp+3B0h+arg_20]
0x18000a9a1  mov     [rbx+63Ch], eax
0x18000a9a7  mov     [rbx+640h], esi
0x18000a9ad  mov     [rbx+644h], r14d
0x18000a9b4  mov     [rbx+648h], edi
0x18000a9ba  mov     r8, [rsp+4B0h+var_458]; unsigned __int16 **
0x18000a9bf  mov     edx, esi; unsigned int
0x18000a9c1  mov     rcx, rbx; struct SPR_Data *
0x18000a9c4  call    ?SetParams@SPR_Data@@SAJPEAU1@KPEAPEAG@Z; SPR_Data::SetParams(SPR_Data *,ulong,ushort * *)
0x18000a9c9  mov     edi, eax
0x18000a9cb  xor     esi, esi
0x18000a9cd  test    eax, eax
0x18000a9cf  js      loc_18000AA74
0x18000a9d5  lea     r8, aRundll32ExeCat; "RunDll32.exe catsrvut.dll,ManagedReques"...
0x18000a9dc  lea     r11d, [rsi+64h]
0x18000a9e0  mov     edx, r11d; unsigned __int64
0x18000a9e3  lea     rcx, [rbp+3B0h+CommandLine]; unsigned __int16 *
0x18000a9ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a9ef  mov     edi, eax
0x18000a9f1  test    eax, eax
0x18000a9f3  js      short loc_18000AA74
0x18000a9f5  lea     r8, [rbp+3B0h+Name]; unsigned __int16 *
0x18000a9f9  mov     edx, r11d; unsigned __int64
0x18000a9fc  lea     rcx, [rbp+3B0h+CommandLine]; unsigned __int16 *
0x18000aa03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aa08  mov     edi, eax
0x18000aa0a  test    eax, eax
0x18000aa0c  js      short loc_18000AA74
0x18000aa0e  lea     rdx, [rbp+3B0h+CommandLine]; lpCommandLine
0x18000aa15  lea     rcx, [rbp+3B0h+Buffer]; lpApplicationName
0x18000aa1c  call    ?ImpersonatingCreateProcess@@YAJPEAG0H@Z; ImpersonatingCreateProcess(ushort *,ushort *,int)
0x18000aa21  mov     edi, eax
0x18000aa23  test    eax, eax
0x18000aa25  js      short loc_18000AA74
0x18000aa27  mov     r15, [rsp+4B0h+var_470]
0x18000aa2c  xor     r13d, r13d
0x18000aa2f  cmp     esi, r14d
0x18000aa32  jnb     short loc_18000AA72
0x18000aa34  lea     rcx, [rbx+64Ch]
0x18000aa3b  mov     eax, r13d
0x18000aa3e  test    esi, esi
0x18000aa40  jz      short loc_18000AA58
0x18000aa42  jmp     short loc_18000AA48
0x18000aa44  add     rcx, 2
0x18000aa48  cmp     [rcx], r13w
0x18000aa4c  jnz     short loc_18000AA44
0x18000aa4e  add     rcx, 2; psz
0x18000aa52  inc     eax
0x18000aa54  cmp     eax, esi
0x18000aa56  jb      short loc_18000AA48
0x18000aa58  call    cs:__imp_SysAllocString
0x18000aa5e  mov     ecx, esi
0x18000aa60  mov     [r15+rcx*8], rax
0x18000aa64  test    rax, rax
0x18000aa67  jz      short loc_18000AA6D
0x18000aa69  inc     esi
0x18000aa6b  jmp     short loc_18000AA2F
0x18000aa6d  mov     edi, 8007000Eh
0x18000aa72  xor     esi, esi
0x18000aa74  mov     eax, [rbx+648h]
0x18000aa7a  test    eax, eax
0x18000aa7c  cmovs   edi, eax
0x18000aa7f  mov     rcx, rbx; lpBaseAddress
0x18000aa82  call    cs:__imp_UnmapViewOfFile
0x18000aa88  mov     rcx, r12; hObject
0x18000aa8b  call    cs:__imp_CloseHandle
0x18000aa91  mov     r15, [rsp+4B0h+var_470]
0x18000aa96  mov     rcx, [rsp+4B0h+TokenHandle]; hObject
0x18000aa9b  test    rcx, rcx
0x18000aa9e  jz      short loc_18000AAA6
0x18000aaa0  call    cs:__imp_CloseHandle
0x18000aaa6  test    edi, edi
0x18000aaa8  jns     short loc_18000AAC9
0x18000aaaa  xor     r13d, r13d
0x18000aaad  test    r14d, r14d
0x18000aab0  jz      short loc_18000AAC9
0x18000aab2  mov     ebx, esi
0x18000aab4  mov     rcx, [r15+rbx*8]; bstrString
0x18000aab8  call    cs:__imp_SysFreeString
0x18000aabe  mov     [r15+rbx*8], r13
0x18000aac2  inc     esi
0x18000aac4  cmp     esi, r14d
0x18000aac7  jb      short loc_18000AAB2
0x18000aac9  lea     rcx, [rbp+3B0h+pSecurityDescriptor]; this
0x18000aacd  call    ??1CSystemAndUserDescriptor@@QEAA@XZ; CSystemAndUserDescriptor::~CSystemAndUserDescriptor(void)
0x18000aad2  nop
0x18000aad3  lea     rcx, [rsp+4B0h+ppInterface]; this
  ... truncated ...
```
