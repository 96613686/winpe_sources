# NcaConfigMgrProbeListEmpty(NCA_PROBE_LIST_ *)

- ea: `0x180005da0`
- end: `0x180005def`
- name: `?NcaConfigMgrProbeListEmpty@@YAXPEAUNCA_PROBE_LIST_@@@Z`
- size: `79`
- prototype: `void __fastcall(struct NCA_PROBE_LIST_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005d04`

## callees

- `0x180003770`
- `0x180005da0`
- `0x180006da0`

## pseudocode

```c
void __fastcall NcaConfigMgrProbeListEmpty(struct NCA_PROBE_LIST_ *a1)
{
  __int64 i; // rsi

  for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
    NcaProbeEmpty(*((_QWORD *)a1 + 1) + 24 * i);
  NcaFree(*((LPVOID *)a1 + 1));
  *(_OWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180005da0  mov     [rsp+arg_0], rbx
0x180005da5  mov     [rsp+arg_8], rsi
0x180005daa  push    rdi
0x180005dab  sub     rsp, 20h
0x180005daf  xor     esi, esi
0x180005db1  mov     rdi, rcx
0x180005db4  cmp     [rcx], esi
0x180005db6  jbe     short loc_180005DCF
0x180005db8  mov     rax, [rdi+8]
0x180005dbc  lea     rdx, [rsi+rsi*2]
0x180005dc0  lea     rcx, [rax+rdx*8]
0x180005dc4  call    NcaProbeEmpty
0x180005dc9  inc     esi
0x180005dcb  cmp     esi, [rdi]
0x180005dcd  jb      short loc_180005DB8
0x180005dcf  mov     rcx, [rdi+8]; lpMem
0x180005dd3  call    NcaFree
0x180005dd8  mov     rbx, [rsp+28h+arg_0]
0x180005ddd  xorps   xmm0, xmm0
0x180005de0  mov     rsi, [rsp+28h+arg_8]
0x180005de5  movups  xmmword ptr [rdi], xmm0
0x180005de8  add     rsp, 20h
0x180005dec  pop     rdi
0x180005ded  retn
```
