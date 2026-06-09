# CabAndUploadFiles(void)

- ea: `0x14003ceb0`
- end: `0x14003d0a2`
- name: `?CabAndUploadFiles@@YAJXZ`
- size: `498`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14003eb60`

## callees

- `0x140020420`
- `0x14003ceb0`
- `0x14003e5f0`
- `0x14003e700`
- `0x140040360`
- `0x140041578`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14003cf22`
- `KERNEL32!HeapAlloc` at `0x14003cf59`
- `KERNEL32!HeapAlloc` at `0x14003cf22`
- `KERNEL32!HeapAlloc` at `0x14003cf59`
- `KERNEL32!HeapFree` at `0x14003d05e`
- `KERNEL32!HeapFree` at `0x14003d083`
- `KERNEL32!HeapFree` at `0x14003d05e`
- `KERNEL32!HeapFree` at `0x14003d083`
- `KERNEL32!GetProcessHeap` at `0x14003cf09`
- `KERNEL32!GetProcessHeap` at `0x14003cf45`
- `KERNEL32!GetProcessHeap` at `0x14003d04a`
- `KERNEL32!GetProcessHeap` at `0x14003d06f`
- `KERNEL32!GetProcessHeap` at `0x14003cf09`
- `KERNEL32!GetProcessHeap` at `0x14003cf45`
- `KERNEL32!GetProcessHeap` at `0x14003d04a`
- `KERNEL32!GetProcessHeap` at `0x14003d06f`
- `KERNEL32!GetFullPathNameW` at `0x14003cfb0`
- `KERNEL32!GetFullPathNameW` at `0x14003cfb0`

## pseudocode

```c
__int64 CabAndUploadFiles(void)
{
  int updated; // eax
  unsigned int v1; // ebx
  int v2; // r9d
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // rsi
  HANDLE v5; // rax
  WCHAR *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // rdi
  int TemporaryFileName; // eax
  Configuration *v11; // r8
  int Cab; // eax
  int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  LPWSTR FilePart; // [rsp+40h] [rbp+8h] BYREF

  FilePart = 0;
  g_ErrorContext = 405;
  updated = UpdateUITextByID(0x164u);
  v1 = updated;
  if ( updated < 0 )
  {
    v2 = 999;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CabAndUploadFiles", v2, updated);
    return v1;
  }
  ProcessHeap = GetProcessHeap();
  v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v4 )
  {
    updated = -2147024882;
    v2 = 1001;
    v1 = -2147024882;
    goto LABEL_3;
  }
  v5 = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(v5, 0, 0x208u);
  v9 = v6;
  if ( v6 )
  {
    TemporaryFileName = GetTemporaryFileName(v6, v7, v8);
    v1 = TemporaryFileName;
    if ( TemporaryFileName >= 0 )
    {
      if ( GetFullPathNameW(v9, 0x104u, v4, &FilePart) - 1 > 0x103 || FilePart <= v4 )
      {
        v1 = -2147319786;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CabAndUploadFiles", 1017, -2147319786);
      }
      else
      {
        v11 = Config;
        *(FilePart - 1) = 0;
        Cab = CreateCab(v4, FilePart, *((unsigned __int16 ***)v11 + 17), *((_DWORD *)v11 + 52));
        v1 = Cab;
        if ( Cab >= 0 )
        {
          v13 = UploadFile(v9);
          v1 = v13;
          if ( v13 < 0 )
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CabAndUploadFiles", 1034, v13);
        }
        else
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CabAndUploadFiles", 1031, Cab);
        }
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CabAndUploadFiles", 1008, TemporaryFileName);
    }
  }
  else
  {
    v1 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CabAndUploadFiles", 1002, -2147024882);
  }
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v4);
  if ( v9 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v9);
  }
  return v1;
}

```

## disassembly

```asm
0x14003ceb0  mov     [rsp+arg_8], rbx
0x14003ceb5  mov     [rsp+arg_10], rsi
0x14003ceba  push    rdi
0x14003cebb  sub     rsp, 30h
0x14003cebf  mov     [rsp+38h+FilePart], 0
0x14003cec8  mov     ecx, 164h; uID
0x14003cecd  mov     cs:?g_ErrorContext@@3IC, 195h; uint volatile g_ErrorContext
0x14003ced7  call    ?UpdateUITextByID@@YAJI@Z; UpdateUITextByID(uint)
0x14003cedc  mov     ebx, eax
0x14003cede  test    eax, eax
0x14003cee0  jns     short loc_14003CF09
0x14003cee2  mov     r9d, 3E7h
0x14003cee8  lea     r8, aCabanduploadfi; "CabAndUploadFiles"
0x14003ceef  mov     [rsp+38h+var_18], eax
0x14003cef3  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003cefa  mov     ecx, 1; Level
0x14003ceff  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003cf04  jmp     loc_14003D08F
0x14003cf09  call    cs:__imp_GetProcessHeap
0x14003cf10  nop     dword ptr [rax+rax+00h]
0x14003cf15  mov     ebx, 208h
0x14003cf1a  xor     edx, edx; dwFlags
0x14003cf1c  mov     rcx, rax; hHeap
0x14003cf1f  mov     r8d, ebx; dwBytes
0x14003cf22  call    cs:__imp_HeapAlloc
0x14003cf29  nop     dword ptr [rax+rax+00h]
0x14003cf2e  mov     rsi, rax
0x14003cf31  test    rax, rax
0x14003cf34  jnz     short loc_14003CF45
0x14003cf36  mov     eax, 8007000Eh
0x14003cf3b  mov     r9d, 3E9h
0x14003cf41  mov     ebx, eax
0x14003cf43  jmp     short loc_14003CEE8
0x14003cf45  call    cs:__imp_GetProcessHeap
0x14003cf4c  nop     dword ptr [rax+rax+00h]
0x14003cf51  mov     r8, rbx; dwBytes
0x14003cf54  xor     edx, edx; dwFlags
0x14003cf56  mov     rcx, rax; hHeap
0x14003cf59  call    cs:__imp_HeapAlloc
0x14003cf60  nop     dword ptr [rax+rax+00h]
0x14003cf65  mov     rdi, rax
0x14003cf68  test    rax, rax
0x14003cf6b  jnz     short loc_14003CF83
0x14003cf6d  mov     eax, 8007000Eh
0x14003cf72  mov     r9d, 3EAh
0x14003cf78  mov     ebx, eax
0x14003cf7a  mov     [rsp+38h+var_18], eax
0x14003cf7e  jmp     loc_14003D032
0x14003cf83  mov     rcx, rdi; lpTempFileName
0x14003cf86  call    ?GetTemporaryFileName@@YAJPEAG@Z; GetTemporaryFileName(ushort *)
0x14003cf8b  mov     ebx, eax
0x14003cf8d  test    eax, eax
0x14003cf8f  jns     short loc_14003CFA0
0x14003cf91  mov     [rsp+38h+var_18], eax
0x14003cf95  mov     r9d, 3F0h
0x14003cf9b  jmp     loc_14003D032
0x14003cfa0  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x14003cfa5  mov     r8, rsi; lpBuffer
0x14003cfa8  mov     edx, 104h; nBufferLength
0x14003cfad  mov     rcx, rdi; lpFileName
0x14003cfb0  call    cs:__imp_GetFullPathNameW
0x14003cfb7  nop     dword ptr [rax+rax+00h]
0x14003cfbc  dec     eax
0x14003cfbe  cmp     eax, 103h
0x14003cfc3  ja      short loc_14003D023
0x14003cfc5  mov     rcx, [rsp+38h+FilePart]
0x14003cfca  cmp     rcx, rsi
0x14003cfcd  jbe     short loc_14003D023
0x14003cfcf  mov     r8, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003cfd6  xor     eax, eax
0x14003cfd8  mov     [rcx-2], ax
0x14003cfdc  mov     rcx, rsi; unsigned __int16 *
0x14003cfdf  mov     rdx, [rsp+38h+FilePart]; unsigned __int16 *
0x14003cfe4  mov     r9d, [r8+0D0h]; unsigned int
0x14003cfeb  mov     r8, [r8+88h]; unsigned __int16 **
0x14003cff2  call    ?CreateCab@@YAJPEBG0PEAPEAGI@Z; CreateCab(ushort const *,ushort const *,ushort * *,uint)
0x14003cff7  mov     ebx, eax
0x14003cff9  test    eax, eax
0x14003cffb  jns     short loc_14003D009
0x14003cffd  mov     [rsp+38h+var_18], eax
0x14003d001  mov     r9d, 407h
0x14003d007  jmp     short loc_14003D032
0x14003d009  mov     rcx, rdi; unsigned __int16 *
0x14003d00c  call    ?UploadFile@@YAJPEAG@Z; UploadFile(ushort *)
0x14003d011  mov     ebx, eax
0x14003d013  test    eax, eax
0x14003d015  jns     short loc_14003D04A
0x14003d017  mov     [rsp+38h+var_18], eax
0x14003d01b  mov     r9d, 40Ah
0x14003d021  jmp     short loc_14003D032
0x14003d023  mov     ebx, 80028016h
0x14003d028  mov     r9d, 3F9h
0x14003d02e  mov     [rsp+38h+var_18], ebx
0x14003d032  lea     r8, aCabanduploadfi; "CabAndUploadFiles"
0x14003d039  mov     ecx, 1; Level
0x14003d03e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003d045  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003d04a  call    cs:__imp_GetProcessHeap
0x14003d051  nop     dword ptr [rax+rax+00h]
0x14003d056  mov     r8, rsi; lpMem
0x14003d059  xor     edx, edx; dwFlags
0x14003d05b  mov     rcx, rax; hHeap
0x14003d05e  call    cs:__imp_HeapFree
0x14003d065  nop     dword ptr [rax+rax+00h]
0x14003d06a  test    rdi, rdi
0x14003d06d  jz      short loc_14003D08F
0x14003d06f  call    cs:__imp_GetProcessHeap
0x14003d076  nop     dword ptr [rax+rax+00h]
0x14003d07b  mov     r8, rdi; lpMem
0x14003d07e  xor     edx, edx; dwFlags
0x14003d080  mov     rcx, rax; hHeap
0x14003d083  call    cs:__imp_HeapFree
0x14003d08a  nop     dword ptr [rax+rax+00h]
0x14003d08f  mov     rsi, [rsp+38h+arg_10]
0x14003d094  mov     eax, ebx
0x14003d096  mov     rbx, [rsp+38h+arg_8]
0x14003d09b  add     rsp, 30h
0x14003d09f  pop     rdi
0x14003d0a0  retn
```
