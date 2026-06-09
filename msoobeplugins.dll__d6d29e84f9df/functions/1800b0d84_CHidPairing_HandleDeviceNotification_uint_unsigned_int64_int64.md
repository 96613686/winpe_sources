# CHidPairing::_HandleDeviceNotification(uint,unsigned __int64,__int64)

- ea: `0x1800b0d84`
- end: `0x1800b1048`
- name: `?_HandleDeviceNotification@CHidPairing@@AEAA_JI_K_J@Z`
- size: `708`
- prototype: `__int64 __fastcall(CHidPairing *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b2930`

## callees

- `0x18000ac48`
- `0x180019a38`
- `0x1800af95c`
- `0x1800b0d84`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0e0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0e0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0ee1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b0e78`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b0e78`
- `USER32!PostMessageW` at `0x1800b0ea7`
- `USER32!PostMessageW` at `0x1800b0f3e`
- `USER32!PostMessageW` at `0x1800b0f9d`
- `USER32!PostMessageW` at `0x1800b1019`
- `USER32!PostMessageW` at `0x1800b0ea7`
- `USER32!PostMessageW` at `0x1800b0f3e`
- `USER32!PostMessageW` at `0x1800b0f9d`
- `USER32!PostMessageW` at `0x1800b1019`
- `USER32!KillTimer` at `0x1800b0ed8`
- `USER32!KillTimer` at `0x1800b0fc2`
- `USER32!KillTimer` at `0x1800b0ed8`
- `USER32!KillTimer` at `0x1800b0fc2`

## string_xrefs

- `0x1800b0eb9`: `CHidPairing::_HandleDeviceNotification - Failed to post accessory arrival message: hr=0x%08X`
- `0x1800b0e87`: `CHidPairing::_HandleDeviceNotification - Posting HID Arrival notification for accessory: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHidPairing::_HandleDeviceNotification(CHidPairing *this, int a2, __int64 a3, _QWORD *a4)
{
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // rax
  unsigned int Error; // eax
  __int64 v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rax
  char *v15; // rdi
  unsigned int v16; // eax
  LPCWCH lpString1; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h]
  __int64 v20; // [rsp+40h] [rbp-38h]

  if ( !a4 || a2 != 537 )
    return 0;
  if ( a3 == 0x8000 )
  {
    if ( *((_BYTE *)this + 88) )
      return 0;
    v6 = *((_DWORD *)this + 49);
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 1 )
        {
          v8 = *(_QWORD *)((char *)a4 + 12) - *(_QWORD *)&GUID_DEVINTERFACE_HID.Data1;
          if ( !v8 )
            v8 = *(_QWORD *)((char *)a4 + 20) - *(_QWORD *)GUID_DEVINTERFACE_HID.Data4;
          if ( !v8 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)this + 6);
            lpString1 = 0;
            v19 = 0;
            v20 = 0;
            if ( *((_QWORD *)this + 14) )
            {
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
              v19 = -1;
              v20 = -1;
              if ( (int)GetAepIDFromDeviceInterfaceID((char *)a4 + 28, &lpString1) >= 0
                && CompareStringOrdinal(lpString1, -1, *((LPCWCH *)this + 14), -1, 0) == 2 )
              {
                UnattendLogW(
                  0,
                  L"CHidPairing::_HandleDeviceNotification - Posting HID Arrival notification for accessory: %s",
                  (char *)a4 + 28);
                if ( PostMessageW(*((HWND *)this + 8), *((_DWORD *)this + 70), 6u, 2) )
                {
                  *((_BYTE *)this + 88) = 1;
                  KillTimer(*((HWND *)this + 9), 0x3E9u);
                }
                else
                {
                  Error = ResultFromKnownLastError();
                  UnattendLogW(
                    1,
                    L"CHidPairing::_HandleDeviceNotification - Failed to post accessory arrival message: hr=0x%08X",
                    Error);
                }
              }
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)this + 6);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
          }
        }
        return 0;
      }
      v10 = *(_QWORD *)((char *)a4 + 12) - *(_QWORD *)&GUID_DEVINTERFACE_KEYBOARD.Data1;
      if ( !v10 )
        v10 = *(_QWORD *)((char *)a4 + 20) - *(_QWORD *)GUID_DEVINTERFACE_KEYBOARD.Data4;
      if ( !v10 )
      {
        UnattendLogW(
          0,
          L"CHidPairing::_HandleDeviceNotification - Posting HID Arrival notification for keyboard: %s",
          (char *)a4 + 28);
        if ( !PostMessageW(*((HWND *)this + 8), *((_DWORD *)this + 70), 6u, 1) )
        {
          v11 = ResultFromKnownLastError();
          UnattendLogW(
            1,
            L"CHidPairing::_HandleDeviceNotification - Failed to post keyboard arrival message: hr=0x%08X",
            v11);
          return 0;
        }
LABEL_28:
        *((_BYTE *)this + 88) = 1;
        KillTimer(*((HWND *)this + 9), 0x3E9u);
      }
    }
    else
    {
      v12 = *(_QWORD *)((char *)a4 + 12) - *(_QWORD *)&GUID_DEVINTERFACE_MOUSE.Data1;
      if ( !v12 )
        v12 = *(_QWORD *)((char *)a4 + 20) - *(_QWORD *)GUID_DEVINTERFACE_MOUSE.Data4;
      if ( !v12 )
      {
        UnattendLogW(
          0,
          L"CHidPairing::_HandleDeviceNotification - Posting HID Arrival notification for mouse %s",
          (char *)a4 + 28);
        if ( !PostMessageW(*((HWND *)this + 8), *((_DWORD *)this + 70), 6u, 0) )
        {
          v13 = ResultFromKnownLastError();
          UnattendLogW(
            1,
            L"CHidPairing::_HandleDeviceNotification - Failed to post mouse arrival message: hr=0x%08X",
            v13);
          return 0;
        }
        goto LABEL_28;
      }
    }
  }
  else if ( a3 == 32774 )
  {
    v14 = a4[4] - *(_QWORD *)&GUID_BLUETOOTH_KEYPRESS_EVENT.Data1;
    if ( !v14 )
      v14 = a4[5] - *(_QWORD *)GUID_BLUETOOTH_KEYPRESS_EVENT.Data4;
    if ( !v14 )
    {
      v15 = (char *)a4 + 52;
      if ( a4 != (_QWORD *)-52LL )
      {
        UnattendLogW(0, L"CHidPairing::_HandleDeviceNotification - Posting Key Pressed notification");
        if ( !PostMessageW(*((HWND *)this + 8), *((_DWORD *)this + 70), 3u, (unsigned __int8)v15[8]) )
        {
          v16 = ResultFromKnownLastError();
          UnattendLogW(
            1,
            L"CHidPairing::_HandleDeviceNotification - Failed to post key pressed message: hr=0x%08X",
            v16);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800b0d84  push    rbx
0x1800b0d86  push    rsi
0x1800b0d87  push    rdi
0x1800b0d88  push    r14
0x1800b0d8a  sub     rsp, 58h
0x1800b0d8e  mov     rdi, r9
0x1800b0d91  mov     rbx, rcx
0x1800b0d94  test    r9, r9
0x1800b0d97  jz      loc_1800B103C
0x1800b0d9d  cmp     edx, 219h
0x1800b0da3  jnz     loc_1800B103C
0x1800b0da9  cmp     r8, 8000h
0x1800b0db0  jnz     loc_1800B0FCA
0x1800b0db6  cmp     byte ptr [rcx+58h], 0
0x1800b0dba  jnz     loc_1800B103C
0x1800b0dc0  mov     ecx, [rcx+0C4h]
0x1800b0dc6  test    ecx, ecx
0x1800b0dc8  jz      loc_1800B0F59
0x1800b0dce  sub     ecx, 1
0x1800b0dd1  jz      loc_1800B0EF7
0x1800b0dd7  cmp     ecx, 1
0x1800b0dda  jnz     loc_1800B103C
0x1800b0de0  mov     rax, [r9+0Ch]
0x1800b0de4  sub     rax, qword ptr cs:GUID_DEVINTERFACE_HID.Data1
0x1800b0deb  jnz     short loc_1800B0DF8
0x1800b0ded  mov     rax, [r9+14h]
0x1800b0df1  sub     rax, qword ptr cs:GUID_DEVINTERFACE_HID.Data4
0x1800b0df8  test    rax, rax
0x1800b0dfb  jnz     loc_1800B103C
0x1800b0e01  lea     rsi, [rbx+0F0h]
0x1800b0e08  mov     rcx, rsi; lpCriticalSection
0x1800b0e0b  call    cs:__imp_EnterCriticalSection
0x1800b0e11  mov     [rsp+78h+lpString1], 0
0x1800b0e1a  mov     [rsp+78h+var_40], 0
0x1800b0e23  mov     [rsp+78h+var_38], 0
0x1800b0e2c  cmp     qword ptr [rbx+70h], 0
0x1800b0e31  jz      loc_1800B0EDE
0x1800b0e37  lea     rcx, [rsp+78h+lpString1]
0x1800b0e3c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b0e41  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800b0e45  mov     [rsp+78h+var_40], r14
0x1800b0e4a  mov     [rsp+78h+var_38], r14
0x1800b0e4f  lea     rdx, [rsp+78h+lpString1]
0x1800b0e54  lea     rcx, [rdi+1Ch]
0x1800b0e58  call    GetAepIDFromDeviceInterfaceID
0x1800b0e5d  test    eax, eax
0x1800b0e5f  js      short loc_1800B0EDE
0x1800b0e61  mov     [rsp+78h+bIgnoreCase], 0; bIgnoreCase
0x1800b0e69  mov     r9d, r14d; cchCount2
0x1800b0e6c  mov     r8, [rbx+70h]; lpString2
0x1800b0e70  mov     edx, r14d; cchCount1
0x1800b0e73  mov     rcx, [rsp+78h+lpString1]; lpString1
0x1800b0e78  call    cs:__imp_CompareStringOrdinal
0x1800b0e7e  cmp     eax, 2
0x1800b0e81  jnz     short loc_1800B0EDE
0x1800b0e83  lea     r8, [rdi+1Ch]
0x1800b0e87  lea     rdx, aChidpairingHan_6; "CHidPairing::_HandleDeviceNotification "...
0x1800b0e8e  xor     ecx, ecx
0x1800b0e90  call    UnattendLogW
0x1800b0e95  lea     r9d, [r14+3]; lParam
0x1800b0e99  lea     r8d, [r14+7]; wParam
0x1800b0e9d  mov     edx, [rbx+118h]; Msg
0x1800b0ea3  mov     rcx, [rbx+40h]; hWnd
0x1800b0ea7  call    cs:__imp_PostMessageW
0x1800b0ead  test    eax, eax
0x1800b0eaf  jnz     short loc_1800B0ECB
0x1800b0eb1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b0eb6  mov     r8d, eax
0x1800b0eb9  lea     rdx, aChidpairingHan_4; "CHidPairing::_HandleDeviceNotification "...
0x1800b0ec0  lea     ecx, [r14+2]
0x1800b0ec4  call    UnattendLogW
0x1800b0ec9  jmp     short loc_1800B0EDE
0x1800b0ecb  mov     byte ptr [rbx+58h], 1
0x1800b0ecf  mov     edx, 3E9h; uIDEvent
0x1800b0ed4  mov     rcx, [rbx+48h]; hWnd
0x1800b0ed8  call    cs:__imp_KillTimer
0x1800b0ede  mov     rcx, rsi; lpCriticalSection
0x1800b0ee1  call    cs:__imp_LeaveCriticalSection
0x1800b0ee7  nop
0x1800b0ee8  lea     rcx, [rsp+78h+lpString1]
0x1800b0eed  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b0ef2  jmp     loc_1800B103C
0x1800b0ef7  mov     rax, [r9+0Ch]
0x1800b0efb  sub     rax, qword ptr cs:GUID_DEVINTERFACE_KEYBOARD.Data1
0x1800b0f02  jnz     short loc_1800B0F0F
0x1800b0f04  mov     rax, [r9+14h]
0x1800b0f08  sub     rax, qword ptr cs:GUID_DEVINTERFACE_KEYBOARD.Data4
0x1800b0f0f  test    rax, rax
0x1800b0f12  jnz     loc_1800B103C
0x1800b0f18  lea     r8, [r9+1Ch]
0x1800b0f1c  lea     rdx, aChidpairingHan_5; "CHidPairing::_HandleDeviceNotification "...
0x1800b0f23  xor     ecx, ecx
0x1800b0f25  call    UnattendLogW
0x1800b0f2a  mov     r9d, 1; lParam
0x1800b0f30  lea     r8d, [r9+5]; wParam
0x1800b0f34  mov     edx, [rbx+118h]; Msg
0x1800b0f3a  mov     rcx, [rbx+40h]; hWnd
0x1800b0f3e  call    cs:__imp_PostMessageW
0x1800b0f44  test    eax, eax
0x1800b0f46  jnz     short loc_1800B0FB5
0x1800b0f48  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b0f4d  lea     rdx, aChidpairingHan_0; "CHidPairing::_HandleDeviceNotification "...
0x1800b0f54  jmp     loc_1800B102F
0x1800b0f59  mov     rax, [r9+0Ch]
0x1800b0f5d  sub     rax, qword ptr cs:GUID_DEVINTERFACE_MOUSE.Data1
0x1800b0f64  jnz     short loc_1800B0F71
0x1800b0f66  mov     rax, [r9+14h]
0x1800b0f6a  sub     rax, qword ptr cs:GUID_DEVINTERFACE_MOUSE.Data4
0x1800b0f71  test    rax, rax
0x1800b0f74  jnz     loc_1800B103C
0x1800b0f7a  lea     r8, [r9+1Ch]
0x1800b0f7e  lea     rdx, aChidpairingHan_3; "CHidPairing::_HandleDeviceNotification "...
0x1800b0f85  xor     ecx, ecx
0x1800b0f87  call    UnattendLogW
0x1800b0f8c  xor     r9d, r9d; lParam
0x1800b0f8f  lea     r8d, [r9+6]; wParam
0x1800b0f93  mov     edx, [rbx+118h]; Msg
0x1800b0f99  mov     rcx, [rbx+40h]; hWnd
0x1800b0f9d  call    cs:__imp_PostMessageW
0x1800b0fa3  test    eax, eax
0x1800b0fa5  jnz     short loc_1800B0FB5
0x1800b0fa7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b0fac  lea     rdx, aChidpairingHan_1; "CHidPairing::_HandleDeviceNotification "...
0x1800b0fb3  jmp     short loc_1800B102F
0x1800b0fb5  mov     byte ptr [rbx+58h], 1
0x1800b0fb9  mov     edx, 3E9h; uIDEvent
0x1800b0fbe  mov     rcx, [rbx+48h]; hWnd
0x1800b0fc2  call    cs:__imp_KillTimer
0x1800b0fc8  jmp     short loc_1800B103C
0x1800b0fca  cmp     r8, 8006h
0x1800b0fd1  jnz     short loc_1800B103C
0x1800b0fd3  mov     rax, [r9+20h]
0x1800b0fd7  sub     rax, qword ptr cs:GUID_BLUETOOTH_KEYPRESS_EVENT.Data1
0x1800b0fde  jnz     short loc_1800B0FEB
0x1800b0fe0  mov     rax, [r9+28h]
0x1800b0fe4  sub     rax, qword ptr cs:GUID_BLUETOOTH_KEYPRESS_EVENT.Data4
0x1800b0feb  test    rax, rax
0x1800b0fee  jnz     short loc_1800B103C
0x1800b0ff0  add     rdi, 34h ; '4'
0x1800b0ff4  jz      short loc_1800B103C
0x1800b0ff6  lea     rdx, aChidpairingHan_2; "CHidPairing::_HandleDeviceNotification "...
0x1800b0ffd  xor     ecx, ecx
0x1800b0fff  call    UnattendLogW
0x1800b1004  movzx   r9d, byte ptr [rdi+8]; lParam
0x1800b1009  mov     r8d, 3; wParam
0x1800b100f  mov     edx, [rbx+118h]; Msg
0x1800b1015  mov     rcx, [rbx+40h]; hWnd
0x1800b1019  call    cs:__imp_PostMessageW
0x1800b101f  test    eax, eax
0x1800b1021  jnz     short loc_1800B103C
0x1800b1023  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b1028  lea     rdx, aChidpairingHan; "CHidPairing::_HandleDeviceNotification "...
0x1800b102f  mov     r8d, eax
0x1800b1032  mov     ecx, 1
0x1800b1037  call    UnattendLogW
0x1800b103c  xor     eax, eax
0x1800b103e  add     rsp, 58h
0x1800b1042  pop     r14
0x1800b1044  pop     rdi
0x1800b1045  pop     rsi
0x1800b1046  pop     rbx
0x1800b1047  retn
```
