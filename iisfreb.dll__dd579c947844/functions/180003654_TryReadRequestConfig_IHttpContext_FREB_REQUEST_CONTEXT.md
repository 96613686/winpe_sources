# TryReadRequestConfig(IHttpContext *,FREB_REQUEST_CONTEXT *)

- ea: `0x180003654`
- end: `0x180003a0a`
- name: `?TryReadRequestConfig@@YAJPEAVIHttpContext@@PEAVFREB_REQUEST_CONTEXT@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct FREB_REQUEST_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18000209c`

## callees

- `0x180001008`
- `0x180003654`
- `0x180004440`
- `0x180005b28`
- `0x18000ac52`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000389d`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000389d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039c7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039d1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039c7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039d1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039dc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036aa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036cf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036aa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036cf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036f4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003715`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003715`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003784`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800038f1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003784`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800038f1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000379c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000379c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800037bc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800037bc`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800037ea`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800037ea`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800037f6`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800037f6`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000380f`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000380f`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800038dc`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800038dc`

## pseudocode

```c
__int64 __fastcall TryReadRequestConfig(struct IHttpContext *a1, struct FREB_REQUEST_CONTEXT *a2)
{
  __int64 v4; // rax
  int v5; // ebx
  const unsigned __int16 *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  int v11; // ebx
  struct FREB_META_STORED_CONTEXT *v12; // rax
  struct FREB_META_STORED_CONTEXT *v13; // rdi
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeSectionException *v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+80h] [rbp-80h]
  _BYTE v22[32]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v23; // [rsp+A8h] [rbp-58h]
  _BYTE v24[32]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD *v25; // [rsp+E0h] [rbp-20h]
  _BYTE v26[56]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v27[256]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v28[256]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v29[256]; // [rsp+530h] [rbp+430h] BYREF

  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v19, v27, 0x100u);
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v24, v28, 0x100u);
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v22, v29, 0x100u);
  v15 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  STRU::STRU((STRU *)v26);
  v4 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a1)(a1);
  if ( !v4
    || (v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4)) == 0
    || (v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1),
        (v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7)) == 0) )
  {
    v5 = -2147024883;
    goto LABEL_26;
  }
  v5 = STRU::Copy((STRU *)v19, L"MACHINE/WEBROOT/APPHOST/");
  if ( v5 >= 0 )
  {
    v5 = STRU::Append((STRU *)v19, v6);
    if ( v5 >= 0 )
    {
      v5 = STRU::Copy((STRU *)v24, *(const unsigned __int16 **)(v8 + 88), *(unsigned __int16 *)(v8 + 68) >> 1);
      if ( v5 >= 0 )
      {
        v9 = *v25 == 47 ? STRU::Append((STRU *)v19, (const struct STRU *)v24) : STRU::Append((STRU *)v19, L"/", 1u);
        v5 = v9;
        if ( v9 >= 0 )
        {
          while ( *(_WORD *)(v20 + 2LL * (unsigned int)(v21 - 1)) == 47 )
            STRU::SetLen((STRU *)v19, v21 - 1);
          v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
          v5 = (**v10)(v10, &IID_INativeConfigurationSystem, &v17);
          if ( v5 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, int *, struct INativeSectionException **))(*(_QWORD *)v17 + 32LL))(
                    v17,
                    v20,
                    v23,
                    &v15,
                    &v16);
            if ( v11 == -2147024774 )
            {
              v5 = STRU::Resize((STRU *)v22, 2 * v15);
              if ( v5 < 0 )
                goto LABEL_26;
              v11 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, int *, struct INativeSectionException **))(*(_QWORD *)v17 + 32LL))(
                      v17,
                      v20,
                      v23,
                      &v15,
                      &v16);
            }
            STRU::SyncWithBuffer((STRU *)v22);
            if ( v11 >= 0 || (v5 = STRU::Copy((STRU *)v22, L"MACHINE/WEBROOT/APPHOST"), v5 >= 0) )
            {
              v12 = (struct FREB_META_STORED_CONTEXT *)operator new(0x28u);
              v13 = v12;
              if ( v12 )
              {
                *((_DWORD *)v12 + 5) = 0;
                *((_DWORD *)v12 + 9) = 0;
                *((_QWORD *)v12 + 1) = 0;
                *(_QWORD *)v12 = &FREB_META_STORED_CONTEXT::`vftable';
                *((_DWORD *)v12 + 4) = 0;
                *((_QWORD *)v12 + 3) = 0;
                *((_DWORD *)v12 + 8) = 0;
                v5 = FREB_META_STORED_CONTEXT::Initialize(
                       v12,
                       v23,
                       (enum FREB_FAILURE_POINT *)&v18,
                       (struct STRU *)v26,
                       &v16);
                if ( v5 < 0 || (v5 = FREB_REQUEST_CONTEXT::InitializeInstance(a2, v13, 1), v5 < 0) )
                  (**(void (__fastcall ***)(struct FREB_META_STORED_CONTEXT *))v13)(v13);
              }
              else
              {
                v5 = -2147024882;
              }
            }
          }
        }
      }
    }
  }
LABEL_26:
  if ( v16 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  STRU::~STRU((STRU *)v26);
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003654  mov     [rsp-8+arg_10], rbx
0x180003659  push    rbp
0x18000365a  push    rsi
0x18000365b  push    rdi
0x18000365c  push    r14
0x18000365e  push    r15
0x180003660  lea     rbp, [rsp-640h]
0x180003668  sub     rsp, 740h
0x18000366f  mov     rax, cs:__security_cookie
0x180003676  xor     rax, rsp
0x180003679  mov     [rbp+660h+var_30], rax
0x180003680  mov     r14, rdx
0x180003683  mov     rbx, rcx
0x180003686  mov     esi, 200h
0x18000368b  lea     rcx, [rbp+660h+var_630]; void *
0x18000368f  mov     r8d, esi; Size
0x180003692  xor     edx, edx; Val
0x180003694  call    memset_0
0x180003699  mov     edi, 100h
0x18000369e  lea     rdx, [rbp+660h+var_630]
0x1800036a2  mov     r8d, edi
0x1800036a5  lea     rcx, [rsp+760h+var_710]
0x1800036aa  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800036b0  mov     r8d, esi; Size
0x1800036b3  lea     rcx, [rbp+660h+var_430]; void *
0x1800036ba  xor     edx, edx; Val
0x1800036bc  call    memset_0
0x1800036c1  mov     r8d, edi
0x1800036c4  lea     rdx, [rbp+660h+var_430]
0x1800036cb  lea     rcx, [rbp+660h+var_6A0]
0x1800036cf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800036d5  mov     r8d, esi; Size
0x1800036d8  lea     rcx, [rbp+660h+var_230]; void *
0x1800036df  xor     edx, edx; Val
0x1800036e1  call    memset_0
0x1800036e6  mov     r8d, edi
0x1800036e9  lea     rdx, [rbp+660h+var_230]
0x1800036f0  lea     rcx, [rbp+660h+var_6D8]
0x1800036f4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800036fa  xor     r15d, r15d
0x1800036fd  lea     rcx, [rbp+660h+var_668]
0x180003701  mov     [rsp+760h+var_730], r15d
0x180003706  mov     [rsp+760h+var_720], r15
0x18000370b  mov     [rsp+760h+var_728], r15
0x180003710  mov     [rsp+760h+var_718], r15d
0x180003715  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000371b  mov     rax, [rbx]
0x18000371e  mov     rcx, rbx
0x180003721  mov     rax, [rax]
0x180003724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003729  mov     rcx, rax
0x18000372c  test    rax, rax
0x18000372f  jnz     short loc_18000373B
0x180003731  mov     ebx, 8007000Dh
0x180003736  jmp     loc_180003983
0x18000373b  mov     rax, [rax]
0x18000373e  mov     rax, [rax+8]
0x180003742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003747  mov     rsi, rax
0x18000374a  test    rax, rax
0x18000374d  jz      short loc_180003731
0x18000374f  mov     rax, [rbx]
0x180003752  mov     rcx, rbx
0x180003755  mov     rax, [rax+18h]
0x180003759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375e  mov     rdx, rax
0x180003761  mov     rcx, [rax]
0x180003764  mov     rax, [rcx+8]
0x180003768  mov     rcx, rdx
0x18000376b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003770  mov     rdi, rax
0x180003773  test    rax, rax
0x180003776  jz      short loc_180003731
0x180003778  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x18000377f  lea     rcx, [rsp+760h+var_710]
0x180003784  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000378a  mov     ebx, eax
0x18000378c  test    eax, eax
0x18000378e  js      loc_180003983
0x180003794  mov     rdx, rsi
0x180003797  lea     rcx, [rsp+760h+var_710]
0x18000379c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800037a2  mov     ebx, eax
0x1800037a4  test    eax, eax
0x1800037a6  js      loc_180003983
0x1800037ac  movzx   r8d, word ptr [rdi+44h]
0x1800037b1  lea     rcx, [rbp+660h+var_6A0]
0x1800037b5  mov     rdx, [rdi+58h]
0x1800037b9  shr     r8d, 1
0x1800037bc  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800037c2  mov     ebx, eax
0x1800037c4  test    eax, eax
0x1800037c6  js      loc_180003983
0x1800037cc  mov     rax, [rbp+660h+var_680]
0x1800037d0  lea     rcx, [rsp+760h+var_710]
0x1800037d5  mov     esi, 1
0x1800037da  cmp     word ptr [rax], 2Fh ; '/'
0x1800037de  jz      short loc_1800037F2
0x1800037e0  mov     r8d, esi
0x1800037e3  lea     rdx, asc_18000CAD0; "/"
0x1800037ea  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x1800037f0  jmp     short loc_1800037FC
0x1800037f2  lea     rdx, [rbp+660h+var_6A0]
0x1800037f6  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800037fc  mov     ebx, eax
0x1800037fe  test    eax, eax
0x180003800  js      loc_180003983
0x180003806  jmp     short loc_180003815
0x180003808  dec     edx
0x18000380a  lea     rcx, [rsp+760h+var_710]
0x18000380f  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180003815  mov     edx, [rbp+660h+var_6E0]
0x180003818  mov     rax, [rsp+760h+var_6F0]
0x18000381d  lea     ecx, [rdx-1]
0x180003820  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x180003825  jz      short loc_180003808
0x180003827  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000382e  mov     rax, [rcx]
0x180003831  mov     rax, [rax+38h]
0x180003835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383a  mov     r9, rax
0x18000383d  lea     r8, [rsp+760h+var_720]
0x180003842  lea     rdx, IID_INativeConfigurationSystem
0x180003849  mov     rcx, [rax]
0x18000384c  mov     rax, [rcx]
0x18000384f  mov     rcx, r9
0x180003852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003857  mov     ebx, eax
0x180003859  test    eax, eax
0x18000385b  js      loc_180003983
0x180003861  mov     rcx, [rsp+760h+var_720]
0x180003866  lea     rdx, [rsp+760h+var_728]
0x18000386b  mov     r8, [rbp+660h+var_6B8]
0x18000386f  lea     r9, [rsp+760h+var_730]
0x180003874  mov     [rsp+760h+var_740], rdx
0x180003879  mov     rdx, [rsp+760h+var_6F0]
0x18000387e  mov     rax, [rcx]
0x180003881  mov     rax, [rax+20h]
0x180003885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388a  mov     ebx, eax
0x18000388c  cmp     eax, 8007007Ah
0x180003891  jnz     short loc_1800038D8
0x180003893  mov     edx, [rsp+760h+var_730]
0x180003897  lea     rcx, [rbp+660h+var_6D8]
0x18000389b  add     edx, edx
0x18000389d  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800038a3  mov     ebx, eax
0x1800038a5  test    eax, eax
0x1800038a7  js      loc_180003983
0x1800038ad  mov     rcx, [rsp+760h+var_720]
0x1800038b2  lea     rdx, [rsp+760h+var_728]
0x1800038b7  mov     r8, [rbp+660h+var_6B8]
0x1800038bb  lea     r9, [rsp+760h+var_730]
0x1800038c0  mov     [rsp+760h+var_740], rdx
0x1800038c5  mov     rdx, [rsp+760h+var_6F0]
0x1800038ca  mov     rax, [rcx]
0x1800038cd  mov     rax, [rax+20h]
0x1800038d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d6  mov     ebx, eax
0x1800038d8  lea     rcx, [rbp+660h+var_6D8]
0x1800038dc  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800038e2  test    ebx, ebx
0x1800038e4  jns     short loc_180003901
0x1800038e6  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800038ed  lea     rcx, [rbp+660h+var_6D8]
0x1800038f1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800038f7  mov     ebx, eax
0x1800038f9  test    eax, eax
0x1800038fb  js      loc_180003983
0x180003901  mov     ecx, 28h ; '('; Size
0x180003906  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000390b  mov     rdi, rax
0x18000390e  test    rax, rax
0x180003911  jz      short loc_18000397E
0x180003913  mov     [rax+14h], r15d
0x180003917  lea     r9, [rbp+660h+var_668]; struct STRU *
0x18000391b  mov     [rax+24h], r15d
0x18000391f  lea     r8, [rsp+760h+var_718]; enum FREB_FAILURE_POINT *
0x180003924  lea     rax, ??_7FREB_META_STORED_CONTEXT@@6B@; const FREB_META_STORED_CONTEXT::`vftable'
0x18000392b  mov     [rdi+8], r15
0x18000392f  mov     [rdi], rax
0x180003932  mov     rcx, rdi; this
0x180003935  lea     rax, [rsp+760h+var_728]
0x18000393a  mov     [rdi+10h], r15d
0x18000393e  mov     [rdi+18h], r15
0x180003942  mov     [rdi+20h], r15d
0x180003946  mov     rdx, [rbp+660h+var_6B8]; unsigned __int16 *
0x18000394a  mov     [rsp+760h+var_740], rax; struct INativeSectionException **
0x18000394f  call    ?Initialize@FREB_META_STORED_CONTEXT@@QEAAJPEBGPEAW4FREB_FAILURE_POINT@@PEAVSTRU@@PEAPEAVINativeSectionException@@@Z; FREB_META_STORED_CONTEXT::Initialize(ushort const *,FREB_FAILURE_POINT *,STRU *,INativeSectionException * *)
0x180003954  mov     ebx, eax
0x180003956  test    eax, eax
0x180003958  js      short loc_18000396E
0x18000395a  mov     r8d, esi; int
0x18000395d  mov     rdx, rdi; struct FREB_META_STORED_CONTEXT *
0x180003960  mov     rcx, r14; this
0x180003963  call    ?InitializeInstance@FREB_REQUEST_CONTEXT@@QEAAJPEAVFREB_META_STORED_CONTEXT@@H@Z; FREB_REQUEST_CONTEXT::InitializeInstance(FREB_META_STORED_CONTEXT *,int)
0x180003968  mov     ebx, eax
0x18000396a  test    eax, eax
0x18000396c  jns     short loc_180003983
0x18000396e  mov     rax, [rdi]
0x180003971  mov     rcx, rdi
0x180003974  mov     rax, [rax]
0x180003977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397c  jmp     short loc_180003983
0x18000397e  mov     ebx, 8007000Eh
0x180003983  mov     rcx, [rsp+760h+var_728]
0x180003988  test    rcx, rcx
0x18000398b  jz      short loc_18000399E
0x18000398d  mov     rax, [rcx]
0x180003990  mov     rax, [rax+10h]
0x180003994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003999  mov     [rsp+760h+var_728], r15
0x18000399e  mov     rcx, [rsp+760h+var_720]
0x1800039a3  test    rcx, rcx
0x1800039a6  jz      short loc_1800039B9
0x1800039a8  mov     rax, [rcx]
0x1800039ab  mov     rax, [rax+10h]
0x1800039af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b4  mov     [rsp+760h+var_720], r15
0x1800039b9  lea     rcx, [rbp+660h+var_668]
0x1800039bd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039c3  lea     rcx, [rbp+660h+var_6D8]
0x1800039c7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039cd  lea     rcx, [rbp+660h+var_6A0]
0x1800039d1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039d7  lea     rcx, [rsp+760h+var_710]
0x1800039dc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039e2  mov     eax, ebx
0x1800039e4  mov     rcx, [rbp+660h+var_30]
0x1800039eb  xor     rcx, rsp; StackCookie
0x1800039ee  call    __security_check_cookie
0x1800039f3  mov     rbx, [rsp+760h+arg_10]
0x1800039fb  add     rsp, 740h
0x180003a02  pop     r15
0x180003a04  pop     r14
0x180003a06  pop     rdi
0x180003a07  pop     rsi
0x180003a08  pop     rbp
0x180003a09  retn
```
