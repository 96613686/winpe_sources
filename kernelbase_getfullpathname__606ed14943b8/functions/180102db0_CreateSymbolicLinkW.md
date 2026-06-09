# CreateSymbolicLinkW

- ea: `0x180102db0`
- end: `0x18010321e`
- name: `CreateSymbolicLinkW`
- size: `1134`
- prototype: `BOOLEAN __stdcall(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x180102db0`
- `0x18012d6c0`
- `0x1801369c9`
- `0x180194eb9`

## import_xrefs

- `ntdll!wcslen` at `0x180102ec7`
- `ntdll!wcslen` at `0x180102f3c`
- `ntdll!wcslen` at `0x180103142`
- `ntdll!wcslen` at `0x180102ec7`
- `ntdll!wcslen` at `0x180102f3c`
- `ntdll!wcslen` at `0x180103142`
- `ntdll!NtSetInformationFile` at `0x1801031e0`
- `ntdll!NtSetInformationFile` at `0x1801031e0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180102ea9`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180102f8c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180102ea9`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180102f8c`
- `ntdll!NtFsControlFile` at `0x180103050`
- `ntdll!NtFsControlFile` at `0x180103050`
- `ntdll!NtCreateFile` at `0x18010300c`
- `ntdll!NtCreateFile` at `0x18010300c`
- `ntdll!RtlSetLastWin32Error` at `0x180102e29`
- `ntdll!RtlSetLastWin32Error` at `0x180103163`
- `ntdll!RtlSetLastWin32Error` at `0x1801a2390`
- `ntdll!RtlSetLastWin32Error` at `0x180102e29`
- `ntdll!RtlSetLastWin32Error` at `0x180103163`
- `ntdll!RtlSetLastWin32Error` at `0x1801a2390`
- `ntdll!RtlReleasePrivilege` at `0x18010306d`
- `ntdll!RtlReleasePrivilege` at `0x18010306d`
- `ntdll!RtlAcquirePrivilege` at `0x180102e4a`
- `ntdll!RtlAcquirePrivilege` at `0x180102e4a`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180102e61`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180102e61`
- `ntdll!NtClose` at `0x1801030d9`
- `ntdll!NtClose` at `0x1801030d9`
- `ntdll!RtlFreeHeap` at `0x180103099`
- `ntdll!RtlFreeHeap` at `0x1801030c3`
- `ntdll!RtlFreeHeap` at `0x180103127`
- `ntdll!RtlFreeHeap` at `0x18010320d`
- `ntdll!RtlFreeHeap` at `0x180103099`
- `ntdll!RtlFreeHeap` at `0x1801030c3`
- `ntdll!RtlFreeHeap` at `0x180103127`
- `ntdll!RtlFreeHeap` at `0x18010320d`
- `ntdll!RtlAllocateHeap` at `0x180102ef3`
- `ntdll!RtlAllocateHeap` at `0x180102ef3`

## pseudocode

```c
BOOLEAN __stdcall CreateSymbolicLinkW(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags)
{
  char v3; // r12
  WCHAR *v4; // rsi
  _DWORD *v5; // rdi
  char v6; // r14
  void *v7; // r15
  NTSTATUS v8; // eax
  RTL_PATH_TYPE v9; // ecx
  __int32 v10; // ecx
  __int32 v11; // ecx
  __int32 v12; // ecx
  USHORT Length; // ax
  ULONG v14; // ebx
  _DWORD *Heap; // rax
  unsigned __int16 v16; // ax
  __int64 v17; // rcx
  unsigned int v18; // eax
  NTSTATUS v19; // eax
  __int64 FullPath; // rax
  ULONG v22; // ecx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-59h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-49h] BYREF
  ULONG Privilege; // [rsp+78h] [rbp-41h] BYREF
  struct _UNICODE_STRING v26; // [rsp+80h] [rbp-39h] BYREF
  PVOID ReturnedState; // [rsp+90h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-11h] BYREF
  char FileInformation; // [rsp+138h] [rbp+7Fh] BYREF

  FileHandle = (HANDLE)-1LL;
  *(_QWORD *)&v26.Length = 0;
  v26.Buffer = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  v3 = dwFlags;
  NtPathName.Buffer = 0;
  v4 = (WCHAR *)lpTargetFileName;
  FileInformation = 0;
  v5 = 0;
  ReturnedState = 0;
  v6 = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !lpSymlinkFileName || !lpTargetFileName )
    goto LABEL_39;
  RtlSetLastWin32Error(0);
  Privilege = 35;
  v8 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
  if ( v8 < 0 && (v3 & 2) == 0 )
    goto LABEL_35;
  v9 = RtlDetermineDosPathNameType_U(v4);
  if ( v9 == RtlPathTypeUnknown )
    goto LABEL_32;
  v10 = v9 - 1;
  if ( !v10 || (v11 = v10 - 1) == 0 )
  {
LABEL_9:
    if ( RtlDosPathNameToNtPathName_U(v4, &NtPathName, 0, 0) )
    {
      Length = NtPathName.Length;
      goto LABEL_11;
    }
LABEL_39:
    v22 = 87;
    goto LABEL_40;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    FullPath = GetFullPath(v4);
    v7 = (void *)FullPath;
    if ( !FullPath )
      goto LABEL_18;
    v4 = (WCHAR *)FullPath;
    goto LABEL_9;
  }
  if ( (unsigned int)(v12 - 1) >= 2 )
    goto LABEL_9;
LABEL_32:
  NtPathName.Buffer = v4;
  v6 = 1;
  Length = 2 * wcslen(v4);
  NtPathName.MaximumLength = Length;
  NtPathName.Length = Length;
LABEL_11:
  v14 = Length + 2 * (wcslen(v4) + 10);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v14);
  v5 = Heap;
  if ( !Heap )
  {
    RtlSetLastWin32Error(8u);
    goto LABEL_18;
  }
  memset_0(Heap, 0, v14);
  if ( v6 )
    v5[4] |= 1u;
  *v5 = -1610612724;
  *((_WORD *)v5 + 2) = v14 - 8;
  *((_WORD *)v5 + 6) = 0;
  v16 = 2 * wcslen(v4);
  *((_WORD *)v5 + 7) = v16;
  memcpy_0(v5 + 5, v4, v16);
  v17 = *((unsigned __int16 *)v5 + 7);
  *((_WORD *)v5 + 4) = v17;
  v18 = NtPathName.Length;
  *((_WORD *)v5 + 5) = NtPathName.Length;
  memcpy_0((char *)v5 + v17 + 20, NtPathName.Buffer, v18);
  if ( !RtlDosPathNameToNtPathName_U(lpSymlinkFileName, &v26, 0, 0) )
  {
    v22 = 3;
LABEL_40:
    RtlSetLastWin32Error(v22);
    goto LABEL_18;
  }
  ObjectAttributes.ObjectName = &v26;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtCreateFile(
         &FileHandle,
         0x110100u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x80u,
         0,
         2u,
         (v3 & 1) != 0 ? 2097185 : 2097248,
         0,
         0);
  if ( v8 < 0 )
  {
LABEL_35:
    BaseSetLastNTError((unsigned int)v8);
    goto LABEL_18;
  }
  v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A4u, v5, v14, 0, 0);
  if ( v19 < 0 )
  {
    BaseSetLastNTError((unsigned int)v19);
    FileInformation = 1;
    NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 1u, FileDispositionInformation);
  }
LABEL_18:
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( !v6 && NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v26.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26.Buffer);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  return NtCurrentTeb()->LastErrorValue == 0;
}

```

## disassembly

```asm
0x180102db0  mov     [rsp-8+arg_8], rbx
0x180102db5  mov     [rsp-8+DosPathName], rcx
0x180102dba  push    rbp
0x180102dbb  push    rsi
0x180102dbc  push    rdi
0x180102dbd  push    r12
0x180102dbf  push    r13
0x180102dc1  push    r14
0x180102dc3  push    r15
0x180102dc5  lea     rbp, [rsp-27h]
0x180102dca  sub     rsp, 0E0h
0x180102dd1  xor     ebx, ebx
0x180102dd3  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180102ddb  xorps   xmm0, xmm0
0x180102dde  mov     qword ptr [rbp+57h+var_90.Length], rbx
0x180102de2  xor     eax, eax
0x180102de4  mov     [rbp+57h+var_90.Buffer], rbx
0x180102de8  mov     qword ptr [rbp+57h+NtPathName.Length], rbx
0x180102dec  mov     r12d, r8d
0x180102def  mov     [rbp+57h+NtPathName.Buffer], rbx
0x180102df3  mov     rsi, rdx
0x180102df6  mov     [rbp+57h+FileInformation], bl
0x180102df9  mov     edi, ebx
0x180102dfb  mov     [rbp+57h+ReturnedState], rbx
0x180102dff  mov     r14b, bl
0x180102e02  mov     r15d, ebx
0x180102e05  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180102e09  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180102e0d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180102e11  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180102e15  test    rcx, rcx
0x180102e18  jz      loc_1801031F1
0x180102e1e  test    rdx, rdx
0x180102e21  jz      loc_1801031F1
0x180102e27  xor     ecx, ecx; LastError
0x180102e29  call    cs:__imp_RtlSetLastWin32Error
0x180102e30  nop     dword ptr [rax+rax+00h]
0x180102e35  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x180102e39  mov     [rbp+57h+Privilege], 23h ; '#'
0x180102e40  xor     r8d, r8d; Flags
0x180102e43  lea     edx, [rbx+1]; NumPriv
0x180102e46  lea     rcx, [rbp+57h+Privilege]; Privilege
0x180102e4a  call    cs:__imp_RtlAcquirePrivilege
0x180102e51  nop     dword ptr [rax+rax+00h]
0x180102e56  test    eax, eax
0x180102e58  js      loc_180103176
0x180102e5e  mov     rcx, rsi; Path
0x180102e61  call    cs:__imp_RtlDetermineDosPathNameType_U
0x180102e68  nop     dword ptr [rax+rax+00h]
0x180102e6d  mov     ecx, eax
0x180102e6f  test    eax, eax
0x180102e71  jz      loc_180103138
0x180102e77  sub     ecx, 1
0x180102e7a  jz      short loc_180102E9C
0x180102e7c  sub     ecx, 1
0x180102e7f  jz      short loc_180102E9C
0x180102e81  sub     ecx, 1
0x180102e84  jz      loc_18010318C
0x180102e8a  sub     ecx, 1
0x180102e8d  jz      loc_180103138
0x180102e93  sub     ecx, 1
0x180102e96  jz      loc_180103138
0x180102e9c  xor     r9d, r9d; DirectoryInfo
0x180102e9f  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180102ea3  xor     r8d, r8d; NtFileNamePart
0x180102ea6  mov     rcx, rsi; DosPathName
0x180102ea9  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180102eb0  nop     dword ptr [rax+rax+00h]
0x180102eb5  test    al, al
0x180102eb7  jz      loc_1801031F1
0x180102ebd  movzx   eax, [rbp+57h+NtPathName.Length]
0x180102ec1  mov     rcx, rsi; String
0x180102ec4  movzx   ebx, ax
0x180102ec7  call    cs:__imp_wcslen
0x180102ece  nop     dword ptr [rax+rax+00h]
0x180102ed3  mov     rcx, gs:60h
0x180102edc  mov     edx, cs:KernelBaseGlobalData; Flags
0x180102ee2  lea     eax, [rax+0Ah]
0x180102ee5  mov     rcx, [rcx+30h]; HeapHandle
0x180102ee9  lea     r13d, [rbx+rax*2]
0x180102eed  mov     r8d, r13d; Size
0x180102ef0  mov     ebx, r13d
0x180102ef3  call    cs:__imp_RtlAllocateHeap
0x180102efa  nop     dword ptr [rax+rax+00h]
0x180102eff  mov     rdi, rax
0x180102f02  test    rax, rax
0x180102f05  jz      loc_18010315E
0x180102f0b  mov     r8d, ebx; Size
0x180102f0e  xor     edx, edx; Val
0x180102f10  mov     rcx, rax; void *
0x180102f13  call    memset_0
0x180102f18  test    r14b, r14b
0x180102f1b  jnz     loc_1801031A8
0x180102f21  lea     eax, [r13-8]
0x180102f25  mov     dword ptr [rdi], 0A000000Ch
0x180102f2b  mov     [rdi+4], ax
0x180102f2f  lea     rbx, [rdi+14h]
0x180102f33  xor     eax, eax
0x180102f35  mov     rcx, rsi; String
0x180102f38  mov     [rdi+0Ch], ax
0x180102f3c  call    cs:__imp_wcslen
0x180102f43  nop     dword ptr [rax+rax+00h]
0x180102f48  mov     rdx, rsi; Src
0x180102f4b  mov     rcx, rbx; void *
0x180102f4e  add     ax, ax
0x180102f51  movzx   r8d, ax; Size
0x180102f55  mov     [rdi+0Eh], r8w
0x180102f5a  call    memcpy_0
0x180102f5f  movzx   ecx, word ptr [rdi+0Eh]
0x180102f63  mov     [rdi+8], cx
0x180102f67  add     rcx, rbx; void *
0x180102f6a  movzx   eax, [rbp+57h+NtPathName.Length]
0x180102f6e  mov     [rdi+0Ah], ax
0x180102f72  mov     r8d, eax; Size
0x180102f75  mov     rdx, [rbp+57h+NtPathName.Buffer]; Src
0x180102f79  call    memcpy_0
0x180102f7e  mov     rcx, [rbp+57h+DosPathName]; DosPathName
0x180102f82  lea     rdx, [rbp+57h+var_90]; NtPathName
0x180102f86  xor     r9d, r9d; DirectoryInfo
0x180102f89  xor     r8d, r8d; NtFileNamePart
0x180102f8c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180102f93  nop     dword ptr [rax+rax+00h]
0x180102f98  xor     ebx, ebx
0x180102f9a  test    al, al
0x180102f9c  jz      loc_1801031B1
0x180102fa2  mov     [rsp+110h+EaLength], ebx; EaLength
0x180102fa6  lea     rax, [rbp+57h+var_90]
0x180102faa  mov     [rsp+110h+EaBuffer], rbx; EaBuffer
0x180102faf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180102fb3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180102fb7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180102fbb  xorps   xmm0, xmm0
0x180102fbe  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180102fc5  and     r12b, 1
0x180102fc9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180102fcd  neg     r12b
0x180102fd0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180102fd7  mov     edx, 110100h; DesiredAccess
0x180102fdc  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180102fe0  sbb     eax, eax
0x180102fe2  and     eax, 0FFFFFFC1h
0x180102fe5  add     eax, 200060h
0x180102fea  mov     [rsp+110h+CreateOptions], eax; CreateOptions
0x180102fee  mov     [rsp+110h+CreateDisposition], 2; CreateDisposition
0x180102ff6  mov     [rsp+110h+ShareAccess], ebx; ShareAccess
0x180102ffa  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180103002  mov     [rsp+110h+AllocationSize], rbx; AllocationSize
0x180103007  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18010300c  call    cs:__imp_NtCreateFile
0x180103013  nop     dword ptr [rax+rax+00h]
0x180103018  test    eax, eax
0x18010301a  js      loc_180103180
0x180103020  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180103024  lea     rax, [rbp+57h+IoStatusBlock]
0x180103028  mov     dword ptr [rsp+110h+EaBuffer], ebx; OutputBufferLength
0x18010302c  xor     r9d, r9d; ApcContext
0x18010302f  mov     qword ptr [rsp+110h+CreateOptions], rbx; OutputBuffer
0x180103034  xor     r8d, r8d; ApcRoutine
0x180103037  mov     [rsp+110h+CreateDisposition], r13d; InputBufferLength
0x18010303c  xor     edx, edx; Event
0x18010303e  mov     qword ptr [rsp+110h+ShareAccess], rdi; InputBuffer
0x180103043  mov     [rsp+110h+FileAttributes], 900A4h; FsControlCode
0x18010304b  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x180103050  call    cs:__imp_NtFsControlFile
0x180103057  nop     dword ptr [rax+rax+00h]
0x18010305c  test    eax, eax
0x18010305e  js      loc_1801031BB
0x180103064  mov     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x180103068  test    rcx, rcx
0x18010306b  jz      short loc_180103079
0x18010306d  call    cs:__imp_RtlReleasePrivilege
0x180103074  nop     dword ptr [rax+rax+00h]
0x180103079  test    r15, r15
0x18010307c  jnz     loc_1801031FB
0x180103082  test    rdi, rdi
0x180103085  jz      short loc_1801030A5
0x180103087  mov     rcx, gs:60h
0x180103090  mov     r8, rdi; P
0x180103093  xor     edx, edx; Flags
0x180103095  mov     rcx, [rcx+30h]; HeapHandle
0x180103099  call    cs:__imp_RtlFreeHeap
0x1801030a0  nop     dword ptr [rax+rax+00h]
0x1801030a5  test    r14b, r14b
0x1801030a8  jz      short loc_18010310E
0x1801030aa  cmp     [rbp+57h+var_90.Buffer], rbx
0x1801030ae  jz      short loc_1801030CF
0x1801030b0  mov     rcx, gs:60h
0x1801030b9  xor     edx, edx; Flags
0x1801030bb  mov     r8, [rbp+57h+var_90.Buffer]; P
0x1801030bf  mov     rcx, [rcx+30h]; HeapHandle
0x1801030c3  call    cs:__imp_RtlFreeHeap
0x1801030ca  nop     dword ptr [rax+rax+00h]
0x1801030cf  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1801030d3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801030d7  jz      short loc_1801030E5
0x1801030d9  call    cs:__imp_NtClose
0x1801030e0  nop     dword ptr [rax+rax+00h]
0x1801030e5  mov     eax, gs:68h
0x1801030ed  test    eax, eax
0x1801030ef  mov     rbx, [rsp+110h+arg_8]
0x1801030f7  setz    al
0x1801030fa  add     rsp, 0E0h
0x180103101  pop     r15
0x180103103  pop     r14
0x180103105  pop     r13
0x180103107  pop     r12
0x180103109  pop     rdi
0x18010310a  pop     rsi
0x18010310b  pop     rbp
0x18010310c  retn
0x18010310e  cmp     [rbp+57h+NtPathName.Buffer], rbx
0x180103112  jz      short loc_1801030AA
0x180103114  mov     rcx, gs:60h
0x18010311d  xor     edx, edx; Flags
0x18010311f  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x180103123  mov     rcx, [rcx+30h]; HeapHandle
0x180103127  call    cs:__imp_RtlFreeHeap
0x18010312e  nop     dword ptr [rax+rax+00h]
0x180103133  jmp     loc_1801030AA
0x180103138  mov     rcx, rsi; String
0x18010313b  mov     [rbp+57h+NtPathName.Buffer], rsi
0x18010313f  mov     r14b, 1
0x180103142  call    cs:__imp_wcslen
0x180103149  nop     dword ptr [rax+rax+00h]
0x18010314e  add     ax, ax
0x180103151  mov     [rbp+57h+NtPathName.MaximumLength], ax
0x180103155  mov     [rbp+57h+NtPathName.Length], ax
0x180103159  jmp     loc_180102EC1
0x18010315e  mov     ecx, 8; LastError
0x180103163  call    cs:__imp_RtlSetLastWin32Error
0x18010316a  nop     dword ptr [rax+rax+00h]
0x18010316f  xor     ebx, ebx
0x180103171  jmp     loc_180103064
0x180103176  test    r12b, 2
0x18010317a  jnz     loc_180102E5E
0x180103180  mov     ecx, eax
0x180103182  call    BaseSetLastNTError
0x180103187  jmp     loc_180103064
0x18010318c  mov     rcx, rsi; lpFileName
0x18010318f  call    GetFullPath
0x180103194  mov     r15, rax
0x180103197  test    rax, rax
0x18010319a  jz      loc_180103064
0x1801031a0  mov     rsi, rax
0x1801031a3  jmp     loc_180102E9C
0x1801031a8  or      dword ptr [rdi+10h], 1
0x1801031ac  jmp     loc_180102F21
0x1801031b1  mov     ecx, 3; LastError
0x1801031b6  jmp     loc_1801A2390
0x1801031bb  mov     ecx, eax
0x1801031bd  call    BaseSetLastNTError
0x1801031c2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1801031c6  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1801031ca  mov     r9d, 1; Length
0x1801031d0  mov     [rbp+57h+FileInformation], 1
0x1801031d4  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801031d8  mov     dword ptr [rsp+110h+AllocationSize], 0Dh; FileInformationClass
0x1801031e0  call    cs:__imp_NtSetInformationFile
0x1801031e7  nop     dword ptr [rax+rax+00h]
0x1801031ec  jmp     loc_180103064
0x1801031f1  mov     ecx, 57h ; 'W'
0x1801031f6  jmp     loc_1801A2390
0x1801031fb  mov     rcx, gs:60h
0x180103204  mov     r8, r15; P
0x180103207  xor     edx, edx; Flags
0x180103209  mov     rcx, [rcx+30h]; HeapHandle
0x18010320d  call    cs:__imp_RtlFreeHeap
0x180103214  nop     dword ptr [rax+rax+00h]
0x180103219  jmp     loc_180103082
0x1801a2390  call    cs:__imp_RtlSetLastWin32Error
0x1801a2397  nop     dword ptr [rax+rax+00h]
0x1801a239c  nop
0x1801a239d  jmp     loc_180103064
```
