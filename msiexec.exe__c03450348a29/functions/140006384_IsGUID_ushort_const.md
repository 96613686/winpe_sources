# IsGUID(ushort const *)

- ea: `0x140006384`
- end: `0x1400063cd`
- name: `?IsGUID@@YA_NPEBG@Z`
- size: `73`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006300`
- `0x140006e10`
- `0x140008b10`

## callees

- `0x140006384`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x14000638d`
- `KERNEL32!lstrlenW` at `0x14000638d`

## pseudocode

```c
bool __fastcall IsGUID(const unsigned __int16 *a1)
{
  return lstrlenW(a1) == 38
      && *a1 == 123
      && a1[9] == 45
      && a1[14] == 45
      && a1[19] == 45
      && a1[24] == 45
      && a1[37] == 125;
}

```

## disassembly

```asm
0x140006384  push    rbx
0x140006386  sub     rsp, 20h
0x14000638a  mov     rbx, rcx
0x14000638d  call    cs:__imp_lstrlenW
0x140006393  cmp     eax, 26h ; '&'
0x140006396  jnz     short loc_1400063C5
0x140006398  cmp     word ptr [rbx], 7Bh ; '{'
0x14000639c  jnz     short loc_1400063C5
0x14000639e  mov     ax, 2Dh ; '-'
0x1400063a2  cmp     [rbx+12h], ax
0x1400063a6  jnz     short loc_1400063C5
0x1400063a8  cmp     [rbx+1Ch], ax
0x1400063ac  jnz     short loc_1400063C5
0x1400063ae  cmp     [rbx+26h], ax
0x1400063b2  jnz     short loc_1400063C5
0x1400063b4  cmp     [rbx+30h], ax
0x1400063b8  jnz     short loc_1400063C5
0x1400063ba  cmp     word ptr [rbx+4Ah], 7Dh ; '}'
0x1400063bf  jnz     short loc_1400063C5
0x1400063c1  mov     al, 1
0x1400063c3  jmp     short loc_1400063C7
0x1400063c5  xor     al, al
0x1400063c7  add     rsp, 20h
0x1400063cb  pop     rbx
0x1400063cc  retn
```
