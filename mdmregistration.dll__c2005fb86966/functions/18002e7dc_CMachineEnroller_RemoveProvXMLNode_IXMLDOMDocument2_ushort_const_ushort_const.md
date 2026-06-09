# CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)

- ea: `0x18002e7dc`
- end: `0x18002eb45`
- name: `?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z`
- size: `873`
- prototype: `static int(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800226a4`
- `0x180022e74`
- `0x18002bcdc`

## callees

- `0x1800141b0`
- `0x180022544`
- `0x18002e7dc`
- `0x18004e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002e867`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e8d5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e867`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e8d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e914`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ead2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eae0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e914`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ead2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eae0`
- `OLEAUT32!__imp_VariantClear` at `0x18002e84f`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8bc`
- `OLEAUT32!__imp_VariantClear` at `0x18002e84f`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8bc`

## string_xrefs

- `0x18002e815`: `CMachineEnroller::RemoveProvXMLNode`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMachineEnroller::RemoveProvXMLNode(
        struct IXMLDOMDocument2 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // r14
  BSTR v7; // rax
  OLECHAR *v8; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  __int64 v12; // [rsp+20h] [rbp-29h] BYREF
  __int64 v13; // [rsp+28h] [rbp-21h] BYREF
  __int64 v14; // [rsp+30h] [rbp-19h] BYREF
  __int64 v15; // [rsp+38h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp+Fh] BYREF
  VARIANTARG v18; // [rsp+70h] [rbp+27h] BYREF
  int v19; // [rsp+B0h] [rbp+67h] BYREF
  int v20; // [rsp+C8h] [rbp+7Fh] BYREF

  v19 = 0;
  v15 = 0;
  v20 = 0;
  v17[0] = "CMachineEnroller::RemoveProvXMLNode";
  v17[1] = &v19;
  if ( a1 )
  {
    if ( !a3 )
      goto LABEL_6;
    lpVtbl = a1->lpVtbl;
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a3);
    if ( !pvarg.llVal )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v18 = pvarg;
    v19 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const OLECHAR *, VARIANTARG *))lpVtbl->setProperty)(
            a1,
            L"SelectionNamespaces",
            &v18);
    VariantClear(&pvarg);
    if ( v19 >= 0 )
    {
LABEL_6:
      v7 = SysAllocString(a2);
      v8 = v7;
      if ( v7 )
      {
        v19 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, __int64 *))a1->lpVtbl->selectNodes)(
                a1,
                v7,
                &v15);
        SysFreeString(v8);
        if ( v19 >= 0 && v15 )
        {
          v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 64LL))(v15, &v20);
          if ( v19 >= 0 )
          {
            v9 = 0;
            if ( v20 > 0 )
            {
              while ( 1 )
              {
                v12 = 0;
                v14 = 0;
                v13 = 0;
                v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 56LL))(v15, v9, &v12);
                if ( v19 < 0 )
                  break;
                v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 88LL))(v12, &v13);
                if ( v19 )
                {
                  if ( v13 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                  if ( v14 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                  goto LABEL_37;
                }
                v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v13 + 160LL))(v13, v12, &v14);
                if ( v19 < 0 )
                {
                  if ( v13 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                  if ( v14 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                  goto LABEL_37;
                }
                if ( v13 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                if ( v14 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                if ( v12 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                if ( (int)++v9 >= v20 )
                  goto LABEL_41;
              }
              if ( v13 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              if ( v14 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_37:
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            }
          }
        }
        else
        {
          v19 = -2102788095;
        }
      }
      else
      {
        v19 = -2147024882;
      }
    }
  }
  else
  {
    v19 = -2147467261;
  }
LABEL_41:
  SysFreeString(0);
  SysFreeString(0);
  v10 = v19;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v17);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return v10;
}

```

## disassembly

```asm
0x18002e7dc  mov     [rsp-8+arg_8], rbx
0x18002e7e1  mov     [rsp-8+arg_10], rsi
0x18002e7e6  push    rbp
0x18002e7e7  push    rdi
0x18002e7e8  push    r14
0x18002e7ea  lea     rbp, [rsp-47h]
0x18002e7ef  sub     rsp, 90h
0x18002e7f6  mov     rdi, r8
0x18002e7f9  mov     rsi, rdx
0x18002e7fc  mov     rbx, rcx
0x18002e7ff  mov     [rbp+57h+arg_0], 0
0x18002e806  mov     [rbp+57h+var_68], 0
0x18002e80e  mov     [rbp+57h+arg_18], 0
0x18002e815  lea     rax, aCmachineenroll; "CMachineEnroller::RemoveProvXMLNode"
0x18002e81c  mov     [rbp+57h+var_48], rax
0x18002e820  lea     rax, [rbp+57h+arg_0]
0x18002e824  mov     [rbp+57h+var_40], rax
0x18002e828  test    rcx, rcx
0x18002e82b  jnz     short loc_18002E839
0x18002e82d  mov     [rbp+57h+arg_0], 80004003h
0x18002e834  jmp     loc_18002EAD0
0x18002e839  test    rdi, rdi
0x18002e83c  jz      loc_18002E8D2
0x18002e842  mov     r14, [rcx]
0x18002e845  xor     eax, eax
0x18002e847  mov     word ptr [rbp+57h+pvarg], ax
0x18002e84b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e84f  call    cs:__imp_VariantClear
0x18002e856  nop     dword ptr [rax+rax+00h]
0x18002e85b  mov     eax, 8
0x18002e860  mov     word ptr [rbp+57h+pvarg], ax
0x18002e864  mov     rcx, rdi; psz
0x18002e867  call    cs:__imp_SysAllocString
0x18002e86e  nop     dword ptr [rax+rax+00h]
0x18002e873  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18002e876  mov     rcx, rax
0x18002e879  sar     rcx, 20h
0x18002e87d  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x18002e880  test    rax, rax
0x18002e883  jz      loc_18002EB2A
0x18002e889  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002e88d  movaps  [rbp+57h+var_30], xmm0
0x18002e891  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002e896  movsd   [rbp+57h+var_20], xmm1
0x18002e89b  lea     r8, [rbp+57h+var_30]
0x18002e89f  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18002e8a6  mov     rcx, rbx
0x18002e8a9  mov     rax, [r14+280h]
0x18002e8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8b5  mov     [rbp+57h+arg_0], eax
0x18002e8b8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e8bc  call    cs:__imp_VariantClear
0x18002e8c3  nop     dword ptr [rax+rax+00h]
0x18002e8c8  cmp     [rbp+57h+arg_0], 0
0x18002e8cc  jl      loc_18002EAD0
0x18002e8d2  mov     rcx, rsi; psz
0x18002e8d5  call    cs:__imp_SysAllocString
0x18002e8dc  nop     dword ptr [rax+rax+00h]
0x18002e8e1  mov     rdi, rax
0x18002e8e4  test    rax, rax
0x18002e8e7  jnz     short loc_18002E8F5
0x18002e8e9  mov     [rbp+57h+arg_0], 8007000Eh
0x18002e8f0  jmp     loc_18002EAD0
0x18002e8f5  mov     rax, [rbx]
0x18002e8f8  lea     r8, [rbp+57h+var_68]
0x18002e8fc  mov     rdx, rdi
0x18002e8ff  mov     rcx, rbx
0x18002e902  mov     rax, [rax+120h]
0x18002e909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e90e  mov     [rbp+57h+arg_0], eax
0x18002e911  mov     rcx, rdi; bstrString
0x18002e914  call    cs:__imp_SysFreeString
0x18002e91b  nop     dword ptr [rax+rax+00h]
0x18002e920  cmp     [rbp+57h+arg_0], 0
0x18002e924  jl      loc_18002EAC9
0x18002e92a  mov     rcx, [rbp+57h+var_68]
0x18002e92e  test    rcx, rcx
0x18002e931  jz      loc_18002EAC9
0x18002e937  mov     rax, [rcx]
0x18002e93a  lea     rdx, [rbp+57h+arg_18]
0x18002e93e  mov     rax, [rax+40h]
0x18002e942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e947  mov     [rbp+57h+arg_0], eax
0x18002e94a  test    eax, eax
0x18002e94c  js      loc_18002EAD0
0x18002e952  xor     ebx, ebx
0x18002e954  cmp     [rbp+57h+arg_18], ebx
0x18002e957  jle     loc_18002EAD0
0x18002e95d  mov     [rbp+57h+var_80], 0
0x18002e965  mov     [rbp+57h+var_70], 0
0x18002e96d  mov     [rbp+57h+var_78], 0
0x18002e975  mov     rcx, [rbp+57h+var_68]
0x18002e979  mov     rax, [rcx]
0x18002e97c  lea     r8, [rbp+57h+var_80]
0x18002e980  mov     edx, ebx
0x18002e982  mov     rax, [rax+38h]
0x18002e986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e98b  mov     [rbp+57h+arg_0], eax
0x18002e98e  test    eax, eax
0x18002e990  js      loc_18002EA85
0x18002e996  mov     rcx, [rbp+57h+var_80]
0x18002e99a  mov     rax, [rcx]
0x18002e99d  lea     rdx, [rbp+57h+var_78]
0x18002e9a1  mov     rax, [rax+58h]
0x18002e9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9aa  mov     [rbp+57h+arg_0], eax
0x18002e9ad  test    eax, eax
0x18002e9af  jnz     loc_18002EA57
0x18002e9b5  mov     rcx, [rbp+57h+var_78]
0x18002e9b9  mov     rax, [rcx]
0x18002e9bc  lea     r8, [rbp+57h+var_70]
0x18002e9c0  mov     rdx, [rbp+57h+var_80]
0x18002e9c4  mov     rax, [rax+0A0h]
0x18002e9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9d0  mov     [rbp+57h+arg_0], eax
0x18002e9d3  test    eax, eax
0x18002e9d5  js      short loc_18002EA29
0x18002e9d7  mov     rcx, [rbp+57h+var_78]
0x18002e9db  test    rcx, rcx
0x18002e9de  jz      short loc_18002E9ED
0x18002e9e0  mov     rax, [rcx]
0x18002e9e3  mov     rax, [rax+10h]
0x18002e9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9ec  nop
0x18002e9ed  mov     rcx, [rbp+57h+var_70]
0x18002e9f1  test    rcx, rcx
0x18002e9f4  jz      short loc_18002EA03
0x18002e9f6  mov     rax, [rcx]
0x18002e9f9  mov     rax, [rax+10h]
0x18002e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea02  nop
0x18002ea03  mov     rcx, [rbp+57h+var_80]
0x18002ea07  test    rcx, rcx
0x18002ea0a  jz      short loc_18002EA19
0x18002ea0c  mov     rax, [rcx]
0x18002ea0f  mov     rax, [rax+10h]
0x18002ea13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea18  nop
0x18002ea19  inc     ebx
0x18002ea1b  cmp     ebx, [rbp+57h+arg_18]
0x18002ea1e  jl      loc_18002E95D
0x18002ea24  jmp     loc_18002EAD0
0x18002ea29  mov     rcx, [rbp+57h+var_78]
0x18002ea2d  test    rcx, rcx
0x18002ea30  jz      short loc_18002EA3F
0x18002ea32  mov     rax, [rcx]
0x18002ea35  mov     rax, [rax+10h]
0x18002ea39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea3e  nop
0x18002ea3f  mov     rcx, [rbp+57h+var_70]
0x18002ea43  test    rcx, rcx
0x18002ea46  jz      short loc_18002EA55
0x18002ea48  mov     rax, [rcx]
0x18002ea4b  mov     rax, [rax+10h]
0x18002ea4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea54  nop
0x18002ea55  jmp     short loc_18002EAB1
0x18002ea57  mov     rcx, [rbp+57h+var_78]
0x18002ea5b  test    rcx, rcx
0x18002ea5e  jz      short loc_18002EA6D
0x18002ea60  mov     rax, [rcx]
0x18002ea63  mov     rax, [rax+10h]
0x18002ea67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea6c  nop
0x18002ea6d  mov     rcx, [rbp+57h+var_70]
0x18002ea71  test    rcx, rcx
0x18002ea74  jz      short loc_18002EA83
0x18002ea76  mov     rax, [rcx]
0x18002ea79  mov     rax, [rax+10h]
0x18002ea7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea82  nop
0x18002ea83  jmp     short loc_18002EAB1
0x18002ea85  mov     rcx, [rbp+57h+var_78]
0x18002ea89  test    rcx, rcx
0x18002ea8c  jz      short loc_18002EA9B
0x18002ea8e  mov     rax, [rcx]
0x18002ea91  mov     rax, [rax+10h]
0x18002ea95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea9a  nop
0x18002ea9b  mov     rcx, [rbp+57h+var_70]
0x18002ea9f  test    rcx, rcx
0x18002eaa2  jz      short loc_18002EAB1
0x18002eaa4  mov     rax, [rcx]
0x18002eaa7  mov     rax, [rax+10h]
0x18002eaab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eab0  nop
0x18002eab1  mov     rcx, [rbp+57h+var_80]
0x18002eab5  test    rcx, rcx
0x18002eab8  jz      short loc_18002EAC7
0x18002eaba  mov     rax, [rcx]
0x18002eabd  mov     rax, [rax+10h]
0x18002eac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac6  nop
0x18002eac7  jmp     short loc_18002EAD0
0x18002eac9  mov     [rbp+57h+arg_0], 82AA0001h
0x18002ead0  xor     ecx, ecx; bstrString
0x18002ead2  call    cs:__imp_SysFreeString
0x18002ead9  nop     dword ptr [rax+rax+00h]
0x18002eade  xor     ecx, ecx; bstrString
0x18002eae0  call    cs:__imp_SysFreeString
0x18002eae7  nop     dword ptr [rax+rax+00h]
0x18002eaec  mov     ebx, [rbp+57h+arg_0]
0x18002eaef  lea     rcx, [rbp+57h+var_48]; this
0x18002eaf3  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002eaf8  nop
0x18002eaf9  mov     rcx, [rbp+57h+var_68]
0x18002eafd  test    rcx, rcx
0x18002eb00  jz      short loc_18002EB0F
0x18002eb02  mov     rdx, [rcx]
0x18002eb05  mov     rax, [rdx+10h]
0x18002eb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb0e  nop
0x18002eb0f  mov     eax, ebx
0x18002eb11  lea     r11, [rsp+0A0h+var_10]
0x18002eb19  mov     rbx, [r11+28h]
0x18002eb1d  mov     rsi, [r11+30h]
0x18002eb21  mov     rsp, r11
0x18002eb24  pop     r14
0x18002eb26  pop     rdi
0x18002eb27  pop     rbp
0x18002eb28  retn
0x18002eb2a  mov     eax, 0Ah
0x18002eb2f  mov     word ptr [rbp+57h+pvarg], ax
0x18002eb33  mov     dword ptr [rbp+57h+pvarg+8], 8007000Eh
0x18002eb3a  mov     ecx, 8007000Eh; int
0x18002eb3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
