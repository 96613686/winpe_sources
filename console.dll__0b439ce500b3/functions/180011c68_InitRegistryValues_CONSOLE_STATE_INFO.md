# InitRegistryValues(_CONSOLE_STATE_INFO *)

- ea: `0x180011c68`
- end: `0x180011ea4`
- name: `?InitRegistryValues@@YAXPEAU_CONSOLE_STATE_INFO@@@Z`
- size: `572`
- prototype: `void __fastcall(struct _CONSOLE_STATE_INFO *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000752c`
- `0x180013ce0`

## pseudocode

```c
void __fastcall InitRegistryValues(struct _CONSOLE_STATE_INFO *a1)
{
  int v1; // edx
  int v2; // eax

  *((_DWORD *)a1 + 25) = 16056327;
  *(_WORD *)a1 = 80;
  v1 = *((_DWORD *)a1 + 53);
  *(_DWORD *)((char *)a1 + 2) = 5242905;
  v2 = *((_DWORD *)a1 + 24);
  *((_WORD *)a1 + 3) = 25;
  *((_DWORD *)a1 + 23) = 25;
  *((_DWORD *)a1 + 26) = 25;
  *((_DWORD *)a1 + 24) = v2 & 0xFFFFFFE0 | 4;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_DWORD *)a1 + 6) = 0;
  *((_WORD *)a1 + 14) = 0;
  *((_DWORD *)a1 + 27) = 4;
  *((_DWORD *)a1 + 28) = v1 != 0 ? 0xC0C0C : 0;
  *((_DWORD *)a1 + 29) = v1 != 0 ? 14300928 : 0x800000;
  *((_DWORD *)a1 + 30) = v1 != 0 ? 958739 : 0x8000;
  *((_DWORD *)a1 + 31) = v1 != 0 ? 14521914 : 8421376;
  *((_DWORD *)a1 + 32) = v1 != 0 ? 2035653 : 128;
  *((_DWORD *)a1 + 33) = v1 != 0 ? 9967496 : 8388736;
  *((_DWORD *)a1 + 34) = v1 != 0 ? 40129 : 32896;
  *((_DWORD *)a1 + 35) = v1 != 0 ? 13421772 : 12632256;
  *((_DWORD *)a1 + 36) = v1 != 0 ? 7763574 : 8421504;
  *((_DWORD *)a1 + 37) = v1 != 0 ? 16742459 : 16711680;
  *((_DWORD *)a1 + 38) = v1 != 0 ? 837142 : 65280;
  *((_DWORD *)a1 + 39) = v1 != 0 ? 14079585 : 16776960;
  *((_DWORD *)a1 + 40) = v1 != 0 ? 5654759 : 255;
  *((_DWORD *)a1 + 41) = v1 != 0 ? 10354868 : 16711935;
  *((_DWORD *)a1 + 42) = v1 != 0 ? 10875385 : 0xFFFF;
  *((_DWORD *)a1 + 43) = v1 != 0 ? 15921906 : 0xFFFFFF;
  *((_DWORD *)a1 + 52) = OEMCP;
  *((_DWORD *)a1 + 54) = 1;
  *(_QWORD *)((char *)a1 + 220) = 1;
  *((_DWORD *)a1 + 57) = 1;
  *((_DWORD *)a1 + 61) = -1;
  *((_DWORD *)a1 + 63) = -1;
  *((_DWORD *)a1 + 64) = -1;
  *((_QWORD *)a1 + 22) = 0;
  *((_QWORD *)a1 + 24) = 0;
  *((_QWORD *)a1 + 25) = 0;
  *((_BYTE *)a1 + 232) = -1;
  *((_DWORD *)a1 + 60) = 0;
  *((_DWORD *)a1 + 62) = 0;
}

```

## disassembly

```asm
0x180011c68  mov     r8, rcx
0x180011c6b  mov     dword ptr [rcx+64h], 0F50007h
0x180011c72  xor     r10d, r10d
0x180011c75  mov     eax, 50h ; 'P'
0x180011c7a  mov     [rcx], ax
0x180011c7d  mov     r9d, 0C0C0Ch
0x180011c83  mov     edx, [r8+0D4h]
0x180011c8a  lea     ecx, [rax-37h]
0x180011c8d  mov     dword ptr [r8+2], 500019h
0x180011c95  mov     eax, [r8+60h]
0x180011c99  mov     [r8+6], cx
0x180011c9e  and     eax, 0FFFFFFE4h
0x180011ca1  mov     [r8+5Ch], ecx
0x180011ca5  or      eax, 4
0x180011ca8  mov     [r8+68h], ecx
0x180011cac  mov     [r8+60h], eax
0x180011cb0  mov     eax, edx
0x180011cb2  neg     eax
0x180011cb4  mov     [r8+8], r10
0x180011cb8  mov     [r8+10h], r10
0x180011cbc  mov     eax, edx
0x180011cbe  sbb     ecx, ecx
0x180011cc0  mov     [r8+18h], r10d
0x180011cc4  and     ecx, r9d
0x180011cc7  mov     [r8+1Ch], r10w
0x180011ccc  neg     eax
0x180011cce  mov     dword ptr [r8+6Ch], 4
0x180011cd6  mov     [r8+70h], ecx
0x180011cda  mov     eax, edx
0x180011cdc  sbb     ecx, ecx
0x180011cde  and     ecx, 5A3700h
0x180011ce4  add     ecx, 800000h
0x180011cea  mov     [r8+74h], ecx
0x180011cee  neg     eax
0x180011cf0  mov     eax, edx
0x180011cf2  sbb     ecx, ecx
0x180011cf4  and     ecx, 0E2113h
0x180011cfa  add     ecx, 8000h
0x180011d00  mov     [r8+78h], ecx
0x180011d04  neg     eax
0x180011d06  mov     eax, edx
0x180011d08  sbb     ecx, ecx
0x180011d0a  and     ecx, 5D163Ah
0x180011d10  add     ecx, 808000h
0x180011d16  mov     [r8+7Ch], ecx
0x180011d1a  neg     eax
0x180011d1c  mov     eax, edx
0x180011d1e  sbb     ecx, ecx
0x180011d20  and     ecx, 1F0F45h
0x180011d26  sub     ecx, 0FFFFFF80h
0x180011d29  mov     [r8+80h], ecx
0x180011d30  neg     eax
0x180011d32  mov     eax, edx
0x180011d34  sbb     ecx, ecx
0x180011d36  and     ecx, 181708h
0x180011d3c  add     ecx, 800080h
0x180011d42  mov     [r8+84h], ecx
0x180011d49  neg     eax
0x180011d4b  mov     eax, edx
0x180011d4d  sbb     ecx, ecx
0x180011d4f  and     ecx, 1C41h
0x180011d55  add     ecx, 8080h
0x180011d5b  mov     [r8+88h], ecx
0x180011d62  neg     eax
0x180011d64  mov     eax, edx
0x180011d66  sbb     ecx, ecx
0x180011d68  and     ecx, r9d
0x180011d6b  add     ecx, 0C0C0C0h
0x180011d71  mov     [r8+8Ch], ecx
0x180011d78  neg     eax
0x180011d7a  mov     eax, edx
0x180011d7c  sbb     ecx, ecx
0x180011d7e  and     ecx, 0FFF5F5F6h
0x180011d84  add     ecx, 808080h
0x180011d8a  mov     [r8+90h], ecx
0x180011d91  neg     eax
0x180011d93  mov     eax, edx
0x180011d95  sbb     ecx, ecx
0x180011d97  and     ecx, 783Bh
0x180011d9d  add     ecx, 0FF0000h
0x180011da3  mov     [r8+94h], ecx
0x180011daa  neg     eax
0x180011dac  mov     eax, edx
0x180011dae  sbb     ecx, ecx
0x180011db0  and     ecx, 0BC716h
0x180011db6  add     ecx, 0FF00h
0x180011dbc  mov     [r8+98h], ecx
0x180011dc3  neg     eax
0x180011dc5  mov     eax, edx
0x180011dc7  sbb     ecx, ecx
0x180011dc9  and     ecx, 0FFD6D761h
0x180011dcf  add     ecx, 0FFFF00h
0x180011dd5  mov     [r8+9Ch], ecx
0x180011ddc  neg     eax
0x180011dde  mov     eax, edx
0x180011de0  sbb     ecx, ecx
0x180011de2  and     ecx, 5647E8h
0x180011de8  add     ecx, 0FFh
0x180011dee  mov     [r8+0A0h], ecx
0x180011df5  neg     eax
0x180011df7  mov     eax, edx
0x180011df9  sbb     ecx, ecx
0x180011dfb  and     ecx, 0FF9EFFB5h
0x180011e01  add     ecx, 0FF00FFh
0x180011e07  mov     [r8+0A4h], ecx
0x180011e0e  neg     eax
0x180011e10  sbb     ecx, ecx
0x180011e12  and     ecx, 0A4F1FAh
0x180011e18  add     ecx, 0FFFFh
0x180011e1e  mov     [r8+0A8h], ecx
0x180011e25  neg     edx
0x180011e27  sbb     eax, eax
0x180011e29  and     eax, 0FFF2F2F3h
0x180011e2e  add     eax, 0FFFFFFh
0x180011e33  mov     [r8+0ACh], eax
0x180011e3a  mov     eax, cs:?OEMCP@@3IA; uint OEMCP
0x180011e40  mov     [r8+0D0h], eax
0x180011e47  lea     eax, [r10+1]
0x180011e4b  mov     [r8+0D8h], eax
0x180011e52  mov     [r8+0DCh], rax
0x180011e59  mov     [r8+0E4h], eax
0x180011e60  or      eax, 0FFFFFFFFh
0x180011e63  mov     [r8+0F4h], eax
0x180011e6a  mov     [r8+0FCh], eax
0x180011e71  mov     [r8+100h], eax
0x180011e78  mov     [r8+0B0h], r10
0x180011e7f  mov     [r8+0C0h], r10
0x180011e86  mov     [r8+0C8h], r10
0x180011e8d  mov     byte ptr [r8+0E8h], 0FFh
0x180011e95  mov     [r8+0F0h], r10d
0x180011e9c  mov     [r8+0F8h], r10d
0x180011ea3  retn
```
