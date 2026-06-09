# CreatePerQueueV4DriverDirectory(_INIPRINTER *,ushort const *)

- ea: `0x18000f774`
- end: `0x18000fa6e`
- name: `?CreatePerQueueV4DriverDirectory@@YAKPEAU_INIPRINTER@@PEBG@Z`
- size: `762`
- prototype: `unsigned int __fastcall(struct _INIPRINTER *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f680`

## callees

- `0x180005d90`
- `0x18000c380`
- `0x18000edc4`
- `0x18000f774`
- `0x18000fb8c`
- `0x180012dc0`
- `0x180045010`
- `0x180046650`
- `0x180046ac0`
- `0x180047330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa18`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f870`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000fa04`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f870`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000fa04`
- `SPOOLSS!DllFreeSplStr` at `0x18000fa40`
- `SPOOLSS!DllFreeSplStr` at `0x18000fa40`
- `SPOOLSS!DllFreeSplMem` at `0x18000fa59`
- `SPOOLSS!DllFreeSplMem` at `0x18000fa59`
- `SPOOLSS!RevertToPrinterSelf` at `0x18000f936`
- `SPOOLSS!RevertToPrinterSelf` at `0x18000f936`
- `SPOOLSS!AllocSplStr` at `0x18000f898`
- `SPOOLSS!AllocSplStr` at `0x18000f898`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18000fa50`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18000fa50`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000f976`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000f976`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f996`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f996`

## string_xrefs

- `0x18000f803`: `PrintQueueV4DriverDirectory`

## pseudocode

```c
unsigned int __fastcall CreatePerQueueV4DriverDirectory(struct _INIPRINTER *a1, const unsigned __int16 *a2)
{
  int v3; // ebx
  __int64 v5; // rsi
  int v6; // eax
  signed int LastError; // eax
  signed int v8; // eax
  __int64 v9; // rax
  int Key; // eax
  signed int v11; // eax
  const unsigned __int16 *v12; // r14
  HANDLE v13; // r15
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // r9
  struct _INISPOOLER *v17; // [rsp+38h] [rbp-C8h]
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v20[110]; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR PathName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  if ( !*((_QWORD *)a1 + 61) )
  {
    v12 = (const unsigned __int16 *)SubChar(*((_QWORD *)a1 + 3), a2);
    if ( !v12 )
    {
      v3 = -2147467259;
      return NCoreLibrary::StatusFromHResult((NCoreLibrary *)(unsigned int)v3, (int)a2);
    }
    v13 = RevertToPrinterSelf();
    if ( !v13 )
      goto LABEL_40;
    memset_0(PathName, 0, 0x208u);
    memset_0(&sz, 0, 0x64u);
    pguid = 0;
    v3 = CoCreateGuid(&pguid);
    if ( v3 >= 0 )
    {
      if ( StringFromGUID2(&pguid, &sz, 50) )
      {
        v5 = -1;
        sz = 92;
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&v20[2 * v14 - 2] );
        v15 = 2 * v14 - 2;
        if ( v15 >= 0x64 )
          _report_rangecheckfailure();
        v16 = *((_QWORD *)a1 + 35);
        *(_WORD *)&v20[v15 - 2] = 0;
        v3 = StringCchPrintfW(PathName, 0x104u, L"%s\\V4Dirs", *(_QWORD *)(v16 + 32));
        if ( v3 >= 0 )
        {
          if ( CreateDirectoryW(PathName, 0) || GetLastError() == 183 )
            goto LABEL_11;
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( v3 >= 0 )
          {
LABEL_11:
            v3 = StringCchCatW(PathName, 0x104u, &sz);
            if ( v3 >= 0 )
            {
              if ( CreateDirectoryW(PathName, 0) )
                goto LABEL_6;
              v8 = GetLastError();
              v3 = v8;
              if ( v8 > 0 )
                v3 = (unsigned __int16)v8 | 0x80070000;
              if ( v3 >= 0 )
              {
LABEL_6:
                v9 = AllocSplStr(PathName);
                *((_QWORD *)a1 + 61) = v9;
                if ( v9 )
                  goto LABEL_44;
                v11 = GetLastError();
                v3 = v11;
                if ( v11 > 0 )
                  v3 = (unsigned __int16)v11 | 0x80070000;
                if ( v3 >= 0 )
                {
LABEL_44:
                  v17 = (struct _INISPOOLER *)*((_QWORD *)a1 + 35);
                  *(_QWORD *)&pguid.Data1 = 0;
                  Key = SplRegCreateKey(*((void **)v17 + 30), v12, 0, 0x2001Fu, 0, (void **)&pguid, 0, v17);
                  v3 = Key;
                  if ( Key > 0 )
                    v3 = (unsigned __int16)Key | 0x80070000;
                  if ( v3 >= 0 )
                  {
                    do
                      ++v5;
                    while ( *(_WORD *)&v20[2 * v5 - 2] );
                    v6 = SplRegSetValue(
                           *(void **)&pguid.Data1,
                           L"PrintQueueV4DriverDirectory",
                           1u,
                           v20,
                           2 * v5,
                           *((struct _INISPOOLER **)a1 + 35));
                    v3 = v6;
                    if ( v6 > 0 )
                      v3 = (unsigned __int16)v6 | 0x80070000;
                    if ( v3 >= 0 )
                      goto LABEL_39;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v3 = -2147467259;
      }
    }
    DllFreeSplStr(*((_QWORD *)a1 + 61));
    *((_QWORD *)a1 + 61) = 0;
LABEL_39:
    ImpersonatePrinterClient(v13);
LABEL_40:
    DllFreeSplMem(v12);
  }
  return NCoreLibrary::StatusFromHResult((NCoreLibrary *)(unsigned int)v3, (int)a2);
}

```

## disassembly

```asm
0x18000f774  push    rbp
0x18000f776  push    rbx
0x18000f777  push    rsi
0x18000f778  push    rdi
0x18000f779  push    r12
0x18000f77b  push    r13
0x18000f77d  push    r14
0x18000f77f  push    r15
0x18000f781  lea     rbp, [rsp-1E8h]
0x18000f789  sub     rsp, 2E8h
0x18000f790  mov     rax, cs:__security_cookie
0x18000f797  xor     rax, rsp
0x18000f79a  mov     [rbp+220h+var_50], rax
0x18000f7a1  xor     r12d, r12d
0x18000f7a4  mov     rdi, rcx
0x18000f7a7  mov     ebx, r12d
0x18000f7aa  cmp     [rcx+1E8h], r12
0x18000f7b1  jz      loc_18000F921
0x18000f7b7  mov     ecx, ebx; this
0x18000f7b9  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x18000f7be  mov     rcx, [rbp+220h+var_50]
0x18000f7c5  xor     rcx, rsp; StackCookie
0x18000f7c8  call    __security_check_cookie
0x18000f7cd  add     rsp, 2E8h
0x18000f7d4  pop     r15
0x18000f7d6  pop     r14
0x18000f7d8  pop     r13
0x18000f7da  pop     r12
0x18000f7dc  pop     rdi
0x18000f7dd  pop     rsi
0x18000f7de  pop     rbx
0x18000f7df  pop     rbp
0x18000f7e0  retn
0x18000f7e1  inc     rsi
0x18000f7e4  cmp     [rax+rsi*2], r12w
0x18000f7e9  jnz     short loc_18000F7E1
0x18000f7eb  mov     rax, [rdi+118h]
0x18000f7f2  lea     ecx, [rsi+rsi]
0x18000f7f5  mov     [rsp+320h+var_2F8], rax; struct _INISPOOLER *
0x18000f7fa  lea     r9, [rsp+320h+var_2CE]; unsigned __int8 *
0x18000f7ff  mov     dword ptr [rsp+320h+var_300], ecx; unsigned int
0x18000f803  lea     rdx, String2; "PrintQueueV4DriverDirectory"
0x18000f80a  mov     rcx, qword ptr [rsp+320h+pguid.Data1]; void *
0x18000f80f  mov     r8d, 1; unsigned int
0x18000f815  call    ?SplRegSetValue@@YAJPEAXPEBGKPEBEKPEAU_INISPOOLER@@@Z; SplRegSetValue(void *,ushort const *,ulong,uchar const *,ulong,_INISPOOLER *)
0x18000f81a  mov     ebx, eax
0x18000f81c  test    eax, eax
0x18000f81e  jle     short loc_18000F826
0x18000f820  movzx   ebx, ax
0x18000f823  or      ebx, r13d
0x18000f826  test    ebx, ebx
0x18000f828  js      loc_18000FA39
0x18000f82e  jmp     loc_18000FA4D
0x18000f833  call    cs:__imp_GetLastError
0x18000f839  mov     ebx, eax
0x18000f83b  test    eax, eax
0x18000f83d  jle     short loc_18000F845
0x18000f83f  movzx   ebx, ax
0x18000f842  or      ebx, r13d
0x18000f845  test    ebx, ebx
0x18000f847  js      loc_18000FA39
0x18000f84d  lea     r8, [rsp+320h+sz]; unsigned __int16 *
0x18000f852  mov     edx, 104h; unsigned __int64
0x18000f857  lea     rcx, [rbp+220h+PathName]; unsigned __int16 *
0x18000f85b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f860  mov     ebx, eax
0x18000f862  test    eax, eax
0x18000f864  js      loc_18000FA39
0x18000f86a  xor     edx, edx; lpSecurityAttributes
0x18000f86c  lea     rcx, [rbp+220h+PathName]; lpPathName
0x18000f870  call    cs:__imp_CreateDirectoryW
0x18000f876  test    eax, eax
0x18000f878  jnz     short loc_18000F894
0x18000f87a  call    cs:__imp_GetLastError
0x18000f880  mov     ebx, eax
0x18000f882  test    eax, eax
0x18000f884  jle     short loc_18000F88C
0x18000f886  movzx   ebx, ax
0x18000f889  or      ebx, r13d
0x18000f88c  test    ebx, ebx
0x18000f88e  js      loc_18000FA39
0x18000f894  lea     rcx, [rbp+220h+PathName]
0x18000f898  call    cs:__imp_AllocSplStr
0x18000f89e  mov     [rdi+1E8h], rax
0x18000f8a5  test    rax, rax
0x18000f8a8  jz      short loc_18000F905
0x18000f8aa  mov     rcx, [rdi+118h]
0x18000f8b1  lea     rax, [rsp+320h+pguid]
0x18000f8b6  mov     [rsp+320h+var_2E8], rcx; struct _INISPOOLER *
0x18000f8bb  mov     r9d, 2001Fh; unsigned int
0x18000f8c1  mov     qword ptr [rsp+320h+pguid.Data1], r12
0x18000f8c6  xor     r8d, r8d; unsigned int
0x18000f8c9  mov     [rsp+320h+var_2F0], r12; unsigned int *
0x18000f8ce  mov     rdx, r14; unsigned __int16 *
0x18000f8d1  mov     rcx, [rcx+0F0h]; void *
0x18000f8d8  mov     [rsp+320h+var_2F8], rax; void **
0x18000f8dd  mov     [rsp+320h+var_300], r12; struct _SECURITY_ATTRIBUTES *
0x18000f8e2  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18000f8e7  mov     ebx, eax
0x18000f8e9  test    eax, eax
0x18000f8eb  jle     short loc_18000F8F3
0x18000f8ed  movzx   ebx, ax
0x18000f8f0  or      ebx, r13d
0x18000f8f3  test    ebx, ebx
0x18000f8f5  js      loc_18000FA39
0x18000f8fb  lea     rax, [rsp+320h+sz]
0x18000f900  jmp     loc_18000F7E1
0x18000f905  call    cs:__imp_GetLastError
0x18000f90b  mov     ebx, eax
0x18000f90d  test    eax, eax
0x18000f90f  jle     short loc_18000F917
0x18000f911  movzx   ebx, ax
0x18000f914  or      ebx, r13d
0x18000f917  test    ebx, ebx
0x18000f919  js      loc_18000FA39
0x18000f91f  jmp     short loc_18000F8AA
0x18000f921  mov     rcx, [rcx+18h]
0x18000f925  call    SubChar
0x18000f92a  mov     r14, rax
0x18000f92d  test    rax, rax
0x18000f930  jz      loc_18000FA64
0x18000f936  call    cs:__imp_RevertToPrinterSelf
0x18000f93c  mov     r15, rax
0x18000f93f  test    rax, rax
0x18000f942  jz      loc_18000FA56
0x18000f948  xor     edx, edx; Val
0x18000f94a  lea     rcx, [rbp+220h+PathName]; void *
0x18000f94e  mov     r8d, 208h; Size
0x18000f954  call    memset_0
0x18000f959  xor     edx, edx; Val
0x18000f95b  lea     rcx, [rsp+320h+sz]; void *
0x18000f960  lea     r8d, [rdx+64h]; Size
0x18000f964  call    memset_0
0x18000f969  xorps   xmm0, xmm0
0x18000f96c  lea     rcx, [rsp+320h+pguid]; pguid
0x18000f971  movups  xmmword ptr [rsp+320h+pguid.Data1], xmm0
0x18000f976  call    cs:__imp_CoCreateGuid
0x18000f97c  mov     ebx, eax
0x18000f97e  test    eax, eax
0x18000f980  js      loc_18000FA39
0x18000f986  mov     r8d, 32h ; '2'; cchMax
0x18000f98c  lea     rdx, [rsp+320h+sz]; lpsz
0x18000f991  lea     rcx, [rsp+320h+pguid]; rguid
0x18000f996  call    cs:__imp_StringFromGUID2
0x18000f99c  test    eax, eax
0x18000f99e  jz      loc_18000FA34
0x18000f9a4  mov     eax, 5Ch ; '\'
0x18000f9a9  lea     rcx, [rsp+320h+sz]
0x18000f9ae  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f9b2  mov     [rsp+320h+sz], ax
0x18000f9b7  mov     rax, rsi
0x18000f9ba  inc     rax
0x18000f9bd  cmp     [rcx+rax*2], r12w
0x18000f9c2  jnz     short loc_18000F9BA
0x18000f9c4  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000f9cc  cmp     rcx, 64h ; 'd'
0x18000f9d0  jnb     short loc_18000FA2E
0x18000f9d2  mov     r9, [rdi+118h]
0x18000f9d9  lea     r8, aSV4dirs; "%s\\V4Dirs"
0x18000f9e0  mov     [rsp+rcx+320h+sz], r12w
0x18000f9e6  mov     edx, 104h; unsigned __int64
0x18000f9eb  lea     rcx, [rbp+220h+PathName]; unsigned __int16 *
0x18000f9ef  mov     r9, [r9+20h]
0x18000f9f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f9f8  mov     ebx, eax
0x18000f9fa  test    eax, eax
0x18000f9fc  js      short loc_18000FA39
0x18000f9fe  xor     edx, edx; lpSecurityAttributes
0x18000fa00  lea     rcx, [rbp+220h+PathName]; lpPathName
0x18000fa04  call    cs:__imp_CreateDirectoryW
0x18000fa0a  mov     r13d, 80070000h
0x18000fa10  test    eax, eax
0x18000fa12  jnz     loc_18000F84D
0x18000fa18  call    cs:__imp_GetLastError
0x18000fa1e  cmp     eax, 0B7h
0x18000fa23  jz      loc_18000F84D
0x18000fa29  jmp     loc_18000F833
0x18000fa2e  call    __report_rangecheckfailure
0x18000fa34  mov     ebx, 80004005h
0x18000fa39  mov     rcx, [rdi+1E8h]
0x18000fa40  call    cs:__imp_DllFreeSplStr
0x18000fa46  mov     [rdi+1E8h], r12
0x18000fa4d  mov     rcx, r15; hToken
0x18000fa50  call    cs:__imp_ImpersonatePrinterClient
0x18000fa56  mov     rcx, r14
0x18000fa59  call    cs:__imp_DllFreeSplMem
0x18000fa5f  jmp     loc_18000F7B7
0x18000fa64  mov     ebx, 80004005h
0x18000fa69  jmp     loc_18000F7B7
```
