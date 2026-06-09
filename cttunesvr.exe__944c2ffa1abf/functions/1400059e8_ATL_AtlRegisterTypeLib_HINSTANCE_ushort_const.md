# ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)

- ea: `0x1400059e8`
- end: `0x140005bc1`
- name: `?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z`
- size: `473`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140005ce4`

## callees

- `0x140001888`
- `0x140002c14`
- `0x140005384`
- `0x1400059e8`
- `0x1400065f0`
- `0x140007010`

## import_xrefs

- `USER32!CharNextW` at `0x140005add`
- `USER32!CharNextW` at `0x140005add`
- `msvcrt!wcsncpy_s` at `0x140005a92`
- `msvcrt!wcsncpy_s` at `0x140005a92`
- `OLEAUT32!__imp_SysFreeString` at `0x140005b55`
- `OLEAUT32!__imp_SysFreeString` at `0x140005b76`
- `OLEAUT32!__imp_SysFreeString` at `0x140005b55`
- `OLEAUT32!__imp_SysFreeString` at `0x140005b76`
- `OLEAUT32!__imp_SysStringLen` at `0x140005a7a`
- `OLEAUT32!__imp_SysStringLen` at `0x140005a7a`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x140005b48`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x140005b48`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterTypeLib(HINSTANCE a1, const unsigned __int16 *a2)
{
  HRESULT v2; // edi
  UINT v3; // eax
  errno_t v4; // eax
  wchar_t *v5; // rdi
  wchar_t *v6; // rsi
  LPWSTR v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdi
  wchar_t *v11; // r8
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *ptlib; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF

  pbstr = 0;
  ptlib = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &pbstr, &ptlib);
  if ( v2 >= 0 )
  {
    bstrString[0] = 0;
    if ( ((int (__fastcall *)(ITypeLib *, __int64, _QWORD, _QWORD, _QWORD, BSTR *))ptlib->lpVtbl->GetDocumentation)(
           ptlib,
           0xFFFFFFFFLL,
           0,
           0,
           0,
           bstrString) >= 0
      && bstrString[0] )
    {
      v3 = SysStringLen(pbstr);
      v4 = wcsncpy_s(Destination, 0x104u, pbstr, v3);
      if ( v4 )
      {
        if ( v4 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v4 == 22 || v4 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v4 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v5 = Destination;
      Destination[259] = 0;
      v6 = Destination;
      if ( Destination[0] )
      {
        do
        {
          v7 = CharNextW(v6);
          v8 = *v6;
          LOWORD(v8) = v8 - 47;
          if ( (unsigned __int16)v8 <= 0x2Du )
          {
            v9 = 0x200000000801LL;
            if ( _bittest64(&v9, v8) )
              v5 = v7;
          }
          v6 = v7;
        }
        while ( *v7 );
      }
      v10 = v5 - Destination;
      if ( (unsigned int)v10 < 0x104 )
      {
        if ( 2 * (unsigned __int64)(unsigned int)v10 >= 0x208 )
          _report_rangecheckfailure();
        Destination[(unsigned int)v10] = 0;
      }
      v11 = Destination;
    }
    else
    {
      v11 = 0;
    }
    v2 = RegisterTypeLib(ptlib, pbstr, v11);
    SysFreeString(bstrString[0]);
  }
  if ( ptlib )
    ((void (__fastcall *)(ITypeLib *))ptlib->lpVtbl->Release)(ptlib);
  SysFreeString(pbstr);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400059e8  push    rbp
0x1400059ea  push    rsi
0x1400059eb  push    rdi
0x1400059ec  push    r14
0x1400059ee  lea     rbp, [rsp-188h]
0x1400059f6  sub     rsp, 288h
0x1400059fd  mov     rax, cs:__security_cookie
0x140005a04  xor     rax, rsp
0x140005a07  mov     [rbp+1A0h+var_30], rax
0x140005a0e  xor     r14d, r14d
0x140005a11  lea     r9, [rsp+2A0h+ptlib]; struct ITypeLib **
0x140005a16  lea     r8, [rsp+2A0h+pbstr]; unsigned __int16 **
0x140005a1b  mov     [rsp+2A0h+pbstr], r14
0x140005a20  mov     [rsp+2A0h+ptlib], r14
0x140005a25  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x140005a2a  mov     edi, eax
0x140005a2c  test    eax, eax
0x140005a2e  js      loc_140005B5B
0x140005a34  mov     rcx, [rsp+2A0h+ptlib]
0x140005a39  lea     rdx, [rsp+2A0h+bstrString]
0x140005a3e  mov     [rsp+2A0h+var_278], rdx
0x140005a43  xor     r9d, r9d
0x140005a46  mov     [rsp+2A0h+bstrString], r14
0x140005a4b  xor     r8d, r8d
0x140005a4e  or      edx, 0FFFFFFFFh
0x140005a51  mov     [rsp+2A0h+var_280], r14
0x140005a56  mov     rax, [rcx]
0x140005a59  mov     rax, [rax+48h]
0x140005a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a62  test    eax, eax
0x140005a64  js      loc_140005B3B
0x140005a6a  cmp     [rsp+2A0h+bstrString], r14
0x140005a6f  jz      loc_140005B3B
0x140005a75  mov     rcx, [rsp+2A0h+pbstr]; pbstr
0x140005a7a  call    cs:__imp_SysStringLen
0x140005a80  mov     r8, [rsp+2A0h+pbstr]; Source
0x140005a85  lea     rcx, [rsp+2A0h+Destination]; Destination
0x140005a8a  mov     r9d, eax; MaxCount
0x140005a8d  mov     edx, 104h; SizeInWords
0x140005a92  call    cs:__imp_wcsncpy_s
0x140005a98  test    eax, eax
0x140005a9a  jz      short loc_140005AC0
0x140005a9c  cmp     eax, 0Ch
0x140005a9f  jz      loc_140005BB6
0x140005aa5  cmp     eax, 16h
0x140005aa8  jz      loc_140005BAB
0x140005aae  cmp     eax, 22h ; '"'
0x140005ab1  jz      loc_140005BAB
0x140005ab7  cmp     eax, 50h ; 'P'
0x140005aba  jnz     loc_140005BA0
0x140005ac0  lea     rdi, [rsp+2A0h+Destination]
0x140005ac5  mov     [rbp+1A0h+var_3A], r14w
0x140005acd  lea     rsi, [rsp+2A0h+Destination]
0x140005ad2  cmp     [rsp+2A0h+Destination], r14w
0x140005ad8  jz      short loc_140005B0C
0x140005ada  mov     rcx, rsi; lpsz
0x140005add  call    cs:__imp_CharNextW
0x140005ae3  movzx   ecx, word ptr [rsi]
0x140005ae6  sub     cx, 2Fh ; '/'
0x140005aea  cmp     cx, 2Dh ; '-'
0x140005aee  ja      short loc_140005B03
0x140005af0  mov     rdx, 200000000801h
0x140005afa  bt      rdx, rcx
0x140005afe  jnb     short loc_140005B03
0x140005b00  mov     rdi, rax
0x140005b03  mov     rsi, rax
0x140005b06  cmp     [rax], r14w
0x140005b0a  jnz     short loc_140005ADA
0x140005b0c  lea     rax, [rsp+2A0h+Destination]
0x140005b11  sub     rdi, rax
0x140005b14  sar     rdi, 1
0x140005b17  cmp     edi, 104h
0x140005b1d  jnb     short loc_140005B34
0x140005b1f  mov     eax, edi
0x140005b21  lea     rcx, [rax+rax]
0x140005b25  cmp     rcx, 208h
0x140005b2c  jnb     short loc_140005B9A
0x140005b2e  mov     [rsp+rcx+2A0h+Destination], r14w
0x140005b34  lea     r8, [rsp+2A0h+Destination]
0x140005b39  jmp     short loc_140005B3E
0x140005b3b  xor     r8d, r8d; szHelpDir
0x140005b3e  mov     rdx, [rsp+2A0h+pbstr]; szFullPath
0x140005b43  mov     rcx, [rsp+2A0h+ptlib]; ptlib
0x140005b48  call    cs:__imp_RegisterTypeLib
0x140005b4e  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x140005b53  mov     edi, eax
0x140005b55  call    cs:__imp_SysFreeString
0x140005b5b  mov     rcx, [rsp+2A0h+ptlib]
0x140005b60  test    rcx, rcx
0x140005b63  jz      short loc_140005B71
0x140005b65  mov     rax, [rcx]
0x140005b68  mov     rax, [rax+10h]
0x140005b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b71  mov     rcx, [rsp+2A0h+pbstr]; bstrString
0x140005b76  call    cs:__imp_SysFreeString
0x140005b7c  mov     eax, edi
0x140005b7e  mov     rcx, [rbp+1A0h+var_30]
0x140005b85  xor     rcx, rsp; StackCookie
0x140005b88  call    __security_check_cookie
0x140005b8d  add     rsp, 288h
0x140005b94  pop     r14
0x140005b96  pop     rdi
0x140005b97  pop     rsi
0x140005b98  pop     rbp
0x140005b99  retn
0x140005b9a  call    __report_rangecheckfailure
0x140005ba0  mov     ecx, 80004005h; int
0x140005ba5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140005bab  mov     ecx, 80070057h; int
0x140005bb0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140005bb6  mov     ecx, 8007000Eh; int
0x140005bbb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
