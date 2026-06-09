# CDIProperties<ID2D1InkEffect>::SetValueCommon(uint,D2D1_PROPERTY_TYPE,uchar const *,uint)

- ea: `0x18005c730`
- end: `0x18005cce4`
- name: `?SetValueCommon@?$CDIProperties@UID2D1InkEffect@@@@IEAAJIW4D2D1_PROPERTY_TYPE@@PEBEI@Z`
- size: `1460`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005c5e0`
- `0x180183820`

## callees

- `0x18001fd58`
- `0x18005bee0`
- `0x18005c730`
- `0x18005ccf0`
- `0x180178a90`
- `0x18025b100`
- `0x18025c961`
- `0x180307010`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18005cc38`
- `ntdll!DbgPrintEx` at `0x18005cc38`

## string_xrefs

- `0x18005cc0a`: `CDIProperties<struct ID2D1InkEffect>::SetValueCommon`

## pseudocode

```c
__int64 __fastcall CDIProperties<ID2D1InkEffect>::SetValueCommon(
        __int64 a1,
        signed int a2,
        enum D2D1_PROPERTY_TYPE a3,
        float *a4,
        unsigned int Size)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  unsigned int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rcx
  int v15; // ebx
  char v17; // al
  struct IEffectInternal *v18; // rax
  int v19; // eax
  unsigned __int32 v20; // xmm4_4
  float *v21; // rdx
  float *v22; // rcx
  unsigned int v23; // eax
  float v24; // xmm2_4
  unsigned __int32 v25; // xmm4_4
  float *v26; // rdx
  float *v27; // rcx
  unsigned int i; // eax
  float v29; // xmm2_4
  unsigned int v30; // eax
  __int64 v31; // rcx
  unsigned __int32 v32; // xmm4_4
  float *v33; // rdx
  float *v34; // rcx
  unsigned int j; // eax
  float v36; // xmm2_4
  unsigned __int32 v37; // xmm5_4
  float *v38; // rdx
  float *v39; // rcx
  unsigned int v40; // eax
  float v41; // xmm2_4
  unsigned __int32 v42; // xmm5_4
  float *v43; // rdx
  float *v44; // rcx
  int v45; // eax
  float v46; // xmm2_4
  unsigned __int8 Buf2[1024]; // [rsp+60h] [rbp-468h] BYREF

  if ( *(_BYTE *)(a1 + 128) )
  {
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 184LL))(a1);
    if ( v15 >= 0 )
      return 0;
LABEL_17:
    DoStackCapture(v15);
    return (unsigned int)v15;
  }
  if ( a2 < 0 )
    v9 = a2 & 0x7FFFFFFF;
  else
    v9 = a2 + *(_DWORD *)(a1 + 96);
  if ( v9 < *(_DWORD *)(a1 + 80) && *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8LL * v9) )
  {
    _mm_lfence();
    v10 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 8LL * v9) + 104LL) + 16LL);
    if ( v10 != 1 )
    {
      switch ( v10 )
      {
        case 2u:
        case 3u:
        case 4u:
        case 5u:
        case 6u:
        case 7u:
        case 8u:
        case 9u:
        case 0xBu:
        case 0xCu:
        case 0xDu:
        case 0xEu:
        case 0xFu:
        case 0x10u:
        case 0x11u:
          break;
        case 0xAu:
        case 0x12u:
          v11 = Size;
          goto LABEL_66;
        default:
          DbgPrintEx(
            0x65u,
            0,
            "\n*** Assertion failed: %ls%ls%ls\n***   %s%ls%sSource: `%ls:%ld`\n\n",
            L"Unexpected property type",
            &cchOriginalDestLength,
            &cchOriginalDestLength,
            "Function: ",
            L"CDIProperties<struct ID2D1InkEffect>::SetValueCommon",
            ", ",
            L"onecoreuap\\windows\\Direct2D\\DImage\\properties\\DIProperties.inl",
            450);
          __int2c();
          return 0;
      }
    }
    v11 = Size;
    if ( Size >= 0x400
      || (v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1), v13 = v12, v12 >= 0x400)
      || (*(int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int8 *, unsigned int))(*(_QWORD *)a1 + 88LL))(
           a1,
           (unsigned int)a2,
           v10,
           Buf2,
           v12) < 0 )
    {
LABEL_66:
      BatchTrackedObject::OnChange(a1 + 16, 7);
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, float *, unsigned int))(*(_QWORD *)a1 + 184LL))(
              a1,
              (unsigned int)a2,
              (unsigned int)a3,
              a4,
              v11);
LABEL_21:
      v15 = v19;
      if ( v19 >= 0 )
        return 0;
      goto LABEL_17;
    }
    if ( (a3 == D2D1_PROPERTY_TYPE_UNKNOWN || a3 == v10) && Size == v13 )
    {
      if ( v10 == 8 )
      {
        v25 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
        v26 = (float *)Buf2;
        v27 = a4;
        for ( i = 0; i < 4; ++i )
        {
          if ( *v26 == 0.0 )
            v29 = FLOAT_1_0;
          else
            v29 = *v26;
          if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*v27 - *v26) / v29) & v25) >= 0.0000011920929 )
          {
LABEL_18:
            v17 = 0;
            goto LABEL_19;
          }
          ++v27;
          ++v26;
        }
LABEL_38:
        v17 = 1;
LABEL_19:
        if ( !v17 )
          goto LABEL_20;
LABEL_40:
        if ( a2 < 0 )
          v30 = a2 & 0x7FFFFFFF;
        else
          v30 = a2 + *(_DWORD *)(a1 + 96);
        v31 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 8LL * v30) + 104LL);
        if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31) )
          return 0;
        goto LABEL_20;
      }
      if ( v10 != 11 )
      {
        if ( v10 == 17 )
        {
          v32 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
          v33 = (float *)Buf2;
          v34 = a4;
          for ( j = 0; j < 0x14; ++j )
          {
            if ( *v33 == 0.0 )
              v36 = FLOAT_1_0;
            else
              v36 = *v33;
            if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*v34 - *v33) / v36) & v32) >= 0.0000011920929 )
              goto LABEL_18;
            ++v34;
            ++v33;
          }
        }
        else
        {
          switch ( v10 )
          {
            case 1u:
            case 9u:
            case 0xCu:
            case 0xDu:
              if ( !memcmp_0(a4, Buf2, Size) )
                goto LABEL_40;
              goto LABEL_20;
            case 2u:
            case 3u:
            case 4u:
              goto LABEL_39;
            case 5u:
              v42 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
              v43 = (float *)Buf2;
              v44 = a4;
              v45 = 0;
              while ( 2 )
              {
                if ( v45 )
                  goto LABEL_38;
                if ( *v43 == 0.0 )
                  v46 = FLOAT_1_0;
                else
                  v46 = *v43;
                if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*v44 - *v43) / v46) & v42) < 0.0000011920929 )
                {
                  ++v44;
                  ++v43;
                  v45 = 1;
                  continue;
                }
                goto LABEL_18;
              }
            case 6u:
              v17 = CDIProperties<ID2D1InkEffect>::AreFloatPropertiesWithinTolerance(v14, a4, Buf2, 2);
              goto LABEL_19;
            case 7u:
              v17 = CDIProperties<ID2D1InkEffect>::AreFloatPropertiesWithinTolerance(v14, a4, Buf2, 3);
              goto LABEL_19;
            case 0xEu:
              v37 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
              v38 = (float *)Buf2;
              v39 = a4;
              v40 = 0;
              while ( 2 )
              {
                if ( v40 >= 6 )
                  goto LABEL_38;
                if ( *v38 == 0.0 )
                  v41 = FLOAT_1_0;
                else
                  v41 = *v38;
                if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*v39 - *v38) / v41) & v37) < 0.0000011920929 )
                {
                  ++v39;
                  ++v38;
                  ++v40;
                  continue;
                }
                goto LABEL_18;
              }
            case 0xFu:
              v17 = CDIProperties<ID2D1InkEffect>::AreFloatPropertiesWithinTolerance(v14, a4, Buf2, 12);
              goto LABEL_19;
            case 0x10u:
              v20 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
              v21 = (float *)Buf2;
              v22 = a4;
              v23 = 0;
              break;
            default:
              goto LABEL_20;
          }
          while ( v23 < 0x10 )
          {
            if ( *v21 == 0.0 )
              v24 = FLOAT_1_0;
            else
              v24 = *v21;
            if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*v22 - *v21) / v24) & v20) >= 0.0000011920929 )
              goto LABEL_18;
            ++v22;
            ++v21;
            ++v23;
          }
        }
        goto LABEL_38;
      }
LABEL_39:
      if ( *(_DWORD *)a4 == *(_DWORD *)Buf2 )
        goto LABEL_40;
    }
LABEL_20:
    v18 = (struct IEffectInternal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 168LL))(a1);
    v19 = BatchTrackedObject::OnEffectPropertyChange(
            (BatchTrackedObject *)(a1 + 16),
            v18,
            a2,
            a3,
            (const unsigned __int8 *)a4,
            Size,
            Buf2,
            v13);
    goto LABEL_21;
  }
  DoStackCapture(-2003238871);
  DoStackCapture(-2003238871);
  return 2291728425LL;
}

```

## disassembly

```asm
0x18005c730  push    rbx
0x18005c732  push    rbp
0x18005c733  push    rsi
0x18005c734  push    rdi
0x18005c735  push    r12
0x18005c737  push    r13
0x18005c739  push    r14
0x18005c73b  push    r15
0x18005c73d  sub     rsp, 488h
0x18005c744  movaps  [rsp+4C8h+var_58], xmm6
0x18005c74c  mov     rax, cs:__security_cookie
0x18005c753  xor     rax, rsp
0x18005c756  mov     [rsp+4C8h+var_68], rax
0x18005c75e  cmp     byte ptr [rcx+80h], 0
0x18005c765  mov     r12, r9
0x18005c768  mov     r15d, r8d
0x18005c76b  mov     esi, edx
0x18005c76d  mov     rdi, rcx
0x18005c770  jnz     loc_18005C855
0x18005c776  test    edx, edx
0x18005c778  js      loc_18005CA9C
0x18005c77e  mov     eax, [rcx+60h]
0x18005c781  add     eax, edx
0x18005c783  cmp     eax, [rcx+50h]
0x18005c786  jnb     loc_18005C8FD
0x18005c78c  mov     ecx, eax
0x18005c78e  mov     rax, [rdi+48h]
0x18005c792  cmp     qword ptr [rax+rcx*8], 0
0x18005c797  jz      loc_18005C8FD
0x18005c79d  lfence
0x18005c7a0  mov     rax, [rdi+48h]
0x18005c7a4  lea     r13, __ImageBase
0x18005c7ab  mov     rcx, [rax+rcx*8]
0x18005c7af  mov     rax, [rcx+68h]
0x18005c7b3  mov     ebx, [rax+10h]
0x18005c7b6  cmp     ebx, 1
0x18005c7b9  jnz     loc_18005CBCE
0x18005c7bf  mov     ebp, dword ptr [rsp+4C8h+Size]; jumptable 00000001802F8EE4 cases 2-9,11-17
0x18005c7c6  cmp     ebp, 400h
0x18005c7cc  jnb     loc_18005CB75
0x18005c7d2  mov     rax, [rdi]
0x18005c7d5  mov     rcx, rdi
0x18005c7d8  mov     rax, [rax+60h]
0x18005c7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7e1  mov     r14d, eax
0x18005c7e4  cmp     eax, 400h
0x18005c7e9  jnb     loc_18005CB75
0x18005c7ef  mov     rcx, [rdi]
0x18005c7f2  lea     r9, [rsp+4C8h+Buf2]
0x18005c7f7  mov     r8d, ebx
0x18005c7fa  mov     dword ptr [rsp+4C8h+var_4A8], r14d
0x18005c7ff  mov     edx, esi
0x18005c801  mov     rax, [rcx+58h]
0x18005c805  mov     rcx, rdi
0x18005c808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c80d  test    eax, eax
0x18005c80f  js      loc_18005CB75
0x18005c815  test    r15d, r15d
0x18005c818  jnz     loc_18005CC45
0x18005c81e  cmp     ebp, r14d
0x18005c821  jnz     short def_18005C853; jumptable 000000018005C853 default case, cases 8,10,11,17,18
0x18005c823  cmp     ebx, 8
0x18005c826  jz      loc_18005C983
0x18005c82c  cmp     ebx, 0Bh
0x18005c82f  jz      loc_18005C9F3; jumptable 000000018005C853 cases 2-4
0x18005c835  cmp     ebx, 11h
0x18005c838  jz      loc_18005CA35
0x18005c83e  dec     ebx; switch 18 cases
0x18005c840  cmp     ebx, 11h
0x18005c843  ja      short def_18005C853; jumptable 000000018005C853 default case, cases 8,10,11,17,18
0x18005c845  movsxd  rax, ebx
0x18005c848  mov     ecx, ds:(jpt_18005C853 - 180000000h)[r13+rax*4]
0x18005c850  add     rcx, r13
0x18005c853  jmp     rcx; switch jump
0x18005c855  mov     rax, [rcx]
0x18005c858  mov     ecx, dword ptr [rsp+4C8h+Size]
0x18005c85f  mov     dword ptr [rsp+4C8h+var_4A8], ecx
0x18005c863  mov     rcx, rdi
0x18005c866  mov     rax, [rax+0B8h]
0x18005c86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c872  mov     ebx, eax
0x18005c874  test    eax, eax
0x18005c876  jns     short loc_18005C8CF
0x18005c878  mov     ecx, ebx; int
0x18005c87a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005c87f  mov     eax, ebx
0x18005c881  jmp     short loc_18005C8D1
0x18005c883  xor     al, al
0x18005c885  test    al, al
0x18005c887  jnz     loc_18005CA01
0x18005c88d  mov     rax, [rdi]; jumptable 000000018005C853 default case, cases 8,10,11,17,18
0x18005c890  mov     rcx, rdi
0x18005c893  mov     rax, [rax+0A8h]
0x18005c89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c89f  mov     [rsp+4C8h+var_490], r14d; unsigned int
0x18005c8a4  lea     rcx, [rdi+10h]; this
0x18005c8a8  mov     rdx, rax; struct IEffectInternal *
0x18005c8ab  mov     r9d, r15d; enum D2D1_PROPERTY_TYPE
0x18005c8ae  lea     rax, [rsp+4C8h+Buf2]
0x18005c8b3  mov     r8d, esi; unsigned int
0x18005c8b6  mov     [rsp+4C8h+var_498], rax; unsigned __int8 *
0x18005c8bb  mov     [rsp+4C8h+var_4A0], ebp; unsigned int
0x18005c8bf  mov     [rsp+4C8h+var_4A8], r12; unsigned __int8 *
0x18005c8c4  call    ?OnEffectPropertyChange@BatchTrackedObject@@QEAAJPEAVIEffectInternal@@IW4D2D1_PROPERTY_TYPE@@PEBEI2I@Z; BatchTrackedObject::OnEffectPropertyChange(IEffectInternal *,uint,D2D1_PROPERTY_TYPE,uchar const *,uint,uchar const *,uint)
0x18005c8c9  mov     ebx, eax
0x18005c8cb  test    eax, eax
0x18005c8cd  js      short loc_18005C878
0x18005c8cf  xor     eax, eax
0x18005c8d1  mov     rcx, [rsp+4C8h+var_68]
0x18005c8d9  xor     rcx, rsp; StackCookie
0x18005c8dc  call    __security_check_cookie
0x18005c8e1  movaps  xmm6, [rsp+4C8h+var_58]
0x18005c8e9  add     rsp, 488h
0x18005c8f0  pop     r15
0x18005c8f2  pop     r14
0x18005c8f4  pop     r13
0x18005c8f6  pop     r12
0x18005c8f8  pop     rdi
0x18005c8f9  pop     rsi
0x18005c8fa  pop     rbp
0x18005c8fb  pop     rbx
0x18005c8fc  retn
0x18005c8fd  mov     ecx, 88990029h; int
0x18005c902  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005c907  mov     ecx, 88990029h; int
0x18005c90c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005c911  mov     eax, 88990029h
0x18005c916  jmp     short loc_18005C8D1
0x18005c918  movdqa  xmm4, cs:__xmm@7fffffff7fffffff7fffffff7fffffff; jumptable 000000018005C853 case 16
0x18005c920  lea     rdx, [rsp+4C8h+Buf2]
0x18005c925  movss   xmm6, cs:__real@3f800000
0x18005c92d  mov     rcx, r12
0x18005c930  movss   xmm5, cs:__real@35a00000
0x18005c938  xor     eax, eax
0x18005c93a  xorps   xmm3, xmm3
0x18005c93d  nop     dword ptr [rax]
0x18005c940  cmp     eax, 10h
0x18005c943  jnb     loc_18005C9EC
0x18005c949  movss   xmm1, dword ptr [rdx]
0x18005c94d  ucomiss xmm1, xmm3
0x18005c950  movss   xmm0, dword ptr [rcx]
0x18005c954  jp      loc_18005C9E4
0x18005c95a  jnz     loc_18005C9E4
0x18005c960  movaps  xmm2, xmm6
0x18005c963  subss   xmm0, xmm1
0x18005c967  divss   xmm0, xmm2
0x18005c96b  andps   xmm0, xmm4
0x18005c96e  comiss  xmm5, xmm0
0x18005c971  jbe     loc_18005C883
0x18005c977  add     rcx, 4
0x18005c97b  add     rdx, 4
0x18005c97f  inc     eax
0x18005c981  jmp     short loc_18005C940
0x18005c983  movdqa  xmm4, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18005c98b  lea     rdx, [rsp+4C8h+Buf2]
0x18005c990  movss   xmm6, cs:__real@3f800000
0x18005c998  mov     rcx, r12
0x18005c99b  movss   xmm5, cs:__real@35a00000
0x18005c9a3  xor     eax, eax
0x18005c9a5  xorps   xmm3, xmm3
0x18005c9a8  cmp     eax, 4
0x18005c9ab  jnb     short loc_18005C9EC
0x18005c9ad  movss   xmm1, dword ptr [rdx]
0x18005c9b1  ucomiss xmm1, xmm3
0x18005c9b4  movss   xmm0, dword ptr [rcx]
0x18005c9b8  jp      short loc_18005C9DF
0x18005c9ba  jnz     short loc_18005C9DF
0x18005c9bc  movaps  xmm2, xmm6
0x18005c9bf  subss   xmm0, xmm1
0x18005c9c3  divss   xmm0, xmm2
0x18005c9c7  andps   xmm0, xmm4
0x18005c9ca  comiss  xmm5, xmm0
0x18005c9cd  jbe     loc_18005C883
0x18005c9d3  add     rcx, 4
0x18005c9d7  add     rdx, 4
0x18005c9db  inc     eax
0x18005c9dd  jmp     short loc_18005C9A8
0x18005c9df  movaps  xmm2, xmm1
0x18005c9e2  jmp     short loc_18005C9BF
0x18005c9e4  movaps  xmm2, xmm1
0x18005c9e7  jmp     loc_18005C963
0x18005c9ec  mov     al, 1
0x18005c9ee  jmp     loc_18005C885
0x18005c9f3  mov     eax, dword ptr [rsp+4C8h+Buf2]; jumptable 000000018005C853 cases 2-4
0x18005c9f7  cmp     [r12], eax
0x18005c9fb  jnz     def_18005C853; jumptable 000000018005C853 default case, cases 8,10,11,17,18
0x18005ca01  test    esi, esi
0x18005ca03  js      loc_18005CBC3
0x18005ca09  mov     eax, [rdi+60h]
0x18005ca0c  add     eax, esi
0x18005ca0e  mov     ecx, eax
0x18005ca10  mov     rax, [rdi+48h]
0x18005ca14  mov     rcx, [rax+rcx*8]
0x18005ca18  mov     rcx, [rcx+68h]
0x18005ca1c  mov     rax, [rcx]
0x18005ca1f  mov     rax, [rax+18h]
0x18005ca23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca28  test    al, al
0x18005ca2a  jz      loc_18005C8CF
0x18005ca30  jmp     def_18005C853; jumptable 000000018005C853 default case, cases 8,10,11,17,18
0x18005ca35  movdqa  xmm4, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18005ca3d  lea     rdx, [rsp+4C8h+Buf2]
0x18005ca42  movss   xmm6, cs:__real@3f800000
0x18005ca4a  mov     rcx, r12
0x18005ca4d  movss   xmm5, cs:__real@35a00000
0x18005ca55  xor     eax, eax
0x18005ca57  xorps   xmm3, xmm3
0x18005ca5a  nop     word ptr [rax+rax+00h]
0x18005ca60  cmp     eax, 14h
0x18005ca63  jnb     short loc_18005C9EC
0x18005ca65  movss   xmm1, dword ptr [rdx]
0x18005ca69  ucomiss xmm1, xmm3
0x18005ca6c  movss   xmm0, dword ptr [rcx]
0x18005ca70  jp      short loc_18005CA97
0x18005ca72  jnz     short loc_18005CA97
0x18005ca74  movaps  xmm2, xmm6
0x18005ca77  subss   xmm0, xmm1
0x18005ca7b  divss   xmm0, xmm2
0x18005ca7f  andps   xmm0, xmm4
0x18005ca82  comiss  xmm5, xmm0
0x18005ca85  jbe     loc_18005C883
0x18005ca8b  add     rcx, 4
0x18005ca8f  add     rdx, 4
0x18005ca93  inc     eax
0x18005ca95  jmp     short loc_18005CA60
0x18005ca97  movaps  xmm2, xmm1
0x18005ca9a  jmp     short loc_18005CA77
0x18005ca9c  mov     eax, esi
0x18005ca9e  btr     eax, 1Fh
0x18005caa2  jmp     loc_18005C783
0x18005caa7  movdqa  xmm5, cs:__xmm@7fffffff7fffffff7fffffff7fffffff; jumptable 000000018005C853 case 14
0x18005caaf  lea     rdx, [rsp+4C8h+Buf2]
0x18005cab4  movss   xmm4, cs:__real@3f800000
0x18005cabc  mov     rcx, r12
0x18005cabf  movss   xmm6, cs:__real@35a00000
0x18005cac7  xor     eax, eax
0x18005cac9  xorps   xmm3, xmm3
0x18005cacc  nop     dword ptr [rax+00h]
0x18005cad0  cmp     eax, 6
0x18005cad3  jnb     loc_18005C9EC
0x18005cad9  movss   xmm1, dword ptr [rdx]
0x18005cadd  ucomiss xmm1, xmm3
0x18005cae0  movss   xmm0, dword ptr [rcx]
0x18005cae4  jp      short loc_18005CB0B
0x18005cae6  jnz     short loc_18005CB0B
0x18005cae8  movaps  xmm2, xmm4
0x18005caeb  subss   xmm0, xmm1
0x18005caef  divss   xmm0, xmm2
0x18005caf3  andps   xmm0, xmm5
0x18005caf6  comiss  xmm6, xmm0
0x18005caf9  jbe     loc_18005C883
0x18005caff  add     rcx, 4
0x18005cb03  add     rdx, 4
0x18005cb07  inc     eax
0x18005cb09  jmp     short loc_18005CAD0
0x18005cb0b  movaps  xmm2, xmm1
0x18005cb0e  jmp     short loc_18005CAEB
0x18005cb10  movdqa  xmm5, cs:__xmm@7fffffff7fffffff7fffffff7fffffff; jumptable 000000018005C853 case 5
0x18005cb18  lea     rdx, [rsp+4C8h+Buf2]
0x18005cb1d  movss   xmm4, cs:__real@3f800000
0x18005cb25  mov     rcx, r12
0x18005cb28  movss   xmm6, cs:__real@35a00000
0x18005cb30  xor     eax, eax
0x18005cb32  xorps   xmm3, xmm3
0x18005cb35  cmp     eax, 1
0x18005cb38  jnb     loc_18005C9EC
0x18005cb3e  movss   xmm1, dword ptr [rdx]
0x18005cb42  ucomiss xmm1, xmm3
0x18005cb45  movss   xmm0, dword ptr [rcx]
0x18005cb49  jp      short loc_18005CB70
0x18005cb4b  jnz     short loc_18005CB70
0x18005cb4d  movaps  xmm2, xmm4
0x18005cb50  subss   xmm0, xmm1
0x18005cb54  divss   xmm0, xmm2
0x18005cb58  andps   xmm0, xmm5
0x18005cb5b  comiss  xmm6, xmm0
0x18005cb5e  jbe     loc_18005C883
0x18005cb64  add     rcx, 4
0x18005cb68  add     rdx, 4
0x18005cb6c  inc     eax
0x18005cb6e  jmp     short loc_18005CB35
0x18005cb70  movaps  xmm2, xmm1
0x18005cb73  jmp     short loc_18005CB50
0x18005cb75  lea     rcx, [rdi+10h]
0x18005cb79  mov     edx, 7
0x18005cb7e  call    ?OnChange@BatchTrackedObject@@QEAAXW4Enum@FlushReason@@@Z; BatchTrackedObject::OnChange(FlushReason::Enum)
0x18005cb83  mov     rax, [rdi]
0x18005cb86  mov     r9, r12
0x18005cb89  mov     r8d, r15d
0x18005cb8c  mov     dword ptr [rsp+4C8h+var_4A8], ebp
0x18005cb90  mov     edx, esi
0x18005cb92  mov     rcx, rdi
0x18005cb95  mov     rax, [rax+0B8h]
0x18005cb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cba1  jmp     loc_18005C8C9
0x18005cba6  mov     r8, rbp; jumptable 000000018005C853 cases 1,9,12,13
0x18005cba9  lea     rdx, [rsp+4C8h+Buf2]; Buf2
0x18005cbae  mov     rcx, r12; Buf1
0x18005cbb1  call    memcmp_0
0x18005cbb6  test    eax, eax
  ... truncated ...
```
