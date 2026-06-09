# DequeuePolledReadSystemIrp

- ea: `0x180023610`
- end: `0x1800236d3`
- name: `DequeuePolledReadSystemIrp`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adc0`

## callees

- `0x180023610`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x18002369e`
- `ntoskrnl!KeReleaseSpinLock` at `0x18002369e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18002362e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18002362e`

## pseudocode

```c
_QWORD *__fastcall DequeuePolledReadSystemIrp(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  _QWORD *v3; // rbx
  KIRQL v4; // r9
  _QWORD *v5; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx

  v1 = (KSPIN_LOCK *)(a1 + 232);
  v3 = 0;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 232));
  v5 = (_QWORD *)(a1 + 216);
  while ( 1 )
  {
    v5 = (_QWORD *)*v5;
    if ( v5 == (_QWORD *)(a1 + 216) )
      break;
    v3 = v5 - 21;
    if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v5[2] + 48LL) + 24LL) + 118LL) )
      goto LABEL_10;
    v6 = (_QWORD *)*v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
      __fastfail(3u);
    *v7 = v6;
    v6[1] = v7;
    if ( _InterlockedExchange64(v3 + 13, 0) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
      if ( v5 != (_QWORD *)168 )
        break;
    }
    else
    {
      v5[1] = v5;
      *v5 = v5;
LABEL_10:
      v3 = 0;
    }
  }
  KeReleaseSpinLock(v1, v4);
  return v3;
}

```

## disassembly

```asm
0x180023610  mov     [rsp+arg_0], rbx
0x180023615  mov     [rsp+arg_8], rsi
0x18002361a  push    rdi
0x18002361b  sub     rsp, 20h
0x18002361f  lea     rsi, [rcx+0E8h]
0x180023626  mov     rdi, rcx
0x180023629  mov     rcx, rsi; SpinLock
0x18002362c  xor     ebx, ebx
0x18002362e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180023635  nop     dword ptr [rax+rax+00h]
0x18002363a  lea     r8, [rdi+0D8h]
0x180023641  mov     r9b, al
0x180023644  mov     rdx, r8
0x180023647  mov     rdx, [rdx]
0x18002364a  cmp     rdx, r8
0x18002364d  jz      short loc_180023698
0x18002364f  lea     rbx, [rdx-0A8h]
0x180023656  mov     rax, [rbx+0B8h]
0x18002365d  mov     rcx, [rax+30h]
0x180023661  mov     rax, [rcx+18h]
0x180023665  cmp     byte ptr [rax+76h], 0
0x180023669  jz      short loc_1800236C5
0x18002366b  mov     rax, [rdx]
0x18002366e  cmp     [rax+8], rdx
0x180023672  jnz     short loc_1800236CC
0x180023674  mov     rcx, [rdx+8]
0x180023678  cmp     [rcx], rdx
0x18002367b  jnz     short loc_1800236CC
0x18002367d  mov     [rcx], rax
0x180023680  mov     [rax+8], rcx
0x180023684  xor     eax, eax
0x180023686  xchg    rax, [rbx+68h]
0x18002368a  test    rax, rax
0x18002368d  jz      short loc_1800236BE
0x18002368f  lock dec dword ptr [rdi+10h]
0x180023693  test    rbx, rbx
0x180023696  jz      short loc_180023647
0x180023698  mov     dl, r9b; NewIrql
0x18002369b  mov     rcx, rsi; SpinLock
0x18002369e  call    cs:__imp_KeReleaseSpinLock
0x1800236a5  nop     dword ptr [rax+rax+00h]
0x1800236aa  mov     rsi, [rsp+28h+arg_8]
0x1800236af  mov     rax, rbx
0x1800236b2  mov     rbx, [rsp+28h+arg_0]
0x1800236b7  add     rsp, 20h
0x1800236bb  pop     rdi
0x1800236bc  retn
0x1800236be  mov     [rdx+8], rdx
0x1800236c2  mov     [rdx], rdx
0x1800236c5  xor     ebx, ebx
0x1800236c7  jmp     loc_180023647
0x1800236cc  mov     ecx, 3
0x1800236d1  int     29h; Win8: RtlFailFast(ecx)
```
