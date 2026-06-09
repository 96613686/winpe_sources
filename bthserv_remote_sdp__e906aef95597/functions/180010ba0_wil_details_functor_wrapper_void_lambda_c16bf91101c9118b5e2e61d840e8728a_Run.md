# wil::details::functor_wrapper_void__lambda_c16bf91101c9118b5e2e61d840e8728a___::Run

- ea: `0x180010ba0`
- end: `0x180010c36`
- name: `wil::details::functor_wrapper_void__lambda_c16bf91101c9118b5e2e61d840e8728a___::Run`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ab64`

## callees

- `0x180010ba0`
- `0x180011b9c`
- `0x18002b060`
- `0x180039010`

## string_xrefs

- `0x180010c24`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\bthserv.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_c16bf91101c9118b5e2e61d840e8728a___::Run(__int64 a1)
{
  _DWORD **v1; // rbx
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v2; // rcx
  const char *v3; // r9
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v5; // [rsp+28h] [rbp-20h] BYREF
  char v6; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController **v8; // [rsp+50h] [rbp+8h] BYREF
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController ***v9; // [rsp+58h] [rbp+10h] BYREF

  v1 = *(_DWORD ***)(a1 + 8);
  v5 = 0;
  v8 = &v5;
  v9 = &v8;
  v6 = 1;
  **v1 = wil::ResultFromException__lambda_6a80e4881cb77c2cccaf9dde37a13450___(&v9);
  if ( v6 )
  {
    v2 = qword_1800470F8;
    qword_1800470F8 = v5;
    if ( v2 )
      (**(void (__fastcall ***)(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *, __int64))v2)(
        v2,
        1);
  }
  v3 = (const char *)(unsigned int)**v1;
  if ( (int)v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\bthserv.cpp",
      v3,
      (int)&qword_1800470F8);
  return 0;
}

```

## disassembly

```asm
0x180010ba0  mov     r11, rsp
0x180010ba3  push    rbx
0x180010ba4  sub     rsp, 40h
0x180010ba8  mov     rbx, [rcx+8]
0x180010bac  lea     rax, qword_1800470F8
0x180010bb3  and     qword ptr [r11-20h], 0
0x180010bb8  lea     rcx, [r11+10h]
0x180010bbc  mov     [r11-28h], rax
0x180010bc0  lea     rax, [r11-20h]
0x180010bc4  mov     [r11+8], rax
0x180010bc8  lea     rax, [r11+8]
0x180010bcc  mov     [r11+10h], rax
0x180010bd0  mov     [rsp+48h+var_18], 1
0x180010bd5  call    wil__ResultFromException__lambda_6a80e4881cb77c2cccaf9dde37a13450___
0x180010bda  mov     rcx, [rbx]
0x180010bdd  mov     [rcx], eax
0x180010bdf  cmp     [rsp+48h+var_18], 0
0x180010be4  jz      short loc_180010C0B
0x180010be6  mov     r8, [rsp+48h+var_28]
0x180010beb  mov     rax, [rsp+48h+var_20]
0x180010bf0  mov     rcx, [r8]
0x180010bf3  mov     [r8], rax
0x180010bf6  test    rcx, rcx
0x180010bf9  jz      short loc_180010C0B
0x180010bfb  mov     rax, [rcx]
0x180010bfe  mov     edx, 1
0x180010c03  mov     rax, [rax]
0x180010c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c0b  mov     rax, [rbx]
0x180010c0e  mov     r9d, [rax]; char *
0x180010c11  test    r9d, r9d
0x180010c14  js      short loc_180010C1F
0x180010c16  xor     eax, eax
0x180010c18  add     rsp, 40h
0x180010c1c  pop     rbx
0x180010c1d  retn
0x180010c1f  mov     rcx, [rsp+48h]; this
0x180010c24  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180010c2b  mov     edx, 0A7h; void *
0x180010c30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
