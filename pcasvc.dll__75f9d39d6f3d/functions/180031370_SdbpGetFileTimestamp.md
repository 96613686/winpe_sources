# SdbpGetFileTimestamp

- ea: `0x180031370`
- end: `0x18003162e`
- name: `SdbpGetFileTimestamp`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e47a0`
- `0x1800e987c`

## callees

- `0x180012920`
- `0x180031370`
- `0x18007a9cf`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180031409`
- `msvcrt!_wcsnicmp` at `0x180031409`
- `ntdll!NtQueryInformationFile` at `0x1800315d6`
- `ntdll!NtQueryInformationFile` at `0x1800315d6`
- `ntdll!ZwClose` at `0x180031623`
- `ntdll!ZwClose` at `0x180031623`
- `ntdll!RtlFreeHeap` at `0x1800314da`
- `ntdll!RtlFreeHeap` at `0x1800314da`
- `ntdll!RtlInitUnicodeString` at `0x1800313f3`
- `ntdll!RtlInitUnicodeString` at `0x1800313f3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180031425`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180031425`
- `ntdll!ZwCreateFile` at `0x18003157c`
- `ntdll!ZwCreateFile` at `0x18003157c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003145f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003145f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031478`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031478`

## string_xrefs

- `0x180031440`: `ntdll.dll`
- `0x180031593`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v10; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
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
  if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v16, 0, 0);
    if ( v6 < 0 )
      goto LABEL_7;
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
    v6 = -1073741823;
    goto LABEL_7;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryInformationByName");
  if ( ProcAddress )
  {
    v10 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, _BYTE *, __int64, int))ProcAddress)(
            &ObjectAttributes,
            &IoStatusBlock,
            v24,
            72,
            68);
    v6 = v10;
    if ( v10 == -1073741772 )
      goto LABEL_7;
    if ( v10 >= 0 )
    {
      v12 = *((_QWORD *)&v25 + 1);
      v13 = v25;
LABEL_14:
      if ( a3 )
        v12 = v13;
      v6 = 0;
      *a1 = v12;
      goto LABEL_7;
    }
  }
  v14 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x60u, 0, 0);
  v6 = v14;
  if ( v14 >= 0 )
  {
    v6 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v6 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetFileTimestamp",
        1583,
        (unsigned int)"Failed to get timestamp from %S. [%x]");
      goto LABEL_7;
    }
    v12 = *((_QWORD *)&v22 + 1);
    v13 = v22;
    v25 = v22;
    goto LABEL_14;
  }
  if ( v14 != -1073741772 )
    AslLogCallPrintf(1, (unsigned int)"SdbpGetFileTimestamp", 1572, (unsigned int)"Failed to open file [%x]");
LABEL_7:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180031370  mov     [rsp-8+arg_10], rbx
0x180031375  mov     [rsp-8+arg_18], rsi
0x18003137a  push    rbp
0x18003137b  push    rdi
0x18003137c  push    r14
0x18003137e  lea     rbp, [rsp-50h]
0x180031383  sub     rsp, 150h
0x18003138a  mov     rax, cs:__security_cookie
0x180031391  xor     rax, rsp
0x180031394  mov     [rbp+60h+var_20], rax
0x180031398  xorps   xmm0, xmm0
0x18003139b  xor     eax, eax
0x18003139d  xorps   xmm1, xmm1
0x1800313a0  mov     [rbp+60h+var_78], rax
0x1800313a4  mov     esi, r8d
0x1800313a7  mov     [rsp+160h+var_F8], rax
0x1800313ac  mov     rdi, rdx
0x1800313af  mov     [rsp+160h+FileHandle], rax
0x1800313b4  mov     r14, rcx
0x1800313b7  lea     r8d, [rax+48h]; Size
0x1800313bb  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1800313bf  xor     edx, edx; Val
0x1800313c1  lea     rcx, [rbp+60h+var_70]; void *
0x1800313c5  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800313c9  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1800313cd  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x1800313d1  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x1800313d6  movups  [rbp+60h+FileInformation], xmm1
0x1800313da  movups  [rbp+60h+var_88], xmm1
0x1800313de  call    memset_0
0x1800313e3  mov     rdx, rdi; SourceString
0x1800313e6  mov     [rsp+160h+P], 0
0x1800313ef  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1800313f3  call    cs:__imp_RtlInitUnicodeString
0x1800313f9  mov     r8d, 0Ch; MaxCount
0x1800313ff  lea     rdx, aSystemroot_6; "\\SystemRoot\\"
0x180031406  mov     rcx, rdi; String1
0x180031409  call    cs:__imp__wcsnicmp
0x18003140f  test    eax, eax
0x180031411  jz      loc_18003151F
0x180031417  xor     r9d, r9d
0x18003141a  lea     rdx, [rsp+160h+var_F8]
0x18003141f  xor     r8d, r8d
0x180031422  mov     rcx, rdi
0x180031425  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18003142b  mov     ebx, eax
0x18003142d  test    eax, eax
0x18003142f  js      short loc_1800314B0
0x180031431  lea     rax, [rsp+160h+var_F8]
0x180031436  xorps   xmm0, xmm0
0x180031439  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180031440  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180031447  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x18003144f  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180031454  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x18003145b  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x18003145f  call    cs:__imp_GetModuleHandleW
0x180031465  test    rax, rax
0x180031468  jz      loc_180031528
0x18003146e  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x180031475  mov     rcx, rax; hModule
0x180031478  call    cs:__imp_GetProcAddress
0x18003147e  test    rax, rax
0x180031481  jz      loc_18003152F
0x180031487  mov     r9d, 48h ; 'H'
0x18003148d  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x180031495  lea     r8, [rbp+60h+var_70]
0x180031499  lea     rdx, [rsp+160h+IoStatusBlock]
0x18003149e  lea     rcx, [rbp+60h+ObjectAttributes]
0x1800314a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314a7  mov     ebx, eax
0x1800314a9  cmp     eax, 0C0000034h
0x1800314ae  jnz     short loc_180031506
0x1800314b0  mov     rcx, [rsp+160h+FileHandle]; Handle
0x1800314b5  test    rcx, rcx
0x1800314b8  jnz     loc_180031623
0x1800314be  cmp     [rsp+160h+P], 0
0x1800314c4  jz      short loc_1800314E0
0x1800314c6  mov     rcx, gs:60h
0x1800314cf  xor     edx, edx; Flags
0x1800314d1  mov     r8, [rsp+160h+P]; P
0x1800314d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800314da  call    cs:__imp_RtlFreeHeap
0x1800314e0  mov     eax, ebx
0x1800314e2  mov     rcx, [rbp+60h+var_20]
0x1800314e6  xor     rcx, rsp; StackCookie
0x1800314e9  call    __security_check_cookie
0x1800314ee  lea     r11, [rsp+160h+var_10]
0x1800314f6  mov     rbx, [r11+30h]
0x1800314fa  mov     rsi, [r11+38h]
0x1800314fe  mov     rsp, r11
0x180031501  pop     r14
0x180031503  pop     rdi
0x180031504  pop     rbp
0x180031505  retn
0x180031506  test    eax, eax
0x180031508  js      short loc_18003152F
0x18003150a  mov     rax, qword ptr [rbp+60h+var_58+8]
0x18003150e  mov     rcx, qword ptr [rbp+60h+var_58]
0x180031512  test    esi, esi
0x180031514  cmovnz  rax, rcx
0x180031518  xor     ebx, ebx
0x18003151a  mov     [r14], rax
0x18003151d  jmp     short loc_1800314B0
0x18003151f  lea     rax, [rbp+60h+DestinationString]
0x180031523  jmp     loc_180031436
0x180031528  mov     ebx, 0C0000001h
0x18003152d  jmp     short loc_1800314B0
0x18003152f  mov     [rsp+160h+EaLength], 0; EaLength
0x180031537  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x18003153c  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x180031545  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180031549  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x180031551  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x180031556  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x18003155e  mov     edx, 80100080h; DesiredAccess
0x180031563  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x18003156b  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x180031573  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x18003157c  call    cs:__imp_ZwCreateFile
0x180031582  mov     ebx, eax
0x180031584  test    eax, eax
0x180031586  jns     short loc_1800315BA
0x180031588  cmp     eax, 0C0000034h
0x18003158d  jz      loc_1800314B0
0x180031593  lea     r9, aFailedToOpenFi_0; "Failed to open file [%x]"
0x18003159a  mov     dword ptr [rsp+160h+AllocationSize], eax
0x18003159e  mov     r8d, 624h
0x1800315a4  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x1800315ab  mov     ecx, 1
0x1800315b0  call    AslLogCallPrintf
0x1800315b5  jmp     loc_1800314B0
0x1800315ba  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x1800315bf  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x1800315c3  mov     r9d, 28h ; '('; Length
0x1800315c9  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x1800315d1  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x1800315d6  call    cs:__imp_NtQueryInformationFile
0x1800315dc  mov     ebx, eax
0x1800315de  test    eax, eax
0x1800315e0  jns     short loc_18003160E
0x1800315e2  mov     [rsp+160h+FileAttributes], eax
0x1800315e6  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x1800315ed  mov     r8d, 62Fh
0x1800315f3  mov     [rsp+160h+AllocationSize], rdi
0x1800315f8  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x1800315ff  mov     ecx, 1
0x180031604  call    AslLogCallPrintf
0x180031609  jmp     loc_1800314B0
0x18003160e  mov     rcx, qword ptr [rbp+60h+var_88]
0x180031612  mov     rax, qword ptr [rbp+60h+var_88+8]
0x180031616  mov     qword ptr [rbp+60h+var_58], rcx
0x18003161a  mov     qword ptr [rbp+60h+var_58+8], rax
0x18003161e  jmp     loc_180031512
0x180031623  call    cs:__imp_ZwClose
0x180031629  jmp     loc_1800314BE
```
