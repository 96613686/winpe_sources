# AddFileExtension(ushort * *)

- ea: `0x140025c54`
- end: `0x140025e4d`
- name: `?AddFileExtension@@YAJPEAPEAG@Z`
- size: `505`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140014574`
- `0x1400146cc`

## callees

- `0x1400020f4`
- `0x1400044f8`
- `0x14000a0e4`
- `0x140025c54`
- `0x140034ce4`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140025d51`
- `KERNEL32!CompareStringW` at `0x140025d51`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140025e08`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140025e08`
- `OLEAUT32!__imp_SysAllocString` at `0x140025cc8`
- `OLEAUT32!__imp_SysAllocString` at `0x140025cc8`
- `OLEAUT32!__imp_SysFreeString` at `0x140025dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x140025e18`
- `OLEAUT32!__imp_SysFreeString` at `0x140025dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x140025e18`
- `OLEAUT32!__imp_SysStringLen` at `0x140025cf4`
- `OLEAUT32!__imp_SysStringLen` at `0x140025d11`
- `OLEAUT32!__imp_SysStringLen` at `0x140025cf4`
- `OLEAUT32!__imp_SysStringLen` at `0x140025d11`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140025dd7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140025dd7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140025de8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140025de8`

## string_xrefs

- `0x140025cb0`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140025d9f`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140025c9e`: `AddFileExtension`
- `0x140025d8d`: `AddFileExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddFileExtension(unsigned __int16 **a1)
{
  const OLECHAR *v2; // rcx
  OLECHAR *v3; // rbx
  _OWORD *v4; // rax
  CEventLogger *v5; // rcx
  WCHAR *v6; // rsi
  unsigned int v7; // edi
  UINT v8; // eax
  __int64 v9; // r9
  int v10; // eax
  CEventLogger *v11; // rcx
  UINT v12; // eax
  unsigned __int16 *v13; // rax
  BSTR bstr; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    v3 = SysAllocString(v2);
    bstr = v3;
    if ( !v3 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v3 = 0;
    bstr = 0;
  }
  v4 = operator new[](0x1Cu, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (WCHAR *)v4;
  if ( v4 )
  {
    *v4 = 0;
    *(_OWORD *)((char *)v4 + 12) = 0;
    if ( SysStringLen(v3) <= 0xD )
      goto LABEL_11;
    v7 = 0;
    v8 = SysStringLen(v3);
    v9 = 0;
    do
    {
      v6[v9] = v3[v8 - 13 + (_DWORD)v9];
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (int)v9 < 13 );
    if ( CompareStringW(0x7Fu, 1u, v6, -1, L".msrcincident", -1) != 2 )
    {
LABEL_11:
      v10 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstr, L".msrcincident");
      if ( v10 < 0 )
        ATL::AtlThrowImpl(v10);
      v3 = bstr;
      if ( bstr )
      {
        if ( *a1 )
        {
          SysFreeString(*a1);
          *a1 = 0;
        }
        v12 = SysStringByteLen(v3);
        v13 = SysAllocStringByteLen((LPCSTR)v3, v12);
        *a1 = v13;
        v7 = v13 == 0 ? 0x8007000E : 0;
      }
      else
      {
        CEventLogger::LogError(
          v11,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x85Au,
          L"AddFileExtension",
          0x8007000E);
        v7 = -2147024882;
      }
    }
    operator delete[](v6);
  }
  else
  {
    v7 = -2147024882;
    CEventLogger::LogError(
      v5,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x82Eu,
      L"AddFileExtension",
      0x8007000E);
  }
  SysFreeString(v3);
  return v7;
}

```

## disassembly

```asm
0x140025c54  mov     [rsp+arg_8], rbx
0x140025c59  mov     [rsp+arg_10], rbp
0x140025c5e  push    rsi
0x140025c5f  push    rdi
0x140025c60  push    r14
0x140025c62  sub     rsp, 30h
0x140025c66  mov     r14, rcx
0x140025c69  mov     rcx, [rcx]; psz
0x140025c6c  test    rcx, rcx
0x140025c6f  jnz     short loc_140025CC8
0x140025c71  xor     ebx, ebx
0x140025c73  mov     [rsp+48h+bstr], rbx
0x140025c78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140025c7f  mov     ecx, 1Ch; unsigned __int64
0x140025c84  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140025c89  mov     rsi, rax
0x140025c8c  test    rax, rax
0x140025c8f  jnz     short loc_140025CE7
0x140025c91  mov     edi, 8007000Eh
0x140025c96  mov     [rsp+48h+cchCount2], 8007000Eh; unsigned int
0x140025c9e  lea     rax, aAddfileextensi; "AddFileExtension"
0x140025ca5  mov     [rsp+48h+lpString2], rax; unsigned __int16 *
0x140025caa  mov     r9d, 82Eh; unsigned int
0x140025cb0  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140025cb7  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140025cbe  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140025cc3  jmp     loc_140025E15
0x140025cc8  call    cs:__imp_SysAllocString
0x140025ccf  nop     dword ptr [rax+rax+00h]
0x140025cd4  mov     rbx, rax
0x140025cd7  mov     [rsp+48h+bstr], rax
0x140025cdc  test    rax, rax
0x140025cdf  jz      loc_140025E42
0x140025ce5  jmp     short loc_140025C78
0x140025ce7  xorps   xmm0, xmm0
0x140025cea  movups  xmmword ptr [rsi], xmm0
0x140025ced  movups  xmmword ptr [rsi+0Ch], xmm0
0x140025cf1  mov     rcx, rbx; pbstr
0x140025cf4  call    cs:__imp_SysStringLen
0x140025cfb  nop     dword ptr [rax+rax+00h]
0x140025d00  lea     rbp, aMsrcincident_1; ".msrcincident"
0x140025d07  cmp     eax, 0Dh
0x140025d0a  jbe     short loc_140025D66
0x140025d0c  xor     edi, edi
0x140025d0e  mov     rcx, rbx; pbstr
0x140025d11  call    cs:__imp_SysStringLen
0x140025d18  nop     dword ptr [rax+rax+00h]
0x140025d1d  xor     r9d, r9d
0x140025d20  lea     edx, [rdi+1]; dwCmpFlags
0x140025d23  lea     ecx, [r9-0Dh]
0x140025d27  add     ecx, eax
0x140025d29  movzx   ecx, word ptr [rbx+rcx*2]
0x140025d2d  mov     [rsi+r9*2], cx
0x140025d32  add     r9d, edx
0x140025d35  cmp     r9d, 0Dh
0x140025d39  jl      short loc_140025D23
0x140025d3b  or      r9d, 0FFFFFFFFh; cchCount1
0x140025d3f  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x140025d44  mov     [rsp+48h+lpString2], rbp; lpString2
0x140025d49  mov     r8, rsi; lpString1
0x140025d4c  mov     ecx, 7Fh; Locale
0x140025d51  call    cs:__imp_CompareStringW
0x140025d58  nop     dword ptr [rax+rax+00h]
0x140025d5d  cmp     eax, 2
0x140025d60  jz      loc_140025E05
0x140025d66  mov     rdx, rbp; unsigned __int16 *
0x140025d69  lea     rcx, [rsp+48h+bstr]; this
0x140025d6e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140025d73  test    eax, eax
0x140025d75  js      loc_140025E3A
0x140025d7b  mov     rbx, [rsp+48h+bstr]
0x140025d80  test    rbx, rbx
0x140025d83  jnz     short loc_140025DB9
0x140025d85  mov     [rsp+48h+cchCount2], 8007000Eh; unsigned int
0x140025d8d  lea     rax, aAddfileextensi; "AddFileExtension"
0x140025d94  mov     [rsp+48h+lpString2], rax; unsigned __int16 *
0x140025d99  mov     r9d, 85Ah; unsigned int
0x140025d9f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140025da6  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140025dad  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140025db2  mov     edi, 8007000Eh
0x140025db7  jmp     short loc_140025E05
0x140025db9  mov     rcx, [r14]; bstrString
0x140025dbc  test    rcx, rcx
0x140025dbf  jz      short loc_140025DD4
0x140025dc1  call    cs:__imp_SysFreeString
0x140025dc8  nop     dword ptr [rax+rax+00h]
0x140025dcd  mov     qword ptr [r14], 0
0x140025dd4  mov     rcx, rbx; bstr
0x140025dd7  call    cs:__imp_SysStringByteLen
0x140025dde  nop     dword ptr [rax+rax+00h]
0x140025de3  mov     edx, eax; len
0x140025de5  mov     rcx, rbx; psz
0x140025de8  call    cs:__imp_SysAllocStringByteLen
0x140025def  nop     dword ptr [rax+rax+00h]
0x140025df4  mov     [r14], rax
0x140025df7  neg     rax
0x140025dfa  sbb     ecx, ecx
0x140025dfc  not     ecx
0x140025dfe  mov     edi, 8007000Eh
0x140025e03  and     edi, ecx
0x140025e05  mov     rcx, rsi
0x140025e08  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140025e0f  nop     dword ptr [rax+rax+00h]
0x140025e14  nop
0x140025e15  mov     rcx, rbx; bstrString
0x140025e18  call    cs:__imp_SysFreeString
0x140025e1f  nop     dword ptr [rax+rax+00h]
0x140025e24  mov     eax, edi
0x140025e26  mov     rbx, [rsp+48h+arg_8]
0x140025e2b  mov     rbp, [rsp+48h+arg_10]
0x140025e30  add     rsp, 30h
0x140025e34  pop     r14
0x140025e36  pop     rdi
0x140025e37  pop     rsi
0x140025e38  retn
0x140025e3a  mov     ecx, eax; int
0x140025e3c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140025e42  mov     ecx, 8007000Eh; int
0x140025e47  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
