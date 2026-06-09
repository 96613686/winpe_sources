# DequeuePolledReadSessionIrp

- ea: `0x180023538`
- end: `0x180023607`
- name: `DequeuePolledReadSessionIrp`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adc0`

## callees

- `0x180023538`

## import_xrefs

- `ntoskrnl!RtlGetActiveConsoleId` at `0x180023590`
- `ntoskrnl!RtlGetActiveConsoleId` at `0x180023590`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800235d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800235d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180023556`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180023556`

## pseudocode

```c
_QWORD *__fastcall DequeuePolledReadSessionIrp(__int64 a1)
{
  KSPIN_LOCK *v1; // r14
  _QWORD *v3; // rsi
  _QWORD *v4; // r15
  KIRQL v5; // r12
  _QWORD *v6; // rdi
  int v7; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rcx

  v1 = (KSPIN_LOCK *)(a1 + 232);
  v3 = 0;
  v4 = (_QWORD *)(a1 + 216);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 232));
  v6 = v4;
  while ( 1 )
  {
    v6 = (_QWORD *)*v6;
    if ( v6 == v4 )
      break;
    v3 = v6 - 21;
    v7 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v6[2] + 48LL) + 24LL) + 124LL);
    if ( v7 != (unsigned int)RtlGetActiveConsoleId() )
      goto LABEL_10;
    v8 = (_QWORD *)*v6;
    if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v9 = (_QWORD *)v6[1], (_QWORD *)*v9 != v6) )
      __fastfail(3u);
    *v9 = v8;
    v8[1] = v9;
    if ( _InterlockedExchange64(v3 + 13, 0) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
      if ( v6 != (_QWORD *)168 )
        break;
    }
    else
    {
      v6[1] = v6;
      *v6 = v6;
LABEL_10:
      v3 = 0;
    }
  }
  KeReleaseSpinLock(v1, v5);
  return v3;
}

```

## disassembly

```asm
0x180023538  push    rbx
0x18002353a  push    rbp
0x18002353b  push    rsi
0x18002353c  push    rdi
0x18002353d  push    r12
0x18002353f  push    r14
0x180023541  push    r15
0x180023543  sub     rsp, 20h
0x180023547  lea     r14, [rcx+0E8h]
0x18002354e  mov     rbp, rcx
0x180023551  mov     rcx, r14; SpinLock
0x180023554  xor     esi, esi
0x180023556  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18002355d  nop     dword ptr [rax+rax+00h]
0x180023562  lea     r15, [rbp+0D8h]
0x180023569  mov     r12b, al
0x18002356c  mov     rdi, r15
0x18002356f  mov     rdi, [rdi]
0x180023572  cmp     rdi, r15
0x180023575  jz      short loc_1800235CD
0x180023577  lea     rsi, [rdi-0A8h]
0x18002357e  mov     rax, [rsi+0B8h]
0x180023585  mov     rcx, [rax+30h]
0x180023589  mov     rax, [rcx+18h]
0x18002358d  mov     ebx, [rax+7Ch]
0x180023590  call    cs:__imp_RtlGetActiveConsoleId
0x180023597  nop     dword ptr [rax+rax+00h]
0x18002359c  cmp     ebx, eax
0x18002359e  jnz     short loc_1800235F9
0x1800235a0  mov     rax, [rdi]
0x1800235a3  cmp     [rax+8], rdi
0x1800235a7  jnz     short loc_180023600
0x1800235a9  mov     rcx, [rdi+8]
0x1800235ad  cmp     [rcx], rdi
0x1800235b0  jnz     short loc_180023600
0x1800235b2  mov     [rcx], rax
0x1800235b5  mov     [rax+8], rcx
0x1800235b9  xor     eax, eax
0x1800235bb  xchg    rax, [rsi+68h]
0x1800235bf  test    rax, rax
0x1800235c2  jz      short loc_1800235F2
0x1800235c4  lock dec dword ptr [rbp+10h]
0x1800235c8  test    rsi, rsi
0x1800235cb  jz      short loc_18002356F
0x1800235cd  mov     dl, r12b; NewIrql
0x1800235d0  mov     rcx, r14; SpinLock
0x1800235d3  call    cs:__imp_KeReleaseSpinLock
0x1800235da  nop     dword ptr [rax+rax+00h]
0x1800235df  mov     rax, rsi
0x1800235e2  add     rsp, 20h
0x1800235e6  pop     r15
0x1800235e8  pop     r14
0x1800235ea  pop     r12
0x1800235ec  pop     rdi
0x1800235ed  pop     rsi
0x1800235ee  pop     rbp
0x1800235ef  pop     rbx
0x1800235f0  retn
0x1800235f2  mov     [rdi+8], rdi
0x1800235f6  mov     [rdi], rdi
0x1800235f9  xor     esi, esi
0x1800235fb  jmp     loc_18002356F
0x180023600  mov     ecx, 3
0x180023605  int     29h; Win8: RtlFailFast(ecx)
```
