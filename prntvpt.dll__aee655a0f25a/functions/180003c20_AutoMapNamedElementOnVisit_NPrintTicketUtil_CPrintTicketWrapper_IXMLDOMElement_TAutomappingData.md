# AutoMapNamedElementOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,TAutomappingData *)

- ea: `0x180003c20`
- end: `0x180003ed6`
- name: `?AutoMapNamedElementOnVisit@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUTAutomappingData@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(struct NPrintTicketUtil::CPrintTicketWrapper *this, struct IXMLDOMElement *, struct TAutomappingData *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180003708`

## callees

- `0x180003c20`
- `0x180004b00`
- `0x1800056e0`
- `0x180005aa4`
- `0x1800070e0`
- `0x1800076e8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003e13`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e23`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e13`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e23`

## pseudocode

```c
__int64 __fastcall AutoMapNamedElementOnVisit(
        struct NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        struct TAutomappingData *a3)
{
  int NameAttribute; // eax
  BSTR v7; // rbx
  int QName; // edi
  int v9; // eax
  int v10; // esi
  __int64 v11; // r9
  __int64 v12; // r10
  BSTR v13; // rax
  int v14; // ecx
  int v15; // edx
  __int64 v16; // rcx
  BSTR v17; // rax
  int v18; // r9d
  int v19; // edx
  BSTR v20; // rax
  int v21; // r9d
  int v22; // edx
  __int64 v23; // rax
  BSTR v24; // rax
  int v25; // ecx
  int v26; // edx
  OLECHAR *v27; // rcx
  char *v29; // r9
  struct IXMLDOMElement *v30; // r8
  NPrintTicketUtil::CPrintTicketWrapper *v31; // rcx
  unsigned __int16 **v32; // [rsp+28h] [rbp-70h]
  void **v33; // [rsp+30h] [rbp-68h] BYREF
  BSTR bstrString[2]; // [rsp+38h] [rbp-60h] BYREF
  BSTR v35[2]; // [rsp+48h] [rbp-50h] BYREF
  int v36; // [rsp+58h] [rbp-40h]
  __int64 v37; // [rsp+60h] [rbp-38h]
  unsigned __int16 *v38; // [rsp+B8h] [rbp+20h] BYREF

  v33 = &NPrintTicketUtil::TFeatureListEntry::`vftable';
  *(_OWORD *)bstrString = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v37 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, a2, &bstrString[1], v35, 0);
  v7 = bstrString[1];
  QName = NameAttribute;
  if ( bstrString[1] && v35[0] )
  {
    if ( NameAttribute < 0 )
    {
      v10 = v36;
    }
    else
    {
      v9 = NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix((NPrintTicketUtil::TFeatureListEntry *)&v33);
      v10 = v36;
      QName = v9;
      if ( v9 >= 0 && !v36 )
      {
        v27 = bstrString[1];
        if ( !bstrString[1] )
          goto LABEL_46;
        goto LABEL_45;
      }
      v7 = bstrString[1];
    }
    if ( QName >= 0 )
    {
      v11 = *((_QWORD *)a3 + 2);
      v12 = 0;
      if ( v11 )
      {
        while ( !v12 )
        {
          v13 = v7;
          do
          {
            v14 = *(BSTR)((char *)v13 + *(_QWORD *)(v11 + 16) - (_QWORD)v7);
            v15 = *v13 - v14;
            if ( v15 )
              break;
            ++v13;
          }
          while ( v14 );
          if ( !v15 )
          {
            v24 = v35[1];
            do
            {
              v25 = *(BSTR)((char *)v24 + *(_QWORD *)(v11 + 32) - (unsigned __int64)v35[1]);
              v26 = *v24 - v25;
              if ( v26 )
                break;
              ++v24;
            }
            while ( v25 );
            if ( !v26 )
            {
              if ( v10 == 3 )
              {
                if ( (unsigned int)(*(_DWORD *)(v11 + 40) - 1) <= 1 )
                  v12 = v11;
              }
              else if ( v10 == 2 && *(_DWORD *)(v11 + 40) == 1 )
              {
                v12 = v11;
              }
            }
          }
          v11 = *(_QWORD *)(v11 + 8);
          if ( !v11 )
          {
            if ( !v12 )
              goto LABEL_43;
            break;
          }
        }
        v16 = *((_QWORD *)a3 + 1);
        if ( v16 )
        {
          while ( v12 )
          {
            v17 = v7;
            do
            {
              v18 = *(BSTR)((char *)v17 + *(_QWORD *)(v16 + 16) - (_QWORD)v7);
              v19 = *v17 - v18;
              if ( v19 )
                break;
              ++v17;
            }
            while ( v18 );
            if ( !v19 )
            {
              v20 = v35[1];
              do
              {
                v21 = *(BSTR)((char *)v20 + *(_QWORD *)(v16 + 32) - (unsigned __int64)v35[1]);
                v22 = *v20 - v21;
                if ( v22 )
                  break;
                ++v20;
              }
              while ( v21 );
              if ( !v22 )
              {
                if ( v10 == 3 )
                {
                  v23 = 0;
                  if ( *(_DWORD *)(v16 + 40) != 2 )
                    v23 = v12;
                  v12 = v23;
                }
                else if ( v10 == 2 && *(_DWORD *)(v16 + 40) == 1 && *(_DWORD *)(v12 + 40) == 1 )
                {
                  v12 = 0;
                }
              }
            }
            v16 = *(_QWORD *)(v16 + 8);
            if ( !v16 )
            {
              if ( !v12 )
                break;
              goto LABEL_56;
            }
          }
        }
        else
        {
LABEL_56:
          v29 = *(char **)(v12 + 16);
          v30 = *(struct IXMLDOMElement **)(v12 + 24);
          v38 = 0;
          QName = NPrintTicketUtil::CreateQName(this, a2, v30, v29, (unsigned __int16 *)&v38, v32);
          if ( QName >= 0 )
            QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v31, a2, L"name", v38);
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v38);
        }
      }
    }
  }
  else
  {
    QName = -2147418113;
  }
LABEL_43:
  if ( !v7 )
    goto LABEL_46;
  v27 = v7;
LABEL_45:
  SysFreeString(v27);
LABEL_46:
  if ( v35[0] )
    SysFreeString(v35[0]);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x180003c20  mov     r11, rsp
0x180003c23  mov     [r11+8], rbx
0x180003c27  mov     [r11+10h], rbp
0x180003c2b  push    rsi
0x180003c2c  push    rdi
0x180003c2d  push    r12
0x180003c2f  push    r14
0x180003c31  push    r15
0x180003c33  sub     rsp, 70h
0x180003c37  xor     r12d, r12d
0x180003c3a  lea     rax, ??_7TFeatureListEntry@NPrintTicketUtil@@6B@; const NPrintTicketUtil::TFeatureListEntry::`vftable'
0x180003c41  mov     [r11-68h], rax
0x180003c45  lea     r9, [r11-50h]; unsigned __int16 **
0x180003c49  xorps   xmm0, xmm0
0x180003c4c  mov     [r11-78h], r12d
0x180003c50  movdqu  xmmword ptr [rsp+98h+bstrString], xmm0
0x180003c56  mov     rbp, r8
0x180003c59  lea     r8, [r11-58h]; unsigned __int16 **
0x180003c5d  xorps   xmm1, xmm1
0x180003c60  mov     r14, rdx
0x180003c63  movdqu  xmmword ptr [rsp+98h+var_50], xmm1
0x180003c69  mov     [r11-40h], r12d
0x180003c6d  mov     r15, rcx
0x180003c70  mov     [r11-38h], r12
0x180003c74  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180003c79  mov     rbx, [rsp+98h+bstrString+8]
0x180003c7e  mov     edi, eax
0x180003c80  test    rbx, rbx
0x180003c83  jz      loc_180003ECC
0x180003c89  cmp     [rsp+98h+var_50], r12
0x180003c8e  jz      loc_180003ECC
0x180003c94  test    eax, eax
0x180003c96  js      loc_180003E44
0x180003c9c  lea     rcx, [rsp+98h+var_68]; this
0x180003ca1  call    ?ConfigureScopePrefix@TFeatureListEntry@NPrintTicketUtil@@QEAAJXZ; NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix(void)
0x180003ca6  mov     esi, [rsp+98h+var_40]
0x180003caa  mov     edi, eax
0x180003cac  test    eax, eax
0x180003cae  js      short loc_180003CB8
0x180003cb0  test    esi, esi
0x180003cb2  jz      loc_180003DFF
0x180003cb8  mov     rbx, [rsp+98h+bstrString+8]
0x180003cbd  test    edi, edi
0x180003cbf  js      loc_180003E0B
0x180003cc5  mov     r9, [rbp+10h]
0x180003cc9  mov     r10, r12
0x180003ccc  test    r9, r9
0x180003ccf  jz      loc_180003E0B
0x180003cd5  mov     r11, [rsp+98h+var_50+8]
0x180003cda  nop     word ptr [rax+rax+00h]
0x180003ce0  test    r10, r10
0x180003ce3  jnz     short loc_180003D1E
0x180003ce5  mov     r8, [r9+10h]
0x180003ce9  mov     rax, rbx
0x180003cec  sub     r8, rbx
0x180003cef  nop
0x180003cf0  movzx   edx, word ptr [rax]
0x180003cf3  movzx   ecx, word ptr [rax+r8]
0x180003cf8  sub     edx, ecx
0x180003cfa  jnz     short loc_180003D04
0x180003cfc  add     rax, 2
0x180003d00  test    ecx, ecx
0x180003d02  jnz     short loc_180003CF0
0x180003d04  test    edx, edx
0x180003d06  jz      loc_180003DA0
0x180003d0c  mov     r9, [r9+8]
0x180003d10  test    r9, r9
0x180003d13  jnz     short loc_180003CE0
0x180003d15  test    r10, r10
0x180003d18  jz      loc_180003E0B
0x180003d1e  mov     rcx, [rbp+8]
0x180003d22  test    rcx, rcx
0x180003d25  jz      loc_180003E73
0x180003d2b  test    r10, r10
0x180003d2e  jz      loc_180003E0B
0x180003d34  mov     r8, [rcx+10h]
0x180003d38  mov     rax, rbx
0x180003d3b  sub     r8, rbx
0x180003d3e  movzx   edx, word ptr [rax]
0x180003d41  movzx   r9d, word ptr [rax+r8]
0x180003d46  sub     edx, r9d
0x180003d49  jnz     short loc_180003D54
0x180003d4b  add     rax, 2
0x180003d4f  test    r9d, r9d
0x180003d52  jnz     short loc_180003D3E
0x180003d54  test    edx, edx
0x180003d56  jnz     loc_180003E61
0x180003d5c  mov     r8, [rcx+20h]
0x180003d60  mov     rax, r11
0x180003d63  sub     r8, r11
0x180003d66  movzx   edx, word ptr [rax]
0x180003d69  movzx   r9d, word ptr [rax+r8]
0x180003d6e  sub     edx, r9d
0x180003d71  jnz     short loc_180003D7C
0x180003d73  add     rax, 2
0x180003d77  test    r9d, r9d
0x180003d7a  jnz     short loc_180003D66
0x180003d7c  test    edx, edx
0x180003d7e  jnz     loc_180003E61
0x180003d84  cmp     esi, 3
0x180003d87  jnz     loc_180003E4D
0x180003d8d  cmp     dword ptr [rcx+28h], 2
0x180003d91  mov     rax, r12
0x180003d94  cmovnz  rax, r10
0x180003d98  mov     r10, rax
0x180003d9b  jmp     loc_180003E61
0x180003da0  mov     r8, [r9+20h]
0x180003da4  mov     rax, r11
0x180003da7  sub     r8, r11
0x180003daa  nop     word ptr [rax+rax+00h]
0x180003db0  movzx   edx, word ptr [rax]
0x180003db3  movzx   ecx, word ptr [rax+r8]
0x180003db8  sub     edx, ecx
0x180003dba  jnz     short loc_180003DC4
0x180003dbc  add     rax, 2
0x180003dc0  test    ecx, ecx
0x180003dc2  jnz     short loc_180003DB0
0x180003dc4  test    edx, edx
0x180003dc6  jnz     loc_180003D0C
0x180003dcc  cmp     esi, 3
0x180003dcf  jz      short loc_180003DE8
0x180003dd1  cmp     esi, 2
0x180003dd4  jnz     loc_180003D0C
0x180003dda  cmp     dword ptr [r9+28h], 1
0x180003ddf  cmovz   r10, r9
0x180003de3  jmp     loc_180003D0C
0x180003de8  mov     eax, [r9+28h]
0x180003dec  dec     eax
0x180003dee  cmp     eax, 1
0x180003df1  ja      loc_180003D0C
0x180003df7  mov     r10, r9
0x180003dfa  jmp     loc_180003D0C
0x180003dff  mov     rcx, [rsp+98h+bstrString+8]
0x180003e04  test    rcx, rcx
0x180003e07  jz      short loc_180003E19
0x180003e09  jmp     short loc_180003E13
0x180003e0b  test    rbx, rbx
0x180003e0e  jz      short loc_180003E19
0x180003e10  mov     rcx, rbx; bstrString
0x180003e13  call    cs:__imp_SysFreeString
0x180003e19  mov     rcx, [rsp+98h+var_50]; bstrString
0x180003e1e  test    rcx, rcx
0x180003e21  jz      short loc_180003E29
0x180003e23  call    cs:__imp_SysFreeString
0x180003e29  lea     r11, [rsp+98h+var_28]
0x180003e2e  mov     eax, edi
0x180003e30  mov     rbx, [r11+30h]
0x180003e34  mov     rbp, [r11+38h]
0x180003e38  mov     rsp, r11
0x180003e3b  pop     r15
0x180003e3d  pop     r14
0x180003e3f  pop     r12
0x180003e41  pop     rdi
0x180003e42  pop     rsi
0x180003e43  retn
0x180003e44  mov     esi, [rsp+98h+var_40]
0x180003e48  jmp     loc_180003CBD
0x180003e4d  cmp     esi, 2
0x180003e50  jnz     short loc_180003E61
0x180003e52  cmp     dword ptr [rcx+28h], 1
0x180003e56  jnz     short loc_180003E61
0x180003e58  cmp     dword ptr [r10+28h], 1
0x180003e5d  cmovz   r10, r12
0x180003e61  mov     rcx, [rcx+8]
0x180003e65  test    rcx, rcx
0x180003e68  jnz     loc_180003D2B
0x180003e6e  test    r10, r10
0x180003e71  jz      short loc_180003E0B
0x180003e73  mov     r9, [r10+10h]; unsigned __int16 *
0x180003e77  lea     rax, [rsp+98h+arg_18]
0x180003e7f  mov     r8, [r10+18h]; struct IXMLDOMElement *
0x180003e83  mov     rdx, r14; struct IXMLDOMElement *
0x180003e86  mov     rcx, r15; this
0x180003e89  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180003e8e  mov     [rsp+98h+arg_18], r12
0x180003e96  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180003e9b  mov     edi, eax
0x180003e9d  test    eax, eax
0x180003e9f  js      short loc_180003EBA
0x180003ea1  mov     r9, [rsp+98h+arg_18]; unsigned __int16 *
0x180003ea9  lea     r8, aName; "name"
0x180003eb0  mov     rdx, r14; struct IXMLDOMElement *
0x180003eb3  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180003eb8  mov     edi, eax
0x180003eba  lea     rcx, [rsp+98h+arg_18]
0x180003ec2  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180003ec7  jmp     loc_180003E0B
0x180003ecc  mov     edi, 8000FFFFh
0x180003ed1  jmp     loc_180003E0B
```
