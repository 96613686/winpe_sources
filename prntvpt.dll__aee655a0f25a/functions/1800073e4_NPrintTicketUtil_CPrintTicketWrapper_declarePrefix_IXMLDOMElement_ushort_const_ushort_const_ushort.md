# NPrintTicketUtil::CPrintTicketWrapper::declarePrefix(IXMLDOMElement *,ushort const *,ushort const *,ushort * *)

- ea: `0x1800073e4`
- end: `0x180007657`
- name: `?declarePrefix@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAG@Z`
- size: `627`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800070e0`

## callees

- `0x1800073e4`
- `0x180007660`
- `0x18000a76c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800074c8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800074e9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800075b6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800074c8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800074e9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800075b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180007588`
- `OLEAUT32!__imp_SysFreeString` at `0x180007622`
- `OLEAUT32!__imp_SysFreeString` at `0x180007634`
- `OLEAUT32!__imp_SysFreeString` at `0x180007588`
- `OLEAUT32!__imp_SysFreeString` at `0x180007622`
- `OLEAUT32!__imp_SysFreeString` at `0x180007634`

## string_xrefs

- `0x1800075d1`: `xmlns:%s`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::declarePrefix(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        OLECHAR *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // r15
  unsigned __int16 **v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rcx
  int XMLAttribute2; // edi
  const OLECHAR *v13; // r14
  __int64 v14; // rdx
  int v15; // r14d
  BSTR v16; // rax
  int v17; // edi
  unsigned __int16 *v18; // rbx
  int v20; // [rsp+88h] [rbp+10h] BYREF

  v5 = a4;
  if ( a2 )
  {
    if ( a3 )
    {
      v9 = a5;
      if ( a5 )
      {
        v10 = -1;
        *a5 = 0;
        if ( !a4 )
          goto LABEL_14;
        v11 = *((_QWORD *)this + 2);
        v20 = 0;
        XMLAttribute2 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMElement *, __int64))(*(_QWORD *)v11 + 56LL))(
                          v11,
                          a2,
                          1);
        if ( XMLAttribute2 < 0 )
        {
          v5 = 0;
          goto LABEL_34;
        }
        v13 = 0;
        if ( (*(unsigned int (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD, int *))(**((_QWORD **)this + 2) + 96LL))(
               *((_QWORD *)this + 2),
               v5,
               0,
               0,
               &v20) == 1 )
          v13 = v5;
        v5 = 0;
        XMLAttribute2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
        if ( XMLAttribute2 < 0 )
          goto LABEL_34;
        if ( v13 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v13[v14] );
          *v9 = SysAllocStringLen(v13, v14);
        }
        if ( !*v9 )
        {
LABEL_14:
          v15 = 1;
          v16 = SysAllocStringLen(0, 6u);
          *v9 = v16;
          if ( !v16 )
          {
LABEL_15:
            XMLAttribute2 = -2147024882;
LABEL_34:
            SysFreeString(*v9);
            *v9 = (unsigned __int16 *)v5;
            return (unsigned int)XMLAttribute2;
          }
          do
          {
            v20 = (int)v5;
            if ( *((_WORD *)this + 16) == 0xFFFF )
            {
              XMLAttribute2 = -2147467259;
            }
            else
            {
              XMLAttribute2 = StringCchPrintfW(*v9, 7u, L"ns%.4X", *((unsigned __int16 *)this + 16));
              if ( XMLAttribute2 >= 0 )
              {
                v15 = (int)v5;
                LOBYTE(v15) = (*(unsigned int (__fastcall **)(_QWORD, unsigned __int16 *, struct IXMLDOMElement *, _QWORD, int *))(**((_QWORD **)this + 2) + 96LL))(
                                *((_QWORD *)this + 2),
                                *v9,
                                a2,
                                0,
                                &v20) == 0;
              }
            }
            ++*((_WORD *)this + 16);
          }
          while ( XMLAttribute2 >= 0 && v15 );
          if ( v15 )
          {
            SysFreeString(*v9);
            *v9 = (unsigned __int16 *)v5;
          }
          if ( XMLAttribute2 < 0 )
            goto LABEL_34;
        }
        if ( !*v9 )
          return (unsigned int)XMLAttribute2;
        do
          ++v10;
        while ( (*v9)[v10] != (_WORD)v5 );
        v17 = v10 + 6;
        v18 = SysAllocStringLen(0, (int)v10 + 6);
        if ( v18 )
        {
          XMLAttribute2 = StringCchPrintfW(v18, v17 + 1, L"xmlns:%s", *v9);
          if ( XMLAttribute2 >= 0 )
          {
            XMLAttribute2 = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute2(
                              this,
                              *((struct IXMLDOMElement **)this + 3),
                              v18,
                              &psz,
                              a3);
            if ( XMLAttribute2 >= 0 )
              XMLAttribute2 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, OLECHAR *))(**((_QWORD **)this + 2)
                                                                                               + 72LL))(
                                *((_QWORD *)this + 2),
                                *v9,
                                a3);
          }
          SysFreeString(v18);
          if ( XMLAttribute2 >= 0 )
            return (unsigned int)XMLAttribute2;
          goto LABEL_34;
        }
        goto LABEL_15;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800073e4  mov     rax, rsp
0x1800073e7  push    rbx
0x1800073e8  push    rbp
0x1800073e9  push    rsi
0x1800073ea  push    rdi
0x1800073eb  push    r12
0x1800073ed  push    r13
0x1800073ef  push    r14
0x1800073f1  push    r15
0x1800073f3  sub     rsp, 38h
0x1800073f7  mov     r15, r9
0x1800073fa  mov     r12, r8
0x1800073fd  mov     r13, rdx
0x180007400  mov     rbp, rcx
0x180007403  test    rdx, rdx
0x180007406  jz      loc_180007641
0x18000740c  test    r8, r8
0x18000740f  jz      loc_180007641
0x180007415  mov     rsi, [rsp+78h+arg_20]
0x18000741d  test    rsi, rsi
0x180007420  jz      loc_180007641
0x180007426  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000742a  mov     qword ptr [rsi], 0
0x180007431  mov     edx, 1
0x180007436  test    r15, r15
0x180007439  jz      loc_1800074DF
0x18000743f  mov     rcx, [rcx+10h]
0x180007443  mov     r8d, edx
0x180007446  mov     dword ptr [rax+10h], 0
0x18000744d  mov     rdx, r13
0x180007450  mov     rax, [rcx]
0x180007453  mov     rax, [rax+38h]
0x180007457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000745c  mov     edi, eax
0x18000745e  test    eax, eax
0x180007460  js      loc_18000762E
0x180007466  mov     rcx, [rbp+10h]
0x18000746a  lea     rdx, [rsp+78h+arg_8]
0x180007472  mov     [rsp+78h+psz], rdx
0x180007477  xor     r9d, r9d
0x18000747a  xor     r8d, r8d
0x18000747d  mov     rdx, r15
0x180007480  mov     rax, [rcx]
0x180007483  mov     rax, [rax+60h]
0x180007487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748c  mov     rcx, [rbp+10h]
0x180007490  xor     r14d, r14d
0x180007493  cmp     eax, 1
0x180007496  cmovz   r14, r15
0x18000749a  mov     rax, [rcx]
0x18000749d  mov     rax, [rax+40h]
0x1800074a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a6  xor     r15d, r15d
0x1800074a9  mov     edi, eax
0x1800074ab  test    eax, eax
0x1800074ad  js      loc_180007631
0x1800074b3  test    r14, r14
0x1800074b6  jz      short loc_1800074D1
0x1800074b8  mov     rdx, rbx
0x1800074bb  inc     rdx; ui
0x1800074be  cmp     [r14+rdx*2], r15w
0x1800074c3  jnz     short loc_1800074BB
0x1800074c5  mov     rcx, r14; strIn
0x1800074c8  call    cs:__imp_SysAllocStringLen
0x1800074ce  mov     [rsi], rax
0x1800074d1  cmp     [rsi], r15
0x1800074d4  jnz     loc_180007599
0x1800074da  mov     edx, 1
0x1800074df  mov     r14d, edx
0x1800074e2  xor     ecx, ecx; strIn
0x1800074e4  mov     edx, 6; ui
0x1800074e9  call    cs:__imp_SysAllocStringLen
0x1800074ef  mov     [rsi], rax
0x1800074f2  test    rax, rax
0x1800074f5  jnz     short loc_180007501
0x1800074f7  mov     edi, 8007000Eh
0x1800074fc  jmp     loc_180007631
0x180007501  mov     ecx, 1
0x180007506  mov     eax, 0FFFFh
0x18000750b  mov     [rsp+78h+arg_8], r15d
0x180007513  cmp     [rbp+20h], ax
0x180007517  jb      short loc_180007520
0x180007519  mov     edi, 80004005h
0x18000751e  jmp     short loc_180007573
0x180007520  movzx   r9d, word ptr [rbp+20h]
0x180007525  lea     r8, aNs4x; "ns%.4X"
0x18000752c  mov     rcx, [rsi]; unsigned __int16 *
0x18000752f  mov     edx, 7; unsigned __int64
0x180007534  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007539  mov     edi, eax
0x18000753b  test    eax, eax
0x18000753d  js      short loc_18000756E
0x18000753f  mov     rcx, [rbp+10h]
0x180007543  lea     rdx, [rsp+78h+arg_8]
0x18000754b  mov     [rsp+78h+psz], rdx
0x180007550  xor     r9d, r9d
0x180007553  mov     rdx, [rsi]
0x180007556  mov     r8, r13
0x180007559  mov     rax, [rcx]
0x18000755c  mov     rax, [rax+60h]
0x180007560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007565  test    eax, eax
0x180007567  mov     r14d, r15d
0x18000756a  setz    r14b
0x18000756e  mov     ecx, 1
0x180007573  add     [rbp+20h], cx
0x180007577  test    edi, edi
0x180007579  js      short loc_180007580
0x18000757b  test    r14d, r14d
0x18000757e  jnz     short loc_180007506
0x180007580  test    r14d, r14d
0x180007583  jz      short loc_180007591
0x180007585  mov     rcx, [rsi]; bstrString
0x180007588  call    cs:__imp_SysFreeString
0x18000758e  mov     [rsi], r15
0x180007591  test    edi, edi
0x180007593  js      loc_180007631
0x180007599  mov     rax, [rsi]
0x18000759c  test    rax, rax
0x18000759f  jz      loc_18000763D
0x1800075a5  inc     rbx
0x1800075a8  cmp     [rax+rbx*2], r15w
0x1800075ad  jnz     short loc_1800075A5
0x1800075af  lea     edi, [rbx+6]
0x1800075b2  xor     ecx, ecx; strIn
0x1800075b4  mov     edx, edi; ui
0x1800075b6  call    cs:__imp_SysAllocStringLen
0x1800075bc  mov     rbx, rax
0x1800075bf  test    rax, rax
0x1800075c2  jz      loc_1800074F7
0x1800075c8  mov     r9, [rsi]
0x1800075cb  lea     eax, [rdi+1]
0x1800075ce  movsxd  rdx, eax; unsigned __int64
0x1800075d1  lea     r8, aXmlnsS; "xmlns:%s"
0x1800075d8  mov     rcx, rbx; unsigned __int16 *
0x1800075db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800075e0  mov     edi, eax
0x1800075e2  test    eax, eax
0x1800075e4  js      short loc_18000761F
0x1800075e6  mov     rdx, [rbp+18h]; struct IXMLDOMElement *
0x1800075ea  lea     r9, psz; unsigned __int16 *
0x1800075f1  mov     r8, rbx; unsigned __int16 *
0x1800075f4  mov     [rsp+78h+psz], r12; psz
0x1800075f9  mov     rcx, rbp; this
0x1800075fc  call    ?CreateXMLAttribute2@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute2(IXMLDOMElement *,ushort const *,ushort const *,ushort const *)
0x180007601  mov     edi, eax
0x180007603  test    eax, eax
0x180007605  js      short loc_18000761F
0x180007607  mov     rcx, [rbp+10h]
0x18000760b  mov     r8, r12
0x18000760e  mov     rdx, [rsi]
0x180007611  mov     rax, [rcx]
0x180007614  mov     rax, [rax+48h]
0x180007618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000761d  mov     edi, eax
0x18000761f  mov     rcx, rbx; bstrString
0x180007622  call    cs:__imp_SysFreeString
0x180007628  test    edi, edi
0x18000762a  js      short loc_180007631
0x18000762c  jmp     short loc_18000763D
0x18000762e  xor     r15d, r15d
0x180007631  mov     rcx, [rsi]; bstrString
0x180007634  call    cs:__imp_SysFreeString
0x18000763a  mov     [rsi], r15
0x18000763d  mov     eax, edi
0x18000763f  jmp     short loc_180007646
0x180007641  mov     eax, 80070057h
0x180007646  add     rsp, 38h
0x18000764a  pop     r15
0x18000764c  pop     r14
0x18000764e  pop     r13
0x180007650  pop     r12
0x180007652  pop     rdi
0x180007653  pop     rsi
0x180007654  pop     rbp
0x180007655  pop     rbx
0x180007656  retn
```
