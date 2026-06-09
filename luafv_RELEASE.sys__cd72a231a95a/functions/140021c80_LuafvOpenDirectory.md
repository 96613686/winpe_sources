# LuafvOpenDirectory

- ea: `0x140021c80`
- end: `0x140021e3a`
- name: `LuafvOpenDirectory`
- size: `442`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _UNICODE_STRING *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140014df0`

## callees

- `0x140006000`
- `0x140021c80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140021da1`
- `ntoskrnl!ExAllocatePool2` at `0x140021da1`
- `FLTMGR!FltReleasePushLockEx` at `0x140021ddf`
- `FLTMGR!FltReleasePushLockEx` at `0x140021ddf`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021dc4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021dc4`
- `FLTMGR!FltClose` at `0x140021d76`
- `FLTMGR!FltClose` at `0x140021d76`
- `FLTMGR!FltCreateFileEx2` at `0x140021d3f`
- `FLTMGR!FltCreateFileEx2` at `0x140021d3f`

## pseudocode

```c
__int64 __fastcall LuafvOpenDirectory(PFLT_INSTANCE Instance, struct _UNICODE_STRING *a2, __int64 a3, unsigned int a4)
{
  NTSTATUS v6; // esi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 Pool2; // rax
  __int64 v10; // r14
  void *v11; // r14
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+77h] BYREF

  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  if ( *(_QWORD *)a3 )
  {
    return 0;
  }
  else
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = FltCreateFileEx2(
           LuafvDriverData,
           Instance,
           &FileHandle,
           0,
           0x100001u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0x80u,
           7u,
           1u,
           0x20u,
           0,
           0,
           0x101u,
           0);
    if ( v6 >= 0 )
    {
      if ( a4 > 0xFFF )
      {
        v7 = 4096;
        v8 = 4104;
      }
      else
      {
        v7 = 654;
        if ( a4 >= 0x28E )
          v7 = a4;
        v8 = v7 + 8;
      }
      Pool2 = ExAllocatePool2(256, v8, 1717663052);
      v10 = Pool2;
      if ( Pool2
        && (*(_DWORD *)Pool2 = v7,
            *(_BYTE *)(Pool2 + 4) = -1,
            FltAcquirePushLockExclusiveEx(&PoolLock, 0),
            dword_14000ECBC += v7,
            FltReleasePushLockEx(&PoolLock, 0),
            (v11 = (void *)(v10 + 8)) != 0) )
      {
        memset(v11, 0, v7);
        *(_QWORD *)a3 = FileHandle;
        *(_DWORD *)(a3 + 12) = v7;
        *(_QWORD *)(a3 + 16) = v11;
        *(_QWORD *)(a3 + 24) = 0;
        *(_DWORD *)(a3 + 8) = 0;
      }
      else
      {
        FltClose(FileHandle);
        return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140021c80  mov     r11, rsp
0x140021c83  mov     [r11+8], rbx
0x140021c87  mov     [r11+10h], rsi
0x140021c8b  push    rbp
0x140021c8c  push    rdi
0x140021c8d  push    r14
0x140021c8f  lea     rbp, [r11-5Fh]
0x140021c93  sub     rsp, 0C0h
0x140021c9a  xor     eax, eax
0x140021c9c  mov     [rbp+57h+FileHandle], 0
0x140021ca4  xorps   xmm0, xmm0
0x140021ca7  mov     r14d, r9d
0x140021caa  mov     rdi, r8
0x140021cad  mov     dword ptr [rbp+57h+var_40+4], eax
0x140021cb0  mov     dword ptr [rbp+57h+var_40+1Ch], eax
0x140021cb3  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140021cb7  cmp     [r8], rax
0x140021cba  jnz     loc_140021E36
0x140021cc0  mov     [r11-60h], rax
0x140021cc4  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140021cc8  mov     [rsp+0D0h+Flags], 101h; Flags
0x140021cd0  xor     r9d, r9d; FileObject
0x140021cd3  mov     [rsp+0D0h+EaLength], eax; EaLength
0x140021cd7  mov     [r11-78h], rax
0x140021cdb  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x140021ce3  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x140021ceb  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x140021cf3  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x140021cfb  mov     [rsp+0D0h+AllocationSize], rax; AllocationSize
0x140021d00  mov     [rbp+57h+var_40.RootDirectory], rax
0x140021d04  lea     rax, [rbp+57h+var_50]
0x140021d08  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x140021d0d  lea     rax, [rbp+57h+var_40]
0x140021d11  mov     [rbp+57h+var_40.ObjectName], rdx
0x140021d15  mov     rdx, rcx; Instance
0x140021d18  mov     rcx, cs:LuafvDriverData; Filter
0x140021d1f  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x140021d24  mov     [rsp+0D0h+DesiredAccess], 100001h; DesiredAccess
0x140021d2c  mov     [rbp+57h+var_40.Length], 30h ; '0'
0x140021d33  mov     [rbp+57h+var_40.Attributes], 240h
0x140021d3a  movdqu  xmmword ptr [rbp+57h+var_40.SecurityDescriptor], xmm0
0x140021d3f  call    cs:__imp_FltCreateFileEx2
0x140021d46  nop     dword ptr [rax+rax+00h]
0x140021d4b  mov     esi, eax
0x140021d4d  test    eax, eax
0x140021d4f  js      loc_140021E1B
0x140021d55  cmp     r14d, 0FFFh
0x140021d5c  ja      short loc_140021D8C
0x140021d5e  mov     ebx, 28Eh
0x140021d63  cmp     r14d, ebx
0x140021d66  cmovnb  ebx, r14d
0x140021d6a  lea     eax, [rbx+8]
0x140021d6d  cmp     eax, 8
0x140021d70  jnb     short loc_140021D94
0x140021d72  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140021d76  call    cs:__imp_FltClose
0x140021d7d  nop     dword ptr [rax+rax+00h]
0x140021d82  mov     esi, 0C000009Ah
0x140021d87  jmp     loc_140021E1B
0x140021d8c  mov     ebx, 1000h
0x140021d91  lea     eax, [rbx+8]
0x140021d94  mov     edx, eax
0x140021d96  mov     ecx, 100h
0x140021d9b  mov     r8d, 6661754Ch
0x140021da1  call    cs:__imp_ExAllocatePool2
0x140021da8  nop     dword ptr [rax+rax+00h]
0x140021dad  mov     r14, rax
0x140021db0  test    rax, rax
0x140021db3  jz      short loc_140021D72
0x140021db5  xor     edx, edx
0x140021db7  mov     [rax], ebx
0x140021db9  lea     rcx, PoolLock
0x140021dc0  mov     byte ptr [rax+4], 0FFh
0x140021dc4  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021dcb  nop     dword ptr [rax+rax+00h]
0x140021dd0  add     cs:dword_14000ECBC, ebx
0x140021dd6  lea     rcx, PoolLock
0x140021ddd  xor     edx, edx
0x140021ddf  call    cs:__imp_FltReleasePushLockEx
0x140021de6  nop     dword ptr [rax+rax+00h]
0x140021deb  add     r14, 8
0x140021def  jz      short loc_140021D72
0x140021df1  mov     r8d, ebx; Size
0x140021df4  xor     edx, edx; Val
0x140021df6  mov     rcx, r14; void *
0x140021df9  call    memset
0x140021dfe  mov     rax, [rbp+57h+FileHandle]
0x140021e02  mov     [rdi], rax
0x140021e05  mov     [rdi+0Ch], ebx
0x140021e08  mov     [rdi+10h], r14
0x140021e0c  mov     qword ptr [rdi+18h], 0
0x140021e14  mov     dword ptr [rdi+8], 0
0x140021e1b  lea     r11, [rsp+0D0h+var_10]
0x140021e23  mov     eax, esi
0x140021e25  mov     rbx, [r11+20h]
0x140021e29  mov     rsi, [r11+28h]
0x140021e2d  mov     rsp, r11
0x140021e30  pop     r14
0x140021e32  pop     rdi
0x140021e33  pop     rbp
0x140021e34  retn
0x140021e36  xor     esi, esi
0x140021e38  jmp     short loc_140021E1B
```
