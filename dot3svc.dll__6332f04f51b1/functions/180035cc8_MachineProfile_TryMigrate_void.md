# MachineProfile::_TryMigrate(void)

- ea: `0x180035cc8`
- end: `0x180035ffb`
- name: `?_TryMigrate@MachineProfile@@AEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(MachineProfile *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003597c`

## callees

- `0x1800025f0`
- `0x1800084ec`
- `0x18000a9c0`
- `0x180021770`
- `0x180024c88`
- `0x1800291a0`
- `0x18002f140`
- `0x18002f214`
- `0x18002f388`
- `0x18002ff18`
- `0x180032e4c`
- `0x1800331c4`
- `0x1800357d4`
- `0x180035810`
- `0x180035be4`
- `0x180035cc8`
- `0x180036004`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180035d69`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180035d69`

## pseudocode

```c
__int64 __fastcall MachineProfile::_TryMigrate(MachineProfile *this, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // edi
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  _OWORD *v11; // rdi
  unsigned __int16 *v12; // rcx
  unsigned int Profile; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  int pszSubDir; // [rsp+20h] [rbp-2C8h]
  unsigned int pszSubDira; // [rsp+20h] [rbp-2C8h]
  unsigned int pszSubDirb; // [rsp+20h] [rbp-2C8h]
  unsigned int v21; // [rsp+30h] [rbp-2B8h] BYREF
  void *lpMem; // [rsp+38h] [rbp-2B0h] BYREF
  _OWORD v23[2]; // [rsp+40h] [rbp-2A8h] BYREF
  void **p_lpMem; // [rsp+60h] [rbp-288h] BYREF
  char v25; // [rsp+68h] [rbp-280h]
  _BYTE v26[32]; // [rsp+80h] [rbp-268h] BYREF
  _BYTE v27[32]; // [rsp+A0h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+C0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_Dc(WPP_GLOBAL_Control[1].Flink, 15, a3, *((unsigned int *)this + 4), *(_BYTE *)this);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *(_BYTE *)this && *((_DWORD *)this + 4) == 1 )
  {
    v5 = SHGetFolderPathAndSubDirW(0, 35, 0, 1u, L"Microsoft\\dot3svc\\MigrationData\\Profiles\\Machine", pszPath);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\net\\dot3\\dot3migration\\machineprofile.cpp",
        (const char *)(unsigned int)v5,
        pszSubDir);
      return v6;
    }
    memset(v23, 0, sizeof(v23));
    v8 = std::_WChar_traits<unsigned short>::length(pszPath);
    std::wstring::_Construct<1,unsigned short const *>(v23, pszPath, v8);
    v9 = std::operator+<unsigned short>(v27, v23);
    v10 = std::operator+<unsigned short>(v26, v9, (char *)this + 20);
    v11 = (_OWORD *)std::operator+<unsigned short>(&p_lpMem, v10, L".xml");
    if ( v23 != v11 )
    {
      std::wstring::_Tidy_deallocate(v23);
      std::wstring::_Take_contents(v23, v11);
    }
    std::wstring::_Tidy_deallocate(&p_lpMem);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v27);
    lpMem = 0;
    p_lpMem = &lpMem;
    v25 = 1;
    v12 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    Profile = LpLoadProfile(v12, pszSubDir);
    if ( Profile )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x63,
              (unsigned int)"onecoreuap\\net\\dot3\\dot3migration\\machineprofile.cpp",
              (const char *)Profile,
              pszSubDira);
      if ( lpMem )
        LpFreeProfileXml(lpMem);
      std::wstring::_Tidy_deallocate(v23);
      return v14;
    }
    v21 = 0;
    v15 = Dot3AcmSetProfile(0, 2u, (unsigned __int16 *)lpMem, 1, &v21);
    if ( v15 )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x66,
              (unsigned int)"onecoreuap\\net\\dot3\\dot3migration\\machineprofile.cpp",
              (const char *)v15,
              pszSubDirb);
      if ( !lpMem )
      {
LABEL_18:
        std::wstring::_Tidy_deallocate(v23);
        return v16;
      }
LABEL_17:
      LpFreeProfileXml(lpMem);
      goto LABEL_18;
    }
    *((_DWORD *)this + 4) = 2;
    v17 = MachineProfile::_SetMigrationStatus(this, 2);
    v16 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\net\\dot3\\dot3migration\\machineprofile.cpp",
        (const char *)(unsigned int)v17,
        pszSubDirb);
      if ( !lpMem )
        goto LABEL_18;
      goto LABEL_17;
    }
    if ( lpMem )
      LpFreeProfileXml(lpMem);
    std::wstring::_Tidy_deallocate(v23);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 16, &WPP_1cf9d866e54432687271528bd30a9afa_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180035cc8  mov     [rsp+arg_8], rbx
0x180035ccd  mov     [rsp+arg_10], rdi
0x180035cd2  push    r14
0x180035cd4  sub     rsp, 2E0h
0x180035cdb  mov     rax, cs:__security_cookie
0x180035ce2  xor     rax, rsp
0x180035ce5  mov     [rsp+2E8h+var_18], rax
0x180035ced  mov     rbx, rcx
0x180035cf0  lea     r14, WPP_GLOBAL_Control
0x180035cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cfe  cmp     rcx, r14
0x180035d01  jz      short loc_180035D2E
0x180035d03  cmp     byte ptr [rcx+19h], 4
0x180035d07  jb      short loc_180035D2E
0x180035d09  test    byte ptr [rcx+1Ch], 1
0x180035d0d  jz      short loc_180035D2E
0x180035d0f  mov     edx, 0Fh
0x180035d14  mov     al, [rbx]
0x180035d16  mov     byte ptr [rsp+2E8h+pszSubDir], al
0x180035d1a  mov     r9d, [rbx+10h]
0x180035d1e  mov     rcx, [rcx+10h]
0x180035d22  call    WPP_SF_Dc
0x180035d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d2e  cmp     byte ptr [rbx], 0
0x180035d31  jz      loc_180035FA3
0x180035d37  cmp     dword ptr [rbx+10h], 1
0x180035d3b  jnz     loc_180035FA3
0x180035d41  lea     rax, [rsp+2E8h+var_228]
0x180035d49  mov     [rsp+2E8h+pszPath], rax; pszPath
0x180035d4e  lea     rax, aMicrosoftDot3s_0; "Microsoft\\dot3svc\\MigrationData\\Prof"...
0x180035d55  mov     [rsp+2E8h+pszSubDir], rax; unsigned int
0x180035d5a  mov     r9d, 1; dwFlags
0x180035d60  xor     r8d, r8d; hToken
0x180035d63  lea     edx, [r9+22h]; csidl
0x180035d67  xor     ecx, ecx; hwnd
0x180035d69  call    cs:__imp_SHGetFolderPathAndSubDirW
0x180035d6f  mov     edi, eax
0x180035d71  test    eax, eax
0x180035d73  jns     short loc_180035D98
0x180035d75  mov     rcx, [rsp+2E8h]; this
0x180035d7d  mov     r9d, eax; char *
0x180035d80  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dot3\\dot3migration\\m"...
0x180035d87  mov     edx, 55h ; 'U'; void *
0x180035d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d91  mov     eax, edi
0x180035d93  jmp     loc_180035FD4
0x180035d98  xorps   xmm0, xmm0
0x180035d9b  movups  [rsp+2E8h+var_2A8], xmm0
0x180035da0  xorps   xmm1, xmm1
0x180035da3  movdqu  [rsp+2E8h+var_298], xmm1
0x180035da9  lea     rcx, [rsp+2E8h+var_228]
0x180035db1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180035db6  mov     r8, rax
0x180035db9  lea     rdx, [rsp+2E8h+var_228]
0x180035dc1  lea     rcx, [rsp+2E8h+var_2A8]
0x180035dc6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035dcb  nop
0x180035dcc  lea     rdx, [rsp+2E8h+var_2A8]
0x180035dd1  lea     rcx, [rsp+2E8h+var_248]
0x180035dd9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180035dde  nop
0x180035ddf  lea     r8, [rbx+14h]
0x180035de3  mov     rdx, rax
0x180035de6  lea     rcx, [rsp+2E8h+var_268]
0x180035dee  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180035df3  nop
0x180035df4  lea     r8, pszExt; ".xml"
0x180035dfb  mov     rdx, rax
0x180035dfe  lea     rcx, [rsp+2E8h+var_288]
0x180035e03  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180035e08  mov     rdi, rax
0x180035e0b  lea     rax, [rsp+2E8h+var_2A8]
0x180035e10  cmp     rax, rdi
0x180035e13  jz      short loc_180035E2C
0x180035e15  lea     rcx, [rsp+2E8h+var_2A8]
0x180035e1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035e1f  mov     rdx, rdi
0x180035e22  lea     rcx, [rsp+2E8h+var_2A8]
0x180035e27  call    ?_Take_contents@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXAEAV12@@Z; std::wstring::_Take_contents(std::wstring &)
0x180035e2c  lea     rcx, [rsp+2E8h+var_288]
0x180035e31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035e36  nop
0x180035e37  lea     rcx, [rsp+2E8h+var_268]
0x180035e3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035e44  nop
0x180035e45  lea     rcx, [rsp+2E8h+var_248]
0x180035e4d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035e52  mov     [rsp+2E8h+lpMem], 0
0x180035e5b  lea     rax, [rsp+2E8h+lpMem]
0x180035e60  mov     [rsp+2E8h+var_288], rax
0x180035e65  mov     [rsp+2E8h+var_280], 1
0x180035e6a  lea     rcx, [rsp+2E8h+var_2A8]
0x180035e6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035e74  mov     rcx, rax; unsigned __int16 *
0x180035e77  lea     r9, [rsp+2E8h+lpMem]
0x180035e7c  xor     r8d, r8d
0x180035e7f  xor     edx, edx
0x180035e81  call    LpLoadProfile
0x180035e86  test    eax, eax
0x180035e88  jz      short loc_180035EC9
0x180035e8a  mov     rcx, [rsp+2E8h]; this
0x180035e92  mov     r9d, eax; char *
0x180035e95  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dot3\\dot3migration\\m"...
0x180035e9c  mov     edx, 63h ; 'c'; void *
0x180035ea1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035ea6  mov     ebx, eax
0x180035ea8  mov     rcx, [rsp+2E8h+lpMem]; lpMem
0x180035ead  test    rcx, rcx
0x180035eb0  jz      short loc_180035EB8
0x180035eb2  call    LpFreeProfileXml
0x180035eb7  nop
0x180035eb8  lea     rcx, [rsp+2E8h+var_2A8]
0x180035ebd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035ec2  mov     eax, ebx
0x180035ec4  jmp     loc_180035FD4
0x180035ec9  mov     [rsp+2E8h+var_2B8], 0
0x180035ed1  lea     rax, [rsp+2E8h+var_2B8]
0x180035ed6  mov     [rsp+2E8h+pszSubDir], rax; int
0x180035edb  mov     r9d, 1; int
0x180035ee1  mov     r8, [rsp+2E8h+lpMem]; unsigned __int16 *
0x180035ee6  lea     edi, [r9+1]
0x180035eea  mov     edx, edi; unsigned int
0x180035eec  xor     ecx, ecx; struct _GUID *
0x180035eee  call    ?Dot3AcmSetProfile@@YAKPEAU_GUID@@KPEBGHPEAK@Z; Dot3AcmSetProfile(_GUID *,ulong,ushort const *,int,ulong *)
0x180035ef3  test    eax, eax
0x180035ef5  jz      short loc_180035F34
0x180035ef7  mov     rcx, [rsp+2E8h]; this
0x180035eff  mov     r9d, eax; char *
0x180035f02  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dot3\\dot3migration\\m"...
0x180035f09  lea     edx, [rdi+64h]; void *
0x180035f0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035f11  mov     ebx, eax
0x180035f13  mov     rcx, [rsp+2E8h+lpMem]; lpMem
0x180035f18  test    rcx, rcx
0x180035f1b  jz      short loc_180035F23
0x180035f1d  call    LpFreeProfileXml
0x180035f22  nop
0x180035f23  lea     rcx, [rsp+2E8h+var_2A8]
0x180035f28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035f2d  mov     eax, ebx
0x180035f2f  jmp     loc_180035FD4
0x180035f34  mov     [rbx+10h], edi
0x180035f37  mov     edx, edi
0x180035f39  mov     rcx, rbx
0x180035f3c  call    ?_SetMigrationStatus@MachineProfile@@AEAAJW4MachineProfileMigrationStatus@@@Z; MachineProfile::_SetMigrationStatus(MachineProfileMigrationStatus)
0x180035f41  mov     ebx, eax
0x180035f43  test    eax, eax
0x180035f45  jns     short loc_180035F82
0x180035f47  mov     rcx, [rsp+2E8h]; this
0x180035f4f  mov     r9d, eax; char *
0x180035f52  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dot3\\dot3migration\\m"...
0x180035f59  mov     edx, 69h ; 'i'; void *
0x180035f5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f63  nop
0x180035f64  mov     rcx, [rsp+2E8h+lpMem]; lpMem
0x180035f69  test    rcx, rcx
0x180035f6c  jz      short loc_180035F74
0x180035f6e  call    LpFreeProfileXml
0x180035f73  nop
0x180035f74  lea     rcx, [rsp+2E8h+var_2A8]
0x180035f79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035f7e  mov     eax, ebx
0x180035f80  jmp     short loc_180035FD4
0x180035f82  mov     rcx, [rsp+2E8h+lpMem]; lpMem
0x180035f87  test    rcx, rcx
0x180035f8a  jz      short loc_180035F92
0x180035f8c  call    LpFreeProfileXml
0x180035f91  nop
0x180035f92  lea     rcx, [rsp+2E8h+var_2A8]
0x180035f97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fa3  cmp     rcx, r14
0x180035fa6  jz      short loc_180035FCC
0x180035fa8  cmp     byte ptr [rcx+19h], 4
0x180035fac  jb      short loc_180035FCC
0x180035fae  test    byte ptr [rcx+1Ch], 1
0x180035fb2  jz      short loc_180035FCC
0x180035fb4  mov     edx, 10h
0x180035fb9  xor     r9d, r9d
0x180035fbc  lea     r8, WPP_1cf9d866e54432687271528bd30a9afa_Traceguids
0x180035fc3  mov     rcx, [rcx+10h]
0x180035fc7  call    WPP_SF_d
0x180035fcc  xor     eax, eax
0x180035fce  jmp     short loc_180035FD4
0x180035fd0  mov     eax, [rsp+2E8h+var_2B8]
0x180035fd4  mov     rcx, [rsp+2E8h+var_18]
0x180035fdc  xor     rcx, rsp; StackCookie
0x180035fdf  call    __security_check_cookie
0x180035fe4  lea     r11, [rsp+2E8h+var_8]
0x180035fec  mov     rbx, [r11+18h]
0x180035ff0  mov     rdi, [r11+20h]
0x180035ff4  mov     rsp, r11
0x180035ff7  pop     r14
0x180035ff9  retn
```
