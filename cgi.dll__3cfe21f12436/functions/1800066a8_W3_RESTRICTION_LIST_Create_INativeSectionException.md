# W3_RESTRICTION_LIST::Create(INativeSectionException * *)

- ea: `0x1800066a8`
- end: `0x1800069ad`
- name: `?Create@W3_RESTRICTION_LIST@@AEAAJPEAPEAVINativeSectionException@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(W3_RESTRICTION_LIST *__hidden this, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800069b4`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800066a8`
- `0x180008010`

## import_xrefs

- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800068bc`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800068bc`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006890`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006890`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800068d4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000691e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800068d4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000691e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800068a7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800068a7`

## string_xrefs

- `0x180006731`: `system.webServer/security/isapiCgiRestriction`

## pseudocode

```c
__int64 __fastcall W3_RESTRICTION_LIST::Create(W3_RESTRICTION_LIST *this, struct INativeSectionException **a2)
{
  __int64 v4; // rax
  __int64 (__fastcall *v5)(struct IHttpServer *); // rax
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  int v7; // ebx
  unsigned int v8; // esi
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  const unsigned __int16 *v11; // rdx
  __int64 v12; // r8
  int inserted; // r15d
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+C0h] [rbp+50h] BYREF
  int v21; // [rsp+C8h] [rbp+58h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  v4 = *(_QWORD *)W3_RESTRICTION_LIST::sm_pGlobalInfo;
  v15 = 0;
  v20 = 0;
  v19 = 0;
  v5 = *(__int64 (__fastcall **)(struct IHttpServer *))(v4 + 56);
  v21 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v5(W3_RESTRICTION_LIST::sm_pGlobalInfo);
  v7 = (**v6)(v6, &IID_INativeConfigurationSystem, &v18);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v18 + 24LL))(
           v18,
           L"system.webServer/security/isapiCgiRestriction",
           L"MACHINE/WEBROOT/APPHOST",
           &v16,
           a2,
           0);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
             v16,
             L"notListedIsapisAllowed",
             (char *)this + 76,
             0,
             0);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
               v16,
               L"notListedCgisAllowed",
               (char *)this + 72,
               0,
               0);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 40LL))(v16, &v17);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v20);
            if ( v7 >= 0 )
            {
              v8 = 0;
              if ( v20 )
              {
                while ( 1 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 32LL))(v17, v8, &v15);
                  if ( v7 < 0 )
                    break;
                  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                         v15,
                         L"path",
                         &v19,
                         0,
                         0);
                  if ( v7 < 0 )
                    break;
                  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
                         v15,
                         L"allowed",
                         &v21,
                         0,
                         0);
                  if ( v7 < 0 )
                    break;
                  v9 = operator new(0x48u);
                  v10 = v9;
                  if ( !v9 )
                  {
                    v7 = -2147024888;
                    break;
                  }
                  *v9 = 1;
                  STRU::STRU((STRU *)(v9 + 2));
                  v11 = v19;
                  v10[16] = v21;
                  v7 = STRU::Copy((STRU *)(v10 + 2), v11);
                  if ( v7 < 0 )
                  {
                    if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFF) == 1 )
                    {
                      STRU::~STRU((STRU *)(v10 + 2));
                      operator delete(v10);
                    }
                    break;
                  }
                  LOBYTE(v12) = 1;
                  inserted = CLKRHashTable::InsertRecord(this, v10, v12);
                  if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFF) == 1 )
                  {
                    STRU::~STRU((STRU *)(v10 + 2));
                    operator delete(v10);
                  }
                  if ( inserted )
                  {
                    v7 = -2147467259;
                    break;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  ++v8;
                  v15 = 0;
                  if ( v8 >= v20 )
                    goto LABEL_24;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
LABEL_24:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800066a8  mov     [rsp-38h+arg_0], rbx
0x1800066ad  push    rbp
0x1800066ae  push    rsi
0x1800066af  push    rdi
0x1800066b0  push    r12
0x1800066b2  push    r13
0x1800066b4  push    r14
0x1800066b6  push    r15
0x1800066b8  mov     rbp, rsp
0x1800066bb  sub     rsp, 70h
0x1800066bf  xor     r12d, r12d
0x1800066c2  mov     r13, rcx
0x1800066c5  mov     rcx, cs:?sm_pGlobalInfo@W3_RESTRICTION_LIST@@0PEAVIHttpServer@@EA; IHttpServer * W3_RESTRICTION_LIST::sm_pGlobalInfo
0x1800066cc  mov     rdi, rdx
0x1800066cf  mov     [rbp+var_18], r12
0x1800066d3  mov     [rbp+var_28], r12
0x1800066d7  mov     [rbp+var_20], r12
0x1800066db  mov     rax, [rcx]
0x1800066de  mov     [rbp+var_30], r12
0x1800066e2  mov     [rbp+arg_10], r12d
0x1800066e6  mov     [rbp+var_10], r12
0x1800066ea  mov     rax, [rax+38h]
0x1800066ee  mov     [rbp+arg_18], r12d
0x1800066f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f7  mov     r9, rax
0x1800066fa  lea     r8, [rbp+var_18]
0x1800066fe  lea     rdx, IID_INativeConfigurationSystem
0x180006705  mov     rcx, [rax]
0x180006708  mov     rax, [rcx]
0x18000670b  mov     rcx, r9
0x18000670e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006713  mov     ebx, eax
0x180006715  test    eax, eax
0x180006717  js      loc_180006933
0x18000671d  mov     rcx, [rbp+var_18]
0x180006721  lea     r9, [rbp+var_28]
0x180006725  mov     [rsp+70h+var_48], r12
0x18000672a  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180006731  lea     rdx, aSystemWebserve; "system.webServer/security/isapiCgiRestr"...
0x180006738  mov     [rsp+70h+var_50], rdi
0x18000673d  mov     rax, [rcx]
0x180006740  mov     rax, [rax+18h]
0x180006744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006749  mov     ebx, eax
0x18000674b  test    eax, eax
0x18000674d  js      loc_180006933
0x180006753  mov     rcx, [rbp+var_28]
0x180006757  lea     r8, [r13+4Ch]
0x18000675b  xor     r9d, r9d
0x18000675e  mov     [rsp+70h+var_50], r12
0x180006763  lea     rdx, aNotlistedisapi; "notListedIsapisAllowed"
0x18000676a  mov     rax, [rcx]
0x18000676d  mov     rax, [rax+48h]
0x180006771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006776  mov     ebx, eax
0x180006778  test    eax, eax
0x18000677a  js      loc_180006933
0x180006780  mov     rcx, [rbp+var_28]
0x180006784  lea     r8, [r13+48h]
0x180006788  xor     r9d, r9d
0x18000678b  mov     [rsp+70h+var_50], r12
0x180006790  lea     rdx, aNotlistedcgisa; "notListedCgisAllowed"
0x180006797  mov     rax, [rcx]
0x18000679a  mov     rax, [rax+48h]
0x18000679e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a3  mov     ebx, eax
0x1800067a5  test    eax, eax
0x1800067a7  js      loc_180006933
0x1800067ad  mov     rcx, [rbp+var_28]
0x1800067b1  lea     rdx, [rbp+var_20]
0x1800067b5  mov     rax, [rcx]
0x1800067b8  mov     rax, [rax+28h]
0x1800067bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067c1  mov     ebx, eax
0x1800067c3  test    eax, eax
0x1800067c5  js      loc_180006933
0x1800067cb  mov     rcx, [rbp+var_20]
0x1800067cf  lea     rdx, [rbp+arg_10]
0x1800067d3  mov     rax, [rcx]
0x1800067d6  mov     rax, [rax+18h]
0x1800067da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067df  mov     ebx, eax
0x1800067e1  test    eax, eax
0x1800067e3  js      loc_180006933
0x1800067e9  mov     esi, r12d
0x1800067ec  cmp     [rbp+arg_10], r12d
0x1800067f0  jbe     loc_180006933
0x1800067f6  mov     rcx, [rbp+var_20]
0x1800067fa  lea     r8, [rbp+var_30]
0x1800067fe  mov     edx, esi
0x180006800  mov     rax, [rcx]
0x180006803  mov     rax, [rax+20h]
0x180006807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000680c  mov     ebx, eax
0x18000680e  test    eax, eax
0x180006810  js      loc_180006933
0x180006816  mov     rcx, [rbp+var_30]
0x18000681a  lea     r8, [rbp+var_10]
0x18000681e  xor     r9d, r9d
0x180006821  mov     [rsp+70h+var_50], r12
0x180006826  lea     rdx, aPath; "path"
0x18000682d  mov     rax, [rcx]
0x180006830  mov     rax, [rax+40h]
0x180006834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006839  mov     ebx, eax
0x18000683b  test    eax, eax
0x18000683d  js      loc_180006933
0x180006843  mov     rcx, [rbp+var_30]
0x180006847  lea     r8, [rbp+arg_18]
0x18000684b  xor     r9d, r9d
0x18000684e  mov     [rsp+70h+var_50], r12
0x180006853  lea     rdx, aAllowed; "allowed"
0x18000685a  mov     rax, [rcx]
0x18000685d  mov     rax, [rax+48h]
0x180006861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006866  mov     ebx, eax
0x180006868  test    eax, eax
0x18000686a  js      loc_180006933
0x180006870  mov     ecx, 48h ; 'H'; Size
0x180006875  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000687a  mov     rdi, rax
0x18000687d  test    rax, rax
0x180006880  jz      loc_18000692E
0x180006886  lea     rcx, [rax+8]
0x18000688a  mov     dword ptr [rax], 1
0x180006890  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006896  mov     ecx, [rbp+arg_18]
0x180006899  lea     r14, [rdi+8]
0x18000689d  mov     rdx, [rbp+var_10]
0x1800068a1  mov     [rdi+40h], ecx
0x1800068a4  mov     rcx, r14
0x1800068a7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800068ad  mov     ebx, eax
0x1800068af  test    eax, eax
0x1800068b1  js      short loc_18000690F
0x1800068b3  mov     r8b, 1
0x1800068b6  mov     rdx, rdi
0x1800068b9  mov     rcx, r13
0x1800068bc  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800068c2  mov     r15d, eax
0x1800068c5  or      edx, 0FFFFFFFFh
0x1800068c8  lock xadd [rdi], edx
0x1800068cc  cmp     edx, 1
0x1800068cf  jnz     short loc_1800068E2
0x1800068d1  mov     rcx, r14
0x1800068d4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800068da  mov     rcx, rdi; Block
0x1800068dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800068e2  test    r15d, r15d
0x1800068e5  jnz     short loc_180006908
0x1800068e7  mov     rcx, [rbp+var_30]
0x1800068eb  mov     rax, [rcx]
0x1800068ee  mov     rax, [rax+10h]
0x1800068f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f7  inc     esi
0x1800068f9  mov     [rbp+var_30], r12
0x1800068fd  cmp     esi, [rbp+arg_10]
0x180006900  jb      loc_1800067F6
0x180006906  jmp     short loc_18000694C
0x180006908  mov     ebx, 80004005h
0x18000690d  jmp     short loc_180006933
0x18000690f  or      eax, 0FFFFFFFFh
0x180006912  lock xadd [rdi], eax
0x180006916  cmp     eax, 1
0x180006919  jnz     short loc_180006933
0x18000691b  mov     rcx, r14
0x18000691e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006924  mov     rcx, rdi; Block
0x180006927  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000692c  jmp     short loc_180006933
0x18000692e  mov     ebx, 80070008h
0x180006933  mov     rcx, [rbp+var_30]
0x180006937  test    rcx, rcx
0x18000693a  jz      short loc_18000694C
0x18000693c  mov     rax, [rcx]
0x18000693f  mov     rax, [rax+10h]
0x180006943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006948  mov     [rbp+var_30], r12
0x18000694c  mov     rcx, [rbp+var_20]
0x180006950  test    rcx, rcx
0x180006953  jz      short loc_180006965
0x180006955  mov     rax, [rcx]
0x180006958  mov     rax, [rax+10h]
0x18000695c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006961  mov     [rbp+var_20], r12
0x180006965  mov     rcx, [rbp+var_28]
0x180006969  test    rcx, rcx
0x18000696c  jz      short loc_18000697E
0x18000696e  mov     rax, [rcx]
0x180006971  mov     rax, [rax+10h]
0x180006975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697a  mov     [rbp+var_28], r12
0x18000697e  mov     rcx, [rbp+var_18]
0x180006982  test    rcx, rcx
0x180006985  jz      short loc_180006993
0x180006987  mov     rax, [rcx]
0x18000698a  mov     rax, [rax+10h]
0x18000698e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006993  mov     eax, ebx
0x180006995  mov     rbx, [rsp+70h+arg_0]
0x18000699d  add     rsp, 70h
0x1800069a1  pop     r15
0x1800069a3  pop     r14
0x1800069a5  pop     r13
0x1800069a7  pop     r12
0x1800069a9  pop     rdi
0x1800069aa  pop     rsi
0x1800069ab  pop     rbp
0x1800069ac  retn
```
