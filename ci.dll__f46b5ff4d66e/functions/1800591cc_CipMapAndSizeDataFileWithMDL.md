# CipMapAndSizeDataFileWithMDL

- ea: `0x1800591cc`
- end: `0x1800594c4`
- name: `CipMapAndSizeDataFileWithMDL`
- size: `760`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID *BaseAddress, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005cee8`
- `0x180071f94`

## callees

- `0x1800591cc`
- `0x1800a6478`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180059459`
- `ntoskrnl!ZwClose` at `0x18005947d`
- `ntoskrnl!ZwClose` at `0x180059459`
- `ntoskrnl!ZwClose` at `0x18005947d`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800594a2`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800594a2`
- `ntoskrnl!MmProbeAndLockPages` at `0x1800593c6`
- `ntoskrnl!MmProbeAndLockPages` at `0x1800593c6`
- `ntoskrnl!IoAllocateMdl` at `0x18005939d`
- `ntoskrnl!IoAllocateMdl` at `0x18005939d`
- `ntoskrnl!ZwCreateSection` at `0x1800592f9`
- `ntoskrnl!ZwCreateSection` at `0x1800592f9`
- `ntoskrnl!ZwMapViewOfSection` at `0x18005934d`
- `ntoskrnl!ZwMapViewOfSection` at `0x18005934d`
- `ntoskrnl!IoFreeMdl` at `0x180059435`
- `ntoskrnl!IoFreeMdl` at `0x180059435`

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
0x1800591cc  mov     r11, rsp
0x1800591cf  mov     [r11+20h], r9
0x1800591d3  push    rbx
0x1800591d4  push    rsi
0x1800591d5  push    rdi
0x1800591d6  push    r14
0x1800591d8  push    r15
0x1800591da  sub     rsp, 0A0h
0x1800591e1  mov     r15, r9
0x1800591e4  xor     eax, eax
0x1800591e6  xor     ebx, ebx
0x1800591e8  mov     dword ptr [rsp+0C8h+ObjectAttributes+4], ebx
0x1800591ec  mov     [r11-44h], ebx
0x1800591f0  mov     [r11+10h], rbx
0x1800591f4  mov     [r11+8], rbx
0x1800591f8  mov     [r11+18h], rbx
0x1800591fc  xorps   xmm0, xmm0
0x1800591ff  movups  [rsp+0C8h+var_70], xmm0
0x180059204  mov     edi, ebx
0x180059206  mov     rsi, [rsp+0C8h+BaseAddress]
0x18005920e  test    rsi, rsi
0x180059211  jz      short loc_180059216
0x180059213  mov     [rsi], rbx
0x180059216  test    r8, r8
0x180059219  jz      short loc_180059232
0x18005921b  mov     dword ptr [rsp+0C8h+var_70], 80008h
0x180059223  mov     qword ptr [rsp+0C8h+var_70+8], r8
0x180059228  lea     rcx, [rsp+0C8h+var_70]
0x18005922d  mov     eax, 2000h
0x180059232  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x18005923a  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rdx
0x18005923f  mov     [rsp+0C8h+ObjectAttributes.Attributes], 2C0h
0x18005924a  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rcx
0x18005924f  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059258  mov     [rsp+0C8h+AllocationAttributes], eax
0x18005925c  lea     rax, [rsp+0C8h+ObjectAttributes]
0x180059261  mov     qword ptr [rsp+0C8h+SectionPageProtection], rax
0x180059266  mov     r9, [rsp+0C8h+arg_40]
0x18005926e  mov     r8, [rsp+0C8h+arg_38]
0x180059276  mov     rdx, [rsp+0C8h+arg_30]
0x18005927e  lea     rcx, [rsp+0C8h+Handle]
0x180059286  call    CipOpenFile
0x18005928b  mov     r14d, eax
0x18005928e  test    eax, eax
0x180059290  js      loc_18005942D
0x180059296  test    rsi, rsi
0x180059299  jz      loc_1800593FC
0x18005929f  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x1800592a7  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rbx
0x1800592ac  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x1800592b7  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rbx
0x1800592bc  xorps   xmm0, xmm0
0x1800592bf  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800592c8  mov     rax, [rsp+0C8h+Handle]
0x1800592d0  mov     [rsp+0C8h+FileHandle], rax; FileHandle
0x1800592d5  mov     [rsp+0C8h+AllocationAttributes], 8000000h; AllocationAttributes
0x1800592dd  mov     [rsp+0C8h+SectionPageProtection], 2; SectionPageProtection
0x1800592e5  xor     r9d, r9d; MaximumSize
0x1800592e8  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x1800592ed  lea     edx, [r9+4]; DesiredAccess
0x1800592f1  lea     rcx, [rsp+0C8h+SectionHandle]; SectionHandle
0x1800592f9  call    cs:__imp_ZwCreateSection
0x180059300  nop     dword ptr [rax+rax+00h]
0x180059305  mov     r14d, eax
0x180059308  test    eax, eax
0x18005930a  js      loc_18005942D
0x180059310  mov     [rsp+0C8h+Win32Protect], 2; Win32Protect
0x180059318  mov     [rsp+0C8h+AllocationType], ebx; AllocationType
0x18005931c  mov     [rsp+0C8h+InheritDisposition], 1; InheritDisposition
0x180059324  lea     rax, [rsp+0C8h+ViewSize]
0x18005932c  mov     [rsp+0C8h+FileHandle], rax; ViewSize
0x180059331  mov     qword ptr [rsp+0C8h+AllocationAttributes], rbx; SectionOffset
0x180059336  mov     qword ptr [rsp+0C8h+SectionPageProtection], rbx; CommitSize
0x18005933b  xor     r9d, r9d; ZeroBits
0x18005933e  mov     r8, rsi; BaseAddress
0x180059341  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180059345  mov     rcx, [rsp+0C8h+SectionHandle]; SectionHandle
0x18005934d  call    cs:__imp_ZwMapViewOfSection
0x180059354  nop     dword ptr [rax+rax+00h]
0x180059359  mov     r14d, eax
0x18005935c  test    eax, eax
0x18005935e  js      loc_18005942D
0x180059364  cmp     [rsp+0C8h+arg_48], rbx
0x18005936c  jz      loc_1800593FC
0x180059372  mov     eax, 0FFFFEFFFh
0x180059377  mov     rdx, [rsp+0C8h+ViewSize]; Length
0x18005937f  cmp     rdx, rax
0x180059382  jbe     short loc_18005938F
0x180059384  mov     r14d, 0C0000040h
0x18005938a  jmp     loc_18005942D
0x18005938f  mov     qword ptr [rsp+0C8h+SectionPageProtection], rbx; Irp
0x180059394  xor     r9d, r9d; ChargeQuota
0x180059397  xor     r8d, r8d; SecondaryBuffer
0x18005939a  mov     rcx, [rsi]; VirtualAddress
0x18005939d  call    cs:__imp_IoAllocateMdl
0x1800593a4  nop     dword ptr [rax+rax+00h]
0x1800593a9  mov     rdi, rax
0x1800593ac  mov     [rsp+0C8h+var_78], rax
0x1800593b1  test    rax, rax
0x1800593b4  jnz     short loc_1800593BE
0x1800593b6  mov     r14d, 0C000009Ah
0x1800593bc  jmp     short loc_18005942D
0x1800593be  xor     r8d, r8d; Operation
0x1800593c1  xor     edx, edx; AccessMode
0x1800593c3  mov     rcx, rdi; MemoryDescriptorList
0x1800593c6  call    cs:__imp_MmProbeAndLockPages
0x1800593cd  nop     dword ptr [rax+rax+00h]
0x1800593d2  nop
0x1800593d3  mov     rax, [rsp+0C8h+arg_48]
0x1800593db  mov     [rax], rdi
0x1800593de  jmp     short loc_1800593FC
0x1800593e0  mov     r14d, eax
0x1800593e3  xor     ebx, ebx
0x1800593e5  mov     rsi, [rsp+0C8h+BaseAddress]
0x1800593ed  mov     r15, [rsp+0C8h+arg_18]
0x1800593f5  mov     rdi, [rsp+0C8h+var_78]
0x1800593fa  jmp     short loc_18005942D
0x1800593fc  mov     rax, [rsp+0C8h+Handle]
0x180059404  mov     [r15], rax
0x180059407  mov     rcx, [rsp+0C8h+SectionHandle]
0x18005940f  mov     rax, [rsp+0C8h+arg_20]
0x180059417  mov     [rax], rcx
0x18005941a  mov     [rsp+0C8h+Handle], rbx
0x180059422  mov     [rsp+0C8h+SectionHandle], rbx
0x18005942a  mov     rdi, rbx
0x18005942d  test    rdi, rdi
0x180059430  jz      short loc_18005944C
0x180059432  mov     rcx, rdi; Mdl
0x180059435  call    cs:__imp_IoFreeMdl
0x18005943c  nop     dword ptr [rax+rax+00h]
0x180059441  mov     rax, [rsp+0C8h+arg_48]
0x180059449  mov     [rax], rbx
0x18005944c  mov     rcx, [rsp+0C8h+SectionHandle]; Handle
0x180059454  test    rcx, rcx
0x180059457  jz      short loc_180059470
0x180059459  call    cs:__imp_ZwClose
0x180059460  nop     dword ptr [rax+rax+00h]
0x180059465  mov     rax, [rsp+0C8h+arg_20]
0x18005946d  mov     [rax], rbx
0x180059470  mov     rcx, [rsp+0C8h+Handle]; Handle
0x180059478  test    rcx, rcx
0x18005947b  jz      short loc_18005948C
0x18005947d  call    cs:__imp_ZwClose
0x180059484  nop     dword ptr [rax+rax+00h]
0x180059489  mov     [r15], rbx
0x18005948c  test    r14d, r14d
0x18005948f  jns     short loc_1800594B1
0x180059491  test    rsi, rsi
0x180059494  jz      short loc_1800594B1
0x180059496  mov     rdx, [rsi]; BaseAddress
0x180059499  test    rdx, rdx
0x18005949c  jz      short loc_1800594B1
0x18005949e  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800594a2  call    cs:__imp_ZwUnmapViewOfSection
0x1800594a9  nop     dword ptr [rax+rax+00h]
0x1800594ae  mov     [rsi], rbx
0x1800594b1  mov     eax, r14d
0x1800594b4  add     rsp, 0A0h
0x1800594bb  pop     r15
0x1800594bd  pop     r14
0x1800594bf  pop     rdi
0x1800594c0  pop     rsi
0x1800594c1  pop     rbx
0x1800594c2  retn
```
