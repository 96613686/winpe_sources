# KbdHid_Power

- ea: `0x140003b20`
- end: `0x140003d4a`
- name: `KbdHid_Power`
- size: `554`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003b20`
- `0x140004130`
- `0x140005a0c`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140003cc4`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140003cc4`
- `ntoskrnl!IofCompleteRequest` at `0x140003bd6`
- `ntoskrnl!IofCompleteRequest` at `0x140003bd6`
- `ntoskrnl!PoCallDriver` at `0x140003cee`
- `ntoskrnl!PoCallDriver` at `0x140003d10`
- `ntoskrnl!PoCallDriver` at `0x140003cee`
- `ntoskrnl!PoCallDriver` at `0x140003d10`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003bc2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003c65`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003bc2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140003c65`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003d2a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003d2a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003bad`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003bad`

## pseudocode

```c
__int64 __fastcall KbdHid_Power(__int64 a1, IRP *a2)
{
  IRP *v2; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PDEVICE_OBJECT *v5; // rdi
  ULONG Options; // r15d
  int LowPart; // r13d
  NTSTATUS v8; // ebp
  int v9; // r8d
  int v10; // r9d
  char v12; // bp
  const char *v13; // rax
  struct _IO_STACK_LOCATION *v14; // rax
  struct _IO_STACK_LOCATION *v15; // rax
  unsigned int v16; // edi
  NTSTATUS v17; // eax
  struct _IO_REMOVE_LOCK *v18; // rcx
  int RemlockSize; // [rsp+20h] [rbp-78h]

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      4,
      21,
      (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v5 = *(PDEVICE_OBJECT **)(a1 + 64);
  Options = CurrentStackLocation->Parameters.Create.Options;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v8 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 19), v2, File, 1u, 0x20u);
  if ( v8 >= 0 )
  {
    v12 = 0;
    if ( CurrentStackLocation->MinorFunction == 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = "S";
        if ( Options )
          v13 = "D";
        WPP_RECORDER_SF_qqsd(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)"D",
          v9,
          v10,
          RemlockSize,
          a1,
          (char)v2,
          (__int64)v13,
          LowPart - 1);
      }
      if ( Options == 1 )
      {
        if ( *((_BYTE *)v5 + 90) )
        {
          if ( *((_DWORD *)v5 + 6) == 1 )
          {
            v12 = 0;
            if ( LowPart > 1 )
              v12 = Options;
          }
        }
        *((_DWORD *)v5 + 6) = LowPart;
      }
    }
    PoStartNextPowerIrp(v2);
    v14 = v2->Tail.Overlay.CurrentStackLocation;
    if ( v12 )
    {
      *(_OWORD *)&v14[-1].MajorFunction = *(_OWORD *)&v14->MajorFunction;
      *(_OWORD *)&v14[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v14->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v14[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v14->Parameters.SetQuota + 6);
      v14[-1].FileObject = v14->FileObject;
      v14[-1].Control = 0;
      if ( IoSetCompletionRoutineEx(*v5, v2, KbdHid_PowerCompletion, v5, 1u, 1u, 1u) < 0 )
      {
        v15 = v2->Tail.Overlay.CurrentStackLocation;
        v15[-1].CompletionRoutine = KbdHid_PowerCompletion;
        v15[-1].Context = v5;
        v15[-1].Control = -32;
      }
      return (unsigned int)PoCallDriver(v5[1], v2);
    }
    else
    {
      ++v2->CurrentLocation;
      v2->Tail.Overlay.CurrentStackLocation = v14 + 1;
      v17 = PoCallDriver(v5[1], v2);
      v18 = (struct _IO_REMOVE_LOCK *)(v5 + 19);
      v16 = v17;
      IoReleaseRemoveLockEx(v18, v2, 0x20u);
    }
    return v16;
  }
  else
  {
    PoStartNextPowerIrp(v2);
    v2->IoStatus.Status = v8;
    IofCompleteRequest(v2, 0);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x140003b20  push    rbx
0x140003b22  push    rbp
0x140003b23  push    rsi
0x140003b24  push    rdi
0x140003b25  push    r12
0x140003b27  push    r13
0x140003b29  push    r14
0x140003b2b  push    r15
0x140003b2d  sub     rsp, 58h
0x140003b31  mov     rbx, rdx
0x140003b34  mov     rsi, rcx
0x140003b37  lea     rax, WPP_RECORDER_INITIALIZED
0x140003b3e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003b45  jz      short loc_140003B78
0x140003b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b4e  cmp     word ptr [rcx+48h], 0
0x140003b53  jz      short loc_140003B78
0x140003b55  mov     rcx, [rcx+40h]
0x140003b59  lea     rax, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140003b60  mov     r9d, 15h
0x140003b66  mov     qword ptr [rsp+98h+RemlockSize], rax
0x140003b6b  mov     r8d, 4
0x140003b71  mov     dl, 5
0x140003b73  call    WPP_RECORDER_SF_
0x140003b78  mov     r14, [rbx+0B8h]
0x140003b7f  lea     r8, File; File
0x140003b86  mov     rdi, [rsi+40h]
0x140003b8a  mov     r9d, 1; Line
0x140003b90  mov     rdx, rbx; Tag
0x140003b93  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x140003b9b  mov     r15d, [r14+10h]
0x140003b9f  mov     r13d, [r14+18h]
0x140003ba3  lea     r12, [rdi+98h]
0x140003baa  mov     rcx, r12; RemoveLock
0x140003bad  call    cs:__imp_IoAcquireRemoveLockEx
0x140003bb4  nop     dword ptr [rax+rax+00h]
0x140003bb9  mov     ebp, eax
0x140003bbb  test    eax, eax
0x140003bbd  jns     short loc_140003BE9
0x140003bbf  mov     rcx, rbx; Irp
0x140003bc2  call    cs:__imp_PoStartNextPowerIrp
0x140003bc9  nop     dword ptr [rax+rax+00h]
0x140003bce  xor     edx, edx; PriorityBoost
0x140003bd0  mov     [rbx+30h], ebp
0x140003bd3  mov     rcx, rbx; Irp
0x140003bd6  call    cs:__imp_IofCompleteRequest
0x140003bdd  nop     dword ptr [rax+rax+00h]
0x140003be2  mov     eax, ebp
0x140003be4  jmp     loc_140003D38
0x140003be9  xor     bpl, bpl
0x140003bec  cmp     byte ptr [r14+1], 2
0x140003bf1  jnz     short loc_140003C62
0x140003bf3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003bfa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003c01  jz      short loc_140003C3F
0x140003c03  lea     ecx, [r13-1]
0x140003c07  test    r15d, r15d
0x140003c0a  mov     [rsp+98h+var_58], ecx
0x140003c0e  lea     rdx, aD; "D"
0x140003c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c1c  lea     rax, aS; "S"
0x140003c23  cmovnz  rax, rdx
0x140003c27  mov     [rsp+98h+var_60], rax
0x140003c2c  mov     qword ptr [rsp+98h+InvokeOnCancel], rbx
0x140003c31  mov     rcx, [rcx+40h]
0x140003c35  mov     qword ptr [rsp+98h+InvokeOnError], rsi
0x140003c3a  call    WPP_RECORDER_SF_qqsd
0x140003c3f  cmp     r15d, 1
0x140003c43  jnz     short loc_140003C62
0x140003c45  cmp     [rdi+5Ah], bpl
0x140003c49  jz      short loc_140003C5E
0x140003c4b  cmp     [rdi+18h], r15d
0x140003c4f  jnz     short loc_140003C5E
0x140003c51  cmp     r13d, r15d
0x140003c54  movzx   ebp, bpl
0x140003c58  mov     eax, r15d
0x140003c5b  cmovg   ebp, eax
0x140003c5e  mov     [rdi+18h], r13d
0x140003c62  mov     rcx, rbx; Irp
0x140003c65  call    cs:__imp_PoStartNextPowerIrp
0x140003c6c  nop     dword ptr [rax+rax+00h]
0x140003c71  mov     rax, [rbx+0B8h]
0x140003c78  mov     rdx, rbx; Irp
0x140003c7b  test    bpl, bpl
0x140003c7e  jz      short loc_140003CFE
0x140003c80  movups  xmm0, xmmword ptr [rax]
0x140003c83  mov     [rsp+98h+InvokeOnCancel], 1; InvokeOnCancel
0x140003c88  lea     rsi, KbdHid_PowerCompletion
0x140003c8f  mov     [rsp+98h+InvokeOnError], 1; InvokeOnError
0x140003c94  mov     r9, rdi; Context
0x140003c97  movups  xmmword ptr [rax-48h], xmm0
0x140003c9b  mov     r8, rsi; CompletionRoutine
0x140003c9e  mov     byte ptr [rsp+98h+RemlockSize], 1; InvokeOnSuccess
0x140003ca3  movups  xmm1, xmmword ptr [rax+10h]
0x140003ca7  movups  xmmword ptr [rax-38h], xmm1
0x140003cab  movups  xmm0, xmmword ptr [rax+20h]
0x140003caf  movups  xmmword ptr [rax-28h], xmm0
0x140003cb3  movsd   xmm1, qword ptr [rax+30h]
0x140003cb8  movsd   qword ptr [rax-18h], xmm1
0x140003cbd  mov     byte ptr [rax-45h], 0
0x140003cc1  mov     rcx, [rdi]; DeviceObject
0x140003cc4  call    cs:__imp_IoSetCompletionRoutineEx
0x140003ccb  nop     dword ptr [rax+rax+00h]
0x140003cd0  test    eax, eax
0x140003cd2  jns     short loc_140003CE7
0x140003cd4  mov     rax, [rbx+0B8h]
0x140003cdb  mov     [rax-10h], rsi
0x140003cdf  mov     [rax-8], rdi
0x140003ce3  mov     byte ptr [rax-45h], 0E0h
0x140003ce7  mov     rcx, [rdi+8]; DeviceObject
0x140003ceb  mov     rdx, rbx; Irp
0x140003cee  call    cs:__imp_PoCallDriver
0x140003cf5  nop     dword ptr [rax+rax+00h]
0x140003cfa  mov     edi, eax
0x140003cfc  jmp     short loc_140003D36
0x140003cfe  inc     byte ptr [rbx+43h]
0x140003d01  add     rax, 48h ; 'H'
0x140003d05  mov     [rbx+0B8h], rax
0x140003d0c  mov     rcx, [rdi+8]; DeviceObject
0x140003d10  call    cs:__imp_PoCallDriver
0x140003d17  nop     dword ptr [rax+rax+00h]
0x140003d1c  mov     r8d, 20h ; ' '; RemlockSize
0x140003d22  mov     rdx, rbx; Tag
0x140003d25  mov     rcx, r12; RemoveLock
0x140003d28  mov     edi, eax
0x140003d2a  call    cs:__imp_IoReleaseRemoveLockEx
0x140003d31  nop     dword ptr [rax+rax+00h]
0x140003d36  mov     eax, edi
0x140003d38  add     rsp, 58h
0x140003d3c  pop     r15
0x140003d3e  pop     r14
0x140003d40  pop     r13
0x140003d42  pop     r12
0x140003d44  pop     rdi
0x140003d45  pop     rsi
0x140003d46  pop     rbp
0x140003d47  pop     rbx
0x140003d48  retn
```
