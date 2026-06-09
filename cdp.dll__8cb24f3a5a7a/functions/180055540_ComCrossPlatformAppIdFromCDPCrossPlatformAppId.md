# ComCrossPlatformAppIdFromCDPCrossPlatformAppId

- ea: `0x180055540`
- end: `0x1800557d4`
- name: `ComCrossPlatformAppIdFromCDPCrossPlatformAppId`
- size: `660`
- prototype: ``
- caller_count: `13`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053e40`
- `0x180054390`
- `0x180055bf0`
- `0x18015b0d0`
- `0x18015c840`
- `0x18015d710`
- `0x18015d9e0`
- `0x18015dca0`
- `0x18015e030`
- `0x1802ff7b0`
- `0x1802ff9d0`
- `0x1802ffe00`
- `0x180300360`

## callees

- `0x180013da0`
- `0x180017cdc`
- `0x180054ba4`
- `0x180055540`
- `0x1800e8518`
- `0x180149448`
- `0x1801f7974`
- `0x180354010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800556a8`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18005573f`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800556a8`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18005573f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005568d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800556e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005568d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800556e6`

## string_xrefs

- `0x1800556fb`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180055766`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18005578d`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800557a2`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
__int64 __fastcall ComCrossPlatformAppIdFromCDPCrossPlatformAppId(__int64 *a1, _OWORD *a2)
{
  __int64 v4; // rax
  unsigned int v5; // r12d
  void *v6; // rax
  int v7; // ebx
  unsigned int i; // edi
  std::_Ref_count_base *v9; // rcx
  int v11; // eax
  __int64 v12; // rax
  const char *v13; // r14
  __int64 v14; // rcx
  rsize_t v15; // r15
  char *v16; // rax
  char *v17; // rbx
  __int64 v18; // rax
  const char *v19; // r14
  __int64 v20; // rcx
  rsize_t v21; // r15
  char *v22; // rax
  char *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  std::_Ref_count_base *v28[2]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v29; // [rsp+30h] [rbp-20h] BYREF
  __int128 v30; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  char v32; // [rsp+88h] [rbp+38h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    if ( !a1 )
      return 0;
    v4 = *a1;
    v30 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *))(v4 + 56))(a1);
    LODWORD(v30) = v5;
    v6 = CoTaskMemAlloc(16LL * v5);
    *((_QWORD *)&v30 + 1) = v6;
    if ( v6 )
    {
      *(_OWORD *)v28 = 0;
      memset_0(v6, 0, 16LL * v5);
      *(_QWORD *)&v29 = 0;
      *((_QWORD *)&v29 + 1) = v28;
      v7 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*a1 + 40))(a1, &v29);
      cdp::detail::address_of<ICDPCrossPlatformAppIdEnumerator>::~address_of<ICDPCrossPlatformAppIdEnumerator>(&v29);
      if ( v7 >= 0 )
      {
        for ( i = 0; i < v5; ++i )
        {
          v11 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, char *))(*(_QWORD *)v28[0] + 24LL))(v28[0], &v32);
          v7 = v11;
          if ( v11 < 0 )
          {
            v26 = (unsigned int)v11;
            v27 = 122;
            goto LABEL_31;
          }
          if ( !v32 )
            break;
          v29 = 0;
          v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v28[0] + 48LL))(v28[0]);
          *((_QWORD *)&v29 + 1) = 0;
          v13 = (const char *)v12;
          if ( v12 )
          {
            v14 = -1;
            do
              ++v14;
            while ( *(_BYTE *)(v12 + v14) );
            v15 = v14 + 1;
            v16 = (char *)CoTaskMemAlloc(v14 + 1);
            v17 = v16;
            if ( !v16 )
            {
              v24 = 116;
              goto LABEL_22;
            }
            strcpy_s(v16, v15, v13);
            *((_QWORD *)&v29 + 1) = v17;
          }
          v18 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v28[0] + 40LL))(v28[0]);
          *(_QWORD *)&v29 = 0;
          v19 = (const char *)v18;
          if ( v18 )
          {
            v20 = -1;
            do
              ++v20;
            while ( *(_BYTE *)(v18 + v20) );
            v21 = v20 + 1;
            v22 = (char *)CoTaskMemAlloc(v20 + 1);
            v23 = v22;
            if ( !v22 )
            {
              v24 = 117;
LABEL_22:
              v7 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v24,
                (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
                (const char *)0x8007000ELL,
                (int)v28[0]);
              FreeCDPComCrossPlatformAppIdEntry(&v29);
              goto LABEL_23;
            }
            strcpy_s(v22, v21, v19);
            *(_QWORD *)&v29 = v23;
          }
          v25 = 2LL * i;
          *(_OWORD *)(*((_QWORD *)&v30 + 1) + 8 * v25) = v29;
        }
        v9 = v28[1];
        *a2 = v30;
        if ( v9 )
          std::_Ref_count_base::_Decref(v9);
        return 0;
      }
      v26 = (unsigned int)v7;
      v27 = 103;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)v26,
        (int)v28[0]);
LABEL_23:
      if ( v28[1] )
        std::_Ref_count_base::_Decref(v28[1]);
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)0x8007000ELL,
        (int)v28[0]);
    }
    FreeCDPComCrossPlatformAppId(&v30);
  }
  else
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      (int)v28[0]);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180055540  mov     [rsp-28h+arg_0], rbx
0x180055545  mov     [rsp-28h+arg_10], rsi
0x18005554a  push    rbp
0x18005554b  push    rdi
0x18005554c  push    r12
0x18005554e  push    r14
0x180055550  push    r15
0x180055552  mov     rbp, rsp
0x180055555  sub     rsp, 50h
0x180055559  mov     rsi, rdx
0x18005555c  mov     rbx, rcx
0x18005555f  test    rdx, rdx
0x180055562  jz      loc_180055762
0x180055568  xorps   xmm0, xmm0
0x18005556b  movdqu  xmmword ptr [rdx], xmm0
0x18005556f  test    rcx, rcx
0x180055572  jz      loc_180055613
0x180055578  mov     rax, [rcx]
0x18005557b  movups  [rbp+var_10], xmm0
0x18005557f  mov     rax, [rax+38h]
0x180055583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055588  mov     edi, eax
0x18005558a  mov     r12d, eax
0x18005558d  shl     rdi, 4
0x180055591  mov     rcx, rdi; cb
0x180055594  mov     dword ptr [rbp+var_10], r12d
0x180055598  call    cs:__imp_CoTaskMemAlloc
0x18005559e  mov     qword ptr [rbp+var_10+8], rax
0x1800555a2  test    rax, rax
0x1800555a5  jz      loc_18005579E
0x1800555ab  xorps   xmm0, xmm0
0x1800555ae  mov     r8, rdi; Size
0x1800555b1  xor     edx, edx; Val
0x1800555b3  mov     rcx, rax; void *
0x1800555b6  movdqu  xmmword ptr [rbp+var_30], xmm0
0x1800555bb  call    memset_0
0x1800555c0  lea     rax, [rbp+var_30]
0x1800555c4  mov     qword ptr [rbp+var_20], 0
0x1800555cc  mov     qword ptr [rbp+var_20+8], rax
0x1800555d0  lea     rdx, [rbp+var_20]
0x1800555d4  mov     rax, [rbx]
0x1800555d7  mov     rcx, rbx
0x1800555da  mov     rax, [rax+28h]
0x1800555de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555e3  lea     rcx, [rbp+var_20]
0x1800555e7  mov     ebx, eax
0x1800555e9  call    ??1?$address_of@VICDPCrossPlatformAppIdEnumerator@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppIdEnumerator>::~address_of<ICDPCrossPlatformAppIdEnumerator>(void)
0x1800555ee  test    ebx, ebx
0x1800555f0  js      loc_180055781
0x1800555f6  xor     edi, edi
0x1800555f8  cmp     edi, r12d
0x1800555fb  jb      short loc_18005562E
0x1800555fd  movups  xmm0, [rbp+var_10]
0x180055601  mov     rcx, [rbp+var_30+8]; this
0x180055605  movdqu  xmmword ptr [rsi], xmm0
0x180055609  test    rcx, rcx
0x18005560c  jz      short loc_180055613
0x18005560e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055613  xor     eax, eax
0x180055615  lea     r11, [rsp+50h+var_s0]
0x18005561a  mov     rbx, [r11+30h]
0x18005561e  mov     rsi, [r11+40h]
0x180055622  mov     rsp, r11
0x180055625  pop     r15
0x180055627  pop     r14
0x180055629  pop     r12
0x18005562b  pop     rdi
0x18005562c  pop     rbp
0x18005562d  retn
0x18005562e  mov     rcx, [rbp+var_30]
0x180055632  lea     rdx, [rbp+arg_8]
0x180055636  mov     rax, [rcx]
0x180055639  mov     rax, [rax+18h]
0x18005563d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055642  mov     ebx, eax
0x180055644  test    eax, eax
0x180055646  js      loc_1800557CA
0x18005564c  cmp     [rbp+arg_8], 0
0x180055650  jz      short loc_1800555FD
0x180055652  mov     rcx, [rbp+var_30]
0x180055656  xorps   xmm0, xmm0
0x180055659  movups  [rbp+var_20], xmm0
0x18005565d  mov     rax, [rcx]
0x180055660  mov     rax, [rax+30h]
0x180055664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055669  mov     qword ptr [rbp+var_20+8], 0
0x180055671  mov     r14, rax
0x180055674  test    rax, rax
0x180055677  jz      short loc_1800556B2
0x180055679  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005567d  inc     rcx
0x180055680  cmp     byte ptr [rax+rcx], 0
0x180055684  jnz     short loc_18005567D
0x180055686  lea     r15, [rcx+1]
0x18005568a  mov     rcx, r15; cb
0x18005568d  call    cs:__imp_CoTaskMemAlloc
0x180055693  mov     rbx, rax
0x180055696  test    rax, rax
0x180055699  jz      loc_1800557C0
0x18005569f  mov     r8, r14; Source
0x1800556a2  mov     rdx, r15; SizeInBytes
0x1800556a5  mov     rcx, rax; Destination
0x1800556a8  call    cs:__imp_strcpy_s
0x1800556ae  mov     qword ptr [rbp+var_20+8], rbx
0x1800556b2  mov     rcx, [rbp+var_30]
0x1800556b6  mov     rax, [rcx]
0x1800556b9  mov     rax, [rax+28h]
0x1800556bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556c2  mov     qword ptr [rbp+var_20], 0
0x1800556ca  mov     r14, rax
0x1800556cd  test    rax, rax
0x1800556d0  jz      short loc_180055749
0x1800556d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800556d6  inc     rcx
0x1800556d9  cmp     byte ptr [rax+rcx], 0
0x1800556dd  jnz     short loc_1800556D6
0x1800556df  lea     r15, [rcx+1]
0x1800556e3  mov     rcx, r15; cb
0x1800556e6  call    cs:__imp_CoTaskMemAlloc
0x1800556ec  mov     rbx, rax
0x1800556ef  test    rax, rax
0x1800556f2  jnz     short loc_180055736
0x1800556f4  lea     edx, [rax+75h]; void *
0x1800556f7  mov     rcx, [rbp+28h]; this
0x1800556fb  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180055702  mov     ebx, 8007000Eh
0x180055707  mov     r9d, ebx; char *
0x18005570a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005570f  lea     rcx, [rbp+var_20]
0x180055713  call    FreeCDPComCrossPlatformAppIdEntry
0x180055718  mov     rcx, [rbp+var_30+8]; this
0x18005571c  test    rcx, rcx
0x18005571f  jz      short loc_180055726
0x180055721  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055726  lea     rcx, [rbp+var_10]
0x18005572a  call    FreeCDPComCrossPlatformAppId
0x18005572f  mov     eax, ebx
0x180055731  jmp     loc_180055615
0x180055736  mov     r8, r14; Source
0x180055739  mov     rdx, r15; SizeInBytes
0x18005573c  mov     rcx, rbx; Destination
0x18005573f  call    cs:__imp_strcpy_s
0x180055745  mov     qword ptr [rbp+var_20], rbx
0x180055749  mov     rax, qword ptr [rbp+var_10+8]
0x18005574d  movups  xmm0, [rbp+var_20]
0x180055751  mov     ecx, edi
0x180055753  add     rcx, rcx
0x180055756  inc     edi
0x180055758  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18005575d  jmp     loc_1800555F8
0x180055762  mov     rcx, [rbp+28h]; this
0x180055766  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18005576d  mov     ebx, 80004003h
0x180055772  mov     edx, 55h ; 'U'; void *
0x180055777  mov     r9d, ebx; char *
0x18005577a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005577f  jmp     short loc_18005572F
0x180055781  mov     r9d, ebx; char *
0x180055784  mov     edx, 67h ; 'g'; void *
0x180055789  mov     rcx, [rbp+28h]; this
0x18005578d  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180055794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055799  jmp     loc_180055718
0x18005579e  mov     rcx, [rbp+28h]; this
0x1800557a2  lea     r8, aOnecoreuapWind_40; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800557a9  mov     ebx, 8007000Eh
0x1800557ae  mov     edx, 63h ; 'c'; void *
0x1800557b3  mov     r9d, ebx; char *
0x1800557b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557bb  jmp     loc_180055726
0x1800557c0  mov     edx, 74h ; 't'
0x1800557c5  jmp     loc_1800556F7
0x1800557ca  mov     r9d, eax
0x1800557cd  mov     edx, 7Ah ; 'z'
0x1800557d2  jmp     short loc_180055789
```
