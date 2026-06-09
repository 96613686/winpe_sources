# NewLinkCross

- ea: `0x14005e23c`
- end: `0x14005e298`
- name: `NewLinkCross`
- size: `92`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14005e0d0`
- `0x14006b1bc`
- `0x14008d5a8`
- `0x14008dd20`

## callees

- `0x14005e23c`
- `0x1400675a0`

## pseudocode

```c
_QWORD *NewLinkCross()
{
  _QWORD *v0; // rbx
  bool v1; // cf
  bool v2; // zf
  _QWORD *result; // rax

  v0 = CS_currentCross;
  CS_currentCross = (char *)CS_currentCross + 24;
  v1 = (unsigned __int64)v0 < CS_limitCross;
  v2 = v0 == (_QWORD *)CS_limitCross;
  if ( v0 == (_QWORD *)CS_limitCross )
  {
    os_raise(4294967292LL, 0);
    v1 = (unsigned __int64)v0 < CS_limitCross;
    v2 = v0 == (_QWORD *)CS_limitCross;
  }
  if ( !v1 && !v2 )
    os_raise(0xFFFFFFFFLL, 0);
  *(_WORD *)v0 = 12288;
  result = v0;
  v0[2] = 0;
  return result;
}

```

## disassembly

```asm
0x14005e23c  push    rbx
0x14005e23e  sub     rsp, 20h
0x14005e242  mov     rbx, cs:CS_currentCross
0x14005e249  mov     rcx, cs:CS_limitCross
0x14005e250  lea     rax, [rbx+18h]
0x14005e254  mov     cs:CS_currentCross, rax
0x14005e25b  cmp     rbx, rcx
0x14005e25e  jnz     short loc_14005E276
0x14005e260  xor     edx, edx
0x14005e262  mov     ecx, 0FFFFFFFCh
0x14005e267  call    os_raise
0x14005e26c  mov     rcx, cs:CS_limitCross
0x14005e273  cmp     rbx, rcx
0x14005e276  jbe     short loc_14005E282
0x14005e278  xor     edx, edx
0x14005e27a  or      ecx, 0FFFFFFFFh
0x14005e27d  call    os_raise
0x14005e282  mov     word ptr [rbx], 3000h
0x14005e287  mov     rax, rbx
0x14005e28a  mov     qword ptr [rbx+10h], 0
0x14005e292  add     rsp, 20h
0x14005e296  pop     rbx
0x14005e297  retn
```
