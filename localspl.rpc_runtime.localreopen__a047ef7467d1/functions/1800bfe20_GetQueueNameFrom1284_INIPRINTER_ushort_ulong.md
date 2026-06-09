# GetQueueNameFrom1284(_INIPRINTER *,ushort *,ulong)

- ea: `0x1800bfe20`
- end: `0x1800c0035`
- name: `?GetQueueNameFrom1284@@YAHPEAU_INIPRINTER@@PEAGK@Z`
- size: `533`
- prototype: `__int64 __fastcall(struct _INIPRINTER *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800c003c`

## callees

- `0x180011f00`
- `0x180024b64`
- `0x18003e984`
- `0x18004550c`
- `0x1800bfe20`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bff4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bff4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bff33`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bff33`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bff8b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bff8b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bff17`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bff17`
- `SPOOLSS!DllFreeSplMem` at `0x1800bfff8`
- `SPOOLSS!DllFreeSplMem` at `0x1800c0001`
- `SPOOLSS!DllFreeSplMem` at `0x1800c000a`
- `SPOOLSS!DllFreeSplMem` at `0x1800c0013`
- `SPOOLSS!DllFreeSplMem` at `0x1800c001c`
- `SPOOLSS!DllFreeSplMem` at `0x1800bfff8`
- `SPOOLSS!DllFreeSplMem` at `0x1800c0001`
- `SPOOLSS!DllFreeSplMem` at `0x1800c000a`
- `SPOOLSS!DllFreeSplMem` at `0x1800c0013`
- `SPOOLSS!DllFreeSplMem` at `0x1800c001c`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe53`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe6a`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe81`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe98`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfeaf`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe53`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe6a`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe81`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfe98`
- `SPOOLSS!DllAllocSplMem` at `0x1800bfeaf`

## pseudocode

```c
__int64 __fastcall GetQueueNameFrom1284(struct _INIPRINTER *a1, unsigned __int16 *a2, unsigned int a3)
{
  WCHAR *lpWideCharStr; // r15
  const unsigned __int16 *v5; // rbp
  const unsigned __int16 *v6; // rdi
  const unsigned __int16 *v7; // rsi
  unsigned __int8 *v9; // r12
  unsigned int v10; // ebx
  HMODULE Library; // rax
  HMODULE v12; // r14
  FARPROC ProcAddress; // rax
  unsigned int v14; // r9d
  int v15; // eax
  unsigned int v17; // [rsp+A0h] [rbp+18h] BYREF

  v17 = a3;
  *a2 = 0;
  lpWideCharStr = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v9 = (unsigned __int8 *)DllAllocSplMem(1024);
  if ( !v9 )
    goto LABEL_18;
  lpWideCharStr = (WCHAR *)DllAllocSplMem(2048);
  if ( !lpWideCharStr )
    goto LABEL_18;
  v5 = (const unsigned __int16 *)DllAllocSplMem(520);
  if ( !v5 )
    goto LABEL_18;
  v6 = (const unsigned __int16 *)DllAllocSplMem(520);
  if ( !v6 )
    goto LABEL_18;
  v7 = (const unsigned __int16 *)DllAllocSplMem(520);
  if ( !v7 )
    goto LABEL_18;
  v17 = 1024;
  if ( InternalGetPrinterDataFromPort(a1, 0x16000Cu, (unsigned __int16 *)&qword_1800EBF90, v9, 0x400u, &v17) )
    goto LABEL_18;
  v10 = MultiByteToWideChar(3u, 1u, (LPCCH)v9, -1, lpWideCharStr, 1024);
  if ( v10 )
  {
    Library = LoadLibraryExW(L"winspool.drv", 0, 0);
    v10 = 0;
    v12 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, (LPCSTR)0x103);
      if ( ProcAddress )
        LOBYTE(v10) = ((unsigned int (__fastcall *)(WCHAR *, const unsigned __int16 *, __int64, const unsigned __int16 *, int, const unsigned __int16 *, int))ProcAddress)(
                        lpWideCharStr,
                        v5,
                        260,
                        v6,
                        260,
                        v7,
                        260) == 0;
      FreeLibrary(v12);
      if ( v10 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "GetQueueNameFrom1284",
          L"Queue name from 1284: MFG='%ws', MDL='%ws', DES='%ws'",
          v5,
          v6,
          v7);
        if ( *v5 && *v6 )
        {
          v15 = BuildQueueName(v5, v6, a2, v14);
LABEL_15:
          v10 = v15 >= 0;
          goto LABEL_19;
        }
        if ( *v7 )
        {
          v15 = StringCchCopyW(a2, 0x104u, v7);
          goto LABEL_15;
        }
LABEL_18:
        v10 = 0;
      }
    }
  }
LABEL_19:
  DllFreeSplMem(v9);
  DllFreeSplMem(lpWideCharStr);
  DllFreeSplMem(v5);
  DllFreeSplMem(v6);
  DllFreeSplMem(v7);
  return v10;
}

```

## disassembly

```asm
0x1800bfe20  mov     [rsp+arg_10], r8d
0x1800bfe25  push    rbx
0x1800bfe26  push    rbp
0x1800bfe27  push    rsi
0x1800bfe28  push    rdi
0x1800bfe29  push    r12
0x1800bfe2b  push    r13
0x1800bfe2d  push    r14
0x1800bfe2f  push    r15
0x1800bfe31  sub     rsp, 48h
0x1800bfe35  xor     r14d, r14d
0x1800bfe38  mov     rbx, rcx
0x1800bfe3b  mov     ecx, 400h
0x1800bfe40  mov     [rdx], r14w
0x1800bfe44  mov     r15d, r14d
0x1800bfe47  mov     ebp, r14d
0x1800bfe4a  mov     edi, r14d
0x1800bfe4d  mov     esi, r14d
0x1800bfe50  mov     r13, rdx
0x1800bfe53  call    cs:__imp_DllAllocSplMem
0x1800bfe59  mov     r12, rax
0x1800bfe5c  test    rax, rax
0x1800bfe5f  jz      loc_1800BFFF2
0x1800bfe65  mov     ecx, 800h
0x1800bfe6a  call    cs:__imp_DllAllocSplMem
0x1800bfe70  mov     r15, rax
0x1800bfe73  test    rax, rax
0x1800bfe76  jz      loc_1800BFFF2
0x1800bfe7c  mov     ecx, 208h
0x1800bfe81  call    cs:__imp_DllAllocSplMem
0x1800bfe87  mov     rbp, rax
0x1800bfe8a  test    rax, rax
0x1800bfe8d  jz      loc_1800BFFF2
0x1800bfe93  mov     ecx, 208h
0x1800bfe98  call    cs:__imp_DllAllocSplMem
0x1800bfe9e  mov     rdi, rax
0x1800bfea1  test    rax, rax
0x1800bfea4  jz      loc_1800BFFF2
0x1800bfeaa  mov     ecx, 208h
0x1800bfeaf  call    cs:__imp_DllAllocSplMem
0x1800bfeb5  mov     rsi, rax
0x1800bfeb8  test    rax, rax
0x1800bfebb  jz      loc_1800BFFF2
0x1800bfec1  mov     ecx, 400h
0x1800bfec6  lea     rax, [rsp+88h+arg_10]
0x1800bfece  mov     qword ptr [rsp+88h+cchWideChar], rax; unsigned int *
0x1800bfed3  lea     r8, qword_1800EBF90; unsigned __int16 *
0x1800bfeda  mov     dword ptr [rsp+88h+lpWideCharStr], ecx; unsigned int
0x1800bfede  mov     r9, r12; unsigned __int8 *
0x1800bfee1  mov     [rsp+88h+arg_10], ecx
0x1800bfee8  mov     edx, 16000Ch; unsigned int
0x1800bfeed  mov     rcx, rbx; struct _INIPRINTER *
0x1800bfef0  call    ?InternalGetPrinterDataFromPort@@YAKPEAU_INIPRINTER@@KPEAGPEAEKPEAK@Z; InternalGetPrinterDataFromPort(_INIPRINTER *,ulong,ushort *,uchar *,ulong,ulong *)
0x1800bfef5  test    eax, eax
0x1800bfef7  jnz     loc_1800BFFF2
0x1800bfefd  mov     [rsp+88h+cchWideChar], 400h; cchWideChar
0x1800bff05  lea     edx, [rax+1]; dwFlags
0x1800bff08  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800bff0c  mov     [rsp+88h+lpWideCharStr], r15; lpWideCharStr
0x1800bff11  mov     r8, r12; lpMultiByteStr
0x1800bff14  lea     ecx, [rax+3]; CodePage
0x1800bff17  call    cs:__imp_MultiByteToWideChar
0x1800bff1d  mov     ebx, eax
0x1800bff1f  test    eax, eax
0x1800bff21  jz      loc_1800BFFF5
0x1800bff27  xor     r8d, r8d; dwFlags
0x1800bff2a  lea     rcx, aWinspoolDrv; "winspool.drv"
0x1800bff31  xor     edx, edx; hFile
0x1800bff33  call    cs:__imp_LoadLibraryExW
0x1800bff39  xor     ebx, ebx
0x1800bff3b  mov     r14, rax
0x1800bff3e  test    rax, rax
0x1800bff41  jz      loc_1800BFFF5
0x1800bff47  mov     edx, 103h; lpProcName
0x1800bff4c  mov     rcx, rax; hModule
0x1800bff4f  call    cs:__imp_GetProcAddress
0x1800bff55  test    rax, rax
0x1800bff58  jz      short loc_1800BFF88
0x1800bff5a  mov     [rsp+88h+var_58], 104h
0x1800bff62  mov     r9, rdi
0x1800bff65  mov     qword ptr [rsp+88h+cchWideChar], rsi
0x1800bff6a  mov     r8d, 104h
0x1800bff70  mov     rdx, rbp
0x1800bff73  mov     dword ptr [rsp+88h+lpWideCharStr], 104h
0x1800bff7b  mov     rcx, r15
0x1800bff7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff83  test    eax, eax
0x1800bff85  setz    bl
0x1800bff88  mov     rcx, r14; hLibModule
0x1800bff8b  call    cs:__imp_FreeLibrary
0x1800bff91  xor     r14d, r14d
0x1800bff94  test    ebx, ebx
0x1800bff96  jz      short loc_1800BFFF5
0x1800bff98  mov     r9, rdi
0x1800bff9b  mov     [rsp+88h+lpWideCharStr], rsi
0x1800bffa0  mov     r8, rbp
0x1800bffa3  lea     rdx, aQueueNameFrom1; "Queue name from 1284: MFG='%ws', MDL='%"...
0x1800bffaa  lea     rcx, aGetqueuenamefr; "GetQueueNameFrom1284"
0x1800bffb1  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800bffb6  cmp     [rbp+0], r14w
0x1800bffbb  jz      short loc_1800BFFDA
0x1800bffbd  cmp     [rdi], r14w
0x1800bffc1  jz      short loc_1800BFFDA
0x1800bffc3  mov     r8, r13; unsigned __int16 *
0x1800bffc6  mov     rdx, rdi; unsigned __int16 *
0x1800bffc9  mov     rcx, rbp; unsigned __int16 *
0x1800bffcc  call    ?BuildQueueName@@YAJPEBG0PEAGK@Z; BuildQueueName(ushort const *,ushort const *,ushort *,ulong)
0x1800bffd1  mov     ebx, eax
0x1800bffd3  not     ebx
0x1800bffd5  shr     ebx, 1Fh
0x1800bffd8  jmp     short loc_1800BFFF5
0x1800bffda  cmp     [rsi], r14w
0x1800bffde  jz      short loc_1800BFFF2
0x1800bffe0  mov     r8, rsi; unsigned __int16 *
0x1800bffe3  mov     edx, 104h; unsigned __int64
0x1800bffe8  mov     rcx, r13; unsigned __int16 *
0x1800bffeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bfff0  jmp     short loc_1800BFFD1
0x1800bfff2  mov     ebx, r14d
0x1800bfff5  mov     rcx, r12
0x1800bfff8  call    cs:__imp_DllFreeSplMem
0x1800bfffe  mov     rcx, r15
0x1800c0001  call    cs:__imp_DllFreeSplMem
0x1800c0007  mov     rcx, rbp
0x1800c000a  call    cs:__imp_DllFreeSplMem
0x1800c0010  mov     rcx, rdi
0x1800c0013  call    cs:__imp_DllFreeSplMem
0x1800c0019  mov     rcx, rsi
0x1800c001c  call    cs:__imp_DllFreeSplMem
0x1800c0022  mov     eax, ebx
0x1800c0024  add     rsp, 48h
0x1800c0028  pop     r15
0x1800c002a  pop     r14
0x1800c002c  pop     r13
0x1800c002e  pop     r12
0x1800c0030  pop     rdi
0x1800c0031  pop     rsi
0x1800c0032  pop     rbp
0x1800c0033  pop     rbx
0x1800c0034  retn
```
