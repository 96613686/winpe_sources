# HsmiCldOpenSyncRoot

- ea: `0x140057bb8`
- end: `0x140057fcd`
- name: `HsmiCldOpenSyncRoot`
- size: `1045`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400516f0`
- `0x140056728`
- `0x140057a00`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14001e280`
- `0x140057bb8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140057dba`
- `ntoskrnl!ObfDereferenceObject` at `0x140057fab`
- `ntoskrnl!ObfDereferenceObject` at `0x140057dba`
- `ntoskrnl!ObfDereferenceObject` at `0x140057fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057e6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057e6b`
- `ntoskrnl!ExAllocatePool2` at `0x140057c30`
- `ntoskrnl!ExAllocatePool2` at `0x140057c30`
- `FLTMGR!FltCreateFileEx` at `0x140057d49`
- `FLTMGR!FltCreateFileEx` at `0x140057d49`
- `FLTMGR!FltClose` at `0x140057dce`
- `FLTMGR!FltClose` at `0x140057fbc`
- `FLTMGR!FltClose` at `0x140057dce`
- `FLTMGR!FltClose` at `0x140057fbc`
- `FLTMGR!FltQueryInformationFile` at `0x140057d90`
- `FLTMGR!FltQueryInformationFile` at `0x140057d90`

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
  __int64 DesiredAccess; // [rsp+20h] [rbp-99h]
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
    LODWORD(DesiredAccess) = v11;
    WPP_SF_qd(v17->AttachedDevice, v18, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1, DesiredAccess);
    goto LABEL_19;
  }
  v10 = *(struct _FLT_INSTANCE **)(a1 + 32);
  WORD1(P[0]) = v6;
  LOWORD(P[0]) = 0;
  P[1] = (PVOID)ExAllocatePool2(256, v6, 1934979912);
  v11 = P[1] == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus((unsigned int)v11);
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
    HsmDbgBreakOnStatus((unsigned int)v11);
    if ( v11 == -1073741772 )
    {
      v11 = 0;
      goto LABEL_10;
    }
    if ( v11 < 0 )
      break;
    v11 = FltQueryInformationFile(v10, FileObject, &FileInformation, 8u, FileAttributeTagInformation, 0);
    HsmDbgBreakOnStatus((unsigned int)v11);
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
        LODWORD(DesiredAccess) = v11;
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
          a1,
          DesiredAccess);
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
0x140057bb8  mov     [rsp-8+arg_10], rbx
0x140057bbd  push    rbp
0x140057bbe  push    rsi
0x140057bbf  push    rdi
0x140057bc0  push    r12
0x140057bc2  push    r13
0x140057bc4  push    r14
0x140057bc6  push    r15
0x140057bc8  lea     rbp, [rsp-27h]
0x140057bcd  sub     rsp, 0E0h
0x140057bd4  xorps   xmm0, xmm0
0x140057bd7  xor     ebx, ebx
0x140057bd9  xor     eax, eax
0x140057bdb  mov     [rbp+57h+FileHandle], rbx
0x140057bdf  movzx   eax, word ptr [rcx+40h]
0x140057be3  mov     rsi, rcx
0x140057be6  movzx   ecx, ax
0x140057be9  mov     [rbp+57h+FileObject], rbx
0x140057bed  add     cx, [rdx]
0x140057bf0  mov     r12, r9
0x140057bf3  mov     r13, r8
0x140057bf6  mov     r14, rdx
0x140057bf9  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x140057bfd  movups  xmmword ptr [rbp+57h+P], xmm0
0x140057c01  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140057c05  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x140057c09  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140057c0d  cmp     cx, ax
0x140057c10  jb      loc_140057E9C
0x140057c16  mov     r15, [rsi+20h]
0x140057c1a  mov     r8d, 73557348h
0x140057c20  mov     word ptr [rbp+57h+P+2], cx
0x140057c24  movzx   edx, cx
0x140057c27  mov     ecx, 100h
0x140057c2c  mov     word ptr [rbp+57h+P], bx
0x140057c30  call    cs:__imp_ExAllocatePool2
0x140057c37  nop     dword ptr [rax+rax+00h]
0x140057c3c  mov     rcx, rax
0x140057c3f  mov     [rbp+57h+P+8], rax
0x140057c43  neg     rcx
0x140057c46  mov     rbx, rax
0x140057c49  sbb     edi, edi
0x140057c4b  not     edi
0x140057c4d  and     edi, 0C000009Ah
0x140057c53  mov     ecx, edi
0x140057c55  call    HsmDbgBreakOnStatus
0x140057c5a  test    rbx, rbx
0x140057c5d  jz      loc_140057F1E
0x140057c63  movzx   r8d, word ptr [rsi+40h]; Size
0x140057c68  mov     rdx, [rsi+48h]; Src
0x140057c6c  mov     rcx, [rbp+57h+P+8]; void *
0x140057c70  call    memmove
0x140057c75  movzx   eax, word ptr [rsi+40h]
0x140057c79  movzx   r8d, word ptr [r14]; Size
0x140057c7d  sub     ax, 2
0x140057c81  mov     rdx, [r14+8]; Src
0x140057c85  movzx   ecx, ax
0x140057c88  mov     word ptr [rbp+57h+P], cx
0x140057c8c  add     rcx, [rbp+57h+P+8]; void *
0x140057c90  call    memmove
0x140057c95  movzx   eax, word ptr [rbp+57h+P]
0x140057c99  xorps   xmm0, xmm0
0x140057c9c  add     ax, [r14]
0x140057ca0  mov     r14d, 0FFFEh
0x140057ca6  movzx   edx, ax
0x140057ca9  mov     rax, [rbp+57h+P+8]
0x140057cad  mov     word ptr [rbp+57h+P], dx
0x140057cb1  shr     rdx, 1
0x140057cb4  xor     ebx, ebx
0x140057cb6  mov     [rax+rdx*2], bx
0x140057cba  lea     rax, [rbp+57h+P]
0x140057cbe  movzx   edx, word ptr [rbp+57h+P]
0x140057cc2  mov     [rbp+57h+var_60.ObjectName], rax
0x140057cc6  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x140057ccd  mov     [rbp+57h+var_60.RootDirectory], rbx
0x140057cd1  mov     [rbp+57h+var_60.Attributes], 240h
0x140057cd8  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x140057cdd  cmp     dx, [rsi+40h]
0x140057ce1  jbe     loc_140057E2B
0x140057ce7  mov     rcx, cs:Filter; Filter
0x140057cee  lea     rax, [rbp+57h+var_70]
0x140057cf2  mov     [rsp+110h+Flags], 800h; Flags
0x140057cfa  lea     r9, [rbp+57h+FileObject]; FileObject
0x140057cfe  mov     [rsp+110h+EaLength], ebx; EaLength
0x140057d02  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140057d06  mov     [rsp+110h+EaBuffer], rbx; EaBuffer
0x140057d0b  mov     rdx, r15; Instance
0x140057d0e  mov     [rsp+110h+CreateOptions], 200000h; CreateOptions
0x140057d16  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x140057d1e  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140057d26  mov     [rsp+110h+FileAttributes], ebx; FileAttributes
0x140057d2a  mov     [rsp+110h+AllocationSize], rbx; AllocationSize
0x140057d2f  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x140057d34  lea     rax, [rbp+57h+var_60]
0x140057d38  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x140057d3d  mov     dword ptr [rsp+110h+DesiredAccess], 100080h; DesiredAccess
0x140057d45  mov     [rbp+57h+FileInformation], rbx
0x140057d49  call    cs:__imp_FltCreateFileEx
0x140057d50  nop     dword ptr [rax+rax+00h]
0x140057d55  mov     ecx, eax
0x140057d57  mov     edi, eax
0x140057d59  call    HsmDbgBreakOnStatus
0x140057d5e  cmp     edi, 0C0000034h
0x140057d64  jz      loc_140057E95
0x140057d6a  test    edi, edi
0x140057d6c  js      loc_140057F75
0x140057d72  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140057d76  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140057d7a  mov     [rsp+110h+ObjectAttributes], rbx; LengthReturned
0x140057d7f  mov     r9d, 8; Length
0x140057d85  mov     rcx, r15; Instance
0x140057d88  mov     dword ptr [rsp+110h+DesiredAccess], 23h ; '#'; FileInformationClass
0x140057d90  call    cs:__imp_FltQueryInformationFile
0x140057d97  nop     dword ptr [rax+rax+00h]
0x140057d9c  mov     ecx, eax
0x140057d9e  mov     edi, eax
0x140057da0  call    HsmDbgBreakOnStatus
0x140057da5  test    edi, edi
0x140057da7  js      loc_140057EEB
0x140057dad  test    dword ptr [rbp+57h+FileInformation+4], 1000h
0x140057db4  jnz     short loc_140057E07
0x140057db6  mov     rcx, [rbp+57h+FileObject]; Object
0x140057dba  call    cs:__imp_ObfDereferenceObject
0x140057dc1  nop     dword ptr [rax+rax+00h]
0x140057dc6  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140057dca  mov     [rbp+57h+FileObject], rbx
0x140057dce  call    cs:__imp_FltClose
0x140057dd5  nop     dword ptr [rax+rax+00h]
0x140057dda  mov     [rbp+57h+FileHandle], rbx
0x140057dde  movzx   edx, word ptr [rbp+57h+P]
0x140057de2  add     dx, r14w
0x140057de6  mov     word ptr [rbp+57h+P], dx
0x140057dea  jz      loc_140057CDD
0x140057df0  mov     rax, [rbp+57h+P+8]
0x140057df4  movzx   ecx, dx
0x140057df7  shr     rcx, 1
0x140057dfa  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140057e00  jnz     short loc_140057DE2
0x140057e02  jmp     loc_140057CDD
0x140057e07  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e0e  lea     rax, WPP_GLOBAL_Control
0x140057e15  cmp     rcx, rax
0x140057e18  jz      short loc_140057E2B
0x140057e1a  mov     eax, [rcx+2Ch]
0x140057e1d  test    al, 1
0x140057e1f  jz      short loc_140057E2B
0x140057e21  cmp     byte ptr [rcx+29h], 5
0x140057e25  jnb     loc_140057F54
0x140057e2b  mov     rax, [rbp+57h+FileObject]
0x140057e2f  mov     [r12], rax
0x140057e33  mov     rax, [rbp+57h+FileHandle]
0x140057e37  mov     [r13+0], rax
0x140057e3b  mov     [rbp+57h+FileObject], rbx
0x140057e3f  mov     [rbp+57h+FileHandle], rbx
0x140057e43  mov     rcx, [rbp+57h+FileObject]; Object
0x140057e47  test    rcx, rcx
0x140057e4a  jnz     loc_140057FAB
0x140057e50  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140057e54  test    rcx, rcx
0x140057e57  jnz     loc_140057FBC
0x140057e5d  mov     rcx, [rbp+57h+P+8]; P
0x140057e61  test    rcx, rcx
0x140057e64  jz      short loc_140057E77
0x140057e66  mov     edx, 73557348h; Tag
0x140057e6b  call    cs:__imp_ExFreePoolWithTag
0x140057e72  nop     dword ptr [rax+rax+00h]
0x140057e77  mov     rbx, [rsp+110h+arg_10]
0x140057e7f  mov     eax, edi
0x140057e81  add     rsp, 0E0h
0x140057e88  pop     r15
0x140057e8a  pop     r14
0x140057e8c  pop     r13
0x140057e8e  pop     r12
0x140057e90  pop     rdi
0x140057e91  pop     rsi
0x140057e92  pop     rbp
0x140057e93  retn
0x140057e95  mov     edi, ebx
0x140057e97  jmp     loc_140057DDE
0x140057e9c  mov     eax, 0FFFFh
0x140057ea1  mov     edi, 0C0000095h
0x140057ea6  mov     word ptr [rbp+57h+P+2], ax
0x140057eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140057eb1  lea     rax, WPP_GLOBAL_Control
0x140057eb8  cmp     rcx, rax
0x140057ebb  jz      short loc_140057E5D
0x140057ebd  mov     eax, [rcx+2Ch]
0x140057ec0  test    al, 1
0x140057ec2  jz      short loc_140057E5D
0x140057ec4  cmp     byte ptr [rcx+29h], 2
0x140057ec8  jb      short loc_140057E5D
0x140057eca  mov     edx, 0Ah
0x140057ecf  mov     rcx, [rcx+18h]
0x140057ed3  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057eda  mov     r9, rsi
0x140057edd  mov     dword ptr [rsp+110h+DesiredAccess], edi
0x140057ee1  call    WPP_SF_qd
0x140057ee6  jmp     loc_140057E43
0x140057eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ef2  lea     rax, WPP_GLOBAL_Control
0x140057ef9  cmp     rcx, rax
0x140057efc  jz      loc_140057E43
0x140057f02  mov     eax, [rcx+2Ch]
0x140057f05  test    al, 1
0x140057f07  jz      loc_140057E43
0x140057f0d  cmp     byte ptr [rcx+29h], 2
0x140057f11  jb      loc_140057E43
0x140057f17  mov     edx, 0Dh
0x140057f1c  jmp     short loc_140057ECF
0x140057f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f25  lea     rax, WPP_GLOBAL_Control
0x140057f2c  cmp     rcx, rax
0x140057f2f  jz      loc_140057E43
0x140057f35  mov     eax, [rcx+2Ch]
0x140057f38  test    al, 1
0x140057f3a  jz      loc_140057E43
0x140057f40  cmp     byte ptr [rcx+29h], 2
0x140057f44  jb      loc_140057E43
0x140057f4a  mov     edx, 0Bh
0x140057f4f  jmp     loc_140057ECF
0x140057f54  mov     rcx, [rcx+18h]
0x140057f58  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140057f5f  mov     edx, 0Eh
0x140057f64  mov     dword ptr [rsp+110h+DesiredAccess], edi
0x140057f68  mov     r9, rsi
0x140057f6b  call    WPP_SF_qd
0x140057f70  jmp     loc_140057E2B
0x140057f75  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f7c  lea     rax, WPP_GLOBAL_Control
0x140057f83  cmp     rcx, rax
0x140057f86  jz      loc_140057E43
0x140057f8c  mov     eax, [rcx+2Ch]
0x140057f8f  test    al, 1
0x140057f91  jz      loc_140057E43
0x140057f97  cmp     byte ptr [rcx+29h], 2
0x140057f9b  jb      loc_140057E43
0x140057fa1  mov     edx, 0Ch
0x140057fa6  jmp     loc_140057ECF
0x140057fab  call    cs:__imp_ObfDereferenceObject
0x140057fb2  nop     dword ptr [rax+rax+00h]
0x140057fb7  jmp     loc_140057E50
0x140057fbc  call    cs:__imp_FltClose
0x140057fc3  nop     dword ptr [rax+rax+00h]
0x140057fc8  jmp     loc_140057E5D
```
