# AddOnlineUserNames(CDPANewMem<CShareUserInfo> &)

- ea: `0x180019068`
- end: `0x18001944b`
- name: `?AddOnlineUserNames@@YAJAEAV?$CDPANewMem@VCShareUserInfo@@@@@Z`
- size: `995`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180072570`

## callees

- `0x1800120e0`
- `0x180019068`
- `0x180019454`
- `0x1800194cc`
- `0x1800194e8`
- `0x180022c18`
- `0x180022d28`
- `0x1800254e0`
- `0x1800259bc`
- `0x18003c01c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800190b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800190b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800191b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001923e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001931b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001933e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001936c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800191b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001923e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001931b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001933e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001936c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800191c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800191c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AddOnlineUserNames(__int64 a1)
{
  HRESULT String; // edi
  const struct _GUID *v3; // rdx
  void *v4; // rcx
  __int64 v5; // rdx
  struct IEnumUnknown *v6; // rax
  CShareUserInfo *v7; // rbx
  LPVOID v8; // rdi
  LPVOID v9; // rdi
  void *v10; // rcx
  LPVOID v11; // rdi
  void *v12; // rcx
  PSID v13; // rdi
  void *v14; // rcx
  unsigned int v15; // edx
  CShareUserInfo *v16; // rcx
  void *v17; // rcx
  void *v19; // [rsp+30h] [rbp-39h] BYREF
  PSID Sid; // [rsp+38h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  LPVOID v22; // [rsp+48h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-19h] BYREF
  LPVOID v24; // [rsp+58h] [rbp-11h] BYREF
  struct IEnumUnknown *v25[2]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v26; // [rsp+70h] [rbp+7h] BYREF

  ppv = 0;
  String = CoCreateInstance(&CLSID_OnlineIdFilter, 0, 1u, &GUID_e6496873_6ddc_4709_8785_1a5b3267843b, &ppv);
  if ( String < 0 )
    goto LABEL_48;
  v25[0] = 0;
  String = (*(__int64 (__fastcall **)(LPVOID, struct IEnumUnknown **))(*(_QWORD *)ppv + 24LL))(ppv, v25);
  if ( String < 0 )
    goto LABEL_46;
  v19 = 0;
  while ( (int)SHNextObjectFromEnumUnknown(v25[0], v3, &v19) >= 0 )
  {
    v22 = 0;
    CoTaskMemFree(0);
    String = IPropertyStore_GetString(v19, &PKEY_Identity_UserName, &v22);
    if ( String < 0 || !v22 || !*(_WORD *)v22 )
      goto LABEL_43;
    v24 = 0;
    CoTaskMemFree(0);
    String = IPropertyStore_GetString(v19, &PKEY_Identity_UserName, &v24);
    if ( String >= 0 )
    {
      pv = 0;
      CoTaskMemFree(0);
      if ( (int)IPropertyStore_GetString(v19, &PKEY_Identity_PrimarySid, &pv) >= 0 )
        goto LABEL_13;
      Sid = 0;
      String = (*(__int64 (__fastcall **)(LPVOID, LPVOID, PSID *))(*(_QWORD *)ppv + 48LL))(ppv, v22, &Sid);
      if ( String >= 0 )
      {
        CoTaskMemFree(pv);
        String = !ConvertSidToStringSidW(Sid, (LPWSTR *)&pv) ? 0x8007000E : 0;
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&Sid);
      if ( String < 0 )
      {
LABEL_40:
        v4 = pv;
      }
      else
      {
LABEL_13:
        v4 = pv;
        if ( pv && *(_WORD *)pv )
        {
          if ( !IsUserAccountDisabled((const unsigned __int16 *)pv) )
          {
            Sid = 0;
            CoTaskMemFree(0);
            if ( (int)IPropertyStore_GetString(v19, &PKEY_Identity_DisplayName, &Sid) < 0 || !Sid || !*(_WORD *)Sid )
            {
              CoTaskMemFree(Sid);
              IPropertyStore_GetString(v19, &PKEY_SAM_Name, &Sid);
            }
            v26 = 0;
            if ( (int)IPropertyStore_GetCLSID(v19, v5, &v26) >= 0 )
              (*(void (__fastcall **)(LPVOID, LPVOID, __int128 *))(*(_QWORD *)ppv + 64LL))(ppv, v22, &v26);
            v6 = (struct IEnumUnknown *)operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
            v7 = (CShareUserInfo *)v6;
            v25[1] = v6;
            if ( v6 )
            {
              v6->lpVtbl = 0;
              v6[1].lpVtbl = 0;
              v6[2].lpVtbl = 0;
              v6[3].lpVtbl = 0;
              v6[4].lpVtbl = 0;
              v6[5].lpVtbl = 0;
              v6[6].lpVtbl = 0;
              v6[7].lpVtbl = 0;
              v6[8].lpVtbl = 0;
              v6[9].lpVtbl = 0;
              v6[10].lpVtbl = 0;
              v6[11].lpVtbl = 0;
              LOBYTE(v6[12].lpVtbl) = 0;
              LOBYTE(v6[12].lpVtbl) = 1;
              v8 = v22;
              v22 = 0;
              if ( v6->lpVtbl )
                CoTaskMemFree(v6->lpVtbl);
              *(_QWORD *)v7 = v8;
              *((_QWORD *)v7 + 2) = -1;
              *((_QWORD *)v7 + 1) = -1;
              v9 = v24;
              v24 = 0;
              v10 = (void *)*((_QWORD *)v7 + 6);
              if ( v10 )
                CoTaskMemFree(v10);
              *((_QWORD *)v7 + 6) = v9;
              *((_QWORD *)v7 + 8) = -1;
              *((_QWORD *)v7 + 7) = -1;
              v11 = pv;
              pv = 0;
              v12 = (void *)*((_QWORD *)v7 + 9);
              if ( v12 )
                CoTaskMemFree(v12);
              *((_QWORD *)v7 + 9) = v11;
              *((_QWORD *)v7 + 11) = -1;
              *((_QWORD *)v7 + 10) = -1;
              v13 = Sid;
              if ( Sid && *(_WORD *)Sid )
              {
                Sid = 0;
                v14 = (void *)*((_QWORD *)v7 + 3);
                if ( v14 )
                  CoTaskMemFree(v14);
                *((_QWORD *)v7 + 3) = v13;
                *((_QWORD *)v7 + 5) = -1;
                *((_QWORD *)v7 + 4) = -1;
              }
              String = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(a1, v7);
              v16 = 0;
              if ( String < 0 )
                v16 = v7;
              if ( v16 )
                CShareUserInfo::`scalar deleting destructor'(v16, v15);
            }
            else
            {
              String = -2147024882;
            }
            CoTaskMemFree(Sid);
          }
          goto LABEL_40;
        }
      }
      CoTaskMemFree(v4);
    }
    CoTaskMemFree(v24);
LABEL_43:
    v17 = v19;
    v19 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
    CoTaskMemFree(v22);
    if ( String < 0 )
      break;
  }
  if ( v19 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_46:
  if ( v25[0] )
    ((void (__fastcall *)(struct IEnumUnknown *))v25[0]->lpVtbl->Release)(v25[0]);
LABEL_48:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180019068  push    rbp
0x18001906a  push    rbx
0x18001906b  push    rsi
0x18001906c  push    rdi
0x18001906d  push    r14
0x18001906f  push    r15
0x180019071  lea     rbp, [rsp-2Fh]
0x180019076  sub     rsp, 98h
0x18001907d  mov     rax, cs:__security_cookie
0x180019084  xor     rax, rsp
0x180019087  mov     [rbp+57h+var_40], rax
0x18001908b  mov     rsi, rcx
0x18001908e  xor     r14d, r14d
0x180019091  mov     [rbp+57h+var_70], r14
0x180019095  lea     rax, [rbp+57h+var_70]
0x180019099  mov     [rsp+0C0h+ppv], rax; ppv
0x18001909e  lea     r9, _GUID_e6496873_6ddc_4709_8785_1a5b3267843b; riid
0x1800190a5  xor     edx, edx; pUnkOuter
0x1800190a7  lea     r8d, [r14+1]; dwClsContext
0x1800190ab  lea     rcx, CLSID_OnlineIdFilter; rclsid
0x1800190b2  call    cs:__imp_CoCreateInstance
0x1800190b8  mov     edi, eax
0x1800190ba  test    eax, eax
0x1800190bc  js      loc_180019417
0x1800190c2  mov     [rbp+57h+var_60], r14
0x1800190c6  mov     rcx, [rbp+57h+var_70]
0x1800190ca  mov     rax, [rcx]
0x1800190cd  lea     rdx, [rbp+57h+var_60]
0x1800190d1  mov     rax, [rax+18h]
0x1800190d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190da  mov     edi, eax
0x1800190dc  test    eax, eax
0x1800190de  js      loc_180019401
0x1800190e4  mov     [rbp+57h+var_90], r14
0x1800190e8  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800190ec  lea     r8, [rbp+57h+var_90]; void **
0x1800190f0  mov     rcx, [rbp+57h+var_60]; struct IEnumUnknown *
0x1800190f4  call    ?SHNextObjectFromEnumUnknown@@YAJPEAUIEnumUnknown@@AEBU_GUID@@PEAPEAX@Z; SHNextObjectFromEnumUnknown(IEnumUnknown *,_GUID const &,void * *)
0x1800190f9  test    eax, eax
0x1800190fb  js      loc_1800193EB
0x180019101  mov     [rbp+57h+var_78], r14
0x180019105  xor     ecx, ecx; pv
0x180019107  call    cs:__imp_CoTaskMemFree
0x18001910d  lea     r8, [rbp+57h+var_78]
0x180019111  lea     rdx, PKEY_Identity_UserName
0x180019118  mov     rcx, [rbp+57h+var_90]
0x18001911c  call    IPropertyStore_GetString
0x180019121  mov     edi, eax
0x180019123  test    eax, eax
0x180019125  js      loc_1800193C4
0x18001912b  mov     rax, [rbp+57h+var_78]
0x18001912f  test    rax, rax
0x180019132  jz      loc_1800193C4
0x180019138  cmp     [rax], r14w
0x18001913c  jz      loc_1800193C4
0x180019142  mov     [rbp+57h+var_68], r14
0x180019146  xor     ecx, ecx; pv
0x180019148  call    cs:__imp_CoTaskMemFree
0x18001914e  lea     r8, [rbp+57h+var_68]
0x180019152  lea     rdx, PKEY_Identity_UserName
0x180019159  mov     rcx, [rbp+57h+var_90]
0x18001915d  call    IPropertyStore_GetString
0x180019162  mov     edi, eax
0x180019164  test    eax, eax
0x180019166  js      loc_1800193BA
0x18001916c  mov     [rbp+57h+pv], r14
0x180019170  xor     ecx, ecx; pv
0x180019172  call    cs:__imp_CoTaskMemFree
0x180019178  lea     r8, [rbp+57h+pv]
0x18001917c  lea     rdx, PKEY_Identity_PrimarySid
0x180019183  mov     rcx, [rbp+57h+var_90]
0x180019187  call    IPropertyStore_GetString
0x18001918c  test    eax, eax
0x18001918e  jns     short loc_1800191E7
0x180019190  mov     [rbp+57h+Sid], r14
0x180019194  mov     rcx, [rbp+57h+var_70]
0x180019198  mov     rax, [rcx]
0x18001919b  lea     r8, [rbp+57h+Sid]
0x18001919f  mov     rdx, [rbp+57h+var_78]
0x1800191a3  mov     rax, [rax+30h]
0x1800191a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191ac  mov     edi, eax
0x1800191ae  test    eax, eax
0x1800191b0  js      short loc_1800191D6
0x1800191b2  mov     rcx, [rbp+57h+pv]; pv
0x1800191b6  call    cs:__imp_CoTaskMemFree
0x1800191bc  lea     rdx, [rbp+57h+pv]; StringSid
0x1800191c0  mov     rcx, [rbp+57h+Sid]; Sid
0x1800191c4  call    cs:__imp_ConvertSidToStringSidW
0x1800191ca  neg     eax
0x1800191cc  sbb     edi, edi
0x1800191ce  not     edi
0x1800191d0  and     edi, 8007000Eh
0x1800191d6  lea     rcx, [rbp+57h+Sid]
0x1800191da  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800191df  test    edi, edi
0x1800191e1  js      loc_1800193AF
0x1800191e7  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x1800191eb  test    rcx, rcx
0x1800191ee  jz      loc_1800193B3
0x1800191f4  cmp     [rcx], r14w
0x1800191f8  jz      loc_1800193B3
0x1800191fe  call    ?IsUserAccountDisabled@@YA_NPEBG@Z; IsUserAccountDisabled(ushort const *)
0x180019203  test    al, al
0x180019205  jnz     loc_1800193AF
0x18001920b  mov     [rbp+57h+Sid], r14
0x18001920f  xor     ecx, ecx; pv
0x180019211  call    cs:__imp_CoTaskMemFree
0x180019217  lea     r8, [rbp+57h+Sid]
0x18001921b  lea     rdx, PKEY_Identity_DisplayName
0x180019222  mov     rcx, [rbp+57h+var_90]
0x180019226  call    IPropertyStore_GetString
0x18001922b  mov     rcx, [rbp+57h+Sid]; pv
0x18001922f  test    eax, eax
0x180019231  js      short loc_18001923E
0x180019233  test    rcx, rcx
0x180019236  jz      short loc_18001923E
0x180019238  cmp     [rcx], r14w
0x18001923c  jnz     short loc_180019258
0x18001923e  call    cs:__imp_CoTaskMemFree
0x180019244  lea     r8, [rbp+57h+Sid]
0x180019248  lea     rdx, PKEY_SAM_Name
0x18001924f  mov     rcx, [rbp+57h+var_90]
0x180019253  call    IPropertyStore_GetString
0x180019258  xorps   xmm0, xmm0
0x18001925b  movups  [rbp+57h+var_50], xmm0
0x18001925f  lea     r8, [rbp+57h+var_50]
0x180019263  mov     rcx, [rbp+57h+var_90]
0x180019267  call    IPropertyStore_GetCLSID
0x18001926c  test    eax, eax
0x18001926e  js      short loc_180019288
0x180019270  mov     rcx, [rbp+57h+var_70]
0x180019274  mov     rax, [rcx]
0x180019277  lea     r8, [rbp+57h+var_50]
0x18001927b  mov     rdx, [rbp+57h+var_78]
0x18001927f  mov     rax, [rax+40h]
0x180019283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019288  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001928f  mov     ecx, 68h ; 'h'; unsigned __int64
0x180019294  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019299  mov     rbx, rax
0x18001929c  mov     [rbp+57h+var_58], rax
0x1800192a0  test    rax, rax
0x1800192a3  jz      loc_1800193A0
0x1800192a9  mov     [rax], r14
0x1800192ac  mov     [rax+8], r14
0x1800192b0  mov     [rax+10h], r14
0x1800192b4  mov     [rax+18h], r14
0x1800192b8  mov     [rax+20h], r14
0x1800192bc  mov     [rax+28h], r14
0x1800192c0  mov     [rax+30h], r14
0x1800192c4  mov     [rax+38h], r14
0x1800192c8  mov     [rax+40h], r14
0x1800192cc  mov     [rax+48h], r14
0x1800192d0  mov     [rax+50h], r14
0x1800192d4  mov     [rax+58h], r14
0x1800192d8  mov     [rax+60h], r14b
0x1800192dc  test    rax, rax
0x1800192df  jz      loc_1800193A0
0x1800192e5  mov     byte ptr [rax+60h], 1
0x1800192e9  mov     rdi, [rbp+57h+var_78]
0x1800192ed  mov     [rbp+57h+var_78], r14
0x1800192f1  mov     rcx, [rax]; pv
0x1800192f4  test    rcx, rcx
0x1800192f7  jz      short loc_1800192FF
0x1800192f9  call    cs:__imp_CoTaskMemFree
0x1800192ff  mov     [rbx], rdi
0x180019302  mov     [rbx+10h], r15
0x180019306  mov     [rbx+8], r15
0x18001930a  mov     rdi, [rbp+57h+var_68]
0x18001930e  mov     [rbp+57h+var_68], r14
0x180019312  mov     rcx, [rbx+30h]; pv
0x180019316  test    rcx, rcx
0x180019319  jz      short loc_180019321
0x18001931b  call    cs:__imp_CoTaskMemFree
0x180019321  mov     [rbx+30h], rdi
0x180019325  mov     [rbx+40h], r15
0x180019329  mov     [rbx+38h], r15
0x18001932d  mov     rdi, [rbp+57h+pv]
0x180019331  mov     [rbp+57h+pv], r14
0x180019335  mov     rcx, [rbx+48h]; pv
0x180019339  test    rcx, rcx
0x18001933c  jz      short loc_180019344
0x18001933e  call    cs:__imp_CoTaskMemFree
0x180019344  mov     [rbx+48h], rdi
0x180019348  mov     [rbx+58h], r15
0x18001934c  mov     [rbx+50h], r15
0x180019350  mov     rdi, [rbp+57h+Sid]
0x180019354  test    rdi, rdi
0x180019357  jz      short loc_18001937E
0x180019359  cmp     [rdi], r14w
0x18001935d  jz      short loc_18001937E
0x18001935f  mov     [rbp+57h+Sid], r14
0x180019363  mov     rcx, [rbx+18h]; pv
0x180019367  test    rcx, rcx
0x18001936a  jz      short loc_180019372
0x18001936c  call    cs:__imp_CoTaskMemFree
0x180019372  mov     [rbx+18h], rdi
0x180019376  mov     [rbx+28h], r15
0x18001937a  mov     [rbx+20h], r15
0x18001937e  mov     rdx, rbx
0x180019381  mov     rcx, rsi
0x180019384  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x180019389  mov     edi, eax
0x18001938b  mov     rcx, r14
0x18001938e  test    eax, eax
0x180019390  cmovs   rcx, rbx; this
0x180019394  test    rcx, rcx
0x180019397  jz      short loc_1800193A5
0x180019399  call    ??_GCShareUserInfo@@QEAAPEAXI@Z; CShareUserInfo::`scalar deleting destructor'(uint)
0x18001939e  jmp     short loc_1800193A5
0x1800193a0  mov     edi, 8007000Eh
0x1800193a5  mov     rcx, [rbp+57h+Sid]; pv
0x1800193a9  call    cs:__imp_CoTaskMemFree
0x1800193af  mov     rcx, [rbp+57h+pv]; pv
0x1800193b3  call    cs:__imp_CoTaskMemFree
0x1800193b9  nop
0x1800193ba  mov     rcx, [rbp+57h+var_68]; pv
0x1800193be  call    cs:__imp_CoTaskMemFree
0x1800193c4  mov     rcx, [rbp+57h+var_90]
0x1800193c8  mov     [rbp+57h+var_90], r14
0x1800193cc  mov     rax, [rcx]
0x1800193cf  mov     rax, [rax+10h]
0x1800193d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193d8  nop
0x1800193d9  mov     rcx, [rbp+57h+var_78]; pv
0x1800193dd  call    cs:__imp_CoTaskMemFree
0x1800193e3  test    edi, edi
0x1800193e5  jns     loc_1800190EC
0x1800193eb  mov     rcx, [rbp+57h+var_90]
0x1800193ef  test    rcx, rcx
0x1800193f2  jz      short loc_180019401
0x1800193f4  mov     rax, [rcx]
0x1800193f7  mov     rax, [rax+10h]
0x1800193fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019400  nop
0x180019401  mov     rcx, [rbp+57h+var_60]
0x180019405  test    rcx, rcx
0x180019408  jz      short loc_180019417
0x18001940a  mov     rax, [rcx]
0x18001940d  mov     rax, [rax+10h]
0x180019411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019416  nop
0x180019417  mov     rcx, [rbp+57h+var_70]
0x18001941b  test    rcx, rcx
0x18001941e  jz      short loc_18001942D
0x180019420  mov     rax, [rcx]
0x180019423  mov     rax, [rax+10h]
0x180019427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001942c  nop
0x18001942d  mov     eax, edi
0x18001942f  mov     rcx, [rbp+57h+var_40]
0x180019433  xor     rcx, rsp; StackCookie
0x180019436  call    __security_check_cookie
0x18001943b  add     rsp, 98h
0x180019442  pop     r15
0x180019444  pop     r14
0x180019446  pop     rdi
0x180019447  pop     rsi
0x180019448  pop     rbx
0x180019449  pop     rbp
0x18001944a  retn
```
