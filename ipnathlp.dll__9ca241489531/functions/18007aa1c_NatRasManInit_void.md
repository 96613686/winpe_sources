# NatRasManInit(void)

- ea: `0x18007aa1c`
- end: `0x18007ac81`
- name: `?NatRasManInit@@YAJXZ`
- size: `613`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007a1b8`

## callees

- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x18004f558`
- `0x18004f6a4`
- `0x18007aa1c`
- `0x18007ad30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007aaca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007aaca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aadc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007ab21`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007ab21`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x18007abba`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x18007abba`
- `ext-ms-win-ras-rasman-l1-1-0!RasReferenceRasman` at `0x18007ab78`
- `ext-ms-win-ras-rasman-l1-1-0!RasReferenceRasman` at `0x18007ab78`
- `ext-ms-win-ras-rasman-l1-1-0!RasInitialize` at `0x18007aa87`
- `ext-ms-win-ras-rasman-l1-1-0!RasInitialize` at `0x18007aa87`

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
0x18007aa1c  push    rbx
0x18007aa1e  push    rbp
0x18007aa1f  push    rsi
0x18007aa20  push    rdi
0x18007aa21  sub     rsp, 38h
0x18007aa25  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aa2c  lea     rsi, WPP_GLOBAL_Control
0x18007aa33  lea     rbp, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007aa3a  mov     edi, 200h
0x18007aa3f  cmp     rcx, rsi
0x18007aa42  jz      short loc_18007AA60
0x18007aa44  test    [rcx+1Ch], edi
0x18007aa47  jz      short loc_18007AA60
0x18007aa49  cmp     byte ptr [rcx+19h], 6
0x18007aa4d  jb      short loc_18007AA60
0x18007aa4f  mov     rcx, [rcx+10h]
0x18007aa53  mov     edx, 0EFh
0x18007aa58  mov     r8, rbp
0x18007aa5b  call    WPP_SF_
0x18007aa60  call    IsRasReferenceRasmanPresent
0x18007aa65  test    al, al
0x18007aa67  jz      loc_18007AC46
0x18007aa6d  call    IsRasReferenceRasmanPresent
0x18007aa72  test    al, al
0x18007aa74  jz      loc_18007AC46
0x18007aa7a  call    IsRasQuerySharedAutoDialPresent
0x18007aa7f  test    al, al
0x18007aa81  jz      loc_18007AC46
0x18007aa87  call    cs:__imp_RasInitialize
0x18007aa8d  mov     ebx, eax
0x18007aa8f  test    eax, eax
0x18007aa91  jz      short loc_18007AAC0
0x18007aa93  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aa9a  cmp     rcx, rsi
0x18007aa9d  jz      loc_18007ABF8
0x18007aaa3  test    [rcx+1Ch], edi
0x18007aaa6  jz      loc_18007ABF8
0x18007aaac  cmp     byte ptr [rcx+19h], 2
0x18007aab0  jb      loc_18007ABF8
0x18007aab6  mov     edx, 0F1h
0x18007aabb  jmp     loc_18007ABE2
0x18007aac0  xor     r9d, r9d; lpName
0x18007aac3  xor     r8d, r8d; bInitialState
0x18007aac6  xor     edx, edx; bManualReset
0x18007aac8  xor     ecx, ecx; lpEventAttributes
0x18007aaca  call    cs:__imp_CreateEventW
0x18007aad0  mov     qword ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+8, rax; NAT_RASMAN_STATE gNatRasManState
0x18007aad7  test    rax, rax
0x18007aada  jnz     short loc_18007AAFD
0x18007aadc  call    cs:__imp_GetLastError
0x18007aae2  mov     ebx, eax
0x18007aae4  test    eax, eax
0x18007aae6  jle     short loc_18007AAF1
0x18007aae8  movzx   ebx, ax
0x18007aaeb  or      ebx, 80070000h
0x18007aaf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aaf8  jmp     loc_18007AC05
0x18007aafd  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18007ab05  lea     r8, ?NatRasManOnNotify@@YAXPEAXE@Z; Callback
0x18007ab0c  xor     r9d, r9d; Context
0x18007ab0f  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18007ab17  mov     rdx, rax; hObject
0x18007ab1a  lea     rcx, phNewWaitObject; phNewWaitObject
0x18007ab21  call    cs:__imp_RegisterWaitForSingleObject
0x18007ab27  test    eax, eax
0x18007ab29  jz      short loc_18007AADC
0x18007ab2b  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18007ab32  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18007ab37  test    al, al
0x18007ab39  jnz     short loc_18007AB73
0x18007ab3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab42  cmp     rcx, rsi
0x18007ab45  jz      short loc_18007AB69
0x18007ab47  test    [rcx+1Ch], edi
0x18007ab4a  jz      short loc_18007AB69
0x18007ab4c  cmp     byte ptr [rcx+19h], 6
0x18007ab50  jb      short loc_18007AB69
0x18007ab52  mov     rcx, [rcx+10h]
0x18007ab56  mov     edx, 0F2h
0x18007ab5b  mov     r9d, 3EBh
0x18007ab61  mov     r8, rbp
0x18007ab64  call    WPP_SF_d
0x18007ab69  mov     ebx, 800703EBh
0x18007ab6e  jmp     loc_18007AC09
0x18007ab73  mov     ecx, 1
0x18007ab78  call    cs:__imp_RasReferenceRasman
0x18007ab7e  mov     ebx, eax
0x18007ab80  test    eax, eax
0x18007ab82  jz      short loc_18007ABA2
0x18007ab84  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab8b  cmp     rcx, rsi
0x18007ab8e  jz      short loc_18007ABF8
0x18007ab90  test    [rcx+1Ch], edi
0x18007ab93  jz      short loc_18007ABF8
0x18007ab95  cmp     byte ptr [rcx+19h], 2
0x18007ab99  jb      short loc_18007ABF8
0x18007ab9b  mov     edx, 0F3h
0x18007aba0  jmp     short loc_18007ABE2
0x18007aba2  mov     rdx, qword ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+8; HANDLE
0x18007aba9  mov     r8d, 3; DWORD
0x18007abaf  or      rcx, 0FFFFFFFFFFFFFFFFh; HRASCONN
0x18007abb3  mov     byte ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+1, 1; NAT_RASMAN_STATE gNatRasManState
0x18007abba  call    cs:__imp_RasConnectionNotificationW
0x18007abc0  mov     ebx, eax
0x18007abc2  test    eax, eax
0x18007abc4  jz      short loc_18007AC10
0x18007abc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007abcd  cmp     rcx, rsi
0x18007abd0  jz      short loc_18007ABF8
0x18007abd2  test    [rcx+1Ch], edi
0x18007abd5  jz      short loc_18007ABF8
0x18007abd7  cmp     byte ptr [rcx+19h], 2
0x18007abdb  jb      short loc_18007ABF8
0x18007abdd  mov     edx, 0F4h
0x18007abe2  mov     rcx, [rcx+10h]
0x18007abe6  mov     r9d, ebx
0x18007abe9  mov     r8, rbp
0x18007abec  call    WPP_SF_d
0x18007abf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007abf8  test    ebx, ebx
0x18007abfa  jle     short loc_18007AC07
0x18007abfc  movzx   ebx, bx
0x18007abff  or      ebx, 80070000h
0x18007ac05  test    ebx, ebx
0x18007ac07  jns     short loc_18007AC20
0x18007ac09  call    ?NatRasManShutdown@@YAXXZ; NatRasManShutdown(void)
0x18007ac0e  jmp     short loc_18007AC19
0x18007ac10  xor     ebx, ebx
0x18007ac12  mov     byte ptr cs:?gNatRasManState@@3UNAT_RASMAN_STATE@@A+2, 1; NAT_RASMAN_STATE gNatRasManState
0x18007ac19  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac20  cmp     rcx, rsi
0x18007ac23  jz      short loc_18007AC76
0x18007ac25  test    [rcx+1Ch], edi
0x18007ac28  jz      short loc_18007AC76
0x18007ac2a  cmp     byte ptr [rcx+19h], 6
0x18007ac2e  jb      short loc_18007AC76
0x18007ac30  mov     rcx, [rcx+10h]
0x18007ac34  mov     edx, 0F5h
0x18007ac39  mov     r9d, ebx
0x18007ac3c  mov     r8, rbp
0x18007ac3f  call    WPP_SF_d
0x18007ac44  jmp     short loc_18007AC76
0x18007ac46  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac4d  mov     ebx, 32h ; '2'
0x18007ac52  cmp     rcx, rsi
0x18007ac55  jz      short loc_18007AC76
0x18007ac57  test    [rcx+1Ch], edi
0x18007ac5a  jz      short loc_18007AC76
0x18007ac5c  cmp     byte ptr [rcx+19h], 6
0x18007ac60  jb      short loc_18007AC76
0x18007ac62  mov     rcx, [rcx+10h]
0x18007ac66  mov     edx, 0F0h
0x18007ac6b  mov     r9d, ebx
0x18007ac6e  mov     r8, rbp
0x18007ac71  call    WPP_SF_d
0x18007ac76  mov     eax, ebx
0x18007ac78  add     rsp, 38h
0x18007ac7c  pop     rdi
0x18007ac7d  pop     rsi
0x18007ac7e  pop     rbp
0x18007ac7f  pop     rbx
0x18007ac80  retn
```
