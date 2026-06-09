# TermsrvPutSyncTime

- ea: `0x180055988`
- end: `0x180055e22`
- name: `TermsrvPutSyncTime`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004d650`

## callees

- `0x180035320`
- `0x180055988`
- `0x18005c390`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180055a57`
- `ntdll!RtlAppendUnicodeToString` at `0x180055a57`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180055a3e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180055a3e`
- `ntdll!NtWaitForSingleObject` at `0x180055bf8`
- `ntdll!NtWaitForSingleObject` at `0x180055d85`
- `ntdll!NtWaitForSingleObject` at `0x180055bf8`
- `ntdll!NtWaitForSingleObject` at `0x180055d85`
- `ntdll!NtClose` at `0x180055dee`
- `ntdll!NtClose` at `0x180055dee`
- `ntdll!wcslen` at `0x180055c3b`
- `ntdll!wcslen` at `0x180055c5a`
- `ntdll!wcslen` at `0x180055c3b`
- `ntdll!wcslen` at `0x180055c5a`
- `ntdll!NtQueryInformationFile` at `0x180055af7`
- `ntdll!NtQueryInformationFile` at `0x180055af7`
- `ntdll!NtSetInformationFile` at `0x180055d32`
- `ntdll!NtSetInformationFile` at `0x180055dbb`
- `ntdll!NtSetInformationFile` at `0x180055d32`
- `ntdll!NtSetInformationFile` at `0x180055dbb`
- `ntdll!NtCreateFile` at `0x180055acc`
- `ntdll!NtCreateFile` at `0x180055acc`
- `ntdll!NtFreeVirtualMemory` at `0x180055dde`
- `ntdll!NtFreeVirtualMemory` at `0x180055dde`
- `ntdll!NtWriteFile` at `0x180055d6c`
- `ntdll!NtWriteFile` at `0x180055d6c`
- `ntdll!NtReadFile` at `0x180055bdf`
- `ntdll!NtReadFile` at `0x180055bdf`
- `ntdll!NtAllocateVirtualMemory` at `0x180055b6d`
- `ntdll!NtAllocateVirtualMemory` at `0x180055b9a`
- `ntdll!NtAllocateVirtualMemory` at `0x180055cb5`
- `ntdll!NtAllocateVirtualMemory` at `0x180055b6d`
- `ntdll!NtAllocateVirtualMemory` at `0x180055b9a`
- `ntdll!NtAllocateVirtualMemory` at `0x180055cb5`
- `ntdll!_wcsicmp` at `0x180055c2c`
- `ntdll!_wcsicmp` at `0x180055c2c`

## pseudocode

```c
int __fastcall TermsrvPutSyncTime(const wchar_t **a1, const UNICODE_STRING *a2, _DWORD *a3)
{
  int result; // eax
  NTSTATUS Status; // ebx
  NTSTATUS v7; // eax
  unsigned int v8; // eax
  wchar_t *v9; // rdi
  wchar_t *v10; // rsi
  int v11; // ebx
  size_t v12; // rax
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r11
  PVOID BaseAddress; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG_PTR v17; // [rsp+70h] [rbp-90h] BYREF
  ULONG_PTR RegionSize; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-10h]
  char v26; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)&Destination.Length = 34209792;
  FileHandle = 0;
  BaseAddress = 0;
  v25 = 0;
  Destination.Buffer = (PWSTR)&v26;
  v17 = 0;
  RegionSize = 0;
  v21 = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( !a1 )
    return -1073741585;
  if ( !a2 )
    return -1073741584;
  if ( !a3 )
    return -1073741583;
  result = RtlAppendUnicodeStringToString(&Destination, a2);
  if ( result >= 0 )
  {
    result = RtlAppendUnicodeToString(&Destination, L"\\inifile.upd");
    if ( result >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &Destination;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      IoStatusBlock.Status = 0;
      Status = NtCreateFile(&FileHandle, 0x100083u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 3u, 0x60u, 0, 0);
      if ( Status < 0 )
        goto LABEL_39;
      v7 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      Status = v7;
      if ( v7 != -2147483643 && v7 < 0 )
        goto LABEL_39;
      v17 = DWORD2(FileInformation);
      if ( (unsigned __int64)DWORD2(FileInformation) + 8 <= DWORD2(FileInformation) )
        goto LABEL_13;
      v17 = DWORD2(FileInformation) + 8LL;
      RegionSize = v17;
      if ( (unsigned __int64)DWORD2(FileInformation) + 4104 < v17 )
        goto LABEL_13;
      RegionSize = DWORD2(FileInformation) + 4104LL;
      Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x2000u, 4u);
      if ( Status < 0 )
        goto LABEL_39;
      Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &v17, 0x1000u, 4u);
      if ( Status < 0 )
        goto LABEL_39;
      v8 = DWORD2(FileInformation);
      if ( DWORD2(FileInformation) )
      {
        Status = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, BaseAddress, DWORD2(FileInformation), 0, 0);
        if ( Status == 259 )
          Status = NtWaitForSingleObject(FileHandle, 0, 0);
        if ( Status < 0 )
          goto LABEL_39;
        Status = IoStatusBlock.Status;
        if ( IoStatusBlock.Status < 0 )
          goto LABEL_39;
        v8 = DWORD2(FileInformation);
      }
      v9 = (wchar_t *)BaseAddress;
      v10 = (wchar_t *)((char *)BaseAddress + v8);
      if ( BaseAddress < v10 )
      {
        do
        {
          v11 = _wcsicmp(v9, a1[1]);
          if ( v11 >= 0 )
            break;
          v9 += wcslen(v9) + 5;
        }
        while ( v9 < v10 );
        if ( v9 < v10 && !v11 )
        {
          v12 = wcslen(v9);
          *(_DWORD *)&v9[v12 + 1] = *a3;
          *(_DWORD *)&v9[v12 + 3] = a3[1];
LABEL_34:
          v20 = 0;
          NtSetInformationFile(FileHandle, &IoStatusBlock, &v20, 8u, FilePositionInformation);
          Status = NtWriteFile(
                     FileHandle,
                     0,
                     0,
                     0,
                     &IoStatusBlock,
                     BaseAddress,
                     (_DWORD)v10 - (_DWORD)BaseAddress + 1,
                     0,
                     0);
          if ( Status == 259 )
            Status = NtWaitForSingleObject(FileHandle, 0, 0);
          if ( Status >= 0 )
          {
            Status = IoStatusBlock.Status;
            if ( IoStatusBlock.Status >= 0 )
            {
              v21 = (unsigned int)((_DWORD)v10 - (_DWORD)BaseAddress);
              Status = NtSetInformationFile(FileHandle, &IoStatusBlock, &v21, 8u, FileEndOfFileInformation);
            }
          }
          goto LABEL_39;
        }
      }
      v13 = *(unsigned __int16 *)a1 + 10LL;
      if ( v13 + v17 < v17 )
      {
LABEL_13:
        Status = -1073741582;
      }
      else
      {
        v17 += v13;
        Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &v17, 0x1000u, 4u);
        if ( Status >= 0 )
        {
          if ( v9 < v10 )
            memmove_0(&v9[v13 >> 1], v9, (char *)v10 - (char *)v9);
          LODWORD(v10) = v13 + (_DWORD)v10;
          StringCbCopyW(v9, v13 - 8, a1[1]);
          v14 = ((unsigned __int64)*(unsigned __int16 *)a1 + 2) >> 1;
          *(_DWORD *)&v9[v14] = *a3;
          *(_DWORD *)&v9[v14 + 2] = a3[1];
          goto LABEL_34;
        }
      }
LABEL_39:
      if ( BaseAddress )
        NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
      if ( FileHandle )
        return NtClose(FileHandle);
      return Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055988  mov     [rsp-8+arg_10], rbx
0x18005598d  push    rbp
0x18005598e  push    rsi
0x18005598f  push    rdi
0x180055990  push    r12
0x180055992  push    r13
0x180055994  push    r14
0x180055996  push    r15
0x180055998  lea     rbp, [rsp-220h]
0x1800559a0  sub     rsp, 320h
0x1800559a7  mov     rax, cs:__security_cookie
0x1800559ae  xor     rax, rsp
0x1800559b1  mov     [rbp+250h+var_40], rax
0x1800559b8  xor     r12d, r12d
0x1800559bb  mov     qword ptr [rbp+250h+Destination.Length], 20A0000h
0x1800559c3  xorps   xmm0, xmm0
0x1800559c6  mov     [rsp+350h+FileHandle], r12
0x1800559cb  xor     eax, eax
0x1800559cd  mov     [rsp+350h+BaseAddress], r12
0x1800559d2  mov     [rbp+250h+var_260], rax
0x1800559d6  lea     rax, [rbp+250h+var_250]
0x1800559da  mov     [rbp+250h+Destination.Buffer], rax
0x1800559de  xorps   xmm1, xmm1
0x1800559e1  mov     [rsp+350h+var_2E0], r12
0x1800559e6  mov     r15, r8
0x1800559e9  mov     [rsp+350h+RegionSize], r12
0x1800559ee  mov     r13, rcx
0x1800559f1  mov     [rbp+250h+var_2B8], r12
0x1800559f5  mov     [rbp+250h+var_2C0], r12
0x1800559f9  movups  xmmword ptr [rbp+250h+ObjectAttributes.ObjectName], xmm0
0x1800559fd  movups  xmmword ptr [rbp+250h+ObjectAttributes.Length], xmm0
0x180055a01  movups  xmmword ptr [rbp+250h+ObjectAttributes+1Ch], xmm0
0x180055a05  movups  xmmword ptr [rbp+250h+IoStatusBlock], xmm0
0x180055a09  movups  [rbp+250h+FileInformation], xmm1
0x180055a0d  test    rcx, rcx
0x180055a10  jnz     short loc_180055A1C
0x180055a12  mov     eax, 0C00000EFh
0x180055a17  jmp     loc_180055DF8
0x180055a1c  test    rdx, rdx
0x180055a1f  jnz     short loc_180055A2B
0x180055a21  mov     eax, 0C00000F0h
0x180055a26  jmp     loc_180055DF8
0x180055a2b  test    r15, r15
0x180055a2e  jnz     short loc_180055A3A
0x180055a30  mov     eax, 0C00000F1h
0x180055a35  jmp     loc_180055DF8
0x180055a3a  lea     rcx, [rbp+250h+Destination]; Destination
0x180055a3e  call    cs:__imp_RtlAppendUnicodeStringToString
0x180055a44  test    eax, eax
0x180055a46  js      loc_180055DF8
0x180055a4c  lea     rdx, aInifileUpd; "\\inifile.upd"
0x180055a53  lea     rcx, [rbp+250h+Destination]; Destination
0x180055a57  call    cs:__imp_RtlAppendUnicodeToString
0x180055a5d  test    eax, eax
0x180055a5f  js      loc_180055DF8
0x180055a65  mov     [rsp+350h+EaLength], r12d; EaLength
0x180055a6a  lea     rax, [rbp+250h+Destination]
0x180055a6e  mov     [rsp+350h+EaBuffer], r12; EaBuffer
0x180055a73  lea     r9, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x180055a77  mov     [rsp+350h+CreateOptions], 60h ; '`'; CreateOptions
0x180055a7f  lea     r8, [rbp+250h+ObjectAttributes]; ObjectAttributes
0x180055a83  mov     [rsp+350h+CreateDisposition], 3; CreateDisposition
0x180055a8b  lea     rcx, [rsp+350h+FileHandle]; FileHandle
0x180055a90  mov     [rsp+350h+ShareAccess], 2; ShareAccess
0x180055a98  xorps   xmm0, xmm0
0x180055a9b  mov     [rsp+350h+FileAttributes], 80h; FileAttributes
0x180055aa3  mov     edx, 100083h; DesiredAccess
0x180055aa8  mov     [rsp+350h+AllocationSize], r12; AllocationSize
0x180055aad  mov     [rbp+250h+ObjectAttributes.Length], 30h ; '0'
0x180055ab4  mov     [rbp+250h+ObjectAttributes.RootDirectory], r12
0x180055ab8  mov     [rbp+250h+ObjectAttributes.Attributes], 40h ; '@'
0x180055abf  mov     [rbp+250h+ObjectAttributes.ObjectName], rax
0x180055ac3  movdqu  xmmword ptr [rbp+250h+ObjectAttributes.SecurityDescriptor], xmm0
0x180055ac8  mov     dword ptr [rbp+250h+IoStatusBlock], r12d
0x180055acc  call    cs:__imp_NtCreateFile
0x180055ad2  mov     ebx, eax
0x180055ad4  test    eax, eax
0x180055ad6  js      loc_180055DC3
0x180055adc  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x180055ae1  lea     r8, [rbp+250h+FileInformation]; FileInformation
0x180055ae5  mov     r9d, 18h; Length
0x180055aeb  mov     dword ptr [rsp+350h+AllocationSize], 5; FileInformationClass
0x180055af3  lea     rdx, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x180055af7  call    cs:__imp_NtQueryInformationFile
0x180055afd  mov     ebx, eax
0x180055aff  cmp     eax, 80000005h
0x180055b04  jz      short loc_180055B0E
0x180055b06  test    eax, eax
0x180055b08  js      loc_180055DC3
0x180055b0e  mov     eax, dword ptr [rbp+250h+FileInformation+8]
0x180055b11  mov     [rsp+350h+var_2E0], rax
0x180055b16  lea     rcx, [rax+8]
0x180055b1a  cmp     rcx, rax
0x180055b1d  ja      short loc_180055B29
0x180055b1f  mov     ebx, 0C00000F2h
0x180055b24  jmp     loc_180055DC3
0x180055b29  lea     rax, [rcx+1000h]
0x180055b30  mov     [rsp+350h+var_2E0], rcx
0x180055b35  mov     [rsp+350h+RegionSize], rcx
0x180055b3a  cmp     rax, rcx
0x180055b3d  jbe     short loc_180055B1F
0x180055b3f  lea     rax, [rcx+1000h]
0x180055b46  mov     edi, 4
0x180055b4b  mov     [rsp+350h+FileAttributes], edi; Protect
0x180055b4f  lea     r9, [rsp+350h+RegionSize]; RegionSize
0x180055b54  xor     r8d, r8d; ZeroBits
0x180055b57  mov     dword ptr [rsp+350h+AllocationSize], 2000h; AllocationType
0x180055b5f  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x180055b64  mov     [rsp+350h+RegionSize], rax
0x180055b69  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055b6d  call    cs:__imp_NtAllocateVirtualMemory
0x180055b73  mov     ebx, eax
0x180055b75  test    eax, eax
0x180055b77  js      loc_180055DC3
0x180055b7d  mov     [rsp+350h+FileAttributes], edi; Protect
0x180055b81  lea     r9, [rsp+350h+var_2E0]; RegionSize
0x180055b86  xor     r8d, r8d; ZeroBits
0x180055b89  mov     dword ptr [rsp+350h+AllocationSize], 1000h; AllocationType
0x180055b91  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x180055b96  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055b9a  call    cs:__imp_NtAllocateVirtualMemory
0x180055ba0  mov     ebx, eax
0x180055ba2  test    eax, eax
0x180055ba4  js      loc_180055DC3
0x180055baa  mov     eax, dword ptr [rbp+250h+FileInformation+8]
0x180055bad  test    eax, eax
0x180055baf  jz      short loc_180055C16
0x180055bb1  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x180055bb6  xor     r9d, r9d; ApcContext
0x180055bb9  mov     qword ptr [rsp+350h+CreateOptions], r12; Key
0x180055bbe  xor     r8d, r8d; ApcRoutine
0x180055bc1  mov     qword ptr [rsp+350h+CreateDisposition], r12; ByteOffset
0x180055bc6  xor     edx, edx; Event
0x180055bc8  mov     [rsp+350h+ShareAccess], eax; Length
0x180055bcc  mov     rax, [rsp+350h+BaseAddress]
0x180055bd1  mov     qword ptr [rsp+350h+FileAttributes], rax; Buffer
0x180055bd6  lea     rax, [rbp+250h+IoStatusBlock]
0x180055bda  mov     [rsp+350h+AllocationSize], rax; IoStatusBlock
0x180055bdf  call    cs:__imp_NtReadFile
0x180055be5  mov     ebx, eax
0x180055be7  cmp     eax, 103h
0x180055bec  jnz     short loc_180055C00
0x180055bee  mov     rcx, [rsp+350h+FileHandle]; Handle
0x180055bf3  xor     r8d, r8d; Timeout
0x180055bf6  xor     edx, edx; Alertable
0x180055bf8  call    cs:__imp_NtWaitForSingleObject
0x180055bfe  mov     ebx, eax
0x180055c00  test    ebx, ebx
0x180055c02  js      loc_180055DC3
0x180055c08  mov     ebx, dword ptr [rbp+250h+IoStatusBlock]
0x180055c0b  test    ebx, ebx
0x180055c0d  js      loc_180055DC3
0x180055c13  mov     eax, dword ptr [rbp+250h+FileInformation+8]
0x180055c16  mov     rdi, [rsp+350h+BaseAddress]
0x180055c1b  mov     esi, eax
0x180055c1d  add     rsi, rdi
0x180055c20  cmp     rdi, rsi
0x180055c23  jnb     short loc_180055C74
0x180055c25  mov     rdx, [r13+8]; String2
0x180055c29  mov     rcx, rdi; String1
0x180055c2c  call    cs:__imp__wcsicmp
0x180055c32  mov     ebx, eax
0x180055c34  test    eax, eax
0x180055c36  jns     short loc_180055C4E
0x180055c38  mov     rcx, rdi; String
0x180055c3b  call    cs:__imp_wcslen
0x180055c41  lea     rdi, [rdi+rax*2]
0x180055c45  add     rdi, 0Ah
0x180055c49  cmp     rdi, rsi
0x180055c4c  jb      short loc_180055C25
0x180055c4e  cmp     rdi, rsi
0x180055c51  jnb     short loc_180055C74
0x180055c53  test    ebx, ebx
0x180055c55  jnz     short loc_180055C74
0x180055c57  mov     rcx, rdi; String
0x180055c5a  call    cs:__imp_wcslen
0x180055c60  mov     ecx, [r15]
0x180055c63  mov     [rdi+rax*2+2], ecx
0x180055c67  mov     ecx, [r15+4]
0x180055c6b  mov     [rdi+rax*2+6], ecx
0x180055c6f  jmp     loc_180055D11
0x180055c74  mov     rax, [rsp+350h+var_2E0]
0x180055c79  movzx   r14d, word ptr [r13+0]
0x180055c7e  add     r14, 0Ah
0x180055c82  lea     rcx, [r14+rax]
0x180055c86  cmp     rcx, rax
0x180055c89  jb      loc_180055B1F
0x180055c8f  mov     [rsp+350h+var_2E0], rcx
0x180055c94  lea     r9, [rsp+350h+var_2E0]; RegionSize
0x180055c99  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055c9d  mov     [rsp+350h+FileAttributes], 4; Protect
0x180055ca5  xor     r8d, r8d; ZeroBits
0x180055ca8  mov     dword ptr [rsp+350h+AllocationSize], 1000h; AllocationType
0x180055cb0  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x180055cb5  call    cs:__imp_NtAllocateVirtualMemory
0x180055cbb  mov     ebx, eax
0x180055cbd  test    eax, eax
0x180055cbf  js      loc_180055DC3
0x180055cc5  cmp     rdi, rsi
0x180055cc8  jnb     short loc_180055CE2
0x180055cca  mov     rax, r14
0x180055ccd  mov     r8, rsi
0x180055cd0  shr     rax, 1
0x180055cd3  sub     r8, rdi; Size
0x180055cd6  mov     rdx, rdi; Src
0x180055cd9  lea     rcx, [rdi+rax*2]; void *
0x180055cdd  call    memmove_0
0x180055ce2  mov     r8, [r13+8]; pszSrc
0x180055ce6  lea     rdx, [r14-8]; cbDest
0x180055cea  mov     rcx, rdi; pszDest
0x180055ced  add     rsi, r14
0x180055cf0  call    StringCbCopyW
0x180055cf5  movzx   r11d, word ptr [r13+0]
0x180055cfa  mov     eax, [r15]
0x180055cfd  add     r11, 2
0x180055d01  shr     r11, 1
0x180055d04  mov     [rdi+r11*2], eax
0x180055d08  mov     eax, [r15+4]
0x180055d0c  mov     [rdi+r11*2+4], eax
0x180055d11  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x180055d16  lea     r8, [rbp+250h+var_2C0]; FileInformation
0x180055d1a  mov     edi, 8
0x180055d1f  mov     [rbp+250h+var_2C0], r12
0x180055d23  mov     r9d, edi; Length
0x180055d26  mov     dword ptr [rsp+350h+AllocationSize], 0Eh; FileInformationClass
0x180055d2e  lea     rdx, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x180055d32  call    cs:__imp_NtSetInformationFile
0x180055d38  mov     rax, [rsp+350h+BaseAddress]
0x180055d3d  mov     ecx, esi
0x180055d3f  sub     ecx, eax
0x180055d41  mov     qword ptr [rsp+350h+CreateOptions], r12; Key
0x180055d46  inc     ecx
0x180055d48  mov     qword ptr [rsp+350h+CreateDisposition], r12; ByteOffset
0x180055d4d  mov     [rsp+350h+ShareAccess], ecx; Length
0x180055d51  xor     r9d, r9d; ApcContext
0x180055d54  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x180055d59  xor     r8d, r8d; ApcRoutine
0x180055d5c  mov     qword ptr [rsp+350h+FileAttributes], rax; Buffer
0x180055d61  xor     edx, edx; Event
0x180055d63  lea     rax, [rbp+250h+IoStatusBlock]
0x180055d67  mov     [rsp+350h+AllocationSize], rax; IoStatusBlock
0x180055d6c  call    cs:__imp_NtWriteFile
0x180055d72  mov     ebx, eax
0x180055d74  cmp     eax, 103h
0x180055d79  jnz     short loc_180055D8D
0x180055d7b  mov     rcx, [rsp+350h+FileHandle]; Handle
0x180055d80  xor     r8d, r8d; Timeout
0x180055d83  xor     edx, edx; Alertable
0x180055d85  call    cs:__imp_NtWaitForSingleObject
0x180055d8b  mov     ebx, eax
0x180055d8d  test    ebx, ebx
0x180055d8f  js      short loc_180055DC3
0x180055d91  mov     ebx, dword ptr [rbp+250h+IoStatusBlock]
0x180055d94  test    ebx, ebx
0x180055d96  js      short loc_180055DC3
0x180055d98  sub     esi, dword ptr [rsp+350h+BaseAddress]
0x180055d9c  lea     r8, [rbp+250h+var_2B8]; FileInformation
0x180055da0  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x180055da5  lea     rdx, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x180055da9  mov     r9d, edi; Length
0x180055dac  mov     dword ptr [rbp+250h+var_2B8], esi
0x180055daf  mov     dword ptr [rbp+250h+var_2B8+4], r12d
0x180055db3  mov     dword ptr [rsp+350h+AllocationSize], 14h; FileInformationClass
0x180055dbb  call    cs:__imp_NtSetInformationFile
0x180055dc1  mov     ebx, eax
0x180055dc3  cmp     [rsp+350h+BaseAddress], r12
0x180055dc8  jz      short loc_180055DE4
0x180055dca  mov     r9d, 8000h; FreeType
0x180055dd0  lea     r8, [rsp+350h+RegionSize]; RegionSize
0x180055dd5  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x180055dda  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055dde  call    cs:__imp_NtFreeVirtualMemory
0x180055de4  mov     rcx, [rsp+350h+FileHandle]; Handle
0x180055de9  test    rcx, rcx
0x180055dec  jz      short loc_180055DF6
0x180055dee  call    cs:__imp_NtClose
0x180055df4  mov     ebx, eax
0x180055df6  mov     eax, ebx
0x180055df8  mov     rcx, [rbp+250h+var_40]
0x180055dff  xor     rcx, rsp; StackCookie
0x180055e02  call    __security_check_cookie
0x180055e07  mov     rbx, [rsp+350h+arg_10]
0x180055e0f  add     rsp, 320h
0x180055e16  pop     r15
0x180055e18  pop     r14
0x180055e1a  pop     r13
0x180055e1c  pop     r12
0x180055e1e  pop     rdi
0x180055e1f  pop     rsi
0x180055e20  pop     rbp
0x180055e21  retn
```
