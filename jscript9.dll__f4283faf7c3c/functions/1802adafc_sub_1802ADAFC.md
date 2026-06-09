# sub_1802ADAFC

- ea: `0x1802adafc`
- end: `0x1802ade88`
- name: `sub_1802ADAFC`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1802032c4`

## callees

- `0x18000b704`
- `0x18007f5e0`
- `0x1800a550c`
- `0x18010e564`
- `0x18016cf40`
- `0x180170044`
- `0x18018ed14`
- `0x1801a2648`
- `0x1801a6cdc`
- `0x1801aad04`
- `0x1802ad50c`
- `0x1802ad53c`
- `0x1802ad56c`
- `0x1802ad59c`
- `0x1802adafc`
- `0x1802ade90`
- `0x1802adeec`

## import_xrefs

- `msvcrt!free` at `0x1802adbb5`
- `msvcrt!free` at `0x1802adc72`
- `msvcrt!free` at `0x1802adc91`
- `msvcrt!free` at `0x1802adcb1`
- `msvcrt!free` at `0x1802adbb5`
- `msvcrt!free` at `0x1802adc72`
- `msvcrt!free` at `0x1802adc91`
- `msvcrt!free` at `0x1802adcb1`
- `KERNEL32!DeleteCriticalSection` at `0x1802add6e`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade12`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade6a`
- `KERNEL32!DeleteCriticalSection` at `0x1802add6e`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade12`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade6a`
- `KERNEL32!EnterCriticalSection` at `0x1802adb33`
- `KERNEL32!EnterCriticalSection` at `0x1802adb33`
- `KERNEL32!LeaveCriticalSection` at `0x1802adba2`
- `KERNEL32!LeaveCriticalSection` at `0x1802adba2`
- `ADVAPI32!CryptReleaseContext` at `0x1802add41`
- `ADVAPI32!CryptReleaseContext` at `0x1802add41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall sub_1802ADAFC(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rax
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx
  _QWORD *v10; // rsi
  _QWORD *i; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // rsi
  _QWORD *j; // rcx
  _QWORD *v15; // rbx
  HCRYPTPROV v16; // rcx

  *(_QWORD *)a1 = off_18036C878;
  EnterCriticalSection(&CriticalSection);
  v2 = *(_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 16);
  if ( v2 )
  {
    *(_QWORD *)(v2 + 8) = v3;
  }
  else if ( v3 )
  {
    qword_18043D9D8 = v3 - 8;
  }
  else
  {
    qword_18043D9D8 = 0;
  }
  v4 = *(_QWORD **)(a1 + 16);
  v5 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    *v4 = v5;
  }
  else if ( v5 )
  {
    qword_18043D9C8 = v5 - 8;
  }
  else
  {
    qword_18043D9C8 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  LeaveCriticalSection(&CriticalSection);
  v6 = *(void **)(a1 + 13960);
  if ( v6 )
  {
    free(v6);
    *(_QWORD *)(a1 + 13960) = 0;
  }
  *(_BYTE *)(a1 + 524) = 1;
  *(_BYTE *)(a1 + 276) = 1;
  if ( *(_QWORD *)(a1 + 576) )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 1824) + 448LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 1824) + 472LL) = 0;
    if ( *(_QWORD *)(a1 + 592) )
    {
      sub_1802AD50C(v6);
      *(_QWORD *)(a1 + 592) = 0;
    }
    sub_18010E564(*(_QWORD *)(a1 + 576), *(_QWORD *)(a1 + 1824), 0);
    *(_QWORD *)(a1 + 1824) = 0;
    sub_1802AD56C(v7, *(_QWORD *)(a1 + 1816));
    *(_QWORD *)(a1 + 1816) = 0;
    sub_1802AD59C(v8, *(_QWORD *)(a1 + 576));
  }
  v9 = *(void **)(a1 + 1800);
  if ( v9 )
  {
    if ( *(_BYTE *)(a1 + 8378) )
      sub_1802AD53C(v9, *(_QWORD *)(a1 + 1800));
    else
      free(v9);
    *(_QWORD *)(a1 + 1800) = 0;
  }
  v10 = (_QWORD *)(a1 + 1792);
  for ( i = *(_QWORD **)(a1 + 1792); i != v10; i = v12 )
  {
    v12 = (_QWORD *)*i;
    free(i);
  }
  *v10 = v10;
  v13 = (_QWORD *)(a1 + 8320);
  for ( j = *(_QWORD **)(a1 + 8320); j != v13; j = v15 )
  {
    v15 = (_QWORD *)*j;
    free(j);
  }
  *v13 = v13;
  *(_QWORD *)(a1 + 8328) = a1 + 8320;
  sub_180170044(a1 + 2064);
  sub_180170044(a1 + 6088);
  *(_QWORD *)(a1 + 8160) = 0;
  *(_QWORD *)(a1 + 8168) = 0;
  *(_QWORD *)(a1 + 8176) = 0;
  *(_QWORD *)(a1 + 8184) = 0;
  *(_DWORD *)(a1 + 0x2000) = 0;
  *(_QWORD *)(a1 + 2048) = a1 + 2048;
  *(_QWORD *)(a1 + 2056) = a1 + 2048;
  *(_QWORD *)(a1 + 8304) = a1 + 8304;
  *(_QWORD *)(a1 + 8312) = a1 + 8304;
  if ( *(_QWORD *)(a1 + 24) )
    *(_QWORD *)(a1 + 24) = 0;
  _InterlockedAdd64(&qword_18043D9D0, -*(_QWORD *)(a1 + 1848));
  v16 = *(_QWORD *)(a1 + 584);
  if ( v16 )
  {
    CryptReleaseContext(v16, 0);
    *(_QWORD *)(a1 + 584) = 0;
  }
  sub_1801A2648(a1 + 13968);
  sub_18018ED14(a1 + 13840);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8856));
  sub_1802ADE90(a1 + 8784);
  *(_QWORD *)(a1 + 8752) = off_18036C790;
  sub_1801AAD04(a1 + 8752);
  sub_1802ADEEC(a1 + 8680);
  *(_QWORD *)(a1 + 8584) = off_18036C808;
  sub_1801AAD04(a1 + 8584);
  *(_QWORD *)(a1 + 8552) = off_18036C7F8;
  sub_1801AAD04(a1 + 8552);
  *(_QWORD *)(a1 + 8520) = off_18036C7E8;
  sub_1801AAD04(a1 + 8520);
  *(_QWORD *)(a1 + 8480) = off_18036C858;
  sub_1801AAD04(a1 + 8480);
  *(_QWORD *)(a1 + 8408) = off_18036C808;
  sub_1801AAD04(a1 + 8408);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8336));
  sub_1800A550C(a1 + 8208);
  sub_18007F5E0(a1 + 8160);
  sub_18016CF40(a1 + 6088);
  sub_18016CF40(a1 + 2064);
  sub_1800A550C(a1 + 1952);
  sub_1800A550C(a1 + 1664);
  sub_18000B704(a1 + 408);
  sub_1801A6CDC(a1 + 160);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
}

```

## disassembly

```asm
0x1802adafc  mov     r11, rsp
0x1802adaff  mov     [r11+8], rcx
0x1802adb03  push    rsi
0x1802adb04  push    rdi
0x1802adb05  push    r12
0x1802adb07  push    r14
0x1802adb09  push    r15
0x1802adb0b  sub     rsp, 30h
0x1802adb0f  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x1802adb17  mov     [r11+10h], rbx
0x1802adb1b  mov     [r11+18h], rbp
0x1802adb1f  lea     rax, off_18036C878
0x1802adb26  mov     rdi, rcx
0x1802adb29  mov     [rcx], rax
0x1802adb2c  lea     rcx, CriticalSection; lpCriticalSection
0x1802adb33  call    cs:EnterCriticalSection
0x1802adb39  mov     rcx, [rdi+8]
0x1802adb3d  mov     rax, [rdi+10h]
0x1802adb41  xor     r12d, r12d
0x1802adb44  test    rcx, rcx
0x1802adb47  jz      short loc_1802ADB4F
0x1802adb49  mov     [rcx+8], rax
0x1802adb4d  jmp     short loc_1802ADB68
0x1802adb4f  test    rax, rax
0x1802adb52  jz      short loc_1802ADB61
0x1802adb54  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802adb58  mov     cs:qword_18043D9D8, rax
0x1802adb5f  jmp     short loc_1802ADB68
0x1802adb61  mov     cs:qword_18043D9D8, r12
0x1802adb68  mov     rcx, [rdi+10h]
0x1802adb6c  mov     rax, [rdi+8]
0x1802adb70  test    rcx, rcx
0x1802adb73  jz      short loc_1802ADB7A
0x1802adb75  mov     [rcx], rax
0x1802adb78  jmp     short loc_1802ADB93
0x1802adb7a  test    rax, rax
0x1802adb7d  jz      short loc_1802ADB8C
0x1802adb7f  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802adb83  mov     cs:qword_18043D9C8, rax
0x1802adb8a  jmp     short loc_1802ADB93
0x1802adb8c  mov     cs:qword_18043D9C8, r12
0x1802adb93  mov     [rdi+8], r12
0x1802adb97  mov     [rdi+10h], r12
0x1802adb9b  lea     rcx, CriticalSection; lpCriticalSection
0x1802adba2  call    cs:LeaveCriticalSection
0x1802adba8  nop
0x1802adba9  mov     rcx, [rdi+3688h]; Block
0x1802adbb0  test    rcx, rcx
0x1802adbb3  jz      short loc_1802ADBC2
0x1802adbb5  call    cs:__imp_free
0x1802adbbb  mov     [rdi+3688h], r12
0x1802adbc2  lea     r14, [rdi+198h]
0x1802adbc9  mov     byte ptr [r14+74h], 1
0x1802adbce  lea     r15, [rdi+0A0h]
0x1802adbd5  mov     byte ptr [r15+74h], 1
0x1802adbda  cmp     [rdi+240h], r12
0x1802adbe1  jz      short loc_1802ADC53
0x1802adbe3  mov     rax, [rdi+720h]
0x1802adbea  mov     [rax+1C0h], r12
0x1802adbf1  mov     rax, [rdi+720h]
0x1802adbf8  mov     [rax+1D8h], r12
0x1802adbff  mov     rdx, [rdi+250h]
0x1802adc06  test    rdx, rdx
0x1802adc09  jz      short loc_1802ADC17
0x1802adc0b  call    sub_1802AD50C
0x1802adc10  mov     [rdi+250h], r12
0x1802adc17  xor     r8d, r8d
0x1802adc1a  mov     rdx, [rdi+720h]
0x1802adc21  mov     rcx, [rdi+240h]
0x1802adc28  call    sub_18010E564
0x1802adc2d  mov     [rdi+720h], r12
0x1802adc34  mov     rdx, [rdi+718h]
0x1802adc3b  call    sub_1802AD56C
0x1802adc40  mov     [rdi+718h], r12
0x1802adc47  mov     rdx, [rdi+240h]
0x1802adc4e  call    sub_1802AD59C
0x1802adc53  mov     rcx, [rdi+708h]; Block
0x1802adc5a  test    rcx, rcx
0x1802adc5d  jz      short loc_1802ADC7F
0x1802adc5f  cmp     [rdi+20BAh], r12b
0x1802adc66  jz      short loc_1802ADC72
0x1802adc68  mov     rdx, rcx
0x1802adc6b  call    sub_1802AD53C
0x1802adc70  jmp     short loc_1802ADC78
0x1802adc72  call    cs:__imp_free
0x1802adc78  mov     [rdi+708h], r12
0x1802adc7f  lea     rsi, [rdi+700h]
0x1802adc86  mov     rcx, [rsi]; Block
0x1802adc89  cmp     rcx, rsi
0x1802adc8c  jz      short loc_1802ADC9C
0x1802adc8e  mov     rbx, [rcx]
0x1802adc91  call    cs:__imp_free
0x1802adc97  mov     rcx, rbx
0x1802adc9a  jmp     short loc_1802ADC89
0x1802adc9c  mov     [rsi], rsi
0x1802adc9f  lea     rsi, [rdi+2080h]
0x1802adca6  mov     rcx, [rsi]; Block
0x1802adca9  cmp     rcx, rsi
0x1802adcac  jz      short loc_1802ADCBC
0x1802adcae  mov     rbx, [rcx]
0x1802adcb1  call    cs:__imp_free
0x1802adcb7  mov     rcx, rbx
0x1802adcba  jmp     short loc_1802ADCA9
0x1802adcbc  mov     [rsi], rsi
0x1802adcbf  mov     [rsi+8], rsi
0x1802adcc3  lea     rsi, [rdi+810h]
0x1802adcca  mov     rcx, rsi
0x1802adccd  call    sub_180170044
0x1802adcd2  lea     rbp, [rdi+17C8h]
0x1802adcd9  mov     rcx, rbp
0x1802adcdc  call    sub_180170044
0x1802adce1  lea     rbx, [rdi+1FE0h]
0x1802adce8  mov     [rbx], r12
0x1802adceb  mov     [rbx+8], r12
0x1802adcef  mov     [rbx+10h], r12
0x1802adcf3  mov     [rbx+18h], r12
0x1802adcf7  mov     [rbx+20h], r12d
0x1802adcfb  lea     rax, [rdi+800h]
0x1802add02  mov     [rax], rax
0x1802add05  mov     [rax+8], rax
0x1802add09  lea     rax, [rdi+2070h]
0x1802add10  mov     [rax], rax
0x1802add13  mov     [rax+8], rax
0x1802add17  cmp     [rdi+18h], r12
0x1802add1b  jz      short loc_1802ADD21
0x1802add1d  mov     [rdi+18h], r12
0x1802add21  mov     rax, [rdi+738h]
0x1802add28  neg     rax
0x1802add2b  lock add cs:qword_18043D9D0, rax
0x1802add33  mov     rcx, [rdi+248h]; hProv
0x1802add3a  test    rcx, rcx
0x1802add3d  jz      short loc_1802ADD4E
0x1802add3f  xor     edx, edx; dwFlags
0x1802add41  call    cs:CryptReleaseContext
0x1802add47  mov     [rdi+248h], r12
0x1802add4e  lea     rcx, [rdi+3690h]
0x1802add55  call    sub_1801A2648
0x1802add5a  lea     rcx, [rdi+3610h]
0x1802add61  call    sub_18018ED14
0x1802add66  nop
0x1802add67  lea     rcx, [rdi+2298h]; lpCriticalSection
0x1802add6e  call    cs:DeleteCriticalSection
0x1802add74  nop
0x1802add75  lea     rcx, [rdi+2250h]
0x1802add7c  call    sub_1802ADE90
0x1802add81  lea     rcx, [rdi+2230h]
0x1802add88  lea     rax, off_18036C790
0x1802add8f  mov     [rcx], rax
0x1802add92  call    sub_1801AAD04
0x1802add97  lea     rcx, [rdi+21E8h]
0x1802add9e  call    sub_1802ADEEC
0x1802adda3  lea     rcx, [rdi+2188h]
0x1802addaa  lea     r12, off_18036C808
0x1802addb1  mov     [rcx], r12
0x1802addb4  call    sub_1801AAD04
0x1802addb9  lea     rcx, [rdi+2168h]
0x1802addc0  lea     rax, off_18036C7F8
0x1802addc7  mov     [rcx], rax
0x1802addca  call    sub_1801AAD04
0x1802addcf  lea     rcx, [rdi+2148h]
0x1802addd6  lea     rax, off_18036C7E8
0x1802adddd  mov     [rcx], rax
0x1802adde0  call    sub_1801AAD04
0x1802adde5  lea     rcx, [rdi+2120h]
0x1802addec  lea     rax, off_18036C858
0x1802addf3  mov     [rcx], rax
0x1802addf6  call    sub_1801AAD04
0x1802addfb  lea     rcx, [rdi+20D8h]
0x1802ade02  mov     [rcx], r12
0x1802ade05  call    sub_1801AAD04
0x1802ade0a  nop
0x1802ade0b  lea     rcx, [rdi+2090h]; lpCriticalSection
0x1802ade12  call    cs:DeleteCriticalSection
0x1802ade18  nop
0x1802ade19  lea     rcx, [rdi+2010h]
0x1802ade20  call    sub_1800A550C
0x1802ade25  mov     rcx, rbx
0x1802ade28  call    sub_18007F5E0
0x1802ade2d  mov     rcx, rbp
0x1802ade30  call    sub_18016CF40
0x1802ade35  mov     rcx, rsi
0x1802ade38  call    sub_18016CF40
0x1802ade3d  lea     rcx, [rdi+7A0h]
0x1802ade44  call    sub_1800A550C
0x1802ade49  lea     rcx, [rdi+680h]
0x1802ade50  call    sub_1800A550C
0x1802ade55  mov     rcx, r14
0x1802ade58  call    sub_18000B704
0x1802ade5d  mov     rcx, r15
0x1802ade60  call    sub_1801A6CDC
0x1802ade65  nop
0x1802ade66  lea     rcx, [rdi+70h]; lpCriticalSection
0x1802ade6a  call    cs:DeleteCriticalSection
0x1802ade70  nop
0x1802ade71  mov     rbx, [rsp+58h+arg_8]
0x1802ade76  mov     rbp, [rsp+58h+arg_10]
0x1802ade7b  add     rsp, 30h
0x1802ade7f  pop     r15
0x1802ade81  pop     r14
0x1802ade83  pop     r12
0x1802ade85  pop     rdi
0x1802ade86  pop     rsi
0x1802ade87  retn
```
