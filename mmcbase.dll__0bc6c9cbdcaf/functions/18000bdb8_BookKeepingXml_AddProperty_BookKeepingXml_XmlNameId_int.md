# BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,int)

- ea: `0x18000bdb8`
- end: `0x18000be16`
- name: `?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@H@Z`
- size: `94`
- prototype: `int __high(enum BookKeepingXml::_XmlNameId, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fc44`
- `0x180010290`

## callees

- `0x18000bf80`
- `0x18001b550`

## import_xrefs

- `msvcrt!_itow` at `0x18000bde6`
- `msvcrt!_itow` at `0x18000bde6`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddProperty(BookKeepingXml *a1, unsigned int a2, int a3)
{
  wchar_t Buffer[32]; // [rsp+20h] [rbp-58h] BYREF

  _itow(a3, Buffer, 10);
  return BookKeepingXml::AddProperty(a1, a2, (__int64)Buffer);
}

```

## disassembly

```asm
0x18000bdb8  mov     [rsp+arg_18], rbx
0x18000bdbd  push    rdi
0x18000bdbe  sub     rsp, 70h
0x18000bdc2  mov     rax, cs:__security_cookie
0x18000bdc9  xor     rax, rsp
0x18000bdcc  mov     [rsp+78h+var_18], rax
0x18000bdd1  mov     eax, r8d
0x18000bdd4  mov     edi, edx
0x18000bdd6  mov     rbx, rcx
0x18000bdd9  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000bdde  mov     ecx, eax; Value
0x18000bde0  mov     r8d, 0Ah; Radix
0x18000bde6  call    cs:__imp__itow
0x18000bdec  lea     r8, [rsp+78h+Buffer]
0x18000bdf1  mov     edx, edi
0x18000bdf3  mov     rcx, rbx
0x18000bdf6  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x18000bdfb  mov     rcx, [rsp+78h+var_18]
0x18000be00  xor     rcx, rsp; StackCookie
0x18000be03  call    __security_check_cookie
0x18000be08  mov     rbx, [rsp+78h+arg_18]
0x18000be10  add     rsp, 70h
0x18000be14  pop     rdi
0x18000be15  retn
```
