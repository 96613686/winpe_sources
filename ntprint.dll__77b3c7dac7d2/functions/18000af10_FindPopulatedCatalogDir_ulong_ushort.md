# FindPopulatedCatalogDir(ulong,ushort *)

- ea: `0x18000af10`
- end: `0x18000b115`
- name: `?FindPopulatedCatalogDir@@YAJKPEAG@Z`
- size: `517`
- prototype: `int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000ac60`

## callees

- `0x180002300`
- `0x1800026e0`
- `0x180002f48`
- `0x1800078f0`
- `0x180007944`
- `0x18000af10`
- `0x18000d020`
- `0x18000d57c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b09a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b067`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b067`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000afaf`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18000afaf`

## string_xrefs

- `0x18000afd1`: `GetTempPath() failed hr: 0x%x`

## pseudocode

```c
__int64 __fastcall FindPopulatedCatalogDir(__int64 a1, unsigned __int16 *a2)
{
  signed int v3; // ebx
  signed int LastError; // eax
  __int64 v6; // rdi
  __int64 FirstFileW; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  _QWORD v10[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF

  Buffer[0] = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_3:
    ClassInstallerTelemetry::WriteDbgTraceError("FindPopulatedCatalogDir", L"Returning hr: 0x%x", (unsigned int)v3);
    return (unsigned int)v3;
  }
  *a2 = 0;
  if ( !GetTempPathW(0x104u, Buffer) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "FindPopulatedCatalogDir",
      L"GetTempPath() failed hr: 0x%x",
      (unsigned int)v3);
    if ( v3 < 0 )
      goto LABEL_3;
  }
  v3 = StringCchCatW(Buffer, 0x104u, L"CDM\\PList\\");
  if ( v3 < 0 )
    goto LABEL_3;
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  v3 = StringCchCatW(Buffer, 0x104u, L"*.inf");
  if ( v3 < 0 )
    goto LABEL_3;
  v10[0] = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (__int64)FindFirstFileW(Buffer, &FindFileData);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(v10);
  v10[0] = FirstFileW ? FirstFileW : -1LL;
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(v10);
  v9 = v6;
  if ( v9 >= 260 )
    _report_rangecheckfailure(v8);
  Buffer[v9] = 0;
  v3 = StringCchCopyW(a2, 0x104u, Buffer);
  if ( v3 < 0 )
    goto LABEL_3;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000af10  mov     [rsp-8+arg_0], rbx
0x18000af15  mov     [rsp-8+arg_10], rsi
0x18000af1a  push    rbp
0x18000af1b  push    rdi
0x18000af1c  push    r12
0x18000af1e  push    r14
0x18000af20  push    r15
0x18000af22  lea     rbp, [rsp-3A0h]
0x18000af2a  sub     rsp, 4A0h
0x18000af31  mov     rax, cs:__security_cookie
0x18000af38  xor     rax, rsp
0x18000af3b  mov     [rbp+3C0h+var_30], rax
0x18000af42  xor     r15d, r15d
0x18000af45  mov     r14, rdx
0x18000af48  mov     [rbp+3C0h+Buffer], r15w
0x18000af50  test    rdx, rdx
0x18000af53  jnz     short loc_18000AF9D
0x18000af55  mov     ebx, 80070057h
0x18000af5a  mov     r8d, ebx
0x18000af5d  lea     rdx, aReturningHr0xX; "Returning hr: 0x%x"
0x18000af64  lea     rcx, aFindpopulatedc; "FindPopulatedCatalogDir"
0x18000af6b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000af70  mov     eax, ebx
0x18000af72  mov     rcx, [rbp+3C0h+var_30]
0x18000af79  xor     rcx, rsp; StackCookie
0x18000af7c  call    __security_check_cookie
0x18000af81  lea     r11, [rsp+4C0h+var_20]
0x18000af89  mov     rbx, [r11+30h]
0x18000af8d  mov     rsi, [r11+40h]
0x18000af91  mov     rsp, r11
0x18000af94  pop     r15
0x18000af96  pop     r14
0x18000af98  pop     r12
0x18000af9a  pop     rdi
0x18000af9b  pop     rbp
0x18000af9c  retn
0x18000af9d  mov     [rdx], r15w
0x18000afa1  mov     esi, 104h
0x18000afa6  mov     ecx, esi; nBufferLength
0x18000afa8  lea     rdx, [rbp+3C0h+Buffer]; lpBuffer
0x18000afaf  call    cs:__imp_GetTempPathW
0x18000afb5  test    eax, eax
0x18000afb7  jnz     short loc_18000AFEC
0x18000afb9  call    cs:__imp_GetLastError
0x18000afbf  mov     ebx, eax
0x18000afc1  test    eax, eax
0x18000afc3  jle     short loc_18000AFCE
0x18000afc5  movzx   ebx, ax
0x18000afc8  or      ebx, 80070000h
0x18000afce  mov     r8d, ebx
0x18000afd1  lea     rdx, aGettemppathFai; "GetTempPath() failed hr: 0x%x"
0x18000afd8  lea     rcx, aFindpopulatedc; "FindPopulatedCatalogDir"
0x18000afdf  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000afe4  test    ebx, ebx
0x18000afe6  js      loc_18000AF5A
0x18000afec  lea     r8, aCdmPlist; "CDM\\PList\\"
0x18000aff3  mov     rdx, rsi; unsigned __int64
0x18000aff6  lea     rcx, [rbp+3C0h+Buffer]; unsigned __int16 *
0x18000affd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b002  mov     ebx, eax
0x18000b004  test    eax, eax
0x18000b006  js      loc_18000AF5A
0x18000b00c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b010  lea     rax, [rbp+3C0h+Buffer]
0x18000b017  mov     rdi, r12
0x18000b01a  inc     rdi
0x18000b01d  cmp     [rax+rdi*2], r15w
0x18000b022  jnz     short loc_18000B01A
0x18000b024  lea     r8, aInf_1; "*.inf"
0x18000b02b  mov     rdx, rsi; unsigned __int64
0x18000b02e  lea     rcx, [rbp+3C0h+Buffer]; unsigned __int16 *
0x18000b035  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b03a  mov     ebx, eax
0x18000b03c  test    eax, eax
0x18000b03e  js      loc_18000AF5A
0x18000b044  xor     edx, edx; Val
0x18000b046  mov     [rsp+4C0h+var_4A0], r12
0x18000b04b  mov     r8d, 250h; Size
0x18000b051  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x18000b056  call    memset_0
0x18000b05b  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x18000b060  lea     rcx, [rbp+3C0h+Buffer]; lpFileName
0x18000b067  call    cs:__imp_FindFirstFileW
0x18000b06d  lea     rcx, [rsp+4C0h+var_4A0]
0x18000b072  mov     rsi, rax
0x18000b075  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleFindFirst@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(void)
0x18000b07a  test    rsi, rsi
0x18000b07d  jnz     short loc_18000B086
0x18000b07f  mov     [rsp+4C0h+var_4A0], r12
0x18000b084  jmp     short loc_18000B0C5
0x18000b086  cmp     rsi, r12
0x18000b089  mov     [rsp+4C0h+var_4A0], rsi
0x18000b08e  mov     rax, r15
0x18000b091  cmovnz  rax, rsi
0x18000b095  cmp     rax, r12
0x18000b098  jnz     short loc_18000B0C5
0x18000b09a  call    cs:__imp_GetLastError
0x18000b0a0  mov     ebx, eax
0x18000b0a2  test    eax, eax
0x18000b0a4  jle     short loc_18000B0AF
0x18000b0a6  movzx   ebx, ax
0x18000b0a9  or      ebx, 80070000h
0x18000b0af  mov     r8d, ebx
0x18000b0b2  lea     rdx, aFindfirstfileF; "FindFirstFile() failed hr: 0x%x"
0x18000b0b9  lea     rcx, aFindpopulatedc; "FindPopulatedCatalogDir"
0x18000b0c0  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000b0c5  lea     rcx, [rsp+4C0h+var_4A0]
0x18000b0ca  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleFindFirst@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(void)
0x18000b0cf  test    ebx, ebx
0x18000b0d1  js      loc_18000AF5A
0x18000b0d7  add     rdi, rdi
0x18000b0da  cmp     rdi, 208h
0x18000b0e1  jnb     short loc_18000B10F
0x18000b0e3  lea     r8, [rbp+3C0h+Buffer]; unsigned __int16 *
0x18000b0ea  mov     [rbp+rdi+3C0h+Buffer], r15w
0x18000b0f3  mov     edx, 104h; unsigned __int64
0x18000b0f8  mov     rcx, r14; unsigned __int16 *
0x18000b0fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b100  mov     ebx, eax
0x18000b102  test    eax, eax
0x18000b104  jns     loc_18000AF70
0x18000b10a  jmp     loc_18000AF5A
0x18000b10f  call    __report_rangecheckfailure
```
