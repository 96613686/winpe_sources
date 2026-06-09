# Win32LiveSystemProvider::VerifyModuleIsTrusted(ushort const *,void * *)

- ea: `0x180016198`
- end: `0x180016430`
- name: `?VerifyModuleIsTrusted@Win32LiveSystemProvider@@IEAAJPEBGPEAPEAX@Z`
- size: `664`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011430`
- `0x180023560`

## callees

- `0x180002170`
- `0x180014b0c`
- `0x180014d78`
- `0x180016198`
- `0x180016438`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800162e5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800162e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163dc`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x180016362`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x180016362`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800163a8`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800163a8`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x180016396`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x180016396`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016283`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016283`

## string_xrefs

- `0x18001630a`: `mscordaccore.dll`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::VerifyModuleIsTrusted(
        __int64 (__fastcall **this)(const unsigned __int16 *, int *),
        const unsigned __int16 *a2,
        void **a3)
{
  __int64 result; // rax
  signed int v7; // ebx
  __int64 (__fastcall *v8)(const unsigned __int16 *, int *); // rax
  unsigned int v9; // eax
  unsigned int v10; // r15d
  signed int LastError; // eax
  __int64 v12; // r12
  HANDLE FileW; // rsi
  wchar_t *v14; // rax
  signed int v15; // eax
  int v16; // [rsp+40h] [rbp-28h] BYREF
  int v17; // [rsp+44h] [rbp-24h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-20h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-10h] BYREF
  int Data; // [rsp+C8h] [rbp+60h] BYREF

  result = Win32LiveSystemProvider::LoadVersion((Win32LiveSystemProvider *)this);
  v7 = result;
  if ( !(_DWORD)result )
  {
    v8 = this[68];
    if ( v8 && this[70] && this[71] )
    {
      v16 = 0;
      v9 = v8(a2, &v16);
      v10 = v9;
      if ( !v9 )
        goto LABEL_6;
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)this[6] + 8LL))(this[6], v9);
      if ( !v12 )
        return 2147942414LL;
      String2 = 0;
      v17 = 0;
      FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
LABEL_6:
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          return (unsigned int)-2147467259;
        }
        return (unsigned int)v7;
      }
      if ( ((unsigned int (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD, __int64))this[70])(a2, 0, v10, v12)
        && ((unsigned int (__fastcall *)(__int64, const wchar_t *, wchar_t **, int *))this[72])(
             v12,
             L"\\StringFileInfo\\040904b0\\OriginalFilename",
             &String2,
             &v17) )
      {
        v14 = wcsrchr(a2, 0x5Cu);
        if ( !String2 || !wcsicmp(v14 + 1, String2) || !String2 || !wcsicmp(L"mscordaccore.dll", String2) )
        {
LABEL_21:
          (*(void (__fastcall **)(__int64 (__fastcall *)(const unsigned __int16 *, int *), __int64))(*(_QWORD *)this[6] + 24LL))(
            this[6],
            v12);
          if ( v7 < 0 )
            goto LABEL_30;
          phkResult = 0;
          Data = 0;
          if ( !RegOpenKeyExA(
                  HKEY_LOCAL_MACHINE,
                  "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\MiniDumpSettings",
                  0,
                  0x20019u,
                  &phkResult) )
          {
            cbData = 4;
            if ( RegQueryValueExA(phkResult, "DisableAuxProviderSignatureCheck", 0, 0, (LPBYTE)&Data, &cbData) )
              Data = 0;
            RegCloseKey(phkResult);
          }
          if ( !Data )
          {
            v7 = Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature((Win32LiveSystemProvider *)this, a2);
            if ( v7 == -2147467263 )
              v7 = Win32LiveSystemProvider::NtVerifyMicrosoftSignature((Win32LiveSystemProvider *)this, FileW);
            if ( v7 < 0 )
            {
LABEL_30:
              CloseHandle(FileW);
              FileW = 0;
            }
          }
          *a3 = FileW;
          return (unsigned int)v7;
        }
      }
      else if ( GetLastError() )
      {
        v15 = GetLastError();
        v7 = v15;
        if ( v15 > 0 )
          v7 = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_21;
      }
      v7 = -2147467259;
      goto LABEL_21;
    }
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x180016198  push    rbp
0x18001619a  push    rbx
0x18001619b  push    rsi
0x18001619c  push    rdi
0x18001619d  push    r12
0x18001619f  push    r13
0x1800161a1  push    r14
0x1800161a3  push    r15
0x1800161a5  mov     rbp, rsp
0x1800161a8  sub     rsp, 68h
0x1800161ac  mov     r13, r8
0x1800161af  mov     r14, rdx
0x1800161b2  mov     rdi, rcx
0x1800161b5  call    ?LoadVersion@Win32LiveSystemProvider@@IEAAJXZ; Win32LiveSystemProvider::LoadVersion(void)
0x1800161ba  xor     esi, esi
0x1800161bc  mov     ebx, eax
0x1800161be  test    eax, eax
0x1800161c0  jnz     loc_18001641F
0x1800161c6  mov     rax, [rdi+220h]
0x1800161cd  test    rax, rax
0x1800161d0  jz      loc_18001641A
0x1800161d6  cmp     [rdi+230h], rsi
0x1800161dd  jz      loc_18001641A
0x1800161e3  cmp     [rdi+238h], rsi
0x1800161ea  jz      loc_18001641A
0x1800161f0  lea     rdx, [rbp+var_28]
0x1800161f4  mov     [rbp+var_28], esi
0x1800161f7  mov     rcx, r14
0x1800161fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161ff  mov     r15d, eax
0x180016202  test    eax, eax
0x180016204  jnz     short loc_180016233
0x180016206  call    cs:__imp_GetLastError
0x18001620c  test    eax, eax
0x18001620e  jz      short loc_180016227
0x180016210  call    cs:__imp_GetLastError
0x180016216  mov     ebx, eax
0x180016218  test    eax, eax
0x18001621a  jle     short loc_18001622C
0x18001621c  movzx   ebx, ax
0x18001621f  or      ebx, 80070000h
0x180016225  jmp     short loc_18001622C
0x180016227  mov     ebx, 80004005h
0x18001622c  mov     eax, ebx
0x18001622e  jmp     loc_18001641F
0x180016233  mov     rcx, [rdi+30h]
0x180016237  mov     edx, r15d
0x18001623a  mov     rax, [rcx]
0x18001623d  mov     rax, [rax+8]
0x180016241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016246  mov     r12, rax
0x180016249  test    rax, rax
0x18001624c  jnz     short loc_180016258
0x18001624e  mov     eax, 8007000Eh
0x180016253  jmp     loc_18001641F
0x180016258  xor     r9d, r9d; lpSecurityAttributes
0x18001625b  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x180016260  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016268  mov     edx, 80000000h; dwDesiredAccess
0x18001626d  mov     rcx, r14; lpFileName
0x180016270  mov     [rbp+String2], rsi
0x180016274  mov     [rbp+var_24], esi
0x180016277  lea     r8d, [r9+1]; dwShareMode
0x18001627b  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180016283  call    cs:__imp_CreateFileW
0x180016289  mov     rsi, rax
0x18001628c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016290  jz      loc_180016206
0x180016296  mov     rax, [rdi+230h]
0x18001629d  mov     r9, r12
0x1800162a0  mov     r8d, r15d
0x1800162a3  xor     edx, edx
0x1800162a5  mov     rcx, r14
0x1800162a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ad  xor     r15d, r15d
0x1800162b0  test    eax, eax
0x1800162b2  jz      loc_1800163EE
0x1800162b8  mov     rax, [rdi+240h]
0x1800162bf  lea     r9, [rbp+var_24]
0x1800162c3  lea     r8, [rbp+String2]
0x1800162c7  mov     rcx, r12
0x1800162ca  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904b0\\OriginalFil"...
0x1800162d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d6  test    eax, eax
0x1800162d8  jz      loc_1800163EE
0x1800162de  lea     edx, [r15+5Ch]; Ch
0x1800162e2  mov     rcx, r14; Str
0x1800162e5  call    cs:__imp_wcsrchr
0x1800162eb  mov     rdx, [rbp+String2]; String2
0x1800162ef  test    rdx, rdx
0x1800162f2  jz      short loc_18001631F
0x1800162f4  lea     rcx, [rax+2]; String1
0x1800162f8  call    _wcsicmp
0x1800162fd  test    eax, eax
0x1800162ff  jz      short loc_18001631F
0x180016301  mov     rdx, [rbp+String2]; String2
0x180016305  test    rdx, rdx
0x180016308  jz      short loc_18001631F
0x18001630a  lea     rcx, aMscordaccoreDl; "mscordaccore.dll"
0x180016311  call    _wcsicmp
0x180016316  test    eax, eax
0x180016318  jz      short loc_18001631F
0x18001631a  mov     ebx, 80004005h
0x18001631f  mov     rcx, [rdi+30h]
0x180016323  mov     rdx, r12
0x180016326  mov     rax, [rcx]
0x180016329  mov     rax, [rax+18h]
0x18001632d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016332  test    ebx, ebx
0x180016334  js      loc_1800163D9
0x18001633a  lea     rax, [rbp+phkResult]
0x18001633e  mov     [rbp+phkResult], r15
0x180016342  mov     r9d, 20019h; samDesired
0x180016348  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; phkResult
0x18001634d  xor     r8d, r8d; ulOptions
0x180016350  mov     [rbp+Data], r15d
0x180016354  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001635b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016362  call    cs:__imp_RegOpenKeyExA
0x180016368  test    eax, eax
0x18001636a  jnz     short loc_1800163AE
0x18001636c  mov     rcx, [rbp+phkResult]; hKey
0x180016370  lea     rax, [rbp+cbData]
0x180016374  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rax; lpcbData
0x180016379  lea     rdx, aDisableauxprov; "DisableAuxProviderSignatureCheck"
0x180016380  lea     rax, [rbp+Data]
0x180016384  mov     [rbp+cbData], 4
0x18001638b  xor     r9d, r9d; lpType
0x18001638e  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; lpData
0x180016393  xor     r8d, r8d; lpReserved
0x180016396  call    cs:__imp_RegQueryValueExA
0x18001639c  test    eax, eax
0x18001639e  jz      short loc_1800163A4
0x1800163a0  mov     [rbp+Data], r15d
0x1800163a4  mov     rcx, [rbp+phkResult]; hKey
0x1800163a8  call    cs:__imp_RegCloseKey
0x1800163ae  cmp     [rbp+Data], r15d
0x1800163b2  jnz     short loc_1800163E5
0x1800163b4  mov     rdx, r14; unsigned __int16 *
0x1800163b7  mov     rcx, rdi; this
0x1800163ba  call    ?WintrustVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEBG@Z; Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature(ushort const *)
0x1800163bf  mov     ebx, eax
0x1800163c1  cmp     eax, 80004001h
0x1800163c6  jnz     short loc_1800163D5
0x1800163c8  mov     rdx, rsi; void *
0x1800163cb  mov     rcx, rdi; this
0x1800163ce  call    ?NtVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEAX@Z; Win32LiveSystemProvider::NtVerifyMicrosoftSignature(void *)
0x1800163d3  mov     ebx, eax
0x1800163d5  test    ebx, ebx
0x1800163d7  jns     short loc_1800163E5
0x1800163d9  mov     rcx, rsi; hObject
0x1800163dc  call    cs:__imp_CloseHandle
0x1800163e2  mov     rsi, r15
0x1800163e5  mov     [r13+0], rsi
0x1800163e9  jmp     loc_18001622C
0x1800163ee  call    cs:__imp_GetLastError
0x1800163f4  test    eax, eax
0x1800163f6  jz      loc_18001631A
0x1800163fc  call    cs:__imp_GetLastError
0x180016402  mov     ebx, eax
0x180016404  test    eax, eax
0x180016406  jle     loc_18001631F
0x18001640c  movzx   ebx, ax
0x18001640f  or      ebx, 80070000h
0x180016415  jmp     loc_18001631F
0x18001641a  mov     eax, 80004001h
0x18001641f  add     rsp, 68h
0x180016423  pop     r15
0x180016425  pop     r14
0x180016427  pop     r13
0x180016429  pop     r12
0x18001642b  pop     rdi
0x18001642c  pop     rsi
0x18001642d  pop     rbx
0x18001642e  pop     rbp
0x18001642f  retn
```
