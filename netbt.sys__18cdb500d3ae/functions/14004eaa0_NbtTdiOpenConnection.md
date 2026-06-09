# NbtTdiOpenConnection

- ea: `0x14004eaa0`
- end: `0x14004ed99`
- name: `NbtTdiOpenConnection`
- size: `761`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140012a10`

## callees

- `0x140019e48`
- `0x14001c5c4`
- `0x140031140`
- `0x140031440`
- `0x14004eaa0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004ed45`
- `ntoskrnl!ZwClose` at `0x14004ed45`
- `ntoskrnl!ZwCreateFile` at `0x14004ec9d`
- `ntoskrnl!ZwCreateFile` at `0x14004ec9d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004ecf0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004ecf0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004eb87`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004eb87`
- `ntoskrnl!IoFreeMdl` at `0x14004ed59`
- `ntoskrnl!IoFreeMdl` at `0x14004ed6d`
- `ntoskrnl!IoFreeMdl` at `0x14004ed59`
- `ntoskrnl!IoFreeMdl` at `0x14004ed6d`
- `ntoskrnl!IoAllocateMdl` at `0x14004eb6c`
- `ntoskrnl!IoAllocateMdl` at `0x14004ebad`
- `ntoskrnl!IoAllocateMdl` at `0x14004eb6c`
- `ntoskrnl!IoAllocateMdl` at `0x14004ebad`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004eb0b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004eb0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ecb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ed83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ecb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ed83`
- `ntoskrnl!ExAllocatePool2` at `0x14004eb3a`
- `ntoskrnl!ExAllocatePool2` at `0x14004ec1a`
- `ntoskrnl!ExAllocatePool2` at `0x14004eb3a`
- `ntoskrnl!ExAllocatePool2` at `0x14004ec1a`

## pseudocode

```c
__int64 __fastcall NbtTdiOpenConnection(char *VirtualAddress, __int64 a2)
{
  struct _MDL *v4; // rbp
  void *Pool2; // rax
  void *v6; // r14
  struct _MDL *Mdl; // rax
  struct _MDL *v8; // rsi
  PMDL v9; // rax
  unsigned __int8 *v10; // rax
  unsigned __int8 *EaBuffer; // rdi
  NTSTATUS v12; // r15d
  void *v13; // rcx
  void *v15; // rcx
  _QWORD v16[2]; // [rsp+60h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-78h] BYREF
  PVOID Object; // [rsp+100h] [rbp+8h] BYREF

  v16[0] = 0;
  v16[1] = 0;
  v4 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(VirtualAddress, 0, 0x58u);
  memset(VirtualAddress + 96, 0, 0xC8u);
  *((_QWORD *)VirtualAddress + 11) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)VirtualAddress + 13);
  *((_DWORD *)VirtualAddress + 4) = 1131900748;
  NBT_REFERENCE_DEVICE_LOWER_CONNECTION(a2);
  *((_QWORD *)VirtualAddress + 5) = a2;
  Pool2 = (void *)ExAllocatePool2(64, 132, 1819566670);
  v6 = Pool2;
  if ( !Pool2 )
  {
    v8 = 0;
LABEL_10:
    v12 = -1073741670;
    goto LABEL_11;
  }
  *((_QWORD *)VirtualAddress + 29) = Pool2;
  Mdl = IoAllocateMdl(Pool2, 0x84u, 0, 0, 0);
  v8 = Mdl;
  if ( !Mdl )
    goto LABEL_10;
  MmBuildMdlForNonPagedPool(Mdl);
  *((_QWORD *)VirtualAddress + 30) = v8;
  v9 = IoAllocateMdl(VirtualAddress, 0x84u, 0, 0, 0);
  v4 = v9;
  if ( !v9 )
    goto LABEL_10;
  *((_QWORD *)VirtualAddress + 31) = v9;
  ObjectAttributes.RootDirectory = *(HANDLE *)(a2 + 624);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
  ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = (unsigned __int8 *)ExAllocatePool2(64, 37, 1836343886);
  EaBuffer = v10;
  if ( !v10 )
    goto LABEL_10;
  *(_DWORD *)v10 = 0;
  *((_DWORD *)v10 + 1) = 528640;
  memmove(v10 + 8, "ConnectionContext", 0x12u);
  *(_QWORD *)&EaBuffer[EaBuffer[5] + 9] = VirtualAddress;
  v12 = ZwCreateFile(
          (PHANDLE)VirtualAddress + 8,
          0xC0000000,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          0,
          2u,
          0,
          EaBuffer,
          0x25u);
  ExFreePoolWithTag(EaBuffer, 0);
  if ( v12 >= 0 )
  {
    v13 = (void *)*((_QWORD *)VirtualAddress + 8);
    Object = 0;
    v12 = ObReferenceObjectByHandle(v13, 0, 0, 0, &Object, 0);
    *((_QWORD *)VirtualAddress + 6) = Object;
    if ( v12 >= 0 )
    {
      *((_QWORD *)VirtualAddress + 12) = *(_QWORD *)(a2 + 704);
      return (unsigned int)v12;
    }
  }
LABEL_11:
  v15 = (void *)*((_QWORD *)VirtualAddress + 8);
  if ( v15 )
    ZwClose(v15);
  if ( v4 )
    IoFreeMdl(v4);
  if ( v8 )
    IoFreeMdl(v8);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  NBT_DEREFERENCE_DEVICE_LOWER_CONNECTION(a2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14004eaa0  mov     r11, rsp
0x14004eaa3  push    rbx
0x14004eaa4  push    rbp
0x14004eaa5  push    rsi
0x14004eaa6  push    rdi
0x14004eaa7  push    r12
0x14004eaa9  push    r13
0x14004eaab  push    r14
0x14004eaad  push    r15
0x14004eaaf  sub     rsp, 0B8h
0x14004eab6  xorps   xmm0, xmm0
0x14004eab9  xor     r15d, r15d
0x14004eabc  mov     r13, rdx
0x14004eabf  mov     [rsp+0F8h+var_98], r15
0x14004eac4  movups  xmmword ptr [r11-68h], xmm0
0x14004eac9  xor     eax, eax
0x14004eacb  mov     [rsp+0F8h+var_90], r15
0x14004ead0  xor     edx, edx; Val
0x14004ead2  mov     r8d, 58h ; 'X'; Size
0x14004ead8  movups  xmmword ptr [r11-5Ch], xmm0
0x14004eadd  mov     rbx, rcx
0x14004eae0  mov     ebp, r15d
0x14004eae3  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x14004eae8  movups  xmmword ptr [r11-78h], xmm0
0x14004eaed  call    memset
0x14004eaf2  lea     rcx, [rbx+60h]; void *
0x14004eaf6  xor     edx, edx; Val
0x14004eaf8  mov     r8d, 0C8h; Size
0x14004eafe  call    memset
0x14004eb03  lea     rcx, [rbx+68h]; SpinLock
0x14004eb07  mov     [rbx+58h], r15
0x14004eb0b  call    cs:__imp_KeInitializeSpinLock
0x14004eb12  nop     dword ptr [rax+rax+00h]
0x14004eb17  mov     rcx, r13
0x14004eb1a  mov     dword ptr [rbx+10h], 43776F4Ch
0x14004eb21  call    NBT_REFERENCE_DEVICE_LOWER_CONNECTION
0x14004eb26  mov     edx, 84h
0x14004eb2b  mov     [rbx+28h], r13
0x14004eb2f  mov     ecx, 40h ; '@'
0x14004eb34  mov     r8d, 6C74624Eh
0x14004eb3a  call    cs:__imp_ExAllocatePool2
0x14004eb41  nop     dword ptr [rax+rax+00h]
0x14004eb46  mov     r14, rax
0x14004eb49  test    rax, rax
0x14004eb4c  jz      loc_14004ED33
0x14004eb52  xor     r9d, r9d; ChargeQuota
0x14004eb55  mov     [rbx+0E8h], rax
0x14004eb5c  xor     r8d, r8d; SecondaryBuffer
0x14004eb5f  mov     [rsp+0F8h+Irp], r15; Irp
0x14004eb64  mov     edx, 84h; Length
0x14004eb69  mov     rcx, rax; VirtualAddress
0x14004eb6c  call    cs:__imp_IoAllocateMdl
0x14004eb73  nop     dword ptr [rax+rax+00h]
0x14004eb78  mov     rsi, rax
0x14004eb7b  test    rax, rax
0x14004eb7e  jz      loc_14004ED36
0x14004eb84  mov     rcx, rax; MemoryDescriptorList
0x14004eb87  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14004eb8e  nop     dword ptr [rax+rax+00h]
0x14004eb93  xor     r9d, r9d; ChargeQuota
0x14004eb96  mov     [rbx+0F0h], rsi
0x14004eb9d  xor     r8d, r8d; SecondaryBuffer
0x14004eba0  mov     [rsp+0F8h+Irp], r15; Irp
0x14004eba5  mov     edx, 84h; Length
0x14004ebaa  mov     rcx, rbx; VirtualAddress
0x14004ebad  call    cs:__imp_IoAllocateMdl
0x14004ebb4  nop     dword ptr [rax+rax+00h]
0x14004ebb9  mov     rbp, rax
0x14004ebbc  test    rax, rax
0x14004ebbf  jz      loc_14004ED36
0x14004ebc5  mov     [rbx+0F8h], rax
0x14004ebcc  xorps   xmm0, xmm0
0x14004ebcf  mov     rax, [r13+270h]
0x14004ebd6  mov     edx, 25h ; '%'
0x14004ebdb  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], rax
0x14004ebe3  mov     ecx, 40h ; '@'
0x14004ebe8  lea     rax, [rsp+0F8h+var_98]
0x14004ebed  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x14004ebf8  mov     r8d, 6D74624Eh
0x14004ebfe  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x14004ec06  mov     [rsp+0F8h+ObjectAttributes.Attributes], 200h
0x14004ec11  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004ec1a  call    cs:__imp_ExAllocatePool2
0x14004ec21  nop     dword ptr [rax+rax+00h]
0x14004ec26  mov     rdi, rax
0x14004ec29  test    rax, rax
0x14004ec2c  jz      loc_14004ED36
0x14004ec32  lea     rcx, [rax+8]; void *
0x14004ec36  mov     [rax], r15d
0x14004ec39  mov     r8d, 12h; Size
0x14004ec3f  mov     dword ptr [rax+4], 81100h
0x14004ec46  lea     rdx, aConnectioncont; "ConnectionContext"
0x14004ec4d  call    memmove
0x14004ec52  movzx   eax, byte ptr [rdi+5]
0x14004ec56  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x14004ec5b  mov     [rsp+0F8h+EaLength], 25h ; '%'; EaLength
0x14004ec63  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x14004ec6b  mov     [rsp+0F8h+EaBuffer], rdi; EaBuffer
0x14004ec70  lea     rcx, [rbx+40h]; FileHandle
0x14004ec74  mov     [rsp+0F8h+CreateOptions], r15d; CreateOptions
0x14004ec79  mov     edx, 0C0000000h; DesiredAccess
0x14004ec7e  mov     [rsp+0F8h+CreateDisposition], 2; CreateDisposition
0x14004ec86  mov     [rsp+0F8h+ShareAccess], r15d; ShareAccess
0x14004ec8b  mov     [rsp+0F8h+FileAttributes], 80h; FileAttributes
0x14004ec93  mov     [rax+rdi+9], rbx
0x14004ec98  mov     [rsp+0F8h+Irp], r15; AllocationSize
0x14004ec9d  call    cs:__imp_ZwCreateFile
0x14004eca4  nop     dword ptr [rax+rax+00h]
0x14004eca9  xor     edx, edx; Tag
0x14004ecab  mov     rcx, rdi; P
0x14004ecae  mov     r15d, eax
0x14004ecb1  call    cs:__imp_ExFreePoolWithTag
0x14004ecb8  nop     dword ptr [rax+rax+00h]
0x14004ecbd  test    r15d, r15d
0x14004ecc0  js      short loc_14004ED3C
0x14004ecc2  mov     rcx, [rbx+40h]; Handle
0x14004ecc6  lea     rax, [rsp+0F8h+Object]
0x14004ecce  mov     qword ptr [rsp+0F8h+FileAttributes], 0; HandleInformation
0x14004ecd7  xor     r9d, r9d; AccessMode
0x14004ecda  xor     r8d, r8d; ObjectType
0x14004ecdd  mov     [rsp+0F8h+Irp], rax; Object
0x14004ece2  xor     edx, edx; DesiredAccess
0x14004ece4  mov     [rsp+0F8h+Object], 0
0x14004ecf0  call    cs:__imp_ObReferenceObjectByHandle
0x14004ecf7  nop     dword ptr [rax+rax+00h]
0x14004ecfc  mov     r15d, eax
0x14004ecff  mov     rax, [rsp+0F8h+Object]
0x14004ed07  mov     [rbx+30h], rax
0x14004ed0b  test    r15d, r15d
0x14004ed0e  js      short loc_14004ED3C
0x14004ed10  mov     rax, [r13+2C0h]
0x14004ed17  mov     [rbx+60h], rax
0x14004ed1b  mov     eax, r15d
0x14004ed1e  add     rsp, 0B8h
0x14004ed25  pop     r15
0x14004ed27  pop     r14
0x14004ed29  pop     r13
0x14004ed2b  pop     r12
0x14004ed2d  pop     rdi
0x14004ed2e  pop     rsi
0x14004ed2f  pop     rbp
0x14004ed30  pop     rbx
0x14004ed31  retn
0x14004ed33  mov     rsi, r15
0x14004ed36  mov     r15d, 0C000009Ah
0x14004ed3c  mov     rcx, [rbx+40h]; Handle
0x14004ed40  test    rcx, rcx
0x14004ed43  jz      short loc_14004ED51
0x14004ed45  call    cs:__imp_ZwClose
0x14004ed4c  nop     dword ptr [rax+rax+00h]
0x14004ed51  test    rbp, rbp
0x14004ed54  jz      short loc_14004ED65
0x14004ed56  mov     rcx, rbp; Mdl
0x14004ed59  call    cs:__imp_IoFreeMdl
0x14004ed60  nop     dword ptr [rax+rax+00h]
0x14004ed65  test    rsi, rsi
0x14004ed68  jz      short loc_14004ED79
0x14004ed6a  mov     rcx, rsi; Mdl
0x14004ed6d  call    cs:__imp_IoFreeMdl
0x14004ed74  nop     dword ptr [rax+rax+00h]
0x14004ed79  test    r14, r14
0x14004ed7c  jz      short loc_14004ED8F
0x14004ed7e  xor     edx, edx; Tag
0x14004ed80  mov     rcx, r14; P
0x14004ed83  call    cs:__imp_ExFreePoolWithTag
0x14004ed8a  nop     dword ptr [rax+rax+00h]
0x14004ed8f  mov     rcx, r13
0x14004ed92  call    NBT_DEREFERENCE_DEVICE_LOWER_CONNECTION
0x14004ed97  jmp     short loc_14004ED1B
```
