# OpenXpsUtility::ShouldForceOXPS(void *)

- ea: `0x14005becc`
- end: `0x14005c01d`
- name: `?ShouldForceOXPS@OpenXpsUtility@@YA_NPEAX@Z`
- size: `337`
- prototype: `bool __fastcall(HANDLE hPrinter, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14005b1f0`

## callees

- `0x140002440`
- `0x14000d494`
- `0x14000fb5c`
- `0x14005becc`
- `0x140063010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14005bf1f`
- `KERNEL32!FreeLibrary` at `0x14005bf1f`
- `KERNEL32!GetLastError` at `0x14005bf5e`
- `KERNEL32!GetLastError` at `0x14005bf5e`
- `KERNEL32!GetProcAddress` at `0x14005bf0a`
- `KERNEL32!GetProcAddress` at `0x14005bf0a`
- `KERNEL32!LoadLibraryExW` at `0x14005beea`
- `KERNEL32!LoadLibraryExW` at `0x14005beea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005bfe9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005bfe9`
- `WINSPOOL!GetPrinterDriverW` at `0x14005bf50`
- `WINSPOOL!GetPrinterDriverW` at `0x14005bfb2`
- `WINSPOOL!GetPrinterDriverW` at `0x14005bf50`
- `WINSPOOL!GetPrinterDriverW` at `0x14005bfb2`

## string_xrefs

- `0x14005bedd`: `ext-ms-win32-subsystem-query-l1-1-0.dll`
- `0x14005bfe2`: `tsprint.dll`

## pseudocode

```c
char __fastcall OpenXpsUtility::ShouldForceOXPS(HANDLE hPrinter, void *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  int v5; // edi
  __int64 (*ProcAddress)(void); // rax
  char v7; // bl
  void *v8; // rax
  LPBYTE v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  DWORD pcbNeeded; // [rsp+58h] [rbp+10h] BYREF
  LPBYTE pDriverInfo; // [rsp+60h] [rbp+18h] BYREF

  Library = LoadLibraryExW(L"ext-ms-win32-subsystem-query-l1-1-0.dll", 0, 0x800u);
  v4 = Library;
  if ( !Library )
    return 0;
  v5 = 0;
  ProcAddress = GetProcAddress(Library, "QueryWin32SubsystemHost");
  if ( ProcAddress )
    v5 = ProcAddress();
  FreeLibrary(v4);
  v7 = 1;
  if ( v5 != 1 )
    return 0;
  pcbNeeded = 0;
  if ( GetPrinterDriverW(hPrinter, 0, 2u, 0, 0, &pcbNeeded) || GetLastError() != 122 )
    return 0;
  v8 = operator new[](pcbNeeded, (const struct std::nothrow_t *)std::nothrow);
  NCoreLibrary::TAutoPtrArray<unsigned char>::TAutoPtrArray<unsigned char>(&pDriverInfo, v8);
  v9 = pDriverInfo;
  if ( !pDriverInfo
    || !GetPrinterDriverW(hPrinter, 0, 2u, pDriverInfo, pcbNeeded, &pcbNeeded)
    || (v10 = *((_QWORD *)v9 + 5)) == 0 )
  {
    NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&pDriverInfo);
    return 0;
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(v10 + 2 * v11) );
  if ( (unsigned int)v11 < dword_140080A74
    || (unsigned int)_o__wcsicmp(L"tsprint.dll", v10 + 2LL * (unsigned int)(v11 - dword_140080A74)) )
  {
    v7 = 0;
  }
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&pDriverInfo);
  return v7;
}

```

## disassembly

```asm
0x14005becc  mov     [rsp+arg_0], rbx
0x14005bed1  push    rbp
0x14005bed2  push    rsi
0x14005bed3  push    rdi
0x14005bed4  sub     rsp, 30h
0x14005bed8  mov     rsi, rcx
0x14005bedb  xor     edx, edx; hFile
0x14005bedd  lea     rcx, aExtMsWin32Subs; "ext-ms-win32-subsystem-query-l1-1-0.dll"
0x14005bee4  mov     r8d, 800h; dwFlags
0x14005beea  call    cs:__imp_LoadLibraryExW
0x14005bef0  xor     ebp, ebp
0x14005bef2  mov     rbx, rax
0x14005bef5  test    rax, rax
0x14005bef8  jz      loc_14005C00E
0x14005befe  lea     rdx, aQuerywin32subs; "QueryWin32SubsystemHost"
0x14005bf05  mov     rcx, rax; hModule
0x14005bf08  mov     edi, ebp
0x14005bf0a  call    cs:__imp_GetProcAddress
0x14005bf10  test    rax, rax
0x14005bf13  jz      short loc_14005BF1C
0x14005bf15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bf1a  mov     edi, eax
0x14005bf1c  mov     rcx, rbx; hLibModule
0x14005bf1f  call    cs:__imp_FreeLibrary
0x14005bf25  mov     ebx, 1
0x14005bf2a  cmp     edi, ebx
0x14005bf2c  jnz     loc_14005C00E
0x14005bf32  lea     rax, [rsp+48h+arg_8]
0x14005bf37  mov     [rsp+48h+arg_8], ebp
0x14005bf3b  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x14005bf40  lea     r8d, [rbx+1]; Level
0x14005bf44  xor     r9d, r9d; pDriverInfo
0x14005bf47  mov     [rsp+48h+cbBuf], ebp; cbBuf
0x14005bf4b  xor     edx, edx; pEnvironment
0x14005bf4d  mov     rcx, rsi; hPrinter
0x14005bf50  call    cs:__imp_GetPrinterDriverW
0x14005bf56  test    eax, eax
0x14005bf58  jnz     loc_14005C00E
0x14005bf5e  call    cs:__imp_GetLastError
0x14005bf64  cmp     eax, 7Ah ; 'z'
0x14005bf67  jnz     loc_14005C00E
0x14005bf6d  mov     ecx, [rsp+48h+arg_8]; unsigned __int64
0x14005bf71  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005bf78  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14005bf7d  mov     rdx, rax
0x14005bf80  lea     rcx, [rsp+48h+pDriverInfo]
0x14005bf85  call    ??0?$TAutoPtrArray@E@NCoreLibrary@@QEAA@PEAE@Z; NCoreLibrary::TAutoPtrArray<uchar>::TAutoPtrArray<uchar>(uchar *)
0x14005bf8a  mov     rdi, [rsp+48h+pDriverInfo]
0x14005bf8f  test    rdi, rdi
0x14005bf92  jz      short loc_14005C004
0x14005bf94  lea     rax, [rsp+48h+arg_8]
0x14005bf99  mov     r9, rdi; pDriverInfo
0x14005bf9c  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x14005bfa1  lea     r8d, [rbx+1]; Level
0x14005bfa5  mov     eax, [rsp+48h+arg_8]
0x14005bfa9  xor     edx, edx; pEnvironment
0x14005bfab  mov     rcx, rsi; hPrinter
0x14005bfae  mov     [rsp+48h+cbBuf], eax; cbBuf
0x14005bfb2  call    cs:__imp_GetPrinterDriverW
0x14005bfb8  test    eax, eax
0x14005bfba  jz      short loc_14005C004
0x14005bfbc  mov     rcx, [rdi+28h]
0x14005bfc0  test    rcx, rcx
0x14005bfc3  jz      short loc_14005C004
0x14005bfc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005bfc9  inc     rax
0x14005bfcc  cmp     [rcx+rax*2], bp
0x14005bfd0  jnz     short loc_14005BFC9
0x14005bfd2  mov     edx, cs:dword_140080A74
0x14005bfd8  cmp     eax, edx
0x14005bfda  jb      short loc_14005BFF3
0x14005bfdc  sub     eax, edx
0x14005bfde  lea     rdx, [rcx+rax*2]
0x14005bfe2  lea     rcx, aTsprintDll; "tsprint.dll"
0x14005bfe9  call    cs:__imp__o__wcsicmp
0x14005bfef  test    eax, eax
0x14005bff1  jz      short loc_14005BFF6
0x14005bff3  mov     bl, bpl
0x14005bff6  lea     rcx, [rsp+48h+pDriverInfo]
0x14005bffb  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x14005c000  mov     al, bl
0x14005c002  jmp     short loc_14005C010
0x14005c004  lea     rcx, [rsp+48h+pDriverInfo]
0x14005c009  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x14005c00e  xor     al, al
0x14005c010  mov     rbx, [rsp+48h+arg_0]
0x14005c015  add     rsp, 30h
0x14005c019  pop     rdi
0x14005c01a  pop     rsi
0x14005c01b  pop     rbp
0x14005c01c  retn
```
