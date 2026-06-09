# CPacket::CloneSameForMove(void)

- ea: `0x140014ba8`
- end: `0x140014bf7`
- name: `?CloneSameForMove@CPacket@@AEAAPEAV1@XZ`
- size: `79`
- prototype: `struct CPacket *__fastcall(CPacket *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140015ac4`
- `0x14001821c`

## callees

- `0x140014a58`
- `0x140014ba8`

## pseudocode

```c
struct CPacket *__fastcall CPacket::CloneSameForMove(CPacket *this)
{
  struct CPacket *result; // rax
  int v3; // r8d

  result = CPacket::CloneSame(this, 0);
  if ( result )
  {
    v3 = *((_DWORD *)result + 13) ^ (*((_DWORD *)this + 13) ^ *((_DWORD *)result + 13)) & 0x800000;
    *((_DWORD *)result + 13) = v3;
    *((_DWORD *)result + 13) = v3 & 0xFEFFFFFF | _byteswap_ulong(*((_BYTE *)this + 55) & 1);
  }
  return result;
}

```

## disassembly

```asm
0x140014ba8  push    rbx
0x140014baa  sub     rsp, 20h
0x140014bae  xor     edx, edx; int
0x140014bb0  mov     rbx, rcx
0x140014bb3  call    ?CloneSame@CPacket@@AEAAPEAV1@H@Z; CPacket::CloneSame(int)
0x140014bb8  mov     r9, rax
0x140014bbb  test    rax, rax
0x140014bbe  jz      short loc_140014BED
0x140014bc0  mov     edx, [rax+34h]
0x140014bc3  mov     r8d, edx
0x140014bc6  xor     r8d, [rbx+34h]
0x140014bca  and     r8d, 800000h
0x140014bd1  xor     r8d, edx
0x140014bd4  mov     [rax+34h], r8d
0x140014bd8  btr     r8d, 18h
0x140014bdd  movzx   eax, byte ptr [rbx+37h]
0x140014be1  and     eax, 1
0x140014be4  bswap   eax
0x140014be6  or      eax, r8d
0x140014be9  mov     [r9+34h], eax
0x140014bed  mov     rax, r9
0x140014bf0  add     rsp, 20h
0x140014bf4  pop     rbx
0x140014bf5  retn
```
