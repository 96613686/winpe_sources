# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>(std::vector<uchar,std::allocator<uchar>> &&)

- ea: `0x180012b38`
- end: `0x180012ce5`
- name: `??$?0V?$vector@EV?$allocator@E@std@@@std@@V01@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@$$QEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `429`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001fb28`
- `0x18002b264`

## callees

- `0x180002490`
- `0x18000289c`
- `0x180008a68`
- `0x180012b38`
- `0x18002229c`
- `0x180022cf4`
- `0x180025c30`
- `0x18002d328`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rcx
  __int128 v5; // xmm6
  __int128 v6; // xmm7
  int v7; // eax
  __int64 v8; // r8
  __int128 *v9; // r8
  int v10; // eax
  __int64 v11; // r8
  _OWORD *v12; // rax
  unsigned __int8 v13; // dl
  void *v14; // rcx
  int v16; // [rsp+28h] [rbp-49h]
  int v17; // [rsp+28h] [rbp-49h]
  int v18; // [rsp+38h] [rbp-39h] BYREF
  void *v19; // [rsp+40h] [rbp-31h] BYREF
  __int128 v20; // [rsp+48h] [rbp-29h] BYREF
  __int128 v21; // [rsp+58h] [rbp-19h]
  __int128 v22; // [rsp+68h] [rbp-9h] BYREF
  __int128 v23; // [rsp+78h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v4 = *a2;
  if ( *a2 == a2[1] )
  {
    v22 = 0;
    *(_QWORD *)&v23 = 0;
    *((_QWORD *)&v23 + 1) = 15;
    LOBYTE(v22) = 0;
    v5 = v23;
    v6 = v22;
  }
  else
  {
    v20 = 0;
    *(_QWORD *)&v21 = 0;
    *((_QWORD *)&v21 + 1) = 15;
    LOBYTE(v20) = 0;
    v18 = 0;
    v7 = base64encodeA(v4, *((_DWORD *)a2 + 2) - *(_DWORD *)a2, 0, 0, (__int64)&v18);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x46, v8, (const char *)(unsigned int)v7, v16);
    std::string::resize(&v20, (unsigned int)v18, 0);
    v9 = &v20;
    if ( *((_QWORD *)&v21 + 1) > 0xFu )
      LODWORD(v9) = v20;
    v10 = base64encodeA(*a2, *((_DWORD *)a2 + 2) - *(_DWORD *)a2, (_DWORD)v9, v21, (__int64)&v18);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x49, v11, (const char *)(unsigned int)v10, v17);
    std::string::resize(&v20, (unsigned int)(v18 - 1), 0);
    v6 = v20;
    v22 = v20;
    v5 = v21;
    v23 = v21;
    *(_QWORD *)&v21 = 0;
    *((_QWORD *)&v21 + 1) = 15;
    LOBYTE(v20) = 0;
    std::string::~string(&v20);
  }
  v12 = operator new(0x20u);
  *v12 = v6;
  v12[1] = v5;
  *(_QWORD *)&v23 = 0;
  *((_QWORD *)&v23 + 1) = 15;
  LOBYTE(v22) = 0;
  v13 = *(_BYTE *)a1;
  *(_BYTE *)a1 = 3;
  LOBYTE(v18) = v13;
  v14 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = v12;
  v19 = v14;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
    &v19,
    v13);
  std::string::~string(&v22);
  return a1;
}

```

## disassembly

```asm
0x180012b38  mov     rax, rsp
0x180012b3b  mov     [rax+18h], rbx
0x180012b3f  push    rbp
0x180012b40  push    rsi
0x180012b41  push    rdi
0x180012b42  lea     rbp, [rax-5Fh]
0x180012b46  sub     rsp, 0B0h
0x180012b4d  movaps  xmmword ptr [rax-28h], xmm6
0x180012b51  movaps  xmmword ptr [rax-38h], xmm7
0x180012b55  mov     rax, cs:__security_cookie
0x180012b5c  xor     rax, rsp
0x180012b5f  mov     [rbp+57h+var_40], rax
0x180012b63  mov     rsi, rdx
0x180012b66  mov     rdi, rcx
0x180012b69  mov     byte ptr [rcx], 0
0x180012b6c  xor     eax, eax
0x180012b6e  mov     [rcx+8], rax
0x180012b72  mov     rcx, [rdx]
0x180012b75  xorps   xmm0, xmm0
0x180012b78  lea     ebx, [rax+0Fh]
0x180012b7b  cmp     rcx, [rdx+8]
0x180012b7f  jnz     short loc_180012B9D
0x180012b81  movups  [rbp+57h+var_60], xmm0
0x180012b85  mov     qword ptr [rbp+57h+var_50], rax
0x180012b89  mov     qword ptr [rbp+57h+var_50+8], rbx
0x180012b8d  mov     byte ptr [rbp+57h+var_60], al
0x180012b90  movups  xmm6, [rbp+57h+var_50]
0x180012b94  movups  xmm7, [rbp+57h+var_60]
0x180012b98  jmp     loc_180012C55
0x180012b9d  movups  [rbp+57h+var_80], xmm0
0x180012ba1  mov     qword ptr [rbp+57h+var_70], rax
0x180012ba5  mov     qword ptr [rbp+57h+var_70+8], rbx
0x180012ba9  mov     byte ptr [rbp+57h+var_80], al
0x180012bac  mov     [rbp+57h+var_90], 0
0x180012bb3  mov     edx, [rdx+8]
0x180012bb6  sub     edx, [rsi]
0x180012bb8  lea     rax, [rbp+57h+var_90]
0x180012bbc  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180012bc1  xor     r9d, r9d
0x180012bc4  xor     r8d, r8d
0x180012bc7  call    base64encodeA
0x180012bcc  mov     rcx, [rbp+5Fh]; this
0x180012bd0  test    eax, eax
0x180012bd2  js      loc_180012CD7
0x180012bd8  mov     edx, [rbp+57h+var_90]
0x180012bdb  xor     r8d, r8d
0x180012bde  lea     rcx, [rbp+57h+var_80]
0x180012be2  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x180012be7  lea     r8, [rbp+57h+var_80]
0x180012beb  cmp     qword ptr [rbp+57h+var_70+8], rbx
0x180012bef  cmova   r8, qword ptr [rbp+57h+var_80]
0x180012bf4  mov     edx, [rsi+8]
0x180012bf7  sub     edx, [rsi]
0x180012bf9  lea     rax, [rbp+57h+var_90]
0x180012bfd  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180012c02  mov     r9d, dword ptr [rbp+57h+var_70]
0x180012c06  mov     rcx, [rsi]
0x180012c09  call    base64encodeA
0x180012c0e  mov     rcx, [rbp+5Fh]; this
0x180012c12  test    eax, eax
0x180012c14  js      loc_180012CC9
0x180012c1a  mov     edx, [rbp+57h+var_90]
0x180012c1d  dec     edx
0x180012c1f  xor     r8d, r8d
0x180012c22  lea     rcx, [rbp+57h+var_80]
0x180012c26  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x180012c2b  movups  xmm7, [rbp+57h+var_80]
0x180012c2f  movups  [rbp+57h+var_60], xmm7
0x180012c33  movups  xmm6, [rbp+57h+var_70]
0x180012c37  movups  [rbp+57h+var_50], xmm6
0x180012c3b  mov     qword ptr [rbp+57h+var_70], 0
0x180012c43  mov     qword ptr [rbp+57h+var_70+8], rbx
0x180012c47  mov     byte ptr [rbp+57h+var_80], 0
0x180012c4b  lea     rcx, [rbp+57h+var_80]
0x180012c4f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180012c54  nop
0x180012c55  mov     ecx, 20h ; ' '; Size
0x180012c5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012c5f  movups  xmmword ptr [rax], xmm7
0x180012c62  movups  xmmword ptr [rax+10h], xmm6
0x180012c66  mov     qword ptr [rbp+57h+var_50], 0
0x180012c6e  mov     qword ptr [rbp+57h+var_50+8], rbx
0x180012c72  mov     byte ptr [rbp+57h+var_60], 0
0x180012c76  mov     dl, [rdi]
0x180012c78  mov     byte ptr [rdi], 3
0x180012c7b  mov     byte ptr [rbp+57h+var_90], dl
0x180012c7e  mov     rcx, [rdi+8]
0x180012c82  mov     [rdi+8], rax
0x180012c86  mov     [rbp+57h+var_88], rcx
0x180012c8a  lea     rcx, [rbp+57h+var_88]
0x180012c8e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180012c93  nop
0x180012c94  lea     rcx, [rbp+57h+var_60]
0x180012c98  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180012c9d  mov     rax, rdi
0x180012ca0  mov     rcx, [rbp+57h+var_40]
0x180012ca4  xor     rcx, rsp; StackCookie
0x180012ca7  call    __security_check_cookie
0x180012cac  lea     r11, [rsp+0C0h+var_10]
0x180012cb4  mov     rbx, [r11+30h]
0x180012cb8  movaps  xmm6, xmmword ptr [r11-10h]
0x180012cbd  movaps  xmm7, xmmword ptr [r11-20h]
0x180012cc2  mov     rsp, r11
0x180012cc5  pop     rdi
0x180012cc6  pop     rsi
0x180012cc7  pop     rbp
0x180012cc8  retn
0x180012cc9  mov     r9d, eax; char *
0x180012ccc  mov     edx, 49h ; 'I'; void *
0x180012cd1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012cd7  mov     r9d, eax; char *
0x180012cda  mov     edx, 46h ; 'F'; void *
0x180012cdf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
