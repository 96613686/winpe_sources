# CXMLValue::ScWriteToBSTR(ushort * *)

- ea: `0x18001fed0`
- end: `0x180020244`
- name: `?ScWriteToBSTR@CXMLValue@@QEBA?AVSC@mmcerror@@PEAPEAG@Z`
- size: `884`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001f080`
- `0x18001f9e0`
- `0x180020508`
- `0x1800234d0`

## callees

- `0x18001fed0`
- `0x18002bfb0`
- `0x180041344`
- `0x180041c64`
- `0x180134540`
- `0x18013f010`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18001ff0b`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18001ff33`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18001ff0b`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18001ff33`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18001ff82`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020070`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18002011b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18001ff82`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180020070`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18002011b`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18001ff8e`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18001ffce`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18001ff8e`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18001ffce`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18001ff42`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180020195`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800201dd`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18001ff42`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180020195`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800201dd`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18001ff1d`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18001ff1d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18001ff57`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18002007a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180020125`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800201aa`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800201f2`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18001ff57`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18002007a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180020125`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800201aa`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800201f2`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18001ff4d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18001ffa4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800201a0`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800201e8`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18001ff4d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18001ffa4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800201a0`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800201e8`
- `ole32!CoTaskMemFree` at `0x180020007`
- `ole32!CoTaskMemFree` at `0x180020007`
- `ole32!StringFromCLSID` at `0x18001ffe2`
- `ole32!StringFromCLSID` at `0x18001ffe2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fff9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fff9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff99`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fff0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff99`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fff0`

## string_xrefs

- `0x18001ff12`: `CXMLValue::ScWriteToBSTR`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
OLECHAR *__fastcall CXMLValue::ScWriteToBSTR(__int64 a1, OLECHAR *a2, BSTR *a3)
{
  int v6; // edx
  const struct mmcerror::SC *v7; // rdx
  const OLECHAR *v9; // rdi
  BSTR v10; // rax
  __int64 v11; // r9
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  unsigned int v14; // eax
  _QWORD *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  BSTR bstrString; // [rsp+20h] [rbp-79h] BYREF
  _BYTE v19[24]; // [rsp+28h] [rbp-71h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v21[40]; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 v22[40]; // [rsp+70h] [rbp-29h] BYREF

  lpsz = a2;
  mmcerror::SC::SC((mmcerror::SC *)v19, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v19, L"CXMLValue::ScWriteToBSTR");
  v6 = -2147024809;
  if ( a3 )
    v6 = 0;
  mmcerror::SC::SC((mmcerror::SC *)v21, v6);
  mmcerror::SC::operator=(v19, v21);
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v19) )
  {
    mmcerror::SC::SC((mmcerror::SC *)a2, (const struct mmcerror::SC *)v19);
  }
  else
  {
    *a3 = 0;
    bstrString = 0;
    if ( *(_DWORD *)a1 != 12 )
    {
      switch ( *(_DWORD *)a1 )
      {
        case 0:
          v11 = **(unsigned int **)(a1 + 8);
          goto LABEL_16;
        case 1:
        case 7:
          v12 = StringCchPrintfW(v22, 0x28u, L"%u", **(unsigned int **)(a1 + 8), bstrString);
          goto LABEL_18;
        case 2:
          v12 = StringCchPrintfW(v22, 0x28u, L"0x%02.2x", **(unsigned __int8 **)(a1 + 8), bstrString);
          goto LABEL_18;
        case 3:
          v11 = (unsigned int)**(__int16 **)(a1 + 8);
LABEL_16:
          v12 = StringCchPrintfW(v22, 0x28u, L"%d", v11, bstrString);
          goto LABEL_18;
        case 4:
          v12 = StringCchPrintfW(v22, 0x28u, L"0x%04.4x", **(unsigned int **)(a1 + 8), bstrString);
LABEL_18:
          mmcerror::SC::operator=(v19, v12);
          if ( (unsigned __int8)mmcerror::SC::operator bool(v19) )
            goto LABEL_12;
          goto LABEL_29;
        case 5:
          v13 = L"true";
          if ( !**(_DWORD **)(a1 + 8) )
            v13 = L"false";
          goto LABEL_24;
        case 6:
          v13 = L"true";
          if ( !**(_BYTE **)(a1 + 8) )
            v13 = L"false";
LABEL_24:
          ATL::CComBSTR::operator=(&bstrString, v13);
          goto LABEL_11;
        case 8:
          v14 = StringCchPrintfW(v22, 0x28u, L"%d", **(unsigned int **)(a1 + 8));
          mmcerror::SC::operator=(v19, v14);
          if ( (unsigned __int8)mmcerror::SC::operator bool(v19) )
            goto LABEL_12;
LABEL_29:
          ATL::CComBSTR::operator=(&bstrString, v22);
          goto LABEL_11;
        case 9:
          ATL::CComBSTR::operator=(&bstrString, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL));
          goto LABEL_11;
        case 0xA:
        case 0xB:
          v15 = *(_QWORD **)(a1 + 8);
          if ( v15[3] < 8u )
            v15 = (_QWORD *)(a1 + 8);
          ATL::CComBSTR::operator=(&bstrString, *v15);
          goto LABEL_11;
        case 0xD:
          v16 = ScEncodeBinary(v21, &bstrString, *(_QWORD *)(a1 + 8));
          mmcerror::SC::operator=(v19, v16);
          mmcerror::SC::~SC((mmcerror::SC *)v21);
          if ( (unsigned __int8)mmcerror::SC::operator bool(v19) )
            goto LABEL_12;
          goto LABEL_11;
        case 0xE:
          v17 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, BSTR *))(**(_QWORD **)(a1 + 8) + 8LL))(
                  *(_QWORD *)(a1 + 8),
                  v21,
                  &bstrString);
          mmcerror::SC::operator=(v19, v17);
          mmcerror::SC::~SC((mmcerror::SC *)v21);
          if ( (unsigned __int8)mmcerror::SC::operator bool(v19) )
            goto LABEL_12;
          goto LABEL_11;
        default:
          v7 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v19, 2147500033LL);
          goto LABEL_7;
      }
    }
    lpsz = 0;
    StringFromCLSID(*(const IID *const *)(a1 + 8), &lpsz);
    v9 = lpsz;
    SysFreeString(bstrString);
    bstrString = SysAllocString(v9);
    CoTaskMemFree(lpsz);
LABEL_11:
    v10 = bstrString;
    bstrString = 0;
    *a3 = v10;
LABEL_12:
    v7 = (const struct mmcerror::SC *)v19;
LABEL_7:
    mmcerror::SC::SC((mmcerror::SC *)a2, v7);
    SysFreeString(bstrString);
  }
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  return a2;
}

```

## disassembly

```asm
0x18001fed0  mov     [rsp-8+arg_8], rdx
0x18001fed5  push    rbp
0x18001fed6  push    rbx
0x18001fed7  push    rsi
0x18001fed8  push    rdi
0x18001fed9  push    r14
0x18001fedb  lea     rbp, [rsp-37h]
0x18001fee0  sub     rsp, 0D0h
0x18001fee7  mov     rax, cs:__security_cookie
0x18001feee  xor     rax, rsp
0x18001fef1  mov     [rbp+57h+var_30], rax
0x18001fef5  mov     rsi, r8
0x18001fef8  mov     rbx, rdx
0x18001fefb  mov     rdi, rcx
0x18001fefe  mov     [rbp+57h+lpsz], rdx
0x18001ff02  xor     r14d, r14d
0x18001ff05  xor     edx, edx
0x18001ff07  lea     rcx, [rbp+57h+var_C8]
0x18001ff0b  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18001ff11  nop
0x18001ff12  lea     rdx, aCxmlvalueScwri; "CXMLValue::ScWriteToBSTR"
0x18001ff19  lea     rcx, [rbp+57h+var_C8]
0x18001ff1d  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18001ff23  mov     edx, 80070057h
0x18001ff28  test    rsi, rsi
0x18001ff2b  cmovnz  edx, r14d
0x18001ff2f  lea     rcx, [rbp+57h+var_A8]
0x18001ff33  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18001ff39  nop
0x18001ff3a  lea     rdx, [rbp+57h+var_A8]
0x18001ff3e  lea     rcx, [rbp+57h+var_C8]
0x18001ff42  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18001ff48  nop
0x18001ff49  lea     rcx, [rbp+57h+var_A8]
0x18001ff4d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18001ff53  lea     rcx, [rbp+57h+var_C8]
0x18001ff57  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18001ff5d  test    al, al
0x18001ff5f  jnz     short loc_18001FFC7
0x18001ff61  mov     [rsi], r14
0x18001ff64  mov     [rbp+57h+bstrString], r14
0x18001ff68  movsxd  rax, dword ptr [rdi]
0x18001ff6b  cmp     eax, 0Ch
0x18001ff6e  jz      short loc_18001FFD6
0x18001ff70  cmp     eax, 0Eh; switch 15 cases
0x18001ff73  jbe     loc_180020021
0x18001ff79  mov     edx, 80004001h; jumptable 0000000180020032 default case, case 12
0x18001ff7e  lea     rcx, [rbp+57h+var_C8]
0x18001ff82  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18001ff88  mov     rdx, rax
0x18001ff8b  mov     rcx, rbx
0x18001ff8e  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18001ff94  nop
0x18001ff95  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001ff99  call    cs:__imp_SysFreeString
0x18001ff9f  nop
0x18001ffa0  lea     rcx, [rbp+57h+var_C8]
0x18001ffa4  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18001ffaa  mov     rax, rbx
0x18001ffad  mov     rcx, [rbp+57h+var_30]
0x18001ffb1  xor     rcx, rsp; StackCookie
0x18001ffb4  call    __security_check_cookie
0x18001ffb9  add     rsp, 0D0h
0x18001ffc0  pop     r14
0x18001ffc2  pop     rdi
0x18001ffc3  pop     rsi
0x18001ffc4  pop     rbx
0x18001ffc5  pop     rbp
0x18001ffc6  retn
0x18001ffc7  lea     rdx, [rbp+57h+var_C8]
0x18001ffcb  mov     rcx, rbx
0x18001ffce  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18001ffd4  jmp     short loc_18001FFA0
0x18001ffd6  mov     [rbp+57h+lpsz], r14
0x18001ffda  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18001ffde  mov     rcx, [rdi+8]; rclsid
0x18001ffe2  call    cs:__imp_StringFromCLSID
0x18001ffe8  mov     rdi, [rbp+57h+lpsz]
0x18001ffec  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001fff0  call    cs:__imp_SysFreeString
0x18001fff6  mov     rcx, rdi; psz
0x18001fff9  call    cs:__imp_SysAllocString
0x18001ffff  mov     [rbp+57h+bstrString], rax
0x180020003  mov     rcx, [rbp+57h+lpsz]; pv
0x180020007  call    cs:__imp_CoTaskMemFree
0x18002000d  mov     rax, [rbp+57h+bstrString]
0x180020011  mov     [rbp+57h+bstrString], r14
0x180020015  mov     [rsi], rax
0x180020018  lea     rdx, [rbp+57h+var_C8]
0x18002001c  jmp     loc_18001FF8B
0x180020021  lea     rdx, __ImageBase
0x180020028  mov     ecx, ds:(jpt_180020032 - 180000000h)[rdx+rax*4]
0x18002002f  add     rcx, rdx
0x180020032  jmp     rcx; switch jump
0x180020034  mov     r9, [rdi+8]; jumptable 0000000180020032 case 0
0x180020038  mov     r9d, [r9]
0x18002003b  jmp     short loc_180020045
0x18002003d  mov     rax, [rdi+8]; jumptable 0000000180020032 case 3
0x180020041  movsx   r9d, word ptr [rax]
0x180020045  lea     r8, aD_2; "%d"
0x18002004c  jmp     short loc_18002005C
0x18002004e  mov     r9, [rdi+8]; jumptable 0000000180020032 case 4
0x180020052  mov     r9d, [r9]
0x180020055  lea     r8, a0x044x; "0x%04.4x"
0x18002005c  mov     edx, 28h ; '('; unsigned __int64
0x180020061  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180020065  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002006a  mov     edx, eax
0x18002006c  lea     rcx, [rbp+57h+var_C8]
0x180020070  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180020076  lea     rcx, [rbp+57h+var_C8]
0x18002007a  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180020080  test    al, al
0x180020082  jz      loc_180020133
0x180020088  jmp     short loc_180020018
0x18002008a  mov     r9, [rdi+8]; jumptable 0000000180020032 cases 1,7
0x18002008e  mov     r9d, [r9]
0x180020091  lea     r8, aU; "%u"
0x180020098  jmp     short loc_18002005C
0x18002009a  mov     rax, [rdi+8]; jumptable 0000000180020032 case 2
0x18002009e  movzx   r9d, byte ptr [rax]
0x1800200a2  lea     r8, a0x022x; "0x%02.2x"
0x1800200a9  jmp     short loc_18002005C
0x1800200ab  mov     rax, [rdi+8]; jumptable 0000000180020032 case 5
0x1800200af  lea     rcx, aFalse; "false"
0x1800200b6  lea     rdx, aTrue; "true"
0x1800200bd  cmp     dword ptr [rax], 0
0x1800200c0  cmovz   rdx, rcx
0x1800200c4  lea     rcx, [rbp+57h+bstrString]
0x1800200c8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800200cd  jmp     loc_18002000D
0x1800200d2  mov     rax, [rdi+8]; jumptable 0000000180020032 case 6
0x1800200d6  lea     rcx, aFalse; "false"
0x1800200dd  lea     rdx, aTrue; "true"
0x1800200e4  cmp     byte ptr [rax], 0
0x1800200e7  cmovz   rdx, rcx
0x1800200eb  lea     rcx, [rbp+57h+bstrString]
0x1800200ef  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800200f4  jmp     loc_18002000D
0x1800200f9  mov     r9, [rdi+8]; jumptable 0000000180020032 case 8
0x1800200fd  mov     r9d, [r9]
0x180020100  lea     r8, aD_2; "%d"
0x180020107  mov     edx, 28h ; '('; unsigned __int64
0x18002010c  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180020110  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020115  mov     edx, eax
0x180020117  lea     rcx, [rbp+57h+var_C8]
0x18002011b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180020121  lea     rcx, [rbp+57h+var_C8]
0x180020125  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18002012b  test    al, al
0x18002012d  jnz     loc_180020018
0x180020133  lea     rdx, [rbp+57h+var_80]
0x180020137  lea     rcx, [rbp+57h+bstrString]
0x18002013b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180020140  jmp     loc_18002000D
0x180020145  mov     rdx, [rdi+8]; jumptable 0000000180020032 case 9
0x180020149  mov     rdx, [rdx+8]
0x18002014d  lea     rcx, [rbp+57h+bstrString]
0x180020151  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180020156  jmp     loc_18002000D
0x18002015b  lea     rax, [rdi+8]; jumptable 0000000180020032 cases 10,11
0x18002015f  mov     rdx, [rax]
0x180020162  cmp     qword ptr [rdx+18h], 8
0x180020167  cmovb   rdx, rax
0x18002016b  mov     rdx, [rdx]
0x18002016e  lea     rcx, [rbp+57h+bstrString]
0x180020172  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180020177  jmp     loc_18002000D
0x18002017c  mov     r8, [rdi+8]; jumptable 0000000180020032 case 13
0x180020180  lea     rdx, [rbp+57h+bstrString]
0x180020184  lea     rcx, [rbp+57h+var_A8]
0x180020188  call    ScEncodeBinary
0x18002018d  nop
0x18002018e  mov     rdx, rax
0x180020191  lea     rcx, [rbp+57h+var_C8]
0x180020195  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18002019b  nop
0x18002019c  lea     rcx, [rbp+57h+var_A8]
0x1800201a0  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800201a6  lea     rcx, [rbp+57h+var_C8]
0x1800201aa  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800201b0  test    al, al
0x1800201b2  jz      loc_18002000D
0x1800201b8  jmp     loc_180020018
0x1800201bd  mov     rcx, [rdi+8]; jumptable 0000000180020032 case 14
0x1800201c1  mov     rax, [rcx]
0x1800201c4  lea     r8, [rbp+57h+bstrString]
0x1800201c8  lea     rdx, [rbp+57h+var_A8]
0x1800201cc  mov     rax, [rax+8]
0x1800201d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d5  nop
0x1800201d6  mov     rdx, rax
0x1800201d9  lea     rcx, [rbp+57h+var_C8]
0x1800201dd  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1800201e3  nop
0x1800201e4  lea     rcx, [rbp+57h+var_A8]
0x1800201e8  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800201ee  lea     rcx, [rbp+57h+var_C8]
0x1800201f2  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800201f8  test    al, al
0x1800201fa  jz      loc_18002000D
0x180020200  jmp     loc_180020018
```
