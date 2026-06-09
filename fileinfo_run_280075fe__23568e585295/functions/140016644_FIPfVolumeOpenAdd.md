# FIPfVolumeOpenAdd

- ea: `0x140016644`
- end: `0x1400166ac`
- name: `FIPfVolumeOpenAdd`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017700`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140016644`

## pseudocode

```c
__int64 __fastcall FIPfVolumeOpenAdd(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rsi
  _QWORD *v5; // rcx

  v2 = a1 + 136;
  FILockExclusiveAcquire(a1 + 136);
  v5 = *(_QWORD **)(a1 + 168);
  if ( *v5 != a1 + 160 )
    __fastfail(3u);
  a2[1] = v5;
  *a2 = a1 + 160;
  *v5 = a2;
  *(_QWORD *)(a1 + 168) = a2;
  ++*(_DWORD *)(a1 + 212);
  return FILockExclusiveRelease(v2);
}

```

## disassembly

```asm
0x140016644  mov     [rsp+arg_0], rbx
0x140016649  mov     [rsp+arg_8], rsi
0x14001664e  push    rdi
0x14001664f  sub     rsp, 20h
0x140016653  lea     rsi, [rcx+88h]
0x14001665a  mov     rdi, rcx
0x14001665d  mov     rcx, rsi
0x140016660  mov     rbx, rdx
0x140016663  call    FILockExclusiveAcquire
0x140016668  lea     rax, [rdi+0A0h]
0x14001666f  mov     rcx, [rax+8]
0x140016673  cmp     [rcx], rax
0x140016676  jz      short loc_14001667F
0x140016678  mov     ecx, 3
0x14001667d  int     29h; Win8: RtlFailFast(ecx)
0x14001667f  mov     [rbx+8], rcx
0x140016683  mov     [rbx], rax
0x140016686  mov     [rcx], rbx
0x140016689  mov     rcx, rsi
0x14001668c  mov     [rax+8], rbx
0x140016690  inc     dword ptr [rdi+0D4h]
0x140016696  call    FILockExclusiveRelease
0x14001669b  mov     rbx, [rsp+28h+arg_0]
0x1400166a0  mov     rsi, [rsp+28h+arg_8]
0x1400166a5  add     rsp, 20h
0x1400166a9  pop     rdi
0x1400166aa  retn
```
