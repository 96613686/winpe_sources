# SdbpGetFileTimestamp

- ea: `0x18005c9c4`
- end: `0x18005cc86`
- name: `SdbpGetFileTimestamp`
- size: `706`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a7bd4`
- `0x1800abcdc`

## callees

- `0x18004281c`
- `0x18005c9c4`
- `0x180075fa0`
- `0x180076e9c`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `ntdll!ZwCreateFile` at `0x18005cbd4`
- `ntdll!ZwCreateFile` at `0x18005cbd4`
- `ntdll!NtQueryInformationFile` at `0x18005cc2e`
- `ntdll!NtQueryInformationFile` at `0x18005cc2e`
- `ntdll!RtlInitUnicodeString` at `0x18005ca47`
- `ntdll!RtlInitUnicodeString` at `0x18005ca47`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005cb67`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005cb67`
- `ntdll!RtlFreeHeap` at `0x18005cb2d`
- `ntdll!RtlFreeHeap` at `0x18005cb2d`
- `ntdll!ZwClose` at `0x18005cc7b`
- `ntdll!ZwClose` at `0x18005cc7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cab0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cab0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ca97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ca97`

## string_xrefs

- `0x18005ca78`: `ntdll.dll`
- `0x18005cbeb`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v23; // [rsp+D8h] [rbp-28h]
  __int64 v24; // [rsp+E8h] [rbp-18h]
  _BYTE v25[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v26; // [rsp+108h] [rbp+8h]

  v24 = 0;
  v17 = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v23 = 0;
  memset_0(v25, 0, 0x48u);
  P = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v10 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v17, 0, 0);
    if ( v10 < 0 )
      goto LABEL_11;
    p_DestinationString = (struct _UNICODE_STRING *)&v17;
  }
  else
  {
    p_DestinationString = &DestinationString;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = p_DestinationString;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
  {
    v10 = -1073741823;
    goto LABEL_11;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryInformationByName");
  if ( ProcAddress )
  {
    v9 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, _IO_STATUS_BLOCK *, _BYTE *, __int64, int))ProcAddress)(
           &ObjectAttributes,
           &IoStatusBlock,
           v25,
           72,
           68);
    v10 = v9;
    if ( v9 == -1073741772 )
      goto LABEL_11;
    if ( v9 >= 0 )
    {
      v11 = *((_QWORD *)&v26 + 1);
      v12 = v26;
LABEL_8:
      if ( a3 )
        v11 = v12;
      v10 = 0;
      *a1 = v11;
      goto LABEL_11;
    }
  }
  v14 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x60u, 0, 0);
  v10 = v14;
  if ( v14 >= 0 )
  {
    v15 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    v10 = v15;
    if ( v15 < 0 )
    {
      AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1583, "Failed to get timestamp from %S. [%x]", a2, v15);
      goto LABEL_11;
    }
    v11 = *((_QWORD *)&v23 + 1);
    v12 = v23;
    v26 = v23;
    goto LABEL_8;
  }
  if ( v14 != -1073741772 )
    AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1572, "Failed to open file [%x]", v14);
LABEL_11:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005c9c4  mov     [rsp-8+arg_10], rbx
0x18005c9c9  mov     [rsp-8+arg_18], rsi
0x18005c9ce  push    rbp
0x18005c9cf  push    rdi
0x18005c9d0  push    r14
0x18005c9d2  lea     rbp, [rsp-50h]
0x18005c9d7  sub     rsp, 150h
0x18005c9de  mov     rax, cs:__security_cookie
0x18005c9e5  xor     rax, rsp
0x18005c9e8  mov     [rbp+60h+var_20], rax
0x18005c9ec  xorps   xmm0, xmm0
0x18005c9ef  xor     eax, eax
0x18005c9f1  xorps   xmm1, xmm1
0x18005c9f4  mov     [rbp+60h+var_78], rax
0x18005c9f8  mov     esi, r8d
0x18005c9fb  mov     [rsp+160h+var_F8], rax
0x18005ca00  mov     rdi, rdx
0x18005ca03  mov     [rsp+160h+FileHandle], rax
0x18005ca08  mov     r14, rcx
0x18005ca0b  lea     r8d, [rax+48h]; Size
0x18005ca0f  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x18005ca13  xor     edx, edx; Val
0x18005ca15  lea     rcx, [rbp+60h+var_70]; void *
0x18005ca19  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x18005ca1d  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x18005ca21  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x18005ca25  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x18005ca2a  movups  [rbp+60h+FileInformation], xmm1
0x18005ca2e  movups  [rbp+60h+var_88], xmm1
0x18005ca32  call    memset_0
0x18005ca37  mov     rdx, rdi; SourceString
0x18005ca3a  mov     [rsp+160h+P], 0
0x18005ca43  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18005ca47  call    cs:__imp_RtlInitUnicodeString
0x18005ca4d  mov     r8d, 0Ch; MaxCount
0x18005ca53  lea     rdx, aSystemroot_1; "\\SystemRoot\\"
0x18005ca5a  mov     rcx, rdi; String1
0x18005ca5d  call    _wcsnicmp
0x18005ca62  test    eax, eax
0x18005ca64  jnz     loc_18005CB59
0x18005ca6a  lea     rax, [rbp+60h+DestinationString]
0x18005ca6e  xorps   xmm0, xmm0
0x18005ca71  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x18005ca78  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18005ca7f  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x18005ca87  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005ca8c  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x18005ca93  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x18005ca97  call    cs:__imp_GetModuleHandleW
0x18005ca9d  test    rax, rax
0x18005caa0  jz      loc_18005CB7D
0x18005caa6  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x18005caad  mov     rcx, rax; hModule
0x18005cab0  call    cs:__imp_GetProcAddress
0x18005cab6  test    rax, rax
0x18005cab9  jz      loc_18005CB87
0x18005cabf  mov     r9d, 48h ; 'H'
0x18005cac5  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x18005cacd  lea     r8, [rbp+60h+var_70]
0x18005cad1  lea     rdx, [rsp+160h+IoStatusBlock]
0x18005cad6  lea     rcx, [rbp+60h+ObjectAttributes]
0x18005cada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cadf  mov     ebx, eax
0x18005cae1  cmp     eax, 0C0000034h
0x18005cae6  jz      short loc_18005CB03
0x18005cae8  test    eax, eax
0x18005caea  js      loc_18005CB87
0x18005caf0  mov     rax, qword ptr [rbp+60h+var_58+8]
0x18005caf4  mov     rcx, qword ptr [rbp+60h+var_58]
0x18005caf8  test    esi, esi
0x18005cafa  cmovnz  rax, rcx
0x18005cafe  xor     ebx, ebx
0x18005cb00  mov     [r14], rax
0x18005cb03  mov     rcx, [rsp+160h+FileHandle]; Handle
0x18005cb08  test    rcx, rcx
0x18005cb0b  jnz     loc_18005CC7B
0x18005cb11  cmp     [rsp+160h+P], 0
0x18005cb17  jz      short loc_18005CB33
0x18005cb19  mov     rcx, gs:60h
0x18005cb22  xor     edx, edx; Flags
0x18005cb24  mov     r8, [rsp+160h+P]; P
0x18005cb29  mov     rcx, [rcx+30h]; HeapHandle
0x18005cb2d  call    cs:__imp_RtlFreeHeap
0x18005cb33  mov     eax, ebx
0x18005cb35  mov     rcx, [rbp+60h+var_20]
0x18005cb39  xor     rcx, rsp; StackCookie
0x18005cb3c  call    __security_check_cookie
0x18005cb41  lea     r11, [rsp+160h+var_10]
0x18005cb49  mov     rbx, [r11+30h]
0x18005cb4d  mov     rsi, [r11+38h]
0x18005cb51  mov     rsp, r11
0x18005cb54  pop     r14
0x18005cb56  pop     rdi
0x18005cb57  pop     rbp
0x18005cb58  retn
0x18005cb59  xor     r9d, r9d
0x18005cb5c  lea     rdx, [rsp+160h+var_F8]
0x18005cb61  xor     r8d, r8d
0x18005cb64  mov     rcx, rdi
0x18005cb67  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18005cb6d  mov     ebx, eax
0x18005cb6f  test    eax, eax
0x18005cb71  js      short loc_18005CB03
0x18005cb73  lea     rax, [rsp+160h+var_F8]
0x18005cb78  jmp     loc_18005CA6E
0x18005cb7d  mov     ebx, 0C0000001h
0x18005cb82  jmp     loc_18005CB03
0x18005cb87  mov     [rsp+160h+EaLength], 0; EaLength
0x18005cb8f  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x18005cb94  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x18005cb9d  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x18005cba1  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x18005cba9  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x18005cbae  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x18005cbb6  mov     edx, 80100080h; DesiredAccess
0x18005cbbb  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x18005cbc3  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x18005cbcb  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x18005cbd4  call    cs:__imp_ZwCreateFile
0x18005cbda  mov     ebx, eax
0x18005cbdc  test    eax, eax
0x18005cbde  jns     short loc_18005CC12
0x18005cbe0  cmp     eax, 0C0000034h
0x18005cbe5  jz      loc_18005CB03
0x18005cbeb  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x18005cbf2  mov     dword ptr [rsp+160h+AllocationSize], eax
0x18005cbf6  mov     r8d, 624h
0x18005cbfc  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x18005cc03  mov     ecx, 1
0x18005cc08  call    AslLogCallPrintf
0x18005cc0d  jmp     loc_18005CB03
0x18005cc12  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x18005cc17  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x18005cc1b  mov     r9d, 28h ; '('; Length
0x18005cc21  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x18005cc29  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x18005cc2e  call    cs:__imp_NtQueryInformationFile
0x18005cc34  mov     ebx, eax
0x18005cc36  test    eax, eax
0x18005cc38  jns     short loc_18005CC66
0x18005cc3a  mov     [rsp+160h+FileAttributes], eax
0x18005cc3e  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x18005cc45  mov     r8d, 62Fh
0x18005cc4b  mov     [rsp+160h+AllocationSize], rdi
0x18005cc50  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x18005cc57  mov     ecx, 1
0x18005cc5c  call    AslLogCallPrintf
0x18005cc61  jmp     loc_18005CB03
0x18005cc66  mov     rcx, qword ptr [rbp+60h+var_88]
0x18005cc6a  mov     rax, qword ptr [rbp+60h+var_88+8]
0x18005cc6e  mov     qword ptr [rbp+60h+var_58], rcx
0x18005cc72  mov     qword ptr [rbp+60h+var_58+8], rax
0x18005cc76  jmp     loc_18005CAF8
0x18005cc7b  call    cs:__imp_ZwClose
0x18005cc81  jmp     loc_18005CB11
```
