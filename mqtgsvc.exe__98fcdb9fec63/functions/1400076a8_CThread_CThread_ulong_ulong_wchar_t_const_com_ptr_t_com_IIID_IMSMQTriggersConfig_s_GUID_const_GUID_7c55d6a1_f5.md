# CThread::CThread(ulong,ulong,wchar_t const *,_com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>)

- ea: `0x1400076a8`
- end: `0x1400078cd`
- name: `??0CThread@@QEAA@KKPEB_WV?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@@Z`
- size: `549`
- prototype: `_DWORD *__fastcall(_DWORD *ArgList, __int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007ea8`
- `0x14000a6dc`

## callees

- `0x140001cc6`
- `0x1400030ac`
- `0x1400037dc`
- `0x140003868`
- `0x1400046bc`
- `0x140004eb4`
- `0x140007554`
- `0x1400076a8`
- `0x140007a18`
- `0x140007a64`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140007817`
- `KERNEL32!GetLastError` at `0x140007817`
- `KERNEL32!CreateEventW` at `0x1400077ef`
- `KERNEL32!CreateEventW` at `0x1400077ef`
- `msvcrt!_beginthreadex` at `0x140007753`
- `msvcrt!_beginthreadex` at `0x140007753`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000779f`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000784b`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000779f`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000784b`

## pseudocode

```c
_DWORD *__fastcall CThread::CThread(_DWORD *ArgList, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v7; // rcx
  uintptr_t v8; // rax
  HANDLE EventW; // rax
  _BYTE v11[8]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD pExceptionObject[5]; // [rsp+38h] [rbp-48h] BYREF
  wchar_t v13[8]; // [rsp+60h] [rbp-20h] BYREF
  int v14; // [rsp+70h] [rbp-10h]

  pExceptionObject[3] = ArgList;
  pExceptionObject[4] = a5;
  ArgList[2] = 1;
  *(_QWORD *)ArgList = &CThread::`vftable';
  v7 = ArgList + 4;
  *v7 = *a5;
  _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(v7);
  *((_QWORD *)ArgList + 5) = 0;
  *((_QWORD *)ArgList + 6) = ArgList;
  ArgList[17] = 8000;
  ArgList[16] = 4;
  ArgList[6] = 0;
  _bstr_t::operator=(ArgList + 10, a4);
  *((_QWORD *)ArgList + 10) = 0;
  v8 = _beginthreadex(0, 0, CThread::ThreadProc, ArgList, ArgList[16], ArgList + 6);
  *((_QWORD *)ArgList + 4) = v8;
  *((_BYTE *)ArgList + 72) = 1;
  if ( v8 )
  {
    *(_OWORD *)v13 = 0;
    v14 = 0;
    if ( (int)StringCchPrintfW(v13, 0xAu, L"%d", (unsigned int)ArgList[6]) < 0 )
    {
      exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    _bstr_t::_bstr_t((_bstr_t *)v11, v13);
    _bstr_t::operator+=((struct _bstr_t *)(ArgList + 10), (struct _bstr_t *)v11);
    _bstr_t::_Free((_bstr_t *)v11);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)ArgList + 10) = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  R<IObjectContext>::~R<IObjectContext>(a5);
  return ArgList;
}

```

## disassembly

```asm
0x1400076a8  mov     [rsp-28h+arg_8], rbx
0x1400076ad  push    rbp
0x1400076ae  push    rsi
0x1400076af  push    rdi
0x1400076b0  push    r14
0x1400076b2  push    r15
0x1400076b4  mov     rbp, rsp
0x1400076b7  sub     rsp, 80h
0x1400076be  mov     rax, cs:__security_cookie
0x1400076c5  xor     rax, rsp
0x1400076c8  mov     [rbp+var_8], rax
0x1400076cc  mov     rbx, r9
0x1400076cf  mov     rdi, rcx
0x1400076d2  mov     [rbp+var_30], rcx
0x1400076d6  mov     r14, [rbp+arg_20]
0x1400076da  mov     [rbp+var_28], r14
0x1400076de  mov     dword ptr [rcx+8], 1
0x1400076e5  lea     rax, ??_7CThread@@6B@; const CThread::`vftable'
0x1400076ec  mov     [rcx], rax
0x1400076ef  add     rcx, 10h
0x1400076f3  mov     rax, [r14]
0x1400076f6  mov     [rcx], rax
0x1400076f9  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x1400076fe  nop
0x1400076ff  lea     r15, [rdi+28h]
0x140007703  mov     qword ptr [r15], 0
0x14000770a  mov     [rdi+30h], rdi
0x14000770e  mov     dword ptr [rdi+44h], 1F40h
0x140007715  mov     dword ptr [rdi+40h], 4
0x14000771c  lea     rsi, [rdi+18h]
0x140007720  mov     dword ptr [rsi], 0
0x140007726  mov     rdx, rbx
0x140007729  mov     rcx, r15
0x14000772c  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x140007731  mov     qword ptr [rdi+50h], 0
0x140007739  mov     [rsp+80h+ThrdAddr], rsi; ThrdAddr
0x14000773e  mov     eax, [rdi+40h]
0x140007741  mov     [rsp+80h+InitFlag], eax; InitFlag
0x140007745  mov     r9, rdi; ArgList
0x140007748  lea     r8, ?ThreadProc@CThread@@CAIPEAX@Z; StartAddress
0x14000774f  xor     edx, edx; StackSize
0x140007751  xor     ecx, ecx; Security
0x140007753  call    cs:__imp__beginthreadex
0x140007759  mov     [rdi+20h], rax
0x14000775d  mov     byte ptr [rdi+48h], 1
0x140007761  mov     ebx, 0Ah
0x140007766  test    rax, rax
0x140007769  jz      short loc_1400077E5
0x14000776b  xorps   xmm0, xmm0
0x14000776e  xor     eax, eax
0x140007770  movups  xmmword ptr [rbp+var_20], xmm0
0x140007774  mov     [rbp+var_10], eax
0x140007777  mov     r9d, [rsi]
0x14000777a  lea     r8, aD; "%d"
0x140007781  mov     edx, ebx; unsigned __int64
0x140007783  lea     rcx, [rbp+var_20]; wchar_t *
0x140007787  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000778c  test    eax, eax
0x14000778e  jns     short loc_1400077C1
0x140007790  lea     r8d, [rbx-9]
0x140007794  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14000779b  lea     rcx, [rbp+pExceptionObject]
0x14000779f  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x1400077a5  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1400077ac  mov     [rbp+pExceptionObject], rax
0x1400077b0  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1400077b7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400077bb  call    _CxxThrowException_0
0x1400077c1  lea     rdx, [rbp+var_20]; wchar_t *
0x1400077c5  lea     rcx, [rbp+var_50]; this
0x1400077c9  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400077ce  nop
0x1400077cf  lea     rdx, [rbp+var_50]; struct _bstr_t *
0x1400077d3  mov     rcx, r15; struct _bstr_t *
0x1400077d6  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1400077db  nop
0x1400077dc  lea     rcx, [rbp+var_50]; this
0x1400077e0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1400077e5  xor     r9d, r9d; lpName
0x1400077e8  xor     r8d, r8d; bInitialState
0x1400077eb  xor     edx, edx; bManualReset
0x1400077ed  xor     ecx, ecx; lpEventAttributes
0x1400077ef  call    cs:__imp_CreateEventW
0x1400077f5  mov     [rdi+50h], rax
0x1400077f9  test    rax, rax
0x1400077fc  jnz     short loc_14000786D
0x1400077fe  lea     rax, WPP_GLOBAL_Control
0x140007805  mov     rcx, cs:WPP_GLOBAL_Control
0x14000780c  cmp     rcx, rax
0x14000780f  jz      short loc_14000783A
0x140007811  test    byte ptr [rcx+1Ch], 1
0x140007815  jz      short loc_14000783A
0x140007817  call    cs:__imp_GetLastError
0x14000781d  mov     edx, ebx
0x14000781f  mov     r9d, eax
0x140007822  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007829  mov     rcx, cs:WPP_GLOBAL_Control
0x140007830  mov     rcx, [rcx+10h]
0x140007834  call    WPP_SF_d
0x140007839  nop
0x14000783a  mov     r8d, 1
0x140007840  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x140007847  lea     rcx, [rbp+pExceptionObject]
0x14000784b  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x140007851  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140007858  mov     [rbp+pExceptionObject], rax
0x14000785c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140007863  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140007867  call    _CxxThrowException_0
0x14000786d  lea     rax, WPP_GLOBAL_Control
0x140007874  mov     rcx, cs:WPP_GLOBAL_Control
0x14000787b  cmp     rcx, rax
0x14000787e  jz      short loc_14000789F
0x140007880  test    byte ptr [rcx+1Ch], 4
0x140007884  jz      short loc_14000789F
0x140007886  mov     edx, 0Bh
0x14000788b  mov     r9d, [rsi]
0x14000788e  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007895  mov     rcx, [rcx+10h]
0x140007899  call    WPP_SF_d
0x14000789e  nop
0x14000789f  mov     rcx, r14
0x1400078a2  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x1400078a7  mov     rax, rdi
0x1400078aa  mov     rcx, [rbp+var_8]
0x1400078ae  xor     rcx, rsp; StackCookie
0x1400078b1  call    __security_check_cookie
0x1400078b6  mov     rbx, [rsp+80h+arg_8]
0x1400078be  add     rsp, 80h
0x1400078c5  pop     r15
0x1400078c7  pop     r14
0x1400078c9  pop     rdi
0x1400078ca  pop     rsi
0x1400078cb  pop     rbp
0x1400078cc  retn
```
