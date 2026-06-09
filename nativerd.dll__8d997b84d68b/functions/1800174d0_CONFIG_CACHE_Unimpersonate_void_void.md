# CONFIG_CACHE::Unimpersonate(void *,void *)

- ea: `0x1800174d0`
- end: `0x18001750d`
- name: `?Unimpersonate@CONFIG_CACHE@@SAJPEAX0@Z`
- size: `61`
- prototype: `signed int __fastcall(void *, void *)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027888`
- `0x18004d674`
- `0x18004dfb8`
- `0x18004e580`
- `0x18004f07c`
- `0x18004f1a0`
- `0x18004f92c`
- `0x180050238`

## callees

- `0x1800174d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174ec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017505`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017505`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800174e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800174e2`

## pseudocode

```c
signed int __fastcall CONFIG_CACHE::Unimpersonate(void *a1, void *a2)
{
  signed int result; // eax
  BOOL v3; // eax

  if ( a2 )
  {
    v3 = SetThreadToken(0, a2);
  }
  else
  {
    if ( !a1 )
      return 0;
    v3 = RevertToSelf();
  }
  if ( v3 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800174d0  sub     rsp, 28h
0x1800174d4  test    rdx, rdx
0x1800174d7  jnz     short loc_180017503
0x1800174d9  test    rcx, rcx
0x1800174dc  jnz     short loc_1800174E2
0x1800174de  xor     eax, eax
0x1800174e0  jmp     short loc_1800174FE
0x1800174e2  call    cs:__imp_RevertToSelf
0x1800174e8  test    eax, eax
0x1800174ea  jnz     short loc_1800174DE
0x1800174ec  call    cs:__imp_GetLastError
0x1800174f2  test    eax, eax
0x1800174f4  jle     short loc_1800174FE
0x1800174f6  movzx   eax, ax
0x1800174f9  or      eax, 80070000h
0x1800174fe  add     rsp, 28h
0x180017502  retn
0x180017503  xor     ecx, ecx; Thread
0x180017505  call    cs:__imp_SetThreadToken
0x18001750b  jmp     short loc_1800174E8
```
