# W3_CONTEXT::SetupSite(INativeSectionException * *)

- ea: `0x1800096a0`
- end: `0x180009b98`
- name: `?SetupSite@W3_CONTEXT@@QEAAJPEAPEAVINativeSectionException@@@Z`
- size: `1272`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180009d44`

## callees

- `0x1800096a0`
- `0x180017a34`
- `0x18001ab30`
- `0x180020fac`
- `0x18002e694`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180009952`
- `msvcrt!_wcsupr` at `0x180009952`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097b3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009b6c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009b7d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097b3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009b6c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009b7d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009850`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800098b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009943`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009984`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800099c6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009a96`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009850`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800098b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009943`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009984`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800099c6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009a96`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180009890`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180009890`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180009932`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180009932`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009969`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009969`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800096f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000971f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800096f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000971f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180009997`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180009997`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180009acd`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180009af1`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180009acd`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180009af1`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180009786`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180009786`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::SetupSite(W3_CONTEXT *this, struct INativeSectionException **a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  W3_SITE **v6; // rbx
  char *v7; // rcx
  int Key; // eax
  W3_SITE *v10; // rax
  W3_SITE *v11; // rax
  int v12; // edi
  __int64 (__fastcall *v13)(__int64, _QWORD, unsigned __int16 *, int *, struct INativeSectionException **); // rdi
  unsigned __int16 *Str; // rax
  int v15; // eax
  __int64 (__fastcall *v16)(__int64, _QWORD, unsigned __int16 *, int *, struct INativeSectionException **); // rdi
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rax
  const unsigned __int16 *v19; // rax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD); // rdi
  unsigned __int16 *v22; // rax
  W3_SITE *v23; // r14
  unsigned int v24; // edi
  unsigned __int16 *v25; // rsi
  const unsigned __int16 *v26; // rax
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v29; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  W3_SITE *v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v36[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v37[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v38[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(v38, 0, 0x208u);
  STRU::STRU((STRU *)v35, v38, 0x104u);
  memset_0(v37, 0, sizeof(v37));
  STRU::STRU((STRU *)v36, v37, 0x100u);
  v4 = *((_QWORD *)this + 6);
  v28 = 260;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v34 = 0;
  v29 = 0;
  v5 = HIDWORD(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 24LL));
  v6 = (W3_SITE **)((char *)this + 8072);
  if ( v6 )
  {
    v7 = (char *)g_pW3Server + 1240;
    *v6 = 0;
    v33 = 0;
    Key = CLKRHashTable::FindKey(v7, v5, &v33);
    *v6 = v33;
    if ( !Key )
    {
      STRU::~STRU((STRU *)v36);
      STRU::~STRU((STRU *)v35);
      return 0;
    }
  }
  v10 = (W3_SITE *)operator new(0x2A0u);
  if ( !v10 )
  {
    *v6 = 0;
    goto LABEL_23;
  }
  v11 = W3_SITE::W3_SITE(v10, v5);
  *v6 = v11;
  if ( !v11 )
  {
LABEL_23:
    v12 = -2147024888;
    goto LABEL_24;
  }
  v27 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)g_pW3Server + 187) + 56LL))(
          *((_QWORD *)g_pW3Server + 187),
          &v27);
  if ( v12 >= 0 )
  {
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, int *, struct INativeSectionException **))(*(_QWORD *)v27 + 24LL);
    Str = STRU::QueryStr((STRU *)v35);
    v15 = v13(v27, (unsigned int)v5, Str, &v28, a2);
    v12 = v15;
    if ( v15 >= 0
      || v15 == -2147024774
      && (v12 = STRU::Resize((STRU *)v35, 2 * v28), v12 >= 0)
      && (v16 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, int *, struct INativeSectionException **))(*(_QWORD *)v27 + 24LL),
          v17 = STRU::QueryStr((STRU *)v35),
          v12 = v16(v27, (unsigned int)v5, v17, &v28, a2),
          v12 >= 0) )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct INativeSectionException **))(*(_QWORD *)v27 + 32LL))(
              v27,
              (unsigned int)v5,
              &v31,
              a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v12 >= 0 )
      {
        STRU::SyncWithBuffer((STRU *)v35);
        v18 = STRU::QueryStr((STRU *)v35);
        _wcsupr(v18);
        v12 = STRU::Copy((STRU *)v36, L"MACHINE/WEBROOT/APPHOST/");
        if ( v12 >= 0 )
        {
          v19 = STRU::QueryStr((STRU *)v35);
          v12 = STRU::Append((STRU *)v36, v19);
          if ( v12 >= 0 )
          {
            v20 = *((_QWORD *)g_pW3Server + 187);
            v21 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v20 + 24LL);
            v22 = STRU::QueryStr((STRU *)v36);
            v12 = v21(v20, L"system.webServer/serverRuntime", v22, &v32, a2, 0);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v32 + 64LL))(
                      v32,
                      L"alternateHostName",
                      &v34,
                      0,
                      0);
              if ( v12 >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v31 + 32LL))(
                        v31,
                        L"limits",
                        &v30);
                if ( v12 >= 0 )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v30 + 48LL))(
                          v30,
                          L"maxUrlSegments",
                          &v29,
                          0,
                          0);
                  if ( v12 >= 0 )
                  {
                    v23 = *v6;
                    v24 = v29;
                    v25 = v34;
                    v26 = STRU::QueryStr((STRU *)v35);
                    v12 = W3_SITE::Initialize(v23, v26, v25, v24);
                    if ( v12 >= 0 )
                    {
                      if ( !(unsigned int)CLKRHashTable::InsertRecord((char *)g_pW3Server + 1312, *v6, 0) )
                        CLKRHashTable::InsertRecord((char *)g_pW3Server + 1240, *v6, 0);
                      goto LABEL_26;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
  }
LABEL_24:
  if ( *v6 )
  {
    W3_SITE::DereferenceSiteInfo(*v6);
    *v6 = 0;
  }
LABEL_26:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  STRU::~STRU((STRU *)v36);
  STRU::~STRU((STRU *)v35);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800096a0  push    rbp
0x1800096a2  push    rbx
0x1800096a3  push    rsi
0x1800096a4  push    r14
0x1800096a6  push    r15
0x1800096a8  lea     rbp, [rsp-410h]
0x1800096b0  sub     rsp, 510h
0x1800096b7  mov     rax, cs:__security_cookie
0x1800096be  xor     rax, rsp
0x1800096c1  mov     [rbp+430h+var_30], rax
0x1800096c8  mov     r14, rdx
0x1800096cb  mov     rbx, rcx
0x1800096ce  xor     edx, edx; Val
0x1800096d0  lea     rcx, [rbp+430h+var_240]; void *
0x1800096d7  mov     r8d, 208h; Size
0x1800096dd  call    memset_0
0x1800096e2  mov     r8d, 104h
0x1800096e8  lea     rdx, [rbp+430h+var_240]
0x1800096ef  lea     rcx, [rsp+530h+var_4B8]
0x1800096f4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800096fb  nop     dword ptr [rax+rax+00h]
0x180009700  xor     edx, edx; Val
0x180009702  lea     rcx, [rbp+430h+var_440]; void *
0x180009706  mov     r8d, 200h; Size
0x18000970c  call    memset_0
0x180009711  mov     r8d, 100h
0x180009717  lea     rdx, [rbp+430h+var_440]
0x18000971b  lea     rcx, [rbp+430h+var_480]
0x18000971f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009726  nop     dword ptr [rax+rax+00h]
0x18000972b  mov     rax, [rbx+30h]
0x18000972f  xor     r15d, r15d
0x180009732  mov     [rsp+530h+var_4E8], 104h
0x18000973a  mov     [rsp+530h+var_4D0], r15
0x18000973f  mov     [rsp+530h+var_4D8], r15
0x180009744  mov     [rsp+530h+var_4E0], r15
0x180009749  mov     [rsp+530h+var_4C0], r15
0x18000974e  mov     [rsp+530h+var_4E4], r15d
0x180009753  mov     rcx, [rax+28h]
0x180009757  mov     rsi, [rcx+18h]
0x18000975b  shr     rsi, 20h
0x18000975f  add     rbx, 1F88h
0x180009766  jz      short loc_1800097E0
0x180009768  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18000976f  lea     r8, [rsp+530h+var_4C8]
0x180009774  add     rcx, 4D8h
0x18000977b  mov     [rbx], r15
0x18000977e  mov     rdx, rsi
0x180009781  mov     [rsp+530h+var_4C8], r15
0x180009786  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000978d  nop     dword ptr [rax+rax+00h]
0x180009792  mov     rcx, [rsp+530h+var_4C8]
0x180009797  mov     [rbx], rcx
0x18000979a  test    eax, eax
0x18000979c  jnz     short loc_1800097E0
0x18000979e  lea     rcx, [rbp+430h+var_480]
0x1800097a2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800097a9  nop     dword ptr [rax+rax+00h]
0x1800097ae  lea     rcx, [rsp+530h+var_4B8]
0x1800097b3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800097ba  nop     dword ptr [rax+rax+00h]
0x1800097bf  xor     eax, eax
0x1800097c1  mov     rcx, [rbp+430h+var_30]
0x1800097c8  xor     rcx, rsp; StackCookie
0x1800097cb  call    __security_check_cookie
0x1800097d0  add     rsp, 510h
0x1800097d7  pop     r15
0x1800097d9  pop     r14
0x1800097db  pop     rsi
0x1800097dc  pop     rbx
0x1800097dd  pop     rbp
0x1800097de  retn
0x1800097e0  mov     ecx, 2A0h; Size
0x1800097e5  mov     [rsp+530h+arg_10], rdi
0x1800097ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800097f2  test    rax, rax
0x1800097f5  jz      loc_180009AFF
0x1800097fb  mov     edx, esi; unsigned int
0x1800097fd  mov     rcx, rax; this
0x180009800  call    ??0W3_SITE@@QEAA@K@Z; W3_SITE::W3_SITE(ulong)
0x180009805  mov     [rbx], rax
0x180009808  test    rax, rax
0x18000980b  jz      loc_180009B02
0x180009811  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009818  lea     rdx, [rsp+530h+var_4F0]
0x18000981d  mov     [rsp+530h+var_4F0], r15
0x180009822  mov     rcx, [rax+5D8h]
0x180009829  mov     rax, [rcx]
0x18000982c  mov     rax, [rax+38h]
0x180009830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009835  mov     edi, eax
0x180009837  test    eax, eax
0x180009839  js      loc_180009B07
0x18000983f  mov     rax, [rsp+530h+var_4F0]
0x180009844  mov     rcx, [rax]
0x180009847  mov     rdi, [rcx+18h]
0x18000984b  lea     rcx, [rsp+530h+var_4B8]
0x180009850  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009857  nop     dword ptr [rax+rax+00h]
0x18000985c  mov     rcx, [rsp+530h+var_4F0]
0x180009861  lea     r9, [rsp+530h+var_4E8]
0x180009866  mov     r8, rax
0x180009869  mov     [rsp+530h+var_510], r14
0x18000986e  mov     rax, rdi
0x180009871  mov     edx, esi
0x180009873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009878  mov     edi, eax
0x18000987a  test    eax, eax
0x18000987c  jns     short loc_1800098F7
0x18000987e  cmp     eax, 8007007Ah
0x180009883  jnz     short loc_1800098E1
0x180009885  mov     edx, [rsp+530h+var_4E8]
0x180009889  lea     rcx, [rsp+530h+var_4B8]
0x18000988e  add     edx, edx
0x180009890  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180009897  nop     dword ptr [rax+rax+00h]
0x18000989c  mov     edi, eax
0x18000989e  test    eax, eax
0x1800098a0  js      short loc_1800098E1
0x1800098a2  mov     rax, [rsp+530h+var_4F0]
0x1800098a7  mov     rcx, [rax]
0x1800098aa  mov     rdi, [rcx+18h]
0x1800098ae  lea     rcx, [rsp+530h+var_4B8]
0x1800098b3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800098ba  nop     dword ptr [rax+rax+00h]
0x1800098bf  mov     rcx, [rsp+530h+var_4F0]
0x1800098c4  lea     r9, [rsp+530h+var_4E8]
0x1800098c9  mov     r8, rax
0x1800098cc  mov     [rsp+530h+var_510], r14
0x1800098d1  mov     rax, rdi
0x1800098d4  mov     edx, esi
0x1800098d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098db  mov     edi, eax
0x1800098dd  test    eax, eax
0x1800098df  jns     short loc_1800098F7
0x1800098e1  mov     rcx, [rsp+530h+var_4F0]
0x1800098e6  mov     rax, [rcx]
0x1800098e9  mov     rax, [rax+10h]
0x1800098ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f2  jmp     loc_180009B07
0x1800098f7  mov     rcx, [rsp+530h+var_4F0]
0x1800098fc  lea     r8, [rsp+530h+var_4D8]
0x180009901  mov     r9, r14
0x180009904  mov     edx, esi
0x180009906  mov     rax, [rcx]
0x180009909  mov     rax, [rax+20h]
0x18000990d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009912  mov     rcx, [rsp+530h+var_4F0]
0x180009917  mov     edi, eax
0x180009919  mov     rax, [rcx]
0x18000991c  mov     rax, [rax+10h]
0x180009920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009925  test    edi, edi
0x180009927  js      loc_180009B07
0x18000992d  lea     rcx, [rsp+530h+var_4B8]
0x180009932  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180009939  nop     dword ptr [rax+rax+00h]
0x18000993e  lea     rcx, [rsp+530h+var_4B8]
0x180009943  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000994a  nop     dword ptr [rax+rax+00h]
0x18000994f  mov     rcx, rax; String
0x180009952  call    cs:__imp__wcsupr
0x180009959  nop     dword ptr [rax+rax+00h]
0x18000995e  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180009965  lea     rcx, [rbp+430h+var_480]
0x180009969  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180009970  nop     dword ptr [rax+rax+00h]
0x180009975  mov     edi, eax
0x180009977  test    eax, eax
0x180009979  js      loc_180009B07
0x18000997f  lea     rcx, [rsp+530h+var_4B8]
0x180009984  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000998b  nop     dword ptr [rax+rax+00h]
0x180009990  mov     rdx, rax
0x180009993  lea     rcx, [rbp+430h+var_480]
0x180009997  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000999e  nop     dword ptr [rax+rax+00h]
0x1800099a3  mov     edi, eax
0x1800099a5  test    eax, eax
0x1800099a7  js      loc_180009B07
0x1800099ad  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800099b4  lea     rcx, [rbp+430h+var_480]
0x1800099b8  mov     rsi, [rax+5D8h]
0x1800099bf  mov     rax, [rsi]
0x1800099c2  mov     rdi, [rax+18h]
0x1800099c6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800099cd  nop     dword ptr [rax+rax+00h]
0x1800099d2  mov     [rsp+530h+var_508], r15
0x1800099d7  lea     r9, [rsp+530h+var_4D0]
0x1800099dc  mov     r8, rax
0x1800099df  mov     [rsp+530h+var_510], r14
0x1800099e4  mov     rax, rdi
0x1800099e7  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x1800099ee  mov     rcx, rsi
0x1800099f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099f6  mov     edi, eax
0x1800099f8  test    eax, eax
0x1800099fa  js      loc_180009B07
0x180009a00  mov     rcx, [rsp+530h+var_4D0]
0x180009a05  lea     r8, [rsp+530h+var_4C0]
0x180009a0a  xor     r9d, r9d
0x180009a0d  mov     [rsp+530h+var_510], r15
0x180009a12  lea     rdx, aAlternatehostn; "alternateHostName"
0x180009a19  mov     rax, [rcx]
0x180009a1c  mov     rax, [rax+40h]
0x180009a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a25  mov     edi, eax
0x180009a27  test    eax, eax
0x180009a29  js      loc_180009B07
0x180009a2f  mov     rcx, [rsp+530h+var_4D8]
0x180009a34  lea     r8, [rsp+530h+var_4E0]
0x180009a39  lea     rdx, aLimits; "limits"
0x180009a40  mov     rax, [rcx]
0x180009a43  mov     rax, [rax+20h]
0x180009a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a4c  mov     edi, eax
0x180009a4e  test    eax, eax
0x180009a50  js      loc_180009B07
0x180009a56  mov     rcx, [rsp+530h+var_4E0]
0x180009a5b  lea     r8, [rsp+530h+var_4E4]
0x180009a60  xor     r9d, r9d
0x180009a63  mov     [rsp+530h+var_510], r15
0x180009a68  lea     rdx, aMaxurlsegments; "maxUrlSegments"
0x180009a6f  mov     rax, [rcx]
0x180009a72  mov     rax, [rax+30h]
0x180009a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7b  mov     edi, eax
0x180009a7d  test    eax, eax
0x180009a7f  js      loc_180009B07
0x180009a85  mov     r14, [rbx]
0x180009a88  lea     rcx, [rsp+530h+var_4B8]
0x180009a8d  mov     edi, [rsp+530h+var_4E4]
0x180009a91  mov     rsi, [rsp+530h+var_4C0]
0x180009a96  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009a9d  nop     dword ptr [rax+rax+00h]
0x180009aa2  mov     r9d, edi; unsigned int
0x180009aa5  mov     r8, rsi; unsigned __int16 *
0x180009aa8  mov     rdx, rax; unsigned __int16 *
0x180009aab  mov     rcx, r14; this
0x180009aae  call    ?Initialize@W3_SITE@@QEAAJPEBG0K@Z; W3_SITE::Initialize(ushort const *,ushort const *,ulong)
0x180009ab3  mov     edi, eax
0x180009ab5  test    eax, eax
0x180009ab7  js      short loc_180009B07
0x180009ab9  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009ac0  xor     r8d, r8d
0x180009ac3  mov     rdx, [rbx]
0x180009ac6  add     rcx, 520h
0x180009acd  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180009ad4  nop     dword ptr [rax+rax+00h]
0x180009ad9  test    eax, eax
0x180009adb  jnz     short loc_180009B17
0x180009add  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009ae4  xor     r8d, r8d
0x180009ae7  mov     rdx, [rbx]
0x180009aea  add     rcx, 4D8h
0x180009af1  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180009af8  nop     dword ptr [rax+rax+00h]
0x180009afd  jmp     short loc_180009B17
0x180009aff  mov     [rbx], r15
0x180009b02  mov     edi, 80070008h
0x180009b07  mov     rcx, [rbx]; this
0x180009b0a  test    rcx, rcx
0x180009b0d  jz      short loc_180009B17
0x180009b0f  call    ?DereferenceSiteInfo@W3_SITE@@QEAAXXZ; W3_SITE::DereferenceSiteInfo(void)
0x180009b14  mov     [rbx], r15
0x180009b17  mov     rcx, [rsp+530h+var_4E0]
0x180009b1c  test    rcx, rcx
0x180009b1f  jz      short loc_180009B32
0x180009b21  mov     rax, [rcx]
0x180009b24  mov     rax, [rax+10h]
0x180009b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b2d  mov     [rsp+530h+var_4E0], r15
0x180009b32  mov     rcx, [rsp+530h+var_4D8]
0x180009b37  test    rcx, rcx
0x180009b3a  jz      short loc_180009B4D
0x180009b3c  mov     rax, [rcx]
0x180009b3f  mov     rax, [rax+10h]
0x180009b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b48  mov     [rsp+530h+var_4D8], r15
0x180009b4d  mov     rcx, [rsp+530h+var_4D0]
0x180009b52  test    rcx, rcx
0x180009b55  jz      short loc_180009B68
0x180009b57  mov     rax, [rcx]
0x180009b5a  mov     rax, [rax+10h]
0x180009b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b63  mov     [rsp+530h+var_4D0], r15
0x180009b68  lea     rcx, [rbp+430h+var_480]
0x180009b6c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009b73  nop     dword ptr [rax+rax+00h]
0x180009b78  lea     rcx, [rsp+530h+var_4B8]
0x180009b7d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009b84  nop     dword ptr [rax+rax+00h]
0x180009b89  mov     eax, edi
0x180009b8b  mov     rdi, [rsp+530h+arg_10]
0x180009b93  jmp     loc_1800097C1
```
