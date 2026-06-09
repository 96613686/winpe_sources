# SendControlComplete

- ea: `0x1400171e0`
- end: `0x140017323`
- name: `SendControlComplete`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001c6d0`

## callees

- `0x14000f698`
- `0x14000f898`
- `0x1400171e0`
- `0x1400181a8`
- `0x14001ac30`
- `0x14001c050`
- `0x14001c400`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400172f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400172f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001724c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001724c`

## pseudocode

```c
__int64 __fastcall SendControlComplete(__int64 a1, _QWORD *a2)
{
  __int16 v2; // ax
  int v4; // r8d
  __int64 v6; // rdi
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  void *v10; // r8
  __int64 v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h]

  v2 = *((_WORD *)a2 + 11);
  a2[9] = 0;
  if ( v2 == 14 || v2 == 4 )
  {
    v6 = a2[6];
    *(_BYTE *)(v6 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 32));
    ReferenceTunnel(v6, 0);
    v7 = *a2;
    if ( (_QWORD *)*a2 != a2 )
    {
      if ( *(_QWORD **)(v7 + 8) != a2 || (v8 = (_QWORD *)a2[1], (_QWORD *)*v8 != a2) )
        __fastfail(3u);
      *v8 = v7;
      *(_QWORD *)(v7 + 8) = v8;
      a2[1] = a2;
      *a2 = a2;
      RemoveTqi(*(_QWORD *)(v6 + 304), (_QWORD *)a2[3], 1u);
      if ( *((_WORD *)a2 + 11) == 14 )
      {
        v9 = a2[7];
        v10 = CloseCall;
      }
      else
      {
        v10 = CloseTunnel;
        v9 = 0;
      }
      ScheduleTunnelWork(v6, v9, (__int64)v10, 0, 0, v11, v12, 0);
      --*(_DWORD *)(v6 + 224);
      DereferenceControlSent(a2);
    }
    DereferenceControlSent(a2);
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 32), *(_BYTE *)(v6 + 40));
    return DereferenceTunnel(v6);
  }
  else
  {
    if ( (_QWORD *)*a2 == a2 )
      v4 = 0;
    else
      v4 = *(_DWORD *)(a2[6] + 248LL);
    return TimerQScheduleItem(*(_QWORD *)(a2[6] + 304LL), a2[3], v4, (unsigned int)&SendControlTimerEvent, (__int64)a2);
  }
}

```

## disassembly

```asm
0x1400171e0  mov     [rsp+arg_0], rbx
0x1400171e5  mov     [rsp+arg_8], rsi
0x1400171ea  push    rdi
0x1400171eb  sub     rsp, 50h
0x1400171ef  movzx   eax, word ptr [rdx+16h]
0x1400171f3  mov     rbx, rdx
0x1400171f6  mov     qword ptr [rdx+48h], 0
0x1400171fe  cmp     ax, 0Eh
0x140017202  jz      short loc_140017244
0x140017204  cmp     ax, 4
0x140017208  jz      short loc_140017244
0x14001720a  cmp     [rdx], rdx
0x14001720d  jnz     short loc_140017214
0x14001720f  xor     r8d, r8d
0x140017212  jmp     short loc_14001721F
0x140017214  mov     rax, [rdx+30h]
0x140017218  mov     r8d, [rax+0F8h]
0x14001721f  mov     rcx, [rdx+30h]
0x140017223  lea     r9, SendControlTimerEvent
0x14001722a  mov     rdx, [rdx+18h]
0x14001722e  mov     [rsp+58h+var_38], rbx
0x140017233  mov     rcx, [rcx+130h]
0x14001723a  call    TimerQScheduleItem
0x14001723f  jmp     loc_14001730B
0x140017244  mov     rdi, [rdx+30h]
0x140017248  lea     rcx, [rdi+20h]; SpinLock
0x14001724c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017253  nop     dword ptr [rax+rax+00h]
0x140017258  xor     edx, edx
0x14001725a  mov     rcx, rdi
0x14001725d  mov     [rdi+28h], al
0x140017260  call    ReferenceTunnel
0x140017265  mov     rax, [rbx]
0x140017268  cmp     rax, rbx
0x14001726b  jz      short loc_1400172E8
0x14001726d  cmp     [rax+8], rbx
0x140017271  jnz     loc_14001731C
0x140017277  mov     rcx, [rbx+8]
0x14001727b  cmp     [rcx], rbx
0x14001727e  jnz     loc_14001731C
0x140017284  mov     [rcx], rax
0x140017287  mov     r8d, 1
0x14001728d  mov     [rax+8], rcx
0x140017291  mov     [rbx+8], rbx
0x140017295  mov     [rbx], rbx
0x140017298  mov     rdx, [rbx+18h]
0x14001729c  mov     rcx, [rdi+130h]
0x1400172a3  call    RemoveTqi
0x1400172a8  xor     r9d, r9d
0x1400172ab  mov     [rsp+58h+var_20], 0
0x1400172b0  cmp     word ptr [rbx+16h], 0Eh
0x1400172b5  mov     rcx, rdi
0x1400172b8  mov     [rsp+58h+var_38], r9
0x1400172bd  jnz     short loc_1400172CC
0x1400172bf  mov     rdx, [rbx+38h]
0x1400172c3  lea     r8, CloseCall
0x1400172ca  jmp     short loc_1400172D5
0x1400172cc  lea     r8, CloseTunnel
0x1400172d3  xor     edx, edx
0x1400172d5  call    ScheduleTunnelWork
0x1400172da  dec     dword ptr [rdi+0E0h]
0x1400172e0  mov     rcx, rbx; Entry
0x1400172e3  call    DereferenceControlSent
0x1400172e8  mov     rcx, rbx; Entry
0x1400172eb  call    DereferenceControlSent
0x1400172f0  mov     dl, [rdi+28h]; NewIrql
0x1400172f3  lea     rcx, [rdi+20h]; SpinLock
0x1400172f7  call    cs:__imp_KeReleaseSpinLock
0x1400172fe  nop     dword ptr [rax+rax+00h]
0x140017303  mov     rcx, rdi
0x140017306  call    DereferenceTunnel
0x14001730b  mov     rbx, [rsp+58h+arg_0]
0x140017310  mov     rsi, [rsp+58h+arg_8]
0x140017315  add     rsp, 50h
0x140017319  pop     rdi
0x14001731a  retn
0x14001731c  mov     ecx, 3
0x140017321  int     29h; Win8: RtlFailFast(ecx)
```
