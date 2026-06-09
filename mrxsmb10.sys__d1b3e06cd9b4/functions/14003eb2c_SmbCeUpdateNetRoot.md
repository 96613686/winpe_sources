# SmbCeUpdateNetRoot

- ea: `0x14003eb2c`
- end: `0x14003ec34`
- name: `SmbCeUpdateNetRoot`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14000fee0`
- `0x1400522a0`

## callees

- `0x14003eb2c`

## import_xrefs

- `rdbss!RxUpdateNetRootCachingMode` at `0x14003ec20`
- `rdbss!RxUpdateNetRootCachingMode` at `0x14003ec20`

## pseudocode

```c
__int64 __fastcall SmbCeUpdateNetRoot(__int64 a1, __int64 a2)
{
  __int16 v2; // r9
  char v4; // dl
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  int v8; // eax
  unsigned int v9; // edx
  int v10; // r9d

  v2 = *(_WORD *)(a1 + 160);
  v4 = *(_BYTE *)(a1 + 105);
  if ( v4 != 4 )
    *(_BYTE *)(a2 + 77) = v4;
  if ( *(_BYTE *)(a2 + 77) )
  {
    switch ( *(_BYTE *)(a2 + 77) )
    {
      case 1:
        v6 = RdrConfigurationBlock;
        *(_DWORD *)(a2 + 80) = 17;
        *(_DWORD *)(a2 + 108) = *(_DWORD *)(v6 + 124);
        *(_DWORD *)(a2 + 112) = *(_DWORD *)(v6 + 128);
        break;
      case 2:
        *(_DWORD *)(a2 + 80) = 27;
        break;
      case 3:
        *(_DWORD *)(a2 + 80) = 24;
        break;
    }
  }
  else
  {
    v7 = (_DWORD *)RdrConfigurationBlock;
    *(_DWORD *)(a2 + 80) = 7;
    *(_DWORD *)(a2 + 116) = v7[29];
    *(_DWORD *)(a2 + 120) = v7[30];
    v8 = v7[43];
    if ( v8 )
    {
      *(_DWORD *)(a2 + 108) = v8;
      *(_DWORD *)(a2 + 112) = 0x8000;
    }
  }
  v9 = *(_DWORD *)(a2 + 56) | 2;
  if ( !*(_BYTE *)(a1 + 104) )
    v9 = *(_DWORD *)(a2 + 56) & 0xFFFFFFFD;
  *(_DWORD *)(a2 + 56) = v9;
  if ( (v2 & 0x10) != 0 )
    *(_DWORD *)(a2 + 56) = v9 | 0x20;
  v10 = v2 & 0xC;
  if ( !v10 || v10 == 4 || v10 == 8 || v10 == 12 )
    RxUpdateNetRootCachingMode(a2);
  return 0;
}

```

## disassembly

```asm
0x14003eb2c  sub     rsp, 28h
0x14003eb30  movzx   r9d, word ptr [rcx+0A0h]
0x14003eb38  mov     r8, rdx
0x14003eb3b  mov     dl, [rcx+69h]
0x14003eb3e  mov     r10, rcx
0x14003eb41  cmp     dl, 4
0x14003eb44  jz      short loc_14003EB4A
0x14003eb46  mov     [r8+4Dh], dl
0x14003eb4a  movzx   ecx, byte ptr [r8+4Dh]
0x14003eb4f  test    ecx, ecx
0x14003eb51  jz      short loc_14003EB98
0x14003eb53  sub     ecx, 1
0x14003eb56  jz      short loc_14003EB76
0x14003eb58  sub     ecx, 1
0x14003eb5b  jz      short loc_14003EB6C
0x14003eb5d  cmp     ecx, 1
0x14003eb60  jnz     short loc_14003EBCB
0x14003eb62  mov     dword ptr [r8+50h], 18h
0x14003eb6a  jmp     short loc_14003EBCB
0x14003eb6c  mov     dword ptr [r8+50h], 1Bh
0x14003eb74  jmp     short loc_14003EBCB
0x14003eb76  mov     rcx, cs:RdrConfigurationBlock
0x14003eb7d  mov     dword ptr [r8+50h], 11h
0x14003eb85  mov     eax, [rcx+7Ch]
0x14003eb88  mov     [r8+6Ch], eax
0x14003eb8c  mov     eax, [rcx+80h]
0x14003eb92  mov     [r8+70h], eax
0x14003eb96  jmp     short loc_14003EBCB
0x14003eb98  mov     rcx, cs:RdrConfigurationBlock
0x14003eb9f  mov     dword ptr [r8+50h], 7
0x14003eba7  mov     eax, [rcx+74h]
0x14003ebaa  mov     [r8+74h], eax
0x14003ebae  mov     eax, [rcx+78h]
0x14003ebb1  mov     [r8+78h], eax
0x14003ebb5  mov     eax, [rcx+0ACh]
0x14003ebbb  test    eax, eax
0x14003ebbd  jz      short loc_14003EBCB
0x14003ebbf  mov     [r8+6Ch], eax
0x14003ebc3  mov     dword ptr [r8+70h], 8000h
0x14003ebcb  mov     edx, [r8+38h]
0x14003ebcf  mov     ecx, edx
0x14003ebd1  and     ecx, 0FFFFFFFDh
0x14003ebd4  or      edx, 2
0x14003ebd7  cmp     byte ptr [r10+68h], 0
0x14003ebdc  cmovz   edx, ecx
0x14003ebdf  mov     [r8+38h], edx
0x14003ebe3  test    r9b, 10h
0x14003ebe7  jz      short loc_14003EBF0
0x14003ebe9  or      edx, 20h
0x14003ebec  mov     [r8+38h], edx
0x14003ebf0  mov     edx, 0Ch
0x14003ebf5  and     r9d, edx
0x14003ebf8  jz      short loc_14003EC1B
0x14003ebfa  cmp     r9d, 4
0x14003ebfe  jz      short loc_14003EC14
0x14003ec00  cmp     r9d, 8
0x14003ec04  jz      short loc_14003EC0D
0x14003ec06  cmp     r9d, edx
0x14003ec09  jnz     short loc_14003EC2C
0x14003ec0b  jmp     short loc_14003EC1D
0x14003ec0d  mov     edx, 8
0x14003ec12  jmp     short loc_14003EC1D
0x14003ec14  mov     edx, 4
0x14003ec19  jmp     short loc_14003EC1D
0x14003ec1b  xor     edx, edx
0x14003ec1d  mov     rcx, r8
0x14003ec20  call    cs:__imp_RxUpdateNetRootCachingMode
0x14003ec27  nop     dword ptr [rax+rax+00h]
0x14003ec2c  xor     eax, eax
0x14003ec2e  add     rsp, 28h
0x14003ec32  retn
```
