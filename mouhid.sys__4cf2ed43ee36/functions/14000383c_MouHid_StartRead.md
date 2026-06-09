# MouHid_StartRead

- ea: `0x14000383c`
- end: `0x140003b44`
- name: `MouHid_StartRead`
- size: `776`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ff0`
- `0x140003fd0`

## callees

- `0x140001464`
- `0x140002d28`
- `0x14000383c`
- `0x140003b4c`
- `0x140003bfc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000396f`
- `ntoskrnl!KeSetEvent` at `0x140003a44`
- `ntoskrnl!KeSetEvent` at `0x140003a5c`
- `ntoskrnl!KeSetEvent` at `0x140003ac5`
- `ntoskrnl!KeSetEvent` at `0x14000396f`
- `ntoskrnl!KeSetEvent` at `0x140003a44`
- `ntoskrnl!KeSetEvent` at `0x140003a5c`
- `ntoskrnl!KeSetEvent` at `0x140003ac5`
- `ntoskrnl!KeResetEvent` at `0x140003926`
- `ntoskrnl!KeResetEvent` at `0x140003926`
- `ntoskrnl!IoReuseIrp` at `0x1400038c5`
- `ntoskrnl!IoReuseIrp` at `0x1400038c5`
- `ntoskrnl!IofCallDriver` at `0x140003959`
- `ntoskrnl!IofCallDriver` at `0x140003959`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400039f0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003ae2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400039f0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003ae2`

## pseudocode

```c
__int64 __fastcall MouHid_StartRead(_QWORD *a1)
{
  IRP *v2; // rbp
  __int64 v3; // r13
  NTSTATUS Status; // edi
  _BYTE *v5; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v7; // rax
  signed __int32 v8; // eax
  char v9; // r15
  int v10; // edx
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v16; // [rsp+20h] [rbp-58h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      14,
      (__int64)WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids);
  v2 = (IRP *)a1[14];
  v3 = a1[27];
  Status = v2->IoStatus.Status;
  if ( _InterlockedExchange((volatile __int32 *)a1 + 7, 1) == 2 )
  {
    v5 = (char *)a1 + 33;
    while ( Status >= 0 )
    {
      IoReuseIrp(v2, 0);
      CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
      v2->MdlAddress = *(PMDL *)(v3 + 144);
      CurrentStackLocation[-1].Parameters.Read.Length = *(unsigned __int16 *)(v3 + 44);
      CurrentStackLocation[-1].Parameters.Create.Options = 0;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = 0;
      CurrentStackLocation[-1].MajorFunction = 3;
      CurrentStackLocation[-1].FileObject = (PFILE_OBJECT)a1[16];
      v7 = v2->Tail.Overlay.CurrentStackLocation;
      v7[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)MouHid_ReadComplete;
      v7[-1].Context = a1;
      v7[-1].Control = -32;
      KeResetEvent((PRKEVENT)a1 + 7);
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 6, 0, 0);
      v9 = v8;
      if ( !v8 || (v5 = (char *)a1 + 33, *((_BYTE *)a1 + 33) == 1) )
      {
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 30), (PVOID)a1[14], 0x20u);
        Status = *v5 != 0 ? -1073741738 : -1073741823;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qDd(WPP_GLOBAL_Control->DeviceExtension, v12, v13, v14, v16, *a1, v9, *v5 != 0 ? 86 : 1);
        KeSetEvent((PRKEVENT)a1 + 7, 0, 0);
        KeSetEvent((PRKEVENT)a1 + 6, 0, 0);
        goto LABEL_21;
      }
      Status = IofCallDriver((PDEVICE_OBJECT)a1[1], v2);
      KeSetEvent((PRKEVENT)a1 + 7, 0, 0);
      if ( _InterlockedExchange((volatile __int32 *)a1 + 7, 2) == 3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_q(WPP_GLOBAL_Control->DeviceExtension, v10, v11, 16, v16, *a1);
        if ( _InterlockedExchange((volatile __int32 *)a1 + 7, 1) == 2 )
          continue;
      }
      goto LABEL_21;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qqd(
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        2,
        17,
        (__int64)WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids,
        *a1,
        (char)v2,
        Status);
    KeSetEvent((PRKEVENT)a1 + 6, 0, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 30), (PVOID)a1[14], 0x20u);
  }
LABEL_21:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      18,
      (__int64)WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000383c  push    rbx
0x14000383e  push    rbp
0x14000383f  push    rsi
0x140003840  push    rdi
0x140003841  push    r13
0x140003843  push    r14
0x140003845  push    r15
0x140003847  sub     rsp, 40h
0x14000384b  mov     rbx, rcx
0x14000384e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140003855  xor     r15d, r15d
0x140003858  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000385f  lea     r14, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003866  jz      short loc_140003895
0x140003868  mov     rcx, cs:WPP_GLOBAL_Control
0x14000386f  cmp     [rcx+48h], r15w
0x140003874  jz      short loc_14000388E
0x140003876  mov     rcx, [rcx+40h]
0x14000387a  lea     r9d, [r15+0Eh]
0x14000387e  lea     r8d, [r15+2]
0x140003882  mov     [rsp+78h+var_58], r14
0x140003887  mov     dl, 5
0x140003889  call    WPP_RECORDER_SF_
0x14000388e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140003895  mov     rbp, [rbx+70h]
0x140003899  mov     eax, 1
0x14000389e  mov     r13, [rbx+0D8h]
0x1400038a5  mov     edi, [rbp+30h]
0x1400038a8  xchg    eax, [rbx+1Ch]
0x1400038ab  cmp     eax, 2
0x1400038ae  jnz     loc_140003AFA
0x1400038b4  lea     rsi, [rbx+21h]
0x1400038b8  test    edi, edi
0x1400038ba  js      loc_140003A77
0x1400038c0  xor     edx, edx; Iostatus
0x1400038c2  mov     rcx, rbp; Irp
0x1400038c5  call    cs:__imp_IoReuseIrp
0x1400038cc  nop     dword ptr [rax+rax+00h]
0x1400038d1  mov     rax, [r13+90h]
0x1400038d8  lea     r14, [rbx+0A8h]
0x1400038df  mov     rcx, [rbp+0B8h]
0x1400038e6  mov     [rbp+8], rax
0x1400038ea  movzx   eax, word ptr [r13+2Ch]
0x1400038ef  mov     [rcx-40h], eax
0x1400038f2  mov     [rcx-38h], r15d
0x1400038f6  mov     [rcx-30h], r15
0x1400038fa  mov     byte ptr [rcx-48h], 3
0x1400038fe  mov     rax, [rbx+80h]
0x140003905  mov     [rcx-18h], rax
0x140003909  lea     rcx, MouHid_ReadComplete
0x140003910  mov     rax, [rbp+0B8h]
0x140003917  mov     [rax-10h], rcx
0x14000391b  mov     rcx, r14; Event
0x14000391e  mov     [rax-8], rbx
0x140003922  mov     byte ptr [rax-45h], 0E0h
0x140003926  call    cs:__imp_KeResetEvent
0x14000392d  nop     dword ptr [rax+rax+00h]
0x140003932  mov     ecx, r15d
0x140003935  xor     eax, eax
0x140003937  lock cmpxchg [rbx+18h], ecx
0x14000393c  mov     r15d, eax
0x14000393f  jz      loc_1400039DF
0x140003945  lea     rsi, [rbx+21h]
0x140003949  cmp     byte ptr [rsi], 1
0x14000394c  jz      loc_1400039DF
0x140003952  mov     rcx, [rbx+8]; DeviceObject
0x140003956  mov     rdx, rbp; Irp
0x140003959  call    cs:__imp_IofCallDriver
0x140003960  nop     dword ptr [rax+rax+00h]
0x140003965  xor     r8d, r8d; Wait
0x140003968  xor     edx, edx; Increment
0x14000396a  mov     rcx, r14; Event
0x14000396d  mov     edi, eax
0x14000396f  call    cs:__imp_KeSetEvent
0x140003976  nop     dword ptr [rax+rax+00h]
0x14000397b  mov     ecx, 2
0x140003980  xchg    ecx, [rbx+1Ch]
0x140003983  cmp     ecx, 3
0x140003986  jnz     loc_140003AF0
0x14000398c  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003993  xor     r15d, r15d
0x140003996  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000399d  jz      short loc_1400039C9
0x14000399f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400039a6  cmp     [rcx+48h], r15w
0x1400039ab  jz      short loc_1400039C2
0x1400039ad  mov     rax, [rbx]
0x1400039b0  lea     r9d, [r15+10h]
0x1400039b4  mov     rcx, [rcx+40h]
0x1400039b8  mov     [rsp+78h+var_50], rax
0x1400039bd  call    WPP_RECORDER_SF_q
0x1400039c2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400039c9  mov     eax, 1
0x1400039ce  xchg    eax, [rbx+1Ch]
0x1400039d1  cmp     eax, 2
0x1400039d4  jz      loc_1400038B8
0x1400039da  jmp     loc_140003AF3
0x1400039df  mov     rdx, [rbx+70h]; Tag
0x1400039e3  lea     rcx, [rbx+0F0h]; RemoveLock
0x1400039ea  mov     r8d, 20h ; ' '; RemlockSize
0x1400039f0  call    cs:__imp_IoReleaseRemoveLockEx
0x1400039f7  nop     dword ptr [rax+rax+00h]
0x1400039fc  mov     al, [rsi]
0x1400039fe  neg     al
0x140003a00  sbb     edi, edi
0x140003a02  and     edi, 55h
0x140003a05  add     edi, 0C0000001h
0x140003a0b  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003a12  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140003a19  jz      short loc_140003A3C
0x140003a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a22  mov     rax, [rbx]
0x140003a25  mov     [rsp+78h+var_40], edi
0x140003a29  mov     dword ptr [rsp+78h+var_48], r15d
0x140003a2e  mov     rcx, [rcx+40h]
0x140003a32  mov     [rsp+78h+var_50], rax
0x140003a37  call    WPP_RECORDER_SF_qDd
0x140003a3c  xor     r8d, r8d; Wait
0x140003a3f  xor     edx, edx; Increment
0x140003a41  mov     rcx, r14; Event
0x140003a44  call    cs:__imp_KeSetEvent
0x140003a4b  nop     dword ptr [rax+rax+00h]
0x140003a50  lea     rcx, [rbx+90h]; Event
0x140003a57  xor     r8d, r8d; Wait
0x140003a5a  xor     edx, edx; Increment
0x140003a5c  call    cs:__imp_KeSetEvent
0x140003a63  nop     dword ptr [rax+rax+00h]
0x140003a68  xor     r15d, r15d
0x140003a6b  lea     r14, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003a72  jmp     loc_140003B01
0x140003a77  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x140003a7e  lea     r14, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003a85  jz      short loc_140003AB9
0x140003a87  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a8e  mov     r9d, 11h
0x140003a94  mov     rax, [rbx]
0x140003a97  mov     dl, 3
0x140003a99  mov     [rsp+78h+var_40], edi
0x140003a9d  mov     [rsp+78h+var_48], rbp
0x140003aa2  mov     rcx, [rcx+40h]
0x140003aa6  lea     r8d, [r9-0Fh]
0x140003aaa  mov     [rsp+78h+var_50], rax
0x140003aaf  mov     [rsp+78h+var_58], r14
0x140003ab4  call    WPP_RECORDER_SF_qqd
0x140003ab9  lea     rcx, [rbx+90h]; Event
0x140003ac0  xor     r8d, r8d; Wait
0x140003ac3  xor     edx, edx; Increment
0x140003ac5  call    cs:__imp_KeSetEvent
0x140003acc  nop     dword ptr [rax+rax+00h]
0x140003ad1  mov     rdx, [rbx+70h]; Tag
0x140003ad5  lea     rcx, [rbx+0F0h]; RemoveLock
0x140003adc  mov     r8d, 20h ; ' '; RemlockSize
0x140003ae2  call    cs:__imp_IoReleaseRemoveLockEx
0x140003ae9  nop     dword ptr [rax+rax+00h]
0x140003aee  jmp     short loc_140003AFA
0x140003af0  xor     r15d, r15d
0x140003af3  lea     r14, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003afa  lea     rsi, WPP_RECORDER_INITIALIZED
0x140003b01  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140003b08  jz      short loc_140003B32
0x140003b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b11  cmp     [rcx+48h], r15w
0x140003b16  jz      short loc_140003B32
0x140003b18  mov     rcx, [rcx+40h]
0x140003b1c  mov     r9d, 12h
0x140003b22  mov     dl, 5
0x140003b24  mov     [rsp+78h+var_58], r14
0x140003b29  lea     r8d, [r9-10h]
0x140003b2d  call    WPP_RECORDER_SF_
0x140003b32  mov     eax, edi
0x140003b34  add     rsp, 40h
0x140003b38  pop     r15
0x140003b3a  pop     r14
0x140003b3c  pop     r13
0x140003b3e  pop     rdi
0x140003b3f  pop     rsi
0x140003b40  pop     rbp
0x140003b41  pop     rbx
0x140003b42  retn
```
