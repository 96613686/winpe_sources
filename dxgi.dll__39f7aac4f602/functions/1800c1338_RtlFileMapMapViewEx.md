# RtlFileMapMapViewEx

- ea: `0x1800c1338`
- end: `0x1800c1501`
- name: `RtlFileMapMapViewEx`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006cf6c`
- `0x1800c0e28`
- `0x1800c1d88`
- `0x1800c2fec`

## callees

- `0x180075fa0`
- `0x1800c1338`

## import_xrefs

- `ntdll!ZwClose` at `0x1800c14ce`
- `ntdll!ZwClose` at `0x1800c14ce`
- `ntdll!ZwQueryInformationFile` at `0x1800c13b2`
- `ntdll!ZwQueryInformationFile` at `0x1800c13b2`
- `ntdll!ZwCreateSection` at `0x1800c141f`
- `ntdll!ZwCreateSection` at `0x1800c141f`
- `ntdll!ZwUnmapViewOfSection` at `0x1800c14e1`
- `ntdll!ZwUnmapViewOfSection` at `0x1800c14e1`
- `ntdll!ZwMapViewOfSection` at `0x1800c1471`
- `ntdll!ZwMapViewOfSection` at `0x1800c1471`

## pseudocode

```c
__int64 __fastcall RtlFileMapMapViewEx(__int64 a1, char a2)
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
0x1800c1338  push    rbp
0x1800c133a  push    rbx
0x1800c133b  push    rsi
0x1800c133c  push    rdi
0x1800c133d  lea     rbp, [rsp-3Fh]
0x1800c1342  sub     rsp, 0D8h
0x1800c1349  mov     rax, cs:__security_cookie
0x1800c1350  xor     rax, rsp
0x1800c1353  mov     [rbp+57h+var_30], rax
0x1800c1357  xor     eax, eax
0x1800c1359  xorps   xmm0, xmm0
0x1800c135c  xorps   xmm1, xmm1
0x1800c135f  mov     sil, dl
0x1800c1362  mov     rdi, rcx
0x1800c1365  mov     [rbp+57h+var_38], rax
0x1800c1369  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800c136d  mov     [rbp+57h+SectionHandle], rax
0x1800c1371  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800c1375  mov     [rbp+57h+BaseAddress], rax
0x1800c1379  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c137d  mov     [rbp+57h+ViewSize], rax
0x1800c1381  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800c1385  movups  [rbp+57h+FileInformation], xmm1
0x1800c1389  cmp     [rcx+18h], rax
0x1800c138d  jz      short loc_1800C1399
0x1800c138f  mov     ebx, 0C000010Eh
0x1800c1394  jmp     loc_1800C14E7
0x1800c1399  mov     rcx, [rcx]; FileHandle
0x1800c139c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800c13a0  mov     r9d, 18h; Length
0x1800c13a6  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x1800c13ae  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800c13b2  call    cs:__imp_ZwQueryInformationFile
0x1800c13b8  mov     ebx, eax
0x1800c13ba  test    eax, eax
0x1800c13bc  js      loc_1800C14C1
0x1800c13c2  mov     al, sil
0x1800c13c5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800c13cc  neg     al
0x1800c13ce  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800c13d6  mov     rax, [rdi]
0x1800c13d9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800c13dd  sbb     ecx, ecx
0x1800c13df  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x1800c13e4  and     ecx, 9000000h
0x1800c13ea  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800c13f1  add     ecx, 8000000h
0x1800c13f7  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800c13ff  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x1800c1403  xorps   xmm0, xmm0
0x1800c1406  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800c140a  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x1800c1412  xor     r9d, r9d; MaximumSize
0x1800c1415  mov     edx, 0F0005h; DesiredAccess
0x1800c141a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c141f  call    cs:__imp_ZwCreateSection
0x1800c1425  mov     ebx, eax
0x1800c1427  test    eax, eax
0x1800c1429  js      loc_1800C14C1
0x1800c142f  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800c1433  lea     rax, [rbp+57h+ViewSize]
0x1800c1437  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x1800c143f  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x1800c1443  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x1800c144b  xor     r9d, r9d; ZeroBits
0x1800c144e  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x1800c1456  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800c145a  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x1800c145f  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x1800c1468  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x1800c1471  call    cs:__imp_ZwMapViewOfSection
0x1800c1477  mov     ebx, eax
0x1800c1479  test    eax, eax
0x1800c147b  js      short loc_1800C14C1
0x1800c147d  mov     rax, [rbp+57h+SectionHandle]
0x1800c1481  test    sil, sil
0x1800c1484  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x1800c1488  mov     [rdi+8], rax
0x1800c148c  mov     rax, [rbp+57h+BaseAddress]
0x1800c1490  mov     [rdi+18h], rax
0x1800c1494  mov     rax, rcx
0x1800c1497  cmovnz  rax, [rbp+57h+ViewSize]
0x1800c149c  xor     edx, edx
0x1800c149e  mov     [rdi+10h], rcx
0x1800c14a2  xor     ecx, ecx
0x1800c14a4  mov     [rbp+57h+SectionHandle], rcx
0x1800c14a8  xor     ebx, ebx
0x1800c14aa  mov     [rbp+57h+BaseAddress], rdx
0x1800c14ae  mov     [rdi+2Ch], cl
0x1800c14b1  mov     word ptr [rdi+29h], 101h
0x1800c14b7  mov     [rdi+20h], rax
0x1800c14bb  mov     [rdi+2Bh], sil
0x1800c14bf  jmp     short loc_1800C14C9
0x1800c14c1  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x1800c14c5  mov     rdx, [rbp+57h+BaseAddress]
0x1800c14c9  test    rcx, rcx
0x1800c14cc  jz      short loc_1800C14D8
0x1800c14ce  call    cs:__imp_ZwClose
0x1800c14d4  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x1800c14d8  test    rdx, rdx
0x1800c14db  jz      short loc_1800C14E7
0x1800c14dd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800c14e1  call    cs:__imp_ZwUnmapViewOfSection
0x1800c14e7  mov     eax, ebx
0x1800c14e9  mov     rcx, [rbp+57h+var_30]
0x1800c14ed  xor     rcx, rsp; StackCookie
0x1800c14f0  call    __security_check_cookie
0x1800c14f5  add     rsp, 0D8h
0x1800c14fc  pop     rdi
0x1800c14fd  pop     rsi
0x1800c14fe  pop     rbx
0x1800c14ff  pop     rbp
0x1800c1500  retn
```
