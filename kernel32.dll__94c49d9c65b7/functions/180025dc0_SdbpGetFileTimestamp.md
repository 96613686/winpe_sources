# SdbpGetFileTimestamp

- ea: `0x180025dc0`
- end: `0x180026082`
- name: `SdbpGetFileTimestamp`
- size: `706`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800245a0`
- `0x180075148`

## callees

- `0x1800212e4`
- `0x180025dc0`
- `0x18005c414`
- `0x18007a7dd`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180025f63`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180025f63`
- `ntdll!NtQueryInformationFile` at `0x18002602a`
- `ntdll!NtQueryInformationFile` at `0x18002602a`
- `ntdll!ZwClose` at `0x180026077`
- `ntdll!ZwClose` at `0x180026077`
- `ntdll!ZwCreateFile` at `0x180025fd0`
- `ntdll!ZwCreateFile` at `0x180025fd0`
- `ntdll!RtlInitUnicodeString` at `0x180025e43`
- `ntdll!RtlInitUnicodeString` at `0x180025e43`
- `ntdll!RtlFreeHeap` at `0x180025f29`
- `ntdll!RtlFreeHeap` at `0x180025f29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025eac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025eac`

## string_xrefs

- `0x180025e74`: `ntdll.dll`
- `0x180025fe7`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v9; // eax
  NTSTATUS v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  NTSTATUS v14; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v22; // [rsp+D8h] [rbp-28h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  _BYTE v24[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v25; // [rsp+108h] [rbp+8h]

  v23 = 0;
  v16 = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v22 = 0;
  memset_0(v24, 0, 0x48u);
  P = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( wcsnicmp_0(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v10 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v16, 0, 0);
    if ( v10 < 0 )
      goto LABEL_11;
    p_DestinationString = (struct _UNICODE_STRING *)&v16;
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
    v9 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, _BYTE *, __int64, int))ProcAddress)(
           &ObjectAttributes,
           &IoStatusBlock,
           v24,
           72,
           68);
    v10 = v9;
    if ( v9 == -1073741772 )
      goto LABEL_11;
    if ( v9 >= 0 )
    {
      v11 = *((_QWORD *)&v25 + 1);
      v12 = v25;
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
    v10 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v10 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetFileTimestamp",
        1583,
        (unsigned int)"Failed to get timestamp from %S. [%x]");
      goto LABEL_11;
    }
    v11 = *((_QWORD *)&v22 + 1);
    v12 = v22;
    v25 = v22;
    goto LABEL_8;
  }
  if ( v14 != -1073741772 )
    AslLogCallPrintf(1, (unsigned int)"SdbpGetFileTimestamp", 1572, (unsigned int)"Failed to open file [%x]");
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
0x180025dc0  mov     [rsp-8+arg_10], rbx
0x180025dc5  mov     [rsp-8+arg_18], rsi
0x180025dca  push    rbp
0x180025dcb  push    rdi
0x180025dcc  push    r14
0x180025dce  lea     rbp, [rsp-50h]
0x180025dd3  sub     rsp, 150h
0x180025dda  mov     rax, cs:__security_cookie
0x180025de1  xor     rax, rsp
0x180025de4  mov     [rbp+60h+var_20], rax
0x180025de8  xorps   xmm0, xmm0
0x180025deb  xor     eax, eax
0x180025ded  xorps   xmm1, xmm1
0x180025df0  mov     [rbp+60h+var_78], rax
0x180025df4  mov     esi, r8d
0x180025df7  mov     [rsp+160h+var_F8], rax
0x180025dfc  mov     rdi, rdx
0x180025dff  mov     [rsp+160h+FileHandle], rax
0x180025e04  mov     r14, rcx
0x180025e07  lea     r8d, [rax+48h]; Size
0x180025e0b  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x180025e0f  xor     edx, edx; Val
0x180025e11  lea     rcx, [rbp+60h+var_70]; void *
0x180025e15  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180025e19  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x180025e1d  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x180025e21  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x180025e26  movups  [rbp+60h+FileInformation], xmm1
0x180025e2a  movups  [rbp+60h+var_88], xmm1
0x180025e2e  call    memset_0
0x180025e33  mov     rdx, rdi; SourceString
0x180025e36  mov     [rsp+160h+P], 0
0x180025e3f  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180025e43  call    cs:__imp_RtlInitUnicodeString
0x180025e49  mov     r8d, 0Ch; MaxCount
0x180025e4f  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x180025e56  mov     rcx, rdi; String1
0x180025e59  call    _wcsnicmp_0
0x180025e5e  test    eax, eax
0x180025e60  jnz     loc_180025F55
0x180025e66  lea     rax, [rbp+60h+DestinationString]
0x180025e6a  xorps   xmm0, xmm0
0x180025e6d  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180025e74  lea     rcx, ModuleName; "ntdll.dll"
0x180025e7b  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x180025e83  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025e88  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x180025e8f  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x180025e93  call    cs:__imp_GetModuleHandleW
0x180025e99  test    rax, rax
0x180025e9c  jz      loc_180025F79
0x180025ea2  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x180025ea9  mov     rcx, rax; hModule
0x180025eac  call    cs:__imp_GetProcAddress
0x180025eb2  test    rax, rax
0x180025eb5  jz      loc_180025F83
0x180025ebb  mov     r9d, 48h ; 'H'
0x180025ec1  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x180025ec9  lea     r8, [rbp+60h+var_70]
0x180025ecd  lea     rdx, [rsp+160h+IoStatusBlock]
0x180025ed2  lea     rcx, [rbp+60h+ObjectAttributes]
0x180025ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025edb  mov     ebx, eax
0x180025edd  cmp     eax, 0C0000034h
0x180025ee2  jz      short loc_180025EFF
0x180025ee4  test    eax, eax
0x180025ee6  js      loc_180025F83
0x180025eec  mov     rax, qword ptr [rbp+60h+var_58+8]
0x180025ef0  mov     rcx, qword ptr [rbp+60h+var_58]
0x180025ef4  test    esi, esi
0x180025ef6  cmovnz  rax, rcx
0x180025efa  xor     ebx, ebx
0x180025efc  mov     [r14], rax
0x180025eff  mov     rcx, [rsp+160h+FileHandle]; Handle
0x180025f04  test    rcx, rcx
0x180025f07  jnz     loc_180026077
0x180025f0d  cmp     [rsp+160h+P], 0
0x180025f13  jz      short loc_180025F2F
0x180025f15  mov     rcx, gs:60h
0x180025f1e  xor     edx, edx; Flags
0x180025f20  mov     r8, [rsp+160h+P]; P
0x180025f25  mov     rcx, [rcx+30h]; HeapHandle
0x180025f29  call    cs:__imp_RtlFreeHeap
0x180025f2f  mov     eax, ebx
0x180025f31  mov     rcx, [rbp+60h+var_20]
0x180025f35  xor     rcx, rsp; StackCookie
0x180025f38  call    __security_check_cookie
0x180025f3d  lea     r11, [rsp+160h+var_10]
0x180025f45  mov     rbx, [r11+30h]
0x180025f49  mov     rsi, [r11+38h]
0x180025f4d  mov     rsp, r11
0x180025f50  pop     r14
0x180025f52  pop     rdi
0x180025f53  pop     rbp
0x180025f54  retn
0x180025f55  xor     r9d, r9d
0x180025f58  lea     rdx, [rsp+160h+var_F8]
0x180025f5d  xor     r8d, r8d
0x180025f60  mov     rcx, rdi
0x180025f63  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180025f69  mov     ebx, eax
0x180025f6b  test    eax, eax
0x180025f6d  js      short loc_180025EFF
0x180025f6f  lea     rax, [rsp+160h+var_F8]
0x180025f74  jmp     loc_180025E6A
0x180025f79  mov     ebx, 0C0000001h
0x180025f7e  jmp     loc_180025EFF
0x180025f83  mov     [rsp+160h+EaLength], 0; EaLength
0x180025f8b  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x180025f90  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x180025f99  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180025f9d  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x180025fa5  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x180025faa  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x180025fb2  mov     edx, 80100080h; DesiredAccess
0x180025fb7  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x180025fbf  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x180025fc7  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x180025fd0  call    cs:__imp_ZwCreateFile
0x180025fd6  mov     ebx, eax
0x180025fd8  test    eax, eax
0x180025fda  jns     short loc_18002600E
0x180025fdc  cmp     eax, 0C0000034h
0x180025fe1  jz      loc_180025EFF
0x180025fe7  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x180025fee  mov     dword ptr [rsp+160h+AllocationSize], eax
0x180025ff2  mov     r8d, 624h
0x180025ff8  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x180025fff  mov     ecx, 1
0x180026004  call    AslLogCallPrintf
0x180026009  jmp     loc_180025EFF
0x18002600e  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x180026013  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x180026017  mov     r9d, 28h ; '('; Length
0x18002601d  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x180026025  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x18002602a  call    cs:__imp_NtQueryInformationFile
0x180026030  mov     ebx, eax
0x180026032  test    eax, eax
0x180026034  jns     short loc_180026062
0x180026036  mov     [rsp+160h+FileAttributes], eax
0x18002603a  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x180026041  mov     r8d, 62Fh
0x180026047  mov     [rsp+160h+AllocationSize], rdi
0x18002604c  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x180026053  mov     ecx, 1
0x180026058  call    AslLogCallPrintf
0x18002605d  jmp     loc_180025EFF
0x180026062  mov     rcx, qword ptr [rbp+60h+var_88]
0x180026066  mov     rax, qword ptr [rbp+60h+var_88+8]
0x18002606a  mov     qword ptr [rbp+60h+var_58], rcx
0x18002606e  mov     qword ptr [rbp+60h+var_58+8], rax
0x180026072  jmp     loc_180025EF4
0x180026077  call    cs:__imp_ZwClose
0x18002607d  jmp     loc_180025F0D
```
