# CipMapAndSizeDataFileWithMDL

- ea: `0x180059e0c`
- end: `0x18005a104`
- name: `CipMapAndSizeDataFileWithMDL`
- size: `760`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID *BaseAddress, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005d4f0`
- `0x180073524`

## callees

- `0x180059e0c`
- `0x1800a7498`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18005a099`
- `ntoskrnl!ZwClose` at `0x18005a0bd`
- `ntoskrnl!ZwClose` at `0x18005a099`
- `ntoskrnl!ZwClose` at `0x18005a0bd`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005a0e2`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005a0e2`
- `ntoskrnl!MmProbeAndLockPages` at `0x18005a006`
- `ntoskrnl!MmProbeAndLockPages` at `0x18005a006`
- `ntoskrnl!IoAllocateMdl` at `0x180059fdd`
- `ntoskrnl!IoAllocateMdl` at `0x180059fdd`
- `ntoskrnl!ZwCreateSection` at `0x180059f39`
- `ntoskrnl!ZwCreateSection` at `0x180059f39`
- `ntoskrnl!ZwMapViewOfSection` at `0x180059f8d`
- `ntoskrnl!ZwMapViewOfSection` at `0x180059f8d`
- `ntoskrnl!IoFreeMdl` at `0x18005a075`
- `ntoskrnl!IoFreeMdl` at `0x18005a075`

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
0x180059e0c  mov     r11, rsp
0x180059e0f  mov     [r11+20h], r9
0x180059e13  push    rbx
0x180059e14  push    rsi
0x180059e15  push    rdi
0x180059e16  push    r14
0x180059e18  push    r15
0x180059e1a  sub     rsp, 0A0h
0x180059e21  mov     r15, r9
0x180059e24  xor     eax, eax
0x180059e26  xor     ebx, ebx
0x180059e28  mov     dword ptr [rsp+0C8h+ObjectAttributes+4], ebx
0x180059e2c  mov     [r11-44h], ebx
0x180059e30  mov     [r11+10h], rbx
0x180059e34  mov     [r11+8], rbx
0x180059e38  mov     [r11+18h], rbx
0x180059e3c  xorps   xmm0, xmm0
0x180059e3f  movups  [rsp+0C8h+var_70], xmm0
0x180059e44  mov     edi, ebx
0x180059e46  mov     rsi, [rsp+0C8h+BaseAddress]
0x180059e4e  test    rsi, rsi
0x180059e51  jz      short loc_180059E56
0x180059e53  mov     [rsi], rbx
0x180059e56  test    r8, r8
0x180059e59  jz      short loc_180059E72
0x180059e5b  mov     dword ptr [rsp+0C8h+var_70], 80008h
0x180059e63  mov     qword ptr [rsp+0C8h+var_70+8], r8
0x180059e68  lea     rcx, [rsp+0C8h+var_70]
0x180059e6d  mov     eax, 2000h
0x180059e72  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x180059e7a  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rdx
0x180059e7f  mov     [rsp+0C8h+ObjectAttributes.Attributes], 2C0h
0x180059e8a  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rcx
0x180059e8f  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059e98  mov     [rsp+0C8h+AllocationAttributes], eax
0x180059e9c  lea     rax, [rsp+0C8h+ObjectAttributes]
0x180059ea1  mov     qword ptr [rsp+0C8h+SectionPageProtection], rax
0x180059ea6  mov     r9, [rsp+0C8h+arg_40]
0x180059eae  mov     r8, [rsp+0C8h+arg_38]
0x180059eb6  mov     rdx, [rsp+0C8h+arg_30]
0x180059ebe  lea     rcx, [rsp+0C8h+Handle]
0x180059ec6  call    CipOpenFile
0x180059ecb  mov     r14d, eax
0x180059ece  test    eax, eax
0x180059ed0  js      loc_18005A06D
0x180059ed6  test    rsi, rsi
0x180059ed9  jz      loc_18005A03C
0x180059edf  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x180059ee7  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rbx
0x180059eec  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x180059ef7  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rbx
0x180059efc  xorps   xmm0, xmm0
0x180059eff  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059f08  mov     rax, [rsp+0C8h+Handle]
0x180059f10  mov     [rsp+0C8h+FileHandle], rax; FileHandle
0x180059f15  mov     [rsp+0C8h+AllocationAttributes], 8000000h; AllocationAttributes
0x180059f1d  mov     [rsp+0C8h+SectionPageProtection], 2; SectionPageProtection
0x180059f25  xor     r9d, r9d; MaximumSize
0x180059f28  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x180059f2d  lea     edx, [r9+4]; DesiredAccess
0x180059f31  lea     rcx, [rsp+0C8h+SectionHandle]; SectionHandle
0x180059f39  call    cs:__imp_ZwCreateSection
0x180059f40  nop     dword ptr [rax+rax+00h]
0x180059f45  mov     r14d, eax
0x180059f48  test    eax, eax
0x180059f4a  js      loc_18005A06D
0x180059f50  mov     [rsp+0C8h+Win32Protect], 2; Win32Protect
0x180059f58  mov     [rsp+0C8h+AllocationType], ebx; AllocationType
0x180059f5c  mov     [rsp+0C8h+InheritDisposition], 1; InheritDisposition
0x180059f64  lea     rax, [rsp+0C8h+ViewSize]
0x180059f6c  mov     [rsp+0C8h+FileHandle], rax; ViewSize
0x180059f71  mov     qword ptr [rsp+0C8h+AllocationAttributes], rbx; SectionOffset
0x180059f76  mov     qword ptr [rsp+0C8h+SectionPageProtection], rbx; CommitSize
0x180059f7b  xor     r9d, r9d; ZeroBits
0x180059f7e  mov     r8, rsi; BaseAddress
0x180059f81  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180059f85  mov     rcx, [rsp+0C8h+SectionHandle]; SectionHandle
0x180059f8d  call    cs:__imp_ZwMapViewOfSection
0x180059f94  nop     dword ptr [rax+rax+00h]
0x180059f99  mov     r14d, eax
0x180059f9c  test    eax, eax
0x180059f9e  js      loc_18005A06D
0x180059fa4  cmp     [rsp+0C8h+arg_48], rbx
0x180059fac  jz      loc_18005A03C
0x180059fb2  mov     eax, 0FFFFEFFFh
0x180059fb7  mov     rdx, [rsp+0C8h+ViewSize]; Length
0x180059fbf  cmp     rdx, rax
0x180059fc2  jbe     short loc_180059FCF
0x180059fc4  mov     r14d, 0C0000040h
0x180059fca  jmp     loc_18005A06D
0x180059fcf  mov     qword ptr [rsp+0C8h+SectionPageProtection], rbx; Irp
0x180059fd4  xor     r9d, r9d; ChargeQuota
0x180059fd7  xor     r8d, r8d; SecondaryBuffer
0x180059fda  mov     rcx, [rsi]; VirtualAddress
0x180059fdd  call    cs:__imp_IoAllocateMdl
0x180059fe4  nop     dword ptr [rax+rax+00h]
0x180059fe9  mov     rdi, rax
0x180059fec  mov     [rsp+0C8h+var_78], rax
0x180059ff1  test    rax, rax
0x180059ff4  jnz     short loc_180059FFE
0x180059ff6  mov     r14d, 0C000009Ah
0x180059ffc  jmp     short loc_18005A06D
0x180059ffe  xor     r8d, r8d; Operation
0x18005a001  xor     edx, edx; AccessMode
0x18005a003  mov     rcx, rdi; MemoryDescriptorList
0x18005a006  call    cs:__imp_MmProbeAndLockPages
0x18005a00d  nop     dword ptr [rax+rax+00h]
0x18005a012  nop
0x18005a013  mov     rax, [rsp+0C8h+arg_48]
0x18005a01b  mov     [rax], rdi
0x18005a01e  jmp     short loc_18005A03C
0x18005a020  mov     r14d, eax
0x18005a023  xor     ebx, ebx
0x18005a025  mov     rsi, [rsp+0C8h+BaseAddress]
0x18005a02d  mov     r15, [rsp+0C8h+arg_18]
0x18005a035  mov     rdi, [rsp+0C8h+var_78]
0x18005a03a  jmp     short loc_18005A06D
0x18005a03c  mov     rax, [rsp+0C8h+Handle]
0x18005a044  mov     [r15], rax
0x18005a047  mov     rcx, [rsp+0C8h+SectionHandle]
0x18005a04f  mov     rax, [rsp+0C8h+arg_20]
0x18005a057  mov     [rax], rcx
0x18005a05a  mov     [rsp+0C8h+Handle], rbx
0x18005a062  mov     [rsp+0C8h+SectionHandle], rbx
0x18005a06a  mov     rdi, rbx
0x18005a06d  test    rdi, rdi
0x18005a070  jz      short loc_18005A08C
0x18005a072  mov     rcx, rdi; Mdl
0x18005a075  call    cs:__imp_IoFreeMdl
0x18005a07c  nop     dword ptr [rax+rax+00h]
0x18005a081  mov     rax, [rsp+0C8h+arg_48]
0x18005a089  mov     [rax], rbx
0x18005a08c  mov     rcx, [rsp+0C8h+SectionHandle]; Handle
0x18005a094  test    rcx, rcx
0x18005a097  jz      short loc_18005A0B0
0x18005a099  call    cs:__imp_ZwClose
0x18005a0a0  nop     dword ptr [rax+rax+00h]
0x18005a0a5  mov     rax, [rsp+0C8h+arg_20]
0x18005a0ad  mov     [rax], rbx
0x18005a0b0  mov     rcx, [rsp+0C8h+Handle]; Handle
0x18005a0b8  test    rcx, rcx
0x18005a0bb  jz      short loc_18005A0CC
0x18005a0bd  call    cs:__imp_ZwClose
0x18005a0c4  nop     dword ptr [rax+rax+00h]
0x18005a0c9  mov     [r15], rbx
0x18005a0cc  test    r14d, r14d
0x18005a0cf  jns     short loc_18005A0F1
0x18005a0d1  test    rsi, rsi
0x18005a0d4  jz      short loc_18005A0F1
0x18005a0d6  mov     rdx, [rsi]; BaseAddress
0x18005a0d9  test    rdx, rdx
0x18005a0dc  jz      short loc_18005A0F1
0x18005a0de  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005a0e2  call    cs:__imp_ZwUnmapViewOfSection
0x18005a0e9  nop     dword ptr [rax+rax+00h]
0x18005a0ee  mov     [rsi], rbx
0x18005a0f1  mov     eax, r14d
0x18005a0f4  add     rsp, 0A0h
0x18005a0fb  pop     r15
0x18005a0fd  pop     r14
0x18005a0ff  pop     rdi
0x18005a100  pop     rsi
0x18005a101  pop     rbx
0x18005a102  retn
```
