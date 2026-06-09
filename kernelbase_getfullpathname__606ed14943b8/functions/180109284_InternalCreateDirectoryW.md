# InternalCreateDirectoryW

- ea: `0x180109284`
- end: `0x1801095a5`
- name: `InternalCreateDirectoryW`
- size: `801`
- prototype: `__int64 __usercall@<rax>(PWSTR FileName@<rcx>, ACCESS_MASK DesiredAccess@<edx>, ULONG ShareAccess@<r8d>, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800730c0`
- `0x18018b1b0`
- `0x18018b230`

## callees

- `0x1800395b0`
- `0x18004b9d0`
- `0x180109284`
- `0x18011a954`
- `0x18018d55c`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1801092f6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1801092f6`
- `ntdll!RtlReleaseRelativeName` at `0x1801093da`
- `ntdll!RtlReleaseRelativeName` at `0x1801093da`
- `ntdll!NtCreateFile` at `0x1801093ad`
- `ntdll!NtCreateFile` at `0x1801093ad`
- `ntdll!RtlSetLastWin32Error` at `0x180109494`
- `ntdll!RtlSetLastWin32Error` at `0x1801094d7`
- `ntdll!RtlSetLastWin32Error` at `0x180109494`
- `ntdll!RtlSetLastWin32Error` at `0x1801094d7`
- `ntdll!RtlIsDosDeviceName_U` at `0x180109410`
- `ntdll!RtlIsDosDeviceName_U` at `0x180109410`
- `ntdll!NtClose` at `0x180109580`
- `ntdll!NtClose` at `0x180109594`
- `ntdll!NtClose` at `0x180109580`
- `ntdll!NtClose` at `0x180109594`
- `ntdll!RtlFreeHeap` at `0x1801093fd`
- `ntdll!RtlFreeHeap` at `0x1801093fd`
- `ntdll!RtlGetFullPathName_UEx` at `0x18010946d`
- `ntdll!RtlGetFullPathName_UEx` at `0x18010946d`

## pseudocode

```c
__int64 __fastcall InternalCreateDirectoryW(
        PWSTR FileName,
        ACCESS_MASK DesiredAccess,
        ULONG ShareAccess,
        char a4,
        __int64 a5)
{
  NTSTATUS DirectoryRedirectionStatus; // ebx
  char v6; // r14
  __int64 v10; // rsi
  PWSTR Buffer; // r15
  HANDLE ContainingDirectory; // rax
  bool v14; // zf
  NTSTATUS FullPathName_UEx; // eax
  ULONG v16; // ecx
  int v17; // eax
  HANDLE FileHandle; // [rsp+60h] [rbp-81h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-79h] BYREF
  __int64 v20; // [rsp+78h] [rbp-69h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-61h] BYREF
  PWSTR FilePart; // [rsp+A0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-9h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+158h] [rbp+77h] BYREF

  FileHandle = (HANDLE)-1LL;
  DirectoryRedirectionStatus = 0;
  v20 = -1;
  v6 = 1;
  v10 = -1;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( (a4 & 1) != 0 )
  {
    if ( (ShareAccess & 2) != 0 )
    {
      v16 = 87;
LABEL_30:
      RtlSetLastWin32Error(v16);
      return -1;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( !RtlDosPathNameToRelativeNtPathName_U(FileName, &NtName, 0, &RelativeName) )
  {
    v16 = 3;
    goto LABEL_30;
  }
  Buffer = NtName.Buffer;
  if ( (unsigned __int8)RtlAreLongPathsEnabled() )
    goto LABEL_6;
  if ( NtName.Length <= 0x1F0u )
    goto LABEL_6;
  v14 = *FileName == 92;
  FilePart = 0;
  if ( v14 && FileName[1] == 92 && FileName[2] == 63 && FileName[3] == 92 )
    goto LABEL_6;
  InputPathType = RtlPathTypeUnknown;
  FullPathName_UEx = RtlGetFullPathName_UEx(FileName, 0, 0, &FilePart, &InputPathType);
  if ( FullPathName_UEx < 0 )
    BaseSetLastNTError((unsigned int)FullPathName_UEx);
  if ( (unsigned int)InputPathType >> 1 && ((unsigned int)InputPathType >> 1) + 12 <= 0x104 )
  {
LABEL_6:
    if ( RelativeName.RelativeName.Length )
    {
      NtName = RelativeName.RelativeName;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtName;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a5 )
      ObjectAttributes.SecurityDescriptor = *(PVOID *)(a5 + 8);
    if ( v6 )
    {
      v17 = BasepOpenParentDirectoryNoRedirection(&NtName, &v20);
      v10 = v20;
      DirectoryRedirectionStatus = v17;
      if ( v17 < 0 )
        goto LABEL_13;
    }
    DirectoryRedirectionStatus = NtCreateFile(
                                   &FileHandle,
                                   DesiredAccess,
                                   &ObjectAttributes,
                                   &IoStatusBlock,
                                   0,
                                   0x80u,
                                   ShareAccess,
                                   2u,
                                   0x204021u,
                                   0,
                                   0);
    if ( DirectoryRedirectionStatus >= 0 )
    {
      if ( !v6
        || (DirectoryRedirectionStatus = BasepGetDirectoryRedirectionStatus(NtName.Buffer, FileHandle),
            DirectoryRedirectionStatus >= 0) )
      {
LABEL_13:
        if ( v10 != -1 )
          NtClose((HANDLE)v10);
        goto LABEL_15;
      }
      NtClose(FileHandle);
    }
    FileHandle = (HANDLE)-1LL;
    goto LABEL_13;
  }
  RtlSetLastWin32Error(0xCEu);
LABEL_15:
  RtlReleaseRelativeName(&RelativeName);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( DirectoryRedirectionStatus < 0 )
  {
    if ( RtlIsDosDeviceName_U(FileName) )
      DirectoryRedirectionStatus = -1073741565;
    BaseSetLastNTError((unsigned int)DirectoryRedirectionStatus);
  }
  return (__int64)FileHandle;
}

```

## disassembly

```asm
0x180109284  push    rbp
0x180109286  push    rbx
0x180109287  push    rsi
0x180109288  push    rdi
0x180109289  push    r12
0x18010928b  push    r13
0x18010928d  push    r14
0x18010928f  push    r15
0x180109291  lea     rbp, [rsp-17h]
0x180109296  sub     rsp, 0F8h
0x18010929d  xorps   xmm0, xmm0
0x1801092a0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801092a4  xor     eax, eax
0x1801092a6  mov     [rsp+130h+FileHandle], r15
0x1801092ab  xor     ebx, ebx
0x1801092ad  mov     [rbp+4Fh+var_B8], r15
0x1801092b1  mov     r14b, 1
0x1801092b4  xorps   xmm1, xmm1
0x1801092b7  mov     r12d, r8d
0x1801092ba  mov     r13d, edx
0x1801092bd  mov     rdi, rcx
0x1801092c0  mov     rsi, r15
0x1801092c3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1801092c7  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1801092cb  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1801092cf  movups  xmmword ptr [rbp+4Fh+NtName.Length], xmm0
0x1801092d3  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x1801092d7  movups  xmmword ptr [rbp+4Fh+RelativeName.RelativeName.Length], xmm0
0x1801092db  movups  xmmword ptr [rbp+4Fh+RelativeName.ContainingDirectory], xmm0
0x1801092df  test    r14b, r9b
0x1801092e2  jnz     loc_1801094C8
0x1801092e8  mov     r14b, bl
0x1801092eb  lea     r9, [rbp+4Fh+RelativeName]; RelativeName
0x1801092ef  xor     r8d, r8d; PartName
0x1801092f2  lea     rdx, [rbp+4Fh+NtName]; NtName
0x1801092f6  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1801092fd  nop     dword ptr [rax+rax+00h]
0x180109302  test    al, al
0x180109304  jz      loc_1801094EB
0x18010930a  mov     r15, [rbp+4Fh+NtName.Buffer]
0x18010930e  call    RtlAreLongPathsEnabled
0x180109313  test    al, al
0x180109315  jnz     short loc_180109326
0x180109317  mov     eax, 1F0h
0x18010931c  cmp     [rbp+4Fh+NtName.Length], ax
0x180109320  ja      loc_180109447
0x180109326  movzx   eax, [rbp+4Fh+RelativeName.RelativeName.Length]
0x18010932a  test    ax, ax
0x18010932d  jnz     loc_1801094A5
0x180109333  mov     rax, rbx
0x180109336  mov     [rbp+4Fh+RelativeName.ContainingDirectory], rbx
0x18010933a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x18010933e  xorps   xmm0, xmm0
0x180109341  lea     rax, [rbp+4Fh+NtName]
0x180109345  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18010934c  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180109350  mov     rax, [rbp+4Fh+arg_20]
0x180109354  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18010935b  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180109360  test    rax, rax
0x180109363  jnz     loc_18010952B
0x180109369  test    r14b, r14b
0x18010936c  jnz     loc_180109538
0x180109372  mov     [rsp+130h+EaLength], ebx; EaLength
0x180109376  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18010937a  mov     [rsp+130h+EaBuffer], rbx; EaBuffer
0x18010937f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180109383  mov     [rsp+130h+CreateOptions], 204021h; CreateOptions
0x18010938b  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x180109390  mov     [rsp+130h+CreateDisposition], 2; CreateDisposition
0x180109398  mov     edx, r13d; DesiredAccess
0x18010939b  mov     [rsp+130h+ShareAccess], r12d; ShareAccess
0x1801093a0  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x1801093a8  mov     [rsp+130h+AllocationSize], rbx; AllocationSize
0x1801093ad  call    cs:__imp_NtCreateFile
0x1801093b4  nop     dword ptr [rax+rax+00h]
0x1801093b9  mov     ebx, eax
0x1801093bb  test    eax, eax
0x1801093bd  jns     loc_18010955A
0x1801093c3  mov     [rsp+130h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1801093cc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1801093d0  jnz     loc_180109591
0x1801093d6  lea     rcx, [rbp+4Fh+RelativeName]; RelativeName
0x1801093da  call    cs:__imp_RtlReleaseRelativeName
0x1801093e1  nop     dword ptr [rax+rax+00h]
0x1801093e6  test    r15, r15
0x1801093e9  jz      short loc_180109409
0x1801093eb  mov     rcx, gs:60h
0x1801093f4  mov     r8, r15; P
0x1801093f7  xor     edx, edx; Flags
0x1801093f9  mov     rcx, [rcx+30h]; HeapHandle
0x1801093fd  call    cs:__imp_RtlFreeHeap
0x180109404  nop     dword ptr [rax+rax+00h]
0x180109409  test    ebx, ebx
0x18010940b  jns     short loc_18010942D
0x18010940d  mov     rcx, rdi; Name
0x180109410  call    cs:__imp_RtlIsDosDeviceName_U
0x180109417  nop     dword ptr [rax+rax+00h]
0x18010941c  mov     ecx, 0C0000103h
0x180109421  test    eax, eax
0x180109423  cmovnz  ebx, ecx
0x180109426  mov     ecx, ebx
0x180109428  call    BaseSetLastNTError
0x18010942d  mov     rax, [rsp+130h+FileHandle]
0x180109432  add     rsp, 0F8h
0x180109439  pop     r15
0x18010943b  pop     r14
0x18010943d  pop     r13
0x18010943f  pop     r12
0x180109441  pop     rdi
0x180109442  pop     rsi
0x180109443  pop     rbx
0x180109444  pop     rbp
0x180109445  retn
0x180109447  cmp     word ptr [rdi], 5Ch ; '\'
0x18010944b  mov     [rbp+4Fh+FilePart], rbx
0x18010944f  jz      loc_1801094F2
0x180109455  lea     rax, [rbp+4Fh+InputPathType]
0x180109459  mov     [rbp+4Fh+InputPathType], ebx
0x18010945c  lea     r9, [rbp+4Fh+FilePart]; FilePart
0x180109460  mov     [rsp+130h+AllocationSize], rax; InputPathType
0x180109465  xor     r8d, r8d; Buffer
0x180109468  xor     edx, edx; BufferLength
0x18010946a  mov     rcx, rdi; FileName
0x18010946d  call    cs:__imp_RtlGetFullPathName_UEx
0x180109474  nop     dword ptr [rax+rax+00h]
0x180109479  test    eax, eax
0x18010947b  jns     short loc_180109484
0x18010947d  mov     ecx, eax
0x18010947f  call    BaseSetLastNTError
0x180109484  mov     eax, [rbp+4Fh+InputPathType]
0x180109487  shr     eax, 1
0x180109489  jnz     loc_180109518
0x18010948f  mov     ecx, 0CEh; LastError
0x180109494  call    cs:__imp_RtlSetLastWin32Error
0x18010949b  nop     dword ptr [rax+rax+00h]
0x1801094a0  jmp     loc_1801093D6
0x1801094a5  mov     [rbp+4Fh+NtName.Length], ax
0x1801094a9  mov     eax, dword ptr [rbp+4Fh+RelativeName.RelativeName.MaximumLength]
0x1801094ac  mov     dword ptr [rbp+4Fh+NtName.MaximumLength], eax
0x1801094af  movzx   eax, word ptr [rbp+4Fh+RelativeName.RelativeName+6]
0x1801094b3  mov     word ptr [rbp+4Fh+NtName+6], ax
0x1801094b7  mov     rax, [rbp+4Fh+RelativeName.RelativeName.Buffer]
0x1801094bb  mov     [rbp+4Fh+NtName.Buffer], rax
0x1801094bf  mov     rax, [rbp+4Fh+RelativeName.ContainingDirectory]
0x1801094c3  jmp     loc_18010933A
0x1801094c8  test    r12b, 2
0x1801094cc  jz      loc_1801092EB
0x1801094d2  mov     ecx, 57h ; 'W'; LastError
0x1801094d7  call    cs:__imp_RtlSetLastWin32Error
0x1801094de  nop     dword ptr [rax+rax+00h]
0x1801094e3  mov     rax, r15
0x1801094e6  jmp     loc_180109432
0x1801094eb  mov     ecx, 3
0x1801094f0  jmp     short loc_1801094D7
0x1801094f2  cmp     word ptr [rdi+2], 5Ch ; '\'
0x1801094f7  jnz     loc_180109455
0x1801094fd  cmp     word ptr [rdi+4], 3Fh ; '?'
0x180109502  jnz     loc_180109455
0x180109508  cmp     word ptr [rdi+6], 5Ch ; '\'
0x18010950d  jz      loc_180109326
0x180109513  jmp     loc_180109455
0x180109518  add     eax, 0Ch
0x18010951b  cmp     eax, 104h
0x180109520  jbe     loc_180109326
0x180109526  jmp     loc_18010948F
0x18010952b  mov     rax, [rax+8]
0x18010952f  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x180109533  jmp     loc_180109369
0x180109538  lea     rdx, [rbp+4Fh+var_B8]
0x18010953c  lea     rcx, [rbp+4Fh+NtName]
0x180109540  call    BasepOpenParentDirectoryNoRedirection
0x180109545  mov     rsi, [rbp+4Fh+var_B8]
0x180109549  mov     ebx, eax
0x18010954b  test    eax, eax
0x18010954d  js      loc_1801093CC
0x180109553  xor     ebx, ebx
0x180109555  jmp     loc_180109372
0x18010955a  test    r14b, r14b
0x18010955d  jz      loc_1801093CC
0x180109563  mov     rdx, [rsp+130h+FileHandle]
0x180109568  mov     rcx, [rbp+4Fh+NtName.Buffer]
0x18010956c  call    BasepGetDirectoryRedirectionStatus
0x180109571  mov     ebx, eax
0x180109573  test    eax, eax
0x180109575  jns     loc_1801093CC
0x18010957b  mov     rcx, [rsp+130h+FileHandle]; Handle
0x180109580  call    cs:__imp_NtClose
0x180109587  nop     dword ptr [rax+rax+00h]
0x18010958c  jmp     loc_1801093C3
0x180109591  mov     rcx, rsi; Handle
0x180109594  call    cs:__imp_NtClose
0x18010959b  nop     dword ptr [rax+rax+00h]
0x1801095a0  jmp     loc_1801093D6
```
