# RtlValidSid

- ea: `0x180015af0`
- end: `0x180015b17`
- name: `RtlValidSid`
- size: `39`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180012eb0`
- `0x180013ed0`
- `0x180014450`
- `0x180014e60`
- `0x1800152b0`
- `0x180015490`
- `0x1800155b0`
- `0x180015710`
- `0x1800412a0`
- `0x1800414a0`
- `0x1800b1420`
- `0x1800b34e0`
- `0x1800b42b0`
- `0x1800d1770`
- `0x1800de100`
- `0x1800e5040`
- `0x18013d080`
- `0x18013d320`
- `0x18013d480`
- `0x18013d800`
- `0x18013d9a0`

## callees

- `0x180015af0`

## pseudocode

```c
bool __fastcall RtlValidSid(_BYTE *a1)
{
  return a1 && (*a1 & 0xF) == 1 && a1[1] <= 0xFu;
}

```

## disassembly

```asm
0x180015af0  test    rcx, rcx
0x180015af3  jz      short loc_180015B12
0x180015af5  movzx   eax, byte ptr [rcx]
0x180015af8  and     al, 0Fh
0x180015afa  cmp     al, 1
0x180015afc  jnz     short loc_180015B12
0x180015afe  movzx   eax, byte ptr [rcx+1]
0x180015b02  cmp     al, 0Fh
0x180015b04  ja      short loc_180015B12
0x180015b06  test    al, al
0x180015b08  jz      short loc_180015B0E
0x180015b0a  mov     edx, [rcx+rax*4+4]
0x180015b0e  mov     al, 1
0x180015b10  jmp     short locret_180015B16
0x180015b12  jmp     short loc_180015B18
0x180015b14  xor     al, al
0x180015b16  retn
0x180015b18  xor     al, al
0x180015b1a  retn
```
