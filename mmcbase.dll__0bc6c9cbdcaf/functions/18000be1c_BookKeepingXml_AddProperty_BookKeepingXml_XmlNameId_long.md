# BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,long)

- ea: `0x18000be1c`
- end: `0x18000be7a`
- name: `?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@J@Z`
- size: `94`
- prototype: `int __high(enum BookKeepingXml::_XmlNameId, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fdcc`
- `0x180010290`

## callees

- `0x18000bf80`
- `0x18001b550`

## import_xrefs

- `msvcrt!_ltow` at `0x18000be4a`
- `msvcrt!_ltow` at `0x18000be4a`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddProperty(BookKeepingXml *a1, unsigned int a2, int a3)
{
  wchar_t Buffer[32]; // [rsp+20h] [rbp-58h] BYREF

  _ltow(a3, Buffer, 10);
  return BookKeepingXml::AddProperty(a1, a2, (__int64)Buffer);
}

```

## disassembly

```asm
0x18000be1c  mov     [rsp+arg_18], rbx
0x18000be21  push    rdi
0x18000be22  sub     rsp, 70h
0x18000be26  mov     rax, cs:__security_cookie
0x18000be2d  xor     rax, rsp
0x18000be30  mov     [rsp+78h+var_18], rax
0x18000be35  mov     eax, r8d
0x18000be38  mov     edi, edx
0x18000be3a  mov     rbx, rcx
0x18000be3d  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000be42  mov     ecx, eax; Value
0x18000be44  mov     r8d, 0Ah; Radix
0x18000be4a  call    cs:__imp__ltow
0x18000be50  lea     r8, [rsp+78h+Buffer]
0x18000be55  mov     edx, edi
0x18000be57  mov     rcx, rbx
0x18000be5a  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x18000be5f  mov     rcx, [rsp+78h+var_18]
0x18000be64  xor     rcx, rsp; StackCookie
0x18000be67  call    __security_check_cookie
0x18000be6c  mov     rbx, [rsp+78h+arg_18]
0x18000be74  add     rsp, 70h
0x18000be78  pop     rdi
0x18000be79  retn
```
