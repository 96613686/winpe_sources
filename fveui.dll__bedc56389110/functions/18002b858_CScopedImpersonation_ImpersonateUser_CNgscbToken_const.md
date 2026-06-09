# CScopedImpersonation::ImpersonateUser(CNgscbToken const &)

- ea: `0x18002b858`
- end: `0x18002b88d`
- name: `?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z`
- size: `53`
- prototype: `signed int __fastcall(CScopedImpersonation *this, HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002bde0`

## callees

- `0x18002b858`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b86e`
- `KERNEL32!GetLastError` at `0x18002b86e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18002b864`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18002b864`

## pseudocode

```c
signed int __fastcall CScopedImpersonation::ImpersonateUser(CScopedImpersonation *this, HANDLE *a2)
{
  signed int result; // eax

  if ( ImpersonateLoggedOnUser(*a2) )
  {
    result = 0;
    *(_BYTE *)this = 1;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002b858  push    rbx
0x18002b85a  sub     rsp, 20h
0x18002b85e  mov     rbx, rcx
0x18002b861  mov     rcx, [rdx]; hToken
0x18002b864  call    cs:__imp_ImpersonateLoggedOnUser
0x18002b86a  test    eax, eax
0x18002b86c  jnz     short loc_18002B882
0x18002b86e  call    cs:__imp_GetLastError
0x18002b874  test    eax, eax
0x18002b876  jle     short loc_18002B887
0x18002b878  movzx   eax, ax
0x18002b87b  or      eax, 80070000h
0x18002b880  jmp     short loc_18002B887
0x18002b882  xor     eax, eax
0x18002b884  mov     byte ptr [rbx], 1
0x18002b887  add     rsp, 20h
0x18002b88b  pop     rbx
0x18002b88c  retn
```
