# GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))

- ea: `0x140036ab8`
- end: `0x140036b20`
- name: `?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z`
- size: `104`
- prototype: `__int64 __fastcall(GdiIdxPfnPairs *__hidden this, int, unsigned int, __int64 (*)(void))`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140036b30`

## callees

- `0x140036ab8`

## pseudocode

```c
__int64 __fastcall GdiIdxPfnPairs::UpdateEntry(GdiIdxPfnPairs *this, int a2, int a3, __int64 (*a4)(void))
{
  unsigned int v5; // ecx
  __int64 v6; // r11

  v5 = 0;
  v6 = *((unsigned int *)this + 3);
  while ( v5 < (unsigned int)v6 )
  {
    if ( *(_DWORD *)(*(_QWORD *)this + 16LL * v5) == a3 )
    {
      *(_QWORD *)(*(_QWORD *)this + 16LL * v5 + 8) = a4;
      return 1;
    }
    ++v5;
  }
  if ( a2 && (unsigned int)v6 < *((_DWORD *)this + 2) )
  {
    *(_DWORD *)(*(_QWORD *)this + 16 * v6) = a3;
    *(_QWORD *)(*(_QWORD *)this + 16LL * (unsigned int)(*((_DWORD *)this + 3))++ + 8) = a4;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140036ab8  mov     [rsp+arg_0], rbx
0x140036abd  mov     r10, rcx
0x140036ac0  mov     ebx, edx
0x140036ac2  xor     ecx, ecx
0x140036ac4  mov     r11d, [r10+0Ch]
0x140036ac8  cmp     ecx, r11d
0x140036acb  jnb     short loc_140036AEB
0x140036acd  mov     rdx, [r10]
0x140036ad0  mov     eax, ecx
0x140036ad2  add     rax, rax
0x140036ad5  cmp     [rdx+rax*8], r8d
0x140036ad9  jz      short loc_140036ADF
0x140036adb  inc     ecx
0x140036add  jmp     short loc_140036AC8
0x140036adf  mov     [rdx+rax*8+8], r9
0x140036ae4  mov     eax, 1
0x140036ae9  jmp     short loc_140036B19
0x140036aeb  test    ebx, ebx
0x140036aed  jz      short loc_140036B17
0x140036aef  cmp     r11d, [r10+8]
0x140036af3  jnb     short loc_140036B17
0x140036af5  mov     rax, [r10]
0x140036af8  mov     rcx, r11
0x140036afb  add     rcx, rcx
0x140036afe  mov     [rax+rcx*8], r8d
0x140036b02  mov     ecx, [r10+0Ch]
0x140036b06  mov     rax, [r10]
0x140036b09  add     rcx, rcx
0x140036b0c  mov     [rax+rcx*8+8], r9
0x140036b11  inc     dword ptr [r10+0Ch]
0x140036b15  jmp     short loc_140036AE4
0x140036b17  xor     eax, eax
0x140036b19  mov     rbx, [rsp+arg_0]
0x140036b1e  retn
```
