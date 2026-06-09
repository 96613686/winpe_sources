# BookKeepingXml::OpenTable(BookKeepingXml::_XmlNameId)

- ea: `0x18000cb94`
- end: `0x18000cbf4`
- name: `?OpenTable@BookKeepingXml@@QEAAJW4_XmlNameId@1@@Z`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f02c`
- `0x18000f18c`
- `0x18000f2fc`

## callees

- `0x18000c2d8`
- `0x18000cb94`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::OpenTable(BookKeepingXml *a1, unsigned int a2)
{
  __int64 result; // rax

  result = 2147549183LL;
  if ( *((_DWORD *)a1 + 2058) == 50 )
  {
    result = BookKeepingXml::AddXml(a1, 1, a2, 0, 0x32u, 0, 0x32u, 0);
    if ( (int)result >= 0 )
      *((_DWORD *)a1 + 2058) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x18000cb94  mov     [rsp+arg_0], rbx
0x18000cb99  push    rdi
0x18000cb9a  sub     rsp, 40h
0x18000cb9e  mov     rbx, rcx
0x18000cba1  mov     edi, edx
0x18000cba3  mov     ecx, 32h ; '2'
0x18000cba8  mov     eax, 8000FFFFh
0x18000cbad  cmp     [rbx+2028h], ecx
0x18000cbb3  jnz     short loc_18000CBE9
0x18000cbb5  mov     [rsp+48h+var_10], 0
0x18000cbbe  mov     r8d, edx
0x18000cbc1  mov     [rsp+48h+var_18], ecx
0x18000cbc5  xor     r9d, r9d
0x18000cbc8  mov     [rsp+48h+var_20], 0
0x18000cbd1  mov     dl, 1
0x18000cbd3  mov     [rsp+48h+var_28], ecx
0x18000cbd7  mov     rcx, rbx
0x18000cbda  call    ?AddXml@BookKeepingXml@@AEAAJ_NW4_XmlNameId@1@PEBG1212@Z; BookKeepingXml::AddXml(bool,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *)
0x18000cbdf  test    eax, eax
0x18000cbe1  js      short loc_18000CBE9
0x18000cbe3  mov     [rbx+2028h], edi
0x18000cbe9  mov     rbx, [rsp+48h+arg_0]
0x18000cbee  add     rsp, 40h
0x18000cbf2  pop     rdi
0x18000cbf3  retn
```
