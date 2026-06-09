# CMCellularEntriesNodeProcessor::ProcessNode(IConfigManager2 *,IDomNode *)

- ea: `0x180022ee0`
- end: `0x180023003`
- name: `?ProcessNode@CMCellularEntriesNodeProcessor@@UEAAJPEAUIConfigManager2@@PEAUIDomNode@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(CMCellularEntriesNodeProcessor *__hidden this, struct IConfigManager2 *, struct IDomNode *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800110bc`
- `0x180012b94`
- `0x180022ee0`
- `0x1800234b8`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180022f7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180022fca`
- `OLEAUT32!__imp_SysFreeString` at `0x180022f7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180022fca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMCellularEntriesNodeProcessor::ProcessNode(
        CMCellularEntriesNodeProcessor *this,
        struct IConfigManager2 *a2,
        struct IDomNode *a3)
{
  unsigned __int16 *v6; // rbx
  int TranslatedPath; // edi
  BSTR *v8; // r14
  int v9; // eax
  CWAPNodeProcessorBase *v10; // rcx
  __int64 v12[7]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v13; // [rsp+78h] [rbp+10h] BYREF
  __int64 v14; // [rsp+88h] [rbp+20h] BYREF

  v14 = 0;
  v12[0] = 0;
  v6 = 0;
  v13 = 0;
  if ( a2 && a3 )
  {
    TranslatedPath = *((_DWORD *)this + 8);
    if ( TranslatedPath >= 0 )
    {
      TranslatedPath = (*(__int64 (__fastcall **)(struct IDomNode *, __int64 *))(*(_QWORD *)a3 + 144LL))(a3, &v14);
      if ( TranslatedPath >= 0 )
      {
        v8 = (BSTR *)((char *)this + 24);
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v14 + 88LL))(
               v14,
               L"ICCID",
               (char *)this + 24);
        TranslatedPath = v9;
        if ( v9 == -2147023728 )
        {
          SysFreeString(*v8);
          *v8 = 0;
        }
        else if ( v9 < 0 )
        {
          goto LABEL_11;
        }
        TranslatedPath = CWAPNodeProcessorBase::GetTranslatedPath(v10, a3, &v13);
        v6 = v13;
        if ( TranslatedPath >= 0 )
          TranslatedPath = CMCellularEntriesNodeProcessor::ProcessNodeInternal(this, a2, a3, 0, v13);
      }
    }
  }
  else
  {
    TranslatedPath = -2147024809;
  }
LABEL_11:
  SysFreeString(v6);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v12);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v14);
  return (unsigned int)TranslatedPath;
}

```

## disassembly

```asm
0x180022ee0  mov     rax, rsp
0x180022ee3  mov     [rax+8], rbx
0x180022ee7  push    rbp
0x180022ee8  push    rsi
0x180022ee9  push    rdi
0x180022eea  push    r14
0x180022eec  push    r15
0x180022eee  sub     rsp, 40h
0x180022ef2  mov     rsi, r8
0x180022ef5  mov     r15, rdx
0x180022ef8  mov     rbp, rcx
0x180022efb  mov     qword ptr [rax+20h], 0
0x180022f03  mov     qword ptr [rax-38h], 0
0x180022f0b  xor     ebx, ebx
0x180022f0d  mov     [rax+10h], rbx
0x180022f11  test    rdx, rdx
0x180022f14  jnz     short loc_180022F20
0x180022f16  mov     edi, 80070057h
0x180022f1b  jmp     loc_180022FC7
0x180022f20  test    rsi, rsi
0x180022f23  jz      short loc_180022F16
0x180022f25  mov     edi, [rcx+20h]
0x180022f28  test    edi, edi
0x180022f2a  js      loc_180022FC7
0x180022f30  mov     rax, [r8]
0x180022f33  lea     rdx, [rsp+68h+arg_18]
0x180022f3b  mov     rcx, rsi
0x180022f3e  mov     rax, [rax+90h]
0x180022f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f4a  mov     edi, eax
0x180022f4c  test    eax, eax
0x180022f4e  js      short loc_180022FC7
0x180022f50  mov     rcx, [rsp+68h+arg_18]
0x180022f58  lea     r14, [rbp+18h]
0x180022f5c  mov     rax, [rcx]
0x180022f5f  mov     r8, r14
0x180022f62  lea     rdx, c_wszICCIDAttribute; "ICCID"
0x180022f69  mov     rax, [rax+58h]
0x180022f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f72  mov     edi, eax
0x180022f74  cmp     eax, 80070490h
0x180022f79  jnz     short loc_180022F93
0x180022f7b  mov     rcx, [r14]; bstrString
0x180022f7e  call    cs:__imp_SysFreeString
0x180022f85  nop     dword ptr [rax+rax+00h]
0x180022f8a  mov     qword ptr [r14], 0
0x180022f91  jmp     short loc_180022F97
0x180022f93  test    eax, eax
0x180022f95  js      short loc_180022FC7
0x180022f97  lea     r8, [rsp+68h+arg_8]; unsigned __int16 **
0x180022f9c  mov     rdx, rsi; struct IDomNode *
0x180022f9f  call    ?GetTranslatedPath@CWAPNodeProcessorBase@@IEAAJPEAUIDomNode@@PEAPEAG@Z; CWAPNodeProcessorBase::GetTranslatedPath(IDomNode *,ushort * *)
0x180022fa4  mov     edi, eax
0x180022fa6  mov     rbx, [rsp+68h+arg_8]
0x180022fab  test    eax, eax
0x180022fad  js      short loc_180022FC7
0x180022faf  mov     [rsp+68h+var_48], rbx; unsigned __int16 *
0x180022fb4  xor     r9d, r9d; unsigned int
0x180022fb7  mov     r8, rsi; struct IDomNode *
0x180022fba  mov     rdx, r15; struct IConfigManager2 *
0x180022fbd  mov     rcx, rbp; this
0x180022fc0  call    ?ProcessNodeInternal@CMCellularEntriesNodeProcessor@@AEAAJPEAUIConfigManager2@@PEAUIDomNode@@KPEBG@Z; CMCellularEntriesNodeProcessor::ProcessNodeInternal(IConfigManager2 *,IDomNode *,ulong,ushort const *)
0x180022fc5  mov     edi, eax
0x180022fc7  mov     rcx, rbx; bstrString
0x180022fca  call    cs:__imp_SysFreeString
0x180022fd1  nop     dword ptr [rax+rax+00h]
0x180022fd6  nop
0x180022fd7  lea     rcx, [rsp+68h+var_38]
0x180022fdc  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180022fe1  nop
0x180022fe2  lea     rcx, [rsp+68h+arg_18]
0x180022fea  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180022fef  mov     eax, edi
0x180022ff1  mov     rbx, [rsp+68h+arg_0]
0x180022ff6  add     rsp, 40h
0x180022ffa  pop     r15
0x180022ffc  pop     r14
0x180022ffe  pop     rdi
0x180022fff  pop     rsi
0x180023000  pop     rbp
0x180023001  retn
```
