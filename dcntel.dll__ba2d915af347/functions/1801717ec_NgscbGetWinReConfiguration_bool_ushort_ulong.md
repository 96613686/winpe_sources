# NgscbGetWinReConfiguration(bool *,ushort *,ulong)

- ea: `0x1801717ec`
- end: `0x1801719b4`
- name: `?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z`
- size: `456`
- prototype: `__int64 __fastcall(bool *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800258b0`
- `0x1800a7030`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x1800127f8`
- `0x180171798`
- `0x1801717ec`
- `0x1801719bc`
- `0x180171b28`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18017185e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18017185e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180171988`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180171988`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801718b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801718b4`

## string_xrefs

- `0x180171855`: `reinfo.dll`
- `0x1801718aa`: `WinReGetConfig`

## pseudocode

```c
__int64 __fastcall NgscbGetWinReConfiguration(bool *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rcx
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rsi
  __int64 v8; // r8
  FARPROC ProcAddress; // rax
  __int64 v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-EC8h] BYREF
  int v15; // [rsp+28h] [rbp-EC0h]
  unsigned __int16 v16[1556]; // [rsp+298h] [rbp-C50h] BYREF

  memset_0(&v14, 0, 0xEA0u);
  KnownLastErrorHR = 0;
  *a1 = 0;
  if ( a2 )
    memset_0(a2, 0, 0x800u);
  if ( !NgscbGet_TEST_BooleanOverride(v4, a1) )
  {
    Library = LoadLibraryExW(L"reinfo.dll", 0, 0x800u);
    v7 = Library;
    if ( !Library )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, v8, KnownLastErrorHR);
      return KnownLastErrorHR;
    }
    ProcAddress = GetProcAddress(Library, "WinReGetConfig");
    if ( ProcAddress )
    {
      v14 = 3744;
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v14) )
      {
        *a1 = v15 != 0;
        if ( !a2 )
          goto LABEL_22;
        KnownLastErrorHR = StringCchCopyW(a2, 0x400u, v16);
        if ( !KnownLastErrorHR )
          goto LABEL_22;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_22;
        v12 = 337;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_22;
        v12 = 336;
      }
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_22;
      v12 = 335;
    }
    WPP_SF_d(v11[2], v12, v10, KnownLastErrorHR);
LABEL_22:
    FreeLibrary(v7);
  }
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x1801717ec  mov     [rsp+arg_10], rbx
0x1801717f1  push    rsi
0x1801717f2  push    rdi
0x1801717f3  push    r14
0x1801717f5  sub     rsp, 0ED0h
0x1801717fc  mov     rax, cs:__security_cookie
0x180171803  xor     rax, rsp
0x180171806  mov     [rsp+0EE8h+var_28], rax
0x18017180e  mov     rdi, rdx
0x180171811  mov     r14, rcx
0x180171814  xor     edx, edx; Val
0x180171816  lea     rcx, [rsp+0EE8h+var_EC8]; void *
0x18017181b  mov     r8d, 0EA0h; Size
0x180171821  call    memset_0
0x180171826  xor     ebx, ebx
0x180171828  mov     esi, 800h
0x18017182d  mov     [r14], bl
0x180171830  test    rdi, rdi
0x180171833  jz      short loc_180171842
0x180171835  mov     r8d, esi; Size
0x180171838  xor     edx, edx; Val
0x18017183a  mov     rcx, rdi; void *
0x18017183d  call    memset_0
0x180171842  mov     rdx, r14; bool *
0x180171845  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x18017184a  test    al, al
0x18017184c  jnz     loc_18017198E
0x180171852  mov     r8d, esi; dwFlags
0x180171855  lea     rcx, aReinfoDll; "reinfo.dll"
0x18017185c  xor     edx, edx; hFile
0x18017185e  call    cs:__imp_LoadLibraryExW
0x180171864  mov     rsi, rax
0x180171867  test    rax, rax
0x18017186a  jnz     short loc_1801718AA
0x18017186c  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180171871  mov     ebx, eax
0x180171873  mov     rcx, cs:WPP_GLOBAL_Control
0x18017187a  lea     rax, WPP_GLOBAL_Control
0x180171881  cmp     rcx, rax
0x180171884  jz      loc_18017198E
0x18017188a  test    byte ptr [rcx+1Ch], 40h
0x18017188e  jz      loc_18017198E
0x180171894  mov     rcx, [rcx+10h]
0x180171898  mov     edx, 14Eh
0x18017189d  mov     r9d, ebx
0x1801718a0  call    WPP_SF_d
0x1801718a5  jmp     loc_18017198E
0x1801718aa  lea     rdx, aWinregetconfig; "WinReGetConfig"
0x1801718b1  mov     rcx, rsi; hModule
0x1801718b4  call    cs:__imp_GetProcAddress
0x1801718ba  test    rax, rax
0x1801718bd  jnz     short loc_1801718F1
0x1801718bf  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1801718c4  mov     ebx, eax
0x1801718c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801718cd  lea     rax, WPP_GLOBAL_Control
0x1801718d4  cmp     rcx, rax
0x1801718d7  jz      loc_180171985
0x1801718dd  test    byte ptr [rcx+1Ch], 40h
0x1801718e1  jz      loc_180171985
0x1801718e7  mov     edx, 14Fh
0x1801718ec  jmp     loc_180171979
0x1801718f1  lea     rdx, [rsp+0EE8h+var_EC8]
0x1801718f6  mov     [rsp+0EE8h+var_EC8], 0EA0h
0x1801718ff  xor     ecx, ecx
0x180171901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171906  test    eax, eax
0x180171908  jnz     short loc_180171931
0x18017190a  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18017190f  mov     ebx, eax
0x180171911  mov     rcx, cs:WPP_GLOBAL_Control
0x180171918  lea     rax, WPP_GLOBAL_Control
0x18017191f  cmp     rcx, rax
0x180171922  jz      short loc_180171985
0x180171924  test    byte ptr [rcx+1Ch], 40h
0x180171928  jz      short loc_180171985
0x18017192a  mov     edx, 150h
0x18017192f  jmp     short loc_180171979
0x180171931  cmp     [rsp+0EE8h+var_EC0], ebx
0x180171935  setnz   al
0x180171938  mov     [r14], al
0x18017193b  test    rdi, rdi
0x18017193e  jz      short loc_180171985
0x180171940  lea     r8, [rsp+0EE8h+var_C50]; unsigned __int16 *
0x180171948  mov     edx, 400h; unsigned __int64
0x18017194d  mov     rcx, rdi; unsigned __int16 *
0x180171950  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180171955  mov     ebx, eax
0x180171957  test    eax, eax
0x180171959  jz      short loc_180171985
0x18017195b  mov     rcx, cs:WPP_GLOBAL_Control
0x180171962  lea     rax, WPP_GLOBAL_Control
0x180171969  cmp     rcx, rax
0x18017196c  jz      short loc_180171985
0x18017196e  test    byte ptr [rcx+1Ch], 40h
0x180171972  jz      short loc_180171985
0x180171974  mov     edx, 151h
0x180171979  mov     rcx, [rcx+10h]
0x18017197d  mov     r9d, ebx
0x180171980  call    WPP_SF_d
0x180171985  mov     rcx, rsi; hLibModule
0x180171988  call    cs:__imp_FreeLibrary
0x18017198e  mov     eax, ebx
0x180171990  mov     rcx, [rsp+0EE8h+var_28]
0x180171998  xor     rcx, rsp; StackCookie
0x18017199b  call    __security_check_cookie
0x1801719a0  mov     rbx, [rsp+0EE8h+arg_10]
0x1801719a8  add     rsp, 0ED0h
0x1801719af  pop     r14
0x1801719b1  pop     rdi
0x1801719b2  pop     rsi
0x1801719b3  retn
```
