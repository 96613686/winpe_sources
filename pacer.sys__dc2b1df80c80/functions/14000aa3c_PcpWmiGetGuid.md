# PcpWmiGetGuid

- ea: `0x14000aa3c`
- end: `0x14000aa9b`
- name: `PcpWmiGetGuid`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400107dc`
- `0x140010c70`
- `0x14001f5fc`
- `0x14001f650`

## callees

- `0x14000aa3c`

## pseudocode

```c
__int64 __fastcall PcpWmiGetGuid(__int64 **a1, _QWORD *a2, int a3)
{
  __int64 *v4; // r9
  unsigned int v5; // r10d
  unsigned int i; // r11d
  bool v7; // zf
  __int64 v9; // rcx

  v4 = PcgSupportedGuids;
  v5 = -1073741823;
  for ( i = 0; i < 0x18; ++i )
  {
    if ( a2 )
    {
      v9 = *v4 - *a2;
      if ( *v4 == *a2 )
        v9 = v4[1] - a2[1];
      v7 = v9 == 0;
    }
    else
    {
      if ( (v4[3] & 2) == 0 )
        goto LABEL_5;
      v7 = *((_DWORD *)v4 + 4) == a3;
    }
    if ( v7 )
    {
      *a1 = v4;
      return 0;
    }
LABEL_5:
    v4 = (__int64 *)((char *)v4 + 28);
  }
  return v5;
}

```

## disassembly

```asm
0x14000aa3c  mov     [rsp+arg_0], rbx
0x14000aa41  mov     rbx, rcx
0x14000aa44  lea     r9, PcgSupportedGuids
0x14000aa4b  mov     r10d, 0C0000001h
0x14000aa51  xor     r11d, r11d
0x14000aa54  cmp     r11d, 18h
0x14000aa58  jnb     short loc_14000AA7C
0x14000aa5a  test    rdx, rdx
0x14000aa5d  jnz     short loc_14000AA86
0x14000aa5f  mov     eax, [r9+18h]
0x14000aa63  test    al, 2
0x14000aa65  jnz     short loc_14000AA70
0x14000aa67  inc     r11d
0x14000aa6a  add     r9, 1Ch
0x14000aa6e  jmp     short loc_14000AA54
0x14000aa70  cmp     [r9+10h], r8d
0x14000aa74  jnz     short loc_14000AA67
0x14000aa76  mov     [rbx], r9
0x14000aa79  xor     r10d, r10d
0x14000aa7c  mov     rbx, [rsp+arg_0]
0x14000aa81  mov     eax, r10d
0x14000aa84  retn
0x14000aa86  mov     rcx, [r9]
0x14000aa89  sub     rcx, [rdx]
0x14000aa8c  jnz     short loc_14000AA96
0x14000aa8e  mov     rcx, [r9+8]
0x14000aa92  sub     rcx, [rdx+8]
0x14000aa96  test    rcx, rcx
0x14000aa99  jmp     short loc_14000AA74
```
