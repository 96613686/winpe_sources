# ATL::CAxHostWindow::TranslateUrl(ulong,ushort *,ushort * *)

- ea: `0x1400180b0`
- end: `0x140018235`
- name: `?TranslateUrl@CAxHostWindow@ATL@@UEAAJKPEAGPEAPEAG@Z`
- size: `389`
- prototype: `int(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400044f8`
- `0x1400180b0`
- `0x14004d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400181d1`
- `msvcrt!memcpy_s` at `0x1400181d1`
- `ole32!CoTaskMemAlloc` at `0x140018194`
- `ole32!CoTaskMemAlloc` at `0x140018194`
- `OLEAUT32!__imp_SysAllocString` at `0x140018118`
- `OLEAUT32!__imp_SysAllocString` at `0x140018118`
- `OLEAUT32!__imp_SysFreeString` at `0x14001814f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400181ad`
- `OLEAUT32!__imp_SysFreeString` at `0x140018201`
- `OLEAUT32!__imp_SysFreeString` at `0x14001814f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400181ad`
- `OLEAUT32!__imp_SysFreeString` at `0x140018201`
- `OLEAUT32!__imp_SysStringLen` at `0x140018168`
- `OLEAUT32!__imp_SysStringLen` at `0x14001817d`
- `OLEAUT32!__imp_SysStringLen` at `0x140018168`
- `OLEAUT32!__imp_SysStringLen` at `0x14001817d`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::TranslateUrl(
        ATL::CAxHostWindow *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 *v7; // rdi
  int v8; // edi
  __int64 v9; // rbp
  OLECHAR *v10; // rbx
  SIZE_T v11; // rbx
  unsigned __int16 *v12; // rax
  errno_t v13; // eax
  BSTR pbstr; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v7 = (__int64 *)*((_QWORD *)this + 13);
  if ( v7 )
  {
    pbstr = 0;
    v9 = *v7;
    if ( a3 )
    {
      v10 = SysAllocString(a3);
      if ( !v10 )
        goto LABEL_23;
    }
    else
    {
      v10 = 0;
    }
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, OLECHAR *, BSTR *))(v9 + 160))(v7, a2, v10, &pbstr);
    SysFreeString(v10);
    if ( v8 < 0 || !SysStringLen(pbstr) )
    {
      v8 = 1;
LABEL_19:
      SysFreeString(pbstr);
      return (unsigned int)v8;
    }
    v11 = 2 * SysStringLen(pbstr) + 2;
    v12 = (unsigned __int16 *)CoTaskMemAlloc(v11);
    *a4 = v12;
    if ( !v12 )
    {
      SysFreeString(pbstr);
      return 2147942414LL;
    }
    v13 = memcpy_s(v12, v11, pbstr, v11);
    if ( !v13 )
      goto LABEL_19;
    if ( v13 != 12 )
    {
      if ( v13 == 22 || v13 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v13 != 80 )
        ATL::AtlThrowImpl(-2147467259);
      goto LABEL_19;
    }
LABEL_23:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 1;
}

```

## disassembly

```asm
0x1400180b0  mov     [rsp+arg_0], rbx
0x1400180b5  mov     [rsp+arg_8], rbp
0x1400180ba  push    rsi
0x1400180bb  push    rdi
0x1400180bc  push    r14
0x1400180be  sub     rsp, 30h
0x1400180c2  mov     rsi, r9
0x1400180c5  mov     r14d, edx
0x1400180c8  test    r9, r9
0x1400180cb  jnz     short loc_1400180E6
0x1400180cd  mov     eax, 80004003h
0x1400180d2  mov     rbx, [rsp+48h+arg_0]
0x1400180d7  mov     rbp, [rsp+48h+arg_8]
0x1400180dc  add     rsp, 30h
0x1400180e0  pop     r14
0x1400180e2  pop     rdi
0x1400180e3  pop     rsi
0x1400180e4  retn
0x1400180e6  mov     qword ptr [r9], 0
0x1400180ed  mov     rdi, [rcx+68h]
0x1400180f1  test    rdi, rdi
0x1400180f4  jnz     short loc_140018100
0x1400180f6  mov     edi, 1
0x1400180fb  jmp     loc_14001820D
0x140018100  mov     [rsp+48h+pbstr], 0
0x140018109  mov     rbp, [rdi]
0x14001810c  test    r8, r8
0x14001810f  jnz     short loc_140018115
0x140018111  xor     ebx, ebx
0x140018113  jmp     short loc_140018130
0x140018115  mov     rcx, r8; psz
0x140018118  call    cs:__imp_SysAllocString
0x14001811f  nop     dword ptr [rax+rax+00h]
0x140018124  mov     rbx, rax
0x140018127  test    rax, rax
0x14001812a  jz      loc_14001822A
0x140018130  mov     rax, [rbp+0A0h]
0x140018137  lea     r9, [rsp+48h+pbstr]
0x14001813c  mov     r8, rbx
0x14001813f  mov     edx, r14d
0x140018142  mov     rcx, rdi
0x140018145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001814a  mov     rcx, rbx; bstrString
0x14001814d  mov     edi, eax
0x14001814f  call    cs:__imp_SysFreeString
0x140018156  nop     dword ptr [rax+rax+00h]
0x14001815b  test    edi, edi
0x14001815d  js      loc_1400181F7
0x140018163  mov     rcx, [rsp+48h+pbstr]; pbstr
0x140018168  call    cs:__imp_SysStringLen
0x14001816f  nop     dword ptr [rax+rax+00h]
0x140018174  test    eax, eax
0x140018176  jz      short loc_1400181F7
0x140018178  mov     rcx, [rsp+48h+pbstr]; pbstr
0x14001817d  call    cs:__imp_SysStringLen
0x140018184  nop     dword ptr [rax+rax+00h]
0x140018189  lea     eax, ds:2[rax*2]
0x140018190  mov     ecx, eax; cb
0x140018192  mov     ebx, eax
0x140018194  call    cs:__imp_CoTaskMemAlloc
0x14001819b  nop     dword ptr [rax+rax+00h]
0x1400181a0  mov     [rsi], rax
0x1400181a3  test    rax, rax
0x1400181a6  jnz     short loc_1400181C3
0x1400181a8  mov     rcx, [rsp+48h+pbstr]; bstrString
0x1400181ad  call    cs:__imp_SysFreeString
0x1400181b4  nop     dword ptr [rax+rax+00h]
0x1400181b9  mov     eax, 8007000Eh
0x1400181be  jmp     loc_1400180D2
0x1400181c3  mov     r8, [rsp+48h+pbstr]; Source
0x1400181c8  mov     r9, rbx; SourceSize
0x1400181cb  mov     rdx, rbx; DestinationSize
0x1400181ce  mov     rcx, rax; Destination
0x1400181d1  call    cs:__imp_memcpy_s
0x1400181d8  nop     dword ptr [rax+rax+00h]
0x1400181dd  test    eax, eax
0x1400181df  jz      short loc_1400181FC
0x1400181e1  cmp     eax, 0Ch
0x1400181e4  jz      short loc_14001822A
0x1400181e6  cmp     eax, 16h
0x1400181e9  jz      short loc_140018214
0x1400181eb  cmp     eax, 22h ; '"'
0x1400181ee  jz      short loc_140018214
0x1400181f0  cmp     eax, 50h ; 'P'
0x1400181f3  jnz     short loc_14001821F
0x1400181f5  jmp     short loc_1400181FC
0x1400181f7  mov     edi, 1
0x1400181fc  mov     rcx, [rsp+48h+pbstr]; bstrString
0x140018201  call    cs:__imp_SysFreeString
0x140018208  nop     dword ptr [rax+rax+00h]
0x14001820d  mov     eax, edi
0x14001820f  jmp     loc_1400180D2
0x140018214  mov     ecx, 80070057h; int
0x140018219  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001821f  mov     ecx, 80004005h; int
0x140018224  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001822a  mov     ecx, 8007000Eh; int
0x14001822f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
