# NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x180002084`
- end: `0x1800022c7`
- name: `?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z`
- size: `579`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001310`
- `0x180001668`
- `0x180001810`
- `0x18001b7b0`
- `0x18001ced0`
- `0x18001d878`
- `0x18001ddc4`
- `0x18001ee20`
- `0x18001f120`
- `0x18001f850`
- `0x1800200fc`
- `0x180020910`
- `0x180021070`
- `0x180021a90`

## callees

- `0x180002084`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002233`
- `OLEAUT32!__imp_SysFreeString` at `0x180002249`
- `OLEAUT32!__imp_SysFreeString` at `0x180002233`
- `OLEAUT32!__imp_SysFreeString` at `0x180002249`

## string_xrefs

- `0x1800021c7`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        char *a3,
        const unsigned __int16 *a4,
        struct IXMLDOMElement **a5)
{
  struct IXMLDOMElement **v6; // rdi
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v8; // ebx
  int v9; // esi
  OLECHAR *v10; // rax
  BSTR v11; // rcx
  int v12; // r8d
  int v13; // edx
  BSTR v14; // rcx
  int v15; // r8d
  int v16; // edx
  NPrintTicketUtil::CPrintTicketWrapper *v17; // rdx
  BSTR bstrString; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  __int64 v21; // [rsp+30h] [rbp-10h] BYREF
  NPrintTicketUtil::CPrintTicketWrapper *v22; // [rsp+70h] [rbp+30h] BYREF
  BSTR v23; // [rsp+78h] [rbp+38h] BYREF
  const unsigned __int16 *v24; // [rsp+88h] [rbp+48h] BYREF

  v24 = a4;
  v22 = this;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v6 = a5;
  if ( !a5 )
    return 2147942487LL;
  *a5 = 0;
  lpVtbl = a2->lpVtbl;
  LODWORD(v24) = 0;
  v20 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))lpVtbl->get_childNodes)(a2, &v20);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v20 + 64LL))(v20, &v24);
    if ( v8 >= 0 )
    {
      v9 = 0;
      if ( (int)v24 <= 0 )
        goto LABEL_35;
      do
      {
        if ( *v6 )
          break;
        v21 = 0;
        v22 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 56LL))(
               v20,
               (unsigned int)v9,
               &v21);
        if ( v8 >= 0
          && (**(int (__fastcall ***)(__int64, GUID *, NPrintTicketUtil::CPrintTicketWrapper **))v21)(
               v21,
               &IID_IXMLDOMElement,
               &v22) >= 0 )
        {
          v23 = 0;
          bstrString = 0;
          v8 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, BSTR *))(*(_QWORD *)v22 + 328LL))(
                 v22,
                 &v23);
          if ( v8 < 0 )
          {
            v10 = v23;
          }
          else
          {
            v8 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, BSTR *))(*(_QWORD *)v22 + 312LL))(
                   v22,
                   &bstrString);
            v10 = v23;
            if ( v8 >= 0 )
            {
              if ( v23 )
              {
                v11 = bstrString;
                if ( bstrString )
                {
                  do
                  {
                    v12 = *(BSTR)((char *)v11
                                + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                                - (char *)bstrString);
                    v13 = *v11 - v12;
                    if ( v13 )
                      break;
                    ++v11;
                  }
                  while ( v12 );
                  if ( !v13 )
                  {
                    v14 = v23;
                    do
                    {
                      v15 = *(BSTR)((char *)v14 + a3 - (char *)v23);
                      v16 = *v14 - v15;
                      if ( v16 )
                        break;
                      ++v14;
                    }
                    while ( v15 );
                    if ( !v16 )
                    {
                      v17 = 0;
                      if ( v22 )
                      {
                        v17 = v22;
                        v22 = 0;
                      }
                      *v6 = (struct IXMLDOMElement *)v17;
                    }
                  }
                }
              }
            }
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            v10 = v23;
            bstrString = 0;
          }
          if ( v10 )
            SysFreeString(v10);
        }
        if ( v22 )
        {
          (*(void (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *))(*(_QWORD *)v22 + 16LL))(v22);
          v22 = 0;
        }
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        ++v9;
      }
      while ( v9 < (int)v24 );
      if ( v8 >= 0 )
LABEL_35:
        v8 = *v6 == 0;
    }
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002084  mov     [rsp-28h+arg_10], rbx
0x180002089  mov     [rsp-28h+arg_18], r9
0x18000208e  mov     [rsp-28h+arg_0], rcx
0x180002093  push    rbp
0x180002094  push    rsi
0x180002095  push    rdi
0x180002096  push    r14
0x180002098  push    r15
0x18000209a  mov     rbp, rsp
0x18000209d  sub     rsp, 40h
0x1800020a1  xor     r15d, r15d
0x1800020a4  mov     r14, r8
0x1800020a7  mov     r9, rdx
0x1800020aa  test    rdx, rdx
0x1800020ad  jz      loc_1800022AE
0x1800020b3  test    r8, r8
0x1800020b6  jz      loc_1800022AE
0x1800020bc  mov     rdi, [rbp+arg_20]
0x1800020c0  test    rdi, rdi
0x1800020c3  jz      loc_1800022AE
0x1800020c9  mov     [rdi], r15
0x1800020cc  mov     rcx, r9
0x1800020cf  mov     rax, [rdx]
0x1800020d2  lea     rdx, [rbp+var_18]
0x1800020d6  mov     dword ptr [rbp+arg_18], r15d
0x1800020da  mov     [rbp+var_18], r15
0x1800020de  mov     rax, [rax+60h]
0x1800020e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e7  mov     ebx, eax
0x1800020e9  test    eax, eax
0x1800020eb  js      loc_180002295
0x1800020f1  mov     rcx, [rbp+var_18]
0x1800020f5  lea     rdx, [rbp+arg_18]
0x1800020f9  mov     rax, [rcx]
0x1800020fc  mov     rax, [rax+40h]
0x180002100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002105  mov     ebx, eax
0x180002107  test    eax, eax
0x180002109  js      loc_180002295
0x18000210f  mov     esi, r15d
0x180002112  cmp     dword ptr [rbp+arg_18], r15d
0x180002116  jle     loc_18000228C
0x18000211c  cmp     [rdi], r15
0x18000211f  jnz     loc_180002288
0x180002125  mov     rcx, [rbp+var_18]
0x180002129  lea     r8, [rbp+var_10]
0x18000212d  mov     [rbp+var_10], r15
0x180002131  mov     edx, esi
0x180002133  mov     [rbp+arg_0], r15
0x180002137  mov     rax, [rcx]
0x18000213a  mov     rax, [rax+38h]
0x18000213e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002143  mov     ebx, eax
0x180002145  test    eax, eax
0x180002147  js      loc_18000224F
0x18000214d  mov     rcx, [rbp+var_10]
0x180002151  lea     r8, [rbp+arg_0]
0x180002155  lea     rdx, IID_IXMLDOMElement
0x18000215c  mov     rax, [rcx]
0x18000215f  mov     rax, [rax]
0x180002162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002167  test    eax, eax
0x180002169  js      loc_18000224F
0x18000216f  mov     rcx, [rbp+arg_0]
0x180002173  lea     rdx, [rbp+arg_8]
0x180002177  mov     [rbp+arg_8], r15
0x18000217b  mov     [rbp+bstrString], r15
0x18000217f  mov     rax, [rcx]
0x180002182  mov     rax, [rax+148h]
0x180002189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000218e  mov     ebx, eax
0x180002190  test    eax, eax
0x180002192  js      loc_180002226
0x180002198  mov     rcx, [rbp+arg_0]
0x18000219c  lea     rdx, [rbp+bstrString]
0x1800021a0  mov     rax, [rcx]
0x1800021a3  mov     rax, [rax+138h]
0x1800021aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021af  mov     ebx, eax
0x1800021b1  test    eax, eax
0x1800021b3  mov     rax, [rbp+arg_8]
0x1800021b7  js      short loc_18000222A
0x1800021b9  test    rax, rax
0x1800021bc  jz      short loc_18000222A
0x1800021be  mov     rcx, [rbp+bstrString]
0x1800021c2  test    rcx, rcx
0x1800021c5  jz      short loc_18000222A
0x1800021c7  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x1800021ce  sub     r9, rcx
0x1800021d1  movzx   edx, word ptr [rcx]
0x1800021d4  movzx   r8d, word ptr [rcx+r9]
0x1800021d9  sub     edx, r8d
0x1800021dc  jnz     short loc_1800021E7
0x1800021de  add     rcx, 2
0x1800021e2  test    r8d, r8d
0x1800021e5  jnz     short loc_1800021D1
0x1800021e7  test    edx, edx
0x1800021e9  jnz     short loc_18000222A
0x1800021eb  mov     r9, r14
0x1800021ee  mov     rcx, rax
0x1800021f1  sub     r9, rax
0x1800021f4  movzx   edx, word ptr [rcx]
0x1800021f7  movzx   r8d, word ptr [rcx+r9]
0x1800021fc  sub     edx, r8d
0x1800021ff  jnz     short loc_18000220A
0x180002201  add     rcx, 2
0x180002205  test    r8d, r8d
0x180002208  jnz     short loc_1800021F4
0x18000220a  test    edx, edx
0x18000220c  jnz     short loc_18000222A
0x18000220e  mov     rcx, [rbp+arg_0]
0x180002212  mov     rdx, r15
0x180002215  test    rcx, rcx
0x180002218  jz      short loc_180002221
0x18000221a  mov     rdx, rcx
0x18000221d  mov     [rbp+arg_0], r15
0x180002221  mov     [rdi], rdx
0x180002224  jmp     short loc_18000222A
0x180002226  mov     rax, [rbp+arg_8]
0x18000222a  mov     rcx, [rbp+bstrString]; bstrString
0x18000222e  test    rcx, rcx
0x180002231  jz      short loc_180002241
0x180002233  call    cs:__imp_SysFreeString
0x180002239  mov     rax, [rbp+arg_8]
0x18000223d  mov     [rbp+bstrString], r15
0x180002241  test    rax, rax
0x180002244  jz      short loc_18000224F
0x180002246  mov     rcx, rax; bstrString
0x180002249  call    cs:__imp_SysFreeString
0x18000224f  mov     rcx, [rbp+arg_0]
0x180002253  test    rcx, rcx
0x180002256  jz      short loc_180002268
0x180002258  mov     rax, [rcx]
0x18000225b  mov     rax, [rax+10h]
0x18000225f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002264  mov     [rbp+arg_0], r15
0x180002268  mov     rcx, [rbp+var_10]
0x18000226c  test    rcx, rcx
0x18000226f  jz      short loc_18000227D
0x180002271  mov     rax, [rcx]
0x180002274  mov     rax, [rax+10h]
0x180002278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000227d  inc     esi
0x18000227f  cmp     esi, dword ptr [rbp+arg_18]
0x180002282  jl      loc_18000211C
0x180002288  test    ebx, ebx
0x18000228a  js      short loc_180002295
0x18000228c  cmp     [rdi], r15
0x18000228f  mov     ebx, r15d
0x180002292  setz    bl
0x180002295  mov     rcx, [rbp+var_18]
0x180002299  test    rcx, rcx
0x18000229c  jz      short loc_1800022AA
0x18000229e  mov     rax, [rcx]
0x1800022a1  mov     rax, [rax+10h]
0x1800022a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022aa  mov     eax, ebx
0x1800022ac  jmp     short loc_1800022B3
0x1800022ae  mov     eax, 80070057h
0x1800022b3  mov     rbx, [rsp+40h+arg_10]
0x1800022bb  add     rsp, 40h
0x1800022bf  pop     r15
0x1800022c1  pop     r14
0x1800022c3  pop     rdi
0x1800022c4  pop     rsi
0x1800022c5  pop     rbp
0x1800022c6  retn
```
