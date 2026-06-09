# AslPathIsTemporaryInternetFile

- ea: `0x180020cc8`
- end: `0x18002113e`
- name: `AslPathIsTemporaryInternetFile`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020374`

## callees

- `0x180020cc8`
- `0x180021144`
- `0x1800212e4`
- `0x18005c414`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180020e11`
- `ntdll!NtQueryValueKey` at `0x180021042`
- `ntdll!NtQueryValueKey` at `0x180020e11`
- `ntdll!NtQueryValueKey` at `0x180021042`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180020d40`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180020d40`
- `ntdll!RtlAppendUnicodeToString` at `0x180020d73`
- `ntdll!RtlAppendUnicodeToString` at `0x180020d73`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180020d58`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180020d58`
- `ntdll!NtClose` at `0x180020ed1`
- `ntdll!NtClose` at `0x180020ed1`
- `ntdll!RtlFreeUnicodeString` at `0x180020e97`
- `ntdll!RtlFreeUnicodeString` at `0x180020e97`
- `ntdll!ZwOpenKey` at `0x180020db9`
- `ntdll!ZwOpenKey` at `0x180020db9`
- `ntdll!RtlAllocateHeap` at `0x180020d29`
- `ntdll!RtlAllocateHeap` at `0x180020de1`
- `ntdll!RtlAllocateHeap` at `0x180021013`
- `ntdll!RtlAllocateHeap` at `0x1800210cb`
- `ntdll!RtlAllocateHeap` at `0x180020d29`
- `ntdll!RtlAllocateHeap` at `0x180020de1`
- `ntdll!RtlAllocateHeap` at `0x180021013`
- `ntdll!RtlAllocateHeap` at `0x1800210cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021055`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021107`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021055`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021107`

## string_xrefs

- `0x180020f49`: `AslPathIsTemporaryInternetFile`
- `0x180020f80`: `AslPathIsTemporaryInternetFile`
- `0x1800210a0`: `AslPathIsTemporaryInternetFile`
- `0x1800210e6`: `AslPathIsTemporaryInternetFile`
- `0x180020f22`: `NtQueryValueKey failed to get registry value of temporary internet file [%x]`
- `0x180020f33`: `RtlAppendUnicodeStringToString failed for root HKCU path [%x]`
- `0x180020f5a`: `RtlAppendUnicodeToString failed for shell folders path [%x]`
- `0x180020f91`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x180020fa4`: `AslRegistryOpenKey failed [%x]`
- `0x180020fd7`: `Error in registry value retrieved with NtQueryValueKey, not REG_SZ or REG_EXPAND_SZ`
- `0x180021095`: `Failed to expand environment variables in temporary internet file path [%x]`

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
0x180020cc8  mov     [rsp-38h+arg_8], rbx
0x180020ccd  mov     [rsp-38h+arg_0], rcx
0x180020cd2  push    rbp
0x180020cd3  push    rsi
0x180020cd4  push    rdi
0x180020cd5  push    r12
0x180020cd7  push    r13
0x180020cd9  push    r14
0x180020cdb  push    r15
0x180020cdd  mov     rbp, rsp
0x180020ce0  sub     rsp, 80h
0x180020ce7  xor     edi, edi
0x180020ce9  mov     eax, 208h
0x180020cee  mov     rsi, rcx
0x180020cf1  mov     [rbp+arg_10], edi
0x180020cf4  mov     [rbp+KeyHandle], rdi
0x180020cf8  xorps   xmm0, xmm0
0x180020cfb  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180020cff  mov     [rbp+Destination.MaximumLength], ax
0x180020d03  mov     r12, rdx
0x180020d06  xorps   xmm1, xmm1
0x180020d09  lea     edx, [rdi+8]; Flags
0x180020d0c  movups  xmmword ptr [rbp+KeyPath.Length], xmm1
0x180020d10  mov     rcx, gs:60h
0x180020d19  mov     r8d, eax; Size
0x180020d1c  mov     r15d, edi
0x180020d1f  mov     r14d, edi
0x180020d22  mov     r13d, edi
0x180020d25  mov     rcx, [rcx+30h]; HeapHandle
0x180020d29  call    cs:__imp_RtlAllocateHeap
0x180020d2f  mov     [rbp+Destination.Buffer], rax
0x180020d33  test    rax, rax
0x180020d36  jz      loc_180020F69
0x180020d3c  lea     rcx, [rbp+KeyPath]; KeyPath
0x180020d40  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180020d46  mov     ebx, eax
0x180020d48  test    eax, eax
0x180020d4a  js      loc_180020F91
0x180020d50  lea     rdx, [rbp+KeyPath]; Source
0x180020d54  lea     rcx, [rbp+Destination]; Destination
0x180020d58  call    cs:__imp_RtlAppendUnicodeStringToString
0x180020d5e  mov     ebx, eax
0x180020d60  test    eax, eax
0x180020d62  js      loc_180020F33
0x180020d68  lea     rdx, aSoftwareMicros_5; "\\Software\\Microsoft\\Windows\\Current"...
0x180020d6f  lea     rcx, [rbp+Destination]; Destination
0x180020d73  call    cs:__imp_RtlAppendUnicodeToString
0x180020d79  mov     ebx, eax
0x180020d7b  test    eax, eax
0x180020d7d  js      loc_180020F5A
0x180020d83  mov     [rbp+KeyHandle], rdi
0x180020d87  lea     rax, [rbp+Destination]
0x180020d8b  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x180020d8f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180020d93  xorps   xmm0, xmm0
0x180020d96  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180020d9e  lea     edi, [r14+1]
0x180020da2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180020daa  mov     edx, edi; DesiredAccess
0x180020dac  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180020db0  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180020db4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180020db9  call    cs:__imp_ZwOpenKey
0x180020dbf  mov     ebx, eax
0x180020dc1  test    eax, eax
0x180020dc3  js      loc_180020F0C
0x180020dc9  mov     rcx, gs:60h
0x180020dd2  lea     edx, [rdi+7]; Flags
0x180020dd5  mov     ebx, 208h
0x180020dda  mov     r8d, ebx; Size
0x180020ddd  mov     rcx, [rcx+30h]; HeapHandle
0x180020de1  call    cs:__imp_RtlAllocateHeap
0x180020de7  mov     r14, rax
0x180020dea  test    rax, rax
0x180020ded  jz      loc_180020FB6
0x180020df3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180020df7  lea     rax, [rbp+arg_10]
0x180020dfb  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180020e00  lea     rdx, ValueName; ValueName
0x180020e07  mov     r9, r14; KeyValueInformation
0x180020e0a  mov     dword ptr [rsp+80h+Length], ebx; Length
0x180020e0e  mov     r8d, edi; KeyValueInformationClass
0x180020e11  call    cs:__imp_NtQueryValueKey
0x180020e17  mov     ebx, eax
0x180020e19  cmp     eax, 0C0000023h
0x180020e1e  jz      loc_180020FE8
0x180020e24  cmp     ebx, 0C0000034h
0x180020e2a  jz      loc_180020F17
0x180020e30  xor     edx, edx; lpDst
0x180020e32  test    ebx, ebx
0x180020e34  js      loc_180020F1E
0x180020e3a  mov     eax, [r14+4]
0x180020e3e  sub     eax, edi
0x180020e40  cmp     eax, edi
0x180020e42  ja      loc_180020FD2
0x180020e48  mov     esi, [r14+8]
0x180020e4c  mov     ecx, [r14+0Ch]
0x180020e50  add     rsi, r14
0x180020e53  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020e57  mov     [rcx+rsi-2], dx
0x180020e5c  inc     rax
0x180020e5f  cmp     [rsi+rax*2], dx
0x180020e63  jnz     short loc_180020E5C
0x180020e65  cmp     dword ptr [r14+4], 2
0x180020e6a  jz      loc_18002104F
0x180020e70  mov     ebx, edx
0x180020e72  mov     r8d, eax; MaxCount
0x180020e75  mov     rdx, r12; String2
0x180020e78  mov     rcx, rsi; String1
0x180020e7b  call    _wcsnicmp_0
0x180020e80  xor     esi, esi
0x180020e82  test    eax, eax
0x180020e84  setz    r13b
0x180020e88  mov     rsi, [rbp+arg_0]
0x180020e8c  cmp     [rbp+KeyPath.Buffer], 0
0x180020e91  jz      short loc_180020E9D
0x180020e93  lea     rcx, [rbp+KeyPath]; UnicodeString
0x180020e97  call    cs:__imp_RtlFreeUnicodeString
0x180020e9d  mov     rcx, gs:60h
0x180020ea6  mov     rdx, [rbp+Destination.Buffer]
0x180020eaa  mov     rcx, [rcx+30h]
0x180020eae  call    AslFree
0x180020eb3  mov     rcx, gs:60h
0x180020ebc  mov     rdx, r14
0x180020ebf  mov     rcx, [rcx+30h]
0x180020ec3  call    AslFree
0x180020ec8  mov     rcx, [rbp+KeyHandle]; Handle
0x180020ecc  test    rcx, rcx
0x180020ecf  jz      short loc_180020ED7
0x180020ed1  call    cs:__imp_NtClose
0x180020ed7  mov     rcx, gs:60h
0x180020ee0  mov     rdx, r15
0x180020ee3  mov     rcx, [rcx+30h]
0x180020ee7  call    AslFree
0x180020eec  mov     eax, ebx
0x180020eee  mov     [rsi], r13d
0x180020ef1  mov     rbx, [rsp+80h+arg_8]
0x180020ef9  add     rsp, 80h
0x180020f00  pop     r15
0x180020f02  pop     r14
0x180020f04  pop     r13
0x180020f06  pop     r12
0x180020f08  pop     rdi
0x180020f09  pop     rsi
0x180020f0a  pop     rbp
0x180020f0b  retn
0x180020f0c  cmp     eax, 0C0000034h
0x180020f11  jnz     loc_180020FA0
0x180020f17  xor     ebx, ebx
0x180020f19  jmp     loc_180020E8C
0x180020f1e  mov     dword ptr [rsp+80h+Length], ebx
0x180020f22  lea     r9, aNtqueryvalueke; "NtQueryValueKey failed to get registry "...
0x180020f29  mov     r8d, 1DBh
0x180020f2f  mov     ecx, edi
0x180020f31  jmp     short loc_180020F49
0x180020f33  lea     r9, aRtlappendunico; "RtlAppendUnicodeStringToString failed f"...
0x180020f3a  mov     r8d, 198h
0x180020f40  mov     dword ptr [rsp+80h+Length], eax
0x180020f44  mov     ecx, 1
0x180020f49  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180020f50  call    AslLogCallPrintf
0x180020f55  jmp     loc_180020E8C
0x180020f5a  lea     r9, aRtlappendunico_1; "RtlAppendUnicodeToString failed for she"...
0x180020f61  mov     r8d, 19Eh
0x180020f67  jmp     short loc_180020F40
0x180020f69  mov     ebx, 0C0000017h
0x180020f6e  lea     r9, aOutOfMemory; "Out of memory"
0x180020f75  mov     r8d, 18Ch
0x180020f7b  mov     ecx, 1
0x180020f80  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x180020f87  call    AslLogCallPrintf
0x180020f8c  jmp     loc_180020E8C
0x180020f91  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x180020f98  mov     r8d, 192h
0x180020f9e  jmp     short loc_180020F40
0x180020fa0  mov     dword ptr [rsp+80h+Length], eax
0x180020fa4  lea     r9, aAslregistryope_1; "AslRegistryOpenKey failed [%x]"
0x180020fab  mov     r8d, 1ADh
0x180020fb1  jmp     loc_180020F2F
0x180020fb6  mov     r8d, 1B7h
0x180020fbc  jmp     short loc_180020FC4
0x180020fbe  mov     r8d, 1C7h
0x180020fc4  lea     r9, aOutOfMemory; "Out of memory"
0x180020fcb  mov     ebx, 0C0000017h
0x180020fd0  jmp     short loc_180020FE4
0x180020fd2  mov     ebx, 0C000014Ch
0x180020fd7  lea     r9, aErrorInRegistr; "Error in registry value retrieved with "...
0x180020fde  mov     r8d, 1E1h
0x180020fe4  mov     ecx, edi
0x180020fe6  jmp     short loc_180020F80
0x180020fe8  mov     rcx, gs:60h
0x180020ff1  mov     rdx, r14
0x180020ff4  mov     rcx, [rcx+30h]
0x180020ff8  call    AslFree
0x180020ffd  mov     rcx, gs:60h
0x180021006  mov     edx, 8; Flags
0x18002100b  mov     r8d, [rbp+arg_10]; Size
0x18002100f  mov     rcx, [rcx+30h]; HeapHandle
0x180021013  call    cs:__imp_RtlAllocateHeap
0x180021019  mov     r14, rax
0x18002101c  test    rax, rax
0x18002101f  jz      short loc_180020FBE
0x180021021  mov     eax, [rbp+arg_10]
0x180021024  lea     rcx, [rbp+arg_10]
0x180021028  mov     [rsp+80h+ResultLength], rcx; ResultLength
0x18002102d  lea     rdx, ValueName; ValueName
0x180021034  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180021038  mov     r9, r14; KeyValueInformation
0x18002103b  mov     r8d, edi; KeyValueInformationClass
0x18002103e  mov     dword ptr [rsp+80h+Length], eax; Length
0x180021042  call    cs:__imp_NtQueryValueKey
0x180021048  mov     ebx, eax
0x18002104a  jmp     loc_180020E24
0x18002104f  xor     r8d, r8d; nSize
0x180021052  mov     rcx, rsi; lpSrc
0x180021055  call    cs:__imp_ExpandEnvironmentStringsW
0x18002105b  mov     ebx, eax
0x18002105d  test    eax, eax
0x18002105f  jnz     short loc_1800210B3
0x180021061  mov     ebx, gs:68h
0x180021069  mov     eax, gs:68h
0x180021071  test    eax, eax
0x180021073  jle     short loc_18002107E
0x180021075  movzx   ebx, bx
0x180021078  or      ebx, 0C0070000h
0x18002107e  mov     r8d, 1EFh
0x180021084  jmp     short loc_180021095
0x180021086  movzx   ebx, bx
0x180021089  or      ebx, 0C0070000h
0x18002108f  mov     r8d, 1FDh
0x180021095  lea     r9, aFailedToExpand; "Failed to expand environment variables "...
0x18002109c  mov     dword ptr [rsp+80h+Length], ebx
0x1800210a0  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x1800210a7  mov     ecx, edi
0x1800210a9  call    AslLogCallPrintf
0x1800210ae  jmp     loc_180020E88
0x1800210b3  mov     rcx, gs:60h
0x1800210bc  mov     r8, rbx
0x1800210bf  add     r8, r8; Size
0x1800210c2  mov     edx, 8; Flags
0x1800210c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800210cb  call    cs:__imp_RtlAllocateHeap
0x1800210d1  mov     r15, rax
0x1800210d4  test    rax, rax
0x1800210d7  jnz     short loc_1800210FE
0x1800210d9  lea     r9, aOutOfMemory; "Out of memory"
0x1800210e0  mov     r8d, 1F6h
0x1800210e6  lea     rdx, aAslpathistempo_0; "AslPathIsTemporaryInternetFile"
0x1800210ed  mov     ecx, edi
0x1800210ef  mov     ebx, 0C0000017h
0x1800210f4  call    AslLogCallPrintf
0x1800210f9  jmp     loc_180020E88
0x1800210fe  mov     r8d, ebx; nSize
0x180021101  mov     rdx, r15; lpDst
0x180021104  mov     rcx, rsi; lpSrc
0x180021107  call    cs:__imp_ExpandEnvironmentStringsW
0x18002110d  xor     edx, edx
0x18002110f  test    eax, eax
0x180021111  jz      short loc_180021121
0x180021113  cmp     eax, ebx
0x180021115  ja      short loc_180021121
0x180021117  mov     rsi, r15
0x18002111a  dec     eax
0x18002111c  jmp     loc_180020E70
0x180021121  mov     ebx, gs:68h
0x180021129  mov     eax, gs:68h
0x180021131  test    eax, eax
0x180021133  jle     loc_18002108F
0x180021139  jmp     loc_180021086
```
