# CVoice::CVoice(void)

- ea: `0x18000acd0`
- end: `0x18000b060`
- name: `??0CVoice@@QEAA@XZ`
- size: `912`
- prototype: `CVoice *__fastcall(CVoice *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a70`
- `0x1800060d0`

## callees

- `0x180001d52`

## pseudocode

```c
CVoice *__fastcall CVoice::CVoice(CVoice *this)
{
  double v2; // xmm6_8
  double v3; // xmm0_8
  CVoice *result; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_WORD *)this + 20) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_WORD *)this + 56) = 0;
  *((_WORD *)this + 59) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_WORD *)this + 69) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_WORD *)this + 96) = 0;
  *((_WORD *)this + 99) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_WORD *)this + 109) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_DWORD *)this + 64) = 0;
  *((_DWORD *)this + 71) = 0;
  *((_WORD *)this + 136) = 0;
  *((_BYTE *)this + 280) = 0;
  *((_QWORD *)this + 38) = 0;
  *(_QWORD *)((char *)this + 316) = 0;
  *(_QWORD *)((char *)this + 324) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 83) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *(_QWORD *)((char *)this + 388) = 0;
  *((_DWORD *)this + 2) = 3804;
  *((_DWORD *)this + 20) = 1;
  *(_DWORD *)((char *)this + 114) = 65536000;
  *((_DWORD *)this + 40) = 1;
  *(_DWORD *)((char *)this + 194) = 65536000;
  *((_DWORD *)this + 60) = 1;
  *(_QWORD *)((char *)this + 260) = 1;
  *((_DWORD *)this + 67) = 22050;
  *(_WORD *)((char *)this + 281) = 15361;
  v2 = o_log_0(50.11363636363637);
  v3 = o_log_0(2.0);
  *(_DWORD *)((char *)this + 610) = 0x7FFF;
  *((_WORD *)this + 307) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_WORD *)this + 304) = (int)(v2 / v3 * 1200.0 + 6900.0);
  *((_QWORD *)this + 81) = 0;
  *((_DWORD *)this + 164) = 3804;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_WORD *)this + 344) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_DWORD *)this + 182) = 1;
  *((_DWORD *)this + 185) = 0;
  *((_DWORD *)this + 186) = 1;
  *((_DWORD *)this + 187) = 64;
  *((_DWORD *)this + 188) = 65;
  *((_DWORD *)this + 184) = 4;
  *((_QWORD *)this + 66) = 0x7FFFFFFFFFFFFFFFLL;
  result = this;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 145) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_DWORD *)this + 142) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 217) = 0;
  *(_QWORD *)((char *)this + 1132) = 0;
  *(_QWORD *)((char *)this + 876) = 0;
  *(_QWORD *)((char *)this + 1140) = 0;
  *(_QWORD *)((char *)this + 884) = 0;
  *(_QWORD *)((char *)this + 1148) = 0;
  *(_QWORD *)((char *)this + 892) = 0;
  *(_QWORD *)((char *)this + 1156) = 0;
  *(_QWORD *)((char *)this + 900) = 0;
  *(_QWORD *)((char *)this + 1164) = 0;
  *(_QWORD *)((char *)this + 908) = 0;
  *(_QWORD *)((char *)this + 1172) = 0;
  *(_QWORD *)((char *)this + 916) = 0;
  *(_QWORD *)((char *)this + 1180) = 0;
  *(_QWORD *)((char *)this + 924) = 0;
  *(_QWORD *)((char *)this + 1188) = 0;
  *(_QWORD *)((char *)this + 932) = 0;
  *(_QWORD *)((char *)this + 1196) = 0;
  *(_QWORD *)((char *)this + 940) = 0;
  *(_QWORD *)((char *)this + 1204) = 0;
  *(_QWORD *)((char *)this + 948) = 0;
  *(_QWORD *)((char *)this + 1212) = 0;
  *(_QWORD *)((char *)this + 956) = 0;
  *(_QWORD *)((char *)this + 1220) = 0;
  *(_QWORD *)((char *)this + 964) = 0;
  *(_QWORD *)((char *)this + 1228) = 0;
  *(_QWORD *)((char *)this + 972) = 0;
  *(_QWORD *)((char *)this + 1236) = 0;
  *(_QWORD *)((char *)this + 980) = 0;
  *(_QWORD *)((char *)this + 1244) = 0;
  *(_QWORD *)((char *)this + 988) = 0;
  *(_QWORD *)((char *)this + 1252) = 0;
  *(_QWORD *)((char *)this + 996) = 0;
  return result;
}

```

## disassembly

```asm
0x18000acd0  mov     [rsp+arg_0], rbx
0x18000acd5  push    rdi
0x18000acd6  sub     rsp, 30h
0x18000acda  xor     edi, edi
0x18000acdc  movsd   xmm0, cs:__real@40490e8ba2e8ba2f; X
0x18000ace4  mov     [rcx], rdi
0x18000ace7  mov     rbx, rcx
0x18000acea  mov     [rcx+10h], rdi
0x18000acee  mov     [rcx+18h], rdi
0x18000acf2  mov     [rcx+20h], rdi
0x18000acf6  mov     [rcx+28h], di
0x18000acfa  mov     [rcx+38h], rdi
0x18000acfe  mov     [rcx+48h], rdi
0x18000ad02  mov     [rcx+58h], rdi
0x18000ad06  mov     [rcx+60h], rdi
0x18000ad0a  mov     [rcx+68h], rdi
0x18000ad0e  mov     [rcx+70h], di
0x18000ad12  mov     [rcx+76h], di
0x18000ad16  mov     [rcx+78h], rdi
0x18000ad1a  mov     [rcx+80h], rdi
0x18000ad21  mov     [rcx+8Ah], di
0x18000ad28  mov     [rcx+98h], rdi
0x18000ad2f  mov     [rcx+0A8h], rdi
0x18000ad36  mov     [rcx+0B0h], rdi
0x18000ad3d  mov     [rcx+0B8h], rdi
0x18000ad44  movaps  [rsp+38h+var_18], xmm6
0x18000ad49  mov     [rcx+0C0h], di
0x18000ad50  mov     [rcx+0C6h], di
0x18000ad57  mov     [rcx+0C8h], rdi
0x18000ad5e  mov     [rcx+0D0h], rdi
0x18000ad65  mov     [rcx+0DAh], di
0x18000ad6c  mov     [rcx+0E8h], rdi
0x18000ad73  mov     [rcx+0F8h], rdi
0x18000ad7a  mov     [rcx+100h], edi
0x18000ad80  mov     [rcx+11Ch], edi
0x18000ad86  mov     [rcx+110h], di
0x18000ad8d  mov     [rcx+118h], dil
0x18000ad94  mov     [rcx+130h], rdi
0x18000ad9b  mov     [rcx+13Ch], rdi
0x18000ada2  mov     [rcx+144h], rdi
0x18000ada9  mov     [rcx+138h], edi
0x18000adaf  mov     [rcx+150h], rdi
0x18000adb6  mov     [rcx+158h], rdi
0x18000adbd  mov     [rcx+160h], rdi
0x18000adc4  mov     [rcx+168h], rdi
0x18000adcb  mov     [rcx+14Ch], edi
0x18000add1  mov     [rcx+190h], rdi
0x18000add8  mov     [rcx+198h], rdi
0x18000addf  mov     [rcx+1A0h], rdi
0x18000ade6  mov     [rcx+184h], rdi
0x18000aded  mov     dword ptr [rcx+8], 0EDCh
0x18000adf4  mov     dword ptr [rcx+50h], 1
0x18000adfb  mov     dword ptr [rcx+72h], 3E80000h
0x18000ae02  mov     dword ptr [rcx+0A0h], 1
0x18000ae0c  mov     dword ptr [rcx+0C2h], 3E80000h
0x18000ae16  mov     dword ptr [rcx+0F0h], 1
0x18000ae20  mov     qword ptr [rcx+104h], 1
0x18000ae2b  mov     dword ptr [rcx+10Ch], 5622h
0x18000ae35  mov     word ptr [rcx+119h], 3C01h
0x18000ae3e  call    _o_log_0
0x18000ae43  movaps  xmm6, xmm0
0x18000ae46  movsd   xmm0, cs:__real@4000000000000000; X
0x18000ae4e  call    _o_log_0
0x18000ae53  mov     dword ptr [rbx+262h], 7FFFh
0x18000ae5d  mov     [rbx+266h], di
0x18000ae64  mov     [rbx+268h], rdi
0x18000ae6b  divsd   xmm6, xmm0
0x18000ae6f  mulsd   xmm6, cs:__real@4092c00000000000
0x18000ae77  addsd   xmm6, cs:__real@40baf40000000000
0x18000ae7f  cvttsd2si eax, xmm6
0x18000ae83  mov     [rbx+260h], ax
0x18000ae8a  mov     [rbx+288h], rdi
0x18000ae91  mov     dword ptr [rbx+290h], 0EDCh
0x18000ae9b  mov     [rbx+298h], rdi
0x18000aea2  mov     [rbx+2A0h], rdi
0x18000aea9  mov     [rbx+2A8h], rdi
0x18000aeb0  mov     [rbx+2B0h], di
0x18000aeb7  mov     [rbx+2C0h], rdi
0x18000aebe  mov     [rbx+2D0h], rdi
0x18000aec5  mov     dword ptr [rbx+2D8h], 1
0x18000aecf  mov     [rbx+2E4h], edi
0x18000aed5  mov     dword ptr [rbx+2E8h], 1
0x18000aedf  mov     dword ptr [rbx+2ECh], 40h ; '@'
0x18000aee9  mov     dword ptr [rbx+2F0h], 41h ; 'A'
0x18000aef3  mov     dword ptr [rbx+2E0h], 4
0x18000aefd  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000af07  mov     [rbx+210h], rax
0x18000af0e  mov     rax, rbx
0x18000af11  mov     [rbx+248h], rdi
0x18000af18  mov     [rbx+1A8h], rdi
0x18000af1f  mov     [rbx+1B0h], rdi
0x18000af26  mov     [rbx+244h], edi
0x18000af2c  mov     [rbx+230h], rdi
0x18000af33  mov     [rbx+220h], rdi
0x18000af3a  mov     [rbx+228h], rdi
0x18000af41  mov     [rbx+208h], rdi
0x18000af48  mov     [rbx+218h], rdi
0x18000af4f  mov     [rbx+238h], edi
0x18000af55  mov     [rbx+258h], rdi
0x18000af5c  mov     [rbx+1C8h], rdi
0x18000af63  mov     [rbx+1D0h], rdi
0x18000af6a  mov     [rbx+364h], edi
0x18000af70  movaps  xmm6, [rsp+38h+var_18]
0x18000af75  mov     [rbx+46Ch], rdi
0x18000af7c  mov     [rbx+36Ch], rdi
0x18000af83  mov     [rbx+474h], rdi
0x18000af8a  mov     [rbx+374h], rdi
0x18000af91  mov     [rbx+47Ch], rdi
0x18000af98  mov     [rbx+37Ch], rdi
0x18000af9f  mov     [rbx+484h], rdi
0x18000afa6  mov     [rbx+384h], rdi
0x18000afad  mov     [rbx+48Ch], rdi
0x18000afb4  mov     [rbx+38Ch], rdi
0x18000afbb  mov     [rbx+494h], rdi
0x18000afc2  mov     [rbx+394h], rdi
0x18000afc9  mov     [rbx+49Ch], rdi
0x18000afd0  mov     [rbx+39Ch], rdi
0x18000afd7  mov     [rbx+4A4h], rdi
0x18000afde  mov     [rbx+3A4h], rdi
0x18000afe5  mov     [rbx+4ACh], rdi
0x18000afec  mov     [rbx+3ACh], rdi
0x18000aff3  mov     [rbx+4B4h], rdi
0x18000affa  mov     [rbx+3B4h], rdi
0x18000b001  mov     [rbx+4BCh], rdi
0x18000b008  mov     [rbx+3BCh], rdi
0x18000b00f  mov     [rbx+4C4h], rdi
0x18000b016  mov     [rbx+3C4h], rdi
0x18000b01d  mov     [rbx+4CCh], rdi
0x18000b024  mov     [rbx+3CCh], rdi
0x18000b02b  mov     [rbx+4D4h], rdi
0x18000b032  mov     [rbx+3D4h], rdi
0x18000b039  mov     [rbx+4DCh], rdi
0x18000b040  mov     [rbx+3DCh], rdi
0x18000b047  mov     [rbx+4E4h], rdi
0x18000b04e  mov     [rbx+3E4h], rdi
0x18000b055  mov     rbx, [rsp+38h+arg_0]
0x18000b05a  add     rsp, 30h
0x18000b05e  pop     rdi
0x18000b05f  retn
```
