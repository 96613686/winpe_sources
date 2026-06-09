# GetVolumeInformationW

- ea: `0x1800c0370`
- end: `0x1800c06fb`
- name: `GetVolumeInformationW`
- size: `907`
- prototype: `BOOL __stdcall(LPCWSTR lpRootPathName, LPWSTR lpVolumeNameBuffer, DWORD nVolumeNameSize, LPDWORD lpVolumeSerialNumber, LPDWORD lpMaximumComponentLength, LPDWORD lpFileSystemFlags, LPWSTR lpFileSystemNameBuffer, DWORD nFileSystemNameSize)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bfc60`
- `0x1800c0090`

## callees

- `0x18004b9d0`
- `0x1800c0370`
- `0x1800c0710`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800c061b`
- `ntdll!NtQueryInformationFile` at `0x1800c061b`
- `ntdll!NtOpenFile` at `0x1800c0498`
- `ntdll!NtOpenFile` at `0x1800c0498`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800c0408`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800c0408`
- `ntdll!RtlSetLastWin32Error` at `0x1800c05ae`
- `ntdll!RtlSetLastWin32Error` at `0x1800c06af`
- `ntdll!RtlSetLastWin32Error` at `0x1800c05ae`
- `ntdll!RtlSetLastWin32Error` at `0x1800c06af`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800c0530`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800c0530`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800c0571`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800c0571`
- `ntdll!NtClose` at `0x1800c0584`
- `ntdll!NtClose` at `0x1800c059d`
- `ntdll!NtClose` at `0x1800c0697`
- `ntdll!NtClose` at `0x1800c0584`
- `ntdll!NtClose` at `0x1800c059d`
- `ntdll!NtClose` at `0x1800c0697`
- `ntdll!RtlFreeHeap` at `0x1800c05cc`
- `ntdll!RtlFreeHeap` at `0x1800c0654`
- `ntdll!RtlFreeHeap` at `0x1800c06d4`
- `ntdll!RtlFreeHeap` at `0x1800c05cc`
- `ntdll!RtlFreeHeap` at `0x1800c0654`
- `ntdll!RtlFreeHeap` at `0x1800c06d4`
- `ntdll!RtlSetThreadErrorMode` at `0x1800c046a`
- `ntdll!RtlSetThreadErrorMode` at `0x1800c04ac`
- `ntdll!RtlSetThreadErrorMode` at `0x1800c046a`
- `ntdll!RtlSetThreadErrorMode` at `0x1800c04ac`

## pseudocode

```c
BOOL __stdcall GetVolumeInformationW(
        LPCWSTR lpRootPathName,
        LPWSTR lpVolumeNameBuffer,
        DWORD nVolumeNameSize,
        LPDWORD lpVolumeSerialNumber,
        LPDWORD lpMaximumComponentLength,
        LPDWORD lpFileSystemFlags,
        LPWSTR lpFileSystemNameBuffer,
        DWORD nFileSystemNameSize)
{
  bool v10; // zf
  const WCHAR *v13; // rcx
  PWSTR Buffer; // rbx
  NTSTATUS v15; // edi
  NTSTATUS v16; // eax
  NTSTATUS v17; // edi
  BOOL VolumeInformationByHandleW; // ebx
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  ULONG OldMode; // [rsp+44h] [rbp-BCh] BYREF
  ULONG DataWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR v27; // [rsp+80h] [rbp-80h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES v29; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK v31; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD FileInformation[136]; // [rsp+110h] [rbp+10h] BYREF
  char v33; // [rsp+330h] [rbp+230h] BYREF

  v27 = lpFileSystemNameBuffer;
  FileHandle = 0;
  v10 = lpRootPathName == 0;
  OldMode = 0;
  v20 = 92;
  v13 = (const WCHAR *)&v20;
  if ( !v10 )
    v13 = lpRootPathName;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  if ( RtlDosPathNameToNtPathName_U(v13, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    if ( NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 1] != 92 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
      BaseSetLastNTError(3221225523LL);
      return 0;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    RtlSetThreadErrorMode(0x10u, &OldMode);
    v15 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
    RtlSetThreadErrorMode(OldMode, 0);
    if ( v15 < 0 )
    {
      BaseSetLastNTError((unsigned int)v15);
      goto LABEL_10;
    }
    SymbolicLinkHandle = 0;
    DataWritten = 0;
    v31 = 0;
    memset(&v29, 0, 44);
    LinkTarget = 0;
    if ( !FileHandle
      || NtQueryInformationFile(FileHandle, &v31, FileInformation, 0x218u, FileNameInformation) < 0
      || *((_WORD *)&FileInformation[1] + (unsigned int)((FileInformation[0] >> 1) - 1)) != 92 )
    {
      v29.Length = 48;
      NtPathName.Length -= 2;
      v29.RootDirectory = 0;
      v29.ObjectName = &NtPathName;
      v29.Attributes = 64;
      *(_OWORD *)&v29.SecurityDescriptor = 0;
      v16 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &v29);
      NtPathName.Length += 2;
      if ( v16 < 0
        || (LinkTarget.Buffer = (PWSTR)&v33,
            *(_DWORD *)&LinkTarget.Length = 68157440,
            DataWritten = 0,
            v17 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten),
            NtClose(SymbolicLinkHandle),
            v17 < 0) )
      {
        NtClose(FileHandle);
        RtlSetLastWin32Error(0x90u);
LABEL_10:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
        return 0;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    VolumeInformationByHandleW = GetVolumeInformationByHandleW(
                                   FileHandle,
                                   lpVolumeNameBuffer,
                                   nVolumeNameSize,
                                   lpVolumeSerialNumber,
                                   lpMaximumComponentLength,
                                   lpFileSystemFlags,
                                   v27,
                                   nFileSystemNameSize);
    NtClose(FileHandle);
    return VolumeInformationByHandleW;
  }
  else
  {
    RtlSetLastWin32Error(3u);
    return 0;
  }
}

```

## disassembly

```asm
0x1800c0370  push    rbp
0x1800c0372  push    rsi
0x1800c0373  push    rdi
0x1800c0374  push    r12
0x1800c0376  push    r13
0x1800c0378  push    r14
0x1800c037a  push    r15
0x1800c037c  lea     rbp, [rsp-660h]
0x1800c0384  sub     rsp, 760h
0x1800c038b  mov     rax, cs:__security_cookie
0x1800c0392  xor     rax, rsp
0x1800c0395  mov     [rbp+690h+var_50], rax
0x1800c039c  mov     rax, [rbp+690h+lpFileSystemNameBuffer]
0x1800c03a3  xorps   xmm0, xmm0
0x1800c03a6  mov     r12, [rbp+690h+lpMaximumComponentLength]
0x1800c03ad  mov     rsi, rdx
0x1800c03b0  mov     r13, [rbp+690h+lpFileSystemFlags]
0x1800c03b7  mov     rdx, rcx
0x1800c03ba  xor     edi, edi
0x1800c03bc  mov     [rbp+690h+var_710], rax
0x1800c03c0  xor     eax, eax
0x1800c03c2  mov     [rsp+790h+FileHandle], rdi
0x1800c03c7  test    rdx, rdx
0x1800c03ca  mov     [rsp+790h+OldMode], edi
0x1800c03ce  mov     r15, r9
0x1800c03d1  mov     [rsp+790h+var_750], 5Ch ; '\'
0x1800c03d9  mov     r14d, r8d
0x1800c03dc  lea     rcx, [rsp+790h+var_750]
0x1800c03e1  cmovnz  rcx, rdx; DosPathName
0x1800c03e5  xorps   xmm1, xmm1
0x1800c03e8  movups  xmmword ptr [rbp+690h+ObjectAttributes.ObjectName], xmm0
0x1800c03ec  xor     r9d, r9d; DirectoryInfo
0x1800c03ef  lea     rdx, [rsp+790h+NtPathName]; NtPathName
0x1800c03f4  xor     r8d, r8d; NtFileNamePart
0x1800c03f7  movups  xmmword ptr [rbp+690h+ObjectAttributes.Length], xmm0
0x1800c03fb  movups  xmmword ptr [rbp+690h+ObjectAttributes+1Ch], xmm0
0x1800c03ff  movups  xmmword ptr [rsp+790h+NtPathName.Length], xmm0
0x1800c0404  movups  xmmword ptr [rbp+690h+IoStatusBlock], xmm1
0x1800c0408  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800c040f  nop     dword ptr [rax+rax+00h]
0x1800c0414  test    al, al
0x1800c0416  jz      loc_1800C06AA
0x1800c041c  movzx   eax, [rsp+790h+NtPathName.Length]
0x1800c0421  mov     [rsp+790h+var_38], rbx
0x1800c0429  mov     rbx, [rsp+790h+NtPathName.Buffer]
0x1800c042e  shr     rax, 1
0x1800c0431  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800c0437  jnz     loc_1800C06C2
0x1800c043d  lea     rax, [rsp+790h+NtPathName]
0x1800c0442  mov     [rbp+690h+ObjectAttributes.Length], 30h ; '0'
0x1800c0449  xorps   xmm0, xmm0
0x1800c044c  mov     [rbp+690h+ObjectAttributes.ObjectName], rax
0x1800c0450  lea     rdx, [rsp+790h+OldMode]; OldMode
0x1800c0455  mov     [rbp+690h+ObjectAttributes.RootDirectory], rdi
0x1800c0459  mov     ecx, 10h; NewMode
0x1800c045e  mov     [rbp+690h+ObjectAttributes.Attributes], 40h ; '@'
0x1800c0465  movdqu  xmmword ptr [rbp+690h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c046a  call    cs:__imp_RtlSetThreadErrorMode
0x1800c0471  nop     dword ptr [rax+rax+00h]
0x1800c0476  lea     r9, [rbp+690h+IoStatusBlock]; IoStatusBlock
0x1800c047a  mov     [rsp+790h+OpenOptions], 4021h; OpenOptions
0x1800c0482  lea     r8, [rbp+690h+ObjectAttributes]; ObjectAttributes
0x1800c0486  mov     [rsp+790h+ShareAccess], 3; ShareAccess
0x1800c048e  mov     edx, 100000h; DesiredAccess
0x1800c0493  lea     rcx, [rsp+790h+FileHandle]; FileHandle
0x1800c0498  call    cs:__imp_NtOpenFile
0x1800c049f  nop     dword ptr [rax+rax+00h]
0x1800c04a4  mov     ecx, [rsp+790h+OldMode]; NewMode
0x1800c04a8  xor     edx, edx; OldMode
0x1800c04aa  mov     edi, eax
0x1800c04ac  call    cs:__imp_RtlSetThreadErrorMode
0x1800c04b3  nop     dword ptr [rax+rax+00h]
0x1800c04b8  test    edi, edi
0x1800c04ba  js      loc_1800C06EF
0x1800c04c0  mov     rcx, [rsp+790h+FileHandle]; FileHandle
0x1800c04c5  xorps   xmm0, xmm0
0x1800c04c8  xor     eax, eax
0x1800c04ca  mov     [rsp+790h+SymbolicLinkHandle], rax
0x1800c04cf  mov     [rsp+790h+DataWritten], eax
0x1800c04d3  movups  xmmword ptr [rbp+690h+var_6D8.ObjectName], xmm0
0x1800c04d7  movups  xmmword ptr [rbp+690h+var_6D8+1Ch], xmm0
0x1800c04db  movups  xmmword ptr [rbp+690h+var_698], xmm0
0x1800c04df  movups  xmmword ptr [rbp+690h+var_6D8.Length], xmm0
0x1800c04e3  movups  xmmword ptr [rsp+790h+LinkTarget.Length], xmm0
0x1800c04e8  test    rcx, rcx
0x1800c04eb  jnz     loc_1800C0605
0x1800c04f1  mov     eax, 0FFFEh
0x1800c04f6  mov     [rbp+690h+var_6D8.Length], 30h ; '0'
0x1800c04fd  add     [rsp+790h+NtPathName.Length], ax
0x1800c0502  lea     r8, [rbp+690h+var_6D8]; ObjectAttributes
0x1800c0506  lea     rax, [rsp+790h+NtPathName]
0x1800c050b  mov     [rbp+690h+var_6D8.RootDirectory], 0
0x1800c0513  xorps   xmm0, xmm0
0x1800c0516  mov     [rbp+690h+var_6D8.ObjectName], rax
0x1800c051a  mov     edx, 1; DesiredAccess
0x1800c051f  mov     [rbp+690h+var_6D8.Attributes], 40h ; '@'
0x1800c0526  lea     rcx, [rsp+790h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1800c052b  movdqu  xmmword ptr [rbp+690h+var_6D8.SecurityDescriptor], xmm0
0x1800c0530  call    cs:__imp_NtOpenSymbolicLinkObject
0x1800c0537  nop     dword ptr [rax+rax+00h]
0x1800c053c  add     [rsp+790h+NtPathName.Length], 2
0x1800c0542  test    eax, eax
0x1800c0544  js      short loc_1800C0598
0x1800c0546  mov     rcx, [rsp+790h+SymbolicLinkHandle]; SymLinkObjHandle
0x1800c054b  lea     rax, [rbp+690h+var_460]
0x1800c0552  lea     r8, [rsp+790h+DataWritten]; DataWritten
0x1800c0557  mov     [rsp+790h+LinkTarget.Buffer], rax
0x1800c055c  lea     rdx, [rsp+790h+LinkTarget]; LinkTarget
0x1800c0561  mov     dword ptr [rsp+790h+LinkTarget.Length], 4100000h
0x1800c0569  mov     [rsp+790h+DataWritten], 0
0x1800c0571  call    cs:__imp_NtQuerySymbolicLinkObject
0x1800c0578  nop     dword ptr [rax+rax+00h]
0x1800c057d  mov     rcx, [rsp+790h+SymbolicLinkHandle]; Handle
0x1800c0582  mov     edi, eax
0x1800c0584  call    cs:__imp_NtClose
0x1800c058b  nop     dword ptr [rax+rax+00h]
0x1800c0590  test    edi, edi
0x1800c0592  jns     loc_1800C0642
0x1800c0598  mov     rcx, [rsp+790h+FileHandle]; Handle
0x1800c059d  call    cs:__imp_NtClose
0x1800c05a4  nop     dword ptr [rax+rax+00h]
0x1800c05a9  mov     ecx, 90h; LastError
0x1800c05ae  call    cs:__imp_RtlSetLastWin32Error
0x1800c05b5  nop     dword ptr [rax+rax+00h]
0x1800c05ba  mov     rcx, gs:60h
0x1800c05c3  mov     r8, rbx; P
0x1800c05c6  xor     edx, edx; Flags
0x1800c05c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800c05cc  call    cs:__imp_RtlFreeHeap
0x1800c05d3  nop     dword ptr [rax+rax+00h]
0x1800c05d8  xor     eax, eax
0x1800c05da  mov     rbx, [rsp+790h+var_38]
0x1800c05e2  mov     rcx, [rbp+690h+var_50]
0x1800c05e9  xor     rcx, rsp; StackCookie
0x1800c05ec  call    __security_check_cookie
0x1800c05f1  add     rsp, 760h
0x1800c05f8  pop     r15
0x1800c05fa  pop     r14
0x1800c05fc  pop     r13
0x1800c05fe  pop     r12
0x1800c0600  pop     rdi
0x1800c0601  pop     rsi
0x1800c0602  pop     rbp
0x1800c0603  retn
0x1800c0605  mov     r9d, 218h; Length
0x1800c060b  mov     [rsp+790h+ShareAccess], 9; FileInformationClass
0x1800c0613  lea     r8, [rbp+690h+FileInformation]; FileInformation
0x1800c0617  lea     rdx, [rbp+690h+var_698]; IoStatusBlock
0x1800c061b  call    cs:__imp_NtQueryInformationFile
0x1800c0622  nop     dword ptr [rax+rax+00h]
0x1800c0627  test    eax, eax
0x1800c0629  js      loc_1800C04F1
0x1800c062f  mov     eax, [rbp+690h+FileInformation]
0x1800c0632  shr     eax, 1
0x1800c0634  dec     eax
0x1800c0636  cmp     [rbp+rax*2+690h+var_67C], 5Ch ; '\'
0x1800c063c  jnz     loc_1800C04F1
0x1800c0642  mov     rcx, gs:60h
0x1800c064b  mov     r8, rbx; P
0x1800c064e  xor     edx, edx; Flags
0x1800c0650  mov     rcx, [rcx+30h]; HeapHandle
0x1800c0654  call    cs:__imp_RtlFreeHeap
0x1800c065b  nop     dword ptr [rax+rax+00h]
0x1800c0660  mov     eax, [rbp+690h+nFileSystemNameSize]
0x1800c0666  mov     r9, r15; lpVolumeSerialNumber
0x1800c0669  mov     rcx, [rsp+790h+FileHandle]; hFile
0x1800c066e  mov     r8d, r14d; nVolumeNameSize
0x1800c0671  mov     [rsp+790h+var_758], eax; nFileSystemNameSize
0x1800c0675  mov     rdx, rsi; lpVolumeNameBuffer
0x1800c0678  mov     rax, [rbp+690h+var_710]
0x1800c067c  mov     [rsp+790h+var_760], rax; lpFileSystemNameBuffer
0x1800c0681  mov     qword ptr [rsp+790h+OpenOptions], r13; lpFileSystemFlags
0x1800c0686  mov     qword ptr [rsp+790h+ShareAccess], r12; lpMaximumComponentLength
0x1800c068b  call    GetVolumeInformationByHandleW
0x1800c0690  mov     rcx, [rsp+790h+FileHandle]; Handle
0x1800c0695  mov     ebx, eax
0x1800c0697  call    cs:__imp_NtClose
0x1800c069e  nop     dword ptr [rax+rax+00h]
0x1800c06a3  mov     eax, ebx
0x1800c06a5  jmp     loc_1800C05DA
0x1800c06aa  mov     ecx, 3; LastError
0x1800c06af  call    cs:__imp_RtlSetLastWin32Error
0x1800c06b6  nop     dword ptr [rax+rax+00h]
0x1800c06bb  xor     eax, eax
0x1800c06bd  jmp     loc_1800C05E2
0x1800c06c2  mov     rcx, gs:60h
0x1800c06cb  mov     r8, rbx; P
0x1800c06ce  xor     edx, edx; Flags
0x1800c06d0  mov     rcx, [rcx+30h]; HeapHandle
0x1800c06d4  call    cs:__imp_RtlFreeHeap
0x1800c06db  nop     dword ptr [rax+rax+00h]
0x1800c06e0  mov     ecx, 0C0000033h
0x1800c06e5  call    BaseSetLastNTError
0x1800c06ea  jmp     loc_1800C05D8
0x1800c06ef  mov     ecx, edi
0x1800c06f1  call    BaseSetLastNTError
0x1800c06f6  jmp     loc_1800C05BA
```
