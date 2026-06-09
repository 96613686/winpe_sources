# UserPresenceTimeUpdate::GetContext(void)

- ea: `0x180089050`
- end: `0x1800890e7`
- name: `?GetContext@UserPresenceTimeUpdate@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18001f17c`
- `0x18001fcac`
- `0x18002aa98`
- `0x18002ab50`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_J@Z` at `0x1800890a4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_J@Z` at `0x1800890a4`

## string_xrefs

- `0x18008906e`: `Time updated shifted time by `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserPresenceTimeUpdate::GetContext(__int64 a1, __int64 a2)
{
  _BYTE v5[16]; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v6[8]; // [rsp+40h] [rbp-F8h] BYREF
  _BYTE v7[240]; // [rsp+48h] [rbp-F0h] BYREF

  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v5);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(
    (__int64)v6,
    (__int64)L"Time updated shifted time by ");
  std::basic_ostream<unsigned short>::operator<<(v6, *(_QWORD *)(a1 + 16) / 10000000LL);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v6, (__int64)L" seconds.");
  std::basic_stringbuf<unsigned short>::str(v7, a2);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v5);
  return a2;
}

```

## disassembly

```asm
0x180089050  mov     [rsp+arg_0], rbx
0x180089055  push    rdi
0x180089056  sub     rsp, 130h
0x18008905d  mov     rdi, rdx
0x180089060  mov     rbx, rcx
0x180089063  lea     rcx, [rsp+138h+var_108]
0x180089068  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18008906d  nop
0x18008906e  lea     rdx, aTimeUpdatedShi; "Time updated shifted time by "
0x180089075  lea     rcx, [rsp+138h+var_F8]
0x18008907a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18008907f  mov     rax, 0D6BF94D5E57A42BDh
0x180089089  imul    qword ptr [rbx+10h]
0x18008908d  add     rdx, [rbx+10h]
0x180089091  sar     rdx, 17h
0x180089095  mov     rax, rdx
0x180089098  shr     rax, 3Fh
0x18008909c  add     rdx, rax
0x18008909f  lea     rcx, [rsp+138h+var_F8]
0x1800890a4  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_J@Z; std::basic_ostream<ushort>::operator<<(__int64)
0x1800890aa  lea     rdx, aSeconds; " seconds."
0x1800890b1  lea     rcx, [rsp+138h+var_F8]
0x1800890b6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800890bb  mov     rdx, rdi
0x1800890be  lea     rcx, [rsp+138h+var_F0]
0x1800890c3  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800890c8  nop
0x1800890c9  lea     rcx, [rsp+138h+var_108]
0x1800890ce  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x1800890d3  mov     rax, rdi
0x1800890d6  mov     rbx, [rsp+138h+arg_0]
0x1800890de  add     rsp, 130h
0x1800890e5  pop     rdi
0x1800890e6  retn
```
