# COSKKeyboardManager::InstantiateSkbComponents(void)

- ea: `0x140012064`
- end: `0x140012199`
- name: `?InstantiateSkbComponents@COSKKeyboardManager@@AEAAJXZ`
- size: `309`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400118d0`

## callees

- `0x14000facc`
- `0x140012064`
- `0x140027010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140012093`
- `ole32!CoCreateInstance` at `0x1400120df`
- `ole32!CoCreateInstance` at `0x140012108`
- `ole32!CoCreateInstance` at `0x140012131`
- `ole32!CoCreateInstance` at `0x140012093`
- `ole32!CoCreateInstance` at `0x1400120df`
- `ole32!CoCreateInstance` at `0x140012108`
- `ole32!CoCreateInstance` at `0x140012131`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COSKKeyboardManager::InstantiateSkbComponents(COSKKeyboardManager *this)
{
  struct IUnknown **v2; // rsi
  struct IUnknown *v3; // rdx
  HRESULT Instance; // edi

  v2 = (struct IUnknown **)((char *)this + 80);
  Instance = CoCreateInstance(
               &GUID_632b0530_3cbf_44f4_bfdc_750a80d4b00a,
               0,
               0x17u,
               &GUID_e800e945_780d_48d3_89e7_d822ea18f0a2,
               (LPVOID *)this + 10);
  if ( Instance < 0
    || (Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))(*v2)->lpVtbl->QueryInterface)(
                     *v2,
                     &GUID_e787250a_f3b3_4e8d_a300_f58fb129b709,
                     (char *)this + 88),
        Instance < 0)
    || (Instance = CoCreateInstance(
                     &GUID_884cff4f_0bb0_4caa_83bd_4fb9ece938fa,
                     0,
                     0x17u,
                     &GUID_6af6b181_3a90_4fac_9655_b34041d46b8f,
                     (LPVOID *)this + 12),
        Instance < 0)
    || (Instance = CoCreateInstance(
                     &GUID_0a56cd6c_b45a_4a6c_a88c_3f42ac7bced4,
                     0,
                     0x17u,
                     &GUID_634f8410_e924_46b8_a1b5_e8b08e8b8750,
                     (LPVOID *)this + 13),
        Instance < 0)
    || (Instance = CoCreateInstance(
                     &GUID_066d2323_d35a_4c15_ae22_f88f136c1613,
                     0,
                     0x17u,
                     &GUID_f3252d7b_e51d_4b14_aa5e_8e3d4315f73c,
                     (LPVOID *)this + 14),
        Instance < 0) )
  {
    if ( *v2 )
      ATL::AtlComPtrAssign(v2, v3);
    if ( *((_QWORD *)this + 11) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 11, v3);
    if ( *((_QWORD *)this + 12) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 12, v3);
    if ( *((_QWORD *)this + 13) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 13, v3);
    if ( *((_QWORD *)this + 14) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 14, v3);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140012064  mov     [rsp+arg_0], rbx
0x140012069  mov     [rsp+arg_8], rsi
0x14001206e  push    rdi
0x14001206f  sub     rsp, 30h
0x140012073  mov     rbx, rcx
0x140012076  lea     rsi, [rcx+50h]
0x14001207a  mov     [rsp+38h+ppv], rsi; ppv
0x14001207f  lea     r9, _GUID_e800e945_780d_48d3_89e7_d822ea18f0a2; riid
0x140012086  xor     edx, edx; pUnkOuter
0x140012088  lea     r8d, [rdx+17h]; dwClsContext
0x14001208c  lea     rcx, _GUID_632b0530_3cbf_44f4_bfdc_750a80d4b00a; rclsid
0x140012093  call    cs:__imp_CoCreateInstance
0x140012099  mov     edi, eax
0x14001209b  test    eax, eax
0x14001209d  js      loc_14001213D
0x1400120a3  mov     rcx, [rsi]
0x1400120a6  mov     rax, [rcx]
0x1400120a9  lea     r8, [rbx+58h]
0x1400120ad  lea     rdx, _GUID_e787250a_f3b3_4e8d_a300_f58fb129b709
0x1400120b4  mov     rax, [rax]
0x1400120b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400120bc  mov     edi, eax
0x1400120be  test    eax, eax
0x1400120c0  js      short loc_14001213D
0x1400120c2  lea     rax, [rbx+60h]
0x1400120c6  mov     [rsp+38h+ppv], rax; ppv
0x1400120cb  lea     r9, _GUID_6af6b181_3a90_4fac_9655_b34041d46b8f; riid
0x1400120d2  xor     edx, edx; pUnkOuter
0x1400120d4  lea     r8d, [rdx+17h]; dwClsContext
0x1400120d8  lea     rcx, _GUID_884cff4f_0bb0_4caa_83bd_4fb9ece938fa; rclsid
0x1400120df  call    cs:__imp_CoCreateInstance
0x1400120e5  mov     edi, eax
0x1400120e7  test    eax, eax
0x1400120e9  js      short loc_14001213D
0x1400120eb  lea     rax, [rbx+68h]
0x1400120ef  mov     [rsp+38h+ppv], rax; ppv
0x1400120f4  lea     r9, _GUID_634f8410_e924_46b8_a1b5_e8b08e8b8750; riid
0x1400120fb  xor     edx, edx; pUnkOuter
0x1400120fd  lea     r8d, [rdx+17h]; dwClsContext
0x140012101  lea     rcx, _GUID_0a56cd6c_b45a_4a6c_a88c_3f42ac7bced4; rclsid
0x140012108  call    cs:__imp_CoCreateInstance
0x14001210e  mov     edi, eax
0x140012110  test    eax, eax
0x140012112  js      short loc_14001213D
0x140012114  lea     rax, [rbx+70h]
0x140012118  mov     [rsp+38h+ppv], rax; ppv
0x14001211d  lea     r9, _GUID_f3252d7b_e51d_4b14_aa5e_8e3d4315f73c; riid
0x140012124  xor     edx, edx; pUnkOuter
0x140012126  lea     r8d, [rdx+17h]; dwClsContext
0x14001212a  lea     rcx, _GUID_066d2323_d35a_4c15_ae22_f88f136c1613; rclsid
0x140012131  call    cs:__imp_CoCreateInstance
0x140012137  mov     edi, eax
0x140012139  test    eax, eax
0x14001213b  jns     short loc_140012187
0x14001213d  cmp     qword ptr [rsi], 0
0x140012141  jz      short loc_14001214B
0x140012143  mov     rcx, rsi; struct IUnknown **
0x140012146  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14001214b  lea     rcx, [rbx+58h]; struct IUnknown **
0x14001214f  cmp     qword ptr [rcx], 0
0x140012153  jz      short loc_14001215A
0x140012155  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14001215a  lea     rcx, [rbx+60h]; struct IUnknown **
0x14001215e  cmp     qword ptr [rcx], 0
0x140012162  jz      short loc_140012169
0x140012164  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140012169  lea     rcx, [rbx+68h]; struct IUnknown **
0x14001216d  cmp     qword ptr [rcx], 0
0x140012171  jz      short loc_140012178
0x140012173  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140012178  lea     rcx, [rbx+70h]; struct IUnknown **
0x14001217c  cmp     qword ptr [rcx], 0
0x140012180  jz      short loc_140012187
0x140012182  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140012187  mov     eax, edi
0x140012189  mov     rbx, [rsp+38h+arg_0]
0x14001218e  mov     rsi, [rsp+38h+arg_8]
0x140012193  add     rsp, 30h
0x140012197  pop     rdi
0x140012198  retn
```
