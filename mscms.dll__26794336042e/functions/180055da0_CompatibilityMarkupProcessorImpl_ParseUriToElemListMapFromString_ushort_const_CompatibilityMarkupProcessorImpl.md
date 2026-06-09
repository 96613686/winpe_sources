# CompatibilityMarkupProcessorImpl::ParseUriToElemListMapFromString(ushort const *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *)

- ea: `0x180055da0`
- end: `0x18005604e`
- name: `?ParseUriToElemListMapFromString@CompatibilityMarkupProcessorImpl@@AEAAJPEBGPEBU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEBU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180010670`

## callees

- `0x18001aa80`
- `0x18001b5d8`
- `0x18001d600`
- `0x18001f5b0`
- `0x18002e5f0`
- `0x18002eac0`
- `0x18002f324`
- `0x180055094`
- `0x18005524c`
- `0x180055714`
- `0x180055da0`
- `0x180056a58`
- `0x180056ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055e61`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055e61`
- `OLEAUT32!__imp_SysFreeString` at `0x180055f89`
- `OLEAUT32!__imp_SysFreeString` at `0x180055f95`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fa1`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fab`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fe1`
- `OLEAUT32!__imp_SysFreeString` at `0x180055ff3`
- `OLEAUT32!__imp_SysFreeString` at `0x180056008`
- `OLEAUT32!__imp_SysFreeString` at `0x180056015`
- `OLEAUT32!__imp_SysFreeString` at `0x180055f89`
- `OLEAUT32!__imp_SysFreeString` at `0x180055f95`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fa1`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fab`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fe1`
- `OLEAUT32!__imp_SysFreeString` at `0x180055ff3`
- `OLEAUT32!__imp_SysFreeString` at `0x180056008`
- `OLEAUT32!__imp_SysFreeString` at `0x180056015`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CompatibilityMarkupProcessorImpl::ParseUriToElemListMapFromString(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int16 *v5; // rdi
  __int64 v6; // rax
  const unsigned __int16 *v7; // r15
  const unsigned __int16 *v8; // rbx
  __int64 v9; // r14
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // r13
  __int64 v13; // rsi
  int v14; // eax
  int v15; // eax
  unsigned int v16; // edi
  BSTR v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 pExceptionObject; // [rsp+28h] [rbp-D8h] BYREF
  BSTR v20; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h]
  _DWORD v24[104]; // [rsp+50h] [rbp-B0h] BYREF

  pExceptionObject = a4;
  v23 = a3;
  v5 = a2;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = &a2[v6];
  while ( v5 != v7 )
  {
    v8 = v5;
    do
    {
      if ( !(unsigned __int8)anonymous_namespace_::is_attr_delim(*v8) )
        break;
      ++v8;
    }
    while ( v8 != v7 );
    v5 = (unsigned __int16 *)v8;
    if ( v8 != v7 )
    {
      do
      {
        if ( (unsigned __int8)anonymous_namespace_::is_attr_delim(*v5) )
          break;
        ++v5;
      }
      while ( v5 != v7 );
      if ( v8 != v5 )
      {
        v9 = v5 - v8;
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&Str, v9, v8);
        v10 = Str;
        v11 = wcschr(Str, 0x3Au);
        v12 = v11;
        if ( !v11 )
        {
          SysFreeString(v10);
          return 2147745801LL;
        }
        v13 = v11 - v10;
        if ( (_DWORD)v13 + 1 == (_DWORD)v9 )
        {
          v16 = -2147221495;
          goto LABEL_26;
        }
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v20, v13, v10);
        v14 = CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>::Find(pExceptionObject, &v20);
        if ( v14 == -1 )
        {
          SysFreeString(v20);
          v16 = -2147221497;
          goto LABEL_26;
        }
        ATL::CComBSTR::CComBSTR(
          (ATL::CComBSTR *)&v18,
          (const struct ATL::CComBSTR *)(16LL * v14 + pExceptionObject + 8));
        if ( (unsigned int)CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Find(v23, &v18) == -1 )
        {
          SysFreeString(v18);
          SysFreeString(v20);
          v16 = -2147221496;
LABEL_26:
          SysFreeString(v10);
          return v16;
        }
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v9 - v13 - 1, v12 + 1);
        v15 = CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>::Find(
                a5,
                &v18);
        if ( v15 == -1 )
        {
          CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>::Vector<ATL::CComBSTR,50>(v24);
          CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>::Add((__int64)v24, (ATL::CComBSTR *)&bstrString);
          CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>::SetValue(
            a5,
            &v18,
            v24);
          `eh vector destructor iterator'((char *)v24, 8, 50, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          if ( v15 < 0 || v15 >= *(_DWORD *)(a5 + 10400) )
          {
            LODWORD(pExceptionObject) = -2147024809;
            throw (ATL::CAtlException *)&pExceptionObject;
          }
          CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>::Add(
            a5 + 416LL * v15 + 8,
            (ATL::CComBSTR *)&bstrString);
        }
        SysFreeString(bstrString);
        SysFreeString(v18);
        SysFreeString(v20);
        SysFreeString(v10);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180055da0  mov     [rsp-8+arg_0], rbx
0x180055da5  push    rbp
0x180055da6  push    rsi
0x180055da7  push    rdi
0x180055da8  push    r12
0x180055daa  push    r13
0x180055dac  push    r14
0x180055dae  push    r15
0x180055db0  lea     rbp, [rsp-100h]
0x180055db8  sub     rsp, 200h
0x180055dbf  mov     rax, cs:__security_cookie
0x180055dc6  xor     rax, rsp
0x180055dc9  mov     [rbp+130h+var_40], rax
0x180055dd0  mov     [rsp+230h+pExceptionObject], r9
0x180055dd5  mov     [rsp+230h+var_1E8], r8
0x180055dda  mov     rdi, rdx
0x180055ddd  mov     r12, [rbp+130h+arg_20]
0x180055de4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055de8  xor     esi, esi
0x180055dea  inc     rax
0x180055ded  cmp     [rdx+rax*2], si
0x180055df1  jnz     short loc_180055DEA
0x180055df3  lea     r15, [rdx+rax*2]
0x180055df7  cmp     rdi, r15
0x180055dfa  jz      loc_180056022
0x180055e00  mov     rbx, rdi
0x180055e03  movzx   ecx, word ptr [rbx]
0x180055e06  call    _anonymous_namespace___is_attr_delim
0x180055e0b  test    al, al
0x180055e0d  jz      short loc_180055E18
0x180055e0f  add     rbx, 2
0x180055e13  cmp     rbx, r15
0x180055e16  jnz     short loc_180055E03
0x180055e18  mov     rdi, rbx
0x180055e1b  cmp     rbx, r15
0x180055e1e  jz      short loc_180055DF7
0x180055e20  movzx   ecx, word ptr [rdi]
0x180055e23  call    _anonymous_namespace___is_attr_delim
0x180055e28  test    al, al
0x180055e2a  jnz     short loc_180055E35
0x180055e2c  add     rdi, 2
0x180055e30  cmp     rdi, r15
0x180055e33  jnz     short loc_180055E20
0x180055e35  cmp     rbx, rdi
0x180055e38  jz      short loc_180055DF7
0x180055e3a  mov     r14, rdi
0x180055e3d  sub     r14, rbx
0x180055e40  sar     r14, 1
0x180055e43  mov     r8, rbx; unsigned __int16 *
0x180055e46  mov     edx, r14d; int
0x180055e49  lea     rcx, [rsp+230h+Str]; this
0x180055e4e  call    ??0CComBSTR@ATL@@QEAA@HPEBG@Z; ATL::CComBSTR::CComBSTR(int,ushort const *)
0x180055e53  nop
0x180055e54  mov     edx, 3Ah ; ':'; Ch
0x180055e59  mov     rbx, [rsp+230h+Str]
0x180055e5e  mov     rcx, rbx; Str
0x180055e61  call    cs:__imp_wcschr
0x180055e67  mov     r13, rax
0x180055e6a  test    rax, rax
0x180055e6d  jz      loc_180056012
0x180055e73  mov     rsi, rax
0x180055e76  sub     rsi, rbx
0x180055e79  sar     rsi, 1
0x180055e7c  lea     ecx, [rsi+1]
0x180055e7f  cmp     ecx, r14d
0x180055e82  jz      loc_180056000
0x180055e88  mov     r8, rbx; unsigned __int16 *
0x180055e8b  mov     edx, esi; int
0x180055e8d  lea     rcx, [rsp+230h+var_200]; this
0x180055e92  call    ??0CComBSTR@ATL@@QEAA@HPEBG@Z; ATL::CComBSTR::CComBSTR(int,ushort const *)
0x180055e97  nop
0x180055e98  lea     rdx, [rsp+230h+var_200]
0x180055e9d  mov     rcx, [rsp+230h+pExceptionObject]
0x180055ea2  call    ?Find@?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@QEBAHAEBVCComBSTR@ATL@@@Z; CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>::Find(ATL::CComBSTR const &)
0x180055ea7  cmp     eax, 0FFFFFFFFh
0x180055eaa  jz      loc_180055FEE
0x180055eb0  cdqe
0x180055eb2  shl     rax, 4
0x180055eb6  mov     rdx, [rsp+230h+pExceptionObject]
0x180055ebb  add     rdx, 8
0x180055ebf  add     rdx, rax; struct ATL::CComBSTR *
0x180055ec2  lea     rcx, [rsp+230h+var_210]; this
0x180055ec7  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x180055ecc  nop
0x180055ecd  lea     rdx, [rsp+230h+var_210]
0x180055ed2  mov     rcx, [rsp+230h+var_1E8]
0x180055ed7  call    ?Find@?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@QEBAHAEBVCComBSTR@ATL@@@Z; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Find(ATL::CComBSTR const &)
0x180055edc  cmp     eax, 0FFFFFFFFh
0x180055edf  jz      loc_180055FD0
0x180055ee5  lea     r8, [r13+2]; unsigned __int16 *
0x180055ee9  sub     r14d, esi
0x180055eec  lea     edx, [r14-1]; int
0x180055ef0  lea     rcx, [rsp+230h+bstrString]; this
0x180055ef5  call    ??0CComBSTR@ATL@@QEAA@HPEBG@Z; ATL::CComBSTR::CComBSTR(int,ushort const *)
0x180055efa  nop
0x180055efb  lea     rdx, [rsp+230h+var_210]
0x180055f00  mov     rcx, r12
0x180055f03  call    ?Find@?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@QEBAHAEBVCComBSTR@ATL@@@Z; CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>::Find(ATL::CComBSTR const &)
0x180055f08  cmp     eax, 0FFFFFFFFh
0x180055f0b  jnz     short loc_180055F59
0x180055f0d  lea     rcx, [rsp+230h+var_1E0]
0x180055f12  call    ??0?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>::Vector<ATL::CComBSTR,50>(void)
0x180055f17  nop
0x180055f18  lea     rdx, [rsp+230h+bstrString]
0x180055f1d  lea     rcx, [rsp+230h+var_1E0]
0x180055f22  call    ?Add@?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@QEAAXAEBVCComBSTR@ATL@@@Z; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>::Add(ATL::CComBSTR const &)
0x180055f27  lea     r8, [rsp+230h+var_1E0]
0x180055f2c  lea     rdx, [rsp+230h+var_210]
0x180055f31  mov     rcx, r12
0x180055f34  call    ?SetValue@?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@QEAAXAEBVCComBSTR@ATL@@AEBU?$Vector@VCComBSTR@ATL@@$0DC@@2@@Z; CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>::SetValue(ATL::CComBSTR const &,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50> const &)
0x180055f39  nop
0x180055f3a  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055f41  mov     edx, 8; unsigned __int64
0x180055f46  lea     r8d, [rdx+2Ah]; unsigned __int64
0x180055f4a  lea     rcx, [rsp+230h+var_1E0]; void *
0x180055f4f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055f54  nop
0x180055f55  xor     esi, esi
0x180055f57  jmp     short loc_180055F84
0x180055f59  xor     esi, esi
0x180055f5b  test    eax, eax
0x180055f5d  js      short loc_180055FB6
0x180055f5f  cmp     eax, [r12+28A0h]
0x180055f67  jge     short loc_180055FB6
0x180055f69  cdqe
0x180055f6b  imul    rcx, rax, 1A0h
0x180055f72  add     rcx, 8
0x180055f76  add     rcx, r12
0x180055f79  lea     rdx, [rsp+230h+bstrString]
0x180055f7e  call    ?Add@?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@QEAAXAEBVCComBSTR@ATL@@@Z; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>::Add(ATL::CComBSTR const &)
0x180055f83  nop
0x180055f84  mov     rcx, [rsp+230h+bstrString]; bstrString
0x180055f89  call    cs:__imp_SysFreeString
0x180055f8f  nop
0x180055f90  mov     rcx, [rsp+230h+var_210]; bstrString
0x180055f95  call    cs:__imp_SysFreeString
0x180055f9b  nop
0x180055f9c  mov     rcx, [rsp+230h+var_200]; bstrString
0x180055fa1  call    cs:__imp_SysFreeString
0x180055fa7  nop
0x180055fa8  mov     rcx, rbx; bstrString
0x180055fab  call    cs:__imp_SysFreeString
0x180055fb1  jmp     loc_180055DF7
0x180055fb6  mov     dword ptr [rsp+230h+pExceptionObject], 80070057h
0x180055fbe  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180055fc5  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180055fca  call    _CxxThrowException_0
0x180055fd0  mov     rcx, [rsp+230h+var_210]; bstrString
0x180055fd5  call    cs:__imp_SysFreeString
0x180055fdb  nop
0x180055fdc  mov     rcx, [rsp+230h+var_200]; bstrString
0x180055fe1  call    cs:__imp_SysFreeString
0x180055fe7  mov     edi, 80040008h
0x180055fec  jmp     short loc_180056005
0x180055fee  mov     rcx, [rsp+230h+var_200]; bstrString
0x180055ff3  call    cs:__imp_SysFreeString
0x180055ff9  mov     edi, 80040007h
0x180055ffe  jmp     short loc_180056005
0x180056000  mov     edi, 80040009h
0x180056005  mov     rcx, rbx; bstrString
0x180056008  call    cs:__imp_SysFreeString
0x18005600e  mov     eax, edi
0x180056010  jmp     short loc_180056024
0x180056012  mov     rcx, rbx; bstrString
0x180056015  call    cs:__imp_SysFreeString
0x18005601b  mov     eax, 80040009h
0x180056020  jmp     short loc_180056024
0x180056022  xor     eax, eax
0x180056024  mov     rcx, [rbp+130h+var_40]
0x18005602b  xor     rcx, rsp; StackCookie
0x18005602e  call    __security_check_cookie
0x180056033  mov     rbx, [rsp+230h+arg_0]
0x18005603b  add     rsp, 200h
0x180056042  pop     r15
0x180056044  pop     r14
0x180056046  pop     r13
0x180056048  pop     r12
0x18005604a  pop     rdi
0x18005604b  pop     rsi
0x18005604c  pop     rbp
0x18005604d  retn
```
