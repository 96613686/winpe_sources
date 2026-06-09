# CKsDevice::DisarmForRemoteWakeup(void)

- ea: `0x18005ba10`
- end: `0x18005bd3c`
- name: `?DisarmForRemoteWakeup@CKsDevice@@AEAAJXZ`
- size: `812`
- prototype: `__int64 __fastcall(CKsDevice *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ae90`
- `0x18005b7e4`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180013a88`
- `0x18005ba10`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x18005bbaf`
- `ntoskrnl!IoCancelIrp` at `0x18005bbaf`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005bc38`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005bc38`
- `ntoskrnl!IofCompleteRequest` at `0x18005bc4e`
- `ntoskrnl!IofCompleteRequest` at `0x18005bc4e`

## pseudocode

```c
__int64 __fastcall CKsDevice::DisarmForRemoteWakeup(CKsDevice *this)
{
  PDEVICE_OBJECT v2; // rcx
  int v3; // r9d
  __int32 v4; // ebx
  IRP *v5; // rsi
  char v6; // al
  __int64 v8; // [rsp+28h] [rbp-50h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      60,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  if ( !this->m_RemoteWakeup )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v2 = WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v3 = 61;
LABEL_22:
        WPP_RECORDER_SF_(v2->DeviceExtension, 5, 1, v3, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        return 0;
      }
    }
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      62,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  v4 = _InterlockedExchange((volatile __int32 *)&this->m_WakeState, 1);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      63,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      v4,
      1);
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v2 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v3 = 65;
          goto LABEL_22;
        }
      }
      return 0;
    }
    v5 = (IRP *)_InterlockedExchange64((volatile __int64 *)&this->m_PendingWakeIrp, 0);
    if ( v5 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          1,
          66,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      IoCancelIrp(v5);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_34:
        KeWaitForSingleObject(&this->m_WakeupCompletionSignal, Executive, 0, 0, 0);
        if ( v5 )
        {
          IofCompleteRequest(v5, 0);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_41:
            v6 = _InterlockedExchange((volatile __int32 *)&this->m_WakeState, 0);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
                WPP_RECORDER_SF_DD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  5,
                  1,
                  71,
                  (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
                  v6,
                  0);
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LODWORD(v8) = 0;
                WPP_RECORDER_SF_D(
                  WPP_GLOBAL_Control->DeviceExtension,
                  5,
                  1,
                  72,
                  (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
                  v8);
              }
            }
            return 0;
          }
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              5,
              1,
              69,
              (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
LABEL_38:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            1,
            70,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        goto LABEL_41;
      }
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          1,
          67,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    else if ( v4 != 2 )
    {
      goto LABEL_38;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        68,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    goto LABEL_34;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v2 = WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v3 = 64;
      goto LABEL_22;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005ba10  push    rbx
0x18005ba12  push    rbp
0x18005ba13  push    rsi
0x18005ba14  push    rdi
0x18005ba15  push    r12
0x18005ba17  push    r14
0x18005ba19  push    r15
0x18005ba1b  sub     rsp, 40h
0x18005ba1f  mov     rdi, rcx
0x18005ba22  xor     ebp, ebp
0x18005ba24  lea     r14, WPP_RECORDER_INITIALIZED
0x18005ba2b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ba32  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005ba39  lea     r15d, [rbp+1]
0x18005ba3d  jz      short loc_18005BA63
0x18005ba3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba46  cmp     [rcx+48h], bp
0x18005ba4a  jz      short loc_18005BA63
0x18005ba4c  mov     rcx, [rcx+40h]
0x18005ba50  lea     r9d, [rbp+3Ch]
0x18005ba54  mov     r8d, r15d
0x18005ba57  mov     [rsp+78h+Timeout], r12
0x18005ba5c  mov     dl, 5
0x18005ba5e  call    WPP_RECORDER_SF_
0x18005ba63  cmp     [rdi+3D0h], bpl
0x18005ba6a  jnz     short loc_18005BA95
0x18005ba6c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ba73  jz      loc_18005BD2A
0x18005ba79  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba80  cmp     [rcx+48h], bp
0x18005ba84  jz      loc_18005BD2A
0x18005ba8a  mov     r9d, 3Dh ; '='
0x18005ba90  jmp     loc_18005BB56
0x18005ba95  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ba9c  jz      short loc_18005BAC4
0x18005ba9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005baa5  cmp     [rcx+48h], bp
0x18005baa9  jz      short loc_18005BAC4
0x18005baab  mov     rcx, [rcx+40h]
0x18005baaf  mov     r9d, 3Eh ; '>'
0x18005bab5  mov     r8d, r15d
0x18005bab8  mov     [rsp+78h+Timeout], r12
0x18005babd  mov     dl, 5
0x18005babf  call    WPP_RECORDER_SF_
0x18005bac4  mov     ebx, r15d
0x18005bac7  xchg    ebx, [rdi+3D4h]
0x18005bacd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bad4  jz      short loc_18005BB05
0x18005bad6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005badd  cmp     [rcx+48h], bp
0x18005bae1  jz      short loc_18005BB05
0x18005bae3  mov     rcx, [rcx+40h]
0x18005bae7  mov     r9d, 3Fh ; '?'
0x18005baed  mov     [rsp+78h+var_48], r15d
0x18005baf2  mov     r8d, r15d
0x18005baf5  mov     dword ptr [rsp+78h+var_50], ebx
0x18005baf9  mov     dl, 5
0x18005bafb  mov     [rsp+78h+Timeout], r12
0x18005bb00  call    WPP_RECORDER_SF_DD
0x18005bb05  test    ebx, ebx
0x18005bb07  jnz     short loc_18005BB2D
0x18005bb09  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bb10  jz      loc_18005BD2A
0x18005bb16  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb1d  cmp     [rcx+48h], bp
0x18005bb21  jz      loc_18005BD2A
0x18005bb27  lea     r9d, [rbx+40h]
0x18005bb2b  jmp     short loc_18005BB56
0x18005bb2d  cmp     ebx, r15d
0x18005bb30  jnz     short loc_18005BB6E
0x18005bb32  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bb39  jz      loc_18005BD2A
0x18005bb3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb46  cmp     [rcx+48h], bp
0x18005bb4a  jz      loc_18005BD2A
0x18005bb50  mov     r9d, 41h ; 'A'
0x18005bb56  mov     rcx, [rcx+40h]
0x18005bb5a  mov     r8d, r15d
0x18005bb5d  mov     dl, 5
0x18005bb5f  mov     [rsp+78h+Timeout], r12
0x18005bb64  call    WPP_RECORDER_SF_
0x18005bb69  jmp     loc_18005BD2A
0x18005bb6e  mov     rsi, rbp
0x18005bb71  xchg    rsi, [rdi+3C8h]
0x18005bb78  test    rsi, rsi
0x18005bb7b  jz      short loc_18005BBEC
0x18005bb7d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bb84  jz      short loc_18005BBAC
0x18005bb86  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb8d  cmp     [rcx+48h], bp
0x18005bb91  jz      short loc_18005BBAC
0x18005bb93  mov     rcx, [rcx+40h]
0x18005bb97  mov     r9d, 42h ; 'B'
0x18005bb9d  mov     r8d, r15d
0x18005bba0  mov     [rsp+78h+Timeout], r12
0x18005bba5  mov     dl, 5
0x18005bba7  call    WPP_RECORDER_SF_
0x18005bbac  mov     rcx, rsi; Irp
0x18005bbaf  call    cs:__imp_IoCancelIrp
0x18005bbb6  nop     dword ptr [rax+rax+00h]
0x18005bbbb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bbc2  jz      short loc_18005BC24
0x18005bbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bbcb  cmp     [rcx+48h], bp
0x18005bbcf  jz      short loc_18005BBF5
0x18005bbd1  mov     rcx, [rcx+40h]
0x18005bbd5  mov     r9d, 43h ; 'C'
0x18005bbdb  mov     r8d, r15d
0x18005bbde  mov     [rsp+78h+Timeout], r12
0x18005bbe3  mov     dl, 5
0x18005bbe5  call    WPP_RECORDER_SF_
0x18005bbea  jmp     short loc_18005BBF5
0x18005bbec  cmp     ebx, 2
0x18005bbef  jnz     loc_18005BC89
0x18005bbf5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bbfc  jz      short loc_18005BC24
0x18005bbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc05  cmp     [rcx+48h], bp
0x18005bc09  jz      short loc_18005BC24
0x18005bc0b  mov     rcx, [rcx+40h]
0x18005bc0f  mov     r9d, 44h ; 'D'
0x18005bc15  mov     r8d, r15d
0x18005bc18  mov     [rsp+78h+Timeout], r12
0x18005bc1d  mov     dl, 5
0x18005bc1f  call    WPP_RECORDER_SF_
0x18005bc24  lea     rcx, [rdi+3F8h]; Object
0x18005bc2b  mov     [rsp+78h+Timeout], rbp; Timeout
0x18005bc30  xor     r9d, r9d; Alertable
0x18005bc33  xor     r8d, r8d; WaitMode
0x18005bc36  xor     edx, edx; WaitReason
0x18005bc38  call    cs:__imp_KeWaitForSingleObject
0x18005bc3f  nop     dword ptr [rax+rax+00h]
0x18005bc44  test    rsi, rsi
0x18005bc47  jz      short loc_18005BC89
0x18005bc49  xor     edx, edx; PriorityBoost
0x18005bc4b  mov     rcx, rsi; Irp
0x18005bc4e  call    cs:__imp_IofCompleteRequest
0x18005bc55  nop     dword ptr [rax+rax+00h]
0x18005bc5a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bc61  jz      short loc_18005BCB8
0x18005bc63  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc6a  cmp     [rcx+48h], bp
0x18005bc6e  jz      short loc_18005BC89
0x18005bc70  mov     rcx, [rcx+40h]
0x18005bc74  mov     r9d, 45h ; 'E'
0x18005bc7a  mov     r8d, r15d
0x18005bc7d  mov     [rsp+78h+Timeout], r12
0x18005bc82  mov     dl, 5
0x18005bc84  call    WPP_RECORDER_SF_
0x18005bc89  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bc90  jz      short loc_18005BCB8
0x18005bc92  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc99  cmp     [rcx+48h], bp
0x18005bc9d  jz      short loc_18005BCB8
0x18005bc9f  mov     rcx, [rcx+40h]
0x18005bca3  mov     r9d, 46h ; 'F'
0x18005bca9  mov     r8d, r15d
0x18005bcac  mov     [rsp+78h+Timeout], r12
0x18005bcb1  mov     dl, 5
0x18005bcb3  call    WPP_RECORDER_SF_
0x18005bcb8  mov     eax, ebp
0x18005bcba  xchg    eax, [rdi+3D4h]
0x18005bcc0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bcc7  jz      short loc_18005BD2A
0x18005bcc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bcd0  cmp     [rcx+48h], bp
0x18005bcd4  jz      short loc_18005BCF7
0x18005bcd6  mov     rcx, [rcx+40h]
0x18005bcda  mov     r9d, 47h ; 'G'
0x18005bce0  mov     [rsp+78h+var_48], ebp
0x18005bce4  mov     r8d, r15d
0x18005bce7  mov     dword ptr [rsp+78h+var_50], eax
0x18005bceb  mov     dl, 5
0x18005bced  mov     [rsp+78h+Timeout], r12
0x18005bcf2  call    WPP_RECORDER_SF_DD
0x18005bcf7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bcfe  jz      short loc_18005BD2A
0x18005bd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd07  cmp     [rcx+48h], bp
0x18005bd0b  jz      short loc_18005BD2A
0x18005bd0d  mov     rcx, [rcx+40h]
0x18005bd11  mov     r9d, 48h ; 'H'
0x18005bd17  mov     dword ptr [rsp+78h+var_50], ebp
0x18005bd1b  mov     r8d, r15d
0x18005bd1e  mov     dl, 5
0x18005bd20  mov     [rsp+78h+Timeout], r12
0x18005bd25  call    WPP_RECORDER_SF_D
0x18005bd2a  xor     eax, eax
0x18005bd2c  add     rsp, 40h
0x18005bd30  pop     r15
0x18005bd32  pop     r14
0x18005bd34  pop     r12
0x18005bd36  pop     rdi
0x18005bd37  pop     rsi
0x18005bd38  pop     rbp
0x18005bd39  pop     rbx
0x18005bd3a  retn
```
