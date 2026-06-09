# ProvPackage::RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x14000cd30`
- end: `0x14000cefb`
- name: `?RemovePackage@ProvPackage@@UEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `459`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x140001008`
- `0x1400010f4`
- `0x140001104`
- `0x140001424`
- `0x1400032e8`
- `0x140008b88`
- `0x140008f60`
- `0x14000a3b8`
- `0x14000cd30`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000ce31`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ce31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ce86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ce86`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000cdff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000cdff`

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
  if ( (unsigned int)dword_140017048 > 5 )
  {
    v6 = a1 + 1;
    if ( a1[4] >= 8u )
      v6 = (_QWORD *)*v6;
    *(_QWORD *)v19 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)a1,
      (unsigned int)byte_140013769,
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
    if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
    {
      v19[0] = GetLastError();
      v13 = std::wstring::c_str(a1 + 1);
      v14 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v20, v13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)v19,
        (unsigned int)&dword_14001372C,
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
0x14000cd30  mov     [rsp+arg_10], rbx
0x14000cd35  mov     [rsp+arg_18], rsi
0x14000cd3a  push    rdi
0x14000cd3b  sub     rsp, 50h
0x14000cd3f  mov     rax, cs:__security_cookie
0x14000cd46  xor     rax, rsp
0x14000cd49  mov     [rsp+58h+var_10], rax
0x14000cd4e  mov     rdi, rdx
0x14000cd51  mov     rbx, rcx
0x14000cd54  mov     [rsp+58h+var_18], rdx
0x14000cd59  mov     eax, cs:dword_140017048
0x14000cd5f  cmp     eax, 5
0x14000cd62  jbe     short loc_14000CD8D
0x14000cd64  lea     rax, [rcx+8]
0x14000cd68  cmp     qword ptr [rax+18h], 8
0x14000cd6d  jb      short loc_14000CD72
0x14000cd6f  mov     rax, [rax]
0x14000cd72  mov     qword ptr [rsp+58h+var_28], rax
0x14000cd77  lea     rax, [rsp+58h+var_28]
0x14000cd7c  mov     qword ptr [rsp+58h+var_38], rax; int
0x14000cd81  lea     rdx, byte_140013769
0x14000cd88  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000cd8d  cmp     qword ptr [rbx+68h], 0
0x14000cd92  jnz     short loc_14000CDAB
0x14000cd94  mov     rax, [rbx]
0x14000cd97  mov     rcx, rbx
0x14000cd9a  mov     rax, [rax+48h]
0x14000cd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cda3  test    al, al
0x14000cda5  jz      loc_14000CED7
0x14000cdab  mov     rcx, [rbx+68h]
0x14000cdaf  test    rcx, rcx
0x14000cdb2  jz      short loc_14000CDCB
0x14000cdb4  mov     rax, [rcx]
0x14000cdb7  mov     rax, [rax+80h]
0x14000cdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cdc3  mov     qword ptr [rbx+68h], 0
0x14000cdcb  mov     rcx, [rbx+70h]
0x14000cdcf  test    rcx, rcx
0x14000cdd2  jz      short loc_14000CDEC
0x14000cdd4  mov     rax, [rcx]
0x14000cdd7  mov     edx, 1
0x14000cddc  mov     rax, [rax]
0x14000cddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cde4  mov     qword ptr [rbx+70h], 0
0x14000cdec  lea     rsi, [rbx+8]
0x14000cdf0  cmp     qword ptr [rsi+18h], 8
0x14000cdf5  jb      short loc_14000CDFC
0x14000cdf7  mov     rcx, [rsi]
0x14000cdfa  jmp     short loc_14000CDFF
0x14000cdfc  mov     rcx, rsi; lpFileName
0x14000cdff  call    cs:__imp_DeleteFileW
0x14000ce05  test    eax, eax
0x14000ce07  jz      short loc_14000CE69
0x14000ce09  cmp     qword ptr [rbx+60h], 8
0x14000ce0e  jb      short loc_14000CE16
0x14000ce10  mov     rcx, [rbx+48h]
0x14000ce14  jmp     short loc_14000CE1A
0x14000ce16  lea     rcx, [rbx+48h]
0x14000ce1a  mov     qword ptr [rbx+58h], 0
0x14000ce22  xor     eax, eax
0x14000ce24  mov     [rcx], ax
0x14000ce27  cmp     qword ptr [rdi+18h], 8
0x14000ce2c  jb      short loc_14000CE37
0x14000ce2e  mov     rcx, [rdi]
0x14000ce31  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ce37  mov     qword ptr [rdi+18h], 7
0x14000ce3f  mov     qword ptr [rdi+10h], 0
0x14000ce47  xor     eax, eax
0x14000ce49  mov     [rdi], ax
0x14000ce4c  mov     rcx, [rsp+58h+var_10]
0x14000ce51  xor     rcx, rsp; StackCookie
0x14000ce54  call    __security_check_cookie
0x14000ce59  mov     rbx, [rsp+58h+arg_10]
0x14000ce5e  mov     rsi, [rsp+58h+arg_18]
0x14000ce63  add     rsp, 50h
0x14000ce67  pop     rdi
0x14000ce68  retn
0x14000ce69  mov     eax, cs:dword_140017048
0x14000ce6f  cmp     eax, 2
0x14000ce72  jbe     short loc_14000CEC0
0x14000ce74  xor     edx, edx
0x14000ce76  lea     rcx, dword_140017048
0x14000ce7d  call    _tlgKeywordOn
0x14000ce82  test    al, al
0x14000ce84  jz      short loc_14000CEC0
0x14000ce86  call    cs:__imp_GetLastError
0x14000ce8c  mov     [rsp+58h+var_28], eax
0x14000ce90  mov     rcx, rsi
0x14000ce93  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14000ce98  mov     rdx, rax
0x14000ce9b  lea     rcx, [rsp+58h+var_20]
0x14000cea0  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x14000cea5  lea     rcx, [rsp+58h+var_28]
0x14000ceaa  mov     [rsp+58h+var_30], rcx
0x14000ceaf  mov     qword ptr [rsp+58h+var_38], rax
0x14000ceb4  lea     rdx, dword_14001372C
0x14000cebb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14000cec0  mov     rcx, [rsp+58h]; this
0x14000cec5  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x14000cecc  mov     edx, 0E5h; void *
0x14000ced1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000ced7  mov     ecx, 8000FFFFh
0x14000cedc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x14000cee1  mov     r9d, eax; char *
0x14000cee4  mov     rcx, [rsp+58h]; this
0x14000cee9  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x14000cef0  mov     edx, 0D6h; void *
0x14000cef5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
