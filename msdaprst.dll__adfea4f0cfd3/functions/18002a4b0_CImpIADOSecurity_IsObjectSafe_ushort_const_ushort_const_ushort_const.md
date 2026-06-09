# CImpIADOSecurity::IsObjectSafe(ushort const *,ushort const *,ushort const *)

- ea: `0x18002a4b0`
- end: `0x18002a53a`
- name: `?IsObjectSafe@CImpIADOSecurity@@UEAAHPEBG00@Z`
- size: `138`
- prototype: `int(CImpIADOSecurity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002a4b0`
- `0x18002abe0`
- `0x18002ac38`
- `0x180031010`

## pseudocode

```c
_BOOL8 __fastcall CImpIADOSecurity::IsObjectSafe(
        CImpIADOSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v6; // rdx

  v6 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  if ( !v6 )
    return 1;
  if ( a2 )
  {
    if ( (int)CImpIADOSecurity::securityCheck(this, a2, *((const unsigned __int16 **)this + 4)) >= 0 )
      return 1;
  }
  else if ( !(unsigned int)CImpIADOSecurity::isTrustedMachine(this, v6) )
  {
    return 1;
  }
  return a3
      && (*(unsigned int (__fastcall **)(CImpIADOSecurity *, _QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)this + 80LL))(
           this,
           *((_QWORD *)this + 5),
           *((_QWORD *)this + 4),
           a3,
           a4) == 0;
}

```

## disassembly

```asm
0x18002a4b0  mov     [rsp+arg_0], rbx
0x18002a4b5  mov     [rsp+arg_8], rsi
0x18002a4ba  push    rdi
0x18002a4bb  sub     rsp, 30h
0x18002a4bf  mov     rax, rdx
0x18002a4c2  mov     rsi, r9
0x18002a4c5  mov     rdx, [rcx+20h]; unsigned __int16 *
0x18002a4c9  mov     rdi, r8
0x18002a4cc  mov     rbx, rcx
0x18002a4cf  test    rdx, rdx
0x18002a4d2  jz      short loc_18002A4E8
0x18002a4d4  test    rax, rax
0x18002a4d7  jz      short loc_18002A4FE
0x18002a4d9  mov     r8, rdx; unsigned __int16 *
0x18002a4dc  mov     rdx, rax; unsigned __int16 *
0x18002a4df  call    ?securityCheck@CImpIADOSecurity@@AEAAJPEBG0@Z; CImpIADOSecurity::securityCheck(ushort const *,ushort const *)
0x18002a4e4  test    eax, eax
0x18002a4e6  js      short loc_18002A507
0x18002a4e8  mov     eax, 1
0x18002a4ed  mov     rbx, [rsp+38h+arg_0]
0x18002a4f2  mov     rsi, [rsp+38h+arg_8]
0x18002a4f7  add     rsp, 30h
0x18002a4fb  pop     rdi
0x18002a4fc  retn
0x18002a4fe  call    ?isTrustedMachine@CImpIADOSecurity@@AEAAJPEBG@Z; CImpIADOSecurity::isTrustedMachine(ushort const *)
0x18002a503  test    eax, eax
0x18002a505  jz      short loc_18002A4E8
0x18002a507  test    rdi, rdi
0x18002a50a  jz      short loc_18002A536
0x18002a50c  mov     rax, [rbx]
0x18002a50f  mov     r9, rdi
0x18002a512  mov     r8, [rbx+20h]
0x18002a516  mov     rcx, rbx
0x18002a519  mov     rdx, [rbx+28h]
0x18002a51d  mov     [rsp+38h+var_18], rsi
0x18002a522  mov     rax, [rax+50h]
0x18002a526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a52b  xor     ecx, ecx
0x18002a52d  test    eax, eax
0x18002a52f  setz    cl
0x18002a532  mov     eax, ecx
0x18002a534  jmp     short loc_18002A4ED
0x18002a536  xor     eax, eax
0x18002a538  jmp     short loc_18002A4ED
```
