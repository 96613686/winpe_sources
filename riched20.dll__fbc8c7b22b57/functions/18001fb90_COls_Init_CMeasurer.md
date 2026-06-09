# COls::Init(CMeasurer *)

- ea: `0x18001fb90`
- end: `0x18001ff1f`
- name: `?Init@COls@@QEAAJPEAVCMeasurer@@@Z`
- size: `911`
- prototype: `__int64 __fastcall(COls *__hidden this, struct CMeasurer *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ec10`
- `0x18001027c`
- `0x180015670`
- `0x18001f9e0`
- `0x180020940`
- `0x180022324`
- `0x180023cac`

## callees

- `0x18001fb90`
- `0x180036310`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `msls31!__imp_LsCreateContext` at `0x18001fde5`
- `msls31!__imp_LsCreateContext` at `0x18001fde5`
- `msls31!__imp_LsSetBreaking` at `0x18001fee5`
- `msls31!__imp_LsSetBreaking` at `0x18001fee5`
- `msls31!__imp_LsGetReverseLsimethods` at `0x18001fc6c`
- `msls31!__imp_LsGetReverseLsimethods` at `0x18001fc6c`

## pseudocode

```c
__int64 __fastcall COls::Init(COls *this, struct CMeasurer *a2)
{
  COls *v2; // rbx
  __m128i si128; // xmm0
  __int64 v4; // rdx
  char *v5; // rcx
  __int128 *v6; // rax
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v21; // rbx
  char *v22; // rdi
  int i; // esi
  int v24; // r15d
  bool v25; // zf
  char v26; // r15
  _OWORD v28[11]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall *v29)(CDisplay *__hidden); // [rsp+E0h] [rbp-20h]
  _BYTE v30[184]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v31[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v32; // [rsp+1A4h] [rbp+A4h]
  _OWORD *v33; // [rsp+1A8h] [rbp+A8h]
  int v34; // [rsp+1B0h] [rbp+B0h]
  __int16 v35; // [rsp+1B4h] [rbp+B4h]
  __int64 v36; // [rsp+1B6h] [rbp+B6h]
  _BYTE v37[18]; // [rsp+1BEh] [rbp+BEh]
  __m128i v38; // [rsp+1D0h] [rbp+D0h]
  _BYTE v39[44]; // [rsp+1E0h] [rbp+E0h] BYREF
  COls *v40; // [rsp+210h] [rbp+110h]
  char v41; // [rsp+218h] [rbp+118h] BYREF
  int v42; // [rsp+408h] [rbp+308h]
  _BYTE v43[256]; // [rsp+410h] [rbp+310h] BYREF

  v2 = g_pols;
  *(_QWORD *)g_pols = a2;
  if ( g_plsc )
    return 0;
  memset_0(v31, 0, 0x270u);
  v28[0] = vlsimethodsOle;
  v29 = CDisplay::GetYScroll;
  v28[2] = *(_OWORD *)&off_180096050;
  v28[1] = *(_OWORD *)&off_180096040;
  v28[4] = *(_OWORD *)byte_180096070;
  v28[3] = xmmword_180096060;
  v28[6] = *(_OWORD *)&off_180096090;
  v28[5] = *(_OWORD *)&off_180096080;
  v28[8] = *(_OWORD *)byte_1800960B0;
  v28[7] = *(_OWORD *)&off_1800960A0;
  v28[10] = *(_OWORD *)byte_1800960D0;
  v28[9] = *(_OWORD *)off_1800960C0;
  if ( (unsigned int)LsGetReverseLsimethods(v30) )
    return 2147500037LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v33 = v28;
  v35 = si128.m128i_i16[2];
  v32 = 2;
  *(__m128i *)&v37[2] = si128;
  *(_WORD *)&v37[6] = 11;
  v4 = 3;
  v42 = 1;
  *(__m128i *)&v39[16] = si128;
  v34 = 66;
  *(__m128i *)v39 = si128;
  strcpy(&v39[12], " ");
  v5 = &v41;
  v38 = si128;
  v38.m128i_i16[0] = 173;
  *(__m128i *)&v39[28] = si128;
  *(_WORD *)&v39[40] = 159;
  v6 = (__int128 *)&lscbk;
  v36 = 0x9002D00200000LL;
  *(_DWORD *)v37 = 655373;
  *(_DWORD *)&v39[14] = 2097184;
  v40 = v2;
  do
  {
    v5 += 128;
    v7 = *v6;
    v8 = v6[1];
    v6 += 8;
    *((_OWORD *)v5 - 8) = v7;
    v9 = *(v6 - 6);
    *((_OWORD *)v5 - 7) = v8;
    v10 = *(v6 - 5);
    *((_OWORD *)v5 - 6) = v9;
    v11 = *(v6 - 4);
    *((_OWORD *)v5 - 5) = v10;
    v12 = *(v6 - 3);
    *((_OWORD *)v5 - 4) = v11;
    v13 = *(v6 - 2);
    *((_OWORD *)v5 - 3) = v12;
    v14 = *(v6 - 1);
    *((_OWORD *)v5 - 2) = v13;
    *((_OWORD *)v5 - 1) = v14;
    --v4;
  }
  while ( v4 );
  v15 = v6[1];
  *(_OWORD *)v5 = *v6;
  v16 = v6[2];
  *((_OWORD *)v5 + 1) = v15;
  v17 = v6[3];
  *((_OWORD *)v5 + 2) = v16;
  v18 = v6[4];
  *((_OWORD *)v5 + 3) = v17;
  v19 = v6[5];
  *((_OWORD *)v5 + 4) = v18;
  v20 = v6[6];
  *((_OWORD *)v5 + 5) = v19;
  *((_OWORD *)v5 + 6) = v20;
  if ( (unsigned int)LsCreateContext(v31, &g_plsc) )
    return 2147500037LL;
  v21 = 0;
  v22 = v43;
  do
  {
    for ( i = 0; i < 16; ++i )
    {
      v24 = (*((unsigned __int16 *)qword_18009B210 + v21) >> i) & 1;
      v25 = 2 * v24 == 0;
      v26 = 2 * v24;
      if ( v25 && (unsigned int)GetKinsokuClass(v21) != 1 && (unsigned int)GetKinsokuClass(i) != 1 )
        v26 = 1;
      *v22++ = v26;
    }
    v21 = (unsigned int)(v21 + 1);
  }
  while ( (int)v21 < 16 );
  return (unsigned int)LsSetBreaking(g_plsc, 3, &qword_18009BFC8, 16, v43) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001fb90  push    rbp
0x18001fb92  push    rbx
0x18001fb93  lea     rbp, [rsp-438h]
0x18001fb9b  sub     rsp, 538h
0x18001fba2  mov     rax, cs:__security_cookie
0x18001fba9  xor     rax, rsp
0x18001fbac  mov     [rbp+440h+var_30], rax
0x18001fbb3  mov     rbx, cs:?g_pols@@3PEAUCOls@@EA; COls * g_pols
0x18001fbba  mov     [rbx], rdx
0x18001fbbd  cmp     cs:?g_plsc@@3PEAUCLineServices@@EA, 0; CLineServices * g_plsc
0x18001fbc5  jnz     loc_18001FF03
0x18001fbcb  xor     edx, edx; Val
0x18001fbcd  lea     rcx, [rbp+440h+var_3A0]; void *
0x18001fbd4  mov     r8d, 270h; Size
0x18001fbda  call    memset_0
0x18001fbdf  movaps  xmm0, xmmword ptr cs:?vlsimethodsOle@@3ULSIMETHODS@@B; LSIMETHODS const vlsimethodsOle
0x18001fbe6  lea     rcx, [rbp+440h+var_458]
0x18001fbea  movaps  xmm1, xmmword ptr cs:off_180096040
0x18001fbf1  mov     rax, cs:off_1800960E0
0x18001fbf8  movups  [rsp+540h+var_510], xmm0
0x18001fbfd  mov     [rbp+440h+var_460], rax
0x18001fc01  movaps  xmm0, xmmword ptr cs:off_180096050
0x18001fc08  movups  [rsp+540h+var_4F0], xmm0
0x18001fc0d  movaps  xmm0, xmmword ptr cs:byte_180096070
0x18001fc14  movups  [rsp+540h+var_500], xmm1
0x18001fc19  movaps  xmm1, cs:xmmword_180096060
0x18001fc20  movups  [rsp+540h+var_4D0], xmm0
0x18001fc25  movaps  xmm0, xmmword ptr cs:off_180096090
0x18001fc2c  movups  [rsp+540h+var_4E0], xmm1
0x18001fc31  movaps  xmm1, xmmword ptr cs:off_180096080
0x18001fc38  movups  [rbp+440h+var_4B0], xmm0
0x18001fc3c  movaps  xmm0, xmmword ptr cs:byte_1800960B0
0x18001fc43  movups  [rbp+440h+var_4C0], xmm1
0x18001fc47  movaps  xmm1, xmmword ptr cs:off_1800960A0
0x18001fc4e  movups  [rbp+440h+var_490], xmm0
0x18001fc52  movaps  xmm0, xmmword ptr cs:byte_1800960D0
0x18001fc59  movups  [rbp+440h+var_4A0], xmm1
0x18001fc5d  movaps  xmm1, xmmword ptr cs:off_1800960C0
0x18001fc64  movups  [rbp+440h+var_470], xmm0
0x18001fc68  movups  [rbp+440h+var_480], xmm1
0x18001fc6c  call    cs:__imp_LsGetReverseLsimethods
0x18001fc73  nop     dword ptr [rax+rax+00h]
0x18001fc78  test    eax, eax
0x18001fc7a  jnz     loc_18001FEFC
0x18001fc80  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001fc88  lea     rax, [rsp+540h+var_510]
0x18001fc8d  mov     [rbp+440h+var_398], rax
0x18001fc94  mov     ecx, 20h ; ' '
0x18001fc99  movups  [rbp+440h+var_390], xmm0
0x18001fca0  mov     eax, 0Bh
0x18001fca5  mov     [rbp+440h+var_39C], 2
0x18001fcaf  movups  [rbp+440h+var_380], xmm0
0x18001fcb6  mov     word ptr [rbp+440h+var_380+4], ax
0x18001fcbd  mov     edx, 3
0x18001fcc2  mov     eax, 0ADh
0x18001fcc7  mov     [rbp+440h+var_138], 1
0x18001fcd1  movups  [rbp+440h+var_350], xmm0
0x18001fcd8  mov     dword ptr [rbp+440h+var_390], 42h ; 'B'
0x18001fce2  movups  [rbp+440h+var_360], xmm0
0x18001fce9  mov     word ptr [rbp+440h+var_360+0Ch], cx
0x18001fcf0  lea     rcx, [rbp+440h+var_328]
0x18001fcf7  movups  [rbp+440h+var_370], xmm0
0x18001fcfe  mov     word ptr [rbp+440h+var_370], ax
0x18001fd05  mov     eax, 9Fh
0x18001fd0a  movups  [rbp+440h+var_350+0Ch], xmm0
0x18001fd11  mov     [rbp+440h+var_338], ax
0x18001fd18  lea     rax, ?lscbk@@3U0@B; lscbk const lscbk
0x18001fd1f  mov     dword ptr [rbp+440h+var_390+6], 200000h
0x18001fd29  mov     dword ptr [rbp+440h+var_390+0Ah], 9002Dh
0x18001fd33  mov     dword ptr [rbp+440h+var_390+0Eh], 0A000Dh
0x18001fd3d  mov     dword ptr [rbp+440h+var_360+0Eh], 200020h
0x18001fd47  mov     [rbp+440h+var_330], rbx
0x18001fd4e  lea     rcx, [rcx+80h]
0x18001fd55  movups  xmm0, xmmword ptr [rax]
0x18001fd58  movups  xmm1, xmmword ptr [rax+10h]
0x18001fd5c  lea     rax, [rax+80h]
0x18001fd63  movups  xmmword ptr [rcx-80h], xmm0
0x18001fd67  movups  xmm0, xmmword ptr [rax-60h]
0x18001fd6b  movups  xmmword ptr [rcx-70h], xmm1
0x18001fd6f  movups  xmm1, xmmword ptr [rax-50h]
0x18001fd73  movups  xmmword ptr [rcx-60h], xmm0
0x18001fd77  movups  xmm0, xmmword ptr [rax-40h]
0x18001fd7b  movups  xmmword ptr [rcx-50h], xmm1
0x18001fd7f  movups  xmm1, xmmword ptr [rax-30h]
0x18001fd83  movups  xmmword ptr [rcx-40h], xmm0
0x18001fd87  movups  xmm0, xmmword ptr [rax-20h]
0x18001fd8b  movups  xmmword ptr [rcx-30h], xmm1
0x18001fd8f  movups  xmm1, xmmword ptr [rax-10h]
0x18001fd93  movups  xmmword ptr [rcx-20h], xmm0
0x18001fd97  movups  xmmword ptr [rcx-10h], xmm1
0x18001fd9b  sub     rdx, 1
0x18001fd9f  jnz     short loc_18001FD4E
0x18001fda1  movups  xmm0, xmmword ptr [rax]
0x18001fda4  lea     rdx, ?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x18001fdab  movups  xmm1, xmmword ptr [rax+10h]
0x18001fdaf  movups  xmmword ptr [rcx], xmm0
0x18001fdb2  movups  xmm0, xmmword ptr [rax+20h]
0x18001fdb6  movups  xmmword ptr [rcx+10h], xmm1
0x18001fdba  movups  xmm1, xmmword ptr [rax+30h]
0x18001fdbe  movups  xmmword ptr [rcx+20h], xmm0
0x18001fdc2  movups  xmm0, xmmword ptr [rax+40h]
0x18001fdc6  movups  xmmword ptr [rcx+30h], xmm1
0x18001fdca  movups  xmm1, xmmword ptr [rax+50h]
0x18001fdce  movups  xmmword ptr [rcx+40h], xmm0
0x18001fdd2  movups  xmm0, xmmword ptr [rax+60h]
0x18001fdd6  movups  xmmword ptr [rcx+50h], xmm1
0x18001fdda  movups  xmmword ptr [rcx+60h], xmm0
0x18001fdde  lea     rcx, [rbp+440h+var_3A0]
0x18001fde5  call    cs:__imp_LsCreateContext
0x18001fdec  nop     dword ptr [rax+rax+00h]
0x18001fdf1  test    eax, eax
0x18001fdf3  jnz     loc_18001FEFC
0x18001fdf9  mov     [rsp+540h+arg_0], rsi
0x18001fe01  xor     ebx, ebx
0x18001fe03  mov     [rsp+540h+arg_8], rdi
0x18001fe0b  lea     rdi, [rbp+440h+var_130]
0x18001fe12  mov     [rsp+540h+arg_10], r12
0x18001fe1a  mov     [rsp+540h+var_10], r13
0x18001fe22  lea     r13, qword_18009B210
0x18001fe29  mov     [rsp+540h+var_18], r14
0x18001fe31  mov     [rsp+540h+var_20], r15
0x18001fe39  xor     esi, esi
0x18001fe3b  lea     r14, ds:0[rbx*2]
0x18001fe43  movzx   r15d, word ptr [r14+r13]
0x18001fe48  movzx   r12d, si
0x18001fe4c  mov     ecx, r12d
0x18001fe4f  shr     r15d, cl
0x18001fe52  and     r15d, 1
0x18001fe56  add     r15d, r15d
0x18001fe59  jnz     short loc_18001FE7C
0x18001fe5b  movzx   ecx, bx; unsigned __int16
0x18001fe5e  call    ?GetKinsokuClass@@YAHG@Z; GetKinsokuClass(ushort)
0x18001fe63  cmp     eax, 1
0x18001fe66  jz      short loc_18001FE7C
0x18001fe68  movzx   ecx, si; unsigned __int16
0x18001fe6b  call    ?GetKinsokuClass@@YAHG@Z; GetKinsokuClass(ushort)
0x18001fe70  cmp     eax, 1
0x18001fe73  mov     eax, 1
0x18001fe78  cmovnz  r15d, eax
0x18001fe7c  mov     [rdi], r15b
0x18001fe7f  inc     esi
0x18001fe81  inc     rdi
0x18001fe84  cmp     esi, 10h
0x18001fe87  jl      short loc_18001FE43
0x18001fe89  inc     ebx
0x18001fe8b  cmp     ebx, 10h
0x18001fe8e  jl      short loc_18001FE39
0x18001fe90  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x18001fe97  lea     rax, [rbp+440h+var_130]
0x18001fe9e  mov     r15, [rsp+540h+var_20]
0x18001fea6  lea     r8, qword_18009BFC8
0x18001fead  mov     r14, [rsp+540h+var_18]
0x18001feb5  mov     r9d, 10h
0x18001febb  mov     r13, [rsp+540h+var_10]
0x18001fec3  mov     edx, 3
0x18001fec8  mov     r12, [rsp+540h+arg_10]
0x18001fed0  mov     rdi, [rsp+540h+arg_8]
0x18001fed8  mov     rsi, [rsp+540h+arg_0]
0x18001fee0  mov     [rsp+540h+var_520], rax
0x18001fee5  call    cs:__imp_LsSetBreaking
0x18001feec  nop     dword ptr [rax+rax+00h]
0x18001fef1  neg     eax
0x18001fef3  sbb     eax, eax
0x18001fef5  and     eax, 80004005h
0x18001fefa  jmp     short loc_18001FF05
0x18001fefc  mov     eax, 80004005h
0x18001ff01  jmp     short loc_18001FF05
0x18001ff03  xor     eax, eax
0x18001ff05  mov     rcx, [rbp+440h+var_30]
0x18001ff0c  xor     rcx, rsp; StackCookie
0x18001ff0f  call    __security_check_cookie
0x18001ff14  add     rsp, 538h
0x18001ff1b  pop     rbx
0x18001ff1c  pop     rbp
0x18001ff1d  retn
```
