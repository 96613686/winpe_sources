# TdiCloseConnection

- ea: `0x140007200`
- end: `0x14000734a`
- name: `TdiCloseConnection`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140033a70`

## callees

- `0x140003cb4`
- `0x140004a68`
- `0x140006a04`
- `0x140007200`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000726f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000726f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400072ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400072ad`

## string_xrefs

- `0x1400072b9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiCloseConnection(__int64 a1, int a2)
{
  __int64 v3; // rdi
  __int64 v4; // rdx
  _QWORD *v5; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      96,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a1);
  if ( a1 && *(_DWORD *)(a1 + 16) == 1313754947 )
  {
    v3 = *(_QWORD *)(a1 + 64);
    TdiCleanupConnection(a1, a2);
    *(_BYTE *)(v3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 48));
    v4 = *(_QWORD *)a1;
    if ( *(_QWORD *)(*(_QWORD *)a1 + 8LL) != a1 || (v5 = *(_QWORD **)(a1 + 8), *v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    *(_QWORD *)(a1 + 8) = a1;
    *(_QWORD *)a1 = a1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 48), *(_BYTE *)(v3 + 56));
    RefObj_ReleaseEx(a1 + 24, 541672532, 2821, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    RefObj_ReleaseEx(v3 + 24, 1313754947, 2822, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    RefObj_ReleaseEx(a1 + 24, 1414090313, 2827, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      97,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      0);
  return 0;
}

```

## disassembly

```asm
0x140007200  push    rbx
0x140007202  push    rbp
0x140007203  push    rsi
0x140007204  push    rdi
0x140007205  push    r15
0x140007207  sub     rsp, 30h
0x14000720b  mov     rbx, rcx
0x14000720e  lea     rbp, WPP_RECORDER_INITIALIZED
0x140007215  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000721c  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140007223  jz      short loc_140007249
0x140007225  mov     [rsp+58h+var_30], rcx
0x14000722a  mov     r9d, 60h ; '`'
0x140007230  mov     rcx, cs:WPP_GLOBAL_Control
0x140007237  mov     [rsp+58h+var_38], r15
0x14000723c  lea     r8d, [r9-51h]
0x140007240  mov     rcx, [rcx+40h]
0x140007244  call    WPP_RECORDER_SF_q
0x140007249  test    rbx, rbx
0x14000724c  jz      loc_140007305
0x140007252  cmp     dword ptr [rbx+10h], 4E4E4F43h
0x140007259  jnz     loc_140007305
0x14000725f  mov     rdi, [rbx+40h]
0x140007263  mov     rcx, rbx
0x140007266  call    TdiCleanupConnection
0x14000726b  lea     rcx, [rdi+30h]; SpinLock
0x14000726f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007276  nop     dword ptr [rax+rax+00h]
0x14000727b  mov     [rdi+38h], al
0x14000727e  mov     rdx, [rbx]
0x140007281  cmp     [rdx+8], rbx
0x140007285  jnz     loc_140007343
0x14000728b  mov     rax, [rbx+8]
0x14000728f  cmp     [rax], rbx
0x140007292  jnz     loc_140007343
0x140007298  mov     [rax], rdx
0x14000729b  lea     rcx, [rdi+30h]; SpinLock
0x14000729f  mov     [rdx+8], rax
0x1400072a3  mov     [rbx+8], rbx
0x1400072a7  mov     [rbx], rbx
0x1400072aa  mov     dl, [rdi+38h]; NewIrql
0x1400072ad  call    cs:__imp_KeReleaseSpinLock
0x1400072b4  nop     dword ptr [rax+rax+00h]
0x1400072b9  lea     rsi, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400072c0  mov     edx, 20494454h
0x1400072c5  mov     r9, rsi
0x1400072c8  lea     rcx, [rbx+18h]
0x1400072cc  mov     r8d, 0B05h
0x1400072d2  call    RefObj_ReleaseEx
0x1400072d7  lea     rcx, [rdi+18h]
0x1400072db  mov     r9, rsi
0x1400072de  mov     edx, 4E4E4F43h
0x1400072e3  mov     r8d, 0B06h
0x1400072e9  call    RefObj_ReleaseEx
0x1400072ee  mov     r9, rsi
0x1400072f1  lea     rcx, [rbx+18h]
0x1400072f5  mov     edx, 54494E49h
0x1400072fa  mov     r8d, 0B0Bh
0x140007300  call    RefObj_ReleaseEx
0x140007305  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000730c  jz      short loc_140007335
0x14000730e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007315  mov     r9d, 61h ; 'a'
0x14000731b  mov     dword ptr [rsp+58h+var_30], 0
0x140007323  mov     [rsp+58h+var_38], r15
0x140007328  mov     rcx, [rcx+40h]
0x14000732c  lea     r8d, [r9-52h]
0x140007330  call    WPP_RECORDER_SF_d
0x140007335  xor     eax, eax
0x140007337  add     rsp, 30h
0x14000733b  pop     r15
0x14000733d  pop     rdi
0x14000733e  pop     rsi
0x14000733f  pop     rbp
0x140007340  pop     rbx
0x140007341  retn
0x140007343  mov     ecx, 3
0x140007348  int     29h; Win8: RtlFailFast(ecx)
```
