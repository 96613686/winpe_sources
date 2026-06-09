# CFDRPlugin::GenerateLogPathAndFileName(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,ulong)

- ea: `0x1800354c8`
- end: `0x180035779`
- name: `?GenerateLogPathAndFileName@CFDRPlugin@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0K@Z`
- size: `689`
- prototype: `__int64 __fastcall(WCHAR *, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180036a5c`

## callees

- `0x1800028b4`
- `0x180006684`
- `0x180009ed8`
- `0x180024bc4`
- `0x1800354c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003560e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003560e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035616`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035616`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18003555a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18003555a`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::GenerateLogPathAndFileName(WCHAR *a1, wchar_t **a2, wchar_t **a3)
{
  const struct std::nothrow_t *v5; // rdx
  LPWSTR v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HRESULT v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  const struct std::nothrow_t **unique_for; // rax
  wchar_t *v13; // rcx
  const struct std::nothrow_t **v14; // rax
  wchar_t *v15; // rcx
  DWORD TickCount; // [rsp+28h] [rbp-50h]
  DWORD CurrentThreadId; // [rsp+30h] [rbp-48h]
  LPWSTR pszPath; // [rsp+80h] [rbp+8h] BYREF

  pszPath = a1;
  if ( a3 && a2 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&pszPath, 0x104u);
    v6 = pszPath;
    if ( !pszPath )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_8;
      v8 = (unsigned int)((_DWORD)pszPath + 60);
LABEL_7:
      WPP_SF_(v7[2], v8, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_8:
      v9 = -2147024882;
      goto LABEL_39;
    }
    v9 = SHGetFolderPathW(0, 28, 0, 0, pszPath);
    if ( v9 >= 0 )
    {
      unique_for = (const struct std::nothrow_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&pszPath, 0x104u);
      v5 = *unique_for;
      *unique_for = 0;
      v13 = *a3;
      *a3 = (wchar_t *)v5;
      if ( v13 )
        operator delete(v13, v5);
      if ( pszPath )
        operator delete(pszPath, v5);
      if ( !*a3 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_8;
        v8 = 62;
        goto LABEL_7;
      }
      CurrentThreadId = GetCurrentThreadId();
      TickCount = GetTickCount();
      v9 = StringCchPrintfW(
             *a3,
             0x104u,
             L"%s\\%s\\%u-%u.etl",
             v6,
             L"Microsoft\\Windows\\FDR",
             TickCount,
             CurrentThreadId);
      if ( v9 >= 0 )
      {
        v14 = (const struct std::nothrow_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&pszPath, 0x104u);
        v5 = *v14;
        *v14 = 0;
        v15 = *a2;
        *a2 = (wchar_t *)v5;
        if ( v15 )
          operator delete(v15, v5);
        if ( pszPath )
          operator delete(pszPath, v5);
        if ( !*a2 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_8;
          v8 = 64;
          goto LABEL_7;
        }
        v9 = StringCchPrintfW(*a2, 0x104u, L"%s\\%s", v6, L"Microsoft\\Windows\\FDR");
        if ( v9 >= 0 )
        {
          v9 = 0;
          goto LABEL_39;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 65;
          goto LABEL_13;
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 63;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 61;
LABEL_13:
        WPP_SF_(v10[2], v11, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      }
    }
LABEL_39:
    if ( v6 )
      operator delete(v6, v5);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800354c8  mov     rax, rsp
0x1800354cb  mov     [rax+8], rcx
0x1800354cf  push    rbx
0x1800354d0  push    rsi
0x1800354d1  push    rdi
0x1800354d2  push    r12
0x1800354d4  push    r14
0x1800354d6  push    r15
0x1800354d8  sub     rsp, 48h
0x1800354dc  mov     rdi, r8
0x1800354df  mov     r14, rdx
0x1800354e2  test    r8, r8
0x1800354e5  jz      loc_180035738
0x1800354eb  test    rdx, rdx
0x1800354ee  jz      loc_180035738
0x1800354f4  mov     r15d, 104h
0x1800354fa  lea     rcx, [rax+8]
0x1800354fe  mov     edx, r15d
0x180035501  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180035506  mov     rsi, [rsp+78h+arg_0]
0x18003550e  test    rsi, rsi
0x180035511  jnz     short loc_180035549
0x180035513  mov     rcx, cs:WPP_GLOBAL_Control
0x18003551a  lea     rax, WPP_GLOBAL_Control
0x180035521  cmp     rcx, rax
0x180035524  jz      short loc_18003553F
0x180035526  test    byte ptr [rcx+1Ch], 1
0x18003552a  jz      short loc_18003553F
0x18003552c  lea     edx, [rsi+3Ch]
0x18003552f  mov     rcx, [rcx+10h]
0x180035533  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x18003553a  call    WPP_SF_
0x18003553f  mov     ebx, 8007000Eh
0x180035544  jmp     loc_180035727
0x180035549  xor     r9d, r9d; dwFlags
0x18003554c  mov     [rsp+78h+pszPath], rsi; pszPath
0x180035551  xor     r8d, r8d; hToken
0x180035554  xor     ecx, ecx; hwnd
0x180035556  lea     edx, [r9+1Ch]; csidl
0x18003555a  call    cs:__imp_SHGetFolderPathW
0x180035560  mov     ebx, eax
0x180035562  test    eax, eax
0x180035564  jns     short loc_1800355A1
0x180035566  mov     rcx, cs:WPP_GLOBAL_Control
0x18003556d  lea     rax, WPP_GLOBAL_Control
0x180035574  cmp     rcx, rax
0x180035577  jz      loc_180035727
0x18003557d  test    byte ptr [rcx+1Ch], 1
0x180035581  jz      loc_180035727
0x180035587  mov     edx, 3Dh ; '='
0x18003558c  mov     rcx, [rcx+10h]
0x180035590  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180035597  call    WPP_SF_
0x18003559c  jmp     loc_180035727
0x1800355a1  mov     rdx, r15
0x1800355a4  lea     rcx, [rsp+78h+arg_0]
0x1800355ac  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800355b1  mov     rdx, [rax]; struct std::nothrow_t *
0x1800355b4  mov     qword ptr [rax], 0
0x1800355bb  mov     rcx, [rdi]; void *
0x1800355be  mov     [rdi], rdx
0x1800355c1  test    rcx, rcx
0x1800355c4  jz      short loc_1800355CB
0x1800355c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800355cb  mov     rcx, [rsp+78h+arg_0]; void *
0x1800355d3  test    rcx, rcx
0x1800355d6  jz      short loc_1800355DD
0x1800355d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800355dd  cmp     qword ptr [rdi], 0
0x1800355e1  jnz     short loc_18003560E
0x1800355e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355ea  lea     rax, WPP_GLOBAL_Control
0x1800355f1  cmp     rcx, rax
0x1800355f4  jz      loc_18003553F
0x1800355fa  test    byte ptr [rcx+1Ch], 1
0x1800355fe  jz      loc_18003553F
0x180035604  mov     edx, 3Eh ; '>'
0x180035609  jmp     loc_18003552F
0x18003560e  call    cs:__imp_GetCurrentThreadId
0x180035614  mov     ebx, eax
0x180035616  call    cs:__imp_GetTickCount
0x18003561c  mov     rcx, [rdi]; wchar_t *
0x18003561f  lea     r12, aMicrosoftWindo; "Microsoft\\Windows\\FDR"
0x180035626  mov     [rsp+78h+var_48], ebx
0x18003562a  lea     r8, aSSUUEtl; "%s\\%s\\%u-%u.etl"
0x180035631  mov     [rsp+78h+var_50], eax
0x180035635  mov     r9, rsi
0x180035638  mov     rdx, r15; unsigned __int64
0x18003563b  mov     [rsp+78h+pszPath], r12
0x180035640  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180035645  mov     ebx, eax
0x180035647  test    eax, eax
0x180035649  jns     short loc_180035676
0x18003564b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035652  lea     rax, WPP_GLOBAL_Control
0x180035659  cmp     rcx, rax
0x18003565c  jz      loc_180035727
0x180035662  test    byte ptr [rcx+1Ch], 1
0x180035666  jz      loc_180035727
0x18003566c  mov     edx, 3Fh ; '?'
0x180035671  jmp     loc_18003558C
0x180035676  mov     rdx, r15
0x180035679  lea     rcx, [rsp+78h+arg_0]
0x180035681  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180035686  mov     rdx, [rax]; struct std::nothrow_t *
0x180035689  mov     qword ptr [rax], 0
0x180035690  mov     rcx, [r14]; void *
0x180035693  mov     [r14], rdx
0x180035696  test    rcx, rcx
0x180035699  jz      short loc_1800356A0
0x18003569b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800356a0  mov     rcx, [rsp+78h+arg_0]; void *
0x1800356a8  test    rcx, rcx
0x1800356ab  jz      short loc_1800356B2
0x1800356ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800356b2  mov     rcx, [r14]; wchar_t *
0x1800356b5  test    rcx, rcx
0x1800356b8  jnz     short loc_1800356E5
0x1800356ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356c1  lea     rax, WPP_GLOBAL_Control
0x1800356c8  cmp     rcx, rax
0x1800356cb  jz      loc_18003553F
0x1800356d1  test    byte ptr [rcx+1Ch], 1
0x1800356d5  jz      loc_18003553F
0x1800356db  mov     edx, 40h ; '@'
0x1800356e0  jmp     loc_18003552F
0x1800356e5  mov     r9, rsi
0x1800356e8  mov     [rsp+78h+pszPath], r12
0x1800356ed  lea     r8, aSS_0; "%s\\%s"
0x1800356f4  mov     rdx, r15; unsigned __int64
0x1800356f7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800356fc  mov     ebx, eax
0x1800356fe  test    eax, eax
0x180035700  jns     short loc_180035725
0x180035702  mov     rcx, cs:WPP_GLOBAL_Control
0x180035709  lea     rax, WPP_GLOBAL_Control
0x180035710  cmp     rcx, rax
0x180035713  jz      short loc_180035727
0x180035715  test    byte ptr [rcx+1Ch], 1
0x180035719  jz      short loc_180035727
0x18003571b  mov     edx, 41h ; 'A'
0x180035720  jmp     loc_18003558C
0x180035725  xor     ebx, ebx
0x180035727  test    rsi, rsi
0x18003572a  jz      short loc_180035734
0x18003572c  mov     rcx, rsi; void *
0x18003572f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035734  mov     eax, ebx
0x180035736  jmp     short loc_18003576B
0x180035738  mov     rcx, cs:WPP_GLOBAL_Control
0x18003573f  lea     rax, WPP_GLOBAL_Control
0x180035746  cmp     rcx, rax
0x180035749  jz      short loc_180035766
0x18003574b  test    byte ptr [rcx+1Ch], 1
0x18003574f  jz      short loc_180035766
0x180035751  mov     rcx, [rcx+10h]
0x180035755  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x18003575c  mov     edx, 3Bh ; ';'
0x180035761  call    WPP_SF_
0x180035766  mov     eax, 80070057h
0x18003576b  add     rsp, 48h
0x18003576f  pop     r15
0x180035771  pop     r14
0x180035773  pop     r12
0x180035775  pop     rdi
0x180035776  pop     rsi
0x180035777  pop     rbx
0x180035778  retn
```
