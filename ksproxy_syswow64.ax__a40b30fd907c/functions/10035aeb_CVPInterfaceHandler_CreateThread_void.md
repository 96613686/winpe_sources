# CVPInterfaceHandler::CreateThread(void)

- ea: `0x10035aeb`
- end: `0x10035baa`
- name: `?CreateThread@CVPInterfaceHandler@@QAEJXZ`
- size: `191`
- prototype: `unsigned int __thiscall(CVPInterfaceHandler *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1003623a`
- `0x1003671a`

## callees

- `0x100063f1`
- `0x10035aeb`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10035b2f`
- `KERNEL32!GetLastError` at `0x10035b70`
- `KERNEL32!GetLastError` at `0x10035b2f`
- `KERNEL32!GetLastError` at `0x10035b70`
- `KERNEL32!CreateEventW` at `0x10035b08`
- `KERNEL32!CreateEventW` at `0x10035b08`
- `KERNEL32!CloseHandle` at `0x10035b65`
- `KERNEL32!CloseHandle` at `0x10035b65`
- `KERNEL32!CreateThread` at `0x10035b22`
- `KERNEL32!CreateThread` at `0x10035b22`

## pseudocode

```c
unsigned int __thiscall CVPInterfaceHandler::CreateThread(CVPInterfaceHandler *this)
{
  unsigned int v2; // esi
  HANDLE EventW; // eax
  HANDLE v4; // eax
  signed int LastError; // eax
  signed int v6; // eax
  DWORD ThreadId; // [esp+Ch] [ebp-4h] BYREF

  v2 = 0;
  if ( !this->m_ThreadHandle )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    this->m_EndEventHandle = EventW;
    if ( EventW )
    {
      v4 = CreateThread(0, 0, CVPInterfaceHandler::InitialThreadProc, this, 0, &ThreadId);
      this->m_ThreadHandle = v4;
      if ( !v4 )
      {
        LastError = GetLastError();
        v2 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v2 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(0xEu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
        CloseHandle(this->m_EndEventHandle);
        this->m_EndEventHandle = 0;
      }
    }
    else
    {
      v6 = GetLastError();
      v2 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v2 = v6;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(0xFu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  return v2;
}

```

## disassembly

```asm
0x10035aeb  mov     edi, edi
0x10035aed  push    ebp
0x10035aee  mov     ebp, esp
0x10035af0  push    ecx
0x10035af1  push    ebx
0x10035af2  push    esi
0x10035af3  push    edi
0x10035af4  mov     edi, ecx
0x10035af6  xor     ebx, ebx
0x10035af8  mov     esi, ebx
0x10035afa  cmp     [edi+30h], ebx
0x10035afd  jnz     loc_10035BA3
0x10035b03  push    ebx; lpName
0x10035b04  push    ebx; bInitialState
0x10035b05  push    1; bManualReset
0x10035b07  push    ebx; lpEventAttributes
0x10035b08  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10035b0e  mov     [edi+14h], eax
0x10035b11  test    eax, eax
0x10035b13  jz      short loc_10035B70
0x10035b15  lea     eax, [ebp+ThreadId]
0x10035b18  push    eax; lpThreadId
0x10035b19  push    ebx; dwCreationFlags
0x10035b1a  push    edi; lpParameter
0x10035b1b  push    offset ?InitialThreadProc@CVPInterfaceHandler@@SGKPAV1@@Z; lpStartAddress
0x10035b20  push    ebx; dwStackSize
0x10035b21  push    ebx; lpThreadAttributes
0x10035b22  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10035b28  mov     [edi+30h], eax
0x10035b2b  test    eax, eax
0x10035b2d  jnz     short loc_10035BA3
0x10035b2f  call    ds:__imp__GetLastError@0; GetLastError()
0x10035b35  movzx   esi, ax
0x10035b38  or      esi, 80070000h
0x10035b3e  test    eax, eax
0x10035b40  cmovle  esi, eax
0x10035b43  mov     eax, _WPP_GLOBAL_Control
0x10035b48  cmp     eax, offset _WPP_GLOBAL_Control
0x10035b4d  jz      short loc_10035B62
0x10035b4f  push    dword ptr [eax+14h]
0x10035b52  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10035b57  push    dword ptr [eax+10h]; LoggerHandle
0x10035b5a  push    0Eh
0x10035b5c  pop     ecx; MessageNumber
0x10035b5d  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10035b62  push    dword ptr [edi+14h]; hObject
0x10035b65  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10035b6b  mov     [edi+14h], ebx
0x10035b6e  jmp     short loc_10035BA3
0x10035b70  call    ds:__imp__GetLastError@0; GetLastError()
0x10035b76  movzx   esi, ax
0x10035b79  or      esi, 80070000h
0x10035b7f  test    eax, eax
0x10035b81  cmovle  esi, eax
0x10035b84  mov     eax, _WPP_GLOBAL_Control
0x10035b89  cmp     eax, offset _WPP_GLOBAL_Control
0x10035b8e  jz      short loc_10035BA3
0x10035b90  push    dword ptr [eax+14h]
0x10035b93  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10035b98  push    dword ptr [eax+10h]; LoggerHandle
0x10035b9b  push    0Fh
0x10035b9d  pop     ecx; MessageNumber
0x10035b9e  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10035ba3  pop     edi
0x10035ba4  mov     eax, esi
0x10035ba6  pop     esi
0x10035ba7  pop     ebx
0x10035ba8  leave
0x10035ba9  retn
```
