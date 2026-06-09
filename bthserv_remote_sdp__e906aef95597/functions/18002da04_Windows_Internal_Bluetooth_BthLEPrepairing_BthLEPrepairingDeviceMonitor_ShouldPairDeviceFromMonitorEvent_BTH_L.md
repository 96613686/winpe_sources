# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)

- ea: `0x18002da04`
- end: `0x18002dcaa`
- name: `?ShouldPairDeviceFromMonitorEvent@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z`
- size: `678`
- prototype: `struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *__hidden this, const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002bd38`

## callees

- `0x180001b94`
- `0x1800114bc`
- `0x1800120b8`
- `0x180012384`
- `0x18002cf20`
- `0x18002d564`
- `0x18002d78c`
- `0x18002da04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002da27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002da27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dc83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dc83`

## pseudocode

```c
struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::ShouldPairDeviceFromMonitorEvent(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *this,
        const struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *DeviceFromMonitorEvent; // rax
  int v5; // r8d
  struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *v6; // r15
  unsigned __int64 v7; // r11
  __int64 v8; // rdx
  __int64 v9; // r8
  char v10; // di
  int v11; // edx
  int v12; // r8d
  char *v14; // r13
  int v15; // edx
  __int64 *v16; // rcx
  __int64 *v17; // rbx
  __int64 *v18; // rax
  __int64 *j; // r8
  __int64 *v20; // rdx
  __int64 *i; // rax
  void *v22; // rax
  _QWORD v23[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v24; // [rsp+B0h] [rbp+8h] BYREF
  struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *v25; // [rsp+B8h] [rbp+10h] BYREF

  v25 = a2;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DeviceFromMonitorEvent = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::GetDeviceFromMonitorEvent(
                             this,
                             v25);
  v6 = DeviceFromMonitorEvent;
  if ( DeviceFromMonitorEvent )
  {
    v7 = *((_QWORD *)DeviceFromMonitorEvent + 6);
    if ( *((_BYTE *)v25 + 9) )
    {
      v24 = *((_QWORD *)DeviceFromMonitorEvent + 6);
      if ( !Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::IsDeviceInRangeLocked(
              this,
              &v24) )
      {
        v10 = 1;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (LOBYTE(v8) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
        {
          LOBYTE(v8) = 0;
        }
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, *((_QWORD *)WPP_GLOBAL_Control + 5));
        v23[1] = this;
        v23[0] = &v25;
        if ( (int)wil::ResultFromException__lambda_b99a1f79a85fe3d31a3fa687ff12843c___(v23, v8, v9) < 0 )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            v10 = 0;
          if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = v10;
            LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v11,
              v12,
              *((_QWORD *)WPP_GLOBAL_Control + 5));
          }
        }
      }
      if ( v2 )
        LeaveCriticalSection(v2);
      return v6;
    }
    v14 = (char *)this + 56;
    v15 = 0;
    v16 = (__int64 *)*((_QWORD *)this + 7);
    v17 = v16;
    v18 = (__int64 *)v16[1];
    while ( !*((_BYTE *)v18 + 25) )
    {
      if ( v18[4] >= v7 )
      {
        v17 = v18;
        v18 = (__int64 *)*v18;
      }
      else
      {
        v18 = (__int64 *)v18[2];
      }
    }
    if ( !*((_BYTE *)v17 + 25) && v7 >= v17[4] && v17 != v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        LOBYTE(v15) = 1;
      if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v5, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      operator delete((void *)v17[5], (const struct std::nothrow_t *)1);
      j = (__int64 *)v17[2];
      v20 = v17;
      if ( *((_BYTE *)j + 25) )
      {
        for ( i = (__int64 *)v17[1]; !*((_BYTE *)i + 25) && v17 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v17 = i;
      }
      else
      {
        for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          ;
      }
      v22 = (void *)std::_Tree_val<std::_Tree_simple_types<Microsoft::Bluetooth::Foundation::AsyncObjectBase *>>::_Extract(
                      v14,
                      v20,
                      j);
      operator delete(v22, (const struct std::nothrow_t *)0x30);
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x18002da04  mov     [rsp+arg_10], rbx
0x18002da09  mov     [rsp+arg_8], rdx
0x18002da0e  push    rbp
0x18002da0f  push    rsi
0x18002da10  push    rdi
0x18002da11  push    r12
0x18002da13  push    r13
0x18002da15  push    r14
0x18002da17  push    r15
0x18002da19  sub     rsp, 70h
0x18002da1d  lea     rbp, [rcx+10h]
0x18002da21  mov     rbx, rcx
0x18002da24  mov     rcx, rbp; lpCriticalSection
0x18002da27  call    cs:__imp_EnterCriticalSection
0x18002da2e  nop     dword ptr [rax+rax+00h]
0x18002da33  mov     rdx, [rsp+0A8h+arg_8]; struct _BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT *
0x18002da3b  mov     rcx, rbx; this
0x18002da3e  call    ?GetDeviceFromMonitorEvent@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@IEAAPEAVBthLEPrepairingDevice@2345@PEBU_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::GetDeviceFromMonitorEvent(_BTH_LE_CONTROLLER_DEVICE_MONITOR_EVENT const *)
0x18002da43  xor     r14d, r14d
0x18002da46  mov     r15, rax
0x18002da49  test    rax, rax
0x18002da4c  jz      loc_18002DC7B
0x18002da52  mov     rcx, [rsp+0A8h+arg_8]
0x18002da5a  mov     r11, [rax+30h]
0x18002da5e  cmp     [rcx+9], r14b
0x18002da62  jz      loc_18002DB71
0x18002da68  lea     rdx, [rsp+0A8h+arg_0]; unsigned __int64 *
0x18002da70  mov     [rsp+0A8h+arg_0], r11
0x18002da78  mov     rcx, rbx; this
0x18002da7b  call    ?IsDeviceInRangeLocked@BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@IEAA_NAEB_K@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::IsDeviceInRangeLocked(unsigned __int64 const &)
0x18002da80  test    al, al
0x18002da82  jnz     loc_18002DB55
0x18002da88  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da8f  lea     rsi, WPP_GLOBAL_Control
0x18002da96  lea     edi, [r14+1]
0x18002da9a  cmp     rcx, rsi
0x18002da9d  jz      short loc_18002DAA8
0x18002da9f  cmp     byte ptr [rcx+19h], 4
0x18002daa3  mov     dl, dil
0x18002daa6  jnb     short loc_18002DAAB
0x18002daa8  mov     dl, r14b
0x18002daab  lea     r14, WPP_RECORDER_INITIALIZED
0x18002dab2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002dab9  lea     r12, WPP_b1c3b0ca35523905939af17a791078e1_Traceguids
0x18002dac0  setnz   r8b
0x18002dac4  test    dl, dl
0x18002dac6  jnz     short loc_18002DACD
0x18002dac8  test    r8b, r8b
0x18002dacb  jz      short loc_18002DAEB
0x18002dacd  mov     r9, [rcx+28h]
0x18002dad1  mov     rcx, [rcx+10h]
0x18002dad5  mov     [rsp+0A8h+var_60], r11
0x18002dada  mov     [rsp+0A8h+var_70], r12
0x18002dadf  mov     [rsp+0A8h+var_78], 0Dh
0x18002dae6  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002daeb  lea     rax, [rsp+0A8h+arg_8]
0x18002daf3  mov     [rsp+0A8h+var_50], rbx
0x18002daf8  lea     rcx, [rsp+0A8h+var_58]
0x18002dafd  mov     [rsp+0A8h+var_58], rax
0x18002db02  call    wil__ResultFromException__lambda_b99a1f79a85fe3d31a3fa687ff12843c___
0x18002db07  test    eax, eax
0x18002db09  jns     short loc_18002DB55
0x18002db0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db12  cmp     rcx, rsi
0x18002db15  jz      short loc_18002DB1D
0x18002db17  cmp     byte ptr [rcx+19h], 2
0x18002db1b  jnb     short loc_18002DB20
0x18002db1d  xor     dil, dil
0x18002db20  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002db27  setnz   r8b
0x18002db2b  test    dil, dil
0x18002db2e  jnz     short loc_18002DB35
0x18002db30  test    r8b, r8b
0x18002db33  jz      short loc_18002DB55
0x18002db35  mov     r9, [rcx+28h]
0x18002db39  mov     dl, dil
0x18002db3c  mov     rcx, [rcx+10h]
0x18002db40  mov     dword ptr [rsp+0A8h+var_60], eax
0x18002db44  mov     [rsp+0A8h+var_70], r12
0x18002db49  mov     [rsp+0A8h+var_78], 0Eh
0x18002db50  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002db55  test    rbp, rbp
0x18002db58  jz      short loc_18002DB69
0x18002db5a  mov     rcx, rbp; lpCriticalSection
0x18002db5d  call    cs:__imp_LeaveCriticalSection
0x18002db64  nop     dword ptr [rax+rax+00h]
0x18002db69  mov     rax, r15
0x18002db6c  jmp     loc_18002DC91
0x18002db71  lea     r13, [rbx+38h]
0x18002db75  xor     edx, edx
0x18002db77  mov     rcx, [r13+0]
0x18002db7b  mov     rbx, rcx
0x18002db7e  mov     rax, [rcx+8]
0x18002db82  jmp     short loc_18002DB96
0x18002db84  cmp     [rax+20h], r11
0x18002db88  jnb     short loc_18002DB90
0x18002db8a  mov     rax, [rax+10h]
0x18002db8e  jmp     short loc_18002DB96
0x18002db90  mov     rbx, rax
0x18002db93  mov     rax, [rax]
0x18002db96  cmp     [rax+19h], r14b
0x18002db9a  jz      short loc_18002DB84
0x18002db9c  cmp     [rbx+19h], r14b
0x18002dba0  jnz     loc_18002DC7B
0x18002dba6  cmp     r11, [rbx+20h]
0x18002dbaa  jb      loc_18002DC7B
0x18002dbb0  cmp     rbx, rcx
0x18002dbb3  jz      loc_18002DC7B
0x18002dbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbc0  lea     rsi, WPP_GLOBAL_Control
0x18002dbc7  mov     edi, 1
0x18002dbcc  cmp     rcx, rsi
0x18002dbcf  jz      short loc_18002DBDA
0x18002dbd1  cmp     byte ptr [rcx+19h], 4
0x18002dbd5  jb      short loc_18002DBDA
0x18002dbd7  mov     dl, dil
0x18002dbda  lea     r14, WPP_RECORDER_INITIALIZED
0x18002dbe1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002dbe8  setnz   r8b
0x18002dbec  xor     r14d, r14d
0x18002dbef  test    dl, dl
0x18002dbf1  jnz     short loc_18002DBF8
0x18002dbf3  test    r8b, r8b
0x18002dbf6  jz      short loc_18002DC1D
0x18002dbf8  mov     r9, [rcx+28h]
0x18002dbfc  lea     r12, WPP_b1c3b0ca35523905939af17a791078e1_Traceguids
0x18002dc03  mov     rcx, [rcx+10h]
0x18002dc07  mov     [rsp+0A8h+var_60], r11
0x18002dc0c  mov     [rsp+0A8h+var_70], r12
0x18002dc11  mov     [rsp+0A8h+var_78], 0Fh
0x18002dc18  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002dc1d  mov     rcx, [rbx+28h]; void *
0x18002dc21  mov     rdx, rdi; struct std::nothrow_t *
0x18002dc24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002dc29  mov     r8, [rbx+10h]
0x18002dc2d  mov     rdx, rbx
0x18002dc30  cmp     [r8+19h], r14b
0x18002dc34  jz      short loc_18002DC51
0x18002dc36  mov     rax, [rbx+8]
0x18002dc3a  jmp     short loc_18002DC49
0x18002dc3c  cmp     rbx, [rax+10h]
0x18002dc40  jnz     short loc_18002DC66
0x18002dc42  mov     rbx, rax
0x18002dc45  mov     rax, [rax+8]
0x18002dc49  cmp     [rax+19h], r14b
0x18002dc4d  jz      short loc_18002DC3C
0x18002dc4f  jmp     short loc_18002DC66
0x18002dc51  mov     r8, [r8]
0x18002dc54  cmp     [r8+19h], r14b
0x18002dc58  jnz     short loc_18002DC66
0x18002dc5a  mov     rax, [r8]
0x18002dc5d  mov     r8, rax
0x18002dc60  cmp     [rax+19h], r14b
0x18002dc64  jz      short loc_18002DC5A
0x18002dc66  mov     rcx, r13
0x18002dc69  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@PEAVAsyncObjectBase@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVAsyncObjectBase@Foundation@Bluetooth@Microsoft@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVAsyncObjectBase@Foundation@Bluetooth@Microsoft@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<Microsoft::Bluetooth::Foundation::AsyncObjectBase *>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<Microsoft::Bluetooth::Foundation::AsyncObjectBase *>>,std::_Iterator_base0>)
0x18002dc6e  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18002dc73  mov     rcx, rax; void *
0x18002dc76  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002dc7b  test    rbp, rbp
0x18002dc7e  jz      short loc_18002DC8F
0x18002dc80  mov     rcx, rbp; lpCriticalSection
0x18002dc83  call    cs:__imp_LeaveCriticalSection
0x18002dc8a  nop     dword ptr [rax+rax+00h]
0x18002dc8f  xor     eax, eax
0x18002dc91  mov     rbx, [rsp+0A8h+arg_10]
0x18002dc99  add     rsp, 70h
0x18002dc9d  pop     r15
0x18002dc9f  pop     r14
0x18002dca1  pop     r13
0x18002dca3  pop     r12
0x18002dca5  pop     rdi
0x18002dca6  pop     rsi
0x18002dca7  pop     rbp
0x18002dca8  retn
```
