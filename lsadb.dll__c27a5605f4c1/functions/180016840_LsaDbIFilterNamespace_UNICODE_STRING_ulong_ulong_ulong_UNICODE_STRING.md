# LsaDbIFilterNamespace(_UNICODE_STRING *,ulong,ulong,ulong,_UNICODE_STRING *)

- ea: `0x180016840`
- end: `0x1800169fe`
- name: `?LsaDbIFilterNamespace@@YAJPEAU_UNICODE_STRING@@KKK0@Z`
- size: `446`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000c0e0`
- `0x18000fd40`
- `0x18000fee8`
- `0x180016840`
- `0x180016c08`
- `0x180026674`

## import_xrefs

- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x1800168c8`
- `LSASRV!LsaIFree_LSAPR_UNICODE_STRING_BUFFER` at `0x1800168c8`
- `LSASRV!LsapCompareDomainNames` at `0x1800168b5`
- `LSASRV!LsapCompareDomainNames` at `0x1800168e0`
- `LSASRV!LsapCompareDomainNames` at `0x1800168b5`
- `LSASRV!LsapCompareDomainNames` at `0x1800168e0`

## pseudocode

```c
__int64 __fastcall LsaDbIFilterNamespace(
        struct _UNICODE_STRING *a1,
        char a2,
        unsigned int a3,
        char a4,
        struct _UNICODE_STRING *a5)
{
  int v6; // edi
  int Match; // ebx
  char v8; // bl
  const __int64 *v9; // rdx
  const wchar_t *v10; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int8 v14; // al
  __int64 v15; // r8
  _OWORD v16[3]; // [rsp+40h] [rbp-38h] BYREF

  if ( a3 && (a2 & 2) != 0 )
  {
    if ( (a4 & 0x20) != 0 )
    {
      v6 = 1;
LABEL_10:
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v9 = &qword_18003DFF8;
        v10 = L"ed";
        if ( !v6 )
        {
          v10 = (const wchar_t *)&qword_18003DFF8;
          v9 = (const __int64 *)L"did not ";
        }
        WPP_SF_ZSSZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v9, (__int64)v10, (__int64)a1);
      }
      return v6 == 0 ? 0xC000019B : 0;
    }
    v6 = 0;
    if ( (a4 & 8) != 0 )
    {
      v16[0] = 0;
      Match = LsaDbpForestTrustFindMatch(4, a5, 0, v16, 0);
      if ( Match >= 0 )
      {
        v8 = LsapCompareDomainNames(a1, v16, 0);
        LOBYTE(v6) = v8 != 0;
        LsaIFree_LSAPR_UNICODE_STRING_BUFFER(v16);
        if ( v8 )
          goto LABEL_10;
LABEL_8:
        if ( (unsigned __int8)LsapCompareDomainNames(a5, a1, 0) )
          v6 = 1;
        goto LABEL_10;
      }
      if ( Match == -1073741198 )
        goto LABEL_8;
      v12 = WPP_GLOBAL_Control;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v13 = 11;
LABEL_18:
        WPP_SF_d(v12[2], v13, &WPP_f02fe0205ee33f4fbd24496f6b8a625c_Traceguids, (unsigned int)Match);
      }
    }
    else
    {
      v14 = LsaDbpNoMoreWin2KForest();
      LOBYTE(v15) = 1;
      Match = LsaDbpForestTrustFindMatch(v14 != 0 ? 1 : 4, a1, v15, 0, 0);
      if ( Match >= 0 )
      {
        v6 = 1;
        goto LABEL_10;
      }
      if ( Match == -1073741198 )
        goto LABEL_8;
      v12 = WPP_GLOBAL_Control;
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v13 = 12;
        goto LABEL_18;
      }
    }
    return (unsigned int)Match;
  }
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f02fe0205ee33f4fbd24496f6b8a625c_Traceguids, a3, a2);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180016840  push    rbx
0x180016842  push    rbp
0x180016843  push    rsi
0x180016844  push    rdi
0x180016845  sub     rsp, 58h
0x180016849  mov     eax, edx
0x18001684b  mov     rbp, rcx
0x18001684e  test    r8d, r8d
0x180016851  jz      loc_1800169C7
0x180016857  test    al, 2
0x180016859  jz      loc_1800169C7
0x18001685f  test    r9b, 20h
0x180016863  jz      short loc_18001686C
0x180016865  mov     edi, 1
0x18001686a  jmp     short loc_1800168EB
0x18001686c  xor     edi, edi
0x18001686e  lea     esi, [rdi+1]
0x180016871  test    r9b, 8
0x180016875  jz      loc_180016978
0x18001687b  mov     rdx, [rsp+78h+arg_20]
0x180016883  lea     r9, [rsp+78h+var_38]
0x180016888  xorps   xmm0, xmm0
0x18001688b  mov     [rsp+78h+var_58], rdi
0x180016890  xor     r8d, r8d
0x180016893  lea     ecx, [rdi+4]
0x180016896  movups  [rsp+78h+var_38], xmm0
0x18001689b  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x1800168a0  mov     ebx, eax
0x1800168a2  test    eax, eax
0x1800168a4  js      loc_180016947
0x1800168aa  xor     r8d, r8d
0x1800168ad  lea     rdx, [rsp+78h+var_38]
0x1800168b2  mov     rcx, rbp
0x1800168b5  call    cs:__imp_LsapCompareDomainNames
0x1800168bb  test    al, al
0x1800168bd  lea     rcx, [rsp+78h+var_38]
0x1800168c2  mov     bl, al
0x1800168c4  setnz   dil
0x1800168c8  call    cs:__imp_LsaIFree_LSAPR_UNICODE_STRING_BUFFER
0x1800168ce  test    bl, bl
0x1800168d0  jnz     short loc_1800168EB
0x1800168d2  mov     rcx, [rsp+78h+arg_20]
0x1800168da  xor     r8d, r8d
0x1800168dd  mov     rdx, rbp
0x1800168e0  call    cs:__imp_LsapCompareDomainNames
0x1800168e6  test    al, al
0x1800168e8  cmovnz  edi, esi
0x1800168eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168f2  test    byte ptr [rcx+1Ch], 80h
0x1800168f6  jz      short loc_180016937
0x1800168f8  mov     r9, [rsp+78h+arg_20]
0x180016900  lea     rdx, qword_18003DFF8
0x180016907  mov     rcx, [rcx+10h]; LoggerHandle
0x18001690b  lea     r8, aDidNot; "did not "
0x180016912  test    edi, edi
0x180016914  mov     [rsp+78h+var_48], rbp; __int64
0x180016919  lea     rax, aEd; "ed"
0x180016920  cmovz   rax, rdx
0x180016924  cmovz   rdx, r8
0x180016928  mov     [rsp+78h+var_50], rax; __int64
0x18001692d  mov     [rsp+78h+var_58], rdx; __int64
0x180016932  call    WPP_SF_ZSSZ
0x180016937  neg     edi
0x180016939  sbb     eax, eax
0x18001693b  not     eax
0x18001693d  and     eax, 0C000019Bh
0x180016942  jmp     loc_1800169F5
0x180016947  cmp     ebx, 0C0000272h
0x18001694d  jz      short loc_1800168D2
0x18001694f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016956  test    byte ptr [rcx+1Ch], 80h
0x18001695a  jz      short loc_180016974
0x18001695c  mov     edx, 0Bh
0x180016961  mov     rcx, [rcx+10h]
0x180016965  lea     r8, WPP_f02fe0205ee33f4fbd24496f6b8a625c_Traceguids
0x18001696c  mov     r9d, ebx
0x18001696f  call    WPP_SF_d
0x180016974  mov     eax, ebx
0x180016976  jmp     short loc_1800169F5
0x180016978  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x18001697d  neg     al
0x18001697f  mov     [rsp+78h+var_58], rdi
0x180016984  mov     r8b, sil
0x180016987  mov     rdx, rbp
0x18001698a  sbb     ecx, ecx
0x18001698c  xor     r9d, r9d
0x18001698f  and     ecx, 0FFFFFFFDh
0x180016992  add     ecx, 4
0x180016995  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x18001699a  mov     ebx, eax
0x18001699c  test    eax, eax
0x18001699e  js      short loc_1800169A7
0x1800169a0  mov     edi, esi
0x1800169a2  jmp     loc_1800168EB
0x1800169a7  cmp     ebx, 0C0000272h
0x1800169ad  jz      loc_1800168D2
0x1800169b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169ba  test    byte ptr [rcx+1Ch], 80h
0x1800169be  jz      short loc_180016974
0x1800169c0  mov     edx, 0Ch
0x1800169c5  jmp     short loc_180016961
0x1800169c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169ce  test    byte ptr [rcx+1Ch], 80h
0x1800169d2  jz      short loc_1800169F0
0x1800169d4  mov     rcx, [rcx+10h]
0x1800169d8  mov     r9d, r8d
0x1800169db  lea     r8, WPP_f02fe0205ee33f4fbd24496f6b8a625c_Traceguids
0x1800169e2  mov     dword ptr [rsp+78h+var_58], eax
0x1800169e6  mov     edx, 0Ah
0x1800169eb  call    WPP_SF_dd
0x1800169f0  mov     eax, 0C000000Dh
0x1800169f5  add     rsp, 58h
0x1800169f9  pop     rdi
0x1800169fa  pop     rsi
0x1800169fb  pop     rbp
0x1800169fc  pop     rbx
0x1800169fd  retn
```
