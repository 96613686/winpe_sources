# PerfpUpdateCounterIndices(void *,PERFLIBCI_QUERY_PROVIDER_NODE *)

- ea: `0x180016ba4`
- end: `0x180016bf1`
- name: `?PerfpUpdateCounterIndices@@YAXPEAXPEAUPERFLIBCI_QUERY_PROVIDER_NODE@@@Z`
- size: `77`
- prototype: `void __fastcall(void *, struct PERFLIBCI_QUERY_PROVIDER_NODE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004b00`

## callees

- `0x180016ba4`

## import_xrefs

- `api-ms-win-core-pcw-l1-1-0!PcwSetQueryItemUserData` at `0x180016bd3`
- `api-ms-win-core-pcw-l1-1-0!PcwSetQueryItemUserData` at `0x180016bd3`

## pseudocode

```c
void __fastcall PerfpUpdateCounterIndices(void *a1, struct PERFLIBCI_QUERY_PROVIDER_NODE *a2)
{
  __int64 i; // rdi
  __int64 v5; // rbp

  for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 7); i = (unsigned int)(*(_DWORD *)(i + v5 + 20) + i) )
  {
    v5 = *((_QWORD *)a2 + 2);
    if ( *(_DWORD *)(i + v5 + 32) != -1 )
      PcwSetQueryItemUserData(a1, *(unsigned int *)(i + v5 + 36), *(unsigned int *)(i + v5 + 32));
  }
  *((_DWORD *)a2 + 9) &= ~4u;
}

```

## disassembly

```asm
0x180016ba4  push    rbx
0x180016ba6  push    rbp
0x180016ba7  push    rsi
0x180016ba8  push    rdi
0x180016ba9  push    r14
0x180016bab  sub     rsp, 20h
0x180016baf  xor     edi, edi
0x180016bb1  mov     rbx, rdx
0x180016bb4  mov     r14, rcx
0x180016bb7  cmp     [rdx+1Ch], edi
0x180016bba  jbe     short loc_180016BE2
0x180016bbc  mov     rbp, [rbx+10h]
0x180016bc0  cmp     dword ptr [rdi+rbp+20h], 0FFFFFFFFh
0x180016bc5  jz      short loc_180016BD9
0x180016bc7  mov     r8d, [rdi+rbp+20h]
0x180016bcc  mov     rcx, r14
0x180016bcf  mov     edx, [rdi+rbp+24h]
0x180016bd3  call    cs:__imp_PcwSetQueryItemUserData
0x180016bd9  add     edi, [rdi+rbp+14h]
0x180016bdd  cmp     edi, [rbx+1Ch]
0x180016be0  jb      short loc_180016BBC
0x180016be2  and     dword ptr [rbx+24h], 0FFFFFFFBh
0x180016be6  add     rsp, 20h
0x180016bea  pop     r14
0x180016bec  pop     rdi
0x180016bed  pop     rsi
0x180016bee  pop     rbp
0x180016bef  pop     rbx
0x180016bf0  retn
```
