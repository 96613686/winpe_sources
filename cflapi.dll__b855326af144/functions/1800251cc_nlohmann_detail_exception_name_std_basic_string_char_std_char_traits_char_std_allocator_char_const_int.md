# nlohmann::detail::exception::name(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,int)

- ea: `0x1800251cc`
- end: `0x180025374`
- name: `?name@exception@detail@nlohmann@@KA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV45@H@Z`
- size: `424`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800226a8`
- `0x1800227b4`
- `0x1800228c8`
- `0x1800229d4`
- `0x180022be8`

## callees

- `0x180002490`
- `0x180008a68`
- `0x18000fc54`
- `0x180012ddc`
- `0x180013070`
- `0x180013814`
- `0x18001a0d0`
- `0x1800251cc`

## string_xrefs

- `0x1800252d9`: `[json.exception.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall nlohmann::detail::exception::name(__int64 a1, _QWORD *a2, __int64 a3)
{
  _BYTE *v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 v11; // [rsp+50h] [rbp-49h] BYREF
  __m128i si128; // [rsp+60h] [rbp-39h]
  _BYTE v13[32]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v14[32]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v15[53]; // [rsp+B0h] [rbp+17h] BYREF
  _BYTE v16[3]; // [rsp+E5h] [rbp+4Ch] BYREF

  v5 = v16;
  if ( (int)a3 >= 0 )
  {
    do
    {
      --v5;
      v6 = (unsigned int)a3 / 0xA;
      *v5 = (unsigned int)a3 % 0xA + 48;
      a3 = v6;
    }
    while ( (_DWORD)v6 );
  }
  else
  {
    LODWORD(a3) = -(int)a3;
    do
    {
      --v5;
      v6 = (unsigned int)a3 / 0xA;
      *v5 = (unsigned int)a3 % 0xA + 48;
      a3 = v6;
    }
    while ( (_DWORD)v6 );
    *--v5 = 45;
  }
  v11 = 0;
  si128 = 0;
  if ( v5 == v16 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v11) = 0;
  }
  else
  {
    std::string::_Construct<1,char *>(&v11, v5, v16 - v5);
  }
  v7 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - v7) < 0x10 )
    std::_Xlen_string();
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  std::string::string(v13, v6, a3, "[json.exception.", 16, a2, v7);
  v8 = std::operator+<char>(v15, v13, ".");
  v9 = std::operator+<char>(v14, v8, &v11);
  std::operator+<char>(a1, v9, "] ");
  std::string::~string(v14);
  std::string::~string(v15);
  std::string::~string(v13);
  std::string::~string(&v11);
  return a1;
}

```

## disassembly

```asm
0x1800251cc  mov     [rsp-8+arg_10], rbx
0x1800251d1  mov     [rsp-8+arg_18], rdi
0x1800251d6  push    rbp
0x1800251d7  lea     rbp, [rsp-57h]
0x1800251dc  sub     rsp, 0F0h
0x1800251e3  mov     rax, cs:__security_cookie
0x1800251ea  xor     rax, rsp
0x1800251ed  mov     [rbp+57h+var_8], rax
0x1800251f1  mov     rbx, rdx
0x1800251f4  mov     rdi, rcx
0x1800251f7  mov     [rbp+57h+var_A8], rcx
0x1800251fb  lea     r9, [rbp+57h+var_B]
0x1800251ff  test    r8d, r8d
0x180025202  jns     short loc_180025239
0x180025204  neg     r8d
0x180025207  dec     r9
0x18002520a  mov     eax, 0CCCCCCCDh
0x18002520f  mul     r8d
0x180025212  shr     edx, 3
0x180025215  mov     al, dl
0x180025217  shl     al, 2
0x18002521a  lea     ecx, [rax+rdx]
0x18002521d  add     cl, cl
0x18002521f  sub     r8b, cl
0x180025222  add     r8b, 30h ; '0'
0x180025226  mov     [r9], r8b
0x180025229  mov     r8d, edx
0x18002522c  test    edx, edx
0x18002522e  jnz     short loc_180025207
0x180025230  dec     r9
0x180025233  mov     byte ptr [r9], 2Dh ; '-'
0x180025237  jmp     short loc_180025262
0x180025239  dec     r9
0x18002523c  mov     eax, 0CCCCCCCDh
0x180025241  mul     r8d
0x180025244  shr     edx, 3
0x180025247  mov     al, dl
0x180025249  shl     al, 2
0x18002524c  lea     ecx, [rax+rdx]
0x18002524f  add     cl, cl
0x180025251  sub     r8b, cl
0x180025254  add     r8b, 30h ; '0'
0x180025258  mov     [r9], r8b
0x18002525b  mov     r8d, edx
0x18002525e  test    edx, edx
0x180025260  jnz     short loc_180025239
0x180025262  xorps   xmm0, xmm0
0x180025265  movups  [rbp+57h+var_A0], xmm0
0x180025269  xorps   xmm1, xmm1
0x18002526c  movdqu  [rbp+57h+var_90], xmm1
0x180025271  lea     rax, [rbp+57h+var_B]
0x180025275  cmp     r9, rax
0x180025278  jnz     short loc_18002528D
0x18002527a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180025282  movdqu  [rbp+57h+var_90], xmm0
0x180025287  mov     byte ptr [rbp+57h+var_A0], 0
0x18002528b  jmp     short loc_1800252A1
0x18002528d  lea     r8, [rbp+57h+var_B]
0x180025291  sub     r8, r9
0x180025294  mov     rdx, r9
0x180025297  lea     rcx, [rbp+57h+var_A0]
0x18002529b  call    ??$_Construct@$00PEAD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEAD_K@Z; std::string::_Construct<1,char *>(char * const,unsigned __int64)
0x1800252a0  nop
0x1800252a1  mov     rcx, [rbx+10h]
0x1800252a5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800252af  sub     rax, rcx
0x1800252b2  cmp     rax, 10h
0x1800252b6  jb      loc_18002536E
0x1800252bc  cmp     qword ptr [rbx+18h], 0Fh
0x1800252c1  jbe     short loc_1800252C6
0x1800252c3  mov     rbx, [rbx]
0x1800252c6  mov     [rsp+0F0h+var_C0], rcx
0x1800252cb  mov     [rsp+0F0h+var_C8], rbx
0x1800252d0  mov     [rsp+0F0h+var_D0], 10h
0x1800252d9  lea     r9, aJsonException; "[json.exception."
0x1800252e0  lea     rcx, [rbp+57h+var_80]
0x1800252e4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800252e9  nop
0x1800252ea  lea     r8, asc_180034D00; "."
0x1800252f1  lea     rdx, [rbp+57h+var_80]
0x1800252f5  lea     rcx, [rbp+57h+var_40]
0x1800252f9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800252fe  nop
0x1800252ff  lea     r8, [rbp+57h+var_A0]
0x180025303  mov     rdx, rax
0x180025306  lea     rcx, [rbp+57h+var_60]
0x18002530a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18002530f  nop
0x180025310  lea     r8, asc_180034CFC; "] "
0x180025317  mov     rdx, rax
0x18002531a  mov     rcx, rdi
0x18002531d  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180025322  nop
0x180025323  lea     rcx, [rbp+57h+var_60]
0x180025327  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002532c  nop
0x18002532d  lea     rcx, [rbp+57h+var_40]
0x180025331  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180025336  nop
0x180025337  lea     rcx, [rbp+57h+var_80]
0x18002533b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180025340  nop
0x180025341  lea     rcx, [rbp+57h+var_A0]
0x180025345  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002534a  mov     rax, rdi
0x18002534d  mov     rcx, [rbp+57h+var_8]
0x180025351  xor     rcx, rsp; StackCookie
0x180025354  call    __security_check_cookie
0x180025359  lea     r11, [rsp+0F0h+var_s0]
0x180025361  mov     rbx, [r11+20h]
0x180025365  mov     rdi, [r11+28h]
0x180025369  mov     rsp, r11
0x18002536c  pop     rbp
0x18002536d  retn
0x18002536e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
