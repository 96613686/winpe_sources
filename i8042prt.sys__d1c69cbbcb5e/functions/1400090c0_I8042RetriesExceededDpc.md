# I8042RetriesExceededDpc

- ea: `0x1400090c0`
- end: `0x1400092c2`
- name: `I8042RetriesExceededDpc`
- size: `514`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x140007f30`
- `0x1400090c0`
- `0x140009ba4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009158`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400092b1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009158`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400092b1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140009250`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140009250`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000922b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000922b`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000913b`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000913b`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400091e6`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400091e6`

## pseudocode

```c
void __fastcall I8042RetriesExceededDpc(
        struct _KDPC *Dpc,
        struct _DEVICE_OBJECT *DeferredContext,
        _DWORD *SystemArgument1,
        PVOID SystemArgument2)
{
  _DWORD *DeviceExtension; // rdi
  unsigned int v7; // esi
  _WORD *ErrorLogEntry; // rbx
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  void *v14; // rcx
  int v15; // r8d
  int v16; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)DeferredContext,
      7,
      59,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  DeviceExtension = DeferredContext->DeviceExtension;
  SystemArgument1[12] = -1073741643;
  if ( HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) == 1 )
  {
    v7 = DeviceExtension[131];
    if ( v7 > 0x30 )
      v7 = 48;
    ErrorLogEntry = IoAllocateErrorLogEntry(DeferredContext, 4 * ((unsigned __int8)v7 + 12));
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 184LL));
    if ( ErrorLogEntry )
    {
      v9 = -(*((_BYTE *)DeviceExtension + 565) != 0);
      ErrorLogEntry[1] = 4 * v7;
      *((_DWORD *)ErrorLogEntry + 3) = (v9 & 0xFFFFFFE5) - 1073414091;
      *((_DWORD *)ErrorLogEntry + 6) = DeviceExtension[106];
      v10 = *((_QWORD *)SystemArgument1 + 23);
      *(_BYTE *)ErrorLogEntry = *(_BYTE *)v10;
      *((_DWORD *)ErrorLogEntry + 7) = *(_DWORD *)(v10 + 24);
      *((_BYTE *)ErrorLogEntry + 1) = *((_BYTE *)DeviceExtension + 560);
      *((_DWORD *)ErrorLogEntry + 4) = 1210;
      *((_DWORD *)ErrorLogEntry + 5) = SystemArgument1[12];
      if ( v7 )
      {
        v11 = 0;
        do
        {
          *(_DWORD *)&ErrorLogEntry[2 * v11 + 20] = *(unsigned __int8 *)(v11 + *((_QWORD *)DeviceExtension + 64));
          v11 = (unsigned int)(v11 + 1);
        }
        while ( (unsigned int)v11 < v7 );
      }
      IoWriteErrorLogEntry(ErrorLogEntry);
      LOBYTE(v12) = *((_BYTE *)ErrorLogEntry + 1);
      LOBYTE(v13) = *(_BYTE *)ErrorLogEntry;
      TraceLoggingRetriesExceeded(*((unsigned int *)ErrorLogEntry + 5), v13, *((unsigned int *)ErrorLogEntry + 7), v12);
    }
  }
  else
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 184LL));
  }
  v14 = (void *)*((_QWORD *)DeviceExtension + 64);
  if ( v14 && v14 != (void *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 200LL) )
    ExFreePoolWithTag(v14, 0);
  *((_QWORD *)DeviceExtension + 64) = 0;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 184LL));
  I8xCompletePendedRequest(DeferredContext, SystemArgument1, v15, -1073741643);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      7,
      60,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
}

```

## disassembly

```asm
0x1400090c0  push    rbx
0x1400090c2  push    rbp
0x1400090c3  push    rsi
0x1400090c4  push    rdi
0x1400090c5  push    r12
0x1400090c7  push    r14
0x1400090c9  sub     rsp, 38h
0x1400090cd  mov     r14, r8
0x1400090d0  mov     rbp, rdx
0x1400090d3  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400090da  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400090e1  lea     r12, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x1400090e8  jz      short loc_140009109
0x1400090ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400090f1  mov     r9d, 3Bh ; ';'
0x1400090f7  mov     [rsp+68h+var_48], r12
0x1400090fc  mov     rcx, [rcx+40h]
0x140009100  lea     r8d, [r9-34h]
0x140009104  call    WPP_RECORDER_SF_
0x140009109  mov     rdi, [rbp+40h]
0x14000910d  mov     dword ptr [r14+30h], 0C00000B5h
0x140009115  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 1
0x14000911c  jnz     loc_1400092A3
0x140009122  mov     esi, [rdi+20Ch]
0x140009128  mov     eax, 30h ; '0'
0x14000912d  cmp     esi, eax
0x14000912f  mov     rcx, rbp; IoObject
0x140009132  cmova   esi, eax
0x140009135  lea     edx, [rsi+0Ch]
0x140009138  shl     dl, 2; EntrySize
0x14000913b  call    cs:__imp_IoAllocateErrorLogEntry
0x140009142  nop     dword ptr [rax+rax+00h]
0x140009147  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000914e  mov     rbx, rax
0x140009151  add     rcx, 0B8h; SpinLock
0x140009158  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000915f  nop     dword ptr [rax+rax+00h]
0x140009164  test    rbx, rbx
0x140009167  jz      loc_140009204
0x14000916d  mov     al, [rdi+235h]
0x140009173  neg     al
0x140009175  movzx   eax, si
0x140009178  sbb     ecx, ecx
0x14000917a  shl     ax, 2
0x14000917e  mov     [rbx+2], ax
0x140009182  and     ecx, 0FFFFFFE5h
0x140009185  add     ecx, 0C0050035h
0x14000918b  mov     [rbx+0Ch], ecx
0x14000918e  mov     eax, [rdi+1A8h]
0x140009194  mov     [rbx+18h], eax
0x140009197  mov     rcx, [r14+0B8h]
0x14000919e  mov     al, [rcx]
0x1400091a0  mov     [rbx], al
0x1400091a2  mov     eax, [rcx+18h]
0x1400091a5  mov     [rbx+1Ch], eax
0x1400091a8  mov     al, [rdi+230h]
0x1400091ae  mov     [rbx+1], al
0x1400091b1  mov     dword ptr [rbx+10h], 4BAh
0x1400091b8  mov     eax, [r14+30h]
0x1400091bc  mov     [rbx+14h], eax
0x1400091bf  test    esi, esi
0x1400091c1  jz      short loc_1400091E3
0x1400091c3  xor     r8d, r8d
0x1400091c6  test    esi, esi
0x1400091c8  jz      short loc_1400091E3
0x1400091ca  mov     rax, [rdi+200h]
0x1400091d1  movzx   ecx, byte ptr [r8+rax]
0x1400091d6  mov     [rbx+r8*4+28h], ecx
0x1400091db  inc     r8d
0x1400091de  cmp     r8d, esi
0x1400091e1  jb      short loc_1400091CA
0x1400091e3  mov     rcx, rbx; ElEntry
0x1400091e6  call    cs:__imp_IoWriteErrorLogEntry
0x1400091ed  nop     dword ptr [rax+rax+00h]
0x1400091f2  mov     r9b, [rbx+1]
0x1400091f6  mov     r8d, [rbx+1Ch]
0x1400091fa  mov     dl, [rbx]
0x1400091fc  mov     ecx, [rbx+14h]
0x1400091ff  call    TraceLoggingRetriesExceeded
0x140009204  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000920b  mov     rcx, [rdi+200h]; P
0x140009212  test    rcx, rcx
0x140009215  jz      short loc_140009237
0x140009217  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000921e  add     rax, 0C8h
0x140009224  cmp     rcx, rax
0x140009227  jz      short loc_140009237
0x140009229  xor     edx, edx; Tag
0x14000922b  call    cs:__imp_ExFreePoolWithTag
0x140009232  nop     dword ptr [rax+rax+00h]
0x140009237  mov     qword ptr [rdi+200h], 0
0x140009242  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140009249  add     rcx, 0B8h; SpinLock
0x140009250  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140009257  nop     dword ptr [rax+rax+00h]
0x14000925c  mov     r9d, 0C00000B5h
0x140009262  mov     rdx, r14; Tag
0x140009265  mov     rcx, rbp; DeviceObject
0x140009268  call    I8xCompletePendedRequest
0x14000926d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140009274  jz      short loc_140009295
0x140009276  mov     rcx, cs:WPP_GLOBAL_Control
0x14000927d  mov     r9d, 3Ch ; '<'
0x140009283  mov     [rsp+68h+var_48], r12
0x140009288  mov     rcx, [rcx+40h]
0x14000928c  lea     r8d, [r9-35h]
0x140009290  call    WPP_RECORDER_SF_
0x140009295  add     rsp, 38h
0x140009299  pop     r14
0x14000929b  pop     r12
0x14000929d  pop     rdi
0x14000929e  pop     rsi
0x14000929f  pop     rbp
0x1400092a0  pop     rbx
0x1400092a1  retn
0x1400092a3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400092aa  add     rcx, 0B8h; SpinLock
0x1400092b1  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400092b8  nop     dword ptr [rax+rax+00h]
0x1400092bd  jmp     loc_14000920B
```
