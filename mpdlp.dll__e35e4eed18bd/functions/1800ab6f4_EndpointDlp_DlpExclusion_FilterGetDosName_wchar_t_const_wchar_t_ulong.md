# EndpointDlp::DlpExclusion::FilterGetDosName(wchar_t const *,wchar_t *,ulong)

- ea: `0x1800ab6f4`
- end: `0x1800ab8f9`
- name: `?FilterGetDosName@DlpExclusion@EndpointDlp@@AEBAJPEB_WPEA_WK@Z`
- size: `517`
- prototype: `int(EndpointDlp::DlpExclusion *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18004d81c`

## callees

- `0x1800ab6f4`
- `0x18010cb40`
- `0x18010cc74`
- `0x18011e7f0`
- `0x180132300`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800ab7a9`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800ab813`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800ab7a9`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800ab813`
- `KERNEL32!GetLastError` at `0x1800ab81d`
- `KERNEL32!GetLastError` at `0x1800ab82f`
- `KERNEL32!GetLastError` at `0x1800ab81d`
- `KERNEL32!GetLastError` at `0x1800ab82f`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800ab865`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800ab865`

## pseudocode

```c
int __fastcall EndpointDlp::DlpExclusion::FilterGetDosName(EndpointDlp::DlpExclusion *this, wchar_t *a2, wchar_t *a3)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rdi
  int result; // eax
  wchar_t *v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // rcx
  DWORD cchReturnLength[4]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t szVolumePathNames[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v4 = -1;
  cchReturnLength[0] = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( !v5 )
    return -2147024735;
  v8 = a2;
  if ( a2[v5 - 1] != 92 )
  {
    if ( (unsigned __int64)(v5 + 1) >= 0x104 )
      return -2147024774;
    _mm_lfence();
    wcscpy_s(Destination, 0x104u, a2);
    wcscat_s(Destination, 0x104u, L"\\");
    v8 = Destination;
  }
  _mm_lfence();
  if ( !GetVolumeNameForVolumeMountPointW(v8, szVolumeName, 0x32u) )
  {
    if ( (unsigned __int64)(v5 + 15) >= 0x104 )
      return -2147024774;
    _mm_lfence();
    wcscpy_s(Destination, 0x104u, L"\\\\?\\GlobalRoot");
    wcscat_s(Destination, 0x104u, a2);
    if ( a2[v5 - 1] != 92 )
      wcscat_s(Destination, 0x104u, L"\\");
    if ( !GetVolumeNameForVolumeMountPointW(Destination, szVolumeName, 0x32u) )
    {
      LastError = GetLastError();
      if ( LastError == 4390 || LastError == 1 )
        return -2147024773;
      goto LABEL_15;
    }
  }
  if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x104u, cchReturnLength) )
  {
    do
      ++v4;
    while ( szVolumePathNames[v4] );
    if ( v4 && Destination[v4 + 263] == 92 )
    {
      --v4;
      if ( 2 * v4 >= 0x208 )
        _report_rangecheckfailure(v10);
      szVolumePathNames[v4] = 0;
    }
    if ( v4 < 0x104 )
    {
      wcscpy_s(a3, 0x104u, szVolumePathNames);
      return 0;
    }
    return -2147024774;
  }
LABEL_15:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800ab6f4  mov     [rsp-8+arg_0], rbx
0x1800ab6f9  mov     [rsp-8+arg_18], rsi
0x1800ab6fe  push    rbp
0x1800ab6ff  push    rdi
0x1800ab700  push    r12
0x1800ab702  push    r14
0x1800ab704  push    r15
0x1800ab706  lea     rbp, [rsp-3D0h]
0x1800ab70e  sub     rsp, 4D0h
0x1800ab715  mov     rax, cs:__security_cookie
0x1800ab71c  xor     rax, rsp
0x1800ab71f  mov     [rbp+3F0h+var_30], rax
0x1800ab726  xor     r15d, r15d
0x1800ab729  mov     r14, r8
0x1800ab72c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ab730  mov     [rsp+4F0h+cchReturnLength], r15d
0x1800ab735  mov     rdi, rbx
0x1800ab738  mov     rsi, rdx
0x1800ab73b  inc     rdi
0x1800ab73e  cmp     [rdx+rdi*2], r15w
0x1800ab743  jnz     short loc_1800AB73B
0x1800ab745  test    rdi, rdi
0x1800ab748  jnz     short loc_1800AB754
0x1800ab74a  mov     eax, 800700A1h
0x1800ab74f  jmp     loc_1800AB8CE
0x1800ab754  cmp     word ptr [rdx+rdi*2-2], 5Ch ; '\'
0x1800ab75a  mov     rcx, rsi
0x1800ab75d  mov     r12d, 104h
0x1800ab763  jz      short loc_1800AB79B
0x1800ab765  lea     rax, [rdi+1]
0x1800ab769  cmp     rax, r12
0x1800ab76c  jnb     loc_1800AB8AD
0x1800ab772  lfence
0x1800ab775  mov     r8, rsi; Source
0x1800ab778  lea     rcx, [rbp+3F0h+Destination]; Destination
0x1800ab77c  mov     edx, r12d; SizeInWords
0x1800ab77f  call    wcscpy_s
0x1800ab784  lea     r8, SubBlock; "\\"
0x1800ab78b  mov     edx, r12d; SizeInWords
0x1800ab78e  lea     rcx, [rbp+3F0h+Destination]; Destination
0x1800ab792  call    wcscat_s
0x1800ab797  lea     rcx, [rbp+3F0h+Destination]; lpszVolumeMountPoint
0x1800ab79b  lfence
0x1800ab79e  mov     r8d, 32h ; '2'; cchBufferLength
0x1800ab7a4  lea     rdx, [rsp+4F0h+szVolumeName]; lpszVolumeName
0x1800ab7a9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800ab7af  test    eax, eax
0x1800ab7b1  jnz     loc_1800AB851
0x1800ab7b7  lea     rax, [rdi+0Fh]
0x1800ab7bb  cmp     rax, r12
0x1800ab7be  jnb     loc_1800AB8AD
0x1800ab7c4  lfence
0x1800ab7c7  lea     r8, aGlobalroot; "\\\\?\\GlobalRoot"
0x1800ab7ce  mov     rdx, r12; SizeInWords
0x1800ab7d1  lea     rcx, [rbp+3F0h+Destination]; Destination
0x1800ab7d5  call    wcscpy_s
0x1800ab7da  mov     r8, rsi; Source
0x1800ab7dd  lea     rcx, [rbp+3F0h+Destination]; Destination
0x1800ab7e1  mov     rdx, r12; SizeInWords
0x1800ab7e4  call    wcscat_s
0x1800ab7e9  cmp     word ptr [rsi+rdi*2-2], 5Ch ; '\'
0x1800ab7ef  jz      short loc_1800AB804
0x1800ab7f1  lea     r8, SubBlock; "\\"
0x1800ab7f8  mov     rdx, r12; SizeInWords
0x1800ab7fb  lea     rcx, [rbp+3F0h+Destination]; Destination
0x1800ab7ff  call    wcscat_s
0x1800ab804  mov     r8d, 32h ; '2'; cchBufferLength
0x1800ab80a  lea     rdx, [rsp+4F0h+szVolumeName]; lpszVolumeName
0x1800ab80f  lea     rcx, [rbp+3F0h+Destination]; lpszVolumeMountPoint
0x1800ab813  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800ab819  test    eax, eax
0x1800ab81b  jnz     short loc_1800AB851
0x1800ab81d  call    cs:__imp_GetLastError
0x1800ab823  cmp     eax, 1126h
0x1800ab828  jz      short loc_1800AB84A
0x1800ab82a  cmp     eax, 1
0x1800ab82d  jz      short loc_1800AB84A
0x1800ab82f  call    cs:__imp_GetLastError
0x1800ab835  test    eax, eax
0x1800ab837  jle     loc_1800AB8CE
0x1800ab83d  movzx   eax, ax
0x1800ab840  or      eax, 80070000h
0x1800ab845  jmp     loc_1800AB8CE
0x1800ab84a  mov     eax, 8007007Bh
0x1800ab84f  jmp     short loc_1800AB8CE
0x1800ab851  lea     r9, [rsp+4F0h+cchReturnLength]; lpcchReturnLength
0x1800ab856  mov     r8d, r12d; cchBufferLength
0x1800ab859  lea     rdx, [rbp+3F0h+szVolumePathNames]; lpszVolumePathNames
0x1800ab860  lea     rcx, [rsp+4F0h+szVolumeName]; lpszVolumeName
0x1800ab865  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800ab86b  test    eax, eax
0x1800ab86d  jz      short loc_1800AB82F
0x1800ab86f  lea     rax, [rbp+3F0h+szVolumePathNames]
0x1800ab876  inc     rbx
0x1800ab879  cmp     [rax+rbx*2], r15w
0x1800ab87e  jnz     short loc_1800AB876
0x1800ab880  test    rbx, rbx
0x1800ab883  jz      short loc_1800AB8A8
0x1800ab885  cmp     [rbp+rbx*2+3F0h+var_242], 5Ch ; '\'
0x1800ab88e  jnz     short loc_1800AB8A8
0x1800ab890  dec     rbx
0x1800ab893  lea     rax, [rbx+rbx]
0x1800ab897  cmp     rax, 208h
0x1800ab89d  jnb     short loc_1800AB8B4
0x1800ab89f  mov     [rbp+rax+3F0h+szVolumePathNames], r15w
0x1800ab8a8  cmp     rbx, r12
0x1800ab8ab  jb      short loc_1800AB8BA
0x1800ab8ad  mov     eax, 8007007Ah
0x1800ab8b2  jmp     short loc_1800AB8CE
0x1800ab8b4  call    __report_rangecheckfailure
0x1800ab8ba  lea     r8, [rbp+3F0h+szVolumePathNames]; Source
0x1800ab8c1  mov     rdx, r12; SizeInWords
0x1800ab8c4  mov     rcx, r14; Destination
0x1800ab8c7  call    wcscpy_s
0x1800ab8cc  xor     eax, eax
0x1800ab8ce  mov     rcx, [rbp+3F0h+var_30]
0x1800ab8d5  xor     rcx, rsp; StackCookie
0x1800ab8d8  call    __security_check_cookie
0x1800ab8dd  lea     r11, [rsp+4F0h+var_20]
0x1800ab8e5  mov     rbx, [r11+30h]
0x1800ab8e9  mov     rsi, [r11+48h]
0x1800ab8ed  mov     rsp, r11
0x1800ab8f0  pop     r15
0x1800ab8f2  pop     r14
0x1800ab8f4  pop     r12
0x1800ab8f6  pop     rdi
0x1800ab8f7  pop     rbp
0x1800ab8f8  retn
```
