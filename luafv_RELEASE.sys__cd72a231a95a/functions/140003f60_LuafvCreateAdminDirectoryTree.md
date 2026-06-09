# LuafvCreateAdminDirectoryTree

- ea: `0x140003f60`
- end: `0x1400041e1`
- name: `LuafvCreateAdminDirectoryTree`
- size: `641`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003b6c`

## callees

- `0x140003f60`
- `0x140005d00`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140004153`
- `ntoskrnl!ObfDereferenceObject` at `0x140004198`
- `ntoskrnl!ObfDereferenceObject` at `0x140004153`
- `ntoskrnl!ObfDereferenceObject` at `0x140004198`
- `FLTMGR!FltClose` at `0x140004163`
- `FLTMGR!FltClose` at `0x1400041a8`
- `FLTMGR!FltClose` at `0x140004163`
- `FLTMGR!FltClose` at `0x1400041a8`
- `FLTMGR!FltCreateFileEx2` at `0x140004135`
- `FLTMGR!FltCreateFileEx2` at `0x140004135`

## pseudocode

```c
__int64 __fastcall LuafvCreateAdminDirectoryTree(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int16 v3; // bx
  __int64 v4; // rdi
  size_t v7; // rsi
  NTSTATUS v8; // r14d
  const void *v9; // rdx
  _WORD *v10; // rdi
  unsigned __int16 v11; // cx
  struct _FLT_INSTANCE *v12; // rdx
  __int128 v14; // [rsp+80h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+118h] [rbp+6Fh] BYREF
  PFILE_OBJECT FileObject; // [rsp+120h] [rbp+77h] BYREF

  v3 = *(_WORD *)a3;
  v4 = *(_QWORD *)(a3 + 8);
  FileHandle = 0;
  FileObject = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  do
  {
    if ( !v3 )
      break;
    v3 -= 2;
  }
  while ( *(_WORD *)(v4 + 2 * ((unsigned __int64)v3 >> 1)) != 92 );
  v7 = *(unsigned __int16 *)(a2 + 120);
  if ( v3 > (unsigned __int16)v7 )
  {
    LOBYTE(a3) = 2;
    WORD1(v14) = v3 + 2;
    *((_QWORD *)&v14 + 1) = LuafvAllocatePool(1, (unsigned __int16)(v3 + 2), a3);
    if ( *((_QWORD *)&v14 + 1) )
    {
      v9 = *(const void **)(a2 + 128);
      LOWORD(v14) = v7;
      v10 = (_WORD *)(v4 + 2 * (v7 >> 1));
      memmove(*((void **)&v14 + 1), v9, v7);
      while ( 1 )
      {
        v3 -= v7;
        if ( !v3 )
          break;
        if ( *v10 == 92 )
        {
          *(_WORD *)(*((_QWORD *)&v14 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v14 >> 1)) = 92;
          v11 = v14 + 2;
          LOWORD(v14) = v14 + 2;
          v3 -= 2;
          if ( !v3 )
            break;
          ++v10;
        }
        else
        {
          v11 = v14;
        }
        LOWORD(v7) = 0;
        do
        {
          if ( v10[(unsigned __int64)(unsigned __int16)v7 >> 1] == 92 )
            break;
          LOWORD(v7) = v7 + 2;
        }
        while ( (unsigned __int16)v7 < v3 );
        memmove((void *)(*((_QWORD *)&v14 + 1) + 2 * ((unsigned __int64)v11 >> 1)), v10, (unsigned __int16)v7);
        v12 = *(struct _FLT_INSTANCE **)(a1 + 24);
        LOWORD(v14) = v7 + v14;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v8 = FltCreateFileEx2(
               LuafvDriverData,
               v12,
               &FileHandle,
               &FileObject,
               0x100001u,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0x10u,
               7u,
               3u,
               0x21u,
               0,
               0,
               0x100u,
               0);
        if ( v8 < 0 )
          goto LABEL_20;
        v10 += (unsigned __int64)(unsigned __int16)v7 >> 1;
        ObfDereferenceObject(FileObject);
        FltClose(FileHandle);
        FileHandle = 0;
        FileObject = 0;
      }
      v8 = 0;
    }
    else
    {
      v8 = -1073741670;
    }
LABEL_20:
    if ( FileHandle )
    {
      if ( FileObject )
        ObfDereferenceObject(FileObject);
      FltClose(FileHandle);
    }
  }
  else
  {
    v8 = 0;
  }
  if ( *((_QWORD *)&v14 + 1) )
    LuafvFreePool(*((_QWORD *)&v14 + 1));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140003f60  mov     [rsp-8+arg_0], rbx
0x140003f65  push    rbp
0x140003f66  push    rsi
0x140003f67  push    rdi
0x140003f68  push    r12
0x140003f6a  push    r13
0x140003f6c  push    r14
0x140003f6e  push    r15
0x140003f70  lea     rbp, [rsp-27h]
0x140003f75  sub     rsp, 0D0h
0x140003f7c  movzx   ebx, word ptr [r8]
0x140003f80  xorps   xmm0, xmm0
0x140003f83  mov     rdi, [r8+8]
0x140003f87  xor     eax, eax
0x140003f89  xor     r12d, r12d
0x140003f8c  mov     r13, rcx
0x140003f8f  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x140003f93  mov     r14, rdx
0x140003f96  mov     [rbp+57h+FileHandle], r12
0x140003f9a  lea     ecx, [rax+5Ch]
0x140003f9d  mov     [rbp+57h+FileObject], r12
0x140003fa1  movups  [rbp+57h+var_80], xmm0
0x140003fa5  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140003fa9  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x140003fad  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140003fb1  jmp     short loc_140003FC7
0x140003fb3  mov     eax, 0FFFEh
0x140003fb8  add     bx, ax
0x140003fbb  movzx   eax, bx
0x140003fbe  shr     rax, 1
0x140003fc1  cmp     [rdi+rax*2], cx
0x140003fc5  jz      short loc_140003FCC
0x140003fc7  test    bx, bx
0x140003fca  jnz     short loc_140003FB3
0x140003fcc  movzx   esi, word ptr [rdx+78h]
0x140003fd0  cmp     bx, si
0x140003fd3  ja      short loc_140003FDD
0x140003fd5  mov     r14d, r12d
0x140003fd8  jmp     loc_1400041B4
0x140003fdd  mov     r15d, 2
0x140003fe3  mov     r8b, r15b
0x140003fe6  lea     eax, [r15+rbx]
0x140003fea  movzx   edx, ax
0x140003fed  lea     ecx, [r15-1]
0x140003ff1  mov     word ptr [rbp+57h+var_80+2], dx
0x140003ff5  call    LuafvAllocatePool
0x140003ffa  mov     qword ptr [rbp+57h+var_80+8], rax
0x140003ffe  mov     rcx, rax; void *
0x140004001  test    rax, rax
0x140004004  jnz     short loc_140004011
0x140004006  mov     r14d, 0C000009Ah
0x14000400c  jmp     loc_140004189
0x140004011  mov     rdx, [r14+80h]; Src
0x140004018  mov     rax, rsi
0x14000401b  shr     rax, 1
0x14000401e  mov     r8, rsi; Size
0x140004021  mov     word ptr [rbp+57h+var_80], si
0x140004025  lea     rdi, [rdi+rax*2]
0x140004029  call    memmove
0x14000402e  jmp     loc_14000417D
0x140004033  mov     edx, 5Ch ; '\'
0x140004038  cmp     [rdi], dx
0x14000403b  jnz     short loc_140004067
0x14000403d  movzx   ecx, word ptr [rbp+57h+var_80]
0x140004041  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140004045  shr     rcx, 1
0x140004048  mov     [rax+rcx*2], dx
0x14000404c  movzx   ecx, word ptr [rbp+57h+var_80]
0x140004050  add     cx, r15w
0x140004054  mov     word ptr [rbp+57h+var_80], cx
0x140004058  sub     bx, r15w
0x14000405c  jz      loc_140004186
0x140004062  add     rdi, r15
0x140004065  jmp     short loc_14000406B
0x140004067  movzx   ecx, word ptr [rbp+57h+var_80]
0x14000406b  mov     esi, r12d
0x14000406e  cmp     r12w, bx
0x140004072  jnb     short loc_140004089
0x140004074  movzx   eax, si
0x140004077  shr     rax, 1
0x14000407a  cmp     [rdi+rax*2], dx
0x14000407e  jz      short loc_140004089
0x140004080  add     si, r15w
0x140004084  cmp     si, bx
0x140004087  jb      short loc_140004074
0x140004089  mov     rax, qword ptr [rbp+57h+var_80+8]
0x14000408d  mov     rdx, rdi; Src
0x140004090  movzx   ecx, cx
0x140004093  shr     rcx, 1
0x140004096  movzx   r15d, si
0x14000409a  mov     r8d, r15d; Size
0x14000409d  lea     rcx, [rax+rcx*2]; void *
0x1400040a1  call    memmove
0x1400040a6  mov     rdx, [r13+18h]; Instance
0x1400040aa  lea     rax, [rbp+57h+var_80]
0x1400040ae  mov     rcx, cs:LuafvDriverData; Filter
0x1400040b5  lea     r9, [rbp+57h+FileObject]; FileObject
0x1400040b9  add     word ptr [rbp+57h+var_80], si
0x1400040bd  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x1400040c1  mov     [rsp+100h+DriverContext], r12; DriverContext
0x1400040c6  xorps   xmm0, xmm0
0x1400040c9  mov     [rsp+100h+Flags], 100h; Flags
0x1400040d1  mov     [rsp+100h+EaLength], r12d; EaLength
0x1400040d6  mov     [rsp+100h+EaBuffer], r12; EaBuffer
0x1400040db  mov     [rsp+100h+CreateOptions], 21h ; '!'; CreateOptions
0x1400040e3  mov     [rsp+100h+CreateDisposition], 3; CreateDisposition
0x1400040eb  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x1400040f3  mov     [rsp+100h+FileAttributes], 10h; FileAttributes
0x1400040fb  mov     [rbp+57h+var_60.ObjectName], rax
0x1400040ff  lea     rax, [rbp+57h+var_70]
0x140004103  mov     [rsp+100h+AllocationSize], r12; AllocationSize
0x140004108  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x14000410d  lea     rax, [rbp+57h+var_60]
0x140004111  mov     [rsp+100h+ObjectAttributes], rax; ObjectAttributes
0x140004116  mov     [rsp+100h+DesiredAccess], 100001h; DesiredAccess
0x14000411e  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x140004125  mov     [rbp+57h+var_60.RootDirectory], r12
0x140004129  mov     [rbp+57h+var_60.Attributes], 240h
0x140004130  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x140004135  call    cs:__imp_FltCreateFileEx2
0x14000413c  nop     dword ptr [rax+rax+00h]
0x140004141  mov     r14d, eax
0x140004144  test    eax, eax
0x140004146  js      short loc_140004189
0x140004148  mov     rcx, [rbp+57h+FileObject]; Object
0x14000414c  shr     r15, 1
0x14000414f  lea     rdi, [rdi+r15*2]
0x140004153  call    cs:__imp_ObfDereferenceObject
0x14000415a  nop     dword ptr [rax+rax+00h]
0x14000415f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140004163  call    cs:__imp_FltClose
0x14000416a  nop     dword ptr [rax+rax+00h]
0x14000416f  mov     [rbp+57h+FileHandle], r12
0x140004173  mov     r15d, 2
0x140004179  mov     [rbp+57h+FileObject], r12
0x14000417d  sub     bx, si
0x140004180  jnz     loc_140004033
0x140004186  mov     r14d, r12d
0x140004189  cmp     [rbp+57h+FileHandle], r12
0x14000418d  jz      short loc_1400041B4
0x14000418f  mov     rcx, [rbp+57h+FileObject]; Object
0x140004193  test    rcx, rcx
0x140004196  jz      short loc_1400041A4
0x140004198  call    cs:__imp_ObfDereferenceObject
0x14000419f  nop     dword ptr [rax+rax+00h]
0x1400041a4  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400041a8  call    cs:__imp_FltClose
0x1400041af  nop     dword ptr [rax+rax+00h]
0x1400041b4  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1400041b8  test    rcx, rcx
0x1400041bb  jz      short loc_1400041C2
0x1400041bd  call    LuafvFreePool
0x1400041c2  mov     rbx, [rsp+100h+arg_0]
0x1400041ca  mov     eax, r14d
0x1400041cd  add     rsp, 0D0h
0x1400041d4  pop     r15
0x1400041d6  pop     r14
0x1400041d8  pop     r13
0x1400041da  pop     r12
0x1400041dc  pop     rdi
0x1400041dd  pop     rsi
0x1400041de  pop     rbp
0x1400041df  retn
```
