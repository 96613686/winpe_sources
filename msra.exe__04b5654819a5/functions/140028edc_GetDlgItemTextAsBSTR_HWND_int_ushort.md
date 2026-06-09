# GetDlgItemTextAsBSTR(HWND__ *,int,ushort * *)

- ea: `0x140028edc`
- end: `0x1400290bb`
- name: `?GetDlgItemTextAsBSTR@@YAJPEAUHWND__@@HPEAPEAG@Z`
- size: `479`
- prototype: `__int64 __fastcall(HWND, int, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000aa78`
- `0x14001cd38`
- `0x14001ea24`
- `0x140022900`
- `0x140025b04`
- `0x14003175c`
- `0x140032bf0`

## callees

- `0x1400020f4`
- `0x1400044f8`
- `0x140028edc`
- `0x140034ce4`

## import_xrefs

- `USER32!GetDlgItem` at `0x140028ef9`
- `USER32!GetDlgItem` at `0x140028ef9`
- `USER32!GetWindowTextLengthW` at `0x140028f14`
- `USER32!GetWindowTextLengthW` at `0x140028f14`
- `USER32!GetWindowTextW` at `0x140028f99`
- `USER32!GetWindowTextW` at `0x140028f99`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140029034`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140029034`
- `OLEAUT32!__imp_SysAllocString` at `0x140028fc6`
- `OLEAUT32!__imp_SysAllocString` at `0x140028fc6`
- `OLEAUT32!__imp_SysFreeString` at `0x140028fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002905d`
- `OLEAUT32!__imp_SysFreeString` at `0x140028fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002905d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140029083`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140029083`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140029094`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140029094`

## string_xrefs

- `0x140028f78`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140029014`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDlgItemTextAsBSTR(HWND a1, int a2, unsigned __int16 **a3)
{
  OLECHAR *v4; // rbx
  HWND DlgItem; // rax
  CEventLogger *v6; // rcx
  HWND v7; // rdi
  int WindowTextLengthW; // eax
  int v9; // r15d
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  CEventLogger *v12; // rcx
  OLECHAR *v13; // rsi
  int v14; // edi
  unsigned int v15; // r9d
  UINT v17; // eax
  unsigned __int16 *v18; // rax
  __int64 *v19; // rdx
  __int64 v20; // [rsp+0h] [rbp-58h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-30h]
  WCHAR *v22; // [rsp+30h] [rbp-28h]
  OLECHAR *v23; // [rsp+38h] [rbp-20h]
  unsigned __int16 **v24; // [rsp+70h] [rbp+18h]
  int v25; // [rsp+78h] [rbp+20h]

  v4 = 0;
  DlgItem = GetDlgItem(a1, a2);
  v7 = DlgItem;
  if ( !DlgItem )
  {
    v13 = 0;
    v21 = 0;
    v15 = 473;
    goto LABEL_12;
  }
  WindowTextLengthW = GetWindowTextLengthW(DlgItem);
  if ( WindowTextLengthW )
  {
    v9 = WindowTextLengthW + 1;
    v10 = 2LL * (WindowTextLengthW + 1);
    if ( !is_mul_ok(v9, 2u) )
      v10 = -1;
    v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v11;
    v22 = v11;
    if ( !v11 )
    {
      v14 = -2147024882;
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x1CDu,
        L"GetDlgItemTextAsBSTR",
        0x8007000E);
      goto LABEL_21;
    }
    if ( GetWindowTextW(v7, v11, v9) )
    {
      SysFreeString(0);
      v4 = SysAllocString(v13);
      v23 = v4;
      if ( !v4 )
      {
        try
        {
          ATL::AtlThrowImpl(-2147024882);
        }
        catch ( ATL::CAtlException )
        {
          v19 = &v20;
          *((_DWORD *)v19 + 30) = -2147024882;
          a3 = v24;
          v14 = v25;
          v13 = v22;
          v4 = v23;
          goto LABEL_13;
        }
      }
      v14 = 0;
LABEL_13:
      if ( v13 )
        operator delete[](v13);
      if ( v14 < 0 )
        goto LABEL_21;
      goto LABEL_16;
    }
    v21 = 0;
    v15 = 465;
LABEL_12:
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v15,
      L"GetDlgItemTextAsBSTR",
      v21);
    v14 = -2147467259;
    goto LABEL_13;
  }
LABEL_16:
  if ( a3 )
  {
    if ( v4 )
    {
      v17 = SysStringByteLen(v4);
      v18 = SysAllocStringByteLen((LPCSTR)v4, v17);
      *a3 = v18;
      if ( !v18 )
      {
        v14 = -2147024882;
        goto LABEL_21;
      }
    }
    else
    {
      *a3 = 0;
    }
    v14 = 0;
  }
  else
  {
    v14 = -2147467261;
  }
LABEL_21:
  SysFreeString(v4);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140028edc  mov     [rsp+arg_0], rbx
0x140028ee1  mov     [rsp+arg_8], rsi
0x140028ee6  mov     [rsp+arg_10], r8
0x140028eeb  push    rdi
0x140028eec  push    r14
0x140028eee  push    r15
0x140028ef0  sub     rsp, 40h
0x140028ef4  mov     r14, r8
0x140028ef7  xor     ebx, ebx
0x140028ef9  call    cs:__imp_GetDlgItem
0x140028f00  nop     dword ptr [rax+rax+00h]
0x140028f05  mov     rdi, rax
0x140028f08  test    rax, rax
0x140028f0b  jz      loc_140028FFC
0x140028f11  mov     rcx, rax; hWnd
0x140028f14  call    cs:__imp_GetWindowTextLengthW
0x140028f1b  nop     dword ptr [rax+rax+00h]
0x140028f20  test    eax, eax
0x140028f22  jz      loc_140029044
0x140028f28  lea     r15d, [rax+1]
0x140028f2c  movsxd  rcx, r15d
0x140028f2f  lea     eax, [rbx+2]
0x140028f32  mul     rcx
0x140028f35  lea     rcx, [rbx-1]
0x140028f39  cmovb   rax, rcx
0x140028f3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140028f44  mov     rcx, rax; unsigned __int64
0x140028f47  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140028f4c  mov     rsi, rax
0x140028f4f  mov     [rsp+58h+var_28], rax
0x140028f54  test    rax, rax
0x140028f57  jnz     short loc_140028F90
0x140028f59  mov     edi, 8007000Eh
0x140028f5e  mov     [rsp+58h+var_30], 8007000Eh; unsigned int
0x140028f66  lea     rax, aGetdlgitemtext; "GetDlgItemTextAsBSTR"
0x140028f6d  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x140028f72  mov     r9d, 1CDh; unsigned int
0x140028f78  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028f7f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140028f86  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028f8b  jmp     loc_14002905A
0x140028f90  mov     r8d, r15d; nMaxCount
0x140028f93  mov     rdx, rsi; lpString
0x140028f96  mov     rcx, rdi; hWnd
0x140028f99  call    cs:__imp_GetWindowTextW
0x140028fa0  nop     dword ptr [rax+rax+00h]
0x140028fa5  test    eax, eax
0x140028fa7  jnz     short loc_140028FB5
0x140028fa9  mov     [rsp+58h+var_30], eax
0x140028fad  mov     r9d, 1D1h
0x140028fb3  jmp     short loc_140029008
0x140028fb5  xor     ecx, ecx; bstrString
0x140028fb7  call    cs:__imp_SysFreeString
0x140028fbe  nop     dword ptr [rax+rax+00h]
0x140028fc3  mov     rcx, rsi; psz
0x140028fc6  call    cs:__imp_SysAllocString
0x140028fcd  nop     dword ptr [rax+rax+00h]
0x140028fd2  mov     rbx, rax
0x140028fd5  mov     [rsp+58h+var_20], rax
0x140028fda  test    rax, rax
0x140028fdd  jz      loc_1400290AF
0x140028fe3  xor     edi, edi
0x140028fe5  jmp     short loc_14002902C
0x140028fe7  mov     r14, [rsp+58h+arg_10]
0x140028fec  mov     edi, [rsp+58h+arg_18]
0x140028ff0  mov     rsi, [rsp+58h+var_28]
0x140028ff5  mov     rbx, [rsp+58h+var_20]
0x140028ffa  jmp     short loc_14002902C
0x140028ffc  xor     esi, esi
0x140028ffe  mov     [rsp+58h+var_30], esi; unsigned int
0x140029002  mov     r9d, 1D9h; unsigned int
0x140029008  lea     rax, aGetdlgitemtext; "GetDlgItemTextAsBSTR"
0x14002900f  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x140029014  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002901b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029022  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140029027  mov     edi, 80004005h
0x14002902c  test    rsi, rsi
0x14002902f  jz      short loc_140029040
0x140029031  mov     rcx, rsi
0x140029034  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002903b  nop     dword ptr [rax+rax+00h]
0x140029040  test    edi, edi
0x140029042  js      short loc_14002905A
0x140029044  test    r14, r14
0x140029047  jnz     short loc_140029050
0x140029049  mov     edi, 80004003h
0x14002904e  jmp     short loc_14002905A
0x140029050  test    rbx, rbx
0x140029053  jnz     short loc_140029080
0x140029055  mov     [r14], rbx
0x140029058  xor     edi, edi
0x14002905a  mov     rcx, rbx; bstrString
0x14002905d  call    cs:__imp_SysFreeString
0x140029064  nop     dword ptr [rax+rax+00h]
0x140029069  mov     eax, edi
0x14002906b  mov     rbx, [rsp+58h+arg_0]
0x140029070  mov     rsi, [rsp+58h+arg_8]
0x140029075  add     rsp, 40h
0x140029079  pop     r15
0x14002907b  pop     r14
0x14002907d  pop     rdi
0x14002907e  retn
0x140029080  mov     rcx, rbx; bstr
0x140029083  call    cs:__imp_SysStringByteLen
0x14002908a  nop     dword ptr [rax+rax+00h]
0x14002908f  mov     edx, eax; len
0x140029091  mov     rcx, rbx; psz
0x140029094  call    cs:__imp_SysAllocStringByteLen
0x14002909b  nop     dword ptr [rax+rax+00h]
0x1400290a0  mov     [r14], rax
0x1400290a3  test    rax, rax
0x1400290a6  jnz     short loc_140029058
0x1400290a8  mov     edi, 8007000Eh
0x1400290ad  jmp     short loc_14002905A
0x1400290af  mov     ecx, 8007000Eh; int
0x1400290b4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
