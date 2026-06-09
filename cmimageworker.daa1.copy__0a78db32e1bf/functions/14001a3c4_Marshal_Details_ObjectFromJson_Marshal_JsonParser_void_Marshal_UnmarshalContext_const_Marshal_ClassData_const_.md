# Marshal::Details::ObjectFromJson(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)

- ea: `0x14001a3c4`
- end: `0x14001a9a0`
- name: `?ObjectFromJson@Details@Marshal@@YA_NAEAVJsonParser@2@PEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z`
- size: `1500`
- prototype: `__int64 __usercall@<rax>(Marshal::JsonParser *this@<rcx>, __int64, __int64)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fccc`
- `0x140010218`
- `0x1400106c8`
- `0x140010c18`
- `0x140011174`

## callees

- `0x14001523c`
- `0x1400158ec`
- `0x140018068`
- `0x14001a31c`
- `0x14001a3c4`
- `0x14001aebc`
- `0x14001b384`
- `0x14001b8a8`
- `0x14001dadc`
- `0x14001e274`
- `0x14001e79c`
- `0x14002087c`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::Details::ObjectFromJson(
        Marshal::JsonParser *this,
        __int64 a2,
        __int64 a3,
        __int64 **a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 **v6; // rbx
  __int64 v7; // r12
  Marshal::JsonParser *v8; // r13
  char v10; // r15
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rdx
  const wchar_t **v14; // rdi
  const wchar_t *v15; // rsi
  size_t v16; // rdi
  unsigned int *v17; // r15
  __int64 v18; // rbx
  unsigned int *v19; // r12
  __int64 *v20; // r14
  const wchar_t *v21; // r12
  unsigned int *v22; // rsi
  __int64 v23; // rcx
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  __int64 v26; // rcx
  __int64 *v27; // r14
  int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rax
  const wchar_t *v31; // rdx
  size_t v32; // r8
  int v33; // eax
  __int64 v34; // rsi
  __int64 v35; // rbx
  __int64 *v36; // rdi
  unsigned __int64 v37; // r8
  int v38; // edx
  __int64 v39; // r15
  const wchar_t *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rdx
  unsigned __int8 (__fastcall *v43)(Marshal::JsonParser *, __int64, void ***); // rax
  const wchar_t *v44; // r8
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rcx
  const wchar_t *v48; // rax
  unsigned __int64 v49; // rsi
  __int64 *v50; // rbx
  __int64 *v51; // rdi
  int v52; // ecx
  __int64 v53; // rdx
  __int64 v54; // rcx
  char v55; // [rsp+28h] [rbp-E0h]
  const wchar_t *v56; // [rsp+30h] [rbp-D8h]
  void **v57; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+40h] [rbp-C8h]
  __int64 v59; // [rsp+48h] [rbp-C0h]
  const wchar_t *v60; // [rsp+50h] [rbp-B8h]
  __int64 v61; // [rsp+58h] [rbp-B0h]
  size_t v62; // [rsp+60h] [rbp-A8h]
  void **v63; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+70h] [rbp-98h]
  __int64 v65; // [rsp+78h] [rbp-90h]
  __int64 v66; // [rsp+80h] [rbp-88h]
  __int64 v67; // [rsp+88h] [rbp-80h]
  unsigned int *v68; // [rsp+90h] [rbp-78h]
  _QWORD v69[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v70[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v71[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v72[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v73[2]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v74[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v75[4]; // [rsp+F8h] [rbp-10h] BYREF

  v6 = a4;
  v7 = a3;
  v8 = this;
  if ( (unsigned int)((__int64 (*)(void))Marshal::JsonParser::PeekValueType)() != 3 )
  {
    Marshal::UnmarshalContext::ReportError(v7, 5);
    return 0;
  }
  v10 = 1;
  v55 = 1;
  std::vector<bool>::vector<bool>(v75, *((unsigned int *)v6 + 4));
  LOBYTE(v11) = 125;
  LOBYTE(v12) = 123;
  if ( (unsigned __int8)Marshal::JsonParser::BeginAggregate(v8, v12, v11, 9) )
  {
    Marshal::JsonParser::ParseObjectKey(v8);
    v14 = (const wchar_t **)((char *)v8 + 32);
    while ( 1 )
    {
      if ( *((_QWORD *)v8 + 7) <= 7u )
        v15 = (const wchar_t *)v14;
      else
        v15 = *v14;
      v56 = v15;
      v16 = *((_QWORD *)v8 + 6);
      v62 = v16;
      v17 = (unsigned int *)v6[1];
      v18 = *((unsigned int *)v6 + 4);
      v19 = &v17[v18];
      v68 = v19;
      if ( v18 )
      {
        v20 = *a4;
        v21 = v15;
        do
        {
          v22 = &v17[v18 / 2];
          v23 = v20[4 * *v22];
          v24 = -1;
          do
            ++v24;
          while ( *(_WORD *)(v23 + 2 * v24) );
          v69[0] = v21;
          v69[1] = v16;
          v70[0] = v23;
          v70[1] = v24;
          if ( (int)Marshal::Details::StringCompareCaseInsensitive(v70, v69) >= 0 )
          {
            v18 /= 2;
          }
          else
          {
            v17 = v22 + 1;
            v18 += -1 - v18 / 2;
          }
        }
        while ( v18 > 0 );
        v19 = v68;
        v8 = this;
        v16 = v62;
        v15 = v56;
      }
      v6 = a4;
      if ( v17 == v19 )
      {
        v7 = a3;
      }
      else
      {
        v25 = (const wchar_t *)(*a4)[4 * *v17];
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        v7 = a3;
        if ( v16 == v26 )
        {
          v27 = (__int64 *)(a3 + 8);
          if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 2) != 0 )
          {
            v71[0] = (*a4)[4 * *v17];
            v71[1] = v26;
            v72[0] = v15;
            v72[1] = v16;
            v28 = Marshal::Details::StringCompareCaseInsensitive(v72, v71);
          }
          else
          {
            v28 = wmemcmp(v15, v25, v16);
          }
          if ( !v28 )
          {
            v29 = *v17;
            goto LABEL_37;
          }
        }
      }
      if ( v17 == (unsigned int *)a4[1] )
        goto LABEL_59;
      v30 = 4LL * *(v17 - 1);
      if ( ((*a4)[v30 + 1] & 0x1000000000LL) == 0 )
        goto LABEL_59;
      v31 = (const wchar_t *)(*a4)[v30];
      v32 = -1;
      do
        ++v32;
      while ( v31[v32] );
      if ( v16 < v32 )
        goto LABEL_59;
      v27 = (__int64 *)(v7 + 8);
      if ( (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 2) != 0 )
      {
        v73[0] = (*a4)[v30];
        v73[1] = v32;
        v74[0] = v15;
        v74[1] = v32;
        v33 = Marshal::Details::StringCompareCaseInsensitive(v74, v73);
      }
      else
      {
        v33 = wmemcmp(v15, v31, v32);
      }
      if ( v33 )
      {
LABEL_59:
        v27 = (__int64 *)(v7 + 8);
LABEL_60:
        Marshal::JsonParser::SkipValue(v8);
        if ( (*(_BYTE *)(*v27 + 24) & 4) == 0 )
          goto LABEL_48;
        v14 = (const wchar_t **)((char *)v8 + 32);
        if ( *((_QWORD *)v8 + 7) <= 7u )
          v48 = (const wchar_t *)((char *)v8 + 32);
        else
          v48 = *v14;
        v58 = *v27;
        v59 = v7;
        v57 = &Marshal::Details::UnmarshalFieldContext::`vftable';
        v60 = v48;
        v61 = *((_QWORD *)v8 + 6);
        Marshal::UnmarshalContext::ReportError(&v57, 17);
LABEL_55:
        v10 = 0;
        v55 = 0;
        goto LABEL_50;
      }
      v29 = *(v17 - 1);
LABEL_37:
      if ( v29 >= *((_DWORD *)a4 + 4) )
        goto LABEL_60;
      v34 = v29;
      v35 = 4LL * v29;
      v36 = *a4;
      v37 = (unsigned __int64)v29 >> 5;
      v38 = *(_DWORD *)(v75[0] + 4 * v37);
      if ( (v38 & (1 << v29)) != 0 )
      {
        v46 = v36[v35];
        v47 = -1;
        do
          ++v47;
        while ( *(_WORD *)(v46 + 2 * v47) );
        v64 = *(_QWORD *)(v7 + 8);
        v65 = v7;
        v63 = &Marshal::Details::UnmarshalFieldContext::`vftable';
        v66 = v46;
        v67 = v47;
        Marshal::UnmarshalContext::ReportError(&v63, 16);
        Marshal::JsonParser::SkipValue(v8);
LABEL_46:
        v10 = 0;
        v55 = 0;
        v6 = a4;
        goto LABEL_49;
      }
      v39 = a2 + LODWORD(v36[v35 + 1]);
      *(_DWORD *)(v75[0] + 4 * v37) = (1 << v29) | v38;
      if ( (unsigned int)Marshal::JsonParser::PeekValueType(v8) == 5 && (v36[v35 + 1] & 0x2000000000LL) == 0 )
      {
        Marshal::JsonParser::ParseNull(v8);
        if ( (v36[v35 + 1] & 0x200000000LL) != 0 && (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 8) == 0 )
        {
          v40 = (const wchar_t *)v36[v35];
          v41 = -1;
          do
            ++v41;
          while ( v40[v41] );
          v58 = *(_QWORD *)(v7 + 8);
          v59 = v7;
          v57 = &Marshal::Details::UnmarshalFieldContext::`vftable';
          v60 = v40;
          v61 = v41;
          Marshal::UnmarshalContext::ReportError(&v57, 11);
          goto LABEL_46;
        }
        _mm_lfence();
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*a5 + 8 * v34) + 8LL))(v39, v36[v35 + 2]);
        v6 = a4;
LABEL_48:
        v10 = v55;
LABEL_49:
        v14 = (const wchar_t **)((char *)v8 + 32);
        goto LABEL_50;
      }
      _mm_lfence();
      v43 = *(unsigned __int8 (__fastcall **)(Marshal::JsonParser *, __int64, void ***))(*(_QWORD *)(*a6 + 8 * v34) + 8LL);
      v44 = (const wchar_t *)v36[v35];
      v45 = -1;
      do
        ++v45;
      while ( v44[v45] );
      v58 = *(_QWORD *)(v7 + 8);
      v59 = v7;
      v57 = &Marshal::Details::UnmarshalFieldContext::`vftable';
      v60 = v44;
      v61 = v45;
      v6 = a4;
      v14 = (const wchar_t **)((char *)v8 + 32);
      if ( !v43(v8, v39, &v57) )
        goto LABEL_55;
      v10 = v55;
LABEL_50:
      LOBYTE(v42) = 125;
      if ( !(unsigned __int8)Marshal::JsonParser::NextElement(v8, v42, 10) )
        goto LABEL_67;
      Marshal::JsonParser::ParseObjectKey(v8);
    }
  }
  v27 = (__int64 *)(v7 + 8);
LABEL_67:
  if ( (*(_BYTE *)(*v27 + 24) & 8) == 0 )
  {
    v49 = 0;
    v50 = *v6;
    v51 = &v50[4 * *((unsigned int *)a4 + 4)];
    while ( v50 != v51 )
    {
      v13 = v49 & 0x1F;
      v52 = *(_DWORD *)(v75[0] + 4 * (v49 >> 5));
      if ( !_bittest(&v52, v13) )
      {
        if ( (*((_BYTE *)v50 + 12) & 2) != 0 )
        {
          v53 = *v50;
          v54 = -1;
          do
            ++v54;
          while ( *(_WORD *)(v53 + 2 * v54) );
          v64 = *v27;
          v65 = v7;
          v63 = &Marshal::Details::UnmarshalFieldContext::`vftable';
          v66 = v53;
          v67 = v54;
          Marshal::UnmarshalContext::ReportError(&v63, 11);
          v10 = 0;
        }
        else
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*a5 + 8 * v49) + 8LL))(
            a2 + *((unsigned int *)v50 + 2),
            v50[2]);
        }
      }
      ++v49;
      v50 += 4;
    }
  }
  std::vector<unsigned int>::~vector<unsigned int>(v75, v13, 0, &Marshal::Details::UnmarshalFieldContext::`vftable');
  return v10;
}

```

## disassembly

```asm
0x14001a3c4  mov     rax, rsp
0x14001a3c7  mov     [rax+20h], r9
0x14001a3cb  mov     [rax+18h], r8
0x14001a3cf  mov     [rax+10h], rdx
0x14001a3d3  mov     [rax+8], rcx
0x14001a3d7  push    rbp
0x14001a3d8  push    rbx
0x14001a3d9  push    rsi
0x14001a3da  push    rdi
0x14001a3db  push    r12
0x14001a3dd  push    r13
0x14001a3df  push    r14
0x14001a3e1  push    r15
0x14001a3e3  lea     rbp, [rax-78h]
0x14001a3e7  sub     rsp, 138h
0x14001a3ee  mov     rbx, r9
0x14001a3f1  mov     r12, r8
0x14001a3f4  mov     r13, rcx
0x14001a3f7  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14001a3fc  cmp     eax, 3
0x14001a3ff  jz      short loc_14001A415
0x14001a401  mov     edx, 5
0x14001a406  mov     rcx, r12
0x14001a409  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14001a40e  xor     al, al
0x14001a410  jmp     loc_14001A98B
0x14001a415  mov     r15b, 1
0x14001a418  mov     byte ptr [rsp+170h+var_150], r15b
0x14001a41d  mov     edx, [rbx+10h]
0x14001a420  lea     rcx, [rbp+70h+var_80]
0x14001a424  call    ??0?$vector@_NV?$allocator@_N@std@@@std@@QEAA@_KAEBV?$allocator@_N@1@@Z; std::vector<bool>::vector<bool>(unsigned __int64,std::allocator<bool> const &)
0x14001a429  nop
0x14001a42a  mov     r9d, 9
0x14001a430  mov     r8b, 7Dh ; '}'
0x14001a433  mov     dl, 7Bh ; '{'
0x14001a435  mov     rcx, r13
0x14001a438  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x14001a43d  lea     r9, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14001a444  xor     r8d, r8d
0x14001a447  test    al, al
0x14001a449  jz      loc_14001A8A5
0x14001a44f  mov     rcx, r13; this
0x14001a452  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14001a457  lea     rdi, [r13+20h]
0x14001a45b  cmp     qword ptr [r13+38h], 7
0x14001a460  jbe     short loc_14001A467
0x14001a462  mov     rsi, [rdi]
0x14001a465  jmp     short loc_14001A46A
0x14001a467  mov     rsi, rdi
0x14001a46a  mov     [rsp+170h+var_148], rsi
0x14001a46f  mov     rdi, [r13+30h]
0x14001a473  mov     [rsp+170h+var_118], rdi
0x14001a478  mov     r15, [rbx+8]
0x14001a47c  mov     ebx, [rbx+10h]
0x14001a47f  lea     r12, [r15+rbx*4]
0x14001a483  mov     [rbp+70h+var_E8], r12
0x14001a487  xor     r11d, r11d
0x14001a48a  test    rbx, rbx
0x14001a48d  jz      loc_14001A51F
0x14001a493  mov     rax, [rbp+70h+arg_18]
0x14001a49a  mov     r14, [rax]
0x14001a49d  mov     r13, rdi
0x14001a4a0  mov     r12, rsi
0x14001a4a3  mov     rdi, rbx
0x14001a4a6  test    rbx, rbx
0x14001a4a9  jns     short loc_14001A4AF
0x14001a4ab  lea     rdi, [rbx+1]
0x14001a4af  sar     rdi, 1
0x14001a4b2  lea     rsi, [r15+rdi*4]
0x14001a4b6  mov     eax, [rsi]
0x14001a4b8  shl     rax, 5
0x14001a4bc  mov     rcx, [rax+r14]
0x14001a4c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a4c4  inc     rax
0x14001a4c7  cmp     [rcx+rax*2], r11w
0x14001a4cc  jnz     short loc_14001A4C4
0x14001a4ce  mov     [rbp+70h+var_E0], r12
0x14001a4d2  mov     [rbp+70h+var_D8], r13
0x14001a4d6  mov     [rbp+70h+var_D0], rcx
0x14001a4da  mov     [rbp+70h+var_C8], rax
0x14001a4de  lea     rdx, [rbp+70h+var_E0]
0x14001a4e2  lea     rcx, [rbp+70h+var_D0]
0x14001a4e6  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x14001a4eb  xor     r11d, r11d
0x14001a4ee  test    eax, eax
0x14001a4f0  jns     short loc_14001A502
0x14001a4f2  lea     r15, [rsi+4]
0x14001a4f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a4fa  sub     rax, rdi
0x14001a4fd  add     rbx, rax
0x14001a500  jmp     short loc_14001A505
0x14001a502  mov     rbx, rdi
0x14001a505  test    rbx, rbx
0x14001a508  jg      short loc_14001A4A3
0x14001a50a  mov     r12, [rbp+70h+var_E8]
0x14001a50e  mov     r13, [rbp+70h+arg_0]
0x14001a515  mov     rdi, [rsp+170h+var_118]
0x14001a51a  mov     rsi, [rsp+170h+var_148]
0x14001a51f  mov     rbx, [rbp+70h+arg_18]
0x14001a526  cmp     r15, r12
0x14001a529  jz      short loc_14001A59A
0x14001a52b  mov     ecx, [r15]
0x14001a52e  shl     rcx, 5
0x14001a532  mov     rax, [rbx]
0x14001a535  mov     rdx, [rcx+rax]; S2
0x14001a539  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001a53d  inc     rcx
0x14001a540  cmp     [rdx+rcx*2], r11w
0x14001a545  jnz     short loc_14001A53D
0x14001a547  mov     r12, [rbp+70h+arg_10]
0x14001a54e  cmp     rdi, rcx
0x14001a551  jnz     short loc_14001A5A1
0x14001a553  lea     r14, [r12+8]
0x14001a558  mov     rax, [r14]
0x14001a55b  test    byte ptr [rax+18h], 2
0x14001a55f  jz      short loc_14001A580
0x14001a561  mov     [rbp+70h+var_C0], rdx
0x14001a565  mov     [rbp+70h+var_B8], rcx
0x14001a569  mov     [rbp+70h+var_B0], rsi
0x14001a56d  mov     [rbp+70h+var_A8], rdi
0x14001a571  lea     rdx, [rbp+70h+var_C0]
0x14001a575  lea     rcx, [rbp+70h+var_B0]
0x14001a579  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x14001a57e  jmp     short loc_14001A58B
0x14001a580  mov     r8, rdi; N
0x14001a583  mov     rcx, rsi; S1
0x14001a586  call    wmemcmp
0x14001a58b  xor     r11d, r11d
0x14001a58e  test    eax, eax
0x14001a590  jnz     short loc_14001A5A1
0x14001a592  mov     eax, [r15]
0x14001a595  jmp     loc_14001A625
0x14001a59a  mov     r12, [rbp+70h+arg_10]
0x14001a5a1  cmp     r15, [rbx+8]
0x14001a5a5  jz      loc_14001A830
0x14001a5ab  mov     eax, [r15-4]
0x14001a5af  shl     rax, 5
0x14001a5b3  mov     rcx, [rbx]
0x14001a5b6  test    byte ptr [rax+rcx+0Ch], 10h
0x14001a5bb  jz      loc_14001A830
0x14001a5c1  mov     rdx, [rax+rcx]; S2
0x14001a5c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001a5c9  inc     r8; N
0x14001a5cc  cmp     [rdx+r8*2], r11w
0x14001a5d1  jnz     short loc_14001A5C9
0x14001a5d3  cmp     rdi, r8
0x14001a5d6  jb      loc_14001A830
0x14001a5dc  lea     r14, [r12+8]
0x14001a5e1  mov     rax, [r14]
0x14001a5e4  test    byte ptr [rax+18h], 2
0x14001a5e8  jz      short loc_14001A609
0x14001a5ea  mov     [rbp+70h+var_A0], rdx
0x14001a5ee  mov     [rbp+70h+var_98], r8
0x14001a5f2  mov     [rbp+70h+var_90], rsi
0x14001a5f6  mov     [rbp+70h+var_88], r8
0x14001a5fa  lea     rdx, [rbp+70h+var_A0]
0x14001a5fe  lea     rcx, [rbp+70h+var_90]
0x14001a602  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x14001a607  jmp     short loc_14001A611
0x14001a609  mov     rcx, rsi; S1
0x14001a60c  call    wmemcmp
0x14001a611  xor     r11d, r11d
0x14001a614  test    eax, eax
0x14001a616  setz    al
0x14001a619  test    al, al
0x14001a61b  jz      loc_14001A830
0x14001a621  mov     eax, [r15-4]
0x14001a625  cmp     eax, [rbx+10h]
0x14001a628  jnb     loc_14001A835
0x14001a62e  mov     esi, eax
0x14001a630  mov     ebx, eax
0x14001a632  shl     rbx, 5
0x14001a636  mov     rax, [rbp+70h+arg_18]
0x14001a63d  mov     rdi, [rax]
0x14001a640  mov     r8d, esi
0x14001a643  shr     r8, 5
0x14001a647  mov     r10, [rbp+70h+var_80]
0x14001a64b  mov     edx, [r10+r8*4]
0x14001a64f  mov     cl, sil
0x14001a652  mov     r9d, 1
0x14001a658  shl     r9d, cl
0x14001a65b  test    r9d, edx
0x14001a65e  jnz     loc_14001A7D8
0x14001a664  mov     r15d, [rbx+rdi+8]
0x14001a669  add     r15, [rbp+70h+arg_8]
0x14001a670  or      edx, r9d
0x14001a673  mov     [r10+r8*4], edx
0x14001a677  mov     rcx, r13
0x14001a67a  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14001a67f  cmp     eax, 5
0x14001a682  jnz     loc_14001A75A
0x14001a688  test    byte ptr [rbx+rdi+0Ch], 20h
0x14001a68d  jnz     loc_14001A75A
0x14001a693  mov     rcx, r13; this
0x14001a696  call    ?ParseNull@JsonParser@Marshal@@QEAAXXZ; Marshal::JsonParser::ParseNull(void)
0x14001a69b  test    byte ptr [rbx+rdi+0Ch], 2
0x14001a6a0  jz      short loc_14001A700
0x14001a6a2  mov     rdx, [r12+8]
0x14001a6a7  test    byte ptr [rdx+18h], 8
0x14001a6ab  jnz     short loc_14001A700
0x14001a6ad  mov     rcx, [rbx+rdi]
0x14001a6b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a6b5  xor     esi, esi
0x14001a6b7  inc     rax
0x14001a6ba  cmp     [rcx+rax*2], si
0x14001a6be  jnz     short loc_14001A6B7
0x14001a6c0  mov     [rsp+170h+var_138], rdx
0x14001a6c5  mov     [rsp+170h+var_130], r12
0x14001a6ca  lea     rdx, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14001a6d1  mov     [rsp+170h+var_140], rdx
0x14001a6d6  mov     [rsp+170h+var_128], rcx
0x14001a6db  mov     [rsp+170h+var_120], rax
0x14001a6e0  mov     edx, 0Bh
0x14001a6e5  lea     rcx, [rsp+170h+var_140]
0x14001a6ea  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14001a6ef  mov     r15b, sil
0x14001a6f2  mov     byte ptr [rsp+170h+var_150], sil
0x14001a6f7  mov     rbx, [rbp+70h+arg_18]
0x14001a6fe  jmp     short loc_14001A72E
0x14001a700  lfence
0x14001a703  mov     rax, [rbp+70h+arg_20]
0x14001a70a  mov     rax, [rax]
0x14001a70d  mov     rdx, [rax+rsi*8]
0x14001a711  mov     rax, [rdx+8]
0x14001a715  mov     rdx, [rbx+rdi+10h]
0x14001a71a  mov     rcx, r15
0x14001a71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a722  mov     rbx, [rbp+70h+arg_18]
0x14001a729  mov     r15b, byte ptr [rsp+170h+var_150]
0x14001a72e  lea     rdi, [r13+20h]
0x14001a732  mov     r8d, 0Ah
0x14001a738  mov     dl, 7Dh ; '}'
0x14001a73a  mov     rcx, r13
0x14001a73d  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x14001a742  xor     r8d, r8d
0x14001a745  test    al, al
0x14001a747  jz      loc_14001A8AC
0x14001a74d  mov     rcx, r13; this
0x14001a750  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14001a755  jmp     loc_14001A45B
0x14001a75a  lfence
0x14001a75d  mov     rax, [rbp+70h+arg_28]
0x14001a764  mov     rax, [rax]
0x14001a767  mov     rcx, [rax+rsi*8]
0x14001a76b  mov     rax, [rcx+8]
0x14001a76f  mov     r8, [rbx+rdi]
0x14001a773  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001a777  xor     esi, esi
0x14001a779  inc     rdx
0x14001a77c  cmp     [r8+rdx*2], si
0x14001a781  jnz     short loc_14001A779
0x14001a783  mov     rcx, [r12+8]
0x14001a788  mov     [rsp+170h+var_138], rcx
0x14001a78d  mov     [rsp+170h+var_130], r12
0x14001a792  lea     rcx, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14001a799  mov     [rsp+170h+var_140], rcx
0x14001a79e  mov     [rsp+170h+var_128], r8
0x14001a7a3  mov     [rsp+170h+var_120], rdx
0x14001a7a8  lea     r8, [rsp+170h+var_140]
0x14001a7ad  mov     rdx, r15
0x14001a7b0  mov     rcx, r13
0x14001a7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a7b8  mov     rbx, [rbp+70h+arg_18]
0x14001a7bf  lea     rdi, [r13+20h]
0x14001a7c3  test    al, al
0x14001a7c5  jnz     loc_14001A89B
0x14001a7cb  mov     r15b, sil
0x14001a7ce  mov     byte ptr [rsp+170h+var_150], sil
0x14001a7d3  jmp     loc_14001A732
0x14001a7d8  mov     rdx, [rbx+rdi]
0x14001a7dc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001a7e0  inc     rcx
0x14001a7e3  cmp     [rdx+rcx*2], r11w
0x14001a7e8  jnz     short loc_14001A7E0
0x14001a7ea  mov     rax, [r12+8]
0x14001a7ef  mov     [rsp+170h+var_108], rax
0x14001a7f4  mov     [rsp+170h+var_100], r12
0x14001a7f9  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x14001a800  mov     [rsp+170h+var_110], rax
0x14001a805  mov     [rsp+170h+var_F8], rdx
0x14001a80a  mov     [rbp+70h+var_F0], rcx
0x14001a80e  mov     edx, 10h
0x14001a813  lea     rcx, [rsp+170h+var_110]
0x14001a818  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14001a81d  lea     rdx, [rbp+70h+var_60]
0x14001a821  mov     rcx, r13; this
0x14001a824  call    ?SkipValue@JsonParser@Marshal@@QEAA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; Marshal::JsonParser::SkipValue(void)
0x14001a829  xor     esi, esi
0x14001a82b  jmp     loc_14001A6EF
0x14001a830  lea     r14, [r12+8]
0x14001a835  lea     rdx, [rbp+70h+var_50]
0x14001a839  mov     rcx, r13; this
0x14001a83c  call    ?SkipValue@JsonParser@Marshal@@QEAA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; Marshal::JsonParser::SkipValue(void)
0x14001a841  mov     rcx, [r14]
0x14001a844  test    byte ptr [rcx+18h], 4
0x14001a848  jz      loc_14001A729
0x14001a84e  lea     rdi, [r13+20h]
0x14001a852  cmp     qword ptr [rdi+18h], 7
0x14001a857  jbe     short loc_14001A85E
0x14001a859  mov     rax, [rdi]
  ... truncated ...
```
