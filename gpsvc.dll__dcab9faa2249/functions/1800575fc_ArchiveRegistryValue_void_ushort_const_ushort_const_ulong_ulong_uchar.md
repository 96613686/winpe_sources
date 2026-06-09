# ArchiveRegistryValue(void *,ushort const *,ushort const *,ulong,ulong,uchar *)

- ea: `0x1800575fc`
- end: `0x180057b33`
- name: `?ArchiveRegistryValue@@YAHPEAXPEBG1KKPEAE@Z`
- size: `1335`
- prototype: `__int64 __fastcall(HANDLE hFile, const wchar_t *lpBuffer, const wchar_t *, int, DWORD nNumberOfBytesToWrite, unsigned __int8 *lpBuffera)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18009ff54`
- `0x1800a1e20`

## callees

- `0x1800575fc`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005767d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800576ea`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18005767d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800576ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057b19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005763f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005794d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005798b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005763f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005794d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005798b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057aff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005765e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005769c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800576ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057709`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057733`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057762`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005778c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800577b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800577e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005781f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800578ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005765e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005769c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800576ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057709`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057733`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180057762`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005778c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800577b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800577e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005781f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800578ac`

## string_xrefs

- `0x180057ad7`: `ArchiveRegistryValue: Failed to write open bracket with %d`
- `0x180057b05`: `ArchiveRegistryValue: Failed to write open bracket with %d`
- `0x180057a79`: `ArchiveRegistryValue: Failed to write key name with %d`
- `0x180057aa3`: `ArchiveRegistryValue: Failed to write key name with %d`
- `0x180057953`: `ArchiveRegistryValue: Failed to write semicolon with %d`
- `0x18005797f`: `ArchiveRegistryValue: Failed to write semicolon with %d`
- `0x180057a17`: `ArchiveRegistryValue: Failed to write value name with %d`
- `0x180057a43`: `ArchiveRegistryValue: Failed to write value name with %d`
- `0x1800579b5`: `ArchiveRegistryValue: Failed to write data type with %d`
- `0x1800579e1`: `ArchiveRegistryValue: Failed to write data type with %d`
- `0x18005785b`: `ArchiveRegistryValue: Failed to write data with %d`
- `0x18005788a`: `ArchiveRegistryValue: Failed to write data with %d`
- `0x1800578f1`: `ArchiveRegistryValue: Failed to write close bracket with %d`
- `0x18005791d`: `ArchiveRegistryValue: Failed to write close bracket with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ArchiveRegistryValue(
        HANDLE hFile,
        const wchar_t *lpBuffer,
        const wchar_t *a3,
        int a4,
        DWORD nNumberOfBytesToWrite,
        unsigned __int8 *lpBuffera)
{
  unsigned int v9; // r12d
  DWORD LastError; // ebx
  DWORD v11; // esi
  DWORD v12; // esi
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v14; // eax
  const wchar_t *v15; // rdx
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  _WORD v24[2]; // [rsp+30h] [rbp-28h] BYREF
  __int16 Buffer; // [rsp+34h] [rbp-24h] BYREF
  __int16 v26[2]; // [rsp+38h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+3Ch] [rbp-1Ch] BYREF
  DWORD v28; // [rsp+40h] [rbp-18h]
  int v29; // [rsp+B8h] [rbp+60h] BYREF

  v29 = a4;
  v9 = 0;
  NumberOfBytesWritten = 0;
  Buffer = 91;
  v26[0] = 93;
  v24[0] = 59;
  LastError = GetLastError();
  if ( !WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
  {
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = GetLastError();
        v15 = L"ArchiveRegistryValue: Failed to write open bracket with %d";
        goto LABEL_65;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v22 = GetLastError();
        RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write open bracket with %d", v22);
      }
    }
    goto LABEL_69;
  }
  v11 = 2 * wcsnlen(lpBuffer, 0x800u) + 2;
  if ( !WriteFile(hFile, lpBuffer, v11, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v11 )
  {
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = GetLastError();
        v15 = L"ArchiveRegistryValue: Failed to write key name with %d";
        goto LABEL_65;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v21 = GetLastError();
        RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write key name with %d", v21);
      }
    }
    goto LABEL_69;
  }
  if ( !WriteFile(hFile, v24, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
    goto LABEL_38;
  v12 = 2 * wcsnlen(a3, 0x200u) + 2;
  if ( !WriteFile(hFile, a3, v12, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v12 )
  {
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = GetLastError();
        v15 = L"ArchiveRegistryValue: Failed to write value name with %d";
        goto LABEL_65;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v20 = GetLastError();
        RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write value name with %d", v20);
      }
    }
    goto LABEL_69;
  }
  if ( !WriteFile(hFile, v24, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
    goto LABEL_38;
  if ( !WriteFile(hFile, &v29, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
    goto LABEL_44;
  if ( !WriteFile(hFile, v24, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
  {
LABEL_38:
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = GetLastError();
        v15 = L"ArchiveRegistryValue: Failed to write semicolon with %d";
        goto LABEL_65;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v18 = GetLastError();
        RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write semicolon with %d", v18);
      }
    }
    goto LABEL_69;
  }
  if ( !WriteFile(hFile, &nNumberOfBytesToWrite, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
  {
LABEL_44:
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = GetLastError();
        v15 = L"ArchiveRegistryValue: Failed to write data type with %d";
        goto LABEL_65;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v19 = GetLastError();
        RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write data type with %d", v19);
      }
    }
    goto LABEL_69;
  }
  if ( !WriteFile(hFile, v24, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
    goto LABEL_38;
  if ( !nNumberOfBytesToWrite
    || !lpBuffera
    || WriteFile(hFile, lpBuffera, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
    && NumberOfBytesWritten == nNumberOfBytesToWrite )
  {
    if ( WriteFile(hFile, v26, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
    {
      v9 = 1;
    }
    else
    {
      LastError = GetLastError();
      v28 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v13 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v14 = GetLastError();
          v15 = L"ArchiveRegistryValue: Failed to write close bracket with %d";
          goto LABEL_65;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v17 = GetLastError();
          RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write close bracket with %d", v17);
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = GetLastError();
        v15 = L"ArchiveRegistryValue: Failed to write data with %d";
LABEL_65:
        v13(2u, v15, v14);
        goto LABEL_69;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v16 = GetLastError();
        RedirectDebugMsg(2u, L"ArchiveRegistryValue: Failed to write data with %d", v16);
      }
    }
  }
LABEL_69:
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x1800575fc  mov     [rsp-40h+arg_18], r9d
0x180057601  push    rbp
0x180057602  push    rbx
0x180057603  push    rsi
0x180057604  push    rdi
0x180057605  push    r12
0x180057607  push    r13
0x180057609  push    r14
0x18005760b  push    r15
0x18005760d  mov     rbp, rsp
0x180057610  sub     rsp, 58h
0x180057614  mov     r15, r8
0x180057617  mov     r14, rdx
0x18005761a  mov     rdi, rcx
0x18005761d  xor     r13d, r13d
0x180057620  mov     r12d, r13d
0x180057623  mov     [rbp+NumberOfBytesWritten], r13d
0x180057627  lea     eax, [r13+5Bh]
0x18005762b  mov     [rbp+Buffer], ax
0x18005762f  lea     eax, [r13+5Dh]
0x180057633  mov     [rbp+var_20], ax
0x180057637  lea     eax, [r13+3Bh]
0x18005763b  mov     [rbp+var_28], ax
0x18005763f  call    cs:__imp_GetLastError
0x180057645  mov     ebx, eax
0x180057647  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x18005764c  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057650  lea     esi, [r13+2]
0x180057654  mov     r8d, esi; nNumberOfBytesToWrite
0x180057657  lea     rdx, [rbp+Buffer]; lpBuffer
0x18005765b  mov     rcx, rdi; hFile
0x18005765e  call    cs:__imp_WriteFile
0x180057664  test    eax, eax
0x180057666  jz      loc_180057AB1
0x18005766c  cmp     [rbp+NumberOfBytesWritten], esi
0x18005766f  jnz     loc_180057AB1
0x180057675  mov     edx, 800h; MaxCount
0x18005767a  mov     rcx, r14; Source
0x18005767d  call    cs:__imp_wcsnlen
0x180057683  lea     esi, ds:2[rax*2]
0x18005768a  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x18005768f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057693  mov     r8d, esi; nNumberOfBytesToWrite
0x180057696  mov     rdx, r14; lpBuffer
0x180057699  mov     rcx, rdi; hFile
0x18005769c  call    cs:__imp_WriteFile
0x1800576a2  test    eax, eax
0x1800576a4  jz      loc_180057A4F
0x1800576aa  cmp     [rbp+NumberOfBytesWritten], esi
0x1800576ad  jnz     loc_180057A4F
0x1800576b3  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x1800576b8  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800576bc  lea     r14d, [r13+2]
0x1800576c0  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800576c3  lea     rdx, [rbp+var_28]; lpBuffer
0x1800576c7  mov     rcx, rdi; hFile
0x1800576ca  call    cs:__imp_WriteFile
0x1800576d0  test    eax, eax
0x1800576d2  jz      loc_180057929
0x1800576d8  cmp     [rbp+NumberOfBytesWritten], r14d
0x1800576dc  jnz     loc_180057929
0x1800576e2  mov     edx, 200h; MaxCount
0x1800576e7  mov     rcx, r15; Source
0x1800576ea  call    cs:__imp_wcsnlen
0x1800576f0  lea     esi, ds:2[rax*2]
0x1800576f7  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x1800576fc  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057700  mov     r8d, esi; nNumberOfBytesToWrite
0x180057703  mov     rdx, r15; lpBuffer
0x180057706  mov     rcx, rdi; hFile
0x180057709  call    cs:__imp_WriteFile
0x18005770f  test    eax, eax
0x180057711  jz      loc_1800579ED
0x180057717  cmp     [rbp+NumberOfBytesWritten], esi
0x18005771a  jnz     loc_1800579ED
0x180057720  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x180057725  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057729  mov     r8d, r14d; nNumberOfBytesToWrite
0x18005772c  lea     rdx, [rbp+var_28]; lpBuffer
0x180057730  mov     rcx, rdi; hFile
0x180057733  call    cs:__imp_WriteFile
0x180057739  test    eax, eax
0x18005773b  jz      loc_180057929
0x180057741  cmp     [rbp+NumberOfBytesWritten], r14d
0x180057745  jnz     loc_180057929
0x18005774b  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x180057750  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057754  lea     esi, [r13+4]
0x180057758  mov     r8d, esi; nNumberOfBytesToWrite
0x18005775b  lea     rdx, [rbp+arg_18]; lpBuffer
0x18005775f  mov     rcx, rdi; hFile
0x180057762  call    cs:__imp_WriteFile
0x180057768  test    eax, eax
0x18005776a  jz      loc_18005798B
0x180057770  cmp     [rbp+NumberOfBytesWritten], esi
0x180057773  jnz     loc_18005798B
0x180057779  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x18005777e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180057782  mov     r8d, r14d; nNumberOfBytesToWrite
0x180057785  lea     rdx, [rbp+var_28]; lpBuffer
0x180057789  mov     rcx, rdi; hFile
0x18005778c  call    cs:__imp_WriteFile
0x180057792  test    eax, eax
0x180057794  jz      loc_180057929
0x18005779a  cmp     [rbp+NumberOfBytesWritten], r14d
0x18005779e  jnz     loc_180057929
0x1800577a4  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x1800577a9  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800577ad  mov     r8d, esi; nNumberOfBytesToWrite
0x1800577b0  lea     rdx, [rbp+nNumberOfBytesToWrite]; lpBuffer
0x1800577b4  mov     rcx, rdi; hFile
0x1800577b7  call    cs:__imp_WriteFile
0x1800577bd  test    eax, eax
0x1800577bf  jz      loc_18005798B
0x1800577c5  cmp     [rbp+NumberOfBytesWritten], esi
0x1800577c8  jnz     loc_18005798B
0x1800577ce  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x1800577d3  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800577d7  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800577da  lea     rdx, [rbp+var_28]; lpBuffer
0x1800577de  mov     rcx, rdi; hFile
0x1800577e1  call    cs:__imp_WriteFile
0x1800577e7  test    eax, eax
0x1800577e9  jz      loc_180057929
0x1800577ef  cmp     [rbp+NumberOfBytesWritten], r14d
0x1800577f3  jnz     loc_180057929
0x1800577f9  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800577fd  test    r8d, r8d
0x180057800  jz      loc_180057899
0x180057806  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18005780a  test    rdx, rdx
0x18005780d  jz      loc_180057899
0x180057813  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x180057818  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005781c  mov     rcx, rdi; hFile
0x18005781f  call    cs:__imp_WriteFile
0x180057825  test    eax, eax
0x180057827  jz      short loc_180057831
0x180057829  mov     eax, [rbp+nNumberOfBytesToWrite]
0x18005782c  cmp     [rbp+NumberOfBytesWritten], eax
0x18005782f  jz      short loc_180057899
0x180057831  call    cs:__imp_GetLastError
0x180057837  mov     ebx, eax
0x180057839  mov     [rbp+var_18], eax
0x18005783c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180057843  jz      loc_180057B17
0x180057849  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057850  test    rdi, rdi
0x180057853  jz      short loc_18005786A
0x180057855  call    cs:__imp_GetLastError
0x18005785b  lea     rdx, aArchiveregistr_1; "ArchiveRegistryValue: Failed to write d"...
0x180057862  mov     ecx, r14d
0x180057865  jmp     loc_180057AE0
0x18005786a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180057871  jz      loc_180057B17
0x180057877  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005787e  jz      loc_180057B17
0x180057884  call    cs:__imp_GetLastError
0x18005788a  lea     rdx, aArchiveregistr_1; "ArchiveRegistryValue: Failed to write d"...
0x180057891  mov     ecx, r14d
0x180057894  jmp     loc_180057B0E
0x180057899  mov     [rsp+58h+lpOverlapped], r13; lpOverlapped
0x18005789e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800578a2  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800578a5  lea     rdx, [rbp+var_20]; lpBuffer
0x1800578a9  mov     rcx, rdi; hFile
0x1800578ac  call    cs:__imp_WriteFile
0x1800578b2  test    eax, eax
0x1800578b4  jz      short loc_1800578C7
0x1800578b6  cmp     [rbp+NumberOfBytesWritten], r14d
0x1800578ba  jnz     short loc_1800578C7
0x1800578bc  mov     r12d, 1
0x1800578c2  jmp     loc_180057B17
0x1800578c7  call    cs:__imp_GetLastError
0x1800578cd  mov     ebx, eax
0x1800578cf  mov     [rbp+var_18], eax
0x1800578d2  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800578d9  jz      loc_180057B17
0x1800578df  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800578e6  test    rdi, rdi
0x1800578e9  jz      short loc_1800578FD
0x1800578eb  call    cs:__imp_GetLastError
0x1800578f1  lea     rdx, aArchiveregistr; "ArchiveRegistryValue: Failed to write c"...
0x1800578f8  jmp     loc_180057862
0x1800578fd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180057904  jz      loc_180057B17
0x18005790a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180057911  jz      loc_180057B17
0x180057917  call    cs:__imp_GetLastError
0x18005791d  lea     rdx, aArchiveregistr; "ArchiveRegistryValue: Failed to write c"...
0x180057924  jmp     loc_180057891
0x180057929  call    cs:__imp_GetLastError
0x18005792f  mov     ebx, eax
0x180057931  mov     [rbp+var_18], eax
0x180057934  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18005793b  jz      loc_180057B17
0x180057941  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057948  test    rdi, rdi
0x18005794b  jz      short loc_18005795F
0x18005794d  call    cs:__imp_GetLastError
0x180057953  lea     rdx, aArchiveregistr_2; "ArchiveRegistryValue: Failed to write s"...
0x18005795a  jmp     loc_180057862
0x18005795f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180057966  jz      loc_180057B17
0x18005796c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180057973  jz      loc_180057B17
0x180057979  call    cs:__imp_GetLastError
0x18005797f  lea     rdx, aArchiveregistr_2; "ArchiveRegistryValue: Failed to write s"...
0x180057986  jmp     loc_180057891
0x18005798b  call    cs:__imp_GetLastError
0x180057991  mov     ebx, eax
0x180057993  mov     [rbp+var_18], eax
0x180057996  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18005799d  jz      loc_180057B17
0x1800579a3  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800579aa  test    rdi, rdi
0x1800579ad  jz      short loc_1800579C1
0x1800579af  call    cs:__imp_GetLastError
0x1800579b5  lea     rdx, aArchiveregistr_4; "ArchiveRegistryValue: Failed to write d"...
0x1800579bc  jmp     loc_180057862
0x1800579c1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800579c8  jz      loc_180057B17
0x1800579ce  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800579d5  jz      loc_180057B17
0x1800579db  call    cs:__imp_GetLastError
0x1800579e1  lea     rdx, aArchiveregistr_4; "ArchiveRegistryValue: Failed to write d"...
0x1800579e8  jmp     loc_180057891
0x1800579ed  call    cs:__imp_GetLastError
0x1800579f3  mov     ebx, eax
0x1800579f5  mov     [rbp+var_18], eax
0x1800579f8  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800579ff  jz      loc_180057B17
0x180057a05  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057a0c  test    rdi, rdi
0x180057a0f  jz      short loc_180057A23
0x180057a11  call    cs:__imp_GetLastError
0x180057a17  lea     rdx, aArchiveregistr_5; "ArchiveRegistryValue: Failed to write v"...
0x180057a1e  jmp     loc_180057862
0x180057a23  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180057a2a  jz      loc_180057B17
0x180057a30  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180057a37  jz      loc_180057B17
0x180057a3d  call    cs:__imp_GetLastError
0x180057a43  lea     rdx, aArchiveregistr_5; "ArchiveRegistryValue: Failed to write v"...
0x180057a4a  jmp     loc_180057891
0x180057a4f  call    cs:__imp_GetLastError
0x180057a55  mov     ebx, eax
0x180057a57  mov     [rbp+var_18], eax
0x180057a5a  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180057a61  jz      loc_180057B17
0x180057a67  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057a6e  test    rdi, rdi
0x180057a71  jz      short loc_180057A87
0x180057a73  call    cs:__imp_GetLastError
0x180057a79  lea     rdx, aArchiveregistr_3; "ArchiveRegistryValue: Failed to write k"...
0x180057a80  mov     ecx, 2
0x180057a85  jmp     short loc_180057AE0
0x180057a87  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180057a8e  jz      loc_180057B17
0x180057a94  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180057a9b  jz      short loc_180057B17
0x180057a9d  call    cs:__imp_GetLastError
0x180057aa3  lea     rdx, aArchiveregistr_3; "ArchiveRegistryValue: Failed to write k"...
0x180057aaa  mov     ecx, 2
0x180057aaf  jmp     short loc_180057B0E
0x180057ab1  call    cs:__imp_GetLastError
0x180057ab7  mov     ebx, eax
0x180057ab9  mov     [rbp+var_18], eax
0x180057abc  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180057ac3  jz      short loc_180057B17
0x180057ac5  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057acc  test    rdi, rdi
0x180057acf  jz      short loc_180057AED
0x180057ad1  call    cs:__imp_GetLastError
0x180057ad7  lea     rdx, aArchiveregistr_0; "ArchiveRegistryValue: Failed to write o"...
0x180057ade  mov     ecx, esi
0x180057ae0  mov     r8d, eax
0x180057ae3  mov     rax, rdi
0x180057ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aeb  jmp     short loc_180057B17
0x180057aed  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180057af4  jz      short loc_180057B17
0x180057af6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180057afd  jz      short loc_180057B17
0x180057aff  call    cs:__imp_GetLastError
0x180057b05  lea     rdx, aArchiveregistr_0; "ArchiveRegistryValue: Failed to write o"...
0x180057b0c  mov     ecx, esi; unsigned int
0x180057b0e  mov     r8d, eax
0x180057b11  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180057b16  nop
0x180057b17  mov     ecx, ebx; dwErrCode
0x180057b19  call    cs:__imp_SetLastError
0x180057b1f  mov     eax, r12d
0x180057b22  add     rsp, 58h
0x180057b26  pop     r15
0x180057b28  pop     r14
0x180057b2a  pop     r13
0x180057b2c  pop     r12
0x180057b2e  pop     rdi
0x180057b2f  pop     rsi
  ... truncated ...
```
