# sfac_ReadGlyphMetrics(sfac_ClientRec const *,ushort,ushort *,ushort *,short *,short *,short *,uchar)

- ea: `0x14001ac14`
- end: `0x14001afcc`
- name: `?sfac_ReadGlyphMetrics@@YAHPEBUsfac_ClientRec@@GPEAG1PEAF22E@Z`
- size: `952`
- prototype: `__int64 __fastcall(const struct sfac_ClientRec *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, __int16 *, __int16 *, __int16 *, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14002a840`

## callees

- `0x14001a950`
- `0x14001ac14`
- `0x14001afd4`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sfac_ReadGlyphMetrics(
        const struct sfac_ClientRec *a1,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int16 *a5,
        __int16 *a6,
        __int16 *a7,
        char a8)
{
  __int64 v10; // r14
  __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // r8
  __int64 v18; // rdx
  __int16 v19; // r8
  __int16 v20; // ax
  __int16 v21; // r8
  unsigned int GlyphLocation; // edi
  __int16 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned __int16 *v27; // r9
  unsigned int v28; // r10d
  signed __int16 v29; // di
  __int64 v30; // rdx
  __int16 v31; // cx
  __int64 v32; // rdx
  __int64 v33; // [rsp+30h] [rbp-48h] BYREF
  int v34; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v35; // [rsp+3Ch] [rbp-3Ch] BYREF
  __int64 v36; // [rsp+40h] [rbp-38h] BYREF
  const struct sfac_ClientRec *v37; // [rsp+48h] [rbp-30h]
  __int64 v38; // [rsp+50h] [rbp-28h]
  const struct sfac_ClientRec *v39; // [rsp+58h] [rbp-20h]
  __int64 v40; // [rsp+60h] [rbp-18h]

  v10 = a2;
  result = sfac_ReadGlyphHorMetrics(a1, a2, a3, a5);
  if ( (_DWORD)result )
    return result;
  v14 = 0;
  v37 = 0;
  v15 = 0;
  v36 = 0;
  v16 = *((unsigned __int16 *)a1 + 109);
  if ( (unsigned __int16)v10 < (unsigned __int16)v16 )
    v17 = (unsigned int)(4 * v10 + 4);
  else
    v17 = (unsigned int)(2 * (v10 + v16) + 2);
  if ( *((_BYTE *)a1 + 220) && *((_DWORD *)a1 + 49) )
  {
    v18 = *((unsigned int *)a1 + 48);
    if ( (unsigned int)v18 > 0x7FFFFFFF )
      goto LABEL_48;
    v14 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))a1 + 1))(*(_QWORD *)a1, v18, v17, &v36);
    v15 = v36;
  }
  v39 = a1;
  v40 = v15;
  if ( *((_BYTE *)a1 + 220) && v14 )
  {
    if ( (unsigned __int16)v10 < (unsigned __int16)v16 )
    {
      v32 = (unsigned int)(4 * v10);
      *a4 = _byteswap_ushort(*(_WORD *)(v32 + v14));
      v19 = *(unsigned __int8 *)(v32 + v14 + 3);
      v20 = *(unsigned __int8 *)(v32 + v14 + 2);
    }
    else
    {
      *a4 = _byteswap_ushort(*(_WORD *)((unsigned int)(4 * v16) + v14 - 4));
      v19 = *(unsigned __int8 *)(v14 + 2 * (v10 + v16) + 1);
      v20 = *(unsigned __int8 *)(v14 + 2 * (v10 + v16));
    }
    v21 = (v20 << 8) | v19;
    goto LABEL_13;
  }
  LODWORD(v33) = 0;
  v35 = 0;
  v34 = 0;
  GlyphLocation = sfac_GetGlyphLocation(
                    (_DWORD)a1,
                    *((unsigned __int16 *)a1 + 116),
                    (unsigned int)&v35,
                    (unsigned int)&v33,
                    (__int64)&v34);
  if ( GlyphLocation )
    goto LABEL_39;
  v25 = (unsigned int)v33;
  if ( (_DWORD)v33 )
  {
    if ( (unsigned int)v33 < 0xA )
    {
      GlyphLocation = 5133;
      goto LABEL_39;
    }
    v26 = 0;
    v33 = 0;
    if ( !*((_DWORD *)a1 + 2 * v34 + 9) )
    {
      v27 = 0;
      GlyphLocation = 5129;
      goto LABEL_31;
    }
    if ( (unsigned int)v25 <= 0x7FFFFFFF )
    {
      v28 = v35 + *((_DWORD *)a1 + 2 * v34 + 8);
      if ( v28 <= 0x7FFFFFFF && v28 >= v35 )
      {
        v27 = (unsigned __int16 *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))a1 + 1))(
                                    *(_QWORD *)a1,
                                    v28,
                                    (unsigned int)v25,
                                    &v33);
        v26 = v33;
        if ( v27 )
          GlyphLocation = 0;
        else
          GlyphLocation = 5128;
LABEL_31:
        v37 = a1;
        v38 = v26;
        if ( GlyphLocation )
        {
          if ( v26 )
            (*((void (__fastcall **)(__int64))a1 + 2))(v26);
        }
        else
        {
          v29 = _byteswap_ushort(v27[4]);
          v30 = *((unsigned __int8 *)v27 + 6);
          LOWORD(v30) = _byteswap_ushort(v27[3]);
          v31 = _byteswap_ushort(v27[1]);
          if ( (__int16)_byteswap_ushort(v27[2]) <= v29 && v31 <= (__int16)v30 )
          {
            if ( v26 )
              (*((void (__fastcall **)(__int64))a1 + 2))(v26);
            goto LABEL_45;
          }
          if ( v26 )
            (*((void (__fastcall **)(__int64, __int64))a1 + 2))(v26, v30);
          GlyphLocation = 5120;
        }
LABEL_39:
        if ( v15 )
          (*((void (__fastcall **)(__int64))a1 + 2))(v15);
        goto LABEL_16;
      }
    }
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v24, v25);
LABEL_48:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v13, v18);
    __debugbreak();
  }
  v29 = HIWORD(v37);
LABEL_45:
  *a4 = *((_WORD *)a1 + 120) - *((_WORD *)a1 + 121);
  v21 = *((_WORD *)a1 + 120) - v29;
LABEL_13:
  *a6 = v21;
  if ( v15 )
    (*((void (__fastcall **)(__int64))a1 + 2))(v15);
  GlyphLocation = 0;
LABEL_16:
  if ( a8 == 1 )
  {
    v23 = -*((_WORD *)a1 + 121) - (*((__int16 *)a1 + 120) - *((__int16 *)a1 + 121) - *a3) / 2;
  }
  else if ( a8 == 2 )
  {
    v23 = 0;
  }
  else
  {
    v23 = *a3 >> 1;
  }
  *a7 = v23;
  return GlyphLocation;
}

```

## disassembly

```asm
0x14001ac14  push    rbp
0x14001ac16  push    rbx
0x14001ac17  push    rsi
0x14001ac18  push    rdi
0x14001ac19  push    r12
0x14001ac1b  push    r13
0x14001ac1d  push    r14
0x14001ac1f  push    r15
0x14001ac21  mov     rbp, rsp
0x14001ac24  sub     rsp, 78h
0x14001ac28  mov     r12, r9
0x14001ac2b  mov     r13, r8
0x14001ac2e  movzx   r14d, dx
0x14001ac32  mov     rbx, rcx
0x14001ac35  mov     r9, [rbp+arg_20]; __int16 *
0x14001ac39  movzx   edx, r14w; unsigned __int16
0x14001ac3d  call    ?sfac_ReadGlyphHorMetrics@@YAHPEBUsfac_ClientRec@@GPEAGPEAF@Z; sfac_ReadGlyphHorMetrics(sfac_ClientRec const *,ushort,ushort *,short *)
0x14001ac42  test    eax, eax
0x14001ac44  jnz     loc_14001AD4F
0x14001ac4a  xor     r9d, r9d
0x14001ac4d  mov     [rbp+var_30], r9
0x14001ac51  xor     esi, esi
0x14001ac53  mov     [rbp+var_38], rsi
0x14001ac57  movzx   edi, word ptr [rbx+0DAh]
0x14001ac5e  cmp     r14w, di
0x14001ac62  jb      loc_14001AEE7
0x14001ac68  lea     eax, [r14+rdi]
0x14001ac6c  lea     r8d, ds:2[rax*2]
0x14001ac74  cmp     [rbx+0DCh], sil
0x14001ac7b  jz      short loc_14001ACAE
0x14001ac7d  cmp     [rbx+0C4h], esi
0x14001ac83  jbe     short loc_14001ACAE
0x14001ac85  mov     edx, [rbx+0C0h]
0x14001ac8b  cmp     edx, 7FFFFFFFh
0x14001ac91  ja      loc_14001AF32
0x14001ac97  lea     r9, [rbp+var_38]
0x14001ac9b  mov     rcx, [rbx]
0x14001ac9e  mov     rax, [rbx+8]
0x14001aca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aca7  mov     r9, rax
0x14001acaa  mov     rsi, [rbp+var_38]
0x14001acae  mov     [rbp+var_20], rbx
0x14001acb2  mov     [rbp+var_18], rsi
0x14001acb6  cmp     byte ptr [rbx+0DCh], 0
0x14001acbd  jz      loc_14001AD60
0x14001acc3  test    r9, r9
0x14001acc6  jz      loc_14001AD60
0x14001accc  cmp     r14w, di
0x14001acd0  jb      loc_14001AE92
0x14001acd6  lea     eax, ds:0[rdi*4]
0x14001acdd  movzx   edx, byte ptr [rax+r9-3]
0x14001ace3  movzx   eax, byte ptr [rax+r9-4]
0x14001ace9  shl     ax, 8
0x14001aced  or      dx, ax
0x14001acf0  mov     [r12], dx
0x14001acf5  mov     rcx, rdi
0x14001acf8  add     rcx, rcx
0x14001acfb  sub     rcx, rdi
0x14001acfe  add     rcx, r14
0x14001ad01  movzx   r8d, byte ptr [r9+rcx*2+1]
0x14001ad07  movzx   eax, byte ptr [r9+rcx*2]
0x14001ad0c  shl     ax, 8
0x14001ad10  or      r8w, ax
0x14001ad14  mov     rax, [rbp+arg_28]
0x14001ad18  mov     [rax], r8w
0x14001ad1c  test    rsi, rsi
0x14001ad1f  jnz     loc_14001AF70
0x14001ad25  xor     edi, edi
0x14001ad27  mov     al, [rbp+arg_38]
0x14001ad2d  cmp     al, 1
0x14001ad2f  jz      loc_14001AF38
0x14001ad35  mov     ecx, 2
0x14001ad3a  cmp     al, cl
0x14001ad3c  jnz     loc_14001AFBE
0x14001ad42  xor     r8d, r8d
0x14001ad45  mov     rcx, [rbp+arg_30]
0x14001ad49  mov     [rcx], r8w
0x14001ad4d  mov     eax, edi
0x14001ad4f  add     rsp, 78h
0x14001ad53  pop     r15
0x14001ad55  pop     r14
0x14001ad57  pop     r13
0x14001ad59  pop     r12
0x14001ad5b  pop     rdi
0x14001ad5c  pop     rsi
0x14001ad5d  pop     rbx
0x14001ad5e  pop     rbp
0x14001ad5f  retn
0x14001ad60  mov     dword ptr [rbp+var_48], 0
0x14001ad67  mov     [rbp+var_3C], 0
0x14001ad6e  mov     [rbp+var_40], 0
0x14001ad75  lea     rax, [rbp+var_40]
0x14001ad79  mov     [rsp+78h+var_58], rax
0x14001ad7e  lea     r9, [rbp+var_48]
0x14001ad82  lea     r8, [rbp+var_3C]
0x14001ad86  movzx   edx, word ptr [rbx+0E8h]
0x14001ad8d  mov     rcx, rbx
0x14001ad90  call    sfac_GetGlyphLocation
0x14001ad95  mov     edi, eax
0x14001ad97  test    eax, eax
0x14001ad99  jnz     loc_14001AECD
0x14001ad9f  mov     edx, dword ptr [rbp+var_48]
0x14001ada2  test    edx, edx
0x14001ada4  jz      loc_14001AF26
0x14001adaa  cmp     edx, 0Ah
0x14001adad  jb      loc_14001AF81
0x14001adb3  xor     r8d, r8d
0x14001adb6  mov     [rbp+var_48], r8
0x14001adba  test    edx, edx
0x14001adbc  jz      short loc_14001ADC9
0x14001adbe  movsxd  rax, [rbp+var_40]
0x14001adc2  cmp     [rbx+rax*8+24h], r8d
0x14001adc7  ja      short loc_14001ADD3
0x14001adc9  xor     r9d, r9d
0x14001adcc  mov     edi, 1409h
0x14001add1  jmp     short loc_14001AE26
0x14001add3  mov     r8d, 7FFFFFFFh
0x14001add9  cmp     edx, r8d
0x14001addc  ja      loc_14001AF2C
0x14001ade2  mov     r10d, [rbx+rax*8+20h]
0x14001ade7  add     r10d, [rbp+var_3C]
0x14001adeb  cmp     r10d, r8d
0x14001adee  ja      loc_14001AF2C
0x14001adf4  cmp     r10d, [rbp+var_3C]
0x14001adf8  jb      loc_14001AF2C
0x14001adfe  lea     r9, [rbp+var_48]
0x14001ae02  mov     r8d, edx
0x14001ae05  mov     edx, r10d
0x14001ae08  mov     rcx, [rbx]
0x14001ae0b  mov     rax, [rbx+8]
0x14001ae0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae14  mov     r9, rax
0x14001ae17  mov     r8, [rbp+var_48]
0x14001ae1b  test    rax, rax
0x14001ae1e  jz      loc_14001AF66
0x14001ae24  xor     edi, edi
0x14001ae26  mov     [rbp+var_30], rbx
0x14001ae2a  mov     [rbp+var_28], r8
0x14001ae2e  test    edi, edi
0x14001ae30  jnz     loc_14001AEC4
0x14001ae36  movzx   r10d, byte ptr [r9+4]
0x14001ae3b  shl     r10w, 8
0x14001ae40  movzx   eax, byte ptr [r9+5]
0x14001ae45  or      r10w, ax
0x14001ae49  movzx   edi, byte ptr [r9+8]
0x14001ae4e  shl     di, 8
0x14001ae52  movzx   eax, byte ptr [r9+9]
0x14001ae57  or      di, ax
0x14001ae5a  movzx   edx, byte ptr [r9+6]
0x14001ae5f  shl     dx, 8
0x14001ae63  movzx   eax, byte ptr [r9+7]
0x14001ae68  or      dx, ax
0x14001ae6b  movzx   ecx, byte ptr [r9+2]
0x14001ae70  shl     cx, 8
0x14001ae74  movzx   eax, byte ptr [r9+3]
0x14001ae79  or      cx, ax
0x14001ae7c  cmp     r10w, di
0x14001ae80  jle     short loc_14001AEF4
0x14001ae82  test    r8, r8
0x14001ae85  jnz     loc_14001AF8B
0x14001ae8b  mov     edi, 1400h
0x14001ae90  jmp     short loc_14001AECD
0x14001ae92  lea     eax, ds:0[r14*4]
0x14001ae9a  mov     edx, eax
0x14001ae9c  movzx   ecx, byte ptr [rax+r9]
0x14001aea1  shl     cx, 8
0x14001aea5  movzx   eax, byte ptr [rax+r9+1]
0x14001aeab  or      cx, ax
0x14001aeae  mov     [r12], cx
0x14001aeb3  movzx   r8d, byte ptr [rdx+r9+3]
0x14001aeb9  movzx   eax, byte ptr [rdx+r9+2]
0x14001aebf  jmp     loc_14001AD0C
0x14001aec4  test    r8, r8
0x14001aec7  jnz     loc_14001AF9C
0x14001aecd  test    rsi, rsi
0x14001aed0  jz      loc_14001AD27
0x14001aed6  mov     rcx, rsi
0x14001aed9  mov     rax, [rbx+10h]
0x14001aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aee2  jmp     loc_14001AD27
0x14001aee7  lea     r8d, ds:4[r14*4]
0x14001aeef  jmp     loc_14001AC74
0x14001aef4  cmp     cx, dx
0x14001aef7  jg      short loc_14001AE82
0x14001aef9  test    r8, r8
0x14001aefc  jnz     loc_14001AFAD
0x14001af02  movzx   eax, word ptr [rbx+0F0h]
0x14001af09  sub     ax, [rbx+0F2h]
0x14001af10  mov     [r12], ax
0x14001af15  movzx   r8d, word ptr [rbx+0F0h]
0x14001af1d  sub     r8w, di
0x14001af21  jmp     loc_14001AD14
0x14001af26  movzx   edi, word ptr [rbp+var_30+6]
0x14001af2a  jmp     short loc_14001AF02
0x14001af2c  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001af31  nop
0x14001af32  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001af37  int     3; Trap to Debugger
0x14001af38  movsx   r8d, word ptr [rbx+0F2h]
0x14001af40  movsx   eax, word ptr [rbx+0F0h]
0x14001af47  sub     eax, r8d
0x14001af4a  movzx   ecx, word ptr [r13+0]
0x14001af4f  sub     eax, ecx
0x14001af51  cdq
0x14001af52  mov     ecx, 2
0x14001af57  idiv    ecx
0x14001af59  neg     r8w
0x14001af5d  sub     r8w, ax
0x14001af61  jmp     loc_14001AD45
0x14001af66  mov     edi, 1408h
0x14001af6b  jmp     loc_14001AE26
0x14001af70  mov     rcx, rsi
0x14001af73  mov     rax, [rbx+10h]
0x14001af77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af7c  jmp     loc_14001AD25
0x14001af81  mov     edi, 140Dh
0x14001af86  jmp     loc_14001AECD
0x14001af8b  mov     rcx, r8
0x14001af8e  mov     rax, [rbx+10h]
0x14001af92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af97  jmp     loc_14001AE8B
0x14001af9c  mov     rcx, r8
0x14001af9f  mov     rax, [rbx+10h]
0x14001afa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001afa8  jmp     loc_14001AECD
0x14001afad  mov     rcx, r8
0x14001afb0  mov     rax, [rbx+10h]
0x14001afb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001afb9  jmp     loc_14001AF02
0x14001afbe  movzx   r8d, word ptr [r13+0]
0x14001afc3  shr     r8w, 1
0x14001afc7  jmp     loc_14001AD45
```
