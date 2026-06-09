# FIPfConflictTelemetryUpdateNode

- ea: `0x14000ff0c`
- end: `0x14000ffb1`
- name: `FIPfConflictTelemetryUpdateNode`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000f9b8`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14000ff0c`

## pseudocode

```c
__int64 __fastcall FIPfConflictTelemetryUpdateNode(__int64 a1, _WORD *a2, int a3, unsigned int a4)
{
  unsigned int v4; // eax
  __int64 v5; // r15
  __int64 v6; // rdi
  unsigned int i; // esi
  unsigned int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // eax

  v4 = 16;
  v5 = a3;
  v6 = 0;
  for ( i = a4; v4 <= a4; v4 *= 2 )
  {
    if ( (unsigned int)v6 >= 0xF )
      break;
    v6 = (unsigned int)(v6 + 1);
  }
  FILockExclusiveAcquire(a1 + 24);
  *(_WORD *)(a1 + 32) += *a2;
  v10 = i;
  *(_WORD *)(a1 + 2 * v5 + 34) += a2[1];
  *(_WORD *)(a1 + 2 * v5 + 42) += a2[2];
  *(_WORD *)(a1 + 2 * v5 + 50) += a2[3];
  v11 = *(_DWORD *)(a1 + 64);
  *(_DWORD *)(a1 + 60) += i;
  if ( v11 < i )
    v10 = v11;
  v12 = *(_DWORD *)(a1 + 68);
  *(_DWORD *)(a1 + 64) = v10;
  if ( v12 > i )
    i = v12;
  *(_DWORD *)(a1 + 68) = i;
  ++*(_WORD *)(a1 + 2 * v6 + 72);
  return FILockExclusiveRelease(a1 + 24);
}

```

## disassembly

```asm
0x14000ff0c  push    rbx
0x14000ff0e  push    rbp
0x14000ff0f  push    rsi
0x14000ff10  push    rdi
0x14000ff11  push    r12
0x14000ff13  push    r14
0x14000ff15  push    r15
0x14000ff17  sub     rsp, 20h
0x14000ff1b  mov     eax, 10h
0x14000ff20  movsxd  r15, r8d
0x14000ff23  xor     edi, edi
0x14000ff25  mov     esi, r9d
0x14000ff28  mov     r14, rdx
0x14000ff2b  mov     rbp, rcx
0x14000ff2e  lea     r12d, [rax-0Fh]
0x14000ff32  cmp     r9d, eax
0x14000ff35  jb      short loc_14000FF45
0x14000ff37  cmp     edi, 0Fh
0x14000ff3a  jnb     short loc_14000FF45
0x14000ff3c  add     edi, r12d
0x14000ff3f  add     eax, eax
0x14000ff41  cmp     eax, esi
0x14000ff43  jbe     short loc_14000FF37
0x14000ff45  add     rcx, 18h
0x14000ff49  call    FILockExclusiveAcquire
0x14000ff4e  movzx   eax, word ptr [r14]
0x14000ff52  lea     rcx, [rbp+18h]
0x14000ff56  add     [rbp+20h], ax
0x14000ff5a  mov     edx, esi
0x14000ff5c  movzx   eax, word ptr [r14+2]
0x14000ff61  add     [rbp+r15*2+22h], ax
0x14000ff67  movzx   eax, word ptr [r14+4]
0x14000ff6c  add     [rbp+r15*2+2Ah], ax
0x14000ff72  movzx   eax, word ptr [r14+6]
0x14000ff77  add     [rbp+r15*2+32h], ax
0x14000ff7d  mov     eax, [rbp+40h]
0x14000ff80  add     [rbp+3Ch], esi
0x14000ff83  cmp     eax, esi
0x14000ff85  cmovb   edx, eax
0x14000ff88  mov     eax, [rbp+44h]
0x14000ff8b  cmp     eax, esi
0x14000ff8d  mov     [rbp+40h], edx
0x14000ff90  cmova   esi, eax
0x14000ff93  mov     [rbp+44h], esi
0x14000ff96  add     [rbp+rdi*2+48h], r12w
0x14000ff9c  call    FILockExclusiveRelease
0x14000ffa1  add     rsp, 20h
0x14000ffa5  pop     r15
0x14000ffa7  pop     r14
0x14000ffa9  pop     r12
0x14000ffab  pop     rdi
0x14000ffac  pop     rsi
0x14000ffad  pop     rbp
0x14000ffae  pop     rbx
0x14000ffaf  retn
```
