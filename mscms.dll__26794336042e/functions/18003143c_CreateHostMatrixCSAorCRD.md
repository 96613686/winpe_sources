# CreateHostMatrixCSAorCRD

- ea: `0x18003143c`
- end: `0x1800317b0`
- name: `CreateHostMatrixCSAorCRD`
- size: `884`
- prototype: `__int64 __fastcall(__int64, __int64 *, _DWORD *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180034008`
- `0x180034560`

## callees

- `0x18002b058`
- `0x18002e5f0`
- `0x180030ca4`
- `0x18003143c`
- `0x1800317b8`
- `0x180031940`
- `0x180036648`
- `0x180037d48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003158d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800315e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003158d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800315e2`

## pseudocode

```c
__int64 __fastcall CreateHostMatrixCSAorCRD(__int64 a1, __int64 *a2, _DWORD *a3, int a4, int a5)
{
  __int64 v9; // r11
  __int64 v10; // r13
  __int64 v11; // rdi
  int v12; // r9d
  __int16 v13; // r10
  int v14; // r11d
  ULONG v16; // ecx
  __int64 v17; // rbx
  BOOL v18; // edi
  int HostTRCInputTable; // eax
  __int64 v20; // rdx
  __int64 i; // rcx
  __int64 v22; // r8
  __int64 j; // rdx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+30h] [rbp-D0h]
  int v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+40h] [rbp-C0h]
  int v30; // [rsp+40h] [rbp-C0h]
  ULONG pulResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+5Ch] [rbp-A4h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  int v37; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  double v40[10]; // [rsp+80h] [rbp-80h] BYREF
  double v41[3]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v42[24]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v43[32]; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)pulResult = 0;
  v38 = 0;
  v39 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  if ( !(unsigned int)GetTag(a1, 0x72545243u, 0xCu, pulResult, &v34, &v37, 0)
    || !(unsigned int)GetTag(a1, 0x67545243u, 0xCu, &v38, &v33, &v36, 0)
    || !(unsigned int)GetTag(a1, 0x62545243u, 0xCu, &v39, &v32, &v35, 0) )
  {
    return 0;
  }
  v9 = *(_QWORD *)pulResult;
  v10 = v39;
  v11 = v38;
  pulResult[0] = 0;
  if ( ULongLongToULong(
         2LL
       * ((2
         * (_byteswap_ulong(*(_DWORD *)(v9 + 8))
          + _byteswap_ulong(*(_DWORD *)(v39 + 8))
          + _byteswap_ulong(*(_DWORD *)(v38 + 8)))
         + 2208)
        / 0xF0
        + 1),
         pulResult) < 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v16 = v12 + pulResult[0];
  if ( a2 )
  {
    v17 = *a2;
    if ( *a2 )
    {
      if ( *a3 < v16 )
      {
        SetLastError(0x7Au);
        return 0;
      }
      *a2 = v17 + 160;
      *a3 -= 160;
      *(_DWORD *)(v17 + 12) = a4;
      *(_DWORD *)v17 = 65696;
      *(_DWORD *)(v17 + 8) = 1482250784;
      *(_BYTE *)(v17 + 42) = 2;
      *(_DWORD *)(v17 + 16) = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)a1 + 68LL));
      *(_DWORD *)(v17 + 20) = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)a1 + 72LL));
      *(_DWORD *)(v17 + 24) = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)a1 + 76LL));
      if ( a5 )
      {
        v29 = v32;
        v27 = v33;
        v24 = v34;
        *(_WORD *)(v17 + 80) = v13;
        *(_BYTE *)(v17 + 40) = 3;
        HostTRCInputTable = CreateHostTRCInputTable((_DWORD)a2, (_DWORD)a3, v17, v14, v24, v11, v27, v10, v29);
        v18 = HostTRCInputTable != 0;
        if ( !HostTRCInputTable )
          return v18;
      }
      else
      {
        v18 = 1;
        v30 = v35;
        v28 = v36;
        v26 = v38;
        v25 = v37;
        *(_WORD *)(v17 + 82) = v13;
        *(_BYTE *)(v17 + 41) = 3;
        if ( !(unsigned int)CreateHostRevTRCInputTable((_DWORD)a2, (_DWORD)a3, v17, v14, v25, v26, v28, v10, v30) )
          return 0;
      }
      if ( !(unsigned int)CreateColorantArray(a1, v41, 1918392666)
        || !(unsigned int)CreateColorantArray(a1, v42, 1733843290)
        || !(unsigned int)CreateColorantArray(a1, v43, 1649957210) )
      {
        v18 = 0;
      }
      v20 = 0;
      while ( v18 )
      {
        v40[v20] = v41[(v20 & 0xFFFFFFF8) + ((3 * (_BYTE)v20) & 7)];
        v20 = (unsigned int)(v20 + 1);
        if ( (unsigned int)v20 >= 9 )
        {
          if ( a5 )
          {
            for ( i = 0; i != 9; ++i )
              *(_DWORD *)(v17 + 4 * i + 44) = (int)(v40[i] * 65536.0);
          }
          else
          {
            InvertColorantArray(v40, v41, 1);
            for ( j = 0; j != 9; j += v22 )
              *(_DWORD *)(v17 + 4 * j + 44) = (int)(v41[j] * 65536.0);
          }
          return v18;
        }
      }
      return v18;
    }
  }
  *a3 = v16;
  return 1;
}

```

## disassembly

```asm
0x18003143c  mov     [rsp-8+arg_18], rbx
0x180031441  push    rbp
0x180031442  push    rsi
0x180031443  push    rdi
0x180031444  push    r12
0x180031446  push    r13
0x180031448  push    r14
0x18003144a  push    r15
0x18003144c  lea     rbp, [rsp-30h]
0x180031451  sub     rsp, 130h
0x180031458  mov     rax, cs:__security_cookie
0x18003145f  xor     rax, rsp
0x180031462  mov     [rbp+60h+var_40], rax
0x180031466  xor     ebx, ebx
0x180031468  lea     rax, [rsp+160h+var_F4]
0x18003146d  mov     [rsp+160h+var_130], rbx
0x180031472  mov     r12d, r9d
0x180031475  mov     [rsp+160h+var_138], rax
0x18003147a  lea     r9, [rsp+160h+pulResult]
0x18003147f  mov     r14, r8
0x180031482  mov     qword ptr [rsp+160h+pulResult], rbx
0x180031487  mov     r15, rdx
0x18003148a  mov     [rsp+160h+var_F0], rbx
0x18003148f  lea     rax, [rsp+160h+var_100]
0x180031494  mov     [rsp+160h+var_E8], rbx
0x180031499  lea     edi, [rbx+0Ch]
0x18003149c  mov     [rsp+160h+var_F4], ebx
0x1800314a0  mov     r8d, edi
0x1800314a3  mov     [rsp+160h+var_F8], ebx
0x1800314a7  mov     edx, 72545243h
0x1800314ac  mov     [rsp+160h+var_FC], ebx
0x1800314b0  mov     rsi, rcx
0x1800314b3  mov     [rsp+160h+var_100], ebx
0x1800314b7  mov     [rsp+160h+var_104], ebx
0x1800314bb  mov     [rsp+160h+var_108], ebx
0x1800314bf  mov     [rsp+160h+var_140], rax
0x1800314c4  call    GetTag
0x1800314c9  test    eax, eax
0x1800314cb  jz      loc_180031593
0x1800314d1  lea     rax, [rsp+160h+var_F8]
0x1800314d6  mov     [rsp+160h+var_130], rbx
0x1800314db  mov     [rsp+160h+var_138], rax
0x1800314e0  lea     r9, [rsp+160h+var_F0]
0x1800314e5  lea     rax, [rsp+160h+var_104]
0x1800314ea  mov     r8d, edi
0x1800314ed  mov     edx, 67545243h
0x1800314f2  mov     [rsp+160h+var_140], rax
0x1800314f7  mov     rcx, rsi
0x1800314fa  call    GetTag
0x1800314ff  test    eax, eax
0x180031501  jz      loc_180031593
0x180031507  lea     rax, [rsp+160h+var_FC]
0x18003150c  mov     [rsp+160h+var_130], rbx
0x180031511  mov     [rsp+160h+var_138], rax
0x180031516  lea     r9, [rsp+160h+var_E8]
0x18003151b  lea     rax, [rsp+160h+var_108]
0x180031520  mov     r8d, edi
0x180031523  mov     edx, 62545243h
0x180031528  mov     [rsp+160h+var_140], rax
0x18003152d  mov     rcx, rsi
0x180031530  call    GetTag
0x180031535  test    eax, eax
0x180031537  jz      short loc_180031593
0x180031539  mov     r11, qword ptr [rsp+160h+pulResult]
0x18003153e  mov     r13, [rsp+160h+var_E8]
0x180031543  mov     rdi, [rsp+160h+var_F0]
0x180031548  mov     [rsp+160h+pulResult], ebx
0x18003154c  mov     r10d, [r11+8]
0x180031550  mov     eax, [r13+8]
0x180031554  mov     ecx, [rdi+8]
0x180031557  bswap   eax
0x180031559  bswap   ecx
0x18003155b  bswap   r10d
0x18003155e  add     eax, r10d
0x180031561  add     ecx, eax
0x180031563  mov     eax, 88888889h
0x180031568  lea     r9d, ds:8A0h[rcx*2]
0x180031570  mul     r9d
0x180031573  shr     edx, 7
0x180031576  lea     ecx, [rdx+1]
0x180031579  add     rcx, rcx; ullOperand
0x18003157c  lea     rdx, [rsp+160h+pulResult]; pulResult
0x180031581  call    ULongLongToULong
0x180031586  test    eax, eax
0x180031588  jns     short loc_1800315BC
0x18003158a  lea     ecx, [rbx+57h]; dwErrCode
0x18003158d  call    cs:__imp_SetLastError
0x180031593  xor     eax, eax
0x180031595  mov     rcx, [rbp+60h+var_40]
0x180031599  xor     rcx, rsp; StackCookie
0x18003159c  call    __security_check_cookie
0x1800315a1  mov     rbx, [rsp+160h+arg_18]
0x1800315a9  add     rsp, 130h
0x1800315b0  pop     r15
0x1800315b2  pop     r14
0x1800315b4  pop     r13
0x1800315b6  pop     r12
0x1800315b8  pop     rdi
0x1800315b9  pop     rsi
0x1800315ba  pop     rbp
0x1800315bb  retn
0x1800315bc  mov     ecx, [rsp+160h+pulResult]
0x1800315c0  add     ecx, r9d
0x1800315c3  test    r15, r15
0x1800315c6  jz      loc_1800317A3
0x1800315cc  mov     rbx, [r15]
0x1800315cf  test    rbx, rbx
0x1800315d2  jz      loc_1800317A3
0x1800315d8  cmp     [r14], ecx
0x1800315db  jnb     short loc_1800315EF
0x1800315dd  mov     ecx, 7Ah ; 'z'; dwErrCode
0x1800315e2  call    cs:__imp_SetLastError
0x1800315e8  xor     edi, edi
0x1800315ea  jmp     loc_18003179C
0x1800315ef  lea     rax, [rbx+0A0h]
0x1800315f6  mov     edx, 1
0x1800315fb  mov     [r15], rax
0x1800315fe  mov     r9, r11
0x180031601  add     dword ptr [r14], 0FFFFFF60h
0x180031608  mov     r8, rbx
0x18003160b  mov     [rbx+0Ch], r12d
0x18003160f  mov     r12d, [rbp+60h+arg_20]
0x180031616  mov     dword ptr [rbx], 100A0h
0x18003161c  mov     dword ptr [rbx+8], 58595A20h
0x180031623  mov     byte ptr [rbx+2Ah], 2
0x180031627  mov     rax, [rsi]
0x18003162a  mov     ecx, [rax+44h]
0x18003162d  bswap   ecx
0x18003162f  mov     [rbx+10h], ecx
0x180031632  mov     rax, [rsi]
0x180031635  mov     ecx, [rax+48h]
0x180031638  bswap   ecx
0x18003163a  mov     [rbx+14h], ecx
0x18003163d  mov     rax, [rsi]
0x180031640  mov     ecx, [rax+4Ch]
0x180031643  bswap   ecx
0x180031645  mov     [rbx+18h], ecx
0x180031648  mov     rcx, r15
0x18003164b  test    r12d, r12d
0x18003164e  jz      short loc_180031695
0x180031650  mov     eax, [rsp+160h+var_108]
0x180031654  mov     rdx, r14
0x180031657  mov     [rsp+160h+var_120], eax
0x18003165b  mov     eax, [rsp+160h+var_104]
0x18003165f  mov     [rsp+160h+var_128], r13
0x180031664  mov     dword ptr [rsp+160h+var_130], eax
0x180031668  mov     eax, [rsp+160h+var_100]
0x18003166c  mov     [rsp+160h+var_138], rdi
0x180031671  mov     dword ptr [rsp+160h+var_140], eax
0x180031675  mov     [rbx+50h], r10w
0x18003167a  mov     byte ptr [rbx+28h], 3
0x18003167e  call    CreateHostTRCInputTable
0x180031683  xor     edi, edi
0x180031685  test    eax, eax
0x180031687  setnz   dil
0x18003168b  test    eax, eax
0x18003168d  jz      loc_18003179C
0x180031693  jmp     short loc_1800316D7
0x180031695  mov     eax, [rsp+160h+var_FC]
0x180031699  mov     edi, edx
0x18003169b  mov     [rsp+160h+var_120], eax
0x18003169f  mov     rdx, r14
0x1800316a2  mov     eax, [rsp+160h+var_F8]
0x1800316a6  mov     [rsp+160h+var_128], r13
0x1800316ab  mov     dword ptr [rsp+160h+var_130], eax
0x1800316af  mov     rax, [rsp+160h+var_F0]
0x1800316b4  mov     [rsp+160h+var_138], rax
0x1800316b9  mov     eax, [rsp+160h+var_F4]
0x1800316bd  mov     dword ptr [rsp+160h+var_140], eax
0x1800316c1  mov     [rbx+52h], r10w
0x1800316c6  mov     byte ptr [rbx+29h], 3
0x1800316ca  call    CreateHostRevTRCInputTable
0x1800316cf  test    eax, eax
0x1800316d1  jz      loc_1800315E8
0x1800316d7  mov     r8d, 7258595Ah
0x1800316dd  lea     rdx, [rbp+60h+var_90]
0x1800316e1  mov     rcx, rsi
0x1800316e4  call    CreateColorantArray
0x1800316e9  test    eax, eax
0x1800316eb  jz      short loc_180031719
0x1800316ed  mov     r8d, 6758595Ah
0x1800316f3  lea     rdx, [rbp+60h+var_78]
0x1800316f7  mov     rcx, rsi
0x1800316fa  call    CreateColorantArray
0x1800316ff  test    eax, eax
0x180031701  jz      short loc_180031719
0x180031703  mov     r8d, 6258595Ah
0x180031709  lea     rdx, [rbp+60h+var_60]
0x18003170d  mov     rcx, rsi
0x180031710  call    CreateColorantArray
0x180031715  test    eax, eax
0x180031717  jnz     short loc_18003171B
0x180031719  xor     edi, edi
0x18003171b  xor     edx, edx
0x18003171d  lea     r8d, [rdx+1]
0x180031721  test    edi, edi
0x180031723  jz      short loc_18003179C
0x180031725  lea     ecx, [rdx+rdx*2]
0x180031728  mov     eax, edx
0x18003172a  and     ecx, 7
0x18003172d  and     eax, 0FFFFFFF8h
0x180031730  add     ecx, eax
0x180031732  mov     rax, [rbp+rcx*8+60h+var_90]
0x180031737  mov     [rbp+rdx*8+60h+var_E0], rax
0x18003173c  add     edx, r8d
0x18003173f  cmp     edx, 9
0x180031742  jb      short loc_180031721
0x180031744  test    r12d, r12d
0x180031747  jz      short loc_18003176D
0x180031749  xor     ecx, ecx
0x18003174b  movsd   xmm0, [rbp+rcx*8+60h+var_E0]
0x180031751  mulsd   xmm0, cs:__real@40f0000000000000
0x180031759  cvttsd2si rax, xmm0
0x18003175e  mov     [rbx+rcx*4+2Ch], eax
0x180031762  add     rcx, r8
0x180031765  cmp     rcx, 9
0x180031769  jnz     short loc_18003174B
0x18003176b  jmp     short loc_18003179C
0x18003176d  lea     rdx, [rbp+60h+var_90]
0x180031771  lea     rcx, [rbp+60h+var_E0]
0x180031775  call    InvertColorantArray
0x18003177a  xor     edx, edx
0x18003177c  movsd   xmm0, [rbp+rdx*8+60h+var_90]
0x180031782  mulsd   xmm0, cs:__real@40f0000000000000
0x18003178a  cvttsd2si rcx, xmm0
0x18003178f  mov     [rbx+rdx*4+2Ch], ecx
0x180031793  add     rdx, r8
0x180031796  cmp     rdx, 9
0x18003179a  jnz     short loc_18003177C
0x18003179c  mov     eax, edi
0x18003179e  jmp     loc_180031595
0x1800317a3  mov     [r14], ecx
0x1800317a6  mov     eax, 1
0x1800317ab  jmp     loc_180031595
```
