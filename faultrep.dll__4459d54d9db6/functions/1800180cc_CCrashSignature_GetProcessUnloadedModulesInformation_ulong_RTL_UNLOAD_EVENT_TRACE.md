# CCrashSignature::GetProcessUnloadedModulesInformation(ulong *,_RTL_UNLOAD_EVENT_TRACE * *)

- ea: `0x1800180cc`
- end: `0x180018351`
- name: `?GetProcessUnloadedModulesInformation@CCrashSignature@@AEAAJPEAKPEAPEAU_RTL_UNLOAD_EVENT_TRACE@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(CCrashSignature *__hidden this, unsigned int *, struct _RTL_UNLOAD_EVENT_TRACE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018358`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x1800180cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182b6`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x180018115`
- `ntdll!RtlGetUnloadEventTraceEx` at `0x180018115`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180018155`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800181bd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180018202`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180018155`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800181bd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180018202`

## pseudocode

```c
__int64 __fastcall CCrashSignature::GetProcessUnloadedModulesInformation(
        CCrashSignature *this,
        unsigned int *a2,
        struct _RTL_UNLOAD_EVENT_TRACE **a3)
{
  void *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  unsigned int v11; // ebx
  signed int LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  signed int v15; // eax
  signed int v16; // eax
  int Buffer; // [rsp+30h] [rbp-30h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-28h] BYREF
  LPCVOID v20; // [rsp+40h] [rbp-20h] BYREF
  LPCVOID v21; // [rsp+48h] [rbp-18h] BYREF
  LPCVOID lpBaseAddress; // [rsp+50h] [rbp-10h] BYREF
  struct _RTL_UNLOAD_EVENT_TRACE *v23; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v24; // [rsp+98h] [rbp+38h] BYREF

  lpBaseAddress = 0;
  v20 = 0;
  v21 = 0;
  NumberOfBytesRead = 0;
  v24 = 0;
  Buffer = 0;
  v23 = 0;
  RtlGetUnloadEventTraceEx(&lpBaseAddress, &v20, &v21);
  if ( !lpBaseAddress || !v20 || !v21 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2147467259;
    v8 = 19;
    goto LABEL_42;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesRead = 0;
  if ( ReadProcessMemory(v6, lpBaseAddress, &Buffer, 4u, &NumberOfBytesRead) && NumberOfBytesRead == 4 )
  {
    if ( Buffer != 104 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)-2147467259;
      v8 = 21;
LABEL_42:
      WPP_SF_(v7[2], v8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
      return (unsigned int)-2147467259;
    }
    v9 = (void *)*((_QWORD *)this + 1);
    NumberOfBytesRead = 0;
    if ( ReadProcessMemory(v9, v20, &v24, 4u, &NumberOfBytesRead) && NumberOfBytesRead == 4 )
    {
      if ( v24 > 0x1000 )
        v24 = 4096;
      v10 = (void *)*((_QWORD *)this + 1);
      NumberOfBytesRead = 0;
      if ( ReadProcessMemory(v10, v21, &v23, 8u, &NumberOfBytesRead) && NumberOfBytesRead == 8 )
      {
        v11 = 0;
        *a2 = v24;
        *a3 = v23;
        return v11;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      v11 = LastError;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 23;
LABEL_38:
        WPP_SF_d(v13[2], v14, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids, v11);
      }
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 >= 0 )
        v15 = -2147467259;
      v11 = v15;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 22;
        goto LABEL_38;
      }
    }
  }
  else
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    v11 = v16;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 20;
      goto LABEL_38;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800180cc  mov     [rsp-18h+arg_0], rbx
0x1800180d1  mov     [rsp-18h+arg_8], rsi
0x1800180d6  push    rbp
0x1800180d7  push    rdi
0x1800180d8  push    r14
0x1800180da  mov     rbp, rsp
0x1800180dd  sub     rsp, 60h
0x1800180e1  xor     r14d, r14d
0x1800180e4  mov     rdi, r8
0x1800180e7  mov     rsi, rdx
0x1800180ea  mov     [rbp+lpBaseAddress], r14
0x1800180ee  mov     rbx, rcx
0x1800180f1  mov     [rbp+var_20], r14
0x1800180f5  lea     r8, [rbp+var_18]
0x1800180f9  mov     [rbp+var_18], r14
0x1800180fd  lea     rdx, [rbp+var_20]
0x180018101  mov     [rbp+NumberOfBytesRead], r14
0x180018105  lea     rcx, [rbp+lpBaseAddress]
0x180018109  mov     [rbp+arg_18], r14d
0x18001810d  mov     [rbp+Buffer], r14d
0x180018111  mov     [rbp+var_8], r14
0x180018115  call    cs:__imp_RtlGetUnloadEventTraceEx
0x18001811b  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x18001811f  test    rdx, rdx
0x180018122  jz      loc_180018307
0x180018128  cmp     [rbp+var_20], r14
0x18001812c  jz      loc_180018307
0x180018132  cmp     [rbp+var_18], r14
0x180018136  jz      loc_180018307
0x18001813c  mov     rcx, [rbx+8]; hProcess
0x180018140  lea     rax, [rbp+NumberOfBytesRead]
0x180018144  lea     r9d, [r14+4]; nSize
0x180018148  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18001814d  lea     r8, [rbp+Buffer]; lpBuffer
0x180018151  mov     [rbp+NumberOfBytesRead], r14
0x180018155  call    cs:__imp_ReadProcessMemory
0x18001815b  test    eax, eax
0x18001815d  jz      loc_1800182B6
0x180018163  cmp     [rbp+NumberOfBytesRead], 4
0x180018168  jnz     loc_1800182B6
0x18001816e  cmp     [rbp+Buffer], 68h ; 'h'
0x180018172  jz      short loc_18001819E
0x180018174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001817b  lea     rax, WPP_GLOBAL_Control
0x180018182  cmp     rcx, rax
0x180018185  jz      loc_180018335
0x18001818b  test    byte ptr [rcx+1Ch], 1
0x18001818f  jz      loc_180018335
0x180018195  lea     edx, [r14+15h]
0x180018199  jmp     loc_180018325
0x18001819e  mov     rdx, [rbp+var_20]; lpBaseAddress
0x1800181a2  lea     rax, [rbp+NumberOfBytesRead]
0x1800181a6  mov     rcx, [rbx+8]; hProcess
0x1800181aa  lea     r8, [rbp+arg_18]; lpBuffer
0x1800181ae  mov     r9d, 4; nSize
0x1800181b4  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800181b9  mov     [rbp+NumberOfBytesRead], r14
0x1800181bd  call    cs:__imp_ReadProcessMemory
0x1800181c3  test    eax, eax
0x1800181c5  jz      loc_180018270
0x1800181cb  cmp     [rbp+NumberOfBytesRead], 4
0x1800181d0  jnz     loc_180018270
0x1800181d6  mov     eax, 1000h
0x1800181db  cmp     [rbp+arg_18], eax
0x1800181de  jbe     short loc_1800181E3
0x1800181e0  mov     [rbp+arg_18], eax
0x1800181e3  mov     rdx, [rbp+var_18]; lpBaseAddress
0x1800181e7  lea     rax, [rbp+NumberOfBytesRead]
0x1800181eb  mov     rcx, [rbx+8]; hProcess
0x1800181ef  lea     r8, [rbp+var_8]; lpBuffer
0x1800181f3  mov     r9d, 8; nSize
0x1800181f9  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800181fe  mov     [rbp+NumberOfBytesRead], r14
0x180018202  call    cs:__imp_ReadProcessMemory
0x180018208  test    eax, eax
0x18001820a  jz      short loc_180018227
0x18001820c  cmp     [rbp+NumberOfBytesRead], 8
0x180018211  jnz     short loc_180018227
0x180018213  mov     eax, [rbp+arg_18]
0x180018216  mov     ebx, r14d
0x180018219  mov     [rsi], eax
0x18001821b  mov     rax, [rbp+var_8]
0x18001821f  mov     [rdi], rax
0x180018222  jmp     loc_18001833A
0x180018227  call    cs:__imp_GetLastError
0x18001822d  test    eax, eax
0x18001822f  jle     short loc_180018239
0x180018231  movzx   eax, ax
0x180018234  or      eax, 80070000h
0x180018239  mov     ebx, 80004005h
0x18001823e  test    eax, eax
0x180018240  cmovns  eax, ebx
0x180018243  mov     ebx, eax
0x180018245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001824c  lea     rax, WPP_GLOBAL_Control
0x180018253  cmp     rcx, rax
0x180018256  jz      loc_18001833A
0x18001825c  test    byte ptr [rcx+1Ch], 1
0x180018260  jz      loc_18001833A
0x180018266  mov     edx, 17h
0x18001826b  jmp     loc_1800182F2
0x180018270  call    cs:__imp_GetLastError
0x180018276  test    eax, eax
0x180018278  jle     short loc_180018282
0x18001827a  movzx   eax, ax
0x18001827d  or      eax, 80070000h
0x180018282  mov     ebx, 80004005h
0x180018287  test    eax, eax
0x180018289  cmovns  eax, ebx
0x18001828c  mov     ebx, eax
0x18001828e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018295  lea     rax, WPP_GLOBAL_Control
0x18001829c  cmp     rcx, rax
0x18001829f  jz      loc_18001833A
0x1800182a5  test    byte ptr [rcx+1Ch], 1
0x1800182a9  jz      loc_18001833A
0x1800182af  mov     edx, 16h
0x1800182b4  jmp     short loc_1800182F2
0x1800182b6  call    cs:__imp_GetLastError
0x1800182bc  test    eax, eax
0x1800182be  jle     short loc_1800182C8
0x1800182c0  movzx   eax, ax
0x1800182c3  or      eax, 80070000h
0x1800182c8  mov     ebx, 80004005h
0x1800182cd  test    eax, eax
0x1800182cf  cmovns  eax, ebx
0x1800182d2  mov     ebx, eax
0x1800182d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182db  lea     rax, WPP_GLOBAL_Control
0x1800182e2  cmp     rcx, rax
0x1800182e5  jz      short loc_18001833A
0x1800182e7  test    byte ptr [rcx+1Ch], 1
0x1800182eb  jz      short loc_18001833A
0x1800182ed  mov     edx, 14h
0x1800182f2  mov     rcx, [rcx+10h]
0x1800182f6  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x1800182fd  mov     r9d, ebx
0x180018300  call    WPP_SF_d
0x180018305  jmp     short loc_18001833A
0x180018307  mov     rcx, cs:WPP_GLOBAL_Control
0x18001830e  lea     rax, WPP_GLOBAL_Control
0x180018315  cmp     rcx, rax
0x180018318  jz      short loc_180018335
0x18001831a  test    byte ptr [rcx+1Ch], 1
0x18001831e  jz      short loc_180018335
0x180018320  mov     edx, 13h
0x180018325  mov     rcx, [rcx+10h]
0x180018329  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018330  call    WPP_SF_
0x180018335  mov     ebx, 80004005h
0x18001833a  lea     r11, [rsp+60h+var_s0]
0x18001833f  mov     eax, ebx
0x180018341  mov     rbx, [r11+20h]
0x180018345  mov     rsi, [r11+28h]
0x180018349  mov     rsp, r11
0x18001834c  pop     r14
0x18001834e  pop     rdi
0x18001834f  pop     rbp
0x180018350  retn
```
