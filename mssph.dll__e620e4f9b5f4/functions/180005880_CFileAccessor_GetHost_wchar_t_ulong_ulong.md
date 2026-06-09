# CFileAccessor::GetHost(wchar_t *,ulong,ulong *)

- ea: `0x180005880`
- end: `0x180005a45`
- name: `?GetHost@CFileAccessor@@UEAAJPEA_WKPEAK@Z`
- size: `453`
- prototype: `int(CFileAccessor *__hidden this, wchar_t *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004ec4`
- `0x180005880`
- `0x180005c00`
- `0x1800075e0`
- `0x180007810`
- `0x1800090b0`
- `0x18000a0a0`
- `0x18000a210`
- `0x18000a890`
- `0x18000e4c8`
- `0x18000fcd0`
- `0x180020bac`
- `0x180020e3c`
- `0x180021724`

## pseudocode

```c
__int64 __fastcall CFileAccessor::GetHost(CFileAccessor *this, wchar_t *a2, unsigned int a3, unsigned int *a4)
{
  const wchar_t *v5; // r9
  unsigned __int16 *v10; // rbx
  __int64 Host; // rax
  unsigned int v12; // ebx
  _DWORD v13[2]; // [rsp+20h] [rbp-1D8h] BYREF
  __int64 v14; // [rsp+28h] [rbp-1D0h]
  _BYTE v15[416]; // [rsp+30h] [rbp-1C8h] BYREF

  *a4 = 0;
  v5 = (const wchar_t *)*((unsigned int *)this + 37);
  if ( (_DWORD)v5 )
    goto LABEL_5;
  if ( !*((_DWORD *)this + 36) || *((_DWORD *)this + 28) == 259 )
  {
    v5 = 0;
LABEL_5:
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x5CE,
      (__int64)L"[SrchPHFile] Check oplock %d\n",
      v5);
    goto LABEL_6;
  }
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_FilterOplockBreak,
      *((_QWORD *)this + 88));
  SearchIndexerTrace::Warning(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
    (const wchar_t *)0x5CA,
    (unsigned int)L"[SrchPHFile] Oplock broken for %ls\n",
    *((const wchar_t **)this + 88));
  *((_DWORD *)this + 37) = 1;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
    (const wchar_t *)0x5CE,
    (__int64)L"[SrchPHFile] Check oplock %d\n",
    (const wchar_t *)1);
LABEL_6:
  if ( *((_DWORD *)this + 37) )
    return 2147942432LL;
  if ( !*((_DWORD *)this + 214) && (*((_BYTE *)this + 904) & 0x10) == 0 )
    return 2147749157LL;
  v10 = (unsigned __int16 *)((char *)this + 224);
  if ( (unsigned int)CURL::IsLocalPath((CURL *)v10) )
    return 2147500033LL;
  Host = CURL::GetHost(v10, v13);
  TLMString<192,64,32767>::TLMString<192,64,32767>(v15, Host);
  CLMString::operator+=(v15);
  CURL::ParseHost((CURL *)v10);
  CLMString::Mid((__int64)(v10 + 12), (__int64)v13, v10[223], v10[224]);
  CLMString::Append((CLMString *)v15, (const wchar_t *)(*(_QWORD *)(v14 + 8) + 2LL * v13[0]), v13[1]);
  v12 = CLMString::Export((CLMString *)v15, a2, a3, a4);
  TLMString<192,64,32767>::~TLMString<192,64,32767>(v15);
  return v12;
}

```

## disassembly

```asm
0x180005880  mov     [rsp+arg_10], rbx
0x180005885  push    rbp
0x180005886  push    rsi
0x180005887  push    rdi
0x180005888  sub     rsp, 1E0h
0x18000588f  mov     rax, cs:__security_cookie
0x180005896  xor     rax, rsp
0x180005899  mov     [rsp+1F8h+var_28], rax
0x1800058a1  mov     rdi, r9
0x1800058a4  mov     dword ptr [r9], 0
0x1800058ab  mov     r9d, [rcx+94h]
0x1800058b2  mov     esi, r8d
0x1800058b5  mov     rbp, rdx
0x1800058b8  mov     rbx, rcx
0x1800058bb  test    r9d, r9d
0x1800058be  jnz     short loc_1800058D5
0x1800058c0  cmp     [rcx+90h], r9d
0x1800058c7  jz      short loc_1800058D2
0x1800058c9  cmp     dword ptr [rcx+70h], 103h
0x1800058d0  jnz     short loc_18000593C
0x1800058d2  xor     r9d, r9d; wchar_t *
0x1800058d5  lea     r8, aSrchphfileChec; "[SrchPHFile] Check oplock %d\n"
0x1800058dc  mov     edx, 5CEh; wchar_t *
0x1800058e1  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800058e8  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800058ed  cmp     dword ptr [rbx+94h], 0
0x1800058f4  jnz     loc_180005990
0x1800058fa  cmp     dword ptr [rbx+358h], 0
0x180005901  jnz     loc_180005997
0x180005907  test    byte ptr [rbx+388h], 10h
0x18000590e  jnz     loc_180005997
0x180005914  mov     eax, 80040D25h
0x180005919  mov     rcx, [rsp+1F8h+var_28]
0x180005921  xor     rcx, rsp; StackCookie
0x180005924  call    __security_check_cookie
0x180005929  mov     rbx, [rsp+1F8h+arg_10]
0x180005931  add     rsp, 1E0h
0x180005938  pop     rdi
0x180005939  pop     rsi
0x18000593a  pop     rbp
0x18000593b  retn
0x18000593c  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 8
0x180005943  jz      short loc_18000595F
0x180005945  mov     r8, [rcx+2C0h]
0x18000594c  lea     rdx, MSSearchTraceId_FilterOplockBreak
0x180005953  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18000595a  call    McTemplateU0z_EventWriteTransfer
0x18000595f  mov     r9, [rbx+2C0h]; wchar_t *
0x180005966  lea     r8, aSrchphfileOplo; "[SrchPHFile] Oplock broken for %ls\n"
0x18000596d  mov     edx, 5CAh; wchar_t *
0x180005972  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180005979  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x18000597e  mov     r9d, 1
0x180005984  mov     [rbx+94h], r9d
0x18000598b  jmp     loc_1800058D5
0x180005990  mov     eax, 80070020h
0x180005995  jmp     short loc_180005919
0x180005997  add     rbx, 0E0h
0x18000599e  mov     rcx, rbx; this
0x1800059a1  call    ?IsLocalPath@CURL@@QEAAHXZ; CURL::IsLocalPath(void)
0x1800059a6  test    eax, eax
0x1800059a8  jz      short loc_1800059B4
0x1800059aa  mov     eax, 80004001h
0x1800059af  jmp     loc_180005919
0x1800059b4  lea     rdx, [rsp+1F8h+var_1D8]
0x1800059b9  mov     rcx, rbx
0x1800059bc  call    ?GetHost@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetHost(void)
0x1800059c1  mov     rdx, rax
0x1800059c4  lea     rcx, [rsp+1F8h+var_1C8]
0x1800059c9  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@AEBVCLMSubStr@@@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(CLMSubStr const &)
0x1800059ce  lea     rcx, [rsp+1F8h+var_1C8]
0x1800059d3  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x1800059d8  mov     rcx, rbx; this
0x1800059db  call    ?ParseHost@CURL@@IEAAXXZ; CURL::ParseHost(void)
0x1800059e0  movzx   r9d, word ptr [rbx+1C0h]
0x1800059e8  lea     rcx, [rbx+18h]
0x1800059ec  movzx   r8d, word ptr [rbx+1BEh]
0x1800059f4  lea     rdx, [rsp+1F8h+var_1D8]
0x1800059f9  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x1800059fe  mov     r8d, [rsp+1F8h+var_1D8]
0x180005a03  mov     rax, [rsp+1F8h+var_1D0]
0x180005a08  mov     rcx, [rax+8]
0x180005a0c  lea     rdx, [rcx+r8*2]; wchar_t *
0x180005a10  mov     r8d, [rsp+1F8h+var_1D4]; unsigned int
0x180005a15  lea     rcx, [rsp+1F8h+var_1C8]; this
0x180005a1a  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180005a1f  mov     r9, rdi; unsigned int *
0x180005a22  lea     rcx, [rsp+1F8h+var_1C8]; this
0x180005a27  mov     r8d, esi; unsigned int
0x180005a2a  mov     rdx, rbp; wchar_t *
0x180005a2d  call    ?Export@CLMString@@QEBAJQEA_WKPEAK@Z; CLMString::Export(wchar_t * const,ulong,ulong *)
0x180005a32  lea     rcx, [rsp+1F8h+var_1C8]
0x180005a37  mov     ebx, eax
0x180005a39  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x180005a3e  mov     eax, ebx
0x180005a40  jmp     loc_180005919
```
