# CreateAcesForScpObject

- ea: `0x180079104`
- end: `0x1800794c8`
- name: `CreateAcesForScpObject`
- size: `964`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007c0e0`

## callees

- `0x18001aea4`
- `0x180078a4c`
- `0x180078a94`
- `0x180078bbc`
- `0x180078dac`
- `0x180079104`
- `0x1800794d0`
- `0x1800a5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18007949c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800794ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18007949c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800794ad`
- `OLEAUT32!__imp_VariantInit` at `0x18007915b`
- `OLEAUT32!__imp_VariantInit` at `0x18007915b`
- `OLEAUT32!__imp_VariantClear` at `0x180079481`
- `OLEAUT32!__imp_VariantClear` at `0x180079481`

## string_xrefs

- `0x180079132`: `nTSecurityDescriptor`
- `0x18007928b`: `"QueryInterface IID_IADsAccessControlList"`
- `0x1800791d9`: `"QueryInterface IID_IADsSecurityDescriptor"`
- `0x18007923c`: `"pSD->get_DiscretionaryAcl"`
- `0x180079376`: `"AddAceToAcl"`
- `0x1800792e3`: `"CreateScpAce"`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreateAcesForScpObject(__int64 *a1, const unsigned __int16 *a2)
{
  int v3; // edi
  _QWORD *v4; // rcx
  int v5; // edx
  const wchar_t *v6; // r9
  BSTR *v7; // rax
  BSTR *v8; // rax
  __int64 v9; // rax
  _BYTE v11[8]; // [rsp+30h] [rbp-19h] BYREF
  LPVOID v12; // [rsp+38h] [rbp-11h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-1h] BYREF
  BSTR v15; // [rsp+50h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp+Fh] BYREF
  VARIANTARG v17; // [rsp+70h] [rbp+27h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+67h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+77h] BYREF
  LPVOID v20; // [rsp+C8h] [rbp+7Fh] BYREF

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v15, a2);
  memset(&pvarg, 0, sizeof(pvarg));
  v19 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"nTSecurityDescriptor");
  v13 = 0;
  v20 = 0;
  v12 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  v3 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *))(*a1 + 120))(a1, bstrString, &pvarg);
  if ( v3 < 0 || pvarg.vt != 9 )
    goto LABEL_37;
  v3 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
         pvarg.llVal,
         &IID_IADsSecurityDescriptor,
         &v19);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v19
                                                                                                  + 152LL))(
           v19,
           &v13);
    if ( v3 >= 0 )
    {
      v3 = (**v13)(v13, &IID_IADsAccessControlList, &v18);
      if ( v3 >= 0 )
      {
        v7 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v11, (const struct ATL::CComBSTR *)&v15);
        v3 = CreateScpAce(&v20, v7, (__int64)L"{28630eb8-41d5-11d1-a9c1-0000f80367c1}");
        if ( v3 >= 0 )
        {
          v8 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v11, (const struct ATL::CComBSTR *)&v15);
          v3 = CreateScpAce(&v12, v8, (__int64)L"{b7b1311c-b82e-11d0-afee-0000f80367c1}");
          if ( v3 >= 0 )
          {
            v3 = AddAceToAcl(v18, v20);
            if ( v3 >= 0 )
            {
              v3 = AddAceToAcl(v18, v12);
              if ( v3 >= 0 )
              {
                v3 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v19 + 160LL))(
                       v19,
                       v13);
                if ( v3 >= 0 )
                {
                  v9 = *a1;
                  v17 = pvarg;
                  v3 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *))(v9 + 128))(a1, bstrString, &v17);
                  if ( v3 >= 0 )
                    v3 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 112))(a1);
                }
                goto LABEL_37;
              }
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_37;
              v5 = 80;
            }
            else
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_37;
              v5 = 79;
            }
            v6 = L"\"AddAceToAcl\"";
            goto LABEL_7;
          }
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_37;
          v5 = 78;
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_37;
          v5 = 77;
        }
        v6 = L"\"CreateScpAce\"";
        goto LABEL_7;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 76;
        v6 = L"\"QueryInterface IID_IADsAccessControlList\"";
        goto LABEL_7;
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 75;
        v6 = L"\"pSD->get_DiscretionaryAcl\"";
        goto LABEL_7;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 74;
      v6 = L"\"QueryInterface IID_IADsSecurityDescriptor\"";
LABEL_7:
      WPP_SF_SD(v4[2], v5, (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, (_DWORD)v6, v3);
    }
  }
LABEL_37:
  if ( v20 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  VariantClear(&pvarg);
  ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(&v13);
  SysFreeString(bstrString);
  SysFreeString(v15);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180079104  push    rbp
0x180079106  push    rsi
0x180079107  push    rdi
0x180079108  lea     rbp, [rsp-47h]
0x18007910d  sub     rsp, 90h
0x180079114  mov     rsi, rcx
0x180079117  lea     rcx, [rbp+57h+var_50]; this
0x18007911b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180079120  nop
0x180079121  xorps   xmm0, xmm0
0x180079124  xor     eax, eax
0x180079126  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18007912a  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18007912e  and     [rbp+57h+arg_10], rax
0x180079132  lea     rdx, aNtsecuritydesc; "nTSecurityDescriptor"
0x180079139  lea     rcx, [rbp+57h+bstrString]; this
0x18007913d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180079142  nop
0x180079143  and     [rbp+57h+var_60], 0
0x180079148  and     [rbp+57h+arg_18], 0
0x18007914d  and     [rbp+57h+var_68], 0
0x180079152  and     [rbp+57h+arg_0], 0
0x180079157  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007915b  call    cs:__imp_VariantInit
0x180079162  nop     dword ptr [rax+rax+00h]
0x180079167  mov     rax, [rsi]
0x18007916a  lea     r8, [rbp+57h+pvarg]
0x18007916e  mov     rdx, [rbp+57h+bstrString]
0x180079172  mov     rcx, rsi
0x180079175  mov     rax, [rax+78h]
0x180079179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007917e  mov     edi, eax
0x180079180  test    eax, eax
0x180079182  js      loc_180079415
0x180079188  cmp     word ptr [rbp+57h+pvarg], 9
0x18007918d  jnz     loc_180079415
0x180079193  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x180079197  mov     rax, [rcx]
0x18007919a  lea     r8, [rbp+57h+arg_10]
0x18007919e  lea     rdx, IID_IADsSecurityDescriptor
0x1800791a5  mov     rax, [rax]
0x1800791a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800791ad  mov     edi, eax
0x1800791af  test    eax, eax
0x1800791b1  jns     short loc_1800791F9
0x1800791b3  lea     rax, WPP_GLOBAL_Control
0x1800791ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791c1  cmp     rcx, rax
0x1800791c4  jz      loc_180079415
0x1800791ca  cmp     byte ptr [rcx+19h], 2
0x1800791ce  jb      loc_180079415
0x1800791d4  mov     edx, 4Ah ; 'J'
0x1800791d9  lea     r9, aQueryinterface_0; "\"QueryInterface IID_IADsSecurityDescri"...
0x1800791e0  mov     [rsp+0A0h+var_80], edi
0x1800791e4  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x1800791eb  mov     rcx, [rcx+10h]
0x1800791ef  call    WPP_SF_SD
0x1800791f4  jmp     loc_180079415
0x1800791f9  mov     rcx, [rbp+57h+arg_10]
0x1800791fd  mov     rax, [rcx]
0x180079200  lea     rdx, [rbp+57h+var_60]
0x180079204  mov     rax, [rax+98h]
0x18007920b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079210  mov     edi, eax
0x180079212  test    eax, eax
0x180079214  jns     short loc_180079245
0x180079216  lea     rax, WPP_GLOBAL_Control
0x18007921d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079224  cmp     rcx, rax
0x180079227  jz      loc_180079415
0x18007922d  cmp     byte ptr [rcx+19h], 2
0x180079231  jb      loc_180079415
0x180079237  mov     edx, 4Bh ; 'K'
0x18007923c  lea     r9, aPsdGetDiscreti; "\"pSD->get_DiscretionaryAcl\""
0x180079243  jmp     short loc_1800791E0
0x180079245  mov     rcx, [rbp+57h+var_60]
0x180079249  mov     rax, [rcx]
0x18007924c  lea     r8, [rbp+57h+arg_0]
0x180079250  lea     rdx, IID_IADsAccessControlList
0x180079257  mov     rax, [rax]
0x18007925a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007925f  mov     edi, eax
0x180079261  test    eax, eax
0x180079263  jns     short loc_180079297
0x180079265  lea     rax, WPP_GLOBAL_Control
0x18007926c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079273  cmp     rcx, rax
0x180079276  jz      loc_180079415
0x18007927c  cmp     byte ptr [rcx+19h], 2
0x180079280  jb      loc_180079415
0x180079286  mov     edx, 4Ch ; 'L'
0x18007928b  lea     r9, aQueryinterface_1; "\"QueryInterface IID_IADsAccessControlL"...
0x180079292  jmp     loc_1800791E0
0x180079297  lea     rdx, [rbp+57h+var_50]; struct ATL::CComBSTR *
0x18007929b  lea     rcx, [rbp+57h+var_70]; this
0x18007929f  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x1800792a4  lea     r8, a28630eb841d511; "{28630eb8-41d5-11d1-a9c1-0000f80367c1}"
0x1800792ab  mov     rdx, rax
0x1800792ae  lea     rcx, [rbp+57h+arg_18]
0x1800792b2  call    CreateScpAce
0x1800792b7  mov     edi, eax
0x1800792b9  test    eax, eax
0x1800792bb  jns     short loc_1800792EF
0x1800792bd  lea     rax, WPP_GLOBAL_Control
0x1800792c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800792cb  cmp     rcx, rax
0x1800792ce  jz      loc_180079415
0x1800792d4  cmp     byte ptr [rcx+19h], 2
0x1800792d8  jb      loc_180079415
0x1800792de  mov     edx, 4Dh ; 'M'
0x1800792e3  lea     r9, aCreatescpace; "\"CreateScpAce\""
0x1800792ea  jmp     loc_1800791E0
0x1800792ef  lea     rdx, [rbp+57h+var_50]; struct ATL::CComBSTR *
0x1800792f3  lea     rcx, [rbp+57h+var_70]; this
0x1800792f7  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x1800792fc  lea     r8, aB7b1311cB82e11; "{b7b1311c-b82e-11d0-afee-0000f80367c1}"
0x180079303  mov     rdx, rax
0x180079306  lea     rcx, [rbp+57h+var_68]
0x18007930a  call    CreateScpAce
0x18007930f  mov     edi, eax
0x180079311  test    eax, eax
0x180079313  jns     short loc_18007933D
0x180079315  lea     rax, WPP_GLOBAL_Control
0x18007931c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079323  cmp     rcx, rax
0x180079326  jz      loc_180079415
0x18007932c  cmp     byte ptr [rcx+19h], 2
0x180079330  jb      loc_180079415
0x180079336  mov     edx, 4Eh ; 'N'
0x18007933b  jmp     short loc_1800792E3
0x18007933d  mov     rdx, [rbp+57h+arg_18]
0x180079341  mov     rcx, [rbp+57h+arg_0]
0x180079345  call    AddAceToAcl
0x18007934a  mov     edi, eax
0x18007934c  test    eax, eax
0x18007934e  jns     short loc_180079382
0x180079350  lea     rax, WPP_GLOBAL_Control
0x180079357  mov     rcx, cs:WPP_GLOBAL_Control
0x18007935e  cmp     rcx, rax
0x180079361  jz      loc_180079415
0x180079367  cmp     byte ptr [rcx+19h], 2
0x18007936b  jb      loc_180079415
0x180079371  mov     edx, 4Fh ; 'O'
0x180079376  lea     r9, aAddacetoacl; "\"AddAceToAcl\""
0x18007937d  jmp     loc_1800791E0
0x180079382  mov     rdx, [rbp+57h+var_68]
0x180079386  mov     rcx, [rbp+57h+arg_0]
0x18007938a  call    AddAceToAcl
0x18007938f  mov     edi, eax
0x180079391  test    eax, eax
0x180079393  jns     short loc_1800793B5
0x180079395  lea     rax, WPP_GLOBAL_Control
0x18007939c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793a3  cmp     rcx, rax
0x1800793a6  jz      short loc_180079415
0x1800793a8  cmp     byte ptr [rcx+19h], 2
0x1800793ac  jb      short loc_180079415
0x1800793ae  mov     edx, 50h ; 'P'
0x1800793b3  jmp     short loc_180079376
0x1800793b5  mov     rcx, [rbp+57h+arg_10]
0x1800793b9  mov     rax, [rcx]
0x1800793bc  mov     rdx, [rbp+57h+var_60]
0x1800793c0  mov     rax, [rax+0A0h]
0x1800793c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793cc  mov     edi, eax
0x1800793ce  test    eax, eax
0x1800793d0  js      short loc_180079415
0x1800793d2  mov     rax, [rsi]
0x1800793d5  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800793d9  movaps  [rbp+57h+var_30], xmm0
0x1800793dd  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800793e2  movsd   [rbp+57h+var_20], xmm1
0x1800793e7  lea     r8, [rbp+57h+var_30]
0x1800793eb  mov     rdx, [rbp+57h+bstrString]
0x1800793ef  mov     rcx, rsi
0x1800793f2  mov     rax, [rax+80h]
0x1800793f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793fe  mov     edi, eax
0x180079400  test    eax, eax
0x180079402  js      short loc_180079415
0x180079404  mov     rax, [rsi]
0x180079407  mov     rcx, rsi
0x18007940a  mov     rax, [rax+70h]
0x18007940e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079413  mov     edi, eax
0x180079415  mov     rcx, [rbp+57h+arg_18]
0x180079419  test    rcx, rcx
0x18007941c  jz      short loc_18007942F
0x18007941e  mov     rax, [rcx]
0x180079421  mov     rax, [rax+10h]
0x180079425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007942a  and     [rbp+57h+arg_18], 0
0x18007942f  mov     rcx, [rbp+57h+var_68]
0x180079433  test    rcx, rcx
0x180079436  jz      short loc_180079449
0x180079438  mov     rax, [rcx]
0x18007943b  mov     rax, [rax+10h]
0x18007943f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079444  and     [rbp+57h+var_68], 0
0x180079449  mov     rcx, [rbp+57h+arg_0]
0x18007944d  test    rcx, rcx
0x180079450  jz      short loc_180079463
0x180079452  mov     rax, [rcx]
0x180079455  mov     rax, [rax+10h]
0x180079459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007945e  and     [rbp+57h+arg_0], 0
0x180079463  mov     rcx, [rbp+57h+arg_10]
0x180079467  test    rcx, rcx
0x18007946a  jz      short loc_18007947D
0x18007946c  mov     rax, [rcx]
0x18007946f  mov     rax, [rax+10h]
0x180079473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079478  and     [rbp+57h+arg_10], 0
0x18007947d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180079481  call    cs:__imp_VariantClear
0x180079488  nop     dword ptr [rax+rax+00h]
0x18007948d  nop
0x18007948e  lea     rcx, [rbp+57h+var_60]
0x180079492  call    ??1?$CComPtrBase@UIADs@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(void)
0x180079497  nop
0x180079498  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18007949c  call    cs:__imp_SysFreeString
0x1800794a3  nop     dword ptr [rax+rax+00h]
0x1800794a8  nop
0x1800794a9  mov     rcx, [rbp+57h+var_50]; bstrString
0x1800794ad  call    cs:__imp_SysFreeString
0x1800794b4  nop     dword ptr [rax+rax+00h]
0x1800794b9  nop
0x1800794ba  mov     eax, edi
0x1800794bc  add     rsp, 90h
0x1800794c3  pop     rdi
0x1800794c4  pop     rsi
0x1800794c5  pop     rbp
0x1800794c6  retn
```
