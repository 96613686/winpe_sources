# BriIsBrokerRegistered

- ea: `0x180001c80`
- end: `0x180001d45`
- name: `BriIsBrokerRegistered`
- size: `197`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c80`
- `0x180002910`
- `0x180003070`
- `0x180004480`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001d3d`
- `ntdll!RtlAcquireSRWLockShared` at `0x180001cc1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180001cc1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001ce5`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001ce5`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180001ca3`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180001ca3`

## pseudocode

```c
__int64 __fastcall BriIsBrokerRegistered(UCHAR *Source1)
{
  unsigned __int8 v2; // bl
  __int64 v3; // rdx
  char v4; // si
  __int64 BindingContextByBrokerId; // rbp

  v2 = 0;
  if ( (int)RtlRunOnceExecuteOnce(&BrokerInternalClientInitOnce, BrpInitOnceRunOnceCallback, 0, 0) >= 0 )
  {
    v4 = 0;
    RtlAcquireSRWLockShared(&BrokerBindingTableLock, v3);
    BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
    if ( !BindingContextByBrokerId )
    {
      if ( !EaLibConvertLockSharedToExclusive() )
        BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
      v4 = 1;
      if ( !BindingContextByBrokerId && !BripCreateBindingContext((const GUID *)Source1) )
        goto LABEL_10;
    }
    v2 = 1;
    if ( !v4 )
    {
      RtlReleaseSRWLockShared(&BrokerBindingTableLock);
    }
    else
    {
LABEL_10:
      dword_180012198 = 0;
      RtlReleaseSRWLockExclusive(&BrokerBindingTableLock);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180001c80  mov     [rsp+arg_10], rbx
0x180001c85  push    rdi
0x180001c86  sub     rsp, 20h
0x180001c8a  mov     rdi, rcx
0x180001c8d  lea     rdx, BrpInitOnceRunOnceCallback
0x180001c94  lea     rcx, BrokerInternalClientInitOnce
0x180001c9b  xor     r9d, r9d
0x180001c9e  xor     r8d, r8d
0x180001ca1  xor     bl, bl
0x180001ca3  call    cs:__imp_RtlRunOnceExecuteOnce
0x180001ca9  test    eax, eax
0x180001cab  js      short loc_180001CF5
0x180001cad  mov     [rsp+28h+arg_0], rbp
0x180001cb2  lea     rcx, BrokerBindingTableLock
0x180001cb9  mov     [rsp+28h+arg_8], rsi
0x180001cbe  xor     sil, sil
0x180001cc1  call    cs:__imp_RtlAcquireSRWLockShared
0x180001cc7  mov     rcx, rdi; Source1
0x180001cca  call    BripFindBindingContextByBrokerId
0x180001ccf  mov     rbp, rax
0x180001cd2  test    rax, rax
0x180001cd5  jz      short loc_180001D03
0x180001cd7  mov     bl, 1
0x180001cd9  test    sil, sil
0x180001cdc  jnz     short loc_180001D2C
0x180001cde  lea     rcx, BrokerBindingTableLock
0x180001ce5  call    cs:__imp_RtlReleaseSRWLockShared
0x180001ceb  mov     rbp, [rsp+28h+arg_0]
0x180001cf0  mov     rsi, [rsp+28h+arg_8]
0x180001cf5  movzx   eax, bl
0x180001cf8  mov     rbx, [rsp+28h+arg_10]
0x180001cfd  add     rsp, 20h
0x180001d01  pop     rdi
0x180001d02  retn
0x180001d03  call    EaLibConvertLockSharedToExclusive
0x180001d08  test    al, al
0x180001d0a  jnz     short loc_180001D17
0x180001d0c  mov     rcx, rdi; Source1
0x180001d0f  call    BripFindBindingContextByBrokerId
0x180001d14  mov     rbp, rax
0x180001d17  mov     sil, 1
0x180001d1a  test    rbp, rbp
0x180001d1d  jnz     short loc_180001CD7
0x180001d1f  mov     rcx, rdi
0x180001d22  call    BripCreateBindingContext
0x180001d27  test    rax, rax
0x180001d2a  jnz     short loc_180001CD7
0x180001d2c  lea     rcx, BrokerBindingTableLock
0x180001d33  mov     cs:dword_180012198, 0
0x180001d3d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001d43  jmp     short loc_180001CEB
```
