# AslPathIsTemporaryInternetFile

- ea: `0x18001966c`
- end: `0x180019aeb`
- name: `AslPathIsTemporaryInternetFile`
- size: `1151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dc40`

## callees

- `0x180012920`
- `0x18001966c`
- `0x180019c84`
- `0x180056904`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001981f`
- `msvcrt!_wcsnicmp` at `0x18001981f`
- `ntdll!ZwOpenKey` at `0x18001975d`
- `ntdll!ZwOpenKey` at `0x18001975d`
- `ntdll!NtQueryValueKey` at `0x1800197b5`
- `ntdll!NtQueryValueKey` at `0x1800199be`
- `ntdll!NtQueryValueKey` at `0x1800197b5`
- `ntdll!NtQueryValueKey` at `0x1800199be`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800196e4`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800196e4`
- `ntdll!NtClose` at `0x1800198b9`
- `ntdll!NtClose` at `0x1800198b9`
- `ntdll!RtlFreeUnicodeString` at `0x18001983c`
- `ntdll!RtlFreeUnicodeString` at `0x18001983c`
- `ntdll!RtlAppendUnicodeToString` at `0x180019717`
- `ntdll!RtlAppendUnicodeToString` at `0x180019717`
- `ntdll!RtlAllocateHeap` at `0x1800196cd`
- `ntdll!RtlAllocateHeap` at `0x180019785`
- `ntdll!RtlAllocateHeap` at `0x180019984`
- `ntdll!RtlAllocateHeap` at `0x180019a7c`
- `ntdll!RtlAllocateHeap` at `0x1800196cd`
- `ntdll!RtlAllocateHeap` at `0x180019785`
- `ntdll!RtlAllocateHeap` at `0x180019984`
- `ntdll!RtlAllocateHeap` at `0x180019a7c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800196fc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800196fc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800199fe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019ab8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800199fe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019ab8`

## string_xrefs

- `0x18001992a`: `AslRegistryOpenKey failed [%x]`
- `0x1800198ff`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x1800198ee`: `AslPathIsTemporaryInternetFile`
- `0x180019939`: `AslPathIsTemporaryInternetFile`
- `0x180019a51`: `AslPathIsTemporaryInternetFile`
- `0x180019a97`: `AslPathIsTemporaryInternetFile`
- `0x18001994a`: `RtlAppendUnicodeStringToString failed for root HKCU path [%x]`
- `0x18001990e`: `RtlAppendUnicodeToString failed for shell folders path [%x]`
- `0x1800199cf`: `NtQueryValueKey failed to get registry value of temporary internet file [%x]`
- `0x1800199e6`: `Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ`
- `0x180019a46`: `Failed to expand environment variables in temporary internet file path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathIsTemporaryInternetFile(_DWORD *a1, const wchar_t *a2)
{
  _DWORD *v2; // rsi
  WCHAR *v4; // r15
  _DWORD *Heap; // r14
  int v6; // r13d
  int appended; // ebx
  NTSTATUS v8; // eax
  const WCHAR *v9; // rsi
  __int64 v10; // rax
  __int64 result; // rax
  const char *v12; // r9
  int v13; // r8d
  DWORD v14; // eax
  DWORD v15; // ebx
  int v16; // r8d
  WCHAR *v17; // rax
  DWORD v18; // eax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp+50h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp+58h] BYREF

  v2 = a1;
  ResultLength = 0;
  KeyHandle = 0;
  Destination = 0;
  Destination.MaximumLength = 520;
  KeyPath = 0;
  v4 = 0;
  Heap = 0;
  v6 = 0;
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
  if ( Destination.Buffer )
  {
    appended = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( appended < 0 )
    {
      v12 = "RtlFormatCurrentUserKeyPath failed [%x]";
      v13 = 402;
    }
    else
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &KeyPath);
      if ( appended < 0 )
      {
        v12 = "RtlAppendUnicodeStringToString failed for root HKCU path [%x]";
        v13 = 408;
      }
      else
      {
        appended = RtlAppendUnicodeToString(
                     &Destination,
                     L"\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders");
        if ( appended < 0 )
        {
          v12 = "RtlAppendUnicodeToString failed for shell folders path [%x]";
          v13 = 414;
        }
        else
        {
          KeyHandle = 0;
          ObjectAttributes.RootDirectory = 0;
          *(_QWORD *)&ObjectAttributes.Length = 48;
          *(_QWORD *)&ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &Destination;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v8 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
          appended = v8;
          if ( v8 < 0 )
          {
            if ( v8 == -1073741772 )
              goto LABEL_22;
            v12 = "AslRegistryOpenKey failed [%x]";
            v13 = 429;
          }
          else
          {
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
            if ( Heap )
            {
              appended = NtQueryValueKey(
                           KeyHandle,
                           (PUNICODE_STRING)&stru_1800F8450,
                           KeyValueFullInformation,
                           Heap,
                           0x208u,
                           &ResultLength);
              if ( appended != -1073741789 )
                goto LABEL_8;
              AslFree(NtCurrentPeb()->ProcessHeap, Heap);
              Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
              if ( Heap )
              {
                appended = NtQueryValueKey(
                             KeyHandle,
                             (PUNICODE_STRING)&stru_1800F8450,
                             KeyValueFullInformation,
                             Heap,
                             ResultLength,
                             &ResultLength);
LABEL_8:
                if ( appended != -1073741772 )
                {
                  if ( appended < 0 )
                  {
                    v12 = "NtQueryValueKey failed to get registry value of temporary internet file [%x]";
                    v13 = 475;
                  }
                  else
                  {
                    if ( (unsigned int)(Heap[1] - 1) <= 1 )
                    {
                      v9 = (const WCHAR *)((char *)Heap + (unsigned int)Heap[2]);
                      v10 = -1;
                      *(const WCHAR *)((char *)v9 + (unsigned int)Heap[3] - 2) = 0;
                      do
                        ++v10;
                      while ( v9[v10] );
                      if ( Heap[1] != 2 )
                        goto LABEL_14;
                      v14 = ExpandEnvironmentStringsW(v9, 0, 0);
                      v15 = v14;
                      if ( v14 )
                      {
                        v17 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v14);
                        v4 = v17;
                        if ( !v17 )
                        {
                          appended = -1073741801;
                          AslLogCallPrintf(
                            1,
                            (unsigned int)"AslPathIsTemporaryInternetFile",
                            502,
                            (unsigned int)"Out of memory");
                          goto LABEL_15;
                        }
                        v18 = ExpandEnvironmentStringsW(v9, v17, v15);
                        if ( v18 && v18 <= v15 )
                        {
                          v9 = v4;
                          LODWORD(v10) = v18 - 1;
LABEL_14:
                          appended = 0;
                          LOBYTE(v6) = _wcsnicmp(v9, a2, (unsigned int)v10) == 0;
LABEL_15:
                          v2 = a1;
                          goto LABEL_16;
                        }
                        if ( (int)GetLastError_0() > 0 )
                          appended = (unsigned __int16)GetLastError_0() | 0xC0070000;
                        else
                          appended = GetLastError_0();
                        v16 = 509;
                      }
                      else
                      {
                        if ( (int)GetLastError_0() > 0 )
                          appended = (unsigned __int16)GetLastError_0() | 0xC0070000;
                        else
                          appended = GetLastError_0();
                        v16 = 495;
                      }
                      AslLogCallPrintf(
                        1,
                        (unsigned int)"AslPathIsTemporaryInternetFile",
                        v16,
                        (unsigned int)"Failed to expand environment variables in temporary internet file path [%x]");
                      goto LABEL_15;
                    }
                    appended = -1073741492;
                    v12 = "Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ";
                    v13 = 481;
                  }
                  goto LABEL_26;
                }
LABEL_22:
                appended = 0;
                goto LABEL_16;
              }
              v13 = 455;
            }
            else
            {
              v13 = 439;
            }
            v12 = "Out of memory";
            appended = -1073741801;
          }
        }
      }
    }
  }
  else
  {
    appended = -1073741801;
    v12 = "Out of memory";
    v13 = 396;
  }
LABEL_26:
  AslLogCallPrintf(1, (unsigned int)"AslPathIsTemporaryInternetFile", v13, (_DWORD)v12);
LABEL_16:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  AslFree(NtCurrentPeb()->ProcessHeap, Destination.Buffer);
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  if ( KeyHandle )
    NtClose(KeyHandle);
  AslFree(NtCurrentPeb()->ProcessHeap, v4);
  result = (unsigned int)appended;
  *v2 = v6;
  return result;
}

```

## disassembly

```asm
0x18001966c  mov     [rsp-38h+arg_8], rbx
0x180019671  mov     [rsp-38h+arg_0], rcx
0x180019676  push    rbp
0x180019677  push    rsi
0x180019678  push    rdi
0x180019679  push    r12
0x18001967b  push    r13
0x18001967d  push    r14
0x18001967f  push    r15
0x180019681  mov     rbp, rsp
0x180019684  sub     rsp, 80h
0x18001968b  xor     edi, edi
0x18001968d  mov     eax, 208h
0x180019692  mov     rsi, rcx
0x180019695  mov     [rbp+arg_10], edi
0x180019698  mov     [rbp+KeyHandle], rdi
0x18001969c  xorps   xmm0, xmm0
0x18001969f  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1800196a3  mov     [rbp+Destination.MaximumLength], ax
0x1800196a7  mov     r12, rdx
0x1800196aa  xorps   xmm1, xmm1
0x1800196ad  lea     edx, [rdi+8]; Flags
0x1800196b0  movups  xmmword ptr [rbp+KeyPath.Length], xmm1
0x1800196b4  mov     rcx, gs:60h
0x1800196bd  mov     r8d, eax; Size
0x1800196c0  mov     r15d, edi
0x1800196c3  mov     r14d, edi
0x1800196c6  mov     r13d, edi
0x1800196c9  mov     rcx, [rcx+30h]; HeapHandle
0x1800196cd  call    cs:__imp_RtlAllocateHeap
0x1800196d3  mov     [rbp+Destination.Buffer], rax
0x1800196d7  test    rax, rax
0x1800196da  jz      loc_1800198C1
0x1800196e0  lea     rcx, [rbp+KeyPath]; KeyPath
0x1800196e4  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800196ea  mov     ebx, eax
0x1800196ec  test    eax, eax
0x1800196ee  js      loc_1800198FF
0x1800196f4  lea     rdx, [rbp+KeyPath]; Source
0x1800196f8  lea     rcx, [rbp+Destination]; Destination
0x1800196fc  call    cs:__imp_RtlAppendUnicodeStringToString
0x180019702  mov     ebx, eax
0x180019704  test    eax, eax
0x180019706  js      loc_18001994A
0x18001970c  lea     rdx, aSoftwareMicros_22; "\\Software\\Microsoft\\Windows\\Current"...
0x180019713  lea     rcx, [rbp+Destination]; Destination
0x180019717  call    cs:__imp_RtlAppendUnicodeToString
0x18001971d  mov     ebx, eax
0x18001971f  test    eax, eax
0x180019721  js      loc_18001990E
0x180019727  mov     [rbp+KeyHandle], rdi
0x18001972b  lea     rax, [rbp+Destination]
0x18001972f  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x180019733  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180019737  xorps   xmm0, xmm0
0x18001973a  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180019742  lea     edi, [r14+1]
0x180019746  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001974e  mov     edx, edi; DesiredAccess
0x180019750  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180019754  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180019758  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001975d  call    cs:__imp_ZwOpenKey
0x180019763  mov     ebx, eax
0x180019765  test    eax, eax
0x180019767  js      loc_1800198AB
0x18001976d  mov     rcx, gs:60h
0x180019776  lea     edx, [rdi+7]; Flags
0x180019779  mov     ebx, 208h
0x18001977e  mov     r8d, ebx; Size
0x180019781  mov     rcx, [rcx+30h]; HeapHandle
0x180019785  call    cs:__imp_RtlAllocateHeap
0x18001978b  mov     r14, rax
0x18001978e  test    rax, rax
0x180019791  jz      loc_1800198DA
0x180019797  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001979b  lea     rax, [rbp+arg_10]
0x18001979f  mov     [rsp+80h+ResultLength], rax; ResultLength
0x1800197a4  lea     rdx, stru_1800F8450; ValueName
0x1800197ab  mov     r9, r14; KeyValueInformation
0x1800197ae  mov     [rsp+80h+Length], ebx; Length
0x1800197b2  mov     r8d, edi; KeyValueInformationClass
0x1800197b5  call    cs:__imp_NtQueryValueKey
0x1800197bb  mov     ebx, eax
0x1800197bd  cmp     eax, 0C0000023h
0x1800197c2  jz      loc_180019959
0x1800197c8  cmp     ebx, 0C0000034h
0x1800197ce  jz      loc_1800198B2
0x1800197d4  xor     edx, edx; lpDst
0x1800197d6  test    ebx, ebx
0x1800197d8  js      loc_1800199CB
0x1800197de  mov     eax, [r14+4]
0x1800197e2  sub     eax, edi
0x1800197e4  cmp     eax, edi
0x1800197e6  ja      loc_1800199E1
0x1800197ec  mov     esi, [r14+8]
0x1800197f0  mov     ecx, [r14+0Ch]
0x1800197f4  add     rsi, r14
0x1800197f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800197fb  mov     [rcx+rsi-2], dx
0x180019800  inc     rax
0x180019803  cmp     [rsi+rax*2], dx
0x180019807  jnz     short loc_180019800
0x180019809  cmp     dword ptr [r14+4], 2
0x18001980e  jz      loc_1800199F8
0x180019814  mov     ebx, edx
0x180019816  mov     r8d, eax; MaxCount
0x180019819  mov     rdx, r12; String2
0x18001981c  mov     rcx, rsi; String1
0x18001981f  call    cs:__imp__wcsnicmp
0x180019825  xor     esi, esi
0x180019827  test    eax, eax
0x180019829  setz    r13b
0x18001982d  mov     rsi, [rbp+arg_0]
0x180019831  cmp     [rbp+KeyPath.Buffer], 0
0x180019836  jz      short loc_180019842
0x180019838  lea     rcx, [rbp+KeyPath]; UnicodeString
0x18001983c  call    cs:__imp_RtlFreeUnicodeString
0x180019842  mov     rcx, gs:60h
0x18001984b  mov     rdx, [rbp+Destination.Buffer]
0x18001984f  mov     rcx, [rcx+30h]
0x180019853  call    AslFree
0x180019858  mov     rcx, gs:60h
0x180019861  mov     rdx, r14
0x180019864  mov     rcx, [rcx+30h]
0x180019868  call    AslFree
0x18001986d  mov     rcx, [rbp+KeyHandle]; Handle
0x180019871  test    rcx, rcx
0x180019874  jnz     short loc_1800198B9
0x180019876  mov     rcx, gs:60h
0x18001987f  mov     rdx, r15
0x180019882  mov     rcx, [rcx+30h]
0x180019886  call    AslFree
0x18001988b  mov     eax, ebx
0x18001988d  mov     [rsi], r13d
0x180019890  mov     rbx, [rsp+80h+arg_8]
0x180019898  add     rsp, 80h
0x18001989f  pop     r15
0x1800198a1  pop     r14
0x1800198a3  pop     r13
0x1800198a5  pop     r12
0x1800198a7  pop     rdi
0x1800198a8  pop     rsi
0x1800198a9  pop     rbp
0x1800198aa  retn
0x1800198ab  cmp     eax, 0C0000034h
0x1800198b0  jnz     short loc_180019926
0x1800198b2  xor     ebx, ebx
0x1800198b4  jmp     loc_180019831
0x1800198b9  call    cs:__imp_NtClose
0x1800198bf  jmp     short loc_180019876
0x1800198c1  mov     ebx, 0C0000017h
0x1800198c6  lea     r9, aOutOfMemory; "Out of memory"
0x1800198cd  mov     r8d, 18Ch
0x1800198d3  mov     ecx, 1
0x1800198d8  jmp     short loc_1800198EE
0x1800198da  mov     r8d, 1B7h
0x1800198e0  lea     r9, aOutOfMemory; "Out of memory"
0x1800198e7  mov     ebx, 0C0000017h
0x1800198ec  mov     ecx, edi
0x1800198ee  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x1800198f5  call    AslLogCallPrintf
0x1800198fa  jmp     loc_180019831
0x1800198ff  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x180019906  mov     r8d, 192h
0x18001990c  jmp     short loc_18001991B
0x18001990e  lea     r9, aRtlappendunico_1; "RtlAppendUnicodeToString failed for she"...
0x180019915  mov     r8d, 19Eh
0x18001991b  mov     [rsp+80h+Length], eax
0x18001991f  mov     ecx, 1
0x180019924  jmp     short loc_180019939
0x180019926  mov     [rsp+80h+Length], eax
0x18001992a  lea     r9, aAslregistryope_3; "AslRegistryOpenKey failed [%x]"
0x180019931  mov     r8d, 1ADh
0x180019937  mov     ecx, edi
0x180019939  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180019940  call    AslLogCallPrintf
0x180019945  jmp     loc_180019831
0x18001994a  lea     r9, aRtlappendunico; "RtlAppendUnicodeStringToString failed f"...
0x180019951  mov     r8d, 198h
0x180019957  jmp     short loc_18001991B
0x180019959  mov     rcx, gs:60h
0x180019962  mov     rdx, r14
0x180019965  mov     rcx, [rcx+30h]
0x180019969  call    AslFree
0x18001996e  mov     rcx, gs:60h
0x180019977  mov     edx, 8; Flags
0x18001997c  mov     r8d, [rbp+arg_10]; Size
0x180019980  mov     rcx, [rcx+30h]; HeapHandle
0x180019984  call    cs:__imp_RtlAllocateHeap
0x18001998a  mov     r14, rax
0x18001998d  test    rax, rax
0x180019990  jnz     short loc_18001999D
0x180019992  mov     r8d, 1C7h
0x180019998  jmp     loc_1800198E0
0x18001999d  mov     eax, [rbp+arg_10]
0x1800199a0  lea     rcx, [rbp+arg_10]
0x1800199a4  mov     [rsp+80h+ResultLength], rcx; ResultLength
0x1800199a9  lea     rdx, stru_1800F8450; ValueName
0x1800199b0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800199b4  mov     r9, r14; KeyValueInformation
0x1800199b7  mov     r8d, edi; KeyValueInformationClass
0x1800199ba  mov     [rsp+80h+Length], eax; Length
0x1800199be  call    cs:__imp_NtQueryValueKey
0x1800199c4  mov     ebx, eax
0x1800199c6  jmp     loc_1800197C8
0x1800199cb  mov     [rsp+80h+Length], ebx
0x1800199cf  lea     r9, aNtqueryvalueke; "NtQueryValueKey failed to get registry "...
0x1800199d6  mov     r8d, 1DBh
0x1800199dc  jmp     loc_180019937
0x1800199e1  mov     ebx, 0C000014Ch
0x1800199e6  lea     r9, aErrorInRegistr; "Error in registry value retrieved with "...
0x1800199ed  mov     r8d, 1E1h
0x1800199f3  jmp     loc_1800198EC
0x1800199f8  xor     r8d, r8d; nSize
0x1800199fb  mov     rcx, rsi; lpSrc
0x1800199fe  call    cs:__imp_ExpandEnvironmentStringsW
0x180019a04  mov     ebx, eax
0x180019a06  test    eax, eax
0x180019a08  jnz     short loc_180019A64
0x180019a0a  call    GetLastError_0
0x180019a0f  test    eax, eax
0x180019a11  jg      short loc_180019A1C
0x180019a13  call    GetLastError_0
0x180019a18  mov     ebx, eax
0x180019a1a  jmp     short loc_180019A2A
0x180019a1c  call    GetLastError_0
0x180019a21  movzx   ebx, ax
0x180019a24  or      ebx, 0C0070000h
0x180019a2a  mov     r8d, 1EFh
0x180019a30  jmp     short loc_180019A46
0x180019a32  call    GetLastError_0
0x180019a37  movzx   ebx, ax
0x180019a3a  or      ebx, 0C0070000h
0x180019a40  mov     r8d, 1FDh
0x180019a46  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x180019a4d  mov     [rsp+80h+Length], ebx
0x180019a51  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180019a58  mov     ecx, edi
0x180019a5a  call    AslLogCallPrintf
0x180019a5f  jmp     loc_18001982D
0x180019a64  mov     rcx, gs:60h
0x180019a6d  mov     r8, rbx
0x180019a70  add     r8, r8; Size
0x180019a73  mov     edx, 8; Flags
0x180019a78  mov     rcx, [rcx+30h]; HeapHandle
0x180019a7c  call    cs:__imp_RtlAllocateHeap
0x180019a82  mov     r15, rax
0x180019a85  test    rax, rax
0x180019a88  jnz     short loc_180019AAF
0x180019a8a  lea     r9, aOutOfMemory; "Out of memory"
0x180019a91  mov     r8d, 1F6h
0x180019a97  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180019a9e  mov     ecx, edi
0x180019aa0  mov     ebx, 0C0000017h
0x180019aa5  call    AslLogCallPrintf
0x180019aaa  jmp     loc_18001982D
0x180019aaf  mov     r8d, ebx; nSize
0x180019ab2  mov     rdx, r15; lpDst
0x180019ab5  mov     rcx, rsi; lpSrc
0x180019ab8  call    cs:__imp_ExpandEnvironmentStringsW
0x180019abe  xor     edx, edx
0x180019ac0  test    eax, eax
0x180019ac2  jz      short loc_180019AD2
0x180019ac4  cmp     eax, ebx
0x180019ac6  ja      short loc_180019AD2
0x180019ac8  mov     rsi, r15
0x180019acb  dec     eax
0x180019acd  jmp     loc_180019814
0x180019ad2  call    GetLastError_0
0x180019ad7  test    eax, eax
0x180019ad9  jg      loc_180019A32
0x180019adf  call    GetLastError_0
0x180019ae4  mov     ebx, eax
0x180019ae6  jmp     loc_180019A40
```
