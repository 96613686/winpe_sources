# FindFirstFileNameW

- ea: `0x1800e26e0`
- end: `0x1800e2b5b`
- name: `FindFirstFileNameW`
- size: `1147`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwFlags, LPDWORD StringLength, PWSTR LinkName)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x180082f80`
- `0x1800e26e0`
- `0x1800e2cfc`
- `0x180194eb9`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800e28f8`
- `ntdll!NtQueryInformationFile` at `0x1800e28f8`
- `ntdll!RtlInitializeCriticalSection` at `0x1800e2863`
- `ntdll!RtlInitializeCriticalSection` at `0x1800e2863`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800e273d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800e273d`
- `ntdll!NtCreateFile` at `0x1800e27ec`
- `ntdll!NtCreateFile` at `0x1800e27ec`
- `ntdll!RtlSetLastWin32Error` at `0x1800e2b2a`
- `ntdll!RtlSetLastWin32Error` at `0x1800e2b2a`
- `ntdll!NtClose` at `0x1800e2b43`
- `ntdll!NtClose` at `0x1801982b7`
- `ntdll!NtClose` at `0x1800e2b43`
- `ntdll!NtClose` at `0x1801982b7`
- `ntdll!RtlFreeHeap` at `0x1800e28a4`
- `ntdll!RtlFreeHeap` at `0x1800e2a79`
- `ntdll!RtlFreeHeap` at `0x1800e2abe`
- `ntdll!RtlFreeHeap` at `0x1800e2ae1`
- `ntdll!RtlFreeHeap` at `0x18019826f`
- `ntdll!RtlFreeHeap` at `0x180198294`
- `ntdll!RtlFreeHeap` at `0x1800e28a4`
- `ntdll!RtlFreeHeap` at `0x1800e2a79`
- `ntdll!RtlFreeHeap` at `0x1800e2abe`
- `ntdll!RtlFreeHeap` at `0x1800e2ae1`
- `ntdll!RtlFreeHeap` at `0x18019826f`
- `ntdll!RtlFreeHeap` at `0x180198294`
- `ntdll!RtlAllocateHeap` at `0x1800e2830`
- `ntdll!RtlAllocateHeap` at `0x1800e28c2`
- `ntdll!RtlAllocateHeap` at `0x1800e2830`
- `ntdll!RtlAllocateHeap` at `0x1800e28c2`

## pseudocode

```c
HANDLE __stdcall FindFirstFileNameW(LPCWSTR lpFileName, DWORD dwFlags, LPDWORD StringLength, PWSTR LinkName)
{
  signed int *v4; // rsi
  signed int v5; // r14d
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  char v7; // r12
  NTSTATUS Parent; // edi
  struct _RTL_CRITICAL_SECTION_DEBUG *v9; // rdi
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  signed int *v11; // rax
  NTSTATUS v12; // eax
  unsigned int *v13; // r15
  size_t v14; // r14
  int v15; // ecx
  DWORD v16; // eax
  DWORD v17; // ecx
  __int64 v18; // rcx
  ULONG_PTR Information; // rax
  ULONG v21; // ecx
  signed int *v22; // [rsp+68h] [rbp-B0h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-A8h] BYREF
  DWORD v24; // [rsp+78h] [rbp-A0h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+80h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-90h] BYREF
  struct _UNICODE_STRING v27; // [rsp+98h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+A8h] [rbp-70h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-68h] BYREF
  DWORD v30; // [rsp+128h] [rbp+10h]

  IoStatusBlock = 0;
  v4 = 0;
  v22 = 0;
  FileHandle = (HANDLE)-1LL;
  memset(&ObjectAttributes, 0, 44);
  v27 = 0;
  if ( dwFlags )
  {
    v21 = 87;
LABEL_44:
    RtlSetLastWin32Error(v21);
    return (HANDLE)-1LL;
  }
  if ( !RtlDosPathNameToNtPathName_U(lpFileName, &v27, 0, 0) )
  {
    v21 = 3;
    goto LABEL_44;
  }
  v5 = 96;
  v6 = 0;
  v25 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v27;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = 1;
  Parent = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x200020u, 0, 0);
  if ( !Parent )
  {
    v9 = (struct _RTL_CRITICAL_SECTION_DEBUG *)FileHandle;
    v28 = 0;
    Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(
                                             NtCurrentPeb()->ProcessHeap,
                                             KernelBaseGlobalData + 786432,
                                             0x50u);
    v6 = Heap;
    v28 = Heap;
    if ( Heap )
    {
      Heap->DebugInfo = v9;
      *(_QWORD *)&Heap->LockCount = 0;
      Heap->OwningThread = 0;
      Heap->LockSemaphore = 0;
      Heap->SpinCount = 0;
      if ( RtlInitializeCriticalSection(Heap + 1) < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
        v6 = 0;
        v28 = 0;
      }
    }
    v25 = v6;
    if ( v6 )
    {
      FileHandle = 0;
      while ( 1 )
      {
        if ( v4 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
        v11 = (signed int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        v4 = v11;
        v22 = v11;
        if ( !v11 )
          break;
        v12 = NtQueryInformationFile(v6->DebugInfo, &IoStatusBlock, v11, v5, FileHardLinkInformation);
        Parent = v12;
        if ( v12 != -2147483643 )
        {
          if ( !v12 )
          {
            if ( IoStatusBlock.Information )
            {
              *(_QWORD *)&v6->LockCount = v4;
              v13 = (unsigned int *)v4;
              LODWORD(v6->LockSemaphore) = IoStatusBlock.Information;
              HIDWORD(v6->LockSemaphore) = IoStatusBlock.Information;
              v22 = 0;
              Parent = FindParent(v6->DebugInfo, *((_QWORD *)v4 + 2), &v22);
              v4 = v22;
              if ( Parent >= 0 )
              {
                v14 = (unsigned int)*v22;
                v15 = 2;
                if ( (_DWORD)v14 == 2 )
                  v15 = 1;
                else
                  v7 = 0;
                v16 = v15 + v13[6] + ((unsigned int)*v22 >> 1);
                v30 = v16;
                v17 = *StringLength;
                v24 = v17;
                Parent = v17 < v16 ? 0x80000005 : 0;
                *StringLength = v16;
                if ( v16 <= v17 )
                {
                  memcpy_0(LinkName, v4 + 1, v14);
                  if ( !v7 )
                  {
                    *(PWSTR)((char *)LinkName + v14) = 92;
                    LODWORD(v14) = v14 + 2;
                  }
                  memcpy_0((char *)LinkName + (unsigned int)v14, v13 + 7, 2LL * v13[6]);
                  *(WCHAR *)((char *)&LinkName[v13[6]] + (unsigned int)v14) = 0;
                  v16 = v30;
                  v17 = v24;
                }
                if ( v16 <= v17 )
                {
                  v18 = *(_QWORD *)&v6->LockCount;
                  if ( v13[2] )
                  {
                    Information = v13[2];
                    v18 += 8;
                  }
                  else
                  {
                    Information = IoStatusBlock.Information;
                  }
                  v6->OwningThread = (HANDLE)(Information + v18);
                }
              }
            }
            else
            {
              Parent = -1073741807;
            }
          }
          goto LABEL_32;
        }
        v5 = *v4;
      }
    }
    Parent = -1073741670;
  }
LABEL_32:
  if ( v27.Length )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27.Buffer);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( Parent )
  {
    BaseSetLastNTError((unsigned int)Parent);
    if ( FileHandle != (HANDLE)-1LL )
      NtClose(FileHandle);
    if ( v6 )
      FindClose(v6);
    return (HANDLE)-1LL;
  }
  return v6;
}

```

## disassembly

```asm
0x1800e26e0  mov     rax, rsp
0x1800e26e3  mov     [rax+20h], r9
0x1800e26e7  mov     [rax+18h], r8
0x1800e26eb  push    rbx
0x1800e26ec  push    rsi
0x1800e26ed  push    rdi
0x1800e26ee  push    r12
0x1800e26f0  push    r13
0x1800e26f2  push    r14
0x1800e26f4  push    r15
0x1800e26f6  sub     rsp, 0E0h
0x1800e26fd  xorps   xmm0, xmm0
0x1800e2700  movups  xmmword ptr [rax-90h], xmm0
0x1800e2707  xor     r13d, r13d
0x1800e270a  mov     esi, r13d
0x1800e270d  mov     [rsp+118h+var_B0], r13
0x1800e2712  mov     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800e271b  xor     r8d, r8d; NtFileNamePart
0x1800e271e  movups  xmmword ptr [rax-68h], xmm0
0x1800e2722  movups  xmmword ptr [rax-58h], xmm0
0x1800e2726  movups  xmmword ptr [rax-4Ch], xmm0
0x1800e272a  movups  xmmword ptr [rax-80h], xmm0
0x1800e272e  test    edx, edx
0x1800e2730  jnz     loc_1800E2B25
0x1800e2736  xor     r9d, r9d; DirectoryInfo
0x1800e2739  lea     rdx, [rax-80h]; NtPathName
0x1800e273d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800e2744  nop     dword ptr [rax+rax+00h]
0x1800e2749  test    al, al
0x1800e274b  jz      loc_1800E2B3C
0x1800e2751  mov     [rsp+118h+var_B8], 0C000000Dh
0x1800e2759  lea     r14d, [r13+60h]
0x1800e275d  mov     ebx, r13d
0x1800e2760  mov     [rsp+118h+var_98], rbx
0x1800e2768  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x1800e2773  mov     [rsp+118h+ObjectAttributes.RootDirectory], r13
0x1800e277b  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x1800e2786  lea     rax, [rsp+118h+var_80]
0x1800e278e  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x1800e2796  xorps   xmm0, xmm0
0x1800e2799  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e27a2  mov     [rsp+118h+EaLength], r13d; EaLength
0x1800e27a7  mov     [rsp+118h+EaBuffer], r13; EaBuffer
0x1800e27ac  mov     [rsp+118h+CreateOptions], 200020h; CreateOptions
0x1800e27b4  lea     r12d, [r13+1]
0x1800e27b8  mov     [rsp+118h+CreateDisposition], r12d; CreateDisposition
0x1800e27bd  mov     [rsp+118h+ShareAccess], 7; ShareAccess
0x1800e27c5  mov     [rsp+118h+FileAttributes], 80h; FileAttributes
0x1800e27cd  mov     [rsp+118h+AllocationSize], r13; AllocationSize
0x1800e27d2  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x1800e27da  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x1800e27e2  mov     edx, 100080h; DesiredAccess
0x1800e27e7  lea     rcx, [rsp+118h+FileHandle]; FileHandle
0x1800e27ec  call    cs:__imp_NtCreateFile
0x1800e27f3  nop     dword ptr [rax+rax+00h]
0x1800e27f8  mov     edi, eax
0x1800e27fa  mov     [rsp+118h+var_B8], eax
0x1800e27fe  test    eax, eax
0x1800e2800  jnz     loc_1800E2A9C
0x1800e2806  mov     rdi, [rsp+118h+FileHandle]
0x1800e280b  mov     [rsp+118h+var_70], r13
0x1800e2813  mov     edx, cs:KernelBaseGlobalData
0x1800e2819  add     edx, 0C0000h; Flags
0x1800e281f  mov     rcx, gs:60h
0x1800e2828  lea     r8d, [r13+50h]; Size
0x1800e282c  mov     rcx, [rcx+30h]; HeapHandle
0x1800e2830  call    cs:__imp_RtlAllocateHeap
0x1800e2837  nop     dword ptr [rax+rax+00h]
0x1800e283c  mov     rbx, rax
0x1800e283f  mov     [rsp+118h+var_70], rax
0x1800e2847  test    rax, rax
0x1800e284a  jz      short loc_1800E2877
0x1800e284c  mov     [rax], rdi
0x1800e284f  mov     [rax+8], r13
0x1800e2853  mov     [rax+10h], r13
0x1800e2857  mov     [rax+18h], r13
0x1800e285b  mov     [rax+20h], r13
0x1800e285f  lea     rcx, [rax+28h]; CriticalSection
0x1800e2863  call    cs:__imp_RtlInitializeCriticalSection
0x1800e286a  nop     dword ptr [rax+rax+00h]
0x1800e286f  test    eax, eax
0x1800e2871  js      loc_1800E2A67
0x1800e2877  mov     [rsp+118h+var_98], rbx
0x1800e287f  test    rbx, rbx
0x1800e2882  jz      loc_1800E2A45
0x1800e2888  mov     [rsp+118h+FileHandle], r13
0x1800e288d  test    rsi, rsi
0x1800e2890  jz      short loc_1800E28B0
0x1800e2892  mov     rcx, gs:60h
0x1800e289b  mov     r8, rsi; P
0x1800e289e  xor     edx, edx; Flags
0x1800e28a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800e28a4  call    cs:__imp_RtlFreeHeap
0x1800e28ab  nop     dword ptr [rax+rax+00h]
0x1800e28b0  movsxd  r8, r14d; Size
0x1800e28b3  mov     rcx, gs:60h
0x1800e28bc  xor     edx, edx; Flags
0x1800e28be  mov     rcx, [rcx+30h]; HeapHandle
0x1800e28c2  call    cs:__imp_RtlAllocateHeap
0x1800e28c9  nop     dword ptr [rax+rax+00h]
0x1800e28ce  mov     rsi, rax
0x1800e28d1  mov     [rsp+118h+var_B0], rax
0x1800e28d6  test    rax, rax
0x1800e28d9  jz      loc_1800E2A45
0x1800e28df  mov     dword ptr [rsp+118h+AllocationSize], 2Eh ; '.'; FileInformationClass
0x1800e28e7  mov     r9d, r14d; Length
0x1800e28ea  mov     r8, rax; FileInformation
0x1800e28ed  lea     rdx, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x1800e28f5  mov     rcx, [rbx]; FileHandle
0x1800e28f8  call    cs:__imp_NtQueryInformationFile
0x1800e28ff  nop     dword ptr [rax+rax+00h]
0x1800e2904  mov     edi, eax
0x1800e2906  mov     [rsp+118h+var_B8], eax
0x1800e290a  cmp     eax, 80000005h
0x1800e290f  jz      loc_1800E2A3D
0x1800e2915  test    eax, eax
0x1800e2917  jnz     loc_1800E2A9C
0x1800e291d  cmp     [rsp+118h+IoStatusBlock.Information], r13
0x1800e2925  jz      loc_1800E2A95
0x1800e292b  mov     [rbx+8], rsi
0x1800e292f  mov     r15, rsi
0x1800e2932  mov     rax, [rsp+118h+IoStatusBlock.Information]
0x1800e293a  mov     [rbx+18h], eax
0x1800e293d  mov     rax, [rsp+118h+IoStatusBlock.Information]
0x1800e2945  mov     [rbx+1Ch], eax
0x1800e2948  mov     [rsp+118h+var_B0], r13
0x1800e294d  lea     r8, [rsp+118h+var_B0]
0x1800e2952  mov     rdx, [rsi+10h]
0x1800e2956  mov     rcx, [rbx]
0x1800e2959  call    FindParent
0x1800e295e  mov     edi, eax
0x1800e2960  mov     [rsp+118h+var_B8], eax
0x1800e2964  mov     rsi, [rsp+118h+var_B0]
0x1800e2969  test    eax, eax
0x1800e296b  js      loc_1800E2A9C
0x1800e2971  mov     r14d, [rsi]
0x1800e2974  mov     ecx, 2
0x1800e2979  cmp     r14d, ecx
0x1800e297c  jz      loc_1800E2A55
0x1800e2982  mov     r12b, r13b
0x1800e2985  mov     rax, r14
0x1800e2988  shr     rax, 1
0x1800e298b  add     eax, [r15+18h]
0x1800e298f  add     eax, ecx
0x1800e2991  mov     [rsp+118h+arg_8], eax
0x1800e2998  mov     rdx, [rsp+118h+arg_10]
0x1800e29a0  mov     ecx, [rdx]
0x1800e29a2  mov     [rsp+118h+var_A0], ecx
0x1800e29a6  cmp     ecx, eax
0x1800e29a8  sbb     edi, edi
0x1800e29aa  and     edi, 80000005h
0x1800e29b0  mov     [rdx], eax
0x1800e29b2  cmp     eax, ecx
0x1800e29b4  ja      loc_1800E2A50
0x1800e29ba  lea     rdx, [rsi+4]; Src
0x1800e29be  mov     r8, r14; Size
0x1800e29c1  mov     rcx, [rsp+118h+arg_18]; void *
0x1800e29c9  call    memcpy_0
0x1800e29ce  test    r12b, r12b
0x1800e29d1  mov     r12, [rsp+118h+arg_18]
0x1800e29d9  jnz     short loc_1800E29E9
0x1800e29db  mov     eax, 5Ch ; '\'
0x1800e29e0  mov     [r12+r14], ax
0x1800e29e5  add     r14d, 2
0x1800e29e9  mov     r8d, [r15+18h]
0x1800e29ed  add     r8, r8; Size
0x1800e29f0  lea     rdx, [r15+1Ch]; Src
0x1800e29f4  mov     ecx, r14d
0x1800e29f7  add     rcx, r12; void *
0x1800e29fa  call    memcpy_0
0x1800e29ff  mov     eax, [r15+18h]
0x1800e2a03  lea     ecx, [r14+rax*2]
0x1800e2a07  xor     r13d, r13d
0x1800e2a0a  mov     [rcx+r12], r13w
0x1800e2a0f  mov     eax, [rsp+118h+arg_8]
0x1800e2a16  mov     ecx, [rsp+118h+var_A0]
0x1800e2a1a  mov     [rsp+118h+var_B8], edi
0x1800e2a1e  cmp     eax, ecx
0x1800e2a20  ja      short loc_1800E2A9C
0x1800e2a22  mov     rcx, [rbx+8]
0x1800e2a26  cmp     [r15+8], r13d
0x1800e2a2a  jbe     short loc_1800E2A5D
0x1800e2a2c  mov     eax, [r15+8]
0x1800e2a30  add     rcx, 8
0x1800e2a34  add     rcx, rax
0x1800e2a37  mov     [rbx+10h], rcx
0x1800e2a3b  jmp     short loc_1800E2A9C
0x1800e2a3d  mov     r14d, [rsi]
0x1800e2a40  jmp     loc_1800E288D
0x1800e2a45  mov     edi, 0C000009Ah
0x1800e2a4a  mov     [rsp+118h+var_B8], edi
0x1800e2a4e  jmp     short loc_1800E2A9C
0x1800e2a50  xor     r13d, r13d
0x1800e2a53  jmp     short loc_1800E2A1A
0x1800e2a55  mov     ecx, r12d
0x1800e2a58  jmp     loc_1800E2985
0x1800e2a5d  mov     rax, [rsp+118h+IoStatusBlock.Information]
0x1800e2a65  jmp     short loc_1800E2A34
0x1800e2a67  mov     rcx, gs:60h
0x1800e2a70  mov     r8, rbx; P
0x1800e2a73  xor     edx, edx; Flags
0x1800e2a75  mov     rcx, [rcx+30h]; HeapHandle
0x1800e2a79  call    cs:__imp_RtlFreeHeap
0x1800e2a80  nop     dword ptr [rax+rax+00h]
0x1800e2a85  mov     rbx, r13
0x1800e2a88  mov     [rsp+118h+var_70], rbx
0x1800e2a90  jmp     loc_1800E2877
0x1800e2a95  mov     edi, 0C0000011h
0x1800e2a9a  jmp     short loc_1800E2A4A
0x1800e2a9c  cmp     [rsp+118h+var_80], r13w
0x1800e2aa5  jz      short loc_1800E2ACA
0x1800e2aa7  mov     rcx, gs:60h
0x1800e2ab0  mov     r8, [rsp+118h+P]; P
0x1800e2ab8  xor     edx, edx; Flags
0x1800e2aba  mov     rcx, [rcx+30h]; HeapHandle
0x1800e2abe  call    cs:__imp_RtlFreeHeap
0x1800e2ac5  nop     dword ptr [rax+rax+00h]
0x1800e2aca  test    rsi, rsi
0x1800e2acd  jz      short loc_1800E2AED
0x1800e2acf  mov     rcx, gs:60h
0x1800e2ad8  mov     r8, rsi; P
0x1800e2adb  xor     edx, edx; Flags
0x1800e2add  mov     rcx, [rcx+30h]; HeapHandle
0x1800e2ae1  call    cs:__imp_RtlFreeHeap
0x1800e2ae8  nop     dword ptr [rax+rax+00h]
0x1800e2aed  test    edi, edi
0x1800e2aef  jnz     short loc_1800E2B08
0x1800e2af1  mov     rax, rbx
0x1800e2af4  add     rsp, 0E0h
0x1800e2afb  pop     r15
0x1800e2afd  pop     r14
0x1800e2aff  pop     r13
0x1800e2b01  pop     r12
0x1800e2b03  pop     rdi
0x1800e2b04  pop     rsi
0x1800e2b05  pop     rbx
0x1800e2b06  retn
0x1800e2b08  mov     ecx, edi
0x1800e2b0a  call    BaseSetLastNTError
0x1800e2b0f  mov     rcx, [rsp+118h+FileHandle]; Handle
0x1800e2b14  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e2b18  jnz     short loc_1800E2B43
0x1800e2b1a  test    rbx, rbx
0x1800e2b1d  jnz     short loc_1800E2B51
0x1800e2b1f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e2b23  jmp     short loc_1800E2AF1
0x1800e2b25  mov     ecx, 57h ; 'W'; LastError
0x1800e2b2a  call    cs:__imp_RtlSetLastWin32Error
0x1800e2b31  nop     dword ptr [rax+rax+00h]
0x1800e2b36  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e2b3a  jmp     short loc_1800E2AF4
0x1800e2b3c  mov     ecx, 3
0x1800e2b41  jmp     short loc_1800E2B2A
0x1800e2b43  call    cs:__imp_NtClose
0x1800e2b4a  nop     dword ptr [rax+rax+00h]
0x1800e2b4f  jmp     short loc_1800E2B1A
0x1800e2b51  mov     rcx, rbx; hFindFile
0x1800e2b54  call    FindClose
0x1800e2b59  jmp     short loc_1800E2B1F
0x180198246  push    rbp
0x180198248  sub     rsp, 60h
0x18019824c  mov     rbp, rdx
0x18019824f  cmp     word ptr [rbp+98h], 0
0x180198257  jz      short loc_18019827C
0x180198259  mov     rcx, gs:60h
0x180198262  mov     r8, [rbp+0A0h]; P
0x180198269  xor     edx, edx; Flags
0x18019826b  mov     rcx, [rcx+30h]; HeapHandle
0x18019826f  call    cs:__imp_RtlFreeHeap
0x180198276  nop     dword ptr [rax+rax+00h]
0x18019827b  nop
0x18019827c  mov     r8, [rbp+68h]; P
0x180198280  test    r8, r8
0x180198283  jz      short loc_1801982A1
0x180198285  mov     rcx, gs:60h
0x18019828e  xor     edx, edx; Flags
0x180198290  mov     rcx, [rcx+30h]; HeapHandle
0x180198294  call    cs:__imp_RtlFreeHeap
0x18019829b  nop     dword ptr [rax+rax+00h]
0x1801982a0  nop
0x1801982a1  mov     ecx, [rbp+60h]
0x1801982a4  test    ecx, ecx
0x1801982a6  jz      short loc_1801982E1
0x1801982a8  call    BaseSetLastNTError
0x1801982ad  mov     rcx, [rbp+70h]; Handle
0x1801982b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801982b5  jz      short loc_1801982C4
0x1801982b7  call    cs:__imp_NtClose
0x1801982be  nop     dword ptr [rax+rax+00h]
0x1801982c3  nop
0x1801982c4  mov     rcx, [rbp+80h]; hFindFile
0x1801982cb  test    rcx, rcx
0x1801982ce  jz      short loc_1801982D6
0x1801982d0  call    FindClose
0x1801982d5  nop
0x1801982d6  mov     qword ptr [rbp+80h], 0FFFFFFFFFFFFFFFFh
0x1801982e1  add     rsp, 60h
0x1801982e5  pop     rbp
0x1801982e6  retn
```
