# BookKeepingXml::CloseRecord(void)

- ea: `0x18000c60c`
- end: `0x18000c645`
- name: `?CloseRecord@BookKeepingXml@@QEAAJXZ`
- size: `57`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000fc44`
- `0x18000fdcc`
- `0x180010290`

## callees

- `0x18000c550`
- `0x18000c60c`
- `0x18000c8f4`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::CloseRecord(BookKeepingXml *this)
{
  __int64 result; // rax
  __int64 v3; // rcx
  const unsigned __int16 *v4; // rax

  result = 2147745799LL;
  v3 = *((unsigned int *)this + 2059);
  if ( (_DWORD)v3 != 50 )
  {
    v4 = (const unsigned __int16 *)BookKeepingXml::LookupName(v3);
    result = BookKeepingXml::CloseNode(this, v4);
    *((_DWORD *)this + 2059) = 50;
  }
  return result;
}

```

## disassembly

```asm
0x18000c60c  push    rbx
0x18000c60e  sub     rsp, 20h
0x18000c612  mov     rbx, rcx
0x18000c615  mov     eax, 80040007h
0x18000c61a  mov     ecx, [rcx+202Ch]
0x18000c620  cmp     ecx, 32h ; '2'
0x18000c623  jz      short loc_18000C63F
0x18000c625  call    ?LookupName@BookKeepingXml@@CAPEBGW4_XmlNameId@1@@Z; BookKeepingXml::LookupName(BookKeepingXml::_XmlNameId)
0x18000c62a  mov     rdx, rax; unsigned __int16 *
0x18000c62d  mov     rcx, rbx; this
0x18000c630  call    ?CloseNode@BookKeepingXml@@AEAAJPEBG@Z; BookKeepingXml::CloseNode(ushort const *)
0x18000c635  mov     dword ptr [rbx+202Ch], 32h ; '2'
0x18000c63f  add     rsp, 20h
0x18000c643  pop     rbx
0x18000c644  retn
```
