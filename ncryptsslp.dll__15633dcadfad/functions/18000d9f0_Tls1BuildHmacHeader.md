# Tls1BuildHmacHeader

- ea: `0x18000d9f0`
- end: `0x18000da94`
- name: `Tls1BuildHmacHeader`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d6cc`

## callees

- `0x18000b654`
- `0x18000d9f0`

## string_xrefs

- `0x18000da75`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1BuildHmacHeader(__int64 a1, char a2, __int16 a3, __int16 a4, _BYTE *a5)
{
  if ( a5 )
  {
    *a5 = HIBYTE(a1);
    a5[1] = BYTE6(a1);
    a5[2] = BYTE5(a1);
    a5[3] = BYTE4(a1);
    a5[4] = BYTE3(a1);
    a5[5] = BYTE2(a1);
    a5[6] = BYTE1(a1);
    a5[9] = HIBYTE(a3);
    a5[11] = HIBYTE(a4);
    a5[7] = a1;
    a5[8] = a2;
    a5[10] = a3;
    a5[12] = a4;
    return 0;
  }
  else
  {
    DebugTraceError(87, "ERROR_INVALID_PARAMETER", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 225);
    return 87;
  }
}

```

## disassembly

```asm
0x18000d9f0  sub     rsp, 28h
0x18000d9f4  mov     rax, [rsp+28h+arg_20]
0x18000d9f9  mov     r10, rcx
0x18000d9fc  test    rax, rax
0x18000d9ff  jz      short loc_18000DA6F
0x18000da01  shr     rcx, 38h
0x18000da05  mov     [rax], cl
0x18000da07  mov     rcx, r10
0x18000da0a  shr     rcx, 30h
0x18000da0e  mov     [rax+1], cl
0x18000da11  mov     rcx, r10
0x18000da14  shr     rcx, 28h
0x18000da18  mov     [rax+2], cl
0x18000da1b  mov     rcx, r10
0x18000da1e  shr     rcx, 20h
0x18000da22  mov     [rax+3], cl
0x18000da25  mov     rcx, r10
0x18000da28  shr     rcx, 18h
0x18000da2c  mov     [rax+4], cl
0x18000da2f  mov     rcx, r10
0x18000da32  shr     rcx, 10h
0x18000da36  mov     [rax+5], cl
0x18000da39  mov     rcx, r10
0x18000da3c  shr     rcx, 8
0x18000da40  mov     [rax+6], cl
0x18000da43  movzx   ecx, r8w
0x18000da47  shr     cx, 8
0x18000da4b  mov     [rax+9], cl
0x18000da4e  movzx   ecx, r9w
0x18000da52  shr     cx, 8
0x18000da56  mov     [rax+0Bh], cl
0x18000da59  mov     [rax+7], r10b
0x18000da5d  mov     [rax+8], dl
0x18000da60  mov     [rax+0Ah], r8b
0x18000da64  mov     [rax+0Ch], r9b
0x18000da68  xor     eax, eax
0x18000da6a  add     rsp, 28h
0x18000da6e  retn
0x18000da6f  mov     r9d, 0E1h
0x18000da75  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da7c  lea     rdx, g_rgbPad1+30h; "ERROR_INVALID_PARAMETER"
0x18000da83  mov     ecx, 57h ; 'W'
0x18000da88  call    DebugTraceError
0x18000da8d  mov     eax, 57h ; 'W'
0x18000da92  jmp     short loc_18000DA6A
```
