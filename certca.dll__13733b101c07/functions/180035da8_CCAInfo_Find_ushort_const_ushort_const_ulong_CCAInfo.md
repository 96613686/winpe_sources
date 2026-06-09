# CCAInfo::Find(ushort const *,ushort const *,ulong,CCAInfo * *)

- ea: `0x180035da8`
- end: `0x1800361a9`
- name: `?Find@CCAInfo@@SAJPEBG0KPEAPEAV1@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LDAP *, unsigned int, struct CCAInfo **)`
- caller_count: `5`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002de40`
- `0x18002df40`
- `0x18002e030`
- `0x18002e170`
- `0x1800361b0`

## callees

- `0x180005944`
- `0x180005f00`
- `0x1800062d0`
- `0x180008400`
- `0x180008420`
- `0x180008610`
- `0x18000ac20`
- `0x18000ce90`
- `0x18000e130`
- `0x18000e52c`
- `0x180035da8`
- `0x1800373bc`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035e4c`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035e98`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035ee5`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035f29`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035fa7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035fe2`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036084`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800360c7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003611a`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036126`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035e4c`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035e98`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035ee5`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035f29`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035fa7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035fe2`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036084`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800360c7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003611a`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036126`
- `WLDAP32!__imp_ldap_unbind` at `0x180036191`
- `WLDAP32!__imp_ldap_unbind` at `0x180036191`

## string_xrefs

- `0x180035f3d`: `CN=Enrollment Services,CN=Public Key Services,CN=Services,`
- `0x180036004`: `(objectCategory=pKIEnrollmentService)`
- `0x1800360dc`: `(objectCategory=pKIEnrollmentService)`

## pseudocode

```c
__int64 __fastcall CCAInfo::Find(const unsigned __int16 *a1, LDAP *a2, unsigned int a3, struct CCAInfo **a4)
{
  unsigned int v4; // r13d
  unsigned __int16 *v6; // r15
  unsigned int v7; // edi
  unsigned __int16 *v8; // r12
  int DoesDSExist; // eax
  unsigned __int16 *v10; // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // r13
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r14
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rdi
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  int v21; // eax
  LDAP *ld; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-60h]
  unsigned __int16 *v26; // [rsp+50h] [rbp-58h]
  unsigned __int16 *v27[10]; // [rsp+58h] [rbp-50h] BYREF

  v4 = a3;
  ld = 0;
  v6 = 0;
  v24 = 0;
  v27[0] = 0;
  if ( !a4 )
  {
    v7 = -2147467261;
    CSPrintErrorLineFile(0xBD0325u, -2147467261);
    goto LABEL_44;
  }
  v8 = 0;
  v26 = 0;
  v25 = 0;
  DoesDSExist = myDoesDSExist(1);
  v7 = DoesDSExist;
  if ( DoesDSExist )
  {
    if ( DoesDSExist != -2147023541 && DoesDSExist != -2147023665 )
      CSPrintErrorLineFileData2(0, 0xC90325u, DoesDSExist, -2147023555);
    goto LABEL_44;
  }
  v10 = (unsigned __int16 *)_set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v27[1] = v10;
  if ( (v4 & 0x800) != 0 )
  {
    ld = a2;
  }
  else
  {
    v20 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, &ld, 0);
    v7 = v20;
    if ( v20 )
    {
      CSPrintErrorLineFileData2(0, 0xE10325u, v20, -2147023573);
      _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
      goto LABEL_44;
    }
    if ( a2 )
    {
      v16 = CertAllocString((const unsigned __int16 *)a2);
      v25 = v16;
      if ( !v16 )
      {
        v7 = -2147024882;
        CSPrintErrorLineFile(0xE80325u, -2147024882);
        _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
        goto LABEL_44;
      }
      v12 = -1;
      goto LABEL_18;
    }
  }
  v11 = CAGetAuthoritativeDomainDn(ld, v27, &v24);
  v7 = v11;
  if ( !v11 )
  {
    v6 = v24;
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( v24[v13] );
    v14 = v13 + 58;
    if ( (unsigned __int64)(v13 + 58) > 0x10000 )
    {
      v7 = -2147024362;
      CSPrintErrorLineFile(0xFA0325u, -2147024362);
      _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
      LOWORD(v4) = a3;
      goto LABEL_38;
    }
    v15 = CertAllocStringLen(0, v14);
    v16 = v15;
    v25 = v15;
    if ( !v15 )
    {
      v7 = -2147024882;
      CSPrintErrorLineFile(0x1000325u, -2147024882);
      _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
      LOWORD(v4) = a3;
      goto LABEL_38;
    }
    StringCchCopyW(v15, v14 + 1, L"CN=Enrollment Services,CN=Public Key Services,CN=Services,");
    StringCchCatW(v16, v14 + 1, v6);
    v4 = a3;
LABEL_18:
    if ( a1 )
    {
      do
        ++v12;
      while ( a1[v12] );
      v17 = v12 + 41;
      if ( v17 > 0x10000 )
      {
        v7 = -2147024362;
        CSPrintErrorLineFile(0x10F0325u, -2147024362);
        _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
LABEL_35:
        if ( v16 )
          CertFreeString(v16);
        LOWORD(v4) = a3;
        goto LABEL_38;
      }
      v8 = CertAllocStringLen(0, v17);
      v26 = v8;
      if ( !v8 )
      {
        v7 = -2147024882;
        CSPrintErrorLineFile(0x1160325u, -2147024882);
        _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
        goto LABEL_35;
      }
      v18 = (unsigned int)(v17 + 1);
      StringCchCopyW(v8, v18, L"(&");
      StringCchCatW(v8, (unsigned int)v18, L"(objectCategory=pKIEnrollmentService)");
      StringCchCatW(v8, (unsigned int)v18, a1);
      StringCchCatW(v8, (unsigned int)v18, L")");
      v19 = v8;
    }
    else
    {
      v19 = L"(objectCategory=pKIEnrollmentService)";
    }
    v21 = CCAInfo::_ProcessFind(ld, v19, v16, v4, a4);
    v7 = v21;
    if ( v21 )
      CSPrintErrorLineFile(0x1260325u, v21);
    _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
    goto LABEL_35;
  }
  CSPrintErrorLineFile(0xF40325u, v11);
  _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v10);
  v6 = v24;
LABEL_38:
  if ( v6 )
    CertFreeString(v6);
  if ( v27[0] )
    CertFreeString(v27[0]);
  if ( v8 )
    CertFreeString(v8);
LABEL_44:
  if ( (v4 & 0x800) == 0 && ld )
    ldap_unbind(ld);
  return v7;
}

```

## disassembly

```asm
0x180035da8  mov     rax, rsp
0x180035dab  mov     [rax+20h], r9
0x180035daf  mov     [rax+18h], r8d
0x180035db3  mov     [rax+8], rcx
0x180035db7  push    rbx
0x180035db8  push    rsi
0x180035db9  push    rdi
0x180035dba  push    r12
0x180035dbc  push    r13
0x180035dbe  push    r14
0x180035dc0  push    r15
0x180035dc2  sub     rsp, 70h
0x180035dc6  mov     r13d, r8d
0x180035dc9  mov     r14, rdx
0x180035dcc  xor     esi, esi
0x180035dce  mov     [rax-70h], rsi
0x180035dd2  mov     r15d, esi
0x180035dd5  mov     [rax-68h], rsi
0x180035dd9  mov     [rax-50h], rsi
0x180035ddd  test    r9, r9
0x180035de0  jnz     short loc_180035DF8
0x180035de2  mov     edi, 80004003h
0x180035de7  mov     edx, edi; int
0x180035de9  mov     ecx, 0BD0325h; unsigned int
0x180035dee  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035df3  jmp     loc_180036180
0x180035df8  mov     r12, rsi
0x180035dfb  mov     [rsp+0A8h+var_58], rsi
0x180035e00  mov     [rsp+0A8h+var_60], rsi
0x180035e05  mov     ecx, 1; int
0x180035e0a  call    ?myDoesDSExist@@YAJH@Z; myDoesDSExist(int)
0x180035e0f  mov     edi, eax
0x180035e11  test    eax, eax
0x180035e13  jz      short loc_180035E45
0x180035e15  cmp     eax, 8007054Bh
0x180035e1a  jz      loc_180036180
0x180035e20  cmp     eax, 800704CFh
0x180035e25  jz      loc_180036180
0x180035e2b  mov     r9d, 8007053Dh; int
0x180035e31  mov     r8d, eax; int
0x180035e34  mov     edx, 0C90325h; unsigned int
0x180035e39  xor     ecx, ecx; unsigned __int16 *
0x180035e3b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180035e40  jmp     loc_180036180
0x180035e45  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x180035e4c  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035e52  mov     rbx, rax
0x180035e55  mov     [rsp+0A8h+var_48], rax
0x180035e5a  bt      r13d, 0Bh
0x180035e5f  jnb     loc_180036040
0x180035e65  mov     [rsp+0A8h+ld], r14
0x180035e6a  lea     r8, [rsp+0A8h+var_68]; unsigned __int16 **
0x180035e6f  lea     rdx, [rsp+0A8h+var_50]; unsigned __int16 **
0x180035e74  mov     rcx, [rsp+0A8h+ld]; struct ldap *
0x180035e79  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x180035e7e  mov     edi, eax
0x180035e80  mov     [rsp+0A8h+var_78], eax
0x180035e84  test    eax, eax
0x180035e86  jz      short loc_180035EA9
0x180035e88  mov     edx, eax; int
0x180035e8a  mov     ecx, 0F40325h; unsigned int
0x180035e8f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035e94  nop
0x180035e95  mov     rcx, rbx
0x180035e98  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035e9e  nop
0x180035e9f  mov     r15, [rsp+0A8h+var_68]
0x180035ea4  jmp     loc_180036157
0x180035ea9  mov     r15, [rsp+0A8h+var_68]
0x180035eae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180035eb2  mov     rax, rdi
0x180035eb5  inc     rax
0x180035eb8  cmp     [r15+rax*2], si
0x180035ebd  jnz     short loc_180035EB5
0x180035ebf  lea     r13, [rax+3Ah]
0x180035ec3  cmp     r13, 10000h
0x180035eca  jbe     short loc_180035EF9
0x180035ecc  mov     edx, 80070216h; int
0x180035ed1  mov     edi, edx
0x180035ed3  mov     [rsp+0A8h+var_78], edx
0x180035ed7  mov     ecx, 0FA0325h; unsigned int
0x180035edc  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035ee1  nop
0x180035ee2  mov     rcx, rbx
0x180035ee5  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035eeb  nop
0x180035eec  mov     r13d, [rsp+0A8h+arg_10]
0x180035ef4  jmp     loc_180036157
0x180035ef9  mov     edx, r13d; unsigned int
0x180035efc  xor     ecx, ecx; Src
0x180035efe  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x180035f03  mov     r14, rax
0x180035f06  mov     [rsp+0A8h+var_60], rax
0x180035f0b  test    rax, rax
0x180035f0e  jnz     short loc_180035F3D
0x180035f10  mov     edx, 8007000Eh; int
0x180035f15  mov     edi, edx
0x180035f17  mov     [rsp+0A8h+var_78], edx
0x180035f1b  mov     ecx, 1000325h; unsigned int
0x180035f20  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035f25  nop
0x180035f26  mov     rcx, rbx
0x180035f29  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035f2f  nop
0x180035f30  mov     r13d, [rsp+0A8h+arg_10]
0x180035f38  jmp     loc_180036157
0x180035f3d  lea     r8, aCnEnrollmentSe; "CN=Enrollment Services,CN=Public Key Se"...
0x180035f44  lea     rdx, [r13+1]; unsigned __int64
0x180035f48  mov     rcx, r14; unsigned __int16 *
0x180035f4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035f50  mov     r8, r15; unsigned __int16 *
0x180035f53  lea     rdx, [r13+1]; unsigned __int64
0x180035f57  mov     rcx, r14; unsigned __int16 *
0x180035f5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035f5f  mov     r13d, [rsp+0A8h+arg_10]
0x180035f67  mov     rax, [rsp+0A8h+arg_0]
0x180035f6f  test    rax, rax
0x180035f72  jz      loc_1800360DC
0x180035f78  inc     rdi
0x180035f7b  cmp     [rax+rdi*2], si
0x180035f7f  jnz     short loc_180035F78
0x180035f81  add     rdi, 29h ; ')'
0x180035f85  cmp     rdi, 10000h
0x180035f8c  jbe     short loc_180035FB3
0x180035f8e  mov     edx, 80070216h; int
0x180035f93  mov     edi, edx
0x180035f95  mov     [rsp+0A8h+var_78], edx
0x180035f99  mov     ecx, 10F0325h; unsigned int
0x180035f9e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035fa3  nop
0x180035fa4  mov     rcx, rbx
0x180035fa7  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035fad  nop
0x180035fae  jmp     loc_180036142
0x180035fb3  mov     edx, edi; unsigned int
0x180035fb5  xor     ecx, ecx; Src
0x180035fb7  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x180035fbc  mov     r12, rax
0x180035fbf  mov     [rsp+0A8h+var_58], rax
0x180035fc4  test    rax, rax
0x180035fc7  jnz     short loc_180035FEE
0x180035fc9  mov     edx, 8007000Eh; int
0x180035fce  mov     edi, edx
0x180035fd0  mov     [rsp+0A8h+var_78], edx
0x180035fd4  mov     ecx, 1160325h; unsigned int
0x180035fd9  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035fde  nop
0x180035fdf  mov     rcx, rbx
0x180035fe2  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035fe8  nop
0x180035fe9  jmp     loc_180036142
0x180035fee  lea     eax, [rdi+1]
0x180035ff1  mov     edi, eax
0x180035ff3  lea     r8, asc_1800B48BC; "(&"
0x180035ffa  mov     edx, eax; unsigned __int64
0x180035ffc  mov     rcx, r12; unsigned __int16 *
0x180035fff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036004  lea     r8, aObjectcategory_0; "(objectCategory=pKIEnrollmentService)"
0x18003600b  mov     edx, edi; unsigned __int64
0x18003600d  mov     rcx, r12; unsigned __int16 *
0x180036010  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036015  mov     r8, [rsp+0A8h+arg_0]; unsigned __int16 *
0x18003601d  mov     edx, edi; unsigned __int64
0x18003601f  mov     rcx, r12; unsigned __int16 *
0x180036022  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036027  lea     r8, asc_1800B3FAC; ")"
0x18003602e  mov     edx, edi; unsigned __int64
0x180036030  mov     rcx, r12; unsigned __int16 *
0x180036033  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036038  mov     rdx, r12
0x18003603b  jmp     loc_1800360E3
0x180036040  mov     [rsp+0A8h+var_80], rsi
0x180036045  lea     rax, [rsp+0A8h+ld]
0x18003604a  mov     [rsp+0A8h+var_88], rax
0x18003604f  xor     r9d, r9d
0x180036052  lea     edx, [r9+8]
0x180036056  xor     ecx, ecx
0x180036058  lea     r8d, [r9+2]
0x18003605c  call    myRobustLdapBindEx
0x180036061  mov     edi, eax
0x180036063  mov     [rsp+0A8h+var_78], eax
0x180036067  test    eax, eax
0x180036069  jz      short loc_180036090
0x18003606b  mov     r9d, 8007052Bh; int
0x180036071  mov     r8d, eax; int
0x180036074  mov     edx, 0E10325h; unsigned int
0x180036079  xor     ecx, ecx; unsigned __int16 *
0x18003607b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180036080  nop
0x180036081  mov     rcx, rbx
0x180036084  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18003608a  nop
0x18003608b  jmp     loc_180036180
0x180036090  test    r14, r14
0x180036093  jz      loc_180035E6A
0x180036099  mov     rcx, r14; Src
0x18003609c  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x1800360a1  mov     r14, rax
0x1800360a4  mov     [rsp+0A8h+var_60], rax
0x1800360a9  test    rax, rax
0x1800360ac  jnz     short loc_1800360D3
0x1800360ae  mov     edx, 8007000Eh; int
0x1800360b3  mov     edi, edx
0x1800360b5  mov     [rsp+0A8h+var_78], edx
0x1800360b9  mov     ecx, 0E80325h; unsigned int
0x1800360be  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800360c3  nop
0x1800360c4  mov     rcx, rbx
0x1800360c7  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800360cd  nop
0x1800360ce  jmp     loc_180036180
0x1800360d3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800360d7  jmp     loc_180035F67
0x1800360dc  lea     rdx, aObjectcategory_0; "(objectCategory=pKIEnrollmentService)"
0x1800360e3  mov     rax, [rsp+0A8h+arg_18]
0x1800360eb  mov     [rsp+0A8h+var_88], rax; struct CCAInfo **
0x1800360f0  mov     r9d, r13d; unsigned int
0x1800360f3  mov     r8, r14; unsigned __int16 *
0x1800360f6  mov     rcx, [rsp+0A8h+ld]; ld
0x1800360fb  call    ?_ProcessFind@CCAInfo@@KAJPEAUldap@@PEBG1KPEAPEAV1@@Z; CCAInfo::_ProcessFind(ldap *,ushort const *,ushort const *,ulong,CCAInfo * *)
0x180036100  mov     edi, eax
0x180036102  mov     [rsp+0A8h+var_78], eax
0x180036106  test    eax, eax
0x180036108  jz      short loc_180036123
0x18003610a  mov     edx, eax; int
0x18003610c  mov     ecx, 1260325h; unsigned int
0x180036111  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180036116  nop
0x180036117  mov     rcx, rbx
0x18003611a  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180036120  nop
0x180036121  jmp     short loc_180036142
0x180036123  mov     rcx, rbx
0x180036126  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18003612c  nop
0x18003612d  jmp     short loc_180036142
0x18003612f  mov     edi, [rsp+0A8h+var_78]
0x180036133  mov     r12, [rsp+0A8h+var_58]
0x180036138  mov     r14, [rsp+0A8h+var_60]
0x18003613d  mov     r15, [rsp+0A8h+var_68]
0x180036142  test    r14, r14
0x180036145  jz      short loc_18003614F
0x180036147  mov     rcx, r14; unsigned __int16 *
0x18003614a  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18003614f  mov     r13d, [rsp+0A8h+arg_10]
0x180036157  test    r15, r15
0x18003615a  jz      short loc_180036164
0x18003615c  mov     rcx, r15; unsigned __int16 *
0x18003615f  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x180036164  mov     rcx, [rsp+0A8h+var_50]; unsigned __int16 *
0x180036169  test    rcx, rcx
0x18003616c  jz      short loc_180036173
0x18003616e  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x180036173  test    r12, r12
0x180036176  jz      short loc_180036180
0x180036178  mov     rcx, r12; unsigned __int16 *
0x18003617b  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x180036180  bt      r13d, 0Bh
0x180036185  jb      short loc_180036197
0x180036187  mov     rcx, [rsp+0A8h+ld]; ld
0x18003618c  test    rcx, rcx
0x18003618f  jz      short loc_180036197
0x180036191  call    cs:__imp_ldap_unbind
0x180036197  mov     eax, edi
0x180036199  add     rsp, 70h
0x18003619d  pop     r15
0x18003619f  pop     r14
0x1800361a1  pop     r13
0x1800361a3  pop     r12
0x1800361a5  pop     rdi
0x1800361a6  pop     rsi
0x1800361a7  pop     rbx
0x1800361a8  retn
```
