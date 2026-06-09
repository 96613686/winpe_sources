# LDAPDictionary::insert(IAttributesRaw *,ldapmsg *)

- ea: `0x180024dcc`
- end: `0x1800250fc`
- name: `?insert@LDAPDictionary@@QEBAXPEAUIAttributesRaw@@PEAUldapmsg@@@Z`
- size: `816`
- prototype: `void(LDAPDictionary *__hidden this, struct IAttributesRaw *, struct ldapmsg *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180024630`

## callees

- `0x18000b2a0`
- `0x18000b648`
- `0x18000b81c`
- `0x18000be24`
- `0x18000e754`
- `0x1800169e0`
- `0x18001b5bc`
- `0x18001db68`
- `0x180024dcc`
- `0x1800254a0`
- `0x18002752c`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!_lfind` at `0x180024ebb`
- `msvcrt!_lfind` at `0x180024ebb`
- `WLDAP32!__imp_ldap_get_optionW` at `0x180024ff7`
- `WLDAP32!__imp_ldap_get_optionW` at `0x180024ff7`
- `WLDAP32!__imp_LdapGetLastError` at `0x180024fc7`
- `WLDAP32!__imp_LdapGetLastError` at `0x180024fc7`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180024fd1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180024fd1`
- `WLDAP32!__imp_ldap_first_entry` at `0x180024e33`
- `WLDAP32!__imp_ldap_first_entry` at `0x180024e33`
- `WLDAP32!__imp_ldap_count_values_len` at `0x180024f38`
- `WLDAP32!__imp_ldap_count_values_len` at `0x180024f38`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180024fa4`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180024fa4`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180024e78`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180024e78`
- `WLDAP32!__imp_ldap_get_dnW` at `0x180024e42`
- `WLDAP32!__imp_ldap_get_dnW` at `0x180024e42`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180024f1e`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180024f1e`
- `WLDAP32!__imp_ldap_memfreeW` at `0x180024e5e`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800250a4`
- `WLDAP32!__imp_ldap_memfreeW` at `0x180024e5e`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800250a4`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x180024fbc`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x180024fbc`
- `WLDAP32!__imp_ldap_conn_from_msg` at `0x180024e03`
- `WLDAP32!__imp_ldap_conn_from_msg` at `0x180024e03`

## string_xrefs

- `0x180025058`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LDAPDictionary::insert(LDAPDictionary *this, struct IAttributesRaw *a2, struct ldapmsg *a3)
{
  LDAP *v5; // r14
  LDAPMessage *entry; // r15
  unsigned __int16 *dnW; // rbx
  PWCHAR i; // rax
  WCHAR *v9; // rbx
  _DWORD *v10; // rdi
  int v11; // r9d
  struct berval **values_lenW; // rax
  struct berval **v13; // rbx
  ULONG v14; // eax
  __int64 v15; // rsi
  __int64 v16; // rax
  bool v17; // r8
  ULONG LastError; // eax
  char v19; // si
  int v20; // edx
  signed int v21; // edi
  WCHAR *v22; // rcx
  PVOID *v23; // rdx
  const wchar_t *v24; // rbx
  WCHAR *Key; // [rsp+40h] [rbp-C0h] BYREF
  BerElement *ptr[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h]
  char v30; // [rsp+74h] [rbp-8Ch]
  _BYTE v31[136]; // [rsp+78h] [rbp-88h] BYREF

  v5 = ldap_conn_from_msg(0, a3);
  v27 = v31;
  v28 = v31;
  v29 = 8;
  v30 = 0;
  entry = ldap_first_entry(v5, a3);
  dnW = ldap_get_dnW(v5, entry);
  IASStoreFQUserName(a2, DS_FQDN_1779_NAME, dnW);
  ldap_memfreeW(dnW);
  ptr[0] = 0;
  for ( i = ldap_first_attributeW(v5, entry, ptr); ; i = ldap_next_attributeW(v5, entry, ptr[0]) )
  {
    v9 = i;
    if ( !i )
      break;
    Key = i;
    v10 = _lfind(&Key, Base, &NumOfElements, 0x20u, LDAPDictionary::compare);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Inserting attribute %S.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_c13ac4c20408372c887c1d9f2960a592_Traceguids,
          v11,
          (__int64)v9);
      }
      values_lenW = ldap_get_values_lenW(v5, entry, v9);
      v13 = values_lenW;
      ptr[1] = (BerElement *)values_lenW;
      if ( !values_lenW )
      {
        LastError = LdapGetLastError();
        v19 = LastError;
        v21 = LdapMapErrorToWin32(LastError);
        if ( v21 )
        {
          Key = 0;
          if ( ldap_get_optionW(v5, 51, &Key) )
          {
            v22 = 0;
            Key = 0;
          }
          else
          {
            v22 = Key;
          }
          v23 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v24 = L"Failed to get extended error info";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in "
                        "%s. Code = 0x%X \n"
                        "Extended error info: %S");
            if ( Key )
              v24 = Key;
            WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"ldap_get_values_lenW", v19, (__int64)v24);
            v22 = Key;
          }
          if ( v22 )
            ldap_memfreeW(v22);
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          IASTL::issue_error((IASTL *)(unsigned int)v21, (int)v23);
        }
        IASTL::issue_error((IASTL *)0x8007000ELL, v20);
      }
      v14 = ldap_count_values_len(values_lenW);
      IASTL::IASAttributeVector::reserve((IASTL::IASAttributeVector *)&v27, v14);
      v15 = 0;
      if ( *v13 )
      {
        do
        {
          v16 = IASAttributeFromBerVal((const char **)v13[v15], v10[3]);
          *(_DWORD *)(v16 + 8) = v10[2];
          *(_DWORD *)(v16 + 4) = v10[4];
          IASTL::IASAttributeVector::push_back((IASTL::IASAttributeVector *)&v27, (struct _IASATTRIBUTE *)v16, v17);
          ++v15;
        }
        while ( v13[v15] );
      }
      (*((void (__fastcall **)(struct IAttributesRaw *, _BYTE *, _BYTE *))v10 + 3))(a2, v27, v28);
      IASTL::IASAttributeVector::clear((IASTL::IASAttributeVector *)&v27);
      ldap_value_free_len(v13);
    }
  }
  IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>((IASTL::IASAttributeVector *)&v27);
}

```

## disassembly

```asm
0x180024dcc  mov     [rsp-8+arg_0], rbx
0x180024dd1  mov     [rsp-8+arg_18], rsi
0x180024dd6  push    rbp
0x180024dd7  push    rdi
0x180024dd8  push    r12
0x180024dda  push    r14
0x180024ddc  push    r15
0x180024dde  lea     rbp, [rsp-10h]
0x180024de3  sub     rsp, 110h
0x180024dea  mov     rax, cs:__security_cookie
0x180024df1  xor     rax, rsp
0x180024df4  mov     [rbp+30h+var_30], rax
0x180024df8  mov     rbx, r8
0x180024dfb  mov     r12, rdx
0x180024dfe  mov     rdx, r8; res
0x180024e01  xor     ecx, ecx; PrimaryConn
0x180024e03  call    cs:__imp_ldap_conn_from_msg
0x180024e09  mov     r14, rax
0x180024e0c  lea     rax, [rsp+130h+var_B8]
0x180024e11  mov     [rsp+130h+var_D0], rax
0x180024e16  lea     rax, [rsp+130h+var_B8]
0x180024e1b  mov     [rsp+130h+var_C8], rax
0x180024e20  mov     [rsp+130h+var_C0], 8
0x180024e28  mov     [rsp+130h+var_BC], 0
0x180024e2d  mov     rdx, rbx; res
0x180024e30  mov     rcx, r14; ld
0x180024e33  call    cs:__imp_ldap_first_entry
0x180024e39  mov     r15, rax
0x180024e3c  mov     rdx, rax; entry
0x180024e3f  mov     rcx, r14; ld
0x180024e42  call    cs:__imp_ldap_get_dnW
0x180024e48  mov     rbx, rax
0x180024e4b  mov     r8, rax; unsigned __int16 *
0x180024e4e  mov     edx, 1; enum DS_NAME_FORMAT
0x180024e53  mov     rcx, r12; struct IAttributesRaw *
0x180024e56  call    ?IASStoreFQUserName@@YAJPEAUIAttributesRaw@@W4DS_NAME_FORMAT@@PEBG@Z; IASStoreFQUserName(IAttributesRaw *,DS_NAME_FORMAT,ushort const *)
0x180024e5b  mov     rcx, rbx; Block
0x180024e5e  call    cs:__imp_ldap_memfreeW
0x180024e64  mov     [rsp+130h+ptr], 0
0x180024e6d  lea     r8, [rsp+130h+ptr]; ptr
0x180024e72  mov     rdx, r15; entry
0x180024e75  mov     rcx, r14; ld
0x180024e78  call    cs:__imp_ldap_first_attributeW
0x180024e7e  lea     rsi, WPP_GLOBAL_Control
0x180024e85  mov     rbx, rax
0x180024e88  test    rax, rax
0x180024e8b  jz      loc_1800250CA
0x180024e91  mov     [rsp+130h+Key], rax
0x180024e96  lea     rax, ?compare@LDAPDictionary@@KAHPEBX0@Z; LDAPDictionary::compare(void const *,void const *)
0x180024e9d  mov     [rsp+130h+CompareFunction], rax; CompareFunction
0x180024ea2  mov     r9d, 20h ; ' '; SizeOfElements
0x180024ea8  lea     r8, NumOfElements; NumOfElements
0x180024eaf  mov     rdx, cs:Base; Base
0x180024eb6  lea     rcx, [rsp+130h+Key]; Key
0x180024ebb  call    cs:__imp__lfind
0x180024ec1  mov     rdi, rax
0x180024ec4  test    rax, rax
0x180024ec7  jz      loc_180024FB1
0x180024ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ed4  cmp     rcx, rsi
0x180024ed7  jz      short loc_180024F15
0x180024ed9  cmp     byte ptr [rcx+19h], 4
0x180024edd  jb      short loc_180024F15
0x180024edf  test    byte ptr [rcx+1Ch], 4
0x180024ee3  jz      short loc_180024F15
0x180024ee5  mov     rdx, rbx
0x180024ee8  lea     rcx, aInsertingAttri; "Inserting attribute %S."
0x180024eef  call    WppDbgPrint
0x180024ef4  mov     edx, 0Ah
0x180024ef9  mov     [rsp+130h+CompareFunction], rbx
0x180024efe  lea     r8, WPP_c13ac4c20408372c887c1d9f2960a592_Traceguids
0x180024f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f0c  mov     rcx, [rcx+10h]
0x180024f10  call    WPP_SF_sS
0x180024f15  mov     r8, rbx; attr
0x180024f18  mov     rdx, r15; Message
0x180024f1b  mov     rcx, r14; ExternalHandle
0x180024f1e  call    cs:__imp_ldap_get_values_lenW
0x180024f24  mov     rbx, rax
0x180024f27  mov     [rsp+130h+var_E0], rax
0x180024f2c  test    rax, rax
0x180024f2f  jz      loc_180024FC7
0x180024f35  mov     rcx, rax; vals
0x180024f38  call    cs:__imp_ldap_count_values_len
0x180024f3e  mov     edx, eax; unsigned int
0x180024f40  lea     rcx, [rsp+130h+var_D0]; this
0x180024f45  call    ?reserve@IASAttributeVector@IASTL@@QEAAXK@Z; IASTL::IASAttributeVector::reserve(ulong)
0x180024f4a  xor     esi, esi
0x180024f4c  cmp     [rbx], rsi
0x180024f4f  jz      short loc_180024F80
0x180024f51  mov     edx, [rdi+0Ch]
0x180024f54  mov     rcx, [rbx+rsi*8]
0x180024f58  call    ?IASAttributeFromBerVal@@YAPEAU_IASATTRIBUTE@@AEBUberval@@W4IASTYPEENUM@@@Z; IASAttributeFromBerVal(berval const &,IASTYPEENUM)
0x180024f5d  mov     ecx, [rdi+8]
0x180024f60  mov     [rax+8], ecx
0x180024f63  mov     ecx, [rdi+10h]
0x180024f66  mov     [rax+4], ecx
0x180024f69  mov     rdx, rax; struct _IASATTRIBUTE *
0x180024f6c  lea     rcx, [rsp+130h+var_D0]; this
0x180024f71  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x180024f76  inc     rsi
0x180024f79  cmp     qword ptr [rbx+rsi*8], 0
0x180024f7e  jnz     short loc_180024F51
0x180024f80  mov     r8, [rsp+130h+var_C8]
0x180024f85  mov     rdx, [rsp+130h+var_D0]
0x180024f8a  mov     rcx, r12
0x180024f8d  mov     rax, [rdi+18h]
0x180024f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f96  lea     rcx, [rsp+130h+var_D0]; this
0x180024f9b  call    ?clear@IASAttributeVector@IASTL@@QEAAXXZ; IASTL::IASAttributeVector::clear(void)
0x180024fa0  nop
0x180024fa1  mov     rcx, rbx; vals
0x180024fa4  call    cs:__imp_ldap_value_free_len
0x180024faa  lea     rsi, WPP_GLOBAL_Control
0x180024fb1  mov     r8, [rsp+130h+ptr]; ptr
0x180024fb6  mov     rdx, r15; entry
0x180024fb9  mov     rcx, r14; ld
0x180024fbc  call    cs:__imp_ldap_next_attributeW
0x180024fc2  jmp     loc_180024E85
0x180024fc7  call    cs:__imp_LdapGetLastError
0x180024fcd  mov     esi, eax
0x180024fcf  mov     ecx, eax; LdapError
0x180024fd1  call    cs:__imp_LdapMapErrorToWin32
0x180024fd7  mov     edi, eax
0x180024fd9  test    eax, eax
0x180024fdb  jz      loc_1800250BF
0x180024fe1  mov     [rsp+130h+Key], 0
0x180024fea  lea     r8, [rsp+130h+Key]; outvalue
0x180024fef  mov     edx, 33h ; '3'; option
0x180024ff4  mov     rcx, r14; ld
0x180024ff7  call    cs:__imp_ldap_get_optionW
0x180024ffd  test    eax, eax
0x180024fff  jz      short loc_18002500A
0x180025001  xor     ecx, ecx
0x180025003  mov     [rsp+130h+Key], rcx
0x180025008  jmp     short loc_18002500F
0x18002500a  mov     rcx, [rsp+130h+Key]
0x18002500f  mov     rax, cs:WPP_GLOBAL_Control
0x180025016  lea     rdx, WPP_GLOBAL_Control
0x18002501d  cmp     rax, rdx
0x180025020  jz      short loc_18002509F
0x180025022  cmp     byte ptr [rax+19h], 2
0x180025026  jb      short loc_18002509F
0x180025028  test    byte ptr [rax+1Ch], 4
0x18002502c  jz      short loc_18002509F
0x18002502e  lea     rbx, aFailedToGetExt; "Failed to get extended error info"
0x180025035  mov     rax, rbx
0x180025038  test    rcx, rcx
0x18002503b  cmovnz  rax, rcx
0x18002503f  mov     [rsp+130h+CompareFunction], rax
0x180025044  mov     r9d, esi
0x180025047  lea     r14, aLdapGetValuesL; "ldap_get_values_lenW"
0x18002504e  mov     r8, r14
0x180025051  lea     rdx, aNpssvc; "NPSSVC"
0x180025058  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002505f  call    WppDbgPrint
0x180025064  mov     rax, [rsp+130h+Key]
0x180025069  test    rax, rax
0x18002506c  cmovnz  rbx, rax
0x180025070  mov     edx, 0Bh
0x180025075  mov     [rsp+130h+var_100], rbx; __int64
0x18002507a  mov     dword ptr [rsp+130h+var_108], esi; char
0x18002507e  mov     [rsp+130h+CompareFunction], r14; __int64
0x180025083  lea     r8, WPP_c13ac4c20408372c887c1d9f2960a592_Traceguids
0x18002508a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025091  mov     rcx, [rcx+10h]; LoggerHandle
0x180025095  call    WPP_SF_ssDS
0x18002509a  mov     rcx, [rsp+130h+Key]; Block
0x18002509f  test    rcx, rcx
0x1800250a2  jz      short loc_1800250AA
0x1800250a4  call    cs:__imp_ldap_memfreeW
0x1800250aa  test    edi, edi
0x1800250ac  jle     short loc_1800250B7
0x1800250ae  movzx   edi, di
0x1800250b1  or      edi, 80070000h
0x1800250b7  mov     ecx, edi; this
0x1800250b9  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x1800250bf  mov     ecx, 8007000Eh; this
0x1800250c4  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x1800250ca  lea     rcx, [rsp+130h+var_D0]; this
0x1800250cf  call    ??1?$IASAttributeVectorWithBuffer@$09@IASTL@@QEAA@XZ; IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>(void)
0x1800250d4  mov     rcx, [rbp+30h+var_30]
0x1800250d8  xor     rcx, rsp; StackCookie
0x1800250db  call    __security_check_cookie
0x1800250e0  lea     r11, [rsp+130h+var_20]
0x1800250e8  mov     rbx, [r11+30h]
0x1800250ec  mov     rsi, [r11+48h]
0x1800250f0  mov     rsp, r11
0x1800250f3  pop     r15
0x1800250f5  pop     r14
0x1800250f7  pop     r12
0x1800250f9  pop     rdi
0x1800250fa  pop     rbp
0x1800250fb  retn
```
