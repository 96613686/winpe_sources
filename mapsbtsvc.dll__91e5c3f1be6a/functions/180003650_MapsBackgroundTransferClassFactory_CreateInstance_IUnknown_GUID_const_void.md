# MapsBackgroundTransferClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003650`
- end: `0x18000371f`
- name: `?CreateInstance@MapsBackgroundTransferClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `207`
- prototype: `__int64 __fastcall(MapsBackgroundTransferClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800033f8`
- `0x180003458`
- `0x18000359c`
- `0x180003650`
- `0x180015010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800036c7`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800036c7`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000368a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000368a`

## string_xrefs

- `0x180003680`: `MapsBackgroundTransferClassFactory::CreateInstance`
- `0x1800036be`: `MapsBackgroundTransferClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferClassFactory::CreateInstance(
        MapsBackgroundTransferClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct IUnknown *v4; // rbx
  int v8; // r8d
  int v9; // ecx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // r8d
  struct IUnknown *v15; // [rsp+20h] [rbp-38h] BYREF
  struct IUnknown *v16; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  v15 = 0;
  v16 = 0;
  if ( a2 )
  {
    v8 = 83;
    v9 = -2147221232;
LABEL_3:
    v10 = ZTraceReportOrigination(v9, "MapsBackgroundTransferClassFactory::CreateInstance", v8, this);
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v8 = 84;
    v9 = -2147467261;
    goto LABEL_3;
  }
  *a4 = 0;
  v12 = ATL::CComObject<MapsIdleBackgroundCopyCallback>::CreateInstance(&v15);
  if ( v12 >= 0 )
  {
    if ( v15 )
    {
      ATL::AtlComPtrAssign(&v16, v15);
      v4 = v16;
    }
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v4->lpVtbl->QueryInterface)(
            v4,
            a3,
            a4);
    if ( v12 >= 0 )
    {
      v11 = 0;
      goto LABEL_15;
    }
    v13 = 91;
  }
  else
  {
    v13 = 88;
  }
  v10 = ZTraceReportPropagation(v12, "MapsBackgroundTransferClassFactory::CreateInstance", v13, this);
LABEL_4:
  v11 = v10;
LABEL_15:
  ATL::CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>((__int64 *)&v16);
  return v11;
}

```

## disassembly

```asm
0x180003650  push    rbx
0x180003652  push    rbp
0x180003653  push    rsi
0x180003654  push    rdi
0x180003655  sub     rsp, 38h
0x180003659  xor     ebx, ebx
0x18000365b  mov     [rsp+58h+var_38], 0
0x180003664  mov     [rsp+58h+arg_8], rbx
0x180003669  mov     rsi, r9
0x18000366c  mov     rbp, r8
0x18000366f  mov     rdi, rcx
0x180003672  test    rdx, rdx
0x180003675  jz      short loc_180003694
0x180003677  lea     r8d, [rbx+53h]
0x18000367b  mov     ecx, 80040110h
0x180003680  lea     rdx, aMapsbackground_42; "MapsBackgroundTransferClassFactory::Cre"...
0x180003687  mov     r9, rdi
0x18000368a  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180003690  mov     ebx, eax
0x180003692  jmp     short loc_18000370A
0x180003694  test    rsi, rsi
0x180003697  jnz     short loc_1800036A4
0x180003699  lea     r8d, [rsi+54h]
0x18000369d  mov     ecx, 80004003h
0x1800036a2  jmp     short loc_180003680
0x1800036a4  lea     rcx, [rsp+58h+var_38]
0x1800036a9  mov     [r9], rbx
0x1800036ac  call    ?CreateInstance@?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<MapsIdleBackgroundCopyCallback>::CreateInstance(ATL::CComObject<MapsIdleBackgroundCopyCallback> * *)
0x1800036b1  test    eax, eax
0x1800036b3  jns     short loc_1800036CF
0x1800036b5  mov     r8d, 58h ; 'X'
0x1800036bb  mov     r9, rdi
0x1800036be  lea     rdx, aMapsbackground_42; "MapsBackgroundTransferClassFactory::Cre"...
0x1800036c5  mov     ecx, eax
0x1800036c7  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800036cd  jmp     short loc_180003690
0x1800036cf  mov     rdx, [rsp+58h+var_38]; struct IUnknown *
0x1800036d4  test    rdx, rdx
0x1800036d7  jz      short loc_1800036E8
0x1800036d9  lea     rcx, [rsp+58h+arg_8]; struct IUnknown **
0x1800036de  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800036e3  mov     rbx, [rsp+58h+arg_8]
0x1800036e8  mov     rax, [rbx]
0x1800036eb  mov     r8, rsi
0x1800036ee  mov     rdx, rbp
0x1800036f1  mov     rcx, rbx
0x1800036f4  mov     rax, [rax]
0x1800036f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036fc  test    eax, eax
0x1800036fe  jns     short loc_180003708
0x180003700  mov     r8d, 5Bh ; '['
0x180003706  jmp     short loc_1800036BB
0x180003708  xor     ebx, ebx
0x18000370a  lea     rcx, [rsp+58h+arg_8]
0x18000370f  call    ??1?$CComPtrBase@V?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>(void)
0x180003714  mov     eax, ebx
0x180003716  add     rsp, 38h
0x18000371a  pop     rdi
0x18000371b  pop     rsi
0x18000371c  pop     rbp
0x18000371d  pop     rbx
0x18000371e  retn
```
