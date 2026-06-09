# CreateHardLinkW

- ea: `0x1800f7d60`
- end: `0x1800f800c`
- name: `CreateHardLinkW`
- size: `684`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, LPCWSTR lpExistingFileName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018b580`

## callees

- `0x18004b9d0`
- `0x1800f7d60`
- `0x180194ec5`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800f7e4c`
- `ntdll!NtOpenFile` at `0x1800f7e4c`
- `ntdll!NtSetInformationFile` at `0x1800f7f05`
- `ntdll!NtSetInformationFile` at `0x1800f7f05`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f7dda`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f7e6e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f7dda`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f7e6e`
- `ntdll!RtlSetLastWin32Error` at `0x1800f7f2c`
- `ntdll!RtlSetLastWin32Error` at `0x1800f7ffc`
- `ntdll!RtlSetLastWin32Error` at `0x1800f7f2c`
- `ntdll!RtlSetLastWin32Error` at `0x1800f7ffc`
- `ntdll!NtClose` at `0x1800f7f83`
- `ntdll!NtClose` at `0x1801986d7`
- `ntdll!NtClose` at `0x1800f7f83`
- `ntdll!NtClose` at `0x1801986d7`
- `ntdll!RtlFreeHeap` at `0x1800f7f69`
- `ntdll!RtlFreeHeap` at `0x1800f7fab`
- `ntdll!RtlFreeHeap` at `0x1800f7fd3`
- `ntdll!RtlFreeHeap` at `0x1801986bd`
- `ntdll!RtlFreeHeap` at `0x1801986fe`
- `ntdll!RtlFreeHeap` at `0x180198725`
- `ntdll!RtlFreeHeap` at `0x1800f7f69`
- `ntdll!RtlFreeHeap` at `0x1800f7fab`
- `ntdll!RtlFreeHeap` at `0x1800f7fd3`
- `ntdll!RtlFreeHeap` at `0x1801986bd`
- `ntdll!RtlFreeHeap` at `0x1801986fe`
- `ntdll!RtlFreeHeap` at `0x180198725`
- `ntdll!RtlAllocateHeap` at `0x1800f7e9f`
- `ntdll!RtlAllocateHeap` at `0x1800f7e9f`

## pseudocode

```c
BOOL __stdcall CreateHardLinkW(
        LPCWSTR lpFileName,
        LPCWSTR lpExistingFileName,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  _QWORD *v5; // rdi
  NTSTATUS v6; // eax
  char *Heap; // rax
  BOOL v8; // ebx
  ULONG v9; // ecx
  struct _UNICODE_STRING NtPathName; // [rsp+38h] [rbp-70h] BYREF
  struct _UNICODE_STRING v12; // [rsp+48h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+B0h] [rbp+8h] BYREF

  *(_QWORD *)&v12.Length = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileHandle = (HANDLE)-1LL;
  if ( !lpFileName || !lpExistingFileName )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  v5 = 0;
  v12.Buffer = 0;
  NtPathName.Buffer = 0;
  if ( !RtlDosPathNameToNtPathName_U(lpExistingFileName, &v12, 0, 0) )
    goto LABEL_13;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v12;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( lpSecurityAttributes )
    ObjectAttributes.SecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
  v6 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
  if ( v6 < 0 )
    goto LABEL_11;
  if ( !RtlDosPathNameToNtPathName_U(lpFileName, &NtPathName, 0, 0) )
  {
LABEL_13:
    v9 = 3;
LABEL_14:
    RtlSetLastWin32Error(v9);
    goto LABEL_12;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, NtPathName.Length + 24LL);
  v5 = Heap;
  if ( !Heap )
  {
    v9 = 8;
    goto LABEL_14;
  }
  memmove_0(Heap + 20, NtPathName.Buffer, NtPathName.Length);
  *(_BYTE *)v5 = 0;
  v5[1] = 0;
  *((_DWORD *)v5 + 4) = NtPathName.Length;
  v6 = NtSetInformationFile(FileHandle, &IoStatusBlock, v5, NtPathName.Length + 24, FileLinkInformation);
  if ( v6 < 0 )
  {
LABEL_11:
    BaseSetLastNTError((unsigned int)v6);
LABEL_12:
    v8 = 0;
    goto LABEL_16;
  }
  v8 = 1;
LABEL_16:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v12.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12.Buffer);
  return v8;
}

```

## disassembly

```asm
0x1800f7d60  mov     r11, rsp
0x1800f7d63  mov     [r11+10h], rbx
0x1800f7d67  mov     [r11+18h], rsi
0x1800f7d6b  push    rdi
0x1800f7d6c  sub     rsp, 0A0h
0x1800f7d73  mov     rbx, r8
0x1800f7d76  mov     rax, rdx
0x1800f7d79  mov     rsi, rcx
0x1800f7d7c  mov     qword ptr [r11-60h], 0
0x1800f7d84  mov     qword ptr [r11-70h], 0
0x1800f7d8c  xor     ecx, ecx
0x1800f7d8e  xorps   xmm0, xmm0
0x1800f7d91  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x1800f7d96  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x1800f7d9b  movups  xmmword ptr [r11-24h], xmm0
0x1800f7da0  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x1800f7da5  mov     qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x1800f7dad  test    rsi, rsi
0x1800f7db0  jz      loc_1800F7FF7
0x1800f7db6  test    rax, rax
0x1800f7db9  jz      loc_1800F7FF7
0x1800f7dbf  xor     edi, edi
0x1800f7dc1  mov     [r11-78h], rdi
0x1800f7dc5  mov     [r11-58h], rcx
0x1800f7dc9  mov     [r11-68h], rcx
0x1800f7dcd  xor     r9d, r9d; DirectoryInfo
0x1800f7dd0  xor     r8d, r8d; NtFileNamePart
0x1800f7dd3  lea     rdx, [r11-60h]; NtPathName
0x1800f7dd7  mov     rcx, rax; DosPathName
0x1800f7dda  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f7de1  nop     dword ptr [rax+rax+00h]
0x1800f7de6  test    al, al
0x1800f7de8  jz      loc_1800F7F27
0x1800f7dee  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800f7df6  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rdi
0x1800f7dfb  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f7e06  lea     rax, [rsp+0A8h+var_60]
0x1800f7e0b  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x1800f7e10  xorps   xmm0, xmm0
0x1800f7e13  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f7e1c  test    rbx, rbx
0x1800f7e1f  jnz     loc_1800F7F3A
0x1800f7e25  mov     [rsp+0A8h+OpenOptions], 204020h; OpenOptions
0x1800f7e2d  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x1800f7e35  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x1800f7e3a  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800f7e3f  mov     edx, 100100h; DesiredAccess
0x1800f7e44  lea     rcx, [rsp+0A8h+FileHandle]; FileHandle
0x1800f7e4c  call    cs:__imp_NtOpenFile
0x1800f7e53  nop     dword ptr [rax+rax+00h]
0x1800f7e58  test    eax, eax
0x1800f7e5a  js      loc_1800F7F1C
0x1800f7e60  xor     r9d, r9d; DirectoryInfo
0x1800f7e63  xor     r8d, r8d; NtFileNamePart
0x1800f7e66  lea     rdx, [rsp+0A8h+NtPathName]; NtPathName
0x1800f7e6b  mov     rcx, rsi; DosPathName
0x1800f7e6e  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f7e75  nop     dword ptr [rax+rax+00h]
0x1800f7e7a  test    al, al
0x1800f7e7c  jz      loc_1800F7F27
0x1800f7e82  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800f7e88  movzx   r8d, [rsp+0A8h+NtPathName.Length]
0x1800f7e8e  add     r8, 18h; Size
0x1800f7e92  mov     rcx, gs:60h
0x1800f7e9b  mov     rcx, [rcx+30h]; HeapHandle
0x1800f7e9f  call    cs:__imp_RtlAllocateHeap
0x1800f7ea6  nop     dword ptr [rax+rax+00h]
0x1800f7eab  mov     rdi, rax
0x1800f7eae  mov     [rsp+0A8h+var_78], rax
0x1800f7eb3  test    rax, rax
0x1800f7eb6  jz      loc_1800F7F4B
0x1800f7ebc  movzx   r8d, [rsp+0A8h+NtPathName.Length]; Size
0x1800f7ec2  lea     rcx, [rax+14h]; void *
0x1800f7ec6  mov     rdx, [rsp+0A8h+NtPathName.Buffer]; Src
0x1800f7ecb  call    memmove_0
0x1800f7ed0  mov     byte ptr [rdi], 0
0x1800f7ed3  mov     qword ptr [rdi+8], 0
0x1800f7edb  movzx   eax, [rsp+0A8h+NtPathName.Length]
0x1800f7ee0  mov     [rdi+10h], eax
0x1800f7ee3  movzx   r9d, [rsp+0A8h+NtPathName.Length]
0x1800f7ee9  add     r9d, 18h; Length
0x1800f7eed  mov     [rsp+0A8h+ShareAccess], 0Bh; FileInformationClass
0x1800f7ef5  mov     r8, rdi; FileInformation
0x1800f7ef8  lea     rdx, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x1800f7efd  mov     rcx, [rsp+0A8h+FileHandle]; FileHandle
0x1800f7f05  call    cs:__imp_NtSetInformationFile
0x1800f7f0c  nop     dword ptr [rax+rax+00h]
0x1800f7f11  test    eax, eax
0x1800f7f13  js      short loc_1800F7F1C
0x1800f7f15  mov     ebx, 1
0x1800f7f1a  jmp     short loc_1800F7F52
0x1800f7f1c  mov     ecx, eax
0x1800f7f1e  call    BaseSetLastNTError
0x1800f7f23  xor     ebx, ebx
0x1800f7f25  jmp     short loc_1800F7F52
0x1800f7f27  mov     ecx, 3; LastError
0x1800f7f2c  call    cs:__imp_RtlSetLastWin32Error
0x1800f7f33  nop     dword ptr [rax+rax+00h]
0x1800f7f38  jmp     short loc_1800F7F23
0x1800f7f3a  mov     rax, [rbx+8]
0x1800f7f3e  mov     [rsp+0A8h+ObjectAttributes.SecurityDescriptor], rax
0x1800f7f46  jmp     loc_1800F7E25
0x1800f7f4b  mov     ecx, 8
0x1800f7f50  jmp     short loc_1800F7F2C
0x1800f7f52  test    rdi, rdi
0x1800f7f55  jz      short loc_1800F7F75
0x1800f7f57  mov     rcx, gs:60h
0x1800f7f60  mov     r8, rdi; P
0x1800f7f63  xor     edx, edx; Flags
0x1800f7f65  mov     rcx, [rcx+30h]; HeapHandle
0x1800f7f69  call    cs:__imp_RtlFreeHeap
0x1800f7f70  nop     dword ptr [rax+rax+00h]
0x1800f7f75  mov     rcx, [rsp+0A8h+FileHandle]; Handle
0x1800f7f7d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f7f81  jz      short loc_1800F7F8F
0x1800f7f83  call    cs:__imp_NtClose
0x1800f7f8a  nop     dword ptr [rax+rax+00h]
0x1800f7f8f  cmp     [rsp+0A8h+NtPathName.Buffer], 0
0x1800f7f95  jz      short loc_1800F7FB7
0x1800f7f97  mov     rcx, gs:60h
0x1800f7fa0  mov     r8, [rsp+0A8h+NtPathName.Buffer]; P
0x1800f7fa5  xor     edx, edx; Flags
0x1800f7fa7  mov     rcx, [rcx+30h]; HeapHandle
0x1800f7fab  call    cs:__imp_RtlFreeHeap
0x1800f7fb2  nop     dword ptr [rax+rax+00h]
0x1800f7fb7  cmp     [rsp+0A8h+P], 0
0x1800f7fbd  jz      short loc_1800F7FDF
0x1800f7fbf  mov     rcx, gs:60h
0x1800f7fc8  mov     r8, [rsp+0A8h+P]; P
0x1800f7fcd  xor     edx, edx; Flags
0x1800f7fcf  mov     rcx, [rcx+30h]; HeapHandle
0x1800f7fd3  call    cs:__imp_RtlFreeHeap
0x1800f7fda  nop     dword ptr [rax+rax+00h]
0x1800f7fdf  mov     eax, ebx
0x1800f7fe1  lea     r11, [rsp+0A8h+var_8]
0x1800f7fe9  mov     rbx, [r11+18h]
0x1800f7fed  mov     rsi, [r11+20h]
0x1800f7ff1  mov     rsp, r11
0x1800f7ff4  pop     rdi
0x1800f7ff5  retn
0x1800f7ff7  mov     ecx, 57h ; 'W'; LastError
0x1800f7ffc  call    cs:__imp_RtlSetLastWin32Error
0x1800f8003  nop     dword ptr [rax+rax+00h]
0x1800f8008  xor     eax, eax
0x1800f800a  jmp     short loc_1800F7FE1
0x18019869c  push    rbp
0x18019869e  sub     rsp, 30h
0x1801986a2  mov     rbp, rdx
0x1801986a5  mov     r8, [rbp+30h]; P
0x1801986a9  test    r8, r8
0x1801986ac  jz      short loc_1801986CA
0x1801986ae  mov     rcx, gs:60h
0x1801986b7  xor     edx, edx; Flags
0x1801986b9  mov     rcx, [rcx+30h]; HeapHandle
0x1801986bd  call    cs:__imp_RtlFreeHeap
0x1801986c4  nop     dword ptr [rax+rax+00h]
0x1801986c9  nop
0x1801986ca  mov     rcx, [rbp+0B0h]; Handle
0x1801986d1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801986d5  jz      short loc_1801986E4
0x1801986d7  call    cs:__imp_NtClose
0x1801986de  nop     dword ptr [rax+rax+00h]
0x1801986e3  nop
0x1801986e4  cmp     qword ptr [rbp+40h], 0
0x1801986e9  jz      short loc_18019870B
0x1801986eb  mov     rcx, gs:60h
0x1801986f4  mov     r8, [rbp+40h]; P
0x1801986f8  xor     edx, edx; Flags
0x1801986fa  mov     rcx, [rcx+30h]; HeapHandle
0x1801986fe  call    cs:__imp_RtlFreeHeap
0x180198705  nop     dword ptr [rax+rax+00h]
0x18019870a  nop
0x18019870b  cmp     qword ptr [rbp+50h], 0
0x180198710  jz      short loc_180198732
0x180198712  mov     rcx, gs:60h
0x18019871b  mov     r8, [rbp+50h]; P
0x18019871f  xor     edx, edx; Flags
0x180198721  mov     rcx, [rcx+30h]; HeapHandle
0x180198725  call    cs:__imp_RtlFreeHeap
0x18019872c  nop     dword ptr [rax+rax+00h]
0x180198731  nop
0x180198732  add     rsp, 30h
0x180198736  pop     rbp
0x180198737  retn
```
