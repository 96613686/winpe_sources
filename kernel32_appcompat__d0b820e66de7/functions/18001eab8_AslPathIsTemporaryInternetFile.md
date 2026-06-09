# AslPathIsTemporaryInternetFile

- ea: `0x18001eab8`
- end: `0x18001ef83`
- name: `AslPathIsTemporaryInternetFile`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e1e8`

## callees

- `0x18001eab8`
- `0x18001ef8c`
- `0x18001f138`
- `0x180061df4`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18001ec25`
- `ntdll!NtQueryValueKey` at `0x18001ee6f`
- `ntdll!NtQueryValueKey` at `0x18001ec25`
- `ntdll!NtQueryValueKey` at `0x18001ee6f`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18001eb36`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18001eb36`
- `ntdll!RtlAppendUnicodeToString` at `0x18001eb75`
- `ntdll!RtlAppendUnicodeToString` at `0x18001eb75`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001eb54`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001eb54`
- `ntdll!NtClose` at `0x18001ecf1`
- `ntdll!NtClose` at `0x18001ecf1`
- `ntdll!RtlFreeUnicodeString` at `0x18001ecb1`
- `ntdll!RtlFreeUnicodeString` at `0x18001ecb1`
- `ntdll!ZwOpenKey` at `0x18001ebc1`
- `ntdll!ZwOpenKey` at `0x18001ebc1`
- `ntdll!RtlAllocateHeap` at `0x18001eb19`
- `ntdll!RtlAllocateHeap` at `0x18001ebef`
- `ntdll!RtlAllocateHeap` at `0x18001ee3a`
- `ntdll!RtlAllocateHeap` at `0x18001ef04`
- `ntdll!RtlAllocateHeap` at `0x18001eb19`
- `ntdll!RtlAllocateHeap` at `0x18001ebef`
- `ntdll!RtlAllocateHeap` at `0x18001ee3a`
- `ntdll!RtlAllocateHeap` at `0x18001ef04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ee88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ef46`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ee88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ef46`

## string_xrefs

- `0x18001ed70`: `AslPathIsTemporaryInternetFile`
- `0x18001eda7`: `AslPathIsTemporaryInternetFile`
- `0x18001eed9`: `AslPathIsTemporaryInternetFile`
- `0x18001ef25`: `AslPathIsTemporaryInternetFile`
- `0x18001ed49`: `NtQueryValueKey failed to get registry value of temporary internet file [%x]`
- `0x18001ed5a`: `RtlAppendUnicodeStringToString failed for root HKCU path [%x]`
- `0x18001ed81`: `RtlAppendUnicodeToString failed for shell folders path [%x]`
- `0x18001edb8`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x18001edcb`: `AslRegistryOpenKey failed [%x]`
- `0x18001edfe`: `Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ`
- `0x18001eece`: `Failed to expand environment variables in temporary internet file path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathIsTemporaryInternetFile(_DWORD *a1, const wchar_t *a2)
{
  _DWORD *v2; // rsi
  WCHAR *v4; // r15
  _DWORD *Heap; // r14
  int v6; // r13d
  NTSTATUS appended; // eax
  int LastErrorValue; // ebx
  NTSTATUS v9; // eax
  const WCHAR *v10; // rsi
  __int64 v11; // rax
  __int64 result; // rax
  const char *v13; // r9
  int v14; // r8d
  DWORD v15; // eax
  DWORD v16; // ebx
  int v17; // r8d
  WCHAR *v18; // rax
  DWORD v19; // eax
  char Length; // [rsp+20h] [rbp-60h]
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
  if ( !Destination.Buffer )
  {
    LastErrorValue = -1073741801;
    v13 = "Out of memory";
    v14 = 396;
    goto LABEL_26;
  }
  appended = RtlFormatCurrentUserKeyPath(&KeyPath);
  LastErrorValue = appended;
  if ( appended < 0 )
  {
    v13 = "RtlFormatCurrentUserKeyPath failed [%x]";
    v14 = 402;
    goto LABEL_25;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, &KeyPath);
  LastErrorValue = appended;
  if ( appended < 0 )
  {
    v13 = "RtlAppendUnicodeStringToString failed for root HKCU path [%x]";
    v14 = 408;
LABEL_25:
    Length = appended;
    goto LABEL_26;
  }
  appended = RtlAppendUnicodeToString(
               &Destination,
               L"\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders");
  LastErrorValue = appended;
  if ( appended < 0 )
  {
    v13 = "RtlAppendUnicodeToString failed for shell folders path [%x]";
    v14 = 414;
    goto LABEL_25;
  }
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  LastErrorValue = v9;
  if ( v9 < 0 )
  {
    if ( v9 == -1073741772 )
      goto LABEL_22;
    Length = v9;
    v13 = "AslRegistryOpenKey failed [%x]";
    v14 = 429;
  }
  else
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( Heap )
    {
      LastErrorValue = NtQueryValueKey(
                         KeyHandle,
                         (PUNICODE_STRING)&ValueName,
                         KeyValueFullInformation,
                         Heap,
                         0x208u,
                         &ResultLength);
      if ( LastErrorValue != -1073741789 )
        goto LABEL_8;
      AslFree(NtCurrentPeb()->ProcessHeap, Heap);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
      if ( Heap )
      {
        LastErrorValue = NtQueryValueKey(
                           KeyHandle,
                           (PUNICODE_STRING)&ValueName,
                           KeyValueFullInformation,
                           Heap,
                           ResultLength,
                           &ResultLength);
LABEL_8:
        if ( LastErrorValue != -1073741772 )
        {
          if ( LastErrorValue < 0 )
          {
            Length = LastErrorValue;
            v13 = "NtQueryValueKey failed to get registry value of temporary internet file [%x]";
            v14 = 475;
          }
          else
          {
            if ( (unsigned int)(Heap[1] - 1) <= 1 )
            {
              v10 = (const WCHAR *)((char *)Heap + (unsigned int)Heap[2]);
              v11 = -1;
              *(const WCHAR *)((char *)v10 + (unsigned int)Heap[3] - 2) = 0;
              do
                ++v11;
              while ( v10[v11] );
              if ( Heap[1] != 2 )
                goto LABEL_14;
              v15 = ExpandEnvironmentStringsW(v10, 0, 0);
              v16 = v15;
              if ( v15 )
              {
                v18 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v15);
                v4 = v18;
                if ( !v18 )
                {
                  LastErrorValue = -1073741801;
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"AslPathIsTemporaryInternetFile",
                    502,
                    (unsigned int)"Out of memory",
                    Length);
                  goto LABEL_15;
                }
                v19 = ExpandEnvironmentStringsW(v10, v18, v16);
                if ( v19 && v19 <= v16 )
                {
                  v10 = v4;
                  LODWORD(v11) = v19 - 1;
LABEL_14:
                  LastErrorValue = 0;
                  LOBYTE(v6) = wcsnicmp_0(v10, a2, (unsigned int)v11) == 0;
LABEL_15:
                  v2 = a1;
                  goto LABEL_16;
                }
                LastErrorValue = NtCurrentTeb()->LastErrorValue;
                if ( LastErrorValue > 0 )
                  LastErrorValue = (unsigned __int16)LastErrorValue | 0xC0070000;
                v17 = 509;
              }
              else
              {
                LastErrorValue = NtCurrentTeb()->LastErrorValue;
                if ( LastErrorValue > 0 )
                  LastErrorValue = (unsigned __int16)LastErrorValue | 0xC0070000;
                v17 = 495;
              }
              AslLogCallPrintf(
                1,
                (unsigned int)"AslPathIsTemporaryInternetFile",
                v17,
                (unsigned int)"Failed to expand environment variables in temporary internet file path [%x]",
                LastErrorValue);
              goto LABEL_15;
            }
            LastErrorValue = -1073741492;
            v13 = "Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ";
            v14 = 481;
          }
          goto LABEL_26;
        }
LABEL_22:
        LastErrorValue = 0;
        goto LABEL_16;
      }
      v14 = 455;
    }
    else
    {
      v14 = 439;
    }
    v13 = "Out of memory";
    LastErrorValue = -1073741801;
  }
LABEL_26:
  AslLogCallPrintf(1, (unsigned int)"AslPathIsTemporaryInternetFile", v14, (_DWORD)v13, Length);
LABEL_16:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  AslFree(NtCurrentPeb()->ProcessHeap, Destination.Buffer);
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  if ( KeyHandle )
    NtClose(KeyHandle);
  AslFree(NtCurrentPeb()->ProcessHeap, v4);
  result = (unsigned int)LastErrorValue;
  *v2 = v6;
  return result;
}

```

## disassembly

```asm
0x18001eab8  mov     [rsp-38h+arg_8], rbx
0x18001eabd  mov     [rsp-38h+arg_0], rcx
0x18001eac2  push    rbp
0x18001eac3  push    rsi
0x18001eac4  push    rdi
0x18001eac5  push    r12
0x18001eac7  push    r13
0x18001eac9  push    r14
0x18001eacb  push    r15
0x18001eacd  mov     rbp, rsp
0x18001ead0  sub     rsp, 80h
0x18001ead7  xor     edi, edi
0x18001ead9  mov     eax, 208h
0x18001eade  mov     rsi, rcx
0x18001eae1  mov     [rbp+arg_10], edi
0x18001eae4  mov     [rbp+KeyHandle], rdi
0x18001eae8  xorps   xmm0, xmm0
0x18001eaeb  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18001eaef  mov     [rbp+Destination.MaximumLength], ax
0x18001eaf3  mov     r12, rdx
0x18001eaf6  xorps   xmm1, xmm1
0x18001eaf9  lea     edx, [rdi+8]; Flags
0x18001eafc  movups  xmmword ptr [rbp+KeyPath.Length], xmm1
0x18001eb00  mov     rcx, gs:60h
0x18001eb09  mov     r8d, eax; Size
0x18001eb0c  mov     r15d, edi
0x18001eb0f  mov     r14d, edi
0x18001eb12  mov     r13d, edi
0x18001eb15  mov     rcx, [rcx+30h]; HeapHandle
0x18001eb19  call    cs:__imp_RtlAllocateHeap
0x18001eb20  nop     dword ptr [rax+rax+00h]
0x18001eb25  mov     [rbp+Destination.Buffer], rax
0x18001eb29  test    rax, rax
0x18001eb2c  jz      loc_18001ED90
0x18001eb32  lea     rcx, [rbp+KeyPath]; KeyPath
0x18001eb36  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18001eb3d  nop     dword ptr [rax+rax+00h]
0x18001eb42  mov     ebx, eax
0x18001eb44  test    eax, eax
0x18001eb46  js      loc_18001EDB8
0x18001eb4c  lea     rdx, [rbp+KeyPath]; Source
0x18001eb50  lea     rcx, [rbp+Destination]; Destination
0x18001eb54  call    cs:__imp_RtlAppendUnicodeStringToString
0x18001eb5b  nop     dword ptr [rax+rax+00h]
0x18001eb60  mov     ebx, eax
0x18001eb62  test    eax, eax
0x18001eb64  js      loc_18001ED5A
0x18001eb6a  lea     rdx, aSoftwareMicros_5; "\\Software\\Microsoft\\Windows\\Current"...
0x18001eb71  lea     rcx, [rbp+Destination]; Destination
0x18001eb75  call    cs:__imp_RtlAppendUnicodeToString
0x18001eb7c  nop     dword ptr [rax+rax+00h]
0x18001eb81  mov     ebx, eax
0x18001eb83  test    eax, eax
0x18001eb85  js      loc_18001ED81
0x18001eb8b  mov     [rbp+KeyHandle], rdi
0x18001eb8f  lea     rax, [rbp+Destination]
0x18001eb93  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x18001eb97  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001eb9b  xorps   xmm0, xmm0
0x18001eb9e  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001eba6  lea     edi, [r14+1]
0x18001ebaa  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001ebb2  mov     edx, edi; DesiredAccess
0x18001ebb4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001ebb8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18001ebbc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ebc1  call    cs:__imp_ZwOpenKey
0x18001ebc8  nop     dword ptr [rax+rax+00h]
0x18001ebcd  mov     ebx, eax
0x18001ebcf  test    eax, eax
0x18001ebd1  js      loc_18001ED33
0x18001ebd7  mov     rcx, gs:60h
0x18001ebe0  lea     edx, [rdi+7]; Flags
0x18001ebe3  mov     ebx, 208h
0x18001ebe8  mov     r8d, ebx; Size
0x18001ebeb  mov     rcx, [rcx+30h]; HeapHandle
0x18001ebef  call    cs:__imp_RtlAllocateHeap
0x18001ebf6  nop     dword ptr [rax+rax+00h]
0x18001ebfb  mov     r14, rax
0x18001ebfe  test    rax, rax
0x18001ec01  jz      loc_18001EDDD
0x18001ec07  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001ec0b  lea     rax, [rbp+arg_10]
0x18001ec0f  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18001ec14  lea     rdx, ValueName; ValueName
0x18001ec1b  mov     r9, r14; KeyValueInformation
0x18001ec1e  mov     dword ptr [rsp+80h+Length], ebx; Length
0x18001ec22  mov     r8d, edi; KeyValueInformationClass
0x18001ec25  call    cs:__imp_NtQueryValueKey
0x18001ec2c  nop     dword ptr [rax+rax+00h]
0x18001ec31  mov     ebx, eax
0x18001ec33  cmp     eax, 0C0000023h
0x18001ec38  jz      loc_18001EE0F
0x18001ec3e  cmp     ebx, 0C0000034h
0x18001ec44  jz      loc_18001ED3E
0x18001ec4a  xor     edx, edx; lpDst
0x18001ec4c  test    ebx, ebx
0x18001ec4e  js      loc_18001ED45
0x18001ec54  mov     eax, [r14+4]
0x18001ec58  sub     eax, edi
0x18001ec5a  cmp     eax, edi
0x18001ec5c  ja      loc_18001EDF9
0x18001ec62  mov     esi, [r14+8]
0x18001ec66  mov     ecx, [r14+0Ch]
0x18001ec6a  add     rsi, r14
0x18001ec6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ec71  mov     [rcx+rsi-2], dx
0x18001ec76  inc     rax
0x18001ec79  cmp     [rsi+rax*2], dx
0x18001ec7d  jnz     short loc_18001EC76
0x18001ec7f  cmp     dword ptr [r14+4], 2
0x18001ec84  jz      loc_18001EE82
0x18001ec8a  mov     ebx, edx
0x18001ec8c  mov     r8d, eax; MaxCount
0x18001ec8f  mov     rdx, r12; String2
0x18001ec92  mov     rcx, rsi; String1
0x18001ec95  call    _wcsnicmp_0
0x18001ec9a  xor     esi, esi
0x18001ec9c  test    eax, eax
0x18001ec9e  setz    r13b
0x18001eca2  mov     rsi, [rbp+arg_0]
0x18001eca6  cmp     [rbp+KeyPath.Buffer], 0
0x18001ecab  jz      short loc_18001ECBD
0x18001ecad  lea     rcx, [rbp+KeyPath]; UnicodeString
0x18001ecb1  call    cs:__imp_RtlFreeUnicodeString
0x18001ecb8  nop     dword ptr [rax+rax+00h]
0x18001ecbd  mov     rcx, gs:60h
0x18001ecc6  mov     rdx, [rbp+Destination.Buffer]
0x18001ecca  mov     rcx, [rcx+30h]
0x18001ecce  call    AslFree
0x18001ecd3  mov     rcx, gs:60h
0x18001ecdc  mov     rdx, r14
0x18001ecdf  mov     rcx, [rcx+30h]
0x18001ece3  call    AslFree
0x18001ece8  mov     rcx, [rbp+KeyHandle]; Handle
0x18001ecec  test    rcx, rcx
0x18001ecef  jz      short loc_18001ECFD
0x18001ecf1  call    cs:__imp_NtClose
0x18001ecf8  nop     dword ptr [rax+rax+00h]
0x18001ecfd  mov     rcx, gs:60h
0x18001ed06  mov     rdx, r15
0x18001ed09  mov     rcx, [rcx+30h]
0x18001ed0d  call    AslFree
0x18001ed12  mov     eax, ebx
0x18001ed14  mov     [rsi], r13d
0x18001ed17  mov     rbx, [rsp+80h+arg_8]
0x18001ed1f  add     rsp, 80h
0x18001ed26  pop     r15
0x18001ed28  pop     r14
0x18001ed2a  pop     r13
0x18001ed2c  pop     r12
0x18001ed2e  pop     rdi
0x18001ed2f  pop     rsi
0x18001ed30  pop     rbp
0x18001ed31  retn
0x18001ed33  cmp     eax, 0C0000034h
0x18001ed38  jnz     loc_18001EDC7
0x18001ed3e  xor     ebx, ebx
0x18001ed40  jmp     loc_18001ECA6
0x18001ed45  mov     dword ptr [rsp+80h+Length], ebx
0x18001ed49  lea     r9, aNtqueryvalueke; "NtQueryValueKey failed to get registry "...
0x18001ed50  mov     r8d, 1DBh
0x18001ed56  mov     ecx, edi
0x18001ed58  jmp     short loc_18001ED70
0x18001ed5a  lea     r9, aRtlappendunico; "RtlAppendUnicodeStringToString failed f"...
0x18001ed61  mov     r8d, 198h
0x18001ed67  mov     dword ptr [rsp+80h+Length], eax
0x18001ed6b  mov     ecx, 1
0x18001ed70  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x18001ed77  call    AslLogCallPrintf
0x18001ed7c  jmp     loc_18001ECA6
0x18001ed81  lea     r9, aRtlappendunico_1; "RtlAppendUnicodeToString failed for she"...
0x18001ed88  mov     r8d, 19Eh
0x18001ed8e  jmp     short loc_18001ED67
0x18001ed90  mov     ebx, 0C0000017h
0x18001ed95  lea     r9, aOutOfMemory; "Out of memory"
0x18001ed9c  mov     r8d, 18Ch
0x18001eda2  mov     ecx, 1
0x18001eda7  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x18001edae  call    AslLogCallPrintf
0x18001edb3  jmp     loc_18001ECA6
0x18001edb8  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x18001edbf  mov     r8d, 192h
0x18001edc5  jmp     short loc_18001ED67
0x18001edc7  mov     dword ptr [rsp+80h+Length], eax
0x18001edcb  lea     r9, aAslregistryope_1; "AslRegistryOpenKey failed [%x]"
0x18001edd2  mov     r8d, 1ADh
0x18001edd8  jmp     loc_18001ED56
0x18001eddd  mov     r8d, 1B7h
0x18001ede3  jmp     short loc_18001EDEB
0x18001ede5  mov     r8d, 1C7h
0x18001edeb  lea     r9, aOutOfMemory; "Out of memory"
0x18001edf2  mov     ebx, 0C0000017h
0x18001edf7  jmp     short loc_18001EE0B
0x18001edf9  mov     ebx, 0C000014Ch
0x18001edfe  lea     r9, aErrorInRegistr; "Error in registry value retrieved with "...
0x18001ee05  mov     r8d, 1E1h
0x18001ee0b  mov     ecx, edi
0x18001ee0d  jmp     short loc_18001EDA7
0x18001ee0f  mov     rcx, gs:60h
0x18001ee18  mov     rdx, r14
0x18001ee1b  mov     rcx, [rcx+30h]
0x18001ee1f  call    AslFree
0x18001ee24  mov     rcx, gs:60h
0x18001ee2d  mov     edx, 8; Flags
0x18001ee32  mov     r8d, [rbp+arg_10]; Size
0x18001ee36  mov     rcx, [rcx+30h]; HeapHandle
0x18001ee3a  call    cs:__imp_RtlAllocateHeap
0x18001ee41  nop     dword ptr [rax+rax+00h]
0x18001ee46  mov     r14, rax
0x18001ee49  test    rax, rax
0x18001ee4c  jz      short loc_18001EDE5
0x18001ee4e  mov     eax, [rbp+arg_10]
0x18001ee51  lea     rcx, [rbp+arg_10]
0x18001ee55  mov     [rsp+80h+ResultLength], rcx; ResultLength
0x18001ee5a  lea     rdx, ValueName; ValueName
0x18001ee61  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001ee65  mov     r9, r14; KeyValueInformation
0x18001ee68  mov     r8d, edi; KeyValueInformationClass
0x18001ee6b  mov     dword ptr [rsp+80h+Length], eax; Length
0x18001ee6f  call    cs:__imp_NtQueryValueKey
0x18001ee76  nop     dword ptr [rax+rax+00h]
0x18001ee7b  mov     ebx, eax
0x18001ee7d  jmp     loc_18001EC3E
0x18001ee82  xor     r8d, r8d; nSize
0x18001ee85  mov     rcx, rsi; lpSrc
0x18001ee88  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ee8f  nop     dword ptr [rax+rax+00h]
0x18001ee94  mov     ebx, eax
0x18001ee96  test    eax, eax
0x18001ee98  jnz     short loc_18001EEEC
0x18001ee9a  mov     ebx, gs:68h
0x18001eea2  mov     eax, gs:68h
0x18001eeaa  test    eax, eax
0x18001eeac  jle     short loc_18001EEB7
0x18001eeae  movzx   ebx, bx
0x18001eeb1  or      ebx, 0C0070000h
0x18001eeb7  mov     r8d, 1EFh
0x18001eebd  jmp     short loc_18001EECE
0x18001eebf  movzx   ebx, bx
0x18001eec2  or      ebx, 0C0070000h
0x18001eec8  mov     r8d, 1FDh
0x18001eece  lea     r9, aFailedToExpand; "Failed to expand environment variables "...
0x18001eed5  mov     dword ptr [rsp+80h+Length], ebx
0x18001eed9  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x18001eee0  mov     ecx, edi
0x18001eee2  call    AslLogCallPrintf
0x18001eee7  jmp     loc_18001ECA2
0x18001eeec  mov     rcx, gs:60h
0x18001eef5  mov     r8, rbx
0x18001eef8  add     r8, r8; Size
0x18001eefb  mov     edx, 8; Flags
0x18001ef00  mov     rcx, [rcx+30h]; HeapHandle
0x18001ef04  call    cs:__imp_RtlAllocateHeap
0x18001ef0b  nop     dword ptr [rax+rax+00h]
0x18001ef10  mov     r15, rax
0x18001ef13  test    rax, rax
0x18001ef16  jnz     short loc_18001EF3D
0x18001ef18  lea     r9, aOutOfMemory; "Out of memory"
0x18001ef1f  mov     r8d, 1F6h
0x18001ef25  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x18001ef2c  mov     ecx, edi
0x18001ef2e  mov     ebx, 0C0000017h
0x18001ef33  call    AslLogCallPrintf
0x18001ef38  jmp     loc_18001ECA2
0x18001ef3d  mov     r8d, ebx; nSize
0x18001ef40  mov     rdx, r15; lpDst
0x18001ef43  mov     rcx, rsi; lpSrc
0x18001ef46  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ef4d  nop     dword ptr [rax+rax+00h]
0x18001ef52  xor     edx, edx
0x18001ef54  test    eax, eax
0x18001ef56  jz      short loc_18001EF66
0x18001ef58  cmp     eax, ebx
0x18001ef5a  ja      short loc_18001EF66
0x18001ef5c  mov     rsi, r15
0x18001ef5f  dec     eax
0x18001ef61  jmp     loc_18001EC8A
0x18001ef66  mov     ebx, gs:68h
0x18001ef6e  mov     eax, gs:68h
0x18001ef76  test    eax, eax
0x18001ef78  jle     loc_18001EEC8
0x18001ef7e  jmp     loc_18001EEBF
```
