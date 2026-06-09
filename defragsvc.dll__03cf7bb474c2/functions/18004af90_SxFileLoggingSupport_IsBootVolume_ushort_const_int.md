# SxFileLoggingSupport::IsBootVolume(ushort const *,int *)

- ea: `0x18004af90`
- end: `0x18004b1c4`
- name: `?IsBootVolume@SxFileLoggingSupport@@AEAAJPEBGPEAH@Z`
- size: `564`
- prototype: `int(SxFileLoggingSupport *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18004aa24`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180044448`
- `0x18004a92c`
- `0x18004af90`
- `0x18004b690`
- `0x180067b30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004b13e`
- `msvcrt!_wcsicmp` at `0x18004b13e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004b034`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004b034`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004aff3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004aff3`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004b06b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004b06b`

## pseudocode

```c
__int64 __fastcall SxFileLoggingSupport::IsBootVolume(SxFileLoggingSupport *this, const unsigned __int16 *a2, int *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int16 v9; // ax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  CSxGlobalTracer *v18; // r10
  __int64 v19; // rax
  int v20; // eax
  const char *v21; // r9
  unsigned int v22; // ebx
  unsigned int LastFailureAsHRESULT; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v25; // [rsp+34h] [rbp-CCh]
  __int16 v26; // [rsp+36h] [rbp-CAh]
  wchar_t szVolumeName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer[264]; // [rsp+490h] [rbp+390h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "SxFileLoggingSupport::IsBootVolume",
    407,
    1);
  *a3 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6, v5, v7, v8);
    v9 = 417;
LABEL_3:
    v26 = v9;
    goto LABEL_22;
  }
  LastFailureAsHRESULT = 0;
  v25 = 417;
  if ( !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11, v10, v12, v13);
    v9 = 418;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v25 = 418;
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15, v14, v16, v17);
    v9 = 419;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v25 = 419;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids,
      (unsigned int)szVolumeName,
      (__int64)szVolumePathName);
    v18 = WPP_GLOBAL_Control;
  }
  v19 = -1;
  do
    ++v19;
  while ( szVolumeName[v19] );
  if ( 2 * (unsigned __int64)(unsigned int)(v19 - 1) >= 0x20A )
    _report_rangecheckfailure();
  szVolumeName[(unsigned int)(v19 - 1)] = 0;
  if ( v18 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x8000000) != 0 )
    WPP_SF_SS(
      *((_QWORD *)v18 + 2),
      21,
      (unsigned int)WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids,
      (_DWORD)a2,
      (__int64)szVolumeName);
  v20 = _wcsicmp(a2, szVolumeName);
  *a3 = v20 == 0;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    v21 = "TRUE";
    if ( v20 )
      v21 = "FALSE";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids, v21);
  }
LABEL_22:
  v22 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v22;
}

```

## disassembly

```asm
0x18004af90  mov     [rsp-8+arg_0], rbx
0x18004af95  push    rbp
0x18004af96  push    rsi
0x18004af97  push    rdi
0x18004af98  push    r14
0x18004af9a  push    r15
0x18004af9c  lea     rbp, [rsp-5B0h]
0x18004afa4  sub     rsp, 6B0h
0x18004afab  mov     rax, cs:__security_cookie
0x18004afb2  xor     rax, rsp
0x18004afb5  mov     [rbp+5D0h+var_30], rax
0x18004afbc  mov     rdi, r8
0x18004afbf  lea     rcx, [rsp+6D0h+var_6A0]; this
0x18004afc4  mov     rbx, rdx
0x18004afc7  mov     r8d, 197h; unsigned __int16
0x18004afcd  lea     rdx, aSxfileloggings_2; "SxFileLoggingSupport::IsBootVolume"
0x18004afd4  mov     r9d, 1; unsigned __int16
0x18004afda  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004afdf  mov     r14d, 104h
0x18004afe5  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x18004afec  xor     esi, esi
0x18004afee  mov     edx, r14d; uSize
0x18004aff1  mov     [rdi], esi
0x18004aff3  call    cs:__imp_GetSystemDirectoryW
0x18004aff9  test    eax, eax
0x18004affb  jnz     short loc_18004B015
0x18004affd  call    GetLastFailureAsHRESULT
0x18004b002  mov     [rsp+6D0h+var_6A0], eax
0x18004b006  mov     eax, 1A1h
0x18004b00b  mov     [rsp+6D0h+var_69A], ax
0x18004b010  jmp     loc_18004B188
0x18004b015  mov     eax, 1A1h
0x18004b01a  mov     [rsp+6D0h+var_6A0], esi
0x18004b01e  mov     r8d, r14d; cchBufferLength
0x18004b021  mov     [rsp+6D0h+var_69C], ax
0x18004b026  lea     rdx, [rbp+5D0h+szVolumePathName]; lpszVolumePathName
0x18004b02d  lea     rcx, [rbp+5D0h+Buffer]; lpszFileName
0x18004b034  call    cs:__imp_GetVolumePathNameW
0x18004b03a  test    eax, eax
0x18004b03c  jnz     short loc_18004B04E
0x18004b03e  call    GetLastFailureAsHRESULT
0x18004b043  mov     [rsp+6D0h+var_6A0], eax
0x18004b047  mov     eax, 1A2h
0x18004b04c  jmp     short loc_18004B00B
0x18004b04e  mov     eax, 1A2h
0x18004b053  mov     [rsp+6D0h+var_6A0], esi
0x18004b057  mov     r8d, r14d; cchBufferLength
0x18004b05a  mov     [rsp+6D0h+var_69C], ax
0x18004b05f  lea     rdx, [rsp+6D0h+szVolumeName]; lpszVolumeName
0x18004b064  lea     rcx, [rbp+5D0h+szVolumePathName]; lpszVolumeMountPoint
0x18004b06b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004b071  test    eax, eax
0x18004b073  jnz     short loc_18004B085
0x18004b075  call    GetLastFailureAsHRESULT
0x18004b07a  mov     [rsp+6D0h+var_6A0], eax
0x18004b07e  mov     eax, 1A3h
0x18004b083  jmp     short loc_18004B00B
0x18004b085  mov     eax, 1A3h
0x18004b08a  mov     [rsp+6D0h+var_6A0], esi
0x18004b08e  mov     [rsp+6D0h+var_69C], ax
0x18004b093  mov     r10, cs:WPP_GLOBAL_Control
0x18004b09a  lea     r15, WPP_GLOBAL_Control
0x18004b0a1  mov     r14d, 8000000h
0x18004b0a7  cmp     r10, r15
0x18004b0aa  jz      short loc_18004B0DF
0x18004b0ac  test    [r10+1Ch], r14d
0x18004b0b0  jz      short loc_18004B0DF
0x18004b0b2  mov     rcx, [r10+10h]
0x18004b0b6  lea     rax, [rbp+5D0h+szVolumePathName]
0x18004b0bd  mov     edx, 14h
0x18004b0c2  mov     [rsp+6D0h+var_6B0], rax
0x18004b0c7  lea     r9, [rsp+6D0h+szVolumeName]
0x18004b0cc  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004b0d3  call    WPP_SF_SS
0x18004b0d8  mov     r10, cs:WPP_GLOBAL_Control
0x18004b0df  lea     rcx, [rsp+6D0h+szVolumeName]
0x18004b0e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b0e8  inc     rax
0x18004b0eb  cmp     [rcx+rax*2], si
0x18004b0ef  jnz     short loc_18004B0E8
0x18004b0f1  lea     ecx, [rax-1]
0x18004b0f4  add     rcx, rcx
0x18004b0f7  cmp     rcx, 20Ah
0x18004b0fe  jnb     loc_18004B1BE
0x18004b104  mov     [rsp+rcx+6D0h+szVolumeName], si
0x18004b109  cmp     r10, r15
0x18004b10c  jz      short loc_18004B136
0x18004b10e  test    [r10+1Ch], r14d
0x18004b112  jz      short loc_18004B136
0x18004b114  mov     rcx, [r10+10h]
0x18004b118  lea     rax, [rsp+6D0h+szVolumeName]
0x18004b11d  mov     edx, 15h
0x18004b122  mov     [rsp+6D0h+var_6B0], rax
0x18004b127  mov     r9, rbx
0x18004b12a  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004b131  call    WPP_SF_SS
0x18004b136  lea     rdx, [rsp+6D0h+szVolumeName]; String2
0x18004b13b  mov     rcx, rbx; String1
0x18004b13e  call    cs:__imp__wcsicmp
0x18004b144  mov     ecx, esi
0x18004b146  test    eax, eax
0x18004b148  setz    cl
0x18004b14b  mov     [rdi], ecx
0x18004b14d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b154  cmp     rcx, r15
0x18004b157  jz      short loc_18004B188
0x18004b159  test    [rcx+1Ch], r14d
0x18004b15d  jz      short loc_18004B188
0x18004b15f  mov     rcx, [rcx+10h]
0x18004b163  lea     rdx, aFalse; "FALSE"
0x18004b16a  test    eax, eax
0x18004b16c  lea     r9, aTrue; "TRUE"
0x18004b173  lea     r8, WPP_7ca5c123dafd3d0bdbf44829d988681f_Traceguids
0x18004b17a  cmovnz  r9, rdx
0x18004b17e  mov     edx, 16h
0x18004b183  call    WPP_SF_s
0x18004b188  mov     ebx, [rsp+6D0h+var_6A0]
0x18004b18c  lea     rcx, [rsp+6D0h+var_6A0]; this
0x18004b191  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004b196  mov     eax, ebx
0x18004b198  mov     rcx, [rbp+5D0h+var_30]
0x18004b19f  xor     rcx, rsp; StackCookie
0x18004b1a2  call    __security_check_cookie
0x18004b1a7  mov     rbx, [rsp+6D0h+arg_0]
0x18004b1af  add     rsp, 6B0h
0x18004b1b6  pop     r15
0x18004b1b8  pop     r14
0x18004b1ba  pop     rdi
0x18004b1bb  pop     rsi
0x18004b1bc  pop     rbp
0x18004b1bd  retn
0x18004b1be  call    __report_rangecheckfailure
```
