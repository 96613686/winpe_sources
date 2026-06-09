# BaseIsAltDnsFQHostname

- ea: `0x18004f13c`
- end: `0x18004f260`
- name: `BaseIsAltDnsFQHostname`
- size: `292`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ed70`

## callees

- `0x1800378d4`
- `0x180037974`
- `0x18004f13c`
- `0x18006828c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004f216`
- `ntdll!RtlNtStatusToDosError` at `0x18004f216`
- `ntdll!RtlFreeHeap` at `0x18004f248`
- `ntdll!RtlFreeHeap` at `0x18004f248`
- `ntdll!RtlAllocateHeap` at `0x18004f1df`
- `ntdll!RtlAllocateHeap` at `0x18004f1df`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004f1c6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004f1c6`

## string_xrefs

- `0x18004f16a`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18004f1a0`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18004f201`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x18004f15e`: `AlternateComputerNames`
- `0x18004f197`: `AlternateComputerNames`
- `0x18004f1f5`: `AlternateComputerNames`
- `0x18004f171`: `Dnscache`
- `0x18004f208`: `Dnscache`

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
0x18004f13c  mov     rax, rsp
0x18004f13f  mov     [rax+8], rbx
0x18004f143  mov     [rax+20h], rsi
0x18004f147  push    rdi
0x18004f148  sub     rsp, 30h
0x18004f14c  xor     edi, edi
0x18004f14e  mov     rsi, rcx
0x18004f151  mov     [rax+18h], edi
0x18004f154  xor     r9d, r9d
0x18004f157  mov     [rax+10h], edi
0x18004f15a  lea     rax, [rax+10h]
0x18004f15e  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18004f165  mov     [rsp+38h+var_18], rax
0x18004f16a  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x18004f171  lea     rcx, aDnscache; "Dnscache"
0x18004f178  call    BasepGetValueFromReg
0x18004f17d  mov     ecx, eax
0x18004f17f  cmp     eax, 0C0000034h
0x18004f184  jnz     short loc_18004F1AE
0x18004f186  lea     rax, [rsp+38h+arg_8]
0x18004f18b  mov     [rsp+38h+arg_8], edi
0x18004f18f  xor     r9d, r9d
0x18004f192  mov     [rsp+38h+var_18], rax
0x18004f197  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18004f19e  xor     ecx, ecx
0x18004f1a0  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x18004f1a7  call    BasepGetValueFromReg
0x18004f1ac  mov     ecx, eax
0x18004f1ae  mov     eax, [rsp+38h+arg_8]
0x18004f1b2  shr     eax, 1
0x18004f1b4  mov     [rsp+38h+arg_8], eax
0x18004f1b8  cmp     ecx, 80000005h
0x18004f1be  jnz     loc_18004F24E
0x18004f1c4  mov     ebx, eax
0x18004f1c6  call    cs:__imp_KernelBaseGetGlobalData
0x18004f1cc  mov     rcx, gs:60h
0x18004f1d5  lea     r8, [rbx+rbx]; Size
0x18004f1d9  mov     edx, [rax]; Flags
0x18004f1db  mov     rcx, [rcx+30h]; HeapHandle
0x18004f1df  call    cs:__imp_RtlAllocateHeap
0x18004f1e5  mov     rbx, rax
0x18004f1e8  test    rax, rax
0x18004f1eb  jz      short loc_18004F24E
0x18004f1ed  lea     rax, [rsp+38h+arg_8]
0x18004f1f2  mov     r9, rbx
0x18004f1f5  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18004f1fc  mov     [rsp+38h+var_18], rax
0x18004f201  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x18004f208  lea     rcx, aDnscache; "Dnscache"
0x18004f20f  call    BasepGetNameFromReg
0x18004f214  mov     ecx, eax; Status
0x18004f216  call    cs:__imp_RtlNtStatusToDosError
0x18004f21c  test    eax, eax
0x18004f21e  jnz     short loc_18004F236
0x18004f220  lea     r8, [rsp+38h+arg_10]
0x18004f225  mov     rdx, rsi; Buf2
0x18004f228  mov     rcx, rbx; String
0x18004f22b  call    BaseGetMultiValueIndex
0x18004f230  test    eax, eax
0x18004f232  setz    dil
0x18004f236  mov     rcx, gs:60h
0x18004f23f  mov     r8, rbx; P
0x18004f242  xor     edx, edx; Flags
0x18004f244  mov     rcx, [rcx+30h]; HeapHandle
0x18004f248  call    cs:__imp_RtlFreeHeap
0x18004f24e  mov     rbx, [rsp+38h+arg_0]
0x18004f253  mov     eax, edi
0x18004f255  mov     rsi, [rsp+38h+arg_18]
0x18004f25a  add     rsp, 30h
0x18004f25e  pop     rdi
0x18004f25f  retn
```
