# CKsDevice::DisarmForRemoteWakeup(void)

- ea: `0x18005b870`
- end: `0x18005bb9c`
- name: `?DisarmForRemoteWakeup@CKsDevice@@AEAAJXZ`
- size: `812`
- prototype: `__int64 __fastcall(CKsDevice *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003aea0`
- `0x18005b644`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180013a88`
- `0x18005b870`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x18005ba0f`
- `ntoskrnl!IoCancelIrp` at `0x18005ba0f`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005ba98`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005ba98`
- `ntoskrnl!IofCompleteRequest` at `0x18005baae`
- `ntoskrnl!IofCompleteRequest` at `0x18005baae`

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
0x18005b870  push    rbx
0x18005b872  push    rbp
0x18005b873  push    rsi
0x18005b874  push    rdi
0x18005b875  push    r12
0x18005b877  push    r14
0x18005b879  push    r15
0x18005b87b  sub     rsp, 40h
0x18005b87f  mov     rdi, rcx
0x18005b882  xor     ebp, ebp
0x18005b884  lea     r14, WPP_RECORDER_INITIALIZED
0x18005b88b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b892  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005b899  lea     r15d, [rbp+1]
0x18005b89d  jz      short loc_18005B8C3
0x18005b89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b8a6  cmp     [rcx+48h], bp
0x18005b8aa  jz      short loc_18005B8C3
0x18005b8ac  mov     rcx, [rcx+40h]
0x18005b8b0  lea     r9d, [rbp+3Ch]
0x18005b8b4  mov     r8d, r15d
0x18005b8b7  mov     [rsp+78h+Timeout], r12
0x18005b8bc  mov     dl, 5
0x18005b8be  call    WPP_RECORDER_SF_
0x18005b8c3  cmp     [rdi+3D0h], bpl
0x18005b8ca  jnz     short loc_18005B8F5
0x18005b8cc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b8d3  jz      loc_18005BB8A
0x18005b8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b8e0  cmp     [rcx+48h], bp
0x18005b8e4  jz      loc_18005BB8A
0x18005b8ea  mov     r9d, 3Dh ; '='
0x18005b8f0  jmp     loc_18005B9B6
0x18005b8f5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b8fc  jz      short loc_18005B924
0x18005b8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b905  cmp     [rcx+48h], bp
0x18005b909  jz      short loc_18005B924
0x18005b90b  mov     rcx, [rcx+40h]
0x18005b90f  mov     r9d, 3Eh ; '>'
0x18005b915  mov     r8d, r15d
0x18005b918  mov     [rsp+78h+Timeout], r12
0x18005b91d  mov     dl, 5
0x18005b91f  call    WPP_RECORDER_SF_
0x18005b924  mov     ebx, r15d
0x18005b927  xchg    ebx, [rdi+3D4h]
0x18005b92d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b934  jz      short loc_18005B965
0x18005b936  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b93d  cmp     [rcx+48h], bp
0x18005b941  jz      short loc_18005B965
0x18005b943  mov     rcx, [rcx+40h]
0x18005b947  mov     r9d, 3Fh ; '?'
0x18005b94d  mov     [rsp+78h+var_48], r15d
0x18005b952  mov     r8d, r15d
0x18005b955  mov     dword ptr [rsp+78h+var_50], ebx
0x18005b959  mov     dl, 5
0x18005b95b  mov     [rsp+78h+Timeout], r12
0x18005b960  call    WPP_RECORDER_SF_DD
0x18005b965  test    ebx, ebx
0x18005b967  jnz     short loc_18005B98D
0x18005b969  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b970  jz      loc_18005BB8A
0x18005b976  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b97d  cmp     [rcx+48h], bp
0x18005b981  jz      loc_18005BB8A
0x18005b987  lea     r9d, [rbx+40h]
0x18005b98b  jmp     short loc_18005B9B6
0x18005b98d  cmp     ebx, r15d
0x18005b990  jnz     short loc_18005B9CE
0x18005b992  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b999  jz      loc_18005BB8A
0x18005b99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9a6  cmp     [rcx+48h], bp
0x18005b9aa  jz      loc_18005BB8A
0x18005b9b0  mov     r9d, 41h ; 'A'
0x18005b9b6  mov     rcx, [rcx+40h]
0x18005b9ba  mov     r8d, r15d
0x18005b9bd  mov     dl, 5
0x18005b9bf  mov     [rsp+78h+Timeout], r12
0x18005b9c4  call    WPP_RECORDER_SF_
0x18005b9c9  jmp     loc_18005BB8A
0x18005b9ce  mov     rsi, rbp
0x18005b9d1  xchg    rsi, [rdi+3C8h]
0x18005b9d8  test    rsi, rsi
0x18005b9db  jz      short loc_18005BA4C
0x18005b9dd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b9e4  jz      short loc_18005BA0C
0x18005b9e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9ed  cmp     [rcx+48h], bp
0x18005b9f1  jz      short loc_18005BA0C
0x18005b9f3  mov     rcx, [rcx+40h]
0x18005b9f7  mov     r9d, 42h ; 'B'
0x18005b9fd  mov     r8d, r15d
0x18005ba00  mov     [rsp+78h+Timeout], r12
0x18005ba05  mov     dl, 5
0x18005ba07  call    WPP_RECORDER_SF_
0x18005ba0c  mov     rcx, rsi; Irp
0x18005ba0f  call    cs:__imp_IoCancelIrp
0x18005ba16  nop     dword ptr [rax+rax+00h]
0x18005ba1b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ba22  jz      short loc_18005BA84
0x18005ba24  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba2b  cmp     [rcx+48h], bp
0x18005ba2f  jz      short loc_18005BA55
0x18005ba31  mov     rcx, [rcx+40h]
0x18005ba35  mov     r9d, 43h ; 'C'
0x18005ba3b  mov     r8d, r15d
0x18005ba3e  mov     [rsp+78h+Timeout], r12
0x18005ba43  mov     dl, 5
0x18005ba45  call    WPP_RECORDER_SF_
0x18005ba4a  jmp     short loc_18005BA55
0x18005ba4c  cmp     ebx, 2
0x18005ba4f  jnz     loc_18005BAE9
0x18005ba55  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ba5c  jz      short loc_18005BA84
0x18005ba5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba65  cmp     [rcx+48h], bp
0x18005ba69  jz      short loc_18005BA84
0x18005ba6b  mov     rcx, [rcx+40h]
0x18005ba6f  mov     r9d, 44h ; 'D'
0x18005ba75  mov     r8d, r15d
0x18005ba78  mov     [rsp+78h+Timeout], r12
0x18005ba7d  mov     dl, 5
0x18005ba7f  call    WPP_RECORDER_SF_
0x18005ba84  lea     rcx, [rdi+3F8h]; Object
0x18005ba8b  mov     [rsp+78h+Timeout], rbp; Timeout
0x18005ba90  xor     r9d, r9d; Alertable
0x18005ba93  xor     r8d, r8d; WaitMode
0x18005ba96  xor     edx, edx; WaitReason
0x18005ba98  call    cs:__imp_KeWaitForSingleObject
0x18005ba9f  nop     dword ptr [rax+rax+00h]
0x18005baa4  test    rsi, rsi
0x18005baa7  jz      short loc_18005BAE9
0x18005baa9  xor     edx, edx; PriorityBoost
0x18005baab  mov     rcx, rsi; Irp
0x18005baae  call    cs:__imp_IofCompleteRequest
0x18005bab5  nop     dword ptr [rax+rax+00h]
0x18005baba  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bac1  jz      short loc_18005BB18
0x18005bac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005baca  cmp     [rcx+48h], bp
0x18005bace  jz      short loc_18005BAE9
0x18005bad0  mov     rcx, [rcx+40h]
0x18005bad4  mov     r9d, 45h ; 'E'
0x18005bada  mov     r8d, r15d
0x18005badd  mov     [rsp+78h+Timeout], r12
0x18005bae2  mov     dl, 5
0x18005bae4  call    WPP_RECORDER_SF_
0x18005bae9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005baf0  jz      short loc_18005BB18
0x18005baf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005baf9  cmp     [rcx+48h], bp
0x18005bafd  jz      short loc_18005BB18
0x18005baff  mov     rcx, [rcx+40h]
0x18005bb03  mov     r9d, 46h ; 'F'
0x18005bb09  mov     r8d, r15d
0x18005bb0c  mov     [rsp+78h+Timeout], r12
0x18005bb11  mov     dl, 5
0x18005bb13  call    WPP_RECORDER_SF_
0x18005bb18  mov     eax, ebp
0x18005bb1a  xchg    eax, [rdi+3D4h]
0x18005bb20  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bb27  jz      short loc_18005BB8A
0x18005bb29  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb30  cmp     [rcx+48h], bp
0x18005bb34  jz      short loc_18005BB57
0x18005bb36  mov     rcx, [rcx+40h]
0x18005bb3a  mov     r9d, 47h ; 'G'
0x18005bb40  mov     [rsp+78h+var_48], ebp
0x18005bb44  mov     r8d, r15d
0x18005bb47  mov     dword ptr [rsp+78h+var_50], eax
0x18005bb4b  mov     dl, 5
0x18005bb4d  mov     [rsp+78h+Timeout], r12
0x18005bb52  call    WPP_RECORDER_SF_DD
0x18005bb57  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005bb5e  jz      short loc_18005BB8A
0x18005bb60  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb67  cmp     [rcx+48h], bp
0x18005bb6b  jz      short loc_18005BB8A
0x18005bb6d  mov     rcx, [rcx+40h]
0x18005bb71  mov     r9d, 48h ; 'H'
0x18005bb77  mov     dword ptr [rsp+78h+var_50], ebp
0x18005bb7b  mov     r8d, r15d
0x18005bb7e  mov     dl, 5
0x18005bb80  mov     [rsp+78h+Timeout], r12
0x18005bb85  call    WPP_RECORDER_SF_D
0x18005bb8a  xor     eax, eax
0x18005bb8c  add     rsp, 40h
0x18005bb90  pop     r15
0x18005bb92  pop     r14
0x18005bb94  pop     r12
0x18005bb96  pop     rdi
0x18005bb97  pop     rsi
0x18005bb98  pop     rbp
0x18005bb99  pop     rbx
0x18005bb9a  retn
```
