# CExtensionHandler::GetKeys(IMVKey * * *,ulong *)

- ea: `0x180013e50`
- end: `0x1800143db`
- name: `?GetKeys@CExtensionHandler@@UEAAJPEAPEAPEAUIMVKey@@PEAK@Z`
- size: `1419`
- prototype: `__int64 __fastcall(CExtensionHandler *__hidden this, struct IMVKey ***, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800017c4`
- `0x180001850`
- `0x180002034`
- `0x180013e50`
- `0x180014a6c`
- `0x180014d68`
- `0x18003661c`
- `0x180037aa8`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013f99`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014069`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014174`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014230`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800142db`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013f99`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014069`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014174`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014230`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800142db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800141b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800141b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014317`
- `OLEAUT32!__imp_VariantInit` at `0x180013e86`
- `OLEAUT32!__imp_VariantInit` at `0x180013e92`
- `OLEAUT32!__imp_VariantInit` at `0x180013e86`
- `OLEAUT32!__imp_VariantInit` at `0x180013e92`
- `OLEAUT32!__imp_VariantClear` at `0x180013fee`
- `OLEAUT32!__imp_VariantClear` at `0x180013ffa`
- `OLEAUT32!__imp_VariantClear` at `0x1800140be`
- `OLEAUT32!__imp_VariantClear` at `0x1800140ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800141bc`
- `OLEAUT32!__imp_VariantClear` at `0x1800141c8`
- `OLEAUT32!__imp_VariantClear` at `0x18001423c`
- `OLEAUT32!__imp_VariantClear` at `0x180014248`
- `OLEAUT32!__imp_VariantClear` at `0x180014323`
- `OLEAUT32!__imp_VariantClear` at `0x18001432f`
- `OLEAUT32!__imp_VariantClear` at `0x180014354`
- `OLEAUT32!__imp_VariantClear` at `0x180014360`
- `OLEAUT32!__imp_VariantClear` at `0x180013fee`
- `OLEAUT32!__imp_VariantClear` at `0x180013ffa`
- `OLEAUT32!__imp_VariantClear` at `0x1800140be`
- `OLEAUT32!__imp_VariantClear` at `0x1800140ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800141bc`
- `OLEAUT32!__imp_VariantClear` at `0x1800141c8`
- `OLEAUT32!__imp_VariantClear` at `0x18001423c`
- `OLEAUT32!__imp_VariantClear` at `0x180014248`
- `OLEAUT32!__imp_VariantClear` at `0x180014323`
- `OLEAUT32!__imp_VariantClear` at `0x18001432f`
- `OLEAUT32!__imp_VariantClear` at `0x180014354`
- `OLEAUT32!__imp_VariantClear` at `0x180014360`

## string_xrefs

- `0x180013eb3`: `Extension handler`
- `0x180014389`: `Extension handler`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CExtensionHandler::GetKeys(CExtensionHandler *this, struct IMVKey ***a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD *v11; // rsi
  _QWORD *v12; // rax
  int ExtensionKeys; // r15d
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r12
  __int64 *i; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  unsigned int v21; // r9d
  int v22; // ecx
  CMvExtensionKey **v23; // rbx
  _QWORD *v24; // r14
  __int64 j; // rbx
  __int64 v26; // rcx
  CMvExtensionKey *v27; // r10
  __int64 v28; // rcx
  unsigned int v29; // edx
  __int64 k; // rbx
  __int64 v31; // rcx
  LPVOID pv[2]; // [rsp+38h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-80h] BYREF
  VARIANTARG v35; // [rsp+60h] [rbp-68h] BYREF
  int v36; // [rsp+D0h] [rbp+8h] BYREF
  struct IMVKey ***v37; // [rsp+D8h] [rbp+10h]
  unsigned int *v38; // [rsp+E0h] [rbp+18h]
  const WCHAR *v39; // [rsp+E8h] [rbp+20h] BYREF

  v38 = a3;
  v37 = a2;
  v6 = 0;
  v36 = 0;
  VariantInit(&v35);
  VariantInit(&pvarg);
  *(_OWORD *)pv = 0;
  v11 = 0;
  if ( (unsigned int)dword_180052170 > 4 )
  {
    v39 = L"Extension handler";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180052170,
      (__int64)&word_1800494B6,
      0,
      0,
      &v39);
  }
  if ( *((_QWORD *)this + 5) - *((_QWORD *)this + 4) < 0x10u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v12 = operator new(8u);
    if ( v12 )
    {
      *v12 = 0;
      v11 = v12;
    }
    if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 2) + 56LL))(
           *((_QWORD *)this + 2),
           L"IMSI",
           &v35) < 0
      || (ExtensionKeys = CfgMgrHelper::SetSessionVariable((LPVOID *)v11, (OLECHAR *)L"IMSI", &v35), ExtensionKeys >= 0) )
    {
      ExtensionKeys = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, VARIANTARG *))(**((_QWORD **)this + 2) + 56LL))(
                        *((_QWORD *)this + 2),
                        L"ICCID",
                        &pvarg);
      if ( ExtensionKeys < 0
        || (ExtensionKeys = CfgMgrHelper::SetSessionVariable((LPVOID *)v11, (OLECHAR *)L"ICCID", &pvarg),
            ExtensionKeys >= 0) )
      {
        v17 = 0;
        for ( i = (__int64 *)*((_QWORD *)this + 4); i != *((__int64 **)this + 5); i += 2 )
        {
          v19 = *i;
          v20 = 0;
          v21 = *(_DWORD *)(*i + 600);
          if ( v21 )
          {
            while ( *(_DWORD *)(v19 + 4 * v20 + 528) != *((_DWORD *)this + 6) )
            {
              v20 = (unsigned int)(v20 + 1);
              if ( (unsigned int)v20 >= v21 )
                goto LABEL_30;
            }
            v22 = *(_DWORD *)(v19 + 616);
            if ( v22 )
            {
              v6 += v22;
              v36 = v6;
            }
          }
LABEL_30:
          ;
        }
        co_array_t<IMVKey *>::allocate((__int64)pv, v6);
        v23 = (CMvExtensionKey **)*((_QWORD *)this + 4);
        v24 = pv[0];
        while ( 1 )
        {
          if ( v23 == *((CMvExtensionKey ***)this + 5) )
          {
            if ( (_DWORD)v17 != v36 )
            {
              if ( !(_DWORD)v17 )
              {
                if ( v11 )
                {
                  if ( *v11 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
                  operator delete(v11);
                }
                if ( v24 )
                {
                  for ( j = 0; (unsigned int)j < LODWORD(pv[1]); j = (unsigned int)(j + 1) )
                  {
                    v26 = v24[j];
                    if ( v26 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                      v24[j] = 0;
                    }
                  }
                  CoTaskMemFree(v24);
                }
                VariantClear(&pvarg);
                VariantClear(&v35);
                if ( ExtensionKeys >= 0 )
                  return (unsigned int)ExtensionKeys;
                goto LABEL_73;
              }
              co_array_t<IMVKey *>::allocate((__int64)pv, (unsigned int)v17);
              v24 = pv[0];
            }
            *v37 = (struct IMVKey **)v24;
            *v38 = (unsigned int)pv[1];
            pv[0] = 0;
            LODWORD(pv[1]) = 0;
            ExtensionKeys = 0;
            if ( v11 )
            {
              if ( *v11 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
              operator delete(v11);
            }
            VariantClear(&pvarg);
            VariantClear(&v35);
            return (unsigned int)ExtensionKeys;
          }
          v27 = *v23;
          v28 = 0;
          v29 = *((_DWORD *)*v23 + 150);
          if ( v29 )
          {
            while ( *((_DWORD *)v27 + v28 + 132) != *((_DWORD *)this + 6) )
            {
              v28 = (unsigned int)(v28 + 1);
              if ( (unsigned int)v28 >= v29 )
                goto LABEL_70;
            }
            if ( *((_DWORD *)v27 + 154) )
            {
              LODWORD(v39) = v36 - v17;
              ExtensionKeys = CMvExtensionKey::GetExtensionKeys(
                                v27,
                                (LPVOID *)v11,
                                (struct IMVKey **)&v24[v17],
                                (unsigned int *)&v39);
              if ( ExtensionKeys < 0 )
              {
                if ( v11 )
                {
                  if ( *v11 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
                  operator delete(v11);
                }
                if ( v24 )
                {
                  for ( k = 0; (unsigned int)k < LODWORD(pv[1]); k = (unsigned int)(k + 1) )
                  {
                    v31 = v24[k];
                    if ( v31 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                      v24[k] = 0;
                    }
                  }
                  CoTaskMemFree(v24);
                }
                VariantClear(&pvarg);
                VariantClear(&v35);
                goto LABEL_73;
              }
              v17 = (unsigned int)((_DWORD)v39 + v17);
            }
          }
LABEL_70:
          v23 += 2;
        }
      }
      if ( !v11 )
        goto LABEL_15;
      if ( *v11 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
    }
    else
    {
      if ( !v11 )
      {
LABEL_15:
        VariantClear(&pvarg);
        VariantClear(&v35);
        goto LABEL_73;
      }
      if ( *v11 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
    }
    operator delete(v11);
    goto LABEL_15;
  }
  ExtensionKeys = -2147467261;
  VariantClear(&pvarg);
  VariantClear(&v35);
LABEL_73:
  if ( (unsigned int)dword_180052170 > 2 )
  {
    v36 = ExtensionKeys;
    v39 = L"Extension handler";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v14,
      (__int64)byte_18004947B,
      v15,
      v16,
      &v39,
      (__int64)&v36);
  }
  return (unsigned int)ExtensionKeys;
}

```

## disassembly

```asm
0x180013e50  mov     rax, rsp
0x180013e53  mov     [rax+18h], r8
0x180013e57  mov     [rax+10h], rdx
0x180013e5b  push    rbx
0x180013e5c  push    rsi
0x180013e5d  push    r12
0x180013e5f  push    r13
0x180013e61  push    r14
0x180013e63  push    r15
0x180013e65  sub     rsp, 98h
0x180013e6c  movaps  xmmword ptr [rax-48h], xmm6
0x180013e70  mov     r14, r8
0x180013e73  mov     r15, rdx
0x180013e76  mov     r13, rcx
0x180013e79  xor     ebx, ebx
0x180013e7b  mov     [rsp+0C8h+arg_0], ebx
0x180013e82  lea     rcx, [rax-68h]; pvarg
0x180013e86  call    cs:__imp_VariantInit
0x180013e8c  nop
0x180013e8d  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x180013e92  call    cs:__imp_VariantInit
0x180013e98  nop
0x180013e99  xorps   xmm6, xmm6
0x180013e9c  movups  xmmword ptr [rsp+0C8h+pv], xmm6
0x180013ea1  xor     esi, esi
0x180013ea3  mov     [rsp+0C8h+var_98], rsi
0x180013ea8  mov     eax, cs:dword_180052170
0x180013eae  cmp     eax, 4
0x180013eb1  jbe     short loc_180013EE8
0x180013eb3  lea     r12, aExtensionHandl; "Extension handler"
0x180013eba  mov     [rsp+0C8h+arg_18], r12
0x180013ec2  lea     rax, [rsp+0C8h+arg_18]
0x180013eca  mov     [rsp+0C8h+var_A8], rax
0x180013ecf  xor     r9d, r9d
0x180013ed2  xor     r8d, r8d
0x180013ed5  lea     rdx, word_1800494B6
0x180013edc  lea     rcx, dword_180052170
0x180013ee3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180013ee8  mov     rax, [r13+28h]
0x180013eec  sub     rax, [r13+20h]
0x180013ef0  cmp     rax, 10h
0x180013ef4  jnb     short loc_180013EFB
0x180013ef6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013efb  test    r15, r15
0x180013efe  jz      loc_180014349
0x180013f04  test    r14, r14
0x180013f07  jz      loc_180014349
0x180013f0d  mov     qword ptr [r15], 0
0x180013f14  mov     dword ptr [r14], 0
0x180013f1b  mov     ecx, 8; Size
0x180013f20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013f25  test    rax, rax
0x180013f28  jz      short loc_180013F39
0x180013f2a  mov     qword ptr [rax], 0
0x180013f31  mov     rsi, rax
0x180013f34  mov     [rsp+0C8h+var_98], rax
0x180013f39  mov     rcx, [r13+10h]
0x180013f3d  mov     rax, [rcx]
0x180013f40  lea     r8, [rsp+0C8h+var_68]
0x180013f45  lea     rdx, c_wszIMSIAttribute; "IMSI"
0x180013f4c  mov     rax, [rax+38h]
0x180013f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f55  test    eax, eax
0x180013f57  js      loc_180014006
0x180013f5d  lea     r8, [rsp+0C8h+var_68]; struct tagVARIANT *
0x180013f62  lea     rdx, c_wszIMSIAttribute; "IMSI"
0x180013f69  mov     rcx, rsi; ppv
0x180013f6c  call    ?SetSessionVariable@CfgMgrHelper@@QEAAJPEBGAEBUtagVARIANT@@@Z; CfgMgrHelper::SetSessionVariable(ushort const *,tagVARIANT const &)
0x180013f71  mov     r15d, eax
0x180013f74  test    eax, eax
0x180013f76  jns     loc_180014006
0x180013f7c  test    rsi, rsi
0x180013f7f  jz      short loc_180013FA0
0x180013f81  mov     rcx, [rsi]
0x180013f84  test    rcx, rcx
0x180013f87  jz      short loc_180013F96
0x180013f89  mov     rax, [rcx]
0x180013f8c  mov     rax, [rax+10h]
0x180013f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f95  nop
0x180013f96  mov     rcx, rsi
0x180013f99  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013f9f  nop
0x180013fa0  movq    rbx, xmm6
0x180013fa5  test    rbx, rbx
0x180013fa8  jz      short loc_180013FE9
0x180013faa  psrldq  xmm6, 8
0x180013faf  movd    r14d, xmm6
0x180013fb4  xor     esi, esi
0x180013fb6  test    r14d, r14d
0x180013fb9  jz      short loc_180013FDF
0x180013fbb  mov     rcx, [rbx+rsi*8]
0x180013fbf  test    rcx, rcx
0x180013fc2  jz      short loc_180013FD8
0x180013fc4  mov     rax, [rcx]
0x180013fc7  mov     rax, [rax+10h]
0x180013fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd0  mov     qword ptr [rbx+rsi*8], 0
0x180013fd8  inc     esi
0x180013fda  cmp     esi, r14d
0x180013fdd  jb      short loc_180013FBB
0x180013fdf  mov     rcx, rbx; pv
0x180013fe2  call    cs:__imp_CoTaskMemFree
0x180013fe8  nop
0x180013fe9  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x180013fee  call    cs:__imp_VariantClear
0x180013ff4  nop
0x180013ff5  lea     rcx, [rsp+0C8h+var_68]; pvarg
0x180013ffa  call    cs:__imp_VariantClear
0x180014000  nop
0x180014001  jmp     loc_180014376
0x180014006  mov     rcx, [r13+10h]
0x18001400a  mov     rax, [rcx]
0x18001400d  lea     r8, [rsp+0C8h+pvarg]
0x180014012  lea     rdx, c_wszICCIDAttribute; "ICCID"
0x180014019  mov     rax, [rax+38h]
0x18001401d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014022  mov     r15d, eax
0x180014025  test    eax, eax
0x180014027  js      loc_1800140D6
0x18001402d  lea     r8, [rsp+0C8h+pvarg]; struct tagVARIANT *
0x180014032  lea     rdx, c_wszICCIDAttribute; "ICCID"
0x180014039  mov     rcx, rsi; ppv
0x18001403c  call    ?SetSessionVariable@CfgMgrHelper@@QEAAJPEBGAEBUtagVARIANT@@@Z; CfgMgrHelper::SetSessionVariable(ushort const *,tagVARIANT const &)
0x180014041  mov     r15d, eax
0x180014044  test    eax, eax
0x180014046  jns     loc_1800140D6
0x18001404c  test    rsi, rsi
0x18001404f  jz      short loc_180014070
0x180014051  mov     rcx, [rsi]
0x180014054  test    rcx, rcx
0x180014057  jz      short loc_180014066
0x180014059  mov     rax, [rcx]
0x18001405c  mov     rax, [rax+10h]
0x180014060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014065  nop
0x180014066  mov     rcx, rsi
0x180014069  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001406f  nop
0x180014070  movq    rbx, xmm6
0x180014075  test    rbx, rbx
0x180014078  jz      short loc_1800140B9
0x18001407a  psrldq  xmm6, 8
0x18001407f  movd    r14d, xmm6
0x180014084  xor     esi, esi
0x180014086  test    r14d, r14d
0x180014089  jz      short loc_1800140AF
0x18001408b  mov     rcx, [rbx+rsi*8]
0x18001408f  test    rcx, rcx
0x180014092  jz      short loc_1800140A8
0x180014094  mov     rax, [rcx]
0x180014097  mov     rax, [rax+10h]
0x18001409b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a0  mov     qword ptr [rbx+rsi*8], 0
0x1800140a8  inc     esi
0x1800140aa  cmp     esi, r14d
0x1800140ad  jb      short loc_18001408B
0x1800140af  mov     rcx, rbx; pv
0x1800140b2  call    cs:__imp_CoTaskMemFree
0x1800140b8  nop
0x1800140b9  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800140be  call    cs:__imp_VariantClear
0x1800140c4  nop
0x1800140c5  lea     rcx, [rsp+0C8h+var_68]; pvarg
0x1800140ca  call    cs:__imp_VariantClear
0x1800140d0  nop
0x1800140d1  jmp     loc_180014376
0x1800140d6  xor     r12d, r12d
0x1800140d9  mov     rax, [r13+20h]
0x1800140dd  cmp     rax, [r13+28h]
0x1800140e1  jz      short loc_180014125
0x1800140e3  mov     r10d, [r13+18h]
0x1800140e7  mov     r8, [rax]
0x1800140ea  xor     edx, edx
0x1800140ec  mov     r9d, [r8+258h]
0x1800140f3  test    r9d, r9d
0x1800140f6  jz      short loc_18001411F
0x1800140f8  cmp     [r8+rdx*4+210h], r10d
0x180014100  jz      short loc_18001410B
0x180014102  inc     edx
0x180014104  cmp     edx, r9d
0x180014107  jb      short loc_1800140F8
0x180014109  jmp     short loc_18001411F
0x18001410b  mov     ecx, [r8+268h]
0x180014112  test    ecx, ecx
0x180014114  jz      short loc_18001411F
0x180014116  add     ebx, ecx
0x180014118  mov     [rsp+0C8h+arg_0], ebx
0x18001411f  add     rax, 10h
0x180014123  jmp     short loc_1800140DD
0x180014125  mov     edx, ebx
0x180014127  lea     rcx, [rsp+0C8h+pv]
0x18001412c  call    ?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z; co_array_t<IMVKey *>::allocate(unsigned __int64)
0x180014131  mov     rbx, [r13+20h]
0x180014135  mov     r14, [rsp+0C8h+pv]
0x18001413a  cmp     rbx, [r13+28h]
0x18001413e  jnz     loc_180014254
0x180014144  cmp     r12d, [rsp+0C8h+arg_0]
0x18001414c  jz      loc_1800141E6
0x180014152  test    r12d, r12d
0x180014155  jnz     short loc_1800141D4
0x180014157  test    rsi, rsi
0x18001415a  jz      short loc_18001417B
0x18001415c  mov     rcx, [rsi]
0x18001415f  test    rcx, rcx
0x180014162  jz      short loc_180014171
0x180014164  mov     rax, [rcx]
0x180014167  mov     rax, [rax+10h]
0x18001416b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014170  nop
0x180014171  mov     rcx, rsi
0x180014174  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001417a  nop
0x18001417b  test    r14, r14
0x18001417e  jz      short loc_1800141B7
0x180014180  xor     ebx, ebx
0x180014182  cmp     dword ptr [rsp+0C8h+pv+8], ebx
0x180014186  jbe     short loc_1800141AD
0x180014188  mov     rcx, [r14+rbx*8]
0x18001418c  test    rcx, rcx
0x18001418f  jz      short loc_1800141A5
0x180014191  mov     rax, [rcx]
0x180014194  mov     rax, [rax+10h]
0x180014198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001419d  mov     qword ptr [r14+rbx*8], 0
0x1800141a5  inc     ebx
0x1800141a7  cmp     ebx, dword ptr [rsp+0C8h+pv+8]
0x1800141ab  jb      short loc_180014188
0x1800141ad  mov     rcx, r14; pv
0x1800141b0  call    cs:__imp_CoTaskMemFree
0x1800141b6  nop
0x1800141b7  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800141bc  call    cs:__imp_VariantClear
0x1800141c2  nop
0x1800141c3  lea     rcx, [rsp+0C8h+var_68]; pvarg
0x1800141c8  call    cs:__imp_VariantClear
0x1800141ce  nop
0x1800141cf  jmp     loc_180014371
0x1800141d4  mov     edx, r12d
0x1800141d7  lea     rcx, [rsp+0C8h+pv]
0x1800141dc  call    ?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z; co_array_t<IMVKey *>::allocate(unsigned __int64)
0x1800141e1  mov     r14, [rsp+0C8h+pv]
0x1800141e6  mov     rax, [rsp+0C8h+arg_8]
0x1800141ee  mov     [rax], r14
0x1800141f1  mov     eax, dword ptr [rsp+0C8h+pv+8]
0x1800141f5  mov     rcx, [rsp+0C8h+arg_10]
0x1800141fd  mov     [rcx], eax
0x1800141ff  mov     [rsp+0C8h+pv], 0
0x180014208  mov     dword ptr [rsp+0C8h+pv+8], 0
0x180014210  xor     r15d, r15d
0x180014213  test    rsi, rsi
0x180014216  jz      short loc_180014237
0x180014218  mov     rcx, [rsi]
0x18001421b  test    rcx, rcx
0x18001421e  jz      short loc_18001422D
0x180014220  mov     rax, [rcx]
0x180014223  mov     rax, [rax+10h]
0x180014227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422c  nop
0x18001422d  mov     rcx, rsi
0x180014230  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014236  nop
0x180014237  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x18001423c  call    cs:__imp_VariantClear
0x180014242  nop
0x180014243  lea     rcx, [rsp+0C8h+var_68]; pvarg
0x180014248  call    cs:__imp_VariantClear
0x18001424e  nop
0x18001424f  jmp     loc_1800143BE
0x180014254  mov     r10, [rbx]
0x180014257  mov     r8d, [r13+18h]
0x18001425b  xor     ecx, ecx
0x18001425d  mov     edx, [r10+258h]
0x180014264  test    edx, edx
0x180014266  jz      loc_180014340
0x18001426c  cmp     [r10+rcx*4+210h], r8d
0x180014274  jz      short loc_180014281
0x180014276  inc     ecx
0x180014278  cmp     ecx, edx
0x18001427a  jb      short loc_18001426C
0x18001427c  jmp     loc_180014340
0x180014281  cmp     dword ptr [r10+268h], 0
0x180014289  jz      loc_180014340
0x18001428f  mov     eax, [rsp+0C8h+arg_0]
0x180014296  sub     eax, r12d
0x180014299  mov     dword ptr [rsp+0C8h+arg_18], eax
0x1800142a0  lea     r8, [r14+r12*8]; struct IMVKey **
0x1800142a4  lea     r9, [rsp+0C8h+arg_18]; unsigned int *
0x1800142ac  mov     rdx, rsi; struct CfgMgrHelper *
0x1800142af  mov     rcx, r10; this
0x1800142b2  call    ?GetExtensionKeys@CMvExtensionKey@@QEBAJPEAVCfgMgrHelper@@PEAPEAUIMVKey@@PEAK@Z; CMvExtensionKey::GetExtensionKeys(CfgMgrHelper *,IMVKey * *,ulong *)
0x1800142b7  mov     r15d, eax
0x1800142ba  test    eax, eax
0x1800142bc  jns     short loc_180014338
0x1800142be  test    rsi, rsi
0x1800142c1  jz      short loc_1800142E2
0x1800142c3  mov     rcx, [rsi]
0x1800142c6  test    rcx, rcx
0x1800142c9  jz      short loc_1800142D8
0x1800142cb  mov     rax, [rcx]
  ... truncated ...
```
