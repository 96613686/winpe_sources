# CBaseURLBlockFilter::StartUrlBlockLookup(ushort const *,bool)

- ea: `0x1807f783c`
- end: `0x1807f7dd5`
- name: `?StartUrlBlockLookup@CBaseURLBlockFilter@@IEAAXPEBG_N@Z`
- size: `1433`
- prototype: `void __fastcall(CBaseURLBlockFilter *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x181094020`

## callees

- `0x1800b9fa0`
- `0x1801bf528`
- `0x180644720`
- `0x1807864b4`
- `0x1807c51f0`
- `0x1807f783c`
- `0x1807f7ddc`
- `0x18103ad3c`
- `0x18105df98`
- `0x1810933f0`
- `0x18109378c`
- `0x181093a78`
- `0x181093cd0`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1807f7bd3`
- `KERNEL32!InitializeCriticalSection` at `0x1807f7bd3`
- `KERNEL32!LeaveCriticalSection` at `0x1807f78c0`
- `KERNEL32!LeaveCriticalSection` at `0x1807f7d5d`
- `KERNEL32!LeaveCriticalSection` at `0x1807f78c0`
- `KERNEL32!LeaveCriticalSection` at `0x1807f7d5d`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1807f7ad8`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1807f7ad8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807f7b0e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807f7be0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807f7d83`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807f7b0e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807f7be0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807f7d83`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x1807f7aa6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x1807f7aa6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7996`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7a60`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7b22`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7bf0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7996`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7a60`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7b22`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1807f7bf0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1807f7aee`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1807f7d92`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1807f7aee`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1807f7d92`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1807f7a90`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1807f7b01`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1807f7a90`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1807f7b01`

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
  __int64 v8; // rax
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
  __int64 v24; // r14
  const WCHAR *v25; // rcx
  int (__fastcall **v26)(__int64, GUID *, __int64 *); // rax
  SAFEARRAY **v27; // rdx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // eax
  int v34; // edx
  int updated; // eax
  unsigned int v36; // [rsp+30h] [rbp-61h]
  unsigned __int8 *v37; // [rsp+38h] [rbp-59h]
  unsigned int v38; // [rsp+40h] [rbp-51h]
  unsigned __int8 v39; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int8 v40; // [rsp+49h] [rbp-48h] BYREF
  char v41; // [rsp+4Ah] [rbp-47h]
  SAFEARRAY *v42; // [rsp+50h] [rbp-41h] BYREF
  LPCRITICAL_SECTION *v43; // [rsp+58h] [rbp-39h] BYREF
  int v44; // [rsp+60h] [rbp-31h] BYREF
  SAFEARRAY *psa; // [rsp+68h] [rbp-29h] BYREF
  __int64 v46; // [rsp+70h] [rbp-21h] BYREF
  __int64 v47; // [rsp+78h] [rbp-19h] BYREF
  unsigned __int8 v48[8]; // [rsp+80h] [rbp-11h] BYREF
  LPCWSTR v49; // [rsp+88h] [rbp-9h]
  LPCRITICAL_SECTION *v50; // [rsp+90h] [rbp-1h] BYREF
  GUID pguid; // [rsp+98h] [rbp+7h] BYREF

  v49 = a2;
  if ( *((_BYTE *)this + 16) && *((_BYTE *)this + 17) )
  {
    CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(&v43, (char *)this + 48);
    v5 = (int)CHashTable<CBaseURLBlockFilter::CLookupItem,unsigned short>::ContainsKey(*((_QWORD *)this + 9), a2) >= 0;
    if ( *v43 )
      LeaveCriticalSection(*v43);
    if ( !v5 )
    {
      v6 = *((_QWORD *)this + 5);
      v43 = 0;
      v46 = 0;
      (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION **))(*(_QWORD *)v6 + 40LL))(v6, &v43);
      (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5), &v46);
      v42 = 0;
      psa = 0;
      CBaseURLBlockFilter::s_GetVerbAndIPAddress(&v43, &v46, &v42, &psa);
      IUnknown_SafeReleaseAndNullPtr<IDispImage>(&v43);
      v7 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      v8 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 32);
      v9 = (SAFEARRAY ***)v8;
      if ( !v8 )
      {
        v15 = v42;
        goto LABEL_59;
      }
      *(_QWORD *)(v8 + 24) = 0;
      *(_OWORD *)v8 = 0;
      *(_QWORD *)(v8 + 16) = 0;
      v10 = (SAFEARRAY **)UrlBlockTaskMemAlloc(0x58u);
      v9[3] = v10;
      memset_0(v10, 0, 0x58u);
      v11 = v9 + 3;
      if ( SHStrDupW(a2, (LPWSTR *)v9[3] + 3) < 0 )
      {
        v15 = v42;
LABEL_57:
        CBaseURLBlockFilter::CLookupItem::`scalar deleting destructor'((CBaseURLBlockFilter::CLookupItem *)v9, v12);
LABEL_59:
        CoTaskMemFree(v15);
        if ( psa )
        {
          SafeArrayDestroy(psa);
          psa = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        return;
      }
      v13 = *((_QWORD *)this + 5);
      v39 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v13 + 16LL))(v13, &v39);
      *((_DWORD *)*v11 + 18) = v39;
      if ( !v39 )
        (*(void (__fastcall **)(_QWORD, SAFEARRAY **))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5), *v11 + 5);
      (***((void (__fastcall ****)(_QWORD, __int64))this + 5))(*((_QWORD *)this + 5), (__int64)(*v11 + 4));
      v14 = *((_QWORD *)this + 5);
      v40 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v14 + 24LL))(v14, &v40);
      v15 = 0;
      *((_DWORD *)*v11 + 19) = v40;
      v16 = *v11;
      v17 = v42;
      v42 = 0;
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
          CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(&v50, (char *)this + 48);
          if ( (int)CHashTable<CBaseURLBlockFilter::CLookupItem,unsigned short>::ContainsKey(*((_QWORD *)this + 9), a2) < 0 )
          {
            v41 = 0;
            for ( i = 0; i < 3; ++i )
            {
              if ( *((_QWORD *)this + i + 12) )
              {
                v23 = *((_QWORD *)this + 1);
                *(_QWORD *)v48 = 3LL * i;
                if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 72LL))(
                        v23,
                        *((unsigned int *)&unk_181559AB0 + 6 * i)) )
                {
                  v24 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 80);
                  if ( v24 )
                  {
                    *(_QWORD *)(v24 + 48) = this;
                    *(_QWORD *)v24 = &CBaseURLBlockFilter::CIsUrlAllowedLookupCallback::`vftable';
                    *(_DWORD *)(v24 + 56) = i;
                    *(_QWORD *)(v24 + 64) = 0;
                    *(_DWORD *)(v24 + 72) = 1;
                    InitializeCriticalSection((LPCRITICAL_SECTION)(v24 + 8));
                    CoTaskMemFree(*(LPVOID *)(v24 + 64));
                    v25 = v49;
                    *(_QWORD *)(v24 + 64) = 0;
                    if ( SHStrDupW(v25, (LPWSTR *)(v24 + 64)) >= 0 )
                    {
                      v26 = *(int (__fastcall ***)(__int64, GUID *, __int64 *))v24;
                      v47 = 0;
                      if ( (*v26)(v24, &GUID_8506bdf6_580a_4b8f_8e4f_9f137ecb35e2, &v47) >= 0 )
                      {
                        v27 = *v11;
                        v44 = 1;
                        v28 = *((_QWORD *)this + i + 12);
                        v29 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY **, __int64, int *))(*(_QWORD *)v28 + 32LL))(
                                v28,
                                v27,
                                v47,
                                &v44);
                        if ( v29 < 0 )
                        {
                          if ( v29 == -2147483638 )
                          {
                            if ( v9[i] )
                              CBaseURLBlockFilter::CLookupItem::PassivateIsUrlAllowedLookupCallback(
                                (CBaseURLBlockFilter::CLookupItem *)v9,
                                i);
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
                            v9[i] = (SAFEARRAY **)v24;
                            if ( !*((_BYTE *)this + 20) )
                            {
                              LOBYTE(v30) = 1;
                              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 96LL))(
                                *((_QWORD *)this + 1),
                                v30);
                              *((_BYTE *)this + 20) = 1;
                            }
                            v41 = 1;
                          }
                        }
                        else if ( *((_BYTE *)this + 17) )
                        {
                          if ( !v44 )
                          {
                            v31 = *((_QWORD *)this + 1);
                            v32 = *(_QWORD *)v48;
                            *((_BYTE *)this + 17) = 0;
                            (*(void (__fastcall **)(__int64, _QWORD, SAFEARRAY *))(*(_QWORD *)v31 + 88LL))(
                              v31,
                              *((unsigned int *)&unk_181559AB0 + 2 * v32),
                              (*v11)[3]);
                            CBaseURLBlockFilter::PassivateUrlBlockFilter(this);
                            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
                            break;
                          }
                          *((_BYTE *)this + 17) = 1;
                        }
                      }
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                  }
                }
              }
            }
            if ( *((_BYTE *)this + 17) && v41 )
            {
              *(_QWORD *)v48 = v9;
              v33 = _SizeOfString(v49);
              updated = CByteHashTable::_AddUpdateItem(
                          *((CByteHashTable **)this + 9),
                          v34,
                          (const unsigned __int8 *)v49,
                          v33,
                          v48,
                          v36,
                          v37,
                          v38);
              v15 = v42;
              if ( updated >= 0 )
              {
                ++*((_DWORD *)this + 6);
                v9 = 0;
              }
            }
            else
            {
              v15 = v42;
            }
          }
          if ( *v50 )
            LeaveCriticalSection(*v50);
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
0x1807f783c  mov     rax, rsp
0x1807f783f  mov     [rax+20h], rbx
0x1807f7843  mov     [rax+18h], r8b
0x1807f7847  mov     [rax+10h], rdx
0x1807f784b  mov     [rax+8], rcx
0x1807f784f  push    rbp
0x1807f7850  push    rsi
0x1807f7851  push    rdi
0x1807f7852  push    r12
0x1807f7854  push    r13
0x1807f7856  push    r14
0x1807f7858  push    r15
0x1807f785a  lea     rbp, [rax-5Fh]
0x1807f785e  sub     rsp, 0B0h
0x1807f7865  mov     rax, cs:__security_cookie
0x1807f786c  xor     rax, rsp
0x1807f786f  mov     [rbp+57h+var_40], rax
0x1807f7873  mov     rsi, [rbp+57h+arg_0]
0x1807f7877  mov     r14, [rbp+57h+psz]
0x1807f787b  mov     [rbp+57h+var_60], r14
0x1807f787f  cmp     byte ptr [rsi+10h], 0
0x1807f7883  jz      loc_1807F7DAE
0x1807f7889  cmp     byte ptr [rsi+11h], 0
0x1807f788d  jz      loc_1807F7DAE
0x1807f7893  lea     rdx, [rsi+30h]
0x1807f7897  lea     rcx, [rbp+57h+var_90]
0x1807f789b  call    ??0?$CGuard@VSpCReferencedCriticalSection@@@@QEAA@AEAVSpCReferencedCriticalSection@@@Z; CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(SpCReferencedCriticalSection &)
0x1807f78a0  mov     rcx, [rsi+48h]
0x1807f78a4  mov     rdx, r14
0x1807f78a7  call    ?ContainsKey@?$CHashTable@VCLookupItem@CBaseURLBlockFilter@@G@@QEBAJPEBG@Z; CHashTable<CBaseURLBlockFilter::CLookupItem,ushort>::ContainsKey(ushort const *)
0x1807f78ac  mov     rcx, [rbp+57h+var_90]
0x1807f78b0  mov     ebx, eax
0x1807f78b2  shr     ebx, 1Fh
0x1807f78b5  xor     bl, 1
0x1807f78b8  mov     rcx, [rcx]; lpCriticalSection
0x1807f78bb  test    rcx, rcx
0x1807f78be  jz      short loc_1807F78C6
0x1807f78c0  call    cs:__imp_LeaveCriticalSection
0x1807f78c6  test    bl, bl
0x1807f78c8  jnz     loc_1807F7DAE
0x1807f78ce  mov     rcx, [rsi+28h]
0x1807f78d2  lea     rdx, [rbp+57h+var_90]
0x1807f78d6  xor     ebx, ebx
0x1807f78d8  mov     [rbp+57h+var_90], rbx
0x1807f78dc  mov     [rbp+57h+var_78], rbx
0x1807f78e0  mov     rax, [rcx]
0x1807f78e3  mov     rax, [rax+28h]
0x1807f78e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f78ec  mov     rcx, [rsi+28h]
0x1807f78f0  lea     rdx, [rbp+57h+var_78]
0x1807f78f4  mov     rax, [rcx]
0x1807f78f7  mov     rax, [rax+20h]
0x1807f78fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7900  lea     r9, [rbp+57h+psa]
0x1807f7904  mov     [rbp+57h+var_98], rbx
0x1807f7908  lea     r8, [rbp+57h+var_98]
0x1807f790c  mov     [rbp+57h+psa], rbx
0x1807f7910  lea     rdx, [rbp+57h+var_78]
0x1807f7914  lea     rcx, [rbp+57h+var_90]
0x1807f7918  call    ?s_GetVerbAndIPAddress@CBaseURLBlockFilter@@CAXAEAV?$CComPtr@UIWinInetHttpInfo@@@ATL@@AEAV?$CComPtr@UIBindingExInternal@@@3@PEAPEADPEAPEAUtagSAFEARRAY@@@Z; CBaseURLBlockFilter::s_GetVerbAndIPAddress(ATL::CComPtr<IWinInetHttpInfo> &,ATL::CComPtr<IBindingExInternal> &,char * *,tagSAFEARRAY * *)
0x1807f791d  lea     rcx, [rbp+57h+var_90]
0x1807f7921  call    ??$IUnknown_SafeReleaseAndNullPtr@UIDispImage@@@@YAXAEAPEAUIDispImage@@@Z; IUnknown_SafeReleaseAndNullPtr<IDispImage>(IDispImage * &)
0x1807f7926  mov     rcx, [rbp+57h+var_78]
0x1807f792a  test    rcx, rcx
0x1807f792d  jz      short loc_1807F793F
0x1807f792f  mov     [rbp+57h+var_78], rbx
0x1807f7933  mov     rax, [rcx]
0x1807f7936  mov     rax, [rax+10h]
0x1807f793a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f793f  mov     rcx, cs:g_hProcessHeap
0x1807f7946  mov     edx, 20h ; ' '
0x1807f794b  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1807f7950  mov     rdi, rax
0x1807f7953  test    rax, rax
0x1807f7956  jz      loc_1807F7D7C
0x1807f795c  mov     [rax+18h], rbx
0x1807f7960  xorps   xmm0, xmm0
0x1807f7963  xor     eax, eax
0x1807f7965  movups  xmmword ptr [rdi], xmm0
0x1807f7968  mov     [rdi+10h], rax
0x1807f796c  lea     ebx, [rax+58h]
0x1807f796f  mov     ecx, ebx; unsigned __int64
0x1807f7971  call    ?UrlBlockTaskMemAlloc@@YAPEAX_K@Z; UrlBlockTaskMemAlloc(unsigned __int64)
0x1807f7976  mov     r8d, ebx; Size
0x1807f7979  mov     [rdi+18h], rax
0x1807f797d  xor     edx, edx; Val
0x1807f797f  mov     rcx, rax; void *
0x1807f7982  call    memset_0
0x1807f7987  lea     r12, [rdi+18h]
0x1807f798b  mov     rcx, r14; psz
0x1807f798e  mov     rdx, [r12]
0x1807f7992  add     rdx, 18h; ppwsz
0x1807f7996  call    cs:__imp_SHStrDupW
0x1807f799c  xor     ebx, ebx
0x1807f799e  test    eax, eax
0x1807f79a0  js      loc_1807F7D6E
0x1807f79a6  mov     rcx, [rsi+28h]
0x1807f79aa  lea     rdx, [rbp+57h+var_A0]
0x1807f79ae  mov     [rbp+57h+var_A0], bl
0x1807f79b1  mov     rax, [rcx]
0x1807f79b4  mov     rax, [rax+10h]
0x1807f79b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f79bd  mov     rax, [r12]
0x1807f79c1  movzx   ecx, [rbp+57h+var_A0]
0x1807f79c5  mov     [rax+48h], ecx
0x1807f79c8  cmp     [rbp+57h+var_A0], bl
0x1807f79cb  jnz     short loc_1807F79E5
0x1807f79cd  mov     rcx, [rsi+28h]
0x1807f79d1  mov     rdx, [r12]
0x1807f79d5  add     rdx, 28h ; '('
0x1807f79d9  mov     rax, [rcx]
0x1807f79dc  mov     rax, [rax+8]
0x1807f79e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f79e5  mov     rcx, [rsi+28h]
0x1807f79e9  mov     rdx, [r12]
0x1807f79ed  add     rdx, 20h ; ' '
0x1807f79f1  mov     rax, [rcx]
0x1807f79f4  mov     rax, [rax]
0x1807f79f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f79fc  mov     rcx, [rsi+28h]
0x1807f7a00  lea     rdx, [rbp+57h+var_9F]
0x1807f7a04  mov     [rbp+57h+var_9F], bl
0x1807f7a07  mov     rax, [rcx]
0x1807f7a0a  mov     rax, [rax+18h]
0x1807f7a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7a13  mov     rax, [r12]
0x1807f7a17  mov     r15, rbx
0x1807f7a1a  movzx   ecx, [rbp+57h+var_9F]
0x1807f7a1e  movzx   edx, [rbp+57h+arg_10]
0x1807f7a22  mov     [rax+4Ch], ecx
0x1807f7a25  mov     rcx, [r12]
0x1807f7a29  mov     rax, [rbp+57h+var_98]
0x1807f7a2d  mov     [rbp+57h+var_98], rbx
0x1807f7a31  mov     [rcx+38h], rax
0x1807f7a35  mov     rax, [rbp+57h+psa]
0x1807f7a39  mov     rcx, [r12]
0x1807f7a3d  mov     [rcx], rax
0x1807f7a40  mov     [rbp+57h+psa], rbx
0x1807f7a44  mov     rax, [r12]
0x1807f7a48  mov     [rax+50h], edx
0x1807f7a4b  test    dl, dl
0x1807f7a4d  jz      short loc_1807F7A7C
0x1807f7a4f  mov     rcx, [rsi+20h]; psz
0x1807f7a53  test    rcx, rcx
0x1807f7a56  jz      short loc_1807F7A66
0x1807f7a58  mov     rdx, [r12]
0x1807f7a5c  add     rdx, 30h ; '0'; ppwsz
0x1807f7a60  call    cs:__imp_SHStrDupW
0x1807f7a66  lea     rbx, [rsi+40h]
0x1807f7a6a  mov     rcx, [rbx]
0x1807f7a6d  test    rcx, rcx
0x1807f7a70  jz      short loc_1807F7A96
0x1807f7a72  mov     rdx, [r12]
0x1807f7a76  add     rdx, 10h
0x1807f7a7a  jmp     short loc_1807F7A90
0x1807f7a7c  lea     rbx, [rsi+40h]
0x1807f7a80  mov     rcx, [rbx]; psa
0x1807f7a83  test    rcx, rcx
0x1807f7a86  jz      short loc_1807F7A96
0x1807f7a88  mov     rdx, [r12]
0x1807f7a8c  add     rdx, 8; ppsaOut
0x1807f7a90  call    cs:__imp_SafeArrayCopy
0x1807f7a96  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1807f7a9d  lea     rcx, [rbp+57h+pguid]; pguid
0x1807f7aa1  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1807f7aa6  call    cs:__imp_CoCreateGuid
0x1807f7aac  test    eax, eax
0x1807f7aae  js      loc_1807F7D6A
0x1807f7ab4  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x1807f7ab9  call    ?UrlBlockTaskMemAlloc@@YAPEAX_K@Z; UrlBlockTaskMemAlloc(unsigned __int64)
0x1807f7abe  mov     rcx, [r12]
0x1807f7ac2  mov     r8d, 27h ; '''; cchMax
0x1807f7ac8  mov     [rcx+40h], rax
0x1807f7acc  lea     rcx, [rbp+57h+pguid]; rguid
0x1807f7ad0  mov     rdx, [r12]
0x1807f7ad4  mov     rdx, [rdx+40h]; lpsz
0x1807f7ad8  call    cs:__imp_StringFromGUID2
0x1807f7ade  test    eax, eax
0x1807f7ae0  jz      loc_1807F7D6A
0x1807f7ae6  mov     rcx, [rbx]; psa
0x1807f7ae9  test    rcx, rcx
0x1807f7aec  jz      short loc_1807F7AF7
0x1807f7aee  call    cs:__imp_SafeArrayDestroy
0x1807f7af4  mov     [rbx], r15
0x1807f7af7  mov     rcx, [r12]
0x1807f7afb  mov     rdx, rbx; ppsaOut
0x1807f7afe  mov     rcx, [rcx]; psa
0x1807f7b01  call    cs:__imp_SafeArrayCopy
0x1807f7b07  lea     rbx, [rsi+20h]
0x1807f7b0b  mov     rcx, [rbx]; pv
0x1807f7b0e  call    cs:__imp_CoTaskMemFree
0x1807f7b14  mov     [rbx], r15
0x1807f7b17  mov     rdx, rbx; ppwsz
0x1807f7b1a  mov     rcx, [r12]
0x1807f7b1e  mov     rcx, [rcx+18h]; psz
0x1807f7b22  call    cs:__imp_SHStrDupW
0x1807f7b28  lea     rdx, [rsi+30h]
0x1807f7b2c  lea     rcx, [rbp+57h+var_58]
0x1807f7b30  call    ??0?$CGuard@VSpCReferencedCriticalSection@@@@QEAA@AEAVSpCReferencedCriticalSection@@@Z; CGuard<SpCReferencedCriticalSection>::CGuard<SpCReferencedCriticalSection>(SpCReferencedCriticalSection &)
0x1807f7b35  mov     rcx, [rsi+48h]
0x1807f7b39  mov     rdx, r14
0x1807f7b3c  call    ?ContainsKey@?$CHashTable@VCLookupItem@CBaseURLBlockFilter@@G@@QEBAJPEBG@Z; CHashTable<CBaseURLBlockFilter::CLookupItem,ushort>::ContainsKey(ushort const *)
0x1807f7b41  xor     ebx, ebx
0x1807f7b43  test    eax, eax
0x1807f7b45  jns     loc_1807F7D51
0x1807f7b4b  mov     [rbp+57h+var_9E], bl
0x1807f7b4e  mov     r13d, ebx
0x1807f7b51  cmp     r13d, 3
0x1807f7b55  jnb     loc_1807F7D0D
0x1807f7b5b  mov     eax, r13d
0x1807f7b5e  cmp     [rsi+rax*8+60h], rbx
0x1807f7b63  jz      loc_1807F7CCA
0x1807f7b69  mov     rcx, [rsi+8]
0x1807f7b6d  lea     rdx, [rax+rax*2]
0x1807f7b71  lea     r8, unk_181559AB0
0x1807f7b78  mov     qword ptr [rbp+57h+var_68], rdx
0x1807f7b7c  mov     edx, [r8+rdx*8]
0x1807f7b80  mov     rax, [rcx]
0x1807f7b83  mov     rax, [rax+48h]
0x1807f7b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7b8c  test    al, al
0x1807f7b8e  jnz     loc_1807F7CCA
0x1807f7b94  mov     rcx, cs:g_hProcessHeap
0x1807f7b9b  mov     edx, 50h ; 'P'
0x1807f7ba0  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1807f7ba5  mov     r14, rax
0x1807f7ba8  test    rax, rax
0x1807f7bab  jz      loc_1807F7CCA
0x1807f7bb1  lea     rax, ??_7CIsUrlAllowedLookupCallback@CBaseURLBlockFilter@@6B@; const CBaseURLBlockFilter::CIsUrlAllowedLookupCallback::`vftable'
0x1807f7bb8  mov     [r14+30h], rsi
0x1807f7bbc  mov     [r14], rax
0x1807f7bbf  lea     rcx, [r14+8]; lpCriticalSection
0x1807f7bc3  mov     [r14+38h], r13d
0x1807f7bc7  mov     [r14+40h], rbx
0x1807f7bcb  mov     dword ptr [r14+48h], 1
0x1807f7bd3  call    cs:__imp_InitializeCriticalSection
0x1807f7bd9  lea     rbx, [r14+40h]
0x1807f7bdd  mov     rcx, [rbx]; pv
0x1807f7be0  call    cs:__imp_CoTaskMemFree
0x1807f7be6  mov     rcx, [rbp+57h+var_60]; psz
0x1807f7bea  mov     rdx, rbx; ppwsz
0x1807f7bed  mov     [rbx], r15
0x1807f7bf0  call    cs:__imp_SHStrDupW
0x1807f7bf6  xor     ebx, ebx
0x1807f7bf8  test    eax, eax
0x1807f7bfa  js      loc_1807F7CBB
0x1807f7c00  mov     rax, [r14]
0x1807f7c03  lea     r8, [rbp+57h+var_70]
0x1807f7c07  lea     rdx, _GUID_8506bdf6_580a_4b8f_8e4f_9f137ecb35e2
0x1807f7c0e  mov     [rbp+57h+var_70], rbx
0x1807f7c12  mov     rcx, r14
0x1807f7c15  mov     rax, [rax]
0x1807f7c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7c1d  test    eax, eax
0x1807f7c1f  js      loc_1807F7CB2
0x1807f7c25  mov     r8, [rbp+57h+var_70]
0x1807f7c29  lea     r9, [rbp+57h+var_88]
0x1807f7c2d  mov     rdx, [r12]
0x1807f7c31  mov     [rbp+57h+var_88], 1
0x1807f7c38  mov     ebx, r13d
0x1807f7c3b  mov     rcx, [rsi+rbx*8+60h]
0x1807f7c40  mov     rax, [rcx]
0x1807f7c43  mov     rax, [rax+20h]
0x1807f7c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7c4c  test    eax, eax
0x1807f7c4e  js      short loc_1807F7C62
0x1807f7c50  xor     ebx, ebx
0x1807f7c52  cmp     [rsi+11h], bl
0x1807f7c55  jz      short loc_1807F7CB2
0x1807f7c57  cmp     [rbp+57h+var_88], ebx
0x1807f7c5a  jz      short loc_1807F7CD2
0x1807f7c5c  mov     byte ptr [rsi+11h], 1
0x1807f7c60  jmp     short loc_1807F7CB2
0x1807f7c62  cmp     eax, 8000000Ah
0x1807f7c67  jnz     short loc_1807F7CB0
0x1807f7c69  cmp     [rdi+rbx*8], r15
0x1807f7c6d  jz      short loc_1807F7C7A
0x1807f7c6f  mov     edx, r13d; unsigned int
0x1807f7c72  mov     rcx, rdi; this
0x1807f7c75  call    ?PassivateIsUrlAllowedLookupCallback@CLookupItem@CBaseURLBlockFilter@@QEAAXK@Z; CBaseURLBlockFilter::CLookupItem::PassivateIsUrlAllowedLookupCallback(ulong)
0x1807f7c7a  mov     rax, [r14]
0x1807f7c7d  mov     rcx, r14
0x1807f7c80  mov     rax, [rax+8]
0x1807f7c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7c89  mov     [rdi+rbx*8], r14
0x1807f7c8d  xor     ebx, ebx
0x1807f7c8f  cmp     [rsi+14h], bl
0x1807f7c92  jnz     short loc_1807F7CAA
0x1807f7c94  mov     rcx, [rsi+8]
0x1807f7c98  mov     dl, 1
0x1807f7c9a  mov     rax, [rcx]
0x1807f7c9d  mov     rax, [rax+60h]
0x1807f7ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807f7ca6  mov     byte ptr [rsi+14h], 1
0x1807f7caa  mov     [rbp+57h+var_9E], 1
0x1807f7cae  jmp     short loc_1807F7CB2
0x1807f7cb0  xor     ebx, ebx
0x1807f7cb2  lea     rcx, [rbp+57h+var_70]
0x1807f7cb6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1807f7cbb  mov     rax, [r14]
  ... truncated ...
```
