# CreateNamedPipeW

- ea: `0x1800ed540`
- end: `0x1800ed8de`
- name: `CreateNamedPipeW`
- size: `926`
- prototype: `HANDLE __stdcall(LPCWSTR lpName, DWORD dwOpenMode, DWORD dwPipeMode, DWORD nMaxInstances, DWORD nOutBufferSize, DWORD nInBufferSize, DWORD nDefaultTimeOut, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x1800ed540`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ed5bf`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ed5bf`
- `ntdll!RtlSetLastWin32Error` at `0x1800ed7f0`
- `ntdll!RtlSetLastWin32Error` at `0x1800ed866`
- `ntdll!RtlSetLastWin32Error` at `0x1800ed7f0`
- `ntdll!RtlSetLastWin32Error` at `0x1800ed866`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800ed62e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800ed62e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800ed648`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800ed648`
- `ntdll!RtlFreeHeap` at `0x1800ed7af`
- `ntdll!RtlFreeHeap` at `0x1800ed7d7`
- `ntdll!RtlFreeHeap` at `0x1800ed814`
- `ntdll!RtlFreeHeap` at `0x1800ed8a0`
- `ntdll!RtlFreeHeap` at `0x1800ed8c8`
- `ntdll!RtlFreeHeap` at `0x1800ed7af`
- `ntdll!RtlFreeHeap` at `0x1800ed7d7`
- `ntdll!RtlFreeHeap` at `0x1800ed814`
- `ntdll!RtlFreeHeap` at `0x1800ed8a0`
- `ntdll!RtlFreeHeap` at `0x1800ed8c8`
- `ntdll!RtlDefaultNpAcl` at `0x1800ed60f`
- `ntdll!RtlDefaultNpAcl` at `0x1800ed60f`
- `ntdll!NtCreateNamedPipeFile` at `0x1800ed779`
- `ntdll!NtCreateNamedPipeFile` at `0x1800ed779`

## pseudocode

```c
HANDLE __stdcall CreateNamedPipeW(
        LPCWSTR lpName,
        DWORD dwOpenMode,
        DWORD dwPipeMode,
        DWORD nMaxInstances,
        DWORD nOutBufferSize,
        DWORD nInBufferSize,
        DWORD nDefaultTimeOut,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  ULONG MaxInstances; // r15d
  PWSTR Buffer; // rdi
  ULONG v12; // ecx
  NTSTATUS v13; // ebx
  LPVOID lpSecurityDescriptor; // rax
  union _LARGE_INTEGER v15; // rcx
  ULONG ShareAccess; // ebx
  int v17; // r14d
  ULONG WriteModeMessage; // r8d
  NTSTATUS v19; // eax
  ULONG v20; // ecx
  __int64 v22; // rcx
  PACL pAcl; // [rsp+70h] [rbp-90h] BYREF
  union _LARGE_INTEGER DefaultTimeOut; // [rsp+78h] [rbp-88h] BYREF
  HANDLE NamedPipeFileHandle; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR NtFileNamePart; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v31; // [rsp+100h] [rbp+0h]

  NamedPipeFileHandle = 0;
  DefaultTimeOut.QuadPart = 0;
  NtFileNamePart = 0;
  v31 = 0;
  pAcl = 0;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( nMaxInstances - 1 > 0xFE )
  {
LABEL_40:
    v22 = 3221225485LL;
    goto LABEL_30;
  }
  MaxInstances = -1;
  if ( nMaxInstances != 255 )
    MaxInstances = nMaxInstances;
  if ( !RtlDosPathNameToNtPathName_U(lpName, &NtPathName, &NtFileNamePart, 0) )
  {
    RtlSetLastWin32Error(3u);
    return (HANDLE)-1LL;
  }
  Buffer = NtPathName.Buffer;
  v12 = 64;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !lpSecurityAttributes )
    goto LABEL_6;
  lpSecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
  if ( lpSecurityAttributes->bInheritHandle )
    v12 = 66;
  ObjectAttributes.SecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
  ObjectAttributes.Attributes = v12;
  if ( !lpSecurityDescriptor )
  {
LABEL_6:
    v13 = RtlDefaultNpAcl(&pAcl);
    if ( v13 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_29:
      v22 = (unsigned int)v13;
LABEL_30:
      BaseSetLastNTError(v22);
      return (HANDLE)-1LL;
    }
    RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, pAcl, 0);
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  }
  if ( nDefaultTimeOut )
    v15.QuadPart = -10000LL * nDefaultTimeOut;
  else
    v15.QuadPart = -500000;
  DefaultTimeOut = v15;
  if ( (dwOpenMode & 0x3EF3FFFC) != 0 || (dwPipeMode & 0xFFFFFFF0) != 0 )
  {
LABEL_38:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( pAcl )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pAcl);
    goto LABEL_40;
  }
  ShareAccess = 3;
  switch ( dwOpenMode & 3 )
  {
    case 1u:
      ShareAccess = 2;
      v17 = -2146435072;
      break;
    case 2u:
      ShareAccess = 1;
      v17 = 1074790400;
      break;
    case 3u:
      v17 = -1072693248;
      break;
    default:
      goto LABEL_38;
  }
  WriteModeMessage = (dwPipeMode >> 2) & 1 | 2;
  if ( (dwPipeMode & 8) == 0 )
    WriteModeMessage = (dwPipeMode >> 2) & 1;
  v19 = NtCreateNamedPipeFile(
          &NamedPipeFileHandle,
          v17 | dwOpenMode & 0x10C0000,
          &ObjectAttributes,
          &IoStatusBlock,
          ShareAccess,
          ((dwOpenMode & 0x80000) == 0) | 2,
          ~(dwOpenMode >> 25) & 0x20 | ((int)dwOpenMode >> 31) & 2,
          WriteModeMessage,
          (dwPipeMode >> 1) & 1,
          dwPipeMode & 1,
          MaxInstances,
          nInBufferSize,
          nOutBufferSize,
          &DefaultTimeOut);
  v13 = v19;
  if ( v19 == -1073741637 || v19 == -1073741808 )
    v13 = -1073741773;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( pAcl )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pAcl);
  if ( v13 < 0 )
    goto LABEL_29;
  if ( IoStatusBlock.Information == 1 )
    v20 = 183;
  else
    v20 = 0;
  RtlSetLastWin32Error(v20);
  return NamedPipeFileHandle;
}

```

## disassembly

```asm
0x1800ed540  push    rbp
0x1800ed542  push    rbx
0x1800ed543  push    rsi
0x1800ed544  push    rdi
0x1800ed545  push    r12
0x1800ed547  push    r14
0x1800ed549  push    r15
0x1800ed54b  lea     rbp, [rsp-10h]
0x1800ed550  sub     rsp, 110h
0x1800ed557  xor     eax, eax
0x1800ed559  xorps   xmm0, xmm0
0x1800ed55c  mov     [rbp+40h+NamedPipeFileHandle], rax
0x1800ed560  xorps   xmm1, xmm1
0x1800ed563  mov     qword ptr [rsp+140h+var_C8], rax
0x1800ed568  mov     r12d, r8d
0x1800ed56b  mov     [rbp+40h+NtFileNamePart], rax
0x1800ed56f  mov     esi, edx
0x1800ed571  mov     [rbp+40h+var_40], rax
0x1800ed575  mov     [rsp+140h+pAcl], rax
0x1800ed57a  lea     eax, [r9-1]
0x1800ed57e  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1800ed582  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1800ed586  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1800ed58a  movups  xmmword ptr [rbp+40h+NtPathName.Length], xmm0
0x1800ed58e  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm1
0x1800ed592  movups  [rbp+40h+SecurityDescriptor], xmm0
0x1800ed596  movups  [rbp+40h+var_50], xmm0
0x1800ed59a  cmp     eax, 0FEh
0x1800ed59f  ja      loc_1800ED8D4
0x1800ed5a5  or      r15d, 0FFFFFFFFh
0x1800ed5a9  lea     r8, [rbp+40h+NtFileNamePart]; NtFileNamePart
0x1800ed5ad  cmp     r9d, 0FFh
0x1800ed5b4  lea     rdx, [rbp+40h+NtPathName]; NtPathName
0x1800ed5b8  cmovnz  r15d, r9d
0x1800ed5bc  xor     r9d, r9d; DirectoryInfo
0x1800ed5bf  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ed5c6  nop     dword ptr [rax+rax+00h]
0x1800ed5cb  test    al, al
0x1800ed5cd  jz      loc_1800ED861
0x1800ed5d3  mov     rdx, [rbp+40h+lpSecurityAttributes]
0x1800ed5da  lea     rax, [rbp+40h+NtPathName]
0x1800ed5de  mov     rdi, [rbp+40h+NtPathName.Buffer]
0x1800ed5e2  mov     ecx, 40h ; '@'
0x1800ed5e7  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1800ed5ee  xorps   xmm0, xmm0
0x1800ed5f1  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x1800ed5f9  mov     [rbp+40h+ObjectAttributes.Attributes], ecx
0x1800ed5fc  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1800ed600  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ed605  test    rdx, rdx
0x1800ed608  jnz     short loc_1800ED65E
0x1800ed60a  lea     rcx, [rsp+140h+pAcl]; pAcl
0x1800ed60f  call    cs:__imp_RtlDefaultNpAcl
0x1800ed616  nop     dword ptr [rax+rax+00h]
0x1800ed61b  mov     ebx, eax
0x1800ed61d  test    eax, eax
0x1800ed61f  js      loc_1800ED802
0x1800ed625  mov     edx, 1; Revision
0x1800ed62a  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x1800ed62e  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800ed635  nop     dword ptr [rax+rax+00h]
0x1800ed63a  mov     r8, [rsp+140h+pAcl]; Dacl
0x1800ed63f  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x1800ed643  xor     r9d, r9d; DaclDefaulted
0x1800ed646  mov     dl, 1; DaclPresent
0x1800ed648  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800ed64f  nop     dword ptr [rax+rax+00h]
0x1800ed654  lea     rax, [rbp+40h+SecurityDescriptor]
0x1800ed658  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x1800ed65c  jmp     short loc_1800ED67C
0x1800ed65e  cmp     dword ptr [rdx+10h], 0
0x1800ed662  mov     r8d, 42h ; 'B'
0x1800ed668  mov     rax, [rdx+8]
0x1800ed66c  cmovnz  ecx, r8d
0x1800ed670  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x1800ed674  mov     [rbp+40h+ObjectAttributes.Attributes], ecx
0x1800ed677  test    rax, rax
0x1800ed67a  jz      short loc_1800ED60A
0x1800ed67c  mov     eax, [rbp+40h+nDefaultTimeOut]
0x1800ed682  mov     r11d, esi
0x1800ed685  shr     r11d, 19h
0x1800ed689  not     r11d
0x1800ed68c  and     r11d, 20h
0x1800ed690  test    eax, eax
0x1800ed692  jnz     loc_1800ED84E
0x1800ed698  mov     rcx, 0FFFFFFFFFFF85EE0h
0x1800ed69f  test    esi, 3EF3FFFCh
0x1800ed6a5  mov     qword ptr [rsp+140h+var_C8], rcx
0x1800ed6aa  setz    cl
0x1800ed6ad  test    r12d, 0FFFFFFF0h
0x1800ed6b4  setz    al
0x1800ed6b7  test    al, cl
0x1800ed6b9  jz      loc_1800ED88E
0x1800ed6bf  mov     eax, esi
0x1800ed6c1  mov     ebx, 3
0x1800ed6c6  and     eax, ebx
0x1800ed6c8  sub     eax, 1
0x1800ed6cb  jz      loc_1800ED83E
0x1800ed6d1  sub     eax, 1
0x1800ed6d4  jz      loc_1800ED874
0x1800ed6da  cmp     eax, 1
0x1800ed6dd  jnz     loc_1800ED88E
0x1800ed6e3  mov     r14d, 0C0100000h
0x1800ed6e9  mov     ecx, esi
0x1800ed6eb  mov     edx, esi
0x1800ed6ed  mov     eax, r12d
0x1800ed6f0  mov     r9d, r12d
0x1800ed6f3  shr     eax, 2
0x1800ed6f6  mov     r10d, r12d
0x1800ed6f9  and     eax, 1
0x1800ed6fc  shr     r9d, 1
0x1800ed6ff  mov     r8d, eax
0x1800ed702  and     r9d, 1
0x1800ed706  or      r8d, 2
0x1800ed70a  and     r10d, 1
0x1800ed70e  test    r12b, 8
0x1800ed712  cmovz   r8d, eax
0x1800ed716  shr     ecx, 13h
0x1800ed719  sar     edx, 1Fh
0x1800ed71c  lea     rax, [rsp+140h+var_C8]
0x1800ed721  mov     [rsp+140h+DefaultTimeOut], rax; DefaultTimeOut
0x1800ed726  not     ecx
0x1800ed728  mov     eax, [rbp+40h+nOutBufferSize]
0x1800ed72b  and     edx, 2
0x1800ed72e  mov     [rsp+140h+OutBufferSize], eax; OutBufferSize
0x1800ed732  and     ecx, 1
0x1800ed735  mov     eax, [rbp+40h+nInBufferSize]
0x1800ed738  or      edx, r11d
0x1800ed73b  mov     [rsp+140h+InBufferSize], eax; InBufferSize
0x1800ed73f  or      ecx, 2
0x1800ed742  mov     [rsp+140h+MaxInstances], r15d; MaxInstances
0x1800ed747  and     esi, 10C0000h
0x1800ed74d  mov     [rsp+140h+NonBlocking], r10d; NonBlocking
0x1800ed752  or      esi, r14d
0x1800ed755  mov     [rsp+140h+ReadModeMessage], r9d; ReadModeMessage
0x1800ed75a  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x1800ed75e  mov     [rsp+140h+WriteModeMessage], r8d; WriteModeMessage
0x1800ed763  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1800ed767  mov     [rsp+140h+CreateOptions], edx; CreateOptions
0x1800ed76b  mov     edx, esi; DesiredAccess
0x1800ed76d  mov     [rsp+140h+CreateDisposition], ecx; CreateDisposition
0x1800ed771  lea     rcx, [rbp+40h+NamedPipeFileHandle]; NamedPipeFileHandle
0x1800ed775  mov     [rsp+140h+ShareAccess], ebx; ShareAccess
0x1800ed779  call    cs:__imp_NtCreateNamedPipeFile
0x1800ed780  nop     dword ptr [rax+rax+00h]
0x1800ed785  mov     ebx, eax
0x1800ed787  cmp     eax, 0C00000BBh
0x1800ed78c  jz      loc_1800ED884
0x1800ed792  cmp     eax, 0C0000010h
0x1800ed797  jz      loc_1800ED884
0x1800ed79d  mov     rcx, gs:60h
0x1800ed7a6  mov     r8, rdi; P
0x1800ed7a9  xor     edx, edx; Flags
0x1800ed7ab  mov     rcx, [rcx+30h]; HeapHandle
0x1800ed7af  call    cs:__imp_RtlFreeHeap
0x1800ed7b6  nop     dword ptr [rax+rax+00h]
0x1800ed7bb  cmp     [rsp+140h+pAcl], 0
0x1800ed7c1  jz      short loc_1800ED7E3
0x1800ed7c3  mov     rcx, gs:60h
0x1800ed7cc  xor     edx, edx; Flags
0x1800ed7ce  mov     r8, [rsp+140h+pAcl]; P
0x1800ed7d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800ed7d7  call    cs:__imp_RtlFreeHeap
0x1800ed7de  nop     dword ptr [rax+rax+00h]
0x1800ed7e3  test    ebx, ebx
0x1800ed7e5  js      short loc_1800ED820
0x1800ed7e7  cmp     [rbp+40h+IoStatusBlock.Information], 1
0x1800ed7ec  jz      short loc_1800ED85A
0x1800ed7ee  xor     ecx, ecx; LastError
0x1800ed7f0  call    cs:__imp_RtlSetLastWin32Error
0x1800ed7f7  nop     dword ptr [rax+rax+00h]
0x1800ed7fc  mov     rax, [rbp+40h+NamedPipeFileHandle]
0x1800ed800  jmp     short loc_1800ED82B
0x1800ed802  mov     rcx, gs:60h
0x1800ed80b  mov     r8, rdi; P
0x1800ed80e  xor     edx, edx; Flags
0x1800ed810  mov     rcx, [rcx+30h]; HeapHandle
0x1800ed814  call    cs:__imp_RtlFreeHeap
0x1800ed81b  nop     dword ptr [rax+rax+00h]
0x1800ed820  mov     ecx, ebx
0x1800ed822  call    BaseSetLastNTError
0x1800ed827  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ed82b  add     rsp, 110h
0x1800ed832  pop     r15
0x1800ed834  pop     r14
0x1800ed836  pop     r12
0x1800ed838  pop     rdi
0x1800ed839  pop     rsi
0x1800ed83a  pop     rbx
0x1800ed83b  pop     rbp
0x1800ed83c  retn
0x1800ed83e  mov     ebx, 2
0x1800ed843  mov     r14d, 80100000h
0x1800ed849  jmp     loc_1800ED6E9
0x1800ed84e  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1800ed855  jmp     loc_1800ED69F
0x1800ed85a  mov     ecx, 0B7h
0x1800ed85f  jmp     short loc_1800ED7F0
0x1800ed861  mov     ecx, 3; LastError
0x1800ed866  call    cs:__imp_RtlSetLastWin32Error
0x1800ed86d  nop     dword ptr [rax+rax+00h]
0x1800ed872  jmp     short loc_1800ED827
0x1800ed874  mov     ebx, 1
0x1800ed879  mov     r14d, 40100000h
0x1800ed87f  jmp     loc_1800ED6E9
0x1800ed884  mov     ebx, 0C0000033h
0x1800ed889  jmp     loc_1800ED79D
0x1800ed88e  mov     rcx, gs:60h
0x1800ed897  mov     r8, rdi; P
0x1800ed89a  xor     edx, edx; Flags
0x1800ed89c  mov     rcx, [rcx+30h]; HeapHandle
0x1800ed8a0  call    cs:__imp_RtlFreeHeap
0x1800ed8a7  nop     dword ptr [rax+rax+00h]
0x1800ed8ac  cmp     [rsp+140h+pAcl], 0
0x1800ed8b2  jz      short loc_1800ED8D4
0x1800ed8b4  mov     rcx, gs:60h
0x1800ed8bd  xor     edx, edx; Flags
0x1800ed8bf  mov     r8, [rsp+140h+pAcl]; P
0x1800ed8c4  mov     rcx, [rcx+30h]; HeapHandle
0x1800ed8c8  call    cs:__imp_RtlFreeHeap
0x1800ed8cf  nop     dword ptr [rax+rax+00h]
0x1800ed8d4  mov     ecx, 0C000000Dh
0x1800ed8d9  jmp     loc_1800ED822
```
