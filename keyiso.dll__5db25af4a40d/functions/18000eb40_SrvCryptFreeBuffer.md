# SrvCryptFreeBuffer

- ea: `0x18000eb40`
- end: `0x18000eba4`
- name: `SrvCryptFreeBuffer`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000a1dc`
- `0x18000eb40`
- `0x18001136c`

## string_xrefs

- `0x18000eb62`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptFreeBuffer(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rax

  if ( a1 )
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)SrvLookupMemoryBufferFromList(a1, a2, 1);
    if ( v5 )
    {
      SrvRundownMemoryBuffer(v5);
      return 0;
    }
    v2 = -2146893785;
    v3 = 1817;
    v4 = 2148073511LL;
  }
  else
  {
    v2 = -2146893786;
    v3 = 1793;
    v4 = 2148073510LL;
  }
  DebugTraceError(v4, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v3);
  return v2;
}

```

## disassembly

```asm
0x18000eb40  push    rbx
0x18000eb42  sub     rsp, 20h
0x18000eb46  test    rcx, rcx
0x18000eb49  jnz     short loc_18000EB70
0x18000eb4b  mov     ebx, 80090026h
0x18000eb50  mov     r9d, 701h
0x18000eb56  mov     ecx, 80090026h
0x18000eb5b  lea     rdx, aStatus; "Status"
0x18000eb62  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eb69  call    DebugTraceError
0x18000eb6e  jmp     short loc_18000EB9C
0x18000eb70  mov     r8d, 1
0x18000eb76  call    SrvLookupMemoryBufferFromList
0x18000eb7b  test    rax, rax
0x18000eb7e  jnz     short loc_18000EB92
0x18000eb80  mov     ebx, 80090027h
0x18000eb85  mov     r9d, 719h
0x18000eb8b  mov     ecx, 80090027h
0x18000eb90  jmp     short loc_18000EB5B
0x18000eb92  mov     rcx, rax; CriticalSection
0x18000eb95  call    SrvRundownMemoryBuffer
0x18000eb9a  xor     ebx, ebx
0x18000eb9c  mov     eax, ebx
0x18000eb9e  add     rsp, 20h
0x18000eba2  pop     rbx
0x18000eba3  retn
```
