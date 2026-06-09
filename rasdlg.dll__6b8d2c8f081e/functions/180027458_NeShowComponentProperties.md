# NeShowComponentProperties

- ea: `0x180027458`
- end: `0x180027973`
- name: `NeShowComponentProperties`
- size: `1307`
- prototype: `__int64 __fastcall(struct _PEINFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x180001264`
- `0x18001b048`
- `0x180027458`
- `0x18002797c`
- `0x18002c03c`
- `0x18003bea0`
- `0x18003c860`
- `0x180040ef8`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027563`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800274ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002751a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800274ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002751a`
- `USER32!PostMessageW` at `0x180027548`
- `USER32!PostMessageW` at `0x180027548`

## pseudocode

```c
void __fastcall NeShowComponentProperties(struct _PEINFO *a1)
{
  HWND v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rbx
  CRasConnectionUiIpInfo *v5; // r9
  CRasConnectionUiIpInfo *v6; // rax
  CRasConnectionUiIpInfo *v7; // rax
  int (__fastcall **v8)(__int64, GUID *, __int64 *); // rax
  __int64 v9; // rbx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  _WORD *v18; // rax
  bool v19; // zf
  int v20; // eax
  PCNZWCH lpString2; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+60h] [rbp-A0h]
  unsigned int v26; // [rsp+64h] [rbp-9Ch]
  wchar_t pszSrc[16]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v28[16]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v29[16]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t v30[16]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t v31[16]; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t v32[256]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t v33[66]; // [rsp+308h] [rbp+208h] BYREF
  int v34; // [rsp+38Ch] [rbp+28Ch]
  wchar_t v35[65]; // [rsp+390h] [rbp+290h] BYREF
  wchar_t v36[65]; // [rsp+412h] [rbp+312h] BYREF
  int v37; // [rsp+494h] [rbp+394h]
  int v38; // [rsp+498h] [rbp+398h]

  v2 = (HWND)*((_QWORD *)a1 + 67);
  lpString2 = 0;
  v3 = PComponentFromCurSel(v2);
  v4 = v3;
  if ( !v3 )
    return;
  if ( (*(int (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v3 + 48LL))(v3, &lpString2) >= 0 )
  {
    if ( CompareStringW(0x7Fu, 1u, L"ms_tcpip", -1, lpString2, -1) != 2
      && CompareStringW(0x7Fu, 1u, L"ms_tcpip6", -1, lpString2, -1) != 2 )
    {
      if ( !(unsigned int)NeModifySettings(a1, lpString2, 2) )
        PostMessageW(*((HWND *)a1 + 1), 0x46Bu, 0, 0);
      CoTaskMemFree((LPVOID)lpString2);
      return;
    }
    CoTaskMemFree((LPVOID)lpString2);
  }
  v5 = (CRasConnectionUiIpInfo *)*((_QWORD *)a1 + 186);
  if ( !v5 )
  {
    v6 = (CRasConnectionUiIpInfo *)operator new(0x18u);
    if ( v6 && (v7 = CRasConnectionUiIpInfo::CRasConnectionUiIpInfo(v6, a1), (v5 = v7) != 0) )
    {
      *((_QWORD *)a1 + 186) = v7;
    }
    else
    {
      *((_QWORD *)a1 + 186) = 0;
      v5 = 0;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, CRasConnectionUiIpInfo *))(*(_QWORD *)v4 + 112LL))(
          v4,
          *((_QWORD *)a1 + 1),
          2,
          v5) )
  {
    v8 = *(int (__fastcall ***)(__int64, GUID *, __int64 *))v4;
    v23 = 0;
    if ( (*v8)(v4, &IID_INetCfgComponentPrivate, &v23) >= 0 )
    {
      v22 = 0;
      if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v23 + 24LL))(
             v23,
             &IID_INetRasConnectionIpUiInfo,
             &v22) >= 0 )
      {
        memset_0(v24, 0, 0x44Cu);
        if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v22 + 24LL))(v22, v24) >= 0 )
        {
          v9 = *(_QWORD *)(*(_QWORD *)a1 + 872LL);
          if ( v25 )
          {
            v15 = *(void **)(v9 + 360);
            *(_DWORD *)(v9 + 356) = 1;
            *(_DWORD *)(v9 + 376) = 1;
            Free0(v15);
            v16 = *(void **)(v9 + 384);
            *(_QWORD *)(v9 + 360) = 0;
            *(_DWORD *)(v9 + 368) = 0;
            Free0(v16);
            v17 = *(void **)(v9 + 392);
            *(_QWORD *)(v9 + 384) = 0;
            Free0(v17);
            *(_QWORD *)(v9 + 392) = 0;
            if ( (v26 & 0x800) != 0 && v33[0] )
            {
              *(_DWORD *)(v9 + 356) = 2;
              *(_QWORD *)(v9 + 360) = StrDup(v33);
              *(_DWORD *)(v9 + 368) = v34;
            }
            if ( (v26 & 0x1000) != 0 )
            {
              if ( v35[0] )
              {
                *(_DWORD *)(v9 + 376) = 2;
                *(_QWORD *)(v9 + 384) = StrDup(v35);
              }
              if ( v36[0] )
              {
                *(_DWORD *)(v9 + 376) = 2;
                *(_QWORD *)(v9 + 392) = StrDup(v36);
              }
            }
            if ( *(_DWORD *)(*(_QWORD *)a1 + 28LL) )
            {
              *(_DWORD *)(v9 + 372) = 0;
            }
            else
            {
              *(_DWORD *)(v9 + 372) = v26 & 0x2000;
              *(_DWORD *)(v9 + 416) = (v26 & 0x4000) != 0 ? v38 : 0;
            }
          }
          else
          {
            v10 = *(void **)(v9 + 280);
            *(_DWORD *)(v9 + 320) = 1;
            *(_DWORD *)(v9 + 324) = 1;
            Free0(v10);
            v11 = *(void **)(v9 + 288);
            *(_QWORD *)(v9 + 280) = 0;
            Free0(v11);
            v12 = *(void **)(v9 + 296);
            *(_QWORD *)(v9 + 288) = 0;
            Free0(v12);
            v13 = *(void **)(v9 + 304);
            *(_QWORD *)(v9 + 296) = 0;
            Free0(v13);
            v14 = *(void **)(v9 + 312);
            *(_QWORD *)(v9 + 304) = 0;
            Free0(v14);
            *(_QWORD *)(v9 + 312) = 0;
            if ( (v26 & 8) != 0 && pszSrc[0] )
            {
              *(_DWORD *)(v9 + 320) = 2;
              *(_QWORD *)(v9 + 280) = StrDup(pszSrc);
            }
            if ( (v26 & 0x10) != 0 )
            {
              if ( v28[0] )
              {
                *(_DWORD *)(v9 + 324) = 2;
                *(_QWORD *)(v9 + 288) = StrDup(v28);
              }
              if ( v29[0] )
              {
                *(_DWORD *)(v9 + 324) = 2;
                *(_QWORD *)(v9 + 296) = StrDup(v29);
              }
              if ( v30[0] )
              {
                *(_DWORD *)(v9 + 324) = 2;
                *(_QWORD *)(v9 + 304) = StrDup(v30);
              }
              if ( v31[0] )
              {
                *(_DWORD *)(v9 + 324) = 2;
                *(_QWORD *)(v9 + 312) = StrDup(v31);
              }
            }
            *(_DWORD *)(v9 + 332) = (v26 >> 10) & 1;
            if ( *(_DWORD *)(*(_QWORD *)a1 + 28LL) )
            {
              *(_DWORD *)(v9 + 272) = 0;
            }
            else
            {
              *(_DWORD *)(v9 + 272) = (v26 >> 5) & 1;
              *(_DWORD *)(v9 + 544) = (v26 >> 15) & 1;
              *(_DWORD *)(v9 + 352) = (v26 & 0x40) != 0 ? v37 : 0;
            }
            *(_DWORD *)(v9 + 276) = v26 & 0x80;
          }
          Free0(*(void **)(v9 + 344));
          v18 = (_WORD *)StrDup(v32);
          *(_QWORD *)(v9 + 344) = v18;
          if ( (v26 & 0x100) != 0 )
          {
            *(_DWORD *)(v9 + 328) = 0;
          }
          else
          {
            if ( !v18 || (v19 = *v18 == 0, v20 = 1, v19) )
              v20 = 0;
            *(_DWORD *)(v9 + 328) = 1;
            if ( (v26 & 0x200) != 0 )
              *(_DWORD *)(v9 + 328) = v20 != 0 ? 3 : 5;
          }
        }
        ReleaseObj(v22);
      }
      ReleaseObj(v23);
    }
  }
}

```

## disassembly

```asm
0x180027458  push    rbp
0x18002745a  push    rbx
0x18002745b  push    rsi
0x18002745c  push    rdi
0x18002745d  push    r14
0x18002745f  push    r15
0x180027461  lea     rbp, [rsp-3B8h]
0x180027469  sub     rsp, 4B8h
0x180027470  mov     rax, cs:__security_cookie
0x180027477  xor     rax, rsp
0x18002747a  mov     [rbp+3E0h+var_40], rax
0x180027481  mov     rdi, rcx
0x180027484  xor     esi, esi
0x180027486  mov     rcx, [rcx+218h]; hWnd
0x18002748d  xor     edx, edx
0x18002748f  mov     [rsp+4E0h+var_4B0], rsi
0x180027494  call    PComponentFromCurSel
0x180027499  mov     rbx, rax
0x18002749c  test    rax, rax
0x18002749f  jz      loc_180027954
0x1800274a5  mov     rcx, [rax]
0x1800274a8  lea     rdx, [rsp+4E0h+var_4B0]
0x1800274ad  mov     rax, [rcx+30h]
0x1800274b1  mov     rcx, rbx
0x1800274b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274b9  lea     r15d, [rsi+1]
0x1800274bd  lea     r14d, [rsi+2]
0x1800274c1  test    eax, eax
0x1800274c3  js      loc_180027569
0x1800274c9  mov     rax, [rsp+4E0h+var_4B0]
0x1800274ce  lea     r8, aMsTcpip; "ms_tcpip"
0x1800274d5  mov     [rsp+4E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800274dd  lea     ecx, [rsi+7Fh]; Locale
0x1800274e0  or      r9d, 0FFFFFFFFh; cchCount1
0x1800274e4  mov     [rsp+4E0h+lpString2], rax; lpString2
0x1800274e9  mov     edx, r15d; dwCmpFlags
0x1800274ec  call    cs:__imp_CompareStringW
0x1800274f2  cmp     eax, r14d
0x1800274f5  jz      short loc_18002755E
0x1800274f7  mov     rax, [rsp+4E0h+var_4B0]
0x1800274fc  lea     r8, aMsTcpip6; "ms_tcpip6"
0x180027503  mov     [rsp+4E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002750b  lea     ecx, [rsi+7Fh]; Locale
0x18002750e  or      r9d, 0FFFFFFFFh; cchCount1
0x180027512  mov     [rsp+4E0h+lpString2], rax; lpString2
0x180027517  mov     edx, r15d; dwCmpFlags
0x18002751a  call    cs:__imp_CompareStringW
0x180027520  cmp     eax, r14d
0x180027523  jz      short loc_18002755E
0x180027525  mov     rdx, [rsp+4E0h+var_4B0]
0x18002752a  mov     r8d, r14d
0x18002752d  mov     rcx, rdi
0x180027530  call    NeModifySettings
0x180027535  test    eax, eax
0x180027537  jnz     short loc_18002754E
0x180027539  mov     rcx, [rdi+8]; hWnd
0x18002753d  xor     r9d, r9d; lParam
0x180027540  xor     r8d, r8d; wParam
0x180027543  mov     edx, 46Bh; Msg
0x180027548  call    cs:__imp_PostMessageW
0x18002754e  mov     rcx, [rsp+4E0h+var_4B0]; pv
0x180027553  call    cs:__imp_CoTaskMemFree
0x180027559  jmp     loc_180027954
0x18002755e  mov     rcx, [rsp+4E0h+var_4B0]; pv
0x180027563  call    cs:__imp_CoTaskMemFree
0x180027569  mov     r9, [rdi+5D0h]
0x180027570  test    r9, r9
0x180027573  jnz     short loc_1800275A9
0x180027575  lea     ecx, [r9+18h]; Size
0x180027579  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002757e  test    rax, rax
0x180027581  jz      short loc_18002759F
0x180027583  mov     rdx, rdi; struct _PEINFO *
0x180027586  mov     rcx, rax; this
0x180027589  call    ??0CRasConnectionUiIpInfo@@QEAA@PEAU_PEINFO@@@Z; CRasConnectionUiIpInfo::CRasConnectionUiIpInfo(_PEINFO *)
0x18002758e  mov     r9, rax
0x180027591  test    rax, rax
0x180027594  jz      short loc_18002759F
0x180027596  mov     [rdi+5D0h], rax
0x18002759d  jmp     short loc_1800275A9
0x18002759f  mov     [rdi+5D0h], rsi
0x1800275a6  mov     r9, rsi
0x1800275a9  mov     rax, [rbx]
0x1800275ac  mov     r8d, r14d
0x1800275af  mov     rdx, [rdi+8]
0x1800275b3  mov     rcx, rbx
0x1800275b6  mov     rax, [rax+70h]
0x1800275ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275bf  test    eax, eax
0x1800275c1  jnz     loc_180027954
0x1800275c7  mov     rax, [rbx]
0x1800275ca  lea     r8, [rsp+4E0h+var_4A0]
0x1800275cf  mov     [rsp+4E0h+var_4A0], rsi
0x1800275d4  lea     rdx, IID_INetCfgComponentPrivate
0x1800275db  mov     rcx, rbx
0x1800275de  mov     rax, [rax]
0x1800275e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275e6  test    eax, eax
0x1800275e8  js      loc_180027954
0x1800275ee  mov     rcx, [rsp+4E0h+var_4A0]
0x1800275f3  lea     r8, [rsp+4E0h+var_4A8]
0x1800275f8  mov     [rsp+4E0h+var_4A8], rsi
0x1800275fd  lea     rdx, IID_INetRasConnectionIpUiInfo
0x180027604  mov     rax, [rcx]
0x180027607  mov     rax, [rax+18h]
0x18002760b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027610  test    eax, eax
0x180027612  js      loc_18002794A
0x180027618  xor     edx, edx; Val
0x18002761a  lea     rcx, [rsp+4E0h+var_490]; void *
0x18002761f  mov     r8d, 44Ch; Size
0x180027625  call    memset_0
0x18002762a  mov     rcx, [rsp+4E0h+var_4A8]
0x18002762f  lea     rdx, [rsp+4E0h+var_490]
0x180027634  mov     rax, [rcx]
0x180027637  mov     rax, [rax+18h]
0x18002763b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027640  test    eax, eax
0x180027642  js      loc_180027940
0x180027648  mov     rax, [rdi]
0x18002764b  mov     rbx, [rax+368h]
0x180027652  cmp     [rsp+4E0h+var_480], esi
0x180027656  jnz     loc_1800277D4
0x18002765c  mov     rcx, [rbx+118h]
0x180027663  mov     [rbx+140h], r15d
0x18002766a  mov     [rbx+144h], r15d
0x180027671  call    Free0
0x180027676  mov     rcx, [rbx+120h]
0x18002767d  mov     [rbx+118h], rsi
0x180027684  call    Free0
0x180027689  mov     rcx, [rbx+128h]
0x180027690  mov     [rbx+120h], rsi
0x180027697  call    Free0
0x18002769c  mov     rcx, [rbx+130h]
0x1800276a3  mov     [rbx+128h], rsi
0x1800276aa  call    Free0
0x1800276af  mov     rcx, [rbx+138h]
0x1800276b6  mov     [rbx+130h], rsi
0x1800276bd  call    Free0
0x1800276c2  mov     [rbx+138h], rsi
0x1800276c9  test    byte ptr [rsp+4E0h+var_47C], 8
0x1800276ce  jz      short loc_1800276EF
0x1800276d0  cmp     [rsp+4E0h+pszSrc], si
0x1800276d5  jz      short loc_1800276EF
0x1800276d7  lea     rcx, [rsp+4E0h+pszSrc]; pszSrc
0x1800276dc  mov     [rbx+140h], r14d
0x1800276e3  call    StrDup
0x1800276e8  mov     [rbx+118h], rax
0x1800276ef  test    byte ptr [rsp+4E0h+var_47C], 10h
0x1800276f4  jz      short loc_18002776A
0x1800276f6  cmp     [rbp+3E0h+var_458], si
0x1800276fa  jz      short loc_180027713
0x1800276fc  lea     rcx, [rbp+3E0h+var_458]; pszSrc
0x180027700  mov     [rbx+144h], r14d
0x180027707  call    StrDup
0x18002770c  mov     [rbx+120h], rax
0x180027713  cmp     [rbp+3E0h+var_438], si
0x180027717  jz      short loc_180027730
0x180027719  lea     rcx, [rbp+3E0h+var_438]; pszSrc
0x18002771d  mov     [rbx+144h], r14d
0x180027724  call    StrDup
0x180027729  mov     [rbx+128h], rax
0x180027730  cmp     [rbp+3E0h+var_418], si
0x180027734  jz      short loc_18002774D
0x180027736  lea     rcx, [rbp+3E0h+var_418]; pszSrc
0x18002773a  mov     [rbx+144h], r14d
0x180027741  call    StrDup
0x180027746  mov     [rbx+130h], rax
0x18002774d  cmp     [rbp+3E0h+var_3F8], si
0x180027751  jz      short loc_18002776A
0x180027753  lea     rcx, [rbp+3E0h+var_3F8]; pszSrc
0x180027757  mov     [rbx+144h], r14d
0x18002775e  call    StrDup
0x180027763  mov     [rbx+138h], rax
0x18002776a  mov     eax, [rsp+4E0h+var_47C]
0x18002776e  shr     eax, 0Ah
0x180027771  and     eax, r15d
0x180027774  mov     [rbx+14Ch], eax
0x18002777a  mov     rax, [rdi]
0x18002777d  cmp     [rax+1Ch], esi
0x180027780  jz      short loc_18002778A
0x180027782  mov     [rbx+110h], esi
0x180027788  jmp     short loc_1800277C0
0x18002778a  mov     eax, [rsp+4E0h+var_47C]
0x18002778e  shr     eax, 5
0x180027791  and     eax, r15d
0x180027794  mov     [rbx+110h], eax
0x18002779a  mov     eax, [rsp+4E0h+var_47C]
0x18002779e  shr     eax, 0Fh
0x1800277a1  and     eax, r15d
0x1800277a4  mov     [rbx+220h], eax
0x1800277aa  mov     al, byte ptr [rsp+4E0h+var_47C]
0x1800277ae  and     al, 40h
0x1800277b0  neg     al
0x1800277b2  sbb     eax, eax
0x1800277b4  and     eax, [rbp+3E0h+var_4C]
0x1800277ba  mov     [rbx+160h], eax
0x1800277c0  mov     eax, [rsp+4E0h+var_47C]
0x1800277c4  and     eax, 80h
0x1800277c9  mov     [rbx+114h], eax
0x1800277cf  jmp     loc_1800278E2
0x1800277d4  mov     rcx, [rbx+168h]
0x1800277db  mov     [rbx+164h], r15d
0x1800277e2  mov     [rbx+178h], r15d
0x1800277e9  call    Free0
0x1800277ee  mov     rcx, [rbx+180h]
0x1800277f5  mov     [rbx+168h], rsi
0x1800277fc  mov     [rbx+170h], esi
0x180027802  call    Free0
0x180027807  mov     rcx, [rbx+188h]
0x18002780e  mov     [rbx+180h], rsi
0x180027815  call    Free0
0x18002781a  mov     [rbx+188h], rsi
0x180027821  test    [rsp+4E0h+var_47C], 800h
0x180027829  jz      short loc_18002785A
0x18002782b  cmp     [rbp+3E0h+var_1D8], si
0x180027832  jz      short loc_18002785A
0x180027834  lea     rcx, [rbp+3E0h+var_1D8]; pszSrc
0x18002783b  mov     [rbx+164h], r14d
0x180027842  call    StrDup
0x180027847  mov     [rbx+168h], rax
0x18002784e  mov     eax, [rbp+3E0h+var_154]
0x180027854  mov     [rbx+170h], eax
0x18002785a  test    [rsp+4E0h+var_47C], 1000h
0x180027862  jz      short loc_1800278AA
0x180027864  cmp     [rbp+3E0h+var_150], si
0x18002786b  jz      short loc_180027887
0x18002786d  lea     rcx, [rbp+3E0h+var_150]; pszSrc
0x180027874  mov     [rbx+178h], r14d
0x18002787b  call    StrDup
0x180027880  mov     [rbx+180h], rax
0x180027887  cmp     [rbp+3E0h+var_CE], si
0x18002788e  jz      short loc_1800278AA
0x180027890  lea     rcx, [rbp+3E0h+var_CE]; pszSrc
0x180027897  mov     [rbx+178h], r14d
0x18002789e  call    StrDup
0x1800278a3  mov     [rbx+188h], rax
0x1800278aa  mov     rax, [rdi]
0x1800278ad  cmp     [rax+1Ch], esi
0x1800278b0  jz      short loc_1800278BA
0x1800278b2  mov     [rbx+174h], esi
0x1800278b8  jmp     short loc_1800278E2
0x1800278ba  mov     eax, [rsp+4E0h+var_47C]
0x1800278be  and     eax, 2000h
0x1800278c3  mov     [rbx+174h], eax
0x1800278c9  mov     eax, [rsp+4E0h+var_47C]
0x1800278cd  and     eax, 4000h
0x1800278d2  neg     eax
0x1800278d4  sbb     eax, eax
0x1800278d6  and     eax, [rbp+3E0h+var_48]
0x1800278dc  mov     [rbx+1A0h], eax
0x1800278e2  mov     rcx, [rbx+158h]
0x1800278e9  call    Free0
0x1800278ee  lea     rcx, [rbp+3E0h+var_3D8]; pszSrc
0x1800278f2  call    StrDup
0x1800278f7  mov     [rbx+158h], rax
0x1800278fe  test    [rsp+4E0h+var_47C], 100h
0x180027906  jz      short loc_180027910
0x180027908  mov     [rbx+148h], esi
0x18002790e  jmp     short loc_180027940
0x180027910  test    rax, rax
0x180027913  jz      short loc_18002791D
0x180027915  cmp     [rax], si
0x180027918  mov     eax, r15d
0x18002791b  jnz     short loc_18002791F
0x18002791d  mov     eax, esi
0x18002791f  mov     [rbx+148h], r15d
0x180027926  test    [rsp+4E0h+var_47C], 200h
0x18002792e  jz      short loc_180027940
0x180027930  neg     eax
0x180027932  sbb     eax, eax
0x180027934  and     eax, 0FFFFFFFEh
0x180027937  add     eax, 5
0x18002793a  mov     [rbx+148h], eax
0x180027940  mov     rcx, [rsp+4E0h+var_4A8]
0x180027945  call    ReleaseObj
0x18002794a  mov     rcx, [rsp+4E0h+var_4A0]
0x18002794f  call    ReleaseObj
0x180027954  mov     rcx, [rbp+3E0h+var_40]
0x18002795b  xor     rcx, rsp; StackCookie
0x18002795e  call    __security_check_cookie
0x180027963  add     rsp, 4B8h
0x18002796a  pop     r15
0x18002796c  pop     r14
0x18002796e  pop     rdi
0x18002796f  pop     rsi
0x180027970  pop     rbx
0x180027971  pop     rbp
0x180027972  retn
```
