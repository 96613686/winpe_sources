# DafCreateAssociationSetContextForAep

- ea: `0x180008a60`
- end: `0x180008b2f`
- name: `DafCreateAssociationSetContextForAep`
- size: `207`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct _DAC_CLIENT_CONTEXT **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002284`
- `0x180002f10`
- `0x180008a60`

## pseudocode

```c
__int64 __fastcall DafCreateAssociationSetContextForAep(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        RPC_BINDING_HANDLE **a6)
{
  _DWORD v11[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v12; // [rsp+28h] [rbp-60h]
  __int64 v13; // [rsp+30h] [rbp-58h]
  int v14; // [rsp+38h] [rbp-50h]
  int v15; // [rsp+3Ch] [rbp-4Ch]
  __int64 v16; // [rsp+40h] [rbp-48h]
  __int64 v17; // [rsp+48h] [rbp-40h]
  __int128 v18; // [rsp+50h] [rbp-38h]

  v11[1] = 0;
  v18 = 0;
  v17 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( !a1 || *(_WORD *)(a1 + 8) != 3503 || a4 && !a5 || !a6 )
    return 2147942487LL;
  v16 = a5;
  *a6 = 0;
  v12 = a1 + 56;
  v11[0] = 3;
  v15 = a4;
  v14 = a3;
  v13 = a2;
  return CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)v11, a6);
}

```

## disassembly

```asm
0x180008a60  push    rbx
0x180008a62  push    rbp
0x180008a63  push    rsi
0x180008a64  push    rdi
0x180008a65  sub     rsp, 68h
0x180008a69  xorps   xmm0, xmm0
0x180008a6c  mov     [rsp+88h+var_64], 0
0x180008a74  movdqa  [rsp+88h+var_38], xmm0
0x180008a7a  mov     edi, r9d
0x180008a7d  mov     esi, r8d
0x180008a80  mov     [rsp+88h+var_40], 0
0x180008a89  mov     rbp, rdx
0x180008a8c  mov     rbx, rcx
0x180008a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a96  lea     rax, WPP_GLOBAL_Control
0x180008a9d  cmp     rcx, rax
0x180008aa0  jz      short loc_180008ABD
0x180008aa2  cmp     byte ptr [rcx+19h], 4
0x180008aa6  jb      short loc_180008ABD
0x180008aa8  mov     rcx, [rcx+10h]
0x180008aac  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x180008ab3  mov     edx, 1Dh
0x180008ab8  call    WPP_SF_s
0x180008abd  test    rbx, rbx
0x180008ac0  jz      short loc_180008B21
0x180008ac2  mov     eax, 0DAFh
0x180008ac7  cmp     [rbx+8], ax
0x180008acb  jnz     short loc_180008B21
0x180008acd  mov     rax, [rsp+88h+arg_20]
0x180008ad5  test    edi, edi
0x180008ad7  jz      short loc_180008ADE
0x180008ad9  test    rax, rax
0x180008adc  jz      short loc_180008B21
0x180008ade  mov     rdx, [rsp+88h+arg_28]; struct _DAC_CLIENT_CONTEXT **
0x180008ae6  test    rdx, rdx
0x180008ae9  jz      short loc_180008B21
0x180008aeb  mov     [rsp+88h+var_48], rax
0x180008af0  lea     rcx, [rsp+88h+var_68]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x180008af5  lea     rax, [rbx+38h]
0x180008af9  mov     qword ptr [rdx], 0
0x180008b00  mov     [rsp+88h+var_60], rax
0x180008b05  mov     [rsp+88h+var_68], 3
0x180008b0d  mov     [rsp+88h+var_4C], edi
0x180008b11  mov     [rsp+88h+var_50], esi
0x180008b15  mov     [rsp+88h+var_58], rbp
0x180008b1a  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x180008b1f  jmp     short loc_180008B26
0x180008b21  mov     eax, 80070057h
0x180008b26  add     rsp, 68h
0x180008b2a  pop     rdi
0x180008b2b  pop     rsi
0x180008b2c  pop     rbp
0x180008b2d  pop     rbx
0x180008b2e  retn
```
