# ReadCredsFromCredVault(ushort *,ushort * *,ushort * *)

- ea: `0x180046470`
- end: `0x180046932`
- name: `?ReadCredsFromCredVault@@YAJPEAGPEAPEAG1@Z`
- size: `1218`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18004743c`

## callees

- `0x180001284`
- `0x180001290`
- `0x18000420c`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180046470`
- `0x18004bcb0`
- `0x18005f010`

## string_xrefs

- `0x1800464e4`: `[msdrm]+ReadCredsFromCredVault wszServer=%S\n`
- `0x1800468ef`: `[msdrm]-ReadCredsFromCredVault hr=%x\n`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall ReadCredsFromCredVault(unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // r15
  unsigned __int16 *v7; // r14
  __int64 v8; // r8
  __int64 v9; // r9
  signed int v10; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  _WORD *v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  signed __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  _WORD *v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  signed __int64 v25; // rsi
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rcx
  __int64 v30; // [rsp+50h] [rbp-C8h] BYREF
  void *v31; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD *v32; // [rsp+60h] [rbp-B8h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-B0h]
  unsigned __int16 *v34; // [rsp+70h] [rbp-A8h]
  __int128 v35; // [rsp+78h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+88h] [rbp-90h]
  __int128 v37; // [rsp+98h] [rbp-80h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-70h]
  __int128 v39; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v40; // [rsp+C8h] [rbp-50h]
  __int64 v41; // [rsp+D8h] [rbp-40h]

  v41 = -2;
  v31 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v32 = 0;
  v30 = 0;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  v34 = 0;
  _RTLTRACE("[msdrm]+ReadCredsFromCredVault wszServer=%S\n", a1);
  if ( !CheckForCredVaultAPI() )
  {
    v10 = -2147418113;
    goto LABEL_48;
  }
  if ( (unsigned __int8)DRMIsValidStringT<unsigned short>(a1, 0, v8, v9) && a2 && a3 )
  {
    v11 = g_pfnVaultOpenVault((struct _GUID *)qword_180084408, 0, &v31);
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    if ( v10 >= 0 )
    {
      LODWORD(v35) = 1;
      DWORD2(v35) = 7;
      *(_QWORD *)&v36 = a1;
      LODWORD(v37) = 2;
      DWORD2(v37) = 7;
      *(_QWORD *)&v38 = aDrmusernameide;
      LODWORD(v39) = 2;
      DWORD2(v39) = 7;
      *(_QWORD *)&v40 = aDrmpasswordide;
      v12 = ((__int64 (__fastcall *)(void *, __int64 *, __int128 *, __int128 *, _QWORD, _QWORD, _DWORD, _QWORD **))g_pfnVaultGetItem)(
              v31,
              qword_180084418,
              &v35,
              &v37,
              0,
              0,
              0,
              &v32);
      v10 = v12;
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      if ( v10 >= 0 )
      {
        v13 = ((__int64 (__fastcall *)(void *, __int64 *, __int128 *, __int128 *, _QWORD, _QWORD, _DWORD, __int64 *))g_pfnVaultGetItem)(
                v31,
                qword_180084418,
                &v35,
                &v39,
                0,
                0,
                0,
                &v30);
        v10 = v13;
        if ( v13 > 0 )
          v10 = (unsigned __int16)v13 | 0x80070000;
        if ( v10 >= 0 )
        {
          if ( v32 && (v14 = v32[5]) != 0 && v30 && *(_QWORD *)(v30 + 40) )
          {
            v15 = *(_WORD **)(v14 + 16);
            if ( v15 )
            {
              v16 = 0x7FFFFFFF;
              do
              {
                if ( !*v15 )
                  break;
                ++v15;
                --v16;
              }
              while ( v16 );
              v10 = v16 == 0 ? 0x80070057 : 0;
              v17 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
              if ( v16 )
              {
                v18 = v17 + 1;
                if ( v17 + 1 < v17 )
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v16);
                v19 = HIDWORD(v18);
                if ( v18 < 0 )
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v19);
                v20 = 2LL * (unsigned int)v18;
                v21 = v19 << 33;
                if ( v21 + v20 < v20 )
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v21);
                if ( !(v21 + v20) )
                  goto LABEL_31;
                v6 = (unsigned __int16 *)operator new[](saturated_mul(v18, 2u));
                v33 = v6;
                if ( !v6 )
                {
                  v10 = -2147024882;
                  goto LABEL_48;
                }
                v10 = StringCchCopyW(v6, v18, *(const unsigned __int16 **)(v32[5] + 16LL));
                if ( v10 >= 0 )
                {
LABEL_31:
                  v22 = *(_WORD **)(*(_QWORD *)(v30 + 40) + 16LL);
                  if ( v22 )
                  {
                    v23 = 0x7FFFFFFF;
                    do
                    {
                      if ( !*v22 )
                        break;
                      ++v22;
                      --v23;
                    }
                    while ( v23 );
                    v10 = v23 == 0 ? 0x80070057 : 0;
                    v24 = (0x7FFFFFFF - v23) & ((unsigned __int128)-(__int128)(unsigned __int64)v23 >> 64);
                    if ( v23 )
                    {
                      v25 = v24 + 1;
                      if ( v24 + 1 < v24 )
                        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v23);
                      v26 = HIDWORD(v25);
                      if ( v25 < 0 )
                        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v26);
                      v27 = 2LL * (unsigned int)v25;
                      v28 = v26 << 33;
                      if ( v28 + v27 < v27 )
                        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v28);
                      if ( !(v28 + v27) )
                        goto LABEL_43;
                      v7 = (unsigned __int16 *)operator new[](saturated_mul(v25, 2u));
                      v34 = v7;
                      if ( !v7 )
                      {
                        v10 = -2147024882;
                        goto LABEL_48;
                      }
                      v10 = StringCchCopyW(v7, v25, *(const unsigned __int16 **)(*(_QWORD *)(v30 + 40) + 16LL));
                      if ( v10 >= 0 )
                      {
LABEL_43:
                        *a2 = v6;
                        *a3 = v7;
                        v6 = 0;
                        v7 = 0;
                      }
                    }
                  }
                  else
                  {
                    v10 = -2147024809;
                  }
                }
              }
            }
            else
            {
              v10 = -2147024809;
            }
          }
          else
          {
            v10 = -2147023728;
          }
        }
      }
    }
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_48:
  if ( v32 )
    g_pfnVaultFree(v32);
  if ( v30 )
    ((void (*)(void))g_pfnVaultFree)();
  if ( v31 )
    ((void (__fastcall *)(void **))g_pfnVaultCloseVault)(&v31);
  operator delete(v6);
  operator delete(v7);
  _RTLTRACE("[msdrm]-ReadCredsFromCredVault hr=%x\n", v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180046470  mov     rax, rsp
0x180046473  mov     [rax+18h], r8
0x180046477  mov     [rax+10h], rdx
0x18004647b  push    rbx
0x18004647c  push    rsi
0x18004647d  push    rdi
0x18004647e  push    r12
0x180046480  push    r13
0x180046482  push    r14
0x180046484  push    r15
0x180046486  sub     rsp, 0E0h
0x18004648d  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x180046495  mov     rbx, r8
0x180046498  mov     rsi, rdx
0x18004649b  mov     r12, rcx
0x18004649e  xor     edi, edi
0x1800464a0  mov     [rsp+118h+var_C0], rdi
0x1800464a5  xorps   xmm0, xmm0
0x1800464a8  movups  [rsp+118h+var_A0], xmm0
0x1800464ad  movups  xmmword ptr [rax-90h], xmm0
0x1800464b4  xorps   xmm1, xmm1
0x1800464b7  movups  xmmword ptr [rax-80h], xmm1
0x1800464bb  movups  xmmword ptr [rax-70h], xmm1
0x1800464bf  movups  xmmword ptr [rax-60h], xmm0
0x1800464c3  movups  xmmword ptr [rax-50h], xmm0
0x1800464c7  mov     [rsp+118h+var_B8], rdi
0x1800464cc  mov     [rsp+118h+var_C8], rdi
0x1800464d1  mov     r15d, edi
0x1800464d4  mov     [rsp+118h+var_B0], rdi
0x1800464d9  mov     r14d, edi
0x1800464dc  mov     [rsp+118h+var_A8], rdi
0x1800464e1  mov     rdx, rcx
0x1800464e4  lea     rcx, aMsdrmReadcreds_0; "[msdrm]+ReadCredsFromCredVault wszServe"...
0x1800464eb  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800464f0  call    ?CheckForCredVaultAPI@@YA_NXZ; CheckForCredVaultAPI(void)
0x1800464f5  test    al, al
0x1800464f7  jnz     short loc_180046503
0x1800464f9  mov     ebx, 8000FFFFh
0x1800464fe  jmp     loc_180046899
0x180046503  xor     edx, edx
0x180046505  mov     rcx, r12
0x180046508  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18004650d  test    al, al
0x18004650f  jz      loc_180046894
0x180046515  test    rsi, rsi
0x180046518  jz      loc_180046894
0x18004651e  test    rbx, rbx
0x180046521  jz      loc_180046894
0x180046527  lea     r8, [rsp+118h+var_C0]
0x18004652c  xor     edx, edx
0x18004652e  lea     rcx, qword_180084408
0x180046535  mov     rax, cs:?g_pfnVaultOpenVault@@3P6AKPEAU_GUID@@KPEAPEAX@ZEA; ulong (*g_pfnVaultOpenVault)(_GUID *,ulong,void * *)
0x18004653c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046541  mov     ebx, eax
0x180046543  mov     esi, 80070000h
0x180046548  test    eax, eax
0x18004654a  jle     short loc_180046551
0x18004654c  movzx   ebx, ax
0x18004654f  or      ebx, esi
0x180046551  test    ebx, ebx
0x180046553  js      loc_180046899
0x180046559  mov     dword ptr [rsp+118h+var_A0], 1
0x180046561  mov     ecx, 7
0x180046566  mov     dword ptr [rsp+118h+var_A0+8], ecx
0x18004656d  mov     qword ptr [rsp+118h+var_90], r12
0x180046575  lea     r13d, [rcx-5]
0x180046579  mov     [rsp+118h+var_80], r13d
0x180046581  mov     [rsp+118h+var_78], ecx
0x180046588  lea     rax, aDrmusernameide; "DrmUserNameIdentity"
0x18004658f  mov     qword ptr [rsp+118h+var_70], rax
0x180046597  mov     [rsp+118h+var_60], r13d
0x18004659f  mov     [rsp+118h+var_58], ecx
0x1800465a6  lea     rax, aDrmpasswordide; "DrmPasswordIdentity"
0x1800465ad  mov     qword ptr [rsp+118h+var_50], rax
0x1800465b5  lea     rax, [rsp+118h+var_B8]
0x1800465ba  mov     [rsp+118h+var_E0], rax
0x1800465bf  mov     [rsp+118h+var_E8], edi
0x1800465c3  mov     [rsp+118h+var_F0], rdi
0x1800465c8  mov     [rsp+118h+var_F8], rdi
0x1800465cd  lea     r9, [rsp+118h+var_80]
0x1800465d5  lea     r8, [rsp+118h+var_A0]
0x1800465da  lea     rdx, qword_180084418
0x1800465e1  mov     rcx, [rsp+118h+var_C0]
0x1800465e6  mov     rax, cs:?g_pfnVaultGetItem@@3P6AKPEAXPEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@22PEAUHWND__@@KPEAPEAU_VAULT_ITEM@@@ZEA; ulong (*g_pfnVaultGetItem)(void *,_GUID *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,HWND__ *,ulong,_VAULT_ITEM * *)
0x1800465ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465f2  mov     ebx, eax
0x1800465f4  test    eax, eax
0x1800465f6  jle     short loc_1800465FD
0x1800465f8  movzx   ebx, ax
0x1800465fb  or      ebx, esi
0x1800465fd  test    ebx, ebx
0x1800465ff  js      loc_180046899
0x180046605  lea     rax, [rsp+118h+var_C8]
0x18004660a  mov     [rsp+118h+var_E0], rax
0x18004660f  mov     [rsp+118h+var_E8], edi
0x180046613  mov     [rsp+118h+var_F0], rdi
0x180046618  mov     [rsp+118h+var_F8], rdi
0x18004661d  lea     r9, [rsp+118h+var_60]
0x180046625  lea     r8, [rsp+118h+var_A0]
0x18004662a  lea     rdx, qword_180084418
0x180046631  mov     rcx, [rsp+118h+var_C0]
0x180046636  mov     rax, cs:?g_pfnVaultGetItem@@3P6AKPEAXPEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@22PEAUHWND__@@KPEAPEAU_VAULT_ITEM@@@ZEA; ulong (*g_pfnVaultGetItem)(void *,_GUID *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,HWND__ *,ulong,_VAULT_ITEM * *)
0x18004663d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046642  mov     ebx, eax
0x180046644  test    eax, eax
0x180046646  jle     short loc_18004664D
0x180046648  movzx   ebx, ax
0x18004664b  or      ebx, esi
0x18004664d  test    ebx, ebx
0x18004664f  js      loc_180046899
0x180046655  mov     rcx, [rsp+118h+var_B8]
0x18004665a  test    rcx, rcx
0x18004665d  jz      loc_18004688D
0x180046663  mov     rax, [rcx+28h]
0x180046667  test    rax, rax
0x18004666a  jz      loc_18004688D
0x180046670  mov     rcx, [rsp+118h+var_C8]
0x180046675  test    rcx, rcx
0x180046678  jz      loc_18004688D
0x18004667e  cmp     [rcx+28h], rdi
0x180046682  jz      loc_18004688D
0x180046688  mov     rax, [rax+10h]
0x18004668c  test    rax, rax
0x18004668f  jz      loc_180046873
0x180046695  mov     r12d, 7FFFFFFFh
0x18004669b  mov     edx, r12d
0x18004669e  cmp     [rax], di
0x1800466a1  jz      short loc_1800466AC
0x1800466a3  add     rax, r13
0x1800466a6  sub     rdx, 1
0x1800466aa  jnz     short loc_18004669E
0x1800466ac  mov     rax, rdx
0x1800466af  neg     rax
0x1800466b2  sbb     ebx, ebx
0x1800466b4  not     ebx
0x1800466b6  mov     esi, 80070057h
0x1800466bb  and     ebx, esi
0x1800466bd  mov     rax, rdx
0x1800466c0  mov     rcx, r12
0x1800466c3  sub     rcx, rdx
0x1800466c6  neg     rax
0x1800466c9  sbb     r8, r8
0x1800466cc  and     r8, rcx
0x1800466cf  test    rdx, rdx
0x1800466d2  jz      loc_180046878
0x1800466d8  lea     rbx, [r8+1]
0x1800466dc  cmp     rbx, r8
0x1800466df  jb      loc_180046910
0x1800466e5  mov     rcx, rbx
0x1800466e8  shr     rcx, 20h
0x1800466ec  mov     rax, rcx
0x1800466ef  shr     rax, 1Fh
0x1800466f3  test    eax, eax
0x1800466f5  jnz     loc_180046916
0x1800466fb  mov     eax, ebx
0x1800466fd  add     rax, rax
0x180046700  shl     rcx, 21h
0x180046704  lea     rdx, [rcx+rax]
0x180046708  cmp     rdx, rax
0x18004670b  jb      loc_18004691B
0x180046711  test    rdx, rdx
0x180046714  jz      short loc_180046769
0x180046716  mov     rax, r13
0x180046719  mul     rbx
0x18004671c  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180046723  cmovb   rax, r13
0x180046727  mov     rcx, rax; unsigned __int64
0x18004672a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004672f  mov     r15, rax
0x180046732  mov     [rsp+118h+var_B0], rax
0x180046737  test    rax, rax
0x18004673a  jnz     short loc_180046746
0x18004673c  mov     ebx, 8007000Eh
0x180046741  jmp     loc_180046899
0x180046746  mov     rax, [rsp+118h+var_B8]
0x18004674b  mov     r8, [rax+28h]
0x18004674f  mov     r8, [r8+10h]; unsigned __int16 *
0x180046753  mov     rdx, rbx; unsigned __int64
0x180046756  mov     rcx, r15; unsigned __int16 *
0x180046759  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004675e  mov     ebx, eax
0x180046760  test    eax, eax
0x180046762  jns     short loc_18004676D
0x180046764  jmp     loc_180046899
0x180046769  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004676d  mov     rax, [rsp+118h+var_C8]
0x180046772  mov     rcx, [rax+28h]
0x180046776  mov     rax, [rcx+10h]
0x18004677a  test    rax, rax
0x18004677d  jz      loc_18004685A
0x180046783  mov     rcx, r12
0x180046786  cmp     [rax], di
0x180046789  jz      short loc_180046795
0x18004678b  add     rax, 2
0x18004678f  sub     rcx, 1
0x180046793  jnz     short loc_180046786
0x180046795  mov     rax, rcx
0x180046798  neg     rax
0x18004679b  sbb     ebx, ebx
0x18004679d  not     ebx
0x18004679f  and     ebx, esi
0x1800467a1  mov     rax, rcx
0x1800467a4  sub     r12, rcx
0x1800467a7  neg     rax
0x1800467aa  sbb     rdx, rdx
0x1800467ad  and     rdx, r12
0x1800467b0  test    rcx, rcx
0x1800467b3  jz      loc_18004685C
0x1800467b9  lea     rsi, [rdx+1]
0x1800467bd  cmp     rsi, rdx
0x1800467c0  jb      loc_180046921
0x1800467c6  mov     rcx, rsi
0x1800467c9  shr     rcx, 20h
0x1800467cd  mov     rax, rcx
0x1800467d0  shr     rax, 1Fh
0x1800467d4  test    eax, eax
0x1800467d6  jnz     loc_180046926
0x1800467dc  mov     eax, esi
0x1800467de  add     rax, rax
0x1800467e1  shl     rcx, 21h
0x1800467e5  lea     rdx, [rcx+rax]
0x1800467e9  cmp     rdx, rax
0x1800467ec  jb      loc_18004692B
0x1800467f2  test    rdx, rdx
0x1800467f5  jz      short loc_18004683F
0x1800467f7  mov     eax, 2
0x1800467fc  mul     rsi
0x1800467ff  cmovb   rax, r13
0x180046803  mov     rcx, rax; unsigned __int64
0x180046806  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004680b  mov     r14, rax
0x18004680e  mov     [rsp+118h+var_A8], rax
0x180046813  test    rax, rax
0x180046816  jnz     short loc_18004681F
0x180046818  mov     ebx, 8007000Eh
0x18004681d  jmp     short loc_180046899
0x18004681f  mov     rax, [rsp+118h+var_C8]
0x180046824  mov     r8, [rax+28h]
0x180046828  mov     r8, [r8+10h]; unsigned __int16 *
0x18004682c  mov     rdx, rsi; unsigned __int64
0x18004682f  mov     rcx, r14; unsigned __int16 *
0x180046832  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046837  mov     ebx, eax
0x180046839  test    eax, eax
0x18004683b  jns     short loc_18004683F
0x18004683d  jmp     short loc_180046899
0x18004683f  mov     rax, [rsp+118h+arg_8]
0x180046847  mov     [rax], r15
0x18004684a  mov     rax, [rsp+118h+arg_10]
0x180046852  mov     [rax], r14
0x180046855  mov     r15, rdi
0x180046858  jmp     short loc_180046888
0x18004685a  mov     ebx, esi
0x18004685c  jmp     short loc_180046899
0x18004685e  xor     edi, edi
0x180046860  mov     ebx, [rsp+118h+arg_18]
0x180046867  mov     r15, [rsp+118h+var_B0]
0x18004686c  mov     r14, [rsp+118h+var_A8]
0x180046871  jmp     short loc_180046899
0x180046873  mov     ebx, 80070057h
0x180046878  jmp     short loc_180046899
0x18004687a  xor     edi, edi
0x18004687c  mov     ebx, [rsp+118h+arg_18]
0x180046883  mov     r15, [rsp+118h+var_B0]
0x180046888  mov     r14, rdi
0x18004688b  jmp     short loc_180046899
0x18004688d  mov     ebx, 80070490h
0x180046892  jmp     short loc_180046899
0x180046894  mov     ebx, 80070057h
0x180046899  mov     rcx, [rsp+118h+var_B8]
0x18004689e  test    rcx, rcx
0x1800468a1  jz      short loc_1800468AF
0x1800468a3  mov     rax, cs:?g_pfnVaultFree@@3P6AXPEAX@ZEA; void (*g_pfnVaultFree)(void *)
0x1800468aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468af  mov     rcx, [rsp+118h+var_C8]
0x1800468b4  test    rcx, rcx
0x1800468b7  jz      short loc_1800468C5
0x1800468b9  mov     rax, cs:?g_pfnVaultFree@@3P6AXPEAX@ZEA; void (*g_pfnVaultFree)(void *)
0x1800468c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468c5  cmp     [rsp+118h+var_C0], rdi
0x1800468ca  jz      short loc_1800468DD
0x1800468cc  lea     rcx, [rsp+118h+var_C0]
0x1800468d1  mov     rax, cs:?g_pfnVaultCloseVault@@3P6AKPEAPEAX@ZEA; ulong (*g_pfnVaultCloseVault)(void * *)
0x1800468d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468dd  mov     rcx, r15; Block
0x1800468e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800468e5  mov     rcx, r14; Block
0x1800468e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800468ed  mov     edx, ebx
0x1800468ef  lea     rcx, aMsdrmReadcreds; "[msdrm]-ReadCredsFromCredVault hr=%x\n"
0x1800468f6  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800468fb  mov     eax, ebx
0x1800468fd  add     rsp, 0E0h
0x180046904  pop     r15
0x180046906  pop     r14
0x180046908  pop     r13
0x18004690a  pop     r12
0x18004690c  pop     rdi
0x18004690d  pop     rsi
0x18004690e  pop     rbx
  ... truncated ...
```
