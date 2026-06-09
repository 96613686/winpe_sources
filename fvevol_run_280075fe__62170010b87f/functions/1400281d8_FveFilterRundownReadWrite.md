# FveFilterRundownReadWrite

- ea: `0x1400281d8`
- end: `0x140028456`
- name: `FveFilterRundownReadWrite`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140027fb0`
- `0x1400304c0`

## callees

- `0x1400082c4`
- `0x140024040`
- `0x1400281d8`
- `0x14002845c`
- `0x140028990`
- `0x140028c84`
- `0x1400292a0`
- `0x1400293a0`
- `0x1400bf900`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002823c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002823c`
- `ntoskrnl!KeIsExecutingDpc` at `0x140028362`
- `ntoskrnl!KeIsExecutingDpc` at `0x140028362`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x140028349`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x140028349`

## pseudocode

```c
__int64 __fastcall FveFilterRundownReadWrite(__int64 a1, IRP *a2, char a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned __int64 v4; // rbp
  __int64 v5; // rdi
  unsigned int Length; // r14d
  IRP *v8; // rbx
  __int64 QuadPart; // rcx
  __int64 v10; // r8
  KIRQL CurrentIrql; // al
  int v12; // eax
  __int64 v14; // r8
  struct _IO_STACK_LOCATION *v15; // rax
  struct _KTHREAD *CurrentThread; // rcx
  int EffectivePriorityThread; // esi
  __int64 v18; // rax
  char v19; // al
  int v20; // eax
  struct _LIST_ENTRY *Flink; // [rsp+70h] [rbp+8h]
  struct _LIST_ENTRY *v22; // [rsp+70h] [rbp+8h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 64);
  Length = 0;
  v8 = a2;
  if ( CurrentStackLocation->MajorFunction != 4 && CurrentStackLocation->MajorFunction != 3 )
  {
    v10 = 3221225485LL;
    return FveFailReadWriteIrp(v5, a2, v10);
  }
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  if ( QuadPart >= 0 )
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    v4 = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  }
  v10 = 0;
  if ( QuadPart < 0 )
    v10 = 3221225485LL;
  if ( (int)v10 < 0 )
    return FveFailReadWriteIrp(v5, a2, v10);
  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
  *((_OWORD *)&a2->Tail.CompletionKey + 1) = 0;
  CurrentIrql = KeGetCurrentIrql();
  Flink = v8->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  LOBYTE(Flink) = CurrentIrql;
  v8->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = Flink;
  if ( *(_BYTE *)(v5 + 1477) )
  {
    CurrentThread = KeGetCurrentThread();
    if ( !CurrentThread )
      CurrentThread = KeGetCurrentThread();
    EffectivePriorityThread = KeQueryEffectivePriorityThread(CurrentThread);
    if ( EffectivePriorityThread >= 32 )
      EffectivePriorityThread = 18;
    if ( (unsigned int)KeIsExecutingDpc() || (unsigned int)(EffectivePriorityThread - 4) > 9 )
      LOBYTE(EffectivePriorityThread) = GetPriorityFromIrpEx(v5, (__int64)v8, 8u);
    v22 = v8->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
    BYTE3(v22) = EffectivePriorityThread;
    v8->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v22;
  }
  v12 = FvepAcquireRundownProtectionOrHold(v5, v8, 1u);
  if ( v12 == 259 )
    return 259;
  if ( v12 < 0 )
  {
    v10 = (unsigned int)v12;
    a2 = v8;
    return FveFailReadWriteIrp(v5, a2, v10);
  }
  if ( (*(_DWORD *)(v5 + 808) & 0x17F) != 0 && (*(_DWORD *)(v5 + 808) & 0x40) == 0 && *(_DWORD *)(v5 + 16) == 2 )
  {
    v15 = v8->Tail.Overlay.CurrentStackLocation;
    if ( v15->MajorFunction == 4 && v15->Parameters.Create.Options == 1178796289 )
      v15->Parameters.Create.Options = 0;
  }
  if ( (*(_DWORD *)(v5 + 808) & 0x100) == 0 )
    goto LABEL_40;
  v18 = *(_QWORD *)(v5 + 736);
  if ( !v18 )
    goto LABEL_40;
  if ( !*(_QWORD *)v18 )
    goto LABEL_40;
  v19 = *(_BYTE *)(*(_QWORD *)v18 + 48LL);
  if ( (v19 & 4) == 0 || (v19 & 3) == 0 )
    goto LABEL_40;
  v20 = FveEowFilterRundownReadWrite(v5, v8, a3, v4, Length);
  if ( v20 == 259 )
    return 259;
  if ( v20 >= 0 )
  {
LABEL_40:
    if ( !*(_DWORD *)(v5 + 1492) )
      goto LABEL_14;
    v20 = FveProtectedNoOverlapWithConvOrHold(v5, v8, v4, Length);
    if ( v20 == 259 )
      return 259;
    if ( v20 >= 0 )
    {
LABEL_14:
      FveConvUpdateUsedBitmap(*(_QWORD *)(v5 + 1496), v4, Length);
      LOBYTE(v14) = a3;
      return FveReadWrite(v5, v8, v14, v4, Length);
    }
  }
  return FveFailRundownReadWriteIrp(
           v5,
           v8,
           (unsigned int)v20,
           (unsigned __int8)BYTE1(LODWORD(v8->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink)));
}

```

## disassembly

```asm
0x1400281d8  push    rbx
0x1400281da  push    rbp
0x1400281db  push    rsi
0x1400281dc  push    rdi
0x1400281dd  push    r14
0x1400281df  push    r15
0x1400281e1  sub     rsp, 38h
0x1400281e5  mov     rax, [rdx+0B8h]
0x1400281ec  xor     ebp, ebp
0x1400281ee  mov     rdi, [rcx+40h]
0x1400281f2  xor     r14d, r14d
0x1400281f5  mov     r15b, r8b
0x1400281f8  mov     rbx, rdx
0x1400281fb  mov     cl, [rax]
0x1400281fd  cmp     cl, 4
0x140028200  jnz     loc_1400282F8
0x140028206  mov     rcx, [rax+18h]
0x14002820a  test    rcx, rcx
0x14002820d  js      short loc_140028216
0x14002820f  mov     r14d, [rax+8]
0x140028213  mov     rbp, rcx
0x140028216  xor     r8d, r8d
0x140028219  mov     eax, 0C000000Dh
0x14002821e  test    rcx, rcx
0x140028221  cmovs   r8d, eax
0x140028225  test    r8d, r8d
0x140028228  js      loc_140028307
0x14002822e  xorps   xmm0, xmm0
0x140028231  movups  xmmword ptr [rdx+78h], xmm0
0x140028235  movups  xmmword ptr [rdx+88h], xmm0
0x14002823c  call    cs:__imp_KeGetCurrentIrql
0x140028243  nop     dword ptr [rax+rax+00h]
0x140028248  mov     rcx, [rbx+78h]
0x14002824c  mov     [rsp+68h+arg_0], rcx
0x140028251  mov     byte ptr [rsp+68h+arg_0], al
0x140028255  mov     rax, [rsp+68h+arg_0]
0x14002825a  mov     [rbx+78h], rax
0x14002825e  cmp     byte ptr [rdi+5C5h], 0
0x140028265  jnz     loc_14002833B
0x14002826b  mov     r8b, 1
0x14002826e  mov     rdx, rbx
0x140028271  mov     rcx, rdi
0x140028274  call    FvepAcquireRundownProtectionOrHold
0x140028279  mov     esi, 103h
0x14002827e  cmp     eax, esi
0x140028280  jnz     short loc_140028292
0x140028282  mov     eax, esi
0x140028284  add     rsp, 38h
0x140028288  pop     r15
0x14002828a  pop     r14
0x14002828c  pop     rdi
0x14002828d  pop     rsi
0x14002828e  pop     rbp
0x14002828f  pop     rbx
0x140028290  retn
0x140028292  test    eax, eax
0x140028294  js      loc_1400283B6
0x14002829a  mov     eax, [rdi+328h]
0x1400282a0  test    eax, 17Fh
0x1400282a5  setnz   cl
0x1400282a8  test    al, 40h
0x1400282aa  setz    al
0x1400282ad  test    al, cl
0x1400282af  jnz     short loc_140028314
0x1400282b1  test    dword ptr [rdi+328h], 100h
0x1400282bb  jnz     loc_1400283C1
0x1400282c1  cmp     dword ptr [rdi+5D4h], 0
0x1400282c8  jnz     loc_140028434
0x1400282ce  mov     rcx, [rdi+5D8h]
0x1400282d5  mov     rdx, rbp
0x1400282d8  mov     r8d, r14d
0x1400282db  call    FveConvUpdateUsedBitmap
0x1400282e0  mov     r9, rbp
0x1400282e3  mov     [rsp+68h+var_48], r14d
0x1400282e8  mov     r8b, r15b
0x1400282eb  mov     rdx, rbx
0x1400282ee  mov     rcx, rdi
0x1400282f1  call    FveReadWrite
0x1400282f6  jmp     short loc_140028284
0x1400282f8  cmp     cl, 3
0x1400282fb  jz      loc_140028206
0x140028301  mov     r8d, 0C000000Dh
0x140028307  mov     rcx, rdi
0x14002830a  call    FveFailReadWriteIrp
0x14002830f  jmp     loc_140028284
0x140028314  cmp     dword ptr [rdi+10h], 2
0x140028318  jnz     short loc_1400282B1
0x14002831a  mov     rax, [rbx+0B8h]
0x140028321  cmp     byte ptr [rax], 4
0x140028324  jnz     short loc_1400282B1
0x140028326  cmp     dword ptr [rax+10h], 46430101h
0x14002832d  jnz     short loc_1400282B1
0x14002832f  mov     dword ptr [rax+10h], 0
0x140028336  jmp     loc_1400282B1
0x14002833b  mov     rcx, gs:188h
0x140028344  test    rcx, rcx
0x140028347  jz      short loc_1400283A1
0x140028349  call    cs:__imp_KeQueryEffectivePriorityThread
0x140028350  nop     dword ptr [rax+rax+00h]
0x140028355  mov     esi, eax
0x140028357  mov     eax, 12h
0x14002835c  cmp     esi, 20h ; ' '
0x14002835f  cmovge  esi, eax
0x140028362  call    cs:__imp_KeIsExecutingDpc
0x140028369  nop     dword ptr [rax+rax+00h]
0x14002836e  test    eax, eax
0x140028370  jz      short loc_1400283AC
0x140028372  mov     r8d, 8
0x140028378  mov     rdx, rbx
0x14002837b  mov     rcx, rdi
0x14002837e  call    GetPriorityFromIrpEx
0x140028383  mov     esi, eax
0x140028385  mov     rcx, [rbx+78h]
0x140028389  mov     [rsp+68h+arg_0], rcx
0x14002838e  mov     byte ptr [rsp+68h+arg_0+3], sil
0x140028393  mov     rax, [rsp+68h+arg_0]
0x140028398  mov     [rbx+78h], rax
0x14002839c  jmp     loc_14002826B
0x1400283a1  mov     rcx, gs:188h
0x1400283aa  jmp     short loc_140028349
0x1400283ac  lea     eax, [rsi-4]
0x1400283af  cmp     eax, 9
0x1400283b2  jbe     short loc_140028385
0x1400283b4  jmp     short loc_140028372
0x1400283b6  mov     r8d, eax
0x1400283b9  mov     rdx, rbx
0x1400283bc  jmp     loc_140028307
0x1400283c1  mov     rax, [rdi+2E0h]
0x1400283c8  test    rax, rax
0x1400283cb  jz      loc_1400282C1
0x1400283d1  mov     rcx, [rax]
0x1400283d4  test    rcx, rcx
0x1400283d7  jz      loc_1400282C1
0x1400283dd  mov     al, [rcx+30h]
0x1400283e0  test    al, 4
0x1400283e2  jz      loc_1400282C1
0x1400283e8  test    al, 3
0x1400283ea  jz      loc_1400282C1
0x1400283f0  mov     r9, rbp
0x1400283f3  mov     [rsp+68h+var_48], r14d
0x1400283f8  mov     r8b, r15b
0x1400283fb  mov     rdx, rbx
0x1400283fe  mov     rcx, rdi
0x140028401  call    FveEowFilterRundownReadWrite
0x140028406  cmp     eax, esi
0x140028408  jz      loc_140028282
0x14002840e  test    eax, eax
0x140028410  jns     loc_1400282C1
0x140028416  mov     ecx, [rbx+78h]
0x140028419  mov     r8d, eax
0x14002841c  shr     rcx, 8
0x140028420  mov     rdx, rbx
0x140028423  movzx   r9d, cl
0x140028427  mov     rcx, rdi
0x14002842a  call    FveFailRundownReadWriteIrp
0x14002842f  jmp     loc_140028284
0x140028434  mov     r9d, r14d
0x140028437  mov     r8, rbp
0x14002843a  mov     rdx, rbx
0x14002843d  mov     rcx, rdi
0x140028440  call    FveProtectedNoOverlapWithConvOrHold
0x140028445  cmp     eax, esi
0x140028447  jz      loc_140028282
0x14002844d  test    eax, eax
0x14002844f  js      short loc_140028416
0x140028451  jmp     loc_1400282CE
```
