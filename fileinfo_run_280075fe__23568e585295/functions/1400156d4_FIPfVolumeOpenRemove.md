# FIPfVolumeOpenRemove

- ea: `0x1400156d4`
- end: `0x14001574b`
- name: `FIPfVolumeOpenRemove`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400153a0`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x1400101c8`
- `0x1400156d4`
- `0x140015754`
- `0x1400165f4`

## pseudocode

```c
__int64 __fastcall FIPfVolumeOpenRemove(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  _DWORD *v7; // r11
  void *v8; // rbx

  v3 = a1 + 136;
  FILockExclusiveAcquire(a1 + 136);
  v8 = (void *)FIPfOpenListRemove(a1 + 160, a1 + 212, a2, a3);
  if ( !*v7 && *(_DWORD *)(a1 + 216) )
    FIPfBlockersRelease(a1 + 176);
  FILockExclusiveRelease(v3);
  return FIPfOpenContextDereference(v8);
}

```

## disassembly

```asm
0x1400156d4  push    rbx
0x1400156d6  push    rbp
0x1400156d7  push    rsi
0x1400156d8  push    rdi
0x1400156d9  sub     rsp, 28h
0x1400156dd  lea     rbp, [rcx+88h]
0x1400156e4  mov     rsi, rcx
0x1400156e7  mov     rcx, rbp
0x1400156ea  mov     rbx, r8
0x1400156ed  mov     rdi, rdx
0x1400156f0  call    FILockExclusiveAcquire
0x1400156f5  lea     r11, [rsi+0D4h]
0x1400156fc  mov     r9, rbx
0x1400156ff  mov     rdx, r11
0x140015702  lea     rcx, [rsi+0A0h]
0x140015709  mov     r8, rdi
0x14001570c  call    FIPfOpenListRemove
0x140015711  cmp     dword ptr [r11], 0
0x140015715  mov     rbx, rax
0x140015718  jnz     short loc_140015723
0x14001571a  cmp     dword ptr [rsi+0D8h], 0
0x140015721  jnz     short loc_14001573D
0x140015723  mov     rcx, rbp
0x140015726  call    FILockExclusiveRelease
0x14001572b  mov     rcx, rbx; P
0x14001572e  call    FIPfOpenContextDereference
0x140015733  add     rsp, 28h
0x140015737  pop     rdi
0x140015738  pop     rsi
0x140015739  pop     rbp
0x14001573a  pop     rbx
0x14001573b  retn
0x14001573d  lea     rcx, [rsi+0B0h]
0x140015744  call    FIPfBlockersRelease
0x140015749  jmp     short loc_140015723
```
