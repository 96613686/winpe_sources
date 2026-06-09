# NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x1800019f0`
- end: `0x18000207b`
- name: `?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z`
- size: `1675`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001310`
- `0x1800014e0`
- `0x180001668`
- `0x180001810`
- `0x1800022d0`
- `0x18000e364`
- `0x18001d7c0`
- `0x18001d878`
- `0x180020020`
- `0x180020910`
- `0x180021738`

## callees

- `0x1800019f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001e83`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001e83`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e44`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e99`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e44`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e99`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180001ecb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180001f77`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180001ecb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180001f77`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ae5`
- `OLEAUT32!__imp_SysFreeString` at `0x180001afb`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ca8`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d38`
- `OLEAUT32!__imp_SysFreeString` at `0x180001dd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180001de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180001f46`
- `OLEAUT32!__imp_SysFreeString` at `0x180002059`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ae5`
- `OLEAUT32!__imp_SysFreeString` at `0x180001afb`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ca8`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d38`
- `OLEAUT32!__imp_SysFreeString` at `0x180001dd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180001de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180001f46`
- `OLEAUT32!__imp_SysFreeString` at `0x180002059`

## string_xrefs

- `0x180001a3c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180001aae`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char *a5,
        const unsigned __int16 *a6,
        struct IXMLDOMElement **a7)
{
  const unsigned __int16 *v7; // rbx
  const unsigned __int16 *v8; // rcx
  struct IXMLDOMElement **v9; // r15
  int v10; // r12d
  int v12; // eax
  int v13; // edx
  BSTR v14; // rcx
  unsigned int v15; // r13d
  BSTR v16; // r8
  int v17; // eax
  int v18; // ecx
  struct IXMLDOMElement *v19; // r14
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  OLECHAR *v21; // rdi
  OLECHAR *v22; // rbx
  OLECHAR *v23; // rsi
  OLECHAR *v24; // rax
  int v25; // ecx
  int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // rdx
  OLECHAR *v29; // rsi
  wchar_t *v30; // rax
  const OLECHAR *v31; // rax
  int v32; // r15d
  bool v33; // sf
  int v34; // eax
  BSTR v35; // rax
  OLECHAR *v36; // rax
  int v37; // ecx
  int v38; // edx
  struct IXMLDOMElement *v39; // rcx
  BSTR Str; // [rsp+38h] [rbp-51h] BYREF
  struct IXMLDOMElement *v41; // [rsp+40h] [rbp-49h] BYREF
  __int64 v42; // [rsp+48h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-39h] BYREF
  __int64 v44; // [rsp+58h] [rbp-31h] BYREF
  __int64 v45; // [rsp+60h] [rbp-29h] BYREF
  __int64 v46; // [rsp+68h] [rbp-21h] BYREF
  BSTR v47; // [rsp+70h] [rbp-19h] BYREF
  __int64 v48; // [rsp+78h] [rbp-11h] BYREF
  const unsigned __int16 *v49; // [rsp+80h] [rbp-9h]
  int v51; // [rsp+E0h] [rbp+57h] BYREF
  const unsigned __int16 *v52; // [rsp+E8h] [rbp+5Fh]
  const unsigned __int16 *v53; // [rsp+F0h] [rbp+67h] BYREF

  v53 = a4;
  v52 = a3;
  v7 = a3;
  v51 = 0;
  v44 = 0;
  if ( !a2 || !a3 || !a5 )
    return 2147942487LL;
  v8 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework";
  v9 = a7;
  if ( a6 )
    v8 = a6;
  v49 = v8;
  *a7 = 0;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))a2->lpVtbl->get_childNodes)(a2, &v44);
  if ( v10 < 0 )
    goto LABEL_7;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 64LL))(v44, &v51);
  if ( v10 < 0 )
    goto LABEL_7;
  v15 = 0;
  if ( v51 <= 0 )
  {
LABEL_23:
    v10 = *v9 == 0;
    goto LABEL_7;
  }
  while ( !*v9 )
  {
    v48 = 0;
    v41 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 56LL))(v44, v15, &v48);
    if ( v10 >= 0
      && (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v48)(v48, &IID_IXMLDOMElement, &v41) >= 0 )
    {
      v47 = 0;
      bstrString = 0;
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v41->lpVtbl->get_baseName)(v41, &v47);
      if ( v10 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v41->lpVtbl->get_namespaceURI)(v41, &bstrString);
        if ( v10 >= 0 )
        {
          v16 = v47;
          if ( v47 )
          {
            v14 = bstrString;
            if ( bstrString )
            {
              do
              {
                v12 = *(BSTR)((char *)v14
                            + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                            - (char *)bstrString);
                v13 = *v14 - v12;
                if ( v13 )
                  break;
                ++v14;
              }
              while ( v12 );
              if ( !v13 )
              {
                do
                {
                  v17 = *(BSTR)((char *)v16 + (char *)v7 - (char *)v47);
                  v18 = *v16 - v17;
                  if ( v18 )
                    break;
                  ++v16;
                }
                while ( v17 );
                if ( !v18 )
                {
                  v19 = v41;
                  if ( v41 )
                  {
                    lpVtbl = v41->lpVtbl;
                    v46 = 0;
                    v42 = 0;
                    v21 = 0;
                    v22 = 0;
                    v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *, BSTR))lpVtbl->get_attributes)(
                            v41,
                            &v46,
                            v16);
                    if ( v10 < 0 )
                      goto LABEL_38;
                    if ( v46 )
                    {
                      v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v46 + 56LL))(
                              v46,
                              L"name",
                              &v42);
                      if ( v10 < 0 )
                        goto LABEL_38;
                    }
                    if ( !v42 )
                      goto LABEL_51;
                    v45 = 0;
                    Str = 0;
                    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v42)(
                            v42,
                            &IID_IXMLDOMAttribute,
                            &v45);
                    if ( v10 < 0 )
                      goto LABEL_43;
                    v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v45 + 208LL))(v45, &Str);
                    if ( v10 < 0 )
                      goto LABEL_43;
                    if ( Str )
                    {
                      v22 = 0;
                      v27 = -1;
                      LODWORD(v53) = 0;
                      v28 = 0;
                      do
                        ++v27;
                      while ( Str[v27] );
                      if ( (int)v27 > 0 )
                      {
                        while ( Str[v28] != 58 )
                        {
                          v28 = (unsigned int)(v28 + 1);
                          if ( (int)v28 >= (int)v27 )
                            goto LABEL_72;
                        }
                        v29 = SysAllocStringLen(Str, v28);
                        if ( v29 )
                          goto LABEL_86;
LABEL_73:
                        v10 = -2147024882;
                      }
                      else
                      {
LABEL_72:
                        v29 = SysAllocString(&psz);
                        if ( !v29 )
                          goto LABEL_73;
LABEL_86:
                        v32 = 0;
                        v10 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, __int64))(**((_QWORD **)this + 2)
                                                                                                  + 56LL))(
                                *((_QWORD *)this + 2),
                                v19,
                                1);
                        if ( v10 >= 0 )
                        {
                          v32 = 1;
                          v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, const unsigned __int16 **))(**((_QWORD **)this + 2) + 96LL))(
                                  *((_QWORD *)this + 2),
                                  v29,
                                  0,
                                  0,
                                  &v53);
                        }
                        v33 = v10 < 0;
                        if ( v10 )
                        {
LABEL_89:
                          if ( v33 && v22 )
                          {
                            SysFreeString(v22);
                            v22 = 0;
                          }
                        }
                        else
                        {
                          LODWORD(v53) = (_DWORD)v53 + 1;
                          v35 = SysAllocStringLen(0, (UINT)v53);
                          v22 = v35;
                          if ( v35 )
                          {
                            v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, BSTR, const unsigned __int16 **))(**((_QWORD **)this + 2) + 96LL))(
                                    *((_QWORD *)this + 2),
                                    v29,
                                    0,
                                    v35,
                                    &v53);
                            v33 = v10 < 0;
                            goto LABEL_89;
                          }
                          v10 = -2147024882;
                        }
                        if ( v32 )
                        {
                          v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
                          if ( v34 < 0 )
                            v10 = v34;
                        }
                        SysFreeString(v29);
                        v9 = a7;
                      }
                      if ( v10 < 0 )
                        goto LABEL_43;
                      v23 = Str;
                      if ( v22 )
                      {
                        if ( Str )
                        {
                          v30 = wcschr(Str, 0x3Au);
                          if ( v30 )
                            v31 = v30 + 1;
                          else
                            v31 = v23;
                          v21 = SysAllocString(v31);
                          v10 = -2147024882;
                          if ( v21 )
                            v10 = 0;
LABEL_43:
                          v23 = Str;
                        }
                        else
                        {
                          v10 = -2147024809;
                        }
                      }
                      else
                      {
                        v10 = -2147221501;
                      }
                      if ( v23 )
                      {
                        SysFreeString(v23);
                        Str = 0;
                      }
                    }
                    if ( v45 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
                    if ( v10 < 0 )
                    {
LABEL_38:
                      SysFreeString(v22);
                      v22 = 0;
                      SysFreeString(v21);
                      v21 = 0;
                    }
                    if ( v42 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                      v42 = 0;
                    }
LABEL_51:
                    if ( v46 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                    if ( v10 < 0 )
                    {
LABEL_60:
                      if ( v22 )
                        SysFreeString(v22);
                    }
                    else if ( v22 )
                    {
                      if ( v21 )
                      {
                        v24 = v22;
                        do
                        {
                          v25 = *(OLECHAR *)((char *)v24 + (char *)v49 - (char *)v22);
                          v26 = *v24 - v25;
                          if ( v26 )
                            break;
                          ++v24;
                        }
                        while ( v25 );
                        if ( !v26 )
                        {
                          v36 = v21;
                          do
                          {
                            v37 = *(OLECHAR *)((char *)v36 + a5 - (char *)v21);
                            v38 = *v36 - v37;
                            if ( v38 )
                              break;
                            ++v36;
                          }
                          while ( v37 );
                          if ( !v38 )
                          {
                            v39 = v41;
                            *v9 = v41;
                            ((void (__fastcall *)(struct IXMLDOMElement *))v39->lpVtbl->AddRef)(v39);
                          }
                        }
                      }
                      goto LABEL_60;
                    }
                    if ( v21 )
                      SysFreeString(v21);
                    v7 = v52;
                  }
                  else
                  {
                    v10 = -2147024809;
                  }
                }
              }
            }
          }
        }
      }
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v47 )
        SysFreeString(v47);
    }
    if ( v41 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v41->lpVtbl->Release)(v41);
      v41 = 0;
    }
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    if ( (int)++v15 >= v51 )
      break;
  }
  if ( v10 >= 0 )
    goto LABEL_23;
LABEL_7:
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800019f0  mov     rax, rsp
0x1800019f3  mov     [rax+20h], r9
0x1800019f7  mov     [rax+18h], r8
0x1800019fb  mov     [rax+8], rcx
0x1800019ff  push    rbp
0x180001a00  push    rbx
0x180001a01  push    rsi
0x180001a02  lea     rbp, [rax-47h]
0x180001a06  sub     rsp, 0B0h
0x180001a0d  xor     esi, esi
0x180001a0f  mov     rbx, r8
0x180001a12  mov     [rbp+3Fh+arg_8], esi
0x180001a15  mov     r9, rdx
0x180001a18  mov     [rbp+3Fh+var_70], rsi
0x180001a1c  test    rdx, rdx
0x180001a1f  jz      loc_180002071
0x180001a25  test    rbx, rbx
0x180001a28  jz      loc_180002071
0x180001a2e  cmp     [rbp+3Fh+arg_20], rsi
0x180001a32  jz      loc_180002071
0x180001a38  mov     [rax-28h], r12
0x180001a3c  lea     rcx, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180001a43  mov     [rax-40h], r15
0x180001a47  mov     rax, [rbp+3Fh+arg_28]
0x180001a4b  mov     r15, [rbp+3Fh+arg_30]
0x180001a4f  test    rax, rax
0x180001a52  cmovnz  rcx, rax
0x180001a56  mov     [rbp+3Fh+var_48], rcx
0x180001a5a  mov     rcx, r9
0x180001a5d  mov     [r15], rsi
0x180001a60  mov     rax, [rdx]
0x180001a63  lea     rdx, [rbp+3Fh+var_70]
0x180001a67  mov     rax, [rax+60h]
0x180001a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a70  mov     r12d, eax
0x180001a73  test    eax, eax
0x180001a75  jns     loc_18000200A
0x180001a7b  mov     rcx, [rbp+3Fh+var_70]
0x180001a7f  mov     r15, [rsp+0C0h+var_38]
0x180001a87  test    rcx, rcx
0x180001a8a  jz      short loc_180001A98
0x180001a8c  mov     rax, [rcx]
0x180001a8f  mov     rax, [rax+10h]
0x180001a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a98  mov     eax, r12d
0x180001a9b  mov     r12, [rsp+0C0h+var_20]
0x180001aa3  add     rsp, 0B0h
0x180001aaa  pop     rsi
0x180001aab  pop     rbx
0x180001aac  pop     rbp
0x180001aad  retn
0x180001aae  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180001ab5  sub     r9, rcx
0x180001ab8  nop     dword ptr [rax+rax+00000000h]
0x180001ac0  movzx   edx, word ptr [rcx]
0x180001ac3  movzx   eax, word ptr [rcx+r9]
0x180001ac8  sub     edx, eax
0x180001aca  jnz     short loc_180001AD4
0x180001acc  add     rcx, 2
0x180001ad0  test    eax, eax
0x180001ad2  jnz     short loc_180001AC0
0x180001ad4  test    edx, edx
0x180001ad6  jz      loc_180001C35
0x180001adc  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180001ae0  test    rcx, rcx
0x180001ae3  jz      short loc_180001AEF
0x180001ae5  call    cs:__imp_SysFreeString
0x180001aeb  mov     [rbp+3Fh+bstrString], rsi
0x180001aef  mov     r8, [rbp+3Fh+var_58]
0x180001af3  test    r8, r8
0x180001af6  jz      short loc_180001B01
0x180001af8  mov     rcx, r8; bstrString
0x180001afb  call    cs:__imp_SysFreeString
0x180001b01  mov     r14, [rbp+3Fh+var_88]
0x180001b05  test    r14, r14
0x180001b08  jz      short loc_180001B1D
0x180001b0a  mov     rax, [r14]
0x180001b0d  mov     rcx, r14
0x180001b10  mov     rax, [rax+10h]
0x180001b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b19  mov     [rbp+3Fh+var_88], rsi
0x180001b1d  mov     rcx, [rbp+3Fh+var_50]
0x180001b21  test    rcx, rcx
0x180001b24  jz      short loc_180001B32
0x180001b26  mov     rax, [rcx]
0x180001b29  mov     rax, [rax+10h]
0x180001b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b32  inc     r13d
0x180001b35  cmp     r13d, [rbp+3Fh+arg_8]
0x180001b39  jl      short loc_180001B78
0x180001b3b  mov     r14, [rsp+0C0h+var_30]
0x180001b43  mov     rdi, [rsp+0C0h+var_18]
0x180001b4b  test    r12d, r12d
0x180001b4e  js      short loc_180001B5B
0x180001b50  cmp     qword ptr [r15], 0
0x180001b54  mov     r12d, esi
0x180001b57  setz    r12b
0x180001b5b  mov     r13, [rsp+0C0h+var_28]
0x180001b63  jmp     loc_180001A7B
0x180001b68  mov     [rsp+0C0h+var_18], rdi
0x180001b70  mov     [rsp+0C0h+var_30], r14
0x180001b78  cmp     qword ptr [r15], 0
0x180001b7c  jnz     short loc_180001B3B
0x180001b7e  mov     rcx, [rbp+3Fh+var_70]
0x180001b82  lea     r8, [rbp+3Fh+var_50]
0x180001b86  mov     [rbp+3Fh+var_50], rsi
0x180001b8a  mov     edx, r13d
0x180001b8d  mov     [rbp+3Fh+var_88], rsi
0x180001b91  mov     rax, [rcx]
0x180001b94  mov     rax, [rax+38h]
0x180001b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b9d  mov     r12d, eax
0x180001ba0  test    eax, eax
0x180001ba2  js      loc_180001B01
0x180001ba8  mov     rcx, [rbp+3Fh+var_50]
0x180001bac  lea     r8, [rbp+3Fh+var_88]
0x180001bb0  lea     rdx, IID_IXMLDOMElement
0x180001bb7  mov     rax, [rcx]
0x180001bba  mov     rax, [rax]
0x180001bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bc2  test    eax, eax
0x180001bc4  js      loc_180001B01
0x180001bca  mov     rcx, [rbp+3Fh+var_88]
0x180001bce  lea     rdx, [rbp+3Fh+var_58]
0x180001bd2  mov     [rbp+3Fh+var_58], rsi
0x180001bd6  mov     [rbp+3Fh+bstrString], rsi
0x180001bda  mov     rax, [rcx]
0x180001bdd  mov     rax, [rax+148h]
0x180001be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001be9  mov     r12d, eax
0x180001bec  test    eax, eax
0x180001bee  js      loc_180001ADC
0x180001bf4  mov     rcx, [rbp+3Fh+var_88]
0x180001bf8  lea     rdx, [rbp+3Fh+bstrString]
0x180001bfc  mov     rax, [rcx]
0x180001bff  mov     rax, [rax+138h]
0x180001c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c0b  mov     r12d, eax
0x180001c0e  test    eax, eax
0x180001c10  js      loc_180001ADC
0x180001c16  mov     r8, [rbp+3Fh+var_58]
0x180001c1a  test    r8, r8
0x180001c1d  jz      loc_180001ADC
0x180001c23  mov     rcx, [rbp+3Fh+bstrString]
0x180001c27  test    rcx, rcx
0x180001c2a  jz      loc_180001ADC
0x180001c30  jmp     loc_180001AAE
0x180001c35  mov     rdx, rbx
0x180001c38  sub     rdx, r8
0x180001c3b  nop     dword ptr [rax+rax+00h]
0x180001c40  movzx   ecx, word ptr [r8]
0x180001c44  movzx   eax, word ptr [r8+rdx]
0x180001c49  sub     ecx, eax
0x180001c4b  jnz     short loc_180001C55
0x180001c4d  add     r8, 2
0x180001c51  test    eax, eax
0x180001c53  jnz     short loc_180001C40
0x180001c55  test    ecx, ecx
0x180001c57  jnz     loc_180001ADC
0x180001c5d  mov     r14, [rbp+3Fh+var_88]
0x180001c61  test    r14, r14
0x180001c64  jz      loc_180001DF1
0x180001c6a  mov     rax, [r14]
0x180001c6d  lea     rdx, [rbp+3Fh+var_60]
0x180001c71  mov     rcx, r14
0x180001c74  mov     [rbp+3Fh+var_60], rsi
0x180001c78  mov     [rbp+3Fh+var_80], rsi
0x180001c7c  mov     rdi, rsi
0x180001c7f  mov     rbx, rsi
0x180001c82  mov     rax, [rax+88h]
0x180001c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c8e  mov     r12d, eax
0x180001c91  test    eax, eax
0x180001c93  jns     loc_180001DFC
0x180001c99  mov     rcx, rbx; bstrString
0x180001c9c  call    cs:__imp_SysFreeString
0x180001ca2  mov     rcx, rdi; bstrString
0x180001ca5  mov     rbx, rsi
0x180001ca8  call    cs:__imp_SysFreeString
0x180001cae  mov     rdi, rsi
0x180001cb1  jmp     loc_180001D62
0x180001cb6  mov     rax, [rcx]
0x180001cb9  lea     r8, [rbp+3Fh+var_80]
0x180001cbd  lea     rdx, aName; "name"
0x180001cc4  mov     rax, [rax+38h]
0x180001cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ccd  mov     r12d, eax
0x180001cd0  test    eax, eax
0x180001cd2  js      short loc_180001C99
0x180001cd4  mov     rcx, [rbp+3Fh+var_80]
0x180001cd8  test    rcx, rcx
0x180001cdb  jz      loc_180001D7B
0x180001ce1  mov     [rbp+3Fh+var_68], rsi
0x180001ce5  lea     r8, [rbp+3Fh+var_68]
0x180001ce9  mov     [rbp+3Fh+Str], rsi
0x180001ced  lea     rdx, IID_IXMLDOMAttribute
0x180001cf4  mov     rax, [rcx]
0x180001cf7  mov     rax, [rax]
0x180001cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cff  mov     r12d, eax
0x180001d02  test    eax, eax
0x180001d04  js      short loc_180001D28
0x180001d06  mov     rcx, [rbp+3Fh+var_68]
0x180001d0a  lea     rdx, [rbp+3Fh+Str]
0x180001d0e  mov     rax, [rcx]
0x180001d11  mov     rax, [rax+0D0h]
0x180001d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d1d  mov     r12d, eax
0x180001d20  test    eax, eax
0x180001d22  jns     loc_180001E0E
0x180001d28  mov     rsi, [rbp+3Fh+Str]
0x180001d2c  test    rsi, rsi
0x180001d2f  jz      loc_180001FB2
0x180001d35  mov     rcx, rsi; bstrString
0x180001d38  call    cs:__imp_SysFreeString
0x180001d3e  xor     esi, esi
0x180001d40  mov     [rbp+3Fh+Str], rsi
0x180001d44  mov     rcx, [rbp+3Fh+var_68]
0x180001d48  test    rcx, rcx
0x180001d4b  jz      short loc_180001D59
0x180001d4d  mov     rax, [rcx]
0x180001d50  mov     rax, [rax+10h]
0x180001d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d59  test    r12d, r12d
0x180001d5c  js      loc_180001C99
0x180001d62  mov     rcx, [rbp+3Fh+var_80]
0x180001d66  test    rcx, rcx
0x180001d69  jz      short loc_180001D7B
0x180001d6b  mov     rax, [rcx]
0x180001d6e  mov     rax, [rax+10h]
0x180001d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d77  mov     [rbp+3Fh+var_80], rsi
0x180001d7b  mov     rcx, [rbp+3Fh+var_60]
0x180001d7f  test    rcx, rcx
0x180001d82  jz      short loc_180001D90
0x180001d84  mov     rax, [rcx]
0x180001d87  mov     rax, [rax+10h]
0x180001d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d90  test    r12d, r12d
0x180001d93  js      short loc_180001DCC
0x180001d95  test    rbx, rbx
0x180001d98  jz      short loc_180001DDA
0x180001d9a  test    rdi, rdi
0x180001d9d  jz      short loc_180001DCC
0x180001d9f  mov     r8, [rbp+3Fh+var_48]
0x180001da3  mov     rax, rbx
0x180001da6  sub     r8, rbx
0x180001da9  nop     dword ptr [rax+00000000h]
0x180001db0  movzx   edx, word ptr [rax]
0x180001db3  movzx   ecx, word ptr [rax+r8]
0x180001db8  sub     edx, ecx
0x180001dba  jnz     short loc_180001DC4
0x180001dbc  add     rax, 2
0x180001dc0  test    ecx, ecx
0x180001dc2  jnz     short loc_180001DB0
0x180001dc4  test    edx, edx
0x180001dc6  jz      loc_180001FB9
0x180001dcc  test    rbx, rbx
0x180001dcf  jz      short loc_180001DDA
0x180001dd1  mov     rcx, rbx; bstrString
0x180001dd4  call    cs:__imp_SysFreeString
0x180001dda  test    rdi, rdi
0x180001ddd  jz      short loc_180001DE8
0x180001ddf  mov     rcx, rdi; bstrString
0x180001de2  call    cs:__imp_SysFreeString
0x180001de8  mov     rbx, [rbp+3Fh+arg_10]
0x180001dec  jmp     loc_180001ADC
0x180001df1  mov     r12d, 80070057h
0x180001df7  jmp     loc_180001ADC
0x180001dfc  mov     rcx, [rbp+3Fh+var_60]
0x180001e00  test    rcx, rcx
0x180001e03  jnz     loc_180001CB6
0x180001e09  jmp     loc_180001CD4
0x180001e0e  mov     rsi, [rbp+3Fh+Str]
0x180001e12  test    rsi, rsi
0x180001e15  jz      loc_180001FB2
0x180001e1b  xor     ebx, ebx
0x180001e1d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001e24  mov     dword ptr [rbp+3Fh+arg_18], ebx
0x180001e27  xor     edx, edx; ui
0x180001e29  nop     dword ptr [rax+00000000h]
0x180001e30  inc     rcx
0x180001e33  cmp     [rsi+rcx*2], dx
0x180001e37  jnz     short loc_180001E30
0x180001e39  test    ecx, ecx
0x180001e3b  jg      short loc_180001EB6
0x180001e3d  lea     rcx, psz; psz
0x180001e44  call    cs:__imp_SysAllocString
0x180001e4a  mov     rsi, rax
0x180001e4d  test    rax, rax
0x180001e50  jnz     loc_180001EDD
0x180001e56  mov     r12d, 8007000Eh
0x180001e5c  test    r12d, r12d
0x180001e5f  js      loc_180001D28
0x180001e65  mov     rsi, [rbp+3Fh+Str]
0x180001e69  test    rbx, rbx
0x180001e6c  jz      loc_180002066
0x180001e72  test    rsi, rsi
0x180001e75  jz      loc_180001FF7
0x180001e7b  mov     edx, 3Ah ; ':'; Ch
  ... truncated ...
```
