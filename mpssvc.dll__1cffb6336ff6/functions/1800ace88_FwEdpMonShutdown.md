# FwEdpMonShutdown

- ea: `0x1800ace88`
- end: `0x1800acff8`
- name: `FwEdpMonShutdown`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053bcc`
- `0x1800b87e0`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x180066564`
- `0x1800ace88`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aced4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800acf25`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800acf64`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aced4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800acf25`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800acf64`
- `ntdll!RtlNtStatusToDosError` at `0x1800acedc`
- `ntdll!RtlNtStatusToDosError` at `0x1800acf2d`
- `ntdll!RtlNtStatusToDosError` at `0x1800acf6c`
- `ntdll!RtlNtStatusToDosError` at `0x1800acedc`
- `ntdll!RtlNtStatusToDosError` at `0x1800acf2d`
- `ntdll!RtlNtStatusToDosError` at `0x1800acf6c`
- `fwbase!FwCriticalSectionDestroy` at `0x1800acfba`
- `fwbase!FwCriticalSectionDestroy` at `0x1800acfba`

## pseudocode

```c
ULONG FwEdpMonShutdown()
{
  NTSTATUS v0; // eax
  ULONG result; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_62cec46a07153fff7d0ab4a1cc7f6c67_Traceguids);
  FwCancelLock();
  if ( qword_18012C6B8 )
  {
    v0 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    result = RtlNtStatusToDosError(v0);
    if ( result )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return result;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_22;
      v3 = 17;
      goto LABEL_9;
    }
  }
  if ( qword_18012C6B0 )
  {
    v4 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    result = RtlNtStatusToDosError(v4);
    if ( result )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return result;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_22;
      v3 = 18;
      goto LABEL_9;
    }
  }
  if ( !qword_18012C6A8
    || (v5 = RtlUnsubscribeWnfNotificationWaitForCompletion(), (result = RtlNtStatusToDosError(v5)) == 0) )
  {
    qword_18012C6B8 = 0;
    qword_18012C6B0 = 0;
    qword_18012C6A8 = 0;
    result = FwCriticalSectionDestroy(qword_18012C6C0);
    dword_18012C698 = 0;
    goto LABEL_21;
  }
  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v3 = 19;
LABEL_9:
    result = WPP_SF_d(*(_QWORD *)(v2 + 16), v3, WPP_62cec46a07153fff7d0ab4a1cc7f6c67_Traceguids, result);
LABEL_21:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 8) != 0 )
    return WPP_SF_(*(_QWORD *)(v2 + 16), 20, WPP_62cec46a07153fff7d0ab4a1cc7f6c67_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800ace88  mov     [rsp+arg_0], rsi
0x1800ace8d  push    rdi
0x1800ace8e  sub     rsp, 20h
0x1800ace92  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace99  lea     rdi, WPP_GLOBAL_Control
0x1800acea0  lea     rsi, WPP_62cec46a07153fff7d0ab4a1cc7f6c67_Traceguids
0x1800acea7  cmp     rcx, rdi
0x1800aceaa  jz      short loc_1800ACEC3
0x1800aceac  test    byte ptr [rcx+1Ch], 8
0x1800aceb0  jz      short loc_1800ACEC3
0x1800aceb2  mov     rcx, [rcx+10h]
0x1800aceb6  mov     edx, 10h
0x1800acebb  mov     r8, rsi
0x1800acebe  call    WPP_SF_
0x1800acec3  call    FwCancelLock
0x1800acec8  mov     rcx, cs:qword_18012C6B8
0x1800acecf  test    rcx, rcx
0x1800aced2  jz      short loc_1800ACF19
0x1800aced4  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800aceda  mov     ecx, eax; Status
0x1800acedc  call    cs:__imp_RtlNtStatusToDosError
0x1800acee2  test    eax, eax
0x1800acee4  jz      short loc_1800ACF19
0x1800acee6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aceed  cmp     rcx, rdi
0x1800acef0  jz      loc_1800ACFED
0x1800acef6  test    byte ptr [rcx+1Ch], 1
0x1800acefa  jz      loc_1800ACFD1
0x1800acf00  mov     edx, 11h
0x1800acf05  mov     rcx, [rcx+10h]
0x1800acf09  mov     r9d, eax
0x1800acf0c  mov     r8, rsi
0x1800acf0f  call    WPP_SF_d
0x1800acf14  jmp     loc_1800ACFCA
0x1800acf19  mov     rcx, cs:qword_18012C6B0
0x1800acf20  test    rcx, rcx
0x1800acf23  jz      short loc_1800ACF58
0x1800acf25  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800acf2b  mov     ecx, eax; Status
0x1800acf2d  call    cs:__imp_RtlNtStatusToDosError
0x1800acf33  test    eax, eax
0x1800acf35  jz      short loc_1800ACF58
0x1800acf37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf3e  cmp     rcx, rdi
0x1800acf41  jz      loc_1800ACFED
0x1800acf47  test    byte ptr [rcx+1Ch], 1
0x1800acf4b  jz      loc_1800ACFD1
0x1800acf51  mov     edx, 12h
0x1800acf56  jmp     short loc_1800ACF05
0x1800acf58  mov     rcx, cs:qword_18012C6A8
0x1800acf5f  test    rcx, rcx
0x1800acf62  jz      short loc_1800ACF92
0x1800acf64  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800acf6a  mov     ecx, eax; Status
0x1800acf6c  call    cs:__imp_RtlNtStatusToDosError
0x1800acf72  test    eax, eax
0x1800acf74  jz      short loc_1800ACF92
0x1800acf76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf7d  cmp     rcx, rdi
0x1800acf80  jz      short loc_1800ACFED
0x1800acf82  test    byte ptr [rcx+1Ch], 1
0x1800acf86  jz      short loc_1800ACFD1
0x1800acf88  mov     edx, 13h
0x1800acf8d  jmp     loc_1800ACF05
0x1800acf92  lea     rcx, qword_18012C6C0
0x1800acf99  mov     cs:qword_18012C6B8, 0
0x1800acfa4  mov     cs:qword_18012C6B0, 0
0x1800acfaf  mov     cs:qword_18012C6A8, 0
0x1800acfba  call    cs:__imp_FwCriticalSectionDestroy
0x1800acfc0  mov     cs:dword_18012C698, 0
0x1800acfca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acfd1  cmp     rcx, rdi
0x1800acfd4  jz      short loc_1800ACFED
0x1800acfd6  test    byte ptr [rcx+1Ch], 8
0x1800acfda  jz      short loc_1800ACFED
0x1800acfdc  mov     rcx, [rcx+10h]
0x1800acfe0  mov     edx, 14h
0x1800acfe5  mov     r8, rsi
0x1800acfe8  call    WPP_SF_
0x1800acfed  mov     rsi, [rsp+28h+arg_0]
0x1800acff2  add     rsp, 20h
0x1800acff6  pop     rdi
0x1800acff7  retn
```
