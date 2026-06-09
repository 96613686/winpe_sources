# GetComputerNameW

- ea: `0x18003c870`
- end: `0x18003cc5f`
- name: `GetComputerNameW`
- size: `1007`
- prototype: `BOOL __stdcall(LPWSTR lpBuffer, LPDWORD nSize)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003c1f0`
- `0x18003c730`

## callees

- `0x18000ccf0`
- `0x18003a504`
- `0x18003c870`
- `0x18004113c`
- `0x180045364`
- `0x180082751`
- `0x180084010`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18003c9dc`
- `ntdll!NtOpenKey` at `0x18003c9dc`
- `ntdll!NtClose` at `0x18003cc38`
- `ntdll!NtClose` at `0x18003cc38`
- `ntdll!wcslen` at `0x18003caa5`
- `ntdll!wcslen` at `0x18003cbc7`
- `ntdll!wcslen` at `0x18003caa5`
- `ntdll!wcslen` at `0x18003cbc7`
- `ntdll!RtlSetLastWin32Error` at `0x18003c8da`
- `ntdll!RtlSetLastWin32Error` at `0x18003c926`
- `ntdll!RtlSetLastWin32Error` at `0x18003ca32`
- `ntdll!RtlSetLastWin32Error` at `0x18003c8da`
- `ntdll!RtlSetLastWin32Error` at `0x18003c926`
- `ntdll!RtlSetLastWin32Error` at `0x18003ca32`
- `ntdll!RtlEnterCriticalSection` at `0x18003cad8`
- `ntdll!RtlEnterCriticalSection` at `0x18003cad8`
- `ntdll!RtlLeaveCriticalSection` at `0x18003cc1a`
- `ntdll!RtlLeaveCriticalSection` at `0x18003cc1a`
- `ntdll!RtlInitUnicodeString` at `0x18003c99d`
- `ntdll!RtlInitUnicodeString` at `0x18003c99d`
- `ntdll!RtlAllocateHeap` at `0x18003cb96`
- `ntdll!RtlAllocateHeap` at `0x18003cb96`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c8ee`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c906`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c93b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cac5`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cb62`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cbd6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cbe8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cc07`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c8ee`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c906`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c93b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cac5`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cb62`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cbd6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cbe8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003cc07`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18003c8b7`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18003c8b7`

## string_xrefs

- `0x18003ca4b`: `ComputerName`
- `0x18003c992`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName`
- `0x18003ca14`: `ActiveComputerName`
- `0x18003cb02`: `\Registry\Machine\System\Setup`
- `0x18003cb33`: `\Registry\Machine\System\Setup`

## pseudocode

```c
BOOL __stdcall GetComputerNameW(LPWSTR lpBuffer, LPDWORD nSize)
{
  DWORD v2; // r8d
  DWORD EnvironmentVariableW; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD v10; // r14d
  BOOL v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  DWORD v20; // edi
  __int64 v22; // rax
  int ComputerName; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  NTSTATUS v28; // eax
  int NameFromValue; // eax
  int v30; // eax
  unsigned int VolatileNameInReg; // eax
  __int64 GlobalData; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  wchar_t *Heap; // rax
  const wchar_t *v39; // r14
  int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  void *KeyHandle; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  int v53; // [rsp+B0h] [rbp+30h] BYREF
  int v54; // [rsp+B8h] [rbp+38h] BYREF

  v2 = *nSize;
  KeyHandle = 0;
  v53 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  EnvironmentVariableW = GetEnvironmentVariableW(L"_CLUSTER_NETWORK_NAME_", lpBuffer, v2);
  v10 = EnvironmentVariableW;
  if ( EnvironmentVariableW )
  {
    if ( *nSize < EnvironmentVariableW )
    {
      v11 = 0;
      RtlSetLastWin32Error(0x6Fu);
    }
    else
    {
      v11 = 1;
    }
    *nSize = v10;
    return v11;
  }
  v13 = *(_QWORD *)(KernelBaseGetGlobalData(v7, v6, v8, v9) + 160);
  if ( !v13 )
  {
    if ( gpTermsrvGetComputerName )
    {
      ComputerName = gpTermsrvGetComputerName(lpBuffer, nSize);
      if ( ComputerName != 1237 )
      {
        if ( ComputerName == 111 )
          goto LABEL_44;
LABEL_27:
        if ( lpBuffer && *nSize )
          *nSize = wcslen(lpBuffer);
        v11 = 1;
        if ( dword_1800BD314 )
        {
          GlobalData = KernelBaseGetGlobalData(v25, v24, v26, v27);
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(GlobalData + 176));
          v54 = 4;
          if ( (int)BasepGetValueFromReg(0, L"\\Registry\\Machine\\System\\Setup", L"OOBEInProgress", &v53, &v54) >= 0
            && v53
            || (v54 = 4,
                (int)BasepGetValueFromReg(
                       0,
                       L"\\Registry\\Machine\\System\\Setup",
                       L"SystemSetupInProgress",
                       &v53,
                       &v54) >= 0)
            && v53 )
          {
            v37 = 0;
            dword_1800BD314 = 0;
          }
          else
          {
            v37 = dword_1800BD314;
          }
          if ( v37 )
          {
            v34 = *(_QWORD *)(KernelBaseGetGlobalData(v34, v33, v35, v36) + 160);
            if ( !v34 )
            {
              Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (*nSize + 1));
              v39 = Heap;
              if ( Heap )
              {
                memcpy_0(Heap, lpBuffer, 2LL * *nSize);
                v39[*nSize] = 0;
                v40 = wcslen(v39);
                *(_DWORD *)(KernelBaseGetGlobalData(v42, v41, v43, v44) + 168) = v40;
                *(_QWORD *)(KernelBaseGetGlobalData(v46, v45, v47, v48) + 160) = v39;
              }
              else
              {
                dword_1800BD314 = 0;
              }
            }
          }
          v49 = KernelBaseGetGlobalData(v34, v33, v35, v36);
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v49 + 176));
        }
        goto LABEL_45;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v28 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v25 = (unsigned int)v28;
    if ( v28 == -1073741772 )
    {
      if ( lpBuffer )
        *lpBuffer = 0;
      *nSize = 0;
      goto LABEL_27;
    }
    if ( v28 >= 0 )
    {
      NameFromValue = GetNameFromValue(KeyHandle, L"ActiveComputerName", lpBuffer, nSize);
      if ( NameFromValue == -2147483643 )
      {
        RtlSetLastWin32Error(0x6Fu);
LABEL_44:
        v11 = 0;
LABEL_45:
        if ( KeyHandle )
          NtClose(KeyHandle);
        return v11;
      }
      if ( NameFromValue >= 0 )
        goto LABEL_27;
      v30 = GetNameFromValue(KeyHandle, L"ComputerName", lpBuffer, nSize);
      v25 = (unsigned int)v30;
      if ( v30 == -1073741772 )
      {
        *lpBuffer = 0;
        *nSize = 0;
        goto LABEL_27;
      }
      if ( v30 >= 0 )
      {
        VolatileNameInReg = BaseCreateVolatileNameInReg(lpBuffer);
        v24 = 0x80000000LL;
        v25 = VolatileNameInReg;
        if ( (int)(VolatileNameInReg + 0x80000000) < 0 || VolatileNameInReg == -1073741790 )
          goto LABEL_27;
      }
    }
    BaseSetLastNTError(v25);
    goto LABEL_44;
  }
  v17 = *(unsigned int *)(KernelBaseGetGlobalData(v13, v12, v14, v15) + 168);
  v20 = v17 + 1;
  if ( *nSize >= (int)v17 + 1 )
  {
    *nSize = v17;
    v22 = KernelBaseGetGlobalData(v17, v16, v18, v19);
    memcpy_0(lpBuffer, *(const void **)(v22 + 160), 2LL * v20);
    return 1;
  }
  else
  {
    *nSize = v20;
    RtlSetLastWin32Error(0x6Fu);
    return 0;
  }
}

```

## disassembly

```asm
0x18003c870  mov     [rsp-18h+arg_0], rbx
0x18003c875  mov     [rsp-18h+arg_8], rsi
0x18003c87a  push    rbp
0x18003c87b  push    rdi
0x18003c87c  push    r14
0x18003c87e  mov     rbp, rsp
0x18003c881  sub     rsp, 80h
0x18003c888  mov     r8d, [rdx]; nSize
0x18003c88b  xorps   xmm0, xmm0
0x18003c88e  xor     eax, eax
0x18003c890  mov     rbx, rdx
0x18003c893  mov     rdx, rcx; lpBuffer
0x18003c896  mov     [rbp+KeyHandle], rax
0x18003c89a  mov     rsi, rcx
0x18003c89d  mov     [rbp+arg_10], eax
0x18003c8a0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003c8a4  lea     rcx, aClusterNetwork; "_CLUSTER_NETWORK_NAME_"
0x18003c8ab  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18003c8af  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003c8b3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18003c8b7  call    cs:__imp_GetEnvironmentVariableW
0x18003c8be  nop     dword ptr [rax+rax+00h]
0x18003c8c3  mov     r14d, eax
0x18003c8c6  test    eax, eax
0x18003c8c8  jz      short loc_18003C8EE
0x18003c8ca  cmp     [rbx], eax
0x18003c8cc  jb      short loc_18003C8D5
0x18003c8ce  mov     edi, 1
0x18003c8d3  jmp     short loc_18003C8E6
0x18003c8d5  xor     edi, edi
0x18003c8d7  lea     ecx, [rdi+6Fh]; LastError
0x18003c8da  call    cs:__imp_RtlSetLastWin32Error
0x18003c8e1  nop     dword ptr [rax+rax+00h]
0x18003c8e6  mov     [rbx], r14d
0x18003c8e9  jmp     loc_18003CC44
0x18003c8ee  call    cs:__imp_KernelBaseGetGlobalData
0x18003c8f5  nop     dword ptr [rax+rax+00h]
0x18003c8fa  mov     rcx, [rax+0A0h]
0x18003c901  test    rcx, rcx
0x18003c904  jz      short loc_18003C966
0x18003c906  call    cs:__imp_KernelBaseGetGlobalData
0x18003c90d  nop     dword ptr [rax+rax+00h]
0x18003c912  mov     ecx, [rax+0A8h]
0x18003c918  lea     edi, [rcx+1]
0x18003c91b  cmp     [rbx], edi
0x18003c91d  jnb     short loc_18003C939
0x18003c91f  mov     ecx, 6Fh ; 'o'; LastError
0x18003c924  mov     [rbx], edi
0x18003c926  call    cs:__imp_RtlSetLastWin32Error
0x18003c92d  nop     dword ptr [rax+rax+00h]
0x18003c932  xor     eax, eax
0x18003c934  jmp     loc_18003CC46
0x18003c939  mov     [rbx], ecx
0x18003c93b  call    cs:__imp_KernelBaseGetGlobalData
0x18003c942  nop     dword ptr [rax+rax+00h]
0x18003c947  mov     r8d, edi
0x18003c94a  mov     rcx, rsi; void *
0x18003c94d  add     r8, r8; Size
0x18003c950  mov     rdx, [rax+0A0h]; Src
0x18003c957  call    memcpy_0
0x18003c95c  mov     eax, 1
0x18003c961  jmp     loc_18003CC46
0x18003c966  mov     rax, cs:gpTermsrvGetComputerName
0x18003c96d  test    rax, rax
0x18003c970  jz      short loc_18003C992
0x18003c972  mov     rdx, rbx
0x18003c975  mov     rcx, rsi
0x18003c978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c97d  cmp     eax, 4D5h
0x18003c982  jz      short loc_18003C992
0x18003c984  cmp     eax, 6Fh ; 'o'
0x18003c987  jnz     loc_18003CA98
0x18003c98d  jmp     loc_18003CC2D
0x18003c992  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003c999  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003c99d  call    cs:__imp_RtlInitUnicodeString
0x18003c9a4  nop     dword ptr [rax+rax+00h]
0x18003c9a9  lea     rax, [rbp+DestinationString]
0x18003c9ad  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003c9b4  xorps   xmm0, xmm0
0x18003c9b7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18003c9bb  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003c9bf  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003c9c7  mov     edx, 20019h; DesiredAccess
0x18003c9cc  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003c9d3  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18003c9d7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c9dc  call    cs:__imp_NtOpenKey
0x18003c9e3  nop     dword ptr [rax+rax+00h]
0x18003c9e8  mov     edi, 0C0000034h
0x18003c9ed  mov     ecx, eax
0x18003c9ef  cmp     eax, edi
0x18003c9f1  jnz     short loc_18003CA08
0x18003c9f3  test    rsi, rsi
0x18003c9f6  jz      short loc_18003C9FD
0x18003c9f8  xor     eax, eax
0x18003c9fa  mov     [rsi], ax
0x18003c9fd  mov     dword ptr [rbx], 0
0x18003ca03  jmp     loc_18003CA98
0x18003ca08  test    eax, eax
0x18003ca0a  js      loc_18003CC28
0x18003ca10  mov     rcx, [rbp+KeyHandle]
0x18003ca14  lea     rdx, aActivecomputer; "ActiveComputerName"
0x18003ca1b  mov     r9, rbx
0x18003ca1e  mov     r8, rsi
0x18003ca21  call    GetNameFromValue
0x18003ca26  cmp     eax, 80000005h
0x18003ca2b  jnz     short loc_18003CA43
0x18003ca2d  mov     ecx, 6Fh ; 'o'; LastError
0x18003ca32  call    cs:__imp_RtlSetLastWin32Error
0x18003ca39  nop     dword ptr [rax+rax+00h]
0x18003ca3e  jmp     loc_18003CC2D
0x18003ca43  test    eax, eax
0x18003ca45  jns     short loc_18003CA98
0x18003ca47  mov     rcx, [rbp+KeyHandle]
0x18003ca4b  lea     rdx, aComputername; "ComputerName"
0x18003ca52  mov     r9, rbx
0x18003ca55  mov     r8, rsi
0x18003ca58  call    GetNameFromValue
0x18003ca5d  mov     ecx, eax
0x18003ca5f  cmp     eax, edi
0x18003ca61  jnz     short loc_18003CA6C
0x18003ca63  xor     eax, eax
0x18003ca65  mov     [rsi], ax
0x18003ca68  mov     [rbx], eax
0x18003ca6a  jmp     short loc_18003CA98
0x18003ca6c  test    eax, eax
0x18003ca6e  js      loc_18003CC28
0x18003ca74  mov     rdx, rbx
0x18003ca77  mov     rcx, rsi; Data
0x18003ca7a  call    BaseCreateVolatileNameInReg
0x18003ca7f  mov     edx, 80000000h
0x18003ca84  mov     ecx, eax
0x18003ca86  add     eax, edx
0x18003ca88  test    edx, eax
0x18003ca8a  jnz     short loc_18003CA98
0x18003ca8c  cmp     ecx, 0C0000022h
0x18003ca92  jnz     loc_18003CC28
0x18003ca98  test    rsi, rsi
0x18003ca9b  jz      short loc_18003CAB3
0x18003ca9d  cmp     dword ptr [rbx], 0
0x18003caa0  jz      short loc_18003CAB3
0x18003caa2  mov     rcx, rsi; String
0x18003caa5  call    cs:__imp_wcslen
0x18003caac  nop     dword ptr [rax+rax+00h]
0x18003cab1  mov     [rbx], eax
0x18003cab3  cmp     cs:dword_1800BD314, 0
0x18003caba  mov     edi, 1
0x18003cabf  jz      loc_18003CC2F
0x18003cac5  call    cs:__imp_KernelBaseGetGlobalData
0x18003cacc  nop     dword ptr [rax+rax+00h]
0x18003cad1  lea     rcx, [rax+0B0h]; CriticalSection
0x18003cad8  call    cs:__imp_RtlEnterCriticalSection
0x18003cadf  nop     dword ptr [rax+rax+00h]
0x18003cae4  lea     rax, [rbp+arg_18]
0x18003cae8  xor     ecx, ecx
0x18003caea  lea     r14d, [rdi+3]
0x18003caee  mov     [rsp+80h+var_60], rax
0x18003caf3  lea     r9, [rbp+arg_10]
0x18003caf7  mov     [rbp+arg_18], r14d
0x18003cafb  lea     r8, aOobeinprogress; "OOBEInProgress"
0x18003cb02  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\Setup"
0x18003cb09  call    BasepGetValueFromReg
0x18003cb0e  test    eax, eax
0x18003cb10  js      short loc_18003CB19
0x18003cb12  mov     eax, [rbp+arg_10]
0x18003cb15  test    eax, eax
0x18003cb17  jnz     short loc_18003CB4A
0x18003cb19  lea     rax, [rbp+arg_18]
0x18003cb1d  mov     [rbp+arg_18], r14d
0x18003cb21  lea     r9, [rbp+arg_10]
0x18003cb25  mov     [rsp+80h+var_60], rax
0x18003cb2a  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x18003cb31  xor     ecx, ecx
0x18003cb33  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\Setup"
0x18003cb3a  call    BasepGetValueFromReg
0x18003cb3f  test    eax, eax
0x18003cb41  js      short loc_18003CB54
0x18003cb43  mov     eax, [rbp+arg_10]
0x18003cb46  test    eax, eax
0x18003cb48  jz      short loc_18003CB54
0x18003cb4a  xor     eax, eax
0x18003cb4c  mov     cs:dword_1800BD314, eax
0x18003cb52  jmp     short loc_18003CB5A
0x18003cb54  mov     eax, cs:dword_1800BD314
0x18003cb5a  test    eax, eax
0x18003cb5c  jz      loc_18003CC07
0x18003cb62  call    cs:__imp_KernelBaseGetGlobalData
0x18003cb69  nop     dword ptr [rax+rax+00h]
0x18003cb6e  mov     rcx, [rax+0A0h]
0x18003cb75  test    rcx, rcx
0x18003cb78  jnz     loc_18003CC07
0x18003cb7e  mov     r8d, [rbx]
0x18003cb81  xor     edx, edx; Flags
0x18003cb83  mov     rcx, gs:60h
0x18003cb8c  add     r8d, edi
0x18003cb8f  add     r8, r8; Size
0x18003cb92  mov     rcx, [rcx+30h]; HeapHandle
0x18003cb96  call    cs:__imp_RtlAllocateHeap
0x18003cb9d  nop     dword ptr [rax+rax+00h]
0x18003cba2  mov     r14, rax
0x18003cba5  test    rax, rax
0x18003cba8  jz      short loc_18003CBFD
0x18003cbaa  mov     r8d, [rbx]
0x18003cbad  mov     rdx, rsi; Src
0x18003cbb0  add     r8, r8; Size
0x18003cbb3  mov     rcx, rax; void *
0x18003cbb6  call    memcpy_0
0x18003cbbb  mov     edx, [rbx]
0x18003cbbd  xor     ecx, ecx
0x18003cbbf  mov     [r14+rdx*2], cx
0x18003cbc4  mov     rcx, r14; String
0x18003cbc7  call    cs:__imp_wcslen
0x18003cbce  nop     dword ptr [rax+rax+00h]
0x18003cbd3  mov     rbx, rax
0x18003cbd6  call    cs:__imp_KernelBaseGetGlobalData
0x18003cbdd  nop     dword ptr [rax+rax+00h]
0x18003cbe2  mov     [rax+0A8h], ebx
0x18003cbe8  call    cs:__imp_KernelBaseGetGlobalData
0x18003cbef  nop     dword ptr [rax+rax+00h]
0x18003cbf4  mov     [rax+0A0h], r14
0x18003cbfb  jmp     short loc_18003CC07
0x18003cbfd  mov     cs:dword_1800BD314, 0
0x18003cc07  call    cs:__imp_KernelBaseGetGlobalData
0x18003cc0e  nop     dword ptr [rax+rax+00h]
0x18003cc13  lea     rcx, [rax+0B0h]; CriticalSection
0x18003cc1a  call    cs:__imp_RtlLeaveCriticalSection
0x18003cc21  nop     dword ptr [rax+rax+00h]
0x18003cc26  jmp     short loc_18003CC2F
0x18003cc28  call    BaseSetLastNTError
0x18003cc2d  xor     edi, edi
0x18003cc2f  mov     rcx, [rbp+KeyHandle]; Handle
0x18003cc33  test    rcx, rcx
0x18003cc36  jz      short loc_18003CC44
0x18003cc38  call    cs:__imp_NtClose
0x18003cc3f  nop     dword ptr [rax+rax+00h]
0x18003cc44  mov     eax, edi
0x18003cc46  lea     r11, [rsp+80h+var_s0]
0x18003cc4e  mov     rbx, [r11+20h]
0x18003cc52  mov     rsi, [r11+28h]
0x18003cc56  mov     rsp, r11
0x18003cc59  pop     r14
0x18003cc5b  pop     rdi
0x18003cc5c  pop     rbp
0x18003cc5d  retn
```
