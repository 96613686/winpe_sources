# UxDuoExecuteUpdateStreamBundleLimits

- ea: `0x1c00150f0`
- end: `0x1c00151d5`
- name: `UxDuoExecuteUpdateStreamBundleLimits`
- size: `229`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c0014370`
- `0x1c00150f0`
- `0x1c001aed0`
- `0x1c009153c`
- `0x1c010e41c`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1c0027348`
- `ntoskrnl!IoFreeMdl` at `0x1c0027348`
- `ntoskrnl!IofCompleteRequest` at `0x1c002730f`
- `ntoskrnl!IofCompleteRequest` at `0x1c002730f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00151b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00151b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c001515a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c001515a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0015129`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0015129`

## pseudocode

```c
void __fastcall UxDuoExecuteUpdateStreamBundleLimits(_QWORD *P)
{
  __int64 v1; // rdi
  KIRQL v3; // al
  int v4; // ecx
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rcx
  IRP *v7; // rcx
  void *v8; // rcx
  struct _MDL *v9; // rcx

  v1 = P[3];
  if ( !*(_BYTE *)(v1 + 76) )
  {
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
      WPP_SF_DLd(
        20,
        WPP_e4d82b0664f433ba4e49d0d4a417570b_Traceguids,
        *(unsigned int *)(*(_QWORD *)(v1 + 32) + 824LL),
        *(unsigned int *)(v1 + 72),
        *((unsigned __int16 *)P + 29));
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(v1 + 32) + 544LL));
    if ( *(_BYTE *)(v1 + 180) )
    {
      v4 = *((unsigned __int16 *)P + 29);
      if ( (_WORD)v4 )
        *(_DWORD *)(v1 + 152) = v4;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v1 + 32) + 544LL), v3);
  }
  switch ( *((_DWORD *)P + 10) )
  {
    case 9:
      v9 = (struct _MDL *)P[6];
      if ( !v9 )
        break;
      IoFreeMdl(v9);
      goto LABEL_24;
    case 0xA:
      v8 = (void *)P[6];
      if ( !v8 )
        break;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
        UxDuoFreeDeclarePushParameters(v8);
      goto LABEL_24;
    case 0x12:
      v7 = (IRP *)P[6];
      if ( v7 )
      {
        IofCompleteRequest(v7, 0);
LABEL_24:
        P[6] = 0;
      }
      break;
  }
  v5 = P[3];
  if ( v5 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v5 + 4)) )
      UxDuoFreeStream();
    P[3] = 0;
  }
  v6 = (volatile signed __int32 *)P[4];
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 1, 0xFFFFFFFF) == 1 )
      UxDuoFreeConnection((PVOID)v6);
    P[4] = 0;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1c00150f0  mov     [rsp+arg_8], rbx
0x1c00150f5  mov     [rsp+arg_10], rsi
0x1c00150fa  push    rdi
0x1c00150fb  sub     rsp, 30h
0x1c00150ff  mov     rdi, [rcx+18h]
0x1c0015103  xor     esi, esi
0x1c0015105  mov     rbx, rcx
0x1c0015108  cmp     [rdi+4Ch], sil
0x1c001510c  jnz     short loc_1C0015166
0x1c001510e  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c0015118  jnz     loc_1C00272D2
0x1c001511e  mov     rcx, [rdi+20h]
0x1c0015122  add     rcx, 220h; SpinLock
0x1c0015129  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c0015130  nop     dword ptr [rax+rax+00h]
0x1c0015135  cmp     [rdi+0B4h], sil
0x1c001513c  jz      short loc_1C001514D
0x1c001513e  movzx   ecx, word ptr [rbx+3Ah]
0x1c0015142  test    cx, cx
0x1c0015145  jz      short loc_1C001514D
0x1c0015147  mov     [rdi+98h], ecx
0x1c001514d  mov     rcx, [rdi+20h]
0x1c0015151  mov     dl, al; NewIrql
0x1c0015153  add     rcx, 220h; SpinLock
0x1c001515a  call    cs:__imp_KeReleaseSpinLock
0x1c0015161  nop     dword ptr [rax+rax+00h]
0x1c0015166  mov     ecx, [rbx+28h]
0x1c0015169  or      edi, 0FFFFFFFFh
0x1c001516c  sub     ecx, 9
0x1c001516f  jz      loc_1C002733B
0x1c0015175  sub     ecx, 1
0x1c0015178  jz      loc_1C002731D
0x1c001517e  cmp     ecx, 8
0x1c0015181  jz      loc_1C0027300
0x1c0015187  mov     rcx, [rbx+18h]
0x1c001518b  test    rcx, rcx
0x1c001518e  jz      short loc_1C001519F
0x1c0015190  mov     eax, edi
0x1c0015192  lock xadd [rcx+4], eax
0x1c0015197  add     eax, edi
0x1c0015199  jz      short loc_1C00151CE
0x1c001519b  mov     [rbx+18h], rsi
0x1c001519f  mov     rcx, [rbx+20h]; P
0x1c00151a3  test    rcx, rcx
0x1c00151a6  jnz     loc_1C002735D
0x1c00151ac  xor     edx, edx; Tag
0x1c00151ae  mov     rcx, rbx; P
0x1c00151b1  call    cs:__imp_ExFreePoolWithTag
0x1c00151b8  nop     dword ptr [rax+rax+00h]
0x1c00151bd  mov     rbx, [rsp+38h+arg_8]
0x1c00151c2  mov     rsi, [rsp+38h+arg_10]
0x1c00151c7  add     rsp, 30h
0x1c00151cb  pop     rdi
0x1c00151cc  retn
0x1c00151ce  call    UxDuoFreeStream
0x1c00151d3  jmp     short loc_1C001519B
0x1c00272d2  mov     rdx, [rdi+20h]
0x1c00272d6  movzx   eax, word ptr [rcx+3Ah]
0x1c00272da  mov     ecx, 14h
0x1c00272df  mov     r9d, [rdi+48h]
0x1c00272e3  mov     [rsp+38h+var_18], eax
0x1c00272e7  mov     r8d, [rdx+338h]
0x1c00272ee  lea     rdx, WPP_e4d82b0664f433ba4e49d0d4a417570b_Traceguids
0x1c00272f5  call    WPP_SF_DLd
0x1c00272fa  nop
0x1c00272fb  jmp     loc_1C001511E
0x1c0027300  mov     rcx, [rbx+30h]; Irp
0x1c0027304  test    rcx, rcx
0x1c0027307  jz      loc_1C0015187
0x1c002730d  xor     edx, edx; PriorityBoost
0x1c002730f  call    cs:__imp_IofCompleteRequest
0x1c0027316  nop     dword ptr [rax+rax+00h]
0x1c002731b  jmp     short loc_1C0027354
0x1c002731d  mov     rcx, [rbx+30h]; P
0x1c0027321  test    rcx, rcx
0x1c0027324  jz      loc_1C0015187
0x1c002732a  mov     eax, edi
0x1c002732c  lock xadd [rcx], eax
0x1c0027330  add     eax, edi
0x1c0027332  jnz     short loc_1C0027354
0x1c0027334  call    UxDuoFreeDeclarePushParameters
0x1c0027339  jmp     short loc_1C0027354
0x1c002733b  mov     rcx, [rbx+30h]; Mdl
0x1c002733f  test    rcx, rcx
0x1c0027342  jz      loc_1C0015187
0x1c0027348  call    cs:__imp_IoFreeMdl
0x1c002734f  nop     dword ptr [rax+rax+00h]
0x1c0027354  mov     [rbx+30h], rsi
0x1c0027358  jmp     loc_1C0015187
0x1c002735d  mov     eax, edi
0x1c002735f  lock xadd [rcx+4], eax
0x1c0027364  add     eax, edi
0x1c0027366  jnz     short loc_1C002736D
0x1c0027368  call    UxDuoFreeConnection
0x1c002736d  mov     [rbx+20h], rsi
0x1c0027371  jmp     loc_1C00151AC
```
