# OfflineRegistry::GetSecureHivePathForFamilyAndUser(ushort const *,void *)

- ea: `0x1800773d0`
- end: `0x1800775c4`
- name: `?GetSecureHivePathForFamilyAndUser@OfflineRegistry@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAX@Z`
- size: `500`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18006fabc`
- `0x180087cd4`
- `0x1800882bc`

## callees

- `0x180005794`
- `0x180009484`
- `0x180010a84`
- `0x18001366c`
- `0x18001513c`
- `0x18002031c`
- `0x1800217f0`
- `0x180024030`
- `0x1800773d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007742f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007749d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007742f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007749d`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18007752f`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18007752f`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18007753f`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18007753f`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x180077423`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x18007748e`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x180077423`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x18007748e`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18007755d`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18007755d`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800773f0`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800773f0`

## string_xrefs

- `0x180077588`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x18007759a`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x1800775af`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OfflineRegistry::GetSecureHivePathForFamilyAndUser(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  const char *v5; // r9
  signed int LastError; // eax
  char v7; // cl
  void *v8; // rsi
  int SecureSystemAppDataFolder; // r14d
  signed int v10; // eax
  __int64 v11; // rax
  unsigned __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+3Ch] [rbp-C4h]
  _QWORD v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v19[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[104]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  unsigned int v22; // [rsp+178h] [rbp+78h] BYREF

  v4 = OpenStateExplicit(a3);
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      v5);
  v22 = 0;
  GetSecureSystemAppDataFolder(v4, 0, &v22);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    if ( LastError <= 0 )
      goto LABEL_6;
  }
  LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)LastError,
      v14);
  v8 = operator new[](saturated_mul(v22, 2u));
  SecureSystemAppDataFolder = GetSecureSystemAppDataFolder(v4, v8, &v22);
  v10 = GetLastError();
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  if ( SecureSystemAppDataFolder != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)v10,
      v14);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v16);
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, v8);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"\\Helium");
  std::basic_stringbuf<unsigned short>::str(v18, a1);
  *(_QWORD *)((char *)v16 + *(int *)(v16[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v15 + *(int *)(v16[0] + 4LL)) = *(_DWORD *)(v16[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v18);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v19);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v20);
  operator delete(v8, v12);
  CloseState(v4);
  return a1;
}

```

## disassembly

```asm
0x1800773d0  mov     [rsp-8+arg_0], rbx
0x1800773d5  mov     [rsp-8+arg_8], rsi
0x1800773da  push    rbp
0x1800773db  push    rdi
0x1800773dc  push    r14
0x1800773de  lea     rbp, [rsp-40h]
0x1800773e3  sub     rsp, 140h
0x1800773ea  mov     rdi, rcx
0x1800773ed  mov     rcx, r8
0x1800773f0  call    cs:__imp_OpenStateExplicit
0x1800773f7  nop     dword ptr [rax+rax+00h]
0x1800773fc  mov     rbx, rax
0x1800773ff  mov     [rsp+150h+var_128], rax
0x180077404  test    rax, rax
0x180077407  setnz   al
0x18007740a  mov     rcx, [rbp+58h]; this
0x18007740e  test    al, al
0x180077410  jz      loc_18007759A
0x180077416  and     [rbp+50h+arg_18], 0
0x18007741a  lea     r8, [rbp+50h+arg_18]
0x18007741e  xor     edx, edx
0x180077420  mov     rcx, rbx
0x180077423  call    cs:__imp_GetSecureSystemAppDataFolder
0x18007742a  nop     dword ptr [rax+rax+00h]
0x18007742f  call    cs:__imp_GetLastError
0x180077436  nop     dword ptr [rax+rax+00h]
0x18007743b  cmp     eax, 7Ah ; 'z'
0x18007743e  jnz     short loc_180077444
0x180077440  xor     cl, cl
0x180077442  jmp     short loc_18007744A
0x180077444  mov     cl, 1
0x180077446  test    eax, eax
0x180077448  jle     short loc_180077452
0x18007744a  movzx   eax, ax
0x18007744d  or      eax, 80070000h
0x180077452  mov     r10, [rbp+58h]
0x180077456  test    cl, cl
0x180077458  jnz     loc_1800775AC
0x18007745e  mov     ecx, [rbp+50h+arg_18]
0x180077461  mov     eax, 2
0x180077466  mul     rcx
0x180077469  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180077470  cmovo   rax, rcx
0x180077474  mov     rcx, rax; unsigned __int64
0x180077477  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007747c  mov     rsi, rax
0x18007747f  mov     [rsp+150h+var_120], rax
0x180077484  lea     r8, [rbp+50h+arg_18]
0x180077488  mov     rdx, rax
0x18007748b  mov     rcx, rbx
0x18007748e  call    cs:__imp_GetSecureSystemAppDataFolder
0x180077495  nop     dword ptr [rax+rax+00h]
0x18007749a  mov     r14d, eax
0x18007749d  call    cs:__imp_GetLastError
0x1800774a4  nop     dword ptr [rax+rax+00h]
0x1800774a9  test    eax, eax
0x1800774ab  jle     short loc_1800774B5
0x1800774ad  movzx   eax, ax
0x1800774b0  or      eax, 80070000h
0x1800774b5  mov     rcx, [rbp+58h]; this
0x1800774b9  cmp     r14d, 1
0x1800774bd  jnz     loc_180077585
0x1800774c3  lea     rcx, [rsp+150h+var_110]
0x1800774c8  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1800774cd  nop
0x1800774ce  mov     rdx, rsi
0x1800774d1  lea     rcx, [rsp+150h+var_100]
0x1800774d6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800774db  mov     rcx, rax
0x1800774de  lea     rdx, aHelium; "\\Helium"
0x1800774e5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800774ea  mov     rdx, rdi
0x1800774ed  lea     rcx, [rsp+150h+var_F8]
0x1800774f2  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800774f7  nop
0x1800774f8  mov     rax, [rsp+150h+var_110]
0x1800774fd  movsxd  rcx, dword ptr [rax+4]
0x180077501  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180077508  mov     [rsp+rcx+150h+var_110], rax
0x18007750d  mov     rax, [rsp+150h+var_110]
0x180077512  movsxd  rcx, dword ptr [rax+4]
0x180077516  lea     edx, [rcx-98h]
0x18007751c  mov     [rsp+rcx+150h+var_114], edx
0x180077520  lea     rcx, [rsp+150h+var_F8]
0x180077525  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18007752a  lea     rcx, [rsp+150h+var_F0]
0x18007752f  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180077536  nop     dword ptr [rax+rax+00h]
0x18007753b  lea     rcx, [rbp+50h+var_78]
0x18007753f  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180077546  nop     dword ptr [rax+rax+00h]
0x18007754b  nop
0x18007754c  mov     rcx, rsi; void *
0x18007754f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180077554  nop
0x180077555  test    rbx, rbx
0x180077558  jz      short loc_180077569
0x18007755a  mov     rcx, rbx
0x18007755d  call    cs:__imp_CloseState
0x180077564  nop     dword ptr [rax+rax+00h]
0x180077569  mov     rax, rdi
0x18007756c  lea     r11, [rsp+150h+var_10]
0x180077574  mov     rbx, [r11+20h]
0x180077578  mov     rsi, [r11+28h]
0x18007757c  mov     rsp, r11
0x18007757f  pop     r14
0x180077581  pop     rdi
0x180077582  pop     rbp
0x180077583  retn
0x180077585  mov     r9d, eax; char *
0x180077588  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007758f  mov     edx, 43h ; 'C'; void *
0x180077594  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007759a  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800775a1  mov     edx, 3Ah ; ':'; void *
0x1800775a6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800775ac  mov     r9d, eax; char *
0x1800775af  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800775b6  mov     edx, 3Fh ; '?'; void *
0x1800775bb  mov     rcx, r10; this
0x1800775be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
