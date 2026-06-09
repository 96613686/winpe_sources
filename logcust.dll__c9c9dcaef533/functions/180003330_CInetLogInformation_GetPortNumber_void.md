# CInetLogInformation::GetPortNumber(void)

- ea: `0x180003330`
- end: `0x18000337a`
- name: `?GetPortNumber@CInetLogInformation@@UEAAKXZ`
- size: `74`
- prototype: `unsigned int __fastcall(CInetLogInformation *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003330`
- `0x180004010`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x18000336c`
- `WS2_32!__imp_ntohs` at `0x18000336c`

## pseudocode

```c
__int64 __fastcall CInetLogInformation::GetPortNumber(CInetLogInformation *this)
{
  __int64 v1; // rax
  _WORD *v2; // rdx
  u_short v3; // cx

  v1 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8));
  v2 = *(_WORD **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1) + 112);
  if ( *v2 == 2 || (v3 = 0, *v2 == 23) )
    v3 = v2[1];
  return ntohs(v3);
}

```

## disassembly

```asm
0x180003330  sub     rsp, 28h
0x180003334  mov     rcx, [rcx+40h]
0x180003338  mov     rax, [rcx]
0x18000333b  mov     rax, [rax+18h]
0x18000333f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003344  mov     rdx, rax
0x180003347  mov     rcx, [rax]
0x18000334a  mov     rax, [rcx+8]
0x18000334e  mov     rcx, rdx
0x180003351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003356  mov     rdx, [rax+70h]
0x18000335a  cmp     word ptr [rdx], 2
0x18000335e  jz      short loc_180003368
0x180003360  xor     ecx, ecx
0x180003362  cmp     word ptr [rdx], 17h
0x180003366  jnz     short loc_18000336C
0x180003368  movzx   ecx, word ptr [rdx+2]; netshort
0x18000336c  call    cs:__imp_ntohs
0x180003372  movzx   eax, ax
0x180003375  add     rsp, 28h
0x180003379  retn
```
