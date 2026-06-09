# MSQAThread(void *)

- ea: `0x1004450e0`
- end: `0x10044562f`
- name: `?MSQAThread@@YAIPEAX@Z`
- size: `1359`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x100430824`
- `0x100444028`
- `0x1004450e0`
- `0x100448458`
- `0x10046a424`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10044521f`
- `KERNEL32!GetLastError` at `0x10044521f`
- `USER32!LoadStringW` at `0x1004451a6`
- `USER32!LoadStringW` at `0x1004451a6`
- `USER32!GetDesktopWindow` at `0x1004451c6`
- `USER32!GetDesktopWindow` at `0x1004451c6`
- `USER32!ReleaseCapture` at `0x100445259`
- `USER32!ReleaseCapture` at `0x100445259`
- `USER32!DispatchMessageW` at `0x100445271`
- `USER32!DispatchMessageW` at `0x100445271`
- `USER32!TranslateMessage` at `0x100445266`
- `USER32!TranslateMessage` at `0x100445266`
- `USER32!GetMessageW` at `0x100445284`
- `USER32!GetMessageW` at `0x100445284`
- `ole32!CoInitializeEx` at `0x100445126`
- `ole32!CoInitializeEx` at `0x100445126`
- `ole32!CoUninitialize` at `0x1004455fb`
- `ole32!CoUninitialize` at `0x1004455fb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004453fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004454d3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004454da`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100445573`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004453fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004454d3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004454da`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100445573`

## string_xrefs

- `0x100445189`: `<MSQAThread|ERR|SNI> MSQAUseInteractive return status: %u.\n`
- `0x10044529d`: `<MSQAThread|ERR|SNI> MSQAUseUsernamePassword return status: %u.\n`
- `0x1004452a4`: `<MSQAThread|ERR|SNI> MSQAUseWindowsAuthentication return status: %u.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MSQAThread(unsigned int **a1)
{
  HRESULT v2; // eax
  char v3; // al
  const wchar_t *v4; // rsi
  HWND DesktopWindow; // rbx
  unsigned int SOSThreadId; // eax
  int v7; // eax
  wchar_t *v8; // r8
  __int64 v9; // rdx
  unsigned int *v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r8
  unsigned int *v13; // rdx
  _QWORD *v14; // r8
  _QWORD *v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  MSG Msg; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v22; // [rsp+98h] [rbp-70h] BYREF
  __m128i v23; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v24; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-40h]
  _QWORD v26[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v28; // [rsp+F0h] [rbp-18h]
  _QWORD Src[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v30; // [rsp+108h] [rbp+0h]
  unsigned __int64 v31; // [rsp+110h] [rbp+8h]
  WCHAR Buffer[128]; // [rsp+118h] [rbp+10h] BYREF
  wchar_t v33[256]; // [rsp+218h] [rbp+110h] BYREF

  v2 = CoInitializeEx(0, 2u);
  if ( v2 >= 0 )
  {
    *a1[3] = 2;
    v3 = *((_BYTE *)a1 + 40);
    if ( v3 == 4 )
    {
      v4 = L"<MSQAThread|ERR|SNI> MSQAUseInteractive return status: %u.\n";
      if ( LoadStringW(g_hinstance_language, *((_DWORD *)a1 + 11), Buffer, 128) )
        swprintf(v33, 0x80u, Buffer, a1[6]);
      DesktopWindow = GetDesktopWindow();
      SOSThreadId = GetSOSThreadId();
      v7 = ((__int64 (__fastcall *)(_QWORD, __int64 (__fastcall *)(), _QWORD, HWND, _QWORD, wchar_t *, _DWORD, _DWORD, _QWORD))qword_1005D9020)(
             *a1,
             MSQAThread_::_2_::Handler::UIComplete,
             SOSThreadId,
             DesktopWindow,
             0,
             v33,
             0,
             0,
             0);
      *a1[3] = 27;
      if ( v7 )
      {
        *a1[4] = GetLastError();
        if ( (bidGblFlags & 2) == 0 || !off_1005E6400 )
          goto LABEL_69;
        v8 = off_1005E6400;
        v9 = 476160;
LABEL_68:
        bidTraceW(0, v9, v8, *a1[4]);
LABEL_69:
        CoUninitialize();
        return 0;
      }
      ReleaseCapture();
      while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      *a1[3] = 28;
    }
    else
    {
      v4 = L"<MSQAThread|ERR|SNI> MSQAUseWindowsAuthentication return status: %u.\n";
      if ( v3 == 3 )
      {
        v4 = L"<MSQAThread|ERR|SNI> MSQAUseUsernamePassword return status: %u.\n";
        v10 = a1[1];
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v24) = 0;
        v11 = -1;
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)v10 + v12) );
        std::wstring::assign(&v24);
        v30 = 0;
        v31 = 15;
        LOBYTE(Src[0]) = 0;
        std::string::_Construct<unsigned short *>(Src);
        v13 = a1[2];
        v23 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v22) = 0;
        do
          ++v11;
        while ( *((_WORD *)v13 + v11) );
        std::wstring::assign(&v22);
        v27 = 0;
        v28 = 15;
        LOBYTE(v26[0]) = 0;
        std::string::_Construct<unsigned short *>(v26);
        v14 = v26;
        if ( v28 >= 0x10 )
          v14 = (_QWORD *)v26[0];
        v15 = Src;
        if ( v31 >= 0x10 )
          v15 = (_QWORD *)Src[0];
        ((void (__fastcall *)(_QWORD, _QWORD *, _QWORD *))qword_1005D9000)(*a1, v15, v14);
        *a1[3] = 18;
        if ( v28 >= 0x10 )
        {
          v16 = v26[0];
          if ( v28 + 1 >= 0x1000 )
          {
            if ( (v26[0] & 0x1F) != 0 || (v16 = *(_QWORD *)(v26[0] - 8LL), v16 >= v26[0]) || v26[0] - v16 - 8 > 0x1F )
              _invalid_parameter_noinfo_noreturn();
          }
          if ( v16 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
        }
        v27 = 0;
        v28 = 15;
        LOBYTE(v26[0]) = 0;
        if ( v23.m128i_i64[1] >= 8uLL )
        {
          v17 = v22;
          if ( (unsigned __int64)(v23.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
            || (unsigned __int64)(2 * (v23.m128i_i64[1] + 1)) >= 0x1000
            && ((v22 & 0x1F) != 0 || (v17 = *(_QWORD *)(v22 - 8), v17 >= v22) || v22 - v17 - 8 > 0x1F) )
          {
            _invalid_parameter_noinfo_noreturn();
          }
          if ( v17 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
        }
        v23 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v22) = 0;
        if ( v31 >= 0x10 )
        {
          v18 = Src[0];
          if ( v31 + 1 >= 0x1000 )
          {
            if ( (Src[0] & 0x1F) != 0 || (v18 = *(_QWORD *)(Src[0] - 8LL), v18 >= Src[0]) || Src[0] - v18 - 8 > 0x1F )
              _invalid_parameter_noinfo_noreturn();
          }
          if ( v18 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
        }
        v30 = 0;
        v31 = 15;
        LOBYTE(Src[0]) = 0;
        if ( si128.m128i_i64[1] >= 8uLL )
        {
          v19 = v24;
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
            || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
            && ((v24 & 0x1F) != 0 || (v19 = *(_QWORD *)(v24 - 8), v19 >= v24) || v24 - v19 - 8 > 0x1F) )
          {
            _invalid_parameter_noinfo_noreturn();
          }
          if ( v19 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
        }
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v24) = 0;
      }
      else if ( v3 == 2 || v3 == 1 )
      {
        ((void (__fastcall *)(_QWORD))qword_1005D9008)(*a1);
        *a1[3] = 19;
      }
    }
    *a1[4] = ((__int64 (__fastcall *)(_QWORD))qword_1005D8FF8)(*a1);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_69;
    if ( (dword_1005D9038 & 1) == 0 )
    {
      dword_1005D9038 |= 1u;
      qword_1005E6408 = (__int64)v4;
    }
    if ( !qword_1005E6408 )
      goto LABEL_69;
    v8 = (wchar_t *)qword_1005E6408;
    v9 = 518144;
    goto LABEL_68;
  }
  *a1[4] = v2;
  if ( (bidGblFlags & 2) != 0 && off_1005E63F8[0] )
  {
    _mm_lfence();
    bidTraceW(0, 450560, off_1005E63F8[0], (unsigned int)v2);
  }
  return 0;
}

```

## disassembly

```asm
0x1004450e0  mov     rax, rsp
0x1004450e3  push    rbp
0x1004450e4  push    r13
0x1004450e6  push    r14
0x1004450e8  lea     rbp, [rax-338h]
0x1004450ef  sub     rsp, 420h
0x1004450f6  mov     qword ptr [rsp+430h+var_3D8], 0FFFFFFFFFFFFFFFEh
0x1004450ff  mov     [rax+10h], rbx
0x100445103  mov     [rax+18h], rsi
0x100445107  mov     [rax+20h], rdi
0x10044510b  mov     rax, cs:__security_cookie
0x100445112  xor     rax, rsp
0x100445115  mov     [rbp+330h+var_20], rax
0x10044511c  mov     rdi, rcx
0x10044511f  mov     edx, 2; dwCoInit
0x100445124  xor     ecx, ecx; pvReserved
0x100445126  call    cs:__imp_CoInitializeEx
0x10044512c  xor     r14d, r14d
0x10044512f  test    eax, eax
0x100445131  jns     short loc_100445174
0x100445133  mov     rcx, [rdi+20h]
0x100445137  mov     [rcx], eax
0x100445139  test    byte ptr cs:_bidGblFlags, 2
0x100445140  jz      loc_100445601
0x100445146  mov     rcx, cs:off_1005E63F8; "<MSQAThread|ERR|SNI> CoInitializeEx fai"...
0x10044514d  test    rcx, rcx
0x100445150  jz      loc_100445601
0x100445156  lfence
0x100445159  mov     r9d, eax
0x10044515c  mov     r8, cs:off_1005E63F8; "<MSQAThread|ERR|SNI> CoInitializeEx fai"...
0x100445163  mov     edx, 6E000h
0x100445168  xor     ecx, ecx
0x10044516a  call    _bidTraceW
0x10044516f  jmp     loc_100445601
0x100445174  mov     rax, [rdi+18h]
0x100445178  mov     dword ptr [rax], 2
0x10044517e  mov     al, [rdi+28h]
0x100445181  cmp     al, 4
0x100445183  jnz     loc_10044529D
0x100445189  lea     rsi, aMsqathreadErrS_1; "<MSQAThread|ERR|SNI> MSQAUseInteractive"...
0x100445190  mov     ebx, 80h
0x100445195  mov     r9d, ebx; cchBufferMax
0x100445198  lea     r8, [rbp+330h+Buffer]; lpBuffer
0x10044519c  mov     edx, [rdi+2Ch]; uID
0x10044519f  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x1004451a6  call    cs:__imp_LoadStringW
0x1004451ac  test    eax, eax
0x1004451ae  jz      short loc_1004451C6
0x1004451b0  mov     r9, [rdi+30h]
0x1004451b4  lea     r8, [rbp+330h+Buffer]; Format
0x1004451b8  mov     edx, ebx; BufferCount
0x1004451ba  lea     rcx, [rbp+330h+var_220]; Buffer
0x1004451c1  call    swprintf
0x1004451c6  call    cs:__imp_GetDesktopWindow
0x1004451cc  mov     rbx, rax
0x1004451cf  call    ?GetSOSThreadId@@YAKXZ; GetSOSThreadId(void)
0x1004451d4  mov     r8d, eax
0x1004451d7  mov     [rsp+430h+var_3F0], r14
0x1004451dc  mov     dword ptr [rsp+430h+var_3F8], r14d
0x1004451e1  mov     [rsp+430h+var_400], r14d
0x1004451e6  lea     rax, [rbp+330h+var_220]
0x1004451ed  mov     qword ptr [rsp+430h+var_408], rax
0x1004451f2  mov     [rsp+430h+var_410], r14
0x1004451f7  mov     r9, rbx
0x1004451fa  lea     rdx, _MSQAThread____2___Handler__UIComplete
0x100445201  mov     rcx, [rdi]
0x100445204  mov     rax, cs:qword_1005D9020
0x10044520b  call    cs:__guard_dispatch_icall_fptr
0x100445211  mov     rcx, [rdi+18h]
0x100445215  mov     dword ptr [rcx], 1Bh
0x10044521b  test    eax, eax
0x10044521d  jz      short loc_100445259
0x10044521f  call    cs:__imp_GetLastError
0x100445225  mov     rcx, [rdi+20h]
0x100445229  mov     [rcx], eax
0x10044522b  test    byte ptr cs:_bidGblFlags, 2
0x100445232  jz      loc_1004455FB
0x100445238  mov     rax, cs:off_1005E6400; "<MSQAThread|ERR|SNI> MSQAAcquireToken f"...
0x10044523f  test    rax, rax
0x100445242  jz      loc_1004455FB
0x100445248  mov     r8, cs:off_1005E6400; "<MSQAThread|ERR|SNI> MSQAAcquireToken f"...
0x10044524f  mov     edx, 74400h
0x100445254  jmp     loc_1004455ED
0x100445259  call    cs:__imp_ReleaseCapture
0x10044525f  jmp     short loc_100445277
0x100445261  lea     rcx, [rsp+430h+Msg]; lpMsg
0x100445266  call    cs:__imp_TranslateMessage
0x10044526c  lea     rcx, [rsp+430h+Msg]; lpMsg
0x100445271  call    cs:__imp_DispatchMessageW
0x100445277  xor     r9d, r9d; wMsgFilterMax
0x10044527a  xor     r8d, r8d; wMsgFilterMin
0x10044527d  xor     edx, edx; hWnd
0x10044527f  lea     rcx, [rsp+430h+Msg]; lpMsg
0x100445284  call    cs:__imp_GetMessageW
0x10044528a  test    eax, eax
0x10044528c  jg      short loc_100445261
0x10044528e  mov     rax, [rdi+18h]
0x100445292  mov     dword ptr [rax], 1Ch
0x100445298  jmp     loc_10044559C
0x10044529d  lea     rcx, aMsqathreadErrS_3; "<MSQAThread|ERR|SNI> MSQAUseUsernamePas"...
0x1004452a4  lea     rsi, aMsqathreadErrS; "<MSQAThread|ERR|SNI> MSQAUseWindowsAuth"...
0x1004452ab  cmp     al, 3
0x1004452ad  cmovz   rsi, rcx
0x1004452b1  jnz     loc_10044557A
0x1004452b7  mov     rdx, [rdi+8]
0x1004452bb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1004452c3  movdqu  [rbp+330h+var_370], xmm0
0x1004452c8  mov     word ptr [rbp+330h+var_380], r14w
0x1004452cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1004452d1  mov     r8, rbx
0x1004452d4  inc     r8
0x1004452d7  cmp     [rdx+r8*2], r14w
0x1004452dc  jnz     short loc_1004452D4
0x1004452de  lea     rcx, [rbp+330h+var_380]; void *
0x1004452e2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1004452e7  nop
0x1004452e8  lea     rcx, [rbp+330h+var_380]
0x1004452ec  cmp     qword ptr [rbp+330h+var_370+8], 8
0x1004452f1  cmovnb  rcx, [rbp+330h+var_380]
0x1004452f6  mov     rax, qword ptr [rbp+330h+var_370]
0x1004452fa  lea     r8, [rcx+rax*2]
0x1004452fe  lea     rdx, [rbp+330h+var_380]
0x100445302  cmovnb  rdx, [rbp+330h+var_380]
0x100445307  mov     [rbp+330h+var_330], r14
0x10044530b  mov     r13d, 0Fh
0x100445311  mov     [rbp+330h+var_328], r13
0x100445315  mov     byte ptr [rbp+330h+Src], r14b
0x100445319  mov     r9b, byte ptr [rsp+430h+var_3E0]
0x10044531e  lea     rcx, [rbp+330h+Src]; Src
0x100445322  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x100445327  nop
0x100445328  mov     rdx, [rdi+10h]
0x10044532c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445334  movdqu  [rbp+330h+var_390], xmm0
0x100445339  mov     word ptr [rbp+330h+var_3A0], r14w
0x10044533e  inc     rbx
0x100445341  cmp     [rdx+rbx*2], r14w
0x100445346  jnz     short loc_10044533E
0x100445348  mov     r8, rbx
0x10044534b  lea     rcx, [rbp+330h+var_3A0]; void *
0x10044534f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100445354  nop
0x100445355  lea     rcx, [rbp+330h+var_3A0]
0x100445359  cmp     qword ptr [rbp+330h+var_390+8], 8
0x10044535e  cmovnb  rcx, [rbp+330h+var_3A0]
0x100445363  mov     rax, qword ptr [rbp+330h+var_390]
0x100445367  lea     r8, [rcx+rax*2]
0x10044536b  lea     rdx, [rbp+330h+var_3A0]
0x10044536f  cmovnb  rdx, [rbp+330h+var_3A0]
0x100445374  mov     [rbp+330h+var_350], r14
0x100445378  mov     [rbp+330h+var_348], r13
0x10044537c  mov     byte ptr [rbp+330h+var_360], r14b
0x100445380  mov     r9b, byte ptr [rsp+430h+var_3E0]
0x100445385  lea     rcx, [rbp+330h+var_360]; Src
0x100445389  call    ??$_Construct@PEAG@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::string::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x10044538e  nop
0x10044538f  lea     r8, [rbp+330h+var_360]
0x100445393  cmp     [rbp+330h+var_348], 10h
0x100445398  cmovnb  r8, [rbp+330h+var_360]
0x10044539d  lea     rdx, [rbp+330h+Src]
0x1004453a1  cmp     [rbp+330h+var_328], 10h
0x1004453a6  cmovnb  rdx, [rbp+330h+Src]
0x1004453ab  mov     rcx, [rdi]
0x1004453ae  mov     rax, cs:qword_1005D9000
0x1004453b5  call    cs:__guard_dispatch_icall_fptr
0x1004453bb  mov     rax, [rdi+18h]
0x1004453bf  mov     dword ptr [rax], 12h
0x1004453c5  mov     ebx, 1000h
0x1004453ca  mov     rax, [rbp+330h+var_348]
0x1004453ce  cmp     rax, 10h
0x1004453d2  jb      short loc_10044541E
0x1004453d4  inc     rax
0x1004453d7  mov     rdx, [rbp+330h+var_360]
0x1004453db  mov     rcx, rdx
0x1004453de  cmp     rax, rbx
0x1004453e1  jb      short loc_100445405
0x1004453e3  test    cl, 1Fh
0x1004453e6  jnz     short loc_1004453FE
0x1004453e8  mov     rdx, [rdx-8]
0x1004453ec  cmp     rdx, rcx
0x1004453ef  jnb     short loc_1004453FE
0x1004453f1  sub     rcx, rdx
0x1004453f4  sub     rcx, 8
0x1004453f8  cmp     rcx, 1Fh
0x1004453fc  jbe     short loc_100445405
0x1004453fe  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x100445405  test    rdx, rdx
0x100445408  jz      short loc_10044541E
0x10044540a  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100445411  mov     rax, [rcx]
0x100445414  mov     rax, [rax+68h]
0x100445418  call    cs:__guard_dispatch_icall_fptr
0x10044541e  mov     [rbp+330h+var_350], r14
0x100445422  mov     [rbp+330h+var_348], r13
0x100445426  mov     byte ptr [rbp+330h+var_360], r14b
0x10044542a  mov     r13, 7FFFFFFFFFFFFFFFh
0x100445434  mov     rax, qword ptr [rbp+330h+var_390+8]
0x100445438  cmp     rax, 8
0x10044543c  jb      short loc_10044548D
0x10044543e  inc     rax
0x100445441  mov     rdx, [rbp+330h+var_3A0]
0x100445445  mov     rcx, rdx
0x100445448  cmp     rax, r13
0x10044544b  ja      loc_1004454DA
0x100445451  add     rax, rax
0x100445454  cmp     rax, rbx
0x100445457  jb      short loc_100445474
0x100445459  test    cl, 1Fh
0x10044545c  jnz     short loc_1004454DA
0x10044545e  mov     rdx, [rdx-8]
0x100445462  cmp     rdx, rcx
0x100445465  jnb     short loc_1004454DA
0x100445467  sub     rcx, rdx
0x10044546a  sub     rcx, 8
0x10044546e  cmp     rcx, 1Fh
0x100445472  ja      short loc_1004454DA
0x100445474  test    rdx, rdx
0x100445477  jz      short loc_10044548D
0x100445479  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100445480  mov     rax, [rcx]
0x100445483  mov     rax, [rax+68h]
0x100445487  call    cs:__guard_dispatch_icall_fptr
0x10044548d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445495  movdqu  [rbp+330h+var_390], xmm0
0x10044549a  mov     word ptr [rbp+330h+var_3A0], r14w
0x10044549f  mov     rax, [rbp+330h+var_328]
0x1004454a3  cmp     rax, 10h
0x1004454a7  jb      short loc_1004454FA
0x1004454a9  inc     rax
0x1004454ac  mov     rdx, [rbp+330h+Src]
0x1004454b0  mov     rcx, rdx
0x1004454b3  cmp     rax, rbx
0x1004454b6  jb      short loc_1004454E1
0x1004454b8  test    cl, 1Fh
0x1004454bb  jnz     short loc_1004454D3
0x1004454bd  mov     rdx, [rdx-8]
0x1004454c1  cmp     rdx, rcx
0x1004454c4  jnb     short loc_1004454D3
0x1004454c6  sub     rcx, rdx
0x1004454c9  sub     rcx, 8
0x1004454cd  cmp     rcx, 1Fh
0x1004454d1  jbe     short loc_1004454E1
0x1004454d3  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004454da  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004454e1  test    rdx, rdx
0x1004454e4  jz      short loc_1004454FA
0x1004454e6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004454ed  mov     rax, [rcx]
0x1004454f0  mov     rax, [rax+68h]
0x1004454f4  call    cs:__guard_dispatch_icall_fptr
0x1004454fa  mov     [rbp+330h+var_330], r14
0x1004454fe  mov     [rbp+330h+var_328], 0Fh
0x100445506  mov     byte ptr [rbp+330h+Src], r14b
0x10044550a  mov     rax, qword ptr [rbp+330h+var_370+8]
0x10044550e  cmp     rax, 8
0x100445512  jb      short loc_10044555F
0x100445514  inc     rax
0x100445517  mov     rdx, [rbp+330h+var_380]
0x10044551b  mov     rcx, rdx
0x10044551e  cmp     rax, r13
0x100445521  ja      short loc_100445573
0x100445523  add     rax, rax
0x100445526  cmp     rax, rbx
0x100445529  jb      short loc_100445546
0x10044552b  test    cl, 1Fh
0x10044552e  jnz     short loc_100445573
0x100445530  mov     rdx, [rdx-8]
0x100445534  cmp     rdx, rcx
0x100445537  jnb     short loc_100445573
0x100445539  sub     rcx, rdx
0x10044553c  sub     rcx, 8
0x100445540  cmp     rcx, 1Fh
0x100445544  ja      short loc_100445573
0x100445546  test    rdx, rdx
0x100445549  jz      short loc_10044555F
0x10044554b  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100445552  mov     rax, [rcx]
0x100445555  mov     rax, [rax+68h]
0x100445559  call    cs:__guard_dispatch_icall_fptr
0x10044555f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100445567  movdqu  [rbp+330h+var_370], xmm0
0x10044556c  mov     word ptr [rbp+330h+var_380], r14w
0x100445571  jmp     short loc_10044559C
0x100445573  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x10044557a  cmp     al, 2
0x10044557c  jz      short loc_100445582
0x10044557e  cmp     al, 1
0x100445580  jnz     short loc_10044559C
0x100445582  mov     rcx, [rdi]
0x100445585  mov     rax, cs:qword_1005D9008
0x10044558c  call    cs:__guard_dispatch_icall_fptr
0x100445592  mov     rax, [rdi+18h]
0x100445596  mov     dword ptr [rax], 13h
0x10044559c  mov     rcx, [rdi]
0x10044559f  mov     rax, cs:qword_1005D8FF8
0x1004455a6  call    cs:__guard_dispatch_icall_fptr
0x1004455ac  mov     rcx, [rdi+20h]
0x1004455b0  mov     [rcx], eax
0x1004455b2  test    byte ptr cs:_bidGblFlags, 2
0x1004455b9  jz      short loc_1004455FB
  ... truncated ...
```
