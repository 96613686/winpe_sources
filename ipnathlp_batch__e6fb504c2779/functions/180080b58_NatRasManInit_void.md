# NatRasManInit(void)

- ea: `0x180080b58`
- end: `0x180080de2`
- name: `?NatRasManInit@@YAJXZ`
- size: `650`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180080298`

## callees

- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x1800533e8`
- `0x180053534`
- `0x180080b58`
- `0x180080e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080c0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c24`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180080c6f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180080c6f`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x180080d14`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x180080d14`
- `ext-ms-win-ras-rasman-l1-1-0!RasReferenceRasman` at `0x180080ccc`
- `ext-ms-win-ras-rasman-l1-1-0!RasReferenceRasman` at `0x180080ccc`
- `ext-ms-win-ras-rasman-l1-1-0!RasInitialize` at `0x180080bc3`
- `ext-ms-win-ras-rasman-l1-1-0!RasInitialize` at `0x180080bc3`

## pseudocode

```c
__int64 NatRasManInit(void)
{
  signed int v0; // ebx
  PVOID *v1; // rcx
  __int64 v2; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v5; // sf

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  if ( (unsigned __int8)IsRasReferenceRasmanPresent()
    && (unsigned __int8)IsRasReferenceRasmanPresent()
    && (unsigned __int8)IsRasQuerySharedAutoDialPresent() )
  {
    v0 = RasInitialize();
    if ( v0 )
    {
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      v2 = 241;
    }
    else
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *(&gNatRasManState + 1) = EventW;
      if ( !EventW || !RegisterWaitForSingleObject(&phNewWaitObject, EventW, NatRasManOnNotify, 0, 0xFFFFFFFF, 0) )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          v0 = (unsigned __int16)LastError | 0x80070000;
        v1 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_37;
      }
      if ( !AcquireComponentReference(&NatComponentReference) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, 1003);
        }
        v0 = -2147023893;
LABEL_39:
        NatRasManShutdown();
LABEL_41:
        v1 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_42;
      }
      v0 = RasReferenceRasman(1);
      if ( v0 )
      {
        v1 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_35;
        }
        v2 = 243;
      }
      else
      {
        *(&gNatRasManState + 1) = 1;
        v0 = RasConnectionNotificationW((HRASCONN)0xFFFFFFFFFFFFFFFFLL, *(&gNatRasManState + 1), 3u);
        if ( !v0 )
        {
          v0 = 0;
          *(&gNatRasManState + 2) = 1;
          goto LABEL_41;
        }
        v1 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_35;
        }
        v2 = 244;
      }
    }
    WPP_SF_d(v1[2], v2, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, (unsigned int)v0);
    v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_35:
    v5 = v0 < 0;
    if ( v0 <= 0 )
      goto LABEL_38;
    v0 = (unsigned __int16)v0 | 0x80070000;
LABEL_37:
    v5 = v0 < 0;
LABEL_38:
    if ( !v5 )
    {
LABEL_42:
      if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x200) != 0 && *((_BYTE *)v1 + 25) >= 6u )
        WPP_SF_d(v1[2], 245, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, (unsigned int)v0);
      return (unsigned int)v0;
    }
    goto LABEL_39;
  }
  v0 = 50;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, 50);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180080b58  push    rbx
0x180080b5a  push    rbp
0x180080b5b  push    rsi
0x180080b5c  push    rdi
0x180080b5d  sub     rsp, 38h
0x180080b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180080b68  lea     rsi, WPP_GLOBAL_Control
0x180080b6f  lea     rbp, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180080b76  mov     edi, 200h
0x180080b7b  cmp     rcx, rsi
0x180080b7e  jz      short loc_180080B9C
0x180080b80  test    [rcx+1Ch], edi
0x180080b83  jz      short loc_180080B9C
0x180080b85  cmp     byte ptr [rcx+19h], 6
0x180080b89  jb      short loc_180080B9C
0x180080b8b  mov     rcx, [rcx+10h]
0x180080b8f  mov     edx, 0EFh
0x180080b94  mov     r8, rbp
0x180080b97  call    WPP_SF_
0x180080b9c  call    IsRasReferenceRasmanPresent
0x180080ba1  test    al, al
0x180080ba3  jz      loc_180080DA6
0x180080ba9  call    IsRasReferenceRasmanPresent
0x180080bae  test    al, al
0x180080bb0  jz      loc_180080DA6
0x180080bb6  call    IsRasQuerySharedAutoDialPresent
0x180080bbb  test    al, al
0x180080bbd  jz      loc_180080DA6
0x180080bc3  call    cs:__imp_RasInitialize
0x180080bca  nop     dword ptr [rax+rax+00h]
0x180080bcf  mov     ebx, eax
0x180080bd1  test    eax, eax
0x180080bd3  jz      short loc_180080C02
0x180080bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180080bdc  cmp     rcx, rsi
0x180080bdf  jz      loc_180080D58
0x180080be5  test    [rcx+1Ch], edi
0x180080be8  jz      loc_180080D58
0x180080bee  cmp     byte ptr [rcx+19h], 2
0x180080bf2  jb      loc_180080D58
0x180080bf8  mov     edx, 0F1h
0x180080bfd  jmp     loc_180080D42
0x180080c02  xor     r9d, r9d; lpName
0x180080c05  xor     r8d, r8d; bInitialState
0x180080c08  xor     edx, edx; bManualReset
0x180080c0a  xor     ecx, ecx; lpEventAttributes
0x180080c0c  call    cs:__imp_CreateEventW
0x180080c13  nop     dword ptr [rax+rax+00h]
0x180080c18  mov     qword ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+8, rax; NAT_RASMAN_STATE gNatRasManState
0x180080c1f  test    rax, rax
0x180080c22  jnz     short loc_180080C4B
0x180080c24  call    cs:__imp_GetLastError
0x180080c2b  nop     dword ptr [rax+rax+00h]
0x180080c30  mov     ebx, eax
0x180080c32  test    eax, eax
0x180080c34  jle     short loc_180080C3F
0x180080c36  movzx   ebx, ax
0x180080c39  or      ebx, 80070000h
0x180080c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180080c46  jmp     loc_180080D65
0x180080c4b  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180080c53  lea     r8, ?NatRasManOnNotify@@YAXPEAXE@Z; Callback
0x180080c5a  xor     r9d, r9d; Context
0x180080c5d  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180080c65  mov     rdx, rax; hObject
0x180080c68  lea     rcx, phNewWaitObject; phNewWaitObject
0x180080c6f  call    cs:__imp_RegisterWaitForSingleObject
0x180080c76  nop     dword ptr [rax+rax+00h]
0x180080c7b  test    eax, eax
0x180080c7d  jz      short loc_180080C24
0x180080c7f  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x180080c86  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180080c8b  test    al, al
0x180080c8d  jnz     short loc_180080CC7
0x180080c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180080c96  cmp     rcx, rsi
0x180080c99  jz      short loc_180080CBD
0x180080c9b  test    [rcx+1Ch], edi
0x180080c9e  jz      short loc_180080CBD
0x180080ca0  cmp     byte ptr [rcx+19h], 6
0x180080ca4  jb      short loc_180080CBD
0x180080ca6  mov     rcx, [rcx+10h]
0x180080caa  mov     edx, 0F2h
0x180080caf  mov     r9d, 3EBh
0x180080cb5  mov     r8, rbp
0x180080cb8  call    WPP_SF_d
0x180080cbd  mov     ebx, 800703EBh
0x180080cc2  jmp     loc_180080D69
0x180080cc7  mov     ecx, 1
0x180080ccc  call    cs:__imp_RasReferenceRasman
0x180080cd3  nop     dword ptr [rax+rax+00h]
0x180080cd8  mov     ebx, eax
0x180080cda  test    eax, eax
0x180080cdc  jz      short loc_180080CFC
0x180080cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180080ce5  cmp     rcx, rsi
0x180080ce8  jz      short loc_180080D58
0x180080cea  test    [rcx+1Ch], edi
0x180080ced  jz      short loc_180080D58
0x180080cef  cmp     byte ptr [rcx+19h], 2
0x180080cf3  jb      short loc_180080D58
0x180080cf5  mov     edx, 0F3h
0x180080cfa  jmp     short loc_180080D42
0x180080cfc  mov     rdx, qword ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+8; HANDLE
0x180080d03  mov     r8d, 3; DWORD
0x180080d09  or      rcx, 0FFFFFFFFFFFFFFFFh; HRASCONN
0x180080d0d  mov     byte ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+1, 1; NAT_RASMAN_STATE gNatRasManState
0x180080d14  call    cs:__imp_RasConnectionNotificationW
0x180080d1b  nop     dword ptr [rax+rax+00h]
0x180080d20  mov     ebx, eax
0x180080d22  test    eax, eax
0x180080d24  jz      short loc_180080D70
0x180080d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d2d  cmp     rcx, rsi
0x180080d30  jz      short loc_180080D58
0x180080d32  test    [rcx+1Ch], edi
0x180080d35  jz      short loc_180080D58
0x180080d37  cmp     byte ptr [rcx+19h], 2
0x180080d3b  jb      short loc_180080D58
0x180080d3d  mov     edx, 0F4h
0x180080d42  mov     rcx, [rcx+10h]
0x180080d46  mov     r9d, ebx
0x180080d49  mov     r8, rbp
0x180080d4c  call    WPP_SF_d
0x180080d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d58  test    ebx, ebx
0x180080d5a  jle     short loc_180080D67
0x180080d5c  movzx   ebx, bx
0x180080d5f  or      ebx, 80070000h
0x180080d65  test    ebx, ebx
0x180080d67  jns     short loc_180080D80
0x180080d69  call    ?NatRasManShutdown@@YAXXZ; NatRasManShutdown(void)
0x180080d6e  jmp     short loc_180080D79
0x180080d70  xor     ebx, ebx
0x180080d72  mov     byte ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+2, 1; NAT_RASMAN_STATE gNatRasManState
0x180080d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180080d80  cmp     rcx, rsi
0x180080d83  jz      short loc_180080DD6
0x180080d85  test    [rcx+1Ch], edi
0x180080d88  jz      short loc_180080DD6
0x180080d8a  cmp     byte ptr [rcx+19h], 6
0x180080d8e  jb      short loc_180080DD6
0x180080d90  mov     rcx, [rcx+10h]
0x180080d94  mov     edx, 0F5h
0x180080d99  mov     r9d, ebx
0x180080d9c  mov     r8, rbp
0x180080d9f  call    WPP_SF_d
0x180080da4  jmp     short loc_180080DD6
0x180080da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180080dad  mov     ebx, 32h ; '2'
0x180080db2  cmp     rcx, rsi
0x180080db5  jz      short loc_180080DD6
0x180080db7  test    [rcx+1Ch], edi
0x180080dba  jz      short loc_180080DD6
0x180080dbc  cmp     byte ptr [rcx+19h], 6
0x180080dc0  jb      short loc_180080DD6
0x180080dc2  mov     rcx, [rcx+10h]
0x180080dc6  mov     edx, 0F0h
0x180080dcb  mov     r9d, ebx
0x180080dce  mov     r8, rbp
0x180080dd1  call    WPP_SF_d
0x180080dd6  mov     eax, ebx
0x180080dd8  add     rsp, 38h
0x180080ddc  pop     rdi
0x180080ddd  pop     rsi
0x180080dde  pop     rbp
0x180080ddf  pop     rbx
0x180080de0  retn
```
