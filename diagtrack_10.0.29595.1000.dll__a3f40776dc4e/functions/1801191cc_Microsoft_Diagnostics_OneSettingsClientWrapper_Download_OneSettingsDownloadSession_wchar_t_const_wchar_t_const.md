# Microsoft::Diagnostics::OneSettingsClientWrapper::Download(OneSettingsDownloadSession *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1801191cc`
- end: `0x1801195aa`
- name: `?Download@OneSettingsClientWrapper@Diagnostics@Microsoft@@QEAAJPEAUOneSettingsDownloadSession@@PEB_W11@Z`
- size: `990`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::OneSettingsClientWrapper *__hidden this, struct OneSettingsDownloadSession *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801583ec`

## callees

- `0x18002b318`
- `0x180064e8c`
- `0x1800a8ed4`
- `0x18010e55c`
- `0x18010f9b8`
- `0x1801191cc`

## import_xrefs

- `OneSettingsClient!OneSettingsSetConfigHandleProperty` at `0x180119295`
- `OneSettingsClient!OneSettingsSetConfigHandleProperty` at `0x180119295`
- `OneSettingsClient!OneSettingsSetConfigBoolProperty` at `0x1801193bc`
- `OneSettingsClient!OneSettingsSetConfigBoolProperty` at `0x1801193bc`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x1801194e4`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x18011936b`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x18011936b`
- `OneSettingsClient!OneSettingsSetConfigDwordProperty` at `0x180119243`
- `OneSettingsClient!OneSettingsSetConfigDwordProperty` at `0x180119243`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x18011945a`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x18011945a`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x180119584`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x180119205`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x180119205`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::OneSettingsClientWrapper::Download(
        Microsoft::Diagnostics::OneSettingsClientWrapper *this,
        struct OneSettingsDownloadSession *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  _QWORD *v5; // rsi
  int DownloadConfig; // ebx
  __int64 *v11; // rbx
  __int64 *v12; // rbx
  int v13; // r14d
  __int64 **v14; // rcx
  __int64 *k; // rax
  __int64 *v16; // rbx
  __int64 **v17; // rcx
  __int64 *n; // rax
  __int64 *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 *v26; // rdi
  const wchar_t *v27; // r9
  __int64 v29; // rdx
  __int64 **v30; // rcx
  __int64 *i; // rax
  __int64 *ii; // rcx
  __int64 *j; // rcx
  __int64 **v34; // rcx
  __int64 *jj; // rax
  __int64 v36; // rdx
  __int64 *kk; // rcx
  __int64 *m; // rcx
  int v39[2]; // [rsp+20h] [rbp-28h]
  __int64 v40; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v41[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  __int64 v43; // [rsp+90h] [rbp+48h] BYREF

  v5 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    v43 = *((_QWORD *)this + 1);
    wil::last_error_context::last_error_context((wil::last_error_context *)v41);
    v40 = OneSettingsFreeDownloadConfig;
    wistd::invoke<void * (*)(void *),void * &>(&v40, &v43);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v41);
  }
  *v5 = 0;
  DownloadConfig = OneSettingsCreateDownloadConfig(v5);
  if ( DownloadConfig < 0 )
  {
    v36 = 132;
  }
  else
  {
    v11 = (__int64 *)**((_QWORD **)this + 3);
    while ( !*((_BYTE *)v11 + 25) )
    {
      if ( *((_BYTE *)v11 + 33) )
      {
        v13 = OneSettingsSetConfigBoolProperty(*v5, *((unsigned int *)v11 + 7), *((unsigned __int8 *)v11 + 32));
        if ( v13 < 0 )
        {
          v29 = 140;
LABEL_30:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
            (const char *)(unsigned int)v13,
            v39[0]);
          return (unsigned int)v13;
        }
      }
      v30 = (__int64 **)v11[2];
      if ( *((_BYTE *)v30 + 25) )
      {
        for ( i = (__int64 *)v11[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v11 = i;
        v11 = i;
      }
      else
      {
        v11 = (__int64 *)v11[2];
        for ( j = *v30; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v11 = j;
      }
    }
    v12 = (__int64 *)**((_QWORD **)this + 5);
    while ( !*((_BYTE *)v12 + 25) )
    {
      if ( *((_BYTE *)v12 + 36) )
      {
        v13 = OneSettingsSetConfigDwordProperty(*v5, *((unsigned int *)v12 + 7), *((unsigned int *)v12 + 8));
        if ( v13 < 0 )
        {
          v29 = 150;
          goto LABEL_30;
        }
      }
      v14 = (__int64 **)v12[2];
      if ( *((_BYTE *)v14 + 25) )
      {
        for ( k = (__int64 *)v12[1]; !*((_BYTE *)k + 25) && v12 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v12 = k;
        v12 = k;
      }
      else
      {
        v12 = (__int64 *)v12[2];
        for ( m = *v14; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v12 = m;
      }
    }
    v16 = (__int64 *)**((_QWORD **)this + 7);
    while ( !*((_BYTE *)v16 + 25) )
    {
      if ( *((_BYTE *)v16 + 48) )
      {
        v13 = OneSettingsSetConfigHandleProperty(*v5, *((unsigned int *)v16 + 8), v16[5]);
        if ( v13 < 0 )
        {
          v29 = 160;
          goto LABEL_30;
        }
      }
      v17 = (__int64 **)v16[2];
      if ( *((_BYTE *)v17 + 25) )
      {
        for ( n = (__int64 *)v16[1]; !*((_BYTE *)n + 25) && v16 == (__int64 *)n[2]; n = (__int64 *)n[1] )
          v16 = n;
        v16 = n;
      }
      else
      {
        v16 = (__int64 *)v16[2];
        for ( ii = *v17; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
          v16 = ii;
      }
    }
    v19 = (__int64 *)**((_QWORD **)this + 9);
    while ( !*((_BYTE *)v19 + 25) )
    {
      if ( v19[6] )
      {
        v13 = OneSettingsSetConfigWideStringProperty(*v5, *((unsigned int *)v19 + 8), v19[5]);
        if ( v13 < 0 )
        {
          v29 = 170;
          goto LABEL_30;
        }
      }
      v34 = (__int64 **)v19[2];
      if ( *((_BYTE *)v34 + 25) )
      {
        for ( jj = (__int64 *)v19[1]; !*((_BYTE *)jj + 25) && v19 == (__int64 *)jj[2]; jj = (__int64 *)jj[1] )
          v19 = jj;
        v19 = jj;
      }
      else
      {
        v19 = (__int64 *)v19[2];
        for ( kk = *v34; !*((_BYTE *)kk + 25); kk = (__int64 *)*kk )
          v19 = kk;
      }
    }
    *((_BYTE *)this + 92) = 0;
    *((_BYTE *)this + 100) = 0;
    *((_QWORD *)this + 16) = &byte_180398499;
    *((_QWORD *)this + 17) = 0;
    v20 = std::_WChar_traits<wchar_t>::length(&Src);
    *((_QWORD *)this + 18) = v21;
    *((_QWORD *)this + 19) = v20;
    v22 = std::_WChar_traits<wchar_t>::length(v21);
    *((_QWORD *)this + 20) = v23;
    *((_QWORD *)this + 21) = v22;
    v24 = std::_WChar_traits<wchar_t>::length(v23);
    *((_QWORD *)this + 22) = v25;
    *((_QWORD *)this + 23) = v24;
    v26 = (__int64 *)((char *)this + 16);
    if ( *v26 )
    {
      v43 = *v26;
      wil::last_error_context::last_error_context((wil::last_error_context *)&v40);
      v41[0] = OneSettingsFreeDownloadResponse;
      wistd::invoke<void * (*)(void *),void * &>(v41, &v43);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v40);
    }
    v27 = a5;
    *v26 = 0;
    *(_QWORD *)v39 = *v5;
    DownloadConfig = OneSettingsDownloadEndpoint(a2, a3, a4, v27);
    if ( DownloadConfig >= 0 )
      return 0;
    v36 = 181;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v36,
    (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
    (const char *)(unsigned int)DownloadConfig,
    v39[0]);
  return (unsigned int)DownloadConfig;
}

```

## disassembly

```asm
0x1801191cc  push    rbp
0x1801191ce  push    rbx
0x1801191cf  push    rsi
0x1801191d0  push    rdi
0x1801191d1  push    r12
0x1801191d3  push    r13
0x1801191d5  push    r14
0x1801191d7  push    r15
0x1801191d9  mov     rbp, rsp
0x1801191dc  sub     rsp, 48h
0x1801191e0  lea     rsi, [rcx+8]
0x1801191e4  xor     r14d, r14d
0x1801191e7  mov     rax, [rsi]
0x1801191ea  mov     r15, r9
0x1801191ed  mov     r12, r8
0x1801191f0  mov     r13, rdx
0x1801191f3  mov     rdi, rcx
0x1801191f6  test    rax, rax
0x1801191f9  jnz     loc_1801194D7
0x1801191ff  mov     rcx, rsi
0x180119202  mov     [rsi], r14
0x180119205  call    cs:__imp_OneSettingsCreateDownloadConfig
0x18011920b  mov     ebx, eax
0x18011920d  test    eax, eax
0x18011920f  js      loc_18011950A
0x180119215  mov     rbx, [rdi+18h]
0x180119219  mov     rbx, [rbx]
0x18011921c  cmp     [rbx+19h], r14b
0x180119220  jz      loc_1801193AB
0x180119226  mov     rbx, [rdi+28h]
0x18011922a  mov     rbx, [rbx]
0x18011922d  cmp     [rbx+19h], r14b
0x180119231  jnz     short loc_180119278
0x180119233  cmp     [rbx+24h], r14b
0x180119237  jz      short loc_180119257
0x180119239  mov     r8d, [rbx+20h]
0x18011923d  mov     edx, [rbx+1Ch]
0x180119240  mov     rcx, [rsi]
0x180119243  call    cs:__imp_OneSettingsSetConfigDwordProperty
0x180119249  mov     r14d, eax
0x18011924c  test    eax, eax
0x18011924e  js      loc_1801193FB
0x180119254  xor     r14d, r14d
0x180119257  mov     rcx, [rbx+10h]
0x18011925b  cmp     [rcx+19h], r14b
0x18011925f  jz      loc_180119531
0x180119265  mov     rax, [rbx+8]
0x180119269  cmp     [rax+19h], r14b
0x18011926d  jz      loc_18011951B
0x180119273  mov     rbx, rax
0x180119276  jmp     short loc_18011922D
0x180119278  mov     rbx, [rdi+38h]
0x18011927c  mov     rbx, [rbx]
0x18011927f  cmp     [rbx+19h], r14b
0x180119283  jnz     short loc_1801192D0
0x180119285  cmp     [rbx+30h], r14b
0x180119289  jz      short loc_1801192A9
0x18011928b  mov     r8, [rbx+28h]
0x18011928f  mov     edx, [rbx+20h]
0x180119292  mov     rcx, [rsi]
0x180119295  call    cs:__imp_OneSettingsSetConfigHandleProperty
0x18011929b  mov     r14d, eax
0x18011929e  test    eax, eax
0x1801192a0  js      loc_18011937F
0x1801192a6  xor     r14d, r14d
0x1801192a9  mov     rcx, [rbx+10h]
0x1801192ad  cmp     [rcx+19h], r14b
0x1801192b1  jz      loc_180119402
0x1801192b7  mov     rax, [rbx+8]
0x1801192bb  cmp     [rax+19h], r14b
0x1801192bf  jnz     short loc_1801192CB
0x1801192c1  cmp     rbx, [rax+10h]
0x1801192c5  jz      loc_180119555
0x1801192cb  mov     rbx, rax
0x1801192ce  jmp     short loc_18011927F
0x1801192d0  mov     rbx, [rdi+48h]
0x1801192d4  mov     rbx, [rbx]
0x1801192d7  cmp     [rbx+19h], r14b
0x1801192db  jz      loc_18011944A
0x1801192e1  mov     [rdi+5Ch], r14b
0x1801192e5  lea     rax, byte_180398499
0x1801192ec  mov     [rdi+64h], r14b
0x1801192f0  lea     rcx, Src
0x1801192f7  mov     [rdi+80h], rax
0x1801192fe  mov     [rdi+88h], r14
0x180119305  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18011930a  mov     [rdi+90h], rcx
0x180119311  mov     [rdi+98h], rax
0x180119318  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18011931d  mov     [rdi+0A0h], rcx
0x180119324  mov     [rdi+0A8h], rax
0x18011932b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180119330  mov     [rdi+0B0h], rcx
0x180119337  mov     [rdi+0B8h], rax
0x18011933e  add     rdi, 10h
0x180119342  mov     rax, [rdi]
0x180119345  test    rax, rax
0x180119348  jnz     loc_180119577
0x18011934e  mov     r9, [rbp+arg_20]
0x180119352  mov     r8, r15
0x180119355  mov     [rdi], r14
0x180119358  mov     rdx, r12
0x18011935b  mov     rax, [rsi]
0x18011935e  mov     rcx, r13
0x180119361  mov     [rsp+48h+var_20], rdi
0x180119366  mov     qword ptr [rsp+48h+var_28], rax; int
0x18011936b  call    cs:__imp_OneSettingsDownloadEndpoint
0x180119371  mov     ebx, eax
0x180119373  test    eax, eax
0x180119375  js      loc_180119494
0x18011937b  xor     eax, eax
0x18011937d  jmp     short loc_18011939A
0x18011937f  mov     edx, 0A0h; void *
0x180119384  mov     rcx, [rbp+40h]; this
0x180119388  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x18011938f  mov     r9d, r14d; char *
0x180119392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119397  mov     eax, r14d
0x18011939a  add     rsp, 48h
0x18011939e  pop     r15
0x1801193a0  pop     r14
0x1801193a2  pop     r13
0x1801193a4  pop     r12
0x1801193a6  pop     rdi
0x1801193a7  pop     rsi
0x1801193a8  pop     rbx
0x1801193a9  pop     rbp
0x1801193aa  retn
0x1801193ab  cmp     [rbx+21h], r14b
0x1801193af  jz      short loc_1801193D0
0x1801193b1  movzx   r8d, byte ptr [rbx+20h]
0x1801193b6  mov     edx, [rbx+1Ch]
0x1801193b9  mov     rcx, [rsi]
0x1801193bc  call    cs:__imp_OneSettingsSetConfigBoolProperty
0x1801193c2  mov     r14d, eax
0x1801193c5  test    eax, eax
0x1801193c7  js      loc_180119511
0x1801193cd  xor     r14d, r14d
0x1801193d0  mov     rcx, [rbx+10h]
0x1801193d4  cmp     [rcx+19h], r14b
0x1801193d8  jz      short loc_180119426
0x1801193da  mov     rax, [rbx+8]
0x1801193de  cmp     [rax+19h], r14b
0x1801193e2  jnz     short loc_1801193F3
0x1801193e4  cmp     rbx, [rax+10h]
0x1801193e8  jnz     short loc_1801193F3
0x1801193ea  mov     rbx, rax
0x1801193ed  mov     rax, [rax+8]
0x1801193f1  jmp     short loc_1801193DE
0x1801193f3  mov     rbx, rax
0x1801193f6  jmp     loc_18011921C
0x1801193fb  mov     edx, 96h
0x180119400  jmp     short loc_180119384
0x180119402  mov     rbx, rcx
0x180119405  mov     rcx, [rcx]
0x180119408  cmp     [rcx+19h], r14b
0x18011940c  jnz     loc_18011927F
0x180119412  mov     rax, [rcx]
0x180119415  mov     rbx, rcx
0x180119418  mov     rcx, rax
0x18011941b  cmp     [rax+19h], r14b
0x18011941f  jz      short loc_180119412
0x180119421  jmp     loc_18011927F
0x180119426  mov     rbx, rcx
0x180119429  mov     rcx, [rcx]
0x18011942c  cmp     [rcx+19h], r14b
0x180119430  jnz     loc_18011921C
0x180119436  mov     rax, [rcx]
0x180119439  mov     rbx, rcx
0x18011943c  mov     rcx, rax
0x18011943f  cmp     [rax+19h], r14b
0x180119443  jz      short loc_180119436
0x180119445  jmp     loc_18011921C
0x18011944a  cmp     [rbx+30h], r14
0x18011944e  jz      short loc_18011946E
0x180119450  mov     r8, [rbx+28h]
0x180119454  mov     edx, [rbx+20h]
0x180119457  mov     rcx, [rsi]
0x18011945a  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x180119460  mov     r14d, eax
0x180119463  test    eax, eax
0x180119465  js      loc_18011956D
0x18011946b  xor     r14d, r14d
0x18011946e  mov     rcx, [rbx+10h]
0x180119472  cmp     [rcx+19h], r14b
0x180119476  jz      short loc_1801194B3
0x180119478  mov     rax, [rbx+8]
0x18011947c  cmp     [rax+19h], r14b
0x180119480  jnz     short loc_18011948C
0x180119482  cmp     rbx, [rax+10h]
0x180119486  jz      loc_180119561
0x18011948c  mov     rbx, rax
0x18011948f  jmp     loc_1801192D7
0x180119494  mov     edx, 0B5h; void *
0x180119499  mov     rcx, [rbp+40h]; this
0x18011949d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x1801194a4  mov     r9d, ebx; char *
0x1801194a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801194ac  mov     eax, ebx
0x1801194ae  jmp     loc_18011939A
0x1801194b3  mov     rbx, rcx
0x1801194b6  mov     rcx, [rcx]
0x1801194b9  cmp     [rcx+19h], r14b
0x1801194bd  jnz     loc_1801192D7
0x1801194c3  mov     rax, [rcx]
0x1801194c6  mov     rbx, rcx
0x1801194c9  mov     rcx, rax
0x1801194cc  cmp     [rax+19h], r14b
0x1801194d0  jz      short loc_1801194C3
0x1801194d2  jmp     loc_1801192D7
0x1801194d7  lea     rcx, [rbp+var_10]; this
0x1801194db  mov     [rbp+arg_0], rax
0x1801194df  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801194e4  mov     rax, cs:__imp_OneSettingsFreeDownloadConfig
0x1801194eb  lea     rdx, [rbp+arg_0]
0x1801194ef  lea     rcx, [rbp+var_18]
0x1801194f3  mov     [rbp+var_18], rax
0x1801194f7  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1801194fc  lea     rcx, [rbp+var_10]; this
0x180119500  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180119505  jmp     loc_1801191FF
0x18011950a  mov     edx, 84h
0x18011950f  jmp     short loc_180119499
0x180119511  mov     edx, 8Ch
0x180119516  jmp     loc_180119384
0x18011951b  cmp     rbx, [rax+10h]
0x18011951f  jnz     loc_180119273
0x180119525  mov     rbx, rax
0x180119528  mov     rax, [rax+8]
0x18011952c  jmp     loc_180119269
0x180119531  mov     rbx, rcx
0x180119534  mov     rcx, [rcx]
0x180119537  cmp     [rcx+19h], r14b
0x18011953b  jnz     loc_18011922D
0x180119541  mov     rax, [rcx]
0x180119544  mov     rbx, rcx
0x180119547  mov     rcx, rax
0x18011954a  cmp     [rax+19h], r14b
0x18011954e  jz      short loc_180119541
0x180119550  jmp     loc_18011922D
0x180119555  mov     rbx, rax
0x180119558  mov     rax, [rax+8]
0x18011955c  jmp     loc_1801192BB
0x180119561  mov     rbx, rax
0x180119564  mov     rax, [rax+8]
0x180119568  jmp     loc_18011947C
0x18011956d  mov     edx, 0AAh
0x180119572  jmp     loc_180119384
0x180119577  lea     rcx, [rbp+var_18]; this
0x18011957b  mov     [rbp+arg_0], rax
0x18011957f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180119584  mov     rax, cs:__imp_OneSettingsFreeDownloadResponse
0x18011958b  lea     rdx, [rbp+arg_0]
0x18011958f  lea     rcx, [rbp+var_10]
0x180119593  mov     [rbp+var_10], rax
0x180119597  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x18011959c  lea     rcx, [rbp+var_18]; this
0x1801195a0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801195a5  jmp     loc_18011934E
```
