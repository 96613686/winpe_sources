# container::FilesystemProvider::Details::InitializeSandbox(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180024700`
- end: `0x180024a7c`
- name: `?InitializeSandbox@Details@FilesystemProvider@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180024a84`

## callees

- `0x180002ad0`
- `0x180004c40`
- `0x1800051b0`
- `0x18000bdec`
- `0x18000be30`
- `0x18000ca10`
- `0x180012b10`
- `0x180022c94`
- `0x180023e64`
- `0x180024208`
- `0x180024700`
- `0x1800251e0`
- `0x18002c978`
- `0x18002c9fc`
- `0x18002e14c`
- `0x18002e578`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800247fc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800247fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024948`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800249da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800249da`

## string_xrefs

- `0x18002497e`: `Path: %ws`
- `0x180024a43`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall container::FilesystemProvider::Details::InitializeSandbox(__int64 a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // rax
  _QWORD *v3; // rcx
  void *v4; // rax
  __int64 v5; // rax
  const WCHAR *v6; // rcx
  const char *v7; // r9
  unsigned int v8; // ebx
  __m128i si128; // xmm6
  unsigned int v10; // eax
  wchar_t *v11; // r8
  unsigned __int64 v12; // rcx
  _QWORD *v13; // r9
  int v14; // eax
  const WCHAR *v15; // rcx
  char *FileW; // rax
  char *v17; // rdi
  LPCWSTR *v18; // r8
  unsigned int v19; // eax
  unsigned int dwCreationDisposition; // [rsp+28h] [rbp-E0h]
  __int64 v22; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B8h]
  __int64 v24; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD lpPathName[3]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v26; // [rsp+90h] [rbp-78h]
  _QWORD Src[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v28; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v29; // [rsp+B8h] [rbp-50h]
  LPCWSTR lpFileName[3]; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 v31; // [rsp+D8h] [rbp-30h]
  _OWORD v32[2]; // [rsp+E0h] [rbp-28h] BYREF
  _OWORD v33[2]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v34; // [rsp+120h] [rbp+18h] BYREF
  char v35; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  std::wstring::wstring(Src, a1);
  v1 = v28;
  if ( v28 )
  {
    v2 = Src;
    if ( v29 > 7 )
      v2 = (_QWORD *)Src[0];
    if ( *((_WORD *)v2 + v28 - 1) != 92 )
    {
      v3 = Src;
      if ( v29 == v28 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
      }
      else
      {
        ++v28;
        if ( v29 > 7 )
          v3 = (_QWORD *)Src[0];
        *(_DWORD *)((char *)v3 + 2 * v1) = 92;
      }
    }
  }
  std::wstring::append(Src, L"WcSandboxState");
  v4 = (void *)std::wstring::wstring(v32, Src);
  v5 = std::wstring::append(v4, L"\\Hives");
  *(_OWORD *)&lpPathName[1] = 0;
  v26 = 0;
  *(_OWORD *)&lpPathName[1] = *(_OWORD *)v5;
  v26 = *(_OWORD *)(v5 + 16);
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 7;
  *(_WORD *)v5 = 0;
  std::wstring::~wstring(v32);
  v6 = (const WCHAR *)&lpPathName[1];
  if ( *((_QWORD *)&v26 + 1) > 7u )
    v6 = (const WCHAR *)lpPathName[1];
  if ( !CreateDirectoryW(v6, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
      v7);
  v8 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v33[0] = 0;
    v33[1] = si128;
    LOWORD(v33[0]) = 0;
    v34 = 0;
    v35 = 1;
    v10 = ORCreateHiveEx(&v34, 1);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7F6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
        (const char *)v10,
        dwCreationDisposition);
    v11 = off_180036CB0[v8];
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v26 < v12 )
      std::_Xlen_string();
    v13 = &lpPathName[1];
    if ( *((_QWORD *)&v26 + 1) > 7u )
      v13 = (_QWORD *)lpPathName[1];
    std::wstring::wstring(lpFileName, v26, v11, v13, v26, v11, v12);
    v23 = -1;
    if ( v8 == 1 )
    {
      LODWORD(v22) = 1;
      memset(v32, 0, sizeof(v32));
      std::wstring::_Construct<1,unsigned short const *>(v32);
      v14 = std::wstring::wstring(&v24, v32);
      OfflineHiveLib::SetValueRecursively(v34, v14, 4, (unsigned int)&v22, 4);
      std::wstring::~wstring(v32);
    }
    v15 = (const WCHAR *)lpFileName;
    if ( v31 > 7 )
      v15 = lpFileName[0];
    FileW = (char *)CreateFileW(v15, 0x40000000u, 1u, 0, 1u, 0x2000000u, 0);
    v17 = FileW;
    v23 = (__int64)FileW;
    v18 = lpFileName;
    if ( v31 > 7 )
      v18 = (LPCWSTR *)lpFileName[0];
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
      (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
      (bool)"Path: %ws",
      (const char *)v18);
    v19 = ORSaveHiveToHandle(v34, (_DWORD)v17, 10, 0, v35 != 0);
    if ( v19 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
        (const char *)v19,
        dwCreationDisposition);
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v17);
    std::wstring::~wstring(lpFileName);
    OfflineHiveLib::OfflineHive::~OfflineHive((OfflineHiveLib::OfflineHive *)v33);
    ++v8;
  }
  while ( v8 < 5 );
  std::wstring::~wstring(&lpPathName[1]);
  return std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180024700  mov     rax, rsp
0x180024703  push    rbp
0x180024704  push    rbx
0x180024705  push    rsi
0x180024706  push    rdi
0x180024707  lea     rbp, [rax-68h]
0x18002470b  sub     rsp, 148h
0x180024712  movaps  xmmword ptr [rax-38h], xmm6
0x180024716  mov     rax, cs:__security_cookie
0x18002471d  xor     rax, rsp
0x180024720  mov     qword ptr [rbp+60h+var_38], rax
0x180024724  xor     esi, esi
0x180024726  mov     rdx, rcx
0x180024729  lea     rcx, [rbp+60h+Src]
0x18002472d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180024732  nop
0x180024733  mov     rdx, [rbp+60h+var_B8]
0x180024737  test    rdx, rdx
0x18002473a  jz      short loc_180024785
0x18002473c  mov     r8, [rbp+60h+var_B0]
0x180024740  lea     rax, [rbp+60h+Src]
0x180024744  cmp     r8, 7
0x180024748  cmova   rax, [rbp+60h+Src]
0x18002474d  lea     r9d, [rsi+5Ch]
0x180024751  cmp     [rax+rdx*2-2], r9w
0x180024757  jz      short loc_180024785
0x180024759  mov     rax, r8
0x18002475c  sub     rax, rdx
0x18002475f  lea     rcx, [rbp+60h+Src]; Src
0x180024763  cmp     rax, 1
0x180024767  jb      short loc_180024780
0x180024769  lea     rax, [rdx+1]
0x18002476d  mov     [rbp+60h+var_B8], rax
0x180024771  cmp     r8, 7
0x180024775  cmova   rcx, [rbp+60h+Src]
0x18002477a  mov     [rcx+rdx*2], r9d
0x18002477e  jmp     short loc_180024785
0x180024780  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180024785  lea     rdx, aWcsandboxstate; "WcSandboxState"
0x18002478c  lea     rcx, [rbp+60h+Src]; Src
0x180024790  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180024795  lea     rdx, [rbp+60h+Src]
0x180024799  lea     rcx, [rbp+60h+var_88]
0x18002479d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800247a2  nop
0x1800247a3  lea     rdx, aHives; "\\Hives"
0x1800247aa  mov     rcx, rax; Src
0x1800247ad  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800247b2  xorps   xmm0, xmm0
0x1800247b5  movups  xmmword ptr [rsp+160h+lpPathName+8], xmm0
0x1800247ba  xorps   xmm1, xmm1
0x1800247bd  movdqu  [rbp+60h+var_D8], xmm1
0x1800247c2  movups  xmm0, xmmword ptr [rax]
0x1800247c5  movups  xmmword ptr [rsp+160h+lpPathName+8], xmm0
0x1800247ca  movups  xmm1, xmmword ptr [rax+10h]
0x1800247ce  movups  [rbp+60h+var_D8], xmm1
0x1800247d2  mov     [rax+10h], rsi
0x1800247d6  mov     qword ptr [rax+18h], 7
0x1800247de  mov     [rax], si
0x1800247e1  lea     rcx, [rbp+60h+var_88]
0x1800247e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800247ea  lea     rcx, [rsp+160h+lpPathName+8]
0x1800247ef  cmp     qword ptr [rbp+60h+var_D8+8], 7
0x1800247f4  cmova   rcx, qword ptr [rsp+160h+lpPathName+8]; lpPathName
0x1800247fa  xor     edx, edx; lpSecurityAttributes
0x1800247fc  call    cs:__imp_CreateDirectoryW
0x180024803  nop     dword ptr [rax+rax+00h]
0x180024808  mov     rcx, [rbp+68h]; this
0x18002480c  test    eax, eax
0x18002480e  jz      loc_180024A55
0x180024814  mov     ebx, esi
0x180024816  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002481e  xorps   xmm0, xmm0
0x180024821  movups  [rbp+60h+var_68], xmm0
0x180024825  movdqu  [rbp+60h+var_58], xmm6
0x18002482a  mov     word ptr [rbp+60h+var_68], si
0x18002482e  mov     [rbp+60h+var_48], rsi
0x180024832  mov     [rbp+60h+var_40], 1
0x180024836  mov     edx, 1
0x18002483b  lea     rcx, [rbp+60h+var_48]
0x18002483f  call    ORCreateHiveEx
0x180024844  mov     rcx, [rbp+68h]; this
0x180024848  test    eax, eax
0x18002484a  jnz     loc_180024A40
0x180024850  mov     eax, ebx
0x180024852  lea     r8, off_180036CB0; "\\Software_Delta"
0x180024859  mov     r8, [r8+rax*8]
0x18002485d  mov     rdx, qword ptr [rbp+60h+var_D8]
0x180024861  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024865  inc     rcx
0x180024868  cmp     [r8+rcx*2], si
0x18002486d  jnz     short loc_180024865
0x18002486f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180024879  sub     rax, rdx
0x18002487c  cmp     rax, rcx
0x18002487f  jb      loc_180024A3A
0x180024885  lea     r9, [rsp+160h+lpPathName+8]
0x18002488a  cmp     qword ptr [rbp+60h+var_D8+8], 7
0x18002488f  cmova   r9, qword ptr [rsp+160h+lpPathName+8]
0x180024895  mov     [rsp+30h], rcx
0x18002489a  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], r8
0x18002489f  mov     qword ptr [rsp+160h+dwCreationDisposition], rdx
0x1800248a4  lea     rcx, [rbp+60h+lpFileName]
0x1800248a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800248ad  nop
0x1800248ae  mov     [rsp+160h+var_118], 0FFFFFFFFFFFFFFFFh
0x1800248b7  cmp     ebx, 1
0x1800248ba  jnz     short loc_180024919
0x1800248bc  mov     dword ptr [rsp+160h+var_120], ebx
0x1800248c0  xorps   xmm0, xmm0
0x1800248c3  movups  [rbp+60h+var_88], xmm0
0x1800248c7  xorps   xmm1, xmm1
0x1800248ca  movdqu  [rbp+60h+var_78], xmm1
0x1800248cf  lea     r8d, [rbx+3Eh]
0x1800248d3  lea     rdx, aControlset001C; "ControlSet001\\Control\\Windows Contain"...
0x1800248da  lea     rcx, [rbp+60h+var_88]
0x1800248de  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800248e3  nop
0x1800248e4  lea     rdx, [rbp+60h+var_88]
0x1800248e8  lea     rcx, [rsp+58h]
0x1800248ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800248f2  mov     [rsp+160h+dwCreationDisposition], 4
0x1800248fa  lea     r9, [rsp+160h+var_120]
0x1800248ff  lea     r8d, [rbx+3]
0x180024903  mov     rdx, rax
0x180024906  mov     rcx, [rbp+60h+var_48]
0x18002490a  call    OfflineHiveLib__SetValueRecursively
0x18002490f  nop
0x180024910  lea     rcx, [rbp+60h+var_88]
0x180024914  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024919  lea     rcx, [rbp+60h+lpFileName]
0x18002491d  cmp     [rbp+60h+var_90], 7
0x180024922  cmova   rcx, [rbp+60h+lpFileName]; lpFileName
0x180024927  mov     [rsp+30h], rsi; hTemplateFile
0x18002492c  mov     [rsp+160h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180024934  mov     [rsp+160h+dwCreationDisposition], 1; dwCreationDisposition
0x18002493c  xor     r9d, r9d; lpSecurityAttributes
0x18002493f  mov     edx, 40000000h; dwDesiredAccess
0x180024944  lea     r8d, [r9+1]; dwShareMode
0x180024948  call    cs:__imp_CreateFileW
0x18002494f  nop     dword ptr [rax+rax+00h]
0x180024954  mov     rdi, rax
0x180024957  mov     [rsp+160h+var_118], rax
0x18002495c  lea     r8, [rbp+60h+lpFileName]
0x180024960  cmp     [rbp+60h+var_90], 7
0x180024965  cmova   r8, [rbp+60h+lpFileName]
0x18002496a  lea     rcx, [rax-1]
0x18002496e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180024972  setnbe  dl
0x180024975  mov     rcx, [rbp+68h]; this
0x180024979  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], r8; char *
0x18002497e  lea     rax, aPathWs; "Path: %ws"
0x180024985  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; bool
0x18002498a  movzx   r9d, dl; char *
0x18002498e  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\container"...
0x180024995  mov     edx, 99h; void *
0x18002499a  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18002499f  nop
0x1800249a0  mov     eax, esi
0x1800249a2  cmp     [rbp+60h+var_40], sil
0x1800249a6  setnz   al
0x1800249a9  mov     [rsp+160h+dwCreationDisposition], eax; unsigned int
0x1800249ad  xor     r9d, r9d
0x1800249b0  lea     r8d, [r9+0Ah]
0x1800249b4  mov     rdx, rdi
0x1800249b7  mov     rcx, [rbp+60h+var_48]
0x1800249bb  call    ORSaveHiveToHandle
0x1800249c0  nop
0x1800249c1  mov     rcx, [rbp+68h]; this
0x1800249c5  test    eax, eax
0x1800249c7  jnz     loc_180024A67
0x1800249cd  lea     rax, [rdi-1]
0x1800249d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800249d5  ja      short loc_1800249E7
0x1800249d7  mov     rcx, rdi; hObject
0x1800249da  call    cs:__imp_CloseHandle
0x1800249e1  nop     dword ptr [rax+rax+00h]
0x1800249e6  nop
0x1800249e7  lea     rcx, [rbp+60h+lpFileName]
0x1800249eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800249f0  nop
0x1800249f1  lea     rcx, [rbp+60h+var_68]; this
0x1800249f5  call    ??1OfflineHive@OfflineHiveLib@@QEAA@XZ; OfflineHiveLib::OfflineHive::~OfflineHive(void)
0x1800249fa  inc     ebx
0x1800249fc  cmp     ebx, 5
0x1800249ff  jb      loc_18002481E
0x180024a05  lea     rcx, [rsp+160h+lpPathName+8]
0x180024a0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024a0f  nop
0x180024a10  lea     rcx, [rbp+60h+Src]
0x180024a14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024a19  mov     rcx, qword ptr [rbp+60h+var_38]
0x180024a1d  xor     rcx, rsp; StackCookie
0x180024a20  call    __security_check_cookie
0x180024a25  movaps  xmm6, [rsp+160h+var_38+8]
0x180024a2d  add     rsp, 148h
0x180024a34  pop     rdi
0x180024a35  pop     rsi
0x180024a36  pop     rbx
0x180024a37  pop     rbp
0x180024a38  retn
0x180024a3a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180024a40  mov     r9d, eax; char *
0x180024a43  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\registry"...
0x180024a4a  mov     edx, 7F6h; void *
0x180024a4f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180024a55  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\container"...
0x180024a5c  mov     edx, 76h ; 'v'; void *
0x180024a61  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180024a67  mov     r9d, eax; char *
0x180024a6a  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\container"...
0x180024a71  mov     edx, 9Bh; void *
0x180024a76  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
