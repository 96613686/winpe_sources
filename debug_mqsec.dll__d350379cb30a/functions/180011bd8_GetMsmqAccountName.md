# _GetMsmqAccountName

- ea: `0x180011bd8`
- end: `0x180011df4`
- name: `_GetMsmqAccountName`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800108f0`

## callees

- `0x180002e44`
- `0x180002ff0`
- `0x180003060`
- `0x1800049ac`
- `0x18000b6e0`
- `0x18000b95c`
- `0x18000eb48`
- `0x18000edd8`
- `0x18000ee9c`
- `0x180011638`
- `0x180011bd8`
- `0x180011dfc`
- `0x18001353c`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180011c6b`
- `KERNEL32!LeaveCriticalSection` at `0x180011cdb`
- `KERNEL32!LeaveCriticalSection` at `0x180011dd5`
- `KERNEL32!LeaveCriticalSection` at `0x180011c6b`
- `KERNEL32!LeaveCriticalSection` at `0x180011cdb`
- `KERNEL32!LeaveCriticalSection` at `0x180011dd5`
- `KERNEL32!GetLastError` at `0x180011d46`
- `KERNEL32!GetLastError` at `0x180011d46`

## string_xrefs

- `0x180011d74`: `NT Authority\NetworkService`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void GetMsmqAccountName()
{
  __int64 v0; // rax
  __int64 v1; // rdx
  DWORD LastError; // eax
  _BYTE v3[40]; // [rsp+28h] [rbp-40h] BYREF

  if ( dword_180043308 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180043308);
    if ( dword_180043308 == -1 )
    {
      CCriticalSection::CCriticalSection((CCriticalSection *)&stru_180043310);
      atexit(_GetMsmqAccountName_::_2_::_dynamic_atexit_destructor_for__s_csAccount__);
      Init_thread_footer(&dword_180043308);
    }
  }
  CCriticalSection::Lock((CCriticalSection *)&stru_180043310);
  if ( byte_180043118 )
  {
    LeaveCriticalSection(&stru_180043310);
  }
  else
  {
    GetMsmqAccountNameInternal();
    if ( qword_180042638 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22));
      byte_180043118 = 1;
      LeaveCriticalSection(&stru_180043310);
    }
    else
    {
      v0 = _BuildAccountNameForSid((__int64)v3, g_pNetworkServiceSid);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(
        &g_pwzLocalMsmqAccount,
        v0,
        0,
        -1);
      LOBYTE(v1) = 1;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v3, v1, 0);
      if ( !qword_180042638 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            53,
            &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids,
            LastError);
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(
          &g_pwzLocalMsmqAccount,
          L"NT Authority\\NetworkService",
          27);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22));
      byte_180043118 = 1;
      LeaveCriticalSection(&stru_180043310);
    }
  }
}

```

## disassembly

```asm
0x180011bd8  mov     [rsp+arg_0], rbx
0x180011bdd  push    rdi
0x180011bde  sub     rsp, 60h
0x180011be2  mov     rax, cs:__security_cookie
0x180011be9  xor     rax, rsp
0x180011bec  mov     [rsp+68h+var_18], rax
0x180011bf1  mov     ecx, cs:_tls_index
0x180011bf7  mov     rax, gs:58h
0x180011c00  mov     edx, 4
0x180011c05  mov     rax, [rax+rcx*8]
0x180011c09  lea     rdi, stru_180043310
0x180011c10  mov     eax, [rdx+rax]
0x180011c13  cmp     cs:dword_180043308, eax
0x180011c19  jle     short loc_180011C51
0x180011c1b  lea     rcx, dword_180043308
0x180011c22  call    _Init_thread_header
0x180011c27  cmp     cs:dword_180043308, 0FFFFFFFFh
0x180011c2e  jnz     short loc_180011C51
0x180011c30  mov     rcx, rdi; this
0x180011c33  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x180011c38  lea     rcx, __GetMsmqAccountName____2____dynamic_atexit_destructor_for__s_csAccount__; void (__cdecl *)()
0x180011c3f  call    atexit
0x180011c44  nop
0x180011c45  lea     rcx, dword_180043308
0x180011c4c  call    _Init_thread_footer
0x180011c51  mov     [rsp+68h+var_48], rdi
0x180011c56  mov     rcx, rdi; this
0x180011c59  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180011c5e  nop
0x180011c5f  cmp     cs:byte_180043118, 0
0x180011c66  jz      short loc_180011C77
0x180011c68  mov     rcx, rdi; lpCriticalSection
0x180011c6b  call    cs:__imp_LeaveCriticalSection
0x180011c71  nop
0x180011c72  jmp     loc_180011DDC
0x180011c77  call    _GetMsmqAccountNameInternal
0x180011c7c  cmp     cs:qword_180042638, 0
0x180011c84  jz      short loc_180011CE7
0x180011c86  lea     rbx, WPP_GLOBAL_Control
0x180011c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c94  cmp     rcx, rbx
0x180011c97  jz      short loc_180011CD1
0x180011c99  test    byte ptr [rcx+0BCh], 4
0x180011ca0  jz      short loc_180011CD1
0x180011ca2  lea     r9, ServerPrincName
0x180011ca9  cmp     cs:qword_180042640, 8
0x180011cb1  cmovnb  r9, cs:ServerPrincName
0x180011cb9  mov     edx, 34h ; '4'
0x180011cbe  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011cc5  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180011ccc  call    WPP_SF_S
0x180011cd1  mov     cs:byte_180043118, 1
0x180011cd8  mov     rcx, rdi; lpCriticalSection
0x180011cdb  call    cs:__imp_LeaveCriticalSection
0x180011ce1  nop
0x180011ce2  jmp     loc_180011DDC
0x180011ce7  mov     rdx, cs:?g_pNetworkServiceSid@@3PEAXEA; void * g_pNetworkServiceSid
0x180011cee  lea     rcx, [rsp+68h+var_40]
0x180011cf3  call    ?_BuildAccountNameForSid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAX@Z; _BuildAccountNameForSid(void *)
0x180011cf8  nop
0x180011cf9  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011cfd  xor     r8d, r8d
0x180011d00  mov     rdx, rax
0x180011d03  lea     rcx, ?g_pwzLocalMsmqAccount@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@A; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> g_pwzLocalMsmqAccount
0x180011d0a  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)
0x180011d0f  nop
0x180011d10  xor     r8d, r8d
0x180011d13  mov     dl, 1
0x180011d15  lea     rcx, [rsp+68h+var_40]
0x180011d1a  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x180011d1f  nop
0x180011d20  lea     rbx, WPP_GLOBAL_Control
0x180011d27  cmp     cs:qword_180042638, 0
0x180011d2f  jnz     short loc_180011D87
0x180011d31  mov     rax, cs:WPP_GLOBAL_Control
0x180011d38  cmp     rax, rbx
0x180011d3b  jz      short loc_180011D6E
0x180011d3d  test    byte ptr [rax+0BCh], 1
0x180011d44  jz      short loc_180011D6E
0x180011d46  call    cs:__imp_GetLastError
0x180011d4c  mov     edx, 35h ; '5'
0x180011d51  mov     r9d, eax
0x180011d54  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d62  mov     rcx, [rcx+0B0h]
0x180011d69  call    WPP_SF_d
0x180011d6e  mov     r8d, 1Bh
0x180011d74  lea     rdx, aNtAuthorityNet; "NT Authority\\NetworkService"
0x180011d7b  lea     rcx, ?g_pwzLocalMsmqAccount@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@A; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> g_pwzLocalMsmqAccount
0x180011d82  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(wchar_t const *,unsigned __int64)
0x180011d87  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d8e  cmp     rcx, rbx
0x180011d91  jz      short loc_180011DCB
0x180011d93  test    byte ptr [rcx+0BCh], 4
0x180011d9a  jz      short loc_180011DCB
0x180011d9c  lea     r9, ServerPrincName
0x180011da3  cmp     cs:qword_180042640, 8
0x180011dab  cmovnb  r9, cs:ServerPrincName
0x180011db3  mov     edx, 36h ; '6'
0x180011db8  lea     r8, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011dbf  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180011dc6  call    WPP_SF_S
0x180011dcb  mov     cs:byte_180043118, 1
0x180011dd2  mov     rcx, rdi; lpCriticalSection
0x180011dd5  call    cs:__imp_LeaveCriticalSection
0x180011ddb  nop
0x180011ddc  mov     rcx, [rsp+68h+var_18]
0x180011de1  xor     rcx, rsp; StackCookie
0x180011de4  call    __security_check_cookie
0x180011de9  mov     rbx, [rsp+68h+arg_0]
0x180011dee  add     rsp, 60h
0x180011df2  pop     rdi
0x180011df3  retn
```
