# CMFDX11SurfaceBuffer::CreateStagingSurface(ID3D11Texture2D *,uint,ID3D11Texture2D * *)

- ea: `0x1800665d4`
- end: `0x1800666e9`
- name: `?CreateStagingSurface@CMFDX11SurfaceBuffer@@SAJPEAUID3D11Texture2D@@IPEAPEAU2@@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct ID3D11Texture2D *, unsigned int, struct ID3D11Texture2D **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057760`

## callees

- `0x180024220`
- `0x180056930`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMFDX11SurfaceBuffer::CreateStagingSurface(
        struct ID3D11Texture2D *a1,
        __int64 a2,
        struct ID3D11Texture2D **a3)
{
  struct ID3D11Texture2D *v4; // rbx
  __int64 v6; // [rsp+30h] [rbp-29h] BYREF
  __int64 v7; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v8[3]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v9[3]; // [rsp+70h] [rbp+17h] BYREF

  v4 = a1;
  memset(v9, 0, 44);
  memset(v8, 0, 44);
  ((void (__fastcall *)(struct ID3D11Texture2D *, _OWORD *))a1->lpVtbl->GetDesc)(a1, v9);
  *(_QWORD *)&v8[0] = *(_QWORD *)&v9[0];
  *(_QWORD *)&v8[1] = LODWORD(v9[1]) | 0x100000000LL;
  *((_QWORD *)&v8[0] + 1) = 0x100000001LL;
  HIDWORD(v8[1]) = 3;
  DWORD1(v8[2]) = 196608;
  v6 = 0;
  ((void (__fastcall *)(struct ID3D11Texture2D *, __int64 *))v4->lpVtbl->GetDevice)(v4, &v6);
  v7 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 320LL))(v6, &v7);
  LODWORD(v4) = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, struct ID3D11Texture2D **))(*(_QWORD *)v6 + 40LL))(
                  v6,
                  v8,
                  0,
                  a3);
  wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(&v7);
  wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800665d4  mov     [rsp-8+arg_8], rbx
0x1800665d9  mov     [rsp-8+arg_18], rdi
0x1800665de  push    rbp
0x1800665df  lea     rbp, [rsp-57h]
0x1800665e4  sub     rsp, 0B0h
0x1800665eb  mov     rax, cs:__security_cookie
0x1800665f2  xor     rax, rsp
0x1800665f5  mov     [rbp+57h+var_10], rax
0x1800665f9  mov     rdi, r8
0x1800665fc  mov     rbx, rcx
0x1800665ff  xorps   xmm0, xmm0
0x180066602  xor     eax, eax
0x180066604  movups  [rbp+57h+var_40], xmm0
0x180066608  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18006660c  movups  xmmword ptr [rbp+57h+var_30+0Ch], xmm0
0x180066610  xorps   xmm1, xmm1
0x180066613  movups  [rbp+57h+var_70], xmm1
0x180066617  movups  [rbp+57h+var_60], xmm1
0x18006661b  movups  [rbp+57h+var_60+0Ch], xmm1
0x18006661f  mov     rax, [rcx]
0x180066622  lea     rdx, [rbp+57h+var_40]
0x180066626  mov     rax, [rax+50h]
0x18006662a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006662f  mov     eax, dword ptr [rbp+57h+var_40]
0x180066632  mov     dword ptr [rbp+57h+var_70], eax
0x180066635  mov     eax, dword ptr [rbp+57h+var_40+4]
0x180066638  mov     dword ptr [rbp+57h+var_70+4], eax
0x18006663b  mov     eax, dword ptr [rbp+57h+var_30]
0x18006663e  mov     dword ptr [rbp+57h+var_60], eax
0x180066641  mov     eax, 1
0x180066646  mov     dword ptr [rbp+57h+var_70+8], eax
0x180066649  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18006664c  mov     dword ptr [rbp+57h+var_60+4], eax
0x18006664f  mov     dword ptr [rbp+57h+var_60+0Ch], 3
0x180066656  mov     [rbp+57h+var_4C], 30000h
0x18006665d  mov     [rbp+57h+var_80], 0
0x180066665  mov     rax, [rbx]
0x180066668  lea     rdx, [rbp+57h+var_80]
0x18006666c  mov     rcx, rbx
0x18006666f  mov     rax, [rax+18h]
0x180066673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066678  mov     [rbp+57h+var_78], 0
0x180066680  mov     rcx, [rbp+57h+var_80]
0x180066684  mov     rax, [rcx]
0x180066687  lea     rdx, [rbp+57h+var_78]
0x18006668b  mov     rax, [rax+140h]
0x180066692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066697  mov     rcx, [rbp+57h+var_80]
0x18006669b  mov     rax, [rcx]
0x18006669e  mov     r9, rdi
0x1800666a1  xor     r8d, r8d
0x1800666a4  lea     rdx, [rbp+57h+var_70]
0x1800666a8  mov     rax, [rax+28h]
0x1800666ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666b1  mov     ebx, eax
0x1800666b3  lea     rcx, [rbp+57h+var_78]
0x1800666b7  call    ??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)
0x1800666bc  nop
0x1800666bd  lea     rcx, [rbp+57h+var_80]
0x1800666c1  call    ??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)
0x1800666c6  mov     eax, ebx
0x1800666c8  mov     rcx, [rbp+57h+var_10]
0x1800666cc  xor     rcx, rsp; StackCookie
0x1800666cf  call    __security_check_cookie
0x1800666d4  lea     r11, [rsp+0B0h+var_s0]
0x1800666dc  mov     rbx, [r11+18h]
0x1800666e0  mov     rdi, [r11+28h]
0x1800666e4  mov     rsp, r11
0x1800666e7  pop     rbp
0x1800666e8  retn
```
