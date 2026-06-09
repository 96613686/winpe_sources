# LuafvDelayOrVirtualizeFile

- ea: `0x1400247e0`
- end: `0x140024a83`
- name: `LuafvDelayOrVirtualizeFile`
- size: `675`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64, unsigned __int16 **, char *, bool *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140025350`

## callees

- `0x140005f30`
- `0x1400157d4`
- `0x140022de8`
- `0x1400247e0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400249b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400249b9`
- `FLTMGR!FltClose` at `0x1400249cd`
- `FLTMGR!FltClose` at `0x140024a3c`
- `FLTMGR!FltClose` at `0x1400249cd`
- `FLTMGR!FltClose` at `0x140024a3c`
- `FLTMGR!FltQueryInformationFile` at `0x140024994`
- `FLTMGR!FltQueryInformationFile` at `0x140024994`
- `FLTMGR!FltCreateFileEx2` at `0x14002495a`
- `FLTMGR!FltCreateFileEx2` at `0x14002495a`

## pseudocode

```c
__int64 __fastcall LuafvDelayOrVirtualizeFile(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        unsigned __int16 **a3,
        char *a4,
        bool *a5,
        _DWORD *a6)
{
  char v6; // di
  unsigned __int16 *v9; // r9
  bool v11; // r12
  char v12; // r8
  unsigned __int64 v13; // r10
  _WORD *v14; // rax
  int InformationFile; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  void *v17; // r9
  int v18; // eax
  void *FileHandle; // [rsp+80h] [rbp-80h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  char *v22; // [rsp+90h] [rbp-70h]
  bool *v23; // [rsp+98h] [rbp-68h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD FileInformation[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-10h]

  v6 = *a4;
  FileHandle = 0;
  FileObject = 0;
  v26 = 0;
  memset(&ObjectAttributes, 0, 32);
  if ( v6 )
    v6 = byte_14000F11C;
  v22 = a4;
  v9 = *a3;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  v23 = a5;
  v11 = 0;
  v12 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v13 = *((_QWORD *)v9 + 1);
  v14 = (_WORD *)(v13 + *v9);
  while ( (unsigned __int64)v14 > v13 )
  {
    if ( *--v14 == 58 )
    {
      v12 = 1;
    }
    else if ( *v14 == 92 )
    {
      break;
    }
  }
  if ( (v9[44] & 2) == 0 && v12 )
  {
    if ( (dword_14000F118 & 8) != 0 )
      *a6 |= 0x40u;
    goto LABEL_14;
  }
  if ( (dword_14000F118 & 8) != 0 && *a6 )
  {
LABEL_14:
    InformationFile = -1073741790;
    goto LABEL_32;
  }
  Iopb = a1->Iopb;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  InformationFile = FltCreateFileEx2(
                      LuafvDriverData,
                      *(PFLT_INSTANCE *)(a2 + 24),
                      &FileHandle,
                      &FileObject,
                      *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 0xFFF2FE28 | 0x81,
                      &ObjectAttributes,
                      &a1->IoStatus,
                      0,
                      0,
                      7u,
                      1u,
                      Iopb->Parameters.Create.Options & 0xFFEFFF,
                      0,
                      0,
                      0xA01u,
                      0);
  if ( InformationFile < 0 )
    goto LABEL_21;
  if ( v6 )
  {
    InformationFile = FltQueryInformationFile(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        FileObject,
                        FileInformation,
                        0x28u,
                        FileBasicInformation,
                        0);
    if ( InformationFile >= 0 )
      v6 = (v26 & 0x10) == 0;
  }
  ObfDereferenceObject(FileObject);
  if ( InformationFile >= 0 )
  {
LABEL_21:
    v17 = FileHandle;
  }
  else
  {
    FltClose(FileHandle);
    v17 = 0;
    FileHandle = 0;
  }
  if ( InformationFile == -1073741772 || InformationFile == -1073741766 )
  {
    v6 = 0;
  }
  else
  {
    if ( InformationFile < 0 )
      goto LABEL_32;
    if ( v6 )
    {
      v18 = LuafvPrepareDelayedVirtualization(a2, a1, a3);
      InformationFile = v18;
      if ( v18 < 0 )
      {
        a1->IoStatus.Status = v18;
        a1->IoStatus.Information = 0;
      }
      goto LABEL_32;
    }
  }
  InformationFile = LuafvCreateVirtualFile(a2, a1, (__int64)a3, v17);
  if ( FileHandle )
    FltClose(FileHandle);
  v11 = InformationFile != -1073741790;
LABEL_32:
  *v22 = v6;
  *v23 = v11;
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x1400247e0  push    rbp
0x1400247e2  push    rbx
0x1400247e3  push    rsi
0x1400247e4  push    rdi
0x1400247e5  push    r12
0x1400247e7  push    r13
0x1400247e9  push    r14
0x1400247eb  push    r15
0x1400247ed  lea     rbp, [rsp-8]
0x1400247f2  sub     rsp, 108h
0x1400247f9  mov     rax, cs:__security_cookie
0x140024800  xor     rax, rsp
0x140024803  mov     [rbp+40h+var_48], rax
0x140024807  movzx   edi, byte ptr [r9]
0x14002480b  xor     r11d, r11d
0x14002480e  movzx   eax, cs:byte_14000F11C
0x140024815  xorps   xmm0, xmm0
0x140024818  movups  xmmword ptr [rbp+40h+var_A0.ObjectName], xmm0
0x14002481c  mov     rsi, rcx
0x14002481f  mov     [rbp+40h+FileHandle], r11
0x140024823  mov     rcx, [rbp+40h+arg_20]
0x140024827  mov     r14, rdx
0x14002482a  xor     edx, edx
0x14002482c  mov     [rbp+40h+FileObject], r11
0x140024830  test    dil, dil
0x140024833  mov     [rbp+40h+var_50], rdx
0x140024837  movups  xmmword ptr [rbp+40h+var_A0.Length], xmm0
0x14002483b  cmovnz  edi, eax
0x14002483e  mov     [rbp+40h+var_B0], r9
0x140024842  mov     r9, [r8]
0x140024845  mov     r13, r8
0x140024848  movups  xmmword ptr [rbp+40h+var_A0+1Ch], xmm0
0x14002484c  mov     [rbp+40h+var_A8], rcx
0x140024850  mov     r12b, r11b
0x140024853  mov     rcx, [rbp+40h+arg_28]
0x140024857  mov     r8b, r11b
0x14002485a  movups  [rbp+40h+FileInformation], xmm0
0x14002485e  movups  [rbp+40h+var_60], xmm0
0x140024862  movzx   eax, word ptr [r9]
0x140024866  mov     r10, [r9+8]
0x14002486a  add     rax, r10
0x14002486d  cmp     rax, r10
0x140024870  jbe     short loc_140024885
0x140024872  sub     rax, 2
0x140024876  movzx   edx, word ptr [rax]
0x140024879  cmp     dx, 3Ah ; ':'
0x14002487d  jz      short loc_1400248A0
0x14002487f  cmp     dx, 5Ch ; '\'
0x140024883  jnz     short loc_14002486D
0x140024885  test    byte ptr [r9+58h], 2
0x14002488a  jnz     short loc_1400248A5
0x14002488c  test    r8b, r8b
0x14002488f  jz      short loc_1400248A5
0x140024891  mov     eax, cs:dword_14000F118
0x140024897  test    al, 8
0x140024899  jz      short loc_1400248B4
0x14002489b  or      dword ptr [rcx], 40h
0x14002489e  jmp     short loc_1400248B4
0x1400248a0  mov     r8b, 1
0x1400248a3  jmp     short loc_14002486D
0x1400248a5  mov     eax, cs:dword_14000F118
0x1400248ab  test    al, 8
0x1400248ad  jz      short loc_1400248BE
0x1400248af  cmp     [rcx], r11d
0x1400248b2  jz      short loc_1400248BE
0x1400248b4  mov     ebx, 0C0000022h
0x1400248b9  jmp     loc_140024A52
0x1400248be  mov     rax, [rsi+10h]
0x1400248c2  lea     r15, [rsi+18h]
0x1400248c6  mov     [rsp+140h+DriverContext], r11; DriverContext
0x1400248cb  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x1400248cf  mov     [rsp+140h+Flags], 0A01h; Flags
0x1400248d7  xorps   xmm0, xmm0
0x1400248da  mov     [rsp+140h+EaLength], r11d; EaLength
0x1400248df  mov     [rsp+140h+EaBuffer], r11; EaBuffer
0x1400248e4  mov     [rbp+40h+var_A0.ObjectName], r9
0x1400248e8  lea     r9, [rbp+40h+FileObject]; FileObject
0x1400248ec  mov     [rbp+40h+var_A0.Length], 30h ; '0'
0x1400248f3  mov     [rbp+40h+var_A0.RootDirectory], r11
0x1400248f7  mov     [rbp+40h+var_A0.Attributes], 240h
0x1400248fe  movdqu  xmmword ptr [rbp+40h+var_A0.SecurityDescriptor], xmm0
0x140024903  mov     ecx, [rax+20h]
0x140024906  mov     rax, [rax+18h]
0x14002490a  and     ecx, 0FFEFFFh
0x140024910  mov     [rsp+140h+CreateOptions], ecx; CreateOptions
0x140024914  mov     rcx, cs:LuafvDriverData; Filter
0x14002491b  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x140024923  mov     edx, [rax+10h]
0x140024926  lea     rax, [rbp+40h+var_A0]
0x14002492a  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x140024932  and     edx, 0FFF2FEA9h
0x140024938  mov     [rsp+140h+FileAttributes], r11d; FileAttributes
0x14002493d  or      edx, 81h
0x140024943  mov     [rsp+140h+AllocationSize], r11; AllocationSize
0x140024948  mov     [rsp+140h+IoStatusBlock], r15; IoStatusBlock
0x14002494d  mov     [rsp+140h+ObjectAttributes], rax; ObjectAttributes
0x140024952  mov     [rsp+140h+DesiredAccess], edx; DesiredAccess
0x140024956  mov     rdx, [r14+18h]; Instance
0x14002495a  call    cs:__imp_FltCreateFileEx2
0x140024961  nop     dword ptr [rax+rax+00h]
0x140024966  mov     ebx, eax
0x140024968  test    eax, eax
0x14002496a  js      short loc_1400249E2
0x14002496c  test    dil, dil
0x14002496f  jz      short loc_1400249B5
0x140024971  mov     rdx, [rbp+40h+FileObject]; FileObject
0x140024975  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140024979  mov     rcx, [r14+18h]; Instance
0x14002497d  mov     r9d, 28h ; '('; Length
0x140024983  mov     [rsp+140h+ObjectAttributes], 0; LengthReturned
0x14002498c  mov     [rsp+140h+DesiredAccess], 4; FileInformationClass
0x140024994  call    cs:__imp_FltQueryInformationFile
0x14002499b  nop     dword ptr [rax+rax+00h]
0x1400249a0  mov     ebx, eax
0x1400249a2  test    eax, eax
0x1400249a4  js      short loc_1400249B5
0x1400249a6  mov     dil, byte ptr [rbp+40h+var_50]
0x1400249aa  shr     dil, 4
0x1400249ae  not     dil
0x1400249b1  and     dil, 1
0x1400249b5  mov     rcx, [rbp+40h+FileObject]; Object
0x1400249b9  call    cs:__imp_ObfDereferenceObject
0x1400249c0  nop     dword ptr [rax+rax+00h]
0x1400249c5  test    ebx, ebx
0x1400249c7  jns     short loc_1400249E2
0x1400249c9  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x1400249cd  call    cs:__imp_FltClose
0x1400249d4  nop     dword ptr [rax+rax+00h]
0x1400249d9  xor     r9d, r9d
0x1400249dc  mov     [rbp+40h+FileHandle], r9
0x1400249e0  jmp     short loc_1400249E6
0x1400249e2  mov     r9, [rbp+40h+FileHandle]
0x1400249e6  cmp     ebx, 0C0000034h
0x1400249ec  jz      short loc_140024A20
0x1400249ee  cmp     ebx, 0C000003Ah
0x1400249f4  jz      short loc_140024A20
0x1400249f6  test    ebx, ebx
0x1400249f8  js      short loc_140024A52
0x1400249fa  test    dil, dil
0x1400249fd  jz      short loc_140024A23
0x1400249ff  mov     r8, r13
0x140024a02  mov     rdx, rsi
0x140024a05  mov     rcx, r14
0x140024a08  call    LuafvPrepareDelayedVirtualization
0x140024a0d  mov     ebx, eax
0x140024a0f  test    eax, eax
0x140024a11  jns     short loc_140024A52
0x140024a13  mov     [r15], eax
0x140024a16  mov     qword ptr [rsi+20h], 0
0x140024a1e  jmp     short loc_140024A52
0x140024a20  xor     dil, dil
0x140024a23  mov     r8, r13
0x140024a26  mov     rdx, rsi
0x140024a29  mov     rcx, r14
0x140024a2c  call    LuafvCreateVirtualFile
0x140024a31  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140024a35  mov     ebx, eax
0x140024a37  test    rcx, rcx
0x140024a3a  jz      short loc_140024A48
0x140024a3c  call    cs:__imp_FltClose
0x140024a43  nop     dword ptr [rax+rax+00h]
0x140024a48  cmp     ebx, 0C0000022h
0x140024a4e  setnz   r12b
0x140024a52  mov     rax, [rbp+40h+var_B0]
0x140024a56  mov     [rax], dil
0x140024a59  mov     rax, [rbp+40h+var_A8]
0x140024a5d  mov     [rax], r12b
0x140024a60  mov     eax, ebx
0x140024a62  mov     rcx, [rbp+40h+var_48]
0x140024a66  xor     rcx, rsp; StackCookie
0x140024a69  call    __security_check_cookie
0x140024a6e  add     rsp, 108h
0x140024a75  pop     r15
0x140024a77  pop     r14
0x140024a79  pop     r13
0x140024a7b  pop     r12
0x140024a7d  pop     rdi
0x140024a7e  pop     rsi
0x140024a7f  pop     rbx
0x140024a80  pop     rbp
0x140024a81  retn
```
