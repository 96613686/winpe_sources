# InitGlobals(void)

- ea: `0x18001435c`
- end: `0x1800146d6`
- name: `?InitGlobals@@YAXXZ`
- size: `890`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004380`
- `0x180005168`
- `0x1800094d4`
- `0x1800183e0`
- `0x18001b700`

## callees

- `0x1800141bc`
- `0x18001435c`
- `0x1800146dc`
- `0x180014914`
- `0x1800149a0`
- `0x180014a6c`
- `0x18001abd8`
- `0x18001ae60`
- `0x18001aef4`
- `0x18001b050`
- `0x18001e178`
- `0x180020430`
- `0x1800222d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001463a`
- `msvcrt!swprintf_s` at `0x18001463a`
- `KERNEL32!EnterCriticalSection` at `0x18001438c`
- `KERNEL32!EnterCriticalSection` at `0x18001438c`
- `KERNEL32!LeaveCriticalSection` at `0x1800146b1`
- `KERNEL32!LeaveCriticalSection` at `0x1800146b1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800145db`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800145db`

## string_xrefs

- `0x180014495`: `MicrosoftEventVwrDisableLinks`
- `0x1800144f4`: `MicrosoftRedirectionProgramCommandLineParameters`
- `0x180014595`: `MicrosoftRedirectionProgramCommandLineParameters`
- `0x180014683`: `riched32.dll`

## pseudocode

```c
void InitGlobals(void)
{
  unsigned int i; // ebx
  bool v1; // bl
  bool v2; // di
  bool v3; // si
  CSynchWindow *v4; // rcx
  __int64 v5; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v6[2]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Src[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Format[264]; // [rsp+240h] [rbp+140h] BYREF

  EnterCriticalSection(&g_csInitFreeGlobals);
  for ( i = 0; i < 6; ++i )
    LoadStr(i + 202, (wchar_t *)&g_awszEventType + 50 * i, 0x32u, 0);
  LoadStr(0xF1u, (wchar_t *)&g_wszAll, 0x104u, 0);
  LoadStr(0xC9u, &g_wszNone, 0x104u, 0);
  LoadStr(0x7Du, &g_wszEventViewer, 0x104u, 0);
  LoadStr(0x156u, &g_wszSnapinType, 0x104u, 0);
  LoadStr(0x131u, &g_wszSnapinDescr, 0x104u, 0);
  InitMachineNameOverride();
  g_wszRedirectionURL = 0;
  g_wszRedirectionProgram = 0;
  g_wszRedirectionCmdLineParams = 0;
  g_wszRedirectionTextToAppend = 0;
  v5 = 0;
  v1 = 0;
  v2 = 0;
  v3 = 0;
  if ( !CSafeReg::Open((CSafeReg *)&v5, HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\EventViewer", 0x20019u) )
  {
    CSafeReg::QueryDword((CSafeReg *)&v5, L"MicrosoftEventVwrDisableLinks", &g_fSuppressURLs);
    if ( !(_BYTE)g_fSuppressURLs )
    {
      v1 = (unsigned int)CSafeReg::QueryStr((CSafeReg *)&v5, L"MicrosoftRedirectionURL", &g_wszRedirectionURL, 0x104u) == 0;
      v2 = (unsigned int)CSafeReg::QueryStr((CSafeReg *)&v5, L"MicrosoftRedirectionProgram", Src, 0x104u) == 0;
      v3 = (unsigned int)CSafeReg::QueryStr(
                           (CSafeReg *)&v5,
                           L"MicrosoftRedirectionProgramCommandLineParameters",
                           &g_wszRedirectionCmdLineParams,
                           0x104u) == 0;
    }
    CSafeReg::Close((CSafeReg *)&v5);
  }
  if ( !(_BYTE)g_fSuppressURLs )
  {
    if ( !CSafeReg::Open(
            (CSafeReg *)&v5,
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Event Viewer",
            0x20019u) )
    {
      if ( !v1 )
        CSafeReg::QueryStr((CSafeReg *)&v5, L"MicrosoftRedirectionURL", &g_wszRedirectionURL, 0x104u);
      if ( !v2 )
        CSafeReg::QueryStr((CSafeReg *)&v5, L"MicrosoftRedirectionProgram", Src, 0x104u);
      if ( !v3 )
        CSafeReg::QueryStr(
          (CSafeReg *)&v5,
          L"MicrosoftRedirectionProgramCommandLineParameters",
          &g_wszRedirectionCmdLineParams,
          0x104u);
      CSafeReg::Close((CSafeReg *)&v5);
    }
    if ( !g_wszRedirectionURL
      || !Src[0]
      || !g_wszRedirectionCmdLineParams
      || !ExpandEnvironmentStringsW(Src, &g_wszRedirectionProgram, 0x104u) )
    {
      g_wszRedirectionProgram = 0;
      g_wszRedirectionCmdLineParams = 0;
    }
    if ( g_wszRedirectionURL )
    {
      LoadStr(0x15Bu, Format, 0x104u, 0);
      if ( !Format[0] || swprintf_s(&g_wszRedirectionTextToAppend, 0x400u, Format, &g_wszRedirectionURL) < 0 )
      {
        g_wszRedirectionURL = 0;
        g_wszRedirectionProgram = 0;
        g_wszRedirectionCmdLineParams = 0;
        g_wszRedirectionTextToAppend = 0;
      }
    }
  }
  IsolationAwareInitCommonControls();
  v6[0] = 8;
  v6[1] = 268;
  IsolationAwareInitCommonControlsEx(v6);
  g_hinstRichEdit = IsolationAwareLoadLibraryW(L"riched32.dll");
  CSynchWindow::CreateSynchWindow(v4);
  InitExtension();
  CSafeReg::Close((CSafeReg *)&v5);
  LeaveCriticalSection(&g_csInitFreeGlobals);
}

```

## disassembly

```asm
0x18001435c  push    rbp
0x18001435e  push    rbx
0x18001435f  push    rsi
0x180014360  push    rdi
0x180014361  push    r14
0x180014363  push    r15
0x180014365  lea     rbp, [rsp-368h]
0x18001436d  sub     rsp, 468h
0x180014374  mov     rax, cs:__security_cookie
0x18001437b  xor     rax, rsp
0x18001437e  mov     [rbp+390h+var_40], rax
0x180014385  lea     rcx, ?g_csInitFreeGlobals@@3VCCritSecHolder@@A; lpCriticalSection
0x18001438c  call    cs:__imp_EnterCriticalSection
0x180014392  xor     r14d, r14d
0x180014395  mov     ebx, r14d
0x180014398  mov     eax, ebx
0x18001439a  lea     ecx, [rbx+0CAh]; uID
0x1800143a0  imul    rdx, rax, 64h ; 'd'
0x1800143a4  xor     r9d, r9d; Source
0x1800143a7  lea     rax, ?g_awszEventType@@3PAY0DC@GA; ushort (near * g_awszEventType)[50]
0x1800143ae  add     rdx, rax; Destination
0x1800143b1  lea     r8d, [r9+32h]; SizeInWords
0x1800143b5  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x1800143ba  inc     ebx
0x1800143bc  cmp     ebx, 6
0x1800143bf  jb      short loc_180014398
0x1800143c1  mov     r15d, 104h
0x1800143c7  lea     rdx, ?g_wszAll@@3PAGA; Destination
0x1800143ce  xor     r9d, r9d; Source
0x1800143d1  mov     r8d, r15d; SizeInWords
0x1800143d4  lea     ecx, [r15-13h]; uID
0x1800143d8  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x1800143dd  xor     r9d, r9d; Source
0x1800143e0  lea     rdx, ?g_wszNone@@3PAGA; Destination
0x1800143e7  mov     r8d, r15d; SizeInWords
0x1800143ea  lea     ecx, [r15-3Bh]; uID
0x1800143ee  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x1800143f3  xor     r9d, r9d; Source
0x1800143f6  lea     rdx, ?g_wszEventViewer@@3PAGA; Destination
0x1800143fd  mov     r8d, r15d; SizeInWords
0x180014400  lea     ecx, [r9+7Dh]; uID
0x180014404  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x180014409  xor     r9d, r9d; Source
0x18001440c  lea     rdx, ?g_wszSnapinType@@3PAGA; Destination
0x180014413  mov     r8d, r15d; SizeInWords
0x180014416  lea     ecx, [r15+52h]; uID
0x18001441a  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18001441f  xor     r9d, r9d; Source
0x180014422  lea     rdx, ?g_wszSnapinDescr@@3PAGA; Destination
0x180014429  mov     r8d, r15d; SizeInWords
0x18001442c  lea     ecx, [r15+2Dh]; uID
0x180014430  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x180014435  call    ?InitMachineNameOverride@@YAXXZ; InitMachineNameOverride(void)
0x18001443a  mov     r9d, 20019h; unsigned int
0x180014440  mov     cs:?g_wszRedirectionURL@@3PAGA, r14w; ushort near * g_wszRedirectionURL
0x180014448  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\EventVie"...
0x18001444f  mov     cs:?g_wszRedirectionProgram@@3PAGA, r14w; ushort near * g_wszRedirectionProgram
0x180014457  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001445e  mov     cs:?g_wszRedirectionCmdLineParams@@3PAGA, r14w; ushort near * g_wszRedirectionCmdLineParams
0x180014466  lea     rcx, [rsp+490h+var_470]; this
0x18001446b  mov     cs:?g_wszRedirectionTextToAppend@@3PAGA, r14w; ushort near * g_wszRedirectionTextToAppend
0x180014473  mov     [rsp+490h+var_470], r14
0x180014478  mov     bl, r14b
0x18001447b  mov     dil, r14b
0x18001447e  mov     sil, r14b
0x180014481  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180014486  test    eax, eax
0x180014488  jnz     loc_18001451A
0x18001448e  lea     r8, ?g_fSuppressURLs@@3_NA; unsigned int *
0x180014495  lea     rdx, aMicrosoftevent; "MicrosoftEventVwrDisableLinks"
0x18001449c  lea     rcx, [rsp+490h+var_470]; this
0x1800144a1  call    ?QueryDword@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryDword(ushort const *,ulong *)
0x1800144a6  cmp     cs:?g_fSuppressURLs@@3_NA, r14b; bool g_fSuppressURLs
0x1800144ad  jnz     short loc_180014510
0x1800144af  mov     r9d, r15d; unsigned int
0x1800144b2  lea     r8, ?g_wszRedirectionURL@@3PAGA; unsigned __int16 *
0x1800144b9  lea     rdx, aMicrosoftredir_0; "MicrosoftRedirectionURL"
0x1800144c0  lea     rcx, [rsp+490h+var_470]; this
0x1800144c5  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x1800144ca  test    eax, eax
0x1800144cc  lea     r8, [rsp+490h+Src]; unsigned __int16 *
0x1800144d1  mov     r9d, r15d; unsigned int
0x1800144d4  lea     rdx, aMicrosoftredir; "MicrosoftRedirectionProgram"
0x1800144db  lea     rcx, [rsp+490h+var_470]; this
0x1800144e0  setz    bl
0x1800144e3  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x1800144e8  test    eax, eax
0x1800144ea  lea     r8, ?g_wszRedirectionCmdLineParams@@3PAGA; unsigned __int16 *
0x1800144f1  mov     r9d, r15d; unsigned int
0x1800144f4  lea     rdx, aMicrosoftredir_1; "MicrosoftRedirectionProgramCommandLineP"...
0x1800144fb  lea     rcx, [rsp+490h+var_470]; this
0x180014500  setz    dil
0x180014504  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x180014509  test    eax, eax
0x18001450b  jnz     short loc_180014510
0x18001450d  mov     sil, 1
0x180014510  lea     rcx, [rsp+490h+var_470]; this
0x180014515  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001451a  cmp     cs:?g_fSuppressURLs@@3_NA, r14b; bool g_fSuppressURLs
0x180014521  jnz     loc_180014664
0x180014527  mov     r9d, 20019h; unsigned int
0x18001452d  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180014534  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001453b  lea     rcx, [rsp+490h+var_470]; this
0x180014540  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180014545  test    eax, eax
0x180014547  jnz     short loc_1800145B0
0x180014549  test    bl, bl
0x18001454b  jnz     short loc_180014568
0x18001454d  mov     r9d, r15d; unsigned int
0x180014550  lea     r8, ?g_wszRedirectionURL@@3PAGA; unsigned __int16 *
0x180014557  lea     rdx, aMicrosoftredir_0; "MicrosoftRedirectionURL"
0x18001455e  lea     rcx, [rsp+490h+var_470]; this
0x180014563  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x180014568  test    dil, dil
0x18001456b  jnz     short loc_180014586
0x18001456d  mov     r9d, r15d; unsigned int
0x180014570  lea     r8, [rsp+490h+Src]; unsigned __int16 *
0x180014575  lea     rdx, aMicrosoftredir; "MicrosoftRedirectionProgram"
0x18001457c  lea     rcx, [rsp+490h+var_470]; this
0x180014581  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x180014586  test    sil, sil
0x180014589  jnz     short loc_1800145A6
0x18001458b  mov     r9d, r15d; unsigned int
0x18001458e  lea     r8, ?g_wszRedirectionCmdLineParams@@3PAGA; unsigned __int16 *
0x180014595  lea     rdx, aMicrosoftredir_1; "MicrosoftRedirectionProgramCommandLineP"...
0x18001459c  lea     rcx, [rsp+490h+var_470]; this
0x1800145a1  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x1800145a6  lea     rcx, [rsp+490h+var_470]; this
0x1800145ab  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800145b0  cmp     cs:?g_wszRedirectionURL@@3PAGA, r14w; ushort near * g_wszRedirectionURL
0x1800145b8  jz      short loc_1800145E5
0x1800145ba  cmp     [rsp+490h+Src], r14w
0x1800145c0  jz      short loc_1800145E5
0x1800145c2  cmp     cs:?g_wszRedirectionCmdLineParams@@3PAGA, r14w; ushort near * g_wszRedirectionCmdLineParams
0x1800145ca  jz      short loc_1800145E5
0x1800145cc  mov     r8d, r15d; nSize
0x1800145cf  lea     rdx, ?g_wszRedirectionProgram@@3PAGA; lpDst
0x1800145d6  lea     rcx, [rsp+490h+Src]; lpSrc
0x1800145db  call    cs:__imp_ExpandEnvironmentStringsW
0x1800145e1  test    eax, eax
0x1800145e3  jnz     short loc_1800145F5
0x1800145e5  mov     cs:?g_wszRedirectionProgram@@3PAGA, r14w; ushort near * g_wszRedirectionProgram
0x1800145ed  mov     cs:?g_wszRedirectionCmdLineParams@@3PAGA, r14w; ushort near * g_wszRedirectionCmdLineParams
0x1800145f5  cmp     cs:?g_wszRedirectionURL@@3PAGA, r14w; ushort near * g_wszRedirectionURL
0x1800145fd  jz      short loc_180014664
0x1800145ff  xor     r9d, r9d; Source
0x180014602  lea     rdx, [rbp+390h+Format]; Destination
0x180014609  mov     r8d, r15d; SizeInWords
0x18001460c  mov     ecx, 15Bh; uID
0x180014611  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x180014616  cmp     [rbp+390h+Format], r14w
0x18001461e  jz      short loc_180014644
0x180014620  lea     r9, ?g_wszRedirectionURL@@3PAGA; ushort near * g_wszRedirectionURL
0x180014627  mov     edx, 400h; BufferCount
0x18001462c  lea     r8, [rbp+390h+Format]; Format
0x180014633  lea     rcx, ?g_wszRedirectionTextToAppend@@3PAGA; Buffer
0x18001463a  call    cs:__imp_swprintf_s
0x180014640  test    eax, eax
0x180014642  jns     short loc_180014664
0x180014644  mov     cs:?g_wszRedirectionURL@@3PAGA, r14w; ushort near * g_wszRedirectionURL
0x18001464c  mov     cs:?g_wszRedirectionProgram@@3PAGA, r14w; ushort near * g_wszRedirectionProgram
0x180014654  mov     cs:?g_wszRedirectionCmdLineParams@@3PAGA, r14w; ushort near * g_wszRedirectionCmdLineParams
0x18001465c  mov     cs:?g_wszRedirectionTextToAppend@@3PAGA, r14w; ushort near * g_wszRedirectionTextToAppend
0x180014664  call    IsolationAwareInitCommonControls
0x180014669  lea     rcx, [rsp+490h+var_468]
0x18001466e  mov     [rsp+490h+var_468], 8
0x180014676  mov     [rsp+490h+var_464], 10Ch
0x18001467e  call    IsolationAwareInitCommonControlsEx
0x180014683  lea     rcx, aRiched32Dll; "riched32.dll"
0x18001468a  call    IsolationAwareLoadLibraryW
0x18001468f  mov     cs:?g_hinstRichEdit@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstRichEdit
0x180014696  call    ?CreateSynchWindow@CSynchWindow@@QEAAJXZ; CSynchWindow::CreateSynchWindow(void)
0x18001469b  call    ?InitExtension@@YAXXZ; InitExtension(void)
0x1800146a0  lea     rcx, [rsp+490h+var_470]; this
0x1800146a5  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800146aa  lea     rcx, ?g_csInitFreeGlobals@@3VCCritSecHolder@@A; lpCriticalSection
0x1800146b1  call    cs:__imp_LeaveCriticalSection
0x1800146b7  mov     rcx, [rbp+390h+var_40]
0x1800146be  xor     rcx, rsp; StackCookie
0x1800146c1  call    __security_check_cookie
0x1800146c6  add     rsp, 468h
0x1800146cd  pop     r15
0x1800146cf  pop     r14
0x1800146d1  pop     rdi
0x1800146d2  pop     rsi
0x1800146d3  pop     rbx
0x1800146d4  pop     rbp
0x1800146d5  retn
```
