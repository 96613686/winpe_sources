# CWapDPUHelper::PopulateChildNodes(IConfigManager2 *,ushort const *,IConfigNode *,IDomNode *,int)

- ea: `0x180027550`
- end: `0x1800278ab`
- name: `?PopulateChildNodes@CWapDPUHelper@@AEAAJPEAUIConfigManager2@@PEBGPEAUIConfigNode@@PEAUIDomNode@@H@Z`
- size: `859`
- prototype: `__int64 __fastcall(CWapDPUHelper *__hidden this, struct IConfigManager2 *, const unsigned __int16 *, struct IConfigNode *, struct IDomNode *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027ce0`

## callees

- `0x1800110bc`
- `0x1800118a0`
- `0x180013b80`
- `0x180014330`
- `0x18001d87c`
- `0x180022874`
- `0x180023b0c`
- `0x180027550`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180027625`
- `OLEAUT32!__imp_SysFreeString` at `0x180027760`
- `OLEAUT32!__imp_SysFreeString` at `0x18002784a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002785c`
- `OLEAUT32!__imp_SysFreeString` at `0x180027625`
- `OLEAUT32!__imp_SysFreeString` at `0x180027760`
- `OLEAUT32!__imp_SysFreeString` at `0x18002784a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002785c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CWapDPUHelper::PopulateChildNodes(
        CWapDPUHelper *this,
        struct IConfigManager2 *a2,
        const unsigned __int16 *a3,
        struct IConfigNode *a4,
        struct IDomNode *a5,
        int a6)
{
  __int64 v8; // r9
  int v9; // ebx
  __int64 (__fastcall *v10)(CWapDPUHelper *, const wchar_t *, __int64 *, struct IDomNode *); // rax
  _QWORD *v11; // r8
  __int64 v13; // [rsp+30h] [rbp-98h] BYREF
  int v14; // [rsp+38h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-88h] BYREF
  __int64 v16; // [rsp+48h] [rbp-80h] BYREF
  int v17; // [rsp+50h] [rbp-78h] BYREF
  BSTR v18; // [rsp+58h] [rbp-70h] BYREF
  __int64 v19; // [rsp+60h] [rbp-68h] BYREF
  _QWORD v20[4]; // [rsp+70h] [rbp-58h] BYREF

  v19 = 0;
  v16 = 0;
  v13 = 0;
  v17 = 1;
  bstrString = 0;
  v18 = 0;
  std::wstring::wstring(v20);
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 192LL))(v8, &v19);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v19 + 24LL))(v19, 1, &v16, &v14);
    if ( v9 >= 0 )
    {
      while ( v14 == 1 )
      {
        SysFreeString(bstrString);
        bstrString = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 128LL))(v16, &bstrString);
        if ( v9 < 0 )
          break;
        v9 = (*(__int64 (__fastcall **)(CWapDPUHelper *, __int64, int *))(*(_QWORD *)this + 88LL))(this, v16, &v17);
        if ( v9 < 0 )
          break;
        if ( v17 == 8 )
        {
          ATL::CComPtrBase<IDomNode>::Release(&v13);
          v10 = *(__int64 (__fastcall **)(CWapDPUHelper *, const wchar_t *, __int64 *, struct IDomNode *))(*(_QWORD *)this + 120LL);
          if ( a6 )
          {
            v9 = v10(this, L"characteristic-query", &v13, a5);
            if ( v9 < 0 )
              break;
          }
          else
          {
            v9 = v10(this, L"characteristic", &v13, a5);
            if ( v9 < 0 )
              break;
          }
          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR))(*(_QWORD *)v13 + 96LL))(
                 v13,
                 L"type",
                 bstrString);
          if ( v9 < 0 )
            break;
        }
        else
        {
          ATL::CComPtrBase<IDomNode>::Release(&v13);
          v9 = (*(__int64 (__fastcall **)(CWapDPUHelper *, const wchar_t *, __int64 *, struct IDomNode *))(*(_QWORD *)this + 120LL))(
                 this,
                 L"parm-query",
                 &v13,
                 a5);
          if ( v9 < 0 )
            break;
          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR))(*(_QWORD *)v13 + 96LL))(
                 v13,
                 L"name",
                 bstrString);
          if ( v9 < 0 )
            break;
        }
        SysFreeString(v18);
        v18 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 72LL))(v13, &v18);
        if ( v9 >= 0 )
        {
          std::wstring::assign(v20);
          std::wstring::append(v20, L"/");
          std::wstring::append(v20, v18);
          v11 = v20;
          if ( v20[3] > 7u )
            v11 = (_QWORD *)v20[0];
          v9 = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, _QWORD *, __int64))(*(_QWORD *)this + 64LL))(
                 this,
                 a2,
                 v11,
                 v13);
          if ( v9 >= 0 )
          {
            v14 = 0;
            ATL::CComPtrBase<IDomNode>::Release(&v16);
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v19 + 24LL))(
                   v19,
                   1,
                   &v16,
                   &v14);
            if ( v9 >= 0 )
              continue;
          }
        }
        break;
      }
    }
  }
  std::wstring::_Tidy_deallocate(v20);
  SysFreeString(v18);
  SysFreeString(bstrString);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v13);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v16);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027550  mov     r11, rsp
0x180027553  push    rbx
0x180027554  push    rsi
0x180027555  push    rdi
0x180027556  push    r14
0x180027558  push    r15
0x18002755a  sub     rsp, 0A0h
0x180027561  mov     rax, cs:__security_cookie
0x180027568  xor     rax, rsp
0x18002756b  mov     [rsp+0C8h+var_38], rax
0x180027573  mov     r14, r8
0x180027576  mov     r15, rdx
0x180027579  mov     rdi, rcx
0x18002757c  mov     rsi, [rsp+0C8h+arg_20]
0x180027584  mov     qword ptr [r11-68h], 0
0x18002758c  mov     qword ptr [r11-80h], 0
0x180027594  mov     [rsp+0C8h+var_98], 0
0x18002759d  mov     [rsp+0C8h+var_78], 1
0x1800275a5  mov     [rsp+0C8h+bstrString], 0
0x1800275ae  mov     qword ptr [r11-70h], 0
0x1800275b6  lea     rcx, [r11-58h]
0x1800275ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800275bf  nop
0x1800275c0  mov     [rsp+0C8h+var_90], 0
0x1800275c8  mov     rax, [r9]
0x1800275cb  lea     rdx, [rsp+0C8h+var_68]
0x1800275d0  mov     rcx, r9
0x1800275d3  mov     rax, [rax+0C0h]
0x1800275da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275df  mov     ebx, eax
0x1800275e1  test    eax, eax
0x1800275e3  jns     short loc_1800275EA
0x1800275e5  jmp     loc_18002783A
0x1800275ea  mov     rcx, [rsp+0C8h+var_68]
0x1800275ef  mov     rax, [rcx]
0x1800275f2  lea     r9, [rsp+0C8h+var_90]
0x1800275f7  lea     r8, [rsp+0C8h+var_80]
0x1800275fc  mov     edx, 1
0x180027601  mov     rax, [rax+18h]
0x180027605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002760a  mov     ebx, eax
0x18002760c  test    eax, eax
0x18002760e  jns     short loc_180027615
0x180027610  jmp     loc_18002783A
0x180027615  cmp     [rsp+0C8h+var_90], 1
0x18002761a  jnz     loc_180027834
0x180027620  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x180027625  call    cs:__imp_SysFreeString
0x18002762c  nop     dword ptr [rax+rax+00h]
0x180027631  mov     [rsp+0C8h+bstrString], 0
0x18002763a  mov     rcx, [rsp+0C8h+var_80]
0x18002763f  mov     rax, [rcx]
0x180027642  lea     rdx, [rsp+0C8h+bstrString]
0x180027647  mov     rax, [rax+80h]
0x18002764e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027653  mov     ebx, eax
0x180027655  test    eax, eax
0x180027657  jns     short loc_18002765E
0x180027659  jmp     loc_18002783A
0x18002765e  mov     rax, [rdi]
0x180027661  lea     r8, [rsp+0C8h+var_78]
0x180027666  mov     rdx, [rsp+0C8h+var_80]
0x18002766b  mov     rcx, rdi
0x18002766e  mov     rax, [rax+58h]
0x180027672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027677  mov     ebx, eax
0x180027679  test    eax, eax
0x18002767b  jns     short loc_180027682
0x18002767d  jmp     loc_18002783A
0x180027682  lea     rcx, [rsp+0C8h+var_98]
0x180027687  cmp     [rsp+0C8h+var_78], 8
0x18002768c  jnz     short loc_180027705
0x18002768e  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x180027693  mov     rax, [rdi]
0x180027696  mov     rax, [rax+78h]
0x18002769a  mov     r9, rsi
0x18002769d  lea     r8, [rsp+0C8h+var_98]
0x1800276a2  mov     rcx, rdi
0x1800276a5  cmp     [rsp+0C8h+arg_28], 0
0x1800276ad  jz      short loc_1800276C6
0x1800276af  lea     rdx, aCharacteristic; "characteristic-query"
0x1800276b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276bb  mov     ebx, eax
0x1800276bd  test    eax, eax
0x1800276bf  jns     short loc_1800276DD
0x1800276c1  jmp     loc_18002783A
0x1800276c6  lea     rdx, aCharacteristic_0; "characteristic"
0x1800276cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276d2  mov     ebx, eax
0x1800276d4  test    eax, eax
0x1800276d6  jns     short loc_1800276DD
0x1800276d8  jmp     loc_18002783A
0x1800276dd  mov     rcx, [rsp+0C8h+var_98]
0x1800276e2  mov     rax, [rcx]
0x1800276e5  mov     r8, [rsp+0C8h+bstrString]
0x1800276ea  lea     rdx, String2; "type"
0x1800276f1  mov     rax, [rax+60h]
0x1800276f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276fa  mov     ebx, eax
0x1800276fc  test    eax, eax
0x1800276fe  jns     short loc_18002775B
0x180027700  jmp     loc_18002783A
0x180027705  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x18002770a  mov     rax, [rdi]
0x18002770d  mov     r9, rsi
0x180027710  lea     r8, [rsp+0C8h+var_98]
0x180027715  lea     rdx, aParmQuery; "parm-query"
0x18002771c  mov     rcx, rdi
0x18002771f  mov     rax, [rax+78h]
0x180027723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027728  mov     ebx, eax
0x18002772a  test    eax, eax
0x18002772c  jns     short loc_180027733
0x18002772e  jmp     loc_18002783A
0x180027733  mov     rcx, [rsp+0C8h+var_98]
0x180027738  mov     rax, [rcx]
0x18002773b  mov     r8, [rsp+0C8h+bstrString]
0x180027740  lea     rdx, aName_0; "name"
0x180027747  mov     rax, [rax+60h]
0x18002774b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027750  mov     ebx, eax
0x180027752  test    eax, eax
0x180027754  jns     short loc_18002775B
0x180027756  jmp     loc_18002783A
0x18002775b  mov     rcx, [rsp+0C8h+var_70]; bstrString
0x180027760  call    cs:__imp_SysFreeString
0x180027767  nop     dword ptr [rax+rax+00h]
0x18002776c  mov     [rsp+0C8h+var_70], 0
0x180027775  mov     rcx, [rsp+0C8h+var_98]
0x18002777a  mov     rax, [rcx]
0x18002777d  lea     rdx, [rsp+0C8h+var_70]
0x180027782  mov     rax, [rax+48h]
0x180027786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002778b  mov     ebx, eax
0x18002778d  test    eax, eax
0x18002778f  jns     short loc_180027796
0x180027791  jmp     loc_18002783A
0x180027796  mov     rdx, r14
0x180027799  lea     rcx, [rsp+0C8h+var_58]
0x18002779e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800277a3  lea     rdx, asc_180032DA8; "/"
0x1800277aa  lea     rcx, [rsp+0C8h+var_58]
0x1800277af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800277b4  mov     rdx, [rsp+0C8h+var_70]
0x1800277b9  lea     rcx, [rsp+0C8h+var_58]
0x1800277be  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800277c3  mov     rax, [rdi]
0x1800277c6  lea     r8, [rsp+0C8h+var_58]
0x1800277cb  cmp     [rsp+0C8h+var_40], 7
0x1800277d4  cmova   r8, [rsp+0C8h+var_58]
0x1800277da  mov     r9, [rsp+0C8h+var_98]
0x1800277df  mov     rdx, r15
0x1800277e2  mov     rcx, rdi
0x1800277e5  mov     rax, [rax+40h]
0x1800277e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277ee  mov     ebx, eax
0x1800277f0  test    eax, eax
0x1800277f2  jns     short loc_1800277F6
0x1800277f4  jmp     short loc_18002783A
0x1800277f6  mov     [rsp+0C8h+var_90], 0
0x1800277fe  lea     rcx, [rsp+0C8h+var_80]
0x180027803  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x180027808  mov     rcx, [rsp+0C8h+var_68]
0x18002780d  mov     rax, [rcx]
0x180027810  lea     r9, [rsp+0C8h+var_90]
0x180027815  lea     r8, [rsp+0C8h+var_80]
0x18002781a  mov     edx, 1
0x18002781f  mov     rax, [rax+18h]
0x180027823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027828  mov     ebx, eax
0x18002782a  test    eax, eax
0x18002782c  jns     loc_180027615
0x180027832  jmp     short loc_18002783A
0x180027834  jmp     short loc_18002783A
0x180027836  mov     ebx, [rsp+0C8h+var_60]
0x18002783a  lea     rcx, [rsp+0C8h+var_58]; void *
0x18002783f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027844  nop
0x180027845  mov     rcx, [rsp+0C8h+var_70]; bstrString
0x18002784a  call    cs:__imp_SysFreeString
0x180027851  nop     dword ptr [rax+rax+00h]
0x180027856  nop
0x180027857  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18002785c  call    cs:__imp_SysFreeString
0x180027863  nop     dword ptr [rax+rax+00h]
0x180027868  nop
0x180027869  lea     rcx, [rsp+0C8h+var_98]
0x18002786e  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180027873  nop
0x180027874  lea     rcx, [rsp+0C8h+var_80]
0x180027879  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002787e  nop
0x18002787f  lea     rcx, [rsp+0C8h+var_68]
0x180027884  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180027889  mov     eax, ebx
0x18002788b  mov     rcx, [rsp+0C8h+var_38]
0x180027893  xor     rcx, rsp; StackCookie
0x180027896  call    __security_check_cookie
0x18002789b  add     rsp, 0A0h
0x1800278a2  pop     r15
0x1800278a4  pop     r14
0x1800278a6  pop     rdi
0x1800278a7  pop     rsi
0x1800278a8  pop     rbx
0x1800278a9  retn
```
