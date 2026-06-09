# BookKeepingXml::OpenRecord(BookKeepingXml::_XmlNameId,int,ushort const *)

- ea: `0x18000caf0`
- end: `0x18000cb8e`
- name: `?OpenRecord@BookKeepingXml@@QEAAJW4_XmlNameId@1@HPEBG@Z`
- size: `158`
- prototype: `int __high(enum BookKeepingXml::_XmlNameId, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000fc44`
- `0x18000fdcc`
- `0x180010290`

## callees

- `0x18000c2d8`
- `0x18000caf0`
- `0x18001b550`

## import_xrefs

- `msvcrt!_itow` at `0x18000cb34`
- `msvcrt!_itow` at `0x18000cb34`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::OpenRecord(BookKeepingXml *a1, unsigned int a2, int a3, unsigned __int16 *a4)
{
  __int64 result; // rax
  wchar_t Buffer[32]; // [rsp+40h] [rbp-68h] BYREF

  result = 2147549183LL;
  if ( *((_DWORD *)a1 + 2059) == 50 )
  {
    _itow(a3, Buffer, 10);
    result = BookKeepingXml::AddXml(a1, 1, a2, 0, 7u, Buffer, 8u, a4);
    if ( (int)result >= 0 )
      *((_DWORD *)a1 + 2059) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x18000caf0  push    rbx
0x18000caf2  push    rsi
0x18000caf3  push    rdi
0x18000caf4  sub     rsp, 90h
0x18000cafb  mov     rax, cs:__security_cookie
0x18000cb02  xor     rax, rsp
0x18000cb05  mov     [rsp+0A8h+var_28], rax
0x18000cb0d  cmp     dword ptr [rcx+202Ch], 32h ; '2'
0x18000cb14  mov     rsi, r9
0x18000cb17  mov     r10d, r8d
0x18000cb1a  mov     edi, edx
0x18000cb1c  mov     rbx, rcx
0x18000cb1f  mov     eax, 8000FFFFh
0x18000cb24  jnz     short loc_18000CB73
0x18000cb26  mov     r8d, 0Ah; Radix
0x18000cb2c  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x18000cb31  mov     ecx, r10d; Value
0x18000cb34  call    cs:__imp__itow
0x18000cb3a  mov     [rsp+0A8h+var_70], rsi
0x18000cb3f  lea     rax, [rsp+0A8h+Buffer]
0x18000cb44  mov     [rsp+0A8h+var_78], 8
0x18000cb4c  xor     r9d, r9d
0x18000cb4f  mov     [rsp+0A8h+var_80], rax
0x18000cb54  mov     r8d, edi
0x18000cb57  mov     dl, 1
0x18000cb59  mov     [rsp+0A8h+var_88], 7
0x18000cb61  mov     rcx, rbx
0x18000cb64  call    ?AddXml@BookKeepingXml@@AEAAJ_NW4_XmlNameId@1@PEBG1212@Z; BookKeepingXml::AddXml(bool,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *)
0x18000cb69  test    eax, eax
0x18000cb6b  js      short loc_18000CB73
0x18000cb6d  mov     [rbx+202Ch], edi
0x18000cb73  mov     rcx, [rsp+0A8h+var_28]
0x18000cb7b  xor     rcx, rsp; StackCookie
0x18000cb7e  call    __security_check_cookie
0x18000cb83  add     rsp, 90h
0x18000cb8a  pop     rdi
0x18000cb8b  pop     rsi
0x18000cb8c  pop     rbx
0x18000cb8d  retn
```
