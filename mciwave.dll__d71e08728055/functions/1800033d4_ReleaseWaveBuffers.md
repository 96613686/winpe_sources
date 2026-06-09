# ReleaseWaveBuffers

- ea: `0x1800033d4`
- end: `0x18000340a`
- name: `ReleaseWaveBuffers`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000492c`
- `0x1800050b0`
- `0x180005170`

## callees

- `0x1800033d4`

## import_xrefs

- `WINMM!waveOutReset` at `0x1800033f4`
- `WINMM!waveInReset` at `0x1800033ff`
- `WINMM!waveInReset` at `0x1800033ff`

## pseudocode

```c
MMRESULT __fastcall ReleaseWaveBuffers(__int64 a1)
{
  MMRESULT result; // eax

  if ( *(_QWORD *)(a1 + 48) || *(_QWORD *)(a1 + 56) )
  {
    if ( *(_DWORD *)(a1 + 28) == 1 )
      return waveOutReset(*(HWAVEOUT *)(a1 + 48));
    else
      return waveInReset(*(HWAVEIN *)(a1 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x1800033d4  sub     rsp, 28h
0x1800033d8  cmp     qword ptr [rcx+30h], 0
0x1800033dd  jnz     short loc_1800033E6
0x1800033df  cmp     qword ptr [rcx+38h], 0
0x1800033e4  jz      short loc_180003405
0x1800033e6  cmp     dword ptr [rcx+1Ch], 1
0x1800033ea  jnz     short loc_1800033FB
0x1800033ec  mov     rcx, [rcx+30h]
0x1800033f0  add     rsp, 28h
0x1800033f4  jmp     cs:__imp_waveOutReset
0x1800033fb  mov     rcx, [rcx+38h]; hwi
0x1800033ff  call    cs:__imp_waveInReset
0x180003405  add     rsp, 28h
0x180003409  retn
```
