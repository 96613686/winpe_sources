# CVPInterfaceHandler::CreateThread(void)

- ea: `0x180040dbc`
- end: `0x180040ee0`
- name: `?CreateThread@CVPInterfaceHandler@@QEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(CVPInterfaceHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180040714`
- `0x1800408d0`

## callees

- `0x180025860`
- `0x180040dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040e32`
- `KERNEL32!GetLastError` at `0x180040e8f`
- `KERNEL32!GetLastError` at `0x180040e32`
- `KERNEL32!GetLastError` at `0x180040e8f`
- `KERNEL32!CreateEventW` at `0x180040de0`
- `KERNEL32!CreateEventW` at `0x180040de0`
- `KERNEL32!CloseHandle` at `0x180040e79`
- `KERNEL32!CloseHandle` at `0x180040e79`
- `KERNEL32!CreateThread` at `0x180040e19`
- `KERNEL32!CreateThread` at `0x180040e19`

## pseudocode

```c
__int64 __fastcall CVPInterfaceHandler::CreateThread(CVPInterfaceHandler *this)
{
  unsigned int v1; // ebx
  HANDLE EventW; // rax
  HANDLE v4; // rax
  signed int LastError; // eax
  signed int v6; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  if ( !this->m_ThreadHandle )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    this->m_EndEventHandle = EventW;
    if ( EventW )
    {
      ThreadId = 0;
      v4 = CreateThread(0, 0, CVPInterfaceHandler::InitialThreadProc, this, 0, &ThreadId);
      this->m_ThreadHandle = v4;
      if ( !v4 )
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
        CloseHandle(this->m_EndEventHandle);
        this->m_EndEventHandle = 0;
      }
    }
    else
    {
      v6 = GetLastError();
      v1 = v6;
      if ( v6 > 0 )
        v1 = (unsigned __int16)v6 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xFu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180040dbc  mov     [rsp+arg_8], rbx
0x180040dc1  push    rdi
0x180040dc2  sub     rsp, 30h
0x180040dc6  xor     ebx, ebx
0x180040dc8  mov     rdi, rcx
0x180040dcb  cmp     [rcx+60h], rbx
0x180040dcf  jnz     loc_180040ED2
0x180040dd5  xor     r9d, r9d; lpName
0x180040dd8  lea     edx, [rbx+1]; bManualReset
0x180040ddb  xor     r8d, r8d; bInitialState
0x180040dde  xor     ecx, ecx; lpEventAttributes
0x180040de0  call    cs:__imp_CreateEventW
0x180040de7  nop     dword ptr [rax+rax+00h]
0x180040dec  mov     [rdi+28h], rax
0x180040df0  test    rax, rax
0x180040df3  jz      loc_180040E8F
0x180040df9  lea     rax, [rsp+38h+ThreadId]
0x180040dfe  mov     [rsp+38h+ThreadId], ebx
0x180040e02  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180040e07  lea     r8, ?InitialThreadProc@CVPInterfaceHandler@@SAKPEAV1@@Z; lpStartAddress
0x180040e0e  mov     r9, rdi; lpParameter
0x180040e11  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180040e15  xor     edx, edx; dwStackSize
0x180040e17  xor     ecx, ecx; lpThreadAttributes
0x180040e19  call    cs:__imp_CreateThread
0x180040e20  nop     dword ptr [rax+rax+00h]
0x180040e25  mov     [rdi+60h], rax
0x180040e29  test    rax, rax
0x180040e2c  jnz     loc_180040ED2
0x180040e32  call    cs:__imp_GetLastError
0x180040e39  nop     dword ptr [rax+rax+00h]
0x180040e3e  mov     ebx, eax
0x180040e40  test    eax, eax
0x180040e42  jle     short loc_180040E4D
0x180040e44  movzx   ebx, ax
0x180040e47  or      ebx, 80070000h
0x180040e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e54  lea     rax, WPP_GLOBAL_Control
0x180040e5b  cmp     rcx, rax
0x180040e5e  jz      short loc_180040E75
0x180040e60  mov     rcx, [rcx+10h]
0x180040e64  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x180040e6b  mov     edx, 0Eh
0x180040e70  call    WPP_SF_
0x180040e75  mov     rcx, [rdi+28h]; hObject
0x180040e79  call    cs:__imp_CloseHandle
0x180040e80  nop     dword ptr [rax+rax+00h]
0x180040e85  mov     qword ptr [rdi+28h], 0
0x180040e8d  jmp     short loc_180040ED2
0x180040e8f  call    cs:__imp_GetLastError
0x180040e96  nop     dword ptr [rax+rax+00h]
0x180040e9b  mov     ebx, eax
0x180040e9d  test    eax, eax
0x180040e9f  jle     short loc_180040EAA
0x180040ea1  movzx   ebx, ax
0x180040ea4  or      ebx, 80070000h
0x180040eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180040eb1  lea     rax, WPP_GLOBAL_Control
0x180040eb8  cmp     rcx, rax
0x180040ebb  jz      short loc_180040ED2
0x180040ebd  mov     rcx, [rcx+10h]
0x180040ec1  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x180040ec8  mov     edx, 0Fh
0x180040ecd  call    WPP_SF_
0x180040ed2  mov     eax, ebx
0x180040ed4  mov     rbx, [rsp+38h+arg_8]
0x180040ed9  add     rsp, 30h
0x180040edd  pop     rdi
0x180040ede  retn
```
