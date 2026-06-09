# CDistribution::HandleCreatePacketCompletedSuccessSync(_IRP *)

- ea: `0x14000e1c0`
- end: `0x14000e1df`
- name: `?HandleCreatePacketCompletedSuccessSync@CDistribution@@EEAAJPEAU_IRP@@@Z`
- size: `31`
- prototype: `__int64 __fastcall(CDistribution *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000df60`
- `0x14000e1c0`

## pseudocode

```c
__int64 __fastcall CDistribution::HandleCreatePacketCompletedSuccessSync(CDistribution *this, struct _IRP *a2)
{
  if ( *((CDistribution **)this + 48) == (CDistribution *)((char *)this + 384) )
    return 0;
  else
    return CDistribution::HandleCreatePacketCompletedSuccessAsync(this, a2);
}

```

## disassembly

```asm
0x14000e1c0  sub     rsp, 28h
0x14000e1c4  lea     rax, [rcx+180h]
0x14000e1cb  cmp     [rax], rax
0x14000e1ce  jnz     short loc_14000E1D4
0x14000e1d0  xor     eax, eax
0x14000e1d2  jmp     short loc_14000E1D9
0x14000e1d4  call    ?HandleCreatePacketCompletedSuccessAsync@CDistribution@@UEAAJPEAU_IRP@@@Z; CDistribution::HandleCreatePacketCompletedSuccessAsync(_IRP *)
0x14000e1d9  add     rsp, 28h
0x14000e1dd  retn
```
