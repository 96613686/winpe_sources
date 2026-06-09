# CDpiCompensation::Register(IDImageFactoryInternal *,HINSTANCE__ *)

- ea: `0x1801d4460`
- end: `0x1801d45b0`
- name: `?Register@CDpiCompensation@@SAJPEAVIDImageFactoryInternal@@PEAUHINSTANCE__@@@Z`
- size: `336`
- prototype: `static int(struct IDImageFactoryInternal *, HINSTANCE)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1801a043c`
- `0x1801d3c04`
- `0x1801d4460`
- `0x18025b100`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801d449e`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801d449e`

## string_xrefs

- `0x1801d4485`: `DPICOMPENSATION.XML`

## pseudocode

```c
__int64 __fastcall CDpiCompensation::Register(struct IDImageFactoryInternal *a1, HINSTANCE a2)
{
  struct IStream *v3; // rbx
  HRSRC Resource; // rax
  int StreamFromResourceHandle; // eax
  unsigned int v7; // edi
  int v8; // ecx
  int v9; // eax
  struct IStream *v11[2]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v12[10]; // [rsp+50h] [rbp-19h] BYREF

  v3 = 0;
  v11[0] = 0;
  Resource = FindResourceExW(a2, (LPCWSTR)0x17, L"DPICOMPENSATION.XML", 0);
  if ( Resource )
  {
    StreamFromResourceHandle = CreateStreamFromResourceHandle(a2, Resource, v11);
    v7 = StreamFromResourceHandle;
    if ( StreamFromResourceHandle < 0 )
    {
LABEL_5:
      DoStackCapture(StreamFromResourceHandle);
      v8 = v7;
LABEL_9:
      DoStackCapture(v8);
      goto LABEL_10;
    }
    v3 = v11[0];
  }
  else
  {
    StreamFromResourceHandle = GetLastErrorAsFailHr();
    v7 = StreamFromResourceHandle;
    if ( StreamFromResourceHandle < 0 )
      goto LABEL_5;
  }
  v12[0] = L"InterpolationMode";
  v12[1] = ValueSetter<long (CDpiCompensation::*)(enum D2D1_DPICOMPENSATION_INTERPOLATION_MODE),&public: long CDpiCompensation::SetInterpolationMode(enum D2D1_DPICOMPENSATION_INTERPOLATION_MODE),ID2D1EffectImpl>;
  v12[2] = ValueGetter<enum D2D1_DPICOMPENSATION_INTERPOLATION_MODE (CDpiCompensation::*)(void)const,&public: enum D2D1_DPICOMPENSATION_INTERPOLATION_MODE CDpiCompensation::GetInterpolationMode(void)const,ID2D1EffectImpl>;
  v12[3] = L"BorderMode";
  v12[4] = ValueSetter<long (CDpiCompensation::*)(enum D2D1_BORDER_MODE),&public: long CDpiCompensation::SetBorderMode(enum D2D1_BORDER_MODE),ID2D1EffectImpl>;
  v12[5] = ValueGetter<enum D2D1_BORDER_MODE (CDpiCompensation::*)(void)const,&public: enum D2D1_BORDER_MODE CDpiCompensation::GetBorderMode(void)const,ID2D1EffectImpl>;
  v12[6] = L"InputDpi";
  v12[7] = ValueSetter<long (CDpiCompensation::*)(D2D_POINT_2F),&public: long CDpiCompensation::SetInputDpi(D2D_POINT_2F),ID2D1EffectImpl>;
  v12[8] = ValueGetter<D2D_POINT_2F (CBitmapSource::*)(void)const,&public: D2D_POINT_2F CBitmapSource::GetScale(void)const,ID2D1EffectImpl>;
  v9 = (*(__int64 (__fastcall **)(struct IDImageFactoryInternal *, GUID *, struct IStream *, _QWORD *, int, __int64 (__fastcall *)(), _DWORD))(*(_QWORD *)a1 + 32LL))(
         a1,
         &CLSID_D2D1DpiCompensation,
         v3,
         v12,
         3,
         CEffectBaseT<ID2D1EffectImpl>::Create<CDpiCompensation>,
         0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = v9;
    goto LABEL_9;
  }
LABEL_10:
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(v11);
  return v7;
}

```

## disassembly

```asm
0x1801d4460  mov     [rsp-8+arg_10], rbx
0x1801d4465  push    rbp
0x1801d4466  push    rsi
0x1801d4467  push    rdi
0x1801d4468  lea     rbp, [rsp-47h]
0x1801d446d  sub     rsp, 0B0h
0x1801d4474  mov     rax, cs:__security_cookie
0x1801d447b  xor     rax, rsp
0x1801d447e  mov     [rbp+57h+var_20], rax
0x1801d4482  mov     rdi, rdx
0x1801d4485  lea     r8, aDpicompensatio; "DPICOMPENSATION.XML"
0x1801d448c  xor     ebx, ebx
0x1801d448e  mov     rsi, rcx
0x1801d4491  xor     r9d, r9d; wLanguage
0x1801d4494  mov     [rbp+57h+var_80], rbx
0x1801d4498  mov     rcx, rdi; hModule
0x1801d449b  lea     edx, [rbx+17h]; lpType
0x1801d449e  call    cs:__imp_FindResourceExW
0x1801d44a4  test    rax, rax
0x1801d44a7  jnz     short loc_1801D44B6
0x1801d44a9  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1801d44ae  mov     edi, eax
0x1801d44b0  test    eax, eax
0x1801d44b2  jns     short loc_1801D44DD
0x1801d44b4  jmp     short loc_1801D44CB
0x1801d44b6  lea     r8, [rbp+57h+var_80]; struct IStream **
0x1801d44ba  mov     rdx, rax; hResInfo
0x1801d44bd  mov     rcx, rdi; hModule
0x1801d44c0  call    ?CreateStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z; CreateStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)
0x1801d44c5  mov     edi, eax
0x1801d44c7  test    eax, eax
0x1801d44c9  jns     short loc_1801D44D9
0x1801d44cb  mov     ecx, eax; int
0x1801d44cd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d44d2  mov     ecx, edi
0x1801d44d4  jmp     loc_1801D4581
0x1801d44d9  mov     rbx, [rbp+57h+var_80]
0x1801d44dd  lea     rax, aInterpolationm; "InterpolationMode"
0x1801d44e4  mov     [rsp+0C0h+var_90], 0
0x1801d44ec  mov     [rbp+57h+var_70], rax
0x1801d44f0  lea     rcx, ??$Create@VCDpiCompensation@@@?$CEffectBaseT@UID2D1EffectImpl@@@@SAJPEAPEAUIUnknown@@@Z; CEffectBaseT<ID2D1EffectImpl>::Create<CDpiCompensation>(IUnknown * *)
0x1801d44f7  mov     [rsp+0C0h+var_98], rcx
0x1801d44fc  lea     rax, ??$ValueSetter@P8CDpiCompensation@@EAAJW4D2D1_DPICOMPENSATION_INTERPOLATION_MODE@@@Z$1?SetInterpolationMode@1@QEAAJ0@ZUID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CDpiCompensation::*)(D2D1_DPICOMPENSATION_INTERPOLATION_MODE),&CDpiCompensation::SetInterpolationMode(D2D1_DPICOMPENSATION_INTERPOLATION_MODE),ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x1801d4503  mov     [rbp+57h+var_68], rax
0x1801d4507  lea     r9, [rbp+57h+var_70]
0x1801d450b  lea     rax, ??$ValueGetter@P8CDpiCompensation@@EBA?AW4D2D1_DPICOMPENSATION_INTERPOLATION_MODE@@XZ$1?GetInterpolationMode@1@QEBA?AW42@XZUID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<D2D1_DPICOMPENSATION_INTERPOLATION_MODE (CDpiCompensation::*)(void),&CDpiCompensation::GetInterpolationMode(void),ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x1801d4512  mov     [rsp+0C0h+var_A0], 3
0x1801d451a  mov     [rbp+57h+var_60], rax
0x1801d451e  lea     rdx, ?CLSID_D2D1DpiCompensation@@3U_GUID@@B; _GUID const CLSID_D2D1DpiCompensation
0x1801d4525  lea     rax, aBordermode; "BorderMode"
0x1801d452c  mov     r8, rbx
0x1801d452f  mov     [rbp+57h+var_58], rax
0x1801d4533  mov     rcx, rsi
0x1801d4536  lea     rax, ??$ValueSetter@P8CDpiCompensation@@EAAJW4D2D1_BORDER_MODE@@@Z$1?SetBorderMode@1@QEAAJ0@ZUID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CDpiCompensation::*)(D2D1_BORDER_MODE),&CDpiCompensation::SetBorderMode(D2D1_BORDER_MODE),ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x1801d453d  mov     [rbp+57h+var_50], rax
0x1801d4541  lea     rax, ??$ValueGetter@P8CDpiCompensation@@EBA?AW4D2D1_BORDER_MODE@@XZ$1?GetBorderMode@1@QEBA?AW42@XZUID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<D2D1_BORDER_MODE (CDpiCompensation::*)(void),&CDpiCompensation::GetBorderMode(void),ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x1801d4548  mov     [rbp+57h+var_48], rax
0x1801d454c  lea     rax, aInputdpi; "InputDpi"
0x1801d4553  mov     [rbp+57h+var_40], rax
0x1801d4557  lea     rax, ??$ValueSetter@P8CDpiCompensation@@EAAJUD2D_POINT_2F@@@Z$1?SetInputDpi@1@QEAAJ0@ZUID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CDpiCompensation::*)(D2D_POINT_2F),&CDpiCompensation::SetInputDpi(D2D_POINT_2F),ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x1801d455e  mov     [rbp+57h+var_38], rax
0x1801d4562  lea     rax, ??$ValueGetter@P8CBitmapSource@@EBA?AUD2D_POINT_2F@@XZ$1?GetScale@1@QEBA?AU2@XZUID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<D2D_POINT_2F (CBitmapSource::*)(void),&CBitmapSource::GetScale(void),ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x1801d4569  mov     [rbp+57h+var_30], rax
0x1801d456d  mov     rax, [rsi]
0x1801d4570  mov     rax, [rax+20h]
0x1801d4574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4579  mov     edi, eax
0x1801d457b  test    eax, eax
0x1801d457d  jns     short loc_1801D4586
0x1801d457f  mov     ecx, eax; int
0x1801d4581  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d4586  lea     rcx, [rbp+57h+var_80]; void *
0x1801d458a  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1801d458f  mov     eax, edi
0x1801d4591  mov     rcx, [rbp+57h+var_20]
0x1801d4595  xor     rcx, rsp; StackCookie
0x1801d4598  call    __security_check_cookie
0x1801d459d  mov     rbx, [rsp+0C0h+arg_10]
0x1801d45a5  add     rsp, 0B0h
0x1801d45ac  pop     rdi
0x1801d45ad  pop     rsi
0x1801d45ae  pop     rbp
0x1801d45af  retn
```
