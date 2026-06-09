# BookKeepingXml::CloseTable(void)

- ea: `0x18000c64c`
- end: `0x18000c685`
- name: `?CloseTable@BookKeepingXml@@QEAAJXZ`
- size: `57`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f02c`
- `0x18000f18c`
- `0x18000f2fc`

## callees

- `0x18000c550`
- `0x18000c64c`
- `0x18000c8f4`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::CloseTable(BookKeepingXml *this)
{
  __int64 result; // rax
  __int64 v3; // rcx
  const unsigned __int16 *v4; // rax

  result = 2147745799LL;
  v3 = *((unsigned int *)this + 2058);
  if ( (_DWORD)v3 != 50 )
  {
    v4 = (const unsigned __int16 *)BookKeepingXml::LookupName(v3);
    result = BookKeepingXml::CloseNode(this, v4);
    *((_DWORD *)this + 2058) = 50;
  }
  return result;
}

```

## disassembly

```asm
0x18000c64c  push    rbx
0x18000c64e  sub     rsp, 20h
0x18000c652  mov     rbx, rcx
0x18000c655  mov     eax, 80040007h
0x18000c65a  mov     ecx, [rcx+2028h]
0x18000c660  cmp     ecx, 32h ; '2'
0x18000c663  jz      short loc_18000C67F
0x18000c665  call    ?LookupName@BookKeepingXml@@CAPEBGW4_XmlNameId@1@@Z; BookKeepingXml::LookupName(BookKeepingXml::_XmlNameId)
0x18000c66a  mov     rdx, rax; unsigned __int16 *
0x18000c66d  mov     rcx, rbx; this
0x18000c670  call    ?CloseNode@BookKeepingXml@@AEAAJPEBG@Z; BookKeepingXml::CloseNode(ushort const *)
0x18000c675  mov     dword ptr [rbx+2028h], 32h ; '2'
0x18000c67f  add     rsp, 20h
0x18000c683  pop     rbx
0x18000c684  retn
```
