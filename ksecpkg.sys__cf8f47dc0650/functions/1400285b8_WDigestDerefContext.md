# WDigestDerefContext

- ea: `0x1400285b8`
- end: `0x1400285f9`
- name: `WDigestDerefContext`
- size: `65`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140021520`
- `0x140021590`
- `0x140021790`
- `0x1400286c0`
- `0x140028790`
- `0x140028800`
- `0x140028e50`

## callees

- `0x1400089e0`
- `0x1400285b8`
- `0x140028600`

## pseudocode

```c
__int64 __fastcall WDigestDerefContext(__int64 a1, int a2)
{
  signed __int32 v3; // eax
  bool v4; // zf
  __int64 result; // rax

  v3 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF);
  v4 = v3 == 1;
  result = (unsigned int)(v3 - 1);
  if ( v4 && a2 )
  {
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(a1 + 28));
    if ( !(_DWORD)result )
    {
      DigestUnMapLsaToKernelContext(*(_QWORD *)(a1 + 8), a1);
      return WDigestFreeKernelContext(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400285b8  push    rbx
0x1400285ba  sub     rsp, 20h
0x1400285be  mov     rbx, rcx
0x1400285c1  or      ecx, 0FFFFFFFFh
0x1400285c4  mov     eax, ecx
0x1400285c6  lock xadd [rbx+18h], eax
0x1400285cb  add     eax, ecx
0x1400285cd  jnz     short loc_1400285F2
0x1400285cf  test    edx, edx
0x1400285d1  jz      short loc_1400285F2
0x1400285d3  mov     eax, ecx
0x1400285d5  lock xadd [rbx+1Ch], eax
0x1400285da  add     eax, ecx
0x1400285dc  jnz     short loc_1400285F2
0x1400285de  mov     rcx, [rbx+8]; unsigned __int64
0x1400285e2  mov     rdx, rbx; unsigned __int64
0x1400285e5  call    ?DigestUnMapLsaToKernelContext@@YAJ_K0@Z; DigestUnMapLsaToKernelContext(unsigned __int64,unsigned __int64)
0x1400285ea  mov     rcx, rbx
0x1400285ed  call    WDigestFreeKernelContext
0x1400285f2  add     rsp, 20h
0x1400285f6  pop     rbx
0x1400285f7  retn
```
