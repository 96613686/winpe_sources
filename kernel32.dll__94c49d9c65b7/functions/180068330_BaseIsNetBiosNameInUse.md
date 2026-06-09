# BaseIsNetBiosNameInUse

- ea: `0x180068330`
- end: `0x180068534`
- name: `BaseIsNetBiosNameInUse`
- size: `516`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180068c30`

## callees

- `0x1800378d4`
- `0x18003dfb0`
- `0x180068330`
- `0x18006896c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180068385`
- `ntdll!RtlNtStatusToDosError` at `0x1800683f6`
- `ntdll!RtlNtStatusToDosError` at `0x180068385`
- `ntdll!RtlNtStatusToDosError` at `0x1800683f6`
- `ntdll!RtlSetLastWin32Error` at `0x1800683bf`
- `ntdll!RtlSetLastWin32Error` at `0x1800683bf`
- `ntdll!RtlFreeHeap` at `0x1800684f7`
- `ntdll!RtlFreeHeap` at `0x180068514`
- `ntdll!RtlFreeHeap` at `0x1800684f7`
- `ntdll!RtlFreeHeap` at `0x180068514`
- `ntdll!RtlAllocateHeap` at `0x1800683ae`
- `ntdll!RtlAllocateHeap` at `0x180068480`
- `ntdll!RtlAllocateHeap` at `0x1800683ae`
- `ntdll!RtlAllocateHeap` at `0x180068480`
- `ntdll!_wcsicmp` at `0x1800684b4`
- `ntdll!_wcsicmp` at `0x1800684b4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180068392`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180068467`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180068392`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180068467`

## string_xrefs

- `0x180068372`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x1800683e1`: `\Registry\Machine\System\CurrentControlSet\Services\DnsCache\Parameters`
- `0x180068367`: `AlternateComputerNames`
- `0x1800683d5`: `AlternateComputerNames`
- `0x180068355`: `Dnscache`
- `0x1800683e8`: `Dnscache`

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
0x180068330  mov     [rsp-38h+arg_0], rbx
0x180068335  push    rbp
0x180068336  push    rsi
0x180068337  push    rdi
0x180068338  push    r12
0x18006833a  push    r13
0x18006833c  push    r14
0x18006833e  push    r15
0x180068340  mov     rbp, rsp
0x180068343  sub     rsp, 40h
0x180068347  xor     r14d, r14d
0x18006834a  lea     rax, [rbp+arg_10]
0x18006834e  mov     r13, rcx
0x180068351  mov     [rbp+arg_10], r14d
0x180068355  lea     rcx, aDnscache; "Dnscache"
0x18006835c  mov     [rbp+Hostname], r14
0x180068360  xor     r9d, r9d
0x180068363  mov     [rbp+arg_18], r14d
0x180068367  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x18006836e  mov     [rbp+nSize], r14d
0x180068372  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x180068379  mov     [rsp+40h+var_20], rax
0x18006837e  call    BasepGetNameFromReg
0x180068383  mov     ecx, eax; Status
0x180068385  call    cs:__imp_RtlNtStatusToDosError
0x18006838b  cmp     eax, 0EAh
0x180068390  jnz     short loc_1800683FC
0x180068392  call    cs:__imp_KernelBaseGetGlobalData
0x180068398  mov     rcx, gs:60h
0x1800683a1  mov     r8d, [rbp+arg_10]
0x1800683a5  add     r8, r8; Size
0x1800683a8  mov     edx, [rax]; Flags
0x1800683aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800683ae  call    cs:__imp_RtlAllocateHeap
0x1800683b4  mov     r14, rax
0x1800683b7  test    rax, rax
0x1800683ba  jnz     short loc_1800683CE
0x1800683bc  lea     ecx, [rax+8]; LastError
0x1800683bf  call    cs:__imp_RtlSetLastWin32Error
0x1800683c5  lea     eax, [r14+1]
0x1800683c9  jmp     loc_18006851C
0x1800683ce  lea     rax, [rbp+arg_10]
0x1800683d2  mov     r9, r14
0x1800683d5  lea     r8, aAlternatecompu; "AlternateComputerNames"
0x1800683dc  mov     [rsp+40h+var_20], rax
0x1800683e1  lea     rdx, aRegistryMachin_24; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800683e8  lea     rcx, aDnscache; "Dnscache"
0x1800683ef  call    BasepGetNameFromReg
0x1800683f4  mov     ecx, eax; Status
0x1800683f6  call    cs:__imp_RtlNtStatusToDosError
0x1800683fc  test    eax, eax
0x1800683fe  jnz     short loc_180068409
0x180068400  test    r14, r14
0x180068403  jz      loc_18006851C
0x180068409  xor     esi, esi
0x18006840b  lea     edi, [rsi+1]
0x18006840e  test    eax, eax
0x180068410  jnz     loc_1800684E0
0x180068416  xor     r15d, r15d
0x180068419  xor     r12d, r12d
0x18006841c  lea     r9, [rbp+arg_18]
0x180068420  mov     edx, r12d
0x180068423  lea     r8, [rbp+Hostname]
0x180068427  mov     rcx, r14; String
0x18006842a  call    BasepGetMultiValueAddr
0x18006842f  mov     ebx, eax
0x180068431  test    eax, eax
0x180068433  jnz     loc_1800684C0
0x180068439  mov     rcx, [rbp+Hostname]; Hostname
0x18006843d  lea     r8, [rbp+nSize]; nSize
0x180068441  mov     rdx, rsi; ComputerName
0x180068444  call    DnsHostnameToComputerNameW
0x180068449  test    eax, eax
0x18006844b  jnz     short loc_1800684AE
0x18006844d  mov     ebx, gs:68h
0x180068455  cmp     ebx, 0EAh
0x18006845b  jnz     short loc_1800684AA
0x18006845d  mov     eax, [rbp+nSize]
0x180068460  add     eax, edi
0x180068462  mov     [rbp+nSize], eax
0x180068465  mov     ebx, eax
0x180068467  call    cs:__imp_KernelBaseGetGlobalData
0x18006846d  mov     rcx, gs:60h
0x180068476  lea     r8, [rbx+rbx]; Size
0x18006847a  mov     edx, [rax]; Flags
0x18006847c  mov     rcx, [rcx+30h]; HeapHandle
0x180068480  call    cs:__imp_RtlAllocateHeap
0x180068486  mov     rsi, rax
0x180068489  test    rax, rax
0x18006848c  jz      short loc_1800684D1
0x18006848e  mov     rcx, [rbp+Hostname]; Hostname
0x180068492  lea     r8, [rbp+nSize]; nSize
0x180068496  mov     rdx, rax; ComputerName
0x180068499  call    DnsHostnameToComputerNameW
0x18006849e  test    eax, eax
0x1800684a0  jnz     short loc_1800684CD
0x1800684a2  mov     ebx, gs:68h
0x1800684aa  test    ebx, ebx
0x1800684ac  jnz     short loc_1800684C0
0x1800684ae  mov     rdx, r13; String2
0x1800684b1  mov     rcx, rsi; String1
0x1800684b4  call    cs:__imp__wcsicmp
0x1800684ba  test    eax, eax
0x1800684bc  cmovz   r15d, edi
0x1800684c0  add     r12d, edi
0x1800684c3  test    ebx, ebx
0x1800684c5  jz      loc_18006841C
0x1800684cb  jmp     short loc_1800684D6
0x1800684cd  xor     ebx, ebx
0x1800684cf  jmp     short loc_1800684AE
0x1800684d1  mov     ebx, 8
0x1800684d6  cmp     ebx, 490h
0x1800684dc  cmovz   edi, r15d
0x1800684e0  test    r14, r14
0x1800684e3  jz      short loc_1800684FD
0x1800684e5  mov     rcx, gs:60h
0x1800684ee  mov     r8, r14; P
0x1800684f1  xor     edx, edx; Flags
0x1800684f3  mov     rcx, [rcx+30h]; HeapHandle
0x1800684f7  call    cs:__imp_RtlFreeHeap
0x1800684fd  test    rsi, rsi
0x180068500  jz      short loc_18006851A
0x180068502  mov     rcx, gs:60h
0x18006850b  mov     r8, rsi; P
0x18006850e  xor     edx, edx; Flags
0x180068510  mov     rcx, [rcx+30h]; HeapHandle
0x180068514  call    cs:__imp_RtlFreeHeap
0x18006851a  mov     eax, edi
0x18006851c  mov     rbx, [rsp+40h+arg_0]
0x180068524  add     rsp, 40h
0x180068528  pop     r15
0x18006852a  pop     r14
0x18006852c  pop     r13
0x18006852e  pop     r12
0x180068530  pop     rdi
0x180068531  pop     rsi
0x180068532  pop     rbp
0x180068533  retn
```
