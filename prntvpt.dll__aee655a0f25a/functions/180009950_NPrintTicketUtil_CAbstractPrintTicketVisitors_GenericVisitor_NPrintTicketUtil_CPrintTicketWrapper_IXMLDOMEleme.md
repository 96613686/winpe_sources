# NPrintTicketUtil::CAbstractPrintTicketVisitors::GenericVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x180009950`
- end: `0x180009bfe`
- name: `?GenericVisitor@CAbstractPrintTicketVisitors@NPrintTicketUtil@@UEAAJPEAVCPrintTicketWrapper@2@PEAUIXMLDOMElement@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CAbstractPrintTicketVisitors *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009950`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009b29`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b39`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b29`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b39`

## string_xrefs

- `0x1800099a2`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CAbstractPrintTicketVisitors::GenericVisitor(
        NPrintTicketUtil::CAbstractPrintTicketVisitors *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  BSTR v9; // rax
  int v10; // ecx
  int v11; // edx
  struct IXMLDOMElementVtbl *v12; // rax
  BSTR v13; // r9
  BSTR v14; // rax
  int v15; // ecx
  int v16; // edx
  BSTR v17; // rax
  int v18; // ecx
  int v19; // edx
  BSTR v20; // rax
  int v21; // ecx
  int v22; // edx
  BSTR v23; // rax
  int v24; // ecx
  int v25; // edx
  BSTR v26; // rax
  int v27; // ecx
  int v28; // edx
  BSTR v29; // rax
  int v30; // ecx
  int v31; // edx
  unsigned int v32; // eax
  BSTR v34; // rax
  int v35; // ecx
  int v36; // edx
  int v37; // eax
  int v38; // ecx
  __int64 v39; // rax
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF
  BSTR v41; // [rsp+58h] [rbp+20h] BYREF

  lpVtbl = a3->lpVtbl;
  v41 = 0;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))lpVtbl->get_namespaceURI)(a3, &v41);
  v8 = v7;
  if ( v7 == 1 )
    goto LABEL_54;
  if ( v7 )
    goto LABEL_36;
  v9 = v41;
  do
  {
    v10 = *(BSTR)((char *)v9
                + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                - (char *)v41);
    v11 = *v9 - v10;
    if ( v11 )
      break;
    ++v9;
  }
  while ( v10 );
  if ( v11 )
  {
LABEL_54:
    v8 = -2147155967;
  }
  else
  {
    v12 = a3->lpVtbl;
    bstrString = 0;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v12->get_baseName)(a3, &bstrString);
    if ( !v8 )
    {
      v13 = bstrString;
      v14 = bstrString;
      do
      {
        v15 = *(BSTR)((char *)v14 + (char *)L"Feature" - (char *)bstrString);
        v16 = *v14 - v15;
        if ( v16 )
          break;
        ++v14;
      }
      while ( v15 );
      if ( v16 )
      {
        v17 = bstrString;
        do
        {
          v18 = *(BSTR)((char *)v17 + (char *)L"Option" - (char *)bstrString);
          v19 = *v17 - v18;
          if ( v19 )
            break;
          ++v17;
        }
        while ( v18 );
        if ( v19 )
        {
          v20 = bstrString;
          do
          {
            v21 = *(BSTR)((char *)v20 + (char *)L"ParameterInit" - (char *)bstrString);
            v22 = *v20 - v21;
            if ( v22 )
              break;
            ++v20;
          }
          while ( v21 );
          if ( v22 )
          {
            v23 = bstrString;
            do
            {
              v24 = *(BSTR)((char *)v23 + (char *)L"Property" - (char *)bstrString);
              v25 = *v23 - v24;
              if ( v25 )
                break;
              ++v23;
            }
            while ( v24 );
            if ( v25 )
            {
              v26 = bstrString;
              do
              {
                v27 = *(BSTR)((char *)v26 + (char *)L"ScoredProperty" - (char *)bstrString);
                v28 = *v26 - v27;
                if ( v28 )
                  break;
                ++v26;
              }
              while ( v27 );
              if ( v28 )
              {
                v29 = bstrString;
                do
                {
                  v30 = *(BSTR)((char *)v29 + (char *)&stru_180026B28 - (char *)bstrString);
                  v31 = *v29 - v30;
                  if ( v31 )
                    break;
                  ++v29;
                }
                while ( v30 );
                if ( v31 )
                {
                  v34 = bstrString;
                  do
                  {
                    v35 = *(BSTR)((char *)v34 + (char *)L"ParameterRef" - (char *)bstrString);
                    v36 = *v34 - v35;
                    if ( v36 )
                      break;
                    ++v34;
                  }
                  while ( v35 );
                  if ( v36 )
                  {
                    do
                    {
                      v37 = *(BSTR)((char *)v13 + (char *)L"ParameterDef" - (char *)bstrString);
                      v38 = *v13 - v37;
                      if ( v38 )
                        break;
                      ++v13;
                    }
                    while ( v37 );
                    v39 = *(_QWORD *)this;
                    if ( v38 )
                      v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(v39 + 72))(
                              this,
                              a2,
                              a3);
                    else
                      v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(v39 + 64))(
                              this,
                              a2,
                              a3);
                  }
                  else
                  {
                    v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 56LL))(
                            this,
                            a2,
                            a3);
                  }
                }
                else
                {
                  v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 40LL))(
                          this,
                          a2,
                          a3);
                }
              }
              else
              {
                v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 32LL))(
                        this,
                        a2,
                        a3);
              }
            }
            else
            {
              v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 24LL))(
                      this,
                      a2,
                      a3);
            }
          }
          else
          {
            v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 48LL))(
                    this,
                    a2,
                    a3);
          }
        }
        else
        {
          v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 16LL))(
                  this,
                  a2,
                  a3);
        }
      }
      else
      {
        v32 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CAbstractPrintTicketVisitors *, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *))(*(_QWORD *)this + 8LL))(
                this,
                a2,
                a3);
      }
      v8 = v32;
    }
    if ( bstrString )
      SysFreeString(bstrString);
  }
LABEL_36:
  if ( v41 )
    SysFreeString(v41);
  return v8;
}

```

## disassembly

```asm
0x180009950  mov     [rsp+arg_0], rbx
0x180009955  mov     [rsp+arg_8], rbp
0x18000995a  push    rsi
0x18000995b  push    rdi
0x18000995c  push    r14
0x18000995e  sub     rsp, 20h
0x180009962  mov     rax, [r8]
0x180009965  mov     rbp, rdx
0x180009968  mov     rsi, rcx
0x18000996b  lea     rdx, [rsp+38h+arg_18]
0x180009970  xor     r14d, r14d
0x180009973  mov     rcx, r8
0x180009976  mov     rdi, r8
0x180009979  mov     [rsp+38h+arg_18], r14
0x18000997e  mov     rax, [rax+138h]
0x180009985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998a  mov     ebx, eax
0x18000998c  cmp     eax, 1
0x18000998f  jz      loc_180009BF4
0x180009995  test    eax, eax
0x180009997  jnz     loc_180009B2F
0x18000999d  mov     rax, [rsp+38h+arg_18]
0x1800099a2  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x1800099a9  sub     r8, rax
0x1800099ac  nop     dword ptr [rax+00h]
0x1800099b0  movzx   edx, word ptr [rax]
0x1800099b3  movzx   ecx, word ptr [rax+r8]
0x1800099b8  sub     edx, ecx
0x1800099ba  jnz     short loc_1800099C4
0x1800099bc  add     rax, 2
0x1800099c0  test    ecx, ecx
0x1800099c2  jnz     short loc_1800099B0
0x1800099c4  test    edx, edx
0x1800099c6  jnz     loc_180009BF4
0x1800099cc  mov     rax, [rdi]
0x1800099cf  lea     rdx, [rsp+38h+bstrString]
0x1800099d4  mov     rcx, rdi
0x1800099d7  mov     [rsp+38h+bstrString], r14
0x1800099dc  mov     rax, [rax+148h]
0x1800099e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099e8  mov     ebx, eax
0x1800099ea  test    eax, eax
0x1800099ec  jnz     loc_180009B1F
0x1800099f2  mov     r9, [rsp+38h+bstrString]
0x1800099f7  lea     r8, aFeature; "Feature"
0x1800099fe  mov     rax, r9
0x180009a01  sub     r8, r9
0x180009a04  movzx   edx, word ptr [rax]
0x180009a07  movzx   ecx, word ptr [rax+r8]
0x180009a0c  sub     edx, ecx
0x180009a0e  jnz     short loc_180009A18
0x180009a10  add     rax, 2
0x180009a14  test    ecx, ecx
0x180009a16  jnz     short loc_180009A04
0x180009a18  test    edx, edx
0x180009a1a  jz      loc_180009BC7
0x180009a20  lea     r8, aOption; "Option"
0x180009a27  mov     rax, r9
0x180009a2a  sub     r8, r9
0x180009a2d  nop     dword ptr [rax]
0x180009a30  movzx   edx, word ptr [rax]
0x180009a33  movzx   ecx, word ptr [rax+r8]
0x180009a38  sub     edx, ecx
0x180009a3a  jnz     short loc_180009A44
0x180009a3c  add     rax, 2
0x180009a40  test    ecx, ecx
0x180009a42  jnz     short loc_180009A30
0x180009a44  test    edx, edx
0x180009a46  jz      loc_180009B5D
0x180009a4c  lea     r8, aParameterinit; "ParameterInit"
0x180009a53  mov     rax, r9
0x180009a56  sub     r8, r9
0x180009a59  nop     dword ptr [rax+00000000h]
0x180009a60  movzx   edx, word ptr [rax]
0x180009a63  movzx   ecx, word ptr [rax+r8]
0x180009a68  sub     edx, ecx
0x180009a6a  jnz     short loc_180009A74
0x180009a6c  add     rax, 2
0x180009a70  test    ecx, ecx
0x180009a72  jnz     short loc_180009A60
0x180009a74  test    edx, edx
0x180009a76  jz      loc_180009BE8
0x180009a7c  lea     r8, aProperty; "Property"
0x180009a83  mov     rax, r9
0x180009a86  sub     r8, r9
0x180009a89  nop     dword ptr [rax+00000000h]
0x180009a90  movzx   edx, word ptr [rax]
0x180009a93  movzx   ecx, word ptr [rax+r8]
0x180009a98  sub     edx, ecx
0x180009a9a  jnz     short loc_180009AA4
0x180009a9c  add     rax, 2
0x180009aa0  test    ecx, ecx
0x180009aa2  jnz     short loc_180009A90
0x180009aa4  test    edx, edx
0x180009aa6  jz      loc_180009B54
0x180009aac  lea     r8, aScoredproperty_0; "ScoredProperty"
0x180009ab3  mov     rax, r9
0x180009ab6  sub     r8, r9
0x180009ab9  nop     dword ptr [rax+00000000h]
0x180009ac0  movzx   edx, word ptr [rax]
0x180009ac3  movzx   ecx, word ptr [rax+r8]
0x180009ac8  sub     edx, ecx
0x180009aca  jnz     short loc_180009AD4
0x180009acc  add     rax, 2
0x180009ad0  test    ecx, ecx
0x180009ad2  jnz     short loc_180009AC0
0x180009ad4  test    edx, edx
0x180009ad6  jz      loc_180009B66
0x180009adc  lea     r8, stru_180026B28
0x180009ae3  mov     rax, r9
0x180009ae6  sub     r8, r9
0x180009ae9  nop     dword ptr [rax+00000000h]
0x180009af0  movzx   edx, word ptr [rax]
0x180009af3  movzx   ecx, word ptr [rax+r8]
0x180009af8  sub     edx, ecx
0x180009afa  jnz     short loc_180009B04
0x180009afc  add     rax, 2
0x180009b00  test    ecx, ecx
0x180009b02  jnz     short loc_180009AF0
0x180009b04  test    edx, edx
0x180009b06  jnz     short loc_180009B6F
0x180009b08  mov     rax, [rsi]
0x180009b0b  mov     rax, [rax+28h]
0x180009b0f  mov     r8, rdi
0x180009b12  mov     rdx, rbp
0x180009b15  mov     rcx, rsi
0x180009b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b1d  mov     ebx, eax
0x180009b1f  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180009b24  test    rcx, rcx
0x180009b27  jz      short loc_180009B2F
0x180009b29  call    cs:__imp_SysFreeString
0x180009b2f  mov     rcx, [rsp+38h+arg_18]; bstrString
0x180009b34  test    rcx, rcx
0x180009b37  jz      short loc_180009B3F
0x180009b39  call    cs:__imp_SysFreeString
0x180009b3f  mov     rbp, [rsp+38h+arg_8]
0x180009b44  mov     eax, ebx
0x180009b46  mov     rbx, [rsp+38h+arg_0]
0x180009b4b  add     rsp, 20h
0x180009b4f  pop     r14
0x180009b51  pop     rdi
0x180009b52  pop     rsi
0x180009b53  retn
0x180009b54  mov     rax, [rsi]
0x180009b57  mov     rax, [rax+18h]
0x180009b5b  jmp     short loc_180009B0F
0x180009b5d  mov     rax, [rsi]
0x180009b60  mov     rax, [rax+10h]
0x180009b64  jmp     short loc_180009B0F
0x180009b66  mov     rax, [rsi]
0x180009b69  mov     rax, [rax+20h]
0x180009b6d  jmp     short loc_180009B0F
0x180009b6f  lea     r8, aParameterref; "ParameterRef"
0x180009b76  mov     rax, r9
0x180009b79  sub     r8, r9
0x180009b7c  nop     dword ptr [rax+00h]
0x180009b80  movzx   edx, word ptr [rax]
0x180009b83  movzx   ecx, word ptr [rax+r8]
0x180009b88  sub     edx, ecx
0x180009b8a  jnz     short loc_180009B94
0x180009b8c  add     rax, 2
0x180009b90  test    ecx, ecx
0x180009b92  jnz     short loc_180009B80
0x180009b94  test    edx, edx
0x180009b96  jz      short loc_180009BDC
0x180009b98  lea     rdx, aParameterdef; "ParameterDef"
0x180009b9f  sub     rdx, r9
0x180009ba2  movzx   ecx, word ptr [r9]
0x180009ba6  movzx   eax, word ptr [r9+rdx]
0x180009bab  sub     ecx, eax
0x180009bad  jnz     short loc_180009BB7
0x180009baf  add     r9, 2
0x180009bb3  test    eax, eax
0x180009bb5  jnz     short loc_180009BA2
0x180009bb7  mov     rax, [rsi]
0x180009bba  test    ecx, ecx
0x180009bbc  jnz     short loc_180009BD3
0x180009bbe  mov     rax, [rax+40h]
0x180009bc2  jmp     loc_180009B0F
0x180009bc7  mov     rax, [rsi]
0x180009bca  mov     rax, [rax+8]
0x180009bce  jmp     loc_180009B0F
0x180009bd3  mov     rax, [rax+48h]
0x180009bd7  jmp     loc_180009B0F
0x180009bdc  mov     rax, [rsi]
0x180009bdf  mov     rax, [rax+38h]
0x180009be3  jmp     loc_180009B0F
0x180009be8  mov     rax, [rsi]
0x180009beb  mov     rax, [rax+30h]
0x180009bef  jmp     loc_180009B0F
0x180009bf4  mov     ebx, 80050001h
0x180009bf9  jmp     loc_180009B2F
```
