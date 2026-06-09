# NlpVerifyTargetServerRODCCachability(_DOMAIN_INFO *,_SERVER_SESSION *,_SECPKG_NTLM_TARGETINFO *,int *)

- ea: `0x1800332c0`
- end: `0x18003358f`
- name: `?NlpVerifyTargetServerRODCCachability@@YAJPEAU_DOMAIN_INFO@@PEAU_SERVER_SESSION@@PEAU_SECPKG_NTLM_TARGETINFO@@PEAH@Z`
- size: `719`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, struct _SERVER_SESSION *, struct _SECPKG_NTLM_TARGETINFO *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032f90`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x18002c758`
- `0x1800332c0`
- `0x180090180`
- `0x180091010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180033431`
- `ntdll!RtlInitUnicodeString` at `0x180033431`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180033522`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180033522`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18003348b`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18003348b`
- `SAMSRV!SamIQueryAccountSecretsCachability` at `0x1800334cc`
- `SAMSRV!SamIQueryAccountSecretsCachability` at `0x1800334cc`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180033512`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180033512`
- `SAMSRV!SamrCloseHandle` at `0x180033532`
- `SAMSRV!SamrCloseHandle` at `0x180033532`

## string_xrefs

- `0x180033334`: `NlpVerifyTargetServerRODCCachability: No NB computer name present in AV pairs - unable to verify RODC cachability for server\n`

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
0x1800332c0  push    rbp
0x1800332c2  push    rbx
0x1800332c3  push    rsi
0x1800332c4  push    rdi
0x1800332c5  push    r12
0x1800332c7  push    r13
0x1800332c9  push    r14
0x1800332cb  push    r15
0x1800332cd  sub     rsp, 0A8h
0x1800332d4  lea     rbp, [rsp+50h]
0x1800332d9  mov     rax, cs:__security_cookie
0x1800332e0  xor     rax, rbp
0x1800332e3  mov     [rbp+90h+var_50], rax
0x1800332e7  mov     r14, rdx
0x1800332ea  xorps   xmm0, xmm0
0x1800332ed  xor     edx, edx
0x1800332ef  xorps   xmm1, xmm1
0x1800332f2  mov     rsi, r9
0x1800332f5  mov     [rbp+90h+var_90], edx
0x1800332f8  mov     r13, r8
0x1800332fb  mov     [rbp+90h+var_80], rdx
0x1800332ff  cmp     dword ptr [r14+20h], 7
0x180033304  mov     r12, rcx
0x180033307  mov     ebx, edx
0x180033309  mov     [rbp+90h+var_88], rdx
0x18003330d  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x180033311  mov     [r9], edx
0x180033314  movups  [rbp+90h+var_68], xmm1
0x180033318  jnz     loc_180033509
0x18003331e  cmp     [r14+0E8h], edx
0x180033325  jz      loc_180033509
0x18003332b  mov     rcx, [r8+8]
0x18003332f  test    rcx, rcx
0x180033332  jnz     short loc_180033356
0x180033334  lea     rdx, aNlpverifytarge_1; "NlpVerifyTargetServerRODCCachability: N"...
0x18003333b  mov     ecx, 100h; unsigned int
0x180033340  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033345  xor     r15d, r15d
0x180033348  mov     dword ptr [rsi], 1
0x18003334e  mov     edi, r15d
0x180033351  jmp     loc_18003350E
0x180033356  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003335a  inc     rax
0x18003335d  cmp     [rcx+rax*2], dx
0x180033361  jnz     short loc_18003335A
0x180033363  lea     r15, [rax+2]
0x180033367  lea     rdi, [r15+r15]
0x18003336b  test    rdi, rdi
0x18003336e  jz      short loc_1800333D1
0x180033370  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180033377  ja      short loc_1800333D1
0x180033379  mov     rcx, cs:g_ulAdditionalProbeSize
0x180033380  add     rcx, 8
0x180033384  add     rcx, rdi
0x180033387  cmp     rcx, rdi
0x18003338a  jb      short loc_1800333D1
0x18003338c  call    VerifyStackAvailable
0x180033391  test    eax, eax
0x180033393  jz      short loc_1800333D1
0x180033395  lea     rax, [rdi+8]
0x180033399  lea     rcx, [rax+0Fh]
0x18003339d  cmp     rcx, rax
0x1800333a0  ja      short loc_1800333AC
0x1800333a2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800333ac  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800333b0  mov     rax, rcx
0x1800333b3  call    _alloca_probe
0x1800333b8  sub     rsp, rcx
0x1800333bb  lea     rbx, [rsp+0E0h+var_90]
0x1800333c0  test    rbx, rbx
0x1800333c3  jz      short loc_1800333D1
0x1800333c5  mov     dword ptr [rbx], 6B637453h
0x1800333cb  add     rbx, 8
0x1800333cf  jnz     short loc_1800333F8
0x1800333d1  lea     rcx, [rdi+8]
0x1800333d5  cmp     rcx, rdi
0x1800333d8  jb      short loc_1800333F8
0x1800333da  mov     rax, cs:g_pfnAllocate
0x1800333e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333e6  mov     rbx, rax
0x1800333e9  test    rax, rax
0x1800333ec  jz      short loc_1800333F8
0x1800333ee  mov     dword ptr [rax], 70616548h
0x1800333f4  add     rbx, 8
0x1800333f8  test    rbx, rbx
0x1800333fb  jnz     short loc_180033407
0x1800333fd  mov     edi, 0C000009Ah
0x180033402  jmp     loc_18003350E
0x180033407  mov     r9, [r13+8]
0x18003340b  lea     r8, aS; "%s$"
0x180033412  mov     rdx, r15; unsigned __int64
0x180033415  mov     rcx, rbx; unsigned __int16 *
0x180033418  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003341d  xor     r15d, r15d
0x180033420  mov     edi, eax
0x180033422  test    eax, eax
0x180033424  js      loc_18003350E
0x18003342a  mov     rdx, rbx; SourceString
0x18003342d  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x180033431  call    cs:__imp_RtlInitUnicodeString
0x180033438  nop     dword ptr [rax+rax+00h]
0x18003343d  lea     r8, [rbp+90h+DestinationString]
0x180033441  mov     ecx, 100h; unsigned int
0x180033446  lea     rdx, aNlpverifytarge_0; "NlpVerifyTargetServerRODCCachability: q"...
0x18003344d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033452  mov     rcx, [r12+178h]
0x18003345a  lea     rax, [rbp+90h+var_80]
0x18003345e  mov     [rsp+0E0h+var_A0], rax
0x180033463  lea     r9d, [r15+4]
0x180033467  lea     rax, [rbp+90h+var_68]
0x18003346b  mov     [rsp+0E0h+var_A8], rax
0x180033470  lea     r8, [rbp+90h+DestinationString]
0x180033474  lea     rax, [rbp+90h+var_88]
0x180033478  mov     [rsp+0E0h+var_B0], rax
0x18003347d  lea     edx, [r15+8]
0x180033481  mov     [rsp+0E0h+var_B8], r15
0x180033486  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x18003348b  call    cs:__imp_SamIGetUserLogonInformation2
0x180033492  nop     dword ptr [rax+rax+00h]
0x180033497  mov     edi, eax
0x180033499  test    eax, eax
0x18003349b  jns     short loc_1800334B7
0x18003349d  mov     r9d, eax
0x1800334a0  lea     r8, [rbp+90h+DestinationString]
0x1800334a4  lea     rdx, aNlpverifytarge; "NlpVerifyTargetServerRODCCachability: S"...
0x1800334ab  mov     ecx, 100h; unsigned int
0x1800334b0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800334b5  jmp     short loc_18003350E
0x1800334b7  mov     rcx, [rbp+90h+var_88]
0x1800334bb  lea     r8, [rbp+90h+var_90]
0x1800334bf  mov     edx, [r14+0E8h]
0x1800334c6  mov     ecx, [rcx+110h]
0x1800334cc  call    cs:__imp_SamIQueryAccountSecretsCachability
0x1800334d3  nop     dword ptr [rax+rax+00h]
0x1800334d8  mov     edi, eax
0x1800334da  test    eax, eax
0x1800334dc  jns     short loc_180033502
0x1800334de  mov     r9, [rbp+90h+var_88]
0x1800334e2  lea     r8, [rbp+90h+DestinationString]
0x1800334e6  lea     rdx, aNlpverifytarge_3; "NlpVerifyTargetServerRODCCachability: S"...
0x1800334ed  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800334f1  mov     ecx, 100h; unsigned int
0x1800334f6  mov     r9d, [r9+110h]
0x1800334fd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033502  mov     eax, [rbp+90h+var_90]
0x180033505  mov     [rsi], eax
0x180033507  jmp     short loc_18003350E
0x180033509  mov     edi, 0C00000E5h
0x18003350e  lea     rcx, [rbp+90h+var_68]
0x180033512  call    cs:__imp_SamIFreeSidAndAttributesList
0x180033519  nop     dword ptr [rax+rax+00h]
0x18003351e  mov     rcx, [rbp+90h+var_88]
0x180033522  call    cs:__imp_SamIFree_UserInternal6Information
0x180033529  nop     dword ptr [rax+rax+00h]
0x18003352e  lea     rcx, [rbp+90h+var_80]
0x180033532  call    cs:__imp_SamrCloseHandle
0x180033539  nop     dword ptr [rax+rax+00h]
0x18003353e  test    rbx, rbx
0x180033541  jz      short loc_18003355B
0x180033543  lea     rcx, [rbx-8]
0x180033547  cmp     dword ptr [rcx], 70616548h
0x18003354d  jnz     short loc_18003355B
0x18003354f  mov     rax, cs:g_pfnFree
0x180033556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003355b  mov     r8d, edi
0x18003355e  lea     rdx, aNlpverifytarge_2; "NlpVerifyTargetServerRODCCachability: r"...
0x180033565  mov     ecx, 100h; unsigned int
0x18003356a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003356f  mov     eax, edi
0x180033571  mov     rcx, [rbp+90h+var_50]
0x180033575  xor     rcx, rbp; StackCookie
0x180033578  call    __security_check_cookie
0x18003357d  lea     rsp, [rbp+58h]
0x180033581  pop     r15
0x180033583  pop     r14
0x180033585  pop     r13
0x180033587  pop     r12
0x180033589  pop     rdi
0x18003358a  pop     rsi
0x18003358b  pop     rbx
0x18003358c  pop     rbp
0x18003358d  retn
```
