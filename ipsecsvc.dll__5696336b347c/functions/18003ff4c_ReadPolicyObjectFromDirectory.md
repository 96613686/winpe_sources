# ReadPolicyObjectFromDirectory

- ea: `0x18003ff4c`
- end: `0x180040378`
- name: `ReadPolicyObjectFromDirectory`
- size: `1068`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c1ec`

## callees

- `0x180006f60`
- `0x18000e510`
- `0x180039400`
- `0x18003eb98`
- `0x18003f2cc`
- `0x18003f574`
- `0x18003f824`
- `0x18003fc98`
- `0x18003ff4c`
- `0x180042240`
- `0x180042ab0`
- `0x180042e20`

## import_xrefs

- `WLDAP32!__imp_ldap_msgfree` at `0x180040332`
- `WLDAP32!__imp_ldap_msgfree` at `0x180040332`

## pseudocode

```c
__int64 __fastcall ReadPolicyObjectFromDirectory(LDAP *a1, const wchar_t *a2, LPVOID *a3)
{
  unsigned int FilterObjectsFromDirectory; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPVOID v11; // [rsp+60h] [rbp-98h] BYREF
  __int64 v12; // [rsp+68h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-88h] BYREF
  __int64 v14; // [rsp+78h] [rbp-80h] BYREF
  __int64 v15; // [rsp+80h] [rbp-78h] BYREF
  unsigned int v16; // [rsp+88h] [rbp-70h]
  LDAPMessage *res; // [rsp+90h] [rbp-68h] BYREF
  LPVOID v18; // [rsp+98h] [rbp-60h] BYREF
  LPVOID v19; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-40h] BYREF
  __int64 v23[7]; // [rsp+C0h] [rbp-38h] BYREF
  __int64 v24; // [rsp+118h] [rbp+20h] BYREF

  res = 0;
  v11 = 0;
  v14 = 0;
  v20 = 0;
  v18 = 0;
  LODWORD(v24) = 0;
  v19 = 0;
  LODWORD(v12) = 0;
  v21 = 0;
  v22 = 0;
  v15 = 0;
  v23[0] = 0;
  lpMem = 0;
  FilterObjectsFromDirectory = ComputePolicyContainerDN(a2, (__int64 *)&lpMem);
  if ( FilterObjectsFromDirectory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v8 = 15;
    goto LABEL_29;
  }
  FilterObjectsFromDirectory = LdapSearchHelper((int)a1, (int)a2, 0, (int)L"(objectClass=*)", &PolicyDNAttributes, &res);
  v16 = FilterObjectsFromDirectory;
  if ( FilterObjectsFromDirectory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v8 = 16;
    goto LABEL_29;
  }
  FilterObjectsFromDirectory = UnMarshallPolicyObject(a1, a2, &v11, res);
  if ( FilterObjectsFromDirectory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v8 = 17;
    goto LABEL_29;
  }
  FilterObjectsFromDirectory = ReadNFAObjectsFromDirectory(
                                 a1,
                                 (int)lpMem,
                                 v9,
                                 *((_QWORD *)v11 + 8),
                                 *((_DWORD *)v11 + 14),
                                 &v20,
                                 (unsigned int *)&v14,
                                 &v18,
                                 (unsigned int *)&v24,
                                 &v19,
                                 &v12);
  if ( FilterObjectsFromDirectory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v8 = 18;
    goto LABEL_29;
  }
  FilterObjectsFromDirectory = ReadFilterObjectsFromDirectory((int)a1, (int)lpMem, (__int64)&v21, (__int64)&v14 + 4);
  if ( FilterObjectsFromDirectory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v8 = 19;
    goto LABEL_29;
  }
  FilterObjectsFromDirectory = ReadNegPolObjectsFromDirectory((int)a1, (int)lpMem, (__int64)&v22, (__int64)&v15);
  if ( FilterObjectsFromDirectory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v8 = 20;
    goto LABEL_29;
  }
  FilterObjectsFromDirectory = ReadISAKMPObjectsFromDirectory((int)a1, (int)lpMem, (__int64)v23, (__int64)&v15 + 4);
  if ( !FilterObjectsFromDirectory )
  {
    *((_QWORD *)v11 + 9) = v20;
    *((_DWORD *)v11 + 15) = v14;
    *((_DWORD *)v11 + 20) = HIDWORD(v14);
    *((_QWORD *)v11 + 11) = v21;
    *((_QWORD *)v11 + 13) = v22;
    *((_DWORD *)v11 + 24) = v15;
    *((_DWORD *)v11 + 28) = HIDWORD(v15);
    *((_QWORD *)v11 + 15) = v23[0];
    *a3 = v11;
    goto LABEL_34;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = 21;
LABEL_29:
    WPP_SF_d(v7[2], v8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, FilterObjectsFromDirectory);
  }
LABEL_30:
  if ( v11 )
    FreeIpsecPolicyObject((LPVOID *)v11);
  *a3 = 0;
LABEL_34:
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( res )
    ldap_msgfree(res);
  if ( v18 )
    FreeNFAReferences(v18, v24);
  if ( v19 )
    FreeNFAReferences(v19, v12);
  return FilterObjectsFromDirectory;
}

```

## disassembly

```asm
0x18003ff4c  mov     rax, rsp
0x18003ff4f  mov     [rax+18h], r8
0x18003ff53  mov     [rax+10h], rdx
0x18003ff57  mov     [rax+8], rcx
0x18003ff5b  push    rbx
0x18003ff5c  push    rsi
0x18003ff5d  push    rdi
0x18003ff5e  push    r14
0x18003ff60  push    r15
0x18003ff62  sub     rsp, 0D0h
0x18003ff69  mov     r15, r8
0x18003ff6c  mov     r14, rdx
0x18003ff6f  mov     rsi, rcx
0x18003ff72  xor     ebx, ebx
0x18003ff74  mov     [rax-68h], rbx
0x18003ff78  mov     [rsp+0F8h+var_98], rbx
0x18003ff7d  mov     [rax-80h], ebx
0x18003ff80  mov     [rax-50h], rbx
0x18003ff84  mov     [rax-60h], rbx
0x18003ff88  mov     [rax+20h], ebx
0x18003ff8b  mov     [rax-58h], rbx
0x18003ff8f  mov     dword ptr [rsp+0F8h+var_90], ebx
0x18003ff93  mov     [rax-48h], rbx
0x18003ff97  mov     [rax-7Ch], ebx
0x18003ff9a  mov     [rax-40h], rbx
0x18003ff9e  mov     [rax-78h], ebx
0x18003ffa1  mov     [rax-38h], rbx
0x18003ffa5  mov     [rax-74h], ebx
0x18003ffa8  mov     [rsp+0F8h+lpMem], rbx
0x18003ffad  lea     rdx, [rsp+0F8h+lpMem]
0x18003ffb2  mov     rcx, r14
0x18003ffb5  call    ComputePolicyContainerDN
0x18003ffba  mov     edi, eax
0x18003ffbc  test    eax, eax
0x18003ffbe  jz      short loc_18003FFE9
0x18003ffc0  lea     rax, WPP_GLOBAL_Control
0x18003ffc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ffce  cmp     rcx, rax
0x18003ffd1  jz      loc_18004027D
0x18003ffd7  test    byte ptr [rcx+1Ch], 10h
0x18003ffdb  jz      loc_18004027D
0x18003ffe1  lea     edx, [rbx+0Fh]
0x18003ffe4  jmp     loc_18004026A
0x18003ffe9  lea     rax, [rsp+0F8h+res]
0x18003fff1  mov     [rsp+0F8h+var_D0], rax; LDAPMessage **
0x18003fff6  lea     rax, PolicyDNAttributes
0x18003fffd  mov     [rsp+0F8h+var_D8], rax; PZPWSTR
0x180040002  lea     r9, aObjectclass; "(objectClass=*)"
0x180040009  xor     r8d, r8d; int
0x18004000c  mov     rdx, r14; int
0x18004000f  mov     rcx, rsi; int
0x180040012  call    LdapSearchHelper
0x180040017  mov     edi, eax
0x180040019  mov     [rsp+0F8h+var_70], eax
0x180040020  jmp     short loc_180040048
0x180040022  mov     edi, 57h ; 'W'
0x180040027  mov     [rsp+0F8h+var_70], edi
0x18004002e  xor     ebx, ebx
0x180040030  mov     r15, [rsp+0F8h+arg_10]
0x180040038  mov     r14, [rsp+0F8h+arg_8]
0x180040040  mov     rsi, [rsp+0F8h+arg_0]
0x180040048  test    edi, edi
0x18004004a  jz      short loc_180040077
0x18004004c  lea     rax, WPP_GLOBAL_Control
0x180040053  mov     rcx, cs:WPP_GLOBAL_Control
0x18004005a  cmp     rcx, rax
0x18004005d  jz      loc_18004027D
0x180040063  test    byte ptr [rcx+1Ch], 10h
0x180040067  jz      loc_18004027D
0x18004006d  mov     edx, 10h
0x180040072  jmp     loc_18004026A
0x180040077  mov     r9, [rsp+0F8h+res]
0x18004007f  lea     r8, [rsp+0F8h+var_98]
0x180040084  mov     rdx, r14
0x180040087  mov     rcx, rsi
0x18004008a  call    UnMarshallPolicyObject
0x18004008f  mov     edi, eax
0x180040091  test    eax, eax
0x180040093  jz      short loc_1800400C0
0x180040095  lea     rax, WPP_GLOBAL_Control
0x18004009c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800400a3  cmp     rcx, rax
0x1800400a6  jz      loc_18004027D
0x1800400ac  test    byte ptr [rcx+1Ch], 10h
0x1800400b0  jz      loc_18004027D
0x1800400b6  mov     edx, 11h
0x1800400bb  jmp     loc_18004026A
0x1800400c0  lea     rax, [rsp+0F8h+var_90]
0x1800400c5  mov     [rsp+0F8h+var_A8], rax; __int64
0x1800400ca  lea     rax, [rsp+0F8h+var_58]
0x1800400d2  mov     [rsp+0F8h+var_B0], rax; __int64
0x1800400d7  lea     rax, [rsp+0F8h+arg_18]
0x1800400df  mov     [rsp+0F8h+var_B8], rax; __int64
0x1800400e4  lea     rax, [rsp+0F8h+var_60]
0x1800400ec  mov     [rsp+0F8h+var_C0], rax; __int64
0x1800400f1  lea     rax, [rsp+0F8h+var_80]
0x1800400f6  mov     [rsp+0F8h+var_C8], rax; __int64
0x1800400fb  lea     rax, [rsp+0F8h+var_50]
0x180040103  mov     [rsp+0F8h+var_D0], rax; __int64
0x180040108  mov     r9, [rsp+0F8h+var_98]
0x18004010d  mov     eax, [r9+38h]
0x180040111  mov     dword ptr [rsp+0F8h+var_D8], eax; int
0x180040115  mov     r9, [r9+40h]
0x180040119  mov     rdx, [rsp+0F8h+lpMem]; int
0x18004011e  mov     rcx, rsi; int
0x180040121  call    ReadNFAObjectsFromDirectory
0x180040126  mov     edi, eax
0x180040128  test    eax, eax
0x18004012a  jz      short loc_180040157
0x18004012c  lea     rax, WPP_GLOBAL_Control
0x180040133  mov     rcx, cs:WPP_GLOBAL_Control
0x18004013a  cmp     rcx, rax
0x18004013d  jz      loc_18004027D
0x180040143  test    byte ptr [rcx+1Ch], 10h
0x180040147  jz      loc_18004027D
0x18004014d  mov     edx, 12h
0x180040152  jmp     loc_18004026A
0x180040157  lea     rax, [rsp+0F8h+var_80+4]
0x18004015c  mov     [rsp+0F8h+var_D0], rax; __int64
0x180040161  lea     rax, [rsp+0F8h+var_48]
0x180040169  mov     [rsp+0F8h+var_D8], rax; __int64
0x18004016e  mov     r9d, dword ptr [rsp+0F8h+arg_18]
0x180040176  mov     r8, [rsp+0F8h+var_60]
0x18004017e  mov     rdx, [rsp+0F8h+lpMem]; int
0x180040183  mov     rcx, rsi; int
0x180040186  call    ReadFilterObjectsFromDirectory
0x18004018b  mov     edi, eax
0x18004018d  test    eax, eax
0x18004018f  jz      short loc_1800401BC
0x180040191  lea     rax, WPP_GLOBAL_Control
0x180040198  mov     rcx, cs:WPP_GLOBAL_Control
0x18004019f  cmp     rcx, rax
0x1800401a2  jz      loc_18004027D
0x1800401a8  test    byte ptr [rcx+1Ch], 10h
0x1800401ac  jz      loc_18004027D
0x1800401b2  mov     edx, 13h
0x1800401b7  jmp     loc_18004026A
0x1800401bc  lea     rax, [rsp+0F8h+var_78]
0x1800401c4  mov     [rsp+0F8h+var_D0], rax; __int64
0x1800401c9  lea     rax, [rsp+0F8h+var_40]
0x1800401d1  mov     [rsp+0F8h+var_D8], rax; __int64
0x1800401d6  mov     r9d, dword ptr [rsp+0F8h+var_90]
0x1800401db  mov     r8, [rsp+0F8h+var_58]
0x1800401e3  mov     rdx, [rsp+0F8h+lpMem]; int
0x1800401e8  mov     rcx, rsi; int
0x1800401eb  call    ReadNegPolObjectsFromDirectory
0x1800401f0  mov     edi, eax
0x1800401f2  test    eax, eax
0x1800401f4  jz      short loc_180040216
0x1800401f6  lea     rax, WPP_GLOBAL_Control
0x1800401fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180040204  cmp     rcx, rax
0x180040207  jz      short loc_18004027D
0x180040209  test    byte ptr [rcx+1Ch], 10h
0x18004020d  jz      short loc_18004027D
0x18004020f  mov     edx, 14h
0x180040214  jmp     short loc_18004026A
0x180040216  mov     r8, [rsp+0F8h+var_98]
0x18004021b  add     r8, 30h ; '0'
0x18004021f  lea     rax, [rsp+0F8h+var_78+4]
0x180040227  mov     [rsp+0F8h+var_D0], rax; __int64
0x18004022c  lea     rax, [rsp+0F8h+var_38]
0x180040234  mov     [rsp+0F8h+var_D8], rax; __int64
0x180040239  mov     rdx, [rsp+0F8h+lpMem]; int
0x18004023e  mov     rcx, rsi; int
0x180040241  call    ReadISAKMPObjectsFromDirectory
0x180040246  mov     edi, eax
0x180040248  test    eax, eax
0x18004024a  jz      short loc_180040294
0x18004024c  lea     rax, WPP_GLOBAL_Control
0x180040253  mov     rcx, cs:WPP_GLOBAL_Control
0x18004025a  cmp     rcx, rax
0x18004025d  jz      short loc_18004027D
0x18004025f  test    byte ptr [rcx+1Ch], 10h
0x180040263  jz      short loc_18004027D
0x180040265  mov     edx, 15h
0x18004026a  mov     r9d, edi
0x18004026d  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x180040274  mov     rcx, [rcx+10h]
0x180040278  call    WPP_SF_d
0x18004027d  mov     rcx, [rsp+0F8h+var_98]; lpMem
0x180040282  test    rcx, rcx
0x180040285  jz      short loc_18004028C
0x180040287  call    FreeIpsecPolicyObject
0x18004028c  mov     [r15], rbx
0x18004028f  jmp     loc_180040316
0x180040294  mov     rcx, [rsp+0F8h+var_50]
0x18004029c  mov     rax, [rsp+0F8h+var_98]
0x1800402a1  mov     [rax+48h], rcx
0x1800402a5  mov     ecx, dword ptr [rsp+0F8h+var_80]
0x1800402a9  mov     rax, [rsp+0F8h+var_98]
0x1800402ae  mov     [rax+3Ch], ecx
0x1800402b1  mov     ecx, dword ptr [rsp+0F8h+var_80+4]
0x1800402b5  mov     rax, [rsp+0F8h+var_98]
0x1800402ba  mov     [rax+50h], ecx
0x1800402bd  mov     rcx, [rsp+0F8h+var_48]
0x1800402c5  mov     rax, [rsp+0F8h+var_98]
0x1800402ca  mov     [rax+58h], rcx
0x1800402ce  mov     rcx, [rsp+0F8h+var_40]
0x1800402d6  mov     rax, [rsp+0F8h+var_98]
0x1800402db  mov     [rax+68h], rcx
0x1800402df  mov     ecx, dword ptr [rsp+0F8h+var_78]
0x1800402e6  mov     rax, [rsp+0F8h+var_98]
0x1800402eb  mov     [rax+60h], ecx
0x1800402ee  mov     ecx, dword ptr [rsp+0F8h+var_78+4]
0x1800402f5  mov     rax, [rsp+0F8h+var_98]
0x1800402fa  mov     [rax+70h], ecx
0x1800402fd  mov     rcx, [rsp+0F8h+var_38]
0x180040305  mov     rax, [rsp+0F8h+var_98]
0x18004030a  mov     [rax+78h], rcx
0x18004030e  mov     rax, [rsp+0F8h+var_98]
0x180040313  mov     [r15], rax
0x180040316  mov     rcx, [rsp+0F8h+lpMem]; lpMem
0x18004031b  test    rcx, rcx
0x18004031e  jz      short loc_180040325
0x180040320  call    IpsecFreeMem
0x180040325  mov     rcx, [rsp+0F8h+res]; res
0x18004032d  test    rcx, rcx
0x180040330  jz      short loc_180040338
0x180040332  call    cs:__imp_ldap_msgfree
0x180040338  mov     rcx, [rsp+0F8h+var_60]; lpMem
0x180040340  test    rcx, rcx
0x180040343  jz      short loc_180040351
0x180040345  mov     edx, dword ptr [rsp+0F8h+arg_18]
0x18004034c  call    FreeNFAReferences
0x180040351  mov     rcx, [rsp+0F8h+var_58]; lpMem
0x180040359  test    rcx, rcx
0x18004035c  jz      short loc_180040367
0x18004035e  mov     edx, dword ptr [rsp+0F8h+var_90]
0x180040362  call    FreeNFAReferences
0x180040367  mov     eax, edi
0x180040369  add     rsp, 0D0h
0x180040370  pop     r15
0x180040372  pop     r14
0x180040374  pop     rdi
0x180040375  pop     rsi
0x180040376  pop     rbx
0x180040377  retn
0x18004d477  push    rbp
0x18004d479  sub     rsp, 60h
0x18004d47d  mov     rbp, rdx
0x18004d480  mov     rax, [rcx]
0x18004d483  xor     ecx, ecx
0x18004d485  cmp     dword ptr [rax], 0C0000005h
0x18004d48b  setz    cl
0x18004d48e  mov     eax, ecx
0x18004d490  add     rsp, 60h
0x18004d494  pop     rbp
0x18004d495  retn
```
