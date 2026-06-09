# EtwpUpdateStreamQpcDelta(_TRACE_STREAM_CONTEXT *)

- ea: `0x180012d64`
- end: `0x180012e0a`
- name: `?EtwpUpdateStreamQpcDelta@@YAXPEAU_TRACE_STREAM_CONTEXT@@@Z`
- size: `166`
- prototype: `void __fastcall(struct _TRACE_STREAM_CONTEXT *)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000ece4`
- `0x18000f384`
- `0x1800108d0`

## callees

- `0x180012d64`

## pseudocode

```c
void __fastcall EtwpUpdateStreamQpcDelta(struct _TRACE_STREAM_CONTEXT *a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // r8
  unsigned int v3; // ecx
  __int64 v4; // rax

  if ( *(_DWORD *)(*((_QWORD *)a1 + 8) + 40LL) != 3 )
  {
    v1 = *((_QWORD *)a1 + 7);
    if ( *(_BYTE *)(v1 + 45) == 81
      && *(_BYTE *)(v1 + 42) == 2
      && *(_WORD *)(v1 + 86) >= 8u
      && *(_QWORD *)(v1 + 24) == *(_QWORD *)&EventTraceGuid.Data1
      && *(_QWORD *)(v1 + 32) == *(_QWORD *)EventTraceGuid.Data4 )
    {
      v2 = (_QWORD *)((char *)a1 + 120);
      *((_QWORD *)a1 + 15) = **(_QWORD **)(v1 + 96);
    }
    else
    {
      v2 = (_QWORD *)((char *)a1 + 120);
    }
    if ( *v2 )
    {
      v3 = *(unsigned __int16 *)(v1 + 84);
      *(_WORD *)(v1 + 4) |= 1u;
      *(_QWORD *)(v1 + 88) = v1 + 136;
      *(_WORD *)(v1 + 84) = v3 + 1;
      v4 = 2LL * v3;
      *(_OWORD *)(v1 + 8 * v4 + 136) = 0;
      *(_WORD *)(v1 + 8 * v4 + 138) = 15;
      *(_WORD *)(v1 + 8 * v4 + 142) = 8;
      *(_QWORD *)(v1 + 8 * v4 + 144) = v2;
    }
  }
}

```

## disassembly

```asm
0x180012d64  mov     rax, [rcx+40h]
0x180012d68  cmp     dword ptr [rax+28h], 3
0x180012d6c  jz      locret_180012E09
0x180012d72  mov     rdx, [rcx+38h]
0x180012d76  mov     r9d, 8
0x180012d7c  cmp     byte ptr [rdx+2Dh], 51h ; 'Q'
0x180012d80  jnz     short loc_180012DB9
0x180012d82  cmp     byte ptr [rdx+2Ah], 2
0x180012d86  jnz     short loc_180012DB9
0x180012d88  cmp     [rdx+56h], r9w
0x180012d8d  jb      short loc_180012DB9
0x180012d8f  mov     rax, [rdx+18h]
0x180012d93  cmp     rax, qword ptr cs:EventTraceGuid.Data1
0x180012d9a  jnz     short loc_180012DB9
0x180012d9c  mov     rax, [rdx+20h]
0x180012da0  cmp     rax, qword ptr cs:EventTraceGuid.Data4
0x180012da7  jnz     short loc_180012DB9
0x180012da9  mov     rax, [rdx+60h]
0x180012dad  lea     r8, [rcx+78h]
0x180012db1  mov     rcx, [rax]
0x180012db4  mov     [r8], rcx
0x180012db7  jmp     short loc_180012DBD
0x180012db9  lea     r8, [rcx+78h]
0x180012dbd  cmp     qword ptr [r8], 0
0x180012dc1  jz      short locret_180012E09
0x180012dc3  movzx   ecx, word ptr [rdx+54h]
0x180012dc7  lea     rax, [rdx+88h]
0x180012dce  or      word ptr [rdx+4], 1
0x180012dd3  xorps   xmm0, xmm0
0x180012dd6  mov     [rdx+58h], rax
0x180012dda  lea     eax, [rcx+1]
0x180012ddd  mov     [rdx+54h], ax
0x180012de1  mov     eax, ecx
0x180012de3  add     rax, rax
0x180012de6  movups  xmmword ptr [rdx+rax*8+88h], xmm0
0x180012dee  mov     word ptr [rdx+rax*8+8Ah], 0Fh
0x180012df8  mov     [rdx+rax*8+8Eh], r9w
0x180012e01  mov     [rdx+rax*8+90h], r8
0x180012e09  retn
```
