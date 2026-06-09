# CdReMountOldVcb

- ea: `0x1400020d0`
- end: `0x1400021bb`
- name: `CdReMountOldVcb`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400142d8`

## callees

- `0x1400020d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400020f5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400020f5`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002106`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002106`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x14000219e`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x14000219e`

## pseudocode

```c
void __fastcall CdReMountOldVcb(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  void *v4; // rcx
  int v8; // eax
  __int64 v9; // rdx
  __int64 i; // rcx
  __int64 v11; // rax
  __int64 Irql; // [rsp+30h] [rbp+8h] BYREF

  Irql = a1;
  v4 = *(void **)(a2 + 16);
  LOBYTE(Irql) = 0;
  ObfDereferenceObject(v4);
  IoAcquireVpbSpinLock((PKIRQL)&Irql);
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 16LL) + 56LL) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(*(_QWORD *)(a2 + 8) + 16LL) = *(_QWORD *)(*(_QWORD *)(a3 + 8) + 16LL);
  *(_QWORD *)(a2 + 16) = a4;
  *(_DWORD *)(a2 + 52) = 2;
  v8 = *(_DWORD *)(a3 + 544);
  *(_DWORD *)(a2 + 48) &= ~0x200u;
  *(_DWORD *)(a2 + 544) = v8;
  v9 = *(_QWORD *)(a3 + 568);
  *(_QWORD *)(a2 + 568) = v9;
  *(_QWORD *)(a3 + 568) = 0;
  if ( v9 )
  {
    for ( i = 0; i != 4; ++i )
    {
      *(_QWORD *)(a2 + 16 * i + 584) = v9;
      v11 = 2 * (i + 36);
      v9 += 49152;
      *(_DWORD *)(a2 + 8 * v11) = -1;
    }
  }
  IoReleaseVpbSpinLock(Irql);
}

```

## disassembly

```asm
0x1400020d0  mov     rax, rsp
0x1400020d3  mov     [rax+10h], rbx
0x1400020d7  mov     [rax+18h], rsi
0x1400020db  mov     [rax+8], rcx
0x1400020df  push    rdi
0x1400020e0  sub     rsp, 20h
0x1400020e4  mov     rcx, [rdx+10h]; Object
0x1400020e8  mov     rbx, r9
0x1400020eb  mov     rdi, r8
0x1400020ee  mov     byte ptr [rax+8], 0
0x1400020f2  mov     rsi, rdx
0x1400020f5  call    cs:__imp_ObfDereferenceObject
0x1400020fc  nop     dword ptr [rax+rax+00h]
0x140002101  lea     rcx, [rsp+28h+Irql]; Irql
0x140002106  call    cs:__imp_IoAcquireVpbSpinLock
0x14000210d  nop     dword ptr [rax+rax+00h]
0x140002112  mov     rax, [rdi+8]
0x140002116  mov     rcx, [rax+10h]
0x14000211a  mov     rax, [rsi+8]
0x14000211e  mov     [rcx+38h], rax
0x140002122  mov     rax, [rdi+8]
0x140002126  mov     rcx, [rsi+8]
0x14000212a  mov     rax, [rax+10h]
0x14000212e  mov     [rcx+10h], rax
0x140002132  mov     [rsi+10h], rbx
0x140002136  mov     dword ptr [rsi+34h], 2
0x14000213d  mov     eax, [rdi+220h]
0x140002143  btr     dword ptr [rsi+30h], 9
0x140002148  mov     [rsi+220h], eax
0x14000214e  mov     rdx, [rdi+238h]
0x140002155  mov     [rsi+238h], rdx
0x14000215c  mov     qword ptr [rdi+238h], 0
0x140002167  test    rdx, rdx
0x14000216a  jz      short loc_14000219A
0x14000216c  xor     ecx, ecx
0x14000216e  mov     rax, rcx
0x140002171  add     rax, rax
0x140002174  mov     [rsi+rax*8+248h], rdx
0x14000217c  lea     rax, [rcx+24h]
0x140002180  add     rax, rax
0x140002183  add     rdx, 0C000h
0x14000218a  inc     rcx
0x14000218d  mov     dword ptr [rsi+rax*8], 0FFFFFFFFh
0x140002194  cmp     rcx, 4
0x140002198  jnz     short loc_14000216E
0x14000219a  mov     cl, byte ptr [rsp+28h+Irql]; Irql
0x14000219e  call    cs:__imp_IoReleaseVpbSpinLock
0x1400021a5  nop     dword ptr [rax+rax+00h]
0x1400021aa  mov     rbx, [rsp+28h+arg_8]
0x1400021af  mov     rsi, [rsp+28h+arg_10]
0x1400021b4  add     rsp, 20h
0x1400021b8  pop     rdi
0x1400021b9  retn
```
