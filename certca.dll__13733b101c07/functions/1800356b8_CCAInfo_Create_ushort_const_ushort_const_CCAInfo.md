# CCAInfo::Create(ushort const *,ushort const *,CCAInfo * *)

- ea: `0x1800356b8`
- end: `0x180035ae1`
- name: `?Create@CCAInfo@@SAJPEBG0PEAPEAV1@@Z`
- size: `1065`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *Src, struct CCAInfo **)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x18002dc00`
- `0x180035ae8`

## callees

- `0x180005944`
- `0x180005f00`
- `0x1800062d0`
- `0x180008400`
- `0x180008420`
- `0x18000ac20`
- `0x18000ce90`
- `0x18000cfc0`
- `0x18000d3a0`
- `0x18000e130`
- `0x18000e52c`
- `0x18000fac0`
- `0x180014fac`
- `0x180035478`
- `0x1800356b8`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003572e`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035778`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800357bb`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800357f6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035899`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800358ed`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035928`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800359e5`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035a20`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035a6a`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003572e`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035778`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800357bb`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800357f6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035899`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800358ed`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035928`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800359e5`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035a20`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035a6a`
- `WLDAP32!__imp_ldap_unbind` at `0x180035ab1`
- `WLDAP32!__imp_ldap_unbind` at `0x180035ab1`

## string_xrefs

- `0x180035967`: `CN=Enrollment Services,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CCAInfo::Create(const unsigned __int16 *a1, const unsigned __int16 *Src, struct CCAInfo **a3)
{
  void *v5; // r14
  unsigned __int16 *v6; // r12
  int DoesDSExist; // eax
  unsigned int v8; // r15d
  struct CCAProperty *v9; // rbx
  int v10; // eax
  unsigned int v11; // edx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  unsigned __int16 *v16; // rcx
  unsigned __int64 v17; // rdi
  struct CCAProperty *v18; // rax
  struct CCAProperty *v19; // rdi
  LDAP *ld; // [rsp+40h] [rbp-58h] BYREF
  struct CCAProperty *v22[3]; // [rsp+48h] [rbp-50h] BYREF
  __int128 v23; // [rsp+60h] [rbp-38h] BYREF
  unsigned __int16 *v25; // [rsp+B8h] [rbp+20h] BYREF

  v5 = 0;
  ld = 0;
  v6 = 0;
  v25 = 0;
  v23 = 0;
  if ( !a3 || !a1 )
  {
    v8 = -2147467261;
    CSPrintErrorLineFile(0x3350325u, -2147467261);
    goto LABEL_35;
  }
  DoesDSExist = myDoesDSExist(1);
  v8 = DoesDSExist;
  if ( DoesDSExist )
  {
    CSPrintErrorLineFile(0x33A0325u, DoesDSExist);
    return v8;
  }
  v9 = (struct CCAProperty *)_set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v22[1] = v9;
  v10 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, &ld, 0);
  v8 = v10;
  if ( !v10 )
  {
    if ( Src )
    {
      v6 = CertAllocString(Src);
      v25 = v6;
      if ( !v6 )
      {
        v8 = -2147024882;
        CSPrintErrorLineFile(0x3500325u, -2147024882);
        _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
        goto LABEL_35;
      }
    }
    else
    {
      v12 = CAGetAuthoritativeDomainDn(ld, 0, &v25);
      v8 = v12;
      if ( v12 )
      {
        CSPrintErrorLineFile(0x35A0325u, v12);
        _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
        v6 = v25;
        goto LABEL_35;
      }
      v6 = v25;
    }
    v5 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v22[0] = (struct CCAProperty *)v5;
    if ( v5 )
    {
      *((_DWORD *)v5 + 4) = 1;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 1) = 0;
      *(_QWORD *)v5 = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_DWORD *)v5 + 10) = 1;
      *((_DWORD *)v5 + 11) = 1;
      *((_DWORD *)v5 + 12) = 4;
      *((_QWORD *)v5 + 7) = 0;
      *((_DWORD *)v5 + 13) = 0;
      *((_DWORD *)v5 + 16) = 1;
      *((_DWORD *)v5 + 17) = 0;
      *((_DWORD *)v5 + 18) = 1;
      *((_DWORD *)v5 + 19) = 0;
    }
    else
    {
      v5 = 0;
    }
    if ( v5 )
    {
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( a1[v14] );
      do
        ++v13;
      while ( v6[v13] );
      v15 = v13 + v14 + 62;
      if ( v15 <= 0x10000 )
      {
        v16 = CertAllocStringLen(0, v15);
        *((_QWORD *)v5 + 4) = v16;
        if ( v16 )
        {
          v17 = (unsigned int)(v15 + 1);
          StringCchCopyW(v16, v17, L"CN=");
          StringCchCatW(*((unsigned __int16 **)v5 + 4), (unsigned int)v17, a1);
          StringCchCatW(*((unsigned __int16 **)v5 + 4), (unsigned int)v17, L",");
          StringCchCatW(
            *((unsigned __int16 **)v5 + 4),
            (unsigned int)v17,
            L"CN=Enrollment Services,CN=Public Key Services,CN=Services,");
          StringCchCatW(*((unsigned __int16 **)v5 + 4), (unsigned int)v17, v6);
          v18 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v19 = v18;
          v22[0] = v18;
          if ( v18 )
          {
            *(_QWORD *)v18 = 0;
            *((_QWORD *)v18 + 2) = 0;
            *((_QWORD *)v18 + 1) = CertAllocString(L"cn");
          }
          else
          {
            v19 = 0;
          }
          v22[0] = v19;
          if ( v19 )
          {
            if ( *((_QWORD *)v19 + 1) )
            {
              v23 = (unsigned __int64)a1;
              CCAProperty::SetValue(v19, (unsigned __int16 **)&v23);
              CCAProperty::Append((struct CCAProperty **)v5 + 1, v19);
              *((_DWORD *)v5 + 10) = 1;
              *a3 = (struct CCAInfo *)v5;
              v5 = 0;
            }
            else
            {
              CCAProperty::DeleteChain(v22);
              v22[0] = 0;
              v8 = -2147024882;
              CSPrintErrorLineFile(0x3850325u, -2147024882);
            }
            _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
          }
          else
          {
            v8 = -2147024882;
            CSPrintErrorLineFile(0x37D0325u, -2147024882);
            _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
          }
        }
        else
        {
          v8 = -2147024882;
          CSPrintErrorLineFile(0x3710325u, -2147024882);
          _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
        }
      }
      else
      {
        v8 = -2147024362;
        CSPrintErrorLineFile(0x36A0325u, -2147024362);
        _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
      }
    }
    else
    {
      v8 = -2147024882;
      CSPrintErrorLineFile(0x3620325u, -2147024882);
      _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
    }
LABEL_35:
    if ( v6 )
      CertFreeString(v6);
    goto LABEL_37;
  }
  CSPrintErrorLineFile(0x3480325u, v10);
  _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v9);
LABEL_37:
  if ( ld )
    ldap_unbind(ld);
  if ( v5 )
    CCAInfo::`scalar deleting destructor'((CCAInfo *)v5, v11);
  return v8;
}

```

## disassembly

```asm
0x1800356b8  mov     rax, rsp
0x1800356bb  mov     [rax+8], rbx
0x1800356bf  mov     [rax+10h], rsi
0x1800356c3  mov     [rax+18h], r8
0x1800356c7  push    rdi
0x1800356c8  push    r12
0x1800356ca  push    r13
0x1800356cc  push    r14
0x1800356ce  push    r15
0x1800356d0  sub     rsp, 70h
0x1800356d4  mov     rdi, rdx
0x1800356d7  mov     r13, rcx
0x1800356da  xor     esi, esi
0x1800356dc  mov     r14d, esi
0x1800356df  mov     [rax-60h], rsi
0x1800356e3  mov     [rax-58h], rsi
0x1800356e7  mov     r12d, esi
0x1800356ea  mov     [rax+20h], rsi
0x1800356ee  xorps   xmm0, xmm0
0x1800356f1  movups  xmmword ptr [rax-38h], xmm0
0x1800356f5  test    r8, r8
0x1800356f8  jz      loc_180035A87
0x1800356fe  test    rcx, rcx
0x180035701  jz      loc_180035A87
0x180035707  lea     ecx, [rsi+1]; int
0x18003570a  call    ?myDoesDSExist@@YAJH@Z; myDoesDSExist(int)
0x18003570f  mov     r15d, eax
0x180035712  test    eax, eax
0x180035714  jz      short loc_180035727
0x180035716  mov     edx, eax; int
0x180035718  mov     ecx, 33A0325h; unsigned int
0x18003571d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035722  jmp     loc_180035AC4
0x180035727  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18003572e  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035734  mov     rbx, rax
0x180035737  mov     [rsp+98h+var_48], rax
0x18003573c  mov     [rsp+98h+var_70], rsi
0x180035741  lea     rax, [rsp+98h+ld]
0x180035746  mov     [rsp+98h+var_78], rax
0x18003574b  xor     r9d, r9d
0x18003574e  lea     edx, [r9+8]
0x180035752  xor     ecx, ecx
0x180035754  lea     r8d, [r9+2]
0x180035758  call    myRobustLdapBindEx
0x18003575d  mov     r15d, eax
0x180035760  mov     [rsp+98h+var_68], eax
0x180035764  test    eax, eax
0x180035766  jz      short loc_180035784
0x180035768  mov     edx, eax; int
0x18003576a  mov     ecx, 3480325h; unsigned int
0x18003576f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035774  nop
0x180035775  mov     rcx, rbx
0x180035778  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18003577e  nop
0x18003577f  jmp     loc_180035AA7
0x180035784  test    rdi, rdi
0x180035787  jz      short loc_1800357C7
0x180035789  mov     rcx, rdi; Src
0x18003578c  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x180035791  mov     r12, rax
0x180035794  mov     [rsp+98h+arg_18], rax
0x18003579c  test    rax, rax
0x18003579f  jnz     short loc_180035812
0x1800357a1  mov     edx, 8007000Eh; int
0x1800357a6  mov     r15d, edx
0x1800357a9  mov     [rsp+98h+var_68], edx
0x1800357ad  mov     ecx, 3500325h; unsigned int
0x1800357b2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800357b7  nop
0x1800357b8  mov     rcx, rbx
0x1800357bb  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800357c1  nop
0x1800357c2  jmp     loc_180035A9A
0x1800357c7  lea     r8, [rsp+98h+arg_18]; unsigned __int16 **
0x1800357cf  xor     edx, edx; unsigned __int16 **
0x1800357d1  mov     rcx, [rsp+98h+ld]; struct ldap *
0x1800357d6  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x1800357db  mov     r15d, eax
0x1800357de  mov     [rsp+98h+var_68], eax
0x1800357e2  test    eax, eax
0x1800357e4  jz      short loc_18003580A
0x1800357e6  mov     edx, eax; int
0x1800357e8  mov     ecx, 35A0325h; unsigned int
0x1800357ed  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800357f2  nop
0x1800357f3  mov     rcx, rbx
0x1800357f6  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800357fc  nop
0x1800357fd  mov     r12, [rsp+98h+arg_18]
0x180035805  jmp     loc_180035A9A
0x18003580a  mov     r12, [rsp+98h+arg_18]
0x180035812  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035819  mov     ecx, 50h ; 'P'; unsigned __int64
0x18003581e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035823  mov     r14, rax
0x180035826  mov     [rsp+98h+var_50], rax
0x18003582b  test    rax, rax
0x18003582e  jz      short loc_180035872
0x180035830  mov     eax, 1
0x180035835  mov     [r14+10h], eax
0x180035839  mov     [r14+18h], rsi
0x18003583d  mov     [r14+8], rsi
0x180035841  mov     [r14], rsi
0x180035844  mov     [r14+20h], rsi
0x180035848  mov     [r14+28h], eax
0x18003584c  mov     [r14+2Ch], eax
0x180035850  mov     dword ptr [r14+30h], 4
0x180035858  mov     [r14+38h], rsi
0x18003585c  mov     [r14+34h], esi
0x180035860  mov     [r14+40h], eax
0x180035864  mov     [r14+44h], esi
0x180035868  mov     [r14+48h], eax
0x18003586c  mov     [r14+4Ch], esi
0x180035870  jmp     short loc_180035875
0x180035872  mov     r14, rsi
0x180035875  mov     [rsp+98h+var_60], r14
0x18003587a  test    r14, r14
0x18003587d  jnz     short loc_1800358A5
0x18003587f  mov     edx, 8007000Eh; int
0x180035884  mov     r15d, edx
0x180035887  mov     [rsp+98h+var_68], edx
0x18003588b  mov     ecx, 3620325h; unsigned int
0x180035890  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035895  nop
0x180035896  mov     rcx, rbx
0x180035899  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18003589f  nop
0x1800358a0  jmp     loc_180035A9A
0x1800358a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800358a9  mov     rcx, rax
0x1800358ac  inc     rcx
0x1800358af  cmp     [r13+rcx*2+0], si
0x1800358b5  jnz     short loc_1800358AC
0x1800358b7  inc     rax
0x1800358ba  cmp     [r12+rax*2], si
0x1800358bf  jnz     short loc_1800358B7
0x1800358c1  lea     rdi, [rcx+3Eh]
0x1800358c5  add     rdi, rax
0x1800358c8  cmp     rdi, 10000h
0x1800358cf  jbe     short loc_1800358F9
0x1800358d1  mov     r15d, 80070216h
0x1800358d7  mov     [rsp+98h+var_68], r15d
0x1800358dc  mov     edx, r15d; int
0x1800358df  mov     ecx, 36A0325h; unsigned int
0x1800358e4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800358e9  nop
0x1800358ea  mov     rcx, rbx
0x1800358ed  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800358f3  nop
0x1800358f4  jmp     loc_180035A9A
0x1800358f9  mov     edx, edi; unsigned int
0x1800358fb  xor     ecx, ecx; Src
0x1800358fd  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x180035902  mov     rcx, rax; unsigned __int16 *
0x180035905  mov     [r14+20h], rax
0x180035909  test    rax, rax
0x18003590c  jnz     short loc_180035934
0x18003590e  mov     edx, 8007000Eh; int
0x180035913  mov     r15d, edx
0x180035916  mov     [rsp+98h+var_68], edx
0x18003591a  mov     ecx, 3710325h; unsigned int
0x18003591f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035924  nop
0x180035925  mov     rcx, rbx
0x180035928  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18003592e  nop
0x18003592f  jmp     loc_180035A9A
0x180035934  lea     eax, [rdi+1]
0x180035937  mov     edi, eax
0x180035939  lea     r8, aCn_2; "CN="
0x180035940  mov     edx, eax; unsigned __int64
0x180035942  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035947  mov     r8, r13; unsigned __int16 *
0x18003594a  mov     edx, edi; unsigned __int64
0x18003594c  mov     rcx, [r14+20h]; unsigned __int16 *
0x180035950  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035955  lea     r8, asc_180063424; ","
0x18003595c  mov     edx, edi; unsigned __int64
0x18003595e  mov     rcx, [r14+20h]; unsigned __int16 *
0x180035962  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035967  lea     r8, aCnEnrollmentSe; "CN=Enrollment Services,CN=Public Key Se"...
0x18003596e  mov     edx, edi; unsigned __int64
0x180035970  mov     rcx, [r14+20h]; unsigned __int16 *
0x180035974  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035979  mov     r8, r12; unsigned __int16 *
0x18003597c  mov     edx, edi; unsigned __int64
0x18003597e  mov     rcx, [r14+20h]; unsigned __int16 *
0x180035982  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035987  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003598e  mov     ecx, 18h; unsigned __int64
0x180035993  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035998  mov     rdi, rax
0x18003599b  mov     [rsp+98h+var_50], rax
0x1800359a0  test    rax, rax
0x1800359a3  jz      short loc_1800359BE
0x1800359a5  mov     [rax], rsi
0x1800359a8  mov     [rax+10h], rsi
0x1800359ac  lea     rcx, aCn_1; "cn"
0x1800359b3  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x1800359b8  mov     [rdi+8], rax
0x1800359bc  jmp     short loc_1800359C1
0x1800359be  mov     rdi, rsi
0x1800359c1  mov     [rsp+98h+var_50], rdi
0x1800359c6  test    rdi, rdi
0x1800359c9  jnz     short loc_1800359F1
0x1800359cb  mov     edx, 8007000Eh; int
0x1800359d0  mov     r15d, edx
0x1800359d3  mov     [rsp+98h+var_68], edx
0x1800359d7  mov     ecx, 37D0325h; unsigned int
0x1800359dc  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800359e1  nop
0x1800359e2  mov     rcx, rbx
0x1800359e5  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800359eb  nop
0x1800359ec  jmp     loc_180035A9A
0x1800359f1  cmp     [rdi+8], rsi
0x1800359f5  jnz     short loc_180035A29
0x1800359f7  lea     rcx, [rsp+98h+var_50]; struct CCAProperty **
0x1800359fc  call    ?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z; CCAProperty::DeleteChain(CCAProperty * *)
0x180035a01  mov     [rsp+98h+var_50], rsi
0x180035a06  mov     edx, 8007000Eh; int
0x180035a0b  mov     r15d, edx
0x180035a0e  mov     [rsp+98h+var_68], edx
0x180035a12  mov     ecx, 3850325h; unsigned int
0x180035a17  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035a1c  nop
0x180035a1d  mov     rcx, rbx
0x180035a20  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035a26  nop
0x180035a27  jmp     short loc_180035A9A
0x180035a29  mov     [rsp+98h+var_38], r13
0x180035a2e  mov     [rsp+98h+var_30], rsi
0x180035a33  lea     rdx, [rsp+98h+var_38]; unsigned __int16 **
0x180035a38  mov     rcx, rdi; this
0x180035a3b  call    ?SetValue@CCAProperty@@QEAAJPEAPEAG@Z; CCAProperty::SetValue(ushort * *)
0x180035a40  lea     rcx, [r14+8]; struct CCAProperty **
0x180035a44  mov     rdx, rdi; struct CCAProperty *
0x180035a47  call    ?Append@CCAProperty@@SAJPEAPEAV1@PEAV1@@Z; CCAProperty::Append(CCAProperty * *,CCAProperty *)
0x180035a4c  mov     dword ptr [r14+28h], 1
0x180035a54  mov     rax, [rsp+98h+arg_10]
0x180035a5c  mov     [rax], r14
0x180035a5f  mov     r14, rsi
0x180035a62  mov     [rsp+98h+var_60], rsi
0x180035a67  mov     rcx, rbx
0x180035a6a  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035a70  nop
0x180035a71  jmp     short loc_180035A9A
0x180035a73  mov     r15d, [rsp+98h+var_68]
0x180035a78  mov     r14, [rsp+98h+var_60]
0x180035a7d  mov     r12, [rsp+98h+arg_18]
0x180035a85  jmp     short loc_180035A9A
0x180035a87  mov     r15d, 80004003h
0x180035a8d  mov     edx, r15d; int
0x180035a90  mov     ecx, 3350325h; unsigned int
0x180035a95  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035a9a  test    r12, r12
0x180035a9d  jz      short loc_180035AA7
0x180035a9f  mov     rcx, r12; unsigned __int16 *
0x180035aa2  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x180035aa7  mov     rcx, [rsp+98h+ld]; ld
0x180035aac  test    rcx, rcx
0x180035aaf  jz      short loc_180035AB7
0x180035ab1  call    cs:__imp_ldap_unbind
0x180035ab7  test    r14, r14
0x180035aba  jz      short loc_180035AC4
0x180035abc  mov     rcx, r14; this
0x180035abf  call    ??_GCCAInfo@@QEAAPEAXI@Z; CCAInfo::`scalar deleting destructor'(uint)
0x180035ac4  mov     eax, r15d
0x180035ac7  lea     r11, [rsp+98h+var_28]
0x180035acc  mov     rbx, [r11+30h]
0x180035ad0  mov     rsi, [r11+38h]
0x180035ad4  mov     rsp, r11
0x180035ad7  pop     r15
0x180035ad9  pop     r14
0x180035adb  pop     r13
0x180035add  pop     r12
0x180035adf  pop     rdi
0x180035ae0  retn
```
