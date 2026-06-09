# SdbpGetFileTimestamp

- ea: `0x180023c84`
- end: `0x180023f77`
- name: `SdbpGetFileTimestamp`
- size: `755`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800224f4`
- `0x18007ce9c`

## callees

- `0x18001f138`
- `0x180023c84`
- `0x180061df4`
- `0x18008275d`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180023e40`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180023e40`
- `ntdll!NtQueryInformationFile` at `0x180023f13`
- `ntdll!NtQueryInformationFile` at `0x180023f13`
- `ntdll!ZwClose` at `0x180023f66`
- `ntdll!ZwClose` at `0x180023f66`
- `ntdll!ZwCreateFile` at `0x180023eb3`
- `ntdll!ZwCreateFile` at `0x180023eb3`
- `ntdll!RtlInitUnicodeString` at `0x180023d07`
- `ntdll!RtlInitUnicodeString` at `0x180023d07`
- `ntdll!RtlFreeHeap` at `0x180023dff`
- `ntdll!RtlFreeHeap` at `0x180023dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023d5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023d5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d7c`

## string_xrefs

- `0x180023d3e`: `ntdll.dll`
- `0x180023ed0`: `Failed to open file [%x]`

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
        1581,
        (unsigned int)"Failed to get timestamp from %S. [%x]");
      goto LABEL_11;
    }
    v11 = *((_QWORD *)&v22 + 1);
    v12 = v22;
    v25 = v22;
    goto LABEL_8;
  }
  if ( v14 != -1073741772 )
    AslLogCallPrintf(1, (unsigned int)"SdbpGetFileTimestamp", 1570, (unsigned int)"Failed to open file [%x]");
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
0x180023c84  mov     [rsp-8+arg_10], rbx
0x180023c89  mov     [rsp-8+arg_18], rsi
0x180023c8e  push    rbp
0x180023c8f  push    rdi
0x180023c90  push    r14
0x180023c92  lea     rbp, [rsp-50h]
0x180023c97  sub     rsp, 150h
0x180023c9e  mov     rax, cs:__security_cookie
0x180023ca5  xor     rax, rsp
0x180023ca8  mov     [rbp+60h+var_20], rax
0x180023cac  xorps   xmm0, xmm0
0x180023caf  xor     eax, eax
0x180023cb1  xorps   xmm1, xmm1
0x180023cb4  mov     [rbp+60h+var_78], rax
0x180023cb8  mov     esi, r8d
0x180023cbb  mov     [rsp+160h+var_F8], rax
0x180023cc0  mov     rdi, rdx
0x180023cc3  mov     [rsp+160h+FileHandle], rax
0x180023cc8  mov     r14, rcx
0x180023ccb  lea     r8d, [rax+48h]; Size
0x180023ccf  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x180023cd3  xor     edx, edx; Val
0x180023cd5  lea     rcx, [rbp+60h+var_70]; void *
0x180023cd9  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180023cdd  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x180023ce1  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x180023ce5  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x180023cea  movups  [rbp+60h+FileInformation], xmm1
0x180023cee  movups  [rbp+60h+var_88], xmm1
0x180023cf2  call    memset_0
0x180023cf7  mov     rdx, rdi; SourceString
0x180023cfa  mov     [rsp+160h+P], 0
0x180023d03  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180023d07  call    cs:__imp_RtlInitUnicodeString
0x180023d0e  nop     dword ptr [rax+rax+00h]
0x180023d13  mov     r8d, 0Ch; MaxCount
0x180023d19  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x180023d20  mov     rcx, rdi; String1
0x180023d23  call    _wcsnicmp_0
0x180023d28  test    eax, eax
0x180023d2a  jnz     loc_180023E32
0x180023d30  lea     rax, [rbp+60h+DestinationString]
0x180023d34  xorps   xmm0, xmm0
0x180023d37  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180023d3e  lea     rcx, ModuleName; "ntdll.dll"
0x180023d45  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x180023d4d  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180023d52  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x180023d59  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x180023d5d  call    cs:__imp_GetModuleHandleW
0x180023d64  nop     dword ptr [rax+rax+00h]
0x180023d69  test    rax, rax
0x180023d6c  jz      loc_180023E5C
0x180023d72  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x180023d79  mov     rcx, rax; hModule
0x180023d7c  call    cs:__imp_GetProcAddress
0x180023d83  nop     dword ptr [rax+rax+00h]
0x180023d88  test    rax, rax
0x180023d8b  jz      loc_180023E66
0x180023d91  mov     r9d, 48h ; 'H'
0x180023d97  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x180023d9f  lea     r8, [rbp+60h+var_70]
0x180023da3  lea     rdx, [rsp+160h+IoStatusBlock]
0x180023da8  lea     rcx, [rbp+60h+ObjectAttributes]
0x180023dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023db1  mov     ebx, eax
0x180023db3  cmp     eax, 0C0000034h
0x180023db8  jz      short loc_180023DD5
0x180023dba  test    eax, eax
0x180023dbc  js      loc_180023E66
0x180023dc2  mov     rax, qword ptr [rbp+60h+var_58+8]
0x180023dc6  mov     rcx, qword ptr [rbp+60h+var_58]
0x180023dca  test    esi, esi
0x180023dcc  cmovnz  rax, rcx
0x180023dd0  xor     ebx, ebx
0x180023dd2  mov     [r14], rax
0x180023dd5  mov     rcx, [rsp+160h+FileHandle]; Handle
0x180023dda  test    rcx, rcx
0x180023ddd  jnz     loc_180023F66
0x180023de3  cmp     [rsp+160h+P], 0
0x180023de9  jz      short loc_180023E0B
0x180023deb  mov     rcx, gs:60h
0x180023df4  xor     edx, edx; Flags
0x180023df6  mov     r8, [rsp+160h+P]; P
0x180023dfb  mov     rcx, [rcx+30h]; HeapHandle
0x180023dff  call    cs:__imp_RtlFreeHeap
0x180023e06  nop     dword ptr [rax+rax+00h]
0x180023e0b  mov     eax, ebx
0x180023e0d  mov     rcx, [rbp+60h+var_20]
0x180023e11  xor     rcx, rsp; StackCookie
0x180023e14  call    __security_check_cookie
0x180023e19  lea     r11, [rsp+160h+var_10]
0x180023e21  mov     rbx, [r11+30h]
0x180023e25  mov     rsi, [r11+38h]
0x180023e29  mov     rsp, r11
0x180023e2c  pop     r14
0x180023e2e  pop     rdi
0x180023e2f  pop     rbp
0x180023e30  retn
0x180023e32  xor     r9d, r9d
0x180023e35  lea     rdx, [rsp+160h+var_F8]
0x180023e3a  xor     r8d, r8d
0x180023e3d  mov     rcx, rdi
0x180023e40  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180023e47  nop     dword ptr [rax+rax+00h]
0x180023e4c  mov     ebx, eax
0x180023e4e  test    eax, eax
0x180023e50  js      short loc_180023DD5
0x180023e52  lea     rax, [rsp+160h+var_F8]
0x180023e57  jmp     loc_180023D34
0x180023e5c  mov     ebx, 0C0000001h
0x180023e61  jmp     loc_180023DD5
0x180023e66  mov     [rsp+160h+EaLength], 0; EaLength
0x180023e6e  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x180023e73  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x180023e7c  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180023e80  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x180023e88  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x180023e8d  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x180023e95  mov     edx, 80100080h; DesiredAccess
0x180023e9a  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x180023ea2  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x180023eaa  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x180023eb3  call    cs:__imp_ZwCreateFile
0x180023eba  nop     dword ptr [rax+rax+00h]
0x180023ebf  mov     ebx, eax
0x180023ec1  test    eax, eax
0x180023ec3  jns     short loc_180023EF7
0x180023ec5  cmp     eax, 0C0000034h
0x180023eca  jz      loc_180023DD5
0x180023ed0  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x180023ed7  mov     dword ptr [rsp+160h+AllocationSize], eax
0x180023edb  mov     r8d, 622h
0x180023ee1  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x180023ee8  mov     ecx, 1
0x180023eed  call    AslLogCallPrintf
0x180023ef2  jmp     loc_180023DD5
0x180023ef7  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x180023efc  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x180023f00  mov     r9d, 28h ; '('; Length
0x180023f06  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x180023f0e  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x180023f13  call    cs:__imp_NtQueryInformationFile
0x180023f1a  nop     dword ptr [rax+rax+00h]
0x180023f1f  mov     ebx, eax
0x180023f21  test    eax, eax
0x180023f23  jns     short loc_180023F51
0x180023f25  mov     [rsp+160h+FileAttributes], eax
0x180023f29  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x180023f30  mov     r8d, 62Dh
0x180023f36  mov     [rsp+160h+AllocationSize], rdi
0x180023f3b  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x180023f42  mov     ecx, 1
0x180023f47  call    AslLogCallPrintf
0x180023f4c  jmp     loc_180023DD5
0x180023f51  mov     rcx, qword ptr [rbp+60h+var_88]
0x180023f55  mov     rax, qword ptr [rbp+60h+var_88+8]
0x180023f59  mov     qword ptr [rbp+60h+var_58], rcx
0x180023f5d  mov     qword ptr [rbp+60h+var_58+8], rax
0x180023f61  jmp     loc_180023DCA
0x180023f66  call    cs:__imp_ZwClose
0x180023f6d  nop     dword ptr [rax+rax+00h]
0x180023f72  jmp     loc_180023DE3
```
