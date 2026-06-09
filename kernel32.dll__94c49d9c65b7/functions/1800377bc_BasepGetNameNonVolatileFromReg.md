# BasepGetNameNonVolatileFromReg

- ea: `0x1800377bc`
- end: `0x1800378cc`
- name: `BasepGetNameNonVolatileFromReg`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180046ce0`

## callees

- `0x1800377bc`
- `0x1800378d4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800378bf`
- `ntdll!RtlFreeHeap` at `0x1800378bf`
- `ntdll!RtlAllocateHeap` at `0x18003787d`
- `ntdll!RtlAllocateHeap` at `0x18003787d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180037860`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180037860`

## string_xrefs

- `0x1800377f1`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180037850`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x1800377ea`: `DnscacheTcpipParameters`
- `0x180037849`: `DnscacheTcpipParameters`
- `0x18003780a`: `ComputerName`
- `0x180037803`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ComputerName`

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
0x1800377bc  push    rbx
0x1800377be  push    rbp
0x1800377bf  push    rsi
0x1800377c0  push    rdi
0x1800377c1  sub     rsp, 38h
0x1800377c5  mov     [rsp+58h+arg_0], 0
0x1800377cd  test    ecx, ecx
0x1800377cf  jz      short loc_180037801
0x1800377d1  sub     ecx, 1
0x1800377d4  jz      short loc_180037849
0x1800377d6  sub     ecx, 1
0x1800377d9  jz      short loc_1800377EA
0x1800377db  sub     ecx, 2
0x1800377de  jz      short loc_180037801
0x1800377e0  sub     ecx, 1
0x1800377e3  jz      short loc_180037849
0x1800377e5  cmp     ecx, 1
0x1800377e8  jnz     short loc_180037845
0x1800377ea  lea     rdi, aDnscachetcpipp; "DnscacheTcpipParameters"
0x1800377f1  lea     rsi, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800377f8  lea     rbp, aNvDomain; "NV Domain"
0x1800377ff  jmp     short loc_180037811
0x180037801  xor     edi, edi
0x180037803  lea     rsi, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003780a  lea     rbp, aComputername; "ComputerName"
0x180037811  lea     rax, [rsp+58h+arg_0]
0x180037816  xor     r9d, r9d
0x180037819  mov     r8, rbp
0x18003781c  mov     [rsp+58h+var_38], rax
0x180037821  mov     rdx, rsi
0x180037824  mov     rcx, rdi
0x180037827  xor     ebx, ebx
0x180037829  call    BasepGetNameFromReg
0x18003782e  cmp     eax, 80000005h
0x180037833  jz      short loc_180037860
0x180037835  test    eax, eax
0x180037837  js      short loc_1800378A8
0x180037839  mov     rax, rbx
0x18003783c  add     rsp, 38h
0x180037840  pop     rdi
0x180037841  pop     rsi
0x180037842  pop     rbp
0x180037843  pop     rbx
0x180037844  retn
0x180037845  xor     eax, eax
0x180037847  jmp     short loc_18003783C
0x180037849  lea     rdi, aDnscachetcpipp; "DnscacheTcpipParameters"
0x180037850  lea     rsi, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x180037857  lea     rbp, aNvHostname; "NV Hostname"
0x18003785e  jmp     short loc_180037811
0x180037860  call    cs:__imp_KernelBaseGetGlobalData
0x180037866  mov     rcx, gs:60h
0x18003786f  mov     r8d, [rsp+58h+arg_0]
0x180037874  add     r8, r8; Size
0x180037877  mov     edx, [rax]; Flags
0x180037879  mov     rcx, [rcx+30h]; HeapHandle
0x18003787d  call    cs:__imp_RtlAllocateHeap
0x180037883  mov     rbx, rax
0x180037886  test    rax, rax
0x180037889  jz      short loc_1800378C5
0x18003788b  lea     rax, [rsp+58h+arg_0]
0x180037890  mov     r9, rbx
0x180037893  mov     r8, rbp
0x180037896  mov     [rsp+58h+var_38], rax
0x18003789b  mov     rdx, rsi
0x18003789e  mov     rcx, rdi
0x1800378a1  call    BasepGetNameFromReg
0x1800378a6  jmp     short loc_180037835
0x1800378a8  test    rbx, rbx
0x1800378ab  jz      short loc_1800378C5
0x1800378ad  mov     rcx, gs:60h
0x1800378b6  mov     r8, rbx; P
0x1800378b9  xor     edx, edx; Flags
0x1800378bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800378bf  call    cs:__imp_RtlFreeHeap
0x1800378c5  xor     ebx, ebx
0x1800378c7  jmp     loc_180037839
```
