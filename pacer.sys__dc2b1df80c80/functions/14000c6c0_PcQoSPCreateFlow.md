# PcQoSPCreateFlow

- ea: `0x14000c6c0`
- end: `0x14000c753`
- name: `PcQoSPCreateFlow`
- size: `147`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x14000adf8`
- `0x14000c6c0`
- `0x14000c75c`

## pseudocode

```c
__int64 __fastcall PcQoSPCreateFlow(__int64 a1)
{
  int v1; // edx
  __int64 i; // rax
  ULONG v3; // edx
  unsigned int Flow; // eax

  v1 = *(_DWORD *)(a1 + 20);
  if ( v1 != 1 )
  {
    for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
    {
      if ( LODWORD(PcgQoSFlowTypeMapping[i]) == v1 )
      {
        v3 = *(_DWORD *)(*(_QWORD *)a1 + 64LL) + 80;
        if ( *(_DWORD *)(*(_QWORD *)a1 + 64LL) >= 0xFFFFFFB0 )
        {
          Flow = -1073741675;
        }
        else if ( *(_QWORD *)(a1 + 8) >= (unsigned __int64)v3 )
        {
          Flow = PcpCreateFlow(
                   *(_QWORD **)(a1 + 24),
                   *(_DWORD *)(a1 + 16),
                   *(_DWORD *)(a1 + 32),
                   0,
                   v3,
                   HIDWORD(PcgQoSFlowTypeMapping[(unsigned int)i]),
                   *(void **)a1,
                   0,
                   a1 + 36);
        }
        else
        {
          Flow = -1073741789;
        }
        return PcpNormalizeNtStatus(Flow);
      }
    }
  }
  Flow = -1073741811;
  return PcpNormalizeNtStatus(Flow);
}

```

## disassembly

```asm
0x14000c6c0  sub     rsp, 58h
0x14000c6c4  mov     edx, [rcx+14h]
0x14000c6c7  cmp     edx, 1
0x14000c6ca  jz      short loc_14000C741
0x14000c6cc  xor     eax, eax
0x14000c6ce  lea     r10, PcgQoSFlowTypeMapping
0x14000c6d5  cmp     eax, 4
0x14000c6d8  jnb     short loc_14000C741
0x14000c6da  mov     r9d, eax
0x14000c6dd  cmp     [r10+rax*8], edx
0x14000c6e1  jz      short loc_14000C6E7
0x14000c6e3  inc     eax
0x14000c6e5  jmp     short loc_14000C6D5
0x14000c6e7  mov     r8, [rcx]
0x14000c6ea  mov     edx, [r8+40h]
0x14000c6ee  add     edx, 50h ; 'P'
0x14000c6f1  cmp     edx, 50h ; 'P'
0x14000c6f4  jb      short loc_14000C73A
0x14000c6f6  mov     eax, edx
0x14000c6f8  cmp     [rcx+8], rax
0x14000c6fc  jnb     short loc_14000C705
0x14000c6fe  mov     eax, 0C0000023h
0x14000c703  jmp     short loc_14000C746
0x14000c705  lea     rax, [rcx+24h]
0x14000c709  mov     [rsp+58h+var_18], rax
0x14000c70e  mov     eax, [r10+r9*8+4]
0x14000c713  xor     r9d, r9d
0x14000c716  mov     [rsp+58h+var_20], 0
0x14000c71b  mov     [rsp+58h+var_28], r8
0x14000c720  mov     r8d, [rcx+20h]
0x14000c724  mov     [rsp+58h+var_30], eax
0x14000c728  mov     [rsp+58h+var_38], edx
0x14000c72c  mov     edx, [rcx+10h]
0x14000c72f  mov     rcx, [rcx+18h]
0x14000c733  call    PcpCreateFlow
0x14000c738  jmp     short loc_14000C746
0x14000c73a  mov     eax, 0C0000095h
0x14000c73f  jmp     short loc_14000C746
0x14000c741  mov     eax, 0C000000Dh
0x14000c746  mov     ecx, eax
0x14000c748  call    PcpNormalizeNtStatus
0x14000c74d  add     rsp, 58h
0x14000c751  retn
```
