# DiscoveriSNSServersThreadRoutine

- ea: `0x18001b540`
- end: `0x18001b5be`
- name: `DiscoveriSNSServersThreadRoutine`
- size: `126`
- prototype: `__int64 __fastcall(__int64 *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001b540`
- `0x18001cd90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b561`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b561`

## pseudocode

```c
__int64 __fastcall DiscoveriSNSServersThreadRoutine(__int64 *Parameter)
{
  __int64 v1; // rdi
  int *v2; // rbx
  int v3; // r9d
  int v4; // ecx
  int v5; // r9d
  __int64 result; // rax
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v1 = *Parameter;
  v2 = (int *)Parameter[1];
  memset(v7, 0, 14);
  free(Parameter);
  LOBYTE(v3) = 83;
  v4 = DhcpGetiSNSDHCPOption(*(_DWORD *)(v1 + 28), v2[4], v2[6], v3, v7);
  if ( v4 )
  {
    LOBYTE(v5) = 43;
    v4 = DhcpGetiSNSDHCPOption(*(_DWORD *)(v1 + 28), v2[4], v2[6], v5, v7);
  }
  result = 0;
  if ( !v4 )
    result = *(unsigned int *)((char *)&v7[1] + 2);
  v2[7] = result;
  return result;
}

```

## disassembly

```asm
0x18001b540  mov     [rsp+arg_0], rbx
0x18001b545  push    rdi
0x18001b546  sub     rsp, 40h
0x18001b54a  mov     rdi, [rcx]
0x18001b54d  xor     eax, eax
0x18001b54f  mov     rbx, [rcx+8]
0x18001b553  mov     [rsp+48h+var_18], rax
0x18001b558  mov     [rsp+48h+var_10], eax
0x18001b55c  mov     [rsp+48h+var_C], ax
0x18001b561  call    cs:__imp_free
0x18001b567  mov     r8d, [rbx+18h]; int
0x18001b56b  lea     rax, [rsp+48h+var_18]
0x18001b570  mov     edx, [rbx+10h]; int
0x18001b573  mov     r9b, 53h ; 'S'; int
0x18001b576  mov     ecx, [rdi+1Ch]; int
0x18001b579  mov     [rsp+48h+var_28], rax; void *
0x18001b57e  call    DhcpGetiSNSDHCPOption
0x18001b583  mov     ecx, eax
0x18001b585  test    eax, eax
0x18001b587  jz      short loc_18001B5A7
0x18001b589  mov     r8d, [rbx+18h]; int
0x18001b58d  lea     rax, [rsp+48h+var_18]
0x18001b592  mov     edx, [rbx+10h]; int
0x18001b595  mov     r9b, 2Bh ; '+'; int
0x18001b598  mov     ecx, [rdi+1Ch]; int
0x18001b59b  mov     [rsp+48h+var_28], rax; void *
0x18001b5a0  call    DhcpGetiSNSDHCPOption
0x18001b5a5  mov     ecx, eax
0x18001b5a7  xor     eax, eax
0x18001b5a9  test    ecx, ecx
0x18001b5ab  cmovz   eax, [rsp+48h+var_10+2]
0x18001b5b0  mov     [rbx+1Ch], eax
0x18001b5b3  mov     rbx, [rsp+48h+arg_0]
0x18001b5b8  add     rsp, 40h
0x18001b5bc  pop     rdi
0x18001b5bd  retn
```
