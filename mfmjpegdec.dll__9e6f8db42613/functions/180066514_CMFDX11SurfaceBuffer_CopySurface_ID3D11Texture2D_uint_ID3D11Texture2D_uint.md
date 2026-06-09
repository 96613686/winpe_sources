# CMFDX11SurfaceBuffer::CopySurface(ID3D11Texture2D *,uint,ID3D11Texture2D *,uint)

- ea: `0x180066514`
- end: `0x1800665ce`
- name: `?CopySurface@CMFDX11SurfaceBuffer@@SAXPEAUID3D11Texture2D@@I0I@Z`
- size: `186`
- prototype: `void __fastcall(struct ID3D11Texture2D *, unsigned int, struct ID3D11Texture2D *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057760`
- `0x180058208`

## callees

- `0x180056930`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMFDX11SurfaceBuffer::CopySurface(
        struct ID3D11Texture2D *a1,
        int a2,
        struct ID3D11Texture2D *a3,
        unsigned int a4)
{
  __int64 v8[7]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v9; // [rsp+90h] [rbp+8h] BYREF

  v8[0] = 0;
  ((void (__fastcall *)(struct ID3D11Texture2D *, __int64 *))a1->lpVtbl->GetDevice)(a1, v8);
  v9 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8[0] + 320LL))(v8[0], &v9);
  (*(void (__fastcall **)(__int64, struct ID3D11Texture2D *, _QWORD, _QWORD, _DWORD, _DWORD, struct ID3D11Texture2D *, int, _QWORD))(*(_QWORD *)v9 + 368LL))(
    v9,
    a3,
    a4,
    0,
    0,
    0,
    a1,
    a2,
    0);
  wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(&v9);
  wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(v8);
}

```

## disassembly

```asm
0x180066514  push    rbx
0x180066516  push    rbp
0x180066517  push    rsi
0x180066518  push    rdi
0x180066519  sub     rsp, 68h
0x18006651d  mov     esi, r9d
0x180066520  mov     rbp, r8
0x180066523  mov     ebx, edx
0x180066525  mov     rdi, rcx
0x180066528  mov     [rsp+88h+var_38], 0
0x180066531  mov     rax, [rcx]
0x180066534  lea     rdx, [rsp+88h+var_38]
0x180066539  mov     rax, [rax+18h]
0x18006653d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066542  mov     [rsp+88h+arg_0], 0
0x18006654e  mov     rcx, [rsp+88h+var_38]
0x180066553  mov     rax, [rcx]
0x180066556  lea     rdx, [rsp+88h+arg_0]
0x18006655e  mov     rax, [rax+140h]
0x180066565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006656a  mov     rcx, [rsp+88h+arg_0]
0x180066572  mov     rax, [rcx]
0x180066575  mov     [rsp+88h+var_48], 0
0x18006657e  mov     [rsp+88h+var_50], ebx
0x180066582  mov     [rsp+88h+var_58], rdi
0x180066587  mov     [rsp+88h+var_60], 0
0x18006658f  mov     [rsp+88h+var_68], 0
0x180066597  xor     r9d, r9d
0x18006659a  mov     r8d, esi
0x18006659d  mov     rdx, rbp
0x1800665a0  mov     rax, [rax+170h]
0x1800665a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665ac  nop
0x1800665ad  lea     rcx, [rsp+88h+arg_0]
0x1800665b5  call    ??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)
0x1800665ba  nop
0x1800665bb  lea     rcx, [rsp+88h+var_38]
0x1800665c0  call    ??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)
0x1800665c5  add     rsp, 68h
0x1800665c9  pop     rdi
0x1800665ca  pop     rsi
0x1800665cb  pop     rbp
0x1800665cc  pop     rbx
0x1800665cd  retn
```
