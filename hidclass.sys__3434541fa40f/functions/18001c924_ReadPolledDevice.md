# ReadPolledDevice

- ea: `0x18001c924`
- end: `0x18001cab5`
- name: `ReadPolledDevice`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800053c0`
- `0x18000deb0`

## callees

- `0x18000a020`
- `0x18000cc90`
- `0x18000ddc8`
- `0x18001c924`
- `0x18001fba0`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x18001c95f`
- `ntoskrnl!IoAllocateIrp` at `0x18001c95f`
- `ntoskrnl!ExAllocatePool2` at `0x18001c988`
- `ntoskrnl!ExAllocatePool2` at `0x18001c988`

## pseudocode

```c
char __fastcall ReadPolledDevice(__int64 a1, char a2, __int64 a3)
{
  __int64 v3; // rdi
  char v6; // si
  __int64 CollectionDesc; // rbp
  __int64 v8; // rdx
  PIRP Irp; // rbx
  __int64 v10; // r8
  unsigned int v11; // ebp
  _BYTE *Pool2; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 (__fastcall *v14)(__int64, __int64, __int64); // rax
  _IO_STACK_LOCATION *v15; // rcx
  int v16; // eax
  int v17; // edx
  int v18; // r8d

  v3 = *(_QWORD *)(a1 + 64);
  v6 = 0;
  CollectionDesc = GetCollectionDesc(v3 + 32, *(unsigned int *)(a1 + 8), a3);
  if ( CollectionDesc )
  {
    Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v3 + 32) + 76LL), 0);
    if ( Irp )
    {
      v11 = *(unsigned __int16 *)(CollectionDesc + 20);
      Pool2 = (_BYTE *)ExAllocatePool2(64, v11, 1130654024);
      Irp->UserBuffer = Pool2;
      if ( Pool2 )
      {
        v6 = 1;
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        if ( !**(_BYTE **)(v3 + 208) )
        {
          *Pool2 = 0;
          ++Irp->UserBuffer;
          --v11;
        }
        CurrentStackLocation[-1].MajorFunction = 15;
        v14 = (__int64 (__fastcall *)(__int64, __int64, __int64))HidpPolledReadComplete_TimerDriven;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 720907;
        CurrentStackLocation[-1].Parameters.Read.Length = v11;
        v15 = Irp->Tail.Overlay.CurrentStackLocation;
        if ( !a2 )
          v14 = HidpPolledReadComplete;
        Irp->IoStatus.Status = -1073741637;
        v15[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))v14;
        v15[-1].Context = (void *)a1;
        v15[-1].Control = -32;
        v16 = HidpCallDriver(*(_QWORD *)(v3 + 32), Irp);
        if ( v16 < 0 )
        {
          LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v17,
              v18,
              *(_QWORD *)(v3 + 704),
              2,
              5,
              11,
              (__int64)WPP_c51b90a246f13983ca6b2f698eaa9bea_Traceguids,
              *(_QWORD *)(v3 + 32),
              v16);
          }
        }
      }
    }
    else
    {
      TraceLoggingIoAllocateIrpFailed((unsigned int)*(char *)(*(_QWORD *)(v3 + 32) + 76LL), v8, v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001c924  push    rbx
0x18001c926  push    rbp
0x18001c927  push    rsi
0x18001c928  push    rdi
0x18001c929  push    r14
0x18001c92b  push    r15
0x18001c92d  sub     rsp, 58h
0x18001c931  mov     rdi, [rcx+40h]
0x18001c935  mov     r15b, dl
0x18001c938  mov     edx, [rcx+8]
0x18001c93b  mov     r14, rcx
0x18001c93e  xor     sil, sil
0x18001c941  lea     rcx, [rdi+20h]
0x18001c945  call    GetCollectionDesc
0x18001c94a  mov     rbp, rax
0x18001c94d  test    rax, rax
0x18001c950  jz      loc_18001CAA4
0x18001c956  mov     rcx, [rdi+20h]
0x18001c95a  xor     edx, edx; ChargeQuota
0x18001c95c  mov     cl, [rcx+4Ch]; StackSize
0x18001c95f  call    cs:__imp_IoAllocateIrp
0x18001c966  nop     dword ptr [rax+rax+00h]
0x18001c96b  mov     rbx, rax
0x18001c96e  test    rax, rax
0x18001c971  jz      loc_18001CA97
0x18001c977  movzx   ebp, word ptr [rbp+14h]
0x18001c97b  mov     ecx, 40h ; '@'
0x18001c980  mov     edx, ebp
0x18001c982  mov     r8d, 43646948h
0x18001c988  call    cs:__imp_ExAllocatePool2
0x18001c98f  nop     dword ptr [rax+rax+00h]
0x18001c994  mov     [rbx+70h], rax
0x18001c998  test    rax, rax
0x18001c99b  jz      loc_18001CAA4
0x18001c9a1  mov     rcx, [rdi+0D0h]
0x18001c9a8  mov     esi, 1
0x18001c9ad  mov     rdx, [rbx+0B8h]
0x18001c9b4  cmp     byte ptr [rcx], 0
0x18001c9b7  jnz     short loc_18001C9C2
0x18001c9b9  mov     byte ptr [rax], 0
0x18001c9bc  add     [rbx+70h], rsi
0x18001c9c0  dec     ebp
0x18001c9c2  mov     byte ptr [rdx-48h], 0Fh
0x18001c9c6  lea     rax, HidpPolledReadComplete_TimerDriven
0x18001c9cd  mov     dword ptr [rdx-30h], 0B000Bh
0x18001c9d4  test    r15b, r15b
0x18001c9d7  mov     [rdx-40h], ebp
0x18001c9da  lea     rdx, HidpPolledReadComplete
0x18001c9e1  mov     rcx, [rbx+0B8h]
0x18001c9e8  cmovz   rax, rdx
0x18001c9ec  mov     dword ptr [rbx+30h], 0C00000BBh
0x18001c9f3  mov     rdx, rbx
0x18001c9f6  mov     [rcx-10h], rax
0x18001c9fa  mov     [rcx-8], r14
0x18001c9fe  mov     byte ptr [rcx-45h], 0E0h
0x18001ca02  mov     rcx, [rdi+20h]
0x18001ca06  call    HidpCallDriver
0x18001ca0b  test    eax, eax
0x18001ca0d  jns     loc_18001CAA4
0x18001ca13  mov     r10, cs:WPP_GLOBAL_Control
0x18001ca1a  lea     rcx, WPP_GLOBAL_Control
0x18001ca21  cmp     r10, rcx
0x18001ca24  jz      short loc_18001CA3B
0x18001ca26  mov     ecx, [r10+2Ch]
0x18001ca2a  test    cl, 10h
0x18001ca2d  jz      short loc_18001CA3B
0x18001ca2f  cmp     byte ptr [r10+29h], 2
0x18001ca34  jb      short loc_18001CA3B
0x18001ca36  mov     dl, sil
0x18001ca39  jmp     short loc_18001CA3D
0x18001ca3b  xor     dl, dl
0x18001ca3d  lea     rcx, WPP_RECORDER_INITIALIZED
0x18001ca44  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18001ca4b  setnz   r8b
0x18001ca4f  test    dl, dl
0x18001ca51  jnz     short loc_18001CA58
0x18001ca53  test    r8b, r8b
0x18001ca56  jz      short loc_18001CAA4
0x18001ca58  mov     r9, [rdi+2C0h]
0x18001ca5f  mov     rcx, [r10+18h]
0x18001ca63  mov     [rsp+88h+var_40], eax
0x18001ca67  mov     rax, [rdi+20h]
0x18001ca6b  mov     [rsp+88h+var_48], rax
0x18001ca70  lea     rax, WPP_c51b90a246f13983ca6b2f698eaa9bea_Traceguids
0x18001ca77  mov     [rsp+88h+var_50], rax
0x18001ca7c  mov     [rsp+88h+var_58], 0Bh
0x18001ca83  mov     [rsp+88h+var_60], 5
0x18001ca8b  mov     [rsp+88h+var_68], 2
0x18001ca90  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18001ca95  jmp     short loc_18001CAA4
0x18001ca97  mov     rcx, [rdi+20h]
0x18001ca9b  movsx   ecx, byte ptr [rcx+4Ch]
0x18001ca9f  call    TraceLoggingIoAllocateIrpFailed
0x18001caa4  mov     al, sil
0x18001caa7  add     rsp, 58h
0x18001caab  pop     r15
0x18001caad  pop     r14
0x18001caaf  pop     rdi
0x18001cab0  pop     rsi
0x18001cab1  pop     rbp
0x18001cab2  pop     rbx
0x18001cab3  retn
```
