# FatCheckDirtyBit

- ea: `0x1400497f4`
- end: `0x1400498df`
- name: `FatCheckDirtyBit`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140040674`
- `0x140042ec8`

## callees

- `0x1400246bc`
- `0x1400497f4`

## import_xrefs

- `ntoskrnl!FsRtlBalanceReads` at `0x1400498ab`
- `ntoskrnl!FsRtlBalanceReads` at `0x1400498ab`
- `ntoskrnl!CcUnpinData` at `0x1400498c2`
- `ntoskrnl!CcUnpinData` at `0x14005fded`
- `ntoskrnl!CcUnpinData` at `0x1400498c2`
- `ntoskrnl!CcUnpinData` at `0x14005fded`

## pseudocode

```c
void __fastcall FatCheckDirtyBit(__int64 a1, __int64 a2)
{
  char v4; // dl
  PVOID Bcb; // [rsp+60h] [rbp+18h] BYREF
  __int64 v6; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  Bcb = 0;
  FatReadVolumeFile(a1, a2, 0, 90, &Bcb, &v6);
  if ( *(_WORD *)(v6 + 22) )
    v4 = *(_BYTE *)(v6 + 37);
  else
    v4 = *(_BYTE *)(v6 + 65);
  if ( (v4 & 1) != 0 )
  {
    if ( *(_BYTE *)(a1 + 64) != 13 || *(_BYTE *)(a1 + 65) != 2 || (*(_DWORD *)(a2 + 200) & 0x800) == 0 )
      _InterlockedOr((volatile signed __int32 *)(a2 + 200), 0x10u);
  }
  else if ( (*(_DWORD *)(a2 + 200) & 0x10) != 0 )
  {
    _InterlockedAnd((volatile signed __int32 *)(a2 + 200), 0xFFFFFFEF);
  }
  else
  {
    FsRtlBalanceReads(*(PDEVICE_OBJECT *)(a2 + 136));
  }
  if ( Bcb )
    CcUnpinData(Bcb);
}

```

## disassembly

```asm
0x1400497f4  mov     r11, rsp
0x1400497f7  mov     [r11+8], rbx
0x1400497fb  mov     [r11+10h], rsi
0x1400497ff  push    rdi
0x140049800  sub     rsp, 40h
0x140049804  mov     rbx, rdx
0x140049807  mov     rdi, rcx
0x14004980a  xor     esi, esi
0x14004980c  mov     [r11+20h], rsi
0x140049810  mov     [r11+18h], rsi
0x140049814  lea     rax, [r11+20h]
0x140049818  mov     [r11-20h], rax
0x14004981c  lea     rax, [r11+18h]
0x140049820  mov     [r11-28h], rax
0x140049824  lea     r9d, [rsi+5Ah]
0x140049828  xor     r8d, r8d
0x14004982b  call    FatReadVolumeFile
0x140049830  nop
0x140049831  mov     rdx, [rsp+48h+arg_18]
0x140049836  cmp     [rdx+16h], si
0x14004983a  jnz     short loc_140049841
0x14004983c  mov     dl, [rdx+41h]
0x14004983f  jmp     short loc_140049844
0x140049841  mov     dl, [rdx+25h]
0x140049844  and     dl, 1
0x140049847  mov     rcx, [rbx+0C0h]
0x14004984e  movzx   eax, word ptr [rcx+6]
0x140049852  mov     [rsp+48h+var_18], ax
0x140049857  mov     eax, 40h ; '@'
0x14004985c  mov     [rsp+48h+var_16], ax
0x140049861  lea     rax, [rcx+20h]
0x140049865  mov     [rsp+48h+var_10], rax
0x14004986a  test    dl, dl
0x14004986c  jz      short loc_140049890
0x14004986e  cmp     byte ptr [rdi+40h], 0Dh
0x140049872  jnz     short loc_140049886
0x140049874  cmp     byte ptr [rdi+41h], 2
0x140049878  jnz     short loc_140049886
0x14004987a  mov     eax, [rbx+0C8h]
0x140049880  bt      eax, 0Bh
0x140049884  jb      short loc_1400498B8
0x140049886  lock or dword ptr [rbx+0C8h], 10h
0x14004988e  jmp     short loc_1400498B8
0x140049890  mov     eax, [rbx+0C8h]
0x140049896  test    al, 10h
0x140049898  jz      short loc_1400498A4
0x14004989a  lock and dword ptr [rbx+0C8h], 0FFFFFFEFh
0x1400498a2  jmp     short loc_1400498B8
0x1400498a4  mov     rcx, [rbx+88h]; TargetDevice
0x1400498ab  call    cs:__imp_FsRtlBalanceReads
0x1400498b2  nop     dword ptr [rax+rax+00h]
0x1400498b7  nop
0x1400498b8  mov     rcx, [rsp+48h+Bcb]; Bcb
0x1400498bd  test    rcx, rcx
0x1400498c0  jz      short loc_1400498CE
0x1400498c2  call    cs:__imp_CcUnpinData
0x1400498c9  nop     dword ptr [rax+rax+00h]
0x1400498ce  mov     rbx, [rsp+48h+arg_0]
0x1400498d3  mov     rsi, [rsp+48h+arg_8]
0x1400498d8  add     rsp, 40h
0x1400498dc  pop     rdi
0x1400498dd  retn
0x14005fddb  push    rbp
0x14005fddd  sub     rsp, 30h
0x14005fde1  mov     rbp, rdx
0x14005fde4  mov     rcx, [rbp+60h]; Bcb
0x14005fde8  test    rcx, rcx
0x14005fdeb  jz      short loc_14005FDFA
0x14005fded  call    cs:__imp_CcUnpinData
0x14005fdf4  nop     dword ptr [rax+rax+00h]
0x14005fdf9  nop
0x14005fdfa  add     rsp, 30h
0x14005fdfe  pop     rbp
0x14005fdff  retn
```
