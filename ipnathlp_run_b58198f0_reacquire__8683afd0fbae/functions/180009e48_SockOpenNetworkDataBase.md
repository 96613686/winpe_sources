# SockOpenNetworkDataBase

- ea: `0x180009e48`
- end: `0x18000a204`
- name: `SockOpenNetworkDataBase`
- size: `956`
- prototype: `HANDLE __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009b60`

## callees

- `0x180008a70`
- `0x180008ac0`
- `0x180008b80`
- `0x180009e48`
- `0x180035820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a09e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a19e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a09e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a19e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a1d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a1d7`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180009f7a`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180009f7a`
- `ntdll!RtlFreeUnicodeString` at `0x18000a139`
- `ntdll!RtlFreeUnicodeString` at `0x18000a139`
- `ntdll!NtOpenKey` at `0x18000a127`
- `ntdll!NtOpenKey` at `0x18000a127`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000a0ea`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000a0ea`
- `ntdll!RtlAllocateHeap` at `0x180009e96`
- `ntdll!RtlAllocateHeap` at `0x180009ec0`
- `ntdll!RtlAllocateHeap` at `0x180009e96`
- `ntdll!RtlAllocateHeap` at `0x180009ec0`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009ef7`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009ef7`
- `ntdll!RtlFreeHeap` at `0x180009fa3`
- `ntdll!RtlFreeHeap` at `0x180009fe6`
- `ntdll!RtlFreeHeap` at `0x180009fa3`
- `ntdll!RtlFreeHeap` at `0x180009fe6`
- `ntdll!RtlInitString` at `0x18000a0d3`
- `ntdll!RtlInitString` at `0x18000a0d3`
- `ntdll!RtlNtStatusToDosError` at `0x180009f18`
- `ntdll!RtlNtStatusToDosError` at `0x180009f18`
- `ntdll!NtClose` at `0x18000a077`
- `ntdll!NtClose` at `0x18000a077`

## string_xrefs

- `0x18000a14d`: `\Registry\Machine\System\CurrentControlSet\Services\Tcp\Parameters`
- `0x18000a049`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18000a0b2`: `\Registry\Machine\System\CurrentControlSet\Services\Tcp\VParameters`

## pseudocode

```c
HANDLE __fastcall SockOpenNetworkDataBase(__int64 a1, char *a2)
{
  HANDLE FileA; // rsi
  CHAR *Heap; // rdi
  WCHAR *v5; // rax
  WCHAR *v6; // r15
  NTSTATUS PersistedStateLocation; // eax
  DWORD v8; // ecx
  __int64 v9; // r8
  char *v10; // rax
  __int64 v11; // r9
  __int64 v13; // rax
  CHAR *v14; // r9
  __int64 v15; // rcx
  char *v16; // r8
  char *v17; // rax
  __int64 v18; // rdx
  int SingleValue; // ebx
  __int64 v20; // rax
  NTSTATUS v21; // ebx
  size_t v22; // rdx
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-41h]
  size_t dwCreationDispositiona; // [rsp+28h] [rbp-41h]
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-21h] BYREF
  struct _STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+5Fh] BYREF
  int v29; // [rsp+E0h] [rbp+77h] BYREF

  Handle = 0;
  v29 = 0;
  FileA = 0;
  Heap = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  if ( !Heap )
  {
    SetLastError(8u);
    return FileA;
  }
  v5 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  v6 = v5;
  if ( !v5 )
  {
    v8 = 8;
    goto LABEL_30;
  }
  dwCreationDisposition = (unsigned int)v5;
  PersistedStateLocation = RtlGetPersistedStateLocation(L"WinsockDatabase", 0, 0, 1);
  if ( PersistedStateLocation == -1073741772 )
  {
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    UnicodeString = 0;
    RtlInitString(&DestinationString, VTCPPARM);
    RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v21 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    RtlFreeUnicodeString(&UnicodeString);
    if ( v21 < 0 && (int)SockOpenKey(&Handle) < 0 && (int)SockOpenKey(&Handle) < 0 )
    {
      v8 = 1011;
      goto LABEL_30;
    }
    SingleValue = SockGetSingleValue(Handle, v18, Heap, &v29, dwCreationDisposition);
    NtClose(Handle);
    if ( SingleValue < 0 )
    {
      v8 = 1012;
      goto LABEL_30;
    }
LABEL_26:
    v20 = -1;
    do
      ++v20;
    while ( Heap[v20] );
    if ( (int)v20 + 11 <= 272 )
    {
      v13 = 2147483646;
      v14 = Heap;
      v15 = 272;
      v16 = a2;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v13;
        --v15;
      }
      while ( v15 );
      v17 = v16 - 1;
      if ( v15 )
        v17 = v16;
      *v17 = 0;
      if ( v15 )
      {
        v9 = 272;
        v10 = a2;
        do
        {
          if ( !*v10 )
            break;
          ++v10;
          --v9;
        }
        while ( v9 );
        if ( v9 )
        {
          v11 = (272 - v9) & -(__int64)(v9 != 0);
          if ( StringCopyWorkerA(&a2[v11], 272 - v11, (size_t *)v9, "\\", dwCreationDispositiona) >= 0 )
            StringCbCatA(a2, v22, "hosts.ics");
        }
      }
      FileA = CreateFileA(a2, 0xC0000000, 0, 0, 4u, 0, 0);
      if ( FileA == (HANDLE)-1LL )
        FileA = 0;
      goto LABEL_12;
    }
    v8 = 122;
    goto LABEL_30;
  }
  if ( PersistedStateLocation < 0 )
  {
    v8 = RtlNtStatusToDosError(PersistedStateLocation);
LABEL_30:
    SetLastError(v8);
    goto LABEL_12;
  }
  if ( WideCharToMultiByte(0, 0x400u, v6, -1, Heap, 1024, 0, 0) > 0 )
    goto LABEL_26;
LABEL_12:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return FileA;
}

```

## disassembly

```asm
0x180009e48  mov     rax, rsp
0x180009e4b  mov     [rax+10h], rbx
0x180009e4f  mov     [rax+18h], rsi
0x180009e53  mov     [rax+20h], r9d
0x180009e57  mov     [rax+8], rcx
0x180009e5b  push    rbp
0x180009e5c  push    rdi
0x180009e5d  push    r12
0x180009e5f  push    r14
0x180009e61  push    r15
0x180009e63  lea     rbp, [rax-57h]
0x180009e67  sub     rsp, 90h
0x180009e6e  xor     r12d, r12d
0x180009e71  mov     r14, rdx
0x180009e74  mov     [rbp+4Fh+Handle], r12
0x180009e78  mov     ebx, 400h
0x180009e7d  mov     rcx, gs:60h
0x180009e86  mov     r8d, ebx; Size
0x180009e89  xor     edx, edx; Flags
0x180009e8b  mov     [rbp+4Fh+arg_18], r12d
0x180009e8f  mov     esi, r12d
0x180009e92  mov     rcx, [rcx+30h]; HeapHandle
0x180009e96  call    cs:__imp_RtlAllocateHeap
0x180009e9d  nop     dword ptr [rax+rax+00h]
0x180009ea2  mov     rdi, rax
0x180009ea5  test    rax, rax
0x180009ea8  jz      loc_18000A199
0x180009eae  mov     rcx, gs:60h
0x180009eb7  mov     r8d, ebx; Size
0x180009eba  xor     edx, edx; Flags
0x180009ebc  mov     rcx, [rcx+30h]; HeapHandle
0x180009ec0  call    cs:__imp_RtlAllocateHeap
0x180009ec7  nop     dword ptr [rax+rax+00h]
0x180009ecc  mov     r15, rax
0x180009ecf  test    rax, rax
0x180009ed2  jz      loc_18000A1AF
0x180009ed8  mov     [rsp+0B0h+hTemplateFile], r12
0x180009edd  lea     r9d, [r12+1]
0x180009ee2  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x180009ee6  lea     rcx, aWinsockdatabas; "WinsockDatabase"
0x180009eed  xor     r8d, r8d
0x180009ef0  mov     [rsp+0B0h+dwCreationDisposition], rax; ULONG
0x180009ef5  xor     edx, edx
0x180009ef7  call    cs:__imp_RtlGetPersistedStateLocation
0x180009efe  nop     dword ptr [rax+rax+00h]
0x180009f03  cmp     eax, 0C0000034h
0x180009f08  jz      loc_18000A0AF
0x180009f0e  test    eax, eax
0x180009f10  jns     loc_18000A1B9
0x180009f16  mov     ecx, eax; Status
0x180009f18  call    cs:__imp_RtlNtStatusToDosError
0x180009f1f  nop     dword ptr [rax+rax+00h]
0x180009f24  mov     ecx, eax
0x180009f26  jmp     loc_18000A09E
0x180009f2b  mov     r8, rdx
0x180009f2e  mov     rax, r14
0x180009f31  cmp     [rax], r12b
0x180009f34  jz      short loc_180009F3F
0x180009f36  inc     rax
0x180009f39  sub     r8, 1; pcchNewDestLength
0x180009f3d  jnz     short loc_180009F31
0x180009f3f  mov     rcx, rdx
0x180009f42  mov     rax, r8
0x180009f45  sub     rcx, r8
0x180009f48  neg     rax
0x180009f4b  sbb     r9, r9
0x180009f4e  and     r9, rcx
0x180009f51  test    r8, r8
0x180009f54  jnz     loc_18000A16A
0x180009f5a  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x180009f5f  xor     r9d, r9d; lpSecurityAttributes
0x180009f62  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180009f67  xor     r8d, r8d; dwShareMode
0x180009f6a  mov     edx, 0C0000000h; dwDesiredAccess
0x180009f6f  mov     dword ptr [rsp+0B0h+dwCreationDisposition], 4; dwCreationDisposition
0x180009f77  mov     rcx, r14; lpFileName
0x180009f7a  call    cs:__imp_CreateFileA
0x180009f81  nop     dword ptr [rax+rax+00h]
0x180009f86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009f8a  mov     rsi, rax
0x180009f8d  cmovz   rsi, r12
0x180009f91  mov     rcx, gs:60h
0x180009f9a  mov     r8, rdi; P
0x180009f9d  xor     edx, edx; Flags
0x180009f9f  mov     rcx, [rcx+30h]; HeapHandle
0x180009fa3  call    cs:__imp_RtlFreeHeap
0x180009faa  nop     dword ptr [rax+rax+00h]
0x180009faf  test    r15, r15
0x180009fb2  jnz     short loc_180009FD4
0x180009fb4  lea     r11, [rsp+0B0h+var_20]
0x180009fbc  mov     rax, rsi
0x180009fbf  mov     rbx, [r11+38h]
0x180009fc3  mov     rsi, [r11+40h]
0x180009fc7  mov     rsp, r11
0x180009fca  pop     r15
0x180009fcc  pop     r14
0x180009fce  pop     r12
0x180009fd0  pop     rdi
0x180009fd1  pop     rbp
0x180009fd2  retn
0x180009fd4  mov     rcx, gs:60h
0x180009fdd  mov     r8, r15; P
0x180009fe0  xor     edx, edx; Flags
0x180009fe2  mov     rcx, [rcx+30h]; HeapHandle
0x180009fe6  call    cs:__imp_RtlFreeHeap
0x180009fed  nop     dword ptr [rax+rax+00h]
0x180009ff2  jmp     short loc_180009FB4
0x180009ff4  add     eax, 0Bh
0x180009ff7  mov     edx, 110h
0x180009ffc  cmp     eax, edx
0x180009ffe  jg      loc_18000A1FA
0x18000a004  mov     eax, 7FFFFFFEh
0x18000a009  mov     r9, rdi
0x18000a00c  mov     ecx, edx
0x18000a00e  mov     r8, r14
0x18000a011  test    rax, rax
0x18000a014  jz      short loc_18000A030
0x18000a016  mov     r10b, [r9]
0x18000a019  test    r10b, r10b
0x18000a01c  jz      short loc_18000A030
0x18000a01e  mov     [r8], r10b
0x18000a021  inc     r9
0x18000a024  inc     r8
0x18000a027  dec     rax
0x18000a02a  sub     rcx, 1
0x18000a02e  jnz     short loc_18000A011
0x18000a030  test    rcx, rcx
0x18000a033  lea     rax, [r8-1]
0x18000a037  cmovnz  rax, r8
0x18000a03b  mov     [rax], r12b
0x18000a03e  jnz     loc_180009F2B
0x18000a044  jmp     loc_180009F5A
0x18000a049  lea     rdx, TCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a050  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18000a054  call    SockOpenKey
0x18000a059  test    eax, eax
0x18000a05b  js      loc_18000A1F0
0x18000a061  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18000a065  lea     r9, [rbp+4Fh+arg_18]
0x18000a069  mov     r8, rdi
0x18000a06c  call    SockGetSingleValue
0x18000a071  mov     rcx, [rbp+4Fh+Handle]; Handle
0x18000a075  mov     ebx, eax
0x18000a077  call    cs:__imp_NtClose
0x18000a07e  nop     dword ptr [rax+rax+00h]
0x18000a083  test    ebx, ebx
0x18000a085  js      short loc_18000A099
0x18000a087  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a08b  inc     rax
0x18000a08e  cmp     [rdi+rax], r12b
0x18000a092  jnz     short loc_18000A08B
0x18000a094  jmp     loc_180009FF4
0x18000a099  mov     ecx, 3F4h; dwErrCode
0x18000a09e  call    cs:__imp_SetLastError
0x18000a0a5  nop     dword ptr [rax+rax+00h]
0x18000a0aa  jmp     loc_180009F91
0x18000a0af  xorps   xmm0, xmm0
0x18000a0b2  lea     rdx, VTCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a0b9  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18000a0bd  xor     eax, eax
0x18000a0bf  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18000a0c3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x18000a0c7  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18000a0cb  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18000a0cf  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x18000a0d3  call    cs:__imp_RtlInitString
0x18000a0da  nop     dword ptr [rax+rax+00h]
0x18000a0df  mov     r8b, 1; AllocateDestinationString
0x18000a0e2  lea     rdx, [rbp+4Fh+DestinationString]; SourceString
0x18000a0e6  lea     rcx, [rbp+4Fh+UnicodeString]; DestinationString
0x18000a0ea  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000a0f1  nop     dword ptr [rax+rax+00h]
0x18000a0f6  lea     rax, [rbp+4Fh+UnicodeString]
0x18000a0fa  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000a102  xorps   xmm0, xmm0
0x18000a105  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18000a109  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000a10d  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18000a115  mov     edx, 20019h; DesiredAccess
0x18000a11a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18000a11e  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18000a122  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a127  call    cs:__imp_NtOpenKey
0x18000a12e  nop     dword ptr [rax+rax+00h]
0x18000a133  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x18000a137  mov     ebx, eax
0x18000a139  call    cs:__imp_RtlFreeUnicodeString
0x18000a140  nop     dword ptr [rax+rax+00h]
0x18000a145  test    ebx, ebx
0x18000a147  jns     loc_18000A061
0x18000a14d  lea     rdx, NTCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a154  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18000a158  call    SockOpenKey
0x18000a15d  test    eax, eax
0x18000a15f  jns     loc_18000A061
0x18000a165  jmp     loc_18000A049
0x18000a16a  sub     rdx, r9; cchDest
0x18000a16d  lea     rcx, [r9+r14]; pszDest
0x18000a171  lea     r9, pszSrc; "\\"
0x18000a178  call    StringCopyWorkerA
0x18000a17d  test    eax, eax
0x18000a17f  js      loc_180009F5A
0x18000a185  lea     r8, aHostsIcs; "hosts.ics"
0x18000a18c  mov     rcx, r14; pszDest
0x18000a18f  call    StringCbCatA
0x18000a194  jmp     loc_180009F5A
0x18000a199  mov     ecx, 8; dwErrCode
0x18000a19e  call    cs:__imp_SetLastError
0x18000a1a5  nop     dword ptr [rax+rax+00h]
0x18000a1aa  jmp     loc_180009FB4
0x18000a1af  mov     ecx, 8
0x18000a1b4  jmp     loc_18000A09E
0x18000a1b9  mov     [rsp+0B0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000a1be  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000a1c2  mov     [rsp+0B0h+hTemplateFile], r12; lpDefaultChar
0x18000a1c7  mov     r8, r15; lpWideCharStr
0x18000a1ca  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx; cbMultiByte
0x18000a1ce  mov     edx, ebx; dwFlags
0x18000a1d0  xor     ecx, ecx; CodePage
0x18000a1d2  mov     [rsp+0B0h+dwCreationDisposition], rdi; lpMultiByteStr
0x18000a1d7  call    cs:__imp_WideCharToMultiByte
0x18000a1de  nop     dword ptr [rax+rax+00h]
0x18000a1e3  test    eax, eax
0x18000a1e5  jle     loc_180009F91
0x18000a1eb  jmp     loc_18000A087
0x18000a1f0  mov     ecx, 3F3h
0x18000a1f5  jmp     loc_18000A09E
0x18000a1fa  mov     ecx, 7Ah ; 'z'
0x18000a1ff  jmp     loc_18000A09E
```
