# D3D11CreateDeviceForD3D12Impl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)

- ea: `0x1800aec50`
- end: `0x1800aedfa`
- name: `?D3D11CreateDeviceForD3D12Impl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IIIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z`
- size: `426`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, ULONGLONG, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180034550`
- `0x180049518`
- `0x18004a74c`
- `0x18004ac20`
- `0x1800a2e84`
- `0x1800a5d80`
- `0x1800aec50`
- `0x1801cb010`

## import_xrefs

- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1800aed5b`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1800aed5b`

## string_xrefs

- `0x1800aecc3`: `D3D11CreateDeviceForD3D12: You must specify a D3D12 device.`
- `0x1800aedbe`: `D3D11CreateDeviceForD3D12: The device provided is not a valid D3D12 device.`
- `0x1800aed29`: `D3D11CreateDeviceForD3D12: The output parameter pChosenFeatureLevel must not overlap with the input paramteter array pFeatureLevels.`
- `0x1800aed66`: `D3D11CreateDeviceForD3D12: The NodeMask parameter must only have a single bit set.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall D3D11CreateDeviceForD3D12Impl(
        struct IUnknown *a1,
        unsigned int a2,
        const enum D3D_FEATURE_LEVEL *a3,
        unsigned int a4,
        unsigned int a5,
        ULONGLONG a6,
        struct ID3D11Device **a7,
        struct ID3D11DeviceContext **a8,
        enum D3D_FEATURE_LEVEL *a9)
{
  __int64 v9; // r14
  struct ID3D11Device **v13; // rsi
  struct ID3D11DeviceContext **v14; // r15
  struct ID3D11Device **v15; // rax
  enum D3D_FEATURE_LEVEL *v16; // rbx
  unsigned int DeviceImpl; // ebx
  ULONGLONG Value; // [rsp+30h] [rbp-48h]
  __int64 v20; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-20h] BYREF

  v9 = a4;
  v13 = a7;
  if ( a7 )
    *a7 = 0;
  v20 = 0;
  v14 = a8;
  if ( a8 )
  {
    *a8 = 0;
    v15 = (struct ID3D11Device **)&v20;
    if ( v13 )
      v15 = v13;
    v13 = v15;
  }
  if ( !ValidSDKVersion(a5) )
    return 2147942487LL;
  DebugPrintF::DebugPrintF((DebugPrintF *)v21, a2);
  if ( a1 )
  {
    a7 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct ID3D11Device ***))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
           &a7) < 0
      || !a7 )
    {
      DebugPrintF::operator()(v21, 0, "D3D11CreateDeviceForD3D12: The device provided is not a valid D3D12 device.");
      goto LABEL_25;
    }
    v16 = a9;
    if ( a3 )
    {
      if ( !a9 )
      {
LABEL_19:
        if ( (_DWORD)v9 )
        {
LABEL_21:
          if ( (unsigned int)RtlNumberOfSetBitsUlongPtr((unsigned int)a6) == 1 )
          {
            LODWORD(Value) = a6;
            DeviceImpl = D3D11On12CreateDeviceImpl(a1, a2, a3, v9, 0, 0, Value, v13, v14, v16);
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&a7);
            DebugPrintF::~DebugPrintF((DebugPrintF *)v21);
            return DeviceImpl;
          }
          DebugPrintF::operator()(
            v21,
            0,
            "D3D11CreateDeviceForD3D12: The NodeMask parameter must only have a single bit set.");
          goto LABEL_25;
        }
LABEL_20:
        a3 = &qword_1801F4B70;
        LODWORD(v9) = 6;
        goto LABEL_21;
      }
      if ( a3 <= a9 && a9 < &a3[v9] )
      {
        DebugPrintF::operator()(
          v21,
          0,
          "D3D11CreateDeviceForD3D12: The output parameter pChosenFeatureLevel must not overlap with the input paramteter"
          " array pFeatureLevels.");
LABEL_25:
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&a7);
        goto LABEL_26;
      }
    }
    else if ( !a9 )
    {
      goto LABEL_20;
    }
    *a9 = 0;
    if ( !a3 )
      goto LABEL_20;
    goto LABEL_19;
  }
  DebugPrintF::operator()(v21, 0, "D3D11CreateDeviceForD3D12: You must specify a D3D12 device.");
LABEL_26:
  DebugPrintF::~DebugPrintF((DebugPrintF *)v21);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800aec50  mov     [rsp-40h+arg_8], edx
0x1800aec54  push    rbp
0x1800aec55  push    rbx
0x1800aec56  push    rsi
0x1800aec57  push    rdi
0x1800aec58  push    r12
0x1800aec5a  push    r13
0x1800aec5c  push    r14
0x1800aec5e  push    r15
0x1800aec60  mov     rbp, rsp
0x1800aec63  sub     rsp, 78h
0x1800aec67  mov     r14d, r9d
0x1800aec6a  mov     rdi, r8
0x1800aec6d  mov     ebx, edx
0x1800aec6f  mov     r12, rcx
0x1800aec72  mov     rsi, [rbp+arg_30]
0x1800aec76  xor     r13d, r13d
0x1800aec79  test    rsi, rsi
0x1800aec7c  jz      short loc_1800AEC81
0x1800aec7e  mov     [rsi], r13
0x1800aec81  mov     [rbp+var_28], r13
0x1800aec85  mov     r15, [rbp+arg_38]
0x1800aec8c  test    r15, r15
0x1800aec8f  jz      short loc_1800AECA2
0x1800aec91  mov     [r15], r13
0x1800aec94  lea     rax, [rbp+var_28]
0x1800aec98  test    rsi, rsi
0x1800aec9b  cmovnz  rax, rsi
0x1800aec9f  mov     rsi, rax
0x1800aeca2  mov     ecx, [rbp+arg_20]; unsigned int
0x1800aeca5  call    ?ValidSDKVersion@@YA_NI@Z; ValidSDKVersion(uint)
0x1800aecaa  test    al, al
0x1800aecac  jz      loc_1800AEDE4
0x1800aecb2  mov     edx, ebx; unsigned int
0x1800aecb4  lea     rcx, [rbp+var_20]; this
0x1800aecb8  call    ??0DebugPrintF@@QEAA@I@Z; DebugPrintF::DebugPrintF(uint)
0x1800aecbd  nop
0x1800aecbe  test    r12, r12
0x1800aecc1  jnz     short loc_1800AECDA
0x1800aecc3  lea     r8, aD3d11createdev_6; "D3D11CreateDeviceForD3D12: You must spe"...
0x1800aecca  xor     edx, edx
0x1800aeccc  lea     rcx, [rbp+var_20]
0x1800aecd0  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800aecd5  jmp     loc_1800AEDDB
0x1800aecda  mov     [rbp+arg_30], r13
0x1800aecde  mov     rax, [r12]
0x1800aece2  lea     r8, [rbp+arg_30]
0x1800aece6  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x1800aeced  mov     rcx, r12
0x1800aecf0  mov     rax, [rax]
0x1800aecf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aecf8  test    eax, eax
0x1800aecfa  js      loc_1800AEDBE
0x1800aed00  cmp     [rbp+arg_30], r13
0x1800aed04  jz      loc_1800AEDBE
0x1800aed0a  mov     rbx, [rbp+arg_40]
0x1800aed11  test    rdi, rdi
0x1800aed14  jz      short loc_1800AED35
0x1800aed16  test    rbx, rbx
0x1800aed19  jz      short loc_1800AED42
0x1800aed1b  cmp     rdi, rbx
0x1800aed1e  ja      short loc_1800AED3A
0x1800aed20  lea     rcx, [rdi+r14*4]
0x1800aed24  cmp     rbx, rcx
0x1800aed27  jnb     short loc_1800AED3A
0x1800aed29  lea     r8, aD3d11createdev_16; "D3D11CreateDeviceForD3D12: The output p"...
0x1800aed30  jmp     loc_1800AEDC5
0x1800aed35  test    rbx, rbx
0x1800aed38  jz      short loc_1800AED47
0x1800aed3a  mov     [rbx], r13d
0x1800aed3d  test    rdi, rdi
0x1800aed40  jz      short loc_1800AED47
0x1800aed42  test    r14d, r14d
0x1800aed45  jnz     short loc_1800AED54
0x1800aed47  lea     rdi, qword_1801F4B70
0x1800aed4e  mov     r14d, 6
0x1800aed54  mov     r13d, dword ptr [rbp+arg_28]
0x1800aed58  mov     ecx, r13d
0x1800aed5b  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x1800aed61  cmp     eax, 1
0x1800aed64  jz      short loc_1800AED6F
0x1800aed66  lea     r8, aD3d11createdev_15; "D3D11CreateDeviceForD3D12: The NodeMask"...
0x1800aed6d  jmp     short loc_1800AEDC5
0x1800aed6f  mov     [rsp+78h+var_30], rbx; enum D3D_FEATURE_LEVEL *
0x1800aed74  mov     [rsp+78h+var_38], r15; struct ID3D11DeviceContext **
0x1800aed79  mov     [rsp+78h+var_40], rsi; struct ID3D11Device **
0x1800aed7e  mov     dword ptr [rsp+78h+Value], r13d; Value
0x1800aed83  mov     [rsp+78h+var_50], 0; unsigned int
0x1800aed8b  mov     [rsp+78h+var_58], 0; struct IUnknown **
0x1800aed94  mov     r9d, r14d; unsigned int
0x1800aed97  mov     r8, rdi; enum D3D_FEATURE_LEVEL *
0x1800aed9a  mov     edx, [rbp+arg_8]; unsigned int
0x1800aed9d  mov     rcx, r12; struct IUnknown *
0x1800aeda0  call    ?D3D11On12CreateDeviceImpl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IPEBQEAU1@IIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z; D3D11On12CreateDeviceImpl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,IUnknown * const *,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)
0x1800aeda5  mov     ebx, eax
0x1800aeda7  lea     rcx, [rbp+arg_30]
0x1800aedab  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800aedb0  nop
0x1800aedb1  lea     rcx, [rbp+var_20]; this
0x1800aedb5  call    ??1DebugPrintF@@QEAA@XZ; DebugPrintF::~DebugPrintF(void)
0x1800aedba  mov     eax, ebx
0x1800aedbc  jmp     short loc_1800AEDE9
0x1800aedbe  lea     r8, aD3d11createdev_10; "D3D11CreateDeviceForD3D12: The device p"...
0x1800aedc5  xor     edx, edx
0x1800aedc7  lea     rcx, [rbp+var_20]
0x1800aedcb  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800aedd0  nop
0x1800aedd1  lea     rcx, [rbp+arg_30]
0x1800aedd5  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800aedda  nop
0x1800aeddb  lea     rcx, [rbp+var_20]; this
0x1800aeddf  call    ??1DebugPrintF@@QEAA@XZ; DebugPrintF::~DebugPrintF(void)
0x1800aede4  mov     eax, 80070057h
0x1800aede9  add     rsp, 78h
0x1800aeded  pop     r15
0x1800aedef  pop     r14
0x1800aedf1  pop     r13
0x1800aedf3  pop     r12
0x1800aedf5  pop     rdi
0x1800aedf6  pop     rsi
0x1800aedf7  pop     rbx
0x1800aedf8  pop     rbp
0x1800aedf9  retn
```
