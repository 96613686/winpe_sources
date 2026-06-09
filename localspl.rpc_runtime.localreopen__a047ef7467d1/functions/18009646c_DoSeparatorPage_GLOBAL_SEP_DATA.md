# DoSeparatorPage(GLOBAL_SEP_DATA *)

- ea: `0x18009646c`
- end: `0x180096ce2`
- name: `?DoSeparatorPage@@YAHPEAUGLOBAL_SEP_DATA@@@Z`
- size: `2166`
- prototype: `__int64 __fastcall(struct GLOBAL_SEP_DATA *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b47c`

## callees

- `0x180008520`
- `0x180008560`
- `0x180046650`
- `0x180047330`
- `0x180054638`
- `0x180095f40`
- `0x180096270`
- `0x180096358`
- `0x180096394`
- `0x180096400`
- `0x18009646c`
- `0x180096ce8`
- `0x180096d40`
- `0x180096e10`
- `0x18009703c`
- `0x1800970f0`
- `0x180097128`
- `0x1800971a8`
- `0x1800971d0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180096af8`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180096af8`
- `api-ms-win-crt-private-l1-1-0!_o_isxdigit` at `0x1800968e0`
- `api-ms-win-crt-private-l1-1-0!_o_isxdigit` at `0x1800968f7`
- `api-ms-win-crt-private-l1-1-0!_o_isxdigit` at `0x1800968e0`
- `api-ms-win-crt-private-l1-1-0!_o_isxdigit` at `0x1800968f7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800967e6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800967e6`
- `ntdll!RtlInitUnicodeString` at `0x180096815`
- `ntdll!RtlInitUnicodeString` at `0x180096be7`
- `ntdll!RtlInitUnicodeString` at `0x180096815`
- `ntdll!RtlInitUnicodeString` at `0x180096be7`
- `ntdll!RtlFreeAnsiString` at `0x180096873`
- `ntdll!RtlFreeAnsiString` at `0x180096c45`
- `ntdll!RtlFreeAnsiString` at `0x180096873`
- `ntdll!RtlFreeAnsiString` at `0x180096c45`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180096828`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180096bfa`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180096828`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180096bfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096a6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096a6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096a8e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800969a4`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800969a4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800969d3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800969d3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180096a03`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180096a03`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096a66`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096a66`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180096a21`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180096a21`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180096a45`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180096a45`
- `SPOOLSS!DllFreeSplStr` at `0x180096c4e`
- `SPOOLSS!DllFreeSplStr` at `0x180096c4e`
- `SPOOLSS!DllFreeSplMem` at `0x180096caf`
- `SPOOLSS!DllFreeSplMem` at `0x180096caf`
- `SPOOLSS!RevertToPrinterSelf` at `0x180096975`
- `SPOOLSS!RevertToPrinterSelf` at `0x180096975`
- `SPOOLSS!AllocSplStr` at `0x180096bb8`
- `SPOOLSS!AllocSplStr` at `0x180096bb8`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800969b0`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800969b0`
- `SspiCli!GetUserNameExW` at `0x1800967cc`
- `SspiCli!GetUserNameExW` at `0x1800967cc`
- `GDI32!DeleteObject` at `0x180096c8b`
- `GDI32!DeleteObject` at `0x180096c9d`
- `GDI32!DeleteObject` at `0x180096c8b`
- `GDI32!DeleteObject` at `0x180096c9d`
- `GDI32!DeleteDC` at `0x180096c79`
- `GDI32!DeleteDC` at `0x180096c79`

## string_xrefs

- `0x180096a99`: `Could not open separator page file %s`

## pseudocode

```c
__int64 __fastcall DoSeparatorPage(struct GLOBAL_SEP_DATA *a1)
{
  int SepChar; // eax
  int (*v4)(struct GLOBAL_SEP_DATA *, int); // r12
  unsigned int v5; // esi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // edx
  int v9; // ebx
  unsigned int v10; // r8d
  char *v11; // rdx
  unsigned int v12; // eax
  CHAR *v13; // rbx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // edx
  struct GLOBAL_SEP_DATA *v17; // rcx
  struct GLOBAL_SEP_DATA *v18; // rcx
  int v19; // edx
  int v20; // eax
  unsigned int v21; // eax
  int v22; // ebx
  wchar_t *v23; // rax
  PCHAR v24; // rbx
  int v25; // r14d
  unsigned int v26; // eax
  CHAR *v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // r14
  char v32; // bl
  char v33; // al
  unsigned int v34; // r8d
  HANDLE v35; // rbx
  HANDLE FileA; // r14
  SIZE_T FileSize; // rbx
  HANDLE FileMappingW; // rax
  void *v39; // r12
  char *v40; // rax
  char *v41; // r15
  unsigned int i; // ebx
  __int64 v43; // r14
  int v44; // ecx
  CHAR *v45; // rbx
  __int64 v46; // rdx
  const WCHAR *v47; // r15
  __int64 v48; // rcx
  PCHAR Buffer; // rbx
  int Length; // r14d
  unsigned int v51; // eax
  HDC v52; // rcx
  void *v53; // rcx
  void *v54; // rcx
  __int64 v55; // rcx
  _STRING AnsiString; // [rsp+40h] [rbp-C0h] BYREF
  ULONG nSize; // [rsp+50h] [rbp-B0h] BYREF
  int (*v58)(struct GLOBAL_SEP_DATA *, int); // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  CHAR FileName[272]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NameBuffer[264]; // [rsp+180h] [rbp+80h] BYREF

  memset_0(FileName, 0, 0x104u);
  SepChar = ReadSepChar(a1);
  if ( SepChar == -1 )
    return 1;
  *((_BYTE *)a1 + 609) = SepChar;
  v4 = AddNormalChar;
  *((_QWORD *)a1 + 73) = *((_QWORD *)a1 + 72);
  v5 = 1;
  v58 = AddNormalChar;
  *((_DWORD *)a1 + 142) = 80;
  *((_QWORD *)a1 + 70) = 0;
  *((_BYTE *)a1 + 608) = 85;
  *((_QWORD *)a1 + 77) = 0;
  *((_QWORD *)a1 + 78) = 0;
  *((_QWORD *)a1 + 79) = 0;
  *((_BYTE *)a1 + 610) = 0;
  *((_QWORD *)a1 + 80) = 0;
  do
  {
    while ( 1 )
    {
LABEL_4:
      v6 = ReadSepChar(a1);
      if ( v6 == -1 )
      {
LABEL_124:
        v5 = FlushOutBuf(a1);
        goto LABEL_125;
      }
      if ( v6 != *((char *)a1 + 609) )
        goto LABEL_122;
      v7 = ReadSepChar(a1);
      v9 = v7;
      if ( v7 == -1 )
        goto LABEL_123;
      if ( v7 <= 69 )
        break;
      if ( v7 > 77 )
      {
        switch ( v7 )
        {
          case 'N':
            EnterSplSem(1);
            v47 = (const WCHAR *)AllocSplStr(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 80LL) + 56LL));
            LeaveSplSem(v48);
            if ( v47 )
            {
              DestinationString = 0;
              AnsiString = 0;
              RtlInitUnicodeString(&DestinationString, v47);
              if ( RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u) >= 0 )
              {
                Buffer = AnsiString.Buffer;
                if ( AnsiString.Buffer )
                {
                  Length = AnsiString.Length;
                  if ( AnsiString.Length )
                  {
                    do
                    {
                      v51 = *Buffer;
                      if ( !*Buffer )
                        break;
                      if ( !v5 )
                        break;
                      ++Buffer;
                      v5 = ((__int64 (__fastcall *)(struct GLOBAL_SEP_DATA *, _QWORD))v4)(a1, v51);
                      --Length;
                    }
                    while ( Length );
                  }
                }
                RtlFreeAnsiString(&AnsiString);
              }
              else
              {
                v5 = 0;
              }
              DllFreeSplStr(v47);
            }
            break;
          case 'S':
            goto LABEL_109;
          case 'T':
            ConvertTimetoChar((SYSTEMTIME *)(*(_QWORD *)(*(_QWORD *)a1 + 80LL) + 144LL), v8, FileName);
            v45 = FileName;
            if ( FileName[0] )
            {
              while ( v5 )
              {
                v46 = (unsigned int)*v45++;
                v5 = ((__int64 (__fastcall *)(struct GLOBAL_SEP_DATA *, __int64))v4)(a1, v46);
                if ( !*v45 )
                  goto LABEL_122;
              }
              goto LABEL_125;
            }
            break;
          case 'U':
            goto LABEL_109;
          case 'W':
            for ( i = 0; ; i = v43 + 2 * (i + 4 * (i - 6)) )
            {
              v43 = (unsigned int)ReadSepChar(a1);
              if ( !(unsigned int)_o_isdigit(v43) )
                break;
            }
            UngetSepChar(a1, v43);
            v44 = 256;
            if ( i <= 0x100 )
              v44 = i;
            *((_DWORD *)a1 + 142) = v44;
            break;
        }
        goto LABEL_122;
      }
      switch ( v7 )
      {
        case 'M':
          goto LABEL_109;
        case 'F':
          v5 = FlushNewLine(a1);
          if ( !v5 )
            goto LABEL_125;
          ReadFileName(a1, FileName, v34);
          if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 168LL) + 168LL) & 0x4000000) == 0 )
          {
            v35 = RevertToPrinterSelf();
            FileA = CreateFileA(FileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
            ImpersonatePrinterClient(v35);
            if ( FileA != (HANDLE)-1LL )
            {
              if ( GetFinalPathNameByHandleW(FileA, NameBuffer, 0x105u, 0) - 1 <= 0x103
                && (unsigned int)IsSepFilePathAllowed(NameBuffer, (wchar_t *)a1 + 8) )
              {
                FileSize = GetFileSize(FileA, 0);
                FileMappingW = CreateFileMappingW(FileA, 0, 2u, 0, 0, 0);
                v39 = FileMappingW;
                if ( FileMappingW && (_DWORD)FileSize )
                {
                  v40 = (char *)MapViewOfFile(FileMappingW, 4u, 0, 0, FileSize);
                  v41 = v40;
                  if ( v40 )
                  {
                    v5 = WriteSepBuf(a1, v40, FileSize);
                    UnmapViewOfFile(v41);
                  }
                  CloseHandle(v39);
                }
                CloseHandle(FileA);
                v4 = v58;
                goto LABEL_122;
              }
              CloseHandle(FileA);
            }
            LocalSpoolerTelemetry::WriteDbgTraceWarning(
              "DoSeparatorPage",
              L"Could not open separator page file %s",
              FileName);
          }
          break;
        case 'H':
          v29 = (unsigned int)ReadSepChar(a1);
          v30 = _o_isxdigit(v29);
          v18 = a1;
          if ( v30 )
          {
            v31 = (unsigned int)ReadSepChar(a1);
            if ( (unsigned int)_o_isxdigit(v31) )
            {
              v32 = 16 * ConvertAtoH(v29);
              v33 = ConvertAtoH(v31);
              v12 = ((__int64 (__fastcall *)(struct GLOBAL_SEP_DATA *, _QWORD))v4)(a1, (unsigned int)(char)(v32 + v33));
              goto LABEL_22;
            }
            v19 = v31;
            v18 = a1;
          }
          else
          {
            v19 = v29;
          }
LABEL_49:
          UngetSepChar(v18, v19);
          goto LABEL_122;
        case 'I':
          StringCchPrintfA(FileName, 0x104u, "%d", *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 80LL) + 40LL));
          v27 = FileName;
          if ( FileName[0] )
          {
            while ( v5 )
            {
              v28 = (unsigned int)*v27++;
              v5 = ((__int64 (__fastcall *)(struct GLOBAL_SEP_DATA *, __int64))v4)(a1, v28);
              if ( !*v27 )
                goto LABEL_122;
            }
            goto LABEL_125;
          }
          goto LABEL_122;
        case 'J':
          nSize = 260;
          if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
          {
            v23 = wcschr(NameBuffer, 0x5Cu);
            if ( v23 )
            {
              *v23 = 0;
              DestinationString = 0;
              AnsiString = 0;
              RtlInitUnicodeString(&DestinationString, NameBuffer);
              if ( RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u) < 0 )
              {
LABEL_46:
                v5 = 0;
                goto LABEL_125;
              }
              v24 = AnsiString.Buffer;
              if ( AnsiString.Buffer )
              {
                v25 = AnsiString.Length;
                if ( AnsiString.Length )
                {
                  do
                  {
                    v26 = *v24;
                    if ( !*v24 )
                      break;
                    if ( !v5 )
                      break;
                    ++v24;
                    v5 = ((__int64 (__fastcall *)(struct GLOBAL_SEP_DATA *, _QWORD))v4)(a1, v26);
                    --v25;
                  }
                  while ( v25 );
                }
              }
              RtlFreeAnsiString(&AnsiString);
            }
          }
          goto LABEL_122;
        case 'L':
          if ( *((_BYTE *)a1 + 608) != 85 )
          {
            while ( 1 )
            {
              if ( !v5 )
                goto LABEL_125;
              v20 = ReadSepChar(a1);
              v16 = v20;
              if ( v20 == -1 )
                goto LABEL_4;
              v17 = a1;
              if ( v20 == 10 )
                break;
              if ( v20 == 13 )
              {
                v22 = ReadSepChar(a1);
                if ( v22 != 10 )
                  v5 = AddBlockChar(a1, 13);
                UngetSepChar(a1, v22);
              }
              else
              {
                if ( v20 == *((char *)a1 + 609) )
                {
                  v16 = ReadSepChar(a1);
                  v17 = a1;
                  if ( v16 != *((char *)a1 + 609) )
                  {
LABEL_48:
                    UngetSepChar(v17, v16);
                    v19 = *((char *)a1 + 609);
                    goto LABEL_49;
                  }
                }
                v21 = AddBlockChar(v17, v16);
LABEL_60:
                v5 = v21;
              }
            }
            v21 = FlushOutBuf(a1);
            goto LABEL_60;
          }
          while ( 1 )
          {
            v15 = ReadSepChar(a1);
            v16 = v15;
            if ( v15 == -1 )
              break;
            if ( v15 == *((char *)a1 + 609) )
            {
              v16 = ReadSepChar(a1);
              if ( v16 != *((char *)a1 + 609) )
              {
                v17 = a1;
                goto LABEL_48;
              }
            }
            v5 = AddNormalChar(a1, v16);
            if ( !v5 )
              goto LABEL_46;
          }
          break;
        default:
          goto LABEL_122;
      }
    }
    if ( v7 == 69 )
    {
      v5 = FlushNewLine(a1);
      if ( !v5 )
        goto LABEL_125;
      v10 = 1;
      v11 = (char *)&qword_18010CCE8;
LABEL_21:
      v12 = WriteSepBuf(a1, v11, v10);
LABEL_22:
      v5 = v12;
      continue;
    }
    if ( v7 > 54 )
    {
      switch ( v7 )
      {
        case '7':
        case '8':
        case '9':
          goto LABEL_16;
        case 'B':
LABEL_109:
          v5 = FlushNewLine(a1);
          *((_BYTE *)a1 + 608) = v9;
          v4 = AddNormalChar;
          if ( (_BYTE)v9 != 85 )
            v4 = (int (*)(struct GLOBAL_SEP_DATA *, int))AddBlockChar;
          v58 = v4;
          break;
        case 'D':
          ConvertDatetoChar((SYSTEMTIME *)(*(_QWORD *)(*(_QWORD *)a1 + 80LL) + 144LL), v8, FileName);
          v13 = FileName;
          if ( FileName[0] )
          {
            while ( v5 )
            {
              v14 = (unsigned int)*v13++;
              v5 = ((__int64 (__fastcall *)(struct GLOBAL_SEP_DATA *, __int64))v4)(a1, v14);
              if ( !*v13 )
                goto LABEL_122;
            }
            goto LABEL_125;
          }
          break;
      }
    }
    else if ( v7 == 54 || v7 == 48 || v7 == 49 || v7 == 50 || v7 == 51 || (unsigned int)(v7 - 52) <= 1 )
    {
LABEL_16:
      if ( *((_BYTE *)a1 + 608) == 85 )
        v5 = AddNormalChar(a1, 10);
      if ( !v5 )
        goto LABEL_125;
      v5 = FlushOutBuf(a1);
      if ( !v5 )
        goto LABEL_125;
      v10 = 2 * v9 - 96;
      v11 = "\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r\n";
      goto LABEL_21;
    }
LABEL_122:
    ;
  }
  while ( v5 );
LABEL_123:
  if ( v5 )
    goto LABEL_124;
LABEL_125:
  v52 = (HDC)*((_QWORD *)a1 + 77);
  if ( v52 )
    DeleteDC(v52);
  v53 = (void *)*((_QWORD *)a1 + 78);
  if ( v53 )
    DeleteObject(v53);
  v54 = (void *)*((_QWORD *)a1 + 79);
  if ( v54 )
    DeleteObject(v54);
  v55 = *((_QWORD *)a1 + 80);
  if ( v55 )
    DllFreeSplMem(v55);
  return v5;
}

```

## disassembly

```asm
0x18009646c  mov     [rsp-8+arg_8], rbx
0x180096471  mov     [rsp-8+arg_10], rsi
0x180096476  push    rbp
0x180096477  push    rdi
0x180096478  push    r12
0x18009647a  push    r14
0x18009647c  push    r15
0x18009647e  lea     rbp, [rsp-2A0h]
0x180096486  sub     rsp, 3A0h
0x18009648d  mov     rax, cs:__security_cookie
0x180096494  xor     rax, rsp
0x180096497  mov     [rbp+2C0h+var_30], rax
0x18009649e  mov     rdi, rcx
0x1800964a1  xor     edx, edx; Val
0x1800964a3  lea     rcx, [rsp+3C0h+FileName]; void *
0x1800964a8  mov     r8d, 104h; Size
0x1800964ae  call    memset_0
0x1800964b3  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800964b6  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x1800964bb  cmp     eax, 0FFFFFFFFh
0x1800964be  jnz     short loc_1800964CA
0x1800964c0  mov     eax, 1
0x1800964c5  jmp     loc_180096CB7
0x1800964ca  xor     r15d, r15d
0x1800964cd  mov     [rdi+261h], al
0x1800964d3  mov     rax, [rdi+240h]
0x1800964da  lea     r12, ?AddNormalChar@@YAHPEAUGLOBAL_SEP_DATA@@H@Z; AddNormalChar(GLOBAL_SEP_DATA *,int)
0x1800964e1  mov     [rdi+248h], rax
0x1800964e8  mov     esi, 1
0x1800964ed  mov     [rsp+3C0h+var_368], r12
0x1800964f2  mov     dword ptr [rdi+238h], 50h ; 'P'
0x1800964fc  mov     [rdi+230h], r15
0x180096503  mov     byte ptr [rdi+260h], 55h ; 'U'
0x18009650a  mov     [rdi+268h], r15
0x180096511  mov     [rdi+270h], r15
0x180096518  mov     [rdi+278h], r15
0x18009651f  mov     [rdi+262h], r15b
0x180096526  mov     [rdi+280h], r15
0x18009652d  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x180096530  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x180096535  cmp     eax, 0FFFFFFFFh
0x180096538  jz      loc_180096C63
0x18009653e  movsx   ecx, byte ptr [rdi+261h]
0x180096545  cmp     eax, ecx
0x180096547  jnz     loc_180096C57
0x18009654d  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x180096550  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x180096555  mov     ebx, eax
0x180096557  cmp     eax, 0FFFFFFFFh
0x18009655a  jz      loc_180096C5F
0x180096560  cmp     eax, 45h ; 'E'
0x180096563  jg      loc_18009667E
0x180096569  jz      loc_18009665A
0x18009656f  cmp     eax, 36h ; '6'
0x180096572  jg      short loc_1800965EA
0x180096574  jz      short loc_18009659A
0x180096576  mov     ecx, eax
0x180096578  sub     ecx, 30h ; '0'
0x18009657b  jz      short loc_18009659A
0x18009657d  sub     ecx, 1
0x180096580  jz      short loc_18009659A
0x180096582  sub     ecx, 1
0x180096585  jz      short loc_18009659A
0x180096587  sub     ecx, 1
0x18009658a  jz      short loc_18009659A
0x18009658c  sub     ecx, 1
0x18009658f  jz      short loc_18009659A
0x180096591  cmp     ecx, 1
0x180096594  jnz     loc_180096C57
0x18009659a  cmp     byte ptr [rdi+260h], 55h ; 'U'
0x1800965a1  jnz     short loc_1800965B2
0x1800965a3  mov     edx, 0Ah; int
0x1800965a8  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800965ab  call    ?AddNormalChar@@YAHPEAUGLOBAL_SEP_DATA@@H@Z; AddNormalChar(GLOBAL_SEP_DATA *,int)
0x1800965b0  mov     esi, eax
0x1800965b2  test    esi, esi
0x1800965b4  jz      loc_180096C6D
0x1800965ba  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800965bd  call    ?FlushOutBuf@@YAHPEAUGLOBAL_SEP_DATA@@@Z; FlushOutBuf(GLOBAL_SEP_DATA *)
0x1800965c2  mov     esi, eax
0x1800965c4  test    eax, eax
0x1800965c6  jz      loc_180096C6D
0x1800965cc  lea     r8d, ds:0FFFFFFFFFFFFFFA0h[rbx*2]; unsigned int
0x1800965d4  lea     rdx, asc_18010CCC0; "\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r\n\r"...
0x1800965db  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800965de  call    ?WriteSepBuf@@YAHPEAUGLOBAL_SEP_DATA@@PEADK@Z; WriteSepBuf(GLOBAL_SEP_DATA *,char *,ulong)
0x1800965e3  mov     esi, eax
0x1800965e5  jmp     loc_180096C57
0x1800965ea  mov     ecx, ebx
0x1800965ec  sub     ecx, 37h ; '7'
0x1800965ef  jz      short loc_18009659A
0x1800965f1  sub     ecx, 1
0x1800965f4  jz      short loc_18009659A
0x1800965f6  sub     ecx, 1
0x1800965f9  jz      short loc_18009659A
0x1800965fb  sub     ecx, 9
0x1800965fe  jz      loc_180096B74
0x180096604  cmp     ecx, 2
0x180096607  jnz     loc_180096C57
0x18009660d  mov     rax, [rdi]
0x180096610  lea     r8, [rsp+3C0h+FileName]; char *
0x180096615  mov     rcx, [rax+50h]
0x180096619  add     rcx, 90h; lpUniversalTime
0x180096620  call    ?ConvertDatetoChar@@YAXPEAU_SYSTEMTIME@@KPEAD@Z; ConvertDatetoChar(_SYSTEMTIME *,ulong,char *)
0x180096625  lea     rbx, [rsp+3C0h+FileName]
0x18009662a  cmp     [rsp+3C0h+FileName], r15b
0x18009662f  jz      loc_180096C57
0x180096635  test    esi, esi
0x180096637  jz      loc_180096C6D
0x18009663d  movsx   edx, byte ptr [rbx]
0x180096640  mov     rcx, rdi
0x180096643  mov     rax, r12
0x180096646  inc     rbx
0x180096649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009664e  mov     esi, eax
0x180096650  cmp     [rbx], r15b
0x180096653  jnz     short loc_180096635
0x180096655  jmp     loc_180096C57
0x18009665a  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x18009665d  call    ?FlushNewLine@@YAHPEAUGLOBAL_SEP_DATA@@@Z; FlushNewLine(GLOBAL_SEP_DATA *)
0x180096662  mov     esi, eax
0x180096664  test    eax, eax
0x180096666  jz      loc_180096C6D
0x18009666c  mov     r8d, 1
0x180096672  lea     rdx, qword_18010CCE8
0x180096679  jmp     loc_1800965DB
0x18009667e  cmp     ebx, 4Dh ; 'M'
0x180096681  jg      loc_180096AB1
0x180096687  jz      loc_180096B74
0x18009668d  sub     ebx, 46h ; 'F'
0x180096690  jz      loc_18009693C
0x180096696  sub     ebx, 2
0x180096699  jz      loc_1800968D4
0x18009669f  sub     ebx, 1
0x1800966a2  jz      loc_18009687E
0x1800966a8  sub     ebx, 1
0x1800966ab  jz      loc_1800967B3
0x1800966b1  cmp     ebx, 2
0x1800966b4  jnz     loc_180096C57
0x1800966ba  cmp     byte ptr [rdi+260h], 55h ; 'U'
0x1800966c1  jnz     loc_1800967AA
0x1800966c7  test    esi, esi
0x1800966c9  jz      loc_180096C6D
0x1800966cf  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800966d2  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x1800966d7  mov     edx, eax
0x1800966d9  cmp     eax, 0FFFFFFFFh
0x1800966dc  jz      loc_18009652D
0x1800966e2  movsx   ecx, byte ptr [rdi+261h]
0x1800966e9  cmp     eax, ecx
0x1800966eb  jnz     short loc_180096702
0x1800966ed  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800966f0  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x1800966f5  mov     edx, eax; int
0x1800966f7  movsx   eax, byte ptr [rdi+261h]
0x1800966fe  cmp     edx, eax
0x180096700  jnz     short loc_180096718
0x180096702  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x180096705  call    ?AddNormalChar@@YAHPEAUGLOBAL_SEP_DATA@@H@Z; AddNormalChar(GLOBAL_SEP_DATA *,int)
0x18009670a  mov     esi, eax
0x18009670c  test    eax, eax
0x18009670e  jnz     short loc_1800966CF
0x180096710  mov     esi, r15d
0x180096713  jmp     loc_180096C6D
0x180096718  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x18009671b  call    ?UngetSepChar@@YAXPEAUGLOBAL_SEP_DATA@@H@Z; UngetSepChar(GLOBAL_SEP_DATA *,int)
0x180096720  movsx   edx, byte ptr [rdi+261h]; int
0x180096727  call    ?UngetSepChar@@YAXPEAUGLOBAL_SEP_DATA@@H@Z; UngetSepChar(GLOBAL_SEP_DATA *,int)
0x18009672c  jmp     loc_180096C57
0x180096731  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x180096734  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x180096739  mov     edx, eax
0x18009673b  cmp     eax, 0FFFFFFFFh
0x18009673e  jz      loc_18009652D
0x180096744  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x180096747  cmp     eax, 0Ah
0x18009674a  jnz     short loc_180096753
0x18009674c  call    ?FlushOutBuf@@YAHPEAUGLOBAL_SEP_DATA@@@Z; FlushOutBuf(GLOBAL_SEP_DATA *)
0x180096751  jmp     short loc_1800967A8
0x180096753  cmp     edx, 0Dh
0x180096756  jnz     short loc_18009677F
0x180096758  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x18009675d  mov     ebx, eax
0x18009675f  cmp     eax, 0Ah
0x180096762  jz      short loc_180096773
0x180096764  mov     edx, 0Dh; int
0x180096769  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x18009676c  call    ?AddBlockChar@@YAHPEAUGLOBAL_SEP_DATA@@H@Z; AddBlockChar(GLOBAL_SEP_DATA *,int)
0x180096771  mov     esi, eax
0x180096773  mov     edx, ebx; int
0x180096775  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x180096778  call    ?UngetSepChar@@YAXPEAUGLOBAL_SEP_DATA@@H@Z; UngetSepChar(GLOBAL_SEP_DATA *,int)
0x18009677d  jmp     short loc_1800967AA
0x18009677f  movsx   eax, byte ptr [rdi+261h]
0x180096786  cmp     edx, eax
0x180096788  jnz     short loc_1800967A3
0x18009678a  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x18009678f  movsx   ecx, byte ptr [rdi+261h]
0x180096796  mov     edx, eax; int
0x180096798  cmp     eax, ecx
0x18009679a  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x18009679d  jnz     loc_18009671B
0x1800967a3  call    ?AddBlockChar@@YAHPEAUGLOBAL_SEP_DATA@@H@Z; AddBlockChar(GLOBAL_SEP_DATA *,int)
0x1800967a8  mov     esi, eax
0x1800967aa  test    esi, esi
0x1800967ac  jnz     short loc_180096731
0x1800967ae  jmp     loc_180096C6D
0x1800967b3  lea     r8, [rsp+3C0h+nSize]; nSize
0x1800967b8  mov     [rsp+3C0h+nSize], 104h
0x1800967c0  lea     rdx, [rbp+2C0h+NameBuffer]; lpNameBuffer
0x1800967c7  mov     ecx, 2; NameFormat
0x1800967cc  call    cs:__imp_GetUserNameExW
0x1800967d2  test    al, al
0x1800967d4  jz      loc_180096C57
0x1800967da  mov     edx, 5Ch ; '\'; Ch
0x1800967df  lea     rcx, [rbp+2C0h+NameBuffer]; Str
0x1800967e6  call    cs:__imp_wcschr
0x1800967ec  test    rax, rax
0x1800967ef  jz      loc_180096C57
0x1800967f5  xorps   xmm0, xmm0
0x1800967f8  mov     [rax], r15w
0x1800967fc  xorps   xmm1, xmm1
0x1800967ff  lea     rdx, [rbp+2C0h+NameBuffer]; SourceString
0x180096806  lea     rcx, [rsp+3C0h+DestinationString]; DestinationString
0x18009680b  movups  xmmword ptr [rsp+3C0h+DestinationString.Length], xmm0
0x180096810  movups  xmmword ptr [rsp+3C0h+AnsiString.Length], xmm1
0x180096815  call    cs:__imp_RtlInitUnicodeString
0x18009681b  mov     r8b, 1; AllocateDestinationString
0x18009681e  lea     rdx, [rsp+3C0h+DestinationString]; SourceString
0x180096823  lea     rcx, [rsp+3C0h+AnsiString]; DestinationString
0x180096828  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18009682e  test    eax, eax
0x180096830  js      loc_180096710
0x180096836  mov     rbx, [rsp+3C0h+AnsiString.Buffer]
0x18009683b  test    rbx, rbx
0x18009683e  jz      short loc_18009686E
0x180096840  movzx   r14d, [rsp+3C0h+AnsiString.Length]
0x180096846  test    r14d, r14d
0x180096849  jz      short loc_18009686E
0x18009684b  movsx   eax, byte ptr [rbx]
0x18009684e  test    al, al
0x180096850  jz      short loc_18009686E
0x180096852  test    esi, esi
0x180096854  jz      short loc_18009686E
0x180096856  mov     edx, eax
0x180096858  mov     rcx, rdi
0x18009685b  mov     rax, r12
0x18009685e  inc     rbx
0x180096861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096866  mov     esi, eax
0x180096868  add     r14d, 0FFFFFFFFh
0x18009686c  jnz     short loc_18009684B
0x18009686e  lea     rcx, [rsp+3C0h+AnsiString]; AnsiString
0x180096873  call    cs:__imp_RtlFreeAnsiString
0x180096879  jmp     loc_180096C57
0x18009687e  mov     rax, [rdi]
0x180096881  lea     r8, aD_0; "%d"
0x180096888  mov     edx, 104h; unsigned __int64
0x18009688d  lea     rcx, [rsp+3C0h+FileName]; char *
0x180096892  mov     r9, [rax+50h]
0x180096896  mov     r9d, [r9+28h]
0x18009689a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18009689f  lea     rbx, [rsp+3C0h+FileName]
0x1800968a4  cmp     [rsp+3C0h+FileName], r15b
0x1800968a9  jz      loc_180096C57
0x1800968af  test    esi, esi
0x1800968b1  jz      loc_180096C6D
0x1800968b7  movsx   edx, byte ptr [rbx]
0x1800968ba  mov     rcx, rdi
0x1800968bd  mov     rax, r12
0x1800968c0  inc     rbx
0x1800968c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800968c8  mov     esi, eax
0x1800968ca  cmp     [rbx], r15b
0x1800968cd  jnz     short loc_1800968AF
0x1800968cf  jmp     loc_180096C57
0x1800968d4  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800968d7  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x1800968dc  mov     ecx, eax
0x1800968de  mov     ebx, eax
0x1800968e0  call    cs:__imp__o_isxdigit
0x1800968e6  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x1800968e9  test    eax, eax
0x1800968eb  jz      short loc_180096935
0x1800968ed  call    ?ReadSepChar@@YAHPEAUGLOBAL_SEP_DATA@@@Z; ReadSepChar(GLOBAL_SEP_DATA *)
0x1800968f2  mov     ecx, eax
0x1800968f4  mov     r14d, eax
0x1800968f7  call    cs:__imp__o_isxdigit
0x1800968fd  test    eax, eax
0x1800968ff  jz      short loc_18009692A
0x180096901  mov     ecx, ebx; int
0x180096903  call    ?ConvertAtoH@@YAHH@Z; ConvertAtoH(int)
0x180096908  mov     ebx, eax
0x18009690a  mov     ecx, r14d; int
0x18009690d  shl     bl, 4
0x180096910  call    ?ConvertAtoH@@YAHH@Z; ConvertAtoH(int)
0x180096915  add     al, bl
0x180096917  mov     rcx, rdi
0x18009691a  movsx   edx, al
0x18009691d  mov     rax, r12
  ... truncated ...
```
