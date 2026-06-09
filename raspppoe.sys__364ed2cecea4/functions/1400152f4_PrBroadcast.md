# PrBroadcast

- ea: `0x1400152f4`
- end: `0x140015657`
- name: `PrBroadcast`
- size: `867`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140016534`
- `0x140017740`

## callees

- `0x14000110c`
- `0x1400024dc`
- `0x140005098`
- `0x140005164`
- `0x140005234`
- `0x1400054d4`
- `0x140006b80`
- `0x140006d40`
- `0x140011cdc`
- `0x1400152f4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001560c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001560c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400153bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400153bd`

## pseudocode

```c
__int64 __fastcall PrBroadcast(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebp
  __int64 i; // rdi
  __int64 PPPoEPacket; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // r14
  __int64 v16; // r8
  __int128 v17[5]; // [rsp+30h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a1);
  }
  if ( gl_ulNumBindings )
  {
    v5 = -1073741823;
    byte_14000A1F8 = KeAcquireSpinLockRaiseToDpc(&gl_lockProtocol);
    if ( gl_ulNumBindings )
    {
      for ( i = gl_linkBindings; (__int64 *)i != &gl_linkBindings; i = *(_QWORD *)i )
      {
        if ( *(_DWORD *)(i + 400) == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x71u,
              (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
          }
          PPPoEPacket = AllocatePPPoEPacket();
          v8 = PPPoEPacket;
          if ( PPPoEPacket )
          {
            v9 = *(_QWORD *)(PPPoEPacket + 112);
            *(_DWORD *)(PPPoEPacket + 144) = *(_DWORD *)(a1 + 144);
            v10 = *(_QWORD *)(a1 + 112);
            *(_OWORD *)v9 = *(_OWORD *)v10;
            *(_DWORD *)(v9 + 16) = *(_DWORD *)(v10 + 16);
            memmove(
              *(void **)(v8 + 120),
              *(const void **)(a1 + 120),
              (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(a1 + 112) + 18LL), 8));
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 136) + 8LL) + 24LL) = (unsigned __int16)__ROR2__(
                                                                                               *(_WORD *)(*(_QWORD *)(a1 + 112) + 18LL),
                                                                                               8)
                                                                         + 20;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids, v8);
            }
            v12 = *(_DWORD *)(i + 320);
            v13 = *(_QWORD *)(v8 + 112);
            *(_QWORD *)&v17[0] = i;
            v17[1] = 0;
            *((_QWORD *)&v17[0] + 1) = v8;
            *(_DWORD *)(v13 + 6) = v12;
            *(_WORD *)(v13 + 10) = *(_WORD *)(i + 324);
            v15 = AllocWorkItem(v13, (__int64)ExecBindingWorkItem, v11, v17, 2);
            if ( v15 )
            {
              LOBYTE(v14) = 1;
              ReferenceBinding(i, v14);
              _InterlockedIncrement((volatile signed __int32 *)v8);
              ScheduleWorkItem(v15);
              v5 = 0;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(__int64))(v8 + 8))(v8);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
              WPP_SF_(
                (__int64)WPP_GLOBAL_Control->AttachedDevice,
                0x72u,
                (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids, 0);
            }
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a1);
    }
    KeReleaseSpinLock(&gl_lockProtocol, byte_14000A1F8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 90, v16, a1, v5);
    }
    return v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 88, a3, a1, -1073741823);
      }
    }
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x1400152f4  push    rbx
0x1400152f6  push    rbp
0x1400152f7  push    rsi
0x1400152f8  push    rdi
0x1400152f9  push    r12
0x1400152fb  push    r14
0x1400152fd  sub     rsp, 58h
0x140015301  mov     rsi, rcx
0x140015304  mov     rcx, cs:WPP_GLOBAL_Control
0x14001530b  lea     r12, WPP_GLOBAL_Control
0x140015312  lea     rbx, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015319  cmp     rcx, r12
0x14001531c  jz      short loc_14001533F
0x14001531e  mov     eax, [rcx+2Ch]
0x140015321  test    al, 4
0x140015323  jz      short loc_14001533F
0x140015325  cmp     byte ptr [rcx+29h], 3
0x140015329  jb      short loc_14001533F
0x14001532b  mov     rcx, [rcx+18h]
0x14001532f  mov     edx, 56h ; 'V'
0x140015334  mov     r9, rsi
0x140015337  mov     r8, rbx
0x14001533a  call    WPP_SF_q
0x14001533f  cmp     cs:gl_ulNumBindings, 0
0x140015346  jnz     short loc_1400153B1
0x140015348  mov     rcx, cs:WPP_GLOBAL_Control
0x14001534f  cmp     rcx, r12
0x140015352  jz      short loc_1400153A7
0x140015354  mov     eax, [rcx+2Ch]
0x140015357  test    al, 4
0x140015359  jz      short loc_140015375
0x14001535b  cmp     byte ptr [rcx+29h], 3
0x14001535f  jb      short loc_140015375
0x140015361  mov     rcx, [rcx+18h]
0x140015365  mov     edx, 57h ; 'W'
0x14001536a  mov     r9, rsi
0x14001536d  mov     r8, rbx
0x140015370  call    WPP_SF_q
0x140015375  mov     rcx, cs:WPP_GLOBAL_Control
0x14001537c  cmp     rcx, r12
0x14001537f  jz      short loc_1400153A7
0x140015381  mov     eax, [rcx+2Ch]
0x140015384  test    al, 4
0x140015386  jz      short loc_1400153A7
0x140015388  cmp     byte ptr [rcx+29h], 3
0x14001538c  jb      short loc_1400153A7
0x14001538e  mov     rcx, [rcx+18h]
0x140015392  mov     edx, 58h ; 'X'
0x140015397  mov     r9, rsi
0x14001539a  mov     [rsp+88h+var_68], 0C0000001h
0x1400153a2  call    WPP_SF_qD
0x1400153a7  mov     eax, 0C0000001h
0x1400153ac  jmp     loc_140015649
0x1400153b1  lea     rcx, gl_lockProtocol; SpinLock
0x1400153b8  mov     ebp, 0C0000001h
0x1400153bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400153c4  nop     dword ptr [rax+rax+00h]
0x1400153c9  cmp     cs:gl_ulNumBindings, 0
0x1400153d0  mov     cs:byte_14000A1F8, al
0x1400153d6  jnz     short loc_140015416
0x1400153d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153df  cmp     rcx, r12
0x1400153e2  jz      loc_1400155FF
0x1400153e8  mov     eax, [rcx+2Ch]
0x1400153eb  test    al, 4
0x1400153ed  jz      loc_1400155FF
0x1400153f3  cmp     byte ptr [rcx+29h], 3
0x1400153f7  jb      loc_1400155FF
0x1400153fd  mov     rcx, [rcx+18h]
0x140015401  mov     edx, 59h ; 'Y'
0x140015406  mov     r9, rsi
0x140015409  mov     r8, rbx
0x14001540c  call    WPP_SF_q
0x140015411  jmp     loc_1400155FF
0x140015416  mov     rdi, cs:gl_linkBindings
0x14001541d  lea     r14, gl_linkBindings
0x140015424  jmp     loc_1400155F6
0x140015429  cmp     dword ptr [rdi+190h], 2
0x140015430  jnz     loc_1400155F3
0x140015436  mov     rcx, cs:WPP_GLOBAL_Control
0x14001543d  cmp     rcx, r12
0x140015440  jz      short loc_140015464
0x140015442  mov     eax, [rcx+2Ch]
0x140015445  test    al, 20h
0x140015447  jz      short loc_140015464
0x140015449  cmp     byte ptr [rcx+29h], 3
0x14001544d  jb      short loc_140015464
0x14001544f  mov     rcx, [rcx+18h]
0x140015453  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x14001545a  mov     edx, 71h ; 'q'
0x14001545f  call    WPP_SF_
0x140015464  call    AllocatePPPoEPacket
0x140015469  mov     rbx, rax
0x14001546c  test    rax, rax
0x14001546f  jnz     short loc_1400154E3
0x140015471  mov     rcx, cs:WPP_GLOBAL_Control
0x140015478  cmp     rcx, r12
0x14001547b  jz      loc_1400155F3
0x140015481  mov     eax, [rcx+2Ch]
0x140015484  test    al, 20h
0x140015486  jz      short loc_1400154A1
0x140015488  cmp     byte ptr [rcx+29h], 1
0x14001548c  jb      short loc_1400154A1
0x14001548e  mov     rcx, [rcx+18h]
0x140015492  lea     edx, [rbx+72h]
0x140015495  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x14001549c  call    WPP_SF_
0x1400154a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154a8  cmp     rcx, r12
0x1400154ab  jz      loc_1400155F3
0x1400154b1  mov     eax, [rcx+2Ch]
0x1400154b4  test    al, 20h
0x1400154b6  jz      loc_1400155F3
0x1400154bc  cmp     byte ptr [rcx+29h], 3
0x1400154c0  jb      loc_1400155F3
0x1400154c6  mov     rcx, [rcx+18h]
0x1400154ca  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x1400154d1  mov     edx, 73h ; 's'
0x1400154d6  xor     r9d, r9d
0x1400154d9  call    WPP_SF_q
0x1400154de  jmp     loc_1400155F3
0x1400154e3  mov     eax, [rsi+90h]
0x1400154e9  mov     rcx, [rbx+70h]
0x1400154ed  mov     [rbx+90h], eax
0x1400154f3  mov     rax, [rsi+70h]
0x1400154f7  movups  xmm0, xmmword ptr [rax]
0x1400154fa  movups  xmmword ptr [rcx], xmm0
0x1400154fd  mov     eax, [rax+10h]
0x140015500  mov     [rcx+10h], eax
0x140015503  mov     rax, [rsi+70h]
0x140015507  mov     rdx, [rsi+78h]; Src
0x14001550b  movzx   ecx, word ptr [rax+12h]
0x14001550f  ror     cx, 8
0x140015513  movzx   r8d, cx; Size
0x140015517  mov     rcx, [rbx+78h]; void *
0x14001551b  call    memmove
0x140015520  mov     rax, [rsi+70h]
0x140015524  movzx   ecx, word ptr [rax+12h]
0x140015528  mov     rax, [rbx+88h]
0x14001552f  ror     cx, 8
0x140015533  movzx   edx, cx
0x140015536  add     edx, 14h
0x140015539  mov     rcx, [rax+8]
0x14001553d  mov     [rcx+18h], edx
0x140015540  mov     rcx, cs:WPP_GLOBAL_Control
0x140015547  cmp     rcx, r12
0x14001554a  jz      short loc_140015571
0x14001554c  mov     eax, [rcx+2Ch]
0x14001554f  test    al, 20h
0x140015551  jz      short loc_140015571
0x140015553  cmp     byte ptr [rcx+29h], 3
0x140015557  jb      short loc_140015571
0x140015559  mov     rcx, [rcx+18h]
0x14001555d  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140015564  mov     edx, 74h ; 't'
0x140015569  mov     r9, rbx
0x14001556c  call    WPP_SF_q
0x140015571  mov     eax, [rdi+140h]
0x140015577  lea     r9, [rsp+88h+var_58]
0x14001557c  mov     rcx, [rbx+70h]
0x140015580  lea     rdx, ExecBindingWorkItem
0x140015587  xorps   xmm0, xmm0
0x14001558a  mov     [rsp+88h+var_58], rdi
0x14001558f  movdqu  [rsp+88h+var_48], xmm0
0x140015595  mov     [rsp+88h+var_50], rbx
0x14001559a  mov     [rcx+6], eax
0x14001559d  movzx   eax, word ptr [rdi+144h]
0x1400155a4  mov     [rcx+0Ah], ax
0x1400155a8  mov     [rsp+88h+var_68], 2
0x1400155b0  call    AllocWorkItem
0x1400155b5  mov     r14, rax
0x1400155b8  test    rax, rax
0x1400155bb  jz      short loc_1400155D4
0x1400155bd  mov     dl, 1
0x1400155bf  mov     rcx, rdi
0x1400155c2  call    ReferenceBinding
0x1400155c7  lock inc dword ptr [rbx]
0x1400155ca  mov     rcx, r14; WorkItemContext
0x1400155cd  call    ScheduleWorkItem
0x1400155d2  xor     ebp, ebp
0x1400155d4  or      eax, 0FFFFFFFFh
0x1400155d7  lock xadd [rbx], eax
0x1400155db  cmp     eax, 1
0x1400155de  jnz     short loc_1400155EC
0x1400155e0  mov     rax, [rbx+8]
0x1400155e4  mov     rcx, rbx
0x1400155e7  call    _guard_dispatch_icall
0x1400155ec  lea     r14, gl_linkBindings
0x1400155f3  mov     rdi, [rdi]
0x1400155f6  cmp     rdi, r14
0x1400155f9  jnz     loc_140015429
0x1400155ff  mov     dl, cs:byte_14000A1F8; NewIrql
0x140015605  lea     rcx, gl_lockProtocol; SpinLock
0x14001560c  call    cs:__imp_KeReleaseSpinLock
0x140015613  nop     dword ptr [rax+rax+00h]
0x140015618  mov     rcx, cs:WPP_GLOBAL_Control
0x14001561f  cmp     rcx, r12
0x140015622  jz      short loc_140015647
0x140015624  mov     edx, [rcx+2Ch]
0x140015627  test    dl, 4
0x14001562a  jz      short loc_140015647
0x14001562c  cmp     byte ptr [rcx+29h], 3
0x140015630  jb      short loc_140015647
0x140015632  mov     rcx, [rcx+18h]
0x140015636  mov     edx, 5Ah ; 'Z'
0x14001563b  mov     r9, rsi
0x14001563e  mov     [rsp+88h+var_68], ebp
0x140015642  call    WPP_SF_qD
0x140015647  mov     eax, ebp
0x140015649  add     rsp, 58h
0x14001564d  pop     r14
0x14001564f  pop     r12
0x140015651  pop     rdi
0x140015652  pop     rsi
0x140015653  pop     rbp
0x140015654  pop     rbx
0x140015655  retn
```
