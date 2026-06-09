# CIISWebService::CreateNewSite(ushort *,tagVARIANT *,ushort *,tagVARIANT,tagVARIANT *)

- ea: `0x180008c40`
- end: `0x180008fba`
- name: `?CreateNewSite@CIISWebService@@UEAAJPEAGPEAUtagVARIANT@@0U2@1@Z`
- size: `890`
- prototype: `__int64 __fastcall(CIISWebService *this, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 *, struct tagVARIANT *pvarSrc, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001048`
- `0x180001054`
- `0x180003efc`
- `0x1800089e8`
- `0x180008c40`
- `0x18000e380`
- `0x180010570`
- `0x180010638`
- `0x180012010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180008e8e`
- `msvcrt!wcscpy_s` at `0x180008e8e`
- `msvcrt!_wcsicmp` at `0x180008d14`
- `msvcrt!_wcsicmp` at `0x180008d14`
- `ole32!CoGetClassObject` at `0x180008da0`
- `ole32!CoGetClassObject` at `0x180008da0`
- `OLEAUT32!__imp_VariantInit` at `0x180008d35`
- `OLEAUT32!__imp_VariantInit` at `0x180008df2`
- `OLEAUT32!__imp_VariantInit` at `0x180008f3c`
- `OLEAUT32!__imp_VariantInit` at `0x180008d35`
- `OLEAUT32!__imp_VariantInit` at `0x180008df2`
- `OLEAUT32!__imp_VariantInit` at `0x180008f3c`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180008e00`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180008e00`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008d53`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008e33`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008d53`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008e33`
- `ATL!__imp_AtlComPtrAssign` at `0x180008ca8`
- `ATL!__imp_AtlComPtrAssign` at `0x180008ca8`

## pseudocode

```c
__int64 __fastcall CIISWebService::CreateNewSite(
        CIISWebService *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        unsigned __int16 *a4,
        struct tagVARIANT *pvarSrc,
        struct tagVARIANT *a6)
{
  __int64 v6; // rbx
  unsigned __int16 *v11; // rdi
  struct tagVARIANT *v12; // rsi
  const wchar_t *v13; // rcx
  int ClassObject; // ebx
  LONG *v15; // r14
  CIISWebService *v16; // rcx
  __int64 v17; // rax
  rsize_t v18; // rbx
  wchar_t *v19; // rax
  __int64 v20; // rdx
  unsigned __int16 v21; // ax
  unsigned __int16 *v22; // rcx
  int v23; // eax
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v26; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarDest; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  __int128 pvReserved; // [rsp+88h] [rbp-78h] BYREF
  __int128 v31; // [rsp+98h] [rbp-68h]
  struct tagVARIANT v32; // [rsp+B0h] [rbp-50h] BYREF
  void **v33; // [rsp+D0h] [rbp-30h] BYREF
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v35; // [rsp+108h] [rbp+8h] BYREF
  char v36; // [rsp+110h] [rbp+10h]
  LONG lVal; // [rsp+160h] [rbp+60h] BYREF
  LONG v38; // [rsp+168h] [rbp+68h] BYREF

  v6 = *((_QWORD *)this + 15);
  v33 = &CSecConLib::`vftable';
  lVal = 0;
  v38 = 0;
  pProxy = 0;
  pvReserved = 0;
  ppv = 0;
  v31 = 0;
  CSafeAutoCriticalSection::CSafeAutoCriticalSection(&CriticalSection);
  v35 = 0;
  AtlComPtrAssign(&v35, v6);
  v36 = 1;
  v26 = 0;
  v11 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !a2 || !a3 || !a4 || (v12 = a6) == 0 )
  {
    ClassObject = -2147467261;
    goto LABEL_39;
  }
  v13 = (const wchar_t *)*((_QWORD *)this + 8);
  pvReserved = 0;
  v31 = 0;
  if ( v13 && _wcsicmp(v13, L"localhost") )
    *((_QWORD *)&pvReserved + 1) = *((_QWORD *)this + 8);
  else
    *((_QWORD *)&pvReserved + 1) = 0;
  *(_QWORD *)&v31 = 0;
  VariantInit(&pvarg);
  ClassObject = VariantChangeType(&pvarg, pvarSrc, 0, 3u);
  if ( ClassObject >= 0 )
  {
    if ( pvarg.vt == 3 && pvarg.lVal )
    {
      v15 = &lVal;
      lVal = pvarg.lVal;
    }
    else
    {
      v15 = 0;
    }
    ClassObject = CoGetClassObject(&CLSID_WamAdmin, 0x15u, &pvReserved, &IID_IClassFactory, &ppv);
    if ( ClassObject >= 0 )
    {
      ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, IUnknown **))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      0,
                      &IID_IIISApplicationAdmin,
                      &pProxy);
      if ( ClassObject >= 0 )
      {
        ClassObject = SetProxyImpersonationLevel(pProxy);
        if ( ClassObject >= 0 )
        {
          VariantInit(&pvarDest);
          ClassObject = VariantCopyInd(&pvarDest, a3);
          if ( ClassObject >= 0 )
          {
            if ( pvarDest.vt == 9 )
            {
              ClassObject = VariantChangeType(&pvarDest, &pvarDest, 0, 8u);
              if ( ClassObject < 0 )
                goto LABEL_39;
              v17 = -1;
              do
                ++v17;
              while ( *(_WORD *)(pvarDest.llVal + 2 * v17) );
              v18 = v17 + 2;
              v19 = (wchar_t *)operator new[](saturated_mul(v17 + 2, 2u));
              v11 = v19;
              if ( !v19 )
              {
                ClassObject = -2147024882;
                goto LABEL_39;
              }
              wcscpy_s(v19, v18, pvarDest.bstrVal);
              v21 = *v11;
              v22 = v11;
              while ( v21 )
              {
                if ( v21 == 44 )
                  *v22 = 0;
                v21 = *++v22;
              }
              v22[1] = 0;
            }
            else
            {
              if ( pvarDest.vt != 8204 )
                goto LABEL_37;
              v32 = pvarDest;
              v23 = CIISWebService::ConvertArrayToMultiSZ(v16, &v32, &v26);
              v11 = v26;
              ClassObject = v23;
              if ( v23 < 0 )
                goto LABEL_39;
            }
            if ( v11 && (!v36 || v35) )
            {
              ClassObject = CSiteCreator::InternalCreateNewSite(&v33, v20, a2, v11, a4, pProxy, &v38, v15);
              if ( ClassObject >= 0 )
              {
                VariantInit(v12);
                v12->lVal = v38;
                v12->vt = 3;
              }
              goto LABEL_39;
            }
LABEL_37:
            ClassObject = -2147024809;
          }
        }
      }
    }
  }
LABEL_39:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v11 )
    operator delete(v11);
  CSiteCreator::~CSiteCreator((CSiteCreator *)&v33);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x180008c40  mov     [rsp-8+arg_10], rbx
0x180008c45  push    rbp
0x180008c46  push    rsi
0x180008c47  push    rdi
0x180008c48  push    r12
0x180008c4a  push    r13
0x180008c4c  push    r14
0x180008c4e  push    r15
0x180008c50  lea     rbp, [rsp-20h]
0x180008c55  sub     rsp, 120h
0x180008c5c  mov     rbx, [rcx+78h]
0x180008c60  lea     rax, ??_7CSecConLib@@6B@; const CSecConLib::`vftable'
0x180008c67  xor     esi, esi
0x180008c69  mov     [rbp+50h+var_80], rax
0x180008c6d  xorps   xmm0, xmm0
0x180008c70  mov     [rbp+50h+arg_0], esi
0x180008c73  mov     r14, rcx
0x180008c76  mov     [rbp+50h+arg_8], esi
0x180008c79  lea     rcx, [rbp+50h+CriticalSection]; lpCriticalSection
0x180008c7d  mov     [rsp+150h+pProxy], rsi
0x180008c82  movups  [rbp+50h+pvReserved], xmm0
0x180008c86  mov     [rsp+150h+var_100], rsi
0x180008c8b  mov     r12, r9
0x180008c8e  movups  [rbp+50h+var_B8], xmm0
0x180008c92  mov     r15, r8
0x180008c95  mov     r13, rdx
0x180008c98  call    ??0CSafeAutoCriticalSection@@QEAA@XZ; CSafeAutoCriticalSection::CSafeAutoCriticalSection(void)
0x180008c9d  mov     rdx, rbx
0x180008ca0  mov     [rbp+50h+var_48], rsi
0x180008ca4  lea     rcx, [rbp+50h+var_48]
0x180008ca8  call    cs:__imp_AtlComPtrAssign
0x180008cae  xor     eax, eax
0x180008cb0  mov     [rbp+50h+var_40], 1
0x180008cb4  mov     qword ptr [rsp+150h+pvarDest+10h], rax
0x180008cb9  xorps   xmm0, xmm0
0x180008cbc  mov     [rsp+150h+var_108], rsi
0x180008cc1  mov     edi, esi
0x180008cc3  mov     qword ptr [rbp+50h+pvarg+10h], rax
0x180008cc7  movups  xmmword ptr [rsp+150h+pvarDest], xmm0
0x180008ccc  movups  xmmword ptr [rsp+150h+pvarg], xmm0
0x180008cd1  test    r13, r13
0x180008cd4  jz      loc_180008F56
0x180008cda  test    r15, r15
0x180008cdd  jz      loc_180008F56
0x180008ce3  test    r12, r12
0x180008ce6  jz      loc_180008F56
0x180008cec  mov     rsi, [rbp+50h+arg_28]
0x180008cf3  test    rsi, rsi
0x180008cf6  jz      loc_180008F56
0x180008cfc  mov     rcx, [r14+40h]; String1
0x180008d00  movups  [rbp+50h+pvReserved], xmm0
0x180008d04  movups  [rbp+50h+var_B8], xmm0
0x180008d08  test    rcx, rcx
0x180008d0b  jz      short loc_180008D28
0x180008d0d  lea     rdx, aLocalhost; "localhost"
0x180008d14  call    cs:__imp__wcsicmp
0x180008d1a  test    eax, eax
0x180008d1c  jz      short loc_180008D28
0x180008d1e  mov     rax, [r14+40h]
0x180008d22  mov     qword ptr [rbp+50h+pvReserved+8], rax
0x180008d26  jmp     short loc_180008D2C
0x180008d28  mov     qword ptr [rbp+50h+pvReserved+8], rdi
0x180008d2c  lea     rcx, [rsp+150h+pvarg]; pvarg
0x180008d31  mov     qword ptr [rbp+50h+var_B8], rdi
0x180008d35  call    cs:__imp_VariantInit
0x180008d3b  mov     rdx, [rbp+50h+pvarSrc]; pvarSrc
0x180008d42  lea     rcx, [rsp+150h+pvarg]; pvargDest
0x180008d47  mov     r14d, 3
0x180008d4d  xor     r8d, r8d; wFlags
0x180008d50  mov     r9d, r14d; vt
0x180008d53  call    cs:__imp_VariantChangeType
0x180008d59  mov     ebx, eax
0x180008d5b  test    eax, eax
0x180008d5d  js      loc_180008F5B
0x180008d63  cmp     word ptr [rsp+150h+pvarg], r14w
0x180008d69  jnz     short loc_180008D7C
0x180008d6b  mov     eax, dword ptr [rsp+150h+pvarg+8]
0x180008d6f  test    eax, eax
0x180008d71  jz      short loc_180008D7C
0x180008d73  lea     r14, [rbp+50h+arg_0]
0x180008d77  mov     [rbp+50h+arg_0], eax
0x180008d7a  jmp     short loc_180008D7F
0x180008d7c  xor     r14d, r14d
0x180008d7f  lea     rax, [rsp+150h+var_100]
0x180008d84  mov     edx, 15h; dwClsContext
0x180008d89  lea     r9, IID_IClassFactory; riid
0x180008d90  mov     [rsp+150h+ppv], rax; ppv
0x180008d95  lea     r8, [rbp+50h+pvReserved]; pvReserved
0x180008d99  lea     rcx, CLSID_WamAdmin; rclsid
0x180008da0  call    cs:__imp_CoGetClassObject
0x180008da6  mov     ebx, eax
0x180008da8  test    eax, eax
0x180008daa  js      loc_180008F5B
0x180008db0  mov     rcx, [rsp+150h+var_100]
0x180008db5  lea     r9, [rsp+150h+pProxy]
0x180008dba  lea     r8, IID_IIISApplicationAdmin
0x180008dc1  xor     edx, edx
0x180008dc3  mov     rax, [rcx]
0x180008dc6  mov     rax, [rax+18h]
0x180008dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dcf  mov     ebx, eax
0x180008dd1  test    eax, eax
0x180008dd3  js      loc_180008F5B
0x180008dd9  mov     rcx, [rsp+150h+pProxy]; pProxy
0x180008dde  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x180008de3  mov     ebx, eax
0x180008de5  test    eax, eax
0x180008de7  js      loc_180008F5B
0x180008ded  lea     rcx, [rsp+150h+pvarDest]; pvarg
0x180008df2  call    cs:__imp_VariantInit
0x180008df8  mov     rdx, r15; pvargSrc
0x180008dfb  lea     rcx, [rsp+150h+pvarDest]; pvarDest
0x180008e00  call    cs:__imp_VariantCopyInd
0x180008e06  xor     r15d, r15d
0x180008e09  mov     ebx, eax
0x180008e0b  test    eax, eax
0x180008e0d  js      loc_180008F5B
0x180008e13  lea     eax, [r15+9]
0x180008e17  cmp     ax, word ptr [rsp+150h+pvarDest]
0x180008e1c  jnz     loc_180008EB9
0x180008e22  lea     r9d, [r15+8]; vt
0x180008e26  xor     r8d, r8d; wFlags
0x180008e29  lea     rdx, [rsp+150h+pvarDest]; pvarSrc
0x180008e2e  lea     rcx, [rsp+150h+pvarDest]; pvargDest
0x180008e33  call    cs:__imp_VariantChangeType
0x180008e39  mov     ebx, eax
0x180008e3b  test    eax, eax
0x180008e3d  js      loc_180008F5B
0x180008e43  mov     rcx, qword ptr [rsp+150h+pvarDest+8]
0x180008e48  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008e4c  mov     rax, r8
0x180008e4f  inc     rax
0x180008e52  cmp     [rcx+rax*2], r15w
0x180008e57  jnz     short loc_180008E4F
0x180008e59  lea     rbx, [rax+2]
0x180008e5d  mov     eax, 2
0x180008e62  mul     rbx
0x180008e65  cmovb   rax, r8
0x180008e69  mov     rcx, rax; unsigned __int64
0x180008e6c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008e71  mov     rdi, rax
0x180008e74  test    rax, rax
0x180008e77  jnz     short loc_180008E83
0x180008e79  mov     ebx, 8007000Eh
0x180008e7e  jmp     loc_180008F5B
0x180008e83  mov     r8, qword ptr [rsp+150h+pvarDest+8]; Source
0x180008e88  mov     rdx, rbx; SizeInWords
0x180008e8b  mov     rcx, rdi; Destination
0x180008e8e  call    cs:__imp_wcscpy_s
0x180008e94  movzx   eax, word ptr [rdi]
0x180008e97  mov     rcx, rdi
0x180008e9a  test    ax, ax
0x180008e9d  jz      short loc_180008EB2
0x180008e9f  cmp     ax, 2Ch ; ','
0x180008ea3  jnz     short loc_180008EA9
0x180008ea5  mov     [rcx], r15w
0x180008ea9  add     rcx, 2
0x180008ead  movzx   eax, word ptr [rcx]
0x180008eb0  jmp     short loc_180008E9A
0x180008eb2  mov     [rcx+2], r15w
0x180008eb7  jmp     short loc_180008EF6
0x180008eb9  mov     eax, 200Ch
0x180008ebe  cmp     ax, word ptr [rsp+150h+pvarDest]
0x180008ec3  jnz     loc_180008F4F
0x180008ec9  movups  xmm0, xmmword ptr [rsp+150h+pvarDest]
0x180008ece  lea     r8, [rsp+150h+var_108]; unsigned __int16 **
0x180008ed3  movsd   xmm1, qword ptr [rsp+150h+pvarDest+10h]
0x180008ed9  lea     rdx, [rbp+50h+var_A0]; struct tagVARIANT
0x180008edd  movaps  xmmword ptr [rbp+50h+var_A0], xmm0
0x180008ee1  movsd   qword ptr [rbp+50h+var_A0+10h], xmm1
0x180008ee6  call    ?ConvertArrayToMultiSZ@CIISWebService@@IEAAJUtagVARIANT@@PEAPEAG@Z; CIISWebService::ConvertArrayToMultiSZ(tagVARIANT,ushort * *)
0x180008eeb  mov     rdi, [rsp+150h+var_108]
0x180008ef0  mov     ebx, eax
0x180008ef2  test    eax, eax
0x180008ef4  js      short loc_180008F5B
0x180008ef6  test    rdi, rdi
0x180008ef9  jz      short loc_180008F4F
0x180008efb  cmp     [rbp+50h+var_40], r15b
0x180008eff  jz      short loc_180008F07
0x180008f01  cmp     [rbp+50h+var_48], r15
0x180008f05  jz      short loc_180008F4F
0x180008f07  mov     rax, [rsp+150h+pProxy]
0x180008f0c  lea     rcx, [rbp+50h+arg_8]
0x180008f10  mov     [rsp+150h+var_118], r14
0x180008f15  mov     r9, rdi
0x180008f18  mov     [rsp+150h+var_120], rcx
0x180008f1d  mov     r8, r13
0x180008f20  mov     [rsp+150h+var_128], rax
0x180008f25  lea     rcx, [rbp+50h+var_80]
0x180008f29  mov     [rsp+150h+ppv], r12
0x180008f2e  call    ?InternalCreateNewSite@CSiteCreator@@AEAAJW4tag_SC_SUPPORTED_SERVICES@@PEBG11PEAUIIISApplicationAdmin@@PEAK3@Z; CSiteCreator::InternalCreateNewSite(tag_SC_SUPPORTED_SERVICES,ushort const *,ushort const *,ushort const *,IIISApplicationAdmin *,ulong *,ulong *)
0x180008f33  mov     ebx, eax
0x180008f35  test    eax, eax
0x180008f37  js      short loc_180008F5B
0x180008f39  mov     rcx, rsi; pvarg
0x180008f3c  call    cs:__imp_VariantInit
0x180008f42  mov     eax, [rbp+50h+arg_8]
0x180008f45  mov     [rsi+8], eax
0x180008f48  mov     word ptr [rsi], 3
0x180008f4d  jmp     short loc_180008F5B
0x180008f4f  mov     ebx, 80070057h
0x180008f54  jmp     short loc_180008F5B
0x180008f56  mov     ebx, 80004003h
0x180008f5b  mov     rcx, [rsp+150h+var_100]
0x180008f60  test    rcx, rcx
0x180008f63  jz      short loc_180008F71
0x180008f65  mov     rax, [rcx]
0x180008f68  mov     rax, [rax+10h]
0x180008f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f71  mov     rcx, [rsp+150h+pProxy]
0x180008f76  test    rcx, rcx
0x180008f79  jz      short loc_180008F87
0x180008f7b  mov     rax, [rcx]
0x180008f7e  mov     rax, [rax+10h]
0x180008f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f87  test    rdi, rdi
0x180008f8a  jz      short loc_180008F94
0x180008f8c  mov     rcx, rdi; Block
0x180008f8f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008f94  lea     rcx, [rbp+50h+var_80]; this
0x180008f98  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180008f9d  mov     eax, ebx
0x180008f9f  mov     rbx, [rsp+150h+arg_10]
0x180008fa7  add     rsp, 120h
0x180008fae  pop     r15
0x180008fb0  pop     r14
0x180008fb2  pop     r13
0x180008fb4  pop     r12
0x180008fb6  pop     rdi
0x180008fb7  pop     rsi
0x180008fb8  pop     rbp
0x180008fb9  retn
```
