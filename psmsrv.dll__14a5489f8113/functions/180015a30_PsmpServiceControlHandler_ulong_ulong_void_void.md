# PsmpServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x180015a30`
- end: `0x180015aff`
- name: `?PsmpServiceControlHandler@@YAKKKPEAX0@Z`
- size: `207`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, _DWORD *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180015a30`
- `0x180019b7c`
- `0x18001c9d8`

## import_xrefs

- `ext-ms-win-core-psm-service-l1-1-4!PsmCrmSessionUserNotification` at `0x180015a9b`
- `ext-ms-win-core-psm-service-l1-1-4!PsmCrmSessionUserNotification` at `0x180015a9b`
- `ext-ms-win-core-psm-service-l1-1-4!PsmCrmSuspendNotification` at `0x180015ad7`
- `ext-ms-win-core-psm-service-l1-1-4!PsmCrmSuspendNotification` at `0x180015ad7`
- `ext-ms-win-core-psm-bi-l1-1-0!PsmBiExtNotifySessionUserStateChange` at `0x180015af7`
- `ext-ms-win-core-psm-bi-l1-1-0!PsmBiExtNotifySessionUserStateChange` at `0x180015af7`
- `ext-ms-win-core-psm-bi-l1-1-0!PsmBiExtNotifySessionStateChange` at `0x180015ab4`
- `ext-ms-win-core-psm-bi-l1-1-0!PsmBiExtNotifySessionStateChange` at `0x180015ab4`

## pseudocode

```c
__int64 __fastcall PsmpServiceControlHandler(
        DWORD dwControl,
        __int64 dwEventType,
        _DWORD *lpEventData,
        LPVOID lpContext)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  DWORD v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int v10; // esi
  __int64 v11; // rbp
  unsigned int v12; // esi
  bool v13; // bl
  __int64 v14; // rcx

  v4 = 0;
  v5 = dwEventType;
  v6 = dwControl - 4;
  if ( v6 )
  {
    v7 = v6 - 9;
    if ( !(_DWORD)v7 )
    {
      if ( (_DWORD)dwEventType == 4 || (_DWORD)dwEventType == 6 || (_DWORD)dwEventType == 7 || (_DWORD)dwEventType == 18 )
      {
        v13 = (_DWORD)dwEventType == 4;
        LOBYTE(v7) = (_DWORD)dwEventType == 4;
        PsmpResourceAwareTimerSuspendNotification(v7, dwEventType, lpEventData, lpContext);
        LOBYTE(v14) = v13;
        PsmCrmSuspendNotification(v14);
        return v4;
      }
      return 120;
    }
    v8 = (unsigned int)(v7 - 1);
    if ( (_DWORD)v8 )
    {
      if ( (_DWORD)v8 != 19 || (_DWORD)dwEventType != 5 && (_DWORD)dwEventType != 6 )
        return 120;
      v10 = lpEventData[1];
      v11 = *((_QWORD *)lpEventData + 1);
      if ( (unsigned __int8)IsPsmBiExtNotifySessionStateChangePresent(v8, dwEventType, lpEventData, lpContext) )
        PsmBiExtNotifySessionUserStateChange(v11, v10, v5);
      PsmCrmSessionUserNotification(v5);
    }
    else
    {
      if ( (_DWORD)dwEventType != 1
        && (_DWORD)dwEventType != 2
        && (_DWORD)dwEventType != 3
        && (_DWORD)dwEventType != 4
        && (_DWORD)dwEventType != 6 )
      {
        return 120;
      }
      v12 = lpEventData[1];
      if ( (unsigned __int8)IsPsmBiExtNotifySessionStateChangePresent(v8, dwEventType, lpEventData, lpContext) )
        PsmBiExtNotifySessionStateChange(v12, v5);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180015a30  push    rbx
0x180015a32  push    rbp
0x180015a33  push    rsi
0x180015a34  push    rdi
0x180015a35  sub     rsp, 28h
0x180015a39  xor     edi, edi
0x180015a3b  mov     ebx, edx
0x180015a3d  sub     ecx, 4
0x180015a40  jz      short loc_180015A6C
0x180015a42  sub     ecx, 9
0x180015a45  jz      short loc_180015ABC
0x180015a47  sub     ecx, 1
0x180015a4a  jnz     short loc_180015A77
0x180015a4c  mov     eax, edx
0x180015a4e  sub     eax, 1
0x180015a51  jz      short loc_180015AA3
0x180015a53  sub     eax, 1
0x180015a56  jz      short loc_180015AA3
0x180015a58  sub     eax, 1
0x180015a5b  jz      short loc_180015AA3
0x180015a5d  sub     eax, 1
0x180015a60  jz      short loc_180015AA3
0x180015a62  cmp     eax, 2
0x180015a65  jz      short loc_180015AA3
0x180015a67  mov     edi, 78h ; 'x'
0x180015a6c  mov     eax, edi
0x180015a6e  add     rsp, 28h
0x180015a72  pop     rdi
0x180015a73  pop     rsi
0x180015a74  pop     rbp
0x180015a75  pop     rbx
0x180015a76  retn
0x180015a77  cmp     ecx, 13h
0x180015a7a  jnz     short loc_180015A67
0x180015a7c  mov     eax, ebx
0x180015a7e  sub     eax, 5
0x180015a81  jz      short loc_180015A88
0x180015a83  cmp     eax, 1
0x180015a86  jnz     short loc_180015A67
0x180015a88  mov     esi, [r8+4]
0x180015a8c  mov     rbp, [r8+8]
0x180015a90  call    IsPsmBiExtNotifySessionStateChangePresent
0x180015a95  test    al, al
0x180015a97  jnz     short loc_180015AEF
0x180015a99  mov     ecx, ebx
0x180015a9b  call    cs:__imp_PsmCrmSessionUserNotification
0x180015aa1  jmp     short loc_180015A6C
0x180015aa3  mov     esi, [r8+4]
0x180015aa7  call    IsPsmBiExtNotifySessionStateChangePresent
0x180015aac  test    al, al
0x180015aae  jz      short loc_180015A6C
0x180015ab0  mov     edx, ebx
0x180015ab2  mov     ecx, esi
0x180015ab4  call    cs:__imp_PsmBiExtNotifySessionStateChange
0x180015aba  jmp     short loc_180015A6C
0x180015abc  mov     eax, ebx
0x180015abe  sub     eax, 4
0x180015ac1  jz      short loc_180015AC8
0x180015ac3  sub     eax, 2
0x180015ac6  jnz     short loc_180015ADF
0x180015ac8  cmp     ebx, 4
0x180015acb  setz    bl
0x180015ace  mov     cl, bl
0x180015ad0  call    PsmpResourceAwareTimerSuspendNotification
0x180015ad5  mov     cl, bl
0x180015ad7  call    cs:__imp_PsmCrmSuspendNotification
0x180015add  jmp     short loc_180015A6C
0x180015adf  sub     eax, 1
0x180015ae2  jz      short loc_180015AC8
0x180015ae4  cmp     eax, 0Bh
0x180015ae7  jnz     loc_180015A67
0x180015aed  jmp     short loc_180015AC8
0x180015aef  mov     r8d, ebx
0x180015af2  mov     edx, esi
0x180015af4  mov     rcx, rbp
0x180015af7  call    cs:__imp_PsmBiExtNotifySessionUserStateChange
0x180015afd  jmp     short loc_180015A99
```
