# ThpCreateRawSnap

- ea: `0x18004a5d0`
- end: `0x18004a8d0`
- name: `ThpCreateRawSnap`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006c250`

## callees

- `0x18004a5d0`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x18004a6c7`
- `ntdll!NtFreeVirtualMemory` at `0x18004a890`
- `ntdll!NtFreeVirtualMemory` at `0x18004a6c7`
- `ntdll!NtFreeVirtualMemory` at `0x18004a890`
- `ntdll!NtAllocateVirtualMemory` at `0x18004a651`
- `ntdll!NtAllocateVirtualMemory` at `0x18004a651`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004a778`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004a8a1`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004a8b4`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004a778`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004a8a1`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18004a8b4`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004a75e`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004a836`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004a75e`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18004a836`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004a714`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004a793`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004a7f9`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004a714`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004a793`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18004a7f9`
- `ntdll!NtQuerySystemInformation` at `0x18004a6a6`
- `ntdll!NtQuerySystemInformation` at `0x18004a6a6`

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
0x18004a5d0  mov     rax, rsp
0x18004a5d3  mov     [rax+20h], r9
0x18004a5d7  mov     [rax+18h], r8
0x18004a5db  mov     [rax+10h], edx
0x18004a5de  mov     [rax+8], ecx
0x18004a5e1  push    rbx
0x18004a5e2  push    rsi
0x18004a5e3  push    rdi
0x18004a5e4  push    r12
0x18004a5e6  push    r13
0x18004a5e8  push    r14
0x18004a5ea  push    r15
0x18004a5ec  sub     rsp, 40h
0x18004a5f0  mov     rsi, r9
0x18004a5f3  mov     r14, r8
0x18004a5f6  mov     eax, edx
0x18004a5f8  mov     r13d, ecx
0x18004a5fb  xor     ebx, ebx
0x18004a5fd  mov     edi, ebx
0x18004a5ff  mov     ecx, 10000h
0x18004a604  mov     [rsp+78h+ReturnLength], ecx
0x18004a608  mov     [rsp+78h+RegionSize], rcx
0x18004a60d  mov     [r8], rbx
0x18004a610  mov     [r9], rbx
0x18004a613  mov     r12, [rsp+78h+ProcessId]
0x18004a61b  mov     [r12], rbx
0x18004a61f  test    r13b, 6
0x18004a623  jz      loc_18004A6FF
0x18004a629  mov     eax, [rsp+78h+ReturnLength]
0x18004a62d  mov     [rsp+78h+RegionSize], rax
0x18004a632  mov     [rsp+78h+Protect], 4; Protect
0x18004a63a  mov     [rsp+78h+AllocationType], 1000h; AllocationType
0x18004a642  lea     r9, [rsp+78h+RegionSize]; RegionSize
0x18004a647  xor     r8d, r8d; ZeroBits
0x18004a64a  mov     rdx, r14; BaseAddress
0x18004a64d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004a651  call    cs:__imp_NtAllocateVirtualMemory
0x18004a657  mov     edi, eax
0x18004a659  mov     [rsp+78h+var_44], eax
0x18004a65d  jmp     short loc_18004A687
0x18004a65f  mov     edi, eax
0x18004a661  mov     [rsp+78h+var_44], eax
0x18004a665  xor     ebx, ebx
0x18004a667  mov     r12, [rsp+78h+ProcessId]
0x18004a66f  mov     rsi, [rsp+78h+arg_18]
0x18004a677  mov     r14, [rsp+78h+arg_10]
0x18004a67f  mov     r13d, [rsp+78h+arg_0]
0x18004a687  test    edi, edi
0x18004a689  js      loc_18004A842
0x18004a68f  mov     r8, [rsp+78h+RegionSize]; SystemInformationLength
0x18004a694  mov     [rsp+78h+ReturnLength], r8d
0x18004a699  lea     r9, [rsp+78h+ReturnLength]; ReturnLength
0x18004a69e  mov     rdx, [r14]; SystemInformation
0x18004a6a1  mov     ecx, 5; SystemInformationClass
0x18004a6a6  call    cs:__imp_NtQuerySystemInformation
0x18004a6ac  mov     edi, eax
0x18004a6ae  cmp     eax, 0C0000004h
0x18004a6b3  jnz     short loc_18004A6E4
0x18004a6b5  mov     r9d, 8000h; FreeType
0x18004a6bb  lea     r8, [rsp+78h+RegionSize]; RegionSize
0x18004a6c0  mov     rdx, r14; BaseAddress
0x18004a6c3  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004a6c7  call    cs:__imp_NtFreeVirtualMemory
0x18004a6cd  mov     [r14], rbx
0x18004a6d0  mov     eax, [rsp+78h+ReturnLength]
0x18004a6d4  add     eax, 1FFFh
0x18004a6d9  and     eax, 0FFFFE000h
0x18004a6de  mov     [rsp+78h+ReturnLength], eax
0x18004a6e2  jmp     short loc_18004A6EC
0x18004a6e4  test    edi, edi
0x18004a6e6  js      loc_18004A842
0x18004a6ec  cmp     edi, 0C0000004h
0x18004a6f2  jz      loc_18004A629
0x18004a6f8  mov     eax, [rsp+78h+arg_8]
0x18004a6ff  test    r13b, 18h
0x18004a703  jz      loc_18004A7EC
0x18004a709  xor     edx, edx; EventPair
0x18004a70b  mov     r15d, 400000h
0x18004a711  mov     ecx, r15d; Size
0x18004a714  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18004a71a  mov     rcx, rax
0x18004a71d  mov     [rsi], rax
0x18004a720  test    rax, rax
0x18004a723  jz      loc_18004A7E5
0x18004a729  mov     edx, r13d
0x18004a72c  and     edx, 10h
0x18004a72f  shl     edx, 2
0x18004a732  mov     eax, r13d
0x18004a735  shr     eax, 3
0x18004a738  and     eax, 1
0x18004a73b  or      edx, eax
0x18004a73d  bts     edx, 1Fh; DebugInfoClassMask
0x18004a741  mov     [rsp+78h+arg_0], edx
0x18004a748  movsxd  rax, [rsp+78h+arg_8]
0x18004a750  mov     [rsp+78h+ProcessId], rax
0x18004a758  mov     r8, rcx; DebugBuffer
0x18004a75b  mov     rcx, rax; ProcessId
0x18004a75e  call    cs:__imp_RtlQueryProcessDebugInformation
0x18004a764  mov     edi, eax
0x18004a766  test    eax, eax
0x18004a768  jns     short loc_18004A7B7
0x18004a76a  cmp     eax, 0C0000023h
0x18004a76f  jnz     loc_18004A83E
0x18004a775  mov     rcx, [rsi]; DebugBuffer
0x18004a778  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18004a77e  mov     [rsi], rbx
0x18004a781  mov     ecx, r15d
0x18004a784  shr     ecx, 1
0x18004a786  add     ecx, r15d; Size
0x18004a789  cmp     ecx, r15d
0x18004a78c  jb      short loc_18004A7AD
0x18004a78e  mov     r15d, ecx
0x18004a791  xor     edx, edx; EventPair
0x18004a793  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18004a799  mov     rcx, rax
0x18004a79c  mov     [rsi], rax
0x18004a79f  test    rax, rax
0x18004a7a2  jz      short loc_18004A7E5
0x18004a7a4  mov     edx, [rsp+78h+arg_0]
0x18004a7ab  jmp     short loc_18004A748
0x18004a7ad  mov     edi, 0C0000017h
0x18004a7b2  jmp     loc_18004A83E
0x18004a7b7  mov     rax, [rsi]
0x18004a7ba  mov     rcx, [rax+8]
0x18004a7be  mov     rax, [rsp+78h+arg_20]
0x18004a7c6  mov     [rax], rcx
0x18004a7c9  mov     rax, [rsi]
0x18004a7cc  mov     rcx, [rax+58h]
0x18004a7d0  mov     rax, [rsp+78h+arg_28]
0x18004a7d8  mov     [rax], rcx
0x18004a7db  mov     r15, [rsp+78h+ProcessId]
0x18004a7e3  jmp     short loc_18004A7EF
0x18004a7e5  mov     edi, 0C0000001h
0x18004a7ea  jmp     short loc_18004A842
0x18004a7ec  movsxd  r15, eax
0x18004a7ef  test    r13b, 1
0x18004a7f3  jz      short loc_18004A83E
0x18004a7f5  xor     edx, edx; EventPair
0x18004a7f7  xor     ecx, ecx; Size
0x18004a7f9  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18004a7ff  mov     [r12], rax
0x18004a803  test    rax, rax
0x18004a806  jz      short loc_18004A7E5
0x18004a808  mov     r8, [rax+8]
0x18004a80c  mov     rax, [rsp+78h+arg_38]
0x18004a814  mov     [rax], r8
0x18004a817  mov     rax, [r12]
0x18004a81b  mov     r8, [rax+58h]
0x18004a81f  mov     rax, [rsp+78h+arg_40]
0x18004a827  mov     [rax], r8
0x18004a82a  mov     r8, [r12]; DebugBuffer
0x18004a82e  mov     edx, 4; DebugInfoClassMask
0x18004a833  mov     rcx, r15; ProcessId
0x18004a836  call    cs:__imp_RtlQueryProcessDebugInformation
0x18004a83c  mov     edi, eax
0x18004a83e  test    edi, edi
0x18004a840  jns     short loc_18004A8BE
0x18004a842  mov     rax, [rsp+78h+arg_20]
0x18004a84a  mov     [rax], rbx
0x18004a84d  mov     rax, [rsp+78h+arg_28]
0x18004a855  mov     [rax], rbx
0x18004a858  mov     rax, [rsp+78h+arg_38]
0x18004a860  mov     [rax], rbx
0x18004a863  mov     rax, [rsp+78h+arg_40]
0x18004a86b  mov     [rax], rbx
0x18004a86e  cmp     [r14], rbx
0x18004a871  jz      short loc_18004A899
0x18004a873  mov     [rsp+78h+ProcessId], rbx
0x18004a87b  mov     r9d, 8000h; FreeType
0x18004a881  lea     r8, [rsp+78h+ProcessId]; RegionSize
0x18004a889  mov     rdx, r14; BaseAddress
0x18004a88c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004a890  call    cs:__imp_NtFreeVirtualMemory
0x18004a896  mov     [r14], rbx
0x18004a899  cmp     [rsi], rbx
0x18004a89c  jz      short loc_18004A8AA
0x18004a89e  mov     rcx, [rsi]; DebugBuffer
0x18004a8a1  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18004a8a7  mov     [rsi], rbx
0x18004a8aa  cmp     [r12], rbx
0x18004a8ae  jz      short loc_18004A8BE
0x18004a8b0  mov     rcx, [r12]; DebugBuffer
0x18004a8b4  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18004a8ba  mov     [r12], rbx
0x18004a8be  mov     eax, edi
0x18004a8c0  add     rsp, 40h
0x18004a8c4  pop     r15
0x18004a8c6  pop     r14
0x18004a8c8  pop     r13
0x18004a8ca  pop     r12
0x18004a8cc  pop     rdi
0x18004a8cd  pop     rsi
0x18004a8ce  pop     rbx
0x18004a8cf  retn
0x18007ba3a  push    rbp
0x18007ba3c  sub     rsp, 30h
0x18007ba40  mov     rbp, rdx
0x18007ba43  mov     rax, [rcx]
0x18007ba46  xor     ecx, ecx
0x18007ba48  cmp     dword ptr [rax], 0C00000FDh
0x18007ba4e  setnz   cl
0x18007ba51  mov     eax, ecx
0x18007ba53  add     rsp, 30h
0x18007ba57  pop     rbp
0x18007ba58  retn
```
