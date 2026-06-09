# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessAdvertisementEvent(_BTH_HCI_LE_ADVERTISEMENT_DATA const *)

- ea: `0x18002b8ac`
- end: `0x18002ba62`
- name: `?ProcessAdvertisementEvent@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJPEBU_BTH_HCI_LE_ADVERTISEMENT_DATA@@@Z`
- size: `438`
- prototype: `int(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this, const struct _BTH_HCI_LE_ADVERTISEMENT_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c884`

## callees

- `0x180012004`
- `0x180012384`
- `0x18002b8ac`
- `0x18002ba68`
- `0x18002c9b8`
- `0x18002d928`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b93a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b93a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b9a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b9a5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessAdvertisementEvent(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this,
        const struct _BTH_HCI_LE_ADVERTISEMENT_DATA *a2)
{
  const struct _BTH_HCI_LE_ADVERTISEMENT_DATA *v2; // r14
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
      v11 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromAdvertisement(
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
0x18002b8ac  mov     [rsp+arg_0], rbx
0x18002b8b1  mov     [rsp+arg_8], rbp
0x18002b8b6  mov     [rsp+arg_10], rsi
0x18002b8bb  push    rdi
0x18002b8bc  push    r12
0x18002b8be  push    r13
0x18002b8c0  push    r14
0x18002b8c2  push    r15
0x18002b8c4  sub     rsp, 60h
0x18002b8c8  mov     r14, rdx
0x18002b8cb  mov     rsi, rcx
0x18002b8ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8d5  lea     r15, WPP_GLOBAL_Control
0x18002b8dc  mov     dil, 1
0x18002b8df  cmp     rcx, r15
0x18002b8e2  jz      short loc_18002B8EF
0x18002b8e4  cmp     byte ptr [rcx+19h], 5
0x18002b8e8  jb      short loc_18002B8EF
0x18002b8ea  mov     dl, dil
0x18002b8ed  jmp     short loc_18002B8F1
0x18002b8ef  xor     dl, dl
0x18002b8f1  lea     r12, WPP_RECORDER_INITIALIZED
0x18002b8f8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002b8ff  lea     r13, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002b906  setnz   r8b
0x18002b90a  test    dl, dl
0x18002b90c  jnz     short loc_18002B913
0x18002b90e  test    r8b, r8b
0x18002b911  jz      short loc_18002B931
0x18002b913  mov     r9, [rcx+28h]
0x18002b917  mov     rcx, [rcx+10h]
0x18002b91b  mov     [rsp+88h+var_40], rsi
0x18002b920  mov     [rsp+88h+var_50], r13
0x18002b925  mov     [rsp+88h+var_58], 1Dh
0x18002b92c  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002b931  lea     rbp, [rsi+30h]
0x18002b935  xor     ebx, ebx
0x18002b937  mov     rcx, rbp; lpCriticalSection
0x18002b93a  call    cs:__imp_EnterCriticalSection
0x18002b941  nop     dword ptr [rax+rax+00h]
0x18002b946  cmp     [rsi+8], ebx
0x18002b949  jnz     short loc_18002B996
0x18002b94b  mov     ebx, 8000000Eh
0x18002b950  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b957  cmp     rcx, r15
0x18002b95a  jz      short loc_18002B967
0x18002b95c  cmp     byte ptr [rcx+19h], 2
0x18002b960  jb      short loc_18002B967
0x18002b962  mov     dl, dil
0x18002b965  jmp     short loc_18002B969
0x18002b967  xor     dl, dl
0x18002b969  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002b970  setnz   r8b
0x18002b974  test    dl, dl
0x18002b976  jnz     short loc_18002B97D
0x18002b978  test    r8b, r8b
0x18002b97b  jz      short loc_18002B99D
0x18002b97d  mov     r9, [rcx+28h]
0x18002b981  mov     rcx, [rcx+10h]
0x18002b985  mov     [rsp+88h+var_50], r13
0x18002b98a  mov     [rsp+88h+var_58], 1Eh
0x18002b991  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002b996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b99d  test    rbp, rbp
0x18002b9a0  jz      short loc_18002B9B8
0x18002b9a2  mov     rcx, rbp; lpCriticalSection
0x18002b9a5  call    cs:__imp_LeaveCriticalSection
0x18002b9ac  nop     dword ptr [rax+rax+00h]
0x18002b9b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9b8  test    ebx, ebx
0x18002b9ba  js      short loc_18002B9E8
0x18002b9bc  cmp     qword ptr [rsi+28h], 0
0x18002b9c1  jz      short loc_18002B9E6
0x18002b9c3  mov     rcx, [rsi+28h]; this
0x18002b9c7  mov     rdx, r14; struct _BTH_HCI_LE_ADVERTISEMENT_DATA *
0x18002b9ca  call    ?ShouldPairDeviceFromAdvertisement@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_HCI_LE_ADVERTISEMENT_DATA@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromAdvertisement(_BTH_HCI_LE_ADVERTISEMENT_DATA const *)
0x18002b9cf  test    rax, rax
0x18002b9d2  jz      short loc_18002B9DF
0x18002b9d4  mov     rdx, rax; struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *
0x18002b9d7  mov     rcx, rsi; this
0x18002b9da  call    ?ProcessDeviceMatch@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJPEAVBthLEPrepairingDevice@2345@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)
0x18002b9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9e6  test    ebx, ebx
0x18002b9e8  jnz     short loc_18002B9F2
0x18002b9ea  xor     eax, eax
0x18002b9ec  cmp     byte ptr [rcx+19h], 5
0x18002b9f0  jmp     short loc_18002B9F8
0x18002b9f2  xor     eax, eax
0x18002b9f4  cmp     byte ptr [rcx+19h], 2
0x18002b9f8  setnb   al
0x18002b9fb  cmp     rcx, r15
0x18002b9fe  jz      short loc_18002BA04
0x18002ba00  test    eax, eax
0x18002ba02  jnz     short loc_18002BA07
0x18002ba04  xor     dil, dil
0x18002ba07  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002ba0e  setnz   r8b
0x18002ba12  test    dil, dil
0x18002ba15  jnz     short loc_18002BA1C
0x18002ba17  test    r8b, r8b
0x18002ba1a  jz      short loc_18002BA41
0x18002ba1c  mov     r9, [rcx+28h]
0x18002ba20  mov     dl, dil
0x18002ba23  mov     rcx, [rcx+10h]
0x18002ba27  mov     [rsp+88h+var_38], ebx
0x18002ba2b  mov     [rsp+88h+var_40], rsi
0x18002ba30  mov     [rsp+88h+var_50], r13
0x18002ba35  mov     [rsp+88h+var_58], 1Fh
0x18002ba3c  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002ba41  lea     r11, [rsp+88h+var_28]
0x18002ba46  mov     eax, ebx
0x18002ba48  mov     rbx, [r11+30h]
0x18002ba4c  mov     rbp, [r11+38h]
0x18002ba50  mov     rsi, [r11+40h]
0x18002ba54  mov     rsp, r11
0x18002ba57  pop     r15
0x18002ba59  pop     r14
0x18002ba5b  pop     r13
0x18002ba5d  pop     r12
0x18002ba5f  pop     rdi
0x18002ba60  retn
```
