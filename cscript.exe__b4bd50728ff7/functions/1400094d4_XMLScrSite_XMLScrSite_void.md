# XMLScrSite::XMLScrSite(void)

- ea: `0x1400094d4`
- end: `0x14000950c`
- name: `??0XMLScrSite@@AEAA@XZ`
- size: `56`
- prototype: `XMLScrSite *__fastcall(XMLScrSite *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140009474`

## pseudocode

```c
XMLScrSite *__fastcall XMLScrSite::XMLScrSite(XMLScrSite *this)
{
  *((_DWORD *)this + 6) = 1;
  *(_QWORD *)this = &XMLScrSite::`vftable'{for `IScriptletSite'};
  *((_QWORD *)this + 1) = &XMLScrSite::`vftable'{for `IScriptletSitePoll'};
  *((_QWORD *)this + 2) = &XMLScrSite::`vftable'{for `IScriptletSiteWSH'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  return this;
}

```

## disassembly

```asm
0x1400094d4  lea     rax, ??_7XMLScrSite@@6BIScriptletSite@@@; const XMLScrSite::`vftable'{for `IScriptletSite'}
0x1400094db  mov     dword ptr [rcx+18h], 1
0x1400094e2  mov     [rcx], rax
0x1400094e5  lea     rax, ??_7XMLScrSite@@6BIScriptletSitePoll@@@; const XMLScrSite::`vftable'{for `IScriptletSitePoll'}
0x1400094ec  mov     [rcx+8], rax
0x1400094f0  lea     rax, ??_7XMLScrSite@@6BIScriptletSiteWSH@@@; const XMLScrSite::`vftable'{for `IScriptletSiteWSH'}
0x1400094f7  mov     [rcx+10h], rax
0x1400094fb  xor     eax, eax
0x1400094fd  mov     [rcx+20h], rax
0x140009501  mov     [rcx+28h], rax
0x140009505  mov     [rcx+30h], eax
0x140009508  mov     rax, rcx
0x14000950b  retn
```
