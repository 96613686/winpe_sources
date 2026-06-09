# IISCryptoDeleteContainerByName

- ea: `0x18000f940`
- end: `0x18000f991`
- name: `IISCryptoDeleteContainerByName`
- size: `81`
- prototype: `__int64 __fastcall(LPCSTR szContainer)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009f60`

## callees

- `0x18000f90c`
- `0x18000f940`

## import_xrefs

- `ADVAPI32!CryptAcquireContextA` at `0x18000f978`
- `ADVAPI32!CryptAcquireContextA` at `0x18000f978`

## pseudocode

```c
__int64 __fastcall IISCryptoDeleteContainerByName(LPCSTR szContainer, int a2)
{
  unsigned int v3; // ebx
  HCRYPTPROV phProv; // [rsp+50h] [rbp+18h] BYREF

  phProv = 0;
  if ( !dword_180016F3C )
    return 0;
  v3 = 0;
  if ( !CryptAcquireContextA(&phProv, szContainer, "Microsoft Base Cryptographic Provider v1.0", 1u, a2 | 0x10) )
    return (unsigned int)IcpGetLastError();
  return v3;
}

```

## disassembly

```asm
0x18000f940  push    rbx
0x18000f942  sub     rsp, 30h
0x18000f946  cmp     cs:dword_180016F3C, 0
0x18000f94d  mov     [rsp+38h+phProv], 0
0x18000f956  jnz     short loc_18000F95C
0x18000f958  xor     eax, eax
0x18000f95a  jmp     short loc_18000F98B
0x18000f95c  or      edx, 10h
0x18000f95f  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18000f966  mov     [rsp+38h+dwFlags], edx; dwFlags
0x18000f96a  xor     ebx, ebx
0x18000f96c  mov     rdx, rcx; szContainer
0x18000f96f  lea     rcx, [rsp+38h+phProv]; phProv
0x18000f974  lea     r9d, [rbx+1]; dwProvType
0x18000f978  call    cs:__imp_CryptAcquireContextA
0x18000f97e  test    eax, eax
0x18000f980  jnz     short loc_18000F989
0x18000f982  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18000f987  mov     ebx, eax
0x18000f989  mov     eax, ebx
0x18000f98b  add     rsp, 30h
0x18000f98f  pop     rbx
0x18000f990  retn
```
