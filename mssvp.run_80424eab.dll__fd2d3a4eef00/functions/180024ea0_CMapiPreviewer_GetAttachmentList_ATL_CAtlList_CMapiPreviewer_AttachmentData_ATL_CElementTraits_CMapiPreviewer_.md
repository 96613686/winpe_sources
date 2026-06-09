# CMapiPreviewer::GetAttachmentList(ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>> &)

- ea: `0x180024ea0`
- end: `0x180025338`
- name: `?GetAttachmentList@CMapiPreviewer@@AEAAJAEAV?$CAtlList@PEAUAttachmentData@CMapiPreviewer@@V?$CElementTraits@PEAUAttachmentData@CMapiPreviewer@@@ATL@@@ATL@@@Z`
- size: `1176`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800239c8`

## callees

- `0x1800031c0`
- `0x180003d70`
- `0x180004058`
- `0x180004850`
- `0x1800048c0`
- `0x180004d40`
- `0x180005210`
- `0x180006270`
- `0x180007110`
- `0x180011374`
- `0x180019084`
- `0x180022110`
- `0x180024544`
- `0x180024ea0`
- `0x180025e54`
- `0x180026300`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180025192`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180025192`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::GetAttachmentList(__int64 a1, __int64 *a2)
{
  int v4; // r15d
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int *v8; // rsi
  unsigned int v9; // r12d
  __int64 v10; // r15
  __int64 v11; // rax
  CMapiPreviewer *v12; // rcx
  unsigned int v13; // r8d
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, _QWORD, _QWORD, __int64); // rbx
  CMapiPreviewer *v16; // rcx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // r8
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rdx
  const wchar_t *ExtensionW; // rax
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rbx
  const struct _SPropValue *v26; // rax
  const struct _SPropValue *v27; // rdi
  unsigned int v28; // eax
  __int64 v29; // rcx
  CURRENCY *p_Value; // rsi
  int *v31; // rdi
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 *v34; // rcx
  unsigned int v35; // ecx
  __int64 v36; // r9
  __int64 v37; // rdx
  const struct _SPropValue **v39; // [rsp+20h] [rbp-E0h]
  __int64 v40; // [rsp+30h] [rbp-D0h] BYREF
  int v41; // [rsp+38h] [rbp-C8h]
  int v42; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  int v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  const struct _SPropValue *v46; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h]
  void **v49; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR pszPath; // [rsp+78h] [rbp-88h]
  __int64 v51; // [rsp+80h] [rbp-80h]
  __int16 v52; // [rsp+88h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v48 = a1;
  v42 = 0;
  v43 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 + 216) + 112LL))(
         *(_QWORD *)(a1 + 216),
         0x80000000LL,
         &v43);
  v41 = v4;
  if ( v4 == -2147221245 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(a1 + 216) + 112LL))(
           *(_QWORD *)(a1 + 216),
           0,
           &v43);
    v41 = v4;
  }
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v43 + 56LL))(v43, qword_1800458F0, 0);
    v41 = v4;
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v43 + 72LL))(v43, 0, &v42);
      v41 = v4;
    }
  }
  v5 = v42;
LABEL_7:
  if ( v5 )
  {
    v47 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int **))(*(_QWORD *)v43 + 152LL))(
           v43,
           10,
           0,
           &v47);
    v7 = v6;
    if ( v6 < 0 )
    {
      v36 = (unsigned int)v6;
      v37 = 2313;
    }
    else
    {
      v8 = v47;
      if ( *v47 )
      {
        v9 = 0;
        v10 = v48;
        while ( 1 )
        {
          v11 = *(_QWORD *)&v8[4 * v9 + 4];
          if ( *(_DWORD *)v11 != 237043715
            || *(_DWORD *)(v11 + 216) != 923074563
            || *(_DWORD *)(v11 + 264) == 2147352587 && *(_WORD *)(v11 + 272)
            || *(_DWORD *)(v11 + 288) == 2147418123 && *(_WORD *)(v11 + 296)
            || *(_DWORD *)(v11 + 240) == 924057603 && (*(_BYTE *)(v11 + 248) & 4) != 0
            || ((*(_DWORD *)(v11 + 224) - 1) & 0xFFFFFFFB) != 0 )
          {
            goto LABEL_48;
          }
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v40);
          pszPath = (LPCWSTR)&v52;
          v51 = 65;
          v52 = 0;
          v49 = &TLMString<64,64,32767>::`vftable';
          if ( !CMapiPreviewer::FGetFirstStringFromRgmval(
                  v12,
                  (const struct _SPropValue *)(*(_QWORD *)&v8[4 * v9 + 4] + 72LL),
                  v13,
                  (struct CLMString *)&v49) )
          {
            v45 = 0;
            v46 = 0;
            v44 = 0;
            v14 = *(_QWORD *)(v10 + 216);
            v15 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v14 + 120LL);
            Microsoft::WRL::ComPtr<IAttach>::InternalRelease(&v45);
            v39 = (const struct _SPropValue **)&v45;
            v15(v14, *(unsigned int *)(*(_QWORD *)&v8[4 * v9 + 4] + 8LL), 0, 8);
            if ( !v45
              || (v39 = &v46,
                  (*(void (__fastcall **)(__int64, __int64 *, _QWORD, int *))(*(_QWORD *)v45 + 40LL))(
                    v45,
                    qword_1800458F0,
                    0,
                    &v44),
                  !v46)
              || v44 != 13
              || !CMapiPreviewer::FGetFirstStringFromRgmval(v16, v46 + 3, v17, (struct CLMString *)&v49) )
            {
              Microsoft::WRL::ComPtr<IAttach>::InternalRelease(&v45);
              goto LABEL_47;
            }
            Microsoft::WRL::ComPtr<IAttach>::InternalRelease(&v45);
          }
          if ( HIDWORD(v51) )
          {
            v18 = *(_QWORD *)&v8[4 * v9 + 4];
            if ( *(_DWORD *)(v18 + 24) == 922943519 )
            {
              v19 = (unsigned int)ocslen(*(const wchar_t **)(v18 + 32));
              v21 = v20;
              goto LABEL_34;
            }
            if ( *(_DWORD *)(v18 + 48) == 922943518 )
            {
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(
                &v40,
                *(_QWORD *)(v18 + 56));
              goto LABEL_35;
            }
            ExtensionW = PathFindExtensionW(pszPath);
            v23 = ocslen(ExtensionW);
            ATL::CSimpleStringT<wchar_t,0>::SetString(&v40, v24, v23);
            v25 = v40;
            if ( !*(_DWORD *)(v40 - 16) )
            {
              v19 = 1;
              v21 = L".";
LABEL_34:
              ATL::CSimpleStringT<wchar_t,0>::SetString(&v40, v21, v19);
LABEL_35:
              v25 = v40;
            }
            v26 = (const struct _SPropValue *)operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
            v27 = v26;
            if ( v26 )
            {
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v26);
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v27->Value);
              v46 = v27;
              v28 = ocslen(pszPath);
              ATL::CSimpleStringT<wchar_t,0>::SetString(v27, v29, v28);
              p_Value = (CURRENCY *)&v27->Value;
              v31 = (int *)(v27->Value.cur.int64 - 24);
              if ( (int *)(v25 - 24) != v31 )
              {
                if ( v31[4] >= 0 && *(_QWORD *)(v25 - 24) == *(_QWORD *)v31 )
                {
                  v32 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
                  ATL::CStringData::Release((ATL::CStringData *)v31);
                  p_Value->int64 = v32 + 24;
                }
                else
                {
                  ATL::CSimpleStringT<wchar_t,0>::SetString(p_Value, v25, *(unsigned int *)(v25 - 16));
                }
              }
              v33 = ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::NewNode(
                      a2,
                      &v46,
                      a2[1]);
              v34 = (__int64 *)a2[1];
              if ( v34 )
                *v34 = v33;
              else
                *a2 = v33;
              a2[1] = v33;
            }
            else
            {
              v46 = 0;
            }
          }
LABEL_47:
          TLMString<64,64,32767>::~TLMString<64,64,32767>(&v49);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v40);
          v8 = v47;
LABEL_48:
          ++v9;
          v35 = *v8;
          if ( v9 >= *v8 )
          {
            v4 = v41;
            v5 = v42 - v35;
            v42 -= v35;
            goto LABEL_7;
          }
        }
      }
      v7 = -2147216895;
      v36 = 2147750401LL;
      v37 = 2314;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssvp\\mapishellfolder\\mapipreviewer.cpp",
      (const char *)v36,
      (int)v39);
  }
  else
  {
    v7 = v4;
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v43);
  return v7;
}

```

## disassembly

```asm
0x180024ea0  mov     [rsp-8+arg_10], rbx
0x180024ea5  push    rbp
0x180024ea6  push    rsi
0x180024ea7  push    rdi
0x180024ea8  push    r12
0x180024eaa  push    r13
0x180024eac  push    r14
0x180024eae  push    r15
0x180024eb0  lea     rbp, [rsp-20h]
0x180024eb5  sub     rsp, 120h
0x180024ebc  mov     rax, cs:__security_cookie
0x180024ec3  xor     rax, rsp
0x180024ec6  mov     [rbp+50h+var_40], rax
0x180024eca  mov     r13, rdx
0x180024ecd  mov     rbx, rcx
0x180024ed0  mov     [rsp+150h+var_E8], rcx
0x180024ed5  xor     edi, edi
0x180024ed7  mov     [rsp+150h+var_114], edi
0x180024edb  mov     [rsp+150h+var_110], rdi
0x180024ee0  mov     rcx, [rcx+0D8h]
0x180024ee7  mov     rax, [rcx]
0x180024eea  lea     r8, [rsp+150h+var_110]
0x180024eef  mov     edx, 80000000h
0x180024ef4  mov     rax, [rax+70h]
0x180024ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024efd  mov     r15d, eax
0x180024f00  mov     [rsp+150h+var_118], eax
0x180024f04  cmp     eax, 80040103h
0x180024f09  jnz     short loc_180024F2C
0x180024f0b  mov     rcx, [rbx+0D8h]
0x180024f12  mov     rax, [rcx]
0x180024f15  lea     r8, [rsp+150h+var_110]
0x180024f1a  xor     edx, edx
0x180024f1c  mov     rax, [rax+70h]
0x180024f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f25  mov     r15d, eax
0x180024f28  mov     [rsp+150h+var_118], eax
0x180024f2c  test    r15d, r15d
0x180024f2f  js      short loc_180024F76
0x180024f31  mov     rcx, [rsp+150h+var_110]
0x180024f36  mov     rax, [rcx]
0x180024f39  xor     r8d, r8d
0x180024f3c  lea     rdx, qword_1800458F0
0x180024f43  mov     rax, [rax+38h]
0x180024f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f4c  mov     r15d, eax
0x180024f4f  mov     [rsp+150h+var_118], eax
0x180024f53  test    eax, eax
0x180024f55  js      short loc_180024F76
0x180024f57  mov     rcx, [rsp+150h+var_110]
0x180024f5c  mov     rax, [rcx]
0x180024f5f  lea     r8, [rsp+150h+var_114]
0x180024f64  xor     edx, edx
0x180024f66  mov     rax, [rax+48h]
0x180024f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f6f  mov     r15d, eax
0x180024f72  mov     [rsp+150h+var_118], eax
0x180024f76  mov     eax, [rsp+150h+var_114]
0x180024f7a  test    eax, eax
0x180024f7c  jz      loc_180025302
0x180024f82  mov     [rsp+150h+var_F0], rdi
0x180024f87  mov     rcx, [rsp+150h+var_110]
0x180024f8c  mov     rax, [rcx]
0x180024f8f  lea     r9, [rsp+150h+var_F0]
0x180024f94  xor     r8d, r8d
0x180024f97  lea     edx, [r8+0Ah]
0x180024f9b  mov     rax, [rax+98h]
0x180024fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fa7  mov     ebx, eax
0x180024fa9  test    eax, eax
0x180024fab  js      loc_1800252F8
0x180024fb1  mov     rsi, [rsp+150h+var_F0]
0x180024fb6  mov     ecx, [rsi]
0x180024fb8  test    ecx, ecx
0x180024fba  jz      loc_1800252D9
0x180024fc0  mov     r12d, edi
0x180024fc3  mov     r15, [rsp+150h+var_E8]
0x180024fc8  mov     r14d, r12d
0x180024fcb  inc     r14
0x180024fce  add     r14, r14
0x180024fd1  mov     rax, [rsi+r14*8]
0x180024fd5  cmp     dword ptr [rax], 0E210003h
0x180024fdb  jnz     loc_1800252B7
0x180024fe1  cmp     dword ptr [rax+0D8h], 37050003h
0x180024feb  jnz     loc_1800252B7
0x180024ff1  cmp     dword ptr [rax+108h], 7FFE000Bh
0x180024ffb  jnz     short loc_18002500A
0x180024ffd  cmp     [rax+110h], di
0x180025004  jnz     loc_1800252B7
0x18002500a  cmp     dword ptr [rax+120h], 7FFF000Bh
0x180025014  jnz     short loc_180025023
0x180025016  cmp     [rax+128h], di
0x18002501d  jnz     loc_1800252B7
0x180025023  cmp     dword ptr [rax+0F0h], 37140003h
0x18002502d  jnz     short loc_18002503C
0x18002502f  test    byte ptr [rax+0F8h], 4
0x180025036  jnz     loc_1800252B7
0x18002503c  mov     eax, [rax+0E0h]
0x180025042  dec     eax
0x180025044  test    eax, 0FFFFFFFBh
0x180025049  jnz     loc_1800252B7
0x18002504f  lea     rcx, [rsp+150h+var_120]
0x180025054  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180025059  nop
0x18002505a  lea     rax, [rbp+50h+var_C8]
0x18002505e  mov     [rsp+150h+pszPath], rax
0x180025063  mov     [rbp+50h+var_D0], 41h ; 'A'
0x18002506b  mov     [rbp+50h+var_C8], di
0x18002506f  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180025076  mov     [rsp+150h+var_E0], rax
0x18002507b  mov     rdx, [rsi+r14*8]
0x18002507f  add     rdx, 48h ; 'H'; struct _SPropValue *
0x180025083  lea     r9, [rsp+150h+var_E0]; struct CLMString *
0x180025088  call    ?FGetFirstStringFromRgmval@CMapiPreviewer@@AEAA_NPEBU_SPropValue@@KAEAVCLMString@@@Z; CMapiPreviewer::FGetFirstStringFromRgmval(_SPropValue const *,ulong,CLMString &)
0x18002508d  test    al, al
0x18002508f  jnz     loc_18002513E
0x180025095  mov     [rsp+150h+var_100], rdi
0x18002509a  mov     [rsp+150h+var_F8], rdi
0x18002509f  mov     [rsp+150h+var_108], edi
0x1800250a3  mov     rdi, [r15+0D8h]
0x1800250aa  mov     rax, [rdi]
0x1800250ad  mov     rbx, [rax+78h]
0x1800250b1  lea     rcx, [rsp+150h+var_100]
0x1800250b6  call    ?InternalRelease@?$ComPtr@UIAttach@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAttach>::InternalRelease(void)
0x1800250bb  mov     rdx, [rsi+r14*8]
0x1800250bf  lea     rax, [rsp+150h+var_100]
0x1800250c4  mov     [rsp+150h+var_130], rax
0x1800250c9  mov     r9d, 8
0x1800250cf  xor     r8d, r8d
0x1800250d2  mov     edx, [rdx+8]
0x1800250d5  mov     rcx, rdi
0x1800250d8  mov     rax, rbx
0x1800250db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250e0  mov     rcx, [rsp+150h+var_100]
0x1800250e5  xor     edi, edi
0x1800250e7  test    rcx, rcx
0x1800250ea  jz      short loc_180025165
0x1800250ec  mov     rax, [rcx]
0x1800250ef  lea     rdx, [rsp+150h+var_F8]
0x1800250f4  mov     [rsp+150h+var_130], rdx
0x1800250f9  lea     r9, [rsp+150h+var_108]
0x1800250fe  xor     r8d, r8d
0x180025101  lea     rdx, qword_1800458F0
0x180025108  mov     rax, [rax+28h]
0x18002510c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025111  mov     rdx, [rsp+150h+var_F8]
0x180025116  test    rdx, rdx
0x180025119  jz      short loc_180025165
0x18002511b  cmp     [rsp+150h+var_108], 0Dh
0x180025120  jnz     short loc_180025165
0x180025122  add     rdx, 48h ; 'H'; struct _SPropValue *
0x180025126  lea     r9, [rsp+150h+var_E0]; struct CLMString *
0x18002512b  call    ?FGetFirstStringFromRgmval@CMapiPreviewer@@AEAA_NPEBU_SPropValue@@KAEAVCLMString@@@Z; CMapiPreviewer::FGetFirstStringFromRgmval(_SPropValue const *,ulong,CLMString &)
0x180025130  test    al, al
0x180025132  jz      short loc_180025165
0x180025134  lea     rcx, [rsp+150h+var_100]
0x180025139  call    ?InternalRelease@?$ComPtr@UIAttach@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAttach>::InternalRelease(void)
0x18002513e  cmp     dword ptr [rbp+50h+var_D0+4], edi
0x180025141  jbe     loc_18002529D
0x180025147  mov     rdx, [rsi+r14*8]
0x18002514b  cmp     dword ptr [rdx+18h], 3703001Fh
0x180025152  jnz     short loc_180025174
0x180025154  mov     rcx, [rdx+20h]; wchar_t *
0x180025158  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18002515d  mov     r8d, eax
0x180025160  mov     rdx, rcx
0x180025163  jmp     short loc_1800251C7
0x180025165  lea     rcx, [rsp+150h+var_100]
0x18002516a  call    ?InternalRelease@?$ComPtr@UIAttach@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAttach>::InternalRelease(void)
0x18002516f  jmp     loc_18002529D
0x180025174  cmp     dword ptr [rdx+30h], 3703001Eh
0x18002517b  jnz     short loc_18002518D
0x18002517d  mov     rdx, [rdx+38h]
0x180025181  lea     rcx, [rsp+150h+var_120]
0x180025186  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(char const *)
0x18002518b  jmp     short loc_1800251D1
0x18002518d  mov     rcx, [rsp+150h+pszPath]; pszPath
0x180025192  call    cs:__imp_PathFindExtensionW
0x180025198  mov     rcx, rax; wchar_t *
0x18002519b  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x1800251a0  mov     r8d, eax
0x1800251a3  mov     rdx, rcx
0x1800251a6  lea     rcx, [rsp+150h+var_120]
0x1800251ab  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800251b0  mov     rbx, [rsp+150h+var_120]
0x1800251b5  cmp     [rbx-10h], edi
0x1800251b8  jnz     short loc_1800251D6
0x1800251ba  mov     r8d, 1
0x1800251c0  lea     rdx, asc_180044C04; "."
0x1800251c7  lea     rcx, [rsp+150h+var_120]
0x1800251cc  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800251d1  mov     rbx, [rsp+150h+var_120]
0x1800251d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800251dd  mov     ecx, 10h; unsigned __int64
0x1800251e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800251e7  mov     rdi, rax
0x1800251ea  test    rax, rax
0x1800251ed  jz      loc_180025296
0x1800251f3  mov     rcx, rax
0x1800251f6  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800251fb  lea     rcx, [rdi+8]
0x1800251ff  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180025204  mov     [rsp+150h+var_F8], rdi
0x180025209  mov     rcx, [rsp+150h+pszPath]; wchar_t *
0x18002520e  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x180025213  mov     r8d, eax
0x180025216  mov     rdx, rcx
0x180025219  mov     rcx, rdi
0x18002521c  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180025221  lea     rsi, [rdi+8]
0x180025225  lea     rcx, [rbx-18h]
0x180025229  mov     rdi, [rsi]
0x18002522c  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180025230  cmp     rcx, rdi
0x180025233  jz      short loc_18002526B
0x180025235  cmp     dword ptr [rdi+10h], 0
0x180025239  jl      short loc_18002525C
0x18002523b  mov     rax, [rdi]
0x18002523e  cmp     [rcx], rax
0x180025241  jnz     short loc_18002525C
0x180025243  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180025248  mov     rbx, rax
0x18002524b  mov     rcx, rdi; this
0x18002524e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180025253  lea     rax, [rbx+18h]
0x180025257  mov     [rsi], rax
0x18002525a  jmp     short loc_18002526B
0x18002525c  mov     r8d, [rbx-10h]
0x180025260  mov     rdx, rbx
0x180025263  mov     rcx, rsi
0x180025266  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002526b  mov     r8, [r13+8]
0x18002526f  lea     rdx, [rsp+150h+var_F8]
0x180025274  mov     rcx, r13
0x180025277  call    ?NewNode@?$CAtlList@PEAUAttachmentData@CMapiPreviewer@@V?$CElementTraits@PEAUAttachmentData@CMapiPreviewer@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAUAttachmentData@CMapiPreviewer@@PEAV312@1@Z; ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::NewNode(CMapiPreviewer::AttachmentData * const &,ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::CNode *,ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::CNode *)
0x18002527c  mov     rcx, [r13+8]
0x180025280  xor     edi, edi
0x180025282  test    rcx, rcx
0x180025285  jz      short loc_18002528C
0x180025287  mov     [rcx], rax
0x18002528a  jmp     short loc_180025290
0x18002528c  mov     [r13+0], rax
0x180025290  mov     [r13+8], rax
0x180025294  jmp     short loc_18002529D
0x180025296  xor     edi, edi
0x180025298  mov     [rsp+150h+var_F8], rdi
0x18002529d  lea     rcx, [rsp+150h+var_E0]
0x1800252a2  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800252a7  nop
0x1800252a8  lea     rcx, [rsp+150h+var_120]
0x1800252ad  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800252b2  mov     rsi, [rsp+150h+var_F0]
0x1800252b7  inc     r12d
0x1800252ba  mov     ecx, [rsi]
0x1800252bc  cmp     r12d, ecx
0x1800252bf  jb      loc_180024FC8
0x1800252c5  mov     r15d, [rsp+150h+var_118]
0x1800252ca  mov     eax, [rsp+150h+var_114]
0x1800252ce  sub     eax, ecx
0x1800252d0  mov     [rsp+150h+var_114], eax
0x1800252d4  jmp     loc_180024F7A
0x1800252d9  mov     ebx, 80041201h
0x1800252de  mov     r9d, ebx; char *
0x1800252e1  mov     edx, 90Ah; void *
0x1800252e6  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800252ed  mov     rcx, [rbp+58h]; this
0x1800252f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800252f6  jmp     short loc_180025305
0x1800252f8  mov     r9d, eax
0x1800252fb  mov     edx, 909h
0x180025300  jmp     short loc_1800252E6
0x180025302  mov     ebx, r15d
0x180025305  lea     rcx, [rsp+150h+var_110]
0x18002530a  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002530f  mov     eax, ebx
0x180025311  mov     rcx, [rbp+50h+var_40]
0x180025315  xor     rcx, rsp; StackCookie
0x180025318  call    __security_check_cookie
0x18002531d  mov     rbx, [rsp+150h+arg_10]
0x180025325  add     rsp, 120h
0x18002532c  pop     r15
0x18002532e  pop     r14
0x180025330  pop     r13
0x180025332  pop     r12
0x180025334  pop     rdi
0x180025335  pop     rsi
0x180025336  pop     rbp
0x180025337  retn
```
