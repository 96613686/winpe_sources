# operator<<(std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>> &,CXdsSignature const &)

- ea: `0x18002e730`
- end: `0x18002e91d`
- name: `??6@YAAEAV?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator_static@D@2@@std@@AEAV01@AEBVCXdsSignature@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180019b94`

## callees

- `0x18000ead8`
- `0x18001ab98`
- `0x18002e3f8`
- `0x18002e658`
- `0x18002e730`
- `0x18002e9ec`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!free` at `0x18002e872`
- `msvcrt!free` at `0x18002e872`

## string_xrefs

- `0x18002e758`: `<Signature xmlns="http://www.w3.org/2000/02/xmldsig#`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall operator<<(__int64 a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdx
  BYTE *v9; // rcx
  __int64 v10; // rdx
  char *v12; // [rsp+30h] [rbp-78h]
  _BYTE v13[8]; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v14[4]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v15[40]; // [rsp+60h] [rbp-48h] BYREF

  std::operator<<<std::char_traits<char>>(a1, "<Signature xmlns=\"http://www.w3.org/2000/02/xmldsig#");
  std::operator<<<std::char_traits<char>>(a1, "\"");
  if ( *(_QWORD *)a2 )
  {
    std::operator<<<std::char_traits<char>>(a1, " Id=\"");
    std::operator<<<std::char_traits<char>>(a1, *(_QWORD *)a2);
    std::operator<<<std::char_traits<char>>(a1, "\"");
  }
  std::operator<<<std::char_traits<char>>(a1, ">");
  v4 = *(_QWORD *)(std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>>::str(a1, v15) + 24);
  LOBYTE(v5) = 1;
  std::string::_Tidy(v15, v5, 0);
  operator<<(a1, a2 + 8);
  v6 = *(_QWORD *)(std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>>::str(a1, v13) + 24);
  LOBYTE(v7) = 1;
  std::string::_Tidy(v13, v7, 0);
  std::operator<<<std::char_traits<char>>(a1, "<SignatureValue>");
  v8 = *(_QWORD *)(a2 + 64);
  if ( v8 )
  {
    std::operator<<<std::char_traits<char>>(a1, v8);
  }
  else
  {
    std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>>::str(a1, v13);
    v9 = (BYTE *)v14;
    if ( v14[3] >= 0x10u )
      v9 = (BYTE *)v14[0];
    v12 = XdsCalcSignature(&v9[v4], (int)v6 - (int)v4, *(_DWORD *)(a2 + 16), *(_DWORD *)(a2 + 80), *(_QWORD *)(a2 + 88));
    std::operator<<<std::char_traits<char>>(a1, v12);
    free(v12);
    LOBYTE(v10) = 1;
    std::string::_Tidy(v13, v10, 0);
  }
  std::operator<<<std::char_traits<char>>(a1, "</SignatureValue>");
  if ( *(_QWORD *)(a2 + 72) )
  {
    std::operator<<<std::char_traits<char>>(a1, "<KeyInfo>");
    std::operator<<<std::char_traits<char>>(a1, "<KeyValue>");
    std::operator<<<std::char_traits<char>>(a1, *(_QWORD *)(a2 + 72));
    std::operator<<<std::char_traits<char>>(a1, "</KeyValue>");
    std::operator<<<std::char_traits<char>>(a1, "</KeyInfo>");
  }
  std::operator<<<std::char_traits<char>>(a1, "</Signature>");
  return a1;
}

```

## disassembly

```asm
0x18002e730  mov     [rsp+arg_10], rbx
0x18002e735  push    rsi
0x18002e736  push    rdi
0x18002e737  push    r14
0x18002e739  sub     rsp, 90h
0x18002e740  mov     rax, cs:__security_cookie
0x18002e747  xor     rax, rsp
0x18002e74a  mov     [rsp+0A8h+var_20], rax
0x18002e752  mov     rsi, rdx
0x18002e755  mov     rdi, rcx
0x18002e758  lea     rdx, aSignatureXmlns; "<Signature xmlns=\"http://www.w3.org/20"...
0x18002e75f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e764  lea     rdx, asc_180036394; "\""
0x18002e76b  mov     rcx, rdi
0x18002e76e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e773  cmp     qword ptr [rsi], 0
0x18002e777  jz      short loc_18002E7A2
0x18002e779  lea     rdx, aId; " Id=\""
0x18002e780  mov     rcx, rdi
0x18002e783  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e788  mov     rdx, [rsi]
0x18002e78b  mov     rcx, rdi
0x18002e78e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e793  lea     rdx, asc_180036394; "\""
0x18002e79a  mov     rcx, rdi
0x18002e79d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e7a2  lea     rdx, asc_1800362F0; ">"
0x18002e7a9  mov     rcx, rdi
0x18002e7ac  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e7b1  lea     rdx, [rsp+0A8h+var_48]
0x18002e7b6  mov     rcx, rdi
0x18002e7b9  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator_static@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@2@XZ; std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>>::str(void)
0x18002e7be  mov     r14, [rax+18h]
0x18002e7c2  xor     r8d, r8d
0x18002e7c5  mov     dl, 1
0x18002e7c7  lea     rcx, [rsp+0A8h+var_48]
0x18002e7cc  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18002e7d1  nop
0x18002e7d2  lea     rdx, [rsi+8]
0x18002e7d6  mov     rcx, rdi
0x18002e7d9  call    ??6@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@AEAV01@AEBVCXdsSignedInfo@@@Z; operator<<(std::ostream &,CXdsSignedInfo const &)
0x18002e7de  lea     rdx, [rsp+0A8h+var_70]
0x18002e7e3  mov     rcx, rdi
0x18002e7e6  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator_static@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@2@XZ; std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>>::str(void)
0x18002e7eb  mov     rbx, [rax+18h]
0x18002e7ef  xor     r8d, r8d
0x18002e7f2  mov     dl, 1
0x18002e7f4  lea     rcx, [rsp+0A8h+var_70]
0x18002e7f9  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18002e7fe  nop
0x18002e7ff  lea     rdx, aSignaturevalue; "<SignatureValue>"
0x18002e806  mov     rcx, rdi
0x18002e809  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e80e  mov     rdx, [rsi+40h]
0x18002e812  mov     rcx, rdi
0x18002e815  test    rdx, rdx
0x18002e818  jz      short loc_18002E821
0x18002e81a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e81f  jmp     short loc_18002E889
0x18002e821  lea     rdx, [rsp+0A8h+var_70]
0x18002e826  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator_static@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@2@XZ; std::basic_ostringstream<char,std::char_traits<char>,std::allocator_static<char>>::str(void)
0x18002e82b  nop
0x18002e82c  mov     r10, [rsi+58h]
0x18002e830  lea     rcx, [rsp+0A8h+var_68]
0x18002e835  cmp     [rsp+0A8h+var_50], 10h
0x18002e83b  cmovnb  rcx, [rsp+0A8h+var_68]
0x18002e841  sub     ebx, r14d
0x18002e844  add     rcx, r14; pbData
0x18002e847  mov     [rsp+0A8h+var_88], r10; unsigned __int64
0x18002e84c  mov     r9d, [rsi+50h]; unsigned int
0x18002e850  mov     r8d, [rsi+10h]; unsigned int
0x18002e854  mov     edx, ebx; dwDataLen
0x18002e856  call    ?XdsCalcSignature@@YAPEADPEBDKIK_K@Z; XdsCalcSignature(char const *,ulong,uint,ulong,unsigned __int64)
0x18002e85b  mov     rbx, rax
0x18002e85e  mov     [rsp+0A8h+var_78], rax
0x18002e863  mov     rdx, rax
0x18002e866  mov     rcx, rdi
0x18002e869  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e86e  nop
0x18002e86f  mov     rcx, rbx; Block
0x18002e872  call    cs:__imp_free
0x18002e878  nop
0x18002e879  xor     r8d, r8d
0x18002e87c  mov     dl, 1
0x18002e87e  lea     rcx, [rsp+0A8h+var_70]
0x18002e883  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18002e888  nop
0x18002e889  lea     rdx, aSignaturevalue_0; "</SignatureValue>"
0x18002e890  mov     rcx, rdi
0x18002e893  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e898  cmp     qword ptr [rsi+48h], 0
0x18002e89d  jz      short loc_18002E8E7
0x18002e89f  lea     rdx, aKeyinfo; "<KeyInfo>"
0x18002e8a6  mov     rcx, rdi
0x18002e8a9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e8ae  lea     rdx, aKeyvalue_0; "<KeyValue>"
0x18002e8b5  mov     rcx, rdi
0x18002e8b8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e8bd  mov     rdx, [rsi+48h]
0x18002e8c1  mov     rcx, rdi
0x18002e8c4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e8c9  lea     rdx, aKeyvalue; "</KeyValue>"
0x18002e8d0  mov     rcx, rdi
0x18002e8d3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e8d8  lea     rdx, aKeyinfo_0; "</KeyInfo>"
0x18002e8df  mov     rcx, rdi
0x18002e8e2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e8e7  lea     rdx, aSignature; "</Signature>"
0x18002e8ee  mov     rcx, rdi
0x18002e8f1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e8f6  mov     rax, rdi
0x18002e8f9  mov     rcx, [rsp+0A8h+var_20]
0x18002e901  xor     rcx, rsp; StackCookie
0x18002e904  call    __security_check_cookie
0x18002e909  mov     rbx, [rsp+0A8h+arg_10]
0x18002e911  add     rsp, 90h
0x18002e918  pop     r14
0x18002e91a  pop     rdi
0x18002e91b  pop     rsi
0x18002e91c  retn
```
