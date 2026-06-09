# CreateHelperAttributeFromXML(IXMLDOMNode *,tagHELPER_ATTRIBUTE *)

- ea: `0x180011934`
- end: `0x180011c18`
- name: `?CreateHelperAttributeFromXML@@YAJPEAUIXMLDOMNode@@PEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180011c20`

## callees

- `0x180011934`
- `0x18001bdc0`
- `0x18001c0f0`
- `0x18001c550`
- `0x18001c8b8`
- `0x18001f652`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180011a31`
- `ole32!CoTaskMemAlloc` at `0x180011a31`
- `ole32!CoTaskMemFree` at `0x180011a8a`
- `ole32!CoTaskMemFree` at `0x180011a8a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001195c`
- `OLEAUT32!__imp_SysAllocString` at `0x180011ab8`
- `OLEAUT32!__imp_SysAllocString` at `0x180011b47`
- `OLEAUT32!__imp_SysAllocString` at `0x18001195c`
- `OLEAUT32!__imp_SysAllocString` at `0x180011ab8`
- `OLEAUT32!__imp_SysAllocString` at `0x180011b47`
- `OLEAUT32!__imp_SysFreeString` at `0x180011983`
- `OLEAUT32!__imp_SysFreeString` at `0x1800119cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ae4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b73`
- `OLEAUT32!__imp_SysFreeString` at `0x180011bf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c01`
- `OLEAUT32!__imp_SysFreeString` at `0x180011983`
- `OLEAUT32!__imp_SysFreeString` at `0x1800119cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ae4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b73`
- `OLEAUT32!__imp_SysFreeString` at `0x180011bf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c01`
- `OLEAUT32!__imp_SysStringLen` at `0x180011a25`
- `OLEAUT32!__imp_SysStringLen` at `0x180011a25`

## pseudocode

```c
__int64 __fastcall CreateHelperAttributeFromXML(struct IXMLDOMNode *a1, struct tagHELPER_ATTRIBUTE *a2)
{
  enum tagATTRIBUTE_TYPE v4; // r15d
  BOOL v5; // esi
  OLECHAR *v6; // rbx
  signed int v7; // edi
  const unsigned __int16 *v8; // rsi
  SIZE_T v9; // rdi
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rbx
  OLECHAR *v12; // rcx
  OLECHAR *v13; // rbx
  OLECHAR *v14; // rbx
  int v15; // eax
  BSTR bstrString; // [rsp+60h] [rbp+40h] BYREF
  BSTR pbstr; // [rsp+70h] [rbp+50h] BYREF
  BSTR v19; // [rsp+78h] [rbp+58h] BYREF

  v4 = AT_INVALID;
  v5 = 0;
  pbstr = 0;
  v6 = SysAllocString(L"Type");
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, BSTR *))a1->lpVtbl->selectSingleNode)(a1, v6, &pbstr);
  SysFreeString(v6);
  if ( v7 )
  {
    v5 = v7 == 1;
  }
  else
  {
    bstrString = 0;
    v7 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)pbstr + 208LL))(pbstr, &bstrString);
    if ( v7 >= 0 )
    {
      v4 = AttributeTypeFromString(bstrString);
      if ( v4 == AT_INVALID )
        v7 = -2147024809;
      SysFreeString(bstrString);
    }
  }
  if ( pbstr )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)pbstr + 16LL))(pbstr);
  pbstr = 0;
  if ( v5 )
  {
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_text)(a1, &pbstr);
    if ( v7 >= 0 )
    {
      v8 = pbstr;
      v9 = SysStringLen(pbstr) >> 1;
      v10 = (unsigned __int8 *)CoTaskMemAlloc(v9);
      v11 = v10;
      if ( v10 )
      {
        memset_0(v10, 0, v9);
        LODWORD(bstrString) = 0;
        if ( HexToBin(v8, v11, v9, (unsigned int *)&bstrString) )
          v7 = DecodeHelperAttribute(v11, v9, a2);
        else
          v7 = -2147467259;
        CoTaskMemFree(v11);
      }
      else
      {
        v7 = -2147024882;
      }
      v12 = pbstr;
LABEL_44:
      SysFreeString(v12);
    }
  }
  else
  {
    v19 = 0;
    if ( v7 >= 0 )
    {
      bstrString = 0;
      v13 = SysAllocString(L"Name");
      if ( v13 )
      {
        v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, BSTR *))a1->lpVtbl->selectSingleNode)(
               a1,
               v13,
               &bstrString);
        SysFreeString(v13);
        if ( v7 )
        {
          if ( v7 == 1 )
            v7 = -2147024809;
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)bstrString + 208LL))(bstrString, &pbstr);
        }
      }
      else
      {
        v7 = -2147024882;
      }
      if ( bstrString )
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
      if ( v7 >= 0 )
      {
        bstrString = 0;
        v14 = SysAllocString(L"Value");
        if ( v14 )
        {
          v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, BSTR *))a1->lpVtbl->selectSingleNode)(
                 a1,
                 v14,
                 &bstrString);
          SysFreeString(v14);
          if ( v7 )
          {
            if ( v7 == 1 )
              v7 = -2147024809;
          }
          else
          {
            v7 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)bstrString + 208LL))(bstrString, &v19);
          }
        }
        else
        {
          v7 = -2147024882;
        }
        if ( bstrString )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
        if ( v7 >= 0 )
        {
          v15 = AttributeFromString(pbstr, v4, v19, a2);
          if ( v15 )
          {
            if ( v15 > 0 )
              v7 = (unsigned __int16)v15 | 0x80070000;
            else
              v7 = v15;
          }
        }
      }
      if ( pbstr )
        SysFreeString(pbstr);
      v12 = v19;
      if ( v19 )
        goto LABEL_44;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180011934  push    rbp
0x180011936  push    rbx
0x180011937  push    rsi
0x180011938  push    rdi
0x180011939  push    r12
0x18001193b  push    r14
0x18001193d  push    r15
0x18001193f  mov     rbp, rsp
0x180011942  sub     rsp, 20h
0x180011946  mov     r12, rdx
0x180011949  mov     r14, rcx
0x18001194c  xor     r15d, r15d
0x18001194f  xor     esi, esi
0x180011951  mov     [rbp+pbstr], rsi
0x180011955  lea     rcx, psz; "Type"
0x18001195c  call    cs:__imp_SysAllocString
0x180011962  mov     rbx, rax
0x180011965  mov     rax, [r14]
0x180011968  lea     r8, [rbp+pbstr]
0x18001196c  mov     rdx, rbx
0x18001196f  mov     rcx, r14
0x180011972  mov     rax, [rax+128h]
0x180011979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001197e  mov     edi, eax
0x180011980  mov     rcx, rbx; bstrString
0x180011983  call    cs:__imp_SysFreeString
0x180011989  lea     eax, [rsi+1]
0x18001198c  mov     ebx, 80070057h
0x180011991  test    edi, edi
0x180011993  jnz     short loc_1800119D3
0x180011995  mov     [rbp+bstrString], rsi
0x180011999  mov     rcx, [rbp+pbstr]
0x18001199d  mov     rax, [rcx]
0x1800119a0  lea     rdx, [rbp+bstrString]
0x1800119a4  mov     rax, [rax+0D0h]
0x1800119ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b0  mov     edi, eax
0x1800119b2  test    eax, eax
0x1800119b4  js      short loc_1800119D8
0x1800119b6  mov     rcx, [rbp+bstrString]; String2
0x1800119ba  call    ?AttributeTypeFromString@@YA?AW4tagATTRIBUTE_TYPE@@PEBG@Z; AttributeTypeFromString(ushort const *)
0x1800119bf  mov     r15d, eax
0x1800119c2  test    eax, eax
0x1800119c4  cmovz   edi, ebx
0x1800119c7  mov     rcx, [rbp+bstrString]; bstrString
0x1800119cb  call    cs:__imp_SysFreeString
0x1800119d1  jmp     short loc_1800119D8
0x1800119d3  cmp     edi, eax
0x1800119d5  cmovz   esi, eax
0x1800119d8  mov     rcx, [rbp+pbstr]
0x1800119dc  test    rcx, rcx
0x1800119df  jz      short loc_1800119EE
0x1800119e1  mov     rax, [rcx]
0x1800119e4  mov     rax, [rax+10h]
0x1800119e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ed  nop
0x1800119ee  mov     [rbp+pbstr], 0
0x1800119f6  test    esi, esi
0x1800119f8  jz      loc_180011A99
0x1800119fe  mov     rax, [r14]
0x180011a01  lea     rdx, [rbp+pbstr]
0x180011a05  mov     rcx, r14
0x180011a08  mov     rax, [rax+0D0h]
0x180011a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a14  mov     edi, eax
0x180011a16  test    eax, eax
0x180011a18  js      loc_180011C07
0x180011a1e  mov     rsi, [rbp+pbstr]
0x180011a22  mov     rcx, rsi; pbstr
0x180011a25  call    cs:__imp_SysStringLen
0x180011a2b  shr     eax, 1
0x180011a2d  mov     edi, eax
0x180011a2f  mov     ecx, eax; cb
0x180011a31  call    cs:__imp_CoTaskMemAlloc
0x180011a37  mov     rbx, rax
0x180011a3a  test    rax, rax
0x180011a3d  jnz     short loc_180011A46
0x180011a3f  mov     edi, 8007000Eh
0x180011a44  jmp     short loc_180011A90
0x180011a46  mov     r8, rdi; Size
0x180011a49  xor     edx, edx; Val
0x180011a4b  mov     rcx, rbx; void *
0x180011a4e  call    memset_0
0x180011a53  mov     dword ptr [rbp+bstrString], 0
0x180011a5a  lea     r9, [rbp+bstrString]; unsigned int *
0x180011a5e  mov     r8d, edi; unsigned int
0x180011a61  mov     rdx, rbx; unsigned __int8 *
0x180011a64  mov     rcx, rsi; unsigned __int16 *
0x180011a67  call    ?HexToBin@@YAHPEBGPEAEKPEAK@Z; HexToBin(ushort const *,uchar *,ulong,ulong *)
0x180011a6c  test    eax, eax
0x180011a6e  jnz     short loc_180011A77
0x180011a70  mov     edi, 80004005h
0x180011a75  jmp     short loc_180011A87
0x180011a77  mov     r8, r12
0x180011a7a  mov     rdx, rdi
0x180011a7d  mov     rcx, rbx
0x180011a80  call    DecodeHelperAttribute
0x180011a85  mov     edi, eax
0x180011a87  mov     rcx, rbx; pv
0x180011a8a  call    cs:__imp_CoTaskMemFree
0x180011a90  mov     rcx, [rbp+pbstr]
0x180011a94  jmp     loc_180011C01
0x180011a99  mov     [rbp+arg_18], 0
0x180011aa1  test    edi, edi
0x180011aa3  js      loc_180011C07
0x180011aa9  mov     [rbp+bstrString], 0
0x180011ab1  lea     rcx, aName; "Name"
0x180011ab8  call    cs:__imp_SysAllocString
0x180011abe  mov     rbx, rax
0x180011ac1  test    rax, rax
0x180011ac4  jz      short loc_180011B15
0x180011ac6  mov     rcx, [r14]
0x180011ac9  mov     rax, [rcx+128h]
0x180011ad0  lea     r8, [rbp+bstrString]
0x180011ad4  mov     rdx, rbx
0x180011ad7  mov     rcx, r14
0x180011ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011adf  mov     edi, eax
0x180011ae1  mov     rcx, rbx; bstrString
0x180011ae4  call    cs:__imp_SysFreeString
0x180011aea  test    edi, edi
0x180011aec  jnz     short loc_180011B09
0x180011aee  mov     rcx, [rbp+bstrString]
0x180011af2  mov     rax, [rcx]
0x180011af5  lea     rdx, [rbp+pbstr]
0x180011af9  mov     rax, [rax+0D0h]
0x180011b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b05  mov     edi, eax
0x180011b07  jmp     short loc_180011B1A
0x180011b09  cmp     edi, 1
0x180011b0c  jnz     short loc_180011B1A
0x180011b0e  mov     edi, 80070057h
0x180011b13  jmp     short loc_180011B1A
0x180011b15  mov     edi, 8007000Eh
0x180011b1a  mov     rcx, [rbp+bstrString]
0x180011b1e  test    rcx, rcx
0x180011b21  jz      short loc_180011B30
0x180011b23  mov     rax, [rcx]
0x180011b26  mov     rax, [rax+10h]
0x180011b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b2f  nop
0x180011b30  test    edi, edi
0x180011b32  js      loc_180011BE9
0x180011b38  mov     [rbp+bstrString], 0
0x180011b40  lea     rcx, aValue; "Value"
0x180011b47  call    cs:__imp_SysAllocString
0x180011b4d  mov     rbx, rax
0x180011b50  test    rax, rax
0x180011b53  jz      short loc_180011BA4
0x180011b55  mov     rcx, [r14]
0x180011b58  mov     rax, [rcx+128h]
0x180011b5f  lea     r8, [rbp+bstrString]
0x180011b63  mov     rdx, rbx
0x180011b66  mov     rcx, r14
0x180011b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b6e  mov     edi, eax
0x180011b70  mov     rcx, rbx; bstrString
0x180011b73  call    cs:__imp_SysFreeString
0x180011b79  test    edi, edi
0x180011b7b  jnz     short loc_180011B98
0x180011b7d  mov     rcx, [rbp+bstrString]
0x180011b81  mov     rax, [rcx]
0x180011b84  lea     rdx, [rbp+arg_18]
0x180011b88  mov     rax, [rax+0D0h]
0x180011b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b94  mov     edi, eax
0x180011b96  jmp     short loc_180011BA9
0x180011b98  cmp     edi, 1
0x180011b9b  jnz     short loc_180011BA9
0x180011b9d  mov     edi, 80070057h
0x180011ba2  jmp     short loc_180011BA9
0x180011ba4  mov     edi, 8007000Eh
0x180011ba9  mov     rcx, [rbp+bstrString]
0x180011bad  test    rcx, rcx
0x180011bb0  jz      short loc_180011BBF
0x180011bb2  mov     rax, [rcx]
0x180011bb5  mov     rax, [rax+10h]
0x180011bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bbe  nop
0x180011bbf  test    edi, edi
0x180011bc1  js      short loc_180011BE9
0x180011bc3  mov     r9, r12; struct tagHELPER_ATTRIBUTE *
0x180011bc6  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180011bca  mov     edx, r15d; enum tagATTRIBUTE_TYPE
0x180011bcd  mov     rcx, [rbp+pbstr]; unsigned __int16 *
0x180011bd1  call    ?AttributeFromString@@YAKPEBGW4tagATTRIBUTE_TYPE@@0AEAUtagHELPER_ATTRIBUTE@@@Z; AttributeFromString(ushort const *,tagATTRIBUTE_TYPE,ushort const *,tagHELPER_ATTRIBUTE &)
0x180011bd6  test    eax, eax
0x180011bd8  jz      short loc_180011BE9
0x180011bda  jg      short loc_180011BE0
0x180011bdc  mov     edi, eax
0x180011bde  jmp     short loc_180011BE9
0x180011be0  movzx   edi, ax
0x180011be3  or      edi, 80070000h
0x180011be9  mov     rcx, [rbp+pbstr]; bstrString
0x180011bed  test    rcx, rcx
0x180011bf0  jz      short loc_180011BF8
0x180011bf2  call    cs:__imp_SysFreeString
0x180011bf8  mov     rcx, [rbp+arg_18]; bstrString
0x180011bfc  test    rcx, rcx
0x180011bff  jz      short loc_180011C07
0x180011c01  call    cs:__imp_SysFreeString
0x180011c07  mov     eax, edi
0x180011c09  add     rsp, 20h
0x180011c0d  pop     r15
0x180011c0f  pop     r14
0x180011c11  pop     r12
0x180011c13  pop     rdi
0x180011c14  pop     rsi
0x180011c15  pop     rbx
0x180011c16  pop     rbp
0x180011c17  retn
```
