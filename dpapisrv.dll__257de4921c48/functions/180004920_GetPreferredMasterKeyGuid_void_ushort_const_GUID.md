# GetPreferredMasterKeyGuid(void *,ushort const *,_GUID *)

- ea: `0x180004920`
- end: `0x180004c61`
- name: `?GetPreferredMasterKeyGuid@@YAJPEAXPEBGPEAU_GUID@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(_QWORD *, const unsigned __int16 *Src, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180018a20`

## callees

- `0x180004640`
- `0x180004920`
- `0x1800063c0`
- `0x180006510`
- `0x180007f10`
- `0x180008300`
- `0x18001d810`
- `0x18001eb8c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004998`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004998`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180004b06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180004b06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c46`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004b2e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004b6e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004b2e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004b6e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180004ad0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180004ad0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004b1a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004b1a`

## string_xrefs

- `0x1800049d5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180004c14`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall GetPreferredMasterKeyGuid(_QWORD *a1, const unsigned __int16 *Src, struct _GUID *a3)
{
  unsigned int LastError; // r14d
  __int64 FileWithRetries; // rsi
  __int64 v5; // rax
  __int64 v10; // rbx
  WCHAR *v11; // rax
  WCHAR *v12; // r15
  struct _SECURITY_ATTRIBUTES *v13; // r9
  int v14; // ecx
  int v15; // r8d
  unsigned __int64 v17; // rdx
  LONG v18; // eax
  unsigned int v19; // ecx
  int v20; // edx
  DWORD v21; // eax
  _FILETIME FileTime; // [rsp+40h] [rbp-59h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-49h] BYREF
  struct _GUID Buffer; // [rsp+58h] [rbp-41h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp-31h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v28[16]; // [rsp+80h] [rbp-19h] BYREF
  const unsigned __int16 *v29; // [rsp+90h] [rbp-9h]
  __int64 v30; // [rsp+98h] [rbp-1h]
  unsigned int *v31; // [rsp+A0h] [rbp+7h]
  __int64 v32; // [rsp+A8h] [rbp+Fh]

  LastError = 0;
  NumberOfBytesRead = 0;
  FileWithRetries = -1;
  FileTime2 = 0;
  v5 = -1;
  FileTime = 0;
  Buffer = 0;
  SystemTime = 0;
  while ( Src[++v5] != 0 )
    ;
  v10 = (unsigned int)(2 * v5);
  v11 = (WCHAR *)LocalAlloc(0, (unsigned int)(v10 + 18) + 2LL);
  v12 = v11;
  if ( !v11 )
  {
    LastError = 8;
LABEL_12:
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7323);
    return 3221226021LL;
  }
  memcpy_0(v11, Src, (unsigned int)v10);
  *(_OWORD *)((char *)v12 + v10) = *(_OWORD *)L"Preferred";
  *(_DWORD *)((char *)v12 + v10 + 16) = *(_DWORD *)L"d";
  if ( !a1 || (LastError = CPSImpersonateClient(a1)) == 0 )
  {
    FileWithRetries = CreateFileWithRetries(v12, 0x80000000, 1u, v13, 3u, 0x88000006);
    if ( FileWithRetries == -1 )
    {
      LastError = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v20,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          124);
    }
    if ( a1 )
      CPSRevertToSelf(a1);
  }
  LocalFree(v12);
  if ( LastError )
  {
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x10) != 0 )
    {
      v24 = 0x80000000;
      v29 = L"Preferred";
      v30 = 20;
      v31 = &v24;
      v32 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        v14,
        (unsigned int)ETW_LOG_MASTERKEY_FILE_OPEN_IN_STORAGE_FAILED,
        v15,
        3,
        (__int64)v28);
    }
    goto LABEL_12;
  }
  if ( !ReadFile((HANDLE)FileWithRetries, &Buffer, 0x18u, &NumberOfBytesRead, 0) )
  {
    v21 = GetLastError();
    DebugTraceError(v21, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7334);
    CloseHandle((HANDLE)FileWithRetries);
    return 3221226021LL;
  }
  CloseHandle((HANDLE)FileWithRetries);
  if ( NumberOfBytesRead != 24 )
    return 3221226021LL;
  *a3 = Buffer;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( CompareFileTime(&FileTime, &FileTime2) >= 0 )
    return 3221225585LL;
  v17 = FileTime.dwLowDateTime + ((unsigned __int64)FileTime.dwHighDateTime << 32) + 78624000000000LL;
  FileTime.dwLowDateTime += 328679424;
  FileTime.dwHighDateTime = HIDWORD(v17);
  v18 = CompareFileTime(&FileTime, &FileTime2);
  v19 = 0;
  if ( v18 < 0 )
    return (unsigned int)-1073741711;
  return v19;
}

```

## disassembly

```asm
0x180004920  mov     [rsp-8+arg_18], rbx
0x180004925  push    rbp
0x180004926  push    rsi
0x180004927  push    rdi
0x180004928  push    r12
0x18000492a  push    r13
0x18000492c  push    r14
0x18000492e  push    r15
0x180004930  lea     rbp, [rsp-27h]
0x180004935  sub     rsp, 0C0h
0x18000493c  mov     rax, cs:__security_cookie
0x180004943  xor     rax, rsp
0x180004946  mov     [rbp+57h+var_40], rax
0x18000494a  xor     r14d, r14d
0x18000494d  xorps   xmm0, xmm0
0x180004950  xor     eax, eax
0x180004952  mov     [rbp+57h+NumberOfBytesRead], r14d
0x180004956  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000495d  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rax
0x180004961  mov     rax, rsi
0x180004964  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180004968  mov     r12, r8
0x18000496b  mov     rdi, rdx
0x18000496e  mov     r13, rcx
0x180004971  movups  [rbp+57h+Buffer], xmm0
0x180004975  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180004979  nop     dword ptr [rax+00000000h]
0x180004980  cmp     [rdx+rax*2+2], r14w
0x180004986  lea     rax, [rax+1]
0x18000498a  jnz     short loc_180004980
0x18000498c  lea     ebx, [rax+rax]
0x18000498f  xor     ecx, ecx; uFlags
0x180004991  lea     edx, [rbx+12h]
0x180004994  add     rdx, 2; uBytes
0x180004998  call    cs:__imp_LocalAlloc
0x18000499f  nop     dword ptr [rax+rax+00h]
0x1800049a4  mov     r15, rax
0x1800049a7  test    rax, rax
0x1800049aa  jz      loc_180004C0E
0x1800049b0  mov     r8d, ebx; Size
0x1800049b3  mov     rdx, rdi; Src
0x1800049b6  mov     rcx, rax; void *
0x1800049b9  call    memcpy_0
0x1800049be  movups  xmm0, xmmword ptr cs:aPreferred; "Preferred"
0x1800049c5  movups  xmmword ptr [rbx+r15], xmm0
0x1800049ca  mov     eax, dword ptr cs:aPreferred+10h; "d"
0x1800049d0  mov     [rbx+r15+10h], eax
0x1800049d5  lea     rbx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800049dc  test    r13, r13
0x1800049df  jnz     short loc_180004A20
0x1800049e1  mov     [rsp+0F0h+var_C8], 88000006h; unsigned int
0x1800049e9  mov     edx, 80000000h; dwDesiredAccess
0x1800049ee  mov     r8d, 1; dwShareMode
0x1800049f4  mov     dword ptr [rsp+0F0h+lpOverlapped], 3; DWORD
0x1800049fc  mov     rcx, r15; lpFileName
0x1800049ff  call    ?CreateFileWithRetries@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CreateFileWithRetries(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180004a04  mov     rsi, rax
0x180004a07  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004a0b  jz      loc_180004BB0
0x180004a11  test    r13, r13
0x180004a14  jz      short loc_180004A2F
0x180004a16  mov     rcx, r13; void *
0x180004a19  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180004a1e  jmp     short loc_180004A2F
0x180004a20  mov     rcx, r13; void *
0x180004a23  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180004a28  mov     r14d, eax
0x180004a2b  test    eax, eax
0x180004a2d  jz      short loc_1800049E1
0x180004a2f  mov     rcx, r15; hMem
0x180004a32  call    cs:__imp_LocalFree
0x180004a39  nop     dword ptr [rax+rax+00h]
0x180004a3e  test    r14d, r14d
0x180004a41  jz      short loc_180004AB8
0x180004a43  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 10h
0x180004a4a  jz      short loc_180004AB3
0x180004a4c  lea     rax, aPreferred; "Preferred"
0x180004a53  mov     [rbp+57h+var_A0], 80000000h
0x180004a5a  mov     [rbp+57h+var_60], rax
0x180004a5e  lea     rdx, ETW_LOG_MASTERKEY_FILE_OPEN_IN_STORAGE_FAILED
0x180004a65  lea     rax, [rbp+57h+var_A0]
0x180004a69  mov     [rbp+57h+var_58], 14h
0x180004a71  mov     [rbp+57h+var_50], rax
0x180004a75  mov     r9d, 3
0x180004a7b  lea     rax, [rbp+57h+var_70]
0x180004a7f  mov     [rbp+57h+var_48], 4
0x180004a87  mov     [rsp+0F0h+lpOverlapped], rax
0x180004a8c  call    McGenEventWrite_EtwEventWriteTransfer
0x180004a91  mov     r9d, 1C9Bh
0x180004a97  lea     rdx, aDwlasterror; "dwLastError"
0x180004a9e  mov     r8, rbx
0x180004aa1  mov     ecx, r14d
0x180004aa4  call    DebugTraceError
0x180004aa9  mov     eax, 0C0000225h
0x180004aae  jmp     loc_180004B88
0x180004ab3  test    r14d, r14d
0x180004ab6  jnz     short loc_180004A91
0x180004ab8  xor     edi, edi
0x180004aba  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180004abe  mov     r8d, 18h; nNumberOfBytesToRead
0x180004ac4  mov     [rsp+0F0h+lpOverlapped], rdi; lpOverlapped
0x180004ac9  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180004acd  mov     rcx, rsi; hFile
0x180004ad0  call    cs:__imp_ReadFile
0x180004ad7  nop     dword ptr [rax+rax+00h]
0x180004adc  test    eax, eax
0x180004ade  jz      loc_180004C20
0x180004ae4  mov     rcx, rsi; hObject
0x180004ae7  call    cs:__imp_CloseHandle
0x180004aee  nop     dword ptr [rax+rax+00h]
0x180004af3  cmp     [rbp+57h+NumberOfBytesRead], 18h
0x180004af7  jnz     short loc_180004AA9
0x180004af9  movups  xmm0, [rbp+57h+Buffer]
0x180004afd  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180004b01  movups  xmmword ptr [r12], xmm0
0x180004b06  call    cs:__imp_GetSystemTime
0x180004b0d  nop     dword ptr [rax+rax+00h]
0x180004b12  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180004b16  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180004b1a  call    cs:__imp_SystemTimeToFileTime
0x180004b21  nop     dword ptr [rax+rax+00h]
0x180004b26  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180004b2a  lea     rcx, [rbp+57h+FileTime]; lpFileTime1
0x180004b2e  call    cs:__imp_CompareFileTime
0x180004b35  nop     dword ptr [rax+rax+00h]
0x180004b3a  test    eax, eax
0x180004b3c  jns     loc_180004C57
0x180004b42  mov     ecx, [rbp+57h+FileTime.dwLowDateTime]
0x180004b45  mov     rdx, 478213974000h
0x180004b4f  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x180004b52  shl     rax, 20h
0x180004b56  add     rdx, rax
0x180004b59  add     rdx, rcx
0x180004b5c  lea     rcx, [rbp+57h+FileTime]; lpFileTime1
0x180004b60  mov     [rbp+57h+FileTime.dwLowDateTime], edx
0x180004b63  shr     rdx, 20h
0x180004b67  mov     [rbp+57h+FileTime.dwHighDateTime], edx
0x180004b6a  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180004b6e  call    cs:__imp_CompareFileTime
0x180004b75  nop     dword ptr [rax+rax+00h]
0x180004b7a  mov     ecx, edi
0x180004b7c  mov     edx, 0C0000071h
0x180004b81  test    eax, eax
0x180004b83  cmovs   ecx, edx
0x180004b86  mov     eax, ecx
0x180004b88  mov     rcx, [rbp+57h+var_40]
0x180004b8c  xor     rcx, rsp; StackCookie
0x180004b8f  call    __security_check_cookie
0x180004b94  mov     rbx, [rsp+0F0h+arg_18]
0x180004b9c  add     rsp, 0C0h
0x180004ba3  pop     r15
0x180004ba5  pop     r14
0x180004ba7  pop     r13
0x180004ba9  pop     r12
0x180004bab  pop     rdi
0x180004bac  pop     rsi
0x180004bad  pop     rbp
0x180004bae  retn
0x180004bb0  call    cs:__imp_GetLastError
0x180004bb7  nop     dword ptr [rax+rax+00h]
0x180004bbc  mov     r14d, eax
0x180004bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bc6  lea     rax, WPP_GLOBAL_Control
0x180004bcd  cmp     rcx, rax
0x180004bd0  jz      loc_180004A11
0x180004bd6  test    byte ptr [rcx+1Ch], 1
0x180004bda  jz      loc_180004A11
0x180004be0  mov     rcx, [rcx+10h]
0x180004be4  lea     r9, aDwlasterror; "dwLastError"
0x180004beb  mov     [rsp+0F0h+var_C0], 1D7Ch
0x180004bf3  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180004bfa  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x180004bff  mov     dword ptr [rsp+0F0h+lpOverlapped], r14d
0x180004c04  call    WPP_SF_sDsd
0x180004c09  jmp     loc_180004A11
0x180004c0e  mov     r14d, 8
0x180004c14  lea     rbx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180004c1b  jmp     loc_180004A91
0x180004c20  call    cs:__imp_GetLastError
0x180004c27  nop     dword ptr [rax+rax+00h]
0x180004c2c  mov     r9d, 1CA6h
0x180004c32  lea     rdx, aGetlasterror; "GetLastError()"
0x180004c39  mov     ecx, eax
0x180004c3b  mov     r8, rbx
0x180004c3e  call    DebugTraceError
0x180004c43  mov     rcx, rsi; hObject
0x180004c46  call    cs:__imp_CloseHandle
0x180004c4d  nop     dword ptr [rax+rax+00h]
0x180004c52  jmp     loc_180004AA9
0x180004c57  mov     eax, 0C0000071h
0x180004c5c  jmp     loc_180004B88
```
