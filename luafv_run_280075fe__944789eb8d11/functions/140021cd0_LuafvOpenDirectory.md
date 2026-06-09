# LuafvOpenDirectory

- ea: `0x140021cd0`
- end: `0x140021e8a`
- name: `LuafvOpenDirectory`
- size: `442`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140014df0`

## callees

- `0x140006380`
- `0x140021cd0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140021df1`
- `ntoskrnl!ExAllocatePool2` at `0x140021df1`
- `FLTMGR!FltReleasePushLockEx` at `0x140021e2f`
- `FLTMGR!FltReleasePushLockEx` at `0x140021e2f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021e14`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021e14`
- `FLTMGR!FltClose` at `0x140021dc6`
- `FLTMGR!FltClose` at `0x140021dc6`
- `FLTMGR!FltCreateFileEx2` at `0x140021d8f`
- `FLTMGR!FltCreateFileEx2` at `0x140021d8f`

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
            dword_14000F2FC += v7,
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
0x140021cd0  mov     r11, rsp
0x140021cd3  mov     [r11+8], rbx
0x140021cd7  mov     [r11+10h], rsi
0x140021cdb  push    rbp
0x140021cdc  push    rdi
0x140021cdd  push    r14
0x140021cdf  lea     rbp, [r11-5Fh]
0x140021ce3  sub     rsp, 0C0h
0x140021cea  xor     eax, eax
0x140021cec  mov     [rbp+57h+FileHandle], 0
0x140021cf4  xorps   xmm0, xmm0
0x140021cf7  mov     r14d, r9d
0x140021cfa  mov     rdi, r8
0x140021cfd  mov     dword ptr [rbp+57h+var_40+4], eax
0x140021d00  mov     dword ptr [rbp+57h+var_40+1Ch], eax
0x140021d03  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140021d07  cmp     [r8], rax
0x140021d0a  jnz     loc_140021E86
0x140021d10  mov     [r11-60h], rax
0x140021d14  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140021d18  mov     [rsp+0D0h+Flags], 101h; Flags
0x140021d20  xor     r9d, r9d; FileObject
0x140021d23  mov     [rsp+0D0h+EaLength], eax; EaLength
0x140021d27  mov     [r11-78h], rax
0x140021d2b  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x140021d33  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x140021d3b  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x140021d43  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x140021d4b  mov     [rsp+0D0h+AllocationSize], rax; AllocationSize
0x140021d50  mov     [rbp+57h+var_40.RootDirectory], rax
0x140021d54  lea     rax, [rbp+57h+var_50]
0x140021d58  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x140021d5d  lea     rax, [rbp+57h+var_40]
0x140021d61  mov     [rbp+57h+var_40.ObjectName], rdx
0x140021d65  mov     rdx, rcx; Instance
0x140021d68  mov     rcx, cs:LuafvDriverData; Filter
0x140021d6f  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x140021d74  mov     [rsp+0D0h+DesiredAccess], 100001h; DesiredAccess
0x140021d7c  mov     [rbp+57h+var_40.Length], 30h ; '0'
0x140021d83  mov     [rbp+57h+var_40.Attributes], 240h
0x140021d8a  movdqu  xmmword ptr [rbp+57h+var_40.SecurityDescriptor], xmm0
0x140021d8f  call    cs:__imp_FltCreateFileEx2
0x140021d96  nop     dword ptr [rax+rax+00h]
0x140021d9b  mov     esi, eax
0x140021d9d  test    eax, eax
0x140021d9f  js      loc_140021E6B
0x140021da5  cmp     r14d, 0FFFh
0x140021dac  ja      short loc_140021DDC
0x140021dae  mov     ebx, 28Eh
0x140021db3  cmp     r14d, ebx
0x140021db6  cmovnb  ebx, r14d
0x140021dba  lea     eax, [rbx+8]
0x140021dbd  cmp     eax, 8
0x140021dc0  jnb     short loc_140021DE4
0x140021dc2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140021dc6  call    cs:__imp_FltClose
0x140021dcd  nop     dword ptr [rax+rax+00h]
0x140021dd2  mov     esi, 0C000009Ah
0x140021dd7  jmp     loc_140021E6B
0x140021ddc  mov     ebx, 1000h
0x140021de1  lea     eax, [rbx+8]
0x140021de4  mov     edx, eax
0x140021de6  mov     ecx, 100h
0x140021deb  mov     r8d, 6661754Ch
0x140021df1  call    cs:__imp_ExAllocatePool2
0x140021df8  nop     dword ptr [rax+rax+00h]
0x140021dfd  mov     r14, rax
0x140021e00  test    rax, rax
0x140021e03  jz      short loc_140021DC2
0x140021e05  xor     edx, edx
0x140021e07  mov     [rax], ebx
0x140021e09  lea     rcx, PoolLock
0x140021e10  mov     byte ptr [rax+4], 0FFh
0x140021e14  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021e1b  nop     dword ptr [rax+rax+00h]
0x140021e20  add     cs:dword_14000F2FC, ebx
0x140021e26  lea     rcx, PoolLock
0x140021e2d  xor     edx, edx
0x140021e2f  call    cs:__imp_FltReleasePushLockEx
0x140021e36  nop     dword ptr [rax+rax+00h]
0x140021e3b  add     r14, 8
0x140021e3f  jz      short loc_140021DC2
0x140021e41  mov     r8d, ebx; Size
0x140021e44  xor     edx, edx; Val
0x140021e46  mov     rcx, r14; void *
0x140021e49  call    memset
0x140021e4e  mov     rax, [rbp+57h+FileHandle]
0x140021e52  mov     [rdi], rax
0x140021e55  mov     [rdi+0Ch], ebx
0x140021e58  mov     [rdi+10h], r14
0x140021e5c  mov     qword ptr [rdi+18h], 0
0x140021e64  mov     dword ptr [rdi+8], 0
0x140021e6b  lea     r11, [rsp+0D0h+var_10]
0x140021e73  mov     eax, esi
0x140021e75  mov     rbx, [r11+20h]
0x140021e79  mov     rsi, [r11+28h]
0x140021e7d  mov     rsp, r11
0x140021e80  pop     r14
0x140021e82  pop     rdi
0x140021e83  pop     rbp
0x140021e84  retn
0x140021e86  xor     esi, esi
0x140021e88  jmp     short loc_140021E6B
```
