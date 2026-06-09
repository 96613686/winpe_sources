# SetLocalPrimaryComputerNameW

- ea: `0x18004ed70`
- end: `0x18004f07b`
- name: `SetLocalPrimaryComputerNameW`
- size: `779`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068d70`

## callees

- `0x180046ce0`
- `0x18004ed70`
- `0x18004f084`
- `0x18004f13c`
- `0x1800687e4`
- `0x180068820`
- `0x180068c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004eddc`
- `ntdll!RtlFreeHeap` at `0x18004edf9`
- `ntdll!RtlFreeHeap` at `0x18004eeb2`
- `ntdll!RtlFreeHeap` at `0x18004eef4`
- `ntdll!RtlFreeHeap` at `0x18004ef9e`
- `ntdll!RtlFreeHeap` at `0x18004efe8`
- `ntdll!RtlFreeHeap` at `0x18004f051`
- `ntdll!RtlFreeHeap` at `0x18004f06e`
- `ntdll!RtlFreeHeap` at `0x18004eddc`
- `ntdll!RtlFreeHeap` at `0x18004edf9`
- `ntdll!RtlFreeHeap` at `0x18004eeb2`
- `ntdll!RtlFreeHeap` at `0x18004eef4`
- `ntdll!RtlFreeHeap` at `0x18004ef9e`
- `ntdll!RtlFreeHeap` at `0x18004efe8`
- `ntdll!RtlFreeHeap` at `0x18004f051`
- `ntdll!RtlFreeHeap` at `0x18004f06e`
- `ntdll!RtlAllocateHeap` at `0x18004ee5e`
- `ntdll!RtlAllocateHeap` at `0x18004ef47`
- `ntdll!RtlAllocateHeap` at `0x18004ee5e`
- `ntdll!RtlAllocateHeap` at `0x18004ef47`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004ee41`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004ef2a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004ee41`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004ef2a`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18004effa`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18004f018`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18004effa`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18004f018`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ee23`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ee7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ef0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ef6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ee23`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ee7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ef0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004ef6a`

## pseudocode

```c
__int64 __fastcall SetLocalPrimaryComputerNameW(wchar_t *Buf2, int a2)
{
  void *v4; // rbp
  void *v5; // rsi
  ULONG LastErrorValue; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rax
  WCHAR *v14; // rdi
  void *NameNonVolatile; // rax
  void *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  ULONG *v21; // rax
  WCHAR *v22; // rax
  WCHAR *v23; // rdi
  void *v24; // rax
  void *v25; // rdi
  DWORD nSize; // [rsp+40h] [rbp+8h] BYREF
  DWORD v27; // [rsp+50h] [rbp+18h] BYREF

  nSize = 0;
  v27 = 0;
  v4 = (void *)BaseParseDnsName(Buf2);
  v5 = (void *)BaseParseDnsName(Buf2);
  if ( !Buf2 || a2 )
    return 87;
  if ( !(unsigned int)BaseIsAltDnsFQHostname(Buf2) )
  {
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    return 87;
  }
  LastErrorValue = 0;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, 0, &nSize) )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    if ( LastErrorValue == 234 )
    {
      GlobalData = (ULONG *)KernelBaseGetGlobalData(v9, v8, v10, v11);
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2LL * nSize);
      v14 = Heap;
      if ( Heap )
      {
        if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Heap, &nSize) && (unsigned int)BaseSetAltNetBiosName(v14) )
          LastErrorValue = 0;
        else
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      }
      else
      {
        LastErrorValue = 8;
      }
    }
  }
  NameNonVolatile = (void *)BasepGetNameNonVolatile(4);
  v16 = NameNonVolatile;
  if ( NameNonVolatile )
  {
    if ( (unsigned int)BaseSetAltNetBiosName(NameNonVolatile) )
      LastErrorValue = 0;
    else
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
  }
  if ( !LastErrorValue )
  {
    if ( !GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, 0, &v27) )
    {
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      if ( LastErrorValue == 234 )
      {
        v21 = (ULONG *)KernelBaseGetGlobalData(v18, v17, v19, v20);
        v22 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v21, 2LL * v27);
        v23 = v22;
        if ( !v22 )
        {
          LastErrorValue = 8;
          goto LABEL_44;
        }
        if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, v22, &v27)
          && (unsigned int)BaseSetAltDnsFQHostname(v23) )
        {
          LastErrorValue = 0;
        }
        else
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      }
      if ( LastErrorValue )
        goto LABEL_44;
    }
    v24 = (void *)BasepGetNameNonVolatile(7);
    v25 = v24;
    if ( !v24
      || ((unsigned int)BaseSetAltDnsFQHostname(v24)
        ? (LastErrorValue = 0)
        : (LastErrorValue = NtCurrentTeb()->LastErrorValue),
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25),
          !LastErrorValue) )
    {
      if ( (SetComputerNameExW(ComputerNamePhysicalDnsHostname, (LPCWSTR)v4)
         || (LastErrorValue = NtCurrentTeb()->LastErrorValue) == 0)
        && (SetComputerNameExW(ComputerNamePhysicalDnsDomain, (LPCWSTR)v5)
         || (LastErrorValue = NtCurrentTeb()->LastErrorValue) == 0) )
      {
        LastErrorValue = RemoveLocalAlternateComputerNameW(Buf2);
      }
    }
  }
LABEL_44:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return LastErrorValue;
}

```

## disassembly

```asm
0x18004ed70  mov     rax, rsp
0x18004ed73  mov     [rax+10h], rbx
0x18004ed77  mov     [rax+20h], rbp
0x18004ed7b  push    rsi
0x18004ed7c  push    rdi
0x18004ed7d  push    r14
0x18004ed7f  sub     rsp, 20h
0x18004ed83  mov     ebx, edx
0x18004ed85  mov     dword ptr [rax+8], 0
0x18004ed8c  xor     edx, edx
0x18004ed8e  mov     dword ptr [rax+18h], 0
0x18004ed95  mov     r14, rcx
0x18004ed98  call    BaseParseDnsName
0x18004ed9d  mov     edx, 1
0x18004eda2  mov     rcx, r14; String
0x18004eda5  mov     rbp, rax
0x18004eda8  call    BaseParseDnsName
0x18004edad  mov     rsi, rax
0x18004edb0  test    r14, r14
0x18004edb3  jz      short loc_18004EDFF
0x18004edb5  test    ebx, ebx
0x18004edb7  jnz     short loc_18004EDFF
0x18004edb9  mov     rcx, r14; Buf2
0x18004edbc  call    BaseIsAltDnsFQHostname
0x18004edc1  test    eax, eax
0x18004edc3  jnz     short loc_18004EE17
0x18004edc5  test    rbp, rbp
0x18004edc8  jz      short loc_18004EDE2
0x18004edca  mov     rcx, gs:60h
0x18004edd3  mov     r8, rbp; P
0x18004edd6  xor     edx, edx; Flags
0x18004edd8  mov     rcx, [rcx+30h]; HeapHandle
0x18004eddc  call    cs:__imp_RtlFreeHeap
0x18004ede2  test    rsi, rsi
0x18004ede5  jz      short loc_18004EDFF
0x18004ede7  mov     rcx, gs:60h
0x18004edf0  mov     r8, rsi; P
0x18004edf3  xor     edx, edx; Flags
0x18004edf5  mov     rcx, [rcx+30h]; HeapHandle
0x18004edf9  call    cs:__imp_RtlFreeHeap
0x18004edff  mov     eax, 57h ; 'W'
0x18004ee04  mov     rbx, [rsp+38h+arg_8]
0x18004ee09  mov     rbp, [rsp+38h+arg_18]
0x18004ee0e  add     rsp, 20h
0x18004ee12  pop     r14
0x18004ee14  pop     rdi
0x18004ee15  pop     rsi
0x18004ee16  retn
0x18004ee17  xor     ebx, ebx
0x18004ee19  lea     r8, [rsp+38h+nSize]; nSize
0x18004ee1e  xor     edx, edx; lpBuffer
0x18004ee20  lea     ecx, [rbx+4]; NameType
0x18004ee23  call    cs:__imp_GetComputerNameExW
0x18004ee29  test    eax, eax
0x18004ee2b  jnz     loc_18004EEB8
0x18004ee31  mov     ebx, gs:68h
0x18004ee39  cmp     ebx, 0EAh
0x18004ee3f  jnz     short loc_18004EEB8
0x18004ee41  call    cs:__imp_KernelBaseGetGlobalData
0x18004ee47  mov     rcx, gs:60h
0x18004ee50  mov     r8d, [rsp+38h+nSize]
0x18004ee55  add     r8, r8; Size
0x18004ee58  mov     edx, [rax]; Flags
0x18004ee5a  mov     rcx, [rcx+30h]; HeapHandle
0x18004ee5e  call    cs:__imp_RtlAllocateHeap
0x18004ee64  mov     rdi, rax
0x18004ee67  test    rax, rax
0x18004ee6a  jnz     short loc_18004EE71
0x18004ee6c  lea     ebx, [rax+8]
0x18004ee6f  jmp     short loc_18004EEB8
0x18004ee71  lea     r8, [rsp+38h+nSize]; nSize
0x18004ee76  mov     rdx, rdi; lpBuffer
0x18004ee79  mov     ecx, 4; NameType
0x18004ee7e  call    cs:__imp_GetComputerNameExW
0x18004ee84  test    eax, eax
0x18004ee86  jz      short loc_18004EE94
0x18004ee88  mov     rcx, rdi; Buf2
0x18004ee8b  call    BaseSetAltNetBiosName
0x18004ee90  test    eax, eax
0x18004ee92  jnz     short loc_18004EE9E
0x18004ee94  mov     ebx, gs:68h
0x18004ee9c  jmp     short loc_18004EEA0
0x18004ee9e  xor     ebx, ebx
0x18004eea0  mov     rcx, gs:60h
0x18004eea9  mov     r8, rdi; P
0x18004eeac  xor     edx, edx; Flags
0x18004eeae  mov     rcx, [rcx+30h]; HeapHandle
0x18004eeb2  call    cs:__imp_RtlFreeHeap
0x18004eeb8  mov     ecx, 4
0x18004eebd  call    BasepGetNameNonVolatile
0x18004eec2  mov     rdi, rax
0x18004eec5  test    rax, rax
0x18004eec8  jz      short loc_18004EEFA
0x18004eeca  mov     rcx, rax; Buf2
0x18004eecd  call    BaseSetAltNetBiosName
0x18004eed2  test    eax, eax
0x18004eed4  jnz     short loc_18004EEE0
0x18004eed6  mov     ebx, gs:68h
0x18004eede  jmp     short loc_18004EEE2
0x18004eee0  xor     ebx, ebx
0x18004eee2  mov     rcx, gs:60h
0x18004eeeb  mov     r8, rdi; P
0x18004eeee  xor     edx, edx; Flags
0x18004eef0  mov     rcx, [rcx+30h]; HeapHandle
0x18004eef4  call    cs:__imp_RtlFreeHeap
0x18004eefa  test    ebx, ebx
0x18004eefc  jnz     loc_18004F03A
0x18004ef02  lea     r8, [rsp+38h+arg_10]; nSize
0x18004ef07  xor     edx, edx; lpBuffer
0x18004ef09  lea     ecx, [rbx+7]; NameType
0x18004ef0c  call    cs:__imp_GetComputerNameExW
0x18004ef12  test    eax, eax
0x18004ef14  jnz     loc_18004EFAC
0x18004ef1a  mov     ebx, gs:68h
0x18004ef22  cmp     ebx, 0EAh
0x18004ef28  jnz     short loc_18004EFA4
0x18004ef2a  call    cs:__imp_KernelBaseGetGlobalData
0x18004ef30  mov     rcx, gs:60h
0x18004ef39  mov     r8d, [rsp+38h+arg_10]
0x18004ef3e  add     r8, r8; Size
0x18004ef41  mov     edx, [rax]; Flags
0x18004ef43  mov     rcx, [rcx+30h]; HeapHandle
0x18004ef47  call    cs:__imp_RtlAllocateHeap
0x18004ef4d  mov     rdi, rax
0x18004ef50  test    rax, rax
0x18004ef53  jnz     short loc_18004EF5D
0x18004ef55  lea     ebx, [rax+8]
0x18004ef58  jmp     loc_18004F03A
0x18004ef5d  lea     r8, [rsp+38h+arg_10]; nSize
0x18004ef62  mov     rdx, rdi; lpBuffer
0x18004ef65  mov     ecx, 7; NameType
0x18004ef6a  call    cs:__imp_GetComputerNameExW
0x18004ef70  test    eax, eax
0x18004ef72  jz      short loc_18004EF80
0x18004ef74  mov     rcx, rdi; Buf2
0x18004ef77  call    BaseSetAltDnsFQHostname
0x18004ef7c  test    eax, eax
0x18004ef7e  jnz     short loc_18004EF8A
0x18004ef80  mov     ebx, gs:68h
0x18004ef88  jmp     short loc_18004EF8C
0x18004ef8a  xor     ebx, ebx
0x18004ef8c  mov     rcx, gs:60h
0x18004ef95  mov     r8, rdi; P
0x18004ef98  xor     edx, edx; Flags
0x18004ef9a  mov     rcx, [rcx+30h]; HeapHandle
0x18004ef9e  call    cs:__imp_RtlFreeHeap
0x18004efa4  test    ebx, ebx
0x18004efa6  jnz     loc_18004F03A
0x18004efac  mov     ecx, 7
0x18004efb1  call    BasepGetNameNonVolatile
0x18004efb6  mov     rdi, rax
0x18004efb9  test    rax, rax
0x18004efbc  jz      short loc_18004EFF2
0x18004efbe  mov     rcx, rax; Buf2
0x18004efc1  call    BaseSetAltDnsFQHostname
0x18004efc6  test    eax, eax
0x18004efc8  jnz     short loc_18004EFD4
0x18004efca  mov     ebx, gs:68h
0x18004efd2  jmp     short loc_18004EFD6
0x18004efd4  xor     ebx, ebx
0x18004efd6  mov     rcx, gs:60h
0x18004efdf  mov     r8, rdi; P
0x18004efe2  xor     edx, edx; Flags
0x18004efe4  mov     rcx, [rcx+30h]; HeapHandle
0x18004efe8  call    cs:__imp_RtlFreeHeap
0x18004efee  test    ebx, ebx
0x18004eff0  jnz     short loc_18004F03A
0x18004eff2  mov     rdx, rbp; lpBuffer
0x18004eff5  mov     ecx, 5; NameType
0x18004effa  call    cs:__imp_SetComputerNameExW
0x18004f000  test    eax, eax
0x18004f002  jnz     short loc_18004F010
0x18004f004  mov     ebx, gs:68h
0x18004f00c  test    ebx, ebx
0x18004f00e  jnz     short loc_18004F03A
0x18004f010  mov     rdx, rsi; lpBuffer
0x18004f013  mov     ecx, 6; NameType
0x18004f018  call    cs:__imp_SetComputerNameExW
0x18004f01e  test    eax, eax
0x18004f020  jnz     short loc_18004F02E
0x18004f022  mov     ebx, gs:68h
0x18004f02a  test    ebx, ebx
0x18004f02c  jnz     short loc_18004F03A
0x18004f02e  xor     edx, edx
0x18004f030  mov     rcx, r14; Buf2
0x18004f033  call    RemoveLocalAlternateComputerNameW
0x18004f038  mov     ebx, eax
0x18004f03a  test    rbp, rbp
0x18004f03d  jz      short loc_18004F057
0x18004f03f  mov     rcx, gs:60h
0x18004f048  mov     r8, rbp; P
0x18004f04b  xor     edx, edx; Flags
0x18004f04d  mov     rcx, [rcx+30h]; HeapHandle
0x18004f051  call    cs:__imp_RtlFreeHeap
0x18004f057  test    rsi, rsi
0x18004f05a  jz      short loc_18004F074
0x18004f05c  mov     rcx, gs:60h
0x18004f065  mov     r8, rsi; P
0x18004f068  xor     edx, edx; Flags
0x18004f06a  mov     rcx, [rcx+30h]; HeapHandle
0x18004f06e  call    cs:__imp_RtlFreeHeap
0x18004f074  mov     eax, ebx
0x18004f076  jmp     loc_18004EE04
```
