# CipMapAndSizeDataFileWithMDL

- ea: `0x180059ee4`
- end: `0x18005a1dc`
- name: `CipMapAndSizeDataFileWithMDL`
- size: `760`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID *BaseAddress, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005d550`
- `0x180073244`

## callees

- `0x180059ee4`
- `0x1800a78f8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18005a171`
- `ntoskrnl!ZwClose` at `0x18005a195`
- `ntoskrnl!ZwClose` at `0x18005a171`
- `ntoskrnl!ZwClose` at `0x18005a195`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005a1ba`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005a1ba`
- `ntoskrnl!MmProbeAndLockPages` at `0x18005a0de`
- `ntoskrnl!MmProbeAndLockPages` at `0x18005a0de`
- `ntoskrnl!IoAllocateMdl` at `0x18005a0b5`
- `ntoskrnl!IoAllocateMdl` at `0x18005a0b5`
- `ntoskrnl!ZwCreateSection` at `0x18005a011`
- `ntoskrnl!ZwCreateSection` at `0x18005a011`
- `ntoskrnl!ZwMapViewOfSection` at `0x18005a065`
- `ntoskrnl!ZwMapViewOfSection` at `0x18005a065`
- `ntoskrnl!IoFreeMdl` at `0x18005a14d`
- `ntoskrnl!IoFreeMdl` at `0x18005a14d`

## pseudocode

```c
__int64 __fastcall CipMapAndSizeDataFileWithMDL(
        struct _UNICODE_STRING *a1,
        void *a2,
        __int64 a3,
        HANDLE *a4,
        void **a5,
        PVOID *BaseAddress,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        struct _MDL **a10)
{
  int v11; // eax
  PVOID *v12; // rsi
  NTSTATUS v13; // r14d
  struct _MDL *Mdl; // rax
  struct _MDL *v15; // rdi
  __int128 v17; // [rsp+58h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-60h] BYREF
  void *SectionHandle; // [rsp+D0h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+D8h] [rbp+10h] BYREF
  ULONG_PTR ViewSize; // [rsp+E0h] [rbp+18h] BYREF
  HANDLE *v22; // [rsp+E8h] [rbp+20h]

  v22 = a4;
  v11 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  Handle = 0;
  SectionHandle = 0;
  ViewSize = 0;
  v17 = 0;
  v12 = BaseAddress;
  if ( BaseAddress )
    *BaseAddress = 0;
  if ( a3 )
  {
    LODWORD(v17) = 524296;
    *((_QWORD *)&v17 + 1) = a3;
    a1 = (struct _UNICODE_STRING *)&v17;
    v11 = 0x2000;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 704;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = CipOpenFile((unsigned int)&Handle, a7, a8, a9, (__int64)&ObjectAttributes, v11);
  if ( v13 >= 0 )
  {
    if ( !v12 )
    {
LABEL_15:
      *a4 = Handle;
      *a5 = SectionHandle;
      Handle = 0;
      SectionHandle = 0;
      goto LABEL_16;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, Handle);
    if ( v13 >= 0 )
    {
      v13 = ZwMapViewOfSection(SectionHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL, v12, 0, 0, 0, &ViewSize, ViewShare, 0, 2u);
      if ( v13 >= 0 )
      {
        if ( a10 )
        {
          if ( ViewSize > 0xFFFFEFFF )
          {
            v13 = -1073741760;
            goto LABEL_16;
          }
          Mdl = IoAllocateMdl(*v12, ViewSize, 0, 0, 0);
          v15 = Mdl;
          if ( !Mdl )
          {
            v13 = -1073741670;
            goto LABEL_16;
          }
          MmProbeAndLockPages(Mdl, 0, IoReadAccess);
          *a10 = v15;
        }
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  if ( SectionHandle )
  {
    ZwClose(SectionHandle);
    *a5 = 0;
  }
  if ( Handle )
  {
    ZwClose(Handle);
    *a4 = 0;
  }
  if ( v13 < 0 && v12 && *v12 )
  {
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, *v12);
    *v12 = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180059ee4  mov     r11, rsp
0x180059ee7  mov     [r11+20h], r9
0x180059eeb  push    rbx
0x180059eec  push    rsi
0x180059eed  push    rdi
0x180059eee  push    r14
0x180059ef0  push    r15
0x180059ef2  sub     rsp, 0A0h
0x180059ef9  mov     r15, r9
0x180059efc  xor     eax, eax
0x180059efe  xor     ebx, ebx
0x180059f00  mov     dword ptr [rsp+0C8h+ObjectAttributes+4], ebx
0x180059f04  mov     [r11-44h], ebx
0x180059f08  mov     [r11+10h], rbx
0x180059f0c  mov     [r11+8], rbx
0x180059f10  mov     [r11+18h], rbx
0x180059f14  xorps   xmm0, xmm0
0x180059f17  movups  [rsp+0C8h+var_70], xmm0
0x180059f1c  mov     edi, ebx
0x180059f1e  mov     rsi, [rsp+0C8h+BaseAddress]
0x180059f26  test    rsi, rsi
0x180059f29  jz      short loc_180059F2E
0x180059f2b  mov     [rsi], rbx
0x180059f2e  test    r8, r8
0x180059f31  jz      short loc_180059F4A
0x180059f33  mov     dword ptr [rsp+0C8h+var_70], 80008h
0x180059f3b  mov     qword ptr [rsp+0C8h+var_70+8], r8
0x180059f40  lea     rcx, [rsp+0C8h+var_70]
0x180059f45  mov     eax, 2000h
0x180059f4a  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x180059f52  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rdx
0x180059f57  mov     [rsp+0C8h+ObjectAttributes.Attributes], 2C0h
0x180059f62  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rcx
0x180059f67  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059f70  mov     [rsp+0C8h+AllocationAttributes], eax
0x180059f74  lea     rax, [rsp+0C8h+ObjectAttributes]
0x180059f79  mov     qword ptr [rsp+0C8h+SectionPageProtection], rax
0x180059f7e  mov     r9, [rsp+0C8h+arg_40]
0x180059f86  mov     r8, [rsp+0C8h+arg_38]
0x180059f8e  mov     rdx, [rsp+0C8h+arg_30]
0x180059f96  lea     rcx, [rsp+0C8h+Handle]
0x180059f9e  call    CipOpenFile
0x180059fa3  mov     r14d, eax
0x180059fa6  test    eax, eax
0x180059fa8  js      loc_18005A145
0x180059fae  test    rsi, rsi
0x180059fb1  jz      loc_18005A114
0x180059fb7  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x180059fbf  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rbx
0x180059fc4  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x180059fcf  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rbx
0x180059fd4  xorps   xmm0, xmm0
0x180059fd7  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059fe0  mov     rax, [rsp+0C8h+Handle]
0x180059fe8  mov     [rsp+0C8h+FileHandle], rax; FileHandle
0x180059fed  mov     [rsp+0C8h+AllocationAttributes], 8000000h; AllocationAttributes
0x180059ff5  mov     [rsp+0C8h+SectionPageProtection], 2; SectionPageProtection
0x180059ffd  xor     r9d, r9d; MaximumSize
0x18005a000  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x18005a005  lea     edx, [r9+4]; DesiredAccess
0x18005a009  lea     rcx, [rsp+0C8h+SectionHandle]; SectionHandle
0x18005a011  call    cs:__imp_ZwCreateSection
0x18005a018  nop     dword ptr [rax+rax+00h]
0x18005a01d  mov     r14d, eax
0x18005a020  test    eax, eax
0x18005a022  js      loc_18005A145
0x18005a028  mov     [rsp+0C8h+Win32Protect], 2; Win32Protect
0x18005a030  mov     [rsp+0C8h+AllocationType], ebx; AllocationType
0x18005a034  mov     [rsp+0C8h+InheritDisposition], 1; InheritDisposition
0x18005a03c  lea     rax, [rsp+0C8h+ViewSize]
0x18005a044  mov     [rsp+0C8h+FileHandle], rax; ViewSize
0x18005a049  mov     qword ptr [rsp+0C8h+AllocationAttributes], rbx; SectionOffset
0x18005a04e  mov     qword ptr [rsp+0C8h+SectionPageProtection], rbx; CommitSize
0x18005a053  xor     r9d, r9d; ZeroBits
0x18005a056  mov     r8, rsi; BaseAddress
0x18005a059  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005a05d  mov     rcx, [rsp+0C8h+SectionHandle]; SectionHandle
0x18005a065  call    cs:__imp_ZwMapViewOfSection
0x18005a06c  nop     dword ptr [rax+rax+00h]
0x18005a071  mov     r14d, eax
0x18005a074  test    eax, eax
0x18005a076  js      loc_18005A145
0x18005a07c  cmp     [rsp+0C8h+arg_48], rbx
0x18005a084  jz      loc_18005A114
0x18005a08a  mov     eax, 0FFFFEFFFh
0x18005a08f  mov     rdx, [rsp+0C8h+ViewSize]; Length
0x18005a097  cmp     rdx, rax
0x18005a09a  jbe     short loc_18005A0A7
0x18005a09c  mov     r14d, 0C0000040h
0x18005a0a2  jmp     loc_18005A145
0x18005a0a7  mov     qword ptr [rsp+0C8h+SectionPageProtection], rbx; Irp
0x18005a0ac  xor     r9d, r9d; ChargeQuota
0x18005a0af  xor     r8d, r8d; SecondaryBuffer
0x18005a0b2  mov     rcx, [rsi]; VirtualAddress
0x18005a0b5  call    cs:__imp_IoAllocateMdl
0x18005a0bc  nop     dword ptr [rax+rax+00h]
0x18005a0c1  mov     rdi, rax
0x18005a0c4  mov     [rsp+0C8h+var_78], rax
0x18005a0c9  test    rax, rax
0x18005a0cc  jnz     short loc_18005A0D6
0x18005a0ce  mov     r14d, 0C000009Ah
0x18005a0d4  jmp     short loc_18005A145
0x18005a0d6  xor     r8d, r8d; Operation
0x18005a0d9  xor     edx, edx; AccessMode
0x18005a0db  mov     rcx, rdi; MemoryDescriptorList
0x18005a0de  call    cs:__imp_MmProbeAndLockPages
0x18005a0e5  nop     dword ptr [rax+rax+00h]
0x18005a0ea  nop
0x18005a0eb  mov     rax, [rsp+0C8h+arg_48]
0x18005a0f3  mov     [rax], rdi
0x18005a0f6  jmp     short loc_18005A114
0x18005a0f8  mov     r14d, eax
0x18005a0fb  xor     ebx, ebx
0x18005a0fd  mov     rsi, [rsp+0C8h+BaseAddress]
0x18005a105  mov     r15, [rsp+0C8h+arg_18]
0x18005a10d  mov     rdi, [rsp+0C8h+var_78]
0x18005a112  jmp     short loc_18005A145
0x18005a114  mov     rax, [rsp+0C8h+Handle]
0x18005a11c  mov     [r15], rax
0x18005a11f  mov     rcx, [rsp+0C8h+SectionHandle]
0x18005a127  mov     rax, [rsp+0C8h+arg_20]
0x18005a12f  mov     [rax], rcx
0x18005a132  mov     [rsp+0C8h+Handle], rbx
0x18005a13a  mov     [rsp+0C8h+SectionHandle], rbx
0x18005a142  mov     rdi, rbx
0x18005a145  test    rdi, rdi
0x18005a148  jz      short loc_18005A164
0x18005a14a  mov     rcx, rdi; Mdl
0x18005a14d  call    cs:__imp_IoFreeMdl
0x18005a154  nop     dword ptr [rax+rax+00h]
0x18005a159  mov     rax, [rsp+0C8h+arg_48]
0x18005a161  mov     [rax], rbx
0x18005a164  mov     rcx, [rsp+0C8h+SectionHandle]; Handle
0x18005a16c  test    rcx, rcx
0x18005a16f  jz      short loc_18005A188
0x18005a171  call    cs:__imp_ZwClose
0x18005a178  nop     dword ptr [rax+rax+00h]
0x18005a17d  mov     rax, [rsp+0C8h+arg_20]
0x18005a185  mov     [rax], rbx
0x18005a188  mov     rcx, [rsp+0C8h+Handle]; Handle
0x18005a190  test    rcx, rcx
0x18005a193  jz      short loc_18005A1A4
0x18005a195  call    cs:__imp_ZwClose
0x18005a19c  nop     dword ptr [rax+rax+00h]
0x18005a1a1  mov     [r15], rbx
0x18005a1a4  test    r14d, r14d
0x18005a1a7  jns     short loc_18005A1C9
0x18005a1a9  test    rsi, rsi
0x18005a1ac  jz      short loc_18005A1C9
0x18005a1ae  mov     rdx, [rsi]; BaseAddress
0x18005a1b1  test    rdx, rdx
0x18005a1b4  jz      short loc_18005A1C9
0x18005a1b6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005a1ba  call    cs:__imp_ZwUnmapViewOfSection
0x18005a1c1  nop     dword ptr [rax+rax+00h]
0x18005a1c6  mov     [rsi], rbx
0x18005a1c9  mov     eax, r14d
0x18005a1cc  add     rsp, 0A0h
0x18005a1d3  pop     r15
0x18005a1d5  pop     r14
0x18005a1d7  pop     rdi
0x18005a1d8  pop     rsi
0x18005a1d9  pop     rbx
0x18005a1da  retn
```
