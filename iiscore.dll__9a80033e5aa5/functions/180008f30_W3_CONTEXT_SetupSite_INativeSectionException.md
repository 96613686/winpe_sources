# W3_CONTEXT::SetupSite(INativeSectionException * *)

- ea: `0x180008f30`
- end: `0x1800093ab`
- name: `?SetupSite@W3_CONTEXT@@QEAAJPEAPEAVINativeSectionException@@@Z`
- size: `1147`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800094c4`

## callees

- `0x180008f30`
- `0x180016700`
- `0x180019558`
- `0x18001f410`
- `0x18002bf30`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800091a5`
- `msvcrt!_wcsupr` at `0x1800091a5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009020`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000902b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000938b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009396`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009020`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000902b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000938b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009396`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800090c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009118`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000919c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800091cb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009201`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800092c7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800090c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009118`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000919c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800091cb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009201`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800092c7`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800090fb`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800090fb`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180009191`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180009191`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800091b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800091b6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008f84`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fa9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008f84`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008fa9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800091d8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800091d8`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800092f8`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180009316`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800092f8`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180009316`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000900a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000900a`

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
0x180008f30  push    rbp
0x180008f32  push    rbx
0x180008f33  push    rsi
0x180008f34  push    r14
0x180008f36  push    r15
0x180008f38  lea     rbp, [rsp-410h]
0x180008f40  sub     rsp, 510h
0x180008f47  mov     rax, cs:__security_cookie
0x180008f4e  xor     rax, rsp
0x180008f51  mov     [rbp+430h+var_30], rax
0x180008f58  mov     r14, rdx
0x180008f5b  mov     rbx, rcx
0x180008f5e  xor     edx, edx; Val
0x180008f60  lea     rcx, [rbp+430h+var_240]; void *
0x180008f67  mov     r8d, 208h; Size
0x180008f6d  call    memset_0
0x180008f72  mov     r8d, 104h
0x180008f78  lea     rdx, [rbp+430h+var_240]
0x180008f7f  lea     rcx, [rsp+530h+var_4B8]
0x180008f84  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008f8a  xor     edx, edx; Val
0x180008f8c  lea     rcx, [rbp+430h+var_440]; void *
0x180008f90  mov     r8d, 200h; Size
0x180008f96  call    memset_0
0x180008f9b  mov     r8d, 100h
0x180008fa1  lea     rdx, [rbp+430h+var_440]
0x180008fa5  lea     rcx, [rbp+430h+var_480]
0x180008fa9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008faf  mov     rax, [rbx+30h]
0x180008fb3  xor     r15d, r15d
0x180008fb6  mov     [rsp+530h+var_4E8], 104h
0x180008fbe  mov     [rsp+530h+var_4D0], r15
0x180008fc3  mov     [rsp+530h+var_4D8], r15
0x180008fc8  mov     [rsp+530h+var_4E0], r15
0x180008fcd  mov     [rsp+530h+var_4C0], r15
0x180008fd2  mov     [rsp+530h+var_4E4], r15d
0x180008fd7  mov     rcx, [rax+28h]
0x180008fdb  mov     rsi, [rcx+18h]
0x180008fdf  shr     rsi, 20h
0x180008fe3  add     rbx, 1F88h
0x180008fea  jz      short loc_180009051
0x180008fec  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180008ff3  lea     r8, [rsp+530h+var_4C8]
0x180008ff8  add     rcx, 4D8h
0x180008fff  mov     [rbx], r15
0x180009002  mov     rdx, rsi
0x180009005  mov     [rsp+530h+var_4C8], r15
0x18000900a  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180009010  mov     rcx, [rsp+530h+var_4C8]
0x180009015  mov     [rbx], rcx
0x180009018  test    eax, eax
0x18000901a  jnz     short loc_180009051
0x18000901c  lea     rcx, [rbp+430h+var_480]
0x180009020  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009026  lea     rcx, [rsp+530h+var_4B8]
0x18000902b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009031  xor     eax, eax
0x180009033  mov     rcx, [rbp+430h+var_30]
0x18000903a  xor     rcx, rsp; StackCookie
0x18000903d  call    __security_check_cookie
0x180009042  add     rsp, 510h
0x180009049  pop     r15
0x18000904b  pop     r14
0x18000904d  pop     rsi
0x18000904e  pop     rbx
0x18000904f  pop     rbp
0x180009050  retn
0x180009051  mov     ecx, 2A0h; Size
0x180009056  mov     [rsp+530h+arg_10], rdi
0x18000905e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009063  test    rax, rax
0x180009066  jz      loc_18000931E
0x18000906c  mov     edx, esi; unsigned int
0x18000906e  mov     rcx, rax; this
0x180009071  call    ??0W3_SITE@@QEAA@K@Z; W3_SITE::W3_SITE(ulong)
0x180009076  mov     [rbx], rax
0x180009079  test    rax, rax
0x18000907c  jz      loc_180009321
0x180009082  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009089  lea     rdx, [rsp+530h+var_4F0]
0x18000908e  mov     [rsp+530h+var_4F0], r15
0x180009093  mov     rcx, [rax+5D8h]
0x18000909a  mov     rax, [rcx]
0x18000909d  mov     rax, [rax+38h]
0x1800090a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a6  mov     edi, eax
0x1800090a8  test    eax, eax
0x1800090aa  js      loc_180009326
0x1800090b0  mov     rax, [rsp+530h+var_4F0]
0x1800090b5  mov     rcx, [rax]
0x1800090b8  mov     rdi, [rcx+18h]
0x1800090bc  lea     rcx, [rsp+530h+var_4B8]
0x1800090c1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800090c7  mov     rcx, [rsp+530h+var_4F0]
0x1800090cc  lea     r9, [rsp+530h+var_4E8]
0x1800090d1  mov     r8, rax
0x1800090d4  mov     [rsp+530h+var_510], r14
0x1800090d9  mov     rax, rdi
0x1800090dc  mov     edx, esi
0x1800090de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e3  mov     edi, eax
0x1800090e5  test    eax, eax
0x1800090e7  jns     short loc_180009156
0x1800090e9  cmp     eax, 8007007Ah
0x1800090ee  jnz     short loc_180009140
0x1800090f0  mov     edx, [rsp+530h+var_4E8]
0x1800090f4  lea     rcx, [rsp+530h+var_4B8]
0x1800090f9  add     edx, edx
0x1800090fb  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180009101  mov     edi, eax
0x180009103  test    eax, eax
0x180009105  js      short loc_180009140
0x180009107  mov     rax, [rsp+530h+var_4F0]
0x18000910c  mov     rcx, [rax]
0x18000910f  mov     rdi, [rcx+18h]
0x180009113  lea     rcx, [rsp+530h+var_4B8]
0x180009118  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000911e  mov     rcx, [rsp+530h+var_4F0]
0x180009123  lea     r9, [rsp+530h+var_4E8]
0x180009128  mov     r8, rax
0x18000912b  mov     [rsp+530h+var_510], r14
0x180009130  mov     rax, rdi
0x180009133  mov     edx, esi
0x180009135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000913a  mov     edi, eax
0x18000913c  test    eax, eax
0x18000913e  jns     short loc_180009156
0x180009140  mov     rcx, [rsp+530h+var_4F0]
0x180009145  mov     rax, [rcx]
0x180009148  mov     rax, [rax+10h]
0x18000914c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009151  jmp     loc_180009326
0x180009156  mov     rcx, [rsp+530h+var_4F0]
0x18000915b  lea     r8, [rsp+530h+var_4D8]
0x180009160  mov     r9, r14
0x180009163  mov     edx, esi
0x180009165  mov     rax, [rcx]
0x180009168  mov     rax, [rax+20h]
0x18000916c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009171  mov     rcx, [rsp+530h+var_4F0]
0x180009176  mov     edi, eax
0x180009178  mov     rax, [rcx]
0x18000917b  mov     rax, [rax+10h]
0x18000917f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009184  test    edi, edi
0x180009186  js      loc_180009326
0x18000918c  lea     rcx, [rsp+530h+var_4B8]
0x180009191  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180009197  lea     rcx, [rsp+530h+var_4B8]
0x18000919c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800091a2  mov     rcx, rax; String
0x1800091a5  call    cs:__imp__wcsupr
0x1800091ab  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x1800091b2  lea     rcx, [rbp+430h+var_480]
0x1800091b6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800091bc  mov     edi, eax
0x1800091be  test    eax, eax
0x1800091c0  js      loc_180009326
0x1800091c6  lea     rcx, [rsp+530h+var_4B8]
0x1800091cb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800091d1  mov     rdx, rax
0x1800091d4  lea     rcx, [rbp+430h+var_480]
0x1800091d8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800091de  mov     edi, eax
0x1800091e0  test    eax, eax
0x1800091e2  js      loc_180009326
0x1800091e8  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800091ef  lea     rcx, [rbp+430h+var_480]
0x1800091f3  mov     rsi, [rax+5D8h]
0x1800091fa  mov     rax, [rsi]
0x1800091fd  mov     rdi, [rax+18h]
0x180009201  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009207  mov     [rsp+530h+var_508], r15
0x18000920c  lea     r9, [rsp+530h+var_4D0]
0x180009211  mov     r8, rax
0x180009214  mov     [rsp+530h+var_510], r14
0x180009219  mov     rax, rdi
0x18000921c  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x180009223  mov     rcx, rsi
0x180009226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922b  mov     edi, eax
0x18000922d  test    eax, eax
0x18000922f  js      loc_180009326
0x180009235  mov     rcx, [rsp+530h+var_4D0]
0x18000923a  lea     r8, [rsp+530h+var_4C0]
0x18000923f  xor     r9d, r9d
0x180009242  mov     [rsp+530h+var_510], r15
0x180009247  lea     rdx, aAlternatehostn; "alternateHostName"
0x18000924e  mov     rax, [rcx]
0x180009251  mov     rax, [rax+40h]
0x180009255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000925a  mov     edi, eax
0x18000925c  test    eax, eax
0x18000925e  js      loc_180009326
0x180009264  mov     rcx, [rsp+530h+var_4D8]
0x180009269  lea     r8, [rsp+530h+var_4E0]
0x18000926e  lea     rdx, aLimits; "limits"
0x180009275  mov     rax, [rcx]
0x180009278  mov     rax, [rax+20h]
0x18000927c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009281  mov     edi, eax
0x180009283  test    eax, eax
0x180009285  js      loc_180009326
0x18000928b  mov     rcx, [rsp+530h+var_4E0]
0x180009290  lea     r8, [rsp+530h+var_4E4]
0x180009295  xor     r9d, r9d
0x180009298  mov     [rsp+530h+var_510], r15
0x18000929d  lea     rdx, aMaxurlsegments; "maxUrlSegments"
0x1800092a4  mov     rax, [rcx]
0x1800092a7  mov     rax, [rax+30h]
0x1800092ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b0  mov     edi, eax
0x1800092b2  test    eax, eax
0x1800092b4  js      short loc_180009326
0x1800092b6  mov     r14, [rbx]
0x1800092b9  lea     rcx, [rsp+530h+var_4B8]
0x1800092be  mov     edi, [rsp+530h+var_4E4]
0x1800092c2  mov     rsi, [rsp+530h+var_4C0]
0x1800092c7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800092cd  mov     r9d, edi; unsigned int
0x1800092d0  mov     r8, rsi; unsigned __int16 *
0x1800092d3  mov     rdx, rax; unsigned __int16 *
0x1800092d6  mov     rcx, r14; this
0x1800092d9  call    ?Initialize@W3_SITE@@QEAAJPEBG0K@Z; W3_SITE::Initialize(ushort const *,ushort const *,ulong)
0x1800092de  mov     edi, eax
0x1800092e0  test    eax, eax
0x1800092e2  js      short loc_180009326
0x1800092e4  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800092eb  xor     r8d, r8d
0x1800092ee  mov     rdx, [rbx]
0x1800092f1  add     rcx, 520h
0x1800092f8  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800092fe  test    eax, eax
0x180009300  jnz     short loc_180009336
0x180009302  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009309  xor     r8d, r8d
0x18000930c  mov     rdx, [rbx]
0x18000930f  add     rcx, 4D8h
0x180009316  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000931c  jmp     short loc_180009336
0x18000931e  mov     [rbx], r15
0x180009321  mov     edi, 80070008h
0x180009326  mov     rcx, [rbx]; this
0x180009329  test    rcx, rcx
0x18000932c  jz      short loc_180009336
0x18000932e  call    ?DereferenceSiteInfo@W3_SITE@@QEAAXXZ; W3_SITE::DereferenceSiteInfo(void)
0x180009333  mov     [rbx], r15
0x180009336  mov     rcx, [rsp+530h+var_4E0]
0x18000933b  test    rcx, rcx
0x18000933e  jz      short loc_180009351
0x180009340  mov     rax, [rcx]
0x180009343  mov     rax, [rax+10h]
0x180009347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934c  mov     [rsp+530h+var_4E0], r15
0x180009351  mov     rcx, [rsp+530h+var_4D8]
0x180009356  test    rcx, rcx
0x180009359  jz      short loc_18000936C
0x18000935b  mov     rax, [rcx]
0x18000935e  mov     rax, [rax+10h]
0x180009362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009367  mov     [rsp+530h+var_4D8], r15
0x18000936c  mov     rcx, [rsp+530h+var_4D0]
0x180009371  test    rcx, rcx
0x180009374  jz      short loc_180009387
0x180009376  mov     rax, [rcx]
0x180009379  mov     rax, [rax+10h]
0x18000937d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009382  mov     [rsp+530h+var_4D0], r15
0x180009387  lea     rcx, [rbp+430h+var_480]
0x18000938b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009391  lea     rcx, [rsp+530h+var_4B8]
0x180009396  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000939c  mov     eax, edi
0x18000939e  mov     rdi, [rsp+530h+arg_10]
0x1800093a6  jmp     loc_180009033
```
