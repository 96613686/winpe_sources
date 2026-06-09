# GetTimeSyncSource(ushort * *)

- ea: `0x180016eac`
- end: `0x180017070`
- name: `?GetTimeSyncSource@@YAJPEAPEAG@Z`
- size: `452`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016c38`

## callees

- `0x180014660`
- `0x180014da0`
- `0x180016eac`
- `0x180017078`
- `0x18001c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180016f17`
- `KERNEL32!LoadLibraryW` at `0x180016f17`
- `KERNEL32!FreeLibrary` at `0x180017055`
- `KERNEL32!FreeLibrary` at `0x180017055`
- `KERNEL32!GetProcAddress` at `0x180016f33`
- `KERNEL32!GetProcAddress` at `0x180016f4f`
- `KERNEL32!GetProcAddress` at `0x180016f33`
- `KERNEL32!GetProcAddress` at `0x180016f4f`

## string_xrefs

- `0x180016ef3`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180017020`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016f10`: `w32time.dll`

## pseudocode

```c
__int64 __fastcall GetTimeSyncSource(unsigned __int16 **a1)
{
  void (*v2)(void); // rsi
  HMODULE v3; // rdi
  signed int v4; // eax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // r9d
  HMODULE LibraryW; // rax
  const struct _EVENT_DESCRIPTOR *Keyword; // rdx
  CEventLogger *v11; // rcx
  FARPROC ProcAddress; // rbx
  unsigned int i; // eax
  unsigned int v14; // r9d
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v16 = 0;
  v3 = 0;
  *a1 = 0;
  v4 = IsW32TimeRunning();
  v7 = v4;
  if ( v4 == -2147023834 )
  {
    v7 = 1;
    goto LABEL_28;
  }
  if ( v4 < 0 )
  {
    v8 = 803;
LABEL_5:
    CEventLogger::LogError(v6, v5, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", v8, L"GetTimeSyncSource", v4);
    goto LABEL_28;
  }
  LibraryW = LoadLibraryW(L"w32time.dll");
  v3 = LibraryW;
  if ( !LibraryW )
  {
    v14 = 806;
    goto LABEL_27;
  }
  ProcAddress = GetProcAddress(LibraryW, "W32TimeQueryNTPProviderStatus");
  if ( !ProcAddress )
  {
    v14 = 812;
    goto LABEL_27;
  }
  v2 = (void (*)(void))GetProcAddress(v3, "W32TimeBufferFree");
  if ( !v2 )
  {
    v14 = 816;
    goto LABEL_27;
  }
  if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, const wchar_t *, __int64 *))ProcAddress)(0, 0, L"NtpClient", &v16) )
  {
    v14 = 823;
    goto LABEL_27;
  }
  v11 = (CEventLogger *)v16;
  if ( !*(_DWORD *)(v16 + 12) )
  {
    v14 = 824;
    goto LABEL_27;
  }
  Keyword = *(const struct _EVENT_DESCRIPTOR **)(v16 + 16);
  if ( !Keyword )
  {
    v14 = 825;
    goto LABEL_27;
  }
  Keyword = (const struct _EVENT_DESCRIPTOR *)Keyword[2].Keyword;
  if ( !Keyword )
  {
    v14 = 826;
LABEL_27:
    CEventLogger::LogError(
      v11,
      Keyword,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      v14,
      L"GetTimeSyncSource",
      0);
    v7 = -2147467259;
    goto LABEL_28;
  }
  for ( i = 0; *(&Keyword->Id + i); ++i )
  {
    if ( *(&Keyword->Id + i) == 44 )
    {
      *(&Keyword->Id + i) = 0;
      v11 = (CEventLogger *)v16;
      break;
    }
  }
  v4 = DuplicateString(*(const unsigned __int16 **)(*((_QWORD *)v11 + 2) + 40LL), a1);
  v7 = v4;
  if ( v4 < 0 )
  {
    v8 = 846;
    goto LABEL_5;
  }
LABEL_28:
  if ( v16 && v2 )
    v2();
  if ( v3 )
    FreeLibrary(v3);
  return v7;
}

```

## disassembly

```asm
0x180016eac  mov     [rsp+arg_8], rbx
0x180016eb1  mov     [rsp+arg_10], rbp
0x180016eb6  push    rsi
0x180016eb7  push    rdi
0x180016eb8  push    r14
0x180016eba  sub     rsp, 30h
0x180016ebe  xor     ebp, ebp
0x180016ec0  mov     r14, rcx
0x180016ec3  mov     esi, ebp
0x180016ec5  mov     [rsp+48h+arg_0], rbp
0x180016eca  mov     edi, ebp
0x180016ecc  mov     [rcx], rbp
0x180016ecf  call    ?IsW32TimeRunning@@YAJXZ; IsW32TimeRunning(void)
0x180016ed4  mov     ebx, eax
0x180016ed6  cmp     eax, 80070426h
0x180016edb  jnz     short loc_180016EE5
0x180016edd  lea     ebx, [rbp+1]
0x180016ee0  jmp     loc_180017036
0x180016ee5  test    eax, eax
0x180016ee7  jns     short loc_180016F10
0x180016ee9  mov     r9d, 323h; unsigned int
0x180016eef  mov     [rsp+48h+var_20], eax; unsigned int
0x180016ef3  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016efa  lea     rax, aGettimesyncsou; "GetTimeSyncSource"
0x180016f01  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180016f06  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016f0b  jmp     loc_180017036
0x180016f10  lea     rcx, aW32timeDll; "w32time.dll"
0x180016f17  call    cs:__imp_LoadLibraryW
0x180016f1d  mov     rdi, rax
0x180016f20  test    rax, rax
0x180016f23  jz      loc_18001700F
0x180016f29  lea     rdx, aW32timequerynt; "W32TimeQueryNTPProviderStatus"
0x180016f30  mov     rcx, rax; hModule
0x180016f33  call    cs:__imp_GetProcAddress
0x180016f39  mov     rbx, rax
0x180016f3c  test    rax, rax
0x180016f3f  jz      loc_180017007
0x180016f45  lea     rdx, aW32timebufferf; "W32TimeBufferFree"
0x180016f4c  mov     rcx, rdi; hModule
0x180016f4f  call    cs:__imp_GetProcAddress
0x180016f55  mov     rsi, rax
0x180016f58  test    rax, rax
0x180016f5b  jz      loc_180016FFF
0x180016f61  lea     r9, [rsp+48h+arg_0]
0x180016f66  xor     edx, edx
0x180016f68  lea     r8, aNtpclient; "NtpClient"
0x180016f6f  xor     ecx, ecx
0x180016f71  mov     rax, rbx
0x180016f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f79  test    eax, eax
0x180016f7b  jnz     short loc_180016FF7
0x180016f7d  mov     rcx, [rsp+48h+arg_0]
0x180016f82  lea     ebx, [rax+1]
0x180016f85  cmp     [rcx+0Ch], ebx
0x180016f88  jb      short loc_180016FEF
0x180016f8a  mov     rdx, [rcx+10h]
0x180016f8e  test    rdx, rdx
0x180016f91  jz      short loc_180016FE7
0x180016f93  mov     rdx, [rdx+28h]
0x180016f97  test    rdx, rdx
0x180016f9a  jz      short loc_180016FDF
0x180016f9c  mov     eax, ebp
0x180016f9e  mov     r8d, eax
0x180016fa1  cmp     [rdx+r8*2], bp
0x180016fa6  jz      short loc_180016FBE
0x180016fa8  cmp     word ptr [rdx+r8*2], 2Ch ; ','
0x180016fae  jz      short loc_180016FB4
0x180016fb0  add     eax, ebx
0x180016fb2  jmp     short loc_180016F9E
0x180016fb4  mov     [rdx+r8*2], bp
0x180016fb9  mov     rcx, [rsp+48h+arg_0]
0x180016fbe  mov     rcx, [rcx+10h]
0x180016fc2  mov     rdx, r14; unsigned __int16 **
0x180016fc5  mov     rcx, [rcx+28h]; Src
0x180016fc9  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180016fce  mov     ebx, eax
0x180016fd0  test    eax, eax
0x180016fd2  jns     short loc_180017036
0x180016fd4  mov     r9d, 34Eh
0x180016fda  jmp     loc_180016EEF
0x180016fdf  mov     r9d, 33Ah
0x180016fe5  jmp     short loc_180017015
0x180016fe7  mov     r9d, 339h
0x180016fed  jmp     short loc_180017015
0x180016fef  mov     r9d, 338h
0x180016ff5  jmp     short loc_180017015
0x180016ff7  mov     r9d, 337h
0x180016ffd  jmp     short loc_180017015
0x180016fff  mov     r9d, 330h
0x180017005  jmp     short loc_180017015
0x180017007  mov     r9d, 32Ch
0x18001700d  jmp     short loc_180017015
0x18001700f  mov     r9d, 326h; unsigned int
0x180017015  lea     rax, aGettimesyncsou; "GetTimeSyncSource"
0x18001701c  mov     [rsp+48h+var_20], ebp; unsigned int
0x180017020  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017027  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001702c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180017031  mov     ebx, 80004005h
0x180017036  mov     rcx, [rsp+48h+arg_0]
0x18001703b  test    rcx, rcx
0x18001703e  jz      short loc_18001704D
0x180017040  test    rsi, rsi
0x180017043  jz      short loc_18001704D
0x180017045  mov     rax, rsi
0x180017048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001704d  test    rdi, rdi
0x180017050  jz      short loc_18001705B
0x180017052  mov     rcx, rdi; hLibModule
0x180017055  call    cs:__imp_FreeLibrary
0x18001705b  mov     rbp, [rsp+48h+arg_10]
0x180017060  mov     eax, ebx
0x180017062  mov     rbx, [rsp+48h+arg_8]
0x180017067  add     rsp, 30h
0x18001706b  pop     r14
0x18001706d  pop     rdi
0x18001706e  pop     rsi
0x18001706f  retn
```
