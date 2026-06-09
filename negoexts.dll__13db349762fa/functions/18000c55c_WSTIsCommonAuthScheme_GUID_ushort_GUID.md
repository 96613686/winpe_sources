# WSTIsCommonAuthScheme(_GUID *,ushort,_GUID *)

- ea: `0x18000c55c`
- end: `0x18000c59b`
- name: `?WSTIsCommonAuthScheme@@YAHPEAU_GUID@@G0@Z`
- size: `63`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16, struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001414`
- `0x18001a3b4`

## callees

- `0x18000c55c`

## pseudocode

```c
_BOOL8 __fastcall WSTIsCommonAuthScheme(struct _GUID *a1, unsigned __int16 a2, struct _GUID *a3)
{
  int v3; // r9d
  unsigned int i; // eax
  __int64 v6; // rcx

  v3 = -1;
  for ( i = 0; i < a2; ++i )
  {
    v6 = *(_QWORD *)&a1[i].Data1 - *(_QWORD *)&a3->Data1;
    if ( !v6 )
      v6 = *(_QWORD *)a1[i].Data4 - *(_QWORD *)a3->Data4;
    if ( !v6 )
    {
      v3 = i;
      return v3 != -1;
    }
  }
  return v3 != -1;
}

```

## disassembly

```asm
0x18000c55c  or      r9d, 0FFFFFFFFh
0x18000c560  movzx   r10d, dx
0x18000c564  xor     eax, eax
0x18000c566  mov     r11, rcx
0x18000c569  cmp     eax, r10d
0x18000c56c  jnb     short loc_18000C58D
0x18000c56e  mov     edx, eax
0x18000c570  add     rdx, rdx
0x18000c573  mov     rcx, [r11+rdx*8]
0x18000c577  sub     rcx, [r8]
0x18000c57a  jnz     short loc_18000C585
0x18000c57c  mov     rcx, [r11+rdx*8+8]
0x18000c581  sub     rcx, [r8+8]
0x18000c585  test    rcx, rcx
0x18000c588  jnz     short loc_18000C597
0x18000c58a  mov     r9d, eax
0x18000c58d  xor     eax, eax
0x18000c58f  cmp     r9d, 0FFFFFFFFh
0x18000c593  setnz   al
0x18000c596  retn
0x18000c597  inc     eax
0x18000c599  jmp     short loc_18000C569
```
