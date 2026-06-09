# CCertTypeInfo::Create(ushort const *,void *,CCertTypeInfo * *)

- ea: `0x18002fa68`
- end: `0x18002fc1e`
- name: `?Create@CCertTypeInfo@@SAJPEBGPEAXPEAPEAV1@@Z`
- size: `438`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ldap *, struct CCertTypeInfo **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002dbe0`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000eac0`
- `0x180011600`
- `0x180012260`
- `0x180014fac`
- `0x18002bd08`
- `0x18002fa14`
- `0x18002fa68`
- `0x1800328a4`
- `0x180038262`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fbf3`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18002fb0c`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18002fb0c`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::Create(const unsigned __int16 *a1, struct ldap *a2, struct CCertTypeInfo **a3)
{
  unsigned __int16 *v6; // rsi
  CCertTypeInfo *v7; // rax
  unsigned int v8; // edx
  CCertTypeInfo *v9; // rdi
  unsigned int v10; // ebx
  ULONG optionW; // eax
  unsigned int v12; // r9d
  int TargetMachineDomainDnsName; // eax
  unsigned __int16 **v15; // [rsp+20h] [rbp-89h]
  const unsigned __int16 *v16; // [rsp+40h] [rbp-69h] BYREF
  int v17; // [rsp+48h] [rbp-61h]
  const wchar_t *v18; // [rsp+50h] [rbp-59h]
  int v19; // [rsp+80h] [rbp-29h]
  int v20; // [rsp+84h] [rbp-25h]
  int v21; // [rsp+88h] [rbp-21h]
  int v22; // [rsp+A4h] [rbp-5h]
  HLOCAL hMem; // [rsp+A8h] [rbp-1h] BYREF
  unsigned __int16 *v24; // [rsp+120h] [rbp+77h] BYREF
  LPCWSTR outvalue; // [rsp+128h] [rbp+7Fh] BYREF

  outvalue = 0;
  v6 = 0;
  v24 = 0;
  if ( !a3 || !a1 )
    return 2147500035LL;
  memset_0(&v16, 0, 0x98u);
  v7 = (CCertTypeInfo *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v9 = CCertTypeInfo::CCertTypeInfo(v7, 1);
  else
    v9 = 0;
  if ( v9 )
  {
    if ( a2 )
    {
      optionW = ldap_get_optionW(a2, 48, &outvalue);
      if ( optionW )
      {
        v10 = myHLdapError3(a2, optionW, 0, v12, v15);
        CSPrintErrorLineFileData2(a1, 0xC7E0328u, v10, 0);
        goto LABEL_17;
      }
      TargetMachineDomainDnsName = myGetTargetMachineDomainDnsName(outvalue, 0, 0, &v24);
      v10 = TargetMachineDomainDnsName;
      if ( TargetMachineDomainDnsName )
      {
        CSPrintErrorLineFile(0xC860328u, TargetMachineDomainDnsName);
        v6 = v24;
        goto LABEL_17;
      }
      v6 = v24;
    }
    v16 = a1;
    v17 = 0;
    v18 = L"O:%1-519G:%1-519D:P(A;;RPLCLORC;;;AU)(A;;CCDCLCSWRPWPDTLOSDRCWDWO;;;%1-512)(A;;CCDCLCSWRPWPDTLOSDRCWDWO;;;%1-5"
           "19)(OA;;WPRPCR;0e10c968-78fb-11d2-90d4-00c04f79dc55;;%1-512)(OA;;WPRPCR;0e10c968-78fb-11d2-90d4-00c04f79dc55;;%1-519)";
    v21 = 100;
    v22 = 2;
    v19 = 157680000;
    v20 = 1209600;
    v10 = I_CAOIDCreateNew(1u, v8, (unsigned __int16 **)&hMem, a2);
    if ( !v10 )
    {
      v10 = CCertTypeInfo::_LoadFromDefaults(v9, &v16, v6);
      if ( !v10 )
      {
        *a3 = v9;
        v9 = 0;
      }
    }
    goto LABEL_17;
  }
  v10 = -2147024882;
LABEL_17:
  if ( hMem )
    LocalFree(hMem);
  if ( v9 )
    CCertTypeInfo::`scalar deleting destructor'(v9, v8);
  if ( v6 )
    LocalFree(v6);
  return v10;
}

```

## disassembly

```asm
0x18002fa68  mov     [rsp-8+arg_0], rbx
0x18002fa6d  mov     [rsp-8+arg_8], rsi
0x18002fa72  push    rbp
0x18002fa73  push    rdi
0x18002fa74  push    r12
0x18002fa76  push    r14
0x18002fa78  push    r15
0x18002fa7a  lea     rbp, [rsp-37h]
0x18002fa7f  sub     rsp, 0E0h
0x18002fa86  mov     r12, r8
0x18002fa89  mov     r14, rdx
0x18002fa8c  mov     r15, rcx
0x18002fa8f  mov     [rbp+57h+outvalue], 0
0x18002fa97  xor     esi, esi
0x18002fa99  mov     [rbp+57h+arg_10], rsi
0x18002fa9d  test    r8, r8
0x18002faa0  jz      loc_18002FBFD
0x18002faa6  test    rcx, rcx
0x18002faa9  jz      loc_18002FBFD
0x18002faaf  xor     edx, edx; Val
0x18002fab1  mov     r8d, 98h; Size
0x18002fab7  lea     rcx, [rbp+57h+var_C0]; void *
0x18002fabb  call    memset_0
0x18002fac0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002fac7  mov     ecx, 0C0h; unsigned __int64
0x18002facc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002fad1  mov     [rbp+57h+var_D0], rax
0x18002fad5  test    rax, rax
0x18002fad8  jz      short loc_18002FAEA
0x18002fada  lea     edx, [rsi+1]; int
0x18002fadd  mov     rcx, rax; this
0x18002fae0  call    ??0CCertTypeInfo@@QEAA@H@Z; CCertTypeInfo::CCertTypeInfo(int)
0x18002fae5  mov     rdi, rax
0x18002fae8  jmp     short loc_18002FAEC
0x18002faea  xor     edi, edi
0x18002faec  test    rdi, rdi
0x18002faef  jnz     short loc_18002FAFB
0x18002faf1  mov     ebx, 8007000Eh
0x18002faf6  jmp     loc_18002FBCF
0x18002fafb  test    r14, r14
0x18002fafe  jz      short loc_18002FB6B
0x18002fb00  lea     r8, [rbp+57h+outvalue]; outvalue
0x18002fb04  mov     edx, 30h ; '0'; option
0x18002fb09  mov     rcx, r14; ld
0x18002fb0c  call    cs:__imp_ldap_get_optionW
0x18002fb12  test    eax, eax
0x18002fb14  jz      short loc_18002FB3D
0x18002fb16  xor     r8d, r8d; unsigned int
0x18002fb19  mov     edx, eax; unsigned int
0x18002fb1b  mov     rcx, r14; ld
0x18002fb1e  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002fb23  mov     ebx, eax
0x18002fb25  xor     r9d, r9d; int
0x18002fb28  mov     r8d, eax; int
0x18002fb2b  mov     edx, 0C7E0328h; unsigned int
0x18002fb30  mov     rcx, r15; unsigned __int16 *
0x18002fb33  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002fb38  jmp     loc_18002FBCF
0x18002fb3d  lea     r9, [rbp+57h+arg_10]; unsigned __int16 **
0x18002fb41  xor     r8d, r8d; unsigned __int16 **
0x18002fb44  xor     edx, edx; unsigned __int16 **
0x18002fb46  mov     rcx, [rbp+57h+outvalue]; lpString
0x18002fb4a  call    ?myGetTargetMachineDomainDnsName@@YAJPEBGPEAPEAG11@Z; myGetTargetMachineDomainDnsName(ushort const *,ushort * *,ushort * *,ushort * *)
0x18002fb4f  mov     ebx, eax
0x18002fb51  test    eax, eax
0x18002fb53  jz      short loc_18002FB67
0x18002fb55  mov     edx, eax; int
0x18002fb57  mov     ecx, 0C860328h; unsigned int
0x18002fb5c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fb61  mov     rsi, [rbp+57h+arg_10]
0x18002fb65  jmp     short loc_18002FBCF
0x18002fb67  mov     rsi, [rbp+57h+arg_10]
0x18002fb6b  mov     [rbp+57h+var_C0], r15
0x18002fb6f  mov     [rbp+57h+var_B8], 0
0x18002fb76  lea     rax, aO1519g1519dPAR; "O:%1-519G:%1-519D:P(A;;RPLCLORC;;;AU)(A"...
0x18002fb7d  mov     [rbp+57h+var_B0], rax
0x18002fb81  mov     [rbp+57h+var_78], 64h ; 'd'
0x18002fb88  mov     [rbp+57h+var_5C], 2
0x18002fb8f  mov     [rbp+57h+var_80], 9660180h
0x18002fb96  mov     [rbp+57h+var_7C], 127500h
0x18002fb9d  mov     r9, r14; struct ldap *
0x18002fba0  lea     r8, [rbp+57h+hMem]; unsigned __int16 **
0x18002fba4  mov     ecx, 1; unsigned int
0x18002fba9  call    ?I_CAOIDCreateNew@@YAJKKPEAPEAGPEAUldap@@@Z; I_CAOIDCreateNew(ulong,ulong,ushort * *,ldap *)
0x18002fbae  mov     ebx, eax
0x18002fbb0  test    eax, eax
0x18002fbb2  jnz     short loc_18002FBCF
0x18002fbb4  mov     r8, rsi; unsigned __int16 *
0x18002fbb7  lea     rdx, [rbp+57h+var_C0]; struct _CERT_TYPE_DEFAULT *
0x18002fbbb  mov     rcx, rdi; this
0x18002fbbe  call    ?_LoadFromDefaults@CCertTypeInfo@@IEAAJPEAU_CERT_TYPE_DEFAULT@@PEAG@Z; CCertTypeInfo::_LoadFromDefaults(_CERT_TYPE_DEFAULT *,ushort *)
0x18002fbc3  mov     ebx, eax
0x18002fbc5  test    eax, eax
0x18002fbc7  jnz     short loc_18002FBCF
0x18002fbc9  mov     [r12], rdi
0x18002fbcd  xor     edi, edi
0x18002fbcf  mov     rcx, [rbp+57h+hMem]; hMem
0x18002fbd3  test    rcx, rcx
0x18002fbd6  jz      short loc_18002FBDE
0x18002fbd8  call    cs:__imp_LocalFree
0x18002fbde  test    rdi, rdi
0x18002fbe1  jz      short loc_18002FBEB
0x18002fbe3  mov     rcx, rdi; this
0x18002fbe6  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x18002fbeb  test    rsi, rsi
0x18002fbee  jz      short loc_18002FBF9
0x18002fbf0  mov     rcx, rsi; hMem
0x18002fbf3  call    cs:__imp_LocalFree
0x18002fbf9  mov     eax, ebx
0x18002fbfb  jmp     short loc_18002FC02
0x18002fbfd  mov     eax, 80004003h
0x18002fc02  lea     r11, [rsp+100h+var_20]
0x18002fc0a  mov     rbx, [r11+30h]
0x18002fc0e  mov     rsi, [r11+38h]
0x18002fc12  mov     rsp, r11
0x18002fc15  pop     r15
0x18002fc17  pop     r14
0x18002fc19  pop     r12
0x18002fc1b  pop     rdi
0x18002fc1c  pop     rbp
0x18002fc1d  retn
```
