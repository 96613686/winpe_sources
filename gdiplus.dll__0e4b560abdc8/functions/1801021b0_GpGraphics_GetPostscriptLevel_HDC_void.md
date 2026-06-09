# GpGraphics::GetPostscriptLevel(HDC__ *,void *)

- ea: `0x1801021b0`
- end: `0x180102570`
- name: `?GetPostscriptLevel@GpGraphics@@KAHPEAUHDC__@@PEAX@Z`
- size: `960`
- prototype: `__int64 __fastcall(HDC hdc, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18006ecbc`

## callees

- `0x1800e9380`
- `0x1800ea0ec`
- `0x1801021b0`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180102354`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180102354`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18010232e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18010232e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801021ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801021ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801022e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180102535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801022e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180102535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102522`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102522`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801023ed`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801023ed`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1801023c7`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1801023c7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801024f5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801024f5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18010244e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18010244e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180102426`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180102426`
- `GDI32!ExtEscape` at `0x18010225c`
- `GDI32!ExtEscape` at `0x18010228d`
- `GDI32!ExtEscape` at `0x1801022ba`
- `GDI32!ExtEscape` at `0x18010225c`
- `GDI32!ExtEscape` at `0x18010228d`
- `GDI32!ExtEscape` at `0x1801022ba`

## pseudocode

```c
__int64 __fastcall GpGraphics::GetPostscriptLevel(HDC hdc, void *a2)
{
  unsigned int v4; // ebx
  HMODULE Library; // rax
  int (*ProcAddress)(void *, char *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *); // rax
  HANDLE FileA; // rax
  void *v9; // rbx
  DWORD FileSize; // r15d
  HANDLE FileMappingA; // rax
  void *v12; // r14
  char *v13; // rsi
  char *v14; // rdx
  char *v15; // r9
  char v16; // r8
  __int64 v17; // rcx
  CHAR OutData[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD FileSizeHigh; // [rsp+44h] [rbp-BCh] BYREF
  CHAR InData[4]; // [rsp+48h] [rbp-B8h] BYREF
  CHAR v21[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  CHAR v22[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v23[3]; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v24[32]; // [rsp+60h] [rbp-A0h] BYREF
  LPCSTR lpFileName; // [rsp+80h] [rbp-80h]

  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  *(_DWORD *)v22 = 2;
  *(_DWORD *)OutData = 0;
  if ( Globals::hCachedPrinter && Globals::hCachedPrinter == a2 )
  {
    v4 = Globals::CachedPSLevel;
LABEL_10:
    LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
    return v4;
  }
  if ( Globals::OsVer.dwMajorVersion >= 5 )
  {
    *(_DWORD *)InData = 4117;
    if ( ExtEscape(hdc, 8, 4, InData, 0, 0) )
    {
      *(_DWORD *)v21 = 0;
      if ( ExtEscape(hdc, 4117, 4, v21, 0, 0) > 0 && ExtEscape(hdc, 4121, 4, v22, 4, OutData) > 0 )
      {
        v4 = *(_DWORD *)OutData;
        Globals::CachedPSLevel = *(_DWORD *)OutData;
LABEL_9:
        Globals::hCachedPrinter = a2;
        goto LABEL_10;
      }
    }
  }
  if ( a2 )
  {
    memset_0(v24, 0, 0x400u);
    v23[0] = 0;
    if ( Globals::WinspoolHandle )
    {
      ProcAddress = Globals::GetPrinterDriverFunction;
    }
    else
    {
      Library = LoadLibraryExA("winspool.drv", 0, 0);
      Globals::WinspoolHandle = Library;
      if ( !Library )
        goto LABEL_38;
      ProcAddress = (int (*)(void *, char *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *))GetProcAddress(Library, "GetPrinterDriverA");
      Globals::GetPrinterDriverFunction = ProcAddress;
    }
    if ( ProcAddress )
    {
      if ( ((unsigned int (__fastcall *)(void *, _QWORD, __int64, _BYTE *, int, int *))ProcAddress)(
             a2,
             0,
             2,
             v24,
             1024,
             v23) )
      {
        FileA = CreateFileA(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        v9 = FileA;
        if ( FileA != (HANDLE)-1LL )
        {
          FileSizeHigh = 0;
          FileSize = GetFileSize(FileA, &FileSizeHigh);
          if ( FileSize != -1 && !FileSizeHigh )
          {
            FileMappingA = CreateFileMappingA(v9, 0, 2u, 0, 0, 0);
            v12 = FileMappingA;
            if ( FileMappingA )
            {
              v13 = (char *)MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
              CloseHandle(v12);
              if ( v13 )
              {
                v14 = v13;
                v15 = &v13[FileSize - 16];
                *(_DWORD *)OutData = -1;
                while ( v14 < v15 )
                {
                  v16 = *v14;
                  if ( *v14 == 76 )
                  {
                    v17 = *(_QWORD *)v14 - 0x65676175676E614CLL;
                    if ( *(_QWORD *)v14 == 0x65676175676E614CLL )
                    {
                      v17 = *((unsigned int *)v14 + 2) - 1702257996LL;
                      if ( *((_DWORD *)v14 + 2) == 1702257996 )
                        v17 = (unsigned __int8)v14[12] - 108LL;
                    }
                    if ( !v17 )
                    {
                      while ( (unsigned __int8)(v16 - 48) > 9u && v14 < v15 )
                        v16 = *++v14;
                      if ( (unsigned __int8)(v16 - 48) <= 9u )
                        *(_DWORD *)OutData = v16 - 48;
                      break;
                    }
                  }
                  ++v14;
                }
                UnmapViewOfFile(v13);
                CloseHandle(v9);
                v4 = *(_DWORD *)OutData;
                Globals::CachedPSLevel = *(_DWORD *)OutData;
                goto LABEL_9;
              }
            }
          }
          CloseHandle(v9);
        }
      }
    }
  }
LABEL_38:
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1801021b0  mov     [rsp-8+arg_10], rbx
0x1801021b5  mov     [rsp-8+arg_18], rsi
0x1801021ba  push    rbp
0x1801021bb  push    rdi
0x1801021bc  push    r12
0x1801021be  push    r14
0x1801021c0  push    r15
0x1801021c2  lea     rbp, [rsp-370h]
0x1801021ca  sub     rsp, 470h
0x1801021d1  mov     rax, cs:__security_cookie
0x1801021d8  xor     rax, rsp
0x1801021db  mov     [rbp+390h+var_30], rax
0x1801021e2  mov     rbx, rcx
0x1801021e5  mov     rdi, rdx
0x1801021e8  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801021ef  call    cs:__imp_EnterCriticalSection
0x1801021f6  nop     dword ptr [rax+rax+00h]
0x1801021fb  mov     rax, cs:?hCachedPrinter@Globals@@3PEAXEA; void * Globals::hCachedPrinter
0x180102202  xor     r12d, r12d
0x180102205  mov     dword ptr [rsp+490h+var_440], 2
0x18010220d  mov     dword ptr [rsp+490h+OutData], r12d
0x180102212  test    rax, rax
0x180102215  jz      short loc_180102227
0x180102217  cmp     rax, rdi
0x18010221a  jnz     short loc_180102227
0x18010221c  mov     ebx, cs:?CachedPSLevel@Globals@@3HA; int Globals::CachedPSLevel
0x180102222  jmp     loc_1801022DD
0x180102227  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, 5; _OSVERSIONINFOA Globals::OsVer ...
0x18010222e  mov     esi, 4
0x180102233  jb      loc_1801022F7
0x180102239  mov     r14d, 1015h
0x18010223f  mov     [rsp+490h+lpOutData], r12; lpOutData
0x180102244  lea     r9, [rsp+490h+InData]; lpInData
0x180102249  mov     dword ptr [rsp+490h+InData], r14d
0x18010224e  mov     r8d, esi; cjInput
0x180102251  mov     [rsp+490h+cjOutput], r12d; cjOutput
0x180102256  lea     edx, [rsi+4]; iEscape
0x180102259  mov     rcx, rbx; hdc
0x18010225c  call    cs:__imp_ExtEscape
0x180102263  nop     dword ptr [rax+rax+00h]
0x180102268  test    eax, eax
0x18010226a  jz      loc_1801022F7
0x180102270  mov     [rsp+490h+lpOutData], r12; lpOutData
0x180102275  lea     r9, [rsp+490h+var_444]; lpInData
0x18010227a  mov     r8d, esi; cjInput
0x18010227d  mov     [rsp+490h+cjOutput], r12d; cjOutput
0x180102282  mov     edx, r14d; iEscape
0x180102285  mov     dword ptr [rsp+490h+var_444], r12d
0x18010228a  mov     rcx, rbx; hdc
0x18010228d  call    cs:__imp_ExtEscape
0x180102294  nop     dword ptr [rax+rax+00h]
0x180102299  test    eax, eax
0x18010229b  jle     short loc_1801022F7
0x18010229d  lea     rax, [rsp+490h+OutData]
0x1801022a2  mov     r8d, esi; cjInput
0x1801022a5  mov     [rsp+490h+lpOutData], rax; lpOutData
0x1801022aa  lea     r9, [rsp+490h+var_440]; lpInData
0x1801022af  lea     edx, [r14+4]; iEscape
0x1801022b3  mov     [rsp+490h+cjOutput], esi; cjOutput
0x1801022b7  mov     rcx, rbx; hdc
0x1801022ba  call    cs:__imp_ExtEscape
0x1801022c1  nop     dword ptr [rax+rax+00h]
0x1801022c6  test    eax, eax
0x1801022c8  jle     short loc_1801022F7
0x1801022ca  mov     eax, dword ptr [rsp+490h+OutData]
0x1801022ce  mov     ebx, eax
0x1801022d0  mov     cs:?CachedPSLevel@Globals@@3HA, eax; int Globals::CachedPSLevel
0x1801022d6  mov     cs:?hCachedPrinter@Globals@@3PEAXEA, rdi; void * Globals::hCachedPrinter
0x1801022dd  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801022e4  call    cs:__imp_LeaveCriticalSection
0x1801022eb  nop     dword ptr [rax+rax+00h]
0x1801022f0  mov     eax, ebx
0x1801022f2  jmp     loc_180102544
0x1801022f7  test    rdi, rdi
0x1801022fa  jz      loc_18010252E
0x180102300  mov     ebx, 400h
0x180102305  lea     rcx, [rsp+490h+var_430]; void *
0x18010230a  mov     r8d, ebx; Size
0x18010230d  xor     edx, edx; Val
0x18010230f  call    memset_0
0x180102314  cmp     cs:?WinspoolHandle@Globals@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * Globals::WinspoolHandle
0x18010231b  mov     [rsp+490h+var_43C], r12d
0x180102320  jnz     short loc_180102369
0x180102322  xor     r8d, r8d; dwFlags
0x180102325  lea     rcx, aWinspoolDrv; "winspool.drv"
0x18010232c  xor     edx, edx; hFile
0x18010232e  call    cs:__imp_LoadLibraryExA
0x180102335  nop     dword ptr [rax+rax+00h]
0x18010233a  mov     cs:?WinspoolHandle@Globals@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Globals::WinspoolHandle
0x180102341  test    rax, rax
0x180102344  jz      loc_18010252E
0x18010234a  lea     rdx, aGetprinterdriv; "GetPrinterDriverA"
0x180102351  mov     rcx, rax; hModule
0x180102354  call    cs:__imp_GetProcAddress
0x18010235b  nop     dword ptr [rax+rax+00h]
0x180102360  mov     cs:?GetPrinterDriverFunction@Globals@@3P6AHPEAXPEADKPEAEKPEAK@ZEA, rax; int (*Globals::GetPrinterDriverFunction)(void *,char *,ulong,uchar *,ulong,ulong *)
0x180102367  jmp     short loc_180102370
0x180102369  mov     rax, cs:?GetPrinterDriverFunction@Globals@@3P6AHPEAXPEADKPEAEKPEAK@ZEA; int (*Globals::GetPrinterDriverFunction)(void *,char *,ulong,uchar *,ulong,ulong *)
0x180102370  test    rax, rax
0x180102373  jz      loc_18010252E
0x180102379  xor     edx, edx
0x18010237b  lea     rcx, [rsp+490h+var_43C]
0x180102380  mov     [rsp+490h+lpOutData], rcx
0x180102385  lea     r9, [rsp+490h+var_430]
0x18010238a  mov     rcx, rdi
0x18010238d  mov     [rsp+490h+cjOutput], ebx
0x180102391  lea     r8d, [rdx+2]
0x180102395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010239a  test    eax, eax
0x18010239c  jz      loc_18010252E
0x1801023a2  mov     rcx, [rbp+390h+lpFileName]; lpFileName
0x1801023a6  xor     r9d, r9d; lpSecurityAttributes
0x1801023a9  mov     [rsp+490h+hTemplateFile], r12; hTemplateFile
0x1801023ae  mov     edx, 80000000h; dwDesiredAccess
0x1801023b3  mov     dword ptr [rsp+490h+lpOutData], 80h; dwFlagsAndAttributes
0x1801023bb  mov     [rsp+490h+cjOutput], 3; dwCreationDisposition
0x1801023c3  lea     r8d, [r9+1]; dwShareMode
0x1801023c7  call    cs:__imp_CreateFileA
0x1801023ce  nop     dword ptr [rax+rax+00h]
0x1801023d3  mov     rbx, rax
0x1801023d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801023da  jz      loc_18010252E
0x1801023e0  lea     rdx, [rsp+490h+FileSizeHigh]; lpFileSizeHigh
0x1801023e5  mov     [rsp+490h+FileSizeHigh], r12d
0x1801023ea  mov     rcx, rax; hFile
0x1801023ed  call    cs:__imp_GetFileSize
0x1801023f4  nop     dword ptr [rax+rax+00h]
0x1801023f9  mov     r15d, eax
0x1801023fc  cmp     eax, 0FFFFFFFFh
0x1801023ff  jz      loc_18010251F
0x180102405  cmp     [rsp+490h+FileSizeHigh], r12d
0x18010240a  jnz     loc_18010251F
0x180102410  xor     r9d, r9d; dwMaximumSizeHigh
0x180102413  mov     [rsp+490h+lpOutData], r12; lpName
0x180102418  xor     edx, edx; lpFileMappingAttributes
0x18010241a  mov     [rsp+490h+cjOutput], r12d; dwMaximumSizeLow
0x18010241f  mov     rcx, rbx; hFile
0x180102422  lea     r8d, [r9+2]; flProtect
0x180102426  call    cs:__imp_CreateFileMappingA
0x18010242d  nop     dword ptr [rax+rax+00h]
0x180102432  mov     r14, rax
0x180102435  test    rax, rax
0x180102438  jz      loc_18010251F
0x18010243e  xor     r9d, r9d; dwFileOffsetLow
0x180102441  mov     qword ptr [rsp+490h+cjOutput], r12; dwNumberOfBytesToMap
0x180102446  xor     r8d, r8d; dwFileOffsetHigh
0x180102449  mov     edx, esi; dwDesiredAccess
0x18010244b  mov     rcx, rax; hFileMappingObject
0x18010244e  call    cs:__imp_MapViewOfFile
0x180102455  nop     dword ptr [rax+rax+00h]
0x18010245a  mov     rcx, r14; hObject
0x18010245d  mov     rsi, rax
0x180102460  call    cs:__imp_CloseHandle
0x180102467  nop     dword ptr [rax+rax+00h]
0x18010246c  test    rsi, rsi
0x18010246f  jz      loc_18010251F
0x180102475  lea     r9d, [r15-10h]
0x180102479  mov     rdx, rsi
0x18010247c  add     r9, rsi
0x18010247f  or      dword ptr [rsp+490h+OutData], 0FFFFFFFFh
0x180102484  cmp     rdx, r9
0x180102487  jnb     short loc_1801024F2
0x180102489  mov     r8b, [rdx]
0x18010248c  cmp     r8b, 4Ch ; 'L'
0x180102490  jnz     short loc_1801024C5
0x180102492  mov     rcx, [rdx]
0x180102495  mov     rax, 65676175676E614Ch
0x18010249f  sub     rcx, rax
0x1801024a2  jnz     short loc_1801024C0
0x1801024a4  mov     ecx, [rdx+8]
0x1801024a7  mov     eax, 6576654Ch
0x1801024ac  sub     rcx, rax
0x1801024af  jnz     short loc_1801024C0
0x1801024b1  movzx   ecx, byte ptr [rdx+0Ch]
0x1801024b5  mov     eax, 6Ch ; 'l'
0x1801024ba  movzx   eax, al
0x1801024bd  sub     rcx, rax
0x1801024c0  test    rcx, rcx
0x1801024c3  jz      short loc_1801024CA
0x1801024c5  inc     rdx
0x1801024c8  jmp     short loc_180102484
0x1801024ca  lea     eax, [r8-30h]
0x1801024ce  cmp     al, 9
0x1801024d0  jbe     short loc_1801024DF
0x1801024d2  cmp     rdx, r9
0x1801024d5  jnb     short loc_1801024DF
0x1801024d7  inc     rdx
0x1801024da  mov     r8b, [rdx]
0x1801024dd  jmp     short loc_1801024CA
0x1801024df  lea     eax, [r8-30h]
0x1801024e3  cmp     al, 9
0x1801024e5  ja      short loc_1801024F2
0x1801024e7  movsx   eax, r8b
0x1801024eb  sub     eax, 30h ; '0'
0x1801024ee  mov     dword ptr [rsp+490h+OutData], eax
0x1801024f2  mov     rcx, rsi; lpBaseAddress
0x1801024f5  call    cs:__imp_UnmapViewOfFile
0x1801024fc  nop     dword ptr [rax+rax+00h]
0x180102501  mov     rcx, rbx; hObject
0x180102504  call    cs:__imp_CloseHandle
0x18010250b  nop     dword ptr [rax+rax+00h]
0x180102510  mov     ebx, dword ptr [rsp+490h+OutData]
0x180102514  mov     cs:?CachedPSLevel@Globals@@3HA, ebx; int Globals::CachedPSLevel
0x18010251a  jmp     loc_1801022D6
0x18010251f  mov     rcx, rbx; hObject
0x180102522  call    cs:__imp_CloseHandle
0x180102529  nop     dword ptr [rax+rax+00h]
0x18010252e  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180102535  call    cs:__imp_LeaveCriticalSection
0x18010253c  nop     dword ptr [rax+rax+00h]
0x180102541  or      eax, 0FFFFFFFFh
0x180102544  mov     rcx, [rbp+390h+var_30]
0x18010254b  xor     rcx, rsp; StackCookie
0x18010254e  call    __security_check_cookie
0x180102553  lea     r11, [rsp+490h+var_20]
0x18010255b  mov     rbx, [r11+40h]
0x18010255f  mov     rsi, [r11+48h]
0x180102563  mov     rsp, r11
0x180102566  pop     r15
0x180102568  pop     r14
0x18010256a  pop     r12
0x18010256c  pop     rdi
0x18010256d  pop     rbp
0x18010256e  retn
```
