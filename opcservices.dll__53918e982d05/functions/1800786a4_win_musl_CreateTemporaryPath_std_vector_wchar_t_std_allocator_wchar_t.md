# win_musl::CreateTemporaryPath(std::vector<wchar_t,std::allocator<wchar_t>> &)

- ea: `0x1800786a4`
- end: `0x180078869`
- name: `?CreateTemporaryPath@win_musl@@YAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180053328`

## callees

- `0x180017320`
- `0x18001c2d0`
- `0x18002db70`
- `0x180060c90`
- `0x18006554c`
- `0x1800786a4`
- `0x180078870`
- `0x180084010`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180078767`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180078767`

## string_xrefs

- `0x180078777`: `GetTempPath returned.`

## pseudocode

```c
__int64 __fastcall win_musl::CreateTemporaryPath(__int64 a1)
{
  DWORD v2; // esi
  DWORD TempPathW; // edi
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  win_musl::Formatter *v14; // rax
  struct win_musl::TStringEllipseBase *v15; // rbx
  win_musl::detail *v16; // rcx
  unsigned int LastErrorAsFailHR; // eax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 result; // rax
  __int16 v28; // [rsp+40h] [rbp-158h] BYREF
  __int64 v29; // [rsp+48h] [rbp-150h]
  _BYTE v30[48]; // [rsp+50h] [rbp-148h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v32[96]; // [rsp+120h] [rbp-78h] BYREF

  v29 = -2;
  v2 = 0;
  TempPathW = 0;
  while ( 1 )
  {
    v4 = TempPathW + 1;
    if ( TempPathW < v2 )
      break;
    if ( TempPathW + 1 <= 0x104 )
    {
      v4 = 260;
    }
    else if ( v4 >= 0x10000 )
    {
      v4 = 0x10000;
    }
    v28 = 0;
    v5 = std::vector<wchar_t>::size(a1, v4);
    if ( v5 >= v6 )
    {
      v12 = std::vector<wchar_t>::size(v7, v6);
      if ( v11 < v12 )
      {
        v13 = *(_QWORD *)(a1 + 8) + 2 * v11;
        if ( v13 != *(_QWORD *)(a1 + 16) )
          *(_QWORD *)(a1 + 16) = v13;
      }
    }
    else
    {
      v8 = std::vector<wchar_t>::size(v7, v6);
      std::vector<wchar_t>::_Insert_n(v10, *(_QWORD *)(a1 + 16), v9 - v8, &v28);
    }
    v2 = std::vector<wchar_t>::size(a1, v11);
    **(_WORD **)(a1 + 8) = 0;
    TempPathW = GetTempPathW(v2, *(LPWSTR *)(a1 + 8));
    if ( !TempPathW )
    {
      std::wstring::wstring(v30, L"GetTempPath returned.");
      v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v32, v30);
      v15 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v14);
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xA7u,
        LastErrorAsFailHR,
        v15);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  v28 = 0;
  v18 = std::vector<wchar_t>::size(a1, v4);
  if ( v18 >= v19 )
  {
    v24 = std::vector<wchar_t>::size(v20, v19);
    if ( v25 < v24 )
    {
      v26 = *(_QWORD *)(a1 + 8) + 2 * v25;
      if ( v26 != *(_QWORD *)(a1 + 16) )
        *(_QWORD *)(a1 + 16) = v26;
    }
  }
  else
  {
    v21 = std::vector<wchar_t>::size(v20, v19);
    std::vector<wchar_t>::_Insert_n(v23, *(_QWORD *)(a1 + 16), v22 - v21, &v28);
  }
  result = 0;
  *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * TempPathW) = 0;
  return result;
}

```

## disassembly

```asm
0x1800786a4  mov     rax, rsp
0x1800786a7  push    rdi
0x1800786a8  sub     rsp, 190h
0x1800786af  mov     [rsp+198h+var_150], 0FFFFFFFFFFFFFFFEh
0x1800786b8  mov     [rax+10h], rbx
0x1800786bc  mov     [rax+18h], rsi
0x1800786c0  mov     rax, cs:__security_cookie
0x1800786c7  xor     rax, rsp
0x1800786ca  mov     [rsp+198h+var_18], rax
0x1800786d2  mov     rbx, rcx
0x1800786d5  xor     esi, esi
0x1800786d7  xor     edi, edi
0x1800786d9  lea     eax, [rdi+1]
0x1800786dc  mov     edx, eax
0x1800786de  cmp     edi, esi
0x1800786e0  jb      loc_1800787ED
0x1800786e6  cmp     eax, 104h
0x1800786eb  jbe     short loc_1800786FD
0x1800786ed  cmp     rdx, 10000h
0x1800786f4  jb      short loc_180078702
0x1800786f6  mov     edx, 10000h
0x1800786fb  jmp     short loc_180078702
0x1800786fd  mov     edx, 104h
0x180078702  xor     eax, eax
0x180078704  mov     [rsp+198h+var_158], ax
0x180078709  mov     rcx, rbx
0x18007870c  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x180078711  cmp     rax, rdx
0x180078714  jnb     short loc_180078731
0x180078716  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x18007871b  sub     rdx, rax
0x18007871e  lea     r9, [rsp+198h+var_158]
0x180078723  mov     r8, rdx
0x180078726  mov     rdx, [rbx+10h]
0x18007872a  call    ?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z; std::vector<wchar_t>::_Insert_n(std::_Vector_iterator<wchar_t>,unsigned __int64,wchar_t const &)
0x18007872f  jmp     short loc_18007874D
0x180078731  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x180078736  cmp     rdx, rax
0x180078739  jnb     short loc_18007874D
0x18007873b  mov     rax, [rbx+8]
0x18007873f  lea     rcx, [rax+rdx*2]
0x180078743  cmp     rcx, [rbx+10h]
0x180078747  jz      short loc_18007874D
0x180078749  mov     [rbx+10h], rcx
0x18007874d  mov     rcx, rbx
0x180078750  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x180078755  mov     rsi, rax
0x180078758  mov     rdx, [rbx+8]
0x18007875c  xor     ecx, ecx
0x18007875e  mov     [rdx], cx
0x180078761  mov     rdx, [rbx+8]; lpBuffer
0x180078765  mov     ecx, eax; nBufferLength
0x180078767  call    cs:__imp_GetTempPathW
0x18007876d  mov     edi, eax
0x18007876f  test    eax, eax
0x180078771  jnz     loc_1800786D9
0x180078777  lea     rdx, aGettemppathRet; "GetTempPath returned."
0x18007877e  lea     rcx, [rsp+198h+var_148]
0x180078783  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180078788  nop
0x180078789  lea     rdx, [rsp+198h+var_148]
0x18007878e  lea     rcx, [rsp+198h+var_78]
0x180078796  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18007879b  nop
0x18007879c  mov     rcx, rax; this
0x18007879f  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800787a4  mov     rbx, rax
0x1800787a7  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800787ac  mov     [rsp+198h+var_168], rbx; struct win_musl::TStringEllipseBase *
0x1800787b1  mov     [rsp+198h+var_170], eax; unsigned int
0x1800787b5  mov     [rsp+198h+var_178], 0A7h; unsigned int
0x1800787bd  lea     r9, word_180139126
0x1800787c4  lea     r8, aNoFilename; "(no filename)"
0x1800787cb  lea     rcx, [rsp+198h+pExceptionObject]; this
0x1800787d3  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800787d8  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800787df  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x1800787e7  call    _CxxThrowException_0
0x1800787ed  xor     eax, eax
0x1800787ef  mov     [rsp+198h+var_158], ax
0x1800787f4  mov     rcx, rbx
0x1800787f7  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x1800787fc  cmp     rax, rdx
0x1800787ff  jnb     short loc_18007881C
0x180078801  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x180078806  sub     rdx, rax
0x180078809  lea     r9, [rsp+198h+var_158]
0x18007880e  mov     r8, rdx
0x180078811  mov     rdx, [rbx+10h]
0x180078815  call    ?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z; std::vector<wchar_t>::_Insert_n(std::_Vector_iterator<wchar_t>,unsigned __int64,wchar_t const &)
0x18007881a  jmp     short loc_180078838
0x18007881c  call    ?size@?$vector@_WV?$allocator@_W@std@@@std@@QEBA_KXZ; std::vector<wchar_t>::size(void)
0x180078821  cmp     rdx, rax
0x180078824  jnb     short loc_180078838
0x180078826  mov     rax, [rbx+8]
0x18007882a  lea     rcx, [rax+rdx*2]
0x18007882e  cmp     rcx, [rbx+10h]
0x180078832  jz      short loc_180078838
0x180078834  mov     [rbx+10h], rcx
0x180078838  mov     edx, edi
0x18007883a  mov     rcx, [rbx+8]
0x18007883e  xor     eax, eax
0x180078840  mov     [rcx+rdx*2], ax
0x180078844  mov     rcx, [rsp+198h+var_18]
0x18007884c  xor     rcx, rsp; StackCookie
0x18007884f  call    __security_check_cookie
0x180078854  lea     r11, [rsp+198h+var_8]
0x18007885c  mov     rbx, [r11+18h]
0x180078860  mov     rsi, [r11+20h]
0x180078864  mov     rsp, r11
0x180078867  pop     rdi
0x180078868  retn
```
