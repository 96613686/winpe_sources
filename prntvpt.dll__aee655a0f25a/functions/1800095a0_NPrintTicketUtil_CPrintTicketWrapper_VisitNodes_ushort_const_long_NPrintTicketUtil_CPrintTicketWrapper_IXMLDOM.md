# NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(ushort const *,long (*)(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,void *),void *,IXMLDOMElement *)

- ea: `0x1800095a0`
- end: `0x18000985a`
- name: `?VisitNodes@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGP6AJPEAV12@PEAUIXMLDOMElement@@PEAX@Z32@Z`
- size: `698`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, const unsigned __int16 *, int (*)(struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, void *), void *, struct IXMLDOMElement *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800014e0`
- `0x180003380`
- `0x180009410`
- `0x180009514`

## callees

- `0x1800095a0`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009710`
- `OLEAUT32!__imp_SysFreeString` at `0x180009726`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180009710`
- `OLEAUT32!__imp_SysFreeString` at `0x180009726`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800097d3`

## string_xrefs

- `0x1800096d8`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        char *a2,
        __int64 (__fastcall *a3)(NPrintTicketUtil::CPrintTicketWrapper *, __int64, void *),
        void *a4,
        struct IXMLDOMElement *a5)
{
  struct IXMLDOMElement *v9; // rcx
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // esi
  OLECHAR *v13; // r9
  OLECHAR *v14; // r10
  BSTR v15; // rax
  int v16; // ecx
  int v17; // edx
  BSTR v18; // rax
  int v19; // ecx
  int v20; // edx
  __int64 v22; // [rsp+20h] [rbp-20h] BYREF
  BSTR v23; // [rsp+28h] [rbp-18h] BYREF
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+38h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+40h] BYREF

  v25 = 0;
  if ( !a3 || !a2 )
    return 2147942487LL;
  v9 = a5;
  if ( !a5 )
    v9 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))v9->lpVtbl->get_childNodes)(v9, &v25);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
    if ( v10 >= 0 )
    {
      v11 = 0;
      v22 = 0;
      v12 = 0;
      while ( 1 )
      {
        if ( v10 < 0 )
        {
LABEL_40:
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          if ( v10 >= 0 )
            v10 = v12 != 0;
          goto LABEL_44;
        }
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 72LL))(v25, &v22);
        if ( v10 )
          goto LABEL_39;
        v24 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(v22, &IID_IXMLDOMElement, &v24) >= 0 )
          break;
LABEL_23:
        v11 = v22;
        if ( v22 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          v11 = 0;
          v22 = 0;
        }
        if ( v24 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          v11 = v22;
        }
      }
      v23 = 0;
      bstrString = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v24 + 312LL))(v24, &v23);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v24 + 328LL))(v24, &bstrString);
        if ( v10 >= 0 )
        {
          v13 = v23;
          v14 = bstrString;
          if ( !v23 )
            goto LABEL_19;
          if ( !bstrString )
          {
LABEL_21:
            if ( v13 )
              SysFreeString(v13);
            goto LABEL_23;
          }
          v15 = v23;
          do
          {
            v16 = *(BSTR)((char *)v15
                        + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                        - (char *)v23);
            v17 = *v15 - v16;
            if ( v17 )
              break;
            ++v15;
          }
          while ( v16 );
          if ( v17 )
            goto LABEL_19;
          v18 = bstrString;
          do
          {
            v19 = *(BSTR)((char *)v18 + a2 - (char *)bstrString);
            v20 = *v18 - v19;
            if ( v20 )
              break;
            ++v18;
          }
          while ( v19 );
          if ( v20 )
          {
LABEL_19:
            if ( v14 )
            {
              SysFreeString(v14);
              v13 = v23;
              bstrString = 0;
            }
            goto LABEL_21;
          }
          v10 = a3(this, v24, a4);
          if ( v10 == 1 )
          {
            v12 = 1;
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v23 )
            {
              SysFreeString(v23);
              v23 = 0;
            }
            if ( v24 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
LABEL_39:
            v11 = v22;
            goto LABEL_40;
          }
        }
      }
      v13 = v23;
      v14 = bstrString;
      goto LABEL_19;
    }
  }
LABEL_44:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800095a0  mov     [rsp-28h+arg_18], rdi
0x1800095a5  push    rbp
0x1800095a6  push    r12
0x1800095a8  push    r13
0x1800095aa  push    r14
0x1800095ac  push    r15
0x1800095ae  mov     rbp, rsp
0x1800095b1  sub     rsp, 40h
0x1800095b5  xor     r13d, r13d
0x1800095b8  mov     r12, r9
0x1800095bb  mov     [rbp+var_8], r13
0x1800095bf  mov     r14, r8
0x1800095c2  mov     rdi, rdx
0x1800095c5  mov     r15, rcx
0x1800095c8  test    r8, r8
0x1800095cb  jz      loc_180009853
0x1800095d1  test    rdx, rdx
0x1800095d4  jz      loc_180009853
0x1800095da  mov     rcx, [rbp+arg_20]
0x1800095de  mov     [rsp+40h+arg_0], rbx
0x1800095e3  test    rcx, rcx
0x1800095e6  jz      loc_18000984A
0x1800095ec  mov     rax, [rcx]
0x1800095ef  lea     rdx, [rbp+var_8]
0x1800095f3  mov     rax, [rax+60h]
0x1800095f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095fc  mov     ebx, eax
0x1800095fe  test    eax, eax
0x180009600  js      loc_180009818
0x180009606  mov     rcx, [rbp+var_8]
0x18000960a  mov     rax, [rcx]
0x18000960d  mov     rax, [rax+50h]
0x180009611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009616  mov     ebx, eax
0x180009618  test    eax, eax
0x18000961a  js      loc_180009818
0x180009620  mov     rcx, r13
0x180009623  mov     [rsp+40h+arg_8], rsi
0x180009628  mov     [rbp+var_20], rcx
0x18000962c  mov     esi, r13d
0x18000962f  nop
0x180009630  test    ebx, ebx
0x180009632  js      loc_1800097F6
0x180009638  mov     rcx, [rbp+var_8]
0x18000963c  lea     rdx, [rbp+var_20]
0x180009640  mov     rax, [rcx]
0x180009643  mov     rax, [rax+48h]
0x180009647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964c  mov     ebx, eax
0x18000964e  test    eax, eax
0x180009650  jnz     loc_1800097F2
0x180009656  mov     rcx, [rbp+var_20]
0x18000965a  lea     r8, [rbp+var_10]
0x18000965e  mov     [rbp+var_10], r13
0x180009662  lea     rdx, IID_IXMLDOMElement
0x180009669  mov     rax, [rcx]
0x18000966c  mov     rax, [rax]
0x18000966f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009674  test    eax, eax
0x180009676  js      loc_18000972C
0x18000967c  mov     rcx, [rbp+var_10]
0x180009680  lea     rdx, [rbp+var_18]
0x180009684  mov     [rbp+var_18], r13
0x180009688  mov     [rbp+bstrString], r13
0x18000968c  mov     rax, [rcx]
0x18000968f  mov     rax, [rax+138h]
0x180009696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969b  mov     ebx, eax
0x18000969d  test    eax, eax
0x18000969f  js      loc_18000976D
0x1800096a5  mov     rcx, [rbp+var_10]
0x1800096a9  lea     rdx, [rbp+bstrString]
0x1800096ad  mov     rax, [rcx]
0x1800096b0  mov     rax, [rax+148h]
0x1800096b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096bc  mov     ebx, eax
0x1800096be  test    eax, eax
0x1800096c0  js      loc_18000976D
0x1800096c6  mov     r9, [rbp+var_18]
0x1800096ca  mov     r10, [rbp+bstrString]
0x1800096ce  test    r9, r9
0x1800096d1  jz      short loc_180009708
0x1800096d3  test    r10, r10
0x1800096d6  jz      short loc_18000971E
0x1800096d8  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x1800096df  mov     rax, r9
0x1800096e2  sub     r8, r9
0x1800096e5  nop     word ptr [rax+rax+00000000h]
0x1800096f0  movzx   edx, word ptr [rax]
0x1800096f3  movzx   ecx, word ptr [rax+r8]
0x1800096f8  sub     edx, ecx
0x1800096fa  jnz     short loc_180009704
0x1800096fc  add     rax, 2
0x180009700  test    ecx, ecx
0x180009702  jnz     short loc_1800096F0
0x180009704  test    edx, edx
0x180009706  jz      short loc_180009777
0x180009708  test    r10, r10
0x18000970b  jz      short loc_18000971E
0x18000970d  mov     rcx, r10; bstrString
0x180009710  call    cs:__imp_SysFreeString
0x180009716  mov     r9, [rbp+var_18]
0x18000971a  mov     [rbp+bstrString], r13
0x18000971e  test    r9, r9
0x180009721  jz      short loc_18000972C
0x180009723  mov     rcx, r9; bstrString
0x180009726  call    cs:__imp_SysFreeString
0x18000972c  mov     rcx, [rbp+var_20]
0x180009730  test    rcx, rcx
0x180009733  jz      short loc_180009748
0x180009735  mov     rax, [rcx]
0x180009738  mov     rax, [rax+10h]
0x18000973c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009741  mov     rcx, r13
0x180009744  mov     [rbp+var_20], rcx
0x180009748  mov     rdx, [rbp+var_10]
0x18000974c  test    rdx, rdx
0x18000974f  jz      loc_180009630
0x180009755  mov     rax, [rdx]
0x180009758  mov     rcx, rdx
0x18000975b  mov     rax, [rax+10h]
0x18000975f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009764  mov     rcx, [rbp+var_20]
0x180009768  jmp     loc_180009630
0x18000976d  mov     r9, [rbp+var_18]
0x180009771  mov     r10, [rbp+bstrString]
0x180009775  jmp     short loc_180009708
0x180009777  mov     r8, rdi
0x18000977a  mov     rax, r10
0x18000977d  sub     r8, r10
0x180009780  movzx   edx, word ptr [rax]
0x180009783  movzx   ecx, word ptr [rax+r8]
0x180009788  sub     edx, ecx
0x18000978a  jnz     short loc_180009794
0x18000978c  add     rax, 2
0x180009790  test    ecx, ecx
0x180009792  jnz     short loc_180009780
0x180009794  test    edx, edx
0x180009796  jnz     loc_180009708
0x18000979c  mov     rdx, [rbp+var_10]
0x1800097a0  mov     r8, r12
0x1800097a3  mov     rcx, r15
0x1800097a6  mov     rax, r14
0x1800097a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ae  mov     ebx, eax
0x1800097b0  cmp     eax, 1
0x1800097b3  jnz     short loc_18000976D
0x1800097b5  mov     rcx, [rbp+bstrString]; bstrString
0x1800097b9  mov     esi, eax
0x1800097bb  test    rcx, rcx
0x1800097be  jz      short loc_1800097CA
0x1800097c0  call    cs:__imp_SysFreeString
0x1800097c6  mov     [rbp+bstrString], r13
0x1800097ca  mov     rcx, [rbp+var_18]; bstrString
0x1800097ce  test    rcx, rcx
0x1800097d1  jz      short loc_1800097DD
0x1800097d3  call    cs:__imp_SysFreeString
0x1800097d9  mov     [rbp+var_18], r13
0x1800097dd  mov     rcx, [rbp+var_10]
0x1800097e1  test    rcx, rcx
0x1800097e4  jz      short loc_1800097F2
0x1800097e6  mov     rax, [rcx]
0x1800097e9  mov     rax, [rax+10h]
0x1800097ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f2  mov     rcx, [rbp+var_20]
0x1800097f6  test    rcx, rcx
0x1800097f9  jz      short loc_180009807
0x1800097fb  mov     rax, [rcx]
0x1800097fe  mov     rax, [rax+10h]
0x180009802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009807  test    ebx, ebx
0x180009809  js      short loc_180009813
0x18000980b  test    esi, esi
0x18000980d  mov     ebx, r13d
0x180009810  setnz   bl
0x180009813  mov     rsi, [rsp+40h+arg_8]
0x180009818  mov     rcx, [rbp+var_8]
0x18000981c  test    rcx, rcx
0x18000981f  jz      short loc_18000982D
0x180009821  mov     rax, [rcx]
0x180009824  mov     rax, [rax+10h]
0x180009828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000982d  mov     eax, ebx
0x18000982f  mov     rbx, [rsp+40h+arg_0]
0x180009834  mov     rdi, [rsp+40h+arg_18]
0x18000983c  add     rsp, 40h
0x180009840  pop     r15
0x180009842  pop     r14
0x180009844  pop     r13
0x180009846  pop     r12
0x180009848  pop     rbp
0x180009849  retn
0x18000984a  mov     rcx, [r15+18h]
0x18000984e  jmp     loc_1800095EC
0x180009853  mov     eax, 80070057h
0x180009858  jmp     short loc_180009834
```
