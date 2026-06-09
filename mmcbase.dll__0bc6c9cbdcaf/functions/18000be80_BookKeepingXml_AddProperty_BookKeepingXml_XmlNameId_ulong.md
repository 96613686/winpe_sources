# BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ulong)

- ea: `0x18000be80`
- end: `0x18000bf0f`
- name: `?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@K@Z`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010290`

## callees

- `0x18000c2d8`
- `0x18000cbfc`
- `0x18001b550`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddProperty(BookKeepingXml *a1, unsigned int a2, unsigned int a3)
{
  unsigned __int16 v6[32]; // [rsp+40h] [rbp-58h] BYREF

  StringCchPrintfW(v6, 0x20u, L"%d", a3);
  return BookKeepingXml::AddXml(a1, 0, a2, (__int64)v6, 0x32u, 0, 0x32u, 0);
}

```

## disassembly

```asm
0x18000be80  mov     [rsp+arg_18], rbx
0x18000be85  push    rdi
0x18000be86  sub     rsp, 90h
0x18000be8d  mov     rax, cs:__security_cookie
0x18000be94  xor     rax, rsp
0x18000be97  mov     [rsp+98h+var_18], rax
0x18000be9f  mov     ebx, edx
0x18000bea1  mov     rdi, rcx
0x18000bea4  mov     r9d, r8d
0x18000bea7  lea     rcx, [rsp+98h+var_58]; unsigned __int16 *
0x18000beac  lea     r8, aD; "%d"
0x18000beb3  mov     edx, 20h ; ' '; unsigned __int64
0x18000beb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bebd  mov     eax, 32h ; '2'
0x18000bec2  mov     [rsp+98h+var_60], 0
0x18000becb  mov     [rsp+98h+var_68], eax
0x18000becf  lea     r9, [rsp+98h+var_58]
0x18000bed4  mov     [rsp+98h+var_70], 0
0x18000bedd  mov     r8d, ebx
0x18000bee0  xor     edx, edx
0x18000bee2  mov     [rsp+98h+var_78], eax
0x18000bee6  mov     rcx, rdi
0x18000bee9  call    ?AddXml@BookKeepingXml@@AEAAJ_NW4_XmlNameId@1@PEBG1212@Z; BookKeepingXml::AddXml(bool,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *)
0x18000beee  mov     rcx, [rsp+98h+var_18]
0x18000bef6  xor     rcx, rsp; StackCookie
0x18000bef9  call    __security_check_cookie
0x18000befe  mov     rbx, [rsp+98h+arg_18]
0x18000bf06  add     rsp, 90h
0x18000bf0d  pop     rdi
0x18000bf0e  retn
```
