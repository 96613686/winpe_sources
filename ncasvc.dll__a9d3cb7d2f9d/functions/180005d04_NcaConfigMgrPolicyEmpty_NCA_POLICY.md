# NcaConfigMgrPolicyEmpty(NCA_POLICY_ *)

- ea: `0x180005d04`
- end: `0x180005d9a`
- name: `?NcaConfigMgrPolicyEmpty@@YAXPEAUNCA_POLICY_@@@Z`
- size: `150`
- prototype: `void __fastcall(struct NCA_POLICY_ *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006190`
- `0x180006c60`

## callees

- `0x180003770`
- `0x180005d04`
- `0x180005da0`
- `0x180006d70`
- `0x180019344`
- `0x18001cc3e`

## pseudocode

```c
void __fastcall NcaConfigMgrPolicyEmpty(struct NCA_POLICY_ *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 i; // rsi

  NcaFree(*((LPVOID *)a1 + 6));
  NcaFree(*((LPVOID *)a1 + 12));
  if ( !*((_DWORD *)a1 + 21) || *((_DWORD *)a1 + 22) )
    NcaFreeMuiString(*((_QWORD *)a1 + 9));
  else
    NcaFree(*((LPVOID *)a1 + 9));
  NcaConfigMgrProbeListEmpty(a1);
  NcaConfigMgrProbeListEmpty((struct NCA_POLICY_ *)((char *)a1 + 16));
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 8); i = (unsigned int)(i + 1) )
    NcaCustomCommandEmpty(*((_QWORD *)a1 + 5) + 8 * i, v2, v3, v4);
  NcaFree(*((LPVOID *)a1 + 5));
  memset_0(a1, 0, 0x68u);
}

```

## disassembly

```asm
0x180005d04  mov     [rsp+arg_0], rbx
0x180005d09  mov     [rsp+arg_8], rsi
0x180005d0e  push    rdi
0x180005d0f  sub     rsp, 20h
0x180005d13  mov     rbx, rcx
0x180005d16  mov     rcx, [rcx+30h]; lpMem
0x180005d1a  call    NcaFree
0x180005d1f  mov     rcx, [rbx+60h]; lpMem
0x180005d23  call    NcaFree
0x180005d28  cmp     dword ptr [rbx+54h], 0
0x180005d2c  jz      short loc_180005D3F
0x180005d2e  cmp     dword ptr [rbx+58h], 0
0x180005d32  jnz     short loc_180005D3F
0x180005d34  mov     rcx, [rbx+48h]; lpMem
0x180005d38  call    NcaFree
0x180005d3d  jmp     short loc_180005D48
0x180005d3f  mov     rcx, [rbx+48h]
0x180005d43  call    NcaFreeMuiString
0x180005d48  mov     rcx, rbx; struct NCA_PROBE_LIST_ *
0x180005d4b  call    ?NcaConfigMgrProbeListEmpty@@YAXPEAUNCA_PROBE_LIST_@@@Z; NcaConfigMgrProbeListEmpty(NCA_PROBE_LIST_ *)
0x180005d50  lea     rcx, [rbx+10h]; struct NCA_PROBE_LIST_ *
0x180005d54  call    ?NcaConfigMgrProbeListEmpty@@YAXPEAUNCA_PROBE_LIST_@@@Z; NcaConfigMgrProbeListEmpty(NCA_PROBE_LIST_ *)
0x180005d59  xor     esi, esi
0x180005d5b  cmp     [rbx+20h], esi
0x180005d5e  jbe     short loc_180005D74
0x180005d60  mov     rax, [rbx+28h]
0x180005d64  lea     rcx, [rax+rsi*8]
0x180005d68  call    NcaCustomCommandEmpty
0x180005d6d  inc     esi
0x180005d6f  cmp     esi, [rbx+20h]
0x180005d72  jb      short loc_180005D60
0x180005d74  mov     rcx, [rbx+28h]; lpMem
0x180005d78  call    NcaFree
0x180005d7d  xor     edx, edx; Val
0x180005d7f  mov     rcx, rbx; void *
0x180005d82  lea     r8d, [rdx+68h]; Size
0x180005d86  mov     rbx, [rsp+28h+arg_0]
0x180005d8b  mov     rsi, [rsp+28h+arg_8]
0x180005d90  add     rsp, 20h
0x180005d94  pop     rdi
0x180005d95  jmp     memset_0
```
