# McTemplateK0jqssssduuuuuqbr12u_EtwWriteTransfer

- ea: `0x140007000`
- end: `0x140007223`
- name: `McTemplateK0jqssssduuuuuqbr12u_EtwWriteTransfer`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400066cc`

## callees

- `0x1400062a0`
- `0x140007000`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jqssssduuuuuqbr12u_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        __int64 a4,
        char a5,
        const char *a6,
        const char *a7,
        const char *a8,
        const char *a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        int a16,
        __int64 a17,
        char a18)
{
  const char *v19; // rdx
  __int64 v21; // rax
  int v22; // r8d
  __int64 v23; // rcx
  int v24; // ecx
  const char *v25; // rdx
  __int64 v26; // rcx
  int v27; // ecx
  const char *v28; // rdx
  __int64 v29; // rcx
  int v30; // ecx
  const char *v31; // rcx
  bool v32; // zf
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  char *v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+58h] [rbp-A8h]
  const char *v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+6Ch] [rbp-94h]
  const char *v42; // [rsp+70h] [rbp-90h]
  int v43; // [rsp+78h] [rbp-88h]
  int v44; // [rsp+7Ch] [rbp-84h]
  const char *v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+88h] [rbp-78h]
  int v47; // [rsp+8Ch] [rbp-74h]
  const char *v48; // [rsp+90h] [rbp-70h]
  int v49; // [rsp+98h] [rbp-68h]
  int v50; // [rsp+9Ch] [rbp-64h]
  char *v51; // [rsp+A0h] [rbp-60h]
  __int64 v52; // [rsp+A8h] [rbp-58h]
  char *v53; // [rsp+B0h] [rbp-50h]
  __int64 v54; // [rsp+B8h] [rbp-48h]
  char *v55; // [rsp+C0h] [rbp-40h]
  __int64 v56; // [rsp+C8h] [rbp-38h]
  char *v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  char *v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  char *v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F8h] [rbp-8h]
  int *v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h]
  __int64 v65; // [rsp+110h] [rbp+10h]
  int v66; // [rsp+118h] [rbp+18h]
  int v67; // [rsp+11Ch] [rbp+1Ch]
  char *v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]

  v35 = a4;
  v37 = &a5;
  v19 = a6;
  v36 = 16;
  v38 = 4;
  v21 = -1;
  v22 = 5;
  if ( a6 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a6[v23] );
    v24 = v23 + 1;
  }
  else
  {
    v24 = 5;
  }
  v40 = v24;
  v41 = 0;
  if ( !a6 )
    v19 = "NULL";
  v39 = v19;
  v25 = a7;
  if ( a7 )
  {
    v26 = -1;
    do
      ++v26;
    while ( a7[v26] );
    v27 = v26 + 1;
  }
  else
  {
    v27 = 5;
  }
  v43 = v27;
  v44 = 0;
  if ( !a7 )
    v25 = "NULL";
  v42 = v25;
  v28 = a8;
  if ( a8 )
  {
    v29 = -1;
    do
      ++v29;
    while ( a8[v29] );
    v30 = v29 + 1;
  }
  else
  {
    v30 = 5;
  }
  v46 = v30;
  v31 = a9;
  if ( !a8 )
    v28 = "NULL";
  v47 = 0;
  v45 = v28;
  v32 = a9 == 0;
  if ( a9 )
  {
    do
      v32 = a9[++v21] == 0;
    while ( !v32 );
    v22 = v21 + 1;
    v32 = a9 == 0;
  }
  v49 = v22;
  v51 = &a10;
  if ( v32 )
    v31 = "NULL";
  v50 = 0;
  v53 = &a11;
  v67 = 0;
  v55 = &a12;
  v48 = v31;
  v57 = &a13;
  v52 = 4;
  v59 = &a14;
  v61 = &a15;
  v63 = &a16;
  v65 = a17;
  v66 = a16;
  v68 = &a18;
  v54 = 1;
  v56 = 1;
  v58 = 1;
  v60 = 1;
  v62 = 1;
  v64 = 4;
  v69 = 1;
  return McGenEventWrite_EtwWriteTransfer((__int64)v31, a2, a3, 0x10u, &v34);
}

```

## disassembly

```asm
0x140007000  mov     [rsp-8+arg_0], rbx
0x140007005  push    rbp
0x140007006  lea     rbp, [rsp-40h]
0x14000700b  sub     rsp, 140h
0x140007012  mov     rax, cs:__security_cookie
0x140007019  xor     rax, rsp
0x14000701c  mov     [rbp+40h+var_10], rax
0x140007020  lea     rax, [rbp+40h+arg_20]
0x140007024  mov     [rsp+140h+var_100], r9
0x140007029  mov     r10, rdx
0x14000702c  mov     [rsp+140h+var_F0], rax
0x140007031  mov     rdx, [rbp+40h+arg_28]
0x140007035  xor     r9d, r9d
0x140007038  mov     [rsp+140h+var_F8], 10h
0x140007041  mov     r11, r8
0x140007044  mov     [rsp+140h+var_E8], 4
0x14000704d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140007054  mov     r8d, 5
0x14000705a  test    rdx, rdx
0x14000705d  jz      loc_14000721B
0x140007063  mov     rcx, rax
0x140007066  inc     rcx
0x140007069  cmp     [rdx+rcx], r9b
0x14000706d  jnz     short loc_140007066
0x14000706f  inc     ecx
0x140007071  test    rdx, rdx
0x140007074  mov     [rsp+140h+var_D8], ecx
0x140007078  lea     rbx, aNull; "NULL"
0x14000707f  mov     [rsp+140h+var_D4], r9d
0x140007084  cmovz   rdx, rbx
0x140007088  mov     [rsp+140h+var_E0], rdx
0x14000708d  mov     rdx, [rbp+40h+arg_30]
0x140007094  test    rdx, rdx
0x140007097  jz      loc_14000720B
0x14000709d  mov     rcx, rax
0x1400070a0  inc     rcx
0x1400070a3  cmp     [rdx+rcx], r9b
0x1400070a7  jnz     short loc_1400070A0
0x1400070a9  inc     ecx
0x1400070ab  test    rdx, rdx
0x1400070ae  mov     [rsp+140h+var_C8], ecx
0x1400070b2  mov     [rsp+140h+var_C4], r9d
0x1400070b7  cmovz   rdx, rbx
0x1400070bb  mov     [rsp+140h+var_D0], rdx
0x1400070c0  mov     rdx, [rbp+40h+arg_38]
0x1400070c7  test    rdx, rdx
0x1400070ca  jz      loc_140007213
0x1400070d0  mov     rcx, rax
0x1400070d3  inc     rcx
0x1400070d6  cmp     [rdx+rcx], r9b
0x1400070da  jnz     short loc_1400070D3
0x1400070dc  inc     ecx
0x1400070de  test    rdx, rdx
0x1400070e1  mov     [rbp+40h+var_B8], ecx
0x1400070e4  mov     rcx, [rbp+40h+arg_40]
0x1400070eb  cmovz   rdx, rbx
0x1400070ef  mov     [rbp+40h+var_B4], r9d
0x1400070f3  mov     [rbp+40h+var_C0], rdx
0x1400070f7  test    rcx, rcx
0x1400070fa  jz      short loc_140007112
0x1400070fc  nop     dword ptr [rax+00h]
0x140007100  cmp     [rcx+rax+1], r9b
0x140007105  lea     rax, [rax+1]
0x140007109  jnz     short loc_140007100
0x14000710b  lea     r8d, [rax+1]
0x14000710f  test    rcx, rcx
0x140007112  lea     rax, [rbp+40h+arg_48]
0x140007119  mov     [rbp+40h+var_A8], r8d
0x14000711d  mov     [rbp+40h+var_A0], rax
0x140007121  cmovz   rcx, rbx
0x140007125  lea     rax, [rbp+40h+arg_50]
0x14000712c  mov     [rbp+40h+var_A4], r9d
0x140007130  mov     [rbp+40h+var_90], rax
0x140007134  mov     r8, r11
0x140007137  lea     rax, [rbp+40h+arg_58]
0x14000713e  mov     [rbp+40h+var_24], r9d
0x140007142  mov     [rbp+40h+var_80], rax
0x140007146  mov     r9d, 10h
0x14000714c  lea     rax, [rbp+40h+arg_60]
0x140007153  mov     [rbp+40h+var_B0], rcx
0x140007157  mov     [rbp+40h+var_70], rax
0x14000715b  mov     rdx, r10
0x14000715e  lea     rax, [rbp+40h+arg_68]
0x140007165  mov     [rbp+40h+var_98], 4
0x14000716d  mov     [rbp+40h+var_60], rax
0x140007171  lea     rax, [rbp+40h+arg_70]
0x140007178  mov     [rbp+40h+var_50], rax
0x14000717c  lea     rax, [rbp+40h+arg_78]
0x140007183  mov     [rbp+40h+var_40], rax
0x140007187  mov     rax, [rbp+40h+arg_80]
0x14000718e  mov     [rbp+40h+var_30], rax
0x140007192  mov     eax, [rbp+40h+arg_78]
0x140007198  mov     [rbp+40h+var_28], eax
0x14000719b  lea     rax, [rbp+40h+arg_88]
0x1400071a2  mov     [rbp+40h+var_20], rax
0x1400071a6  lea     rax, [rsp+140h+var_110]
0x1400071ab  mov     [rsp+140h+var_120], rax
0x1400071b0  mov     [rbp+40h+var_88], 1
0x1400071b8  mov     [rbp+40h+var_78], 1
0x1400071c0  mov     [rbp+40h+var_68], 1
0x1400071c8  mov     [rbp+40h+var_58], 1
0x1400071d0  mov     [rbp+40h+var_48], 1
0x1400071d8  mov     [rbp+40h+var_38], 4
0x1400071e0  mov     [rbp+40h+var_18], 1
0x1400071e8  call    McGenEventWrite_EtwWriteTransfer
0x1400071ed  mov     rcx, [rbp+40h+var_10]
0x1400071f1  xor     rcx, rsp; StackCookie
0x1400071f4  call    __security_check_cookie
0x1400071f9  mov     rbx, [rsp+140h+arg_0]
0x140007201  add     rsp, 140h
0x140007208  pop     rbp
0x140007209  retn
0x14000720b  mov     ecx, r8d
0x14000720e  jmp     loc_1400070AB
0x140007213  mov     ecx, r8d
0x140007216  jmp     loc_1400070DE
0x14000721b  mov     ecx, r8d
0x14000721e  jmp     loc_140007071
```
