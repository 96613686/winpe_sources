# CiReadFileOpenWithFlags

- ea: `0x18009b440`
- end: `0x18009b643`
- name: `CiReadFileOpenWithFlags`
- size: `515`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, PHANDLE, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180099aa4`
- `0x18009b23c`
- `0x18009b314`
- `0x18009b350`
- `0x18009e7a8`

## callees

- `0x18009b440`
- `0x18009b64c`
- `0x18009b7b0`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x18009b49d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18009b577`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18009b577`
- `ntoskrnl!ZwCreateSection` at `0x18009b530`
- `ntoskrnl!ZwCreateSection` at `0x18009b530`
- `ntoskrnl!ZwQueryInformationThread` at `0x18009b5ec`
- `ntoskrnl!ZwQueryInformationThread` at `0x18009b5ec`
- `ntoskrnl!ZwSetInformationThread` at `0x18009b626`
- `ntoskrnl!ZwSetInformationThread` at `0x18009b626`
- `ntoskrnl!MmSectionObjectType` at `0x18009b548`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18009b4c4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18009b4c4`

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
0x18009b440  mov     [rsp-28h+arg_0], rbx
0x18009b445  mov     [rsp-28h+arg_8], rsi
0x18009b44a  push    rbp
0x18009b44b  push    rdi
0x18009b44c  push    r12
0x18009b44e  push    r14
0x18009b450  push    r15
0x18009b452  mov     rbp, rsp
0x18009b455  sub     rsp, 70h
0x18009b459  mov     rbx, [rbp+arg_20]
0x18009b45d  xorps   xmm1, xmm1
0x18009b460  xorps   xmm0, xmm0
0x18009b463  mov     [rbp+ThreadInformation], 0
0x18009b46a  xor     eax, eax
0x18009b46c  mov     esi, r9d
0x18009b46f  mov     r15, r8
0x18009b472  mov     r12d, edx
0x18009b475  mov     r14, rcx
0x18009b478  movups  xmmword ptr [rbx], xmm1
0x18009b47b  movups  xmmword ptr [rbx+10h], xmm1
0x18009b47f  movups  xmmword ptr [rbx+20h], xmm1
0x18009b483  mov     [rbx+20h], r9d
0x18009b487  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18009b48b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18009b48f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18009b493  test    r9b, 1
0x18009b497  jnz     loc_18009B5D2
0x18009b49d  mov     rax, cs:__imp_IoFileObjectType
0x18009b4a4  xor     r9d, r9d; DesiredAccess
0x18009b4a7  mov     [rsp+70h+Handle], rbx; Handle
0x18009b4ac  xor     r8d, r8d; PassedAccessState
0x18009b4af  mov     [rsp+70h+AccessMode], 0; AccessMode
0x18009b4b4  mov     edx, 240h; HandleAttributes
0x18009b4b9  mov     rcx, [rax]
0x18009b4bc  mov     [rsp+70h+ObjectType], rcx; ObjectType
0x18009b4c1  mov     rcx, r14; Object
0x18009b4c4  call    cs:__imp_ObOpenObjectByPointer
0x18009b4cb  nop     dword ptr [rax+rax+00h]
0x18009b4d0  mov     edi, eax
0x18009b4d2  test    eax, eax
0x18009b4d4  jns     short loc_18009B4E3
0x18009b4d6  mov     rcx, rbx
0x18009b4d9  call    CiReadFileClose
0x18009b4de  jmp     loc_18009B5B6
0x18009b4e3  mov     rax, [rbx]
0x18009b4e6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18009b4ea  mov     [rsp+70h+Handle], rax; FileHandle
0x18009b4ef  lea     rcx, [rbx+10h]; SectionHandle
0x18009b4f3  xor     r9d, r9d; MaximumSize
0x18009b4f6  mov     dword ptr [rsp+70h+AccessMode], 8000000h; AllocationAttributes
0x18009b4fe  xorps   xmm0, xmm0
0x18009b501  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18009b508  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18009b510  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18009b517  lea     edx, [r9+4]; DesiredAccess
0x18009b51b  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18009b523  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18009b528  mov     dword ptr [rsp+70h+ObjectType], 2; SectionPageProtection
0x18009b530  call    cs:__imp_ZwCreateSection
0x18009b537  nop     dword ptr [rax+rax+00h]
0x18009b53c  mov     edi, eax
0x18009b53e  test    eax, eax
0x18009b540  js      short loc_18009B4D6
0x18009b542  test    sil, 2
0x18009b546  jnz     short loc_18009B595
0x18009b548  mov     r8, cs:__imp_MmSectionObjectType
0x18009b54f  lea     rax, [rbp+arg_20]
0x18009b553  mov     rcx, [rbx+10h]; Handle
0x18009b557  xor     r9d, r9d; AccessMode
0x18009b55a  mov     qword ptr [rsp+70h+AccessMode], 0; HandleInformation
0x18009b563  mov     [rbp+arg_20], 0
0x18009b56b  mov     r8, [r8]; ObjectType
0x18009b56e  lea     edx, [r9+4]; DesiredAccess
0x18009b572  mov     [rsp+70h+ObjectType], rax; Object
0x18009b577  call    cs:__imp_ObReferenceObjectByHandle
0x18009b57e  nop     dword ptr [rax+rax+00h]
0x18009b583  mov     edi, eax
0x18009b585  mov     rax, [rbp+arg_20]
0x18009b589  mov     [rbx+8], rax
0x18009b58d  test    edi, edi
0x18009b58f  js      loc_18009B4D6
0x18009b595  mov     r9, [rbp+arg_28]
0x18009b599  test    r9, r9
0x18009b59c  jz      short loc_18009B5B6
0x18009b59e  mov     r8, r15
0x18009b5a1  mov     edx, r12d
0x18009b5a4  mov     rcx, rbx
0x18009b5a7  call    CiReadFileSetView
0x18009b5ac  mov     edi, eax
0x18009b5ae  test    eax, eax
0x18009b5b0  js      loc_18009B4D6
0x18009b5b6  lea     r11, [rsp+70h+var_s0]
0x18009b5bb  mov     eax, edi
0x18009b5bd  mov     rbx, [r11+30h]
0x18009b5c1  mov     rsi, [r11+38h]
0x18009b5c5  mov     rsp, r11
0x18009b5c8  pop     r15
0x18009b5ca  pop     r14
0x18009b5cc  pop     r12
0x18009b5ce  pop     rdi
0x18009b5cf  pop     rbp
0x18009b5d0  retn
0x18009b5d2  mov     r9d, 4; ThreadInformationLength
0x18009b5d8  mov     [rsp+70h+ObjectType], rax; ReturnLength
0x18009b5dd  lea     r8, [rbx+28h]; ThreadInformation
0x18009b5e1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18009b5e8  lea     edx, [r9+14h]; ThreadInformationClass
0x18009b5ec  call    cs:__imp_ZwQueryInformationThread
0x18009b5f3  nop     dword ptr [rax+rax+00h]
0x18009b5f8  test    eax, eax
0x18009b5fa  js      loc_18009B49D
0x18009b600  cmp     dword ptr [rbx+28h], 1
0x18009b604  jz      loc_18009B49D
0x18009b60a  mov     r9d, 4; ThreadInformationLength
0x18009b610  mov     [rbp+ThreadInformation], 1
0x18009b617  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18009b61b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18009b622  lea     edx, [r9+14h]; ThreadInformationClass
0x18009b626  call    cs:__imp_ZwSetInformationThread
0x18009b62d  nop     dword ptr [rax+rax+00h]
0x18009b632  test    eax, eax
0x18009b634  js      loc_18009B49D
0x18009b63a  mov     byte ptr [rbx+24h], 1
0x18009b63e  jmp     loc_18009B49D
```
