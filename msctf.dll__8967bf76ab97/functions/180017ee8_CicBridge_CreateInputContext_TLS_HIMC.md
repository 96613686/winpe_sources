# CicBridge::CreateInputContext(TLS *,HIMC__ *)

- ea: `0x180017ee8`
- end: `0x18001834b`
- name: `?CreateInputContext@CicBridge@@QEAAJPEAVTLS@@PEAUHIMC__@@@Z`
- size: `1123`
- prototype: `int(CicBridge *__hidden this, struct TLS *, HIMC)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073a70`
- `0x18007fd70`

## callees

- `0x180016dc0`
- `0x180016df0`
- `0x180016e7c`
- `0x1800173b8`
- `0x180017ee8`
- `0x1800185f0`
- `0x180018640`
- `0x18001a460`
- `0x18001a4a8`
- `0x18001cc80`
- `0x18004f940`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018056`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800180f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800180f8`
- `USER32!GetFocus` at `0x1800182d1`
- `USER32!GetFocus` at `0x1800182d1`
- `IMM32!ImmLockIMC` at `0x180017f54`
- `IMM32!ImmLockIMC` at `0x180017f54`
- `IMM32!ImmUnlockIMC` at `0x180018064`
- `IMM32!ImmUnlockIMC` at `0x18001815a`
- `IMM32!ImmUnlockIMC` at `0x180018064`
- `IMM32!ImmUnlockIMC` at `0x18001815a`
- `IMM32!ImmLockIMCC` at `0x1800180b7`
- `IMM32!ImmLockIMCC` at `0x1800180b7`
- `IMM32!ImmUnlockIMCC` at `0x18001804c`
- `IMM32!ImmUnlockIMCC` at `0x18001804c`
- `IMM32!ImmCreateIMCC` at `0x180018097`
- `IMM32!ImmCreateIMCC` at `0x180018097`

## string_xrefs

- `0x180017f10`: `CicBridge::CreateInputContext`
- `0x180017f6d`: `CicBridge::CreateInputContext. imc==NULL`
- `0x180018103`: `CicBridge::CreateInputContext. _pCicContext==NULL`
- `0x180018138`: `CicBridge::CreateInputContext. imc_ctfime==NULL`
- `0x18001827a`: `CicBridge::CreateInputContext. _pCicContext->CreateInputContext==NULL`
- `0x1800182b6`: `CicBridge::CreateInputContext. hCtfImeContext==NULL`
- `0x180018310`: `CicBridge::CreateInputContext. ptim_P==NULL`

## pseudocode

```c
__int64 __fastcall CicBridge::CreateInputContext(CicBridge *this, struct TLS *a2, HIMC a3)
{
  int InputContext; // ebx
  LPINPUTCONTEXT v6; // rax
  LPINPUTCONTEXT v7; // r15
  __int64 v8; // rdx
  struct IUnknown *v9; // rcx
  HIMCC v11; // r13
  HIMCC IMCC; // rax
  struct ITfDocumentMgr **v13; // r12
  unsigned int v14; // edi
  CicInputContext *v15; // rax
  struct TLS *v16; // rdx
  CicBridge *v17; // rcx
  CicInputContext *v18; // rdi
  struct IUnknown *v19; // rsi
  struct ITfDocumentMgr *lpVtbl; // rdi
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  struct IUnknown *EmptyBackingStore; // [rsp+58h] [rbp-39h]
  __int64 v25; // [rsp+60h] [rbp-31h] BYREF
  struct CicBridge *Current; // [rsp+68h] [rbp-29h]
  __int128 v27; // [rsp+70h] [rbp-21h] BYREF
  HIMCC v28; // [rsp+80h] [rbp-11h]
  unsigned int v29; // [rsp+88h] [rbp-9h]
  void **v30; // [rsp+90h] [rbp-1h] BYREF
  LPINPUTCONTEXT v31; // [rsp+98h] [rbp+7h]
  HIMC v32; // [rsp+A0h] [rbp+Fh]
  __int64 v33; // [rsp+A8h] [rbp+17h]
  struct IUnknown *v36; // [rsp+110h] [rbp+7Fh] BYREF

  CicTrace(8u, "CicBridge::CreateInputContext");
  if ( (*((_BYTE *)this + 40) & 1) != 0 )
    return 2147500037LL;
  v32 = a3;
  v31 = 0;
  v33 = 0;
  InputContext = -2147467259;
  v30 = &IMCLock::`vftable';
  if ( !a3 )
  {
LABEL_5:
    CicTrace(2u, "CicBridge::CreateInputContext. imc==NULL");
LABEL_6:
    IMCLock::~IMCLock((IMCLock *)&v30);
    return (unsigned int)InputContext;
  }
  v6 = ImmLockIMC(a3);
  v31 = v6;
  v7 = v6;
  if ( !v6 )
  {
    LODWORD(v33) = -2147467259;
    goto LABEL_5;
  }
  v11 = *(HIMCC *)&v6[1].lfFont.W.lfWidth;
  if ( !v11 )
  {
    IMCC = ImmCreateIMCC(0x10u);
    v11 = IMCC;
    if ( !IMCC )
    {
      CicTrace(2u, "CicBridge::CreateInputContext. hCtfImeContext==NULL");
      InputContext = -2147024882;
      goto LABEL_6;
    }
    *(_QWORD *)&v7[1].lfFont.W.lfWidth = IMCC;
  }
  v28 = v11;
  *((_QWORD *)&v27 + 1) = ImmLockIMCC(v11);
  v13 = (struct ITfDocumentMgr **)*((_QWORD *)&v27 + 1);
  *(_QWORD *)&v27 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
  v14 = *((_QWORD *)&v27 + 1) != 0 ? 0 : 0x80004005;
  v29 = v14;
  if ( *((_QWORD *)&v27 + 1) )
  {
    if ( (*((_QWORD *)&v27 + 1) != 0) - 1 >= 0 )
    {
      if ( **((_QWORD **)&v27 + 1) )
      {
        InputContext = 0;
LABEL_17:
        if ( !ImmUnlockIMCC(v11) )
          GetLastError();
        goto LABEL_19;
      }
      v15 = (CicInputContext *)LocalAlloc(0x40u, 0x570u);
      if ( v15
        && (v18 = CicInputContext::CicInputContext(v15, *((_DWORD *)this + 26), (CicBridge *)((char *)this + 112), a3)) != 0 )
      {
        v19 = (struct IUnknown *)*((_QWORD *)a2 + 2);
        v36 = v19;
        if ( v19 )
        {
          ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->AddRef)(v19);
          **((_QWORD **)&v27 + 1) = v18;
          InputContext = CicInputContext::CreateInputContext(v18, v19, (struct IMCLock *)&v30);
          if ( InputContext >= 0 )
          {
            lpVtbl = *v13;
            if ( *v13 )
            {
              lpVtbl = (struct ITfDocumentMgr *)lpVtbl[5].lpVtbl;
              if ( lpVtbl )
                ((void (__fastcall *)(struct ITfDocumentMgr *))lpVtbl->lpVtbl->AddRef)(lpVtbl);
            }
            EmptyBackingStore = CicBridge::GetEmptyBackingStore(this);
            Current = CicBridge::GetCurrent();
            if ( !Current )
              goto LABEL_13;
            v21 = 0;
            v25 = 0;
            if ( lpVtbl )
            {
              ((void (__fastcall *)(struct ITfDocumentMgr *, GUID *, __int64 *))lpVtbl->lpVtbl->QueryInterface)(
                lpVtbl,
                &GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c,
                &v25);
              v21 = v25;
            }
            v36 = 0;
            if ( !v21 )
              goto LABEL_13;
            v22 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v21 + 24LL))(
                    v21,
                    &GUID_COMPARTMENT_TRANSITORYEXTENSION_PARENT,
                    &v36);
            v9 = v36;
            if ( v22 >= 0 )
            {
              if ( !v36 )
              {
LABEL_11:
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_13:
                if ( v7->hWnd && v7->hWnd == GetFocus() )
                  CicBridge::SetAssociate(this, a2, v7->hWnd, a3, (struct ITfThreadMgr_P *)v19, lpVtbl, 0, 0, 0);
                if ( lpVtbl )
                  ((void (__fastcall *)(struct ITfDocumentMgr *))lpVtbl->lpVtbl->Release)(lpVtbl);
                ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
                goto LABEL_17;
              }
              if ( EmptyBackingStore )
              {
                ((void (__fastcall *)(struct IUnknown *))EmptyBackingStore->lpVtbl->AddRef)(EmptyBackingStore);
                v28 = 0;
                v27 = 0;
                v8 = *((unsigned int *)Current + 26);
                LOWORD(v27) = 13;
                *((_QWORD *)&v27 + 1) = EmptyBackingStore;
                ((void (__fastcall *)(struct IUnknown *, __int64, __int128 *))v36->lpVtbl[1].QueryInterface)(
                  v36,
                  v8,
                  &v27);
                ((void (__fastcall *)(struct IUnknown *))EmptyBackingStore->lpVtbl->Release)(EmptyBackingStore);
                v9 = v36;
              }
            }
            if ( v9 )
              ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
            goto LABEL_11;
          }
          CicTrace(2u, "CicBridge::CreateInputContext. _pCicContext->CreateInputContext==NULL");
          (*(void (__fastcall **)(CicInputContext *))(*(_QWORD *)v18 + 16LL))(v18);
          *v13 = 0;
          ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
        }
        else
        {
          CicTrace(2u, "CicBridge::CreateInputContext. ptim_P==NULL");
          (*(void (__fastcall **)(CicInputContext *))(*(_QWORD *)v18 + 16LL))(v18);
          **((_QWORD **)&v27 + 1) = 0;
          InputContext = -2147467262;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36, v23);
        }
      }
      else
      {
        CicTrace(2u, "CicBridge::CreateInputContext. _pCicContext==NULL");
        InputContext = -2147024882;
      }
      InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v27);
      CicBridge::DestroyInputContext(v17, v16, a3);
LABEL_19:
      if ( v7 )
        ImmUnlockIMC(a3);
      return (unsigned int)InputContext;
    }
  }
  else
  {
    v14 = -2147467259;
  }
  CicTrace(2u, "CicBridge::CreateInputContext. imc_ctfime==NULL");
  InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v27);
  if ( v7 )
    ImmUnlockIMC(a3);
  return v14;
}

```

## disassembly

```asm
0x180017ee8  mov     rax, rsp
0x180017eeb  mov     [rax+18h], rbx
0x180017eef  mov     [rax+10h], rdx
0x180017ef3  mov     [rax+8], rcx
0x180017ef7  push    rbp
0x180017ef8  push    rsi
0x180017ef9  push    rdi
0x180017efa  push    r12
0x180017efc  push    r13
0x180017efe  push    r14
0x180017f00  push    r15
0x180017f02  lea     rbp, [rax-5Fh]
0x180017f06  sub     rsp, 0B0h
0x180017f0d  mov     rsi, rcx
0x180017f10  lea     rdx, aCicbridgeCreat_6; "CicBridge::CreateInputContext"
0x180017f17  mov     ecx, 8; unsigned int
0x180017f1c  mov     r14, r8
0x180017f1f  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180017f24  test    byte ptr [rsi+28h], 1
0x180017f28  jnz     loc_180018167
0x180017f2e  xor     edi, edi
0x180017f30  mov     [rbp+57h+var_48], r14
0x180017f34  mov     [rbp+57h+var_50], rdi
0x180017f38  lea     rax, ??_7IMCLock@@6B@; const IMCLock::`vftable'
0x180017f3f  mov     [rbp+57h+var_40], rdi
0x180017f43  mov     ebx, 80004005h
0x180017f48  mov     [rbp+57h+var_58], rax
0x180017f4c  test    r14, r14
0x180017f4f  jz      short loc_180017F6D
0x180017f51  mov     rcx, r14; HIMC
0x180017f54  call    cs:__imp_ImmLockIMC
0x180017f5a  mov     [rbp+57h+var_50], rax
0x180017f5e  mov     r15, rax
0x180017f61  test    rax, rax
0x180017f64  jnz     loc_180018087
0x180017f6a  mov     dword ptr [rbp+57h+var_40], ebx
0x180017f6d  lea     rdx, aCicbridgeCreat_5; "CicBridge::CreateInputContext. imc==NUL"...
0x180017f74  mov     ecx, 2; unsigned int
0x180017f79  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180017f7e  lea     rcx, [rbp+57h+var_58]; this
0x180017f82  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180017f87  jmp     loc_18001806A
0x180017f8c  mov     rdx, [rbp+57h+var_90]
0x180017f90  test    rdx, rdx
0x180017f93  jz      short loc_180017FF1
0x180017f95  mov     rax, [rdx]
0x180017f98  mov     rcx, rdx
0x180017f9b  mov     rax, [rax+8]
0x180017f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fa4  mov     rcx, [rbp+57h+arg_18]
0x180017fa8  lea     r8, [rbp+57h+var_78]
0x180017fac  mov     rdx, [rbp+57h+var_80]
0x180017fb0  xor     eax, eax
0x180017fb2  mov     [rbp+57h+var_68], rax
0x180017fb6  xorps   xmm0, xmm0
0x180017fb9  movups  [rbp+57h+var_78], xmm0
0x180017fbd  mov     eax, 0Dh
0x180017fc2  mov     edx, [rdx+68h]
0x180017fc5  mov     word ptr [rbp+57h+var_78], ax
0x180017fc9  mov     rax, [rbp+57h+var_90]
0x180017fcd  mov     qword ptr [rbp+57h+var_78+8], rax
0x180017fd1  mov     rax, [rcx]
0x180017fd4  mov     rax, [rax+18h]
0x180017fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fdd  mov     rcx, [rbp+57h+var_90]
0x180017fe1  mov     rax, [rcx]
0x180017fe4  mov     rax, [rax+10h]
0x180017fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fed  mov     rcx, [rbp+57h+arg_18]
0x180017ff1  test    rcx, rcx
0x180017ff4  jz      short loc_180018002
0x180017ff6  mov     rax, [rcx]
0x180017ff9  mov     rax, [rax+10h]
0x180017ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018002  mov     rcx, [rbp+57h+var_88]
0x180018006  test    rcx, rcx
0x180018009  jz      short loc_180018017
0x18001800b  mov     rax, [rcx]
0x18001800e  mov     rax, [rax+10h]
0x180018012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018017  cmp     qword ptr [r15], 0
0x18001801b  jnz     loc_1800182D1
0x180018021  test    rdi, rdi
0x180018024  jz      short loc_180018035
0x180018026  mov     rax, [rdi]
0x180018029  mov     rcx, rdi
0x18001802c  mov     rax, [rax+10h]
0x180018030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018035  mov     rax, [rsi]
0x180018038  mov     rcx, rsi
0x18001803b  mov     rax, [rax+10h]
0x18001803f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018044  test    r12, r12
0x180018047  jz      short loc_18001805C
0x180018049  mov     rcx, r13; HIMCC
0x18001804c  call    cs:__imp_ImmUnlockIMCC
0x180018052  test    eax, eax
0x180018054  jnz     short loc_18001805C
0x180018056  call    cs:__imp_GetLastError
0x18001805c  test    r15, r15
0x18001805f  jz      short loc_18001806A
0x180018061  mov     rcx, r14; HIMC
0x180018064  call    cs:__imp_ImmUnlockIMC
0x18001806a  mov     eax, ebx
0x18001806c  mov     rbx, [rsp+0E0h+arg_10]
0x180018074  add     rsp, 0B0h
0x18001807b  pop     r15
0x18001807d  pop     r14
0x18001807f  pop     r13
0x180018081  pop     r12
0x180018083  pop     rdi
0x180018084  pop     rsi
0x180018085  pop     rbp
0x180018086  retn
0x180018087  mov     r13, [rax+188h]
0x18001808e  test    r13, r13
0x180018091  jnz     short loc_1800180B0
0x180018093  lea     ecx, [r13+10h]; DWORD
0x180018097  call    cs:__imp_ImmCreateIMCC
0x18001809d  mov     r13, rax
0x1800180a0  test    rax, rax
0x1800180a3  jz      loc_1800182B6
0x1800180a9  mov     [r15+188h], rax
0x1800180b0  mov     rcx, r13; HIMCC
0x1800180b3  mov     [rbp+57h+var_68], r13
0x1800180b7  call    cs:__imp_ImmLockIMCC
0x1800180bd  mov     rcx, rax
0x1800180c0  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800180c4  neg     rcx
0x1800180c7  mov     r12, rax
0x1800180ca  lea     rax, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x1800180d1  sbb     edi, edi
0x1800180d3  mov     qword ptr [rbp+57h+var_78], rax
0x1800180d7  not     edi
0x1800180d9  and     edi, ebx
0x1800180db  mov     [rbp+57h+var_60], edi
0x1800180de  test    r12, r12
0x1800180e1  jz      short loc_180018136
0x1800180e3  test    edi, edi
0x1800180e5  js      short loc_180018138
0x1800180e7  cmp     qword ptr [r12], 0
0x1800180ec  jnz     short loc_18001812F
0x1800180ee  mov     edx, 570h; uBytes
0x1800180f3  mov     ecx, 40h ; '@'; uFlags
0x1800180f8  call    cs:__imp_LocalAlloc
0x1800180fe  test    rax, rax
0x180018101  jnz     short loc_180018171
0x180018103  lea     rdx, aCicbridgeCreat_1; "CicBridge::CreateInputContext. _pCicCon"...
0x18001810a  mov     ecx, 2; unsigned int
0x18001810f  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180018114  mov     ebx, 8007000Eh
0x180018119  lea     rcx, [rbp+57h+var_78]; this
0x18001811d  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x180018122  mov     r8, r14; HIMC
0x180018125  call    ?DestroyInputContext@CicBridge@@QEAAJPEAVTLS@@PEAUHIMC__@@@Z; CicBridge::DestroyInputContext(TLS *,HIMC__ *)
0x18001812a  jmp     loc_18001805C
0x18001812f  xor     ebx, ebx
0x180018131  jmp     loc_180018044
0x180018136  mov     edi, ebx
0x180018138  lea     rdx, aCicbridgeCreat_4; "CicBridge::CreateInputContext. imc_ctfi"...
0x18001813f  mov     ecx, 2; unsigned int
0x180018144  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180018149  lea     rcx, [rbp+57h+var_78]; this
0x18001814d  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x180018152  test    r15, r15
0x180018155  jz      short loc_180018160
0x180018157  mov     rcx, r14; HIMC
0x18001815a  call    cs:__imp_ImmUnlockIMC
0x180018160  mov     eax, edi
0x180018162  jmp     loc_18001806C
0x180018167  mov     eax, 80004005h
0x18001816c  jmp     loc_18001806C
0x180018171  mov     edx, [rsi+68h]; unsigned int
0x180018174  lea     r8, [rsi+70h]; struct tag_LIBTHREAD *
0x180018178  mov     r9, r14; HIMC
0x18001817b  mov     rcx, rax; this
0x18001817e  call    ??0CicInputContext@@QEAA@KPEAUtag_LIBTHREAD@@PEAUHIMC__@@@Z; CicInputContext::CicInputContext(ulong,tag_LIBTHREAD *,HIMC__ *)
0x180018183  mov     rdi, rax
0x180018186  test    rax, rax
0x180018189  jz      loc_180018103
0x18001818f  mov     rsi, [rbp+57h+arg_8]
0x180018193  mov     rsi, [rsi+10h]
0x180018197  mov     [rbp+57h+arg_18], rsi
0x18001819b  test    rsi, rsi
0x18001819e  jz      loc_180018310
0x1800181a4  mov     rcx, [rsi]
0x1800181a7  mov     rax, [rcx+8]
0x1800181ab  mov     rcx, rsi
0x1800181ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181b3  lea     r8, [rbp+57h+var_58]; struct IMCLock *
0x1800181b7  mov     [r12], rdi
0x1800181bb  mov     rdx, rsi; struct IUnknown *
0x1800181be  mov     rcx, rdi; this
0x1800181c1  call    ?CreateInputContext@CicInputContext@@QEAAJPEAUITfThreadMgr_P@@AEAVIMCLock@@@Z; CicInputContext::CreateInputContext(ITfThreadMgr_P *,IMCLock &)
0x1800181c6  mov     ebx, eax
0x1800181c8  test    eax, eax
0x1800181ca  js      loc_18001827A
0x1800181d0  mov     rdi, [r12]
0x1800181d4  test    rdi, rdi
0x1800181d7  jz      short loc_1800181F1
0x1800181d9  mov     rdi, [rdi+28h]
0x1800181dd  test    rdi, rdi
0x1800181e0  jz      short loc_1800181F1
0x1800181e2  mov     rax, [rdi]
0x1800181e5  mov     rcx, rdi
0x1800181e8  mov     rax, [rax+8]
0x1800181ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181f1  mov     rcx, [rbp+57h+arg_0]; this
0x1800181f5  call    ?GetEmptyBackingStore@CicBridge@@AEAAPEAUIUnknown@@XZ; CicBridge::GetEmptyBackingStore(void)
0x1800181fa  mov     [rbp+57h+var_90], rax
0x1800181fe  call    ?GetCurrent@CicBridge@@SAPEAV1@XZ; CicBridge::GetCurrent(void)
0x180018203  mov     [rbp+57h+var_80], rax
0x180018207  test    rax, rax
0x18001820a  jz      loc_180018017
0x180018210  xor     ecx, ecx
0x180018212  mov     [rbp+57h+var_88], rcx
0x180018216  test    rdi, rdi
0x180018219  jz      short loc_180018238
0x18001821b  mov     rcx, [rdi]
0x18001821e  lea     r8, [rbp+57h+var_88]
0x180018222  lea     rdx, _GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c
0x180018229  mov     rax, [rcx]
0x18001822c  mov     rcx, rdi
0x18001822f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018234  mov     rcx, [rbp+57h+var_88]
0x180018238  mov     [rbp+57h+arg_18], 0
0x180018240  test    rcx, rcx
0x180018243  jz      loc_180018017
0x180018249  mov     rax, [rcx]
0x18001824c  lea     r8, [rbp+57h+arg_18]
0x180018250  lea     rdx, GUID_COMPARTMENT_TRANSITORYEXTENSION_PARENT
0x180018257  mov     rax, [rax+18h]
0x18001825b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018260  mov     rcx, [rbp+57h+arg_18]
0x180018264  test    eax, eax
0x180018266  js      loc_180017FF1
0x18001826c  test    rcx, rcx
0x18001826f  jnz     loc_180017F8C
0x180018275  jmp     loc_180018002
0x18001827a  lea     rdx, aCicbridgeCreat; "CicBridge::CreateInputContext. _pCicCon"...
0x180018281  mov     ecx, 2; unsigned int
0x180018286  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001828b  mov     rdx, [rdi]
0x18001828e  mov     rcx, rdi
0x180018291  mov     rax, [rdx+10h]
0x180018295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001829a  mov     qword ptr [r12], 0
0x1800182a2  mov     rcx, rsi
0x1800182a5  mov     rax, [rsi]
0x1800182a8  mov     rax, [rax+10h]
0x1800182ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182b1  jmp     loc_180018119
0x1800182b6  lea     rdx, aCicbridgeCreat_3; "CicBridge::CreateInputContext. hCtfImeC"...
0x1800182bd  mov     ecx, 2; unsigned int
0x1800182c2  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x1800182c7  mov     ebx, 8007000Eh
0x1800182cc  jmp     loc_180017F7E
0x1800182d1  call    cs:__imp_GetFocus
0x1800182d7  cmp     [r15], rax
0x1800182da  jnz     loc_180018021
0x1800182e0  mov     r8, [r15]; HWND
0x1800182e3  xor     eax, eax
0x1800182e5  mov     rdx, [rbp+57h+arg_8]; struct TLS *
0x1800182e9  mov     r9, r14; HIMC
0x1800182ec  mov     rcx, [rbp+57h+arg_0]; this
0x1800182f0  mov     [rsp+40h], al; bool
0x1800182f4  mov     [rsp+0E0h+var_A8], eax; int
0x1800182f8  mov     [rsp+0E0h+var_B0], eax; int
0x1800182fc  mov     [rsp+0E0h+var_B8], rdi; struct ITfDocumentMgr *
0x180018301  mov     [rsp+0E0h+var_C0], rsi; struct ITfThreadMgr_P *
0x180018306  call    ?SetAssociate@CicBridge@@AEAAXPEAVTLS@@PEAUHWND__@@PEAUHIMC__@@PEAUITfThreadMgr_P@@PEAUITfDocumentMgr@@HH_N@Z; CicBridge::SetAssociate(TLS *,HWND__ *,HIMC__ *,ITfThreadMgr_P *,ITfDocumentMgr *,int,int,bool)
0x18001830b  jmp     loc_180018021
0x180018310  lea     rdx, aCicbridgeCreat_2; "CicBridge::CreateInputContext. ptim_P=="...
0x180018317  mov     ecx, 2; unsigned int
0x18001831c  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180018321  mov     rax, [rdi]
0x180018324  mov     rcx, rdi
0x180018327  mov     rax, [rax+10h]
0x18001832b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018330  lea     rcx, [rbp+57h+arg_18]
0x180018334  mov     qword ptr [r12], 0
0x18001833c  mov     ebx, 80004002h
0x180018341  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018346  jmp     loc_180018119
```
