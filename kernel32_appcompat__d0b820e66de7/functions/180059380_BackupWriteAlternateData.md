# BackupWriteAlternateData

- ea: `0x180059380`
- end: `0x1800595df`
- name: `BackupWriteAlternateData`
- size: `607`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070ff0`

## callees

- `0x18000ccf0`
- `0x180059380`
- `0x1800717bc`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x1800593f2`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800593f2`
- `ntdll!NtFsControlFile` at `0x18005959d`
- `ntdll!NtFsControlFile` at `0x18005959d`
- `ntdll!NtCreateFile` at `0x18005952f`
- `ntdll!NtCreateFile` at `0x18005952f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059498`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059498`

## pseudocode

```c
int __fastcall BackupWriteAlternateData(HANDLE FileHandle, __int64 a2, __int64 a3)
{
  bool v6; // al
  __int64 v7; // rdx
  int result; // eax
  HANDLE *v9; // rsi
  bool v10; // zf
  __int16 v11; // ax
  ULONG CreateOptions; // eax
  NTSTATUS v13; // eax
  HANDLE v14; // rcx
  void *v15; // rcx
  _WORD v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+64h] [rbp-9Ch]
  __int64 v18; // [rsp+68h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _DWORD FsInformation[136]; // [rsp+B0h] [rbp-50h] BYREF

  if ( !*(_BYTE *)(a2 + 1136) )
  {
    memset_0(FsInformation, 0, 0x218u);
    *(_BYTE *)(a2 + 1136) = 1;
    IoStatusBlock = 0;
    v6 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation) >= 0;
    *(_BYTE *)(a2 + 1137) = v6;
    if ( v6 )
      *(_DWORD *)(a2 + 1140) = FsInformation[0];
  }
  if ( *(_BYTE *)(a2 + 1137) && (*(_DWORD *)(a2 + 1140) & 0x40000) == 0 )
  {
    v7 = *(unsigned int *)(a3 + 16);
    result = 1;
    *(_QWORD *)(a2 + 1056) += v7;
    **(_DWORD **)(a3 + 8) += v7;
    *(_DWORD *)(a3 + 16) -= v7;
    *(_QWORD *)a3 += v7;
    return result;
  }
  if ( *(_BYTE *)(a2 + 1129) )
  {
    v9 = (HANDLE *)(a2 + 1072);
    v10 = *(_QWORD *)(a2 + 1072) == -1;
    v11 = *(_WORD *)(a2 + 16);
    v17 = 0;
    v16[0] = v11;
    v16[1] = v11;
    v18 = a2 + 20;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    if ( !v10 )
    {
      CloseHandle(*v9);
      *v9 = (HANDLE)-1LL;
      *(_BYTE *)(a2 + 1105) = 0;
    }
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
    CreateOptions = ((*(_DWORD *)(a2 + 1132) & 0x400) << 11) | 0x4020;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = NtCreateFile(
            (PHANDLE)(a2 + 1072),
            0x100002u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            7u,
            5u,
            CreateOptions,
            0,
            0);
    if ( v13 < 0 )
    {
      BaseSetLastNTError((unsigned int)v13);
LABEL_12:
      *(_BYTE *)(a2 + 1131) = 1;
      return 0;
    }
    if ( (*(_BYTE *)(a2 + 4) & 8) != 0 )
    {
      v14 = *v9;
      *(_BYTE *)(a2 + 1105) = 1;
      NtFsControlFile(v14, 0, 0, 0, &IoStatusBlock, 0x900C4u, 0, 0, 0, 0);
    }
  }
  v15 = *(void **)(a2 + 1072);
  if ( v15 == (void *)-1LL )
    goto LABEL_12;
  return BackupWriteStream(v15, a2, a3);
}

```

## disassembly

```asm
0x180059380  push    rbp
0x180059382  push    rbx
0x180059383  push    rsi
0x180059384  push    rdi
0x180059385  push    r14
0x180059387  lea     rbp, [rsp-1E0h]
0x18005938f  sub     rsp, 2E0h
0x180059396  mov     rax, cs:__security_cookie
0x18005939d  xor     rax, rsp
0x1800593a0  mov     [rbp+200h+var_30], rax
0x1800593a7  cmp     byte ptr [rdx+470h], 0
0x1800593ae  mov     rdi, r8
0x1800593b1  mov     rbx, rdx
0x1800593b4  mov     r14, rcx
0x1800593b7  jnz     short loc_180059414
0x1800593b9  mov     esi, 218h
0x1800593be  lea     rcx, [rbp+200h+FsInformation]; void *
0x1800593c2  mov     r8d, esi; Size
0x1800593c5  xor     edx, edx; Val
0x1800593c7  call    memset_0
0x1800593cc  xorps   xmm0, xmm0
0x1800593cf  mov     byte ptr [rbx+470h], 1
0x1800593d6  mov     r9d, esi; Length
0x1800593d9  mov     [rsp+300h+FsInformationClass], 5; FsInformationClass
0x1800593e1  lea     r8, [rbp+200h+FsInformation]; FsInformation
0x1800593e5  mov     rcx, r14; FileHandle
0x1800593e8  lea     rdx, [rsp+300h+IoStatusBlock]; IoStatusBlock
0x1800593ed  movups  xmmword ptr [rsp+300h+IoStatusBlock], xmm0
0x1800593f2  call    cs:__imp_NtQueryVolumeInformationFile
0x1800593f9  nop     dword ptr [rax+rax+00h]
0x1800593fe  shr     eax, 1Fh
0x180059401  xor     al, 1
0x180059403  mov     [rbx+471h], al
0x180059409  jz      short loc_180059414
0x18005940b  mov     eax, [rbp+200h+FsInformation]
0x18005940e  mov     [rbx+474h], eax
0x180059414  cmp     byte ptr [rbx+471h], 0
0x18005941b  jz      short loc_180059449
0x18005941d  test    dword ptr [rbx+474h], 40000h
0x180059427  jnz     short loc_180059449
0x180059429  mov     edx, [rdi+10h]
0x18005942c  mov     eax, 1
0x180059431  add     [rbx+420h], rdx
0x180059438  mov     rcx, [rdi+8]
0x18005943c  add     [rcx], edx
0x18005943e  sub     [rdi+10h], edx
0x180059441  add     [rdi], rdx
0x180059444  jmp     loc_1800595C1
0x180059449  cmp     byte ptr [rbx+469h], 0
0x180059450  jz      loc_1800595A9
0x180059456  xorps   xmm0, xmm0
0x180059459  lea     rsi, [rbx+430h]
0x180059460  xor     eax, eax
0x180059462  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180059466  movzx   eax, word ptr [rbx+10h]
0x18005946a  movups  [rsp+300h+var_2A0], xmm0
0x18005946f  mov     word ptr [rsp+300h+var_2A0], ax
0x180059474  mov     word ptr [rsp+300h+var_2A0+2], ax
0x180059479  lea     rax, [rbx+14h]
0x18005947d  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x180059481  mov     qword ptr [rsp+300h+var_2A0+8], rax
0x180059486  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x18005948a  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x18005948e  movups  xmmword ptr [rsp+300h+IoStatusBlock], xmm0
0x180059493  jz      short loc_1800594B2
0x180059495  mov     rcx, [rsi]; hObject
0x180059498  call    cs:__imp_CloseHandle
0x18005949f  nop     dword ptr [rax+rax+00h]
0x1800594a4  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800594ab  mov     byte ptr [rbx+451h], 0
0x1800594b2  mov     [rsp+300h+EaLength], 0; EaLength
0x1800594ba  lea     rax, [rsp+300h+var_2A0]
0x1800594bf  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1800594c3  lea     r9, [rsp+300h+IoStatusBlock]; IoStatusBlock
0x1800594c8  mov     eax, [rbx+46Ch]
0x1800594ce  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x1800594d2  mov     [rsp+300h+EaBuffer], 0; EaBuffer
0x1800594db  and     eax, 400h
0x1800594e0  shl     eax, 0Bh
0x1800594e3  xorps   xmm0, xmm0
0x1800594e6  or      eax, 4020h
0x1800594eb  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x1800594f2  mov     [rsp+300h+CreateOptions], eax; CreateOptions
0x1800594f6  mov     edx, 100002h; DesiredAccess
0x1800594fb  mov     [rsp+300h+CreateDisposition], 5; CreateDisposition
0x180059503  mov     rcx, rsi; FileHandle
0x180059506  mov     [rsp+300h+ShareAccess], 7; ShareAccess
0x18005950e  mov     [rsp+300h+FileAttributes], 80h; FileAttributes
0x180059516  mov     qword ptr [rsp+300h+FsInformationClass], 0; AllocationSize
0x18005951f  mov     [rbp+200h+ObjectAttributes.RootDirectory], r14
0x180059523  mov     [rbp+200h+ObjectAttributes.Attributes], 40h ; '@'
0x18005952a  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005952f  call    cs:__imp_NtCreateFile
0x180059536  nop     dword ptr [rax+rax+00h]
0x18005953b  test    eax, eax
0x18005953d  jns     short loc_180059551
0x18005953f  mov     ecx, eax
0x180059541  call    BaseSetLastNTError
0x180059546  mov     byte ptr [rbx+46Bh], 1
0x18005954d  xor     eax, eax
0x18005954f  jmp     short loc_1800595C1
0x180059551  test    byte ptr [rbx+4], 8
0x180059555  jz      short loc_1800595A9
0x180059557  mov     rcx, [rsi]; FileHandle
0x18005955a  lea     rax, [rsp+300h+IoStatusBlock]
0x18005955f  mov     dword ptr [rsp+300h+EaBuffer], 0; OutputBufferLength
0x180059567  xor     r9d, r9d; ApcContext
0x18005956a  mov     qword ptr [rsp+300h+CreateOptions], 0; OutputBuffer
0x180059573  xor     r8d, r8d; ApcRoutine
0x180059576  mov     [rsp+300h+CreateDisposition], 0; InputBufferLength
0x18005957e  xor     edx, edx; Event
0x180059580  mov     qword ptr [rsp+300h+ShareAccess], 0; InputBuffer
0x180059589  mov     [rsp+300h+FileAttributes], 900C4h; FsControlCode
0x180059591  mov     qword ptr [rsp+300h+FsInformationClass], rax; IoStatusBlock
0x180059596  mov     byte ptr [rbx+451h], 1
0x18005959d  call    cs:__imp_NtFsControlFile
0x1800595a4  nop     dword ptr [rax+rax+00h]
0x1800595a9  mov     rcx, [rbx+430h]; hFile
0x1800595b0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800595b4  jz      short loc_180059546
0x1800595b6  mov     r8, rdi
0x1800595b9  mov     rdx, rbx
0x1800595bc  call    BackupWriteStream
0x1800595c1  mov     rcx, [rbp+200h+var_30]
0x1800595c8  xor     rcx, rsp; StackCookie
0x1800595cb  call    __security_check_cookie
0x1800595d0  add     rsp, 2E0h
0x1800595d7  pop     r14
0x1800595d9  pop     rdi
0x1800595da  pop     rsi
0x1800595db  pop     rbx
0x1800595dc  pop     rbp
0x1800595dd  retn
```
