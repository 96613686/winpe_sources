# RtlFileMapMapView

- ea: `0x18006db9c`
- end: `0x18006dd65`
- name: `RtlFileMapMapView`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006d524`
- `0x18006d5dc`
- `0x18006e92c`
- `0x18006feb0`

## callees

- `0x180005e40`
- `0x18006db9c`

## import_xrefs

- `ntdll!ZwMapViewOfSection` at `0x18006dcd5`
- `ntdll!ZwMapViewOfSection` at `0x18006dcd5`
- `ntdll!ZwUnmapViewOfSection` at `0x18006dd45`
- `ntdll!ZwUnmapViewOfSection` at `0x18006dd45`
- `ntdll!ZwCreateSection` at `0x18006dc83`
- `ntdll!ZwCreateSection` at `0x18006dc83`
- `ntdll!ZwQueryInformationFile` at `0x18006dc16`
- `ntdll!ZwQueryInformationFile` at `0x18006dc16`
- `ntdll!ZwClose` at `0x18006dd32`
- `ntdll!ZwClose` at `0x18006dd32`

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
0x18006db9c  push    rbp
0x18006db9e  push    rbx
0x18006db9f  push    rsi
0x18006dba0  push    rdi
0x18006dba1  lea     rbp, [rsp-3Fh]
0x18006dba6  sub     rsp, 0D8h
0x18006dbad  mov     rax, cs:__security_cookie
0x18006dbb4  xor     rax, rsp
0x18006dbb7  mov     [rbp+57h+var_30], rax
0x18006dbbb  xor     eax, eax
0x18006dbbd  xorps   xmm0, xmm0
0x18006dbc0  xorps   xmm1, xmm1
0x18006dbc3  mov     sil, dl
0x18006dbc6  mov     rdi, rcx
0x18006dbc9  mov     [rbp+57h+var_38], rax
0x18006dbcd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006dbd1  mov     [rbp+57h+SectionHandle], rax
0x18006dbd5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006dbd9  mov     [rbp+57h+BaseAddress], rax
0x18006dbdd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006dbe1  mov     [rbp+57h+ViewSize], rax
0x18006dbe5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18006dbe9  movups  [rbp+57h+FileInformation], xmm1
0x18006dbed  cmp     [rcx+18h], rax
0x18006dbf1  jz      short loc_18006DBFD
0x18006dbf3  mov     ebx, 0C000010Eh
0x18006dbf8  jmp     loc_18006DD4B
0x18006dbfd  mov     rcx, [rcx]; FileHandle
0x18006dc00  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18006dc04  mov     r9d, 18h; Length
0x18006dc0a  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x18006dc12  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006dc16  call    cs:__imp_ZwQueryInformationFile
0x18006dc1c  mov     ebx, eax
0x18006dc1e  test    eax, eax
0x18006dc20  js      loc_18006DD25
0x18006dc26  mov     al, sil
0x18006dc29  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006dc30  neg     al
0x18006dc32  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18006dc3a  mov     rax, [rdi]
0x18006dc3d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006dc41  sbb     ecx, ecx
0x18006dc43  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x18006dc48  and     ecx, 9000000h
0x18006dc4e  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18006dc55  add     ecx, 8000000h
0x18006dc5b  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18006dc63  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x18006dc67  xorps   xmm0, xmm0
0x18006dc6a  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18006dc6e  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x18006dc76  xor     r9d, r9d; MaximumSize
0x18006dc79  mov     edx, 0F0005h; DesiredAccess
0x18006dc7e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006dc83  call    cs:__imp_ZwCreateSection
0x18006dc89  mov     ebx, eax
0x18006dc8b  test    eax, eax
0x18006dc8d  js      loc_18006DD25
0x18006dc93  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18006dc97  lea     rax, [rbp+57h+ViewSize]
0x18006dc9b  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x18006dca3  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x18006dca7  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x18006dcaf  xor     r9d, r9d; ZeroBits
0x18006dcb2  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x18006dcba  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006dcbe  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x18006dcc3  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x18006dccc  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x18006dcd5  call    cs:__imp_ZwMapViewOfSection
0x18006dcdb  mov     ebx, eax
0x18006dcdd  test    eax, eax
0x18006dcdf  js      short loc_18006DD25
0x18006dce1  mov     rax, [rbp+57h+SectionHandle]
0x18006dce5  test    sil, sil
0x18006dce8  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x18006dcec  mov     [rdi+8], rax
0x18006dcf0  mov     rax, [rbp+57h+BaseAddress]
0x18006dcf4  mov     [rdi+18h], rax
0x18006dcf8  mov     rax, rcx
0x18006dcfb  cmovnz  rax, [rbp+57h+ViewSize]
0x18006dd00  xor     edx, edx
0x18006dd02  mov     [rdi+10h], rcx
0x18006dd06  xor     ecx, ecx
0x18006dd08  mov     [rbp+57h+SectionHandle], rcx
0x18006dd0c  xor     ebx, ebx
0x18006dd0e  mov     [rbp+57h+BaseAddress], rdx
0x18006dd12  mov     [rdi+2Ch], cl
0x18006dd15  mov     word ptr [rdi+29h], 101h
0x18006dd1b  mov     [rdi+20h], rax
0x18006dd1f  mov     [rdi+2Bh], sil
0x18006dd23  jmp     short loc_18006DD2D
0x18006dd25  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x18006dd29  mov     rdx, [rbp+57h+BaseAddress]
0x18006dd2d  test    rcx, rcx
0x18006dd30  jz      short loc_18006DD3C
0x18006dd32  call    cs:__imp_ZwClose
0x18006dd38  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x18006dd3c  test    rdx, rdx
0x18006dd3f  jz      short loc_18006DD4B
0x18006dd41  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006dd45  call    cs:__imp_ZwUnmapViewOfSection
0x18006dd4b  mov     eax, ebx
0x18006dd4d  mov     rcx, [rbp+57h+var_30]
0x18006dd51  xor     rcx, rsp; StackCookie
0x18006dd54  call    __security_check_cookie
0x18006dd59  add     rsp, 0D8h
0x18006dd60  pop     rdi
0x18006dd61  pop     rsi
0x18006dd62  pop     rbx
0x18006dd63  pop     rbp
0x18006dd64  retn
```
