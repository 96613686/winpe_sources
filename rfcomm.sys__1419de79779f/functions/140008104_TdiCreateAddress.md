# TdiCreateAddress

- ea: `0x140008104`
- end: `0x14000832d`
- name: `TdiCreateAddress`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009cc8`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140008104`
- `0x14000bbfc`
- `0x14001e8f4`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400082dd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400082dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008154`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008154`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400081ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400081ea`
- `ntoskrnl!ExAllocatePool2` at `0x14000820a`
- `ntoskrnl!ExAllocatePool2` at `0x14000820a`
- `ntoskrnl!ObfDereferenceObject` at `0x140008233`
- `ntoskrnl!ObfDereferenceObject` at `0x140008233`
- `ntoskrnl!ObfReferenceObject` at `0x1400081ce`
- `ntoskrnl!ObfReferenceObject` at `0x1400081ce`

## string_xrefs

- `0x140008303`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiCreateAddress(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rsi
  __int64 *v7; // rdi
  KIRQL v8; // al
  __int64 *v9; // rdx
  __int64 *v10; // rax
  int v11; // ebx
  int v12; // edx
  __int64 Pool2; // rax
  _QWORD *v14; // rsi
  __int128 v16; // xmm1
  bool v17; // zf

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF__guid_d(WPP_GLOBAL_Control->DeviceExtension, a2, (_DWORD)a3, a2 + 8);
  v6 = *(_QWORD *)(a1 + 80);
  v7 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6);
  v9 = (__int64 *)(v6 + 24);
  *(_BYTE *)(v6 + 8) = v8;
  v10 = *(__int64 **)(v6 + 24);
  if ( v10 == (__int64 *)(v6 + 24) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        1,
        174,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    v11 = -1073741810;
  }
  else
  {
    if ( a2 && *(_QWORD *)a2 )
    {
      while ( *(_QWORD *)a2 != v10[15] )
      {
        v10 = (__int64 *)*v10;
        if ( v10 == v9 )
        {
          v11 = -1073741503;
          goto LABEL_13;
        }
      }
    }
    v7 = v10;
    ObfReferenceObject((PVOID)v10[10]);
    v11 = 0;
  }
LABEL_13:
  if ( v11 < 0 )
    v7 = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)v6, *(_BYTE *)(v6 + 8));
  if ( v11 >= 0 )
  {
    Pool2 = ExAllocatePool2(64, 232, 1145136722);
    v14 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 16) = 1380205633;
      *(_OWORD *)(Pool2 + 88) = *(_OWORD *)a2;
      v16 = *(_OWORD *)(a2 + 12);
      *(_QWORD *)(Pool2 + 80) = v7;
      *(_OWORD *)(Pool2 + 100) = v16;
      v17 = *(_DWORD *)(a2 + 24) == 0;
      *(_DWORD *)(Pool2 + 204) = 1;
      *(_BYTE *)(Pool2 + 136) = !v17;
      *(_DWORD *)(Pool2 + 216) = 1;
      *(_DWORD *)(Pool2 + 224) = 0;
      *(_DWORD *)(Pool2 + 220) = 0;
      KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 48));
      v14[1] = v14;
      v14[16] = v14 + 15;
      v14[15] = v14 + 15;
      *v14 = v14;
      RefObj_InitEx(
        (_DWORD)v14 + 24,
        (unsigned int)FreeAddrObject,
        1414090313,
        1343,
        (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      v11 = 0;
      *a3 = v14;
      goto LABEL_20;
    }
    v11 = -1073741670;
  }
  *a3 = 0;
  if ( v7 )
    ObfDereferenceObject((PVOID)v7[10]);
LABEL_20:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      15,
      53,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      *a3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140008104  push    rbx
0x140008106  push    rsi
0x140008107  push    rdi
0x140008108  push    r12
0x14000810a  push    r14
0x14000810c  push    r15
0x14000810e  sub     rsp, 48h
0x140008112  mov     r15, r8
0x140008115  mov     r14, rdx
0x140008118  mov     rsi, rcx
0x14000811b  lea     r12, WPP_RECORDER_INITIALIZED
0x140008122  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008129  jz      short loc_14000814B
0x14000812b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008132  lea     r9, [rdx+8]
0x140008136  mov     eax, [rdx+18h]
0x140008139  mov     [rsp+78h+var_48], eax
0x14000813d  mov     [rsp+78h+var_50], r9
0x140008142  mov     rcx, [rcx+40h]
0x140008146  call    WPP_RECORDER_SF__guid_d
0x14000814b  mov     rsi, [rsi+50h]
0x14000814f  xor     edi, edi
0x140008151  mov     rcx, rsi; SpinLock
0x140008154  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000815b  nop     dword ptr [rax+rax+00h]
0x140008160  lea     rdx, [rsi+18h]
0x140008164  mov     [rsi+8], al
0x140008167  mov     rax, [rdx]
0x14000816a  cmp     rax, rdx
0x14000816d  jnz     short loc_1400081A5
0x14000816f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008176  jz      short loc_14000819E
0x140008178  mov     rcx, cs:WPP_GLOBAL_Control
0x14000817f  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140008186  mov     r9d, 0AEh
0x14000818c  mov     [rsp+78h+var_58], rax
0x140008191  lea     r8d, [rdi+1]
0x140008195  mov     rcx, [rcx+40h]
0x140008199  call    WPP_RECORDER_SF_
0x14000819e  mov     ebx, 0C000000Eh
0x1400081a3  jmp     short loc_1400081DC
0x1400081a5  test    r14, r14
0x1400081a8  jz      short loc_1400081C7
0x1400081aa  mov     rcx, [r14]
0x1400081ad  test    rcx, rcx
0x1400081b0  jz      short loc_1400081C7
0x1400081b2  cmp     rcx, [rax+78h]
0x1400081b6  jz      short loc_1400081C7
0x1400081b8  mov     rax, [rax]
0x1400081bb  cmp     rax, rdx
0x1400081be  jnz     short loc_1400081B2
0x1400081c0  mov     ebx, 0C0000141h
0x1400081c5  jmp     short loc_1400081DC
0x1400081c7  mov     rcx, [rax+50h]; Object
0x1400081cb  mov     rdi, rax
0x1400081ce  call    cs:__imp_ObfReferenceObject
0x1400081d5  nop     dword ptr [rax+rax+00h]
0x1400081da  xor     ebx, ebx
0x1400081dc  mov     dl, [rsi+8]; NewIrql
0x1400081df  xor     eax, eax
0x1400081e1  test    ebx, ebx
0x1400081e3  mov     rcx, rsi; SpinLock
0x1400081e6  cmovs   rdi, rax
0x1400081ea  call    cs:__imp_KeReleaseSpinLock
0x1400081f1  nop     dword ptr [rax+rax+00h]
0x1400081f6  test    ebx, ebx
0x1400081f8  js      short loc_140008223
0x1400081fa  mov     edx, 0E8h
0x1400081ff  mov     ecx, 40h ; '@'
0x140008204  mov     r8d, 44416652h
0x14000820a  call    cs:__imp_ExAllocatePool2
0x140008211  nop     dword ptr [rax+rax+00h]
0x140008216  mov     rsi, rax
0x140008219  test    rax, rax
0x14000821c  jnz     short loc_140008287
0x14000821e  mov     ebx, 0C000009Ah
0x140008223  mov     qword ptr [r15], 0
0x14000822a  test    rdi, rdi
0x14000822d  jz      short loc_14000823F
0x14000822f  mov     rcx, [rdi+50h]; Object
0x140008233  call    cs:__imp_ObfDereferenceObject
0x14000823a  nop     dword ptr [rax+rax+00h]
0x14000823f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008246  jz      short loc_140008276
0x140008248  mov     rcx, [r15]
0x14000824b  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140008252  mov     [rsp+78h+var_50], rcx
0x140008257  mov     r9d, 35h ; '5'
0x14000825d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008264  mov     [rsp+78h+var_58], rax
0x140008269  lea     r8d, [r9-26h]
0x14000826d  mov     rcx, [rcx+40h]
0x140008271  call    WPP_RECORDER_SF_q
0x140008276  mov     eax, ebx
0x140008278  add     rsp, 48h
0x14000827c  pop     r15
0x14000827e  pop     r14
0x140008280  pop     r12
0x140008282  pop     rdi
0x140008283  pop     rsi
0x140008284  pop     rbx
0x140008285  retn
0x140008287  mov     dword ptr [rax+10h], 52444441h
0x14000828e  lea     rcx, [rsi+30h]; SpinLock
0x140008292  movups  xmm0, xmmword ptr [r14]
0x140008296  movups  xmmword ptr [rax+58h], xmm0
0x14000829a  movups  xmm1, xmmword ptr [r14+0Ch]
0x14000829f  mov     [rax+50h], rdi
0x1400082a3  movups  xmmword ptr [rax+64h], xmm1
0x1400082a7  cmp     dword ptr [r14+18h], 0
0x1400082ac  mov     dword ptr [rsi+0CCh], 1
0x1400082b6  setnz   al
0x1400082b9  mov     [rsi+88h], al
0x1400082bf  mov     dword ptr [rsi+0D8h], 1
0x1400082c9  mov     dword ptr [rsi+0E0h], 0
0x1400082d3  mov     dword ptr [rsi+0DCh], 0
0x1400082dd  call    cs:__imp_KeInitializeSpinLock
0x1400082e4  nop     dword ptr [rax+rax+00h]
0x1400082e9  lea     rax, [rsi+78h]
0x1400082ed  mov     [rsi+8], rsi
0x1400082f1  mov     [rax+8], rax
0x1400082f5  lea     rcx, [rsi+18h]
0x1400082f9  mov     [rax], rax
0x1400082fc  lea     rdx, FreeAddrObject
0x140008303  lea     rax, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000830a  mov     [rsi], rsi
0x14000830d  mov     r9d, 53Fh
0x140008313  mov     [rsp+78h+var_58], rax
0x140008318  mov     r8d, 54494E49h
0x14000831e  call    RefObj_InitEx
0x140008323  xor     ebx, ebx
0x140008325  mov     [r15], rsi
0x140008328  jmp     loc_14000823F
```
