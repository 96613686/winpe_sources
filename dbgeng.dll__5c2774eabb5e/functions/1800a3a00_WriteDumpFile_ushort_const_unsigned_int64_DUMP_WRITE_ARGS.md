# WriteDumpFile(ushort const *,unsigned __int64,DUMP_WRITE_ARGS *)

- ea: `0x1800a3a00`
- end: `0x1800a403d`
- name: `?WriteDumpFile@@YAJPEBG_KPEAUDUMP_WRITE_ARGS@@@Z`
- size: `1597`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, HANDLE hObject, struct DUMP_WRITE_ARGS *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801b2a1c`
- `0x180216510`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x18007cf9c`
- `0x18007d308`
- `0x180085700`
- `0x18008b49c`
- `0x18008e740`
- `0x180092338`
- `0x1800954c4`
- `0x1800986ec`
- `0x1800a3a00`
- `0x1800b94c4`
- `0x1800c12b8`
- `0x1800cc028`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x1801951ec`
- `0x180216000`
- `0x1802aa190`
- `0x180418224`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3eda`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a3eed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a3fb0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a3eed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a3fb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a3def`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a3def`

## string_xrefs

- `0x1800a3ae4`: `Invalid arguments - can not create dump file\n`
- `0x1800a3b2c`: `Cannot find KiProcessorBlock - can not create dump file\n`
- `0x1800a3ba4`: `Writing this dump file may take a long time.\nPress Ctrl-C or Ctrl-Break if you want to terminate the command.\n`
- `0x1800a3bbc`: `Please avoid compressing kernel full memory dump in a CAB if the debugged target has more than 2GB of memory.\n`
- `0x1800a3bc8`: `The debugger cannot compress dump files larger than 2GB due to CAB max file size limitations.\n`
- `0x1800a3cc0`: `Unable to allocate dump write target\n`
- `0x1800a3e59`: `Unable to create file '%ws' - %s\n    "%s"\n`
- `0x1800a3fbe`: `Failed creating the Cab file, but the temporal Dump file won't be deleted.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteDumpFile(
        unsigned __int16 *lpWideCharStr,
        HANDLE hObject,
        struct DUMP_WRITE_ARGS *a3,
        __int64 a4)
{
  HANDLE v5; // rbx
  TargetInfo *v8; // rcx
  int v9; // eax
  unsigned int *v10; // r14
  int v11; // edx
  __int64 v12; // r8
  char v13; // cl
  int v14; // ecx
  unsigned int v15; // ecx
  char v16; // cl
  unsigned int v17; // ecx
  char v18; // cl
  struct TargetInfo *v19; // r12
  unsigned int CabFromDump; // edi
  const unsigned __int16 *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8
  WCHAR *v24; // rsi
  HANDLE FileW; // r13
  int *v26; // r8
  unsigned __int16 **v27; // r9
  signed int LastError; // eax
  const unsigned __int16 *v29; // rbx
  unsigned __int16 *v30; // rax
  const char *v31; // rbx
  char *v32; // rdx
  unsigned int v33; // [rsp+48h] [rbp-C0h]
  const char *v36; // [rsp+68h] [rbp-A0h] BYREF
  int v37; // [rsp+74h] [rbp-94h]
  char *v38; // [rsp+188h] [rbp+80h] BYREF
  int v39; // [rsp+194h] [rbp+8Ch]
  WCHAR FileName[520]; // [rsp+2A8h] [rbp+1A0h] BYREF

  v5 = hObject;
  if ( (g_EngOptions & 0x400000) != 0 )
  {
    ErrOut(
      L"This dump file contains sensitive data.\n"
       "Gathering a dump of this data has been disabled and your dump could not be saved.\n");
    return 2147500037LL;
  }
  v8 = g_Target;
  if ( g_Target && *((_BYTE *)g_Target + 44) && (g_EngStatus & 2) != 0 && g_Process && g_Thread && g_Machine )
  {
    v9 = *((_DWORD *)g_Target + 1026);
    if ( v9 == 1 )
    {
      v10 = (unsigned int *)((char *)a3 + 4);
      if ( (*((_DWORD *)a3 + 1) & 0xFFFFFFF) != 0 )
      {
        ErrOut(L"Invalid arguments - can not create dump file\n");
        return 2147942487LL;
      }
      if ( !*((_QWORD *)g_Target + 167) )
      {
        v11 = *((_DWORD *)g_Target + 1027);
        if ( ((unsigned int)(v11 - 1024) <= 5 || v11 == 3143)
          && !*((_QWORD *)g_Target + (unsigned int)(*((_DWORD *)g_Thread + 16) - 1) + 558) )
        {
          ErrOut(L"Cannot find KiProcessorBlock - can not create dump file\n");
          return 2147500037LL;
        }
      }
      if ( *((_DWORD *)g_Target + 1027) )
        v12 = 0;
      else
        v12 = *((_QWORD *)g_Target + 530);
      switch ( *(_DWORD *)a3 )
      {
        case 0x400:
          v15 = (*(_BYTE *)(*((_QWORD *)g_Target + 83) + 56LL) != 0) + 4;
          break;
        case 0x401:
          v18 = *(_BYTE *)(*((_QWORD *)g_Target + 83) + 56LL);
          if ( EngineConfiguration::s_UseRangeDumpFormatForKernelMemDumpFiles )
          {
            v14 = -(v18 != 0);
LABEL_29:
            v15 = v14 + 9;
            break;
          }
          v15 = (v18 != 0) + 6;
          break;
        case 0x402:
          if ( v12 && !*(_BYTE *)(v12 + 36) )
          {
            WarnOut(
              L"Writing this dump file may take a long time.\n"
               "Press Ctrl-C or Ctrl-Break if you want to terminate the command.\n");
            v8 = g_Target;
          }
          if ( (*v10 & 0x20000000) != 0 )
          {
            WarnOut(
              L"Please avoid compressing kernel full memory dump in a CAB if the debugged target has more than 2GB of memory.\n");
            WarnOut(L"The debugger cannot compress dump files larger than 2GB due to CAB max file size limitations.\n");
            v8 = g_Target;
          }
          v16 = *(_BYTE *)(*((_QWORD *)v8 + 83) + 56LL);
          if ( EngineConfiguration::s_UseRangeDumpFormatForFullMemDumpFiles )
            v17 = v16 != 0 ? 0xFFFFFFFC : 0;
          else
            v17 = v16 != 0;
          v15 = v17 + 12;
          break;
        case 0x406:
          v13 = *(_BYTE *)(*((_QWORD *)g_Target + 83) + 56LL);
          if ( EngineConfiguration::s_UseRangeDumpFormatForKernelMemDumpFiles )
            v14 = v13 != 0 ? 2 : 0;
          else
            v14 = v13 != 0;
          goto LABEL_29;
        default:
          return 2147942487LL;
      }
    }
    else
    {
      if ( (unsigned int)(v9 - 2) > 1 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(g_Target, hObject, g_Thread, a4);
        v8 = g_Target;
      }
      if ( *(_DWORD *)a3 == 1024 )
      {
        v10 = (unsigned int *)((char *)a3 + 4);
        if ( (*((_DWORD *)a3 + 1) & 0x3F80000) != 0 )
          return 2147942487LL;
        v15 = 17;
        if ( (*(_BYTE *)v10 & 1) == 0 )
          v15 = 16;
      }
      else
      {
        if ( *(_DWORD *)a3 != 1025 )
          return 2147942487LL;
        v10 = (unsigned int *)((char *)a3 + 4);
        if ( (*((_DWORD *)a3 + 1) & 0xFFFFFFF) != 0 )
          return 2147942487LL;
        v15 = (*(_BYTE *)(*((_QWORD *)v8 + 83) + 56LL) != 0) + 14;
      }
    }
    v19 = NewFileTargetInfo(v15);
    if ( !v19 )
    {
      ErrOut(L"Unable to allocate dump write target\n");
      return 2147942414LL;
    }
    v33 = *((_DWORD *)g_Target + 168);
    TargetInfo::SetEffMachine(g_Target, *((_DWORD *)g_Target + 23), 0);
    TargetInfo::FlushRegContext(g_Target);
    if ( (*v10 & 0x20000000) != 0 )
    {
      if ( v5 )
      {
LABEL_56:
        CabFromDump = -2147024809;
LABEL_98:
        TargetInfo::SetEffMachine(g_Target, v33, 0);
        (**(void (__fastcall ***)(struct TargetInfo *, __int64))v19)(v19, 1);
        return CabFromDump;
      }
      if ( !DbgGetTempPathW(0x208u, FileName) )
        CopyNStringW(FileName);
      v21 = PathTail(lpWideCharStr);
      CatNStringW(FileName, v21, v22, 520);
      CatNStringW(FileName, L".dmp", v23, 520);
      v24 = FileName;
      *v10 &= ~0x80000000;
    }
    else
    {
      v24 = L"<HandleOnly>";
      if ( lpWideCharStr )
        v24 = lpWideCharStr;
      if ( v5 )
      {
        if ( v5 == (HANDLE)-1LL )
          goto LABEL_56;
        FileW = v5;
LABEL_74:
        dprintf(L"Creating %ws - ", v24);
        CabFromDump = (*(__int64 (__fastcall **)(struct TargetInfo *, HANDLE, struct DUMP_WRITE_ARGS *))(*(_QWORD *)v19 + 1568LL))(
                        v19,
                        FileW,
                        a3);
        if ( !CabFromDump )
        {
          dprintf(L"Dump successfully written\n");
          if ( *((_DWORD *)g_Target + 23) == 452 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)g_Target + 83) + 128LL))(*((_QWORD *)g_Target + 83));
        }
        if ( v5 )
        {
          if ( CabFromDump )
            goto LABEL_98;
        }
        else
        {
          CloseHandle(FileW);
          if ( CabFromDump )
          {
            DeleteFileW(v24);
            goto LABEL_98;
          }
        }
        if ( (*v10 & 0x20000000) == 0 )
          goto LABEL_98;
        DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(&v36);
        if ( v24 )
        {
          if ( !DbsDynamicString<char>::CopyStr((DbsDynamicBuffer *)&v36, v24, -1) )
          {
            CabFromDump = -2147024882;
LABEL_97:
            DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v36);
            goto LABEL_98;
          }
          v31 = 0;
          if ( v37 )
            v31 = v36;
        }
        else
        {
          v31 = 0;
        }
        DbsDeclDynamicString<char,260,1>::DbsDeclDynamicString<char,260,1>(&v38);
        v32 = (char *)lpWideCharStr;
        if ( lpWideCharStr )
        {
          if ( !DbsDynamicString<char>::CopyStr((DbsDynamicBuffer *)&v38, lpWideCharStr, -1) )
          {
            CabFromDump = -2147024882;
LABEL_96:
            DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v38);
            goto LABEL_97;
          }
          v32 = 0;
          if ( v39 )
            v32 = v38;
        }
        CabFromDump = CreateCabFromDump(v31, v32, *v10);
        if ( CabFromDump )
          dprintf(L"Failed creating the Cab file, but the temporal Dump file won't be deleted.\n");
        else
          DeleteFileW(FileName);
        goto LABEL_96;
      }
    }
    if ( IsSecureMode() )
    {
      ErrOut(L"SECURE: Dump writing disallowed\n");
      return 2147942405LL;
    }
    FileW = CreateFileW(v24, 0xC0000000, 0, 0, ((int)*v10 >> 31) + 2, 0x8000080u, 0);
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        CabFromDump = LastError;
        if ( LastError > 0 )
          CabFromDump = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        CabFromDump = -2147467259;
      }
      v29 = FormatAnyStatus(CabFromDump, 0, v26, v27);
      v30 = FormatStatusCode(CabFromDump);
      ErrOut(L"Unable to create file '%ws' - %s\n    \"%s\"\n", v24, v30, v29);
      if ( CabFromDump )
        goto LABEL_98;
      v5 = hObject;
    }
    goto LABEL_74;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800a3a00  mov     rax, rsp
0x1800a3a03  push    rbp
0x1800a3a04  push    rsi
0x1800a3a05  push    rdi
0x1800a3a06  push    r12
0x1800a3a08  push    r13
0x1800a3a0a  push    r14
0x1800a3a0c  push    r15
0x1800a3a0e  lea     rbp, [rax-5F8h]
0x1800a3a15  sub     rsp, 6C0h
0x1800a3a1c  mov     [rsp+6F0h+var_698], 0FFFFFFFFFFFFFFFEh
0x1800a3a25  mov     [rax+20h], rbx
0x1800a3a29  mov     rax, cs:__security_cookie
0x1800a3a30  xor     rax, rsp
0x1800a3a33  mov     [rbp+5F0h+var_40], rax
0x1800a3a3a  mov     r15, r8
0x1800a3a3d  mov     rbx, rdx
0x1800a3a40  mov     [rsp+6F0h+var_6A8], rdx
0x1800a3a45  mov     rdi, rcx
0x1800a3a48  mov     [rsp+6F0h+lpWideCharStr], rcx
0x1800a3a4d  test    cs:?g_EngOptions@@3KA, 400000h; ulong g_EngOptions
0x1800a3a57  jz      short loc_1800A3A6F
0x1800a3a59  lea     rcx, aThisDumpFileCo; "This dump file contains sensitive data."...
0x1800a3a60  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800a3a65  mov     eax, 80004005h
0x1800a3a6a  jmp     loc_1800A4012
0x1800a3a6f  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800a3a76  xor     r13d, r13d
0x1800a3a79  test    rcx, rcx
0x1800a3a7c  jz      loc_1800A400D
0x1800a3a82  cmp     [rcx+2Ch], r13b
0x1800a3a86  jz      loc_1800A400D
0x1800a3a8c  test    byte ptr cs:?g_EngStatus@@3KA, 2; ulong g_EngStatus
0x1800a3a93  jz      loc_1800A400D
0x1800a3a99  cmp     cs:?g_Process@@3PEAVProcessInfo@@EA, r13; ProcessInfo * g_Process
0x1800a3aa0  jz      loc_1800A400D
0x1800a3aa6  mov     r8, cs:?g_Thread@@3PEAVThreadInfo@@EA; ThreadInfo * g_Thread
0x1800a3aad  test    r8, r8
0x1800a3ab0  jz      loc_1800A400D
0x1800a3ab6  cmp     cs:?g_Machine@@3PEAVMachineInfo@@EA, r13; MachineInfo * g_Machine
0x1800a3abd  jz      loc_1800A400D
0x1800a3ac3  mov     eax, [rcx+1008h]
0x1800a3ac9  mov     esi, 20000000h
0x1800a3ace  cmp     eax, 1
0x1800a3ad1  jnz     loc_1800A3C44
0x1800a3ad7  lea     r14, [r15+4]
0x1800a3adb  test    dword ptr [r14], 0FFFFFFFh
0x1800a3ae2  jz      short loc_1800A3AFA
0x1800a3ae4  lea     rcx, aInvalidArgumen_3; "Invalid arguments - can not create dump"...
0x1800a3aeb  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800a3af0  mov     eax, 80070057h
0x1800a3af5  jmp     loc_1800A4012
0x1800a3afa  cmp     [rcx+538h], r13
0x1800a3b01  jnz     short loc_1800A3B38
0x1800a3b03  mov     edx, [rcx+100Ch]
0x1800a3b09  lea     eax, [rdx-400h]
0x1800a3b0f  cmp     eax, 5
0x1800a3b12  jbe     short loc_1800A3B1C
0x1800a3b14  cmp     edx, 0C47h
0x1800a3b1a  jnz     short loc_1800A3B38
0x1800a3b1c  mov     eax, [r8+40h]
0x1800a3b20  dec     eax
0x1800a3b22  cmp     [rcx+rax*8+1170h], r13
0x1800a3b2a  jnz     short loc_1800A3B38
0x1800a3b2c  lea     rcx, aCannotFindKipr; "Cannot find KiProcessorBlock - can not "...
0x1800a3b33  jmp     loc_1800A3A60
0x1800a3b38  cmp     [rcx+100Ch], r13d
0x1800a3b3f  jnz     short loc_1800A3B4A
0x1800a3b41  mov     r8, [rcx+1090h]
0x1800a3b48  jmp     short loc_1800A3B4D
0x1800a3b4a  mov     r8, r13
0x1800a3b4d  mov     edx, [r15]
0x1800a3b50  sub     edx, 400h
0x1800a3b56  jz      loc_1800A3C2F
0x1800a3b5c  sub     edx, 1
0x1800a3b5f  jz      loc_1800A3C05
0x1800a3b65  sub     edx, 1
0x1800a3b68  jz      short loc_1800A3B99
0x1800a3b6a  cmp     edx, 4
0x1800a3b6d  jnz     short loc_1800A3AF0
0x1800a3b6f  mov     rax, [rcx+298h]
0x1800a3b76  mov     cl, [rax+38h]
0x1800a3b79  cmp     cs:?s_UseRangeDumpFormatForKernelMemDumpFiles@EngineConfiguration@@0_NA, r13b; bool EngineConfiguration::s_UseRangeDumpFormatForKernelMemDumpFiles
0x1800a3b80  jz      short loc_1800A3B8B
0x1800a3b82  neg     cl
0x1800a3b84  sbb     ecx, ecx
0x1800a3b86  and     ecx, 2
0x1800a3b89  jmp     short loc_1800A3B91
0x1800a3b8b  neg     cl
0x1800a3b8d  sbb     ecx, ecx
0x1800a3b8f  neg     ecx
0x1800a3b91  add     ecx, 9
0x1800a3b94  jmp     loc_1800A3CB3
0x1800a3b99  test    r8, r8
0x1800a3b9c  jz      short loc_1800A3BB7
0x1800a3b9e  cmp     [r8+24h], r13b
0x1800a3ba2  jnz     short loc_1800A3BB7
0x1800a3ba4  lea     rcx, aWritingThisDum; "Writing this dump file may take a long "...
0x1800a3bab  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1800a3bb0  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800a3bb7  test    [r14], esi
0x1800a3bba  jz      short loc_1800A3BDB
0x1800a3bbc  lea     rcx, aPleaseAvoidCom; "Please avoid compressing kernel full me"...
0x1800a3bc3  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1800a3bc8  lea     rcx, aTheDebuggerCan; "The debugger cannot compress dump files"...
0x1800a3bcf  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1800a3bd4  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800a3bdb  mov     rax, [rcx+298h]
0x1800a3be2  mov     cl, [rax+38h]
0x1800a3be5  cmp     cs:?s_UseRangeDumpFormatForFullMemDumpFiles@EngineConfiguration@@0_NA, r13b; bool EngineConfiguration::s_UseRangeDumpFormatForFullMemDumpFiles
0x1800a3bec  jz      short loc_1800A3BF7
0x1800a3bee  neg     cl
0x1800a3bf0  sbb     ecx, ecx
0x1800a3bf2  and     ecx, 0FFFFFFFCh
0x1800a3bf5  jmp     short loc_1800A3BFD
0x1800a3bf7  neg     cl
0x1800a3bf9  sbb     ecx, ecx
0x1800a3bfb  neg     ecx
0x1800a3bfd  add     ecx, 0Ch
0x1800a3c00  jmp     loc_1800A3CB3
0x1800a3c05  mov     rax, [rcx+298h]
0x1800a3c0c  mov     cl, [rax+38h]
0x1800a3c0f  cmp     cs:?s_UseRangeDumpFormatForKernelMemDumpFiles@EngineConfiguration@@0_NA, r13b; bool EngineConfiguration::s_UseRangeDumpFormatForKernelMemDumpFiles
0x1800a3c16  jz      short loc_1800A3C21
0x1800a3c18  neg     cl
0x1800a3c1a  sbb     ecx, ecx
0x1800a3c1c  jmp     loc_1800A3B91
0x1800a3c21  neg     cl
0x1800a3c23  sbb     ecx, ecx
0x1800a3c25  neg     ecx
0x1800a3c27  add     ecx, 6
0x1800a3c2a  jmp     loc_1800A3CB3
0x1800a3c2f  mov     rax, [rcx+298h]
0x1800a3c36  mov     cl, [rax+38h]
0x1800a3c39  neg     cl
0x1800a3c3b  sbb     ecx, ecx
0x1800a3c3d  neg     ecx
0x1800a3c3f  add     ecx, 4
0x1800a3c42  jmp     short loc_1800A3CB3
0x1800a3c44  add     eax, 0FFFFFFFEh
0x1800a3c47  cmp     eax, 1
0x1800a3c4a  jbe     short loc_1800A3C58
0x1800a3c4c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a3c51  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800a3c58  mov     edx, [r15]
0x1800a3c5b  sub     edx, 400h
0x1800a3c61  jz      short loc_1800A3C92
0x1800a3c63  cmp     edx, 1
0x1800a3c66  jnz     loc_1800A3AF0
0x1800a3c6c  lea     r14, [r15+4]
0x1800a3c70  test    dword ptr [r14], 0FFFFFFFh
0x1800a3c77  jnz     loc_1800A3AF0
0x1800a3c7d  mov     rax, [rcx+298h]
0x1800a3c84  mov     cl, [rax+38h]
0x1800a3c87  neg     cl
0x1800a3c89  sbb     ecx, ecx
0x1800a3c8b  neg     ecx
0x1800a3c8d  add     ecx, 0Eh
0x1800a3c90  jmp     short loc_1800A3CB3
0x1800a3c92  lea     r14, [r15+4]
0x1800a3c96  test    dword ptr [r14], 3F80000h
0x1800a3c9d  jnz     loc_1800A3AF0
0x1800a3ca3  test    byte ptr [r14], 1
0x1800a3ca7  mov     ecx, 11h
0x1800a3cac  jnz     short loc_1800A3CB3
0x1800a3cae  mov     ecx, 10h; unsigned int
0x1800a3cb3  call    ?NewFileTargetInfo@@YAPEAVTargetInfo@@K@Z; NewFileTargetInfo(ulong)
0x1800a3cb8  mov     r12, rax
0x1800a3cbb  test    rax, rax
0x1800a3cbe  jnz     short loc_1800A3CD6
0x1800a3cc0  lea     rcx, aUnableToAlloca_16; "Unable to allocate dump write target\n"
0x1800a3cc7  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800a3ccc  mov     eax, 8007000Eh
0x1800a3cd1  jmp     loc_1800A4012
0x1800a3cd6  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x1800a3cdd  mov     eax, [rcx+2A0h]
0x1800a3ce3  mov     [rsp+6F0h+var_6B0], eax
0x1800a3ce7  xor     r8d, r8d; int
0x1800a3cea  mov     edx, [rcx+5Ch]; unsigned int
0x1800a3ced  call    ?SetEffMachine@TargetInfo@@QEAAXKH@Z; TargetInfo::SetEffMachine(ulong,int)
0x1800a3cf2  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; this
0x1800a3cf9  call    ?FlushRegContext@TargetInfo@@QEAAXXZ; TargetInfo::FlushRegContext(void)
0x1800a3cfe  test    [r14], esi
0x1800a3d01  jz      loc_1800A3DA2
0x1800a3d07  test    rbx, rbx
0x1800a3d0a  jz      short loc_1800A3D16
0x1800a3d0c  mov     edi, 80070057h
0x1800a3d11  jmp     loc_1800A3FE2
0x1800a3d16  lea     rdx, [rbp+5F0h+FileName]; unsigned __int16 *
0x1800a3d1d  mov     esi, 208h
0x1800a3d22  mov     ecx, esi; unsigned int
0x1800a3d24  call    ?DbgGetTempPathW@@YAKKPEAG@Z; DbgGetTempPathW(ulong,ushort *)
0x1800a3d29  test    eax, eax
0x1800a3d2b  jnz     short loc_1800A3D47
0x1800a3d2d  mov     r9d, esi
0x1800a3d30  or      r8d, 0FFFFFFFFh
0x1800a3d34  lea     rdx, asc_1806158FC; ".\\"
0x1800a3d3b  lea     rcx, [rbp+5F0h+FileName]; void *
0x1800a3d42  call    CopyNStringW
0x1800a3d47  mov     rcx, rdi; unsigned __int16 *
0x1800a3d4a  call    ?PathTail@@YAPEBGPEBG@Z; PathTail(ushort const *)
0x1800a3d4f  mov     rdx, rax
0x1800a3d52  mov     r9d, esi
0x1800a3d55  lea     rcx, [rbp+5F0h+FileName]
0x1800a3d5c  call    CatNStringW
0x1800a3d61  mov     r9d, esi
0x1800a3d64  lea     rdx, aDmp; ".dmp"
0x1800a3d6b  lea     rcx, [rbp+5F0h+FileName]
0x1800a3d72  call    CatNStringW
0x1800a3d77  lea     rsi, [rbp+5F0h+FileName]
0x1800a3d7e  btr     dword ptr [r14], 1Fh
0x1800a3d83  call    ?IsSecureMode@@YA_NXZ; IsSecureMode(void)
0x1800a3d88  test    al, al
0x1800a3d8a  jz      short loc_1800A3DC7
0x1800a3d8c  lea     rcx, aSecureDumpWrit; "SECURE: Dump writing disallowed\n"
0x1800a3d93  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800a3d98  mov     eax, 80070005h
0x1800a3d9d  jmp     loc_1800A4012
0x1800a3da2  lea     rsi, aHandleonly; "<HandleOnly>"
0x1800a3da9  test    rdi, rdi
0x1800a3dac  cmovnz  rsi, rdi
0x1800a3db0  test    rbx, rbx
0x1800a3db3  jz      short loc_1800A3D83
0x1800a3db5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3db9  jz      loc_1800A3D0C
0x1800a3dbf  mov     r13, rbx
0x1800a3dc2  jmp     loc_1800A3E72
0x1800a3dc7  mov     eax, [r14]
0x1800a3dca  sar     eax, 1Fh
0x1800a3dcd  add     eax, 2
0x1800a3dd0  mov     [rsp+30h], r13; hTemplateFile
0x1800a3dd5  mov     [rsp+6F0h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1800a3ddd  mov     [rsp+6F0h+dwCreationDisposition], eax; dwCreationDisposition
0x1800a3de1  xor     r9d, r9d; lpSecurityAttributes
0x1800a3de4  xor     r8d, r8d; dwShareMode
0x1800a3de7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a3dec  mov     rcx, rsi; lpFileName
0x1800a3def  call    cs:__imp_CreateFileW
0x1800a3df6  nop     dword ptr [rax+rax+00h]
0x1800a3dfb  mov     r13, rax
0x1800a3dfe  lea     rcx, [rax+1]
0x1800a3e02  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800a3e09  jnz     short loc_1800A3E72
0x1800a3e0b  call    cs:__imp_GetLastError
0x1800a3e12  nop     dword ptr [rax+rax+00h]
0x1800a3e17  test    eax, eax
0x1800a3e19  jnz     short loc_1800A3E22
0x1800a3e1b  mov     edi, 80004005h
0x1800a3e20  jmp     short loc_1800A3E3D
0x1800a3e22  call    cs:__imp_GetLastError
0x1800a3e29  nop     dword ptr [rax+rax+00h]
0x1800a3e2e  mov     edi, eax
0x1800a3e30  test    eax, eax
0x1800a3e32  jle     short loc_1800A3E3D
0x1800a3e34  movzx   edi, ax
0x1800a3e37  or      edi, 80070000h
0x1800a3e3d  xor     edx, edx; Arguments
0x1800a3e3f  mov     ecx, edi; dwMessageId
0x1800a3e41  call    ?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z; FormatAnyStatus(long,void *,int *,ushort * *)
0x1800a3e46  mov     rbx, rax
0x1800a3e49  mov     ecx, edi; int
0x1800a3e4b  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800a3e50  mov     r9, rbx
0x1800a3e53  mov     r8, rax
0x1800a3e56  mov     rdx, rsi
0x1800a3e59  lea     rcx, aUnableToCreate_5; "Unable to create file '%ws' - %s\n    "...
0x1800a3e60  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800a3e65  test    edi, edi
0x1800a3e67  jnz     loc_1800A3FE2
0x1800a3e6d  mov     rbx, [rsp+6F0h+var_6A8]
0x1800a3e72  mov     rdx, rsi
0x1800a3e75  lea     rcx, aCreatingWs; "Creating %ws - "
0x1800a3e7c  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800a3e81  mov     rax, [r12]
0x1800a3e85  mov     r8, r15
0x1800a3e88  mov     rdx, r13
0x1800a3e8b  mov     rcx, r12
0x1800a3e8e  mov     rax, [rax+620h]
0x1800a3e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e9a  mov     edi, eax
0x1800a3e9c  test    eax, eax
0x1800a3e9e  jnz     short loc_1800A3ED2
0x1800a3ea0  lea     rcx, aDumpSuccessful; "Dump successfully written\n"
0x1800a3ea7  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800a3eac  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800a3eb3  cmp     dword ptr [rcx+5Ch], 1C4h
0x1800a3eba  jnz     short loc_1800A3ED2
0x1800a3ebc  mov     rcx, [rcx+298h]
0x1800a3ec3  mov     rdx, [rcx]
0x1800a3ec6  mov     rax, [rdx+80h]
0x1800a3ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ed2  test    rbx, rbx
0x1800a3ed5  jnz     short loc_1800A3EFE
0x1800a3ed7  mov     rcx, r13; hObject
0x1800a3eda  call    cs:__imp_CloseHandle
0x1800a3ee1  nop     dword ptr [rax+rax+00h]
0x1800a3ee6  test    edi, edi
0x1800a3ee8  jz      short loc_1800A3F06
0x1800a3eea  mov     rcx, rsi; lpFileName
0x1800a3eed  call    cs:__imp_DeleteFileW
  ... truncated ...
```
