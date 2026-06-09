# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::InitializeBoutique(ushort const *,Microsoft::VisualStudio::PkgDef::PKGDEFMANAGEMENT_FLAGS,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void *)

- ea: `0x140046030`
- end: `0x1400462c9`
- name: `?InitializeBoutique@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@UEAAJPEBGW4PKGDEFMANAGEMENT_FLAGS@234@000000PEAX@Z`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400410d0`

## callees

- `0x140002f00`
- `0x140003160`
- `0x140004950`
- `0x14001d17c`
- `0x14002a644`
- `0x140046030`
- `0x1400464b0`
- `0x140046514`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x1400461bc`
- `SHLWAPI!PathFileExistsW` at `0x1400461bc`
- `SHLWAPI!PathIsDirectoryW` at `0x1400461da`
- `SHLWAPI!PathIsDirectoryW` at `0x1400461da`

## string_xrefs

- `0x1400461d1`: `The path specified for application root folder does not exist`
- `0x1400461ec`: `The path specified for application root folder is a file`
- `0x1400461fa`: `Invalid path specified for application root folder`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::InitializeBoutique(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  LPCWSTR *v21; // rbx
  _QWORD *v22; // rdx
  const unsigned __int16 *v23; // r8
  int v24; // edx
  const unsigned __int16 *v25; // rcx
  _QWORD *v26; // rdx
  __int64 result; // rax
  char v28; // [rsp+30h] [rbp-78h]
  __int64 v29; // [rsp+80h] [rbp-28h] BYREF
  __int64 v30; // [rsp+88h] [rbp-20h] BYREF

  if ( (a3 & 0x30) == 0 )
  {
    if ( a2 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(a2 + 2 * v14) );
      if ( v14 )
      {
        if ( a5 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(a5 + 2 * v15) );
          if ( v15 )
          {
            v16 = a1 + 120;
            v17 = -1;
            do
              ++v17;
            while ( *(_WORD *)(a2 + 2 * v17) );
            ATL::CSimpleStringT<unsigned short,0>::SetString(v16, a2);
            v18 = -1;
            do
              ++v18;
            while ( *(_WORD *)(a5 + 2 * v18) );
            ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 128, a5);
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)(a2 + 2 * v19) );
            ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 136, a2);
            if ( a7 )
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)(a7 + 2 * v20) );
              ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 112, a7);
            }
            *(_DWORD *)(a1 + 68) = 0;
            if ( !a6 )
              goto LABEL_32;
            v29 = 0;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v29,
              a6);
            if ( (int)GetCanonicalName(&v29) < 0 )
            {
              v23 = a6;
              v24 = 0;
              v25 = L"Invalid path specified for application root folder";
            }
            else
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v30,
                v29);
              v21 = (LPCWSTR *)(a1 + 96);
              ATL::CSimpleStringT<unsigned short,0>::operator=(a1 + 96, &v30);
              v22 = (_QWORD *)(v30 - 24);
              if ( _InterlockedDecrement((volatile signed __int32 *)(v30 - 24 + 16)) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
              }
              if ( PathFileExistsW(*v21) )
              {
                if ( PathIsDirectoryW(*v21) )
                  goto LABEL_30;
                v23 = *v21;
                v24 = -2147287037;
                v25 = L"The path specified for application root folder is a file";
              }
              else
              {
                v23 = *v21;
                v24 = -2147287037;
                v25 = L"The path specified for application root folder does not exist";
              }
            }
            CLogger::LogWarn(v25, v24, v23);
LABEL_30:
            v26 = (_QWORD *)(v29 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
            }
LABEL_32:
            v28 = 0;
            result = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::Initialize(
                       a1,
                       a4,
                       0,
                       a8,
                       a9,
                       a3,
                       v28,
                       0,
                       0,
                       a10,
                       0,
                       0,
                       0,
                       0,
                       0);
            _mm_lfence();
            return result;
          }
        }
      }
    }
  }
  CLogger::LogError(L"Unsupported flag or missing argument for Boutique PkgDefManagement", -2147024809, 0);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140046030  mov     rax, rsp
0x140046033  mov     [rax+8], rbx
0x140046037  mov     [rax+10h], rbp
0x14004603b  mov     [rax+18h], rsi
0x14004603f  mov     [rax+20h], rdi
0x140046043  push    r12
0x140046045  push    r14
0x140046047  push    r15
0x140046049  sub     rsp, 90h
0x140046050  mov     r14, r9
0x140046053  mov     ebp, r8d
0x140046056  mov     rbx, rdx
0x140046059  mov     rsi, rcx
0x14004605c  test    r8b, 30h
0x140046060  jnz     loc_14004628F
0x140046066  xor     r15d, r15d
0x140046069  test    rdx, rdx
0x14004606c  jz      loc_14004628F
0x140046072  or      r12, 0FFFFFFFFFFFFFFFFh
0x140046076  mov     rax, r12
0x140046079  inc     rax
0x14004607c  cmp     [rdx+rax*2], r15w
0x140046081  jnz     short loc_140046079
0x140046083  test    rax, rax
0x140046086  jz      loc_14004628F
0x14004608c  mov     rdi, [rsp+0A8h+arg_20]
0x140046094  test    rdi, rdi
0x140046097  jz      loc_14004628F
0x14004609d  mov     rax, r12
0x1400460a0  inc     rax
0x1400460a3  cmp     [rdi+rax*2], r15w
0x1400460a8  jnz     short loc_1400460A0
0x1400460aa  test    rax, rax
0x1400460ad  jz      loc_14004628F
0x1400460b3  add     rcx, 78h ; 'x'
0x1400460b7  mov     r8, r12
0x1400460ba  inc     r8
0x1400460bd  cmp     [rdx+r8*2], r15w
0x1400460c2  jnz     short loc_1400460BA
0x1400460c4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400460c9  lea     rcx, [rsi+80h]
0x1400460d0  mov     r8, r12
0x1400460d3  inc     r8
0x1400460d6  cmp     [rdi+r8*2], r15w
0x1400460db  jnz     short loc_1400460D3
0x1400460dd  mov     rdx, rdi
0x1400460e0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400460e5  lea     rcx, [rsi+88h]
0x1400460ec  mov     r8, r12
0x1400460ef  inc     r8
0x1400460f2  cmp     [rbx+r8*2], r15w
0x1400460f7  jnz     short loc_1400460EF
0x1400460f9  mov     rdx, rbx
0x1400460fc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140046101  mov     rdx, [rsp+0A8h+arg_30]
0x140046109  test    rdx, rdx
0x14004610c  jz      short loc_140046124
0x14004610e  lea     rcx, [rsi+70h]
0x140046112  mov     r8, r12
0x140046115  inc     r8
0x140046118  cmp     [rdx+r8*2], r15w
0x14004611d  jnz     short loc_140046115
0x14004611f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140046124  mov     [rsi+44h], r15d
0x140046128  mov     rbx, [rsp+0A8h+arg_28]
0x140046130  test    rbx, rbx
0x140046133  jz      loc_14004622E
0x140046139  mov     [rsp+0A8h+var_28], r15
0x140046141  mov     rdx, rbx
0x140046144  lea     rcx, [rsp+0A8h+var_28]
0x14004614c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140046151  nop
0x140046152  lea     rcx, [rsp+0A8h+var_28]
0x14004615a  call    ?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14004615f  test    eax, eax
0x140046161  js      loc_1400461F5
0x140046167  mov     rdx, [rsp+0A8h+var_28]
0x14004616f  lea     rcx, [rsp+0A8h+var_20]
0x140046177  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004617c  nop
0x14004617d  lea     rbx, [rsi+60h]
0x140046181  lea     rdx, [rsp+0A8h+var_20]
0x140046189  mov     rcx, rbx
0x14004618c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140046191  nop
0x140046192  mov     rdx, [rsp+0A8h+var_20]
0x14004619a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004619e  mov     eax, r12d
0x1400461a1  lock xadd [rdx+10h], eax
0x1400461a6  add     eax, r12d
0x1400461a9  test    eax, eax
0x1400461ab  jg      short loc_1400461B9
0x1400461ad  lfence
0x1400461b0  mov     rcx, [rdx]
0x1400461b3  mov     rax, [rcx]
0x1400461b6  call    qword ptr [rax+8]
0x1400461b9  mov     rcx, [rbx]; pszPath
0x1400461bc  call    cs:__imp_PathFileExistsW
0x1400461c2  mov     rcx, [rbx]; pszPath
0x1400461c5  test    eax, eax
0x1400461c7  jnz     short loc_1400461DA
0x1400461c9  mov     r8, rcx
0x1400461cc  mov     edx, 80030003h
0x1400461d1  lea     rcx, aThePathSpecifi; "The path specified for application root"...
0x1400461d8  jmp     short loc_140046201
0x1400461da  call    cs:__imp_PathIsDirectoryW
0x1400461e0  test    eax, eax
0x1400461e2  jnz     short loc_140046207
0x1400461e4  mov     r8, [rbx]
0x1400461e7  mov     edx, 80030003h
0x1400461ec  lea     rcx, aThePathSpecifi_0; "The path specified for application root"...
0x1400461f3  jmp     short loc_140046201
0x1400461f5  mov     r8, rbx; unsigned __int16 *
0x1400461f8  xor     edx, edx; int
0x1400461fa  lea     rcx, aInvalidPathSpe; "Invalid path specified for application "...
0x140046201  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x140046206  nop
0x140046207  mov     rdx, [rsp+0A8h+var_28]
0x14004620f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140046213  mov     eax, r12d
0x140046216  lock xadd [rdx+10h], eax
0x14004621b  add     eax, r12d
0x14004621e  test    eax, eax
0x140046220  jg      short loc_14004622E
0x140046222  lfence
0x140046225  mov     rcx, [rdx]
0x140046228  mov     rax, [rcx]
0x14004622b  call    qword ptr [rax+8]
0x14004622e  mov     [rsp+0A8h+var_38], r15d
0x140046233  mov     [rsp+0A8h+var_40], r15
0x140046238  mov     [rsp+0A8h+var_48], r15d
0x14004623d  mov     [rsp+0A8h+var_50], r15
0x140046242  mov     [rsp+0A8h+var_58], r15
0x140046247  mov     rax, [rsp+0A8h+arg_48]
0x14004624f  mov     [rsp+0A8h+var_60], rax
0x140046254  mov     [rsp+0A8h+var_68], r15
0x140046259  mov     [rsp+0A8h+var_70], r15
0x14004625e  mov     [rsp+0A8h+var_78], r15b
0x140046263  mov     [rsp+0A8h+var_80], ebp
0x140046267  mov     rax, [rsp+0A8h+arg_40]
0x14004626f  mov     [rsp+0A8h+var_88], rax
0x140046274  mov     r9, [rsp+0A8h+arg_38]
0x14004627c  xor     r8d, r8d
0x14004627f  mov     rdx, r14
0x140046282  mov     rcx, rsi
0x140046285  call    ?Initialize@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJPEBG000W4PKGDEFMANAGEMENT_FLAGS@234@_N00PEAXPEAUHKEY__@@PEBU_GUID@@IPEBQEBGI@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,Microsoft::VisualStudio::PkgDef::PKGDEFMANAGEMENT_FLAGS,bool,ushort const *,ushort const *,void *,HKEY__ *,_GUID const *,uint,ushort const * const *,uint)
0x14004628a  lfence
0x14004628d  jmp     short loc_1400462A7
0x14004628f  xor     r8d, r8d; unsigned __int16 *
0x140046292  mov     ebx, 80070057h
0x140046297  mov     edx, ebx; int
0x140046299  lea     rcx, aUnsupportedFla; "Unsupported flag or missing argument fo"...
0x1400462a0  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x1400462a5  mov     eax, ebx
0x1400462a7  lea     r11, [rsp+0A8h+var_18]
0x1400462af  mov     rbx, [r11+20h]
0x1400462b3  mov     rbp, [r11+28h]
0x1400462b7  mov     rsi, [r11+30h]
0x1400462bb  mov     rdi, [r11+38h]
0x1400462bf  mov     rsp, r11
0x1400462c2  pop     r15
0x1400462c4  pop     r14
0x1400462c6  pop     r12
0x1400462c8  retn
```
