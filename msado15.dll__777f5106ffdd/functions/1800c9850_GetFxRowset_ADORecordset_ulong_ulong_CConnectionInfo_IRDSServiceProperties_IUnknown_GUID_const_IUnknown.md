# GetFxRowset(_ADORecordset *,ulong,ulong,CConnectionInfo &,IRDSServiceProperties *,IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x1800c9850`
- end: `0x1800c9b61`
- name: `?GetFxRowset@@YAJPEAU_ADORecordset@@KKAEAVCConnectionInfo@@PEAUIRDSServiceProperties@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@@Z`
- size: `785`
- prototype: `int(struct _ADORecordset *, unsigned int, unsigned int, struct CConnectionInfo *, struct IRDSServiceProperties *, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180068dd0`
- `0x1800ad30c`

## callees

- `0x180011530`
- `0x180019770`
- `0x1800c8f34`
- `0x1800c9850`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800c9982`
- `ole32!CoCreateInstance` at `0x1800c9982`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9b13`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9b13`

## pseudocode

```c
__int64 __fastcall GetFxRowset(
        struct _ADORecordset *a1,
        unsigned int a2,
        unsigned int a3,
        struct CConnectionInfo *a4,
        struct IRDSServiceProperties *a5,
        struct IUnknown *a6,
        const struct _GUID *a7,
        struct IUnknown **a8)
{
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned int v13; // ebx
  HRESULT v14; // eax
  __int64 v15; // rdx
  struct IRDSServiceProperties *v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // edi
  struct tagDBPROPSET *i; // rdx
  __int64 v20; // r14
  __int64 v21; // rsi
  LPVOID *ppv; // [rsp+20h] [rbp-69h]
  unsigned int v24; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v25; // [rsp+64h] [rbp-25h] BYREF
  LPVOID v26; // [rsp+68h] [rbp-21h] BYREF
  struct tagDBPROPSET *v27; // [rsp+70h] [rbp-19h] BYREF
  __int64 v28; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v29[8]; // [rsp+80h] [rbp-9h] BYREF

  v28 = 0;
  v26 = 0;
  v27 = 0;
  lpVtbl = a6->lpVtbl;
  v24 = 0;
  v25 = 0;
  v29[0] = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))lpVtbl->QueryInterface)(
         a6,
         &IID_ICreateRowset,
         v29) < 0 )
  {
    v16 = a5;
    if ( a5 )
    {
      (*(void (__fastcall **)(struct IRDSServiceProperties *))(*(_QWORD *)a5 + 8LL))(a5);
      v26 = a5;
    }
    else
    {
      v14 = CoCreateInstance(&CLSID_FoxRowset, 0, 3u, &IID_IRDSServiceProperties, &v26);
      v13 = v14;
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_25;
        LODWORD(ppv) = 2680;
        v15 = 2744329;
        goto LABEL_6;
      }
      v16 = (struct IRDSServiceProperties *)v26;
    }
    v14 = (**(__int64 (__fastcall ***)(struct IRDSServiceProperties *, GUID *, __int64 *))v16)(
            v16,
            &IID_IRDSService,
            &v28);
    v13 = v14;
    if ( v14 >= 0 )
    {
      v14 = FillCommandProps(a2, a3, 0, 0, 0, 0, 0, a4, adUseNone, &v27, &v24, &v25);
      v13 = v14;
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct tagDBPROPSET *))(*(_QWORD *)v26 + 40LL))(v26, v24, v27);
        v13 = v14;
        if ( v14 == -2147217887 || v14 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct IUnknown *, struct IUnknown **))(*(_QWORD *)v28 + 32LL))(
                  v28,
                  a7,
                  a6,
                  a8);
          goto LABEL_25;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_25;
        LODWORD(ppv) = 2693;
        v15 = 2757641;
      }
      else
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_25;
        LODWORD(ppv) = 2686;
        v15 = 2750473;
      }
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_25;
      LODWORD(ppv) = 2683;
      v15 = 2747401;
    }
LABEL_6:
    bidTraceW(off_18012A218[0], v15, L"<GetFxRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n", (unsigned int)v14, ppv);
    goto LABEL_25;
  }
  v13 = 0;
  *a8 = a6;
  if ( !a1 )
    goto LABEL_25;
  v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LPVOID *))a6->lpVtbl->QueryInterface)(
          a6,
          &IID_IRDSServiceProperties,
          &v26);
  v13 = v14;
  if ( v14 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_25;
    LODWORD(ppv) = 2658;
    v15 = 2721801;
    goto LABEL_6;
  }
  (*(void (__fastcall **)(struct _ADORecordset *, LPVOID))(*(_QWORD *)a1 + 736LL))(a1, v26);
LABEL_25:
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v26 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
  v17 = v24;
  v18 = 0;
  for ( i = v27; v18 < v17; ++v18 )
  {
    v20 = 0;
    v21 = v18;
    if ( i[v21].cProperties )
    {
      do
      {
        VariantClear((VARIANTARG *)((char *)&i->rgProperties->vValue + 64 * v20 + 8 * v20));
        i = v27;
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (unsigned int)v20 < v27[v21].cProperties );
      v17 = v24;
    }
  }
  if ( i )
  {
    operator delete(i->rgProperties);
    operator delete(v27);
  }
  return v13;
}

```

## disassembly

```asm
0x1800c9850  push    rbp
0x1800c9852  push    rbx
0x1800c9853  push    rsi
0x1800c9854  push    rdi
0x1800c9855  push    r12
0x1800c9857  push    r14
0x1800c9859  push    r15
0x1800c985b  lea     rbp, [rsp-7]
0x1800c9860  sub     rsp, 90h
0x1800c9867  mov     rdi, [rbp+37h+arg_28]
0x1800c986b  mov     r15d, r8d
0x1800c986e  mov     r12d, edx
0x1800c9871  mov     [rbp+37h+var_48], 0
0x1800c9879  mov     rsi, rcx
0x1800c987c  mov     [rbp+37h+var_58], 0
0x1800c9884  lea     r8, [rbp+37h+var_40]
0x1800c9888  mov     [rbp+37h+var_50], 0
0x1800c9890  mov     rax, [rdi]
0x1800c9893  lea     rdx, IID_ICreateRowset
0x1800c989a  mov     rcx, rdi
0x1800c989d  mov     [rbp+37h+var_60], 0
0x1800c98a4  mov     r14, r9
0x1800c98a7  mov     [rbp+37h+var_5C], 0
0x1800c98ae  mov     [rbp+37h+var_40], 0
0x1800c98b6  mov     rax, [rax]
0x1800c98b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c98be  test    eax, eax
0x1800c98c0  js      loc_1800C9947
0x1800c98c6  mov     rax, [rbp+37h+arg_38]
0x1800c98ca  xor     ebx, ebx
0x1800c98cc  mov     [rax], rdi
0x1800c98cf  test    rsi, rsi
0x1800c98d2  jz      loc_1800C9ABA
0x1800c98d8  mov     rax, [rdi]
0x1800c98db  lea     r8, [rbp+37h+var_58]
0x1800c98df  lea     rdx, ?IID_IRDSServiceProperties@@3U_GUID@@B; _GUID const IID_IRDSServiceProperties
0x1800c98e6  mov     rcx, rdi
0x1800c98e9  mov     rax, [rax]
0x1800c98ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c98f1  mov     ebx, eax
0x1800c98f3  test    eax, eax
0x1800c98f5  jns     short loc_1800C992C
0x1800c98f7  test    byte ptr cs:_bidGblFlags, 2
0x1800c98fe  jz      loc_1800C9ABA
0x1800c9904  mov     dword ptr [rsp+0C0h+ppv], 0A62h
0x1800c990c  mov     edx, 298809h
0x1800c9911  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c9918  lea     r8, aGetfxrowsetAdo; "<GetFxRowset|ADO|ERR> 0x%08x{HRESULT} l"...
0x1800c991f  mov     r9d, eax
0x1800c9922  call    _bidTraceW
0x1800c9927  jmp     loc_1800C9ABA
0x1800c992c  mov     rax, [rsi]
0x1800c992f  mov     rcx, rsi
0x1800c9932  mov     rdx, [rbp+37h+var_58]
0x1800c9936  mov     rax, [rax+2E0h]
0x1800c993d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9942  jmp     loc_1800C9ABA
0x1800c9947  mov     rbx, [rbp+37h+arg_20]
0x1800c994b  test    rbx, rbx
0x1800c994e  jz      short loc_1800C9965
0x1800c9950  mov     rax, [rbx]
0x1800c9953  mov     rcx, rbx
0x1800c9956  mov     rax, [rax+8]
0x1800c995a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c995f  mov     [rbp+37h+var_58], rbx
0x1800c9963  jmp     short loc_1800C99B7
0x1800c9965  xor     edx, edx; pUnkOuter
0x1800c9967  lea     rax, [rbp+37h+var_58]
0x1800c996b  lea     r9, ?IID_IRDSServiceProperties@@3U_GUID@@B; riid
0x1800c9972  mov     [rsp+0C0h+ppv], rax; ppv
0x1800c9977  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x1800c997e  lea     r8d, [rdx+3]; dwClsContext
0x1800c9982  call    cs:__imp_CoCreateInstance
0x1800c9989  nop     dword ptr [rax+rax+00h]
0x1800c998e  mov     ebx, eax
0x1800c9990  test    eax, eax
0x1800c9992  jns     short loc_1800C99B3
0x1800c9994  test    byte ptr cs:_bidGblFlags, 2
0x1800c999b  jz      loc_1800C9ABA
0x1800c99a1  mov     dword ptr [rsp+0C0h+ppv], 0A78h
0x1800c99a9  mov     edx, 29E009h
0x1800c99ae  jmp     loc_1800C9911
0x1800c99b3  mov     rbx, [rbp+37h+var_58]
0x1800c99b7  mov     rax, [rbx]
0x1800c99ba  lea     r8, [rbp+37h+var_48]
0x1800c99be  lea     rdx, ?IID_IRDSService@@3U_GUID@@B; _GUID const IID_IRDSService
0x1800c99c5  mov     rcx, rbx
0x1800c99c8  mov     rax, [rax]
0x1800c99cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c99d0  mov     ebx, eax
0x1800c99d2  test    eax, eax
0x1800c99d4  jns     short loc_1800C99F5
0x1800c99d6  test    byte ptr cs:_bidGblFlags, 2
0x1800c99dd  jz      loc_1800C9ABA
0x1800c99e3  mov     dword ptr [rsp+0C0h+ppv], 0A7Bh
0x1800c99eb  mov     edx, 29EC09h
0x1800c99f0  jmp     loc_1800C9911
0x1800c99f5  lea     rax, [rbp+37h+var_5C]
0x1800c99f9  xor     r9d, r9d; bool
0x1800c99fc  mov     [rsp+0C0h+var_68], rax; unsigned int *
0x1800c9a01  xor     r8d, r8d; int
0x1800c9a04  lea     rax, [rbp+37h+var_60]
0x1800c9a08  mov     edx, r15d; unsigned int
0x1800c9a0b  mov     [rsp+0C0h+var_70], rax; unsigned int *
0x1800c9a10  mov     ecx, r12d; unsigned int
0x1800c9a13  lea     rax, [rbp+37h+var_50]
0x1800c9a17  mov     [rsp+0C0h+var_78], rax; struct tagDBPROPSET **
0x1800c9a1c  mov     [rsp+0C0h+var_80], 1; enum CursorLocationEnum
0x1800c9a24  mov     [rsp+0C0h+var_88], r14; struct CConnectionInfo *
0x1800c9a29  mov     [rsp+0C0h+var_90], 0; bool
0x1800c9a2e  mov     [rsp+0C0h+var_98], 0; bool
0x1800c9a33  mov     byte ptr [rsp+0C0h+ppv], 0; bool
0x1800c9a38  call    ?FillCommandProps@@YAJKKJ_N000AEAVCConnectionInfo@@W4CursorLocationEnum@@PEAPEAUtagDBPROPSET@@PEAK4@Z; FillCommandProps(ulong,ulong,long,bool,bool,bool,bool,CConnectionInfo &,CursorLocationEnum,tagDBPROPSET * *,ulong *,ulong *)
0x1800c9a3d  mov     ebx, eax
0x1800c9a3f  test    eax, eax
0x1800c9a41  jns     short loc_1800C9A5E
0x1800c9a43  test    byte ptr cs:_bidGblFlags, 2
0x1800c9a4a  jz      short loc_1800C9ABA
0x1800c9a4c  mov     dword ptr [rsp+0C0h+ppv], 0A7Eh
0x1800c9a54  mov     edx, 29F809h
0x1800c9a59  jmp     loc_1800C9911
0x1800c9a5e  mov     rcx, [rbp+37h+var_58]
0x1800c9a62  mov     r8, [rbp+37h+var_50]
0x1800c9a66  mov     edx, [rbp+37h+var_60]
0x1800c9a69  mov     rax, [rcx]
0x1800c9a6c  mov     rax, [rax+28h]
0x1800c9a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9a75  mov     ebx, eax
0x1800c9a77  cmp     eax, 80040E21h
0x1800c9a7c  jz      short loc_1800C9A9D
0x1800c9a7e  test    eax, eax
0x1800c9a80  jns     short loc_1800C9A9D
0x1800c9a82  test    byte ptr cs:_bidGblFlags, 2
0x1800c9a89  jz      short loc_1800C9ABA
0x1800c9a8b  mov     dword ptr [rsp+0C0h+ppv], 0A85h
0x1800c9a93  mov     edx, 2A1409h
0x1800c9a98  jmp     loc_1800C9911
0x1800c9a9d  mov     rcx, [rbp+37h+var_48]
0x1800c9aa1  mov     r8, rdi
0x1800c9aa4  mov     r9, [rbp+37h+arg_38]
0x1800c9aa8  mov     rdx, [rbp+37h+arg_30]
0x1800c9aac  mov     rax, [rcx]
0x1800c9aaf  mov     rax, [rax+20h]
0x1800c9ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9ab8  mov     ebx, eax
0x1800c9aba  mov     rcx, [rbp+37h+var_48]
0x1800c9abe  test    rcx, rcx
0x1800c9ac1  jz      short loc_1800C9ACF
0x1800c9ac3  mov     rax, [rcx]
0x1800c9ac6  mov     rax, [rax+10h]
0x1800c9aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9acf  mov     rcx, [rbp+37h+var_58]
0x1800c9ad3  test    rcx, rcx
0x1800c9ad6  jz      short loc_1800C9AE4
0x1800c9ad8  mov     rax, [rcx]
0x1800c9adb  mov     rax, [rax+10h]
0x1800c9adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9ae4  mov     eax, [rbp+37h+var_60]
0x1800c9ae7  xor     edi, edi
0x1800c9ae9  mov     rdx, [rbp+37h+var_50]
0x1800c9aed  test    eax, eax
0x1800c9aef  jz      short loc_1800C9B36
0x1800c9af1  mov     esi, edi
0x1800c9af3  xor     r14d, r14d
0x1800c9af6  shl     rsi, 5
0x1800c9afa  cmp     [rsi+rdx+8], r14d
0x1800c9aff  jbe     short loc_1800C9B30
0x1800c9b01  mov     rax, [rdx]
0x1800c9b04  lea     rcx, ds:6[r14*8]
0x1800c9b0c  add     rcx, r14
0x1800c9b0f  lea     rcx, [rax+rcx*8]; pvarg
0x1800c9b13  call    cs:__imp_VariantClear
0x1800c9b1a  nop     dword ptr [rax+rax+00h]
0x1800c9b1f  mov     rdx, [rbp+37h+var_50]
0x1800c9b23  inc     r14d
0x1800c9b26  cmp     r14d, [rsi+rdx+8]
0x1800c9b2b  jb      short loc_1800C9B01
0x1800c9b2d  mov     eax, [rbp+37h+var_60]
0x1800c9b30  inc     edi
0x1800c9b32  cmp     edi, eax
0x1800c9b34  jb      short loc_1800C9AF1
0x1800c9b36  test    rdx, rdx
0x1800c9b39  jz      short loc_1800C9B4C
0x1800c9b3b  mov     rcx, [rdx]; void *
0x1800c9b3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c9b43  mov     rcx, [rbp+37h+var_50]; void *
0x1800c9b47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c9b4c  mov     eax, ebx
0x1800c9b4e  add     rsp, 90h
0x1800c9b55  pop     r15
0x1800c9b57  pop     r14
0x1800c9b59  pop     r12
0x1800c9b5b  pop     rdi
0x1800c9b5c  pop     rsi
0x1800c9b5d  pop     rbx
0x1800c9b5e  pop     rbp
0x1800c9b5f  retn
```
