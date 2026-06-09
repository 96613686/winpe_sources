# RtlFileMapMapView

- ea: `0x180013814`
- end: `0x1800139dd`
- name: `RtlFileMapMapView`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000dcf4`
- `0x18000ddac`
- `0x18000f980`
- `0x180010f04`

## callees

- `0x180013814`
- `0x1800191f0`

## import_xrefs

- `ntdll!ZwClose` at `0x1800139aa`
- `ntdll!ZwClose` at `0x1800139aa`
- `ntdll!ZwQueryInformationFile` at `0x18001388e`
- `ntdll!ZwQueryInformationFile` at `0x18001388e`
- `ntdll!ZwMapViewOfSection` at `0x18001394d`
- `ntdll!ZwMapViewOfSection` at `0x18001394d`
- `ntdll!ZwCreateSection` at `0x1800138fb`
- `ntdll!ZwCreateSection` at `0x1800138fb`
- `ntdll!ZwUnmapViewOfSection` at `0x1800139bd`
- `ntdll!ZwUnmapViewOfSection` at `0x1800139bd`

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
0x180013814  push    rbp
0x180013816  push    rbx
0x180013817  push    rsi
0x180013818  push    rdi
0x180013819  lea     rbp, [rsp-3Fh]
0x18001381e  sub     rsp, 0D8h
0x180013825  mov     rax, cs:__security_cookie
0x18001382c  xor     rax, rsp
0x18001382f  mov     [rbp+57h+var_30], rax
0x180013833  xor     eax, eax
0x180013835  xorps   xmm0, xmm0
0x180013838  xorps   xmm1, xmm1
0x18001383b  mov     sil, dl
0x18001383e  mov     rdi, rcx
0x180013841  mov     [rbp+57h+var_38], rax
0x180013845  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180013849  mov     [rbp+57h+SectionHandle], rax
0x18001384d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180013851  mov     [rbp+57h+BaseAddress], rax
0x180013855  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013859  mov     [rbp+57h+ViewSize], rax
0x18001385d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180013861  movups  [rbp+57h+FileInformation], xmm1
0x180013865  cmp     [rcx+18h], rax
0x180013869  jz      short loc_180013875
0x18001386b  mov     ebx, 0C000010Eh
0x180013870  jmp     loc_1800139C3
0x180013875  mov     rcx, [rcx]; FileHandle
0x180013878  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18001387c  mov     r9d, 18h; Length
0x180013882  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x18001388a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001388e  call    cs:__imp_ZwQueryInformationFile
0x180013894  mov     ebx, eax
0x180013896  test    eax, eax
0x180013898  js      loc_18001399D
0x18001389e  mov     al, sil
0x1800138a1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800138a8  neg     al
0x1800138aa  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800138b2  mov     rax, [rdi]
0x1800138b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800138b9  sbb     ecx, ecx
0x1800138bb  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x1800138c0  and     ecx, 9000000h
0x1800138c6  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800138cd  add     ecx, 8000000h
0x1800138d3  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800138db  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x1800138df  xorps   xmm0, xmm0
0x1800138e2  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800138e6  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x1800138ee  xor     r9d, r9d; MaximumSize
0x1800138f1  mov     edx, 0F0005h; DesiredAccess
0x1800138f6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800138fb  call    cs:__imp_ZwCreateSection
0x180013901  mov     ebx, eax
0x180013903  test    eax, eax
0x180013905  js      loc_18001399D
0x18001390b  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18001390f  lea     rax, [rbp+57h+ViewSize]
0x180013913  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x18001391b  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x18001391f  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x180013927  xor     r9d, r9d; ZeroBits
0x18001392a  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x180013932  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180013936  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x18001393b  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x180013944  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x18001394d  call    cs:__imp_ZwMapViewOfSection
0x180013953  mov     ebx, eax
0x180013955  test    eax, eax
0x180013957  js      short loc_18001399D
0x180013959  mov     rax, [rbp+57h+SectionHandle]
0x18001395d  test    sil, sil
0x180013960  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x180013964  mov     [rdi+8], rax
0x180013968  mov     rax, [rbp+57h+BaseAddress]
0x18001396c  mov     [rdi+18h], rax
0x180013970  mov     rax, rcx
0x180013973  cmovnz  rax, [rbp+57h+ViewSize]
0x180013978  xor     edx, edx
0x18001397a  mov     [rdi+10h], rcx
0x18001397e  xor     ecx, ecx
0x180013980  mov     [rbp+57h+SectionHandle], rcx
0x180013984  xor     ebx, ebx
0x180013986  mov     [rbp+57h+BaseAddress], rdx
0x18001398a  mov     [rdi+2Ch], cl
0x18001398d  mov     word ptr [rdi+29h], 101h
0x180013993  mov     [rdi+20h], rax
0x180013997  mov     [rdi+2Bh], sil
0x18001399b  jmp     short loc_1800139A5
0x18001399d  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x1800139a1  mov     rdx, [rbp+57h+BaseAddress]
0x1800139a5  test    rcx, rcx
0x1800139a8  jz      short loc_1800139B4
0x1800139aa  call    cs:__imp_ZwClose
0x1800139b0  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x1800139b4  test    rdx, rdx
0x1800139b7  jz      short loc_1800139C3
0x1800139b9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800139bd  call    cs:__imp_ZwUnmapViewOfSection
0x1800139c3  mov     eax, ebx
0x1800139c5  mov     rcx, [rbp+57h+var_30]
0x1800139c9  xor     rcx, rsp; StackCookie
0x1800139cc  call    __security_check_cookie
0x1800139d1  add     rsp, 0D8h
0x1800139d8  pop     rdi
0x1800139d9  pop     rsi
0x1800139da  pop     rbx
0x1800139db  pop     rbp
0x1800139dc  retn
```
