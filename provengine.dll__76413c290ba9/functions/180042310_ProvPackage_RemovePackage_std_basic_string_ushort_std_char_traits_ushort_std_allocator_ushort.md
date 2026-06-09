# ProvPackage::RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180042310`
- end: `0x1800424ef`
- name: `?RemovePackage@ProvPackage@@UEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x18000109c`
- `0x1800011ac`
- `0x1800018ec`
- `0x1800071a4`
- `0x18000b140`
- `0x180021cd8`
- `0x180021cf4`
- `0x180042310`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004241b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004241b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042470`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800423e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800423e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvPackage::RemovePackage(_QWORD *a1, __int64 a2, __int64 a3, int a4)
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
  int v15; // r9d
  unsigned int v16; // eax
  int v17; // [rsp+20h] [rbp-38h]
  int v18[2]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v20; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v20 = a2;
  if ( (unsigned int)dword_18005A000 > 5 )
  {
    v6 = a1 + 1;
    if ( a1[4] >= 8u )
      v6 = (_QWORD *)*v6;
    *(_QWORD *)v18 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18005A000,
      (unsigned int)byte_180050791,
      0,
      a4,
      (__int64)v18);
  }
  if ( !a1[13] && !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*a1 + 72LL))(a1) )
  {
    v16 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v16,
      v17);
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
    if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
    {
      v18[0] = GetLastError();
      v13 = std::wstring::c_str(a1 + 1);
      v14 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v19, v13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)&word_180050726,
        0,
        v15,
        v14,
        (__int64)v18);
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
0x180042310  mov     [rsp+arg_10], rbx
0x180042315  mov     [rsp+arg_18], rsi
0x18004231a  push    rdi
0x18004231b  sub     rsp, 50h
0x18004231f  mov     rax, cs:__security_cookie
0x180042326  xor     rax, rsp
0x180042329  mov     [rsp+58h+var_10], rax
0x18004232e  mov     rdi, rdx
0x180042331  mov     rbx, rcx
0x180042334  mov     [rsp+58h+var_18], rdx
0x180042339  mov     eax, cs:dword_18005A000
0x18004233f  cmp     eax, 5
0x180042342  jbe     short loc_180042377
0x180042344  lea     rax, [rcx+8]
0x180042348  cmp     qword ptr [rax+18h], 8
0x18004234d  jb      short loc_180042352
0x18004234f  mov     rax, [rax]
0x180042352  mov     qword ptr [rsp+58h+var_28], rax
0x180042357  lea     rax, [rsp+58h+var_28]
0x18004235c  mov     qword ptr [rsp+58h+var_38], rax; int
0x180042361  xor     r8d, r8d
0x180042364  lea     rdx, byte_180050791
0x18004236b  lea     rcx, dword_18005A000
0x180042372  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180042377  cmp     qword ptr [rbx+68h], 0
0x18004237c  jnz     short loc_180042395
0x18004237e  mov     rax, [rbx]
0x180042381  mov     rcx, rbx
0x180042384  mov     rax, [rax+48h]
0x180042388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004238d  test    al, al
0x18004238f  jz      loc_1800424CB
0x180042395  mov     rcx, [rbx+68h]
0x180042399  test    rcx, rcx
0x18004239c  jz      short loc_1800423B5
0x18004239e  mov     rax, [rcx]
0x1800423a1  mov     rax, [rax+80h]
0x1800423a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423ad  mov     qword ptr [rbx+68h], 0
0x1800423b5  mov     rcx, [rbx+70h]
0x1800423b9  test    rcx, rcx
0x1800423bc  jz      short loc_1800423D6
0x1800423be  mov     rax, [rcx]
0x1800423c1  mov     edx, 1
0x1800423c6  mov     rax, [rax]
0x1800423c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423ce  mov     qword ptr [rbx+70h], 0
0x1800423d6  lea     rsi, [rbx+8]
0x1800423da  cmp     qword ptr [rsi+18h], 8
0x1800423df  jb      short loc_1800423E6
0x1800423e1  mov     rcx, [rsi]
0x1800423e4  jmp     short loc_1800423E9
0x1800423e6  mov     rcx, rsi; lpFileName
0x1800423e9  call    cs:__imp_DeleteFileW
0x1800423ef  test    eax, eax
0x1800423f1  jz      short loc_180042453
0x1800423f3  cmp     qword ptr [rbx+60h], 8
0x1800423f8  jb      short loc_180042400
0x1800423fa  mov     rcx, [rbx+48h]
0x1800423fe  jmp     short loc_180042404
0x180042400  lea     rcx, [rbx+48h]
0x180042404  mov     qword ptr [rbx+58h], 0
0x18004240c  xor     eax, eax
0x18004240e  mov     [rcx], ax
0x180042411  cmp     qword ptr [rdi+18h], 8
0x180042416  jb      short loc_180042421
0x180042418  mov     rcx, [rdi]
0x18004241b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180042421  mov     qword ptr [rdi+18h], 7
0x180042429  mov     qword ptr [rdi+10h], 0
0x180042431  xor     eax, eax
0x180042433  mov     [rdi], ax
0x180042436  mov     rcx, [rsp+58h+var_10]
0x18004243b  xor     rcx, rsp; StackCookie
0x18004243e  call    __security_check_cookie
0x180042443  mov     rbx, [rsp+58h+arg_10]
0x180042448  mov     rsi, [rsp+58h+arg_18]
0x18004244d  add     rsp, 50h
0x180042451  pop     rdi
0x180042452  retn
0x180042453  mov     eax, cs:dword_18005A000
0x180042459  cmp     eax, 2
0x18004245c  jbe     short loc_1800424B4
0x18004245e  xor     edx, edx
0x180042460  lea     rcx, dword_18005A000
0x180042467  call    _tlgKeywordOn
0x18004246c  test    al, al
0x18004246e  jz      short loc_1800424B4
0x180042470  call    cs:__imp_GetLastError
0x180042476  mov     [rsp+58h+var_28], eax
0x18004247a  mov     rcx, rsi
0x18004247d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180042482  mov     rdx, rax
0x180042485  lea     rcx, [rsp+58h+var_20]
0x18004248a  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18004248f  lea     rdx, [rsp+58h+var_28]
0x180042494  mov     [rsp+58h+var_30], rdx
0x180042499  mov     qword ptr [rsp+58h+var_38], rax
0x18004249e  xor     r8d, r8d
0x1800424a1  lea     rdx, word_180050726
0x1800424a8  lea     rcx, dword_18005A000
0x1800424af  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800424b4  mov     rcx, [rsp+58h]; this
0x1800424b9  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800424c0  mov     edx, 0E5h; void *
0x1800424c5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800424cb  mov     ecx, 8000FFFFh
0x1800424d0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800424d5  mov     r9d, eax; char *
0x1800424d8  mov     rcx, [rsp+58h]; this
0x1800424dd  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800424e4  mov     edx, 0D6h; void *
0x1800424e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
