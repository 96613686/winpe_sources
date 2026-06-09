# TdiCloseAddress

- ea: `0x1400070c8`
- end: `0x1400071fa`
- name: `TdiCloseAddress`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140033a70`

## callees

- `0x140004a68`
- `0x1400070c8`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007132`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007132`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007188`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007188`

## string_xrefs

- `0x140007194`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiCloseAddress(__int64 *a1, int a2)
{
  __int64 v3; // rdi
  __int64 *v4; // rcx
  __int64 **v5; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      95,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a1);
  if ( a1 && *((_DWORD *)a1 + 4) == 1380205633 )
  {
    v3 = a1[8];
    *(_BYTE *)(v3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 48));
    v4 = (__int64 *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v5 = (__int64 **)a1[1], *v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    v4[1] = (__int64)v5;
    a1[1] = (__int64)a1;
    *a1 = (__int64)a1;
    if ( *((_BYTE *)a1 + 136) )
      *(_DWORD *)(v3 + 92) &= ~(1 << *((_DWORD *)a1 + 28));
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 48), *(_BYTE *)(v3 + 56));
    RefObj_ReleaseEx(a1 + 3, 541672532, 2786, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    RefObj_ReleaseEx(v3 + 24, 1380205633, 2787, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    RefObj_ReleaseEx(a1 + 3, 1414090313, 2789, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  }
  return 0;
}

```

## disassembly

```asm
0x1400070c8  mov     r11, rsp
0x1400070cb  mov     [r11+8], rbx
0x1400070cf  mov     [r11+10h], rsi
0x1400070d3  push    rdi
0x1400070d4  sub     rsp, 30h
0x1400070d8  mov     rbx, rcx
0x1400070db  lea     rax, WPP_RECORDER_INITIALIZED
0x1400070e2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400070e9  jz      short loc_140007114
0x1400070eb  mov     [r11-10h], rcx
0x1400070ef  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400070f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070fd  mov     r9d, 5Fh ; '_'
0x140007103  mov     [r11-18h], rax
0x140007107  mov     rcx, [rcx+40h]
0x14000710b  lea     r8d, [r9-50h]
0x14000710f  call    WPP_RECORDER_SF_q
0x140007114  test    rbx, rbx
0x140007117  jz      loc_1400071E0
0x14000711d  cmp     dword ptr [rbx+10h], 52444441h
0x140007124  jnz     loc_1400071E0
0x14000712a  mov     rdi, [rbx+40h]
0x14000712e  lea     rcx, [rdi+30h]; SpinLock
0x140007132  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007139  nop     dword ptr [rax+rax+00h]
0x14000713e  mov     [rdi+38h], al
0x140007141  mov     rcx, [rbx]
0x140007144  cmp     [rcx+8], rbx
0x140007148  jnz     loc_1400071F3
0x14000714e  mov     rax, [rbx+8]
0x140007152  cmp     [rax], rbx
0x140007155  jnz     loc_1400071F3
0x14000715b  mov     [rax], rcx
0x14000715e  mov     [rcx+8], rax
0x140007162  mov     [rbx+8], rbx
0x140007166  mov     [rbx], rbx
0x140007169  cmp     byte ptr [rbx+88h], 0
0x140007170  jz      short loc_140007181
0x140007172  mov     ecx, [rbx+70h]
0x140007175  mov     eax, 1
0x14000717a  shl     eax, cl
0x14000717c  not     eax
0x14000717e  and     [rdi+5Ch], eax
0x140007181  mov     dl, [rdi+38h]; NewIrql
0x140007184  lea     rcx, [rdi+30h]; SpinLock
0x140007188  call    cs:__imp_KeReleaseSpinLock
0x14000718f  nop     dword ptr [rax+rax+00h]
0x140007194  lea     rsi, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000719b  mov     edx, 20494454h
0x1400071a0  mov     r9, rsi
0x1400071a3  lea     rcx, [rbx+18h]
0x1400071a7  mov     r8d, 0AE2h
0x1400071ad  call    RefObj_ReleaseEx
0x1400071b2  lea     rcx, [rdi+18h]
0x1400071b6  mov     r9, rsi
0x1400071b9  mov     edx, 52444441h
0x1400071be  mov     r8d, 0AE3h
0x1400071c4  call    RefObj_ReleaseEx
0x1400071c9  mov     r9, rsi
0x1400071cc  lea     rcx, [rbx+18h]
0x1400071d0  mov     edx, 54494E49h
0x1400071d5  mov     r8d, 0AE5h
0x1400071db  call    RefObj_ReleaseEx
0x1400071e0  mov     rbx, [rsp+38h+arg_0]
0x1400071e5  xor     eax, eax
0x1400071e7  mov     rsi, [rsp+38h+arg_8]
0x1400071ec  add     rsp, 30h
0x1400071f0  pop     rdi
0x1400071f1  retn
0x1400071f3  mov     ecx, 3
0x1400071f8  int     29h; Win8: RtlFailFast(ecx)
```
