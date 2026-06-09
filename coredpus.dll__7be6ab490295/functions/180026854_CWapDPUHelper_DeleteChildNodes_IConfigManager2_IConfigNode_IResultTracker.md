# CWapDPUHelper::DeleteChildNodes(IConfigManager2 *,IConfigNode *,IResultTracker *)

- ea: `0x180026854`
- end: `0x180026a17`
- name: `?DeleteChildNodes@CWapDPUHelper@@AEAAJPEAUIConfigManager2@@PEAUIConfigNode@@PEAUIResultTracker@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CWapDPUHelper *__hidden this, struct IConfigManager2 *, struct IConfigNode *, struct IResultTracker *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026a20`

## callees

- `0x1800110bc`
- `0x180023b0c`
- `0x180026854`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180026934`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180026934`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CWapDPUHelper::DeleteChildNodes(
        CWapDPUHelper *this,
        struct IConfigManager2 *a2,
        struct IConfigNode *a3,
        struct IResultTracker *a4)
{
  int i; // ebx
  __int64 v8; // rcx
  BSTR bstrString; // [rsp+38h] [rbp-50h] BYREF
  __int64 v11; // [rsp+40h] [rbp-48h] BYREF
  __int64 v12; // [rsp+48h] [rbp-40h] BYREF
  __int64 v13[7]; // [rsp+50h] [rbp-38h] BYREF
  int v14; // [rsp+A0h] [rbp+18h] BYREF

  v14 = 0;
  v13[0] = 0;
  v12 = 0;
  v11 = 0;
  bstrString = 0;
  i = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64 *))(*(_QWORD *)a3 + 192LL))(a3, v13);
  if ( i >= 0 )
  {
    for ( i = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v13[0] + 24LL))(
                v13[0],
                1,
                &v12,
                &v14);
          i >= 0;
          i = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v13[0] + 24LL))(
                v13[0],
                1,
                &v12,
                &v14) )
    {
      if ( v14 != 1 )
        break;
      v8 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      i = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 120LL))(v12, &v11);
      if ( i < 0 )
        break;
      SysFreeString(bstrString);
      bstrString = 0;
      i = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v11 + 64LL))(v11, 0, 0, &bstrString);
      if ( i < 0 )
        break;
      i = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, BSTR, struct IResultTracker *))(*(_QWORD *)this + 40LL))(
            this,
            a2,
            bstrString,
            a4);
      if ( i < 0 )
        break;
      v14 = 0;
      ATL::CComPtrBase<IDomNode>::Release(&v12);
    }
  }
  SysFreeString(bstrString);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v11);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v12);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v13);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180026854  mov     rax, rsp
0x180026857  push    rbx
0x180026858  push    rsi
0x180026859  push    rdi
0x18002685a  push    r14
0x18002685c  sub     rsp, 68h
0x180026860  mov     rsi, r9
0x180026863  mov     r14, rdx
0x180026866  mov     rdi, rcx
0x180026869  mov     dword ptr [rax+18h], 0
0x180026870  mov     qword ptr [rax-38h], 0
0x180026878  mov     qword ptr [rax-40h], 0
0x180026880  mov     qword ptr [rax-48h], 0
0x180026888  mov     qword ptr [rax-50h], 0
0x180026890  mov     rax, [r8]
0x180026893  lea     rdx, [rsp+88h+var_38]
0x180026898  mov     rcx, r8
0x18002689b  mov     rax, [rax+0C0h]
0x1800268a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268a7  mov     ebx, eax
0x1800268a9  test    eax, eax
0x1800268ab  jns     short loc_1800268B2
0x1800268ad  jmp     loc_1800269D8
0x1800268b2  mov     rcx, [rsp+88h+var_38]
0x1800268b7  mov     rax, [rcx]
0x1800268ba  lea     r9, [rsp+88h+arg_10]
0x1800268c2  lea     r8, [rsp+88h+var_40]
0x1800268c7  mov     edx, 1
0x1800268cc  mov     rax, [rax+18h]
0x1800268d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268d5  mov     ebx, eax
0x1800268d7  test    eax, eax
0x1800268d9  jns     short loc_1800268E0
0x1800268db  jmp     loc_1800269D8
0x1800268e0  cmp     [rsp+88h+arg_10], 1
0x1800268e8  jnz     loc_1800269D2
0x1800268ee  mov     rcx, [rsp+88h+var_48]
0x1800268f3  test    rcx, rcx
0x1800268f6  jz      short loc_18002690E
0x1800268f8  mov     [rsp+88h+var_48], 0
0x180026901  mov     rax, [rcx]
0x180026904  mov     rax, [rax+10h]
0x180026908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002690d  nop
0x18002690e  mov     rcx, [rsp+88h+var_40]
0x180026913  mov     rax, [rcx]
0x180026916  lea     rdx, [rsp+88h+var_48]
0x18002691b  mov     rax, [rax+78h]
0x18002691f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026924  mov     ebx, eax
0x180026926  test    eax, eax
0x180026928  jns     short loc_18002692F
0x18002692a  jmp     loc_1800269D8
0x18002692f  mov     rcx, [rsp+88h+bstrString]; bstrString
0x180026934  call    cs:__imp_SysFreeString
0x18002693b  nop     dword ptr [rax+rax+00h]
0x180026940  mov     [rsp+88h+bstrString], 0
0x180026949  mov     rcx, [rsp+88h+var_48]
0x18002694e  mov     rax, [rcx]
0x180026951  lea     r9, [rsp+88h+bstrString]
0x180026956  xor     r8d, r8d
0x180026959  xor     edx, edx
0x18002695b  mov     rax, [rax+40h]
0x18002695f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026964  mov     ebx, eax
0x180026966  test    eax, eax
0x180026968  jns     short loc_18002696C
0x18002696a  jmp     short loc_1800269D8
0x18002696c  mov     rax, [rdi]
0x18002696f  mov     r9, rsi
0x180026972  mov     r8, [rsp+88h+bstrString]
0x180026977  mov     rdx, r14
0x18002697a  mov     rcx, rdi
0x18002697d  mov     rax, [rax+28h]
0x180026981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026986  mov     ebx, eax
0x180026988  test    eax, eax
0x18002698a  jns     short loc_18002698E
0x18002698c  jmp     short loc_1800269D8
0x18002698e  mov     [rsp+88h+arg_10], 0
0x180026999  lea     rcx, [rsp+88h+var_40]
0x18002699e  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x1800269a3  mov     rcx, [rsp+88h+var_38]
0x1800269a8  mov     rax, [rcx]
0x1800269ab  lea     r9, [rsp+88h+arg_10]
0x1800269b3  lea     r8, [rsp+88h+var_40]
0x1800269b8  mov     edx, 1
0x1800269bd  mov     rax, [rax+18h]
0x1800269c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269c6  mov     ebx, eax
0x1800269c8  test    eax, eax
0x1800269ca  jns     loc_1800268E0
0x1800269d0  jmp     short loc_1800269D8
0x1800269d2  jmp     short loc_1800269D8
0x1800269d4  mov     ebx, [rsp+88h+var_58]
0x1800269d8  mov     rcx, [rsp+88h+bstrString]; bstrString
0x1800269dd  call    cs:__imp_SysFreeString
0x1800269e4  nop     dword ptr [rax+rax+00h]
0x1800269e9  nop
0x1800269ea  lea     rcx, [rsp+88h+var_48]
0x1800269ef  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800269f4  nop
0x1800269f5  lea     rcx, [rsp+88h+var_40]
0x1800269fa  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800269ff  nop
0x180026a00  lea     rcx, [rsp+88h+var_38]
0x180026a05  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026a0a  mov     eax, ebx
0x180026a0c  add     rsp, 68h
0x180026a10  pop     r14
0x180026a12  pop     rdi
0x180026a13  pop     rsi
0x180026a14  pop     rbx
0x180026a15  retn
```
