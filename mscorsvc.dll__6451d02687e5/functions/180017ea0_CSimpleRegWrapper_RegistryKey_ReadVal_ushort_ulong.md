# CSimpleRegWrapper::RegistryKey::ReadVal(ushort *,ulong *)

- ea: `0x180017ea0`
- end: `0x180017f2e`
- name: `?ReadVal@RegistryKey@CSimpleRegWrapper@@UEAA_NPEAGPEAK@Z`
- size: `142`
- prototype: `bool __fastcall(CSimpleRegWrapper::RegistryKey *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001da0`
- `0x180017ea0`
- `0x180034fd4`
- `0x1800350c4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180017ecb`
- `ADVAPI32!RegQueryValueExW` at `0x180017ecb`

## string_xrefs

- `0x180017efa`: `Consistency error: registry key is of wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CSimpleRegWrapper::RegistryKey::ReadVal(HKEY *this, unsigned __int16 *a2, BYTE *a3)
{
  LSTATUS v3; // eax
  __int64 v4; // rdx
  const struct SString *v6; // rax
  unsigned int v7; // ecx
  _BYTE v8[40]; // [rsp+30h] [rbp-28h] BYREF
  DWORD v9; // [rsp+60h] [rbp+8h] BYREF
  DWORD v10; // [rsp+78h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 4;
  v3 = RegQueryValueExW(this[2], a2, 0, &v9, a3, &v10);
  if ( v3 == 2 || v3 == 161 )
    return 0;
  if ( v3 )
  {
    v7 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      v7 = v3;
    ThrowHR(v7);
  }
  if ( v9 != 4 || v10 != 4 )
  {
    v6 = (const struct SString *)SString::SString(v8, v4, L"Consistency error: registry key is of wrong type");
    ThrowHR(-2147418113, v6);
  }
  return 1;
}

```

## disassembly

```asm
0x180017ea0  mov     r11, rsp
0x180017ea3  sub     rsp, 58h
0x180017ea7  and     [rsp+58h+arg_0], 0
0x180017eac  mov     [rsp+58h+arg_18], 4
0x180017eb4  lea     rax, [r11+20h]
0x180017eb8  mov     [r11-30h], rax
0x180017ebc  mov     [r11-38h], r8
0x180017ec0  lea     r9, [r11+8]; lpType
0x180017ec4  xor     r8d, r8d; lpReserved
0x180017ec7  mov     rcx, [rcx+10h]; hKey
0x180017ecb  call    cs:__imp_RegQueryValueExW
0x180017ed1  cmp     eax, 2
0x180017ed4  jz      short loc_180017EF3
0x180017ed6  cmp     eax, 0A1h
0x180017edb  jz      short loc_180017EF3
0x180017edd  test    eax, eax
0x180017edf  jnz     short loc_180017F1A
0x180017ee1  cmp     [rsp+58h+arg_0], 4
0x180017ee6  jnz     short loc_180017EFA
0x180017ee8  cmp     [rsp+58h+arg_18], 4
0x180017eed  jnz     short loc_180017EFA
0x180017eef  mov     al, 1
0x180017ef1  jmp     short loc_180017EF5
0x180017ef3  xor     al, al
0x180017ef5  add     rsp, 58h
0x180017ef9  retn
0x180017efa  lea     r8, aConsistencyErr_1; "Consistency error: registry key is of w"...
0x180017f01  lea     rcx, [rsp+58h+var_28]
0x180017f06  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x180017f0b  nop
0x180017f0c  mov     rdx, rax; struct SString *
0x180017f0f  mov     ecx, 8000FFFFh; int
0x180017f14  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
0x180017f1a  movzx   ecx, ax
0x180017f1d  or      ecx, 80070000h
0x180017f23  test    eax, eax
0x180017f25  cmovle  ecx, eax; int
0x180017f28  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
