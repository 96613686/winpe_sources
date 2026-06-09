# LPA::EsimManager::AddRetryWhenInternetNotAvailable(ushort const (*)[33])

- ea: `0x180087c60`
- end: `0x180087e72`
- name: `?AddRetryWhenInternetNotAvailable@EsimManager@LPA@@AEAAXPEAY0CB@$$CBG@Z`
- size: `530`
- prototype: `void __fastcall(LPA::EsimManager *__hidden this, const unsigned __int16 (*)[33])`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18008f990`

## callees

- `0x180001010`
- `0x1800035a4`
- `0x1800037f4`
- `0x18000df90`
- `0x18000e46c`
- `0x18006361c`
- `0x180063668`
- `0x180071650`
- `0x180080f88`
- `0x180085430`
- `0x180087c60`
- `0x180096544`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180087d33`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180087d33`

## string_xrefs

- `0x180087ce5`: `LpaServiceEsimManager`
- `0x180087db3`: `LpaServiceEsimManager`
- `0x180087e1f`: `LpaServiceEsimManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LPA::EsimManager::AddRetryWhenInternetNotAvailable(
        LPA::EsimManager *this,
        const unsigned __int16 (*a2)[33],
        int a3,
        int a4)
{
  _QWORD **v6; // rdi
  _QWORD *i; // rbx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rdi
  _QWORD *v12; // rbx
  _QWORD *v13; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ebx
  const char *v18; // [rsp+40h] [rbp-19h] BYREF
  const char *v19; // [rsp+48h] [rbp-11h] BYREF
  _QWORD *v20; // [rsp+50h] [rbp-9h]
  const unsigned __int16 *v21; // [rsp+58h] [rbp-1h] BYREF
  const char *v22; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp+Fh] BYREF

  if ( a2 )
  {
    std::wstring::wstring(v23, (const unsigned __int16 *)a2);
    v6 = (_QWORD **)*((_QWORD *)this + 28);
    for ( i = *v6; i != v6; i = (_QWORD *)*i )
    {
      if ( !(unsigned int)std::wstring::compare(v23, i + 2) )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v21 = (const unsigned __int16 *)a2;
          v22 = "LPA::EsimManager::AddRetryWhenInternetNotAvailable";
          v18 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v8,
            (unsigned int)&unk_18012D3C0,
            v9,
            v10,
            (__int64)&v18,
            (__int64)&v22,
            (__int64)&v21);
        }
LABEL_13:
        std::wstring::_Tidy_deallocate(v23);
        return;
      }
    }
    if ( *((_QWORD *)this + 29) == 0x555555555555555LL )
      std::_Xlength_error("list too long");
    v11 = *((_QWORD *)this + 28);
    v19 = (char *)this + 224;
    v12 = operator new(0x30u);
    v20 = v12;
    std::wstring::wstring(v12 + 2, v23);
    ++*((_QWORD *)this + 29);
    v13 = *(_QWORD **)(v11 + 8);
    *v12 = v11;
    v12[1] = v13;
    v20 = 0;
    *(_QWORD *)(v11 + 8) = v12;
    *v13 = v12;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(&v19);
    v17 = *((_DWORD *)this + 58);
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v21) = *((_DWORD *)this + 58);
      v18 = (const char *)a2;
      v22 = "LPA::EsimManager::AddRetryWhenInternetNotAvailable";
      v19 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&dword_18012D344,
        v15,
        v16,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)&v18,
        (__int64)&v21);
    }
    if ( v17 > 1 )
      goto LABEL_13;
    std::wstring::_Tidy_deallocate(v23);
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v19 = "LPA::EsimManager::AddRetryWhenInternetNotAvailable";
    v18 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)&dword_18012D2F4,
      a3,
      a4,
      (__int64)&v18,
      (__int64)&v19);
  }
  LPA::EsimManager::UpdateServiceTriggerEvent(this, 1u);
}

```

## disassembly

```asm
0x180087c60  mov     [rsp-8+arg_10], rbx
0x180087c65  push    rbp
0x180087c66  push    rsi
0x180087c67  push    rdi
0x180087c68  push    r14
0x180087c6a  push    r15
0x180087c6c  lea     rbp, [rsp-37h]
0x180087c71  sub     rsp, 90h
0x180087c78  mov     rax, cs:__security_cookie
0x180087c7f  xor     rax, rsp
0x180087c82  mov     [rbp+57h+var_28], rax
0x180087c86  mov     rsi, rdx
0x180087c89  mov     r15, rcx
0x180087c8c  test    rdx, rdx
0x180087c8f  jz      loc_180087E09
0x180087c95  lea     rcx, [rbp+57h+var_48]
0x180087c99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180087c9e  nop
0x180087c9f  lea     r14, [r15+0E0h]
0x180087ca6  mov     rdi, [r14]
0x180087ca9  mov     rbx, [rdi]
0x180087cac  cmp     rbx, rdi
0x180087caf  jz      short loc_180087D1C
0x180087cb1  lea     rdx, [rbx+10h]
0x180087cb5  lea     rcx, [rbp+57h+var_48]
0x180087cb9  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180087cbe  test    eax, eax
0x180087cc0  jz      short loc_180087CC7
0x180087cc2  mov     rbx, [rbx]
0x180087cc5  jmp     short loc_180087CAC
0x180087cc7  mov     eax, cs:CallbackContext
0x180087ccd  cmp     eax, 4
0x180087cd0  jbe     loc_180087DF3
0x180087cd6  mov     [rbp+57h+var_58], rsi
0x180087cda  lea     rax, aLpaEsimmanager_12; "LPA::EsimManager::AddRetryWhenInternetN"...
0x180087ce1  mov     [rbp+57h+var_50], rax
0x180087ce5  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x180087cec  mov     [rbp+57h+var_70], rax
0x180087cf0  lea     rax, [rbp+57h+var_58]
0x180087cf4  mov     [rsp+0B0h+var_80], rax
0x180087cf9  lea     rax, [rbp+57h+var_50]
0x180087cfd  mov     [rsp+0B0h+var_88], rax
0x180087d02  lea     rax, [rbp+57h+var_70]
0x180087d06  mov     [rsp+0B0h+var_90], rax
0x180087d0b  lea     rdx, unk_18012D3C0
0x180087d12  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180087d17  jmp     loc_180087DF3
0x180087d1c  mov     rax, 555555555555555h
0x180087d26  cmp     [r14+8], rax
0x180087d2a  jnz     short loc_180087D3A
0x180087d2c  lea     rcx, aListTooLong; "list too long"
0x180087d33  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180087d3a  mov     rdi, [r14]
0x180087d3d  mov     [rbp+57h+var_68], r14
0x180087d41  mov     [rbp+57h+var_60], 0
0x180087d49  mov     ecx, 30h ; '0'; Size
0x180087d4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087d53  mov     rbx, rax
0x180087d56  mov     [rbp+57h+var_60], rax
0x180087d5a  lea     rcx, [rax+10h]
0x180087d5e  lea     rdx, [rbp+57h+var_48]
0x180087d62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087d67  nop
0x180087d68  inc     qword ptr [r14+8]
0x180087d6c  mov     rcx, [rdi+8]
0x180087d70  mov     [rbx], rdi
0x180087d73  mov     [rbx+8], rcx
0x180087d77  mov     [rbp+57h+var_60], 0
0x180087d7f  mov     [rdi+8], rbx
0x180087d83  mov     [rcx], rbx
0x180087d86  lea     rcx, [rbp+57h+var_68]
0x180087d8a  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
0x180087d8f  mov     ebx, [r15+0E8h]
0x180087d96  mov     eax, cs:CallbackContext
0x180087d9c  cmp     eax, 4
0x180087d9f  jbe     short loc_180087DEE
0x180087da1  mov     dword ptr [rbp+57h+var_58], ebx
0x180087da4  mov     [rbp+57h+var_70], rsi
0x180087da8  lea     rax, aLpaEsimmanager_12; "LPA::EsimManager::AddRetryWhenInternetN"...
0x180087daf  mov     [rbp+57h+var_50], rax
0x180087db3  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x180087dba  mov     [rbp+57h+var_68], rax
0x180087dbe  lea     rax, [rbp+57h+var_58]
0x180087dc2  mov     [rsp+0B0h+var_78], rax
0x180087dc7  lea     rax, [rbp+57h+var_70]
0x180087dcb  mov     [rsp+0B0h+var_80], rax
0x180087dd0  lea     rax, [rbp+57h+var_50]
0x180087dd4  mov     [rsp+0B0h+var_88], rax
0x180087dd9  lea     rax, [rbp+57h+var_68]
0x180087ddd  mov     [rsp+0B0h+var_90], rax
0x180087de2  lea     rdx, dword_18012D344
0x180087de9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180087dee  cmp     ebx, 1
0x180087df1  jbe     short loc_180087DFE
0x180087df3  lea     rcx, [rbp+57h+var_48]
0x180087df7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087dfc  jmp     short loc_180087E4F
0x180087dfe  lea     rcx, [rbp+57h+var_48]
0x180087e02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087e07  jmp     short loc_180087E48
0x180087e09  mov     eax, cs:CallbackContext
0x180087e0f  cmp     eax, 4
0x180087e12  jbe     short loc_180087E48
0x180087e14  lea     rax, aLpaEsimmanager_12; "LPA::EsimManager::AddRetryWhenInternetN"...
0x180087e1b  mov     [rbp+57h+var_68], rax
0x180087e1f  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x180087e26  mov     [rbp+57h+var_70], rax
0x180087e2a  lea     rax, [rbp+57h+var_68]
0x180087e2e  mov     [rsp+0B0h+var_88], rax
0x180087e33  lea     rax, [rbp+57h+var_70]
0x180087e37  mov     [rsp+0B0h+var_90], rax
0x180087e3c  lea     rdx, dword_18012D2F4
0x180087e43  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180087e48  mov     dl, 1; bool
0x180087e4a  call    ?UpdateServiceTriggerEvent@EsimManager@LPA@@AEAAX_N@Z; LPA::EsimManager::UpdateServiceTriggerEvent(bool)
0x180087e4f  mov     rcx, [rbp+57h+var_28]
0x180087e53  xor     rcx, rsp; StackCookie
0x180087e56  call    __security_check_cookie
0x180087e5b  mov     rbx, [rsp+0B0h+arg_10]
0x180087e63  add     rsp, 90h
0x180087e6a  pop     r15
0x180087e6c  pop     r14
0x180087e6e  pop     rdi
0x180087e6f  pop     rsi
0x180087e70  pop     rbp
0x180087e71  retn
```
