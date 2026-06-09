# XMLScrSite::Create(CHost *,IScriptletContext *,XMLScrSite * *)

- ea: `0x140009474`
- end: `0x1400094cc`
- name: `?Create@XMLScrSite@@SAJPEAVCHost@@PEAUIScriptletContext@@PEAPEAV1@@Z`
- size: `88`
- prototype: `__int64 __fastcall(struct CHost *, struct IScriptletContext *, struct XMLScrSite **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400069d0`

## callees

- `0x140009474`
- `0x1400094d4`
- `0x140009c70`

## pseudocode

```c
__int64 __fastcall XMLScrSite::Create(struct CHost *a1, struct IScriptletContext *a2, struct XMLScrSite **a3)
{
  XMLScrSite *v6; // rax
  XMLScrSite *v7; // rax

  v6 = (XMLScrSite *)operator new(0x38u);
  if ( !v6 )
    return 2147942414LL;
  v7 = XMLScrSite::XMLScrSite(v6);
  if ( !v7 )
    return 2147942414LL;
  *((_QWORD *)v7 + 4) = a1;
  *((_QWORD *)v7 + 5) = a2;
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x140009474  mov     [rsp+arg_0], rbx
0x140009479  mov     [rsp+arg_8], rsi
0x14000947e  push    rdi
0x14000947f  sub     rsp, 20h
0x140009483  mov     rsi, rcx
0x140009486  mov     rbx, r8
0x140009489  mov     ecx, 38h ; '8'; Size
0x14000948e  mov     rdi, rdx
0x140009491  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009496  test    rax, rax
0x140009499  jz      short loc_1400094B7
0x14000949b  mov     rcx, rax; this
0x14000949e  call    ??0XMLScrSite@@AEAA@XZ; XMLScrSite::XMLScrSite(void)
0x1400094a3  test    rax, rax
0x1400094a6  jz      short loc_1400094B7
0x1400094a8  mov     [rax+20h], rsi
0x1400094ac  mov     [rax+28h], rdi
0x1400094b0  mov     [rbx], rax
0x1400094b3  xor     eax, eax
0x1400094b5  jmp     short loc_1400094BC
0x1400094b7  mov     eax, 8007000Eh
0x1400094bc  mov     rbx, [rsp+28h+arg_0]
0x1400094c1  mov     rsi, [rsp+28h+arg_8]
0x1400094c6  add     rsp, 20h
0x1400094ca  pop     rdi
0x1400094cb  retn
```
