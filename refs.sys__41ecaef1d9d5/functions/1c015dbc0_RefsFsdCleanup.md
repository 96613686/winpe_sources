# RefsFsdCleanup

- ea: `0x1c015dbc0`
- end: `0x1c015de74`
- name: `RefsFsdCleanup`
- size: `692`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1c0003db0`
- `0x1c000444c`
- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c015dbc0`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c015dd05`
- `ntoskrnl!KeInitializeEvent` at `0x1c015dd05`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c015dd7c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c015dd7c`
- `ntoskrnl!IofCompleteRequest` at `0x1c0183ab0`
- `ntoskrnl!IofCompleteRequest` at `0x1c0183ab0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015dca6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015dca6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015dd11`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015dd11`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015dd2d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015dd2d`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0183b00`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0183b00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015de3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015de3c`

## pseudocode

```c
__int64 __fastcall RefsFsdCleanup(__int64 a1, IRP *a2)
{
  int v4; // r14d
  __int64 v5; // rsi
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  BOOL v9; // r15d
  unsigned int Status; // [rsp+30h] [rbp-208h]
  _QWORD v12[2]; // [rsp+40h] [rbp-1F8h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-1E8h] BYREF
  _OWORD v14[2]; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 v15; // [rsp+88h] [rbp-1B0h]
  __int128 v16; // [rsp+90h] [rbp-1A8h] BYREF
  _QWORD v17[42]; // [rsp+A0h] [rbp-198h] BYREF
  _OWORD v18[2]; // [rsp+1F0h] [rbp-48h] BYREF

  v12[1] = a2;
  memset(v14, 0, sizeof(v14));
  v15 = 0;
  memset(v17, 0, sizeof(v17));
  v4 = 0;
  memset(&Event, 0, sizeof(Event));
  v16 = 0;
  v12[0] = 0;
  if ( *(_WORD *)(a1 + 2) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  else
  {
    v5 = RefsInitializeTopLevelIrp(v14, 0, 0);
    v6 = RefsInitializeLocalIrpContext(a2, v17);
    v7 = v6;
    Status = v6;
    if ( v6 < 0 )
    {
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(v6);
      RefsExtendedCompleteRequestInternal(0, a2, Status);
      return Status;
    }
    else
    {
      v8 = *(_QWORD *)(v5 + 32);
      if ( !v8 )
      {
        *(_DWORD *)(v5 + 4) = 1397140410;
        *(_QWORD *)(v5 + 32) = v17;
        LODWORD(v17[1]) |= 0x100000u;
        IoSetTopLevelIrp((PIRP)v5);
        v8 = *(_QWORD *)(v5 + 32);
      }
      v17[13] = v8;
      memset(v18, 0, sizeof(v18));
      v17[6] = v18;
      WORD1(v17[5]) = 4;
      v17[19] = &Event;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      KeEnterCriticalRegion();
      v9 = (int)IoPropagateActivityIdToThread(a2, &v16, v12) >= 0;
      do
      {
        if ( v7 == -1073741432 )
        {
          RefsCheckpointForLogFileFull(v17);
          if ( (unsigned int)++v4 >= 2 )
            HIDWORD(v17[0]) |= 0x10u;
        }
        else if ( v7 == 871 )
        {
          a2->Tail.Overlay.CurrentStackLocation->Control &= ~1u;
          KeWaitForSingleObject((PVOID)v17[19], Executive, 0, 0, 0);
        }
        RefsPreRequestProcessingExtend(v17);
        v7 = RefsCommonCleanupOnNewStack(v17, a2);
      }
      while ( v7 == -1073741608 || v7 == -1073741400 || v7 == -1073741432 || v7 == 871 );
      if ( v9 )
        IoClearActivityIdThread(v12[0]);
      KeLeaveCriticalRegion();
      return v7;
    }
  }
}

```

## disassembly

```asm
0x1c015dbc0  mov     r11, rsp
0x1c015dbc3  mov     [r11+8], rbx
0x1c015dbc7  mov     [r11+18h], rsi
0x1c015dbcb  push    rdi
0x1c015dbcc  push    r14
0x1c015dbce  push    r15
0x1c015dbd0  sub     rsp, 220h
0x1c015dbd7  mov     rax, cs:__security_cookie
0x1c015dbde  xor     rax, rsp
0x1c015dbe1  mov     [rsp+238h+var_28], rax
0x1c015dbe9  mov     rdi, rdx
0x1c015dbec  mov     rbx, rcx
0x1c015dbef  mov     [rsp+238h+var_1F0], rdx
0x1c015dbf4  xorps   xmm0, xmm0
0x1c015dbf7  xor     eax, eax
0x1c015dbf9  movups  [rsp+238h+var_1D0], xmm0
0x1c015dbfe  movups  [rsp+238h+var_1C0], xmm0
0x1c015dc03  mov     [r11-1B0h], rax
0x1c015dc0a  mov     esi, 150h
0x1c015dc0f  mov     r8d, esi; Size
0x1c015dc12  xor     edx, edx; Val
0x1c015dc14  lea     rcx, [r11-198h]; void *
0x1c015dc1b  call    memset
0x1c015dc20  xor     r14d, r14d
0x1c015dc23  mov     [rsp+238h+var_204], r14d
0x1c015dc28  xorps   xmm0, xmm0
0x1c015dc2b  xor     eax, eax
0x1c015dc2d  movups  xmmword ptr [rsp+238h+Event.Header], xmm0
0x1c015dc32  mov     [rsp+238h+Event.Header.WaitListHead.Blink], rax
0x1c015dc37  movups  [rsp+238h+var_1A8], xmm0
0x1c015dc3f  and     [rsp+238h+var_1F8], rax
0x1c015dc44  cmp     [rbx+2], si
0x1c015dc48  jz      loc_1C0183A9E
0x1c015dc4e  xor     r8d, r8d
0x1c015dc51  xor     edx, edx
0x1c015dc53  lea     rcx, [rsp+238h+var_1D0]
0x1c015dc58  call    RefsInitializeTopLevelIrp
0x1c015dc5d  mov     rsi, rax
0x1c015dc60  lea     rdx, [rsp+238h+var_198]
0x1c015dc68  mov     rcx, rdi
0x1c015dc6b  call    RefsInitializeLocalIrpContext
0x1c015dc70  mov     ebx, eax
0x1c015dc72  mov     [rsp+238h+Status], eax
0x1c015dc76  test    eax, eax
0x1c015dc78  js      loc_1C0183AC3
0x1c015dc7e  mov     rax, [rsi+20h]
0x1c015dc82  test    rax, rax
0x1c015dc85  jnz     short loc_1C015DCB6
0x1c015dc87  mov     dword ptr [rsi+4], 5346ABBAh
0x1c015dc8e  lea     rax, [rsp+238h+var_198]
0x1c015dc96  mov     [rsi+20h], rax
0x1c015dc9a  bts     [rsp+238h+var_190], 14h
0x1c015dca3  mov     rcx, rsi; Irp
0x1c015dca6  call    cs:__imp_IoSetTopLevelIrp
0x1c015dcad  nop     dword ptr [rax+rax+00h]
0x1c015dcb2  mov     rax, [rsi+20h]
0x1c015dcb6  mov     [rsp+238h+var_130], rax
0x1c015dcbe  xorps   xmm0, xmm0
0x1c015dcc1  movups  [rsp+238h+var_48], xmm0
0x1c015dcc9  movups  [rsp+238h+var_38], xmm0
0x1c015dcd1  lea     rax, [rsp+238h+var_48]
0x1c015dcd9  mov     [rsp+238h+var_168], rax
0x1c015dce1  mov     eax, 4
0x1c015dce6  mov     [rsp+238h+var_16E], ax
0x1c015dcee  lea     rax, [rsp+238h+Event]
0x1c015dcf3  mov     [rsp+238h+Object], rax
0x1c015dcfb  xor     r8d, r8d; State
0x1c015dcfe  xor     edx, edx; Type
0x1c015dd00  lea     rcx, [rsp+238h+Event]; Event
0x1c015dd05  call    cs:__imp_KeInitializeEvent
0x1c015dd0c  nop     dword ptr [rax+rax+00h]
0x1c015dd11  call    cs:__imp_KeEnterCriticalRegion
0x1c015dd18  nop     dword ptr [rax+rax+00h]
0x1c015dd1d  lea     r8, [rsp+238h+var_1F8]
0x1c015dd22  lea     rdx, [rsp+238h+var_1A8]
0x1c015dd2a  mov     rcx, rdi
0x1c015dd2d  call    cs:__imp_IoPropagateActivityIdToThread
0x1c015dd34  nop     dword ptr [rax+rax+00h]
0x1c015dd39  xor     r15d, r15d
0x1c015dd3c  lea     esi, [r15+1]
0x1c015dd40  test    eax, eax
0x1c015dd42  cmovns  r15d, esi
0x1c015dd46  mov     [rsp+238h+var_200], r15d
0x1c015dd4b  cmp     ebx, 0C0000188h
0x1c015dd51  jz      short loc_1C015DD8E
0x1c015dd53  cmp     ebx, 367h
0x1c015dd59  jnz     short loc_1C015DDB1
0x1c015dd5b  mov     rax, [rdi+0B8h]
0x1c015dd62  and     byte ptr [rax+3], 0FEh
0x1c015dd66  and     [rsp+238h+var_218], 0
0x1c015dd6c  xor     r9d, r9d; Alertable
0x1c015dd6f  xor     r8d, r8d; WaitMode
0x1c015dd72  xor     edx, edx; WaitReason
0x1c015dd74  mov     rcx, [rsp+238h+Object]; Object
0x1c015dd7c  call    cs:__imp_KeWaitForSingleObject
0x1c015dd83  nop     dword ptr [rax+rax+00h]
0x1c015dd88  mov     [rsp+238h+Status], eax
0x1c015dd8c  jmp     short loc_1C015DDB1
0x1c015dd8e  lea     rcx, [rsp+238h+var_198]
0x1c015dd96  call    RefsCheckpointForLogFileFull
0x1c015dd9b  add     r14d, esi
0x1c015dd9e  mov     [rsp+238h+var_204], r14d
0x1c015dda3  cmp     r14d, 2
0x1c015dda7  jb      short loc_1C015DDB1
0x1c015dda9  or      [rsp+238h+var_194], 10h
0x1c015ddb1  lea     rcx, [rsp+238h+var_198]
0x1c015ddb9  call    RefsPreRequestProcessingExtend
0x1c015ddbe  mov     rdx, rdi
0x1c015ddc1  lea     rcx, [rsp+238h+var_198]
0x1c015ddc9  call    RefsCommonCleanupOnNewStack
0x1c015ddce  mov     ebx, eax
0x1c015ddd0  mov     [rsp+238h+Status], eax
0x1c015ddd4  jmp     short loc_1C015DE03
0x1c015ddd6  mov     r8d, eax
0x1c015ddd9  mov     rdi, [rsp+238h+var_1F0]
0x1c015ddde  mov     rdx, rdi
0x1c015dde1  lea     rcx, [rsp+238h+var_198]
0x1c015dde9  call    RefsProcessException
0x1c015ddee  mov     ebx, eax
0x1c015ddf0  mov     [rsp+238h+Status], eax
0x1c015ddf4  mov     esi, 1
0x1c015ddf9  mov     r14d, [rsp+238h+var_204]
0x1c015ddfe  mov     r15d, [rsp+238h+var_200]
0x1c015de03  cmp     ebx, 0C00000D8h
0x1c015de09  jz      loc_1C015DD4B
0x1c015de0f  cmp     ebx, 0C00001A8h
0x1c015de15  jz      loc_1C015DD4B
0x1c015de1b  cmp     ebx, 0C0000188h
0x1c015de21  jz      loc_1C015DD4B
0x1c015de27  cmp     ebx, 367h
0x1c015de2d  jz      loc_1C015DD4B
0x1c015de33  test    r15d, r15d
0x1c015de36  jnz     loc_1C0183AFB
0x1c015de3c  call    cs:__imp_KeLeaveCriticalRegion
0x1c015de43  nop     dword ptr [rax+rax+00h]
0x1c015de48  mov     eax, ebx
0x1c015de4a  mov     rcx, [rsp+238h+var_28]
0x1c015de52  xor     rcx, rsp; StackCookie
0x1c015de55  call    __security_check_cookie
0x1c015de5a  lea     r11, [rsp+238h+var_18]
0x1c015de62  mov     rbx, [r11+20h]
0x1c015de66  mov     rsi, [r11+30h]
0x1c015de6a  mov     rsp, r11
0x1c015de6d  pop     r15
0x1c015de6f  pop     r14
0x1c015de71  pop     rdi
0x1c015de72  retn
0x1c017eaa1  push    rbp
0x1c017eaa3  sub     rsp, 30h
0x1c017eaa7  mov     rbp, rdx
0x1c017eaaa  mov     rdx, rcx
0x1c017eaad  lea     rcx, [rbp+0A0h]
0x1c017eab4  call    RefsExceptionFilter
0x1c017eab9  nop
0x1c017eaba  add     rsp, 30h
0x1c017eabe  pop     rbp
0x1c017eabf  retn
0x1c0183a9e  and     [rdi+30h], eax
0x1c0183aa1  mov     esi, 1
0x1c0183aa6  mov     [rdi+38h], rsi
0x1c0183aaa  mov     dl, sil; PriorityBoost
0x1c0183aad  mov     rcx, rdi; Irp
0x1c0183ab0  call    cs:__imp_IofCompleteRequest
0x1c0183ab7  nop     dword ptr [rax+rax+00h]
0x1c0183abc  xor     eax, eax
0x1c0183abe  jmp     loc_1C015DE4A
0x1c0183ac3  mov     al, cs:RefsStatusDebugEnabled
0x1c0183ac9  test    al, al
0x1c0183acb  jz      short loc_1C0183AE3
0x1c0183acd  mov     r8d, 148h
0x1c0183ad3  lea     rdx, aCleanupC; "Cleanup.c"
0x1c0183ada  mov     ecx, [rsp+238h+Status]; Status
0x1c0183ade  call    RefsStatusDebug
0x1c0183ae3  mov     r8d, [rsp+238h+Status]
0x1c0183ae8  mov     rdx, rdi
0x1c0183aeb  xor     ecx, ecx
0x1c0183aed  call    RefsExtendedCompleteRequestInternal
0x1c0183af2  mov     eax, [rsp+238h+Status]
0x1c0183af6  jmp     loc_1C015DE4A
0x1c0183afb  mov     rcx, [rsp+238h+var_1F8]
0x1c0183b00  call    cs:__imp_IoClearActivityIdThread
0x1c0183b07  nop     dword ptr [rax+rax+00h]
0x1c0183b0c  nop
0x1c0183b0d  jmp     loc_1C015DE3C
```
