# AslFileOpen

- ea: `0x180047c04`
- end: `0x180047ec1`
- name: `AslFileOpen`
- size: `701`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, PWSTR FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002010c`

## callees

- `0x18001ef8c`
- `0x18001f138`
- `0x180047c04`
- `0x180061df4`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180047d76`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180047d76`
- `ntdll!RtlFreeUnicodeString` at `0x180047e7c`
- `ntdll!RtlFreeUnicodeString` at `0x180047e7c`
- `ntdll!RtlGetFullPathName_UEx` at `0x180047cd9`
- `ntdll!RtlGetFullPathName_UEx` at `0x180047cd9`
- `ntdll!ZwCreateFile` at `0x180047e0a`
- `ntdll!ZwCreateFile` at `0x180047e0a`
- `ntdll!RtlInitUnicodeString` at `0x180047c4b`
- `ntdll!RtlInitUnicodeString` at `0x180047c4b`
- `ntdll!RtlAllocateHeap` at `0x180047cad`
- `ntdll!RtlAllocateHeap` at `0x180047cad`

## string_xrefs

- `0x180047d35`: `AslFileOpen`
- `0x180047e38`: `AslFileOpen`
- `0x180047e5c`: `AslFileOpen`
- `0x180047d28`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x180047e2b`: `Failed to get full path [%x]`
- `0x180047d88`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`
- `0x180047e1c`: `NtCreateFile failed [%x]`

## pseudocode

```c
__int64 __fastcall AslFileOpen(PHANDLE FileHandle, PWSTR FileName)
{
  WCHAR *Heap; // rdi
  char v5; // r14
  RTL_PATH_TYPE v6; // esi
  NTSTATUS FullPathName_UEx; // eax
  unsigned int v8; // ebx
  bool v9; // cf
  const char *v10; // r9
  int v11; // r8d
  char InputPathType; // [rsp+20h] [rbp-59h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  RTL_PATH_TYPE v17; // [rsp+E0h] [rbp+67h] BYREF

  *FileHandle = 0;
  v17 = RtlPathTypeUnknown;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  if ( DestinationString.Length <= 8u
    || *DestinationString.Buffer != 92
    || DestinationString.Buffer[1] != 92 && DestinationString.Buffer[1] != 63
    || DestinationString.Buffer[2] != 63
    || (Heap = 0, DestinationString.Buffer[3] != 92) )
  {
    v5 = 0;
    v6 = 520;
    while ( 1 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v6);
      if ( !Heap )
      {
        AslLogCallPrintf(1, (unsigned int)"AslFileOpen", 1843, (unsigned int)"Out of memory", InputPathType);
        v8 = -1073741801;
        goto LABEL_24;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v6, Heap, 0, &v17);
      v8 = FullPathName_UEx;
      if ( FullPathName_UEx < 0 )
      {
        v10 = "Failed to get full path [%x]";
        v11 = 1854;
        goto LABEL_22;
      }
      v9 = v17 < (unsigned int)v6;
      if ( v17 > (unsigned int)v6 )
      {
        if ( v5 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslFileOpen",
            1862,
            (unsigned int)"RtlGetFullPathName_UEx failed to get full path with larger buffer.",
            InputPathType);
          v8 = -1073741789;
          goto LABEL_24;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v6 = v17;
        v9 = 0;
      }
      if ( v9 )
        break;
      v5 = 1;
    }
    if ( wcsnicmp_0(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      v8 = FullPathName_UEx;
      if ( FullPathName_UEx < 0 )
      {
        v10 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v11 = 1885;
        goto LABEL_22;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FullPathName_UEx = ZwCreateFile(
                       FileHandle,
                       0x80100080,
                       &ObjectAttributes,
                       &IoStatusBlock,
                       0,
                       0x80u,
                       1u,
                       1u,
                       0x60u,
                       0,
                       0);
  v8 = FullPathName_UEx;
  if ( FullPathName_UEx < 0 )
  {
    v10 = "NtCreateFile failed [%x]";
    v11 = 1910;
LABEL_22:
    AslLogCallPrintf(1, (unsigned int)"AslFileOpen", v11, (_DWORD)v10, FullPathName_UEx);
  }
LABEL_24:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v8;
}

```

## disassembly

```asm
0x180047c04  mov     [rsp-8+arg_8], rbx
0x180047c09  mov     [rsp-8+arg_10], rsi
0x180047c0e  push    rbp
0x180047c0f  push    rdi
0x180047c10  push    r12
0x180047c12  push    r14
0x180047c14  push    r15
0x180047c16  lea     rbp, [rsp-37h]
0x180047c1b  sub     rsp, 0B0h
0x180047c22  xorps   xmm0, xmm0
0x180047c25  xor     eax, eax
0x180047c27  mov     [rcx], rax
0x180047c2a  mov     r12, rcx
0x180047c2d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180047c31  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180047c35  mov     [rbp+57h+arg_0], eax
0x180047c38  mov     r15, rdx
0x180047c3b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180047c3f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180047c43  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180047c47  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180047c4b  call    cs:__imp_RtlInitUnicodeString
0x180047c52  nop     dword ptr [rax+rax+00h]
0x180047c57  mov     eax, 8
0x180047c5c  cmp     [rbp+57h+DestinationString.Length], ax
0x180047c60  jbe     short loc_180047C93
0x180047c62  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180047c66  cmp     word ptr [rax], 5Ch ; '\'
0x180047c6a  jnz     short loc_180047C8E
0x180047c6c  cmp     word ptr [rax+2], 5Ch ; '\'
0x180047c71  jz      short loc_180047C7A
0x180047c73  cmp     word ptr [rax+2], 3Fh ; '?'
0x180047c78  jnz     short loc_180047C8E
0x180047c7a  cmp     word ptr [rax+4], 3Fh ; '?'
0x180047c7f  jnz     short loc_180047C8E
0x180047c81  xor     edi, edi
0x180047c83  cmp     word ptr [rax+6], 5Ch ; '\'
0x180047c88  jz      loc_180047D9A
0x180047c8e  mov     eax, 8
0x180047c93  xor     r14b, r14b
0x180047c96  mov     esi, 208h
0x180047c9b  mov     rcx, gs:60h
0x180047ca4  mov     edx, eax; Flags
0x180047ca6  mov     r8d, esi; Size
0x180047ca9  mov     rcx, [rcx+30h]; HeapHandle
0x180047cad  call    cs:__imp_RtlAllocateHeap
0x180047cb4  nop     dword ptr [rax+rax+00h]
0x180047cb9  mov     rdi, rax
0x180047cbc  test    rax, rax
0x180047cbf  jz      loc_180047E4F
0x180047cc5  lea     rax, [rbp+57h+arg_0]
0x180047cc9  xor     r9d, r9d; FilePart
0x180047ccc  mov     r8, rdi; Buffer
0x180047ccf  mov     [rsp+0D0h+InputPathType], rax; InputPathType
0x180047cd4  mov     edx, esi; BufferLength
0x180047cd6  mov     rcx, r15; FileName
0x180047cd9  call    cs:__imp_RtlGetFullPathName_UEx
0x180047ce0  nop     dword ptr [rax+rax+00h]
0x180047ce5  mov     ebx, eax
0x180047ce7  test    eax, eax
0x180047ce9  js      loc_180047E2B
0x180047cef  mov     eax, [rbp+57h+arg_0]
0x180047cf2  cmp     eax, esi
0x180047cf4  jbe     short loc_180047D19
0x180047cf6  test    r14b, r14b
0x180047cf9  jnz     short loc_180047D28
0x180047cfb  mov     rcx, gs:60h
0x180047d04  mov     rdx, rdi
0x180047d07  mov     rcx, [rcx+30h]
0x180047d0b  call    AslFree
0x180047d10  mov     eax, [rbp+57h+arg_0]
0x180047d13  xor     edi, edi
0x180047d15  mov     esi, eax
0x180047d17  cmp     eax, eax
0x180047d19  jb      short loc_180047D50
0x180047d1b  mov     r14b, 1
0x180047d1e  mov     eax, 8
0x180047d23  jmp     loc_180047C9B
0x180047d28  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x180047d2f  mov     r8d, 746h
0x180047d35  lea     rdx, aAslfileopen; "AslFileOpen"
0x180047d3c  mov     ecx, 1
0x180047d41  call    AslLogCallPrintf
0x180047d46  mov     ebx, 0C0000023h
0x180047d4b  jmp     loc_180047E72
0x180047d50  mov     r8d, 0Ch; MaxCount
0x180047d56  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x180047d5d  mov     rcx, rdi; String1
0x180047d60  call    _wcsnicmp_0
0x180047d65  test    eax, eax
0x180047d67  jz      short loc_180047D9A
0x180047d69  xor     r9d, r9d
0x180047d6c  lea     rdx, [rbp+57h+DestinationString]
0x180047d70  xor     r8d, r8d
0x180047d73  mov     rcx, rdi
0x180047d76  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180047d7d  nop     dword ptr [rax+rax+00h]
0x180047d82  mov     ebx, eax
0x180047d84  test    eax, eax
0x180047d86  jns     short loc_180047D9A
0x180047d88  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180047d8f  mov     r8d, 75Dh
0x180047d95  jmp     loc_180047E38
0x180047d9a  mov     [rsp+0D0h+EaLength], 0; EaLength
0x180047da2  lea     rax, [rbp+57h+DestinationString]
0x180047da6  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x180047daf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180047db3  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x180047dbb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180047dbf  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x180047dc7  xorps   xmm0, xmm0
0x180047dca  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x180047dd2  mov     edx, 80100080h; DesiredAccess
0x180047dd7  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180047ddf  mov     rcx, r12; FileHandle
0x180047de2  mov     [rsp+0D0h+InputPathType], 0; AllocationSize
0x180047deb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180047df2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180047dfa  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180047e01  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180047e05  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180047e0a  call    cs:__imp_ZwCreateFile
0x180047e11  nop     dword ptr [rax+rax+00h]
0x180047e16  mov     ebx, eax
0x180047e18  test    eax, eax
0x180047e1a  jns     short loc_180047E72
0x180047e1c  lea     r9, aNtcreatefileFa; "NtCreateFile failed [%x]"
0x180047e23  mov     r8d, 776h
0x180047e29  jmp     short loc_180047E38
0x180047e2b  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x180047e32  mov     r8d, 73Eh
0x180047e38  lea     rdx, aAslfileopen; "AslFileOpen"
0x180047e3f  mov     dword ptr [rsp+0D0h+InputPathType], eax
0x180047e43  mov     ecx, 1
0x180047e48  call    AslLogCallPrintf
0x180047e4d  jmp     short loc_180047E72
0x180047e4f  lea     r9, aOutOfMemory; "Out of memory"
0x180047e56  mov     r8d, 733h
0x180047e5c  lea     rdx, aAslfileopen; "AslFileOpen"
0x180047e63  mov     ecx, 1
0x180047e68  call    AslLogCallPrintf
0x180047e6d  mov     ebx, 0C0000017h
0x180047e72  cmp     [rbp+57h+DestinationString.Buffer], r15
0x180047e76  jz      short loc_180047E88
0x180047e78  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x180047e7c  call    cs:__imp_RtlFreeUnicodeString
0x180047e83  nop     dword ptr [rax+rax+00h]
0x180047e88  test    rdi, rdi
0x180047e8b  jz      short loc_180047EA2
0x180047e8d  mov     rcx, gs:60h
0x180047e96  mov     rdx, rdi
0x180047e99  mov     rcx, [rcx+30h]
0x180047e9d  call    AslFree
0x180047ea2  lea     r11, [rsp+0D0h+var_20]
0x180047eaa  mov     eax, ebx
0x180047eac  mov     rbx, [r11+38h]
0x180047eb0  mov     rsi, [r11+40h]
0x180047eb4  mov     rsp, r11
0x180047eb7  pop     r15
0x180047eb9  pop     r14
0x180047ebb  pop     r12
0x180047ebd  pop     rdi
0x180047ebe  pop     rbp
0x180047ebf  retn
```
