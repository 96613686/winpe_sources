# CFilteringPlatformHelperClass::traceEvent(tagNDFEventChannel,ushort const *)

- ea: `0x1800097dc`
- end: `0x180009818`
- name: `?traceEvent@CFilteringPlatformHelperClass@@AEAAXW4tagNDFEventChannel@@PEBG@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008b74`
- `0x180008d7c`
- `0x180009820`

## callees

- `0x1800097dc`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::traceEvent(__int64 a1, __int64 a2)
{
  __int64 v2; // r10
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 544);
  if ( v2 )
  {
    if ( *(_QWORD *)(a1 + 552) )
      return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v2 + 24LL))(v2, a2, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800097dc  sub     rsp, 38h
0x1800097e0  mov     r11, r8
0x1800097e3  mov     r10, [rcx+220h]
0x1800097ea  test    r10, r10
0x1800097ed  jz      short loc_180009813
0x1800097ef  mov     r9, [rcx+228h]
0x1800097f6  test    r9, r9
0x1800097f9  jz      short loc_180009813
0x1800097fb  mov     rax, [r10]
0x1800097fe  xor     r8d, r8d
0x180009801  mov     [rsp+38h+var_18], r11
0x180009806  mov     rcx, r10
0x180009809  mov     rax, [rax+18h]
0x18000980d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009812  nop
0x180009813  add     rsp, 38h
0x180009817  retn
```
