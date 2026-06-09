# LegacyVerifyFileSignature(ushort const *,ushort const *)

- ea: `0x180037b98`
- end: `0x180037dd8`
- name: `?LegacyVerifyFileSignature@@YAHPEBG0@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180037098`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18001c660`
- `0x180037af4`
- `0x180037b98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037da8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037bf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037bf0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037ce9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037ce9`
- `WINTRUST!WinVerifyTrust` at `0x180037c7e`
- `WINTRUST!WinVerifyTrust` at `0x180037d62`
- `WINTRUST!WinVerifyTrust` at `0x180037d97`
- `WINTRUST!WinVerifyTrust` at `0x180037c7e`
- `WINTRUST!WinVerifyTrust` at `0x180037d62`
- `WINTRUST!WinVerifyTrust` at `0x180037d97`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180037cc7`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180037d05`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180037cc7`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180037d05`

## pseudocode

```c
_BOOL8 __fastcall LegacyVerifyFileSignature(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  BOOL v2; // esi
  HANDLE FileW; // rdi
  BYTE *v6; // rax
  BYTE *v7; // rbx
  DWORD LastError; // eax
  DWORD v9; // ebx
  DWORD pcbHash[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WINTRUST_DATA pWVTData; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v13[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v14; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v15; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v16; // [rsp+E8h] [rbp-18h]
  HANDLE v17; // [rsp+F0h] [rbp-10h]
  BYTE *v18; // [rsp+F8h] [rbp-8h]
  DWORD v19; // [rsp+100h] [rbp+0h]
  GUID pgActionID; // [rsp+120h] [rbp+20h] BYREF

  v2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    memset_0(&pWVTData, 0, 0x58u);
    pgActionID.Data1 = 11191659;
    *(_DWORD *)&pgActionID.Data2 = 298896708;
    *(_DWORD *)pgActionID.Data4 = -1073692020;
    *(_DWORD *)&pgActionID.Data4[4] = -292175281;
    if ( a2 )
    {
      pcbHash[0] = 0;
      memset_0(&v14, 0, 0x48u);
      if ( CryptCATAdminCalcHashFromFileHandle(FileW, pcbHash, 0, 0) || GetLastError() == 122 )
      {
        v6 = (BYTE *)LocalAlloc(0x40u, pcbHash[0]);
        v7 = v6;
        if ( v6 )
        {
          if ( CryptCATAdminCalcHashFromFileHandle(FileW, pcbHash, v6, 0) )
          {
            v19 = pcbHash[0];
            v14 = 72;
            pWVTData.pFile = (struct WINTRUST_FILE_INFO_ *)&v14;
            v15 = a2;
            v16 = a1;
            v17 = FileW;
            v18 = v7;
            pWVTData.cbStruct = 88;
            *(_QWORD *)&pWVTData.dwUIChoice = 2;
            pWVTData.dwUnionChoice = 2;
            pWVTData.dwStateAction = 1;
            pWVTData.dwUIContext = 1;
            if ( !WinVerifyTrust(0, &pgActionID, &pWVTData) )
              v2 = 1;
          }
          DllFreeSplMem(v7);
        }
      }
    }
    else
    {
      v13[0] = 32;
      pWVTData.pFile = (struct WINTRUST_FILE_INFO_ *)v13;
      v13[3] = 0;
      v13[1] = a1;
      v13[2] = FileW;
      pWVTData.cbStruct = 88;
      pWVTData.dwUIChoice = 2;
      pWVTData.dwUnionChoice = 1;
      pWVTData.dwStateAction = 1;
      pWVTData.dwProvFlags = 4224;
      pWVTData.dwUIContext = 1;
      if ( !WinVerifyTrust(0, &pgActionID, &pWVTData) )
        v2 = IsCertificateTrusted(&pWVTData) != 0;
    }
    if ( pWVTData.hWVTStateData )
    {
      LastError = GetLastError();
      pWVTData.dwStateAction = 2;
      v9 = LastError;
      WinVerifyTrust(0, &pgActionID, &pWVTData);
      SetLastError(v9);
    }
    CloseHandle(FileW);
  }
  return v2;
}

```

## disassembly

```asm
0x180037b98  mov     [rsp-8+arg_10], rbx
0x180037b9d  mov     [rsp-8+arg_18], rsi
0x180037ba2  push    rbp
0x180037ba3  push    rdi
0x180037ba4  push    r13
0x180037ba6  push    r14
0x180037ba8  push    r15
0x180037baa  lea     rbp, [rsp-40h]
0x180037baf  sub     rsp, 140h
0x180037bb6  mov     rax, cs:__security_cookie
0x180037bbd  xor     rax, rsp
0x180037bc0  mov     [rbp+60h+var_30], rax
0x180037bc4  xor     esi, esi
0x180037bc6  mov     r15, rdx
0x180037bc9  mov     [rsp+160h+hTemplateFile], rsi; hTemplateFile
0x180037bce  xor     r9d, r9d; lpSecurityAttributes
0x180037bd1  mov     [rsp+160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180037bd9  mov     edx, 80000000h; dwDesiredAccess
0x180037bde  mov     r14, rcx
0x180037be1  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x180037be9  lea     r13d, [rsi+1]
0x180037bed  mov     r8d, r13d; dwShareMode
0x180037bf0  call    cs:__imp_CreateFileW
0x180037bf6  mov     rdi, rax
0x180037bf9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037bfd  jz      loc_180037DAE
0x180037c03  lea     ebx, [rsi+58h]
0x180037c06  xor     edx, edx; Val
0x180037c08  mov     r8d, ebx; Size
0x180037c0b  lea     rcx, [rsp+160h+pWVTData]; void *
0x180037c10  call    memset_0
0x180037c15  mov     [rbp+60h+pgActionID.Data1], 0AAC56Bh
0x180037c1c  mov     dword ptr [rbp+60h+pgActionID.Data2], 11D0CD44h
0x180037c23  mov     dword ptr [rbp+60h+pgActionID.Data4], 0C000C28Ch
0x180037c2a  mov     dword ptr [rbp+60h+pgActionID.Data4+4], 0EE95C24Fh
0x180037c31  test    r15, r15
0x180037c34  jnz     short loc_180037CA6
0x180037c36  lea     rax, [rbp+60h+var_B0]
0x180037c3a  mov     [rbp+60h+var_B0], 20h ; ' '
0x180037c42  lea     r8, [rsp+160h+pWVTData]; pWVTData
0x180037c47  mov     [rsp+160h+var_E8], rax
0x180037c4c  lea     rdx, [rbp+60h+pgActionID]; pgActionID
0x180037c50  mov     [rbp+60h+var_98], rsi
0x180037c54  xor     ecx, ecx; hwnd
0x180037c56  mov     [rbp+60h+var_A8], r14
0x180037c5a  mov     [rbp+60h+var_A0], rdi
0x180037c5e  mov     [rsp+160h+pWVTData], ebx
0x180037c62  mov     dword ptr [rsp+160h+var_F8], 2
0x180037c6a  mov     [rsp+160h+var_F0], r13d
0x180037c6f  mov     [rbp+60h+var_E0], r13d
0x180037c73  mov     [rbp+60h+var_C8], 1080h
0x180037c7a  mov     [rbp+60h+var_C4], r13d
0x180037c7e  call    cs:__imp_WinVerifyTrust
0x180037c84  test    eax, eax
0x180037c86  jnz     loc_180037D76
0x180037c8c  lea     rcx, [rsp+160h+pWVTData]; struct _WINTRUST_DATA *
0x180037c91  call    ?IsCertificateTrusted@@YAHPEAU_WINTRUST_DATA@@@Z; IsCertificateTrusted(_WINTRUST_DATA *)
0x180037c96  test    eax, eax
0x180037c98  jz      loc_180037D76
0x180037c9e  mov     esi, r13d
0x180037ca1  jmp     loc_180037D76
0x180037ca6  xor     edx, edx; Val
0x180037ca8  mov     [rsp+160h+pcbHash], esi
0x180037cac  lea     rcx, [rbp+60h+var_90]; void *
0x180037cb0  lea     r8d, [rdx+48h]; Size
0x180037cb4  call    memset_0
0x180037cb9  xor     r9d, r9d; dwFlags
0x180037cbc  lea     rdx, [rsp+160h+pcbHash]; pcbHash
0x180037cc1  xor     r8d, r8d; pbHash
0x180037cc4  mov     rcx, rdi; hFile
0x180037cc7  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180037ccd  test    eax, eax
0x180037ccf  jnz     short loc_180037CE0
0x180037cd1  call    cs:__imp_GetLastError
0x180037cd7  cmp     eax, 7Ah ; 'z'
0x180037cda  jnz     loc_180037D76
0x180037ce0  mov     edx, [rsp+160h+pcbHash]; uBytes
0x180037ce4  mov     ecx, 40h ; '@'; uFlags
0x180037ce9  call    cs:__imp_LocalAlloc
0x180037cef  mov     rbx, rax
0x180037cf2  test    rax, rax
0x180037cf5  jz      short loc_180037D76
0x180037cf7  xor     r9d, r9d; dwFlags
0x180037cfa  lea     rdx, [rsp+160h+pcbHash]; pcbHash
0x180037cff  mov     r8, rax; pbHash
0x180037d02  mov     rcx, rdi; hFile
0x180037d05  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180037d0b  test    eax, eax
0x180037d0d  jz      short loc_180037D6E
0x180037d0f  mov     eax, [rsp+160h+pcbHash]
0x180037d13  lea     r8, [rsp+160h+pWVTData]; pWVTData
0x180037d18  mov     [rbp+60h+var_60], eax
0x180037d1b  lea     rdx, [rbp+60h+pgActionID]; pgActionID
0x180037d1f  lea     rax, [rbp+60h+var_90]
0x180037d23  mov     [rbp+60h+var_90], 48h ; 'H'
0x180037d2a  xor     ecx, ecx; hwnd
0x180037d2c  mov     [rsp+160h+var_E8], rax
0x180037d31  mov     [rbp+60h+var_88], r15
0x180037d35  mov     [rbp+60h+var_78], r14
0x180037d39  mov     [rbp+60h+var_70], rdi
0x180037d3d  mov     [rbp+60h+var_68], rbx
0x180037d41  mov     [rsp+160h+pWVTData], 58h ; 'X'
0x180037d49  mov     [rsp+160h+var_F8], 2
0x180037d52  mov     [rsp+160h+var_F0], 2
0x180037d5a  mov     [rbp+60h+var_E0], r13d
0x180037d5e  mov     [rbp+60h+var_C4], r13d
0x180037d62  call    cs:__imp_WinVerifyTrust
0x180037d68  test    eax, eax
0x180037d6a  cmovz   esi, r13d
0x180037d6e  mov     rcx, rbx
0x180037d71  call    DllFreeSplMem
0x180037d76  cmp     [rbp+60h+var_D8], 0
0x180037d7b  jz      short loc_180037DA5
0x180037d7d  call    cs:__imp_GetLastError
0x180037d83  lea     r8, [rsp+160h+pWVTData]; pWVTData
0x180037d88  mov     [rbp+60h+var_E0], 2
0x180037d8f  lea     rdx, [rbp+60h+pgActionID]; pgActionID
0x180037d93  xor     ecx, ecx; hwnd
0x180037d95  mov     ebx, eax
0x180037d97  call    cs:__imp_WinVerifyTrust
0x180037d9d  mov     ecx, ebx; dwErrCode
0x180037d9f  call    cs:__imp_SetLastError
0x180037da5  mov     rcx, rdi; hObject
0x180037da8  call    cs:__imp_CloseHandle
0x180037dae  mov     eax, esi
0x180037db0  mov     rcx, [rbp+60h+var_30]
0x180037db4  xor     rcx, rsp; StackCookie
0x180037db7  call    __security_check_cookie
0x180037dbc  lea     r11, [rsp+160h+var_20]
0x180037dc4  mov     rbx, [r11+40h]
0x180037dc8  mov     rsi, [r11+48h]
0x180037dcc  mov     rsp, r11
0x180037dcf  pop     r15
0x180037dd1  pop     r14
0x180037dd3  pop     r13
0x180037dd5  pop     rdi
0x180037dd6  pop     rbp
0x180037dd7  retn
```
