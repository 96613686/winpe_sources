# FindDHCPServersThreadRoutine

- ea: `0x18001b780`
- end: `0x18001b82d`
- name: `FindDHCPServersThreadRoutine`
- size: `173`
- prototype: `ULONG __fastcall(__int64 *Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001b430`
- `0x18001b780`
- `0x18001c924`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b796`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b796`
- `WS2_32!__imp_inet_addr` at `0x18001b7a3`
- `WS2_32!__imp_inet_addr` at `0x18001b7b2`
- `WS2_32!__imp_inet_addr` at `0x18001b7a3`
- `WS2_32!__imp_inet_addr` at `0x18001b7b2`

## pseudocode

```c
ULONG __fastcall FindDHCPServersThreadRoutine(__int64 *Parameter)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  unsigned int v3; // esi
  ULONG result; // eax
  ULONG v5; // ebx
  int v6; // edx
  int v7; // ecx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = *Parameter;
  v2 = Parameter[1];
  free(Parameter);
  v3 = inet_addr((const char *)(v2 + 448));
  result = inet_addr((const char *)(v2 + 464));
  v5 = result;
  if ( v3 )
  {
    v6 = *(_DWORD *)(v1 + 28);
    v7 = *(_DWORD *)(v1 + 24);
    v8 = 0;
    v9 = 0;
    result = DhcpFindDHCPServers(v7, v6, v3, (int)&v8, &v9);
    if ( !result )
    {
      if ( v8 )
        result = AddServerToList(v1, v3, v5);
      if ( v9 )
        return AddServerToList(v1, v3, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b780  mov     [rsp+arg_10], rbx
0x18001b785  mov     [rsp+arg_18], rsi
0x18001b78a  push    rdi
0x18001b78b  sub     rsp, 30h
0x18001b78f  mov     rdi, [rcx]
0x18001b792  mov     rbx, [rcx+8]
0x18001b796  call    cs:__imp_free
0x18001b79c  lea     rcx, [rbx+1C0h]; cp
0x18001b7a3  call    cs:__imp_inet_addr
0x18001b7a9  lea     rcx, [rbx+1D0h]; cp
0x18001b7b0  mov     esi, eax
0x18001b7b2  call    cs:__imp_inet_addr
0x18001b7b8  mov     ebx, eax
0x18001b7ba  test    esi, esi
0x18001b7bc  jz      short loc_18001B81D
0x18001b7be  mov     edx, [rdi+1Ch]; int
0x18001b7c1  lea     rax, [rsp+38h+arg_8]
0x18001b7c6  mov     ecx, [rdi+18h]; int
0x18001b7c9  lea     r9, [rsp+38h+arg_0]; int
0x18001b7ce  mov     r8d, esi; int
0x18001b7d1  mov     [rsp+38h+var_18], rax; void *
0x18001b7d6  mov     [rsp+38h+arg_0], 0
0x18001b7de  mov     [rsp+38h+arg_8], 0
0x18001b7e6  call    DhcpFindDHCPServers
0x18001b7eb  test    eax, eax
0x18001b7ed  jnz     short loc_18001B81D
0x18001b7ef  mov     r9d, [rsp+38h+arg_0]
0x18001b7f4  test    r9d, r9d
0x18001b7f7  jz      short loc_18001B806
0x18001b7f9  mov     r8d, ebx
0x18001b7fc  mov     edx, esi
0x18001b7fe  mov     rcx, rdi
0x18001b801  call    AddServerToList
0x18001b806  mov     r9d, [rsp+38h+arg_8]
0x18001b80b  test    r9d, r9d
0x18001b80e  jz      short loc_18001B81D
0x18001b810  mov     r8d, ebx
0x18001b813  mov     edx, esi
0x18001b815  mov     rcx, rdi
0x18001b818  call    AddServerToList
0x18001b81d  mov     rbx, [rsp+38h+arg_10]
0x18001b822  mov     rsi, [rsp+38h+arg_18]
0x18001b827  add     rsp, 30h
0x18001b82b  pop     rdi
0x18001b82c  retn
```
