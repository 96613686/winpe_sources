# SaveMetabaseFile(ushort *,ulong,ulong,ulong,ulong,int,ushort *,ushort *,ushort *,ushort *,int *)

- ea: `0x180024bc4`
- end: `0x180024e8a`
- name: `?SaveMetabaseFile@@YAJPEAGKKKKH0000PEAH@Z`
- size: `710`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, int, unsigned int, unsigned int, int, LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, LPCWSTR lpFileName, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180023548`

## callees

- `0x18001d084`
- `0x1800204fc`
- `0x1800231ec`
- `0x180024bc4`
- `0x1800274d0`

## import_xrefs

- `KERNEL32!MoveFileW` at `0x180024d3c`
- `KERNEL32!MoveFileW` at `0x180024d8f`
- `KERNEL32!MoveFileW` at `0x180024db6`
- `KERNEL32!MoveFileW` at `0x180024dcb`
- `KERNEL32!MoveFileW` at `0x180024df0`
- `KERNEL32!MoveFileW` at `0x180024d3c`
- `KERNEL32!MoveFileW` at `0x180024d8f`
- `KERNEL32!MoveFileW` at `0x180024db6`
- `KERNEL32!MoveFileW` at `0x180024dcb`
- `KERNEL32!MoveFileW` at `0x180024df0`
- `KERNEL32!DeleteFileW` at `0x180024da6`
- `KERNEL32!DeleteFileW` at `0x180024dfd`
- `KERNEL32!DeleteFileW` at `0x180024da6`
- `KERNEL32!DeleteFileW` at `0x180024dfd`
- `KERNEL32!GetLastError` at `0x180024d4a`
- `KERNEL32!GetLastError` at `0x180024d59`
- `KERNEL32!GetLastError` at `0x180024d99`
- `KERNEL32!GetLastError` at `0x180024dd5`
- `KERNEL32!GetLastError` at `0x180024d4a`
- `KERNEL32!GetLastError` at `0x180024d59`
- `KERNEL32!GetLastError` at `0x180024d99`
- `KERNEL32!GetLastError` at `0x180024dd5`
- `IisRTL!PuDbgPrintW` at `0x180024c1d`
- `IisRTL!PuDbgPrintW` at `0x180024c50`
- `IisRTL!PuDbgPrintW` at `0x180024cc9`
- `IisRTL!PuDbgPrintW` at `0x180024d20`
- `IisRTL!PuDbgPrintW` at `0x180024e5b`
- `IisRTL!PuDbgPrintW` at `0x180024c1d`
- `IisRTL!PuDbgPrintW` at `0x180024c50`
- `IisRTL!PuDbgPrintW` at `0x180024cc9`
- `IisRTL!PuDbgPrintW` at `0x180024d20`
- `IisRTL!PuDbgPrintW` at `0x180024e5b`

## pseudocode

```c
__int64 __fastcall SaveMetabaseFile(
        unsigned __int16 *a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        LPCWSTR lpExistingFileName,
        LPCWSTR lpNewFileName,
        LPCWSTR lpFileName,
        unsigned __int16 *a10,
        int *a11)
{
  signed int v11; // ebx
  int v12; // r12d
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  signed int v20; // esi
  __int64 v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]

  v11 = 0;
  v12 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      8691,
      "SaveMetabaseFile",
      L"[SaveAllData] HistoryMajorVersionNumber: %d.\n",
      g_ulHistoryMajorVersionNumber);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v22) = a2;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8694,
        "SaveMetabaseFile",
        L"[SaveAllData] HistoryMajorVersionNumber: %d.\n",
        v22);
    }
  }
  if ( a3 && !a10 )
    CreateHistoryFiles((unsigned __int16 *)g_wszTempFileName, a1, a2, a4);
  if ( g_dwEnableEditWhileRunning && !a6 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8716,
        "SaveMetabaseFile",
        L"[SaveAllData] Edit while running is enabled and a user has edited the file and the edit hasn't been processed. M"
         "eanwhile SaveAllData has been called. Hence SaveAllData is not renaming the file, so that the user edits are no"
         "t overwrittem.\n");
    goto LABEL_29;
  }
  if ( a10 )
  {
LABEL_16:
    if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
    {
      if ( GetLastError() == 183
        && ((ResetFileAttributesIfNeeded((LPCSTR)lpNewFileName, 1), MoveFileW(lpNewFileName, lpFileName))
         || GetLastError() == 183 && DeleteFileW(lpFileName) && MoveFileW(lpNewFileName, lpFileName)) )
      {
        if ( MoveFileW(lpExistingFileName, lpNewFileName) )
          goto LABEL_28;
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( MoveFileW(lpFileName, lpNewFileName) )
LABEL_28:
          DeleteFileW(lpFileName);
      }
      else
      {
        v18 = GetLastError();
        v11 = v18;
        if ( v18 > 0 )
          v11 = (unsigned __int16)v18 | 0x80070000;
      }
    }
LABEL_29:
    if ( a10 )
      goto LABEL_36;
    goto LABEL_30;
  }
  v17 = UnlockMetabaseFile(0);
  v11 = v17;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      8734,
      "SaveMetabaseFile",
      L"[SaveMetabaseFile] Unlocking metabase file %s returned 0x%x.\n",
      lpNewFileName,
      v17);
  if ( v11 >= 0 )
  {
    v12 = 1;
    goto LABEL_16;
  }
LABEL_30:
  if ( !g_dwEnableEditWhileRunning && v12 )
  {
    v20 = LockMetabaseFile(lpNewFileName, 0);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v23) = v11;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8842,
        "SaveMetabaseFile",
        L"[SaveMetabaseFile] Locking metabase file %s returned 0x%x.\n",
        lpNewFileName,
        v23);
    }
    if ( v11 < 0 )
      goto LABEL_37;
    v11 = v20;
  }
LABEL_36:
  if ( v11 < 0 )
LABEL_37:
    *a11 = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180024bc4  push    rbx
0x180024bc6  push    rbp
0x180024bc7  push    rsi
0x180024bc8  push    rdi
0x180024bc9  push    r12
0x180024bcb  push    r14
0x180024bcd  push    r15
0x180024bcf  sub     rsp, 40h
0x180024bd3  xor     ebx, ebx
0x180024bd5  lea     r15, aSavealldataHis; "[SaveAllData] HistoryMajorVersionNumber"...
0x180024bdc  xor     r12d, r12d
0x180024bdf  mov     ebp, r9d
0x180024be2  test    byte ptr cs:g_dwDebugFlags, 3
0x180024be9  mov     esi, r8d
0x180024bec  mov     edi, edx
0x180024bee  mov     r14, rcx
0x180024bf1  jz      short loc_180024C56
0x180024bf3  mov     eax, cs:?g_ulHistoryMajorVersionNumber@@3KA; ulong g_ulHistoryMajorVersionNumber
0x180024bf9  lea     r9, aSavemetabasefi_0; "SaveMetabaseFile"
0x180024c00  mov     rcx, cs:g_pDebug
0x180024c07  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024c0e  mov     dword ptr [rsp+78h+var_50], eax
0x180024c12  mov     r8d, 21F3h
0x180024c18  mov     [rsp+78h+var_58], r15
0x180024c1d  call    cs:__imp_PuDbgPrintW
0x180024c23  test    byte ptr cs:g_dwDebugFlags, 3
0x180024c2a  jz      short loc_180024C56
0x180024c2c  mov     rcx, cs:g_pDebug
0x180024c33  lea     r9, aSavemetabasefi_0; "SaveMetabaseFile"
0x180024c3a  mov     dword ptr [rsp+78h+var_50], edi
0x180024c3e  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024c45  mov     r8d, 21F6h
0x180024c4b  mov     [rsp+78h+var_58], r15
0x180024c50  call    cs:__imp_PuDbgPrintW
0x180024c56  mov     r15, [rsp+78h+arg_48]
0x180024c5e  test    esi, esi
0x180024c60  jz      short loc_180024C7C
0x180024c62  test    r15, r15
0x180024c65  jnz     short loc_180024C7C
0x180024c67  mov     rcx, cs:?g_wszTempFileName@@3PEAGEA; unsigned __int16 *
0x180024c6e  mov     r9d, ebp; unsigned int
0x180024c71  mov     r8d, edi; unsigned int
0x180024c74  mov     rdx, r14; unsigned __int16 *
0x180024c77  call    ?CreateHistoryFiles@@YAJPEAG0KK@Z; CreateHistoryFiles(ushort *,ushort *,ulong,ulong)
0x180024c7c  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, ebx; ulong g_dwEnableEditWhileRunning
0x180024c82  mov     rdi, [rsp+78h+lpNewFileName]
0x180024c8a  jz      short loc_180024CD4
0x180024c8c  cmp     [rsp+78h+arg_28], ebx
0x180024c93  jnz     short loc_180024CD4
0x180024c95  test    byte ptr cs:g_dwDebugFlags, 3
0x180024c9c  jz      loc_180024E03
0x180024ca2  mov     rcx, cs:g_pDebug
0x180024ca9  lea     rax, aSavealldataEdi; "[SaveAllData] Edit while running is ena"...
0x180024cb0  lea     r9, aSavemetabasefi_0; "SaveMetabaseFile"
0x180024cb7  mov     [rsp+78h+var_58], rax
0x180024cbc  mov     r8d, 220Ch
0x180024cc2  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024cc9  call    cs:__imp_PuDbgPrintW
0x180024ccf  jmp     loc_180024E03
0x180024cd4  mov     esi, 1
0x180024cd9  test    r15, r15
0x180024cdc  jnz     short loc_180024D31
0x180024cde  xor     ecx, ecx
0x180024ce0  call    ?UnlockMetabaseFile@@YAJW4_eMetabaseFile@@H@Z; UnlockMetabaseFile(_eMetabaseFile,int)
0x180024ce5  test    byte ptr cs:g_dwDebugFlags, 3
0x180024cec  mov     ebx, eax
0x180024cee  jz      short loc_180024D26
0x180024cf0  mov     rcx, cs:g_pDebug
0x180024cf7  lea     r9, aSavemetabasefi_0; "SaveMetabaseFile"
0x180024cfe  mov     dword ptr [rsp+78h+var_48], eax
0x180024d02  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024d09  lea     rax, aSavemetabasefi; "[SaveMetabaseFile] Unlocking metabase f"...
0x180024d10  mov     [rsp+78h+var_50], rdi
0x180024d15  mov     r8d, 221Eh
0x180024d1b  mov     [rsp+78h+var_58], rax
0x180024d20  call    cs:__imp_PuDbgPrintW
0x180024d26  test    ebx, ebx
0x180024d28  js      loc_180024E08
0x180024d2e  mov     r12d, esi
0x180024d31  mov     rcx, [rsp+78h+lpExistingFileName]; lpExistingFileName
0x180024d39  mov     rdx, rdi; lpNewFileName
0x180024d3c  call    cs:__imp_MoveFileW
0x180024d42  test    eax, eax
0x180024d44  jnz     loc_180024E03
0x180024d4a  call    cs:__imp_GetLastError
0x180024d50  mov     ebp, 0B7h
0x180024d55  cmp     eax, ebp
0x180024d57  jz      short loc_180024D77
0x180024d59  call    cs:__imp_GetLastError
0x180024d5f  mov     ebx, eax
0x180024d61  test    eax, eax
0x180024d63  jle     loc_180024E03
0x180024d69  movzx   ebx, ax
0x180024d6c  or      ebx, 80070000h
0x180024d72  jmp     loc_180024E03
0x180024d77  mov     edx, esi; int
0x180024d79  mov     rcx, rdi; lpFileName
0x180024d7c  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x180024d81  mov     rsi, [rsp+78h+lpFileName]
0x180024d89  mov     rcx, rdi; lpExistingFileName
0x180024d8c  mov     rdx, rsi; lpNewFileName
0x180024d8f  call    cs:__imp_MoveFileW
0x180024d95  test    eax, eax
0x180024d97  jnz     short loc_180024DC0
0x180024d99  call    cs:__imp_GetLastError
0x180024d9f  cmp     eax, ebp
0x180024da1  jnz     short loc_180024D59
0x180024da3  mov     rcx, rsi; lpFileName
0x180024da6  call    cs:__imp_DeleteFileW
0x180024dac  test    eax, eax
0x180024dae  jz      short loc_180024D59
0x180024db0  mov     rdx, rsi; lpNewFileName
0x180024db3  mov     rcx, rdi; lpExistingFileName
0x180024db6  call    cs:__imp_MoveFileW
0x180024dbc  test    eax, eax
0x180024dbe  jz      short loc_180024D59
0x180024dc0  mov     rcx, [rsp+78h+lpExistingFileName]; lpExistingFileName
0x180024dc8  mov     rdx, rdi; lpNewFileName
0x180024dcb  call    cs:__imp_MoveFileW
0x180024dd1  test    eax, eax
0x180024dd3  jnz     short loc_180024DFA
0x180024dd5  call    cs:__imp_GetLastError
0x180024ddb  mov     ebx, eax
0x180024ddd  test    eax, eax
0x180024ddf  jle     short loc_180024DEA
0x180024de1  movzx   ebx, ax
0x180024de4  or      ebx, 80070000h
0x180024dea  mov     rdx, rdi; lpNewFileName
0x180024ded  mov     rcx, rsi; lpExistingFileName
0x180024df0  call    cs:__imp_MoveFileW
0x180024df6  test    eax, eax
0x180024df8  jz      short loc_180024E03
0x180024dfa  mov     rcx, rsi; lpFileName
0x180024dfd  call    cs:__imp_DeleteFileW
0x180024e03  test    r15, r15
0x180024e06  jnz     short loc_180024E67
0x180024e08  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, 0; ulong g_dwEnableEditWhileRunning
0x180024e0f  jnz     short loc_180024E67
0x180024e11  test    r12d, r12d
0x180024e14  jz      short loc_180024E67
0x180024e16  xor     edx, edx
0x180024e18  mov     rcx, rdi
0x180024e1b  call    ?LockMetabaseFile@@YAJPEBGW4_eMetabaseFile@@H@Z; LockMetabaseFile(ushort const *,_eMetabaseFile,int)
0x180024e20  test    byte ptr cs:g_dwDebugFlags, 3
0x180024e27  mov     esi, eax
0x180024e29  jz      short loc_180024E61
0x180024e2b  mov     rcx, cs:g_pDebug
0x180024e32  lea     rax, aSavemetabasefi_1; "[SaveMetabaseFile] Locking metabase fil"...
0x180024e39  mov     dword ptr [rsp+78h+var_48], ebx
0x180024e3d  lea     r9, aSavemetabasefi_0; "SaveMetabaseFile"
0x180024e44  mov     [rsp+78h+var_50], rdi
0x180024e49  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024e50  mov     r8d, 228Ah
0x180024e56  mov     [rsp+78h+var_58], rax
0x180024e5b  call    cs:__imp_PuDbgPrintW
0x180024e61  test    ebx, ebx
0x180024e63  js      short loc_180024E6B
0x180024e65  mov     ebx, esi
0x180024e67  test    ebx, ebx
0x180024e69  jns     short loc_180024E79
0x180024e6b  mov     rax, [rsp+78h+arg_50]
0x180024e73  mov     dword ptr [rax], 0
0x180024e79  mov     eax, ebx
0x180024e7b  add     rsp, 40h
0x180024e7f  pop     r15
0x180024e81  pop     r14
0x180024e83  pop     r12
0x180024e85  pop     rdi
0x180024e86  pop     rsi
0x180024e87  pop     rbp
0x180024e88  pop     rbx
0x180024e89  retn
```
