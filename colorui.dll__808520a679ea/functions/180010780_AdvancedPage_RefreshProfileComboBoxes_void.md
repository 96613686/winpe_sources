# AdvancedPage::RefreshProfileComboBoxes(void)

- ea: `0x180010780`
- end: `0x180010dc0`
- name: `?RefreshProfileComboBoxes@AdvancedPage@@AEAAJXZ`
- size: `1600`
- prototype: `__int64 __fastcall(AdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010388`

## callees

- `0x180001334`
- `0x180001340`
- `0x18000134c`
- `0x18000c5d0`
- `0x18000fb18`
- `0x180010780`
- `0x180011050`
- `0x180011318`
- `0x1800116f8`
- `0x18001772c`
- `0x1800178d4`
- `0x1800179f0`
- `0x180017f54`
- `0x180017fa8`
- `0x180017ff4`
- `0x180018040`
- `0x180018500`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010b01`
- `msvcrt!_wcsicmp` at `0x180010b01`
- `USER32!SendMessageW` at `0x180010abe`
- `USER32!SendMessageW` at `0x180010ae2`
- `USER32!SendMessageW` at `0x180010b1f`
- `USER32!SendMessageW` at `0x180010caf`
- `USER32!SendMessageW` at `0x180010d0b`
- `USER32!SendMessageW` at `0x180010abe`
- `USER32!SendMessageW` at `0x180010ae2`
- `USER32!SendMessageW` at `0x180010b1f`
- `USER32!SendMessageW` at `0x180010caf`
- `USER32!SendMessageW` at `0x180010d0b`
- `USER32!CharPrevW` at `0x180010a74`
- `USER32!CharPrevW` at `0x180010a74`
- `USER32!CharNextW` at `0x180010a8d`
- `USER32!CharNextW` at `0x180010a8d`
- `mscms!ColorCplGetDefaultProfileScope` at `0x180010cd8`
- `mscms!ColorCplGetDefaultProfileScope` at `0x180010cd8`

## pseudocode

```c
__int64 __fastcall AdvancedPage::RefreshProfileComboBoxes(AdvancedPage *this)
{
  unsigned __int64 v1; // r14
  unsigned __int64 v3; // rbx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  HDSA v7; // rbx
  int StringFromRC; // edi
  const wchar_t *v9; // r12
  struct _DSA *i; // r15
  __int64 v11; // r15
  int v12; // eax
  int v13; // eax
  char *v14; // rax
  void *v15; // rsi
  __int64 v16; // rdx
  _OWORD *v17; // rcx
  unsigned int *p_pitem; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  int DefaultProfile; // eax
  const WCHAR *v22; // rsi
  __int64 v23; // rax
  LPWSTR v24; // rax
  HWND *v25; // r15
  int j; // esi
  int v27; // eax
  LRESULT v28; // rax
  int v29; // eax
  enum COLORPROFILESUBTYPE v30; // r13d
  enum COLORPROFILETYPE v31; // r8d
  unsigned int v32; // r12d
  int v33; // eax
  int v34; // eax
  HWND *v35; // r15
  int v36; // esi
  int DefaultProfileScope; // eax
  int v38; // eax
  unsigned int v39; // esi
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  HDSA hdsa; // [rsp+38h] [rbp-C8h] BYREF
  HWND *v43; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM lParam; // [rsp+48h] [rbp-B8h]
  int v45; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpszStart; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v48; // [rsp+68h] [rbp-98h]
  AdvancedPage *v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+80h] [rbp-80h]
  COLORPROFILETYPE v51; // [rsp+88h] [rbp-78h]
  COLORPROFILESUBTYPE v52; // [rsp+8Ch] [rbp-74h]
  unsigned int v53[2]; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h]
  int v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A4h] [rbp-5Ch]
  __int64 v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  int v59; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  int v61; // [rsp+D0h] [rbp-30h]
  __int64 v62; // [rsp+D4h] [rbp-2Ch]
  __int64 v63; // [rsp+E0h] [rbp-20h]
  int v64; // [rsp+E8h] [rbp-18h]
  __int64 v65; // [rsp+ECh] [rbp-14h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  int v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+104h] [rbp+4h]
  unsigned int pitem; // [rsp+110h] [rbp+10h] BYREF
  __int64 v70; // [rsp+114h] [rbp+14h]
  __int16 v71; // [rsp+11Ch] [rbp+1Ch]
  __int16 v72; // [rsp+324h] [rbp+224h]
  __int64 v73; // [rsp+52Ch] [rbp+42Ch]
  int v74; // [rsp+540h] [rbp+440h] BYREF
  __int64 v75; // [rsp+544h] [rbp+444h]
  _WORD v76[520]; // [rsp+54Ch] [rbp+44Ch] BYREF
  __int64 v77; // [rsp+95Ch] [rbp+85Ch]

  v1 = 0;
  v49 = this;
  v45 = 0;
  hdsa = DSA_Create(1060, 10);
  pitem = 0;
  v70 = 4;
  v48 = &NCoreLibrary::TString::gszNullState;
  v3 = 0;
  v50 = *((_QWORD *)this + 5);
  v54 = *((_QWORD *)this + 6);
  v57 = *((_QWORD *)this + 8);
  v60 = *((_QWORD *)this + 9);
  v63 = *((_QWORD *)this + 10);
  v66 = *((_QWORD *)this + 11);
  v73 = 1;
  v71 = 0;
  v72 = 0;
  v47 = 1735554163;
  lpszStart = 0;
  v51 = CPT_DMP;
  v52 = CPST_RGB_WORKING_SPACE;
  v53[0] = 1934772034;
  v55 = 2;
  v56 = 4;
  v58 = 3;
  v59 = 0;
  v61 = 3;
  v62 = 1;
  v64 = 3;
  v65 = 3;
  v67 = 3;
  v68 = 2;
  do
    Combo<Device>::Clear((HWND *)*(&v50 + 3 * v3++));
  while ( v3 < 6 );
  v5 = ColorDataController::EnumerateProfiles(v4, (WCS_PROFILE_MANAGEMENT_SCOPE)*((_DWORD *)this + 8), 0, 0, 0, &hdsa);
  v7 = hdsa;
  StringFromRC = v5;
  if ( v5 >= 0 )
  {
    v9 = 0;
    hdsa = 0;
    for ( i = 0; (unsigned __int64)i < 6; hdsa = i )
    {
      v11 = 3LL * (_QWORD)i;
      v43 = (HWND *)*(&v50 + v11);
      if ( !v43 )
        goto LABEL_47;
      while ( 1 )
      {
        v12 = v7 ? *(_DWORD *)v7 : 0;
        if ( (int)v1 >= v12 )
          break;
        if ( !v7 )
          goto LABEL_71;
        if ( (int)v1 >= *(_DWORD *)v7 )
        {
          StringFromRC = -2147024809;
          goto LABEL_74;
        }
        if ( !DSA_GetItem(v7, v1, &pitem) )
          goto LABEL_71;
        v13 = *((_DWORD *)&v51 + 2 * v11);
        if ( v13 == 1 )
        {
          if ( pitem > 1 )
            goto LABEL_21;
        }
        else if ( pitem != v13 )
        {
          goto LABEL_21;
        }
        v14 = (char *)operator new(0x424u);
        v15 = v14;
        if ( !v14 )
        {
          StringFromRC = -2147024882;
          goto LABEL_74;
        }
        v16 = 8;
        *(_DWORD *)v14 = 0;
        *(_QWORD *)(v14 + 4) = 4;
        v17 = v14;
        *(_QWORD *)(v14 + 1052) = 1;
        *((_WORD *)v14 + 6) = 0;
        *((_WORD *)v14 + 266) = 0;
        p_pitem = &pitem;
        do
        {
          *v17 = *(_OWORD *)p_pitem;
          v17[1] = *((_OWORD *)p_pitem + 1);
          v17[2] = *((_OWORD *)p_pitem + 2);
          v17[3] = *((_OWORD *)p_pitem + 3);
          v17[4] = *((_OWORD *)p_pitem + 4);
          v17[5] = *((_OWORD *)p_pitem + 5);
          v17[6] = *((_OWORD *)p_pitem + 6);
          v19 = *((_OWORD *)p_pitem + 7);
          p_pitem += 32;
          v17[7] = v19;
          v17 += 8;
          --v16;
        }
        while ( v16 );
        v20 = *(_OWORD *)p_pitem;
        LODWORD(Block) = 0;
        *v17 = v20;
        v17[1] = *((_OWORD *)p_pitem + 1);
        *((_DWORD *)v17 + 8) = p_pitem[8];
        StringFromRC = Combo<unsigned long>::AddItem(
                         (HWND *)*(&v50 + v11),
                         (LPARAM)v15 + 12,
                         (LPARAM)v15,
                         (int *)&Block);
        if ( StringFromRC < 0 )
        {
          operator delete(v15);
          goto LABEL_74;
        }
LABEL_21:
        LODWORD(v1) = v1 + 1;
      }
      DefaultProfile = ColorDataController::GetDefaultProfile(
                         (ColorDataController *)v6,
                         *((enum WCS_PROFILE_MANAGEMENT_SCOPE *)this + 8),
                         *(&v51 + 2 * v11),
                         v53[2 * v11 - 1],
                         v53[2 * v11],
                         (unsigned __int16 **)&lpszStart);
      v1 = 0;
      StringFromRC = DefaultProfile;
      if ( DefaultProfile >= 0 )
      {
        v22 = lpszStart;
        if ( lpszStart )
        {
          v23 = -1;
          do
            ++v23;
          while ( lpszStart[v23] );
          if ( (_DWORD)v23 )
          {
            v24 = (LPWSTR)&lpszStart[(unsigned int)v23];
            while ( 1 )
            {
              v24 = CharPrevW(v22, v24);
              v6 = *v24;
              if ( (_WORD)v6 == 92 )
                break;
              if ( v22 >= v24 )
                goto LABEL_33;
            }
            v24 = CharNextW(v24);
            v6 = *v24;
LABEL_33:
            LOWORD(v6) = -(__int16)v6;
            v9 = (const wchar_t *)((unsigned __int64)v24 & -(__int64)((_WORD)v6 != 0));
          }
          else
          {
            v9 = 0;
          }
        }
        if ( !v9 )
          goto LABEL_47;
        v25 = v43;
        for ( j = 0; ; ++j )
        {
          v27 = SendMessageW(*v25, 0x146u, 0, 0);
          v6 = -1;
          if ( v27 == -1 )
            v27 = -1;
          if ( j >= v27 )
            goto LABEL_46;
          v28 = SendMessageW(*v25, 0x150u, j, 0);
          if ( v28 == -1 )
          {
            StringFromRC = -2147467259;
          }
          else
          {
            StringFromRC = 0;
            if ( !_wcsicmp((const wchar_t *)(v28 + 532), v9) )
            {
              v29 = SendMessageW(*v25, 0x14Eu, j, 0);
              v6 = -1;
              if ( j == -1 || v29 != -1 && j == v29 )
              {
LABEL_46:
                v1 = 0;
                goto LABEL_47;
              }
LABEL_71:
              StringFromRC = -2147467259;
              goto LABEL_74;
            }
          }
        }
      }
      v45 = DefaultProfile;
LABEL_47:
      i = (HDSA)((char *)hdsa + 1);
    }
    if ( *((_DWORD *)this + 8) == 1 )
    {
      StringFromRC = NCoreLibrary::TString::LoadStringFromRC(
                       (NCoreLibrary::TString *)&v47,
                       *((HINSTANCE *)this + 2),
                       0x7EBu);
      if ( StringFromRC >= 0 )
      {
        do
        {
          Block = 0;
          lParam = (LPARAM)&NCoreLibrary::TString::gszNullState;
          v30 = v53[6 * v1 - 1];
          v31 = *((_DWORD *)&v51 + 6 * v1);
          v32 = v53[6 * v1];
          LODWORD(v43) = 1735554163;
          LODWORD(hdsa) = v31;
          v33 = ColorDataController::GetDefaultProfile(
                  (ColorDataController *)&Block,
                  WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE,
                  v31,
                  v30,
                  v32,
                  (unsigned __int16 **)&Block);
          StringFromRC = v33;
          if ( v33 < 0 )
          {
            if ( v33 != -2147024894 )
              goto LABEL_73;
            v34 = NCoreLibrary::TString::LoadStringFromRC(
                    (NCoreLibrary::TString *)&v43,
                    *((HINSTANCE *)v49 + 2),
                    0x7ECu);
          }
          else
          {
            v74 = 0;
            v75 = 4;
            v77 = 1;
            v76[0] = 0;
            v76[260] = 0;
            StringFromRC = ColorDataController::FillProfile(0, (const unsigned __int16 *)Block, (struct Profile *)&v74);
            operator delete[](Block);
            if ( StringFromRC < 0 )
              goto LABEL_73;
            v34 = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v43, v48, v76);
          }
          StringFromRC = v34;
          if ( v34 < 0 )
          {
LABEL_73:
            NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v43);
            break;
          }
          v35 = (HWND *)*(&v50 + 3 * v1);
          v36 = SendMessageW(*v35, 0x143u, 0, lParam);
          if ( v36 == -1 )
          {
            NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v43);
            StringFromRC = -2147467259;
            break;
          }
          LODWORD(Block) = 0;
          DefaultProfileScope = ColorCplGetDefaultProfileScope((unsigned int)hdsa, (unsigned int)v30, v32, &Block);
          StringFromRC = DefaultProfileScope;
          if ( DefaultProfileScope < 0 )
          {
            if ( DefaultProfileScope != -2147024894 )
              goto LABEL_73;
          }
          else if ( (_DWORD)Block == 1 )
          {
            goto LABEL_68;
          }
          v38 = SendMessageW(*v35, 0x14Eu, v36, 0);
          if ( v38 == -1 || v36 != v38 )
          {
            NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v43);
            goto LABEL_71;
          }
          StringFromRC = 0;
LABEL_68:
          NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v43);
          ++v1;
        }
        while ( v1 < 6 );
      }
    }
  }
LABEL_74:
  operator delete[]((void *)lpszStart);
  v39 = v45;
  if ( v45 >= 0 )
    v39 = StringFromRC;
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v47);
  if ( v7 )
  {
    DSA_DeleteAllItems(v7);
    DSA_Destroy(v7);
  }
  return v39;
}

```

## disassembly

```asm
0x180010780  push    rbp
0x180010782  push    rbx
0x180010783  push    rsi
0x180010784  push    rdi
0x180010785  push    r12
0x180010787  push    r13
0x180010789  push    r14
0x18001078b  push    r15
0x18001078d  lea     rbp, [rsp-888h]
0x180010795  sub     rsp, 988h
0x18001079c  mov     rax, cs:__security_cookie
0x1800107a3  xor     rax, rsp
0x1800107a6  mov     [rbp+8C0h+var_50], rax
0x1800107ad  xor     r14d, r14d
0x1800107b0  mov     [rsp+9C0h+var_950], rcx
0x1800107b5  mov     r13, rcx
0x1800107b8  mov     [rsp+9C0h+var_970], r14d
0x1800107bd  mov     ecx, 424h; cbItem
0x1800107c2  lea     edx, [r14+0Ah]; cItemGrow
0x1800107c6  call    DSA_Create
0x1800107cb  mov     [rsp+9C0h+hdsa], rax
0x1800107d0  lea     edi, [r14+1]
0x1800107d4  lea     ecx, [rdi+2]
0x1800107d7  mov     [rbp+8C0h+pitem], r14d
0x1800107db  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800107e2  mov     [rbp+8C0h+var_8AC], 4
0x1800107ea  mov     [rsp+9C0h+var_958], rax
0x1800107ef  lea     edx, [rdi+1]
0x1800107f2  mov     rax, [r13+28h]
0x1800107f6  mov     ebx, r14d
0x1800107f9  mov     [rbp+8C0h+var_940], rax
0x1800107fd  mov     rax, [r13+30h]
0x180010801  mov     [rbp+8C0h+var_928], rax
0x180010805  mov     rax, [r13+40h]
0x180010809  mov     [rbp+8C0h+var_910], rax
0x18001080d  mov     rax, [r13+48h]
0x180010811  mov     [rbp+8C0h+var_8F8], rax
0x180010815  mov     rax, [r13+50h]
0x180010819  mov     [rbp+8C0h+var_8E0], rax
0x18001081d  mov     rax, [r13+58h]
0x180010821  mov     [rbp+8C0h+var_8C8], rax
0x180010825  mov     [rbp+8C0h+var_494], rdi
0x18001082c  mov     [rbp+8C0h+var_8A4], r14w
0x180010831  mov     [rbp+8C0h+var_69C], r14w
0x180010839  mov     [rsp+9C0h+var_960], 67727473h
0x180010841  mov     [rsp+9C0h+lpszStart], r14
0x180010846  mov     [rbp+8C0h+var_938], edi
0x180010849  mov     [rbp+8C0h+var_934], 5
0x180010850  mov     [rbp+8C0h+var_930], 73524742h
0x180010857  mov     [rbp+8C0h+var_920], edx
0x18001085a  mov     [rbp+8C0h+var_91C], 4
0x180010862  mov     [rbp+8C0h+var_908], rcx
0x180010866  mov     [rbp+8C0h+var_900], r14d
0x18001086a  mov     [rbp+8C0h+var_8F0], ecx
0x18001086d  mov     [rbp+8C0h+var_8EC], rdi
0x180010871  mov     [rbp+8C0h+var_8D8], ecx
0x180010874  mov     [rbp+8C0h+var_8D4], rcx
0x180010878  mov     [rbp+8C0h+var_8C0], ecx
0x18001087b  mov     [rbp+8C0h+var_8BC], rdx
0x18001087f  lea     rcx, [rbx+rbx*2]
0x180010883  mov     rcx, [rbp+rcx*8+8C0h+var_940]
0x180010888  call    ?Clear@?$Combo@UDevice@@@@QEAAXXZ; Combo<Device>::Clear(void)
0x18001088d  add     rbx, rdi
0x180010890  cmp     rbx, 6
0x180010894  jb      short loc_18001087F
0x180010896  mov     edx, [r13+20h]
0x18001089a  lea     rax, [rsp+9C0h+hdsa]
0x18001089f  mov     [rsp+9C0h+var_998], rax
0x1800108a4  xor     r9d, r9d
0x1800108a7  xor     r8d, r8d
0x1800108aa  mov     qword ptr [rsp+9C0h+var_9A0], r14
0x1800108af  call    ?EnumerateProfiles@ColorDataController@@AEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKPEAHPEAV?$Array@UProfile@@@@@Z; ColorDataController::EnumerateProfiles(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int *,Array<Profile> *)
0x1800108b4  mov     rbx, [rsp+9C0h+hdsa]
0x1800108b9  mov     edi, eax
0x1800108bb  test    eax, eax
0x1800108bd  js      loc_180010D69
0x1800108c3  mov     r12, r14
0x1800108c6  mov     [rsp+9C0h+hdsa], r14
0x1800108cb  mov     r15, r14
0x1800108ce  lea     r15, [r15+r15*2]
0x1800108d2  mov     rax, [rbp+r15*8+8C0h+var_940]
0x1800108d7  mov     [rsp+9C0h+var_980], rax
0x1800108dc  test    rax, rax
0x1800108df  jz      loc_180010B40
0x1800108e5  xor     edi, edi
0x1800108e7  test    rbx, rbx
0x1800108ea  jz      short loc_1800108F0
0x1800108ec  mov     eax, [rbx]
0x1800108ee  jmp     short loc_1800108F2
0x1800108f0  mov     eax, edi
0x1800108f2  cmp     r14d, eax
0x1800108f5  jge     loc_180010A14
0x1800108fb  test    rbx, rbx
0x1800108fe  jz      loc_180010D3F
0x180010904  cmp     r14d, [rbx]
0x180010907  jge     loc_180010C62
0x18001090d  lea     r8, [rbp+8C0h+pitem]; pitem
0x180010911  mov     edx, r14d; i
0x180010914  mov     rcx, rbx; hdsa
0x180010917  call    DSA_GetItem
0x18001091c  test    eax, eax
0x18001091e  jz      loc_180010D3F
0x180010924  mov     eax, [rbp+r15*8+8C0h+var_938]
0x180010929  cmp     eax, 1
0x18001092c  jnz     short loc_180010939
0x18001092e  cmp     [rbp+8C0h+pitem], eax
0x180010931  ja      loc_180010A0C
0x180010937  jmp     short loc_180010942
0x180010939  cmp     [rbp+8C0h+pitem], eax
0x18001093c  jnz     loc_180010A0C
0x180010942  mov     ecx, 424h; Size
0x180010947  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001094c  mov     rsi, rax
0x18001094f  test    rax, rax
0x180010952  jz      loc_180010C58
0x180010958  mov     edx, 8
0x18001095d  mov     [rax], edi
0x18001095f  mov     qword ptr [rax+4], 4
0x180010967  mov     rcx, rax
0x18001096a  mov     qword ptr [rax+41Ch], 1
0x180010975  mov     [rax+0Ch], di
0x180010979  mov     [rax+214h], di
0x180010980  lea     r8d, [rdx+78h]
0x180010984  lea     rax, [rbp+8C0h+pitem]
0x180010988  movups  xmm0, xmmword ptr [rax]
0x18001098b  movups  xmmword ptr [rcx], xmm0
0x18001098e  movups  xmm1, xmmword ptr [rax+10h]
0x180010992  movups  xmmword ptr [rcx+10h], xmm1
0x180010996  movups  xmm0, xmmword ptr [rax+20h]
0x18001099a  movups  xmmword ptr [rcx+20h], xmm0
0x18001099e  movups  xmm1, xmmword ptr [rax+30h]
0x1800109a2  movups  xmmword ptr [rcx+30h], xmm1
0x1800109a6  movups  xmm0, xmmword ptr [rax+40h]
0x1800109aa  movups  xmmword ptr [rcx+40h], xmm0
0x1800109ae  movups  xmm1, xmmword ptr [rax+50h]
0x1800109b2  movups  xmmword ptr [rcx+50h], xmm1
0x1800109b6  movups  xmm0, xmmword ptr [rax+60h]
0x1800109ba  movups  xmmword ptr [rcx+60h], xmm0
0x1800109be  movups  xmm1, xmmword ptr [rax+70h]
0x1800109c2  add     rax, r8
0x1800109c5  movups  xmmword ptr [rcx+70h], xmm1
0x1800109c9  add     rcx, r8
0x1800109cc  sub     rdx, 1
0x1800109d0  jnz     short loc_180010988
0x1800109d2  movups  xmm0, xmmword ptr [rax]
0x1800109d5  lea     rdx, [rsi+0Ch]
0x1800109d9  mov     dword ptr [rsp+9C0h+Block], edi
0x1800109dd  lea     r9, [rsp+9C0h+Block]
0x1800109e2  mov     r8, rsi
0x1800109e5  movups  xmmword ptr [rcx], xmm0
0x1800109e8  movups  xmm1, xmmword ptr [rax+10h]
0x1800109ec  movups  xmmword ptr [rcx+10h], xmm1
0x1800109f0  mov     eax, [rax+20h]
0x1800109f3  mov     [rcx+20h], eax
0x1800109f6  mov     rcx, [rbp+r15*8+8C0h+var_940]
0x1800109fb  call    ?AddItem@?$Combo@K@@QEAAJPEBGPEAKPEAH@Z; Combo<ulong>::AddItem(ushort const *,ulong *,int *)
0x180010a00  mov     edi, eax
0x180010a02  test    eax, eax
0x180010a04  js      loc_180010C4B
0x180010a0a  xor     edi, edi
0x180010a0c  inc     r14d
0x180010a0f  jmp     loc_1800108E7
0x180010a14  mov     r9d, [rbp+r15*8+8C0h+var_934]; enum COLORPROFILESUBTYPE
0x180010a19  lea     rax, [rsp+9C0h+lpszStart]
0x180010a1e  mov     r8d, [rbp+r15*8+8C0h+var_938]; enum COLORPROFILETYPE
0x180010a23  mov     edx, [r13+20h]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180010a27  mov     [rsp+9C0h+var_998], rax; unsigned __int16 **
0x180010a2c  mov     eax, [rbp+r15*8+8C0h+var_930]
0x180010a31  mov     [rsp+9C0h+var_9A0], eax; unsigned int
0x180010a35  call    ?GetDefaultProfile@ColorDataController@@QEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@W4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@KPEAPEAG@Z; ColorDataController::GetDefaultProfile(WCS_PROFILE_MANAGEMENT_SCOPE,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort * *)
0x180010a3a  xor     r14d, r14d
0x180010a3d  mov     edi, eax
0x180010a3f  test    eax, eax
0x180010a41  js      loc_180010C42
0x180010a47  mov     rsi, [rsp+9C0h+lpszStart]
0x180010a4c  test    rsi, rsi
0x180010a4f  jz      short loc_180010A9F
0x180010a51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010a55  inc     rax
0x180010a58  cmp     [rsi+rax*2], r14w
0x180010a5d  jnz     short loc_180010A55
0x180010a5f  test    eax, eax
0x180010a61  jnz     short loc_180010A68
0x180010a63  mov     r12, r14
0x180010a66  jmp     short loc_180010A9F
0x180010a68  mov     eax, eax
0x180010a6a  lea     rax, [rsi+rax*2]
0x180010a6e  mov     rdx, rax; lpszCurrent
0x180010a71  mov     rcx, rsi; lpszStart
0x180010a74  call    cs:__imp_CharPrevW
0x180010a7a  movzx   ecx, word ptr [rax]
0x180010a7d  cmp     cx, 5Ch ; '\'
0x180010a81  jz      short loc_180010A8A
0x180010a83  cmp     rsi, rax
0x180010a86  jb      short loc_180010A6E
0x180010a88  jmp     short loc_180010A96
0x180010a8a  mov     rcx, rax; lpsz
0x180010a8d  call    cs:__imp_CharNextW
0x180010a93  movzx   ecx, word ptr [rax]
0x180010a96  neg     cx
0x180010a99  sbb     r12, r12
0x180010a9c  and     r12, rax
0x180010a9f  test    r12, r12
0x180010aa2  jz      loc_180010B40
0x180010aa8  mov     r15, [rsp+9C0h+var_980]
0x180010aad  mov     esi, r14d
0x180010ab0  mov     rcx, [r15]; hWnd
0x180010ab3  xor     r9d, r9d; lParam
0x180010ab6  xor     r8d, r8d; wParam
0x180010ab9  mov     edx, 146h; Msg
0x180010abe  call    cs:__imp_SendMessageW
0x180010ac4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010ac8  cmp     eax, ecx
0x180010aca  cmovz   eax, ecx
0x180010acd  cmp     esi, eax
0x180010acf  jge     short loc_180010B3D
0x180010ad1  mov     rcx, [r15]; hWnd
0x180010ad4  xor     r9d, r9d; lParam
0x180010ad7  movsxd  r14, esi
0x180010ada  mov     edx, 150h; Msg
0x180010adf  mov     r8, r14; wParam
0x180010ae2  call    cs:__imp_SendMessageW
0x180010ae8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010aec  jnz     short loc_180010AF5
0x180010aee  mov     edi, 80004005h
0x180010af3  jmp     short loc_180010B0D
0x180010af5  lea     rcx, [rax+214h]; String1
0x180010afc  mov     rdx, r12; String2
0x180010aff  xor     edi, edi
0x180010b01  call    cs:__imp__wcsicmp
0x180010b07  xor     ecx, ecx
0x180010b09  test    eax, eax
0x180010b0b  jz      short loc_180010B11
0x180010b0d  inc     esi
0x180010b0f  jmp     short loc_180010AB0
0x180010b11  mov     rcx, [r15]; hWnd
0x180010b14  xor     r9d, r9d; lParam
0x180010b17  mov     r8, r14; wParam
0x180010b1a  mov     edx, 14Eh; Msg
0x180010b1f  call    cs:__imp_SendMessageW
0x180010b25  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010b29  cmp     esi, ecx
0x180010b2b  jz      short loc_180010B3D
0x180010b2d  cmp     eax, ecx
0x180010b2f  jz      loc_180010D3F
0x180010b35  cmp     esi, eax
0x180010b37  jnz     loc_180010D3F
0x180010b3d  xor     r14d, r14d
0x180010b40  mov     r15, [rsp+9C0h+hdsa]
0x180010b45  inc     r15
0x180010b48  mov     [rsp+9C0h+hdsa], r15
0x180010b4d  cmp     r15, 6
0x180010b51  jb      loc_1800108CE
0x180010b57  cmp     dword ptr [r13+20h], 1
0x180010b5c  jnz     loc_180010D69
0x180010b62  mov     rdx, [r13+10h]; HINSTANCE
0x180010b66  lea     rcx, [rsp+9C0h+var_960]; this
0x180010b6b  mov     r8d, 7EBh; unsigned int
0x180010b71  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180010b76  mov     edi, eax
0x180010b78  test    eax, eax
0x180010b7a  js      loc_180010D69
0x180010b80  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180010b87  mov     [rsp+9C0h+Block], 0
0x180010b90  lea     rsi, [r14+r14*2]
0x180010b94  mov     [rsp+9C0h+lParam], rax
0x180010b99  mov     eax, [rbp+rsi*8+8C0h+var_938]
0x180010b9d  lea     rcx, [rsp+9C0h+Block]; this
0x180010ba2  mov     r13d, [rbp+rsi*8+8C0h+var_934]
0x180010ba7  mov     r8d, eax; enum COLORPROFILETYPE
0x180010baa  mov     r12d, [rbp+rsi*8+8C0h+var_930]
0x180010baf  mov     r9d, r13d; enum COLORPROFILESUBTYPE
0x180010bb2  mov     [rsp+9C0h+var_998], rcx; unsigned __int16 **
0x180010bb7  xor     edx, edx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180010bb9  mov     dword ptr [rsp+9C0h+var_980], 67727473h
0x180010bc1  mov     dword ptr [rsp+9C0h+hdsa], eax
0x180010bc5  mov     [rsp+9C0h+var_9A0], r12d; unsigned int
0x180010bca  call    ?GetDefaultProfile@ColorDataController@@QEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@W4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@KPEAPEAG@Z; ColorDataController::GetDefaultProfile(WCS_PROFILE_MANAGEMENT_SCOPE,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort * *)
0x180010bcf  xor     ecx, ecx; this
0x180010bd1  mov     edi, eax
0x180010bd3  test    eax, eax
0x180010bd5  js      loc_180010C6C
0x180010bdb  mov     rdx, [rsp+9C0h+Block]; unsigned __int16 *
0x180010be0  lea     r8, [rbp+8C0h+var_480]; struct Profile *
0x180010be7  mov     [rbp+8C0h+var_480], ecx
0x180010bed  mov     [rbp+8C0h+var_47C], 4
0x180010bf8  mov     [rbp+8C0h+var_64], 1
0x180010c03  mov     [rbp+8C0h+var_474], cx
0x180010c0a  mov     [rbp+8C0h+var_26C], cx
0x180010c11  call    ?FillProfile@ColorDataController@@QEBAJPEBGPEAUProfile@@@Z; ColorDataController::FillProfile(ushort const *,Profile *)
0x180010c16  mov     rcx, [rsp+9C0h+Block]; Block
0x180010c1b  mov     edi, eax
0x180010c1d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180010c22  lea     rcx, [rsp+9C0h+var_980]; this
0x180010c27  test    edi, edi
0x180010c29  js      loc_180010D64
0x180010c2f  mov     rdx, [rsp+9C0h+var_958]; unsigned __int16 *
0x180010c34  lea     r8, [rbp+8C0h+var_474]
0x180010c3b  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180010c40  jmp     short loc_180010C90
  ... truncated ...
```
