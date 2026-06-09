# PcpIoctlDeleteFlow

- ea: `0x140005438`
- end: `0x140005570`
- name: `PcpIoctlDeleteFlow`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140020b50`

## callees

- `0x140003934`
- `0x140005438`
- `0x140005578`
- `0x14000577c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400054be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400054eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005531`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400054be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400054eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005531`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005498`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005498`

## pseudocode

```c
__int64 __fastcall PcpIoctlDeleteFlow(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  __int64 v5; // rdi
  int Flow; // ebx
  __int64 v7; // rsi
  __int64 v8; // rbx
  KSPIN_LOCK *v9; // r14
  KIRQL v10; // r15
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  __int64 v13; // rdx

  if ( *(_DWORD *)(a2 + 8) < 0x18u )
    return 3221225507LL;
  v5 = *(_QWORD *)(a1 + 24);
  if ( *(_DWORD *)(a2 + 16) >= 0x10u )
  {
    v7 = *(_QWORD *)(v5 + 8);
    if ( v7 )
    {
      v8 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
      v9 = (KSPIN_LOCK *)(v8 + 32);
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 32));
      Flow = PcpFindFlow((_QWORD *)v7, v8);
      if ( Flow >= 0 )
      {
        RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)(v7 + 96));
        if ( *(_QWORD *)(v7 + 568) == v7 + 568 )
        {
          v11 = *(_QWORD *)(v7 + 16);
          if ( *(_QWORD *)(v11 + 8) != v7 + 16 || (v12 = *(_QWORD **)(v7 + 24), *v12 != v7 + 16) )
            __fastfail(3u);
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          _InterlockedDecrement((volatile signed __int32 *)(v7 + 104));
          KeReleaseSpinLock(v9, v10);
          v13 = *(_QWORD *)(v7 + 592);
          *(_QWORD *)(v5 + 16) = v13;
          *(_QWORD *)(v5 + 8) = 0;
          PcpDeleteFlow((char *)v7, v13);
          goto LABEL_15;
        }
        _InterlockedDecrement((volatile signed __int32 *)(v7 + 104));
        KeReleaseSpinLock(v9, v10);
        Flow = -1073741567;
      }
      else
      {
        KeReleaseSpinLock(v9, v10);
      }
    }
    else
    {
      Flow = -1073741275;
    }
  }
  else
  {
    Flow = -1073741789;
  }
  *(_OWORD *)v5 = 0;
  *(_QWORD *)(v5 + 16) = 0;
LABEL_15:
  *(_DWORD *)v5 = Flow;
  result = (unsigned int)Flow;
  *a3 = 24;
  return result;
}

```

## disassembly

```asm
0x140005438  push    rbx
0x14000543a  push    rbp
0x14000543b  push    rsi
0x14000543c  push    rdi
0x14000543d  push    r12
0x14000543f  push    r14
0x140005441  push    r15
0x140005443  sub     rsp, 20h
0x140005447  cmp     dword ptr [rdx+8], 18h
0x14000544b  mov     r12, r8
0x14000544e  jnb     short loc_140005465
0x140005450  mov     eax, 0C0000023h
0x140005455  add     rsp, 20h
0x140005459  pop     r15
0x14000545b  pop     r14
0x14000545d  pop     r12
0x14000545f  pop     rdi
0x140005460  pop     rsi
0x140005461  pop     rbp
0x140005462  pop     rbx
0x140005463  retn
0x140005465  cmp     dword ptr [rdx+10h], 10h
0x140005469  mov     rdi, [rcx+18h]
0x14000546d  jnb     short loc_140005479
0x14000546f  mov     ebx, 0C0000023h
0x140005474  jmp     loc_1400054FC
0x140005479  mov     rsi, [rdi+8]
0x14000547d  test    rsi, rsi
0x140005480  jnz     short loc_140005489
0x140005482  mov     ebx, 0C0000225h
0x140005487  jmp     short loc_1400054FC
0x140005489  mov     rax, [rdx+30h]
0x14000548d  mov     rbx, [rax+18h]
0x140005491  lea     r14, [rbx+20h]
0x140005495  mov     rcx, r14; SpinLock
0x140005498  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000549f  nop     dword ptr [rax+rax+00h]
0x1400054a4  mov     rdx, rbx
0x1400054a7  mov     rcx, rsi
0x1400054aa  mov     r15b, al
0x1400054ad  call    PcpFindFlow
0x1400054b2  mov     ebx, eax
0x1400054b4  test    eax, eax
0x1400054b6  jns     short loc_1400054CC
0x1400054b8  mov     dl, r15b; NewIrql
0x1400054bb  mov     rcx, r14; SpinLock
0x1400054be  call    cs:__imp_KeReleaseSpinLock
0x1400054c5  nop     dword ptr [rax+rax+00h]
0x1400054ca  jmp     short loc_1400054FC
0x1400054cc  lea     rcx, [rsi+60h]; SpinLock
0x1400054d0  call    RtlAcquireReadLockAtDpcLevel
0x1400054d5  lea     rax, [rsi+238h]
0x1400054dc  cmp     [rax], rax
0x1400054df  jz      short loc_14000550A
0x1400054e1  lock dec dword ptr [rsi+68h]
0x1400054e5  mov     dl, r15b; NewIrql
0x1400054e8  mov     rcx, r14; SpinLock
0x1400054eb  call    cs:__imp_KeReleaseSpinLock
0x1400054f2  nop     dword ptr [rax+rax+00h]
0x1400054f7  mov     ebx, 0C0000101h
0x1400054fc  xorps   xmm0, xmm0
0x1400054ff  xor     eax, eax
0x140005501  movups  xmmword ptr [rdi], xmm0
0x140005504  mov     [rdi+10h], rax
0x140005508  jmp     short loc_140005558
0x14000550a  lea     rax, [rsi+10h]
0x14000550e  mov     rcx, [rax]
0x140005511  cmp     [rcx+8], rax
0x140005515  jnz     short loc_140005569
0x140005517  mov     rdx, [rax+8]
0x14000551b  cmp     [rdx], rax
0x14000551e  jnz     short loc_140005569
0x140005520  mov     [rdx], rcx
0x140005523  mov     [rcx+8], rdx
0x140005527  mov     dl, r15b; NewIrql
0x14000552a  lock dec dword ptr [rsi+68h]
0x14000552e  mov     rcx, r14; SpinLock
0x140005531  call    cs:__imp_KeReleaseSpinLock
0x140005538  nop     dword ptr [rax+rax+00h]
0x14000553d  mov     rdx, [rsi+250h]
0x140005544  mov     rcx, rsi; P
0x140005547  mov     [rdi+10h], rdx
0x14000554b  mov     qword ptr [rdi+8], 0
0x140005553  call    PcpDeleteFlow
0x140005558  mov     [rdi], ebx
0x14000555a  mov     eax, ebx
0x14000555c  mov     dword ptr [r12], 18h
0x140005564  jmp     loc_140005455
0x140005569  mov     ecx, 3
0x14000556e  int     29h; Win8: RtlFailFast(ecx)
```
