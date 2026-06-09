# FTP_METADATA::InitializeUrlAuthorizationConfig(IErrorInfo * *)

- ea: `0x1800150d0`
- end: `0x18001554d`
- name: `?InitializeUrlAuthorizationConfig@FTP_METADATA@@QEAAJPEAPEAUIErrorInfo@@@Z`
- size: `1149`
- prototype: `int(FTP_METADATA *__hidden this, struct IErrorInfo **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014288`

## callees

- `0x180001210`
- `0x180001250`
- `0x180014094`
- `0x1800150d0`
- `0x180024834`
- `0x18002b0c4`
- `0x18002b488`
- `0x18002b5bc`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180015415`
- `OLEAUT32!__imp_SysFreeString` at `0x18001542a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001548c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800154a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180015415`
- `OLEAUT32!__imp_SysFreeString` at `0x18001542a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001548c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800154a1`
- `OLEAUT32!__imp_VariantInit` at `0x18001515e`
- `OLEAUT32!__imp_VariantInit` at `0x18001515e`
- `OLEAUT32!__imp_VariantClear` at `0x18001547c`
- `OLEAUT32!__imp_VariantClear` at `0x18001547c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800152f0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800152f0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180015143`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180015143`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015319`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015334`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015319`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180015334`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001551d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001551d`

## string_xrefs

- `0x180015329`: `Write`
- `0x180015188`: `system.ftpServer/security/authorization`
- `0x180015255`: `accessType`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_METADATA::InitializeUrlAuthorizationConfig(
        const unsigned __int16 **this,
        struct IErrorInfo **a2)
{
  struct IAppHostAdminManager *v4; // r12
  int Section; // edi
  unsigned int i; // esi
  int v7; // eax
  URL_AUTHZ_RULE_ENTRY *v8; // rax
  URL_AUTHZ_RULE_ENTRY *v9; // rbx
  char *v10; // rax
  char **v11; // rcx
  __int64 v12; // rcx
  struct IAppHostElement *v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v16; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v19; // [rsp+50h] [rbp-B0h] BYREF
  struct IAppHostElement *v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  URL_AUTHZ_RULE_ENTRY *v23; // [rsp+80h] [rbp-80h]
  VARIANTARG v24; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[32]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v26; // [rsp+D0h] [rbp-30h]
  int v27; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v28[32]; // [rsp+F0h] [rbp-10h] BYREF

  v20 = 0;
  v21 = 0;
  v14 = 0;
  v17 = 0;
  bstrString = 0;
  v19 = 0;
  v15 = 0;
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v25, v28, 0x20u);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 24LL))(g_pFtpServer);
  Section = Config_GetSection(v4, L"system.ftpServer/security/authorization", this[6], &v20, a2);
  if ( Section >= 0 )
  {
    Section = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))v20->lpVtbl->get_Collection)(v20, &v21);
    if ( Section >= 0 )
    {
      ((void (__fastcall *)(struct IAppHostElement *))v20->lpVtbl->Release)(v20);
      v20 = 0;
      Section = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v17);
      if ( Section >= 0 )
      {
        for ( i = 0; i < v17; ++i )
        {
          v16 = 0;
          pvarg.vt = 19;
          pvarg.lVal = i;
          v24 = pvarg;
          Section = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v21 + 32LL))(
                      v21,
                      &v24,
                      &v14);
          if ( Section < 0 )
            break;
          Section = Config_GetDWORDProperty(v14, L"accessType", &v16);
          if ( Section < 0 )
            break;
          Section = Config_GetStringProperty(v14, L"users", &bstrString);
          if ( Section < 0 )
            break;
          Section = Config_GetStringProperty(v14, L"roles", &v19);
          if ( Section < 0 )
            break;
          Section = Config_GetDWORDProperty(v14, L"permissions", &v15);
          if ( Section < 0 )
            break;
          *v26 = 0;
          v7 = 0;
          v27 = 0;
          if ( (v15 & 1) != 0 )
          {
            Section = STRU::Copy((STRU *)v25, L"Read");
            if ( Section < 0 )
              break;
            v7 = v27;
          }
          if ( (v15 & 2) != 0 )
          {
            if ( v7 )
            {
              Section = STRU::Append((STRU *)v25, L",");
              if ( Section < 0 )
                break;
            }
            Section = STRU::Append((STRU *)v25, L"Write");
            if ( Section < 0 )
              break;
          }
          v8 = (URL_AUTHZ_RULE_ENTRY *)operator new(0x60u);
          v9 = v8;
          v23 = v8;
          if ( !v8 )
          {
            Section = -2147024888;
            break;
          }
          *((_DWORD *)v8 + 5) = 2;
          *((_QWORD *)v8 + 3) = 0;
          *((_DWORD *)v8 + 8) = 0;
          *((_QWORD *)v8 + 5) = 0;
          *((_DWORD *)v8 + 12) = 0;
          *((_DWORD *)v8 + 13) = 0;
          *((_QWORD *)v8 + 7) = 0;
          *((_DWORD *)v8 + 16) = 0;
          *((_QWORD *)v8 + 9) = 0;
          *((_QWORD *)v8 + 10) = 0;
          *((_DWORD *)v8 + 22) = 0;
          *((_QWORD *)v8 + 1) = 0;
          *(_QWORD *)v8 = 0;
          *((_DWORD *)v8 + 4) = 1163018581;
          Section = URL_AUTHZ_RULE_ENTRY::InitializeInstance(v8, v16, bstrString, v19, v26);
          if ( Section < 0 )
          {
            URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(v9);
            operator delete(v9);
            break;
          }
          v10 = (char *)(this + 83);
          if ( v16 )
          {
            v12 = *(_QWORD *)v10;
            if ( *(char **)(*(_QWORD *)v10 + 8LL) != v10 )
LABEL_30:
              __fastfail(3u);
            *(_QWORD *)v9 = v12;
            *((_QWORD *)v9 + 1) = v10;
            *(_QWORD *)(v12 + 8) = v9;
            *(_QWORD *)v10 = v9;
          }
          else
          {
            v11 = (char **)this[84];
            if ( *v11 != v10 )
              goto LABEL_30;
            *(_QWORD *)v9 = v10;
            *((_QWORD *)v9 + 1) = v11;
            *v11 = (char *)v9;
            this[84] = (const unsigned __int16 *)v9;
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v19 )
          {
            SysFreeString(v19);
            v19 = 0;
          }
          ((void (__fastcall *)(struct IAppHostElement *))v14->lpVtbl->Release)(v14);
          v14 = 0;
        }
      }
    }
  }
  VariantClear(&pvarg);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v19 )
  {
    SysFreeString(v19);
    v19 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v20 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 208LL))(g_pFtpServer);
  STRU::~STRU(v25);
  return (unsigned int)Section;
}

```

## disassembly

```asm
0x1800150d0  mov     [rsp-8+arg_10], rbx
0x1800150d5  mov     [rsp-8+arg_18], rsi
0x1800150da  push    rbp
0x1800150db  push    rdi
0x1800150dc  push    r12
0x1800150de  push    r13
0x1800150e0  push    r15
0x1800150e2  lea     rbp, [rsp-40h]
0x1800150e7  sub     rsp, 140h
0x1800150ee  mov     rax, cs:__security_cookie
0x1800150f5  xor     rax, rsp
0x1800150f8  mov     [rbp+60h+var_30], rax
0x1800150fc  mov     rbx, rdx
0x1800150ff  mov     r15, rcx
0x180015102  xor     r13d, r13d
0x180015105  mov     [rsp+160h+var_108], r13
0x18001510a  mov     [rsp+160h+var_100], r13
0x18001510f  mov     [rsp+160h+var_130], r13
0x180015114  mov     [rsp+160h+var_120], r13d
0x180015119  mov     [rsp+160h+bstrString], r13
0x18001511e  mov     [rsp+160h+var_110], r13
0x180015123  mov     [rsp+160h+var_128], r13d
0x180015128  xor     edx, edx; Val
0x18001512a  lea     r8d, [r13+40h]; Size
0x18001512e  lea     rcx, [rbp+60h+var_70]; void *
0x180015132  call    memset_0
0x180015137  lea     r8d, [r13+20h]
0x18001513b  lea     rdx, [rbp+60h+var_70]
0x18001513f  lea     rcx, [rbp+60h+var_B0]
0x180015143  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180015149  nop
0x18001514a  xorps   xmm0, xmm0
0x18001514d  xor     eax, eax
0x18001514f  movups  xmmword ptr [rsp+160h+pvarg], xmm0
0x180015154  mov     qword ptr [rsp+160h+pvarg+10h], rax
0x180015159  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18001515e  call    cs:__imp_VariantInit
0x180015164  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001516b  mov     rax, [rcx]
0x18001516e  mov     rax, [rax+18h]
0x180015172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015177  mov     r12, rax
0x18001517a  mov     [rsp+160h+var_140], rbx; struct IErrorInfo **
0x18001517f  lea     r9, [rsp+160h+var_108]; struct IAppHostElement **
0x180015184  mov     r8, [r15+30h]; unsigned __int16 *
0x180015188  lea     rdx, aSystemFtpserve; "system.ftpServer/security/authorization"
0x18001518f  mov     rcx, rax; struct IAppHostAdminManager *
0x180015192  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@PEAPEAUIErrorInfo@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *,IErrorInfo * *)
0x180015197  mov     edi, eax
0x180015199  test    eax, eax
0x18001519b  js      loc_180015477
0x1800151a1  mov     rcx, [rsp+160h+var_108]
0x1800151a6  mov     rdx, [rcx]
0x1800151a9  mov     rax, [rdx+20h]
0x1800151ad  lea     rdx, [rsp+160h+var_100]
0x1800151b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151b7  mov     edi, eax
0x1800151b9  test    eax, eax
0x1800151bb  js      loc_180015477
0x1800151c1  mov     rcx, [rsp+160h+var_108]
0x1800151c6  mov     rax, [rcx]
0x1800151c9  mov     rax, [rax+10h]
0x1800151cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151d2  mov     [rsp+160h+var_108], r13
0x1800151d7  mov     rcx, [rsp+160h+var_100]
0x1800151dc  mov     rax, [rcx]
0x1800151df  lea     rdx, [rsp+160h+var_120]
0x1800151e4  mov     rax, [rax+18h]
0x1800151e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ed  mov     edi, eax
0x1800151ef  test    eax, eax
0x1800151f1  js      loc_180015477
0x1800151f7  mov     esi, r13d
0x1800151fa  cmp     [rsp+160h+var_120], r13d
0x1800151ff  jbe     loc_180015477
0x180015205  mov     [rsp+160h+var_124], r13d
0x18001520a  mov     eax, 13h
0x18001520f  mov     word ptr [rsp+160h+pvarg], ax
0x180015214  mov     dword ptr [rsp+160h+pvarg+8], esi
0x180015218  movups  xmm0, xmmword ptr [rsp+160h+pvarg]
0x18001521d  movaps  [rbp+60h+var_D0], xmm0
0x180015221  movsd   xmm1, qword ptr [rsp+160h+pvarg+10h]
0x180015227  movsd   [rbp+60h+var_C0], xmm1
0x18001522c  mov     rcx, [rsp+160h+var_100]
0x180015231  mov     rax, [rcx]
0x180015234  lea     r8, [rsp+160h+var_130]
0x180015239  lea     rdx, [rbp+60h+var_D0]
0x18001523d  mov     rax, [rax+20h]
0x180015241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015246  mov     edi, eax
0x180015248  test    eax, eax
0x18001524a  js      loc_180015477
0x180015250  lea     r8, [rsp+160h+var_124]; unsigned int *
0x180015255  lea     rdx, aAccesstype; "accessType"
0x18001525c  mov     rcx, [rsp+160h+var_130]; struct IAppHostElement *
0x180015261  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180015266  mov     edi, eax
0x180015268  test    eax, eax
0x18001526a  js      loc_180015477
0x180015270  lea     r8, [rsp+160h+bstrString]; unsigned __int16 **
0x180015275  lea     rdx, aUsers; "users"
0x18001527c  mov     rcx, [rsp+160h+var_130]; struct IAppHostElement *
0x180015281  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x180015286  mov     edi, eax
0x180015288  test    eax, eax
0x18001528a  js      loc_180015477
0x180015290  lea     r8, [rsp+160h+var_110]; unsigned __int16 **
0x180015295  lea     rdx, aRoles; "roles"
0x18001529c  mov     rcx, [rsp+160h+var_130]; struct IAppHostElement *
0x1800152a1  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800152a6  mov     edi, eax
0x1800152a8  test    eax, eax
0x1800152aa  js      loc_180015477
0x1800152b0  lea     r8, [rsp+160h+var_128]; unsigned int *
0x1800152b5  lea     rdx, aPermissions; "permissions"
0x1800152bc  mov     rcx, [rsp+160h+var_130]; struct IAppHostElement *
0x1800152c1  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x1800152c6  mov     edi, eax
0x1800152c8  test    eax, eax
0x1800152ca  js      loc_180015477
0x1800152d0  mov     rax, [rbp+60h+var_90]
0x1800152d4  mov     [rax], r13w
0x1800152d8  mov     eax, r13d
0x1800152db  mov     [rbp+60h+var_80], eax
0x1800152de  test    byte ptr [rsp+160h+var_128], 1
0x1800152e3  jz      short loc_180015303
0x1800152e5  lea     rdx, aRead; "Read"
0x1800152ec  lea     rcx, [rbp+60h+var_B0]
0x1800152f0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800152f6  mov     edi, eax
0x1800152f8  test    eax, eax
0x1800152fa  js      loc_180015477
0x180015300  mov     eax, [rbp+60h+var_80]
0x180015303  test    byte ptr [rsp+160h+var_128], 2
0x180015308  jz      short loc_180015344
0x18001530a  test    eax, eax
0x18001530c  jz      short loc_180015329
0x18001530e  lea     rdx, asc_18004EC70; ","
0x180015315  lea     rcx, [rbp+60h+var_B0]
0x180015319  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001531f  mov     edi, eax
0x180015321  test    eax, eax
0x180015323  js      loc_180015477
0x180015329  lea     rdx, aWrite; "Write"
0x180015330  lea     rcx, [rbp+60h+var_B0]
0x180015334  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001533a  mov     edi, eax
0x18001533c  test    eax, eax
0x18001533e  js      loc_180015477
0x180015344  mov     ecx, 60h ; '`'; Size
0x180015349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001534e  mov     rbx, rax
0x180015351  mov     [rbp+60h+var_E0], rax
0x180015355  test    rax, rax
0x180015358  jz      loc_180015472
0x18001535e  mov     dword ptr [rax+14h], 2
0x180015365  mov     [rax+18h], r13
0x180015369  mov     [rax+20h], r13d
0x18001536d  mov     [rax+28h], r13
0x180015371  mov     [rax+30h], r13d
0x180015375  mov     [rax+34h], r13d
0x180015379  mov     [rax+38h], r13
0x18001537d  mov     [rax+40h], r13d
0x180015381  mov     [rax+48h], r13
0x180015385  mov     [rax+50h], r13
0x180015389  mov     [rax+58h], r13d
0x18001538d  mov     [rax+8], r13
0x180015391  mov     [rax], r13
0x180015394  mov     dword ptr [rax+10h], 45524155h
0x18001539b  test    rax, rax
0x18001539e  jz      loc_180015472
0x1800153a4  mov     rax, [rbp+60h+var_90]
0x1800153a8  mov     [rsp+160h+var_140], rax
0x1800153ad  mov     r9, [rsp+160h+var_110]
0x1800153b2  mov     r8, [rsp+160h+bstrString]
0x1800153b7  mov     edx, [rsp+160h+var_124]
0x1800153bb  mov     rcx, rbx
0x1800153be  call    ?InitializeInstance@URL_AUTHZ_RULE_ENTRY@@QEAAJW4AUTHORIZATION_ACCESS_TYPE@@PEBG11@Z; URL_AUTHZ_RULE_ENTRY::InitializeInstance(AUTHORIZATION_ACCESS_TYPE,ushort const *,ushort const *,ushort const *)
0x1800153c3  mov     edi, eax
0x1800153c5  test    eax, eax
0x1800153c7  js      loc_180015460
0x1800153cd  lea     rax, [r15+298h]
0x1800153d4  cmp     [rsp+160h+var_124], r13d
0x1800153d9  jnz     short loc_1800153F4
0x1800153db  mov     rcx, [rax+8]
0x1800153df  cmp     [rcx], rax
0x1800153e2  jnz     short loc_180015459
0x1800153e4  mov     [rbx], rax
0x1800153e7  mov     [rbx+8], rcx
0x1800153eb  mov     [rcx], rbx
0x1800153ee  mov     [rax+8], rbx
0x1800153f2  jmp     short loc_18001540B
0x1800153f4  mov     rcx, [rax]
0x1800153f7  cmp     [rcx+8], rax
0x1800153fb  jnz     short loc_180015459
0x1800153fd  mov     [rbx], rcx
0x180015400  mov     [rbx+8], rax
0x180015404  mov     [rcx+8], rbx
0x180015408  mov     [rax], rbx
0x18001540b  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180015410  test    rcx, rcx
0x180015413  jz      short loc_180015420
0x180015415  call    cs:__imp_SysFreeString
0x18001541b  mov     [rsp+160h+bstrString], r13
0x180015420  mov     rcx, [rsp+160h+var_110]; bstrString
0x180015425  test    rcx, rcx
0x180015428  jz      short loc_180015435
0x18001542a  call    cs:__imp_SysFreeString
0x180015430  mov     [rsp+160h+var_110], r13
0x180015435  mov     rcx, [rsp+160h+var_130]
0x18001543a  mov     rax, [rcx]
0x18001543d  mov     rax, [rax+10h]
0x180015441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015446  mov     [rsp+160h+var_130], r13
0x18001544b  inc     esi
0x18001544d  cmp     esi, [rsp+160h+var_120]
0x180015451  jb      loc_180015205
0x180015457  jmp     short loc_180015477
0x180015459  mov     ecx, 3
0x18001545e  int     29h; Win8: RtlFailFast(ecx)
0x180015460  mov     rcx, rbx; this
0x180015463  call    ??1URL_AUTHZ_RULE_ENTRY@@QEAA@XZ; URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(void)
0x180015468  mov     rcx, rbx; Block
0x18001546b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015470  jmp     short loc_180015477
0x180015472  mov     edi, 80070008h
0x180015477  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18001547c  call    cs:__imp_VariantClear
0x180015482  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180015487  test    rcx, rcx
0x18001548a  jz      short loc_180015497
0x18001548c  call    cs:__imp_SysFreeString
0x180015492  mov     [rsp+160h+bstrString], r13
0x180015497  mov     rcx, [rsp+160h+var_110]; bstrString
0x18001549c  test    rcx, rcx
0x18001549f  jz      short loc_1800154AC
0x1800154a1  call    cs:__imp_SysFreeString
0x1800154a7  mov     [rsp+160h+var_110], r13
0x1800154ac  mov     rcx, [rsp+160h+var_130]
0x1800154b1  test    rcx, rcx
0x1800154b4  jz      short loc_1800154C7
0x1800154b6  mov     rax, [rcx]
0x1800154b9  mov     rax, [rax+10h]
0x1800154bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c2  mov     [rsp+160h+var_130], r13
0x1800154c7  mov     rcx, [rsp+160h+var_100]
0x1800154cc  test    rcx, rcx
0x1800154cf  jz      short loc_1800154E2
0x1800154d1  mov     rax, [rcx]
0x1800154d4  mov     rax, [rax+10h]
0x1800154d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154dd  mov     [rsp+160h+var_100], r13
0x1800154e2  mov     rcx, [rsp+160h+var_108]
0x1800154e7  test    rcx, rcx
0x1800154ea  jz      short loc_1800154FD
0x1800154ec  mov     rax, [rcx]
0x1800154ef  mov     rax, [rax+10h]
0x1800154f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f8  mov     [rsp+160h+var_108], r13
0x1800154fd  test    r12, r12
0x180015500  jz      short loc_180015519
0x180015502  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180015509  mov     rax, [rcx]
0x18001550c  mov     rax, [rax+0D0h]
0x180015513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015518  nop
0x180015519  lea     rcx, [rbp+60h+var_B0]
0x18001551d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180015523  mov     eax, edi
0x180015525  mov     rcx, [rbp+60h+var_30]
0x180015529  xor     rcx, rsp; StackCookie
0x18001552c  call    __security_check_cookie
0x180015531  lea     r11, [rsp+160h+var_20]
0x180015539  mov     rbx, [r11+40h]
0x18001553d  mov     rsi, [r11+48h]
0x180015541  mov     rsp, r11
0x180015544  pop     r15
0x180015546  pop     r13
0x180015548  pop     r12
0x18001554a  pop     rdi
0x18001554b  pop     rbp
0x18001554c  retn
```
