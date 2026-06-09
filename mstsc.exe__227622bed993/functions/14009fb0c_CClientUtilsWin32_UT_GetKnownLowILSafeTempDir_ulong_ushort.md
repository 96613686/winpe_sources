# CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(ulong,ushort *)

- ea: `0x14009fb0c`
- end: `0x14009fe02`
- name: `?UT_GetKnownLowILSafeTempDir@CClientUtilsWin32@@SAJKPEAG@Z`
- size: `758`
- prototype: `static int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140056130`

## callees

- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e210`
- `0x14009fb0c`
- `0x140112010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x14009fd00`
- `KERNEL32!CreateDirectoryW` at `0x14009fd00`
- `KERNEL32!LoadLibraryExW` at `0x14009fb3e`
- `KERNEL32!LoadLibraryExW` at `0x14009fb3e`
- `KERNEL32!FreeLibrary` at `0x14009fde6`
- `KERNEL32!FreeLibrary` at `0x14009fde6`
- `KERNEL32!GetProcAddress` at `0x14009fbd0`
- `KERNEL32!GetProcAddress` at `0x14009fbd0`
- `KERNEL32!GetLastError` at `0x14009fb6b`
- `KERNEL32!GetLastError` at `0x14009fba8`
- `KERNEL32!GetLastError` at `0x14009fbfa`
- `KERNEL32!GetLastError` at `0x14009fd0e`
- `KERNEL32!GetLastError` at `0x14009fb6b`
- `KERNEL32!GetLastError` at `0x14009fba8`
- `KERNEL32!GetLastError` at `0x14009fbfa`
- `KERNEL32!GetLastError` at `0x14009fd0e`
- `ole32!CoTaskMemFree` at `0x14009fdd8`
- `ole32!CoTaskMemFree` at `0x14009fdd8`

## string_xrefs

- `0x14009fb35`: `shell32.dll`
- `0x14009fbc6`: `SHGetKnownFolderPath`
- `0x14009fc6f`: `SHGetKnownFolderPath(LocalAppDataLow) failed`
- `0x14009fc7d`: `%s\Temp`
- `0x14009fccc`: `StringCchPrintf(KnownFolderPath\Temp) failed`

## pseudocode

```c
__int64 __fastcall CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(__int64 a1, unsigned __int16 *a2)
{
  void *v2; // rcx
  HMODULE Library; // rax
  HMODULE v5; // r14
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // ebx
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  signed int LastError; // eax
  signed int v18; // ebp
  PVOID *v19; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v21; // eax
  void *v23; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v23 = 0;
  if ( a2 )
  {
    Library = LoadLibraryExW(L"shell32.dll", 0, 0);
    v5 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SHGetKnownFolderPath");
      if ( ProcAddress )
      {
        v11 = ((__int64 (__fastcall *)(const GUID *, _QWORD, _QWORD, void **))ProcAddress)(
                &FOLDERID_LocalAppDataLow,
                0,
                0,
                &v23);
        if ( v11 >= 0 )
        {
          v11 = StringCchPrintfW(a2, 0x104u, L"%s\\Temp", v23);
          if ( v11 >= 0 )
          {
            if ( CreateDirectoryW(a2, 0) )
              goto LABEL_45;
            LastError = GetLastError();
            v18 = LastError;
            if ( LastError == 183 )
              goto LABEL_45;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
            else
              v11 = LastError;
            v19 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  52,
                  &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                  CurrentThreadActivityIdPrefix,
                  v18);
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 3u )
              {
                v21 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  53,
                  (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                  v21,
                  (__int64)a2);
              }
            }
LABEL_43:
            if ( v11 >= 0 )
            {
LABEL_45:
              v2 = v23;
              goto LABEL_47;
            }
LABEL_44:
            *a2 = 0;
            goto LABEL_45;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 51;
          v16 = "StringCchPrintf(KnownFolderPath\\Temp) failed";
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 50;
          v16 = "SHGetKnownFolderPath(LocalAppDataLow) failed";
        }
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
          v14,
          (__int64)v16,
          v11);
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 49;
        goto LABEL_9;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 48;
LABEL_9:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v8, v7);
    }
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_43;
  }
  v5 = 0;
  v11 = -2147024809;
LABEL_47:
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v5 )
    FreeLibrary(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14009fb0c  mov     [rsp+arg_0], rbx
0x14009fb11  mov     [rsp+arg_10], rbp
0x14009fb16  push    rdi
0x14009fb17  push    r14
0x14009fb19  push    r15
0x14009fb1b  sub     rsp, 30h
0x14009fb1f  xor     ecx, ecx; pv
0x14009fb21  mov     r15, rdx
0x14009fb24  mov     [rsp+48h+arg_8], rcx
0x14009fb29  test    rdx, rdx
0x14009fb2c  jz      loc_14009FDCB
0x14009fb32  xor     r8d, r8d; dwFlags
0x14009fb35  lea     rcx, aShell32Dll_0; "shell32.dll"
0x14009fb3c  xor     edx, edx; hFile
0x14009fb3e  call    cs:__imp_LoadLibraryExW
0x14009fb44  mov     r14, rax
0x14009fb47  test    rax, rax
0x14009fb4a  jnz     short loc_14009FBC6
0x14009fb4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fb53  lea     rdi, WPP_GLOBAL_Control
0x14009fb5a  cmp     rcx, rdi
0x14009fb5d  jz      short loc_14009FBA8
0x14009fb5f  test    byte ptr [rcx+1Ch], 8
0x14009fb63  jz      short loc_14009FBA8
0x14009fb65  cmp     byte ptr [rcx+19h], 2
0x14009fb69  jb      short loc_14009FBA8
0x14009fb6b  call    cs:__imp_GetLastError
0x14009fb71  mov     ebx, eax
0x14009fb73  test    eax, eax
0x14009fb75  jle     short loc_14009FB80
0x14009fb77  movzx   ebx, ax
0x14009fb7a  or      ebx, 80070000h
0x14009fb80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fb85  mov     edx, 30h ; '0'
0x14009fb8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fb91  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009fb98  mov     r9d, eax
0x14009fb9b  mov     dword ptr [rsp+48h+var_28], ebx
0x14009fb9f  mov     rcx, [rcx+10h]
0x14009fba3  call    WPP_SF_Dd
0x14009fba8  call    cs:__imp_GetLastError
0x14009fbae  mov     ebx, eax
0x14009fbb0  test    eax, eax
0x14009fbb2  jle     loc_14009FDBA
0x14009fbb8  movzx   ebx, ax
0x14009fbbb  or      ebx, 80070000h
0x14009fbc1  jmp     loc_14009FDBA
0x14009fbc6  lea     rdx, aShgetknownfold_0; "SHGetKnownFolderPath"
0x14009fbcd  mov     rcx, rax; hModule
0x14009fbd0  call    cs:__imp_GetProcAddress
0x14009fbd6  test    rax, rax
0x14009fbd9  jnz     short loc_14009FC1E
0x14009fbdb  mov     rax, cs:WPP_GLOBAL_Control
0x14009fbe2  lea     rdi, WPP_GLOBAL_Control
0x14009fbe9  cmp     rax, rdi
0x14009fbec  jz      short loc_14009FBA8
0x14009fbee  test    byte ptr [rax+1Ch], 8
0x14009fbf2  jz      short loc_14009FBA8
0x14009fbf4  cmp     byte ptr [rax+19h], 2
0x14009fbf8  jb      short loc_14009FBA8
0x14009fbfa  call    cs:__imp_GetLastError
0x14009fc00  mov     ebx, eax
0x14009fc02  test    eax, eax
0x14009fc04  jle     short loc_14009FC0F
0x14009fc06  movzx   ebx, ax
0x14009fc09  or      ebx, 80070000h
0x14009fc0f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fc14  mov     edx, 31h ; '1'
0x14009fc19  jmp     loc_14009FB8A
0x14009fc1e  lea     r9, [rsp+48h+arg_8]
0x14009fc23  xor     r8d, r8d
0x14009fc26  xor     edx, edx
0x14009fc28  lea     rcx, FOLDERID_LocalAppDataLow
0x14009fc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009fc34  mov     ebx, eax
0x14009fc36  test    eax, eax
0x14009fc38  jns     short loc_14009FC78
0x14009fc3a  mov     rax, cs:WPP_GLOBAL_Control
0x14009fc41  lea     rdi, WPP_GLOBAL_Control
0x14009fc48  cmp     rax, rdi
0x14009fc4b  jz      loc_14009FDBE
0x14009fc51  test    byte ptr [rax+1Ch], 8
0x14009fc55  jz      loc_14009FDBE
0x14009fc5b  cmp     byte ptr [rax+19h], 2
0x14009fc5f  jb      loc_14009FDBE
0x14009fc65  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fc6a  mov     edx, 32h ; '2'
0x14009fc6f  lea     rcx, aShgetknownfold_2; "SHGetKnownFolderPath(LocalAppDataLow) f"...
0x14009fc76  jmp     short loc_14009FCD3
0x14009fc78  mov     r9, [rsp+48h+arg_8]
0x14009fc7d  lea     r8, aSTemp; "%s\\Temp"
0x14009fc84  mov     edx, 104h; unsigned __int64
0x14009fc89  mov     rcx, r15; unsigned __int16 *
0x14009fc8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14009fc91  mov     ebx, eax
0x14009fc93  test    eax, eax
0x14009fc95  jns     short loc_14009FCFB
0x14009fc97  mov     rax, cs:WPP_GLOBAL_Control
0x14009fc9e  lea     rdi, WPP_GLOBAL_Control
0x14009fca5  cmp     rax, rdi
0x14009fca8  jz      loc_14009FDBE
0x14009fcae  test    byte ptr [rax+1Ch], 8
0x14009fcb2  jz      loc_14009FDBE
0x14009fcb8  cmp     byte ptr [rax+19h], 2
0x14009fcbc  jb      loc_14009FDBE
0x14009fcc2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fcc7  mov     edx, 33h ; '3'
0x14009fccc  lea     rcx, aStringcchprint_3; "StringCchPrintf(KnownFolderPath\\Temp) "...
0x14009fcd3  mov     [rsp+48h+var_20], ebx
0x14009fcd7  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009fcde  mov     [rsp+48h+var_28], rcx
0x14009fce3  mov     r9d, eax
0x14009fce6  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fced  mov     rcx, [rcx+10h]
0x14009fcf1  call    WPP_SF_DsD
0x14009fcf6  jmp     loc_14009FDBE
0x14009fcfb  xor     edx, edx; lpSecurityAttributes
0x14009fcfd  mov     rcx, r15; lpPathName
0x14009fd00  call    cs:__imp_CreateDirectoryW
0x14009fd06  test    eax, eax
0x14009fd08  jnz     loc_14009FDC4
0x14009fd0e  call    cs:__imp_GetLastError
0x14009fd14  mov     ebp, eax
0x14009fd16  cmp     eax, 0B7h
0x14009fd1b  jz      loc_14009FDC4
0x14009fd21  test    eax, eax
0x14009fd23  jg      short loc_14009FD29
0x14009fd25  mov     ebx, eax
0x14009fd27  jmp     short loc_14009FD32
0x14009fd29  movzx   ebx, bp
0x14009fd2c  or      ebx, 80070000h
0x14009fd32  mov     rax, cs:WPP_GLOBAL_Control
0x14009fd39  lea     rdi, WPP_GLOBAL_Control
0x14009fd40  cmp     rax, rdi
0x14009fd43  jz      short loc_14009FDBA
0x14009fd45  test    byte ptr [rax+1Ch], 1
0x14009fd49  jz      short loc_14009FD80
0x14009fd4b  cmp     byte ptr [rax+19h], 2
0x14009fd4f  jb      short loc_14009FD80
0x14009fd51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fd56  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fd5d  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009fd64  mov     edx, 34h ; '4'
0x14009fd69  mov     dword ptr [rsp+48h+var_28], ebp
0x14009fd6d  mov     r9d, eax
0x14009fd70  mov     rcx, [rcx+10h]
0x14009fd74  call    WPP_SF_Dd
0x14009fd79  mov     rax, cs:WPP_GLOBAL_Control
0x14009fd80  cmp     rax, rdi
0x14009fd83  jz      short loc_14009FDBA
0x14009fd85  test    byte ptr [rax+1Ch], 1
0x14009fd89  jz      short loc_14009FDBA
0x14009fd8b  cmp     byte ptr [rax+19h], 3
0x14009fd8f  jb      short loc_14009FDBA
0x14009fd91  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009fd96  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fd9d  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x14009fda4  mov     edx, 35h ; '5'
0x14009fda9  mov     [rsp+48h+var_28], r15
0x14009fdae  mov     r9d, eax
0x14009fdb1  mov     rcx, [rcx+10h]
0x14009fdb5  call    WPP_SF_DS
0x14009fdba  test    ebx, ebx
0x14009fdbc  jns     short loc_14009FDC4
0x14009fdbe  xor     eax, eax
0x14009fdc0  mov     [r15], ax
0x14009fdc4  mov     rcx, [rsp+48h+arg_8]
0x14009fdc9  jmp     short loc_14009FDD3
0x14009fdcb  xor     r14d, r14d
0x14009fdce  mov     ebx, 80070057h
0x14009fdd3  test    rcx, rcx
0x14009fdd6  jz      short loc_14009FDDE
0x14009fdd8  call    cs:__imp_CoTaskMemFree
0x14009fdde  test    r14, r14
0x14009fde1  jz      short loc_14009FDEC
0x14009fde3  mov     rcx, r14; hLibModule
0x14009fde6  call    cs:__imp_FreeLibrary
0x14009fdec  mov     rbp, [rsp+48h+arg_10]
0x14009fdf1  mov     eax, ebx
0x14009fdf3  mov     rbx, [rsp+48h+arg_0]
0x14009fdf8  add     rsp, 30h
0x14009fdfc  pop     r15
0x14009fdfe  pop     r14
0x14009fe00  pop     rdi
0x14009fe01  retn
```
