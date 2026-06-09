# NlpVerifyTargetServerRODCCachability(_DOMAIN_INFO *,_SERVER_SESSION *,_SECPKG_NTLM_TARGETINFO *,int *)

- ea: `0x18003153c`
- end: `0x1800317e6`
- name: `?NlpVerifyTargetServerRODCCachability@@YAJPEAU_DOMAIN_INFO@@PEAU_SERVER_SESSION@@PEAU_SECPKG_NTLM_TARGETINFO@@PEAH@Z`
- size: `682`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, struct _SERVER_SESSION *, struct _SECPKG_NTLM_TARGETINFO *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003121c`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000e270`
- `0x18002ae5c`
- `0x18003153c`
- `0x180089a30`
- `0x18008a010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800316ad`
- `ntdll!RtlInitUnicodeString` at `0x1800316ad`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180031786`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180031786`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180031701`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180031701`
- `SAMSRV!SamIQueryAccountSecretsCachability` at `0x18003173c`
- `SAMSRV!SamIQueryAccountSecretsCachability` at `0x18003173c`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003177c`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003177c`
- `SAMSRV!SamrCloseHandle` at `0x180031790`
- `SAMSRV!SamrCloseHandle` at `0x180031790`

## string_xrefs

- `0x1800315b0`: `NlpVerifyTargetServerRODCCachability: No NB computer name present in AV pairs - unable to verify RODC cachability for server\n`

## pseudocode

```c
__int64 __fastcall NlpVerifyTargetServerRODCCachability(
        struct _DOMAIN_INFO *a1,
        struct _SERVER_SESSION *a2,
        struct _SECPKG_NTLM_TARGETINFO *a3,
        int *a4)
{
  bool v7; // zf
  unsigned __int16 *v9; // rbx
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rax
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdi
  __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  unsigned __int16 *v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v22; // [rsp+0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+20h] [rbp-30h]
  int v24; // [rsp+50h] [rbp+0h] BYREF
  __int64 v25; // [rsp+58h] [rbp+8h] BYREF
  __int64 v26; // [rsp+60h] [rbp+10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+18h] BYREF
  __int128 v28; // [rsp+78h] [rbp+28h] BYREF

  v24 = 0;
  v26 = 0;
  v7 = *((_DWORD *)a2 + 8) == 7;
  v9 = 0;
  v25 = 0;
  DestinationString = 0;
  *a4 = 0;
  v28 = 0;
  if ( v7 && *((_DWORD *)a2 + 58) )
  {
    v10 = *((_QWORD *)a3 + 1);
    if ( v10 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v10 + 2 * v12) );
      v13 = v12 + 2;
      v14 = 2 * (v12 + 2);
      if ( !v14
        || v14 > g_ulMaxStackAllocSize
        || v14 + g_ulAdditionalProbeSize + 8 < v14
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_33;
      }
      v15 = v14 + 23;
      if ( v14 + 23 <= v14 + 8 )
        v15 = 0xFFFFFFFFFFFFFF0LL;
      v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
      v17 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = (unsigned __int16 *)&v24;
      if ( &v22 == (__int64 *)-80LL || (v24 = 1801679955, (v9 = (unsigned __int16 *)&v25) == 0) )
      {
LABEL_33:
        if ( v14 + 8 >= v14 )
        {
          v18 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
          v9 = v18;
          if ( v18 )
          {
            *(_DWORD *)v18 = 1885431112;
            v9 = v18 + 4;
          }
        }
      }
      if ( v9 )
      {
        v11 = RtlStringCchPrintfW(v9, v13, L"%s$", *((_QWORD *)a3 + 1));
        if ( v11 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, v9);
          NlPrintRoutine(
            0x100u,
            L"NlpVerifyTargetServerRODCCachability: querying SAM for target account TargetServer:'%wZ'\n",
            &DestinationString);
          v19 = SamIGetUserLogonInformation2(*((_QWORD *)a1 + 47), 8, &DestinationString, 4, 0, 0, &v25, &v28, &v26);
          v11 = v19;
          if ( v19 >= 0 )
          {
            v20 = SamIQueryAccountSecretsCachability(*(unsigned int *)(v25 + 272), *((unsigned int *)a2 + 58), &v24);
            v11 = v20;
            if ( v20 < 0 )
            {
              LODWORD(v23) = v20;
              NlPrintRoutine(
                0x100u,
                L"NlpVerifyTargetServerRODCCachability: SamIQueryAccountSecretsCachability failed TargetServer:'%wZ' Rid:0"
                 "x%x Status:0x%x\n",
                &DestinationString,
                *(unsigned int *)(v25 + 272),
                v23);
            }
            *a4 = v24;
          }
          else
          {
            NlPrintRoutine(
              0x100u,
              L"NlpVerifyTargetServerRODCCachability: SamIGetUserLogonInformation2 failed TargetServer:'%wZ' Status:0x%x\n",
              &DestinationString,
              (unsigned int)v19);
          }
        }
      }
      else
      {
        v11 = -1073741670;
      }
    }
    else
    {
      NlPrintRoutine(
        0x100u,
        L"NlpVerifyTargetServerRODCCachability: No NB computer name present in AV pairs - unable to verify RODC cachability for server\n");
      *a4 = 1;
      v11 = 0;
    }
  }
  else
  {
    v11 = -1073741595;
  }
  SamIFreeSidAndAttributesList(&v28);
  SamIFree_UserInternal6Information(v25);
  SamrCloseHandle(&v26);
  if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  NlPrintRoutine(0x100u, L"NlpVerifyTargetServerRODCCachability: returning Status:0x%x\n", (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003153c  push    rbp
0x18003153e  push    rbx
0x18003153f  push    rsi
0x180031540  push    rdi
0x180031541  push    r12
0x180031543  push    r13
0x180031545  push    r14
0x180031547  push    r15
0x180031549  sub     rsp, 0A8h
0x180031550  lea     rbp, [rsp+50h]
0x180031555  mov     rax, cs:__security_cookie
0x18003155c  xor     rax, rbp
0x18003155f  mov     [rbp+90h+var_50], rax
0x180031563  mov     r14, rdx
0x180031566  xorps   xmm0, xmm0
0x180031569  xor     edx, edx
0x18003156b  xorps   xmm1, xmm1
0x18003156e  mov     rsi, r9
0x180031571  mov     [rbp+90h+var_90], edx
0x180031574  mov     r13, r8
0x180031577  mov     [rbp+90h+var_80], rdx
0x18003157b  cmp     dword ptr [r14+20h], 7
0x180031580  mov     r12, rcx
0x180031583  mov     ebx, edx
0x180031585  mov     [rbp+90h+var_88], rdx
0x180031589  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18003158d  mov     [r9], edx
0x180031590  movups  [rbp+90h+var_68], xmm1
0x180031594  jnz     loc_180031773
0x18003159a  cmp     [r14+0E8h], edx
0x1800315a1  jz      loc_180031773
0x1800315a7  mov     rcx, [r8+8]
0x1800315ab  test    rcx, rcx
0x1800315ae  jnz     short loc_1800315D2
0x1800315b0  lea     rdx, aNlpverifytarge_1; "NlpVerifyTargetServerRODCCachability: N"...
0x1800315b7  mov     ecx, 100h; unsigned int
0x1800315bc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800315c1  xor     r15d, r15d
0x1800315c4  mov     dword ptr [rsi], 1
0x1800315ca  mov     edi, r15d
0x1800315cd  jmp     loc_180031778
0x1800315d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800315d6  inc     rax
0x1800315d9  cmp     [rcx+rax*2], dx
0x1800315dd  jnz     short loc_1800315D6
0x1800315df  lea     r15, [rax+2]
0x1800315e3  lea     rdi, [r15+r15]
0x1800315e7  test    rdi, rdi
0x1800315ea  jz      short loc_18003164D
0x1800315ec  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800315f3  ja      short loc_18003164D
0x1800315f5  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800315fc  add     rcx, 8
0x180031600  add     rcx, rdi
0x180031603  cmp     rcx, rdi
0x180031606  jb      short loc_18003164D
0x180031608  call    VerifyStackAvailable
0x18003160d  test    eax, eax
0x18003160f  jz      short loc_18003164D
0x180031611  lea     rax, [rdi+8]
0x180031615  lea     rcx, [rax+0Fh]
0x180031619  cmp     rcx, rax
0x18003161c  ja      short loc_180031628
0x18003161e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180031628  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003162c  mov     rax, rcx
0x18003162f  call    _alloca_probe
0x180031634  sub     rsp, rcx
0x180031637  lea     rbx, [rsp+0E0h+var_90]
0x18003163c  test    rbx, rbx
0x18003163f  jz      short loc_18003164D
0x180031641  mov     dword ptr [rbx], 6B637453h
0x180031647  add     rbx, 8
0x18003164b  jnz     short loc_180031674
0x18003164d  lea     rcx, [rdi+8]
0x180031651  cmp     rcx, rdi
0x180031654  jb      short loc_180031674
0x180031656  mov     rax, cs:g_pfnAllocate
0x18003165d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031662  mov     rbx, rax
0x180031665  test    rax, rax
0x180031668  jz      short loc_180031674
0x18003166a  mov     dword ptr [rax], 70616548h
0x180031670  add     rbx, 8
0x180031674  test    rbx, rbx
0x180031677  jnz     short loc_180031683
0x180031679  mov     edi, 0C000009Ah
0x18003167e  jmp     loc_180031778
0x180031683  mov     r9, [r13+8]
0x180031687  lea     r8, aS; "%s$"
0x18003168e  mov     rdx, r15; unsigned __int64
0x180031691  mov     rcx, rbx; unsigned __int16 *
0x180031694  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031699  xor     r15d, r15d
0x18003169c  mov     edi, eax
0x18003169e  test    eax, eax
0x1800316a0  js      loc_180031778
0x1800316a6  mov     rdx, rbx; SourceString
0x1800316a9  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800316ad  call    cs:__imp_RtlInitUnicodeString
0x1800316b3  lea     r8, [rbp+90h+DestinationString]
0x1800316b7  mov     ecx, 100h; unsigned int
0x1800316bc  lea     rdx, aNlpverifytarge_0; "NlpVerifyTargetServerRODCCachability: q"...
0x1800316c3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800316c8  mov     rcx, [r12+178h]
0x1800316d0  lea     rax, [rbp+90h+var_80]
0x1800316d4  mov     [rsp+0E0h+var_A0], rax
0x1800316d9  lea     r9d, [r15+4]
0x1800316dd  lea     rax, [rbp+90h+var_68]
0x1800316e1  mov     [rsp+0E0h+var_A8], rax
0x1800316e6  lea     r8, [rbp+90h+DestinationString]
0x1800316ea  lea     rax, [rbp+90h+var_88]
0x1800316ee  mov     [rsp+0E0h+var_B0], rax
0x1800316f3  lea     edx, [r15+8]
0x1800316f7  mov     [rsp+0E0h+var_B8], r15
0x1800316fc  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x180031701  call    cs:__imp_SamIGetUserLogonInformation2
0x180031707  mov     edi, eax
0x180031709  test    eax, eax
0x18003170b  jns     short loc_180031727
0x18003170d  mov     r9d, eax
0x180031710  lea     r8, [rbp+90h+DestinationString]
0x180031714  lea     rdx, aNlpverifytarge; "NlpVerifyTargetServerRODCCachability: S"...
0x18003171b  mov     ecx, 100h; unsigned int
0x180031720  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180031725  jmp     short loc_180031778
0x180031727  mov     rcx, [rbp+90h+var_88]
0x18003172b  lea     r8, [rbp+90h+var_90]
0x18003172f  mov     edx, [r14+0E8h]
0x180031736  mov     ecx, [rcx+110h]
0x18003173c  call    cs:__imp_SamIQueryAccountSecretsCachability
0x180031742  mov     edi, eax
0x180031744  test    eax, eax
0x180031746  jns     short loc_18003176C
0x180031748  mov     r9, [rbp+90h+var_88]
0x18003174c  lea     r8, [rbp+90h+DestinationString]
0x180031750  lea     rdx, aNlpverifytarge_3; "NlpVerifyTargetServerRODCCachability: S"...
0x180031757  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18003175b  mov     ecx, 100h; unsigned int
0x180031760  mov     r9d, [r9+110h]
0x180031767  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003176c  mov     eax, [rbp+90h+var_90]
0x18003176f  mov     [rsi], eax
0x180031771  jmp     short loc_180031778
0x180031773  mov     edi, 0C00000E5h
0x180031778  lea     rcx, [rbp+90h+var_68]
0x18003177c  call    cs:__imp_SamIFreeSidAndAttributesList
0x180031782  mov     rcx, [rbp+90h+var_88]
0x180031786  call    cs:__imp_SamIFree_UserInternal6Information
0x18003178c  lea     rcx, [rbp+90h+var_80]
0x180031790  call    cs:__imp_SamrCloseHandle
0x180031796  test    rbx, rbx
0x180031799  jz      short loc_1800317B3
0x18003179b  lea     rcx, [rbx-8]
0x18003179f  cmp     dword ptr [rcx], 70616548h
0x1800317a5  jnz     short loc_1800317B3
0x1800317a7  mov     rax, cs:g_pfnFree
0x1800317ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317b3  mov     r8d, edi
0x1800317b6  lea     rdx, aNlpverifytarge_2; "NlpVerifyTargetServerRODCCachability: r"...
0x1800317bd  mov     ecx, 100h; unsigned int
0x1800317c2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800317c7  mov     eax, edi
0x1800317c9  mov     rcx, [rbp+90h+var_50]
0x1800317cd  xor     rcx, rbp; StackCookie
0x1800317d0  call    __security_check_cookie
0x1800317d5  lea     rsp, [rbp+58h]
0x1800317d9  pop     r15
0x1800317db  pop     r14
0x1800317dd  pop     r13
0x1800317df  pop     r12
0x1800317e1  pop     rdi
0x1800317e2  pop     rsi
0x1800317e3  pop     rbx
0x1800317e4  pop     rbp
0x1800317e5  retn
```
