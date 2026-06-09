# IASSamInitialize

- ea: `0x18002a960`
- end: `0x18002aa08`
- name: `IASSamInitialize`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800291bc`

## callees

- `0x18002a960`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002a9fc`
- `ntdll!RtlNtStatusToDosError` at `0x18002a9fc`
- `SAMLIB!SamOpenDomain` at `0x18002a9a7`
- `SAMLIB!SamOpenDomain` at `0x18002a9cb`
- `SAMLIB!SamOpenDomain` at `0x18002a9a7`
- `SAMLIB!SamOpenDomain` at `0x18002a9cb`
- `SAMLIB!SamConnect` at `0x18002a983`
- `SAMLIB!SamConnect` at `0x18002a983`
- `SAMLIB!SamCloseHandle` at `0x18002a9de`
- `SAMLIB!SamCloseHandle` at `0x18002a9f4`
- `SAMLIB!SamCloseHandle` at `0x18002a9de`
- `SAMLIB!SamCloseHandle` at `0x18002a9f4`

## pseudocode

```c
ULONG IASSamInitialize()
{
  NTSTATUS v0; // ebx
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v0 = SamConnect(0, &v2, 32, &theObjectAttributes);
  if ( v0 >= 0 )
  {
    v0 = SamOpenDomain(v2, 641, theAccountDomainSid, &theAccountDomainHandle);
    if ( v0 >= 0 )
    {
      v0 = SamOpenDomain(v2, 640, theBuiltinDomainSid, &theBuiltinDomainHandle);
      if ( v0 < 0 )
      {
        SamCloseHandle(theAccountDomainHandle);
        theAccountDomainHandle = 0;
      }
    }
    SamCloseHandle(v2);
  }
  return RtlNtStatusToDosError(v0);
}

```

## disassembly

```asm
0x18002a960  push    rbx
0x18002a962  sub     rsp, 20h
0x18002a966  lea     r9, theObjectAttributes
0x18002a96d  mov     [rsp+28h+arg_0], 0
0x18002a976  mov     r8d, 20h ; ' '
0x18002a97c  lea     rdx, [rsp+28h+arg_0]
0x18002a981  xor     ecx, ecx
0x18002a983  call    cs:__imp_SamConnect
0x18002a989  mov     ebx, eax
0x18002a98b  test    eax, eax
0x18002a98d  js      short loc_18002A9FA
0x18002a98f  mov     r8, cs:theAccountDomainSid
0x18002a996  lea     r9, theAccountDomainHandle
0x18002a99d  mov     rcx, [rsp+28h+arg_0]
0x18002a9a2  mov     edx, 281h
0x18002a9a7  call    cs:__imp_SamOpenDomain
0x18002a9ad  mov     ebx, eax
0x18002a9af  test    eax, eax
0x18002a9b1  js      short loc_18002A9EF
0x18002a9b3  mov     r8, cs:theBuiltinDomainSid
0x18002a9ba  lea     r9, theBuiltinDomainHandle
0x18002a9c1  mov     rcx, [rsp+28h+arg_0]
0x18002a9c6  mov     edx, 280h
0x18002a9cb  call    cs:__imp_SamOpenDomain
0x18002a9d1  mov     ebx, eax
0x18002a9d3  test    eax, eax
0x18002a9d5  jns     short loc_18002A9EF
0x18002a9d7  mov     rcx, cs:theAccountDomainHandle
0x18002a9de  call    cs:__imp_SamCloseHandle
0x18002a9e4  mov     cs:theAccountDomainHandle, 0
0x18002a9ef  mov     rcx, [rsp+28h+arg_0]
0x18002a9f4  call    cs:__imp_SamCloseHandle
0x18002a9fa  mov     ecx, ebx; Status
0x18002a9fc  call    cs:__imp_RtlNtStatusToDosError
0x18002aa02  add     rsp, 20h
0x18002aa06  pop     rbx
0x18002aa07  retn
```
