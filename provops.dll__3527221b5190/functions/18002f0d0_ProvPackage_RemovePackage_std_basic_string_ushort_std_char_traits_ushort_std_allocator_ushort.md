# ProvPackage::RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18002f0d0`
- end: `0x18002f2a6`
- name: `?RemovePackage@ProvPackage@@UEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x1800015b4`
- `0x18000164c`
- `0x1800017ec`
- `0x180001878`
- `0x180004d68`
- `0x18001b388`
- `0x180020710`
- `0x180021200`
- `0x18002f0d0`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002f1d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f22b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f22b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002f1a5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002f1a5`

## pseudocode

```c
__int64 __fastcall ProvPackage::RemovePackage(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v6; // rax
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  const WCHAR **v9; // rsi
  const WCHAR *v10; // rcx
  const char *v11; // r9
  _WORD *v12; // rcx
  __int64 result; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // r9
  unsigned int v18; // eax
  int v19; // [rsp+20h] [rbp-38h]
  int v20[2]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v22; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v22 = a2;
  if ( *(_DWORD *)g_hProvTraceProvider > 5u )
  {
    v6 = a1 + 1;
    if ( a1[4] >= 8u )
      v6 = (_QWORD *)*v6;
    *(_QWORD *)v20 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      g_hProvTraceProvider,
      (__int64)&dword_180041B3C,
      0,
      a4,
      v20);
  }
  if ( !a1[13] && !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*a1 + 72LL))(a1) )
  {
    v18 = wil::verify_hresult<long>(0x8000FFFF);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v18,
      v19);
  }
  v7 = a1[13];
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 128LL))(v7);
    a1[13] = 0;
  }
  v8 = (void (__fastcall ***)(_QWORD, __int64))a1[14];
  if ( v8 )
  {
    (**v8)(v8, 1);
    a1[14] = 0;
  }
  v9 = (const WCHAR **)(a1 + 1);
  if ( a1[4] < 8u )
    v10 = (const WCHAR *)(a1 + 1);
  else
    v10 = *v9;
  if ( !DeleteFileW(v10) )
  {
    v14 = g_hProvTraceProvider;
    if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
    {
      v20[0] = GetLastError();
      v15 = std::wstring::c_str(v9);
      v16 = (_QWORD *)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v21, v15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)&byte_180041AFF,
        0,
        v17,
        v16);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      v11);
  }
  if ( a1[12] < 8u )
    v12 = a1 + 9;
  else
    v12 = (_WORD *)a1[9];
  a1[11] = 0;
  *v12 = 0;
  if ( *(_QWORD *)(a2 + 24) >= 8u )
    operator delete(*(void **)a2);
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  result = 0;
  *(_WORD *)a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18002f0d0  mov     [rsp+arg_10], rbx
0x18002f0d5  mov     [rsp+arg_18], rsi
0x18002f0da  push    rdi
0x18002f0db  sub     rsp, 50h
0x18002f0df  mov     rax, cs:__security_cookie
0x18002f0e6  xor     rax, rsp
0x18002f0e9  mov     [rsp+58h+var_10], rax
0x18002f0ee  mov     rdi, rdx
0x18002f0f1  mov     rbx, rcx
0x18002f0f4  mov     [rsp+58h+var_18], rdx
0x18002f0f9  mov     rcx, cs:g_hProvTraceProvider
0x18002f100  mov     eax, [rcx]
0x18002f102  cmp     eax, 5
0x18002f105  jbe     short loc_18002F133
0x18002f107  lea     rax, [rbx+8]
0x18002f10b  cmp     qword ptr [rax+18h], 8
0x18002f110  jb      short loc_18002F115
0x18002f112  mov     rax, [rax]
0x18002f115  mov     qword ptr [rsp+58h+var_28], rax
0x18002f11a  lea     rax, [rsp+58h+var_28]
0x18002f11f  mov     qword ptr [rsp+58h+var_38], rax; int
0x18002f124  xor     r8d, r8d
0x18002f127  lea     rdx, dword_180041B3C
0x18002f12e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002f133  cmp     qword ptr [rbx+68h], 0
0x18002f138  jnz     short loc_18002F151
0x18002f13a  mov     rax, [rbx]
0x18002f13d  mov     rcx, rbx
0x18002f140  mov     rax, [rax+48h]
0x18002f144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f149  test    al, al
0x18002f14b  jz      loc_18002F282
0x18002f151  mov     rcx, [rbx+68h]
0x18002f155  test    rcx, rcx
0x18002f158  jz      short loc_18002F171
0x18002f15a  mov     rax, [rcx]
0x18002f15d  mov     rax, [rax+80h]
0x18002f164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f169  mov     qword ptr [rbx+68h], 0
0x18002f171  mov     rcx, [rbx+70h]
0x18002f175  test    rcx, rcx
0x18002f178  jz      short loc_18002F192
0x18002f17a  mov     rax, [rcx]
0x18002f17d  mov     edx, 1
0x18002f182  mov     rax, [rax]
0x18002f185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f18a  mov     qword ptr [rbx+70h], 0
0x18002f192  lea     rsi, [rbx+8]
0x18002f196  cmp     qword ptr [rsi+18h], 8
0x18002f19b  jb      short loc_18002F1A2
0x18002f19d  mov     rcx, [rsi]
0x18002f1a0  jmp     short loc_18002F1A5
0x18002f1a2  mov     rcx, rsi; lpFileName
0x18002f1a5  call    cs:__imp_DeleteFileW
0x18002f1ab  test    eax, eax
0x18002f1ad  jz      short loc_18002F20F
0x18002f1af  cmp     qword ptr [rbx+60h], 8
0x18002f1b4  jb      short loc_18002F1BC
0x18002f1b6  mov     rcx, [rbx+48h]
0x18002f1ba  jmp     short loc_18002F1C0
0x18002f1bc  lea     rcx, [rbx+48h]
0x18002f1c0  mov     qword ptr [rbx+58h], 0
0x18002f1c8  xor     eax, eax
0x18002f1ca  mov     [rcx], ax
0x18002f1cd  cmp     qword ptr [rdi+18h], 8
0x18002f1d2  jb      short loc_18002F1DD
0x18002f1d4  mov     rcx, [rdi]
0x18002f1d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002f1dd  mov     qword ptr [rdi+18h], 7
0x18002f1e5  mov     qword ptr [rdi+10h], 0
0x18002f1ed  xor     eax, eax
0x18002f1ef  mov     [rdi], ax
0x18002f1f2  mov     rcx, [rsp+58h+var_10]
0x18002f1f7  xor     rcx, rsp; StackCookie
0x18002f1fa  call    __security_check_cookie
0x18002f1ff  mov     rbx, [rsp+58h+arg_10]
0x18002f204  mov     rsi, [rsp+58h+arg_18]
0x18002f209  add     rsp, 50h
0x18002f20d  pop     rdi
0x18002f20e  retn
0x18002f20f  mov     rbx, cs:g_hProvTraceProvider
0x18002f216  mov     eax, [rbx]
0x18002f218  cmp     eax, 2
0x18002f21b  jbe     short loc_18002F26B
0x18002f21d  xor     edx, edx
0x18002f21f  mov     rcx, rbx
0x18002f222  call    _tlgKeywordOn
0x18002f227  test    al, al
0x18002f229  jz      short loc_18002F26B
0x18002f22b  call    cs:__imp_GetLastError
0x18002f231  mov     [rsp+58h+var_28], eax
0x18002f235  mov     rcx, rsi
0x18002f238  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002f23d  mov     rdx, rax
0x18002f240  lea     rcx, [rsp+58h+var_20]
0x18002f245  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18002f24a  lea     rcx, [rsp+58h+var_28]
0x18002f24f  mov     [rsp+58h+var_30], rcx
0x18002f254  mov     qword ptr [rsp+58h+var_38], rax
0x18002f259  xor     r8d, r8d
0x18002f25c  lea     rdx, byte_180041AFF
0x18002f263  mov     rcx, rbx
0x18002f266  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002f26b  mov     rcx, [rsp+58h]; this
0x18002f270  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002f277  mov     edx, 0E5h; void *
0x18002f27c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002f282  mov     ecx, 8000FFFFh
0x18002f287  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f28c  mov     r9d, eax; char *
0x18002f28f  mov     rcx, [rsp+58h]; this
0x18002f294  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002f29b  mov     edx, 0D6h; void *
0x18002f2a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
