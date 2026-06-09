# GpGraphics::GetPostscriptLevel(HDC__ *,void *)

- ea: `0x180113c2c`
- end: `0x180113f8a`
- name: `?GetPostscriptLevel@GpGraphics@@KAHPEAUHDC__@@PEAX@Z`
- size: `862`
- prototype: `__int64 __fastcall(HDC hdc, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180007a18`

## callees

- `0x1800fe680`
- `0x1800ff04c`
- `0x180113c2c`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180113d87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180113d87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113da7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113da7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180113c6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180113c6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180113d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180113f56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180113d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180113f56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113e96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113f31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113f49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113e96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113f31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113f49`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180113e34`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180113e34`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180113e14`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180113e14`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180113f28`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180113f28`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180113e8a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180113e8a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180113e67`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180113e67`
- `GDI32!ExtEscape` at `0x180113cd2`
- `GDI32!ExtEscape` at `0x180113cf8`
- `GDI32!ExtEscape` at `0x180113d1f`
- `GDI32!ExtEscape` at `0x180113cd2`
- `GDI32!ExtEscape` at `0x180113cf8`
- `GDI32!ExtEscape` at `0x180113d1f`

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
0x180113c2c  mov     [rsp-8+arg_10], rbx
0x180113c31  mov     [rsp-8+arg_18], rsi
0x180113c36  push    rbp
0x180113c37  push    rdi
0x180113c38  push    r12
0x180113c3a  push    r14
0x180113c3c  push    r15
0x180113c3e  lea     rbp, [rsp-370h]
0x180113c46  sub     rsp, 470h
0x180113c4d  mov     rax, cs:__security_cookie
0x180113c54  xor     rax, rsp
0x180113c57  mov     [rbp+390h+var_30], rax
0x180113c5e  mov     rbx, rcx
0x180113c61  mov     rdi, rdx
0x180113c64  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180113c6b  call    cs:__imp_EnterCriticalSection
0x180113c71  mov     rax, cs:?hCachedPrinter@Globals@@3PEAXEA; void * Globals::hCachedPrinter
0x180113c78  xor     r12d, r12d
0x180113c7b  mov     dword ptr [rsp+490h+var_440], 2
0x180113c83  mov     dword ptr [rsp+490h+OutData], r12d
0x180113c88  test    rax, rax
0x180113c8b  jz      short loc_180113C9D
0x180113c8d  cmp     rax, rdi
0x180113c90  jnz     short loc_180113C9D
0x180113c92  mov     ebx, cs:?CachedPSLevel@Globals@@3HA; int Globals::CachedPSLevel
0x180113c98  jmp     loc_180113D3C
0x180113c9d  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, 5; _OSVERSIONINFOA Globals::OsVer ...
0x180113ca4  mov     r14d, 4
0x180113caa  jb      loc_180113D50
0x180113cb0  mov     esi, 1015h
0x180113cb5  mov     [rsp+490h+lpOutData], r12; lpOutData
0x180113cba  lea     r9, [rsp+490h+InData]; lpInData
0x180113cbf  mov     dword ptr [rsp+490h+InData], esi
0x180113cc3  mov     r8d, r14d; cjInput
0x180113cc6  mov     [rsp+490h+cjOutput], r12d; cjOutput
0x180113ccb  lea     edx, [r14+4]; iEscape
0x180113ccf  mov     rcx, rbx; hdc
0x180113cd2  call    cs:__imp_ExtEscape
0x180113cd8  test    eax, eax
0x180113cda  jz      short loc_180113D50
0x180113cdc  mov     [rsp+490h+lpOutData], r12; lpOutData
0x180113ce1  lea     r9, [rsp+490h+var_444]; lpInData
0x180113ce6  mov     r8d, r14d; cjInput
0x180113ce9  mov     [rsp+490h+cjOutput], r12d; cjOutput
0x180113cee  mov     edx, esi; iEscape
0x180113cf0  mov     dword ptr [rsp+490h+var_444], r12d
0x180113cf5  mov     rcx, rbx; hdc
0x180113cf8  call    cs:__imp_ExtEscape
0x180113cfe  test    eax, eax
0x180113d00  jle     short loc_180113D50
0x180113d02  lea     rax, [rsp+490h+OutData]
0x180113d07  mov     r8d, r14d; cjInput
0x180113d0a  mov     [rsp+490h+lpOutData], rax; lpOutData
0x180113d0f  lea     r9, [rsp+490h+var_440]; lpInData
0x180113d14  lea     edx, [rsi+4]; iEscape
0x180113d17  mov     [rsp+490h+cjOutput], r14d; cjOutput
0x180113d1c  mov     rcx, rbx; hdc
0x180113d1f  call    cs:__imp_ExtEscape
0x180113d25  test    eax, eax
0x180113d27  jle     short loc_180113D50
0x180113d29  mov     eax, dword ptr [rsp+490h+OutData]
0x180113d2d  mov     ebx, eax
0x180113d2f  mov     cs:?CachedPSLevel@Globals@@3HA, eax; int Globals::CachedPSLevel
0x180113d35  mov     cs:?hCachedPrinter@Globals@@3PEAXEA, rdi; void * Globals::hCachedPrinter
0x180113d3c  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180113d43  call    cs:__imp_LeaveCriticalSection
0x180113d49  mov     eax, ebx
0x180113d4b  jmp     loc_180113F5F
0x180113d50  test    rdi, rdi
0x180113d53  jz      loc_180113F4F
0x180113d59  mov     ebx, 400h
0x180113d5e  lea     rcx, [rsp+490h+var_430]; void *
0x180113d63  mov     r8d, ebx; Size
0x180113d66  xor     edx, edx; Val
0x180113d68  call    memset_0
0x180113d6d  cmp     cs:?WinspoolHandle@Globals@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * Globals::WinspoolHandle
0x180113d74  mov     [rsp+490h+var_43C], r12d
0x180113d79  jnz     short loc_180113DB6
0x180113d7b  xor     r8d, r8d; dwFlags
0x180113d7e  lea     rcx, aWinspoolDrv; "winspool.drv"
0x180113d85  xor     edx, edx; hFile
0x180113d87  call    cs:__imp_LoadLibraryExA
0x180113d8d  mov     cs:?WinspoolHandle@Globals@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Globals::WinspoolHandle
0x180113d94  test    rax, rax
0x180113d97  jz      loc_180113F4F
0x180113d9d  lea     rdx, aGetprinterdriv; "GetPrinterDriverA"
0x180113da4  mov     rcx, rax; hModule
0x180113da7  call    cs:__imp_GetProcAddress
0x180113dad  mov     cs:?GetPrinterDriverFunction@Globals@@3P6AHPEAXPEADKPEAEKPEAK@ZEA, rax; int (*Globals::GetPrinterDriverFunction)(void *,char *,ulong,uchar *,ulong,ulong *)
0x180113db4  jmp     short loc_180113DBD
0x180113db6  mov     rax, cs:?GetPrinterDriverFunction@Globals@@3P6AHPEAXPEADKPEAEKPEAK@ZEA; int (*Globals::GetPrinterDriverFunction)(void *,char *,ulong,uchar *,ulong,ulong *)
0x180113dbd  test    rax, rax
0x180113dc0  jz      loc_180113F4F
0x180113dc6  xor     edx, edx
0x180113dc8  lea     rcx, [rsp+490h+var_43C]
0x180113dcd  mov     [rsp+490h+lpOutData], rcx
0x180113dd2  lea     r9, [rsp+490h+var_430]
0x180113dd7  mov     rcx, rdi
0x180113dda  mov     [rsp+490h+cjOutput], ebx
0x180113dde  lea     r8d, [rdx+2]
0x180113de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113de7  test    eax, eax
0x180113de9  jz      loc_180113F4F
0x180113def  mov     rcx, [rbp+390h+lpFileName]; lpFileName
0x180113df3  xor     r9d, r9d; lpSecurityAttributes
0x180113df6  mov     [rsp+490h+hTemplateFile], r12; hTemplateFile
0x180113dfb  mov     edx, 80000000h; dwDesiredAccess
0x180113e00  mov     dword ptr [rsp+490h+lpOutData], 80h; dwFlagsAndAttributes
0x180113e08  mov     [rsp+490h+cjOutput], 3; dwCreationDisposition
0x180113e10  lea     r8d, [r9+1]; dwShareMode
0x180113e14  call    cs:__imp_CreateFileA
0x180113e1a  mov     rbx, rax
0x180113e1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180113e21  jz      loc_180113F4F
0x180113e27  lea     rdx, [rsp+490h+FileSizeHigh]; lpFileSizeHigh
0x180113e2c  mov     [rsp+490h+FileSizeHigh], r12d
0x180113e31  mov     rcx, rax; hFile
0x180113e34  call    cs:__imp_GetFileSize
0x180113e3a  mov     r15d, eax
0x180113e3d  cmp     eax, 0FFFFFFFFh
0x180113e40  jz      loc_180113F46
0x180113e46  cmp     [rsp+490h+FileSizeHigh], r12d
0x180113e4b  jnz     loc_180113F46
0x180113e51  xor     r9d, r9d; dwMaximumSizeHigh
0x180113e54  mov     [rsp+490h+lpOutData], r12; lpName
0x180113e59  xor     edx, edx; lpFileMappingAttributes
0x180113e5b  mov     [rsp+490h+cjOutput], r12d; dwMaximumSizeLow
0x180113e60  mov     rcx, rbx; hFile
0x180113e63  lea     r8d, [r9+2]; flProtect
0x180113e67  call    cs:__imp_CreateFileMappingA
0x180113e6d  mov     rsi, rax
0x180113e70  test    rax, rax
0x180113e73  jz      loc_180113F46
0x180113e79  xor     r9d, r9d; dwFileOffsetLow
0x180113e7c  mov     qword ptr [rsp+490h+cjOutput], r12; dwNumberOfBytesToMap
0x180113e81  xor     r8d, r8d; dwFileOffsetHigh
0x180113e84  mov     edx, r14d; dwDesiredAccess
0x180113e87  mov     rcx, rax; hFileMappingObject
0x180113e8a  call    cs:__imp_MapViewOfFile
0x180113e90  mov     rcx, rsi; hObject
0x180113e93  mov     r14, rax
0x180113e96  call    cs:__imp_CloseHandle
0x180113e9c  test    r14, r14
0x180113e9f  jz      loc_180113F46
0x180113ea5  lea     r9d, [r15-10h]
0x180113ea9  mov     dword ptr [rsp+490h+OutData], 0FFFFFFFFh
0x180113eb1  add     r9, r14
0x180113eb4  mov     rdx, r14
0x180113eb7  mov     r8b, 4Ch ; 'L'
0x180113eba  cmp     rdx, r9
0x180113ebd  jnb     short loc_180113F25
0x180113ebf  cmp     [rdx], r8b
0x180113ec2  jnz     short loc_180113EF7
0x180113ec4  mov     rcx, [rdx]
0x180113ec7  mov     rax, 65676175676E614Ch
0x180113ed1  sub     rcx, rax
0x180113ed4  jnz     short loc_180113EF2
0x180113ed6  mov     ecx, [rdx+8]
0x180113ed9  mov     eax, 6576654Ch
0x180113ede  sub     rcx, rax
0x180113ee1  jnz     short loc_180113EF2
0x180113ee3  movzx   ecx, byte ptr [rdx+0Ch]
0x180113ee7  mov     eax, 6Ch ; 'l'
0x180113eec  movzx   eax, al
0x180113eef  sub     rcx, rax
0x180113ef2  test    rcx, rcx
0x180113ef5  jz      short loc_180113EFC
0x180113ef7  inc     rdx
0x180113efa  jmp     short loc_180113EBA
0x180113efc  sub     r8b, 30h ; '0'
0x180113f00  cmp     r8b, 9
0x180113f04  jbe     short loc_180113F13
0x180113f06  cmp     rdx, r9
0x180113f09  jnb     short loc_180113F13
0x180113f0b  inc     rdx
0x180113f0e  mov     r8b, [rdx]
0x180113f11  jmp     short loc_180113EFC
0x180113f13  mov     al, [rdx]
0x180113f15  sub     al, 30h ; '0'
0x180113f17  cmp     al, 9
0x180113f19  ja      short loc_180113F25
0x180113f1b  movsx   eax, byte ptr [rdx]
0x180113f1e  sub     eax, 30h ; '0'
0x180113f21  mov     dword ptr [rsp+490h+OutData], eax
0x180113f25  mov     rcx, r14; lpBaseAddress
0x180113f28  call    cs:__imp_UnmapViewOfFile
0x180113f2e  mov     rcx, rbx; hObject
0x180113f31  call    cs:__imp_CloseHandle
0x180113f37  mov     ebx, dword ptr [rsp+490h+OutData]
0x180113f3b  mov     cs:?CachedPSLevel@Globals@@3HA, ebx; int Globals::CachedPSLevel
0x180113f41  jmp     loc_180113D35
0x180113f46  mov     rcx, rbx; hObject
0x180113f49  call    cs:__imp_CloseHandle
0x180113f4f  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180113f56  call    cs:__imp_LeaveCriticalSection
0x180113f5c  or      eax, 0FFFFFFFFh
0x180113f5f  mov     rcx, [rbp+390h+var_30]
0x180113f66  xor     rcx, rsp; StackCookie
0x180113f69  call    __security_check_cookie
0x180113f6e  lea     r11, [rsp+490h+var_20]
0x180113f76  mov     rbx, [r11+40h]
0x180113f7a  mov     rsi, [r11+48h]
0x180113f7e  mov     rsp, r11
0x180113f81  pop     r15
0x180113f83  pop     r14
0x180113f85  pop     r12
0x180113f87  pop     rdi
0x180113f88  pop     rbp
0x180113f89  retn
```
