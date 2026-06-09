# sub_1802DDCB0

- ea: `0x1802ddcb0`
- end: `0x1802debc1`
- name: `sub_1802DDCB0`
- size: `3857`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x1802dbef0`

## callees

- `0x180003e60`
- `0x180005740`
- `0x180020bc0`
- `0x180020e60`
- `0x180021240`
- `0x180023780`
- `0x1800608c0`
- `0x1800a2a00`
- `0x1801ad7d0`
- `0x1801adc90`
- `0x1801ae334`
- `0x1801ae380`
- `0x180201310`
- `0x18021ecb0`
- `0x1802336a0`
- `0x180234740`
- `0x180237650`
- `0x1802548d0`
- `0x18026a700`
- `0x1802a31b0`
- `0x1802a3200`
- `0x1802a3260`
- `0x1802c9230`
- `0x1802d8180`
- `0x1802d8240`
- `0x1802d82f0`
- `0x1802ddcb0`
- `0x1802debd0`
- `0x1802e0240`
- `0x1802eb6b0`
- `0x18034a060`
- `0x18034d1c0`
- `0x18037b520`

## string_xrefs

- `0x1802de6f7`: `broker_app_used`
- `0x1802de162`: `ImportRefreshToken: GetAllAccounts response is null. User interaction is required to get ATs.`
- `0x1802de28e`: `ImportRefreshToken:broker is present but no accounts exist in broker cache. User interaction is required to get ATs.`
- `0x1802de458`: `ImportRefreshToken:broker is present but account is not found in broker cache. User interaction is required to get ATs.`
- `0x1802de82b`: `ImportRefreshToken:broker is present but AT request failed. User interaction is required to get ATs.`

## pseudocode

```c
__int64 __fastcall sub_1802DDCB0(__int64 a1)
{
  __int64 **v2; // r12
  __int64 **v3; // rbx
  char v4; // r13
  char v5; // al
  __int64 v6; // r14
  bool v7; // di
  __int64 v8; // rax
  __m128i si128; // xmm6
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 result; // rax
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdi
  void (__fastcall *v19)(__int64, _QWORD); // rbx
  unsigned __int8 v20; // al
  char v21; // bl
  __int64 v22; // r14
  void (__fastcall *v23)(__int64, __int128 *, __int64, __int64, char, __int64); // rsi
  char v24; // di
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // r8d
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // r8d
  __int64 v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rbx
  _QWORD *v34; // rsi
  _QWORD *v35; // rax
  _QWORD *v36; // rdx
  __int64 v37; // rax
  _QWORD *v38; // rcx
  char v39; // di
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  int v43; // r8d
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rdi
  void (__fastcall *v47)(__int64, __int64); // rbx
  __int64 v48; // rax
  __int64 *v49; // rsi
  void (__fastcall *v50)(__int64 *, __int128 *, __int128 *); // rdi
  __int64 v51; // rbx
  __int64 *v52; // rdi
  void (__fastcall *v53)(__int64 *, _BYTE *, __int64 *); // rbx
  __int64 *v54; // rcx
  __int64 v55; // rax
  int v56; // r8d
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r9
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rsi
  __int64 v63; // rdi
  int v64; // eax
  __int64 v65; // rax
  __int64 v66; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v67; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v68[24]; // [rsp+50h] [rbp-B0h]
  __int64 v69; // [rsp+68h] [rbp-98h]
  _BYTE v70[14]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v71; // [rsp+8Eh] [rbp-72h]
  __m128i v72; // [rsp+90h] [rbp-70h]
  __int128 v73; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B0h] [rbp-50h]
  __int128 v75; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v76; // [rsp+D0h] [rbp-30h]
  __int128 v77; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v78; // [rsp+F0h] [rbp-10h]
  __int128 v79; // [rsp+100h] [rbp+0h] BYREF
  __int128 v80; // [rsp+110h] [rbp+10h] BYREF
  __m128i v81; // [rsp+120h] [rbp+20h]
  _BYTE v82[8]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v83; // [rsp+138h] [rbp+38h]
  __int128 v84; // [rsp+140h] [rbp+40h] BYREF
  __int128 v85; // [rsp+150h] [rbp+50h] BYREF
  __int128 v86; // [rsp+160h] [rbp+60h] BYREF
  __int128 v87; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v88[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v89; // [rsp+190h] [rbp+90h]
  unsigned __int64 v90; // [rsp+198h] [rbp+98h]
  __int128 v91; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v92; // [rsp+1B0h] [rbp+B0h]
  __int128 v93; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v94; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v95; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v96; // [rsp+1E8h] [rbp+E8h] BYREF

  sub_1801AE334(&word_18064BE06);
  v2 = (__int64 **)(a1 + 112);
  sub_1802A31B0(520712897, a1 + 112);
  v3 = (__int64 **)(a1 + 176);
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 176) + 424LL))(*(_QWORD *)(a1 + 176), 211);
  v5 = sub_1802E0240(a1 + 240, a1 + 176, a1 + 112);
  v86 = 0;
  v6 = *(_QWORD *)(a1 + 88);
  v7 = !v5 || v4;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(**v3 + 288))(*v3, &v66);
  sub_18034D1C0(v6, &v86, v8, v7);
  if ( *(_QWORD *)&v68[8] > 0xFu )
  {
    _mm_lfence();
    sub_180020E60(v66, *(_QWORD *)&v68[8] + 1LL);
  }
  si128 = _mm_load_si128((const __m128i *)&xmmword_18041F110);
  *(__m128i *)v68 = si128;
  LOBYTE(v66) = 0;
  if ( !(_QWORD)v86 )
  {
    sub_1802A31B0(520712898, a1 + 112);
    v73 = 0;
    v74 = 0;
    v10 = sub_180021240(53, 15, 0x7FFFFFFFFFFFFFFFLL);
    *(_QWORD *)&v73 = sub_180003E60(v10 + 1);
    *(_QWORD *)&v74 = 53;
    *((_QWORD *)&v74 + 1) = v10;
    strcpy((char *)v73, "ImportRefreshToken failed to return a valid response.");
    v11 = sub_1802548D0((unsigned int)v82, 520712899, 0, 0, (__int64)&v73);
    v12 = sub_1801AD7D0(496);
    v13 = v12;
    *(_QWORD *)&v80 = v12;
    if ( v12 )
    {
      *(_OWORD *)v12 = 0;
      *(_DWORD *)(v12 + 8) = 1;
      *(_DWORD *)(v12 + 12) = 1;
      *(_QWORD *)v12 = &std::_Ref_count_obj2<Msai::AuthenticationResultInternalImpl>::`vftable';
      sub_1802C9230(v12 + 16, v11);
    }
    else
    {
      v13 = 0;
    }
    *(_QWORD *)&v79 = v13 + 16;
    *((_QWORD *)&v79 + 1) = v13;
    result = sub_1802DEBD0(a1, &v79);
    if ( *((_QWORD *)&v79 + 1) )
      result = sub_180020BC0(*((_QWORD *)&v79 + 1));
    if ( v83 )
      result = sub_180020BC0(v83);
    if ( *((_QWORD *)&v74 + 1) > 0xFu )
    {
      _mm_lfence();
      result = sub_180020E60(v73, *((_QWORD *)&v74 + 1) + 1LL);
    }
    goto LABEL_137;
  }
  v84 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v86 + 24LL))(v86, &v84);
  if ( (_QWORD)v84 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64))(**v3 + 424))(*v3, 210) )
    {
      sub_1802A31B0(520712901, a1 + 112);
      sub_1802336A0(*(_QWORD *)(a1 + 128), &v84, a1 + 176, a1 + 112);
    }
    if ( *(_QWORD *)(a1 + 240) )
    {
      v87 = 0;
      v16 = *v3;
      v17 = **v3;
      v79 = 0;
      (*(void (__fastcall **)(__int64 *, __int128 *, __int128 *))(v17 + 8))(v16, &v87, &v79);
      if ( *((_QWORD *)&v79 + 1) )
        sub_180020BC0(*((_QWORD *)&v79 + 1));
      v18 = v87;
      v19 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 104LL);
      v20 = sub_1802EB6B0();
      v19(v18, v20);
      v21 = *(_BYTE *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *))(**(_QWORD **)(a1 + 240) + 8LL))(
                        *(_QWORD *)(a1 + 240),
                        &v66,
                        &v87);
      if ( *(_QWORD *)&v68[16] > 0xFu )
      {
        _mm_lfence();
        sub_180020E60(v67, *(_QWORD *)&v68[16] + 1LL);
      }
      *(__m128i *)&v68[8] = si128;
      LOBYTE(v67) = 0;
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64 *, __int64))(**v2 + 136))(*v2, 571277977);
        v95 = 0;
        v22 = *(_QWORD *)(a1 + 240);
        v23 = *(void (__fastcall **)(__int64, __int128 *, __int64, __int64, char, __int64))(*(_QWORD *)v22 + 48LL);
        v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 200LL))(*(_QWORD *)(a1 + 24));
        v25 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 176) + 320LL))(*(_QWORD *)(a1 + 176), v70);
        v26 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 176) + 48LL))(
                *(_QWORD *)(a1 + 176),
                &v66);
        v23(v22, &v95, v26, v25, v24, a1 + 112);
        if ( *(_QWORD *)&v68[8] > 0xFu )
        {
          _mm_lfence();
          sub_180020E60(v66, *(_QWORD *)&v68[8] + 1LL);
        }
        *(__m128i *)v68 = si128;
        LOBYTE(v66) = 0;
        if ( (_QWORD)v95 )
        {
          (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v95 + 16LL))(v95, &v79);
          if ( (_QWORD)v79 )
            sub_1802A31B0(520496099, a1 + 112);
          if ( *((_QWORD *)&v79 + 1) )
            sub_180020BC0(*((_QWORD *)&v79 + 1));
          v91 = 0;
          v92 = 0;
          (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v95 + 8LL))(v95, &v91);
          if ( (_QWORD)v91 == *((_QWORD *)&v91 + 1) )
          {
            if ( v4 )
            {
              sub_1802A31B0(520488418, a1 + 112);
              sub_1802DEBD0(a1, &v86);
            }
            else
            {
              sub_180023780(
                &v66,
                "ImportRefreshToken:broker is present but no accounts exist in broker cache. User interaction is required to get ATs.");
              LOBYTE(v30) = 2;
              v31 = sub_1802548D0((unsigned int)&v80, 520712906, v30, 0, (__int64)&v66);
              v32 = sub_1802D82F0(v82, v31, &v84);
              sub_18026A700(&v79, v32);
              sub_1802DEBD0(a1, &v79);
              if ( *((_QWORD *)&v79 + 1) )
                sub_180020BC0(*((_QWORD *)&v79 + 1));
              if ( v83 )
                sub_180020BC0(v83);
              if ( *((_QWORD *)&v80 + 1) )
                sub_180020BC0(*((_QWORD *)&v80 + 1));
              sub_180005740(&v66);
            }
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v84 + 48LL))(v84, v88);
            v85 = 0;
            v34 = (_QWORD *)*((_QWORD *)&v91 + 1);
            v33 = (_QWORD *)v91;
            if ( (_QWORD)v91 != *((_QWORD *)&v91 + 1) )
            {
              while ( 1 )
              {
                v35 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v33 + 48LL))(*v33, &v66);
                v36 = v35;
                if ( v35[3] > 0xFu )
                  v36 = (_QWORD *)*v35;
                v37 = v35[2];
                v38 = v88;
                if ( v90 > 0xF )
                  v38 = (_QWORD *)v88[0];
                *(_QWORD *)&v79 = v36;
                *((_QWORD *)&v79 + 1) = v37;
                *(_QWORD *)&v80 = v38;
                *((_QWORD *)&v80 + 1) = v89;
                v39 = sub_180201310(&v80, &v79);
                if ( *(_QWORD *)&v68[8] > 0xFu )
                {
                  _mm_lfence();
                  sub_180020E60(v66, *(_QWORD *)&v68[8] + 1LL);
                }
                *(__m128i *)v68 = si128;
                LOBYTE(v66) = 0;
                if ( v39 )
                  break;
                v33 += 2;
                if ( v33 == v34 )
                  goto LABEL_70;
              }
              v40 = v33[1];
              if ( v40 )
                _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
              v41 = v33[1];
              *(_QWORD *)&v85 = *v33;
              v42 = *((_QWORD *)&v85 + 1);
              *((_QWORD *)&v85 + 1) = v41;
              if ( v42 )
                sub_180020BC0(v42);
            }
LABEL_70:
            if ( (_QWORD)v85 )
            {
              sub_1802A31B0(520712908, a1 + 112);
              v46 = v85;
              v47 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v85 + 248LL);
              v48 = sub_180237650(*(_QWORD *)(a1 + 128), &v66, &v85, a1 + 112);
              v47(v46, v48);
              if ( *(_QWORD *)&v68[8] )
              {
                sub_180020E60(*(_QWORD *)&v68[8], (v69 - *(_QWORD *)&v68[8]) & 0xFFFFFFFFFFFFFFF8uLL);
                *(_OWORD *)&v68[8] = 0;
                v69 = 0;
              }
              sub_1800608C0(&v67, v67);
              sub_180020E60(v67, 80);
              (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v87 + 112LL))(v87, &v85);
              sub_1802A3260(520712909, a1 + 112, 10);
              v94 = 0;
              (*(void (__fastcall **)(_QWORD, __int128 *, __int128 *, __int64))(**(_QWORD **)(a1 + 240) + 16LL))(
                *(_QWORD *)(a1 + 240),
                &v94,
                &v87,
                a1 + 112);
              v49 = *v2;
              v50 = *(void (__fastcall **)(__int64 *, __int128 *, __int128 *))(**v2 + 112);
              v75 = 0;
              v76 = _mm_load_si128((const __m128i *)&xmmword_180423110);
              strcpy((char *)&v75, "true");
              v80 = 0;
              v81 = 0;
              v51 = sub_180021240(27, 15, 0x7FFFFFFFFFFFFFFFLL);
              *(_QWORD *)&v80 = sub_180003E60(v51 + 1);
              v81.m128i_i64[0] = 27;
              v81.m128i_i64[1] = v51;
              strcpy((char *)v80, "request_eligible_for_broker");
              v50(v49, &v80, &v75);
              if ( v81.m128i_i64[1] > 0xFuLL )
              {
                _mm_lfence();
                sub_180020E60(v80, v81.m128i_i64[1] + 1);
              }
              v81 = si128;
              LOBYTE(v80) = 0;
              if ( v76.m128i_i64[1] > 0xFuLL )
              {
                _mm_lfence();
                sub_180020E60(v75, v76.m128i_i64[1] + 1);
              }
              v76 = si128;
              LOBYTE(v75) = 0;
              v52 = *v2;
              v53 = *(void (__fastcall **)(__int64 *, _BYTE *, __int64 *))(**v2 + 112);
              sub_180023780(&v66, "true");
              v72 = _mm_load_si128((const __m128i *)&xmmword_1804233E0);
              qmemcpy(v70, "broker_app_use", sizeof(v70));
              v71 = (unsigned __int8)aBrokerAppUsed[14];
              v53(v52, v70, &v66);
              if ( v72.m128i_i64[1] > 0xFuLL )
              {
                _mm_lfence();
                sub_180020E60(*(_QWORD *)v70, v72.m128i_i64[1] + 1);
              }
              v72 = si128;
              v70[0] = 0;
              if ( *(_QWORD *)&v68[8] > 0xFu )
              {
                _mm_lfence();
                sub_180020E60(v66, *(_QWORD *)&v68[8] + 1LL);
              }
              *(__m128i *)v68 = si128;
              LOBYTE(v66) = 0;
              v54 = *v2;
              v55 = **v2;
              v77 = 0;
              v78 = _mm_load_si128((const __m128i *)&xmmword_18041F470);
              strcpy((char *)&v77, "Broker");
              (*(void (__fastcall **)(__int64 *, __int128 *))(v55 + 88))(v54, &v77);
              if ( v78.m128i_i64[1] > 0xFuLL )
              {
                _mm_lfence();
                sub_180020E60(v77, v78.m128i_i64[1] + 1);
              }
              LOBYTE(v77) = 0;
              sub_1802A3200(520712910, a1 + 112, 10);
              if ( (_QWORD)v94 )
              {
                sub_1802A31B0(520712912, a1 + 112);
                v96 = 0;
                sub_1802D8180(&v96, &v87, a1 + 112, &v94);
                if ( !v4 )
                {
                  sub_1802A31B0(520487940, a1 + 112);
                  v79 = 0;
                  v60 = *(_QWORD *)(a1 + 96);
                  v61 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v84 + 64LL))(v84, &v66);
                  sub_18021ECB0(v60, &v79, v61);
                  sub_180005740(&v66);
                  v62 = *(_QWORD *)(a1 + 128);
                  v63 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 176) + 48LL))(
                          *(_QWORD *)(a1 + 176),
                          &v75);
                  LODWORD(v60) = v79;
                  v64 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v84 + 48LL))(v84, &v73);
                  sub_180234740(v62, (unsigned int)v82, v64, v60 + 32, v63, 0, a1 + 112);
                  sub_180005740(&v73);
                  sub_180005740(&v75);
                  if ( v83 )
                    sub_180020BC0(v83);
                  if ( *((_QWORD *)&v79 + 1) )
                    sub_180020BC0(*((_QWORD *)&v79 + 1));
                }
                v93 = 0;
                LOBYTE(v59) = 1;
                sub_18034A060(*(_QWORD *)(a1 + 88), &v93, &v96, v59);
                (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v93 + 16LL))(v93, &v80);
                if ( (_QWORD)v80 )
                {
                  sub_1802A31B0(520455071, a1 + 112);
                  if ( v4 )
                  {
                    sub_1802A31B0(520455072, a1 + 112);
                    sub_1802DEBD0(a1, &v86);
                  }
                  else
                  {
                    v65 = sub_1802D8240(v82, &v80, &v85);
                    sub_18026A700(&v79, v65);
                    sub_1802DEBD0(a1, &v79);
                    if ( *((_QWORD *)&v79 + 1) )
                      sub_180020BC0(*((_QWORD *)&v79 + 1));
                    if ( v83 )
                      sub_180020BC0(v83);
                  }
                  if ( *((_QWORD *)&v80 + 1) )
                    sub_180020BC0(*((_QWORD *)&v80 + 1));
                }
                else
                {
                  if ( *((_QWORD *)&v80 + 1) )
                    sub_180020BC0(*((_QWORD *)&v80 + 1));
                  sub_1802DEBD0(a1, &v93);
                }
                if ( *((_QWORD *)&v93 + 1) )
                  sub_180020BC0(*((_QWORD *)&v93 + 1));
                if ( *((_QWORD *)&v96 + 1) )
                  sub_180020BC0(*((_QWORD *)&v96 + 1));
              }
              else if ( v4 )
              {
                sub_1802A31B0(520488448, a1 + 112);
                sub_1802DEBD0(a1, &v86);
              }
              else
              {
                sub_180023780(
                  &v66,
                  "ImportRefreshToken:broker is present but AT request failed. User interaction is required to get ATs.");
                LOBYTE(v56) = 2;
                v57 = sub_1802548D0((unsigned int)&v80, 520712911, v56, 0, (__int64)&v66);
                v58 = sub_1802D82F0(v82, v57, &v84);
                sub_18026A700(&v79, v58);
                sub_1802DEBD0(a1, &v79);
                if ( *((_QWORD *)&v79 + 1) )
                  sub_180020BC0(*((_QWORD *)&v79 + 1));
                if ( v83 )
                  sub_180020BC0(v83);
                if ( *((_QWORD *)&v80 + 1) )
                  sub_180020BC0(*((_QWORD *)&v80 + 1));
                sub_180005740(&v66);
              }
              if ( *((_QWORD *)&v94 + 1) )
                sub_180020BC0(*((_QWORD *)&v94 + 1));
            }
            else if ( v4 )
            {
              sub_1802A31B0(520488419, a1 + 112);
              sub_1802DEBD0(a1, &v86);
            }
            else
            {
              sub_180023780(
                &v66,
                "ImportRefreshToken:broker is present but account is not found in broker cache. User interaction is required to get ATs.");
              LOBYTE(v43) = 2;
              v44 = sub_1802548D0((unsigned int)&v80, 520712907, v43, 0, (__int64)&v66);
              v45 = sub_1802D82F0(v82, v44, &v84);
              sub_18026A700(&v79, v45);
              sub_1802DEBD0(a1, &v79);
              if ( *((_QWORD *)&v79 + 1) )
                sub_180020BC0(*((_QWORD *)&v79 + 1));
              if ( v83 )
                sub_180020BC0(v83);
              if ( *((_QWORD *)&v80 + 1) )
                sub_180020BC0(*((_QWORD *)&v80 + 1));
              sub_180005740(&v66);
            }
            if ( *((_QWORD *)&v85 + 1) )
              sub_180020BC0(*((_QWORD *)&v85 + 1));
            if ( v90 > 0xF )
            {
              _mm_lfence();
              sub_180020E60(v88[0], v90 + 1);
            }
            v89 = 0;
            v90 = 15;
            LOBYTE(v88[0]) = 0;
          }
          result = sub_1800A2A00(&v91);
        }
        else if ( v4 )
        {
          sub_1802A31B0(520488417, a1 + 112);
          result = sub_1802DEBD0(a1, &v86);
        }
        else
        {
          sub_180023780(
            &v73,
            "ImportRefreshToken: GetAllAccounts response is null. User interaction is required to get ATs.");
          LOBYTE(v27) = 2;
          v28 = sub_1802548D0((unsigned int)&v80, 520712904, v27, 0, (__int64)&v73);
          v29 = sub_1802D82F0(v82, v28, &v84);
          sub_18026A700(&v79, v29);
          sub_1802DEBD0(a1, &v79);
          if ( *((_QWORD *)&v79 + 1) )
            sub_180020BC0(*((_QWORD *)&v79 + 1));
          if ( v83 )
            sub_180020BC0(v83);
          if ( *((_QWORD *)&v80 + 1) )
            sub_180020BC0(*((_QWORD *)&v80 + 1));
          result = sub_180005740(&v73);
        }
        if ( *((_QWORD *)&v95 + 1) )
          result = sub_180020BC0(*((_QWORD *)&v95 + 1));
      }
      else
      {
        sub_1802A31B0(520712903, a1 + 112);
        result = sub_1802DEBD0(a1, &v86);
      }
      if ( *((_QWORD *)&v87 + 1) )
        result = sub_180020BC0(*((_QWORD *)&v87 + 1));
      goto LABEL_135;
    }
    v15 = 520712902;
  }
  else
  {
    v15 = 520712900;
  }
  sub_1802A31B0(v15, a1 + 112);
  result = sub_1802DEBD0(a1, &v86);
LABEL_135:
  if ( *((_QWORD *)&v84 + 1) )
    result = sub_180020BC0(*((_QWORD *)&v84 + 1));
LABEL_137:
  if ( *((_QWORD *)&v86 + 1) )
    return sub_180020BC0(*((_QWORD *)&v86 + 1));
  return result;
}

```

## disassembly

```asm
0x1802ddcb0  mov     [rsp-8+arg_8], rbx
0x1802ddcb5  mov     [rsp-8+arg_10], rsi
0x1802ddcba  mov     [rsp-8+arg_18], rdi
0x1802ddcbf  push    rbp
0x1802ddcc0  push    r12
0x1802ddcc2  push    r13
0x1802ddcc4  push    r14
0x1802ddcc6  push    r15
0x1802ddcc8  lea     rbp, [rsp-110h]
0x1802ddcd0  mov     eax, 210h
0x1802ddcd5  call    __alloca_probe
0x1802ddcda  sub     rsp, rax
0x1802ddcdd  movaps  [rsp+230h+var_30], xmm6
0x1802ddce5  mov     rax, cs:__security_cookie
0x1802ddcec  xor     rax, rsp
0x1802ddcef  mov     [rbp+130h+var_38], rax
0x1802ddcf6  mov     r15, rcx
0x1802ddcf9  lea     rcx, word_18064BE06
0x1802ddd00  call    sub_1801AE334
0x1802ddd05  lea     r12, [r15+70h]
0x1802ddd09  mov     rdx, r12
0x1802ddd0c  mov     ecx, 1F0972C1h
0x1802ddd11  call    sub_1802A31B0
0x1802ddd16  lea     rbx, [r15+0B0h]
0x1802ddd1d  mov     rcx, [rbx]
0x1802ddd20  mov     rax, [rcx]
0x1802ddd23  mov     edx, 0D3h
0x1802ddd28  mov     rax, [rax+1A8h]
0x1802ddd2f  call    cs:__guard_dispatch_icall_fptr
0x1802ddd35  movzx   r13d, al
0x1802ddd39  mov     r8, r12
0x1802ddd3c  mov     rdx, rbx
0x1802ddd3f  lea     rcx, [r15+0F0h]
0x1802ddd46  call    sub_1802E0240
0x1802ddd4b  xorps   xmm0, xmm0
0x1802ddd4e  movups  [rbp+130h+var_D0], xmm0
0x1802ddd52  mov     r14, [r15+58h]
0x1802ddd56  test    al, al
0x1802ddd58  jz      short loc_1802DDD63
0x1802ddd5a  test    r13b, r13b
0x1802ddd5d  jnz     short loc_1802DDD63
0x1802ddd5f  xor     edi, edi
0x1802ddd61  jmp     short loc_1802DDD66
0x1802ddd63  mov     dil, 1
0x1802ddd66  mov     rcx, [rbx]
0x1802ddd69  mov     rax, [rcx]
0x1802ddd6c  lea     rdx, [rsp+230h+var_1F0]
0x1802ddd71  mov     rax, [rax+120h]
0x1802ddd78  call    cs:__guard_dispatch_icall_fptr
0x1802ddd7e  nop
0x1802ddd7f  movzx   r9d, dil
0x1802ddd83  mov     r8, rax
0x1802ddd86  lea     rdx, [rbp+130h+var_D0]
0x1802ddd8a  mov     rcx, r14
0x1802ddd8d  call    sub_18034D1C0
0x1802ddd92  nop
0x1802ddd93  cmp     qword ptr [rsp+230h+var_1D8], 0Fh
0x1802ddd99  jbe     short loc_1802DDDB0
0x1802ddd9b  lfence
0x1802ddd9e  mov     rdx, qword ptr [rsp+230h+var_1D8]
0x1802ddda3  inc     rdx
0x1802ddda6  mov     rcx, [rsp+230h+var_1F0]
0x1802dddab  call    sub_180020E60
0x1802dddb0  movdqa  xmm6, cs:xmmword_18041F110
0x1802dddb8  movdqu  xmmword ptr [rsp+50h], xmm6
0x1802dddbe  mov     byte ptr [rsp+230h+var_1F0], 0
0x1802dddc3  mov     rcx, qword ptr [rbp+130h+var_D0]
0x1802dddc7  test    rcx, rcx
0x1802dddca  jnz     loc_1802DDF19
0x1802dddd0  mov     rdx, r12
0x1802dddd3  mov     ecx, 1F0972C2h
0x1802dddd8  call    sub_1802A31B0
0x1802ddddd  xorps   xmm0, xmm0
0x1802ddde0  movups  [rbp+130h+var_190], xmm0
0x1802ddde4  xorps   xmm1, xmm1
0x1802ddde7  movdqu  [rbp+130h+var_180], xmm1
0x1802dddec  mov     edx, 0Fh
0x1802dddf1  mov     ecx, 35h ; '5'
0x1802dddf6  mov     r8, 7FFFFFFFFFFFFFFFh
0x1802dde00  call    sub_180021240
0x1802dde05  mov     rbx, rax
0x1802dde08  lea     rcx, [rax+1]
0x1802dde0c  call    sub_180003E60
0x1802dde11  mov     rdx, rax
0x1802dde14  mov     qword ptr [rbp+130h+var_190], rax
0x1802dde18  mov     qword ptr [rbp+130h+var_180], 35h ; '5'
0x1802dde20  mov     qword ptr [rbp+130h+var_180+8], rbx
0x1802dde24  movups  xmm0, cs:xmmword_1805149E8
0x1802dde2b  movups  xmmword ptr [rax], xmm0
0x1802dde2e  movups  xmm1, cs:xmmword_1805149F8
0x1802dde35  movups  xmmword ptr [rax+10h], xmm1
0x1802dde39  movups  xmm0, cs:xmmword_180514A08
0x1802dde40  movups  xmmword ptr [rax+20h], xmm0
0x1802dde44  mov     ecx, cs:dword_180514A18
0x1802dde4a  mov     [rax+30h], ecx
0x1802dde4d  movzx   eax, cs:byte_180514A1C
0x1802dde54  mov     [rdx+34h], al
0x1802dde57  mov     byte ptr [rdx+35h], 0
0x1802dde5b  lea     rax, [rbp+130h+var_190]
0x1802dde5f  mov     [rsp+230h+var_210], rax
0x1802dde64  xor     r9d, r9d
0x1802dde67  xor     r8d, r8d
0x1802dde6a  mov     edx, 1F0972C3h
0x1802dde6f  lea     rcx, [rbp+130h+var_100]
0x1802dde73  call    sub_1802548D0
0x1802dde78  mov     rdi, rax
0x1802dde7b  mov     ecx, 1F0h
0x1802dde80  call    sub_1801AD7D0
0x1802dde85  mov     rbx, rax
0x1802dde88  mov     qword ptr [rbp+130h+var_120], rax
0x1802dde8c  test    rax, rax
0x1802dde8f  jz      short loc_1802DDEBE
0x1802dde91  xorps   xmm0, xmm0
0x1802dde94  movups  xmmword ptr [rax], xmm0
0x1802dde97  mov     dword ptr [rax+8], 1
0x1802dde9e  mov     dword ptr [rax+0Ch], 1
0x1802ddea5  lea     rax, ??_7?$_Ref_count_obj2@VAuthenticationResultInternalImpl@Msai@@@std@@6B@; const std::_Ref_count_obj2<Msai::AuthenticationResultInternalImpl>::`vftable'
0x1802ddeac  mov     [rbx], rax
0x1802ddeaf  lea     rcx, [rbx+10h]
0x1802ddeb3  mov     rdx, rdi
0x1802ddeb6  call    sub_1802C9230
0x1802ddebb  nop
0x1802ddebc  jmp     short loc_1802DDEC0
0x1802ddebe  xor     ebx, ebx
0x1802ddec0  lea     rax, [rbx+10h]
0x1802ddec4  mov     qword ptr [rbp+130h+var_130], rax
0x1802ddec8  mov     qword ptr [rbp+130h+var_130+8], rbx
0x1802ddecc  lea     rdx, [rbp+130h+var_130]
0x1802dded0  mov     rcx, r15
0x1802dded3  call    sub_1802DEBD0
0x1802dded8  mov     rcx, qword ptr [rbp+130h+var_130+8]
0x1802ddedc  test    rcx, rcx
0x1802ddedf  jz      short loc_1802DDEE7
0x1802ddee1  call    sub_180020BC0
0x1802ddee6  nop
0x1802ddee7  mov     rcx, [rbp+130h+var_F8]
0x1802ddeeb  test    rcx, rcx
0x1802ddeee  jz      short loc_1802DDEF6
0x1802ddef0  call    sub_180020BC0
0x1802ddef5  nop
0x1802ddef6  cmp     qword ptr [rbp+130h+var_180+8], 0Fh
0x1802ddefb  jbe     loc_1802DEB7E
0x1802ddf01  lfence
0x1802ddf04  mov     rdx, qword ptr [rbp+130h+var_180+8]
0x1802ddf08  inc     rdx
0x1802ddf0b  mov     rcx, qword ptr [rbp+130h+var_190]
0x1802ddf0f  call    sub_180020E60
0x1802ddf14  jmp     loc_1802DEB7E
0x1802ddf19  xorps   xmm0, xmm0
0x1802ddf1c  movups  [rbp+130h+var_F0], xmm0
0x1802ddf20  mov     rax, [rcx]
0x1802ddf23  lea     rdx, [rbp+130h+var_F0]
0x1802ddf27  mov     rax, [rax+18h]
0x1802ddf2b  call    cs:__guard_dispatch_icall_fptr
0x1802ddf31  nop
0x1802ddf32  cmp     qword ptr [rbp+130h+var_F0], 0
0x1802ddf37  jnz     short loc_1802DDF40
0x1802ddf39  mov     ecx, 1F0972C4h
0x1802ddf3e  jmp     short loc_1802DDF8E
0x1802ddf40  mov     rcx, [rbx]
0x1802ddf43  mov     rax, [rcx]
0x1802ddf46  mov     edx, 0D2h
0x1802ddf4b  mov     rax, [rax+1A8h]
0x1802ddf52  call    cs:__guard_dispatch_icall_fptr
0x1802ddf58  test    al, al
0x1802ddf5a  jz      short loc_1802DDF7F
0x1802ddf5c  mov     rdx, r12
0x1802ddf5f  mov     ecx, 1F0972C5h
0x1802ddf64  call    sub_1802A31B0
0x1802ddf69  mov     r9, r12
0x1802ddf6c  mov     r8, rbx
0x1802ddf6f  lea     rdx, [rbp+130h+var_F0]
0x1802ddf73  mov     rcx, [r15+80h]
0x1802ddf7a  call    sub_1802336A0
0x1802ddf7f  cmp     qword ptr [r15+0F0h], 0
0x1802ddf87  jnz     short loc_1802DDFA7
0x1802ddf89  mov     ecx, 1F0972C6h
0x1802ddf8e  mov     rdx, r12
0x1802ddf91  call    sub_1802A31B0
0x1802ddf96  lea     rdx, [rbp+130h+var_D0]
0x1802ddf9a  mov     rcx, r15
0x1802ddf9d  call    sub_1802DEBD0
0x1802ddfa2  jmp     loc_1802DEB6F
0x1802ddfa7  xorps   xmm0, xmm0
0x1802ddfaa  movups  [rbp+130h+var_C0], xmm0
0x1802ddfae  mov     rcx, [rbx]
0x1802ddfb1  mov     rax, [rcx]
0x1802ddfb4  movdqu  [rbp+130h+var_130], xmm0
0x1802ddfb9  lea     r8, [rbp+130h+var_130]
0x1802ddfbd  lea     rdx, [rbp+130h+var_C0]
0x1802ddfc1  mov     rax, [rax+8]
0x1802ddfc5  call    cs:__guard_dispatch_icall_fptr
0x1802ddfcb  nop
0x1802ddfcc  mov     rcx, qword ptr [rbp+130h+var_130+8]
0x1802ddfd0  test    rcx, rcx
0x1802ddfd3  jz      short loc_1802DDFDA
0x1802ddfd5  call    sub_180020BC0
0x1802ddfda  mov     rdi, qword ptr [rbp+130h+var_C0]
0x1802ddfde  mov     rax, [rdi]
0x1802ddfe1  mov     rbx, [rax+68h]
0x1802ddfe5  call    sub_1802EB6B0
0x1802ddfea  movzx   edx, al
0x1802ddfed  mov     rcx, rdi
0x1802ddff0  mov     rax, rbx
0x1802ddff3  call    cs:__guard_dispatch_icall_fptr
0x1802ddff9  mov     rcx, [r15+0F0h]
0x1802de000  mov     rax, [rcx]
0x1802de003  lea     r8, [rbp+130h+var_C0]
0x1802de007  lea     rdx, [rsp+230h+var_1F0]
0x1802de00c  mov     rax, [rax+8]
0x1802de010  call    cs:__guard_dispatch_icall_fptr
0x1802de016  movzx   ebx, byte ptr [rax]
0x1802de019  cmp     qword ptr [rsp+230h+var_1D8+8], 0Fh
0x1802de01f  jbe     short loc_1802DE036
0x1802de021  lfence
0x1802de024  mov     rdx, qword ptr [rsp+230h+var_1D8+8]
0x1802de029  inc     rdx
0x1802de02c  mov     rcx, [rsp+230h+var_1E8]
0x1802de031  call    sub_180020E60
0x1802de036  movdqu  [rsp+230h+var_1D8], xmm6
0x1802de03c  mov     byte ptr [rsp+230h+var_1E8], 0
0x1802de041  test    bl, bl
0x1802de043  jnz     short loc_1802DE063
0x1802de045  mov     rdx, r12
0x1802de048  mov     ecx, 1F0972C7h
0x1802de04d  call    sub_1802A31B0
0x1802de052  lea     rdx, [rbp+130h+var_D0]
0x1802de056  mov     rcx, r15
0x1802de059  call    sub_1802DEBD0
0x1802de05e  jmp     loc_1802DEB60
0x1802de063  mov     rcx, [r12]
0x1802de067  mov     rax, [rcx]
0x1802de06a  mov     edx, 220D0299h
0x1802de06f  mov     rax, [rax+88h]
0x1802de076  call    cs:__guard_dispatch_icall_fptr
0x1802de07c  xorps   xmm0, xmm0
0x1802de07f  movups  [rbp+130h+var_58], xmm0
0x1802de086  mov     r14, [r15+0F0h]
0x1802de08d  mov     rax, [r14]
0x1802de090  mov     rsi, [rax+30h]
0x1802de094  mov     rcx, [r15+18h]
0x1802de098  mov     rax, [rcx]
0x1802de09b  mov     rax, [rax+0C8h]
0x1802de0a2  call    cs:__guard_dispatch_icall_fptr
0x1802de0a8  movzx   edi, al
0x1802de0ab  mov     rcx, [r15+0B0h]
0x1802de0b2  mov     rdx, [rcx]
0x1802de0b5  mov     rax, [rdx+140h]
0x1802de0bc  lea     rdx, [rbp+130h+var_1B0]
0x1802de0c0  call    cs:__guard_dispatch_icall_fptr
0x1802de0c6  mov     rbx, rax
0x1802de0c9  mov     rcx, [r15+0B0h]
0x1802de0d0  mov     rdx, [rcx]
0x1802de0d3  mov     rax, [rdx+30h]
0x1802de0d7  lea     rdx, [rsp+230h+var_1F0]
0x1802de0dc  call    cs:__guard_dispatch_icall_fptr
0x1802de0e2  nop
0x1802de0e3  mov     [rsp+230h+var_208], r12
0x1802de0e8  mov     byte ptr [rsp+230h+var_210], dil
0x1802de0ed  mov     r9, rbx
0x1802de0f0  mov     r8, rax
0x1802de0f3  lea     rdx, [rbp+130h+var_58]
0x1802de0fa  mov     rcx, r14
0x1802de0fd  mov     rax, rsi
0x1802de100  call    cs:__guard_dispatch_icall_fptr
0x1802de106  nop
0x1802de107  cmp     qword ptr [rsp+230h+var_1D8], 0Fh
0x1802de10d  jbe     short loc_1802DE124
0x1802de10f  lfence
0x1802de112  mov     rdx, qword ptr [rsp+230h+var_1D8]
0x1802de117  inc     rdx
0x1802de11a  mov     rcx, [rsp+230h+var_1F0]
0x1802de11f  call    sub_180020E60
0x1802de124  movdqu  xmmword ptr [rsp+50h], xmm6
0x1802de12a  mov     byte ptr [rsp+230h+var_1F0], 0
0x1802de12f  mov     rcx, qword ptr [rbp+130h+var_58]
0x1802de136  test    rcx, rcx
0x1802de139  jnz     loc_1802DE1F3
0x1802de13f  test    r13b, r13b
0x1802de142  jz      short loc_1802DE162
0x1802de144  mov     rdx, r12
0x1802de147  mov     ecx, 1F0605E1h
0x1802de14c  call    sub_1802A31B0
0x1802de151  lea     rdx, [rbp+130h+var_D0]
0x1802de155  mov     rcx, r15
0x1802de158  call    sub_1802DEBD0
0x1802de15d  jmp     loc_1802DEB4E
0x1802de162  lea     rdx, aImportrefresht; "ImportRefreshToken: GetAllAccounts resp"...
0x1802de169  lea     rcx, [rbp+130h+var_190]
0x1802de16d  call    sub_180023780
0x1802de172  nop
0x1802de173  lea     rax, [rbp+130h+var_190]
0x1802de177  mov     [rsp+230h+var_210], rax
0x1802de17c  xor     r9d, r9d
0x1802de17f  mov     r8b, 2
0x1802de182  mov     edx, 1F0972C8h
0x1802de187  lea     rcx, [rbp+130h+var_120]
0x1802de18b  call    sub_1802548D0
0x1802de190  nop
0x1802de191  lea     r8, [rbp+130h+var_F0]
  ... truncated ...
```
