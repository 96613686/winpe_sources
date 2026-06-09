# DoGetProcessId(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006580`
- end: `0x1800065b6`
- name: `?DoGetProcessId@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180006580`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800065a0`
- `KERNEL32!GetCurrentProcessId` at `0x1800065a0`

## pseudocode

```c
__int64 __fastcall DoGetProcessId(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  unsigned int v2; // ebx

  if ( a2 )
  {
    v2 = 0;
    a2->vt = 19;
    a2->lVal = GetCurrentProcessId();
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v2;
}

```

## disassembly

```asm
0x180006580  mov     [rsp+arg_0], rbx
0x180006585  push    rdi
0x180006586  sub     rsp, 20h
0x18000658a  mov     rdi, rdx
0x18000658d  test    rdx, rdx
0x180006590  jnz     short loc_180006599
0x180006592  mov     ebx, 80004003h
0x180006597  jmp     short loc_1800065A9
0x180006599  xor     ebx, ebx
0x18000659b  mov     word ptr [rdx], 13h
0x1800065a0  call    cs:__imp_GetCurrentProcessId
0x1800065a6  mov     [rdi+8], eax
0x1800065a9  mov     eax, ebx
0x1800065ab  mov     rbx, [rsp+28h+arg_0]
0x1800065b0  add     rsp, 20h
0x1800065b4  pop     rdi
0x1800065b5  retn
```
