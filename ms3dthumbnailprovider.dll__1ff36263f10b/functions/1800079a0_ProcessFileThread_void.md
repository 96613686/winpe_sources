# ProcessFileThread(void *)

- ea: `0x1800079a0`
- end: `0x180007b5a`
- name: `?ProcessFileThread@@YAKPEAX@Z`
- size: `442`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ef0`
- `0x180002954`
- `0x180005624`
- `0x1800079a0`
- `0x180008cf0`
- `0x180008e98`
- `0x18000b010`

## import_xrefs

- `ole32!CoAllowSetForegroundWindow` at `0x180007a27`
- `ole32!CoAllowSetForegroundWindow` at `0x180007a27`
- `ole32!CoCreateInstance` at `0x180007a12`
- `ole32!CoCreateInstance` at `0x180007a12`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ProcessFileThread(LPVOID lpThreadParameter)
{
  LPVOID v2; // rbx
  int v3; // eax
  IUnknown *pUnk; // [rsp+30h] [rbp-D0h] BYREF
  int v6; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v7; // [rsp+40h] [rbp-C0h]
  void **v8; // [rsp+50h] [rbp-B0h] BYREF
  int v9; // [rsp+58h] [rbp-A8h] BYREF
  char v10; // [rsp+5Ch] [rbp-A4h]
  int v11; // [rsp+80h] [rbp-80h] BYREF
  const char *v12; // [rsp+88h] [rbp-78h]
  __int64 v13; // [rsp+90h] [rbp-70h]
  char v14; // [rsp+98h] [rbp-68h]
  int v15; // [rsp+A0h] [rbp-60h]
  _BYTE v16[152]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v17; // [rsp+140h] [rbp+40h]
  int v18; // [rsp+150h] [rbp+50h]
  __int64 v19; // [rsp+158h] [rbp+58h]
  int *v20; // [rsp+160h] [rbp+60h]
  __int64 v21; // [rsp+168h] [rbp+68h]
  __int64 v22; // [rsp+170h] [rbp+70h]
  void ***v23; // [rsp+178h] [rbp+78h]
  __int64 v24; // [rsp+180h] [rbp+80h]
  int v25; // [rsp+188h] [rbp+88h]
  int *v26; // [rsp+190h] [rbp+90h]
  char v27; // [rsp+198h] [rbp+98h]

  v2 = 0;
  v7 = 0;
  if ( lpThreadParameter )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpThreadParameter + 8LL))(lpThreadParameter);
    v2 = lpThreadParameter;
    v7 = lpThreadParameter;
  }
  v6 = 0;
  pUnk = 0;
  if ( CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 4u, &IID_IApplicationActivationManager, (LPVOID *)&pUnk) >= 0
    && CoAllowSetForegroundWindow(pUnk, 0) >= 0 )
  {
    v9 = 0;
    v10 = 0;
    v14 = 0;
    v11 = 0;
    v12 = "RightClickToPrint";
    v13 = 0;
    v15 = 0;
    v17 = 0;
    memset_0(v16, 0, sizeof(v16));
    v18 = 1;
    v19 = 0;
    v20 = &v9;
    v21 = 0;
    v22 = 0;
    v23 = &v8;
    v24 = 0;
    v25 = 0;
    v26 = &v11;
    v27 = 0;
    v8 = &ShellExtensionTelemetry::RightClickToPrint::`vftable';
    ShellExtensionTelemetry::RightClickToPrint::StartActivity((ShellExtensionTelemetry::RightClickToPrint *)&v8);
    v3 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, LPVOID, const wchar_t *, int *))pUnk->lpVtbl[1].AddRef)(
           pUnk,
           L"Microsoft.3DBuilder_8wekyb3d8bbwe!App",
           v2,
           L"open",
           &v6);
    wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      (__int64)&v8,
      v3);
    ShellExtensionTelemetry::RightClickToPrint::~RightClickToPrint((ShellExtensionTelemetry::RightClickToPrint *)&v8);
  }
  if ( pUnk )
    ((void (__fastcall *)(IUnknown *))pUnk->lpVtbl->Release)(pUnk);
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x1800079a0  push    rbp
0x1800079a2  push    rbx
0x1800079a3  push    rsi
0x1800079a4  push    rdi
0x1800079a5  lea     rbp, [rsp-0B8h]
0x1800079ad  sub     rsp, 1B8h
0x1800079b4  mov     rax, cs:__security_cookie
0x1800079bb  xor     rax, rsp
0x1800079be  mov     [rbp+0D0h+var_30], rax
0x1800079c5  mov     rdi, rcx
0x1800079c8  xor     esi, esi
0x1800079ca  mov     ebx, esi
0x1800079cc  mov     [rsp+1D0h+var_190], rbx
0x1800079d1  test    rcx, rcx
0x1800079d4  jz      short loc_1800079EB
0x1800079d6  mov     rax, [rcx]
0x1800079d9  mov     rax, [rax+8]
0x1800079dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e2  nop
0x1800079e3  mov     rbx, rdi
0x1800079e6  mov     [rsp+1D0h+var_190], rbx
0x1800079eb  mov     [rsp+1D0h+var_198], esi
0x1800079ef  mov     [rsp+1D0h+pUnk], rsi
0x1800079f4  lea     rax, [rsp+1D0h+pUnk]
0x1800079f9  mov     [rsp+1D0h+ppv], rax; ppv
0x1800079fe  lea     r9, IID_IApplicationActivationManager; riid
0x180007a05  xor     edx, edx; pUnkOuter
0x180007a07  lea     r8d, [rdx+4]; dwClsContext
0x180007a0b  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x180007a12  call    cs:__imp_CoCreateInstance
0x180007a18  test    eax, eax
0x180007a1a  js      loc_180007B11
0x180007a20  xor     edx, edx; lpvReserved
0x180007a22  mov     rcx, [rsp+1D0h+pUnk]; pUnk
0x180007a27  call    cs:__imp_CoAllowSetForegroundWindow
0x180007a2d  test    eax, eax
0x180007a2f  js      loc_180007B11
0x180007a35  mov     [rsp+1D0h+var_178], esi
0x180007a39  mov     [rsp+1D0h+var_174], sil
0x180007a3e  mov     [rbp+0D0h+var_138], sil
0x180007a42  mov     [rbp+0D0h+var_150], esi
0x180007a45  lea     rax, aRightclicktopr; "RightClickToPrint"
0x180007a4c  mov     [rbp+0D0h+var_148], rax
0x180007a50  mov     [rbp+0D0h+var_140], rsi
0x180007a54  mov     [rbp+0D0h+var_130], esi
0x180007a57  xorps   xmm0, xmm0
0x180007a5a  movdqa  [rbp+0D0h+var_90], xmm0
0x180007a5f  xor     edx, edx; Val
0x180007a61  mov     r8d, 98h; Size
0x180007a67  lea     rcx, [rbp+0D0h+var_128]; void *
0x180007a6b  call    memset_0
0x180007a70  mov     [rbp+0D0h+var_80], 1
0x180007a77  xor     eax, eax
0x180007a79  mov     [rbp+0D0h+var_78], rax
0x180007a7d  lea     rax, [rsp+1D0h+var_178]
0x180007a82  mov     [rbp+0D0h+var_70], rax
0x180007a86  mov     [rbp+0D0h+var_68], rsi
0x180007a8a  mov     [rbp+0D0h+var_60], rsi
0x180007a8e  lea     rax, [rsp+1D0h+var_180]
0x180007a93  mov     [rbp+0D0h+var_58], rax
0x180007a97  mov     [rbp+0D0h+var_50], rsi
0x180007a9e  mov     [rbp+0D0h+var_48], esi
0x180007aa4  lea     rax, [rbp+0D0h+var_150]
0x180007aa8  mov     [rbp+0D0h+var_40], rax
0x180007aaf  mov     [rbp+0D0h+var_38], sil
0x180007ab6  lea     rax, ??_7RightClickToPrint@ShellExtensionTelemetry@@6B@; const ShellExtensionTelemetry::RightClickToPrint::`vftable'
0x180007abd  mov     [rsp+1D0h+var_180], rax
0x180007ac2  lea     rcx, [rsp+1D0h+var_180]; this
0x180007ac7  call    ?StartActivity@RightClickToPrint@ShellExtensionTelemetry@@QEAAXXZ; ShellExtensionTelemetry::RightClickToPrint::StartActivity(void)
0x180007acc  nop
0x180007acd  mov     rcx, [rsp+1D0h+pUnk]
0x180007ad2  mov     rax, [rcx]
0x180007ad5  lea     rdx, [rsp+1D0h+var_198]
0x180007ada  mov     [rsp+1D0h+ppv], rdx
0x180007adf  lea     r9, aOpen; "open"
0x180007ae6  mov     r8, rbx
0x180007ae9  lea     rdx, aMicrosoft3dbui; "Microsoft.3DBuilder_8wekyb3d8bbwe!App"
0x180007af0  mov     rax, [rax+20h]
0x180007af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af9  mov     edx, eax
0x180007afb  lea     rcx, [rsp+1D0h+var_180]
0x180007b00  call    ?Stop@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180007b05  nop
0x180007b06  lea     rcx, [rsp+1D0h+var_180]; this
0x180007b0b  call    ??1RightClickToPrint@ShellExtensionTelemetry@@QEAA@XZ; ShellExtensionTelemetry::RightClickToPrint::~RightClickToPrint(void)
0x180007b10  nop
0x180007b11  mov     rcx, [rsp+1D0h+pUnk]
0x180007b16  test    rcx, rcx
0x180007b19  jz      short loc_180007B28
0x180007b1b  mov     rax, [rcx]
0x180007b1e  mov     rax, [rax+10h]
0x180007b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b27  nop
0x180007b28  test    rbx, rbx
0x180007b2b  jz      short loc_180007B3D
0x180007b2d  mov     rax, [rbx]
0x180007b30  mov     rcx, rbx
0x180007b33  mov     rax, [rax+10h]
0x180007b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3c  nop
0x180007b3d  xor     eax, eax
0x180007b3f  mov     rcx, [rbp+0D0h+var_30]
0x180007b46  xor     rcx, rsp; StackCookie
0x180007b49  call    __security_check_cookie
0x180007b4e  add     rsp, 1B8h
0x180007b55  pop     rdi
0x180007b56  pop     rsi
0x180007b57  pop     rbx
0x180007b58  pop     rbp
0x180007b59  retn
```
