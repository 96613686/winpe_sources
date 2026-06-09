# PackageCollection::FindConfigFile(ushort const *,ushort * *)

- ea: `0x140053bac`
- end: `0x140053e08`
- name: `?FindConfigFile@PackageCollection@@AEAAJPEBGPEAPEAG@Z`
- size: `604`
- prototype: `__int64 __fastcall(PackageCollection *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140052f10`

## callees

- `0x1400039b1`
- `0x1400070b0`
- `0x140020420`
- `0x140053bac`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140053d40`
- `KERNEL32!GetLastError` at `0x140053d40`
- `KERNEL32!HeapAlloc` at `0x140053c02`
- `KERNEL32!HeapAlloc` at `0x140053ccb`
- `KERNEL32!HeapAlloc` at `0x140053c02`
- `KERNEL32!HeapAlloc` at `0x140053ccb`
- `KERNEL32!HeapFree` at `0x140053dad`
- `KERNEL32!HeapFree` at `0x140053dd2`
- `KERNEL32!HeapFree` at `0x140053dad`
- `KERNEL32!HeapFree` at `0x140053dd2`
- `KERNEL32!GetProcessHeap` at `0x140053be9`
- `KERNEL32!GetProcessHeap` at `0x140053cb7`
- `KERNEL32!GetProcessHeap` at `0x140053d99`
- `KERNEL32!GetProcessHeap` at `0x140053dbe`
- `KERNEL32!GetProcessHeap` at `0x140053be9`
- `KERNEL32!GetProcessHeap` at `0x140053cb7`
- `KERNEL32!GetProcessHeap` at `0x140053d99`
- `KERNEL32!GetProcessHeap` at `0x140053dbe`
- `KERNEL32!FindFirstFileW` at `0x140053c9a`
- `KERNEL32!FindFirstFileW` at `0x140053c9a`
- `KERNEL32!FindClose` at `0x140053d8d`
- `KERNEL32!FindClose` at `0x140053d8d`

## string_xrefs

- `0x140053c1b`: `PackageCollection::FindConfigFile`
- `0x140053c77`: `PackageCollection::FindConfigFile`
- `0x140053d1b`: `PackageCollection::FindConfigFile`
- `0x140053d65`: `PackageCollection::FindConfigFile`

## pseudocode

```c
__int64 __fastcall PackageCollection::FindConfigFile(
        PackageCollection *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rbp
  unsigned int v7; // ebx
  int v8; // eax
  unsigned __int16 *v9; // rdi
  char *FirstFileW; // rsi
  HANDLE v11; // rax
  int v12; // eax
  int v13; // r9d
  signed int LastError; // eax
  HANDLE v15; // rax
  HANDLE v16; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-288h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v6 )
  {
    v7 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::FindConfigFile", 2021, -2147024882);
    return v7;
  }
  v8 = StringCchPrintfW(v6, 0x104u, L"%s\\*.%s", a2, L"diagcfg");
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = 0;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::FindConfigFile", 2024, v8);
    goto LABEL_17;
  }
  FirstFileW = (char *)FindFirstFileW(v6, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::FindConfigFile", 2027, v7);
    v9 = 0;
    if ( FirstFileW == (char *)-1LL || !FirstFileW )
      goto LABEL_17;
    goto LABEL_16;
  }
  v11 = GetProcessHeap();
  v9 = (unsigned __int16 *)HeapAlloc(v11, 0, 0x208u);
  if ( v9 )
  {
    v12 = StringCchPrintfW(v9, 0x104u, L"%s\\%s", a2, FindFileData.cFileName);
    v7 = v12;
    if ( v12 >= 0 )
    {
      *a3 = v9;
      v9 = 0;
      goto LABEL_16;
    }
    v13 = 2037;
  }
  else
  {
    v12 = -2147024882;
    v13 = 2029;
    v7 = -2147024882;
  }
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::FindConfigFile", v13, v12);
LABEL_16:
  FindClose(FirstFileW);
LABEL_17:
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v6);
  if ( v9 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v9);
  }
  return v7;
}

```

## disassembly

```asm
0x140053bac  mov     [rsp+arg_0], rbx
0x140053bb1  push    rbp
0x140053bb2  push    rsi
0x140053bb3  push    rdi
0x140053bb4  push    r14
0x140053bb6  push    r15
0x140053bb8  sub     rsp, 290h
0x140053bbf  mov     rax, cs:__security_cookie
0x140053bc6  xor     rax, rsp
0x140053bc9  mov     [rsp+2B8h+var_38], rax
0x140053bd1  mov     r15, r8
0x140053bd4  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x140053bd9  mov     r14, rdx
0x140053bdc  mov     r8d, 250h; Size
0x140053be2  xor     edx, edx; Val
0x140053be4  call    memset_0
0x140053be9  call    cs:__imp_GetProcessHeap
0x140053bf0  nop     dword ptr [rax+rax+00h]
0x140053bf5  mov     edi, 208h
0x140053bfa  xor     edx, edx; dwFlags
0x140053bfc  mov     rcx, rax; hHeap
0x140053bff  mov     r8d, edi; dwBytes
0x140053c02  call    cs:__imp_HeapAlloc
0x140053c09  nop     dword ptr [rax+rax+00h]
0x140053c0e  mov     rbp, rax
0x140053c11  test    rax, rax
0x140053c14  jnz     short loc_140053C42
0x140053c16  mov     eax, 8007000Eh
0x140053c1b  lea     r8, aPackagecollect_2; "PackageCollection::FindConfigFile"
0x140053c22  mov     r9d, 7E5h
0x140053c28  mov     dword ptr [rsp+2B8h+var_298], eax
0x140053c2c  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053c33  mov     ebx, eax
0x140053c35  lea     ecx, [rbp+1]; Level
0x140053c38  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053c3d  jmp     loc_140053DDE
0x140053c42  lea     rax, aDiagcfg; "diagcfg"
0x140053c49  mov     r9, r14
0x140053c4c  lea     r8, aSS_0; "%s\\*.%s"
0x140053c53  mov     [rsp+2B8h+var_298], rax
0x140053c58  mov     edx, 104h; unsigned __int64
0x140053c5d  mov     rcx, rbp; unsigned __int16 *
0x140053c60  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140053c65  mov     ebx, eax
0x140053c67  test    eax, eax
0x140053c69  jns     short loc_140053C92
0x140053c6b  xor     edi, edi
0x140053c6d  mov     dword ptr [rsp+2B8h+var_298], eax
0x140053c71  mov     r9d, 7E8h
0x140053c77  lea     r8, aPackagecollect_2; "PackageCollection::FindConfigFile"
0x140053c7e  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053c85  lea     ecx, [rdi+1]; Level
0x140053c88  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053c8d  jmp     loc_140053D99
0x140053c92  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x140053c97  mov     rcx, rbp; lpFileName
0x140053c9a  call    cs:__imp_FindFirstFileW
0x140053ca1  nop     dword ptr [rax+rax+00h]
0x140053ca6  mov     rsi, rax
0x140053ca9  lea     rcx, [rax-1]
0x140053cad  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140053cb1  ja      loc_140053D40
0x140053cb7  call    cs:__imp_GetProcessHeap
0x140053cbe  nop     dword ptr [rax+rax+00h]
0x140053cc3  mov     r8, rdi; dwBytes
0x140053cc6  xor     edx, edx; dwFlags
0x140053cc8  mov     rcx, rax; hHeap
0x140053ccb  call    cs:__imp_HeapAlloc
0x140053cd2  nop     dword ptr [rax+rax+00h]
0x140053cd7  mov     rdi, rax
0x140053cda  test    rax, rax
0x140053cdd  jnz     short loc_140053CEE
0x140053cdf  mov     eax, 8007000Eh
0x140053ce4  mov     r9d, 7EDh
0x140053cea  mov     ebx, eax
0x140053cec  jmp     short loc_140053D1B
0x140053cee  lea     rax, [rsp+2B8h+FindFileData.cFileName]
0x140053cf3  mov     r9, r14
0x140053cf6  lea     r8, aSS_1; "%s\\%s"
0x140053cfd  mov     [rsp+2B8h+var_298], rax
0x140053d02  mov     edx, 104h; unsigned __int64
0x140053d07  mov     rcx, rdi; unsigned __int16 *
0x140053d0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140053d0f  mov     ebx, eax
0x140053d11  test    eax, eax
0x140053d13  jns     short loc_140053D39
0x140053d15  mov     r9d, 7F5h
0x140053d1b  lea     r8, aPackagecollect_2; "PackageCollection::FindConfigFile"
0x140053d22  mov     dword ptr [rsp+2B8h+var_298], eax
0x140053d26  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053d2d  mov     ecx, 1; Level
0x140053d32  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053d37  jmp     short loc_140053D8A
0x140053d39  mov     [r15], rdi
0x140053d3c  xor     edi, edi
0x140053d3e  jmp     short loc_140053D8A
0x140053d40  call    cs:__imp_GetLastError
0x140053d47  nop     dword ptr [rax+rax+00h]
0x140053d4c  mov     ebx, eax
0x140053d4e  test    eax, eax
0x140053d50  jle     short loc_140053D5B
0x140053d52  movzx   ebx, ax
0x140053d55  or      ebx, 80070000h
0x140053d5b  mov     r9d, 7EBh
0x140053d61  mov     dword ptr [rsp+2B8h+var_298], ebx
0x140053d65  lea     r8, aPackagecollect_2; "PackageCollection::FindConfigFile"
0x140053d6c  mov     ecx, 1; Level
0x140053d71  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053d78  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053d7d  xor     edi, edi
0x140053d7f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140053d83  jz      short loc_140053D99
0x140053d85  test    rsi, rsi
0x140053d88  jz      short loc_140053D99
0x140053d8a  mov     rcx, rsi; hFindFile
0x140053d8d  call    cs:__imp_FindClose
0x140053d94  nop     dword ptr [rax+rax+00h]
0x140053d99  call    cs:__imp_GetProcessHeap
0x140053da0  nop     dword ptr [rax+rax+00h]
0x140053da5  mov     r8, rbp; lpMem
0x140053da8  xor     edx, edx; dwFlags
0x140053daa  mov     rcx, rax; hHeap
0x140053dad  call    cs:__imp_HeapFree
0x140053db4  nop     dword ptr [rax+rax+00h]
0x140053db9  test    rdi, rdi
0x140053dbc  jz      short loc_140053DDE
0x140053dbe  call    cs:__imp_GetProcessHeap
0x140053dc5  nop     dword ptr [rax+rax+00h]
0x140053dca  mov     r8, rdi; lpMem
0x140053dcd  xor     edx, edx; dwFlags
0x140053dcf  mov     rcx, rax; hHeap
0x140053dd2  call    cs:__imp_HeapFree
0x140053dd9  nop     dword ptr [rax+rax+00h]
0x140053dde  mov     eax, ebx
0x140053de0  mov     rcx, [rsp+2B8h+var_38]
0x140053de8  xor     rcx, rsp; StackCookie
0x140053deb  call    __security_check_cookie
0x140053df0  mov     rbx, [rsp+2B8h+arg_0]
0x140053df8  add     rsp, 290h
0x140053dff  pop     r15
0x140053e01  pop     r14
0x140053e03  pop     rdi
0x140053e04  pop     rsi
0x140053e05  pop     rbp
0x140053e06  retn
```
