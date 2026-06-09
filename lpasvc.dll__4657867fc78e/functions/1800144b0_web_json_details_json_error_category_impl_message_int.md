# web::json::details::json_error_category_impl::message(int)

- ea: `0x1800144b0`
- end: `0x180014628`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800144b0`
- `0x1800a4db8`

## string_xrefs

- `0x1800144dc`: `Left-over characters in stream after parsing a JSON value`
- `0x18001450c`: `Malformed comment`
- `0x180014584`: `Malformed token`
- `0x1800145cc`: `Unexpected token`
- `0x1800145e4`: `Unknown json error`

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
0x1800144b0  push    rbx
0x1800144b2  sub     rsp, 30h
0x1800144b6  dec     r8d; switch 11 cases
0x1800144b9  mov     rbx, rdx
0x1800144bc  cmp     r8d, 0Ah
0x1800144c0  ja      def_1800144DA; jumptable 00000001800144DA default case
0x1800144c6  lea     rdx, __ImageBase
0x1800144cd  movsxd  rax, r8d
0x1800144d0  mov     ecx, ds:(jpt_1800144DA - 180000000h)[rdx+rax*4]
0x1800144d7  add     rcx, rdx
0x1800144da  jmp     rcx; switch jump
0x1800144dc  lea     rdx, aLeftOverCharac_0; jumptable 00000001800144DA case 1
0x1800144e3  mov     rcx, rbx
0x1800144e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800144eb  mov     rax, rbx
0x1800144ee  add     rsp, 30h
0x1800144f2  pop     rbx
0x1800144f3  retn
0x1800144f4  lea     rdx, aMalformedArray; jumptable 00000001800144DA case 2
0x1800144fb  mov     rcx, rbx
0x1800144fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014503  mov     rax, rbx
0x180014506  add     rsp, 30h
0x18001450a  pop     rbx
0x18001450b  retn
0x18001450c  lea     rdx, aMalformedComme; jumptable 00000001800144DA case 3
0x180014513  mov     rcx, rbx
0x180014516  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001451b  mov     rax, rbx
0x18001451e  add     rsp, 30h
0x180014522  pop     rbx
0x180014523  retn
0x180014524  lea     rdx, aMalformedLiter; jumptable 00000001800144DA case 4
0x18001452b  mov     rcx, rbx
0x18001452e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014533  mov     rax, rbx
0x180014536  add     rsp, 30h
0x18001453a  pop     rbx
0x18001453b  retn
0x18001453c  lea     rdx, aMalformedObjec; jumptable 00000001800144DA case 5
0x180014543  mov     rcx, rbx
0x180014546  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001454b  mov     rax, rbx
0x18001454e  add     rsp, 30h
0x180014552  pop     rbx
0x180014553  retn
0x180014554  lea     rdx, aMalformedNumer; jumptable 00000001800144DA case 6
0x18001455b  mov     rcx, rbx
0x18001455e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014563  mov     rax, rbx
0x180014566  add     rsp, 30h
0x18001456a  pop     rbx
0x18001456b  retn
0x18001456c  lea     rdx, aMalformedStrin; jumptable 00000001800144DA case 7
0x180014573  mov     rcx, rbx
0x180014576  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001457b  mov     rax, rbx
0x18001457e  add     rsp, 30h
0x180014582  pop     rbx
0x180014583  retn
0x180014584  lea     rdx, aMalformedToken; jumptable 00000001800144DA case 8
0x18001458b  mov     rcx, rbx
0x18001458e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180014593  mov     rax, rbx
0x180014596  add     rsp, 30h
0x18001459a  pop     rbx
0x18001459b  retn
0x18001459c  lea     rdx, aMismatchedBrac; jumptable 00000001800144DA case 9
0x1800145a3  mov     rcx, rbx
0x1800145a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800145ab  mov     rax, rbx
0x1800145ae  add     rsp, 30h
0x1800145b2  pop     rbx
0x1800145b3  retn
0x1800145b4  lea     rdx, aNestingTooDeep; jumptable 00000001800144DA case 10
0x1800145bb  mov     rcx, rbx
0x1800145be  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800145c3  mov     rax, rbx
0x1800145c6  add     rsp, 30h
0x1800145ca  pop     rbx
0x1800145cb  retn
0x1800145cc  lea     rdx, aUnexpectedToke; jumptable 00000001800144DA case 11
0x1800145d3  mov     rcx, rbx
0x1800145d6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800145db  mov     rax, rbx
0x1800145de  add     rsp, 30h
0x1800145e2  pop     rbx
0x1800145e3  retn
0x1800145e4  lea     rdx, aUnknownJsonErr; jumptable 00000001800144DA default case
0x1800145eb  mov     rcx, rbx
0x1800145ee  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800145f3  mov     rax, rbx
0x1800145f6  add     rsp, 30h
0x1800145fa  pop     rbx
0x1800145fb  retn
```
