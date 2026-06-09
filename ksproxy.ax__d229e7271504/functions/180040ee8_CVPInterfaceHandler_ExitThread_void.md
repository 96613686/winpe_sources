# CVPInterfaceHandler::ExitThread(void)

- ea: `0x180040ee8`
- end: `0x180040fc2`
- name: `?ExitThread@CVPInterfaceHandler@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(CVPInterfaceHandler *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180040a8c`
- `0x180040af0`
- `0x180040ba8`

## callees

- `0x180002b58`
- `0x180025860`
- `0x180040ee8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040f60`
- `KERNEL32!GetLastError` at `0x180040f60`
- `KERNEL32!SetEvent` at `0x180040f00`
- `KERNEL32!SetEvent` at `0x180040f00`
- `KERNEL32!WaitForSingleObjectEx` at `0x180040f42`
- `KERNEL32!WaitForSingleObjectEx` at `0x180040f42`
- `KERNEL32!CloseHandle` at `0x180040f8f`
- `KERNEL32!CloseHandle` at `0x180040fa7`
- `KERNEL32!CloseHandle` at `0x180040f8f`
- `KERNEL32!CloseHandle` at `0x180040fa7`

## pseudocode

```c
void __fastcall CVPInterfaceHandler::ExitThread(CVPInterfaceHandler *this)
{
  DWORD LastError; // eax
  void *m_ThreadHandle; // rcx

  if ( this->m_ThreadHandle )
  {
    if ( SetEvent(this->m_EndEventHandle) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x10u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
      WaitForSingleObjectEx(this->m_ThreadHandle, 0xFFFFFFFF, 0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x11u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, LastError);
    }
    CloseHandle(this->m_EndEventHandle);
    m_ThreadHandle = this->m_ThreadHandle;
    this->m_EndEventHandle = 0;
    CloseHandle(m_ThreadHandle);
    this->m_ThreadHandle = 0;
  }
}

```

## disassembly

```asm
0x180040ee8  push    rbx
0x180040eea  sub     rsp, 20h
0x180040eee  cmp     qword ptr [rcx+60h], 0
0x180040ef3  mov     rbx, rcx
0x180040ef6  jz      loc_180040FBB
0x180040efc  mov     rcx, [rcx+28h]; hEvent
0x180040f00  call    cs:__imp_SetEvent
0x180040f07  nop     dword ptr [rax+rax+00h]
0x180040f0c  test    eax, eax
0x180040f0e  jz      short loc_180040F50
0x180040f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f17  lea     rax, WPP_GLOBAL_Control
0x180040f1e  cmp     rcx, rax
0x180040f21  jz      short loc_180040F38
0x180040f23  mov     rcx, [rcx+10h]
0x180040f27  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x180040f2e  mov     edx, 10h
0x180040f33  call    WPP_SF_
0x180040f38  mov     rcx, [rbx+60h]; hHandle
0x180040f3c  xor     r8d, r8d; bAlertable
0x180040f3f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180040f42  call    cs:__imp_WaitForSingleObjectEx
0x180040f49  nop     dword ptr [rax+rax+00h]
0x180040f4e  jmp     short loc_180040F8B
0x180040f50  lea     rax, WPP_GLOBAL_Control
0x180040f57  cmp     cs:WPP_GLOBAL_Control, rax
0x180040f5e  jz      short loc_180040F8B
0x180040f60  call    cs:__imp_GetLastError
0x180040f67  nop     dword ptr [rax+rax+00h]
0x180040f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f73  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x180040f7a  mov     edx, 11h
0x180040f7f  mov     r9d, eax
0x180040f82  mov     rcx, [rcx+10h]
0x180040f86  call    WPP_SF_d
0x180040f8b  mov     rcx, [rbx+28h]; hObject
0x180040f8f  call    cs:__imp_CloseHandle
0x180040f96  nop     dword ptr [rax+rax+00h]
0x180040f9b  mov     rcx, [rbx+60h]; hObject
0x180040f9f  mov     qword ptr [rbx+28h], 0
0x180040fa7  call    cs:__imp_CloseHandle
0x180040fae  nop     dword ptr [rax+rax+00h]
0x180040fb3  mov     qword ptr [rbx+60h], 0
0x180040fbb  add     rsp, 20h
0x180040fbf  pop     rbx
0x180040fc0  retn
```
