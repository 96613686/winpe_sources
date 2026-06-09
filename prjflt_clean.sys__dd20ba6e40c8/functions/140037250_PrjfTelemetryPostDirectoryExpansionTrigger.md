# PrjfTelemetryPostDirectoryExpansionTrigger

- ea: `0x140037250`
- end: `0x140037412`
- name: `PrjfTelemetryPostDirectoryExpansionTrigger`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002aa24`

## callees

- `0x140001008`
- `0x14000ba20`
- `0x140037250`

## pseudocode

```c
NTSTATUS __fastcall PrjfTelemetryPostDirectoryExpansionTrigger(int a1, __int64 a2, int a3, int a4, unsigned __int8 a5)
{
  void *v5; // r11
  int v8; // r9d
  __int64 v9; // r8
  __int64 v10; // r10
  unsigned __int16 v11; // dx
  NTSTATUS result; // eax
  void *v13; // rax
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+3Ch] [rbp-C4h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+60h] [rbp-A0h] BYREF
  int *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  int *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  _DWORD *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  void *v28; // [rsp+B0h] [rbp-50h]
  _DWORD v29[2]; // [rsp+B8h] [rbp-48h] BYREF
  int *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  __int64 *v32; // [rsp+D0h] [rbp-30h]
  __int64 v33; // [rsp+D8h] [rbp-28h]
  int *v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+E8h] [rbp-18h]
  int *v36; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  __int128 *v38; // [rsp+100h] [rbp+0h]
  __int64 v39; // [rsp+108h] [rbp+8h]

  v5 = 0;
  v20 = 0;
  if ( a4 < 0 )
  {
    v8 = 0;
    v9 = 0;
    v11 = 0;
  }
  else
  {
    v8 = *(_DWORD *)(a2 + 296);
    v9 = *(_QWORD *)(a2 + 288);
    v10 = *(_QWORD *)(*(_QWORD *)(a2 + 272) + 72LL);
    v11 = *(_WORD *)(v10 + 288);
    v5 = (void *)(v10 + 290);
  }
  result = dword_14001A068;
  if ( (unsigned int)dword_14001A068 > 5 )
  {
    result = qword_14001A078;
    if ( (qword_14001A078 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
      {
        v16 = v8;
        v19 = v9;
        v22 = &v14;
        v14 = a4;
        v24 = &v15;
        v26 = v29;
        v13 = v5;
        if ( !v5 )
          v13 = &unk_1400155F4;
        v28 = v13;
        v23 = 4;
        v15 = a1;
        v29[0] = v5 != 0 ? v11 : 0;
        v25 = 4;
        v30 = &v16;
        v27 = 2;
        v32 = &v19;
        v34 = &v17;
        v18 = a5;
        v36 = &v18;
        v38 = &v20;
        v29[1] = 0;
        v31 = 4;
        v33 = 8;
        v17 = a3;
        v35 = 4;
        v37 = 4;
        *(_QWORD *)&v20 = 0x1000000;
        v39 = 8;
        return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14001A068, byte_140016EB8, 0, 0, 0xBu, &v21);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037250  push    rbp
0x140037252  push    rbx
0x140037253  push    rsi
0x140037254  push    rdi
0x140037255  lea     rbp, [rsp-28h]
0x14003725a  sub     rsp, 128h
0x140037261  mov     rax, cs:__security_cookie
0x140037268  xor     rax, rsp
0x14003726b  mov     [rbp+40h+var_30], rax
0x14003726f  xor     r11d, r11d
0x140037272  xorps   xmm0, xmm0
0x140037275  mov     ebx, r9d
0x140037278  mov     edi, r8d
0x14003727b  mov     esi, ecx
0x14003727d  movups  [rsp+140h+var_F0], xmm0
0x140037282  test    r9d, r9d
0x140037285  js      short loc_1400372B1
0x140037287  mov     rax, [rdx+110h]
0x14003728e  mov     r9d, [rdx+128h]
0x140037295  mov     r8, [rdx+120h]
0x14003729c  mov     r10, [rax+48h]
0x1400372a0  movzx   edx, word ptr [r10+120h]
0x1400372a8  lea     r11, [r10+122h]
0x1400372af  jmp     short loc_1400372B9
0x1400372b1  xor     r9d, r9d
0x1400372b4  xor     r8d, r8d
0x1400372b7  xor     edx, edx
0x1400372b9  mov     eax, cs:dword_14001A068
0x1400372bf  cmp     eax, 5
0x1400372c2  jbe     loc_1400373F9
0x1400372c8  mov     rcx, cs:qword_14001A080
0x1400372cf  mov     r10, 400000000000h
0x1400372d9  mov     rax, cs:qword_14001A078
0x1400372e0  test    r10, rax
0x1400372e3  jz      loc_1400373F9
0x1400372e9  mov     rax, rcx
0x1400372ec  and     rax, r10
0x1400372ef  cmp     rax, rcx
0x1400372f2  jnz     loc_1400373F9
0x1400372f8  test    r11, r11
0x1400372fb  mov     [rsp+140h+var_108], r9d
0x140037300  lea     rax, [rsp+140h+var_110]
0x140037305  mov     [rsp+140h+var_F8], r8
0x14003730a  mov     [rbp+40h+var_C0], rax
0x14003730e  lea     rcx, dword_14001A068
0x140037315  lea     rax, [rsp+140h+var_10C]
0x14003731a  mov     [rsp+140h+var_110], ebx
0x14003731e  mov     [rbp+40h+var_B0], rax
0x140037322  lea     rax, [rbp+40h+var_88]
0x140037326  mov     [rbp+40h+var_A0], rax
0x14003732a  mov     rax, r11
0x14003732d  cmovz   rax, cs:off_140015518
0x140037335  neg     r11
0x140037338  mov     [rbp+40h+var_90], rax
0x14003733c  sbb     ax, ax
0x14003733f  mov     [rbp+40h+var_B8], 4
0x140037347  and     ax, dx
0x14003734a  mov     [rsp+140h+var_10C], esi
0x14003734e  movzx   eax, ax
0x140037351  lea     rdx, byte_140016EB8
0x140037358  mov     [rbp+40h+var_88], eax
0x14003735b  xor     r9d, r9d
0x14003735e  lea     rax, [rsp+140h+var_108]
0x140037363  mov     [rbp+40h+var_A8], 4
0x14003736b  mov     [rbp+40h+var_80], rax
0x14003736f  xor     r8d, r8d
0x140037372  lea     rax, [rsp+140h+var_F8]
0x140037377  mov     [rbp+40h+var_98], 2
0x14003737f  mov     [rbp+40h+var_70], rax
0x140037383  lea     rax, [rsp+140h+var_104]
0x140037388  mov     [rbp+40h+var_60], rax
0x14003738c  movzx   eax, [rbp+40h+arg_20]
0x140037390  mov     [rsp+140h+var_100], eax
0x140037394  lea     rax, [rsp+140h+var_100]
0x140037399  mov     [rbp+40h+var_50], rax
0x14003739d  lea     rax, [rsp+140h+var_F0]
0x1400373a2  mov     [rbp+40h+var_40], rax
0x1400373a6  lea     rax, [rsp+140h+var_E0]
0x1400373ab  mov     [rsp+140h+var_118], rax
0x1400373b0  mov     [rsp+140h+var_120], 0Bh
0x1400373b8  mov     [rbp+40h+var_84], 0
0x1400373bf  mov     [rbp+40h+var_78], 4
0x1400373c7  mov     [rbp+40h+var_68], 8
0x1400373cf  mov     [rsp+140h+var_104], edi
0x1400373d3  mov     [rbp+40h+var_58], 4
0x1400373db  mov     [rbp+40h+var_48], 4
0x1400373e3  mov     qword ptr [rsp+140h+var_F0], 1000000h
0x1400373ec  mov     [rbp+40h+var_38], 8
0x1400373f4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400373f9  mov     rcx, [rbp+40h+var_30]
0x1400373fd  xor     rcx, rsp; StackCookie
0x140037400  call    __security_check_cookie
0x140037405  add     rsp, 128h
0x14003740c  pop     rdi
0x14003740d  pop     rsi
0x14003740e  pop     rbx
0x14003740f  pop     rbp
0x140037410  retn
```
