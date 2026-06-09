# CRemoteAssistanceApp::CanUserBeNovice(int,int,HWND__ *)

- ea: `0x14000e8b8`
- end: `0x14000e9fc`
- name: `?CanUserBeNovice@CRemoteAssistanceApp@@QEAAHHHPEAUHWND__@@@Z`
- size: `324`
- prototype: `int(CRemoteAssistanceApp *__hidden this, int, int, HWND)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140012794`
- `0x140013f4c`
- `0x1400146cc`
- `0x140032274`

## callees

- `0x14000e8b8`
- `0x14002b26c`
- `0x14002c0a4`
- `0x14002c8e4`
- `0x14002cb94`
- `0x140034ce4`
- `0x140034eac`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14000e95c`
- `KERNEL32!CreateThread` at `0x14000e95c`
- `KERNEL32!CloseHandle` at `0x14000e9e4`
- `KERNEL32!CloseHandle` at `0x14000e9e4`
- `KERNEL32!WaitForSingleObject` at `0x14000e982`
- `KERNEL32!WaitForSingleObject` at `0x14000e982`

## pseudocode

```c
__int64 __fastcall CRemoteAssistanceApp::CanUserBeNovice(CRemoteAssistanceApp *this, int a2, int a3, HWND a4)
{
  unsigned int v4; // edi
  CEventLogger *v8; // rcx
  HANDLE v9; // rax
  CEventLogger *v10; // rcx
  void *v11; // rbx
  CEventLogger *v12; // rcx
  HWND v13; // rcx
  int Parameter; // [rsp+60h] [rbp+8h] BYREF
  int Parameter_4; // [rsp+64h] [rbp+Ch]

  Parameter_4 = HIDWORD(this);
  v4 = 0;
  Parameter = 2;
  if ( (unsigned int)TakeLock(1) )
  {
    ReleaseLock(1);
    v9 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)GetRASystemHealth, &Parameter, 0, 0);
    v11 = v9;
    if ( v9 )
    {
      if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
      {
        CEventLogger::LogError(
          v12,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x5F2u,
          L"CRemoteAssistanceApp::CanUserBeNovice",
          0);
      }
      else if ( Parameter == 2 )
      {
        CEventLogger::LogEvent(v12, &Settings_No_Invite);
        if ( a2 == 1 )
          ShowSystemNotConfigured(v13);
      }
      else
      {
        v4 = 1;
      }
      CloseHandle(v11);
    }
    else
    {
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x5EBu,
        L"CRemoteAssistanceApp::CanUserBeNovice",
        0);
    }
  }
  else
  {
    if ( a3 )
      ShowErrorMessage(0x225u, 0x295u, a4, 0, (unsigned __int16 *)0xFFFE, 0);
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x5D8u,
      L"CRemoteAssistanceApp::CanUserBeNovice",
      0x80000225);
  }
  return v4;
}

```

## disassembly

```asm
0x14000e8b8  mov     [rsp+Parameter], rcx
0x14000e8bd  push    rbx
0x14000e8be  push    rbp
0x14000e8bf  push    rsi
0x14000e8c0  push    rdi
0x14000e8c1  sub     rsp, 38h
0x14000e8c5  xor     edi, edi
0x14000e8c7  mov     dword ptr [rsp+58h+Parameter], 2
0x14000e8cf  mov     rsi, r9
0x14000e8d2  mov     ebx, r8d
0x14000e8d5  mov     ebp, edx
0x14000e8d7  lea     ecx, [rdi+1]; int
0x14000e8da  call    ?TakeLock@@YAHH@Z; TakeLock(int)
0x14000e8df  test    eax, eax
0x14000e8e1  jnz     short loc_14000E939
0x14000e8e3  test    ebx, ebx
0x14000e8e5  jz      short loc_14000E907
0x14000e8e7  mov     edx, 295h; int
0x14000e8ec  mov     dword ptr [rsp+58h+lpThreadId], edi; int
0x14000e8f0  xor     r9d, r9d; int
0x14000e8f3  mov     qword ptr [rsp+58h+dwCreationFlags], 0FFFEh; unsigned __int16 *
0x14000e8fc  mov     r8, rsi; HWND
0x14000e8ff  lea     ecx, [rdx-70h]; int
0x14000e902  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14000e907  mov     dword ptr [rsp+58h+lpThreadId], 80000225h; unsigned int
0x14000e90f  mov     r9d, 5D8h; unsigned int
0x14000e915  lea     rax, aCremoteassista_7; "CRemoteAssistanceApp::CanUserBeNovice"
0x14000e91c  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14000e923  mov     qword ptr [rsp+58h+dwCreationFlags], rax; unsigned __int16 *
0x14000e928  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000e92f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e934  jmp     loc_14000E9F0
0x14000e939  mov     ecx, 1; int
0x14000e93e  call    ?ReleaseLock@@YAXH@Z; ReleaseLock(int)
0x14000e943  lea     r9, [rsp+58h+Parameter]; lpParameter
0x14000e948  mov     [rsp+58h+lpThreadId], rdi; lpThreadId
0x14000e94d  lea     r8, ?GetRASystemHealth@@YAKPEAX@Z; lpStartAddress
0x14000e954  mov     [rsp+58h+dwCreationFlags], edi; dwCreationFlags
0x14000e958  xor     edx, edx; dwStackSize
0x14000e95a  xor     ecx, ecx; lpThreadAttributes
0x14000e95c  call    cs:__imp_CreateThread
0x14000e963  nop     dword ptr [rax+rax+00h]
0x14000e968  mov     rbx, rax
0x14000e96b  test    rax, rax
0x14000e96e  jnz     short loc_14000E97C
0x14000e970  mov     dword ptr [rsp+58h+lpThreadId], edi
0x14000e974  mov     r9d, 5EBh
0x14000e97a  jmp     short loc_14000E915
0x14000e97c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000e97f  mov     rcx, rbx; hHandle
0x14000e982  call    cs:__imp_WaitForSingleObject
0x14000e989  nop     dword ptr [rax+rax+00h]
0x14000e98e  test    eax, eax
0x14000e990  jz      short loc_14000E9BD
0x14000e992  lea     rax, aCremoteassista_7; "CRemoteAssistanceApp::CanUserBeNovice"
0x14000e999  mov     dword ptr [rsp+58h+lpThreadId], edi; unsigned int
0x14000e99d  mov     r9d, 5F2h; unsigned int
0x14000e9a3  mov     qword ptr [rsp+58h+dwCreationFlags], rax; unsigned __int16 *
0x14000e9a8  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14000e9af  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000e9b6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e9bb  jmp     short loc_14000E9E1
0x14000e9bd  cmp     dword ptr [rsp+58h+Parameter], 2
0x14000e9c2  jnz     short loc_14000E9DC
0x14000e9c4  lea     rdx, Settings_No_Invite; struct _EVENT_DESCRIPTOR *
0x14000e9cb  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x14000e9d0  cmp     ebp, 1
0x14000e9d3  jnz     short loc_14000E9E1
0x14000e9d5  call    ?ShowSystemNotConfigured@@YAJPEAUHWND__@@K@Z; ShowSystemNotConfigured(HWND__ *,ulong)
0x14000e9da  jmp     short loc_14000E9E1
0x14000e9dc  mov     edi, 1
0x14000e9e1  mov     rcx, rbx; hObject
0x14000e9e4  call    cs:__imp_CloseHandle
0x14000e9eb  nop     dword ptr [rax+rax+00h]
0x14000e9f0  mov     eax, edi
0x14000e9f2  add     rsp, 38h
0x14000e9f6  pop     rdi
0x14000e9f7  pop     rsi
0x14000e9f8  pop     rbp
0x14000e9f9  pop     rbx
0x14000e9fa  retn
```
