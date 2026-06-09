# BaseIsNetBiosNameInUse

- ea: `0x18006f378`
- end: `0x18006f5bd`
- name: `BaseIsNetBiosNameInUse`
- size: `581`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006fd70`

## callees

- `0x18003a464`
- `0x180041720`
- `0x18006f378`
- `0x18006fa60`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006f3cd`
- `ntdll!RtlNtStatusToDosError` at `0x18006f45a`
- `ntdll!RtlNtStatusToDosError` at `0x18006f3cd`
- `ntdll!RtlNtStatusToDosError` at `0x18006f45a`
- `ntdll!RtlSetLastWin32Error` at `0x18006f41d`
- `ntdll!RtlSetLastWin32Error` at `0x18006f41d`
- `ntdll!RtlFreeHeap` at `0x18006f573`
- `ntdll!RtlFreeHeap` at `0x18006f596`
- `ntdll!RtlFreeHeap` at `0x18006f573`
- `ntdll!RtlFreeHeap` at `0x18006f596`
- `ntdll!RtlAllocateHeap` at `0x18006f406`
- `ntdll!RtlAllocateHeap` at `0x18006f4f0`
- `ntdll!RtlAllocateHeap` at `0x18006f406`
- `ntdll!RtlAllocateHeap` at `0x18006f4f0`
- `ntdll!_wcsicmp` at `0x18006f52a`
- `ntdll!_wcsicmp` at `0x18006f52a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006f3e4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006f4d1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006f3e4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006f4d1`

## string_xrefs

- `0x18006f3ba`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18006f445`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18006f3af`: `AlternateComputerNames`
- `0x18006f439`: `AlternateComputerNames`
- `0x18006f39d`: `Dnscache`
- `0x18006f44c`: `Dnscache`

## pseudocode

```c
ULONG __fastcall BaseIsNetBiosNameInUse(wchar_t *String2)
{
  wchar_t *Heap; // r14
  NTSTATUS NameFromReg; // eax
  ULONG result; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  ULONG *GlobalData; // rax
  NTSTATUS v10; // eax
  WCHAR *v11; // rsi
  int v12; // edi
  int v13; // r15d
  int v14; // r12d
  ULONG MultiValueAddr; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rbx
  ULONG *v21; // rax
  WCHAR *v22; // rax
  DWORD nSize; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+50h] BYREF
  int v25; // [rsp+98h] [rbp+58h]

  Heap = 0;
  v24 = 0;
  v25 = 0;
  nSize = 0;
  NameFromReg = BasepGetNameFromReg(
                  (unsigned int)L"Dnscache",
                  (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\DnsCache\\Parameters",
                  (unsigned int)L"AlternateComputerNames",
                  0,
                  (__int64)&v24);
  result = RtlNtStatusToDosError(NameFromReg);
  if ( result == 234 )
  {
    GlobalData = (ULONG *)KernelBaseGetGlobalData(v6, v5, v7, v8);
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2LL * v24);
    if ( !Heap )
    {
      RtlSetLastWin32Error(8u);
      return 1;
    }
    v10 = BasepGetNameFromReg(
            (unsigned int)L"Dnscache",
            (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\DnsCache\\Parameters",
            (unsigned int)L"AlternateComputerNames",
            (_DWORD)Heap,
            (__int64)&v24);
    result = RtlNtStatusToDosError(v10);
  }
  if ( result || Heap )
  {
    v11 = 0;
    v12 = 1;
    if ( result )
      goto LABEL_24;
    v13 = 0;
    v14 = 0;
    while ( 1 )
    {
      MultiValueAddr = BasepGetMultiValueAddr(Heap);
      if ( !MultiValueAddr )
      {
        if ( DnsHostnameToComputerNameW(0, v11, &nSize) )
          goto LABEL_16;
        MultiValueAddr = NtCurrentTeb()->LastErrorValue;
        if ( MultiValueAddr == 234 )
        {
          v20 = ++nSize;
          v21 = (ULONG *)KernelBaseGetGlobalData(v17, v16, v18, v19);
          v22 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v21, 2 * v20);
          v11 = v22;
          if ( !v22 )
          {
            MultiValueAddr = 8;
LABEL_22:
            if ( MultiValueAddr == 1168 )
              v12 = v13;
LABEL_24:
            if ( Heap )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            if ( v11 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
            return v12;
          }
          if ( DnsHostnameToComputerNameW(0, v22, &nSize) )
          {
            MultiValueAddr = 0;
LABEL_16:
            if ( !_wcsicmp(v11, String2) )
              v13 = 1;
            goto LABEL_18;
          }
          MultiValueAddr = NtCurrentTeb()->LastErrorValue;
        }
        if ( !MultiValueAddr )
          goto LABEL_16;
      }
LABEL_18:
      ++v14;
      if ( MultiValueAddr )
        goto LABEL_22;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006f378  mov     [rsp-38h+arg_0], rbx
0x18006f37d  push    rbp
0x18006f37e  push    rsi
0x18006f37f  push    rdi
0x18006f380  push    r12
0x18006f382  push    r13
0x18006f384  push    r14
0x18006f386  push    r15
0x18006f388  mov     rbp, rsp
0x18006f38b  sub     rsp, 40h
0x18006f38f  xor     r14d, r14d
0x18006f392  lea     rax, [rbp+arg_10]
0x18006f396  mov     r13, rcx
0x18006f399  mov     [rbp+arg_10], r14d
0x18006f39d  lea     rcx, aDnscache; "Dnscache"
0x18006f3a4  mov     [rbp+Hostname], r14
0x18006f3a8  xor     r9d, r9d
0x18006f3ab  mov     [rbp+arg_18], r14d
0x18006f3af  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18006f3b6  mov     [rbp+nSize], r14d
0x18006f3ba  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006f3c1  mov     [rsp+40h+var_20], rax
0x18006f3c6  call    BasepGetNameFromReg
0x18006f3cb  mov     ecx, eax; Status
0x18006f3cd  call    cs:__imp_RtlNtStatusToDosError
0x18006f3d4  nop     dword ptr [rax+rax+00h]
0x18006f3d9  cmp     eax, 0EAh
0x18006f3de  jnz     loc_18006F466
0x18006f3e4  call    cs:__imp_KernelBaseGetGlobalData
0x18006f3eb  nop     dword ptr [rax+rax+00h]
0x18006f3f0  mov     rcx, gs:60h
0x18006f3f9  mov     r8d, [rbp+arg_10]
0x18006f3fd  add     r8, r8; Size
0x18006f400  mov     edx, [rax]; Flags
0x18006f402  mov     rcx, [rcx+30h]; HeapHandle
0x18006f406  call    cs:__imp_RtlAllocateHeap
0x18006f40d  nop     dword ptr [rax+rax+00h]
0x18006f412  mov     r14, rax
0x18006f415  test    rax, rax
0x18006f418  jnz     short loc_18006F432
0x18006f41a  lea     ecx, [rax+8]; LastError
0x18006f41d  call    cs:__imp_RtlSetLastWin32Error
0x18006f424  nop     dword ptr [rax+rax+00h]
0x18006f429  lea     eax, [r14+1]
0x18006f42d  jmp     loc_18006F5A4
0x18006f432  lea     rax, [rbp+arg_10]
0x18006f436  mov     r9, r14
0x18006f439  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18006f440  mov     [rsp+40h+var_20], rax
0x18006f445  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006f44c  lea     rcx, aDnscache; "Dnscache"
0x18006f453  call    BasepGetNameFromReg
0x18006f458  mov     ecx, eax; Status
0x18006f45a  call    cs:__imp_RtlNtStatusToDosError
0x18006f461  nop     dword ptr [rax+rax+00h]
0x18006f466  test    eax, eax
0x18006f468  jnz     short loc_18006F473
0x18006f46a  test    r14, r14
0x18006f46d  jz      loc_18006F5A4
0x18006f473  xor     esi, esi
0x18006f475  lea     edi, [rsi+1]
0x18006f478  test    eax, eax
0x18006f47a  jnz     loc_18006F55C
0x18006f480  xor     r15d, r15d
0x18006f483  xor     r12d, r12d
0x18006f486  lea     r9, [rbp+arg_18]
0x18006f48a  mov     edx, r12d
0x18006f48d  lea     r8, [rbp+Hostname]
0x18006f491  mov     rcx, r14; String
0x18006f494  call    BasepGetMultiValueAddr
0x18006f499  mov     ebx, eax
0x18006f49b  test    eax, eax
0x18006f49d  jnz     loc_18006F53C
0x18006f4a3  mov     rcx, [rbp+Hostname]; Hostname
0x18006f4a7  lea     r8, [rbp+nSize]; nSize
0x18006f4ab  mov     rdx, rsi; ComputerName
0x18006f4ae  call    DnsHostnameToComputerNameW
0x18006f4b3  test    eax, eax
0x18006f4b5  jnz     short loc_18006F524
0x18006f4b7  mov     ebx, gs:68h
0x18006f4bf  cmp     ebx, 0EAh
0x18006f4c5  jnz     short loc_18006F520
0x18006f4c7  mov     eax, [rbp+nSize]
0x18006f4ca  add     eax, edi
0x18006f4cc  mov     [rbp+nSize], eax
0x18006f4cf  mov     ebx, eax
0x18006f4d1  call    cs:__imp_KernelBaseGetGlobalData
0x18006f4d8  nop     dword ptr [rax+rax+00h]
0x18006f4dd  mov     rcx, gs:60h
0x18006f4e6  lea     r8, [rbx+rbx]; Size
0x18006f4ea  mov     edx, [rax]; Flags
0x18006f4ec  mov     rcx, [rcx+30h]; HeapHandle
0x18006f4f0  call    cs:__imp_RtlAllocateHeap
0x18006f4f7  nop     dword ptr [rax+rax+00h]
0x18006f4fc  mov     rsi, rax
0x18006f4ff  test    rax, rax
0x18006f502  jz      short loc_18006F54D
0x18006f504  mov     rcx, [rbp+Hostname]; Hostname
0x18006f508  lea     r8, [rbp+nSize]; nSize
0x18006f50c  mov     rdx, rax; ComputerName
0x18006f50f  call    DnsHostnameToComputerNameW
0x18006f514  test    eax, eax
0x18006f516  jnz     short loc_18006F549
0x18006f518  mov     ebx, gs:68h
0x18006f520  test    ebx, ebx
0x18006f522  jnz     short loc_18006F53C
0x18006f524  mov     rdx, r13; String2
0x18006f527  mov     rcx, rsi; String1
0x18006f52a  call    cs:__imp__wcsicmp
0x18006f531  nop     dword ptr [rax+rax+00h]
0x18006f536  test    eax, eax
0x18006f538  cmovz   r15d, edi
0x18006f53c  add     r12d, edi
0x18006f53f  test    ebx, ebx
0x18006f541  jz      loc_18006F486
0x18006f547  jmp     short loc_18006F552
0x18006f549  xor     ebx, ebx
0x18006f54b  jmp     short loc_18006F524
0x18006f54d  mov     ebx, 8
0x18006f552  cmp     ebx, 490h
0x18006f558  cmovz   edi, r15d
0x18006f55c  test    r14, r14
0x18006f55f  jz      short loc_18006F57F
0x18006f561  mov     rcx, gs:60h
0x18006f56a  mov     r8, r14; P
0x18006f56d  xor     edx, edx; Flags
0x18006f56f  mov     rcx, [rcx+30h]; HeapHandle
0x18006f573  call    cs:__imp_RtlFreeHeap
0x18006f57a  nop     dword ptr [rax+rax+00h]
0x18006f57f  test    rsi, rsi
0x18006f582  jz      short loc_18006F5A2
0x18006f584  mov     rcx, gs:60h
0x18006f58d  mov     r8, rsi; P
0x18006f590  xor     edx, edx; Flags
0x18006f592  mov     rcx, [rcx+30h]; HeapHandle
0x18006f596  call    cs:__imp_RtlFreeHeap
0x18006f59d  nop     dword ptr [rax+rax+00h]
0x18006f5a2  mov     eax, edi
0x18006f5a4  mov     rbx, [rsp+40h+arg_0]
0x18006f5ac  add     rsp, 40h
0x18006f5b0  pop     r15
0x18006f5b2  pop     r14
0x18006f5b4  pop     r13
0x18006f5b6  pop     r12
0x18006f5b8  pop     rdi
0x18006f5b9  pop     rsi
0x18006f5ba  pop     rbp
0x18006f5bb  retn
```
