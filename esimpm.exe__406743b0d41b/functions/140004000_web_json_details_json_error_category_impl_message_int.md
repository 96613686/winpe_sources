# web::json::details::json_error_category_impl::message(int)

- ea: `0x140004000`
- end: `0x140004178`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004000`
- `0x14001e8f4`

## string_xrefs

- `0x14000402c`: `Left-over characters in stream after parsing a JSON value`
- `0x14000405c`: `Malformed comment`
- `0x1400040d4`: `Malformed token`
- `0x14000411c`: `Unexpected token`
- `0x140004134`: `Unknown json error`

## pseudocode

```c
__int64 __fastcall web::json::details::json_error_category_impl::message(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  switch ( a3 )
  {
    case 1:
      std::string::string(a2, "Left-over characters in stream after parsing a JSON value");
      result = a2;
      break;
    case 2:
      std::string::string(a2, "Malformed array literal");
      result = a2;
      break;
    case 3:
      std::string::string(a2, "Malformed comment");
      result = a2;
      break;
    case 4:
      std::string::string(a2, "Malformed literal");
      result = a2;
      break;
    case 5:
      std::string::string(a2, "Malformed object literal");
      result = a2;
      break;
    case 6:
      std::string::string(a2, "Malformed numeric literal");
      result = a2;
      break;
    case 7:
      std::string::string(a2, "Malformed string literal");
      result = a2;
      break;
    case 8:
      std::string::string(a2, "Malformed token");
      result = a2;
      break;
    case 9:
      std::string::string(a2, "Mismatched braces");
      result = a2;
      break;
    case 10:
      std::string::string(a2, "Nesting too deep");
      result = a2;
      break;
    case 11:
      std::string::string(a2, "Unexpected token");
      result = a2;
      break;
    default:
      std::string::string(a2, "Unknown json error");
      result = a2;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x140004000  push    rbx
0x140004002  sub     rsp, 30h
0x140004006  dec     r8d; switch 11 cases
0x140004009  mov     rbx, rdx
0x14000400c  cmp     r8d, 0Ah
0x140004010  ja      def_14000402A; jumptable 000000014000402A default case
0x140004016  lea     rdx, __ImageBase
0x14000401d  movsxd  rax, r8d
0x140004020  mov     ecx, ds:(jpt_14000402A - 140000000h)[rdx+rax*4]
0x140004027  add     rcx, rdx
0x14000402a  jmp     rcx; switch jump
0x14000402c  lea     rdx, aLeftOverCharac_0; jumptable 000000014000402A case 1
0x140004033  mov     rcx, rbx
0x140004036  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000403b  mov     rax, rbx
0x14000403e  add     rsp, 30h
0x140004042  pop     rbx
0x140004043  retn
0x140004044  lea     rdx, aMalformedArray; jumptable 000000014000402A case 2
0x14000404b  mov     rcx, rbx
0x14000404e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140004053  mov     rax, rbx
0x140004056  add     rsp, 30h
0x14000405a  pop     rbx
0x14000405b  retn
0x14000405c  lea     rdx, aMalformedComme; jumptable 000000014000402A case 3
0x140004063  mov     rcx, rbx
0x140004066  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000406b  mov     rax, rbx
0x14000406e  add     rsp, 30h
0x140004072  pop     rbx
0x140004073  retn
0x140004074  lea     rdx, aMalformedLiter; jumptable 000000014000402A case 4
0x14000407b  mov     rcx, rbx
0x14000407e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140004083  mov     rax, rbx
0x140004086  add     rsp, 30h
0x14000408a  pop     rbx
0x14000408b  retn
0x14000408c  lea     rdx, aMalformedObjec; jumptable 000000014000402A case 5
0x140004093  mov     rcx, rbx
0x140004096  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000409b  mov     rax, rbx
0x14000409e  add     rsp, 30h
0x1400040a2  pop     rbx
0x1400040a3  retn
0x1400040a4  lea     rdx, aMalformedNumer; jumptable 000000014000402A case 6
0x1400040ab  mov     rcx, rbx
0x1400040ae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400040b3  mov     rax, rbx
0x1400040b6  add     rsp, 30h
0x1400040ba  pop     rbx
0x1400040bb  retn
0x1400040bc  lea     rdx, aMalformedStrin; jumptable 000000014000402A case 7
0x1400040c3  mov     rcx, rbx
0x1400040c6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400040cb  mov     rax, rbx
0x1400040ce  add     rsp, 30h
0x1400040d2  pop     rbx
0x1400040d3  retn
0x1400040d4  lea     rdx, aMalformedToken; jumptable 000000014000402A case 8
0x1400040db  mov     rcx, rbx
0x1400040de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400040e3  mov     rax, rbx
0x1400040e6  add     rsp, 30h
0x1400040ea  pop     rbx
0x1400040eb  retn
0x1400040ec  lea     rdx, aMismatchedBrac; jumptable 000000014000402A case 9
0x1400040f3  mov     rcx, rbx
0x1400040f6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400040fb  mov     rax, rbx
0x1400040fe  add     rsp, 30h
0x140004102  pop     rbx
0x140004103  retn
0x140004104  lea     rdx, aNestingTooDeep; jumptable 000000014000402A case 10
0x14000410b  mov     rcx, rbx
0x14000410e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140004113  mov     rax, rbx
0x140004116  add     rsp, 30h
0x14000411a  pop     rbx
0x14000411b  retn
0x14000411c  lea     rdx, aUnexpectedToke; jumptable 000000014000402A case 11
0x140004123  mov     rcx, rbx
0x140004126  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000412b  mov     rax, rbx
0x14000412e  add     rsp, 30h
0x140004132  pop     rbx
0x140004133  retn
0x140004134  lea     rdx, aUnknownJsonErr; jumptable 000000014000402A default case
0x14000413b  mov     rcx, rbx
0x14000413e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140004143  mov     rax, rbx
0x140004146  add     rsp, 30h
0x14000414a  pop     rbx
0x14000414b  retn
```
