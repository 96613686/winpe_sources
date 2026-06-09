# CCabFolder::GetPathOf(_CABITEM *,tagVARIANT *)

- ea: `0x18000e7a4`
- end: `0x18000e840`
- name: `?GetPathOf@CCabFolder@@SAJPEFAU_CABITEM@@PEAUtagVARIANT@@@Z`
- size: `156`
- prototype: `static int(struct _CABITEM *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e260`

## callees

- `0x180002620`
- `0x180002a10`
- `0x18000e7a4`
- `0x18000ecb0`

## import_xrefs

- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e7df`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e7df`

## pseudocode

```c
int __fastcall CCabFolder::GetPathOf(PERCEIVED *a1, struct tagVARIANT *a2, __int64 a3, PWSTR *a4)
{
  WCHAR pszExt[264]; // [rsp+20h] [rbp-228h] BYREF

  ualstrcpynW(pszExt, a1 + 4, (PERCEIVEDFLAG *)0x104, a4);
  if ( *((_WORD *)a1 + 7) >= 0x104u )
    return -2147467259;
  if ( 2 * (unsigned __int64)*((unsigned __int16 *)a1 + 7) >= 0x208 )
    _report_rangecheckfailure();
  pszExt[*((unsigned __int16 *)a1 + 7)] = 0;
  return InitVariantFromString(pszExt, a2);
}

```

## disassembly

```asm
0x18000e7a4  mov     [rsp+arg_10], rbx
0x18000e7a9  mov     [rsp+arg_18], rsi
0x18000e7ae  push    rdi
0x18000e7af  sub     rsp, 240h
0x18000e7b6  mov     rax, cs:__security_cookie
0x18000e7bd  xor     rax, rsp
0x18000e7c0  mov     [rsp+248h+var_18], rax
0x18000e7c8  mov     rdi, rdx
0x18000e7cb  mov     rbx, rcx
0x18000e7ce  lea     rdx, [rcx+10h]; ptype
0x18000e7d2  mov     esi, 104h
0x18000e7d7  mov     r8d, esi; pflag
0x18000e7da  lea     rcx, [rsp+248h+pszExt]; pszExt
0x18000e7df  call    cs:__imp_ualstrcpynW
0x18000e7e5  cmp     si, [rbx+0Eh]
0x18000e7e9  jbe     short loc_18000E816
0x18000e7eb  movzx   eax, word ptr [rbx+0Eh]
0x18000e7ef  add     rax, rax
0x18000e7f2  cmp     rax, 208h
0x18000e7f8  jnb     short loc_18000E810
0x18000e7fa  xor     ecx, ecx
0x18000e7fc  mov     rdx, rdi; struct tagVARIANT *
0x18000e7ff  mov     [rsp+rax+248h+pszExt], cx
0x18000e804  lea     rcx, [rsp+248h+pszExt]; unsigned __int16 *
0x18000e809  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x18000e80e  jmp     short loc_18000E81B
0x18000e810  call    __report_rangecheckfailure
0x18000e816  mov     eax, 80004005h
0x18000e81b  mov     rcx, [rsp+248h+var_18]
0x18000e823  xor     rcx, rsp; StackCookie
0x18000e826  call    __security_check_cookie
0x18000e82b  lea     r11, [rsp+248h+var_8]
0x18000e833  mov     rbx, [r11+20h]
0x18000e837  mov     rsi, [r11+28h]
0x18000e83b  mov     rsp, r11
0x18000e83e  pop     rdi
0x18000e83f  retn
```
