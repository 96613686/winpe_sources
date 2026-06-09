# CAppRecorderPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x18002f060`
- end: `0x18002f31c`
- name: `?Initialize@CAppRecorderPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x18002f060`
- `0x18002f660`
- `0x18003e5a8`
- `0x1800492d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002f259`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002f259`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::Initialize(
        CAppRecorderPlugin *this,
        struct WER_PLUGIN_INIT_IN *a2,
        __int64 a3,
        HINSTANCE a4)
{
  __int64 v7; // rcx
  unsigned int IsAppRecorderEnabled; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8

  if ( a2 )
  {
    if ( wcscmp_0(*(const wchar_t **)a2, L"APPCRASH")
      && wcscmp_0(*(const wchar_t **)a2, L"MoAppCrash")
      && wcscmp_0(*(const wchar_t **)a2, L"AppHangB1")
      && wcscmp_0(*(const wchar_t **)a2, L"AppHangXProcB1")
      && wcscmp_0(*(const wchar_t **)a2, L"MoAppHang")
      && wcscmp_0(*(const wchar_t **)a2, L"MoAppHangXProc") )
    {
      IsAppRecorderEnabled = -2147467263;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return IsAppRecorderEnabled;
      v10 = 11;
LABEL_15:
      WPP_SF_(v9[2], v10, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
      return IsAppRecorderEnabled;
    }
    if ( (unsigned int)(*((_DWORD *)a2 + 63) - 1) > 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    v11 = *((_DWORD *)a2 + 63);
    if ( v11 == 1 )
    {
      if ( !*((_QWORD *)a2 + 33) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v7);
      if ( !*((_QWORD *)a2 + 38) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v7);
      if ( !*((_DWORD *)a2 + 70) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v7);
      *((_DWORD *)this + 10) = *((_DWORD *)a2 + 70);
      v12 = *((_QWORD *)a2 + 33);
      if ( v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(v12 + 2 * v13) );
      }
      else
      {
        v13 = 0;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               (char *)this + 8,
                               v12,
                               v13) )
      {
        IsAppRecorderEnabled = -2147024882;
        goto LABEL_34;
      }
      if ( *((_QWORD *)this + 1) == *((_QWORD *)this + 2) )
      {
        IsAppRecorderEnabled = 0;
LABEL_34:
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return IsAppRecorderEnabled;
        v10 = 12;
        goto LABEL_15;
      }
LABEL_54:
      IsAppRecorderEnabled = CAppRecorderPlugin::IsAppRecorderEnabled(this, *((_DWORD *)this + 10));
      if ( (IsAppRecorderEnabled & 0x80000000) == 0 )
      {
        return 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
          IsAppRecorderEnabled);
      }
      return IsAppRecorderEnabled;
    }
    if ( v11 != 2 )
      goto LABEL_54;
    if ( !*((_QWORD *)a2 + 32) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    if ( !*((_QWORD *)a2 + 33) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    *((_DWORD *)this + 10) = GetProcessId(*((HANDLE *)a2 + 33));
    v14 = *((_QWORD *)a2 + 32);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
    }
    else
    {
      v15 = 0;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            (char *)this + 8,
                            v14,
                            v15) )
    {
      if ( *((_QWORD *)this + 1) != *((_QWORD *)this + 2) )
        goto LABEL_54;
      IsAppRecorderEnabled = 0;
    }
    else
    {
      IsAppRecorderEnabled = -2147024882;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return IsAppRecorderEnabled;
    v10 = 13;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002f060  mov     [rsp+arg_0], rbx
0x18002f065  mov     [rsp+arg_8], rsi
0x18002f06a  push    rdi
0x18002f06b  sub     rsp, 20h
0x18002f06f  xor     esi, esi
0x18002f071  mov     rbx, rdx
0x18002f074  mov     rdi, rcx
0x18002f077  test    rdx, rdx
0x18002f07a  jnz     short loc_18002F0B2
0x18002f07c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f083  lea     rax, WPP_GLOBAL_Control
0x18002f08a  cmp     rcx, rax
0x18002f08d  jz      short loc_18002F0A8
0x18002f08f  test    byte ptr [rcx+1Ch], 1
0x18002f093  jz      short loc_18002F0A8
0x18002f095  mov     rcx, [rcx+10h]
0x18002f099  lea     edx, [rbx+0Ah]
0x18002f09c  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f0a3  call    WPP_SF_
0x18002f0a8  mov     eax, 80070057h
0x18002f0ad  jmp     loc_18002F30C
0x18002f0b2  mov     rcx, [rbx]; String1
0x18002f0b5  lea     rdx, aAppcrash; "APPCRASH"
0x18002f0bc  call    wcscmp_0
0x18002f0c1  test    eax, eax
0x18002f0c3  jz      loc_18002F16C
0x18002f0c9  mov     rcx, [rbx]; String1
0x18002f0cc  lea     rdx, aMoappcrash; "MoAppCrash"
0x18002f0d3  call    wcscmp_0
0x18002f0d8  test    eax, eax
0x18002f0da  jz      loc_18002F16C
0x18002f0e0  mov     rcx, [rbx]; String1
0x18002f0e3  lea     rdx, aApphangb1; "AppHangB1"
0x18002f0ea  call    wcscmp_0
0x18002f0ef  test    eax, eax
0x18002f0f1  jz      short loc_18002F16C
0x18002f0f3  mov     rcx, [rbx]; String1
0x18002f0f6  lea     rdx, aApphangxprocb1; "AppHangXProcB1"
0x18002f0fd  call    wcscmp_0
0x18002f102  test    eax, eax
0x18002f104  jz      short loc_18002F16C
0x18002f106  mov     rcx, [rbx]; String1
0x18002f109  lea     rdx, aMoapphang; "MoAppHang"
0x18002f110  call    wcscmp_0
0x18002f115  test    eax, eax
0x18002f117  jz      short loc_18002F16C
0x18002f119  mov     rcx, [rbx]; String1
0x18002f11c  lea     rdx, aMoapphangxproc; "MoAppHangXProc"
0x18002f123  call    wcscmp_0
0x18002f128  test    eax, eax
0x18002f12a  jz      short loc_18002F16C
0x18002f12c  mov     ebx, 80004001h
0x18002f131  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f138  lea     rax, WPP_GLOBAL_Control
0x18002f13f  cmp     rcx, rax
0x18002f142  jz      loc_18002F30A
0x18002f148  test    byte ptr [rcx+1Ch], 1
0x18002f14c  jz      loc_18002F30A
0x18002f152  mov     edx, 0Bh
0x18002f157  mov     rcx, [rcx+10h]
0x18002f15b  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f162  call    WPP_SF_
0x18002f167  jmp     loc_18002F30A
0x18002f16c  mov     eax, [rbx+0FCh]
0x18002f172  dec     eax
0x18002f174  cmp     eax, 1
0x18002f177  jbe     short loc_18002F17E
0x18002f179  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f17e  mov     eax, [rbx+0FCh]
0x18002f184  cmp     eax, 1
0x18002f187  jnz     loc_18002F22D
0x18002f18d  cmp     [rbx+108h], rsi
0x18002f194  jnz     short loc_18002F19B
0x18002f196  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f19b  cmp     [rbx+130h], rsi
0x18002f1a2  jnz     short loc_18002F1A9
0x18002f1a4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f1a9  cmp     [rbx+118h], esi
0x18002f1af  jnz     short loc_18002F1B6
0x18002f1b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f1b6  mov     eax, [rbx+118h]
0x18002f1bc  mov     [rdi+28h], eax
0x18002f1bf  mov     rdx, [rbx+108h]
0x18002f1c6  test    rdx, rdx
0x18002f1c9  jz      short loc_18002F1DB
0x18002f1cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f1cf  inc     r8
0x18002f1d2  cmp     [rdx+r8*2], si
0x18002f1d7  jnz     short loc_18002F1CF
0x18002f1d9  jmp     short loc_18002F1DE
0x18002f1db  mov     r8, rsi
0x18002f1de  lea     rcx, [rdi+8]
0x18002f1e2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002f1e7  test    al, al
0x18002f1e9  jnz     short loc_18002F1F2
0x18002f1eb  mov     ebx, 8007000Eh
0x18002f1f0  jmp     short loc_18002F202
0x18002f1f2  mov     rax, [rdi+10h]
0x18002f1f6  cmp     [rdi+8], rax
0x18002f1fa  jnz     loc_18002F2C4
0x18002f200  mov     ebx, esi
0x18002f202  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f209  lea     rax, WPP_GLOBAL_Control
0x18002f210  cmp     rcx, rax
0x18002f213  jz      loc_18002F30A
0x18002f219  test    byte ptr [rcx+1Ch], 1
0x18002f21d  jz      loc_18002F30A
0x18002f223  mov     edx, 0Ch
0x18002f228  jmp     loc_18002F157
0x18002f22d  cmp     eax, 2
0x18002f230  jnz     loc_18002F2C4
0x18002f236  cmp     [rbx+100h], rsi
0x18002f23d  jnz     short loc_18002F244
0x18002f23f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f244  cmp     [rbx+108h], rsi
0x18002f24b  jnz     short loc_18002F252
0x18002f24d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f252  mov     rcx, [rbx+108h]; Process
0x18002f259  call    cs:__imp_GetProcessId
0x18002f25f  mov     [rdi+28h], eax
0x18002f262  mov     rdx, [rbx+100h]
0x18002f269  test    rdx, rdx
0x18002f26c  jz      short loc_18002F27E
0x18002f26e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f272  inc     r8
0x18002f275  cmp     [rdx+r8*2], si
0x18002f27a  jnz     short loc_18002F272
0x18002f27c  jmp     short loc_18002F281
0x18002f27e  mov     r8, rsi
0x18002f281  lea     rcx, [rdi+8]
0x18002f285  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002f28a  test    al, al
0x18002f28c  jnz     short loc_18002F295
0x18002f28e  mov     ebx, 8007000Eh
0x18002f293  jmp     short loc_18002F2A1
0x18002f295  mov     rax, [rdi+10h]
0x18002f299  cmp     [rdi+8], rax
0x18002f29d  jnz     short loc_18002F2C4
0x18002f29f  mov     ebx, esi
0x18002f2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2a8  lea     rax, WPP_GLOBAL_Control
0x18002f2af  cmp     rcx, rax
0x18002f2b2  jz      short loc_18002F30A
0x18002f2b4  test    byte ptr [rcx+1Ch], 1
0x18002f2b8  jz      short loc_18002F30A
0x18002f2ba  mov     edx, 0Dh
0x18002f2bf  jmp     loc_18002F157
0x18002f2c4  mov     edx, [rdi+28h]; unsigned int
0x18002f2c7  mov     rcx, rdi; this
0x18002f2ca  call    ?IsAppRecorderEnabled@CAppRecorderPlugin@@AEAAJK@Z; CAppRecorderPlugin::IsAppRecorderEnabled(ulong)
0x18002f2cf  mov     ebx, eax
0x18002f2d1  test    eax, eax
0x18002f2d3  jns     short loc_18002F308
0x18002f2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2dc  lea     rax, WPP_GLOBAL_Control
0x18002f2e3  cmp     rcx, rax
0x18002f2e6  jz      short loc_18002F30A
0x18002f2e8  test    byte ptr [rcx+1Ch], 1
0x18002f2ec  jz      short loc_18002F30A
0x18002f2ee  mov     rcx, [rcx+10h]
0x18002f2f2  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f2f9  mov     edx, 0Eh
0x18002f2fe  mov     r9d, ebx
0x18002f301  call    WPP_SF_d
0x18002f306  jmp     short loc_18002F30A
0x18002f308  mov     ebx, esi
0x18002f30a  mov     eax, ebx
0x18002f30c  mov     rbx, [rsp+28h+arg_0]
0x18002f311  mov     rsi, [rsp+28h+arg_8]
0x18002f316  add     rsp, 20h
0x18002f31a  pop     rdi
0x18002f31b  retn
```
