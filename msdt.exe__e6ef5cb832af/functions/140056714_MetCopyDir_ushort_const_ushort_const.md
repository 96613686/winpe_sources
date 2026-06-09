# MetCopyDir(ushort const *,ushort const *)

- ea: `0x140056714`
- end: `0x140056a61`
- name: `?MetCopyDir@@YAJPEBG0@Z`
- size: `845`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400537a4`
- `0x140056714`

## callees

- `0x1400039b1`
- `0x1400070b0`
- `0x140020420`
- `0x140056714`
- `0x140056a68`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005693d`
- `KERNEL32!GetLastError` at `0x1400569b5`
- `KERNEL32!GetLastError` at `0x14005693d`
- `KERNEL32!GetLastError` at `0x1400569b5`
- `KERNEL32!HeapAlloc` at `0x140056770`
- `KERNEL32!HeapAlloc` at `0x1400567c4`
- `KERNEL32!HeapAlloc` at `0x140056770`
- `KERNEL32!HeapAlloc` at `0x1400567c4`
- `KERNEL32!HeapFree` at `0x140056a06`
- `KERNEL32!HeapFree` at `0x140056a26`
- `KERNEL32!HeapFree` at `0x140056a06`
- `KERNEL32!HeapFree` at `0x140056a26`
- `KERNEL32!GetProcessHeap` at `0x140056757`
- `KERNEL32!GetProcessHeap` at `0x1400567b0`
- `KERNEL32!GetProcessHeap` at `0x1400569f2`
- `KERNEL32!GetProcessHeap` at `0x140056a12`
- `KERNEL32!GetProcessHeap` at `0x140056757`
- `KERNEL32!GetProcessHeap` at `0x1400567b0`
- `KERNEL32!GetProcessHeap` at `0x1400569f2`
- `KERNEL32!GetProcessHeap` at `0x140056a12`
- `KERNEL32!FindFirstFileW` at `0x14005683c`
- `KERNEL32!FindFirstFileW` at `0x14005683c`
- `KERNEL32!FindNextFileW` at `0x140056964`
- `KERNEL32!FindNextFileW` at `0x140056964`
- `KERNEL32!FindClose` at `0x14005697b`
- `KERNEL32!FindClose` at `0x14005697b`
- `KERNEL32!CopyFileW` at `0x140056929`
- `KERNEL32!CopyFileW` at `0x140056929`
- `msvcrt!_wcsicmp` at `0x1400568be`
- `msvcrt!_wcsicmp` at `0x1400568de`
- `msvcrt!_wcsicmp` at `0x1400568be`
- `msvcrt!_wcsicmp` at `0x1400568de`

## string_xrefs

- `0x140056789`: `MetCopyDir`
- `0x1400567dd`: `MetCopyDir`
- `0x1400569da`: `MetCopyDir`

## pseudocode

```c
__int64 __fastcall MetCopyDir(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rdi
  signed int v6; // ebx
  HANDLE v7; // rax
  unsigned __int16 *v8; // rsi
  int v9; // eax
  char *FirstFileW; // rbp
  int v11; // eax
  int v12; // eax
  int Directory; // eax
  int v14; // eax
  signed int v15; // eax
  int v16; // r9d
  signed int LastError; // eax
  HANDLE v18; // rax
  HANDLE v19; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-288h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v5 )
  {
    v7 = GetProcessHeap();
    v8 = (unsigned __int16 *)HeapAlloc(v7, 0, 0x208u);
    if ( v8 )
    {
      v9 = StringCchPrintfW(v5, 0x104u, L"%s\\*", a2);
      v6 = v9;
      if ( v9 >= 0 )
      {
        FirstFileW = (char *)FindFirstFileW(v5, &FindFileData);
        if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          v16 = 714;
LABEL_30:
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", v16, v6);
        }
        else
        {
          while ( 1 )
          {
            v11 = StringCchPrintfW(v5, 0x104u, L"%s\\%s", a2, FindFileData.cFileName);
            v6 = v11;
            if ( v11 < 0 )
              break;
            v12 = StringCchPrintfW(v8, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
            v6 = v12;
            if ( v12 < 0 )
            {
              SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 731, v12);
              goto LABEL_31;
            }
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              if ( _wcsicmp(FindFileData.cFileName, L".") && _wcsicmp(FindFileData.cFileName, L"..") )
              {
                Directory = MetCreateDirectory(a1);
                v6 = Directory;
                if ( Directory < 0 )
                {
                  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 740, Directory);
                  goto LABEL_31;
                }
                v14 = MetCopyDir(v8, v5);
                v6 = v14;
                if ( v14 < 0 )
                {
                  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 743, v14);
                  goto LABEL_31;
                }
              }
            }
            else if ( CopyFileW(v5, v8, 0) )
            {
              v6 = 0;
            }
            else
            {
              v15 = GetLastError();
              v6 = v15;
              if ( v15 > 0 )
                v6 = (unsigned __int16)v15 | 0x80070000;
              if ( v6 < 0 )
              {
                v16 = 751;
                goto LABEL_30;
              }
            }
            if ( !FindNextFileW(FirstFileW, &FindFileData) )
            {
              FindClose(FirstFileW);
              goto LABEL_31;
            }
          }
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 723, v11);
        }
      }
      else
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 711, v9);
      }
LABEL_31:
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v8);
    }
    else
    {
      v6 = -2147024882;
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 708, -2147024882);
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  else
  {
    v6 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCopyDir", 707, -2147024882);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140056714  mov     [rsp+arg_10], rbx
0x140056719  mov     [rsp+arg_18], rbp
0x14005671e  push    rsi
0x14005671f  push    rdi
0x140056720  push    r12
0x140056722  push    r14
0x140056724  push    r15
0x140056726  sub     rsp, 290h
0x14005672d  mov     rax, cs:__security_cookie
0x140056734  xor     rax, rsp
0x140056737  mov     [rsp+2B8h+var_38], rax
0x14005673f  mov     r15, rdx
0x140056742  mov     r14, rcx
0x140056745  xor     edx, edx; Val
0x140056747  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x14005674c  mov     r8d, 250h; Size
0x140056752  call    memset_0
0x140056757  call    cs:__imp_GetProcessHeap
0x14005675e  nop     dword ptr [rax+rax+00h]
0x140056763  mov     ebx, 208h
0x140056768  xor     edx, edx; dwFlags
0x14005676a  mov     rcx, rax; hHeap
0x14005676d  mov     r8d, ebx; dwBytes
0x140056770  call    cs:__imp_HeapAlloc
0x140056777  nop     dword ptr [rax+rax+00h]
0x14005677c  mov     rdi, rax
0x14005677f  test    rax, rax
0x140056782  jnz     short loc_1400567B0
0x140056784  mov     eax, 8007000Eh
0x140056789  lea     r8, aMetcopydir; "MetCopyDir"
0x140056790  mov     r9d, 2C3h
0x140056796  mov     dword ptr [rsp+2B8h+var_298], eax
0x14005679a  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400567a1  mov     ebx, eax
0x1400567a3  lea     ecx, [rdi+1]; Level
0x1400567a6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400567ab  jmp     loc_140056A32
0x1400567b0  call    cs:__imp_GetProcessHeap
0x1400567b7  nop     dword ptr [rax+rax+00h]
0x1400567bc  mov     r8, rbx; dwBytes
0x1400567bf  xor     edx, edx; dwFlags
0x1400567c1  mov     rcx, rax; hHeap
0x1400567c4  call    cs:__imp_HeapAlloc
0x1400567cb  nop     dword ptr [rax+rax+00h]
0x1400567d0  mov     rsi, rax
0x1400567d3  test    rax, rax
0x1400567d6  jnz     short loc_140056804
0x1400567d8  mov     eax, 8007000Eh
0x1400567dd  lea     r8, aMetcopydir; "MetCopyDir"
0x1400567e4  mov     r9d, 2C4h
0x1400567ea  mov     dword ptr [rsp+2B8h+var_298], eax
0x1400567ee  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400567f5  mov     ebx, eax
0x1400567f7  lea     ecx, [rsi+1]; Level
0x1400567fa  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400567ff  jmp     loc_140056A12
0x140056804  mov     r12d, 104h
0x14005680a  lea     r8, aS; "%s\\*"
0x140056811  mov     edx, r12d; unsigned __int64
0x140056814  mov     r9, r15
0x140056817  mov     rcx, rdi; unsigned __int16 *
0x14005681a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005681f  mov     ebx, eax
0x140056821  test    eax, eax
0x140056823  jns     short loc_140056834
0x140056825  mov     dword ptr [rsp+2B8h+var_298], eax
0x140056829  mov     r9d, 2C7h
0x14005682f  jmp     loc_1400569DA
0x140056834  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x140056839  mov     rcx, rdi; lpFileName
0x14005683c  call    cs:__imp_FindFirstFileW
0x140056843  nop     dword ptr [rax+rax+00h]
0x140056848  mov     rbp, rax
0x14005684b  lea     rcx, [rax-1]
0x14005684f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140056853  ja      loc_1400569B5
0x140056859  lea     rax, [rsp+2B8h+FindFileData.cFileName]
0x14005685e  mov     r9, r15
0x140056861  lea     r8, aSS_1; "%s\\%s"
0x140056868  mov     [rsp+2B8h+var_298], rax
0x14005686d  mov     rdx, r12; unsigned __int64
0x140056870  mov     rcx, rdi; unsigned __int16 *
0x140056873  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140056878  mov     ebx, eax
0x14005687a  test    eax, eax
0x14005687c  js      loc_1400569A9
0x140056882  lea     rax, [rsp+2B8h+FindFileData.cFileName]
0x140056887  mov     r9, r14
0x14005688a  lea     r8, aSS_1; "%s\\%s"
0x140056891  mov     [rsp+2B8h+var_298], rax
0x140056896  mov     rdx, r12; unsigned __int64
0x140056899  mov     rcx, rsi; unsigned __int16 *
0x14005689c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400568a1  mov     ebx, eax
0x1400568a3  test    eax, eax
0x1400568a5  js      loc_14005699D
0x1400568ab  test    byte ptr [rsp+2B8h+FindFileData.dwFileAttributes], 10h
0x1400568b0  jz      short loc_140056920
0x1400568b2  lea     rdx, asc_1400707D8; "."
0x1400568b9  lea     rcx, [rsp+2B8h+FindFileData.cFileName]; String1
0x1400568be  call    cs:__imp__wcsicmp
0x1400568c5  nop     dword ptr [rax+rax+00h]
0x1400568ca  test    eax, eax
0x1400568cc  jz      loc_14005695C
0x1400568d2  lea     rdx, asc_140070B9C; ".."
0x1400568d9  lea     rcx, [rsp+2B8h+FindFileData.cFileName]; String1
0x1400568de  call    cs:__imp__wcsicmp
0x1400568e5  nop     dword ptr [rax+rax+00h]
0x1400568ea  test    eax, eax
0x1400568ec  jz      short loc_14005695C
0x1400568ee  mov     rcx, r14; lpSrc
0x1400568f1  call    ?MetCreateDirectory@@YAJPEBG@Z; MetCreateDirectory(ushort const *)
0x1400568f6  mov     ebx, eax
0x1400568f8  test    eax, eax
0x1400568fa  js      loc_140056989
0x140056900  mov     rdx, rdi; unsigned __int16 *
0x140056903  mov     rcx, rsi; unsigned __int16 *
0x140056906  call    ?MetCopyDir@@YAJPEBG0@Z; MetCopyDir(ushort const *,ushort const *)
0x14005690b  mov     ebx, eax
0x14005690d  test    eax, eax
0x14005690f  jns     short loc_14005695C
0x140056911  mov     dword ptr [rsp+2B8h+var_298], eax
0x140056915  mov     r9d, 2E7h
0x14005691b  jmp     loc_1400569DA
0x140056920  xor     r8d, r8d; bFailIfExists
0x140056923  mov     rdx, rsi; lpNewFileName
0x140056926  mov     rcx, rdi; lpExistingFileName
0x140056929  call    cs:__imp_CopyFileW
0x140056930  nop     dword ptr [rax+rax+00h]
0x140056935  test    eax, eax
0x140056937  jz      short loc_14005693D
0x140056939  xor     ebx, ebx
0x14005693b  jmp     short loc_14005695C
0x14005693d  call    cs:__imp_GetLastError
0x140056944  nop     dword ptr [rax+rax+00h]
0x140056949  mov     ebx, eax
0x14005694b  test    eax, eax
0x14005694d  jle     short loc_140056958
0x14005694f  movzx   ebx, ax
0x140056952  or      ebx, 80070000h
0x140056958  test    ebx, ebx
0x14005695a  js      short loc_140056995
0x14005695c  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x140056961  mov     rcx, rbp; hFindFile
0x140056964  call    cs:__imp_FindNextFileW
0x14005696b  nop     dword ptr [rax+rax+00h]
0x140056970  test    eax, eax
0x140056972  jnz     loc_140056859
0x140056978  mov     rcx, rbp; hFindFile
0x14005697b  call    cs:__imp_FindClose
0x140056982  nop     dword ptr [rax+rax+00h]
0x140056987  jmp     short loc_1400569F2
0x140056989  mov     dword ptr [rsp+2B8h+var_298], eax
0x14005698d  mov     r9d, 2E4h
0x140056993  jmp     short loc_1400569DA
0x140056995  mov     r9d, 2EFh
0x14005699b  jmp     short loc_1400569D6
0x14005699d  mov     dword ptr [rsp+2B8h+var_298], eax
0x1400569a1  mov     r9d, 2DBh
0x1400569a7  jmp     short loc_1400569DA
0x1400569a9  mov     dword ptr [rsp+2B8h+var_298], eax
0x1400569ad  mov     r9d, 2D3h
0x1400569b3  jmp     short loc_1400569DA
0x1400569b5  call    cs:__imp_GetLastError
0x1400569bc  nop     dword ptr [rax+rax+00h]
0x1400569c1  mov     ebx, eax
0x1400569c3  test    eax, eax
0x1400569c5  jle     short loc_1400569D0
0x1400569c7  movzx   ebx, ax
0x1400569ca  or      ebx, 80070000h
0x1400569d0  mov     r9d, 2CAh
0x1400569d6  mov     dword ptr [rsp+2B8h+var_298], ebx
0x1400569da  lea     r8, aMetcopydir; "MetCopyDir"
0x1400569e1  mov     ecx, 1; Level
0x1400569e6  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400569ed  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400569f2  call    cs:__imp_GetProcessHeap
0x1400569f9  nop     dword ptr [rax+rax+00h]
0x1400569fe  mov     r8, rsi; lpMem
0x140056a01  xor     edx, edx; dwFlags
0x140056a03  mov     rcx, rax; hHeap
0x140056a06  call    cs:__imp_HeapFree
0x140056a0d  nop     dword ptr [rax+rax+00h]
0x140056a12  call    cs:__imp_GetProcessHeap
0x140056a19  nop     dword ptr [rax+rax+00h]
0x140056a1e  mov     r8, rdi; lpMem
0x140056a21  xor     edx, edx; dwFlags
0x140056a23  mov     rcx, rax; hHeap
0x140056a26  call    cs:__imp_HeapFree
0x140056a2d  nop     dword ptr [rax+rax+00h]
0x140056a32  mov     eax, ebx
0x140056a34  mov     rcx, [rsp+2B8h+var_38]
0x140056a3c  xor     rcx, rsp; StackCookie
0x140056a3f  call    __security_check_cookie
0x140056a44  lea     r11, [rsp+2B8h+var_28]
0x140056a4c  mov     rbx, [r11+40h]
0x140056a50  mov     rbp, [r11+48h]
0x140056a54  mov     rsp, r11
0x140056a57  pop     r15
0x140056a59  pop     r14
0x140056a5b  pop     r12
0x140056a5d  pop     rdi
0x140056a5e  pop     rsi
0x140056a5f  retn
```
