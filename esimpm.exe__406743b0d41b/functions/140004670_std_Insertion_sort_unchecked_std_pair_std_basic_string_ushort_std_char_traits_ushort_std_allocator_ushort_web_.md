# std::_Insertion_sort_unchecked<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &)>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> * const,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> * const,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &))

- ea: `0x140004670`
- end: `0x140004a54`
- name: `??$_Insertion_sort_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0P6A_NAEBU10@1@Z@Z`
- size: `996`
- prototype: `__int128 *__fastcall(__int64, __int128 *, unsigned __int8 (__fastcall *)(__int128 *, __int64 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140005960`

## callees

- `0x140002f60`
- `0x140003244`
- `0x140004670`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int128 *__fastcall std::_Insertion_sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        __int64 a1,
        __int128 *a2,
        unsigned __int8 (__fastcall *a3)(__int128 *, __int64 *))
{
  __int128 *i; // r14
  __int64 v7; // rax
  __int64 *v8; // rdi
  __int64 *v9; // rbx
  unsigned __int64 v10; // rdx
  char *v11; // rax
  char *v12; // rcx
  __int64 *v13; // rdx
  __int64 *v14; // r8
  __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // rax
  char *v18; // rcx
  __int64 *v19; // rdx
  __int64 v20; // rcx
  __int64 *j; // rbx
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rcx
  __int64 *v25; // rdx
  __int64 *v26; // rdi
  __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  __int64 v29; // rax
  void *v30; // rcx
  __int64 *v31; // rdi
  void *v32; // rcx
  __int128 v34; // [rsp+20h] [rbp-30h] BYREF
  __int64 v35; // [rsp+30h] [rbp-20h]
  unsigned __int64 v36; // [rsp+38h] [rbp-18h]
  __int64 v37; // [rsp+40h] [rbp-10h] BYREF

  if ( (__int128 *)a1 != a2 )
  {
    for ( i = (__int128 *)(a1 + 40); i != a2; i = (__int128 *)((char *)i + 40) )
    {
      v34 = 0;
      v34 = *i;
      v35 = *((_QWORD *)i + 2);
      v36 = *((_QWORD *)i + 3);
      *((_QWORD *)i + 2) = 0;
      *((_QWORD *)i + 3) = 7;
      *(_WORD *)i = 0;
      v7 = *((_QWORD *)i + 4);
      *((_QWORD *)i + 4) = 0;
      v37 = v7;
      v8 = (__int64 *)i;
      if ( a3(&v34, (__int64 *)a1) )
      {
        v9 = (__int64 *)i + 5;
        if ( (__int128 *)a1 != i )
        {
          do
          {
            v8 -= 5;
            v9 -= 5;
            if ( v9 != v8 )
            {
              v10 = v9[3];
              if ( v10 > 7 )
              {
                v11 = (char *)*v9;
                if ( 2 * v10 + 2 < 0x1000 )
                {
                  v12 = (char *)*v9;
                }
                else
                {
                  v12 = (char *)*((_QWORD *)v11 - 1);
                  if ( (unsigned __int64)(v11 - v12 - 8) > 0x1F )
                    goto LABEL_58;
                }
                operator delete(v12);
              }
              v9[2] = 0;
              v9[3] = 7;
              *(_WORD *)v9 = 0;
              *(_OWORD *)v9 = *(_OWORD *)v8;
              *((_OWORD *)v9 + 1) = *((_OWORD *)v8 + 1);
              v8[2] = 0;
              v8[3] = 7;
              *(_WORD *)v8 = 0;
            }
            v13 = v8 + 4;
            v14 = v9 + 4;
            if ( v9 + 4 != v8 + 4 )
            {
              v15 = *v14;
              *v14 = *v13;
              *v13 = v15;
            }
          }
          while ( (__int64 *)a1 != v8 );
        }
        if ( (__int128 *)a1 != &v34 )
        {
          v16 = *(_QWORD *)(a1 + 24);
          if ( v16 > 7 )
          {
            v17 = *(char **)a1;
            if ( 2 * v16 + 2 < 0x1000 )
            {
              v18 = *(char **)a1;
            }
            else
            {
              v18 = (char *)*((_QWORD *)v17 - 1);
              if ( (unsigned __int64)(v17 - v18 - 8) > 0x1F )
                goto LABEL_58;
            }
            operator delete(v18);
          }
          *(_OWORD *)a1 = v34;
          *(_QWORD *)(a1 + 16) = v35;
          *(_QWORD *)(a1 + 24) = v36;
          v35 = 0;
          v36 = 7;
          LOWORD(v34) = 0;
        }
        v19 = (__int64 *)(a1 + 32);
        if ( (__int64 *)(a1 + 32) == &v37 )
          goto LABEL_48;
        v20 = *v19;
        *v19 = v37;
        v37 = v20;
      }
      else
      {
        for ( j = (__int64 *)i - 5; a3(&v34, j); j -= 5 )
        {
          if ( v8 != j )
          {
            v22 = v8[3];
            if ( v22 > 7 )
            {
              v23 = *v8;
              if ( 2 * v22 + 2 < 0x1000 )
              {
                v24 = (void *)*v8;
              }
              else
              {
                v24 = *(void **)(v23 - 8);
                if ( (unsigned __int64)(v23 - (_QWORD)v24 - 8) > 0x1F )
                  goto LABEL_58;
              }
              operator delete(v24);
            }
            *(_OWORD *)v8 = *(_OWORD *)j;
            *((_OWORD *)v8 + 1) = *((_OWORD *)j + 1);
            j[2] = 0;
            j[3] = 7;
            *(_WORD *)j = 0;
          }
          v25 = j + 4;
          v26 = v8 + 4;
          if ( v26 != j + 4 )
          {
            v27 = *v26;
            *v26 = *v25;
            *v25 = v27;
          }
          v8 = j;
        }
        if ( v8 != (__int64 *)&v34 )
        {
          v28 = v8[3];
          if ( v28 > 7 )
          {
            v29 = *v8;
            if ( 2 * v28 + 2 < 0x1000 )
            {
              v30 = (void *)*v8;
            }
            else
            {
              v30 = *(void **)(v29 - 8);
              if ( (unsigned __int64)(v29 - (_QWORD)v30 - 8) > 0x1F )
LABEL_58:
                __fastfail(5u);
            }
            operator delete(v30);
          }
          *(_OWORD *)v8 = v34;
          v8[2] = v35;
          v8[3] = v36;
          v35 = 0;
          v36 = 7;
          LOWORD(v34) = 0;
        }
        v31 = v8 + 4;
        if ( v31 == &v37 )
        {
LABEL_48:
          v20 = v37;
          goto LABEL_49;
        }
        v20 = *v31;
        *v31 = v37;
        v37 = v20;
      }
LABEL_49:
      if ( v20 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 192LL))(v20, 1);
      if ( v36 > 7 )
      {
        v32 = (void *)v34;
        if ( 2 * v36 + 2 >= 0x1000 )
        {
          if ( (unsigned __int64)(v34 - *(_QWORD *)(v34 - 8) - 8) > 0x1F )
            __fastfail(5u);
          v32 = *(void **)(v34 - 8);
        }
        operator delete(v32);
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140004670  mov     [rsp-38h+arg_8], rbx
0x140004675  push    rbp
0x140004676  push    rsi
0x140004677  push    rdi
0x140004678  push    r12
0x14000467a  push    r13
0x14000467c  push    r14
0x14000467e  push    r15
0x140004680  mov     rbp, rsp
0x140004683  sub     rsp, 50h
0x140004687  mov     rax, cs:__security_cookie
0x14000468e  xor     rax, rsp
0x140004691  mov     [rbp+var_8], rax
0x140004695  mov     r15, r8
0x140004698  mov     r12, rdx
0x14000469b  mov     rsi, rcx
0x14000469e  cmp     rcx, rdx
0x1400046a1  jz      loc_140004A1F
0x1400046a7  lea     r14, [rcx+28h]
0x1400046ab  cmp     r14, rdx
0x1400046ae  jz      loc_140004A1F
0x1400046b4  xor     r13d, r13d
0x1400046b7  nop     word ptr [rax+rax+00000000h]
0x1400046c0  xorps   xmm0, xmm0
0x1400046c3  movups  [rbp+var_30], xmm0
0x1400046c7  mov     rax, [r14]
0x1400046ca  mov     qword ptr [rbp+var_30], rax
0x1400046ce  mov     rax, [r14+8]
0x1400046d2  mov     qword ptr [rbp+var_30+8], rax
0x1400046d6  mov     rax, [r14+10h]
0x1400046da  mov     [rbp+var_20], rax
0x1400046de  mov     rax, [r14+18h]
0x1400046e2  mov     [rbp+var_18], rax
0x1400046e6  mov     [r14+10h], r13
0x1400046ea  mov     qword ptr [r14+18h], 7
0x1400046f2  mov     [r14], r13w
0x1400046f6  mov     rax, [r14+20h]
0x1400046fa  mov     [r14+20h], r13
0x1400046fe  mov     [rbp+var_10], rax
0x140004702  mov     rdx, rsi
0x140004705  lea     rcx, [rbp+var_30]
0x140004709  mov     rax, r15
0x14000470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004711  mov     rdi, r14
0x140004714  test    al, al
0x140004716  jz      loc_14000486C
0x14000471c  lea     rbx, [r14+28h]
0x140004720  cmp     rsi, r14
0x140004723  jz      loc_1400047CE
0x140004729  nop     dword ptr [rax+00000000h]
0x140004730  sub     rdi, 28h ; '('
0x140004734  sub     rbx, 28h ; '('
0x140004738  cmp     rbx, rdi
0x14000473b  jz      short loc_1400047AC
0x14000473d  mov     rdx, [rbx+18h]
0x140004741  cmp     rdx, 7
0x140004745  jbe     short loc_14000477E
0x140004747  mov     rax, [rbx]
0x14000474a  lea     rdx, ds:2[rdx*2]
0x140004752  cmp     rdx, 1000h
0x140004759  jb      short loc_140004776
0x14000475b  mov     rcx, [rax-8]
0x14000475f  sub     rax, rcx
0x140004762  sub     rax, 8
0x140004766  cmp     rax, 1Fh
0x14000476a  ja      loc_140004A46
0x140004770  add     rdx, 27h ; '''
0x140004774  jmp     short loc_140004779
0x140004776  mov     rcx, rax; Block
0x140004779  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000477e  mov     [rbx+10h], r13
0x140004782  mov     qword ptr [rbx+18h], 7
0x14000478a  mov     [rbx], r13w
0x14000478e  movups  xmm0, xmmword ptr [rdi]
0x140004791  movups  xmmword ptr [rbx], xmm0
0x140004794  movups  xmm1, xmmword ptr [rdi+10h]
0x140004798  movups  xmmword ptr [rbx+10h], xmm1
0x14000479c  mov     [rdi+10h], r13
0x1400047a0  mov     qword ptr [rdi+18h], 7
0x1400047a8  mov     [rdi], r13w
0x1400047ac  lea     rdx, [rdi+20h]
0x1400047b0  lea     r8, [rbx+20h]
0x1400047b4  cmp     r8, rdx
0x1400047b7  jz      short loc_1400047C5
0x1400047b9  mov     rcx, [r8]
0x1400047bc  mov     rax, [rdx]
0x1400047bf  mov     [r8], rax
0x1400047c2  mov     [rdx], rcx
0x1400047c5  cmp     rsi, rdi
0x1400047c8  jnz     loc_140004730
0x1400047ce  lea     rax, [rbp+var_30]
0x1400047d2  cmp     rsi, rax
0x1400047d5  jz      short loc_140004848
0x1400047d7  mov     rdx, [rsi+18h]
0x1400047db  cmp     rdx, 7
0x1400047df  jbe     short loc_140004818
0x1400047e1  mov     rax, [rsi]
0x1400047e4  lea     rdx, ds:2[rdx*2]
0x1400047ec  cmp     rdx, 1000h
0x1400047f3  jb      short loc_140004810
0x1400047f5  mov     rcx, [rax-8]
0x1400047f9  sub     rax, rcx
0x1400047fc  sub     rax, 8
0x140004800  cmp     rax, 1Fh
0x140004804  ja      loc_140004A46
0x14000480a  add     rdx, 27h ; '''
0x14000480e  jmp     short loc_140004813
0x140004810  mov     rcx, rax; Block
0x140004813  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004818  mov     rax, qword ptr [rbp+var_30]
0x14000481c  mov     [rsi], rax
0x14000481f  mov     rax, qword ptr [rbp+var_30+8]
0x140004823  mov     [rsi+8], rax
0x140004827  mov     rax, [rbp+var_20]
0x14000482b  mov     [rsi+10h], rax
0x14000482f  mov     rax, [rbp+var_18]
0x140004833  mov     [rsi+18h], rax
0x140004837  mov     [rbp+var_20], r13
0x14000483b  mov     [rbp+var_18], 7
0x140004843  mov     word ptr [rbp+var_30], r13w
0x140004848  lea     rdx, [rsi+20h]
0x14000484c  lea     rax, [rbp+var_10]
0x140004850  cmp     rdx, rax
0x140004853  jz      loc_1400049B9
0x140004859  mov     rcx, [rdx]
0x14000485c  mov     rax, [rbp+var_10]
0x140004860  mov     [rdx], rax
0x140004863  mov     [rbp+var_10], rcx
0x140004867  jmp     loc_1400049BD
0x14000486c  lea     rbx, [r14-28h]
0x140004870  mov     rdx, rbx
0x140004873  lea     rcx, [rbp+var_30]
0x140004877  mov     rax, r15
0x14000487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000487f  test    al, al
0x140004881  jz      loc_140004922
0x140004887  cmp     rdi, rbx
0x14000488a  jz      short loc_1400048EB
0x14000488c  mov     rdx, [rdi+18h]
0x140004890  cmp     rdx, 7
0x140004894  jbe     short loc_1400048CD
0x140004896  mov     rax, [rdi]
0x140004899  lea     rdx, ds:2[rdx*2]
0x1400048a1  cmp     rdx, 1000h
0x1400048a8  jb      short loc_1400048C5
0x1400048aa  mov     rcx, [rax-8]
0x1400048ae  sub     rax, rcx
0x1400048b1  sub     rax, 8
0x1400048b5  cmp     rax, 1Fh
0x1400048b9  ja      loc_140004A46
0x1400048bf  add     rdx, 27h ; '''
0x1400048c3  jmp     short loc_1400048C8
0x1400048c5  mov     rcx, rax; Block
0x1400048c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400048cd  movups  xmm0, xmmword ptr [rbx]
0x1400048d0  movups  xmmword ptr [rdi], xmm0
0x1400048d3  movups  xmm1, xmmword ptr [rbx+10h]
0x1400048d7  movups  xmmword ptr [rdi+10h], xmm1
0x1400048db  mov     [rbx+10h], r13
0x1400048df  mov     qword ptr [rbx+18h], 7
0x1400048e7  mov     [rbx], r13w
0x1400048eb  lea     rdx, [rbx+20h]
0x1400048ef  add     rdi, 20h ; ' '
0x1400048f3  cmp     rdi, rdx
0x1400048f6  jz      short loc_140004904
0x1400048f8  mov     rcx, [rdi]
0x1400048fb  mov     rax, [rdx]
0x1400048fe  mov     [rdi], rax
0x140004901  mov     [rdx], rcx
0x140004904  mov     rdi, rbx
0x140004907  sub     rbx, 28h ; '('
0x14000490b  mov     rdx, rbx
0x14000490e  lea     rcx, [rbp+var_30]
0x140004912  mov     rax, r15
0x140004915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000491a  test    al, al
0x14000491c  jnz     loc_140004887
0x140004922  lea     rax, [rbp+var_30]
0x140004926  cmp     rdi, rax
0x140004929  jz      short loc_14000499C
0x14000492b  mov     rdx, [rdi+18h]
0x14000492f  cmp     rdx, 7
0x140004933  jbe     short loc_14000496C
0x140004935  mov     rax, [rdi]
0x140004938  lea     rdx, ds:2[rdx*2]
0x140004940  cmp     rdx, 1000h
0x140004947  jb      short loc_140004964
0x140004949  mov     rcx, [rax-8]
0x14000494d  sub     rax, rcx
0x140004950  sub     rax, 8
0x140004954  cmp     rax, 1Fh
0x140004958  ja      loc_140004A46
0x14000495e  add     rdx, 27h ; '''
0x140004962  jmp     short loc_140004967
0x140004964  mov     rcx, rax; Block
0x140004967  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000496c  mov     rax, qword ptr [rbp+var_30]
0x140004970  mov     [rdi], rax
0x140004973  mov     rax, qword ptr [rbp+var_30+8]
0x140004977  mov     [rdi+8], rax
0x14000497b  mov     rax, [rbp+var_20]
0x14000497f  mov     [rdi+10h], rax
0x140004983  mov     rax, [rbp+var_18]
0x140004987  mov     [rdi+18h], rax
0x14000498b  mov     [rbp+var_20], r13
0x14000498f  mov     [rbp+var_18], 7
0x140004997  mov     word ptr [rbp+var_30], r13w
0x14000499c  add     rdi, 20h ; ' '
0x1400049a0  lea     rax, [rbp+var_10]
0x1400049a4  cmp     rdi, rax
0x1400049a7  jz      short loc_1400049B9
0x1400049a9  mov     rcx, [rdi]
0x1400049ac  mov     rax, [rbp+var_10]
0x1400049b0  mov     [rdi], rax
0x1400049b3  mov     [rbp+var_10], rcx
0x1400049b7  jmp     short loc_1400049BD
0x1400049b9  mov     rcx, [rbp+var_10]
0x1400049bd  test    rcx, rcx
0x1400049c0  jz      short loc_1400049D6
0x1400049c2  mov     rax, [rcx]
0x1400049c5  mov     edx, 1
0x1400049ca  mov     rax, [rax+0C0h]
0x1400049d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049d6  mov     rdx, [rbp+var_18]
0x1400049da  cmp     rdx, 7
0x1400049de  jbe     short loc_140004A12
0x1400049e0  lea     rdx, ds:2[rdx*2]
0x1400049e8  mov     rcx, qword ptr [rbp+var_30]
0x1400049ec  cmp     rdx, 1000h
0x1400049f3  jb      short loc_140004A0D
0x1400049f5  mov     rax, [rcx-8]
0x1400049f9  sub     rcx, rax
0x1400049fc  sub     rcx, 8
0x140004a00  cmp     rcx, 1Fh
0x140004a04  ja      short loc_140004A4D
0x140004a06  add     rdx, 27h ; '''
0x140004a0a  mov     rcx, rax; Block
0x140004a0d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004a12  add     r14, 28h ; '('
0x140004a16  cmp     r14, r12
0x140004a19  jnz     loc_1400046C0
0x140004a1f  mov     rax, r12
0x140004a22  mov     rcx, [rbp+var_8]
0x140004a26  xor     rcx, rsp; StackCookie
0x140004a29  call    __security_check_cookie
0x140004a2e  mov     rbx, [rsp+50h+arg_8]
0x140004a36  add     rsp, 50h
0x140004a3a  pop     r15
0x140004a3c  pop     r14
0x140004a3e  pop     r13
0x140004a40  pop     r12
0x140004a42  pop     rdi
0x140004a43  pop     rsi
0x140004a44  pop     rbp
0x140004a45  retn
0x140004a46  mov     ecx, 5
0x140004a4b  int     29h; Win8: RtlFailFast(ecx)
0x140004a4d  mov     ecx, 5
0x140004a52  int     29h; Win8: RtlFailFast(ecx)
```
