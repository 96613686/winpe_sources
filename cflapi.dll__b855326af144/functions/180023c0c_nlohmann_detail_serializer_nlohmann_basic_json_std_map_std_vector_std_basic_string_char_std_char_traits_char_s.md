# nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::dump_escaped(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool)

- ea: `0x180023c0c`
- end: `0x180024023`
- name: `?dump_escaped@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002330c`

## callees

- `0x180002490`
- `0x180002f04`
- `0x180002fc8`
- `0x180012fb0`
- `0x180013070`
- `0x180013130`
- `0x180013240`
- `0x18001a1e8`
- `0x18001b54c`
- `0x18002256c`
- `0x180022be8`
- `0x180023c0c`
- `0x180027994`
- `0x1800279a0`
- `0x180030010`

## string_xrefs

- `0x180023fee`: `incomplete UTF-8 string; last byte: 0x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_escaped(
        _QWORD *a1,
        _QWORD *a2)
{
  unsigned int v4; // r14d
  int v5; // r13d
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned __int64 v9; // r15
  __int64 *v10; // r9
  _QWORD *v11; // rax
  __int64 v12; // r12
  __int64 v13; // rcx
  _QWORD *v14; // rax
  int v15; // r9d
  unsigned __int64 v16; // rax
  char *v17; // rdx
  _QWORD *v18; // rax
  int v19; // ecx
  int v20; // ecx
  __int64 *v21; // rdx
  size_t v22; // rax
  char *const v23; // r10
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  size_t v28; // rax
  int v29; // r9d
  char *const v30; // r10
  __int64 v31; // rax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-B9h] BYREF
  _BYTE v33[32]; // [rsp+58h] [rbp-81h] BYREF
  _BYTE v34[32]; // [rsp+78h] [rbp-61h] BYREF
  char v35[32]; // [rsp+98h] [rbp-41h] BYREF
  char v36[32]; // [rsp+B8h] [rbp-21h] BYREF
  char v37[32]; // [rsp+D8h] [rbp-1h] BYREF

  v4 = 0;
  LOBYTE(v5) = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2[2] )
    return;
  v10 = `nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d;
  do
  {
    if ( a2[3] <= 0xFu )
      v11 = a2;
    else
      v11 = (_QWORD *)*a2;
    v12 = *((unsigned __int8 *)v11 + v9);
    if ( (_BYTE)v5 )
      v4 = (v4 << 6) | v12 & 0x3F;
    else
      v4 = v12
         & (0xFFu >> *((_BYTE *)`nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d
                     + v12));
    v13 = *((unsigned __int8 *)`nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d
          + v12)
        + 16LL * (unsigned __int8)v5;
    v5 = *((unsigned __int8 *)&`nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d[32]
         + v13);
    if ( !*((_BYTE *)&`nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d[32]
          + v13) )
    {
      switch ( v4 )
      {
        case 8u:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 98;
          break;
        case 9u:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 116;
          break;
        case 0xAu:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 110;
          break;
        case 0xCu:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 102;
          break;
        case 0xDu:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 114;
          break;
        case 0x22u:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 34;
          break;
        case 0x5Cu:
          *((_BYTE *)a1 + v6 + 90) = 92;
          *((_BYTE *)a1 + v6 + 91) = 92;
          break;
        default:
          if ( v4 <= 0x1F )
          {
            snprintf((char *const)a1 + v6 + 90, 7u, "\\u%04x", (unsigned __int16)v4);
            v6 += 6;
          }
          else
          {
            if ( a2[3] <= 0xFu )
              v18 = a2;
            else
              v18 = (_QWORD *)*a2;
            *((_BYTE *)a1 + v6++ + 90) = *((_BYTE *)v18 + v9);
          }
          goto LABEL_46;
      }
      v6 += 2;
LABEL_46:
      if ( (unsigned __int64)(512 - v6) < 0xD )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(*(_QWORD *)*a1 + 8LL))(
          *a1,
          (__int64)a1 + 90,
          v6,
          v10);
        v6 = 0;
      }
      v7 = v6;
      v8 = 0;
      goto LABEL_49;
    }
    if ( v5 == 1 )
    {
      v15 = *((_DWORD *)a1 + 160);
      if ( !v15 )
      {
        std::string::string(v33, 3);
        std::string::operator[](v33);
        v22 = std::string::size(v33);
        snprintf(v23, v22, "%.2X", v12);
        v24 = std::to_string(v35, v9);
        v25 = std::operator+<char>(v36, "invalid UTF-8 byte at index ", v24);
        v26 = std::operator+<char>(v37, v25, ": 0x");
        v27 = std::operator+<char>(v34, v26, v33);
        nlohmann::detail::type_error::create(pExceptionObject, 316, v27);
        throw (nlohmann::detail::type_error *)pExceptionObject;
      }
      if ( (unsigned int)(v15 - 1) <= 1 )
      {
        v16 = v9 - 1;
        if ( !v8 )
          v16 = v9;
        v9 = v16;
        if ( v15 == 1 )
        {
          v17 = (char *)a1 + 90;
          v17[v7] = -17;
          *((_BYTE *)a1 + v7 + 91) = -65;
          v17[v7 + 2] = -67;
          v6 = v7 + 3;
          if ( (unsigned __int64)(511 - (v7 + 2)) < 0xD )
          {
            (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a1 + 8LL))(*a1, v17, v7 + 3);
            v6 = 0;
          }
          v7 = v6;
        }
        else
        {
          v6 = v7;
        }
        v8 = 0;
        LOBYTE(v5) = 0;
      }
LABEL_49:
      v10 = `nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d;
      goto LABEL_50;
    }
    if ( a2[3] <= 0xFu )
      v14 = a2;
    else
      v14 = (_QWORD *)*a2;
    *((_BYTE *)a1 + v6++ + 90) = *((_BYTE *)v14 + v9);
    ++v8;
LABEL_50:
    ++v9;
  }
  while ( v9 < a2[2] );
  if ( (_BYTE)v5 )
  {
    v19 = *((_DWORD *)a1 + 160);
    if ( !v19 )
    {
      std::string::string(v33, 3);
      std::string::back(a2);
      std::string::operator[](v33);
      v28 = std::string::size(v33);
      snprintf(v30, v28, "%.2X", v29);
      v31 = std::operator+<char>(v34, "incomplete UTF-8 string; last byte: 0x", v33);
      nlohmann::detail::type_error::create(pExceptionObject, 316, v31);
      throw (nlohmann::detail::type_error *)pExceptionObject;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      if ( v20 != 1 )
        return;
LABEL_57:
      v21 = (_QWORD *)((char *)a1 + 90);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(*(_QWORD *)*a1 + 8LL))(
        *a1,
        (__int64)a1 + 90,
        v7,
        `nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::decode'::`2'::utf8d);
      v7 = 3;
      v21 = &qword_180033418;
    }
    (*(void (__fastcall **)(_QWORD, __int64 *, __int64, __int64 *))(*(_QWORD *)*a1 + 8LL))(*a1, v21, v7, v10);
  }
  else if ( v6 )
  {
    v7 = v6;
    goto LABEL_57;
  }
}

```

## disassembly

```asm
0x180023c0c  mov     [rsp-8+arg_10], rbx
0x180023c11  push    rbp
0x180023c12  push    rsi
0x180023c13  push    rdi
0x180023c14  push    r12
0x180023c16  push    r13
0x180023c18  push    r14
0x180023c1a  push    r15
0x180023c1c  lea     rbp, [rsp-27h]
0x180023c21  sub     rsp, 100h
0x180023c28  mov     rax, cs:__security_cookie
0x180023c2f  xor     rax, rsp
0x180023c32  mov     [rbp+57h+var_38], rax
0x180023c36  mov     rsi, rdx
0x180023c39  mov     rdi, rcx
0x180023c3c  xor     r14d, r14d
0x180023c3f  xor     r13b, r13b
0x180023c42  xor     ebx, ebx
0x180023c44  xor     r8d, r8d
0x180023c47  xor     edx, edx
0x180023c49  xor     r15d, r15d
0x180023c4c  cmp     [rsi+10h], rdx
0x180023c50  jbe     loc_180023EB0
0x180023c56  lea     r9, ?utf8d@?1??decode@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@CAEAEAEAEAIE@Z@4V?$array@E$0BJA@@std@@B; std::array<uchar,400> const `nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::decode(uchar &,uint &,uchar)'::`2'::utf8d
0x180023c5d  cmp     qword ptr [rsi+18h], 0Fh
0x180023c62  jbe     short loc_180023C69
0x180023c64  mov     rax, [rsi]
0x180023c67  jmp     short loc_180023C6C
0x180023c69  mov     rax, rsi
0x180023c6c  movzx   r12d, byte ptr [rax+r15]
0x180023c71  test    r13b, r13b
0x180023c74  jz      short loc_180023C8A
0x180023c76  mov     ecx, r12d
0x180023c79  and     ecx, 3Fh
0x180023c7c  mov     eax, r14d
0x180023c7f  shl     eax, 6
0x180023c82  mov     r14d, ecx
0x180023c85  or      r14d, eax
0x180023c88  jmp     short loc_180023C9A
0x180023c8a  mov     cl, [r12+r9]
0x180023c8e  mov     r14d, 0FFh
0x180023c94  shr     r14d, cl
0x180023c97  and     r14d, r12d
0x180023c9a  movzx   ecx, r13b
0x180023c9e  shl     rcx, 4
0x180023ca2  movzx   eax, byte ptr [r12+r9]
0x180023ca7  add     rcx, rax
0x180023caa  movzx   r13d, byte ptr [rcx+r9+100h]
0x180023cb3  test    r13d, r13d
0x180023cb6  jz      loc_180023D68
0x180023cbc  cmp     r13d, 1
0x180023cc0  jz      short loc_180023CE4
0x180023cc2  cmp     qword ptr [rsi+18h], 0Fh
0x180023cc7  jbe     short loc_180023CCE
0x180023cc9  mov     rax, [rsi]
0x180023ccc  jmp     short loc_180023CD1
0x180023cce  mov     rax, rsi
0x180023cd1  mov     al, [rax+r15]
0x180023cd5  mov     [rdi+rbx+5Ah], al
0x180023cd9  inc     rbx
0x180023cdc  inc     rdx
0x180023cdf  jmp     loc_180023E69
0x180023ce4  mov     r9d, [rdi+280h]
0x180023ceb  mov     ecx, r9d
0x180023cee  test    r9d, r9d
0x180023cf1  jz      loc_180023EF9
0x180023cf7  sub     ecx, 1
0x180023cfa  jz      short loc_180023D05
0x180023cfc  cmp     ecx, 1
0x180023cff  jnz     loc_180023E62
0x180023d05  lea     rax, [r15-1]
0x180023d09  test    rdx, rdx
0x180023d0c  cmovz   rax, r15
0x180023d10  mov     r15, rax
0x180023d13  cmp     r9d, 1
0x180023d17  jnz     short loc_180023D5B
0x180023d19  lea     rdx, [rdi+5Ah]
0x180023d1d  lea     rcx, [r8+2]
0x180023d21  mov     byte ptr [rdx+r8], 0EFh
0x180023d26  mov     byte ptr [rdi+r8+5Bh], 0BFh
0x180023d2c  mov     byte ptr [rcx+rdx], 0BDh
0x180023d30  lea     rbx, [rcx+1]
0x180023d34  mov     eax, 1FFh
0x180023d39  sub     rax, rcx
0x180023d3c  cmp     rax, 0Dh
0x180023d40  jnb     short loc_180023D56
0x180023d42  mov     rcx, [rdi]
0x180023d45  mov     rax, [rcx]
0x180023d48  mov     r8, rbx
0x180023d4b  mov     rax, [rax+8]
0x180023d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d54  xor     ebx, ebx
0x180023d56  mov     r8, rbx
0x180023d59  jmp     short loc_180023D5E
0x180023d5b  mov     rbx, r8
0x180023d5e  xor     edx, edx
0x180023d60  xor     r13b, r13b
0x180023d63  jmp     loc_180023E62
0x180023d68  mov     eax, r14d
0x180023d6b  sub     eax, 8
0x180023d6e  jz      loc_180023E26
0x180023d74  sub     eax, 1
0x180023d77  jz      loc_180023E1A
0x180023d7d  sub     eax, 1
0x180023d80  jz      loc_180023E0E
0x180023d86  sub     eax, 2
0x180023d89  jz      short loc_180023E02
0x180023d8b  sub     eax, 1
0x180023d8e  jz      short loc_180023DF6
0x180023d90  sub     eax, 15h
0x180023d93  jz      short loc_180023DEA
0x180023d95  cmp     eax, 3Ah ; ':'
0x180023d98  jz      short loc_180023DDE
0x180023d9a  cmp     r14d, 1Fh
0x180023d9e  jbe     short loc_180023DBC
0x180023da0  cmp     qword ptr [rsi+18h], 0Fh
0x180023da5  jbe     short loc_180023DAC
0x180023da7  mov     rax, [rsi]
0x180023daa  jmp     short loc_180023DAF
0x180023dac  mov     rax, rsi
0x180023daf  mov     al, [rax+r15]
0x180023db3  mov     [rdi+rbx+5Ah], al
0x180023db7  inc     rbx
0x180023dba  jmp     short loc_180023E34
0x180023dbc  movzx   r9d, r14w
0x180023dc0  lea     rcx, [rdi+5Ah]
0x180023dc4  add     rcx, rbx; Buffer
0x180023dc7  lea     r8, Format; "\\u%04x"
0x180023dce  mov     edx, 7; BufferCount
0x180023dd3  call    snprintf
0x180023dd8  add     rbx, 6
0x180023ddc  jmp     short loc_180023E34
0x180023dde  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023de3  mov     byte ptr [rbx+rdi+5Bh], 5Ch ; '\'
0x180023de8  jmp     short loc_180023E30
0x180023dea  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023def  mov     byte ptr [rbx+rdi+5Bh], 22h ; '"'
0x180023df4  jmp     short loc_180023E30
0x180023df6  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023dfb  mov     byte ptr [rbx+rdi+5Bh], 72h ; 'r'
0x180023e00  jmp     short loc_180023E30
0x180023e02  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023e07  mov     byte ptr [rbx+rdi+5Bh], 66h ; 'f'
0x180023e0c  jmp     short loc_180023E30
0x180023e0e  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023e13  mov     byte ptr [rbx+rdi+5Bh], 6Eh ; 'n'
0x180023e18  jmp     short loc_180023E30
0x180023e1a  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023e1f  mov     byte ptr [rbx+rdi+5Bh], 74h ; 't'
0x180023e24  jmp     short loc_180023E30
0x180023e26  mov     byte ptr [rdi+rbx+5Ah], 5Ch ; '\'
0x180023e2b  mov     byte ptr [rbx+rdi+5Bh], 62h ; 'b'
0x180023e30  add     rbx, 2
0x180023e34  mov     rdx, rdi
0x180023e37  mov     eax, 200h
0x180023e3c  sub     rax, rbx
0x180023e3f  cmp     rax, 0Dh
0x180023e43  jnb     short loc_180023E5D
0x180023e45  mov     rcx, [rdi]
0x180023e48  mov     rax, [rcx]
0x180023e4b  add     rdx, 5Ah ; 'Z'
0x180023e4f  mov     r8, rbx
0x180023e52  mov     rax, [rax+8]
0x180023e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e5b  xor     ebx, ebx
0x180023e5d  mov     r8, rbx
0x180023e60  xor     edx, edx
0x180023e62  lea     r9, ?utf8d@?1??decode@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@CAEAEAEAEAIE@Z@4V?$array@E$0BJA@@std@@B; std::array<uchar,400> const `nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::decode(uchar &,uint &,uchar)'::`2'::utf8d
0x180023e69  inc     r15
0x180023e6c  cmp     r15, [rsi+10h]
0x180023e70  jb      loc_180023C5D
0x180023e76  test    r13b, r13b
0x180023e79  jnz     short loc_180023E85
0x180023e7b  test    rbx, rbx
0x180023e7e  jz      short loc_180023EB0
0x180023e80  mov     r8, rbx
0x180023e83  jmp     short loc_180023E9D
0x180023e85  mov     ecx, [rdi+280h]
0x180023e8b  test    ecx, ecx
0x180023e8d  jz      loc_180023FA2
0x180023e93  sub     ecx, 1
0x180023e96  jz      short loc_180023ED7
0x180023e98  cmp     ecx, 1
0x180023e9b  jnz     short loc_180023EB0
0x180023e9d  lea     rdx, [rdi+5Ah]
0x180023ea1  mov     rcx, [rdi]
0x180023ea4  mov     rax, [rcx]
0x180023ea7  mov     rax, [rax+8]
0x180023eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eb0  mov     rcx, [rbp+57h+var_38]
0x180023eb4  xor     rcx, rsp; StackCookie
0x180023eb7  call    __security_check_cookie
0x180023ebc  mov     rbx, [rsp+130h+arg_10]
0x180023ec4  add     rsp, 100h
0x180023ecb  pop     r15
0x180023ecd  pop     r14
0x180023ecf  pop     r13
0x180023ed1  pop     r12
0x180023ed3  pop     rdi
0x180023ed4  pop     rsi
0x180023ed5  pop     rbp
0x180023ed6  retn
0x180023ed7  mov     rcx, [rdi]
0x180023eda  mov     rax, [rcx]
0x180023edd  lea     rdx, [rdi+5Ah]
0x180023ee1  mov     rax, [rax+8]
0x180023ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eea  mov     r8d, 3
0x180023ef0  lea     rdx, qword_180033418
0x180023ef7  jmp     short loc_180023EA1
0x180023ef9  xor     r8d, r8d
0x180023efc  lea     edx, [r8+3]
0x180023f00  lea     rcx, [rsp+130h+var_D8]
0x180023f05  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180023f0a  nop
0x180023f0b  lea     rcx, [rsp+130h+var_D8]
0x180023f10  call    ??A?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAD_K@Z; std::string::operator[](unsigned __int64)
0x180023f15  mov     r10, rax
0x180023f18  lea     rcx, [rsp+130h+var_D8]
0x180023f1d  call    ?size@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KXZ; std::string::size(void)
0x180023f22  mov     rdx, rax; BufferCount
0x180023f25  mov     r9d, r12d
0x180023f28  lea     r8, a2x; "%.2X"
0x180023f2f  mov     rcx, r10; Buffer
0x180023f32  call    snprintf
0x180023f37  mov     rdx, r15
0x180023f3a  lea     rcx, [rbp+57h+var_98]
0x180023f3e  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::to_string(unsigned __int64)
0x180023f43  nop
0x180023f44  mov     r8, rax
0x180023f47  lea     rdx, aInvalidUtf8Byt; "invalid UTF-8 byte at index "
0x180023f4e  lea     rcx, [rbp+57h+var_78]
0x180023f52  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180023f57  nop
0x180023f58  lea     r8, a0x; ": 0x"
0x180023f5f  mov     rdx, rax
0x180023f62  lea     rcx, [rbp+57h+var_58]
0x180023f66  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180023f6b  nop
0x180023f6c  lea     r8, [rsp+130h+var_D8]
0x180023f71  mov     rdx, rax
0x180023f74  lea     rcx, [rbp+57h+var_B8]
0x180023f78  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180023f7d  nop
0x180023f7e  mov     r8, rax
0x180023f81  mov     edx, 13Ch
0x180023f86  lea     rcx, [rsp+130h+pExceptionObject]
0x180023f8b  call    ?create@type_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::type_error::create(int,std::string const &)
0x180023f90  lea     rdx, _TI3?AVtype_error@detail@nlohmann@@; pThrowInfo
0x180023f97  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180023f9c  call    _CxxThrowException_0
0x180023fa2  xor     r8d, r8d
0x180023fa5  lea     edx, [r8+3]
0x180023fa9  lea     rcx, [rsp+130h+var_D8]
0x180023fae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180023fb3  nop
0x180023fb4  mov     rcx, rsi
0x180023fb7  call    ?back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAAEBDXZ; std::string::back(void)
0x180023fbc  movzx   r9d, byte ptr [rax]
0x180023fc0  lea     rcx, [rsp+130h+var_D8]
0x180023fc5  call    ??A?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAD_K@Z; std::string::operator[](unsigned __int64)
0x180023fca  mov     r10, rax
0x180023fcd  lea     rcx, [rsp+130h+var_D8]
0x180023fd2  call    ?size@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KXZ; std::string::size(void)
0x180023fd7  mov     rdx, rax; BufferCount
0x180023fda  lea     r8, a2x; "%.2X"
0x180023fe1  mov     rcx, r10; Buffer
0x180023fe4  call    snprintf
0x180023fe9  lea     r8, [rsp+130h+var_D8]
0x180023fee  lea     rdx, aIncompleteUtf8; "incomplete UTF-8 string; last byte: 0x"
0x180023ff5  lea     rcx, [rbp+57h+var_B8]
0x180023ff9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180023ffe  nop
0x180023fff  mov     r8, rax
0x180024002  mov     edx, 13Ch
0x180024007  lea     rcx, [rsp+130h+pExceptionObject]
0x18002400c  call    ?create@type_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::type_error::create(int,std::string const &)
0x180024011  lea     rdx, _TI3?AVtype_error@detail@nlohmann@@; pThrowInfo
0x180024018  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18002401d  call    _CxxThrowException_0
```
