# EndpointDlp::WindowsPlatformApi::GetUserEvaluationIds(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180071090`
- end: `0x1800714ee`
- name: `?GetUserEvaluationIds@WindowsPlatformApi@EndpointDlp@@UEBA?AV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `1118`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18002403c`
- `0x180024ac0`
- `0x18002c150`
- `0x180071090`
- `0x1800714f0`
- `0x180071710`
- `0x18010ce44`
- `0x180127010`
- `0x180181430`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800711ef`
- `KERNEL32!CompareStringOrdinal` at `0x18007142b`
- `KERNEL32!CompareStringOrdinal` at `0x1800711ef`
- `KERNEL32!CompareStringOrdinal` at `0x18007142b`
- `KERNEL32!AcquireSRWLockShared` at `0x180071193`
- `KERNEL32!AcquireSRWLockShared` at `0x180071193`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800713bd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800713bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char *__fastcall EndpointDlp::WindowsPlatformApi::GetUserEvaluationIds(RTL_SRWLOCK *a1, char *a2, const WCHAR *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rbx
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rax
  RTL_SRWLOCK *v12; // rsi
  char *Ptr; // rdi
  char *v14; // rbx
  char *v15; // rax
  const WCHAR *v16; // r8
  _QWORD *v17; // rbx
  _QWORD *v18; // rdi
  _QWORD *v19; // r15
  _QWORD *v20; // r13
  __int64 i; // r15
  _QWORD *v22; // r13
  _QWORD *v23; // rbp
  _QWORD *v24; // rsi
  __int64 v25; // rcx
  _QWORD *v26; // rax
  unsigned __int64 v27; // rdi
  __int64 v28; // rcx
  float v29; // xmm0_4
  float v30; // xmm0_4
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rcx
  const WCHAR *v35; // rcx
  const WCHAR *v36; // r8
  int v37; // eax
  char **v38; // rcx
  __int64 v39; // rax
  RTL_SRWLOCK *v40; // [rsp+70h] [rbp-58h]

  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  *((_OWORD *)a2 + 2) = 0;
  *((_OWORD *)a2 + 3) = 0;
  *(_DWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  v6 = operator new(0x50u);
  *v6 = v6;
  v6[1] = v6;
  *((_QWORD *)a2 + 1) = v6;
  *((_QWORD *)a2 + 3) = 0;
  *((_QWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 7;
  *((_QWORD *)a2 + 7) = 8;
  *(_DWORD *)a2 = 1065353216;
  v7 = *((_QWORD *)a2 + 1);
  v8 = operator new(0x80u);
  v9 = *((_QWORD *)a2 + 3);
  v10 = (*((_QWORD *)a2 + 5) - v9) >> 3;
  if ( v10 )
    std::_Deallocate<16>(v9, 8 * v10);
  *((_QWORD *)a2 + 3) = v8;
  v11 = v8 + 16;
  *((_QWORD *)a2 + 4) = v8 + 16;
  *((_QWORD *)a2 + 5) = v8 + 16;
  do
    *v8++ = v7;
  while ( v8 != v11 );
  v12 = a1 + 107;
  v40 = a1 + 107;
  AcquireSRWLockShared(a1 + 107);
  Ptr = (char *)a1[108].Ptr;
  v14 = (char *)*((_QWORD *)Ptr + 1);
  if ( v14[25] )
  {
    v15 = (char *)a1[108].Ptr;
  }
  else
  {
    do
    {
      v35 = (const WCHAR *)(v14 + 32);
      v36 = a3;
      if ( *((_QWORD *)a3 + 3) > 7u )
        v36 = *(const WCHAR **)a3;
      if ( *((_QWORD *)v14 + 7) > 7u )
        v35 = *(const WCHAR **)v35;
      v37 = CompareStringOrdinal(v35, -1, v36, -1, 1);
      if ( v37 != 1 )
        Ptr = v14;
      v38 = (char **)(v14 + 16);
      if ( v37 != 1 )
        v38 = (char **)v14;
      v14 = *v38;
    }
    while ( !(*v38)[25] );
    v15 = (char *)a1[108].Ptr;
  }
  if ( Ptr[25] )
    goto LABEL_14;
  v16 = (const WCHAR *)(Ptr + 32);
  if ( *((_QWORD *)Ptr + 7) > 7u )
    v16 = *(const WCHAR **)v16;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  if ( CompareStringOrdinal(a3, -1, v16, -1, 1) == 1 )
  {
    v15 = (char *)a1[108].Ptr;
LABEL_14:
    Ptr = v15;
  }
  if ( Ptr != a1[108].Ptr && a2 != Ptr + 64 )
  {
    *(_DWORD *)a2 = *((_DWORD *)Ptr + 16);
    v17 = (_QWORD *)*((_QWORD *)Ptr + 9);
    v18 = (_QWORD *)*v17;
    v19 = (_QWORD *)*((_QWORD *)a2 + 1);
    v20 = (_QWORD *)*v19;
    while ( v20 != v19 )
    {
      if ( v18 == v17 )
      {
        std::list<std::pair<std::wstring const,std::wstring>>::_Unchecked_erase(a2 + 8, v20, v19);
        goto LABEL_25;
      }
      std::wstring::operator=(v20 + 2, v18 + 2);
      std::wstring::operator=(v20 + 6, v18 + 6);
      v20 = (_QWORD *)*v20;
      v18 = (_QWORD *)*v18;
    }
    i = 0;
    if ( v18 == v17 )
    {
      v22 = 0;
      v23 = 0;
    }
    else
    {
      v22 = operator new(0x50u);
      std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v22 + 2, v18 + 2);
      v23 = v22;
      for ( i = 1; ; ++i )
      {
        v18 = (_QWORD *)*v18;
        if ( v18 == v17 )
          break;
        v24 = operator new(0x50u);
        std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v24 + 2, v18 + 2);
        *v23 = v24;
        v24[1] = v23;
        v23 = v24;
      }
    }
    v25 = *((_QWORD *)a2 + 1);
    if ( i )
    {
      v26 = *(_QWORD **)(v25 + 8);
      v22[1] = v26;
      *v26 = v22;
      *v23 = v25;
      *(_QWORD *)(v25 + 8) = v23;
      *((_QWORD *)a2 + 2) += i;
    }
LABEL_25:
    v27 = *((_QWORD *)a2 + 7);
    v28 = *((_QWORD *)a2 + 2);
    if ( v28 < 0 )
    {
      v39 = *((_QWORD *)a2 + 2) & 1LL | ((unsigned __int64)v28 >> 1);
      v29 = (float)(int)v39 + (float)(int)v39;
    }
    else
    {
      v29 = (float)(int)v28;
    }
    v30 = ceilf(v29 / *(float *)a2);
    v31 = 0;
    if ( v30 >= 9.223372e18 )
    {
      v30 = v30 - 9.223372e18;
      if ( v30 < 9.223372e18 )
        v31 = 0x8000000000000000uLL;
    }
    v32 = v31 + (unsigned int)(int)v30;
    v33 = 8;
    if ( v32 > 8 )
      v33 = v32;
    if ( v27 < v33 )
    {
      if ( v27 >= 0x200 || (v27 *= 8LL, v27 < v33) )
        v27 = v33;
    }
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
      a2,
      v27);
    v12 = v40;
  }
  if ( v12 )
    ReleaseSRWLockShared(v12);
  return a2;
}

```

## disassembly

```asm
0x180071090  mov     [rsp+arg_18], rbx
0x180071095  mov     [rsp+arg_8], rdx
0x18007109a  push    rbp
0x18007109b  push    rsi
0x18007109c  push    rdi
0x18007109d  push    r12
0x18007109f  push    r13
0x1800710a1  push    r14
0x1800710a3  push    r15
0x1800710a5  sub     rsp, 90h
0x1800710ac  mov     r15, r8
0x1800710af  mov     r14, rdx
0x1800710b2  mov     rbp, rcx
0x1800710b5  mov     [rsp+0C8h+var_50], rdx
0x1800710ba  xor     edi, edi
0x1800710bc  mov     [rsp+0C8h+var_98], edi
0x1800710c0  xorps   xmm0, xmm0
0x1800710c3  movups  xmmword ptr [rdx], xmm0
0x1800710c6  movups  xmmword ptr [rdx+10h], xmm0
0x1800710ca  movups  xmmword ptr [rdx+20h], xmm0
0x1800710ce  movups  xmmword ptr [rdx+30h], xmm0
0x1800710d2  mov     [rdx], edi
0x1800710d4  mov     [rdx+8], rdi
0x1800710d8  mov     [rdx+10h], rdi
0x1800710dc  mov     ecx, 50h ; 'P'; Size
0x1800710e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800710e6  mov     [rax], rax
0x1800710e9  mov     [rax+8], rax
0x1800710ed  mov     [r14+8], rax
0x1800710f1  mov     [r14+18h], rdi
0x1800710f5  mov     [r14+20h], rdi
0x1800710f9  mov     [r14+28h], rdi
0x1800710fd  mov     qword ptr [r14+30h], 7
0x180071105  mov     qword ptr [r14+38h], 8
0x18007110d  mov     dword ptr [r14], 3F800000h
0x180071114  mov     rbx, [r14+8]
0x180071118  mov     ecx, edi
0x18007111a  mov     eax, edi
0x18007111c  sar     rax, 3
0x180071120  cmp     rax, 10h
0x180071124  jnb     loc_1800713E1
0x18007112a  mov     ecx, 80h; Size
0x18007112f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180071134  mov     rdi, rax
0x180071137  mov     rcx, [r14+18h]
0x18007113b  mov     rdx, [r14+28h]
0x18007113f  sub     rdx, rcx
0x180071142  sar     rdx, 3
0x180071146  test    rdx, rdx
0x180071149  jnz     loc_18007149F
0x18007114f  mov     [r14+18h], rdi
0x180071153  lea     rax, [rdi+80h]
0x18007115a  mov     [r14+20h], rax
0x18007115e  mov     [r14+28h], rax
0x180071162  cmp     rdi, rax
0x180071165  jz      short loc_18007117C
0x180071167  nop     word ptr [rax+rax+00000000h]
0x180071170  mov     [rdi], rbx
0x180071173  add     rdi, 8
0x180071177  cmp     rdi, rax
0x18007117a  jnz     short loc_180071170
0x18007117c  mov     [rsp+0C8h+var_98], 1
0x180071184  lea     rsi, [rbp+358h]
0x18007118b  mov     [rsp+0C8h+var_58], rsi
0x180071190  mov     rcx, rsi; SRWLock
0x180071193  call    cs:__imp_AcquireSRWLockShared
0x180071199  mov     [rsp+0C8h+var_48], rsi
0x1800711a1  mov     rdi, [rbp+360h]
0x1800711a8  mov     rbx, [rdi+8]
0x1800711ac  xor     eax, eax
0x1800711ae  mov     [rsp+0C8h+var_84], eax
0x1800711b2  cmp     [rbx+19h], al
0x1800711b5  jz      loc_180071400
0x1800711bb  mov     rax, rdi
0x1800711be  cmp     byte ptr [rdi+19h], 0
0x1800711c2  jnz     short loc_180071201
0x1800711c4  lea     r8, [rdi+20h]
0x1800711c8  cmp     qword ptr [r8+18h], 7
0x1800711cd  jbe     short loc_1800711D2
0x1800711cf  mov     r8, [r8]; lpString2
0x1800711d2  cmp     qword ptr [r15+18h], 7
0x1800711d7  jbe     short loc_1800711DC
0x1800711d9  mov     r15, [r15]
0x1800711dc  mov     [rsp+0C8h+bIgnoreCase], 1; bIgnoreCase
0x1800711e4  mov     edx, 0FFFFFFFFh; cchCount1
0x1800711e9  mov     r9d, edx; cchCount2
0x1800711ec  mov     rcx, r15; lpString1
0x1800711ef  call    cs:__imp_CompareStringOrdinal
0x1800711f5  cmp     eax, 1
0x1800711f8  jnz     short loc_180071204
0x1800711fa  mov     rax, [rbp+360h]
0x180071201  mov     rdi, rax
0x180071204  cmp     rdi, [rbp+360h]
0x18007120b  jz      loc_1800713B5
0x180071211  lea     rbx, [rdi+40h]
0x180071215  cmp     r14, rbx
0x180071218  jz      loc_1800713B5
0x18007121e  mov     [rsp+0C8h+var_40], r14
0x180071226  mov     eax, [rbx]
0x180071228  mov     [r14], eax
0x18007122b  lea     r12, [r14+8]
0x18007122f  mov     rbx, [rbx+8]
0x180071233  mov     rdi, [rbx]
0x180071236  mov     r15, [r12]
0x18007123a  mov     r13, [r15]
0x18007123d  cmp     r13, r15
0x180071240  jnz     loc_180071474
0x180071246  mov     [rsp+0C8h+var_78], r12
0x18007124b  xor     esi, esi
0x18007124d  mov     r15d, esi
0x180071250  mov     [rsp+0C8h+var_70], rsi
0x180071255  xorps   xmm0, xmm0
0x180071258  movdqu  [rsp+0C8h+var_68], xmm0
0x18007125e  cmp     rdi, rbx
0x180071261  jz      loc_1800714DE
0x180071267  mov     [rsp+0C8h+var_90], r12
0x18007126c  mov     [rsp+40h], rsi
0x180071271  mov     ecx, 50h ; 'P'; Size
0x180071276  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007127b  mov     r13, rax
0x18007127e  mov     [rsp+40h], rax
0x180071283  lea     rdx, [rdi+10h]
0x180071287  lea     rcx, [rax+10h]
0x18007128b  call    ??0?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(std::pair<std::wstring const,std::wstring> const &)
0x180071290  mov     [rsp+40h], rsi
0x180071295  mov     qword ptr [rsp+0C8h+var_68+8], r13
0x18007129a  mov     rbp, r13
0x18007129d  mov     qword ptr [rsp+0C8h+var_68], r13
0x1800712a2  mov     r15d, 1
0x1800712a8  mov     rdi, [rdi]
0x1800712ab  mov     [rsp+0C8h+var_70], r15
0x1800712b0  cmp     rdi, rbx
0x1800712b3  jz      short loc_1800712F9
0x1800712b5  mov     [rsp+40h], rsi
0x1800712ba  mov     ecx, 50h ; 'P'; Size
0x1800712bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800712c4  mov     rsi, rax
0x1800712c7  mov     [rsp+40h], rax
0x1800712cc  lea     rdx, [rdi+10h]
0x1800712d0  lea     rcx, [rax+10h]
0x1800712d4  call    ??0?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(std::pair<std::wstring const,std::wstring> const &)
0x1800712d9  mov     [rbp+0], rsi
0x1800712dd  mov     [rsi+8], rbp
0x1800712e1  mov     qword ptr [rsp+40h], 0
0x1800712ea  mov     rbp, rsi
0x1800712ed  mov     qword ptr [rsp+0C8h+var_68], rsi
0x1800712f2  inc     r15
0x1800712f5  xor     esi, esi
0x1800712f7  jmp     short loc_1800712A8
0x1800712f9  mov     rcx, [r12]
0x1800712fd  test    r15, r15
0x180071300  jz      short loc_18007131D
0x180071302  mov     rax, [rcx+8]
0x180071306  mov     [r13+8], rax
0x18007130a  mov     [rax], r13
0x18007130d  mov     [rbp+0], rcx
0x180071311  mov     [rcx+8], rbp
0x180071315  add     [r12+8], r15
0x18007131a  mov     r15, rsi
0x18007131d  test    r15, r15
0x180071320  jnz     loc_180071455
0x180071326  mov     rdi, [r14+38h]
0x18007132a  mov     rcx, [r14+10h]
0x18007132e  xorps   xmm0, xmm0
0x180071331  test    rcx, rcx
0x180071334  js      loc_1800714B1
0x18007133a  cvtsi2ss xmm0, rcx
0x18007133f  divss   xmm0, dword ptr [r14]; X
0x180071344  call    ceilf
0x180071349  xor     ecx, ecx
0x18007134b  movss   xmm1, cs:__real@5f000000
0x180071353  comiss  xmm0, xmm1
0x180071356  jb      short loc_18007136E
0x180071358  subss   xmm0, xmm1
0x18007135c  comiss  xmm0, xmm1
0x18007135f  jnb     short loc_18007136E
0x180071361  mov     rax, 8000000000000000h
0x18007136b  mov     rcx, rax
0x18007136e  cvttss2si rax, xmm0
0x180071373  add     rax, rcx
0x180071376  cmp     rax, 8
0x18007137a  mov     ecx, 8
0x18007137f  cmova   rcx, rax
0x180071383  cmp     rdi, rcx
0x180071386  jnb     short loc_1800713A4
0x180071388  cmp     rdi, 200h
0x18007138f  jnb     short loc_1800713A1
0x180071391  lea     rax, ds:0[rdi*8]
0x180071399  mov     rdi, rax
0x18007139c  cmp     rax, rcx
0x18007139f  jnb     short loc_1800713A4
0x1800713a1  mov     rdi, rcx
0x1800713a4  mov     rdx, rdi
0x1800713a7  mov     rcx, r14
0x1800713aa  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(unsigned __int64)
0x1800713af  nop
0x1800713b0  mov     rsi, [rsp+0C8h+var_58]
0x1800713b5  test    rsi, rsi
0x1800713b8  jz      short loc_1800713C3
0x1800713ba  mov     rcx, rsi; SRWLock
0x1800713bd  call    cs:__imp_ReleaseSRWLockShared
0x1800713c3  mov     rax, r14
0x1800713c6  mov     rbx, [rsp+0C8h+arg_18]
0x1800713ce  add     rsp, 90h
0x1800713d5  pop     r15
0x1800713d7  pop     r14
0x1800713d9  pop     r13
0x1800713db  pop     r12
0x1800713dd  pop     rdi
0x1800713de  pop     rsi
0x1800713df  pop     rbp
0x1800713e0  retn
0x1800713e1  add     rcx, 7
0x1800713e5  shr     rcx, 3
0x1800713e9  test    rcx, rcx
0x1800713ec  jz      loc_18007117C
0x1800713f2  xor     edi, edi
0x1800713f4  mov     rax, rbx
0x1800713f7  rep stosq
0x1800713fa  jmp     loc_18007117C
0x180071400  lea     rcx, [rbx+20h]
0x180071404  mov     r8, r15
0x180071407  cmp     qword ptr [r15+18h], 7
0x18007140c  jbe     short loc_180071411
0x18007140e  mov     r8, [r15]; lpString2
0x180071411  cmp     qword ptr [rcx+18h], 7
0x180071416  jbe     short loc_18007141B
0x180071418  mov     rcx, [rcx]; lpString1
0x18007141b  mov     [rsp+0C8h+bIgnoreCase], 1; bIgnoreCase
0x180071423  mov     edx, 0FFFFFFFFh; cchCount1
0x180071428  mov     r9d, edx; cchCount2
0x18007142b  call    cs:__imp_CompareStringOrdinal
0x180071431  cmp     eax, 1
0x180071434  cmovnz  rdi, rbx
0x180071438  lea     rcx, [rbx+10h]
0x18007143c  cmovnz  rcx, rbx
0x180071440  mov     rbx, [rcx]
0x180071443  cmp     byte ptr [rbx+19h], 0
0x180071447  jz      short loc_180071400
0x180071449  mov     rax, [rbp+360h]
0x180071450  jmp     loc_1800711BE
0x180071455  mov     [r13+8], rsi
0x180071459  mov     [rbp+0], rsi
0x18007145d  mov     rdx, r13
0x180071460  mov     r13, [r13+0]
0x180071464  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180071469  test    r13, r13
0x18007146c  jz      loc_180071326
0x180071472  jmp     short loc_18007145D
0x180071474  cmp     rdi, rbx
0x180071477  jz      short loc_1800714CB
0x180071479  lea     rdx, [rdi+10h]; Src
0x18007147d  lea     rcx, [r13+10h]; void *
0x180071481  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180071486  lea     rdx, [rdi+30h]; Src
0x18007148a  lea     rcx, [r13+30h]; void *
0x18007148e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180071493  mov     r13, [r13+0]
0x180071497  mov     rdi, [rdi]
0x18007149a  jmp     loc_18007123D
0x18007149f  lea     rdx, ds:0[rdx*8]
0x1800714a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800714ac  jmp     loc_18007114F
0x1800714b1  mov     rax, rcx
0x1800714b4  shr     rax, 1
0x1800714b7  and     ecx, 1
0x1800714ba  or      rax, rcx
0x1800714bd  cvtsi2ss xmm0, rax
0x1800714c2  addss   xmm0, xmm0
0x1800714c6  jmp     loc_18007133F
0x1800714cb  mov     r8, r15
0x1800714ce  mov     rdx, r13
0x1800714d1  mov     rcx, r12
0x1800714d4  call    ?_Unchecked_erase@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::list<std::pair<std::wstring const,std::wstring>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x1800714d9  jmp     loc_180071326
0x1800714de  mov     r13, qword ptr [rsp+0C8h+var_68+8]
0x1800714e3  mov     rbp, qword ptr [rsp+0C8h+var_68]
0x1800714e8  jmp     loc_1800712F9
```
