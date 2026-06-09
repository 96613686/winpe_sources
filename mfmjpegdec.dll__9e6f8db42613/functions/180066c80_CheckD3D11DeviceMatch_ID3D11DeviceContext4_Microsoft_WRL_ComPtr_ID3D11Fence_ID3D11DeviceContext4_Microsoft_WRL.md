# CheckD3D11DeviceMatch<ID3D11DeviceContext4 *,Microsoft::WRL::ComPtr<ID3D11Fence>>(ID3D11DeviceContext4 * &,Microsoft::WRL::ComPtr<ID3D11Fence> &)

- ea: `0x180066c80`
- end: `0x180066d1e`
- name: `??$CheckD3D11DeviceMatch@PEAUID3D11DeviceContext4@@V?$ComPtr@UID3D11Fence@@@WRL@Microsoft@@@@YA_NAEAPEAUID3D11DeviceContext4@@AEAV?$ComPtr@UID3D11Fence@@@WRL@Microsoft@@@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006bb00`
- `0x18006c880`

## callees

- `0x18004a11c`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CheckD3D11DeviceMatch<ID3D11DeviceContext4 *,Microsoft::WRL::ComPtr<ID3D11Fence>>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, __int64 *); // rbx
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, __int64 *); // rbx
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  v8 = 0;
  v3 = *a1;
  v4 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 24LL);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v9);
  v4(v3, &v9);
  v5 = *a2;
  v6 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 24LL);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v8);
  v6(v5, &v8);
  LOBYTE(v6) = v9 == v8;
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v8);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v9);
  return (char)v6;
}

```

## disassembly

```asm
0x180066c80  mov     r11, rsp
0x180066c83  mov     [r11+18h], rbx
0x180066c87  mov     [r11+20h], rsi
0x180066c8b  push    rdi
0x180066c8c  sub     rsp, 20h
0x180066c90  mov     rsi, rdx
0x180066c93  mov     qword ptr [r11+10h], 0
0x180066c9b  mov     qword ptr [r11+8], 0
0x180066ca3  mov     rdi, [rcx]
0x180066ca6  mov     rax, [rdi]
0x180066ca9  mov     rbx, [rax+18h]
0x180066cad  lea     rcx, [r11+10h]
0x180066cb1  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180066cb6  lea     rdx, [rsp+28h+arg_8]
0x180066cbb  mov     rcx, rdi
0x180066cbe  mov     rax, rbx
0x180066cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cc6  mov     rdi, [rsi]
0x180066cc9  mov     rax, [rdi]
0x180066ccc  mov     rbx, [rax+18h]
0x180066cd0  lea     rcx, [rsp+28h+arg_0]
0x180066cd5  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180066cda  lea     rdx, [rsp+28h+arg_0]
0x180066cdf  mov     rcx, rdi
0x180066ce2  mov     rax, rbx
0x180066ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cea  mov     rax, [rsp+28h+arg_0]
0x180066cef  cmp     [rsp+28h+arg_8], rax
0x180066cf4  setz    bl
0x180066cf7  lea     rcx, [rsp+28h+arg_0]
0x180066cfc  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180066d01  nop
0x180066d02  lea     rcx, [rsp+28h+arg_8]
0x180066d07  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180066d0c  mov     al, bl
0x180066d0e  mov     rbx, [rsp+28h+arg_10]
0x180066d13  mov     rsi, [rsp+28h+arg_18]
0x180066d18  add     rsp, 20h
0x180066d1c  pop     rdi
0x180066d1d  retn
```
