# LoadTrackingOptions

- ea: `0x1800155f8`
- end: `0x18001579d`
- name: `LoadTrackingOptions`
- size: `421`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd8c`

## callees

- `0x180005eac`
- `0x1800071e8`
- `0x18000d7e4`
- `0x18000d94c`
- `0x1800155f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001574e`
- `ADVAPI32!RegCloseKey` at `0x18001574e`

## string_xrefs

- `0x1800156ba`: `NotifyIncomingCompletion`
- `0x1800156cd`: `NotifyOutgoingCompletion`

## pseudocode

```c
__int64 __fastcall LoadTrackingOptions(LPBYTE lpData)
{
  _BOOL8 v3; // rcx
  __int64 v4; // rdx
  HKEY v5; // rax
  HKEY v6; // rdi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids);
  }
  if ( !lpData )
    return 87;
  v3 = (unsigned int)IsServerSku() == 0;
  *((_DWORD *)lpData + 1) = v3;
  *((_DWORD *)lpData + 2) = v3;
  *((_DWORD *)lpData + 3) = v3;
  *((_DWORD *)lpData + 4) = v3;
  *((_DWORD *)lpData + 5) = v3;
  *((_DWORD *)lpData + 6) = v3;
  *((_DWORD *)lpData + 8) = v3;
  *((_DWORD *)lpData + 7) = v3;
  *((_DWORD *)lpData + 9) = v3;
  v5 = OpenRegistryKey(v3, v4, 0, 0x20019u);
  v6 = v5;
  if ( v5 )
  {
    GetRegistryDwordEx(v5, L"DeviceToMonitor", lpData);
    GetRegistryDwordEx(v6, L"NotifyProgress", lpData + 4);
    GetRegistryDwordEx(v6, L"NotifyIncomingCompletion", lpData + 8);
    GetRegistryDwordEx(v6, L"NotifyOutgoingCompletion", lpData + 12);
    GetRegistryDwordEx(v6, L"MonitorOnSend", lpData + 16);
    GetRegistryDwordEx(v6, L"MonitorOnReceive", lpData + 20);
    GetRegistryDwordEx(v6, L"SoundOnRing", lpData + 24);
    GetRegistryDwordEx(v6, L"SoundOnReceive", lpData + 28);
    GetRegistryDwordEx(v6, L"SoundOnSent", lpData + 32);
    GetRegistryDwordEx(v6, L"SoundOnError", lpData + 36);
    RegCloseKey(v6);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1800155f8  push    rbx
0x1800155fa  push    rbp
0x1800155fb  push    rsi
0x1800155fc  push    rdi
0x1800155fd  push    r12
0x1800155ff  push    r13
0x180015601  push    r14
0x180015603  push    r15
0x180015605  sub     rsp, 28h
0x180015609  mov     rbx, rcx
0x18001560c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015613  lea     rax, WPP_GLOBAL_Control
0x18001561a  cmp     rcx, rax
0x18001561d  jz      short loc_180015640
0x18001561f  test    byte ptr [rcx+1Ch], 2
0x180015623  jz      short loc_180015640
0x180015625  cmp     byte ptr [rcx+19h], 5
0x180015629  jb      short loc_180015640
0x18001562b  mov     rcx, [rcx+10h]
0x18001562f  lea     r8, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids
0x180015636  mov     edx, 17h
0x18001563b  call    WPP_SF_
0x180015640  test    rbx, rbx
0x180015643  jnz     short loc_18001564D
0x180015645  lea     eax, [rbx+57h]
0x180015648  jmp     loc_18001578C
0x18001564d  call    IsServerSku
0x180015652  xor     ecx, ecx
0x180015654  mov     r9d, 20019h
0x18001565a  test    eax, eax
0x18001565c  setz    cl
0x18001565f  xor     r8d, r8d
0x180015662  mov     [rbx+4], ecx
0x180015665  mov     [rbx+8], ecx
0x180015668  mov     [rbx+0Ch], ecx
0x18001566b  mov     [rbx+10h], ecx
0x18001566e  mov     [rbx+14h], ecx
0x180015671  mov     [rbx+18h], ecx
0x180015674  mov     [rbx+20h], ecx
0x180015677  mov     [rbx+1Ch], ecx
0x18001567a  mov     [rbx+24h], ecx
0x18001567d  call    OpenRegistryKey
0x180015682  mov     rdi, rax
0x180015685  test    rax, rax
0x180015688  jz      loc_180015756
0x18001568e  mov     r8, rbx; lpData
0x180015691  lea     rdx, aDevicetomonito; "DeviceToMonitor"
0x180015698  mov     rcx, rax; hKey
0x18001569b  call    GetRegistryDwordEx
0x1800156a0  lea     r8, [rbx+4]; lpData
0x1800156a4  mov     rcx, rdi; hKey
0x1800156a7  lea     rdx, aNotifyprogress; "NotifyProgress"
0x1800156ae  call    GetRegistryDwordEx
0x1800156b3  lea     r8, [rbx+8]; lpData
0x1800156b7  mov     rcx, rdi; hKey
0x1800156ba  lea     rdx, aNotifyincoming; "NotifyIncomingCompletion"
0x1800156c1  call    GetRegistryDwordEx
0x1800156c6  lea     r8, [rbx+0Ch]; lpData
0x1800156ca  mov     rcx, rdi; hKey
0x1800156cd  lea     rdx, aNotifyoutgoing; "NotifyOutgoingCompletion"
0x1800156d4  call    GetRegistryDwordEx
0x1800156d9  lea     r8, [rbx+10h]; lpData
0x1800156dd  mov     rcx, rdi; hKey
0x1800156e0  lea     rdx, aMonitoronsend; "MonitorOnSend"
0x1800156e7  call    GetRegistryDwordEx
0x1800156ec  lea     r8, [rbx+14h]; lpData
0x1800156f0  mov     rcx, rdi; hKey
0x1800156f3  lea     rdx, aMonitoronrecei; "MonitorOnReceive"
0x1800156fa  call    GetRegistryDwordEx
0x1800156ff  lea     r8, [rbx+18h]; lpData
0x180015703  mov     rcx, rdi; hKey
0x180015706  lea     rdx, aSoundonring; "SoundOnRing"
0x18001570d  call    GetRegistryDwordEx
0x180015712  lea     r8, [rbx+1Ch]; lpData
0x180015716  mov     rcx, rdi; hKey
0x180015719  lea     rdx, aSoundonreceive; "SoundOnReceive"
0x180015720  call    GetRegistryDwordEx
0x180015725  lea     r8, [rbx+20h]; lpData
0x180015729  mov     rcx, rdi; hKey
0x18001572c  lea     rdx, aSoundonsent; "SoundOnSent"
0x180015733  call    GetRegistryDwordEx
0x180015738  lea     r8, [rbx+24h]; lpData
0x18001573c  mov     rcx, rdi; hKey
0x18001573f  lea     rdx, aSoundonerror; "SoundOnError"
0x180015746  call    GetRegistryDwordEx
0x18001574b  mov     rcx, rdi; hKey
0x18001574e  call    cs:__imp_RegCloseKey
0x180015754  jmp     short loc_18001578A
0x180015756  mov     rcx, cs:WPP_GLOBAL_Control
0x18001575d  lea     rax, WPP_GLOBAL_Control
0x180015764  cmp     rcx, rax
0x180015767  jz      short loc_18001578A
0x180015769  test    byte ptr [rcx+1Ch], 2
0x18001576d  jz      short loc_18001578A
0x18001576f  cmp     byte ptr [rcx+19h], 3
0x180015773  jb      short loc_18001578A
0x180015775  mov     rcx, [rcx+10h]
0x180015779  lea     r8, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids
0x180015780  mov     edx, 18h
0x180015785  call    WPP_SF_
0x18001578a  xor     eax, eax
0x18001578c  add     rsp, 28h
0x180015790  pop     r15
0x180015792  pop     r14
0x180015794  pop     r13
0x180015796  pop     r12
0x180015798  pop     rdi
0x180015799  pop     rsi
0x18001579a  pop     rbp
0x18001579b  pop     rbx
0x18001579c  retn
```
