# Imapi2Utility::ReadMediaCapacity(IDiscRecorder2Ex *,ulong *,ulong *)

- ea: `0x180046708`
- end: `0x180046a24`
- name: `?ReadMediaCapacity@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAK1@Z`
- size: `796`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned int *, unsigned int *)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009984`
- `0x18000a8ac`
- `0x18001b830`
- `0x18001dd30`
- `0x180025508`
- `0x180026860`

## callees

- `0x18000ae3c`
- `0x1800140f4`
- `0x180014134`
- `0x1800236b4`
- `0x18002cf74`
- `0x180046708`
- `0x180049880`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::ReadMediaCapacity(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v5; // rax
  __int64 (__fastcall *v7)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int, __int64 *, int, _BYTE *); // rax
  int v8; // eax
  int *v9; // r9
  unsigned int v10; // edi
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  char v14; // cl
  char v15; // cl
  char v16; // cl
  int v17; // r8d
  char v18; // cl
  PVOID *v19; // rcx
  int v20; // r10d
  int v21; // edx
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v24[24]; // [rsp+58h] [rbp-11h] BYREF
  union _CDB v25; // [rsp+70h] [rbp+7h] BYREF
  __int16 v26; // [rsp+80h] [rbp+17h]
  __int128 v27; // [rsp+88h] [rbp+1Fh] BYREF

  LODWORD(a2->lpVtbl) = 2048;
  *a3 = 0;
  v26 = 0;
  *(_DWORD *)&v24[4] = 0;
  v5 = *(_QWORD *)this;
  v23 = 0;
  v7 = *(__int64 (__fastcall **)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int, __int64 *, int, _BYTE *))(v5 + 40);
  v27 = 0;
  LOBYTE(v27) = 37;
  v25 = 0;
  v8 = v7(this, &v27, 10, &v25, 10, &v23, 8, &v24[4]);
  *(_DWORD *)v24 = v8;
  v10 = v8;
  if ( v8 == 11141632 )
  {
    Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v27, &v25, (const struct _SENSE_DATA *)v24, v9);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      return *(unsigned int *)v24;
    }
    else
    {
      v10 = *(_DWORD *)v24;
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      *(_WORD *)&v24[8] = 18;
      *(_QWORD *)&v24[16] = &v25;
      *(_DWORD *)&v24[10] = 0;
      *(_WORD *)&v24[14] = 0;
      WPP_SF_dDDD_HEX_(
        v11,
        70,
        (unsigned int)&WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        *(_DWORD *)v24,
        v25.CDB6GENERIC.CommandUniqueBytes[0] & 0xF,
        v25.CDB16.TransferLength[2],
        v25.CDB16.TransferLength[3],
        (__int64)&v24[8]);
    }
    return v10;
  }
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)v8);
    }
    return v10;
  }
  if ( *(_DWORD *)&v24[4] < 8u )
  {
    v10 = -1062599937;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      return v10;
    }
    v13 = 72;
    goto LABEL_17;
  }
  v14 = BYTE3(v23);
  BYTE3(v23) = v23;
  LOBYTE(v23) = v14;
  v15 = BYTE2(v23);
  BYTE2(v23) = BYTE1(v23);
  BYTE1(v23) = v15;
  v16 = HIBYTE(v23);
  v17 = v23;
  HIBYTE(v23) = BYTE4(v23);
  BYTE4(v23) = v16;
  v18 = BYTE6(v23);
  BYTE6(v23) = BYTE5(v23);
  BYTE5(v23) = v18;
  if ( (((_DWORD)v23 + 1) & 0xFFFFFFFE) != 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)v23);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v17 = -1;
    LODWORD(v23) = -1;
  }
  v20 = 0;
  v21 = HIDWORD(v23);
  if ( HIDWORD(v23) )
  {
    do
    {
      ++v20;
      v21 &= v21 - 1;
    }
    while ( v21 );
    if ( v20 == 1 )
    {
      LODWORD(a2->lpVtbl) = HIDWORD(v23);
      *a3 = v17 + 1;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        return v10;
      }
      v13 = 75;
LABEL_17:
      WPP_SF_DDDd(v12[2], v13, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      return v10;
    }
  }
  v10 = -1062599937;
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 3u )
    WPP_SF_Dd(v19[2], 74, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, HIDWORD(v23), HIDWORD(v23));
  return v10;
}

```

## disassembly

```asm
0x180046708  push    rbp
0x18004670a  push    rbx
0x18004670b  push    rsi
0x18004670c  push    rdi
0x18004670d  push    r14
0x18004670f  lea     rbp, [rsp-37h]
0x180046714  sub     rsp, 0A0h
0x18004671b  mov     rax, cs:__security_cookie
0x180046722  xor     rax, rsp
0x180046725  mov     [rbp+57h+var_28], rax
0x180046729  xor     eax, eax
0x18004672b  mov     dword ptr [rdx], 800h
0x180046731  mov     rsi, rdx
0x180046734  mov     [r8], eax
0x180046737  mov     [rbp+57h+var_40], ax
0x18004673b  lea     rdx, [rbp+57h+var_68+4]
0x18004673f  mov     [rsp+0C0h+var_88], rdx
0x180046744  lea     r9, [rbp+57h+var_50]
0x180046748  mov     dword ptr [rbp+57h+var_68+4], eax
0x18004674b  lea     rdx, [rbp+57h+var_70]
0x18004674f  mov     rax, [rcx]
0x180046752  mov     r14, r8
0x180046755  xorps   xmm0, xmm0
0x180046758  mov     [rsp+0C0h+var_90], 8
0x180046760  mov     [rsp+0C0h+var_98], rdx
0x180046765  xorps   xmm1, xmm1
0x180046768  mov     r8d, 0Ah
0x18004676e  mov     [rbp+57h+var_70], 0
0x180046776  mov     rax, [rax+28h]
0x18004677a  lea     rdx, [rbp+57h+var_38]
0x18004677e  movups  [rbp+57h+var_38], xmm0
0x180046782  mov     byte ptr [rbp+57h+var_38], 25h ; '%'
0x180046786  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x18004678a  mov     [rsp+0C0h+var_A0], r8d
0x18004678f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046794  mov     dword ptr [rbp+57h+var_68], eax
0x180046797  mov     edi, eax
0x180046799  cmp     eax, 0AA0200h
0x18004679e  jnz     loc_18004683F
0x1800467a4  lea     r8, [rbp+57h+var_68]; struct _SENSE_DATA *
0x1800467a8  lea     rdx, [rbp+57h+var_50]; union _CDB *
0x1800467ac  lea     rcx, [rbp+57h+var_38]; this
0x1800467b0  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x1800467b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800467bc  lea     rbx, WPP_GLOBAL_Control
0x1800467c3  cmp     rcx, rbx
0x1800467c6  jz      short loc_180046837
0x1800467c8  test    byte ptr [rcx+1Ch], 4
0x1800467cc  jz      short loc_180046837
0x1800467ce  cmp     byte ptr [rcx+19h], 3
0x1800467d2  jb      short loc_180046837
0x1800467d4  movzx   r8d, byte ptr [rbp+57h+var_50+0Ch]
0x1800467d9  lea     r10, [rbp+57h+var_68+8]
0x1800467dd  movzx   r9d, byte ptr [rbp+57h+var_50+2]
0x1800467e2  xor     edx, edx
0x1800467e4  mov     edi, dword ptr [rbp+57h+var_68]
0x1800467e7  and     r9d, 0Fh
0x1800467eb  mov     rcx, [rcx+10h]
0x1800467ef  mov     eax, 12h
0x1800467f4  mov     [rsp+0C0h+var_88], r10
0x1800467f9  mov     word ptr [rbp+57h+var_68+8], ax
0x1800467fd  lea     rax, [rbp+57h+var_50]
0x180046801  mov     qword ptr [rbp+57h+var_68+10h], rax
0x180046805  movzx   eax, byte ptr [rbp+57h+var_50+0Dh]
0x180046809  mov     [rsp+0C0h+var_90], eax
0x18004680d  mov     dword ptr [rsp+0C0h+var_98], r8d
0x180046812  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180046819  mov     [rsp+0C0h+var_A0], r9d
0x18004681e  mov     r9d, edi
0x180046821  mov     dword ptr [rbp+57h+var_68+0Ah], edx
0x180046824  mov     word ptr [rbp+57h+var_68+0Eh], dx
0x180046828  mov     edx, 46h ; 'F'
0x18004682d  call    WPP_SF_dDDD_HEX_
0x180046832  jmp     loc_180046A08
0x180046837  mov     edi, dword ptr [rbp+57h+var_68]
0x18004683a  jmp     loc_180046A08
0x18004683f  test    eax, eax
0x180046841  jns     short loc_18004688B
0x180046843  mov     rcx, cs:WPP_GLOBAL_Control
0x18004684a  lea     rbx, WPP_GLOBAL_Control
0x180046851  cmp     rcx, rbx
0x180046854  jz      loc_180046A08
0x18004685a  test    byte ptr [rcx+1Ch], 4
0x18004685e  jz      loc_180046A08
0x180046864  cmp     byte ptr [rcx+19h], 3
0x180046868  jb      loc_180046A08
0x18004686e  mov     rcx, [rcx+10h]
0x180046872  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180046879  mov     edx, 47h ; 'G'
0x18004687e  mov     r9d, eax
0x180046881  call    WPP_SF_d
0x180046886  jmp     loc_180046A08
0x18004688b  mov     r9d, dword ptr [rbp+57h+var_68+4]
0x18004688f  cmp     r9d, 8
0x180046893  jnb     short loc_1800468F4
0x180046895  mov     edi, 0C0AA02FFh
0x18004689a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468a1  lea     rbx, WPP_GLOBAL_Control
0x1800468a8  cmp     rcx, rbx
0x1800468ab  jz      loc_180046A08
0x1800468b1  test    byte ptr [rcx+1Ch], 4
0x1800468b5  jz      loc_180046A08
0x1800468bb  cmp     byte ptr [rcx+19h], 3
0x1800468bf  jb      loc_180046A08
0x1800468c5  mov     [rsp+0C0h+var_90], 8
0x1800468cd  mov     edx, 48h ; 'H'
0x1800468d2  mov     dword ptr [rsp+0C0h+var_98], 8
0x1800468da  mov     rcx, [rcx+10h]
0x1800468de  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800468e5  mov     [rsp+0C0h+var_A0], r9d
0x1800468ea  call    WPP_SF_DDDd
0x1800468ef  jmp     loc_180046A08
0x1800468f4  mov     al, byte ptr [rbp+57h+var_70]
0x1800468f7  lea     rbx, WPP_GLOBAL_Control
0x1800468fe  mov     cl, byte ptr [rbp+57h+var_70+3]
0x180046901  mov     byte ptr [rbp+57h+var_70+3], al
0x180046904  mov     al, byte ptr [rbp+57h+var_70+1]
0x180046907  mov     byte ptr [rbp+57h+var_70], cl
0x18004690a  mov     cl, byte ptr [rbp+57h+var_70+2]
0x18004690d  mov     byte ptr [rbp+57h+var_70+2], al
0x180046910  mov     al, byte ptr [rbp+57h+var_70+4]
0x180046913  mov     byte ptr [rbp+57h+var_70+1], cl
0x180046916  mov     cl, byte ptr [rbp+57h+var_70+7]
0x180046919  mov     r8d, dword ptr [rbp+57h+var_70]
0x18004691d  mov     byte ptr [rbp+57h+var_70+7], al
0x180046920  mov     al, byte ptr [rbp+57h+var_70+5]
0x180046923  mov     byte ptr [rbp+57h+var_70+4], cl
0x180046926  mov     cl, byte ptr [rbp+57h+var_70+6]
0x180046929  mov     byte ptr [rbp+57h+var_70+6], al
0x18004692c  lea     eax, [r8+1]
0x180046930  mov     byte ptr [rbp+57h+var_70+5], cl
0x180046933  test    eax, 0FFFFFFFEh
0x180046938  jnz     short loc_18004697B
0x18004693a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046941  cmp     rcx, rbx
0x180046944  jz      short loc_180046971
0x180046946  test    byte ptr [rcx+1Ch], 4
0x18004694a  jz      short loc_180046971
0x18004694c  cmp     byte ptr [rcx+19h], 3
0x180046950  jb      short loc_180046971
0x180046952  mov     rcx, [rcx+10h]
0x180046956  mov     r9d, r8d
0x180046959  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180046960  mov     edx, 49h ; 'I'
0x180046965  call    WPP_SF_d
0x18004696a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046971  or      r8d, 0FFFFFFFFh
0x180046975  mov     dword ptr [rbp+57h+var_70], r8d
0x180046979  jmp     short loc_180046982
0x18004697b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046982  mov     r9d, dword ptr [rbp+57h+var_70+4]
0x180046986  xor     r10d, r10d
0x180046989  mov     edx, r9d
0x18004698c  test    r9d, r9d
0x18004698f  jz      short loc_1800469D8
0x180046991  lea     eax, [rdx-1]
0x180046994  inc     r10d
0x180046997  and     edx, eax
0x180046999  jnz     short loc_180046991
0x18004699b  cmp     r10d, 1
0x18004699f  jnz     short loc_1800469D8
0x1800469a1  inc     r8d
0x1800469a4  mov     [rsi], r9d
0x1800469a7  mov     [r14], r8d
0x1800469aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469b1  cmp     rcx, rbx
0x1800469b4  jz      short loc_180046A08
0x1800469b6  test    byte ptr [rcx+1Ch], 4
0x1800469ba  jz      short loc_180046A08
0x1800469bc  cmp     byte ptr [rcx+19h], 5
0x1800469c0  jb      short loc_180046A08
0x1800469c2  mov     r9d, [rsi]
0x1800469c5  lea     edx, [r10+4Ah]
0x1800469c9  mov     [rsp+0C0h+var_90], r8d
0x1800469ce  mov     dword ptr [rsp+0C0h+var_98], r8d
0x1800469d3  jmp     loc_1800468DA
0x1800469d8  mov     edi, 0C0AA02FFh
0x1800469dd  cmp     rcx, rbx
0x1800469e0  jz      short loc_180046A08
0x1800469e2  test    byte ptr [rcx+1Ch], 4
0x1800469e6  jz      short loc_180046A08
0x1800469e8  cmp     byte ptr [rcx+19h], 3
0x1800469ec  jb      short loc_180046A08
0x1800469ee  mov     rcx, [rcx+10h]
0x1800469f2  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800469f9  mov     edx, 4Ah ; 'J'
0x1800469fe  mov     [rsp+0C0h+var_A0], r9d
0x180046a03  call    WPP_SF_Dd
0x180046a08  mov     eax, edi
0x180046a0a  mov     rcx, [rbp+57h+var_28]
0x180046a0e  xor     rcx, rsp; StackCookie
0x180046a11  call    __security_check_cookie
0x180046a16  add     rsp, 0A0h
0x180046a1d  pop     r14
0x180046a1f  pop     rdi
0x180046a20  pop     rsi
0x180046a21  pop     rbx
0x180046a22  pop     rbp
0x180046a23  retn
```
