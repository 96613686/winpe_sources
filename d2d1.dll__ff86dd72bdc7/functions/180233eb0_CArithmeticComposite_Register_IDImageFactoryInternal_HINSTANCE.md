# CArithmeticComposite::Register(IDImageFactoryInternal *,HINSTANCE__ *)

- ea: `0x180233eb0`
- end: `0x180233fd3`
- name: `?Register@CArithmeticComposite@@SAJPEAVIDImageFactoryInternal@@PEAUHINSTANCE__@@@Z`
- size: `291`
- prototype: `static int(struct IDImageFactoryInternal *, HINSTANCE)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1801a043c`
- `0x1801d3c04`
- `0x180233eb0`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180233edc`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180233edc`

## string_xrefs

- `0x180233ec3`: `ARITHMETIC.XML`

## pseudocode

```c
__int64 __fastcall CArithmeticComposite::Register(struct IDImageFactoryInternal *a1, HINSTANCE a2)
{
  struct IStream *v3; // rbx
  HRSRC Resource; // rax
  int LastErrorAsFailHr; // eax
  unsigned int v7; // edi
  int v8; // ecx
  int v9; // eax
  _QWORD v11[6]; // [rsp+40h] [rbp-38h] BYREF
  struct IStream *v12; // [rsp+90h] [rbp+18h] BYREF

  v3 = 0;
  v12 = 0;
  Resource = FindResourceExW(a2, (LPCWSTR)0x17, L"ARITHMETIC.XML", 0);
  if ( Resource )
  {
    LastErrorAsFailHr = CreateStreamFromResourceHandle(a2, Resource, &v12);
    v7 = LastErrorAsFailHr;
    if ( LastErrorAsFailHr < 0 )
    {
LABEL_5:
      DoStackCapture(LastErrorAsFailHr);
      v8 = v7;
LABEL_9:
      DoStackCapture(v8);
      goto LABEL_10;
    }
    v3 = v12;
  }
  else
  {
    LastErrorAsFailHr = GetLastErrorAsFailHr();
    v7 = LastErrorAsFailHr;
    if ( LastErrorAsFailHr < 0 )
      goto LABEL_5;
  }
  v11[0] = L"Coefficients";
  v11[1] = ValueSetter<long (CVignette::*)(D2D_VECTOR_4F),{public: long CVignette::SetColor(D2D_VECTOR_4F),0},ID2D1EffectImpl>;
  v11[2] = ValueGetter<D2D_VECTOR_4F (CArithmeticComposite::*)(void)const,{public: D2D_VECTOR_4F CArithmeticComposite::GetCoefficients(void)const,0},ID2D1EffectImpl>;
  v11[3] = L"ClampOutput";
  v11[4] = ValueSetter<long (CArithmeticComposite::*)(int),{public: long CArithmeticComposite::SetClampOutput(int),0},ID2D1EffectImpl>;
  v11[5] = ValueGetter<int (CArithmeticComposite::*)(void)const,{public: int CArithmeticComposite::GetClampOutput(void)const,0},ID2D1EffectImpl>;
  v9 = (*(__int64 (__fastcall **)(struct IDImageFactoryInternal *, GUID *, struct IStream *, _QWORD *, int, __int64 (__fastcall *)(), _DWORD))(*(_QWORD *)a1 + 32LL))(
         a1,
         &CLSID_D2D1ArithmeticComposite,
         v3,
         v11,
         2,
         CEffectBaseT<ID2D1EffectImpl>::Create<CArithmeticComposite>,
         0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = v9;
    goto LABEL_9;
  }
LABEL_10:
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v12);
  return v7;
}

```

## disassembly

```asm
0x180233eb0  mov     rax, rsp
0x180233eb3  mov     [rax+8], rbx
0x180233eb7  mov     [rax+10h], rsi
0x180233ebb  push    rdi
0x180233ebc  sub     rsp, 70h
0x180233ec0  mov     rdi, rdx
0x180233ec3  lea     r8, aArithmeticXml; "ARITHMETIC.XML"
0x180233eca  xor     ebx, ebx
0x180233ecc  mov     rsi, rcx
0x180233ecf  xor     r9d, r9d; wLanguage
0x180233ed2  mov     [rax+18h], rbx
0x180233ed6  mov     rcx, rdi; hModule
0x180233ed9  lea     edx, [rbx+17h]; lpType
0x180233edc  call    cs:__imp_FindResourceExW
0x180233ee2  test    rax, rax
0x180233ee5  jnz     short loc_180233EF4
0x180233ee7  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x180233eec  mov     edi, eax
0x180233eee  test    eax, eax
0x180233ef0  jns     short loc_180233F23
0x180233ef2  jmp     short loc_180233F0D
0x180233ef4  lea     r8, [rsp+78h+arg_10]; struct IStream **
0x180233efc  mov     rdx, rax; hResInfo
0x180233eff  mov     rcx, rdi; hModule
0x180233f02  call    ?CreateStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z; CreateStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)
0x180233f07  mov     edi, eax
0x180233f09  test    eax, eax
0x180233f0b  jns     short loc_180233F1B
0x180233f0d  mov     ecx, eax; int
0x180233f0f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180233f14  mov     ecx, edi
0x180233f16  jmp     loc_180233FAD
0x180233f1b  mov     rbx, [rsp+78h+arg_10]
0x180233f23  lea     rax, aCoefficients; "Coefficients"
0x180233f2a  mov     [rsp+78h+var_48], 0
0x180233f32  mov     [rsp+78h+var_38], rax
0x180233f37  lea     rcx, ??$Create@VCArithmeticComposite@@@?$CEffectBaseT@UID2D1EffectImpl@@@@SAJPEAPEAUIUnknown@@@Z; CEffectBaseT<ID2D1EffectImpl>::Create<CArithmeticComposite>(IUnknown * *)
0x180233f3e  mov     [rsp+78h+var_50], rcx
0x180233f43  lea     rax, ??$ValueSetter@P8CVignette@@EAAJUD2D_VECTOR_4F@@@Z$H?SetColor@1@QEAAJ0@ZA@UID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CVignette::*)(D2D_VECTOR_4F),{CVignette::SetColor(D2D_VECTOR_4F),0},ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x180233f4a  mov     [rsp+78h+var_30], rax
0x180233f4f  lea     r9, [rsp+78h+var_38]
0x180233f54  lea     rax, ??$ValueGetter@P8CArithmeticComposite@@EBA?AUD2D_VECTOR_4F@@XZ$H?GetCoefficients@1@QEBA?AU2@XZA@UID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<D2D_VECTOR_4F (CArithmeticComposite::*)(void),{CArithmeticComposite::GetCoefficients(void),0},ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x180233f5b  mov     [rsp+78h+var_58], 2
0x180233f63  mov     [rsp+78h+var_28], rax
0x180233f68  lea     rdx, ?CLSID_D2D1ArithmeticComposite@@3U_GUID@@B; _GUID const CLSID_D2D1ArithmeticComposite
0x180233f6f  lea     rax, aClampoutput; "ClampOutput"
0x180233f76  mov     r8, rbx
0x180233f79  mov     [rsp+78h+var_20], rax
0x180233f7e  mov     rcx, rsi
0x180233f81  lea     rax, ??$ValueSetter@P8CArithmeticComposite@@EAAJH@Z$H?SetClampOutput@1@QEAAJH@ZA@UID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CArithmeticComposite::*)(int),{CArithmeticComposite::SetClampOutput(int),0},ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x180233f88  mov     [rsp+78h+var_18], rax
0x180233f8d  lea     rax, ??$ValueGetter@P8CArithmeticComposite@@EBAHXZ$H?GetClampOutput@1@QEBAHXZA@UID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<int (CArithmeticComposite::*)(void),{CArithmeticComposite::GetClampOutput(void),0},ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x180233f94  mov     [rsp+78h+var_10], rax
0x180233f99  mov     rax, [rsi]
0x180233f9c  mov     rax, [rax+20h]
0x180233fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233fa5  mov     edi, eax
0x180233fa7  test    eax, eax
0x180233fa9  jns     short loc_180233FB2
0x180233fab  mov     ecx, eax; int
0x180233fad  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180233fb2  lea     rcx, [rsp+78h+arg_10]; void *
0x180233fba  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x180233fbf  lea     r11, [rsp+78h+var_8]
0x180233fc4  mov     eax, edi
0x180233fc6  mov     rbx, [r11+10h]
0x180233fca  mov     rsi, [r11+18h]
0x180233fce  mov     rsp, r11
0x180233fd1  pop     rdi
0x180233fd2  retn
```
