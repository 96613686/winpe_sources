# CDomNode::PrintStartElement(IXmlWriter *)

- ea: `0x180024b40`
- end: `0x180024d02`
- name: `?PrintStartElement@CDomNode@@UEAAJPEAUIXmlWriter@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CDomNode *__hidden this, struct IXmlWriter *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180024b40`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180024c1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180024c32`
- `OLEAUT32!__imp_SysFreeString` at `0x180024cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ce2`
- `OLEAUT32!__imp_SysFreeString` at `0x180024c1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180024c32`
- `OLEAUT32!__imp_SysFreeString` at `0x180024cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ce2`

## string_xrefs

- `0x180024b80`: `xmlns`
- `0x180024c62`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDomNode::PrintStartElement(CDomNode *this, struct IXmlWriter *a2)
{
  OLECHAR *v4; // rcx
  int v5; // edi
  _QWORD *v6; // r8
  unsigned int v7; // r14d
  OLECHAR *v8; // rbx
  unsigned int v10; // [rsp+68h] [rbp+38h] BYREF
  BSTR v11; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  bstrString = 0;
  v4 = 0;
  v11 = 0;
  v10 = 0;
  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(CDomNode *, const wchar_t *, BSTR *))(*(_QWORD *)this + 88LL))(this, L"xmlns", &v11);
    if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147023728 )
    {
      v6 = (_QWORD *)((char *)this + 128);
      if ( *((_QWORD *)this + 19) > 7u )
        v6 = (_QWORD *)*v6;
      v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, _QWORD *, BSTR))a2->lpVtbl->WriteStartElement)(
             a2,
             0,
             v6,
             v11);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(CDomNode *, unsigned int *))(*(_QWORD *)this + 112LL))(this, &v10);
        if ( v5 >= 0 )
        {
          if ( v10 )
          {
            v7 = 0;
            v8 = bstrString;
            do
            {
              SysFreeString(v8);
              bstrString = 0;
              SysFreeString(v11);
              v11 = 0;
              v5 = (*(__int64 (__fastcall **)(CDomNode *, _QWORD, BSTR *))(*(_QWORD *)this + 120LL))(
                     this,
                     v7,
                     &bstrString);
              if ( v5 < 0 )
                break;
              v8 = bstrString;
              if ( wcscmp_0(bstrString, L"xmlns") )
              {
                v5 = (*(__int64 (__fastcall **)(CDomNode *, OLECHAR *, BSTR *))(*(_QWORD *)this + 88LL))(this, v8, &v11);
                if ( v5 < 0 )
                  break;
                v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, BSTR, _QWORD, BSTR))a2->lpVtbl->WriteAttributeString)(
                       a2,
                       0,
                       bstrString,
                       0,
                       v11);
                if ( v5 < 0 )
                  break;
                v8 = bstrString;
              }
              ++v7;
            }
            while ( v7 < v10 );
          }
        }
      }
    }
    v4 = v11;
  }
  else
  {
    v5 = -2147024809;
  }
  SysFreeString(v4);
  SysFreeString(bstrString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024b40  mov     [rsp-28h+arg_0], rbx
0x180024b45  push    rbp
0x180024b46  push    rsi
0x180024b47  push    rdi
0x180024b48  push    r14
0x180024b4a  push    r15
0x180024b4c  mov     rbp, rsp
0x180024b4f  sub     rsp, 30h
0x180024b53  mov     r15, rdx
0x180024b56  mov     rsi, rcx
0x180024b59  mov     [rbp+bstrString], 0
0x180024b61  xor     ecx, ecx
0x180024b63  mov     [rbp+arg_10], rcx
0x180024b67  mov     [rbp+arg_8], ecx
0x180024b6a  test    rdx, rdx
0x180024b6d  jnz     short loc_180024B79
0x180024b6f  mov     edi, 80070057h
0x180024b74  jmp     loc_180024CD1
0x180024b79  mov     rax, [rsi]
0x180024b7c  lea     r8, [rbp+arg_10]
0x180024b80  lea     rdx, aXmlns; "xmlns"
0x180024b87  mov     rcx, rsi
0x180024b8a  mov     rax, [rax+58h]
0x180024b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b93  mov     edi, eax
0x180024b95  mov     eax, 80000000h
0x180024b9a  lea     ecx, [rdi+rax]
0x180024b9d  test    eax, ecx
0x180024b9f  jnz     short loc_180024BAD
0x180024ba1  cmp     edi, 80070490h
0x180024ba7  jnz     loc_180024CCD
0x180024bad  mov     rax, [r15]
0x180024bb0  lea     r8, [rsi+80h]
0x180024bb7  cmp     qword ptr [r8+18h], 7
0x180024bbc  jbe     short loc_180024BC1
0x180024bbe  mov     r8, [r8]
0x180024bc1  mov     r9, [rbp+arg_10]
0x180024bc5  xor     edx, edx
0x180024bc7  mov     rcx, r15
0x180024bca  mov     rax, [rax+0D8h]
0x180024bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bd6  mov     edi, eax
0x180024bd8  test    eax, eax
0x180024bda  js      loc_180024CCD
0x180024be0  mov     rax, [rsi]
0x180024be3  lea     rdx, [rbp+arg_8]
0x180024be7  mov     rcx, rsi
0x180024bea  mov     rax, [rax+70h]
0x180024bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bf3  mov     edi, eax
0x180024bf5  test    eax, eax
0x180024bf7  js      loc_180024CCD
0x180024bfd  mov     eax, [rbp+arg_8]
0x180024c00  test    eax, eax
0x180024c02  jz      loc_180024CCD
0x180024c08  xor     r14d, r14d
0x180024c0b  test    eax, eax
0x180024c0d  jz      loc_180024CCD
0x180024c13  mov     rbx, [rbp+bstrString]
0x180024c17  mov     rcx, rbx; bstrString
0x180024c1a  call    cs:__imp_SysFreeString
0x180024c21  nop     dword ptr [rax+rax+00h]
0x180024c26  mov     [rbp+bstrString], 0
0x180024c2e  mov     rcx, [rbp+arg_10]; bstrString
0x180024c32  call    cs:__imp_SysFreeString
0x180024c39  nop     dword ptr [rax+rax+00h]
0x180024c3e  mov     [rbp+arg_10], 0
0x180024c46  mov     rax, [rsi]
0x180024c49  lea     r8, [rbp+bstrString]
0x180024c4d  mov     edx, r14d
0x180024c50  mov     rcx, rsi
0x180024c53  mov     rax, [rax+78h]
0x180024c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c5c  mov     edi, eax
0x180024c5e  test    eax, eax
0x180024c60  js      short loc_180024CCD
0x180024c62  lea     rdx, aXmlns; "xmlns"
0x180024c69  mov     rbx, [rbp+bstrString]
0x180024c6d  mov     rcx, rbx; String1
0x180024c70  call    wcscmp_0
0x180024c75  test    eax, eax
0x180024c77  jz      short loc_180024CC0
0x180024c79  mov     rax, [rsi]
0x180024c7c  lea     r8, [rbp+arg_10]
0x180024c80  mov     rdx, rbx
0x180024c83  mov     rcx, rsi
0x180024c86  mov     rax, [rax+58h]
0x180024c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c8f  mov     edi, eax
0x180024c91  test    eax, eax
0x180024c93  js      short loc_180024CCD
0x180024c95  mov     rcx, [rbp+arg_10]
0x180024c99  mov     rax, [r15]
0x180024c9c  mov     [rsp+30h+var_10], rcx
0x180024ca1  xor     r9d, r9d
0x180024ca4  mov     r8, [rbp+bstrString]
0x180024ca8  xor     edx, edx
0x180024caa  mov     rcx, r15
0x180024cad  mov     rax, [rax+38h]
0x180024cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cb6  mov     edi, eax
0x180024cb8  test    eax, eax
0x180024cba  js      short loc_180024CCD
0x180024cbc  mov     rbx, [rbp+bstrString]
0x180024cc0  inc     r14d
0x180024cc3  cmp     r14d, [rbp+arg_8]
0x180024cc7  jb      loc_180024C17
0x180024ccd  mov     rcx, [rbp+arg_10]; bstrString
0x180024cd1  call    cs:__imp_SysFreeString
0x180024cd8  nop     dword ptr [rax+rax+00h]
0x180024cdd  nop
0x180024cde  mov     rcx, [rbp+bstrString]; bstrString
0x180024ce2  call    cs:__imp_SysFreeString
0x180024ce9  nop     dword ptr [rax+rax+00h]
0x180024cee  mov     eax, edi
0x180024cf0  mov     rbx, [rsp+30h+arg_0]
0x180024cf5  add     rsp, 30h
0x180024cf9  pop     r15
0x180024cfb  pop     r14
0x180024cfd  pop     rdi
0x180024cfe  pop     rsi
0x180024cff  pop     rbp
0x180024d00  retn
```
