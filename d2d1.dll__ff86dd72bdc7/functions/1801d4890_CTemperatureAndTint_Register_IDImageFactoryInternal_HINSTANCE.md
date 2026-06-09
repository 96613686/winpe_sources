# CTemperatureAndTint::Register(IDImageFactoryInternal *,HINSTANCE__ *)

- ea: `0x1801d4890`
- end: `0x1801d49b3`
- name: `?Register@CTemperatureAndTint@@SAJPEAVIDImageFactoryInternal@@PEAUHINSTANCE__@@@Z`
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
- `0x1801d4890`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801d48bc`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801d48bc`

## string_xrefs

- `0x1801d48a3`: `TemperatureTint.XML`
- `0x1801d4903`: `Temperature`

## pseudocode

```c
__int64 __fastcall CTemperatureAndTint::Register(struct IDImageFactoryInternal *a1, HINSTANCE a2)
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
  Resource = FindResourceExW(a2, (LPCWSTR)0x17, L"TemperatureTint.XML", 0);
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
  v11[0] = L"Temperature";
  v11[1] = ValueSetter<long (CTemperatureAndTint::*)(float),&public: long CTemperatureAndTint::SetTemperature(float),ID2D1EffectImpl>;
  v11[2] = ValueGetter<float (CTemperatureAndTint::*)(void)const,&public: float CTemperatureAndTint::GetTemperature(void)const,ID2D1EffectImpl>;
  v11[3] = L"Tint";
  v11[4] = ValueSetter<long (CTemperatureAndTint::*)(float),&public: long CTemperatureAndTint::SetTint(float),ID2D1EffectImpl>;
  v11[5] = ValueGetter<float (CTemperatureAndTint::*)(void)const,&public: float CTemperatureAndTint::GetTint(void)const,ID2D1EffectImpl>;
  v9 = (*(__int64 (__fastcall **)(struct IDImageFactoryInternal *, GUID *, struct IStream *, _QWORD *, int, __int64 (__fastcall *)(), _DWORD))(*(_QWORD *)a1 + 32LL))(
         a1,
         &CLSID_D2D1TemperatureTint,
         v3,
         v11,
         2,
         CEffectBaseT<ID2D1EffectImpl>::Create<CTemperatureAndTint>,
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
0x1801d4890  mov     rax, rsp
0x1801d4893  mov     [rax+8], rbx
0x1801d4897  mov     [rax+10h], rsi
0x1801d489b  push    rdi
0x1801d489c  sub     rsp, 70h
0x1801d48a0  mov     rdi, rdx
0x1801d48a3  lea     r8, aTemperaturetin; "TemperatureTint.XML"
0x1801d48aa  xor     ebx, ebx
0x1801d48ac  mov     rsi, rcx
0x1801d48af  xor     r9d, r9d; wLanguage
0x1801d48b2  mov     [rax+18h], rbx
0x1801d48b6  mov     rcx, rdi; hModule
0x1801d48b9  lea     edx, [rbx+17h]; lpType
0x1801d48bc  call    cs:__imp_FindResourceExW
0x1801d48c2  test    rax, rax
0x1801d48c5  jnz     short loc_1801D48D4
0x1801d48c7  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1801d48cc  mov     edi, eax
0x1801d48ce  test    eax, eax
0x1801d48d0  jns     short loc_1801D4903
0x1801d48d2  jmp     short loc_1801D48ED
0x1801d48d4  lea     r8, [rsp+78h+arg_10]; struct IStream **
0x1801d48dc  mov     rdx, rax; hResInfo
0x1801d48df  mov     rcx, rdi; hModule
0x1801d48e2  call    ?CreateStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z; CreateStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)
0x1801d48e7  mov     edi, eax
0x1801d48e9  test    eax, eax
0x1801d48eb  jns     short loc_1801D48FB
0x1801d48ed  mov     ecx, eax; int
0x1801d48ef  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d48f4  mov     ecx, edi
0x1801d48f6  jmp     loc_1801D498D
0x1801d48fb  mov     rbx, [rsp+78h+arg_10]
0x1801d4903  lea     rax, aTemperature; "Temperature"
0x1801d490a  mov     [rsp+78h+var_48], 0
0x1801d4912  mov     [rsp+78h+var_38], rax
0x1801d4917  lea     rcx, ??$Create@VCTemperatureAndTint@@@?$CEffectBaseT@UID2D1EffectImpl@@@@SAJPEAPEAUIUnknown@@@Z; CEffectBaseT<ID2D1EffectImpl>::Create<CTemperatureAndTint>(IUnknown * *)
0x1801d491e  mov     [rsp+78h+var_50], rcx
0x1801d4923  lea     rax, ??$ValueSetter@P8CTemperatureAndTint@@EAAJM@Z$1?SetTemperature@1@QEAAJM@ZUID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CTemperatureAndTint::*)(float),&CTemperatureAndTint::SetTemperature(float),ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x1801d492a  mov     [rsp+78h+var_30], rax
0x1801d492f  lea     r9, [rsp+78h+var_38]
0x1801d4934  lea     rax, ??$ValueGetter@P8CTemperatureAndTint@@EBAMXZ$1?GetTemperature@1@QEBAMXZUID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<float (CTemperatureAndTint::*)(void),&CTemperatureAndTint::GetTemperature(void),ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x1801d493b  mov     [rsp+78h+var_58], 2
0x1801d4943  mov     [rsp+78h+var_28], rax
0x1801d4948  lea     rdx, ?CLSID_D2D1TemperatureTint@@3U_GUID@@B; _GUID const CLSID_D2D1TemperatureTint
0x1801d494f  lea     rax, aTint; "Tint"
0x1801d4956  mov     r8, rbx
0x1801d4959  mov     [rsp+78h+var_20], rax
0x1801d495e  mov     rcx, rsi
0x1801d4961  lea     rax, ??$ValueSetter@P8CTemperatureAndTint@@EAAJM@Z$1?SetTint@1@QEAAJM@ZUID2D1EffectImpl@@@@YAJPEAUIUnknown@@PEBEI@Z; ValueSetter<long (CTemperatureAndTint::*)(float),&CTemperatureAndTint::SetTint(float),ID2D1EffectImpl>(IUnknown *,uchar const *,uint)
0x1801d4968  mov     [rsp+78h+var_18], rax
0x1801d496d  lea     rax, ??$ValueGetter@P8CTemperatureAndTint@@EBAMXZ$1?GetTint@1@QEBAMXZUID2D1EffectImpl@@@@YAJPEBUIUnknown@@PEAEIPEAI@Z; ValueGetter<float (CTemperatureAndTint::*)(void),&CTemperatureAndTint::GetTint(void),ID2D1EffectImpl>(IUnknown const *,uchar *,uint,uint *)
0x1801d4974  mov     [rsp+78h+var_10], rax
0x1801d4979  mov     rax, [rsi]
0x1801d497c  mov     rax, [rax+20h]
0x1801d4980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4985  mov     edi, eax
0x1801d4987  test    eax, eax
0x1801d4989  jns     short loc_1801D4992
0x1801d498b  mov     ecx, eax; int
0x1801d498d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801d4992  lea     rcx, [rsp+78h+arg_10]; void *
0x1801d499a  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1801d499f  lea     r11, [rsp+78h+var_8]
0x1801d49a4  mov     eax, edi
0x1801d49a6  mov     rbx, [r11+10h]
0x1801d49aa  mov     rsi, [r11+18h]
0x1801d49ae  mov     rsp, r11
0x1801d49b1  pop     rdi
0x1801d49b2  retn
```
