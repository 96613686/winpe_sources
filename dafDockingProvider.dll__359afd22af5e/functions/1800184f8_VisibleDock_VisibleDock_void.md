# VisibleDock::~VisibleDock(void)

- ea: `0x1800184f8`
- end: `0x180018538`
- name: `??1VisibleDock@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(VisibleDock *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180018310`
- `0x1800183d4`
- `0x180018540`
- `0x18001884c`
- `0x1800195cc`
- `0x180019be0`
- `0x18001a0ac`
- `0x18001dcff`
- `0x18001df38`

## callees

- `0x18000c308`
- `0x1800184f8`

## pseudocode

```c
void __fastcall VisibleDock::~VisibleDock(VisibleDock *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids, this);
  }
}

```

## disassembly

```asm
0x1800184f8  sub     rsp, 28h
0x1800184fc  mov     r9, rcx
0x1800184ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180018506  lea     rax, WPP_GLOBAL_Control
0x18001850d  cmp     rcx, rax
0x180018510  jz      short loc_180018533
0x180018512  cmp     byte ptr [rcx+19h], 4
0x180018516  jb      short loc_180018533
0x180018518  test    byte ptr [rcx+1Ch], 1
0x18001851c  jz      short loc_180018533
0x18001851e  mov     rcx, [rcx+10h]
0x180018522  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x180018529  mov     edx, 0Dh
0x18001852e  call    WPP_SF_q
0x180018533  add     rsp, 28h
0x180018537  retn
```
