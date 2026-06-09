# LuafvCreateAdminDirectoryTree

- ea: `0x140003d30`
- end: `0x140003fb1`
- name: `LuafvCreateAdminDirectoryTree`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000393c`

## callees

- `0x140003d30`
- `0x140006080`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140003f23`
- `ntoskrnl!ObfDereferenceObject` at `0x140003f68`
- `ntoskrnl!ObfDereferenceObject` at `0x140003f23`
- `ntoskrnl!ObfDereferenceObject` at `0x140003f68`
- `FLTMGR!FltClose` at `0x140003f33`
- `FLTMGR!FltClose` at `0x140003f78`
- `FLTMGR!FltClose` at `0x140003f33`
- `FLTMGR!FltClose` at `0x140003f78`
- `FLTMGR!FltCreateFileEx2` at `0x140003f05`
- `FLTMGR!FltCreateFileEx2` at `0x140003f05`

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
    WORD1(v14) = v3 + 2;
    *((_QWORD *)&v14 + 1) = LuafvAllocatePool(1, (unsigned __int16)(v3 + 2), 2);
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
0x140003d30  mov     [rsp-8+arg_0], rbx
0x140003d35  push    rbp
0x140003d36  push    rsi
0x140003d37  push    rdi
0x140003d38  push    r12
0x140003d3a  push    r13
0x140003d3c  push    r14
0x140003d3e  push    r15
0x140003d40  lea     rbp, [rsp-27h]
0x140003d45  sub     rsp, 0D0h
0x140003d4c  movzx   ebx, word ptr [r8]
0x140003d50  xorps   xmm0, xmm0
0x140003d53  mov     rdi, [r8+8]
0x140003d57  xor     eax, eax
0x140003d59  xor     r12d, r12d
0x140003d5c  mov     r13, rcx
0x140003d5f  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x140003d63  mov     r14, rdx
0x140003d66  mov     [rbp+57h+FileHandle], r12
0x140003d6a  lea     ecx, [rax+5Ch]
0x140003d6d  mov     [rbp+57h+FileObject], r12
0x140003d71  movups  [rbp+57h+var_80], xmm0
0x140003d75  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140003d79  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x140003d7d  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140003d81  jmp     short loc_140003D97
0x140003d83  mov     eax, 0FFFEh
0x140003d88  add     bx, ax
0x140003d8b  movzx   eax, bx
0x140003d8e  shr     rax, 1
0x140003d91  cmp     [rdi+rax*2], cx
0x140003d95  jz      short loc_140003D9C
0x140003d97  test    bx, bx
0x140003d9a  jnz     short loc_140003D83
0x140003d9c  movzx   esi, word ptr [rdx+78h]
0x140003da0  cmp     bx, si
0x140003da3  ja      short loc_140003DAD
0x140003da5  mov     r14d, r12d
0x140003da8  jmp     loc_140003F84
0x140003dad  mov     r15d, 2
0x140003db3  mov     r8b, r15b
0x140003db6  lea     eax, [r15+rbx]
0x140003dba  movzx   edx, ax
0x140003dbd  lea     ecx, [r15-1]
0x140003dc1  mov     word ptr [rbp+57h+var_80+2], dx
0x140003dc5  call    LuafvAllocatePool
0x140003dca  mov     qword ptr [rbp+57h+var_80+8], rax
0x140003dce  mov     rcx, rax; void *
0x140003dd1  test    rax, rax
0x140003dd4  jnz     short loc_140003DE1
0x140003dd6  mov     r14d, 0C000009Ah
0x140003ddc  jmp     loc_140003F59
0x140003de1  mov     rdx, [r14+80h]; Src
0x140003de8  mov     rax, rsi
0x140003deb  shr     rax, 1
0x140003dee  mov     r8, rsi; Size
0x140003df1  mov     word ptr [rbp+57h+var_80], si
0x140003df5  lea     rdi, [rdi+rax*2]
0x140003df9  call    memmove
0x140003dfe  jmp     loc_140003F4D
0x140003e03  mov     edx, 5Ch ; '\'
0x140003e08  cmp     [rdi], dx
0x140003e0b  jnz     short loc_140003E37
0x140003e0d  movzx   ecx, word ptr [rbp+57h+var_80]
0x140003e11  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140003e15  shr     rcx, 1
0x140003e18  mov     [rax+rcx*2], dx
0x140003e1c  movzx   ecx, word ptr [rbp+57h+var_80]
0x140003e20  add     cx, r15w
0x140003e24  mov     word ptr [rbp+57h+var_80], cx
0x140003e28  sub     bx, r15w
0x140003e2c  jz      loc_140003F56
0x140003e32  add     rdi, r15
0x140003e35  jmp     short loc_140003E3B
0x140003e37  movzx   ecx, word ptr [rbp+57h+var_80]
0x140003e3b  mov     esi, r12d
0x140003e3e  cmp     r12w, bx
0x140003e42  jnb     short loc_140003E59
0x140003e44  movzx   eax, si
0x140003e47  shr     rax, 1
0x140003e4a  cmp     [rdi+rax*2], dx
0x140003e4e  jz      short loc_140003E59
0x140003e50  add     si, r15w
0x140003e54  cmp     si, bx
0x140003e57  jb      short loc_140003E44
0x140003e59  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140003e5d  mov     rdx, rdi; Src
0x140003e60  movzx   ecx, cx
0x140003e63  shr     rcx, 1
0x140003e66  movzx   r15d, si
0x140003e6a  mov     r8d, r15d; Size
0x140003e6d  lea     rcx, [rax+rcx*2]; void *
0x140003e71  call    memmove
0x140003e76  mov     rdx, [r13+18h]; Instance
0x140003e7a  lea     rax, [rbp+57h+var_80]
0x140003e7e  mov     rcx, cs:LuafvDriverData; Filter
0x140003e85  lea     r9, [rbp+57h+FileObject]; FileObject
0x140003e89  add     word ptr [rbp+57h+var_80], si
0x140003e8d  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140003e91  mov     [rsp+100h+DriverContext], r12; DriverContext
0x140003e96  xorps   xmm0, xmm0
0x140003e99  mov     [rsp+100h+Flags], 100h; Flags
0x140003ea1  mov     [rsp+100h+EaLength], r12d; EaLength
0x140003ea6  mov     [rsp+100h+EaBuffer], r12; EaBuffer
0x140003eab  mov     [rsp+100h+CreateOptions], 21h ; '!'; CreateOptions
0x140003eb3  mov     [rsp+100h+CreateDisposition], 3; CreateDisposition
0x140003ebb  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x140003ec3  mov     [rsp+100h+FileAttributes], 10h; FileAttributes
0x140003ecb  mov     [rbp+57h+var_60.ObjectName], rax
0x140003ecf  lea     rax, [rbp+57h+var_70]
0x140003ed3  mov     [rsp+100h+AllocationSize], r12; AllocationSize
0x140003ed8  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x140003edd  lea     rax, [rbp+57h+var_60]
0x140003ee1  mov     [rsp+100h+ObjectAttributes], rax; ObjectAttributes
0x140003ee6  mov     [rsp+100h+DesiredAccess], 100001h; DesiredAccess
0x140003eee  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x140003ef5  mov     [rbp+57h+var_60.RootDirectory], r12
0x140003ef9  mov     [rbp+57h+var_60.Attributes], 240h
0x140003f00  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x140003f05  call    cs:__imp_FltCreateFileEx2
0x140003f0c  nop     dword ptr [rax+rax+00h]
0x140003f11  mov     r14d, eax
0x140003f14  test    eax, eax
0x140003f16  js      short loc_140003F59
0x140003f18  mov     rcx, [rbp+57h+FileObject]; Object
0x140003f1c  shr     r15, 1
0x140003f1f  lea     rdi, [rdi+r15*2]
0x140003f23  call    cs:__imp_ObfDereferenceObject
0x140003f2a  nop     dword ptr [rax+rax+00h]
0x140003f2f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140003f33  call    cs:__imp_FltClose
0x140003f3a  nop     dword ptr [rax+rax+00h]
0x140003f3f  mov     [rbp+57h+FileHandle], r12
0x140003f43  mov     r15d, 2
0x140003f49  mov     [rbp+57h+FileObject], r12
0x140003f4d  sub     bx, si
0x140003f50  jnz     loc_140003E03
0x140003f56  mov     r14d, r12d
0x140003f59  cmp     [rbp+57h+FileHandle], r12
0x140003f5d  jz      short loc_140003F84
0x140003f5f  mov     rcx, [rbp+57h+FileObject]; Object
0x140003f63  test    rcx, rcx
0x140003f66  jz      short loc_140003F74
0x140003f68  call    cs:__imp_ObfDereferenceObject
0x140003f6f  nop     dword ptr [rax+rax+00h]
0x140003f74  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140003f78  call    cs:__imp_FltClose
0x140003f7f  nop     dword ptr [rax+rax+00h]
0x140003f84  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x140003f88  test    rcx, rcx
0x140003f8b  jz      short loc_140003F92
0x140003f8d  call    LuafvFreePool
0x140003f92  mov     rbx, [rsp+100h+arg_0]
0x140003f9a  mov     eax, r14d
0x140003f9d  add     rsp, 0D0h
0x140003fa4  pop     r15
0x140003fa6  pop     r14
0x140003fa8  pop     r13
0x140003faa  pop     r12
0x140003fac  pop     rdi
0x140003fad  pop     rsi
0x140003fae  pop     rbp
0x140003faf  retn
```
