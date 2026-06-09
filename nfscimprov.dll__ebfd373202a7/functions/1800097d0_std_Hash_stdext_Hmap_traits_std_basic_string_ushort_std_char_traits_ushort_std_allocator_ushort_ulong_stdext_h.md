# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::~_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>(void)

- ea: `0x1800097d0`
- end: `0x18000980d`
- name: `??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@stdext@@@std@@QEAA@XZ`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009824`
- `0x18000c9e4`
- `0x18000f574`
- `0x18000fd5c`
- `0x18000ffbc`
- `0x180013b84`
- `0x180014168`

## callees

- `0x1800097d0`
- `0x180009830`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800097e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800097e2`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,unsigned long,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(
        _QWORD *a1)
{
  void *v2; // rcx

  v2 = (void *)a1[2];
  if ( v2 )
  {
    operator delete(v2);
    a1[2] = 0;
    a1[3] = 0;
    a1[4] = 0;
  }
  return std::list<std::pair<std::wstring const,unsigned long>>::~list<std::pair<std::wstring const,unsigned long>>(a1);
}

```

## disassembly

```asm
0x1800097d0  push    rbx
0x1800097d2  sub     rsp, 20h
0x1800097d6  mov     rbx, rcx
0x1800097d9  mov     rcx, [rcx+10h]
0x1800097dd  test    rcx, rcx
0x1800097e0  jz      short loc_180009800
0x1800097e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800097e8  mov     qword ptr [rbx+10h], 0
0x1800097f0  mov     qword ptr [rbx+18h], 0
0x1800097f8  mov     qword ptr [rbx+20h], 0
0x180009800  mov     rcx, rbx
0x180009803  add     rsp, 20h
0x180009807  pop     rbx
0x180009808  jmp     ??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,ulong>>::~list<std::pair<std::wstring const,ulong>>(void)
```
