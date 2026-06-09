# ProvPackage::RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180034440`
- end: `0x18003461e`
- name: `?RemovePackage@ProvPackage@@UEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001a30`
- `0x180001a40`
- `0x180001b14`
- `0x180001cf0`
- `0x1800046ac`
- `0x1800090e0`
- `0x18000929c`
- `0x180024508`
- `0x180034440`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180034547`
- `msvcrt!??3@YAXPEAX@Z` at `0x180034547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345a3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003450f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003450f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvPackage::RemovePackage(_QWORD *a1, __int64 a2, int a3, int a4)
{
  _QWORD *v6; // rax
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  const WCHAR *v9; // rcx
  const char *v10; // r9
  _WORD *v11; // rcx
  __int64 result; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // [rsp+20h] [rbp-38h]
  int v19[2]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v21; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v21 = a2;
  if ( (unsigned int)dword_1800495B0 > 5 )
  {
    v6 = a1 + 1;
    if ( a1[4] >= 8u )
      v6 = (_QWORD *)*v6;
    *(_QWORD *)v19 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)a1,
      (unsigned int)word_180041B12,
      a3,
      a4,
      (__int64)v19);
  }
  if ( !a1[13] && !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*a1 + 72LL))(a1) )
  {
    v17 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v17,
      v18);
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
  if ( a1[4] < 8u )
    v9 = (const WCHAR *)(a1 + 1);
  else
    v9 = (const WCHAR *)a1[1];
  if ( !DeleteFileW(v9) )
  {
    if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
    {
      v19[0] = GetLastError();
      v13 = std::wstring::c_str(a1 + 1);
      v14 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v20, v13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)v19,
        (unsigned int)byte_180041B39,
        v15,
        v16,
        v14,
        (__int64)v19);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      v10);
  }
  if ( a1[12] < 8u )
    v11 = a1 + 9;
  else
    v11 = (_WORD *)a1[9];
  a1[11] = 0;
  *v11 = 0;
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
0x180034440  mov     [rsp+arg_10], rbx
0x180034445  mov     [rsp+arg_18], rsi
0x18003444a  push    rdi
0x18003444b  sub     rsp, 50h
0x18003444f  mov     rax, cs:__security_cookie
0x180034456  xor     rax, rsp
0x180034459  mov     [rsp+58h+var_10], rax
0x18003445e  mov     rdi, rdx
0x180034461  mov     rbx, rcx
0x180034464  mov     [rsp+58h+var_18], rdx
0x180034469  mov     eax, cs:dword_1800495B0
0x18003446f  cmp     eax, 5
0x180034472  jbe     short loc_18003449D
0x180034474  lea     rax, [rcx+8]
0x180034478  cmp     qword ptr [rax+18h], 8
0x18003447d  jb      short loc_180034482
0x18003447f  mov     rax, [rax]
0x180034482  mov     qword ptr [rsp+58h+var_28], rax
0x180034487  lea     rax, [rsp+58h+var_28]
0x18003448c  mov     qword ptr [rsp+58h+var_38], rax; int
0x180034491  lea     rdx, word_180041B12
0x180034498  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003449d  cmp     qword ptr [rbx+68h], 0
0x1800344a2  jnz     short loc_1800344BB
0x1800344a4  mov     rax, [rbx]
0x1800344a7  mov     rcx, rbx
0x1800344aa  mov     rax, [rax+48h]
0x1800344ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344b3  test    al, al
0x1800344b5  jz      loc_1800345FA
0x1800344bb  mov     rcx, [rbx+68h]
0x1800344bf  test    rcx, rcx
0x1800344c2  jz      short loc_1800344DB
0x1800344c4  mov     rax, [rcx]
0x1800344c7  mov     rax, [rax+80h]
0x1800344ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344d3  mov     qword ptr [rbx+68h], 0
0x1800344db  mov     rcx, [rbx+70h]
0x1800344df  test    rcx, rcx
0x1800344e2  jz      short loc_1800344FC
0x1800344e4  mov     rax, [rcx]
0x1800344e7  mov     edx, 1
0x1800344ec  mov     rax, [rax]
0x1800344ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344f4  mov     qword ptr [rbx+70h], 0
0x1800344fc  lea     rsi, [rbx+8]
0x180034500  cmp     qword ptr [rsi+18h], 8
0x180034505  jb      short loc_18003450C
0x180034507  mov     rcx, [rsi]
0x18003450a  jmp     short loc_18003450F
0x18003450c  mov     rcx, rsi; lpFileName
0x18003450f  call    cs:__imp_DeleteFileW
0x180034516  nop     dword ptr [rax+rax+00h]
0x18003451b  test    eax, eax
0x18003451d  jz      short loc_180034586
0x18003451f  cmp     qword ptr [rbx+60h], 8
0x180034524  jb      short loc_18003452C
0x180034526  mov     rcx, [rbx+48h]
0x18003452a  jmp     short loc_180034530
0x18003452c  lea     rcx, [rbx+48h]
0x180034530  mov     qword ptr [rbx+58h], 0
0x180034538  xor     eax, eax
0x18003453a  mov     [rcx], ax
0x18003453d  cmp     qword ptr [rdi+18h], 8
0x180034542  jb      short loc_180034553
0x180034544  mov     rcx, [rdi]
0x180034547  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003454e  nop     dword ptr [rax+rax+00h]
0x180034553  mov     qword ptr [rdi+18h], 7
0x18003455b  mov     qword ptr [rdi+10h], 0
0x180034563  xor     eax, eax
0x180034565  mov     [rdi], ax
0x180034568  mov     rcx, [rsp+58h+var_10]
0x18003456d  xor     rcx, rsp; StackCookie
0x180034570  call    __security_check_cookie
0x180034575  mov     rbx, [rsp+58h+arg_10]
0x18003457a  mov     rsi, [rsp+58h+arg_18]
0x18003457f  add     rsp, 50h
0x180034583  pop     rdi
0x180034584  retn
0x180034586  mov     eax, cs:dword_1800495B0
0x18003458c  cmp     eax, 2
0x18003458f  jbe     short loc_1800345E3
0x180034591  xor     edx, edx
0x180034593  lea     rcx, dword_1800495B0
0x18003459a  call    _tlgKeywordOn
0x18003459f  test    al, al
0x1800345a1  jz      short loc_1800345E3
0x1800345a3  call    cs:__imp_GetLastError
0x1800345aa  nop     dword ptr [rax+rax+00h]
0x1800345af  mov     [rsp+58h+var_28], eax
0x1800345b3  mov     rcx, rsi
0x1800345b6  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800345bb  mov     rdx, rax
0x1800345be  lea     rcx, [rsp+58h+var_20]
0x1800345c3  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800345c8  lea     rcx, [rsp+58h+var_28]
0x1800345cd  mov     [rsp+58h+var_30], rcx
0x1800345d2  mov     qword ptr [rsp+58h+var_38], rax
0x1800345d7  lea     rdx, byte_180041B39
0x1800345de  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800345e3  mov     rcx, [rsp+58h]; this
0x1800345e8  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800345ef  mov     edx, 0E5h; void *
0x1800345f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800345fa  mov     ecx, 8000FFFFh
0x1800345ff  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180034604  mov     r9d, eax; char *
0x180034607  mov     rcx, [rsp+58h]; this
0x18003460c  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180034613  mov     edx, 0D6h; void *
0x180034618  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
