# ATL::CComSafeArray<tagVARIANT,12>::Create(tagSAFEARRAYBOUND const *,uint)

- ea: `0x18001a748`
- end: `0x18001a79d`
- name: `?Create@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJPEBUtagSAFEARRAYBOUND@@I@Z`
- size: `85`
- prototype: `HRESULT __fastcall(SAFEARRAY **, SAFEARRAYBOUND *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a56c`
- `0x18001a610`

## callees

- `0x18001a748`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001a76e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001a76e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001a78b`

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
0x18001a748  push    rbx
0x18001a74a  sub     rsp, 20h
0x18001a74e  cmp     qword ptr [rcx], 0
0x18001a752  mov     rbx, rcx
0x18001a755  jz      short loc_18001A75E
0x18001a757  mov     eax, 80004005h
0x18001a75c  jmp     short loc_18001A797
0x18001a75e  test    rdx, rdx
0x18001a761  jz      short loc_18001A792
0x18001a763  mov     ecx, 0Ch; vt
0x18001a768  mov     r8, rdx; rgsabound
0x18001a76b  lea     edx, [rcx-0Bh]; cDims
0x18001a76e  call    cs:__imp_SafeArrayCreate
0x18001a774  mov     [rbx], rax
0x18001a777  test    rax, rax
0x18001a77a  jnz     short loc_18001A783
0x18001a77c  mov     eax, 8007000Eh
0x18001a781  jmp     short loc_18001A797
0x18001a783  mov     rcx, rax
0x18001a786  add     rsp, 20h
0x18001a78a  pop     rbx
0x18001a78b  jmp     cs:__imp_SafeArrayLock
0x18001a792  mov     eax, 80070057h
0x18001a797  add     rsp, 20h
0x18001a79b  pop     rbx
0x18001a79c  retn
```
