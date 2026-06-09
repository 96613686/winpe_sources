# GetProcessInfo

- ea: `0x18001e50c`
- end: `0x18001e732`
- name: `GetProcessInfo`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18001eb10`

## callees

- `0x180014d6c`
- `0x180018e48`
- `0x1800198c4`
- `0x18001e32c`
- `0x18001e368`
- `0x18001e3ac`
- `0x18001e50c`
- `0x18001e738`
- `0x18001ead4`
- `0x18001f175`
- `0x18001f1b0`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18001e6c4`
- `ntdll!_wcsicmp` at `0x18001e6d8`
- `ntdll!_wcsicmp` at `0x18001e6c4`
- `ntdll!_wcsicmp` at `0x18001e6d8`
- `ntdll!wcsrchr` at `0x18001e639`
- `ntdll!wcsrchr` at `0x18001e639`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e5f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e5f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e57f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e57f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18001e5a1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18001e5a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e6e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e6e9`

## string_xrefs

- `0x18001e6ce`: `dllhost.exe`

## pseudocode

```c
int GetProcessInfo()
{
  wchar_t *v0; // rax
  HANDLE CurrentProcess; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  size_t v3; // rdx
  WCHAR *v4; // rbx
  wchar_t *v5; // rax
  ULONGLONG v6; // rdx
  ULONGLONG v7; // rdi
  __int64 v8; // rbx
  DWORD CurrentProcessId; // eax
  size_t pcchLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME CreationTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME UserTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME KernelTime; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ExitTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[260]; // [rsp+60h] [rbp-A0h] BYREF
  char v17; // [rsp+268h] [rbp+168h] BYREF

  if ( g_pCertInUseProcessInfo || (v0 = (wchar_t *)CertInUseZeroAlloc(24), (g_pCertInUseProcessInfo = (__int64)v0) != 0) )
  {
    CreationTime = 0;
    ExitTime = 0;
    KernelTime = 0;
    UserTime = 0;
    CurrentProcess = GetCurrentProcess();
    if ( GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime)
      && (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))FiletimeToString)(
                         CreationTime,
                         g_pCertInUseProcessInfo + 8) )
    {
      CertInUseFree(g_pCertInUseProcessInfo + 8);
    }
    memset_0(Filename, 0, sizeof(Filename));
    LODWORD(v0) = GetModuleFileNameW(0, Filename, 0x104u);
    if ( (_DWORD)v0 )
    {
      IsEnabledDeviceUsageNoInline = Feature_Fix_CIU_Get_Module_Name_OOBR__private_IsEnabledDeviceUsageNoInline();
      v3 = 92;
      if ( IsEnabledDeviceUsageNoInline )
      {
        v5 = wcsrchr(Filename, 0x5Cu);
        v4 = v5 + 1;
        if ( !v5 )
          v4 = Filename;
      }
      else
      {
        v4 = (WCHAR *)&v17;
        while ( *v4 != 92 )
        {
          if ( --v4 == Filename )
          {
            if ( *v4 != 92 )
              goto LABEL_15;
            break;
          }
        }
        ++v4;
      }
LABEL_15:
      pcchLength = 0;
      LODWORD(v0) = StringCchLengthW(v4, v3, &pcchLength);
      if ( (int)v0 >= 0 )
      {
        LODWORD(v0) = pcchLength;
        v7 = pcchLength + 1;
        if ( pcchLength + 1 >= pcchLength )
        {
          ++pcchLength;
          LODWORD(v0) = ULongLongMult(v7, v6, &pcchLength);
          if ( (int)v0 >= 0 )
          {
            v0 = (wchar_t *)CertInUseZeroAlloc(pcchLength);
            *(_QWORD *)g_pCertInUseProcessInfo = v0;
            if ( v0 )
            {
              StringCchCopyW(v0, v7, v4);
              if ( !_wcsicmp(v4, L"svchost.exe") || (LODWORD(v0) = _wcsicmp(v4, L"dllhost.exe"), !(_DWORD)v0) )
              {
                v8 = g_pCertInUseProcessInfo;
                CurrentProcessId = GetCurrentProcessId();
                LODWORD(v0) = GetServiceTag(CurrentProcessId, v8 + 16);
                if ( (_DWORD)v0 )
                  LODWORD(v0) = CertInUseFree(g_pCertInUseProcessInfo + 16);
              }
            }
          }
        }
      }
    }
  }
  return (int)v0;
}

```

## disassembly

```asm
0x18001e50c  mov     [rsp-8+arg_0], rbx
0x18001e511  mov     [rsp-8+arg_8], rdi
0x18001e516  push    rbp
0x18001e517  lea     rbp, [rsp-180h]
0x18001e51f  sub     rsp, 280h
0x18001e526  mov     rax, cs:__security_cookie
0x18001e52d  xor     rax, rsp
0x18001e530  mov     [rbp+180h+var_10], rax
0x18001e537  cmp     cs:g_pCertInUseProcessInfo, 0
0x18001e53f  jnz     short loc_18001E55B
0x18001e541  mov     ecx, 18h
0x18001e546  call    CertInUseZeroAlloc
0x18001e54b  mov     cs:g_pCertInUseProcessInfo, rax
0x18001e552  test    rax, rax
0x18001e555  jz      loc_18001E70E
0x18001e55b  mov     qword ptr [rsp+280h+CreationTime.dwLowDateTime], 0
0x18001e564  mov     qword ptr [rsp+280h+ExitTime.dwLowDateTime], 0
0x18001e56d  mov     qword ptr [rsp+280h+KernelTime.dwLowDateTime], 0
0x18001e576  mov     qword ptr [rsp+280h+UserTime.dwLowDateTime], 0
0x18001e57f  call    cs:__imp_GetCurrentProcess
0x18001e585  mov     rcx, rax; hProcess
0x18001e588  lea     r9, [rsp+280h+KernelTime]; lpKernelTime
0x18001e58d  lea     rax, [rsp+280h+UserTime]
0x18001e592  lea     r8, [rsp+280h+ExitTime]; lpExitTime
0x18001e597  mov     [rsp+280h+lpUserTime], rax; lpUserTime
0x18001e59c  lea     rdx, [rsp+280h+CreationTime]; lpCreationTime
0x18001e5a1  call    cs:__imp_GetProcessTimes
0x18001e5a7  test    eax, eax
0x18001e5a9  jz      short loc_18001E5D4
0x18001e5ab  mov     rdx, cs:g_pCertInUseProcessInfo
0x18001e5b2  mov     rcx, qword ptr [rsp+280h+CreationTime.dwLowDateTime]
0x18001e5b7  add     rdx, 8
0x18001e5bb  call    FiletimeToString
0x18001e5c0  test    eax, eax
0x18001e5c2  jz      short loc_18001E5D4
0x18001e5c4  mov     rcx, cs:g_pCertInUseProcessInfo
0x18001e5cb  add     rcx, 8
0x18001e5cf  call    CertInUseFree
0x18001e5d4  xor     edx, edx; Val
0x18001e5d6  lea     rcx, [rsp+280h+Filename]; void *
0x18001e5db  mov     r8d, 208h; Size
0x18001e5e1  call    memset_0
0x18001e5e6  mov     r8d, 104h; nSize
0x18001e5ec  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18001e5f1  xor     ecx, ecx; hModule
0x18001e5f3  call    cs:__imp_GetModuleFileNameW
0x18001e5f9  test    eax, eax
0x18001e5fb  jz      loc_18001E70E
0x18001e601  call    Feature_Fix_CIU_Get_Module_Name_OOBR__private_IsEnabledDeviceUsageNoInline
0x18001e606  mov     edx, 5Ch ; '\'; Ch
0x18001e60b  test    eax, eax
0x18001e60d  jnz     short loc_18001E634
0x18001e60f  lea     rbx, [rbp+180h+var_18]
0x18001e616  cmp     [rbx], dx
0x18001e619  jz      short loc_18001E62E
0x18001e61b  sub     rbx, 2
0x18001e61f  lea     rax, [rsp+280h+Filename]
0x18001e624  cmp     rbx, rax
0x18001e627  jnz     short loc_18001E616
0x18001e629  cmp     [rbx], dx
0x18001e62c  jnz     short loc_18001E64D
0x18001e62e  add     rbx, 2
0x18001e632  jmp     short loc_18001E64D
0x18001e634  lea     rcx, [rsp+280h+Filename]; Str
0x18001e639  call    cs:__imp_wcsrchr
0x18001e63f  lea     rbx, [rax+2]
0x18001e643  test    rax, rax
0x18001e646  jnz     short loc_18001E64D
0x18001e648  lea     rbx, [rsp+280h+Filename]
0x18001e64d  lea     r8, [rsp+280h+pcchLength]; pcchLength
0x18001e652  mov     [rsp+280h+pcchLength], 0
0x18001e65b  mov     rcx, rbx; psz
0x18001e65e  call    StringCchLengthW
0x18001e663  test    eax, eax
0x18001e665  js      loc_18001E70E
0x18001e66b  mov     rax, [rsp+280h+pcchLength]
0x18001e670  lea     rdi, [rax+1]
0x18001e674  cmp     rdi, rax
0x18001e677  jb      loc_18001E70E
0x18001e67d  lea     r8, [rsp+280h+pcchLength]; pullResult
0x18001e682  mov     [rsp+280h+pcchLength], rdi
0x18001e687  mov     rcx, rdi; ullMultiplicand
0x18001e68a  call    ULongLongMult
0x18001e68f  test    eax, eax
0x18001e691  js      short loc_18001E70E
0x18001e693  mov     rcx, [rsp+280h+pcchLength]
0x18001e698  call    CertInUseZeroAlloc
0x18001e69d  mov     rcx, cs:g_pCertInUseProcessInfo
0x18001e6a4  mov     [rcx], rax
0x18001e6a7  test    rax, rax
0x18001e6aa  jz      short loc_18001E70E
0x18001e6ac  mov     r8, rbx; pszSrc
0x18001e6af  mov     rdx, rdi; cchDest
0x18001e6b2  mov     rcx, rax; pszDest
0x18001e6b5  call    StringCchCopyW
0x18001e6ba  lea     rdx, aSvchostExe; "svchost.exe"
0x18001e6c1  mov     rcx, rbx; String1
0x18001e6c4  call    cs:__imp__wcsicmp
0x18001e6ca  test    eax, eax
0x18001e6cc  jz      short loc_18001E6E2
0x18001e6ce  lea     rdx, aDllhostExe; "dllhost.exe"
0x18001e6d5  mov     rcx, rbx; String1
0x18001e6d8  call    cs:__imp__wcsicmp
0x18001e6de  test    eax, eax
0x18001e6e0  jnz     short loc_18001E70E
0x18001e6e2  mov     rbx, cs:g_pCertInUseProcessInfo
0x18001e6e9  call    cs:__imp_GetCurrentProcessId
0x18001e6ef  mov     ecx, eax
0x18001e6f1  lea     rdx, [rbx+10h]
0x18001e6f5  call    GetServiceTag
0x18001e6fa  test    eax, eax
0x18001e6fc  jz      short loc_18001E70E
0x18001e6fe  mov     rcx, cs:g_pCertInUseProcessInfo
0x18001e705  add     rcx, 10h
0x18001e709  call    CertInUseFree
0x18001e70e  mov     rcx, [rbp+180h+var_10]
0x18001e715  xor     rcx, rsp; StackCookie
0x18001e718  call    __security_check_cookie
0x18001e71d  lea     r11, [rsp+280h+var_s0]
0x18001e725  mov     rbx, [r11+10h]
0x18001e729  mov     rdi, [r11+18h]
0x18001e72d  mov     rsp, r11
0x18001e730  pop     rbp
0x18001e731  retn
```
