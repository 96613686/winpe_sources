# BriGetBrokerAvailabilityChangeStamp

- ea: `0x1800089c0`
- end: `0x180008ae8`
- name: `BriGetBrokerAvailabilityChangeStamp`
- size: `296`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002910`
- `0x180003070`
- `0x180004480`
- `0x1800089c0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008ac4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008ac4`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008a20`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008a20`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008ad3`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008ad3`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180008a06`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180008a06`
- `ntdll!NtQueryWnfStateData` at `0x180008a9b`
- `ntdll!NtQueryWnfStateData` at `0x180008a9b`

## pseudocode

```c
__int64 __fastcall BriGetBrokerAvailabilityChangeStamp(UCHAR *Source1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  char v6; // si
  __int64 BindingContextByBrokerId; // rbx
  int v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  v9 = 0;
  if ( Source1 )
  {
    v4 = RtlRunOnceExecuteOnce(&BrokerInternalClientInitOnce, BrpInitOnceRunOnceCallback, 0, 0);
    if ( v4 >= 0 )
    {
      v6 = 0;
      RtlAcquireSRWLockShared(&BrokerBindingTableLock, v5);
      BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
      if ( BindingContextByBrokerId )
        goto LABEL_21;
      if ( !EaLibConvertLockSharedToExclusive() )
        BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
      v6 = 1;
      if ( BindingContextByBrokerId || (BindingContextByBrokerId = BripCreateBindingContext((const GUID *)Source1)) != 0 )
      {
LABEL_21:
        if ( *(_DWORD *)(BindingContextByBrokerId + 56) || *(_DWORD *)(BindingContextByBrokerId + 60) )
        {
          v4 = NtQueryWnfStateData(BindingContextByBrokerId + 56, 0, 0, a2, &v10, &v9);
          if ( v4 == -1073741789 )
            v4 = 0;
        }
        else
        {
          v4 = -1073741637;
        }
        if ( !v6 )
        {
          RtlReleaseSRWLockShared(&BrokerBindingTableLock);
          return (unsigned int)v4;
        }
      }
      else
      {
        v4 = -1073741275;
      }
      dword_180012198 = 0;
      RtlReleaseSRWLockExclusive(&BrokerBindingTableLock);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800089c0  mov     [rsp+arg_8], rbx
0x1800089c5  push    rbp
0x1800089c6  push    rsi
0x1800089c7  push    rdi
0x1800089c8  sub     rsp, 30h
0x1800089cc  mov     [rsp+48h+arg_10], 0
0x1800089d5  mov     rbp, rdx
0x1800089d8  mov     [rsp+48h+arg_0], 0
0x1800089e0  mov     rdi, rcx
0x1800089e3  test    rcx, rcx
0x1800089e6  jnz     short loc_1800089F2
0x1800089e8  mov     ebx, 0C000000Dh
0x1800089ed  jmp     loc_180008AD9
0x1800089f2  xor     r9d, r9d
0x1800089f5  lea     rdx, BrpInitOnceRunOnceCallback
0x1800089fc  xor     r8d, r8d
0x1800089ff  lea     rcx, BrokerInternalClientInitOnce
0x180008a06  call    cs:__imp_RtlRunOnceExecuteOnce
0x180008a0c  mov     ebx, eax
0x180008a0e  test    eax, eax
0x180008a10  js      loc_180008AD9
0x180008a16  lea     rcx, BrokerBindingTableLock
0x180008a1d  xor     sil, sil
0x180008a20  call    cs:__imp_RtlAcquireSRWLockShared
0x180008a26  mov     rcx, rdi; Source1
0x180008a29  call    BripFindBindingContextByBrokerId
0x180008a2e  mov     rbx, rax
0x180008a31  test    rax, rax
0x180008a34  jnz     short loc_180008A69
0x180008a36  call    EaLibConvertLockSharedToExclusive
0x180008a3b  test    al, al
0x180008a3d  jnz     short loc_180008A4A
0x180008a3f  mov     rcx, rdi; Source1
0x180008a42  call    BripFindBindingContextByBrokerId
0x180008a47  mov     rbx, rax
0x180008a4a  mov     sil, 1
0x180008a4d  test    rbx, rbx
0x180008a50  jnz     short loc_180008A69
0x180008a52  mov     rcx, rdi
0x180008a55  call    BripCreateBindingContext
0x180008a5a  mov     rbx, rax
0x180008a5d  test    rax, rax
0x180008a60  jnz     short loc_180008A69
0x180008a62  mov     ebx, 0C0000225h
0x180008a67  jmp     short loc_180008AB3
0x180008a69  lea     rcx, [rbx+38h]
0x180008a6d  cmp     dword ptr [rcx], 0
0x180008a70  jnz     short loc_180008A7F
0x180008a72  cmp     dword ptr [rbx+3Ch], 0
0x180008a76  jnz     short loc_180008A7F
0x180008a78  mov     ebx, 0C00000BBh
0x180008a7d  jmp     short loc_180008AAE
0x180008a7f  lea     rax, [rsp+48h+arg_0]
0x180008a84  mov     r9, rbp
0x180008a87  mov     [rsp+48h+var_20], rax
0x180008a8c  xor     r8d, r8d
0x180008a8f  lea     rax, [rsp+48h+arg_10]
0x180008a94  xor     edx, edx
0x180008a96  mov     [rsp+48h+var_28], rax
0x180008a9b  call    cs:__imp_NtQueryWnfStateData
0x180008aa1  mov     ebx, eax
0x180008aa3  xor     eax, eax
0x180008aa5  cmp     ebx, 0C0000023h
0x180008aab  cmovz   ebx, eax
0x180008aae  test    sil, sil
0x180008ab1  jz      short loc_180008ACC
0x180008ab3  lea     rcx, BrokerBindingTableLock
0x180008aba  mov     cs:dword_180012198, 0
0x180008ac4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008aca  jmp     short loc_180008AD9
0x180008acc  lea     rcx, BrokerBindingTableLock
0x180008ad3  call    cs:__imp_RtlReleaseSRWLockShared
0x180008ad9  mov     eax, ebx
0x180008adb  mov     rbx, [rsp+48h+arg_8]
0x180008ae0  add     rsp, 30h
0x180008ae4  pop     rdi
0x180008ae5  pop     rsi
0x180008ae6  pop     rbp
0x180008ae7  retn
```
