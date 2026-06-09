# PmBuildStableGuid(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)

- ea: `0x1400206f0`
- end: `0x14002076f`
- name: `?PmBuildStableGuid@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007f70`
- `0x1400254c8`

## callees

- `0x14000ae88`
- `0x1400206f0`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140020710`
- `ntoskrnl!ExUuidCreate` at `0x140020710`

## pseudocode

```c
__int64 __fastcall PmBuildStableGuid(struct _DEVICE_EXTENSION *a1, struct _PARTITION_EXTENSION *a2)
{
  __int64 v2; // rdx
  unsigned int v3; // r8d
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned int *v6; // r10
  __int64 v7; // rax
  __int128 v8; // xmm0

  if ( (ScReadNoFence((unsigned int *)a1 + 129) & 0x800) != 0 )
  {
    return (unsigned int)ExUuidCreate((UUID *)(v2 + 64));
  }
  else
  {
    if ( (ScReadNoFence((unsigned int *)(v2 + 40)) & 0x200) != 0 || (ScReadNoFence(v6) & 0x2000) != 0 )
    {
      v8 = *(_OWORD *)(v5 + 216);
    }
    else
    {
      v7 = 216;
      if ( *(_DWORD *)(v4 + 168) != 1 )
        v7 = 208;
      v8 = *(_OWORD *)(v7 + v4);
    }
    *(_OWORD *)(v4 + 64) = v8;
  }
  return v3;
}

```

## disassembly

```asm
0x1400206f0  sub     rsp, 28h
0x1400206f4  lea     r10, [rcx+204h]
0x1400206fb  mov     r9, rcx
0x1400206fe  mov     rcx, r10; unsigned int *
0x140020701  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140020706  bt      eax, 0Bh
0x14002070a  jnb     short loc_140020721
0x14002070c  lea     rcx, [rdx+40h]; Uuid
0x140020710  call    cs:__imp_ExUuidCreate
0x140020717  nop     dword ptr [rax+rax+00h]
0x14002071c  mov     r8d, eax
0x14002071f  jmp     short loc_140020766
0x140020721  lea     rcx, [rdx+28h]; unsigned int *
0x140020725  xor     r8d, r8d
0x140020728  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14002072d  bt      eax, 9
0x140020731  jb      short loc_140020759
0x140020733  mov     rcx, r10; unsigned int *
0x140020736  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14002073b  bt      eax, 0Dh
0x14002073f  jb      short loc_140020759
0x140020741  cmp     dword ptr [rdx+0A8h], 1
0x140020748  mov     eax, 0D8h
0x14002074d  lea     ecx, [rax-8]
0x140020750  cmovnz  eax, ecx
0x140020753  movups  xmm0, xmmword ptr [rax+rdx]
0x140020757  jmp     short loc_140020761
0x140020759  movups  xmm0, xmmword ptr [r9+0D8h]
0x140020761  movdqu  xmmword ptr [rdx+40h], xmm0
0x140020766  mov     eax, r8d
0x140020769  add     rsp, 28h
0x14002076d  retn
```
