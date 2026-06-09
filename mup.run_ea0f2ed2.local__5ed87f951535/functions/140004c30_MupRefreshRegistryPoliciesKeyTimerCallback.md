# MupRefreshRegistryPoliciesKeyTimerCallback

- ea: `0x140004c30`
- end: `0x140004e52`
- name: `MupRefreshRegistryPoliciesKeyTimerCallback`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140004c30`
- `0x140016808`
- `0x140016bf0`
- `0x140016d74`
- `0x140016edc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140004c84`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004c84`
- `ntoskrnl!ZwClose` at `0x140004d2f`
- `ntoskrnl!ZwClose` at `0x140004e2c`
- `ntoskrnl!ZwClose` at `0x140004d2f`
- `ntoskrnl!ZwClose` at `0x140004e2c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004dff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004dff`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140004cb6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140004cb6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140004d77`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140004d77`
- `ntoskrnl!PsInitialSystemProcess` at `0x140004d85`
- `ntoskrnl!ObDuplicateObject` at `0x140004db4`
- `ntoskrnl!ObDuplicateObject` at `0x140004db4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140004df3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140004df3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004c96`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004c96`

## pseudocode

```c
void __fastcall MupRefreshRegistryPoliciesKeyTimerCallback(__int64 a1, struct _EX_RUNDOWN_REF *a2)
{
  HANDLE *v3; // rdi
  ULONG_PTR Count; // rdx
  int v5; // esi
  int v6; // eax
  HANDLE Handle; // [rsp+78h] [rbp+10h] BYREF

  Handle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Au) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_4108bb1397623747c94676978a28aeb5_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&a2[2], 0);
  v3 = (HANDLE *)&a2[3];
  Count = a2[3].Count;
  if ( Count )
  {
    v6 = ObDuplicateObject(PsInitialSystemProcess, Count, PsInitialSystemProcess, &Handle, 0, 512, 2, 0);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_4108bb1397623747c94676978a28aeb5_Traceguids,
        (unsigned int)v6);
    }
  }
  else if ( ExAcquireRundownProtection(a2 + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Au) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_4108bb1397623747c94676978a28aeb5_Traceguids);
    }
    if ( (int)MupiOpenPoliciesKeyFromRegistry((void **)&a2[3]) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Au) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_4108bb1397623747c94676978a28aeb5_Traceguids);
      }
      v5 = MupiRegisterPoliciesKeyRegistryChangeNotification(a2);
      if ( v5 < 0 )
      {
        ZwClose(*v3);
        *v3 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_4108bb1397623747c94676978a28aeb5_Traceguids,
            (unsigned int)v5);
        }
      }
    }
    MupiArmParametersKeyRefreshTimer(a2);
    ExReleaseRundownProtection(a2 + 1);
  }
  ExReleasePushLockSharedEx(&a2[2], 0);
  KeLeaveCriticalRegion();
  if ( Handle )
  {
    LOBYTE(MupEnableMailslotsByPolicy) = MupiReadEnableMailslotsFromPoliciesRegistry(Handle);
    if ( Handle )
      ZwClose(Handle);
  }
}

```

## disassembly

```asm
0x140004c30  mov     [rsp+arg_0], rbx
0x140004c35  mov     [rsp+arg_10], rbp
0x140004c3a  push    rsi
0x140004c3b  push    rdi
0x140004c3c  push    r12
0x140004c3e  push    r13
0x140004c40  push    r14
0x140004c42  sub     rsp, 40h
0x140004c46  mov     rbx, rdx
0x140004c49  mov     [rsp+68h+Handle], 0
0x140004c52  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c59  lea     r12, WPP_GLOBAL_Control
0x140004c60  lea     r13, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004c67  cmp     rcx, r12
0x140004c6a  jz      short loc_140004C84
0x140004c6c  bt      dword ptr [rcx+2Ch], 1Ah
0x140004c71  jnb     short loc_140004C84
0x140004c73  mov     rcx, [rcx+18h]
0x140004c77  mov     edx, 0Eh
0x140004c7c  mov     r8, r13
0x140004c7f  call    WPP_SF_
0x140004c84  call    cs:__imp_KeEnterCriticalRegion
0x140004c8b  nop     dword ptr [rax+rax+00h]
0x140004c90  xor     edx, edx
0x140004c92  lea     rcx, [rbx+10h]
0x140004c96  call    cs:__imp_ExAcquirePushLockSharedEx
0x140004c9d  nop     dword ptr [rax+rax+00h]
0x140004ca2  lea     rdi, [rbx+18h]
0x140004ca6  mov     rdx, [rdi]
0x140004ca9  test    rdx, rdx
0x140004cac  jnz     loc_140004D85
0x140004cb2  lea     rcx, [rbx+8]; RunRef
0x140004cb6  call    cs:__imp_ExAcquireRundownProtection
0x140004cbd  nop     dword ptr [rax+rax+00h]
0x140004cc2  test    al, al
0x140004cc4  jz      loc_140004DED
0x140004cca  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cd1  cmp     rcx, r12
0x140004cd4  jz      short loc_140004CEE
0x140004cd6  bt      dword ptr [rcx+2Ch], 1Ah
0x140004cdb  jnb     short loc_140004CEE
0x140004cdd  mov     rcx, [rcx+18h]
0x140004ce1  mov     edx, 0Fh
0x140004ce6  mov     r8, r13
0x140004ce9  call    WPP_SF_
0x140004cee  mov     rcx, rdi
0x140004cf1  call    MupiOpenPoliciesKeyFromRegistry
0x140004cf6  test    eax, eax
0x140004cf8  js      short loc_140004D6B
0x140004cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d01  cmp     rcx, r12
0x140004d04  jz      short loc_140004D1E
0x140004d06  bt      dword ptr [rcx+2Ch], 1Ah
0x140004d0b  jnb     short loc_140004D1E
0x140004d0d  mov     rcx, [rcx+18h]
0x140004d11  mov     edx, 10h
0x140004d16  mov     r8, r13
0x140004d19  call    WPP_SF_
0x140004d1e  mov     rcx, rbx
0x140004d21  call    MupiRegisterPoliciesKeyRegistryChangeNotification
0x140004d26  mov     esi, eax
0x140004d28  test    eax, eax
0x140004d2a  jns     short loc_140004D6B
0x140004d2c  mov     rcx, [rdi]; Handle
0x140004d2f  call    cs:__imp_ZwClose
0x140004d36  nop     dword ptr [rax+rax+00h]
0x140004d3b  mov     qword ptr [rdi], 0
0x140004d42  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d49  cmp     rcx, r12
0x140004d4c  jz      short loc_140004D6B
0x140004d4e  test    dword ptr [rcx+2Ch], 1000000h
0x140004d55  jz      short loc_140004D6B
0x140004d57  mov     rcx, [rcx+18h]
0x140004d5b  mov     edx, 11h
0x140004d60  mov     r9d, esi
0x140004d63  mov     r8, r13
0x140004d66  call    WPP_SF_d
0x140004d6b  mov     rcx, rbx
0x140004d6e  call    MupiArmParametersKeyRefreshTimer
0x140004d73  lea     rcx, [rbx+8]; RunRef
0x140004d77  call    cs:__imp_ExReleaseRundownProtection
0x140004d7e  nop     dword ptr [rax+rax+00h]
0x140004d83  jmp     short loc_140004DED
0x140004d85  mov     rax, cs:__imp_PsInitialSystemProcess
0x140004d8c  lea     r9, [rsp+68h+Handle]
0x140004d91  mov     [rsp+68h+var_30], 0
0x140004d96  mov     [rsp+68h+var_38], 2
0x140004d9e  mov     [rsp+68h+var_40], 200h
0x140004da6  mov     rcx, [rax]
0x140004da9  mov     r8, rcx
0x140004dac  mov     [rsp+68h+var_48], 0
0x140004db4  call    cs:__imp_ObDuplicateObject
0x140004dbb  nop     dword ptr [rax+rax+00h]
0x140004dc0  test    eax, eax
0x140004dc2  jns     short loc_140004DED
0x140004dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140004dcb  cmp     rcx, r12
0x140004dce  jz      short loc_140004DED
0x140004dd0  test    dword ptr [rcx+2Ch], 1000000h
0x140004dd7  jz      short loc_140004DED
0x140004dd9  mov     rcx, [rcx+18h]
0x140004ddd  mov     edx, 12h
0x140004de2  mov     r9d, eax
0x140004de5  mov     r8, r13
0x140004de8  call    WPP_SF_d
0x140004ded  xor     edx, edx
0x140004def  lea     rcx, [rbx+10h]
0x140004df3  call    cs:__imp_ExReleasePushLockSharedEx
0x140004dfa  nop     dword ptr [rax+rax+00h]
0x140004dff  call    cs:__imp_KeLeaveCriticalRegion
0x140004e06  nop     dword ptr [rax+rax+00h]
0x140004e0b  mov     rcx, [rsp+68h+Handle]; KeyHandle
0x140004e10  test    rcx, rcx
0x140004e13  jz      short loc_140004E38
0x140004e15  mov     dl, 1
0x140004e17  call    MupiReadEnableMailslotsFromPoliciesRegistry
0x140004e1c  mov     byte ptr cs:MupEnableMailslotsByPolicy, al
0x140004e22  mov     rcx, [rsp+68h+Handle]; Handle
0x140004e27  test    rcx, rcx
0x140004e2a  jz      short loc_140004E38
0x140004e2c  call    cs:__imp_ZwClose
0x140004e33  nop     dword ptr [rax+rax+00h]
0x140004e38  lea     r11, [rsp+68h+var_28]
0x140004e3d  mov     rbx, [r11+30h]
0x140004e41  mov     rbp, [r11+40h]
0x140004e45  mov     rsp, r11
0x140004e48  pop     r14
0x140004e4a  pop     r13
0x140004e4c  pop     r12
0x140004e4e  pop     rdi
0x140004e4f  pop     rsi
0x140004e50  retn
```
