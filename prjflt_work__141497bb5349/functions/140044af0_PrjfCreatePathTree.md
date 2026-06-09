# PrjfCreatePathTree

- ea: `0x140044af0`
- end: `0x140044bae`
- name: `PrjfCreatePathTree`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14004437c`
- `0x140044794`
- `0x140044cec`

## callees

- `0x14000d008`
- `0x140044af0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140044b10`
- `ntoskrnl!ExAllocatePool2` at `0x140044b10`

## pseudocode

```c
__int64 __fastcall PrjfCreatePathTree(_QWORD *a1)
{
  _QWORD *Pool2; // rax
  int v3; // edx
  int v4; // r8d

  *a1 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(256, 16, 1835944528);
  if ( Pool2 )
  {
    *Pool2 = 0;
    Pool2[1] = 0;
    *a1 = Pool2;
    return 0;
  }
  else
  {
    if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = BYTE2(xmmword_14001A3D0) & 0x10;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        532,
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        20,
        37,
        (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
        104);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140044af0  push    rbx
0x140044af2  sub     rsp, 50h
0x140044af6  mov     rbx, rcx
0x140044af9  mov     qword ptr [rcx], 0
0x140044b00  mov     ecx, 100h
0x140044b05  mov     edx, 10h
0x140044b0a  mov     r8d, 6D6E4A50h
0x140044b10  call    cs:__imp_ExAllocatePool2
0x140044b17  nop     dword ptr [rax+rax+00h]
0x140044b1c  test    rax, rax
0x140044b1f  jnz     short loc_140044B93
0x140044b21  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044b27  lea     rax, WPP_RECORDER_INITIALIZED
0x140044b2e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044b35  setnz   r8b
0x140044b39  and     dl, 10h
0x140044b3c  jnz     short loc_140044B43
0x140044b3e  test    r8b, r8b
0x140044b41  jz      short loc_140044B8C
0x140044b43  mov     r9, cs:WPP_GLOBAL_Control
0x140044b4a  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044b51  mov     [rsp+58h+var_10], 468h
0x140044b59  mov     ecx, 214h
0x140044b5e  mov     [rsp+58h+var_18], rax
0x140044b63  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044b6a  mov     [rsp+58h+var_20], rax
0x140044b6f  mov     r9, [r9+40h]
0x140044b73  mov     [rsp+58h+var_28], 25h ; '%'
0x140044b7a  mov     [rsp+58h+var_30], 14h
0x140044b82  mov     [rsp+58h+var_38], 2
0x140044b87  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140044b8c  mov     eax, 0C000009Ah
0x140044b91  jmp     short loc_140044BA7
0x140044b93  mov     qword ptr [rax], 0
0x140044b9a  mov     qword ptr [rax+8], 0
0x140044ba2  mov     [rbx], rax
0x140044ba5  xor     eax, eax
0x140044ba7  add     rsp, 50h
0x140044bab  pop     rbx
0x140044bac  retn
```
