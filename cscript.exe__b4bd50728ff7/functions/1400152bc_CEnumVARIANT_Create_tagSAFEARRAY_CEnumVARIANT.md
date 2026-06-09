# CEnumVARIANT::Create(tagSAFEARRAY *,CEnumVARIANT * *)

- ea: `0x1400152bc`
- end: `0x140015361`
- name: `?Create@CEnumVARIANT@@SAJPEAUtagSAFEARRAY@@PEAPEAV1@@Z`
- size: `165`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, struct CEnumVARIANT **)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140014450`
- `0x1400144e0`
- `0x140014570`
- `0x140015280`

## callees

- `0x140009c70`
- `0x140015218`
- `0x1400152bc`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x140015311`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x140015311`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400152f9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400152f9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x14001532a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x14001532a`

## pseudocode

```c
__int64 __fastcall CEnumVARIANT::Create(SAFEARRAY *psa, struct CEnumVARIANT **a2)
{
  CEnumVARIANT *v4; // rax
  CEnumVARIANT *v5; // rax
  CEnumVARIANT *v6; // rbx
  HRESULT LBound; // edi

  v4 = (CEnumVARIANT *)operator new(0x20u);
  if ( v4 && (v5 = CEnumVARIANT::CEnumVARIANT(v4), (v6 = v5) != 0) )
  {
    LBound = SafeArrayGetLBound(psa, 1u, (LONG *)v5 + 4);
    if ( LBound < 0
      || (LBound = SafeArrayGetUBound(psa, 1u, (LONG *)v6 + 5), LBound < 0)
      || (*((_DWORD *)v6 + 3) = *((_DWORD *)v6 + 4), LBound = SafeArrayCopy(psa, (SAFEARRAY **)v6 + 3), LBound < 0) )
    {
      (*(void (__fastcall **)(CEnumVARIANT *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      *a2 = v6;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x1400152bc  push    rbx
0x1400152be  push    rsi
0x1400152bf  push    rdi
0x1400152c0  push    r14
0x1400152c2  push    r15
0x1400152c4  sub     rsp, 20h
0x1400152c8  mov     rsi, rcx
0x1400152cb  mov     r14, rdx
0x1400152ce  mov     ecx, 20h ; ' '; Size
0x1400152d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400152d8  test    rax, rax
0x1400152db  jz      short loc_14001534E
0x1400152dd  mov     rcx, rax; this
0x1400152e0  call    ??0CEnumVARIANT@@AEAA@XZ; CEnumVARIANT::CEnumVARIANT(void)
0x1400152e5  mov     rbx, rax
0x1400152e8  test    rax, rax
0x1400152eb  jz      short loc_14001534E
0x1400152ed  lea     r8, [rax+10h]; plLbound
0x1400152f1  mov     edx, 1; nDim
0x1400152f6  mov     rcx, rsi; psa
0x1400152f9  call    cs:__imp_SafeArrayGetLBound
0x1400152ff  mov     edi, eax
0x140015301  test    eax, eax
0x140015303  js      short loc_14001533D
0x140015305  lea     r8, [rbx+14h]; plUbound
0x140015309  mov     edx, 1; nDim
0x14001530e  mov     rcx, rsi; psa
0x140015311  call    cs:__imp_SafeArrayGetUBound
0x140015317  mov     edi, eax
0x140015319  test    eax, eax
0x14001531b  js      short loc_14001533D
0x14001531d  mov     eax, [rbx+10h]
0x140015320  lea     rdx, [rbx+18h]; ppsaOut
0x140015324  mov     rcx, rsi; psa
0x140015327  mov     [rbx+0Ch], eax
0x14001532a  call    cs:__imp_SafeArrayCopy
0x140015330  mov     edi, eax
0x140015332  test    eax, eax
0x140015334  js      short loc_14001533D
0x140015336  mov     [r14], rbx
0x140015339  xor     edi, edi
0x14001533b  jmp     short loc_140015353
0x14001533d  mov     rax, [rbx]
0x140015340  mov     rcx, rbx
0x140015343  mov     rax, [rax+10h]
0x140015347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001534c  jmp     short loc_140015353
0x14001534e  mov     edi, 8007000Eh
0x140015353  mov     eax, edi
0x140015355  add     rsp, 20h
0x140015359  pop     r15
0x14001535b  pop     r14
0x14001535d  pop     rdi
0x14001535e  pop     rsi
0x14001535f  pop     rbx
0x140015360  retn
```
