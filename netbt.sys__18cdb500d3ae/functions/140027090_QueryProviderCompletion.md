# QueryProviderCompletion

- ea: `0x140027090`
- end: `0x1400271f1`
- name: `QueryProviderCompletion`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140027090`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400270e9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400270e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027176`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027176`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400271d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400271d2`

## pseudocode

```c
__int64 __fastcall QueryProviderCompletion(_DWORD *a1, __int64 a2)
{
  __int64 v4; // rcx
  _DWORD *v5; // rbx
  unsigned int v6; // eax
  int v7; // eax
  unsigned int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // eax
  KIRQL v11; // al
  __int64 i; // rdx

  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  if ( *(int *)(a2 + 48) >= 0 )
  {
    v4 = *(_QWORD *)(a2 + 8);
    if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
      v5 = *(_DWORD **)(v4 + 24);
    else
      v5 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000000u);
    if ( v5 )
    {
      v6 = v5[1];
      v5[4] = 74989;
      v5[5] = 128;
      if ( v6 <= 4 )
      {
        v7 = 0;
      }
      else if ( v6 <= 0x20003 )
      {
        v7 = v6 - 4;
      }
      else
      {
        v7 = 0x1FFFF;
      }
      v5[1] = v7;
      if ( a1[85] == 1 || (v8 = 2 * (unsigned __int16)word_1400395DC + 80, v9 = v5[3], v9 <= v8) )
      {
        v5[3] = 0;
      }
      else
      {
        v10 = v9 - v8;
        v5[3] = v10;
        if ( v10 > 0x200 )
          v5[3] = 512;
      }
      v11 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      for ( i = NbtConfig; (__int64 *)i != &NbtConfig; i = *(_QWORD *)i )
      {
        if ( (a1[122] & a1[123]) == (*(_DWORD *)(i + 144) & *(_DWORD *)(i + 148)) && *(_DWORD *)(i + 516) )
        {
          v5[4] |= 0x1000u;
          break;
        }
      }
      KeReleaseSpinLock(&SpinLock, v11);
    }
    else
    {
      *(_DWORD *)(a2 + 48) = -1073741670;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140027090  mov     [rsp+arg_0], rbx
0x140027095  mov     [rsp+arg_8], rsi
0x14002709a  push    rdi
0x14002709b  sub     rsp, 30h
0x14002709f  cmp     byte ptr [rdx+41h], 0
0x1400270a3  mov     rdi, rdx
0x1400270a6  mov     rsi, rcx
0x1400270a9  jz      short loc_1400270B6
0x1400270ab  mov     rax, [rdx+0B8h]
0x1400270b2  or      byte ptr [rax+3], 1
0x1400270b6  cmp     dword ptr [rdx+30h], 0
0x1400270ba  jl      loc_1400271DE
0x1400270c0  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400270c4  test    byte ptr [rcx+0Ah], 5
0x1400270c8  jz      short loc_1400270D0
0x1400270ca  mov     rbx, [rcx+18h]
0x1400270ce  jmp     short loc_1400270F8
0x1400270d0  xor     r9d, r9d; RequestedAddress
0x1400270d3  mov     [rsp+38h+Priority], 40000000h; Priority
0x1400270db  xor     edx, edx; AccessMode
0x1400270dd  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400270e5  lea     r8d, [r9+1]; CacheType
0x1400270e9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400270f0  nop     dword ptr [rax+rax+00h]
0x1400270f5  mov     rbx, rax
0x1400270f8  test    rbx, rbx
0x1400270fb  jnz     short loc_140027109
0x1400270fd  mov     dword ptr [rdi+30h], 0C000009Ah
0x140027104  jmp     loc_1400271DE
0x140027109  mov     eax, [rbx+4]
0x14002710c  mov     dword ptr [rbx+10h], 124EDh
0x140027113  mov     dword ptr [rbx+14h], 80h
0x14002711a  cmp     eax, 4
0x14002711d  jbe     short loc_140027132
0x14002711f  cmp     eax, 20003h
0x140027124  jbe     short loc_14002712D
0x140027126  mov     eax, 1FFFFh
0x14002712b  jmp     short loc_140027134
0x14002712d  add     eax, 0FFFFFFFCh
0x140027130  jmp     short loc_140027134
0x140027132  xor     eax, eax
0x140027134  mov     [rbx+4], eax
0x140027137  cmp     dword ptr [rsi+154h], 1
0x14002713e  jz      short loc_140027168
0x140027140  movzx   eax, cs:word_1400395DC
0x140027147  lea     ecx, ds:50h[rax*2]
0x14002714e  mov     eax, [rbx+0Ch]
0x140027151  cmp     eax, ecx
0x140027153  jbe     short loc_140027168
0x140027155  sub     eax, ecx
0x140027157  mov     ecx, 200h
0x14002715c  mov     [rbx+0Ch], eax
0x14002715f  cmp     eax, ecx
0x140027161  jbe     short loc_14002716F
0x140027163  mov     [rbx+0Ch], ecx
0x140027166  jmp     short loc_14002716F
0x140027168  mov     dword ptr [rbx+0Ch], 0
0x14002716f  lea     rcx, SpinLock; SpinLock
0x140027176  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002717d  nop     dword ptr [rax+rax+00h]
0x140027182  mov     r8d, [rsi+1ECh]
0x140027189  lea     r9, NbtConfig
0x140027190  and     r8d, [rsi+1E8h]
0x140027197  mov     rdx, cs:NbtConfig
0x14002719e  jmp     short loc_1400271BD
0x1400271a0  mov     ecx, [rdx+94h]
0x1400271a6  and     ecx, [rdx+90h]
0x1400271ac  cmp     r8d, ecx
0x1400271af  jnz     short loc_1400271BA
0x1400271b1  cmp     dword ptr [rdx+204h], 0
0x1400271b8  jnz     short loc_1400271C4
0x1400271ba  mov     rdx, [rdx]
0x1400271bd  cmp     rdx, r9
0x1400271c0  jnz     short loc_1400271A0
0x1400271c2  jmp     short loc_1400271C9
0x1400271c4  bts     dword ptr [rbx+10h], 0Ch
0x1400271c9  mov     dl, al; NewIrql
0x1400271cb  lea     rcx, SpinLock; SpinLock
0x1400271d2  call    cs:__imp_KeReleaseSpinLock
0x1400271d9  nop     dword ptr [rax+rax+00h]
0x1400271de  mov     rbx, [rsp+38h+arg_0]
0x1400271e3  xor     eax, eax
0x1400271e5  mov     rsi, [rsp+38h+arg_8]
0x1400271ea  add     rsp, 30h
0x1400271ee  pop     rdi
0x1400271ef  retn
```
