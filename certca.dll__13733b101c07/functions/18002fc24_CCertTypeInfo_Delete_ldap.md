# CCertTypeInfo::Delete(ldap *)

- ea: `0x18002fc24`
- end: `0x18002ff33`
- name: `?Delete@CCertTypeInfo@@QEAAJPEAUldap@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, struct ldap *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002dd30`

## callees

- `0x180005944`
- `0x180005f00`
- `0x1800062d0`
- `0x180008400`
- `0x180008420`
- `0x18000e130`
- `0x18000e52c`
- `0x180010070`
- `0x180011600`
- `0x18002fc24`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fc69`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fcf7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fd2c`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fd91`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fdcd`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fe58`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fc69`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fcf7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fd2c`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fd91`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fdcd`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002fe58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fefe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fefe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002fed6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002fed6`
- `WLDAP32!__imp_ldap_unbind` at `0x18002feee`
- `WLDAP32!__imp_ldap_unbind` at `0x18002feee`
- `WLDAP32!__imp_ldap_delete_sW` at `0x18002fe37`
- `WLDAP32!__imp_ldap_delete_sW` at `0x18002fe37`

## string_xrefs

- `0x18002fe0c`: `CN=Certificate Templates,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::Delete(CCertTypeInfo *this, struct ldap *a2)
{
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // r14
  void (*v6)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  int v7; // eax
  unsigned int v8; // edi
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  unsigned __int16 *v11; // r9
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  unsigned __int16 *v16; // rax
  ULONG v17; // eax
  unsigned int v18; // r9d
  signed int v19; // eax
  bool v20; // cc
  unsigned __int16 **v22; // [rsp+20h] [rbp-A8h]
  struct _SECURITY_ATTRIBUTES *v23; // [rsp+30h] [rbp-98h]
  unsigned __int16 *v24; // [rsp+58h] [rbp-70h] BYREF
  LDAP *v25; // [rsp+60h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int16 *v27; // [rsp+70h] [rbp-58h]
  void (*v28)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+78h] [rbp-50h]
  unsigned __int64 v29; // [rsp+80h] [rbp-48h]
  DWORD v30; // [rsp+E0h] [rbp+18h] BYREF
  LDAP *ld; // [rsp+E8h] [rbp+20h]

  hKey = 0;
  v30 = 0;
  ld = 0;
  v4 = 0;
  v24 = 0;
  v5 = 0;
  v27 = 0;
  v6 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v28 = v6;
  ld = 0;
  v25 = 0;
  if ( a2 )
  {
    ld = a2;
  }
  else
  {
    v7 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, &v25, 0);
    v8 = v7;
    a2 = v25;
    ld = v25;
    if ( v7 )
    {
      CSPrintErrorLineFile(0x9E0336u, v7);
      a2 = ld;
    }
    if ( v8 )
    {
      CSPrintErrorLineFile(0x10F20328u, v8);
      _set_se_translator(v6);
      goto LABEL_17;
    }
  }
  v12 = CAGetAuthoritativeDomainDn(a2, 0, &v24);
  v8 = v12;
  if ( v12 )
  {
    CSPrintErrorLineFile(0x10F50328u, v12);
    _set_se_translator(v6);
    v4 = v24;
  }
  else
  {
    v4 = v24;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v24[v14] );
    do
      ++v13;
    while ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v13) );
    v15 = v13 + v14 + 65;
    v29 = v15;
    if ( v15 > 0x10000 )
    {
      v8 = -2147024362;
      CSPrintErrorLineFile(0x10FB0328u, -2147024362);
      _set_se_translator(v6);
      goto LABEL_23;
    }
    v16 = CertAllocStringLen(0, (int)v15 - 1);
    v5 = v16;
    v27 = v16;
    if ( !v16 )
    {
      v8 = -2147024882;
      CSPrintErrorLineFile(0x11010328u, -2147024882);
      _set_se_translator(v6);
      goto LABEL_23;
    }
    StringCchCopyW(v16, v15, L"CN=");
    StringCchCatW(v5, v15, *((const unsigned __int16 **)this + 1));
    StringCchCatW(v5, v15, L",");
    StringCchCatW(v5, v15, L"CN=Certificate Templates,CN=Public Key Services,CN=Services,");
    StringCchCatW(v5, v15, v4);
    v17 = ldap_delete_sW(ld, v5);
    v8 = myHLdapError3(ld, v17, 0, v18, v22);
    _set_se_translator(v6);
  }
LABEL_17:
  if ( !v8 )
  {
    v19 = ctRegCreateKeyEx(
            (HKEY)((*((_DWORD *)this + 31) != 0) - 0x7FFFFFFFLL),
            v9,
            v10,
            v11,
            (unsigned int)v22,
            0x20019u,
            v23,
            &hKey,
            &v30);
    v8 = v19;
    v20 = v19 <= 0;
    if ( v19 || (v19 = RegDeleteKeyExW(hKey, *((LPCWSTR *)this + 1), 0, 0), v8 = v19, v20 = v19 <= 0, v19) )
    {
      if ( !v20 )
        v8 = (unsigned __int16)v19 | 0x80070000;
    }
    else
    {
      v8 = 0;
    }
  }
LABEL_23:
  if ( v25 )
    ldap_unbind(v25);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    CertFreeString(v5);
  if ( v4 )
    CertFreeString(v4);
  return v8;
}

```

## disassembly

```asm
0x18002fc24  mov     rax, rsp
0x18002fc27  mov     [rax+8], rcx
0x18002fc2b  push    rbx
0x18002fc2c  push    rsi
0x18002fc2d  push    rdi
0x18002fc2e  push    r12
0x18002fc30  push    r13
0x18002fc32  push    r14
0x18002fc34  push    r15
0x18002fc36  sub     rsp, 90h
0x18002fc3d  mov     r12, rdx
0x18002fc40  mov     r13, rcx
0x18002fc43  xor     esi, esi
0x18002fc45  mov     [rax-60h], rsi
0x18002fc49  mov     [rax+18h], esi
0x18002fc4c  mov     [rax-68h], rsi
0x18002fc50  mov     [rax+20h], rsi
0x18002fc54  mov     r15d, esi
0x18002fc57  mov     [rax-70h], rsi
0x18002fc5b  mov     r14d, esi
0x18002fc5e  mov     [rax-58h], rsi
0x18002fc62  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18002fc69  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002fc6f  mov     rbx, rax
0x18002fc72  mov     [rsp+0C8h+var_50], rax
0x18002fc77  mov     [rsp+0C8h+ld], rsi
0x18002fc7f  mov     [rsp+0C8h+var_68], rsi
0x18002fc84  test    r12, r12
0x18002fc87  jz      short loc_18002FC97
0x18002fc89  mov     [rsp+0C8h+ld], r12
0x18002fc91  mov     [rsp+0C8h+var_78], esi
0x18002fc95  jmp     short loc_18002FD03
0x18002fc97  mov     qword ptr [rsp+0C8h+samDesired], rsi
0x18002fc9c  lea     rax, [rsp+0C8h+var_68]
0x18002fca1  mov     [rsp+0C8h+var_A8], rax
0x18002fca6  xor     r9d, r9d
0x18002fca9  lea     edx, [r9+8]
0x18002fcad  xor     ecx, ecx
0x18002fcaf  lea     r8d, [r9+2]
0x18002fcb3  call    myRobustLdapBindEx
0x18002fcb8  mov     edi, eax
0x18002fcba  mov     r12, [rsp+0C8h+var_68]
0x18002fcbf  mov     [rsp+0C8h+ld], r12
0x18002fcc7  test    eax, eax
0x18002fcc9  jz      short loc_18002FCDF
0x18002fccb  mov     edx, eax; int
0x18002fccd  mov     ecx, 9E0336h; unsigned int
0x18002fcd2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fcd7  mov     r12, [rsp+0C8h+ld]
0x18002fcdf  mov     [rsp+0C8h+var_78], edi
0x18002fce3  test    edi, edi
0x18002fce5  jz      short loc_18002FD03
0x18002fce7  mov     edx, edi; int
0x18002fce9  mov     ecx, 10F20328h; unsigned int
0x18002fcee  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fcf3  nop
0x18002fcf4  mov     rcx, rbx
0x18002fcf7  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002fcfd  nop
0x18002fcfe  jmp     loc_18002FE79
0x18002fd03  lea     r8, [rsp+0C8h+var_70]; unsigned __int16 **
0x18002fd08  xor     edx, edx; unsigned __int16 **
0x18002fd0a  mov     rcx, r12; struct ldap *
0x18002fd0d  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x18002fd12  mov     edi, eax
0x18002fd14  mov     [rsp+0C8h+var_78], eax
0x18002fd18  test    eax, eax
0x18002fd1a  jz      short loc_18002FD3D
0x18002fd1c  mov     edx, eax; int
0x18002fd1e  mov     ecx, 10F50328h; unsigned int
0x18002fd23  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fd28  nop
0x18002fd29  mov     rcx, rbx
0x18002fd2c  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002fd32  nop
0x18002fd33  mov     r15, [rsp+0C8h+var_70]
0x18002fd38  jmp     loc_18002FE79
0x18002fd3d  mov     r15, [rsp+0C8h+var_70]
0x18002fd42  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fd46  mov     rcx, rax
0x18002fd49  inc     rcx
0x18002fd4c  cmp     [r15+rcx*2], si
0x18002fd51  jnz     short loc_18002FD49
0x18002fd53  mov     rdx, [r13+8]
0x18002fd57  inc     rax
0x18002fd5a  cmp     [rdx+rax*2], si
0x18002fd5e  jnz     short loc_18002FD57
0x18002fd60  lea     rdi, [rcx+41h]
0x18002fd64  add     rdi, rax
0x18002fd67  mov     [rsp+0C8h+var_48], rdi
0x18002fd6f  cmp     rdi, 10000h
0x18002fd76  jbe     short loc_18002FD9D
0x18002fd78  mov     edi, 80070216h
0x18002fd7d  mov     [rsp+0C8h+var_78], edi
0x18002fd81  mov     edx, edi; int
0x18002fd83  mov     ecx, 10FB0328h; unsigned int
0x18002fd88  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fd8d  nop
0x18002fd8e  mov     rcx, rbx
0x18002fd91  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002fd97  nop
0x18002fd98  jmp     loc_18002FEE4
0x18002fd9d  lea     edx, [rdi-1]; unsigned int
0x18002fda0  xor     ecx, ecx; Src
0x18002fda2  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002fda7  mov     r14, rax
0x18002fdaa  mov     [rsp+0C8h+var_58], rax
0x18002fdaf  test    rax, rax
0x18002fdb2  jnz     short loc_18002FDD9
0x18002fdb4  mov     edi, 8007000Eh
0x18002fdb9  mov     [rsp+0C8h+var_78], edi
0x18002fdbd  mov     edx, edi; int
0x18002fdbf  mov     ecx, 11010328h; unsigned int
0x18002fdc4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fdc9  nop
0x18002fdca  mov     rcx, rbx
0x18002fdcd  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002fdd3  nop
0x18002fdd4  jmp     loc_18002FEE4
0x18002fdd9  lea     r8, aCn_2; "CN="
0x18002fde0  mov     rdx, rdi; unsigned __int64
0x18002fde3  mov     rcx, r14; unsigned __int16 *
0x18002fde6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fdeb  mov     r8, [r13+8]; unsigned __int16 *
0x18002fdef  mov     rdx, rdi; unsigned __int64
0x18002fdf2  mov     rcx, r14; unsigned __int16 *
0x18002fdf5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fdfa  lea     r8, asc_180063424; ","
0x18002fe01  mov     rdx, rdi; unsigned __int64
0x18002fe04  mov     rcx, r14; unsigned __int16 *
0x18002fe07  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe0c  lea     r8, aCnCertificateT_0; "CN=Certificate Templates,CN=Public Key "...
0x18002fe13  mov     rdx, rdi; unsigned __int64
0x18002fe16  mov     rcx, r14; unsigned __int16 *
0x18002fe19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe1e  mov     r8, r15; unsigned __int16 *
0x18002fe21  mov     rdx, rdi; unsigned __int64
0x18002fe24  mov     rcx, r14; unsigned __int16 *
0x18002fe27  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe2c  mov     rdx, r14; dn
0x18002fe2f  mov     rcx, [rsp+0C8h+ld]; ld
0x18002fe37  call    cs:__imp_ldap_delete_sW
0x18002fe3d  xor     r8d, r8d; unsigned int
0x18002fe40  mov     edx, eax; unsigned int
0x18002fe42  mov     rcx, [rsp+0C8h+ld]; ld
0x18002fe4a  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002fe4f  mov     edi, eax
0x18002fe51  mov     [rsp+0C8h+var_78], eax
0x18002fe55  mov     rcx, rbx
0x18002fe58  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002fe5e  nop
0x18002fe5f  jmp     short loc_18002FE79
0x18002fe61  xor     esi, esi
0x18002fe63  mov     r13, [rsp+0C8h+arg_0]
0x18002fe6b  mov     edi, [rsp+0C8h+var_78]
0x18002fe6f  mov     r15, [rsp+0C8h+var_70]
0x18002fe74  mov     r14, [rsp+0C8h+var_58]
0x18002fe79  test    edi, edi
0x18002fe7b  jnz     short loc_18002FEE4
0x18002fe7d  mov     eax, [r13+7Ch]
0x18002fe81  neg     eax
0x18002fe83  sbb     rcx, rcx
0x18002fe86  neg     rcx
0x18002fe89  add     rcx, 0FFFFFFFF80000001h; HKEY
0x18002fe90  lea     rax, [rsp+0C8h+arg_10]
0x18002fe98  mov     [rsp+0C8h+var_88], rax; LPDWORD
0x18002fe9d  lea     rax, [rsp+0C8h+hKey]
0x18002fea2  mov     [rsp+0C8h+var_90], rax; PHKEY
0x18002fea7  mov     [rsp+0C8h+samDesired], 20019h; samDesired
0x18002feaf  call    ?ctRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ctRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18002feb4  mov     edi, eax
0x18002feb6  test    eax, eax
0x18002feb8  jz      short loc_18002FEC7
0x18002feba  jle     short loc_18002FEE4
0x18002febc  movzx   edi, ax
0x18002febf  or      edi, 80070000h
0x18002fec5  jmp     short loc_18002FEE4
0x18002fec7  xor     r9d, r9d; Reserved
0x18002feca  xor     r8d, r8d; samDesired
0x18002fecd  mov     rdx, [r13+8]; lpSubKey
0x18002fed1  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18002fed6  call    cs:__imp_RegDeleteKeyExW
0x18002fedc  mov     edi, eax
0x18002fede  test    eax, eax
0x18002fee0  jnz     short loc_18002FEBA
0x18002fee2  mov     edi, esi
0x18002fee4  mov     rcx, [rsp+0C8h+var_68]; ld
0x18002fee9  test    rcx, rcx
0x18002feec  jz      short loc_18002FEF4
0x18002feee  call    cs:__imp_ldap_unbind
0x18002fef4  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18002fef9  test    rcx, rcx
0x18002fefc  jz      short loc_18002FF04
0x18002fefe  call    cs:__imp_RegCloseKey
0x18002ff04  test    r14, r14
0x18002ff07  jz      short loc_18002FF11
0x18002ff09  mov     rcx, r14; unsigned __int16 *
0x18002ff0c  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002ff11  test    r15, r15
0x18002ff14  jz      short loc_18002FF1E
0x18002ff16  mov     rcx, r15; unsigned __int16 *
0x18002ff19  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002ff1e  mov     eax, edi
0x18002ff20  add     rsp, 90h
0x18002ff27  pop     r15
0x18002ff29  pop     r14
0x18002ff2b  pop     r13
0x18002ff2d  pop     r12
0x18002ff2f  pop     rdi
0x18002ff30  pop     rsi
0x18002ff31  pop     rbx
0x18002ff32  retn
```
