# DsRolepIsDnsNameChild

- ea: `0x180016c68`
- end: `0x180016cb0`
- name: `DsRolepIsDnsNameChild`
- size: `72`
- prototype: `__int64 __fastcall(PCWSTR pName2, wchar_t *Str)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800058a0`
- `0x180006c30`

## callees

- `0x180016c68`

## import_xrefs

- `msvcrt!wcschr` at `0x180016c80`
- `msvcrt!wcschr` at `0x180016c80`
- `DNSAPI!DnsNameCompare_W` at `0x180016c94`
- `DNSAPI!DnsNameCompare_W` at `0x180016c94`

## pseudocode

```c
__int64 __fastcall DsRolepIsDnsNameChild(PCWSTR pName2, wchar_t *Str)
{
  wchar_t *v3; // rax
  unsigned int v4; // ebx

  v3 = wcschr(Str, 0x2Eu);
  if ( !v3 )
    return 1212;
  v4 = 0;
  if ( !DnsNameCompare_W(v3 + 1, pName2) )
    return 1212;
  return v4;
}

```

## disassembly

```asm
0x180016c68  mov     [rsp+arg_0], rbx
0x180016c6d  push    rdi
0x180016c6e  sub     rsp, 20h
0x180016c72  mov     rax, rdx
0x180016c75  mov     rdi, rcx
0x180016c78  mov     rcx, rax; Str
0x180016c7b  mov     edx, 2Eh ; '.'; Ch
0x180016c80  call    cs:__imp_wcschr
0x180016c86  test    rax, rax
0x180016c89  jz      short loc_180016C9E
0x180016c8b  lea     rcx, [rax+2]; pName1
0x180016c8f  mov     rdx, rdi; pName2
0x180016c92  xor     ebx, ebx
0x180016c94  call    cs:__imp_DnsNameCompare_W
0x180016c9a  test    eax, eax
0x180016c9c  jnz     short loc_180016CA3
0x180016c9e  mov     ebx, 4BCh
0x180016ca3  mov     eax, ebx
0x180016ca5  mov     rbx, [rsp+28h+arg_0]
0x180016caa  add     rsp, 20h
0x180016cae  pop     rdi
0x180016caf  retn
```
