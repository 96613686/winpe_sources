# MRxSmbCacheInfo

- ea: `0x14004a930`
- end: `0x14004a98a`
- name: `MRxSmbCacheInfo`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400281f8`

## callees

- `0x14004a930`
- `0x14004a990`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004a96c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004a96c`

## pseudocode

```c
bool __fastcall MRxSmbCacheInfo(__int64 a1, __int64 a2)
{
  return MRxSmbInfoCacheLevel
      && !*(_BYTE *)(a2 + 505)
      && (MRxSmbInfoCacheLevel != 1 || !(unsigned __int8)MRxSmbIsLongFileName() || *(_DWORD *)(a2 + 416) == 4)
      && *(_DWORD *)(MRxSmbGetConfigurationBlock() + 144);
}

```

## disassembly

```asm
0x14004a930  push    rbx
0x14004a932  sub     rsp, 20h
0x14004a936  mov     eax, cs:MRxSmbInfoCacheLevel
0x14004a93c  mov     rbx, rdx
0x14004a93f  test    eax, eax
0x14004a941  jnz     short loc_14004A94C
0x14004a943  xor     al, al
0x14004a945  add     rsp, 20h
0x14004a949  pop     rbx
0x14004a94a  retn
0x14004a94c  cmp     byte ptr [rdx+1F9h], 0
0x14004a953  jnz     short loc_14004A943
0x14004a955  cmp     eax, 1
0x14004a958  jnz     short loc_14004A96C
0x14004a95a  call    MRxSmbIsLongFileName
0x14004a95f  test    al, al
0x14004a961  jz      short loc_14004A96C
0x14004a963  cmp     dword ptr [rbx+1A0h], 4
0x14004a96a  jnz     short loc_14004A943
0x14004a96c  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14004a973  nop     dword ptr [rax+rax+00h]
0x14004a978  cmp     dword ptr [rax+90h], 0
0x14004a97f  jz      short loc_14004A943
0x14004a981  mov     al, 1
0x14004a983  add     rsp, 20h
0x14004a987  pop     rbx
0x14004a988  retn
```
