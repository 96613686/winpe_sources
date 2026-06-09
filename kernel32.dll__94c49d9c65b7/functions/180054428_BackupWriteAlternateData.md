# BackupWriteAlternateData

- ea: `0x180054428`
- end: `0x18005466e`
- name: `BackupWriteAlternateData`
- size: `582`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180069e20`

## callees

- `0x18000f920`
- `0x180054428`
- `0x18006a5a0`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18005449a`
- `ntdll!NtQueryVolumeInformationFile` at `0x18005449a`
- `ntdll!NtFsControlFile` at `0x180054633`
- `ntdll!NtFsControlFile` at `0x180054633`
- `ntdll!NtCreateFile` at `0x1800545cb`
- `ntdll!NtCreateFile` at `0x1800545cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005453a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005453a`

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
0x180054428  push    rbp
0x18005442a  push    rbx
0x18005442b  push    rsi
0x18005442c  push    rdi
0x18005442d  push    r14
0x18005442f  lea     rbp, [rsp-1E0h]
0x180054437  sub     rsp, 2E0h
0x18005443e  mov     rax, cs:__security_cookie
0x180054445  xor     rax, rsp
0x180054448  mov     [rbp+200h+var_30], rax
0x18005444f  cmp     byte ptr [rdx+470h], 0
0x180054456  mov     rdi, r8
0x180054459  mov     rbx, rdx
0x18005445c  mov     r14, rcx
0x18005445f  jnz     short loc_1800544B6
0x180054461  mov     esi, 218h
0x180054466  lea     rcx, [rbp+200h+FsInformation]; void *
0x18005446a  mov     r8d, esi; Size
0x18005446d  xor     edx, edx; Val
0x18005446f  call    memset_0
0x180054474  xorps   xmm0, xmm0
0x180054477  mov     byte ptr [rbx+470h], 1
0x18005447e  mov     r9d, esi; Length
0x180054481  mov     [rsp+300h+FsInformationClass], 5; FsInformationClass
0x180054489  lea     r8, [rbp+200h+FsInformation]; FsInformation
0x18005448d  mov     rcx, r14; FileHandle
0x180054490  lea     rdx, [rsp+300h+IoStatusBlock]; IoStatusBlock
0x180054495  movups  xmmword ptr [rsp+300h+IoStatusBlock], xmm0
0x18005449a  call    cs:__imp_NtQueryVolumeInformationFile
0x1800544a0  shr     eax, 1Fh
0x1800544a3  xor     al, 1
0x1800544a5  mov     [rbx+471h], al
0x1800544ab  jz      short loc_1800544B6
0x1800544ad  mov     eax, [rbp+200h+FsInformation]
0x1800544b0  mov     [rbx+474h], eax
0x1800544b6  cmp     byte ptr [rbx+471h], 0
0x1800544bd  jz      short loc_1800544EB
0x1800544bf  test    dword ptr [rbx+474h], 40000h
0x1800544c9  jnz     short loc_1800544EB
0x1800544cb  mov     edx, [rdi+10h]
0x1800544ce  mov     eax, 1
0x1800544d3  add     [rbx+420h], rdx
0x1800544da  mov     rcx, [rdi+8]
0x1800544de  add     [rcx], edx
0x1800544e0  sub     [rdi+10h], edx
0x1800544e3  add     [rdi], rdx
0x1800544e6  jmp     loc_180054651
0x1800544eb  cmp     byte ptr [rbx+469h], 0
0x1800544f2  jz      loc_180054639
0x1800544f8  xorps   xmm0, xmm0
0x1800544fb  lea     rsi, [rbx+430h]
0x180054502  xor     eax, eax
0x180054504  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180054508  movzx   eax, word ptr [rbx+10h]
0x18005450c  movups  [rsp+300h+var_2A0], xmm0
0x180054511  mov     word ptr [rsp+300h+var_2A0], ax
0x180054516  mov     word ptr [rsp+300h+var_2A0+2], ax
0x18005451b  lea     rax, [rbx+14h]
0x18005451f  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x180054523  mov     qword ptr [rsp+300h+var_2A0+8], rax
0x180054528  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x18005452c  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x180054530  movups  xmmword ptr [rsp+300h+IoStatusBlock], xmm0
0x180054535  jz      short loc_18005454E
0x180054537  mov     rcx, [rsi]; hObject
0x18005453a  call    cs:__imp_CloseHandle
0x180054540  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180054547  mov     byte ptr [rbx+451h], 0
0x18005454e  mov     [rsp+300h+EaLength], 0; EaLength
0x180054556  lea     rax, [rsp+300h+var_2A0]
0x18005455b  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x18005455f  lea     r9, [rsp+300h+IoStatusBlock]; IoStatusBlock
0x180054564  mov     eax, [rbx+46Ch]
0x18005456a  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x18005456e  mov     [rsp+300h+EaBuffer], 0; EaBuffer
0x180054577  and     eax, 400h
0x18005457c  shl     eax, 0Bh
0x18005457f  xorps   xmm0, xmm0
0x180054582  or      eax, 4020h
0x180054587  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x18005458e  mov     [rsp+300h+CreateOptions], eax; CreateOptions
0x180054592  mov     edx, 100002h; DesiredAccess
0x180054597  mov     [rsp+300h+CreateDisposition], 5; CreateDisposition
0x18005459f  mov     rcx, rsi; FileHandle
0x1800545a2  mov     [rsp+300h+ShareAccess], 7; ShareAccess
0x1800545aa  mov     [rsp+300h+FileAttributes], 80h; FileAttributes
0x1800545b2  mov     qword ptr [rsp+300h+FsInformationClass], 0; AllocationSize
0x1800545bb  mov     [rbp+200h+ObjectAttributes.RootDirectory], r14
0x1800545bf  mov     [rbp+200h+ObjectAttributes.Attributes], 40h ; '@'
0x1800545c6  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800545cb  call    cs:__imp_NtCreateFile
0x1800545d1  test    eax, eax
0x1800545d3  jns     short loc_1800545E7
0x1800545d5  mov     ecx, eax
0x1800545d7  call    BaseSetLastNTError
0x1800545dc  mov     byte ptr [rbx+46Bh], 1
0x1800545e3  xor     eax, eax
0x1800545e5  jmp     short loc_180054651
0x1800545e7  test    byte ptr [rbx+4], 8
0x1800545eb  jz      short loc_180054639
0x1800545ed  mov     rcx, [rsi]; FileHandle
0x1800545f0  lea     rax, [rsp+300h+IoStatusBlock]
0x1800545f5  mov     dword ptr [rsp+300h+EaBuffer], 0; OutputBufferLength
0x1800545fd  xor     r9d, r9d; ApcContext
0x180054600  mov     qword ptr [rsp+300h+CreateOptions], 0; OutputBuffer
0x180054609  xor     r8d, r8d; ApcRoutine
0x18005460c  mov     [rsp+300h+CreateDisposition], 0; InputBufferLength
0x180054614  xor     edx, edx; Event
0x180054616  mov     qword ptr [rsp+300h+ShareAccess], 0; InputBuffer
0x18005461f  mov     [rsp+300h+FileAttributes], 900C4h; FsControlCode
0x180054627  mov     qword ptr [rsp+300h+FsInformationClass], rax; IoStatusBlock
0x18005462c  mov     byte ptr [rbx+451h], 1
0x180054633  call    cs:__imp_NtFsControlFile
0x180054639  mov     rcx, [rbx+430h]; hFile
0x180054640  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180054644  jz      short loc_1800545DC
0x180054646  mov     r8, rdi
0x180054649  mov     rdx, rbx
0x18005464c  call    BackupWriteStream
0x180054651  mov     rcx, [rbp+200h+var_30]
0x180054658  xor     rcx, rsp; StackCookie
0x18005465b  call    __security_check_cookie
0x180054660  add     rsp, 2E0h
0x180054667  pop     r14
0x180054669  pop     rdi
0x18005466a  pop     rsi
0x18005466b  pop     rbx
0x18005466c  pop     rbp
0x18005466d  retn
```
