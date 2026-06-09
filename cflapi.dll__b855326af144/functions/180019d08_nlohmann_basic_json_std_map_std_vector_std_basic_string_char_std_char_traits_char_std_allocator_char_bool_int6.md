# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> const &)

- ea: `0x180019d08`
- end: `0x180019ea6`
- name: `??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBV01@@Z`
- size: `414`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180013904`
- `0x18001a57c`
- `0x180024128`
- `0x180024220`
- `0x1800250a0`

## callees

- `0x18000289c`
- `0x180019d08`
- `0x180019eac`
- `0x18001a470`
- `0x18001a57c`
- `0x18001aa1c`
- `0x180021420`
- `0x18002e008`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // r15
  _QWORD *v4; // r14
  __int64 v5; // rdx
  char *v6; // rdi
  size_t v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  void *v11; // [rsp+28h] [rbp-8h]
  __int64 v12; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  *(_BYTE *)a1 = *(_BYTE *)a2;
  *(_QWORD *)(a1 + 8) = 0;
  switch ( *(_BYTE *)a1 )
  {
    case 1:
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        &v12,
        *(_QWORD *)(a2 + 8));
      goto LABEL_19;
    case 2:
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        &v12,
        *(_QWORD *)(a2 + 8));
LABEL_19:
      *(_QWORD *)(a1 + 8) = v12;
      return a1;
    case 3:
      v9 = *(_QWORD *)(a2 + 8);
      v11 = operator new(0x20u);
      std::string::string(v11, v9);
      *(_QWORD *)(a1 + 8) = v11;
      return a1;
    case 4:
      *(_BYTE *)(a1 + 8) = *(_BYTE *)(a2 + 8);
      *(_DWORD *)(a1 + 9) = *(_DWORD *)((char *)&v12 + 1);
      *(_WORD *)(a1 + 13) = *(_WORD *)((char *)&v12 + 5);
      *(_BYTE *)(a1 + 15) = HIBYTE(v12);
      return a1;
    case 5:
    case 6:
      v8 = *(_QWORD *)(a2 + 8);
      goto LABEL_14;
    case 7:
      v8 = *(_QWORD *)(a2 + 8);
LABEL_14:
      *(_QWORD *)(a1 + 8) = v8;
      return a1;
    case 8:
      v3 = *(_QWORD *)(a2 + 8);
      v4 = operator new(0x20u);
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      v5 = *(_QWORD *)(v3 + 8) - *(_QWORD *)v3;
      if ( v5 )
      {
        std::vector<unsigned char>::_Buy_nonzero(v4, v5);
        v6 = (char *)*v4;
        v7 = *(_QWORD *)(v3 + 8) - *(_QWORD *)v3;
        memmove_0((void *)*v4, *(const void **)v3, v7);
        v4[1] = &v6[v7];
        v13 = 0;
        std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v13);
      }
      *((_BYTE *)v4 + 24) = *(_BYTE *)(v3 + 24);
      *((_BYTE *)v4 + 25) = *(_BYTE *)(v3 + 25);
      *(_QWORD *)(a1 + 8) = v4;
      break;
  }
  return a1;
}

```

## disassembly

```asm
0x180019d08  mov     [rsp-28h+arg_10], rbx
0x180019d0d  push    rbp
0x180019d0e  push    rsi
0x180019d0f  push    rdi
0x180019d10  push    r14
0x180019d12  push    r15
0x180019d14  mov     rbp, rsp
0x180019d17  sub     rsp, 30h
0x180019d1b  mov     rsi, rcx
0x180019d1e  mov     al, [rdx]
0x180019d20  mov     [rcx], al
0x180019d22  xor     eax, eax
0x180019d24  mov     [rcx+8], rax
0x180019d28  movzx   r8d, byte ptr [rcx]
0x180019d2c  sub     r8d, 1
0x180019d30  jz      loc_180019E7D
0x180019d36  sub     r8d, 1
0x180019d3a  jz      loc_180019E6E
0x180019d40  sub     r8d, 1
0x180019d44  jz      loc_180019E3F
0x180019d4a  sub     r8d, 1
0x180019d4e  jz      loc_180019E23
0x180019d54  sub     r8d, 1
0x180019d58  jz      loc_180019E19
0x180019d5e  sub     r8d, 1
0x180019d62  jz      loc_180019E19
0x180019d68  sub     r8d, 1
0x180019d6c  jz      loc_180019E09
0x180019d72  cmp     r8d, 1
0x180019d76  jnz     loc_180019E92
0x180019d7c  mov     r15, [rdx+8]
0x180019d80  lea     ecx, [rax+20h]; Size
0x180019d83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019d88  mov     r14, rax
0x180019d8b  lea     rax, [rbp+arg_0]
0x180019d8f  mov     [rbp+var_10], rax
0x180019d93  mov     [rbp+var_8], r14
0x180019d97  mov     qword ptr [r14], 0
0x180019d9e  mov     qword ptr [r14+8], 0
0x180019da6  mov     qword ptr [r14+10h], 0
0x180019dae  mov     rdx, [r15+8]
0x180019db2  sub     rdx, [r15]
0x180019db5  jz      short loc_180019DF0
0x180019db7  mov     rcx, r14
0x180019dba  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180019dbf  mov     rdi, [r14]
0x180019dc2  mov     rbx, [r15+8]
0x180019dc6  sub     rbx, [r15]
0x180019dc9  mov     r8, rbx; Size
0x180019dcc  mov     rdx, [r15]; Src
0x180019dcf  mov     rcx, rdi; void *
0x180019dd2  call    memmove_0
0x180019dd7  lea     rax, [rbx+rdi]
0x180019ddb  mov     [r14+8], rax
0x180019ddf  mov     [rbp+arg_8], 0
0x180019de7  lea     rcx, [rbp+arg_8]
0x180019deb  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180019df0  mov     al, [r15+18h]
0x180019df4  mov     [r14+18h], al
0x180019df8  mov     al, [r15+19h]
0x180019dfc  mov     [r14+19h], al
0x180019e00  mov     [rsi+8], r14
0x180019e04  jmp     loc_180019E92
0x180019e09  movsd   xmm0, qword ptr [rdx+8]
0x180019e0e  movsd   [rbp+arg_0], xmm0
0x180019e13  mov     rax, [rbp+arg_0]
0x180019e17  jmp     short loc_180019E1D
0x180019e19  mov     rax, [rdx+8]
0x180019e1d  mov     [rcx+8], rax
0x180019e21  jmp     short loc_180019E92
0x180019e23  mov     al, [rdx+8]
0x180019e26  mov     [rcx+8], al
0x180019e29  mov     eax, dword ptr [rbp+arg_0+1]
0x180019e2c  mov     [rcx+9], eax
0x180019e2f  movzx   eax, word ptr [rbp+arg_0+5]
0x180019e33  mov     [rcx+0Dh], ax
0x180019e37  mov     al, byte ptr [rbp+arg_0+7]
0x180019e3a  mov     [rcx+0Fh], al
0x180019e3d  jmp     short loc_180019E92
0x180019e3f  mov     rbx, [rdx+8]
0x180019e43  mov     ecx, 20h ; ' '; Size
0x180019e48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019e4d  mov     rdi, rax
0x180019e50  lea     rax, [rbp+arg_0]
0x180019e54  mov     [rbp+var_10], rax
0x180019e58  mov     [rbp+var_8], rdi
0x180019e5c  mov     rdx, rbx
0x180019e5f  mov     rcx, rdi
0x180019e62  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180019e67  nop
0x180019e68  mov     [rsi+8], rdi
0x180019e6c  jmp     short loc_180019E92
0x180019e6e  mov     rdx, [rdx+8]
0x180019e72  lea     rcx, [rbp+arg_0]
0x180019e76  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBV?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> const &)
0x180019e7b  jmp     short loc_180019E8A
0x180019e7d  mov     rdx, [rdx+8]
0x180019e81  lea     rcx, [rbp+arg_0]
0x180019e85  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> const &)
0x180019e8a  mov     rax, [rbp+arg_0]
0x180019e8e  mov     [rsi+8], rax
0x180019e92  mov     rax, rsi
0x180019e95  mov     rbx, [rsp+30h+arg_10]
0x180019e9a  add     rsp, 30h
0x180019e9e  pop     r15
0x180019ea0  pop     r14
0x180019ea2  pop     rdi
0x180019ea3  pop     rsi
0x180019ea4  pop     rbp
0x180019ea5  retn
```
