# PrjfRelPathToFullPath

- ea: `0x140033878`
- end: `0x1400339a0`
- name: `PrjfRelPathToFullPath`
- size: `296`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, const void *, const void *, unsigned __int16)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14002f5f0`
- `0x1400306f8`
- `0x140035238`
- `0x1400368c4`

## callees

- `0x14000bb80`
- `0x14000d128`
- `0x140033878`

## pseudocode

```c
__int64 __fastcall PrjfRelPathToFullPath(
        __int64 a1,
        unsigned __int16 a2,
        const void *a3,
        const void *a4,
        unsigned __int16 a5)
{
  __int64 v6; // rsi
  __int64 v9; // rax
  __int16 v10; // cx

  v6 = a2;
  if ( *(unsigned __int16 *)(a1 + 2) >= (unsigned __int64)(a2 + (unsigned int)a5) + 2 )
  {
    memmove(*(void **)(a1 + 8), a3, a2);
    v9 = *(_QWORD *)(a1 + 8);
    *(_WORD *)(v9 + v6) = 92;
    memmove((void *)(v6 + v9 + 2), a4, a5);
    if ( (unsigned __int16)(a5 + v6) >= (unsigned __int16)v6 )
    {
      if ( (unsigned __int16)(a5 + v6 + 2) < 2u )
        v10 = -1;
      else
        v10 = a5 + v6 + 2;
      *(_WORD *)a1 = v10;
      return (unsigned __int16)(a5 + v6) >= 0xFFFEu ? 0xC0000095 : 0;
    }
    else
    {
      *(_WORD *)a1 = -1;
      return 3221225621LL;
    }
  }
  else
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        13,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        125,
        35);
    }
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x140033878  push    rbx
0x14003387a  push    rsi
0x14003387b  push    rdi
0x14003387c  push    r14
0x14003387e  push    r15
0x140033880  sub     rsp, 60h
0x140033884  movzx   r11d, [rsp+88h+arg_20]
0x14003388d  mov     r15d, 2
0x140033893  movzx   eax, word ptr [rcx+2]
0x140033897  mov     r14, r9
0x14003389a  movzx   esi, dx
0x14003389d  mov     r9, r8
0x1400338a0  add     r11d, esi
0x1400338a3  mov     rdi, rcx
0x1400338a6  add     r11, r15
0x1400338a9  cmp     rax, r11
0x1400338ac  jnb     short loc_140033926
0x1400338ae  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400338b4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400338bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400338c2  mov     ebx, 0C0000023h
0x1400338c7  setnz   r8b
0x1400338cb  and     dl, 40h
0x1400338ce  jnz     short loc_1400338D5
0x1400338d0  test    r8b, r8b
0x1400338d3  jz      short loc_140033922
0x1400338d5  mov     [rsp+88h+var_38], ebx
0x1400338d9  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400338e0  mov     [rsp+88h+var_40], 17Dh
0x1400338e8  mov     ecx, 20Eh
0x1400338ed  mov     [rsp+88h+var_48], r9
0x1400338f2  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400338f9  mov     [rsp+88h+var_50], r9
0x1400338fe  mov     r9, cs:WPP_GLOBAL_Control
0x140033905  mov     [rsp+88h+var_58], 0Dh
0x14003390c  mov     [rsp+88h+var_60], 0Eh
0x140033914  mov     [rsp+88h+var_68], r15b
0x140033919  mov     r9, [r9+40h]
0x14003391d  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140033922  mov     eax, ebx
0x140033924  jmp     short loc_140033993
0x140033926  mov     rcx, [rcx+8]; void *
0x14003392a  mov     r8, rsi; Size
0x14003392d  mov     rdx, r9; Src
0x140033930  call    memmove
0x140033935  mov     rax, [rdi+8]
0x140033939  mov     rdx, r14; Src
0x14003393c  movzx   r8d, [rsp+88h+arg_20]; Size
0x140033945  lea     rcx, [rax+2]
0x140033949  mov     word ptr [rax+rsi], 5Ch ; '\'
0x14003394f  add     rcx, rsi; void *
0x140033952  call    memmove
0x140033957  movzx   eax, si
0x14003395a  add     ax, [rsp+88h+arg_20]
0x140033962  cmp     ax, si
0x140033965  jnb     short loc_140033973
0x140033967  mov     word ptr [rdi], 0FFFFh
0x14003396c  mov     eax, 0C0000095h
0x140033971  jmp     short loc_140033993
0x140033973  add     ax, r15w
0x140033977  cmp     ax, r15w
0x14003397b  jb      short loc_140033982
0x14003397d  movzx   ecx, ax
0x140033980  jmp     short loc_140033987
0x140033982  mov     ecx, 0FFFFh
0x140033987  mov     [rdi], cx
0x14003398a  mov     eax, 0C0000095h
0x14003398f  sbb     ecx, ecx
0x140033991  and     eax, ecx
0x140033993  add     rsp, 60h
0x140033997  pop     r15
0x140033999  pop     r14
0x14003399b  pop     rdi
0x14003399c  pop     rsi
0x14003399d  pop     rbx
0x14003399e  retn
```
