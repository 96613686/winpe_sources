# RtlFileMapMapView

- ea: `0x18001a768`
- end: `0x18001a931`
- name: `RtlFileMapMapView`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a0f0`
- `0x18001a1a8`
- `0x18001b104`
- `0x18001c688`

## callees

- `0x180002bf0`
- `0x18001a768`

## import_xrefs

- `ntdll!ZwQueryInformationFile` at `0x18001a7e2`
- `ntdll!ZwQueryInformationFile` at `0x18001a7e2`
- `ntdll!ZwCreateSection` at `0x18001a84f`
- `ntdll!ZwCreateSection` at `0x18001a84f`
- `ntdll!ZwClose` at `0x18001a8fe`
- `ntdll!ZwClose` at `0x18001a8fe`
- `ntdll!ZwUnmapViewOfSection` at `0x18001a911`
- `ntdll!ZwUnmapViewOfSection` at `0x18001a911`
- `ntdll!ZwMapViewOfSection` at `0x18001a8a1`
- `ntdll!ZwMapViewOfSection` at `0x18001a8a1`

## pseudocode

```c
__int64 __fastcall RtlFileMapMapView(__int64 a1, char a2)
{
  NTSTATUS v4; // ebx
  ULONG_PTR v5; // rcx
  ULONG_PTR v6; // rax
  PVOID v7; // rdx
  void *v8; // rcx
  HANDLE FileHandle; // [rsp+30h] [rbp-69h]
  void *SectionHandle; // [rsp+50h] [rbp-49h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-41h] BYREF
  ULONG_PTR ViewSize; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-1h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+B8h] [rbp+1Fh]

  v17 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SectionHandle = 0;
  BaseAddress = 0;
  ViewSize = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    return (unsigned int)-1073741554;
  }
  else
  {
    v4 = ZwQueryInformationFile(*(HANDLE *)a1, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v4 < 0
      || (ObjectAttributes.Length = 48,
          memset(&ObjectAttributes.RootDirectory, 0, 20),
          FileHandle = *(HANDLE *)a1,
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
          v4 = ZwCreateSection(
                 &SectionHandle,
                 0xF0005u,
                 &ObjectAttributes,
                 0,
                 2u,
                 a2 != 0 ? 285212672 : 0x8000000,
                 FileHandle),
          v4 < 0)
      || (v4 = ZwMapViewOfSection(
                 SectionHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &BaseAddress,
                 0,
                 0,
                 0,
                 &ViewSize,
                 ViewUnmap,
                 0x500000u,
                 2u),
          v4 < 0) )
    {
      v8 = SectionHandle;
      v7 = BaseAddress;
    }
    else
    {
      v5 = *((_QWORD *)&FileInformation + 1);
      *(_QWORD *)(a1 + 8) = SectionHandle;
      *(_QWORD *)(a1 + 24) = BaseAddress;
      v6 = v5;
      if ( a2 )
        v6 = ViewSize;
      v7 = 0;
      *(_QWORD *)(a1 + 16) = v5;
      v8 = 0;
      SectionHandle = 0;
      v4 = 0;
      BaseAddress = 0;
      *(_BYTE *)(a1 + 44) = 0;
      *(_WORD *)(a1 + 41) = 257;
      *(_QWORD *)(a1 + 32) = v6;
      *(_BYTE *)(a1 + 43) = a2;
    }
    if ( v8 )
    {
      ZwClose(v8);
      v7 = BaseAddress;
    }
    if ( v7 )
      ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a768  push    rbp
0x18001a76a  push    rbx
0x18001a76b  push    rsi
0x18001a76c  push    rdi
0x18001a76d  lea     rbp, [rsp-3Fh]
0x18001a772  sub     rsp, 0D8h
0x18001a779  mov     rax, cs:__security_cookie
0x18001a780  xor     rax, rsp
0x18001a783  mov     [rbp+57h+var_30], rax
0x18001a787  xor     eax, eax
0x18001a789  xorps   xmm0, xmm0
0x18001a78c  xorps   xmm1, xmm1
0x18001a78f  mov     sil, dl
0x18001a792  mov     rdi, rcx
0x18001a795  mov     [rbp+57h+var_38], rax
0x18001a799  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001a79d  mov     [rbp+57h+SectionHandle], rax
0x18001a7a1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001a7a5  mov     [rbp+57h+BaseAddress], rax
0x18001a7a9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a7ad  mov     [rbp+57h+ViewSize], rax
0x18001a7b1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001a7b5  movups  [rbp+57h+FileInformation], xmm1
0x18001a7b9  cmp     [rcx+18h], rax
0x18001a7bd  jz      short loc_18001A7C9
0x18001a7bf  mov     ebx, 0C000010Eh
0x18001a7c4  jmp     loc_18001A917
0x18001a7c9  mov     rcx, [rcx]; FileHandle
0x18001a7cc  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18001a7d0  mov     r9d, 18h; Length
0x18001a7d6  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x18001a7de  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001a7e2  call    cs:__imp_ZwQueryInformationFile
0x18001a7e8  mov     ebx, eax
0x18001a7ea  test    eax, eax
0x18001a7ec  js      loc_18001A8F1
0x18001a7f2  mov     al, sil
0x18001a7f5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001a7fc  neg     al
0x18001a7fe  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001a806  mov     rax, [rdi]
0x18001a809  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001a80d  sbb     ecx, ecx
0x18001a80f  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x18001a814  and     ecx, 9000000h
0x18001a81a  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18001a821  add     ecx, 8000000h
0x18001a827  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18001a82f  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x18001a833  xorps   xmm0, xmm0
0x18001a836  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18001a83a  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x18001a842  xor     r9d, r9d; MaximumSize
0x18001a845  mov     edx, 0F0005h; DesiredAccess
0x18001a84a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a84f  call    cs:__imp_ZwCreateSection
0x18001a855  mov     ebx, eax
0x18001a857  test    eax, eax
0x18001a859  js      loc_18001A8F1
0x18001a85f  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18001a863  lea     rax, [rbp+57h+ViewSize]
0x18001a867  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x18001a86f  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x18001a873  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x18001a87b  xor     r9d, r9d; ZeroBits
0x18001a87e  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x18001a886  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001a88a  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x18001a88f  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x18001a898  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x18001a8a1  call    cs:__imp_ZwMapViewOfSection
0x18001a8a7  mov     ebx, eax
0x18001a8a9  test    eax, eax
0x18001a8ab  js      short loc_18001A8F1
0x18001a8ad  mov     rax, [rbp+57h+SectionHandle]
0x18001a8b1  test    sil, sil
0x18001a8b4  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x18001a8b8  mov     [rdi+8], rax
0x18001a8bc  mov     rax, [rbp+57h+BaseAddress]
0x18001a8c0  mov     [rdi+18h], rax
0x18001a8c4  mov     rax, rcx
0x18001a8c7  cmovnz  rax, [rbp+57h+ViewSize]
0x18001a8cc  xor     edx, edx
0x18001a8ce  mov     [rdi+10h], rcx
0x18001a8d2  xor     ecx, ecx
0x18001a8d4  mov     [rbp+57h+SectionHandle], rcx
0x18001a8d8  xor     ebx, ebx
0x18001a8da  mov     [rbp+57h+BaseAddress], rdx
0x18001a8de  mov     [rdi+2Ch], cl
0x18001a8e1  mov     word ptr [rdi+29h], 101h
0x18001a8e7  mov     [rdi+20h], rax
0x18001a8eb  mov     [rdi+2Bh], sil
0x18001a8ef  jmp     short loc_18001A8F9
0x18001a8f1  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x18001a8f5  mov     rdx, [rbp+57h+BaseAddress]
0x18001a8f9  test    rcx, rcx
0x18001a8fc  jz      short loc_18001A908
0x18001a8fe  call    cs:__imp_ZwClose
0x18001a904  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x18001a908  test    rdx, rdx
0x18001a90b  jz      short loc_18001A917
0x18001a90d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001a911  call    cs:__imp_ZwUnmapViewOfSection
0x18001a917  mov     eax, ebx
0x18001a919  mov     rcx, [rbp+57h+var_30]
0x18001a91d  xor     rcx, rsp; StackCookie
0x18001a920  call    __security_check_cookie
0x18001a925  add     rsp, 0D8h
0x18001a92c  pop     rdi
0x18001a92d  pop     rsi
0x18001a92e  pop     rbx
0x18001a92f  pop     rbp
0x18001a930  retn
```
