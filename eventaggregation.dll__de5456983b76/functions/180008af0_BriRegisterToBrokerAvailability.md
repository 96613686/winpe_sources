# BriRegisterToBrokerAvailability

- ea: `0x180008af0`
- end: `0x180008c1e`
- name: `BriRegisterToBrokerAvailability`
- size: `302`
- prototype: `__int64 __usercall@<rax>(void *Source1@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002910`
- `0x180003070`
- `0x180004480`
- `0x180008af0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008bf3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008bf3`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008b49`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008b49`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008c02`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008c02`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180008b2f`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180008b2f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180008bd5`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180008bd5`

## pseudocode

```c
__int64 __fastcall BriRegisterToBrokerAvailability(UCHAR *Source1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v9; // rdx
  int v10; // ebx
  char v11; // si
  __int64 BindingContextByBrokerId; // rbx

  if ( !Source1 || !a3 )
    return (unsigned int)-1073741811;
  v10 = RtlRunOnceExecuteOnce(&BrokerInternalClientInitOnce, BrpInitOnceRunOnceCallback, 0, 0);
  if ( v10 >= 0 )
  {
    v11 = 0;
    RtlAcquireSRWLockShared(&BrokerBindingTableLock, v9);
    BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
    if ( BindingContextByBrokerId )
      goto LABEL_21;
    if ( !EaLibConvertLockSharedToExclusive() )
      BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
    v11 = 1;
    if ( BindingContextByBrokerId || (BindingContextByBrokerId = BripCreateBindingContext((const GUID *)Source1)) != 0 )
    {
LABEL_21:
      if ( *(_DWORD *)(BindingContextByBrokerId + 56) || *(_DWORD *)(BindingContextByBrokerId + 60) )
        v10 = RtlSubscribeWnfStateChangeNotification(
                a5,
                *(_QWORD *)(BindingContextByBrokerId + 56),
                a2,
                a3,
                a4,
                0,
                0,
                0);
      else
        v10 = -1073741637;
      if ( !v11 )
      {
        RtlReleaseSRWLockShared(&BrokerBindingTableLock);
        return (unsigned int)v10;
      }
    }
    else
    {
      v10 = -1073741275;
    }
    dword_180012198 = 0;
    RtlReleaseSRWLockExclusive(&BrokerBindingTableLock);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008af0  push    rbx
0x180008af2  push    rbp
0x180008af3  push    rsi
0x180008af4  push    rdi
0x180008af5  push    r14
0x180008af7  push    r15
0x180008af9  sub     rsp, 48h
0x180008afd  mov     r14, r9
0x180008b00  mov     rbp, r8
0x180008b03  mov     r15d, edx
0x180008b06  mov     rdi, rcx
0x180008b09  test    rcx, rcx
0x180008b0c  jz      loc_180008C0A
0x180008b12  test    r8, r8
0x180008b15  jz      loc_180008C0A
0x180008b1b  xor     r9d, r9d
0x180008b1e  lea     rdx, BrpInitOnceRunOnceCallback
0x180008b25  xor     r8d, r8d
0x180008b28  lea     rcx, BrokerInternalClientInitOnce
0x180008b2f  call    cs:__imp_RtlRunOnceExecuteOnce
0x180008b35  mov     ebx, eax
0x180008b37  test    eax, eax
0x180008b39  js      loc_180008C0F
0x180008b3f  lea     rcx, BrokerBindingTableLock
0x180008b46  xor     sil, sil
0x180008b49  call    cs:__imp_RtlAcquireSRWLockShared
0x180008b4f  mov     rcx, rdi; Source1
0x180008b52  call    BripFindBindingContextByBrokerId
0x180008b57  mov     rbx, rax
0x180008b5a  test    rax, rax
0x180008b5d  jnz     short loc_180008B92
0x180008b5f  call    EaLibConvertLockSharedToExclusive
0x180008b64  test    al, al
0x180008b66  jnz     short loc_180008B73
0x180008b68  mov     rcx, rdi; Source1
0x180008b6b  call    BripFindBindingContextByBrokerId
0x180008b70  mov     rbx, rax
0x180008b73  mov     sil, 1
0x180008b76  test    rbx, rbx
0x180008b79  jnz     short loc_180008B92
0x180008b7b  mov     rcx, rdi
0x180008b7e  call    BripCreateBindingContext
0x180008b83  mov     rbx, rax
0x180008b86  test    rax, rax
0x180008b89  jnz     short loc_180008B92
0x180008b8b  mov     ebx, 0C0000225h
0x180008b90  jmp     short loc_180008BE2
0x180008b92  cmp     dword ptr [rbx+38h], 0
0x180008b96  jnz     short loc_180008BA5
0x180008b98  cmp     dword ptr [rbx+3Ch], 0
0x180008b9c  jnz     short loc_180008BA5
0x180008b9e  mov     ebx, 0C00000BBh
0x180008ba3  jmp     short loc_180008BDD
0x180008ba5  mov     rdx, [rbx+38h]
0x180008ba9  mov     r9, rbp
0x180008bac  mov     rcx, [rsp+78h+arg_20]
0x180008bb4  mov     r8d, r15d
0x180008bb7  mov     [rsp+78h+var_40], 0
0x180008bbf  mov     [rsp+78h+var_48], 0
0x180008bc7  mov     [rsp+78h+var_50], 0
0x180008bd0  mov     [rsp+78h+var_58], r14
0x180008bd5  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180008bdb  mov     ebx, eax
0x180008bdd  test    sil, sil
0x180008be0  jz      short loc_180008BFB
0x180008be2  lea     rcx, BrokerBindingTableLock
0x180008be9  mov     cs:dword_180012198, 0
0x180008bf3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008bf9  jmp     short loc_180008C0F
0x180008bfb  lea     rcx, BrokerBindingTableLock
0x180008c02  call    cs:__imp_RtlReleaseSRWLockShared
0x180008c08  jmp     short loc_180008C0F
0x180008c0a  mov     ebx, 0C000000Dh
0x180008c0f  mov     eax, ebx
0x180008c11  add     rsp, 48h
0x180008c15  pop     r15
0x180008c17  pop     r14
0x180008c19  pop     rdi
0x180008c1a  pop     rsi
0x180008c1b  pop     rbp
0x180008c1c  pop     rbx
0x180008c1d  retn
```
