# MatchTimeStamp(ushort *,ushort *,ushort *,int *)

- ea: `0x180020e0c`
- end: `0x180020f10`
- name: `?MatchTimeStamp@@YAJPEAG00PEAH@Z`
- size: `260`
- prototype: `__int64 __fastcall(LPCWSTR lpString, LPCWSTR lpFileName, LPCWSTR, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b98c`

## callees

- `0x18001e718`
- `0x180020e0c`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180020ea6`
- `KERNEL32!CompareFileTime` at `0x180020ee4`
- `KERNEL32!CompareFileTime` at `0x180020ea6`
- `KERNEL32!CompareFileTime` at `0x180020ee4`
- `KERNEL32!GetFileAttributesExW` at `0x180020e94`
- `KERNEL32!GetFileAttributesExW` at `0x180020ed2`
- `KERNEL32!GetFileAttributesExW` at `0x180020e94`
- `KERNEL32!GetFileAttributesExW` at `0x180020ed2`

## string_xrefs

- `0x180020e5b`: `XMLSchemaTimeStamp`

## pseudocode

```c
__int64 __fastcall MatchTimeStamp(LPCWSTR lpString, LPCWSTR lpFileName, LPCWSTR a3, int *a4)
{
  int TimeStamp; // ecx
  __int64 result; // rax
  FILETIME FileTime1; // [rsp+20h] [rbp-39h] BYREF
  FILETIME v11; // [rsp+28h] [rbp-31h] BYREF
  __int128 FileInformation; // [rsp+30h] [rbp-29h] BYREF
  FILETIME FileTime2[2]; // [rsp+40h] [rbp-19h] BYREF
  int v14; // [rsp+50h] [rbp-9h]
  __int128 v15; // [rsp+58h] [rbp-1h] BYREF
  FILETIME v16[2]; // [rsp+68h] [rbp+Fh] BYREF
  int v17; // [rsp+78h] [rbp+1Fh]

  FileTime1 = 0;
  v14 = 0;
  v17 = 0;
  *a4 = 0;
  v11 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  v15 = 0;
  *(_OWORD *)&v16[0].dwLowDateTime = 0;
  TimeStamp = GetTimeStamp(lpString, L"XMLSchemaTimeStamp", &FileTime1);
  if ( TimeStamp < 0 )
  {
LABEL_2:
    result = 2149648394LL;
    if ( TimeStamp == -2145318902 )
      return result;
    return 0;
  }
  if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation)
    && !CompareFileTime(&FileTime1, (const FILETIME *)&FileTime2[0].dwHighDateTime) )
  {
    TimeStamp = GetTimeStamp(lpString, L"BINSchemaTimeStamp", &v11);
    if ( TimeStamp < 0 )
      goto LABEL_2;
    if ( GetFileAttributesExW(a3, GetFileExInfoStandard, &v15) )
    {
      if ( !CompareFileTime(&v11, (const FILETIME *)&v16[0].dwHighDateTime) )
        *a4 = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020e0c  push    rbp
0x180020e0e  push    rbx
0x180020e0f  push    rsi
0x180020e10  push    rdi
0x180020e11  push    r14
0x180020e13  lea     rbp, [rsp-37h]
0x180020e18  sub     rsp, 90h
0x180020e1f  mov     rax, cs:__security_cookie
0x180020e26  xor     rax, rsp
0x180020e29  mov     [rbp+57h+var_30], rax
0x180020e2d  xor     eax, eax
0x180020e2f  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], 0
0x180020e37  xorps   xmm0, xmm0
0x180020e3a  mov     [rbp+57h+var_60], eax
0x180020e3d  xorps   xmm1, xmm1
0x180020e40  mov     [rbp+57h+var_38], eax
0x180020e43  mov     r14, r8
0x180020e46  mov     [r9], eax
0x180020e49  mov     rsi, rdx
0x180020e4c  mov     qword ptr [rbp+57h+var_88.dwLowDateTime], 0
0x180020e54  lea     r8, [rbp+57h+FileTime1]; struct _FILETIME *
0x180020e58  mov     rbx, r9
0x180020e5b  lea     rdx, aXmlschematimes; "XMLSchemaTimeStamp"
0x180020e62  mov     rdi, rcx
0x180020e65  movups  [rbp+57h+FileInformation], xmm0
0x180020e69  movups  xmmword ptr [rbp+57h+FileTime2.dwLowDateTime], xmm0
0x180020e6d  movups  [rbp+57h+var_58], xmm1
0x180020e71  movups  xmmword ptr [rbp+57h+var_48.dwLowDateTime], xmm1
0x180020e75  call    ?GetTimeStamp@@YAJPEAG0PEAU_FILETIME@@@Z; GetTimeStamp(ushort *,ushort *,_FILETIME *)
0x180020e7a  mov     ecx, eax
0x180020e7c  test    eax, eax
0x180020e7e  jns     short loc_180020E8B
0x180020e80  mov     eax, 8021080Ah
0x180020e85  cmp     ecx, eax
0x180020e87  jz      short loc_180020EF6
0x180020e89  jmp     short loc_180020EF4
0x180020e8b  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180020e8f  xor     edx, edx; fInfoLevelId
0x180020e91  mov     rcx, rsi; lpFileName
0x180020e94  call    cs:__imp_GetFileAttributesExW
0x180020e9a  test    eax, eax
0x180020e9c  jz      short loc_180020EF4
0x180020e9e  lea     rdx, [rbp+57h+FileTime2.dwHighDateTime]; lpFileTime2
0x180020ea2  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180020ea6  call    cs:__imp_CompareFileTime
0x180020eac  test    eax, eax
0x180020eae  jnz     short loc_180020EF4
0x180020eb0  lea     r8, [rbp+57h+var_88]; struct _FILETIME *
0x180020eb4  mov     rcx, rdi; lpString
0x180020eb7  lea     rdx, aBinschematimes; "BINSchemaTimeStamp"
0x180020ebe  call    ?GetTimeStamp@@YAJPEAG0PEAU_FILETIME@@@Z; GetTimeStamp(ushort *,ushort *,_FILETIME *)
0x180020ec3  mov     ecx, eax
0x180020ec5  test    eax, eax
0x180020ec7  js      short loc_180020E80
0x180020ec9  lea     r8, [rbp+57h+var_58]; lpFileInformation
0x180020ecd  xor     edx, edx; fInfoLevelId
0x180020ecf  mov     rcx, r14; lpFileName
0x180020ed2  call    cs:__imp_GetFileAttributesExW
0x180020ed8  test    eax, eax
0x180020eda  jz      short loc_180020EF4
0x180020edc  lea     rdx, [rbp+57h+var_48.dwHighDateTime]; lpFileTime2
0x180020ee0  lea     rcx, [rbp+57h+var_88]; lpFileTime1
0x180020ee4  call    cs:__imp_CompareFileTime
0x180020eea  test    eax, eax
0x180020eec  jnz     short loc_180020EF4
0x180020eee  mov     dword ptr [rbx], 1
0x180020ef4  xor     eax, eax
0x180020ef6  mov     rcx, [rbp+57h+var_30]
0x180020efa  xor     rcx, rsp; StackCookie
0x180020efd  call    __security_check_cookie
0x180020f02  add     rsp, 90h
0x180020f09  pop     r14
0x180020f0b  pop     rdi
0x180020f0c  pop     rsi
0x180020f0d  pop     rbx
0x180020f0e  pop     rbp
0x180020f0f  retn
```
