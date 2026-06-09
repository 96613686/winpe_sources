# RTSecurityContextBase::SetDefaultProviderHelper(void)

- ea: `0x1800175f0`
- end: `0x180017625`
- name: `?SetDefaultProviderHelper@RTSecurityContextBase@@IEAAXXZ`
- size: `53`
- prototype: `void __fastcall(RTSecurityContextBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016944`
- `0x180016f9c`

## callees

- `0x1800175f0`
- `0x180023c66`

## pseudocode

```c
void __fastcall RTSecurityContextBase::SetDefaultProviderHelper(RTSecurityContextBase *this)
{
  BOOL v2; // eax

  v2 = *((_DWORD *)this + 14) == 24
    && !wcscmp_0(*((const wchar_t **)this + 3), L"Microsoft Enhanced RSA and AES Cryptographic Provider");
  *((_DWORD *)this + 15) = v2;
}

```

## disassembly

```asm
0x1800175f0  push    rbx
0x1800175f2  sub     rsp, 20h
0x1800175f6  cmp     dword ptr [rcx+38h], 18h
0x1800175fa  mov     rbx, rcx
0x1800175fd  jnz     short loc_18001761A
0x1800175ff  mov     rcx, [rcx+18h]; String1
0x180017603  lea     rdx, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18001760a  call    wcscmp_0
0x18001760f  test    eax, eax
0x180017611  jnz     short loc_18001761A
0x180017613  mov     eax, 1
0x180017618  jmp     short loc_18001761C
0x18001761a  xor     eax, eax
0x18001761c  mov     [rbx+3Ch], eax
0x18001761f  add     rsp, 20h
0x180017623  pop     rbx
0x180017624  retn
```
