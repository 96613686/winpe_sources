# CiReadFileOpenWithFlags

- ea: `0x1800a0780`
- end: `0x1800a0983`
- name: `CiReadFileOpenWithFlags`
- size: `515`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, PHANDLE, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18008fa34`
- `0x18009e9b0`
- `0x1800a057c`
- `0x1800a0654`
- `0x1800a0690`

## callees

- `0x1800a0780`
- `0x1800a098c`
- `0x1800a0af0`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x1800a07dd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800a08b7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800a08b7`
- `ntoskrnl!ZwCreateSection` at `0x1800a0870`
- `ntoskrnl!ZwCreateSection` at `0x1800a0870`
- `ntoskrnl!ZwQueryInformationThread` at `0x1800a092c`
- `ntoskrnl!ZwQueryInformationThread` at `0x1800a092c`
- `ntoskrnl!ZwSetInformationThread` at `0x1800a0966`
- `ntoskrnl!ZwSetInformationThread` at `0x1800a0966`
- `ntoskrnl!MmSectionObjectType` at `0x1800a0888`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a0804`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a0804`

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
0x1800a0780  mov     [rsp-28h+arg_0], rbx
0x1800a0785  mov     [rsp-28h+arg_8], rsi
0x1800a078a  push    rbp
0x1800a078b  push    rdi
0x1800a078c  push    r12
0x1800a078e  push    r14
0x1800a0790  push    r15
0x1800a0792  mov     rbp, rsp
0x1800a0795  sub     rsp, 70h
0x1800a0799  mov     rbx, [rbp+arg_20]
0x1800a079d  xorps   xmm1, xmm1
0x1800a07a0  xorps   xmm0, xmm0
0x1800a07a3  mov     [rbp+ThreadInformation], 0
0x1800a07aa  xor     eax, eax
0x1800a07ac  mov     esi, r9d
0x1800a07af  mov     r15, r8
0x1800a07b2  mov     r12d, edx
0x1800a07b5  mov     r14, rcx
0x1800a07b8  movups  xmmword ptr [rbx], xmm1
0x1800a07bb  movups  xmmword ptr [rbx+10h], xmm1
0x1800a07bf  movups  xmmword ptr [rbx+20h], xmm1
0x1800a07c3  mov     [rbx+20h], r9d
0x1800a07c7  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800a07cb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800a07cf  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800a07d3  test    r9b, 1
0x1800a07d7  jnz     loc_1800A0912
0x1800a07dd  mov     rax, cs:__imp_IoFileObjectType
0x1800a07e4  xor     r9d, r9d; DesiredAccess
0x1800a07e7  mov     [rsp+70h+Handle], rbx; Handle
0x1800a07ec  xor     r8d, r8d; PassedAccessState
0x1800a07ef  mov     [rsp+70h+AccessMode], 0; AccessMode
0x1800a07f4  mov     edx, 240h; HandleAttributes
0x1800a07f9  mov     rcx, [rax]
0x1800a07fc  mov     [rsp+70h+ObjectType], rcx; ObjectType
0x1800a0801  mov     rcx, r14; Object
0x1800a0804  call    cs:__imp_ObOpenObjectByPointer
0x1800a080b  nop     dword ptr [rax+rax+00h]
0x1800a0810  mov     edi, eax
0x1800a0812  test    eax, eax
0x1800a0814  jns     short loc_1800A0823
0x1800a0816  mov     rcx, rbx
0x1800a0819  call    CiReadFileClose
0x1800a081e  jmp     loc_1800A08F6
0x1800a0823  mov     rax, [rbx]
0x1800a0826  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800a082a  mov     [rsp+70h+Handle], rax; FileHandle
0x1800a082f  lea     rcx, [rbx+10h]; SectionHandle
0x1800a0833  xor     r9d, r9d; MaximumSize
0x1800a0836  mov     dword ptr [rsp+70h+AccessMode], 8000000h; AllocationAttributes
0x1800a083e  xorps   xmm0, xmm0
0x1800a0841  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800a0848  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800a0850  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1800a0857  lea     edx, [r9+4]; DesiredAccess
0x1800a085b  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800a0863  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a0868  mov     dword ptr [rsp+70h+ObjectType], 2; SectionPageProtection
0x1800a0870  call    cs:__imp_ZwCreateSection
0x1800a0877  nop     dword ptr [rax+rax+00h]
0x1800a087c  mov     edi, eax
0x1800a087e  test    eax, eax
0x1800a0880  js      short loc_1800A0816
0x1800a0882  test    sil, 2
0x1800a0886  jnz     short loc_1800A08D5
0x1800a0888  mov     r8, cs:__imp_MmSectionObjectType
0x1800a088f  lea     rax, [rbp+arg_20]
0x1800a0893  mov     rcx, [rbx+10h]; Handle
0x1800a0897  xor     r9d, r9d; AccessMode
0x1800a089a  mov     qword ptr [rsp+70h+AccessMode], 0; HandleInformation
0x1800a08a3  mov     [rbp+arg_20], 0
0x1800a08ab  mov     r8, [r8]; ObjectType
0x1800a08ae  lea     edx, [r9+4]; DesiredAccess
0x1800a08b2  mov     [rsp+70h+ObjectType], rax; Object
0x1800a08b7  call    cs:__imp_ObReferenceObjectByHandle
0x1800a08be  nop     dword ptr [rax+rax+00h]
0x1800a08c3  mov     edi, eax
0x1800a08c5  mov     rax, [rbp+arg_20]
0x1800a08c9  mov     [rbx+8], rax
0x1800a08cd  test    edi, edi
0x1800a08cf  js      loc_1800A0816
0x1800a08d5  mov     r9, [rbp+arg_28]
0x1800a08d9  test    r9, r9
0x1800a08dc  jz      short loc_1800A08F6
0x1800a08de  mov     r8, r15
0x1800a08e1  mov     edx, r12d
0x1800a08e4  mov     rcx, rbx
0x1800a08e7  call    CiReadFileSetView
0x1800a08ec  mov     edi, eax
0x1800a08ee  test    eax, eax
0x1800a08f0  js      loc_1800A0816
0x1800a08f6  lea     r11, [rsp+70h+var_s0]
0x1800a08fb  mov     eax, edi
0x1800a08fd  mov     rbx, [r11+30h]
0x1800a0901  mov     rsi, [r11+38h]
0x1800a0905  mov     rsp, r11
0x1800a0908  pop     r15
0x1800a090a  pop     r14
0x1800a090c  pop     r12
0x1800a090e  pop     rdi
0x1800a090f  pop     rbp
0x1800a0910  retn
0x1800a0912  mov     r9d, 4; ThreadInformationLength
0x1800a0918  mov     [rsp+70h+ObjectType], rax; ReturnLength
0x1800a091d  lea     r8, [rbx+28h]; ThreadInformation
0x1800a0921  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800a0928  lea     edx, [r9+14h]; ThreadInformationClass
0x1800a092c  call    cs:__imp_ZwQueryInformationThread
0x1800a0933  nop     dword ptr [rax+rax+00h]
0x1800a0938  test    eax, eax
0x1800a093a  js      loc_1800A07DD
0x1800a0940  cmp     dword ptr [rbx+28h], 1
0x1800a0944  jz      loc_1800A07DD
0x1800a094a  mov     r9d, 4; ThreadInformationLength
0x1800a0950  mov     [rbp+ThreadInformation], 1
0x1800a0957  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800a095b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800a0962  lea     edx, [r9+14h]; ThreadInformationClass
0x1800a0966  call    cs:__imp_ZwSetInformationThread
0x1800a096d  nop     dword ptr [rax+rax+00h]
0x1800a0972  test    eax, eax
0x1800a0974  js      loc_1800A07DD
0x1800a097a  mov     byte ptr [rbx+24h], 1
0x1800a097e  jmp     loc_1800A07DD
```
