# win_musl::CreateTemporaryFileName(void)

- ea: `0x180053328`
- end: `0x180053684`
- name: `?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `860`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180052f98`
- `0x1800a9638`

## callees

- `0x180017320`
- `0x180019410`
- `0x180031600`
- `0x180053328`
- `0x1800593d0`
- `0x1800629f8`
- `0x1800786a4`
- `0x18007acf0`
- `0x1800cd1c4`
- `0x1800df84c`
- `0x1800df8a8`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005350e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005350e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18005339f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18005339f`

## string_xrefs

- `0x180053398`: `windows.storage.dll`
- `0x180053424`: `\Temp\Microsoft\OPC`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
__int64 __fastcall win_musl::CreateTemporaryFileName(__int64 a1)
{
  HMODULE LibraryW; // rax
  HINSTANCE v3; // rdx
  HMODULE v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  _WORD *v8; // rcx
  PVOID *v9; // rdx
  void **v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rbx
  void *v13; // rcx
  __int64 v14; // rbx
  void *v15; // rsi
  _WORD *v17; // [rsp+38h] [rbp-89h] BYREF
  _QWORD v18[4]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v19[8]; // [rsp+60h] [rbp-61h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-59h]
  __int64 v21; // [rsp+78h] [rbp-49h]
  unsigned __int64 v22; // [rsp+80h] [rbp-41h]
  _BYTE v23[8]; // [rsp+88h] [rbp-39h] BYREF
  void *v24; // [rsp+90h] [rbp-31h]
  __int64 v25; // [rsp+A0h] [rbp-21h]
  unsigned __int64 v26; // [rsp+A8h] [rbp-19h]
  _BYTE v27[8]; // [rsp+B0h] [rbp-11h] BYREF
  void *v28; // [rsp+B8h] [rbp-9h]
  __int64 v29; // [rsp+C8h] [rbp+7h]
  unsigned __int64 v30; // [rsp+D0h] [rbp+Fh]
  _BYTE v31[8]; // [rsp+D8h] [rbp+17h] BYREF
  void *v32; // [rsp+E0h] [rbp+1Fh]
  __int64 v33; // [rsp+F0h] [rbp+2Fh]
  unsigned __int64 v34; // [rsp+F8h] [rbp+37h]

  v18[2] = -2;
  v18[0] = a1;
  if ( !byte_1801C5078 )
  {
    v18[0] = &CriticalSection;
    win_musl::CriticalSection::Enter((win_musl::CriticalSection *)&CriticalSection);
    if ( byte_1801C5078 )
    {
LABEL_30:
      win_musl::Locker<win_musl::CriticalSection *>::~Locker<win_musl::CriticalSection *>(v18);
      goto LABEL_31;
    }
    LibraryW = LoadLibraryW(L"windows.storage.dll");
    v4 = 0;
    if ( LibraryW )
      v4 = LibraryW;
    v18[3] = v4;
    win_musl::InitializeFolderFunctions(v4, v3);
    if ( !qword_1801C5070 )
    {
LABEL_28:
      byte_1801C5078 = 1;
      if ( v4 )
        FreeLibrary(v4);
      goto LABEL_30;
    }
    v17 = 0;
    v5 = qword_1801C5070(&FOLDERID_LocalAppDataLow, 0x8000, 0, &v17);
    v7 = v5;
    v8 = v17;
    if ( (v5 & 0x80000000) == 0 && v17 && *v17 )
    {
      std::wstring::assign(&qword_1801C4DF8, v17, v6, v5);
      if ( qword_1801C5068 )
      {
        std::wstring::append(&qword_1801C4DF8, L"\\Temp\\Microsoft\\OPC");
        v10 = &qword_1801C4E00;
        if ( (unsigned __int64)qword_1801C4E18 >= 8 )
          v10 = (void **)qword_1801C4E00;
        v11 = ((__int64 (__fastcall *)(_QWORD, void **, _QWORD))qword_1801C5068)(0, v10, 0);
        if ( v11 && v11 != 80 && v11 != 183 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids, v11);
          std::wstring::assign(&qword_1801C4DF8, v17, v6, v7);
        }
      }
      byte_1801C4DB4 = 1;
    }
    else
    {
      v9 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_24:
        if ( v8 )
        {
          if ( win_musl::close_sh_free::pSHFree )
            win_musl::close_sh_free::pSHFree(v8, v9, v6, v7);
          v17 = 0;
        }
        goto LABEL_28;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids, v5);
    }
    v8 = v17;
    goto LABEL_24;
  }
LABEL_31:
  if ( byte_1801C4DB4 )
  {
    v12 = std::wstring::wstring(v23, L".tmp");
    std::wstring::wstring(v19, L"DDT");
    win_musl::CreateTemporaryFileName(a1, &qword_1801C4DF8, v19, v12);
    if ( v22 >= 8 )
      operator delete(Block[0]);
    v22 = 7;
    v21 = 0;
    LOWORD(Block[0]) = 0;
    if ( v26 >= 8 )
    {
      v13 = v24;
LABEL_44:
      operator delete(v13);
    }
  }
  else
  {
    *(_OWORD *)Block = 0;
    v21 = 0;
    win_musl::CreateTemporaryPath(v19);
    v14 = std::wstring::wstring(v23, L".tmp");
    std::wstring::wstring(v31, L"DDT");
    v15 = Block[0];
    std::wstring::wstring(v27, Block[0]);
    win_musl::CreateTemporaryFileName(a1, v27, v31, v14);
    if ( v30 >= 8 )
      operator delete(v28);
    v30 = 7;
    v29 = 0;
    LOWORD(v28) = 0;
    if ( v34 >= 8 )
      operator delete(v32);
    v34 = 7;
    v33 = 0;
    LOWORD(v32) = 0;
    if ( v26 >= 8 )
      operator delete(v24);
    v26 = 7;
    v25 = 0;
    LOWORD(v24) = 0;
    if ( v15 )
    {
      v13 = v15;
      goto LABEL_44;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180053328  mov     rax, rsp
0x18005332b  push    rbp
0x18005332c  push    rdi
0x18005332d  push    r14
0x18005332f  lea     rbp, [rax-5Fh]
0x180053333  sub     rsp, 100h
0x18005333a  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFEh
0x180053342  mov     [rax+10h], rbx
0x180053346  mov     [rax+18h], rsi
0x18005334a  mov     rax, cs:__security_cookie
0x180053351  xor     rax, rsp
0x180053354  mov     [rbp+57h+var_18], rax
0x180053358  mov     rdi, rcx
0x18005335b  mov     [rsp+110h+var_D8], rcx
0x180053360  xor     r14d, r14d
0x180053363  mov     al, cs:byte_1801C5078
0x180053369  lea     rsi, qword_1801C4DF8
0x180053370  test    al, al
0x180053372  jnz     loc_18005351F
0x180053378  lea     rcx, CriticalSection; this
0x18005337f  mov     [rsp+110h+var_D8], rcx
0x180053384  call    ?Enter@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Enter(void)
0x180053389  nop
0x18005338a  mov     al, cs:byte_1801C5078
0x180053390  test    al, al
0x180053392  jnz     loc_180053515
0x180053398  lea     rcx, LibFileName; "windows.storage.dll"
0x18005339f  call    cs:__imp_LoadLibraryW
0x1800533a5  mov     ebx, r14d
0x1800533a8  test    rax, rax
0x1800533ab  cmovnz  rbx, rax
0x1800533af  mov     [rbp+57h+var_C0], rbx
0x1800533b3  mov     rcx, rbx; hModule
0x1800533b6  call    ?InitializeFolderFunctions@win_musl@@YAXPEAUHINSTANCE__@@@Z; win_musl::InitializeFolderFunctions(HINSTANCE__ *)
0x1800533bb  mov     rax, cs:qword_1801C5070
0x1800533c2  test    rax, rax
0x1800533c5  jz      loc_1800534FF
0x1800533cb  mov     [rsp+110h+var_E0], r14
0x1800533d0  lea     r9, [rsp+110h+var_E0]
0x1800533d5  xor     r8d, r8d
0x1800533d8  mov     edx, 8000h
0x1800533dd  lea     rcx, FOLDERID_LocalAppDataLow
0x1800533e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533e9  mov     r9d, eax
0x1800533ec  mov     rcx, [rsp+110h+var_E0]
0x1800533f1  test    eax, eax
0x1800533f3  js      loc_1800534B1
0x1800533f9  test    rcx, rcx
0x1800533fc  jz      loc_1800534B1
0x180053402  cmp     [rcx], r14w
0x180053406  jz      loc_1800534B1
0x18005340c  mov     rdx, rcx
0x18005340f  mov     rcx, rsi
0x180053412  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x180053417  cmp     cs:qword_1801C5068, r14
0x18005341e  jz      loc_1800534A8
0x180053424  lea     rdx, ?gc_TempFileFolder@win_musl@@3QB_WB; "\\Temp\\Microsoft\\OPC"
0x18005342b  mov     rcx, rsi
0x18005342e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x180053433  lea     rdx, qword_1801C4E00
0x18005343a  cmp     cs:qword_1801C4E18, 8
0x180053442  cmovnb  rdx, cs:qword_1801C4E00
0x18005344a  xor     r8d, r8d
0x18005344d  xor     ecx, ecx
0x18005344f  mov     rax, cs:qword_1801C5068
0x180053456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005345b  test    eax, eax
0x18005345d  jz      short loc_1800534A8
0x18005345f  cmp     eax, 50h ; 'P'
0x180053462  jz      short loc_1800534A8
0x180053464  cmp     eax, 0B7h
0x180053469  jz      short loc_1800534A8
0x18005346b  lea     rdx, WPP_GLOBAL_Control
0x180053472  mov     rcx, cs:WPP_GLOBAL_Control
0x180053479  cmp     rcx, rdx
0x18005347c  jz      short loc_18005349B
0x18005347e  test    byte ptr [rcx+44h], 1
0x180053482  jz      short loc_18005349B
0x180053484  lea     edx, [r14+0Bh]
0x180053488  mov     r9d, eax
0x18005348b  lea     r8, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids
0x180053492  mov     rcx, [rcx+38h]
0x180053496  call    WPP_SF_d
0x18005349b  mov     rdx, [rsp+110h+var_E0]
0x1800534a0  mov     rcx, rsi
0x1800534a3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x1800534a8  mov     cs:byte_1801C4DB4, 1
0x1800534af  jmp     short loc_1800534DF
0x1800534b1  lea     rdx, WPP_GLOBAL_Control
0x1800534b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800534bf  cmp     rax, rdx
0x1800534c2  jz      short loc_1800534E4
0x1800534c4  test    byte ptr [rax+44h], 1
0x1800534c8  jz      short loc_1800534E4
0x1800534ca  mov     edx, 0Ah
0x1800534cf  lea     r8, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids
0x1800534d6  mov     rcx, [rax+38h]
0x1800534da  call    WPP_SF_d
0x1800534df  mov     rcx, [rsp+110h+var_E0]
0x1800534e4  test    rcx, rcx
0x1800534e7  jz      short loc_1800534FF
0x1800534e9  mov     rax, cs:?pSHFree@close_sh_free@win_musl@@2P6AXPEAX@ZEA; void (*win_musl::close_sh_free::pSHFree)(void *)
0x1800534f0  test    rax, rax
0x1800534f3  jz      short loc_1800534FA
0x1800534f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534fa  mov     [rsp+110h+var_E0], r14
0x1800534ff  mov     cs:byte_1801C5078, 1
0x180053506  test    rbx, rbx
0x180053509  jz      short loc_180053515
0x18005350b  mov     rcx, rbx; hLibModule
0x18005350e  call    cs:__imp_FreeLibrary
0x180053514  nop
0x180053515  lea     rcx, [rsp+110h+var_D8]
0x18005351a  call    ??1?$Locker@PEAVCriticalSection@win_musl@@@win_musl@@QEAA@XZ; win_musl::Locker<win_musl::CriticalSection *>::~Locker<win_musl::CriticalSection *>(void)
0x18005351f  mov     al, cs:byte_1801C4DB4
0x180053525  test    al, al
0x180053527  jz      short loc_180053596
0x180053529  lea     rdx, aTmp; ".tmp"
0x180053530  lea     rcx, [rbp+57h+var_90]
0x180053534  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180053539  mov     rbx, rax
0x18005353c  lea     rdx, aDdt; "DDT"
0x180053543  lea     rcx, [rbp+57h+var_B8]
0x180053547  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005354c  nop
0x18005354d  mov     r9, rbx
0x180053550  lea     r8, [rbp+57h+var_B8]
0x180053554  mov     rdx, rsi
0x180053557  mov     rcx, rdi
0x18005355a  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@00@Z; win_musl::CreateTemporaryFileName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18005355f  nop
0x180053560  cmp     [rbp+57h+var_98], 8
0x180053565  jb      short loc_180053570
0x180053567  mov     rcx, [rbp+57h+Block]; Block
0x18005356b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053570  mov     ebx, 7
0x180053575  mov     [rbp+57h+var_98], rbx
0x180053579  mov     [rbp+57h+var_A0], r14
0x18005357d  mov     word ptr [rbp+57h+Block], r14w
0x180053582  cmp     [rbp+57h+var_70], 8
0x180053587  jb      loc_18005365D
0x18005358d  mov     rcx, [rbp+57h+var_88]
0x180053591  jmp     loc_180053658
0x180053596  xorps   xmm0, xmm0
0x180053599  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x18005359e  mov     [rbp+57h+var_A0], r14
0x1800535a2  lea     rcx, [rbp+57h+var_B8]
0x1800535a6  call    ?CreateTemporaryPath@win_musl@@YAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@@Z; win_musl::CreateTemporaryPath(std::vector<wchar_t> &)
0x1800535ab  lea     rdx, aTmp; ".tmp"
0x1800535b2  lea     rcx, [rbp+57h+var_90]
0x1800535b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800535bb  mov     rbx, rax
0x1800535be  lea     rdx, aDdt; "DDT"
0x1800535c5  lea     rcx, [rbp+57h+var_40]
0x1800535c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800535ce  nop
0x1800535cf  mov     rsi, [rbp+57h+Block]
0x1800535d3  mov     rdx, rsi
0x1800535d6  lea     rcx, [rbp+57h+var_68]
0x1800535da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800535df  nop
0x1800535e0  mov     r9, rbx
0x1800535e3  lea     r8, [rbp+57h+var_40]
0x1800535e7  lea     rdx, [rbp+57h+var_68]
0x1800535eb  mov     rcx, rdi
0x1800535ee  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@00@Z; win_musl::CreateTemporaryFileName(std::wstring const &,std::wstring const &,std::wstring const &)
0x1800535f3  nop
0x1800535f4  cmp     [rbp+57h+var_48], 8
0x1800535f9  jb      short loc_180053604
0x1800535fb  mov     rcx, [rbp+57h+var_60]; Block
0x1800535ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053604  mov     ebx, 7
0x180053609  mov     [rbp+57h+var_48], rbx
0x18005360d  mov     [rbp+57h+var_50], r14
0x180053611  mov     word ptr [rbp+57h+var_60], r14w
0x180053616  cmp     [rbp+57h+var_20], 8
0x18005361b  jb      short loc_180053626
0x18005361d  mov     rcx, [rbp+57h+var_38]; Block
0x180053621  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053626  mov     [rbp+57h+var_20], rbx
0x18005362a  mov     [rbp+57h+var_28], r14
0x18005362e  mov     word ptr [rbp+57h+var_38], r14w
0x180053633  cmp     [rbp+57h+var_70], 8
0x180053638  jb      short loc_180053643
0x18005363a  mov     rcx, [rbp+57h+var_88]; Block
0x18005363e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053643  mov     [rbp+57h+var_70], rbx
0x180053647  mov     [rbp+57h+var_78], r14
0x18005364b  mov     word ptr [rbp+57h+var_88], r14w
0x180053650  test    rsi, rsi
0x180053653  jz      short loc_18005365D
0x180053655  mov     rcx, rsi; Block
0x180053658  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005365d  mov     rax, rdi
0x180053660  mov     rcx, [rbp+57h+var_18]
0x180053664  xor     rcx, rsp; StackCookie
0x180053667  call    __security_check_cookie
0x18005366c  lea     r11, [rsp+110h+var_10]
0x180053674  mov     rbx, [r11+28h]
0x180053678  mov     rsi, [r11+30h]
0x18005367c  mov     rsp, r11
0x18005367f  pop     r14
0x180053681  pop     rdi
0x180053682  pop     rbp
0x180053683  retn
```
