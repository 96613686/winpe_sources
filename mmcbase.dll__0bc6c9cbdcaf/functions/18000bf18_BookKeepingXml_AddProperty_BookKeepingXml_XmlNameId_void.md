# BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,void *)

- ea: `0x18000bf18`
- end: `0x18000bf79`
- name: `?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEAX@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010290`

## callees

- `0x18000bf80`
- `0x18000cbfc`
- `0x18001b550`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddProperty(BookKeepingXml *a1, unsigned int a2, __int64 a3)
{
  unsigned __int16 v6[32]; // [rsp+20h] [rbp-58h] BYREF

  StringCchPrintfW(v6, 0x20u, L"%p", a3);
  return BookKeepingXml::AddProperty(a1, a2, (__int64)v6);
}

```

## disassembly

```asm
0x18000bf18  mov     [rsp+arg_18], rbx
0x18000bf1d  push    rdi
0x18000bf1e  sub     rsp, 70h
0x18000bf22  mov     rax, cs:__security_cookie
0x18000bf29  xor     rax, rsp
0x18000bf2c  mov     [rsp+78h+var_18], rax
0x18000bf31  mov     edi, edx
0x18000bf33  mov     rbx, rcx
0x18000bf36  mov     r9, r8
0x18000bf39  lea     rcx, [rsp+78h+var_58]; unsigned __int16 *
0x18000bf3e  lea     r8, aP; "%p"
0x18000bf45  mov     edx, 20h ; ' '; unsigned __int64
0x18000bf4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bf4f  lea     r8, [rsp+78h+var_58]
0x18000bf54  mov     edx, edi
0x18000bf56  mov     rcx, rbx
0x18000bf59  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x18000bf5e  mov     rcx, [rsp+78h+var_18]
0x18000bf63  xor     rcx, rsp; StackCookie
0x18000bf66  call    __security_check_cookie
0x18000bf6b  mov     rbx, [rsp+78h+arg_18]
0x18000bf73  add     rsp, 70h
0x18000bf77  pop     rdi
0x18000bf78  retn
```
