# CInpagePlugIn::IsWdiHostProcess(void)

- ea: `0x18002a28c`
- end: `0x18002a5f8`
- name: `?IsWdiHostProcess@CInpagePlugIn@@AEAAHXZ`
- size: `876`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x180029f1c`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180007118`
- `0x180009e04`
- `0x180009f00`
- `0x180016414`
- `0x18002a28c`
- `0x18003b2e8`
- `0x18003b790`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a384`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a45c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a384`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a45c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a54e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a52d`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002a3a5`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002a3a5`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18002a50b`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18002a50b`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18002a3cc`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18002a3cc`

## string_xrefs

- `0x18002a43f`: `wdi.dll`

## pseudocode

```c
__int64 __fastcall CInpagePlugIn::IsWdiHostProcess(CInpagePlugIn *this)
{
  unsigned int v2; // esi
  char *Toolhelp32Snapshot; // rbx
  DWORD v4; // eax
  MODULEENTRY32W *p_me; // rcx
  __int64 v6; // rdx
  _BYTE *v7; // rax
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int64 v18; // rax
  DWORD LastError; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  void *v24[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v25[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *v26; // [rsp+40h] [rbp-C0h] BYREF
  char *v27; // [rsp+48h] [rbp-B8h]
  _WORD v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[1088]; // [rsp+60h] [rbp-A0h] BYREF
  MODULEENTRY32W me; // [rsp+4A0h] [rbp+3A0h] BYREF

  v26 = v28;
  v27 = (char *)v28;
  v28[0] = 0;
  v24[0] = v25;
  v24[1] = v25;
  v25[0] = 0;
  memset_0(&me, 0, sizeof(me));
  v2 = 0;
  UtilGetWindowsDirectory(&v26);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                           v24,
                           ((v27 - (_BYTE *)v26) >> 1) + 12)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v24,
                           v26,
                           (v27 - (_BYTE *)v26) >> 1)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v24,
                           L"svchost.exe") )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v21 = 26;
    v22 = 2147942414LL;
LABEL_25:
    WPP_SF_d(v20[2], v21, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids, v22);
    goto LABEL_26;
  }
  if ( (unsigned int)_o__wcsicmp((char *)this + 1088, v24[0]) || !UtilIsSystem() )
    goto LABEL_26;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(8u, *((_DWORD *)this + 10));
  if ( Toolhelp32Snapshot == (char *)-1LL || Toolhelp32Snapshot + 1 == (char *)1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    v21 = 27;
    v22 = LastError;
    goto LABEL_25;
  }
  me.dwSize = 1080;
  if ( Module32FirstW(Toolhelp32Snapshot, &me) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      v24,
      v26,
      (v27 - (_BYTE *)v26) >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v24, L"wdi.dll");
    while ( (unsigned int)_o__wcsicmp(me.szExePath, v24[0]) )
    {
      memset_0(v29, 0, 0x438u);
      p_me = &me;
      v6 = 8;
      v7 = v29;
      do
      {
        v8 = *(_OWORD *)v7;
        v9 = *((_OWORD *)v7 + 1);
        v7 += 128;
        *(_OWORD *)&p_me->dwSize = v8;
        v10 = *((_OWORD *)v7 - 6);
        *(_OWORD *)&p_me->ProccntUsage = v9;
        v11 = *((_OWORD *)v7 - 5);
        *(_OWORD *)&p_me->modBaseSize = v10;
        v12 = *((_OWORD *)v7 - 4);
        *(_OWORD *)p_me->szModule = v11;
        v13 = *((_OWORD *)v7 - 3);
        *(_OWORD *)&p_me->szModule[8] = v12;
        v14 = *((_OWORD *)v7 - 2);
        *(_OWORD *)&p_me->szModule[16] = v13;
        v15 = *((_OWORD *)v7 - 1);
        *(_OWORD *)&p_me->szModule[24] = v14;
        *(_OWORD *)&p_me->szModule[32] = v15;
        p_me = (MODULEENTRY32W *)((char *)p_me + 128);
        --v6;
      }
      while ( v6 );
      v16 = *((_OWORD *)v7 + 1);
      *(_OWORD *)&p_me->dwSize = *(_OWORD *)v7;
      v17 = *((_OWORD *)v7 + 2);
      v18 = *((_QWORD *)v7 + 6);
      *(_OWORD *)&p_me->ProccntUsage = v16;
      *(_OWORD *)&p_me->modBaseSize = v17;
      *(_QWORD *)p_me->szModule = v18;
      me.dwSize = 1080;
      if ( !Module32NextW(Toolhelp32Snapshot, &me) )
        goto LABEL_18;
    }
    v2 = 1;
    *((_DWORD *)this + 456) = 5;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids, v4);
  }
LABEL_18:
  CloseHandle(Toolhelp32Snapshot);
LABEL_26:
  if ( v24[0] != v25 )
    operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v26 != v28 )
    operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
  return v2;
}

```

## disassembly

```asm
0x18002a28c  mov     [rsp-8+arg_8], rbx
0x18002a291  mov     [rsp-8+arg_10], rsi
0x18002a296  push    rbp
0x18002a297  push    rdi
0x18002a298  push    r15
0x18002a29a  lea     rbp, [rsp-7F0h]
0x18002a2a2  sub     rsp, 8F0h
0x18002a2a9  mov     rax, cs:__security_cookie
0x18002a2b0  xor     rax, rsp
0x18002a2b3  mov     [rbp+800h+var_20], rax
0x18002a2ba  lea     rax, [rsp+900h+var_8B0]
0x18002a2bf  mov     rdi, rcx
0x18002a2c2  mov     [rsp+900h+var_8C0], rax
0x18002a2c7  lea     rcx, [rbp+800h+me]; void *
0x18002a2ce  lea     rax, [rsp+900h+var_8B0]
0x18002a2d3  mov     r15d, 438h
0x18002a2d9  mov     [rsp+900h+var_8B8], rax
0x18002a2de  mov     r8d, r15d; Size
0x18002a2e1  xor     eax, eax
0x18002a2e3  xor     edx, edx; Val
0x18002a2e5  mov     [rsp+900h+var_8B0], ax
0x18002a2ea  lea     rax, [rsp+900h+var_8D0]
0x18002a2ef  mov     [rsp+900h+var_8E0], rax
0x18002a2f4  lea     rax, [rsp+900h+var_8D0]
0x18002a2f9  mov     [rsp+900h+var_8D8], rax
0x18002a2fe  xor     eax, eax
0x18002a300  mov     [rsp+900h+var_8D0], ax
0x18002a305  call    memset_0
0x18002a30a  lea     rcx, [rsp+900h+var_8C0]
0x18002a30f  xor     esi, esi
0x18002a311  call    ?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18002a316  mov     rdx, [rsp+900h+var_8B8]
0x18002a31b  lea     rcx, [rsp+900h+var_8E0]
0x18002a320  sub     rdx, [rsp+900h+var_8C0]
0x18002a325  sar     rdx, 1
0x18002a328  add     rdx, 0Ch
0x18002a32c  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18002a331  test    al, al
0x18002a333  jz      loc_18002A565
0x18002a339  mov     r8, [rsp+900h+var_8B8]
0x18002a33e  lea     rcx, [rsp+900h+var_8E0]
0x18002a343  mov     rdx, [rsp+900h+var_8C0]
0x18002a348  sub     r8, rdx
0x18002a34b  sar     r8, 1
0x18002a34e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002a353  test    al, al
0x18002a355  jz      loc_18002A565
0x18002a35b  lea     r8d, [rsi+0Bh]
0x18002a35f  lea     rdx, aSvchostExe; "svchost.exe"
0x18002a366  lea     rcx, [rsp+900h+var_8E0]
0x18002a36b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002a370  test    al, al
0x18002a372  jz      loc_18002A565
0x18002a378  mov     rdx, [rsp+900h+var_8E0]
0x18002a37d  lea     rcx, [rdi+440h]
0x18002a384  call    cs:__imp__o__wcsicmp
0x18002a38a  test    eax, eax
0x18002a38c  jnz     loc_18002A599
0x18002a392  call    ?UtilIsSystem@@YA_NXZ; UtilIsSystem(void)
0x18002a397  test    al, al
0x18002a399  jz      loc_18002A599
0x18002a39f  mov     edx, [rdi+28h]; th32ProcessID
0x18002a3a2  lea     ecx, [rsi+8]; dwFlags
0x18002a3a5  call    cs:__imp_CreateToolhelp32Snapshot
0x18002a3ab  mov     rbx, rax
0x18002a3ae  inc     rax
0x18002a3b1  cmp     rax, 1
0x18002a3b5  jbe     loc_18002A535
0x18002a3bb  lea     rdx, [rbp+800h+me]; lpme
0x18002a3c2  mov     [rbp+800h+me.dwSize], r15d
0x18002a3c9  mov     rcx, rbx; hSnapshot
0x18002a3cc  call    cs:__imp_Module32FirstW
0x18002a3d2  test    eax, eax
0x18002a3d4  jnz     short loc_18002A41F
0x18002a3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3dd  lea     rax, WPP_GLOBAL_Control
0x18002a3e4  cmp     rcx, rax
0x18002a3e7  jz      loc_18002A52A
0x18002a3ed  test    byte ptr [rcx+1Ch], 1
0x18002a3f1  jz      loc_18002A52A
0x18002a3f7  call    cs:__imp_GetLastError
0x18002a3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a404  lea     edx, [rsi+1Ch]
0x18002a407  mov     r9d, eax
0x18002a40a  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002a411  mov     rcx, [rcx+10h]
0x18002a415  call    WPP_SF_d
0x18002a41a  jmp     loc_18002A52A
0x18002a41f  mov     r8, [rsp+900h+var_8B8]
0x18002a424  lea     rcx, [rsp+900h+var_8E0]
0x18002a429  mov     rdx, [rsp+900h+var_8C0]
0x18002a42e  sub     r8, rdx
0x18002a431  sar     r8, 1
0x18002a434  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002a439  mov     r8d, 7
0x18002a43f  lea     rdx, aWdiDll; "wdi.dll"
0x18002a446  lea     rcx, [rsp+900h+var_8E0]
0x18002a44b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002a450  mov     rdx, [rsp+900h+var_8E0]
0x18002a455  lea     rcx, [rbp+800h+me.szExePath]
0x18002a45c  call    cs:__imp__o__wcsicmp
0x18002a462  test    eax, eax
0x18002a464  jz      loc_18002A51B
0x18002a46a  mov     r8, r15; Size
0x18002a46d  lea     rcx, [rsp+900h+var_8A0]; void *
0x18002a472  xor     edx, edx; Val
0x18002a474  call    memset_0
0x18002a479  lea     rcx, [rbp+800h+me]
0x18002a480  mov     edx, 8
0x18002a485  lea     rax, [rsp+900h+var_8A0]
0x18002a48a  movups  xmm0, xmmword ptr [rax]
0x18002a48d  movups  xmm1, xmmword ptr [rax+10h]
0x18002a491  lea     rax, [rax+80h]
0x18002a498  movups  xmmword ptr [rcx], xmm0
0x18002a49b  movups  xmm0, xmmword ptr [rax-60h]
0x18002a49f  movups  xmmword ptr [rcx+10h], xmm1
0x18002a4a3  movups  xmm1, xmmword ptr [rax-50h]
0x18002a4a7  movups  xmmword ptr [rcx+20h], xmm0
0x18002a4ab  movups  xmm0, xmmword ptr [rax-40h]
0x18002a4af  movups  xmmword ptr [rcx+30h], xmm1
0x18002a4b3  movups  xmm1, xmmword ptr [rax-30h]
0x18002a4b7  movups  xmmword ptr [rcx+40h], xmm0
0x18002a4bb  movups  xmm0, xmmword ptr [rax-20h]
0x18002a4bf  movups  xmmword ptr [rcx+50h], xmm1
0x18002a4c3  movups  xmm1, xmmword ptr [rax-10h]
0x18002a4c7  movups  xmmword ptr [rcx+60h], xmm0
0x18002a4cb  movups  xmmword ptr [rcx+70h], xmm1
0x18002a4cf  lea     rcx, [rcx+80h]
0x18002a4d6  sub     rdx, 1
0x18002a4da  jnz     short loc_18002A48A
0x18002a4dc  movups  xmm0, xmmword ptr [rax]
0x18002a4df  lea     rdx, [rbp+800h+me]; lpme
0x18002a4e6  movups  xmm1, xmmword ptr [rax+10h]
0x18002a4ea  movups  xmmword ptr [rcx], xmm0
0x18002a4ed  movups  xmm0, xmmword ptr [rax+20h]
0x18002a4f1  mov     rax, [rax+30h]
0x18002a4f5  movups  xmmword ptr [rcx+10h], xmm1
0x18002a4f9  movups  xmmword ptr [rcx+20h], xmm0
0x18002a4fd  mov     [rcx+30h], rax
0x18002a501  mov     rcx, rbx; hSnapshot
0x18002a504  mov     [rbp+800h+me.dwSize], r15d
0x18002a50b  call    cs:__imp_Module32NextW
0x18002a511  test    eax, eax
0x18002a513  jnz     loc_18002A450
0x18002a519  jmp     short loc_18002A52A
0x18002a51b  mov     esi, 1
0x18002a520  mov     dword ptr [rdi+720h], 5
0x18002a52a  mov     rcx, rbx; hObject
0x18002a52d  call    cs:__imp_CloseHandle
0x18002a533  jmp     short loc_18002A599
0x18002a535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a53c  lea     rax, WPP_GLOBAL_Control
0x18002a543  cmp     rcx, rax
0x18002a546  jz      short loc_18002A599
0x18002a548  test    byte ptr [rcx+1Ch], 1
0x18002a54c  jz      short loc_18002A599
0x18002a54e  call    cs:__imp_GetLastError
0x18002a554  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a55b  mov     edx, 1Bh
0x18002a560  mov     r9d, eax
0x18002a563  jmp     short loc_18002A589
0x18002a565  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a56c  lea     rax, WPP_GLOBAL_Control
0x18002a573  cmp     rcx, rax
0x18002a576  jz      short loc_18002A599
0x18002a578  test    byte ptr [rcx+1Ch], 1
0x18002a57c  jz      short loc_18002A599
0x18002a57e  mov     edx, 1Ah
0x18002a583  mov     r9d, 8007000Eh
0x18002a589  mov     rcx, [rcx+10h]
0x18002a58d  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002a594  call    WPP_SF_d
0x18002a599  mov     rcx, [rsp+900h+var_8E0]; void *
0x18002a59e  lea     rax, [rsp+900h+var_8D0]
0x18002a5a3  cmp     rcx, rax
0x18002a5a6  jz      short loc_18002A5B4
0x18002a5a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a5af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a5b4  mov     rcx, [rsp+900h+var_8C0]; void *
0x18002a5b9  lea     rax, [rsp+900h+var_8B0]
0x18002a5be  cmp     rcx, rax
0x18002a5c1  jz      short loc_18002A5CF
0x18002a5c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a5ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a5cf  mov     eax, esi
0x18002a5d1  mov     rcx, [rbp+800h+var_20]
0x18002a5d8  xor     rcx, rsp; StackCookie
0x18002a5db  call    __security_check_cookie
0x18002a5e0  lea     r11, [rsp+900h+var_10]
0x18002a5e8  mov     rbx, [r11+28h]
0x18002a5ec  mov     rsi, [r11+30h]
0x18002a5f0  mov     rsp, r11
0x18002a5f3  pop     r15
0x18002a5f5  pop     rdi
0x18002a5f6  pop     rbp
0x18002a5f7  retn
```
