# IDNATargetInfo::InitializeCommandTree(void)

- ea: `0x1802623f4`
- end: `0x180262615`
- name: `?InitializeCommandTree@IDNATargetInfo@@IEAAJXZ`
- size: `545`
- prototype: `__int64 __fastcall(IDNATargetInfo *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18023f4e0`

## callees

- `0x1800b94c4`
- `0x1800f0f40`
- `0x18019679c`
- `0x18026059c`
- `0x180261384`
- `0x1802623f4`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802624cf`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802624ed`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802624cf`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802624ed`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180262442`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180262442`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180262461`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180262461`

## string_xrefs

- `0x180262515`: `<b>* other than WinDBG or WinDBGX. Consequently the .cmdtree command is ***\n</b>`
- `0x18026252d`: `<b>* you can open in a text editor as a workaround:                     ***\n</b>`
- `0x180262569`: `<b>* Time Travel Tracing Timeline available. Windbg command:          ***\n</b>`
- `0x180262588`: `<b>* <link cmd=".cmdtree %s">.cmdtree %s</link>\n</b>`
- `0x1802625cc`: `<b>* Time Travel Tracing Timeline may be available. Windbg command:   ***\n</b>`
- `0x180262457`: `CreateDbgCmdTree`
- `0x18026243b`: `TTTraceReader.DLL`

## pseudocode

```c
__int64 __fastcall IDNATargetInfo::InitializeCommandTree(IDNATargetInfo *this)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  FARPROC ProcAddress; // rbx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // edx
  unsigned __int16 v10[264]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v11[624]; // [rsp+240h] [rbp+140h] BYREF
  wchar_t String1[1024]; // [rsp+720h] [rbp+620h] BYREF

  memset(v10, 0, 520);
  ModuleHandleW = GetModuleHandleW(L"TTTraceReader.DLL");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CreateDbgCmdTree");
    if ( ProcAddress )
    {
      if ( !*((_QWORD *)this + 528) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v6, v7);
      if ( !((unsigned int (__fastcall *)(_QWORD, unsigned __int16 *, __int64, _QWORD))ProcAddress)(
              *((_QWORD *)this + 528),
              v10,
              260,
              0) )
      {
        if ( (unsigned int)GetIDNAHostName(String1, v8) )
        {
          DmlOut(L"<b>**********************************************************************\n</b>");
          DmlOut(L"<b>* Unable to determine if WinDBG is executing.                      ***\n</b>");
          DmlOut(L"<b>* Time Travel Tracing Timeline may be available. Windbg command:   ***\n</b>");
          DmlOut(L"<b>.cmdtree %s\n</b>", v10);
        }
        else
        {
          if ( _wcsicmp(String1, L"windbg.exe") && _wcsicmp(String1, L"enghost.exe") )
          {
            DmlOut(L"<b>************************************************************************\n</b>");
            DmlOut(L"<b>* Time Travel Tracing Timeline is not yet implemented in clients     ***\n</b>");
            DmlOut(L"<b>* other than WinDBG or WinDBGX. Consequently the .cmdtree command is ***\n</b>");
            DmlOut(L"<b>* currently unavailable. The timeline is stored in a text file which ***\n</b>");
            DmlOut(L"<b>* you can open in a text editor as a workaround:                     ***\n</b>");
            DmlOut(L"<b>*   %s\n</b>", v10);
            DmlOut(L"<b>************************************************************************\n</b>");
            return 0;
          }
          DmlOut(L"<b>**********************************************************************\n</b>");
          DmlOut(L"<b>* Time Travel Tracing Timeline available. Windbg command:          ***\n</b>");
          if ( (unsigned int)_snwprintf_s<620>(
                               v11,
                               -1,
                               L"<b>* <link cmd=\".cmdtree %s\">.cmdtree %s</link>\n</b>",
                               v10,
                               v10) )
            DmlOut(v11);
        }
        DmlOut(L"<b>**********************************************************************\n</b>");
        return 0;
      }
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1802623f4  mov     [rsp-8+arg_8], rbx
0x1802623f9  mov     [rsp-8+arg_10], rdi
0x1802623fe  push    rbp
0x1802623ff  lea     rbp, [rsp-0E30h]
0x180262407  sub     rsp, 0F30h
0x18026240e  mov     rax, cs:__security_cookie
0x180262415  xor     rax, rsp
0x180262418  mov     [rbp+0E30h+var_10], rax
0x18026241f  mov     rdi, rcx
0x180262422  xor     eax, eax
0x180262424  lea     rcx, [rsp+0F30h+var_EFE]; void *
0x180262429  mov     [rsp+0F30h+var_F00], ax
0x18026242e  xor     edx, edx; Val
0x180262430  mov     r8d, 206h; Size
0x180262436  call    memset
0x18026243b  lea     rcx, aTttracereaderD; "TTTraceReader.DLL"
0x180262442  call    cs:__imp_GetModuleHandleW
0x180262449  nop     dword ptr [rax+rax+00h]
0x18026244e  test    rax, rax
0x180262451  jz      loc_1802625EB
0x180262457  lea     rdx, aCreatedbgcmdtr; "CreateDbgCmdTree"
0x18026245e  mov     rcx, rax; hModule
0x180262461  call    cs:__imp_GetProcAddress
0x180262468  nop     dword ptr [rax+rax+00h]
0x18026246d  mov     rbx, rax
0x180262470  test    rax, rax
0x180262473  jz      loc_1802625EB
0x180262479  cmp     qword ptr [rdi+1080h], 0
0x180262481  jnz     short loc_180262488
0x180262483  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180262488  mov     rcx, [rdi+1080h]
0x18026248f  lea     rdx, [rsp+0F30h+var_F00]
0x180262494  xor     r9d, r9d
0x180262497  mov     r8d, 104h
0x18026249d  mov     rax, rbx
0x1802624a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802624a5  test    eax, eax
0x1802624a7  jnz     loc_1802625EB
0x1802624ad  lea     rcx, [rbp+0E30h+String1]; unsigned __int16 *
0x1802624b4  call    ?GetIDNAHostName@@YAJPEAGK@Z; GetIDNAHostName(ushort *,ulong)
0x1802624b9  test    eax, eax
0x1802624bb  jnz     loc_1802625B4
0x1802624c1  lea     rdx, aWindbgExe; "windbg.exe"
0x1802624c8  lea     rcx, [rbp+0E30h+String1]; String1
0x1802624cf  call    cs:__imp__wcsicmp
0x1802624d6  nop     dword ptr [rax+rax+00h]
0x1802624db  test    eax, eax
0x1802624dd  jz      short loc_18026255D
0x1802624df  lea     rdx, aEnghostExe; "enghost.exe"
0x1802624e6  lea     rcx, [rbp+0E30h+String1]; String1
0x1802624ed  call    cs:__imp__wcsicmp
0x1802624f4  nop     dword ptr [rax+rax+00h]
0x1802624f9  test    eax, eax
0x1802624fb  jz      short loc_18026255D
0x1802624fd  lea     rcx, aB_0; "<b>************************************"...
0x180262504  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262509  lea     rcx, aBTimeTravelTra_0; "<b>* Time Travel Tracing Timeline is no"...
0x180262510  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262515  lea     rcx, aBOtherThanWind; "<b>* other than WinDBG or WinDBGX. Cons"...
0x18026251c  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262521  lea     rcx, aBCurrentlyUnav; "<b>* currently unavailable. The timelin"...
0x180262528  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x18026252d  lea     rcx, aBYouCanOpenInA; "<b>* you can open in a text editor as a"...
0x180262534  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262539  lea     rdx, [rsp+0F30h+var_F00]
0x18026253e  lea     rcx, aBSB; "<b>*   %s\n</b>"
0x180262545  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x18026254a  lea     rcx, aB_0; "<b>************************************"...
0x180262551  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262556  xor     eax, eax
0x180262558  jmp     loc_1802625F0
0x18026255d  lea     rcx, aB_8; "<b>************************************"...
0x180262564  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262569  lea     rcx, aBTimeTravelTra; "<b>* Time Travel Tracing Timeline avail"...
0x180262570  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x180262575  lea     rax, [rsp+0F30h+var_F00]
0x18026257a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18026257e  lea     r9, [rsp+0F30h+var_F00]
0x180262583  mov     [rsp+0F30h+var_F10], rax
0x180262588  lea     r8, aBLinkCmdCmdtre; "<b>* <link cmd=\".cmdtree %s\">.cmdtree"...
0x18026258f  lea     rcx, [rbp+0E30h+var_CF0]
0x180262596  call    ??$_snwprintf_s@$0CGM@@@YAHAEAY0CGM@G_KPEBGZZ; _snwprintf_s<620>(ushort (&)[620],unsigned __int64,ushort const *,...)
0x18026259b  test    eax, eax
0x18026259d  jz      short loc_1802625AB
0x18026259f  lea     rcx, [rbp+0E30h+var_CF0]; unsigned __int16 *
0x1802625a6  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802625ab  lea     rcx, aB_8; "<b>************************************"...
0x1802625b2  jmp     short loc_180262551
0x1802625b4  lea     rcx, aB_8; "<b>************************************"...
0x1802625bb  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802625c0  lea     rcx, aBUnableToDeter; "<b>* Unable to determine if WinDBG is e"...
0x1802625c7  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802625cc  lea     rcx, aBTimeTravelTra_1; "<b>* Time Travel Tracing Timeline may b"...
0x1802625d3  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802625d8  lea     rdx, [rsp+0F30h+var_F00]
0x1802625dd  lea     rcx, aBCmdtreeSB; "<b>.cmdtree %s\n</b>"
0x1802625e4  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802625e9  jmp     short loc_1802625AB
0x1802625eb  mov     eax, 80004005h
0x1802625f0  mov     rcx, [rbp+0E30h+var_10]
0x1802625f7  xor     rcx, rsp; StackCookie
0x1802625fa  call    __security_check_cookie
0x1802625ff  lea     r11, [rsp+0F30h+var_s0]
0x180262607  mov     rbx, [r11+18h]
0x18026260b  mov     rdi, [r11+20h]
0x18026260f  mov     rsp, r11
0x180262612  pop     rbp
0x180262613  retn
```
