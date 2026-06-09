# ThpCreateRawSnap

- ea: `0x18004ebb0`
- end: `0x18004eefd`
- name: `ThpCreateRawSnap`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180073800`

## callees

- `0x18004ebb0`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x18004ecb3`
- `ntdll!NtFreeVirtualMemory` at `0x18004eeaa`
- `ntdll!NtFreeVirtualMemory` at `0x18004ecb3`
- `ntdll!NtFreeVirtualMemory` at `0x18004eeaa`
- `ntdll!NtAllocateVirtualMemory` at `0x18004ec31`
- `ntdll!NtAllocateVirtualMemory` at `0x18004ec31`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004ed76`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004eec1`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004eeda`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004ed76`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004eec1`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004eeda`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004ed56`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004ee46`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004ed56`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004ee46`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004ed06`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004ed97`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004ee03`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004ed06`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004ed97`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004ee03`
- `ntdll!NtQuerySystemInformation` at `0x18004ec8c`
- `ntdll!NtQuerySystemInformation` at `0x18004ec8c`

## pseudocode

```c
__int64 __fastcall ThpCreateRawSnap(
        unsigned int a1,
        signed int a2,
        PVOID *a3,
        PRTL_DEBUG_INFORMATION *a4,
        PVOID *a5,
        PRTL_PROCESS_BACKTRACES *a6,
        ULONG_PTR ProcessId,
        PVOID *a8,
        PRTL_PROCESS_BACKTRACES *a9)
{
  ULONG v11; // eax
  NTSTATUS VirtualMemory; // edi
  PRTL_DEBUG_INFORMATION *v14; // r12
  unsigned int v15; // r15d
  struct _RTL_DEBUG_INFORMATION *QueryDebugBuffer; // rcx
  ULONG i; // edx
  NTSTATUS ProcessDebugInformation; // eax
  ULONG v19; // ecx
  ULONG v20; // r15d
  PRTL_DEBUG_INFORMATION v21; // rax
  ULONG ReturnLength[2]; // [rsp+30h] [rbp-48h] BYREF
  ULONG_PTR RegionSize[8]; // [rsp+38h] [rbp-40h] BYREF

  v11 = a2;
  VirtualMemory = 0;
  ReturnLength[0] = 0x10000;
  RegionSize[0] = 0x10000;
  *a3 = 0;
  *a4 = 0;
  v14 = (PRTL_DEBUG_INFORMATION *)ProcessId;
  *(_QWORD *)ProcessId = 0;
  if ( (a1 & 6) != 0 )
  {
    while ( 1 )
    {
      RegionSize[0] = ReturnLength[0];
      VirtualMemory = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, a3, 0, RegionSize, 0x1000u, 4u);
      ReturnLength[1] = VirtualMemory;
      if ( VirtualMemory < 0 )
        goto LABEL_24;
      ReturnLength[0] = RegionSize[0];
      VirtualMemory = NtQuerySystemInformation(SystemProcessInformation, *a3, RegionSize[0], ReturnLength);
      if ( VirtualMemory == -1073741820 )
      {
        NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, a3, RegionSize, 0x8000u);
        *a3 = 0;
        ReturnLength[0] = (ReturnLength[0] + 0x1FFF) & 0xFFFFE000;
      }
      else if ( VirtualMemory < 0 )
      {
        goto LABEL_24;
      }
      if ( VirtualMemory != -1073741820 )
      {
        v11 = a2;
        break;
      }
    }
  }
  if ( (a1 & 0x18) != 0 )
  {
    v15 = 0x400000;
    QueryDebugBuffer = RtlCreateQueryDebugBuffer(0x400000u, 0);
    *a4 = QueryDebugBuffer;
    if ( !QueryDebugBuffer )
      goto LABEL_18;
    for ( i = (a1 >> 3) & 1 | (4 * (a1 & 0x10)) | 0x80000000; ; i = (a1 >> 3) & 1 | (4 * (a1 & 0x10)) | 0x80000000 )
    {
      ProcessId = a2;
      ProcessDebugInformation = RtlQueryProcessDebugInformation(a2, i, QueryDebugBuffer);
      VirtualMemory = ProcessDebugInformation;
      if ( ProcessDebugInformation >= 0 )
        break;
      if ( ProcessDebugInformation != -1073741789 )
        goto LABEL_23;
      RtlDestroyQueryDebugBuffer(*a4);
      *a4 = 0;
      v19 = v15 + (v15 >> 1);
      if ( v19 < v15 )
      {
        VirtualMemory = -1073741801;
        goto LABEL_23;
      }
      v15 += v15 >> 1;
      QueryDebugBuffer = RtlCreateQueryDebugBuffer(v19, 0);
      *a4 = QueryDebugBuffer;
      if ( !QueryDebugBuffer )
        goto LABEL_18;
    }
    *a5 = (*a4)->ViewBaseClient;
    *a6 = (*a4)->BackTraces;
    v20 = ProcessId;
  }
  else
  {
    v20 = v11;
  }
  if ( (a1 & 1) == 0 )
    goto LABEL_23;
  v21 = RtlCreateQueryDebugBuffer(0, 0);
  *v14 = v21;
  if ( v21 )
  {
    *a8 = v21->ViewBaseClient;
    *a9 = (*v14)->BackTraces;
    VirtualMemory = RtlQueryProcessDebugInformation(v20, 4u, *v14);
LABEL_23:
    if ( VirtualMemory >= 0 )
      return (unsigned int)VirtualMemory;
    goto LABEL_24;
  }
LABEL_18:
  VirtualMemory = -1073741823;
LABEL_24:
  *a5 = 0;
  *a6 = 0;
  *a8 = 0;
  *a9 = 0;
  if ( *a3 )
  {
    ProcessId = 0;
    NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, a3, &ProcessId, 0x8000u);
    *a3 = 0;
  }
  if ( *a4 )
  {
    RtlDestroyQueryDebugBuffer(*a4);
    *a4 = 0;
  }
  if ( *v14 )
  {
    RtlDestroyQueryDebugBuffer(*v14);
    *v14 = 0;
  }
  return (unsigned int)VirtualMemory;
}

```

## disassembly

```asm
0x18004ebb0  mov     rax, rsp
0x18004ebb3  mov     [rax+20h], r9
0x18004ebb7  mov     [rax+18h], r8
0x18004ebbb  mov     [rax+10h], edx
0x18004ebbe  mov     [rax+8], ecx
0x18004ebc1  push    rbx
0x18004ebc2  push    rsi
0x18004ebc3  push    rdi
0x18004ebc4  push    r12
0x18004ebc6  push    r13
0x18004ebc8  push    r14
0x18004ebca  push    r15
0x18004ebcc  sub     rsp, 40h
0x18004ebd0  mov     rsi, r9
0x18004ebd3  mov     r14, r8
0x18004ebd6  mov     eax, edx
0x18004ebd8  mov     r13d, ecx
0x18004ebdb  xor     ebx, ebx
0x18004ebdd  mov     edi, ebx
0x18004ebdf  mov     ecx, 10000h
0x18004ebe4  mov     [rsp+78h+ReturnLength], ecx
0x18004ebe8  mov     [rsp+78h+RegionSize], rcx
0x18004ebed  mov     [r8], rbx
0x18004ebf0  mov     [r9], rbx
0x18004ebf3  mov     r12, [rsp+78h+ProcessId]
0x18004ebfb  mov     [r12], rbx
0x18004ebff  test    r13b, 6
0x18004ec03  jz      loc_18004ECF1
0x18004ec09  mov     eax, [rsp+78h+ReturnLength]
0x18004ec0d  mov     [rsp+78h+RegionSize], rax
0x18004ec12  mov     [rsp+78h+Protect], 4; Protect
0x18004ec1a  mov     [rsp+78h+AllocationType], 1000h; AllocationType
0x18004ec22  lea     r9, [rsp+78h+RegionSize]; RegionSize
0x18004ec27  xor     r8d, r8d; ZeroBits
0x18004ec2a  mov     rdx, r14; BaseAddress
0x18004ec2d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004ec31  call    cs:__imp_NtAllocateVirtualMemory
0x18004ec38  nop     dword ptr [rax+rax+00h]
0x18004ec3d  mov     edi, eax
0x18004ec3f  mov     [rsp+78h+var_44], eax
0x18004ec43  jmp     short loc_18004EC6D
0x18004ec45  mov     edi, eax
0x18004ec47  mov     [rsp+78h+var_44], eax
0x18004ec4b  xor     ebx, ebx
0x18004ec4d  mov     r12, [rsp+78h+ProcessId]
0x18004ec55  mov     rsi, [rsp+78h+arg_18]
0x18004ec5d  mov     r14, [rsp+78h+arg_10]
0x18004ec65  mov     r13d, [rsp+78h+arg_0]
0x18004ec6d  test    edi, edi
0x18004ec6f  js      loc_18004EE5C
0x18004ec75  mov     r8, [rsp+78h+RegionSize]; SystemInformationLength
0x18004ec7a  mov     [rsp+78h+ReturnLength], r8d
0x18004ec7f  lea     r9, [rsp+78h+ReturnLength]; ReturnLength
0x18004ec84  mov     rdx, [r14]; SystemInformation
0x18004ec87  mov     ecx, 5; SystemInformationClass
0x18004ec8c  call    cs:__imp_NtQuerySystemInformation
0x18004ec93  nop     dword ptr [rax+rax+00h]
0x18004ec98  mov     edi, eax
0x18004ec9a  cmp     eax, 0C0000004h
0x18004ec9f  jnz     short loc_18004ECD6
0x18004eca1  mov     r9d, 8000h; FreeType
0x18004eca7  lea     r8, [rsp+78h+RegionSize]; RegionSize
0x18004ecac  mov     rdx, r14; BaseAddress
0x18004ecaf  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004ecb3  call    cs:__imp_NtFreeVirtualMemory
0x18004ecba  nop     dword ptr [rax+rax+00h]
0x18004ecbf  mov     [r14], rbx
0x18004ecc2  mov     eax, [rsp+78h+ReturnLength]
0x18004ecc6  add     eax, 1FFFh
0x18004eccb  and     eax, 0FFFFE000h
0x18004ecd0  mov     [rsp+78h+ReturnLength], eax
0x18004ecd4  jmp     short loc_18004ECDE
0x18004ecd6  test    edi, edi
0x18004ecd8  js      loc_18004EE5C
0x18004ecde  cmp     edi, 0C0000004h
0x18004ece4  jz      loc_18004EC09
0x18004ecea  mov     eax, [rsp+78h+arg_8]
0x18004ecf1  test    r13b, 18h
0x18004ecf5  jz      loc_18004EDF6
0x18004ecfb  xor     edx, edx; EventPair
0x18004ecfd  mov     r15d, 400000h
0x18004ed03  mov     ecx, r15d; Size
0x18004ed06  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18004ed0d  nop     dword ptr [rax+rax+00h]
0x18004ed12  mov     rcx, rax
0x18004ed15  mov     [rsi], rax
0x18004ed18  test    rax, rax
0x18004ed1b  jz      loc_18004EDEF
0x18004ed21  mov     edx, r13d
0x18004ed24  and     edx, 10h
0x18004ed27  shl     edx, 2
0x18004ed2a  mov     eax, r13d
0x18004ed2d  shr     eax, 3
0x18004ed30  and     eax, 1
0x18004ed33  or      edx, eax
0x18004ed35  bts     edx, 1Fh; DebugInfoClassMask
0x18004ed39  mov     [rsp+78h+arg_0], edx
0x18004ed40  movsxd  rax, [rsp+78h+arg_8]
0x18004ed48  mov     [rsp+78h+ProcessId], rax
0x18004ed50  mov     r8, rcx; DebugBuffer
0x18004ed53  mov     rcx, rax; ProcessId
0x18004ed56  call    cs:__imp_RtlQueryProcessDebugInformation
0x18004ed5d  nop     dword ptr [rax+rax+00h]
0x18004ed62  mov     edi, eax
0x18004ed64  test    eax, eax
0x18004ed66  jns     short loc_18004EDC1
0x18004ed68  cmp     eax, 0C0000023h
0x18004ed6d  jnz     loc_18004EE54
0x18004ed73  mov     rcx, [rsi]; DebugBuffer
0x18004ed76  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18004ed7d  nop     dword ptr [rax+rax+00h]
0x18004ed82  mov     [rsi], rbx
0x18004ed85  mov     ecx, r15d
0x18004ed88  shr     ecx, 1
0x18004ed8a  add     ecx, r15d; Size
0x18004ed8d  cmp     ecx, r15d
0x18004ed90  jb      short loc_18004EDB7
0x18004ed92  mov     r15d, ecx
0x18004ed95  xor     edx, edx; EventPair
0x18004ed97  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18004ed9e  nop     dword ptr [rax+rax+00h]
0x18004eda3  mov     rcx, rax
0x18004eda6  mov     [rsi], rax
0x18004eda9  test    rax, rax
0x18004edac  jz      short loc_18004EDEF
0x18004edae  mov     edx, [rsp+78h+arg_0]
0x18004edb5  jmp     short loc_18004ED40
0x18004edb7  mov     edi, 0C0000017h
0x18004edbc  jmp     loc_18004EE54
0x18004edc1  mov     rax, [rsi]
0x18004edc4  mov     rcx, [rax+8]
0x18004edc8  mov     rax, [rsp+78h+arg_20]
0x18004edd0  mov     [rax], rcx
0x18004edd3  mov     rax, [rsi]
0x18004edd6  mov     rcx, [rax+58h]
0x18004edda  mov     rax, [rsp+78h+arg_28]
0x18004ede2  mov     [rax], rcx
0x18004ede5  mov     r15, [rsp+78h+ProcessId]
0x18004eded  jmp     short loc_18004EDF9
0x18004edef  mov     edi, 0C0000001h
0x18004edf4  jmp     short loc_18004EE5C
0x18004edf6  movsxd  r15, eax
0x18004edf9  test    r13b, 1
0x18004edfd  jz      short loc_18004EE54
0x18004edff  xor     edx, edx; EventPair
0x18004ee01  xor     ecx, ecx; Size
0x18004ee03  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18004ee0a  nop     dword ptr [rax+rax+00h]
0x18004ee0f  mov     [r12], rax
0x18004ee13  test    rax, rax
0x18004ee16  jz      short loc_18004EDEF
0x18004ee18  mov     r8, [rax+8]
0x18004ee1c  mov     rax, [rsp+78h+arg_38]
0x18004ee24  mov     [rax], r8
0x18004ee27  mov     rax, [r12]
0x18004ee2b  mov     r8, [rax+58h]
0x18004ee2f  mov     rax, [rsp+78h+arg_40]
0x18004ee37  mov     [rax], r8
0x18004ee3a  mov     r8, [r12]; DebugBuffer
0x18004ee3e  mov     edx, 4; DebugInfoClassMask
0x18004ee43  mov     rcx, r15; ProcessId
0x18004ee46  call    cs:__imp_RtlQueryProcessDebugInformation
0x18004ee4d  nop     dword ptr [rax+rax+00h]
0x18004ee52  mov     edi, eax
0x18004ee54  test    edi, edi
0x18004ee56  jns     loc_18004EEEA
0x18004ee5c  mov     rax, [rsp+78h+arg_20]
0x18004ee64  mov     [rax], rbx
0x18004ee67  mov     rax, [rsp+78h+arg_28]
0x18004ee6f  mov     [rax], rbx
0x18004ee72  mov     rax, [rsp+78h+arg_38]
0x18004ee7a  mov     [rax], rbx
0x18004ee7d  mov     rax, [rsp+78h+arg_40]
0x18004ee85  mov     [rax], rbx
0x18004ee88  cmp     [r14], rbx
0x18004ee8b  jz      short loc_18004EEB9
0x18004ee8d  mov     [rsp+78h+ProcessId], rbx
0x18004ee95  mov     r9d, 8000h; FreeType
0x18004ee9b  lea     r8, [rsp+78h+ProcessId]; RegionSize
0x18004eea3  mov     rdx, r14; BaseAddress
0x18004eea6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004eeaa  call    cs:__imp_NtFreeVirtualMemory
0x18004eeb1  nop     dword ptr [rax+rax+00h]
0x18004eeb6  mov     [r14], rbx
0x18004eeb9  cmp     [rsi], rbx
0x18004eebc  jz      short loc_18004EED0
0x18004eebe  mov     rcx, [rsi]; DebugBuffer
0x18004eec1  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18004eec8  nop     dword ptr [rax+rax+00h]
0x18004eecd  mov     [rsi], rbx
0x18004eed0  cmp     [r12], rbx
0x18004eed4  jz      short loc_18004EEEA
0x18004eed6  mov     rcx, [r12]; DebugBuffer
0x18004eeda  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18004eee1  nop     dword ptr [rax+rax+00h]
0x18004eee6  mov     [r12], rbx
0x18004eeea  mov     eax, edi
0x18004eeec  add     rsp, 40h
0x18004eef0  pop     r15
0x18004eef2  pop     r14
0x18004eef4  pop     r13
0x18004eef6  pop     r12
0x18004eef8  pop     rdi
0x18004eef9  pop     rsi
0x18004eefa  pop     rbx
0x18004eefb  retn
0x180083bc3  push    rbp
0x180083bc5  sub     rsp, 30h
0x180083bc9  mov     rbp, rdx
0x180083bcc  mov     rax, [rcx]
0x180083bcf  xor     ecx, ecx
0x180083bd1  cmp     dword ptr [rax], 0C00000FDh
0x180083bd7  setnz   cl
0x180083bda  mov     eax, ecx
0x180083bdc  add     rsp, 30h
0x180083be0  pop     rbp
0x180083be1  retn
```
