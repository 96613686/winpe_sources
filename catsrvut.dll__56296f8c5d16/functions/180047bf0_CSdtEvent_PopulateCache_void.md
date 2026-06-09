# CSdtEvent::PopulateCache(void)

- ea: `0x180047bf0`
- end: `0x1800481d4`
- name: `?PopulateCache@CSdtEvent@@UEAAJXZ`
- size: `1508`
- prototype: `__int64 __fastcall(CSdtEvent *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180044ab0`
- `0x180044b50`
- `0x180044c94`
- `0x180047bf0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180047cd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180047cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047d8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047f89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047d8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047f89`
- `OLEAUT32!__imp_SysAllocString` at `0x180047e06`
- `OLEAUT32!__imp_SysAllocString` at `0x180047e2c`
- `OLEAUT32!__imp_SysAllocString` at `0x180047e06`
- `OLEAUT32!__imp_SysAllocString` at `0x180047e2c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800481ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800481b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005693d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005694a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800481ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800481b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005693d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005694a`

## pseudocode

```c
__int64 __fastcall CSdtEvent::PopulateCache(CSdtEvent *this)
{
  IUnknown *pItf; // r13
  __int64 v3; // r12
  OLECHAR *v4; // r15
  SubscriptionLoader *v5; // rsi
  COSERVERINFO *v6; // r9
  DWORD v7; // r8d
  HRESULT hr; // ebx
  int v9; // eax
  EventClassLoader *v10; // rax
  const OLECHAR *v11; // rcx
  SubscriptionLoader *v12; // rax
  __int64 v13; // rcx
  OLECHAR *v14; // rcx
  __int64 *v15; // r13
  __int64 *v16; // r12
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  LPVOID v21; // r10
  BOOL v22; // eax
  char v24; // [rsp+44h] [rbp-D4h]
  __int64 v25; // [rsp+48h] [rbp-D0h] BYREF
  IUnknown *v26; // [rsp+50h] [rbp-C8h]
  __int64 v27; // [rsp+58h] [rbp-C0h]
  SubscriptionLoader *v28; // [rsp+60h] [rbp-B8h]
  __int64 v29; // [rsp+68h] [rbp-B0h] BYREF
  OLECHAR *v30; // [rsp+70h] [rbp-A8h]
  __int64 v31; // [rsp+78h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-98h]
  MULTI_QI pResults; // [rsp+88h] [rbp-90h] BYREF
  GUID *v34; // [rsp+A0h] [rbp-78h]
  __int128 v35; // [rsp+A8h] [rbp-70h]
  __int128 v36; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v37; // [rsp+C8h] [rbp-50h]
  int v38; // [rsp+128h] [rbp+10h] BYREF
  int v39; // [rsp+130h] [rbp+18h] BYREF
  __int64 v40; // [rsp+138h] [rbp+20h] BYREF

  pItf = 0;
  v26 = 0;
  v3 = 0;
  v27 = 0;
  v40 = 0;
  v25 = 0;
  v29 = 0;
  v4 = 0;
  v30 = 0;
  v5 = 0;
  v28 = 0;
  v24 = 0;
  v36 = 0;
  v37 = 0;
  v6 = 0;
  v7 = 23;
  bstrString = 0;
  if ( *((_QWORD *)this + 10) )
  {
    *((_QWORD *)&v36 + 1) = *((_QWORD *)this + 10);
    *(_QWORD *)&v37 = 0;
    LODWORD(v36) = 0;
    DWORD2(v37) = 0;
    v6 = (COSERVERINFO *)&v36;
    v7 = 16;
  }
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v35 = 0;
  pResults.pIID = &IID_IEventSystem;
  v34 = &IID_IEventSystemInitialize;
  hr = CoCreateInstanceEx(&CLSID_CEventSystem, 0, v7, v6, 2u, &pResults);
  if ( hr >= 0 && pResults.hr >= 0 && (SDWORD2(v35) & 0x80000000) == 0 )
  {
    pItf = pResults.pItf;
    v26 = pResults.pItf;
    v3 = v35;
    v27 = v35;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v35 + 24LL))(v35, 1);
    v9 = *((_DWORD *)this + 12);
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        v12 = (SubscriptionLoader *)CoTaskMemAlloc(0x28u);
        if ( v12 )
        {
          v13 = *((_QWORD *)this + 11) - tidTRANSIENTSUBSCRIPTIONS;
          if ( !v13 )
            v13 = *((_QWORD *)this + 12) - 0x432C75F800021B1LL;
          v5 = SubscriptionLoader::SubscriptionLoader(
                 v12,
                 *((struct ISimpleTableWrite **)this + 4),
                 *((struct ISimpleTableControl **)this + 5),
                 v13 == 0,
                 *((_DWORD *)this + 27));
        }
        else
        {
          v5 = 0;
        }
        v28 = v5;
        if ( !v5 )
          goto LABEL_11;
        v11 = L"EventSystem.EventSubscriptionCollection";
      }
      else
      {
        if ( (unsigned int)(v9 - 2) > 1 )
        {
          hr = -2147418113;
          goto LABEL_63;
        }
        v11 = L"EventSystem.EventSubscription";
      }
    }
    else
    {
      v10 = (EventClassLoader *)CoTaskMemAlloc(0x20u);
      if ( v10 )
        v5 = EventClassLoader::EventClassLoader(
               v10,
               *((struct ISimpleTableWrite **)this + 4),
               *((struct ISimpleTableControl **)this + 5),
               *((_DWORD *)this + 27));
      else
        v5 = 0;
      v28 = v5;
      if ( !v5 )
        goto LABEL_11;
      v11 = L"EventSystem.EventClassCollection";
    }
    v4 = SysAllocString(v11);
    v30 = v4;
    if ( !v4 || (v39 = -1, v14 = SysAllocString(*((const OLECHAR **)this + 7)), (bstrString = v14) == 0) )
    {
LABEL_11:
      hr = -2147024882;
      goto LABEL_63;
    }
    hr = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, OLECHAR *, int *, __int64 *))pItf->lpVtbl[2].AddRef)(
           pItf,
           v4,
           v14,
           &v39,
           &v40);
    if ( hr >= 0 )
    {
      hr = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5), 0);
      if ( hr >= 0 )
      {
        v24 = 1;
        if ( (unsigned int)(*((_DWORD *)this + 12) - 2) <= 1 )
        {
          if ( v40 )
          {
            v15 = (__int64 *)((char *)this + 64);
            hr = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v40)(
                   v40,
                   &IID_IEventSubscription2,
                   (char *)this + 64);
            if ( hr < 0 )
              goto LABEL_50;
            v16 = (__int64 *)((char *)this + 72);
            v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v40)(
                    v40,
                    &IID_IEventSubscription3,
                    (char *)this + 72);
            hr = v17;
            if ( v17 < 0 )
            {
              if ( v17 != -2147467262 )
                goto LABEL_50;
              *v16 = 0;
            }
            v18 = (_QWORD *)*v15;
            v19 = *(_QWORD *)*v15;
            if ( *((_DWORD *)this + 12) == 2 )
              v20 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v19 + 272))(v18, &v25);
            else
              v20 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v19 + 304))(v18, &v25);
            hr = v20;
            if ( v20 < 0 )
              goto LABEL_50;
            v21 = CoTaskMemAlloc(0x40u);
            if ( v21 )
            {
              v22 = *((_QWORD *)this + 11) == tidTRANSIENTSUBSCRIBERPROPERTIES
                 && *((_QWORD *)this + 12) == 0x432C75F800023B1LL
                 || *((_QWORD *)this + 11) == tidTRANSIENTPUBLISHERPROPERTIES
                 && *((_QWORD *)this + 12) == 0x432C75F800023B1LL;
              v5 = (SubscriptionLoader *)PropertyLoader::PropertyLoader(
                                           (__int64)v21,
                                           *((struct ISimpleTableWrite **)this + 4),
                                           *((struct ISimpleTableControl **)this + 5),
                                           *((_DWORD *)this + 12),
                                           *v15,
                                           *v16,
                                           v22,
                                           *((_DWORD *)this + 27));
            }
            else
            {
              v5 = 0;
            }
            v28 = v5;
            if ( !v5 )
            {
              hr = -2147024882;
              goto LABEL_50;
            }
            v3 = v27;
            pItf = v26;
          }
        }
        else
        {
          hr = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v40)(v40, &IID_IEventObjectCollection, &v25);
        }
        if ( !v25 )
          goto LABEL_63;
        hr = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 72LL))(v25, &v29);
        if ( hr >= 0 )
        {
          while ( 1 )
          {
            v31 = 0;
            v38 = 1;
            if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v29 + 32LL))(
                   v29,
                   1,
                   &v31,
                   &v38) == 1
              || v38 != 1 )
            {
              break;
            }
            (*(void (__fastcall **)(SubscriptionLoader *, __int64))(*(_QWORD *)v5 + 8LL))(v5, v31);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          }
          hr = 0;
          goto LABEL_63;
        }
      }
    }
LABEL_50:
    v3 = v27;
    pItf = v26;
    goto LABEL_63;
  }
  if ( hr >= 0 )
  {
    if ( pResults.hr >= 0 )
    {
      if ( SDWORD2(v35) < 0 )
        hr = DWORD2(v35);
    }
    else
    {
      hr = pResults.hr;
    }
  }
LABEL_63:
  if ( v24 )
  {
    hr = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5));
    if ( hr >= 0 )
      *((_DWORD *)this + 26) = 1;
  }
  if ( v5 )
    (**(void (__fastcall ***)(SubscriptionLoader *, __int64))v5)(v5, 1);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( pItf )
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  SysFreeString(v4);
  SysFreeString(bstrString);
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x180047bf0  mov     r11, rsp
0x180047bf3  mov     [r11+8], rcx
0x180047bf7  push    rbx
0x180047bf8  push    rsi
0x180047bf9  push    rdi
0x180047bfa  push    r12
0x180047bfc  push    r13
0x180047bfe  push    r14
0x180047c00  push    r15
0x180047c02  sub     rsp, 0E0h
0x180047c09  mov     rdi, rcx
0x180047c0c  xor     r14d, r14d
0x180047c0f  mov     r13d, r14d
0x180047c12  mov     [rsp+118h+var_C8], r14
0x180047c17  mov     r12d, r14d
0x180047c1a  mov     [rsp+118h+var_C0], r14
0x180047c1f  mov     [r11+20h], r14
0x180047c23  mov     [rsp+118h+var_D0], r14
0x180047c28  mov     [rsp+118h+var_B0], r14
0x180047c2d  mov     r15d, r14d
0x180047c30  mov     [rsp+118h+var_A8], r14
0x180047c35  mov     esi, r14d
0x180047c38  mov     [rsp+118h+var_B8], r14
0x180047c3d  mov     [rsp+118h+var_D4], r14b
0x180047c42  xorps   xmm0, xmm0
0x180047c45  movups  xmmword ptr [r11-60h], xmm0
0x180047c4a  movups  xmmword ptr [r11-50h], xmm0
0x180047c4f  mov     r9d, r14d
0x180047c52  lea     r8d, [r14+17h]
0x180047c56  mov     [r11-98h], r14
0x180047c5d  mov     rax, [rcx+50h]
0x180047c61  test    rax, rax
0x180047c64  jz      short loc_180047C7E
0x180047c66  mov     [r11-58h], rax
0x180047c6a  mov     [r11-50h], r14
0x180047c6e  mov     [r11-60h], r14d
0x180047c72  mov     [r11-48h], r14d
0x180047c76  lea     r9, [r11-60h]; pServerInfo
0x180047c7a  lea     r8d, [r14+10h]; dwClsCtx
0x180047c7e  movups  xmmword ptr [rsp+118h+var_90.pIID], xmm0
0x180047c86  movups  xmmword ptr [rsp+118h+var_90.hr], xmm0
0x180047c8e  movups  [rsp+118h+var_70], xmm0
0x180047c96  lea     rax, IID_IEventSystem
0x180047c9d  mov     [rsp+118h+var_90.pIID], rax
0x180047ca5  lea     rax, IID_IEventSystemInitialize
0x180047cac  mov     [rsp+118h+var_78], rax
0x180047cb4  lea     rax, [rsp+118h+var_90]
0x180047cbc  mov     [rsp+118h+pResults], rax; pResults
0x180047cc1  mov     [rsp+118h+dwCount], 2; dwCount
0x180047cc9  xor     edx, edx; punkOuter
0x180047ccb  lea     rcx, CLSID_CEventSystem; Clsid
0x180047cd2  call    cs:__imp_CoCreateInstanceEx
0x180047cd8  mov     ebx, eax
0x180047cda  mov     [rsp+118h+var_D8], eax
0x180047cde  test    eax, eax
0x180047ce0  js      loc_1800480D7
0x180047ce6  cmp     [rsp+118h+var_90.hr], r14d
0x180047cee  jl      loc_1800480D7
0x180047cf4  cmp     dword ptr [rsp+118h+var_70+8], r14d
0x180047cfc  jl      loc_1800480D7
0x180047d02  mov     r13, [rsp+118h+var_90.pItf]
0x180047d0a  mov     [rsp+118h+var_C8], r13
0x180047d0f  mov     r12, qword ptr [rsp+118h+var_70]
0x180047d17  mov     [rsp+118h+var_C0], r12
0x180047d1c  mov     rax, [r12]
0x180047d20  mov     r14d, 1
0x180047d26  mov     edx, r14d
0x180047d29  mov     rcx, r12
0x180047d2c  mov     rax, [rax+18h]
0x180047d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d35  mov     eax, [rdi+30h]
0x180047d38  test    eax, eax
0x180047d3a  jnz     short loc_180047D85
0x180047d3c  lea     ecx, [rax+20h]; cb
0x180047d3f  call    cs:__imp_CoTaskMemAlloc
0x180047d45  test    rax, rax
0x180047d48  jz      short loc_180047D63
0x180047d4a  mov     r9d, [rdi+6Ch]; int
0x180047d4e  mov     r8, [rdi+28h]; struct ISimpleTableControl *
0x180047d52  mov     rdx, [rdi+20h]; struct ISimpleTableWrite *
0x180047d56  mov     rcx, rax; this
0x180047d59  call    ??0EventClassLoader@@QEAA@PEAUISimpleTableWrite@@PEAUISimpleTableControl@@H@Z; EventClassLoader::EventClassLoader(ISimpleTableWrite *,ISimpleTableControl *,int)
0x180047d5e  mov     rsi, rax
0x180047d61  jmp     short loc_180047D65
0x180047d63  xor     esi, esi
0x180047d65  mov     [rsp+118h+var_B8], rsi
0x180047d6a  test    rsi, rsi
0x180047d6d  jnz     short loc_180047D79
0x180047d6f  mov     ebx, 8007000Eh
0x180047d74  jmp     loc_1800480D1
0x180047d79  lea     rcx, aEventsystemEve_1; "EventSystem.EventClassCollection"
0x180047d80  jmp     loc_180047E06
0x180047d85  cmp     eax, r14d
0x180047d88  jnz     short loc_180047DED
0x180047d8a  mov     ecx, 28h ; '('; cb
0x180047d8f  call    cs:__imp_CoTaskMemAlloc
0x180047d95  test    rax, rax
0x180047d98  jz      short loc_180047DD8
0x180047d9a  mov     edx, [rdi+6Ch]
0x180047d9d  mov     rcx, [rdi+58h]
0x180047da1  sub     rcx, cs:tidTRANSIENTSUBSCRIPTIONS
0x180047da8  jnz     short loc_180047DB5
0x180047daa  mov     rcx, [rdi+60h]
0x180047dae  sub     rcx, cs:qword_180061388
0x180047db5  xor     r9d, r9d
0x180047db8  test    rcx, rcx
0x180047dbb  setz    r9b; int
0x180047dbf  mov     [rsp+118h+dwCount], edx; int
0x180047dc3  mov     r8, [rdi+28h]; struct ISimpleTableControl *
0x180047dc7  mov     rdx, [rdi+20h]; struct ISimpleTableWrite *
0x180047dcb  mov     rcx, rax; this
0x180047dce  call    ??0SubscriptionLoader@@QEAA@PEAUISimpleTableWrite@@PEAUISimpleTableControl@@HH@Z; SubscriptionLoader::SubscriptionLoader(ISimpleTableWrite *,ISimpleTableControl *,int,int)
0x180047dd3  mov     rsi, rax
0x180047dd6  jmp     short loc_180047DDA
0x180047dd8  xor     esi, esi
0x180047dda  mov     [rsp+118h+var_B8], rsi
0x180047ddf  test    rsi, rsi
0x180047de2  jz      short loc_180047D6F
0x180047de4  lea     rcx, aEventsystemEve; "EventSystem.EventSubscriptionCollection"
0x180047deb  jmp     short loc_180047E06
0x180047ded  add     eax, 0FFFFFFFEh
0x180047df0  cmp     eax, r14d
0x180047df3  jbe     short loc_180047DFF
0x180047df5  mov     ebx, 8000FFFFh
0x180047dfa  jmp     loc_1800480D1
0x180047dff  lea     rcx, aEventsystemEve_2; "EventSystem.EventSubscription"
0x180047e06  call    cs:__imp_SysAllocString
0x180047e0c  mov     r15, rax
0x180047e0f  mov     [rsp+118h+var_A8], rax
0x180047e14  test    rax, rax
0x180047e17  jz      loc_180047D6F
0x180047e1d  mov     [rsp+118h+arg_10], 0FFFFFFFFh
0x180047e28  mov     rcx, [rdi+38h]; psz
0x180047e2c  call    cs:__imp_SysAllocString
0x180047e32  mov     rcx, rax
0x180047e35  mov     [rsp+118h+bstrString], rax
0x180047e3d  test    rax, rax
0x180047e40  jz      loc_180047D6F
0x180047e46  mov     rax, [r13+0]
0x180047e4a  lea     rdx, [rsp+118h+arg_18]
0x180047e52  mov     qword ptr [rsp+118h+dwCount], rdx
0x180047e57  lea     r9, [rsp+118h+arg_10]
0x180047e5f  mov     r8, rcx
0x180047e62  mov     rdx, r15
0x180047e65  mov     rcx, r13
0x180047e68  mov     rax, [rax+38h]
0x180047e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e71  mov     ebx, eax
0x180047e73  mov     [rsp+118h+var_D8], eax
0x180047e77  test    eax, eax
0x180047e79  js      loc_18004801D
0x180047e7f  mov     rcx, [rdi+28h]
0x180047e83  mov     rax, [rcx]
0x180047e86  xor     edx, edx
0x180047e88  mov     rax, [rax+20h]
0x180047e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e91  mov     ebx, eax
0x180047e93  mov     [rsp+118h+var_D8], eax
0x180047e97  test    eax, eax
0x180047e99  js      loc_18004801D
0x180047e9f  mov     [rsp+118h+var_D4], r14b
0x180047ea4  mov     eax, [rdi+30h]
0x180047ea7  sub     eax, 2
0x180047eaa  mov     rcx, [rsp+118h+arg_18]
0x180047eb2  cmp     eax, r14d
0x180047eb5  jbe     short loc_180047ED9
0x180047eb7  mov     rax, [rcx]
0x180047eba  lea     r8, [rsp+118h+var_D0]
0x180047ebf  lea     rdx, IID_IEventObjectCollection
0x180047ec6  mov     rax, [rax]
0x180047ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ece  mov     ebx, eax
0x180047ed0  mov     [rsp+118h+var_D8], eax
0x180047ed4  jmp     loc_180048036
0x180047ed9  test    rcx, rcx
0x180047edc  jz      loc_180048036
0x180047ee2  lea     r13, [rdi+40h]
0x180047ee6  mov     rax, [rcx]
0x180047ee9  mov     r8, r13
0x180047eec  lea     rdx, IID_IEventSubscription2
0x180047ef3  mov     rax, [rax]
0x180047ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047efb  mov     ebx, eax
0x180047efd  mov     [rsp+118h+var_D8], eax
0x180047f01  test    eax, eax
0x180047f03  js      loc_18004801D
0x180047f09  lea     r12, [rdi+48h]
0x180047f0d  mov     rcx, [rsp+118h+arg_18]
0x180047f15  mov     rax, [rcx]
0x180047f18  mov     r8, r12
0x180047f1b  lea     rdx, IID_IEventSubscription3
0x180047f22  mov     rax, [rax]
0x180047f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f2a  mov     ebx, eax
0x180047f2c  mov     [rsp+118h+var_D8], eax
0x180047f30  test    eax, eax
0x180047f32  jns     short loc_180047F4F
0x180047f34  cmp     eax, 80004002h
0x180047f39  jnz     loc_18004801D
0x180047f3f  mov     [rsp+118h+var_D8], 0
0x180047f47  mov     qword ptr [r12], 0
0x180047f4f  mov     rcx, [r13+0]
0x180047f53  mov     rax, [rcx]
0x180047f56  lea     rdx, [rsp+118h+var_D0]
0x180047f5b  cmp     dword ptr [rdi+30h], 2
0x180047f5f  jnz     short loc_180047F6A
0x180047f61  mov     rax, [rax+110h]
0x180047f68  jmp     short loc_180047F71
0x180047f6a  mov     rax, [rax+130h]
0x180047f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f76  mov     [rsp+118h+var_D8], eax
0x180047f7a  mov     ebx, eax
0x180047f7c  test    eax, eax
0x180047f7e  js      loc_18004801D
0x180047f84  mov     ecx, 40h ; '@'; cb
0x180047f89  call    cs:__imp_CoTaskMemAlloc
0x180047f8f  mov     r10, rax
0x180047f92  test    rax, rax
0x180047f95  jz      short loc_180048008
0x180047f97  mov     edx, [rdi+6Ch]
0x180047f9a  mov     rcx, [rdi+58h]
0x180047f9e  cmp     rcx, cs:tidTRANSIENTSUBSCRIBERPROPERTIES
0x180047fa5  jnz     short loc_180047FB4
0x180047fa7  mov     rcx, [rdi+60h]
0x180047fab  cmp     rcx, cs:qword_180062180
0x180047fb2  jz      short loc_180047FCE
0x180047fb4  mov     rax, [rdi+58h]
0x180047fb8  cmp     rax, cs:tidTRANSIENTPUBLISHERPROPERTIES
0x180047fbf  jnz     short loc_180047FD3
0x180047fc1  mov     rax, [rdi+60h]
0x180047fc5  cmp     rax, cs:qword_180062170
0x180047fcc  jnz     short loc_180047FD3
0x180047fce  mov     eax, r14d
0x180047fd1  jmp     short loc_180047FD5
0x180047fd3  xor     eax, eax
0x180047fd5  mov     [rsp+118h+var_E0], edx
0x180047fd9  mov     [rsp+118h+var_E8], eax
0x180047fdd  mov     rax, [r12]
0x180047fe1  mov     [rsp+118h+pResults], rax
0x180047fe6  mov     rax, [r13+0]
0x180047fea  mov     qword ptr [rsp+118h+dwCount], rax
0x180047fef  mov     r9d, [rdi+30h]
0x180047ff3  mov     r8, [rdi+28h]
0x180047ff7  mov     rdx, [rdi+20h]
0x180047ffb  mov     rcx, r10
0x180047ffe  call    ??0PropertyLoader@@QEAA@PEAUISimpleTableWrite@@PEAUISimpleTableControl@@W4EventObjectKind@@PEAUIEventSubscription2@@PEAUIEventSubscription3@@HH@Z; PropertyLoader::PropertyLoader(ISimpleTableWrite *,ISimpleTableControl *,EventObjectKind,IEventSubscription2 *,IEventSubscription3 *,int,int)
0x180048003  mov     rsi, rax
0x180048006  jmp     short loc_18004800A
0x180048008  xor     esi, esi
0x18004800a  mov     [rsp+118h+var_B8], rsi
0x18004800f  test    rsi, rsi
0x180048012  jnz     short loc_18004802C
0x180048014  mov     ebx, 8007000Eh
0x180048019  mov     [rsp+118h+var_D8], ebx
0x18004801d  mov     r12, [rsp+118h+var_C0]
0x180048022  mov     r13, [rsp+118h+var_C8]
0x180048027  jmp     loc_180048102
0x18004802c  mov     r12, [rsp+118h+var_C0]
0x180048031  mov     r13, [rsp+118h+var_C8]
0x180048036  mov     rcx, [rsp+118h+var_D0]
0x18004803b  test    rcx, rcx
0x18004803e  jz      loc_180048102
0x180048044  mov     rax, [rcx]
0x180048047  lea     rdx, [rsp+118h+var_B0]
0x18004804c  mov     rax, [rax+48h]
0x180048050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048055  mov     ebx, eax
0x180048057  mov     [rsp+118h+var_D8], eax
0x18004805b  test    eax, eax
0x18004805d  js      short loc_18004801D
0x18004805f  mov     [rsp+118h+var_A0], 0
0x180048068  mov     [rsp+118h+arg_8], r14d
0x180048070  mov     rcx, [rsp+118h+var_B0]
0x180048075  mov     rax, [rcx]
0x180048078  lea     r9, [rsp+118h+arg_8]
0x180048080  lea     r8, [rsp+118h+var_A0]
0x180048085  mov     edx, r14d
0x180048088  mov     rax, [rax+20h]
0x18004808c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048091  mov     [rsp+118h+var_D8], eax
0x180048095  cmp     eax, r14d
0x180048098  jz      short loc_1800480CF
0x18004809a  cmp     [rsp+118h+arg_8], r14d
0x1800480a2  jnz     short loc_1800480CF
0x1800480a4  mov     rax, [rsi]
0x1800480a7  mov     rdx, [rsp+118h+var_A0]
0x1800480ac  mov     rcx, rsi
0x1800480af  mov     rax, [rax+8]
0x1800480b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480b8  mov     [rsp+118h+var_D8], eax
0x1800480bc  mov     rcx, [rsp+118h+var_A0]
0x1800480c1  mov     rax, [rcx]
0x1800480c4  mov     rax, [rax+10h]
0x1800480c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480cd  jmp     short loc_18004805F
0x1800480cf  xor     ebx, ebx
0x1800480d1  mov     [rsp+118h+var_D8], ebx
0x1800480d5  jmp     short loc_180048102
0x1800480d7  mov     r14d, 1
0x1800480dd  test    ebx, ebx
  ... truncated ...
```
