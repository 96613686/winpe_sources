# Windows::Compat::Inventory::Service::PnpListener::Initialize(void)

- ea: `0x1800c1f5c`
- end: `0x1800c1ffd`
- name: `?Initialize@PnpListener@Service@Inventory@Compat@Windows@@AEAAXXZ`
- size: `161`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::PnpListener *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c0f44`
- `0x1800c2ce0`

## callees

- `0x180002c40`
- `0x1800c17e0`
- `0x1800c1f5c`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800c1ff0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800c1ff0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c1fdc`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c1fdc`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800c1f9c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800c1f9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Compat::Inventory::Service::PnpListener::Initialize(
        Windows::Compat::Inventory::Service::PnpListener *this)
{
  _QWORD *v2; // rax
  __int64 v3; // rax
  __int64 v4; // rdx
  int v5; // r8d
  __int64 v6; // rcx
  int v7; // [rsp+38h] [rbp-10h] BYREF
  int v8; // [rsp+3Ch] [rbp-Ch]

  Windows::Compat::Inventory::Service::PnpListener::GetOneSettings();
  v2 = operator new(8u);
  *v2 = this;
  v3 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_203fbad178b0da3db020893f3a03ef6b____0_,
         v2,
         0,
         &v7);
  if ( v3 )
  {
    v4 = *((_QWORD *)this + 4);
    v5 = *((_DWORD *)this + 10);
    v6 = *((unsigned int *)this + 11);
    *((_QWORD *)this + 4) = v3;
    *((_DWORD *)this + 10) = v7;
    *((_DWORD *)this + 11) = v8;
    v7 = v5;
    v8 = v6;
    if ( !v5 )
      return;
    _o_terminate(v6, v4);
  }
  v7 = 0;
  std::_Throw_Cpp_error(6);
}

```

## disassembly

```asm
0x1800c1f5c  push    rbx
0x1800c1f5e  sub     rsp, 40h
0x1800c1f62  mov     rbx, rcx
0x1800c1f65  call    ?GetOneSettings@PnpListener@Service@Inventory@Compat@Windows@@CAXXZ; Windows::Compat::Inventory::Service::PnpListener::GetOneSettings(void)
0x1800c1f6a  mov     ecx, 8; Size
0x1800c1f6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c1f74  mov     [rax], rbx
0x1800c1f77  mov     [rsp+48h+arg_0], rax
0x1800c1f7c  lea     rcx, [rsp+48h+var_10]
0x1800c1f81  mov     [rsp+48h+var_20], rcx
0x1800c1f86  mov     [rsp+48h+var_28], 0
0x1800c1f8e  mov     r9, rax
0x1800c1f91  lea     r8, std__thread___Invoke_std__tuple__lambda_203fbad178b0da3db020893f3a03ef6b____0_
0x1800c1f98  xor     edx, edx
0x1800c1f9a  xor     ecx, ecx
0x1800c1f9c  call    cs:__imp__o__beginthreadex
0x1800c1fa2  mov     [rsp+48h+var_18], rax
0x1800c1fa7  test    rax, rax
0x1800c1faa  jz      short loc_1800C1FE3
0x1800c1fac  mov     rdx, [rbx+20h]
0x1800c1fb0  mov     r8d, [rbx+28h]
0x1800c1fb4  mov     ecx, [rbx+2Ch]
0x1800c1fb7  mov     [rbx+20h], rax
0x1800c1fbb  mov     eax, [rsp+48h+var_10]
0x1800c1fbf  mov     [rbx+28h], eax
0x1800c1fc2  mov     eax, [rsp+48h+var_C]
0x1800c1fc6  mov     [rbx+2Ch], eax
0x1800c1fc9  mov     [rsp+48h+var_18], rdx
0x1800c1fce  mov     [rsp+48h+var_10], r8d
0x1800c1fd3  mov     [rsp+48h+var_C], ecx
0x1800c1fd7  test    r8d, r8d
0x1800c1fda  jz      short loc_1800C1FF7
0x1800c1fdc  call    cs:__imp__o_terminate
0x1800c1fe2  nop
0x1800c1fe3  mov     [rsp+48h+var_10], 0
0x1800c1feb  mov     ecx, 6
0x1800c1ff0  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800c1ff6  nop
0x1800c1ff7  add     rsp, 40h
0x1800c1ffb  pop     rbx
0x1800c1ffc  retn
```
