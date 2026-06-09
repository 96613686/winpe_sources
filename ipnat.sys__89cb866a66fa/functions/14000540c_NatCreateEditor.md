# NatCreateEditor

- ea: `0x14000540c`
- end: `0x140005774`
- name: `NatCreateEditor`
- size: `872`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140002b38`
- `0x140015558`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140002200`
- `0x14000540c`
- `0x140006260`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140005519`
- `ntoskrnl!KeInitializeSpinLock` at `0x140005519`
- `ntoskrnl!ExAllocatePool2` at `0x14000549f`
- `ntoskrnl!ExAllocatePool2` at `0x14000549f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400055fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400055fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400055b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005671`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400055b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005671`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005587`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005587`

## pseudocode

```c
__int64 __fastcall NatCreateEditor(__int64 a1)
{
  char v2; // al
  __int64 Pool2; // rax
  _QWORD *v4; // rdi
  KIRQL v6; // si
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
  }
  v2 = *(_BYTE *)(a1 + 8);
  v9 = 0;
  if ( (v2 == 6 || v2 == 17)
    && *(_WORD *)(a1 + 10)
    && *(_DWORD *)(a1 + 12) <= 1u
    && (*(_QWORD *)(a1 + 40) || *(_QWORD *)(a1 + 48)) )
  {
    Pool2 = ExAllocatePool2(64, 96, 1165254990);
    v4 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 24));
      *((_DWORD *)v4 + 5) = 1;
      *((_DWORD *)v4 + 12) = *(_DWORD *)(a1 + 4);
      *((_DWORD *)v4 + 4) = *(unsigned __int16 *)(a1 + 10)
                          | (*(unsigned __int8 *)(a1 + 8) << 24)
                          | ((unsigned __int8)*(_DWORD *)(a1 + 12) << 16);
      v4[5] = v4 + 4;
      v4[4] = v4 + 4;
      v4[7] = *(_QWORD *)(a1 + 16);
      v4[8] = *(_QWORD *)(a1 + 24);
      v4[9] = *(_QWORD *)(a1 + 32);
      v4[10] = *(_QWORD *)(a1 + 40);
      v4[11] = *(_QWORD *)(a1 + 48);
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
      if ( NatLookupEditor(*((unsigned int *)v4 + 4), &v9) )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue, v6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids,
            *(unsigned __int8 *)(a1 + 8),
            *(unsigned __int16 *)(a1 + 10));
        }
        ExFreePoolWithTag(v4, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids,
            3221225473LL);
        }
        return 3221225473LL;
      }
      else
      {
        v7 = v9;
        v8 = *(_QWORD **)(v9 + 8);
        if ( *v8 != v9 )
          __fastfail(3u);
        v4[1] = v8;
        *v4 = v7;
        *v8 = v4;
        *(_QWORD *)(v7 + 8) = v4;
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue, v6);
        _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
        *(_QWORD *)(a1 + 56) = v4;
        *(_QWORD *)(a1 + 64) = NatEditorCreateTicket;
        *(_QWORD *)(a1 + 72) = NatEditorDeleteTicket;
        *(_QWORD *)(a1 + 80) = NatEditorDeregister;
        *(_QWORD *)(a1 + 88) = NatEditorDissociateSession;
        *(_QWORD *)(a1 + 96) = NatEditorEditSession;
        *(_QWORD *)(a1 + 104) = NatEditorQueryInfoSession;
        *(_QWORD *)(a1 + 112) = NatEditorTimeoutSession;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids, 0);
        }
        return 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids,
            3221225485LL);
        }
      }
      return 3221225495LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids, 3221225485LL);
      }
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000540c  push    rbx
0x14000540e  push    rsi
0x14000540f  push    rdi
0x140005410  push    r13
0x140005412  push    r14
0x140005414  push    r15
0x140005416  sub     rsp, 38h
0x14000541a  mov     rbx, rcx
0x14000541d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005424  lea     r15, WPP_GLOBAL_Control
0x14000542b  lea     r14, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x140005432  cmp     rcx, r15
0x140005435  jz      short loc_140005455
0x140005437  mov     eax, [rcx+2Ch]
0x14000543a  test    al, 1
0x14000543c  jz      short loc_140005455
0x14000543e  cmp     byte ptr [rcx+29h], 6
0x140005442  jb      short loc_140005455
0x140005444  mov     rcx, [rcx+18h]
0x140005448  mov     edx, 0Ch
0x14000544d  mov     r8, r14
0x140005450  call    WPP_SF_
0x140005455  mov     al, [rbx+8]
0x140005458  xor     r13d, r13d
0x14000545b  mov     [rsp+68h+arg_0], r13
0x140005460  cmp     al, 6
0x140005462  jz      short loc_14000546C
0x140005464  cmp     al, 11h
0x140005466  jnz     loc_140005706
0x14000546c  cmp     [rbx+0Ah], r13w
0x140005471  jz      loc_140005706
0x140005477  cmp     dword ptr [rbx+0Ch], 1
0x14000547b  ja      loc_140005706
0x140005481  cmp     [rbx+28h], r13
0x140005485  jnz     short loc_140005491
0x140005487  cmp     [rbx+30h], r13
0x14000548b  jz      loc_140005706
0x140005491  mov     edx, 60h ; '`'
0x140005496  mov     r8d, 4574614Eh
0x14000549c  lea     ecx, [rdx-20h]
0x14000549f  call    cs:__imp_ExAllocatePool2
0x1400054a6  nop     dword ptr [rax+rax+00h]
0x1400054ab  mov     rdi, rax
0x1400054ae  test    rax, rax
0x1400054b1  jnz     short loc_140005515
0x1400054b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054ba  cmp     rcx, r15
0x1400054bd  jz      short loc_14000550B
0x1400054bf  mov     eax, [rcx+2Ch]
0x1400054c2  test    al, 1
0x1400054c4  jz      short loc_1400054DB
0x1400054c6  cmp     byte ptr [rcx+29h], 2
0x1400054ca  jb      short loc_1400054DB
0x1400054cc  mov     rcx, [rcx+18h]
0x1400054d0  lea     edx, [rdi+0Fh]
0x1400054d3  mov     r8, r14
0x1400054d6  call    WPP_SF_
0x1400054db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054e2  cmp     rcx, r15
0x1400054e5  jz      short loc_14000550B
0x1400054e7  mov     eax, [rcx+2Ch]
0x1400054ea  test    al, 1
0x1400054ec  jz      short loc_14000550B
0x1400054ee  cmp     byte ptr [rcx+29h], 6
0x1400054f2  jb      short loc_14000550B
0x1400054f4  mov     rcx, [rcx+18h]
0x1400054f8  mov     edx, 10h
0x1400054fd  mov     r9d, 0C000000Dh
0x140005503  mov     r8, r14
0x140005506  call    WPP_SF_d
0x14000550b  mov     eax, 0C0000017h
0x140005510  jmp     loc_140005765
0x140005515  lea     rcx, [rax+18h]; SpinLock
0x140005519  call    cs:__imp_KeInitializeSpinLock
0x140005520  nop     dword ptr [rax+rax+00h]
0x140005525  mov     dword ptr [rdi+14h], 1
0x14000552c  mov     eax, [rbx+4]
0x14000552f  mov     [rdi+30h], eax
0x140005532  mov     eax, [rbx+0Ch]
0x140005535  movzx   ecx, al
0x140005538  movzx   eax, byte ptr [rbx+8]
0x14000553c  shl     eax, 18h
0x14000553f  shl     ecx, 10h
0x140005542  or      ecx, eax
0x140005544  movzx   eax, word ptr [rbx+0Ah]
0x140005548  or      ecx, eax
0x14000554a  lea     rax, [rdi+20h]
0x14000554e  mov     [rdi+10h], ecx
0x140005551  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x140005558  mov     [rax+8], rax
0x14000555c  mov     [rax], rax
0x14000555f  mov     rax, [rbx+10h]
0x140005563  mov     [rdi+38h], rax
0x140005567  mov     rax, [rbx+18h]
0x14000556b  mov     [rdi+40h], rax
0x14000556f  mov     rax, [rbx+20h]
0x140005573  mov     [rdi+48h], rax
0x140005577  mov     rax, [rbx+28h]
0x14000557b  mov     [rdi+50h], rax
0x14000557f  mov     rax, [rbx+30h]
0x140005583  mov     [rdi+58h], rax
0x140005587  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000558e  nop     dword ptr [rax+rax+00h]
0x140005593  mov     ecx, [rdi+10h]
0x140005596  lea     rdx, [rsp+68h+arg_0]
0x14000559b  mov     sil, al
0x14000559e  call    NatLookupEditor
0x1400055a3  test    rax, rax
0x1400055a6  jz      loc_140005644
0x1400055ac  mov     dl, sil; NewIrql
0x1400055af  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x1400055b6  call    cs:__imp_KeReleaseSpinLock
0x1400055bd  nop     dword ptr [rax+rax+00h]
0x1400055c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055c9  cmp     rcx, r15
0x1400055cc  jz      short loc_1400055F9
0x1400055ce  mov     eax, [rcx+2Ch]
0x1400055d1  test    al, 1
0x1400055d3  jz      short loc_1400055F9
0x1400055d5  cmp     byte ptr [rcx+29h], 2
0x1400055d9  jb      short loc_1400055F9
0x1400055db  movzx   eax, word ptr [rbx+0Ah]
0x1400055df  mov     edx, 11h
0x1400055e4  movzx   r9d, byte ptr [rbx+8]
0x1400055e9  mov     r8, r14
0x1400055ec  mov     rcx, [rcx+18h]
0x1400055f0  mov     [rsp+68h+var_48], eax
0x1400055f4  call    WPP_SF_dd
0x1400055f9  xor     edx, edx; Tag
0x1400055fb  mov     rcx, rdi; P
0x1400055fe  call    cs:__imp_ExFreePoolWithTag
0x140005605  nop     dword ptr [rax+rax+00h]
0x14000560a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005611  mov     ebx, 0C0000001h
0x140005616  cmp     rcx, r15
0x140005619  jz      short loc_14000563D
0x14000561b  mov     edx, [rcx+2Ch]
0x14000561e  test    dl, 1
0x140005621  jz      short loc_14000563D
0x140005623  cmp     byte ptr [rcx+29h], 6
0x140005627  jb      short loc_14000563D
0x140005629  mov     rcx, [rcx+18h]
0x14000562d  mov     edx, 12h
0x140005632  mov     r9d, ebx
0x140005635  mov     r8, r14
0x140005638  call    WPP_SF_d
0x14000563d  mov     eax, ebx
0x14000563f  jmp     loc_140005765
0x140005644  mov     rax, [rsp+68h+arg_0]
0x140005649  mov     rcx, [rax+8]
0x14000564d  cmp     [rcx], rax
0x140005650  jz      short loc_140005659
0x140005652  mov     ecx, 3
0x140005657  int     29h; Win8: RtlFailFast(ecx)
0x140005659  mov     [rdi+8], rcx
0x14000565d  mov     dl, sil; NewIrql
0x140005660  mov     [rdi], rax
0x140005663  mov     [rcx], rdi
0x140005666  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000566d  mov     [rax+8], rdi
0x140005671  call    cs:__imp_KeReleaseSpinLock
0x140005678  nop     dword ptr [rax+rax+00h]
0x14000567d  lock inc dword ptr cs:WPP_MAIN_CB.Queue+38h
0x140005684  lea     rax, NatEditorCreateTicket
0x14000568b  mov     [rbx+38h], rdi
0x14000568f  mov     [rbx+40h], rax
0x140005693  lea     rax, NatEditorDeleteTicket
0x14000569a  mov     [rbx+48h], rax
0x14000569e  lea     rax, NatEditorDeregister
0x1400056a5  mov     [rbx+50h], rax
0x1400056a9  lea     rax, NatEditorDissociateSession
0x1400056b0  mov     [rbx+58h], rax
0x1400056b4  lea     rax, NatEditorEditSession
0x1400056bb  mov     [rbx+60h], rax
0x1400056bf  lea     rax, NatEditorQueryInfoSession
0x1400056c6  mov     [rbx+68h], rax
0x1400056ca  lea     rax, NatEditorTimeoutSession
0x1400056d1  mov     [rbx+70h], rax
0x1400056d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400056dc  cmp     rcx, r15
0x1400056df  jz      short loc_140005702
0x1400056e1  mov     eax, [rcx+2Ch]
0x1400056e4  test    al, 1
0x1400056e6  jz      short loc_140005702
0x1400056e8  cmp     byte ptr [rcx+29h], 6
0x1400056ec  jb      short loc_140005702
0x1400056ee  mov     rcx, [rcx+18h]
0x1400056f2  mov     edx, 13h
0x1400056f7  xor     r9d, r9d
0x1400056fa  mov     r8, r14
0x1400056fd  call    WPP_SF_d
0x140005702  xor     eax, eax
0x140005704  jmp     short loc_140005765
0x140005706  mov     rcx, cs:WPP_GLOBAL_Control
0x14000570d  cmp     rcx, r15
0x140005710  jz      short loc_140005760
0x140005712  mov     eax, [rcx+2Ch]
0x140005715  test    al, 1
0x140005717  jz      short loc_140005730
0x140005719  cmp     byte ptr [rcx+29h], 2
0x14000571d  jb      short loc_140005730
0x14000571f  mov     rcx, [rcx+18h]
0x140005723  mov     edx, 0Dh
0x140005728  mov     r8, r14
0x14000572b  call    WPP_SF_
0x140005730  mov     rcx, cs:WPP_GLOBAL_Control
0x140005737  cmp     rcx, r15
0x14000573a  jz      short loc_140005760
0x14000573c  mov     eax, [rcx+2Ch]
0x14000573f  test    al, 1
0x140005741  jz      short loc_140005760
0x140005743  cmp     byte ptr [rcx+29h], 6
0x140005747  jb      short loc_140005760
0x140005749  mov     rcx, [rcx+18h]
0x14000574d  mov     edx, 0Eh
0x140005752  mov     r9d, 0C000000Dh
0x140005758  mov     r8, r14
0x14000575b  call    WPP_SF_d
0x140005760  mov     eax, 0C000000Dh
0x140005765  add     rsp, 38h
0x140005769  pop     r15
0x14000576b  pop     r14
0x14000576d  pop     r13
0x14000576f  pop     rdi
0x140005770  pop     rsi
0x140005771  pop     rbx
0x140005772  retn
```
