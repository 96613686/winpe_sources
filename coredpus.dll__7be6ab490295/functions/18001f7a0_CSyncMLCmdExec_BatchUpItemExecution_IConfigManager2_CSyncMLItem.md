# CSyncMLCmdExec::BatchUpItemExecution(IConfigManager2 *,CSyncMLItem *)

- ea: `0x18001f7a0`
- end: `0x18001fa36`
- name: `?BatchUpItemExecution@CSyncMLCmdExec@@EEAAJPEAUIConfigManager2@@PEAVCSyncMLItem@@@Z`
- size: `662`
- prototype: `int(CSyncMLCmdExec *__hidden this, struct IConfigManager2 *, struct CSyncMLItem *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800034d0`
- `0x1800038a0`
- `0x180009380`
- `0x18001e454`
- `0x18001f7a0`
- `0x18002164c`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001f8bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f8bd`
- `OLEAUT32!__imp_VariantInit` at `0x18001f7fe`
- `OLEAUT32!__imp_VariantInit` at `0x18001f80e`
- `OLEAUT32!__imp_VariantInit` at `0x18001f7fe`
- `OLEAUT32!__imp_VariantInit` at `0x18001f80e`
- `OLEAUT32!__imp_VariantClear` at `0x18001f9d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001f9e6`
- `OLEAUT32!__imp_VariantClear` at `0x18001f9d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001f9e6`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdExec::BatchUpItemExecution(
        CSyncMLCmdExec *this,
        struct IConfigManager2 *a2,
        struct CSyncMLItem *a3)
{
  struct IConfigManager2URI *TargetLocURI; // r14
  int DataAsVariant; // ebx
  const OLECHAR *v8; // rcx
  __int64 (__fastcall *v9)(struct IConfigNode *, __int64 *, VARIANTARG *); // rax
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v14; // [rsp+30h] [rbp-29h] BYREF
  struct IConfigNode *v15; // [rsp+38h] [rbp-21h] BYREF
  VARIANTARG v16; // [rsp+40h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-1h] BYREF
  VARIANTARG v18[2]; // [rsp+70h] [rbp+17h] BYREF
  int v19; // [rsp+D0h] [rbp+77h] BYREF
  int v20; // [rsp+D8h] [rbp+7Fh] BYREF

  v19 = 0;
  v20 = 0;
  v15 = 0;
  TargetLocURI = CSyncMLItem::GetTargetLocURI(a3);
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v16, 0, sizeof(v16));
  VariantInit(&pvarg);
  VariantInit(&v16);
  if ( !TargetLocURI )
  {
    DataAsVariant = -2102788095;
    goto LABEL_18;
  }
  DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigManager2 *, struct IConfigManager2URI *, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
                    a2,
                    TargetLocURI,
                    &v15);
  if ( DataAsVariant >= 0 )
  {
    DataAsVariant = CSyncMLItem::ValidateData(a3);
    if ( DataAsVariant >= 0 )
    {
      DataAsVariant = CSyncMLItem::GetDataAsVariant(a3, &pvarg);
      if ( DataAsVariant >= 0 )
      {
        DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v15 + 144LL))(v15, &v19);
        if ( DataAsVariant >= 0 )
        {
          *((_DWORD *)a3 + 8) = v19;
          DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 56LL))(a2);
          if ( DataAsVariant >= 0 )
          {
            v8 = (const OLECHAR *)*((_QWORD *)this + 21);
            if ( v8 )
            {
              v16.llVal = (LONGLONG)SysAllocString(v8);
              if ( !v16.llVal )
              {
                DataAsVariant = -2147024882;
LABEL_16:
                (*(void (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 72LL))(a2);
                goto LABEL_17;
              }
              v18[0].pRecInfo = v16.pRecInfo;
              v16.vt = 8;
              v9 = *(__int64 (__fastcall **)(struct IConfigNode *, __int64 *, VARIANTARG *))(*(_QWORD *)v15 + 168LL);
              *(_OWORD *)&v18[0].vt = *(_OWORD *)&v16.vt;
              DataAsVariant = v9(v15, OMADM_PROPERTY_CORRELATOR, v18);
              if ( DataAsVariant < 0 )
                goto LABEL_16;
            }
            v10 = *(_QWORD *)v15;
            v18[0] = pvarg;
            DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, VARIANTARG *))(v10 + 88))(v15, v18);
            if ( DataAsVariant >= 0 )
            {
              DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v15 + 144LL))(
                                v15,
                                &v20);
              if ( DataAsVariant >= 0 )
              {
                *((_DWORD *)a3 + 10) = v20 - v19;
                DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 64LL))(a2);
                if ( DataAsVariant >= 0 )
                {
                  DataAsVariant = CSyncMLItem::SetCfgNode(a3, v15, 0);
                  if ( DataAsVariant >= 0 )
                    goto LABEL_17;
                }
              }
            }
            goto LABEL_16;
          }
        }
      }
    }
  }
LABEL_17:
  (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)TargetLocURI + 16LL))(TargetLocURI);
LABEL_18:
  if ( v15 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  VariantClear(&pvarg);
  VariantClear(&v16);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v14 = DataAsVariant;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&dword_18003659C,
      v11,
      v12,
      (__int64)&v14);
  }
  return (unsigned int)DataAsVariant;
}

```

## disassembly

```asm
0x18001f7a0  mov     [rsp-8+arg_0], rbx
0x18001f7a5  push    rbp
0x18001f7a6  push    rsi
0x18001f7a7  push    rdi
0x18001f7a8  push    r14
0x18001f7aa  push    r15
0x18001f7ac  lea     rbp, [rsp-37h]
0x18001f7b1  sub     rsp, 90h
0x18001f7b8  mov     r15, rcx
0x18001f7bb  mov     [rbp+57h+arg_10], 0
0x18001f7c2  mov     rcx, r8; this
0x18001f7c5  mov     [rbp+57h+arg_18], 0
0x18001f7cc  mov     rsi, r8
0x18001f7cf  mov     [rbp+57h+var_78], 0
0x18001f7d7  mov     rdi, rdx
0x18001f7da  call    ?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetTargetLocURI(void)
0x18001f7df  mov     r14, rax
0x18001f7e2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f7e6  xor     eax, eax
0x18001f7e8  xorps   xmm0, xmm0
0x18001f7eb  xorps   xmm1, xmm1
0x18001f7ee  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001f7f2  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18001f7f6  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001f7fa  movups  xmmword ptr [rbp+57h+var_70], xmm1
0x18001f7fe  call    cs:__imp_VariantInit
0x18001f805  nop     dword ptr [rax+rax+00h]
0x18001f80a  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001f80e  call    cs:__imp_VariantInit
0x18001f815  nop     dword ptr [rax+rax+00h]
0x18001f81a  test    r14, r14
0x18001f81d  jnz     short loc_18001F829
0x18001f81f  mov     ebx, 82AA0001h
0x18001f824  jmp     loc_18001F9B5
0x18001f829  mov     rax, [rdi]
0x18001f82c  lea     r8, [rbp+57h+var_78]
0x18001f830  mov     rdx, r14
0x18001f833  mov     rcx, rdi
0x18001f836  mov     rax, [rax+58h]
0x18001f83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f83f  mov     ebx, eax
0x18001f841  test    eax, eax
0x18001f843  js      loc_18001F9A6
0x18001f849  mov     rcx, rsi; struct CSyncMLItem *
0x18001f84c  call    ?ValidateData@CSyncMLItem@@SAJPEAV1@@Z; CSyncMLItem::ValidateData(CSyncMLItem *)
0x18001f851  mov     ebx, eax
0x18001f853  test    eax, eax
0x18001f855  js      loc_18001F9A6
0x18001f85b  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18001f85f  mov     rcx, rsi; this
0x18001f862  call    ?GetDataAsVariant@CSyncMLItem@@QEBAJPEAUtagVARIANT@@@Z; CSyncMLItem::GetDataAsVariant(tagVARIANT *)
0x18001f867  mov     ebx, eax
0x18001f869  test    eax, eax
0x18001f86b  js      loc_18001F9A6
0x18001f871  mov     rcx, [rbp+57h+var_78]
0x18001f875  lea     rdx, [rbp+57h+arg_10]
0x18001f879  mov     rax, [rcx]
0x18001f87c  mov     rax, [rax+90h]
0x18001f883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f888  mov     ebx, eax
0x18001f88a  test    eax, eax
0x18001f88c  js      loc_18001F9A6
0x18001f892  mov     eax, [rbp+57h+arg_10]
0x18001f895  mov     rcx, rdi
0x18001f898  mov     [rsi+20h], eax
0x18001f89b  mov     rax, [rdi]
0x18001f89e  mov     rax, [rax+38h]
0x18001f8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8a7  mov     ebx, eax
0x18001f8a9  test    eax, eax
0x18001f8ab  js      loc_18001F9A6
0x18001f8b1  mov     rcx, [r15+0A8h]; psz
0x18001f8b8  test    rcx, rcx
0x18001f8bb  jz      short loc_18001F91B
0x18001f8bd  call    cs:__imp_SysAllocString
0x18001f8c4  nop     dword ptr [rax+rax+00h]
0x18001f8c9  mov     qword ptr [rbp+57h+var_70+8], rax
0x18001f8cd  test    rax, rax
0x18001f8d0  jnz     short loc_18001F8DC
0x18001f8d2  mov     ebx, 8007000Eh
0x18001f8d7  jmp     loc_18001F997
0x18001f8dc  mov     rcx, [rbp+57h+var_78]
0x18001f8e0  lea     r8, [rbp+57h+var_40]
0x18001f8e4  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x18001f8e9  lea     rdx, OMADM_PROPERTY_CORRELATOR
0x18001f8f0  mov     eax, 8
0x18001f8f5  movsd   [rbp+57h+var_30], xmm1
0x18001f8fa  mov     word ptr [rbp+57h+var_70], ax
0x18001f8fe  mov     rax, [rcx]
0x18001f901  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18001f905  mov     rax, [rax+0A8h]
0x18001f90c  movaps  [rbp+57h+var_40], xmm0
0x18001f910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f915  mov     ebx, eax
0x18001f917  test    eax, eax
0x18001f919  js      short loc_18001F997
0x18001f91b  mov     rcx, [rbp+57h+var_78]
0x18001f91f  lea     rdx, [rbp+57h+var_40]
0x18001f923  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18001f927  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18001f92c  mov     rax, [rcx]
0x18001f92f  movaps  [rbp+57h+var_40], xmm0
0x18001f933  movsd   [rbp+57h+var_30], xmm1
0x18001f938  mov     rax, [rax+58h]
0x18001f93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f941  mov     ebx, eax
0x18001f943  test    eax, eax
0x18001f945  js      short loc_18001F997
0x18001f947  mov     rcx, [rbp+57h+var_78]
0x18001f94b  lea     rdx, [rbp+57h+arg_18]
0x18001f94f  mov     rax, [rcx]
0x18001f952  mov     rax, [rax+90h]
0x18001f959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f95e  mov     ebx, eax
0x18001f960  test    eax, eax
0x18001f962  js      short loc_18001F997
0x18001f964  mov     eax, [rbp+57h+arg_18]
0x18001f967  mov     rcx, rdi
0x18001f96a  sub     eax, [rbp+57h+arg_10]
0x18001f96d  mov     [rsi+28h], eax
0x18001f970  mov     rax, [rdi]
0x18001f973  mov     rax, [rax+40h]
0x18001f977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f97c  mov     ebx, eax
0x18001f97e  test    eax, eax
0x18001f980  js      short loc_18001F997
0x18001f982  mov     rdx, [rbp+57h+var_78]; struct IConfigNode *
0x18001f986  xor     r8d, r8d; unsigned int
0x18001f989  mov     rcx, rsi; this
0x18001f98c  call    ?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z; CSyncMLItem::SetCfgNode(IConfigNode *,ulong)
0x18001f991  mov     ebx, eax
0x18001f993  test    eax, eax
0x18001f995  jns     short loc_18001F9A6
0x18001f997  mov     rax, [rdi]
0x18001f99a  mov     rcx, rdi
0x18001f99d  mov     rax, [rax+48h]
0x18001f9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9a6  mov     rax, [r14]
0x18001f9a9  mov     rcx, r14
0x18001f9ac  mov     rax, [rax+10h]
0x18001f9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9b5  mov     rcx, [rbp+57h+var_78]
0x18001f9b9  test    rcx, rcx
0x18001f9bc  jz      short loc_18001F9D2
0x18001f9be  mov     rax, [rcx]
0x18001f9c1  mov     rax, [rax+10h]
0x18001f9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9ca  mov     [rbp+57h+var_78], 0
0x18001f9d2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f9d6  call    cs:__imp_VariantClear
0x18001f9dd  nop     dword ptr [rax+rax+00h]
0x18001f9e2  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001f9e6  call    cs:__imp_VariantClear
0x18001f9ed  nop     dword ptr [rax+rax+00h]
0x18001f9f2  mov     eax, cs:dword_18003E048
0x18001f9f8  cmp     eax, 5
0x18001f9fb  jbe     short loc_18001FA1C
0x18001f9fd  lea     rax, [rbp+57h+var_80]
0x18001fa01  mov     [rbp+57h+var_80], ebx
0x18001fa04  lea     rdx, dword_18003659C
0x18001fa0b  mov     [rsp+0B0h+var_90], rax
0x18001fa10  lea     rcx, dword_18003E048
0x18001fa17  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001fa1c  mov     eax, ebx
0x18001fa1e  mov     rbx, [rsp+0B0h+arg_0]
0x18001fa26  add     rsp, 90h
0x18001fa2d  pop     r15
0x18001fa2f  pop     r14
0x18001fa31  pop     rdi
0x18001fa32  pop     rsi
0x18001fa33  pop     rbp
0x18001fa34  retn
```
