# AddToListOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,TConstructionData *,EListMode)

- ea: `0x180003ee0`
- end: `0x1800042b2`
- name: `?AddToListOnVisit@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUTConstructionData@@W4EListMode@@@Z`
- size: `978`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004aa8`
- `0x180004abc`

## callees

- `0x180003ee0`
- `0x180004abc`
- `0x180004b00`
- `0x180005aa4`
- `0x18000fd6c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004110`
- `OLEAUT32!__imp_SysFreeString` at `0x180004126`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180004110`
- `OLEAUT32!__imp_SysFreeString` at `0x180004126`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041d6`

## string_xrefs

- `0x180004022`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall AddToListOnVisit(
        NPrintTicketUtil::CPrintTicketWrapper *a1,
        struct IXMLDOMElement *a2,
        __int64 a3,
        int a4)
{
  void *v8; // r12
  int NameAttribute; // eax
  int v10; // r15d
  __int64 v11; // rcx
  int v12; // ebx
  OLECHAR *v13; // r9
  OLECHAR *v14; // r10
  BSTR v15; // rax
  int v16; // ecx
  int v17; // edx
  BSTR v18; // rax
  int v19; // ecx
  int v20; // edx
  __int64 v21; // rax
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24; // [rsp+38h] [rbp-38h] BYREF
  BSTR v25; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMElement *v26; // [rsp+48h] [rbp-28h] BYREF
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  _DWORD v28[2]; // [rsp+58h] [rbp-18h] BYREF
  __int128 v29; // [rsp+60h] [rbp-10h]

  v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
    return 2147942414LL;
  *(_QWORD *)v8 = &NPrintTicketUtil::TFeatureListEntry::`vftable';
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 4) = 0;
  *((_DWORD *)v8 + 10) = 0;
  *((_QWORD *)v8 + 6) = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
                    a1,
                    a2,
                    (unsigned __int16 **)v8 + 2,
                    (unsigned __int16 **)v8 + 3,
                    0);
  v10 = NameAttribute;
  if ( *((_QWORD *)v8 + 2) && *((_QWORD *)v8 + 3) )
  {
    if ( NameAttribute >= 0 )
    {
      if ( *(_DWORD *)a3
        || (v10 = NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix((NPrintTicketUtil::TFeatureListEntry *)v8),
            v10 >= 0) )
      {
        if ( a4 )
          goto LABEL_52;
        v28[0] = *(_DWORD *)a3 + 1;
        v28[1] = 0;
        v27 = 0;
        v29 = 0;
        if ( !a2 )
          a2 = (struct IXMLDOMElement *)*((_QWORD *)a1 + 3);
        v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))a2->lpVtbl->get_childNodes)(a2, &v27);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 80LL))(v27);
          if ( v10 >= 0 )
          {
            v11 = 0;
            v24 = 0;
            v12 = 0;
            while ( 1 )
            {
              if ( v10 < 0 )
              {
LABEL_45:
                if ( v11 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                if ( v10 >= 0 )
                  v10 = v12 != 0;
                goto LABEL_49;
              }
              v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 72LL))(v27, &v24);
              if ( v10 )
                goto LABEL_44;
              v26 = 0;
              if ( (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v24)(
                     v24,
                     &IID_IXMLDOMElement,
                     &v26) >= 0 )
                break;
LABEL_28:
              v11 = v24;
              if ( v24 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                v11 = 0;
                v24 = 0;
              }
              if ( v26 )
              {
                ((void (__fastcall *)(struct IXMLDOMElement *))v26->lpVtbl->Release)(v26);
                v11 = v24;
              }
            }
            v25 = 0;
            bstrString = 0;
            v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v26->lpVtbl->get_namespaceURI)(v26, &v25);
            if ( v10 >= 0 )
            {
              v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v26->lpVtbl->get_baseName)(
                      v26,
                      &bstrString);
              if ( v10 >= 0 )
              {
                v13 = v25;
                v14 = bstrString;
                if ( !v25 )
                  goto LABEL_24;
                if ( !bstrString )
                {
LABEL_26:
                  if ( v13 )
                    SysFreeString(v13);
                  goto LABEL_28;
                }
                v15 = v25;
                do
                {
                  v16 = *(BSTR)((char *)v15
                              + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                              - (char *)v25);
                  v17 = *v15 - v16;
                  if ( v17 )
                    break;
                  ++v15;
                }
                while ( v16 );
                if ( v17 )
                  goto LABEL_24;
                v18 = bstrString;
                do
                {
                  v19 = *(BSTR)((char *)v18 + (char *)L"Feature" - (char *)bstrString);
                  v20 = *v18 - v19;
                  if ( v20 )
                    break;
                  ++v18;
                }
                while ( v19 );
                if ( v20 )
                {
LABEL_24:
                  if ( v14 )
                  {
                    SysFreeString(v14);
                    v13 = v25;
                    bstrString = 0;
                  }
                  goto LABEL_26;
                }
                v10 = AddToFeatureToListOnVisit(a1, v26, (struct TConstructionData *)v28);
                if ( v10 == 1 )
                {
                  v12 = 1;
                  if ( bstrString )
                  {
                    SysFreeString(bstrString);
                    bstrString = 0;
                  }
                  if ( v25 )
                  {
                    SysFreeString(v25);
                    v25 = 0;
                  }
                  if ( v26 )
                    ((void (__fastcall *)(struct IXMLDOMElement *))v26->lpVtbl->Release)(v26);
LABEL_44:
                  v11 = v24;
                  goto LABEL_45;
                }
              }
            }
            v13 = v25;
            v14 = bstrString;
            goto LABEL_24;
          }
        }
LABEL_49:
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        *((_QWORD *)v8 + 6) = *((_QWORD *)&v29 + 1);
        if ( v10 >= 0 )
        {
LABEL_52:
          v21 = *(_QWORD *)(a3 + 8);
          if ( v21 )
          {
            *(_QWORD *)(v21 + 8) = v8;
            *(_QWORD *)(a3 + 8) = v8;
          }
          else
          {
            *(_QWORD *)(a3 + 8) = v8;
            *(_QWORD *)(a3 + 16) = v8;
          }
        }
      }
    }
  }
  else
  {
    v10 = -2147418113;
  }
  if ( v10 < 0 )
    (**(void (__fastcall ***)(void *, __int64))v8)(v8, 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp-28h+arg_18], rdi
0x180003ee5  mov     [rsp-28h+arg_0], rcx
0x180003eea  push    rbp
0x180003eeb  push    r12
0x180003eed  push    r13
0x180003eef  push    r14
0x180003ef1  push    r15
0x180003ef3  mov     rbp, rsp
0x180003ef6  sub     rsp, 70h
0x180003efa  mov     rdi, rdx
0x180003efd  mov     r15, rcx
0x180003f00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003f07  mov     ecx, 38h ; '8'; unsigned __int64
0x180003f0c  mov     r14d, r9d
0x180003f0f  mov     r13, r8
0x180003f12  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003f17  mov     r12, rax
0x180003f1a  test    rax, rax
0x180003f1d  jz      loc_18000427A
0x180003f23  lea     rax, ??_7TFeatureListEntry@NPrintTicketUtil@@6B@; const NPrintTicketUtil::TFeatureListEntry::`vftable'
0x180003f2a  mov     [rsp+70h+arg_8], rbx
0x180003f32  mov     [r12], rax
0x180003f36  lea     r9, [r12+18h]; unsigned __int16 **
0x180003f3b  xor     eax, eax
0x180003f3d  mov     [rsp+70h+arg_10], rsi
0x180003f45  lea     r8, [r12+10h]; unsigned __int16 **
0x180003f4a  mov     [r12+8], rax
0x180003f4f  mov     rdx, rdi; struct IXMLDOMElement *
0x180003f52  mov     [r12+10h], rax
0x180003f57  mov     rcx, r15; this
0x180003f5a  mov     [r12+18h], rax
0x180003f5f  mov     [r12+20h], rax
0x180003f64  mov     [r12+28h], eax
0x180003f69  mov     [r12+30h], rax
0x180003f6e  mov     [rsp+70h+var_50], eax; int
0x180003f72  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180003f77  cmp     qword ptr [r12+10h], 0
0x180003f7d  mov     r15d, eax
0x180003f80  jz      loc_180004294
0x180003f86  cmp     qword ptr [r12+18h], 0
0x180003f8c  jz      loc_180004294
0x180003f92  test    eax, eax
0x180003f94  js      loc_18000424C
0x180003f9a  cmp     dword ptr [r13+0], 0
0x180003f9f  jnz     short loc_180003FB4
0x180003fa1  mov     rcx, r12; this
0x180003fa4  call    ?ConfigureScopePrefix@TFeatureListEntry@NPrintTicketUtil@@QEAAJXZ; NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix(void)
0x180003fa9  mov     r15d, eax
0x180003fac  test    eax, eax
0x180003fae  js      loc_18000424C
0x180003fb4  test    r14d, r14d
0x180003fb7  jnz     loc_18000423B
0x180003fbd  mov     eax, [r13+0]
0x180003fc1  xor     r14d, r14d
0x180003fc4  mov     rsi, [rbp+arg_0]
0x180003fc8  inc     eax
0x180003fca  mov     [rbp+var_18], eax
0x180003fcd  xorps   xmm0, xmm0
0x180003fd0  mov     [rbp+var_14], r14d
0x180003fd4  mov     [rbp+var_20], r14
0x180003fd8  movdqu  [rbp+var_10], xmm0
0x180003fdd  test    rdi, rdi
0x180003fe0  jz      loc_18000428B
0x180003fe6  mov     rax, [rdi]
0x180003fe9  lea     rdx, [rbp+var_20]
0x180003fed  mov     rcx, rdi
0x180003ff0  mov     rax, [rax+60h]
0x180003ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff9  mov     r15d, eax
0x180003ffc  test    eax, eax
0x180003ffe  js      loc_180004218
0x180004004  mov     rcx, [rbp+var_20]
0x180004008  mov     rax, [rcx]
0x18000400b  mov     rax, [rax+50h]
0x18000400f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004014  mov     r15d, eax
0x180004017  test    eax, eax
0x180004019  js      loc_180004218
0x18000401f  mov     rcx, r14
0x180004022  lea     rdi, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180004029  mov     [rbp+var_38], rcx
0x18000402d  mov     ebx, r14d
0x180004030  test    r15d, r15d
0x180004033  js      loc_1800041F9
0x180004039  mov     rcx, [rbp+var_20]
0x18000403d  lea     rdx, [rbp+var_38]
0x180004041  mov     rax, [rcx]
0x180004044  mov     rax, [rax+48h]
0x180004048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000404d  mov     r15d, eax
0x180004050  test    eax, eax
0x180004052  jnz     loc_1800041F5
0x180004058  mov     rcx, [rbp+var_38]
0x18000405c  lea     r8, [rbp+var_28]
0x180004060  mov     [rbp+var_28], r14
0x180004064  lea     rdx, IID_IXMLDOMElement
0x18000406b  mov     rax, [rcx]
0x18000406e  mov     rax, [rax]
0x180004071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004076  test    eax, eax
0x180004078  js      loc_18000412C
0x18000407e  mov     rcx, [rbp+var_28]
0x180004082  lea     rdx, [rbp+var_30]
0x180004086  mov     [rbp+var_30], r14
0x18000408a  mov     [rbp+bstrString], r14
0x18000408e  mov     rax, [rcx]
0x180004091  mov     rax, [rax+138h]
0x180004098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409d  mov     r15d, eax
0x1800040a0  test    eax, eax
0x1800040a2  js      loc_18000416D
0x1800040a8  mov     rcx, [rbp+var_28]
0x1800040ac  lea     rdx, [rbp+bstrString]
0x1800040b0  mov     rax, [rcx]
0x1800040b3  mov     rax, [rax+148h]
0x1800040ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bf  mov     r15d, eax
0x1800040c2  test    eax, eax
0x1800040c4  js      loc_18000416D
0x1800040ca  mov     r9, [rbp+var_30]
0x1800040ce  mov     r10, [rbp+bstrString]
0x1800040d2  test    r9, r9
0x1800040d5  jz      short loc_180004108
0x1800040d7  test    r10, r10
0x1800040da  jz      short loc_18000411E
0x1800040dc  mov     r8, rdi
0x1800040df  mov     rax, r9
0x1800040e2  sub     r8, r9
0x1800040e5  nop     word ptr [rax+rax+00000000h]
0x1800040f0  movzx   edx, word ptr [rax]
0x1800040f3  movzx   ecx, word ptr [rax+r8]
0x1800040f8  sub     edx, ecx
0x1800040fa  jnz     short loc_180004104
0x1800040fc  add     rax, 2
0x180004100  test    ecx, ecx
0x180004102  jnz     short loc_1800040F0
0x180004104  test    edx, edx
0x180004106  jz      short loc_180004177
0x180004108  test    r10, r10
0x18000410b  jz      short loc_18000411E
0x18000410d  mov     rcx, r10; bstrString
0x180004110  call    cs:__imp_SysFreeString
0x180004116  mov     r9, [rbp+var_30]
0x18000411a  mov     [rbp+bstrString], r14
0x18000411e  test    r9, r9
0x180004121  jz      short loc_18000412C
0x180004123  mov     rcx, r9; bstrString
0x180004126  call    cs:__imp_SysFreeString
0x18000412c  mov     rcx, [rbp+var_38]
0x180004130  test    rcx, rcx
0x180004133  jz      short loc_180004148
0x180004135  mov     rax, [rcx]
0x180004138  mov     rax, [rax+10h]
0x18000413c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004141  mov     rcx, r14
0x180004144  mov     [rbp+var_38], rcx
0x180004148  mov     rdx, [rbp+var_28]
0x18000414c  test    rdx, rdx
0x18000414f  jz      loc_180004030
0x180004155  mov     rax, [rdx]
0x180004158  mov     rcx, rdx
0x18000415b  mov     rax, [rax+10h]
0x18000415f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004164  mov     rcx, [rbp+var_38]
0x180004168  jmp     loc_180004030
0x18000416d  mov     r9, [rbp+var_30]
0x180004171  mov     r10, [rbp+bstrString]
0x180004175  jmp     short loc_180004108
0x180004177  lea     r8, aFeature; "Feature"
0x18000417e  mov     rax, r10
0x180004181  sub     r8, r10
0x180004184  movzx   edx, word ptr [rax]
0x180004187  movzx   ecx, word ptr [rax+r8]
0x18000418c  sub     edx, ecx
0x18000418e  jnz     short loc_180004198
0x180004190  add     rax, 2
0x180004194  test    ecx, ecx
0x180004196  jnz     short loc_180004184
0x180004198  test    edx, edx
0x18000419a  jnz     loc_180004108
0x1800041a0  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x1800041a4  lea     r8, [rbp+var_18]; struct TConstructionData *
0x1800041a8  mov     rcx, rsi; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800041ab  call    ?AddToFeatureToListOnVisit@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUTConstructionData@@@Z; AddToFeatureToListOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,TConstructionData *)
0x1800041b0  mov     r15d, eax
0x1800041b3  cmp     eax, 1
0x1800041b6  jnz     short loc_18000416D
0x1800041b8  mov     rcx, [rbp+bstrString]; bstrString
0x1800041bc  mov     ebx, eax
0x1800041be  test    rcx, rcx
0x1800041c1  jz      short loc_1800041CD
0x1800041c3  call    cs:__imp_SysFreeString
0x1800041c9  mov     [rbp+bstrString], r14
0x1800041cd  mov     rcx, [rbp+var_30]; bstrString
0x1800041d1  test    rcx, rcx
0x1800041d4  jz      short loc_1800041E0
0x1800041d6  call    cs:__imp_SysFreeString
0x1800041dc  mov     [rbp+var_30], r14
0x1800041e0  mov     rcx, [rbp+var_28]
0x1800041e4  test    rcx, rcx
0x1800041e7  jz      short loc_1800041F5
0x1800041e9  mov     rax, [rcx]
0x1800041ec  mov     rax, [rax+10h]
0x1800041f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041f5  mov     rcx, [rbp+var_38]
0x1800041f9  test    rcx, rcx
0x1800041fc  jz      short loc_18000420A
0x1800041fe  mov     rax, [rcx]
0x180004201  mov     rax, [rax+10h]
0x180004205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420a  test    r15d, r15d
0x18000420d  js      short loc_180004218
0x18000420f  test    ebx, ebx
0x180004211  mov     r15d, r14d
0x180004214  setnz   r15b
0x180004218  mov     rcx, [rbp+var_20]
0x18000421c  test    rcx, rcx
0x18000421f  jz      short loc_18000422D
0x180004221  mov     rax, [rcx]
0x180004224  mov     rax, [rax+10h]
0x180004228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422d  mov     rax, qword ptr [rbp+var_10+8]
0x180004231  mov     [r12+30h], rax
0x180004236  test    r15d, r15d
0x180004239  js      short loc_18000424C
0x18000423b  mov     rax, [r13+8]
0x18000423f  test    rax, rax
0x180004242  jz      short loc_180004281
0x180004244  mov     [rax+8], r12
0x180004248  mov     [r13+8], r12
0x18000424c  mov     rsi, [rsp+70h+arg_10]
0x180004254  mov     rbx, [rsp+70h+arg_8]
0x18000425c  test    r15d, r15d
0x18000425f  js      short loc_18000429C
0x180004261  mov     eax, r15d
0x180004264  mov     rdi, [rsp+70h+arg_18]
0x18000426c  add     rsp, 70h
0x180004270  pop     r15
0x180004272  pop     r14
0x180004274  pop     r13
0x180004276  pop     r12
0x180004278  pop     rbp
0x180004279  retn
0x18000427a  mov     eax, 8007000Eh
0x18000427f  jmp     short loc_180004264
0x180004281  mov     [r13+8], r12
0x180004285  mov     [r13+10h], r12
0x180004289  jmp     short loc_18000424C
0x18000428b  mov     rdi, [rsi+18h]
0x18000428f  jmp     loc_180003FE6
0x180004294  mov     r15d, 8000FFFFh
0x18000429a  jmp     short loc_18000424C
0x18000429c  mov     r8, [r12]
0x1800042a0  mov     edx, 1
0x1800042a5  mov     rcx, r12
0x1800042a8  mov     rax, [r8]
0x1800042ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b0  jmp     short loc_180004261
```
