# CHNetCfgMgr::RefreshTargetComputerAddress(ushort *,ulong)

- ea: `0x180017000`
- end: `0x18001741d`
- name: `?RefreshTargetComputerAddress@CHNetCfgMgr@@UEAAJPEAGK@Z`
- size: `1053`
- prototype: `int(CHNetCfgMgr *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180017000`
- `0x180027e10`
- `0x180028078`
- `0x180028210`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800171a7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800171ff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800171a7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800171ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180017244`
- `OLEAUT32!__imp_SysFreeString` at `0x180017244`
- `OLEAUT32!__imp_VariantInit` at `0x1800170f6`
- `OLEAUT32!__imp_VariantInit` at `0x1800170f6`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::RefreshTargetComputerAddress(CHNetCfgMgr *this, unsigned __int16 *a2, LONG a3)
{
  PVOID *v6; // rcx
  int v8; // eax
  int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // edi
  unsigned __int16 *v20; // [rsp+40h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v24; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  bstrString = 0;
  v24 = 0;
  v20 = 0;
  v22 = 0;
  v25 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !*((_QWORD *)this + 9) )
  {
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_d(v6[2], 222, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_d(v6[2], 223, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
    }
    return 2147500035LL;
  }
  VariantInit(&pvarg);
  if ( a2 && a3 )
  {
    v8 = BuildQuotedEqualsString(&v24, L"TargetName", a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v11 = 225;
LABEL_22:
      v12 = (unsigned int)v8;
      goto LABEL_62;
    }
    if ( v8 )
      goto LABEL_63;
    v13 = BuildAndString(&v20, v24, L"NameActive != FALSE");
    v9 = v13;
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        226,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v13);
    }
    operator delete[](v24);
    if ( v9 )
      goto LABEL_63;
    v15 = BuildSelectQueryBstr(&bstrString, v14, L"HNet_ConnectionPortMapping2", v20);
    v9 = v15;
    if ( v15 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        227,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v15);
    }
    operator delete[](v20);
    if ( v9 )
      goto LABEL_63;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR, __int64, _QWORD, __int64 *))(**((_QWORD **)this + 9) + 160LL))(
           *((_QWORD *)this + 9),
           *((_QWORD *)this + 12),
           bstrString,
           48,
           0,
           &v22);
    SysFreeString(bstrString);
    while ( 1 )
    {
      do
      {
        if ( v9 )
          goto LABEL_63;
        LODWORD(v24) = 0;
        v25 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned __int16 **))(*(_QWORD *)v22 + 32LL))(
               v22,
               0xFFFFFFFFLL,
               1,
               &v25,
               &v24);
        v9 = v8;
        if ( v8 < 0 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = 228;
            goto LABEL_22;
          }
          goto LABEL_64;
        }
      }
      while ( (_DWORD)v24 != 1 );
      pvarg.lVal = a3;
      pvarg.vt = 3;
      v16 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v25 + 40LL))(
              v25,
              L"TargetIPAddress",
              0,
              &pvarg,
              0);
      v9 = v16;
      if ( v16 >= 0 )
      {
        if ( !v16 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 9) + 112LL))(
                  *((_QWORD *)this + 9),
                  v25,
                  1);
          v9 = v16;
          if ( v16 < 0 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v18 = 230;
              goto LABEL_50;
            }
          }
        }
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 229;
LABEL_50:
          WPP_SF_d(v17[2], v18, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v16);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  v9 = -2147024809;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_64;
  }
  v11 = 224;
  v12 = 2147942487LL;
LABEL_62:
  WPP_SF_d(v10[2], v11, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v12);
LABEL_63:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
  v19 = 0;
  if ( v9 != 1 )
    v19 = v9;
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 231, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v19);
  return v19;
}

```

## disassembly

```asm
0x180017000  mov     [rsp-28h+arg_8], rbx
0x180017005  push    rbp
0x180017006  push    rsi
0x180017007  push    rdi
0x180017008  push    r12
0x18001700a  push    r13
0x18001700c  mov     rbp, rsp
0x18001700f  sub     rsp, 70h
0x180017013  mov     esi, r8d
0x180017016  mov     rbx, rdx
0x180017019  mov     rdi, rcx
0x18001701c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017023  lea     r12, WPP_GLOBAL_Control
0x18001702a  lea     r13, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180017031  cmp     rcx, r12
0x180017034  jz      short loc_18001705A
0x180017036  test    byte ptr [rcx+1Ch], 8
0x18001703a  jz      short loc_18001705A
0x18001703c  cmp     byte ptr [rcx+19h], 6
0x180017040  jb      short loc_18001705A
0x180017042  mov     rcx, [rcx+10h]
0x180017046  mov     edx, 0DDh
0x18001704b  mov     r8, r13
0x18001704e  call    WPP_SF_
0x180017053  mov     rcx, cs:WPP_GLOBAL_Control
0x18001705a  xor     eax, eax
0x18001705c  mov     [rbp+bstrString], 0
0x180017064  xorps   xmm0, xmm0
0x180017067  mov     [rbp+arg_0], 0
0x18001706f  mov     [rbp+var_30], 0
0x180017077  mov     [rbp+var_20], 0
0x18001707f  mov     [rbp+arg_18], 0
0x180017087  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001708b  mov     qword ptr [rbp+pvarg+10h], rax
0x18001708f  cmp     [rdi+48h], rax
0x180017093  jnz     short loc_1800170F2
0x180017095  mov     ebx, 80004003h
0x18001709a  cmp     rcx, r12
0x18001709d  jz      short loc_1800170EB
0x18001709f  test    byte ptr [rcx+1Ch], 8
0x1800170a3  jz      short loc_1800170C6
0x1800170a5  cmp     byte ptr [rcx+19h], 2
0x1800170a9  jb      short loc_1800170C6
0x1800170ab  mov     rcx, [rcx+10h]
0x1800170af  mov     edx, 0DEh
0x1800170b4  mov     r9d, ebx
0x1800170b7  mov     r8, r13
0x1800170ba  call    WPP_SF_d
0x1800170bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170c6  cmp     rcx, r12
0x1800170c9  jz      short loc_1800170EB
0x1800170cb  test    byte ptr [rcx+1Ch], 8
0x1800170cf  jz      short loc_1800170EB
0x1800170d1  cmp     byte ptr [rcx+19h], 6
0x1800170d5  jb      short loc_1800170EB
0x1800170d7  mov     rcx, [rcx+10h]
0x1800170db  mov     edx, 0DFh
0x1800170e0  mov     r9d, ebx
0x1800170e3  mov     r8, r13
0x1800170e6  call    WPP_SF_d
0x1800170eb  mov     eax, ebx
0x1800170ed  jmp     loc_180017409
0x1800170f2  lea     rcx, [rbp+pvarg]; pvarg
0x1800170f6  call    cs:__imp_VariantInit
0x1800170fc  test    rbx, rbx
0x1800170ff  jz      loc_180017383
0x180017105  test    esi, esi
0x180017107  jz      loc_180017383
0x18001710d  mov     r8, rbx; unsigned __int16 *
0x180017110  lea     rdx, ?c_wszTargetName@@3QBGB; "TargetName"
0x180017117  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18001711b  call    ?BuildQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x180017120  mov     ebx, eax
0x180017122  test    eax, eax
0x180017124  jns     short loc_180017157
0x180017126  mov     rcx, cs:WPP_GLOBAL_Control
0x18001712d  cmp     rcx, r12
0x180017130  jz      loc_1800173BB
0x180017136  test    byte ptr [rcx+1Ch], 8
0x18001713a  jz      loc_1800173BB
0x180017140  cmp     byte ptr [rcx+19h], 2
0x180017144  jb      loc_1800173BB
0x18001714a  mov     edx, 0E1h
0x18001714f  mov     r9d, eax
0x180017152  jmp     loc_1800173A8
0x180017157  jnz     loc_1800173B4
0x18001715d  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x180017161  lea     r8, aNameactiveFals_0; "NameActive != FALSE"
0x180017168  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x18001716c  call    ?BuildAndString@@YAJPEAPEAGPEBG1@Z; BuildAndString(ushort * *,ushort const *,ushort const *)
0x180017171  mov     ebx, eax
0x180017173  test    eax, eax
0x180017175  jns     short loc_1800171A3
0x180017177  mov     rcx, cs:WPP_GLOBAL_Control
0x18001717e  cmp     rcx, r12
0x180017181  jz      short loc_1800171A3
0x180017183  test    byte ptr [rcx+1Ch], 8
0x180017187  jz      short loc_1800171A3
0x180017189  cmp     byte ptr [rcx+19h], 2
0x18001718d  jb      short loc_1800171A3
0x18001718f  mov     rcx, [rcx+10h]
0x180017193  mov     edx, 0E2h
0x180017198  mov     r9d, eax
0x18001719b  mov     r8, r13
0x18001719e  call    WPP_SF_d
0x1800171a3  mov     rcx, [rbp+arg_0]
0x1800171a7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800171ad  test    ebx, ebx
0x1800171af  jnz     loc_1800173B4
0x1800171b5  mov     r9, [rbp+var_30]; unsigned __int16 *
0x1800171b9  lea     r8, ?c_wszHnetConnectionPortMapping@@3QBGB; "HNet_ConnectionPortMapping2"
0x1800171c0  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x1800171c4  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x1800171c9  mov     ebx, eax
0x1800171cb  test    eax, eax
0x1800171cd  jns     short loc_1800171FB
0x1800171cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171d6  cmp     rcx, r12
0x1800171d9  jz      short loc_1800171FB
0x1800171db  test    byte ptr [rcx+1Ch], 8
0x1800171df  jz      short loc_1800171FB
0x1800171e1  cmp     byte ptr [rcx+19h], 2
0x1800171e5  jb      short loc_1800171FB
0x1800171e7  mov     rcx, [rcx+10h]
0x1800171eb  mov     edx, 0E3h
0x1800171f0  mov     r9d, eax
0x1800171f3  mov     r8, r13
0x1800171f6  call    WPP_SF_d
0x1800171fb  mov     rcx, [rbp+var_30]
0x1800171ff  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180017205  test    ebx, ebx
0x180017207  jnz     loc_1800173B4
0x18001720d  mov     rcx, [rdi+48h]
0x180017211  lea     rdx, [rbp+var_20]
0x180017215  mov     r8, [rbp+bstrString]
0x180017219  lea     r9d, [rbx+30h]
0x18001721d  mov     [rsp+70h+var_48], rdx
0x180017222  mov     rdx, [rdi+60h]
0x180017226  mov     rax, [rcx]
0x180017229  mov     [rsp+70h+var_50], 0
0x180017232  mov     rax, [rax+0A0h]
0x180017239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001723e  mov     rcx, [rbp+bstrString]; bstrString
0x180017242  mov     ebx, eax
0x180017244  call    cs:__imp_SysFreeString
0x18001724a  jmp     loc_180017357
0x18001724f  mov     rcx, [rbp+var_20]
0x180017253  lea     rdx, [rbp+arg_0]
0x180017257  mov     dword ptr [rbp+arg_0], 0
0x18001725e  lea     r9, [rbp+arg_18]
0x180017262  mov     [rbp+arg_18], 0
0x18001726a  mov     r8d, 1
0x180017270  mov     [rsp+70h+var_50], rdx
0x180017275  or      edx, 0FFFFFFFFh
0x180017278  mov     rax, [rcx]
0x18001727b  mov     rax, [rax+20h]
0x18001727f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017284  mov     ebx, eax
0x180017286  test    eax, eax
0x180017288  js      loc_180017361
0x18001728e  cmp     dword ptr [rbp+arg_0], 1
0x180017292  jnz     loc_180017357
0x180017298  mov     rcx, [rbp+arg_18]
0x18001729c  lea     r9, [rbp+pvarg]
0x1800172a0  mov     eax, 3
0x1800172a5  mov     dword ptr [rbp+pvarg+8], esi
0x1800172a8  mov     word ptr [rbp+pvarg], ax
0x1800172ac  lea     rdx, ?c_wszTargetIPAddress@@3QBGB; "TargetIPAddress"
0x1800172b3  xor     r8d, r8d
0x1800172b6  mov     dword ptr [rsp+70h+var_50], 0
0x1800172be  mov     rax, [rcx]
0x1800172c1  mov     rax, [rax+28h]
0x1800172c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ca  mov     ebx, eax
0x1800172cc  test    eax, eax
0x1800172ce  jns     short loc_1800172EF
0x1800172d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172d7  cmp     rcx, r12
0x1800172da  jz      short loc_180017347
0x1800172dc  test    byte ptr [rcx+1Ch], 8
0x1800172e0  jz      short loc_180017347
0x1800172e2  cmp     byte ptr [rcx+19h], 2
0x1800172e6  jb      short loc_180017347
0x1800172e8  mov     edx, 0E5h
0x1800172ed  jmp     short loc_180017338
0x1800172ef  jnz     short loc_180017347
0x1800172f1  mov     rcx, [rdi+48h]
0x1800172f5  xor     r9d, r9d
0x1800172f8  mov     rdx, [rbp+arg_18]
0x1800172fc  mov     [rsp+70h+var_50], 0
0x180017305  mov     rax, [rcx]
0x180017308  lea     r8d, [r9+1]
0x18001730c  mov     rax, [rax+70h]
0x180017310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017315  mov     ebx, eax
0x180017317  test    eax, eax
0x180017319  jns     short loc_180017347
0x18001731b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017322  cmp     rcx, r12
0x180017325  jz      short loc_180017347
0x180017327  test    byte ptr [rcx+1Ch], 8
0x18001732b  jz      short loc_180017347
0x18001732d  cmp     byte ptr [rcx+19h], 2
0x180017331  jb      short loc_180017347
0x180017333  mov     edx, 0E6h
0x180017338  mov     rcx, [rcx+10h]
0x18001733c  mov     r9d, eax
0x18001733f  mov     r8, r13
0x180017342  call    WPP_SF_d
0x180017347  mov     rcx, [rbp+arg_18]
0x18001734b  mov     rax, [rcx]
0x18001734e  mov     rax, [rax+10h]
0x180017352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017357  test    ebx, ebx
0x180017359  jz      loc_18001724F
0x18001735f  jmp     short loc_1800173B4
0x180017361  mov     rcx, cs:WPP_GLOBAL_Control
0x180017368  cmp     rcx, r12
0x18001736b  jz      short loc_1800173BB
0x18001736d  test    byte ptr [rcx+1Ch], 8
0x180017371  jz      short loc_1800173BB
0x180017373  cmp     byte ptr [rcx+19h], 2
0x180017377  jb      short loc_1800173BB
0x180017379  mov     edx, 0E4h
0x18001737e  jmp     loc_18001714F
0x180017383  mov     ebx, 80070057h
0x180017388  mov     rcx, cs:WPP_GLOBAL_Control
0x18001738f  cmp     rcx, r12
0x180017392  jz      short loc_1800173BB
0x180017394  test    byte ptr [rcx+1Ch], 8
0x180017398  jz      short loc_1800173BB
0x18001739a  cmp     byte ptr [rcx+19h], 2
0x18001739e  jb      short loc_1800173BB
0x1800173a0  mov     edx, 0E0h
0x1800173a5  mov     r9d, ebx
0x1800173a8  mov     rcx, [rcx+10h]
0x1800173ac  mov     r8, r13
0x1800173af  call    WPP_SF_d
0x1800173b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173bb  mov     rdx, [rbp+var_20]
0x1800173bf  xor     edi, edi
0x1800173c1  cmp     ebx, 1
0x1800173c4  cmovnz  edi, ebx
0x1800173c7  test    rdx, rdx
0x1800173ca  jz      short loc_1800173E2
0x1800173cc  mov     rax, [rdx]
0x1800173cf  mov     rcx, rdx
0x1800173d2  mov     rax, [rax+10h]
0x1800173d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173e2  cmp     rcx, r12
0x1800173e5  jz      short loc_180017407
0x1800173e7  test    byte ptr [rcx+1Ch], 8
0x1800173eb  jz      short loc_180017407
0x1800173ed  cmp     byte ptr [rcx+19h], 6
0x1800173f1  jb      short loc_180017407
0x1800173f3  mov     rcx, [rcx+10h]
0x1800173f7  mov     edx, 0E7h
0x1800173fc  mov     r9d, edi
0x1800173ff  mov     r8, r13
0x180017402  call    WPP_SF_d
0x180017407  mov     eax, edi
0x180017409  mov     rbx, [rsp+70h+arg_8]
0x180017411  add     rsp, 70h
0x180017415  pop     r13
0x180017417  pop     r12
0x180017419  pop     rdi
0x18001741a  pop     rsi
0x18001741b  pop     rbp
0x18001741c  retn
```
