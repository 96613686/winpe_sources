# CollectTrustsToScan(_SCANNER_REQUEST *,_LIST_ENTRY *)

- ea: `0x18002f9d0`
- end: `0x18002fda7`
- name: `?CollectTrustsToScan@@YAJPEAU_SCANNER_REQUEST@@PEAU_LIST_ENTRY@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(struct _SCANNER_REQUEST *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180031d70`

## callees

- `0x18000cca4`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x18002f9d0`
- `0x18002fdb0`
- `0x1800303e4`
- `0x1800307cc`
- `0x18003080c`
- `0x180032b38`
- `0x180032bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002faf0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002faf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fafc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fafc`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002fa35`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002fa35`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002fd47`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002fd47`

## pseudocode

```c
__int64 __fastcall CollectTrustsToScan(struct _SCANNER_REQUEST *a1, struct _LIST_ENTRY *a2)
{
  int v2; // r12d
  void *v5; // rcx
  int LockTrustedDomainList; // eax
  int v7; // ebx
  unsigned int v8; // edi
  int v9; // esi
  int v10; // eax
  struct _LIST_ENTRY *v11; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v13; // r8
  _QWORD *v14; // r11
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v15; // rsi
  int v16; // ebx
  __int64 v17; // rdx
  char *v18; // r9
  char *v19; // r14
  int TrustScanContext; // eax
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v22; // rax
  struct _LIST_ENTRY *v23; // rax
  HLOCAL v25; // [rsp+40h] [rbp-30h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v26; // [rsp+48h] [rbp-28h] BYREF
  struct _LSAPR_TRUST_INFORMATION *v27; // [rsp+50h] [rbp-20h] BYREF
  struct _LIST_ENTRY v28; // [rsp+58h] [rbp-18h] BYREF
  int v29; // [rsp+C0h] [rbp+50h]
  HLOCAL hMem; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  hMem = 0;
  v28 = 0;
  v25 = 0;
  v26 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
  v28.Blink = &v28;
  v28.Flink = &v28;
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v5);
  v7 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        (unsigned int)LockTrustedDomainList);
    goto LABEL_55;
  }
  v29 = 0;
  v8 = 0;
  v9 = 0;
  v10 = LsaDbpTraverseTrustedDomainList(&v26, &v27);
  v14 = WPP_GLOBAL_Control;
  while ( v10 >= 0 )
  {
    ++v2;
    v15 = v26;
    if ( (*((_BYTE *)v14 + 28) & 0x10) != 0 )
    {
      WPP_SF_ZDDD(
        v14[2],
        (_DWORD)v11,
        v13,
        (_DWORD)v26 + 16,
        *((_DWORD *)v26 + 15),
        *((_DWORD *)v26 + 14),
        *((_DWORD *)v26 + 16));
      v14 = WPP_GLOBAL_Control;
    }
    if ( *((_QWORD *)a1 + 2) )
    {
      v7 = CopyLsaString((struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *)((char *)v15 + 16), (unsigned __int16 **)&hMem);
      if ( v7 < 0 )
        goto LABEL_54;
      v16 = _o__wcsicmp(*((_QWORD *)a1 + 2), hMem);
      LocalFree(hMem);
      hMem = 0;
      if ( v16 )
      {
        ++v8;
        v14 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v17 = 37;
          v18 = (char *)v15 + 16;
          goto LABEL_37;
        }
        goto LABEL_38;
      }
      v14 = WPP_GLOBAL_Control;
    }
    v19 = (char *)v15 + 16;
    if ( *((_DWORD *)v15 + 15) != 2 )
    {
      ++v8;
      if ( (*((_BYTE *)v14 + 28) & 0x10) == 0 )
        goto LABEL_38;
      v17 = 38;
      goto LABEL_36;
    }
    if ( !*((_QWORD *)v15 + 6) )
    {
      ++v8;
      if ( (*((_BYTE *)v14 + 28) & 0x10) == 0 )
        goto LABEL_38;
      v17 = 39;
      goto LABEL_36;
    }
    if ( (*((_BYTE *)v15 + 56) & 1) == 0 )
    {
      ++v8;
      if ( (*((_BYTE *)v14 + 28) & 0x10) == 0 )
        goto LABEL_38;
      v17 = 40;
      goto LABEL_36;
    }
    if ( (*((_BYTE *)v15 + 64) & 8) == 0 )
    {
      ++v8;
      if ( (*((_BYTE *)v14 + 28) & 0x10) == 0 )
        goto LABEL_38;
      v17 = 42;
LABEL_36:
      v18 = (char *)v15 + 16;
LABEL_37:
      WPP_SF_Z(v14[2], v17, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, v18);
LABEL_38:
      v9 = v29;
      goto LABEL_39;
    }
    if ( !DcInRootDomain )
    {
      ++v8;
      if ( (*((_BYTE *)v14 + 28) & 0x10) == 0 )
        goto LABEL_38;
      v17 = 41;
      goto LABEL_36;
    }
    TrustScanContext = CreateTrustScanContext(v15, (struct _TRUST_SCAN_CONTEXT **)&v25);
    v7 = TrustScanContext;
    if ( TrustScanContext < 0 )
    {
      Flink = (struct _LIST_ENTRY *)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
          (unsigned int)TrustScanContext);
      goto LABEL_54;
    }
    Blink = v28.Blink;
    if ( v28.Blink->Flink != &v28 )
      goto LABEL_58;
    v22 = (struct _LIST_ENTRY *)v25;
    v11 = &v28;
    v9 = v29 + 1;
    v25 = 0;
    ++v29;
    v22->Flink = &v28;
    v22->Blink = Blink;
    Blink->Flink = v22;
    v28.Blink = v22;
    v14 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, v19);
      v14 = WPP_GLOBAL_Control;
    }
    if ( *((_QWORD *)a1 + 2) )
      goto LABEL_44;
LABEL_39:
    v10 = LsaDbpTraverseTrustedDomainList(&v26, &v27);
  }
  v7 = 0;
  if ( v10 != -2147483622 )
    v7 = v10;
  if ( v7 < 0 )
    goto LABEL_54;
LABEL_44:
  Flink = v28.Flink;
  if ( v28.Flink != &v28 )
  {
    if ( v28.Flink->Blink != &v28
      || (v23 = v28.Blink, v28.Blink->Flink != &v28)
      || (v28.Blink->Flink = v28.Flink, Flink->Blink = v23, v28.Blink = &v28, v28.Flink = &v28, a2->Flink->Blink != a2)
      || (v11 = a2->Blink, v11->Flink != a2)
      || Flink->Flink->Blink != Flink
      || Flink->Blink->Flink != Flink )
    {
LABEL_58:
      __fastfail(3u);
    }
    v11->Flink = Flink;
    a2->Blink = Flink->Blink;
    Flink->Blink->Flink = a2;
    Flink->Blink = v11;
    v14 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v14 + 28) & 0x10) != 0 )
    WPP_SF_ddd(v14[2], v11, v13, v8, v9, v2);
LABEL_54:
  LsapDbExpReleaseLockTrustedDomainList(Flink);
LABEL_55:
  FreeTrustScanContext(v25);
  FreeTrustScanContextList(&v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002f9d0  mov     [rsp-38h+arg_0], rbx
0x18002f9d5  push    rbp
0x18002f9d6  push    rsi
0x18002f9d7  push    rdi
0x18002f9d8  push    r12
0x18002f9da  push    r13
0x18002f9dc  push    r14
0x18002f9de  push    r15
0x18002f9e0  mov     rbp, rsp
0x18002f9e3  sub     rsp, 70h
0x18002f9e7  xor     r12d, r12d
0x18002f9ea  xorps   xmm0, xmm0
0x18002f9ed  mov     [rbp+hMem], r12
0x18002f9f1  mov     r15, rdx
0x18002f9f4  movups  xmmword ptr [rbp+var_18.Flink], xmm0
0x18002f9f8  mov     [rbp+var_30], r12
0x18002f9fc  mov     r13, rcx
0x18002f9ff  mov     [rbp+var_28], r12
0x18002fa03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa0a  test    byte ptr [rcx+1Ch], 10h
0x18002fa0e  jz      short loc_18002FA25
0x18002fa10  mov     rcx, [rcx+10h]
0x18002fa14  lea     edx, [r12+22h]
0x18002fa19  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18002fa20  call    WPP_SF_
0x18002fa25  lea     rax, [rbp+var_18]
0x18002fa29  mov     [rbp+var_18.Blink], rax
0x18002fa2d  lea     rax, [rbp+var_18]
0x18002fa31  mov     [rbp+var_18.Flink], rax
0x18002fa35  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x18002fa3b  mov     ebx, eax
0x18002fa3d  test    eax, eax
0x18002fa3f  jns     short loc_18002FA6F
0x18002fa41  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa48  test    byte ptr [rcx+1Ch], 10h
0x18002fa4c  jz      loc_18002FD4D
0x18002fa52  mov     rcx, [rcx+10h]
0x18002fa56  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18002fa5d  mov     edx, 23h ; '#'
0x18002fa62  mov     r9d, eax
0x18002fa65  call    WPP_SF_d
0x18002fa6a  jmp     loc_18002FD4D
0x18002fa6f  lea     rdx, [rbp+var_20]; struct _LSAPR_TRUST_INFORMATION **
0x18002fa73  mov     [rbp+arg_10], r12d
0x18002fa77  lea     rcx, [rbp+var_28]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18002fa7b  mov     edi, r12d
0x18002fa7e  mov     esi, r12d
0x18002fa81  call    ?LsaDbpTraverseTrustedDomainList@@YAJPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpTraverseTrustedDomainList(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *,_LSAPR_TRUST_INFORMATION * *)
0x18002fa86  mov     r11, cs:WPP_GLOBAL_Control
0x18002fa8d  jmp     loc_18002FC79
0x18002fa92  inc     r12d
0x18002fa95  test    byte ptr [r11+1Ch], 10h
0x18002fa9a  mov     rsi, [rbp+var_28]
0x18002fa9e  jz      short loc_18002FACA
0x18002faa0  mov     rcx, [r11+10h]
0x18002faa4  lea     r9, [rsi+10h]
0x18002faa8  mov     eax, [r9+30h]
0x18002faac  mov     [rsp+70h+var_40], eax
0x18002fab0  mov     eax, [rsi+38h]
0x18002fab3  mov     [rsp+70h+var_48], eax
0x18002fab7  mov     eax, [rsi+3Ch]
0x18002faba  mov     [rsp+70h+var_50], eax
0x18002fabe  call    WPP_SF_ZDDD
0x18002fac3  mov     r11, cs:WPP_GLOBAL_Control
0x18002faca  cmp     qword ptr [r13+10h], 0
0x18002facf  jz      short loc_18002FB37
0x18002fad1  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18002fad5  lea     rcx, [rsi+10h]; struct _LSAPR_UNICODE_STRING *
0x18002fad9  call    ?CopyLsaString@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAG@Z; CopyLsaString(_LSAPR_UNICODE_STRING *,ushort * *)
0x18002fade  mov     ebx, eax
0x18002fae0  test    eax, eax
0x18002fae2  js      loc_18002FD47
0x18002fae8  mov     rdx, [rbp+hMem]
0x18002faec  mov     rcx, [r13+10h]
0x18002faf0  call    cs:__imp__o__wcsicmp
0x18002faf6  mov     rcx, [rbp+hMem]; hMem
0x18002fafa  mov     ebx, eax
0x18002fafc  call    cs:__imp_LocalFree
0x18002fb02  mov     [rbp+hMem], 0
0x18002fb0a  test    ebx, ebx
0x18002fb0c  jz      short loc_18002FB30
0x18002fb0e  inc     edi
0x18002fb10  mov     r11, cs:WPP_GLOBAL_Control
0x18002fb17  test    byte ptr [r11+1Ch], 10h
0x18002fb1c  jz      loc_18002FC69
0x18002fb22  mov     edx, 25h ; '%'
0x18002fb27  lea     r9, [rsi+10h]
0x18002fb2b  jmp     loc_18002FC52
0x18002fb30  mov     r11, cs:WPP_GLOBAL_Control
0x18002fb37  lea     r14, [rsi+10h]
0x18002fb3b  cmp     dword ptr [r14+2Ch], 2
0x18002fb40  jz      short loc_18002FB59
0x18002fb42  inc     edi
0x18002fb44  test    byte ptr [r11+1Ch], 10h
0x18002fb49  jz      loc_18002FC69
0x18002fb4f  mov     edx, 26h ; '&'
0x18002fb54  jmp     loc_18002FC4F
0x18002fb59  cmp     qword ptr [rsi+30h], 0
0x18002fb5e  jnz     short loc_18002FB77
0x18002fb60  inc     edi
0x18002fb62  test    byte ptr [r11+1Ch], 10h
0x18002fb67  jz      loc_18002FC69
0x18002fb6d  mov     edx, 27h ; '''
0x18002fb72  jmp     loc_18002FC4F
0x18002fb77  test    byte ptr [rsi+38h], 1
0x18002fb7b  jnz     short loc_18002FB94
0x18002fb7d  inc     edi
0x18002fb7f  test    byte ptr [r11+1Ch], 10h
0x18002fb84  jz      loc_18002FC69
0x18002fb8a  mov     edx, 28h ; '('
0x18002fb8f  jmp     loc_18002FC4F
0x18002fb94  test    byte ptr [rsi+40h], 8
0x18002fb98  jz      loc_18002FC41
0x18002fb9e  cmp     cs:?DcInRootDomain@@3EA, 0; uchar DcInRootDomain
0x18002fba5  jnz     short loc_18002FBBE
0x18002fba7  inc     edi
0x18002fba9  test    byte ptr [r11+1Ch], 10h
0x18002fbae  jz      loc_18002FC69
0x18002fbb4  mov     edx, 29h ; ')'
0x18002fbb9  jmp     loc_18002FC4F
0x18002fbbe  lea     rdx, [rbp+var_30]; struct _TRUST_SCAN_CONTEXT **
0x18002fbc2  mov     rcx, rsi; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *
0x18002fbc5  call    ?CreateTrustScanContext@@YAJPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAPEAU_TRUST_SCAN_CONTEXT@@@Z; CreateTrustScanContext(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *,_TRUST_SCAN_CONTEXT * *)
0x18002fbca  mov     ebx, eax
0x18002fbcc  test    eax, eax
0x18002fbce  js      loc_18002FD79
0x18002fbd4  mov     rcx, [rbp+var_18.Blink]
0x18002fbd8  lea     rax, [rbp+var_18]
0x18002fbdc  cmp     [rcx], rax
0x18002fbdf  jnz     loc_18002FDA0
0x18002fbe5  mov     rax, [rbp+var_30]
0x18002fbe9  lea     rdx, [rbp+var_18]
0x18002fbed  mov     esi, [rbp+arg_10]
0x18002fbf0  inc     esi
0x18002fbf2  mov     [rbp+var_30], 0
0x18002fbfa  mov     [rbp+arg_10], esi
0x18002fbfd  mov     [rax], rdx
0x18002fc00  mov     [rax+8], rcx
0x18002fc04  mov     [rcx], rax
0x18002fc07  mov     [rbp+var_18.Blink], rax
0x18002fc0b  mov     r11, cs:WPP_GLOBAL_Control
0x18002fc12  test    byte ptr [r11+1Ch], 10h
0x18002fc17  jz      short loc_18002FC38
0x18002fc19  mov     rcx, [r11+10h]
0x18002fc1d  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18002fc24  mov     edx, 2Ch ; ','
0x18002fc29  mov     r9, r14
0x18002fc2c  call    WPP_SF_Z
0x18002fc31  mov     r11, cs:WPP_GLOBAL_Control
0x18002fc38  cmp     qword ptr [r13+10h], 0
0x18002fc3d  jnz     short loc_18002FC93
0x18002fc3f  jmp     short loc_18002FC6C
0x18002fc41  inc     edi
0x18002fc43  test    byte ptr [r11+1Ch], 10h
0x18002fc48  jz      short loc_18002FC69
0x18002fc4a  mov     edx, 2Ah ; '*'
0x18002fc4f  mov     r9, r14
0x18002fc52  mov     rcx, [r11+10h]
0x18002fc56  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18002fc5d  call    WPP_SF_Z
0x18002fc62  mov     r11, cs:WPP_GLOBAL_Control
0x18002fc69  mov     esi, [rbp+arg_10]
0x18002fc6c  lea     rdx, [rbp+var_20]; struct _LSAPR_TRUST_INFORMATION **
0x18002fc70  lea     rcx, [rbp+var_28]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18002fc74  call    ?LsaDbpTraverseTrustedDomainList@@YAJPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z; LsaDbpTraverseTrustedDomainList(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *,_LSAPR_TRUST_INFORMATION * *)
0x18002fc79  test    eax, eax
0x18002fc7b  jns     loc_18002FA92
0x18002fc81  xor     ebx, ebx
0x18002fc83  cmp     eax, 8000001Ah
0x18002fc88  cmovnz  ebx, eax
0x18002fc8b  test    ebx, ebx
0x18002fc8d  js      loc_18002FD47
0x18002fc93  mov     rcx, [rbp+var_18.Flink]
0x18002fc97  lea     rax, [rbp+var_18]
0x18002fc9b  cmp     rcx, rax
0x18002fc9e  jz      loc_18002FD2B
0x18002fca4  lea     rax, [rbp+var_18]
0x18002fca8  cmp     [rcx+8], rax
0x18002fcac  jnz     loc_18002FDA0
0x18002fcb2  mov     rax, [rbp+var_18.Blink]
0x18002fcb6  lea     rdx, [rbp+var_18]
0x18002fcba  cmp     [rax], rdx
0x18002fcbd  jnz     loc_18002FDA0
0x18002fcc3  mov     [rax], rcx
0x18002fcc6  mov     [rcx+8], rax
0x18002fcca  lea     rax, [rbp+var_18]
0x18002fcce  mov     [rbp+var_18.Blink], rax
0x18002fcd2  lea     rax, [rbp+var_18]
0x18002fcd6  mov     [rbp+var_18.Flink], rax
0x18002fcda  mov     rax, [r15]
0x18002fcdd  cmp     [rax+8], r15
0x18002fce1  jnz     loc_18002FDA0
0x18002fce7  mov     rdx, [r15+8]
0x18002fceb  cmp     [rdx], r15
0x18002fcee  jnz     loc_18002FDA0
0x18002fcf4  mov     rax, [rcx]
0x18002fcf7  cmp     [rax+8], rcx
0x18002fcfb  jnz     loc_18002FDA0
0x18002fd01  mov     rax, [rcx+8]
0x18002fd05  cmp     [rax], rcx
0x18002fd08  jnz     loc_18002FDA0
0x18002fd0e  mov     [rdx], rcx
0x18002fd11  mov     rax, [rcx+8]
0x18002fd15  mov     [r15+8], rax
0x18002fd19  mov     rax, [rcx+8]
0x18002fd1d  mov     [rax], r15
0x18002fd20  mov     [rcx+8], rdx
0x18002fd24  mov     r11, cs:WPP_GLOBAL_Control
0x18002fd2b  test    byte ptr [r11+1Ch], 10h
0x18002fd30  jz      short loc_18002FD47
0x18002fd32  mov     rcx, [r11+10h]
0x18002fd36  mov     r9d, edi
0x18002fd39  mov     [rsp+70h+var_48], r12d
0x18002fd3e  mov     [rsp+70h+var_50], esi
0x18002fd42  call    WPP_SF_ddd
0x18002fd47  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18002fd4d  mov     rcx, [rbp+var_30]; hMem
0x18002fd51  call    ?FreeTrustScanContext@@YAXPEAU_TRUST_SCAN_CONTEXT@@@Z; FreeTrustScanContext(_TRUST_SCAN_CONTEXT *)
0x18002fd56  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x18002fd5a  call    ?FreeTrustScanContextList@@YAXPEAU_LIST_ENTRY@@@Z; FreeTrustScanContextList(_LIST_ENTRY *)
0x18002fd5f  mov     eax, ebx
0x18002fd61  mov     rbx, [rsp+70h+arg_0]
0x18002fd69  add     rsp, 70h
0x18002fd6d  pop     r15
0x18002fd6f  pop     r14
0x18002fd71  pop     r13
0x18002fd73  pop     r12
0x18002fd75  pop     rdi
0x18002fd76  pop     rsi
0x18002fd77  pop     rbp
0x18002fd78  retn
0x18002fd79  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd80  test    byte ptr [rcx+1Ch], 10h
0x18002fd84  jz      short loc_18002FD47
0x18002fd86  mov     rcx, [rcx+10h]
0x18002fd8a  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18002fd91  mov     edx, 2Bh ; '+'
0x18002fd96  mov     r9d, eax
0x18002fd99  call    WPP_SF_d
0x18002fd9e  jmp     short loc_18002FD47
0x18002fda0  mov     ecx, 3
0x18002fda5  int     29h; Win8: RtlFailFast(ecx)
```
