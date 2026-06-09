# CscDelete(ushort const *)

- ea: `0x18001123c`
- end: `0x180011287`
- name: `?CscDelete@@YAKPEBG@Z`
- size: `75`
- prototype: `DWORD __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000db90`
- `0x18000dfc4`

## callees

- `0x18001123c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001125f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001125f`
- `CSCDLL!__imp_CSCDeleteW` at `0x180011255`
- `CSCDLL!__imp_CSCDeleteW` at `0x180011255`

## pseudocode

```c
DWORD __fastcall CscDelete(const unsigned __int16 *a1)
{
  DWORD result; // eax
  int i; // ebx

  result = 0;
  for ( i = 3; i > 0; --i )
  {
    if ( (unsigned int)CSCDeleteW(a1) )
      return 0;
    result = GetLastError();
    if ( result != 5 )
      return result;
  }
  if ( !result )
    return 31;
  return result;
}

```

## disassembly

```asm
0x18001123c  mov     [rsp+arg_0], rbx
0x180011241  push    rdi
0x180011242  sub     rsp, 20h
0x180011246  xor     eax, eax
0x180011248  mov     rdi, rcx
0x18001124b  lea     ebx, [rax+3]
0x18001124e  test    ebx, ebx
0x180011250  jle     short loc_180011272
0x180011252  mov     rcx, rdi
0x180011255  call    cs:__imp_CSCDeleteW
0x18001125b  test    eax, eax
0x18001125d  jnz     short loc_18001126E
0x18001125f  call    cs:__imp_GetLastError
0x180011265  cmp     eax, 5
0x180011268  jnz     short loc_18001127C
0x18001126a  dec     ebx
0x18001126c  jmp     short loc_18001124E
0x18001126e  xor     eax, eax
0x180011270  jmp     short loc_18001127C
0x180011272  test    eax, eax
0x180011274  mov     ecx, 1Fh
0x180011279  cmovz   eax, ecx
0x18001127c  mov     rbx, [rsp+28h+arg_0]
0x180011281  add     rsp, 20h
0x180011285  pop     rdi
0x180011286  retn
```
