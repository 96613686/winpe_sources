# CImpIADOSecurity::isTrustedMachine(ushort const *)

- ea: `0x18002abe0`
- end: `0x18002ac2f`
- name: `?isTrustedMachine@CImpIADOSecurity@@AEAAJPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a310`
- `0x18002a4b0`

## callees

- `0x18002a920`
- `0x18002ab14`
- `0x18002abe0`

## pseudocode

```c
_BOOL8 __fastcall CImpIADOSecurity::isTrustedMachine(CImpIADOSecurity *this, const unsigned __int16 *a2)
{
  CImpIADOSecurity *v2; // rcx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]

  v5 = HIDWORD(this);
  v4 = 4;
  return (int)CImpIADOSecurity::getZone(this, a2, &v4, 0) < 0
      || v4
      || (int)CImpIADOSecurity::getPolicy(v2, 0, &v4) < 0
      || v4 != 0;
}

```

## disassembly

```asm
0x18002abe0  mov     qword ptr [rsp+arg_0], rcx
0x18002abe5  sub     rsp, 28h
0x18002abe9  xor     r9d, r9d; struct IInternetSecurityManager **
0x18002abec  mov     [rsp+28h+arg_0], 4
0x18002abf4  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18002abf9  call    ?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z; CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)
0x18002abfe  test    eax, eax
0x18002ac00  js      short loc_18002AC24
0x18002ac02  cmp     [rsp+28h+arg_0], 0
0x18002ac07  jnz     short loc_18002AC24
0x18002ac09  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18002ac0e  xor     edx, edx; unsigned int
0x18002ac10  call    ?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z; CImpIADOSecurity::getPolicy(ulong,ulong *)
0x18002ac15  test    eax, eax
0x18002ac17  js      short loc_18002AC24
0x18002ac19  xor     eax, eax
0x18002ac1b  cmp     [rsp+28h+arg_0], eax
0x18002ac1f  setnz   al
0x18002ac22  jmp     short loc_18002AC29
0x18002ac24  mov     eax, 1
0x18002ac29  add     rsp, 28h
0x18002ac2d  retn
```
