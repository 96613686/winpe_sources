# TextMove(x,x)

- ea: `0x1001f830`
- end: `0x1001fb97`
- name: `_TextMove@8`
- size: `871`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x10011060`
- `0x10013800`
- `0x10015740`

## callees

- `0x1001f240`
- `0x1001f270`
- `0x1001f830`
- `0x10021670`
- `0x100226f0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TextMove(int a1, int a2)
{
  int NextRow; // edx
  int v3; // eax
  int v4; // ebx
  int result; // eax
  int i; // edi
  __m128i v7; // xmm0
  int v8; // eax
  __m128i v9; // xmm0
  __m128i v10; // xmm1
  int v11; // ebx
  __int32 v12; // edi
  __m128i v13; // xmm1
  __m128i v14; // xmm0
  __m128i v15; // xmm2
  __int128 v16; // xmm3
  __m128i v17; // xmm0
  __m128i v18; // xmm1
  int v19; // eax
  __m128i v20; // xmm0
  __int128 v21; // xmm1
  __m128i v22; // [esp-20h] [ebp-60h]
  __m128i v23; // [esp-20h] [ebp-60h]
  __m128i v24; // [esp+Ch] [ebp-34h] BYREF
  __m128i v25; // [esp+1Ch] [ebp-24h] BYREF
  __m128i v26; // [esp+2Ch] [ebp-14h] BYREF

  NextRow = 0;
  v3 = *(_DWORD *)(a1 + 524);
  switch ( a2 )
  {
    case 0:
      if ( *(_DWORD *)(a1 + 8780) )
      {
        v22 = _mm_loadu_si128((const __m128i *)(a1 + 8784));
        NextRow = TextGotoBookmark(
                    a1,
                    v22.m128i_i32[0],
                    v22.m128i_i32[1],
                    v22.m128i_i32[2],
                    v22.m128i_i32[3],
                    *(_OWORD *)&_mm_loadu_si128((const __m128i *)(a1 + 8800)));
LABEL_12:
        *(_DWORD *)(a1 + 560) = 1;
        *(_DWORD *)(a1 + 11960) = 0;
        return NextRow;
      }
      v4 = *(_DWORD *)(v3 + 32);
      if ( *(_DWORD *)(v3 + 28) )
        ++v4;
      result = TextRewind(a1);
      NextRow = result;
      if ( !result )
      {
        for ( i = 0; i <= v4; ++i )
        {
          NextRow = TextGetNextRow(a1, 0);
          if ( NextRow )
            return NextRow;
        }
        *(__m128i *)(a1 + 8784) = _mm_loadu_si128((const __m128i *)(a1 + 8856));
        v7 = _mm_loadu_si128((const __m128i *)(a1 + 8872));
        *(_DWORD *)(a1 + 8780) = 1;
        *(__m128i *)(a1 + 8800) = v7;
        if ( *(_DWORD *)(a1 + 548) == *(_DWORD *)(a1 + 8788) + *(_DWORD *)(a1 + 8784) + 1 )
          *(_DWORD *)(a1 + 8772) = 1;
        goto LABEL_12;
      }
      return result;
    case 1:
      v25 = _mm_loadu_si128((const __m128i *)(a1 + 8856));
      v24 = _mm_loadu_si128((const __m128i *)(a1 + 8872));
      v8 = TextGetNextRow(a1, 1);
      NextRow = v8;
      if ( !*(_DWORD *)(a1 + 11960) )
        ++*(_DWORD *)(a1 + 560);
      if ( v8 == -1603 )
      {
        v9 = _mm_loadu_si128(&v25);
        *(_DWORD *)(a1 + 11960) = 1;
        *(__m128i *)(a1 + 8856) = v9;
        *(__m128i *)(a1 + 8872) = _mm_loadu_si128(&v24);
      }
      return NextRow;
    case 2:
      v10 = _mm_loadu_si128((const __m128i *)(a1 + 8856));
      v11 = _mm_cvtsi128_si32(v10);
      v25 = v10;
      v12 = v10.m128i_i32[1];
      v26 = _mm_loadu_si128((const __m128i *)(a1 + 8872));
      if ( __PAIR64__(v10.m128i_u32[1], v11) == *(_QWORD *)(a1 + 8784) )
        return -1603;
      result = TextRewind(a1);
      if ( result )
        return result;
      v23 = _mm_loadu_si128((const __m128i *)(a1 + 8784));
      result = TextGotoBookmark(
                 a1,
                 v23.m128i_i32[0],
                 v23.m128i_i32[1],
                 v23.m128i_i32[2],
                 v23.m128i_i32[3],
                 *(_OWORD *)&_mm_loadu_si128((const __m128i *)(a1 + 8800)));
      if ( result )
        return result;
      TextGetBookmark(a1, &v25);
      result = TextGetNextRow(a1, 1);
      if ( result )
        return result;
      v13 = _mm_loadu_si128(&v26);
      v14 = _mm_loadu_si128(&v25);
      while ( 2 )
      {
        v15 = v14;
        v16 = (__int128)v13;
        v17 = _mm_loadu_si128((const __m128i *)(a1 + 8856));
        v18 = _mm_loadu_si128((const __m128i *)(a1 + 8872));
        v25 = v17;
        v24 = v18;
        if ( _mm_cvtsi128_si32(v17) == v11 && _mm_cvtsi128_si32(_mm_srli_si128(v17, 4)) == v12 )
        {
          v19 = TextGotoBookmark(a1, v15.m128i_i32[0], v15.m128i_i32[1], v15.m128i_i32[2], v15.m128i_i32[3], v16);
          --*(_DWORD *)(a1 + 560);
          NextRow = v19;
          if ( *(_DWORD *)(a1 + 11960) )
            *(_DWORD *)(a1 + 11960) = 0;
          return NextRow;
        }
        else
        {
          result = TextGetNextRow(a1, 1);
          if ( !result )
          {
            v14 = _mm_loadu_si128(&v25);
            v13 = _mm_loadu_si128(&v24);
            continue;
          }
        }
        break;
      }
      return result;
    case 3:
      v24 = _mm_loadu_si128((const __m128i *)(a1 + 8856));
      v25 = _mm_loadu_si128((const __m128i *)(a1 + 8872));
      for ( result = TextGetNextRow(a1, 1); !result; result = TextGetNextRow(a1, 1) )
      {
        ++*(_DWORD *)(a1 + 560);
        v24 = _mm_loadu_si128((const __m128i *)(a1 + 8856));
        v25 = _mm_loadu_si128((const __m128i *)(a1 + 8872));
      }
      if ( result != -1603 )
        return result;
      v20 = _mm_loadu_si128(&v24);
      *(_DWORD *)(a1 + 11960) = 0;
      v21 = (__int128)_mm_loadu_si128(&v25);
      *(__m128i *)(a1 + 8856) = v20;
      *(_OWORD *)(a1 + 8872) = v21;
      return TextGotoBookmark(a1, v20.m128i_i32[0], v20.m128i_i32[1], v20.m128i_i32[2], v20.m128i_i32[3], v21);
    default:
      return NextRow;
  }
}

```

## disassembly

```asm
0x1001f830  sub     esp, 34h
0x1001f833  mov     eax, ___security_cookie
0x1001f838  xor     eax, esp
0x1001f83a  mov     [esp+34h+var_4], eax
0x1001f83e  mov     ecx, [esp+34h+arg_4]
0x1001f842  xor     edx, edx
0x1001f844  push    ebx
0x1001f845  push    esi
0x1001f846  mov     esi, [esp+3Ch+arg_0]
0x1001f84a  push    edi
0x1001f84b  mov     eax, [esi+20Ch]
0x1001f851  cmp     ecx, 3; switch 4 cases
0x1001f854  ja      def_1001F85A; jumptable 1001F85A default case
0x1001f85a  jmp     ds:jpt_1001F85A[ecx*4]; switch jump
0x1001f861  cmp     [esi+224Ch], edx; jumptable 1001F85A case 0
0x1001f867  jnz     loc_1001F8F2
0x1001f86d  mov     ebx, [eax+20h]
0x1001f870  cmp     [eax+1Ch], edx
0x1001f873  jz      short loc_1001F876
0x1001f875  inc     ebx
0x1001f876  push    esi
0x1001f877  call    _TextRewind@4; TextRewind(x)
0x1001f87c  mov     edx, eax
0x1001f87e  test    edx, edx
0x1001f880  jnz     loc_1001FB83
0x1001f886  xor     edi, edi
0x1001f888  test    ebx, ebx
0x1001f88a  js      short loc_1001F8A7
0x1001f88c  lea     esp, [esp+0]
0x1001f890  push    0
0x1001f892  push    esi
0x1001f893  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001f898  mov     edx, eax
0x1001f89a  test    edx, edx
0x1001f89c  jnz     def_1001F85A; jumptable 1001F85A default case
0x1001f8a2  inc     edi
0x1001f8a3  cmp     edi, ebx
0x1001f8a5  jle     short loc_1001F890
0x1001f8a7  movdqu  xmm0, xmmword ptr [esi+2298h]
0x1001f8af  movdqu  xmmword ptr [esi+2250h], xmm0
0x1001f8b7  movdqu  xmm0, xmmword ptr [esi+22A8h]
0x1001f8bf  mov     dword ptr [esi+224Ch], 1
0x1001f8c9  movdqu  xmmword ptr [esi+2260h], xmm0
0x1001f8d1  mov     eax, [esi+2250h]
0x1001f8d7  inc     eax
0x1001f8d8  add     eax, [esi+2254h]
0x1001f8de  cmp     [esi+224h], eax
0x1001f8e4  jnz     short loc_1001F918
0x1001f8e6  mov     dword ptr [esi+2244h], 1
0x1001f8f0  jmp     short loc_1001F918
0x1001f8f2  movdqu  xmm0, xmmword ptr [esi+2250h]
0x1001f8fa  sub     esp, 20h
0x1001f8fd  mov     eax, esp
0x1001f8ff  push    esi; int
0x1001f900  movdqu  xmmword ptr [eax], xmm0
0x1001f904  movdqu  xmm0, xmmword ptr [esi+2260h]
0x1001f90c  movdqu  xmmword ptr [eax+10h], xmm0
0x1001f911  call    _TextGotoBookmark@36; TextGotoBookmark(x,x,x,x,x,x,x,x,x)
0x1001f916  mov     edx, eax
0x1001f918  mov     dword ptr [esi+230h], 1
0x1001f922  mov     dword ptr [esi+2EB8h], 0
0x1001f92c  jmp     def_1001F85A; jumptable 1001F85A default case
0x1001f931  movdqu  xmm0, xmmword ptr [esi+2298h]; jumptable 1001F85A case 1
0x1001f939  push    1
0x1001f93b  push    esi
0x1001f93c  movdqu  [esp+48h+var_24], xmm0
0x1001f942  movdqu  xmm0, xmmword ptr [esi+22A8h]
0x1001f94a  movdqu  [esp+48h+var_34], xmm0
0x1001f950  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001f955  cmp     dword ptr [esi+2EB8h], 0
0x1001f95c  mov     edx, eax
0x1001f95e  jnz     short loc_1001F966
0x1001f960  inc     dword ptr [esi+230h]
0x1001f966  cmp     edx, 0FFFFF9BDh
0x1001f96c  jnz     def_1001F85A; jumptable 1001F85A default case
0x1001f972  movdqu  xmm0, [esp+40h+var_24]
0x1001f978  mov     dword ptr [esi+2EB8h], 1
0x1001f982  movdqu  xmmword ptr [esi+2298h], xmm0
0x1001f98a  movdqu  xmm0, [esp+40h+var_34]
0x1001f990  movdqu  xmmword ptr [esi+22A8h], xmm0
0x1001f998  jmp     def_1001F85A; jumptable 1001F85A default case
0x1001f99d  movdqu  xmm1, xmmword ptr [esi+2298h]; jumptable 1001F85A case 2
0x1001f9a5  movdqu  xmm0, xmmword ptr [esi+22A8h]
0x1001f9ad  movd    ebx, xmm1
0x1001f9b1  movdqu  [esp+40h+var_24], xmm1
0x1001f9b7  mov     edi, dword ptr [esp+40h+var_24+4]
0x1001f9bb  movdqu  [esp+40h+var_14], xmm0
0x1001f9c1  cmp     ebx, [esi+2250h]
0x1001f9c7  jnz     short loc_1001F9EA
0x1001f9c9  cmp     edi, [esi+2254h]
0x1001f9cf  jnz     short loc_1001F9EA
0x1001f9d1  mov     eax, 0FFFFF9BDh
0x1001f9d6  pop     edi
0x1001f9d7  pop     esi
0x1001f9d8  pop     ebx
0x1001f9d9  mov     ecx, [esp+34h+var_4]
0x1001f9dd  xor     ecx, esp; StackCookie
0x1001f9df  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001f9e4  add     esp, 34h
0x1001f9e7  retn    8
0x1001f9ea  push    esi
0x1001f9eb  call    _TextRewind@4; TextRewind(x)
0x1001f9f0  test    eax, eax
0x1001f9f2  jnz     loc_1001FB83
0x1001f9f8  movdqu  xmm0, xmmword ptr [esi+2250h]
0x1001fa00  sub     esp, 20h
0x1001fa03  mov     eax, esp
0x1001fa05  push    esi; int
0x1001fa06  movdqu  xmmword ptr [eax], xmm0
0x1001fa0a  movdqu  xmm0, xmmword ptr [esi+2260h]
0x1001fa12  movdqu  xmmword ptr [eax+10h], xmm0
0x1001fa17  call    _TextGotoBookmark@36; TextGotoBookmark(x,x,x,x,x,x,x,x,x)
0x1001fa1c  test    eax, eax
0x1001fa1e  jnz     loc_1001FB83
0x1001fa24  lea     eax, [esp+40h+var_24]
0x1001fa28  push    eax
0x1001fa29  push    esi
0x1001fa2a  call    _TextGetBookmark@8; TextGetBookmark(x,x)
0x1001fa2f  push    1
0x1001fa31  push    esi
0x1001fa32  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001fa37  test    eax, eax
0x1001fa39  jnz     loc_1001FB83
0x1001fa3f  movdqu  xmm1, [esp+40h+var_14]
0x1001fa45  movdqu  xmm0, [esp+40h+var_24]
0x1001fa4b  jmp     short loc_1001FA50
0x1001fa50  movdqu  xmm2, xmm0
0x1001fa54  movdqu  xmm3, xmm1
0x1001fa58  movdqu  xmm0, xmmword ptr [esi+2298h]
0x1001fa60  movdqu  xmm1, xmmword ptr [esi+22A8h]
0x1001fa68  movd    eax, xmm0
0x1001fa6c  movdqu  [esp+40h+var_24], xmm0
0x1001fa72  movdqu  [esp+40h+var_34], xmm1
0x1001fa78  cmp     eax, ebx
0x1001fa7a  jnz     short loc_1001FA89
0x1001fa7c  psrldq  xmm0, 4
0x1001fa81  movd    eax, xmm0
0x1001fa85  cmp     eax, edi
0x1001fa87  jz      short loc_1001FAA7
0x1001fa89  push    1
0x1001fa8b  push    esi
0x1001fa8c  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001fa91  test    eax, eax
0x1001fa93  jnz     loc_1001FB83
0x1001fa99  movdqu  xmm0, [esp+40h+var_24]
0x1001fa9f  movdqu  xmm1, [esp+40h+var_34]
0x1001faa5  jmp     short loc_1001FA50
0x1001faa7  sub     esp, 20h
0x1001faaa  mov     eax, esp
0x1001faac  push    esi; int
0x1001faad  movdqu  xmmword ptr [eax], xmm2
0x1001fab1  movdqu  xmmword ptr [eax+10h], xmm3
0x1001fab6  call    _TextGotoBookmark@36; TextGotoBookmark(x,x,x,x,x,x,x,x,x)
0x1001fabb  dec     dword ptr [esi+230h]
0x1001fac1  mov     edx, eax
0x1001fac3  cmp     dword ptr [esi+2EB8h], 0
0x1001faca  jz      def_1001F85A; jumptable 1001F85A default case
0x1001fad0  mov     dword ptr [esi+2EB8h], 0
0x1001fada  jmp     def_1001F85A; jumptable 1001F85A default case
0x1001fadf  movdqu  xmm0, xmmword ptr [esi+2298h]; jumptable 1001F85A case 3
0x1001fae7  push    1
0x1001fae9  push    esi
0x1001faea  movdqu  [esp+48h+var_34], xmm0
0x1001faf0  movdqu  xmm0, xmmword ptr [esi+22A8h]
0x1001faf8  movdqu  [esp+48h+var_24], xmm0
0x1001fafe  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001fb03  test    eax, eax
0x1001fb05  jnz     short loc_1001FB3E
0x1001fb07  jmp     short loc_1001FB10
0x1001fb10  inc     dword ptr [esi+230h]
0x1001fb16  movdqu  xmm0, xmmword ptr [esi+2298h]
0x1001fb1e  push    1
0x1001fb20  push    esi
0x1001fb21  movdqu  [esp+48h+var_34], xmm0
0x1001fb27  movdqu  xmm0, xmmword ptr [esi+22A8h]
0x1001fb2f  movdqu  [esp+48h+var_24], xmm0
0x1001fb35  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001fb3a  test    eax, eax
0x1001fb3c  jz      short loc_1001FB10
0x1001fb3e  cmp     eax, 0FFFFF9BDh
0x1001fb43  jnz     short loc_1001FB83
0x1001fb45  movdqu  xmm0, [esp+40h+var_34]
0x1001fb4b  sub     esp, 20h
0x1001fb4e  mov     dword ptr [esi+2EB8h], 0
0x1001fb58  movdqu  xmm1, [esp+60h+var_24]
0x1001fb5e  mov     eax, esp
0x1001fb60  movdqu  xmmword ptr [esi+2298h], xmm0
0x1001fb68  push    esi; int
0x1001fb69  movdqu  xmmword ptr [esi+22A8h], xmm1
0x1001fb71  movdqu  xmmword ptr [eax], xmm0
0x1001fb75  movdqu  xmmword ptr [eax+10h], xmm1
0x1001fb7a  call    _TextGotoBookmark@36; TextGotoBookmark(x,x,x,x,x,x,x,x,x)
0x1001fb7f  mov     edx, eax
0x1001fb81  mov     eax, edx; jumptable 1001F85A default case
0x1001fb83  mov     ecx, [esp+40h+var_4]
0x1001fb87  pop     edi
0x1001fb88  pop     esi
0x1001fb89  pop     ebx
0x1001fb8a  xor     ecx, esp; StackCookie
0x1001fb8c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001fb91  add     esp, 34h
0x1001fb94  retn    8
```
