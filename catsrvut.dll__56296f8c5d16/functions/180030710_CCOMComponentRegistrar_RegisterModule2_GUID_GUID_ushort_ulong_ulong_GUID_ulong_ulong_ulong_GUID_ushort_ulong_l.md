# CCOMComponentRegistrar::RegisterModule2(_GUID,_GUID,ushort * *,ulong,ulong,_GUID *,ulong,ulong * *,ulong *,_GUID * *,ushort * * *,ulong * *,long * *)

- ea: `0x180030710`
- end: `0x180030d26`
- name: `?RegisterModule2@CCOMComponentRegistrar@@UEAAJU_GUID@@0PEAPEAGKKPEAU2@KPEAPEAKPEAKPEAPEAU2@PEAPEAPEAG3PEAPEAJ@Z`
- size: `1558`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, struct _GUID *, struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, struct _GUID *, unsigned int, unsigned int **, unsigned int *, struct _GUID **, unsigned __int16 ***, unsigned int **, int **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007a4c`
- `0x18001c6a4`
- `0x18002d5a8`
- `0x18002d710`
- `0x18002d8c0`
- `0x18002dedc`
- `0x18002e32c`
- `0x18002fa5c`
- `0x180030710`
- `0x18003188c`
- `0x1800319dc`
- `0x180043b94`
- `0x180043c14`
- `0x18005583a`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800308cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030bfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800308cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030bfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030c83`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCOMComponentRegistrar::RegisterModule2(
        CCOMComponentRegistrar *this,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 **a4,
        unsigned int a5,
        unsigned int a6,
        struct _GUID *a7,
        unsigned int a8,
        unsigned int **a9,
        unsigned int *a10,
        struct _GUID **a11,
        unsigned __int16 ***a12,
        unsigned int **a13,
        int **a14)
{
  CCOMComponentRegistrar *v15; // rcx
  struct InstallList *v16; // r12
  unsigned int v17; // edi
  _DWORD *v18; // rbx
  unsigned int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // rcx
  struct _GUID *v22; // r13
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // eax
  struct _GUID *v26; // rax
  unsigned int v27; // edi
  unsigned int *v28; // rax
  unsigned int **v29; // rbx
  int *v30; // rax
  unsigned __int16 **v31; // rax
  unsigned __int16 ***v32; // r13
  __int16 v33; // r11
  __int64 v34; // rax
  SIZE_T v35; // rbx
  unsigned __int16 *v36; // rcx
  int v37; // ebx
  unsigned int v38; // r14d
  SIZE_T v39; // rdi
  unsigned int *v40; // rax
  unsigned int **v41; // r15
  unsigned int i; // r8d
  int v44; // [rsp+30h] [rbp-81h] BYREF
  int v45; // [rsp+34h] [rbp-7Dh] BYREF
  unsigned int v46; // [rsp+38h] [rbp-79h]
  unsigned int v47; // [rsp+3Ch] [rbp-75h]
  struct _GUID *v48[2]; // [rsp+40h] [rbp-71h] BYREF
  struct _GUID *v49; // [rsp+50h] [rbp-61h]
  struct _GUID **v50; // [rsp+58h] [rbp-59h]
  int **v51; // [rsp+60h] [rbp-51h]
  unsigned int **v52; // [rsp+68h] [rbp-49h]
  void *ppInterface; // [rsp+70h] [rbp-41h] BYREF
  int v54; // [rsp+78h] [rbp-39h]
  __int64 v55; // [rsp+80h] [rbp-31h]
  struct _GUID v56; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int16 ***v57; // [rsp+A0h] [rbp-11h]
  unsigned int **v58; // [rsp+A8h] [rbp-9h]

  *(_QWORD *)&v56.Data1 = a4;
  v48[0] = a3;
  v49 = a2;
  v46 = a5;
  v15 = (CCOMComponentRegistrar *)a9;
  v58 = a9;
  v50 = a11;
  v57 = a12;
  v52 = a13;
  v51 = a14;
  v16 = 0;
  ppInterface = 0;
  v54 = 0;
  v55 = 0;
  v45 = 1;
  v17 = a6;
  if ( (a6 & 0x1F) != 0 || !a5 || !a4 || !a9 || !a10 || !a11 || !a12 || !a13 || !a14 || a8 && !a7 )
  {
    CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
    return 2147942487LL;
  }
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  *a12 = 0;
  *a13 = 0;
  *a14 = 0;
  v18 = (_DWORD *)((char *)this - 8);
  *(struct _GUID *)((char *)this + 136) = *a3;
  if ( (a6 & 0x100) == 0 )
  {
    v44 = CImpersonate::ImpersonateClient(&ppInterface);
    if ( v44 )
      goto LABEL_45;
    a2 = v49;
  }
  v18[35] = (a6 >> 11) & 1;
  *((_DWORD *)this + 32) = 0;
  v47 = a6 & 0x20;
  if ( (a6 & 0x20) != 0 || (a6 & 0x8000) != 0 || (v44 = CCOMComponentRegistrar::CheckApplication(v15, a2)) == 0 )
  {
    if ( (*(unsigned int (__fastcall **)(char *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v18 + 40LL))(
           (char *)this - 8,
           *(_QWORD *)&v56.Data1,
           v46,
           a6) )
    {
LABEL_19:
      v44 = -2147467259;
      goto LABEL_45;
    }
    if ( a7 && a8 )
    {
      v16 = (struct InstallList *)CoTaskMemAlloc(saturated_mul(a8, 0x14u));
      if ( !v16 )
      {
        v44 = -2147024882;
        goto LABEL_45;
      }
      v19 = 0;
      v20 = 0;
      do
      {
        v21 = 5 * v20;
        *(struct _GUID *)((char *)v16 + 4 * v21) = a7[v20];
        *((_DWORD *)v16 + v21 + 4) = 0;
        ++v19;
        ++v20;
      }
      while ( v19 < a8 );
    }
    v22 = v49;
    v56 = *v49;
    if ( (*(unsigned int (__fastcall **)(char *, _QWORD, struct _GUID *, struct InstallList *, unsigned int))(*(_QWORD *)v18 + 48LL))(
           (char *)this - 8,
           a6,
           &v56,
           v16,
           a8)
      || (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v18 + 64LL))((char *)this - 8) )
    {
      goto LABEL_19;
    }
    v44 = CCOMComponentRegistrar::CheckDllTypes(
            (CCOMComponentRegistrar *)((char *)this - 8),
            v49,
            v48[0],
            (enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *)&v45);
    if ( !v44 )
    {
      *((_DWORD *)this + 42) = v45;
      *(struct _GUID *)v48 = *v22;
      v44 = (*(__int64 (__fastcall **)(char *, _QWORD, struct _GUID **))(*(_QWORD *)v18 + 56LL))(
              (char *)this - 8,
              a6,
              v48);
      if ( !v44 )
      {
        if ( (unsigned int)CCOMComponentRegistrar::CheckForErrors((CCOMComponentRegistrar *)((char *)this - 8), 0) )
          goto LABEL_19;
        v44 = CCOMComponentRegistrar::CheckCLSIDEqAPPID((CCOMComponentRegistrar *)((char *)this - 8));
        if ( !v44 )
        {
          if ( !v47 )
          {
            v45 = 0;
            v44 = CCOMComponentRegistrar::CheckRefCountRequired((CCOMComponentRegistrar *)((char *)this - 8), &v45);
            if ( v44 < 0 )
              goto LABEL_45;
            v23 = a6 | (v45 != 0 ? 0x10000 : 0);
            v44 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD))(*(_QWORD *)v18 + 72LL))((char *)this - 8, 1, v23);
            if ( v44 )
              goto LABEL_19;
            if ( (unsigned int)CCOMComponentRegistrar::CheckForErrors((CCOMComponentRegistrar *)((char *)this - 8), 1) )
              goto LABEL_19;
            v17 = v23 & 0xFFFEFFFF;
            if ( (v17 & 0x1000) == 0 )
            {
              if ( *((_DWORD *)this + 32) )
              {
                *(struct _GUID *)v48 = *v22;
                v44 = (*(__int64 (__fastcall **)(char *, _QWORD, struct _GUID **, struct InstallList *, unsigned int))(*(_QWORD *)v18 + 48LL))(
                        (char *)this - 8,
                        v17,
                        v48,
                        v16,
                        a8);
                if ( v44 )
                  goto LABEL_19;
              }
            }
          }
          if ( (v17 & 0x1020) != 0
            || (*(struct _GUID *)v48 = *v22,
                (v44 = (*(__int64 (__fastcall **)(char *, struct _GUID **, _QWORD))(*(_QWORD *)v18 + 80LL))(
                         (char *)this - 8,
                         v48,
                         v17)) == 0) )
          {
            if ( v16 )
            {
              v24 = CCOMComponentRegistrar::MarkComponentsNotFound(
                      (CCOMComponentRegistrar *)((char *)this - 8),
                      v16,
                      a8);
              if ( v24 )
                v24 = -2147467259;
              v44 = v24;
            }
          }
        }
      }
    }
  }
LABEL_45:
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v44);
  v25 = *((_DWORD *)this + 28);
  *a10 = v25;
  if ( !v25 )
  {
    *a10 = 0;
LABEL_60:
    v37 = v44;
    goto LABEL_61;
  }
  v26 = (struct _GUID *)CoTaskMemAlloc(16LL * v25);
  *v50 = v26;
  v27 = 0;
  if ( v26 )
  {
    v28 = (unsigned int *)CoTaskMemAlloc(4LL * *a10);
    v29 = v52;
    *v52 = v28;
    if ( v28 )
    {
      v30 = (int *)CoTaskMemAlloc(4LL * *a10);
      *v51 = v30;
      if ( v30 )
      {
        v31 = (unsigned __int16 **)CoTaskMemAlloc(8LL * *a10);
        v32 = v57;
        *v57 = v31;
        if ( v31 )
        {
          memset_0(v31, 0, 8LL * *a10);
          v33 = 0;
          while ( v27 < *a10 )
          {
            (*v50)[v27] = *(struct _GUID *)*(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)v27);
            (*v29)[v27] = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)v27) + 36LL);
            (*v51)[v27] = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)v27) + 72LL);
            v34 = -1;
            do
              ++v34;
            while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)v27) + 16LL) + 2 * v34) != v33 );
            v35 = 2 * v34 + 2;
            (*v32)[v27] = (unsigned __int16 *)CoTaskMemAlloc(v35);
            v36 = (*v32)[v27];
            if ( !v36 )
              goto LABEL_58;
            v37 = StringCbCopyW(
                    v36,
                    v35,
                    *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)v27) + 16LL));
            if ( v37 < 0 )
            {
              CoTaskMemFree((*v32)[v27]);
              (*v32)[v27] = 0;
              goto LABEL_61;
            }
            ++v27;
            v29 = v52;
          }
          goto LABEL_60;
        }
      }
    }
  }
LABEL_58:
  v37 = -2147024882;
LABEL_61:
  v38 = *((_DWORD *)this + 20);
  if ( v38 )
  {
    v39 = 4LL * v46;
    v40 = (unsigned int *)CoTaskMemAlloc(v39);
    v41 = v58;
    *v58 = v40;
    if ( v40 )
    {
      memset_0(v40, 0, v39);
      for ( i = 0; i < v38; ++i )
        (*v41)[i] = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * (int)i) + 12LL);
    }
    else
    {
      v37 = -2147024882;
    }
  }
  CArray<FileInfo1 *,FileInfo1 * const &>::SetSize((char *)this + 64, 0);
  CArray<CompInfo1 *,CompInfo1 * const &>::SetSize((char *)this + 96, 0);
  *((_DWORD *)this + 32) = 0;
  if ( v16 )
    CoTaskMemFree(v16);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x180030710  push    rbp
0x180030712  push    rbx
0x180030713  push    rsi
0x180030714  push    rdi
0x180030715  push    r12
0x180030717  push    r13
0x180030719  push    r14
0x18003071b  push    r15
0x18003071d  lea     rbp, [rsp-7]
0x180030722  sub     rsp, 0B8h
0x180030729  mov     qword ptr [rbp+3Fh+var_60], r9
0x18003072d  mov     [rbp+3Fh+var_B0], r8
0x180030731  mov     [rbp+3Fh+var_A0], rdx
0x180030735  mov     rsi, rcx
0x180030738  mov     r15d, [rbp+3Fh+arg_20]
0x18003073c  mov     [rbp+3Fh+var_B8], r15d
0x180030740  mov     rcx, [rbp+3Fh+arg_40]
0x180030747  mov     [rbp+3Fh+var_48], rcx
0x18003074b  mov     r14, [rbp+3Fh+arg_48]
0x180030752  mov     rbx, [rbp+3Fh+arg_50]
0x180030759  mov     [rbp+3Fh+var_98], rbx
0x18003075d  mov     rax, [rbp+3Fh+arg_58]
0x180030764  mov     [rbp+3Fh+var_50], rax
0x180030768  mov     r10, [rbp+3Fh+arg_60]
0x18003076f  mov     [rbp+3Fh+var_88], r10
0x180030773  mov     r11, [rbp+3Fh+arg_68]
0x18003077a  mov     [rbp+3Fh+var_90], r11
0x18003077e  xor     r12d, r12d
0x180030781  mov     [rbp+3Fh+ppInterface], r12
0x180030785  mov     [rbp+3Fh+var_78], r12d
0x180030789  mov     [rbp+3Fh+var_70], r12
0x18003078d  mov     [rbp+3Fh+var_BC], 1
0x180030794  mov     edi, [rbp+3Fh+arg_28]
0x180030797  test    dil, 1Fh
0x18003079b  jnz     loc_180030D04
0x1800307a1  test    r15d, r15d
0x1800307a4  jz      loc_180030D04
0x1800307aa  test    r9, r9
0x1800307ad  jz      loc_180030D04
0x1800307b3  test    rcx, rcx
0x1800307b6  jz      loc_180030D04
0x1800307bc  test    r14, r14
0x1800307bf  jz      loc_180030D04
0x1800307c5  test    rbx, rbx
0x1800307c8  jz      loc_180030D04
0x1800307ce  test    rax, rax
0x1800307d1  jz      loc_180030D04
0x1800307d7  test    r10, r10
0x1800307da  jz      loc_180030D04
0x1800307e0  test    r11, r11
0x1800307e3  jz      loc_180030D04
0x1800307e9  mov     r13, [rbp+3Fh+arg_30]
0x1800307ed  mov     r15d, [rbp+3Fh+arg_38]
0x1800307f4  test    r15d, r15d
0x1800307f7  jz      short loc_180030802
0x1800307f9  test    r13, r13
0x1800307fc  jz      loc_180030D04
0x180030802  xor     r9d, r9d
0x180030805  mov     [rcx], r9
0x180030808  mov     [r14], r9d
0x18003080b  mov     [rbx], r9
0x18003080e  mov     [rax], r9
0x180030811  mov     [r10], r9
0x180030814  mov     [r11], r9
0x180030817  lea     rbx, [rsi-8]
0x18003081b  movups  xmm0, xmmword ptr [r8]
0x18003081f  movdqu  xmmword ptr [rbx+90h], xmm0
0x180030827  bt      edi, 8
0x18003082b  jb      short loc_180030849
0x18003082d  lea     rcx, [rbp+3Fh+ppInterface]; ppInterface
0x180030831  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x180030836  mov     [rsp+0F0h+var_C0], eax
0x18003083a  xor     r9d, r9d
0x18003083d  test    eax, eax
0x18003083f  jnz     loc_180030ADD
0x180030845  mov     rdx, [rbp+3Fh+var_A0]; struct _GUID *
0x180030849  mov     eax, edi
0x18003084b  shr     eax, 0Bh
0x18003084e  and     eax, 1
0x180030851  mov     [rbx+8Ch], eax
0x180030857  mov     [rsi+80h], r9d
0x18003085e  mov     eax, edi
0x180030860  and     eax, 20h
0x180030863  mov     [rbp+3Fh+var_B4], eax
0x180030866  jnz     short loc_18003087F
0x180030868  bt      edi, 0Fh
0x18003086c  jb      short loc_18003087F
0x18003086e  call    ?CheckApplication@CCOMComponentRegistrar@@AEAAJAEBU_GUID@@@Z; CCOMComponentRegistrar::CheckApplication(_GUID const &)
0x180030873  mov     [rsp+0F0h+var_C0], eax
0x180030877  test    eax, eax
0x180030879  jnz     loc_180030ADD
0x18003087f  mov     rax, [rbx]
0x180030882  mov     r9d, edi
0x180030885  mov     r8d, [rbp+3Fh+var_B8]
0x180030889  mov     rdx, qword ptr [rbp+3Fh+var_60]
0x18003088d  mov     rcx, rbx
0x180030890  mov     rax, [rax+28h]
0x180030894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030899  test    eax, eax
0x18003089b  jz      short loc_1800308AB
0x18003089d  mov     ecx, 80004005h
0x1800308a2  mov     [rsp+0F0h+var_C0], ecx
0x1800308a6  jmp     loc_180030ADD
0x1800308ab  test    r13, r13
0x1800308ae  jz      short loc_180030915
0x1800308b0  test    r15d, r15d
0x1800308b3  jz      short loc_180030915
0x1800308b5  mov     eax, 14h
0x1800308ba  mul     r15
0x1800308bd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800308c4  cmovb   rax, rcx
0x1800308c8  mov     rcx, rax; cb
0x1800308cb  call    cs:__imp_CoTaskMemAlloc
0x1800308d1  mov     r12, rax
0x1800308d4  xor     r9d, r9d
0x1800308d7  test    rax, rax
0x1800308da  jnz     short loc_1800308E9
0x1800308dc  mov     [rsp+0F0h+var_C0], 8007000Eh
0x1800308e4  jmp     loc_180030ADD
0x1800308e9  mov     r8d, r9d
0x1800308ec  mov     rdx, r9
0x1800308ef  lea     rcx, [rdx+rdx*4]
0x1800308f3  mov     rax, rdx
0x1800308f6  add     rax, rax
0x1800308f9  movups  xmm0, xmmword ptr [r13+rax*8+0]
0x1800308ff  movdqu  xmmword ptr [r12+rcx*4], xmm0
0x180030905  mov     [r12+rcx*4+10h], r9d
0x18003090a  inc     r8d
0x18003090d  inc     rdx
0x180030910  cmp     r8d, r15d
0x180030913  jb      short loc_1800308EF
0x180030915  mov     r13, [rbp+3Fh+var_A0]
0x180030919  movups  xmm0, xmmword ptr [r13+0]
0x18003091e  movdqu  [rbp+3Fh+var_60], xmm0
0x180030923  mov     rax, [rbx]
0x180030926  mov     [rsp+0F0h+var_D0], r15d
0x18003092b  mov     r9, r12
0x18003092e  lea     r8, [rbp+3Fh+var_60]
0x180030932  mov     edx, edi
0x180030934  mov     rcx, rbx
0x180030937  mov     rax, [rax+30h]
0x18003093b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030940  test    eax, eax
0x180030942  jnz     loc_18003089D
0x180030948  mov     rax, [rbx]
0x18003094b  mov     rcx, rbx
0x18003094e  mov     rax, [rax+40h]
0x180030952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030957  test    eax, eax
0x180030959  jnz     loc_18003089D
0x18003095f  lea     r9, [rbp+3Fh+var_BC]; enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *
0x180030963  mov     r8, [rbp+3Fh+var_B0]; struct _GUID *
0x180030967  mov     rdx, r13; struct _GUID *
0x18003096a  mov     rcx, rbx; this
0x18003096d  call    ?CheckDllTypes@CCOMComponentRegistrar@@AEAAJAEBU_GUID@@0PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; CCOMComponentRegistrar::CheckDllTypes(_GUID const &,_GUID const &,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)
0x180030972  mov     [rsp+0F0h+var_C0], eax
0x180030976  test    eax, eax
0x180030978  jnz     loc_180030ADD
0x18003097e  mov     eax, [rbp+3Fh+var_BC]
0x180030981  mov     [rsi+0A8h], eax
0x180030987  movups  xmm0, xmmword ptr [r13+0]
0x18003098c  movdqu  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180030991  mov     rax, [rbx]
0x180030994  lea     r8, [rbp+3Fh+var_B0]
0x180030998  mov     edx, edi
0x18003099a  mov     rcx, rbx
0x18003099d  mov     rax, [rax+38h]
0x1800309a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309a6  mov     [rsp+0F0h+var_C0], eax
0x1800309aa  test    eax, eax
0x1800309ac  jnz     loc_180030ADD
0x1800309b2  xor     edx, edx; int
0x1800309b4  mov     rcx, rbx; this
0x1800309b7  call    ?CheckForErrors@CCOMComponentRegistrar@@AEAAHH@Z; CCOMComponentRegistrar::CheckForErrors(int)
0x1800309bc  test    eax, eax
0x1800309be  jnz     loc_18003089D
0x1800309c4  mov     rcx, rbx; this
0x1800309c7  call    ?CheckCLSIDEqAPPID@CCOMComponentRegistrar@@AEAAJXZ; CCOMComponentRegistrar::CheckCLSIDEqAPPID(void)
0x1800309cc  mov     [rsp+0F0h+var_C0], eax
0x1800309d0  xor     ecx, ecx
0x1800309d2  test    eax, eax
0x1800309d4  jnz     loc_180030ADD
0x1800309da  cmp     [rbp+3Fh+var_B4], ecx
0x1800309dd  jnz     loc_180030A8C
0x1800309e3  mov     [rbp+3Fh+var_BC], ecx
0x1800309e6  lea     rdx, [rbp+3Fh+var_BC]; int *
0x1800309ea  mov     rcx, rbx; this
0x1800309ed  call    ?CheckRefCountRequired@CCOMComponentRegistrar@@AEAAJPEAH@Z; CCOMComponentRegistrar::CheckRefCountRequired(int *)
0x1800309f2  mov     [rsp+0F0h+var_C0], eax
0x1800309f6  test    eax, eax
0x1800309f8  js      loc_180030ADD
0x1800309fe  mov     eax, [rbp+3Fh+var_BC]
0x180030a01  neg     eax
0x180030a03  sbb     ecx, ecx
0x180030a05  and     ecx, 10000h
0x180030a0b  or      ecx, edi
0x180030a0d  mov     edi, ecx
0x180030a0f  mov     rax, [rbx]
0x180030a12  mov     r8d, ecx
0x180030a15  mov     edx, 1
0x180030a1a  mov     rcx, rbx
0x180030a1d  mov     rax, [rax+48h]
0x180030a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a26  mov     [rsp+0F0h+var_C0], eax
0x180030a2a  test    eax, eax
0x180030a2c  jnz     loc_18003089D
0x180030a32  lea     edx, [rax+1]; int
0x180030a35  mov     rcx, rbx; this
0x180030a38  call    ?CheckForErrors@CCOMComponentRegistrar@@AEAAHH@Z; CCOMComponentRegistrar::CheckForErrors(int)
0x180030a3d  xor     ecx, ecx
0x180030a3f  test    eax, eax
0x180030a41  jnz     loc_18003089D
0x180030a47  btr     edi, 10h
0x180030a4b  bt      edi, 0Ch
0x180030a4f  jb      short loc_180030A8C
0x180030a51  cmp     [rsi+80h], ecx
0x180030a57  jz      short loc_180030A8C
0x180030a59  movups  xmm0, xmmword ptr [r13+0]
0x180030a5e  movdqu  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180030a63  mov     rax, [rbx]
0x180030a66  mov     [rsp+0F0h+var_D0], r15d
0x180030a6b  mov     r9, r12
0x180030a6e  lea     r8, [rbp+3Fh+var_B0]
0x180030a72  mov     edx, edi
0x180030a74  mov     rcx, rbx
0x180030a77  mov     rax, [rax+30h]
0x180030a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a80  mov     [rsp+0F0h+var_C0], eax
0x180030a84  test    eax, eax
0x180030a86  jnz     loc_18003089D
0x180030a8c  test    edi, 1020h
0x180030a92  jnz     short loc_180030ABC
0x180030a94  movups  xmm0, xmmword ptr [r13+0]
0x180030a99  movdqu  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180030a9e  mov     rax, [rbx]
0x180030aa1  mov     r8d, edi
0x180030aa4  lea     rdx, [rbp+3Fh+var_B0]
0x180030aa8  mov     rcx, rbx
0x180030aab  mov     rax, [rax+50h]
0x180030aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ab4  mov     [rsp+0F0h+var_C0], eax
0x180030ab8  test    eax, eax
0x180030aba  jnz     short loc_180030ADD
0x180030abc  test    r12, r12
0x180030abf  jz      short loc_180030ADD
0x180030ac1  mov     r8d, r15d; unsigned int
0x180030ac4  mov     rdx, r12; struct InstallList *
0x180030ac7  mov     rcx, rbx; this
0x180030aca  call    ?MarkComponentsNotFound@CCOMComponentRegistrar@@AEAAJPEAUInstallList@@K@Z; CCOMComponentRegistrar::MarkComponentsNotFound(InstallList *,ulong)
0x180030acf  mov     ecx, 80004005h
0x180030ad4  test    eax, eax
0x180030ad6  cmovnz  eax, ecx
0x180030ad9  mov     [rsp+0F0h+var_C0], eax
0x180030add  lea     rdx, [rsp+0F0h+var_C0]; int *
0x180030ae2  lea     rcx, [rbp+3Fh+ppInterface]; this
0x180030ae6  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x180030aeb  mov     eax, [rsi+70h]
0x180030aee  mov     [r14], eax
0x180030af1  xor     ecx, ecx
0x180030af3  test    eax, eax
0x180030af5  jz      loc_180030C66
0x180030afb  mov     ecx, eax
0x180030afd  shl     rcx, 4; cb
0x180030b01  call    cs:__imp_CoTaskMemAlloc
0x180030b07  mov     rcx, [rbp+3Fh+var_98]
0x180030b0b  mov     [rcx], rax
0x180030b0e  xor     edi, edi
0x180030b10  test    rax, rax
0x180030b13  jz      loc_180030C5F
0x180030b19  mov     ecx, [r14]
0x180030b1c  shl     rcx, 2; cb
0x180030b20  call    cs:__imp_CoTaskMemAlloc
0x180030b26  mov     rbx, [rbp+3Fh+var_88]
0x180030b2a  mov     [rbx], rax
0x180030b2d  test    rax, rax
0x180030b30  jz      loc_180030C5F
0x180030b36  mov     ecx, [r14]
0x180030b39  shl     rcx, 2; cb
0x180030b3d  call    cs:__imp_CoTaskMemAlloc
0x180030b43  mov     rcx, [rbp+3Fh+var_90]
0x180030b47  mov     [rcx], rax
0x180030b4a  test    rax, rax
0x180030b4d  jz      loc_180030C5F
0x180030b53  mov     ecx, [r14]
0x180030b56  shl     rcx, 3; cb
0x180030b5a  call    cs:__imp_CoTaskMemAlloc
0x180030b60  mov     r13, [rbp+3Fh+var_50]
0x180030b64  mov     [r13+0], rax
0x180030b68  test    rax, rax
0x180030b6b  jz      loc_180030C5F
0x180030b71  mov     r8d, [r14]
0x180030b74  shl     r8, 3; Size
0x180030b78  xor     edx, edx; Val
0x180030b7a  mov     rcx, rax; void *
0x180030b7d  call    memset_0
0x180030b82  xor     r11d, r11d
0x180030b85  cmp     edi, [r14]
0x180030b88  jnb     loc_180030C69
0x180030b8e  movsxd  rdx, edi
0x180030b91  mov     rax, [rsi+68h]
  ... truncated ...
```
