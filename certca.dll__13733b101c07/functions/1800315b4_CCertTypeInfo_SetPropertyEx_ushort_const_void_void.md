# CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)

- ea: `0x1800315b4`
- end: `0x180031989`
- name: `?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z`
- size: `981`
- prototype: `__int64 __fastcall(unsigned __int16 **this, const unsigned __int16 *, unsigned __int16 **, struct ldap *)`
- caller_count: `6`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180012ae8`
- `0x180012f0c`
- `0x18002dc40`
- `0x180031af8`
- `0x180032d6c`
- `0x180033144`

## callees

- `0x1800016e0`
- `0x180001920`
- `0x180002ef0`
- `0x180005944`
- `0x180008400`
- `0x180008610`
- `0x18000ce90`
- `0x18000d520`
- `0x18000e480`
- `0x1800113e0`
- `0x180012f0c`
- `0x18002bd08`
- `0x1800315b4`
- `0x180031af8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003194b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003195a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031968`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003194b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003195a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031968`

## string_xrefs

- `0x180031636`: `msPKI-Template-Schema-Version`
- `0x1800317c1`: `msPKI-Template-Schema-Version`
- `0x180031755`: `msPKI-Template-Minor-Revision`
- `0x180031908`: `msPKI-Cert-Template-OID`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::SetPropertyEx(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ldap *a4)
{
  unsigned __int16 *v4; // r15
  unsigned int v9; // ecx
  int v10; // edx
  unsigned int v11; // ebx
  unsigned int v12; // edx
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edx
  int v17; // r8d
  unsigned int Property; // eax
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  bool v22; // cf
  unsigned int v23; // eax
  HLOCAL hMem; // [rsp+20h] [rbp-20h] BYREF
  HLOCAL v26; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v27[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v28; // [rsp+78h] [rbp+38h] BYREF

  v4 = 0;
  v26 = 0;
  hMem = 0;
  v28 = 0;
  if ( !a2 )
  {
    v9 = 322569000;
LABEL_3:
    v10 = -2147467261;
LABEL_4:
    v11 = v10;
LABEL_5:
    CSPrintErrorLineFile(v9, v10);
    goto LABEL_58;
  }
  if ( !(unsigned int)mylstrcmpNLSub(a2, L"distinguishedName", -1, 1u) )
  {
    v10 = -2147418113;
    v9 = 323027752;
    goto LABEL_4;
  }
  if ( (unsigned int)mylstrcmpNLSub(a2, L"msPKI-Template-Schema-Version", -1, 1u) )
  {
    if ( *((_DWORD *)this + 22) < 2u && (unsigned int)IsV2Property(a2) )
    {
      v16 = 325452584;
    }
    else
    {
      if ( *((_DWORD *)this + 22) >= 3u || !(unsigned int)IsV3Property(a2) )
      {
        v11 = 0;
        if ( (unsigned int)mylstrcmpNLSub(a2, L"cn", -1, 1u) )
          goto LABEL_67;
        if ( !a3 )
        {
          v9 = 326435624;
          goto LABEL_3;
        }
        if ( !*a3 )
        {
          v9 = 326828840;
          goto LABEL_3;
        }
        Property = CCertTypeInfo::GetPropertyEx((CCertTypeInfo *)this, a2, &v26);
        v11 = Property;
        if ( !Property )
        {
LABEL_67:
          if ( (unsigned int)mylstrcmpNLSub(a2, L"msPKI-Template-Minor-Revision", -1, 1u) )
          {
            if ( (unsigned int)mylstrcmpNLSub(a2, L"msPKI-RA-Signature", -1, 1u) )
            {
              if ( (unsigned int)mylstrcmpNLSub(a2, L"msPKI-Minimal-Key-Size", -1, 1u) )
              {
                if ( (unsigned int)mylstrcmpNLSub(a2, L"msPKI-Template-Schema-Version", -1, 1u) )
                {
                  if ( (unsigned int)mylstrcmpNLSub(a2, L"revision", -1, 1u) )
                  {
                    v11 = CCertTypeInfo::SetProperty((CCAProperty **)this, a2, a3);
                    if ( !v11 && v26 && *(_QWORD *)v26 && (unsigned int)mylstrcmpNLSub(*(PCNZWCH *)v26, *a3, -1, 1u) )
                    {
                      v19 = this[1];
                      if ( v19 )
                      {
                        CertFreeString(v19);
                        this[1] = 0;
                      }
                      v20 = CertAllocString(*a3);
                      this[1] = v20;
                      if ( v20 )
                      {
                        v11 = CCertTypeInfo::SetProperty((CCAProperty **)this, L"distinguishedName", a3);
                        if ( !v11 )
                        {
                          v22 = *((_DWORD *)this + 22) < 2u;
                          *((_DWORD *)this + 30) = 1;
                          *((_WORD *)this + 29) = 0;
                          *((_DWORD *)this + 36) = 100;
                          if ( v22 )
                          {
                            if ( !CCertTypeInfo::GetProperty((CCertTypeInfo *)this, L"pKIExtendedKeyUsage", &hMem) )
                              CCertTypeInfo::SetProperty(
                                (CCAProperty **)this,
                                L"msPKI-Certificate-Application-Policy",
                                (unsigned __int16 **)hMem);
                            *((_DWORD *)this + 22) = 2;
                          }
                          v23 = I_CAOIDCreateNew(1, v21, &v28, a4);
                          v4 = v28;
                          v11 = v23;
                          if ( !v23 )
                          {
                            v27[0] = v28;
                            v27[1] = 0;
                            v11 = CCertTypeInfo::SetProperty((CCAProperty **)this, L"msPKI-Cert-Template-OID", v27);
                            if ( !v11 )
                            {
                              v27[0] = 0;
                              v11 = CCertTypeInfo::SetProperty((CCAProperty **)this, L"displayName", v27);
                            }
                          }
                        }
                      }
                      else
                      {
                        v11 = -2147024882;
                      }
                    }
                  }
                  else
                  {
                    *((_DWORD *)this + 36) = *(_DWORD *)a3;
                  }
                }
                else
                {
                  *((_DWORD *)this + 22) = *(_DWORD *)a3;
                }
              }
              else
              {
                *((_DWORD *)this + 20) = *(_DWORD *)a3;
              }
            }
            else
            {
              *((_DWORD *)this + 21) = *(_DWORD *)a3;
            }
          }
          else
          {
            *((_DWORD *)this + 16) = *(_DWORD *)a3;
          }
          goto LABEL_58;
        }
        v17 = Property;
        v16 = 327156520;
LABEL_21:
        CSPrintErrorLineFileData2(a2, v16, v17, 0);
        goto LABEL_58;
      }
      v16 = 325845800;
    }
    v17 = -2147023728;
    v11 = -2147023728;
    goto LABEL_21;
  }
  v12 = *(_DWORD *)a3;
  v13 = *((_DWORD *)this + 22);
  if ( *(_DWORD *)a3 == v13 )
  {
    v14 = CCertTypeInfo::_PersistSchemaVersion((CCertTypeInfo *)this, v12);
    v11 = v14;
    if ( v14 )
    {
      v10 = v14;
      v9 = 324010792;
      goto LABEL_5;
    }
  }
  else
  {
    if ( (unsigned int)(v13 - 2) > 2 || v12 - 2 > 2 )
    {
      v10 = -2147418113;
      v9 = 324993832;
      goto LABEL_4;
    }
    v15 = CCertTypeInfo::_ChangeSchemaVersion((CCertTypeInfo *)this, v12);
    v11 = v15;
    if ( v15 )
    {
      v10 = v15;
      v9 = 324600616;
      goto LABEL_5;
    }
  }
LABEL_58:
  if ( hMem )
    LocalFree(hMem);
  if ( v26 )
    LocalFree(v26);
  if ( v4 )
    LocalFree(v4);
  return v11;
}

```

## disassembly

```asm
0x1800315b4  mov     [rsp-28h+arg_0], rbx
0x1800315b9  mov     [rsp-28h+arg_10], rsi
0x1800315be  push    rbp
0x1800315bf  push    rdi
0x1800315c0  push    r12
0x1800315c2  push    r14
0x1800315c4  push    r15
0x1800315c6  mov     rbp, rsp
0x1800315c9  sub     rsp, 40h
0x1800315cd  xor     r15d, r15d
0x1800315d0  mov     [rbp+var_18], 0
0x1800315d8  mov     [rbp+hMem], 0
0x1800315e0  mov     r12, r9
0x1800315e3  mov     [rbp+arg_8], r15
0x1800315e7  mov     rsi, r8
0x1800315ea  mov     r14, rdx
0x1800315ed  mov     rdi, rcx
0x1800315f0  test    rdx, rdx
0x1800315f3  jnz     short loc_18003160B
0x1800315f5  mov     ecx, 133A0328h; unsigned int
0x1800315fa  mov     edx, 80004003h; int
0x1800315ff  mov     ebx, edx
0x180031601  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180031606  jmp     loc_180031942
0x18003160b  or      ebx, 0FFFFFFFFh
0x18003160e  lea     rdx, aDistinguishedn; "distinguishedName"
0x180031615  mov     r8d, ebx; int
0x180031618  mov     r9b, 1; bool
0x18003161b  mov     rcx, r14; lpString1
0x18003161e  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031623  test    eax, eax
0x180031625  jnz     short loc_180031633
0x180031627  mov     edx, 8000FFFFh
0x18003162c  mov     ecx, 13410328h
0x180031631  jmp     short loc_1800315FF
0x180031633  mov     r9b, 1; bool
0x180031636  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x18003163d  mov     r8d, ebx; int
0x180031640  mov     rcx, r14; lpString1
0x180031643  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031648  test    eax, eax
0x18003164a  jnz     short loc_1800316AD
0x18003164c  mov     edx, [rsi]; unsigned int
0x18003164e  mov     eax, [rdi+58h]
0x180031651  cmp     edx, eax
0x180031653  jnz     short loc_180031670
0x180031655  mov     rcx, rdi; this
0x180031658  call    ?_PersistSchemaVersion@CCertTypeInfo@@IEAAJK@Z; CCertTypeInfo::_PersistSchemaVersion(ulong)
0x18003165d  mov     ebx, eax
0x18003165f  test    eax, eax
0x180031661  jz      loc_180031942
0x180031667  mov     edx, eax
0x180031669  mov     ecx, 13500328h
0x18003166e  jmp     short loc_180031601
0x180031670  add     eax, 0FFFFFFFEh
0x180031673  cmp     eax, 2
0x180031676  ja      short loc_18003169E
0x180031678  lea     eax, [rdx-2]
0x18003167b  cmp     eax, 2
0x18003167e  ja      short loc_18003169E
0x180031680  mov     rcx, rdi; this
0x180031683  call    ?_ChangeSchemaVersion@CCertTypeInfo@@IEAAJK@Z; CCertTypeInfo::_ChangeSchemaVersion(ulong)
0x180031688  mov     ebx, eax
0x18003168a  test    eax, eax
0x18003168c  jz      loc_180031942
0x180031692  mov     edx, eax
0x180031694  mov     ecx, 13590328h
0x180031699  jmp     loc_180031601
0x18003169e  mov     edx, 8000FFFFh
0x1800316a3  mov     ecx, 135F0328h
0x1800316a8  jmp     loc_1800315FF
0x1800316ad  cmp     dword ptr [rdi+58h], 2
0x1800316b1  jnb     short loc_1800316DD
0x1800316b3  mov     rcx, r14; lpString1
0x1800316b6  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x1800316bb  test    eax, eax
0x1800316bd  jz      short loc_1800316DD
0x1800316bf  mov     edx, 13660328h; unsigned int
0x1800316c4  mov     r8d, 80070490h; int
0x1800316ca  mov     ebx, r8d
0x1800316cd  xor     r9d, r9d; int
0x1800316d0  mov     rcx, r14; unsigned __int16 *
0x1800316d3  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800316d8  jmp     loc_180031942
0x1800316dd  cmp     dword ptr [rdi+58h], 3
0x1800316e1  jnb     short loc_1800316F6
0x1800316e3  mov     rcx, r14; lpString1
0x1800316e6  call    ?IsV3Property@@YAHPEBG@Z; IsV3Property(ushort const *)
0x1800316eb  test    eax, eax
0x1800316ed  jz      short loc_1800316F6
0x1800316ef  mov     edx, 136C0328h
0x1800316f4  jmp     short loc_1800316C4
0x1800316f6  mov     r9b, 1; bool
0x1800316f9  lea     rdx, aCn_1; "cn"
0x180031700  or      r8d, 0FFFFFFFFh; int
0x180031704  mov     rcx, r14; lpString1
0x180031707  xor     ebx, ebx
0x180031709  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003170e  test    eax, eax
0x180031710  jnz     short loc_180031752
0x180031712  test    rsi, rsi
0x180031715  jnz     short loc_180031721
0x180031717  mov     ecx, 13750328h
0x18003171c  jmp     loc_1800315FA
0x180031721  cmp     [rsi], rbx
0x180031724  jnz     short loc_180031730
0x180031726  mov     ecx, 137B0328h
0x18003172b  jmp     loc_1800315FA
0x180031730  lea     r8, [rbp+var_18]; void *
0x180031734  mov     rdx, r14; unsigned __int16 *
0x180031737  mov     rcx, rdi; this
0x18003173a  call    ?GetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX@Z; CCertTypeInfo::GetPropertyEx(ushort const *,void *)
0x18003173f  mov     ebx, eax
0x180031741  test    eax, eax
0x180031743  jz      short loc_180031752
0x180031745  mov     r8d, eax
0x180031748  mov     edx, 13800328h
0x18003174d  jmp     loc_1800316CD
0x180031752  mov     r9b, 1; bool
0x180031755  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x18003175c  or      r8d, 0FFFFFFFFh; int
0x180031760  mov     rcx, r14; lpString1
0x180031763  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031768  test    eax, eax
0x18003176a  jnz     short loc_180031776
0x18003176c  mov     eax, [rsi]
0x18003176e  mov     [rdi+40h], eax
0x180031771  jmp     loc_180031942
0x180031776  mov     r9b, 1; bool
0x180031779  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180031780  or      r8d, 0FFFFFFFFh; int
0x180031784  mov     rcx, r14; lpString1
0x180031787  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003178c  test    eax, eax
0x18003178e  jnz     short loc_18003179A
0x180031790  mov     eax, [rsi]
0x180031792  mov     [rdi+54h], eax
0x180031795  jmp     loc_180031942
0x18003179a  mov     r9b, 1; bool
0x18003179d  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x1800317a4  or      r8d, 0FFFFFFFFh; int
0x1800317a8  mov     rcx, r14; lpString1
0x1800317ab  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800317b0  test    eax, eax
0x1800317b2  jnz     short loc_1800317BE
0x1800317b4  mov     eax, [rsi]
0x1800317b6  mov     [rdi+50h], eax
0x1800317b9  jmp     loc_180031942
0x1800317be  mov     r9b, 1; bool
0x1800317c1  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x1800317c8  or      r8d, 0FFFFFFFFh; int
0x1800317cc  mov     rcx, r14; lpString1
0x1800317cf  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800317d4  test    eax, eax
0x1800317d6  jnz     short loc_1800317E2
0x1800317d8  mov     eax, [rsi]
0x1800317da  mov     [rdi+58h], eax
0x1800317dd  jmp     loc_180031942
0x1800317e2  mov     r9b, 1; bool
0x1800317e5  lea     rdx, aRevision_0; "revision"
0x1800317ec  or      r8d, 0FFFFFFFFh; int
0x1800317f0  mov     rcx, r14; lpString1
0x1800317f3  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800317f8  test    eax, eax
0x1800317fa  jnz     short loc_180031809
0x1800317fc  mov     eax, [rsi]
0x1800317fe  mov     [rdi+90h], eax
0x180031804  jmp     loc_180031942
0x180031809  mov     r8, rsi; unsigned __int16 **
0x18003180c  mov     rdx, r14; unsigned __int16 *
0x18003180f  mov     rcx, rdi; this
0x180031812  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180031817  mov     ebx, eax
0x180031819  test    eax, eax
0x18003181b  jnz     loc_180031942
0x180031821  mov     rcx, [rbp+var_18]
0x180031825  test    rcx, rcx
0x180031828  jz      loc_180031942
0x18003182e  mov     rcx, [rcx]; lpString1
0x180031831  test    rcx, rcx
0x180031834  jz      loc_180031942
0x18003183a  mov     rdx, [rsi]; unsigned __int16 *
0x18003183d  lea     r14d, [rax+1]
0x180031841  mov     r9b, r14b; bool
0x180031844  or      r8d, 0FFFFFFFFh; int
0x180031848  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003184d  test    eax, eax
0x18003184f  jz      loc_180031942
0x180031855  mov     rcx, [rdi+8]; unsigned __int16 *
0x180031859  test    rcx, rcx
0x18003185c  jz      short loc_180031867
0x18003185e  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x180031863  mov     [rdi+8], r15
0x180031867  mov     rcx, [rsi]; Src
0x18003186a  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18003186f  mov     [rdi+8], rax
0x180031873  test    rax, rax
0x180031876  jnz     short loc_180031882
0x180031878  mov     ebx, 8007000Eh
0x18003187d  jmp     loc_180031942
0x180031882  mov     r8, rsi; unsigned __int16 **
0x180031885  lea     rdx, aDistinguishedn; "distinguishedName"
0x18003188c  mov     rcx, rdi; this
0x18003188f  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180031894  mov     ebx, eax
0x180031896  test    eax, eax
0x180031898  jnz     loc_180031942
0x18003189e  cmp     dword ptr [rdi+58h], 2
0x1800318a2  mov     [rdi+78h], r14d
0x1800318a6  mov     [rdi+3Ah], ax
0x1800318aa  mov     dword ptr [rdi+90h], 64h ; 'd'
0x1800318b4  jnb     short loc_1800318E7
0x1800318b6  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x1800318ba  mov     rcx, rdi; this
0x1800318bd  lea     rdx, aPkiextendedkey; "pKIExtendedKeyUsage"
0x1800318c4  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x1800318c9  test    eax, eax
0x1800318cb  jnz     short loc_1800318E0
0x1800318cd  mov     r8, [rbp+hMem]; unsigned __int16 **
0x1800318d1  lea     rdx, aMspkiCertifica_0; "msPKI-Certificate-Application-Policy"
0x1800318d8  mov     rcx, rdi; this
0x1800318db  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x1800318e0  mov     dword ptr [rdi+58h], 2
0x1800318e7  mov     r9, r12; struct ldap *
0x1800318ea  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x1800318ee  mov     ecx, r14d; unsigned int
0x1800318f1  call    ?I_CAOIDCreateNew@@YAJKKPEAPEAGPEAUldap@@@Z; I_CAOIDCreateNew(ulong,ulong,ushort * *,ldap *)
0x1800318f6  mov     r15, [rbp+arg_8]
0x1800318fa  mov     ebx, eax
0x1800318fc  test    eax, eax
0x1800318fe  jnz     short loc_180031942
0x180031900  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180031904  mov     [rbp+var_10], r15
0x180031908  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18003190f  mov     [rbp+var_8], 0
0x180031917  mov     rcx, rdi; this
0x18003191a  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x18003191f  mov     ebx, eax
0x180031921  test    eax, eax
0x180031923  jnz     short loc_180031942
0x180031925  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180031929  mov     [rbp+var_10], 0
0x180031931  lea     rdx, aDisplayname_0; "displayName"
0x180031938  mov     rcx, rdi; this
0x18003193b  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180031940  mov     ebx, eax
0x180031942  mov     rcx, [rbp+hMem]; hMem
0x180031946  test    rcx, rcx
0x180031949  jz      short loc_180031951
0x18003194b  call    cs:__imp_LocalFree
0x180031951  mov     rcx, [rbp+var_18]; hMem
0x180031955  test    rcx, rcx
0x180031958  jz      short loc_180031960
0x18003195a  call    cs:__imp_LocalFree
0x180031960  test    r15, r15
0x180031963  jz      short loc_18003196E
0x180031965  mov     rcx, r15; hMem
0x180031968  call    cs:__imp_LocalFree
0x18003196e  lea     r11, [rsp+40h+var_s0]
0x180031973  mov     eax, ebx
0x180031975  mov     rbx, [r11+30h]
0x180031979  mov     rsi, [r11+40h]
0x18003197d  mov     rsp, r11
0x180031980  pop     r15
0x180031982  pop     r14
0x180031984  pop     r12
0x180031986  pop     rdi
0x180031987  pop     rbp
0x180031988  retn
```
