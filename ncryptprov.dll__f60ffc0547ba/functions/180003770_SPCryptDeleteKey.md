# SPCryptDeleteKey

- ea: `0x180003770`
- end: `0x180003a6e`
- name: `SPCryptDeleteKey`
- size: `766`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003770`
- `0x180004350`
- `0x180004400`
- `0x180004428`
- `0x1800044d0`
- `0x180009440`
- `0x18000af80`
- `0x18000b250`
- `0x1800204b4`
- `0x180028114`
- `0x180059588`
- `0x18005cd34`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180003a52`
- `ntdll!RtlReleaseResource` at `0x180003a52`
- `ntdll!RtlAcquireResourceShared` at `0x1800037a3`
- `ntdll!RtlAcquireResourceShared` at `0x1800037a3`

## string_xrefs

- `0x1800037cf`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180003871`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000396e`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x1800039cd`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall SPCryptDeleteKey(__int64 a1, __int64 a2, int a3)
{
  char v5; // si
  __int64 v6; // rax
  int v7; // edx
  int v8; // r8d
  __int64 v9; // r14
  struct _RTL_RESOURCE *v10; // rbp
  __int64 v11; // rax
  __int64 v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // eax
  char v22; // si
  int *v23; // rcx

  v5 = 1;
  v6 = KspValidateProvHandle();
  v9 = v6;
  if ( !v6 )
  {
    v12 = 0;
    v13 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        118);
LABEL_41:
    KspCryptAuditCryptOperation(0, v7, v12, 2482, v13);
    v10 = (struct _RTL_RESOURCE *)(v9 + 64);
    if ( !v12 )
      goto LABEL_47;
    goto LABEL_42;
  }
  v10 = (struct _RTL_RESOURCE *)(v6 + 64);
  RtlAcquireResourceShared((PRTL_RESOURCE)(v6 + 64), 1u);
  v11 = KspValidateKeyHandle(a2);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -2146893786;
    v14 = 3199;
    v15 = 2148073510LL;
LABEL_4:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v14);
    goto LABEL_41;
  }
  if ( (a3 & 0xFFFFFFBF) != 0 )
  {
    v13 = -2146893815;
    v14 = 3206;
    v15 = 2148073481LL;
    goto LABEL_4;
  }
  if ( (*(_DWORD *)(v11 + 428) & 0x20) != 0 )
  {
    v13 = -2146893808;
    v14 = 3217;
    v15 = 2148073488LL;
    goto LABEL_4;
  }
  v13 = 0;
  SKCacheRemove(v11);
  if ( !*(_QWORD *)(v12 + 224) )
    goto LABEL_30;
  if ( !*(_QWORD *)(v12 + 240) || *(_DWORD *)(v12 + 568) || (v13 = RemoveKeyFromStore(v12)) == 0 )
  {
    if ( *(_QWORD *)(v12 + 256) )
    {
      v17 = *(_DWORD *)(*(_QWORD *)(v12 + 64) + 32LL);
      if ( v17 == 196609 )
      {
        v5 = 0;
        v13 = RemoveKeyFromLegacyStore(v12, 1);
        if ( v13 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v19 = 21;
LABEL_29:
            WPP_SF_D(v18[2], v19, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids, v13);
          }
        }
      }
      else if ( (unsigned int)(v17 - 196610) <= 1 )
      {
        v5 = 0;
        v13 = RemoveKeyFromLegacyStore(v12, 0);
        if ( v13 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v19 = 22;
            goto LABEL_29;
          }
        }
      }
    }
LABEL_30:
    v20 = *(_QWORD *)(v12 + 416);
    if ( v20 && (*(_BYTE *)(v20 + 4) & 4) != 0 )
    {
      v21 = DeleteEncryptedPinFile(*(_QWORD *)(v12 + 16), *(unsigned int *)(v12 + 528), *(_QWORD *)(v12 + 80));
      v13 = v21;
      if ( v21 )
      {
        DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 3289);
        goto LABEL_35;
      }
    }
    else if ( v13 )
    {
LABEL_35:
      if ( v13 != -2146893802 )
        KspCryptAuditCryptOperation(0, v7, v12, 2482, v13);
    }
    v13 = 0;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v16,
      (unsigned int)"Status",
      v13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
      168);
  if ( v13 != -2146893778 )
    goto LABEL_41;
LABEL_42:
  if ( !*(_DWORD *)(v12 + 568) )
  {
    v22 = 2 * (v5 ^ 1);
    if ( v9 )
      v23 = *(int **)(v9 + 16);
    else
      v23 = &dword_18006B48C;
    EtwLogNCryptDeleteKey((int)v23, *(_QWORD *)(v12 + 8), *(_QWORD *)(v12 + 16), a3, v22, v13);
  }
LABEL_47:
  if ( v9 )
    RtlReleaseResource(v10);
  return v13;
}

```

## disassembly

```asm
0x180003770  push    rbx
0x180003772  push    rbp
0x180003773  push    rsi
0x180003774  push    rdi
0x180003775  push    r14
0x180003777  push    r15
0x180003779  sub     rsp, 48h
0x18000377d  mov     r15d, r8d
0x180003780  mov     rbx, rdx
0x180003783  mov     esi, 1
0x180003788  call    KspValidateProvHandle
0x18000378d  mov     r14, rax
0x180003790  test    rax, rax
0x180003793  jz      loc_1800039A9
0x180003799  lea     rbp, [rax+40h]
0x18000379d  mov     dl, sil; Wait
0x1800037a0  mov     rcx, rbp; Resource
0x1800037a3  call    cs:__imp_RtlAcquireResourceShared
0x1800037aa  nop     dword ptr [rax+rax+00h]
0x1800037af  mov     rcx, rbx
0x1800037b2  call    KspValidateKeyHandle
0x1800037b7  mov     rdi, rax
0x1800037ba  test    rax, rax
0x1800037bd  jnz     short loc_1800037E7
0x1800037bf  mov     ebx, 80090026h
0x1800037c4  mov     r9d, 0C7Fh
0x1800037ca  mov     ecx, 80090026h
0x1800037cf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800037d6  lea     rdx, aStatus; "Status"
0x1800037dd  call    DebugTraceError
0x1800037e2  jmp     loc_1800039F5
0x1800037e7  test    r15d, 0FFFFFFBFh
0x1800037ee  jz      short loc_180003802
0x1800037f0  mov     ebx, 80090009h
0x1800037f5  mov     r9d, 0C86h
0x1800037fb  mov     ecx, 80090009h
0x180003800  jmp     short loc_1800037CF
0x180003802  mov     eax, [rax+1ACh]
0x180003808  test    al, 20h
0x18000380a  jz      short loc_18000381E
0x18000380c  mov     ebx, 80090010h
0x180003811  mov     r9d, 0C91h
0x180003817  mov     ecx, 80090010h
0x18000381c  jmp     short loc_1800037CF
0x18000381e  mov     rcx, rdi
0x180003821  xor     ebx, ebx
0x180003823  call    SKCacheRemove
0x180003828  cmp     [rdi+0E0h], rbx
0x18000382f  jz      loc_18000393D
0x180003835  cmp     [rdi+0F0h], rbx
0x18000383c  jz      short loc_1800038A6
0x18000383e  cmp     [rdi+238h], ebx
0x180003844  jnz     short loc_1800038A6
0x180003846  mov     rcx, rdi
0x180003849  call    RemoveKeyFromStore
0x18000384e  mov     ebx, eax
0x180003850  test    eax, eax
0x180003852  jz      short loc_1800038A6
0x180003854  mov     rcx, cs:WPP_GLOBAL_Control
0x18000385b  lea     rax, WPP_GLOBAL_Control
0x180003862  cmp     rcx, rax
0x180003865  jz      short loc_180003895
0x180003867  test    [rcx+1Ch], sil
0x18000386b  jz      short loc_180003895
0x18000386d  mov     rcx, [rcx+10h]
0x180003871  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003878  mov     [rsp+78h+var_48], 0CA8h
0x180003880  lea     r9, aStatus; "Status"
0x180003887  mov     [rsp+78h+var_50], rax
0x18000388c  mov     [rsp+78h+var_58], ebx
0x180003890  call    WPP_SF_sDsd
0x180003895  cmp     ebx, 8009002Eh
0x18000389b  jz      loc_180003A12
0x1800038a1  jmp     loc_1800039F5
0x1800038a6  cmp     qword ptr [rdi+100h], 0
0x1800038ae  jz      loc_18000393D
0x1800038b4  mov     rax, [rdi+40h]
0x1800038b8  mov     eax, [rax+20h]
0x1800038bb  cmp     eax, 30001h
0x1800038c0  jnz     short loc_1800038F3
0x1800038c2  xor     esi, esi
0x1800038c4  mov     rcx, rdi
0x1800038c7  lea     edx, [rsi+1]
0x1800038ca  call    RemoveKeyFromLegacyStore
0x1800038cf  mov     ebx, eax
0x1800038d1  test    eax, eax
0x1800038d3  jz      short loc_18000393D
0x1800038d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038dc  lea     rax, WPP_GLOBAL_Control
0x1800038e3  cmp     rcx, rax
0x1800038e6  jz      short loc_18000393D
0x1800038e8  test    byte ptr [rcx+1Ch], 2
0x1800038ec  jz      short loc_18000393D
0x1800038ee  lea     edx, [rsi+15h]
0x1800038f1  jmp     short loc_18000392A
0x1800038f3  add     eax, 0FFFCFFFEh
0x1800038f8  cmp     eax, esi
0x1800038fa  ja      short loc_18000393D
0x1800038fc  xor     edx, edx
0x1800038fe  mov     rcx, rdi
0x180003901  xor     esi, esi
0x180003903  call    RemoveKeyFromLegacyStore
0x180003908  mov     ebx, eax
0x18000390a  test    eax, eax
0x18000390c  jz      short loc_18000393D
0x18000390e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003915  lea     rax, WPP_GLOBAL_Control
0x18000391c  cmp     rcx, rax
0x18000391f  jz      short loc_18000393D
0x180003921  test    byte ptr [rcx+1Ch], 2
0x180003925  jz      short loc_18000393D
0x180003927  lea     edx, [rsi+16h]
0x18000392a  mov     rcx, [rcx+10h]
0x18000392e  lea     r8, WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids
0x180003935  mov     r9d, ebx
0x180003938  call    WPP_SF_D
0x18000393d  mov     rax, [rdi+1A0h]
0x180003944  test    rax, rax
0x180003947  jz      short loc_180003985
0x180003949  test    byte ptr [rax+4], 4
0x18000394d  jz      short loc_180003985
0x18000394f  mov     r8, [rdi+50h]
0x180003953  mov     edx, [rdi+210h]
0x180003959  mov     rcx, [rdi+10h]
0x18000395d  call    DeleteEncryptedPinFile
0x180003962  mov     ebx, eax
0x180003964  test    eax, eax
0x180003966  jz      short loc_1800039A5
0x180003968  mov     r9d, 0CD9h
0x18000396e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003975  lea     rdx, aStatus; "Status"
0x18000397c  mov     ecx, eax
0x18000397e  call    DebugTraceError
0x180003983  jmp     short loc_180003989
0x180003985  test    ebx, ebx
0x180003987  jz      short loc_1800039A5
0x180003989  cmp     ebx, 80090016h
0x18000398f  jz      short loc_1800039A5
0x180003991  mov     r9d, 9B2h
0x180003997  mov     [rsp+78h+var_58], ebx
0x18000399b  mov     r8, rdi
0x18000399e  xor     ecx, ecx
0x1800039a0  call    KspCryptAuditCryptOperation
0x1800039a5  xor     ebx, ebx
0x1800039a7  jmp     short loc_180003A12
0x1800039a9  xor     edi, edi
0x1800039ab  mov     ebx, 80090026h
0x1800039b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039b7  lea     rax, WPP_GLOBAL_Control
0x1800039be  cmp     rcx, rax
0x1800039c1  jz      short loc_1800039F5
0x1800039c3  test    [rcx+1Ch], sil
0x1800039c7  jz      short loc_1800039F5
0x1800039c9  mov     rcx, [rcx+10h]
0x1800039cd  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800039d4  mov     [rsp+78h+var_48], 0C76h
0x1800039dc  lea     r9, aStatus; "Status"
0x1800039e3  mov     [rsp+78h+var_50], rax
0x1800039e8  mov     [rsp+78h+var_58], 80090026h
0x1800039f0  call    WPP_SF_sDsd
0x1800039f5  mov     r9d, 9B2h
0x1800039fb  mov     [rsp+78h+var_58], ebx
0x1800039ff  mov     r8, rdi
0x180003a02  xor     ecx, ecx
0x180003a04  call    KspCryptAuditCryptOperation
0x180003a09  lea     rbp, [r14+40h]
0x180003a0d  test    rdi, rdi
0x180003a10  jz      short loc_180003A4A
0x180003a12  cmp     dword ptr [rdi+238h], 0
0x180003a19  jnz     short loc_180003A4A
0x180003a1b  xor     esi, 1
0x180003a1e  add     esi, esi
0x180003a20  test    r14, r14
0x180003a23  jz      short loc_180003A2B
0x180003a25  mov     rcx, [r14+10h]
0x180003a29  jmp     short loc_180003A32
0x180003a2b  lea     rcx, dword_18006B48C
0x180003a32  mov     r8, [rdi+10h]
0x180003a36  mov     r9d, r15d
0x180003a39  mov     rdx, [rdi+8]
0x180003a3d  mov     dword ptr [rsp+78h+var_50], ebx
0x180003a41  mov     [rsp+78h+var_58], esi
0x180003a45  call    EtwLogNCryptDeleteKey
0x180003a4a  test    r14, r14
0x180003a4d  jz      short loc_180003A5E
0x180003a4f  mov     rcx, rbp; Resource
0x180003a52  call    cs:__imp_RtlReleaseResource
0x180003a59  nop     dword ptr [rax+rax+00h]
0x180003a5e  mov     eax, ebx
0x180003a60  add     rsp, 48h
0x180003a64  pop     r15
0x180003a66  pop     r14
0x180003a68  pop     rdi
0x180003a69  pop     rsi
0x180003a6a  pop     rbp
0x180003a6b  pop     rbx
0x180003a6c  retn
```
