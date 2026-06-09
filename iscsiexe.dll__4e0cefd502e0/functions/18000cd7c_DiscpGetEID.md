# DiscpGetEID

- ea: `0x18000cd7c`
- end: `0x18000ce21`
- name: `DiscpGetEID`
- size: `165`
- prototype: `DWORD __fastcall(CHAR **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d364`
- `0x18000d490`

## callees

- `0x18000cd7c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18000cddd`
- `ISCSIUM!DiscpAllocMemory` at `0x18000cddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce09`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000cd9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000cdf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000cd9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000cdf8`

## pseudocode

```c
DWORD __fastcall DiscpGetEID(CHAR **a1)
{
  DWORD v2; // ecx
  DWORD result; // eax
  CHAR *v4; // rax
  CHAR *v5; // rbx
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 0;
  if ( GetComputerNameExA(ComputerNameDnsFullyQualified, 0, &nSize) )
  {
    v2 = 4096;
    nSize = 4096;
LABEL_9:
    v4 = (CHAR *)DiscpAllocMemory(v2 + 1);
    v5 = v4;
    if ( !v4 )
      return 8;
    if ( !GetComputerNameExA(ComputerNameDnsFullyQualified, v4, &nSize) )
      return GetLastError();
    *a1 = v5;
    return 0;
  }
  result = GetLastError();
  v2 = nSize;
  if ( !nSize )
  {
    v2 = 4096;
    nSize = 4096;
  }
  if ( (result == 234 || result == 122 || !result) && v2 )
    goto LABEL_9;
  return result;
}

```

## disassembly

```asm
0x18000cd7c  mov     [rsp+arg_0], rbx
0x18000cd81  push    rdi
0x18000cd82  sub     rsp, 20h
0x18000cd86  xor     edx, edx; lpBuffer
0x18000cd88  mov     [rsp+28h+nSize], 0
0x18000cd90  mov     rdi, rcx
0x18000cd93  lea     r8, [rsp+28h+nSize]; nSize
0x18000cd98  lea     ecx, [rdx+3]; NameType
0x18000cd9b  call    cs:__imp_GetComputerNameExA
0x18000cda1  test    eax, eax
0x18000cda3  jz      short loc_18000CDB0
0x18000cda5  mov     ecx, 1000h
0x18000cdaa  mov     [rsp+28h+nSize], ecx
0x18000cdae  jmp     short loc_18000CDDB
0x18000cdb0  call    cs:__imp_GetLastError
0x18000cdb6  mov     ecx, [rsp+28h+nSize]
0x18000cdba  test    ecx, ecx
0x18000cdbc  jnz     short loc_18000CDC7
0x18000cdbe  mov     ecx, 1000h
0x18000cdc3  mov     [rsp+28h+nSize], ecx
0x18000cdc7  cmp     eax, 0EAh
0x18000cdcc  jz      short loc_18000CDD7
0x18000cdce  cmp     eax, 7Ah ; 'z'
0x18000cdd1  jz      short loc_18000CDD7
0x18000cdd3  test    eax, eax
0x18000cdd5  jnz     short loc_18000CE16
0x18000cdd7  test    ecx, ecx
0x18000cdd9  jz      short loc_18000CE16
0x18000cddb  inc     ecx
0x18000cddd  call    cs:__imp_DiscpAllocMemory
0x18000cde3  mov     rbx, rax
0x18000cde6  test    rax, rax
0x18000cde9  jz      short loc_18000CE11
0x18000cdeb  lea     r8, [rsp+28h+nSize]; nSize
0x18000cdf0  mov     rdx, rax; lpBuffer
0x18000cdf3  mov     ecx, 3; NameType
0x18000cdf8  call    cs:__imp_GetComputerNameExA
0x18000cdfe  test    eax, eax
0x18000ce00  jz      short loc_18000CE09
0x18000ce02  mov     [rdi], rbx
0x18000ce05  xor     eax, eax
0x18000ce07  jmp     short loc_18000CE16
0x18000ce09  call    cs:__imp_GetLastError
0x18000ce0f  jmp     short loc_18000CE16
0x18000ce11  mov     eax, 8
0x18000ce16  mov     rbx, [rsp+28h+arg_0]
0x18000ce1b  add     rsp, 20h
0x18000ce1f  pop     rdi
0x18000ce20  retn
```
