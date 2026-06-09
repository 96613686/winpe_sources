# BaseIsAltDnsFQHostname

- ea: `0x180054128`
- end: `0x180054265`
- name: `BaseIsAltDnsFQHostname`
- size: `317`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053cc0`

## callees

- `0x18003a464`
- `0x18003a504`
- `0x180054128`
- `0x18006f2bc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005420e`
- `ntdll!RtlNtStatusToDosError` at `0x18005420e`
- `ntdll!RtlFreeHeap` at `0x180054246`
- `ntdll!RtlFreeHeap` at `0x180054246`
- `ntdll!RtlAllocateHeap` at `0x1800541d1`
- `ntdll!RtlAllocateHeap` at `0x1800541d1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800541b2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800541b2`

## string_xrefs

- `0x180054156`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18005418c`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x1800541f9`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18005414a`: `AlternateComputerNames`
- `0x180054183`: `AlternateComputerNames`
- `0x1800541ed`: `AlternateComputerNames`
- `0x18005415d`: `Dnscache`
- `0x180054200`: `Dnscache`

## pseudocode

```c
__int64 __fastcall BaseIsAltDnsFQHostname(void *Buf2)
{
  unsigned int v1; // edi
  unsigned int ValueFromReg; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rbx
  ULONG *GlobalData; // rax
  wchar_t *Heap; // rbx
  NTSTATUS NameFromReg; // eax
  unsigned int v14; // [rsp+48h] [rbp+10h] BYREF
  int v15; // [rsp+50h] [rbp+18h]

  v1 = 0;
  v15 = 0;
  v14 = 0;
  ValueFromReg = BasepGetValueFromReg(
                   L"Dnscache",
                   L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\DnsCache\\Parameters",
                   L"AlternateComputerNames",
                   0,
                   &v14);
  v7 = ValueFromReg;
  if ( ValueFromReg == -1073741772 )
  {
    v14 = 0;
    v7 = (unsigned int)BasepGetValueFromReg(
                         0,
                         L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\DnsCache\\Parameters",
                         L"AlternateComputerNames",
                         0,
                         &v14);
  }
  v8 = v14 >> 1;
  v14 >>= 1;
  if ( (_DWORD)v7 == -2147483643 )
  {
    v9 = v8;
    GlobalData = (ULONG *)KernelBaseGetGlobalData(v7, v4, v5, v6);
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2 * v9);
    if ( Heap )
    {
      NameFromReg = BasepGetNameFromReg(
                      (unsigned int)L"Dnscache",
                      (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\DnsCache\\Parameters",
                      (unsigned int)L"AlternateComputerNames",
                      (_DWORD)Heap,
                      (__int64)&v14);
      if ( !RtlNtStatusToDosError(NameFromReg) )
        LOBYTE(v1) = (unsigned int)BaseGetMultiValueIndex(Heap, Buf2) == 0;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180054128  mov     rax, rsp
0x18005412b  mov     [rax+8], rbx
0x18005412f  mov     [rax+20h], rsi
0x180054133  push    rdi
0x180054134  sub     rsp, 30h
0x180054138  xor     edi, edi
0x18005413a  mov     rsi, rcx
0x18005413d  mov     [rax+18h], edi
0x180054140  xor     r9d, r9d
0x180054143  mov     [rax+10h], edi
0x180054146  lea     rax, [rax+10h]
0x18005414a  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x180054151  mov     [rsp+38h+var_18], rax
0x180054156  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x18005415d  lea     rcx, aDnscache; "Dnscache"
0x180054164  call    BasepGetValueFromReg
0x180054169  mov     ecx, eax
0x18005416b  cmp     eax, 0C0000034h
0x180054170  jnz     short loc_18005419A
0x180054172  lea     rax, [rsp+38h+arg_8]
0x180054177  mov     [rsp+38h+arg_8], edi
0x18005417b  xor     r9d, r9d
0x18005417e  mov     [rsp+38h+var_18], rax
0x180054183  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18005418a  xor     ecx, ecx
0x18005418c  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x180054193  call    BasepGetValueFromReg
0x180054198  mov     ecx, eax
0x18005419a  mov     eax, [rsp+38h+arg_8]
0x18005419e  shr     eax, 1
0x1800541a0  mov     [rsp+38h+arg_8], eax
0x1800541a4  cmp     ecx, 80000005h
0x1800541aa  jnz     loc_180054252
0x1800541b0  mov     ebx, eax
0x1800541b2  call    cs:__imp_KernelBaseGetGlobalData
0x1800541b9  nop     dword ptr [rax+rax+00h]
0x1800541be  mov     rcx, gs:60h
0x1800541c7  lea     r8, [rbx+rbx]; Size
0x1800541cb  mov     edx, [rax]; Flags
0x1800541cd  mov     rcx, [rcx+30h]; HeapHandle
0x1800541d1  call    cs:__imp_RtlAllocateHeap
0x1800541d8  nop     dword ptr [rax+rax+00h]
0x1800541dd  mov     rbx, rax
0x1800541e0  test    rax, rax
0x1800541e3  jz      short loc_180054252
0x1800541e5  lea     rax, [rsp+38h+arg_8]
0x1800541ea  mov     r9, rbx
0x1800541ed  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x1800541f4  mov     [rsp+38h+var_18], rax
0x1800541f9  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x180054200  lea     rcx, aDnscache; "Dnscache"
0x180054207  call    BasepGetNameFromReg
0x18005420c  mov     ecx, eax; Status
0x18005420e  call    cs:__imp_RtlNtStatusToDosError
0x180054215  nop     dword ptr [rax+rax+00h]
0x18005421a  test    eax, eax
0x18005421c  jnz     short loc_180054234
0x18005421e  lea     r8, [rsp+38h+arg_10]
0x180054223  mov     rdx, rsi; Buf2
0x180054226  mov     rcx, rbx; String
0x180054229  call    BaseGetMultiValueIndex
0x18005422e  test    eax, eax
0x180054230  setz    dil
0x180054234  mov     rcx, gs:60h
0x18005423d  mov     r8, rbx; P
0x180054240  xor     edx, edx; Flags
0x180054242  mov     rcx, [rcx+30h]; HeapHandle
0x180054246  call    cs:__imp_RtlFreeHeap
0x18005424d  nop     dword ptr [rax+rax+00h]
0x180054252  mov     rbx, [rsp+38h+arg_0]
0x180054257  mov     eax, edi
0x180054259  mov     rsi, [rsp+38h+arg_18]
0x18005425e  add     rsp, 30h
0x180054262  pop     rdi
0x180054263  retn
```
