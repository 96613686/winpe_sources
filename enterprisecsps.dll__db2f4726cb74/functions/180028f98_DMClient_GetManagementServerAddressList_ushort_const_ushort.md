# DMClient::GetManagementServerAddressList(ushort const *,ushort * *)

- ea: `0x180028f98`
- end: `0x180029236`
- name: `?GetManagementServerAddressList@DMClient@@YAJPEBGPEAPEAG@Z`
- size: `670`
- prototype: `__int64 __fastcall(DMClient *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180037b70`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x18000f0c8`
- `0x180019fd8`
- `0x18002031c`
- `0x180025824`
- `0x180028f98`
- `0x18002dd24`

## import_xrefs

- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x180029095`
- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x180029095`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x18002913d`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x180029206`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x18002913d`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x180029206`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1800290c7`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x1800290c7`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x180029037`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x180029037`
- `DMCmnUtils!CopyString` at `0x1800291a2`
- `DMCmnUtils!CopyString` at `0x1800291c5`
- `DMCmnUtils!CopyString` at `0x1800291a2`
- `DMCmnUtils!CopyString` at `0x1800291c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall DMClient::GetManagementServerAddressList(
        DMClient *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // edi
  int v6; // eax
  __int64 v7; // rax
  _WORD *v9; // rax
  int v10; // eax
  const unsigned __int16 *v11; // rax
  int v12; // [rsp+20h] [rbp-2A8h]
  int AcctInfo; // [rsp+30h] [rbp-298h] BYREF
  _QWORD *v14; // [rsp+38h] [rbp-290h] BYREF
  unsigned __int16 **v15; // [rsp+40h] [rbp-288h] BYREF
  _QWORD v16[4]; // [rsp+48h] [rbp-280h] BYREF
  char v17; // [rsp+68h] [rbp-260h]
  _BYTE v18[16]; // [rsp+70h] [rbp-258h] BYREF
  __int64 v19; // [rsp+80h] [rbp-248h]
  _BYTE v20[32]; // [rsp+90h] [rbp-238h] BYREF
  int v21; // [rsp+B0h] [rbp-218h] BYREF
  _BYTE v22[516]; // [rsp+B4h] [rbp-214h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v15 = a2;
  AcctInfo = 0;
  memset_0(v22, 0, 0x1FCu);
  v21 = 512;
  v16[1] = &AcctInfo;
  v16[2] = &v15;
  v16[3] = &v21;
  v17 = 1;
  if ( !a2 )
  {
    v5 = -2147024809;
    AcctInfo = -2147024809;
LABEL_17:
    OmaDmFreeAcctInfo(&v21);
    return v5;
  }
  *a2 = 0;
  v6 = OmaDmSetNodeValuePresence(56, &v21, 0xFFFFFFFFLL);
  v5 = v6;
  AcctInfo = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
      (const char *)(unsigned int)v6,
      v12);
    goto LABEL_17;
  }
  v16[0] = L":0";
  v14 = v16;
  AcctInfo = OmaDmGetAcctInfo(this, 1, &v21);
  if ( AcctInfo < 0 || (AcctInfo = OmaDmGetValueFromStruct(56, &v21, 0xFFFFFFFFLL, &v14, 0), AcctInfo < 0) || !*v14 )
    v14 = v16;
  std::wstring::wstring(v20, *v14);
  v7 = std::wstring::rfind(v20);
  if ( v7 == -1 )
  {
    AcctInfo = -2147418113;
    std::wstring::~wstring(v20);
    v17 = 0;
    OmaDmFreeAcctInfo(&v21);
    return 2147549183LL;
  }
  std::wstring::wstring(v18, v20, 0, v7);
  if ( v19 == 2
    && (v9 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18), *v9 == 60)
    && v9[1] == 62 )
  {
    v10 = CopyString(&Class, 0xFFFFFFFF, v15);
  }
  else
  {
    v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    v10 = CopyString(v11, 0xFFFFFFFF, v15);
  }
  AcctInfo = v10;
  std::wstring::~wstring(v18);
  std::wstring::~wstring(v20);
  v5 = AcctInfo;
  if ( v17 )
    goto LABEL_17;
  return v5;
}

```

## disassembly

```asm
0x180028f98  mov     [rsp+arg_10], rsi
0x180028f9d  push    rdi
0x180028f9e  sub     rsp, 2C0h
0x180028fa5  mov     rax, cs:__security_cookie
0x180028fac  xor     rax, rsp
0x180028faf  mov     [rsp+2C8h+var_10], rax
0x180028fb7  mov     rdi, rdx
0x180028fba  mov     rsi, rcx
0x180028fbd  mov     [rsp+2C8h+var_288], rdx
0x180028fc2  mov     [rsp+2C8h+var_298], 0
0x180028fca  xor     edx, edx; Val
0x180028fcc  mov     r8d, 1FCh; Size
0x180028fd2  lea     rcx, [rsp+2C8h+var_214]; void *
0x180028fda  call    memset_0
0x180028fdf  mov     [rsp+2C8h+var_218], 200h
0x180028fea  lea     rax, [rsp+2C8h+var_298]
0x180028fef  mov     [rsp+2C8h+var_278], rax
0x180028ff4  lea     rax, [rsp+2C8h+var_288]
0x180028ff9  mov     [rsp+2C8h+var_270], rax
0x180028ffe  lea     rax, [rsp+2C8h+var_218]
0x180029006  mov     [rsp+2C8h+var_268], rax
0x18002900b  mov     [rsp+2C8h+var_260], 1
0x180029010  test    rdi, rdi
0x180029013  jnz     short loc_180029020
0x180029015  mov     edi, 80070057h
0x18002901a  mov     [rsp+2C8h+var_298], edi
0x18002901e  jmp     short loc_18002906A
0x180029020  mov     qword ptr [rdi], 0
0x180029027  or      r8d, 0FFFFFFFFh
0x18002902b  lea     rdx, [rsp+2C8h+var_218]
0x180029033  lea     ecx, [r8+39h]
0x180029037  call    cs:__imp_OmaDmSetNodeValuePresence
0x18002903e  nop     dword ptr [rax+rax+00h]
0x180029043  mov     edi, eax
0x180029045  mov     [rsp+2C8h+var_298], eax
0x180029049  test    eax, eax
0x18002904b  jns     short loc_18002906F
0x18002904d  mov     rcx, [rsp+2C8h]; this
0x180029055  mov     r9d, eax; char *
0x180029058  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002905f  mov     edx, 606h; void *
0x180029064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029069  nop
0x18002906a  jmp     loc_1800291FE
0x18002906f  lea     rax, a0_1; ":0"
0x180029076  mov     [rsp+2C8h+var_280], rax
0x18002907b  lea     rax, [rsp+2C8h+var_280]
0x180029080  mov     [rsp+2C8h+var_290], rax
0x180029085  lea     r8, [rsp+2C8h+var_218]
0x18002908d  mov     edx, 1
0x180029092  mov     rcx, rsi
0x180029095  call    cs:__imp_OmaDmGetAcctInfo
0x18002909c  nop     dword ptr [rax+rax+00h]
0x1800290a1  mov     [rsp+2C8h+var_298], eax
0x1800290a5  test    eax, eax
0x1800290a7  js      short loc_1800290E6
0x1800290a9  mov     qword ptr [rsp+2C8h+var_2A8], 0
0x1800290b2  lea     r9, [rsp+2C8h+var_290]
0x1800290b7  or      r8d, 0FFFFFFFFh
0x1800290bb  lea     rdx, [rsp+2C8h+var_218]
0x1800290c3  lea     ecx, [r8+39h]
0x1800290c7  call    cs:__imp_OmaDmGetValueFromStruct
0x1800290ce  nop     dword ptr [rax+rax+00h]
0x1800290d3  mov     [rsp+2C8h+var_298], eax
0x1800290d7  test    eax, eax
0x1800290d9  js      short loc_1800290E6
0x1800290db  mov     rax, [rsp+2C8h+var_290]
0x1800290e0  cmp     qword ptr [rax], 0
0x1800290e4  jnz     short loc_1800290F0
0x1800290e6  lea     rax, [rsp+2C8h+var_280]
0x1800290eb  mov     [rsp+2C8h+var_290], rax
0x1800290f0  mov     rdx, [rsp+2C8h+var_290]
0x1800290f5  mov     rdx, [rdx]
0x1800290f8  lea     rcx, [rsp+2C8h+var_238]
0x180029100  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029105  nop
0x180029106  lea     rcx, [rsp+2C8h+var_238]
0x18002910e  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::rfind(ushort const * const,unsigned __int64)
0x180029113  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029117  jnz     short loc_180029150
0x180029119  mov     edi, 8000FFFFh
0x18002911e  mov     [rsp+2C8h+var_298], edi
0x180029122  lea     rcx, [rsp+2C8h+var_238]
0x18002912a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002912f  nop
0x180029130  mov     [rsp+2C8h+var_260], 0
0x180029135  lea     rcx, [rsp+2C8h+var_218]
0x18002913d  call    cs:__imp_OmaDmFreeAcctInfo
0x180029144  nop     dword ptr [rax+rax+00h]
0x180029149  mov     eax, edi
0x18002914b  jmp     loc_180029214
0x180029150  mov     r9, rax
0x180029153  xor     r8d, r8d
0x180029156  lea     rdx, [rsp+2C8h+var_238]
0x18002915e  lea     rcx, [rsp+2C8h+var_258]
0x180029163  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x180029168  nop
0x180029169  cmp     [rsp+2C8h+var_248], 2
0x180029172  jnz     short loc_1800291B0
0x180029174  lea     rcx, [rsp+2C8h+var_258]
0x180029179  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002917e  mov     ecx, 3Ch ; '<'
0x180029183  cmp     cx, [rax]
0x180029186  jnz     short loc_1800291B0
0x180029188  mov     ecx, 3Eh ; '>'
0x18002918d  cmp     cx, [rax+2]
0x180029191  jnz     short loc_1800291B0
0x180029193  mov     r8, [rsp+2C8h+var_288]
0x180029198  or      edx, 0FFFFFFFFh
0x18002919b  lea     rcx, Class
0x1800291a2  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800291a9  nop     dword ptr [rax+rax+00h]
0x1800291ae  jmp     short loc_1800291D2
0x1800291b0  lea     rcx, [rsp+2C8h+var_258]
0x1800291b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800291ba  mov     r8, [rsp+2C8h+var_288]
0x1800291bf  or      edx, 0FFFFFFFFh
0x1800291c2  mov     rcx, rax
0x1800291c5  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800291cc  nop     dword ptr [rax+rax+00h]
0x1800291d1  nop
0x1800291d2  mov     [rsp+2C8h+var_298], eax
0x1800291d6  lea     rcx, [rsp+2C8h+var_258]
0x1800291db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800291e0  nop
0x1800291e1  lea     rcx, [rsp+2C8h+var_238]
0x1800291e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800291ee  nop
0x1800291ef  jmp     short loc_1800291F3
0x1800291f1  jmp     short $+2
0x1800291f3  mov     edi, [rsp+2C8h+var_298]
0x1800291f7  cmp     [rsp+2C8h+var_260], 0
0x1800291fc  jz      short loc_180029212
0x1800291fe  lea     rcx, [rsp+2C8h+var_218]
0x180029206  call    cs:__imp_OmaDmFreeAcctInfo
0x18002920d  nop     dword ptr [rax+rax+00h]
0x180029212  mov     eax, edi
0x180029214  mov     rcx, [rsp+2C8h+var_10]
0x18002921c  xor     rcx, rsp; StackCookie
0x18002921f  call    __security_check_cookie
0x180029224  mov     rsi, [rsp+2C8h+arg_10]
0x18002922c  add     rsp, 2C0h
0x180029233  pop     rdi
0x180029234  retn
```
