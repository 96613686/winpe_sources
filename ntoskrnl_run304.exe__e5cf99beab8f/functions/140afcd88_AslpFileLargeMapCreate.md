# AslpFileLargeMapCreate

- ea: `0x140afcd88`
- end: `0x140afcfed`
- name: `AslpFileLargeMapCreate`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140735778`

## callees

- `0x1406dad90`
- `0x1406db1d0`
- `0x140733ed4`
- `0x140979890`
- `0x14097d158`
- `0x140a49790`
- `0x140afcd88`

## string_xrefs

- `0x140afce30`: `ZwCreateSection failed [%x]`
- `0x140afce3d`: `AslpFileLargeMapCreate`
- `0x140afcee8`: `AslpFileLargeMapCreate`

## pseudocode

```c
__int64 __fastcall AslpFileLargeMapCreate(__int64 *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  unsigned int v6; // edi
  NTSTATUS v7; // eax
  const char *v8; // r9
  int v9; // r8d
  HANDLE v10; // rax
  unsigned __int64 v11; // rsi
  HANDLE v12; // rax
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-49h]
  HANDLE FileHandle; // [rsp+30h] [rbp-39h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int64 v17; // [rsp+E0h] [rbp+77h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = AslAlloc(a1, 80);
  v17 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = -1073741801;
    goto LABEL_20;
  }
  ObjectAttributes.Length = 48;
  FileHandle = *(HANDLE *)a2;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwCreateSection((PHANDLE)(v4 + 8), 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwCreateSection failed [%x]";
    v9 = 346;
LABEL_5:
    SectionPageProtection[0] = v7;
    AslLogCallPrintf(1, (unsigned int)"AslpFileLargeMapCreate", v9, (_DWORD)v8, *(_QWORD *)SectionPageProtection);
    goto LABEL_20;
  }
  *(_QWORD *)(v5 + 64) = *(_QWORD *)(a2 + 16) - 4096LL - (unsigned __int16)(*(_QWORD *)(a2 + 16) - 4096);
  v7 = ZwMapViewOfSection(
         *(HANDLE *)(v5 + 8),
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (PVOID *)(v5 + 48),
         0,
         0,
         (PLARGE_INTEGER)(v5 + 64),
         (PSIZE_T)(v5 + 56),
         ViewUnmap,
         0x500000u,
         2u);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the end of the file [%x]";
    v9 = 374;
    goto LABEL_5;
  }
  v10 = MmSecureVirtualMemory(*(PVOID *)(v5 + 48), *(_QWORD *)(v5 + 56), 2u);
  *(_QWORD *)(v5 + 72) = v10;
  if ( !v10 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileLargeMapCreate",
      381,
      (unsigned int)"MmSecureVirtualMemory failed to secure the end view");
LABEL_10:
    v6 = -1073741823;
    goto LABEL_20;
  }
  v11 = *(_QWORD *)(a2 + 16);
  if ( v11 > 0x20000000 )
    v11 = 0x20000000;
  do
  {
    *(_QWORD *)(v5 + 24) = v11;
    *(_QWORD *)(v5 + 32) = 0;
    v7 = ZwMapViewOfSection(
           *(HANDLE *)(v5 + 8),
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (PVOID *)(v5 + 16),
           0,
           0,
           (PLARGE_INTEGER)(v5 + 32),
           (PSIZE_T)(v5 + 24),
           ViewUnmap,
           0x500000u,
           2u);
    v6 = v7;
    if ( v7 != -1073741801 )
      break;
    v11 >>= 1;
  }
  while ( v11 >= 0x100000 );
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v9 = 416;
    goto LABEL_5;
  }
  v12 = MmSecureVirtualMemory(*(PVOID *)(v5 + 16), *(_QWORD *)(v5 + 24), 2u);
  *(_QWORD *)(v5 + 40) = v12;
  if ( !v12 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileLargeMapCreate",
      423,
      (unsigned int)"MmSecureVirtualMemory failed to secure the start view");
    goto LABEL_10;
  }
  *(_QWORD *)v5 = a2;
  *a1 = v5;
  v5 = 0;
  v17 = 0;
  v6 = 0;
LABEL_20:
  if ( v5 )
    AslpFileLargeMapDelete(&v17);
  return v6;
}

```

## disassembly

```asm
0x140afcd88  push    rbp
0x140afcd8a  push    rbx
0x140afcd8b  push    rsi
0x140afcd8c  push    rdi
0x140afcd8d  push    r12
0x140afcd8f  push    r13
0x140afcd91  push    r14
0x140afcd93  push    r15
0x140afcd95  lea     rbp, [rsp-1Fh]
0x140afcd9a  sub     rsp, 88h
0x140afcda1  xorps   xmm0, xmm0
0x140afcda4  mov     r14, rdx
0x140afcda7  mov     edx, 50h ; 'P'
0x140afcdac  mov     r13, rcx
0x140afcdaf  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140afcdb3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140afcdb7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140afcdbb  call    AslAlloc
0x140afcdc0  mov     [rbp+57h+arg_10], rax
0x140afcdc4  mov     rbx, rax
0x140afcdc7  test    rax, rax
0x140afcdca  jnz     short loc_140AFCDD6
0x140afcdcc  mov     edi, 0C0000017h
0x140afcdd1  jmp     loc_140AFCFC8
0x140afcdd6  lea     rcx, [rax+8]; SectionHandle
0x140afcdda  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140afcde1  mov     rax, [r14]
0x140afcde4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140afcde8  mov     [rsp+0C0h+FileHandle], rax; FileHandle
0x140afcded  xorps   xmm0, xmm0
0x140afcdf0  mov     esi, 2
0x140afcdf5  mov     [rsp+0C0h+AllocationAttributes], 8000000h; AllocationAttributes
0x140afcdfd  xor     r9d, r9d; MaximumSize
0x140afce00  mov     [rsp+0C0h+SectionPageProtection], esi; SectionPageProtection
0x140afce04  mov     edx, 0F0005h; DesiredAccess
0x140afce09  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140afce11  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140afce18  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140afce20  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140afce25  call    ZwCreateSection
0x140afce2a  mov     edi, eax
0x140afce2c  test    eax, eax
0x140afce2e  jns     short loc_140AFCE57
0x140afce30  lea     r9, aZwcreatesectio_0; "ZwCreateSection failed [%x]"
0x140afce37  mov     r8d, 15Ah
0x140afce3d  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140afce44  mov     [rsp+0C0h+SectionPageProtection], eax
0x140afce48  mov     ecx, 1
0x140afce4d  call    AslLogCallPrintf
0x140afce52  jmp     loc_140AFCFC8
0x140afce57  mov     rcx, [r14+10h]
0x140afce5b  lea     rdx, [rbx+40h]
0x140afce5f  mov     [rsp+0C0h+Win32Protect], esi; Win32Protect
0x140afce63  lea     r8, [rbx+30h]; BaseAddress
0x140afce67  add     rcx, 0FFFFFFFFFFFFF000h
0x140afce6e  mov     [rsp+0C0h+AllocationType], 500000h; AllocationType
0x140afce76  movzx   eax, cx
0x140afce79  xor     r9d, r9d; ZeroBits
0x140afce7c  sub     rcx, rax
0x140afce7f  mov     [rsp+0C0h+InheritDisposition], esi; InheritDisposition
0x140afce83  mov     [rdx], rcx
0x140afce86  lea     rax, [rbx+38h]
0x140afce8a  mov     rcx, [rbx+8]; SectionHandle
0x140afce8e  mov     [rsp+0C0h+FileHandle], rax; ViewSize
0x140afce93  mov     qword ptr [rsp+0C0h+AllocationAttributes], rdx; SectionOffset
0x140afce98  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140afce9c  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; CommitSize
0x140afcea5  call    ZwMapViewOfSection
0x140afceaa  mov     edi, eax
0x140afceac  test    eax, eax
0x140afceae  jns     short loc_140AFCEC2
0x140afceb0  lea     r9, aZwmapviewofsec_2; "ZwMapViewOfSection failed to map the en"...
0x140afceb7  mov     r8d, 176h
0x140afcebd  jmp     loc_140AFCE3D
0x140afcec2  mov     rdx, [rbx+38h]; Size
0x140afcec6  mov     r8d, esi; ProbeMode
0x140afcec9  mov     rcx, [rbx+30h]; Address
0x140afcecd  call    MmSecureVirtualMemory
0x140afced2  mov     [rbx+48h], rax
0x140afced6  test    rax, rax
0x140afced9  jnz     short loc_140AFCF03
0x140afcedb  lea     r9, aMmsecurevirtua_0; "MmSecureVirtualMemory failed to secure "...
0x140afcee2  mov     r8d, 17Dh
0x140afcee8  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140afceef  mov     ecx, 1
0x140afcef4  call    AslLogCallPrintf
0x140afcef9  mov     edi, 0C0000001h
0x140afcefe  jmp     loc_140AFCFC8
0x140afcf03  mov     rsi, [r14+10h]
0x140afcf07  mov     eax, 20000000h
0x140afcf0c  cmp     rsi, rax
0x140afcf0f  cmova   rsi, rax
0x140afcf13  mov     ecx, 2
0x140afcf18  lea     rax, [rbx+20h]
0x140afcf1c  mov     [rsp+0C0h+Win32Protect], ecx; Win32Protect
0x140afcf20  lea     r15, [rbx+18h]
0x140afcf24  mov     [rsp+0C0h+AllocationType], 500000h; AllocationType
0x140afcf2c  lea     r8, [rbx+10h]; BaseAddress
0x140afcf30  mov     [rsp+0C0h+InheritDisposition], ecx; InheritDisposition
0x140afcf34  xor     r9d, r9d; ZeroBits
0x140afcf37  mov     [r15], rsi
0x140afcf3a  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140afcf3e  mov     [rsp+0C0h+FileHandle], r15; ViewSize
0x140afcf43  mov     qword ptr [rax], 0
0x140afcf4a  mov     rcx, [rbx+8]; SectionHandle
0x140afcf4e  mov     qword ptr [rsp+0C0h+AllocationAttributes], rax; SectionOffset
0x140afcf53  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; CommitSize
0x140afcf5c  call    ZwMapViewOfSection
0x140afcf61  mov     edi, eax
0x140afcf63  cmp     eax, 0C0000017h
0x140afcf68  jnz     short loc_140AFCF76
0x140afcf6a  shr     rsi, 1
0x140afcf6d  cmp     rsi, 100000h
0x140afcf74  jnb     short loc_140AFCF13
0x140afcf76  test    eax, eax
0x140afcf78  jns     short loc_140AFCF8C
0x140afcf7a  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the st"...
0x140afcf81  mov     r8d, 1A0h
0x140afcf87  jmp     loc_140AFCE3D
0x140afcf8c  mov     rdx, [r15]; Size
0x140afcf8f  mov     r8d, 2; ProbeMode
0x140afcf95  mov     rcx, [rbx+10h]; Address
0x140afcf99  call    MmSecureVirtualMemory
0x140afcf9e  mov     [rbx+28h], rax
0x140afcfa2  test    rax, rax
0x140afcfa5  jnz     short loc_140AFCFB9
0x140afcfa7  lea     r9, aMmsecurevirtua_1; "MmSecureVirtualMemory failed to secure "...
0x140afcfae  mov     r8d, 1A7h
0x140afcfb4  jmp     loc_140AFCEE8
0x140afcfb9  mov     [rbx], r14
0x140afcfbc  mov     [r13+0], rbx
0x140afcfc0  xor     ebx, ebx
0x140afcfc2  mov     [rbp+57h+arg_10], rbx
0x140afcfc6  xor     edi, edi
0x140afcfc8  test    rbx, rbx
0x140afcfcb  jz      short loc_140AFCFD6
0x140afcfcd  lea     rcx, [rbp+57h+arg_10]
0x140afcfd1  call    AslpFileLargeMapDelete
0x140afcfd6  mov     eax, edi
0x140afcfd8  add     rsp, 88h
0x140afcfdf  pop     r15
0x140afcfe1  pop     r14
0x140afcfe3  pop     r13
0x140afcfe5  pop     r12
0x140afcfe7  pop     rdi
0x140afcfe8  pop     rsi
0x140afcfe9  pop     rbx
0x140afcfea  pop     rbp
0x140afcfeb  retn
```
