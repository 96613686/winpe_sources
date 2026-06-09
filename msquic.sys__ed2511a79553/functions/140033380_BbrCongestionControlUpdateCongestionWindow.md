# BbrCongestionControlUpdateCongestionWindow

- ea: `0x140033380`
- end: `0x14003346d`
- name: `BbrCongestionControlUpdateCongestionWindow`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140032950`

## callees

- `0x140032330`
- `0x140033100`
- `0x140033380`
- `0x1400335c8`
- `0x140033674`

## pseudocode

```c
void __fastcall BbrCongestionControlUpdateCongestionWindow(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v6; // ax
  unsigned __int16 v7; // bp
  __int64 v8; // r8
  unsigned __int64 TargetCwnd; // r9
  char v10; // r10
  unsigned int v11; // ecx
  _QWORD v12[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_DWORD *)(a1 + 220) == 3 )
    return;
  v6 = 28;
  if ( *(_WORD *)(a1 - 1792) != 2 )
    v6 = 48;
  v7 = *(_WORD *)(a1 - 1832) - v6;
  BbrCongestionControlSetSendQuantum(a1);
  TargetCwnd = (unsigned int)BbrCongestionControlGetTargetCwnd(a1, *(unsigned int *)(a1 + 176));
  v10 = *(_BYTE *)(a1 + 136) & 1;
  if ( v10 )
  {
    v12[0] = 0;
    if ( (int)QuicSlidingWindowExtremumGet(a1 + 272, v12, v8, TargetCwnd) >= 0 )
      TargetCwnd += v12[0];
  }
  v11 = *(_DWORD *)(a1 + 144);
  if ( v10 )
  {
    if ( TargetCwnd < a3 + (unsigned __int64)v11 )
    {
      v11 = TargetCwnd;
      goto LABEL_13;
    }
LABEL_12:
    v11 += a3;
    goto LABEL_13;
  }
  if ( v11 < TargetCwnd || a2 < *(unsigned int *)(a1 + 148) )
    goto LABEL_12;
LABEL_13:
  if ( v11 <= 4 * (unsigned int)v7 )
    v11 = 4 * v7;
  *(_DWORD *)(a1 + 144) = v11;
  QuicConnLogBbr(a1 - 2168);
}

```

## disassembly

```asm
0x140033380  mov     [rsp+arg_0], rbx
0x140033385  mov     [rsp+arg_8], rbp
0x14003338a  mov     [rsp+arg_10], rsi
0x14003338f  push    rdi
0x140033390  sub     rsp, 30h
0x140033394  cmp     dword ptr [rcx+0DCh], 3
0x14003339b  mov     rdi, r8
0x14003339e  mov     rsi, rdx
0x1400333a1  mov     rbx, rcx
0x1400333a4  jz      loc_140033457
0x1400333aa  cmp     word ptr [rbx-700h], 2
0x1400333b2  mov     eax, 1Ch
0x1400333b7  movzx   ebp, word ptr [rbx-728h]
0x1400333be  lea     ecx, [rax+14h]
0x1400333c1  cmovnz  ax, cx
0x1400333c5  mov     rcx, rbx
0x1400333c8  sub     bp, ax
0x1400333cb  call    BbrCongestionControlSetSendQuantum
0x1400333d0  mov     edx, [rbx+0B0h]
0x1400333d6  mov     rcx, rbx
0x1400333d9  call    BbrCongestionControlGetTargetCwnd
0x1400333de  mov     r10b, [rbx+88h]
0x1400333e5  mov     r9d, eax
0x1400333e8  and     r10b, 1
0x1400333ec  jz      short loc_14003340E
0x1400333ee  and     [rsp+38h+var_18], 0
0x1400333f4  lea     rcx, [rbx+110h]
0x1400333fb  lea     rdx, [rsp+38h+var_18]
0x140033400  call    QuicSlidingWindowExtremumGet
0x140033405  test    eax, eax
0x140033407  js      short loc_14003340E
0x140033409  add     r9, [rsp+38h+var_18]
0x14003340e  mov     ecx, [rbx+90h]
0x140033414  movzx   edx, bp
0x140033417  mov     eax, ecx
0x140033419  shl     edx, 2
0x14003341c  test    r10b, r10b
0x14003341f  jz      short loc_14003342E
0x140033421  add     rax, rdi
0x140033424  cmp     r9, rax
0x140033427  jnb     short loc_14003343E
0x140033429  mov     ecx, r9d
0x14003342c  jmp     short loc_140033440
0x14003342e  cmp     rax, r9
0x140033431  jb      short loc_14003343E
0x140033433  mov     eax, [rbx+94h]
0x140033439  cmp     rsi, rax
0x14003343c  jnb     short loc_140033440
0x14003343e  add     ecx, edi
0x140033440  cmp     ecx, edx
0x140033442  cmovbe  ecx, edx
0x140033445  mov     [rbx+90h], ecx
0x14003344b  lea     rcx, [rbx-878h]
0x140033452  call    QuicConnLogBbr
0x140033457  mov     rbx, [rsp+38h+arg_0]
0x14003345c  mov     rbp, [rsp+38h+arg_8]
0x140033461  mov     rsi, [rsp+38h+arg_10]
0x140033466  add     rsp, 30h
0x14003346a  pop     rdi
0x14003346b  retn
```
