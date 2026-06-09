# CVPInterfaceHandler::ExitThread(void)

- ea: `0x10035bb0`
- end: `0x10035c3f`
- name: `?ExitThread@CVPInterfaceHandler@@QAEXXZ`
- size: `143`
- prototype: `void __thiscall(CVPInterfaceHandler *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1003599a`
- `0x100363ca`
- `0x100368aa`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x10035bb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10035c04`
- `KERNEL32!GetLastError` at `0x10035c04`
- `KERNEL32!SetEvent` at `0x10035bc1`
- `KERNEL32!SetEvent` at `0x10035bc1`
- `KERNEL32!WaitForSingleObjectEx` at `0x10035bf0`
- `KERNEL32!WaitForSingleObjectEx` at `0x10035bf0`
- `KERNEL32!CloseHandle` at `0x10035c26`
- `KERNEL32!CloseHandle` at `0x10035c32`
- `KERNEL32!CloseHandle` at `0x10035c26`
- `KERNEL32!CloseHandle` at `0x10035c32`

## pseudocode

```c
void __thiscall CVPInterfaceHandler::ExitThread(CVPInterfaceHandler *this)
{
  char LastError; // al
  void *m_ThreadHandle; // [esp-4h] [ebp-10h]

  if ( this->m_ThreadHandle )
  {
    if ( SetEvent(this->m_EndEventHandle) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(0x10u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
      WaitForSingleObjectEx(this->m_ThreadHandle, 0xFFFFFFFF, 0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_q(0x11u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
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
0x10035bb0  mov     edi, edi
0x10035bb2  push    ecx
0x10035bb3  push    esi
0x10035bb4  mov     esi, ecx
0x10035bb6  push    edi
0x10035bb7  xor     edi, edi
0x10035bb9  cmp     [esi+30h], edi
0x10035bbc  jz      short loc_10035C3B
0x10035bbe  push    dword ptr [esi+14h]; hEvent
0x10035bc1  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10035bc7  test    eax, eax
0x10035bc9  jz      short loc_10035BF8
0x10035bcb  mov     eax, _WPP_GLOBAL_Control
0x10035bd0  cmp     eax, offset _WPP_GLOBAL_Control
0x10035bd5  jz      short loc_10035BEA
0x10035bd7  push    dword ptr [eax+14h]
0x10035bda  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10035bdf  push    dword ptr [eax+10h]; LoggerHandle
0x10035be2  push    10h
0x10035be4  pop     ecx; MessageNumber
0x10035be5  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10035bea  push    edi; bAlertable
0x10035beb  push    0FFFFFFFFh; dwMilliseconds
0x10035bed  push    dword ptr [esi+30h]; hHandle
0x10035bf0  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x10035bf6  jmp     short loc_10035C23
0x10035bf8  cmp     _WPP_GLOBAL_Control, offset _WPP_GLOBAL_Control
0x10035c02  jz      short loc_10035C23
0x10035c04  call    ds:__imp__GetLastError@0; GetLastError()
0x10035c0a  push    eax; char
0x10035c0b  mov     eax, _WPP_GLOBAL_Control
0x10035c10  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10035c15  push    dword ptr [eax+14h]
0x10035c18  push    dword ptr [eax+10h]; LoggerHandle
0x10035c1b  push    11h
0x10035c1d  pop     ecx; MessageNumber
0x10035c1e  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10035c23  push    dword ptr [esi+14h]; hObject
0x10035c26  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10035c2c  push    dword ptr [esi+30h]; hObject
0x10035c2f  mov     [esi+14h], edi
0x10035c32  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10035c38  mov     [esi+30h], edi
0x10035c3b  pop     edi
0x10035c3c  pop     esi
0x10035c3d  pop     ecx
0x10035c3e  retn
```
