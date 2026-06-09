# SessionConnectComplete

- ea: `0x1400174a8`
- end: `0x1400176fe`
- name: `SessionConnectComplete`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d370`

## callees

- `0x140003818`
- `0x140003bf4`
- `0x14001552c`
- `0x1400157dc`
- `0x140015b04`
- `0x1400174a8`
- `0x140017db4`
- `0x140018bd0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400174fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400174fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017630`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017672`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017630`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017672`

## pseudocode

```c
__int64 __fastcall SessionConnectComplete(__int64 a1, __int64 a2)
{
  unsigned int v4; // esi
  char v5; // bp
  char v6; // al
  KIRQL v7; // dl
  KSPIN_LOCK *v8; // rcx
  int v9; // edx
  int v10; // r14d
  int v11; // eax
  __int64 v12; // r8
  int v13; // r9d
  signed int v14; // eax

  v4 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      16,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_BYTE *)(a1 + 272) = *(_WORD *)(a2 + 22) != 531;
  *(_DWORD *)(a1 + 476) = *(_DWORD *)(a2 + 124);
  _InterlockedExchange64((volatile __int64 *)(a1 + 280), *(_QWORD *)(a2 + 112));
  *(_OWORD *)(a1 + 384) = *(_OWORD *)(a2 + 376);
  *(_OWORD *)(a1 + 400) = *(_OWORD *)(a2 + 392);
  *(_OWORD *)(a1 + 416) = *(_OWORD *)(a2 + 408);
  *(_OWORD *)(a1 + 432) = *(_OWORD *)(a2 + 424);
  *(_OWORD *)(a1 + 448) = *(_OWORD *)(a2 + 440);
  *(_OWORD *)(a1 + 304) = *(_OWORD *)(a2 + 288);
  *(_OWORD *)(a1 + 320) = *(_OWORD *)(a2 + 304);
  *(_OWORD *)(a1 + 336) = *(_OWORD *)(a2 + 320);
  *(_OWORD *)(a1 + 352) = *(_OWORD *)(a2 + 336);
  *(_OWORD *)(a1 + 368) = *(_OWORD *)(a2 + 352);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qdDdD(
      WPP_GLOBAL_Control->DeviceExtension,
      *(unsigned __int8 *)(a1 + 430),
      *(unsigned __int16 *)(a1 + 388),
      17);
  v5 = *(_BYTE *)(a1 + 272);
  v6 = RfcommSetState(a1, 3 - (v5 != 0));
  v7 = *(_BYTE *)(a1 + 64);
  v8 = (KSPIN_LOCK *)(a1 + 56);
  if ( v6 )
  {
    v10 = *(_DWORD *)(a1 + 48);
    v11 = 3;
    if ( *(_BYTE *)(a1 + 350) != 3 )
      v11 = 1;
    *(_DWORD *)(a1 + 296) = v11;
    KeReleaseSpinLock(v8, v7);
    if ( !v5 )
      RfcommStartTimer(*(_QWORD *)(a1 + 72));
    RfcommStartRead((_QWORD *)a1, 0, v12, v13);
    if ( v10 == 2 )
    {
      v14 = RfcommSendSABM(a1, 0);
      v4 = v14;
      if ( v14 < 0 )
        SessionDisconnectInd(a1, 1, v14, 1);
    }
  }
  else
  {
    KeReleaseSpinLock(v8, v7);
    SessionDisconnectInd(a1, 1, 0xC00000C4, 1);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      18,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x1400174a8  push    rbx
0x1400174aa  push    rbp
0x1400174ab  push    rsi
0x1400174ac  push    rdi
0x1400174ad  push    r13
0x1400174af  push    r14
0x1400174b1  push    r15
0x1400174b3  sub     rsp, 50h
0x1400174b7  mov     rdi, rdx
0x1400174ba  mov     rbx, rcx
0x1400174bd  xor     esi, esi
0x1400174bf  lea     r13, WPP_RECORDER_INITIALIZED
0x1400174c6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400174cd  lea     r14, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400174d4  jz      short loc_1400174F3
0x1400174d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174dd  lea     r9d, [rsi+10h]
0x1400174e1  lea     r8d, [rsi+3]
0x1400174e5  mov     [rsp+88h+var_68], r14
0x1400174ea  mov     rcx, [rcx+40h]
0x1400174ee  call    WPP_RECORDER_SF_
0x1400174f3  lea     r15, [rbx+38h]
0x1400174f7  mov     rcx, r15; SpinLock
0x1400174fa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017501  nop     dword ptr [rax+rax+00h]
0x140017506  mov     [rbx+40h], al
0x140017509  mov     eax, 213h
0x14001750e  cmp     [rdi+16h], ax
0x140017512  setnz   al
0x140017515  mov     [rbx+110h], al
0x14001751b  mov     eax, [rdi+7Ch]
0x14001751e  mov     [rbx+1DCh], eax
0x140017524  mov     rax, [rdi+70h]
0x140017528  xchg    rax, [rbx+118h]
0x14001752f  movups  xmm0, xmmword ptr [rdi+178h]
0x140017536  movups  xmmword ptr [rbx+180h], xmm0
0x14001753d  movups  xmm1, xmmword ptr [rdi+188h]
0x140017544  movups  xmmword ptr [rbx+190h], xmm1
0x14001754b  movups  xmm0, xmmword ptr [rdi+198h]
0x140017552  movups  xmmword ptr [rbx+1A0h], xmm0
0x140017559  movups  xmm1, xmmword ptr [rdi+1A8h]
0x140017560  movups  xmmword ptr [rbx+1B0h], xmm1
0x140017567  movups  xmm0, xmmword ptr [rdi+1B8h]
0x14001756e  movups  xmmword ptr [rbx+1C0h], xmm0
0x140017575  movups  xmm0, xmmword ptr [rdi+120h]
0x14001757c  movups  xmmword ptr [rbx+130h], xmm0
0x140017583  movups  xmm1, xmmword ptr [rdi+130h]
0x14001758a  movups  xmmword ptr [rbx+140h], xmm1
0x140017591  movups  xmm0, xmmword ptr [rdi+140h]
0x140017598  movups  xmmword ptr [rbx+150h], xmm0
0x14001759f  movups  xmm1, xmmword ptr [rdi+150h]
0x1400175a6  movups  xmmword ptr [rbx+160h], xmm1
0x1400175ad  movups  xmm0, xmmword ptr [rdi+160h]
0x1400175b4  movups  xmmword ptr [rbx+170h], xmm0
0x1400175bb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400175c2  jz      short loc_14001760D
0x1400175c4  movzx   ecx, word ptr [rbx+134h]
0x1400175cb  mov     r9d, 11h
0x1400175d1  movzx   eax, byte ptr [rbx+15Eh]
0x1400175d8  movzx   edx, byte ptr [rbx+1AEh]
0x1400175df  movzx   r8d, word ptr [rbx+184h]
0x1400175e7  mov     [rsp+88h+var_40], eax
0x1400175eb  mov     [rsp+88h+var_48], ecx
0x1400175ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175f6  mov     [rsp+88h+var_50], edx
0x1400175fa  mov     [rsp+88h+var_58], r8d
0x1400175ff  mov     [rsp+88h+var_60], rbx
0x140017604  mov     rcx, [rcx+40h]
0x140017608  call    WPP_RECORDER_SF_qdDdD
0x14001760d  mov     bpl, [rbx+110h]
0x140017614  mov     rcx, rbx
0x140017617  mov     al, bpl
0x14001761a  neg     al
0x14001761c  sbb     edx, edx
0x14001761e  add     edx, 3
0x140017621  call    RfcommSetState
0x140017626  mov     dl, [rbx+40h]; NewIrql
0x140017629  mov     rcx, r15; SpinLock
0x14001762c  test    al, al
0x14001762e  jnz     short loc_140017657
0x140017630  call    cs:__imp_KeReleaseSpinLock
0x140017637  nop     dword ptr [rax+rax+00h]
0x14001763c  mov     edi, 1
0x140017641  mov     r8d, 0C00000C4h
0x140017647  mov     r9b, dil
0x14001764a  mov     dl, dil
0x14001764d  mov     rcx, rbx
0x140017650  call    SessionDisconnectInd
0x140017655  jmp     short loc_1400176C4
0x140017657  mov     r14d, [rbx+30h]
0x14001765b  mov     eax, 3
0x140017660  cmp     [rbx+15Eh], al
0x140017666  lea     edi, [rax-2]
0x140017669  cmovnz  eax, edi
0x14001766c  mov     [rbx+128h], eax
0x140017672  call    cs:__imp_KeReleaseSpinLock
0x140017679  nop     dword ptr [rax+rax+00h]
0x14001767e  test    bpl, bpl
0x140017681  jnz     short loc_14001768C
0x140017683  mov     rcx, [rbx+48h]
0x140017687  call    RfcommStartTimer
0x14001768c  xor     edx, edx
0x14001768e  mov     rcx, rbx
0x140017691  call    RfcommStartRead
0x140017696  cmp     r14d, 2
0x14001769a  jnz     short loc_1400176BD
0x14001769c  xor     edx, edx
0x14001769e  mov     rcx, rbx
0x1400176a1  call    RfcommSendSABM
0x1400176a6  mov     esi, eax
0x1400176a8  test    eax, eax
0x1400176aa  jns     short loc_1400176BD
0x1400176ac  mov     r9b, dil
0x1400176af  mov     r8d, eax
0x1400176b2  mov     dl, dil
0x1400176b5  mov     rcx, rbx
0x1400176b8  call    SessionDisconnectInd
0x1400176bd  lea     r14, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400176c4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400176cb  jz      short loc_1400176EC
0x1400176cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176d4  mov     r9d, 12h
0x1400176da  mov     [rsp+88h+var_68], r14
0x1400176df  mov     rcx, [rcx+40h]
0x1400176e3  lea     r8d, [r9-0Fh]
0x1400176e7  call    WPP_RECORDER_SF_
0x1400176ec  mov     eax, esi
0x1400176ee  add     rsp, 50h
0x1400176f2  pop     r15
0x1400176f4  pop     r14
0x1400176f6  pop     r13
0x1400176f8  pop     rdi
0x1400176f9  pop     rsi
0x1400176fa  pop     rbp
0x1400176fb  pop     rbx
0x1400176fc  retn
```
