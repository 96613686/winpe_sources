# MCIResetCompressionGlobal

- ea: `0x180001ab8`
- end: `0x180001b3a`
- name: `MCIResetCompressionGlobal`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019d0`

## callees

- `0x180001ab8`
- `0x18001727c`

## pseudocode

```c
__int64 __fastcall MCIResetCompressionGlobal(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v4; // rax
  __int64 v5; // rax

  switch ( *(_WORD *)(a1 + 676) & 0xF )
  {
    case 0:
      return 1;
    case 1:
      v4 = *(_QWORD *)(a1 + 8);
      if ( *(_DWORD *)v4 == 1128874829 )
      {
        v5 = *(_QWORD *)(v4 + 24);
        if ( v5 )
          *(_BYTE *)(v5 + 12248) = 0;
        return 1;
      }
      goto LABEL_12;
    case 3:
      v2 = *(_QWORD *)(a1 + 8);
      if ( *(_DWORD *)v2 == 1128874828 )
      {
        init_compression_memory(*(_QWORD *)(v2 + 32));
        return 1;
      }
LABEL_12:
      v1 = *(_QWORD *)(a1 + 88);
      *(_QWORD *)v1 = 8;
      goto LABEL_13;
    case 15:
      return 1;
  }
  v1 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)v1 = 5;
LABEL_13:
  *(_DWORD *)(v1 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180001ab8  sub     rsp, 28h
0x180001abc  movzx   edx, word ptr [rcx+2A4h]
0x180001ac3  xor     r8d, r8d
0x180001ac6  and     edx, 0Fh
0x180001ac9  jz      short loc_180001AFC
0x180001acb  sub     edx, 1
0x180001ace  jz      short loc_180001B06
0x180001ad0  sub     edx, 2
0x180001ad3  jz      short loc_180001AE7
0x180001ad5  cmp     edx, 0Ch
0x180001ad8  jz      short loc_180001AFC
0x180001ada  mov     rax, [rcx+58h]
0x180001ade  mov     qword ptr [rax], 5
0x180001ae5  jmp     short loc_180001B2F
0x180001ae7  mov     rax, [rcx+8]
0x180001aeb  cmp     dword ptr [rax], 4349434Ch
0x180001af1  jnz     short loc_180001B24
0x180001af3  mov     rcx, [rax+20h]
0x180001af7  call    init_compression_memory
0x180001afc  mov     eax, 1
0x180001b01  add     rsp, 28h
0x180001b05  retn
0x180001b06  mov     rax, [rcx+8]
0x180001b0a  cmp     dword ptr [rax], 4349434Dh
0x180001b10  jnz     short loc_180001B24
0x180001b12  mov     rax, [rax+18h]
0x180001b16  test    rax, rax
0x180001b19  jz      short loc_180001AFC
0x180001b1b  mov     [rax+2FD8h], r8b
0x180001b22  jmp     short loc_180001AFC
0x180001b24  mov     rax, [rcx+58h]
0x180001b28  mov     qword ptr [rax], 8
0x180001b2f  mov     dword ptr [rax+8], 1
0x180001b36  xor     eax, eax
0x180001b38  jmp     short loc_180001B01
```
