# FveFilterRundownReadWrite

- ea: `0x1400291d8`
- end: `0x140029456`
- name: `FveFilterRundownReadWrite`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140028fb0`
- `0x1400314c0`

## callees

- `0x140008384`
- `0x140025040`
- `0x1400291d8`
- `0x14002945c`
- `0x140029990`
- `0x140029c84`
- `0x14002a2a0`
- `0x14002a3a0`
- `0x1400c3370`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002923c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002923c`
- `ntoskrnl!KeIsExecutingDpc` at `0x140029362`
- `ntoskrnl!KeIsExecutingDpc` at `0x140029362`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x140029349`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x140029349`

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
0x1400291d8  push    rbx
0x1400291da  push    rbp
0x1400291db  push    rsi
0x1400291dc  push    rdi
0x1400291dd  push    r14
0x1400291df  push    r15
0x1400291e1  sub     rsp, 38h
0x1400291e5  mov     rax, [rdx+0B8h]
0x1400291ec  xor     ebp, ebp
0x1400291ee  mov     rdi, [rcx+40h]
0x1400291f2  xor     r14d, r14d
0x1400291f5  mov     r15b, r8b
0x1400291f8  mov     rbx, rdx
0x1400291fb  mov     cl, [rax]
0x1400291fd  cmp     cl, 4
0x140029200  jnz     loc_1400292F8
0x140029206  mov     rcx, [rax+18h]
0x14002920a  test    rcx, rcx
0x14002920d  js      short loc_140029216
0x14002920f  mov     r14d, [rax+8]
0x140029213  mov     rbp, rcx
0x140029216  xor     r8d, r8d
0x140029219  mov     eax, 0C000000Dh
0x14002921e  test    rcx, rcx
0x140029221  cmovs   r8d, eax
0x140029225  test    r8d, r8d
0x140029228  js      loc_140029307
0x14002922e  xorps   xmm0, xmm0
0x140029231  movups  xmmword ptr [rdx+78h], xmm0
0x140029235  movups  xmmword ptr [rdx+88h], xmm0
0x14002923c  call    cs:__imp_KeGetCurrentIrql
0x140029243  nop     dword ptr [rax+rax+00h]
0x140029248  mov     rcx, [rbx+78h]
0x14002924c  mov     [rsp+68h+arg_0], rcx
0x140029251  mov     byte ptr [rsp+68h+arg_0], al
0x140029255  mov     rax, [rsp+68h+arg_0]
0x14002925a  mov     [rbx+78h], rax
0x14002925e  cmp     byte ptr [rdi+5C5h], 0
0x140029265  jnz     loc_14002933B
0x14002926b  mov     r8b, 1
0x14002926e  mov     rdx, rbx
0x140029271  mov     rcx, rdi
0x140029274  call    FvepAcquireRundownProtectionOrHold
0x140029279  mov     esi, 103h
0x14002927e  cmp     eax, esi
0x140029280  jnz     short loc_140029292
0x140029282  mov     eax, esi
0x140029284  add     rsp, 38h
0x140029288  pop     r15
0x14002928a  pop     r14
0x14002928c  pop     rdi
0x14002928d  pop     rsi
0x14002928e  pop     rbp
0x14002928f  pop     rbx
0x140029290  retn
0x140029292  test    eax, eax
0x140029294  js      loc_1400293B6
0x14002929a  mov     eax, [rdi+328h]
0x1400292a0  test    eax, 17Fh
0x1400292a5  setnz   cl
0x1400292a8  test    al, 40h
0x1400292aa  setz    al
0x1400292ad  test    al, cl
0x1400292af  jnz     short loc_140029314
0x1400292b1  test    dword ptr [rdi+328h], 100h
0x1400292bb  jnz     loc_1400293C1
0x1400292c1  cmp     dword ptr [rdi+5D4h], 0
0x1400292c8  jnz     loc_140029434
0x1400292ce  mov     rcx, [rdi+5D8h]
0x1400292d5  mov     rdx, rbp
0x1400292d8  mov     r8d, r14d
0x1400292db  call    FveConvUpdateUsedBitmap
0x1400292e0  mov     r9, rbp
0x1400292e3  mov     [rsp+68h+var_48], r14d
0x1400292e8  mov     r8b, r15b
0x1400292eb  mov     rdx, rbx
0x1400292ee  mov     rcx, rdi
0x1400292f1  call    FveReadWrite
0x1400292f6  jmp     short loc_140029284
0x1400292f8  cmp     cl, 3
0x1400292fb  jz      loc_140029206
0x140029301  mov     r8d, 0C000000Dh
0x140029307  mov     rcx, rdi
0x14002930a  call    FveFailReadWriteIrp
0x14002930f  jmp     loc_140029284
0x140029314  cmp     dword ptr [rdi+10h], 2
0x140029318  jnz     short loc_1400292B1
0x14002931a  mov     rax, [rbx+0B8h]
0x140029321  cmp     byte ptr [rax], 4
0x140029324  jnz     short loc_1400292B1
0x140029326  cmp     dword ptr [rax+10h], 46430101h
0x14002932d  jnz     short loc_1400292B1
0x14002932f  mov     dword ptr [rax+10h], 0
0x140029336  jmp     loc_1400292B1
0x14002933b  mov     rcx, gs:188h
0x140029344  test    rcx, rcx
0x140029347  jz      short loc_1400293A1
0x140029349  call    cs:__imp_KeQueryEffectivePriorityThread
0x140029350  nop     dword ptr [rax+rax+00h]
0x140029355  mov     esi, eax
0x140029357  mov     eax, 12h
0x14002935c  cmp     esi, 20h ; ' '
0x14002935f  cmovge  esi, eax
0x140029362  call    cs:__imp_KeIsExecutingDpc
0x140029369  nop     dword ptr [rax+rax+00h]
0x14002936e  test    eax, eax
0x140029370  jz      short loc_1400293AC
0x140029372  mov     r8d, 8
0x140029378  mov     rdx, rbx
0x14002937b  mov     rcx, rdi
0x14002937e  call    GetPriorityFromIrpEx
0x140029383  mov     esi, eax
0x140029385  mov     rcx, [rbx+78h]
0x140029389  mov     [rsp+68h+arg_0], rcx
0x14002938e  mov     byte ptr [rsp+68h+arg_0+3], sil
0x140029393  mov     rax, [rsp+68h+arg_0]
0x140029398  mov     [rbx+78h], rax
0x14002939c  jmp     loc_14002926B
0x1400293a1  mov     rcx, gs:188h
0x1400293aa  jmp     short loc_140029349
0x1400293ac  lea     eax, [rsi-4]
0x1400293af  cmp     eax, 9
0x1400293b2  jbe     short loc_140029385
0x1400293b4  jmp     short loc_140029372
0x1400293b6  mov     r8d, eax
0x1400293b9  mov     rdx, rbx
0x1400293bc  jmp     loc_140029307
0x1400293c1  mov     rax, [rdi+2E0h]
0x1400293c8  test    rax, rax
0x1400293cb  jz      loc_1400292C1
0x1400293d1  mov     rcx, [rax]
0x1400293d4  test    rcx, rcx
0x1400293d7  jz      loc_1400292C1
0x1400293dd  mov     al, [rcx+30h]
0x1400293e0  test    al, 4
0x1400293e2  jz      loc_1400292C1
0x1400293e8  test    al, 3
0x1400293ea  jz      loc_1400292C1
0x1400293f0  mov     r9, rbp
0x1400293f3  mov     [rsp+68h+var_48], r14d
0x1400293f8  mov     r8b, r15b
0x1400293fb  mov     rdx, rbx
0x1400293fe  mov     rcx, rdi
0x140029401  call    FveEowFilterRundownReadWrite
0x140029406  cmp     eax, esi
0x140029408  jz      loc_140029282
0x14002940e  test    eax, eax
0x140029410  jns     loc_1400292C1
0x140029416  mov     ecx, [rbx+78h]
0x140029419  mov     r8d, eax
0x14002941c  shr     rcx, 8
0x140029420  mov     rdx, rbx
0x140029423  movzx   r9d, cl
0x140029427  mov     rcx, rdi
0x14002942a  call    FveFailRundownReadWriteIrp
0x14002942f  jmp     loc_140029284
0x140029434  mov     r9d, r14d
0x140029437  mov     r8, rbp
0x14002943a  mov     rdx, rbx
0x14002943d  mov     rcx, rdi
0x140029440  call    FveProtectedNoOverlapWithConvOrHold
0x140029445  cmp     eax, esi
0x140029447  jz      loc_140029282
0x14002944d  test    eax, eax
0x14002944f  js      short loc_140029416
0x140029451  jmp     loc_1400292CE
```
