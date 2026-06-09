# CiReadFileOpenWithFlags

- ea: `0x180099e10`
- end: `0x18009a013`
- name: `CiReadFileOpenWithFlags`
- size: `515`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, PHANDLE, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180098474`
- `0x180099c0c`
- `0x180099ce4`
- `0x180099d20`
- `0x18009d178`

## callees

- `0x180099e10`
- `0x18009a01c`
- `0x18009a180`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x180099e6d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180099f47`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180099f47`
- `ntoskrnl!ZwCreateSection` at `0x180099f00`
- `ntoskrnl!ZwCreateSection` at `0x180099f00`
- `ntoskrnl!ZwQueryInformationThread` at `0x180099fbc`
- `ntoskrnl!ZwQueryInformationThread` at `0x180099fbc`
- `ntoskrnl!ZwSetInformationThread` at `0x180099ff6`
- `ntoskrnl!ZwSetInformationThread` at `0x180099ff6`
- `ntoskrnl!MmSectionObjectType` at `0x180099f18`
- `ntoskrnl!ObOpenObjectByPointer` at `0x180099e94`
- `ntoskrnl!ObOpenObjectByPointer` at `0x180099e94`

## pseudocode

```c
__int64 __fastcall CiReadFileOpenWithFlags(PVOID Object, unsigned int a2, __int64 a3, int a4, PHANDLE a5, __int64 a6)
{
  PHANDLE v6; // rbx
  char v7; // si
  NTSTATUS FileSetView; // edi
  void *v12; // rcx
  PHANDLE Handle; // [rsp+30h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int ThreadInformation; // [rsp+B8h] [rbp+48h] BYREF

  v6 = a5;
  ThreadInformation = 0;
  v7 = a4;
  *(_OWORD *)a5 = 0;
  *((_OWORD *)v6 + 1) = 0;
  *((_OWORD *)v6 + 2) = 0;
  *((_DWORD *)v6 + 8) = a4;
  memset(&ObjectAttributes, 0, 44);
  if ( (a4 & 1) != 0
    && ZwQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, v6 + 5, 4u, 0) >= 0
    && *((_DWORD *)v6 + 10) != 1 )
  {
    ThreadInformation = 1;
    if ( ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &ThreadInformation, 4u) >= 0 )
      *((_BYTE *)v6 + 36) = 1;
  }
  FileSetView = ObOpenObjectByPointer(Object, 0x240u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, v6);
  if ( FileSetView < 0 )
    goto LABEL_3;
  Handle = (PHANDLE)*v6;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileSetView = ZwCreateSection(v6 + 2, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, Handle);
  if ( FileSetView < 0 )
    goto LABEL_3;
  if ( (v7 & 2) == 0 )
  {
    v12 = v6[2];
    a5 = 0;
    FileSetView = ObReferenceObjectByHandle(v12, 4u, MmSectionObjectType, 0, (PVOID *)&a5, 0);
    v6[1] = a5;
    if ( FileSetView < 0 )
      goto LABEL_3;
  }
  if ( a6 )
  {
    FileSetView = CiReadFileSetView(v6, a2, a3);
    if ( FileSetView < 0 )
LABEL_3:
      CiReadFileClose(v6);
  }
  return (unsigned int)FileSetView;
}

```

## disassembly

```asm
0x180099e10  mov     [rsp-28h+arg_0], rbx
0x180099e15  mov     [rsp-28h+arg_8], rsi
0x180099e1a  push    rbp
0x180099e1b  push    rdi
0x180099e1c  push    r12
0x180099e1e  push    r14
0x180099e20  push    r15
0x180099e22  mov     rbp, rsp
0x180099e25  sub     rsp, 70h
0x180099e29  mov     rbx, [rbp+arg_20]
0x180099e2d  xorps   xmm1, xmm1
0x180099e30  xorps   xmm0, xmm0
0x180099e33  mov     [rbp+ThreadInformation], 0
0x180099e3a  xor     eax, eax
0x180099e3c  mov     esi, r9d
0x180099e3f  mov     r15, r8
0x180099e42  mov     r12d, edx
0x180099e45  mov     r14, rcx
0x180099e48  movups  xmmword ptr [rbx], xmm1
0x180099e4b  movups  xmmword ptr [rbx+10h], xmm1
0x180099e4f  movups  xmmword ptr [rbx+20h], xmm1
0x180099e53  mov     [rbx+20h], r9d
0x180099e57  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180099e5b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180099e5f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180099e63  test    r9b, 1
0x180099e67  jnz     loc_180099FA2
0x180099e6d  mov     rax, cs:__imp_IoFileObjectType
0x180099e74  xor     r9d, r9d; DesiredAccess
0x180099e77  mov     [rsp+70h+Handle], rbx; Handle
0x180099e7c  xor     r8d, r8d; PassedAccessState
0x180099e7f  mov     [rsp+70h+AccessMode], 0; AccessMode
0x180099e84  mov     edx, 240h; HandleAttributes
0x180099e89  mov     rcx, [rax]
0x180099e8c  mov     [rsp+70h+ObjectType], rcx; ObjectType
0x180099e91  mov     rcx, r14; Object
0x180099e94  call    cs:__imp_ObOpenObjectByPointer
0x180099e9b  nop     dword ptr [rax+rax+00h]
0x180099ea0  mov     edi, eax
0x180099ea2  test    eax, eax
0x180099ea4  jns     short loc_180099EB3
0x180099ea6  mov     rcx, rbx
0x180099ea9  call    CiReadFileClose
0x180099eae  jmp     loc_180099F86
0x180099eb3  mov     rax, [rbx]
0x180099eb6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180099eba  mov     [rsp+70h+Handle], rax; FileHandle
0x180099ebf  lea     rcx, [rbx+10h]; SectionHandle
0x180099ec3  xor     r9d, r9d; MaximumSize
0x180099ec6  mov     dword ptr [rsp+70h+AccessMode], 8000000h; AllocationAttributes
0x180099ece  xorps   xmm0, xmm0
0x180099ed1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180099ed8  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180099ee0  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180099ee7  lea     edx, [r9+4]; DesiredAccess
0x180099eeb  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180099ef3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180099ef8  mov     dword ptr [rsp+70h+ObjectType], 2; SectionPageProtection
0x180099f00  call    cs:__imp_ZwCreateSection
0x180099f07  nop     dword ptr [rax+rax+00h]
0x180099f0c  mov     edi, eax
0x180099f0e  test    eax, eax
0x180099f10  js      short loc_180099EA6
0x180099f12  test    sil, 2
0x180099f16  jnz     short loc_180099F65
0x180099f18  mov     r8, cs:__imp_MmSectionObjectType
0x180099f1f  lea     rax, [rbp+arg_20]
0x180099f23  mov     rcx, [rbx+10h]; Handle
0x180099f27  xor     r9d, r9d; AccessMode
0x180099f2a  mov     qword ptr [rsp+70h+AccessMode], 0; HandleInformation
0x180099f33  mov     [rbp+arg_20], 0
0x180099f3b  mov     r8, [r8]; ObjectType
0x180099f3e  lea     edx, [r9+4]; DesiredAccess
0x180099f42  mov     [rsp+70h+ObjectType], rax; Object
0x180099f47  call    cs:__imp_ObReferenceObjectByHandle
0x180099f4e  nop     dword ptr [rax+rax+00h]
0x180099f53  mov     edi, eax
0x180099f55  mov     rax, [rbp+arg_20]
0x180099f59  mov     [rbx+8], rax
0x180099f5d  test    edi, edi
0x180099f5f  js      loc_180099EA6
0x180099f65  mov     r9, [rbp+arg_28]
0x180099f69  test    r9, r9
0x180099f6c  jz      short loc_180099F86
0x180099f6e  mov     r8, r15
0x180099f71  mov     edx, r12d
0x180099f74  mov     rcx, rbx
0x180099f77  call    CiReadFileSetView
0x180099f7c  mov     edi, eax
0x180099f7e  test    eax, eax
0x180099f80  js      loc_180099EA6
0x180099f86  lea     r11, [rsp+70h+var_s0]
0x180099f8b  mov     eax, edi
0x180099f8d  mov     rbx, [r11+30h]
0x180099f91  mov     rsi, [r11+38h]
0x180099f95  mov     rsp, r11
0x180099f98  pop     r15
0x180099f9a  pop     r14
0x180099f9c  pop     r12
0x180099f9e  pop     rdi
0x180099f9f  pop     rbp
0x180099fa0  retn
0x180099fa2  mov     r9d, 4; ThreadInformationLength
0x180099fa8  mov     [rsp+70h+ObjectType], rax; ReturnLength
0x180099fad  lea     r8, [rbx+28h]; ThreadInformation
0x180099fb1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180099fb8  lea     edx, [r9+14h]; ThreadInformationClass
0x180099fbc  call    cs:__imp_ZwQueryInformationThread
0x180099fc3  nop     dword ptr [rax+rax+00h]
0x180099fc8  test    eax, eax
0x180099fca  js      loc_180099E6D
0x180099fd0  cmp     dword ptr [rbx+28h], 1
0x180099fd4  jz      loc_180099E6D
0x180099fda  mov     r9d, 4; ThreadInformationLength
0x180099fe0  mov     [rbp+ThreadInformation], 1
0x180099fe7  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180099feb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180099ff2  lea     edx, [r9+14h]; ThreadInformationClass
0x180099ff6  call    cs:__imp_ZwSetInformationThread
0x180099ffd  nop     dword ptr [rax+rax+00h]
0x18009a002  test    eax, eax
0x18009a004  js      loc_180099E6D
0x18009a00a  mov     byte ptr [rbx+24h], 1
0x18009a00e  jmp     loc_180099E6D
```
