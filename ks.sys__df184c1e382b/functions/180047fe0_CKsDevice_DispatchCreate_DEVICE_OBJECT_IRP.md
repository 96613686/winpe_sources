# CKsDevice::DispatchCreate(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180047fe0`
- end: `0x1800481c0`
- name: `?DispatchCreate@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800073d0`
- `0x18000b7bc`
- `0x180019cb0`
- `0x180047fe0`
- `0x1800485a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1800481af`
- `ntoskrnl!IofCompleteRequest` at `0x1800481af`

## pseudocode

```c
__int64 __fastcall CKsDevice::DispatchCreate(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rsi
  int v6; // edx
  unsigned int v7; // ebx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      157,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  v4 = *(_QWORD *)(*(_QWORD *)a1->DeviceExtension + 360LL);
  v5 = v4 - 200;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v4 - 200) + 40LL))(v4 - 200);
  if ( *(_BYTE *)(v4 - 200 + 788) )
  {
    v7 = -1073741436;
  }
  else if ( *(_BYTE *)(v5 + 784) )
  {
    if ( *(_BYTE *)(v4 + 48) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          160,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
      v7 = 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          159,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
      v7 = -1073741661;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        158,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    KsAddIrpToCancelableQueue((PLIST_ENTRY)(v5 + 536), (PKSPIN_LOCK)(v5 + 552), v2, KsListEntryTail, 0);
    v7 = 259;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5);
  if ( v7 )
  {
    if ( v7 != 259 )
    {
      v2->IoStatus.Status = v7;
      IofCompleteRequest(v2, 0);
    }
  }
  else
  {
    return (unsigned int)DispatchCreate(a1, v2);
  }
  return v7;
}

```

## disassembly

```asm
0x180047fe0  push    rbx
0x180047fe2  push    rbp
0x180047fe3  push    rsi
0x180047fe4  push    rdi
0x180047fe5  push    r13
0x180047fe7  push    r14
0x180047fe9  push    r15
0x180047feb  sub     rsp, 30h
0x180047fef  mov     rdi, rdx
0x180047ff2  mov     rbp, rcx
0x180047ff5  lea     r15, WPP_RECORDER_INITIALIZED
0x180047ffc  xor     r14d, r14d
0x180047fff  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180048006  lea     r13, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18004800d  jz      short loc_180048021
0x18004800f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048016  cmp     [rcx+48h], r14w
0x18004801b  jnz     loc_1800480FC
0x180048021  mov     rax, [rbp+40h]
0x180048025  mov     rcx, [rax]
0x180048028  mov     rbx, [rcx+168h]
0x18004802f  lea     rsi, [rbx-0C8h]
0x180048036  mov     rax, [rsi]
0x180048039  mov     rcx, rsi
0x18004803c  mov     rax, [rax+28h]
0x180048040  call    _guard_dispatch_icall
0x180048045  cmp     [rsi+314h], r14b
0x18004804c  jnz     short loc_1800480BF
0x18004804e  cmp     [rsi+310h], r14b
0x180048055  jz      short loc_1800480C6
0x180048057  cmp     [rbx+30h], r14b
0x18004805b  jz      loc_180048149
0x180048061  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180048068  jz      short loc_18004807C
0x18004806a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048071  cmp     [rcx+48h], r14w
0x180048076  jnz     loc_180048186
0x18004807c  mov     ebx, r14d
0x18004807f  mov     rax, [rsi]
0x180048082  mov     rcx, rsi
0x180048085  mov     rax, [rax+30h]
0x180048089  call    _guard_dispatch_icall
0x18004808e  test    ebx, ebx
0x180048090  jz      short loc_1800480B0
0x180048092  cmp     ebx, 103h
0x180048098  jnz     loc_1800481A7
0x18004809e  mov     eax, ebx
0x1800480a0  add     rsp, 30h
0x1800480a4  pop     r15
0x1800480a6  pop     r14
0x1800480a8  pop     r13
0x1800480aa  pop     rdi
0x1800480ab  pop     rsi
0x1800480ac  pop     rbp
0x1800480ad  pop     rbx
0x1800480ae  retn
0x1800480b0  mov     rdx, rdi
0x1800480b3  mov     rcx, rbp
0x1800480b6  call    DispatchCreate
0x1800480bb  mov     ebx, eax
0x1800480bd  jmp     short loc_18004809E
0x1800480bf  mov     ebx, 0C0000184h
0x1800480c4  jmp     short loc_18004807F
0x1800480c6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800480cd  jnz     short loc_18004811D
0x1800480cf  mov     rax, [rdi+0B8h]
0x1800480d6  lea     rcx, [rsi+218h]; QueueHead
0x1800480dd  lea     rdx, [rcx+10h]; SpinLock
0x1800480e1  mov     [rsp+68h+DriverCancel], r14; DriverCancel
0x1800480e6  xor     r9d, r9d; ListLocation
0x1800480e9  mov     r8, rdi; Irp
0x1800480ec  or      byte ptr [rax+3], 1
0x1800480f0  call    KsAddIrpToCancelableQueue
0x1800480f5  mov     ebx, 103h
0x1800480fa  jmp     short loc_18004807F
0x1800480fc  mov     rcx, [rcx+40h]
0x180048100  mov     r9d, 9Dh
0x180048106  mov     r8d, 1
0x18004810c  mov     [rsp+68h+DriverCancel], r13
0x180048111  mov     dl, 5
0x180048113  call    WPP_RECORDER_SF_
0x180048118  jmp     loc_180048021
0x18004811d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048124  cmp     [rcx+48h], r14w
0x180048129  jz      short loc_1800480CF
0x18004812b  mov     rcx, [rcx+40h]
0x18004812f  mov     r9d, 9Eh
0x180048135  mov     r8d, 1
0x18004813b  mov     [rsp+68h+DriverCancel], r13
0x180048140  mov     dl, 5
0x180048142  call    WPP_RECORDER_SF_
0x180048147  jmp     short loc_1800480CF
0x180048149  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180048150  jz      short loc_18004817C
0x180048152  mov     rcx, cs:WPP_GLOBAL_Control
0x180048159  cmp     [rcx+48h], r14w
0x18004815e  jz      short loc_18004817C
0x180048160  mov     rcx, [rcx+40h]
0x180048164  mov     r9d, 9Fh
0x18004816a  mov     r8d, 1
0x180048170  mov     [rsp+68h+DriverCancel], r13
0x180048175  mov     dl, 5
0x180048177  call    WPP_RECORDER_SF_
0x18004817c  mov     ebx, 0C00000A3h
0x180048181  jmp     loc_18004807F
0x180048186  mov     rcx, [rcx+40h]
0x18004818a  mov     r9d, 0A0h
0x180048190  mov     r8d, 1
0x180048196  mov     [rsp+68h+DriverCancel], r13
0x18004819b  mov     dl, 5
0x18004819d  call    WPP_RECORDER_SF_
0x1800481a2  jmp     loc_18004807C
0x1800481a7  xor     edx, edx; PriorityBoost
0x1800481a9  mov     [rdi+30h], ebx
0x1800481ac  mov     rcx, rdi; Irp
0x1800481af  call    cs:__imp_IofCompleteRequest
0x1800481b6  nop     dword ptr [rax+rax+00h]
0x1800481bb  jmp     loc_18004809E
```
