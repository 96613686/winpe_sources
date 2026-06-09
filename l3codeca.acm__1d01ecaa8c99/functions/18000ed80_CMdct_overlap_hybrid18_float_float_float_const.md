# CMdct::overlap_hybrid18(float *,float *,float const *)

- ea: `0x18000ed80`
- end: `0x18000f1c1`
- name: `?overlap_hybrid18@CMdct@@IEAAXPEAM0PEBM@Z`
- size: `1089`
- prototype: `void __fastcall(CMdct *__hidden this, float *, float *, const float *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e200`

## pseudocode

```c
void __fastcall CMdct::overlap_hybrid18(CMdct *this, float *a2, float *a3, const float *a4)
{
  *a3 = (float)((float)(*((float *)this + 44) - *((float *)this + 53)) * *a4) + *a2;
  a3[17] = (float)((float)(*((float *)this + 44) - *((float *)this + 53)) * a4[17]) + a2[17];
  *a2 = (float)(*((float *)this + 53) + *((float *)this + 44)) * a4[18];
  a2[17] = (float)(*((float *)this + 53) + *((float *)this + 44)) * a4[35];
  a3[1] = (float)((float)(*((float *)this + 43) - *((float *)this + 52)) * a4[1]) + a2[1];
  a3[16] = (float)((float)(*((float *)this + 43) - *((float *)this + 52)) * a4[16]) + a2[16];
  a2[1] = (float)(*((float *)this + 52) + *((float *)this + 43)) * a4[19];
  a2[16] = (float)(*((float *)this + 52) + *((float *)this + 43)) * a4[34];
  a3[2] = (float)((float)(*((float *)this + 42) - *((float *)this + 51)) * a4[2]) + a2[2];
  a3[15] = (float)((float)(*((float *)this + 42) - *((float *)this + 51)) * a4[15]) + a2[15];
  a2[2] = (float)(*((float *)this + 51) + *((float *)this + 42)) * a4[20];
  a2[15] = (float)(*((float *)this + 51) + *((float *)this + 42)) * a4[33];
  a3[3] = (float)((float)(*((float *)this + 41) - *((float *)this + 50)) * a4[3]) + a2[3];
  a3[14] = (float)((float)(*((float *)this + 41) - *((float *)this + 50)) * a4[14]) + a2[14];
  a2[3] = (float)(*((float *)this + 50) + *((float *)this + 41)) * a4[21];
  a2[14] = (float)(*((float *)this + 50) + *((float *)this + 41)) * a4[32];
  a3[4] = (float)((float)(*((float *)this + 40) - *((float *)this + 49)) * a4[4]) + a2[4];
  a3[13] = (float)((float)(*((float *)this + 40) - *((float *)this + 49)) * a4[13]) + a2[13];
  a2[4] = (float)(*((float *)this + 49) + *((float *)this + 40)) * a4[22];
  a2[13] = (float)(*((float *)this + 49) + *((float *)this + 40)) * a4[31];
  a3[5] = (float)((float)(*((float *)this + 39) - *((float *)this + 48)) * a4[5]) + a2[5];
  a3[12] = (float)((float)(*((float *)this + 39) - *((float *)this + 48)) * a4[12]) + a2[12];
  a2[5] = (float)(*((float *)this + 48) + *((float *)this + 39)) * a4[23];
  a2[12] = (float)(*((float *)this + 48) + *((float *)this + 39)) * a4[30];
  a3[6] = (float)((float)(*((float *)this + 38) - *((float *)this + 47)) * a4[6]) + a2[6];
  a3[11] = (float)((float)(*((float *)this + 38) - *((float *)this + 47)) * a4[11]) + a2[11];
  a2[6] = (float)(*((float *)this + 47) + *((float *)this + 38)) * a4[24];
  a2[11] = (float)(*((float *)this + 47) + *((float *)this + 38)) * a4[29];
  a3[7] = (float)((float)(*((float *)this + 37) - *((float *)this + 46)) * a4[7]) + a2[7];
  a3[10] = (float)((float)(*((float *)this + 37) - *((float *)this + 46)) * a4[10]) + a2[10];
  a2[7] = (float)(*((float *)this + 46) + *((float *)this + 37)) * a4[25];
  a2[10] = (float)(*((float *)this + 46) + *((float *)this + 37)) * a4[28];
  a3[8] = (float)((float)(*((float *)this + 36) - *((float *)this + 45)) * a4[8]) + a2[8];
  a3[9] = (float)((float)(*((float *)this + 36) - *((float *)this + 45)) * a4[9]) + a2[9];
  a2[8] = (float)(*((float *)this + 45) + *((float *)this + 36)) * a4[26];
  a2[9] = (float)(*((float *)this + 45) + *((float *)this + 36)) * a4[27];
}

```

## disassembly

```asm
0x18000ed80  movss   xmm0, dword ptr [rcx+0B0h]
0x18000ed88  subss   xmm0, dword ptr [rcx+0D4h]
0x18000ed90  mulss   xmm0, dword ptr [r9]
0x18000ed95  addss   xmm0, dword ptr [rdx]
0x18000ed99  movss   dword ptr [r8], xmm0
0x18000ed9e  movss   xmm1, dword ptr [rcx+0B0h]
0x18000eda6  subss   xmm1, dword ptr [rcx+0D4h]
0x18000edae  mulss   xmm1, dword ptr [r9+44h]
0x18000edb4  addss   xmm1, dword ptr [rdx+44h]
0x18000edb9  movss   dword ptr [r8+44h], xmm1
0x18000edbf  movss   xmm0, dword ptr [rcx+0D4h]
0x18000edc7  addss   xmm0, dword ptr [rcx+0B0h]
0x18000edcf  mulss   xmm0, dword ptr [r9+48h]
0x18000edd5  movss   dword ptr [rdx], xmm0
0x18000edd9  movss   xmm1, dword ptr [rcx+0D4h]
0x18000ede1  addss   xmm1, dword ptr [rcx+0B0h]
0x18000ede9  mulss   xmm1, dword ptr [r9+8Ch]
0x18000edf2  movss   dword ptr [rdx+44h], xmm1
0x18000edf7  movss   xmm0, dword ptr [rcx+0ACh]
0x18000edff  subss   xmm0, dword ptr [rcx+0D0h]
0x18000ee07  mulss   xmm0, dword ptr [r9+4]
0x18000ee0d  addss   xmm0, dword ptr [rdx+4]
0x18000ee12  movss   dword ptr [r8+4], xmm0
0x18000ee18  movss   xmm1, dword ptr [rcx+0ACh]
0x18000ee20  subss   xmm1, dword ptr [rcx+0D0h]
0x18000ee28  mulss   xmm1, dword ptr [r9+40h]
0x18000ee2e  addss   xmm1, dword ptr [rdx+40h]
0x18000ee33  movss   dword ptr [r8+40h], xmm1
0x18000ee39  movss   xmm0, dword ptr [rcx+0D0h]
0x18000ee41  addss   xmm0, dword ptr [rcx+0ACh]
0x18000ee49  mulss   xmm0, dword ptr [r9+4Ch]
0x18000ee4f  movss   dword ptr [rdx+4], xmm0
0x18000ee54  movss   xmm1, dword ptr [rcx+0D0h]
0x18000ee5c  addss   xmm1, dword ptr [rcx+0ACh]
0x18000ee64  mulss   xmm1, dword ptr [r9+88h]
0x18000ee6d  movss   dword ptr [rdx+40h], xmm1
0x18000ee72  movss   xmm0, dword ptr [rcx+0A8h]
0x18000ee7a  subss   xmm0, dword ptr [rcx+0CCh]
0x18000ee82  mulss   xmm0, dword ptr [r9+8]
0x18000ee88  addss   xmm0, dword ptr [rdx+8]
0x18000ee8d  movss   dword ptr [r8+8], xmm0
0x18000ee93  movss   xmm1, dword ptr [rcx+0A8h]
0x18000ee9b  subss   xmm1, dword ptr [rcx+0CCh]
0x18000eea3  mulss   xmm1, dword ptr [r9+3Ch]
0x18000eea9  addss   xmm1, dword ptr [rdx+3Ch]
0x18000eeae  movss   dword ptr [r8+3Ch], xmm1
0x18000eeb4  movss   xmm0, dword ptr [rcx+0CCh]
0x18000eebc  addss   xmm0, dword ptr [rcx+0A8h]
0x18000eec4  mulss   xmm0, dword ptr [r9+50h]
0x18000eeca  movss   dword ptr [rdx+8], xmm0
0x18000eecf  movss   xmm1, dword ptr [rcx+0CCh]
0x18000eed7  addss   xmm1, dword ptr [rcx+0A8h]
0x18000eedf  mulss   xmm1, dword ptr [r9+84h]
0x18000eee8  movss   dword ptr [rdx+3Ch], xmm1
0x18000eeed  movss   xmm0, dword ptr [rcx+0A4h]
0x18000eef5  subss   xmm0, dword ptr [rcx+0C8h]
0x18000eefd  mulss   xmm0, dword ptr [r9+0Ch]
0x18000ef03  addss   xmm0, dword ptr [rdx+0Ch]
0x18000ef08  movss   dword ptr [r8+0Ch], xmm0
0x18000ef0e  movss   xmm1, dword ptr [rcx+0A4h]
0x18000ef16  subss   xmm1, dword ptr [rcx+0C8h]
0x18000ef1e  mulss   xmm1, dword ptr [r9+38h]
0x18000ef24  addss   xmm1, dword ptr [rdx+38h]
0x18000ef29  movss   dword ptr [r8+38h], xmm1
0x18000ef2f  movss   xmm0, dword ptr [rcx+0C8h]
0x18000ef37  addss   xmm0, dword ptr [rcx+0A4h]
0x18000ef3f  mulss   xmm0, dword ptr [r9+54h]
0x18000ef45  movss   dword ptr [rdx+0Ch], xmm0
0x18000ef4a  movss   xmm1, dword ptr [rcx+0C8h]
0x18000ef52  addss   xmm1, dword ptr [rcx+0A4h]
0x18000ef5a  mulss   xmm1, dword ptr [r9+80h]
0x18000ef63  movss   dword ptr [rdx+38h], xmm1
0x18000ef68  movss   xmm0, dword ptr [rcx+0A0h]
0x18000ef70  subss   xmm0, dword ptr [rcx+0C4h]
0x18000ef78  mulss   xmm0, dword ptr [r9+10h]
0x18000ef7e  addss   xmm0, dword ptr [rdx+10h]
0x18000ef83  movss   dword ptr [r8+10h], xmm0
0x18000ef89  movss   xmm1, dword ptr [rcx+0A0h]
0x18000ef91  subss   xmm1, dword ptr [rcx+0C4h]
0x18000ef99  mulss   xmm1, dword ptr [r9+34h]
0x18000ef9f  addss   xmm1, dword ptr [rdx+34h]
0x18000efa4  movss   dword ptr [r8+34h], xmm1
0x18000efaa  movss   xmm0, dword ptr [rcx+0C4h]
0x18000efb2  addss   xmm0, dword ptr [rcx+0A0h]
0x18000efba  mulss   xmm0, dword ptr [r9+58h]
0x18000efc0  movss   dword ptr [rdx+10h], xmm0
0x18000efc5  movss   xmm1, dword ptr [rcx+0C4h]
0x18000efcd  addss   xmm1, dword ptr [rcx+0A0h]
0x18000efd5  mulss   xmm1, dword ptr [r9+7Ch]
0x18000efdb  movss   dword ptr [rdx+34h], xmm1
0x18000efe0  movss   xmm0, dword ptr [rcx+9Ch]
0x18000efe8  subss   xmm0, dword ptr [rcx+0C0h]
0x18000eff0  mulss   xmm0, dword ptr [r9+14h]
0x18000eff6  addss   xmm0, dword ptr [rdx+14h]
0x18000effb  movss   dword ptr [r8+14h], xmm0
0x18000f001  movss   xmm1, dword ptr [rcx+9Ch]
0x18000f009  subss   xmm1, dword ptr [rcx+0C0h]
0x18000f011  mulss   xmm1, dword ptr [r9+30h]
0x18000f017  addss   xmm1, dword ptr [rdx+30h]
0x18000f01c  movss   dword ptr [r8+30h], xmm1
0x18000f022  movss   xmm0, dword ptr [rcx+0C0h]
0x18000f02a  addss   xmm0, dword ptr [rcx+9Ch]
0x18000f032  mulss   xmm0, dword ptr [r9+5Ch]
0x18000f038  movss   dword ptr [rdx+14h], xmm0
0x18000f03d  movss   xmm1, dword ptr [rcx+0C0h]
0x18000f045  addss   xmm1, dword ptr [rcx+9Ch]
0x18000f04d  mulss   xmm1, dword ptr [r9+78h]
0x18000f053  movss   dword ptr [rdx+30h], xmm1
0x18000f058  movss   xmm0, dword ptr [rcx+98h]
0x18000f060  subss   xmm0, dword ptr [rcx+0BCh]
0x18000f068  mulss   xmm0, dword ptr [r9+18h]
0x18000f06e  addss   xmm0, dword ptr [rdx+18h]
0x18000f073  movss   dword ptr [r8+18h], xmm0
0x18000f079  movss   xmm1, dword ptr [rcx+98h]
0x18000f081  subss   xmm1, dword ptr [rcx+0BCh]
0x18000f089  mulss   xmm1, dword ptr [r9+2Ch]
0x18000f08f  addss   xmm1, dword ptr [rdx+2Ch]
0x18000f094  movss   dword ptr [r8+2Ch], xmm1
0x18000f09a  movss   xmm0, dword ptr [rcx+0BCh]
0x18000f0a2  addss   xmm0, dword ptr [rcx+98h]
0x18000f0aa  mulss   xmm0, dword ptr [r9+60h]
0x18000f0b0  movss   dword ptr [rdx+18h], xmm0
0x18000f0b5  movss   xmm1, dword ptr [rcx+0BCh]
0x18000f0bd  addss   xmm1, dword ptr [rcx+98h]
0x18000f0c5  mulss   xmm1, dword ptr [r9+74h]
0x18000f0cb  movss   dword ptr [rdx+2Ch], xmm1
0x18000f0d0  movss   xmm0, dword ptr [rcx+94h]
0x18000f0d8  subss   xmm0, dword ptr [rcx+0B8h]
0x18000f0e0  mulss   xmm0, dword ptr [r9+1Ch]
0x18000f0e6  addss   xmm0, dword ptr [rdx+1Ch]
0x18000f0eb  movss   dword ptr [r8+1Ch], xmm0
0x18000f0f1  movss   xmm1, dword ptr [rcx+94h]
0x18000f0f9  subss   xmm1, dword ptr [rcx+0B8h]
0x18000f101  mulss   xmm1, dword ptr [r9+28h]
0x18000f107  addss   xmm1, dword ptr [rdx+28h]
0x18000f10c  movss   dword ptr [r8+28h], xmm1
0x18000f112  movss   xmm0, dword ptr [rcx+0B8h]
0x18000f11a  addss   xmm0, dword ptr [rcx+94h]
0x18000f122  mulss   xmm0, dword ptr [r9+64h]
0x18000f128  movss   dword ptr [rdx+1Ch], xmm0
0x18000f12d  movss   xmm1, dword ptr [rcx+0B8h]
0x18000f135  addss   xmm1, dword ptr [rcx+94h]
0x18000f13d  mulss   xmm1, dword ptr [r9+70h]
0x18000f143  movss   dword ptr [rdx+28h], xmm1
0x18000f148  movss   xmm0, dword ptr [rcx+90h]
0x18000f150  subss   xmm0, dword ptr [rcx+0B4h]
0x18000f158  mulss   xmm0, dword ptr [r9+20h]
0x18000f15e  addss   xmm0, dword ptr [rdx+20h]
0x18000f163  movss   dword ptr [r8+20h], xmm0
0x18000f169  movss   xmm1, dword ptr [rcx+90h]
0x18000f171  subss   xmm1, dword ptr [rcx+0B4h]
0x18000f179  mulss   xmm1, dword ptr [r9+24h]
0x18000f17f  addss   xmm1, dword ptr [rdx+24h]
0x18000f184  movss   dword ptr [r8+24h], xmm1
0x18000f18a  movss   xmm0, dword ptr [rcx+0B4h]
0x18000f192  addss   xmm0, dword ptr [rcx+90h]
0x18000f19a  mulss   xmm0, dword ptr [r9+68h]
0x18000f1a0  movss   dword ptr [rdx+20h], xmm0
0x18000f1a5  movss   xmm1, dword ptr [rcx+0B4h]
0x18000f1ad  addss   xmm1, dword ptr [rcx+90h]
0x18000f1b5  mulss   xmm1, dword ptr [r9+6Ch]
0x18000f1bb  movss   dword ptr [rdx+24h], xmm1
0x18000f1c0  retn
```
