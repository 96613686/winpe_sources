# CSubscription2::Load(IEventSystemTier2 *,tagPROPVARIANT * const,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagBLOB *)

- ea: `0x1800140c0`
- end: `0x1800145f8`
- name: `?Load@CSubscription2@@UEAAJPEAUIEventSystemTier2@@QEAUtagPROPVARIANT@@PEAU3@222PEAUtagBLOB@@@Z`
- size: `1336`
- prototype: `int(CSubscription2 *__hidden this, struct IEventSystemTier2 *, struct tagPROPVARIANT *const, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagBLOB *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180013cb8`
- `0x1800140c0`
- `0x180014600`
- `0x180015850`
- `0x18001c8f0`
- `0x18003efe8`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014539`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001454d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014558`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014563`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001456e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800443f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044405`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044412`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004441f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004442c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014539`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001454d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014558`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014563`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001456e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800443f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044405`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044412`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004441f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004442c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145e8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800143cc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800144d1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800143cc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800144d1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180014346`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180014346`

## pseudocode

```c
__int64 __fastcall CSubscription2::Load(
        CSubscription2 *this,
        struct IUnknown *a2,
        struct tagPROPVARIANT *const a3,
        PROPVARIANT *a4,
        PROPVARIANT *a5,
        PROPVARIANT *a6,
        PROPVARIANT *a7,
        struct tagBLOB *a8)
{
  int v11; // ebx
  __int64 result; // rax
  char v13; // r15
  HRESULT v14; // edi
  __int64 v15; // r9
  int v16; // r13d
  HRESULT v17; // eax
  int v18; // ebx
  __int64 i; // r13
  void *v20; // rcx
  LPVOID pv; // [rsp+38h] [rbp-210h] BYREF
  struct IUnknown *v22; // [rsp+40h] [rbp-208h] BYREF
  int v23; // [rsp+48h] [rbp-200h]
  HRESULT v24; // [rsp+4Ch] [rbp-1FCh]
  __int64 v25; // [rsp+50h] [rbp-1F8h] BYREF
  PROPVARIANT *pvar; // [rsp+58h] [rbp-1F0h]
  PROPVARIANT *v27; // [rsp+60h] [rbp-1E8h]
  PROPVARIANT *v28; // [rsp+68h] [rbp-1E0h]
  PROPVARIANT *v29; // [rsp+70h] [rbp-1D8h]
  CSubscription2 *v30; // [rsp+78h] [rbp-1D0h]
  struct tagPROPVARIANT *v31; // [rsp+80h] [rbp-1C8h]
  PROPVARIANT *v32; // [rsp+88h] [rbp-1C0h]
  PROPVARIANT *v33; // [rsp+90h] [rbp-1B8h]
  PROPVARIANT *v34; // [rsp+98h] [rbp-1B0h]
  PROPVARIANT *v35; // [rsp+A0h] [rbp-1A8h]
  struct tagPROPVARIANT v36; // [rsp+B0h] [rbp-198h] BYREF
  struct tagPROPVARIANT v37; // [rsp+D0h] [rbp-178h] BYREF
  struct tagPROPVARIANT v38; // [rsp+F0h] [rbp-158h] BYREF
  unsigned __int16 v39[120]; // [rsp+110h] [rbp-138h] BYREF

  pvar = a4;
  v30 = this;
  v31 = a3;
  v32 = a4;
  v27 = a5;
  v33 = a5;
  v28 = a6;
  v34 = a6;
  v29 = a7;
  v35 = a7;
  v11 = 0;
  v25 = 0;
  v22 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  *(_OWORD *)a4 = 0;
  a4[2] = 0;
  *(_OWORD *)a5 = 0;
  a5[2] = 0;
  *(_OWORD *)a6 = 0;
  a6[2] = 0;
  *(_OWORD *)a7 = 0;
  a7[2] = 0;
  *a8 = 0;
  if ( !a2 )
    return 2147500035LL;
  result = CheckInterfaceIsProcessLocal(a2);
  if ( (int)result >= 0 )
  {
    LODWORD(pv) = 1;
    v13 = 0;
    result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
               a2,
               &GUID_dc7c5ccc_34e1_4531_941d_035e29ff8257,
               &v25);
    v14 = result;
    if ( (int)result >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 96LL))(*((_QWORD *)this + 3));
      while ( 1 )
      {
        v23 = v11;
        if ( v11 >= 18 )
          break;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPVARIANT *))(**((_QWORD **)this + 3) + 24LL))(
                *((_QWORD *)this + 3),
                (unsigned int)v11,
                &a3[v11]);
        if ( v14 < 0 )
          break;
        ++v11;
      }
      if ( v14 >= 0 )
      {
        v36 = a3[17];
        v37 = a3[16];
        v38 = *a3;
        if ( (int)ConcatenateECID_PARTID_APPID(&v38, &v37, &v36, v15, v39) < 0 )
        {
          v14 = -2147160063;
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, PROPVARIANT *, PROPVARIANT *))(**((_QWORD **)this + 3)
                                                                                                 + 40LL))(
                  *((_QWORD *)this + 3),
                  L"PublisherProperties",
                  pvar,
                  v27);
          if ( v14 >= 0 )
          {
            v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, PROPVARIANT *, PROPVARIANT *))(**((_QWORD **)this + 3) + 40LL))(
                    *((_QWORD *)this + 3),
                    L"SubscriberProperties",
                    v28,
                    v29);
            if ( v14 >= 0 && !a3[5].vt && !a3[13].vt )
            {
              v17 = CoImpersonateClient();
              v14 = v17;
              v24 = v17;
              if ( v17 < 0 )
              {
                if ( v17 == -2147417833 )
                {
                  v13 = 0;
                  v14 = 0;
                  v24 = 0;
                }
              }
              else
              {
                v13 = 1;
              }
              if ( v14 >= 0 )
              {
                v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct IUnknown **))(*(_QWORD *)v25 + 48LL))(
                        v25,
                        v39,
                        &v22);
                if ( v14 )
                {
                  if ( v14 != -2147024891 )
                  {
                    v16 = (int)pv;
                    if ( v14 == 1 )
                      v16 = 0;
                    LODWORD(pv) = v16;
                    v14 = -2147160063;
                    goto LABEL_34;
                  }
                }
                else
                {
                  v14 = MarshalIUnknownIntoBlob(a8, v22);
                  ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
                  v22 = 0;
                  if ( v13 )
                  {
                    CoRevertToSelf();
                    v13 = 0;
                  }
                  if ( v14 == -2147023174 || v14 == -2147417848 || (unsigned int)(v14 + 2147023170) <= 1 )
                  {
                    ((void (__fastcall *)(struct IUnknown *, const wchar_t *))a2->lpVtbl[4].QueryInterface)(a2, L"ALL");
                    v14 = 0;
                  }
                  else if ( v14 < 0 )
                  {
                    LogMessage_HR(0x11u, 0xC000120E, v14, 1u, v39);
                  }
                }
              }
            }
          }
        }
      }
      v16 = (int)pv;
LABEL_34:
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 104LL))(*((_QWORD *)this + 3));
      if ( v22 )
        ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
      v18 = 0;
      if ( v14 < 0 )
      {
        for ( i = 0; i != 18; ++i )
          PropVariantClear((PROPVARIANT *)&a3[i]);
        PropVariantClear(pvar);
        PropVariantClear(v27);
        PropVariantClear(v28);
        PropVariantClear(v29);
        v16 = (int)pv;
        if ( v14 == -2147160063 )
          v18 = 1;
      }
      else
      {
        v14 = 0;
      }
      if ( v18 == 1 )
      {
        pv = 0;
        (*(void (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 3) + 64LL))(*((_QWORD *)this + 3), &pv);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 88LL))(*((_QWORD *)this + 3));
        v20 = pv;
        if ( pv )
        {
          if ( v16 )
          {
            LogMessage(0x11u, 0x8000110A, 1u, pv);
            v20 = pv;
          }
          CoTaskMemFree(v20);
        }
        v14 = -2147024894;
      }
      if ( v13 )
        CoRevertToSelf();
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      return (unsigned int)v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800140c0  push    rbx
0x1800140c2  push    rsi
0x1800140c3  push    rdi
0x1800140c4  push    r12
0x1800140c6  push    r13
0x1800140c8  push    r14
0x1800140ca  push    r15
0x1800140cc  sub     rsp, 210h
0x1800140d3  mov     rax, cs:__security_cookie
0x1800140da  xor     rax, rsp
0x1800140dd  mov     [rsp+248h+var_48], rax
0x1800140e5  mov     rax, r9
0x1800140e8  mov     [rsp+248h+pvar], rax
0x1800140ed  mov     r14, r8
0x1800140f0  mov     r12, rdx
0x1800140f3  mov     rsi, rcx
0x1800140f6  mov     [rsp+248h+var_1D0], rcx
0x1800140fb  mov     [rsp+248h+var_1C8], r8
0x180014103  mov     [rsp+248h+var_1C0], rax
0x18001410b  mov     rcx, [rsp+248h+arg_20]
0x180014113  mov     [rsp+248h+var_1E8], rcx
0x180014118  mov     [rsp+248h+var_1B8], rcx
0x180014120  mov     rdx, [rsp+248h+arg_28]
0x180014128  mov     [rsp+248h+var_1E0], rdx
0x18001412d  mov     [rsp+248h+var_1B0], rdx
0x180014135  mov     r8, [rsp+248h+arg_30]
0x18001413d  mov     [rsp+248h+var_1D8], r8
0x180014142  mov     [rsp+248h+var_1A8], r8
0x18001414a  mov     r13, [rsp+248h+arg_38]
0x180014152  xor     ebx, ebx
0x180014154  mov     [rsp+248h+var_1F8], rbx
0x180014159  mov     [rsp+248h+var_208], rbx
0x18001415e  xorps   xmm0, xmm0
0x180014161  xor     r9d, r9d
0x180014164  movups  xmmword ptr [r14], xmm0
0x180014168  mov     [r14+10h], r9
0x18001416c  xorps   xmm1, xmm1
0x18001416f  movups  xmmword ptr [rax], xmm1
0x180014172  mov     [rax+10h], r9
0x180014176  xor     eax, eax
0x180014178  movups  xmmword ptr [rcx], xmm0
0x18001417b  mov     [rcx+10h], rax
0x18001417f  movups  xmmword ptr [rdx], xmm1
0x180014182  mov     [rdx+10h], rax
0x180014186  movups  xmmword ptr [r8], xmm0
0x18001418a  mov     [r8+10h], rax
0x18001418e  movups  xmmword ptr [r13+0], xmm0
0x180014193  test    r12, r12
0x180014196  jz      loc_180014512
0x18001419c  mov     rcx, r12; struct IUnknown *
0x18001419f  call    ?CheckInterfaceIsProcessLocal@@YAJPEAUIUnknown@@@Z; CheckInterfaceIsProcessLocal(IUnknown *)
0x1800141a4  test    eax, eax
0x1800141a6  js      loc_1800144EF
0x1800141ac  mov     dword ptr [rsp+248h+pv], 1
0x1800141b4  xor     r15b, r15b
0x1800141b7  mov     rax, [r12]
0x1800141bb  lea     r8, [rsp+248h+var_1F8]
0x1800141c0  lea     rdx, _GUID_dc7c5ccc_34e1_4531_941d_035e29ff8257
0x1800141c7  mov     rcx, r12
0x1800141ca  mov     rax, [rax]
0x1800141cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141d2  mov     edi, eax
0x1800141d4  mov     [rsp+248h+var_218], eax
0x1800141d8  test    eax, eax
0x1800141da  js      loc_1800144EF
0x1800141e0  mov     rcx, [rsi+18h]
0x1800141e4  mov     rax, [rcx]
0x1800141e7  mov     rax, [rax+60h]
0x1800141eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141f0  mov     [rsp+248h+var_200], ebx
0x1800141f4  cmp     ebx, 12h
0x1800141f7  jge     short loc_180014224
0x1800141f9  mov     rcx, [rsi+18h]
0x1800141fd  mov     r9, [rcx]
0x180014200  movsxd  rax, ebx
0x180014203  lea     rdx, [rax+rax*2]
0x180014207  lea     r8, [r14+rdx*8]
0x18001420b  mov     edx, ebx
0x18001420d  mov     rax, [r9+18h]
0x180014211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014216  mov     edi, eax
0x180014218  mov     [rsp+248h+var_218], eax
0x18001421c  test    eax, eax
0x18001421e  js      short loc_180014224
0x180014220  inc     ebx
0x180014222  jmp     short loc_1800141F0
0x180014224  test    edi, edi
0x180014226  jns     short loc_180014238
0x180014228  mov     r12d, 11h
0x18001422e  mov     r13d, dword ptr [rsp+248h+pv]
0x180014233  jmp     loc_1800144A1
0x180014238  movups  xmm0, xmmword ptr [r14+198h]
0x180014240  movaps  xmmword ptr [rsp+248h+var_198], xmm0
0x180014248  movsd   xmm1, qword ptr [r14+1A8h]
0x180014251  movsd   qword ptr [rsp+248h+var_198+10h], xmm1
0x18001425a  movups  xmm0, xmmword ptr [r14+180h]
0x180014262  movaps  xmmword ptr [rsp+248h+var_178], xmm0
0x18001426a  movsd   xmm1, qword ptr [r14+190h]
0x180014273  movsd   qword ptr [rsp+248h+var_178+10h], xmm1
0x18001427c  movups  xmm0, xmmword ptr [r14]
0x180014280  movaps  xmmword ptr [rsp+248h+var_158], xmm0
0x180014288  movsd   xmm1, qword ptr [r14+10h]
0x18001428e  movsd   qword ptr [rsp+248h+var_158+10h], xmm1
0x180014297  lea     rax, [rsp+248h+var_138]
0x18001429f  mov     [rsp+248h+var_228], rax; unsigned __int16 *
0x1800142a4  lea     r8, [rsp+248h+var_198]; struct tagPROPVARIANT *
0x1800142ac  lea     rdx, [rsp+248h+var_178]; struct tagPROPVARIANT *
0x1800142b4  lea     rcx, [rsp+248h+var_158]; struct tagPROPVARIANT *
0x1800142bc  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x1800142c1  mov     [rsp+248h+var_218], eax
0x1800142c5  test    eax, eax
0x1800142c7  js      loc_180014481
0x1800142cd  mov     rcx, [rsi+18h]
0x1800142d1  mov     rax, [rcx]
0x1800142d4  mov     r9, [rsp+248h+var_1E8]
0x1800142d9  mov     r8, [rsp+248h+pvar]
0x1800142de  lea     rdx, aPublisherprope; "PublisherProperties"
0x1800142e5  mov     rax, [rax+28h]
0x1800142e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ee  mov     edi, eax
0x1800142f0  mov     [rsp+248h+var_218], eax
0x1800142f4  test    eax, eax
0x1800142f6  js      loc_180014228
0x1800142fc  mov     rcx, [rsi+18h]
0x180014300  mov     rax, [rcx]
0x180014303  mov     r9, [rsp+248h+var_1D8]
0x180014308  mov     r8, [rsp+248h+var_1E0]
0x18001430d  lea     rdx, aSubscriberprop; "SubscriberProperties"
0x180014314  mov     rax, [rax+28h]
0x180014318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431d  mov     edi, eax
0x18001431f  mov     [rsp+248h+var_218], eax
0x180014323  test    eax, eax
0x180014325  js      loc_180014228
0x18001432b  cmp     word ptr [r14+78h], 0
0x180014331  jnz     loc_180014228
0x180014337  cmp     word ptr [r14+138h], 0
0x180014340  jnz     loc_180014228
0x180014346  call    cs:__imp_CoImpersonateClient
0x18001434c  mov     edi, eax
0x18001434e  mov     [rsp+248h+var_1FC], eax
0x180014352  test    eax, eax
0x180014354  js      loc_180014488
0x18001435a  mov     r15b, 1
0x18001435d  mov     [rsp+248h+var_214], r15b
0x180014362  mov     [rsp+248h+var_218], edi
0x180014366  test    edi, edi
0x180014368  js      loc_180014228
0x18001436e  mov     rcx, [rsp+248h+var_1F8]
0x180014373  mov     rax, [rcx]
0x180014376  lea     r8, [rsp+248h+var_208]
0x18001437b  lea     rdx, [rsp+248h+var_138]
0x180014383  mov     rax, [rax+30h]
0x180014387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001438c  mov     edi, eax
0x18001438e  mov     [rsp+248h+var_218], eax
0x180014392  test    eax, eax
0x180014394  jnz     loc_18001442B
0x18001439a  mov     rdx, [rsp+248h+var_208]; struct IUnknown *
0x18001439f  mov     rcx, r13; struct tagBLOB *
0x1800143a2  call    ?MarshalIUnknownIntoBlob@@YAJAEAUtagBLOB@@PEAUIUnknown@@KK@Z; MarshalIUnknownIntoBlob(tagBLOB &,IUnknown *,ulong,ulong)
0x1800143a7  mov     edi, eax
0x1800143a9  mov     [rsp+248h+var_218], eax
0x1800143ad  mov     rcx, [rsp+248h+var_208]
0x1800143b2  mov     rax, [rcx]
0x1800143b5  mov     rax, [rax+10h]
0x1800143b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143be  mov     [rsp+248h+var_208], 0
0x1800143c7  test    r15b, r15b
0x1800143ca  jz      short loc_1800143DA
0x1800143cc  call    cs:__imp_CoRevertToSelf
0x1800143d2  xor     r15b, r15b
0x1800143d5  mov     [rsp+248h+var_214], r15b
0x1800143da  cmp     edi, 800706BAh
0x1800143e0  jz      short loc_18001445B
0x1800143e2  cmp     edi, 80010108h
0x1800143e8  jz      short loc_18001445B
0x1800143ea  lea     eax, [rdi+7FF8F942h]
0x1800143f0  cmp     eax, 1
0x1800143f3  jbe     short loc_18001445B
0x1800143f5  test    edi, edi
0x1800143f7  jns     loc_180014228
0x1800143fd  mov     r12d, 11h
0x180014403  lea     rax, [rsp+248h+var_138]
0x18001440b  mov     [rsp+248h+var_228], rax
0x180014410  mov     r9d, 1; unsigned int
0x180014416  mov     r8d, edi; int
0x180014419  mov     edx, 0C000120Eh; unsigned int
0x18001441e  mov     ecx, r12d; unsigned __int16
0x180014421  call    ?LogMessage_HR@@YAXGKJKZZ; LogMessage_HR(ushort,ulong,long,ulong,...)
0x180014426  jmp     loc_18001422E
0x18001442b  cmp     edi, 80070005h
0x180014431  jz      loc_180014228
0x180014437  mov     r13d, dword ptr [rsp+248h+pv]
0x18001443c  xor     eax, eax
0x18001443e  cmp     edi, 1
0x180014441  cmovz   r13d, eax
0x180014445  mov     dword ptr [rsp+248h+pv], r13d
0x18001444a  mov     edi, 8004F001h
0x18001444f  mov     [rsp+248h+var_218], edi
0x180014453  mov     r12d, 11h
0x180014459  jmp     short loc_1800144A1
0x18001445b  mov     rax, [r12]
0x18001445f  lea     rdx, aAll; "ALL"
0x180014466  mov     rcx, r12
0x180014469  mov     rax, [rax+60h]
0x18001446d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014472  mov     [rsp+248h+var_218], eax
0x180014476  xor     edi, edi
0x180014478  mov     [rsp+248h+var_218], edi
0x18001447c  jmp     loc_180014228
0x180014481  mov     edi, 8004F001h
0x180014486  jmp     short loc_180014478
0x180014488  cmp     eax, 80010117h
0x18001448d  jnz     loc_180014362
0x180014493  xor     r15b, r15b
0x180014496  xor     edi, edi
0x180014498  mov     [rsp+248h+var_1FC], edi
0x18001449c  jmp     loc_18001435D
0x1800144a1  mov     rcx, [rsi+18h]
0x1800144a5  mov     rax, [rcx]
0x1800144a8  mov     rax, [rax+68h]
0x1800144ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144b1  mov     rcx, [rsp+248h+var_208]
0x1800144b6  test    rcx, rcx
0x1800144b9  jnz     short loc_180014519
0x1800144bb  xor     ebx, ebx
0x1800144bd  test    edi, edi
0x1800144bf  js      short loc_180014527
0x1800144c1  xor     edi, edi
0x1800144c3  cmp     ebx, 1
0x1800144c6  jz      loc_18001458F
0x1800144cc  test    r15b, r15b
0x1800144cf  jz      short loc_1800144D7
0x1800144d1  call    cs:__imp_CoRevertToSelf
0x1800144d7  mov     rcx, [rsp+248h+var_1F8]
0x1800144dc  test    rcx, rcx
0x1800144df  jz      short loc_1800144ED
0x1800144e1  mov     rax, [rcx]
0x1800144e4  mov     rax, [rax+10h]
0x1800144e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ed  mov     eax, edi
0x1800144ef  mov     rcx, [rsp+248h+var_48]
0x1800144f7  xor     rcx, rsp; StackCookie
0x1800144fa  call    __security_check_cookie
0x1800144ff  add     rsp, 210h
0x180014506  pop     r15
0x180014508  pop     r14
0x18001450a  pop     r13
0x18001450c  pop     r12
0x18001450e  pop     rdi
0x18001450f  pop     rsi
0x180014510  pop     rbx
0x180014511  retn
0x180014512  mov     eax, 80004003h
0x180014517  jmp     short loc_1800144EF
0x180014519  mov     rax, [rcx]
0x18001451c  mov     rax, [rax+10h]
0x180014520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014525  jmp     short loc_1800144BB
0x180014527  xor     r13d, r13d
0x18001452a  lea     rax, ds:0[r13*2]
0x180014532  add     rax, r13
0x180014535  lea     rcx, [r14+rax*8]; pvar
0x180014539  call    cs:__imp_PropVariantClear
0x18001453f  inc     r13
0x180014542  cmp     r13, 12h
0x180014546  jnz     short loc_18001452A
0x180014548  mov     rcx, [rsp+248h+pvar]; pvar
0x18001454d  call    cs:__imp_PropVariantClear
0x180014553  mov     rcx, [rsp+248h+var_1E8]; pvar
0x180014558  call    cs:__imp_PropVariantClear
0x18001455e  mov     rcx, [rsp+248h+var_1E0]; pvar
0x180014563  call    cs:__imp_PropVariantClear
0x180014569  mov     rcx, [rsp+248h+var_1D8]; pvar
0x18001456e  call    cs:__imp_PropVariantClear
0x180014574  mov     r13d, dword ptr [rsp+248h+pv]
0x180014579  cmp     edi, 8004F001h
0x18001457f  jnz     loc_1800144C3
0x180014585  mov     ebx, 1
0x18001458a  jmp     loc_1800144C3
0x18001458f  mov     [rsp+248h+pv], 0
0x180014598  mov     rcx, [rsi+18h]
0x18001459c  mov     rax, [rcx]
0x18001459f  lea     rdx, [rsp+248h+pv]
0x1800145a4  mov     rax, [rax+40h]
0x1800145a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145ad  mov     rcx, [rsi+18h]
0x1800145b1  mov     rax, [rcx]
0x1800145b4  mov     rax, [rax+58h]
0x1800145b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145bd  mov     rcx, [rsp+248h+pv]
0x1800145c2  test    rcx, rcx
0x1800145c5  jz      short loc_1800145EE
0x1800145c7  test    r13d, r13d
0x1800145ca  jz      short loc_1800145E8
0x1800145cc  mov     r9, rcx
0x1800145cf  mov     edx, 8000110Ah; unsigned int
0x1800145d4  mov     r8d, 1; unsigned int
0x1800145da  movzx   ecx, r12w; unsigned __int16
  ... truncated ...
```
