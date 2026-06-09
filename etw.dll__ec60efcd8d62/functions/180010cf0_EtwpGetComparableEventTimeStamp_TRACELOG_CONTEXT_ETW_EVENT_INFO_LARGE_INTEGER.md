# EtwpGetComparableEventTimeStamp(_TRACELOG_CONTEXT *,_ETW_EVENT_INFO *,_LARGE_INTEGER *)

- ea: `0x180010cf0`
- end: `0x180010d3e`
- name: `?EtwpGetComparableEventTimeStamp@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_ETW_EVENT_INFO@@PEAT_LARGE_INTEGER@@@Z`
- size: `78`
- prototype: `void __fastcall(struct _TRACELOG_CONTEXT *, struct _ETW_EVENT_INFO *, union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014558`
- `0x180014688`
- `0x180015578`

## callees

- `0x180010cf0`

## pseudocode

```c
void __fastcall EtwpGetComparableEventTimeStamp(
        struct _TRACELOG_CONTEXT *a1,
        struct _ETW_EVENT_INFO *a2,
        union _LARGE_INTEGER *a3)
{
  bool v3; // zf
  LONGLONG v5; // r11
  __int64 v6; // r8
  unsigned int v7; // eax

  v3 = (*((_DWORD *)a1 + 8) & 0x10000000) == 0;
  v5 = *((_QWORD *)a2 + 2);
  a3->QuadPart = v5;
  if ( !v3 && *((_DWORD *)a1 + 10) == 1 && *((_WORD *)a2 + 42) )
  {
    v6 = *((_QWORD *)a2 + 11);
    v7 = 0;
    while ( *(_WORD *)(v6 + 16LL * v7 + 2) != 15 )
    {
      if ( ++v7 >= *((unsigned __int16 *)a2 + 42) )
        return;
    }
    a3->QuadPart = v5 + **(_QWORD **)(v6 + 16LL * v7 + 8);
  }
}

```

## disassembly

```asm
0x180010cf0  test    dword ptr [rcx+20h], 10000000h
0x180010cf7  mov     r10, r8
0x180010cfa  mov     r11, [rdx+10h]
0x180010cfe  mov     [r8], r11
0x180010d01  jz      short locret_180010D3D
0x180010d03  cmp     dword ptr [rcx+28h], 1
0x180010d07  jnz     short locret_180010D3D
0x180010d09  movzx   r9d, word ptr [rdx+54h]
0x180010d0e  test    r9d, r9d
0x180010d11  jz      short locret_180010D3D
0x180010d13  mov     r8, [rdx+58h]
0x180010d17  xor     eax, eax
0x180010d19  mov     ecx, eax
0x180010d1b  add     rcx, rcx
0x180010d1e  cmp     word ptr [r8+rcx*8+2], 0Fh
0x180010d25  jz      short loc_180010D2F
0x180010d27  inc     eax
0x180010d29  cmp     eax, r9d
0x180010d2c  jb      short loc_180010D19
0x180010d2e  retn
0x180010d2f  mov     rax, [r8+rcx*8+8]
0x180010d34  mov     rax, [rax]
0x180010d37  add     rax, r11
0x180010d3a  mov     [r10], rax
0x180010d3d  retn
```
