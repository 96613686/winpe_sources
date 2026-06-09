# ContextCacheInitialize

- ea: `0x1800833c4`
- end: `0x1800834b3`
- name: `ContextCacheInitialize`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035cbc`

## callees

- `0x180036394`
- `0x1800833c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083465`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800833fe`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800833fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18008345b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18008345b`

## pseudocode

```c
__int64 __fastcall ContextCacheInitialize(__int64 a1)
{
  __int128 v1; // rdi
  HANDLE MutexW; // rax
  DWORD v3; // eax
  DWORD v4; // ebx
  CObjectMonitor *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD LastError; // eax

  *((_QWORD *)&v1 + 1) = g_hPeerDistInstance;
  *(_QWORD *)&v1 = a1;
  xmmword_1800B8650 = 0;
  *(_OWORD *)&hObject = 0;
  xmmword_1800B8670 = 0;
  MutexW = CreateMutexW(0, 1, 0);
  hObject = MutexW;
  if ( MutexW )
  {
    xmmword_1800B8650 = v1;
    v4 = 0;
    LODWORD(xmmword_1800B8670) = 128;
    if ( !ReleaseMutex(MutexW) )
    {
      LastError = GetLastError();
      v4 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        v6 = 25;
        v7 = LastError;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      v6 = 24;
      v7 = v3;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_081e01272b2b30be004c5e64f228de41_Traceguids, v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800833c4  mov     [rsp+arg_0], rbx
0x1800833c9  mov     [rsp+arg_8], rsi
0x1800833ce  push    rdi
0x1800833cf  sub     rsp, 20h
0x1800833d3  mov     rsi, cs:g_hPeerDistInstance
0x1800833da  xorps   xmm0, xmm0
0x1800833dd  xor     r8d, r8d; lpName
0x1800833e0  mov     rdi, rcx
0x1800833e3  xor     ecx, ecx; lpMutexAttributes
0x1800833e5  movups  cs:xmmword_1800B8650, xmm0
0x1800833ec  lea     edx, [r8+1]; bInitialOwner
0x1800833f0  movups  cs:hObject, xmm0
0x1800833f7  movups  cs:xmmword_1800B8670, xmm0
0x1800833fe  call    cs:__imp_CreateMutexW
0x180083404  mov     qword ptr cs:hObject, rax
0x18008340b  test    rax, rax
0x18008340e  jnz     short loc_18008343E
0x180083410  call    cs:__imp_GetLastError
0x180083416  mov     ebx, eax
0x180083418  mov     rcx, cs:WPP_GLOBAL_Control
0x18008341f  lea     rdx, WPP_GLOBAL_Control
0x180083426  cmp     rcx, rdx
0x180083429  jz      short loc_1800834A1
0x18008342b  test    dword ptr [rcx+1Ch], 10000000h
0x180083432  jz      short loc_1800834A1
0x180083434  mov     edx, 18h
0x180083439  mov     r9d, eax
0x18008343c  jmp     short loc_180083491
0x18008343e  mov     rcx, rax; hMutex
0x180083441  mov     qword ptr cs:xmmword_1800B8650, rdi
0x180083448  xor     ebx, ebx
0x18008344a  mov     qword ptr cs:xmmword_1800B8650+8, rsi
0x180083451  mov     dword ptr cs:xmmword_1800B8670, 80h
0x18008345b  call    cs:__imp_ReleaseMutex
0x180083461  test    eax, eax
0x180083463  jnz     short loc_1800834A1
0x180083465  call    cs:__imp_GetLastError
0x18008346b  mov     ebx, eax
0x18008346d  mov     rcx, cs:WPP_GLOBAL_Control
0x180083474  lea     rdx, WPP_GLOBAL_Control
0x18008347b  cmp     rcx, rdx
0x18008347e  jz      short loc_1800834A1
0x180083480  test    dword ptr [rcx+1Ch], 10000000h
0x180083487  jz      short loc_1800834A1
0x180083489  mov     edx, 19h
0x18008348e  mov     r9d, eax
0x180083491  mov     rcx, [rcx+10h]
0x180083495  lea     r8, WPP_081e01272b2b30be004c5e64f228de41_Traceguids
0x18008349c  call    WPP_SF_d
0x1800834a1  mov     rsi, [rsp+28h+arg_8]
0x1800834a6  mov     eax, ebx
0x1800834a8  mov     rbx, [rsp+28h+arg_0]
0x1800834ad  add     rsp, 20h
0x1800834b1  pop     rdi
0x1800834b2  retn
```
