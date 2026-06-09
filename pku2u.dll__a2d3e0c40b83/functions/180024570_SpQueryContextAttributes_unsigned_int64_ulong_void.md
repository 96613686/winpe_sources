# SpQueryContextAttributes(unsigned __int64,ulong,void *)

- ea: `0x180024570`
- end: `0x1800248fa`
- name: `?SpQueryContextAttributes@@YAJ_KKPEAX@Z`
- size: `906`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001b284`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023e70`
- `0x180024570`
- `0x18002eaa8`
- `0x18002f174`
- `0x18002f964`
- `0x18002fbe4`
- `0x180043a74`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800247cc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800247cc`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18002478a`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180024871`
- `SspiCli!QuerySecurityPackageInfoW` at `0x18002478a`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180024871`
- `SspiCli!FreeContextBuffer` at `0x1800248a4`
- `SspiCli!FreeContextBuffer` at `0x1800248a4`

## string_xrefs

- `0x180024744`: `PKU2U Security Package`

## pseudocode

```c
__int64 __fastcall SpQueryContextAttributes(unsigned __int64 a1, unsigned int a2, __int64 *a3)
{
  int v6; // eax
  struct _UNICODE_STRING *v7; // r14
  SECURITY_STATUS v8; // edi
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  _OWORD *v12; // rcx
  const wchar_t *v13; // rcx
  unsigned __int8 v14; // r9
  int v15; // eax
  basessp::BaseSSP *v16; // rax
  int v17; // ecx
  void *v18; // rax
  basessp::BaseSSP *v19; // rcx
  unsigned __int64 v20; // rbx
  void *Src[2]; // [rsp+30h] [rbp-10h] BYREF
  PSecPkgInfoW ppPackageInfo; // [rsp+88h] [rbp+48h] BYREF

  Src[0] = 0;
  ppPackageInfo = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids);
  v6 = WSTReferenceUserModeContextByLsaHandle(a1, 0, (struct _WST_USERMODE_CONTEXT **)Src);
  v7 = (struct _UNICODE_STRING *)Src[0];
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids, a1, v6);
    goto LABEL_35;
  }
  if ( a2 )
  {
    switch ( a2 )
    {
      case 3u:
        v13 = (const wchar_t *)*((_QWORD *)Src[0] + 13);
        *(_OWORD *)Src = 0;
        if ( wcschr(v13, 0x40u) )
          v15 = basessp::BaseSSP::WSTDuplicateStringEx(Pku2uGlobalBaseSSP, (struct _UNICODE_STRING *)Src, v7 + 6, v14);
        else
          v15 = WSTBuildFullServiceName(v7 + 7, v7 + 6, (struct _UNICODE_STRING *)Src);
        v8 = v15;
        if ( v15 >= 0 )
        {
          v16 = Pku2uGlobalBaseSSP;
          v17 = LOWORD(Src[0]);
          *(_DWORD *)a3 = 1;
          v18 = (void *)(**((__int64 (__fastcall ***)(_QWORD))v16 + 31))((unsigned int)(v17 + 2));
          a3[1] = (__int64)v18;
          if ( v18 )
          {
            v20 = LOWORD(Src[0]);
            memcpy_0(v18, Src[1], LOWORD(Src[0]));
            v19 = (basessp::BaseSSP *)a3[1];
            *((_WORD *)v19 + (v20 >> 1)) = 0;
          }
          else
          {
            v8 = -1073741670;
          }
          basessp::BaseSSP::WSTFreeString(v19, (struct _UNICODE_STRING *)Src);
        }
        break;
      case 0xAu:
      case 0xCu:
        v10 = (**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(90);
        *a3 = v10;
        if ( !v10 )
        {
LABEL_21:
          v8 = -1073741670;
          break;
        }
        *(_QWORD *)(v10 + 16) = v10 + 32;
        *(_QWORD *)(*a3 + 24) = *(_QWORD *)(*a3 + 16) + 12LL;
        v11 = *(_QWORD *)(*a3 + 16);
        *(_QWORD *)v11 = *(_QWORD *)L"pku2u";
        *(_DWORD *)(v11 + 8) = *(_DWORD *)L"u";
        v12 = *(_OWORD **)(*a3 + 24);
        *v12 = *(_OWORD *)L"PKU2U Security Package";
        v12[1] = *(_OWORD *)L"curity Package";
        *(_OWORD *)((char *)v12 + 30) = *(_OWORD *)L"Package";
        *(_WORD *)(*a3 + 4) = 1;
        *(_WORD *)(*a3 + 6) = 31;
        *(_DWORD *)*a3 = 10555667;
        v8 = QuerySecurityPackageInfoW((LPWSTR)L"pku2u", &ppPackageInfo);
        if ( v8 >= 0 )
        {
          *(_DWORD *)(*a3 + 8) = ppPackageInfo->cbMaxToken;
          if ( a2 == 12 )
            *((_DWORD *)a3 + 2) = 0;
        }
        break;
      case 0x11u:
        if ( !a3 )
        {
          v8 = -1073741811;
          break;
        }
        a3[1] = 0;
        if ( !v7[8].Buffer )
        {
          *(_DWORD *)a3 = 0;
          v8 = 0;
          break;
        }
        v9 = (void *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))(*(unsigned int *)&v7[9].Length);
        a3[1] = (__int64)v9;
        if ( v9 )
        {
          memcpy_0(v9, v7[8].Buffer, *(unsigned int *)&v7[9].Length);
          *(_DWORD *)a3 = *(_DWORD *)&v7[9].Length;
          break;
        }
        goto LABEL_21;
      default:
        v8 = WSTQueryContextAttributes((struct _WST_USERMODE_CONTEXT *)Src[0], a2, a3);
        break;
    }
  }
  else
  {
    v8 = QuerySecurityPackageInfoW((LPWSTR)L"pku2u", &ppPackageInfo);
    if ( v8 >= 0 )
    {
      *(_DWORD *)a3 = ppPackageInfo->cbMaxToken;
      *((_DWORD *)a3 + 1) = 28;
      *((_DWORD *)a3 + 2) = 1;
      *((_DWORD *)a3 + 3) = 76;
    }
  }
LABEL_35:
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  if ( v7 )
    WSTDereferenceUserModeContext((struct _WST_USERMODE_CONTEXT *)v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024570  mov     [rsp-28h+arg_0], rbx
0x180024575  mov     [rsp-28h+arg_8], rsi
0x18002457a  push    rbp
0x18002457b  push    rdi
0x18002457c  push    r13
0x18002457e  push    r14
0x180024580  push    r15
0x180024582  mov     rbp, rsp
0x180024585  sub     rsp, 40h
0x180024589  mov     rsi, r8
0x18002458c  mov     [rbp+Src], 0
0x180024594  mov     ebx, edx
0x180024596  mov     [rbp+ppPackageInfo], 0
0x18002459e  mov     r15, rcx
0x1800245a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245a8  lea     r13, WPP_GLOBAL_Control
0x1800245af  cmp     rcx, r13
0x1800245b2  jz      short loc_1800245CF
0x1800245b4  test    byte ptr [rcx+1Ch], 8
0x1800245b8  jz      short loc_1800245CF
0x1800245ba  mov     rcx, [rcx+10h]
0x1800245be  lea     r8, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids
0x1800245c5  mov     edx, 22h ; '"'
0x1800245ca  call    WPP_SF_
0x1800245cf  lea     r8, [rbp+Src]; struct _WST_USERMODE_CONTEXT **
0x1800245d3  xor     edx, edx; unsigned __int8
0x1800245d5  mov     rcx, r15; unsigned __int64
0x1800245d8  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_WST_USERMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_WST_USERMODE_CONTEXT * *)
0x1800245dd  mov     r14, [rbp+Src]
0x1800245e1  mov     edi, eax
0x1800245e3  test    eax, eax
0x1800245e5  jns     short loc_180024626
0x1800245e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245ee  cmp     rcx, r13
0x1800245f1  jz      loc_18002489B
0x1800245f7  mov     edx, 1
0x1800245fc  test    [rcx+1Ch], dl
0x1800245ff  jz      loc_18002489B
0x180024605  mov     rcx, [rcx+10h]
0x180024609  lea     r8, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids
0x180024610  mov     edx, 23h ; '#'
0x180024615  mov     [rsp+40h+var_20], eax
0x180024619  mov     r9, r15
0x18002461c  call    WPP_SF_qD
0x180024621  jmp     loc_18002489B
0x180024626  test    ebx, ebx
0x180024628  jz      loc_180024866
0x18002462e  cmp     ebx, 3
0x180024631  jz      loc_1800247BC
0x180024637  cmp     ebx, 0Ah
0x18002463a  jz      loc_1800246DA
0x180024640  cmp     ebx, 0Ch
0x180024643  jz      loc_1800246DA
0x180024649  cmp     ebx, 11h
0x18002464c  jz      short loc_180024662
0x18002464e  mov     r8, rsi; void *
0x180024651  mov     edx, ebx; unsigned int
0x180024653  mov     rcx, r14; struct _WST_USERMODE_CONTEXT *
0x180024656  call    ?WSTQueryContextAttributes@@YAJPEAU_WST_USERMODE_CONTEXT@@KPEAX@Z; WSTQueryContextAttributes(_WST_USERMODE_CONTEXT *,ulong,void *)
0x18002465b  mov     edi, eax
0x18002465d  jmp     loc_18002489B
0x180024662  test    rsi, rsi
0x180024665  jnz     short loc_180024671
0x180024667  mov     edi, 0C000000Dh
0x18002466c  jmp     loc_18002489B
0x180024671  mov     qword ptr [rsi+8], 0
0x180024679  cmp     qword ptr [r14+88h], 0
0x180024681  jnz     short loc_180024690
0x180024683  mov     dword ptr [rsi], 0
0x180024689  xor     edi, edi
0x18002468b  jmp     loc_18002489B
0x180024690  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180024697  mov     rcx, [rax+0F8h]
0x18002469e  mov     rax, [rcx]
0x1800246a1  mov     ecx, [r14+90h]
0x1800246a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246ad  mov     [rsi+8], rax
0x1800246b1  test    rax, rax
0x1800246b4  jz      short loc_180024700
0x1800246b6  mov     r8d, [r14+90h]; Size
0x1800246bd  mov     rcx, rax; void *
0x1800246c0  mov     rdx, [r14+88h]; Src
0x1800246c7  call    memcpy_0
0x1800246cc  mov     eax, [r14+90h]
0x1800246d3  mov     [rsi], eax
0x1800246d5  jmp     loc_18002489B
0x1800246da  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x1800246e1  mov     rcx, [rax+0F8h]
0x1800246e8  mov     rax, [rcx]
0x1800246eb  mov     ecx, 5Ah ; 'Z'
0x1800246f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246f5  mov     [rsi], rax
0x1800246f8  mov     rcx, rax
0x1800246fb  test    rax, rax
0x1800246fe  jnz     short loc_18002470A
0x180024700  mov     edi, 0C000009Ah
0x180024705  jmp     loc_18002489B
0x18002470a  add     rax, 20h ; ' '
0x18002470e  lea     rdx, [rbp+ppPackageInfo]; ppPackageInfo
0x180024712  mov     [rcx+10h], rax
0x180024716  mov     rcx, [rsi]
0x180024719  mov     rax, [rcx+10h]
0x18002471d  add     rax, 0Ch
0x180024721  mov     [rcx+18h], rax
0x180024725  mov     rax, [rsi]
0x180024728  movsd   xmm0, qword ptr cs:pszPackageName; "pku2u"
0x180024730  mov     rcx, [rax+10h]
0x180024734  movsd   qword ptr [rcx], xmm0
0x180024738  mov     eax, dword ptr cs:pszPackageName+8; "u"
0x18002473e  mov     [rcx+8], eax
0x180024741  mov     rax, [rsi]
0x180024744  movups  xmm0, xmmword ptr cs:aPku2uSecurityP; "PKU2U Security Package"
0x18002474b  mov     rcx, [rax+18h]
0x18002474f  movups  xmmword ptr [rcx], xmm0
0x180024752  movups  xmm1, xmmword ptr cs:aPku2uSecurityP+10h; "curity Package"
0x180024759  movups  xmmword ptr [rcx+10h], xmm1
0x18002475d  movups  xmm0, xmmword ptr cs:aPku2uSecurityP+1Eh; "Package"
0x180024764  movups  xmmword ptr [rcx+1Eh], xmm0
0x180024768  mov     rax, [rsi]
0x18002476b  lea     rcx, pszPackageName; "pku2u"
0x180024772  mov     word ptr [rax+4], 1
0x180024778  mov     rax, [rsi]
0x18002477b  mov     word ptr [rax+6], 1Fh
0x180024781  mov     rax, [rsi]
0x180024784  mov     dword ptr [rax], 0A11113h
0x18002478a  call    cs:__imp_QuerySecurityPackageInfoW
0x180024790  mov     edi, eax
0x180024792  test    eax, eax
0x180024794  js      loc_18002489B
0x18002479a  mov     rax, [rbp+ppPackageInfo]
0x18002479e  mov     rdx, [rsi]
0x1800247a1  mov     ecx, [rax+8]
0x1800247a4  mov     [rdx+8], ecx
0x1800247a7  cmp     ebx, 0Ch
0x1800247aa  jnz     loc_18002489B
0x1800247b0  mov     dword ptr [rsi+8], 0
0x1800247b7  jmp     loc_18002489B
0x1800247bc  mov     rcx, [r14+68h]; Str
0x1800247c0  xorps   xmm0, xmm0
0x1800247c3  mov     edx, 40h ; '@'; Ch
0x1800247c8  movups  xmmword ptr [rbp+Src], xmm0
0x1800247cc  call    cs:__imp_wcschr
0x1800247d2  test    rax, rax
0x1800247d5  jz      short loc_1800247ED
0x1800247d7  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x1800247de  lea     r8, [r14+60h]; struct _UNICODE_STRING *
0x1800247e2  lea     rdx, [rbp+Src]; struct _UNICODE_STRING *
0x1800247e6  call    ?WSTDuplicateStringEx@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@0E@Z; basessp::BaseSSP::WSTDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x1800247eb  jmp     short loc_1800247FE
0x1800247ed  lea     rcx, [r14+70h]; struct _UNICODE_STRING *
0x1800247f1  lea     r8, [rbp+Src]; struct _UNICODE_STRING *
0x1800247f5  lea     rdx, [r14+60h]; struct _UNICODE_STRING *
0x1800247f9  call    ?WSTBuildFullServiceName@@YAJPEAU_UNICODE_STRING@@00@Z; WSTBuildFullServiceName(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1800247fe  mov     edi, eax
0x180024800  test    eax, eax
0x180024802  js      loc_18002489B
0x180024808  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18002480f  movzx   ecx, word ptr [rbp+Src]
0x180024813  mov     dword ptr [rsi], 1
0x180024819  add     ecx, 2
0x18002481c  mov     rax, [rax+0F8h]
0x180024823  mov     rax, [rax]
0x180024826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002482b  mov     [rsi+8], rax
0x18002482f  test    rax, rax
0x180024832  jz      short loc_180024856
0x180024834  movzx   ebx, word ptr [rbp+Src]
0x180024838  mov     rcx, rax; void *
0x18002483b  mov     rdx, [rbp+Src+8]; Src
0x18002483f  mov     r8d, ebx; Size
0x180024842  call    memcpy_0
0x180024847  mov     rcx, [rsi+8]
0x18002484b  shr     rbx, 1
0x18002484e  xor     eax, eax
0x180024850  mov     [rcx+rbx*2], ax
0x180024854  jmp     short loc_18002485B
0x180024856  mov     edi, 0C000009Ah
0x18002485b  lea     rdx, [rbp+Src]; struct _UNICODE_STRING *
0x18002485f  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x180024864  jmp     short loc_18002489B
0x180024866  lea     rdx, [rbp+ppPackageInfo]; ppPackageInfo
0x18002486a  lea     rcx, pszPackageName; "pku2u"
0x180024871  call    cs:__imp_QuerySecurityPackageInfoW
0x180024877  mov     edi, eax
0x180024879  test    eax, eax
0x18002487b  js      short loc_18002489B
0x18002487d  mov     rax, [rbp+ppPackageInfo]
0x180024881  mov     ecx, [rax+8]
0x180024884  mov     [rsi], ecx
0x180024886  mov     dword ptr [rsi+4], 1Ch
0x18002488d  mov     dword ptr [rsi+8], 1
0x180024894  mov     dword ptr [rsi+0Ch], 4Ch ; 'L'
0x18002489b  mov     rcx, [rbp+ppPackageInfo]; pvContextBuffer
0x18002489f  test    rcx, rcx
0x1800248a2  jz      short loc_1800248AA
0x1800248a4  call    cs:__imp_FreeContextBuffer
0x1800248aa  test    r14, r14
0x1800248ad  jz      short loc_1800248B7
0x1800248af  mov     rcx, r14; struct _WST_USERMODE_CONTEXT *
0x1800248b2  call    ?WSTDereferenceUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_WST_USERMODE_CONTEXT *)
0x1800248b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248be  cmp     rcx, r13
0x1800248c1  jz      short loc_1800248E1
0x1800248c3  test    byte ptr [rcx+1Ch], 8
0x1800248c7  jz      short loc_1800248E1
0x1800248c9  mov     rcx, [rcx+10h]
0x1800248cd  lea     r8, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids
0x1800248d4  mov     edx, 24h ; '$'
0x1800248d9  mov     r9d, edi
0x1800248dc  call    WPP_SF_d
0x1800248e1  mov     rbx, [rsp+40h+arg_0]
0x1800248e6  mov     eax, edi
0x1800248e8  mov     rsi, [rsp+40h+arg_8]
0x1800248ed  add     rsp, 40h
0x1800248f1  pop     r15
0x1800248f3  pop     r14
0x1800248f5  pop     r13
0x1800248f7  pop     rdi
0x1800248f8  pop     rbp
0x1800248f9  retn
```
