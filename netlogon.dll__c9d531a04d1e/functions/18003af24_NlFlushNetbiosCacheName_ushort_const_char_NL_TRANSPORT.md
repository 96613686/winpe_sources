# NlFlushNetbiosCacheName(ushort const *,char,_NL_TRANSPORT *)

- ea: `0x18003af24`
- end: `0x18003b11c`
- name: `?NlFlushNetbiosCacheName@@YAJPEBGDPEAU_NL_TRANSPORT@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(PCWCH UnicodeString, CHAR, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003a5bc`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18003af24`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18003affd`
- `ntdll!NtCreateFile` at `0x18003affd`
- `ntdll!NtDeviceIoControlFile` at `0x18003b0c2`
- `ntdll!NtDeviceIoControlFile` at `0x18003b0c2`
- `ntdll!RtlLeaveCriticalSection` at `0x18003b010`
- `ntdll!RtlLeaveCriticalSection` at `0x18003b040`
- `ntdll!RtlLeaveCriticalSection` at `0x18003b010`
- `ntdll!RtlLeaveCriticalSection` at `0x18003b040`
- `ntdll!RtlEnterCriticalSection` at `0x18003af67`
- `ntdll!RtlEnterCriticalSection` at `0x18003af67`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18003b071`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18003b071`
- `ntdll!RtlInitUnicodeString` at `0x18003af9d`
- `ntdll!RtlInitUnicodeString` at `0x18003af9d`

## string_xrefs

- `0x18003b019`: `NlFlushNetbiosCacheName: NtCreateFile failed 0x%lx\n`
- `0x18003b07d`: `NlFlushNetbiosCacheName: RtlUpcaseUnicodeToOemN failed 0x%lx\n`
- `0x18003b0de`: `NlFlushNetbiosCacheName: NtDeviceIoControlFile failed 0x%lx\n`

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
0x18003af24  mov     [rsp-8+arg_8], rbx
0x18003af29  mov     [rsp-8+arg_18], rsi
0x18003af2e  push    rbp
0x18003af2f  push    rdi
0x18003af30  push    r12
0x18003af32  push    r14
0x18003af34  push    r15
0x18003af36  lea     rbp, [rsp-37h]
0x18003af3b  sub     rsp, 0D0h
0x18003af42  mov     rax, cs:__security_cookie
0x18003af49  xor     rax, rsp
0x18003af4c  mov     [rbp+57h+var_28], rax
0x18003af50  mov     r14, rcx
0x18003af53  xorps   xmm0, xmm0
0x18003af56  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18003af5d  mov     rdi, r8
0x18003af60  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18003af64  mov     r15b, dl
0x18003af67  call    cs:__imp_RtlEnterCriticalSection
0x18003af6d  xor     r12d, r12d
0x18003af70  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003af74  cmp     [rdi+18h], rbx
0x18003af78  jnz     loc_18003B039
0x18003af7e  xorps   xmm0, xmm0
0x18003af81  mov     [rbp+57h+FileHandle], r12
0x18003af85  lea     rdx, [rdi+20h]; SourceString
0x18003af89  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003af8d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003af91  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003af95  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003af99  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003af9d  call    cs:__imp_RtlInitUnicodeString
0x18003afa3  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x18003afa8  lea     rax, [rbp+57h+DestinationString]
0x18003afac  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x18003afb1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18003afb5  mov     [rsp+0F0h+CreateOptions], r12d; CreateOptions
0x18003afba  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003afbe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003afc2  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003afc6  lea     eax, [rbx+4]
0x18003afc9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003afd0  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x18003afd4  xorps   xmm0, xmm0
0x18003afd7  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x18003afdb  mov     edx, 2000000h; DesiredAccess
0x18003afe0  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x18003afe8  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x18003afed  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18003aff1  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18003aff8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003affd  call    cs:__imp_NtCreateFile
0x18003b003  mov     esi, eax
0x18003b005  test    eax, eax
0x18003b007  jns     short loc_18003B031
0x18003b009  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18003b010  call    cs:__imp_RtlLeaveCriticalSection
0x18003b016  mov     r8d, esi
0x18003b019  lea     rdx, aNlflushnetbios_0; "NlFlushNetbiosCacheName: NtCreateFile f"...
0x18003b020  mov     ecx, 100h; unsigned int
0x18003b025  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003b02a  mov     eax, esi
0x18003b02c  jmp     loc_18003B0F4
0x18003b031  mov     rax, [rbp+57h+FileHandle]
0x18003b035  mov     [rdi+18h], rax
0x18003b039  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18003b040  call    cs:__imp_RtlLeaveCriticalSection
0x18003b046  movdqa  xmm0, cs:__xmm@20202020202020202020202020202020
0x18003b04e  movups  xmmword ptr [rbp+57h+OemString], xmm0
0x18003b052  inc     rbx
0x18003b055  cmp     [r14+rbx*2], r12w
0x18003b05a  jnz     short loc_18003B052
0x18003b05c  xor     r8d, r8d; ResultSize
0x18003b05f  lea     eax, [rbx+rbx]
0x18003b062  mov     r9, r14; UnicodeString
0x18003b065  mov     dword ptr [rsp+0F0h+AllocationSize], eax; UnicodeSize
0x18003b069  lea     rcx, [rbp+57h+OemString]; OemString
0x18003b06d  lea     edx, [r8+0Fh]; OemSize
0x18003b071  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x18003b077  mov     ebx, eax
0x18003b079  test    eax, eax
0x18003b07b  jns     short loc_18003B086
0x18003b07d  lea     rdx, aNlflushnetbios_1; "NlFlushNetbiosCacheName: RtlUpcaseUnico"...
0x18003b084  jmp     short loc_18003B0E5
0x18003b086  mov     rcx, [rdi+18h]; FileHandle
0x18003b08a  lea     rax, [rbp+57h+OemString]
0x18003b08e  mov     dword ptr [rsp+0F0h+EaBuffer], r12d; OutputBufferLength
0x18003b093  xor     r9d, r9d; ApcContext
0x18003b096  mov     qword ptr [rsp+0F0h+CreateOptions], r12; OutputBuffer
0x18003b09b  xor     r8d, r8d; ApcRoutine
0x18003b09e  mov     [rsp+0F0h+CreateDisposition], 10h; InputBufferLength
0x18003b0a6  xor     edx, edx; Event
0x18003b0a8  mov     qword ptr [rsp+0F0h+ShareAccess], rax; InputBuffer
0x18003b0ad  lea     rax, [rbp+57h+IoStatusBlock]
0x18003b0b1  mov     [rsp+0F0h+FileAttributes], 2180E0h; IoControlCode
0x18003b0b9  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x18003b0be  mov     [rbp+57h+OemString+0Fh], r15b
0x18003b0c2  call    cs:__imp_NtDeviceIoControlFile
0x18003b0c8  mov     ebx, eax
0x18003b0ca  mov     eax, 80000000h
0x18003b0cf  lea     ecx, [rbx+rax]
0x18003b0d2  test    eax, ecx
0x18003b0d4  jnz     short loc_18003B0F2
0x18003b0d6  cmp     ebx, 0C000008Bh
0x18003b0dc  jz      short loc_18003B0F2
0x18003b0de  lea     rdx, aNlflushnetbios; "NlFlushNetbiosCacheName: NtDeviceIoCont"...
0x18003b0e5  mov     r8d, ebx
0x18003b0e8  mov     ecx, 100h; unsigned int
0x18003b0ed  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003b0f2  mov     eax, ebx
0x18003b0f4  mov     rcx, [rbp+57h+var_28]
0x18003b0f8  xor     rcx, rsp; StackCookie
0x18003b0fb  call    __security_check_cookie
0x18003b100  lea     r11, [rsp+0F0h+var_20]
0x18003b108  mov     rbx, [r11+38h]
0x18003b10c  mov     rsi, [r11+48h]
0x18003b110  mov     rsp, r11
0x18003b113  pop     r15
0x18003b115  pop     r14
0x18003b117  pop     r12
0x18003b119  pop     rdi
0x18003b11a  pop     rbp
0x18003b11b  retn
```
