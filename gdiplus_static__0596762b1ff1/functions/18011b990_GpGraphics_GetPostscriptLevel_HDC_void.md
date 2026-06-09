# GpGraphics::GetPostscriptLevel(HDC__ *,void *)

- ea: `0x18011b990`
- end: `0x18011bd53`
- name: `?GetPostscriptLevel@GpGraphics@@KAHPEAUHDC__@@PEAX@Z`
- size: `963`
- prototype: `__int64 __fastcall(HDC hdc, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18006651c`

## callees

- `0x180105d40`
- `0x18010673c`
- `0x18011b990`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18011bb0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18011bb0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18011bb33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18011bb33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011b9cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011b9cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bd18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bd18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bc40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bd05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bc40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bd05`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18011bbcc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18011bbcc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18011bba6`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18011bba6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18011bcd8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18011bcd8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18011bc2e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18011bc2e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18011bc05`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18011bc05`
- `GDI32!ExtEscape` at `0x18011ba3c`
- `GDI32!ExtEscape` at `0x18011ba6c`
- `GDI32!ExtEscape` at `0x18011ba99`
- `GDI32!ExtEscape` at `0x18011ba3c`
- `GDI32!ExtEscape` at `0x18011ba6c`
- `GDI32!ExtEscape` at `0x18011ba99`

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
  void *v12; // rsi
  char *v13; // r14
  char *v14; // r9
  char *v15; // rdx
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
                *(_DWORD *)OutData = -1;
                v14 = &v13[FileSize - 16];
                v15 = v13;
                v16 = 76;
                while ( v15 < v14 )
                {
                  if ( *v15 == 76 )
                  {
                    v17 = *(_QWORD *)v15 - 0x65676175676E614CLL;
                    if ( *(_QWORD *)v15 == 0x65676175676E614CLL )
                    {
                      v17 = *((unsigned int *)v15 + 2) - 1702257996LL;
                      if ( *((_DWORD *)v15 + 2) == 1702257996 )
                        v17 = (unsigned __int8)v15[12] - 108LL;
                    }
                    if ( !v17 )
                    {
                      while ( (unsigned __int8)(v16 - 48) > 9u && v15 < v14 )
                        v16 = *++v15;
                      if ( (unsigned __int8)(*v15 - 48) <= 9u )
                        *(_DWORD *)OutData = *v15 - 48;
                      break;
                    }
                  }
                  ++v15;
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
0x18011b990  mov     [rsp-8+arg_10], rbx
0x18011b995  mov     [rsp-8+arg_18], rsi
0x18011b99a  push    rbp
0x18011b99b  push    rdi
0x18011b99c  push    r12
0x18011b99e  push    r14
0x18011b9a0  push    r15
0x18011b9a2  lea     rbp, [rsp-370h]
0x18011b9aa  sub     rsp, 470h
0x18011b9b1  mov     rax, cs:__security_cookie
0x18011b9b8  xor     rax, rsp
0x18011b9bb  mov     [rbp+390h+var_30], rax
0x18011b9c2  mov     rbx, rcx
0x18011b9c5  mov     rdi, rdx
0x18011b9c8  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011b9cf  call    cs:__imp_EnterCriticalSection
0x18011b9d6  nop     dword ptr [rax+rax+00h]
0x18011b9db  mov     rax, cs:?hCachedPrinter@Globals@@3PEAXEA; void * Globals::hCachedPrinter
0x18011b9e2  xor     r12d, r12d
0x18011b9e5  mov     dword ptr [rsp+490h+var_440], 2
0x18011b9ed  mov     dword ptr [rsp+490h+OutData], r12d
0x18011b9f2  test    rax, rax
0x18011b9f5  jz      short loc_18011BA07
0x18011b9f7  cmp     rax, rdi
0x18011b9fa  jnz     short loc_18011BA07
0x18011b9fc  mov     ebx, cs:?CachedPSLevel@Globals@@3HA; int Globals::CachedPSLevel
0x18011ba02  jmp     loc_18011BABC
0x18011ba07  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, 5; _OSVERSIONINFOA Globals::OsVer ...
0x18011ba0e  mov     r14d, 4
0x18011ba14  jb      loc_18011BAD6
0x18011ba1a  mov     esi, 1015h
0x18011ba1f  mov     [rsp+490h+lpOutData], r12; lpOutData
0x18011ba24  lea     r9, [rsp+490h+InData]; lpInData
0x18011ba29  mov     dword ptr [rsp+490h+InData], esi
0x18011ba2d  mov     r8d, r14d; cjInput
0x18011ba30  mov     [rsp+490h+cjOutput], r12d; cjOutput
0x18011ba35  lea     edx, [r14+4]; iEscape
0x18011ba39  mov     rcx, rbx; hdc
0x18011ba3c  call    cs:__imp_ExtEscape
0x18011ba43  nop     dword ptr [rax+rax+00h]
0x18011ba48  test    eax, eax
0x18011ba4a  jz      loc_18011BAD6
0x18011ba50  mov     [rsp+490h+lpOutData], r12; lpOutData
0x18011ba55  lea     r9, [rsp+490h+var_444]; lpInData
0x18011ba5a  mov     r8d, r14d; cjInput
0x18011ba5d  mov     [rsp+490h+cjOutput], r12d; cjOutput
0x18011ba62  mov     edx, esi; iEscape
0x18011ba64  mov     dword ptr [rsp+490h+var_444], r12d
0x18011ba69  mov     rcx, rbx; hdc
0x18011ba6c  call    cs:__imp_ExtEscape
0x18011ba73  nop     dword ptr [rax+rax+00h]
0x18011ba78  test    eax, eax
0x18011ba7a  jle     short loc_18011BAD6
0x18011ba7c  lea     rax, [rsp+490h+OutData]
0x18011ba81  mov     r8d, r14d; cjInput
0x18011ba84  mov     [rsp+490h+lpOutData], rax; lpOutData
0x18011ba89  lea     r9, [rsp+490h+var_440]; lpInData
0x18011ba8e  lea     edx, [rsi+4]; iEscape
0x18011ba91  mov     [rsp+490h+cjOutput], r14d; cjOutput
0x18011ba96  mov     rcx, rbx; hdc
0x18011ba99  call    cs:__imp_ExtEscape
0x18011baa0  nop     dword ptr [rax+rax+00h]
0x18011baa5  test    eax, eax
0x18011baa7  jle     short loc_18011BAD6
0x18011baa9  mov     eax, dword ptr [rsp+490h+OutData]
0x18011baad  mov     ebx, eax
0x18011baaf  mov     cs:?CachedPSLevel@Globals@@3HA, eax; int Globals::CachedPSLevel
0x18011bab5  mov     cs:?hCachedPrinter@Globals@@3PEAXEA, rdi; void * Globals::hCachedPrinter
0x18011babc  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011bac3  call    cs:__imp_LeaveCriticalSection
0x18011baca  nop     dword ptr [rax+rax+00h]
0x18011bacf  mov     eax, ebx
0x18011bad1  jmp     loc_18011BD27
0x18011bad6  test    rdi, rdi
0x18011bad9  jz      loc_18011BD11
0x18011badf  mov     ebx, 400h
0x18011bae4  lea     rcx, [rsp+490h+var_430]; void *
0x18011bae9  mov     r8d, ebx; Size
0x18011baec  xor     edx, edx; Val
0x18011baee  call    memset_0
0x18011baf3  cmp     cs:?WinspoolHandle@Globals@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * Globals::WinspoolHandle
0x18011bafa  mov     [rsp+490h+var_43C], r12d
0x18011baff  jnz     short loc_18011BB48
0x18011bb01  xor     r8d, r8d; dwFlags
0x18011bb04  lea     rcx, aWinspoolDrv; "winspool.drv"
0x18011bb0b  xor     edx, edx; hFile
0x18011bb0d  call    cs:__imp_LoadLibraryExA
0x18011bb14  nop     dword ptr [rax+rax+00h]
0x18011bb19  mov     cs:?WinspoolHandle@Globals@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Globals::WinspoolHandle
0x18011bb20  test    rax, rax
0x18011bb23  jz      loc_18011BD11
0x18011bb29  lea     rdx, aGetprinterdriv; "GetPrinterDriverA"
0x18011bb30  mov     rcx, rax; hModule
0x18011bb33  call    cs:__imp_GetProcAddress
0x18011bb3a  nop     dword ptr [rax+rax+00h]
0x18011bb3f  mov     cs:?GetPrinterDriverFunction@Globals@@3P6AHPEAXPEADKPEAEKPEAK@ZEA, rax; int (*Globals::GetPrinterDriverFunction)(void *,char *,ulong,uchar *,ulong,ulong *)
0x18011bb46  jmp     short loc_18011BB4F
0x18011bb48  mov     rax, cs:?GetPrinterDriverFunction@Globals@@3P6AHPEAXPEADKPEAEKPEAK@ZEA; int (*Globals::GetPrinterDriverFunction)(void *,char *,ulong,uchar *,ulong,ulong *)
0x18011bb4f  test    rax, rax
0x18011bb52  jz      loc_18011BD11
0x18011bb58  xor     edx, edx
0x18011bb5a  lea     rcx, [rsp+490h+var_43C]
0x18011bb5f  mov     [rsp+490h+lpOutData], rcx
0x18011bb64  lea     r9, [rsp+490h+var_430]
0x18011bb69  mov     rcx, rdi
0x18011bb6c  mov     [rsp+490h+cjOutput], ebx
0x18011bb70  lea     r8d, [rdx+2]
0x18011bb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bb79  test    eax, eax
0x18011bb7b  jz      loc_18011BD11
0x18011bb81  mov     rcx, [rbp+390h+lpFileName]; lpFileName
0x18011bb85  xor     r9d, r9d; lpSecurityAttributes
0x18011bb88  mov     [rsp+490h+hTemplateFile], r12; hTemplateFile
0x18011bb8d  mov     edx, 80000000h; dwDesiredAccess
0x18011bb92  mov     dword ptr [rsp+490h+lpOutData], 80h; dwFlagsAndAttributes
0x18011bb9a  mov     [rsp+490h+cjOutput], 3; dwCreationDisposition
0x18011bba2  lea     r8d, [r9+1]; dwShareMode
0x18011bba6  call    cs:__imp_CreateFileA
0x18011bbad  nop     dword ptr [rax+rax+00h]
0x18011bbb2  mov     rbx, rax
0x18011bbb5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011bbb9  jz      loc_18011BD11
0x18011bbbf  lea     rdx, [rsp+490h+FileSizeHigh]; lpFileSizeHigh
0x18011bbc4  mov     [rsp+490h+FileSizeHigh], r12d
0x18011bbc9  mov     rcx, rax; hFile
0x18011bbcc  call    cs:__imp_GetFileSize
0x18011bbd3  nop     dword ptr [rax+rax+00h]
0x18011bbd8  mov     r15d, eax
0x18011bbdb  cmp     eax, 0FFFFFFFFh
0x18011bbde  jz      loc_18011BD02
0x18011bbe4  cmp     [rsp+490h+FileSizeHigh], r12d
0x18011bbe9  jnz     loc_18011BD02
0x18011bbef  xor     r9d, r9d; dwMaximumSizeHigh
0x18011bbf2  mov     [rsp+490h+lpOutData], r12; lpName
0x18011bbf7  xor     edx, edx; lpFileMappingAttributes
0x18011bbf9  mov     [rsp+490h+cjOutput], r12d; dwMaximumSizeLow
0x18011bbfe  mov     rcx, rbx; hFile
0x18011bc01  lea     r8d, [r9+2]; flProtect
0x18011bc05  call    cs:__imp_CreateFileMappingA
0x18011bc0c  nop     dword ptr [rax+rax+00h]
0x18011bc11  mov     rsi, rax
0x18011bc14  test    rax, rax
0x18011bc17  jz      loc_18011BD02
0x18011bc1d  xor     r9d, r9d; dwFileOffsetLow
0x18011bc20  mov     qword ptr [rsp+490h+cjOutput], r12; dwNumberOfBytesToMap
0x18011bc25  xor     r8d, r8d; dwFileOffsetHigh
0x18011bc28  mov     edx, r14d; dwDesiredAccess
0x18011bc2b  mov     rcx, rax; hFileMappingObject
0x18011bc2e  call    cs:__imp_MapViewOfFile
0x18011bc35  nop     dword ptr [rax+rax+00h]
0x18011bc3a  mov     rcx, rsi; hObject
0x18011bc3d  mov     r14, rax
0x18011bc40  call    cs:__imp_CloseHandle
0x18011bc47  nop     dword ptr [rax+rax+00h]
0x18011bc4c  test    r14, r14
0x18011bc4f  jz      loc_18011BD02
0x18011bc55  lea     r9d, [r15-10h]
0x18011bc59  mov     dword ptr [rsp+490h+OutData], 0FFFFFFFFh
0x18011bc61  add     r9, r14
0x18011bc64  mov     rdx, r14
0x18011bc67  mov     r8b, 4Ch ; 'L'
0x18011bc6a  cmp     rdx, r9
0x18011bc6d  jnb     short loc_18011BCD5
0x18011bc6f  cmp     [rdx], r8b
0x18011bc72  jnz     short loc_18011BCA7
0x18011bc74  mov     rcx, [rdx]
0x18011bc77  mov     rax, 65676175676E614Ch
0x18011bc81  sub     rcx, rax
0x18011bc84  jnz     short loc_18011BCA2
0x18011bc86  mov     ecx, [rdx+8]
0x18011bc89  mov     eax, 6576654Ch
0x18011bc8e  sub     rcx, rax
0x18011bc91  jnz     short loc_18011BCA2
0x18011bc93  movzx   ecx, byte ptr [rdx+0Ch]
0x18011bc97  mov     eax, 6Ch ; 'l'
0x18011bc9c  movzx   eax, al
0x18011bc9f  sub     rcx, rax
0x18011bca2  test    rcx, rcx
0x18011bca5  jz      short loc_18011BCAC
0x18011bca7  inc     rdx
0x18011bcaa  jmp     short loc_18011BC6A
0x18011bcac  sub     r8b, 30h ; '0'
0x18011bcb0  cmp     r8b, 9
0x18011bcb4  jbe     short loc_18011BCC3
0x18011bcb6  cmp     rdx, r9
0x18011bcb9  jnb     short loc_18011BCC3
0x18011bcbb  inc     rdx
0x18011bcbe  mov     r8b, [rdx]
0x18011bcc1  jmp     short loc_18011BCAC
0x18011bcc3  mov     al, [rdx]
0x18011bcc5  sub     al, 30h ; '0'
0x18011bcc7  cmp     al, 9
0x18011bcc9  ja      short loc_18011BCD5
0x18011bccb  movsx   eax, byte ptr [rdx]
0x18011bcce  sub     eax, 30h ; '0'
0x18011bcd1  mov     dword ptr [rsp+490h+OutData], eax
0x18011bcd5  mov     rcx, r14; lpBaseAddress
0x18011bcd8  call    cs:__imp_UnmapViewOfFile
0x18011bcdf  nop     dword ptr [rax+rax+00h]
0x18011bce4  mov     rcx, rbx; hObject
0x18011bce7  call    cs:__imp_CloseHandle
0x18011bcee  nop     dword ptr [rax+rax+00h]
0x18011bcf3  mov     ebx, dword ptr [rsp+490h+OutData]
0x18011bcf7  mov     cs:?CachedPSLevel@Globals@@3HA, ebx; int Globals::CachedPSLevel
0x18011bcfd  jmp     loc_18011BAB5
0x18011bd02  mov     rcx, rbx; hObject
0x18011bd05  call    cs:__imp_CloseHandle
0x18011bd0c  nop     dword ptr [rax+rax+00h]
0x18011bd11  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011bd18  call    cs:__imp_LeaveCriticalSection
0x18011bd1f  nop     dword ptr [rax+rax+00h]
0x18011bd24  or      eax, 0FFFFFFFFh
0x18011bd27  mov     rcx, [rbp+390h+var_30]
0x18011bd2e  xor     rcx, rsp; StackCookie
0x18011bd31  call    __security_check_cookie
0x18011bd36  lea     r11, [rsp+490h+var_20]
0x18011bd3e  mov     rbx, [r11+40h]
0x18011bd42  mov     rsi, [r11+48h]
0x18011bd46  mov     rsp, r11
0x18011bd49  pop     r15
0x18011bd4b  pop     r14
0x18011bd4d  pop     r12
0x18011bd4f  pop     rdi
0x18011bd50  pop     rbp
0x18011bd51  retn
```
