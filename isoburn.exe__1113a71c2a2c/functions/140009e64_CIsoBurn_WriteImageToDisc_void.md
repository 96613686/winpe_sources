# CIsoBurn::_WriteImageToDisc(void)

- ea: `0x140009e64`
- end: `0x14000a495`
- name: `?_WriteImageToDisc@CIsoBurn@@AEAAXXZ`
- size: `1585`
- prototype: `void __fastcall(CIsoBurn *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000a4a0`

## callees

- `0x140001fa0`
- `0x140002bc6`
- `0x140003954`
- `0x140004bb0`
- `0x1400086e4`
- `0x1400089a0`
- `0x140009870`
- `0x140009a48`
- `0x140009e64`
- `0x14000a514`
- `0x140010010`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14000a3c2`
- `ADVAPI32!EventWrite` at `0x14000a3c2`
- `ADVAPI32!EventEnabled` at `0x14000a31b`
- `ADVAPI32!EventEnabled` at `0x14000a31b`
- `KERNEL32!CloseHandle` at `0x14000a433`
- `KERNEL32!CloseHandle` at `0x14000a433`
- `KERNEL32!PowerCreateRequest` at `0x140009ec6`
- `KERNEL32!PowerCreateRequest` at `0x140009ec6`
- `KERNEL32!PowerSetRequest` at `0x140009edd`
- `KERNEL32!PowerSetRequest` at `0x140009edd`
- `KERNEL32!PowerClearRequest` at `0x14000a42a`
- `KERNEL32!PowerClearRequest` at `0x14000a42a`
- `OLEAUT32!__imp_SysAllocString` at `0x140009fbb`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a127`
- `OLEAUT32!__imp_SysAllocString` at `0x140009fbb`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a127`
- `OLEAUT32!__imp_SysFreeString` at `0x140009fe2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a14a`
- `OLEAUT32!__imp_SysFreeString` at `0x140009fe2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a14a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009fac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a08b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009fac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a08b`

## pseudocode

```c
void __fastcall CIsoBurn::_WriteImageToDisc(CIsoBurn *this)
{
  bool v1; // si
  HANDLE v3; // rax
  void *v4; // r13
  unsigned int v5; // r12d
  const OLECHAR *v6; // rdi
  HRESULT Instance; // ebx
  OLECHAR *v8; // rdi
  const WCHAR *v9; // rcx
  char v10; // r14
  int DiscRecorderForVolume; // eax
  struct IDiscRecorder2 *v12; // rbx
  HRESULT v13; // edi
  OLECHAR *v14; // rdi
  struct IUnknown *v15; // rsi
  int v16; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v18; // ecx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  struct IUnknown *ppv; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  _REASON_CONTEXT Context; // [rsp+48h] [rbp-B8h] BYREF
  void **v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+78h] [rbp-88h] BYREF
  char v31; // [rsp+7Ch] [rbp-84h]
  int v32; // [rsp+A0h] [rbp-60h] BYREF
  const char *v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  char v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+C0h] [rbp-40h]
  _BYTE v37[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v38; // [rsp+160h] [rbp+60h]
  int v39; // [rsp+170h] [rbp+70h]
  __int64 v40; // [rsp+178h] [rbp+78h]
  int *v41; // [rsp+180h] [rbp+80h]
  __int64 v42; // [rsp+188h] [rbp+88h]
  __int64 v43; // [rsp+190h] [rbp+90h]
  void ***v44; // [rsp+198h] [rbp+98h]
  __int64 v45; // [rsp+1A0h] [rbp+A0h]
  int v46; // [rsp+1A8h] [rbp+A8h]
  int *v47; // [rsp+1B0h] [rbp+B0h]
  char v48; // [rsp+1B8h] [rbp+B8h]
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR *v51; // [rsp+1E0h] [rbp+E0h]
  __int64 v52; // [rsp+1E8h] [rbp+E8h]
  int *v53; // [rsp+1F0h] [rbp+F0h]
  __int64 v54; // [rsp+1F8h] [rbp+F8h]
  struct IUnknown **p_ppv; // [rsp+200h] [rbp+100h]
  __int64 v56; // [rsp+208h] [rbp+108h]

  v1 = 0;
  v27 = 0;
  Context.Version = 0;
  Context.Reason.Detailed.LocalizedReasonModule = hInstance;
  Context.Flags = 2;
  *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0x106u;
  v3 = PowerCreateRequest(&Context);
  v4 = v3;
  if ( v3 != (HANDLE)-1LL )
    PowerSetRequest(v3, PowerRequestSystemRequired);
  v30 = 0;
  v33 = "BurnImage";
  v38 = 0;
  v31 = 0;
  v35 = 0;
  v32 = 0;
  v34 = 0;
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v39 = 1;
  v40 = 0;
  v42 = 0;
  v41 = &v30;
  v5 = 0;
  v43 = 0;
  v44 = &v29;
  v47 = &v32;
  v29 = &IsoBurnLoggingTelemetry::BurnImage::`vftable';
  v45 = 0;
  v46 = 0;
  v48 = 0;
  IsoBurnLoggingTelemetry::BurnImage::StartActivity((IsoBurnLoggingTelemetry::BurnImage *)&v29);
  v6 = (const OLECHAR *)*((_QWORD *)this + 15);
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_MsftIsoImageManager,
               0,
               0x17u,
               &GUID_6ca38be5_fbbb_4800_95a1_a438865eb0d4,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v8 = SysAllocString(v6);
    if ( v8 )
    {
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *))ppv->lpVtbl[3].QueryInterface)(ppv, v8);
      SysFreeString(v8);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct IUnknown *))ppv->lpVtbl[3].Release)(ppv);
        if ( Instance >= 0 )
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))ppv->lpVtbl[2].Release)(ppv, &v27);
      }
    }
    else
    {
      Instance = -2147024882;
    }
  }
  if ( ppv )
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
  if ( Instance < 0 )
  {
    v13 = -1062539261;
    goto LABEL_56;
  }
  v9 = (const WCHAR *)*((_QWORD *)this + 16);
  v10 = 0;
  ppv = 0;
  DiscRecorderForVolume = CIsoBurn::_GetDiscRecorderForVolume(v9, (struct IDiscRecorder2 **)&ppv);
  v12 = (struct IDiscRecorder2 *)ppv;
  v13 = DiscRecorderForVolume;
  if ( DiscRecorderForVolume < 0 )
    goto LABEL_50;
  ppv = 0;
  v13 = CoCreateInstance(
          &CLSID_MsftDiscFormat2Data,
          0,
          0x17u,
          &GUID_27354153_9f64_5b0f_8f00_5d77afbe261e,
          (LPVOID *)&ppv);
  if ( v13 < 0 )
    goto LABEL_43;
  v49.Ptr = 0;
  v13 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct _EVENT_DATA_DESCRIPTOR *))ppv->lpVtbl->QueryInterface)(
          ppv,
          &GUID_d2ffd834_958b_426d_8470_2a13879c6a91,
          &v49);
  if ( v13 >= 0 )
    v13 = (*(__int64 (__fastcall **)(ULONGLONG, _QWORD))(*(_QWORD *)v49.Ptr + 24LL))(
            v49.Ptr,
            *((_DWORD *)this + 34) != 0 ? 2 : 0);
  if ( v49.Ptr )
    (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v49.Ptr + 16LL))(v49.Ptr);
  if ( v13 < 0 )
    goto LABEL_43;
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 19) + 24LL))(*((_QWORD *)this + 19), 0);
  v14 = SysAllocString(L"ISOBURN");
  ((void (__fastcall *)(struct IUnknown *, OLECHAR *))ppv->lpVtbl[10].QueryInterface)(ppv, v14);
  SysFreeString(v14);
  v13 = ((__int64 (__fastcall *)(struct IUnknown *, struct IDiscRecorder2 *))ppv->lpVtbl[4].QueryInterface)(ppv, v12);
  if ( v13 < 0 )
    goto LABEL_43;
  v15 = ppv;
  LOWORD(v26) = 0;
  v16 = ((__int64 (__fastcall *)(struct IUnknown *, int *))ppv->lpVtbl[3].AddRef)(ppv, &v26);
  v13 = v16;
  if ( v16 >= 0 && !(_WORD)v26 )
  {
    lpVtbl = v15->lpVtbl;
    LODWORD(v49.Ptr) = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, struct _EVENT_DATA_DESCRIPTOR *))lpVtbl[9].Release)(v15, &v49) >= 0
      && LODWORD(v49.Ptr) <= 0xA )
    {
      v18 = 1160;
      if ( _bittest(&v18, v49.Ptr) )
        v10 = 1;
    }
    v13 = -1062539260;
LABEL_28:
    if ( v10 && *((_DWORD *)this + 35) )
    {
      if ( (int)CIsoBurn::_EraseMedia(v12, *((struct IIsoBurnProgress **)this + 19)) >= 0 )
      {
        v1 = 0;
LABEL_34:
        v13 = ATL::_IDispEvent::DispEventAdvise((CIsoBurn *)((char *)this + 8), ppv, &IID_DDiscFormat2DataEvents);
        if ( v13 < 0 )
          goto LABEL_43;
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 19) + 24LL))(*((_QWORD *)this + 19), 2);
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v19, (int)&CDBurn_IsoBurn_Task_Start, v20, v21, &v49);
        v13 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))ppv->lpVtbl[13].Release)(ppv, v27);
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v22, (int)&CDBurn_IsoBurn_Task_Stop, v23, v24, &v49);
        goto LABEL_42;
      }
      v10 = 0;
    }
    goto LABEL_33;
  }
  if ( v16 == -1062539260 )
    goto LABEL_28;
LABEL_33:
  v1 = v13 == -1062600187;
  if ( v13 >= 0 )
    goto LABEL_34;
  if ( (!v10 || *((_DWORD *)this + 35)) && v13 != -1062600187 )
LABEL_42:
    ((void (__fastcall *)(struct IDiscRecorder2 *))v12->lpVtbl->EjectMedia)(v12);
LABEL_43:
  if ( ppv )
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
  if ( v13 >= 0 )
  {
    v5 = 10;
    LODWORD(v49.Ptr) = 4326;
    if ( EventEnabled(Microsoft_Windows_Shell_Core_Provider_Context, &CDBurn_SQM_IsoBurn_Session) )
    {
      v26 = 6;
      LODWORD(ppv) = 1;
      UserData.Ptr = (ULONGLONG)&g_SHSqmGlobalSession;
      v53 = &v26;
      v51 = &v49;
      *(_QWORD *)&UserData.Size = 16;
      p_ppv = &ppv;
      v52 = 4;
      v54 = 4;
      v56 = 4;
      EventWrite(Microsoft_Windows_Shell_Core_Provider_Context, &CDBurn_SQM_IsoBurn_Session, 4u, &UserData);
    }
    goto LABEL_53;
  }
  if ( v1 )
  {
    v5 = 5;
    goto LABEL_52;
  }
LABEL_50:
  if ( v13 != -1062539260 )
    goto LABEL_53;
  v5 = 4 - (v10 != 0);
LABEL_52:
  v13 = 0;
LABEL_53:
  if ( v12 )
    ((void (__fastcall *)(struct IDiscRecorder2 *))v12->lpVtbl->Release)(v12);
LABEL_56:
  wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v29,
    (unsigned int)v13);
  if ( v13 < 0 )
    v5 = 1;
  if ( v4 != (void *)-1LL )
  {
    PowerClearRequest(v4, PowerRequestSystemRequired);
    CloseHandle(v4);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 19) + 40LL))(
    *((_QWORD *)this + 19),
    v5,
    (unsigned int)v13);
  IsoBurnLoggingTelemetry::BurnImage::~BurnImage((IsoBurnLoggingTelemetry::BurnImage *)&v29);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
}

```

## disassembly

```asm
0x140009e64  push    rbp
0x140009e66  push    rbx
0x140009e67  push    rsi
0x140009e68  push    rdi
0x140009e69  push    r12
0x140009e6b  push    r13
0x140009e6d  push    r14
0x140009e6f  push    r15
0x140009e71  lea     rbp, [rsp-128h]
0x140009e79  sub     rsp, 228h
0x140009e80  mov     rax, cs:__security_cookie
0x140009e87  xor     rax, rsp
0x140009e8a  mov     [rbp+160h+var_50], rax
0x140009e91  mov     rax, cs:hInstance
0x140009e98  xor     esi, esi
0x140009e9a  mov     r15, rcx
0x140009e9d  mov     [rsp+260h+var_220], rsi
0x140009ea2  lea     rcx, [rsp+260h+Context]; Context
0x140009ea7  mov     [rsp+260h+Context.Version], esi
0x140009eab  mov     qword ptr [rsp+260h+Context.Reason], rax
0x140009eb0  mov     qword ptr [rsp+260h+Context.Reason+10h], rsi
0x140009eb5  mov     [rsp+260h+Context.Flags], 2
0x140009ebd  mov     qword ptr [rsp+260h+Context.Reason+8], 106h
0x140009ec6  call    cs:__imp_PowerCreateRequest
0x140009ecc  lea     ebx, [rsi+1]
0x140009ecf  mov     r13, rax
0x140009ed2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009ed6  jz      short loc_140009EE3
0x140009ed8  mov     edx, ebx; RequestType
0x140009eda  mov     rcx, rax; PowerRequest
0x140009edd  call    cs:__imp_PowerSetRequest
0x140009ee3  lea     rax, aBurnimage; "BurnImage"
0x140009eea  mov     [rsp+260h+var_1E8], esi
0x140009eee  xorps   xmm0, xmm0
0x140009ef1  mov     [rbp+160h+var_1B8], rax
0x140009ef5  xor     edx, edx; Val
0x140009ef7  movdqa  [rbp+160h+var_100], xmm0
0x140009efc  mov     r8d, 98h; Size
0x140009f02  mov     [rsp+260h+var_1E4], sil
0x140009f07  lea     rcx, [rbp+160h+var_198]; void *
0x140009f0b  mov     [rbp+160h+var_1A8], sil
0x140009f0f  mov     [rbp+160h+var_1C0], esi
0x140009f12  mov     [rbp+160h+var_1B0], rsi
0x140009f16  mov     [rbp+160h+var_1A0], esi
0x140009f19  call    memset_0
0x140009f1e  xor     eax, eax
0x140009f20  mov     [rbp+160h+var_F0], ebx
0x140009f23  mov     [rbp+160h+var_E8], rax
0x140009f27  lea     rcx, [rsp+260h+var_1F0]; this
0x140009f2c  lea     rax, [rsp+260h+var_1E8]
0x140009f31  mov     [rbp+160h+var_D8], rsi
0x140009f38  mov     [rbp+160h+var_E0], rax
0x140009f3f  mov     r12d, esi
0x140009f42  lea     rax, [rsp+260h+var_1F0]
0x140009f47  mov     [rbp+160h+var_D0], rsi
0x140009f4e  mov     [rbp+160h+var_C8], rax
0x140009f55  lea     rax, [rbp+160h+var_1C0]
0x140009f59  mov     [rbp+160h+var_B0], rax
0x140009f60  lea     rax, ??_7BurnImage@IsoBurnLoggingTelemetry@@6B@; const IsoBurnLoggingTelemetry::BurnImage::`vftable'
0x140009f67  mov     [rsp+260h+var_1F0], rax
0x140009f6c  mov     [rbp+160h+var_C0], rsi
0x140009f73  mov     [rbp+160h+var_B8], esi
0x140009f79  mov     [rbp+160h+var_A8], sil
0x140009f80  call    ?StartActivity@BurnImage@IsoBurnLoggingTelemetry@@QEAAXXZ; IsoBurnLoggingTelemetry::BurnImage::StartActivity(void)
0x140009f85  mov     rdi, [r15+78h]
0x140009f89  lea     rax, [rsp+260h+var_230]
0x140009f8e  xor     edx, edx; pUnkOuter
0x140009f90  mov     [rsp+260h+var_230], rsi
0x140009f95  lea     r9, _GUID_6ca38be5_fbbb_4800_95a1_a438865eb0d4; riid
0x140009f9c  mov     [rsp+260h+ppv], rax; ppv
0x140009fa1  lea     rcx, CLSID_MsftIsoImageManager; rclsid
0x140009fa8  lea     r8d, [rdx+17h]; dwClsContext
0x140009fac  call    cs:__imp_CoCreateInstance
0x140009fb2  mov     ebx, eax
0x140009fb4  test    eax, eax
0x140009fb6  js      short loc_14000A022
0x140009fb8  mov     rcx, rdi; psz
0x140009fbb  call    cs:__imp_SysAllocString
0x140009fc1  mov     rdi, rax
0x140009fc4  test    rax, rax
0x140009fc7  jz      short loc_14000A01D
0x140009fc9  mov     rcx, [rsp+260h+var_230]
0x140009fce  mov     rdx, [rcx]
0x140009fd1  mov     rax, [rdx+48h]
0x140009fd5  mov     rdx, rdi
0x140009fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fdd  mov     rcx, rdi; bstrString
0x140009fe0  mov     ebx, eax
0x140009fe2  call    cs:__imp_SysFreeString
0x140009fe8  test    ebx, ebx
0x140009fea  js      short loc_14000A022
0x140009fec  mov     rcx, [rsp+260h+var_230]
0x140009ff1  mov     rax, [rcx]
0x140009ff4  mov     rax, [rax+58h]
0x140009ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ffd  mov     ebx, eax
0x140009fff  test    eax, eax
0x14000a001  js      short loc_14000A022
0x14000a003  mov     rcx, [rsp+260h+var_230]
0x14000a008  lea     rdx, [rsp+260h+var_220]
0x14000a00d  mov     rax, [rcx]
0x14000a010  mov     rax, [rax+40h]
0x14000a014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a019  mov     ebx, eax
0x14000a01b  jmp     short loc_14000A022
0x14000a01d  mov     ebx, 8007000Eh
0x14000a022  mov     rcx, [rsp+260h+var_230]
0x14000a027  test    rcx, rcx
0x14000a02a  jz      short loc_14000A038
0x14000a02c  mov     rax, [rcx]
0x14000a02f  mov     rax, [rax+10h]
0x14000a033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a038  test    ebx, ebx
0x14000a03a  js      loc_14000A403
0x14000a040  mov     rcx, [r15+80h]; lpString1
0x14000a047  lea     rdx, [rsp+260h+var_230]; struct IDiscRecorder2 **
0x14000a04c  mov     r14b, sil
0x14000a04f  mov     [rsp+260h+var_230], rsi
0x14000a054  call    ?_GetDiscRecorderForVolume@CIsoBurn@@CAJPEBGPEAPEAUIDiscRecorder2@@@Z; CIsoBurn::_GetDiscRecorderForVolume(ushort const *,IDiscRecorder2 * *)
0x14000a059  mov     rbx, [rsp+260h+var_230]
0x14000a05e  mov     edi, eax
0x14000a060  test    eax, eax
0x14000a062  js      loc_14000A3D9
0x14000a068  xor     edx, edx; pUnkOuter
0x14000a06a  mov     [rsp+260h+var_230], rsi
0x14000a06f  lea     rax, [rsp+260h+var_230]
0x14000a074  lea     r9, _GUID_27354153_9f64_5b0f_8f00_5d77afbe261e; riid
0x14000a07b  mov     [rsp+260h+ppv], rax; ppv
0x14000a080  lea     rcx, CLSID_MsftDiscFormat2Data; rclsid
0x14000a087  lea     r8d, [rdx+17h]; dwClsContext
0x14000a08b  call    cs:__imp_CoCreateInstance
0x14000a091  xor     ecx, ecx
0x14000a093  mov     edi, eax
0x14000a095  test    eax, eax
0x14000a097  js      loc_14000A2DF
0x14000a09d  mov     [rbp+160h+var_A0.Ptr], rcx
0x14000a0a4  lea     r8, [rbp+160h+var_A0]
0x14000a0ab  mov     rcx, [rsp+260h+var_230]
0x14000a0b0  lea     rdx, _GUID_d2ffd834_958b_426d_8470_2a13879c6a91
0x14000a0b7  mov     rax, [rcx]
0x14000a0ba  mov     rax, [rax]
0x14000a0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0c2  mov     edi, eax
0x14000a0c4  test    eax, eax
0x14000a0c6  js      short loc_14000A0EB
0x14000a0c8  mov     eax, [r15+88h]
0x14000a0cf  mov     rcx, [rbp+160h+var_A0.Ptr]
0x14000a0d6  neg     eax
0x14000a0d8  sbb     edx, edx
0x14000a0da  and     edx, 2
0x14000a0dd  mov     r8, [rcx]
0x14000a0e0  mov     rax, [r8+18h]
0x14000a0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0e9  mov     edi, eax
0x14000a0eb  mov     rcx, [rbp+160h+var_A0.Ptr]
0x14000a0f2  test    rcx, rcx
0x14000a0f5  jz      short loc_14000A103
0x14000a0f7  mov     rax, [rcx]
0x14000a0fa  mov     rax, [rax+10h]
0x14000a0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a103  test    edi, edi
0x14000a105  js      loc_14000A2DF
0x14000a10b  mov     rcx, [r15+98h]
0x14000a112  xor     edx, edx
0x14000a114  mov     rax, [rcx]
0x14000a117  mov     rax, [rax+18h]
0x14000a11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a120  lea     rcx, psz; "ISOBURN"
0x14000a127  call    cs:__imp_SysAllocString
0x14000a12d  mov     rcx, [rsp+260h+var_230]
0x14000a132  mov     rdi, rax
0x14000a135  mov     rdx, [rcx]
0x14000a138  mov     rax, [rdx+0F0h]
0x14000a13f  mov     rdx, rdi
0x14000a142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a147  mov     rcx, rdi; bstrString
0x14000a14a  call    cs:__imp_SysFreeString
0x14000a150  mov     rcx, [rsp+260h+var_230]
0x14000a155  mov     rdx, rbx
0x14000a158  mov     rax, [rcx]
0x14000a15b  mov     rax, [rax+60h]
0x14000a15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a164  xor     ecx, ecx
0x14000a166  mov     edi, eax
0x14000a168  test    eax, eax
0x14000a16a  js      loc_14000A2DF
0x14000a170  mov     rsi, [rsp+260h+var_230]
0x14000a175  lea     rdx, [rsp+260h+var_228]
0x14000a17a  mov     word ptr [rsp+260h+var_228], cx
0x14000a17f  mov     rcx, rsi
0x14000a182  mov     rax, [rsi]
0x14000a185  mov     rax, [rax+50h]
0x14000a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a18e  xor     ecx, ecx
0x14000a190  mov     edi, eax
0x14000a192  test    eax, eax
0x14000a194  js      short loc_14000A1E3
0x14000a196  cmp     word ptr [rsp+260h+var_228], cx
0x14000a19b  jnz     short loc_14000A1E3
0x14000a19d  mov     rax, [rsi]
0x14000a1a0  lea     rdx, [rbp+160h+var_A0]
0x14000a1a7  mov     dword ptr [rbp+160h+var_A0.Ptr], ecx
0x14000a1ad  mov     rcx, rsi
0x14000a1b0  mov     rax, [rax+0E8h]
0x14000a1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1bc  xor     ecx, ecx
0x14000a1be  test    eax, eax
0x14000a1c0  js      short loc_14000A1DC
0x14000a1c2  mov     eax, dword ptr [rbp+160h+var_A0.Ptr]
0x14000a1c8  cmp     eax, 0Ah
0x14000a1cb  ja      short loc_14000A1DC
0x14000a1cd  mov     ecx, 488h
0x14000a1d2  bt      ecx, eax
0x14000a1d5  jnb     short loc_14000A1DA
0x14000a1d7  mov     r14b, 1
0x14000a1da  xor     ecx, ecx
0x14000a1dc  mov     edi, 0C0AAF004h
0x14000a1e1  jmp     short loc_14000A1EA
0x14000a1e3  cmp     eax, 0C0AAF004h
0x14000a1e8  jnz     short loc_14000A215
0x14000a1ea  test    r14b, r14b
0x14000a1ed  jz      short loc_14000A215
0x14000a1ef  cmp     [r15+8Ch], ecx
0x14000a1f6  jz      short loc_14000A215
0x14000a1f8  mov     rdx, [r15+98h]; struct IIsoBurnProgress *
0x14000a1ff  mov     rcx, rbx; struct IDiscRecorder2 *
0x14000a202  call    ?_EraseMedia@CIsoBurn@@CAJPEAUIDiscRecorder2@@PEAUIIsoBurnProgress@@@Z; CIsoBurn::_EraseMedia(IDiscRecorder2 *,IIsoBurnProgress *)
0x14000a207  xor     ecx, ecx
0x14000a209  test    eax, eax
0x14000a20b  js      short loc_14000A212
0x14000a20d  mov     sil, cl
0x14000a210  jmp     short loc_14000A228
0x14000a212  mov     r14b, cl
0x14000a215  mov     eax, 0C0AA0205h
0x14000a21a  cmp     edi, eax
0x14000a21c  setz    sil
0x14000a220  test    edi, edi
0x14000a222  js      loc_14000A2BE
0x14000a228  mov     rdx, [rsp+260h+var_230]; struct IUnknown *
0x14000a22d  lea     rcx, [r15+8]; this
0x14000a231  lea     r8, IID_DDiscFormat2DataEvents; struct _GUID *
0x14000a238  call    ?DispEventAdvise@_IDispEvent@ATL@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; ATL::_IDispEvent::DispEventAdvise(IUnknown *,_GUID const *)
0x14000a23d  mov     edi, eax
0x14000a23f  test    eax, eax
0x14000a241  js      loc_14000A2DF
0x14000a247  mov     rcx, [r15+98h]
0x14000a24e  mov     edx, 2
0x14000a253  mov     rax, [rcx]
0x14000a256  mov     rax, [rax+18h]
0x14000a25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a25f  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x14000a266  jz      short loc_14000A280
0x14000a268  lea     rax, [rbp+160h+var_A0]
0x14000a26f  lea     rdx, CDBurn_IsoBurn_Task_Start; int
0x14000a276  mov     [rsp+260h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x14000a27b  call    McGenEventWrite_EventWriteTransfer
0x14000a280  mov     rcx, [rsp+260h+var_230]
0x14000a285  mov     rdx, [rsp+260h+var_220]
0x14000a28a  mov     rax, [rcx]
0x14000a28d  mov     rax, [rax+148h]
0x14000a294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a299  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x14000a2a0  mov     edi, eax
0x14000a2a2  jz      short loc_14000A2D0
0x14000a2a4  lea     rax, [rbp+160h+var_A0]
0x14000a2ab  lea     rdx, CDBurn_IsoBurn_Task_Stop; int
0x14000a2b2  mov     [rsp+260h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x14000a2b7  call    McGenEventWrite_EventWriteTransfer
0x14000a2bc  jmp     short loc_14000A2D0
0x14000a2be  test    r14b, r14b
0x14000a2c1  jz      short loc_14000A2CC
0x14000a2c3  cmp     [r15+8Ch], ecx
0x14000a2ca  jz      short loc_14000A2DF
0x14000a2cc  cmp     edi, eax
0x14000a2ce  jz      short loc_14000A2DF
0x14000a2d0  mov     rax, [rbx]
0x14000a2d3  mov     rcx, rbx
0x14000a2d6  mov     rax, [rax+38h]
0x14000a2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2df  mov     rcx, [rsp+260h+var_230]
0x14000a2e4  test    rcx, rcx
0x14000a2e7  jz      short loc_14000A2F5
0x14000a2e9  mov     rax, [rcx]
0x14000a2ec  mov     rax, [rax+10h]
0x14000a2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2f5  test    edi, edi
0x14000a2f7  js      loc_14000A3CA
0x14000a2fd  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x14000a304  lea     rdx, CDBurn_SQM_IsoBurn_Session; EventDescriptor
0x14000a30b  mov     r12d, 0Ah
0x14000a311  mov     dword ptr [rbp+160h+var_A0.Ptr], 10E6h
0x14000a31b  call    cs:__imp_EventEnabled
0x14000a321  test    al, al
0x14000a323  jz      loc_14000A3ED
0x14000a329  xorps   xmm0, xmm0
0x14000a32c  mov     [rsp+260h+var_228], 6
0x14000a334  movups  [rbp+160h+var_78], xmm0
0x14000a33b  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x14000a342  mov     dword ptr [rsp+260h+var_230], 1
0x14000a34a  mov     [rbp+160h+UserData.Ptr], rax
  ... truncated ...
```
