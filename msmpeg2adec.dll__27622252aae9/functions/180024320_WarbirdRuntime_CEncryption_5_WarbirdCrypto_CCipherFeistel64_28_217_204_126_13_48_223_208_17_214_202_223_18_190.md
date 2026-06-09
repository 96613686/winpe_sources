# WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)

- ea: `0x180024320`
- end: `0x1800246f5`
- name: `?Encrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z`
- size: `981`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022f00`

## callees

- `0x1800017b0`
- `0x180024320`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt(
        unsigned __int64 a1,
        unsigned __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        _BYTE *a6)
{
  int v7; // ebp
  char v8; // al
  int v9; // esi
  __int64 v10; // rdi
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r15
  unsigned __int16 v14; // cx
  unsigned __int64 v15; // r12
  unsigned __int64 *v16; // rbx
  unsigned __int64 v17; // r13
  unsigned int v18; // edx
  int v19; // r8d
  int v20; // ecx
  int v21; // edx
  unsigned int v22; // r8d
  int v23; // r10d
  int v24; // edx
  int v25; // ecx
  int v26; // esi
  char *v27; // rdx
  int v28; // ebp
  __int64 v29; // rcx
  unsigned __int64 *v30; // r8
  char v31; // al
  char *v32; // rdx
  __int64 v33; // rcx
  unsigned __int64 *v34; // r8
  unsigned __int64 *v35; // r10
  __int64 v36; // rdx
  char v37; // cl
  unsigned __int64 v38; // r14
  unsigned __int64 *v39; // rdx
  int v40; // r11d
  unsigned __int64 v41; // rdi
  int v42; // r8d
  int v43; // r10d
  int v44; // edx
  unsigned int v45; // r11d
  int v46; // ebx
  int v47; // r8d
  int v48; // r10d
  unsigned int v49; // edx
  int v50; // r8d
  unsigned __int64 *v51; // rdx
  unsigned __int64 v52; // rbp
  unsigned __int64 v53; // [rsp+0h] [rbp-78h] BYREF
  int v54; // [rsp+8h] [rbp-70h]
  int v55; // [rsp+Ch] [rbp-6Ch]
  unsigned __int64 v56; // [rsp+10h] [rbp-68h] BYREF
  unsigned __int64 *v57; // [rsp+18h] [rbp-60h]
  unsigned __int64 v58; // [rsp+20h] [rbp-58h]
  unsigned __int64 *v59; // [rsp+28h] [rbp-50h]

  if ( a3 )
  {
    v7 = a5;
    v8 = *(_BYTE *)(a3 + a1 - 1);
    v9 = ~a5;
    v53 = a1;
    v57 = a2;
    v55 = a4;
    *a6 = v8;
    v10 = a3 & 7;
    if ( (a3 & 7) != 0 )
    {
      v13 = HIDWORD(a4);
      v17 = HIWORD(a4);
      v15 = a4 >> 16;
      v18 = v9 ^ (WORD2(a4) * (WORD1(a4) + __ROR4__(v9, 13)));
      v54 = (unsigned __int16)a4;
      v19 = a5 ^ (v18 >> 15) ^ ((unsigned __int16)a4 * (WORD1(a4) ^ v18));
      v20 = v18 ^ (v19 - HIWORD(a4) - a4);
      v21 = v19 ^ (__ROR4__(v20, 5) + WORD2(a4) * __ROR4__(a4 ^ v20, 2));
      v22 = v20 ^ __ROR4__(v21, 4) ^ (WORD1(a4) * __ROL4__((unsigned __int16)a4 ^ v21, 7));
      v23 = v21 ^ (v22 >> 13) ^ ((unsigned __int16)a4 * __ROL4__(v22 - HIWORD(a4), 2));
      v24 = v22 ^ __ROR4__(v23, 14) ^ (HIWORD(a4) * __ROR4__(v23 - a4, 11));
      v11 = v53;
      v25 = v23 ^ (WORD2(a4) * __ROR4__(a4 ^ v24, 17) - __ROR4__(v24, 7));
      v26 = v24 ^ (__ROR4__(v25, 23) + WORD1(a4) * __ROR4__(HIDWORD(a4) - v25, 7));
      v27 = (char *)v53;
      v28 = v25 ^ v26 ^ a4 ^ HIDWORD(a4);
      v29 = v10;
      v58 = 0;
      v56 = 0;
      v30 = &v56;
      do
      {
        v31 = *v27++;
        *(_BYTE *)v30 = v31;
        v30 = (unsigned __int64 *)((char *)v30 + 1);
        --v29;
      }
      while ( v29 );
      v7 = HIDWORD(v56) ^ v28;
      v12 = v56;
      v32 = (char *)&v53 + v10;
      v9 = v56 ^ v26;
      v53 = __PAIR64__(v7, v9);
      v33 = 8 - v10;
      if ( v10 != 8 )
      {
        do
        {
          *v32++ = 0;
          --v33;
        }
        while ( v33 );
        v7 = HIDWORD(v53);
        v9 = v53;
      }
      v16 = v57;
      v34 = &v53;
      v35 = v57;
      v36 = v10;
      do
      {
        v37 = *(_BYTE *)v34;
        v34 = (unsigned __int64 *)((char *)v34 + 1);
        *(_BYTE *)v35 = v37;
        v35 = (unsigned __int64 *)((char *)v35 + 1);
        --v36;
      }
      while ( v36 );
      v14 = v54;
    }
    else
    {
      v11 = v53;
      v12 = 0;
      v13 = HIDWORD(a4);
      v14 = a4;
      v15 = a4 >> 16;
      v16 = a2;
      v58 = 0;
      v17 = HIWORD(a4);
    }
    v38 = a3 >> 3;
    v57 = (unsigned __int64 *)((char *)v16 + v10);
    v39 = (unsigned __int64 *)(v10 + v11);
    if ( v38 )
    {
      v40 = (unsigned __int16)v13;
      LODWORD(v56) = (unsigned __int16)v13;
      v54 = v14;
      do
      {
        v41 = *v39;
        v59 = v39 + 1;
        v42 = v7 ^ v9 ^ v41 ^ a4 ^ v13 ^ HIDWORD(v41);
        v43 = v9 ^ v41 ^ (__ROR4__(v42, 23) + (unsigned __int16)v15 * __ROR4__(v13 - v42, 7));
        v44 = v42 ^ (v40 * __ROR4__(v55 ^ v43, 17) - __ROR4__(v43, 7));
        v45 = v43 ^ __ROR4__(v44, 14) ^ (v17 * __ROR4__(v44 - v55, 11));
        v46 = v44 ^ (v45 >> 13) ^ (v54 * __ROL4__(v45 - v17, 2));
        v47 = v45 ^ __ROR4__(v46, 4) ^ ((unsigned __int16)v15 * __ROL4__(v54 ^ v46, 7));
        v40 = v56;
        v48 = v46 ^ (__ROR4__(v47, 5) + v56 * __ROR4__(v55 ^ v47, 2));
        v49 = v47 ^ (v48 - v17 - v55);
        v50 = v48 ^ (v49 >> 15) ^ (v54 * ((unsigned __int16)v15 ^ v49));
        v9 = v12 ^ v49 ^ (v56 * ((unsigned __int16)v15 + __ROR4__(~v50, 13)));
        LODWORD(v53) = v9;
        v51 = v57;
        v52 = HIDWORD(v12);
        v12 = v41;
        v7 = v50 ^ v52;
        HIDWORD(v53) = v7;
        *v57 = v53;
        v57 = v51 + 1;
        v39 = v59;
        ++v58;
      }
      while ( v58 < v38 );
    }
  }
}

```

## disassembly

```asm
0x180024320  test    r8, r8
0x180024323  jz      locret_1800246F3
0x180024329  mov     r11, rsp
0x18002432c  push    r14
0x18002432e  sub     rsp, 70h
0x180024332  mov     rax, cs:__security_cookie
0x180024339  xor     rax, rsp
0x18002433c  mov     [rsp+78h+var_48], rax
0x180024341  mov     [r11+8], rbx
0x180024345  mov     rax, rcx
0x180024348  mov     [r11-10h], rbp
0x18002434c  mov     r14, r8
0x18002434f  mov     ebp, [rsp+78h+arg_20]
0x180024356  mov     [r11-18h], rsi
0x18002435a  mov     esi, ebp
0x18002435c  movzx   eax, byte ptr [r8+rax-1]
0x180024362  not     esi
0x180024364  mov     [r11-20h], rdi
0x180024368  mov     rdi, r8
0x18002436b  mov     [r11-28h], r12
0x18002436f  mov     r12, r9
0x180024372  mov     [r11-30h], r13
0x180024376  mov     r13, r9
0x180024379  mov     [rsp+78h+var_78], rcx
0x18002437d  mov     rcx, [rsp+78h+arg_28]
0x180024385  mov     [r11-38h], r15
0x180024389  mov     r15, r9
0x18002438c  mov     [rsp+78h+var_60], rdx
0x180024391  mov     [rsp+78h+var_6C], r9d
0x180024396  mov     [rcx], al
0x180024398  and     edi, 7
0x18002439b  jnz     short loc_1800243C0
0x18002439d  mov     r11, [rsp+78h+var_78]
0x1800243a1  xor     eax, eax
0x1800243a3  shr     r15, 20h
0x1800243a7  movzx   ecx, r9w
0x1800243ab  shr     r12, 10h
0x1800243af  mov     rbx, rdx
0x1800243b2  mov     [rsp+78h+var_58], rax
0x1800243b7  shr     r13, 30h
0x1800243bb  jmp     loc_180024549
0x1800243c0  mov     edx, esi
0x1800243c2  shr     r15, 20h
0x1800243c6  ror     edx, 0Dh
0x1800243c9  movzx   r11d, r15w
0x1800243cd  shr     r13, 30h
0x1800243d1  shr     r12, 10h
0x1800243d5  movzx   ebx, r12w
0x1800243d9  add     edx, ebx
0x1800243db  imul    edx, r11d
0x1800243df  xor     edx, esi
0x1800243e1  movzx   esi, r9w
0x1800243e5  mov     eax, edx
0x1800243e7  mov     [rsp+78h+var_70], esi
0x1800243eb  mov     r8d, edx
0x1800243ee  shr     eax, 0Fh
0x1800243f1  xor     r8d, ebx
0x1800243f4  imul    r8d, esi
0x1800243f8  xor     r8d, eax
0x1800243fb  xor     r8d, ebp
0x1800243fe  mov     ebp, r15d
0x180024401  mov     ecx, r8d
0x180024404  xor     ebp, r9d
0x180024407  sub     ecx, r13d
0x18002440a  sub     ecx, r9d
0x18002440d  xor     ecx, edx
0x18002440f  mov     edx, ecx
0x180024411  mov     eax, ecx
0x180024413  xor     edx, r9d
0x180024416  ror     eax, 5
0x180024419  ror     edx, 2
0x18002441c  imul    edx, r11d
0x180024420  add     edx, eax
0x180024422  xor     edx, r8d
0x180024425  mov     eax, edx
0x180024427  mov     r8d, edx
0x18002442a  xor     r8d, esi
0x18002442d  ror     eax, 4
0x180024430  rol     r8d, 7
0x180024434  imul    r8d, ebx
0x180024438  xor     r8d, eax
0x18002443b  xor     r8d, ecx
0x18002443e  mov     eax, r8d
0x180024441  mov     r10d, r8d
0x180024444  shr     eax, 0Dh
0x180024447  sub     r10d, r13d
0x18002444a  rol     r10d, 2
0x18002444e  imul    r10d, esi
0x180024452  mov     esi, r15d
0x180024455  xor     r10d, eax
0x180024458  xor     r10d, edx
0x18002445b  mov     edx, r10d
0x18002445e  mov     eax, r10d
0x180024461  sub     edx, r9d
0x180024464  ror     eax, 0Eh
0x180024467  ror     edx, 0Bh
0x18002446a  imul    edx, r13d
0x18002446e  xor     edx, eax
0x180024470  xor     edx, r8d
0x180024473  mov     ecx, edx
0x180024475  mov     eax, edx
0x180024477  xor     ecx, r9d
0x18002447a  ror     eax, 7
0x18002447d  ror     ecx, 11h
0x180024480  imul    ecx, r11d
0x180024484  mov     r11, [rsp+78h+var_78]
0x180024488  sub     ecx, eax
0x18002448a  xor     ecx, r10d
0x18002448d  sub     esi, ecx
0x18002448f  mov     eax, ecx
0x180024491  ror     esi, 7
0x180024494  imul    esi, ebx
0x180024497  ror     eax, 17h
0x18002449a  add     esi, eax
0x18002449c  xor     esi, edx
0x18002449e  mov     rdx, r11
0x1800244a1  xor     ebp, esi
0x1800244a3  xor     ebp, ecx
0x1800244a5  mov     rcx, rdi
0x1800244a8  xor     eax, eax
0x1800244aa  mov     [rsp+78h+var_58], rax
0x1800244af  mov     [rsp+78h+var_68], rax
0x1800244b4  lea     r8, [rsp+78h+var_68]
0x1800244b9  nop     dword ptr [rax+00000000h]
0x1800244c0  movzx   eax, byte ptr [rdx]
0x1800244c3  lea     rdx, [rdx+1]
0x1800244c7  mov     [r8], al
0x1800244ca  lea     r8, [r8+1]
0x1800244ce  sub     rcx, 1
0x1800244d2  jnz     short loc_1800244C0
0x1800244d4  xor     ebp, dword ptr [rsp+78h+var_68+4]
0x1800244d8  lea     rdx, [rsp+78h+var_78]
0x1800244dc  mov     rax, [rsp+78h+var_68]
0x1800244e1  lea     rdx, [rdx+rdi]
0x1800244e5  xor     esi, eax
0x1800244e7  mov     dword ptr [rsp+78h+var_78+4], ebp
0x1800244eb  mov     ecx, 8
0x1800244f0  mov     dword ptr [rsp+78h+var_78], esi
0x1800244f3  sub     rcx, rdi
0x1800244f6  jz      short loc_180024514
0x1800244f8  nop     dword ptr [rax+rax+00000000h]
0x180024500  mov     byte ptr [rdx], 0
0x180024503  lea     rdx, [rdx+1]
0x180024507  sub     rcx, 1
0x18002450b  jnz     short loc_180024500
0x18002450d  mov     ebp, dword ptr [rsp+78h+var_78+4]
0x180024511  mov     esi, dword ptr [rsp+78h+var_78]
0x180024514  mov     rbx, [rsp+78h+var_60]
0x180024519  lea     r8, [rsp+78h+var_78]
0x18002451d  mov     r10, rbx
0x180024520  mov     rdx, rdi
0x180024523  nop     dword ptr [rax+00h]
0x180024527  nop     word ptr [rax+rax+00000000h]
0x180024530  movzx   ecx, byte ptr [r8]
0x180024534  lea     r8, [r8+1]
0x180024538  mov     [r10], cl
0x18002453b  lea     r10, [r10+1]
0x18002453f  sub     rdx, 1
0x180024543  jnz     short loc_180024530
0x180024545  mov     ecx, [rsp+78h+var_70]
0x180024549  shr     r14, 3
0x18002454d  lea     r8, [rdi+rbx]
0x180024551  mov     [rsp+78h+var_60], r8
0x180024556  lea     rdx, [rdi+r11]
0x18002455a  test    r14, r14
0x18002455d  jz      loc_1800246BA
0x180024563  movzx   r11d, r15w
0x180024567  movzx   r8d, cx
0x18002456b  mov     dword ptr [rsp+78h+var_68], r11d
0x180024570  mov     [rsp+78h+var_70], r8d
0x180024575  movzx   r12d, r12w
0x180024579  nop     dword ptr [rax+00000000h]
0x180024580  mov     rdi, [rdx]
0x180024583  mov     r10d, r15d
0x180024586  add     rdx, 8
0x18002458a  mov     r8, rdi
0x18002458d  shr     r8, 20h
0x180024591  xor     r8d, r15d
0x180024594  mov     [rsp+78h+var_50], rdx
0x180024599  xor     r8d, r9d
0x18002459c  mov     edx, edi
0x18002459e  xor     edx, esi
0x1800245a0  mov     esi, [rsp+78h+var_6C]
0x1800245a4  xor     r8d, edx
0x1800245a7  xor     r8d, ebp
0x1800245aa  mov     ebp, [rsp+78h+var_70]
0x1800245ae  sub     r10d, r8d
0x1800245b1  mov     ecx, r8d
0x1800245b4  ror     ecx, 17h
0x1800245b7  ror     r10d, 7
0x1800245bb  imul    r10d, r12d
0x1800245bf  add     r10d, ecx
0x1800245c2  xor     r10d, edx
0x1800245c5  mov     edx, r10d
0x1800245c8  mov     ecx, r10d
0x1800245cb  xor     edx, esi
0x1800245cd  ror     ecx, 7
0x1800245d0  ror     edx, 11h
0x1800245d3  imul    edx, r11d
0x1800245d7  sub     edx, ecx
0x1800245d9  xor     edx, r8d
0x1800245dc  mov     r11d, edx
0x1800245df  mov     ecx, edx
0x1800245e1  sub     r11d, esi
0x1800245e4  ror     ecx, 0Eh
0x1800245e7  ror     r11d, 0Bh
0x1800245eb  imul    r11d, r13d
0x1800245ef  xor     r11d, ecx
0x1800245f2  xor     r11d, r10d
0x1800245f5  mov     ebx, r11d
0x1800245f8  mov     ecx, r11d
0x1800245fb  shr     ecx, 0Dh
0x1800245fe  sub     ebx, r13d
0x180024601  rol     ebx, 2
0x180024604  imul    ebx, ebp
0x180024607  xor     ebx, ecx
0x180024609  xor     ebx, edx
0x18002460b  mov     r8d, ebx
0x18002460e  mov     ecx, ebx
0x180024610  xor     r8d, ebp
0x180024613  ror     ecx, 4
0x180024616  rol     r8d, 7
0x18002461a  imul    r8d, r12d
0x18002461e  xor     r8d, ecx
0x180024621  xor     r8d, r11d
0x180024624  mov     r11d, dword ptr [rsp+78h+var_68]
0x180024629  mov     r10d, r8d
0x18002462c  mov     ecx, r8d
0x18002462f  xor     r10d, esi
0x180024632  ror     ecx, 5
0x180024635  ror     r10d, 2
0x180024639  imul    r10d, r11d
0x18002463d  add     r10d, ecx
0x180024640  xor     r10d, ebx
0x180024643  mov     edx, r10d
0x180024646  sub     edx, r13d
0x180024649  sub     edx, esi
0x18002464b  xor     edx, r8d
0x18002464e  mov     r8d, edx
0x180024651  mov     ecx, edx
0x180024653  xor     r8d, r12d
0x180024656  shr     ecx, 0Fh
0x180024659  imul    r8d, ebp
0x18002465d  xor     r8d, ecx
0x180024660  xor     r8d, r10d
0x180024663  mov     esi, r8d
0x180024666  not     esi
0x180024668  ror     esi, 0Dh
0x18002466b  add     esi, r12d
0x18002466e  imul    esi, r11d
0x180024672  xor     esi, edx
0x180024674  xor     esi, eax
0x180024676  mov     dword ptr [rsp+78h+var_78], esi
0x180024679  mov     rdx, [rsp+78h+var_60]
0x18002467e  mov     rbp, rax
0x180024681  shr     rbp, 20h
0x180024685  mov     rax, rdi
0x180024688  xor     ebp, r8d
0x18002468b  mov     dword ptr [rsp+78h+var_78+4], ebp
0x18002468f  mov     rcx, [rsp+78h+var_78]
0x180024693  mov     [rdx], rcx
0x180024696  add     rdx, 8
0x18002469a  mov     rcx, [rsp+78h+var_58]
0x18002469f  inc     rcx
0x1800246a2  mov     [rsp+78h+var_60], rdx
0x1800246a7  mov     rdx, [rsp+78h+var_50]
0x1800246ac  mov     [rsp+78h+var_58], rcx
0x1800246b1  cmp     rcx, r14
0x1800246b4  jb      loc_180024580
0x1800246ba  mov     r13, [rsp+78h+var_30]
0x1800246bf  mov     r12, [rsp+78h+var_28]
0x1800246c4  mov     r15, [rsp+78h+var_38]
0x1800246c9  mov     rsi, [rsp+78h+var_18]
0x1800246ce  mov     rbp, [rsp+78h+var_10]
0x1800246d3  mov     rbx, [rsp+78h+arg_0]
0x1800246db  mov     rdi, [rsp+78h+var_20]
0x1800246e0  mov     rcx, [rsp+78h+var_48]
0x1800246e5  xor     rcx, rsp; StackCookie
0x1800246e8  call    __security_check_cookie
0x1800246ed  add     rsp, 70h
0x1800246f1  pop     r14
0x1800246f3  retn
```
