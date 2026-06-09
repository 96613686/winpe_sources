# PrjfAddSubContext

- ea: `0x1400249dc`
- end: `0x140024ad1`
- name: `PrjfAddSubContext`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140028464`

## callees

- `0x14000be80`
- `0x14000d128`
- `0x1400249dc`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400249f5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400249f5`

## pseudocode

```c
__int64 __fastcall PrjfAddSubContext(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  _QWORD *v8; // rax
  int v9; // edx
  int v10; // r8d
  _QWORD *v11; // rbx
  unsigned int v12; // edi
  _QWORD *v13; // rax

  v8 = ExAllocateFromPagedLookasideList(&stru_14001A8C0);
  v11 = v8;
  if ( v8 )
  {
    memset(v8, 0, 0x50u);
    v11[9] = a5;
    v11[3] = a3;
    v11[4] = a2;
    v13 = *(_QWORD **)(a1 + 8);
    if ( *v13 != a1 )
      __fastfail(3u);
    *v11 = a1;
    v12 = 0;
    v11[1] = v13;
    *v13 = v11;
    *(_QWORD *)(a1 + 8) = v11;
  }
  else
  {
    v12 = -1073741670;
    if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = BYTE2(xmmword_14001A3D0) & 4;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        530,
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        18,
        21,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        148,
        154);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1400249dc  push    rbx
0x1400249de  push    rbp
0x1400249df  push    rsi
0x1400249e0  push    rdi
0x1400249e1  sub     rsp, 68h
0x1400249e5  mov     rsi, rcx
0x1400249e8  mov     rdi, r8
0x1400249eb  lea     rcx, stru_14001A8C0; Lookaside
0x1400249f2  mov     rbp, rdx
0x1400249f5  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400249fc  nop     dword ptr [rax+rax+00h]
0x140024a01  mov     rbx, rax
0x140024a04  test    rax, rax
0x140024a07  jnz     short loc_140024A83
0x140024a09  mov     edi, 0C000009Ah
0x140024a0e  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140024a14  lea     rax, WPP_RECORDER_INITIALIZED
0x140024a1b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024a22  setnz   r8b
0x140024a26  and     dl, 4
0x140024a29  jnz     short loc_140024A34
0x140024a2b  test    r8b, r8b
0x140024a2e  jz      loc_140024AC5
0x140024a34  mov     r9, cs:WPP_GLOBAL_Control
0x140024a3b  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140024a42  mov     [rsp+88h+var_38], edi
0x140024a46  mov     ecx, 212h
0x140024a4b  mov     [rsp+88h+var_40], 694h
0x140024a53  mov     [rsp+88h+var_48], rax
0x140024a58  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140024a5f  mov     r9, [r9+40h]
0x140024a63  mov     [rsp+88h+var_50], rax
0x140024a68  mov     [rsp+88h+var_58], 15h
0x140024a6f  mov     [rsp+88h+var_60], 12h
0x140024a77  mov     [rsp+88h+var_68], 2
0x140024a7c  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140024a81  jmp     short loc_140024AC5
0x140024a83  xor     edx, edx; Val
0x140024a85  mov     rcx, rbx; void *
0x140024a88  lea     r8d, [rdx+50h]; Size
0x140024a8c  call    memset
0x140024a91  mov     rax, [rsp+88h+arg_20]
0x140024a99  mov     [rbx+48h], rax
0x140024a9d  mov     [rbx+18h], rdi
0x140024aa1  mov     [rbx+20h], rbp
0x140024aa5  mov     rax, [rsi+8]
0x140024aa9  cmp     [rax], rsi
0x140024aac  jz      short loc_140024AB5
0x140024aae  mov     ecx, 3
0x140024ab3  int     29h; Win8: RtlFailFast(ecx)
0x140024ab5  mov     [rbx], rsi
0x140024ab8  xor     edi, edi
0x140024aba  mov     [rbx+8], rax
0x140024abe  mov     [rax], rbx
0x140024ac1  mov     [rsi+8], rbx
0x140024ac5  mov     eax, edi
0x140024ac7  add     rsp, 68h
0x140024acb  pop     rdi
0x140024acc  pop     rsi
0x140024acd  pop     rbp
0x140024ace  pop     rbx
0x140024acf  retn
```
