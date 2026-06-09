# BasepGetNameNonVolatileFromReg

- ea: `0x18003a338`
- end: `0x18003a45b`
- name: `BasepGetNameNonVolatileFromReg`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b35c`

## callees

- `0x18003a338`
- `0x18003a464`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003a448`
- `ntdll!RtlFreeHeap` at `0x18003a448`
- `ntdll!RtlAllocateHeap` at `0x18003a400`
- `ntdll!RtlAllocateHeap` at `0x18003a400`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003a3dd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003a3dd`

## string_xrefs

- `0x18003a36d`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18003a3cd`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18003a366`: `DnscacheTcpipParameters`
- `0x18003a3c6`: `DnscacheTcpipParameters`
- `0x18003a386`: `ComputerName`
- `0x18003a37f`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ComputerName`

## pseudocode

```c
PVOID __fastcall BasepGetNameNonVolatileFromReg(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  const wchar_t *v5; // rdi
  const wchar_t *v6; // rsi
  const wchar_t *v7; // rbp
  PVOID Heap; // rbx
  int NameFromReg; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  ULONG *GlobalData; // rax
  unsigned int v16; // [rsp+60h] [rbp+8h] BYREF

  v16 = 0;
  if ( !a1 )
    goto LABEL_8;
  v1 = a1 - 1;
  if ( !v1 )
  {
LABEL_13:
    v5 = L"DnscacheTcpipParameters";
    v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
    v7 = L"NV Hostname";
LABEL_9:
    Heap = 0;
    NameFromReg = BasepGetNameFromReg((_DWORD)v5, (_DWORD)v6, (_DWORD)v7, 0, (__int64)&v16);
    if ( NameFromReg == -2147483643 )
    {
      GlobalData = (ULONG *)KernelBaseGetGlobalData(v11, v10, v12, v13);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2LL * v16);
      if ( !Heap )
        return 0;
      NameFromReg = BasepGetNameFromReg((_DWORD)v5, (_DWORD)v6, (_DWORD)v7, (_DWORD)Heap, (__int64)&v16);
    }
    if ( NameFromReg >= 0 )
      return Heap;
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    return 0;
  }
  v2 = v1 - 1;
  if ( !v2 )
  {
LABEL_7:
    v5 = L"DnscacheTcpipParameters";
    v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
    v7 = L"NV Domain";
    goto LABEL_9;
  }
  v3 = v2 - 2;
  if ( !v3 )
  {
LABEL_8:
    LODWORD(v5) = 0;
    v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ComputerName";
    v7 = L"ComputerName";
    goto LABEL_9;
  }
  v4 = v3 - 1;
  if ( !v4 )
    goto LABEL_13;
  if ( v4 == 1 )
    goto LABEL_7;
  return 0;
}

```

## disassembly

```asm
0x18003a338  push    rbx
0x18003a33a  push    rbp
0x18003a33b  push    rsi
0x18003a33c  push    rdi
0x18003a33d  sub     rsp, 38h
0x18003a341  mov     [rsp+58h+arg_0], 0
0x18003a349  test    ecx, ecx
0x18003a34b  jz      short loc_18003A37D
0x18003a34d  sub     ecx, 1
0x18003a350  jz      short loc_18003A3C6
0x18003a352  sub     ecx, 1
0x18003a355  jz      short loc_18003A366
0x18003a357  sub     ecx, 2
0x18003a35a  jz      short loc_18003A37D
0x18003a35c  sub     ecx, 1
0x18003a35f  jz      short loc_18003A3C6
0x18003a361  cmp     ecx, 1
0x18003a364  jnz     short loc_18003A3C2
0x18003a366  lea     rdi, aDnscachetcpipp; "DnscacheTcpipParameters"
0x18003a36d  lea     rsi, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003a374  lea     rbp, aNvDomain; "NV Domain"
0x18003a37b  jmp     short loc_18003A38D
0x18003a37d  xor     edi, edi
0x18003a37f  lea     rsi, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003a386  lea     rbp, aComputername; "ComputerName"
0x18003a38d  lea     rax, [rsp+58h+arg_0]
0x18003a392  xor     r9d, r9d
0x18003a395  mov     r8, rbp
0x18003a398  mov     [rsp+58h+var_38], rax
0x18003a39d  mov     rdx, rsi
0x18003a3a0  mov     rcx, rdi
0x18003a3a3  xor     ebx, ebx
0x18003a3a5  call    BasepGetNameFromReg
0x18003a3aa  cmp     eax, 80000005h
0x18003a3af  jz      short loc_18003A3DD
0x18003a3b1  test    eax, eax
0x18003a3b3  js      short loc_18003A431
0x18003a3b5  mov     rax, rbx
0x18003a3b8  add     rsp, 38h
0x18003a3bc  pop     rdi
0x18003a3bd  pop     rsi
0x18003a3be  pop     rbp
0x18003a3bf  pop     rbx
0x18003a3c0  retn
0x18003a3c2  xor     eax, eax
0x18003a3c4  jmp     short loc_18003A3B8
0x18003a3c6  lea     rdi, aDnscachetcpipp; "DnscacheTcpipParameters"
0x18003a3cd  lea     rsi, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003a3d4  lea     rbp, aNvHostname; "NV Hostname"
0x18003a3db  jmp     short loc_18003A38D
0x18003a3dd  call    cs:__imp_KernelBaseGetGlobalData
0x18003a3e4  nop     dword ptr [rax+rax+00h]
0x18003a3e9  mov     rcx, gs:60h
0x18003a3f2  mov     r8d, [rsp+58h+arg_0]
0x18003a3f7  add     r8, r8; Size
0x18003a3fa  mov     edx, [rax]; Flags
0x18003a3fc  mov     rcx, [rcx+30h]; HeapHandle
0x18003a400  call    cs:__imp_RtlAllocateHeap
0x18003a407  nop     dword ptr [rax+rax+00h]
0x18003a40c  mov     rbx, rax
0x18003a40f  test    rax, rax
0x18003a412  jz      short loc_18003A454
0x18003a414  lea     rax, [rsp+58h+arg_0]
0x18003a419  mov     r9, rbx
0x18003a41c  mov     r8, rbp
0x18003a41f  mov     [rsp+58h+var_38], rax
0x18003a424  mov     rdx, rsi
0x18003a427  mov     rcx, rdi
0x18003a42a  call    BasepGetNameFromReg
0x18003a42f  jmp     short loc_18003A3B1
0x18003a431  test    rbx, rbx
0x18003a434  jz      short loc_18003A454
0x18003a436  mov     rcx, gs:60h
0x18003a43f  mov     r8, rbx; P
0x18003a442  xor     edx, edx; Flags
0x18003a444  mov     rcx, [rcx+30h]; HeapHandle
0x18003a448  call    cs:__imp_RtlFreeHeap
0x18003a44f  nop     dword ptr [rax+rax+00h]
0x18003a454  xor     ebx, ebx
0x18003a456  jmp     loc_18003A3B5
```
