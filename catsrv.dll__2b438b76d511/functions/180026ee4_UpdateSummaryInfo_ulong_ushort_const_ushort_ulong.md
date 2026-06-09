# UpdateSummaryInfo(ulong,ushort const *,ushort *,ulong)

- ea: `0x180026ee4`
- end: `0x18002708e`
- name: `?UpdateSummaryInfo@@YAJKPEBGPEAGK@Z`
- size: `426`
- prototype: `int(unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18002673c`

## callees

- `0x180009ee0`
- `0x18000a01c`
- `0x180026ee4`
- `0x180055550`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x180027064`
- `msi!__imp_MsiCloseHandle` at `0x180027064`
- `msi!__imp_MsiGetSummaryInformationW` at `0x180026f25`
- `msi!__imp_MsiGetSummaryInformationW` at `0x180026f25`
- `msi!__imp_MsiSummaryInfoGetPropertyW` at `0x180026f94`
- `msi!__imp_MsiSummaryInfoGetPropertyW` at `0x180026f94`
- `msi!__imp_MsiSummaryInfoPersist` at `0x180027047`
- `msi!__imp_MsiSummaryInfoPersist` at `0x180027047`
- `msi!__imp_MsiSummaryInfoSetPropertyW` at `0x180026fed`
- `msi!__imp_MsiSummaryInfoSetPropertyW` at `0x180027013`
- `msi!__imp_MsiSummaryInfoSetPropertyW` at `0x180027039`
- `msi!__imp_MsiSummaryInfoSetPropertyW` at `0x180026fed`
- `msi!__imp_MsiSummaryInfoSetPropertyW` at `0x180027013`
- `msi!__imp_MsiSummaryInfoSetPropertyW` at `0x180027039`

## pseudocode

```c
int __fastcall UpdateSummaryInfo(MSIHANDLE a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  int result; // eax
  int v6; // eax
  unsigned int v7; // ebx
  signed int v8; // eax
  bool v9; // cc
  MSIHANDLE phSummaryInfo; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchValueBuf; // [rsp+44h] [rbp-BCh] BYREF
  int piValue; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int puiDataType; // [rsp+4Ch] [rbp-B4h] BYREF
  FILETIME pftValue; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szValueBuf[304]; // [rsp+60h] [rbp-A0h] BYREF

  phSummaryInfo = 0;
  result = MsiGetSummaryInformationW(a1, 0, 0xFu, &phSummaryInfo);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    puiDataType = 30;
    piValue = 0;
    pftValue = 0;
    pcchValueBuf = 260;
    if ( MsiSummaryInfoGetPropertyW(phSummaryInfo, 2u, &puiDataType, &piValue, &pftValue, szValueBuf, &pcchValueBuf) )
      v6 = StringCchCopyW(a3, 0x130u, a2);
    else
      v6 = StringCchPrintfW(a3, 0x130u, szValueBuf, L" : ", a2);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v8 = MsiSummaryInfoSetPropertyW(phSummaryInfo, 6u, 0x1Eu, 0, 0, a2);
      v9 = v8 <= 0;
      if ( v8
        || (v8 = MsiSummaryInfoSetPropertyW(phSummaryInfo, 9u, 0x1Eu, 0, 0, a2), v9 = v8 <= 0, v8)
        || (v8 = MsiSummaryInfoSetPropertyW(phSummaryInfo, 2u, 0x1Eu, 0, 0, a3), v9 = v8 <= 0, v8)
        || (v8 = MsiSummaryInfoPersist(phSummaryInfo), v9 = v8 <= 0, v8) )
      {
        if ( v9 )
          v7 = v8;
        else
          v7 = (unsigned __int16)v8 | 0x80070000;
      }
    }
    MsiCloseHandle(phSummaryInfo);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180026ee4  mov     [rsp-8+arg_18], rbx
0x180026ee9  push    rbp
0x180026eea  push    rsi
0x180026eeb  push    rdi
0x180026eec  lea     rbp, [rsp-1D0h]
0x180026ef4  sub     rsp, 2D0h
0x180026efb  mov     rax, cs:__security_cookie
0x180026f02  xor     rax, rsp
0x180026f05  mov     [rbp+1E0h+var_20], rax
0x180026f0c  mov     rdi, rdx
0x180026f0f  mov     [rsp+2E0h+phSummaryInfo], 0
0x180026f17  xor     edx, edx; szDatabasePath
0x180026f19  lea     r9, [rsp+2E0h+phSummaryInfo]; phSummaryInfo
0x180026f1e  mov     rsi, r8
0x180026f21  lea     r8d, [rdx+0Fh]; uiUpdateCount
0x180026f25  call    cs:__imp_MsiGetSummaryInformationW
0x180026f2b  test    eax, eax
0x180026f2d  jz      short loc_180026F42
0x180026f2f  jle     loc_18002706C
0x180026f35  movzx   eax, ax
0x180026f38  or      eax, 80070000h
0x180026f3d  jmp     loc_18002706C
0x180026f42  mov     ecx, [rsp+2E0h+phSummaryInfo]; hSummaryInfo
0x180026f46  lea     rax, [rsp+2E0h+var_29C]
0x180026f4b  mov     [rsp+2E0h+pcchValueBuf], rax; pcchValueBuf
0x180026f50  lea     r9, [rsp+2E0h+piValue]; piValue
0x180026f55  lea     rax, [rsp+2E0h+var_280]
0x180026f5a  mov     [rsp+2E0h+puiDataType], 1Eh
0x180026f62  mov     [rsp+2E0h+szValueBuf], rax; szValueBuf
0x180026f67  lea     r8, [rsp+2E0h+puiDataType]; puiDataType
0x180026f6c  lea     rax, [rsp+2E0h+var_290]
0x180026f71  mov     [rsp+2E0h+piValue], 0
0x180026f79  mov     edx, 2; uiProperty
0x180026f7e  mov     [rsp+2E0h+pftValue], rax; pftValue
0x180026f83  mov     qword ptr [rsp+2E0h+var_290.dwLowDateTime], 0
0x180026f8c  mov     [rsp+2E0h+var_29C], 104h
0x180026f94  call    cs:__imp_MsiSummaryInfoGetPropertyW
0x180026f9a  mov     edx, 130h; unsigned __int64
0x180026f9f  mov     rcx, rsi; unsigned __int16 *
0x180026fa2  test    eax, eax
0x180026fa4  jnz     short loc_180026FBE
0x180026fa6  lea     r9, asc_18005D6C8; " : "
0x180026fad  mov     [rsp+2E0h+pftValue], rdi
0x180026fb2  lea     r8, [rsp+2E0h+var_280]; unsigned __int16 *
0x180026fb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026fbc  jmp     short loc_180026FC6
0x180026fbe  mov     r8, rdi; unsigned __int16 *
0x180026fc1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026fc6  mov     ebx, eax
0x180026fc8  test    eax, eax
0x180026fca  js      loc_180027060
0x180026fd0  mov     ecx, [rsp+2E0h+phSummaryInfo]; hSummaryInfo
0x180026fd4  xor     r9d, r9d; iValue
0x180026fd7  mov     [rsp+2E0h+szValueBuf], rdi; szValue
0x180026fdc  mov     [rsp+2E0h+pftValue], 0; pftValue
0x180026fe5  lea     edx, [r9+6]; uiProperty
0x180026fe9  lea     r8d, [r9+1Eh]; uiDataType
0x180026fed  call    cs:__imp_MsiSummaryInfoSetPropertyW
0x180026ff3  test    eax, eax
0x180026ff5  jnz     short loc_180027051
0x180026ff7  mov     ecx, [rsp+2E0h+phSummaryInfo]; hSummaryInfo
0x180026ffb  lea     edx, [rax+9]; uiProperty
0x180026ffe  mov     [rsp+2E0h+szValueBuf], rdi; szValue
0x180027003  lea     r8d, [rax+1Eh]; uiDataType
0x180027007  xor     r9d, r9d; iValue
0x18002700a  mov     [rsp+2E0h+pftValue], 0; pftValue
0x180027013  call    cs:__imp_MsiSummaryInfoSetPropertyW
0x180027019  test    eax, eax
0x18002701b  jnz     short loc_180027051
0x18002701d  mov     ecx, [rsp+2E0h+phSummaryInfo]; hSummaryInfo
0x180027021  lea     edx, [rax+2]; uiProperty
0x180027024  mov     [rsp+2E0h+szValueBuf], rsi; szValue
0x180027029  lea     r8d, [rax+1Eh]; uiDataType
0x18002702d  xor     r9d, r9d; iValue
0x180027030  mov     [rsp+2E0h+pftValue], 0; pftValue
0x180027039  call    cs:__imp_MsiSummaryInfoSetPropertyW
0x18002703f  test    eax, eax
0x180027041  jnz     short loc_180027051
0x180027043  mov     ecx, [rsp+2E0h+phSummaryInfo]; hSummaryInfo
0x180027047  call    cs:__imp_MsiSummaryInfoPersist
0x18002704d  test    eax, eax
0x18002704f  jz      short loc_180027060
0x180027051  jg      short loc_180027057
0x180027053  mov     ebx, eax
0x180027055  jmp     short loc_180027060
0x180027057  movzx   ebx, ax
0x18002705a  or      ebx, 80070000h
0x180027060  mov     ecx, [rsp+2E0h+phSummaryInfo]; hAny
0x180027064  call    cs:__imp_MsiCloseHandle
0x18002706a  mov     eax, ebx
0x18002706c  mov     rcx, [rbp+1E0h+var_20]
0x180027073  xor     rcx, rsp; StackCookie
0x180027076  call    __security_check_cookie
0x18002707b  mov     rbx, [rsp+2E0h+arg_18]
0x180027083  add     rsp, 2D0h
0x18002708a  pop     rdi
0x18002708b  pop     rsi
0x18002708c  pop     rbp
0x18002708d  retn
```
