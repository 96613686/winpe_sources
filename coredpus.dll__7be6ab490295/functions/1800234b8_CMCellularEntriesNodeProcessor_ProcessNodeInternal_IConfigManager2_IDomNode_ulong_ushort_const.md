# CMCellularEntriesNodeProcessor::ProcessNodeInternal(IConfigManager2 *,IDomNode *,ulong,ushort const *)

- ea: `0x1800234b8`
- end: `0x1800237f1`
- name: `?ProcessNodeInternal@CMCellularEntriesNodeProcessor@@AEAAJPEAUIConfigManager2@@PEAUIDomNode@@KPEBG@Z`
- size: `825`
- prototype: `__int64 __fastcall(CMCellularEntriesNodeProcessor *__hidden this, struct IConfigManager2 *, struct IDomNode *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022ee0`
- `0x1800234b8`

## callees

- `0x1800012b0`
- `0x180001488`
- `0x1800110bc`
- `0x1800118a0`
- `0x180013b80`
- `0x180014330`
- `0x18001d87c`
- `0x180022874`
- `0x1800229fc`
- `0x1800234b8`
- `0x180023b0c`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180023689`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237bf`
- `OLEAUT32!__imp_SysFreeString` at `0x180023689`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800237bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMCellularEntriesNodeProcessor::ProcessNodeInternal(
        CMCellularEntriesNodeProcessor *this,
        struct IConfigManager2 *a2,
        struct IDomNode *a3,
        int a4,
        const unsigned __int16 *a5)
{
  const unsigned __int16 *v9; // rsi
  unsigned int v10; // edi
  __int64 v11; // r8
  int v12; // ecx
  int v13; // ebx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  const unsigned __int16 *v19; // rax
  struct IDomNode *v21; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v22; // [rsp+48h] [rbp-90h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-80h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-78h] BYREF
  wchar_t *v26; // [rsp+68h] [rbp-70h] BYREF
  const unsigned __int16 *v27; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int16 *v28[4]; // [rsp+78h] [rbp-60h] BYREF

  v9 = a5;
  v27 = a5;
  v10 = 0;
  String2 = 0;
  bstrString = 0;
  v22 = 0;
  v21 = 0;
  std::wstring::wstring(v28);
  try
  {
    v13 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v11 + 40LL))(v11, &String2);
    if ( v13 < 0 )
    {
      std::wstring::_Tidy_deallocate(v28);
      goto LABEL_29;
    }
    if ( (unsigned int)dword_18003E080 > 5 )
    {
      v23 = a5;
      v26 = String2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&word_1800374F6,
        v14,
        v15,
        (__int64)&v26,
        (__int64)&v23);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, struct IConfigManager2 *, const unsigned __int16 *, struct IDomNode *))(**((_QWORD **)this + 2) + 72LL))(
            *((_QWORD *)this + 2),
            a2,
            a5,
            a3);
    if ( v13 < 0 )
      goto LABEL_7;
    if ( !wcscmp_0(L"characteristic-query", String2) )
    {
      v13 = 0;
      std::wstring::_Tidy_deallocate(v28);
    }
    else
    {
      if ( a4 == 1 )
      {
        v13 = CMCellularEntriesNodeProcessor::PreProcessCmCellularEntries(this, a3);
        if ( v13 < 0 )
        {
LABEL_7:
          std::wstring::_Tidy_deallocate(v28);
          goto LABEL_29;
        }
      }
      v13 = (*(__int64 (__fastcall **)(struct IDomNode *, unsigned int *))(*(_QWORD *)a3 + 200LL))(a3, &v22);
      if ( v13 >= 0 )
      {
        while ( v10 < v22 )
        {
          ATL::CComPtrBase<IDomNode>::Release(&v21);
          v13 = (*(__int64 (__fastcall **)(struct IDomNode *, _QWORD, struct IDomNode **))(*(_QWORD *)a3 + 192LL))(
                  a3,
                  v10,
                  &v21);
          if ( v13 < 0 )
            break;
          if ( !v21 )
          {
            v13 = -2147024882;
            std::wstring::_Tidy_deallocate(v28);
            goto LABEL_29;
          }
          SysFreeString(bstrString);
          bstrString = 0;
          v13 = (*(__int64 (__fastcall **)(struct IDomNode *, BSTR *))(*(_QWORD *)v21 + 72LL))(v21, &bstrString);
          if ( v13 < 0 )
            break;
          std::wstring::assign(v28);
          std::wstring::append(v28, L"/");
          std::wstring::append(v28, bstrString);
          v19 = (const unsigned __int16 *)v28;
          if ( v28[3] > (unsigned __int16 *)7 )
            v19 = v28[0];
          v13 = CMCellularEntriesNodeProcessor::ProcessNodeInternal(this, a2, v21, a4 + 1, v19);
          if ( v13 < 0 )
            break;
          ++v10;
        }
        std::wstring::_Tidy_deallocate(v28);
      }
      else
      {
        std::wstring::_Tidy_deallocate(v28);
      }
    }
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v23) = -2147024882;
    v13 = -2147024882;
    v9 = v27;
  }
LABEL_29:
  if ( (unsigned int)dword_18003E080 > 5 )
  {
    v27 = v9;
    v26 = String2;
    LODWORD(v23) = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v16,
      (unsigned int)word_1800375AA,
      v17,
      v18,
      (__int64)&v23,
      (__int64)&v26,
      (__int64)&v27);
  }
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v21);
  SysFreeString(bstrString);
  SysFreeString(String2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800234b8  push    rbx
0x1800234ba  push    rsi
0x1800234bb  push    rdi
0x1800234bc  push    r12
0x1800234be  push    r13
0x1800234c0  push    r14
0x1800234c2  push    r15
0x1800234c4  sub     rsp, 0A0h
0x1800234cb  mov     rax, cs:__security_cookie
0x1800234d2  xor     rax, rsp
0x1800234d5  mov     [rsp+0D8h+var_40], rax
0x1800234dd  mov     r15d, r9d
0x1800234e0  mov     r14, r8
0x1800234e3  mov     r12, rdx
0x1800234e6  mov     r13, rcx
0x1800234e9  mov     rsi, [rsp+0D8h+arg_20]
0x1800234f1  mov     [rsp+0D8h+var_68], rsi
0x1800234f6  xor     edi, edi
0x1800234f8  mov     [rsp+0D8h+String2], rdi
0x1800234fd  mov     [rsp+0D8h+bstrString], rdi
0x180023502  mov     [rsp+0D8h+var_90], edi
0x180023506  mov     [rsp+0D8h+var_98], rdi
0x18002350b  lea     rcx, [rsp+0D8h+var_60]
0x180023510  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023515  nop
0x180023516  mov     rax, [r8]
0x180023519  lea     rdx, [rsp+0D8h+String2]
0x18002351e  mov     rcx, r8
0x180023521  mov     rax, [rax+28h]
0x180023525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002352a  mov     ebx, eax
0x18002352c  test    eax, eax
0x18002352e  jns     short loc_180023540
0x180023530  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023535  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002353a  nop
0x18002353b  jmp     loc_180023754
0x180023540  mov     eax, cs:dword_18003E080
0x180023546  cmp     eax, 5
0x180023549  jbe     short loc_18002357A
0x18002354b  mov     [rsp+0D8h+var_88], rsi
0x180023550  mov     rax, [rsp+0D8h+String2]
0x180023555  mov     [rsp+0D8h+var_70], rax
0x18002355a  lea     rax, [rsp+0D8h+var_88]
0x18002355f  mov     [rsp+0D8h+var_B0], rax
0x180023564  lea     rax, [rsp+0D8h+var_70]
0x180023569  mov     [rsp+0D8h+var_B8], rax
0x18002356e  lea     rdx, word_1800374F6
0x180023575  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002357a  mov     rcx, [r13+10h]
0x18002357e  mov     rax, [rcx]
0x180023581  mov     r9, r14
0x180023584  mov     r8, rsi
0x180023587  mov     rdx, r12
0x18002358a  mov     rax, [rax+48h]
0x18002358e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023593  mov     ebx, eax
0x180023595  test    eax, eax
0x180023597  jns     short loc_1800235A9
0x180023599  lea     rcx, [rsp+0D8h+var_60]; void *
0x18002359e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235a3  nop
0x1800235a4  jmp     loc_180023754
0x1800235a9  mov     rdx, [rsp+0D8h+String2]; String2
0x1800235ae  lea     rcx, aCharacteristic; "characteristic-query"
0x1800235b5  call    wcscmp_0
0x1800235ba  test    eax, eax
0x1800235bc  jnz     short loc_1800235D0
0x1800235be  mov     ebx, edi
0x1800235c0  lea     rcx, [rsp+0D8h+var_60]; void *
0x1800235c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235ca  nop
0x1800235cb  jmp     loc_180023754
0x1800235d0  cmp     r15d, 1
0x1800235d4  jnz     short loc_1800235F7
0x1800235d6  mov     rdx, r14; struct IDomNode *
0x1800235d9  mov     rcx, r13; this
0x1800235dc  call    ?PreProcessCmCellularEntries@CMCellularEntriesNodeProcessor@@AEAAJPEAUIDomNode@@@Z; CMCellularEntriesNodeProcessor::PreProcessCmCellularEntries(IDomNode *)
0x1800235e1  mov     ebx, eax
0x1800235e3  test    eax, eax
0x1800235e5  jns     short loc_1800235F7
0x1800235e7  lea     rcx, [rsp+0D8h+var_60]; void *
0x1800235ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235f1  nop
0x1800235f2  jmp     loc_180023754
0x1800235f7  mov     rax, [r14]
0x1800235fa  lea     rdx, [rsp+0D8h+var_90]
0x1800235ff  mov     rcx, r14
0x180023602  mov     rax, [rax+0C8h]
0x180023609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002360e  mov     ebx, eax
0x180023610  test    eax, eax
0x180023612  jns     short loc_180023624
0x180023614  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023619  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002361e  nop
0x18002361f  jmp     loc_180023754
0x180023624  cmp     edi, [rsp+0D8h+var_90]
0x180023628  jnb     loc_18002373E
0x18002362e  lea     rcx, [rsp+0D8h+var_98]
0x180023633  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x180023638  mov     rax, [r14]
0x18002363b  lea     r8, [rsp+0D8h+var_98]
0x180023640  mov     edx, edi
0x180023642  mov     rcx, r14
0x180023645  mov     rax, [rax+0C0h]
0x18002364c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023651  mov     ebx, eax
0x180023653  test    eax, eax
0x180023655  jns     short loc_180023667
0x180023657  lea     rcx, [rsp+0D8h+var_60]; void *
0x18002365c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023661  nop
0x180023662  jmp     loc_180023754
0x180023667  cmp     [rsp+0D8h+var_98], 0
0x18002366d  jnz     short loc_180023684
0x18002366f  mov     ebx, 8007000Eh
0x180023674  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023679  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002367e  nop
0x18002367f  jmp     loc_180023754
0x180023684  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180023689  call    cs:__imp_SysFreeString
0x180023690  nop     dword ptr [rax+rax+00h]
0x180023695  mov     [rsp+0D8h+bstrString], 0
0x18002369e  mov     rcx, [rsp+0D8h+var_98]
0x1800236a3  mov     rax, [rcx]
0x1800236a6  lea     rdx, [rsp+0D8h+bstrString]
0x1800236ab  mov     rax, [rax+48h]
0x1800236af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236b4  mov     ebx, eax
0x1800236b6  test    eax, eax
0x1800236b8  jns     short loc_1800236CA
0x1800236ba  lea     rcx, [rsp+0D8h+var_60]; void *
0x1800236bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800236c4  nop
0x1800236c5  jmp     loc_180023754
0x1800236ca  mov     rdx, rsi
0x1800236cd  lea     rcx, [rsp+0D8h+var_60]
0x1800236d2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800236d7  lea     rdx, asc_180032DA8; "/"
0x1800236de  lea     rcx, [rsp+0D8h+var_60]
0x1800236e3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800236e8  mov     rdx, [rsp+0D8h+bstrString]
0x1800236ed  lea     rcx, [rsp+0D8h+var_60]
0x1800236f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800236f7  lea     rax, [rsp+0D8h+var_60]
0x1800236fc  cmp     [rsp+0D8h+var_48], 7
0x180023705  cmova   rax, [rsp+0D8h+var_60]
0x18002370b  mov     [rsp+0D8h+var_B8], rax; unsigned __int16 *
0x180023710  lea     r9d, [r15+1]; unsigned int
0x180023714  mov     r8, [rsp+0D8h+var_98]; struct IDomNode *
0x180023719  mov     rdx, r12; struct IConfigManager2 *
0x18002371c  mov     rcx, r13; this
0x18002371f  call    ?ProcessNodeInternal@CMCellularEntriesNodeProcessor@@AEAAJPEAUIConfigManager2@@PEAUIDomNode@@KPEBG@Z; CMCellularEntriesNodeProcessor::ProcessNodeInternal(IConfigManager2 *,IDomNode *,ulong,ushort const *)
0x180023724  mov     ebx, eax
0x180023726  test    eax, eax
0x180023728  jns     short loc_180023737
0x18002372a  lea     rcx, [rsp+0D8h+var_60]; void *
0x18002372f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023734  nop
0x180023735  jmp     short loc_180023754
0x180023737  inc     edi
0x180023739  jmp     loc_180023624
0x18002373e  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023743  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023748  nop
0x180023749  jmp     short loc_180023754
0x18002374b  mov     ebx, dword ptr [rsp+0D8h+var_88]
0x18002374f  mov     rsi, [rsp+0D8h+var_68]
0x180023754  mov     eax, cs:dword_18003E080
0x18002375a  cmp     eax, 5
0x18002375d  jbe     short loc_18002379D
0x18002375f  mov     [rsp+0D8h+var_68], rsi
0x180023764  mov     rax, [rsp+0D8h+String2]
0x180023769  mov     [rsp+0D8h+var_70], rax
0x18002376e  mov     dword ptr [rsp+0D8h+var_88], ebx
0x180023772  lea     rax, [rsp+0D8h+var_68]
0x180023777  mov     [rsp+0D8h+var_A8], rax
0x18002377c  lea     rax, [rsp+0D8h+var_70]
0x180023781  mov     [rsp+0D8h+var_B0], rax
0x180023786  lea     rax, [rsp+0D8h+var_88]
0x18002378b  mov     [rsp+0D8h+var_B8], rax
0x180023790  lea     rdx, word_1800375AA
0x180023797  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002379c  nop
0x18002379d  lea     rcx, [rsp+0D8h+var_98]
0x1800237a2  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800237a7  nop
0x1800237a8  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x1800237ad  call    cs:__imp_SysFreeString
0x1800237b4  nop     dword ptr [rax+rax+00h]
0x1800237b9  nop
0x1800237ba  mov     rcx, [rsp+0D8h+String2]; bstrString
0x1800237bf  call    cs:__imp_SysFreeString
0x1800237c6  nop     dword ptr [rax+rax+00h]
0x1800237cb  mov     eax, ebx
0x1800237cd  mov     rcx, [rsp+0D8h+var_40]
0x1800237d5  xor     rcx, rsp; StackCookie
0x1800237d8  call    __security_check_cookie
0x1800237dd  add     rsp, 0A0h
0x1800237e4  pop     r15
0x1800237e6  pop     r14
0x1800237e8  pop     r13
0x1800237ea  pop     r12
0x1800237ec  pop     rdi
0x1800237ed  pop     rsi
0x1800237ee  pop     rbx
0x1800237ef  retn
```
