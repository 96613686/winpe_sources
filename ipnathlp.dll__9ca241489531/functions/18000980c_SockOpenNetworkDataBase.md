# SockOpenNetworkDataBase

- ea: `0x18000980c`
- end: `0x180009b6d`
- name: `SockOpenNetworkDataBase`
- size: `865`
- prototype: `HANDLE __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009538`

## callees

- `0x180008580`
- `0x1800085d0`
- `0x180008670`
- `0x18000980c`
- `0x180032f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b13`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009b46`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009b46`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180009926`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180009926`
- `ntdll!RtlFreeUnicodeString` at `0x180009ab4`
- `ntdll!RtlFreeUnicodeString` at `0x180009ab4`
- `ntdll!NtOpenKey` at `0x180009aa8`
- `ntdll!NtOpenKey` at `0x180009aa8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180009a71`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180009a71`
- `ntdll!RtlAllocateHeap` at `0x18000985a`
- `ntdll!RtlAllocateHeap` at `0x18000987e`
- `ntdll!RtlAllocateHeap` at `0x18000985a`
- `ntdll!RtlAllocateHeap` at `0x18000987e`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800098af`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800098af`
- `ntdll!RtlFreeHeap` at `0x180009949`
- `ntdll!RtlFreeHeap` at `0x180009985`
- `ntdll!RtlFreeHeap` at `0x180009949`
- `ntdll!RtlFreeHeap` at `0x180009985`
- `ntdll!RtlInitString` at `0x180009a60`
- `ntdll!RtlInitString` at `0x180009a60`
- `ntdll!RtlNtStatusToDosError` at `0x1800098ca`
- `ntdll!RtlNtStatusToDosError` at `0x1800098ca`
- `ntdll!NtClose` at `0x180009a10`
- `ntdll!NtClose` at `0x180009a10`

## string_xrefs

- `0x180009ac2`: `\Registry\Machine\System\CurrentControlSet\Services\Tcp\Parameters`
- `0x1800099e2`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180009a3f`: `\Registry\Machine\System\CurrentControlSet\Services\Tcp\VParameters`

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
  int SingleValue; // ebx
  __int64 v19; // rax
  NTSTATUS v20; // ebx
  size_t v21; // rdx
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-41h]
  size_t dwCreationDispositiona; // [rsp+28h] [rbp-41h]
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-21h] BYREF
  struct _STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+5Fh] BYREF
  int v28; // [rsp+E0h] [rbp+77h]

  Handle = 0;
  v28 = 0;
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
    v20 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    RtlFreeUnicodeString(&UnicodeString);
    if ( v20 < 0 && (int)SockOpenKey(&Handle) < 0 && (int)SockOpenKey(&Handle) < 0 )
    {
      v8 = 1011;
      goto LABEL_30;
    }
    SingleValue = SockGetSingleValue(Handle, dwCreationDisposition);
    NtClose(Handle);
    if ( SingleValue < 0 )
    {
      v8 = 1012;
      goto LABEL_30;
    }
LABEL_26:
    v19 = -1;
    do
      ++v19;
    while ( Heap[v19] );
    if ( (int)v19 + 11 <= 272 )
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
            StringCbCatA(a2, v21, "hosts.ics");
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
0x18000980c  mov     rax, rsp
0x18000980f  mov     [rax+10h], rbx
0x180009813  mov     [rax+18h], rsi
0x180009817  mov     [rax+20h], r9d
0x18000981b  mov     [rax+8], rcx
0x18000981f  push    rbp
0x180009820  push    rdi
0x180009821  push    r12
0x180009823  push    r14
0x180009825  push    r15
0x180009827  lea     rbp, [rax-57h]
0x18000982b  sub     rsp, 90h
0x180009832  xor     r12d, r12d
0x180009835  mov     r14, rdx
0x180009838  mov     [rbp+4Fh+Handle], r12
0x18000983c  mov     ebx, 400h
0x180009841  mov     rcx, gs:60h
0x18000984a  mov     r8d, ebx; Size
0x18000984d  xor     edx, edx; Flags
0x18000984f  mov     [rbp+4Fh+arg_18], r12d
0x180009853  mov     esi, r12d
0x180009856  mov     rcx, [rcx+30h]; HeapHandle
0x18000985a  call    cs:__imp_RtlAllocateHeap
0x180009860  mov     rdi, rax
0x180009863  test    rax, rax
0x180009866  jz      loc_180009B0E
0x18000986c  mov     rcx, gs:60h
0x180009875  mov     r8d, ebx; Size
0x180009878  xor     edx, edx; Flags
0x18000987a  mov     rcx, [rcx+30h]; HeapHandle
0x18000987e  call    cs:__imp_RtlAllocateHeap
0x180009884  mov     r15, rax
0x180009887  test    rax, rax
0x18000988a  jz      loc_180009B1E
0x180009890  mov     [rsp+0B0h+hTemplateFile], r12
0x180009895  lea     r9d, [r12+1]
0x18000989a  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x18000989e  lea     rcx, aWinsockdatabas; "WinsockDatabase"
0x1800098a5  xor     r8d, r8d
0x1800098a8  mov     [rsp+0B0h+dwCreationDisposition], rax; ULONG
0x1800098ad  xor     edx, edx
0x1800098af  call    cs:__imp_RtlGetPersistedStateLocation
0x1800098b5  cmp     eax, 0C0000034h
0x1800098ba  jz      loc_180009A3C
0x1800098c0  test    eax, eax
0x1800098c2  jns     loc_180009B28
0x1800098c8  mov     ecx, eax; Status
0x1800098ca  call    cs:__imp_RtlNtStatusToDosError
0x1800098d0  mov     ecx, eax
0x1800098d2  jmp     loc_180009A31
0x1800098d7  mov     r8, rdx
0x1800098da  mov     rax, r14
0x1800098dd  cmp     [rax], r12b
0x1800098e0  jz      short loc_1800098EB
0x1800098e2  inc     rax
0x1800098e5  sub     r8, 1; pcchNewDestLength
0x1800098e9  jnz     short loc_1800098DD
0x1800098eb  mov     rcx, rdx
0x1800098ee  mov     rax, r8
0x1800098f1  sub     rcx, r8
0x1800098f4  neg     rax
0x1800098f7  sbb     r9, r9
0x1800098fa  and     r9, rcx
0x1800098fd  test    r8, r8
0x180009900  jnz     loc_180009ADF
0x180009906  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x18000990b  xor     r9d, r9d; lpSecurityAttributes
0x18000990e  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180009913  xor     r8d, r8d; dwShareMode
0x180009916  mov     edx, 0C0000000h; dwDesiredAccess
0x18000991b  mov     dword ptr [rsp+0B0h+dwCreationDisposition], 4; dwCreationDisposition
0x180009923  mov     rcx, r14; lpFileName
0x180009926  call    cs:__imp_CreateFileA
0x18000992c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009930  mov     rsi, rax
0x180009933  cmovz   rsi, r12
0x180009937  mov     rcx, gs:60h
0x180009940  mov     r8, rdi; P
0x180009943  xor     edx, edx; Flags
0x180009945  mov     rcx, [rcx+30h]; HeapHandle
0x180009949  call    cs:__imp_RtlFreeHeap
0x18000994f  test    r15, r15
0x180009952  jnz     short loc_180009973
0x180009954  lea     r11, [rsp+0B0h+var_20]
0x18000995c  mov     rax, rsi
0x18000995f  mov     rbx, [r11+38h]
0x180009963  mov     rsi, [r11+40h]
0x180009967  mov     rsp, r11
0x18000996a  pop     r15
0x18000996c  pop     r14
0x18000996e  pop     r12
0x180009970  pop     rdi
0x180009971  pop     rbp
0x180009972  retn
0x180009973  mov     rcx, gs:60h
0x18000997c  mov     r8, r15; P
0x18000997f  xor     edx, edx; Flags
0x180009981  mov     rcx, [rcx+30h]; HeapHandle
0x180009985  call    cs:__imp_RtlFreeHeap
0x18000998b  jmp     short loc_180009954
0x18000998d  add     eax, 0Bh
0x180009990  mov     edx, 110h
0x180009995  cmp     eax, edx
0x180009997  jg      loc_180009B63
0x18000999d  mov     eax, 7FFFFFFEh
0x1800099a2  mov     r9, rdi
0x1800099a5  mov     ecx, edx
0x1800099a7  mov     r8, r14
0x1800099aa  test    rax, rax
0x1800099ad  jz      short loc_1800099C9
0x1800099af  mov     r10b, [r9]
0x1800099b2  test    r10b, r10b
0x1800099b5  jz      short loc_1800099C9
0x1800099b7  mov     [r8], r10b
0x1800099ba  inc     r9
0x1800099bd  inc     r8
0x1800099c0  dec     rax
0x1800099c3  sub     rcx, 1
0x1800099c7  jnz     short loc_1800099AA
0x1800099c9  test    rcx, rcx
0x1800099cc  lea     rax, [r8-1]
0x1800099d0  cmovnz  rax, r8
0x1800099d4  mov     [rax], r12b
0x1800099d7  jnz     loc_1800098D7
0x1800099dd  jmp     loc_180009906
0x1800099e2  lea     rdx, TCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800099e9  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x1800099ed  call    SockOpenKey
0x1800099f2  test    eax, eax
0x1800099f4  js      loc_180009B59
0x1800099fa  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x1800099fe  lea     r9, [rbp+4Fh+arg_18]
0x180009a02  mov     r8, rdi
0x180009a05  call    SockGetSingleValue
0x180009a0a  mov     rcx, [rbp+4Fh+Handle]; Handle
0x180009a0e  mov     ebx, eax
0x180009a10  call    cs:__imp_NtClose
0x180009a16  test    ebx, ebx
0x180009a18  js      short loc_180009A2C
0x180009a1a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a1e  inc     rax
0x180009a21  cmp     [rdi+rax], r12b
0x180009a25  jnz     short loc_180009A1E
0x180009a27  jmp     loc_18000998D
0x180009a2c  mov     ecx, 3F4h; dwErrCode
0x180009a31  call    cs:__imp_SetLastError
0x180009a37  jmp     loc_180009937
0x180009a3c  xorps   xmm0, xmm0
0x180009a3f  lea     rdx, VTCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x180009a46  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x180009a4a  xor     eax, eax
0x180009a4c  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180009a50  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x180009a54  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180009a58  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x180009a5c  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x180009a60  call    cs:__imp_RtlInitString
0x180009a66  mov     r8b, 1; AllocateDestinationString
0x180009a69  lea     rdx, [rbp+4Fh+DestinationString]; SourceString
0x180009a6d  lea     rcx, [rbp+4Fh+UnicodeString]; DestinationString
0x180009a71  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180009a77  lea     rax, [rbp+4Fh+UnicodeString]
0x180009a7b  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180009a83  xorps   xmm0, xmm0
0x180009a86  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180009a8a  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180009a8e  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180009a96  mov     edx, 20019h; DesiredAccess
0x180009a9b  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180009a9f  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x180009aa3  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180009aa8  call    cs:__imp_NtOpenKey
0x180009aae  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x180009ab2  mov     ebx, eax
0x180009ab4  call    cs:__imp_RtlFreeUnicodeString
0x180009aba  test    ebx, ebx
0x180009abc  jns     loc_1800099FA
0x180009ac2  lea     rdx, NTCPPARM; "\\Registry\\Machine\\System\\CurrentCon"...
0x180009ac9  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x180009acd  call    SockOpenKey
0x180009ad2  test    eax, eax
0x180009ad4  jns     loc_1800099FA
0x180009ada  jmp     loc_1800099E2
0x180009adf  sub     rdx, r9; cchDest
0x180009ae2  lea     rcx, [r9+r14]; pszDest
0x180009ae6  lea     r9, pszSrc; "\\"
0x180009aed  call    StringCopyWorkerA
0x180009af2  test    eax, eax
0x180009af4  js      loc_180009906
0x180009afa  lea     r8, aHostsIcs; "hosts.ics"
0x180009b01  mov     rcx, r14; pszDest
0x180009b04  call    StringCbCatA
0x180009b09  jmp     loc_180009906
0x180009b0e  mov     ecx, 8; dwErrCode
0x180009b13  call    cs:__imp_SetLastError
0x180009b19  jmp     loc_180009954
0x180009b1e  mov     ecx, 8
0x180009b23  jmp     loc_180009A31
0x180009b28  mov     [rsp+0B0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180009b2d  or      r9d, 0FFFFFFFFh; cchWideChar
0x180009b31  mov     [rsp+0B0h+hTemplateFile], r12; lpDefaultChar
0x180009b36  mov     r8, r15; lpWideCharStr
0x180009b39  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx; cbMultiByte
0x180009b3d  mov     edx, ebx; dwFlags
0x180009b3f  xor     ecx, ecx; CodePage
0x180009b41  mov     [rsp+0B0h+dwCreationDisposition], rdi; lpMultiByteStr
0x180009b46  call    cs:__imp_WideCharToMultiByte
0x180009b4c  test    eax, eax
0x180009b4e  jle     loc_180009937
0x180009b54  jmp     loc_180009A1A
0x180009b59  mov     ecx, 3F3h
0x180009b5e  jmp     loc_180009A31
0x180009b63  mov     ecx, 7Ah ; 'z'
0x180009b68  jmp     loc_180009A31
```
