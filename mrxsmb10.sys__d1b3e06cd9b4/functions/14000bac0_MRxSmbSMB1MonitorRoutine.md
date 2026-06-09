# MRxSmbSMB1MonitorRoutine

- ea: `0x14000bac0`
- end: `0x14000bd09`
- name: `MRxSmbSMB1MonitorRoutine`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000bac0`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000fa8c`
- `0x140031a18`
- `0x140032d5c`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x14000bca4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14000bca4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb2d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bad8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bad8`

## pseudocode

```c
__int64 MRxSmbSMB1MonitorRoutine()
{
  char v0; // bl
  KIRQL v1; // al
  __int64 *v2; // rcx
  __int64 *v3; // rdx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  unsigned int v7; // esi
  NTSTATUS updated; // eax
  int v9; // eax
  __int64 v10; // rcx

  v0 = 1;
  v1 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v2 = (__int64 *)s_DbServers;
  s_SmbCeDbSpinLockSavedIrql = v1;
  while ( 1 )
  {
    v3 = 0;
    if ( v2 != &s_DbServers )
      v3 = v2 - 4;
    if ( !v3 )
      break;
    if ( v3[96] != 0xFFFFFFFFLL )
    {
      v0 = 0;
      break;
    }
    v2 = (__int64 *)v3[4];
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( v0 )
  {
    if ( _InterlockedExchange(&MRxSmb1ObservedInthisPeriod, 0) )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
      {
        v5 = 24;
        goto LABEL_16;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids);
      }
      if ( (Microsoft_Windows_SMBClientEnableBits & 0x800) != 0 )
        McTemplateK0q_EtwWriteTransfer(v6, NoSMB1ObservedInLastPeriod);
      v7 = MRxSmbGetSMB1UnusedCounter() + 1;
      MRxSmb1UnusedCounter = v7;
      updated = MRxSmbUpdateSMB1UnusedCounter(v7);
      if ( updated < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids,
          (unsigned int)updated);
      }
      if ( v7 >= 72 * MRxSmbUninstallSMB1LBDays
        && v7 == 72 * (v7 / 0x48)
        && (*(_BYTE *)(RdrConfigurationBlock + 64) & 0x10) != 0
        && MRxSmbSMB1DeprecationEnabled )
      {
        v9 = ZwUpdateWnfStateData(&WNF_RDR_SMB1_NOT_IN_USE_STATE_CHANGE, 0, 0, 0, 0, 0, 0);
        if ( v9 >= 0 )
        {
          if ( (Microsoft_Windows_SMBClientEnableBits & 0x800000000LL) != 0 )
            McTemplateK0q_EtwWriteTransfer(v10, UninstallSMB1Client);
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids,
            (unsigned int)v9);
        }
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
    {
      v5 = 23;
LABEL_16:
      WPP_SF_(v4->AttachedDevice, v5, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000bac0  mov     [rsp+arg_0], rbx
0x14000bac5  mov     [rsp+arg_8], rsi
0x14000baca  push    rdi
0x14000bacb  sub     rsp, 40h
0x14000bacf  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000bad6  mov     bl, 1
0x14000bad8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000badf  nop     dword ptr [rax+rax+00h]
0x14000bae4  mov     rcx, cs:s_DbServers
0x14000baeb  lea     r8, s_DbServers
0x14000baf2  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000baf8  xor     edx, edx
0x14000bafa  lea     rax, [rcx-20h]
0x14000bafe  cmp     rcx, r8
0x14000bb01  cmovnz  rdx, rax
0x14000bb05  test    rdx, rdx
0x14000bb08  jz      short loc_14000BB20
0x14000bb0a  mov     eax, 0FFFFFFFFh
0x14000bb0f  cmp     [rdx+300h], rax
0x14000bb16  jnz     short loc_14000BB1E
0x14000bb18  mov     rcx, [rdx+20h]
0x14000bb1c  jmp     short loc_14000BAF8
0x14000bb1e  xor     bl, bl
0x14000bb20  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000bb26  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000bb2d  call    cs:__imp_KeReleaseSpinLock
0x14000bb34  nop     dword ptr [rax+rax+00h]
0x14000bb39  test    bl, bl
0x14000bb3b  jnz     short loc_14000BB66
0x14000bb3d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000bb44  lea     rdi, WPP_GLOBAL_Control
0x14000bb4b  cmp     rcx, rdi
0x14000bb4e  jz      loc_14000BCF6
0x14000bb54  bt      dword ptr [rcx+2Ch], 0Ah
0x14000bb59  jnb     loc_14000BCF6
0x14000bb5f  mov     edx, 17h
0x14000bb64  jmp     short loc_14000BB99
0x14000bb66  xor     eax, eax
0x14000bb68  xchg    eax, cs:MRxSmb1ObservedInthisPeriod
0x14000bb6e  test    eax, eax
0x14000bb70  jz      short loc_14000BBAE
0x14000bb72  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000bb79  lea     rdi, WPP_GLOBAL_Control
0x14000bb80  cmp     rcx, rdi
0x14000bb83  jz      loc_14000BCF6
0x14000bb89  bt      dword ptr [rcx+2Ch], 0Ah
0x14000bb8e  jnb     loc_14000BCF6
0x14000bb94  mov     edx, 18h
0x14000bb99  mov     rcx, [rcx+18h]
0x14000bb9d  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14000bba4  call    WPP_SF_
0x14000bba9  jmp     loc_14000BCF6
0x14000bbae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000bbb5  lea     rdi, WPP_GLOBAL_Control
0x14000bbbc  cmp     rcx, rdi
0x14000bbbf  jz      short loc_14000BBDD
0x14000bbc1  bt      dword ptr [rcx+2Ch], 0Ah
0x14000bbc6  jnb     short loc_14000BBDD
0x14000bbc8  mov     rcx, [rcx+18h]
0x14000bbcc  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14000bbd3  mov     edx, 19h
0x14000bbd8  call    WPP_SF_
0x14000bbdd  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits+1, 8
0x14000bbe4  jz      short loc_14000BBF2
0x14000bbe6  lea     rdx, NoSMB1ObservedInLastPeriod
0x14000bbed  call    McTemplateK0q_EtwWriteTransfer
0x14000bbf2  call    MRxSmbGetSMB1UnusedCounter
0x14000bbf7  lea     esi, [rax+1]
0x14000bbfa  mov     ecx, esi
0x14000bbfc  mov     cs:MRxSmb1UnusedCounter, esi
0x14000bc02  call    MRxSmbUpdateSMB1UnusedCounter
0x14000bc07  test    eax, eax
0x14000bc09  jns     short loc_14000BC36
0x14000bc0b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000bc12  cmp     rcx, rdi
0x14000bc15  jz      short loc_14000BC36
0x14000bc17  bt      dword ptr [rcx+2Ch], 0Ah
0x14000bc1c  jnb     short loc_14000BC36
0x14000bc1e  mov     rcx, [rcx+18h]
0x14000bc22  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14000bc29  mov     edx, 1Ah
0x14000bc2e  mov     r9d, eax
0x14000bc31  call    WPP_SF_d
0x14000bc36  mov     eax, cs:MRxSmbUninstallSMB1LBDays
0x14000bc3c  lea     ecx, [rax+rax*8]
0x14000bc3f  shl     ecx, 3
0x14000bc42  cmp     esi, ecx
0x14000bc44  jb      loc_14000BCF6
0x14000bc4a  mov     eax, 38E38E39h
0x14000bc4f  mul     esi
0x14000bc51  shr     edx, 4
0x14000bc54  lea     eax, [rdx+rdx*8]
0x14000bc57  shl     eax, 3
0x14000bc5a  cmp     esi, eax
0x14000bc5c  jnz     loc_14000BCF6
0x14000bc62  mov     rax, cs:RdrConfigurationBlock
0x14000bc69  test    byte ptr [rax+40h], 10h
0x14000bc6d  jz      loc_14000BCF6
0x14000bc73  cmp     cs:MRxSmbSMB1DeprecationEnabled, 0
0x14000bc7a  jz      short loc_14000BCF6
0x14000bc7c  mov     [rsp+48h+var_18], 0
0x14000bc84  lea     rcx, WNF_RDR_SMB1_NOT_IN_USE_STATE_CHANGE
0x14000bc8b  mov     [rsp+48h+var_20], 0
0x14000bc93  xor     r9d, r9d
0x14000bc96  xor     r8d, r8d
0x14000bc99  mov     [rsp+48h+var_28], 0
0x14000bca2  xor     edx, edx
0x14000bca4  call    cs:__imp_ZwUpdateWnfStateData
0x14000bcab  nop     dword ptr [rax+rax+00h]
0x14000bcb0  test    eax, eax
0x14000bcb2  jns     short loc_14000BCE1
0x14000bcb4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000bcbb  cmp     rcx, rdi
0x14000bcbe  jz      short loc_14000BCF6
0x14000bcc0  bt      dword ptr [rcx+2Ch], 0Ah
0x14000bcc5  jnb     short loc_14000BCF6
0x14000bcc7  mov     rcx, [rcx+18h]
0x14000bccb  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14000bcd2  mov     edx, 1Bh
0x14000bcd7  mov     r9d, eax
0x14000bcda  call    WPP_SF_d
0x14000bcdf  jmp     short loc_14000BCF6
0x14000bce1  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits+4, 8
0x14000bce8  jz      short loc_14000BCF6
0x14000bcea  lea     rdx, UninstallSMB1Client
0x14000bcf1  call    McTemplateK0q_EtwWriteTransfer
0x14000bcf6  mov     rbx, [rsp+48h+arg_0]
0x14000bcfb  xor     eax, eax
0x14000bcfd  mov     rsi, [rsp+48h+arg_8]
0x14000bd02  add     rsp, 40h
0x14000bd06  pop     rdi
0x14000bd07  retn
```
