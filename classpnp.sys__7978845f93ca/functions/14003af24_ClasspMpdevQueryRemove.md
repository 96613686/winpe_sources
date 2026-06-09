# ClasspMpdevQueryRemove

- ea: `0x14003af24`
- end: `0x14003b140`
- name: `ClasspMpdevQueryRemove`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003a790`

## callees

- `0x14001fc38`
- `0x14002249c`
- `0x14003af24`
- `0x14003e430`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14003b116`
- `ntoskrnl!IofCallDriver` at `0x14003b116`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003afe7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003b0c4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003afe7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003b0c4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003b082`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003b082`
- `ntoskrnl!IofCompleteRequest` at `0x14003b029`
- `ntoskrnl!IofCompleteRequest` at `0x14003b029`

## pseudocode

```c
NTSTATUS __fastcall ClasspMpdevQueryRemove(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rdi
  NTSTATUS v4; // esi
  __int64 (__fastcall *v7)(_QWORD, __int64, __int64); // rax
  int v8; // eax
  int v9; // ecx
  volatile signed __int32 *DriverObjectExtension; // rax
  bool v12; // zf
  int v13; // ecx
  __int128 v14; // [rsp+30h] [rbp-38h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v4 = 0;
  if ( *(_BYTE *)(v3 + 583)
    && *(_DWORD *)(v3 + 544)
    && (v7 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64))(v3 + 560)) != 0
    && (LOBYTE(a3) = 1, v8 = v7(*(_QWORD *)(v3 + 536), a1, a3), v4 = v8, v8 < 0) )
  {
    a2->IoStatus.Status = v8;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, a1);
    }
    if ( ClassPnPETWEnabled )
    {
      v14 = 0;
      if ( (int)IoGetActivityIdIrp(a2, &v14) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(
          v9,
          (unsigned int)EventPnpRequestComplete,
          (unsigned int)&v14,
          *(_DWORD *)(v3 + 576),
          (char)a2,
          a2->IoStatus.Status);
    }
    IofCompleteRequest(a2, 0);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, a1);
    }
    DriverObjectExtension = (volatile signed __int32 *)IoGetDriverObjectExtension(
                                                         *(PDRIVER_OBJECT *)(v3 + 512),
                                                         ClassInitialize);
    *(_BYTE *)(v3 + 581) = *(_BYTE *)(v3 + 580);
    *(_BYTE *)(v3 + 580) = 1;
    _InterlockedDecrement(DriverObjectExtension + 102);
    v12 = ClassPnPETWEnabled == 0;
    a2->IoStatus.Status = v4;
    if ( !v12 )
    {
      v14 = 0;
      if ( (int)IoGetActivityIdIrp(a2, &v14) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(
          v13,
          (unsigned int)EventPnpRequestComplete,
          (unsigned int)&v14,
          *(_DWORD *)(v3 + 576),
          (char)a2,
          a2->IoStatus.Status);
    }
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 520), a2);
  }
}

```

## disassembly

```asm
0x14003af24  mov     [rsp+arg_10], rbx
0x14003af29  push    rbp
0x14003af2a  push    rsi
0x14003af2b  push    rdi
0x14003af2c  sub     rsp, 50h
0x14003af30  mov     rax, cs:__security_cookie
0x14003af37  xor     rax, rsp
0x14003af3a  mov     [rsp+68h+var_28], rax
0x14003af3f  mov     rdi, [rcx+40h]
0x14003af43  xor     esi, esi
0x14003af45  mov     rbx, rdx
0x14003af48  mov     rbp, rcx
0x14003af4b  cmp     [rdi+247h], sil
0x14003af52  jz      loc_14003B03C
0x14003af58  cmp     [rdi+220h], esi
0x14003af5e  jz      loc_14003B03C
0x14003af64  mov     rax, [rdi+230h]
0x14003af6b  test    rax, rax
0x14003af6e  jz      loc_14003B03C
0x14003af74  mov     rdx, rcx
0x14003af77  mov     r8b, 1
0x14003af7a  mov     rcx, [rdi+218h]
0x14003af81  call    _guard_dispatch_icall
0x14003af86  mov     esi, eax
0x14003af88  test    eax, eax
0x14003af8a  jns     loc_14003B03C
0x14003af90  mov     [rbx+30h], eax
0x14003af93  mov     r10, cs:WPP_GLOBAL_Control
0x14003af9a  lea     rdx, WPP_GLOBAL_Control
0x14003afa1  cmp     r10, rdx
0x14003afa4  jz      short loc_14003AFCE
0x14003afa6  mov     ecx, [r10+2Ch]
0x14003afaa  test    cl, 2
0x14003afad  jz      short loc_14003AFCE
0x14003afaf  cmp     byte ptr [r10+29h], 3
0x14003afb4  jb      short loc_14003AFCE
0x14003afb6  mov     rcx, [r10+18h]
0x14003afba  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003afc1  mov     edx, 19h
0x14003afc6  mov     r9, rbp
0x14003afc9  call    WPP_SF_q
0x14003afce  cmp     cs:ClassPnPETWEnabled, 0
0x14003afd5  jz      short loc_14003B024
0x14003afd7  xorps   xmm0, xmm0
0x14003afda  lea     rdx, [rsp+68h+var_38]
0x14003afdf  mov     rcx, rbx
0x14003afe2  movups  [rsp+68h+var_38], xmm0
0x14003afe7  call    cs:__imp_IoGetActivityIdIrp
0x14003afee  nop     dword ptr [rax+rax+00h]
0x14003aff3  test    eax, eax
0x14003aff5  js      short loc_14003B024
0x14003aff7  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003affe  jz      short loc_14003B024
0x14003b000  mov     eax, [rbx+30h]
0x14003b003  lea     r8, [rsp+68h+var_38]
0x14003b008  mov     r9d, [rdi+240h]
0x14003b00f  lea     rdx, EventPnpRequestComplete
0x14003b016  mov     [rsp+68h+var_40], eax
0x14003b01a  mov     [rsp+68h+var_48], rbx
0x14003b01f  call    McTemplateK0qpd_EtwWriteTransfer
0x14003b024  xor     edx, edx; PriorityBoost
0x14003b026  mov     rcx, rbx; Irp
0x14003b029  call    cs:__imp_IofCompleteRequest
0x14003b030  nop     dword ptr [rax+rax+00h]
0x14003b035  mov     eax, esi
0x14003b037  jmp     loc_14003B122
0x14003b03c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b043  lea     rdx, WPP_GLOBAL_Control
0x14003b04a  cmp     rcx, rdx
0x14003b04d  jz      short loc_14003B074
0x14003b04f  mov     eax, [rcx+2Ch]
0x14003b052  test    al, 2
0x14003b054  jz      short loc_14003B074
0x14003b056  cmp     byte ptr [rcx+29h], 4
0x14003b05a  jb      short loc_14003B074
0x14003b05c  mov     rcx, [rcx+18h]
0x14003b060  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003b067  mov     edx, 18h
0x14003b06c  mov     r9, rbp
0x14003b06f  call    WPP_SF_q
0x14003b074  mov     rcx, [rdi+200h]; DriverObject
0x14003b07b  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14003b082  call    cs:__imp_IoGetDriverObjectExtension
0x14003b089  nop     dword ptr [rax+rax+00h]
0x14003b08e  mov     cl, [rdi+244h]
0x14003b094  mov     [rdi+245h], cl
0x14003b09a  mov     byte ptr [rdi+244h], 1
0x14003b0a1  lock dec dword ptr [rax+198h]
0x14003b0a8  cmp     cs:ClassPnPETWEnabled, 0
0x14003b0af  mov     [rbx+30h], esi
0x14003b0b2  jz      short loc_14003B101
0x14003b0b4  xorps   xmm0, xmm0
0x14003b0b7  lea     rdx, [rsp+68h+var_38]
0x14003b0bc  mov     rcx, rbx
0x14003b0bf  movups  [rsp+68h+var_38], xmm0
0x14003b0c4  call    cs:__imp_IoGetActivityIdIrp
0x14003b0cb  nop     dword ptr [rax+rax+00h]
0x14003b0d0  test    eax, eax
0x14003b0d2  js      short loc_14003B101
0x14003b0d4  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003b0db  jz      short loc_14003B101
0x14003b0dd  mov     eax, [rbx+30h]
0x14003b0e0  lea     r8, [rsp+68h+var_38]
0x14003b0e5  mov     r9d, [rdi+240h]
0x14003b0ec  lea     rdx, EventPnpRequestComplete
0x14003b0f3  mov     [rsp+68h+var_40], eax
0x14003b0f7  mov     [rsp+68h+var_48], rbx
0x14003b0fc  call    McTemplateK0qpd_EtwWriteTransfer
0x14003b101  inc     byte ptr [rbx+43h]
0x14003b104  mov     rdx, rbx; Irp
0x14003b107  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14003b10f  mov     rcx, [rdi+208h]; DeviceObject
0x14003b116  call    cs:__imp_IofCallDriver
0x14003b11d  nop     dword ptr [rax+rax+00h]
0x14003b122  mov     rcx, [rsp+68h+var_28]
0x14003b127  xor     rcx, rsp; StackCookie
0x14003b12a  call    __security_check_cookie
0x14003b12f  mov     rbx, [rsp+68h+arg_10]
0x14003b137  add     rsp, 50h
0x14003b13b  pop     rdi
0x14003b13c  pop     rsi
0x14003b13d  pop     rbp
0x14003b13e  retn
```
