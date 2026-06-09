# CUniscribe::ApplyDigitSubstitution(uchar)

- ea: `0x18008b8b0`
- end: `0x18008b960`
- name: `?ApplyDigitSubstitution@CUniscribe@@QEAAGE@Z`
- size: `176`
- prototype: `unsigned __int16 __fastcall(CUniscribe *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180041c94`
- `0x18008b7ec`

## callees

- `0x18008b8b0`
- `0x18008b9c8`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18008b8e9`
- `KERNEL32!GetThreadLocale` at `0x18008b8e9`
- `USP10!ScriptItemize` at `0x18008b93b`
- `USP10!ScriptItemize` at `0x18008b93b`

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
0x18008b8b0  push    rbp
0x18008b8b2  push    rbx
0x18008b8b3  mov     rbp, rsp
0x18008b8b6  sub     rsp, 58h
0x18008b8ba  xor     eax, eax
0x18008b8bc  mov     rbx, rcx
0x18008b8bf  mov     [rcx+40h], ax
0x18008b8c3  test    dl, 0FDh
0x18008b8c6  jz      loc_18008B955
0x18008b8cc  mov     eax, 30h ; '0'
0x18008b8d1  mov     [rbp+arg_18], 0
0x18008b8d8  mov     [rbp+pwcInChars], ax
0x18008b8dc  xor     eax, eax
0x18008b8de  mov     word ptr [rbp+arg_8.uBidiLevel], ax
0x18008b8e2  mov     dword ptr [rbp+psControl.uDefaultLanguage], 0
0x18008b8e9  call    cs:__imp_GetThreadLocale
0x18008b8ef  mov     edx, eax; unsigned int
0x18008b8f1  call    ?GetNationalDigitLanguage@CUniscribe@@AEAAKK@Z; CUniscribe::GetNationalDigitLanguage(ulong)
0x18008b8f6  mov     ecx, 100h
0x18008b8fb  lea     r9, [rbp+psControl]; psControl
0x18008b8ff  or      word ptr [rbp+arg_8.uBidiLevel], cx
0x18008b903  mov     edx, 1; cInChars
0x18008b908  movzx   ecx, ax
0x18008b90b  mov     eax, dword ptr [rbp+psControl.uDefaultLanguage]
0x18008b90e  and     eax, 0FFFE0000h
0x18008b913  or      ecx, eax
0x18008b915  lea     r8d, [rdx+1]; cMaxItems
0x18008b919  lea     rax, [rbp+arg_18]
0x18008b91d  mov     dword ptr [rbp+psControl.uDefaultLanguage], ecx
0x18008b920  mov     [rsp+58h+pcItems], rax; pcItems
0x18008b925  lea     rcx, [rbp+pwcInChars]; pwcInChars
0x18008b929  lea     rax, [rbp+var_18]
0x18008b92d  mov     [rsp+58h+pItems], rax; pItems
0x18008b932  lea     rax, [rbp+arg_8]
0x18008b936  mov     [rsp+58h+psState], rax; psState
0x18008b93b  call    cs:__imp_ScriptItemize
0x18008b941  test    eax, eax
0x18008b943  js      short loc_18008B955
0x18008b945  movzx   eax, word ptr [rbp+var_18.a.eScript]
0x18008b949  mov     ecx, 3FFh
0x18008b94e  and     ax, cx
0x18008b951  mov     [rbx+40h], ax
0x18008b955  movzx   eax, word ptr [rbx+40h]
0x18008b959  add     rsp, 58h
0x18008b95d  pop     rbx
0x18008b95e  pop     rbp
0x18008b95f  retn
```
