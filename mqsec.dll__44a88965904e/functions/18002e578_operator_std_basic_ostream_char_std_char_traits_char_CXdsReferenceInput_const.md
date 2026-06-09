# operator<<(std::basic_ostream<char,std::char_traits<char>> &,CXdsReferenceInput const &)

- ea: `0x18002e578`
- end: `0x18002e651`
- name: `??6@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@AEAV01@AEBVCXdsReferenceInput@@@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e658`

## callees

- `0x18002e3f8`
- `0x18002e578`

## string_xrefs

- `0x18002e588`: `<Reference URI="`

## pseudocode

```c
__int64 __fastcall operator<<(__int64 a1, _QWORD *a2)
{
  std::operator<<<std::char_traits<char>>(a1, "<Reference URI=\"");
  std::operator<<<std::char_traits<char>>(a1, a2[4]);
  if ( a2[6] )
  {
    std::operator<<<std::char_traits<char>>(a1, "\" Type=\"");
    std::operator<<<std::char_traits<char>>(a1, a2[6]);
  }
  std::operator<<<std::char_traits<char>>(a1, "\">");
  std::operator<<<std::char_traits<char>>(a1, "<DigestMethod Algorithm=\"");
  std::operator<<<std::char_traits<char>>(a1, a2[5]);
  std::operator<<<std::char_traits<char>>(a1, "\">");
  std::operator<<<std::char_traits<char>>(a1, "</DigestMethod>");
  std::operator<<<std::char_traits<char>>(a1, "<DigestValue>");
  std::operator<<<std::char_traits<char>>(a1, a2[3]);
  std::operator<<<std::char_traits<char>>(a1, "</DigestValue>");
  std::operator<<<std::char_traits<char>>(a1, "</Reference>");
  return a1;
}

```

## disassembly

```asm
0x18002e578  mov     [rsp+arg_0], rbx
0x18002e57d  push    rdi
0x18002e57e  sub     rsp, 20h
0x18002e582  mov     rdi, rdx
0x18002e585  mov     rbx, rcx
0x18002e588  lea     rdx, aReferenceUri; "<Reference URI=\""
0x18002e58f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e594  mov     rdx, [rdi+20h]
0x18002e598  mov     rcx, rbx
0x18002e59b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5a0  cmp     qword ptr [rdi+30h], 0
0x18002e5a5  jz      short loc_18002E5C2
0x18002e5a7  lea     rdx, aType; "\" Type=\""
0x18002e5ae  mov     rcx, rbx
0x18002e5b1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5b6  mov     rdx, [rdi+30h]
0x18002e5ba  mov     rcx, rbx
0x18002e5bd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5c2  lea     rdx, asc_1800362F4; "\">"
0x18002e5c9  mov     rcx, rbx
0x18002e5cc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5d1  lea     rdx, aDigestmethodAl; "<DigestMethod Algorithm=\""
0x18002e5d8  mov     rcx, rbx
0x18002e5db  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5e0  mov     rdx, [rdi+28h]
0x18002e5e4  mov     rcx, rbx
0x18002e5e7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5ec  lea     rdx, asc_1800362F4; "\">"
0x18002e5f3  mov     rcx, rbx
0x18002e5f6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e5fb  lea     rdx, aDigestmethod; "</DigestMethod>"
0x18002e602  mov     rcx, rbx
0x18002e605  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e60a  lea     rdx, aDigestvalue_0; "<DigestValue>"
0x18002e611  mov     rcx, rbx
0x18002e614  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e619  mov     rdx, [rdi+18h]
0x18002e61d  mov     rcx, rbx
0x18002e620  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e625  lea     rdx, aDigestvalue; "</DigestValue>"
0x18002e62c  mov     rcx, rbx
0x18002e62f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e634  lea     rdx, aReference; "</Reference>"
0x18002e63b  mov     rcx, rbx
0x18002e63e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e643  mov     rax, rbx
0x18002e646  mov     rbx, [rsp+28h+arg_0]
0x18002e64b  add     rsp, 20h
0x18002e64f  pop     rdi
0x18002e650  retn
```
