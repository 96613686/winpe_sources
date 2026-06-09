# GetFileHash(ushort const *,ushort * *)

- ea: `0x180024764`
- end: `0x180024a43`
- name: `?GetFileHash@@YAKPEBGPEAPEAG@Z`
- size: `735`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180024e00`

## callees

- `0x180002300`
- `0x18000d57c`
- `0x180024764`
- `0x1800250b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800247d9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800247d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024869`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024913`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002499d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024869`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024913`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002499d`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x180024839`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x180024839`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x180024859`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x18002488d`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x180024859`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x18002488d`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800248cd`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800248cd`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180024901`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002492e`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180024901`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002492e`

## string_xrefs

- `0x1800247f8`: `Failed to open %ws! Error %d`

## pseudocode

```c
__int64 __fastcall GetFileHash(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 LastError; // rbx
  unsigned __int16 v5; // dx
  unsigned __int16 v6; // cx
  HANDLE FileW; // rsi
  unsigned __int16 v8; // r8
  BYTE *v9; // rdi
  BYTE *v10; // rax
  DWORD v11; // eax
  unsigned __int16 *v12; // rdx
  DWORD v13; // eax
  unsigned __int16 *v14; // rdx
  BYTE *v15; // rax
  unsigned __int16 *v16; // r9
  int v17; // eax
  __int64 i; // r10
  __int64 v19; // r8
  BYTE v20; // dl
  SIZE_T uBytes; // [rsp+40h] [rbp-19h] BYREF
  HCATADMIN hCatAdmin; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v24[2]; // [rsp+50h] [rbp-9h]
  wchar_t v25; // [rsp+70h] [rbp+17h]
  _DWORD v26[4]; // [rsp+78h] [rbp+1Fh] BYREF

  LODWORD(LastError) = 0;
  v26[0] = -145692989;
  *a2 = 0;
  LODWORD(uBytes) = 0;
  hCatAdmin = 0;
  v26[1] = 298924270;
  v26[2] = -1073683067;
  v26[3] = -292175281;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError("GetFileHash", L"Failed to open %ws! Error %d", a1, LastError);
    if ( (_DWORD)LastError )
      return (unsigned int)LastError;
  }
  v9 = 0;
  if ( IsWindowsVersionOrGreater(v6, v5, v8) )
  {
    if ( (unsigned int)CryptCATAdminAcquireContext2(&hCatAdmin, v26, L"SHA256", 0, 0) )
    {
      if ( (unsigned int)CryptCATAdminCalcHashFromFileHandle2(hCatAdmin, FileW, &uBytes, 0, 0) )
      {
        v10 = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v9 = v10;
        if ( v10 )
        {
          if ( !(unsigned int)CryptCATAdminCalcHashFromFileHandle2(hCatAdmin, FileW, &uBytes, v10, 0) )
          {
            v11 = GetLastError();
            v12 = L"CryptCATAdminCalcHashFromFileHandle2 (Hash) failed! Error %d";
LABEL_11:
            LODWORD(LastError) = v11;
            ClassInstallerTelemetry::WriteDbgTraceError("GetFileHash", v12, v11);
          }
        }
        else
        {
          LODWORD(LastError) = 14;
        }
        CryptCATAdminReleaseContext(hCatAdmin, 0);
        goto LABEL_21;
      }
      v11 = GetLastError();
      v12 = L"CryptCATAdminCalcHashFromFileHandle2 (Hash size) failed! Error %d";
      goto LABEL_11;
    }
    v13 = GetLastError();
    v14 = L"CryptCATAdminAcquireContext2 failed! Error %d";
    goto LABEL_14;
  }
  if ( CryptCATAdminCalcHashFromFileHandle(FileW, (DWORD *)&uBytes, 0, 0) )
  {
    v15 = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
    v9 = v15;
    if ( v15 )
    {
      if ( CryptCATAdminCalcHashFromFileHandle(FileW, (DWORD *)&uBytes, v15, 0) )
        goto LABEL_22;
      v13 = GetLastError();
      v14 = L"CryptCATAdminCalcHashFromFileHandle (Hash) failed! Error %d";
LABEL_14:
      LODWORD(LastError) = v13;
      ClassInstallerTelemetry::WriteDbgTraceError("GetFileHash", v14, v13);
      goto LABEL_21;
    }
    LODWORD(LastError) = 14;
  }
  else
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "GetFileHash",
      L"CryptCATAdminCalcHashFromFileHandle (HashSize) failed! Error %d",
      0);
    LODWORD(LastError) = 21;
  }
LABEL_21:
  if ( !(_DWORD)LastError )
  {
LABEL_22:
    v25 = a0123456789abcd[16];
    v24[0] = *(_OWORD *)L"0123456789ABCDEF";
    v24[1] = *(_OWORD *)L"89ABCDEF";
    v16 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(4 * uBytes + 2));
    if ( v16 )
    {
      v17 = uBytes;
      for ( i = 0; (unsigned int)i < (unsigned int)uBytes; v17 = uBytes )
      {
        v19 = (unsigned int)(2 * i);
        v16[v19] = *((_WORD *)v24 + ((unsigned __int64)v9[i] >> 4));
        v20 = v9[i];
        i = (unsigned int)(i + 1);
        v16[(unsigned int)(v19 + 1)] = *((_WORD *)v24 + (v20 & 0xF));
      }
      v16[2 * v17] = 0;
      *a2 = v16;
    }
    else
    {
      LODWORD(LastError) = 14;
    }
  }
  if ( v9 )
    LocalFree(v9);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180024764  mov     [rsp-8+arg_10], rbx
0x180024769  push    rbp
0x18002476a  push    rsi
0x18002476b  push    rdi
0x18002476c  push    r12
0x18002476e  push    r14
0x180024770  lea     rbp, [rsp-37h]
0x180024775  sub     rsp, 90h
0x18002477c  mov     rax, cs:__security_cookie
0x180024783  xor     rax, rsp
0x180024786  mov     [rbp+57h+var_28], rax
0x18002478a  xor     ebx, ebx
0x18002478c  mov     [rbp+57h+var_38], 0F750E6C3h
0x180024793  mov     r14, rdx
0x180024796  mov     [rdx], rbx
0x180024799  mov     [rsp+0B0h+hTemplateFile], rbx; hTemplateFile
0x18002479e  xor     r9d, r9d; lpSecurityAttributes
0x1800247a1  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800247a9  mov     edx, 80000000h; dwDesiredAccess
0x1800247ae  lea     r8d, [rbx+1]; dwShareMode
0x1800247b2  mov     dword ptr [rbp+57h+uBytes], ebx
0x1800247b5  mov     rdi, rcx
0x1800247b8  mov     [rbp+57h+hCatAdmin], rbx
0x1800247bc  mov     [rbp+57h+var_34], 11D138EEh
0x1800247c3  mov     [rbp+57h+var_30], 0C000E585h
0x1800247ca  mov     [rbp+57h+var_2C], 0EE95C24Fh
0x1800247d1  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800247d9  call    cs:__imp_CreateFileW
0x1800247df  lea     r12, aGetfilehash; "GetFileHash"
0x1800247e6  mov     rsi, rax
0x1800247e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800247ed  jnz     short loc_180024814
0x1800247ef  call    cs:__imp_GetLastError
0x1800247f5  mov     r8, rdi
0x1800247f8  lea     rdx, aFailedToOpenWs; "Failed to open %ws! Error %d"
0x1800247ff  mov     r9d, eax
0x180024802  mov     rcx, r12; char *
0x180024805  mov     ebx, eax
0x180024807  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002480c  test    ebx, ebx
0x18002480e  jnz     loc_180024A1E
0x180024814  xor     edi, edi
0x180024816  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18002481b  test    al, al
0x18002481d  jz      loc_1800248F4
0x180024823  xor     r9d, r9d
0x180024826  mov     [rsp+0B0h+dwCreationDisposition], edi
0x18002482a  lea     r8, aSha256; "SHA256"
0x180024831  lea     rdx, [rbp+57h+var_38]
0x180024835  lea     rcx, [rbp+57h+hCatAdmin]
0x180024839  call    cs:__imp_CryptCATAdminAcquireContext2
0x18002483f  test    eax, eax
0x180024841  jz      loc_1800248D8
0x180024847  mov     rcx, [rbp+57h+hCatAdmin]
0x18002484b  lea     r8, [rbp+57h+uBytes]
0x18002484f  xor     r9d, r9d
0x180024852  mov     [rsp+0B0h+dwCreationDisposition], edi
0x180024856  mov     rdx, rsi
0x180024859  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle2
0x18002485f  test    eax, eax
0x180024861  jz      short loc_1800248AD
0x180024863  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180024866  lea     ecx, [rdi+40h]; uFlags
0x180024869  call    cs:__imp_LocalAlloc
0x18002486f  mov     rdi, rax
0x180024872  test    rax, rax
0x180024875  jz      short loc_1800248A6
0x180024877  mov     rcx, [rbp+57h+hCatAdmin]
0x18002487b  lea     r8, [rbp+57h+uBytes]
0x18002487f  mov     r9, rax
0x180024882  mov     [rsp+0B0h+dwCreationDisposition], 0
0x18002488a  mov     rdx, rsi
0x18002488d  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle2
0x180024893  test    eax, eax
0x180024895  jnz     short loc_1800248C7
0x180024897  call    cs:__imp_GetLastError
0x18002489d  lea     rdx, aCryptcatadminc_0; "CryptCATAdminCalcHashFromFileHandle2 (H"...
0x1800248a4  jmp     short loc_1800248BA
0x1800248a6  mov     ebx, 0Eh
0x1800248ab  jmp     short loc_1800248C7
0x1800248ad  call    cs:__imp_GetLastError
0x1800248b3  lea     rdx, aCryptcatadminc_2; "CryptCATAdminCalcHashFromFileHandle2 (H"...
0x1800248ba  mov     r8d, eax
0x1800248bd  mov     rcx, r12; char *
0x1800248c0  mov     ebx, eax
0x1800248c2  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800248c7  mov     rcx, [rbp+57h+hCatAdmin]; hCatAdmin
0x1800248cb  xor     edx, edx; dwFlags
0x1800248cd  call    cs:__imp_CryptCATAdminReleaseContext
0x1800248d3  jmp     loc_180024965
0x1800248d8  call    cs:__imp_GetLastError
0x1800248de  lea     rdx, aCryptcatadmina; "CryptCATAdminAcquireContext2 failed! Er"...
0x1800248e5  mov     r8d, eax
0x1800248e8  mov     rcx, r12; char *
0x1800248eb  mov     ebx, eax
0x1800248ed  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800248f2  jmp     short loc_180024965
0x1800248f4  xor     r9d, r9d; dwFlags
0x1800248f7  lea     rdx, [rbp+57h+uBytes]; pcbHash
0x1800248fb  xor     r8d, r8d; pbHash
0x1800248fe  mov     rcx, rsi; hFile
0x180024901  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180024907  test    eax, eax
0x180024909  jz      short loc_18002494E
0x18002490b  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18002490e  mov     ecx, 40h ; '@'; uFlags
0x180024913  call    cs:__imp_LocalAlloc
0x180024919  mov     rdi, rax
0x18002491c  test    rax, rax
0x18002491f  jz      short loc_180024947
0x180024921  xor     r9d, r9d; dwFlags
0x180024924  lea     rdx, [rbp+57h+uBytes]; pcbHash
0x180024928  mov     r8, rax; pbHash
0x18002492b  mov     rcx, rsi; hFile
0x18002492e  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180024934  test    eax, eax
0x180024936  jnz     short loc_18002496D
0x180024938  call    cs:__imp_GetLastError
0x18002493e  lea     rdx, aCryptcatadminc_1; "CryptCATAdminCalcHashFromFileHandle (Ha"...
0x180024945  jmp     short loc_1800248E5
0x180024947  mov     ebx, 0Eh
0x18002494c  jmp     short loc_180024965
0x18002494e  xor     r8d, r8d
0x180024951  lea     rdx, aCryptcatadminc; "CryptCATAdminCalcHashFromFileHandle (Ha"...
0x180024958  mov     rcx, r12; char *
0x18002495b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024960  mov     ebx, 15h
0x180024965  test    ebx, ebx
0x180024967  jnz     loc_180024A01
0x18002496d  movzx   eax, word ptr cs:a0123456789abcd+20h; ""
0x180024974  mov     ecx, 40h ; '@'; uFlags
0x180024979  movups  xmm0, xmmword ptr cs:a0123456789abcd; "0123456789ABCDEF"
0x180024980  mov     [rbp+57h+var_40], ax
0x180024984  mov     eax, dword ptr [rbp+57h+uBytes]
0x180024987  movups  xmm1, xmmword ptr cs:a0123456789abcd+10h; "89ABCDEF"
0x18002498e  movups  [rbp+57h+var_60], xmm0
0x180024992  lea     edx, ds:2[rax*4]; uBytes
0x180024999  movups  [rbp+57h+var_50], xmm1
0x18002499d  call    cs:__imp_LocalAlloc
0x1800249a3  mov     r9, rax
0x1800249a6  test    rax, rax
0x1800249a9  jz      short loc_1800249FC
0x1800249ab  mov     eax, dword ptr [rbp+57h+uBytes]
0x1800249ae  xor     r10d, r10d
0x1800249b1  test    eax, eax
0x1800249b3  jz      short loc_1800249ED
0x1800249b5  movzx   eax, byte ptr [r10+rdi]
0x1800249ba  lea     r8d, [r10+r10]
0x1800249be  shr     rax, 4
0x1800249c2  lea     ecx, [r8+1]
0x1800249c6  movzx   eax, word ptr [rbp+rax*2+57h+var_60]
0x1800249cb  mov     [r9+r8*2], ax
0x1800249d0  movzx   edx, byte ptr [r10+rdi]
0x1800249d5  inc     r10d
0x1800249d8  and     edx, 0Fh
0x1800249db  movzx   eax, word ptr [rbp+rdx*2+57h+var_60]
0x1800249e0  mov     [r9+rcx*2], ax
0x1800249e5  mov     eax, dword ptr [rbp+57h+uBytes]
0x1800249e8  cmp     r10d, eax
0x1800249eb  jb      short loc_1800249B5
0x1800249ed  lea     ecx, [rax+rax]
0x1800249f0  xor     eax, eax
0x1800249f2  mov     [r9+rcx*2], ax
0x1800249f7  mov     [r14], r9
0x1800249fa  jmp     short loc_180024A01
0x1800249fc  mov     ebx, 0Eh
0x180024a01  test    rdi, rdi
0x180024a04  jz      short loc_180024A0F
0x180024a06  mov     rcx, rdi; hMem
0x180024a09  call    cs:__imp_LocalFree
0x180024a0f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180024a13  jz      short loc_180024A1E
0x180024a15  mov     rcx, rsi; hObject
0x180024a18  call    cs:__imp_CloseHandle
0x180024a1e  mov     eax, ebx
0x180024a20  mov     rcx, [rbp+57h+var_28]
0x180024a24  xor     rcx, rsp; StackCookie
0x180024a27  call    __security_check_cookie
0x180024a2c  mov     rbx, [rsp+0B0h+arg_10]
0x180024a34  add     rsp, 90h
0x180024a3b  pop     r14
0x180024a3d  pop     r12
0x180024a3f  pop     rdi
0x180024a40  pop     rsi
0x180024a41  pop     rbp
0x180024a42  retn
```
