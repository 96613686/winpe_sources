# NcaEvCollProbesInnerDelete(NCA_EVCOLL_USER_PROBES_ *)

- ea: `0x180011f10`
- end: `0x180011f77`
- name: `?NcaEvCollProbesInnerDelete@@YAXPEAUNCA_EVCOLL_USER_PROBES_@@@Z`
- size: `103`
- prototype: `void __fastcall(struct NCA_EVCOLL_USER_PROBES_ *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800127ec`
- `0x180012b6c`
- `0x180012c20`
- `0x180017610`

## callees

- `0x180003770`
- `0x180011bc0`
- `0x180011f10`

## pseudocode

```c
void __fastcall NcaEvCollProbesInnerDelete(struct NCA_EVCOLL_USER_PROBES_ *a1)
{
  unsigned int v2; // edi
  unsigned int i; // esi

  if ( *((_QWORD *)a1 + 3) )
  {
    v2 = *((_DWORD *)a1 + 4);
    if ( v2 )
    {
      for ( i = 0; i < v2; ++i )
        NcaEvCollProbeStop((struct NCA_EVCOLL_PROBE_ *)(*((_QWORD *)a1 + 3) + 392LL * i));
      NcaFree(*((LPVOID *)a1 + 3));
      *((_QWORD *)a1 + 3) = 0;
      *((_DWORD *)a1 + 4) = 0;
    }
  }
}

```

## disassembly

```asm
0x180011f10  mov     [rsp+arg_0], rbx
0x180011f15  mov     [rsp+arg_8], rsi
0x180011f1a  push    rdi
0x180011f1b  sub     rsp, 20h
0x180011f1f  cmp     qword ptr [rcx+18h], 0
0x180011f24  mov     rbx, rcx
0x180011f27  jz      short loc_180011F66
0x180011f29  mov     edi, [rcx+10h]
0x180011f2c  test    edi, edi
0x180011f2e  jz      short loc_180011F66
0x180011f30  xor     esi, esi
0x180011f32  test    edi, edi
0x180011f34  jz      short loc_180011F4E
0x180011f36  mov     eax, esi
0x180011f38  imul    rcx, rax, 188h
0x180011f3f  add     rcx, [rbx+18h]; struct NCA_EVCOLL_PROBE_ *
0x180011f43  call    ?NcaEvCollProbeStop@@YAXPEAUNCA_EVCOLL_PROBE_@@@Z; NcaEvCollProbeStop(NCA_EVCOLL_PROBE_ *)
0x180011f48  inc     esi
0x180011f4a  cmp     esi, edi
0x180011f4c  jb      short loc_180011F36
0x180011f4e  mov     rcx, [rbx+18h]; lpMem
0x180011f52  call    NcaFree
0x180011f57  mov     qword ptr [rbx+18h], 0
0x180011f5f  mov     dword ptr [rbx+10h], 0
0x180011f66  mov     rbx, [rsp+28h+arg_0]
0x180011f6b  mov     rsi, [rsp+28h+arg_8]
0x180011f70  add     rsp, 20h
0x180011f74  pop     rdi
0x180011f75  retn
```
