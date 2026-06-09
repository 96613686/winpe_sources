# __crtCompareStringA

- ea: `0x18002d5e0`
- end: `0x18002d667`
- name: `__crtCompareStringA`
- size: `135`
- prototype: `__int64 __usercall@<rax>(struct localeinfo_struct *@<rcx>, int, __int64, int, int)`
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026850`
- `0x180026fa0`
- `0x180027c70`
- `0x1800284b0`
- `0x1800293a0`
- `0x180029c10`
- `0x18005e580`
- `0x18005e690`
- `0x18005eb10`
- `0x18005edf0`

## callees

- `0x180001038`
- `0x18002d24c`
- `0x18002d5e0`

## pseudocode

```c
__int64 __fastcall _crtCompareStringA(
        struct localeinfo_struct *a1,
        LCID a2,
        DWORD a3,
        const CHAR *a4,
        int a5,
        const CHAR *a6,
        int a7,
        UINT a8)
{
  __int64 result; // rax
  _BYTE v12[16]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]
  char v14; // [rsp+58h] [rbp-10h]

  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)v12, a1);
  result = _crtCompareStringA_stat((__int64)v12, a2, a3, a4, a5, a6, a7, a8);
  if ( v14 )
    *(_DWORD *)(v13 + 200) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18002d5e0  mov     [rsp+arg_0], rbx
0x18002d5e5  mov     [rsp+arg_8], rsi
0x18002d5ea  push    rdi
0x18002d5eb  sub     rsp, 60h
0x18002d5ef  mov     esi, edx
0x18002d5f1  mov     rbx, r9
0x18002d5f4  mov     rdx, rcx; struct localeinfo_struct *
0x18002d5f7  mov     edi, r8d
0x18002d5fa  lea     rcx, [rsp+68h+var_28]; this
0x18002d5ff  call    ??0_LocaleUpdate@@QEAA@PEAUlocaleinfo_struct@@@Z; _LocaleUpdate::_LocaleUpdate(localeinfo_struct *)
0x18002d604  mov     eax, [rsp+68h+arg_38]
0x18002d60b  lea     rcx, [rsp+68h+var_28]
0x18002d610  mov     [rsp+68h+var_30], eax
0x18002d614  mov     r9, rbx
0x18002d617  mov     eax, [rsp+68h+arg_30]
0x18002d61e  mov     r8d, edi
0x18002d621  mov     [rsp+68h+var_38], eax
0x18002d625  mov     edx, esi
0x18002d627  mov     rax, [rsp+68h+arg_28]
0x18002d62f  mov     [rsp+68h+var_40], rax
0x18002d634  mov     eax, [rsp+68h+arg_20]
0x18002d63b  mov     [rsp+68h+var_48], eax
0x18002d63f  call    __crtCompareStringA_stat
0x18002d644  cmp     [rsp+68h+var_10], 0
0x18002d649  jz      short loc_18002D657
0x18002d64b  mov     rcx, [rsp+68h+var_18]
0x18002d650  and     dword ptr [rcx+0C8h], 0FFFFFFFDh
0x18002d657  mov     rbx, [rsp+68h+arg_0]
0x18002d65c  mov     rsi, [rsp+68h+arg_8]
0x18002d661  add     rsp, 60h
0x18002d665  pop     rdi
0x18002d666  retn
```
