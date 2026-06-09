# CMapperCache::ProcessOneCategory(_GUID const &,ICreateDevEnum *)

- ea: `0x18000e770`
- end: `0x18000eb79`
- name: `?ProcessOneCategory@CMapperCache@@AEAAJAEBU_GUID@@PEAUICreateDevEnum@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(CMapperCache *__hidden this, const struct _GUID *, struct ICreateDevEnum *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180065f88`

## callees

- `0x18000e770`
- `0x18000ed50`
- `0x18000ef80`
- `0x18001a050`
- `0x180020e20`
- `0x18002a3a0`
- `0x180038458`
- `0x1800388a0`
- `0x18015bb8c`
- `0x18015e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e9a5`
- `ole32!CoTaskMemFree` at `0x18000e9d0`
- `ole32!CoTaskMemFree` at `0x18000e9a5`
- `ole32!CoTaskMemFree` at `0x18000e9d0`
- `ole32!CoTaskMemAlloc` at `0x18000e937`
- `ole32!CoTaskMemAlloc` at `0x18000e937`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea1b`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea1b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000e8d7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000e8d7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000ea03`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000ea03`

## pseudocode

```c
__int64 __fastcall CMapperCache::ProcessOneCategory(
        CMapperCache *this,
        const struct _GUID *a2,
        struct ICreateDevEnum *a3)
{
  struct ICreateDevEnumVtbl *lpVtbl; // r8
  bool v5; // cc
  __int64 v6; // r9
  CMapperCache *v7; // rdi
  __int64 result; // rax
  signed int v9; // r15d
  CMapperCache::CMapFilter *v10; // rax
  CMapperCache::CMapFilter *v11; // r13
  int v12; // esi
  __int64 *v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // r12d
  CUnsquish *v17; // rcx
  int v18; // ebx
  void *v19; // r14
  int v20; // edi
  int v21; // ebx
  struct REGFILTER2 *v22; // rax
  struct REGFILTER2 *v23; // rsi
  unsigned __int8 *v24; // r9
  __int64 v25; // rax
  LPVOID v26; // rax
  unsigned int v27; // edx
  int v28; // r15d
  __int64 *v29; // rcx
  SIZE_T cb; // [rsp+30h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-71h] BYREF
  __int64 *v32; // [rsp+40h] [rbp-69h] BYREF
  int v33; // [rsp+48h] [rbp-61h] BYREF
  int v34; // [rsp+4Ch] [rbp-5Dh]
  __int64 v35; // [rsp+50h] [rbp-59h] BYREF
  __int64 v36; // [rsp+58h] [rbp-51h] BYREF
  void *ppvData; // [rsp+60h] [rbp-49h] BYREF
  struct REGFILTER_REG1 *v38; // [rsp+68h] [rbp-41h] BYREF
  VARIANTARG psa; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int8 *v40; // [rsp+88h] [rbp-21h]
  LPVOID *p_pv; // [rsp+90h] [rbp-19h]
  __int64 *v42; // [rsp+98h] [rbp-11h]
  CMapperCache *v43; // [rsp+A0h] [rbp-9h]
  _DWORD v44[2]; // [rsp+A8h] [rbp-1h] BYREF
  struct REGFILTER2 *v45; // [rsp+B0h] [rbp+7h]
  struct _GUID Buf1; // [rsp+B8h] [rbp+Fh] BYREF

  v43 = this;
  lpVtbl = a3->lpVtbl;
  v5 = *((_DWORD *)this + 13) <= 0x200000u;
  v6 = 8;
  v7 = this;
  v36 = 0;
  if ( v5 )
    v6 = 0;
  result = ((__int64 (__fastcall *)(struct ICreateDevEnum *, const struct _GUID *, __int64 *, __int64))lpVtbl->CreateClassEnumerator)(
             a3,
             a2,
             &v36,
             v6);
  if ( !(_DWORD)result )
  {
    v33 = 0;
    v32 = 0;
    while ( 1 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 **, int *))(*(_QWORD *)v36 + 24LL))(v36, 1, &v32, &v33);
      if ( v9 )
      {
LABEL_40:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        return (unsigned int)v9;
      }
      v10 = (CMapperCache::CMapFilter *)operator new(0x18u);
      v11 = v10;
      if ( !v10 )
      {
        v29 = v32;
        v9 = -2147024882;
        *((_DWORD *)v7 + 10) = 1;
        (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
        goto LABEL_40;
      }
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      v12 = 31;
      v13 = v32;
      v42 = v32;
      v34 = 31;
      v14 = *v32;
      v35 = 0;
      if ( (*(int (__fastcall **)(__int64 *, _QWORD, _QWORD, GUID *, __int64 *))(v14 + 72))(
             v32,
             0,
             0,
             &IID_IPropertyBag,
             &v35) < 0 )
        goto LABEL_33;
      *(_QWORD *)&psa.vt = 8209;
      *(_OWORD *)&psa.decVal.Lo32 = 0u;
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v35 + 24LL))(
             v35,
             L"FilterData",
             &psa,
             0) >= 0 )
      {
        ppvData = 0;
        v16 = *(_DWORD *)(psa.llVal + 24);
        if ( SafeArrayAccessData(psa.parray, &ppvData) >= 0 )
        {
          pv = 0;
          p_pv = &pv;
          v18 = 0;
          v40 = (unsigned __int8 *)ppvData;
          v19 = ppvData;
          v38 = (struct REGFILTER_REG1 *)ppvData;
          v20 = 0;
          while ( v20 < 1 )
          {
            LODWORD(cb) = 0;
            v18 = CUnsquish::CbRequiredUnquishAndValidate(v17, (const unsigned __int8 *)v19, (unsigned int *)&cb, v16);
            if ( v18 < 0 )
              goto LABEL_19;
            v21 = cb;
            v22 = (struct REGFILTER2 *)CoTaskMemAlloc((unsigned int)cb);
            v23 = v22;
            if ( !v22 )
            {
              v18 = -2147024882;
LABEL_19:
              _mm_lfence();
              CoTaskMemFree(pv);
              v26 = 0;
              pv = 0;
              goto LABEL_21;
            }
            v24 = v40;
            v44[1] = v21 - 24;
            v22->dwVersion = 2;
            v22->dwMerit = *((_DWORD *)v19 + 1);
            v22->cPins = *((_DWORD *)v19 + 2);
            v45 = v22;
            v44[0] = 24;
            v18 = CUnsquish::UnSquishPins((CUnsquish *)v44, v22, &v38, v24);
            if ( v18 < 0 )
            {
              CoTaskMemFree(v23);
              v19 = v38;
              ++v20;
            }
            else
            {
              v19 = v38;
              v25 = v20++;
              v17 = (CUnsquish *)(&p_pv)[v25];
              *(_QWORD *)v17 = v23;
            }
          }
          if ( v18 < 0 )
            goto LABEL_19;
          v26 = pv;
LABEL_21:
          if ( v18 )
          {
            v12 = v34;
          }
          else
          {
            *((_QWORD *)v11 + 1) = v26;
            v12 = 0;
          }
          SafeArrayUnaccessData(psa.parray);
          v13 = v42;
          v7 = v43;
        }
        VariantClear(&psa);
        if ( !v12 )
        {
          *(_QWORD *)v11 = v13;
          (*(void (__fastcall **)(__int64 *))(*v13 + 8))(v13);
          Buf1 = 0;
          if ( *((_BYTE *)v7 + 64) )
          {
            if ( GetMonikerClsid(*(struct IMoniker **)v11, &Buf1) >= 0 && !memcmp_0(&Buf1, &CLSID_Dither, 0x10u) )
              *(_DWORD *)(*((_QWORD *)v11 + 1) + 4LL) = 0x800000;
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      if ( v12 )
      {
LABEL_33:
        CMapperCache::CMapFilter::`scalar deleting destructor'(v11, v15);
        if ( v12 != 31 )
        {
          v28 = v12;
          goto LABEL_36;
        }
        v9 = 0;
      }
      else if ( !CBaseList::AddTailI(*((CBaseList **)v7 + 7), v11) )
      {
        v28 = 8;
        CMapperCache::CMapFilter::`scalar deleting destructor'(v11, v27);
LABEL_36:
        v9 = v28 | 0x80070000;
        *((_DWORD *)v7 + 10) = 1;
      }
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
      if ( v9 < 0 )
        goto LABEL_40;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e770  push    rbp
0x18000e772  push    rdi
0x18000e773  push    r14
0x18000e775  lea     rbp, [rsp-47h]
0x18000e77a  sub     rsp, 0F0h
0x18000e781  mov     rax, cs:__security_cookie
0x18000e788  xor     rax, rsp
0x18000e78b  mov     [rbp+57h+var_38], rax
0x18000e78f  mov     r10, r8
0x18000e792  mov     [rbp+57h+var_60], rcx
0x18000e796  mov     r8, [r8]
0x18000e799  xor     r14d, r14d
0x18000e79c  cmp     dword ptr [rcx+34h], 200000h
0x18000e7a3  mov     r9d, 8
0x18000e7a9  mov     rdi, rcx
0x18000e7ac  mov     [rbp+57h+var_A8], r14
0x18000e7b0  cmovbe  r9d, r14d
0x18000e7b4  mov     rcx, r10
0x18000e7b7  mov     rax, [r8+18h]
0x18000e7bb  lea     r8, [rbp+57h+var_A8]
0x18000e7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c4  test    eax, eax
0x18000e7c6  jnz     loc_18000EB60
0x18000e7cc  mov     [rsp+100h+arg_18], rbx
0x18000e7d4  mov     [rsp+100h+var_18], rsi
0x18000e7dc  mov     [rsp+100h+var_20], r12
0x18000e7e4  mov     r12d, 2011h
0x18000e7ea  mov     [rsp+100h+var_30], r15
0x18000e7f2  mov     [rsp+100h+var_28], r13
0x18000e7fa  mov     [rbp+57h+var_B8], r14d
0x18000e7fe  mov     [rbp+57h+var_C0], r14
0x18000e802  mov     rcx, [rbp+57h+var_A8]
0x18000e806  lea     r9, [rbp+57h+var_B8]
0x18000e80a  lea     r8, [rbp+57h+var_C0]
0x18000e80e  mov     edx, 1
0x18000e813  mov     rax, [rcx]
0x18000e816  mov     rax, [rax+18h]
0x18000e81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81f  mov     r15d, eax
0x18000e822  test    eax, eax
0x18000e824  jnz     loc_18000EB25
0x18000e82a  mov     ecx, 18h; Size
0x18000e82f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e834  mov     r13, rax
0x18000e837  test    rax, rax
0x18000e83a  jz      loc_18000EB08
0x18000e840  mov     [rax], r14
0x18000e843  lea     rcx, [rbp+57h+var_B0]
0x18000e847  mov     [rax+8], r14
0x18000e84b  lea     r9, IID_IPropertyBag
0x18000e852  mov     [rax+10h], r14
0x18000e856  mov     esi, 1Fh
0x18000e85b  mov     rbx, [rbp+57h+var_C0]
0x18000e85f  xor     r8d, r8d
0x18000e862  mov     [rsp+100h+var_E0], rcx
0x18000e867  xor     edx, edx
0x18000e869  mov     rcx, rbx
0x18000e86c  mov     [rbp+57h+var_68], rbx
0x18000e870  mov     [rbp+57h+var_B4], esi
0x18000e873  mov     rax, [rbx]
0x18000e876  mov     [rbp+57h+var_B0], r14
0x18000e87a  mov     rax, [rax+48h]
0x18000e87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e883  test    eax, eax
0x18000e885  js      loc_18000EAC2
0x18000e88b  mov     rcx, [rbp+57h+var_B0]
0x18000e88f  lea     r8, [rbp+57h+psa]
0x18000e893  xor     eax, eax
0x18000e895  lea     rdx, aFilterdata; "FilterData"
0x18000e89c  mov     [rbp+57h+var_80], rax
0x18000e8a0  xorps   xmm0, xmm0
0x18000e8a3  movups  xmmword ptr [rbp+57h+psa], xmm0
0x18000e8a7  mov     word ptr [rbp+57h+psa], r12w
0x18000e8ac  xor     r9d, r9d
0x18000e8af  mov     [rbp+57h+psa+8], r14
0x18000e8b3  mov     rax, [rcx]
0x18000e8b6  mov     rax, [rax+18h]
0x18000e8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8bf  test    eax, eax
0x18000e8c1  js      loc_18000EA81
0x18000e8c7  mov     rcx, [rbp+57h+psa+8]; psa
0x18000e8cb  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18000e8cf  mov     [rbp+57h+ppvData], r14
0x18000e8d3  mov     r12d, [rcx+18h]
0x18000e8d7  call    cs:__imp_SafeArrayAccessData
0x18000e8de  nop     dword ptr [rax+rax+00h]
0x18000e8e3  test    eax, eax
0x18000e8e5  js      loc_18000EA17
0x18000e8eb  lea     rax, [rbp+57h+pv]
0x18000e8ef  mov     [rbp+57h+pv], r14
0x18000e8f3  mov     [rbp+57h+var_70], rax
0x18000e8f7  mov     ebx, r14d
0x18000e8fa  mov     rax, [rbp+57h+ppvData]
0x18000e8fe  mov     [rbp+57h+var_78], rax
0x18000e902  mov     r14, rax
0x18000e905  mov     [rbp+57h+var_98], rax
0x18000e909  xor     eax, eax
0x18000e90b  mov     edi, eax
0x18000e90d  cmp     edi, 1
0x18000e910  jge     loc_18000E9C5
0x18000e916  mov     r9d, r12d; unsigned int
0x18000e919  mov     dword ptr [rbp+57h+cb], eax
0x18000e91c  lea     r8, [rbp+57h+cb]; unsigned int *
0x18000e920  mov     rdx, r14; unsigned __int8 *
0x18000e923  call    ?CbRequiredUnquishAndValidate@CUnsquish@@AEAAJPEBEPEAKK@Z; CUnsquish::CbRequiredUnquishAndValidate(uchar const *,ulong *,ulong)
0x18000e928  mov     ebx, eax
0x18000e92a  test    eax, eax
0x18000e92c  js      loc_18000E9C9
0x18000e932  mov     ebx, dword ptr [rbp+57h+cb]
0x18000e935  mov     ecx, ebx; cb
0x18000e937  call    cs:__imp_CoTaskMemAlloc
0x18000e93e  nop     dword ptr [rax+rax+00h]
0x18000e943  mov     rsi, rax
0x18000e946  test    rax, rax
0x18000e949  jz      short loc_18000E9BE
0x18000e94b  mov     r9, [rbp+57h+var_78]; unsigned __int8 *
0x18000e94f  lea     ecx, [rbx-18h]
0x18000e952  mov     [rbp+57h+var_54], ecx
0x18000e955  lea     r8, [rbp+57h+var_98]; struct REGFILTER_REG1 **
0x18000e959  mov     dword ptr [rax], 2
0x18000e95f  mov     rdx, rax; struct REGFILTER2 *
0x18000e962  mov     ecx, [r14+4]
0x18000e966  mov     [rax+4], ecx
0x18000e969  mov     ecx, [r14+8]
0x18000e96d  mov     [rax+8], ecx
0x18000e970  lea     rcx, [rbp+57h+var_58]; this
0x18000e974  mov     [rbp+57h+var_50], rax
0x18000e978  mov     [rbp+57h+var_58], 18h
0x18000e97f  call    ?UnSquishPins@CUnsquish@@AEAAJPEAUREGFILTER2@@PEAPEBUREGFILTER_REG1@@PEBE@Z; CUnsquish::UnSquishPins(REGFILTER2 *,REGFILTER_REG1 const * *,uchar const *)
0x18000e984  mov     ebx, eax
0x18000e986  test    eax, eax
0x18000e988  js      short loc_18000E9A2
0x18000e98a  mov     r14, [rbp+57h+var_98]
0x18000e98e  movsxd  rax, edi
0x18000e991  inc     edi
0x18000e993  mov     rcx, [rbp+rax*8+57h+var_70]
0x18000e998  xor     eax, eax
0x18000e99a  mov     [rcx], rsi
0x18000e99d  jmp     loc_18000E90D
0x18000e9a2  mov     rcx, rsi; pv
0x18000e9a5  call    cs:__imp_CoTaskMemFree
0x18000e9ac  nop     dword ptr [rax+rax+00h]
0x18000e9b1  mov     r14, [rbp+57h+var_98]
0x18000e9b5  inc     edi
0x18000e9b7  xor     eax, eax
0x18000e9b9  jmp     loc_18000E90D
0x18000e9be  mov     ebx, 8007000Eh
0x18000e9c3  jmp     short loc_18000E9C9
0x18000e9c5  test    ebx, ebx
0x18000e9c7  jns     short loc_18000E9E8
0x18000e9c9  lfence
0x18000e9cc  mov     rcx, [rbp+57h+pv]; pv
0x18000e9d0  call    cs:__imp_CoTaskMemFree
0x18000e9d7  nop     dword ptr [rax+rax+00h]
0x18000e9dc  xor     r14d, r14d
0x18000e9df  mov     eax, r14d
0x18000e9e2  mov     [rbp+57h+pv], rax
0x18000e9e6  jmp     short loc_18000E9EF
0x18000e9e8  mov     rax, [rbp+57h+pv]
0x18000e9ec  xor     r14d, r14d
0x18000e9ef  test    ebx, ebx
0x18000e9f1  jnz     short loc_18000E9FC
0x18000e9f3  mov     [r13+8], rax
0x18000e9f7  mov     esi, r14d
0x18000e9fa  jmp     short loc_18000E9FF
0x18000e9fc  mov     esi, [rbp+57h+var_B4]
0x18000e9ff  mov     rcx, [rbp+57h+psa+8]; psa
0x18000ea03  call    cs:__imp_SafeArrayUnaccessData
0x18000ea0a  nop     dword ptr [rax+rax+00h]
0x18000ea0f  mov     rbx, [rbp+57h+var_68]
0x18000ea13  mov     rdi, [rbp+57h+var_60]
0x18000ea17  lea     rcx, [rbp+57h+psa]; pvarg
0x18000ea1b  call    cs:__imp_VariantClear
0x18000ea22  nop     dword ptr [rax+rax+00h]
0x18000ea27  test    esi, esi
0x18000ea29  jnz     short loc_18000EA81
0x18000ea2b  mov     [r13+0], rbx
0x18000ea2f  mov     rcx, rbx
0x18000ea32  mov     rax, [rbx]
0x18000ea35  mov     rax, [rax+8]
0x18000ea39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea3e  xorps   xmm0, xmm0
0x18000ea41  movups  [rbp+57h+Buf1], xmm0
0x18000ea45  cmp     [rdi+40h], sil
0x18000ea49  jz      short loc_18000EA81
0x18000ea4b  mov     rcx, [r13+0]; struct IMoniker *
0x18000ea4f  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x18000ea53  call    ?GetMonikerClsid@@YAJPEAUIMoniker@@PEAU_GUID@@@Z; GetMonikerClsid(IMoniker *,_GUID *)
0x18000ea58  test    eax, eax
0x18000ea5a  js      short loc_18000EA81
0x18000ea5c  mov     r8d, 10h; Size
0x18000ea62  lea     rdx, CLSID_Dither; Buf2
0x18000ea69  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000ea6d  call    memcmp_0
0x18000ea72  test    eax, eax
0x18000ea74  jnz     short loc_18000EA81
0x18000ea76  mov     rax, [r13+8]
0x18000ea7a  mov     dword ptr [rax+4], 800000h
0x18000ea81  mov     rcx, [rbp+57h+var_B0]
0x18000ea85  mov     rax, [rcx]
0x18000ea88  mov     rax, [rax+10h]
0x18000ea8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea91  test    esi, esi
0x18000ea93  jnz     short loc_18000EABC
0x18000ea95  mov     rcx, [rdi+38h]; this
0x18000ea99  mov     rdx, r13; void *
0x18000ea9c  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000eaa1  test    rax, rax
0x18000eaa4  jnz     short loc_18000EAE7
0x18000eaa6  mov     rcx, r13; this
0x18000eaa9  mov     r15d, 8
0x18000eaaf  call    ??_GCMapFilter@CMapperCache@@QEAAPEAXI@Z; CMapperCache::CMapFilter::`scalar deleting destructor'(uint)
0x18000eab4  mov     r12d, 2011h
0x18000eaba  jmp     short loc_18000EAD7
0x18000eabc  mov     r12d, 2011h
0x18000eac2  mov     rcx, r13; this
0x18000eac5  call    ??_GCMapFilter@CMapperCache@@QEAAPEAXI@Z; CMapperCache::CMapFilter::`scalar deleting destructor'(uint)
0x18000eaca  cmp     esi, 1Fh
0x18000eacd  jnz     short loc_18000EAD4
0x18000eacf  mov     r15d, r14d
0x18000ead2  jmp     short loc_18000EAED
0x18000ead4  mov     r15d, esi
0x18000ead7  or      r15d, 80070000h
0x18000eade  mov     dword ptr [rdi+28h], 1
0x18000eae5  jmp     short loc_18000EAED
0x18000eae7  mov     r12d, 2011h
0x18000eaed  mov     rcx, [rbp+57h+var_C0]
0x18000eaf1  mov     rax, [rcx]
0x18000eaf4  mov     rax, [rax+10h]
0x18000eaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eafd  test    r15d, r15d
0x18000eb00  jns     loc_18000E802
0x18000eb06  jmp     short loc_18000EB25
0x18000eb08  mov     rcx, [rbp+57h+var_C0]
0x18000eb0c  mov     r15d, 8007000Eh
0x18000eb12  mov     dword ptr [rdi+28h], 1
0x18000eb19  mov     rax, [rcx]
0x18000eb1c  mov     rax, [rax+10h]
0x18000eb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb25  mov     rcx, [rbp+57h+var_A8]
0x18000eb29  mov     rax, [rcx]
0x18000eb2c  mov     rax, [rax+10h]
0x18000eb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb35  mov     r13, [rsp+100h+var_28]
0x18000eb3d  mov     eax, r15d
0x18000eb40  mov     r15, [rsp+100h+var_30]
0x18000eb48  mov     r12, [rsp+100h+var_20]
0x18000eb50  mov     rsi, [rsp+100h+var_18]
0x18000eb58  mov     rbx, [rsp+100h+arg_18]
0x18000eb60  mov     rcx, [rbp+57h+var_38]
0x18000eb64  xor     rcx, rsp; StackCookie
0x18000eb67  call    __security_check_cookie
0x18000eb6c  add     rsp, 0F0h
0x18000eb73  pop     r14
0x18000eb75  pop     rdi
0x18000eb76  pop     rbp
0x18000eb77  retn
```
