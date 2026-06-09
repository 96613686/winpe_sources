# NlFlushNetbiosCacheName(ushort const *,char,_NL_TRANSPORT *)

- ea: `0x18003d3ac`
- end: `0x18003d5cf`
- name: `?NlFlushNetbiosCacheName@@YAJPEBGDPEAU_NL_TRANSPORT@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(PCWCH UnicodeString, char, struct _NL_TRANSPORT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c9b8`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18003d3ac`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18003d491`
- `ntdll!NtCreateFile` at `0x18003d491`
- `ntdll!NtDeviceIoControlFile` at `0x18003d56e`
- `ntdll!NtDeviceIoControlFile` at `0x18003d56e`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d4aa`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d4e0`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d4aa`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d4e0`
- `ntdll!RtlEnterCriticalSection` at `0x18003d3ef`
- `ntdll!RtlEnterCriticalSection` at `0x18003d3ef`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18003d517`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18003d517`
- `ntdll!RtlInitUnicodeString` at `0x18003d42b`
- `ntdll!RtlInitUnicodeString` at `0x18003d42b`

## string_xrefs

- `0x18003d4b9`: `NlFlushNetbiosCacheName: NtCreateFile failed 0x%lx\n`
- `0x18003d529`: `NlFlushNetbiosCacheName: RtlUpcaseUnicodeToOemN failed 0x%lx\n`
- `0x18003d590`: `NlFlushNetbiosCacheName: NtDeviceIoControlFile failed 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlFlushNetbiosCacheName(PCWCH UnicodeString, CHAR a2, const WCHAR *a3)
{
  __int64 v6; // rbx
  NTSTATUS v7; // esi
  unsigned int v9; // ebx
  void *v10; // rcx
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  CHAR OemString[16]; // [rsp+B8h] [rbp+1Fh] BYREF

  IoStatusBlock = 0;
  RtlEnterCriticalSection(&NlGlobalTransportCritSect);
  v6 = -1;
  if ( *((_QWORD *)a3 + 3) == -1 )
  {
    FileHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a3 + 16);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtCreateFile(&FileHandle, 0x2000000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0, 0, 0);
    if ( v7 < 0 )
    {
      RtlLeaveCriticalSection(&NlGlobalTransportCritSect);
      NlPrintRoutine(0x100u, L"NlFlushNetbiosCacheName: NtCreateFile failed 0x%lx\n", (unsigned int)v7);
      return (unsigned int)v7;
    }
    *((_QWORD *)a3 + 3) = FileHandle;
  }
  RtlLeaveCriticalSection(&NlGlobalTransportCritSect);
  *(__m128i *)OemString = _mm_load_si128((const __m128i *)&_xmm);
  do
    ++v6;
  while ( UnicodeString[v6] );
  v9 = RtlUpcaseUnicodeToOemN(OemString, 0xFu, 0, UnicodeString, 2 * v6);
  if ( (v9 & 0x80000000) == 0 )
  {
    v10 = (void *)*((_QWORD *)a3 + 3);
    OemString[15] = a2;
    v9 = NtDeviceIoControlFile(v10, 0, 0, 0, &IoStatusBlock, 0x2180E0u, OemString, 0x10u, 0, 0);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741685 )
      NlPrintRoutine(0x100u, L"NlFlushNetbiosCacheName: NtDeviceIoControlFile failed 0x%lx\n", v9);
  }
  else
  {
    NlPrintRoutine(0x100u, L"NlFlushNetbiosCacheName: RtlUpcaseUnicodeToOemN failed 0x%lx\n", v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18003d3ac  mov     [rsp-8+arg_8], rbx
0x18003d3b1  mov     [rsp-8+arg_18], rsi
0x18003d3b6  push    rbp
0x18003d3b7  push    rdi
0x18003d3b8  push    r12
0x18003d3ba  push    r14
0x18003d3bc  push    r15
0x18003d3be  lea     rbp, [rsp-37h]
0x18003d3c3  sub     rsp, 0D0h
0x18003d3ca  mov     rax, cs:__security_cookie
0x18003d3d1  xor     rax, rsp
0x18003d3d4  mov     [rbp+57h+var_28], rax
0x18003d3d8  mov     r14, rcx
0x18003d3db  xorps   xmm0, xmm0
0x18003d3de  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18003d3e5  mov     rdi, r8
0x18003d3e8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18003d3ec  mov     r15b, dl
0x18003d3ef  call    cs:__imp_RtlEnterCriticalSection
0x18003d3f6  nop     dword ptr [rax+rax+00h]
0x18003d3fb  xor     r12d, r12d
0x18003d3fe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d402  cmp     [rdi+18h], rbx
0x18003d406  jnz     loc_18003D4D9
0x18003d40c  xorps   xmm0, xmm0
0x18003d40f  mov     [rbp+57h+FileHandle], r12
0x18003d413  lea     rdx, [rdi+20h]; SourceString
0x18003d417  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003d41b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003d41f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003d423  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d427  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003d42b  call    cs:__imp_RtlInitUnicodeString
0x18003d432  nop     dword ptr [rax+rax+00h]
0x18003d437  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x18003d43c  lea     rax, [rbp+57h+DestinationString]
0x18003d440  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x18003d445  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18003d449  mov     [rsp+0F0h+CreateOptions], r12d; CreateOptions
0x18003d44e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003d452  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003d456  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003d45a  lea     eax, [rbx+4]
0x18003d45d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003d464  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x18003d468  xorps   xmm0, xmm0
0x18003d46b  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x18003d46f  mov     edx, 2000000h; DesiredAccess
0x18003d474  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x18003d47c  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x18003d481  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18003d485  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18003d48c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d491  call    cs:__imp_NtCreateFile
0x18003d498  nop     dword ptr [rax+rax+00h]
0x18003d49d  mov     esi, eax
0x18003d49f  test    eax, eax
0x18003d4a1  jns     short loc_18003D4D1
0x18003d4a3  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18003d4aa  call    cs:__imp_RtlLeaveCriticalSection
0x18003d4b1  nop     dword ptr [rax+rax+00h]
0x18003d4b6  mov     r8d, esi
0x18003d4b9  lea     rdx, aNlflushnetbios_0; "NlFlushNetbiosCacheName: NtCreateFile f"...
0x18003d4c0  mov     ecx, 100h; unsigned int
0x18003d4c5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003d4ca  mov     eax, esi
0x18003d4cc  jmp     loc_18003D5A6
0x18003d4d1  mov     rax, [rbp+57h+FileHandle]
0x18003d4d5  mov     [rdi+18h], rax
0x18003d4d9  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18003d4e0  call    cs:__imp_RtlLeaveCriticalSection
0x18003d4e7  nop     dword ptr [rax+rax+00h]
0x18003d4ec  movdqa  xmm0, cs:__xmm@20202020202020202020202020202020
0x18003d4f4  movups  xmmword ptr [rbp+57h+OemString], xmm0
0x18003d4f8  inc     rbx
0x18003d4fb  cmp     [r14+rbx*2], r12w
0x18003d500  jnz     short loc_18003D4F8
0x18003d502  xor     r8d, r8d; ResultSize
0x18003d505  lea     eax, [rbx+rbx]
0x18003d508  mov     r9, r14; UnicodeString
0x18003d50b  mov     dword ptr [rsp+0F0h+AllocationSize], eax; UnicodeSize
0x18003d50f  lea     rcx, [rbp+57h+OemString]; OemString
0x18003d513  lea     edx, [r8+0Fh]; OemSize
0x18003d517  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x18003d51e  nop     dword ptr [rax+rax+00h]
0x18003d523  mov     ebx, eax
0x18003d525  test    eax, eax
0x18003d527  jns     short loc_18003D532
0x18003d529  lea     rdx, aNlflushnetbios_1; "NlFlushNetbiosCacheName: RtlUpcaseUnico"...
0x18003d530  jmp     short loc_18003D597
0x18003d532  mov     rcx, [rdi+18h]; FileHandle
0x18003d536  lea     rax, [rbp+57h+OemString]
0x18003d53a  mov     dword ptr [rsp+0F0h+EaBuffer], r12d; OutputBufferLength
0x18003d53f  xor     r9d, r9d; ApcContext
0x18003d542  mov     qword ptr [rsp+0F0h+CreateOptions], r12; OutputBuffer
0x18003d547  xor     r8d, r8d; ApcRoutine
0x18003d54a  mov     [rsp+0F0h+CreateDisposition], 10h; InputBufferLength
0x18003d552  xor     edx, edx; Event
0x18003d554  mov     qword ptr [rsp+0F0h+ShareAccess], rax; InputBuffer
0x18003d559  lea     rax, [rbp+57h+IoStatusBlock]
0x18003d55d  mov     [rsp+0F0h+FileAttributes], 2180E0h; IoControlCode
0x18003d565  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x18003d56a  mov     [rbp+57h+OemString+0Fh], r15b
0x18003d56e  call    cs:__imp_NtDeviceIoControlFile
0x18003d575  nop     dword ptr [rax+rax+00h]
0x18003d57a  mov     ebx, eax
0x18003d57c  mov     eax, 80000000h
0x18003d581  lea     ecx, [rbx+rax]
0x18003d584  test    eax, ecx
0x18003d586  jnz     short loc_18003D5A4
0x18003d588  cmp     ebx, 0C000008Bh
0x18003d58e  jz      short loc_18003D5A4
0x18003d590  lea     rdx, aNlflushnetbios; "NlFlushNetbiosCacheName: NtDeviceIoCont"...
0x18003d597  mov     r8d, ebx
0x18003d59a  mov     ecx, 100h; unsigned int
0x18003d59f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003d5a4  mov     eax, ebx
0x18003d5a6  mov     rcx, [rbp+57h+var_28]
0x18003d5aa  xor     rcx, rsp; StackCookie
0x18003d5ad  call    __security_check_cookie
0x18003d5b2  lea     r11, [rsp+0F0h+var_20]
0x18003d5ba  mov     rbx, [r11+38h]
0x18003d5be  mov     rsi, [r11+48h]
0x18003d5c2  mov     rsp, r11
0x18003d5c5  pop     r15
0x18003d5c7  pop     r14
0x18003d5c9  pop     r12
0x18003d5cb  pop     rdi
0x18003d5cc  pop     rbp
0x18003d5cd  retn
```
