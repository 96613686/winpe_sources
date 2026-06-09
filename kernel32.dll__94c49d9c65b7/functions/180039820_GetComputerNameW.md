# GetComputerNameW

- ea: `0x180039820`
- end: `0x180039b92`
- name: `GetComputerNameW`
- size: `882`
- prototype: `BOOL __stdcall(LPWSTR lpBuffer, LPDWORD nSize)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039230`
- `0x180039700`

## callees

- `0x18000f920`
- `0x180037974`
- `0x180039820`
- `0x18003d8e0`
- `0x180041518`
- `0x18007a7d1`
- `0x18007c010`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180039962`
- `ntdll!NtOpenKey` at `0x180039962`
- `ntdll!NtClose` at `0x180039b72`
- `ntdll!NtClose` at `0x180039b72`
- `ntdll!wcslen` at `0x180039a1f`
- `ntdll!wcslen` at `0x180039b1f`
- `ntdll!wcslen` at `0x180039a1f`
- `ntdll!wcslen` at `0x180039b1f`
- `ntdll!RtlSetLastWin32Error` at `0x180039884`
- `ntdll!RtlSetLastWin32Error` at `0x1800398be`
- `ntdll!RtlSetLastWin32Error` at `0x1800399b2`
- `ntdll!RtlSetLastWin32Error` at `0x180039884`
- `ntdll!RtlSetLastWin32Error` at `0x1800398be`
- `ntdll!RtlSetLastWin32Error` at `0x1800399b2`
- `ntdll!RtlEnterCriticalSection` at `0x180039a46`
- `ntdll!RtlEnterCriticalSection` at `0x180039a46`
- `ntdll!RtlLeaveCriticalSection` at `0x180039b5a`
- `ntdll!RtlLeaveCriticalSection` at `0x180039b5a`
- `ntdll!RtlInitUnicodeString` at `0x180039929`
- `ntdll!RtlInitUnicodeString` at `0x180039929`
- `ntdll!RtlAllocateHeap` at `0x180039af4`
- `ntdll!RtlAllocateHeap` at `0x180039af4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039892`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800398a4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800398cd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039a39`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039aca`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039b28`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039b34`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039b4d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039892`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800398a4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800398cd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039a39`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039aca`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039b28`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039b34`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180039b4d`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180039867`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180039867`

## string_xrefs

- `0x1800399c5`: `ComputerName`
- `0x18003991e`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName`
- `0x180039994`: `ActiveComputerName`
- `0x180039a6a`: `\Registry\Machine\System\Setup`
- `0x180039a9b`: `\Registry\Machine\System\Setup`

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
        if ( dword_1800B5314 )
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
            dword_1800B5314 = 0;
          }
          else
          {
            v37 = dword_1800B5314;
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
                dword_1800B5314 = 0;
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
0x180039820  mov     [rsp-18h+arg_0], rbx
0x180039825  mov     [rsp-18h+arg_8], rsi
0x18003982a  push    rbp
0x18003982b  push    rdi
0x18003982c  push    r14
0x18003982e  mov     rbp, rsp
0x180039831  sub     rsp, 80h
0x180039838  mov     r8d, [rdx]; nSize
0x18003983b  xorps   xmm0, xmm0
0x18003983e  xor     eax, eax
0x180039840  mov     rbx, rdx
0x180039843  mov     rdx, rcx; lpBuffer
0x180039846  mov     [rbp+KeyHandle], rax
0x18003984a  mov     rsi, rcx
0x18003984d  mov     [rbp+arg_10], eax
0x180039850  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180039854  lea     rcx, aClusterNetwork; "_CLUSTER_NETWORK_NAME_"
0x18003985b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18003985f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180039863  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180039867  call    cs:__imp_GetEnvironmentVariableW
0x18003986d  mov     r14d, eax
0x180039870  test    eax, eax
0x180039872  jz      short loc_180039892
0x180039874  cmp     [rbx], eax
0x180039876  jb      short loc_18003987F
0x180039878  mov     edi, 1
0x18003987d  jmp     short loc_18003988A
0x18003987f  xor     edi, edi
0x180039881  lea     ecx, [rdi+6Fh]; LastError
0x180039884  call    cs:__imp_RtlSetLastWin32Error
0x18003988a  mov     [rbx], r14d
0x18003988d  jmp     loc_180039B78
0x180039892  call    cs:__imp_KernelBaseGetGlobalData
0x180039898  mov     rcx, [rax+0A0h]
0x18003989f  test    rcx, rcx
0x1800398a2  jz      short loc_1800398F2
0x1800398a4  call    cs:__imp_KernelBaseGetGlobalData
0x1800398aa  mov     ecx, [rax+0A8h]
0x1800398b0  lea     edi, [rcx+1]
0x1800398b3  cmp     [rbx], edi
0x1800398b5  jnb     short loc_1800398CB
0x1800398b7  mov     ecx, 6Fh ; 'o'; LastError
0x1800398bc  mov     [rbx], edi
0x1800398be  call    cs:__imp_RtlSetLastWin32Error
0x1800398c4  xor     eax, eax
0x1800398c6  jmp     loc_180039B7A
0x1800398cb  mov     [rbx], ecx
0x1800398cd  call    cs:__imp_KernelBaseGetGlobalData
0x1800398d3  mov     r8d, edi
0x1800398d6  mov     rcx, rsi; void *
0x1800398d9  add     r8, r8; Size
0x1800398dc  mov     rdx, [rax+0A0h]; Src
0x1800398e3  call    memcpy_0
0x1800398e8  mov     eax, 1
0x1800398ed  jmp     loc_180039B7A
0x1800398f2  mov     rax, cs:gpTermsrvGetComputerName
0x1800398f9  test    rax, rax
0x1800398fc  jz      short loc_18003991E
0x1800398fe  mov     rdx, rbx
0x180039901  mov     rcx, rsi
0x180039904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039909  cmp     eax, 4D5h
0x18003990e  jz      short loc_18003991E
0x180039910  cmp     eax, 6Fh ; 'o'
0x180039913  jnz     loc_180039A12
0x180039919  jmp     loc_180039B67
0x18003991e  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180039925  lea     rcx, [rbp+DestinationString]; DestinationString
0x180039929  call    cs:__imp_RtlInitUnicodeString
0x18003992f  lea     rax, [rbp+DestinationString]
0x180039933  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003993a  xorps   xmm0, xmm0
0x18003993d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180039941  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180039945  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003994d  mov     edx, 20019h; DesiredAccess
0x180039952  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180039959  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18003995d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180039962  call    cs:__imp_NtOpenKey
0x180039968  mov     edi, 0C0000034h
0x18003996d  mov     ecx, eax
0x18003996f  cmp     eax, edi
0x180039971  jnz     short loc_180039988
0x180039973  test    rsi, rsi
0x180039976  jz      short loc_18003997D
0x180039978  xor     eax, eax
0x18003997a  mov     [rsi], ax
0x18003997d  mov     dword ptr [rbx], 0
0x180039983  jmp     loc_180039A12
0x180039988  test    eax, eax
0x18003998a  js      loc_180039B62
0x180039990  mov     rcx, [rbp+KeyHandle]
0x180039994  lea     rdx, aActivecomputer; "ActiveComputerName"
0x18003999b  mov     r9, rbx
0x18003999e  mov     r8, rsi
0x1800399a1  call    GetNameFromValue
0x1800399a6  cmp     eax, 80000005h
0x1800399ab  jnz     short loc_1800399BD
0x1800399ad  mov     ecx, 6Fh ; 'o'; LastError
0x1800399b2  call    cs:__imp_RtlSetLastWin32Error
0x1800399b8  jmp     loc_180039B67
0x1800399bd  test    eax, eax
0x1800399bf  jns     short loc_180039A12
0x1800399c1  mov     rcx, [rbp+KeyHandle]
0x1800399c5  lea     rdx, aComputername; "ComputerName"
0x1800399cc  mov     r9, rbx
0x1800399cf  mov     r8, rsi
0x1800399d2  call    GetNameFromValue
0x1800399d7  mov     ecx, eax
0x1800399d9  cmp     eax, edi
0x1800399db  jnz     short loc_1800399E6
0x1800399dd  xor     eax, eax
0x1800399df  mov     [rsi], ax
0x1800399e2  mov     [rbx], eax
0x1800399e4  jmp     short loc_180039A12
0x1800399e6  test    eax, eax
0x1800399e8  js      loc_180039B62
0x1800399ee  mov     rdx, rbx
0x1800399f1  mov     rcx, rsi; Data
0x1800399f4  call    BaseCreateVolatileNameInReg
0x1800399f9  mov     edx, 80000000h
0x1800399fe  mov     ecx, eax
0x180039a00  add     eax, edx
0x180039a02  test    edx, eax
0x180039a04  jnz     short loc_180039A12
0x180039a06  cmp     ecx, 0C0000022h
0x180039a0c  jnz     loc_180039B62
0x180039a12  test    rsi, rsi
0x180039a15  jz      short loc_180039A27
0x180039a17  cmp     dword ptr [rbx], 0
0x180039a1a  jz      short loc_180039A27
0x180039a1c  mov     rcx, rsi; String
0x180039a1f  call    cs:__imp_wcslen
0x180039a25  mov     [rbx], eax
0x180039a27  cmp     cs:dword_1800B5314, 0
0x180039a2e  mov     edi, 1
0x180039a33  jz      loc_180039B69
0x180039a39  call    cs:__imp_KernelBaseGetGlobalData
0x180039a3f  lea     rcx, [rax+0B0h]; CriticalSection
0x180039a46  call    cs:__imp_RtlEnterCriticalSection
0x180039a4c  lea     rax, [rbp+arg_18]
0x180039a50  xor     ecx, ecx
0x180039a52  lea     r14d, [rdi+3]
0x180039a56  mov     [rsp+80h+var_60], rax
0x180039a5b  lea     r9, [rbp+arg_10]
0x180039a5f  mov     [rbp+arg_18], r14d
0x180039a63  lea     r8, aOobeinprogress; "OOBEInProgress"
0x180039a6a  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\Setup"
0x180039a71  call    BasepGetValueFromReg
0x180039a76  test    eax, eax
0x180039a78  js      short loc_180039A81
0x180039a7a  mov     eax, [rbp+arg_10]
0x180039a7d  test    eax, eax
0x180039a7f  jnz     short loc_180039AB2
0x180039a81  lea     rax, [rbp+arg_18]
0x180039a85  mov     [rbp+arg_18], r14d
0x180039a89  lea     r9, [rbp+arg_10]
0x180039a8d  mov     [rsp+80h+var_60], rax
0x180039a92  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x180039a99  xor     ecx, ecx
0x180039a9b  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\Setup"
0x180039aa2  call    BasepGetValueFromReg
0x180039aa7  test    eax, eax
0x180039aa9  js      short loc_180039ABC
0x180039aab  mov     eax, [rbp+arg_10]
0x180039aae  test    eax, eax
0x180039ab0  jz      short loc_180039ABC
0x180039ab2  xor     eax, eax
0x180039ab4  mov     cs:dword_1800B5314, eax
0x180039aba  jmp     short loc_180039AC2
0x180039abc  mov     eax, cs:dword_1800B5314
0x180039ac2  test    eax, eax
0x180039ac4  jz      loc_180039B4D
0x180039aca  call    cs:__imp_KernelBaseGetGlobalData
0x180039ad0  mov     rcx, [rax+0A0h]
0x180039ad7  test    rcx, rcx
0x180039ada  jnz     short loc_180039B4D
0x180039adc  mov     r8d, [rbx]
0x180039adf  xor     edx, edx; Flags
0x180039ae1  mov     rcx, gs:60h
0x180039aea  add     r8d, edi
0x180039aed  add     r8, r8; Size
0x180039af0  mov     rcx, [rcx+30h]; HeapHandle
0x180039af4  call    cs:__imp_RtlAllocateHeap
0x180039afa  mov     r14, rax
0x180039afd  test    rax, rax
0x180039b00  jz      short loc_180039B43
0x180039b02  mov     r8d, [rbx]
0x180039b05  mov     rdx, rsi; Src
0x180039b08  add     r8, r8; Size
0x180039b0b  mov     rcx, rax; void *
0x180039b0e  call    memcpy_0
0x180039b13  mov     edx, [rbx]
0x180039b15  xor     ecx, ecx
0x180039b17  mov     [r14+rdx*2], cx
0x180039b1c  mov     rcx, r14; String
0x180039b1f  call    cs:__imp_wcslen
0x180039b25  mov     rbx, rax
0x180039b28  call    cs:__imp_KernelBaseGetGlobalData
0x180039b2e  mov     [rax+0A8h], ebx
0x180039b34  call    cs:__imp_KernelBaseGetGlobalData
0x180039b3a  mov     [rax+0A0h], r14
0x180039b41  jmp     short loc_180039B4D
0x180039b43  mov     cs:dword_1800B5314, 0
0x180039b4d  call    cs:__imp_KernelBaseGetGlobalData
0x180039b53  lea     rcx, [rax+0B0h]; CriticalSection
0x180039b5a  call    cs:__imp_RtlLeaveCriticalSection
0x180039b60  jmp     short loc_180039B69
0x180039b62  call    BaseSetLastNTError
0x180039b67  xor     edi, edi
0x180039b69  mov     rcx, [rbp+KeyHandle]; Handle
0x180039b6d  test    rcx, rcx
0x180039b70  jz      short loc_180039B78
0x180039b72  call    cs:__imp_NtClose
0x180039b78  mov     eax, edi
0x180039b7a  lea     r11, [rsp+80h+var_s0]
0x180039b82  mov     rbx, [r11+20h]
0x180039b86  mov     rsi, [r11+28h]
0x180039b8a  mov     rsp, r11
0x180039b8d  pop     r14
0x180039b8f  pop     rdi
0x180039b90  pop     rbp
0x180039b91  retn
```
