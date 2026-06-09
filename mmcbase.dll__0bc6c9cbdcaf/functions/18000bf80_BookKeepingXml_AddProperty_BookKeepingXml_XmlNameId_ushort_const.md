# BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)

- ea: `0x18000bf80`
- end: `0x18000bfc5`
- name: `?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z`
- size: `69`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bdb8`
- `0x18000be1c`
- `0x18000bf18`
- `0x18000fc44`
- `0x18000fdcc`
- `0x180010290`

## callees

- `0x18000bf80`
- `0x18000c2d8`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddProperty(BookKeepingXml *a1, unsigned int a2, __int64 a3)
{
  __int64 result; // rax

  result = 2147549183LL;
  if ( *((_DWORD *)a1 + 2059) != 50 )
    return BookKeepingXml::AddXml(a1, 0, a2, a3, 0x32u, 0, 0x32u, 0);
  return result;
}

```

## disassembly

```asm
0x18000bf80  mov     r11, rsp
0x18000bf83  sub     rsp, 48h
0x18000bf87  mov     r9d, 32h ; '2'
0x18000bf8d  mov     eax, 8000FFFFh
0x18000bf92  cmp     [rcx+202Ch], r9d
0x18000bf99  jz      short loc_18000BFC0
0x18000bf9b  mov     qword ptr [r11-10h], 0
0x18000bfa3  mov     [r11-18h], r9d
0x18000bfa7  mov     qword ptr [r11-20h], 0
0x18000bfaf  mov     [r11-28h], r9d
0x18000bfb3  mov     r9, r8
0x18000bfb6  mov     r8d, edx
0x18000bfb9  xor     edx, edx
0x18000bfbb  call    ?AddXml@BookKeepingXml@@AEAAJ_NW4_XmlNameId@1@PEBG1212@Z; BookKeepingXml::AddXml(bool,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *)
0x18000bfc0  add     rsp, 48h
0x18000bfc4  retn
```
