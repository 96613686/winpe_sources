# DP_DRIVE::OpenDrive(WSTRING const *,ulong,uchar,void * *,ulong *,MESSAGE *)

- ea: `0x18007c640`
- end: `0x18007c7f8`
- name: `?OpenDrive@DP_DRIVE@@KAJPEBVWSTRING@@KEPEAPEAXPEAKPEAVMESSAGE@@@Z`
- size: `440`
- prototype: `static int(const struct WSTRING *, unsigned int, unsigned __int8, void **, unsigned int *, struct MESSAGE *)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007c440`
- `0x18007cd20`
- `0x18007cf30`

## callees

- `0x180004ab0`
- `0x1800063b8`
- `0x18007c640`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18007c6d6`
- `ntdll!NtOpenFile` at `0x18007c6d6`
- `ntdll!NtQueryInformationFile` at `0x18007c72c`
- `ntdll!NtQueryInformationFile` at `0x18007c72c`
- `KERNEL32!DeviceIoControl` at `0x18007c7db`
- `KERNEL32!DeviceIoControl` at `0x18007c7db`

## pseudocode

```c
__int64 __fastcall DP_DRIVE::OpenDrive(
        const struct WSTRING *a1,
        DWORD a2,
        char a3,
        void **a4,
        unsigned int *a5,
        struct MESSAGE *a6)
{
  __int16 v6; // ax
  NTSTATUS v8; // ebx
  MESSAGE *v9; // rcx
  unsigned int v10; // edx
  NTSTATUS v11; // eax
  int v12; // edi
  __int128 v14; // [rsp+48h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp+7h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+17h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+5Fh] BYREF
  unsigned int FileInformation; // [rsp+B8h] [rbp+67h] BYREF

  LOBYTE(FileInformation) = a3;
  BytesReturned = a2;
  v6 = *((_WORD *)a1 + 12);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v14 = 0;
  LOWORD(v14) = 2 * v6;
  WORD1(v14) = 2 * v6;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a1 + 2);
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
  IoStatusBlock = 0;
  BytesReturned = 0;
  FileInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenFile(a4, 0x100003u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v8 >= 0 )
  {
    v11 = NtQueryInformationFile(*a4, &IoStatusBlock, &FileInformation, 4u, FileAlignmentInformation);
    v8 = v11;
    if ( v11 >= 0 )
    {
      *a5 = FileInformation;
      DeviceIoControl(*a4, 0x90083u, 0, 0, 0, 0, &BytesReturned, 0);
      return (unsigned int)v8;
    }
    if ( v11 == -2147483632 )
    {
      v12 = 3047;
    }
    else if ( v11 == -2147483631 || v11 == -1073741661 )
    {
      v12 = 2096;
    }
    else
    {
      v12 = 2006;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids);
    v9 = (MESSAGE *)a6;
    if ( a6 )
    {
      v10 = v12;
LABEL_5:
      MESSAGE::DisplayMsg(v9, v10, MultiByteStr);
    }
  }
  else
  {
    v9 = (MESSAGE *)a6;
    v10 = 3029;
    if ( v8 != -1073741790 )
      v10 = 2007;
    if ( a6 )
      goto LABEL_5;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007c640  mov     rax, rsp
0x18007c643  mov     [rax+8], rbx
0x18007c647  mov     [rax+20h], rdi
0x18007c64b  mov     [rax+18h], r8b
0x18007c64f  mov     [rax+10h], edx
0x18007c652  push    rbp
0x18007c653  lea     rbp, [rax-4Fh]
0x18007c657  sub     rsp, 90h
0x18007c65e  movzx   eax, word ptr [rcx+18h]
0x18007c662  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x18007c666  add     ax, ax
0x18007c669  mov     [rsp+90h+OpenOptions], 20h ; ' '; OpenOptions
0x18007c671  xorps   xmm0, xmm0
0x18007c674  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x18007c67c  movups  [rbp+47h+var_50], xmm0
0x18007c680  mov     word ptr [rbp+47h+var_50], ax
0x18007c684  mov     rdi, r9
0x18007c687  mov     word ptr [rbp+47h+var_50+2], ax
0x18007c68b  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x18007c68f  mov     rax, [rcx+10h]
0x18007c693  mov     edx, 100003h; DesiredAccess
0x18007c698  mov     qword ptr [rbp+47h+var_50+8], rax
0x18007c69c  mov     rcx, rdi; FileHandle
0x18007c69f  lea     rax, [rbp+47h+var_50]
0x18007c6a3  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 40h ; '@'
0x18007c6ab  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x18007c6af  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x18007c6b3  mov     [rbp+47h+BytesReturned], 0
0x18007c6ba  mov     [rbp+47h+FileInformation], 0
0x18007c6c1  mov     [rbp+47h+ObjectAttributes.RootDirectory], 0
0x18007c6c9  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007c6ce  mov     [rsp+90h+ShareAccess], 3; ShareAccess
0x18007c6d6  call    cs:__imp_NtOpenFile
0x18007c6dc  mov     ebx, eax
0x18007c6de  test    eax, eax
0x18007c6e0  jns     short loc_18007C713
0x18007c6e2  mov     rcx, [rbp+47h+arg_28]; this
0x18007c6e6  cmp     ebx, 0C0000022h
0x18007c6ec  mov     edx, 0BD5h
0x18007c6f1  mov     eax, 7D7h
0x18007c6f6  cmovnz  edx, eax; unsigned int
0x18007c6f9  test    rcx, rcx
0x18007c6fc  jz      loc_18007C7E1
0x18007c702  lea     r8, MultiByteStr; char *
0x18007c709  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x18007c70e  jmp     loc_18007C7E1
0x18007c713  mov     rcx, [rdi]; FileHandle
0x18007c716  lea     r8, [rbp+47h+FileInformation]; FileInformation
0x18007c71a  mov     r9d, 4; Length
0x18007c720  mov     [rsp+90h+ShareAccess], 11h; FileInformationClass
0x18007c728  lea     rdx, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x18007c72c  call    cs:__imp_NtQueryInformationFile
0x18007c732  mov     ebx, eax
0x18007c734  test    eax, eax
0x18007c736  jns     short loc_18007C7A1
0x18007c738  cmp     eax, 80000010h
0x18007c73d  jz      short loc_18007C75B
0x18007c73f  cmp     eax, 80000011h
0x18007c744  jz      short loc_18007C754
0x18007c746  cmp     eax, 0C00000A3h
0x18007c74b  jz      short loc_18007C754
0x18007c74d  mov     edi, 7D6h
0x18007c752  jmp     short loc_18007C760
0x18007c754  mov     edi, 830h
0x18007c759  jmp     short loc_18007C760
0x18007c75b  mov     edi, 0BE7h
0x18007c760  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c767  lea     rax, WPP_GLOBAL_Control
0x18007c76e  cmp     rcx, rax
0x18007c771  jz      short loc_18007C791
0x18007c773  test    byte ptr [rcx+1Ch], 1
0x18007c777  jz      short loc_18007C791
0x18007c779  mov     rcx, [rcx+10h]
0x18007c77d  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18007c784  mov     edx, 0Ah
0x18007c789  mov     r9d, ebx
0x18007c78c  call    WPP_SF_d
0x18007c791  mov     rcx, [rbp+47h+arg_28]
0x18007c795  test    rcx, rcx
0x18007c798  jz      short loc_18007C7E1
0x18007c79a  mov     edx, edi
0x18007c79c  jmp     loc_18007C702
0x18007c7a1  mov     eax, [rbp+47h+FileInformation]
0x18007c7a4  xor     r9d, r9d; nInBufferSize
0x18007c7a7  mov     rcx, [rbp+47h+arg_20]
0x18007c7ab  xor     r8d, r8d; lpInBuffer
0x18007c7ae  mov     [rsp+90h+lpOverlapped], 0; lpOverlapped
0x18007c7b7  mov     edx, 90083h; dwIoControlCode
0x18007c7bc  mov     [rcx], eax
0x18007c7be  lea     rax, [rbp+47h+BytesReturned]
0x18007c7c2  mov     rcx, [rdi]; hDevice
0x18007c7c5  mov     [rsp+90h+lpBytesReturned], rax; lpBytesReturned
0x18007c7ca  mov     [rsp+90h+OpenOptions], 0; nOutBufferSize
0x18007c7d2  mov     qword ptr [rsp+90h+ShareAccess], 0; lpOutBuffer
0x18007c7db  call    cs:__imp_DeviceIoControl
0x18007c7e1  lea     r11, [rsp+90h+var_s0]
0x18007c7e9  mov     eax, ebx
0x18007c7eb  mov     rbx, [r11+10h]
0x18007c7ef  mov     rdi, [r11+28h]
0x18007c7f3  mov     rsp, r11
0x18007c7f6  pop     rbp
0x18007c7f7  retn
```
