# CBaseURLBlockFilter::StartUrlBlockLookup(ushort const *,bool)

- ea: `0x1808023d0`
- end: `0x1808029ca`
- name: `?StartUrlBlockLookup@CBaseURLBlockFilter@@IEAAXPEBG_N@Z`
- size: `1530`
- prototype: `void __fastcall(CBaseURLBlockFilter *this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1810c6590`

## callees

- `0x18005d080`
- `0x180275414`
- `0x18063b9e4`
- `0x180797478`
- `0x1807cf208`
- `0x1808023d0`
- `0x1808029d0`
- `0x181069628`
- `0x18108e018`
- `0x1810c57f0`
- `0x1810c5bd4`
- `0x1810c5f60`
- `0x1810c622c`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1808027a3`
- `KERNEL32!InitializeCriticalSection` at `0x1808027a3`
- `KERNEL32!LeaveCriticalSection` at `0x180802454`
- `KERNEL32!LeaveCriticalSection` at `0x18080293f`
- `KERNEL32!LeaveCriticalSection` at `0x180802454`
- `KERNEL32!LeaveCriticalSection` at `0x18080293f`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x18080268a`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x18080268a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1808026d2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1808027b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18080296b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1808026d2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1808027b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18080296b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x180802652`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x180802652`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180802530`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180802600`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1808026ec`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1808027cc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180802530`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180802600`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1808026ec`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1808027cc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1808026a6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180802980`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1808026a6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180802980`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180802636`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1808026bf`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180802636`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1808026bf`

## pseudocode

```c
void __fastcall CBaseURLBlockFilter::StartUrlBlockLookup(
        CBaseURLBlockFilter *this,
        const unsigned __int16 *a2,
        unsigned __int8 a3)
{
  bool v5; // bl
  __int64 v6; // rcx
  __int64 v7; // rcx
  SAFEARRAY ***v8; // rax
  SAFEARRAY ***v9; // rdi
  SAFEARRAY **v10; // rax
  SAFEARRAY ***v11; // r12
  unsigned int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rcx
  SAFEARRAY *v15; // r15
  SAFEARRAY **v16; // rcx
  SAFEARRAY *v17; // rax
  const WCHAR *v18; // rcx
  SAFEARRAY **v19; // rbx
  SAFEARRAY *v20; // rcx
  SAFEARRAY **v21; // rdx
  unsigned int i; // r13d
  __int64 v23; // rcx
  char *v24; // r14
  const WCHAR *v25; // rcx
  int (__fastcall **v26)(LPVOID, GUID *, __int64 *); // rax
  SAFEARRAY **v27; // rdx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  unsigned int v34; // eax
  int v35; // edx
  int updated; // eax
  unsigned int v37; // [rsp+30h] [rbp-61h]
  unsigned __int8 *v38; // [rsp+38h] [rbp-59h]
  unsigned int v39; // [rsp+40h] [rbp-51h]
  unsigned __int8 v40; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int8 v41; // [rsp+49h] [rbp-48h] BYREF
  char v42; // [rsp+4Ah] [rbp-47h]
  SAFEARRAY *v43; // [rsp+50h] [rbp-41h] BYREF
  LPCRITICAL_SECTION *v44; // [rsp+58h] [rbp-39h] BYREF
  int v45; // [rsp+60h] [rbp-31h] BYREF
  SAFEARRAY *psa; // [rsp+68h] [rbp-29h] BYREF
  __int64 v47; // [rsp+70h] [rbp-21h] BYREF
  __int64 v48; // [rsp+78h] [rbp-19h] BYREF
  unsigned __int8 v49[8]; // [rsp+80h] [rbp-11h] BYREF
  LPCWSTR v50; // [rsp+88h] [rbp-9h]
  LPCRITICAL_SECTION *v51; // [rsp+90h] [rbp-1h] BYREF
  GUID pguid; // [rsp+98h] [rbp+7h] BYREF

  v50 = a2;
  if ( *((_BYTE *)this + 16) && *((_BYTE *)this + 17) )
  {
    CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(&v44, (LPCRITICAL_SECTION *)this + 6);
    v5 = (int)CHashTable<CBaseURLBlockFilter::CLookupItem,unsigned short>::ContainsKey(
                *((CByteHashTable **)this + 9),
                a2) >= 0;
    if ( *v44 )
      LeaveCriticalSection(*v44);
    if ( !v5 )
    {
      v6 = *((_QWORD *)this + 5);
      v44 = 0;
      v47 = 0;
      (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION **))(*(_QWORD *)v6 + 40LL))(v6, &v44);
      (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5), &v47);
      v43 = 0;
      psa = 0;
      CBaseURLBlockFilter::s_GetVerbAndIPAddress(&v44, &v47, &v43, &psa);
      IUnknown_SafeReleaseAndNullPtr<IDispImage>(&v44);
      v7 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      v8 = (SAFEARRAY ***)MemoryProtection::HeapAlloc<0>((MemoryProtection *)g_hProcessHeap, 0x20u);
      v9 = v8;
      if ( !v8 )
      {
        v15 = v43;
        goto LABEL_59;
      }
      v8[3] = 0;
      *(_OWORD *)v8 = 0;
      v8[2] = 0;
      v10 = (SAFEARRAY **)UrlBlockTaskMemAlloc(0x58u);
      v9[3] = v10;
      memset_0(v10, 0, 0x58u);
      v11 = v9 + 3;
      if ( SHStrDupW(a2, (LPWSTR *)v9[3] + 3) < 0 )
      {
        v15 = v43;
LABEL_57:
        CBaseURLBlockFilter::CLookupItem::`scalar deleting destructor'((CBaseURLBlockFilter::CLookupItem *)v9, v12);
LABEL_59:
        CoTaskMemFree(v15);
        if ( psa )
        {
          SafeArrayDestroy(psa);
          psa = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v44);
        return;
      }
      v13 = *((_QWORD *)this + 5);
      v40 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v13 + 16LL))(v13, &v40);
      *((_DWORD *)*v11 + 18) = v40;
      if ( !v40 )
        (*(void (__fastcall **)(_QWORD, SAFEARRAY **))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5), *v11 + 5);
      (***((void (__fastcall ****)(_QWORD, __int64))this + 5))(*((_QWORD *)this + 5), (__int64)(*v11 + 4));
      v14 = *((_QWORD *)this + 5);
      v41 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v14 + 24LL))(v14, &v41);
      v15 = 0;
      *((_DWORD *)*v11 + 19) = v41;
      v16 = *v11;
      v17 = v43;
      v43 = 0;
      v16[7] = v17;
      **v11 = psa;
      psa = 0;
      *((_DWORD *)*v11 + 20) = a3;
      if ( a3 )
      {
        v18 = (const WCHAR *)*((_QWORD *)this + 4);
        if ( v18 )
          SHStrDupW(v18, (LPWSTR *)*v11 + 6);
        v19 = (SAFEARRAY **)((char *)this + 64);
        v20 = (SAFEARRAY *)*((_QWORD *)this + 8);
        if ( !v20 )
          goto LABEL_20;
        v21 = *v11 + 2;
      }
      else
      {
        v19 = (SAFEARRAY **)((char *)this + 64);
        v20 = (SAFEARRAY *)*((_QWORD *)this + 8);
        if ( !v20 )
          goto LABEL_20;
        v21 = *v11 + 1;
      }
      SafeArrayCopy(v20, v21);
LABEL_20:
      pguid = GUID_NULL;
      if ( CoCreateGuid(&pguid) >= 0 )
      {
        (*v11)[8] = (SAFEARRAY *)UrlBlockTaskMemAlloc(0x4Eu);
        if ( StringFromGUID2(&pguid, &(*v11)[8]->cDims, 39) )
        {
          if ( *v19 )
          {
            SafeArrayDestroy(*v19);
            *v19 = 0;
          }
          SafeArrayCopy(**v11, v19);
          CoTaskMemFree(*((LPVOID *)this + 4));
          *((_QWORD *)this + 4) = 0;
          SHStrDupW(&(*v11)[3]->cDims, (LPWSTR *)this + 4);
          CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(
            &v51,
            (LPCRITICAL_SECTION *)this + 6);
          if ( (int)CHashTable<CBaseURLBlockFilter::CLookupItem,unsigned short>::ContainsKey(
                      *((CByteHashTable **)this + 9),
                      a2) < 0 )
          {
            v42 = 0;
            for ( i = 0; i < 3; ++i )
            {
              if ( *((_QWORD *)this + i + 12) )
              {
                v23 = *((_QWORD *)this + 1);
                *(_QWORD *)v49 = 3LL * i;
                if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 72LL))(
                        v23,
                        LODWORD(qword_18158CAD0[3 * i])) )
                {
                  v24 = (char *)MemoryProtection::HeapAlloc<0>((MemoryProtection *)g_hProcessHeap, 0x50u);
                  if ( v24 )
                  {
                    *((_QWORD *)v24 + 6) = this;
                    *(_QWORD *)v24 = &CBaseURLBlockFilter::CIsUrlAllowedLookupCallback::`vftable';
                    *((_DWORD *)v24 + 14) = i;
                    *((_QWORD *)v24 + 8) = 0;
                    *((_DWORD *)v24 + 18) = 1;
                    InitializeCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
                    CoTaskMemFree(*((LPVOID *)v24 + 8));
                    v25 = v50;
                    *((_QWORD *)v24 + 8) = 0;
                    if ( SHStrDupW(v25, (LPWSTR *)v24 + 8) >= 0 )
                    {
                      v26 = *(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v24;
                      v48 = 0;
                      if ( (*v26)(v24, &GUID_8506bdf6_580a_4b8f_8e4f_9f137ecb35e2, &v48) >= 0 )
                      {
                        v27 = *v11;
                        v45 = 1;
                        v28 = *((_QWORD *)this + i + 12);
                        v29 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY **, __int64, int *))(*(_QWORD *)v28 + 32LL))(
                                v28,
                                v27,
                                v48,
                                &v45);
                        if ( v29 < 0 )
                        {
                          if ( v29 == -2147483638 )
                          {
                            if ( v9[i] )
                              CBaseURLBlockFilter::CLookupItem::PassivateIsUrlAllowedLookupCallback(
                                (CBaseURLBlockFilter::CLookupItem *)v9,
                                i);
                            (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
                            v9[i] = (SAFEARRAY **)v24;
                            if ( !*((_BYTE *)this + 20) )
                            {
                              LOBYTE(v30) = 1;
                              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 96LL))(
                                *((_QWORD *)this + 1),
                                v30);
                              *((_BYTE *)this + 20) = 1;
                            }
                            v42 = 1;
                          }
                        }
                        else if ( *((_BYTE *)this + 17) )
                        {
                          if ( !v45 )
                          {
                            v31 = *((_QWORD *)this + 1);
                            v32 = *(_QWORD *)v49;
                            *((_BYTE *)this + 17) = 0;
                            (*(void (__fastcall **)(__int64, _QWORD, SAFEARRAY *))(*(_QWORD *)v31 + 88LL))(
                              v31,
                              LODWORD(qword_18158CAD0[v32]),
                              (*v11)[3]);
                            CBaseURLBlockFilter::PassivateUrlBlockFilter(this, v33);
                            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
                            break;
                          }
                          *((_BYTE *)this + 17) = 1;
                        }
                      }
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
                    }
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 16LL))(v24);
                  }
                }
              }
            }
            if ( *((_BYTE *)this + 17) && v42 )
            {
              *(_QWORD *)v49 = v9;
              v34 = _SizeOfString(v50);
              updated = CByteHashTable::_AddUpdateItem(
                          *((CByteHashTable **)this + 9),
                          v35,
                          (const unsigned __int8 *)v50,
                          v34,
                          v49,
                          v37,
                          v38,
                          v39);
              v15 = v43;
              if ( updated >= 0 )
              {
                ++*((_DWORD *)this + 6);
                v9 = 0;
              }
            }
            else
            {
              v15 = v43;
            }
          }
          if ( *v51 )
            LeaveCriticalSection(*v51);
          if ( !v9 )
            goto LABEL_59;
        }
      }
      goto LABEL_57;
    }
  }
}

```

## disassembly

```asm
0x1808023d0  mov     rax, rsp
0x1808023d3  mov     [rax+20h], rbx
0x1808023d7  mov     [rax+18h], r8b
0x1808023db  mov     [rax+10h], rdx
0x1808023df  mov     [rax+8], rcx
0x1808023e3  push    rbp
0x1808023e4  push    rsi
0x1808023e5  push    rdi
0x1808023e6  push    r12
0x1808023e8  push    r13
0x1808023ea  push    r14
0x1808023ec  push    r15
0x1808023ee  lea     rbp, [rax-5Fh]
0x1808023f2  sub     rsp, 0B0h
0x1808023f9  mov     rax, cs:__security_cookie
0x180802400  xor     rax, rsp
0x180802403  mov     [rbp+57h+var_40], rax
0x180802407  mov     rsi, [rbp+57h+arg_0]
0x18080240b  mov     r14, [rbp+57h+psz]
0x18080240f  mov     [rbp+57h+var_60], r14
0x180802413  cmp     byte ptr [rsi+10h], 0
0x180802417  jz      loc_1808029A2
0x18080241d  cmp     byte ptr [rsi+11h], 0
0x180802421  jz      loc_1808029A2
0x180802427  lea     rdx, [rsi+30h]
0x18080242b  lea     rcx, [rbp+57h+var_90]
0x18080242f  call    ??0?$CGuard@VSpCReferencedCriticalSection@@@@QEAA@AEAVSpCReferencedCriticalSection@@@Z; CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(SpCReferencedCriticalSection &)
0x180802434  mov     rcx, [rsi+48h]
0x180802438  mov     rdx, r14
0x18080243b  call    ?ContainsKey@?$CHashTable@VCLookupItem@CBaseURLBlockFilter@@G@@QEBAJPEBG@Z; CHashTable<CBaseURLBlockFilter::CLookupItem,ushort>::ContainsKey(ushort const *)
0x180802440  mov     rcx, [rbp+57h+var_90]
0x180802444  mov     ebx, eax
0x180802446  shr     ebx, 1Fh
0x180802449  xor     bl, 1
0x18080244c  mov     rcx, [rcx]; lpCriticalSection
0x18080244f  test    rcx, rcx
0x180802452  jz      short loc_180802460
0x180802454  call    cs:__imp_LeaveCriticalSection
0x18080245b  nop     dword ptr [rax+rax+00h]
0x180802460  test    bl, bl
0x180802462  jnz     loc_1808029A2
0x180802468  mov     rcx, [rsi+28h]
0x18080246c  lea     rdx, [rbp+57h+var_90]
0x180802470  xor     ebx, ebx
0x180802472  mov     [rbp+57h+var_90], rbx
0x180802476  mov     [rbp+57h+var_78], rbx
0x18080247a  mov     rax, [rcx]
0x18080247d  mov     rax, [rax+28h]
0x180802481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180802486  mov     rcx, [rsi+28h]
0x18080248a  lea     rdx, [rbp+57h+var_78]
0x18080248e  mov     rax, [rcx]
0x180802491  mov     rax, [rax+20h]
0x180802495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18080249a  lea     r9, [rbp+57h+psa]
0x18080249e  mov     [rbp+57h+var_98], rbx
0x1808024a2  lea     r8, [rbp+57h+var_98]
0x1808024a6  mov     [rbp+57h+psa], rbx
0x1808024aa  lea     rdx, [rbp+57h+var_78]
0x1808024ae  lea     rcx, [rbp+57h+var_90]
0x1808024b2  call    ?s_GetVerbAndIPAddress@CBaseURLBlockFilter@@CAXAEAV?$CComPtr@UIWinInetHttpInfo@@@ATL@@AEAV?$CComPtr@UIBindingExInternal@@@3@PEAPEADPEAPEAUtagSAFEARRAY@@@Z; CBaseURLBlockFilter::s_GetVerbAndIPAddress(ATL::CComPtr<IWinInetHttpInfo> &,ATL::CComPtr<IBindingExInternal> &,char * *,tagSAFEARRAY * *)
0x1808024b7  lea     rcx, [rbp+57h+var_90]
0x1808024bb  call    ??$IUnknown_SafeReleaseAndNullPtr@UIDispImage@@@@YAXAEAPEAUIDispImage@@@Z; IUnknown_SafeReleaseAndNullPtr<IDispImage>(IDispImage * &)
0x1808024c0  mov     rcx, [rbp+57h+var_78]
0x1808024c4  test    rcx, rcx
0x1808024c7  jz      short loc_1808024D9
0x1808024c9  mov     [rbp+57h+var_78], rbx
0x1808024cd  mov     rax, [rcx]
0x1808024d0  mov     rax, [rax+10h]
0x1808024d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808024d9  mov     rcx, cs:g_hProcessHeap
0x1808024e0  mov     edx, 20h ; ' '
0x1808024e5  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1808024ea  mov     rdi, rax
0x1808024ed  test    rax, rax
0x1808024f0  jz      loc_180802964
0x1808024f6  mov     [rax+18h], rbx
0x1808024fa  xorps   xmm0, xmm0
0x1808024fd  xor     eax, eax
0x1808024ff  movups  xmmword ptr [rdi], xmm0
0x180802502  mov     [rdi+10h], rax
0x180802506  lea     ebx, [rax+58h]
0x180802509  mov     ecx, ebx; unsigned __int64
0x18080250b  call    ?UrlBlockTaskMemAlloc@@YAPEAX_K@Z; UrlBlockTaskMemAlloc(unsigned __int64)
0x180802510  mov     r8d, ebx; Size
0x180802513  mov     [rdi+18h], rax
0x180802517  xor     edx, edx; Val
0x180802519  mov     rcx, rax; void *
0x18080251c  call    memset_0
0x180802521  lea     r12, [rdi+18h]
0x180802525  mov     rcx, r14; psz
0x180802528  mov     rdx, [r12]
0x18080252c  add     rdx, 18h; ppwsz
0x180802530  call    cs:__imp_SHStrDupW
0x180802537  nop     dword ptr [rax+rax+00h]
0x18080253c  xor     ebx, ebx
0x18080253e  test    eax, eax
0x180802540  js      loc_180802956
0x180802546  mov     rcx, [rsi+28h]
0x18080254a  lea     rdx, [rbp+57h+var_A0]
0x18080254e  mov     [rbp+57h+var_A0], bl
0x180802551  mov     rax, [rcx]
0x180802554  mov     rax, [rax+10h]
0x180802558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18080255d  mov     rax, [r12]
0x180802561  movzx   ecx, [rbp+57h+var_A0]
0x180802565  mov     [rax+48h], ecx
0x180802568  cmp     [rbp+57h+var_A0], bl
0x18080256b  jnz     short loc_180802585
0x18080256d  mov     rcx, [rsi+28h]
0x180802571  mov     rdx, [r12]
0x180802575  add     rdx, 28h ; '('
0x180802579  mov     rax, [rcx]
0x18080257c  mov     rax, [rax+8]
0x180802580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180802585  mov     rcx, [rsi+28h]
0x180802589  mov     rdx, [r12]
0x18080258d  add     rdx, 20h ; ' '
0x180802591  mov     rax, [rcx]
0x180802594  mov     rax, [rax]
0x180802597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18080259c  mov     rcx, [rsi+28h]
0x1808025a0  lea     rdx, [rbp+57h+var_9F]
0x1808025a4  mov     [rbp+57h+var_9F], bl
0x1808025a7  mov     rax, [rcx]
0x1808025aa  mov     rax, [rax+18h]
0x1808025ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808025b3  mov     rax, [r12]
0x1808025b7  mov     r15, rbx
0x1808025ba  movzx   ecx, [rbp+57h+var_9F]
0x1808025be  movzx   edx, [rbp+57h+arg_10]
0x1808025c2  mov     [rax+4Ch], ecx
0x1808025c5  mov     rcx, [r12]
0x1808025c9  mov     rax, [rbp+57h+var_98]
0x1808025cd  mov     [rbp+57h+var_98], rbx
0x1808025d1  mov     [rcx+38h], rax
0x1808025d5  mov     rax, [rbp+57h+psa]
0x1808025d9  mov     rcx, [r12]
0x1808025dd  mov     [rcx], rax
0x1808025e0  mov     [rbp+57h+psa], rbx
0x1808025e4  mov     rax, [r12]
0x1808025e8  mov     [rax+50h], edx
0x1808025eb  test    dl, dl
0x1808025ed  jz      short loc_180802622
0x1808025ef  mov     rcx, [rsi+20h]; psz
0x1808025f3  test    rcx, rcx
0x1808025f6  jz      short loc_18080260C
0x1808025f8  mov     rdx, [r12]
0x1808025fc  add     rdx, 30h ; '0'; ppwsz
0x180802600  call    cs:__imp_SHStrDupW
0x180802607  nop     dword ptr [rax+rax+00h]
0x18080260c  lea     rbx, [rsi+40h]
0x180802610  mov     rcx, [rbx]
0x180802613  test    rcx, rcx
0x180802616  jz      short loc_180802642
0x180802618  mov     rdx, [r12]
0x18080261c  add     rdx, 10h
0x180802620  jmp     short loc_180802636
0x180802622  lea     rbx, [rsi+40h]
0x180802626  mov     rcx, [rbx]; psa
0x180802629  test    rcx, rcx
0x18080262c  jz      short loc_180802642
0x18080262e  mov     rdx, [r12]
0x180802632  add     rdx, 8; ppsaOut
0x180802636  call    cs:__imp_SafeArrayCopy
0x18080263d  nop     dword ptr [rax+rax+00h]
0x180802642  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180802649  lea     rcx, [rbp+57h+pguid]; pguid
0x18080264d  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180802652  call    cs:__imp_CoCreateGuid
0x180802659  nop     dword ptr [rax+rax+00h]
0x18080265e  test    eax, eax
0x180802660  js      loc_180802952
0x180802666  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x18080266b  call    ?UrlBlockTaskMemAlloc@@YAPEAX_K@Z; UrlBlockTaskMemAlloc(unsigned __int64)
0x180802670  mov     rcx, [r12]
0x180802674  mov     r8d, 27h ; '''; cchMax
0x18080267a  mov     [rcx+40h], rax
0x18080267e  lea     rcx, [rbp+57h+pguid]; rguid
0x180802682  mov     rdx, [r12]
0x180802686  mov     rdx, [rdx+40h]; lpsz
0x18080268a  call    cs:__imp_StringFromGUID2
0x180802691  nop     dword ptr [rax+rax+00h]
0x180802696  test    eax, eax
0x180802698  jz      loc_180802952
0x18080269e  mov     rcx, [rbx]; psa
0x1808026a1  test    rcx, rcx
0x1808026a4  jz      short loc_1808026B5
0x1808026a6  call    cs:__imp_SafeArrayDestroy
0x1808026ad  nop     dword ptr [rax+rax+00h]
0x1808026b2  mov     [rbx], r15
0x1808026b5  mov     rcx, [r12]
0x1808026b9  mov     rdx, rbx; ppsaOut
0x1808026bc  mov     rcx, [rcx]; psa
0x1808026bf  call    cs:__imp_SafeArrayCopy
0x1808026c6  nop     dword ptr [rax+rax+00h]
0x1808026cb  lea     rbx, [rsi+20h]
0x1808026cf  mov     rcx, [rbx]; pv
0x1808026d2  call    cs:__imp_CoTaskMemFree
0x1808026d9  nop     dword ptr [rax+rax+00h]
0x1808026de  mov     [rbx], r15
0x1808026e1  mov     rdx, rbx; ppwsz
0x1808026e4  mov     rcx, [r12]
0x1808026e8  mov     rcx, [rcx+18h]; psz
0x1808026ec  call    cs:__imp_SHStrDupW
0x1808026f3  nop     dword ptr [rax+rax+00h]
0x1808026f8  lea     rdx, [rsi+30h]
0x1808026fc  lea     rcx, [rbp+57h+var_58]
0x180802700  call    ??0?$CGuard@VSpCReferencedCriticalSection@@@@QEAA@AEAVSpCReferencedCriticalSection@@@Z; CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(SpCReferencedCriticalSection &)
0x180802705  mov     rcx, [rsi+48h]
0x180802709  mov     rdx, r14
0x18080270c  call    ?ContainsKey@?$CHashTable@VCLookupItem@CBaseURLBlockFilter@@G@@QEBAJPEBG@Z; CHashTable<CBaseURLBlockFilter::CLookupItem,ushort>::ContainsKey(ushort const *)
0x180802711  xor     ebx, ebx
0x180802713  test    eax, eax
0x180802715  jns     loc_180802933
0x18080271b  mov     [rbp+57h+var_9E], bl
0x18080271e  mov     r13d, ebx
0x180802721  cmp     r13d, 3
0x180802725  jnb     loc_1808028EF
0x18080272b  mov     eax, r13d
0x18080272e  cmp     [rsi+rax*8+60h], rbx
0x180802733  jz      loc_1808028AC
0x180802739  mov     rcx, [rsi+8]
0x18080273d  lea     rdx, [rax+rax*2]
0x180802741  lea     r8, qword_18158CAD0
0x180802748  mov     qword ptr [rbp+57h+var_68], rdx
0x18080274c  mov     edx, [r8+rdx*8]
0x180802750  mov     rax, [rcx]
0x180802753  mov     rax, [rax+48h]
0x180802757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18080275c  test    al, al
0x18080275e  jnz     loc_1808028AC
0x180802764  mov     rcx, cs:g_hProcessHeap
0x18080276b  mov     edx, 50h ; 'P'
0x180802770  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180802775  mov     r14, rax
0x180802778  test    rax, rax
0x18080277b  jz      loc_1808028AC
0x180802781  lea     rax, ??_7CIsUrlAllowedLookupCallback@CBaseURLBlockFilter@@6B@; const CBaseURLBlockFilter::CIsUrlAllowedLookupCallback::`vftable'
0x180802788  mov     [r14+30h], rsi
0x18080278c  mov     [r14], rax
0x18080278f  lea     rcx, [r14+8]; lpCriticalSection
0x180802793  mov     [r14+38h], r13d
0x180802797  mov     [r14+40h], rbx
0x18080279b  mov     dword ptr [r14+48h], 1
0x1808027a3  call    cs:__imp_InitializeCriticalSection
0x1808027aa  nop     dword ptr [rax+rax+00h]
0x1808027af  lea     rbx, [r14+40h]
0x1808027b3  mov     rcx, [rbx]; pv
0x1808027b6  call    cs:__imp_CoTaskMemFree
0x1808027bd  nop     dword ptr [rax+rax+00h]
0x1808027c2  mov     rcx, [rbp+57h+var_60]; psz
0x1808027c6  mov     rdx, rbx; ppwsz
0x1808027c9  mov     [rbx], r15
0x1808027cc  call    cs:__imp_SHStrDupW
0x1808027d3  nop     dword ptr [rax+rax+00h]
0x1808027d8  xor     ebx, ebx
0x1808027da  test    eax, eax
0x1808027dc  js      loc_18080289D
0x1808027e2  mov     rax, [r14]
0x1808027e5  lea     r8, [rbp+57h+var_70]
0x1808027e9  lea     rdx, _GUID_8506bdf6_580a_4b8f_8e4f_9f137ecb35e2
0x1808027f0  mov     [rbp+57h+var_70], rbx
0x1808027f4  mov     rcx, r14
0x1808027f7  mov     rax, [rax]
0x1808027fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808027ff  test    eax, eax
0x180802801  js      loc_180802894
0x180802807  mov     r8, [rbp+57h+var_70]
0x18080280b  lea     r9, [rbp+57h+var_88]
0x18080280f  mov     rdx, [r12]
0x180802813  mov     [rbp+57h+var_88], 1
0x18080281a  mov     ebx, r13d
0x18080281d  mov     rcx, [rsi+rbx*8+60h]
0x180802822  mov     rax, [rcx]
0x180802825  mov     rax, [rax+20h]
0x180802829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18080282e  test    eax, eax
0x180802830  js      short loc_180802844
0x180802832  xor     ebx, ebx
0x180802834  cmp     [rsi+11h], bl
0x180802837  jz      short loc_180802894
0x180802839  cmp     [rbp+57h+var_88], ebx
0x18080283c  jz      short loc_1808028B4
0x18080283e  mov     byte ptr [rsi+11h], 1
0x180802842  jmp     short loc_180802894
0x180802844  cmp     eax, 8000000Ah
0x180802849  jnz     short loc_180802892
0x18080284b  cmp     [rdi+rbx*8], r15
0x18080284f  jz      short loc_18080285C
0x180802851  mov     edx, r13d; unsigned int
0x180802854  mov     rcx, rdi; this
0x180802857  call    ?PassivateIsUrlAllowedLookupCallback@CLookupItem@CBaseURLBlockFilter@@QEAAXK@Z; CBaseURLBlockFilter::CLookupItem::PassivateIsUrlAllowedLookupCallback(ulong)
0x18080285c  mov     rax, [r14]
0x18080285f  mov     rcx, r14
0x180802862  mov     rax, [rax+8]
0x180802866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18080286b  mov     [rdi+rbx*8], r14
0x18080286f  xor     ebx, ebx
0x180802871  cmp     [rsi+14h], bl
  ... truncated ...
```
