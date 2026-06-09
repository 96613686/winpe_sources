# ATL::CComSafeArray<ushort *,8>::Create(tagSAFEARRAYBOUND const *,uint)

- ea: `0x18001d4bc`
- end: `0x18001d511`
- name: `?Create@?$CComSafeArray@PEAG$07@ATL@@QEAAJPEBUtagSAFEARRAYBOUND@@I@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c868`
- `0x18001cc7c`

## callees

- `0x18001d4bc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001d4e2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001d4e2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001d4ff`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Create(SAFEARRAY **a1, SAFEARRAYBOUND *a2)
{
  SAFEARRAY *v4; // rax

  if ( *a1 )
    return -2147467259;
  if ( !a2 )
    return -2147024809;
  v4 = SafeArrayCreate(8u, 1u, a2);
  *a1 = v4;
  if ( v4 )
    return SafeArrayLock(v4);
  else
    return -2147024882;
}

```

## disassembly

```asm
0x18001d4bc  push    rbx
0x18001d4be  sub     rsp, 20h
0x18001d4c2  cmp     qword ptr [rcx], 0
0x18001d4c6  mov     rbx, rcx
0x18001d4c9  jz      short loc_18001D4D2
0x18001d4cb  mov     eax, 80004005h
0x18001d4d0  jmp     short loc_18001D50B
0x18001d4d2  test    rdx, rdx
0x18001d4d5  jz      short loc_18001D506
0x18001d4d7  mov     ecx, 8; vt
0x18001d4dc  mov     r8, rdx; rgsabound
0x18001d4df  lea     edx, [rcx-7]; cDims
0x18001d4e2  call    cs:__imp_SafeArrayCreate
0x18001d4e8  mov     [rbx], rax
0x18001d4eb  test    rax, rax
0x18001d4ee  jnz     short loc_18001D4F7
0x18001d4f0  mov     eax, 8007000Eh
0x18001d4f5  jmp     short loc_18001D50B
0x18001d4f7  mov     rcx, rax
0x18001d4fa  add     rsp, 20h
0x18001d4fe  pop     rbx
0x18001d4ff  jmp     cs:__imp_SafeArrayLock
0x18001d506  mov     eax, 80070057h
0x18001d50b  add     rsp, 20h
0x18001d50f  pop     rbx
0x18001d510  retn
```
