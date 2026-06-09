# MsiUIMessageContext::ChildUIThread(MsiUIMessageContext *)

- ea: `0x180008d90`
- end: `0x180009195`
- name: `?ChildUIThread@MsiUIMessageContext@@CAKPEAU1@@Z`
- size: `1029`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x180008d90`
- `0x180009c38`
- `0x18000c4bc`
- `0x180027634`
- `0x18009436c`
- `0x180120824`
- `0x18015c964`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x180008fa6`
- `KERNEL32!GetExitCodeThread` at `0x180008fa6`
- `KERNEL32!GetLastError` at `0x18000901b`
- `KERNEL32!GetLastError` at `0x180009132`
- `KERNEL32!GetLastError` at `0x18000901b`
- `KERNEL32!GetLastError` at `0x180009132`
- `KERNEL32!WaitForSingleObject` at `0x180008eed`
- `KERNEL32!WaitForSingleObject` at `0x180008eed`
- `KERNEL32!GetModuleFileNameW` at `0x180008dff`
- `KERNEL32!GetModuleFileNameW` at `0x180008dff`
- `KERNEL32!SetEvent` at `0x18000911b`
- `KERNEL32!SetEvent` at `0x18000911b`
- `KERNEL32!WaitForMultipleObjects` at `0x180008ed5`
- `KERNEL32!WaitForMultipleObjects` at `0x180008ed5`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180009188`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180009188`

## string_xrefs

- `0x18000914d`: `Wait Failed in ChildUIThread. GetLastError returned %d.`
- `0x180008f5e`: `ChildUIThread wait timed out`
- `0x180008fd1`: `hMainThread is gone. ChildUIThread will finish as well.`
- `0x18000902c`: `GetExitCodeThread returned %d in MsiUIMessageContext::ChildUIThread`
- `0x180009090`: `Invalid event trigger in ChildUIThread`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::ChildUIThread(unsigned int *Parameter)
{
  unsigned int v1; // eax
  HMODULE LibraryW; // r15
  bool v4; // r8
  DWORD v6; // ebp
  int v7; // esi
  char v8; // r14
  DWORD v9; // eax
  CBasicUI *v10; // rcx
  void *v11; // rcx
  DWORD LastError; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // r8
  DWORD v16; // eax
  unsigned int v17; // [rsp+50h] [rbp-288h]
  void *v18; // [rsp+58h] [rbp-280h]
  DWORD ExitCode[4]; // [rsp+60h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-268h] BYREF

  v1 = Parameter[47];
  if ( v1 == 5 )
  {
    Parameter[47] = 0;
LABEL_3:
    if ( !*((_BYTE *)Parameter + 229) && (int)((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0) >= 0 )
      *((_BYTE *)Parameter + 229) = 1;
    if ( GetModuleFileNameW(g_hInstance, Filename, 0x103u) )
    {
      Filename[259] = 0;
      LibraryW = (HMODULE)IsolationAwareLoadLibraryW(Filename);
    }
    else
    {
      LibraryW = 0;
    }
    v6 = 0;
    v7 = 0;
    v8 = 1;
    while ( 1 )
    {
      v9 = *((_QWORD *)Parameter + 10)
         ? WaitForMultipleObjects(2u, (const HANDLE *)Parameter + 9, 0, g_iUIWaitTick)
         : WaitForSingleObject(*((HANDLE *)Parameter + 9), g_iUIWaitTick);
      if ( v9 == -1 )
        break;
      if ( v9 == 258 )
      {
        if ( !*((_QWORD *)Parameter + 21) )
          MsiUIMessageContext::ProcessMessage(Parameter, 167772160, &off_18030FDB0);
        if ( !Parameter[48] )
        {
          v7 += g_iUITicksStep;
          if ( v7 >= g_cWaitTimeout )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                "ChildUIThread wait timed out",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                v17,
                v18);
            v7 = 0;
          }
        }
      }
      else if ( v9 == 1 )
      {
        v11 = (void *)*((_QWORD *)Parameter + 10);
        ExitCode[0] = 0;
        if ( GetExitCodeThread(v11, ExitCode) )
        {
          if ( ExitCode[0] != 259 )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"hMainThread is gone. ChildUIThread will finish as well.",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            v8 = 0;
          }
        }
        else if ( g_dmDiagnosticMode )
        {
          LastError = GetLastError();
          DebugString(
            9,
            0,
            0,
            L"GetExitCodeThread returned %d in MsiUIMessageContext::ChildUIThread",
            (const unsigned __int16 *)LastError,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      else
      {
        v13 = Parameter[16];
        v7 = 0;
        if ( (_DWORD)v13 == 0x80000000 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              "Invalid event trigger in ChildUIThread",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              v17,
              v18);
        }
        else
        {
          if ( (_DWORD)v13 == 251658549 )
          {
            if ( byte_180310E64 )
              CBasicUI::Terminate(v10);
            if ( *((_BYTE *)Parameter + 229) == 1 )
            {
              OLE32::CoUninitialize();
              *((_BYTE *)Parameter + 229) = 0;
            }
            v8 = 0;
            v14 = 0;
          }
          else
          {
            v15 = *((_QWORD *)Parameter + 7);
            Parameter[36] = -2147483647;
            v14 = MsiUIMessageContext::ProcessMessage(Parameter, v13, v15);
            Parameter[16] = 0x80000000;
          }
          Parameter[36] = v14;
          SetEvent(*((HANDLE *)Parameter + 11));
        }
      }
      if ( !v8 )
        goto LABEL_50;
    }
    v16 = GetLastError();
    v6 = v16;
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Wait Failed in ChildUIThread. GetLastError returned %d.",
        (const unsigned __int16 *)v16,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
LABEL_50:
    FreeLibraryAndExitThread(LibraryW, v6);
  }
  if ( v1 == 3 || (v4 = 0, v1 == 0x2000) )
    v4 = 1;
  if ( CBasicUI::Initialize(
         (CBasicUI *)Parameter,
         qword_1803138F8,
         v4,
         *((_BYTE *)Parameter + 204),
         *((_BYTE *)Parameter + 313),
         *((_BYTE *)Parameter + 224),
         *((_BYTE *)Parameter + 225),
         *((_BYTE *)Parameter + 226)) )
  {
    goto LABEL_3;
  }
  return 1631;
}

```

## disassembly

```asm
0x180008d90  push    rbx
0x180008d92  push    rbp
0x180008d93  push    rsi
0x180008d94  push    rdi
0x180008d95  push    r12
0x180008d97  push    r13
0x180008d99  push    r14
0x180008d9b  push    r15
0x180008d9d  sub     rsp, 298h
0x180008da4  mov     rax, cs:__security_cookie
0x180008dab  xor     rax, rsp
0x180008dae  mov     [rsp+2D8h+var_58], rax
0x180008db6  mov     eax, [rcx+0BCh]
0x180008dbc  xor     ebx, ebx
0x180008dbe  mov     rdi, rcx
0x180008dc1  cmp     eax, 5
0x180008dc4  jnz     short loc_180008E1B
0x180008dc6  mov     [rcx+0BCh], ebx
0x180008dcc  cmp     [rdi+0E5h], bl
0x180008dd2  jnz     short loc_180008DED
0x180008dd4  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x180008ddb  xor     ecx, ecx
0x180008ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de2  test    eax, eax
0x180008de4  js      short loc_180008DED
0x180008de6  mov     byte ptr [rdi+0E5h], 1
0x180008ded  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180008df4  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x180008df9  mov     r8d, 103h; nSize
0x180008dff  call    cs:__imp_GetModuleFileNameW
0x180008e06  nop     dword ptr [rax+rax+00h]
0x180008e0b  test    eax, eax
0x180008e0d  jnz     loc_180008E9A
0x180008e13  mov     r15, rbx
0x180008e16  jmp     loc_180008EAF
0x180008e1b  cmp     eax, 3
0x180008e1e  jz      short loc_180008E2A
0x180008e20  mov     r8b, bl
0x180008e23  cmp     eax, 2000h
0x180008e28  jnz     short loc_180008E2D
0x180008e2a  mov     r8b, 1; bool
0x180008e2d  mov     al, [rcx+0E2h]
0x180008e33  mov     r9b, [rcx+0CCh]; bool
0x180008e3a  mov     rdx, cs:qword_1803138F8; HWND
0x180008e41  mov     byte ptr [rsp+2D8h+var_2A0], al; bool
0x180008e45  mov     al, [rcx+0E1h]
0x180008e4b  mov     byte ptr [rsp+2D8h+var_2A8], al; bool
0x180008e4f  mov     al, [rcx+0E0h]
0x180008e55  mov     byte ptr [rsp+2D8h+var_2B0], al; bool
0x180008e59  mov     al, [rcx+139h]
0x180008e5f  mov     byte ptr [rsp+2D8h+var_2B8], al; bool
0x180008e63  call    ?Initialize@CBasicUI@@QEAA_NPEAUHWND__@@_N11111@Z; CBasicUI::Initialize(HWND__ *,bool,bool,bool,bool,bool,bool)
0x180008e68  test    al, al
0x180008e6a  jnz     loc_180008DCC
0x180008e70  mov     eax, 65Fh
0x180008e75  mov     rcx, [rsp+2D8h+var_58]
0x180008e7d  xor     rcx, rsp; StackCookie
0x180008e80  call    __security_check_cookie
0x180008e85  add     rsp, 298h
0x180008e8c  pop     r15
0x180008e8e  pop     r14
0x180008e90  pop     r13
0x180008e92  pop     r12
0x180008e94  pop     rdi
0x180008e95  pop     rsi
0x180008e96  pop     rbp
0x180008e97  pop     rbx
0x180008e98  retn
0x180008e9a  lea     rcx, [rsp+2D8h+Filename]; lpLibFileName
0x180008e9f  mov     [rsp+2D8h+var_62], bx
0x180008ea7  call    IsolationAwareLoadLibraryW
0x180008eac  mov     r15, rax
0x180008eaf  mov     ebp, ebx
0x180008eb1  lea     r13, aNull; "(NULL)"
0x180008eb8  mov     esi, ebx
0x180008eba  mov     r14b, 1
0x180008ebd  cmp     [rdi+50h], rbx
0x180008ec1  jz      short loc_180008EE3
0x180008ec3  mov     r9d, cs:?g_iUIWaitTick@@3HA; dwMilliseconds
0x180008eca  lea     rdx, [rdi+48h]; lpHandles
0x180008ece  xor     r8d, r8d; bWaitAll
0x180008ed1  lea     ecx, [r8+2]; nCount
0x180008ed5  call    cs:__imp_WaitForMultipleObjects
0x180008edc  nop     dword ptr [rax+rax+00h]
0x180008ee1  jmp     short loc_180008EF9
0x180008ee3  mov     edx, cs:?g_iUIWaitTick@@3HA; dwMilliseconds
0x180008ee9  mov     rcx, [rdi+48h]; hHandle
0x180008eed  call    cs:__imp_WaitForSingleObject
0x180008ef4  nop     dword ptr [rax+rax+00h]
0x180008ef9  cmp     eax, 0FFFFFFFFh
0x180008efc  jz      loc_180009132
0x180008f02  cmp     eax, 102h
0x180008f07  jnz     loc_180008F90
0x180008f0d  cmp     [rdi+0A8h], rbx
0x180008f14  jnz     short loc_180008F2A
0x180008f16  lea     r8, off_18030FDB0
0x180008f1d  mov     edx, 0A000000h
0x180008f22  mov     rcx, rdi
0x180008f25  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x180008f2a  cmp     [rdi+0C0h], ebx
0x180008f30  jnz     loc_180009127
0x180008f36  add     esi, cs:?g_iUITicksStep@@3HA; int g_iUITicksStep
0x180008f3c  cmp     esi, cs:?g_cWaitTimeout@@3HA; int g_cWaitTimeout
0x180008f42  jl      loc_180009127
0x180008f48  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180008f4e  jz      short loc_180008F89
0x180008f50  lea     rax, aNull_0; "(NULL)"
0x180008f57  xor     edx, edx; unsigned __int16
0x180008f59  mov     [rsp+2D8h+var_290], rax; char *
0x180008f5e  lea     r9, aChilduithreadW; "ChildUIThread wait timed out"
0x180008f65  mov     [rsp+2D8h+var_298], rax; char *
0x180008f6a  xor     r8d, r8d; int
0x180008f6d  mov     [rsp+2D8h+var_2A0], rax; char *
0x180008f72  mov     [rsp+2D8h+var_2A8], rax; char *
0x180008f77  lea     ecx, [rdx+9]; int
0x180008f7a  mov     [rsp+2D8h+var_2B0], rax; char *
0x180008f7f  mov     [rsp+2D8h+var_2B8], rax; char *
0x180008f84  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180008f89  mov     esi, ebx
0x180008f8b  jmp     loc_180009127
0x180008f90  cmp     eax, 1
0x180008f93  jnz     loc_180009069
0x180008f99  mov     rcx, [rdi+50h]; hThread
0x180008f9d  lea     rdx, [rsp+2D8h+ExitCode]; lpExitCode
0x180008fa2  mov     [rsp+2D8h+ExitCode], ebx
0x180008fa6  call    cs:__imp_GetExitCodeThread
0x180008fad  nop     dword ptr [rax+rax+00h]
0x180008fb2  test    eax, eax
0x180008fb4  jz      short loc_18000900F
0x180008fb6  cmp     [rsp+2D8h+ExitCode], 103h
0x180008fbe  jz      loc_180009127
0x180008fc4  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180008fca  jz      short loc_180009007
0x180008fcc  mov     [rsp+2D8h+var_280], rbx; void *
0x180008fd1  lea     r9, aHmainthreadIsG; "hMainThread is gone. ChildUIThread will"...
0x180008fd8  mov     [rsp+2D8h+var_288], ebx; unsigned int
0x180008fdc  xor     edx, edx; unsigned __int16
0x180008fde  mov     [rsp+2D8h+var_290], r13; unsigned __int16 *
0x180008fe3  xor     r8d, r8d; int
0x180008fe6  mov     [rsp+2D8h+var_298], r13; unsigned __int16 *
0x180008feb  mov     [rsp+2D8h+var_2A0], r13; unsigned __int16 *
0x180008ff0  mov     [rsp+2D8h+var_2A8], r13; unsigned __int16 *
0x180008ff5  lea     ecx, [rdx+9]; int
0x180008ff8  mov     [rsp+2D8h+var_2B0], r13; unsigned __int16 *
0x180008ffd  mov     [rsp+2D8h+var_2B8], r13; unsigned __int16 *
0x180009002  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180009007  mov     r14b, bl
0x18000900a  jmp     loc_180009127
0x18000900f  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180009015  jz      loc_180009127
0x18000901b  call    cs:__imp_GetLastError
0x180009022  nop     dword ptr [rax+rax+00h]
0x180009027  mov     [rsp+2D8h+var_280], rbx; void *
0x18000902c  lea     r9, aGetexitcodethr; "GetExitCodeThread returned %d in MsiUIM"...
0x180009033  mov     [rsp+2D8h+var_288], ebx; unsigned int
0x180009037  xor     edx, edx; unsigned __int16
0x180009039  mov     [rsp+2D8h+var_290], r13; unsigned __int16 *
0x18000903e  xor     r8d, r8d; int
0x180009041  mov     [rsp+2D8h+var_298], r13; unsigned __int16 *
0x180009046  mov     [rsp+2D8h+var_2A0], r13; unsigned __int16 *
0x18000904b  mov     [rsp+2D8h+var_2A8], r13; unsigned __int16 *
0x180009050  lea     ecx, [rdx+9]; int
0x180009053  mov     eax, eax
0x180009055  mov     [rsp+2D8h+var_2B0], r13; unsigned __int16 *
0x18000905a  mov     [rsp+2D8h+var_2B8], rax; unsigned __int16 *
0x18000905f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180009064  jmp     loc_180009127
0x180009069  mov     edx, [rdi+40h]
0x18000906c  mov     esi, ebx
0x18000906e  cmp     edx, 80000000h
0x180009074  jnz     short loc_1800090BD
0x180009076  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18000907c  jz      loc_180009127
0x180009082  lea     rax, aNull_0; "(NULL)"
0x180009089  xor     edx, edx; unsigned __int16
0x18000908b  mov     [rsp+2D8h+var_290], rax; char *
0x180009090  lea     r9, aInvalidEventTr_0; "Invalid event trigger in ChildUIThread"
0x180009097  mov     [rsp+2D8h+var_298], rax; char *
0x18000909c  xor     r8d, r8d; int
0x18000909f  mov     [rsp+2D8h+var_2A0], rax; char *
0x1800090a4  mov     [rsp+2D8h+var_2A8], rax; char *
0x1800090a9  lea     ecx, [rdx+9]; int
0x1800090ac  mov     [rsp+2D8h+var_2B0], rax; char *
0x1800090b1  mov     [rsp+2D8h+var_2B8], rax; char *
0x1800090b6  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1800090bb  jmp     short loc_180009127
0x1800090bd  cmp     edx, 0F000135h
0x1800090c3  jnz     short loc_1800090F4
0x1800090c5  cmp     cs:byte_180310E64, bl
0x1800090cb  jz      short loc_1800090D2
0x1800090cd  call    ?Terminate@CBasicUI@@QEAA_NXZ; CBasicUI::Terminate(void)
0x1800090d2  cmp     byte ptr [rdi+0E5h], 1
0x1800090d9  jnz     short loc_1800090ED
0x1800090db  mov     rax, cs:?CoUninitialize@OLE32@@3P6AXXZEA; void (*OLE32::CoUninitialize)(void)
0x1800090e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e7  mov     [rdi+0E5h], bl
0x1800090ed  mov     r14b, bl
0x1800090f0  mov     eax, ebx
0x1800090f2  jmp     short loc_180009111
0x1800090f4  mov     r8, [rdi+38h]
0x1800090f8  mov     rcx, rdi
0x1800090fb  mov     dword ptr [rdi+90h], 80000001h
0x180009105  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x18000910a  mov     dword ptr [rdi+40h], 80000000h
0x180009111  mov     [rdi+90h], eax
0x180009117  mov     rcx, [rdi+58h]; hEvent
0x18000911b  call    cs:__imp_SetEvent
0x180009122  nop     dword ptr [rax+rax+00h]
0x180009127  test    r14b, r14b
0x18000912a  jnz     loc_180008EBD
0x180009130  jmp     short loc_180009183
0x180009132  call    cs:__imp_GetLastError
0x180009139  nop     dword ptr [rax+rax+00h]
0x18000913e  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180009144  mov     ebp, eax
0x180009146  jz      short loc_180009183
0x180009148  mov     [rsp+2D8h+var_280], rbx; void *
0x18000914d  lea     r9, aWaitFailedInCh; "Wait Failed in ChildUIThread. GetLastEr"...
0x180009154  mov     [rsp+2D8h+var_288], ebx; unsigned int
0x180009158  xor     edx, edx; unsigned __int16
0x18000915a  mov     [rsp+2D8h+var_290], r13; unsigned __int16 *
0x18000915f  xor     r8d, r8d; int
0x180009162  mov     [rsp+2D8h+var_298], r13; unsigned __int16 *
0x180009167  mov     [rsp+2D8h+var_2A0], r13; unsigned __int16 *
0x18000916c  mov     [rsp+2D8h+var_2A8], r13; unsigned __int16 *
0x180009171  lea     ecx, [rdx+9]; int
0x180009174  mov     [rsp+2D8h+var_2B0], r13; unsigned __int16 *
0x180009179  mov     [rsp+2D8h+var_2B8], rbp; unsigned __int16 *
0x18000917e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180009183  mov     edx, ebp; dwExitCode
0x180009185  mov     rcx, r15; hLibModule
0x180009188  call    cs:__imp_FreeLibraryAndExitThread
```
