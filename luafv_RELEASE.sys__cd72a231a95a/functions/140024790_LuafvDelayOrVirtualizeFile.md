# LuafvDelayOrVirtualizeFile

- ea: `0x140024790`
- end: `0x140024a33`
- name: `LuafvDelayOrVirtualizeFile`
- size: `675`
- prototype: `__int64 __fastcall(__int64, __int64, const UNICODE_STRING **, char *, bool *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140025300`

## callees

- `0x140005bb0`
- `0x1400157d4`
- `0x140022d98`
- `0x140024790`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140024969`
- `ntoskrnl!ObfDereferenceObject` at `0x140024969`
- `FLTMGR!FltClose` at `0x14002497d`
- `FLTMGR!FltClose` at `0x1400249ec`
- `FLTMGR!FltClose` at `0x14002497d`
- `FLTMGR!FltClose` at `0x1400249ec`
- `FLTMGR!FltQueryInformationFile` at `0x140024944`
- `FLTMGR!FltQueryInformationFile` at `0x140024944`
- `FLTMGR!FltCreateFileEx2` at `0x14002490a`
- `FLTMGR!FltCreateFileEx2` at `0x14002490a`

## pseudocode

```c
__int64 __fastcall LuafvDelayOrVirtualizeFile(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING **a3,
        char *a4,
        bool *a5,
        _DWORD *a6)
{
  char v6; // di
  UNICODE_STRING *v9; // r9
  bool v11; // r12
  char v12; // r8
  PWSTR Buffer; // r10
  PWSTR v14; // rax
  int InformationFile; // ebx
  __int64 v16; // rax
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
    v6 = byte_14000EADC;
  v22 = a4;
  v9 = (UNICODE_STRING *)*a3;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  v23 = a5;
  v11 = 0;
  v12 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  Buffer = v9->Buffer;
  v14 = (PWSTR)((char *)Buffer + v9->Length);
  while ( v14 > Buffer )
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
  if ( ((__int64)v9[5].Buffer & 2) == 0 && v12 )
  {
    if ( (dword_14000EAD8 & 8) != 0 )
      *a6 |= 0x40u;
    goto LABEL_14;
  }
  if ( (dword_14000EAD8 & 8) != 0 && *a6 )
  {
LABEL_14:
    InformationFile = -1073741790;
    goto LABEL_32;
  }
  v16 = *(_QWORD *)(a1 + 16);
  ObjectAttributes.ObjectName = v9;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  InformationFile = FltCreateFileEx2(
                      LuafvDriverData,
                      *(PFLT_INSTANCE *)(a2 + 24),
                      &FileHandle,
                      &FileObject,
                      *(_DWORD *)(*(_QWORD *)(v16 + 24) + 16LL) & 0xFFF2FE28 | 0x81,
                      &ObjectAttributes,
                      (PIO_STATUS_BLOCK)(a1 + 24),
                      0,
                      0,
                      7u,
                      1u,
                      *(_DWORD *)(v16 + 32) & 0xFFEFFF,
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
      v18 = LuafvPrepareDelayedVirtualization(a2, a1, a3, v17);
      InformationFile = v18;
      if ( v18 < 0 )
      {
        *(_DWORD *)(a1 + 24) = v18;
        *(_QWORD *)(a1 + 32) = 0;
      }
      goto LABEL_32;
    }
  }
  InformationFile = LuafvCreateVirtualFile(a2, a1, (__int64 *)a3, (__int64)v17);
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
0x140024790  push    rbp
0x140024792  push    rbx
0x140024793  push    rsi
0x140024794  push    rdi
0x140024795  push    r12
0x140024797  push    r13
0x140024799  push    r14
0x14002479b  push    r15
0x14002479d  lea     rbp, [rsp-8]
0x1400247a2  sub     rsp, 108h
0x1400247a9  mov     rax, cs:__security_cookie
0x1400247b0  xor     rax, rsp
0x1400247b3  mov     [rbp+40h+var_48], rax
0x1400247b7  movzx   edi, byte ptr [r9]
0x1400247bb  xor     r11d, r11d
0x1400247be  movzx   eax, cs:byte_14000EADC
0x1400247c5  xorps   xmm0, xmm0
0x1400247c8  movups  xmmword ptr [rbp+40h+var_A0.ObjectName], xmm0
0x1400247cc  mov     rsi, rcx
0x1400247cf  mov     [rbp+40h+FileHandle], r11
0x1400247d3  mov     rcx, [rbp+40h+arg_20]
0x1400247d7  mov     r14, rdx
0x1400247da  xor     edx, edx
0x1400247dc  mov     [rbp+40h+FileObject], r11
0x1400247e0  test    dil, dil
0x1400247e3  mov     [rbp+40h+var_50], rdx
0x1400247e7  movups  xmmword ptr [rbp+40h+var_A0.Length], xmm0
0x1400247eb  cmovnz  edi, eax
0x1400247ee  mov     [rbp+40h+var_B0], r9
0x1400247f2  mov     r9, [r8]
0x1400247f5  mov     r13, r8
0x1400247f8  movups  xmmword ptr [rbp+40h+var_A0+1Ch], xmm0
0x1400247fc  mov     [rbp+40h+var_A8], rcx
0x140024800  mov     r12b, r11b
0x140024803  mov     rcx, [rbp+40h+arg_28]
0x140024807  mov     r8b, r11b
0x14002480a  movups  [rbp+40h+FileInformation], xmm0
0x14002480e  movups  [rbp+40h+var_60], xmm0
0x140024812  movzx   eax, word ptr [r9]
0x140024816  mov     r10, [r9+8]
0x14002481a  add     rax, r10
0x14002481d  cmp     rax, r10
0x140024820  jbe     short loc_140024835
0x140024822  sub     rax, 2
0x140024826  movzx   edx, word ptr [rax]
0x140024829  cmp     dx, 3Ah ; ':'
0x14002482d  jz      short loc_140024850
0x14002482f  cmp     dx, 5Ch ; '\'
0x140024833  jnz     short loc_14002481D
0x140024835  test    byte ptr [r9+58h], 2
0x14002483a  jnz     short loc_140024855
0x14002483c  test    r8b, r8b
0x14002483f  jz      short loc_140024855
0x140024841  mov     eax, cs:dword_14000EAD8
0x140024847  test    al, 8
0x140024849  jz      short loc_140024864
0x14002484b  or      dword ptr [rcx], 40h
0x14002484e  jmp     short loc_140024864
0x140024850  mov     r8b, 1
0x140024853  jmp     short loc_14002481D
0x140024855  mov     eax, cs:dword_14000EAD8
0x14002485b  test    al, 8
0x14002485d  jz      short loc_14002486E
0x14002485f  cmp     [rcx], r11d
0x140024862  jz      short loc_14002486E
0x140024864  mov     ebx, 0C0000022h
0x140024869  jmp     loc_140024A02
0x14002486e  mov     rax, [rsi+10h]
0x140024872  lea     r15, [rsi+18h]
0x140024876  mov     [rsp+140h+DriverContext], r11; DriverContext
0x14002487b  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x14002487f  mov     [rsp+140h+Flags], 0A01h; Flags
0x140024887  xorps   xmm0, xmm0
0x14002488a  mov     [rsp+140h+EaLength], r11d; EaLength
0x14002488f  mov     [rsp+140h+EaBuffer], r11; EaBuffer
0x140024894  mov     [rbp+40h+var_A0.ObjectName], r9
0x140024898  lea     r9, [rbp+40h+FileObject]; FileObject
0x14002489c  mov     [rbp+40h+var_A0.Length], 30h ; '0'
0x1400248a3  mov     [rbp+40h+var_A0.RootDirectory], r11
0x1400248a7  mov     [rbp+40h+var_A0.Attributes], 240h
0x1400248ae  movdqu  xmmword ptr [rbp+40h+var_A0.SecurityDescriptor], xmm0
0x1400248b3  mov     ecx, [rax+20h]
0x1400248b6  mov     rax, [rax+18h]
0x1400248ba  and     ecx, 0FFEFFFh
0x1400248c0  mov     [rsp+140h+CreateOptions], ecx; CreateOptions
0x1400248c4  mov     rcx, cs:LuafvDriverData; Filter
0x1400248cb  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x1400248d3  mov     edx, [rax+10h]
0x1400248d6  lea     rax, [rbp+40h+var_A0]
0x1400248da  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x1400248e2  and     edx, 0FFF2FEA9h
0x1400248e8  mov     [rsp+140h+FileAttributes], r11d; FileAttributes
0x1400248ed  or      edx, 81h
0x1400248f3  mov     [rsp+140h+AllocationSize], r11; AllocationSize
0x1400248f8  mov     [rsp+140h+IoStatusBlock], r15; IoStatusBlock
0x1400248fd  mov     [rsp+140h+ObjectAttributes], rax; ObjectAttributes
0x140024902  mov     [rsp+140h+DesiredAccess], edx; DesiredAccess
0x140024906  mov     rdx, [r14+18h]; Instance
0x14002490a  call    cs:__imp_FltCreateFileEx2
0x140024911  nop     dword ptr [rax+rax+00h]
0x140024916  mov     ebx, eax
0x140024918  test    eax, eax
0x14002491a  js      short loc_140024992
0x14002491c  test    dil, dil
0x14002491f  jz      short loc_140024965
0x140024921  mov     rdx, [rbp+40h+FileObject]; FileObject
0x140024925  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140024929  mov     rcx, [r14+18h]; Instance
0x14002492d  mov     r9d, 28h ; '('; Length
0x140024933  mov     [rsp+140h+ObjectAttributes], 0; LengthReturned
0x14002493c  mov     [rsp+140h+DesiredAccess], 4; FileInformationClass
0x140024944  call    cs:__imp_FltQueryInformationFile
0x14002494b  nop     dword ptr [rax+rax+00h]
0x140024950  mov     ebx, eax
0x140024952  test    eax, eax
0x140024954  js      short loc_140024965
0x140024956  mov     dil, byte ptr [rbp+40h+var_50]
0x14002495a  shr     dil, 4
0x14002495e  not     dil
0x140024961  and     dil, 1
0x140024965  mov     rcx, [rbp+40h+FileObject]; Object
0x140024969  call    cs:__imp_ObfDereferenceObject
0x140024970  nop     dword ptr [rax+rax+00h]
0x140024975  test    ebx, ebx
0x140024977  jns     short loc_140024992
0x140024979  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14002497d  call    cs:__imp_FltClose
0x140024984  nop     dword ptr [rax+rax+00h]
0x140024989  xor     r9d, r9d
0x14002498c  mov     [rbp+40h+FileHandle], r9
0x140024990  jmp     short loc_140024996
0x140024992  mov     r9, [rbp+40h+FileHandle]
0x140024996  cmp     ebx, 0C0000034h
0x14002499c  jz      short loc_1400249D0
0x14002499e  cmp     ebx, 0C000003Ah
0x1400249a4  jz      short loc_1400249D0
0x1400249a6  test    ebx, ebx
0x1400249a8  js      short loc_140024A02
0x1400249aa  test    dil, dil
0x1400249ad  jz      short loc_1400249D3
0x1400249af  mov     r8, r13
0x1400249b2  mov     rdx, rsi
0x1400249b5  mov     rcx, r14
0x1400249b8  call    LuafvPrepareDelayedVirtualization
0x1400249bd  mov     ebx, eax
0x1400249bf  test    eax, eax
0x1400249c1  jns     short loc_140024A02
0x1400249c3  mov     [r15], eax
0x1400249c6  mov     qword ptr [rsi+20h], 0
0x1400249ce  jmp     short loc_140024A02
0x1400249d0  xor     dil, dil
0x1400249d3  mov     r8, r13
0x1400249d6  mov     rdx, rsi
0x1400249d9  mov     rcx, r14
0x1400249dc  call    LuafvCreateVirtualFile
0x1400249e1  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x1400249e5  mov     ebx, eax
0x1400249e7  test    rcx, rcx
0x1400249ea  jz      short loc_1400249F8
0x1400249ec  call    cs:__imp_FltClose
0x1400249f3  nop     dword ptr [rax+rax+00h]
0x1400249f8  cmp     ebx, 0C0000022h
0x1400249fe  setnz   r12b
0x140024a02  mov     rax, [rbp+40h+var_B0]
0x140024a06  mov     [rax], dil
0x140024a09  mov     rax, [rbp+40h+var_A8]
0x140024a0d  mov     [rax], r12b
0x140024a10  mov     eax, ebx
0x140024a12  mov     rcx, [rbp+40h+var_48]
0x140024a16  xor     rcx, rsp; StackCookie
0x140024a19  call    __security_check_cookie
0x140024a1e  add     rsp, 108h
0x140024a25  pop     r15
0x140024a27  pop     r14
0x140024a29  pop     r13
0x140024a2b  pop     r12
0x140024a2d  pop     rdi
0x140024a2e  pop     rsi
0x140024a2f  pop     rbx
0x140024a30  pop     rbp
0x140024a31  retn
```
