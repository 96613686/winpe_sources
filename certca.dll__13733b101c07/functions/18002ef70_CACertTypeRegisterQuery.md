# CACertTypeRegisterQuery

- ea: `0x18002ef70`
- end: `0x18002f279`
- name: `CACertTypeRegisterQuery`
- size: `777`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x180005944`
- `0x180005f00`
- `0x1800062d0`
- `0x180008400`
- `0x180008420`
- `0x18000a3b0`
- `0x18000ac20`
- `0x18000e130`
- `0x18000e52c`
- `0x180011600`
- `0x18002ef70`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f256`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002f1de`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002f1de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f24d`
- `WLDAP32!__imp_ldap_unbind` at `0x18002f23e`
- `WLDAP32!__imp_ldap_unbind` at `0x18002f23e`
- `WLDAP32!__imp_ldap_search_extW` at `0x18002f1a0`
- `WLDAP32!__imp_ldap_search_extW` at `0x18002f1a0`

## string_xrefs

- `0x18002efe1`: `CN=Certificate Templates,CN=Public Key Services,CN=Services,`
- `0x18002efd7`: `CN=Enrollment Services,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CACertTypeRegisterQuery(int a1, __int64 a2, _QWORD *a3)
{
  unsigned int v5; // ecx
  int v6; // edx
  unsigned int v7; // ebx
  unsigned __int16 *v8; // r12
  char *v9; // rdi
  struct ldap **v10; // rsi
  int DoesDSExist; // eax
  unsigned int v12; // ecx
  unsigned __int16 *v13; // r14
  unsigned int v14; // eax
  unsigned __int16 *v15; // r15
  unsigned int v16; // ecx
  int v17; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  ULONG v22; // eax
  HANDLE v23; // rax
  DWORD LastError; // eax
  LDAP *v25; // rcx
  void *v26; // rcx
  PLDAPControlW ServerControls[2]; // [rsp+60h] [rbp-19h] BYREF
  PWSTR attrs[2]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v30; // [rsp+80h] [rbp+7h] BYREF
  __int128 v31; // [rsp+90h] [rbp+17h]
  DWORD ThreadId; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int16 *v33; // [rsp+F8h] [rbp+7Fh] BYREF

  ThreadId = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  *(_OWORD *)ServerControls = 0;
  *(_OWORD *)attrs = 0;
  if ( (a1 & 0xFFFFFFFC) != 0 )
  {
    v5 = 9241385;
LABEL_3:
    v6 = -2147024809;
LABEL_4:
    v7 = v6;
    CSPrintErrorLineFile(v5, v6);
    return v7;
  }
  v8 = L"CN=Certificate Templates,CN=Public Key Services,CN=Services,";
  if ( (a1 & 1) == 0 )
    v8 = L"CN=Enrollment Services,CN=Public Key Services,CN=Services,";
  if ( !a3 )
  {
    v5 = 9896745;
    goto LABEL_3;
  }
  v9 = (char *)LocalAlloc(0x40u, 0x28u);
  if ( !v9 )
  {
    v6 = -2147024882;
    v5 = 10355497;
    goto LABEL_4;
  }
  *(_OWORD *)v9 = 0;
  *((_OWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *(_DWORD *)v9 = 1;
  if ( a2 )
  {
    v10 = (struct ldap **)(v9 + 8);
    *((_QWORD *)v9 + 1) = a2;
    goto LABEL_19;
  }
  DoesDSExist = myDoesDSExist(1);
  v7 = DoesDSExist;
  if ( DoesDSExist )
  {
    v12 = 11535145;
LABEL_15:
    CSPrintErrorLineFile(v12, DoesDSExist);
LABEL_40:
    if ( *((_DWORD *)v9 + 1) )
    {
      v25 = (LDAP *)*((_QWORD *)v9 + 1);
      if ( v25 )
        ldap_unbind(v25);
    }
    v26 = (void *)*((_QWORD *)v9 + 3);
    if ( v26 )
      CloseHandle(v26);
    LocalFree(v9);
    return v7;
  }
  v10 = (struct ldap **)(v9 + 8);
  DoesDSExist = myRobustLdapBindEx(0, (const unsigned __int16 *)0x208, 0, 0, (LDAP **)v9 + 1, 0);
  v7 = DoesDSExist;
  if ( DoesDSExist )
  {
    v12 = 12124969;
    goto LABEL_15;
  }
  *((_DWORD *)v9 + 1) = 1;
LABEL_19:
  v13 = 0;
  v14 = CAGetAuthoritativeDomainDn(*v10, 0, &v33);
  v15 = v33;
  v7 = v14;
  if ( v14 )
  {
    v16 = 12583721;
LABEL_21:
    v17 = v14;
LABEL_22:
    CSPrintErrorLineFile(v16, v17);
    goto LABEL_35;
  }
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( v8[v19] );
  do
    ++v18;
  while ( v33[v18] );
  v20 = v19 + v18 + 1;
  if ( v20 > 0x10000 )
  {
    v7 = -2147024362;
    v16 = 13042473;
    v17 = -2147024362;
    goto LABEL_22;
  }
  v21 = CertAllocStringLen(0, v20);
  v13 = v21;
  if ( !v21 )
  {
    v17 = -2147024882;
    v16 = 13435689;
    v7 = -2147024882;
    goto LABEL_22;
  }
  StringCchCopyW(v21, v20, v8);
  StringCchCatW(v13, v20, v15);
  v7 = 0;
  *(_QWORD *)&v30 = L"1.2.840.113556.1.4.528";
  DWORD2(v30) = 0;
  BYTE8(v31) = 1;
  ServerControls[0] = (PLDAPControlW)&v30;
  *(_QWORD *)&v31 = 0;
  attrs[0] = (PWSTR)L"cn";
  ServerControls[1] = 0;
  attrs[1] = 0;
  v22 = ldap_search_extW(
          *v10,
          v13,
          1u,
          (const PWSTR)L"ObjectClass=*",
          attrs,
          1u,
          ServerControls,
          0,
          0,
          0,
          (ULONG *)v9 + 4);
  if ( v22 )
  {
    v14 = myHLdapError3(*v10, v22, 0);
    v7 = v14;
    v16 = 15729449;
    goto LABEL_21;
  }
  v23 = CreateThread(0, 0, CertTypeQueryProc, v9, 0, &ThreadId);
  *((_QWORD *)v9 + 3) = v23;
  if ( !v23 )
  {
    LastError = GetLastError();
    v14 = myHError(LastError);
    v7 = v14;
    v16 = 16712489;
    goto LABEL_21;
  }
  *a3 = v9;
  v9 = 0;
LABEL_35:
  if ( v15 )
    CertFreeString(v15);
  if ( v13 )
    CertFreeString(v13);
  if ( v9 )
    goto LABEL_40;
  return v7;
}

```

## disassembly

```asm
0x18002ef70  mov     [rsp-8+arg_8], rbx
0x18002ef75  push    rbp
0x18002ef76  push    rsi
0x18002ef77  push    rdi
0x18002ef78  push    r12
0x18002ef7a  push    r13
0x18002ef7c  push    r14
0x18002ef7e  push    r15
0x18002ef80  lea     rbp, [rsp-27h]
0x18002ef85  sub     rsp, 0A0h
0x18002ef8c  xor     r15d, r15d
0x18002ef8f  xorps   xmm0, xmm0
0x18002ef92  mov     [rbp+57h+ThreadId], r15d
0x18002ef96  xorps   xmm1, xmm1
0x18002ef99  mov     [rbp+57h+arg_18], r15
0x18002ef9d  mov     r13, r8
0x18002efa0  mov     rbx, rdx
0x18002efa3  movups  [rbp+57h+var_50], xmm0
0x18002efa7  movups  [rbp+57h+var_40], xmm0
0x18002efab  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18002efaf  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18002efb3  test    ecx, 0FFFFFFFCh
0x18002efb9  jz      short loc_18002EFD1
0x18002efbb  mov     ecx, 8D0329h; unsigned int
0x18002efc0  mov     edx, 80070057h; int
0x18002efc5  mov     ebx, edx
0x18002efc7  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002efcc  jmp     loc_18002F25C
0x18002efd1  mov     r14d, 1
0x18002efd7  lea     rax, aCnEnrollmentSe; "CN=Enrollment Services,CN=Public Key Se"...
0x18002efde  test    r14b, cl
0x18002efe1  lea     r12, aCnCertificateT_0; "CN=Certificate Templates,CN=Public Key "...
0x18002efe8  cmovz   r12, rax
0x18002efec  test    r13, r13
0x18002efef  jnz     short loc_18002EFF8
0x18002eff1  mov     ecx, 970329h
0x18002eff6  jmp     short loc_18002EFC0
0x18002eff8  mov     edx, 28h ; '('; uBytes
0x18002effd  lea     ecx, [rdx+18h]; uFlags
0x18002f000  call    cs:__imp_LocalAlloc
0x18002f006  mov     rdi, rax
0x18002f009  test    rax, rax
0x18002f00c  jnz     short loc_18002F01A
0x18002f00e  mov     edx, 8007000Eh
0x18002f013  mov     ecx, 9E0329h
0x18002f018  jmp     short loc_18002EFC5
0x18002f01a  xorps   xmm0, xmm0
0x18002f01d  xor     eax, eax
0x18002f01f  movups  xmmword ptr [rdi], xmm0
0x18002f022  movups  xmmword ptr [rdi+10h], xmm0
0x18002f026  mov     [rdi+20h], rax
0x18002f02a  mov     [rdi], r14d
0x18002f02d  test    rbx, rbx
0x18002f030  jz      short loc_18002F03B
0x18002f032  lea     rsi, [rdi+8]
0x18002f036  mov     [rsi], rbx
0x18002f039  jmp     short loc_18002F08B
0x18002f03b  mov     ecx, r14d; int
0x18002f03e  call    ?myDoesDSExist@@YAJH@Z; myDoesDSExist(int)
0x18002f043  mov     ebx, eax
0x18002f045  test    eax, eax
0x18002f047  jz      short loc_18002F05A
0x18002f049  mov     ecx, 0B00329h; unsigned int
0x18002f04e  mov     edx, eax; int
0x18002f050  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002f055  jmp     loc_18002F22F
0x18002f05a  lea     rsi, [rdi+8]
0x18002f05e  mov     qword ptr [rsp+0D0h+attrsonly], r15
0x18002f063  xor     r9d, r9d
0x18002f066  mov     [rsp+0D0h+attrs], rsi
0x18002f06b  xor     r8d, r8d
0x18002f06e  mov     edx, 208h
0x18002f073  xor     ecx, ecx
0x18002f075  call    myRobustLdapBindEx
0x18002f07a  mov     ebx, eax
0x18002f07c  test    eax, eax
0x18002f07e  jz      short loc_18002F087
0x18002f080  mov     ecx, 0B90329h
0x18002f085  jmp     short loc_18002F04E
0x18002f087  mov     [rdi+4], r14d
0x18002f08b  mov     rcx, [rsi]; struct ldap *
0x18002f08e  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x18002f092  xor     edx, edx; unsigned __int16 **
0x18002f094  mov     r14, r15
0x18002f097  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x18002f09c  mov     r15, [rbp+57h+arg_18]
0x18002f0a0  xor     edx, edx
0x18002f0a2  mov     ebx, eax
0x18002f0a4  test    eax, eax
0x18002f0a6  jz      short loc_18002F0B9
0x18002f0a8  mov     ecx, 0C00329h; unsigned int
0x18002f0ad  mov     edx, eax; int
0x18002f0af  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002f0b4  jmp     loc_18002F20D
0x18002f0b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f0bd  mov     rcx, rax
0x18002f0c0  inc     rcx
0x18002f0c3  cmp     [r12+rcx*2], dx
0x18002f0c8  jnz     short loc_18002F0C0
0x18002f0ca  inc     rax
0x18002f0cd  cmp     [r15+rax*2], dx
0x18002f0d2  jnz     short loc_18002F0CA
0x18002f0d4  lea     rbx, [rax+1]
0x18002f0d8  add     rbx, rcx
0x18002f0db  cmp     rbx, 10000h
0x18002f0e2  jbe     short loc_18002F0F2
0x18002f0e4  mov     ebx, 80070216h
0x18002f0e9  mov     ecx, 0C70329h
0x18002f0ee  mov     edx, ebx
0x18002f0f0  jmp     short loc_18002F0AF
0x18002f0f2  mov     edx, ebx; unsigned int
0x18002f0f4  xor     ecx, ecx; Src
0x18002f0f6  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002f0fb  mov     r14, rax
0x18002f0fe  test    rax, rax
0x18002f101  jnz     short loc_18002F111
0x18002f103  mov     edx, 8007000Eh
0x18002f108  mov     ecx, 0CD0329h
0x18002f10d  mov     ebx, edx
0x18002f10f  jmp     short loc_18002F0AF
0x18002f111  mov     r8, r12; unsigned __int16 *
0x18002f114  mov     rdx, rbx; unsigned __int64
0x18002f117  mov     rcx, r14; unsigned __int16 *
0x18002f11a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002f11f  mov     r8, r15; unsigned __int16 *
0x18002f122  mov     rdx, rbx; unsigned __int64
0x18002f125  mov     rcx, r14; unsigned __int16 *
0x18002f128  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f12d  xor     ebx, ebx
0x18002f12f  lea     rax, a12840113556145; "1.2.840.113556.1.4.528"
0x18002f136  mov     qword ptr [rbp+57h+var_50], rax
0x18002f13a  lea     r9, aObjectclass_0; "ObjectClass=*"
0x18002f141  mov     r8d, 1; scope
0x18002f147  mov     dword ptr [rbp+57h+var_50+8], ebx
0x18002f14a  lea     rax, [rbp+57h+var_50]
0x18002f14e  mov     byte ptr [rbp+57h+var_40+8], r8b
0x18002f152  mov     [rbp+57h+var_70], rax
0x18002f156  mov     rdx, r14; base
0x18002f159  lea     rax, aCn_1; "cn"
0x18002f160  mov     qword ptr [rbp+57h+var_40], rbx
0x18002f164  mov     [rbp+57h+var_60], rax
0x18002f168  lea     rax, [rdi+10h]
0x18002f16c  mov     [rsp+0D0h+MessageNumber], rax; MessageNumber
0x18002f171  lea     rax, [rbp+57h+var_70]
0x18002f175  mov     [rsp+0D0h+SizeLimit], ebx; SizeLimit
0x18002f179  mov     [rsp+0D0h+TimeLimit], ebx; TimeLimit
0x18002f17d  mov     [rsp+0D0h+ClientControls], rbx; ClientControls
0x18002f182  mov     [rsp+0D0h+ServerControls], rax; ServerControls
0x18002f187  lea     rax, [rbp+57h+var_60]
0x18002f18b  mov     [rbp+57h+var_70+8], rbx
0x18002f18f  mov     [rbp+57h+var_60+8], rbx
0x18002f193  mov     rcx, [rsi]; ld
0x18002f196  mov     [rsp+0D0h+attrsonly], r8d; attrsonly
0x18002f19b  mov     [rsp+0D0h+attrs], rax; unsigned __int16 **
0x18002f1a0  call    cs:__imp_ldap_search_extW
0x18002f1a6  test    eax, eax
0x18002f1a8  jz      short loc_18002F1C3
0x18002f1aa  mov     rcx, [rsi]; ld
0x18002f1ad  xor     r8d, r8d; unsigned int
0x18002f1b0  mov     edx, eax; unsigned int
0x18002f1b2  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002f1b7  mov     ebx, eax
0x18002f1b9  mov     ecx, 0F00329h
0x18002f1be  jmp     loc_18002F0AD
0x18002f1c3  lea     rax, [rbp+57h+ThreadId]
0x18002f1c7  mov     r9, rdi; lpParameter
0x18002f1ca  mov     qword ptr [rsp+0D0h+attrsonly], rax; lpThreadId
0x18002f1cf  lea     r8, ?CertTypeQueryProc@@YAKPEAX@Z; lpStartAddress
0x18002f1d6  xor     edx, edx; dwStackSize
0x18002f1d8  mov     dword ptr [rsp+0D0h+attrs], ebx; dwCreationFlags
0x18002f1dc  xor     ecx, ecx; lpThreadAttributes
0x18002f1de  call    cs:__imp_CreateThread
0x18002f1e4  mov     [rdi+18h], rax
0x18002f1e8  test    rax, rax
0x18002f1eb  jnz     short loc_18002F206
0x18002f1ed  call    cs:__imp_GetLastError
0x18002f1f3  mov     ecx, eax; int
0x18002f1f5  call    ?myHError@@YAJJ@Z; myHError(long)
0x18002f1fa  mov     ebx, eax
0x18002f1fc  mov     ecx, 0FF0329h
0x18002f201  jmp     loc_18002F0AD
0x18002f206  mov     [r13+0], rdi
0x18002f20a  mov     rdi, rbx
0x18002f20d  test    r15, r15
0x18002f210  jz      short loc_18002F21A
0x18002f212  mov     rcx, r15; unsigned __int16 *
0x18002f215  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002f21a  xor     r15d, r15d
0x18002f21d  test    r14, r14
0x18002f220  jz      short loc_18002F22A
0x18002f222  mov     rcx, r14; unsigned __int16 *
0x18002f225  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002f22a  test    rdi, rdi
0x18002f22d  jz      short loc_18002F25C
0x18002f22f  cmp     [rdi+4], r15d
0x18002f233  jz      short loc_18002F244
0x18002f235  mov     rcx, [rdi+8]; ld
0x18002f239  test    rcx, rcx
0x18002f23c  jz      short loc_18002F244
0x18002f23e  call    cs:__imp_ldap_unbind
0x18002f244  mov     rcx, [rdi+18h]; hObject
0x18002f248  test    rcx, rcx
0x18002f24b  jz      short loc_18002F253
0x18002f24d  call    cs:__imp_CloseHandle
0x18002f253  mov     rcx, rdi; hMem
0x18002f256  call    cs:__imp_LocalFree
0x18002f25c  mov     eax, ebx
0x18002f25e  mov     rbx, [rsp+0D0h+arg_8]
0x18002f266  add     rsp, 0A0h
0x18002f26d  pop     r15
0x18002f26f  pop     r14
0x18002f271  pop     r13
0x18002f273  pop     r12
0x18002f275  pop     rdi
0x18002f276  pop     rsi
0x18002f277  pop     rbp
0x18002f278  retn
```
