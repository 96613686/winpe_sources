# ATL::CComSafeArray<tagVARIANT,12>::Create(tagSAFEARRAYBOUND const *,uint)

- ea: `0x18001d518`
- end: `0x18001d56d`
- name: `?Create@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJPEBUtagSAFEARRAYBOUND@@I@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c8c8`
- `0x18001cda0`

## callees

- `0x18001d518`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001d53e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001d53e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001d55b`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<tagVARIANT,12>::Create(SAFEARRAY **a1, SAFEARRAYBOUND *a2)
{
  SAFEARRAY *v4; // rax

  if ( *a1 )
    return -2147467259;
  if ( !a2 )
    return -2147024809;
  v4 = SafeArrayCreate(0xCu, 1u, a2);
  *a1 = v4;
  if ( v4 )
    return SafeArrayLock(v4);
  else
    return -2147024882;
}

```

## disassembly

```asm
0x18001d518  push    rbx
0x18001d51a  sub     rsp, 20h
0x18001d51e  cmp     qword ptr [rcx], 0
0x18001d522  mov     rbx, rcx
0x18001d525  jz      short loc_18001D52E
0x18001d527  mov     eax, 80004005h
0x18001d52c  jmp     short loc_18001D567
0x18001d52e  test    rdx, rdx
0x18001d531  jz      short loc_18001D562
0x18001d533  mov     ecx, 0Ch; vt
0x18001d538  mov     r8, rdx; rgsabound
0x18001d53b  lea     edx, [rcx-0Bh]; cDims
0x18001d53e  call    cs:__imp_SafeArrayCreate
0x18001d544  mov     [rbx], rax
0x18001d547  test    rax, rax
0x18001d54a  jnz     short loc_18001D553
0x18001d54c  mov     eax, 8007000Eh
0x18001d551  jmp     short loc_18001D567
0x18001d553  mov     rcx, rax
0x18001d556  add     rsp, 20h
0x18001d55a  pop     rbx
0x18001d55b  jmp     cs:__imp_SafeArrayLock
0x18001d562  mov     eax, 80070057h
0x18001d567  add     rsp, 20h
0x18001d56b  pop     rbx
0x18001d56c  retn
```
