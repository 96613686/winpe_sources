# EtwpUpdateBufferEntryQpcDelta(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)

- ea: `0x180012cc0`
- end: `0x180012d5c`
- name: `?EtwpUpdateBufferEntryQpcDelta@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z`
- size: `156`
- prototype: `void __fastcall(struct _TRACELOG_CONTEXT *, struct _TRACE_BUFFER_LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180014b10`
- `0x180014e88`
- `0x18001502c`

## callees

- `0x180012cc0`

## pseudocode

```c
void __fastcall EtwpUpdateBufferEntryQpcDelta(struct _TRACELOG_CONTEXT *a1, struct _TRACE_BUFFER_LIST_ENTRY *a2)
{
  _QWORD *v3; // r9
  unsigned int v4; // ecx
  char *v5; // rdx
  __int64 v6; // rax

  if ( *((_DWORD *)a1 + 10) != 3 )
  {
    if ( *((_BYTE *)a2 + 85) == 81
      && *((_BYTE *)a2 + 82) == 2
      && *((_WORD *)a2 + 63) >= 8u
      && *((_QWORD *)a2 + 8) == *(_QWORD *)&EventTraceGuid.Data1
      && *((_QWORD *)a2 + 9) == *(_QWORD *)EventTraceGuid.Data4 )
    {
      v3 = (_QWORD *)((char *)a2 + 32);
      *((_QWORD *)a2 + 4) = **((_QWORD **)a2 + 17);
    }
    else
    {
      v3 = (_QWORD *)((char *)a2 + 32);
    }
    if ( *v3 )
    {
      v4 = *((unsigned __int16 *)a2 + 62);
      *((_WORD *)a2 + 22) |= 1u;
      v5 = (char *)a2 + 176;
      *((_QWORD *)a2 + 16) = v5;
      *((_WORD *)a2 + 62) = v4 + 1;
      v6 = 2LL * v4;
      *(_OWORD *)&v5[8 * v6] = 0;
      *(_WORD *)&v5[8 * v6 + 2] = 15;
      *(_WORD *)&v5[8 * v6 + 6] = 8;
      *(_QWORD *)&v5[8 * v6 + 8] = v3;
    }
  }
}

```

## disassembly

```asm
0x180012cc0  cmp     dword ptr [rcx+28h], 3
0x180012cc4  mov     r8, rdx
0x180012cc7  jz      locret_180012D5B
0x180012ccd  cmp     byte ptr [rdx+55h], 51h ; 'Q'
0x180012cd1  mov     r10d, 8
0x180012cd7  jnz     short loc_180012D13
0x180012cd9  cmp     byte ptr [rdx+52h], 2
0x180012cdd  jnz     short loc_180012D13
0x180012cdf  cmp     [rdx+7Eh], r10w
0x180012ce4  jb      short loc_180012D13
0x180012ce6  mov     rax, [rdx+40h]
0x180012cea  cmp     rax, qword ptr cs:EventTraceGuid.Data1
0x180012cf1  jnz     short loc_180012D13
0x180012cf3  mov     rax, [rdx+48h]
0x180012cf7  cmp     rax, qword ptr cs:EventTraceGuid.Data4
0x180012cfe  jnz     short loc_180012D13
0x180012d00  mov     rax, [rdx+88h]
0x180012d07  lea     r9, [rdx+20h]
0x180012d0b  mov     rcx, [rax]
0x180012d0e  mov     [r9], rcx
0x180012d11  jmp     short loc_180012D17
0x180012d13  lea     r9, [rdx+20h]
0x180012d17  cmp     qword ptr [r9], 0
0x180012d1b  jz      short locret_180012D5B
0x180012d1d  movzx   ecx, word ptr [r8+7Ch]
0x180012d22  xorps   xmm0, xmm0
0x180012d25  or      word ptr [rdx+2Ch], 1
0x180012d2a  add     rdx, 0B0h
0x180012d31  mov     [r8+80h], rdx
0x180012d38  lea     eax, [rcx+1]
0x180012d3b  mov     [r8+7Ch], ax
0x180012d40  mov     eax, ecx
0x180012d42  add     rax, rax
0x180012d45  movups  xmmword ptr [rdx+rax*8], xmm0
0x180012d49  mov     word ptr [rdx+rax*8+2], 0Fh
0x180012d50  mov     [rdx+rax*8+6], r10w
0x180012d56  mov     [rdx+rax*8+8], r9
0x180012d5b  retn
```
