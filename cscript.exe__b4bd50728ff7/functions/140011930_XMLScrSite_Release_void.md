# XMLScrSite::Release(void)

- ea: `0x140011930`
- end: `0x140011975`
- name: `?Release@XMLScrSite@@UEAAKXZ`
- size: `69`
- prototype: `unsigned int __fastcall(XMLScrSite *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x140011980`
- `0x140011990`

## callees

- `0x140009cb0`
- `0x140011930`

## pseudocode

```c
__int64 __fastcall XMLScrSite::Release(XMLScrSite *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &XMLScrSite::`vftable'{for `IScriptletSite'};
    *((_QWORD *)this + 1) = &XMLScrSite::`vftable'{for `IScriptletSitePoll'};
    *((_QWORD *)this + 2) = &XMLScrSite::`vftable'{for `IScriptletSiteWSH'};
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x140011930  push    rbx
0x140011932  sub     rsp, 20h
0x140011936  or      ebx, 0FFFFFFFFh
0x140011939  lock xadd [rcx+18h], ebx
0x14001193e  sub     ebx, 1
0x140011941  jnz     short loc_14001196D
0x140011943  test    rcx, rcx
0x140011946  jz      short loc_14001196D
0x140011948  lea     rax, ??_7XMLScrSite@@6BIScriptletSite@@@; const XMLScrSite::`vftable'{for `IScriptletSite'}
0x14001194f  mov     [rcx], rax
0x140011952  lea     rax, ??_7XMLScrSite@@6BIScriptletSitePoll@@@; const XMLScrSite::`vftable'{for `IScriptletSitePoll'}
0x140011959  mov     [rcx+8], rax
0x14001195d  lea     rax, ??_7XMLScrSite@@6BIScriptletSiteWSH@@@; const XMLScrSite::`vftable'{for `IScriptletSiteWSH'}
0x140011964  mov     [rcx+10h], rax
0x140011968  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001196d  mov     eax, ebx
0x14001196f  add     rsp, 20h
0x140011973  pop     rbx
0x140011974  retn
```
