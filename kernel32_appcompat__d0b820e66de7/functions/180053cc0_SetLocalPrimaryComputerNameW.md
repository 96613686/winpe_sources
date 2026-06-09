# SetLocalPrimaryComputerNameW

- ea: `0x180053cc0`
- end: `0x180054040`
- name: `SetLocalPrimaryComputerNameW`
- size: `896`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006fed0`

## callees

- `0x18004b35c`
- `0x180053cc0`
- `0x180054048`
- `0x180054128`
- `0x18006f8b0`
- `0x18006f8ec`
- `0x18006fd70`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180053d2c`
- `ntdll!RtlFreeHeap` at `0x180053d4f`
- `ntdll!RtlFreeHeap` at `0x180053e2b`
- `ntdll!RtlFreeHeap` at `0x180053e73`
- `ntdll!RtlFreeHeap` at `0x180053f3f`
- `ntdll!RtlFreeHeap` at `0x180053f8f`
- `ntdll!RtlFreeHeap` at `0x18005400a`
- `ntdll!RtlFreeHeap` at `0x18005402d`
- `ntdll!RtlFreeHeap` at `0x180053d2c`
- `ntdll!RtlFreeHeap` at `0x180053d4f`
- `ntdll!RtlFreeHeap` at `0x180053e2b`
- `ntdll!RtlFreeHeap` at `0x180053e73`
- `ntdll!RtlFreeHeap` at `0x180053f3f`
- `ntdll!RtlFreeHeap` at `0x180053f8f`
- `ntdll!RtlFreeHeap` at `0x18005400a`
- `ntdll!RtlFreeHeap` at `0x18005402d`
- `ntdll!RtlAllocateHeap` at `0x180053dcb`
- `ntdll!RtlAllocateHeap` at `0x180053edc`
- `ntdll!RtlAllocateHeap` at `0x180053dcb`
- `ntdll!RtlAllocateHeap` at `0x180053edc`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180053da8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180053eb9`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180053da8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180053eb9`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180053fa7`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180053fcb`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180053fa7`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180053fcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053d80`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053df1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053e91`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053f05`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053d80`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053df1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053e91`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180053f05`

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
0x180053cc0  mov     rax, rsp
0x180053cc3  mov     [rax+10h], rbx
0x180053cc7  mov     [rax+20h], rbp
0x180053ccb  push    rsi
0x180053ccc  push    rdi
0x180053ccd  push    r14
0x180053ccf  sub     rsp, 20h
0x180053cd3  mov     ebx, edx
0x180053cd5  mov     dword ptr [rax+8], 0
0x180053cdc  xor     edx, edx
0x180053cde  mov     dword ptr [rax+18h], 0
0x180053ce5  mov     r14, rcx
0x180053ce8  call    BaseParseDnsName
0x180053ced  mov     edx, 1
0x180053cf2  mov     rcx, r14; String
0x180053cf5  mov     rbp, rax
0x180053cf8  call    BaseParseDnsName
0x180053cfd  mov     rsi, rax
0x180053d00  test    r14, r14
0x180053d03  jz      short loc_180053D5B
0x180053d05  test    ebx, ebx
0x180053d07  jnz     short loc_180053D5B
0x180053d09  mov     rcx, r14; Buf2
0x180053d0c  call    BaseIsAltDnsFQHostname
0x180053d11  test    eax, eax
0x180053d13  jnz     short loc_180053D74
0x180053d15  test    rbp, rbp
0x180053d18  jz      short loc_180053D38
0x180053d1a  mov     rcx, gs:60h
0x180053d23  mov     r8, rbp; P
0x180053d26  xor     edx, edx; Flags
0x180053d28  mov     rcx, [rcx+30h]; HeapHandle
0x180053d2c  call    cs:__imp_RtlFreeHeap
0x180053d33  nop     dword ptr [rax+rax+00h]
0x180053d38  test    rsi, rsi
0x180053d3b  jz      short loc_180053D5B
0x180053d3d  mov     rcx, gs:60h
0x180053d46  mov     r8, rsi; P
0x180053d49  xor     edx, edx; Flags
0x180053d4b  mov     rcx, [rcx+30h]; HeapHandle
0x180053d4f  call    cs:__imp_RtlFreeHeap
0x180053d56  nop     dword ptr [rax+rax+00h]
0x180053d5b  mov     eax, 57h ; 'W'
0x180053d60  mov     rbx, [rsp+38h+arg_8]
0x180053d65  mov     rbp, [rsp+38h+arg_18]
0x180053d6a  add     rsp, 20h
0x180053d6e  pop     r14
0x180053d70  pop     rdi
0x180053d71  pop     rsi
0x180053d72  retn
0x180053d74  xor     ebx, ebx
0x180053d76  lea     r8, [rsp+38h+nSize]; nSize
0x180053d7b  xor     edx, edx; lpBuffer
0x180053d7d  lea     ecx, [rbx+4]; NameType
0x180053d80  call    cs:__imp_GetComputerNameExW
0x180053d87  nop     dword ptr [rax+rax+00h]
0x180053d8c  test    eax, eax
0x180053d8e  jnz     loc_180053E37
0x180053d94  mov     ebx, gs:68h
0x180053d9c  cmp     ebx, 0EAh
0x180053da2  jnz     loc_180053E37
0x180053da8  call    cs:__imp_KernelBaseGetGlobalData
0x180053daf  nop     dword ptr [rax+rax+00h]
0x180053db4  mov     rcx, gs:60h
0x180053dbd  mov     r8d, [rsp+38h+nSize]
0x180053dc2  add     r8, r8; Size
0x180053dc5  mov     edx, [rax]; Flags
0x180053dc7  mov     rcx, [rcx+30h]; HeapHandle
0x180053dcb  call    cs:__imp_RtlAllocateHeap
0x180053dd2  nop     dword ptr [rax+rax+00h]
0x180053dd7  mov     rdi, rax
0x180053dda  test    rax, rax
0x180053ddd  jnz     short loc_180053DE4
0x180053ddf  lea     ebx, [rax+8]
0x180053de2  jmp     short loc_180053E37
0x180053de4  lea     r8, [rsp+38h+nSize]; nSize
0x180053de9  mov     rdx, rdi; lpBuffer
0x180053dec  mov     ecx, 4; NameType
0x180053df1  call    cs:__imp_GetComputerNameExW
0x180053df8  nop     dword ptr [rax+rax+00h]
0x180053dfd  test    eax, eax
0x180053dff  jz      short loc_180053E0D
0x180053e01  mov     rcx, rdi; Buf2
0x180053e04  call    BaseSetAltNetBiosName
0x180053e09  test    eax, eax
0x180053e0b  jnz     short loc_180053E17
0x180053e0d  mov     ebx, gs:68h
0x180053e15  jmp     short loc_180053E19
0x180053e17  xor     ebx, ebx
0x180053e19  mov     rcx, gs:60h
0x180053e22  mov     r8, rdi; P
0x180053e25  xor     edx, edx; Flags
0x180053e27  mov     rcx, [rcx+30h]; HeapHandle
0x180053e2b  call    cs:__imp_RtlFreeHeap
0x180053e32  nop     dword ptr [rax+rax+00h]
0x180053e37  mov     ecx, 4
0x180053e3c  call    BasepGetNameNonVolatile
0x180053e41  mov     rdi, rax
0x180053e44  test    rax, rax
0x180053e47  jz      short loc_180053E7F
0x180053e49  mov     rcx, rax; Buf2
0x180053e4c  call    BaseSetAltNetBiosName
0x180053e51  test    eax, eax
0x180053e53  jnz     short loc_180053E5F
0x180053e55  mov     ebx, gs:68h
0x180053e5d  jmp     short loc_180053E61
0x180053e5f  xor     ebx, ebx
0x180053e61  mov     rcx, gs:60h
0x180053e6a  mov     r8, rdi; P
0x180053e6d  xor     edx, edx; Flags
0x180053e6f  mov     rcx, [rcx+30h]; HeapHandle
0x180053e73  call    cs:__imp_RtlFreeHeap
0x180053e7a  nop     dword ptr [rax+rax+00h]
0x180053e7f  test    ebx, ebx
0x180053e81  jnz     loc_180053FF3
0x180053e87  lea     r8, [rsp+38h+arg_10]; nSize
0x180053e8c  xor     edx, edx; lpBuffer
0x180053e8e  lea     ecx, [rbx+7]; NameType
0x180053e91  call    cs:__imp_GetComputerNameExW
0x180053e98  nop     dword ptr [rax+rax+00h]
0x180053e9d  test    eax, eax
0x180053e9f  jnz     loc_180053F53
0x180053ea5  mov     ebx, gs:68h
0x180053ead  cmp     ebx, 0EAh
0x180053eb3  jnz     loc_180053F4B
0x180053eb9  call    cs:__imp_KernelBaseGetGlobalData
0x180053ec0  nop     dword ptr [rax+rax+00h]
0x180053ec5  mov     rcx, gs:60h
0x180053ece  mov     r8d, [rsp+38h+arg_10]
0x180053ed3  add     r8, r8; Size
0x180053ed6  mov     edx, [rax]; Flags
0x180053ed8  mov     rcx, [rcx+30h]; HeapHandle
0x180053edc  call    cs:__imp_RtlAllocateHeap
0x180053ee3  nop     dword ptr [rax+rax+00h]
0x180053ee8  mov     rdi, rax
0x180053eeb  test    rax, rax
0x180053eee  jnz     short loc_180053EF8
0x180053ef0  lea     ebx, [rax+8]
0x180053ef3  jmp     loc_180053FF3
0x180053ef8  lea     r8, [rsp+38h+arg_10]; nSize
0x180053efd  mov     rdx, rdi; lpBuffer
0x180053f00  mov     ecx, 7; NameType
0x180053f05  call    cs:__imp_GetComputerNameExW
0x180053f0c  nop     dword ptr [rax+rax+00h]
0x180053f11  test    eax, eax
0x180053f13  jz      short loc_180053F21
0x180053f15  mov     rcx, rdi; Buf2
0x180053f18  call    BaseSetAltDnsFQHostname
0x180053f1d  test    eax, eax
0x180053f1f  jnz     short loc_180053F2B
0x180053f21  mov     ebx, gs:68h
0x180053f29  jmp     short loc_180053F2D
0x180053f2b  xor     ebx, ebx
0x180053f2d  mov     rcx, gs:60h
0x180053f36  mov     r8, rdi; P
0x180053f39  xor     edx, edx; Flags
0x180053f3b  mov     rcx, [rcx+30h]; HeapHandle
0x180053f3f  call    cs:__imp_RtlFreeHeap
0x180053f46  nop     dword ptr [rax+rax+00h]
0x180053f4b  test    ebx, ebx
0x180053f4d  jnz     loc_180053FF3
0x180053f53  mov     ecx, 7
0x180053f58  call    BasepGetNameNonVolatile
0x180053f5d  mov     rdi, rax
0x180053f60  test    rax, rax
0x180053f63  jz      short loc_180053F9F
0x180053f65  mov     rcx, rax; Buf2
0x180053f68  call    BaseSetAltDnsFQHostname
0x180053f6d  test    eax, eax
0x180053f6f  jnz     short loc_180053F7B
0x180053f71  mov     ebx, gs:68h
0x180053f79  jmp     short loc_180053F7D
0x180053f7b  xor     ebx, ebx
0x180053f7d  mov     rcx, gs:60h
0x180053f86  mov     r8, rdi; P
0x180053f89  xor     edx, edx; Flags
0x180053f8b  mov     rcx, [rcx+30h]; HeapHandle
0x180053f8f  call    cs:__imp_RtlFreeHeap
0x180053f96  nop     dword ptr [rax+rax+00h]
0x180053f9b  test    ebx, ebx
0x180053f9d  jnz     short loc_180053FF3
0x180053f9f  mov     rdx, rbp; lpBuffer
0x180053fa2  mov     ecx, 5; NameType
0x180053fa7  call    cs:__imp_SetComputerNameExW
0x180053fae  nop     dword ptr [rax+rax+00h]
0x180053fb3  test    eax, eax
0x180053fb5  jnz     short loc_180053FC3
0x180053fb7  mov     ebx, gs:68h
0x180053fbf  test    ebx, ebx
0x180053fc1  jnz     short loc_180053FF3
0x180053fc3  mov     rdx, rsi; lpBuffer
0x180053fc6  mov     ecx, 6; NameType
0x180053fcb  call    cs:__imp_SetComputerNameExW
0x180053fd2  nop     dword ptr [rax+rax+00h]
0x180053fd7  test    eax, eax
0x180053fd9  jnz     short loc_180053FE7
0x180053fdb  mov     ebx, gs:68h
0x180053fe3  test    ebx, ebx
0x180053fe5  jnz     short loc_180053FF3
0x180053fe7  xor     edx, edx
0x180053fe9  mov     rcx, r14; Buf2
0x180053fec  call    RemoveLocalAlternateComputerNameW
0x180053ff1  mov     ebx, eax
0x180053ff3  test    rbp, rbp
0x180053ff6  jz      short loc_180054016
0x180053ff8  mov     rcx, gs:60h
0x180054001  mov     r8, rbp; P
0x180054004  xor     edx, edx; Flags
0x180054006  mov     rcx, [rcx+30h]; HeapHandle
0x18005400a  call    cs:__imp_RtlFreeHeap
0x180054011  nop     dword ptr [rax+rax+00h]
0x180054016  test    rsi, rsi
0x180054019  jz      short loc_180054039
0x18005401b  mov     rcx, gs:60h
0x180054024  mov     r8, rsi; P
0x180054027  xor     edx, edx; Flags
0x180054029  mov     rcx, [rcx+30h]; HeapHandle
0x18005402d  call    cs:__imp_RtlFreeHeap
0x180054034  nop     dword ptr [rax+rax+00h]
0x180054039  mov     eax, ebx
0x18005403b  jmp     loc_180053D60
```
