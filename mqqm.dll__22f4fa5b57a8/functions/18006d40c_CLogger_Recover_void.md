# CLogger::Recover(void)

- ea: `0x18006d40c`
- end: `0x18006d760`
- name: `?Recover@CLogger@@QEAAJXZ`
- size: `852`
- prototype: `__int64 __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002e55c`

## callees

- `0x18000f35c`
- `0x18002c61c`
- `0x18006c2fc`
- `0x18006d1ac`
- `0x18006d2d4`
- `0x18006d40c`
- `0x1800e4010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006d54d`
- `KERNEL32!GetLastError` at `0x18006d5c9`
- `KERNEL32!GetLastError` at `0x18006d6b2`
- `KERNEL32!GetLastError` at `0x18006d54d`
- `KERNEL32!GetLastError` at `0x18006d5c9`
- `KERNEL32!GetLastError` at `0x18006d6b2`
- `KERNEL32!CloseHandle` at `0x18006d606`
- `KERNEL32!CloseHandle` at `0x18006d6f1`
- `KERNEL32!CloseHandle` at `0x18006d6fa`
- `KERNEL32!CloseHandle` at `0x18006d606`
- `KERNEL32!CloseHandle` at `0x18006d6f1`
- `KERNEL32!CloseHandle` at `0x18006d6fa`
- `KERNEL32!CreateEventW` at `0x18006d53b`
- `KERNEL32!CreateEventW` at `0x18006d5bb`
- `KERNEL32!CreateEventW` at `0x18006d53b`
- `KERNEL32!CreateEventW` at `0x18006d5bb`
- `KERNEL32!CreateThread` at `0x18006d6a0`
- `KERNEL32!CreateThread` at `0x18006d6a0`
- `mqsec!GetFalconKeyValue` at `0x18006d672`
- `mqsec!GetFalconKeyValue` at `0x18006d672`

## pseudocode

```c
__int64 __fastcall CLogger::Recover(CLogger *this, void (*a2)(unsigned __int16, void *, unsigned int))
{
  int LRP; // eax
  void (*v3)(unsigned __int16, void *, unsigned int); // rdx
  CLogger *v4; // rcx
  unsigned int Next; // ebx
  int v6; // esi
  CLogger *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  DWORD v11; // eax
  signed int v12; // ebx
  bool v13; // sf
  HANDLE EventW; // rsi
  DWORD v15; // eax
  signed int v16; // ebx
  bool v17; // sf
  DWORD LastError; // eax
  signed int v19; // ebx
  bool v20; // sf
  CLogger *v21; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v22; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v23; // [rsp+60h] [rbp+18h] BYREF
  DWORD ThreadId; // [rsp+68h] [rbp+20h] BYREF

  v21 = this;
  try
  {
    HIDWORD(qword_18013B198) = 1;
    LRP = CLogger::ReadLRP(this, a2);
    Next = LRP;
    if ( LRP >= 0 )
    {
      while ( !Next )
        Next = CLogger::ReadNext(v4, v3);
    }
    else
    {
      LogMsgHR(LRP, (wchar_t *)L"xactlog", 0x528u);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 57), 21, &WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids, Next);
    v6 = 0;
    if ( Next != -2147479510 )
      v6 = Next;
  }
  catch ( exception )
  {
    LogIllegalPoint((wchar_t *)L"xactlog", 0x641u);
    LODWORD(v21) = -1072824319;
    v10 = -1072824319;
    LogMsgHR(-1072824319, (wchar_t *)L"xactlog", 0x3Cu);
    return v10;
  }
  if ( v6 >= 0 )
  {
    HIDWORD(qword_18013B198) = 0;
    (*(void (__fastcall **)(CLogger *))(*(_QWORD *)xmmword_18013B030 + 16LL))(xmmword_18013B030);
    xmmword_18013B030 = 0;
    v9 = CLogger::InitLogWrite(v8);
    v10 = v9;
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**(&g_Logger + 1) + 16LL))(*(&g_Logger + 1));
      *(&g_Logger + 1) = 0;
      (*(void (__fastcall **)(_QWORD))(*g_Logger + 16LL))(g_Logger);
      g_Logger = 0;
      hObject = CreateEventW(0, 0, 0, 0);
      if ( hObject )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        if ( EventW )
        {
          LODWORD(v21) = 1800000;
          v22 = 4;
          v23 = 4;
          GetFalconKeyValue(L"RMFlushInterval", &v23, &dword_18013B1A8, &v22, (const wchar_t *)&v21);
          ThreadId = 0;
          hHandle = CreateThread(0, 0, FlusherThreadRoutine, EventW, 0, &ThreadId);
          if ( hHandle )
          {
            return v10;
          }
          else
          {
            LastError = GetLastError();
            v19 = LastError;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 57),
                24,
                &WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids,
                LastError);
            CloseHandle(hObject);
            CloseHandle(EventW);
            v20 = v19 < 0;
            if ( v19 > 0 )
            {
              v19 = (unsigned __int16)v19 | 0x80070000;
              v20 = v19 < 0;
            }
            if ( v20 )
              LogMsgHR(v19, (wchar_t *)L"xactlog", 0x680u);
            return (unsigned int)v19;
          }
        }
        else
        {
          v15 = GetLastError();
          v16 = v15;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 57), 23, &WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids, v15);
          CloseHandle(hObject);
          v17 = v16 < 0;
          if ( v16 > 0 )
          {
            v16 = (unsigned __int16)v16 | 0x80070000;
            v17 = v16 < 0;
          }
          if ( v17 )
            LogMsgHR(v16, (wchar_t *)L"xactlog", 0x67Eu);
          return (unsigned int)v16;
        }
      }
      else
      {
        v11 = GetLastError();
        v12 = v11;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 57), 22, &WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids, v11);
        v13 = v12 < 0;
        if ( v12 > 0 )
        {
          v12 = (unsigned __int16)v12 | 0x80070000;
          v13 = v12 < 0;
        }
        if ( v13 )
          LogMsgHR(v12, (wchar_t *)L"xactlog", 0xB8u);
        return (unsigned int)v12;
      }
    }
    else
    {
      LogMsgHR(v9, (wchar_t *)L"xactlog", 0x47Eu);
      return v10;
    }
  }
  else
  {
    LogMsgHR(v6, (wchar_t *)L"xactlog", 0x474u);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18006d40c  mov     [rsp+arg_0], rcx
0x18006d411  push    rbx
0x18006d412  push    rsi
0x18006d413  push    r12
0x18006d415  sub     rsp, 30h
0x18006d419  mov     dword ptr cs:qword_18013B198+4, 1
0x18006d423  call    ?ReadLRP@CLogger@@AEAAJP6AXGPEAXK@Z@Z; CLogger::ReadLRP(void (*)(ushort,void *,ulong))
0x18006d428  mov     ebx, eax
0x18006d42a  test    eax, eax
0x18006d42c  jns     loc_18006D72B
0x18006d432  mov     r8d, 528h; unsigned __int16
0x18006d438  lea     rdx, aXactlog; "xactlog"
0x18006d43f  mov     ecx, eax; int
0x18006d441  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d446  lea     r12, WPP_GLOBAL_Control
0x18006d44d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d454  cmp     rcx, r12
0x18006d457  jz      short loc_18006D47D
0x18006d459  test    byte ptr [rcx+1D4h], 4
0x18006d460  jz      short loc_18006D47D
0x18006d462  mov     edx, 15h
0x18006d467  mov     r9d, ebx
0x18006d46a  lea     r8, WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids
0x18006d471  mov     rcx, [rcx+1C8h]
0x18006d478  call    WPP_SF_d
0x18006d47d  xor     esi, esi
0x18006d47f  cmp     ebx, 8000102Ah
0x18006d485  cmovnz  esi, ebx
0x18006d488  test    esi, esi
0x18006d48a  jns     short loc_18006D4A7
0x18006d48c  mov     r8d, 474h; unsigned __int16
0x18006d492  lea     rdx, aXactlog; "xactlog"
0x18006d499  mov     ecx, esi; int
0x18006d49b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d4a0  mov     eax, esi
0x18006d4a2  jmp     loc_18006D756
0x18006d4a7  mov     dword ptr cs:qword_18013B198+4, 0
0x18006d4b1  mov     rcx, qword ptr cs:xmmword_18013B030
0x18006d4b8  mov     rax, [rcx]
0x18006d4bb  mov     rax, [rax+10h]
0x18006d4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d4c4  mov     qword ptr cs:xmmword_18013B030, 0
0x18006d4cf  call    ?InitLogWrite@CLogger@@AEAAJXZ; CLogger::InitLogWrite(void)
0x18006d4d4  mov     ebx, eax
0x18006d4d6  test    eax, eax
0x18006d4d8  jns     short loc_18006D4F5
0x18006d4da  mov     r8d, 47Eh; unsigned __int16
0x18006d4e0  lea     rdx, aXactlog; "xactlog"
0x18006d4e7  mov     ecx, eax; int
0x18006d4e9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d4ee  mov     eax, ebx
0x18006d4f0  jmp     loc_18006D756
0x18006d4f5  mov     rcx, qword ptr cs:?g_Logger@@3VCLogger@@A+8; CLogger g_Logger
0x18006d4fc  mov     rax, [rcx]
0x18006d4ff  mov     rax, [rax+10h]
0x18006d503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d508  mov     qword ptr cs:?g_Logger@@3VCLogger@@A+8, 0; CLogger g_Logger
0x18006d513  mov     rcx, qword ptr cs:?g_Logger@@3VCLogger@@A; CLogger g_Logger
0x18006d51a  mov     rax, [rcx]
0x18006d51d  mov     rax, [rax+10h]
0x18006d521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d526  mov     qword ptr cs:?g_Logger@@3VCLogger@@A, 0; CLogger g_Logger
0x18006d531  xor     r9d, r9d; lpName
0x18006d534  xor     r8d, r8d; bInitialState
0x18006d537  xor     edx, edx; bManualReset
0x18006d539  xor     ecx, ecx; lpEventAttributes
0x18006d53b  call    cs:__imp_CreateEventW
0x18006d541  mov     cs:hObject, rax
0x18006d548  test    rax, rax
0x18006d54b  jnz     short loc_18006D5B1
0x18006d54d  call    cs:__imp_GetLastError
0x18006d553  mov     ebx, eax
0x18006d555  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d55c  cmp     rcx, r12
0x18006d55f  jz      short loc_18006D585
0x18006d561  test    byte ptr [rcx+1D4h], 1
0x18006d568  jz      short loc_18006D585
0x18006d56a  mov     edx, 16h
0x18006d56f  mov     r9d, eax
0x18006d572  lea     r8, WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids
0x18006d579  mov     rcx, [rcx+1C8h]
0x18006d580  call    WPP_SF_d
0x18006d585  test    ebx, ebx
0x18006d587  jle     short loc_18006D594
0x18006d589  movzx   ebx, bx
0x18006d58c  or      ebx, 80070000h
0x18006d592  test    ebx, ebx
0x18006d594  jns     short loc_18006D5AA
0x18006d596  mov     r8d, 0B8h; unsigned __int16
0x18006d59c  lea     rdx, aXactlog; "xactlog"
0x18006d5a3  mov     ecx, ebx; int
0x18006d5a5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d5aa  mov     eax, ebx
0x18006d5ac  jmp     loc_18006D756
0x18006d5b1  xor     r9d, r9d; lpName
0x18006d5b4  xor     r8d, r8d; bInitialState
0x18006d5b7  xor     edx, edx; bManualReset
0x18006d5b9  xor     ecx, ecx; lpEventAttributes
0x18006d5bb  call    cs:__imp_CreateEventW
0x18006d5c1  mov     rsi, rax
0x18006d5c4  test    rax, rax
0x18006d5c7  jnz     short loc_18006D638
0x18006d5c9  call    cs:__imp_GetLastError
0x18006d5cf  mov     ebx, eax
0x18006d5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5d8  cmp     rcx, r12
0x18006d5db  jz      short loc_18006D5FF
0x18006d5dd  test    byte ptr [rcx+1D4h], 1
0x18006d5e4  jz      short loc_18006D5FF
0x18006d5e6  lea     edx, [rsi+17h]
0x18006d5e9  mov     r9d, eax
0x18006d5ec  lea     r8, WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids
0x18006d5f3  mov     rcx, [rcx+1C8h]
0x18006d5fa  call    WPP_SF_d
0x18006d5ff  mov     rcx, cs:hObject; hObject
0x18006d606  call    cs:__imp_CloseHandle
0x18006d60c  test    ebx, ebx
0x18006d60e  jle     short loc_18006D61B
0x18006d610  movzx   ebx, bx
0x18006d613  or      ebx, 80070000h
0x18006d619  test    ebx, ebx
0x18006d61b  jns     short loc_18006D631
0x18006d61d  mov     r8d, 67Eh; unsigned __int16
0x18006d623  lea     rdx, aXactlog; "xactlog"
0x18006d62a  mov     ecx, ebx; int
0x18006d62c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d631  mov     eax, ebx
0x18006d633  jmp     loc_18006D756
0x18006d638  mov     dword ptr [rsp+48h+arg_0], 1B7740h
0x18006d640  mov     [rsp+48h+arg_8], 4
0x18006d648  mov     [rsp+48h+arg_10], 4
0x18006d650  lea     rax, [rsp+48h+arg_0]
0x18006d655  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x18006d65a  lea     r9, [rsp+48h+arg_8]
0x18006d65f  lea     r8, dword_18013B1A8
0x18006d666  lea     rdx, [rsp+48h+arg_10]
0x18006d66b  lea     rcx, aRmflushinterva; "RMFlushInterval"
0x18006d672  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18006d678  mov     [rsp+48h+ThreadId], 0
0x18006d680  lea     rax, [rsp+48h+ThreadId]
0x18006d685  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18006d68a  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18006d692  mov     r9, rsi; lpParameter
0x18006d695  lea     r8, FlusherThreadRoutine; lpStartAddress
0x18006d69c  xor     edx, edx; dwStackSize
0x18006d69e  xor     ecx, ecx; lpThreadAttributes
0x18006d6a0  call    cs:__imp_CreateThread
0x18006d6a6  mov     cs:hHandle, rax
0x18006d6ad  test    rax, rax
0x18006d6b0  jnz     short loc_18006D729
0x18006d6b2  call    cs:__imp_GetLastError
0x18006d6b8  mov     ebx, eax
0x18006d6ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d6c1  cmp     rcx, r12
0x18006d6c4  jz      short loc_18006D6EA
0x18006d6c6  test    byte ptr [rcx+1D4h], 1
0x18006d6cd  jz      short loc_18006D6EA
0x18006d6cf  mov     edx, 18h
0x18006d6d4  mov     r9d, eax
0x18006d6d7  lea     r8, WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids
0x18006d6de  mov     rcx, [rcx+1C8h]
0x18006d6e5  call    WPP_SF_d
0x18006d6ea  mov     rcx, cs:hObject; hObject
0x18006d6f1  call    cs:__imp_CloseHandle
0x18006d6f7  mov     rcx, rsi; hObject
0x18006d6fa  call    cs:__imp_CloseHandle
0x18006d700  test    ebx, ebx
0x18006d702  jle     short loc_18006D70F
0x18006d704  movzx   ebx, bx
0x18006d707  or      ebx, 80070000h
0x18006d70d  test    ebx, ebx
0x18006d70f  jns     short loc_18006D725
0x18006d711  mov     r8d, 680h; unsigned __int16
0x18006d717  lea     rdx, aXactlog; "xactlog"
0x18006d71e  mov     ecx, ebx; int
0x18006d720  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d725  mov     eax, ebx
0x18006d727  jmp     short loc_18006D756
0x18006d729  jmp     short loc_18006D754
0x18006d72b  test    ebx, ebx
0x18006d72d  jnz     loc_18006D446
0x18006d733  call    ?ReadNext@CLogger@@AEAAJP6AXGPEAXK@Z@Z; CLogger::ReadNext(void (*)(ushort,void *,ulong))
0x18006d738  mov     ebx, eax
0x18006d73a  jmp     short loc_18006D72B
0x18006d73c  mov     r8d, 3Ch ; '<'; unsigned __int16
0x18006d742  lea     rdx, aXactlog; "xactlog"
0x18006d749  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18006d74d  mov     ecx, ebx; int
0x18006d74f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006d754  mov     eax, ebx
0x18006d756  add     rsp, 30h
0x18006d75a  pop     r12
0x18006d75c  pop     rsi
0x18006d75d  pop     rbx
0x18006d75e  retn
```
