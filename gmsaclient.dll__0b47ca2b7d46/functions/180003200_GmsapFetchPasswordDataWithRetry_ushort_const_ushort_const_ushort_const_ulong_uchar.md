# GmsapFetchPasswordDataWithRetry(ushort const *,ushort const *,ushort const *,ulong *,uchar * *)

- ea: `0x180003200`
- end: `0x1800034fa`
- name: `?GmsapFetchPasswordDataWithRetry@@YAJPEBG00PEAKPEAPEAE@Z`
- size: `762`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003e84`

## callees

- `0x180002b18`
- `0x180003200`
- `0x180006084`
- `0x180006280`
- `0x1800062b0`
- `0x1800062f4`
- `0x18000634c`
- `0x180006494`
- `0x180007378`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034b2`
- `WLDAP32!__imp_ldap_unbind` at `0x1800032e8`
- `WLDAP32!__imp_ldap_unbind` at `0x180003497`
- `WLDAP32!__imp_ldap_unbind` at `0x1800032e8`
- `WLDAP32!__imp_ldap_unbind` at `0x180003497`

## pseudocode

```c
__int64 __fastcall GmsapFetchPasswordDataWithRetry(
        const unsigned __int16 *a1,
        WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  HLOCAL v5; // rdi
  LDAP *v7; // r15
  int v10; // eax
  int GMSAData; // ebx
  _UNKNOWN **v12; // rcx
  HLOCAL v13; // r13
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // edi
  __int64 v19; // r9
  int v21; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+40h] [rbp-10h] BYREF
  LDAP *ld; // [rsp+48h] [rbp-8h]
  unsigned int v25; // [rsp+98h] [rbp+48h]

  v5 = 0;
  v7 = 0;
  hMem = 0;
  ld = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x41u, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  *a4 = 0;
  *a5 = 0;
  if ( a2 )
  {
    v13 = 0;
  }
  else
  {
    v10 = GmsapCrackDomainName(0, 1, a3, (unsigned __int16 **)&hMem, 0, 0);
    GMSAData = v10;
    if ( v10 < 0 )
    {
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v5 = hMem;
        goto LABEL_38;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (_DWORD)a3,
        v10);
      v5 = hMem;
      goto LABEL_37;
    }
    v5 = hMem;
    a2 = (WCHAR *)hMem;
    v13 = hMem;
  }
  v25 = 1;
  while ( 1 )
  {
    if ( v7 )
    {
      ldap_unbind(v7);
      ld = 0;
    }
    v14 = GmsapLdapBind(a2, v21);
    v7 = ld;
    GMSAData = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
          (_DWORD)a2,
          v14);
    }
    else
    {
      GMSAData = GmsapLdapRetrieveGMSAData(ld);
      if ( GMSAData >= 0 )
      {
        v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
        GMSAData = 0;
        goto LABEL_35;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1, (__int64)a2, GMSAData);
    }
    if ( v13 )
    {
      LocalFree(v5);
      hMem = 0;
    }
    v15 = GmsapCrackDomainName(1, 1, a3, (unsigned __int16 **)&hMem, 0, 0);
    v18 = v15;
    if ( v15 < 0 )
      break;
    v19 = v25;
    v5 = hMem;
    ++v25;
    a2 = (WCHAR *)hMem;
    v13 = hMem;
    if ( v25 > 5 )
    {
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, v19, GMSAData);
        v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
      goto LABEL_35;
    }
  }
  v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
      (_DWORD)a3,
      v15);
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  GMSAData = v18;
  v5 = hMem;
LABEL_35:
  if ( v7 )
  {
    ldap_unbind(v7);
LABEL_37:
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( v5 )
  {
    LocalFree(v5);
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_D((TRACEHANDLE)v12[2], 0x47u, &WPP_70b8577d707437755865c965214ce19a_Traceguids, GMSAData);
  return (unsigned int)GMSAData;
}

```

## disassembly

```asm
0x180003200  mov     [rsp-38h+arg_18], r9
0x180003205  mov     [rsp-38h+arg_0], rcx
0x18000320a  push    rbp
0x18000320b  push    rbx
0x18000320c  push    rsi
0x18000320d  push    rdi
0x18000320e  push    r12
0x180003210  push    r13
0x180003212  push    r15
0x180003214  mov     rbp, rsp
0x180003217  sub     rsp, 50h
0x18000321b  xor     edi, edi
0x18000321d  mov     rbx, r9
0x180003220  xor     r15d, r15d
0x180003223  mov     [rbp+hMem], rdi
0x180003227  mov     [rbp+ld], r15
0x18000322b  mov     r12, r8
0x18000322e  mov     rsi, rdx
0x180003231  mov     rcx, cs:WPP_GLOBAL_Control
0x180003238  lea     r13, WPP_GLOBAL_Control
0x18000323f  cmp     rcx, r13
0x180003242  jz      short loc_18000325D
0x180003244  test    byte ptr [rcx+1Ch], 8
0x180003248  jz      short loc_18000325D
0x18000324a  mov     rcx, [rcx+10h]
0x18000324e  lea     edx, [rdi+41h]
0x180003251  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003258  call    WPP_SF_
0x18000325d  mov     rax, [rbp+arg_20]
0x180003261  mov     [rbx], edi
0x180003263  mov     [rax], rdi
0x180003266  test    rsi, rsi
0x180003269  jnz     short loc_1800032D6
0x18000326b  mov     [rsp+50h+var_28], rdi; unsigned __int16 **
0x180003270  lea     r9, [rbp+hMem]; unsigned __int16 **
0x180003274  mov     r8, r12; unsigned __int16 *
0x180003277  mov     [rsp+50h+var_30], rdi; unsigned __int16 **
0x18000327c  lea     edx, [rsi+1]; int
0x18000327f  xor     ecx, ecx; int
0x180003281  call    ?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z; GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)
0x180003286  mov     ebx, eax
0x180003288  test    eax, eax
0x18000328a  jns     short loc_1800032CA
0x18000328c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003293  cmp     rcx, r13
0x180003296  jz      short loc_1800032C1
0x180003298  test    byte ptr [rcx+1Ch], 4
0x18000329c  jz      short loc_1800032C1
0x18000329e  mov     rcx, [rcx+10h]
0x1800032a2  lea     edx, [rsi+42h]
0x1800032a5  mov     r9, r12
0x1800032a8  mov     dword ptr [rsp+50h+var_30], eax
0x1800032ac  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800032b3  call    WPP_SF_SD
0x1800032b8  mov     rdi, [rbp+hMem]
0x1800032bc  jmp     loc_1800034A3
0x1800032c1  mov     rdi, [rbp+hMem]
0x1800032c5  jmp     loc_1800034AA
0x1800032ca  mov     rdi, [rbp+hMem]
0x1800032ce  mov     rsi, rdi
0x1800032d1  mov     r13, rdi
0x1800032d4  jmp     short loc_1800032D9
0x1800032d6  xor     r13d, r13d
0x1800032d9  mov     [rbp+arg_8], 1
0x1800032e0  test    r15, r15
0x1800032e3  jz      short loc_1800032FC
0x1800032e5  mov     rcx, r15; ld
0x1800032e8  call    cs:__imp_ldap_unbind
0x1800032ef  nop     dword ptr [rax+rax+00h]
0x1800032f4  mov     [rbp+ld], 0
0x1800032fc  lea     r8, [rbp+ld]
0x180003300  mov     rdx, r12
0x180003303  mov     rcx, rsi; HostName
0x180003306  call    GmsapLdapBind
0x18000330b  mov     r15, [rbp+ld]
0x18000330f  mov     ebx, eax
0x180003311  test    eax, eax
0x180003313  js      short loc_18000336C
0x180003315  mov     r9, [rbp+arg_20]
0x180003319  mov     rcx, r15; ld
0x18000331c  mov     r8, [rbp+arg_18]
0x180003320  mov     rdx, [rbp+arg_0]
0x180003324  call    GmsapLdapRetrieveGMSAData
0x180003329  mov     ebx, eax
0x18000332b  test    eax, eax
0x18000332d  jns     loc_18000343B
0x180003333  mov     rcx, cs:WPP_GLOBAL_Control
0x18000333a  lea     rax, WPP_GLOBAL_Control
0x180003341  cmp     rcx, rax
0x180003344  jz      short loc_1800033A1
0x180003346  test    byte ptr [rcx+1Ch], 4
0x18000334a  jz      short loc_1800033A1
0x18000334c  mov     rax, [rbp+arg_0]
0x180003350  mov     r9, r12
0x180003353  mov     rcx, [rcx+10h]; LoggerHandle
0x180003357  mov     dword ptr [rsp+50h+var_20], ebx; char
0x18000335b  mov     [rsp+50h+var_28], rsi; __int64
0x180003360  mov     [rsp+50h+var_30], rax; __int64
0x180003365  call    WPP_SF_SSSD
0x18000336a  jmp     short loc_1800033A1
0x18000336c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003373  lea     rax, WPP_GLOBAL_Control
0x18000337a  cmp     rcx, rax
0x18000337d  jz      short loc_1800033A1
0x18000337f  test    byte ptr [rcx+1Ch], 4
0x180003383  jz      short loc_1800033A1
0x180003385  mov     rcx, [rcx+10h]
0x180003389  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003390  mov     edx, 44h ; 'D'
0x180003395  mov     dword ptr [rsp+50h+var_30], ebx
0x180003399  mov     r9, rsi
0x18000339c  call    WPP_SF_SD
0x1800033a1  test    r13, r13
0x1800033a4  jz      short loc_1800033BD
0x1800033a6  mov     rcx, rdi; hMem
0x1800033a9  call    cs:__imp_LocalFree
0x1800033b0  nop     dword ptr [rax+rax+00h]
0x1800033b5  mov     [rbp+hMem], 0
0x1800033bd  mov     r13d, 1
0x1800033c3  mov     [rsp+50h+var_28], 0; unsigned __int16 **
0x1800033cc  mov     edx, r13d; int
0x1800033cf  mov     [rsp+50h+var_30], 0; unsigned __int16 **
0x1800033d8  mov     ecx, r13d; int
0x1800033db  lea     r9, [rbp+hMem]; unsigned __int16 **
0x1800033df  mov     r8, r12; unsigned __int16 *
0x1800033e2  call    ?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z; GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)
0x1800033e7  mov     edi, eax
0x1800033e9  test    eax, eax
0x1800033eb  js      short loc_18000344D
0x1800033ed  mov     eax, [rbp+arg_8]
0x1800033f0  mov     r9d, eax
0x1800033f3  mov     rdi, [rbp+hMem]
0x1800033f7  add     eax, r13d
0x1800033fa  mov     [rbp+arg_8], eax
0x1800033fd  mov     rsi, rdi
0x180003400  mov     r13, rdi
0x180003403  cmp     eax, 5
0x180003406  jbe     loc_1800032E0
0x18000340c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003413  lea     r13, WPP_GLOBAL_Control
0x18000341a  cmp     rcx, r13
0x18000341d  jz      short loc_18000348F
0x18000341f  test    byte ptr [rcx+1Ch], 4
0x180003423  jz      short loc_18000348F
0x180003425  mov     rcx, [rcx+10h]
0x180003429  mov     dword ptr [rsp+50h+var_30], ebx
0x18000342d  call    WPP_SF_DD
0x180003432  mov     rcx, cs:WPP_GLOBAL_Control
0x180003439  jmp     short loc_18000348F
0x18000343b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003442  lea     r13, WPP_GLOBAL_Control
0x180003449  xor     ebx, ebx
0x18000344b  jmp     short loc_18000348F
0x18000344d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003454  lea     r13, WPP_GLOBAL_Control
0x18000345b  cmp     rcx, r13
0x18000345e  jz      short loc_180003489
0x180003460  test    byte ptr [rcx+1Ch], 4
0x180003464  jz      short loc_180003489
0x180003466  mov     rcx, [rcx+10h]
0x18000346a  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003471  mov     edx, 45h ; 'E'
0x180003476  mov     dword ptr [rsp+50h+var_30], edi
0x18000347a  mov     r9, r12
0x18000347d  call    WPP_SF_SD
0x180003482  mov     rcx, cs:WPP_GLOBAL_Control
0x180003489  mov     ebx, edi
0x18000348b  mov     rdi, [rbp+hMem]
0x18000348f  test    r15, r15
0x180003492  jz      short loc_1800034AA
0x180003494  mov     rcx, r15; ld
0x180003497  call    cs:__imp_ldap_unbind
0x18000349e  nop     dword ptr [rax+rax+00h]
0x1800034a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034aa  test    rdi, rdi
0x1800034ad  jz      short loc_1800034C5
0x1800034af  mov     rcx, rdi; hMem
0x1800034b2  call    cs:__imp_LocalFree
0x1800034b9  nop     dword ptr [rax+rax+00h]
0x1800034be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034c5  cmp     rcx, r13
0x1800034c8  jz      short loc_1800034E8
0x1800034ca  test    byte ptr [rcx+1Ch], 8
0x1800034ce  jz      short loc_1800034E8
0x1800034d0  mov     rcx, [rcx+10h]
0x1800034d4  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800034db  mov     edx, 47h ; 'G'
0x1800034e0  mov     r9d, ebx
0x1800034e3  call    WPP_SF_D
0x1800034e8  mov     eax, ebx
0x1800034ea  add     rsp, 50h
0x1800034ee  pop     r15
0x1800034f0  pop     r13
0x1800034f2  pop     r12
0x1800034f4  pop     rdi
0x1800034f5  pop     rsi
0x1800034f6  pop     rbx
0x1800034f7  pop     rbp
0x1800034f8  retn
```
