# sfac_ComputeMapping(sfac_ClientRec *,ushort,ushort)

- ea: `0x140011484`
- end: `0x140011901`
- name: `?sfac_ComputeMapping@@YAHPEAUsfac_ClientRec@@GG@Z`
- size: `1149`
- prototype: `__int64 __fastcall(struct sfac_ClientRec *, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a538`

## callees

- `0x140011484`
- `0x140013240`
- `0x1400265a8`
- `0x14002926c`
- `0x140050e4c`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sfac_ComputeMapping(__int64 a1, __int64 a2, __int16 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // r13
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned __int16 *v7; // r15
  __int64 v8; // r14
  unsigned __int64 v9; // rdx
  char v10; // r12
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned int v20; // r12d
  unsigned __int16 v21; // cx
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int8 *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 v27; // rsi
  __int64 (__fastcall *v29)(); // rax
  unsigned int v30; // ebx
  __int64 v31; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v32; // [rsp+38h] [rbp-28h]
  char v33[8]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v34[3]; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v36; // [rsp+B8h] [rbp+58h] BYREF

  v4 = (unsigned __int16)a2;
  v5 = a1;
  if ( (_WORD)a2 == 0xFFFF )
  {
    *(_QWORD *)(a1 + 224) = _scrt_initialize_winrt;
    return 0;
  }
  v6 = *(unsigned int *)(a1 + 100);
  v7 = 0;
  v8 = 0;
  v31 = 0;
  if ( (_DWORD)v6 )
  {
    if ( (unsigned int)v6 > 0x7FFFFFFF || (a2 = *(unsigned int *)(a1 + 96), (unsigned int)a2 > 0x7FFFFFFF) )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
      goto LABEL_47;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *))(a1 + 8))(
           *(_QWORD *)a1,
           a2,
           (unsigned int)v6,
           &v31);
    v8 = v31;
  }
  else
  {
    v3 = 0;
  }
  v34[0] = v5;
  v34[1] = v8;
  if ( !v3 )
  {
    v30 = 0;
LABEL_73:
    *(_QWORD *)(v5 + 224) = _scrt_initialize_winrt;
    AutoReleaseSfntFrag::~AutoReleaseSfntFrag((AutoReleaseSfntFrag *)v34);
    return v30;
  }
  if ( (unsigned int)v6 < 4 )
    goto LABEL_43;
  v9 = 8 * (*(unsigned __int8 *)(v3 + 3) | ((unsigned __int64)*(unsigned __int8 *)(v3 + 2) << 8));
  if ( v9 > 0xFFFF )
  {
LABEL_55:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, v9);
    __debugbreak();
  }
  v10 = 0;
  v11 = v3 + 4;
  v36 = v3 + 4;
  v12 = *(_QWORD *)operator+=<unsigned char,unsigned short,SafeIntExceptionHandler<SafeIntRasterizerException>>(&v36);
  v32 = v12;
  v9 = 0;
  while ( 1 )
  {
    a1 = 0xFFFFFFFFLL;
    if ( v11 >= v12 )
    {
      if ( !v10 )
      {
        *(_DWORD *)(v5 + 28) = 0;
LABEL_72:
        v30 = 5126;
        goto LABEL_73;
      }
LABEL_19:
      v36 = *(unsigned int *)(v5 + 28);
      v15 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                         &v36,
                         v33,
                         1);
      if ( v15 < 0 )
      {
        v15 = -v15;
        if ( v15 <= v3 )
        {
          v7 = (unsigned __int16 *)(v3 - v15);
LABEL_21:
          v16 = *(unsigned int *)(v5 + 28) + 6LL;
          a1 = 0xFFFFFFFFLL;
          if ( v16 <= 0xFFFFFFFF )
          {
            *(_DWORD *)(v5 + 28) = v16;
            v4 = (unsigned int)(v6 - 2);
            v36 = v4;
            v18 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                               &v36,
                               v33,
                               1);
            LODWORD(v6) = 0;
            if ( v18 >= 0 )
            {
              v19 = v18 + v3;
              if ( v18 + v3 >= v3 )
                goto LABEL_24;
              goto LABEL_48;
            }
LABEL_47:
            v18 = -v18;
            if ( v18 <= v3 )
            {
              v19 = v3 - v18;
LABEL_24:
              if ( (unsigned __int64)v7 > v19 )
              {
LABEL_71:
                *(_DWORD *)(v5 + 28) = v6;
                goto LABEL_72;
              }
              v20 = v6;
              v21 = _byteswap_ushort(*v7);
              *(_WORD *)(v5 + 222) = v21;
              if ( v21 )
              {
                switch ( v21 )
                {
                  case 2u:
                    v29 = sfac_ComputeIndex2;
                    break;
                  case 4u:
                    *(_QWORD *)(v5 + 224) = sfac_ComputeIndex4;
                    v36 = *(unsigned int *)(v5 + 28);
                    v23 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                                       &v36,
                                       v33,
                                       1);
                    if ( v23 < 0 )
                    {
                      v23 = -v23;
                      if ( v23 <= v3 )
                      {
                        v24 = (unsigned __int8 *)(v3 - v23);
LABEL_30:
                        v36 = v4;
                        v26 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                                           &v36,
                                           v33,
                                           1);
                        if ( v26 < 0 )
                        {
                          v26 = -v26;
                          if ( v26 <= v3 )
                          {
                            v27 = v3 - v26;
                            goto LABEL_33;
                          }
                        }
                        else if ( v26 + v3 >= v3 )
                        {
                          v27 = v26 + v3;
LABEL_33:
                          if ( (unsigned __int64)v24 <= v27 )
                          {
                            sfac_ComputeBinarySearchParams(
                              (unsigned __int16)(*v24 << 7) | (unsigned __int8)(v24[1] >> 1),
                              v5 + 234,
                              v5 + 236,
                              v5 + 238);
LABEL_35:
                            if ( v8 )
                              (*(void (__fastcall **)(__int64))(v5 + 16))(v8);
                            return v20;
                          }
                          LODWORD(v6) = 0;
                          goto LABEL_71;
                        }
                        SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v26, v25);
                        __debugbreak();
                      }
                    }
                    else
                    {
                      v24 = (unsigned __int8 *)(v23 + v3);
                      if ( v23 + v3 >= v3 )
                        goto LABEL_30;
                    }
                    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v23, v22);
                    __debugbreak();
                  case 6u:
                    v29 = sfac_ComputeIndex6;
                    break;
                  default:
                    v29 = _scrt_initialize_winrt;
                    v20 = 5130;
                    break;
                }
              }
              else
              {
                v29 = sfac_ComputeIndex0;
              }
              *(_QWORD *)(v5 + 224) = v29;
              goto LABEL_35;
            }
LABEL_48:
            SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v18, v17);
            __debugbreak();
          }
          goto LABEL_55;
        }
      }
      else
      {
        v7 = (unsigned __int16 *)(v15 + v3);
        if ( v15 + v3 >= v3 )
          goto LABEL_21;
      }
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v15, v9);
      __debugbreak();
    }
    if ( v10 )
      goto LABEL_19;
    if ( (unsigned __int64)(v6 - 8) > 0xFFFFFFFF )
      goto LABEL_55;
    v36 = (unsigned int)(v6 - 8);
    v13 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                       &v36,
                       v33,
                       1);
    v9 = 0;
    if ( v13 < 0 )
      break;
    v14 = v13 + v3;
    if ( v13 + v3 < v3 )
      goto LABEL_42;
LABEL_15:
    if ( v11 > v14 )
      goto LABEL_43;
    if ( _byteswap_ushort(*(_WORD *)v11) == (_WORD)v4 && _byteswap_ushort(*(_WORD *)(v11 + 2)) == a3 )
    {
      v10 = 1;
      *(_DWORD *)(v5 + 28) = *(unsigned __int8 *)(v11 + 7)
                           | ((*(unsigned __int8 *)(v11 + 6)
                             | ((*(unsigned __int8 *)(v11 + 5) | (*(unsigned __int8 *)(v11 + 4) << 8)) << 8)) << 8);
    }
    v11 += 8LL;
    v12 = v32;
  }
  v13 = -v13;
  if ( v13 <= v3 )
  {
    v14 = v3 - v13;
    goto LABEL_15;
  }
LABEL_42:
  SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v13, 0);
LABEL_43:
  if ( v8 )
    (*(void (__fastcall **)(__int64))(v5 + 16))(v8);
  return 5126;
}

```

## disassembly

```asm
0x140011484  mov     [rsp-38h+arg_0], rbx
0x140011489  mov     [rsp-38h+arg_10], r8w
0x14001148f  push    rbp
0x140011490  push    rsi
0x140011491  push    rdi
0x140011492  push    r12
0x140011494  push    r13
0x140011496  push    r14
0x140011498  push    r15
0x14001149a  mov     rbp, rsp
0x14001149d  sub     rsp, 60h
0x1400114a1  movzx   r13d, dx
0x1400114a5  mov     rdi, rcx
0x1400114a8  mov     r12d, 0FFFFh
0x1400114ae  cmp     dx, r12w
0x1400114b2  jz      loc_1400117B3
0x1400114b8  mov     ebx, [rcx+64h]
0x1400114bb  xor     r15d, r15d
0x1400114be  mov     r14d, r15d
0x1400114c1  mov     [rbp+var_30], r15
0x1400114c5  test    ebx, ebx
0x1400114c7  jz      loc_140011841
0x1400114cd  mov     eax, 7FFFFFFFh
0x1400114d2  cmp     ebx, eax
0x1400114d4  ja      loc_1400117EA
0x1400114da  mov     edx, [rcx+60h]
0x1400114dd  cmp     edx, eax
0x1400114df  ja      loc_1400117EA
0x1400114e5  lea     r9, [rbp+var_30]
0x1400114e9  mov     r8d, ebx
0x1400114ec  mov     rcx, [rcx]
0x1400114ef  mov     rax, [rdi+8]
0x1400114f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114f8  mov     rsi, rax
0x1400114fb  mov     r14, [rbp+var_30]
0x1400114ff  mov     [rbp+var_18], rdi
0x140011503  mov     [rbp+var_10], r14
0x140011507  test    rsi, rsi
0x14001150a  jz      loc_14001189F
0x140011510  cmp     ebx, 4
0x140011513  jb      loc_1400117D7
0x140011519  movzx   edx, byte ptr [rsi+2]
0x14001151d  shl     rdx, 8
0x140011521  movzx   eax, byte ptr [rsi+3]
0x140011525  or      rdx, rax
0x140011528  shl     rdx, 3
0x14001152c  cmp     rdx, r12
0x14001152f  ja      loc_140011828
0x140011535  mov     r12b, r15b
0x140011538  lea     r15, [rsi+4]
0x14001153c  mov     [rbp+arg_18], r15
0x140011540  lea     rcx, [rbp+arg_18]
0x140011544  call    ??$?YEGV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEAEAEAPEAEV?$SafeInt@GV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar,ushort,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar * &,SafeInt<ushort,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140011549  mov     rax, [rax]
0x14001154c  mov     [rbp+var_28], rax
0x140011550  xor     edx, edx
0x140011552  mov     ecx, 0FFFFFFFFh
0x140011557  cmp     r15, rax
0x14001155a  jnb     short loc_1400115CF
0x14001155c  test    r12b, r12b
0x14001155f  jnz     short loc_1400115D8
0x140011561  lea     rax, [rbx-8]
0x140011565  cmp     rax, rcx
0x140011568  ja      loc_140011828
0x14001156e  mov     eax, eax
0x140011570  mov     [rbp+arg_18], rax
0x140011574  mov     r8d, 1
0x14001157a  lea     rdx, [rbp+var_20]
0x14001157e  lea     rcx, [rbp+arg_18]
0x140011582  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140011587  mov     rcx, [rax]
0x14001158a  xor     edx, edx
0x14001158c  test    rcx, rcx
0x14001158f  js      loc_1400117C5
0x140011595  lea     rax, [rcx+rsi]
0x140011599  cmp     rax, rsi
0x14001159c  jb      loc_1400117D1
0x1400115a2  cmp     r15, rax
0x1400115a5  ja      loc_1400117D7
0x1400115ab  movzx   ecx, byte ptr [r15]
0x1400115af  shl     cx, 8
0x1400115b3  movzx   eax, byte ptr [r15+1]
0x1400115b8  or      cx, ax
0x1400115bb  cmp     cx, r13w
0x1400115bf  jz      loc_14001176A
0x1400115c5  add     r15, 8
0x1400115c9  mov     rax, [rbp+var_28]
0x1400115cd  jmp     short loc_140011552
0x1400115cf  test    r12b, r12b
0x1400115d2  jz      loc_1400118A4
0x1400115d8  mov     eax, [rdi+1Ch]
0x1400115db  mov     [rbp+arg_18], rax
0x1400115df  mov     r8d, 1
0x1400115e5  lea     rdx, [rbp+var_20]
0x1400115e9  lea     rcx, [rbp+arg_18]
0x1400115ed  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x1400115f2  mov     rcx, [rax]
0x1400115f5  test    rcx, rcx
0x1400115f8  js      loc_1400117FE
0x1400115fe  lea     r15, [rcx+rsi]
0x140011602  cmp     r15, rsi
0x140011605  jb      loc_140011806
0x14001160b  mov     eax, [rdi+1Ch]
0x14001160e  add     rax, 6
0x140011612  mov     ecx, 0FFFFFFFFh
0x140011617  cmp     rax, rcx
0x14001161a  ja      loc_140011828
0x140011620  mov     [rdi+1Ch], eax
0x140011623  add     ebx, 0FFFFFFFEh
0x140011626  mov     r13d, ebx
0x140011629  mov     [rbp+arg_18], r13
0x14001162d  mov     r8d, 1
0x140011633  lea     rdx, [rbp+var_20]
0x140011637  lea     rcx, [rbp+arg_18]
0x14001163b  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140011640  mov     rcx, [rax]
0x140011643  xor     ebx, ebx
0x140011645  test    rcx, rcx
0x140011648  js      loc_1400117F0
0x14001164e  lea     rax, [rcx+rsi]
0x140011652  cmp     rax, rsi
0x140011655  jb      loc_1400117F8
0x14001165b  cmp     r15, rax
0x14001165e  ja      loc_1400118DB
0x140011664  mov     r12d, ebx
0x140011667  movzx   ecx, byte ptr [r15]
0x14001166b  shl     cx, 8
0x14001166f  movzx   eax, byte ptr [r15+1]
0x140011674  or      cx, ax
0x140011677  mov     [rdi+0DEh], cx
0x14001167e  jz      loc_14001182E
0x140011684  cmp     cx, 2
0x140011688  jz      loc_1400118CD
0x14001168e  mov     eax, 4
0x140011693  cmp     cx, ax
0x140011696  jnz     loc_1400118A9
0x14001169c  lea     rax, sfac_ComputeIndex4
0x1400116a3  mov     [rdi+0E0h], rax
0x1400116aa  mov     eax, [rdi+1Ch]
0x1400116ad  mov     [rbp+arg_18], rax
0x1400116b1  mov     r15d, 1
0x1400116b7  mov     r8d, r15d
0x1400116ba  lea     rdx, [rbp+var_20]
0x1400116be  lea     rcx, [rbp+arg_18]
0x1400116c2  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x1400116c7  mov     rcx, [rax]
0x1400116ca  test    rcx, rcx
0x1400116cd  js      loc_14001181A
0x1400116d3  lea     rbx, [rcx+rsi]
0x1400116d7  cmp     rbx, rsi
0x1400116da  jb      loc_140011822
0x1400116e0  mov     [rbp+arg_18], r13
0x1400116e4  mov     r8, r15
0x1400116e7  lea     rdx, [rbp+var_20]
0x1400116eb  lea     rcx, [rbp+arg_18]
0x1400116ef  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x1400116f4  mov     rcx, [rax]
0x1400116f7  test    rcx, rcx
0x1400116fa  js      loc_14001180C
0x140011700  lea     rax, [rcx+rsi]
0x140011704  cmp     rax, rsi
0x140011707  jb      loc_140011814
0x14001170d  mov     rsi, rax
0x140011710  cmp     rbx, rsi
0x140011713  ja      loc_1400118D9
0x140011719  lea     r9, [rdi+0EEh]
0x140011720  lea     r8, [rdi+0ECh]
0x140011727  lea     rdx, [rdi+0EAh]
0x14001172e  mov     al, [rbx+1]
0x140011731  shr     al, 1
0x140011733  movzx   ecx, al
0x140011736  movzx   eax, byte ptr [rbx]
0x140011739  shl     ax, 7
0x14001173d  or      cx, ax
0x140011740  call    sfac_ComputeBinarySearchParams
0x140011745  nop
0x140011746  test    r14, r14
0x140011749  jnz     loc_140011849
0x14001174f  mov     eax, r12d
0x140011752  mov     rbx, [rsp+60h+arg_0]
0x14001175a  add     rsp, 60h
0x14001175e  pop     r15
0x140011760  pop     r14
0x140011762  pop     r13
0x140011764  pop     r12
0x140011766  pop     rdi
0x140011767  pop     rsi
0x140011768  pop     rbp
0x140011769  retn
0x14001176a  movzx   ecx, byte ptr [r15+2]
0x14001176f  shl     cx, 8
0x140011773  movzx   eax, byte ptr [r15+3]
0x140011778  or      cx, ax
0x14001177b  cmp     cx, [rbp+arg_10]
0x14001177f  jnz     loc_1400115C5
0x140011785  mov     r12b, 1
0x140011788  movzx   ecx, byte ptr [r15+4]
0x14001178d  shl     ecx, 8
0x140011790  movzx   eax, byte ptr [r15+5]
0x140011795  or      ecx, eax
0x140011797  shl     ecx, 8
0x14001179a  movzx   eax, byte ptr [r15+6]
0x14001179f  or      ecx, eax
0x1400117a1  shl     ecx, 8
0x1400117a4  movzx   eax, byte ptr [r15+7]
0x1400117a9  or      ecx, eax
0x1400117ab  mov     [rdi+1Ch], ecx
0x1400117ae  jmp     loc_1400115C5
0x1400117b3  lea     rax, __scrt_initialize_winrt
0x1400117ba  mov     [rcx+0E0h], rax
0x1400117c1  xor     eax, eax
0x1400117c3  jmp     short loc_140011752
0x1400117c5  neg     rcx
0x1400117c8  cmp     rcx, rsi
0x1400117cb  jbe     loc_14001185A
0x1400117d1  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x1400117d6  nop
0x1400117d7  test    r14, r14
0x1400117da  jnz     loc_14001188E
0x1400117e0  mov     eax, 1406h
0x1400117e5  jmp     loc_140011752
0x1400117ea  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x1400117ef  nop
0x1400117f0  neg     rcx
0x1400117f3  cmp     rcx, rsi
0x1400117f6  jbe     short loc_140011870
0x1400117f8  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x1400117fd  int     3; Trap to Debugger
0x1400117fe  neg     rcx
0x140011801  cmp     rcx, rsi
0x140011804  jbe     short loc_140011865
0x140011806  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001180b  int     3; Trap to Debugger
0x14001180c  neg     rcx
0x14001180f  cmp     rcx, rsi
0x140011812  jbe     short loc_140011886
0x140011814  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140011819  int     3; Trap to Debugger
0x14001181a  neg     rcx
0x14001181d  cmp     rcx, rsi
0x140011820  jbe     short loc_14001187B
0x140011822  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140011827  int     3; Trap to Debugger
0x140011828  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001182d  int     3; Trap to Debugger
0x14001182e  lea     rax, sfac_ComputeIndex0
0x140011835  mov     [rdi+0E0h], rax
0x14001183c  jmp     loc_140011746
0x140011841  mov     rsi, r15
0x140011844  jmp     loc_1400114FF
0x140011849  mov     rcx, r14
0x14001184c  mov     rax, [rdi+10h]
0x140011850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011855  jmp     loc_14001174F
0x14001185a  mov     rax, rsi
0x14001185d  sub     rax, rcx
0x140011860  jmp     loc_1400115A2
0x140011865  mov     r15, rsi
0x140011868  sub     r15, rcx
0x14001186b  jmp     loc_14001160B
0x140011870  mov     rax, rsi
0x140011873  sub     rax, rcx
0x140011876  jmp     loc_14001165B
0x14001187b  mov     rbx, rsi
0x14001187e  sub     rbx, rcx
0x140011881  jmp     loc_1400116E0
0x140011886  sub     rsi, rcx
0x140011889  jmp     loc_140011710
0x14001188e  mov     rcx, r14
0x140011891  mov     rax, [rdi+10h]
0x140011895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001189a  jmp     loc_1400117E0
0x14001189f  mov     ebx, r15d
0x1400118a2  jmp     short loc_1400118E3
0x1400118a4  mov     [rdi+1Ch], edx
0x1400118a7  jmp     short loc_1400118DE
0x1400118a9  cmp     cx, 6
0x1400118ad  jz      short loc_1400118C1
0x1400118af  lea     rax, __scrt_initialize_winrt
0x1400118b6  mov     r12d, 140Ah
0x1400118bc  jmp     loc_140011835
0x1400118c1  lea     rax, sfac_ComputeIndex6
0x1400118c8  jmp     loc_140011835
0x1400118cd  lea     rax, sfac_ComputeIndex2
0x1400118d4  jmp     loc_140011835
0x1400118d9  xor     ebx, ebx
0x1400118db  mov     [rdi+1Ch], ebx
0x1400118de  mov     ebx, 1406h
0x1400118e3  lea     rax, __scrt_initialize_winrt
0x1400118ea  mov     [rdi+0E0h], rax
0x1400118f1  lea     rcx, [rbp+var_18]; this
0x1400118f5  call    ??1AutoReleaseSfntFrag@@QEAA@XZ; AutoReleaseSfntFrag::~AutoReleaseSfntFrag(void)
0x1400118fa  mov     eax, ebx
0x1400118fc  jmp     loc_140011752
```
