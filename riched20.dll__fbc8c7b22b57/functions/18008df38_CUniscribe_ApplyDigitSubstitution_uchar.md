# CUniscribe::ApplyDigitSubstitution(uchar)

- ea: `0x18008df38`
- end: `0x18008dff5`
- name: `?ApplyDigitSubstitution@CUniscribe@@QEAAGE@Z`
- size: `189`
- prototype: `unsigned __int16 __fastcall(CUniscribe *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180042bf8`
- `0x18008de6c`

## callees

- `0x18008df38`
- `0x18008e05c`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18008df71`
- `KERNEL32!GetThreadLocale` at `0x18008df71`
- `USP10!ScriptItemize` at `0x18008dfc9`
- `USP10!ScriptItemize` at `0x18008dfc9`

## pseudocode

```c
__int64 __fastcall CUniscribe::ApplyDigitSubstitution(CUniscribe *this, char a2)
{
  LCID ThreadLocale; // eax
  CUniscribe *v4; // rcx
  unsigned __int16 NationalDigitLanguage; // ax
  SCRIPT_ITEM pItems; // [rsp+40h] [rbp-18h] BYREF
  WCHAR pwcInChars; // [rsp+70h] [rbp+18h] BYREF
  SCRIPT_STATE psState; // [rsp+78h] [rbp+20h] BYREF
  SCRIPT_CONTROL psControl; // [rsp+80h] [rbp+28h] BYREF
  int pcItems; // [rsp+88h] [rbp+30h] BYREF

  *((_WORD *)this + 32) = 0;
  if ( (a2 & 0xFD) != 0 )
  {
    pcItems = 0;
    pwcInChars = 48;
    psState = 0;
    psControl = 0;
    ThreadLocale = GetThreadLocale();
    NationalDigitLanguage = CUniscribe::GetNationalDigitLanguage(v4, ThreadLocale);
    psState = (SCRIPT_STATE)(*(_WORD *)&psState | 0x100);
    psControl = (SCRIPT_CONTROL)(*(_DWORD *)&psControl & 0xFFFE0000 | NationalDigitLanguage);
    if ( ScriptItemize(&pwcInChars, 1, 2, &psControl, &psState, &pItems, &pcItems) >= 0 )
      *((_WORD *)this + 32) = *(_WORD *)&pItems.a & 0x3FF;
  }
  return *((unsigned __int16 *)this + 32);
}

```

## disassembly

```asm
0x18008df38  push    rbp
0x18008df3a  push    rbx
0x18008df3b  mov     rbp, rsp
0x18008df3e  sub     rsp, 58h
0x18008df42  xor     eax, eax
0x18008df44  mov     rbx, rcx
0x18008df47  mov     [rcx+40h], ax
0x18008df4b  test    dl, 0FDh
0x18008df4e  jz      loc_18008DFE9
0x18008df54  mov     eax, 30h ; '0'
0x18008df59  mov     [rbp+arg_18], 0
0x18008df60  mov     [rbp+pwcInChars], ax
0x18008df64  xor     eax, eax
0x18008df66  mov     word ptr [rbp+arg_8.uBidiLevel], ax
0x18008df6a  mov     dword ptr [rbp+psControl.uDefaultLanguage], 0
0x18008df71  call    cs:__imp_GetThreadLocale
0x18008df78  nop     dword ptr [rax+rax+00h]
0x18008df7d  mov     edx, eax; unsigned int
0x18008df7f  call    ?GetNationalDigitLanguage@CUniscribe@@AEAAKK@Z; CUniscribe::GetNationalDigitLanguage(ulong)
0x18008df84  mov     ecx, 100h
0x18008df89  lea     r9, [rbp+psControl]; psControl
0x18008df8d  or      word ptr [rbp+arg_8.uBidiLevel], cx
0x18008df91  mov     edx, 1; cInChars
0x18008df96  movzx   ecx, ax
0x18008df99  mov     eax, dword ptr [rbp+psControl.uDefaultLanguage]
0x18008df9c  and     eax, 0FFFE0000h
0x18008dfa1  or      ecx, eax
0x18008dfa3  lea     r8d, [rdx+1]; cMaxItems
0x18008dfa7  lea     rax, [rbp+arg_18]
0x18008dfab  mov     dword ptr [rbp+psControl.uDefaultLanguage], ecx
0x18008dfae  mov     [rsp+58h+pcItems], rax; pcItems
0x18008dfb3  lea     rcx, [rbp+pwcInChars]; pwcInChars
0x18008dfb7  lea     rax, [rbp+var_18]
0x18008dfbb  mov     [rsp+58h+pItems], rax; pItems
0x18008dfc0  lea     rax, [rbp+arg_8]
0x18008dfc4  mov     [rsp+58h+psState], rax; psState
0x18008dfc9  call    cs:__imp_ScriptItemize
0x18008dfd0  nop     dword ptr [rax+rax+00h]
0x18008dfd5  test    eax, eax
0x18008dfd7  js      short loc_18008DFE9
0x18008dfd9  movzx   eax, word ptr [rbp+var_18.a.eScript]
0x18008dfdd  mov     ecx, 3FFh
0x18008dfe2  and     ax, cx
0x18008dfe5  mov     [rbx+40h], ax
0x18008dfe9  movzx   eax, word ptr [rbx+40h]
0x18008dfed  add     rsp, 58h
0x18008dff1  pop     rbx
0x18008dff2  pop     rbp
0x18008dff3  retn
```
