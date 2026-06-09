# CSimpleWAPNodeProcessor::ProcessNodeInternal(IConfigManager2 *,IDomNode *,ushort const *)

- ea: `0x1800237f8`
- end: `0x180023b05`
- name: `?ProcessNodeInternal@CSimpleWAPNodeProcessor@@AEAAJPEAUIConfigManager2@@PEAUIDomNode@@PEBG@Z`
- size: `781`
- prototype: `__int64 __fastcall(CSimpleWAPNodeProcessor *__hidden this, struct IConfigManager2 *, struct IDomNode *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800233b0`
- `0x1800237f8`

## callees

- `0x1800012b0`
- `0x180001488`
- `0x1800110bc`
- `0x1800118a0`
- `0x180013b80`
- `0x180014330`
- `0x18001d87c`
- `0x180022874`
- `0x1800237f8`
- `0x180023b0c`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800239a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800239a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ad5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSimpleWAPNodeProcessor::ProcessNodeInternal(
        CSimpleWAPNodeProcessor *this,
        struct IConfigManager2 *a2,
        struct IDomNode *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // rsi
  __int64 v8; // r8
  int v9; // ecx
  int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int i; // edi
  const unsigned __int16 *v17; // r9
  struct IDomNode *v19; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-90h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-80h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-78h] BYREF
  wchar_t *v24; // [rsp+68h] [rbp-70h] BYREF
  const unsigned __int16 *v25; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int16 *v26[4]; // [rsp+78h] [rbp-60h] BYREF

  v4 = a4;
  v25 = a4;
  String2 = 0;
  bstrString = 0;
  v20 = 0;
  v19 = 0;
  std::wstring::wstring(v26);
  try
  {
    v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v8 + 40LL))(v8, &String2);
    if ( v10 >= 0 )
    {
      if ( (unsigned int)dword_18003E080 > 5 )
      {
        v21 = v4;
        v24 = String2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v9,
          (unsigned int)byte_180037631,
          v11,
          v12,
          (__int64)&v24,
          (__int64)&v21);
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, struct IConfigManager2 *, const unsigned __int16 *, struct IDomNode *))(**((_QWORD **)this + 2) + 72LL))(
              *((_QWORD *)this + 2),
              a2,
              v4,
              a3);
      if ( v10 >= 0 )
      {
        if ( !wcscmp_0(L"characteristic-query", String2) )
        {
          v10 = 0;
          std::wstring::_Tidy_deallocate(v26);
        }
        else
        {
          v10 = (*(__int64 (__fastcall **)(struct IDomNode *, unsigned int *))(*(_QWORD *)a3 + 200LL))(a3, &v20);
          if ( v10 >= 0 )
          {
            for ( i = 0; i < v20; ++i )
            {
              ATL::CComPtrBase<IDomNode>::Release(&v19);
              v10 = (*(__int64 (__fastcall **)(struct IDomNode *, _QWORD, struct IDomNode **))(*(_QWORD *)a3 + 192LL))(
                      a3,
                      i,
                      &v19);
              if ( v10 < 0 )
                break;
              if ( !v19 )
              {
                v10 = -2147024882;
                std::wstring::_Tidy_deallocate(v26);
                goto LABEL_28;
              }
              SysFreeString(bstrString);
              bstrString = 0;
              v10 = (*(__int64 (__fastcall **)(struct IDomNode *, BSTR *))(*(_QWORD *)v19 + 72LL))(v19, &bstrString);
              if ( v10 < 0 )
                break;
              std::wstring::assign(v26);
              std::wstring::append(v26, L"/");
              std::wstring::append(v26, bstrString);
              v17 = (const unsigned __int16 *)v26;
              if ( v26[3] > (unsigned __int16 *)7 )
                v17 = v26[0];
              v10 = CSimpleWAPNodeProcessor::ProcessNodeInternal(this, a2, v19, v17);
              if ( v10 < 0 )
                break;
            }
            std::wstring::_Tidy_deallocate(v26);
          }
          else
          {
            std::wstring::_Tidy_deallocate(v26);
          }
        }
      }
      else
      {
        std::wstring::_Tidy_deallocate(v26);
      }
    }
    else
    {
      std::wstring::_Tidy_deallocate(v26);
    }
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v21) = -2147024882;
    v10 = -2147024882;
    v4 = v25;
  }
LABEL_28:
  if ( (unsigned int)dword_18003E080 > 5 )
  {
    v25 = v4;
    v24 = String2;
    LODWORD(v21) = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v13,
      (unsigned int)byte_1800376DD,
      v14,
      v15,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v25);
  }
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v19);
  SysFreeString(bstrString);
  SysFreeString(String2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800237f8  push    rbx
0x1800237fa  push    rsi
0x1800237fb  push    rdi
0x1800237fc  push    r12
0x1800237fe  push    r14
0x180023800  push    r15
0x180023802  sub     rsp, 0A8h
0x180023809  mov     rax, cs:__security_cookie
0x180023810  xor     rax, rsp
0x180023813  mov     [rsp+0D8h+var_40], rax
0x18002381b  mov     rsi, r9
0x18002381e  mov     r14, r8
0x180023821  mov     r12, rdx
0x180023824  mov     r15, rcx
0x180023827  mov     [rsp+0D8h+var_68], r9
0x18002382c  mov     [rsp+0D8h+String2], 0
0x180023835  mov     [rsp+0D8h+bstrString], 0
0x18002383e  mov     [rsp+0D8h+var_90], 0
0x180023846  mov     [rsp+0D8h+var_98], 0
0x18002384f  lea     rcx, [rsp+0D8h+var_60]
0x180023854  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023859  nop
0x18002385a  mov     rax, [r8]
0x18002385d  lea     rdx, [rsp+0D8h+String2]
0x180023862  mov     rcx, r8
0x180023865  mov     rax, [rax+28h]
0x180023869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002386e  mov     ebx, eax
0x180023870  test    eax, eax
0x180023872  jns     short loc_180023884
0x180023874  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023879  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002387e  nop
0x18002387f  jmp     loc_180023A6A
0x180023884  mov     eax, cs:dword_18003E080
0x18002388a  cmp     eax, 5
0x18002388d  jbe     short loc_1800238BE
0x18002388f  mov     [rsp+0D8h+var_88], rsi
0x180023894  mov     rax, [rsp+0D8h+String2]
0x180023899  mov     [rsp+0D8h+var_70], rax
0x18002389e  lea     rax, [rsp+0D8h+var_88]
0x1800238a3  mov     [rsp+0D8h+var_B0], rax
0x1800238a8  lea     rax, [rsp+0D8h+var_70]
0x1800238ad  mov     [rsp+0D8h+var_B8], rax
0x1800238b2  lea     rdx, byte_180037631
0x1800238b9  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800238be  mov     rcx, [r15+10h]
0x1800238c2  mov     rax, [rcx]
0x1800238c5  mov     r9, r14
0x1800238c8  mov     r8, rsi
0x1800238cb  mov     rdx, r12
0x1800238ce  mov     rax, [rax+48h]
0x1800238d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238d7  mov     ebx, eax
0x1800238d9  test    eax, eax
0x1800238db  jns     short loc_1800238ED
0x1800238dd  lea     rcx, [rsp+0D8h+var_60]; void *
0x1800238e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800238e7  nop
0x1800238e8  jmp     loc_180023A6A
0x1800238ed  mov     rdx, [rsp+0D8h+String2]; String2
0x1800238f2  lea     rcx, aCharacteristic; "characteristic-query"
0x1800238f9  call    wcscmp_0
0x1800238fe  test    eax, eax
0x180023900  jnz     short loc_180023914
0x180023902  xor     ebx, ebx
0x180023904  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023909  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002390e  nop
0x18002390f  jmp     loc_180023A6A
0x180023914  mov     rax, [r14]
0x180023917  lea     rdx, [rsp+0D8h+var_90]
0x18002391c  mov     rcx, r14
0x18002391f  mov     rax, [rax+0C8h]
0x180023926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002392b  mov     ebx, eax
0x18002392d  test    eax, eax
0x18002392f  jns     short loc_180023941
0x180023931  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023936  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002393b  nop
0x18002393c  jmp     loc_180023A6A
0x180023941  xor     edi, edi
0x180023943  cmp     edi, [rsp+0D8h+var_90]
0x180023947  jnb     loc_180023A54
0x18002394d  lea     rcx, [rsp+0D8h+var_98]
0x180023952  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x180023957  mov     rax, [r14]
0x18002395a  lea     r8, [rsp+0D8h+var_98]
0x18002395f  mov     edx, edi
0x180023961  mov     rcx, r14
0x180023964  mov     rax, [rax+0C0h]
0x18002396b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023970  mov     ebx, eax
0x180023972  test    eax, eax
0x180023974  jns     short loc_180023986
0x180023976  lea     rcx, [rsp+0D8h+var_60]; void *
0x18002397b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023980  nop
0x180023981  jmp     loc_180023A6A
0x180023986  cmp     [rsp+0D8h+var_98], 0
0x18002398c  jnz     short loc_1800239A3
0x18002398e  mov     ebx, 8007000Eh
0x180023993  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023998  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002399d  nop
0x18002399e  jmp     loc_180023A6A
0x1800239a3  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x1800239a8  call    cs:__imp_SysFreeString
0x1800239af  nop     dword ptr [rax+rax+00h]
0x1800239b4  mov     [rsp+0D8h+bstrString], 0
0x1800239bd  mov     rcx, [rsp+0D8h+var_98]
0x1800239c2  mov     rax, [rcx]
0x1800239c5  lea     rdx, [rsp+0D8h+bstrString]
0x1800239ca  mov     rax, [rax+48h]
0x1800239ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239d3  mov     ebx, eax
0x1800239d5  test    eax, eax
0x1800239d7  jns     short loc_1800239E9
0x1800239d9  lea     rcx, [rsp+0D8h+var_60]; void *
0x1800239de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800239e3  nop
0x1800239e4  jmp     loc_180023A6A
0x1800239e9  mov     rdx, rsi
0x1800239ec  lea     rcx, [rsp+0D8h+var_60]
0x1800239f1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800239f6  lea     rdx, asc_180032DA8; "/"
0x1800239fd  lea     rcx, [rsp+0D8h+var_60]
0x180023a02  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023a07  mov     rdx, [rsp+0D8h+bstrString]
0x180023a0c  lea     rcx, [rsp+0D8h+var_60]
0x180023a11  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180023a16  lea     r9, [rsp+0D8h+var_60]
0x180023a1b  cmp     [rsp+0D8h+var_48], 7
0x180023a24  cmova   r9, [rsp+0D8h+var_60]; unsigned __int16 *
0x180023a2a  mov     r8, [rsp+0D8h+var_98]; struct IDomNode *
0x180023a2f  mov     rdx, r12; struct IConfigManager2 *
0x180023a32  mov     rcx, r15; this
0x180023a35  call    ?ProcessNodeInternal@CSimpleWAPNodeProcessor@@AEAAJPEAUIConfigManager2@@PEAUIDomNode@@PEBG@Z; CSimpleWAPNodeProcessor::ProcessNodeInternal(IConfigManager2 *,IDomNode *,ushort const *)
0x180023a3a  mov     ebx, eax
0x180023a3c  test    eax, eax
0x180023a3e  jns     short loc_180023A4D
0x180023a40  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023a45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023a4a  nop
0x180023a4b  jmp     short loc_180023A6A
0x180023a4d  inc     edi
0x180023a4f  jmp     loc_180023943
0x180023a54  lea     rcx, [rsp+0D8h+var_60]; void *
0x180023a59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023a5e  nop
0x180023a5f  jmp     short loc_180023A6A
0x180023a61  mov     ebx, dword ptr [rsp+0D8h+var_88]
0x180023a65  mov     rsi, [rsp+0D8h+var_68]
0x180023a6a  mov     eax, cs:dword_18003E080
0x180023a70  cmp     eax, 5
0x180023a73  jbe     short loc_180023AB3
0x180023a75  mov     [rsp+0D8h+var_68], rsi
0x180023a7a  mov     rax, [rsp+0D8h+String2]
0x180023a7f  mov     [rsp+0D8h+var_70], rax
0x180023a84  mov     dword ptr [rsp+0D8h+var_88], ebx
0x180023a88  lea     rax, [rsp+0D8h+var_68]
0x180023a8d  mov     [rsp+0D8h+var_A8], rax
0x180023a92  lea     rax, [rsp+0D8h+var_70]
0x180023a97  mov     [rsp+0D8h+var_B0], rax
0x180023a9c  lea     rax, [rsp+0D8h+var_88]
0x180023aa1  mov     [rsp+0D8h+var_B8], rax
0x180023aa6  lea     rdx, byte_1800376DD
0x180023aad  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180023ab2  nop
0x180023ab3  lea     rcx, [rsp+0D8h+var_98]
0x180023ab8  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180023abd  nop
0x180023abe  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180023ac3  call    cs:__imp_SysFreeString
0x180023aca  nop     dword ptr [rax+rax+00h]
0x180023acf  nop
0x180023ad0  mov     rcx, [rsp+0D8h+String2]; bstrString
0x180023ad5  call    cs:__imp_SysFreeString
0x180023adc  nop     dword ptr [rax+rax+00h]
0x180023ae1  mov     eax, ebx
0x180023ae3  mov     rcx, [rsp+0D8h+var_40]
0x180023aeb  xor     rcx, rsp; StackCookie
0x180023aee  call    __security_check_cookie
0x180023af3  add     rsp, 0A8h
0x180023afa  pop     r15
0x180023afc  pop     r14
0x180023afe  pop     r12
0x180023b00  pop     rdi
0x180023b01  pop     rsi
0x180023b02  pop     rbx
0x180023b03  retn
```
