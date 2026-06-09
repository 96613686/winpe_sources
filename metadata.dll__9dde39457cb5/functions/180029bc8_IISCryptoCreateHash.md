# IISCryptoCreateHash

- ea: `0x180029bc8`
- end: `0x180029c1e`
- name: `IISCryptoCreateHash`
- size: `86`
- prototype: `__int64 __fastcall(HCRYPTHASH *phHash, HCRYPTPROV hProv)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180029aa4`
- `0x18002a710`
- `0x18002a9c0`
- `0x18002aea0`
- `0x18002b0a0`
- `0x18002b2a0`
- `0x18002b42c`
- `0x18002b580`
- `0x18002b794`

## callees

- `0x18002937c`
- `0x180029bc8`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x180029c0b`
- `ADVAPI32!CryptCreateHash` at `0x180029c0b`

## pseudocode

```c
__int64 __fastcall IISCryptoCreateHash(HCRYPTHASH *phHash, HCRYPTPROV hProv)
{
  if ( dword_180048964 )
  {
    if ( CryptCreateHash(hProv, 0x8003u, 0, 0, phHash) )
      return 0;
    return IcpGetLastError();
  }
  else
  {
    if ( hProv == 1984918096 )
    {
      *phHash = 1750294856;
      return 0;
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180029bc8  sub     rsp, 38h
0x180029bcc  cmp     cs:dword_180048964, 0
0x180029bd3  mov     rax, rdx
0x180029bd6  jnz     short loc_180029BF8
0x180029bd8  cmp     rax, 764F7250h
0x180029bde  jnz     short loc_180029BEE
0x180029be0  mov     qword ptr [rcx], 68536148h
0x180029be7  xor     eax, eax
0x180029be9  add     rsp, 38h
0x180029bed  retn
0x180029bee  mov     eax, 80070057h
0x180029bf3  add     rsp, 38h
0x180029bf7  retn
0x180029bf8  mov     [rsp+38h+phHash], rcx; phHash
0x180029bfd  xor     r9d, r9d; dwFlags
0x180029c00  mov     rcx, rax; hProv
0x180029c03  xor     r8d, r8d; hKey
0x180029c06  mov     edx, 8003h; Algid
0x180029c0b  call    cs:__imp_CryptCreateHash
0x180029c11  test    eax, eax
0x180029c13  jnz     short loc_180029BE7
0x180029c15  add     rsp, 38h
0x180029c19  jmp     ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
```
