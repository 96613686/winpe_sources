# HsmiCldOpenSyncRoot

- ea: `0x140057cd8`
- end: `0x1400580ed`
- name: `HsmiCldOpenSyncRoot`
- size: `1045`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, void **, PFILE_OBJECT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140051810`
- `0x140056848`
- `0x140057b20`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14001e300`
- `0x140057cd8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140057eda`
- `ntoskrnl!ObfDereferenceObject` at `0x1400580cb`
- `ntoskrnl!ObfDereferenceObject` at `0x140057eda`
- `ntoskrnl!ObfDereferenceObject` at `0x1400580cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057f8b`
- `ntoskrnl!ExAllocatePool2` at `0x140057d50`
- `ntoskrnl!ExAllocatePool2` at `0x140057d50`
- `FLTMGR!FltCreateFileEx` at `0x140057e69`
- `FLTMGR!FltCreateFileEx` at `0x140057e69`
- `FLTMGR!FltClose` at `0x140057eee`
- `FLTMGR!FltClose` at `0x1400580dc`
- `FLTMGR!FltClose` at `0x140057eee`
- `FLTMGR!FltClose` at `0x1400580dc`
- `FLTMGR!FltQueryInformationFile` at `0x140057eb0`
- `FLTMGR!FltQueryInformationFile` at `0x140057eb0`

## pseudocode

```c
__int64 __fastcall HsmiCldOpenSyncRoot(__int64 a1, unsigned __int16 *a2, void **a3, PFILE_OBJECT *a4)
{
  unsigned __int16 v4; // ax
  unsigned __int16 v6; // cx
  struct _FLT_INSTANCE *v10; // r15
  NTSTATUS v11; // edi
  size_t v12; // r8
  const void *v13; // rdx
  unsigned __int16 v14; // dx
  bool v15; // zf
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  void *FileHandle; // [rsp+80h] [rbp-39h] BYREF
  __int64 FileInformation; // [rsp+88h] [rbp-31h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-9h] BYREF
  PFILE_OBJECT FileObject; // [rsp+128h] [rbp+6Fh] BYREF

  FileHandle = 0;
  v4 = *(_WORD *)(a1 + 64);
  FileObject = 0;
  v6 = *a2 + v4;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( v6 < v4 )
  {
    v11 = -1073741675;
    WORD1(P[0]) = -1;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_23;
    }
    v18 = 10;
LABEL_31:
    WPP_SF_qd(v17->AttachedDevice, v18, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1, v11);
    goto LABEL_19;
  }
  v10 = *(struct _FLT_INSTANCE **)(a1 + 32);
  WORD1(P[0]) = v6;
  LOWORD(P[0]) = 0;
  P[1] = (PVOID)ExAllocatePool2(256, v6, 1934979912);
  v11 = P[1] == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v11);
  if ( !P[1] )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_19;
    }
    v18 = 11;
    goto LABEL_31;
  }
  memmove(P[1], *(const void **)(a1 + 72), *(unsigned __int16 *)(a1 + 64));
  v12 = *a2;
  v13 = (const void *)*((_QWORD *)a2 + 1);
  LOWORD(P[0]) = *(_WORD *)(a1 + 64) - 2;
  memmove((char *)P[1] + LOWORD(P[0]), v13, v12);
  LOWORD(P[0]) += *a2;
  *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 0;
  v14 = (unsigned __int16)P[0];
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  while ( 1 )
  {
    if ( v14 <= *(_WORD *)(a1 + 64) )
      goto LABEL_18;
    FileInformation = 0;
    v11 = FltCreateFileEx(
            Filter,
            v10,
            &FileHandle,
            &FileObject,
            0x100080u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            7u,
            1u,
            0x200000u,
            0,
            0,
            0x800u);
    HsmDbgBreakOnStatus(v11);
    if ( v11 == -1073741772 )
    {
      v11 = 0;
      goto LABEL_10;
    }
    if ( v11 < 0 )
      break;
    v11 = FltQueryInformationFile(v10, FileObject, &FileInformation, 8u, FileAttributeTagInformation, 0);
    HsmDbgBreakOnStatus(v11);
    if ( v11 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v18 = 13;
        goto LABEL_31;
      }
      goto LABEL_19;
    }
    if ( (FileInformation & 0x100000000000LL) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1, v11);
      }
LABEL_18:
      *a4 = FileObject;
      *a3 = FileHandle;
      FileObject = 0;
      FileHandle = 0;
      goto LABEL_19;
    }
    ObfDereferenceObject(FileObject);
    FileObject = 0;
    FltClose(FileHandle);
    FileHandle = 0;
LABEL_10:
    v14 = (unsigned __int16)P[0];
    do
    {
      v15 = v14 == 2;
      v14 -= 2;
      LOWORD(P[0]) = v14;
    }
    while ( !v15 && *((_WORD *)P[1] + ((unsigned __int64)v14 >> 1) - 1) != 92 );
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v18 = 12;
    goto LABEL_31;
  }
LABEL_19:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
LABEL_23:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140057cd8  mov     [rsp-8+arg_10], rbx
0x140057cdd  push    rbp
0x140057cde  push    rsi
0x140057cdf  push    rdi
0x140057ce0  push    r12
0x140057ce2  push    r13
0x140057ce4  push    r14
0x140057ce6  push    r15
0x140057ce8  lea     rbp, [rsp-27h]
0x140057ced  sub     rsp, 0E0h
0x140057cf4  xorps   xmm0, xmm0
0x140057cf7  xor     ebx, ebx
0x140057cf9  xor     eax, eax
0x140057cfb  mov     [rbp+57h+FileHandle], rbx
0x140057cff  movzx   eax, word ptr [rcx+40h]
0x140057d03  mov     rsi, rcx
0x140057d06  movzx   ecx, ax
0x140057d09  mov     [rbp+57h+FileObject], rbx
0x140057d0d  add     cx, [rdx]
0x140057d10  mov     r12, r9
0x140057d13  mov     r13, r8
0x140057d16  mov     r14, rdx
0x140057d19  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x140057d1d  movups  xmmword ptr [rbp+57h+P], xmm0
0x140057d21  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140057d25  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x140057d29  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140057d2d  cmp     cx, ax
0x140057d30  jb      loc_140057FBC
0x140057d36  mov     r15, [rsi+20h]
0x140057d3a  mov     r8d, 73557348h
0x140057d40  mov     word ptr [rbp+57h+P+2], cx
0x140057d44  movzx   edx, cx
0x140057d47  mov     ecx, 100h
0x140057d4c  mov     word ptr [rbp+57h+P], bx
0x140057d50  call    cs:__imp_ExAllocatePool2
0x140057d57  nop     dword ptr [rax+rax+00h]
0x140057d5c  mov     rcx, rax
0x140057d5f  mov     [rbp+57h+P+8], rax
0x140057d63  neg     rcx
0x140057d66  mov     rbx, rax
0x140057d69  sbb     edi, edi
0x140057d6b  not     edi
0x140057d6d  and     edi, 0C000009Ah
0x140057d73  mov     ecx, edi
0x140057d75  call    HsmDbgBreakOnStatus
0x140057d7a  test    rbx, rbx
0x140057d7d  jz      loc_14005803E
0x140057d83  movzx   r8d, word ptr [rsi+40h]; Size
0x140057d88  mov     rdx, [rsi+48h]; Src
0x140057d8c  mov     rcx, [rbp+57h+P+8]; void *
0x140057d90  call    memmove
0x140057d95  movzx   eax, word ptr [rsi+40h]
0x140057d99  movzx   r8d, word ptr [r14]; Size
0x140057d9d  sub     ax, 2
0x140057da1  mov     rdx, [r14+8]; Src
0x140057da5  movzx   ecx, ax
0x140057da8  mov     word ptr [rbp+57h+P], cx
0x140057dac  add     rcx, [rbp+57h+P+8]; void *
0x140057db0  call    memmove
0x140057db5  movzx   eax, word ptr [rbp+57h+P]
0x140057db9  xorps   xmm0, xmm0
0x140057dbc  add     ax, [r14]
0x140057dc0  mov     r14d, 0FFFEh
0x140057dc6  movzx   edx, ax
0x140057dc9  mov     rax, [rbp+57h+P+8]
0x140057dcd  mov     word ptr [rbp+57h+P], dx
0x140057dd1  shr     rdx, 1
0x140057dd4  xor     ebx, ebx
0x140057dd6  mov     [rax+rdx*2], bx
0x140057dda  lea     rax, [rbp+57h+P]
0x140057dde  movzx   edx, word ptr [rbp+57h+P]
0x140057de2  mov     [rbp+57h+var_60.ObjectName], rax
0x140057de6  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x140057ded  mov     [rbp+57h+var_60.RootDirectory], rbx
0x140057df1  mov     [rbp+57h+var_60.Attributes], 240h
0x140057df8  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x140057dfd  cmp     dx, [rsi+40h]
0x140057e01  jbe     loc_140057F4B
0x140057e07  mov     rcx, cs:Filter; Filter
0x140057e0e  lea     rax, [rbp+57h+var_70]
0x140057e12  mov     [rsp+110h+Flags], 800h; Flags
0x140057e1a  lea     r9, [rbp+57h+FileObject]; FileObject
0x140057e1e  mov     [rsp+110h+EaLength], ebx; EaLength
0x140057e22  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140057e26  mov     [rsp+110h+EaBuffer], rbx; EaBuffer
0x140057e2b  mov     rdx, r15; Instance
0x140057e2e  mov     [rsp+110h+CreateOptions], 200000h; CreateOptions
0x140057e36  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x140057e3e  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140057e46  mov     [rsp+110h+FileAttributes], ebx; FileAttributes
0x140057e4a  mov     [rsp+110h+AllocationSize], rbx; AllocationSize
0x140057e4f  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x140057e54  lea     rax, [rbp+57h+var_60]
0x140057e58  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x140057e5d  mov     [rsp+110h+DesiredAccess], 100080h; DesiredAccess
0x140057e65  mov     [rbp+57h+FileInformation], rbx
0x140057e69  call    cs:__imp_FltCreateFileEx
0x140057e70  nop     dword ptr [rax+rax+00h]
0x140057e75  mov     ecx, eax
0x140057e77  mov     edi, eax
0x140057e79  call    HsmDbgBreakOnStatus
0x140057e7e  cmp     edi, 0C0000034h
0x140057e84  jz      loc_140057FB5
0x140057e8a  test    edi, edi
0x140057e8c  js      loc_140058095
0x140057e92  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140057e96  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140057e9a  mov     [rsp+110h+ObjectAttributes], rbx; LengthReturned
0x140057e9f  mov     r9d, 8; Length
0x140057ea5  mov     rcx, r15; Instance
0x140057ea8  mov     [rsp+110h+DesiredAccess], 23h ; '#'; FileInformationClass
0x140057eb0  call    cs:__imp_FltQueryInformationFile
0x140057eb7  nop     dword ptr [rax+rax+00h]
0x140057ebc  mov     ecx, eax
0x140057ebe  mov     edi, eax
0x140057ec0  call    HsmDbgBreakOnStatus
0x140057ec5  test    edi, edi
0x140057ec7  js      loc_14005800B
0x140057ecd  test    dword ptr [rbp+57h+FileInformation+4], 1000h
0x140057ed4  jnz     short loc_140057F27
0x140057ed6  mov     rcx, [rbp+57h+FileObject]; Object
0x140057eda  call    cs:__imp_ObfDereferenceObject
0x140057ee1  nop     dword ptr [rax+rax+00h]
0x140057ee6  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140057eea  mov     [rbp+57h+FileObject], rbx
0x140057eee  call    cs:__imp_FltClose
0x140057ef5  nop     dword ptr [rax+rax+00h]
0x140057efa  mov     [rbp+57h+FileHandle], rbx
0x140057efe  movzx   edx, word ptr [rbp+57h+P]
0x140057f02  add     dx, r14w
0x140057f06  mov     word ptr [rbp+57h+P], dx
0x140057f0a  jz      loc_140057DFD
0x140057f10  mov     rax, [rbp+57h+P+8]
0x140057f14  movzx   ecx, dx
0x140057f17  shr     rcx, 1
0x140057f1a  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140057f20  jnz     short loc_140057F02
0x140057f22  jmp     loc_140057DFD
0x140057f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f2e  lea     rax, WPP_GLOBAL_Control
0x140057f35  cmp     rcx, rax
0x140057f38  jz      short loc_140057F4B
0x140057f3a  mov     eax, [rcx+2Ch]
0x140057f3d  test    al, 1
0x140057f3f  jz      short loc_140057F4B
0x140057f41  cmp     byte ptr [rcx+29h], 5
0x140057f45  jnb     loc_140058074
0x140057f4b  mov     rax, [rbp+57h+FileObject]
0x140057f4f  mov     [r12], rax
0x140057f53  mov     rax, [rbp+57h+FileHandle]
0x140057f57  mov     [r13+0], rax
0x140057f5b  mov     [rbp+57h+FileObject], rbx
0x140057f5f  mov     [rbp+57h+FileHandle], rbx
0x140057f63  mov     rcx, [rbp+57h+FileObject]; Object
0x140057f67  test    rcx, rcx
0x140057f6a  jnz     loc_1400580CB
0x140057f70  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140057f74  test    rcx, rcx
0x140057f77  jnz     loc_1400580DC
0x140057f7d  mov     rcx, [rbp+57h+P+8]; P
0x140057f81  test    rcx, rcx
0x140057f84  jz      short loc_140057F97
0x140057f86  mov     edx, 73557348h; Tag
0x140057f8b  call    cs:__imp_ExFreePoolWithTag
0x140057f92  nop     dword ptr [rax+rax+00h]
0x140057f97  mov     rbx, [rsp+110h+arg_10]
0x140057f9f  mov     eax, edi
0x140057fa1  add     rsp, 0E0h
0x140057fa8  pop     r15
0x140057faa  pop     r14
0x140057fac  pop     r13
0x140057fae  pop     r12
0x140057fb0  pop     rdi
0x140057fb1  pop     rsi
0x140057fb2  pop     rbp
0x140057fb3  retn
0x140057fb5  mov     edi, ebx
0x140057fb7  jmp     loc_140057EFE
0x140057fbc  mov     eax, 0FFFFh
0x140057fc1  mov     edi, 0C0000095h
0x140057fc6  mov     word ptr [rbp+57h+P+2], ax
0x140057fca  mov     rcx, cs:WPP_GLOBAL_Control
0x140057fd1  lea     rax, WPP_GLOBAL_Control
0x140057fd8  cmp     rcx, rax
0x140057fdb  jz      short loc_140057F7D
0x140057fdd  mov     eax, [rcx+2Ch]
0x140057fe0  test    al, 1
0x140057fe2  jz      short loc_140057F7D
0x140057fe4  cmp     byte ptr [rcx+29h], 2
0x140057fe8  jb      short loc_140057F7D
0x140057fea  mov     edx, 0Ah
0x140057fef  mov     rcx, [rcx+18h]
0x140057ff3  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057ffa  mov     r9, rsi
0x140057ffd  mov     [rsp+110h+DesiredAccess], edi
0x140058001  call    WPP_SF_qd
0x140058006  jmp     loc_140057F63
0x14005800b  mov     rcx, cs:WPP_GLOBAL_Control
0x140058012  lea     rax, WPP_GLOBAL_Control
0x140058019  cmp     rcx, rax
0x14005801c  jz      loc_140057F63
0x140058022  mov     eax, [rcx+2Ch]
0x140058025  test    al, 1
0x140058027  jz      loc_140057F63
0x14005802d  cmp     byte ptr [rcx+29h], 2
0x140058031  jb      loc_140057F63
0x140058037  mov     edx, 0Dh
0x14005803c  jmp     short loc_140057FEF
0x14005803e  mov     rcx, cs:WPP_GLOBAL_Control
0x140058045  lea     rax, WPP_GLOBAL_Control
0x14005804c  cmp     rcx, rax
0x14005804f  jz      loc_140057F63
0x140058055  mov     eax, [rcx+2Ch]
0x140058058  test    al, 1
0x14005805a  jz      loc_140057F63
0x140058060  cmp     byte ptr [rcx+29h], 2
0x140058064  jb      loc_140057F63
0x14005806a  mov     edx, 0Bh
0x14005806f  jmp     loc_140057FEF
0x140058074  mov     rcx, [rcx+18h]
0x140058078  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005807f  mov     edx, 0Eh
0x140058084  mov     [rsp+110h+DesiredAccess], edi
0x140058088  mov     r9, rsi
0x14005808b  call    WPP_SF_qd
0x140058090  jmp     loc_140057F4B
0x140058095  mov     rcx, cs:WPP_GLOBAL_Control
0x14005809c  lea     rax, WPP_GLOBAL_Control
0x1400580a3  cmp     rcx, rax
0x1400580a6  jz      loc_140057F63
0x1400580ac  mov     eax, [rcx+2Ch]
0x1400580af  test    al, 1
0x1400580b1  jz      loc_140057F63
0x1400580b7  cmp     byte ptr [rcx+29h], 2
0x1400580bb  jb      loc_140057F63
0x1400580c1  mov     edx, 0Ch
0x1400580c6  jmp     loc_140057FEF
0x1400580cb  call    cs:__imp_ObfDereferenceObject
0x1400580d2  nop     dword ptr [rax+rax+00h]
0x1400580d7  jmp     loc_140057F70
0x1400580dc  call    cs:__imp_FltClose
0x1400580e3  nop     dword ptr [rax+rax+00h]
0x1400580e8  jmp     loc_140057F7D
```
