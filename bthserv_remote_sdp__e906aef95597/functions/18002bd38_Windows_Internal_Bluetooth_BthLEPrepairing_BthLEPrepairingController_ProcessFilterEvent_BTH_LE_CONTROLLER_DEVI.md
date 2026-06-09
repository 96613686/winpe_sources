# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessFilterEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)

- ea: `0x18002bd38`
- end: `0x18002beee`
- name: `?ProcessFilterEvent@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJPEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this, const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c9cc`

## callees

- `0x180012004`
- `0x180012384`
- `0x18002ba68`
- `0x18002bd38`
- `0x18002c9b8`
- `0x18002da04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bdc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bdc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be31`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessFilterEvent(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this,
        const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *a2)
{
  const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *v2; // r14
  char v4; // di
  int v5; // ebx
  int v6; // edx
  int v7; // r8d
  _BYTE *v8; // rcx
  bool v9; // dl
  bool v10; // zf
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *v11; // rax
  int v12; // eax
  bool v13; // cf

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 2) )
    goto LABEL_16;
  v5 = -2147483634;
  v8 = WPP_GLOBAL_Control;
  v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_16:
    v8 = WPP_GLOBAL_Control;
  }
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v8 = WPP_GLOBAL_Control;
  }
  v10 = v5 == 0;
  if ( v5 >= 0 )
  {
    if ( *((_QWORD *)this + 5) )
    {
      v11 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(
              *((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor **)this + 5),
              v2);
      if ( v11 )
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(this, v11);
      v8 = WPP_GLOBAL_Control;
    }
    v10 = v5 == 0;
  }
  v12 = 0;
  if ( v10 )
    v13 = v8[25] < 5u;
  else
    v13 = v8[25] < 2u;
  if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v12) = !v13, !v12) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = v4;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v8 + 2), v6, v7, *((_QWORD *)v8 + 5));
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002bd38  mov     [rsp+arg_0], rbx
0x18002bd3d  mov     [rsp+arg_8], rbp
0x18002bd42  mov     [rsp+arg_10], rsi
0x18002bd47  push    rdi
0x18002bd48  push    r12
0x18002bd4a  push    r13
0x18002bd4c  push    r14
0x18002bd4e  push    r15
0x18002bd50  sub     rsp, 60h
0x18002bd54  mov     r14, rdx
0x18002bd57  mov     rsi, rcx
0x18002bd5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd61  lea     r15, WPP_GLOBAL_Control
0x18002bd68  mov     dil, 1
0x18002bd6b  cmp     rcx, r15
0x18002bd6e  jz      short loc_18002BD7B
0x18002bd70  cmp     byte ptr [rcx+19h], 5
0x18002bd74  jb      short loc_18002BD7B
0x18002bd76  mov     dl, dil
0x18002bd79  jmp     short loc_18002BD7D
0x18002bd7b  xor     dl, dl
0x18002bd7d  lea     r12, WPP_RECORDER_INITIALIZED
0x18002bd84  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002bd8b  lea     r13, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002bd92  setnz   r8b
0x18002bd96  test    dl, dl
0x18002bd98  jnz     short loc_18002BD9F
0x18002bd9a  test    r8b, r8b
0x18002bd9d  jz      short loc_18002BDBD
0x18002bd9f  mov     r9, [rcx+28h]
0x18002bda3  mov     rcx, [rcx+10h]
0x18002bda7  mov     [rsp+88h+var_40], rsi
0x18002bdac  mov     [rsp+88h+var_50], r13
0x18002bdb1  mov     [rsp+88h+var_58], 1Ah
0x18002bdb8  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002bdbd  lea     rbp, [rsi+30h]
0x18002bdc1  xor     ebx, ebx
0x18002bdc3  mov     rcx, rbp; lpCriticalSection
0x18002bdc6  call    cs:__imp_EnterCriticalSection
0x18002bdcd  nop     dword ptr [rax+rax+00h]
0x18002bdd2  cmp     [rsi+8], ebx
0x18002bdd5  jnz     short loc_18002BE22
0x18002bdd7  mov     ebx, 8000000Eh
0x18002bddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bde3  cmp     rcx, r15
0x18002bde6  jz      short loc_18002BDF3
0x18002bde8  cmp     byte ptr [rcx+19h], 2
0x18002bdec  jb      short loc_18002BDF3
0x18002bdee  mov     dl, dil
0x18002bdf1  jmp     short loc_18002BDF5
0x18002bdf3  xor     dl, dl
0x18002bdf5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002bdfc  setnz   r8b
0x18002be00  test    dl, dl
0x18002be02  jnz     short loc_18002BE09
0x18002be04  test    r8b, r8b
0x18002be07  jz      short loc_18002BE29
0x18002be09  mov     r9, [rcx+28h]
0x18002be0d  mov     rcx, [rcx+10h]
0x18002be11  mov     [rsp+88h+var_50], r13
0x18002be16  mov     [rsp+88h+var_58], 1Bh
0x18002be1d  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002be22  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be29  test    rbp, rbp
0x18002be2c  jz      short loc_18002BE44
0x18002be2e  mov     rcx, rbp; lpCriticalSection
0x18002be31  call    cs:__imp_LeaveCriticalSection
0x18002be38  nop     dword ptr [rax+rax+00h]
0x18002be3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be44  test    ebx, ebx
0x18002be46  js      short loc_18002BE74
0x18002be48  cmp     qword ptr [rsi+28h], 0
0x18002be4d  jz      short loc_18002BE72
0x18002be4f  mov     rcx, [rsi+28h]; this
0x18002be53  mov     rdx, r14; struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *
0x18002be56  call    ?ShouldPairDeviceFromMonitorEvent@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)
0x18002be5b  test    rax, rax
0x18002be5e  jz      short loc_18002BE6B
0x18002be60  mov     rdx, rax; struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *
0x18002be63  mov     rcx, rsi; this
0x18002be66  call    ?ProcessDeviceMatch@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJPEAVBthLEPrepairingDevice@2345@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)
0x18002be6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be72  test    ebx, ebx
0x18002be74  jnz     short loc_18002BE7E
0x18002be76  xor     eax, eax
0x18002be78  cmp     byte ptr [rcx+19h], 5
0x18002be7c  jmp     short loc_18002BE84
0x18002be7e  xor     eax, eax
0x18002be80  cmp     byte ptr [rcx+19h], 2
0x18002be84  setnb   al
0x18002be87  cmp     rcx, r15
0x18002be8a  jz      short loc_18002BE90
0x18002be8c  test    eax, eax
0x18002be8e  jnz     short loc_18002BE93
0x18002be90  xor     dil, dil
0x18002be93  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002be9a  setnz   r8b
0x18002be9e  test    dil, dil
0x18002bea1  jnz     short loc_18002BEA8
0x18002bea3  test    r8b, r8b
0x18002bea6  jz      short loc_18002BECD
0x18002bea8  mov     r9, [rcx+28h]
0x18002beac  mov     dl, dil
0x18002beaf  mov     rcx, [rcx+10h]
0x18002beb3  mov     [rsp+88h+var_38], ebx
0x18002beb7  mov     [rsp+88h+var_40], rsi
0x18002bebc  mov     [rsp+88h+var_50], r13
0x18002bec1  mov     [rsp+88h+var_58], 1Ch
0x18002bec8  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002becd  lea     r11, [rsp+88h+var_28]
0x18002bed2  mov     eax, ebx
0x18002bed4  mov     rbx, [r11+30h]
0x18002bed8  mov     rbp, [r11+38h]
0x18002bedc  mov     rsi, [r11+40h]
0x18002bee0  mov     rsp, r11
0x18002bee3  pop     r15
0x18002bee5  pop     r14
0x18002bee7  pop     r13
0x18002bee9  pop     r12
0x18002beeb  pop     rdi
0x18002beec  retn
```
