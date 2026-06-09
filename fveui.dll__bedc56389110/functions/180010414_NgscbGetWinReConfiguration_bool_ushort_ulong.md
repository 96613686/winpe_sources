# NgscbGetWinReConfiguration(bool *,ushort *,ulong)

- ea: `0x180010414`
- end: `0x1800105f2`
- name: `?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z`
- size: `478`
- prototype: `__int64 __fastcall(bool *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180014aac`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x18000b978`
- `0x1800103b8`
- `0x180010414`
- `0x1800105f8`
- `0x18002d010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800105c6`
- `KERNEL32!FreeLibrary` at `0x1800105c6`
- `KERNEL32!LoadLibraryExW` at `0x18001048e`
- `KERNEL32!LoadLibraryExW` at `0x18001048e`
- `KERNEL32!GetProcAddress` at `0x1800104eb`
- `KERNEL32!GetProcAddress` at `0x1800104eb`

## string_xrefs

- `0x180010481`: `reinfo.dll`
- `0x1800104e1`: `WinReGetConfig`

## pseudocode

```c
__int64 __fastcall NgscbGetWinReConfiguration(bool *a1, unsigned __int16 *a2)
{
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rsi
  FARPROC ProcAddress; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v11; // [rsp+20h] [rbp-EC8h] BYREF
  int v12; // [rsp+28h] [rbp-EC0h]
  unsigned __int16 v13[1556]; // [rsp+298h] [rbp-C50h] BYREF

  memset_0(&v11, 0, 0xEA0u);
  KnownLastErrorHR = 0;
  *a1 = 0;
  if ( a2 )
    memset_0(a2, 0, 0x25Cu);
  if ( !NgscbGet_TEST_BooleanOverride(L"ReportWinREAvailable", a1) )
  {
    Library = LoadLibraryExW(L"reinfo.dll", 0, 0x800u);
    v6 = Library;
    if ( !Library )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          334,
          WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          KnownLastErrorHR);
      return KnownLastErrorHR;
    }
    ProcAddress = GetProcAddress(Library, "WinReGetConfig");
    if ( ProcAddress )
    {
      v11 = 3744;
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v11) )
      {
        *a1 = v12 != 0;
        if ( !a2 )
          goto LABEL_22;
        KnownLastErrorHR = StringCchCopyW(a2, 0x12Eu, v13);
        if ( !KnownLastErrorHR )
          goto LABEL_22;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_22;
        v9 = 337;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_22;
        v9 = 336;
      }
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_22;
      v9 = 335;
    }
    WPP_SF_d(v8[2], v9, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, KnownLastErrorHR);
LABEL_22:
    FreeLibrary(v6);
  }
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x180010414  mov     [rsp+arg_10], rbx
0x180010419  push    rsi
0x18001041a  push    rdi
0x18001041b  push    r14
0x18001041d  sub     rsp, 0ED0h
0x180010424  mov     rax, cs:__security_cookie
0x18001042b  xor     rax, rsp
0x18001042e  mov     [rsp+0EE8h+var_28], rax
0x180010436  mov     rdi, rdx
0x180010439  mov     r14, rcx
0x18001043c  xor     edx, edx; Val
0x18001043e  lea     rcx, [rsp+0EE8h+var_EC8]; void *
0x180010443  mov     r8d, 0EA0h; Size
0x180010449  call    memset_0
0x18001044e  xor     ebx, ebx
0x180010450  mov     [r14], bl
0x180010453  test    rdi, rdi
0x180010456  jz      short loc_180010468
0x180010458  xor     edx, edx; Val
0x18001045a  mov     r8d, 25Ch; Size
0x180010460  mov     rcx, rdi; void *
0x180010463  call    memset_0
0x180010468  mov     rdx, r14; bool *
0x18001046b  lea     rcx, aReportwinreava; "ReportWinREAvailable"
0x180010472  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x180010477  test    al, al
0x180010479  jnz     loc_1800105CC
0x18001047f  xor     edx, edx; hFile
0x180010481  lea     rcx, aReinfoDll; "reinfo.dll"
0x180010488  mov     r8d, 800h; dwFlags
0x18001048e  call    cs:__imp_LoadLibraryExW
0x180010494  mov     rsi, rax
0x180010497  test    rax, rax
0x18001049a  jnz     short loc_1800104E1
0x18001049c  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800104a1  mov     ebx, eax
0x1800104a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104aa  lea     rax, WPP_GLOBAL_Control
0x1800104b1  cmp     rcx, rax
0x1800104b4  jz      loc_1800105CC
0x1800104ba  test    byte ptr [rcx+1Ch], 40h
0x1800104be  jz      loc_1800105CC
0x1800104c4  mov     rcx, [rcx+10h]
0x1800104c8  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800104cf  mov     edx, 14Eh
0x1800104d4  mov     r9d, ebx
0x1800104d7  call    WPP_SF_d
0x1800104dc  jmp     loc_1800105CC
0x1800104e1  lea     rdx, aWinregetconfig; "WinReGetConfig"
0x1800104e8  mov     rcx, rsi; hModule
0x1800104eb  call    cs:__imp_GetProcAddress
0x1800104f1  test    rax, rax
0x1800104f4  jnz     short loc_180010528
0x1800104f6  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800104fb  mov     ebx, eax
0x1800104fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180010504  lea     rax, WPP_GLOBAL_Control
0x18001050b  cmp     rcx, rax
0x18001050e  jz      loc_1800105C3
0x180010514  test    byte ptr [rcx+1Ch], 40h
0x180010518  jz      loc_1800105C3
0x18001051e  mov     edx, 14Fh
0x180010523  jmp     loc_1800105B0
0x180010528  lea     rdx, [rsp+0EE8h+var_EC8]
0x18001052d  mov     [rsp+0EE8h+var_EC8], 0EA0h
0x180010536  xor     ecx, ecx
0x180010538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001053d  test    eax, eax
0x18001053f  jnz     short loc_180010568
0x180010541  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180010546  mov     ebx, eax
0x180010548  mov     rcx, cs:WPP_GLOBAL_Control
0x18001054f  lea     rax, WPP_GLOBAL_Control
0x180010556  cmp     rcx, rax
0x180010559  jz      short loc_1800105C3
0x18001055b  test    byte ptr [rcx+1Ch], 40h
0x18001055f  jz      short loc_1800105C3
0x180010561  mov     edx, 150h
0x180010566  jmp     short loc_1800105B0
0x180010568  cmp     [rsp+0EE8h+var_EC0], ebx
0x18001056c  setnz   al
0x18001056f  mov     [r14], al
0x180010572  test    rdi, rdi
0x180010575  jz      short loc_1800105C3
0x180010577  lea     r8, [rsp+0EE8h+var_C50]; unsigned __int16 *
0x18001057f  mov     edx, 12Eh; unsigned __int64
0x180010584  mov     rcx, rdi; unsigned __int16 *
0x180010587  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001058c  mov     ebx, eax
0x18001058e  test    eax, eax
0x180010590  jz      short loc_1800105C3
0x180010592  mov     rcx, cs:WPP_GLOBAL_Control
0x180010599  lea     rax, WPP_GLOBAL_Control
0x1800105a0  cmp     rcx, rax
0x1800105a3  jz      short loc_1800105C3
0x1800105a5  test    byte ptr [rcx+1Ch], 40h
0x1800105a9  jz      short loc_1800105C3
0x1800105ab  mov     edx, 151h
0x1800105b0  mov     rcx, [rcx+10h]
0x1800105b4  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800105bb  mov     r9d, ebx
0x1800105be  call    WPP_SF_d
0x1800105c3  mov     rcx, rsi; hLibModule
0x1800105c6  call    cs:__imp_FreeLibrary
0x1800105cc  mov     eax, ebx
0x1800105ce  mov     rcx, [rsp+0EE8h+var_28]
0x1800105d6  xor     rcx, rsp; StackCookie
0x1800105d9  call    __security_check_cookie
0x1800105de  mov     rbx, [rsp+0EE8h+arg_10]
0x1800105e6  add     rsp, 0ED0h
0x1800105ed  pop     r14
0x1800105ef  pop     rdi
0x1800105f0  pop     rsi
0x1800105f1  retn
```
